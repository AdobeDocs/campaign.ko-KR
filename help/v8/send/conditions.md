---
title: 조건부 콘텐츠
description: 조건부 콘텐츠를 만드는 방법 알아보기
feature: Personalization
role: User
level: Beginner
exl-id: bcbf3101-d43c-4ed3-ab02-a9936ec55b71
source-git-commit: c248dd899ea704e43873652545c6b945c2915b57
workflow-type: tm+mt
source-wordcount: '428'
ht-degree: 10%

---

# 조건부 콘텐츠 만들기{#conditional-content}

조건부 콘텐츠 필드를 구성하여 고급 개인화를 만들 수 있습니다. 특정 조건이 충족되면 전체 텍스트 블록 및/또는 이미지가 교체됩니다.


## 이메일에서 조건 사용 {#conditions-in-an-email}

아래 예에서는 수신자의 도시와 관심사에 따라 동적으로 개인화된 메시지를 만드는 방법을 알아봅니다.

* 받는 사람의 도시에 따라 메시지를 변경합니다.
* 수신자의 관심사에 따라 오퍼의 콘텐츠를 개인화합니다.

필드의 값에 따라 조건부 콘텐츠를 만들려면 다음 단계를 적용합니다.

1. 기존 게재를 열거나 새 이메일 게재를 만듭니다.
1. 전자 메일 콘텐츠 편집기에서 개인화 아이콘을 클릭하고 **[!UICONTROL Conditional content > If]**&#x200B;을(를) 선택합니다.

   ![조건 삽입](assets/condition-insert.png)

   개인화 요소는 메시지 본문에 삽입됩니다. 이제 구성해야 합니다.

1. **if** 식의 매개 변수를 입력합니다.

   * 식의 첫 번째 요소인 **`<FIELD>`**&#x200B;을(를) 선택하고 개인화 아이콘을 클릭하여 테스트 필드로 바꿉니다.
   * **`<VALUE>`**&#x200B;을(를) 조건이 충족되는 필드의 값으로 바꿉니다. 이 값은 따옴표로 묶어야 합니다.
   * 조건이 충족될 때 삽입할 콘텐츠를 지정합니다. 텍스트, 이미지, 양식, 하이퍼텍스트 링크 등이 될 수 있습니다.

   전자 메일의 ![상태](assets/condition-in-email.png)

1. **[!UICONTROL Preview]** 탭을 클릭하여 게재 수신자에 따라 메시지의 내용을 확인합니다. 조건이 true인 수신자를 선택하여 콘텐츠를 확인합니다. 그런 다음 false인 다른 수신자를 선택하고 다시 확인하십시오.

다른 대소문자를 추가하고 하나 이상의 필드 값에 따라 다른 콘텐츠를 정의할 수 있습니다. 이렇게 하려면 **[!UICONTROL Conditional content > Else]** 및 **[!UICONTROL Conditional content > Else if]**&#x200B;을(를) 사용합니다. 이러한 식은 **if** 식과 동일한 방식으로 구성됩니다.

>[!CAUTION]
>
>**Else** 및 **Else if** 조건을 추가한 후 **%> &lt;%**&#x200B;자를 삭제해야 합니다.


## 사용 사례: 다국어 이메일 만들기 {#creating-multilingual-email}

아래 예에서는 다국어 이메일을 만드는 방법을 알아봅니다. 콘텐츠는 수신자의 선호 언어에 따라 하나의 언어 또는 다른 언어로 표시됩니다.

1. 이메일을 만들고 대상 모집단을 선택합니다. 이 예제에서 한 버전 또는 다른 버전을 표시하는 조건은 받는 사람 프로필의 **Language** 값을 기반으로 합니다. 이 값은 **EN**, **FR**, **ES**(으)로 설정됩니다.
1. 전자 메일 HTML 콘텐츠에서 **[!UICONTROL Source]** 탭을 클릭하고 다음 코드를 붙여넣습니다.

   ```
   <% if (language == "EN" ) { %>
   <DIV id=en-version>Hello <%= recipient.firstName %>,</DIV>
   <DIV>Discover your new offers!</DIV>
   <DIV><a href="https://www.adobe.com/products/en">www.adobe.com/products/en</A></FONT></DIV><%
    } %>
   <% if (language == "FR" ) { %>
   <DIV id=fr-version>Bonjour <%= recipient.firstName %>,</DIV>
   <DIV>Découvrez nos nouvelles offres !</DIV>
   <DIV><a href="https://www.adobe.com/products/fr">www.adobe.com/products/fr</A></DIV><%
    } %>
    <% if (language == "ES" ) { %>
   <DIV id=es-version><FONT face=Arial>
   <DIV>Olà <%= recipient.firstName %>,</DIV>
   <DIV>Descubra nuestros nuevas ofertas !</DIV>
   <DIV><a href="https://www.adobe.com/products/es">www.adobe.com/products/es</A></DIV>
   <% } %>
   ```

1. 기본 언어가 다른 수신자를 선택하여 **[!UICONTROL Preview]** 탭에서 전자 메일 콘텐츠를 테스트합니다.

   >[!NOTE]
   >
   >이메일 콘텐츠에 대체 버전이 정의되지 않았으므로 이메일을 보내기 전에 대상 모집단을 필터링해야 합니다.

## 튜토리얼 비디오 {#conditionnal-content-video}

다중 언어 뉴스레터의 예에 따라 게재에 조건부 콘텐츠를 추가하는 방법을 알아봅니다.

>[!VIDEO](https://video.tv.adobe.com/v/335682?quality=12)
