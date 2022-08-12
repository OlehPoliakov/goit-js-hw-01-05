# Module 1 "Переменные и типы. Разветление. Циклы"

# Task 1 ЗАКАЗ ПРОДУКТА

Магазин по продаже ремонтных дроидов готов к открытию, осталось написать скрипт для их заказа. Объяви переменные и присвой им соответствующие значения:

- `pricePerDroid` - цена одного дроида, значение `800`
- `orderedQuantity` - количество дроидов в заказе, значение `6`
- `deliveryFee` - стоимость доставки, значение `50`
- `totalPrice` - общая сумма заказа к оплате, не забудь о стоимости доставки
- `message` - сообщение о состоянии заказа в формате `"You ordered droids worth <total price> credits. Delivery (<delivery fee> credits) is included in total price."`

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

Функция `makeMessage(name, price)` составляет и возвращает сообщение о покупке. Она объявляет два параметра, значения которых будут задаваться во время её вызова.

- `name` - название товара
- `price` - цена товара

Дополни код функции так, чтобы в переменную `message` записывалась строка `"You picked <product name>, price per item is <product price> credits"`, где `<product name>` и `<product price>` это значения параметров name и price. Используй синтаксис шаблонных строк.

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

Функция `calculateTotalPrice` считает и возвращает общую сумму покупки. Она принимает два параметра, значения которых будут задаваться во время её вызова.

- `orderedQuantity` - количество единиц товара в заказе;
- `pricePerItem` - цена одной единицы товара.

Дополни код функции так, чтобы в переменную `totalPrice` записывалась общая сумма покупки, результат умножения кол-ва товаров на цену одного.

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

Функция `makeOrderMessage(orderedQuantity, pricePerDroid, deliveryFee)` составляет и возвращает сообщение о покупке ремонтных дроидов. Она объявляет три параметра, значения которых будут задаваться во время её вызова.

- `orderedQuantity` - количество дроидов в заказе
- `pricePerDroid` - цена одного дроида
- `deliveryFee` - стоимость доставки

Дополни код функции так, чтобы она возвращала сообщение о заказе в формате `"You ordered droids worth <total price> credits. Delivery (<delivery fee> credits) is included in total price."`. 
Не забудь о цене доставки при вычислениях общей стоимости.

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

Функция `checkStorage(available, ordered)` проверяет возможность оформления заказа и возвращает сообщение о результате. Она объявляет два параметра, значения которых будут задаваться во время её вызова:

- `available` - общее количество товаров на складе
- `ordered` - единиц товара в заказе

Используя ветвления дополни код функции так, что:

- Если в заказе указано число, превышающее количество товаров на складе, в переменную `message` записывается строка `"Not enough goods in stock!"`.

- В противном случае записывается строка `"Order is processed, our manager will contact you."`.

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

# Task 6 ПРОВЕРКА БАЛАНСА

Станция по продаже ремонтных дроидов готова к запуску, осталось написать программное обеспечение для отдела продаж.

Функция `makeTransaction(pricePerDroid, orderedQuantity, customerCredits)` выполняет транзакцию по продаже дроидов и возвращает сообщение о результате операции. Она объявляет три параметра, значения которых будут задаваться во время её вызова:

- `pricePerDroid` - цена одного дроида
- `orderedQuantity` - кол-во заказанных дроидов
- `customerCredits` - сумма средств на счету клиента

Дополни её следующим функционалом:

- Объяви переменную `totalPrice` для хранения общей суммы заказа и присвой ей выражение расчёта этой суммы.

- Добавь проверку сможет ли клиент оплатить заказ:
-	если сумма к оплате превышает количество кредитов на счету клиента, запиши в переменную `message` строку `"Insufficient funds!"`;
-	в противном случае, вычти сумму покупки со счёта клиента и запиши в переменную `message` сообщение: `"You ordered <число> droids, you have <число> credits left"`.

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

# Task 7 СКЛАД ТОВАРОВ 2.0

