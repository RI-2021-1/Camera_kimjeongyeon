# Camera_kimjeongyeon

**USB 카메라**

준비된 USB 카메라를 컴퓨터에 연결한다.



**카메라 연결 정보**

다음과 같은 명령어로 카메라가 잘 연결되었는지 확인한다. 구동시 아래와 같이 메시지를 통해 카메라 접속 유무를 확인할 수 있다.

```$ lsusb```

![camera_lsusb](https://user-images.githubusercontent.com/84000076/121798411-1fa91200-cc61-11eb-9542-7a0f4ed1c72c.png)



**uvc camera 패키지 설치**

다음으로 ros 버전에 맞는 uvc camera 패키지를 설치한다.

```$ sudo apt-get install ros-melodic-uvc-camera```

image 관련 패키지도 설치해준다.

```$ sudo apt-get install ros-melodic-image-*```

```$ sudo apt-get install ros-melodic-rqt-image-view```



**uvc_camera 노드 실행**

다음과 같은 명령어로 uvc_camera 노드를 실행한다.

```$ roscore```

```$ rosrun uvc_camera uvc_camera_node```



**토픽 메시지 확인**

다음과 같은 명령어로 토픽 메시지를 확인해 카메라 정보(camera_info)와 이미지 정보(image_raw)가 퍼블리시되고 있음을 볼 수 있다.

```$ rostopic list```

![camera_topicmessage](https://user-images.githubusercontent.com/84000076/121798594-34d27080-cc62-11eb-98b1-a5d9dc159e18.png)



**image_view 노드를 통한 이미지 정보 확인**

이미지 정보를 확인할 수 있는 image_view 노드를 실행한다. 실행시 아래와 같이 작은 창에 카메라의 이미지가 표시된다.

```$ rosrun image_view image_view image:=/image_raw```

![camera_imageview](https://user-images.githubusercontent.com/84000076/121798669-972b7100-cc62-11eb-9226-59011c9b77c9.png)



**rqt_image_view 노드를 통한 이미지 정보 확인**

rqt_image_view는 image_view에 rqt 플러그인으로 GUI 요소가 추가된 것이다. 실행 후에도 실행된 이미지 뷰어 GUI 상에서 토픽을 선택할 수 있다.

```$ rqt_image_view image:=/image_raw```

![camera_rqt_image_view](https://user-images.githubusercontent.com/84000076/121798752-03a67000-cc63-11eb-8ad2-0c3a8b970310.png)



**Rviz를 통한 이미지 정보 확인**

먼저 Rviz를 실행한다.

```$ rviz```

Rviz가 실행되면 왼쪽 하단의 Add 버튼을 클릭하여 display type에서 Image를 선택한다.

![rviz_1](https://user-images.githubusercontent.com/84000076/121798793-5b44db80-cc63-11eb-84a3-fff12caa99d6.png)

그 다음 Image Topic의 값을 '/image_raw'로 변경한다. 변경 후 다음과 같이 이미지가 표시된다.

![rviz_2](https://user-images.githubusercontent.com/84000076/121798832-947d4b80-cc63-11eb-9181-8df5d0df6eb8.png)

