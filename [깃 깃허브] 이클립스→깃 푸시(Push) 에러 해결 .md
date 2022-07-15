# [깃/깃허브] 이클립스→깃 푸시(Push) 에러 해결 (Eclipse : Push Results : reject-non-fast -forward)




이클립스에서 자바 패키지를 만들면 패키지명으로 폴더가 생성된다.

이때 패키지명에 . (마침표,온점)을 입력하면 하위폴더를 자동으로 생성할 수 있다.

예) 패키지명 : ch03.java_01 / 클래스명 : ConditionalOperator.java


- ch03
    - java_01
        
         ConditionalOperator.java
        


> 깃허브 디렉토리가 깔끔하지않으면 죽는 병에 걸렸습니다.
> 



<aside>
💡 보기 좋은 떡이 먹기도 좋은거 아닌가? 카테고리 정리 못참지!

</aside>


그런데,

어느순간 깃허브에 폴더대로 정리가 안되어있는것 아닌가?

- 이클립스 Git Repositories에서 폴더이동, 깃허브에 커밋한 파일 삭제후 재업로드 모두 실패했다.

자세한 이야기는 토글을 눌러 확인
    
    
<-- 토글내용 -->    

    
    이클립스에 연동되어있는 Git Repositories 안에서 폴더를 Drag&Drop 으로 옮겨 정리하였다.
    
    (이렇게 하면 깃허브에 자동 반영되는줄 알았던 것..)
    
    이 방법으로도 정리가 되지 않아서 
    
    아예 깃허브에 커밋했던 해당 폴더를 아예 삭제하고 
    
    패키지명, 클래스명 모두 동일하게 다시 생성하여 Push & Commit 하였으나 실패🤯
    
 
<-- 토글내용 끝 --> 



심지어 다시 생성한 자바 프로젝트 파일도 아래 같은 오류와 함께 Push 되지 않았다.

### main→main[rejected-non-fast-forward]

![Push Results : main→main [rejected-non-fast-forward]](https://github.com/geniigrace/TIL/blob/main/img/2207140101_git_rejected-non-fast-forward.png?raw=true)

Push Results : main→main [rejected-non-fast-forward]

검색하여 나와 같은 시행착오를 겪고계신 분들의 글을 참고했지만 (잘 정리해주신 분의 글은 아래 첨부하겠다.)

내 Configure Fetch의 Ref mappings 에는 아무 이상이 없었다.

(보통  Ref mappings 부분에 +refs/heads/*.refs/remotes/origin/* 과 같은 내용이 추가되어있는 듯 하다.)

![아무것도 없는 나의 “Ref mappings”](https://github.com/geniigrace/TIL/blob/main/img/2207140102_git_rejected-non-fast-forward.png?raw=true)

아무것도 없는 나의 “Ref mappings”

> 해결방법
> 

이클립스에서 Push가 안되는 상황이므로

직접 깃허브에 파일을 업로드하기로 했다.

![업로드 원하는 디렉토리에 Add file → Upload files](https://github.com/geniigrace/TIL/blob/main/img/2207140103_git_rejected-non-fast-forward.png?raw=true)

업로드 원하는 디렉토리에 Add file → Upload files

![Untitled](https://github.com/geniigrace/TIL/blob/main/img/2207140104_git_rejected-non-fast-forward.png?raw=true)

업로드하고싶은 폴더 그대로 Drag&Drop 하고  Commit Changes 하면 끝이다.

이후 다른 패키지명으로 생성하여 푸시/커밋 진행했을때도 문제없이 잘되었다.

근본적인 세팅의 부분에서 해결이 아니긴 하지만, 

나와 같은 문제를 겪는 분들이 계시다면 이런 방법도 있으니 참고가 되었으면 좋겠다.

같은 rejected-non-fast-forward 문제를 겪으신 분들의 후기를 보고

이후에 한번 그분들 방법대로 해볼생각이다.

같은 문제에 다양한 해결방법을 알고있으면 언젠가는 도움이 될테니..!
여러 포스팅을 찾아봤지만 가장 깔끔하게 정리되어 참고하기 좋았던 분의 포스팅도 

함께 남겨둔다.

// http://handa.tistory.com/36

[[Eclipse + GIT] rejected - non-fast-forward 오류 해결](https://hanyda.tistory.com/36)


2022-07-15

결국 또 한번의 오류로 위의 링크 글을 참고해서 

근본적인 오류를 해결했다.

>내가 처리했던건 임시방편이었던 것🥲
>
