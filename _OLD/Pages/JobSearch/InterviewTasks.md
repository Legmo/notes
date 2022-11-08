<h1>Задачки для собеседования разработчика (js frontend)</h1>

[//]: # (Сайты для тренировки)
<details><summary><b>Сайты для тренировки</b></summary><p>

- [codingame.com](https://www.codingame.com)
- [codewars.com](https://www.codewars.com)
- [leetcode.com](http://leetcode.com/)
- [hackerrank.com](https://www.hackerrank.com/)
- [coderbyte.com](https://coderbyte.com/)
- [Топ 8 лучших ресурсов для практики программирования в 2018](https://habr.com/ru/post/414009/)

<br></p>
</details> 

[//]: # (Темы для практики)
<details><summary><b>Темы для практики</b></summary><p>

- циклы
- методы массивов
- промисы
- React - хуки
- TypeScript

<br></p>
</details> 

[//]: # (Задачки из курса LearnJS)
<details><summary><b>Задачки из курса LearnJS</b></summary><p>

- Циклы - https://learn.javascript.ru/while-for#tasks
- Switch - https://learn.javascript.ru/switch#tasks
- Методы строк - https://learn.javascript.ru/string#tasks
- Массивы
  - https://learn.javascript.ru/array#tasks
  - https://learn.javascript.ru/array-methods#tasks
- Объекты
  - https://learn.javascript.ru/object#tasks
  - https://learn.javascript.ru/object-methods#tasks
- Рекурсия и стек - https://learn.javascript.ru/recursion#tasks
- Замыкания - https://learn.javascript.ru/closure#tasks
- Bind - https://learn.javascript.ru/bind#tasks
- Call, Apply - https://learn.javascript.ru/call-apply-decorators#tasks
- Timeout - https://learn.javascript.ru/settimeout-setinterval#tasks
- Колбэки
- Промисы
  - https://learn.javascript.ru/promise-basics#tasks
  - https://learn.javascript.ru/promise-chaining#tasks
- Async/Await
  - https://learn.javascript.ru/async-await#tasks

<br></p>
</details> 

[//]: # (Из личного опыта)
<details><summary><b>Из личного опыта</b></summary><p>

***

[//]: # (В каком порядке выведутся «console.log»)
<details id="task-1"><summary><b>В каком порядке выведутся «console.log»</b></summary><p>

```js
console.log('1')
setTimeout(function foo() {
  console.log('2')
}, 0)
console.log('3')

// Ответ: 1, 3, 2
```

```js
console.log('Start');

setTimeout(function timeout() {
  console.log('Timeout');
}, 0);

const promise = new Promise(function (resolve, reject) {
  console.log('Promise'); // Выполянется как обычный синхронный код
  resolve(true);
});

promise.then(function () {
  console.log('Then'); // Очередь микрозадач
});

console.log('End');

// Ответ: Start,  Promise, End, Then, Timeout
```

```js
console.log('Start');

setTimeout(function timeout() {
  console.log('Timeout');
}, 0);

//В стэке отрабатывает resolve, и отправляет .then в очередь микрозадач
Promise.resolve().then(function () {
  console.log('Then');
})

console.log('End');

// Ответ: Start,  End,  Then, Timeout
```

```js
console.log('Start');

setTimeout(function timeout() {
  console.log('setTimeout');
}, 0);

Promise.resolve().then(function () {
  console.log('Promise 1');
}).then(function () {
  console.log('Promise 2');
})

console.log('End');

// Ответ: Start,  End,  Promise 1, Promise 2, Timeout
```

```js
setTimeout(()=>{
  console.log('timeOut 1');
}, 0)
  
console.log(1);
  
new Promise(resolve => {
  console.log("Promise")
  setTimeout(()=>{
    console.log('timeOut 2');
    resolve()         // обратить внимание! После этого момента всё идёт немного иначе.Следом сразу отработают then. — т.к. resolve() прерывает очередь макрозадач, и отрабатывают все then
  }, 0)
})
.then(() => {
  console.log("then1")
})
.then(() => {
  console.log("then2")
})
        
console.log(4);
  
setTimeout(()=>{
  console.log('timeOut 3');
}, 0)

// 1, Promise, 4, timeOut 1, timeOut 2 (Сработал resolve! Очередь макрозадач прервалась) then1, then2, timeOut 3
```

```js
console.log('start');  // Выполянется как обычный синхронный код

setTimeout(function(){
  console.log('timeout 5');
}, 5 );
  
setTimeout(function(){
  console.log('timeout 0');
}, 0 );

const promise = new Promise(function(resolve, reject) {
  console.log('promise');  // Выполянется как обычный синхронный код
  resolve(true);
});

promise
.then(
  function(){console.log('then 1');}  // Очередь микрозадач
)
.then(
  function(){console.log('then 2');}  // Очередь микрозадач
);
  
console.log('end ');  // Выполянется как обычный синхронный код
  
//start, promise, end
//then 1 - then/catch всегда после обычных задач (это microtasks)
//then 2
//timeout 0 - timeout/interval выполняются в самом конце, после
//timeout 5
```

```js
setTimeout(()=>{
  console.log('timeOut');
}, 0)
    
console.log(1);
    
new Promise(resolve => {
  console.log("Promise")
  setTimeout(()=>{
    console.log('777');
    resolve()         // Внимание! Дальше всё идёт иначе — промис разрешился, макротаск прервался. Следом отработают then
  }, 0)
})
.then(() => {
  console.log("then1")
})
.then(() => {
  console.log("then2")
})
          
console.log(4);
    
setTimeout(()=>{
  console.log('timeOuts');
}, 0)
  
// 1, Promise, 4, timeOut, 777, (Сработал resolve! Очередь макрозадач прервалась) then1, then2, timeOuts
```

```js
var a = 5;
  
setTimeout(function timeout(){
  console.log(a);
  a = 10;
}, 0)
    
var p = new Promise(function(resolve, reject){
  console.log(a);
  a = 25;
  resolve();
})
  
p.then(function(){
  a = 15;
  console.log(a)
})   
  
console.log(a);

  
// 5, 25, 15, 15
```

**Подробнее**
- [Legmo - JS. Работа движка JS](../JS/JS.md#engine)
- [Legmo - JS. Асинхронность](../JS/JS.md#asynchrony)

<br></p>
</details> 

[//]: # (Числа Фибоначчи. Рекурсия)
<details id="task-2"><summary><b>Числа Фибоначчи. Рекурсия</b></summary><p>

Напишите функцию fib(n) которая возвращает n-е число Фибоначчи.
- Последовательность [чисел Фибоначчи](https://ru.wikipedia.org/wiki/%D0%A7%D0%B8%D1%81%D0%BB%D0%B0_%D0%A4%D0%B8%D0%B1%D0%BE%D0%BD%D0%B0%D1%87%D1%87%D0%B8) определяется формулой `Fn = Fn-1 + Fn-2`.
- То есть, следующее число получается как сумма двух предыдущих.
- Первые два числа равны `1`, затем `2(1+1)`, затем `3(1+2)`, `5(2+3)` и так далее: `1, 1, 2, 3, 5, 8, 13, 21...`.
- Напишите функцию `fib(n)` которая возвращает `n-е` число Фибоначчи.

**Вариант 1 - Рекурсия**
```js
function test(n) {
  if (n <= 1) { return 1 }
  else {
    return  test(n - 1) + test(n - 2);
  }
  alert( test(3) ); // 2
}
```
<br>
<br>

**Вариант 2 - Рекурсия + мемоизация** 
- чтоб по несколько раз не высчитывать одно и то же значение
```js
// ДОДЕЛАТЬ!!!! ОШИБКИ!!!

function fib(n) { 
    let map = new Map();
    let a = n-1;
    let b = n-2;
    let stepA = null;
    let stepB = null;
    
    if (n <= 1) {
        return 1
    } 
    else {
        //Оптимизировать:
        //Надо ли всегда прверять map.has(a), если map.has(b) === false ?
        //вынести в f(x) повторяющийся код (поиск в map, если нет - присваивать в map и рекурсия) 
        
        if(map.has(b)) { 
            stepB = map.get(b)
        } else {
            stepB = fib(b);
            map.set(b, stepB);
        };
            
        if(map.has(a)) {
          stepA = map.get(a)
        } else {
            stepA = fib(a);
            map.set(a, stepA);
        };
    
        return stepA + stepB;
        
    }
}

console.log(fib(3)); // 2
console.log(fib(7)); // 13
//console.log(fib(77)); // 5527939700884757
```
  <br>
  <br>

**Вариант 3 - цикл for** 
- любая рекурсия может быть сведена к циклу
- начнёт с 1 и 2, затем из них получит fib(3) как их сумму, затем fib(4)как сумму предыдущих значений, затем fib(5)
  и так далее, до финального результата. На каждом шаге нам нужно помнить только значения двух предыдущих чисел
  последовательности.
- ```js
    function test(n) {
      let prev = 1;
      let cur = 1;
      for (let i = 3; i <= n; i++) {
        let temp = prev + cur;
        prev = cur;
        cur = temp;
      }
      return cur;
    }
  ```
<br>
<br>

**Вариант 4 - цикл for + деструктурирующее присваивание**
```js
function fib(n) {
  let cur = 1, prev = 1;
  for (let i = 3; i <= n; i++) {
    // cur = актуальное значение. Сумма «актуального» числа из пред. итерации и «предыдущего» числа из пред. итерации 
    // prev = предыдущее значение
    [cur, prev] = [cur + prev, cur]; 
  }
  return cur;
}
```
<br>
<br>

**Ссылки**
- [learn.javascript.ru - Задачка «Числа Фибоначчи» с решением](https://learn.javascript.ru/task/fibonacci-numbers)
- [Пример решения через «for» + деструктурирующее присваивание](https://ilyachalov.livejournal.com/162627.html)

<br></p>
</details> 

[//]: # (Генерация строки из массива объектов)
<details id="task-3"><summary><b>Генерация строки из массива объектов</b></summary><p>

**Задача**
- есть массив однотипных объектов, у каждого есть свойства value, order, expired.
  - надо написать функцию которая
    - исключить объекты с expired=true,
    - оставшиеся отсортировать по значению order (предполагалось использовать метод sort),
    - потом взять значения свойства value,
    - сделать каждому значению reverse,
    - записать всё это в строку,
    - при этом ни один символ в строке не должен повторяться дважды (предполагалось использовать коллекцию Set)
```js
// Написать функцию, либо последовательность операций, которая вернёт результат следующих условий:
// результате есть строка из сконкатенированных value элементов коллекции, расположенных в обратном порядке
// реузльтат не содержит одинаковых букв, если буква уже добавлена в строку, она более не добавляется
// результат собирается только из непросроченных записей (т.е. из тех, у которых expired: false)
// результат конкатенируется в порядке возрастания order
  
const input = [
  {value: 'qweq', order: 4, expired: false},
  {value: 'asdq', order: 2, expired: true},
  {value: 'jkri', order: 1, expired: false},
  {value: 'oiod', order: 3, expired: false},
];
```  
<br>
<br>

1. **Решение «в лоб»**
```js
const input = [
  {value: 'qweq', order: 4, expired: false},
  {value: 'asdq', order: 2, expired: true},
  {value: 'jkri', order: 1, expired: false},
  {value: 'oiod', order: 3, expired: false},
];

console.log('start: ', input)

let actual = input.filter(obj => !obj.expired)

console.log('actual: ', actual)

const temp = actual;
let sorted = temp.sort((a,b) => a.order-b.order)

console.log('sorted 1: ', sorted)

let reversed = sorted.map(obj => {
  let objCopy = {...obj};
  console.log(objCopy.value);
  objCopy.value = objCopy.value.split("").reverse().join("");
  console.log(objCopy.value);
  return objCopy;
})
console.log('reversed: ', reversed)

let output = sorted.reduce((result, current) => {
    let valArray = current.value.split("");
    let finalStr = ''
    valArray.forEach((item, index, array) =>{
    console.log('result', result, 'item: ', item)
        if(!result.includes(item) && !finalStr.includes(item)) {
            finalStr = finalStr + item;
        }
    })
    return result + finalStr;
}, '' );

console.log('output: ', output)
```
<br>
<br>

2. **Решение «в лоб» через SET**
```js
const input = [
  {value: 'qweq', order: 4, expired: false},
  {value: 'asdq', order: 2, expired: true},
  {value: 'jkri', order: 1, expired: false},
  {value: 'oiod', order: 3, expired: false},
];

let actual = input.filter(obj => !obj.expired)

const temp = actual;
let sorted = temp.sort((a,b) => a.order-b.order)

let reversed = sorted.map(obj => {
  let objCopy = {...obj};
  console.log(objCopy.value);
  objCopy.value = objCopy.value.split("").reverse().join("");
  console.log(objCopy.value);
  return objCopy;
})

let output = new Set(); 

sorted.map(obj => {
  let valArray = obj.value.split("");

  valArray.map(symb => {
    output.add(symb)
  })
}, '' );

output = [...output].join('')
```
<br>		
<br>

3. **Решение оптимизированное**
```js
const input = [
  {value: 'qweq', order: 4, expired: false},
  {value: 'Asdq', order: 2, expired: true},
  {value: 'jkri', order: 1, expired: false},
  {value: 'oiod', order: 3, expired: false},
];

const temp = [...actual];
let set = new Set(); 

let actual = temp.filter(obj => !obj.expired)
let sorted = actual.sort((a,b) => a.order-b.order)

sorted.map(obj => {
  let valArray = obj.value.split("").reverse();
  valArray.map(symb => set.add(symb));
})

let output = [...set].join('');

console.log('output:', output); //irkjdoqew
```

<br></p>
</details> 

[//]: # (Обработка строки — вырезать N восклицательных знаков)
<details id="task-4"><summary><b>Обработка строки — вырезать N восклицательных знаков</b></summary><p>

**Задача**
- Напишите функцию, которая принимает строку и удаляет из неё N восклицательных знаков
```js
  const removeExclamations = (str, count) => {};
  console.log(removeExclamations('!!!Hello, !!world!', 5)) //Hello, world!
```

**Решение**
- Решил через `map`. Можно было через `filter`, но так тоже ок.
```js
const removeExclamations = (str, count) => {
    let strArray = str.split('');
    let result = '';
    strArray.map(symbol =>{
        if((symbol === '!') && (count > 0)) {
           count--;
           return;  
        }
        else {
            result = result + symbol;
        }
    });
    return result;
};
console.log(removeExclamations('!!!Hello, !!world!', 5)) //Hello, world!
```

<br></p>
</details> 

[//]: # (Найти пересечение двух массивов чисел)
<details id="task-5"><summary><b>Найти пересечение двух массивов чисел</b></summary><p>

Написать функцию находящую пересечение двух массивов чисел.
  
**Задача**
```js
const a = [1, 10, 2, 6, 9, -32];
const b = [-7, 1, 9, 8, 0, 1, 10];
const intersect = (a,b) => {
//your code here
}
//console.log(intersect(a,b)); //[1,9,10]
```

**Решение**
```js
const a = [1, 10, 2, 6, 9, -32];
const b = [-7, 1, 9, 8, 0, 1, 10];

const intersect = (a, b) => {  
  let bCopy = [...b];  
  let result = new Set;  
  
  a.map((itemA, index) => {
    bCopy.forEach(itemB => {
        (itemA === itemB) && result.add(itemA); 
    })  
  })  
  return Array.from(result);}  
  
console.log(intersect(a, b)); //[1,9,10]
```

<br></p>
</details> 

[//]: # (Сортировка массива чисел по их квадратам)
<details id="task-6"><summary><b>Сортировка массива чисел по их квадратам *</b></summary><p>

- Отсортировать исходный массив положительных и отрицательных чисел по их квадратам. 
- Использовать алгоритм не требующий много памяти

**Решение 1 — «в лоб»**
```js
let orig = [-1,3,1,7,-5,2];
console.log(original)
let abs = orig.map(item => Math.abs(item))
let final = abs.sort((a, b) => (a*a) - (b*b) );
console.log(final)
```

<br></p>
</details> 

[//]: # (React. Создать компонент, который по нажатию кнопки создаёт новый <input>, с валидаций)
<details id="task-7"><summary><b>React. Создать компонент, который по нажатию кнопки создаёт новый «input», с валидаций</b></summary><p>

**Задача**
- написать React-компонент, который по нажатию кнопки создаёт новый инпут. Все значения валидируются формой validate. Если форма невалидна — кнопка «Сохранить» disabled.
- Добавление любого количества input'ов по кнопке
- Валидация введённого во все input значения с помощью функции `validate`
- Если форма не валидна - кнопка «Сохранить» должна быть `disabled`

**Решение**
```tsx
import { useState, useEffect, useRef } from "react";

const App:PropTypes = () => {
  let [fieldsetCount, setFieldsetCount] = useState(0);
  let [fields, setFields] = useState<any>({});
  let [formStatus, setFormStatus] = useState(false);
  const itemsRef = useRef<HTMLInputElement>();

  const range = (count:number) => {
    if(count > 0) {
      return Array(count).fill(count)
    } else {
      return [];
    }
  };

  const submitForm = (e: React.FormEvent<HTMLInputElement>) => {
    e.preventDefault();
    // some submit logic will be here
    console.log('submit')
    return true
  }

  const isInputValid = (value:string) => {
    // some validation logic will be here
    let result = true;
    console.log(`validation of ${value} is ${result}`)
    return result;
  };

  const isFormValid = () => {
    if(fieldsetCount > 0) {
      for (let key in fields) {
        if (!fields[key].isValid) {
          setFormStatus(false);
          return false
        }
      }
      setFormStatus(true);
      return true
    }
  };

  const addFieldset = () => {
    const name = fieldsetCount + 1;
    setFieldsetCount(count => count + 1)

    setFields({
      ...fields,
      [name]: {
        isValid: false,
      },
    })
  }

  const handleInputChange = (e:any) => {
    const name = e.target.name;
    const value = e.target.value;
    const currentField = itemsRef.current[name];
    if(isInputValid(value)) {
      setFields({
        ...fields,
        [name]: {
          isValid: true,
        },
      })
      currentField.classList.add("valid");
    } 
    else {
      setFields({
        ...fields,
        [name]: {
          isValid: false,
        },
      })
      currentField.classList.add("invalid");
    }
  }

  const FieldsetsGroup = range(fieldsetCount).map((field, index) => {
     const fieldName = index+1;
     return <fieldset key={fieldName}>
      <input 
        type="text" 
        name={fieldName} 
        ref={el => (itemsRef.current[fieldName] = el)}
        onChange={e => handleInputChange(e)}
      />
    </fieldset>
  });
  
  useEffect(() => isFormValid());

  const ButtonSubmit = <button 
    type="submit" 
    onClick={submitForm}
    disabled={!formStatus}
  >
    Submit
  </button>;


  const ButtonAddField = <button onClick={() => addFieldset()}>
    Add intput ({fieldsetCount})
  </button>


  return (
    <>
      <form className="App" onSubmit={submitForm}>
        {FieldsetsGroup}
        {ButtonSubmit}
      </form>
      {ButtonAddField}
    </>
  );
}
```

<br></p>
</details> 

[//]: # (React. Найти все ошибки в компоненте. Типизировать хук useState)
<details id="task-8"><summary><b>React. Найти все ошибки в компоненте. Типизировать хук useState()</b></summary><p>

**Задачка**
```
//Найти все ошибки
export const ComponentA = () => {
  const [state, setState] = useState([
    {id: 1, name: "a", status: true}, 
    {id: 2, name: "b", status: false}, 
    {id: 3, name: "c", status: true}, 
  ])

  return (
    <div>
      {state.map((item, index) => (
         <div>
           <label key={index} for={item.id}></label>
           <input type="caheckbox" id={item.id} onChange={ev => {
               state[index].status = ev.target.checked;
           }}/>
           {item.name}
         </div> 
      ))}
    </div>
  )
}
```
<br>
<br>

**Решение (проверить могут быть ошибки)**
```

export const ComponentA = () => {
  const [state, setState] = useState<Array<{id:number, name:string, status:boolean}>>([
    {id: 1, name: "a", status: true}, 
    {id: 2, name: "b", status: false}, 
    {id: 3, name: "c", status: true}, 
  ])

  const setStatus = (e) => {
    setState([
      //...state,
      //state[index].status = e.target.checked
      state.map((item,index) => {
         if(item.id === e.target.id){
           return {
             ...item,
             status: e.traget.checked,
           }
         }
         else {
           return item;
         }
      })
    ]);
  }
  
  return (
    <div>
      {state.map((item, index) => (
         <div>
           <label key={index} for={item.id}></label>
           <input type="caheckbox" id={item.id} onChange={ev => setStatus(e)}/>
           {item.name}
         </div> 
      ))}
    </div>
  )
}

```
<br>
<br>

**Комментарии**
- key ставить родительскому элементу внутри map(), а не вложенном элементу
- почему в key лучше использовать id, а не index
- onChange - использовать SetState() вместо прямого присваивания нового значения (state[index].status =
  e.target.checked)
- вообще концептуально неправильно ориентироваться на e.target.checked — лучше оперировать pRevState

<br></p>
</details> 

[//]: # (Написать асинхронную функцию запроса данных. 5 попыток. Промис)
<details id="task-9"><summary><b>Написать асинхронную функцию запроса данных. 5 попыток. (Промис)</b></summary><p>

Написать функцию getData, которая запрашивает данные по url и
в случае неуспешного запроса, повторяет его еще 5 раз
в случае неудачи возвращает ошибку “Заданный URL недоступен”
Как делаем запрос (fetch или что-то ещё - не важно)

```js
function getData() { }

getData('https://example.com')
  .then(console.log)
  .catch(console.error)
```

Решение 2
```js
const getData = str  => {return new Promise(
  (resolve, reject) => {

    let getResult = (str) => {
      const numb = +(Math.random() * 10). toFixed(4);
      return numb;
    }
    let result = getResult('STEP '+ 1);
    let count = 1;

    for(; count<6; count++) {

      if (result > 9) {
        console.log('Finish')
        resolve('YES!!!');
        break
      }
      else {
        result = getResult('STEP '+ (count+1));
      }
    }

    if(count === 6) {
      reject('Noooo')
    }

  }
)}

getData('AAA')
.then(result => console.log(result))
.catch(err => console.error(err));

```

Решение 1
```js
  function getData(str) { 
    console.log('getData start')

    let getResult = (str) => {
      //console.log('getResult', str);
      const numb = +(Math.random() * 10). toFixed(4);
      return numb;
    }
    let result = getResult('STEP '+ 1);

    for(let i=1; i<6; i++) {
      console.log('st-',i);
      console.log('result', result);

      if (result > 5) {
        console.log('Finish')
        return true;
      }
      else {
        result = getResult('STEP '+ (i+1));
      }
    }
  }

```

<br></p>
</details> 

[//]: # (Написать асинхронную функцию запроса данных. 5 попыток. Промис)
<details id="task-10"><summary><b>Написать синхронную функцию генерации случайного числа > Х. 5 попыток.</b></summary><p>

- Написать синхронную функцию
- Внутри функции генерируем случайное число
- Если число больше 0,5 - возвращаем его
- Если число меньше 0,5 - вызываем снова. И так 5 раз
- Если 5 раз неудача - выводим console.log

ВАРИАНТ через рекурсию
```js
function getNumberRec(count=5) {
  const randomNumber = Math.random();
  
  if (randomNumber > 0.9) {
    return(randomNumber);
  } 
  else {
      count--;
      if(count > 0) {
        getNumberRec(count);
      }
  }
}
getNumberRec();
```

ВАРИАНТ через for
```js
function getNumber() {
    let randomNumber = Math.random();
    
    if(randomNumber > 0.7) {
      console.log('Finish');
    } else {
      for(let i=0; i<6; i++) {
        randomNumber = Math.random();
      }
    }
}
getNumber();
```

ВАРИАНТ через while
```js
function getNumber() {
  let randomNumber = Math.random();
  let counter = 5;

  while(counter > 0) {
    console.log(`Step ${counter} randomNumber = ${randomNumber}`);
    if (randomNumber > 1) {
      console.log('randomNumber', randomNumber);
      return randomNumber;
    }
    else {
      randomNumber = Math.random();
      counter --;
    }
  }
}
```

<br></p>
</details> 

[//]: # (TypeScript. Типизировать функцию *)
<details id="task-11"><summary><b>TypeScript. Типизировать функцию *</b></summary><p>

**Задачка**
```js
/* 
 Есть объект X (произвольный) и функция getProperty, которая на вход принимает произвольный объект 
 и строковое значение свойств
 необходимо при помощи TypeScript допилить функцию getProperty таким образомю чтобы на этапе написания кода 
 в строке getProperty(X, 'm') компилятор выдавал ошибку «Argument of type '"m"' is not assignable to parameter of type '"a"' | '"b"' | '"c"' | '"d"'»
*/

const X = {a:1, b: 2, c: 3, d:4}
  
let getProperty = function(obj, key){
  return obj[key]
}
  
//getProperty(X,a)
//getProperty(X,m) 
  
// Должно получиться что-то вроде: 
// let getProperty:<V extends Record<string, >, T extends keyof V> = function(obj: V, data: T) => number;
```  

<br></p>
</details> 

[//]: # (React. Console.log внутри setTimeout внутри UseEffect *)
<details id="task-12"><summary><b>React. Console.log внутри setTimeout внутри UseEffect() *</b></summary><p>

- в `return ()` компонента есть кнопка. При клике она увеличивает счётчик в `useState()`
- есть `useEffect()`, в нём `setTimeout`, в нём `console.log`, который выводит значения счётчика
- если мы быстро нажмем несколько раз на кнопку (прям моментально) — какие значения выведет `console.log`?

**Задача**
```jsx
//Что будет выведено в console.log если очень быстро нажать 3 раза подряд на кнопку?

import React, {useStae, useEffect} from "react";
import ReactDOM  from "react-dom"; 

function Exmple() {
  const [count, setCount] = useState(0);
  
  useEffect(() => {
    setTimeout(() => {
      console.log(`You clicked ${count} times`)
    }, 3000);
  });
  
  return (
    <div>
      <p>You clicked {count} times</p>
      <button onClick={() => setCount(count +1)}>
        Click me
      </button>
    </div>    
  )
}

const rootElement = document.getElementById("root");
ReactDOM.render(<Example />, rootElement);
```

**Решение**
- Будут выведены числа 1-2-3
- При каждом клике useEffect создаёт замыкание и запоминает своё значение useState. 
- Когда таймер отработает — он возьмёт значение из замыкания
- Как-то так
- +
- выведет 1,2,3... - при каждом клике меняется счётчик в useState(), его значение хранится в замыкании с `setTimeout`
- когда таймер «дотикает» — он выведет в консоль значения счётчика из замыкания

<br></p>
</details>

[//]: # (Алгоритмы. Есть линейный график из множества точек, предложить алгоритм его построения *)
<details id="task-13"><summary><b>Алгоритмы. Есть линейный график из множества точек, предложить алгоритм его построения * </b></summary><p>

- К сожалению картинка графика не сохранилась, опишу «на пальцах» 
- График состоит из множества близко расположенных точек
- график растёт, но не равномерно, а как «зубья пилы»
- На локальных максимумах цвет точек меняется: те что «локально повыше» - ближе к красному, те что пониже - к синему.
- цвет меняется именно локально, а не абсолютно
  - Предположим, число = высота точек по y
  - `a`=3, `b`=4, `c`=6, `d`=3.7, `e`=4.5, `f`=7, `g`=6.2
  - тогда точки `с` и `f` будут по цвету ближе к красному
  - а точки `a`, `d` и `g` — ближе к синему
  - примерно так

<br></p>
</details> 

[//]: # (Поиск квадратного корня *)
<details id="task-14"><summary><b>Поиск квадратного корня *</b></summary><p>

- Реализовать алгоритм поиска квадратного корня числа S, не используя математические методы `sqrt`, `pow` и `log`.
- Для простоты ищем целочисленный положительный корень.
- Есть несколько алгоритмов.
- PS: вместо `pow` можно использовать побитовый сдвиг. Побитовый сдвиг влево на N позиций эквивалентен умножению числа на 2N
- PPS: вроде бы есть способы получить квадратный корень при помощи побитого сдвига. Но это не точно. [Пример](https://question-it.com/questions/2518187/obedinenie-kvadratnogo-kornja-i-bitovyj-sdvig)

Суть задачи:
- Для решения этой и подобных задач надо знать вычислительные методы в математике (теория рядов, разложение в ряды).
- Т.е. основа — вычислительная математика + оценка.
- В паре слов: любую подобную функцию можно решить (с опр. точностью) через [ряд Телора](): 
  - что-то вроде `e^x = 1 + x/(1!) + x^2/(2!) + x^3/(3!)...`
  - точнее так: `f(x) = f(a) + f'(a)(x-a) + (((f^2)*a)/2!)*(x-a)^2 + ... + (((f^k)*a)/k!)*(x-a)^k`
- Есть разные ряды, кроме ряда Тейлора. 
- Ряды «сходятся» быстро и медленно - т.е. разное количество итераций. Т.е. разная алгоритмическая сложность.
- Правильно подобрать ряд для данного случая — отдельная сложная задача. Надо изучать вопрос, гуглить, считать и т.д.

Ниже идут решения «в лоб», без знания рядов и т.д.<br>
Надо бы изучить и дополнить...

**Геометрический метод**
```js
/*
- Площадь квадрата со стороной A равна S = A*A
- Нужно построить такой квадрат, что его площадь будет равна S, тогда длина стороны квадрата будет искомым корнем (a = sqrt(S))
- Строим итеративно
- Вначале посторим прямоугольник, у которого одна сторона = S, а другая = 1. 
- Площадь такого прямоугольника совпадает с площадью исходного квадрата.
- Если при этом длины сторон отличаются на величину допустимой погрешности вычислений Eps — сторона прямоугольника является ответом.
- Если же стороны различаются слишком сильно — то мы усредняем одну из сторон (a), а вторую вычислить как b = S/a. 
- Т.к. одна сторона усредняется, разница длин сторон сокращается.
- Вторая сторона вычисляется так, чтобы площадь прямоугольника не изменялась.
).

- Этот алгоритм ищет корни не из всех чисел, если не нашёл - вернёт «undefined». Например sqr(12) — undefined
*/

const sqr = (num) => {
  let height = 1;
  let width = num;

  for(let i = 0; i <= num; i++){
    //Здесь в исходном алгоритме была проверка на отличие от заранее заданной погрешности Eps. 
    // Т.е. (Math.abs(width - height) > Eps)
    if (Math.abs(width - height) === 0 ) {
      return height
    }
    else {
      height = (height + width)/2;
      width = num/height;
    }
  }
};

console.log(sqr(16)); //4
console.log(sqr(25)); //5

```

**Бинарный поиск**
```js
/*
- Делим находим число Х посередине интервала 0-S 
- Проверяем — является ли X искомым. 
- Если нет - повторяем тот же процесс с одной из оставшихся половин 
   - если X больше искомого — c интервалом 0-X, 
   - иначе с интервалом X-S
*/

const sqr = (num) => {
  let min = 0;
  let max = num;
  let t = num;
  let mid;

  while(true) {
    mid = (min + max)/2; //можно округлить через Math.round() — тогда на выходе будут целые числа
    let pow = mid*mid;

    if ((mid===t) || (pow === num)) {
      console.log('final — ', 'mid', mid, 'pow', pow, 't', t )
      break
    }
    else if (pow < num) {
      console.log('pow < num', pow, '<', num )
      min = mid
    }
    else {
      console.log('pow > num', pow, '>', num )
      max = mid
    }
    t = mid;
  }
  return mid;
};

console.log(sqr(16)); //4
console.log(sqr(25)); //5

```

**Бинарный поиск, с использованием степеней Math.pow()**
```js
/*
- Возведение в квадрат — операция обратная получению квадратного корня
- Math.pow(a,2) === Math.sqrt(b)
- можно реализовать то же самое, но вместо Math.pow(middle,2) использовать (middle * middle)

- Этот алгоритм ищет только целочисленные положительные корни, если такого нет - вернёт «undefined». 
    - Например sqr(11) — undefined
*/

const sqr = (num) => {
  let min = 1;
  let max = num;

  for(let i = 0; i <= num; i++){
    let middle = min + Math.round((max - min) / 2);
    let assumption = Math.pow(middle, 2);

    if (assumption === num) {
      return middle
    }
    else if (assumption > num) {
      max = middle;
    }
    else {
      min = middle;
    }
  }
};

console.log(sqr(16)); //4
console.log(sqr(25)); //5
```

**Бинарный поиск, С использованием логарифмов Math.log()**
```js

/*
- Логарифм - операция, обратная возведению в степень. 
- logA(B) — в какую степень нужно возвести A, чтобы получить B. 
- Пример
  - log2(16) = 4. 
  - Степень — какое число получим, если умножим 4 само на себя Х раз (степень 2 = умножим само на себя 1 раз) 
  - Логарифм — в какую степень надо возвести 2, чтоб получить 16
  - Корень — какое число надо возвести в степень 2, чтоб получить 16

- Задача сводится к поиску основания логрифма. 
- Известен его аргумент (число из которого берём корень) и значение (2, т.к. корень квадратный)
- Перебираем разные числа в основания для заданного аргумента, и смотрим - равен ли ответ двум? 
*/
const sqr = (num) => {
  let min = 1;
  let max = num;

  for(let i = 0; i <= num; i++){
    let middle = min + Math.round((max - min) / 2);
    let assumption = Math.log(num) / Math.log(middle); //  т.е. log middle(num)

    if (assumption === 2) {
      return middle
    }
    else if (assumption < 2) {
      max = middle;
    }
    else {
      min = middle;
    }
  }
};

console.log(sqr(16)); //4
console.log(sqr(25)); //5
```

**Ссылки**
- [Алгоритмы. Вычисление целочисленного квадратного корня. Реализация в Python и Java.(YouTube)](https://youtu.be/1GxkwIIvfQM)
- [Алгоритмы вычисления квадратного корня](https://pro-prof.com/forums/topic/sqrt-algorithm)
- [stackoverflow.com - Вычисление квадратного корня без библиотечных методов](https://ru.stackoverflow.com/questions/566475/%D0%92%D1%8B%D1%87%D0%B8%D1%81%D0%BB%D0%B5%D0%BD%D0%B8%D0%B5-%D0%BA%D0%B2%D0%B0%D0%B4%D1%80%D0%B0%D1%82%D0%BD%D0%BE%D0%B3%D0%BE-%D0%BA%D0%BE%D1%80%D0%BD%D1%8F-%D0%B1%D0%B5%D0%B7-%D0%B1%D0%B8%D0%B1%D0%BB%D0%B8%D0%BE%D1%82%D0%B5%D1%87%D0%BD%D1%8B%D1%85-%D0%BC%D0%B5%D1%82%D0%BE%D0%B4%D0%BE%D0%B2)
- [Wikipedia - Методы вычисления квадратных корней](https://ru.wikipedia.org/wiki/%D0%9C%D0%B5%D1%82%D0%BE%D0%B4%D1%8B_%D0%B2%D1%8B%D1%87%D0%B8%D1%81%D0%BB%D0%B5%D0%BD%D0%B8%D1%8F_%D0%BA%D0%B2%D0%B0%D0%B4%D1%80%D0%B0%D1%82%D0%BD%D1%8B%D1%85_%D0%BA%D0%BE%D1%80%D0%BD%D0%B5%D0%B9)
- [Habr — [Неочевидные алгоритмы очевидных вещей] Алгоритм 1. Корень квадратный](https://habr.com/ru/post/128468/)
- [Про крони, степени и логарифмы](https://dzen.ru/media/math_easy/bazovye-matematicheskie-operacii-i-ih-svoistva-slojenie-i-vychitanie-umnojenie-i-delenie-stepen-koren-logarifm-62420246729bf019a65b1d05)
- [mathway.com](https://www.mathway.com/ru/Algebra)

<br></p>
</details> 

[//]: # (Все ли символы строки уникальны  *)
<details id="task-15"><summary><b>Все ли символы строки уникальны *</b></summary><p>

- Проверить строку на уникальность символов (т.е. есть ли в ней повторяющиеся символы — да/нет)

- есть три решения
  - приводим строку к массиву `orig`, символы из строки пишем в массив `result`, и сравниваем `orig` и `result`. Сложность `O(n + n^2)`
  - из строки символы по одному присваиваем в объект hashMap (ключ = символ, значение = индекс символа в строке). Тогда при попытке присвоить второй такой же символ - он присвоится существующему. Потом можно посмотреть размер массива, например. И сравнить с длиной строке. Сложность алгоритма будет проще
  - символы строки присвоить коллекции Set и сравнить str.length === Set.size. Сложность `O(n)`

```ts
/* Варинат 1.
Сложность O(n + n^2)
  - разбор строки через split = O(n)
  - добавляем к этому перебор массива через map = O(n + n)
  - добавляем к этому перебор массива forEach внутри map = O(n + n*n)
*/
const isStringUnique = (str:string):boolean => {
  let strArray = str.split('');
  let resultArray = [];
  let result = true;

  strArray.map(symb => {
    if(resultArray.length > 0){
      resultArray.forEach(item => {
        if(symb === item){
          result = false;
          return false;
        } else {
          resultArray.push(symb);
        }
      })
    } else {
      resultArray.push(symb);
    }
  });

  return result;
}

console.log(isStringUnique('ssdsau')); // not
console.log(isStringUnique('sdau')); // yes
```

```ts
/* Варинат 2.
Сложность  ???
*/
const isStringUnique = (str:string):boolean => {
  let resultObj = {};

  [...str].forEach((symb, index) => {
    resultObj[symb] = index;
  })
  
  return (str.length === Object.keys(resultObj).length);
}

console.log(isStringUnique('ssdsau')); // not
console.log(isStringUnique('sdau')); // yes
```

```ts
/* Варинат 3.
Сложность  O(n)?
*/
const isStringUnique = (str:string):boolean => {
  return (str.length === new Set(str).size);
}

console.log(isStringUnique('ssdsau')); // not
console.log(isStringUnique('sdau')); // yes
```

<br></p>
</details> 

***

<br></p>
</details> 

[//]: # (Популярные задачки)
<details><summary><b>Популярные задачки</b></summary><p>

****

[//]: # (Использование var/let в «for»)
<details><summary><b>Использование var/let в «for()»</b></summary><p>

Использование `var`/`let` в `for()`.<br>
Могут дать в связке с «замыканиями» или другими задачами.

<br></p>
</details> 

[//]: # (Замыкания - написать функцию, add, чтобы вызов add_1_2_ вернул 3)
<details><summary><b>Замыкания - написать функцию, add, чтобы вызов add(1)(2) вернул 3</b></summary><p>

```js
//Стерлочная
const add = x => y => {
  return x + y;
};
const res = add(3)(6);
console.log(res);  // вернёт 9
```

```js
//Обычная
function fA() {
  var currentCount = 1;
  function fB() { 
    return currentCount++;
  };
  return fB;
}
var counter1 = fA();     
console.log(counter1()); // 1
console.log(counter1()); // 2
console.log(counter1()); // 3

// создаём другой счётчик, он будет независим от первого
var counter2 = fA();
console.log(counter2()); // 1
```

<br></p>
</details> 

[//]: # (Замыкания, this - написать декоратор для кэширования)
<details><summary><b>Замыкания, this - написать декоратор для кэширования</b></summary><p>

```js
let worker = {
  //Вариант 1 -  без func.call(this, x) 
  // здесь может быть страшно тяжёлая задача для процессора
  // alert(`Called with ${x}`);
  // return x;

  //Вариант с использование метода объекта - для демонатрации func.call(this, x) 
  someMethod() {
    return 1;
  },
  slow(x) {
    // здесь может быть страшно тяжёлая задача для процессора
    alert("Called with " + x);
    return x * this.someMethod();
  }
};

function cachingDecorator(func) {
  let cache = new Map();
  return function(x) {
    if (cache.has(x)) { // если кеш содержит такой x,
      return cache.get(x); // читаем из него результат
    }

    // иначе, вызываем функцию
    //Вариант 1 - без привязки this
    // let result = func(x); // вариант 
  
    //Вариант 2 - с привязкой this
    let result = func.call(this, x); // .call() позволяет вызывать функцию, явно устанавливая this.
    cache.set(x, result); //кешируем (запоминаем) результат
    return result;
  };
}

worker.slow = cachingDecorator(worker.slow); // добавляем к функции обёртку-декоратор, делаем её кеширующей

alert( worker.slow(2) ); // работает
alert( worker.slow(2) ); // работает, не вызывая первоначальную функцию (кешируется)
```

- [learn.javascript.ru - Декораторы и переадресация вызова, call/apply](https://learn.javascript.ru/call-apply-decorators)

<br></p>
</details> 

[//]: # (Армия функций *)
<details><summary><b>Армия функций *</b></summary><p>

  - https://learn.javascript.ru/task/make-army
  - https://learn.javascript.ru/let-const
  - https://qna.habr.com/q/365769

<br></p>
</details> 

[//]: # (Рекурсия - возведение в степень)
<details><summary><b>Рекурсия - возведение в степень</b></summary><p>

```js
//через рекурсию
function pow(x, n) {
  if (n == 1) {
    return x;
  } else {
    return x * pow(x, n - 1);
  }
}
alert(pow());
```

```js
//итеартивно, цикл for
function pow(x, n) {
  let result = 1;
  for (let i = 0; i < n; i++) {
    result *= x; // умножаем result на x n раз в цикле
  }
  return result;
}
alert( pow(2, 3) ); // 8
```

<br></p>
</details> 

[//]: # (Рекурсия - поиск факториала)
<details><summary><b>Рекурсия - посик факториала</b></summary><p>

- Число, умноженное на "себя минус один", затем на "себя минус два", и так далее до 1

```js
function fact(n) {
  if(n == 1) {
    return 1
  }
  else {
    return n * fact(n - 1);
  }
}
alert( fact(4) ); // 24
```

- [learn.javascript.ru - Рекурсия](https://learn.javascript.ru/recursion#dva-sposoba-myshleniya]v

<br></p>
</details> 

[//]: # (Рекурсия - вывод односвязного списка *)
<details><summary><b>Рекурсия - вывод односвязного списка *</b></summary><p>

- [learn.javascript.ru - Вывод односвязного списка. Рекурсия, цикл](https://learn.javascript.ru/task/output-single-linked-list)

<br></p>
</details> 

[//]: # (Кофеварка *)
<details><summary><b>Кофеварка *</b></summary><p>

  - один раз написать самому (подсматривая в учебник)
  - https://learn.javascript.ru/private-protected-properties-methods
  - https://learn.javascript.ru/task/add-method-property-coffeemachine
  - https://learn.javascript.ru/task/add-public-coffeemachine
  - https://learn.javascript.ru/functional-inheritance
  - https://learn.javascript.ru/getters-setters

<br></p>
</details> 

[//]: # (Написать debounce функцию *)
<details><summary><b>Написать debounce функцию *</b></summary><p>

- [learn.javascript.ru - Сделать Debounce](https://learn.javascript.ru/task/debounce)
- [doka - Сделать Debounce на примере формы поиска](https://doka.guide/js/debounce/)
- [Habr - Debouncing с помощью React Hooks](https://habr.com/ru/post/492248/)
- [Habr - Debouncing с помощью React Hooks: хук для функций](https://habr.com/ru/company/domclick/blog/510616/)
- [Habr - Микропаттерны оптимизации в Javascript: декораторы функций debouncing и throttling](https://habr.com/ru/post/60957/)

<br></p>
</details> 

[//]: # (Написать throttling функцию *)
<details><summary><b>Написать throttling функцию *</b></summary><p>

- [Habr - Микропаттерны оптимизации в Javascript: декораторы функций debouncing и throttling](https://habr.com/ru/post/60957/)

<br></p>
</details> 

[//]: # (Написать декоратор для кэширования *)
<details><summary><b>Написать декоратор для кэширования *</b></summary><p>

- https://learn.javascript.ru/call-apply-decorators#tasks

<br></p>
</details> 

[//]: # (Предложить разные методы организации кэша для вычисления Фибоначчи *)
<details><summary><b>Предложить разные методы организации кэша для вычисления Фибоначчи *</b></summary><p>

- кэш ограничен 20 значениями, а поступить может хоть 10000 - как оптимизировать?
- часть кэша выделяем под хранение предыдущих вычисленных значений (мемоизация).
- Рекурсия - самый дорогой вариант вычисления Фибоначчи

<br></p>
</details> 

[//]: # (Нормализация данных для проектирования стэйта React)
<details><summary><b>Нормализация данных для проектирования стэйта React</b></summary><p>

- Например: в качестве ответа сервера получаем очень большой неупорядоченный массив - как с ним работать?
- Решение: дробление по принципу связи. Точно не помню, надо повторять, но вроде идея такая - создаём отдельный массив
  для одних сущностей (задачи, например) и отдельный для других (пользователи) и устанавливаем между ними связи.

<br></p>
</details> 

[//]: # (Планирование вызовов через вложенные SetTimeout)
<details><summary><b>Планирование вызовов через вложенные SetTimeout()</b></summary><p>

```js
let delay = 500;
const getData = () => {
  console.log('getData')
    return false
};
  
let timerID = setTimeout(function work(){
      
    if (!getData()) {
        console.log('if')
        delay= delay*2
    }
  
    timerID = setTimeout(work, delay);
  
}, delay)
  
timer();
```

- https://learn.javascript.ru/settimeout-setinterval#vlozhennyy-settimeout

<br></p>
</details> 


***

<br></p>
</details> 

[//]: # (Задачки с собеседований в крупнейшую IT-компанию России)
<details><summary><b>Задачки с собеседований в крупнейшую IT-компанию России (2022)</b></summary><p>

***

[//]: # (Реализовать ф-цию, которая вернет результат выполнения другой ф-ции, в которой коллбек с ошибкой и данными)
<details><summary><b>Реализовать функцию, которая вернет результат выполнения auth(callback(ошибка, данные)))</b></summary><p>

**Задача**
- Есть функция `auth()`, она принимает коллбек, который принимает аргументами ошибку и какие-то данные.
- Написать функцию `asyncAuth()`, которая вернет результат выполнения функции `auth()`.  

**Решение 1 - «В лоб»**
```js
const errorData = new Error('Some error');
const succesData = 'Some data';

const someCallback = (error, data) => {
  if(true) {
    return data;
  }
  return error;
};

const auth = (callback) => {
    return callback();
};

const asyncAuth = (func) => {
  console.log(func());
};

asyncAuth(() => auth(() => someCallback(errorData, succesData)));
```

**Решение 2 - Промис**
```js
const errorData = new Error('Some error');
const succesData = 'Some data';

const someCallback = (error, data) => {
  if(true) {
    return data;
  }
  return error;
};

const auth = (callback) => {
    return callback();
};

const asyncAuth = (func) => {
  return new Promise((resolve,reject) => {
    if(typeof(func()) === 'string') {
      resolve(func());
    }
    reject(func());
  });
};

const promise =  asyncAuth(() => auth(() => someCallback(errorData, succesData)));

promise.then (
  data => console.log(data),
  error => console.log(error)
);
```

<br></p>
</details> 

[//]: # (Объединить пересекающиеся интервалы)
<details><summary><b>Объединить пересекающиеся интервалы</b></summary><p>

**Задача**
- Дана последовательность интервалов.
- Надо объединить те, которые имеют пересечения.
```js
mergeIntervals([[4, 8], [3, 5], [7, 12], [1, 2]]) // => [[3, 12], [1, 2]]
mergeIntervals([[3, 4], [1, 2], [4, 5], [2, 3]]) // => [[1, 5]]
```

**Решение**
```js
const mergeIntervals = (arr) => {
  if(arr.length > 0) {
    const arrCopy = arr.map( item => [...item]);
    let result = [];
    let isResultChanged = false;
    let isAIncludesB = ([a,b], [c,d]) => {return (a < c) && (b > d)};
    let isABIntersect = ([a,b], [c,d]) => {return ((b >= c) && (b <= d)) || ((a >= c) && (a <= d))};

    arrCopy.forEach(intervalAB => {
      if( result.length > 0) {
        result.forEach((item,index) => {
          let [a,b] = intervalAB;
          let [c,d] = item;

          console.log(
            `(${a}-${b}), ${c}-${d} —`,
            isAIncludesB([a,b], [c,d]),
            isAIncludesB([c,d], [a,b]),
            isABIntersect([a,b], [c,d]),
            '—',  (isAIncludesB([a,b], [c,d]) || isAIncludesB([c,d], [a,b]) || isABIntersect([a,b], [c,d]))
          )

          if (isAIncludesB([a,b], [c,d]) || isAIncludesB([c,d], [a,b]) || isABIntersect([a,b], [c,d])) {
            let x =  Math.min(a, c);
            let y =  Math.max(b, d);
            result[index]=([x,y]);
            isResultChanged = true;
          }
          else {
            console.log('Else')
            result.push(intervalAB)
          }
        })
      }
      else {
        result.push(intervalAB)
      }
    });


    if((result.length > 1) && (isResultChanged)) {
      mergeIntervals(result)
    } else {
      console.log('result', result);
      return result;
    }

  }
};

mergeIntervals([[4, 8], [3, 5], [7, 12], [1, 2]]); // => [[3, 12], [1, 2]]
mergeIntervals([[3, 4], [1, 2], [4, 5], [2, 3]]); // => [[1, 5]]
```

**Добавить проверки (TypeScript)**
- в исходном массиве два значения, это числа и они не отрицательные
- сначала идёт меньшее число, потом большее (или равное?)

**Идеи**
- использовать `arrCopy.sort()` — вызывается для каждого элемента. в функции ставить проверку, если ок — записываем в result. Надо использовать другой алгоритм - чтоб сравнивал каждый с каждым
- использовать `arrCopy.filter()`
- использовать `Array.prototype.every()` — возвращает true/false. прерывается после первого false
  - https://developer.mozilla.org/ru/docs/Web/JavaScript/Reference/Global_Objects/Array/every

- Проблема в том, что надо по кругу проверять result. Потому что в result 
  - элементы изменяются в процессе работы алгоритма. К концу обработки элементы могут стать другими - и у них самих возникнут пересечения.
  - у меня могут «через один» стоять несколько элементов, которые надо бы объединить.
- Варианты решения
  - Реализовать полноценную рекурсию. 
    - Для этого надо как-то проверять, есть ли в массиве элементы, которые могут пересекаться
  - использовать какие-то хитрые структуры, типа Map или Set? В принципе да, позволит избежать дублирования. Но кардинально проблему не решает
  - сортировать исходные массивы до начала преобразований? Проблема в том, что элементы содержат по два числа (мин и макс). А сортировать я могу только по одному...
  - обрабатывать исходный массив, а не писать в финальный? Из двух пересекающихся элементов оставляем один новый, старые убираем
  - внутри элементов разбирать два числа (границы мин-макс) в полноценный интервал из набора чисел и работать с ним?


**Рабочие ссылки**
- https://plnkr.co/edit/jXj1QgBx0iPp8IAh?preview
- https://efim360.ru/javascript-kak-najti-razlichiya-v-massivah/
- https://badtry.net/pieriesiechieniie-raznitsa-sliianiie-merge-dvukh-massivov-v-javascript-es6/

<br></p>
</details> 

[//]: # (Реализовать функцию-светофор)
<details><summary><b>Реализовать функцию-светофор</b></summary><p>

**Задача** 
- На понимание асинхронности
- Реализовать функцию, которая в бесконечном цикле выводит в консоль сообщения с определенными интервалами
  - "Зеленый" 25 секунд
  - "Желтый" 5 секунд
  - "Красный" 30 секунд

**Решение**
```js
const trafficLight = () => {
  console.log('Зеленый')

  setTimeout(()=> {
    console.log('Жёлтый')//От Зёлёного до Жёлтого - 25

    setTimeout(()=> {
      console.log('Красный')//От Жёлтого до Красного - 5
      
      setTimeout(()=> test(),30000); // От Красного до Зелёного - 30 

    },5000);
  },25000);
}

trafficLight();
```

<br></p>
</details> 

[//]: # (Вернуть массив одинаковых повторяющихся значений)
<details><summary><b>Вернуть массив одинаковых повторяющихся значений</b></summary><p>

**Задача** 
- Есть 2 массива чисел, отсортированных по возрастанию. 
- Нужно вернуть массив одинаковых повторяющихся значений.
```js
getEquals([1,2,2,3], [2,3,5]); //[2, 3]  
getEquals([1,2,2,3], [2,2,2,2]); //[2, 2]
```

**Решение**
```js
const getEquals = (a, b) => {
  const copyA = [...a];
  const copyB = [...b];
  const result = [];
  
  copyA.map((itemA, indexA) => {
    copyB.forEach((itemB, indexB) => {
      if (itemA === itemB) {
        copyB.splice(indexB,1);
        copyA.splice(indexA,1);
        result.push(itemA);
      }
    })
  })
  return result;
};

console.log(getEquals([1,2,2,3], [2,3,5])); //[2, 3]  
console.log(getEquals([1,2,2,3], [2,2,2,2])); //[2, 2]
```

**Доработка**
- Вместо двух переборов попробовать sort? reduce?
- find и findIndex - поиск первого совпадения
- filter - поиск всех совпадений. Вернёт новый массив.

<br></p>
</details> 


[//]: # (Unsorted)
<details><summary><b>Unsorted</b></summary><p>

- 3 - React. Создать компонент который принимает массив любых валют и для каждой валюты выводит одну и ту же сумму. Плюс отправка.
    - Реализовать компонент, который содержит 2 числовых input. 
    - В input-1 введено значение валюты в рублях, 
    - В input-2 введено значение валюты в долларах. 
    - При изменении в значения в одном input, сумма должна автоматически измениться в другом. 
    - Усложняем. Должен получиться универсальный компонент: 
      - принимает массив любых валют и для каждой валюты выводит одну и ту же сумму. 
      - должна быть кнопка, которая отправляет установленное значение с выбранной пользователем валютой.
- 4 - Реализовать функцию A, которая возвращает функцию B, которая первые N вызовов возвращает `yes`, затем `no`
  ```js
    const t = f(2)  
    t() === 'yes'  
    t() === 'yes'  
    t() === 'no'
  ```
- 5 - Написать класс, который реализует стек, который имеет методы `push`, `pop`, `max`  
    - Каждый метод должен иметь сложность `O(1)`.
- 6 + Реализовать метод который 5 раз пытается сделать запрос
      - Реализовать метод, который принимает url, делает запрос
      - если запрос неудачный, то повторить запрос 5 раз до удачного
      - если всё равно нет ответа, то вернуть ошибку "Ошибка"
- 7 - Вернуть поле объекта по строке-пути
    - Реализовать функцию, которая должна вернуть соответствующее поле объекта. 
    - На вход функция принимает объект и путь до поля объекта. 
    - Путь - это строка разделённая точкой. 
    - `get(obj, 'a.b'); // { c : 'd' }`  
- 8 - Дан массив строк, необходимо сгруппировать анаграммы
  ```js
    groupup(["eat", "tea", "tan", "ate", "nat", "bat"]);
    
    /*Результат  
    [  
      ["ate", "eat", "tea"],  
      ["nat", "tan"],  
      ["bat"]  
    ]
    */
  ```
- 9 - Проверить, что скобки в строке сбалансированы
    - Дана строка, состоящая из букв латинского алфавита, цифр и скобок `{([])}`. 
    - Необходимо проверить, что скобки в строке сбалансированы — на каждую открывающую скобку приходится закрывающая, и скобочные группы не пересекаются.   
    - `isValid("[(){}()()]"); // true`
    - `isValid("{f[o}o]");    // false`
- 10 - Написать HOC  async throttle
  - Реализовать функцию `async throttle`, которая оборачивает асинхронную функцию, таким образом что:  
  - Сначала вызывается переданная функция и возвращается ее результат  
  - Если во время выполнения первого вызова функцию вызвали еще раз, то возвращается результат первого вызова   
  ```js
    const delay = msec => new Promise(resolve => setTimeout(resolve, msec))  
        
    async function countUp (n = 0) {  
      console.log({ n });  
        
      for (let i = 0; i < 5; i++) {  
        console.log(n + i)  
        await delay(250)  
      }  
    }  
        
    // Your code...  
        
    async function run() {  
      const throttledCountUp = asyncThrottle(countUp)  
        
      throttledCountUp(0) // Запустит  
      throttledCountUp(10) // Пропустит  
      await throttledCountUp(20) // Пропустит, но дождется завершения throttledCountUp(0)  
         
      throttledCountUp(30) // Запустит  
    }  
        
    run()
  ```
- 13 - Реализовать класс паттерна Observer (наблюдатель)
  - Паттерн Observer (наблюдатель). Описать, дать небольшую реализацию в виде класса.
- 14 - Написать функцию, которая выдает сумму всех значений листьев бинарного дерева чисел
  - Дано бинарное дерево из чисел. Форма:  
  ```js
    class Node {  
      constructor(val, left = null, right = null){  
        this.val = val  
        this.left = left  
        this.right = right  
      }  
    }
  ```
    - Нужно написать функцию, которая выдает сумму всех значений листьев (нодов без потомков)
    - Реализовать эту функцию без рекурсии (DFS, со стеком и посещенными нодами)
- 15 - Что будет в консоли и почему
  ```js
  var i = 10;  
  var array = [];  
    
  while(i--) {  
    array.push(function (){  
        return i + i;  
    })  
  }  
    
  console.log(array[0]())  
  console.log(array[1]())  
  ```
- 16 - Написать функцию range
  - написать функцию range  
  ```js
  range(start,stop,step =1); 
  range(10) // [0,1,2,3,4,5,6,7,8,9]  
  range(-6) // []  
  range(0) //[]  
  range(-6, 0, -1)  
  ```  
<br></p>
</details> 


***

<br></p>
</details> 

<br>
<br>

*[Legmo, 2019-2022](https://github.com/Legmo/notes/)*