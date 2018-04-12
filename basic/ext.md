# Ext

## 확장자의 이해 - VFX에 자주 사용하는 포멧만 추가했습니다.

| 구분 | bit | colorspace | 정보손실 | 압축 | 디스크캐쉬 |
| --- | --- | --- | --- | --- | --- |
| dpx | 10bit | log | 비손실 | 비압축 | 가능 |
| exr | 16~32bit | linear,ACES | 선택가능 | 4:3 | 선택가능 |
| jpg | 8bit | sRGB | 손실 | 압축 | . |
| png | 8~16bit | sRGB | 손실 | 압축 | . |
| tif | 8~32bit | sRGB | 비손실 | 선택가능 | 가능 |
| tga | 8bit | sRGB | 비손실 | 선택가능 | 가능 |

* 디스크캐쉬 : 용량을 좀 많이 차지하지만 이미지를 띄울 때 CPU를 사용하지 않아서 시퀀스 플레이시 하드디스크 속도만 빠르다면 실시간 플레이를 할 수 있는 형태.

## EXR의 압축방식\(압축률이 높은 순\)

* B44A : 개념은 B44와 같습니다. 단색 영역을 좀더 압축합니다.
* B44 : 데이터의 반정도를 손실시키는 압축입니다.
* DWAA : DWA형태의 압축입니다. 32개의 스캔라인블럭으로 픽셀을 압축합니다. OpenEXR 2.2부터 지원합니다.
* DWAB : DWA와 알고리즘은 같습니다. 256개의 스캔라인을 압축합니다. 많은 스캔라인을 압축하면 추후 전체 이미지를 한번에 읽을 때 성능을 향상시킬 수 있습니다. OpenEXR 2.2부터 지원합니다.
* Piz : 고화질의 HDR 사진소스에 적합합니다. 웨이블렛 방식을 채용하고 있습니다.
* Zip16 : 16줄을 Zip방식으로 압축, 렌더링 이미지 텍스쳐 방식에 적합합니다.
* Zip : 1줄을 Zip방식으로 압축, 압축은 느리나 읽을땐 빠릅니다.
* RLE : 스틸이미지 경우 로딩이 빠름, 용량은 조금만 줄어듭니다.
* PXR24 : 24비트 정도로 32비트 정보를 압축합니다.
* None : 무압축 방식입니다. 용량은 크지만 파일을 읽고 쓰는게 빠릅니다.

## 참고문서

* openEXR샘플 : [http://www.openexr.com/samples.html](http://www.openexr.com/samples.html)
* openEXR 기술문서 : [http://www.openexr.com/TechnicalIntroduction.pdf](http://www.openexr.com/TechnicalIntroduction.pdf)
* wiki EXR : [https://en.wikipedia.org/wiki/OpenEXR](https://en.wikipedia.org/wiki/OpenEXR)
* wiki에서 diskcache를 입력하면 disk buffer 페이지로 안내합니다. : [https://en.wikipedia.org/wiki/Disk\_buffer](https://en.wikipedia.org/wiki/Disk_buffer)

