2/10 Homework

Easy.net1

지난번에 우연한 계기로 이 문제를 건드려본적이 있었다.

그때는 알던 리버싱이랑은 달라서 디컴파일(?)까지 진행하고 포기했었다.

나중에 꼭 한번 풀어봐야지 했는데, 이번 과제를 통해 풀게 되었다.

[문제 내용]

실행시켜보면 알겠지만, KEY값을 입력받고 틀리다면 invalid k3y.. 를 출력하고, hack the plane이란, 문자를 클릭하면 base64인코딩된 문자열이 나온다. aHR0cDovL2lsc3B5Lm5ldC8= 인데 디코딩하면 
http://ilspy.net/ 가 나온다. 우리한테 힌트는 이미 과제 낼 때 주어졌으니 이 힌트는... ㅠ

[풀이]

어쨋든 그때는 디컴파일하는것도 힘들었지만, 지금은 디컴파일하는법도 알고 소스코드도 그때 대충 봤었다.

그때 기억상으로 이 코드를 똑같이 옮겨와서 내 컴퓨터에서 컴파일해서 돌리면 문자열을 바탕으로 연산하는 계산이 몇가지 있는데 그 과정을 통해 키값을 알아낼 수 있었던 것 같다. (그때 힌트 얻었던 부분) 물론 변수명이 public string odf03mfg03mn4__dsfij9834rosdf043 이런식이라서 알아보는데 힘들다.

CODEGATE때 신나게 IDA로 분석만 하다가와서 이번엔 자신이 있었다.닷넷프로그램은 찾아보니 관리코드 기반 언어라서 디컴파일이 매---우 잘된다는 것을 알았다. 대신 이 문제는 변수명이... ㅠㅠ

어쨋든 리버싱을 해보니 의심가는 부분이

// POWEROFXX_easy_reversing.Form1

[1번 의심]

![alt tag](https://github.com/y2sman/SweetHomeWork/blob/master/2-10/img/easy_1.PNG)

[2번 의심]

![alt tag](https://github.com/y2sman/SweetHomeWork/blob/master/2-10/img/easy_2.PNG)

이다. 어쨋든 비밀번호를 연산해야되는데, 인자로 string input / string key 해서 결과값을 내는 부분이 이 두 함수 밖에 없다. 사실 함수 자체가 몇개 없다. 그중에 연산(?)을 하는건 이 두개인것같다.
