# Структуры данных
## 1. Структура объекта
Объекты можно описывать с помощью интерфейсов или типов. Например:
```typescript
interface Person {
  name: string;
  age: number;
}

const person: Person = {
  name: "Alice",
  age: 30
};
```
Здесь `Person` — это интерфейс, который описывает структуру объекта. 

У объекта `person` должны быть свойства name типа `string` и `age` типа `number`.

## 2. Необязательные свойства объекта
Если нужно сделать свойство объекта необязательным, это можно сделать с помощью `?`:
```typescript
interface Person {
  name: string;
  age?: number; // необязательное свойство
}

const person1: Person = { name: "Alice" }; // без age
const person2: Person = { name: "Bob", age: 25 }; // с age
```

Здесь свойство `age` необязательно, и объект может быть как с этим свойством, так и без него.

## 3. Интерфейсы
Интерфейсы позволяют задавать структуру объектов, а также могут наследоваться и расширяться:
```typescript
interface Animal {
  name: string;
  age: number;
}

interface Dog extends Animal {
  breed: string;
}

const dog: Dog = {
  name: "Buddy",
  age: 3,
  breed: "Labrador"
};
```
Интерфейс `Dog` расширяет интерфейс `Animal` и добавляет новое свойство `breed`.

## 4. Массивы в объектах
Можно хранить массивы внутри объектов. Для этого нужно использовать тип массивов, например `string[]`, `number[]` или `Array<T>`:
```typescript
interface Person {
  name: string;
  hobbies: string[];
}

const person: Person = {
  name: "Alice",
  hobbies: ["reading", "painting"]
};
```

В данном примере свойство `hobbies` — это массив строк, который хранит интересы человека.

## 5. Интерфейс как тип объекта с массивом
Интерфейсы можно использовать для описания объектов, содержащих массивы:
```typescript
interface School {
  name: string;
  students: string[];
}

const school: School = {
  name: "Sunshine High",
  students: ["Alice", "Bob", "Charlie"]
};
```

Здесь объект `School` имеет массив студентов `students` типа `string[]`.

## 6. Сложные объекты
Сложные объекты — это объекты, которые содержат другие объекты, массивы или комбинацию этих элементов.
```typescript
interface Address {
  street: string;
  city: string;
}

interface Person {
  name: string;
  age: number;
  address: Address; // Вложенный объект
}

const person: Person = {
  name: "Alice",
  age: 30,
  address: {
    street: "123 Main St",
    city: "Wonderland"
  }
};
```

Здесь объект `Person` имеет вложенный объект `address` типа `Address`.

## 7. Объекты в объектах
Объекты в объектах — это когда одно свойство объекта является еще одним объектом.
```typescript
interface Company {
  name: string;
  CEO: {
    name: string;
    age: number;
  };
}

const company: Company = {
  name: "TechCorp",
  CEO: {
    name: "John Doe",
    age: 45
  }
};
```

Здесь свойство `CEO` является объектом, содержащим имя и возраст.

## 8. Массивы объектов
Массивы объектов — это когда массив состоит из объектов одного типа.
```typescript
interface Product {
  id: number;
  name: string;
}

const products: Product[] = [
  { id: 1, name: "Laptop" },
  { id: 2, name: "Phone" }
];
```

Массив `products` состоит из объектов типа `Product`, каждый из которых имеет свойства `id` и `name`.
