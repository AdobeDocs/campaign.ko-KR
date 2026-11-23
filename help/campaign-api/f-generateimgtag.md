---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '64'
ht-degree: 20%
---
# generateImgTag

공개 리소스를 기반으로 HTML &lt;img> 태그를 생성할 수 있습니다.

```text
generateImgTag (ID)
```

## 매개변수

**ID** 공용 리소스 ID

## 반환 값

공개 리소스 정의에 포함된 이미지의 속성과 함께 HTML &lt;img> 태그를 반환합니다.

## 비고

리소스는 전면 서버에 게시해야 합니다. 예:

```xml
              <%= generateImgTag(content.@["banner-id"]) %>Code HTML généré :<img src="http://media.adobe.com/res/img/18cd386d9e8b7f35f3477ac6a9efd762.jpg" width="800" height="200" alt="My image"/>
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
