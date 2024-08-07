## 리액트 9일차(Redux)  

Redux 사용 시 js파일에 state들을 보관 가능하고 컴포넌트들이 state를 빼서 사용가능하다  

react, react-dom 두가지 항목의 버전이 18.1.0 이상 되어야 사용할 수 있다  

Redux 설치 명령어
```npm install @reduxjs/toolkit react-redux ```  

js 파일 생성 후 입력
```
import { configureStore } from '@reduxjs/toolkit'

export default configureStore({
  reducer: { }
})
```

index.js 파일에 <Provider> import 해서 설정하기  

Redux store에 state 보관하는 법(예시)  
```
let user = createSlice({
  name : 'user',
  initialState : 'kim'
})
```
1. state 이름과 초기 state 값 선언

```
   reducer: { 
    user : user.reducer,
    stock : stock.reducer
  }
```
2. state 선언명과 위에서 만든 state변수.reducer로 보관

```
let state = useSelector((state)=>{
        return state;
    });
```
Reduc store에 보관한 state를 사용하고 싶은 곳에서 해당 예시처럼 사용 가능  
위의 예시는 보관된 state 전부를 가져오는 예시  

원하는 state만 가져오려면  
```
let state = useSelector((state)=>{
        return state.user;
    });
```
state 리턴값을 지정  

또한 return과 중괄호는 같이 생략가능  
```
let state = useSelector((state)=> state);
```
