---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '141'
ht-degree: 6%
---
# 추가

새 엔티티를 컬렉션에 추가합니다.

```text
add ( [index ], xml)
```

## 매개변수

**index** 이 인덱스 지점에 엔터티가 추가됩니다. 이 인수를 지정하지 않으면 엔티티가 목록 끝에 추가됩니다.

**xml** XML 양식에 삽입할 엔터티입니다.

## 반환 값

요소가 생성되었습니다.

## 비고

다음 예제에서는 새 요소를 컬렉션에 추가하는 두 가지 방법을 보여줍니다. 첫 번째 솔루션은 요소의 전체 정의를 add() 메서드에 전달하지만 두 번째 솔루션은 빈 &lt;attachment/> 요소를 전달한 다음 속성을 일반적인 방법으로 할당합니다.

```javascript
var delivery = NLWS.nmsDelivery.load("12435")

delivery.attachment.add(
  {attachment: {
    compressMode: "print", filterActive: "false", label: "First File", 
    nameScriptActive: "false", type: "normal", upload: "false", 
    name: { $: "file1.txt" }
  }})

var attach = delivery.attachment.add()
attach.label            = "Second File"
attach.name             = "file2.txt"
attach.compressMode     = "print"
attach.type             = "normal"
attach.filterActive     = false
attach.nameScriptActive = false
attach.upload           = false

delivery.save()
```

두 솔루션은 동일하지만 두 번째 솔루션을 사용하면 속성 유형에 해당하는 JavaScript 유형을 사용할 수 있지만 첫 번째 솔루션은 문자열만 지원합니다.

## 기능

**클래스의 메서드:** [EntityCollection](c-entitycollection.md)

**다음 위치에서 사용 가능:**

* 콘텐츠 관리
* 게재 속성
* 유형화 규칙
* JSSP
* SOAP 메서드
* 웹 앱
* 워크플로
