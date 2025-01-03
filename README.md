# Pizza-API

## 1. Идеята на проекта
Идеята на проекта е да се разработят основните услуги на дадена пицария, за да може да бъде конкурентно способна (Шаблон).

## 2. Функционалности към самия проект

### № 1 CRUD Операций с:
- Менюто с пиците.
  - End-point: `/pizza`
- Менюто с топингите.
  - End-point: `/toppings`
- Менюто с напитки.
  - End-point: `/drinks`
- Потребителите (User, Delivere, Admin).
  - End-point: `/role`
- Местоположение на пицариите.
  - End-point: `/locations`
- Разплащателна единица.
  - End-point: `/currencies`

### № 2 Валидиране на потребителя и неговите правомощия чрез JWT
- End-point: `POST /auth/validate`

### № 3 Създаване на поръчка
- Потвърждение за създаване на поръчка
- Изпращане на заявка (поръчка) на доставчика.
- Изпращане на QR code, който съдържа следните данни:
  - Идентификатора на доставчика;
  - Идентификатора на потребителя;
  - Поръчката на човека;
  - Информация за разплащане;
  - End-point: `POST /orders/create`

#### № 3.1 Премахване на поръчка
- Премахване на поръчката в случай, в който поръчката не е потвърден в даден период от време (3 минути);
  - End-point: `DELETE /orders/{order_id}/delete`

#### № 3.2 Следене на поръчки
- Времево изчисляване на текущото местоположението.
- QR code за поръчката се сканира, за да се отчете поръчка за приключена.
  - End-point: `GET /orders/{order_id}/tracking`

#### № 3.3 Вземане на поръчка
- Изпращане на заявка до всички доставчици в района
- При вземане на поръчка се активира подточка 3.
- Ако даден доставчик не може да вземе повече от една поръчка, докато е активна.
  - End-point: `POST /orders/{order_id}/take`

### № 4 Оценяване на поръчки
- End-point: `POST /reviews/purchases`

#### № 4.1 Оценяване на храни и напитки
- End-point: `POST /reviews/items`

### № 5 История за транзакцийте
- End-point: `GET /history/transactions`

#### № 5.1 Преглед на история от взетите поръчки на доставчиците
- End-point: `GET /history/delivery-orders`

### № 6 Плащане
- End-point: `POST /payment/{user_info}`

## 3. Описание на правата

### Хората, които са регистрирани като “User” мога да:
- Правят поръчки.
- Да премахнат поръчка до определен период от време.
- Следят поръчките си.
- Да коментират дадената поръчка.
- Да коментират дадени артикули.

### Хората, които са регистрирани като “Delivere” мога да:
- Взимат поръчки
- Следят определени поръчки, които са заети от тях.
- Да преглеждат история от взетите им поръчки.
- Сканират QR код на потребителя, на който са му взели поръчката, за да извършат транзакция.

### Хората, които са регистрирани като “Admin” мога да:
- Имат пълни правомощия!

## 4. Технологии за реализиране на проекта
- Postman - За проверка на заявките
- Spring - За създаване на нашия Rest API
- Mysql - За съхранение и анализ на нашето приложение.

# Документацията все още се разработва!
