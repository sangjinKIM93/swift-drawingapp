# swift-drawingapp

클린 스위프트 과제2

# 구조도

![image](https://user-images.githubusercontent.com/62230118/223130886-bbbfa757-1901-4c89-8a00-5ab131363888.png)

<br><br>

## 객체 설명

### [View]

### CanvasView

- 터치 인식

### DrawingLayerMaker

- Square, Line 객체에 있는 도형 정보를 가지고 CAShapeLayer 객체를 만듬
- **DrawingMaker**와 **PathMaker**를 가지고 있음

<br><br>
### [ViewController]

### DrawingViewController

- 사용자의 입력을 DrawingViewModel에 전달
- DrawingViewModel에서 받은 명령을 CanvasView에 전달. (DrawingLayerMaker로 한번 처리 후 전달)

<br><br>
### [ViewModel]

### DrawingViewModel

- 비즈니스 로직 처리
- 입력에 따라 Square, Line 인스턴스를 DrawingStore에 저장하고, 이를 바탕으로 View에 표현하도록 함
- 소켓 연결 관련 로그인 처리, 데이터 전송 및 응답 결과 View 표현

<br><br>
### [Model]

### DrawingFactory

- Square, Line 인스턴스를 생성
- **LineFactory**와 **SquareFactory**를 가지고 있음

### Shape

- uuid와 points(도형 좌표)를 가지는 protocol

### Square, Line

- Shape을 채택하는 도형 객체

<br><br>
### [Store]

### DrawingStore

- Shape(Square, Line) 데이터를 저장

<br><br>
### [Network]

### ChatServerClient

- Drawing 공유 채팅 기능을 위한 데이터 전송 및 응답 처리
- ChatCommandConverter라는 유틸 객체 보유 (model <-> json 변환기)

### SocketManager

- 소켓 기본 기능

<br><br>
