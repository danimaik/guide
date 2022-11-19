### JS

- [замыкание](https://ru.wikipedia.org/wiki/%D0%97%D0%B0%D0%BC%D1%8B%D0%BA%D0%B0%D0%BD%D0%B8%D0%B5_(%D0%BF%D1%80%D0%BE%D0%B3%D1%80%D0%B0%D0%BC%D0%BC%D0%B8%D1%80%D0%BE%D0%B2%D0%B0%D0%BD%D0%B8%D0%B5))
- методы массивов, нужно сказать какие мутируют, какие нет
- разница между ключами Object.keys и ключами из цикла for in
- разница между var, let и const
- как отработает код
```
for (var i = 0; i < 10; i++) {
  setTimeout(() => {
    console.log(i);
  }, 0);
}
```
- контекст вызова this. Как ведет себя в стрелочной и обычной функции
- Что выведет консоль и почему
```
const user = {
  name: 'Bob',
  funcFunc() {
    return function() {
      console.log(this);
    }
  },
  funcArrow() {
    return () => {
      console.log(this);
    }
  },
  arrowFunc: () => {
    return function() {
      console.log(this);
    }
  },
  arrowArrow: () => {
    return () => {
      console.log(this);
    }
  },
};

user.funcFunc()();
user.funcArrow()();
user.arrowFunc()();
user.arrowArrow()();
```
- Что выведет консоль и почему
```
const user2 = {
  name: 'Jim',
  funcFunc: user.funcFunc(),
  funcArrow: user.funcArrow(),
  arrowFunc: user.arrowFunc(),
  arrowArrow: user.arrowArrow()
}

user2.funcFunc();
user2.funcArrow();
user2.arrowFunc();
user2.arrowArrow();
```
- что такое [асинхронность](https://doka.guide/js/async-in-js/), определение
- микро и макро таски
- как отработает код и почему
```
console.log(1);
setTimeout(() => {
  console.log(2);
}, 0);
const myPromise = new Promise((resolve, reject) => {
  console.log(3);
  resolve(4);
}).then((value) => console.log(value));
console.log(5);
```
```
new Promise((resolve) => {
  console.log("Message 0");
});

console.log("Message 1");

setTimeout(() => console.log("Message 2"));

Promise.resolve()
  .then(() => console.log("Message 3"))
  .then(() => setTimeout(() => console.log("Message 4")));
  
setTimeout(() => console.log("Message 5"));

console.log("Message 6");
```
