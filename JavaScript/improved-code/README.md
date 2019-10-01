# JavaScript Improved Code

### Arrays

**To cache array length in loop**

```javascript
for (let i = 0, { length } = array; i < length; i++) {
 console.log(i);
}
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
}

console.log(getCarsByState()); // []
console.log(getCarsByState('usa')); // ['Ford', 'Dodge']
console.log(getCarsByState('italy')); // ['Fiat']
```