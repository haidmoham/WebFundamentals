---
title: "비대칭 애니메이션 타이밍"
description: "대칭을 파괴하면 프로젝트의 대비가 뚜렷하고 매력적입니다. 이를 프로젝트에 언제 어떻게 적용하는지 배웁니다."
updated_on: 2014-10-21
key-takeaways:
  code:
    - "비대칭 애니메이션 타이밍을 사용하여 작업에 개성과 대비를 추가합니다."
    - "항상 사용자 상호작용을 고려합니다. 누르기나 클릭에 반응할 때 더 짧은 기간을 사용하고, 비활성 상태인 동안에는 더 느린 기간을 유지합니다."
---
<p class="intro">
  애니메이션 기간의 비대칭은 개성을 표현하면서 동시에 사용자 상호작용에 빠르게 응답하여 사용자에게 만족감을 줍니다. 또한 대비감을 제공하여 인터페이스를 시각적으로 더욱 매력적으로 보이게 만듭니다.
</p>

{% include shared/takeaway.liquid list=page.key-takeaways.code %}

대부분의 애니메이션 "규칙"과 마찬가지로, 애플리케이션에서 어떻게 작동하는지 알아보는 과정이 필요하지만, 사용자 경험 측면에서 보면 사용자는 참을성이 없습니다. 일반적으로 **사용자 상호작용에 항상 빠르게 응답**하는 것이 좋습니다. 그러나, 대부분의 사용자 동작은 비대칭이므로 애니메이션도 비대칭이 될 수 있습니다.

예를 들어, 사용자가 사이드바 탐색을 누른 경우 100ms 정도로 가능한 한 빨리 화면에 표시해야 합니다. 하지만 사용자가 메뉴를 해제하는 경우 300ms 정도로 약간 더 느리게 설정하여 애니메이션을 보기에 적용해야 합니다.

반대로, 모달 보기를 가져올 때는 이렇게 하면 오류 또는 기타 중대 오류 메시지가 표시됩니다. 이 경우에 개발자는 보기를 300ms 정도로 악간 더 느리게 가져오고 사용자가 트리거하는 해제는 매우 빠르게 발생하도록 하고 싶을 것입니다.

이 경우 일반적인 규칙은 다음과 같습니다.

* 보기 전환 또는 요소 표시 등 사용자의 상호작용으로 트리거되는 UI 애니메이션의 경우, 빠른 표시(짧은 기간)와 느린 숨기기(긴 기간)를 설정합니다.
* 오류 또는 모달 보기 등 코드로 트리거되는 UI 애니메이션의 경우, 느린 표시(긴 기간)와 빠른 숨기기(짧은 기간)를 설정합니다.

