# JavaScript Generators and Iterators


#### Iterators
In JavaScript an iterator is an object which defines a sequence and potentially a return value upon its termination. More specifically an iterator is any object which implements the Iterator protocol by having a next() method which returns an object with two properties: value, the next value in the sequence; and done, which is true if the last value in the sequence has already been consumed. If value is present alongside done, it is the iterator's return value.

```javascript

```

#### Generators
Generators, also called **“iterator factories”**, are a new type of JavaScript function that creates specific iterations. They give you special, self-defined ways to loop over stuff.

```javascript
function* getNextPrime() {
  let nextNumber = 2;

  while (true) {
    if (isPrime(nextNumber)) {
      yield nextNumber;
    }
    nextNumber++;
  }
}

const nextPrime = getNextPrime();

console.log(nextPrime.next().value); // {value: 2, done: false}
console.log(nextPrime.next().value); // {value: 3, done: false}
console.log(nextPrime.next().value); // {value: 5, done: false}
console.log(nextPrime.next().value); // {value: 7, done: false}
```

![Generators and Iterators](image1.png)
