## 리액트 6일차(useEffect)

useEffect 사용 시 컴포넌트의 mount update 마다 안에 선언한 내용이 실행된다  

<h4>but 그냥 선언하는것과 어떤 차이?</h4>  
useEffect로 선언한 내용은 html 랜더링 이후 실행된다  
고로 useEffect에는 어려운 연산, 서버에서 데이터를 가져오는 등의 기능을 넣으면 좋다  

```
useEffect(()=>{
    let removeTag = document.getElementById('needRemove');
    setTimeout(()=>{setAlert(false)},2000);
  },[])
```
뒤에 [] 는 실행조건을 넣어줄 수 있어서 안에 있는 값이 변할 때마다 작동하게 만들 수 있다  
그냥 빈칸으로 [] 할 때에는 mount 시에만 실행되고 update 할 때에는 실행되지 않음  
```
useEffect(()=>{
    let removeTag = document.getElementById('needRemove');
    setTimeout(()=>{setAlert(false)},2000);
    return ()=>{
      
    }
  },[])
```
return 안에 작성된 코드는 useEffect 동작 전에 실행된다  
예를 들어 update 때마다 어떤 것을 생성한다면 그것이 누적되고 그것을 update 마다 기존에 생성된 것을 삭제하는 등의 기능을 추가할 수 있다( unmount 시 코드 실행 )  



