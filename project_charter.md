# Устав проекта APTracker

> **Версия**: 0.9.0.

> **APTracker** - Adeptik Project Tracker - система ведения учета расхода времени по статьям в рамках проектов.

## 1. Начальные условия

На данный момент команда Adeptik использует существующее решение для отслеживания времени выполнения проектов.

### Существующее решение имеет недостатки

- Решение имеет неинтуитивный интерфейс, что выражается в сложности его использования, система не помогает пользователю избежать ошибок при вводе данных.
- В системе отсутсвует расширенный механизм проверок и рекомендаций в зависимости от сферы деятельности сотрудника.
- Решение является устаревшим с технической и функциональной точки зрения, т.к. реализовывалось около 3-х лет назад по существующему на тот момент видению проблемы.
- Заказчик не имеет полной информации по рентабельности проектов и временным затратам.

Необходимость разработки нового решения объясняется недостатками существующего.

## 2. Цели и ожидания проекта

- С помощью разрабатываемой системы заказчик должен иметь возможность оценить затраты на выпонение проектов (выражается временем), успешность конкретных этапов разработки и токсичность клиента.

## 3. Содержание и результаты

В результате разработки системы должны быть получены следующие компоненты:

- BackEnd сервис с базой данных, реализующие основную бизнес логику приложения;
- клиентское веб-приложение;
- пояснительные записки, включающие документацию по архитектуре системы, основным методам веб-сервиса, структуре базы данных (в том числе, в виде диаграмм UML);
- презентация проекта.

## 4. Ключевые требования и характеристики

### Функциональные требования

#### Вход и система ролей

- Система должна обеспечивать авторизацию пользователя с помощью Active Directory (аккаунт Microsoft).
- Система должна поддерживать разделение возможностей и прав для ролей администратора, руководителя и сотрудника проекта.
- Администратор должен иметь возможность устанавливать роли других пользователей (администратор, руководитель, сотрудник).

#### Руководители и сотрудники

Руководитель должен иметь возможность просматривать отчеты уровня проектов, клиентов и организации.

Сотрудник должен иметь следующие возможности:

- зафиксировать собственный дневной отчет, указав статьи и соответствующие им временные затраты;
- просмотреть собственный дневной отчет;
- просмотреть список заполненных им дневных отчетов.

Система должна:

- показывать рекомендуемые пользователю статьи расхода времени;
- выдавать предупреждения при вводе нестандартных для пользователя данных;
- ограничивать ввод некорректных данных пользователем.

#### Добавление данных и механизмы проверок

- Исполнитель должен иметь возможность указывать расходы времени за день по статьям в рамках ассоциированных с ним проектов.
- Система должна выдавать предупреждения о вводе нестандартных для пользователя данных.
- Система должна обеспечивать проверку совпадения введенного количества часов с соответствующим пользователю количеству рабочих часов в сутки.

#### Администрирование

Администратор должен иметь следующие возможности:

- Просматривать список клиентов.
- Создавать новых клиентов и изменять названия существующих клиентов.
- Управлять проектами клиента:
  - создавать новый проект;
  - завершать проект;
  - возобновлять проект;
  - просматривать список проектов клиента.
- Управлять статьями проекта:
  - просматривать статьи проекта;
  - устанавливать и снимать запрет на отчет по статье;
  - изменять название статьи.
- Управлять портфелями:
  - создать портфель;
  - изменить название портфеля;
  - управлять набором статей в портфеле;
  - управлять набором проектов в портфеле;
  - управлять набором клиентов в портфеле;
  - изменять владельца портфеля.

### Нефункциональные требования

- Срок обучения работе с системой не должен занимать более 15 минут для пользователя и 2 часов для администратора.
- Бизнес-логика системы должна быть реализована в объектно ориентированном стиле, в разработке должна применяться система контроля версий GIT.
- Поддержка системы должна стоить не более 36000 рублей в год (затраты электроэнергии + подключение к сети + оплата труда поддерживающего персонала + стоимость оборудования и его использования).
- Система должна разрабатываться на базе открытых свободных компонентов.
- Развертывание системы (установка веб-сервиса, веб-клиента и базы данных) должно занимать не более одного часа.
- Система должна поддерживать одновременную работу не менее 100 человек.
- Uptime системы должен составлять не менее 99.9% от общего времени работы (не менее месяца).
- Время отклика системы на действия пользователя должно составлять не более 0.9 секунд.
- Элементы системы должны иметь систему версионирования в соответствии Semantic Versioning 2.0.0.

## 5. Бюджет и сроки

Срок реализации: осенний семестр 2019 года.

1. Сентябрь: создание устава проекта, анализ сущностей, выбор стека.
2. Октябрь: разработка модели базы данных, разработка первой версии API, реализация первой версии веб-клиента.
3. Ноябрь: дополнительный анализ требований, реализация всего основного функционала.
4. Декабрь:

   - 1-я половина: дополнительная доработка функционала, внедрение первой тестовой версии.
   - 2-я половина: финальная доработка в соответствии с замечаниями заказчика, защита проекта.

Время реализации: не менее 4 и не более 6 часов в неделю на каждого исполнителя.

## 6. Ключевые участники

### Исполнители

- Евгений (@D5T)
- Илья (@leaptonisetee)
- Мончача (@judinilson)
- Алишер (@iwbas)

### Заказчик

Компания Adeptik.
Контактное лицо: Морозов А.В. (@avmorozov)

## 7. Допущения и ограничения проекта

- Возможна реализация Unit-тестов.
- Предполагается работа и развертывание системы на Ubuntu Linux 19.04.
- Возможно развертывание системы в виде Docker-контейнера.

## 8. Риски

### Несоответстиве результата разработки ожиданиям заказчика

- Минимизация: разрабатываемая система может быть внедрена для тестового использования по желанию заказчика начиная с первой работающей версии.
- Разрешение: требования к системе могут быть изменены в ходе реализации проекта по взаимному согласию заказчика и исполнителей.

### Изменение количества ресурсов (числа разработчиков)

- Минимизация: распределение ролей в соответствии с компетенциями и интересами исполнителя, освобождение исполнителя на некоторый согласованный промежуток времени, помощь исполнителю в решении конкретной задачи.
- Разрешение: При изменении количества участников проекта в меньшую сторону и при отсутствии достаточного количества времени у нового состава исполнителей функциональные требования могут быть пересмотрены и согласованы с заказчиком повторно.
