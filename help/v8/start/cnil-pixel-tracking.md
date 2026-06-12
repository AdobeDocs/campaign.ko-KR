---
title: 이메일 추적 픽셀 및 CNIL 지침
description: 이메일 추적 픽셀 및 규정 준수 노력을 지원할 수 있는 Adobe Campaign 기능에 대한 CNIL의 업데이트된 지침을 이해합니다.
feature: Overview
role: User
level: Beginner
hide: true
source-git-commit: 5c27d45ebac8ad300d35ef0ff858fbdaef6ec9fb
workflow-type: tm+mt
source-wordcount: '857'
ht-degree: 1%

---

# 이메일 추적 픽셀에 대한 CNIL의 업데이트된 지침 이해

이 게시물은 정보 제공용으로만 제공됩니다. 이는 법률적인 조언이 아니며, 해당 법률의 준수를 보증하지 않습니다. 아래에 설명된 Adobe Campaign 제품 기능은 적절하게 구성되고 작동되어 규정 준수 구현을 지원할 수 있는 기본 구성단위입니다. 각 고객은 해당 법률에 따라 의무를 결정하고 준수할 책임이 있습니다.

## 개요

2026년 4월 14일, 프랑스 데이터 보호 당국인 CNIL(Commission national de l&#39;informatique et des libertés)은 [이메일 내의 픽셀 추적 사용에 대한 권장 사항](https://www.cnil.fr/sites/default/files/2026-04/recommandation-pixels_de_suivi.pdf)을 발표했습니다. 안내서에서는 동의가 필요한 시기를 명확히 설명하고 이메일 픽셀 추적에 대한 적절한 동의 사례의 중요성을 강조합니다. 이 정책은 프랑스에 기반을 둔 구독자에게 이메일을 게재하는 모든 엔터티의 전송 사례에 영향을 줄 수 있습니다.

CNIL은 기업이 이메일 수신자(&#39;사용자&#39;)에게 추적 픽셀의 존재 여부, 목적, 사용자의 옵트아웃 권리 등을 알리도록 권고일로부터 3개월의 기간을 제공했다. 이 전환 기간 동안 고객은 픽셀 추적에 대해 사용자에게 알리고 필요한 경우 옵트아웃을 제공할 것으로 예상됩니다. CNIL은 2026년 7월 14일 이후 집행 활동을 시작할 것으로 예상된다.

CNIL 및 기타 규제 기관이 픽셀 추적 및 관련 문제에 대한 지침을 명확히 함에 따라 Adobe은 업데이트를 계속 모니터링하고 Adobe Campaign을 비롯한 이메일 마케팅을 지원하는 Adobe 제품의 기술 기능을 고객에게 알릴 예정입니다.

Adobe Journey Optimizer, Journey Optimizer B2B, Adobe Campaign 및 Marketo Engage을 포함한 Adobe 이메일 마케팅 실행 애플리케이션은 고객이 게재 또는 이메일 수준에서 열린 추적을 관리하는 데 도움이 되는 컨트롤을 제공합니다. 고객은 해당 CNIL 지침 및 기타 법률에 따라 자신의 규정 준수 의무를 결정할 책임이 있지만 이러한 기능은 고객 규정 준수 노력을 지원할 수 있습니다.

## 이메일 추적 픽셀이란 무엇입니까?

이메일 추적 픽셀은 이메일의 HTML에 임베드된 1x1 투명 이미지입니다. 수신자의 이메일 클라이언트가 해당 이미지를 로드할 때 픽셀은 타임스탬프, 디바이스 유형, 이메일 클라이언트 및 경우에 따라 대략적인 위치에 대한 IP 주소와 같은 데이터를 기록하는 서버를 ping합니다. 그러면 해당 로그가 수신자의 레코드에 연결되어 마케터는 이메일이 열렸는지 여부를 확인할 수 있습니다.

## 고객 지원

위에서 설명한 변경 사항을 구현하는 데 도움을 원하는 고객은 기존 Adobe 에코시스템과 연계될 수 있습니다. 참조된 Adobe 기능에 대한 기술적인 질문이 있는 경우 고객 성공 관리자 또는 기술 계정 관리자에게 문의하십시오.

## 이메일 추적과 관련된 Adobe Campaign 기능

고객은 CNIL 지침을 처리하기 위해 아키텍처를 구성할 때 Adobe Campaign의 기본 추적, 스키마 및 개인화 메커니즘을 사용하여 특정 요소를 처리할 수 있습니다.

* **게재 분류.** emailType 특성(인증, 전달만 가능, 트랜잭션, 마케팅, 공개 서비스, B2B 전망)으로 nms:delivery을(를) 확장합니다. 분류는 동의 없이 허용되는 픽셀을 구동합니다.
* **동의 캡처.** 단어 버전, 타임스탬프, 캡처 원본 및 만료가 포함된 목적별 동의 구조로 nms:recipient을(를) 확장합니다. 등록 양식 및 기본 설정 센터를 확장하여 이메일 옵트인과 별도로 픽셀 동의를 수집합니다.
* **픽셀 발광.** 픽셀 목적(인증, 전달성, 성능, 프로파일링, 사기 행위 탐지)당 하나의 NmsTracking_OpenFormula를 정의합니다. 게재 유형화 규칙은 emailType 및 수신자의 용도별 동의를 기반으로 내보낼 수식을 선택합니다. 개인화 블록은 논리를 캡슐화하므로 개별 크리에이티브에서 활성화되지 않습니다.
* **철회.** 구독 취소 링크와 구별되는 모든 이메일 바닥글에 추적기 환경 설정 관리 링크를 추가합니다. 링크는 idTracking을 통해 인증된 nms:webApp 랜딩 페이지를 가리킵니다. 수신자는 이메일 주소를 다시 입력하지 않고 한 번의 클릭으로 동의를 철회합니다. 표준 추적 워크플로우에 추가된 필터 단계는 이전에 게재한 이메일의 다시 열기를 철회 후 악용하지 않도록 합니다.
* **동의 증명.** 문구 변경 후 검색을 위해 별도로 저장된 문구 버전을 사용하여 추가 전용 로그(pix:consentLog 확장 네임스페이스 등)에서 각 동의 이벤트를 캡처합니다. Adobe Campaign 탐색기를 통해 로그를 표시하고 정기적으로 내보냅니다.
* **다시 요청 거버넌스입니다.** lastPixelRebentionDate 필드 및 필터링 유형화 규칙은 거부 후 최소 6개월 동안 다시 요청을 금지합니다. 주기적인 워크플로우는 동의 만료를 관리하는 데 도움이 될 수 있습니다.
* **보고 중.** 기존 Adobe Campaign 보고는 코드를 변경하지 않고 새 필드(urlCategory, emailType, 동의 플래그)에 대해 계속 작동합니다.

Adobe 이메일 마케팅 실행 애플리케이션의 이메일 추적에 대한 자세한 내용은 다음 설명서를 참조하십시오.

| 제품 | 설명서 참조 |
|---|---|
| Campaign v8 | [메시지 추적](https://experienceleague.adobe.com/en/docs/campaign/campaign-v8/analytics/tracking/url-tracking){target="_blank"} |
| Campaign Classic | [메시지 추적 시작](https://experienceleague.adobe.com/en/docs/campaign-classic/using/sending-messages/monitoring-deliveries/about-message-tracking){target="_blank"} |
| Campaign Standard | [전자 메일 채널 구성](https://experienceleague.adobe.com/en/docs/campaign-standard/using/administrating/configuring-channels/configuring-email-channel){target="_blank"} |
| Journey Optimizer | [메시지 추적 설명서](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/channels/email/design-email/add-content/message-tracking){target="_blank"} |
| Marketo Engage | [전자 메일 링크 추적 사용 안 함](https://experienceleague.adobe.com/en/docs/marketo/using/product-docs/email-marketing/general/functions-in-the-editor/disable-tracking-for-an-email-link){target="_blank"} |
| Journey Optimizer | [전자 메일 설정 설명서](https://experienceleague.adobe.com/en/docs/journey-optimizer-b2b/user/journey-content/email-channel/add-email){target="_blank"} |
