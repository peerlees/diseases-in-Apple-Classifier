# diseases-in-Apple-Classifier
Theme : Classifier based on apple quality using Arduino and Jetson nano

-Purpose

Apple quality screening machines are already available for video processing through computer vision, but expensive equipment, 
including computers and CCD cameras, are not commercialized, and private farm owners are said to be jointly owned by the village.
Therefore, I planned it with the thought that it would be good to be able to select it with a smartphone.
When the apple is detected on the container belt with the top, bottom, and sides as the default image dataset, 
it stops and identifies by camera from the top and bottom verticals and categorizes them according to quality.

: 컴퓨터 비전을 통한 영상처리로 사과품질 선별기가 이미 있지만 컴퓨터와 CCD camera를 비롯한 고가의 장비가 필요하여 상용화가 되어 있지않고 
 개인농장주들은 사용하지 못한채 마을 공동 소유로 한곳에서 사용되고 있다고 한다. 따라서 스마트폰으로도 선별을 할 수 있게하면 좋겠다는 생각으로 기획함.
 사과는 위, 아래, 옆면을 기본 이미지 데이터셋으로 두고 컨베이어 벨트에서 사과를 탐지하면 멈춰 위, 아래 수직에서 카메라로 식별하여 품질에 따라 분류함.


-Operation

train  : AlexeyAB darknet YOLOv3, YOLOv4, YOLOv5s

detection : Arduino infrared proximity detection sensor & jetson nano with logitech streamcam

operation : One apple from the conveyor belt, Arduino infrared proximity detection sensor detect apple and stop.
            Up and down verticals, cameras detect apples in 30fps, yielding average values. ( Inference Time: 0.09s )
            And determine the quality and classification.

<img width="729" alt="스크린샷 2021-04-25 오후 5 31 40" src="https://user-images.githubusercontent.com/82746560/115986669-4b5a3500-a5ec-11eb-93d2-15c360dc32e3.png">

Algorithm

<img width="695" alt="스크린샷 2021-04-25 오후 5 31 18" src="https://user-images.githubusercontent.com/82746560/115986719-93795780-a5ec-11eb-8abb-b0f5479fcacb.png">


-datasets

taken by myself

3500 images. Train : Val : Test = 7 : 2 : 1


-requirements

-labeling

3 classes : bruised, unhealthy, healthy

초기에 xml파일로 데이터 가공을 진행하였으나 darknet에서 txt파일의 labeling이 필요한 것을 확인하여 xml to txt로 바꿈.

<img width="500" height="500" src="https://user-images.githubusercontent.com/82746560/116021867-07b30a00-a684-11eb-9651-11632b768855.PNG>
<img width="500" height="500" src="https://user-images.githubusercontent.com/82746560/116021878-0d105480-a684-11eb-8beb-f3557be2cd50.PNG>


-train result

YOLOv3

YOLOv4

YOLOv5s

-processing

arduino
