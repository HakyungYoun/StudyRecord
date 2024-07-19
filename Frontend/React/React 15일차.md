## 리액트 15일차(useTransition, useDeferredValue)  

리액트 18버전 이후 Auto batching기능이 생겼음  
여러 state 변경이 일어날 때마다 재렌더링이 발생하는 것이 아니라 마지막 state 변경 시 재렌더링이 1번만 일어난다  
이를 위해 성능 최적화가 된다  

---

useTransition 기능으로 느린 컴포넌트 성능 향상이 가능하다  

사용예시
