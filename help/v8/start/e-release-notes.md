---
title: 초기 Campaign v8 릴리스 정보
description: 초기 Campaign v8 릴리스
feature: Release Notes
role: Admin, Developer, User
level: Beginner, Intermediate, Experienced
hide: true
hidefromtoc: true
exl-id: a45f7b22-44c7-4dad-af0a-ae8f683ae3d9
source-git-commit: e0ec2940db3120dc8fbfd17dd2f5083bbf31232c
workflow-type: tm+mt
source-wordcount: '586'
ht-degree: 33%

---

# 초기 릴리스 정보 {#e-new-release}

이 페이지에서는 다음 Campaign v8 릴리스에 포함된 개선 사항 및 문제 해결에 대해 설명합니다. 이 내용은 릴리스 일자까지 사전 예고 없이 변경될 수 있습니다. 공식 릴리스 정보는 이 [페이지](../start/release-notes.md)에서 확인할 수 있습니다.

## 릴리스 8.5.1 {#release-8-5}

_2023년 6월 30일_

**새로운 기능**

<table> 
<thead>
<tr> 
<th> <strong>향상된 푸시 알림 서비스</strong><br /> </th> 
</tr> 
</thead> 
<tbody> 
<tr> 
<td><p>Campaign 8.5.1은 최신 첨단 기술을 기반으로 구축된 강력한 프레임워크를 기반으로 하는 v8의 최신 푸시 알림 서비스를 도입했습니다. 이 서비스는 새로운 차원의 확장성을 제공하도록 설계되었으므로, 원활한 효율성으로 더 많은 대상자에게 알림이 전달될 수 있습니다. 향상된 인프라와 최적화된 프로세스를 통해 더 높은 규모와 신뢰성을 기대할 수 있으며, 이전과 달리 모바일 앱 사용자를 참여시키고 연결할 수 있는 역량을 확보할 수 있습니다. 이 기능은 선택한 고객 그룹만 사용할 수 있습니다(제한된 가용성).</p>
</td> 
</tr> 
</tbody> 
</table>

**호환성 업데이트**

* 이제 클라이언트 콘솔의 32비트 버전은 더 이상 사용되지 않습니다. 8.6 릴리스부터 클라이언트 콘솔은 64비트로만 사용할 수 있습니다. 클라이언트 콘솔의 64비트 버전으로 원활하게 업그레이드됩니다. 운영 체제를 업그레이드하는 자세한 방법은 [기술 정보](https://experienceleague.adobe.com/docs/campaign/technotes-ac/tn-new/console.html?lang=ko)를 참조하십시오.
* 이제 Campaign v8 인스턴스를 Azure synapse 외부 데이터베이스에 연결할 수 있습니다. 이 연결은 새 외부 계정을 통해 관리됩니다.

**개선 사항**

* SMS 처리량은 다양한 최적화를 구현하여 크게 향상되었으므로 SMS 커뮤니케이션의 속도와 효율성이 향상되었습니다.
* Campaign v8.5.1부터 Campaign v8에 대한 인증 프로세스가 개선되었습니다. 기술 운영자는 IMS(Adobe Identity Management System)를 사용하여 Campaign에 연결해야 합니다.
* 이제 대상 및 소스 연결을 활용하여 Adobe Experience Platform과 Campaign v8 데이터베이스 간에 옵트아웃 데이터와 같은 프로필 속성을 동기화할 수 있습니다
* 게재 준비가 최적화되었습니다.
* 기존 사용자/암호 인증 방식과 함께 SFTP 외부 계정에 대해 새로운 키 기반 인증 옵션이 추가되었습니다. 이제 사용자는 개인 키를 사용하여 안전하게 인증할 수 있으므로 보안을 강화하고 SFTP 액세스에 대한 대체 인증 메커니즘을 제공합니다.

**향상된 보안 기능**

* 더 이상 클라이언트 콘솔에서 연산자를 만들 수 없습니다. 이제 Admin Console을 사용해야 합니다. [자세히 알아보기](../start/gs-permissions.md)
* 보안을 최적화하기 위해 여러 타사 도구가 업데이트되었습니다.

**패치**

* 게재 HTML 콘텐츠의 특수 문자가 여러 브라우저에서 잘못 인코딩될 수 있는 문제를 해결했습니다. (NEO-60081)
* Campaign v8 엔터프라이즈(FFDA) 배포에 보고서를 저장할 수 없는 문제를 해결했습니다. (NEO-56836)
* 데이터 업데이트 워크플로우 활동을 통해 사용자 지정 FFDA 스키마에 데이터를 삽입하거나 업데이트할 때 발생하는 문제를 수정했습니다. (NEO-54708)
* 데이터베이스 정리 워크플로우가 FFDA의 nms:address 테이블에서 주소를 제거할 수 없는 문제를 해결했습니다. (NEO-54460)
* &quot;컴파일 메모리 소진&quot; 오류로 인해 실패할 수 있는 과금 워크플로우 문제를 해결했습니다. (NEO-51137)
* 데이터 로드(파일) 워크플로우 활동에서 GPG 암호 해독이 제대로 작동하지 않는 문제를 해결했습니다. (NEO-50257)
* `JSPContext.sqlExecWithOneParam` 함수가 작동하지 않는 문제를 해결했습니다. (NEO-50066)
* 개인화 필드에서 인쇄할 수 없는 문자를 사용할 때 게재 실패로 이어지는 문제를 해결했습니다. (NEO-48588)
* Adobe Target 동적 이미지를 삽입할 때 게재 오류가 발생할 수 있는 문제를 해결했습니다. (NEO-62689)
* 게재에서 조건부 콘텐츠를 사용할 때 브라우저에서 공백을 추가하지 못하는 문제를 해결했습니다. (NEO-62132)
* 이메일 콘텐츠 편집기에서 이미지를 클릭할 때 팝업 창이 열리는 문제를 해결했습니다. (NEO-60752)
* 게재 콘텐츠를 편집할 때 오류를 일으키고 스크롤하지 못하는 문제를 해결했습니다. (NEO-61364)
