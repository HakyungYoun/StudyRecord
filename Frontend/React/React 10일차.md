## 리액트 10일차(Redux)  

Redux state 변경하기  

1. state 변경하는 함수만들기(ex)
state 선언한 곳에
   ```
   reducers : {
    changeName(state){
      return 'john kim';
    }
   }
해당 예시와 같이 변경하는 함수를 만든다  

2. 만든 함수를 export 해준다(ex)
```
export let {changeName} = user.actions
```

3. 사용할 곳에서 import 후 dispatch(state 변경 함수()) 형식으로 사용
```
let dispatch = useDispatch();
dispatch(changeName())
```
dispatch는 안에 있는 reducer 함수를 호출  

state가 object/array일 경우 변경하는 법  
```
reducers: {
    plusCount(state,index) {
      state[index.payload].count +=1;
    }
  }
```
이런식으로 직접 수정해도 state 변경된다(immer.js가 자동으로 다운되는데 그것의 도움)  
return 없이 직접 수정. 일부러 수정하기 쉽게 그냥 문자로 state값을 안 넣고 object/array 형태로 넣는 경우도 있다  
파라미터를 넣어서 활용하기 위해서는 괄호에 파라미터 값을 넣고 .payload를 쓴다

