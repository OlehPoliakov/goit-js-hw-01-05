# Module 1 "Переменные и типы. Разветление. Циклы"

# Task 1

Магазин по продаже ремонтных дроидов готов к открытию, осталось написать скрипт для их заказа. Объяви переменные и присвой им соответствующие значения:

- pricePerDroid - цена одного дроида, значение 800
- orderedQuantity - количество дроидов в заказе, значение 6
- deliveryFee - стоимость доставки, значение 50
- totalPrice - общая сумма заказа к оплате, не забудь о стоимости доставки
- message - сообщение о состоянии заказа в формате "You ordered droids worth <total price> credits. Delivery (<delivery fee> credits) is included in total price."

```js
// Change code below this line
const pricePerDroid = 800;
const orderedQuantity = 6;
const deliveryFee = 50;

const totalPrice = pricePerDroid * orderedQuantity + deliveryFee;

const message = `You ordered droids worth ${totalPrice} credits. Delivery (${deliveryFee} credits) is included in total price.`;
console.log (message)

- Значение переменной message это строка "You ordered droids worth 4850 credits. Delivery (50 credits) is included in total price."
```

# Задание 2

Напиши класс `User` для создания пользователя со следующим свойствами:

- `name` - строка
- `age` - число
- `followers` - число

Добавь метод `getInfo()`, который, выводит строку:
`User ${имя} is ${возраст} years old and has ${кол-во фоловеров} followers`

```js
const mango = new User({
  name: 'Mango',
  age: 2,
  followers: 20,
});

mango.getInfo(); // User Mango is 2 years old and has 20 followers

const poly = new User({
  name: 'Poly',
  age: 3,
  followers: 17,
});

poly.getInfo(); // User Poly is 3 years old and has 17 followers
```

# Задание 3

Напиши класс `Storage`, который будет создавать объекты для управления складом
товаров. При вызове будет получать один аргумент - начальный массив товаров, и
записывать его в свойство `items`.

Добавь методы класса:

- `getItems()` - возвращает массив текущих товаров
- `addItem(item)` - получает новый товар и добавляет его к текущим
- `removeItem(item)` - получет товар и, если он есть, удаляет его из текущих

```js
const storage = new Storage([
  'Нанитоиды',
  'Пролонгер',
  'Железные жупи',
  'Антигравитатор',
]);

const items = storage.getItems();
console.table(items); // [ "Нанитоиды", "Пролонгер", "Железные жупи", "Антигравитатор" ]

storage.addItem('Дроид');
console.table(storage.items); // [ "Нанитоиды", "Пролонгер", "Железные жупи", "Антигравитатор", "Дроид" ]

storage.removeItem('Пролонгер');
console.table(storage.items); // [ "Нанитоиды", "Железные жупи", "Антигравитатор", "Дроид" ]
```

# Задание 4

Напиши класс `StringBuilder`. На вход он получает один параметр - строку,
которую записывает в свойство `_value`.

Добавь классу следующий функционал:

- Геттер `value` - возвращает текущее значение поля `_value`
- Метод `append(str)` - получает парметр str (строку) и добавляет ее в конец
  `_value`
- Метод `prepend(str)` - получает парметр str (строку) и добавляет ее в начало
  value
- Метод `pad(str)` - получает парметр str (строку) и добавляет ее в начало и в
  конец `_value`

```js
const builder = new StringBuilder('.');

builder.append('^');
console.log(builder.value); // '.^'

builder.prepend('^');
console.log(builder.value); // '^.^'

builder.pad('=');
console.log(builder.value); // '=^.^='
```

# Задание 5

Напиши класс `Car` с указанными свойствами и методами.

```js
class Car {
  /*
   * Добавь статический метод `getSpecs(car)`,
   * который принимает объект-машину как параметр и выводит
   * в консоль значения свойств maxSpeed, speed, isOn, distance и price.
   */

  /*
   * Конструктор получает объект настроек.
   *
   * Добавь свойства будущеего экземпляра класса:
   *  speed - текущая скорость, изначально 0
   *  price - цена автомобиля
   *  maxSpeed - максимальная скорость
   *  isOn - заведен ли автомобиль, значения true или false. Изначально false
   *  distance - общий киллометраж, изначально 0
   */
  constructor() {}

  /*
   * Добавь геттер и сеттер для свойства price,
   * который будет работать с свойством цены автомобиля.
   */

  /*
   * Добавь код для того чтобы завести автомобиль
   * Записывает в свойство isOn значение true
   */
  turnOn() {}

  /*
   * Добавь код для того чтобы заглушить автомобиль
   * Записывает в свойство isOn значение false,
   * и сбрасывает текущую скорость в 0
   */
  turnOff() {}

  /*
   * Добавялет к свойству speed полученное значение,
   * при условии что результирующая скорость
   * не больше чем значение свойства maxSpeed
   */
  accelerate(value) {}

  /*
   * Отнимает от свойства speed полученное значение,
   * при условии что результирующая скорость не меньше нуля
   */
  decelerate(value) {}

  /*
   * Добавляет в поле distance киллометраж (hours * speed),
   * но только в том случае если машина заведена!
   */
  drive(hours) {}
}

const mustang = new Car({ maxSpeed: 200, price: 2000 });

mustang.turnOn();
mustang.accelerate(50);
mustang.drive(2);

Car.getSpecs(mustang);
// maxSpeed: 200, speed: 50, isOn: true, distance: 100, price: 2000

mustang.decelerate(20);
mustang.drive(1);
mustang.turnOff();

Car.getSpecs(mustang);
// maxSpeed: 200, speed: 0, isOn: false, distance: 130, price: 2000

console.log(mustang.price); // 2000
mustang.price = 4000;
console.log(mustang.price); // 4000
