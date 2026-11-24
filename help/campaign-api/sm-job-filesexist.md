---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '51'
ht-degree: 33%
---
# 파일 있음

파일이 서버에 이미 존재하는지 확인합니다(파일로 또는 리소스 테이블에 있음).

```text
XML exist = FilesExist ( XML files )
```

## 매개변수

**파일** 파일 목록(@name), MD5 키(@md5) 및 리소스(@checkResource)일 수 있는지 여부를 나타내는 부울입니다.

## 반환 값

**존재** 결과 목록(@md5 및 @exists)

## 기능

**스키마:** [xtk:job](s-xtk-job.md)

**정적:**

예
