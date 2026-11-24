---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '199'
ht-degree: 5%
---
# execCommand

> 경고: 이 함수는 온-프레미스 환경에서 사용할 수 있습니다.

명령을 실행하고 오류 코드와 표준 출력을 캡처합니다.

```text
execCommand (command [, bNoThrow ])
```

## 매개변수

**command** 매개 변수로 실행할 명령입니다.

**bNoThrow** true를 사용하면 명령이 0을 반환하지 않더라도 출력 및 오류 코드를 가져올 수 있습니다(기본적으로 false).

## 반환 값

첫 번째 요소가 명령의 반환 코드에 해당하고(반환 코드가 0과 다른 경우 예외 항목이 있음) 두 번째 요소가 생성된 표준 출력을 포함하는 문자열인 테이블을 반환합니다.

## 비고

bNothrow 옵션이 없으면 명령을 실행할 수 없거나 오류가 발생하여 명령을 실행하는 경우 예외가 발생합니다. bNoThrow가 true인 경우 명령을 실행할 수 없는 경우에만 예외가 발생합니다. 이 함수를 사용하려면 연산자에 &#39;createProcess&#39; 권한이 있어야 합니다. 그렇지 않으면 예외가 발생합니다. 설치에 따라 일부 명령이 차단 목록에 있을 수 있습니다. 예: ln, dd, openssl, curl, wget, python, python3, perl, ruby, sh, bash, dash, zsh, base64, nlserver, node, phantomjs, java, awk, nc, telnet, ssh, scp, ftp.

## 예제

```text
var result = execCommand('gpg-exec.sh gpg --no-tty --yes -r CampaignOperations@adobe.com --encrypt "file_to_encrypt"', true);
```

## 기능

**다음 위치에서 사용 가능:**

* 콘텐츠 관리
* 게재 속성
* 유형화 규칙
* JSSP
* SOAP 메서드
* 웹 앱
* 워크플로
