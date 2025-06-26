# Навигация по документации сервиса отправки сообщений

## Выберите версию документации

<div style="margin-bottom: 20px;">
  <button onclick="setVersion('1.0')" style="padding: 8px 16px; background:#eeeeee; border:none; border-radius:4px; cursor:pointer; font-weight:bold; margin-right:10px;">
    Версия 1.0
  </button>
  <button onclick="setVersion('2.0')" style="padding: 8px 16px; background:#90caf9; border:none; border-radius:4px; cursor:pointer; font-weight:bold;">
    Версия 2.0
  </button>
</div>

<script>
  function setVersion(version) {
    document.getElementById('docVersion').textContent = version;
    document.getElementById('versionText').textContent = version;
  }
  // Установка версии по умолчанию
  window.addEventListener('DOMContentLoaded', () => setVersion('2.0'));
</script>

---

## Содержимое версии <span id="versionText">2.0</span>

- [Чейнджлог](Servis_otpravki_SMS_i_Viber_soobschenij_2.0_dlja_BPMSoft/Changelog.md)
- [Маркетинговая кампания](Servis_otpravki_SMS_i_Viber_soobschenij_2.0_dlja_BPMSoft/Element_marketingovoj_kampanii_SMS-rassylka.md)
- [Хронология сообщений](Servis_otpravki_SMS_i_Viber_soobschenij_2.0_dlja_BPMSoft/Hronologija_SMS-soobschenij.md)

### История отправки SMS

- [Контакт](Servis_otpravki_SMS_i_Viber_soobschenij_2.0_dlja_BPMSoft/Istorija_otpravki_SMS-soobschenij/Istorija_SMS-soobschenij_kontakta.md)
- [Контрагент](Servis_otpravki_SMS_i_Viber_soobschenij_2.0_dlja_BPMSoft/Istorija_otpravki_SMS-soobschenij/Istorija_SMS-soobschenij_kontragenta.md)
- [Общая история](Servis_otpravki_SMS_i_Viber_soobschenij_2.0_dlja_BPMSoft/Istorija_otpravki_SMS-soobschenij/Istorija_otpravki_SMS-soobschenij.md)

### Настройки и интеграции

- [Конфиги](Servis_otpravki_SMS_i_Viber_soobschenij_2.0_dlja_BPMSoft/Nastrojka_konfigov.md)
- [Ограничения по рассылке](Servis_otpravki_SMS_i_Viber_soobschenij_2.0_dlja_BPMSoft/Nastrojka_ogranichenija_kolichestva_SMS_rassylok.md)
- [Подключение провайдера](Servis_otpravki_SMS_i_Viber_soobschenij_2.0_dlja_BPMSoft/Nastrojka_podkljuchenija_k_SMS-provajderu.md)

### Отправка и рассылки

- [Отправка из действий](Servis_otpravki_SMS_i_Viber_soobschenij_2.0_dlja_BPMSoft/Otpravka_SMS-soobschenija_iz_paneli_dejstvij.md)
- [Запуск рассылки](Servis_otpravki_SMS_i_Viber_soobschenij_2.0_dlja_BPMSoft/SMS-rassylka/Kak_zapustit__SMS-rassylku.md)
- [Тестовая отправка](Servis_otpravki_SMS_i_Viber_soobschenij_2.0_dlja_BPMSoft/SMS-rassylka/Kak_vypolnit__testovuju_otpravku_SMS-soobschenija.md)