---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '698'
ht-degree: 77%
---
# 게재

이 스키마는 게재 작업 또는 템플릿을 나타냅니다.

템플릿은 필요한 모든 매개 변수를 포함하는 게재 템플릿입니다. 게재 템플릿은 클라이언트 콘솔에서 수동으로 실행하거나 이벤트 발생 시(스케줄러 또는 SOAP 호출에서 프로그래밍 방식으로 시작됨) 실행할 수 있습니다.

## 방법

| 방법 | 설명 |
| --- | --- |
| [AppendDeliveryPart](sm-delivery-appenddeliverypart.md) | 준비 중인 게재에 한 부분을 추가합니다. |
| [BuildForward](sm-delivery-buildforward.md) | HTML 페이지를 작성합니다. |
| [BuildMirror](sm-delivery-buildmirror.md) | HTML 미러 페이지를 작성합니다. |
| [BuildMirrorEx](sm-delivery-buildmirrorex.md) | HTML 미러 페이지를 작성합니다. |
| [BuildPreview](sm-delivery-buildpreview.md) | (외부 모드에) 게재 콘텐츠 또는 출력 파일 라인의 미리보기 기능이 내장되어 있습니다. |
| [BuildPreviewFromId](sm-delivery-buildpreviewfromid.md) | (외부 모드에) 게재 콘텐츠 또는 출력 파일 라인의 미리보기 기능이 내장되어 있습니다. |
| [BuildTargetDataSchema](sm-delivery-buildtargetdataschema.md) |  |
| [CleanupDeliveries](sm-delivery-cleanupdeliveries.md) | 중간 소싱 서버에서 특정 게재가 삭제되도록 지정합니다. |
| [로그 수집](sm-delivery-collectlogs.md) | 게재 목록의 게재 로그 메시지로 테이블 만들기 |
| [모델 만들기](sm-delivery-createfrommodel.md) | 템플릿(해당 내부 이름)에서 게재 생성. |
| [DeployTriggerMessageSingle](sm-delivery-deploytriggermessagesingle.md) | 실행 인스턴스에 트랜잭션 메시지를 게시합니다. 게시가 성공하면 true를 반환하고 그렇지 않으면 false를 반환합니다. |
| [DeployTriggermessages](sm-delivery-deploytriggermessages.md) | 실행 인스턴스에 선택한 트랜잭션 메시지 게시 |
| [DiagnoseHTML](sm-delivery-diagnosehtml.md) | HTML 콘텐츠 진단을 시작합니다. |
| [DispatchImages](sm-delivery-dispatchimages.md) | 애플리케이션 서버에서 이미지를 중간 소싱 서버에 전송하도록 명령합니다. |
| [ExecCommand](sm-delivery-execcommand.md) | 게재 시 명령을 실행합니다. |
| [ExecuteJob](sm-delivery-executejob.md) | 게재 중 동기 프로세스를 실행합니다. |
| [FinalizeMidPreparation](sm-delivery-finalizemidpreparation.md) | 중간 소싱 모드에서 게재 분석을 완료합니다. |
| [GetDeviceList](sm-delivery-getdevicelist.md) |  |
| [GetDlStatusAndLogs](sm-delivery-getdlstatusandlogs.md) | 저널 및 게재 상태에서 마지막 로그를 가져옵니다. |
| [GetFilesToDownload](sm-delivery-getfilestodownload.md) | 게재와 연계된 서버에 있는 파일 목록을 반환합니다. |
| [GetMidBroadLogs](sm-delivery-getmidbroadlogs.md) | 중간 소싱 모드에서 마지막으로 수정된 게재 로그를 가져옵니다. |
| [GetMidDeliveries](sm-delivery-getmiddeliveries.md) | 중간 소싱 모드에서 마지막으로 수정된 게재 상태를 가져옵니다. |
| [GetMidXtkKey](sm-delivery-getmidxtkkey.md) | 중간 서버의 Xtk 키를 반환합니다. |
| [GetMirrorURL](sm-delivery-getmirrorurl.md) | HTML 미러 페이지의 URL을 얻습니다. |
| [GetSeedList](sm-delivery-getseedlist.md) |  |
| [HtmlToText](sm-delivery-htmltotext.md) | HTML 콘텐츠를 일반 텍스트로 변환합니다. |
| [이미지 게시](sm-delivery-imagepublishing.md) | 후처리를 수행합니다. 이미지를 특정 폴더로 이동하고 온라인에서 사용할 수 있게 합니다. |
| [InstallTransactionalMessage](sm-delivery-installtransactionalmessage.md) | 실행 인스턴스에 트랜잭션 메시지 템플릿을 설치합니다. |
| [InvalidateDeliveryCache](sm-delivery-invalidatedeliverycache.md) | 중간 소싱(비공개 방법)을 제외하고 메시지 준비 마지막에 호출되어야 합니다. |
| [LaunchFCP](sm-delivery-launchfcp.md) | 게재 교정쇄 복사 시작 |
| [LoadExpandedContents](sm-delivery-loadexpandedcontents.md) | 종속성이 포함된 전처리의 구성 요소 목록을 로드합니다(개인화 블록, 옵션, 추가 스크립트 오브젝트 등). |
| [일시 중지](sm-delivery-pause.md) | 게재를 일시 중단합니다. |
| [재생](sm-delivery-play.md) | 게재를 시작합니다. |
| [준비](sm-delivery-prepare.md) | 게재 분석: 타겟팅 및 개인화 |
| [준비 및 시작](sm-delivery-prepareandstart.md) | 게재를 분석하고 오류 미발생 시 즉시 실행 |
| [PrepareFromId](sm-delivery-preparefromid.md) | 게재를 분석합니다. |
| [준비 메시지](sm-delivery-preparemessage.md) | 메시지 개인화 |
| [PrepareMessageImpl](sm-delivery-preparemessageimpl.md) | 메시지 개인화 |
| [PrepareMultipartRelated](sm-delivery-preparemultipartrelated.md) | 데이터베이스에 이메일에 포함할 이미지 저장 |
| [PrepareNotification](sm-delivery-preparenotification.md) | 기존 게재 액션에 추가되는 알림 분석 |
| [PrepareProof](sm-delivery-prepareproof.md) | 교정쇄 생성 차원에서 게재 분석 |
| [PrepareTarget](sm-delivery-preparetarget.md) | 게재 대상 카운트 및 중재 |
| [PrepareTargetImpl](sm-delivery-preparetargetimpl.md) | 게재 대상 카운트 및 중재 |
| [미리 보기 추출](sm-delivery-previewextraction.md) | 추출 파일 미리보기 |
| [로그 우선 순위 지정](sm-delivery-prioritizelogs.md) | 게재 목록에 대한 게재 로그의 우선 순위 지정 |
| [PrioritizeTarget](sm-delivery-prioritizetarget.md) | 게재 대상 중재 |
| [QueueNotification](sm-delivery-queuenotification.md) | 게재 템플릿을 참조하는 알림에 대한 큐 대기 요청. |
| [RecomputeStats](sm-delivery-recomputestats.md) | 게재 액션용 게재 및 추적 통계를 다시 계산합니다. |
| [SaveUrlInfo](sm-delivery-saveurlinfo.md) | 이 게재의 URL을 URL 템플릿으로 저장합니다. |
| [중지](sm-delivery-stop.md) | 진행 중인 게재를 중지합니다. |
| [StoreMirrorPageInfo](sm-delivery-storemirrorpageinfo.md) | 정보를 추가하여 게재 부분 세트의 미러 페이지를 생성합니다. |
| [StoreMirrorPageInfoEx](sm-delivery-storemirrorpageinfoex.md) | 정보를 추가하여 게재 부분 세트의 미러 페이지를 생성합니다. |
| [SubmitDelivery](sm-delivery-submitdelivery.md) | 시나리오(해당 내부 이름)에서 게재 생성 및 제출. |
| [SubmitDeliveryById](sm-delivery-submitdeliverybyid.md) | (내부 이름에 의해 식별되는) 시나리오에서 게재를 생성하고 제출합니다. |
| [SubmitJob](sm-delivery-submitjob.md) | 비동기 처리를 위해 게재용 작업 제출 |
| [SubmitMidSourcing](sm-delivery-submitmidsourcing.md) | 중간 소싱 모드의 게재를 제출합니다. |
| [SubmitNotification](sm-delivery-submitnotification.md) | 시나리오에서 알림 만들기 및 제출. |
| [UpdateBroadLogs](sm-delivery-updatebroadlogs.md) | 게재 로그 상태를 업데이트하고, 오류 처리를 수행하고, 게재 카운터를 업데이트합니다. |
| [UpdateCachedDelivery](sm-delivery-updatecacheddelivery.md) | 다른 스레드에서 최신 버전(비공개 방법)에 액세스할 수 있도록 메모리에서 게재를 수정할 때마다 호출되어야 합니다. |
| [UpdateImageConfig](sm-delivery-updateimageconfig.md) | 서버에 이미 있는 이미지를 감안하기 위해 imageConfig 노드를 수정합니다. |
| [ValidateWavesDefinition](sm-delivery-validatewavesdefinition.md) | 예약된 일괄 처리 정의에서 사용된 정보의 일관성 확인. |

## 제네릭 메서드

| 방법 | 설명 |
| --- | --- |
| [만들기](f-create.md) | 지정된 스키마에 해당하는 새 엔티티를 만듭니다. |
| [로드](f-load.md) | 주어진 스키마 및 키에 해당하는 엔티티를 로드하고 반환합니다. |
| [저장](m-entity-save.md) | 데이터베이스에 엔티티를 저장합니다. |
