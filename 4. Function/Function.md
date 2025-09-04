# Функции
При объявлении параметров функций мы можем указать их тип:
```typescript
function func(a: number, b: number) {
	return a + b;
}
```

Можно указать тип возвращаемого функцией значения:
```typescript
function func(a: number, b: number): number {
	return a + b;
}
```

Бывают функции, которые ничего не возвращают. В этом случае ставим void:
```typescript
function func(test: string): void {
	alert(test);
}
```

## 1. Количество параметров функции
TypeScript позволяет задавать функции с различным количеством параметров. Количество параметров функции может быть фиксированным или переменным (с использованием rest параметров).

```typescript
function sum(a: number, b: number): number {
  return a + b;
}
```

## 2. Необязательные параметры функций
Можно задавать параметры, которые являются необязательными, используя `?`. Это означает, что параметр может быть передан, но не обязателен.

```typescript
function greet(name: string, age?: number): string {
  return age ? `Привет, ${name}, тебе ${age} лет!` : `Привет, ${name}!`;
}
```
Здесь параметр `age` является необязательным.

## 3. Значения параметров по умолчанию
Вы можете задать значения по умолчанию для параметров функции:
```typescript
function greet(name: string, age: number = 30): string {
  return `Привет, ${name}, тебе ${age} лет!`;
}
```
Если при вызове функции `age` не будет передан, то используется значение по умолчанию — `30`.

## 4. Rest параметры функции
Rest параметры позволяют передавать в функцию произвольное количество аргументов:
```typescript
function sum(...numbers: number[]): number {
  return numbers.reduce((acc, num) => acc + num, 0);
}
```
Здесь `numbers` — это массив всех переданных аргументов.

## 5. Тип функций
В TypeScript функции можно типизировать, указывая типы для параметров и возвращаемого значения:
```typescript
function multiply(a: number, b: number): number {
  return a * b;
}
```
В этом примере функции задаются типы для параметров `a` и `b` как `number`, а тип возвращаемого значения — `number`.

## 6. Свой тип с функцией
Вы можете создавать собственные типы для функций, например, с помощью интерфейсов или типов:
```typescript
type MathOperation = (a: number, b: number) => number;

const add: MathOperation = (a, b) => a + b;
const subtract: MathOperation = (a, b) => a - b;
```

Здесь мы определили тип `MathOperation`, который описывает функцию, принимающую два числа и возвращающую число.

## 7. Функции-коллбэки
Функции-коллбэки — это функции, которые передаются в другие функции как аргументы и могут быть вызваны внутри этих функций:
```typescript
function fetchData(callback: (data: string) => void): void {
  const data = 'some data';
  callback(data);
}

fetchData((data) => {
  console.log(data);
});
```

Здесь функция `fetchData` принимает коллбэк в качестве параметра, который затем вызывается с данными.

## 8. Стрелочные функции
```typescript
const add = (a: number, b: number): number => a + b;
```
