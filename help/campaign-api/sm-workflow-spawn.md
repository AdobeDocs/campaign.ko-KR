---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '120'
ht-degree: 3%
---
# 종균

템플릿에서 워크플로 인스턴스를 만들고 패치를 적용한 다음 이 워크플로를 시작합니다.

```text
Number instanceId = Spawn ( String workflowId, XML patch )
```

## 매개변수

**workflowId** 워크플로 템플릿의 식별자 또는 내부 이름입니다.

**patch** 실행하기 전에 인스턴스를 가져오기 위해 모델과 병합해야 하는 XML 요소입니다. 예:

```xml
    <workflow>
      <activities>
        <extern name="notepad">
          <additionnalArgs><![CDATA[c:\xxx.txt]]>
          </additionnalArgs>
        </extern>
      </activities>
    </workflow>
    
```

이 예제는 &#39;메모장&#39; 활동의 인수를 대체합니다. 이 패치를 적용하지 않으려면 빈 &lt;workflow/> 요소 또는 빈 문자열을 사용합니다.

## 반환 값

템플릿에서 만든 인스턴스의 **instanceId** 식별자입니다.

## 비고

명령은 비동기 모드에서 실행되고 메서드 반환 후 즉각적인 영향을 주지 않습니다. 호출 연산자의 계정으로 워크플로우가 시작됩니다.

## 기능

**스키마:** [xtk:workflow](s-xtk-workflow.md)

**정적:**

예