Функция `checkStorage(available, ordered)` проверяет возможность оформления заказа и возвращает сообщение о результате. Она объявляет два параметра, значения которых будут задаваться во время её вызова.

- `available` - доступное количество товаров на складе
- `ordered` - единиц товара в заказе

Используя ветвления дополни код функции так, что:

- Если в заказе еще нет товаров, то есть значение параметра `ordered` равно 0, в переменную `message` присваивается строка `"There are no products in the order!"`.

- Eсли товаров в заказе больше чем доступно товаров на складе, то в переменную `message` присваивается строка `"Your order is too large, there are not enough items in stock!"`.

- В противном случае в переменную `message` присваевается строка `"The order is accepted, our manager will contact you"`.

```js
function checkStorage(available, ordered) {
  let message;
  // Change code below this line
  if (ordered === 0) { 
    message =  'There are no products in the order!';
  } else if (ordered > available) {
    message = 'Your order is too large, there are not enough items in stock!';
  } else {
    message = 'The order is accepted, our manager will contact you';
  }
  // Change code above this line
  return message;
};

- Вызов checkStorage(70, 0) возвращает "There are no products in the order!"
- Вызов checkStorage(100, 130) возвращает "Your order is too large, there are not enough items in stock!"
- Вызов checkStorage(100, 50) возвращает "The order is accepted, our manager will contact you"
```

# Task 8 РАСЧЁТ СКИДКИ

Функция `getDiscount(totalSpent)` определяет значение скидки в зависимости от общей суммы потраченных денег (параметр `totalSpent`) в магазине за всё время (партнёрская программа). Скидка записывается в переменную `discount` и возвращается из функции как результат её работы.

Используя ветвления и логические операторы, дополни код функции.

- Если потрачено от `50000` ( включительно ) или больше кредитов - скидка `10%` (золотой партнёр)
- Если потрачено от `20000` (включительно) до `50000` кредитов - скидка `5%` (серебрянный партнёр)
- Если потрачено от `5000` (включительно) до `20000` кредитов - скидка `2%` (бронзовый партнёр)
- Если потрачено меньше чем `5000` кредитов - скидка `0` (базовый партнёр)

Значения скидок каждого уровня хранятся в одноимённых константах `BASE_DISCOUNT`, `BRONZE_DISCOUNT`, `SILVER_DISCOUNT` и `GOLD_DISCOUNT`.

```js
function getDiscount(totalSpent) {
  const BASE_DISCOUNT = 0;
  const BRONZE_DISCOUNT = 0.02;
  const SILVER_DISCOUNT = 0.05;
  const GOLD_DISCOUNT = 0.1;
  let discount;
  // Change code below this line
  
  if (totalSpent >= 50000 ){
    return GOLD_DISCOUNT;
  }else if (totalSpent < 50000  && totalSpent >= 20000) {
    return SILVER_DISCOUNT;
  }else if (totalSpent < 20000  && totalSpent >= 5000) {
    return BRONZE_DISCOUNT;
  }else if (totalSpent < 5000) {
    return BASE_DISCOUNT;
  }
  
  // Change code above this line
  return discount;
};

-Вызов getDiscount(137000) возвращает 0.1; getDiscount(46900) возвращает 0.05; getDiscount(8250) возвращает 0.02; getDiscount(1300) возвращает 0
```

# Task 9 ПРОВЕРКА ПАРОЛЯ

Функция `checkPassword(password)` сравнивает переданный ей пароль (параметр `password`) с сохранённым паролем администратора (константа `ADMIN_PASSWORD`) и возвращает строку с сообщением о результате.

Используя тернарный оператор дополни функцию так, что:

- Если значения `password` и `ADMIN_PASSWORD` совпадают, присвой переменной `message` строку `"Access is allowed"`.

- В противном случае, присвой `message` строку `"Access denied, wrong password!"`.

