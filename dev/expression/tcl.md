# Tcl

* 출처 : Nuke-users Digest, Vol 98, Issue 4

  **변수선언**

  ```text
  [set x 2]
  ```

## 변수의 사용, list split

* 변수를 사용하는 방법, 변수를 사용해서 리스트 나누기.

  ```text
  [set x 2]
  [lindex {1 2 3} $x]
  //return 2 3
  ```

* 한줄로 처리시

  ```text
  [set x 2; return][lindex {1 2 3} $x]
  ```

