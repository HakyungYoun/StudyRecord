## 리액트 6일차(useEffect)

useEffect 사용 시 컴포넌트의 mount update 마다 안에 선언한 내용이 실행된다  

<h4>but 그냥 선언하는것과 어떤 차이?</h4>  
useEffect로 선언한 내용은 html 랜더링 이후 실행된다  
고로 useEffect에는 어려운 연산, 서버에서 데이터를 가져오는 등의 기능을 넣으면 좋다
