## 리액트 14일차(memo,useMemo)  

memo : props가 변할 때만 재렌더링 해주는 기능  

사용법 예시  
```
let Child = memo(function(){
    return<div>메모 테스트용</div>;
})
```
컴포넌트를 해당 형식처럼 memo로 감싸준다  

