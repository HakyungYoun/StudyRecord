## 리액트 12일차(React-Query)  

ajax 요청하다보면 이런 기능들이 가끔 필요해진다  

- 몇초마다 자동으로 데이터 다시 가져오게 하려면?

- 요청실패시 몇초 간격으로 재시도?

- 다음 페이지 미리가져오기?

- ajax 성공/실패시 각각 다른 html을 보여주려면?

이러한 상황일 때 React-Query를 사용해 볼 수 있다
SNS, 코인 거래소 같이 실시간 데이터를 보여줘야하는 사이트들은 유용하지만 그렇지 않은 경우 유용하지 않을 수 있다  

설치방법  
```npm install react-query```

설치 후 index.js파일에 관련 기능 import  
```import { QueryClient, QueryClientProvider, useQuery } from 'react-query'  ```  

그리고 ```const queryClient = new QueryClient();``` 선언  

그리고 <App> 컴포넌트를 <QueryClientProvider > 으로 감싸고 => ```<QueryClientProvider client={queryClient}>``` 이렇게 선언  

react-quert로 ajax 요청하기  
```
function App(){
  let result = useQuery(['작명'], ()=>
    axios.get('https://codingapple1.github.io/userdata.json')
    .then((a)=>{ return a.data })
  )
}
```
result라는 변수에 ajax 현재 상태가 알아서 저장된다

- ajax요청이 로딩중일 땐 result.isLoading 이 true가 된다  

- ajax요청이 실패시엔 result.error 가 true가 된다  

- ajax요청이 성공시엔 result.data 안에 데이터가 들어온다

페이지 체류하고나서 일정시간이 경과하거나, 다른 창으로 갔다가 다시 페이지로 돌아오거나, 다시 메인페이지로 돌아가거나 이런 여러 경우에 알아서 ajax 요청을 다시 해준다  
```
function App(){
  let result = useQuery(['작명'], ()=>
    axios.get('https://codingapple1.github.io/userdata.json')
    .then((a)=>{ return a.data })
  ),
  { staleTime : 2000 }
}
```
해당 내용처럼 stableTime으로 시간 설정을 하면 해당 시간동안은 refetch가 되지 않는다  

ajax 실패 시 재시도를 알아서 해준다(4~5회정도)  

ajax로 가져온 결과는 state 공유가 필요없다  
똑같이 요청하는 코드를 필요한 곳에 또 적으면 2개의 ajax 요청 중 1개만 날리고 캐싱기능으로 그걸 가져와서 쓴다
