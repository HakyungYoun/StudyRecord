## 리액트 7일차(ajax)  

ajax 사용하여 요청 시 비동기 식으로 작동하여 새로고침이 되지 않음  

그중에서 axios를 사용하기 위해
```npm install axios```  
명령어로 axios 설치 후 진행  

```
axios.get('https://codingapple1.github.io/shop/data2.json')
        .then((data)=>{ 
          addMainItems(data.data);
        }).catch(()=>{
          console.log('fail');
        })
```
요청 결과는 axios.get(url).then() 으로 확인한다  
만약 요청 실패 시 .catch() 로 예외처리 가능
