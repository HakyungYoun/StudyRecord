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
