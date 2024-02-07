---
lab:
  title: Language Studio를 사용하여 텍스트 분석
---

# Language Studio를 사용하여 텍스트 분석

이 연습에서는 몇 가지 예제 호텔 리뷰를 분석하여 Azure AI Language의 기능을 살펴봅니다. Language Studio를 사용하여 리뷰가 대부분 긍정적인지 부정적인지 이해합니다.

NLP(자연어 처리)는 서면 및 음성 언어를 다루는 AI의 분기입니다. NLP를 사용하여 텍스트 또는 음성에서 의미 체계적 의미를 추출하거나 자연어로 의미 있는 응답을 작성하는 솔루션을 빌드할 수 있습니다.

예를 들어 가상의 여행사인 Margie's Travel이 고객이 호텔 숙박에 대한 리뷰를 제출하도록 권장한다고 가정해 보겠습니다. 언어 서비스를 사용하여 핵심 구를 식별하거나, 어떤 리뷰가 긍정적이고 어떤 리뷰가 부정적인지 확인하거나, 위치 또는 사용자와 같은 알려진 엔터티의 멘션 대한 검토 텍스트를 분석할 수 있습니다.

Azure AI Language Service에는 텍스트 분석 및 NLP 기능이 포함됩니다. 여기에는 텍스트의 핵심 구 식별 및 감정에 따른 텍스트 분류가 포함됩니다.

## *Language* 리소스 만들기

언어 또는 Azure AI 서비스 리소스와 **함께 많은 Azure AI 언어 기능을 사용할 수 있습니다 **.**** 언어 리소스만 사용할 수 있는 일부 인스턴스가 있습니다. 아래 연습에서는 언어** 리소스를 **사용합니다. 아직 만들지 않았다면 Azure 구독에서 **Language** 리소스를 만듭니다.

