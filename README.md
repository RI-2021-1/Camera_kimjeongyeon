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
