---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '59'
ht-degree: 28%
---
# 다운로드 대상 파일

이 전송에서 사용되고 서버에 있는 파일 목록 반환

```text
[ XML filesToDownload, XML filesNotToDownload ] = GetFilesToDownload ( Number jobId )
```

## 매개변수

**jobId** 전송 식별자

## 반환 값

**filesToDownload** 요소 \[dataTransfer/properties/filesToDownload\]로 다운로드할 수 있는 파일 목록을 반환합니다.

**filesNotToDownload** 요소 \[dataTransfer/properties/filesNotToDownload\]로 다운로드할 수 없는 파일 목록을 반환합니다.

## 기능

**스키마:** [xtk:dataTransfer](s-xtk-datatransfer.md)

**정적:**

예
