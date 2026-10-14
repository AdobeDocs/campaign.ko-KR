---
title: 이메일 추적 픽셀 관련 지침
description: 규정 준수 활동을 지원할 수 있는 이메일 추적 픽셀 및 Adobe Campaign 기능과 관련된 규정 지침을 이해합니다.
version: Campaign v8, Campaign Classic v7
hide: true
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: d0e9f0b2-1f2b-4134-9844-49cd4e950f27
    internal-label: Campaign v8
source-git-commit: 93335b46b1c706a9409f0816b2ced4ebc612d5fe
workflow-type: tm+mt
source-wordcount: '834'
ht-degree: 0%
---

# 이메일 추적 픽셀 관련 지침

이 게시물은 정보 제공용으로만 제공됩니다. 이는 법률적인 조언이 아니며, 해당 법률의 준수를 보증하지 않습니다. 아래에 설명된 Adobe Campaign 제품 기능은 적절하게 구성되고 작동되어 규정 준수 구현을 지원할 수 있는 기본 구성단위입니다. 각 고객은 해당 법률에 따라 의무를 결정하고 준수할 책임이 있습니다.

## 개요

2026년 4월 14일, 프랑스의 데이터 보호 당국인 _Commission national de l&#39;informatique et des libertés_(CNIL)에서 [이메일 내의 픽셀 추적 사용에 대한 권장 사항](https://www.cnil.fr/sites/default/files/2026-04/recommandation-pixels_de_suivi.pdf)을 게시했습니다. 얼마 지나지 않아 이탈리아의 독립 데이터 보호 기관(&quot;Garante&quot;)은 규정 No를 공표하였다. 284(2026년 4월 17일 &quot;가란테 조항&quot;). 두 지침 문서 모두 법적 구속력이 없지만 동의가 필요한 시기를 명확히 하고 이메일 픽셀 추적에 대한 적절한 동의 방식의 중요성을 강조합니다. 이 정책은 적용 가능한 EU 개인 정보 보호법에 따라 가입자에게 이메일을 전달하는 엔티티의 전송 사례에 영향을 줄 수 있습니다.

규제 당국이 픽셀 추적 및 관련 문제에 대한 지침을 계속 명확히 함에 따라 Adobe은 변경 사항을 계속 모니터링하고 Adobe Campaign을 비롯한 이메일 마케팅을 지원하는 Adobe 제품의 기술 기능을 고객에게 알릴 예정입니다. 이메일 추적 픽셀에 대한 Adobe의 설명서는 현재 규제 지침을 반영합니다. Adobe은 규정 요구 사항이 발전함에 따라 Adobe CXO 제품 사용에 영향을 미칠 수 있는 관련 변경 사항을 반영하기 위해 필요에 따라 설명서를 계속 업데이트할 예정입니다. 자료 업데이트 지연은 Adobe 대신 실패를 구성하지 않습니다.

Adobe Journey Optimizer, Journey Optimizer B2B, Adobe Campaign 및 Marketo Engage을 포함한 Adobe 이메일 마케팅 실행 애플리케이션은 고객이 게재 또는 이메일 수준에서 열린 추적을 관리하는 데 도움이 되는 컨트롤을 제공합니다. 고객은 해당 지침 및 기타 법률에 따라 자신의 규정 준수 의무를 결정할 책임이 있지만 이러한 기능은 고객 규정 준수 노력을 지원할 수 있습니다.

## 이메일 추적 픽셀이란 무엇입니까?

이메일 추적 픽셀은 이메일의 HTML에 임베드된 1x1 투명 이미지입니다. 수신자의 이메일 클라이언트가 해당 이미지를 로드할 때 픽셀은 타임스탬프, 디바이스 유형, 이메일 클라이언트 및 경우에 따라 대략적인 위치에 대한 IP 주소와 같은 데이터를 기록하는 서버를 ping합니다. 그러면 해당 로그가 수신자의 레코드에 연결되어 마케터는 이메일이 열렸는지 여부를 확인할 수 있습니다.

## 고객 지원

