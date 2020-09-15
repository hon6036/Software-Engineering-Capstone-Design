# Software-Engineering-Capstone-Design

### OpenCV를 이용한 졸음운전 방지 시스템
|Participant|Roles|Skills|Training needs|
|------|---|---|---|
|이정민|Team leader|Java, Python, OpenCV|UML|
|김선우|Implementor|Python, OpenCV, Web crawling|UML|
|강원준|Implementor|Java, C|UML|
|홍승환|Tester|Python, Javascript|UML|


##요구사항 기술
졸음운전 사고를 막기위해 졸음을 인식하고 경고음으로 주의를 주는 시스템

##풀고자하는 문제
1. 졸음인식을 어떤 방식으로 할 것인지 2. 졸음 확인 시 어떤 이벤트를 줄 것인지 3. 졸음의 기준을 어떻게 잡을 것인지

##제공 해야하는 기능
운전자의 얼굴과 눈을 정확히 인식해야한다.
연속되는 사진 프레임을 읽어들이는데 딜레이는 0.3초 이하로 프로세싱 돼야한다.

##사용하는 주체
화물트럭 운전사, 택시운전사와 같은 장시간 운전자

##활용해야 되는 IO 디바이스
카메라(실시간 촬영), 임베드디장비(경고음)
