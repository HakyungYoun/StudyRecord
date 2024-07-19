## 리액트 13일차(lazy import)  

사용하기는 하지만 당장 필요한 컴포넌트들이 아닌 경우  
필요해질 때 import 해주는 lazy를 사용할 수 있다  
(예시)  
```import Detail from '/Detail.js' -> const Detail = lazy(() => import('/Detail.js'));```  

이렇게 하면 사이트 발행 시 별도의 js 파일로 분리된다  

단점으로는 컴포넌트 로딩시간이 발생할 수 있다  
그래서 로딩 중 표시등으로 눈길을 돌려야 한다  
이럴 때 Suspense를 사용해서 해당 컴포넌트를 감싸고 설정할 수 있음  

보통 대부분 lazy 처리하기 때문에 Routes 전체를 Suspense로 감싸서 활용할 수 있다  
(예시)  
```
<Suspense fallback={<div>로딩중</div>}>
  <Routes>

  </Routes>
</Suspense>
```
이런 형식으로 메인페이지 로딩시간 개선 가능

