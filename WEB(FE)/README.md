## FRONTEND 실행법

```
$ cd WEB\(FE\)/

$ cd ts-wilim

$ npm install

$ npm start
```
or...

[배포된 페이지](https://front.wilimbackend.tk) 로 가기
(비용 이슈로 현재 배포는 닫혀있습니다. 시연 영상 참고 부탁드립니다.)

## 💡 WILIM (What I Learned In Military)
![](https://ndevthumb-phinf.pstatic.net/20221014_254/1665758181351XQFWU_PNG/5Jr6kLwmqvGI20221014233621.png)

군복무를 하면서 자격증 준비, 수능 준비 등 자기개발을 위해 힘쓰는 장병들이 많습니다. 그러나, 군대라는 제한된 환경에서 공부를 하기에는 여러 애로사항이 존재합니다. 장병들이 일과 후 시간을 다른 곳에 뺏기지 않고 온전히 공부에만 활용하도록 돕기 위해, 저희는 WILIM 서비스를 개발해 보았습니다. 

 - **시험 일정**부터 **문제집**, **기출문제** 등의 자격증 정보를 찾아줍니다.
 -  촘촘한  자신만의 **플랜**을 세워 보다 건설적으로 공부할 수 있게 도와줍니다.
 - **커뮤니티**를 통해 서로의 공부를 돕고, 동기부여 할 수 있는 공간을 만들어줍니다.
 - 장병들은 WILIM을 통해 전보다 나은 환경에서 공부에 전념할 수 있게 됩니다.

## 🤖 WILIM 프론트엔드만의 특징


 - [typescript](https://www.typescriptlang.org/): "^4.8.4" - Typescript를 이용한 정적 타입 기반의 견고한 아키텍쳐 구성
 - [react](https://ko.reactjs.org/): "^18.2.0" - React 라이브러리를 이용한 반응형 SPA 개발,✅
 - [axios](https://axios-http.com/kr/): "^0.27.2" - 비동기 API호출을 위한 모듈입니다.✅
 - [redux-toolkit](https://redux-toolkit.js.org/): "^1.8.5" - Redux를 이용한 전역 상태관리를 쉽게 하도록 도와주는 툴. 비동기 함수들도 관리하기 용이하도록 함.✅
 - [styled-components](https://styled-components.com/): "^5.3.5" - CSS In JS 문법을 이용하여 컴포넌트 별 스타일 관리를 용이하게 하는 라이브러리.✅


...이외에도 다양한 툴 및 모듈을 사용했습니다

## WILIM Front-End Code Architecture

Atomic design을 참고하여 설계하되, 대규모 서비스를 개발하는 것이 아니므로 구조는
1. Button, Text, label, Input 과 같은 **Atom**
2. SRP(Single Responsibility Principle, 단일 책임 원칙)을 준수하여 동일한 역할을 맡는 Atom들을 합쳐 만든 **Molecule**
3. Molecule을 합쳐서 만든 하나의 서비스적인 역할을 맡는 영역인(GNB,  Nav, Card 등) **Organism**
4. Organism을 합쳐서 만든 실제 보여질 전체 Page의 뼈대가 되는 **Template**
5. Template에 데이터를 합쳐서 제작하는 **Page** -> Template에 데이터를 심어줌으로써 제작함.

Design Pattern 은 Redux(Redux-toolkit)을 이용한 Flux 패턴을 적용한다.

#### Action / Action creator

Action은 Redux 에서 관리되는 전역 상태를 변경할 수 있는 명령 단위입니다. 모든 전역 상태는 Action을 통해서만 변경 가능합니다.

#### Dispatcher

Dispatcher는 Action의 동작에 의한 전역 상태 변경이 감지되면 해당 변경 사항을 각 Store에 전달하는 역할을 한다.

#### Store(Model)

Store는 전역 상태와, 상태를 변경 가능한 메서드를 담은 하나의 단위이다. 들어오는 Action에 따라 상태를 변경하는 Trigger를 발동시킨다.

#### View

UI와 직접적으로 연결되는 부분. 위의 Atomic Pattern에서 Template과 View를 연결시켜 데이터를 전달하고 Page를 생성함.

### Reference

[아토믹 디자인을 활용한 디자인 시스템 도입기 - kakao 기술블로그](https://fe-developers.kakaoent.com/2022/220505-how-page-part-use-atomic-design-system/) 
[Flux | 사용자 인터페이스를 만들기 위한 어플리케이션 아키텍쳐](https://haruair.github.io/flux/docs/overview.html)

## 📜TEAM INFO

 
 - 오형근 [kandy1002@naver.com](mailto:kandy1002@naver.com)], Github Id: Geun-Oh
 - 이정인 ([leeji7682@gmail.com](mailto:leeji7682@gmail.com)), Github Id: leeji7682
