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
담당자: 홍승환

![UseCase](https://user-images.githubusercontent.com/50129757/100823932-7d7dc580-3498-11eb-9248-ae3201920f33.png)

1. Drowsiness prevention system  
Camera는 사용자의 얼굴을 DetectDrowsiness use case에 전송해 졸음 운전인지 아닌지 확인한다.(DetectDrowsiness use case)  
Buzzer는 Driver가 졸음운전이라 인식되면 Driver에 경고음을 발생시킨다. (WarnUser use case)  

2. Drowsiness prevention edge system  
Edge는 Drowsiness prevention system을 통해 받은 위치정보와 Cloud에서 받은 위치정보를 분석한다. (DataAnalysis use case)  
Edge는 Drowsiness prevention system에서 받은 정보를 저장한다.(ReceiveData)  
Edge에서 받은 정보를 Cloud에 전송하게 되며 사용자들이 많이 졸았던 위치를 분석해서 Edge에 전송한다. (CollectData use case)   

## Scenario Description
담당자: 홍승환  
![Scenario](https://user-images.githubusercontent.com/50129757/95862484-f4061d00-0d9d-11eb-99c1-b06000d03e25.png)

## Sequence Diagram
담당자: 김선우
![Sequence Diagram1](https://user-images.githubusercontent.com/50129757/95867927-a6d97980-0da4-11eb-9a86-9b9d87291999.png)
![Sequence Diagram2](https://user-images.githubusercontent.com/50129757/95863063-b0f87980-0d9e-11eb-84aa-5ceb2a1f6e35.png)

## Class Diagram
담당자: 이정민
![Class Diagram](https://user-images.githubusercontent.com/50129757/100181932-b826b180-2f1e-11eb-9e24-5fa25027c5a3.png)


## Object Diagram
담당자: 강원준
![](https://user-images.githubusercontent.com/50129757/95863260-f2892480-0d9e-11eb-9940-3a80c27a268a.png)


## Design Goal Description
담당자: 이정민 
|Design criterion|Definition|
|------|---|
|Security|사용자의 위치정보가 타인에게 노출되면 안된다. 응답 시간: 즉각적인 이미지 프로세싱으로 졸음을 판별해내야한다.(0.3초 이내)|
|Reliability|사용자의 졸음운전을 파악하는 것에 대한 신뢰가 보장되어야 한다.|
|Fault Tolerance|cloud와의 연결이 끊어져도 졸음 운전을 판독해낼 수 있어야한다.|

## Component Diagram
담당자: 이정민, 홍승환
![Component Diagram](https://user-images.githubusercontent.com/50129757/100562932-6efca600-3300-11eb-8020-4377dc6a90b4.png)
## Deployment Diagram
담당자: 김선우, 강원준 
![Deployment Diagram](https://user-images.githubusercontent.com/50129757/102851137-60686100-445e-11eb-9cbf-50ccab664dbf.png)

