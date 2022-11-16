# Мой гайд по прохождению собеседований
##### Возможно я его буду дополнять

- Что такое [API](https://superbwebsitebuilders.com/ru/chto-takoe-api-prostymi-slovami/). Привести [пример](https://ant.design/components/button/#API) API, для взаимодействия с которыми не нужно запрашивать данные с сервера

### JS

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
- что такое асинхронность, определение
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

### React

- отличие componentDidMount, useEffect и useLayoutEffect
- React.memo
- Алгоритм [Reconciliation](https://ru.reactjs.org/docs/reconciliation.html)
- Новые фичи React, начиная с React 16 по 18 ([React docs](https://reactjs.org)) (делаете особый акцент на auto-batching, useTransition и useDeferredValue), что [завезли](https://github.com/facebook/react/blob/main/CHANGELOG.md) в реакт начиная с 16 версии
- React Fiber engine (по-моему уже не очень хорошо говорить что главная фича React это Virtual DOM, на мой взгляд это все-таки Fiber если речь про 16 версию и выше) [link](https://blog.logrocket.com/deep-dive-react-fiber/#what-react-fiber) - обычно не нужно глубоко понимать а достаточно знать что это такое
- [Redux Toolkit](https://redux-toolkit.js.org/), Redux Toolkit Query (особенно метод [createApi](https://redux-toolkit.js.org/rtk-query/overview#apis))
- Посмотреть [мою кастомную реализацию createApi со стабами](https://github.com/danimaik/black-wall-group/blob/master/src/components/service.js)

Дополнительно

- Желательно вообще прочитать всю документацию по React и Redux (но можно и без этого, не делайте, если чувствуете что выгораете, практика всегда лучше)
- react-query (чтоб получить оффер должно хватить Redux Toolkit Query, надо просто знать что это такое)
- CORS, погуглить что такое preflight запрос
- [Критические этапы рендеринга](https://developer.mozilla.org/ru/docs/Web/Performance/Critical_rendering_path)

###### For me only
###### This is the *[Markdown Guide](https://www.markdownguide.org)*.
