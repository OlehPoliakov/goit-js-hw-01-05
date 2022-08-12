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

! ВНИМАНИЕ !
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

# Task 6 КОМПОЗИЦИЯ МАССИВОВ

Напиши функцию `makeArray(firstArray, secondArray, maxLength)` для создания нового массива со всеми элементами двух исходных `firstArray` и `secondArray`. Параметр maxLength содержит максимально допустимую длину нового массива.

Если количество элементов нового массива больше `maxLength`, функция должна вернуть копию массива длиной `maxLength` элементов. В противном случае функция должна вернуть новый массив целиком.

```js
function makeArray(firstArray, secondArray, maxLength) {
    // Change code below this line
    
    let allClients = firstArray.concat(secondArray);

    let maxLengthClients = allClients.slice(0,maxLength);

    return maxLengthClients 
};

- Вызов makeArray(["Mango"], ["Ajax", "Chelsea", "Poly", "Houston"], 3) возвращает ["Mango", "Ajax", "Chelsea"]
- Вызов makeArray(["Mango", "Poly", "Houston"], ["Ajax", "Chelsea"], 4) возвращает ["Mango", "Poly", "Houston", "Ajax"]
```

# Task 7 СУММА ЧИСЕЛ (ЦИКЛ FOR)

Напиши функцию `calculateTotal(number)`, которая принимает целое число (параметр `number`) и возвращает сумму всех целых чисел от единицы и до этого числа. Например, если `number` равно `3`, то сумма это `1 + 2 + 3`, то есть `6`.

```js
function calculateTotal(number) {
 // Change code below this line
  let total = 0;

    for (let i = 0; i <= number; i += 1) { 
      total += i;
    }

  return total
  // Change code above this line
};
```

# Task 8 ПОДСЧЁТ СУММЫ ПОКУПКИ

Напиши функцию `calculateTotalPrice(order)`, которая принимает один параметр `order` - массив чисел, и рассчитывает общую сумму его элементов. Общая сумма элементов должна сохраняться в переменной `total`, которая возвращается, как результат работы функции.

```js
function calculateTotalPrice(order) {
  let total = 0;
  // Change code below this line

  for (i = 0; i < order.length; i += 1) { 
      total += order[i];
    }
  // Change code above this line
  return total;
};
```

# Task 9 ПОИСК САМОГО ДЛИННОГО СЛОВА

Напиши функцию `findLongestWord(string)` которая принимает произвольную строку состоящую только из слов разделённых пробелом (параметр `string`) и возвращает самое длинное слово в этой строке.

```js
function findLongestWord(string) {
  // Change code below this line
  
  let arrStr = string.split(' ');
  let wordLength = 0;
  let longestWord;

  for (let i = 0; i < arrStr.length; i += 1) {
    wordLength = arrStr[1].length;

  if (arrStr[i].length > wordLength) {
      longestWord = arrStr[i];
    
      return longestWord;
    }
  }
};
```

# Task 10 ФИЛЬТРАЦИЯ МАССИВА ЧИСЕЛ

Напиши функцию `filterArray(numbers, value)`, которая принимает массив чисел (параметр `numbers`) и возвращает новый массив, в котором будут только те элементы массива `numbers`, которые больше чем значение параметра `value` (число).

```js
function filterArray(numbers, value) {
   // Change code below this line
 const newArray = [];

  for(let i = 0; numbers.length > i; i++){
       
      if (numbers[i]>value){
      
       newArray.push(numbers[i])
      }
    }
 return newArray
  // Change code above this line
};

- Вызов функции filterArray([1, 2, 3, 4, 5], 3) возвращает [4, 5]
```

# Task 11 ОБЩИЕ ЭЛЕМЕНТЫ

Общими элементами массивов называют те элементы, которые присутствуют во всех массивах.

Например, в двух массивах `[1, 3, 5]` и `[0, 8, 5, 3]` общими будут числа `3` и `5`, т.к. они присутствуют в обоих исходных массивах. А числа `0`, `1` и `8` присутствуют только в одном из массивов.

Напиши функцию `getCommonElements(array1, array2)` которая получает два массива произвольной длины в параметры `array1` и `array2`, и возвращает новый массив, состоящий из тех элементов, которые присутствуют в обоих исходных массивах.

