## 리액트 8일차(Context API,Redux)  

컴포넌트가 중복되다보면 props가 복잡해지고, 부모부터 자식까지 props 전부 선언해줘야한다  
이러한 문제를 해결하기 위해 Context API, Redux를 활용할 수 있다  

실전에서는 ContextAPI보다 Redux를 많이 사용한다(성능 이슈, 컴포넌트 재활용이 어렵다는 이슈로 인해)  

ContextAPI 사용법  
ex) ```let Context1 = createContext();```  
해당 예시처럼 createContext() 선언  

ex)``` <Route path='/' element={<Context1.Provider><Main Product={Product} /></Context1.Provider>} />```  
```<Context>```로 state 공유를 원하는 컴포넌트 감싸기  

```<Context1.Provider value={{stock,Product}}><Main NewJeans={Product} /></Context1.Provider>```  
value에 state 넣는다. 이렇게 되면 감싼 컴포넌트의 자식들까지도 사용가능




