# Python

## 개 요

* 뉴크에는 파이썬이 내장되어 있습니다.
* 파이썬을 이용해서 뉴크에서 불편하거나 필요한 기능을 작성해서 툴을 좀더 확장할 수 있습니다.
* 매 픽셀의 연산같은 무거운 연산은 NDK를 활용한 C++, Blink Script를 추천합니다.

## 파이썬 참고 사이트.

* Nukepedia : [http://www.nukepedia.com](http://www.nukepedia.com)
  * 오픈된 스크립트와 기즈모들이 공유되는 사이트 입니다.

## Documents

* Guide : [https://www.thefoundry.co.uk/products/nuke/developers/90/pythondevguide/](https://www.thefoundry.co.uk/products/nuke/developers/90/pythondevguide/)
* Python API : [http://docs.thefoundry.co.uk/nuke/90/pythonreference/](http://docs.thefoundry.co.uk/nuke/90/pythonreference/)
* Hiero python API : [https://www.thefoundry.co.uk/products/hiero/developers/2.0/hieropythondevguide/](https://www.thefoundry.co.uk/products/hiero/developers/2.0/hieropythondevguide/)

## 만약 사용자를 위한 인터페이스\(GUI\)를 개발다면 선택할 수 있는 솔루션

* 뉴크에서는 GUI를 만드는 방법이 3가지 있습니다.
* TCL/TK 사용하기 : 하위 호환성\(뉴크 전버젼에서 작동되는 코드\)를 유지하면서 간단한 GUI를 만들때 추천합니다.
* Python PyQt 사용하기.
* Python PySide 사용하기.
* PySide는 뉴크 내부에 내장되어 있습니다. 최신 뉴크를 사용하신다면, Pyside사용을 추천합니다.

