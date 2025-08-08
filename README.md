#### Differences Between Interfaces and Types in TypeScript

- Interfaces can only be used in classes and objects whereas types are used for primitives, objects, tuples, unions, etc.
- When declaring an interface and type, there are differences in syntax.

```typescript
interface Car {
  name: string;
  year: number;
  model: string;
}

type Car = {
  name: string;
  year: number;
  model: string;
};
```

- While extending an interface, the "extends" keyword is used, whereas for type intersection, the "&" keyword is used.

```typescript
interface Animal {
  name: string;
}
interface Dog extends Animal {
  age: number;
  species: string;
}
```

```typescript
type AnimalType = { name: string };
type DogType = AnimalType & { age: number; species: string };
```

- Type is more flexible. Interface is less flexible compared to the type.

- Interface is used for implementation and extending classes whereas type is not used for implementation purposes.



#### Provide an example of using union and intersection types in TypeScript.

Example:

```typescript
// Union Type
function getValue(value: number | string) {
  if (typeof value === "string") {
    return parseInt(value);
  }
  return value;
}

getValue("555");
getValue(100);
```

```typescript
// Intersection  Type
interface IPerson {
  name: string;
}

interface IEmployee {
  employeeId: number;
}

type StaffMember = IPerson & IEmployee;

const staff: StaffMember = {
  name: "John Doe",
  employeeId: 100001,
};

console.log(staff);
```