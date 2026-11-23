---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '58'
ht-degree: 22%
---
# getImageUrl

공개 리소스 액세스 URL 생성 활성화

```text
getImageUrl (ID|internal name)
```

## 매개변수

공용 리소스의 **ID\|내부 이름** ID 또는 리소스의 내부 이름입니다.

## 반환 값

공개 리소스 액세스 URL을 반환합니다.

## 비고

리소스는 전면 서버에 게시해야 합니다. 예:

```xml
              <%= getImageUrl(content.@["banner-id"]) %>Code HTML généré :http://media.adobe.com/res/img/18cd386d9e8b7f35f3477ac6a9efd762.jpg
```

## 기능

**다음 위치에서 사용 가능:**

* 콘텐츠 관리
* 게재 속성
* 게재 메시지
* 유형화 규칙
* 가져오기
* JSSP
* SOAP 메서드
* 웹 앱
* 워크플로
