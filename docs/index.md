# Добро пожаловать в документацию BPMSoft!

Это главная страница с полезными элементами и навигацией.

---

##  Майнд-карта (Mermaid)

<div class="mermaid">
graph TD
    A[Идея] --> B[Разработка]
    B --> C[Документация]
    C --> D[Готово!]
</div>

---

##  Холст (Canvas)

<canvas id="myCanvas" width="400" height="200" style="border:2px solid #000000; border-radius:8px;"></canvas>

<script>
window.addEventListener('load', () => {
  const canvas = document.getElementById("myCanvas");
  const ctx = canvas.getContext("2d");

  // Красный прямоугольник
  ctx.fillStyle = "#FF0000";
  ctx.fillRect(20, 20, 150, 100);

  // Синий круг
  ctx.beginPath();
  ctx.arc(300, 100, 50, 0, 2 * Math.PI);
  ctx.fillStyle = "#0000FF";
  ctx.fill();

  // Текст
  ctx.font = "20px Arial";
  ctx.fillStyle = "#000000";
  ctx.fillText("Canvas Example", 120, 180);
});
</script>

---

##  Галерея с лайтбоксом (Glightbox)

Нажмите на любую картинку для увеличения:

<div style="display: flex; gap: 10px; flex-wrap: wrap;">
  <a href="https://placekitten.com/800/600" class="glightbox" data-glightbox="title: Милый котик; description: Вот такой котик.">
    <img src="https://placekitten.com/200/150" alt="Котик" style="border-radius:8px; cursor:pointer;"/>
  </a>
  <a href="https://placebear.com/800/600" class="glightbox" data-glightbox="title: Медведь; description: Медведь в природе.">
    <img src="https://placebear.com/200/150" alt="Медведь" style="border-radius:8px; cursor:pointer;"/>
  </a>
</div>

---

##  Таблица с данными

| Имя            | Роль           | Статус    |
| -------------- | -------------- | --------- |
| Егор           | Аналитик       | Активен   |
| Анна           | Разработчик    | В отпуске |
| Иван           | Тестировщик    | Активен   |

---

##  Внимание!

> **Важно:** Не забудьте обновить конфигурацию перед сборкой.

---

##  Полезный совет

> Используйте горячие клавиши Material для быстрого доступа:
> - `Ctrl + P` — поиск страниц
> - `Ctrl + Shift + F` — поиск по всему сайту

---

## Макросы

Текущая дата: {{ now().strftime('%d-%m-%Y') }}

{% set version = "1.2.3" %}
Текущая версия документации: **{{ version }}**

---

##  Кнопки

<button onclick="alert('Вы нажали кнопку!')" style="padding: 8px 16px; background:#2196F3; color:#fff; border:none; border-radius:4px; cursor:pointer;">
  Нажми меня
</button>

---

##  Поиск

Используйте поиск в верхнем меню для быстрого перехода.

---

##  Навигация по разделам

### Сервис отправки SMS и Viber сообщений 2.0 для BPMSoft

- [Чейнджлог](Servis_otpravki_SMS_i_Viber_soobschenij_2.0_dlja_BPMSoft/Changelog.md)
- [Элемент маркетинговой кампании](Servis_otpravki_SMS_i_Viber_soobschenij_2.0_dlja_BPMSoft/Element_marketingovoj_kampanii_SMS-rassylka.md)
- [Хронология SMS сообщений](Servis_otpravki_SMS_i_Viber_soobschenij_2.0_dlja_BPMSoft/Hronologija_SMS-soobschenij.md)

#### История отправки SMS сообщений

- [История контакта](Servis_otpravki_SMS_i_Viber_soobschenij_2.0_dlja_BPMSoft/Istorija_otpravki_SMS-soobschenij/Istorija_SMS-soobschenij_kontakta.md)
- [История контрагента](Servis_otpravki_SMS_i_Viber_soobschenij_2.0_dlja_BPMSoft/Istorija_otpravki_SMS-soobschenij/Istorija_SMS-soobschenij_kontragenta.md)
- [История отправки](Servis_otpravki_SMS_i_Viber_soobschenij_2.0_dlja_BPMSoft/Istorija_otpravki_SMS-soobschenij/Istorija_otpravki_SMS-soobschenij.md)

- [Настройка конфигов](Servis_otpravki_SMS_i_Viber_soobschenij_2.0_dlja_BPMSoft/Nastrojka_konfigov.md)
- [Настройка ограничения количества SMS рассылок](Servis_otpravki_SMS_i_Viber_soobschenij_2.0_dlja_BPMSoft/Nastrojka_ogranichenija_kolichestva_SMS_rassylok.md)

#### Настройка отображения разделов Сервиса

- [Добавление рабочего места](Servis_otpravki_SMS_i_Viber_soobschenij_2.0_dlja_BPMSoft/Nastrojka_otobrazhenija_razdelov_Servisa_otpravki_SMS_i_Viber_soobschenij_2.0_dlja_BPMSoft/Dobavlenie_rabochego_mesta.md)
- [Настройка рабочего места](Servis_otpravki_SMS_i_Viber_soobschenij_2.0_dlja_BPMSoft/Nastrojka_otobrazhenija_razdelov_Servisa_otpravki_SMS_i_Viber_soobschenij_2.0_dlja_BPMSoft/Nastrojka_rabochego_mesta.md)
- [SMSVIB 1](Servis_otpravki_SMS_i_Viber_soobschenij_2.0_dlja_BPMSoft/Nastrojka_otobrazhenija_razdelov_Servisa_otpravki_SMS_i_Viber_soobschenij_2.0_dlja_BPMSoft/SMSVIB_1.MD)