```js
function getCommonElements(array1, array2) {
  // Change code below this line
  console.log (array1);
  console.log (array2);

  const uniquelElement = [];
  for (const element of array1) {
    
    if(array2.includes(element)){
      uniquelElement.push(element)
    }
  }
  return uniquelElement;
 // Change code above this line
};

- Вызов getCommonElements([24, 12, 27, 3], [12, 8, 3, 36, 27]) возвращает [12, 27, 3]
```

# Task 12 ФИЛЬТРАЦИЯ МАССИВА ЧИСЕЛ 2.0

Выполни рефакторинг функции `filterArray(numbers, value)` заменив цикл `for на for...of`.

```js
function filterArray(numbers, value) {

  const filteredNumbers = [];
  
    for (const number of numbers) {

        if (number > value) {
            filteredNumbers.push(number);
        }
    }
  return filteredNumbers;
};
```

# Task 13 ЧЁТНЫЕ ЧИСЛА

Напиши функцию `getEvenNumbers(start, end)` которая возвращает массив всех чётных чисел от `start` до `end`. Чётным считается число которое делится на `2` без остатка (`10 % 2 === 0`).

```js
 function getEvenNumbers(start, end) {
 
   const numbers = [];
   
    for(let i = start;  i <= end; i+= 1){
       console.log (i)

      if (i % 2 === 0){
        numbers.push(i)   
      }
   }
  return numbers;
};
```

# Task 14 ФУНКЦИЯ INCLUDES()

Напиши функцию `includes(array, value)`, которая делает тоже самое, что и метод массива `массив.includes(значение)` - проверяет, есть ли в массиве `array` значение `value`, возвращая `true` если есть и `false` в противном случае.

При выполнении этой задачи в теле функции `includes()` нельзя использовать метод `массив.includes(значение)`.

```js
function includes(array, value) {
  // Change code below this line
  
    for (let i = 0; i < array.length; i += 1) {
      if (array[i] === value){
        return true;
      }
    }
    return false;
    
  // Change code above this line
};
```

# Module 3 "Обьекты. Операции rest/spread"

# Task 1 ПОДСЧЁТ СВОЙСТВ

Напиши функцию `countProps(object)`, которая считает и возвращает количество собственных свойств объекта в параметре `object`. Используй переменную `propCount` для хранения количества свойств объекта.

```js
function countProps(object) {
  let propCount = 0;
  // Change code below this line

    const keys = Object.keys(object);
    propCount = keys.length;

  // Change code above this line
  return propCount;
};
```

# Task 2 РАСХОДЫ НА ЗАРПЛАТУ

Напиши функцию `countTotalSalary(salaries)` которая принимает объект зарплат, где имя свойства это имя сотрудника, а значение свойства это зарплата. Функция должна рассчитать общую сумму зарплат сотрудников и вернуть её. Используй переменную `totalSalary` для хранения общей суммы зарплаты.

```js
function countTotalSalary(salaries) {
  let totalSalary = 0;
  // Change code below this line

  for (const salary of Object.values(salaries)) {
  
    totalSalary += salary;
};
```

# Task 3 ПОИСК ОБЪЕКТА ПО ЗНАЧЕНИЮ СВОЙСТВА

Напиши функцию `getProductPrice(productName)` которая принимает один параметр `productName` - название продукта. Функция ищет объект продукта с таким именем (свойство `name`) в массиве `products` и возвращает его цену (свойство `price`). Если продукт с таким названием не найден, функция должна возвращать `null`.

```js
const products = [
  { name: 'Radar', price: 1300, quantity: 4 },
  { name: 'Scanner', price: 2700, quantity: 3 },
  { name: 'Droid', price: 400, quantity: 7 },
  { name: 'Grip', price: 1200, quantity: 9 },
];

function getProductPrice(productName) {
  for (const item of products)
    if (item.name === productName)
      return item.price;
  return null;
};

- Вызов getProductPrice("Radar") возвращает 1300.
```

# Task 4 КОЛЛЕКЦИЯ ЗНАЧЕНИЙ СВОЙСТВА

