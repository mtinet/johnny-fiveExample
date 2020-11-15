# johnny-fiveExample  

## 1. 작업폴더를 만듬

## 2. cmd 창으로 들어가 해당 폴더로 이동  

## 3. johnny-five 모듈을 설치(node.org에서 node를 먼저 다운로드 받아 설치해 놓은 상태여야 함)    
```
npm install johnny-five
```

## 4. 아두이노에 firmata 업로드  
- 파일 - 예제 - Firmata - StandardFirmataPlus  

## 5. 아래 예제 파일을 index.js 라는 이름으로 만듬  
```
var five = require("johnny-five"),
    board = new five.Board();

board.on("ready", function() {
  // Create an Led on pin 13
  var led = new five.Led(13);

  // Strobe the pin on/off, defaults to 100ms phases
  led.strobe();
});
```
- 단, 시리얼 통신 포트가 자동으로 잡히지 않는 경우가 많은데 이럴 때는 장치관리자에서 통신 포트를 직접 확인한 다음 위 예제의 포트 잡는 부분을 아래와 같이(아두이노가 연결된 포트로 지정) 인위로 지정해 줌  
```
    board = new five.Board({ port: "COM10" });
```

## 6. node로 작성한 파일을 실행  
```
node index.js
```

## 7. 아두이노의 13번 핀에 연결된 LED가 깜빡거리는 것을 확인할 수 있음  
