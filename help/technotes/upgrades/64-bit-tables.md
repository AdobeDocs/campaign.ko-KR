---
title: 64비트 스키마
description: Campaign Standard 마이그레이션된 고객을 위한 Adobe Campaign v8의 64비트 스키마에 대해 알아봅니다
feature: Technote
role: Admin
exl-id: ab5f01fd-4ad5-46e9-b132-011fe0f7bbd2
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: d0e9f0b2-1f2b-4134-9844-49cd4e950f27
    internal-label: Campaign v8
feature_v2:
  - id: ab81f6c3-9317-564f-af92-6670a8784294
    internal-label: Technote
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
source-git-commit: 7fd43a8d3d6afe9f4d3fb000d925cc6185ba9f40
workflow-type: tm+mt
source-wordcount: '176'
ht-degree: 7%
---
# 64비트 스키마 {#sixty-four-bit-tables}

Campaign Standard에서 Campaign v8로 원활하게 전환하기 위해 몇 개의 표가 32비트에서 64비트로 변경되었습니다. 실제로 Campaign Standard은 여러 기본 스키마에서 64비트 PK를 지원하는 반면, Campaign v8은 대부분의 스키마에서 32비트 PK를 지원합니다.

## 제한 사항

* 이 기술 변경 사항은 Campaign Standard에서 마이그레이션하는 고객에게만 적용됩니다.
* 스키마 및 브로드로그 확장은 64비트에서 지원되지 않습니다. 32비트로 유지됩니다.
* 기술 사용자에게 전송된 게재와 관련된 로그는 Campaign v8에서 사용할 수 없습니다.
* PostgreSQL만 지원됩니다.

## 수정된 스키마

다음은 64비트로 변경된 스키마와 수정된 속성 목록입니다.

| 스키마 이름 | 속성 이름 |
|--- |--- |
| nms:broadLogRcp | ID |
| nms:trackingLogRcp | ID |
| nms:excludeLogRcp | ID |
| nms:broadLogVisitor | ID |
| nms:trackingLogVisitor | ID |
| nms:propositionRcp | interactionId |
| nms:propositionVisitor | interactionId |
| nms:webTrackingLog | ID |
| nms:tmpBroadcast | message-id |
| nms:tmpMarketingPressure | message-id |
| nms:tmpBroadcastExclusion | message-id |
| nms:tmpBroadcastPaper | message-id |
| nms:broadLogAppSubRcp | ID |
| nms:trackingLogAppSubRcp | ID |
| nms:excludeLogAppSubRcp | ID |
| nms:webEvent | broadLogSrc-id, broadLogRemkt-id |
| nms:broadLogMid | mktBroadLogId |
| nms:mirrorPageSearch | remoteMessageId |
