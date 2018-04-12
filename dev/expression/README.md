# Expression

## 개  요

* 뉴크에서 사용할 수 있는 익스프레션에 대해서 설명합니다.
* 보통 노드의 값에서 '='키를 눌러서 익스프레션을 설정할 수 있습니다.
* Text 노드 내부에서도 익스프레션을 설정할 수 있습니다.
* 사실 뉴크에서 사용하는 익스프레션은 TCL언어 입니다.

## 삼항 연산자.

* 만약 조건이 참이면 A값을 출력 거짓이면 B값을 출력하는 삼항연산자는 옆의 수식을 사용합니다. `조건?A:B`

## 카메라의 Z포지션으로 2D좌표 구하기.

```text
1/((Camera3D1.Transform3DOp.Translate.X+Locator3D1.Transform3DOp.Translate.X)^2+ (Camera3D1.Transform3DOp.Translate.Y+Locator3D1.Transform3DOp.Translate.Y)^2+(Ca
mera3D1.Transform3DOp.Translate.Z+Locator3D1.Transform3DOp.Translate.Z)^2)
```

## link

* TCL 메뉴얼 : [https://www.tcl.tk/man/tcl8.4/](https://www.tcl.tk/man/tcl8.4/)
* 날짜 처리 : [http://www.tcl.tk/man/tcl8.5/tutorial/Tcl41.html](http://www.tcl.tk/man/tcl8.5/tutorial/Tcl41.html)

