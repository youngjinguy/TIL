# CORS
CORS(Cross Origin Resource Sharing)는 브라우저에서만 적용되는 정책이기 때문에 서버로 요청은 온다. 따라서 서버는 요청을 수신하고 처리할 수 있지만, 브라우저에서 해당 요청에 대한 응답을 받을 때 CORS 정책이 적용된다.

Access-Control-Allow-Origin 설정 값이 중복되면 브라우저에서 CORS 오류를 발생시킨다.

크롬 기준 메시지는 아래와 같다.
``` html
has been blocked by CORS policy: The 'Access-Control-Allow-Origin' header contains multiple values
```
