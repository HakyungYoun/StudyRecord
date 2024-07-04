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
리액트는 코드를 하나로 합치기 때문에 다른 곳에 적용될 수 있다  
css파일로 구성하지 않기 때문에 페이지에 선언한 css만 골라서 로드를 할 수 있기에 페이지 로딩시간이 조금이나마 빨라질 수 있다  

다른 방법으로는 예시로 App.js에 종속되는 css파일은 App.module.css 작명하면 App.js에 종속된다  

styled-components는 모듈처럼 작동하기에 선언 시 대문자로 선언필요

```let YellowBtn = styled.button`background : ${ props => props.bg }; color : black; padding : 10px` ``` 해당 예시처럼 props 선언해서  
```<YellowBtn bg='blue'/>``` 모듈처럼 props 값을 넣어줄 수 있음  

```let YellowBtn = styled.button`background : ${ props => props.bg }; color : ${props => props.bg =='blue'? 'white' : 'black'}; padding : 10px` ```  
해당 방식처럼 사용도 가능  

```let NewBtn = styled.button(YellowBtn);``` 기존 선언한 내용 복사가능
