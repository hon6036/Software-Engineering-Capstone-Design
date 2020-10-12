# Software-Engineering-Capstone-Design

### OpenCV를 이용한 졸음운전 방지 시스템
|Participant|Roles|Skills|Training needs|
|------|---|---|---|
|이정민|Team leader|Java, Python, OpenCV|UML|
|김선우|Implementor|Python, OpenCV, Web crawling|UML|
|강원준|Implementor|Java, C|UML|
|홍승환|Tester|Python, Javascript|UML|


## 요구사항 기술
졸음운전 사고를 막기위해 운전자의 졸음을 인식하고 경고음으로 주의를 주는 시스템

## 풀고자하는 문제
1. 졸음인식을 어떤 방식으로 할 것인지 
2. 졸음 확인 시 어떤 이벤트를 줄 것인지 
3. 졸음의 기준을 어떻게 잡을 것인지

## 제공 해야하는 기능
1. 운전자의 얼굴과 눈을 정확히 인식해야한다.
2. 연속되는 사진 프레임을 읽어들이는데 딜레이는 0.3초 이하로 프로세싱 돼야한다.

## 사용하는 주체
1. 화물트럭 운전사
2. 택시운전사와 같은 장시간 운전자

## 활용해야 되는 IO 디바이스
1. 카메라(실시간 촬영)
2. 임베드디장비(경고음)

## Use Case
![Use Case](https://user-images.githubusercontent.com/50129757/95698319-84e4d780-0c7c-11eb-88c7-d390e6d5d883.png)

1. 졸음운전 감지 하는 Use Case  
Driver는 Camera를 통해 화면에 얼굴이 찍한다. (ShootFace use case)  
Camera는 찍힌 얼굴을 캡쳐한다. (CaptureFace use case)  
캡쳐된 사진은 Blink model로 이동하여 눈 깜밖임을 데이터화하고 DectAlogrithm으로 보내진다.  
Dectect Module은 DectAlgorithm을 통해 얼굴을 분석해 졸음 운전인지 아닌지 확인한다. (DectModel use case)  
Buzzer는 Driver가 졸음운전이라 인식되면 Driver에 경고음을 발생시킨다. (WarnSleep use case)  

2. 졸음운전 감지 후 해당 위치에 대한 데이터 수집 Use Case  
System은 사용자가 졸았던 위치를 edge에 전송한다. (SendData use case)  
Edge는 받은 위치 정보를 분석한다. (DataAnalysis use case)  
Edge에서 받은 정보를 Cloud에 전송하게 되며 사용자들이 많이 졸았던 위치를 분석해서 Edge에 전송한다. (DataCollection use case)  
Buzzer는 사용자가 다수가 졸았던 곳에 위치하게 되면 사용자에게 경고한다. (WarnLocation use case)  

## Scenario Description
![졸음운전시나리오](https://user-images.githubusercontent.com/67508204/93899288-212b5680-fd2f-11ea-83d9-823b68160f08.jpg)


