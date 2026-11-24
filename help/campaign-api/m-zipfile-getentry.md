---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '86'
ht-degree: 10%
---
# getEntry

아카이브에서 파일 추출

```text
getEntry (filename)
```

## 매개변수

**파일 이름** 보관 파일의 이름입니다.

## 반환 값

파일의 내용이 포함된 ⌐ [MemoryBuffer](c-memorybuffer.md).

## 비고

이 메서드를 사용하려면 먼저 ⌐[open()](m-zipfile-open.md) 메서드로 아카이브를 열어야 합니다. 그렇지 않으면 예외가 발생합니다. 예: 다음 예제에서는 아카이브에서 dir/content.xml 파일을 추출하여 /tmp/ 폴더에 저장합니다.

```javascript
var zip = new ZipFile("/tmp/archive.zip")
zip.open()

var content = zip.getEntry("dir/content.xml")
content.save("/tmp/content.xml")

zip.dispose()
content.dispose()
```

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