```js
function checkPassword(password) {
  const ADMIN_PASSWORD = "jqueryismyjam";
  let message;
  // Change code below this line

  message = password === ADMIN_PASSWORD ? "Access is allowed" : "Access denied, wrong password!";

  // Change code above this line
  return message;
};

- Вызов checkPassword("jqueryismyjam") возвращает "Access is allowed"
- Вызов checkPassword("r3actsux") возвращает "Access denied, wrong password!"
```

# Task 10 ДОСТАВКА ТОВАРА

Функция `getShippingCost(country)` должна проверять возможность доставки товара в страну пользователя (параметр country) и возвращать сообщение о результате хранящееся в переменной `message`. Обязательно используй инструкцию `switch`.

Формат возвращаемой строки `"Shipping to <country> will cost <price> credits"`, где вместо `<country>` и `<price>` необходимо подставить соотвествующие значения.

Список стран и стоимость доставки:

- `China` - 100 кредитов
- `Chile` - 250 кредитов
- `Australia` - 170 кредитов
- `Jamaica` - 120 кредитов

Из списка видно, что доставка есть не везде. Если указанной страны нет в списке, то функция должна вернуть строку `"Sorry, there is no delivery to your country"`

```js
function getShippingCost(country) {
  let message;
  // Change code below this line

   switch (country) { 
   
   case ("Australia"): 
     message = "Shipping to Australia will cost 170 credits";
     break;

   case ("China"): 
     message = "Shipping to China will cost 100 credits"; 
     break;

    case ("Chile"): 
     message = "Shipping to Chile will cost 250 credits"; 
     break;

     case ("Jamaica"): 
     message = "Shipping to Jamaica will cost 120 credits"; 
     break;

   default: 
     message = "Sorry, there is no delivery to your country";
 }
  // Change code above this line
  return message;
};

- Вызов getShippingCost("Australia") возвращает "Shipping to Australia will cost 170 credits"
- Вызов getShippingCost("Germany") возвращает "Sorry, there is no delivery to your country"
```

# Task 11 ФОРМАТИРОВАНИЕ СООБЩЕНИЯ

Функция `formatMessage(message, maxLength)` принимает строку (параметр message) и форматирует её, если длина превышает значение в параметре `maxLength`.

Дополни код функции так, что если длина строки:

- не превышает `maxLength`, функция возвращает её в исходном виде.

- больше `maxLength`, то функция обрезает строку до `maxLength` символов и добавляет в конец троеточие `"..."`, после чего возвращает укороченную версию.

```js
function formatMessage(message, maxLength) {
  let result;
  // Change code below this line
  return (message.length <= maxLength) ? message : (message.slice(0, maxLength) + '...') 
  /// Change code above this line
  return result;
};

- Вызов функции formatMessage("Vestibulum facilisis purus nec", 20) возвращает "Vestibulum facilisis..."
```

# Task 12 ПРОВЕРКА СПАМА

Функция `checkForSpam(message)` принимает строку (параметр message), проверяет её на содержание запрещенных слов `spam` и `sale`, и возвращает результат проверки. Слова в строке параметра `message` могут быть в произвольном регистре, например `SPAM` или `sAlE`.

- Если нашли запрещенное слово (`spam` или `sale`) то функция возвращает буль `true`.
- Если в строке нет запрещенных слов, функция возвращает буль `false`.

```js
function checkForSpam(message) {
  let result;
  // Change code below this line
  if (message.toLowerCase().includes("sale") || message.toLowerCase().includes("spam"))  {
    return true;
  }
  // Change code above this line
  return false;
};

- Вызов функции checkForSpam("Amazing SalE, only tonight!") возвращает true
- Вызов функции checkForSpam("Latest technology news") возвращает false
```

# Module 2 "Масивы. Функции"

# Task 1 ПРОВЕРКА ПАРОЛЯ 2.0 (РАННИЙ ВОЗВРАТ)

Функция `checkPassword` получает пароль пользователя в параметр `password`, проверяет его на совпадение с паролем администратора в переменной `ADMIN_PASSWORD` и возвращает сообщение о результате сравнения.