Напиши функцию `getAllPropValues(propName)` которая принимает один параметр `propName` - имя (ключ) свойства. Функция должна вернуть массив всех значений свойства с таким именем из каждого объекта в массиве `products`. Если в объектах нет свойства с таким именем, функция должна вернуть пустой массив.
```js
const products = [
  { name: "Radar", price: 1300, quantity: 4 },
  { name: "Scanner", price: 2700, quantity: 3 },
  { name: "Droid", price: 400, quantity: 7 },
  { name: "Grip", price: 1200, quantity: 9 },
];

function getAllPropValues(propName) {
  const valueArray = [];
   
  for (const product of products) {
    if (product.hasOwnProperty(propName)) {
      valueArray.push(product[propName]);
    }
  }
  return valueArray;
};

- Вызов getAllPropValues("name") возвращает ["Radar", "Scanner", "Droid", "Grip"]; 
			("price") возвращает [1300, 2700, 400, 1200] ; 
			("quantity") возвращает [4, 3, 7, 9];
			("category") возвращает []
```

# Task 5 ЗАДАЧА. ОБЩАЯ СТОИМОСТЬ ТОВАРА

Напиши функцию `calculateTotalPrice(productName)` которая принимает один параметр `productName` - название товара. Функция должна вернуть общую стоимость (цена * количество) товара с таким именем из массива `products`.

```js
const products = [
  { name: "Radar", price: 1300, quantity: 4 },
  { name: "Scanner", price: 2700, quantity: 3 },
  { name: "Droid", price: 400, quantity: 7 },
  { name: "Grip", price: 1200, quantity: 9 },
];

  function calculateTotalPrice(productName) {
    
    for(const product of products){
      
    let totalPrice = product.price * product.quantity;
      
    	if(productName === product.name){
      
    return totalPrice;
    }
  }
    return 0;
};

- Вызов calculateTotalPrice("Blaster") возвращает 0; 
			   ("Radar") возвращает 5200; 
			   ("Grip") возвращает 10800
```

# Task 6 КАРТОЧКИ ЗАДАЧ

Напиши функцию `makeTask(data)` которая принимает один параметр `data` - объект со следующими свойствами.

- `text` - текст задачи.
- `category` - категория задачи.
- `priority` - приоритет задачи.

Функция должна составить и вернуть новый объект задачи, не изменяя напрямую параметр `data`. В новом объекте должно быть свойство `completed`, значение которого хранится в одноимённой локальной переменной.

В параметре `data` гарантированно будет только свойство `text`, а остальные два, `category` и `priority`, могут отсутствовать. Тогда, в новом объекте задачи, в свойствах `category` и `priority` должны быть значения по умолчанию, хранящиеся в одноимённых локальных переменных.

```js
function makeTask(data) {
  const completed = false;
  const category = "General";
  const priority = "Normal";
  // Change code below this line

      return {...{category, priority, completed},...data};
  
  // Change code above this line
};

- Вызов makeTask({}) возвращает { category: "General", priority: "Normal", completed: false }
```

# Task 7 МАССИВ СОВПАДЕНИЙ

Функция `findMatches()` принимает произвольное количество аргументов. Первым аргументом всегда будет массив чисел, а остальные аргументы будут просто числами.

Дополни код функции так, чтобы она возвращала новый массив `matches`, в котором будут только те аргументы, начиная со второго, которые есть в массиве первого аргумента.

Например, `findMatches([1, 2, 3, 4, 5], 1, 8, 2, 7)` должна вернуть массив `[1, 2]`, потому что только они есть в массиве первого аргумента.

```js
function findMatches(numbers, ...args) {
  const matches = []; 
    for (const number of numbers) {
      
      if (args.includes(number)){
        matches.push(number);
      }
    }
  return matches;
};

- Вызов makeTask({}) возвращает { category: "General", priority: "Normal", completed: false }
```

# Task 8.1 ЛАВКА ЗЕЛИЙ «У СТАРОЙ ЖАБЫ» 

К нам обратилась владелица лавки зелий «У старой жабы» и заказала программу для ведения инвентаря - добавления, удаления, поиска и обновления зелий. Добавь объекту `atTheOldToad` свойство `potions`, значением которого сделай пустой массив.

```js
const atTheOldToad = {

  potions: []

};
```

# Task 8.2 ПОЛУЧАЕМ ВСЕ ЗЕЛЬЯ

Добавь объекту `atTheOldToad` метод `getPotions()`, который просто возвращает значение свойства potions.

```js
const atTheOldToad = {
  potions: ["Speed potion", "Dragon breath", "Stone skin"],
  
  getPotions() { return this.potions },
};
```

