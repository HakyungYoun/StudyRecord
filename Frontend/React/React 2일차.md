## 리액트 2일차(스크립트 기능, 옛날 컴포넌트 생성 방식)

input 태그에 여러 이벤트 핸들러를 넣을 수 있다  
ex) onMouseOver={} , onScroll={}  

하위태그의 이벤트가 상위태그까지 퍼지느 **이벤트 버블링** 을 막고 싶다면 e.stopPropagaion() 사용하면 된다  

onClick={addTitle()} 처음에는 이런식으로 코드를 만들었으나 자바스크립트는 함수() 로 작성 시 렌더링 시 실행되면서 에러발생 위험이 있음
실제로 무한반복되는 에러가 나왔음  

해당 문제 onClick={()=>{addTitle()}} 해당 코드처럼 콜백함수로 사용하던가 onClick={addTitle} 이런식으로 괄호 없이 사용할 수 있으면 작성할 수 있다
***  
옛날 컴포넌트 생성 방식  
```
class Modal2 extends React.Component{
  constructor(props){
    super(props);
    this.state={
      name:'kim',
      age:20
    }
  }
  render(){
    return(
      <div>{this.state.name}
        <button onClick={()=>this.setState({age:21})}>버튼</button>
      </div>
    )
  }
}
```
이런식으로 생성 가능 생성을 위해 constructor(){ super(); } render(){} 3가지 정의 필요  

state set 방식 차이 있음  

props 는 constructor() super() 안에 props 선언가능 this.props 써야 사용가능