위에서 설명한 변경 사항을 구현하는 데 도움을 원하는 고객은 기존 Adobe 에코시스템과 연계될 수 있습니다. 참조된 Adobe 기능에 대한 기술적인 질문이 있는 경우 고객 성공 관리자 또는 기술 계정 관리자에게 문의하십시오.

## 이메일 추적과 관련된 Adobe Campaign 기능

고객은 이메일 추적 픽셀 관련 지침을 처리하기 위해 아키텍처를 구성할 때 Adobe Campaign의 기본 추적, 스키마 및 개인화 메커니즘을 사용하여 특정 요소를 처리할 수 있습니다.

* **게재 분류.** `nms:delivery`을(를) `emailType` 특성(인증, 전달만 가능, 트랜잭션, 마케팅, 공개 서비스, B2B 전망)으로 확장합니다. 분류는 동의 없이 허용되는 픽셀을 구동합니다.

* **동의 캡처.** 언어 버전, 타임스탬프, 캡처 원본 및 만료 정보를 포함하는 목적별 동의 구조로 `nms:recipient`을(를) 확장합니다. 등록 양식 및 기본 설정 센터를 확장하여 이메일 옵트인과 별도로 픽셀 동의를 수집합니다.

* **픽셀 발광.** 픽셀 목적(인증, 전달성, 성능, 프로파일링, 사기 행위 탐지)당 하나의 `NmsTracking_OpenFormula`을(를) 정의합니다. 게재 유형화 규칙은 emailType 및 수신자의 용도별 동의를 기반으로 내보낼 수식을 선택합니다. 개인화 블록은 논리를 캡슐화하므로 개별 크리에이티브에서 활성화되지 않습니다.

* **철회.** 구독 취소 링크와 별도로 모든 이메일 바닥글에 **추적기 환경 설정 관리** 링크를 추가합니다. 링크는 `idTracking`을(를) 통해 인증된 `nms:webApp` 랜딩 페이지를 가리킵니다. 수신자는 이메일 주소를 다시 입력하지 않고 한 번의 클릭으로 동의를 철회합니다. 표준 **추적** 워크플로에 추가된 필터 단계는 이전에 배달된 전자 메일의 다시 열기를 철회 후 사용하지 못하도록 합니다.

* **동의 증명.** 추가 전용 로그(예: `pix:consentLog` 확장 네임스페이스)에서 각 동의 이벤트를 캡처합니다. 이때 단어 변경 후 검색을 위해 단어 버전은 별도로 저장됩니다. Adobe Campaign 탐색기를 통해 로그를 표시하고 정기적으로 내보냅니다.
* **다시 요청 거버넌스입니다.** `lastPixelRefusalDate` 필드 및 필터링 유형화 규칙은 거부 후 최소 6개월 동안 다시 요청을 금지합니다. 주기적인 워크플로우는 동의 만료를 관리하는 데 도움이 될 수 있습니다.

* **보고 중.** 기존 Adobe Campaign 보고는 코드를 변경하지 않고 새 필드(urlCategory, emailType, 동의 플래그)에 대해 계속 작동합니다.

Adobe 이메일 마케팅 실행 애플리케이션의 이메일 추적에 대한 자세한 내용은 다음 설명서를 참조하십시오.

| 제품 | 설명서 참조 |
|---|---|
| Campaign v8 | [메시지 추적](https://experienceleague.adobe.com/en/docs/campaign/campaign-v8/analytics/tracking/url-tracking){target="_blank"} |
| Campaign Classic | [메시지 추적 시작](https://experienceleague.adobe.com/en/docs/campaign-classic/using/sending-messages/monitoring-deliveries/about-message-tracking){target="_blank"} |
| Journey Optimizer | [메시지 추적 설명서](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/channels/email/design-email/add-content/message-tracking){target="_blank"} |
| Marketo Engage | [전자 메일 링크 추적 사용 안 함](https://experienceleague.adobe.com/en/docs/marketo/using/product-docs/email-marketing/general/functions-in-the-editor/disable-tracking-for-an-email-link){target="_blank"} |
| Journey Optimizer | [전자 메일 설정 설명서](https://experienceleague.adobe.com/en/docs/journey-optimizer-b2b/user/journey-content/email-channel/add-email){target="_blank"} |


