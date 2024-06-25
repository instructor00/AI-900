---
lab:
  title: Language Studio로 텍스트 분석
---

# Language Studio로 텍스트 분석

이 연습에서는 몇 가지 호텔 검토 예를 분석하여 Azure AI 언어의 기능을 살펴봅니다. 검토가 대부분 긍정적인지 부정적인지 이해하기 위해 Language Studio를 사용하게 됩니다.

NLP(자연어 처리)는 문어와 구어를 처리하는 AI의 한 분야입니다. NLP를 사용하여 텍스트나 음성에서 의미를 추출하거나 의미 있는 답변을 자연어로 조합하는 솔루션을 구축할 수 있습니다.

예를 들어, 가상의 여행사 Margie's Travel이 고객에게 호텔 숙박에 대한 검토를 제출하도록 권장한다고 가정해 보겠습니다. 언어 서비스를 사용하여 핵심 구를 식별하고, 어떤 검토가 긍정적이고 어떤 검토가 부정적인지 확인하거나, 위치나 사람과 같은 알려진 엔터티에 대한 언급에 대한 검토 텍스트를 분석할 수 있습니다.

Azure AI 언어 서비스에는 텍스트 분석 및 NLP 기능이 포함되어 있습니다. 여기에는 텍스트의 핵심 구 식별, 감정에 따른 텍스트 분류가 포함됩니다.

## *Language* 리소스 만들기

**언어** 또는 **Azure AI 서비스** 리소스를 통해 다양한 Azure AI 언어 기능을 사용할 수 있습니다. 언어 리소스만 사용할 수 있는 경우가 있습니다. 아래 연습에서는 **언어** 리소스를 사용합니다. 아직 만들지 않았다면 Azure 구독에서 **Language** 리소스를 만듭니다.

