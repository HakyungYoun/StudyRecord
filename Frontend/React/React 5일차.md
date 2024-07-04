## 리액트 5일차(url 파라미터를 통한 페이지)  

userParam() 훅을 이용해 파라미터 값을 가져올 수 있음  
ex) 파라미터 설정 ```<Route path='/detail/:id' element={<Detail data={data}/>}/>```  
해당 예시처럼 ' :파라미터 ' 형식으로 파라미터 설정 가능  

```let {id}=useParams();``` 이 예시처럼 id 값으로 선언한 곳의 파라미터 값을 가져올 수 있다  


