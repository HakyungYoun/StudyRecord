# 💻FrontEnd 공부
## 리액트 1일차(map을 통한 반복문, props)

map을 사용하면 array 안에 있는 개수만큼 반복시켜줌

ex) [1,2,3].map(function()콜백함수자리 {
  해당 map은 3번 반복됨
})

ex) [1,2,3].map(function(){}) function 괄호의 첫번째 값은 array 안에 있는 값, 그 다음 , 뒤에 선언한 것은 index 값
function(num, index) num = 1,2,3 나올 것이고 index는 0,1,2 나올 것이다

반복문으로 생성한 html 같은 경우 속성값으로 key 값이 들어가야한다
ex) ```<div className='test' key={index}></div>```

부모 component에 있는 state를 자식 component에서 쓰고 싶으면 props 문법을 사용해야한다

ex) ```<Modal titles={titles}>``` 자식 component 호출하는 곳에서 작명한 props 값과 전송할 state 값을 기입한다
    이후 props 를 해당 component의 파라미터로 등록후에 {props.작명한props} 형태로 state를 가져다 쓸 수 있다
```<Modal titles={titles} titleIndex={titleIndex}/>``` 이런식으로 state를 여러개 넘겨줄 수도 있다
