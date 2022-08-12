# Module 1 "Переменные и типы. Разветление. Циклы"

# Task 1 ЗАКАЗ ПРОДУКТА

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

# Task 2 ШАБЛОННЫЕ СТРОКИ 

Функция makeMessage(name, price) составляет и возвращает сообщение о покупке. Она объявляет два параметра, значения которых будут задаваться во время её вызова.

- name - название товара
- price - цена товара

Дополни код функции так, чтобы в переменную message записывалась строка "You picked <product name>, price per item is <product price> credits", где <product name> и <product price> это значения параметров name и price. Используй синтаксис шаблонных строк.

```js
function makeMessage (name, price) {
  // Change code below this line
   const message = `You picked ${name}, price per item is ${price} credits`;
  // Change code above this line
  return message;
};
makeMessage('Mango', 3500);
```
# Task 3 МАТЕМАТИЧЕСКИЕ ОПЕРАТОРЫ

Функция calculateTotalPrice считает и возвращает общую сумму покупки. Она принимает два параметра, значения которых будут задаваться во время её вызова.

- orderedQuantity - количество единиц товара в заказе;
- pricePerItem - цена одной единицы товара.

Дополни код функции так, чтобы в переменную totalPrice записывалась общая сумма покупки, результат умножения кол-ва товаров на цену одного.

```js
function calculateTotalPrice (orderedQuantity, pricePerItem) {
  // Change code below this line
  const totalPrice = (orderedQuantity * pricePerItem);
  // Change code above this line
  return totalPrice;
};
- Вызов calculateTotalPrice(5, 100) возвращает 500
```

# Task 4 ЗАКАЗ ПРОДУКТА 2.0

Функция makeOrderMessage(orderedQuantity, pricePerDroid, deliveryFee) составляет и возвращает сообщение о покупке ремонтных дроидов. Она объявляет три параметра, значения которых будут задаваться во время её вызова.

- orderedQuantity - количество дроидов в заказе
- pricePerDroid - цена одного дроида
- deliveryFee - стоимость доставки

Дополни код функции так, чтобы она возвращала сообщение о заказе в формате "You ordered droids worth <total price> credits. Delivery (<delivery fee> credits) is included in total price.". Не забудь о цене доставки при вычислениях общей стоимости.

```js
function makeOrderMessage(orderedQuantity, pricePerDroid, deliveryFee) {
  // Change code below this line
  const totalPrice = orderedQuantity * pricePerDroid + deliveryFee;
  const message = `You ordered droids worth ${totalPrice} credits. Delivery (${deliveryFee} credits) is included in total price.`;
  // Change code above this line
  return message;
};
- Вызов makeOrderMessage(2, 100, 50) возвращает "You ordered droids worth 250 credits. Delivery (50 credits) is included in total price."
```

# Task 5 СКЛАД ТОВАРОВ

Функция checkStorage(available, ordered) проверяет возможность оформления заказа и возвращает сообщение о результате. Она объявляет два параметра, значения которых будут задаваться во время её вызова:

- available - общее количество товаров на складе
- ordered - единиц товара в заказе

Используя ветвления дополни код функции так, что:

- Если в заказе указано число, превышающее количество товаров на складе, в переменную message записывается строка "Not enough goods in stock!".

- В противном случае записывается строка "Order is processed, our manager will contact you.".

```js
function checkStorage(available, ordered) {
  let message;
  // Change code below this line
  if (available >= ordered) { // Change this line
    message = 'Order is processed, our manager will contact you.';
  } else {(available < ordered)
    message = 'Not enough goods in stock!';
  }
  // Change code above this line
  return message;
};

- Вызов checkStorage(100, 50) возвращает "Order is processed, our manager will contact you."
- Вызов checkStorage(100, 130) возвращает "Not enough goods in stock!"
```

# Task 6

Станция по продаже ремонтных дроидов готова к запуску, осталось написать программное обеспечение для отдела продаж.

Функция makeTransaction(pricePerDroid, orderedQuantity, customerCredits) выполняет транзакцию по продаже дроидов и возвращает сообщение о результате операции. Она объявляет три параметра, значения которых будут задаваться во время её вызова:

- pricePerDroid - цена одного дроида
- orderedQuantity - кол-во заказанных дроидов
- customerCredits - сумма средств на счету клиента

Дополни её следующим функционалом:

- Объяви переменную totalPrice для хранения общей суммы заказа и присвой ей выражение расчёта этой суммы.

- Добавь проверку сможет ли клиент оплатить заказ:
-	если сумма к оплате превышает количество кредитов на счету клиента, запиши в переменную message строку "Insufficient funds!";
-	в противном случае, вычти сумму покупки со счёта клиента и запиши в переменную message сообщение: "You ordered <число> droids, you have <число> credits left".

```js
function makeTransaction(pricePerDroid, orderedQuantity, customerCredits) {
  let message;
  // Change code below this line
const totalPrice = pricePerDroid * orderedQuantity;
  
  if (totalPrice > customerCredits) { 
    message = 'Insufficient funds!';
  } else {
    message = `You ordered ${orderedQuantity} droids, you have ${customerCredits - totalPrice} credits left`
  }
  // Change code above this line
  return message;
};

- Вызов makeTransaction(3000, 5, 23000) возвращает "You ordered 5 droids, you have 8000 credits left"
- Вызов makeTransaction(500, 10, 5000) возвращает "You ordered 10 droids, you have 0 credits left"
- Вызов makeTransaction(5000, 10, 8000) возвращает "Insufficient funds!"
```
