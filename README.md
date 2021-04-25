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
            Up and down verticals, cameras detect apples in 30fps, yielding average values.
            And determine the quality and classification.


-datasets

taken by myself

3500 images. Train : Val : Test = 7 : 2 : 1


-requirements
