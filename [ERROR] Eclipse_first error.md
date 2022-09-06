# [이클립스] 이클립스 설치 후 초기 오류 해결(Eclipse : The selection cannot be launched and there are no recent launches)

> **첫 에러에 직면하다.**
> 

Java 공부를 위해 이클립스를 설치하고 첫 예제 소스코드를 Run 했더니

<aside>
🚫 “ *The selection cannot be launched and there are no recent launches.*”

</aside>

라는 문구와 함께 팝업상자가 나왔다.

난 오늘 처음인데 최근 실행된게 없다는 문구에 꽤나 당황스러웠다.

검색해보니 default 설정의 문제였던 것.

> **해결 방법**
> 

(Macbook 기준)

***Eclipse → Preferences → Run/Debug → Launching → Launch Operation*** 항목에서

***Launch the associated project*** 를 선택✅한다

![img](https://github.com/geniigrace/TIL/blob/main/img/220712_eclips_error_01.png?raw=true![image](https://user-images.githubusercontent.com/109070629/178994178-10632d89-cc0a-49e0-9abb-7d2567cbb334.png))

나처럼 처음 사용하는 사용자에게는 당연히 최근 실행한 파일이 없는데

이 설정이 기본으로 설정되어있다는게 조금은 당황스러웠다.

-끝- 
