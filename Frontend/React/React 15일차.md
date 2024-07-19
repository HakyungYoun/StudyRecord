## 리액트 15일차(useTransition, useDeferredValue)  

리액트 18버전 이후 Auto batching기능이 생겼음  
여러 state 변경이 일어날 때마다 재렌더링이 발생하는 것이 아니라 마지막 state 변경 시 재렌더링이 1번만 일어난다  
이를 위해 성능 최적화가 된다  

---

useTransition 기능으로 느린 컴포넌트 성능 향상이 가능하다  

사용 예시  
```
let a = new Array(10000).fill(0)
let [isPending, startTransition] = useTransition();  -> [변수,함수]

<input onChange={ (e)=>{ 
        startTransition(()=>{
          setName(e.target.value) 
        })
      }}/>

      {
        a.map(()=>{
          return <div>{name}</div>
        })
      }
```
예시 처럼 state 변경 함수를 감싸면 해당 코드를 다르 코드들보다 나중에 처리한다

변수로 선언한 것은 오르쪽 함수가 처리중일 때 true로 변하는 변수다

근본적인 성능 개선이라기보다 특정 코드의 실행시점을 뒤로 옮겨주는 것일 뿐이다  

---  