1. 다른 브라우저 탭에서 [https://portal.azure.com](https://portal.azure.com?azure-portal=true)의 Azure Portal을 열고 Azure 구독과 연결된 Microsoft 계정으로 로그인합니다.

1. **&#65291;리소스 만들기** 단추를 클릭하고 *언어 서비스*를 검색합니다. **언어 서비스** 계획 **만들기**를 선택합니다. **추가 기능을 선택**할 수 있는 페이지로 이동됩니다. 기본 선택을 유지하고 **계속하여 리소스 만들기**를 클릭합니다. 

1. **언어 만들기** 페이지에서 다음 설정으로 구성합니다.
    - **구독**: *자신의 Azure 구독*.
    - **리소스 그룹**: *고유한 이름이 있는 리소스 그룹을 선택하거나 생성*합니다.
    - **지역**: *지리적으로 가장 가까운 지역을 선택합니다. 미국 동부에 있는 경우 "미국 동부 2"* 를 사용합니다.
    - **이름**: 고유한 이름을 입력합니다.
    - **가격 책정 계층**: *무료 F0을 사용할 수 없는 경우 무료 F0 또는 S*
    - **이 상자를 선택함으로써 나는 아래의 모든 용어를 읽고 이해했음을 인정합니다.** *선택됨*.

1. **검토 + 만들기**를 선택한 다음 **만들기**를 선택하고 배포가 완료될 때까지 기다립니다.

## Azure AI 언어 스튜디오에서 리소스 구성

1. 다른 브라우저 탭에서 [https://language.cognitive.azure.com](https://language.cognitive.azure.com?azure-portal=true)의 **Language Studio**를 열고 로그인합니다.

1. **Azure 리소스 선택** 메시지가 표시되면 다음과 같이 구성합니다.
    - **Azure 디렉터리**: *기본 디렉터리, 사용 중인 디렉터리*
    - **Azure 구독**: *사용 중인 구독 선택*
    - **리소스 종류**: 언어
    - **리소스 이름**: *방금 만든 언어 서비스 리소스 선택*

그런 다음 **완료**를 선택합니다.

> **중요**: 2023년 7월부터 Azure AI 서비스는 이전에 Cognitive Services 및 Azure Applied AI Services로 알려진 모든 것을 포함합니다. 일부 사용자 인터페이스는 아직 참조를 `Cognitive Services`에서 `Azure AI services`로 업데이트하고 있습니다. 두 이름은 동일한 형식의 리소스를 나타냅니다.

> **참고**: 언어 리소스를 선택하라는 메시지가 표시되지 ***않으면*** 구독에 여러 언어 리소스가 있기 때문일 수 있습니다. 이 경우 다음을 수행합니다.
> 1. 페이지 상단 표시줄에서 **설정(&#9881;)** 을 선택합니다. 
> 1. **설정** 페이지에서 **리소스** 탭을 봅니다.
> 1. 방금 만든 리소스를 선택하고 **리소스 전환**을 선택합니다. 관리 ID가 **사용**인지 확인합니다.
> ![언어 리소스를 사용하도록 설정합니다.](media/analyze-text-language-service/language-resource-enabled.png)
> 1. 페이지 상단에서 **Language Studio**를 선택하여 Language Studio 홈페이지로 돌아갑니다.

## Language Studio에서 검토 분석

1. 웹브라우저에서 [https://language.cognitive.azure.com](https://language.cognitive.azure.com?azure-portal=true)의 **Language Studio**로 이동합니다.

1. **Language Studio 시작** 방문 페이지에서 **텍스트 분류** 탭을 선택한 다음 **감정 및 마이닝 오피니언 분석** 타일을 선택합니다.

1. *텍스트 언어 선택*에서 **영어**를 선택합니다.

1. *Azure 리소스 선택*에서 리소스를 선택합니다.

1. *텍스트 입력, 파일 업로드 또는 샘플 텍스트 중 하나 사용* 아래에 다음 검토를 복사하여 붙여넣습니다.

    ```
    Tired hotel with poor service
    The Royal Hotel, London, United Kingdom
    5/6/2018
    This is an old hotel (has been around since 1950's) and the room furnishings are average - becoming a bit old now and require changing. The internet didn't work and had to come to one of their office rooms to check in for my flight home. The website says it's close to the British Museum, but it's too far to walk.
    ```

1. 데모를 사용하면 비용이 발생할 수 있음을 확인하는 확인란을 선택한 다음 **실행**을 선택합니다.

1. 출력을 검토합니다. *문서*의 감정은 물론 각 *문장*도 분석됩니다. 해당 문장에 대한 감정 분석을 보려면 **문장 1**을 선택합니다. 

전반적인 감정에 이어 *긍정 점수*, *중립 점수*, *부정 점수*의 세 가지 범주 옆에 점수가 표시됩니다. 각 범주에서 0에서 1 사이의 점수가 제공됩니다. 이러한 신뢰도 점수는 제공된 텍스트가 특정 감정일 가능성을 나타냅니다. 

닫으려면 다시 **문장 1**을 선택합니다.

1. 위로 스크롤하여 **텍스트 상자 지우기**를 선택하고 다음 검토를 복사하여 붙여넣습니다.

    ```
    Good Hotel and staff
    The Royal Hotel, London, UK
    3/2/2018
    Clean rooms, good service, great location near Buckingham Palace and Westminster Abbey, and so on. We thoroughly enjoyed our stay. The courtyard is very peaceful and we went to a restaurant which is part of the same group and is Indian ( West coast so plenty of fish) with a Michelin Star. We had the taster menu which was fabulous. The rooms were very well appointed with a kitchen, lounge, bedroom and enormous bathroom. Thoroughly recommended.
    ```
    
    
1. **실행**을 선택합니다. 출력을 검토하고 감정과 신뢰 수준을 검토합니다.

1. **텍스트 지우기** 상자를 다시 선택하고 다음 검토를 복사하여 붙여넣습니다.

    >매우 시끄럽고 객실은 작습니다. 2018년 9월 5일 미국 샌프란시스코 더 롬바드 호텔, 호텔은 금문교 바로 옆에 있는 매우 번화한 6차선 거리인 롬바드 스트리트에 있습니다. 특히 주말에는 이른 아침부터 늦은 밤까지 교통이 혼잡합니다. 방음이 잘 되었다면 객실이 그리 시끄럽지 않았겠지만, 그렇지 않았습니다. 잠을 자기 위해 솜뭉치로 귀를 막아야 했으며, 너무 피곤해 다음날 도시를 제대로 즐기지 못했습니다. 객실은 정말로 작습니다. 퀸사이즈 침대가 두 개 있는 객실을 골랐지만, 객실에는 이를 수용할 공간이 거의 없었습니다. 4인 가족이 머무르기에는 너무 비좁았습니다. 그렇긴 하지만, 객실은 깨끗했고 새로 수리를 했습니다. 호텔은 좋은 식당이 많은 마리나 지역에 있고 프레시디오까지 걸어갈 수 있습니다. 예산이 빠듯하고 늦게까지 자지 않는 젊은이들에게는 좋은 호텔일 수 있습니다.

1. **실행**을 선택하고 신뢰 수준과 함께 감정을 검토합니다. 텍스트를 살펴보고 서비스가 반환한 감정 분석과 텍스트를 비교합니다.

이 연습에서는 Language Studio를 사용하여 새 언어 리소스를 만들거나 기존 언어 리소스를 사용했습니다. 감정 및 오피니언 마이닝 서비스를 사용해 보기 전에 설정에서 리소스를 사용하도록 설정했습니다. 그런 다음 세 가지 텍스트로 서비스를 테스트했습니다.

## 정리

더 이상 연습할 생각이 없다면 더 이상 필요하지 않은 리소스를 삭제합니다. 이렇게 하면 불필요한 비용이 발생하는 것을 방지할 수 있습니다.

1. [https://portal.azure.com](https://portal.azure.com)에서 **Azure Portal**을 열고 만든 리소스가 포함된 리소스 그룹을 선택합니다.
1. 리소스를 선택하고 **삭제**를 선택한 다음 **예**를 선택하여 확인합니다. 그러면 리소스가 삭제됩니다.

## 자세한 정보

이 서비스를 사용하여 수행할 수 있는 작업을 자세히 알아보려면 [언어 서비스 페이지](https://learn.microsoft.com/azure/ai-services/language-service/overview)를 참조하세요.
