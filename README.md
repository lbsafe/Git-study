# GIT 사용법

<p align="center"><img src="https://user-images.githubusercontent.com/65703793/230288932-04010e95-2e47-4b60-8dfa-612741886fd9.png" alt="js" width="200px"></p>

## git 기본 명령어

> Ctril+Shift+` 터미널 단축기

1. **git init**

    >git 사용을 선언한다.

    ```html
    git init
    ```

2. **git add test.html**

    >파일 현재 상태 기록 => 스테이징한다.
    ```html
    git add 파일명
    ```

3. **git commit -m'test'**

    >파일에 설명을 첨부한다.
    ```html
    git commit -m'테스트입니다.'
    ```

4. **git add**

    >파일을 스테이징한다.
    * 특정 파일 스테이징
    
        ```html
        git add test.html
        ```
    * 모든 파일 스테이징

        ```html
        git add .
        ```
    * 2개 이상 파일 스타이징

        ```html
        git add test.html test2.html
        ```

5. **git status**

    >git 상태창 열기
    ```html
    git status
    ```

6. **git log**

    >commit 내역 조회
    ```html
    git log --all --online
    ```

7. **git diff**

    >최근 commit과 현재 파일을 비교해서 보여준다.
    * git diff

        ```html
        j/k 조작 q종료
        ```
    * git difftool

        ```html
        hjkl 조작 :q종료
        git difftool 커밋아이디1 커밋아이디2
         => 커밋 끼리 비교 가능(아이디는 log를 통해 조회)
        ```
:pushpin:**Git Graph**   
>Git Graph 확장자를 통해 더 명확한 비교가 가능하다.   
단축키 ctrl + k + g
***

## git 터미널 명령어

1. **sudo**

    >관리자 권한으로 실행
    ```html
    $ sudo
    ```

2. **cd**
    
    >디렉토리
    * 홈 디렉토리로 이동

        ```html
        $ cd ~
        ```
    * 디렉토리로 이동

        ```html
        $ cd 디렉토리이름
        ```
    * 상위(부모) 디렉토리로 이동

        ```html
        $ cd ..
        ```

3. **mkdir**

    > 디렉토리 생성
        
    ```html
    $ mkdir 디렉토리이름
    ```

4. **touch**

    > 파일 생성
        
    ```html
    $ touch 파일이름
    ```

5. **rm**

    > 삭제
        
    * 파일 삭제

        ```html
        $ rm 파일이름
        ```
    * 디렉토리 삭제

        ```html
        $ rm -r 디렉토리이름
        ```
***

## README 작성법

1. **제목**

    ```js
    # This is a H1
    ## This is a H2
    ### This is a H3
    #### This is a H4
    ##### This is a H5
    ###### This is a H6
    ```
***

2. **BlockQuote**

    > ">" 표시로 사용한다
***

3. **목록**

    3-1. 순서있는 목록은 숫자와 점을 사용한다.  
    3-2. 순서없는 목록(글머리 기호: *, +, - 지원)
    * 순서1
        + 순서2
            - 순서3
***

4. **들여쓰기**

    4-1. 들여쓰기는 4개의 공백 또는 하나의 탭으로 한다.  
    4-2. 한줄을 내리고 쓰지 않으면 제대로 인식되지 않는다.
***

5. **줄바꿈**

    텍스트 뒤에 space bar를 두번 치고 enter를 누른다.
***

6. **코드블럭**

    6-1. < pre >< code >{code}</ code ></ pre > 방식  
    6-2. 코드블럭코드("```") js 을 이용하는 방법
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

7. **수평선 < hr/ >**

    ```
    ***
    ---
    ```
 ***

8. **링크**

    8-1. 참조링크
    ```js
    // code
    Link: [Google][googlelink]

    [googlelink]: https://google.com "Go google"
    ```
    > code Link: [Google][googlelink]

    [googlelink]: https://google.com "Go google"
    
    8-2. 자동연결

    일반적인 URL 혹은 이메일주소인 경우 적절한 형식으로 링크를 형성한다.

    ```js
    * 외부링크: <https://github.com/lbsafe/git-study>
    * 이메일링크: <lbsafe@naver.com>
    ```
    > 외부링크: <https://github.com/lbsafe/git-study>  
    > 이메일링크: <lbsafe@naver.com>
***

9. **강조**
    
    9-1. Italic
    ```js
    사용법: *text* or _text_
    ```

    *single asterisks*  
    _single underscores_  

    9-2. Bold
    ```js
    사용법: **text** or __text__
    ```
    **double asterisks**  
    __double underscores__  

    9-3. 삭선
    ```js
    사용법: ~~text~~
    ```
    ~~cancelline~~

    9-4. 동시 사용
    ```js
    사용법: ~~**_text_**~~
    ```
    ~~**_multi_**~~
***

10. **이미지**

    ![테스트 이미지](https://picsum.photos/id/237/300/300)

    ![테스트 이미지](https://picsum.photos/id/103/200/200 "사진")

    ```js
    사이즈 조절 기능은 없기 때문에 <img width="" height=""></img>를 이용한다.
    ```

    <img src="https://picsum.photos/seed/picsum/200" width="250px" height="200px" title="px(픽셀) 크기 설정" alt="이미지"></img>
***

11. **테이블**

    --- 정렬하지 않음  
    :--- 왼쪽으로 정렬  
    ---: 오른쪽으로 정렬  
    :---: 가운데 정렬  

    ```js
    | **번호** | **제작** | **나이** |
    |:---|:---:|---:|
    |1|오건희|26|
    |2|오뿌까|10|
    |3|오안녕|1|
    ```

    | **번호** | **제작** | **나이** |
    |:---|:---:|---:|
    |1|오건희|26|
    |2|오뿌까|10|
    |3|오안녕|1|
***
    
12. **토글**
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
***

13. **이모지**

    Markdown Emoji 설치 후 필요 코드 사용  
    _ex)_
    >:rocket:
    :smile:
    :dog:
    :cat:
    :grin:
    :exclamation:
    :star:
    :pushpin:
    :wink:
***