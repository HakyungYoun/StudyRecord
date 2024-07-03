## 리액트 4일차(about 리액트 라우터)  

리액트는 html파일 단일로 화면 구성이된다  
화면 변경 시 컴포넌트를 보여주는 방식  

리액트 라우터 사용을 위해 설치 필요  
npm install react-router-dom@6 - dom 6버전 설치  

index.js 파일에 ```<BrowserRouter></BrowserRouter> 해당 태그 사이에 <App/> ```태그를 넣는다  

```
<Routes>
        <Route path='/' element={<Main/>}/>
        <Route path='/detail' element={<Detail/>}/>
      </Routes>
```
Routes, Route 이용해서 path 설정과 띄울 컴포넌트 설정 가능  

useNavigate import 후  ```let navigate = useNavigate();``` 해당 예시처럼 선언 후 사용 가능  
ex) ```<Nav.Link onClick={()=>{navigate('/detail')}}>Detail</Nav.Link>```  

nested router 기능을 이용해서  
```
<Route path='/about' element={<About/>}>
          <Route path='member' element={<div>멤버</div>}/>
          <Route path='location' element={<div>로케이션</div>}/>
</Route>
```
이런식으로 Route 안에 Route들을 넣을 수 있음  
장점 : ex) /about/member로 갔을 때 about 과 멤버 정보를 둘 다 띄울 수 있음  
단 Outlet을 이용해서 어떤곳에 memeber 요소를 넣어줄 지 정해야 한다  
```
function About(){
  return(
    <div>
      <h4>회사정보</h4>
      <Outlet></Outlet>
    </div>
  )
}
```
nested route는 유사한 여러 페이지를 구성할 때 쓰이면 좋다
