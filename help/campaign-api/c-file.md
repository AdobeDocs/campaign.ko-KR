---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '270'
ht-degree: 5%
---
# 파일(클래스)

파일 클래스

> 경고:
>
> 파일 API를 통한 액세스는 Adobe Campaign의 **var**, **sftp** 및 임시 폴더로 제한됩니다.

다음은 클래스를 사용하여 파일의 모든 줄을 순서대로 읽고 처리하는 방법에 대한 예입니다.

```javascript
var file = new File("/tmp/test.txt")
file.open()
for each(var line in file)
  logInfo(line)
file.close()
 
```

## 방법

| 방법 | 설명 |
| --- | --- |
| [파일](m-file-file.md) | 파일과 연결된 새 개체를 만듭니다. |
| [닫기](m-file-close.md) | 파일을 닫습니다. |
| [복사 위치](m-file-copyto.md) | 파일을 복사합니다. |
| [dispose](m-file-dispose.md) | 개체에서 사용하는 리소스를 해제합니다. |
| [플러시](m-file-flush.md) | 디스크에 강제로 쓰기 |
| [목록](m-file-list.md) | 디렉토리의 컨텐트를 나열합니다. |
| [mkdir](m-file-mkdir.md) | 현재 [File](c-file.md) 개체의 경로를 사용하여 디렉터리를 만듭니다. |
| [열기](m-file-open.md) | 파일을 읽기 또는 쓰기 모드로 엽니다. |
| [제거](m-file-remove.md) | 파일을 삭제합니다. |
| [이름 바꾸기](m-file-renameto.md) | 파일 이름을 바꿉니다. |
| [readln](m-file-readln.md) | 텍스트 파일의 한 줄을 읽습니다. |
| [rmdir](m-file-rmdir.md) | 디렉토리를 삭제합니다(계단식이 아님). |
| [쓰기](m-file-writeln.md) | 파일에 텍스트 줄을 씁니다. |

## 속성

| 속성 | 설명 |
| --- | --- |
| [읽을 수 있음](p-file-canread.md) | 파일을 읽을 수 있으면 true를 반환합니다. |
| [canWrite](p-file-canwrite.md) | 파일을 수정할 수 있으면 true를 반환합니다. |
| [존재함](p-file-exists.md) | 이 이름의 파일 또는 폴더가 있으면 true를 반환합니다. |
| [전체 이름](p-file-fullname.md) | 절대 파일 이름을 반환합니다. |
| [isDirectory](p-file-isdirectory.md) | 파일이 디렉터리인 경우 true를 반환합니다. |
| [isFile](p-file-isfile.md) | 파일이 존재하고 파일인 경우 true를 반환합니다. |
| [isOpen](p-file-isopen.md) | 파일이 열려 있으면 true를 반환합니다. |
| [마지막 수정일](p-file-lastmodified.md) | 마지막 수정 날짜를 Date 개체 형식으로 반환합니다. |
| [이름](p-file-name.md) | 확장명이 있지만 경로는 없는 파일의 이름을 반환합니다. |
| [경로](p-file-path.md) | 구분 기호로 끝나는 파일의 전체 경로를 반환합니다. |
| [크기](p-file-size.md) | 파일의 크기(바이트)를 반환합니다. |

## 기능

**다음 위치에서 사용 가능:**

* 콘텐츠 관리
* 게재 속성
* 유형화 규칙
* JSSP
* SOAP 메서드
* 웹 앱
* 워크플로
