## 리액트 5일차(url 파라미터를 통한 페이지, styled-components)  

userParam() 훅을 이용해 파라미터 값을 가져올 수 있음  
ex) 파라미터 설정 ```<Route path='/detail/:id' element={<Detail data={data}/>}/>```  
해당 예시처럼 ' :파라미터 ' 형식으로 파라미터 설정 가능  

```let {id}=useParams();``` 이 예시처럼 id 값으로 선언한 곳의 파라미터 값을 가져올 수 있다  

id에 해당하는 데이터를 가져오기 위해 javascript find를 써서 해당하는 item의 id를 가져왔다
find, filter 를 쓸 수 있지만 나는 Unique한 값인 id를 가져오기 때문에 효율이 더 좋은 find를 사용하였음  

```let itemNum=props.data.find(item=>item.id=id).id;```  

find -> 찾으면 그만두고 반환  
filter -> 전체에 대해서 확인 후 반환
##  

styled-components 사용을 위해 설치를 해준다  
npm install styled-components  

styled-components의 장점 : 스타일이 다른 js 파일로 오염(전이)되지 않는다  
코드를 하나로 합치기 때문에 다른 곳에 적용될 수 있다  

다른 방법으로는 예시로 App.js에 종속되는 css파일은 App.module.css 작명하면 App.js에 종속된다
