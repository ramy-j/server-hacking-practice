# 로컬 서버 취약점 공격 및 방어 실습

## 공격 대상 탐색과정

- 파일 업로드 기능이 있는 게시판
- 윈도우에서 PHP 로 작성된 환경

## 분석 과정

- 경로 출력 됨
- 검증 로직 존재 (화이트 리스트)
    1. test.a test.php 실패 test.png 성공
    2. 공백 문자 삽입 실패 (test.php%00.png, test.php;test.png, test.php[NULL].png)
    3. test.php:png 업로드는 성공했으나 내용이 업로드 되지 않음 (이유를 알수 없어서 이부분을 좀더 공부 해야 할거같음)

## 실패 원인

- 파일 업로드 기능의 화이트 리스트 확장자 검증 방식으로 인하여 공격 기능을 가진 php 파일 업로드 실패
- 업로드 되는 파일의 웹 디렉토리 경로는 확인 했으나 파일을 업로드 할수 없어서 공격 진행 불가능