# Task 8.3 ДОБАВЛЯЕМ НОВОЕ ЗЕЛЬЕ

Дополни метод `addPotion(potionName)` так, чтобы он добавлял зелье `potionName` в конец массива зелий в свойстве `potions`.

```js
const atTheOldToad = {
  potions: ["Speed potion", "Dragon breath", "Stone skin"],
  
  addPotion(potionName) {
	this.potions.push(potionName)
  },
};
```

# Task 8.4 УДАЛЯЕМ ЗЕЛЬЕ

Дополни метод `addPotion(potionName)` так, чтобы он добавлял зелье `potionName` в конец массива зелий в свойстве `potions`.

```js
const atTheOldToad = {
  potions: ["Speed potion", "Dragon breath", "Stone skin"],
  
  removePotion(potionName) {
  
    for (let i = 0; i < this.potions.length; i+=1) {
    
      if (potionName === this.potions[i]) {
      
        console.log('мы нашли такой продукт');
        
        this.potions.splice(i, 1)
      }
    }
  },
};
```

# Task 8.5 ОБНОВЛЯЕМ ЗЕЛЬЕ

Дополни метод `updatePotionName(oldName, newName)` так, чтобы он обновлял название зелья с `oldName` на `newName`, в массиве зелий в свойстве `potions`.

```js
const atTheOldToad = {

  potions: ["Speed potion", "Dragon breath", "Stone skin"],
  
  updatePotionName(oldName, newName) {

    const potionsNameIndex = this.potions.indexOf(oldName);
    
    this.potions.splice(potionsNameIndex, 1, newName);
  }
};
```

# Task 8.6 РАСШИРЯЕМ ИНВЕНТАРЬ

Заказчица хочет чтобы каждое зелье было представлено не только именем, но и ценой, а в будущем может быть и другими характеристиками. Поэтому теперь в свойстве `potions` будет храниться массив объектов со следующими свойствами.

Выполни рефакторинг методов объекта `atTheOldToad` так, чтобы они работали не с массивом строк, а с массивом объектов.

- `getPotions()` - метод для получения всех зелий. Возвращает значение свойства potions.

- `addPotion(newPotion)` - добавляет зелье `newPotion` (уже объект) в массив в свойстве `potions`, но только если такого зелья еще нет в инвентаре. В противном случае возвращается строка.

- `removePotion(potionName)` - удаляет объект зелья с именем `potionName` из массива в свойстве `potions`.

- `updatePotionName(oldName, newName)` - обновляет свойство `name` объекта-зелья с названием `oldName` на `newName` в массиве `potions`.

```js
const atTheOldToad = {
    potions: [
        { name: "Speed potion", price: 460 },
        { name: "Dragon breath", price: 780 },
        { name: "Stone skin", price: 520 },
    ],
    
    getPotions() {
        return this.potions;
    },
    
    addPotion(newPotion) {
        for (const item of this.potions) {
                if (item.name === newPotion.name) {
                    return `Error! Potion ${newPotion.name} is already in your inventory!`;
                }
            }
        this.potions.push(newPotion);
    },
    
    removePotion(potionName) {
        for (let i = 0; i < this.potions.length; i += 1) {
        const potion = this.potions[i];
            if (potionName === potion.name) {
                this.potions.splice(i, 1);
            }
        }
    },
    
    updatePotionName(oldName, newName) {
        let resalt = `Potion ${oldName} is not in inventory`;
        for (let i = 0; i < this.potions.length; i += 1) {
        const potion = this.potions[i];

        if (oldName === potion.name) {
            potion.name = newName;
            resalt = `Found ${oldName} change to ${newName} `;
        }
      }
        return console.log(resalt);
    },
};
```

# Module 4 "Перебирающие методи масивов."

# Task 1 ФИЛЬТРАЦИЯ МАССИВА ЧИСЕЛ

Функция `filterArray(numbers, value)` принимает массив чисел `numbers` и возвращает новый массив, в котором будут только те элементы оригинального массива, которые больше чем значение параметра `value`.

Выполни рефакторинг функции так, чтобы вместо цикла `for` она использовала метод `forEach`.

```js
function filterArray(numbers, value) {
  const filteredNumbers = [];

    numbers.forEach(number => {
        if (number > value) {
            filteredNumbers.push(number)
        }
    });

  return filteredNumbers;
};

- Вызов функции filterArray([1, 2, 3, 4, 5], 3) возвращает [4, 5]
```

