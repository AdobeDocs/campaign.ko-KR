---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '54'
ht-degree: 29%
---
# 다운로드 대상 파일

게재와 연계된 서버에 있는 파일 목록을 반환합니다.

```text
[ XML filesToDownload, XML filesNotToDownload ] = GetFilesToDownload ( Number deliveryId )
```

## 매개변수

**deliveryId** 게재 식별자

## 반환 값

**filesToDownload** 요소 \[properties/filesToDownload\]로 다운로드할 수 있는 파일 목록을 반환합니다.

**filesNotToDownload** 요소 \[properties/filesNotToDownload\]로 다운로드할 수 없는 파일 목록을 반환합니다.

## 기능

**스키마:** [nms:delivery](s-nms-delivery.md)

**정적:**

예
