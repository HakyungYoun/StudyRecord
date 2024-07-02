## 리액트 3일차(쇼핑몰 프로젝트 시작)  

Bootstrap을 쓰기 위해 React-Bootstrap 검색 후  
'npm install react-bootstrap bootstrap'  
해당 명령어 터미널에 입력해서 설치(명령어는 달라질 수 있으므로 공식 사이트에서 확인 필요)  

public 폴더에 있는 url을 쓸때에 process.env.PUBLIC_URL 이런식으로 써야 주소가 바뀌었을때 따로 수정을 하지 않아도 된다  
ex) ```<img className='profile' src={process.env.PUBLIC_URL+props.data[props.index].url} alt='이미지' width="40%"></img>```

import, export를 통해 데이터, 변수값, 함수등 여러 기능들을 분리 및 가져올 수 있다  

ex) test.js 파일의 컴포넌트  
```
function MainItems(props){
  return(
  <div className='col-md-4'>
            <img className='profile' src={process.env.PUBLIC_URL+props.data[props.index].url} alt='이미지' width="40%"></img>
            <h4>{props.data[props.index].title}</h4>
            <p>{props.data[props.index].content}</p>
          </div>
  )
}

export default MainItems
```
import 시 import 할 곳에서 선언할 이름과 위치로 import 가능  
ex) import MainItems from './test.js';
