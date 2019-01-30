# Commandline\_Rendering

## 개 요

* 터미널을 이용해서 뉴크파일을 렌더링 하는 방법을 배웁니다.
* 렌더팜이 없는 집에서 렌더링시 활용하면 좋습니다.
* nuke.nk 파일을 1~100프레임까지 렌더링

  ```text
  nuke -x renderfile.nk 1,100
  ```

* nuke.nk 파일에 Write노드가 2개 있는데 그 중에서 Write2 노드만 렌더링 하고 싶을 때.

  ```text
  nuke -X Write2 renderfile.nk 1,100
  ```

* 렌더링을 실행하는데 myname이라는 파일명으로 아웃풋 되도록 설정하고 싶을 때.
  * 일단 Write노드에 아래처럼 설정합니다.

    ```text
    [argv 0].%04d.exr //파일명만 가능.
    [argv 0].%04d.[argv 1] //확장자까지 가능.
    ```

  * 터미널에서는 다음과 같이 타이핑 합니다.

    ```text
    nuke -x renderfile.nk myname 1,5
    nuke -x renderfile.nk myname exr 1,5 //확장자까지 셋팅
    ```
* 파이썬을 이용한 exr을 jpg로 변환하는 스크립트.
  * imageconvert.py 파일을 하나 만듭니다.

    ```text
    r = nuke.nodes.Read(file="image.%04d.exr")
    w = nuke.nodes.Write(file="image.%04d.jpg")
    nuke.execute("Write1",1,5)
    quit()
    ```

  * 터미널에서 아래처럼 타이핑 합니다.

    ```text
    nuke -t < imageconvert.py
    ```

