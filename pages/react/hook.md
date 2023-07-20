# Table Of Content

- [Table Of Content](#table-of-content)
- [React Hooks](#react-hooks)
  - [1. `useState()`](#1-usestate)
  - [2. `Two way binding`](#2-two-way-binding)
  - [3. `useEffect()`](#3-useeffect)
  - [4. `useRef()`](#4-useref)
  - [5. `React.memo()`](#5-reactmemo)
  - [6. `useCallback()`](#6-usecallback)
  - [7. `useMemo()`](#7-usememo)
  - [8. `useImperativeHandle()`](#8-useimperativehandle)
  - [9. `useReducer(reducer, initState)`](#9-usereducerreducer-initstate)
    - [9.1 Với những component đơn giản, nhỏ, props chỉ truyền xuống con gần nhất thì ta chỉ cần dùng `useState()`](#91-với-những-component-đơn-giản-nhỏ-props-chỉ-truyền-xuống-con-gần-nhất-thì-ta-chỉ-cần-dùng-usestate)
    - [9.2 Với những component phức tạp, nhiều state, props drilling thì ta có thể dùng `useReducer()`](#92-với-những-component-phức-tạp-nhiều-state-props-drilling-thì-ta-có-thể-dùng-usereducer)
  - [10. React Context và `useContext()`](#10-react-context-và-usecontext)
  - [11. Tạo fake api server bằng json-server](#11-tạo-fake-api-server-bằng-json-server)

# React Hooks

## 1. `useState()`

- Cách dùng:

```jsx
const [state, setState] = useState(initState);
```

- **_setState với callback_**: _setState sẽ lấy giá trị trả về của callback để set lại giá trị_

VD:

```jsx
const [counter, setCounter] = useState(1);
const handleIncrease = () => {
  setCounter(prevCounter => prevCounter + 1);
};
```

- **_initState với callback_**: _initState có thể là mảng, số, null, NAN nhưng với TH là hàm thì sẽ lấy giá trị mà hàm trả về để làm initState (nếu hàm không trả về thì là undefined)_

```jsx
const orders = [100, 200, 300];

function App() {
  const [counter, setCounter] = useState(() => {
    const total = orders.reduce((total, cur) => total + cur, 0);
    return total;
  });
}
```

## 2. `Two way binding`

- Text input
- Raio
- Checkbox

## 3. `useEffect()`

- `useEffect(callback)`:

  - Gọi callback sau khi component được mounted
  - Gọi callback sau khi component được re-render
  - Hàm callback sẽ được thực hiện sau khi UI được render (Tức là thực hiện nội dung của return rồi sau đó mới thực hiện nội dụng của hàm callback)

- `useEffect(callback, [])` (Thường được dùng để call API):

  - Callback chỉ được gọi duy nhất 1 lần khi component được mounted
  - Component re-render thì không thực hiện callback lần nữa
  - Hàm callback sẽ được thực hiện sau khi UI được render (Tức là thực hiện nội dung của return rồi sau đó mới thực hiện nội dụng của hàm callback)

- `useEffect(callback ,[deps])` (Thường được dùng để call API)

  - Gọi callback sau khi component được mounted
  - Gọi callback sau khi deps thay đổi
  - Hàm callback sẽ được thực hiện sau khi UI được render (Tức là thực hiện nội dung của return rồi sau đó mới thực hiện nội dụng của hàm callback)

- Hàm clean up trong uesEffect
  - Dùng để clear events (VD: `window.addEventListenter()`, `document.addEventListener()`)
  - Dùng để `clearTimeout()`, `clearInterval(0)`
  - Lưu ý:
    - Với `useEffect(cb,[])` thì hàm clean up sẽ được gọi khi component unmount.
    - Với `useEffect(cb,[deps])` hàm clean up sẽ được gọi khi component unmount và khi deps thay đổi (component render lại) thì hàm clean up sẽ được gọi trước (clean up này là của useEffect trước) rồi sau đó với gọi hàm callback (callback này của useEffect sau)

## 4. `useRef()`

- Use cases:

```jsx
const ref = useRef(null)
  ref.current = setTimeout(...) // hoặc setInterval
  clearTimeout(ref.current)
```

- Tạo 1 biến tham chiếu có phạm vi ngoài component (VD: Khi component được re-render lại thì biến sẽ không bị tạo lại)

- `useRef` sẽ luôn trả về 1 object, giá trị thật sự mà ta muốn sử dụng sẽ ở `object.current`

VD:

```jsx
const object = useRef({ name: 'Hieu', age: 20 });
console.log(object.current); // {name: 'Hieu', age: 20}
```

- Tham chiếu đến 1 DOM Element (Nếu DOM Element có thay đổi giá trị thì ref cũng auto được thay đổi theo)

```jsx
const h1Ref = useRef();
console.log(h1Ref);

return <h1 ref={h1Ref}></h1>;
```

## 5. `React.memo()`

https://react.dev/reference/react/memo

- Use cases: Khi component con nhận props từ cha (nhận biến primitive, hoặc hàm - hàm tính toán, nếu là hàm onClick, ... thì không nên sử dụng) thì nên sử dụng useMemo

- Là 1 `HOC` **(Higher Order Component)** dùng để bọc component

- Khi 1 component cha được render (khi được mount), re-render (khi được setState) thì component con cũng được render hoặc re-render lại. React.memo() có tác dụng bọc component con lại, kiểm tra xem có props nào từ component cha truyền vào component con bị thay đổi không, nếu không thay đổi (hoặc thậm chí không có props nào được truyền nào) thì không thực hiện lại re-render component con

VD:

```jsx
const Content = () => {...}

export default React.memo(Content, compareFunction?);
```

## 6. `useCallback()`

- Use cases:

  - Khi trong `useEffect` gọi 1 hàm ngoài (thường là hàm tính toán), hàm ngoài này làm DEPS cho useEffect, khi đó ta nên sử dụng useCallback cho hàm ngoài đó

  - Khi muồn truyền 1 hàm từ cha làm props cho con, nên sử dụng useCallback cho hàm đó và đồng thời sử dụng React.memo() cho hàm con

- Khi 1 component cha được re-render lại (do setState) thì các biến được tạo lại (biến cũ đã bị xoá,có thể ngăn tạo lại bằng cách dùng useRef), các hàm cũng được tạo lại (các hàm cũ bị xoá ,có thể ngăn tạo lại bằng cách dùng callback) và component con được re-render lại (có thể dùng memo để kiểm tra xem props truyền từ component cha vào component con có thay đổi không, nếu không đổi thì không re-render lại component con)

- Props truyền vào component con (component con có sử dụng memo()) có thể là biến, hàm vậy ta có thể sử dụng useRef và useCallback cho các biến, hàm này truyền vào làm props cho component con để tránh việc component con bị re-render lại không cần thiết

- `useCallback(callback, [])`: _trả về 1 hàm được tạo ra khi component mount và không tạo lại hàm khi component re-render_
- `useCallback(callback, [deps])`: _trả về 1 hàm được tạo ra khi component mount và tạo lại hàm khi deps thay đổi (ví dụ hàm phụ thuộc vào deps)_

- VD:

```jsx
const handleIncrease = useCallback(() => setCount(prev => prev + 1), []);
...
<Content onIncrease={handleIncrease} />;

// Content đã được bọc memo(Content)
```

## 7. `useMemo()`

- Use cases:

  - Muốn nhận kết quả từ 1 hàm tính toán logic (expensive - n hoặc n log n, ...)

- Với `useEffect()`: **_callback được truyền vào thực hiện sau khi re-render Component, re-render UI rồi mới thực hiện nội dung trong callback. useEffect() không trả về 1 giá trị gì mà chỉ thực hiện logic trong callback_**

- Với `useMemo()`: **_useMemo sẽ trả về giá trị mà callback trả về (useMemo dùng để thực hiện 1 tính toán, 1 phép logic cần kết quả trả về). Nếu hàm callback trong useEffect sẽ được thực hiện sau khi render UI (tức là luôn được thực hiện cuối cùng) thì callback trong useMemo được thực hiên trước khi render UI (tức là re-render Component - load lại Component, thực hiện callback trong useMemo, re-render UI)_**

- `useMemo(callback, [])`: _chỉ được thực hiện 1 lần khi component mount_
- `useMemo(callback, [deps])`: _được thực hiện khi component mount và khi deps thay đổi_

VD:

```jsx
const total = useMemo(() => {
  console.log('Re-caculatate');
  return products.reduce((total, cur) => total + cur.price, 0);
}, [products]);
```

## 8. `useImperativeHandle()`

- **Bài toán**: _Có 1 biến useRef ở component cha muốn truyền xuống cho component con (để chỉ biến useRef của component cha tới 1 DOM element của component con)_

- **Vấn đề 1**:

  - Chỉ có DOM Element thật sự trong React mới có props `ref (ref={nameRef})`
  - Các function component không thể có props ref (nên không thể truyền biến useRef ở component cha qua component qua theo cách thông thường)

- **Giải pháp 1**: Sử dụng **HOC (Higher Order Component)** `forwardRef` cho component con (Có tác dụng truyền ref từ component cha qua component con). Ref này sẽ làm đối số thứ 2 cho function component con

- VD:

```jsx
function Child (props, refFromParent) {...}
```

VD:

```jsx
// Parent.js

...

  const refFromParent= useRef();
  return (
    <>
      <Child ref={refFromParent}/>
    </>
)
```

```jsx
// Child.js

import {forwardRef} from 'react'

function Child (props, refFromParent) {
  ...
  <input ref={refFromParent} />
}
export default forwardRef(Child);
```

- **Vấn đề 2**: _Sau khi thực hiện như **giải pháp 1** thì ta đã có biến `ref` ở Parent chỉ thẳng tới DOM Element ở Child. Vấn đề là biến ref ở Parent này lại có thể truy cập (làm tất cả mọi thứ với DOM Element ở Child thông qua các hàm như DOM JS bình thường), ta chỉ muốn ref này có thể sử dụng 1 số hàm (chức năng) mà Child cung cấp (Ví dụ Parent chỉ sử dụng 2 hàm A() và B() thì Child chỉ cung cấp 2 hàm A() và B() thông qua refFromParent) (Mục đích của việc này để đảm bảo tính an toàn - tránh việc Parent gọi đến 1 số hàm ngoài phạm vi khiến child bị lỗi, tính đóng gói - chỉ cái gì cần thì mới cho bên ngoài dùng)_

- **Giải pháp**: _Sử dụng `useImperativeHandle(ref, callback)`_

VD:

```jsx
useImperativeHandle(refFromParent, () => (
    {
      function A() {...},
      function B() {...}
    }
  )
)
```

- Giải thích:

  - `refFromParent` truyền qua forwardRef sẽ làm đối số thứ 1 của useImperativeHandle
  - `Đối số thứ 2` sẽ là 1 callback trả về 1 object (object này chính thứ mà
    `refFromParent.current` sẽ trỏ đến, object này sẽ chứa các hàm - các chức năng mà Child cho phép Parent sử dụng)

  - VD:

  ```jsx
  // Child.js;

  const videoRef = useRef();

  useImperativeHandle(refFromParent, () => ({
    play() {
      videoRef.current.play();
    },
    pause() {
      videoRef.current.pause();
    },
  }));

  return (
    <>
      <div>
        <video ref={videoRef} src={video} width={'600px'} />
      </div>
    </>
  );
  ```

  - Ta thấy như ở trên hàm `play()` và `pause()` trong object sẽ gọi tới 2 hàm `play()` và `pause()` của DOM Element video (tức là ta đã giới hạn được những hàm - chức năng mà `refFromParent.current` có thể sử dụng)

## 9. `useReducer(reducer, initState)`

### 9.1 Với những component đơn giản, nhỏ, props chỉ truyền xuống con gần nhất thì ta chỉ cần dùng `useState()`

```jsx
const [state, setState] = useState(initState);
```

### 9.2 Với những component phức tạp, nhiều state, props drilling thì ta có thể dùng `useReducer()`

1. `initState`

2. `Action`:

   - **Action type**: _"UP", "DOWN", "LEFT", "RIGHT"_
   - **Action payload**
   - **Action generater**: là hàm sẽ trả về 1 Action object gồm kiểu của `action` và `data`

   VD:

   ```jsx
   {
     type: 'UP' | 'DOWN' | 'LEFT' | 'RIGHT';
     payload: data;
   }
   ```

3. `dispatch`: _là hàm sẽ gửi `action` (nhận đầu vào là kết quả trả về của 1 Action generator)_

VD:

```jsx
dispatch(actionGenerator());
```

4. `reducer`: _là hàm xử lý action được dispatch gửi tới, đối số được truyền vào hàm dispatch sẽ là tham số action (tham số thứ 2) cho hàm reducer_

VD:

```jsx
dispatch(A); // thì action = A
```

- `reducer` nhận tham số thứ 1 (state) là kho chứa trạng thái chung (khi component mới tạo thì state sẽ bằng initState)

```jsx
  const reducer = (state, action) => {
    switch (action.type) {
      case A: ... return newState;
      case B: ... return newState;
      default: throw new Error('...')
    }
}
```

5. **Cách sử dụng**: _nhận đầu vào là hàm reducer (hàm xử lý action) được định nghĩa từ trước và initState_

VD:

```jsx
const [state, dispatcher] = useReducer(reducer, initState);
```

## 10. React Context và `useContext()`

- Bao gồm: `Context`, `Provider`, `Consumer`
- Sử dụng:

```jsx
const Context = React.createContext();

function ContextProvider({chilren}) {
  ...
  return (
    <Context.Provider value={...}>
      {chilren}
    <Context.Provider/>
  )
}
```

## 11. `useTransition()`

https://www.youtube.com/watch?v=U9Cth5xDEKs&list=PL0Zuz27SZ-6PSdiQpSxO9zxvB0ns6m3ta&index=9

https://react.dev/reference/react/useTransition

## 12. `useDefferedValue()`

https://www.youtube.com/watch?v=U9Cth5xDEKs&list=PL0Zuz27SZ-6PSdiQpSxO9zxvB0ns6m3ta&index=9

https://react.dev/reference/react/useDeferredValue

## 13. React `Suspense`

## 14. React `lazy()`

## 15. Tạo fake api server bằng json-server

- Tạo folder data (cùng cấp với src), trong data tạo `db.json` (tuỳ chỉnh dữ liệu trong `db.json`)

- Chạy:

```bash
npx json-server -p 8888 -w data/db.json

# Server sẽ start ở cổng 8888: localhost:8888/items

```

- Có thể gửi method `GET`, `POST`, `PUT`, `PATCH`, `DELETE` tới `http://localhost:8888/items/itemId`
