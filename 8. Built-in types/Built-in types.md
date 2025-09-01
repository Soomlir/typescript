# Встроенные типы в TypeScript
В TypeScript существует множество встроенных типов, включая типы для работы с датами, регулярными выражениями, элементами HTML и коллекциями. Рассмотрим их подробнее:

1. Дата (`Date`)
Тип `Date` используется для представления даты и времени. Он является стандартным объектом в JavaScript и TypeScript.

Пример:
```typescript
let currentDate: Date = new Date();
console.log(currentDate); // выводит текущую дату и время
```

2. Регулярные выражения (`RegExp`)
Тип `RegExp` используется для работы с регулярными выражениями в TypeScript.

Пример:
```typescript
let regex: RegExp = /abc/i; // регулярное выражение, ищет "abc" без учета регистра
console.log(regex.test('AbC')); // true
```

3. Тип `HTMLElement`
Тип `HTMLElement` используется для представления объектов DOM в браузере. Это базовый тип для всех элементов HTML-страницы, например, для `<div>`, `<p>`, `<input>` и других.

Пример:
```typescript
let divElement: HTMLElement = document.getElementById('myDiv');
if (divElement) {
    divElement.style.backgroundColor = 'yellow';
}
```

4. Коллекции
- Массивы (`Array`) В TypeScript массивы могут быть типизированы, что позволяет гарантировать, что все элементы массива будут одного типа.

Пример:
```typescript
let numbers: number[] = [1, 2, 3];
let strings: Array<string> = ['a', 'b', 'c'];
```

- Множества (`Set`) Тип Set представляет коллекцию уникальных значений. В TypeScript также можно задавать тип элементов множества.

Пример:
```typescript
let uniqueNumbers: Set<number> = new Set([1, 2, 3]);
uniqueNumbers.add(4); // добавление элемента
console.log(uniqueNumbers.has(2)); // true
```

- Карты (`Map`) Тип Map позволяет хранить коллекцию пар ключ-значение, где ключи могут быть любого типа, а значения — тоже.

Пример:
```typescript
let map: Map<string, number> = new Map();
map.set('a', 1);
map.set('b', 2);
console.log(map.get('a')); // 1
```
