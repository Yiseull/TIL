# 이모지(emoji) 저장하기

이모지는 최대 4 Byte가 필요한데 MySQL의 utf8 문자셋의 경우, 글자당 최대 3바이트까지만 지원한다. 

❤ 와 같은 일부 이모지를 제외하고는 대부분 오류가 발생한다.

해결 방법은 utf8 문자셋을 utf8mb4으로 변경하면 된다. utf8은 utf8mb4의 서브셋이므로 인코딩 타입을 변경해도 기존의 저장된 문자열에는 문제가 없다.


## 1) my.ini 파일 변경

```C:\ProgramData\MySQL\MySQL Server 8.0```

위의 경로에 있는 my.ini 파일 맨 밑에 다음 내용을 추가한다.

```
collation-server=utf8mb4_unicode_ci
character-set-server=utf8mb4
skip-character-set-client-handshake
```

파일에 대한 권한이 없는 경우는 아래와 같이 바꿔준다.
1. 속성에 들어간다.
2. 상단의 '보안' 탭을 누르고 '편집'을 누른다.
3. '그룹 또는 사용자 이름(G)'에서 Users를 선택하고 Users의 사용 권한에 대해 모든 권한에 허용을 체크한다. 확인 -> 확인을 누르면 권한이 변경된다.


## 2) 기존 데이터베이스 및 테이블의 문자셋 변경

```bash
>> ALTER DATABASE [데이터베이스명] CHARACTER SET = utf8mb4 COLLATE = utf8mb4_unicode_ci;

>> use [데이터베이스명]

>> ALTER TABLE [테이블명] CONVERT TO CHARACTER SET utf8mb4;
```