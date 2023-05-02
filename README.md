# GIT 사용법

<p align="center"><img src="https://user-images.githubusercontent.com/65703793/230288932-04010e95-2e47-4b60-8dfa-612741886fd9.png" alt="js" width="200px"></p>

## git 기본 명령어

> Ctril+Shift+` 터미널 단축기

1. **git init**

    >git 사용을 선언한다.

    ```html
    git init
    ```

2. **git add**

    >파일 현재 상태 기록 => 스테이징한다.
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

3. **git commit -m'test'**

    >파일에 설명을 첨부한다.
    ```html
    git commit -m'테스트입니다.'
    ```

4. **git status**

    >git 상태창 열기
    ```html
    git status
    ```

5. **git log**

    >commit 내역 조회
    ```html
    git log --all --online
    ```

6. **git diff**

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
    :pushpin: **Git Graph**   
    >Git Graph 확장자를 통해 더 명확한 비교가 가능하다.   
    단축키 ctrl + k + g

7. **git branch**

    >브랜치를 생성해준다.
    ```html
    git branch 브랜치명
    ```
    * git branch -d 브랜치명

        ```html
        git branch -d branch_test
        
        merge 가 완료된 브랜치를 삭제한다.
        ```

    * git branch -D 브랜치명
        
        ```html
        git branch -D branch_test
        
        merge 하지 않은 브랜치를 삭제한다.
        ```

8. **git switch**

    >브랜치로 이동한다.
    ```html
    git switch 브랜치명
    ```

9. **git merge**

    >브랜치를 합친다.
    ```html
    git merge 브랜치명
    ```

    10-1. **다양한 merge 방법**

    **:one: 3-way merge**
    > 각 브랜치에 신규 commit이 있는 경우   
    일반적인 merge옵션

    ```html
                       commit2-1	
                     ↗          ↘
    commit1 → commit2 → commit3 → commit4
    ```

    **:two: fast-forward merge**
    > 기준 브랜치에 신규 commit이 없는 경우   
    예시를 기준으로 commit2-2를 main 브랜치로 지칭

    ```html
                       commit2-1 → commit2-2(main)
                     ↗
    commit1 → commit2
    ```
    * **'git merge --no-ff 브랜치명'** 을 통해 3-way merge 강제로 가능

    **:three: git rebase & merge**
    > 신규 branch의 시작점을 다른 commit으로 옮긴다.   
    간단하고 짧은 branch는 사용시 git log가 깔끔해진다.
    
    ```html
    <Before>
                       commit2-1 → commit2-2
                     ↗
    commit1 → commit2 → commit3
    ```
    ```html
    <After>
                                 commit2-1 → commit2-2
                               ↗
    commit1 → commit2 → commit3
    ```
    * **'git rebase & fast-forward merge'** 가 된다.   
    * :warning:Conflict가 발생할 위험도가 크다.
    * rebase & merge 과정   
        - step1. 새로운 브랜치로 이동   
        - step2. 'git rebase 메인 브랜치명(main)'   
        - step3. 메인 브랜치(main) 이동 후 'git merge 새로운 브랜치명'   

    **:four: squash & merge**
    > 새 브랜치의 커밋 내용을 합쳐서 메인 브랜치에 새로 커밋 내역을 만든다.

    ```html
    <Before>
                       commit2-1 → commit2-2
                     ↗
    commit1 → commit2 → commit3
    ```
    ```html
    <After>
        
    commit1 → commit2 → commit3 → commit4
    ```
    * **'git merge --squash 새 브랜치명'**

    **:exclamation: 주의사항**   
    * 브랜치를 합칠 때는 기준이 될 브랜치로 이동 후 merge한다.   
    * Conflct(충돌)발생 시 해당 코드를 수정하고 git add와 git commit을 해준다.
    
10. **git fetch**

    >원격 저장소의 변경사항을 로컬 저장소로 가져온다. 이때 git pull과 다르게 병합은 하지 않는다.
    
    ```html
    git fetch
    ```
    * git fetch --prune origin 

        ```html
        prune은 fetching 하기 전, 리모트에 존재하지 않는 remote tracking branch를 삭제한다.
        ```

11. **git reset**

    >커밋 취소하기

    * git reset --hard

        ```html
        $ git log --oneline
        af4068f (HEAD -> main, origin/main) README.md 내용수정
        e81d561 브랜치, 스위치, 머지 내용 추가
        78d3604 취소할 커밋


        마지막 커밋 78d3604을 취소하고 싶을 때,
        git reset --hard a3bbb3c(COMMIT ID) 명령어로 HEAD가 이전 커밋(e81d561)을 가리키도록 한다.

        특징: hard 옵션을 사용하면 돌아간 커밋 이후의 변경 이력은 모두 삭제한다.
        ```

    * git reset --mixed

        ```html
        git reset --mixed a3bbb3c 명령어로 리셋 후 코드를 반영하려면 add 명령어로 stage에 반영하고 커밋한다.

        특징: 변경 이력은 모두 삭제하지만 변경 내용은 남아있다.
        ```

    * git reset --soft

        ```html
        git reset --soft a3bbb3c 명령어로 리셋 후 코드를 반영할 때 add 를 하지 않고 바로 커밋이 가능하다.

        특징: 변경 이력은 모두 삭제하지만 변경 내용은 남아있다. stage 되어있다.
        ```
    
    * git reset HEAD^

        ```html
        git reset HEAD^

        특징: 가장 최근의 commit이 취소된다.(기본 옵션 mixed)
        ```

    * git reset --hard origin/main

        ```html
        origin/main branch와 일치시킨다.
        
        (git fetch로 remote tracking branch의 커밋을 remote 저장소의 브랜치와 일치시켰기에 효용이 있다.)
        ```
    
    **:heavy_exclamation_mark: 주의사항**   
    * branch를 공유하는 협업에서는 다른 사용자에게 에러를 발생시킬 수 있기에 사용을 자제한다.
    * 커밋이 로컬과 원격의 커밋 히스토리가 불일치해도 **git push --force** 로 강제 push 가능

12. **git revert**

    > 커밋 내용 되돌리기

    ```html
    git revert 2664ce8(돌아갈 COMMIT ID)

    특정 커밋의 내용만을 되돌리기에 코드충돌을 최소화 한다.
    ```
***

**:pushpin: 원격 저장소와 로컬 저장소의 소스코드를 일치시키는 방법**

```html
git fetch --prune origin 
git reset --hard origin/main 
git clean
```

1. **git fetch --prune origin**을 통해 remote tracking branch (origin/main)를 깃의 원격 저장소와 일치 시킨다.

2. **git reset --hard origin/main**를 통해 방금 전 동기화된 remote tracking branch (origin/main)에 로컬 브랜치를 일치 시킨다.

3. 만약 작성 중인 코드가 있었고, 필요 없다고 생각하면 **git clean**을 통하여 삭제한다. (필요에 따라 사용)
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