- [Настройка подключения к SMS провайдеру](Servis_otpravki_SMS_i_Viber_soobschenij_2.0_dlja_BPMSoft/Nastrojka_podkljuchenija_k_SMS-provajderu.md)

#### Отправка SMS сообщений из разделов системы

- [Операция Возможность отправки SMS](Servis_otpravki_SMS_i_Viber_soobschenij_2.0_dlja_BPMSoft/Otpravka_SMS-soobschenija_iz_razdelov_sistemy/Operatsija_Vozmozhnost__otpravki_SMS.md)
- [Отправка SMS из панели действий](Servis_otpravki_SMS_i_Viber_soobschenij_2.0_dlja_BPMSoft/Otpravka_SMS-soobschenija_iz_paneli_dejstvij.md)
- [Отправка SMS из разделов системы](Servis_otpravki_SMS_i_Viber_soobschenij_2.0_dlja_BPMSoft/Otpravka_SMS-soobschenija_iz_razdelov_sistemy.md)
- [Выбор шаблона SMS сообщения](Servis_otpravki_SMS_i_Viber_soobschenij_2.0_dlja_BPMSoft/Vybor_shablona_SMS-soobschenija.md)

- [Подключение BPMsoft к Сервису](Servis_otpravki_SMS_i_Viber_soobschenij_2.0_dlja_BPMSoft/Podkljuchenie_BPMsoft_k_Servisu_otpravki_SMS_i_Viber_soobschenij_2.0_dlja_BPMSoft.md)

#### SMS рассылка

- [Аудитория рассылки](Servis_otpravki_SMS_i_Viber_soobschenij_2.0_dlja_BPMSoft/SMS-rassylka/Auditorija_rassylki.md)
- [Как остановить SMS рассылку](Servis_otpravki_SMS_i_Viber_soobschenij_2.0_dlja_BPMSoft/SMS-rassylka/Kak_ostanovit__SMS-rassylku.md)
- [Как выполнить тестовую отправку SMS сообщения](Servis_otpravki_SMS_i_Viber_soobschenij_2.0_dlja_BPMSoft/SMS-rassylka/Kak_vypolnit__testovuju_otpravku_SMS-soobschenija.md)
- [Как запустить SMS рассылку](Servis_otpravki_SMS_i_Viber_soobschenij_2.0_dlja_BPMSoft/SMS-rassylka/Kak_zapustit__SMS-rassylku.md)
- [SMS рассылок](Servis_otpravki_SMS_i_Viber_soobschenij_2.0_dlja_BPMSoft/SMS-rassylka/SMS_rassylok.md)
- [Создание SMS рассылки](Servis_otpravki_SMS_i_Viber_soobschenij_2.0_dlja_BPMSoft/SMS-rassylka/Sozdanie_SMS-rassylki.md)
- [Статистика SMS рассылок](Servis_otpravki_SMS_i_Viber_soobschenij_2.0_dlja_BPMSoft/SMS-rassylka/Statistika_SMS-rassylok.md)

- [Сервис отправки SMS и Viber](Servis_otpravki_SMS_i_Viber_soobschenij_2.0_dlja_BPMSoft/Servis_otpravki_SMS_i_Viber_soobschenij_2.0_dlja_BPMSoft.md)

#### Создание шаблона SMS сообщений

- [Добавление макросов](Servis_otpravki_SMS_i_Viber_soobschenij_2.0_dlja_BPMSoft/Sozdanie_shablona_SMS-soobschenij/Dobavlenie_makrosov.md)
- [Создание пользовательских макросов](Servis_otpravki_SMS_i_Viber_soobschenij_2.0_dlja_BPMSoft/Sozdanie_shablona_SMS-soobschenij/Sozdanie_pol_zovatel_skih_makrosov.md)
- [Создание шаблона SMS сообщения](Servis_otpravki_SMS_i_Viber_soobschenij_2.0_dlja_BPMSoft/Sozdanie_shablona_SMS-soobschenij/Sozdanie_shablona_SMS-soobschenij.md)

- [Технические требования](Servis_otpravki_SMS_i_Viber_soobschenij_2.0_dlja_BPMSoft/Tehnicheskie_trebovanija.md)
- [Триггерная SMS рассылка](Servis_otpravki_SMS_i_Viber_soobschenij_2.0_dlja_BPMSoft/Triggernaja_SMS-rassylka.md)

#### Установка

- [Установка BPMsoft](Servis_otpravki_SMS_i_Viber_soobschenij_2.0_dlja_BPMSoft/Ustanovka_BPMsoft.md)
- [Установка Docker](Servis_otpravki_SMS_i_Viber_soobschenij_2.0_dlja_BPMSoft/Ustanovka_Docker.md)
- [Установка PostgreSQL](Servis_otpravki_SMS_i_Viber_soobschenij_2.0_dlja_BPMSoft/Ustanovka_PostgreSQL.md)
- [Установка RabbitMQ](Servis_otpravki_SMS_i_Viber_soobschenij_2.0_dlja_BPMSoft/Ustanovka_RabbitMQ.md)
- [Установка Сервиса](Servis_otpravki_SMS_i_Viber_soobschenij_2.0_dlja_BPMSoft/Ustanovka_Servisa_otpravki_SMS_i_Viber_soobschenij_2.0_dlja_BPMSoft.md)

- [Viber рассылка](Servis_otpravki_SMS_i_Viber_soobschenij_2.0_dlja_BPMSoft/Viber-rassylka.md)
