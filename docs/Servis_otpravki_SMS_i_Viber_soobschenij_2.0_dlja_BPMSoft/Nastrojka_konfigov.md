Пример docker-compose файла представлен ниже:

```
version: '3.3'

services:
  smssender:
    image: registry.gitlab.com/samarasoft/samarasoft.smssender.2.0/master
    environment:
      ASPNETCORE_URLS: "http://*:5000"
      DB_HOST: [Адрес БД сервиса sms-рассылок]
      DB_PORT: 5432
      DB_NAME: sms_sender
      DB_USER: admin
      DB_PASSWORD: password
      RMQ_HOST: rabbitmq
      RMQ_USER: admin
      RMQ_PASSWORD: password
      RMQ_QUEUE_SMS: SmsSender
      RMQ_QUEUE_PROVIDER_STATUS_CHANGE: SmsProviderStatusChanged
      RMQ_QUEUE_SMS_STATUS_CHANGED: SmsStatusChanged
      API_AUTH_TOKEN: secret
    restart: on-failure
    ports:
      - "5000:5000"
    labels:
      NAME: "smssender"
    depends_on:
      - rabbitmq
      - postgres
    networks:
      - mynetwork

  
```

**DB_HOST** — ip-адрес машины, на которой развернута Ваша база данных в формате x.x.x.x (например, 172.68.0.2)

**DB_PORT** — порт машины, который слушает подключение к Вашей базе данных (например, 5432)

**DB_NAME** — имя базы данных (например, Sms_sender)

**DB_USER** — имя пользователя Вашей базы данных (например, test)

**DB_PASSWORD** — пароль пользователя Вашей базы данных (например, test)

**RMQ_HOST**— ip-адрес машины, на которой развернут RabbitMQ (например, 172.68.0.3)

**RMQ_USER** — имя пользователя RabbitMQ (например, guest)

**RMQ_PASSWORD**— пароль пользователя RabbitMQ (например, guest)

**RMQ_QUEUE_SMS** — очередь с смсками  
**RMQ_QUEUE_PROVIDER_STATUS_CHANGE** — очередь с событиями изменения статуса подключения к провайдеру  
**RMQ_QUEUE_SMS_STATUS_CHANGED** — очередь с событиями изменения статуса смс

**API_AUTH_TOKEN** — Ваш токен аутентификации (например, secret). Набор символов, задается пользователем в данном параметре, рекомендуется использовать сложный произвольный ряд символов одинаковый для кассы и процессинга.