## 리액트 11일차(localStorage)  

localStorage에 key value 형태로 값을 저장 가능  

해당 value값에 넣을때는 String 값이 필요함으로 Json 형태로 변환해서 넣을 필요가 있다  
또한 값을 다시 가져와서 활용할 때에도 Json.parse 가 필요  

localStorage는 쉽게 설정할 수 있다
```localStorage.setItem('키', 값);```  
이러한 형태로 set가능  

가져올 때는  
```localStorage.getItem('키');```
이러한 형태로 get가능  

다시 설정할 때에는 따로 수정 기능이 없기 때문에 get해서 안에 값을 바꿔서 다시 set하는 형식으로 수정해야한다  

추가로 저장할때 array 안에 object형태로 넣었는데 getItem을 했을 경우 Json.parse가 array에만 먹혀서  
```let parsedLog = recentSearchLog.map(item => JSON.parse(item));```  
해당 방식대로 가져온 array안에 object들을 한 번 더 parse해줘서 문제 해결을 하였다
