# Hiero\_Python

## 개요

* foundry Hiero 와 관련된 파이썬 코드 예제를 다루는 페이지 입니다.

## import Sequence

* 파이썬을 이용해서 여러 미디어를 검색 importSequence 하는 방법.
* EDL, XML, AAF 파일이 EDLPath에 들어갈 수 있다.
* 출 처 : Nuke-python Digest Vol 99, Issue 2

```text
p = hiero.core.newProject()
topLevelBin = p.clipsBin()
seq = topLevelBin.importSequence(EDLPath)

seq.matchMedia(mediasPath)
```

