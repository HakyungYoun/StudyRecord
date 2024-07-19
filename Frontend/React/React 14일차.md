## 리액트 14일차(memo,useMemo)  

memo : props가 변할 때만 재렌더링 해주는 기능  

사용법 예시  
```
let Child = memo(function(){
    return<div>메모 테스트용</div>;
})
```
컴포넌트를 해당 형식처럼 memo로 감싸준다  

하지만 무조건 memo를 쓰는 것은 좋은 방법이 아니다  
Why? -> 기존 props, 신규 props가 변했는지 비교하는 로직때문에  
재렌더링 되는것이 부담스러운 무거운 컴포넌트들에 대해서 쓰는 것이 좋은 방법이 될 수 있다  

useMemo : 컴포넌트 렌더링 시 1회만 실행해준다 -> useEffect와 쓰임이 비슷하다  

사용법 예시  
```
function test(){
    return '반복문 10억번 돌린 결과';
}
let result = useMemo(()=>{return test()})
let result = useMemo(()=>{return test()},[state])
```
useEffect처럼 state 집어넣어서 변경될 때마다 실행시킬 수 있음 

useEffect와 useMemo의 차이점??  
useEffect는 html 렌더링 후 실행, useMemo는 렌더링 될 때 실행
