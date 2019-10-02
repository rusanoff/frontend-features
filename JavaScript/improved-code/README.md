# JavaScript Code Improvement Tips

### Arrays

**To cache array length in loop**

```javascript
for (let i = 0, { length } = array; i < length; i++) {
 console.log(i);
}
```

### Objects

**Use `Object.assign()` to set default object properties**

```javascript
const user = {
  id: 100,
  name: 'Andrew',
  // has not property `age`
};

const createUser = (userObj) => {
  const newUser = Object.assign(
    {
      id: null,
      name: 'Unknown',
      age: 'Age is not specified',
    },
    userObj,
  );

  // ...
};

createUser(user);
```

### Conditions

**Use Map instead of Switch-Case**

```javascript
const cars = new Map()
  .set('usa', ['Ford', 'Dodge'])
  .set('france', ['Renault', 'Peugeot'])
  .set('italy', ['Fiat']);

const getCarsByState = (state) => {
  return cars.get(state) || [];
};

console.log(getCarsByState()); // []
console.log(getCarsByState('usa')); // ['Ford', 'Dodge']
console.log(getCarsByState('italy')); // ['Fiat']
```
