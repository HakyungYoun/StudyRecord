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

post 요청은  
```
axios.post(url,{data})
        .then((data)=>{ 
          addMainItems(data.data);
        }).catch(()=>{
          console.log('fail');
        })
```
이런식으로 요청 url + (보낼 데이터) 넣어서 보낸다  


동시에 ajax 요청을 여러개 하려면  
```
Promis.all([ axios.get(url1), axios.get(url2)])
        .then(()=>{
        const response1 = responses[0];
        const response2 = responses[1];
        })
```
이런식으로 쓸 수 있다  

axios는 json 데이터를 자동으로 array로 바꿔준다  

fetch를 사용하면 json으로 온 data를 array/object로 바꿔주는 작업을 해야함
