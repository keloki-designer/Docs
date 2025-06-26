Для персонализации сообщений в текст шаблона вы можете добавить макросы.

Для настройки пользовательских макросов необходимо выполнить следующие действия:

- Перейти в конфигуратор и создать исходный код в пользовательском пакете

![](https://samarasoft.com/wp-content/uploads/2023/11/%D1%81%D0%BE%D0%B7%D0%B4%D0%B0%D0%BD%D0%B8%D0%B5-%D0%BF%D0%BE%D0%BB%D1%8C%D0%B7%D0%BE%D0%B2%D0%B0%D1%82%D0%B5%D0%BB%D1%8C%D1%81%D0%BA%D0%B8%D1%85-%D0%BC%D0%B0%D0%BA%D1%80%D0%BE%D1%81%D0%BE%D0%B21-1024x415.png)

- В исходном коде должен содержаться класс, реализующий интерфейс IMacros

```
using Samarasoft.Sender.Macros;
using BPMSoft.Core;
using System;

namespace BPMSoft.Configuration
{
  public class FirstMacros : IMacros
  {
    public FirstMacros(UserConnection userConnection)
    {
      UserConnection = userConnection;
    }
    
    public UserConnection UserConnection
    {
      get;
    }
    
    public string GetMacrosValue(Guid id, object arguments)
    {
      return $"UserConnectionContactId: {UserConnection.CurrentUser.ContactId} id: {id.ToString()}; arguments: {arguments};";
    }
  }
}
```

В классе должен быть реализован метод **GetMacrosValue**, возвращающий необходимое значение

- Вызов макроса просходит стандартным способом [#@Invoke.название класса в исходном коде#]

![](https://samarasoft.com/wp-content/uploads/2023/11/%D1%81%D0%BE%D0%B7%D0%B4%D0%B0%D0%BD%D0%B8%D0%B5-%D0%BF%D0%BE%D0%BB%D1%8C%D0%B7%D0%BE%D0%B2%D0%B0%D1%82%D0%B5%D0%BB%D1%8C%D1%81%D0%BA%D0%B8%D1%85-%D0%BC%D0%B0%D0%BA%D1%80%D0%BE%D1%81%D0%BE%D0%B22-1024x168.png)

В итоге будет получено сообщение вида:  
UserConnectionContactid: полученное значение id: полученное значение; arguments:

**Например**: необходимо прибавлять к дате рождения контакта N кол-во дней

- Добавим класс и назовем его BirthDateMacros

- добавим метод получения даты рождения контакта

```
private DateTime GetBirthDate(Guid contactId)
        {
            var select = (Select)new Select(UserConnection).Column("BirthDate")
                .From("Contact")
                .Where("Id")
                .IsEqual(Column.Parameter(contactId));
            select.SpecifyNoLockHints();
            return select.ExecuteScalar<DateTime>();
        }
```

*Для выполнения запросов к базе необходимо добавить оператор using BPMSoft.Core.DB;

- Далее в методе GetMacrosValue получаем значение даты рождения и прибавляем указанное в параметре кол-во дней

```
var birthDate = GetBirthDate(id);
            if (birthDate != DateTime.MinValue)
            {
                var days = Convert.ToInt32(arguments.ToString());
                birthDate = birthDate.AddDays(days);
                return birthDate.ToString("d");
            }

            return "";
```

- Для вызова макроса будет использовать [#@Invoke.BirthDateMacros(кол-во дней)#]

## **Пример**[](https://samarasoft.com/docs/sms-sender/create-template-sms-messages/create-custom-macros/#%D0%BF%D1%80%D0%B8%D0%BC%D0%B5%D1%80)

- Добавим класс FirstMacros который будет выполнять расчет бонусного баланса контакта по определеному типу бонусных баллов

```
using Samarasoft.Sender.Macros;
using BPMSoft.Core;
using System;
using Samarasoft.Loyalty.BpmOnline.Services.BonusBalance;
using Samarasoft.Loyalty.BpmOnline;

namespace BPMSoft.Configuration
{
  public class FirstMacros : IMacros
  {
    public FirstMacros(UserConnection userConnection)
    {
      UserConnection = userConnection;
    }
    
    public UserConnection UserConnection
    {
      get;
    }
    
    public string GetMacrosValue(Guid id, object arguments)
    {
    	var balanceService = Startup.ServiceProvider.GetInstance<ContactBonusBalanceService>();
    	var balance = balanceService.GetBonusBalanceByContactId(id, new Guid("AA84565E-A343-4DBA-8E19-6E31EBD92AA9"), DateTime.UtcNow);
		return balance.Balance.ToString();
    }
  }
}
```

- Создаем рассылку в которой используем контакт «Парфенов Никита» в аудитории

![](https://samarasoft.com/wp-content/uploads/2023/11/%D1%81%D0%BE%D0%B7%D0%B4%D0%B0%D0%BD%D0%B8%D0%B5-%D0%BF%D0%BE%D0%BB%D1%8C%D0%B7%D0%BE%D0%B2%D0%B0%D1%82%D0%B5%D0%BB%D1%8C%D1%81%D0%BA%D0%B8%D1%85-%D0%BC%D0%B0%D0%BA%D1%80%D0%BE%D1%81%D0%BE%D0%B23-1024x575.png)

Добавим вызов макроса, где:

- [ #Contact.Name# ] возвращает имя контакта из аудитории рассылки
- [#@Invoke.FirstMacros#] возвращает количество бонусного баланса по определенному типу для контакта из аудитории рассылки

![](https://samarasoft.com/wp-content/uploads/2023/11/%D1%81%D0%BE%D0%B7%D0%B4%D0%B0%D0%BD%D0%B8%D0%B5-%D0%BF%D0%BE%D0%BB%D1%8C%D0%B7%D0%BE%D0%B2%D0%B0%D1%82%D0%B5%D0%BB%D1%8C%D1%81%D0%BA%D0%B8%D1%85-%D0%BC%D0%B0%D0%BA%D1%80%D0%BE%D1%81%D0%BE%D0%B24-1024x168.png)

В итоге получаем сообщение:  
«Никита Парфенов, Ваш бонусный баланс = 150»

**Примечание:** макрос может не примениться при использовании перегруженного метода в коде.