# Task 2 ОБЩИЕ ЭЛЕМЕНТЫ

Функция `getCommonElements(firstArray, secondArray)` принимает два массива произвольной длины в параметры `firstArray` и `secondArray`, и возвращает новый массив их общих элементов, то есть тех которые есть в обоих массивах.

Выполни рефакторинг функции так, чтобы вместо цикла `for` она использовала метод `forEach`.

```js
function getCommonElements(firstArray, secondArray) {
  const commonElements = [];

  firstArray.forEach(firstArray => {
        if (secondArray.includes(firstArray)) {
            commonElements.push(firstArray);
        }
    });

  return commonElements;
};

- Вызов getCommonElements([10, 20, 30, 40], [4, 30, 17, 10, 40]) возвращает [10, 30, 40]
```

# Task 3 ФИЛЬТРАЦИЯ МАССИВА ЧИСЕЛ 2.0

Замени объявление функции `filterArray()` и коллбек для метода `forEach()` на стрелочные функции.

```js
const filterArray = (numbers, value) => {
  
  let filteredNumbers = [];

  numbers.forEach((number) => {
    if (number > value) {
      filteredNumbers.push(number);
    }
  });
  return filteredNumbers;
};
```

# Task 4  ОБЩИЕ ЭЛЕМЕНТЫ 2.0

Замени объявление функции `getCommonElements()` и коллбек для метода `forEach()` на стрелочные функции.

```js
const getCommonElements = (firstArray, secondArray) => {
  const commonElements = [];

  firstArray.forEach((element) => {
    if (secondArray.includes(element)) {
      commonElements.push(element);
    }
  });
  return commonElements;
};
```
# Task 5 МЕТОД REDUCE() И МАССИВ ОБЪЕКТОВ 

Нашему сервису необходимо рассчитать среднее время проведённое в одной игре для каждого игрока, и получить общую сумму этих времён. Рассчитать время для каждого из игроков, можно разделив его время (свойство `playtime`) на количество игр (свойство `gamesPlayed`).

```js
const players = [
  { name: "Mango", playtime: 1270, gamesPlayed: 4 },
  { name: "Poly", playtime: 469, gamesPlayed: 2 },
  { name: "Ajax", playtime: 690, gamesPlayed: 3 },
  { name: "Kiwi", playtime: 241, gamesPlayed: 1 },
];
// Change code below this line


const totalAveragePlaytimePerGame = players.reduce((total, number) => {
  return total + number.playtime / number.gamesPlayed;
}, 0);
```

# Task 1 ИМЕНА ПОЛЬЗОВАТЕЛЕЙ//////

Дополни функцию `getUserNames(users)` так, чтобы она возвращала массив имён пользователей (свойство `name`) из массива объектов в параметре `users`.

```js
const getUserNames = users => {

    return users.map(user => user.name);
    
};
```

# Task 2 ПОЧТЫ ПОЛЬЗОВАТЕЛЕЙ//////

Дополни функцию getUserEmails(users) так, чтобы она возвращала массив почтовых адресов пользователей (свойство email) из массива объектов в параметре users.

```js
const getUserEmails = users => {

  return users.map(user => user.email);

};
```

# Task 3 ПОЛЬЗОВАТЕЛИ С ЦВЕТОМ ГЛАЗ//////

Дополни функцию `getUsersWithEyeColor(users, color)` так, чтобы она возвращала массив пользователей у которых цвет глаз (свойство `eyeColor`) совпадает со значением параметра `color`.

```js
const getUsersWithEyeColor = (users, color) => {

 return users.filter(users => users.eyeColor === color);

};
```

# Task 4 ПОЛЬЗОВАТЕЛИ В ВОЗРАСТНОЙ КАТЕГОРИИ//////

Дополни функцию `getUsersWithAge(users, minAge, maxAge)` так, чтобы она возвращала массив пользователей, возраст которых (свойство `age`) попадает в промежуток от `minAge` до `maxAge`.

```js
const getUsersWithAge = (users, minAge, maxAge) => {

  return users.filter (({age}) => age >= minAge && age <= maxAge);

};
```

# Task 5 ПОЛЬЗОВАТЕЛИ С ДРУГОМ //////

