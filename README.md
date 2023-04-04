# GIT 사용법
## README 작성법
1. BlockQuote
    > ">" 표시로 사용한다
***

2. 목록

    2-1. 순서있는 목록은 숫자와 점을 사용한다.<br>
    2-2. 순서없는 목록(글머리 기호: *, +, - 지원)
    * 순서1
        + 순서2
            - 순서3
***

3. 들여쓰기

    3-1. 들여쓰기는 4개의 공백 또는 하나의 탭으로 한다.<br>
    3-2. 한줄을 내리고 쓰지 않으면 제대로 인식되지 않는다.
***

4. 코드블럭

    4-1. < pre >< code >{code}</ code ></ pre > 방식<br>
    4-2. 코드블럭코드("```") js 을 이용하는 방법
<pre>
<code>
let 변수 = 'abc';
const 변수 = 'abc';
var 변수 = 'abc';
</code>
</pre>

```js
let 변수 = 'abc';
const 변수 = 'abc';
var 변수 = 'abc';
```
***

5. 수평선 < hr/ >
```
***
---
```
***

6. 링크

    6-1. 참조링크

    // code
    Link: [Google][googlelink]

    [googlelink]: https://google.com "Go google"

    6-2. 자동연결

    일반적인 URL 혹은 이메일주소인 경우 적절한 형식으로 링크를 형성한다.

    * 외부링크: <https://github.com/lbsafe/git-study>
    * 이메일링크: <lbsafe@naver.com>
***

7. 강조
    
    7-1. Italic

    *single asterisks* <br>
    _single underscores_ <br>

    7-2. Bold

    **double asterisks** <br>
    __double underscores__ <br>

    3-2. 삭선

    ~~cancelline~~
***

8. 이미지

    ![테스트 이미지](https://picsum.photos/id/237/300/300)

    ![테스트 이미지](https://picsum.photos/id/103/200/200 "사진")

    ```js
    사이즈 조절 기능은 없기 때문에 <img width="" height=""></img>를 이용한다.
    ```

    <img src="https://picsum.photos/seed/picsum/200" width="250px" height="200px" title="px(픽셀) 크기 설정" alt="이미지"></img>
***