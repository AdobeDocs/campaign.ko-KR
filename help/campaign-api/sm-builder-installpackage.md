---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '38'
ht-degree: 18%
---
# 패키지 설치

패키지를 설치합니다.

```text
InstallPackage ( XML parameters )
```

## 매개변수

가져올 패키지가 포함된 **매개 변수** XML 요소입니다.

## 반환 값

없음.

## 비고

SpecFile.Generate() 메서드로 생성된 패키지는 빌더 요소에 캡슐화해야 합니다. 예:

```javascript
var params =
  {builder:
    {package:
      { ... }
    }
  }

NLWS.xtkBuilder.InstallPackage(params)
```

## 기능

**스키마:** [xtk:builder](s-xtk-builder.md)

**정적:**

예