Дополни функцию `getUsersWithFriend(users, friendName)` так, чтобы она возвращала массив пользователей у которых есть друг с именем в параметре `friendName`. Массив друзей пользователя хранится в свойстве `friends`.

```js
const getUsersWithFriend = (users, friendName) => {
  
  return users.filter(users => users.friends.indexOf(friendName) !== -1);
  
};
```

# Task 6 СПИСОК ДРУЗЕЙ //////

Дополни функцию `getFriends(users)` так, чтобы она возвращала массив друзей всех пользователей (свойство `friends`). У нескольких пользователей могут быть одинаковые друзья, сделай так чтобы возвращаемый массив не содержал повторений.

```js
const getFriends = (users) => {
  
  return users
        .flatMap(user => user.friends)
            .filter((friend, index, array) => array
                .indexOf(friend) === index);
};
```

# Task 7 АКТИВНЫЕ ПОЛЬЗОВАТЕЛИ //////

Дополни функцию `getActiveUsers(users)` так, чтобы она возвращала массив активных пользователей, значение свойства `isActive` которых `true`.

```js
const getActiveUsers = (users) => {

    return users.filter(users => users.isActive);
};
```

# Task 8 НЕАКТИВНЫЕ ПОЛЬЗОВАТЕЛИ //////

Дополни функцию `getInactiveUsers(users)` так, чтобы она возвращала массив неактивных пользователей, значение свойства `isActive` которых `false`.

```js
const getInactiveUsers = (users) => {
   
  return users.filter(users => users.isActive === false);

};
```

# Task 9 ПОЛЬЗОВАТЕЛЬ С ПОЧТОЙ //////

Дополни функцию `getUserWithEmail(users, email)` так, чтобы она возвращала объект пользователя, почта которого (свойство `email`) совпадает со значением параметра `email`.

```js
const getUserWithEmail = (users, email) => {
  
   return users.find(users => users.email === email);

};
```

# Task 10 ВСЕ ЛИ ПОЛЬЗОВАТЕЛИ АКТИВНЫ //////

Дополни функцию `isEveryUserActive(users)` так, чтобы она проверяла все ли пользователи сейчас активны (свойство `isActive`) и возвращала `true` или `false`.

```js
const isEveryUserActive = (users) => {

  return users.every(users => users.isActive);

};
```

# Task 11 ЕСТЬ ЛИ АКТИВНЫЕ ПОЛЬЗОВАТЕЛИ //////

Дополни функцию `isAnyUserActive(users)` так, чтобы она проверяла наличие активных пользователей (свойство `isActive`) и возвращала `true` или `false`.

```js
const isAnyUserActive = users => {
 
  return users.some(users => users.isActive);
 
};
```

# Task 12 ОБЩИЙ БАЛАНС ПОЛЬЗОВАТЕЛЕЙ //////

Дополни функцию `calculateTotalBalance(users)` так, чтобы она считала и возвращала сумму всех средств (свойство `balance`) которые хранят пользователи из массива `users`.

```js
const calculateTotalBalance = users => {
  
  return users.flatMap(user => user.balance).reduce((total, number) => total + number, 0); 

};
```

# Task 13 ОБЩЕЕ КОЛИЧЕСТВО ДРУЗЕЙ //////

Дополни функцию `getTotalFriendCount(users)` так, чтобы она считала и возвращала общее количество друзей (свойство `friends`) всех пользователей из массива `users`.

```js
const getTotalFriendCount = users => {

       const totalFriends = users.reduce((total, user) => {
        return [...total, ...user.friends];
    }, []);
    
    return totalFriends.length;
};
```

# Task 14 СОРТИРОВКА ПО БАЛАНСУ //////

Дополни функцию sortByAscendingBalance(users) так, чтобы она возвращала массив пользователей отсортированный по возрастанию их баланса (свойство balance).

```js
const sortByAscendingBalance = users => {

  return users.sort((firstRating, secondRating) => firstRating.balance - secondRating.balance);

};
```

# Task 15  СОРТИРОВКА ПО КОЛИЧЕСТВУ ДРУЗЕЙ //////

Дополни функцию `sortByDescendingFriendCount(users)` так, чтобы она возвращала массив пользователей отсортированный по убыванию количества их друзей (свойство `friends`).

```js
const sortByDescendingFriendCount = users => {

  return [...users].sort((a, b) => b.friends.length - a.friends.length);

};
```