```js
function checkPassword(password) {
  const ADMIN_PASSWORD = "jqueryismyjam";
  // Change code below this line
  if (password === ADMIN_PASSWORD) {
	return  "Welcome!";
  } 
	return  "Access denied, wrong password!";
  }
  // Change code above this line

- Вызов checkPassword("jqueryismyjam") возвращает "Welcome!"
- Вызов checkPassword("mangohackzor") возвращает "Access denied, wrong password!"
```

# Task 2 СКЛАД ТОВАРОВ 3.0 (РАННИЙ ВОЗВРАТ)

Функция `checkStorage` проверяет возможность оформления заказа и возвращает сообщение о результате. Она принимает два параметра, значения которых будут задаваться во время её вызова.

- `available` - доступное количество товаров на складе
- `ordered` - количество единиц товара в заказе

```js
function checkStorage(available, ordered) {
  // Change code below this line
  if (ordered === 0) {
      return "Your order is empty!";
  } if (ordered > available) {
	return "Your order is too large, not enough goods in stock!";
  } 
	return "The order is accepted, our manager will contact you";
  // Change code above this line
};

- Вызов checkStorage(70, 0) возвращает "Your order is empty!"
- Вызов checkStorage(100, 130) возвращает "Your order is too large, not enough goods in stock!"
- Вызов checkStorage(100, 50) возвращает "The order is accepted, our manager will contact you"
```

# Task 3 КРАЙНИЕ ЭЛЕМЕНТЫ МАССИВА

Напиши функцию `getExtremeElements(array)` которая принимает один параметр `array` - массив элементов произвольной длины. Функция должна возвращать массив из двух элементов - первого и последнего элемента параметра `array`.

```js
function getExtremeElements(array) {
  // Change code below this line
  
    return [array[0], array[array.length -1]];
    
  // Change code above this line
}

- Вызов getExtremeElements([1, 2, 3, 4, 5]) возвращает [1, 5]
- Вызов getExtremeElements(["Earth", "Mars", "Venus"]) возвращает ["Earth", "Venus"]
- Вызов getExtremeElements(["apple", "peach", "pear", "banana"]) возвращает ["apple", "banana"]
```

# Task 4 ГРАВИРОВКА УКРАШЕНИЙ

Сервису гравировки украшений нужна функция, которая бы автоматически считала цену гравировки, в зависимости от количества слов и цены за слово.

Объявлена функция `calculateEngravingPrice(message, pricePerWord)`. Эта функция принимает строку, состоящую из слов разделённых только пробелами (параметр `message`) и цену гравировки одного слова (параметр `pricePerWord`).

Напиши тело функции, чтобы она возвращала общую стоимость гравировки всех слов в строке.

```js
function calculateEngravingPrice(message, pricePerWord) {
   // Change code below this line

    if (message) {
    return message.split(" ").length * pricePerWord;
  } 
};

- Вызов calculateEngravingPrice("JavaScript is in my blood", 10) возвращает 50
```

# Task 5 ГЕНЕРАТОР SLUG

`Термин slug` - это человеко-понятный уникальный идентификатор, который используется в веб-разработке для создания читабельных URL-адесов.

Например, вместо того чтобы пользователь увидел в адресной строке `mysite.com/posts/1q8fh74tx`, можно сделать slug из названия статьи. В результате адрес получится более приятным для восприятия: `mysite.com/posts/arrays-for-begginers`.

&nbsp;ВНИМАНИЕ&nbsp;
Slug это всегда строка в нижнем регистре, слова которой разделены тире.

Напиши функцию `slugify(title)` которая принимает заголовок статьи, параметр `title`, и возвращает `slug`, созданный из этой строки.

- Значением параметра `title` будут строки, слова которых разделены только пробелами
- Все символы `slug` должны быть в нижнем регистре
- Все слова `slug` должна быть разделены тире


```js
function slugify(title) {
  // Change code below this line
  
   return title.toLowerCase().split (" ").join ("-")  
     
  // Change code above this line
}

- Вызов slugify("English for developer") возвращает "english-for-developer"
```
