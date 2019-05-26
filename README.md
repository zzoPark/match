# match
같은 그림 맞추기 게임

## 개발방식
1. 우선 모놀리식으로 개발
    - RestAPI Node.js로 구현
    - Vue.js 프론트엔드 구현
    - MongoDB 이용
1. 마이크로서비스로 나누기
1. AWS Lambda로 이관

### 고려사항
* AWS Lambda + Node.js를 이용한 backend API 구성
    * 원래는 EC2와 Docker를 이용하려고 생각했지만 EC2 이용시 아무런 요청을 하지 않아도 꾸준히 높은 비용이 발생한다는 단점이 있어서 아무래도 소규모 개인 프로젝트이다보니 핵심기능 위주로 함수 호출시에만 비용이 발생하는 Lambda를 선택하게 되었다.
* Vue.js + Bootstrap으로 reactive frontend 구성
    * 이것도 Lambda로 구성할 수 있는지는 더 공부가 필요하다. Static resource의 경우 S3를 이용하는 것 같기도.. 월요일날 책이 오면 읽어봐야지
    * Vue.js 자체는 Node.js를 파고들면 더 익숙해질 수 있을 것 같다. 둘 다 Javascript 기반이라..vuex랑 Vue가 제공하는 편리한 기능들만 숙지하면 될듯.
* 아마 DynamoDB(NoSQL)를 이용?
* 서버리스 아키텍쳐는 처음 접하는 거다 보니 설계부터가 어디서 시작해야할지 막막하다. 방법론과 어떻게들 구현했는지가 궁금한데 도서관에 자료가 없어서 아쉽다. 모놀리식 앱을 설계 후 기능 단위로 쪼개면 되는 걸까?

## Flowchart
![Flowchart](/docs/flowchart.jpg)
