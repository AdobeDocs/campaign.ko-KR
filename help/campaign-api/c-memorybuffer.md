---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '270'
ht-degree: 6%
---
# MemoryBuffer(클래스)

메모리에 저장된 이진 콘텐츠를 나타냅니다.

는 파일에서 데이터를 조작하기 위한 중간 개체입니다.

## 방법

| 방법 | 설명 |
| --- | --- |
| [dispose](m-memorybuffer-dispose.md) | 개체에서 사용하는 리소스를 해제합니다. |
| [로드](m-memorybuffer-load.md) | 파일의 내용을 버퍼에 로드합니다. |
| [저장](m-memorybuffer-save.md) | 버퍼의 내용을 파일에 저장합니다. |
| [toXML](m-memorybuffer-toxml.md) | [MemoryBuffer](c-memorybuffer.md)의 콘텐츠에서 가져온 XML JavaScript 개체를 반환합니다. 이 함수는 더 이상 사용되지 않습니다. [toDocument()](m-memorybuffer-todocument.md)을(를) 사용하십시오. |
| [toDocument](m-memorybuffer-todocument.md) | 이 버퍼의 텍스트 콘텐츠에서 XML 문서를 반환합니다. |
| [toString](m-memorybuffer-tostring.md) | 문자열 형식으로 [MemoryBuffer](c-memorybuffer.md)의 내용을 반환합니다. |
| [fromString](m-memorybuffer-fromstring.md) | 문자열의 내용을 버퍼에 로드합니다. |
| [toBase64](m-memorybuffer-tobase64.md) | 밑줄 64에 인코딩된 문자열의 버퍼 또는 일부를 변환합니다. |
| [appendBase64](m-memorybuffer-appendbase64.md) | 밑줄 64로 인코딩된 문자열의 데이터를 버퍼 끝에 추가합니다. |
| [removeAll](m-memorybuffer-removeall.md) | 버퍼를 플러시합니다. |
| [sha1](m-memorybuffer-sha1.md) | MemoryBuffer 콘텐츠의 SHA-1 서명을 계산합니다. |
| [sha224](m-memorybuffer-sha224.md) | MemoryBuffer 콘텐츠의 SHA-2 224비트 서명을 계산합니다. |
| [sha256](m-memorybuffer-sha256.md) | MemoryBuffer 콘텐츠의 SHA-2 256비트 서명을 계산합니다. |
| [sha384](m-memorybuffer-sha384.md) | MemoryBuffer 콘텐츠의 SHA-2 384비트 서명을 계산합니다. |
| [sha512](m-memorybuffer-sha512.md) | MemoryBuffer 콘텐츠의 SHA-2 512비트 서명을 계산합니다. |
| [fromHexString](m-memorybuffer-fromhexstring.md) | 버퍼에 16진수 문자열의 콘텐츠를 로드합니다. |
| [toHexString](m-memorybuffer-tohexstring.md) | 버퍼를 16진수 문자 문자열로 변환합니다. |
| [hmac](m-memorybuffer-hmac.md) | 버퍼의 MD5, SHA-1 또는 SHA-256 해시를 계산합니다. |

## 속성

| 속성 | 설명 |
| --- | --- |
| [크기](p-memorybuffer-size.md) | 버퍼 크기(바이트)를 반환합니다. |
| [isEmpty](p-memorybuffer-isempty.md) | 버퍼가 비어 있으면 true를 반환합니다. |

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
