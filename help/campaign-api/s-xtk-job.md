---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '171'
ht-degree: 57%
---
# 작업

애플리케이션 서버에서 실행되는 배치 작업

## 방법

| 방법 | 설명 |
| --- | --- |
| [취소](sm-job-cancel.md) | 작업 취소 |
| [CheckIfJobInProcess](sm-job-checkifjobinprocess.md) | 작업이 계속 실행 중인지 확인 |
| [실행](sm-job-execute.md) | 작업을 동기식으로 실행합니다(이 모드에서는 진행 정보 및 취소를 사용할 수 없음). |
| [FilesExist](sm-job-filesexist.md) | 파일이 서버에 이미 존재하는지 확인합니다(파일로 또는 리소스 테이블에 있음). |
| [GetJobsInProcess](sm-job-getjobsinprocess.md) | 현재 실행 중인 비외부 작업을 반환합니다. |
| [GetStatus](sm-job-getstatus.md) | 작업 처리 진행 정보를 가져옵니다. 경고: 이 API는 고유한 로그 항목 목록을 반환하지 않습니다(호출자는 ID를 사용하여 중복을 제거해야 함). |
| [HasWarning](sm-job-haswarning.md) | 이 작업에 대해 경고 또는 오류가 생성되었는지에 대한 쿼리 |
| [일시 중지](sm-job-pause.md) | 작업 일시 정지 |
| [제출](sm-job-submit.md) | 비동기 처리 작업 제출 |
| [SubmitFromModel](sm-job-submitfrommodel.md) | 템플릿에서 작업 제출 |
| [SubmitSoapCall](sm-job-submitsoapcall.md) | 비동기 처리 작업 제출 |
| [WaitJobCancelled](sm-job-waitjobcancelled.md) | 작업이 취소되기를 기다리는 중 |

## 제네릭 메서드

| 방법 | 설명 |
| --- | --- |
| [만들기](f-create.md) | 지정된 스키마에 해당하는 새 엔티티를 만듭니다. |
| [로드](f-load.md) | 주어진 스키마 및 키에 해당하는 엔티티를 로드하고 반환합니다. |
| [저장](m-entity-save.md) | 데이터베이스에 엔티티를 저장합니다. |