1. 다른 브라우저 탭에서 Azure Portal을 [https://portal.azure.com](https://portal.azure.com?azure-portal=true)열고 Azure 구독과 연결된 Microsoft 계정으로 로그인합니다.

1. **65291을 클릭합니다. 리소스** 단추를 만들고 언어 서비스를* 검색*합니다. 언어 서비스** 계획 만들기**를 **선택합니다**. 페이지 **로 이동하여 추가 기능을** 선택합니다. 기본 선택을 유지하고 계속을 클릭하여 **리소스**를 만듭니다. 

1. 언어** 만들기 페이지에서 **다음 설정을 사용하여 구성합니다.
    - **구독**: *자신의 Azure 구독*.
    - **리소스 그룹**: *고유한 이름이 있는 리소스 그룹을 선택하거나 생성*합니다.
    - **지역**: 미국 동부.
    - **이름**: 고유한 이름을 입력합니다.
    - **가격 책정 계층**: *무료 F0 또는 무료 F0을 사용할 수 없는 경우 S*
    - **이 상자를 검사 아래의 모든 용어를 읽고 이해했음*을 인정합니다.***

1. 검토 + 만들기**를 선택한 다음 **만들기**를 선택하고 **배포가 완료되기를 기다립니다.

## Azure AI Language Studio에서 리소스 구성

1. 다른 브라우저 탭에서 Language Studio**를 [https://language.cognitive.azure.com](https://language.cognitive.azure.com?azure-portal=true) 열고 **로그인합니다.

1. Azure 리소스**를 선택하라는 **메시지가 표시되면 다음 구성을 수행합니다.
    - **Azure 디렉터리**: *기본 디렉터리, 사용 중인 디렉터리*
    - **Azure 구독**: *사용 중인 구독 선택*
    - **리소스 종류**: 언어
    - **리소스 이름**: *방금 만든 언어 서비스 리소스 선택*

그런 다음 **완료**를 선택합니다.

> **중요**: 2023년 7월부터 Azure AI 서비스는 이전에 Cognitive Services 및 Azure 앱lied AI Services로 알려진 모든 서비스를 포함합니다. 일부 사용자 인터페이스는 여전히 참조 `Cognitive Services` 를 업데이트합니다 `Azure AI services`. 두 이름은 동일한 유형의 리소스를 참조합니다.

> **참고**: 언어 리소스를 선택하라는 ***메시지가 표시되지 않으면*** 구독에 여러 언어 리소스가 있기 때문일 수 있습니다. 이 경우 다음을 수행합니다.
> 1. 페이지의 맨 위에 있는 막대에서 설정(&#9881;)**를 선택합니다**. 
> 1. **설정** 페이지에서 **리소스** 탭을 봅니다.
> 1. 방금 만든 리소스를 선택하고 리소스** 전환을 선택합니다**. 관리 ID가 **사용되도록** 설정되어 있는지 확인합니다.
> ![언어 리소스를 사용하도록 설정합니다.](media/analyze-text-language-service/language-resource-enabled.png)
> 1. 페이지 맨 위에서 Language Studio를 선택하여 **Language Studio** 홈 페이지로 돌아갑니다.

## Language Studio에서 검토 분석

1. 웹 브라우저에서 .에서https://language.cognitive.azure.com[](https://language.cognitive.azure.com?azure-portal=true) Language Studio**로 **이동합니다.

1. **Language Studio** 시작 방문 페이지에서 텍스트** 분류 탭을 **선택한 다음, 감정 분석 및 내 의견 타일을** 선택합니다**.

1. 텍스트 언어 선택에서 *영어를** 선택합니다**.*

1. Azure 리소스* 선택에서 *리소스를 선택합니다.

1. 사용자 고유의 텍스트 입력에서 *파일을 업로드하거나 샘플 텍스트* 중 하나를 사용하여 다음 검토를 복사하여 붙여넣습니다.

    ```
    Tired hotel with poor service
    The Royal Hotel, London, United Kingdom
    5/6/2018
    This is an old hotel (has been around since 1950's) and the room furnishings are average - becoming a bit old now and require changing. The internet didn't work and had to come to one of their office rooms to check in for my flight home. The website says it's close to the British Museum, but it's too far to walk.
    ```

1. 데모에서 사용량이 발생하고 비용이 발생할 수 있음을 확인하는 확인란을 선택한 다음 실행을 선택합니다****.

1. 출력을 검토합니다. *문서는* 각 *문장*뿐만 아니라 감정에 대해 분석됩니다. 문장 1**을 선택하여 **해당 문장에 대한 감정 분석을 표시합니다. 

전체 감정 다음에는 긍정 점수, 중립** 점수, **음수 점수의 세 가지 범주 옆에 점수*가 잇는 것을 알 수 있습니다*. 각 범주에서 0에서 1 사이의 점수가 제공됩니다. 이러한 신뢰도 점수는 제공된 텍스트가 특정 감정일 가능성이 있음을 나타냅니다. 

문장 1**을 다시 선택하여 **닫습니다.

1. 위로 스크롤하여 텍스트 상자** 지우기를 선택하고 **다음 검토를 복사하여 붙여넣습니다.

    ```
    Good Hotel and staff
    The Royal Hotel, London, UK
    3/2/2018
    Clean rooms, good service, great location near Buckingham Palace and Westminster Abbey, and so on. We thoroughly enjoyed our stay. The courtyard is very peaceful and we went to a restaurant which is part of the same group and is Indian ( West coast so plenty of fish) with a Michelin Star. We had the taster menu which was fabulous. The rooms were very well appointed with a kitchen, lounge, bedroom and enormous bathroom. Thoroughly recommended.
    ```
    
    
1. **실행**을 선택합니다. 출력을 검토하고 감정 및 신뢰도 수준을 검토합니다.

1. 텍스트** 상자 지우기를 다시 선택하고 **다음 검토를 복사하여 붙여넣습니다.

    >매우 시끄럽고 객실은 작습니다. 2018년 9월 5일 미국 샌프란시스코 더 롬바드 호텔, 호텔은 금문교 바로 옆에 있는 매우 번화한 6차선 거리인 롬바드 스트리트에 있습니다. 특히 주말에는 이른 아침부터 늦은 밤까지 교통이 혼잡합니다. 방음이 잘 되었다면 객실이 그리 시끄럽지 않았겠지만, 그렇지 않았습니다. 잠을 자기 위해 솜뭉치로 귀를 막아야 했으며, 너무 피곤해 다음날 도시를 제대로 즐기지 못했습니다. 객실은 정말로 작습니다. 퀸사이즈 침대가 두 개 있는 객실을 골랐지만, 객실에는 이를 수용할 공간이 거의 없었습니다. 4인 가족이 머무르기에는 너무 비좁았습니다. 그렇긴 하지만, 객실은 깨끗했고 새로 수리를 했습니다. 호텔은 좋은 식당이 많은 마리나 지역에 있고 프레시디오까지 걸어갈 수 있습니다. 예산이 빠듯하고 늦게까지 자지 않는 젊은이들에게는 좋은 호텔일 수 있습니다.

1. 실행을** 선택하고 **신뢰 수준과 함께 감정을 검토합니다. 텍스트를 살펴보고 서비스가 반환한 감정 분석과 텍스트를 비교합니다.

이 연습에서는 Language Studio를 사용하여 새 언어 리소스를 만들거나 기존 언어 리소스를 사용했습니다. 감정 및 오피니언 마이닝 서비스를 시도하기 전에 설정 리소스를 사용하도록 설정했습니다. 그런 다음 세 개의 텍스트로 서비스를 테스트했습니다.

## 정리

더 많은 연습을 수행하지 않으려면 더 이상 필요하지 않은 리소스를 삭제합니다. 이렇게 하면 불필요한 비용이 발생하지 않습니다.

1. Azure Portal을 **[https://portal.azure.com](https://portal.azure.com) 열고 만든 리소스가 포함된 리소스 그룹을 선택합니다.**
1. 리소스를 선택하고 삭제**를 선택한 다음 **예(예**)를 선택하여 **확인합니다. 그런 다음 리소스가 삭제됩니다.

## 자세한 정보

이 서비스를 사용하여 수행할 수 있는 작업을 자세히 알아보려면 [언어 서비스 페이지](https://learn.microsoft.com/azure/ai-services/language-service/overview)를 참조하세요.
