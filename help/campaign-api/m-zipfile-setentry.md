---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '60'
ht-degree: 15%
---
# setEntry

아카이브에 파일을 추가하거나 업데이트합니다.

```text
setEntry (filename, buffer)
```

## 매개변수

**파일 이름** 원본 파일의 이름입니다.

파일이 포함된 **buffer** MemoryBuffer.

## 반환 값

없음.

## 비고

[save()](m-zipfile-save.md) 메서드가 호출될 때까지 디스크에서 아카이브가 효과적으로 수정되지 않습니다.

## 기능

**클래스의 메서드:** [ZipFile](c-zipfile.md)

**다음 위치에서 사용 가능:**

* 콘텐츠 관리
* 게재 속성
* 유형화 규칙
* JSSP
* SOAP 메서드
* 웹 앱
* 워크플로
