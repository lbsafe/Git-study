# GIT 사용법
## README 작성법

0. **제목**
    ```js
    # This is a H1
    ## This is a H2
    ### This is a H3
    #### This is a H4
    ##### This is a H5
    ###### This is a H6
    ```
***

1. **BlockQuote**
    > ">" 표시로 사용한다
***

2. **목록**

    2-1. 순서있는 목록은 숫자와 점을 사용한다.  
    2-2. 순서없는 목록(글머리 기호: *, +, - 지원)
    * 순서1
        + 순서2
            - 순서3
***

3. **들여쓰기**

    3-1. 들여쓰기는 4개의 공백 또는 하나의 탭으로 한다.  
    3-2. 한줄을 내리고 쓰지 않으면 제대로 인식되지 않는다.
***

4. **줄바꿈**

    텍스트 뒤에 space bar를 두번 치고 enter를 누른다.
***

5. **코드블럭**

    4-1. < pre >< code >{code}</ code ></ pre > 방식  
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

6. **수평선 < hr/ >**
    ```
    ***
    ---
    ```
 ***

7. **링크**

    6-1. 참조링크

    // code
    Link: [Google][googlelink]

    [googlelink]: https://google.com "Go google"

    6-2. 자동연결

    일반적인 URL 혹은 이메일주소인 경우 적절한 형식으로 링크를 형성한다.

    * 외부링크: <https://github.com/lbsafe/git-study>
    * 이메일링크: <lbsafe@naver.com>
***

8. **강조**
    
    7-1. Italic
    ```js
    사용법: *text* or _text_
    ```

    *single asterisks*  
    _single underscores_  

    7-2. Bold
    ```js
    사용법: **text** or __text__
    ```
    **double asterisks**  
    __double underscores__  

    3-2. 삭선
    ```js
    사용법: ~~text~~
    ```
    ~~cancelline~~

    3-3. 동시 사용
    ```js
    사용법: ~~**_text_**~~
    ```
    ~~**_multi_**~~
***

9. **이미지**

    ![테스트 이미지](https://picsum.photos/id/237/300/300)

    ![테스트 이미지](https://picsum.photos/id/103/200/200 "사진")

    ```js
    사이즈 조절 기능은 없기 때문에 <img width="" height=""></img>를 이용한다.
    ```

    <img src="https://picsum.photos/seed/picsum/200" width="250px" height="200px" title="px(픽셀) 크기 설정" alt="이미지"></img>
***

10. **테이블**

    --- 정렬하지 않음  
    :--- 왼쪽으로 정렬  
    ---: 오른쪽으로 정렬  
    :---: 가운데 정렬  

    ```js
    | 항목 | 제작 | 나이 |
    |:---|:---:|---:|
    |1|오건희|22|
    |2|오뿌까|10|
    ```

    | 번호 | 제작 | 나이 |
    |:---|:---:|---:|
    |1|오건희|26|
    |2|오뿌까|10|
***
    
11. **토글**
    ```js
    <details open>
    <summary>열린 토글바</summary>
    열린 상태로 보여준다.
    </details>
    <details>
    <summary>닫힌 토글바</summary>
    닫힌 상태로 보여준다.
    </details>
    ```

    <details open>
    <summary>열린 토글바</summary>
    열린 상태로 보여준다.
    </details>
    <details>
    <summary>닫힌 토글바</summary>
    닫힌 상태로 보여준다.
    </details>