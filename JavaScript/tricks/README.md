# JavaScript Tricks

### Arrays

**Filter array by logically truthy elements**

```javascript
const filteredArray = [false, '', null, undefined, NaN, 0].filter(Boolean); // []
```

**Filter array by unique elements**

```javascript
const uniqueArray = [...new Set([1, 1, 1, 2, 3, 2, 1, 6])]; // [1, 2, 3, 6]
```

**Convert array of numbers to array of strings**

```javascript
const stringArray = [1, 2, 3].map(String); // ['1', '2', '3']
```

**Quickly create a numeric array**

```javascript
const numArray = Array.from(new Array(100), (el, i) => i); // [0, 1, 2, ..., 99]
```

***

### Objects

**Create absolutely empty objects**

```javascript
const emptyObj = Object.create(null); // {} without `__proto__`
```

**Adding properties by condition**

```javascript
const user = { id: 100, name: 'Andrew' };
const password = 'password';
const hasPassword = true;
const userWithPassword = {
  ...user,
  id: 312,
  ...(hasPassword && { password }),
};
```

**Object nesting conditions**

```javascript
const a = {
  b: {
    c: {
      d: 1,
    },
  },
};

console.log(a.b && a.b.c && a.b.c.d || null); // 1
console.log(a.b && a.b.c && a.b.c.e || null); // null
```

**Deep cloning of objects**

```javascript
const cloneObject = JSON.parse(JSON.stringify(obj));
```

***

### Others

**Get query string parameters from url**

```javascript
const urlParams = new URLSearchParams(window.location.search);

urlParams.has('param');
urlParams.get('param');
urlParams.getAll('param');
urlParams.toString();
urlParams.append('newParam', '1');
```

**Remove fractional part from numbers**

```javascript
console.log((21.777 | 0)); // 21
console.log((-21.777 | 0)); // -21
console.log(~~21.777); // 21
console.log(~~(-21.777)); // -21
```

**Creating Two-Factor authentication codes**

```javascript
const code = Math.floor(Math.random() * 1000000).toString().padStart(6, "0"); // '034592'
```
