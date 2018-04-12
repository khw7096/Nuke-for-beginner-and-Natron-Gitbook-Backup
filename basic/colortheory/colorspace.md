# Colorspace

## 컬러스페이스란.

* 어떻게 픽셀의 색을 구성할 것인지 정의한 방법들입니다.
* 하나씩 하나씩 배워봅시다.

## 자세하게..

![](../../.gitbook/assets/colorspace_dduck.jpeg)

* 여러분이 친구3명과 떡볶이 집에 갔습니다.
* 메뉴판에 순한맛, 보통맛, 매운맛이 있습니다.
* 보통맛을 주문했습니다.
* 어떤 친구에게는 보통맛이 매울 수 있고, 어떤 친구에게는 어쩌면 순할 수 있습니다.
* 이처럼 여러분이 만든 순한 빨간색이 어떤 장비에서는 주황색일 수 있고, 어떤 장비에서는 채도가 높은 빨강일 수 있습니다.
* 이런 오류가 없기 위해서는 이미지가 출력되는 최종장비의 컬러스페이스를 적용해서 미리 색이 어떻게 나오는지 시뮬레이션 해보는것이 하나의 방법입니다.
* 뉴크에서는 이런 상황을 설정하기 위해서 컬러스페이스 설정, LUT\(Lookup Table\) 적용을 해볼 수 있습니다.

## sRGB

* 일반사람에게는 가장 많이 사용하는 컬러스페이스 입니다.
* 일반적으로 jpeg, png 이미지등등 많은 이미지들이 기본적으로 sRGB 컬러스페이스로 저장됩니다.
* 감마 2.2에 가깝습니다. 실제로는 소수점 아래로 몇자리가 더 있습니다.
* [https://en.wikipedia.org/wiki/SRGB](https://en.wikipedia.org/wiki/SRGB)

## Rec709

* HDTV작업을 할 때 사용하는 컬러스페이스 입니다.
* [https://en.wikipedia.org/wiki/Rec.\_709](https://en.wikipedia.org/wiki/Rec._709)

## Log / Cineon

* 확장자는 보통 cin, dpx를 사용합니다.
* 코닥에서 필름을 디지털로 바꾸기위해 개발된 컬러스페이스 입니다.
* 10비트까지 일반적으로 저장합니다.\(16비트도 저장이 가능하지만 시장에서 잘 사용하지 않습니다.\)

## CameraRaw & Camera Colorspace

* 카메라 회사는 자신의 제품에 잘 맞는 컬러스페이스를 설계하고 같이 출시합니다.
* 제조사별로 서로 다른 컬러스페이스를 그대로 작업에 활용하면 몇몇 컬러스페이스는 문제가 될 수 있습니다.
* 보통은 자주 사용하는 일반적인 컬러스페이스로 컨버팅해서 VFX작업을 진행합니다.
* AlexaV3LogC 같은 형태의 컬러스페이스가 카메라 제조사와 관련된 컬러스페이스 입니다.

## Linear

* VFX작업시 자주 사용하는 exr포멧의 기본 컬러스페이스 입니다.
* 인간을 위한 감마가 적용되지 않은 값 자체이며, 컬러 값을 데이터로 바로 저장한 구조입니다.

## OpencolorIO v1.0.x / ACES

* Academy Color Encoding System의 약자입니다.
* ACES의 컬러 메니징 시스템인 OpenColorIO는 무료이며, 오픈소스입니다.
* ACEScg컬러스페이스가 ACES작업에서 사용하는 컬러스페이스 입니다.
* 이미지 캡쳐, 편집, VFX작업, DI, 인코딩등을 할 때 하나의 컬러스페이스로 작업을 통일하기 위해서 표준으로 만들어졌습니다. 
* OpencolorIO : [http://opencolorio.org](http://opencolorio.org)
* OpencolorIO Google Code : [https://code.google.com/archive/p/opencolorio/downloads](https://code.google.com/archive/p/opencolorio/downloads)
* ACES : [http://www.oscars.org/science-technology/sci-tech-projects/aces](http://www.oscars.org/science-technology/sci-tech-projects/aces)

## P3DCI

* 미국 디지털 프로젝션 장비에서 사용하는 일반적인 컬러스페이스 입니다.
* 보통 DI실 프로젝터가 이 컬러스페이스를 사용합니다.
* [https://en.wikipedia.org/wiki/DCI-P3](https://en.wikipedia.org/wiki/DCI-P3)

