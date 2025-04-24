# Azure AI 파운드리 포털에서 텍스트 분석

NLP(자연어 처리)는 문어와 구어를 처리하는 AI의 한 분야입니다. NLP를 사용하여 텍스트나 음성에서 의미를 추출하거나 의미 있는 답변을 자연어로 조합하는 솔루션을 구축할 수 있습니다.

Azure AI 언어 서비스에는 엔터티 인식, 핵심 구 추출, 요약 및 감정 분석과 같은 기능을 갖춘 텍스트 분석이 포함되어 있습니다. 예를 들어, 가상의 여행사 Margie's Travel이 고객에게 호텔 숙박에 대한 검토를 제출하도록 권장한다고 가정해 보겠습니다. 언어 서비스를 사용하여 명명된 엔터티를 추출하고, 핵심 구를 식별하고, 텍스트를 요약하는 등의 작업을 할 수 있습니다.

이 연습에서는 지능형 애플리케이션을 만들기 위한 Microsoft 플랫폼인 Azure AI 파운드리 포털의 Azure AI 언어를 사용하여 호텔 리뷰를 분석합니다. 

## Azure AI 파운드리 포털에서 프로젝트 만들기

1. 브라우저 탭에서 [Azure AI 파운드리](https://ai.azure.com?azure-portal=true)로 이동합니다.

1. 사용자 계정으로 로그인합니다. 

1. Azure AI 파운드리 포털 홈페이지에서 **프로젝트 만들기**를 선택합니다. Azure AI 파운드리에서 프로젝트는 작업을 구성하는 데 도움이 되는 컨테이너입니다.  

    ![프로젝트 만들기가 선택된 Azure AI 파운드리 홈페이지의 스크린샷.](./media/azure-ai-foundry-home-page.png)

1. *프로젝트 만들기* 창에 생성된 프로젝트 이름이 표시되며, 이 이름은 그대로 사용할 수 있습니다. 이전에 허브를 만들었는지 여부에 따라 만들려는 *새로운* Azure 리소스 목록 또는 기존 허브의 드롭다운 목록이 표시됩니다. 기존 허브의 드롭다운 목록이 표시되면 *새 허브 만들기*를 선택하고 허브의 고유 이름을 만든 다음 *다음*을 선택합니다.  
 
    ![허브 및 프로젝트의 이름이 자동으로 생성된 프로젝트 만들기 창의 스크린샷.](./media/azure-ai-foundry-create-project.png)

> **중요**: 나머지 랩을 완료하려면 특정 위치에 프로비저닝된 Azure AI 서비스 리소스가 있어야 합니다.

1. 같은 *프로젝트 만들기* 창에서 **사용자 지정**을 선택하고 다음 **위치**(미국 동부, 프랑스 중부, 한국 중부, 서유럽 또는 미국 서부) 중 하나를 선택하여 나머지 랩을 완료합니다. 그런 다음 **만들기**를 선택합니다. 

1. 생성된 리소스를 기록해 둡니다. 
- Azure AI 서비스
- Azure AI 허브
- Azure AI 프로젝트
- 스토리지 계정
- Key vault
- Resource group  
 
1. 리소스를 만든 후에는 프로젝트의 *개요* 페이지로 이동합니다. 화면 왼쪽 메뉴에서 **플레이그라운드**를 선택합니다.
 
    ![플레이그라운드가 선택된 프로젝트 화면의 왼쪽 메뉴 스크린샷.](./media/azure-ai-foundry-playgrounds.png)  

1. *플레이그라운드* 페이지에서 **언어 플레이그라운드** 타일을 선택하여 몇 가지 Azure AI 언어 기능을 사용해 봅니다.

## Azure AI 파운드리 포털에서 Azure AI 언어를 사용하여 명명된 엔터티 추출

*명명된 엔터티*는 사람, 장소 및 사물을 고유한 이름으로 설명하는 단어입니다. Azure AI 언어의 명명된 엔터티 추출 기능을 사용하여 리뷰에서 정보 유형을 식별해 보겠습니다.

1. 언어 플레이그라운드에서 **정보 추출**을 선택합니다. 그런 다음 **명명된 엔터티 추출** 타일을 선택합니다. 

1. *샘플*에서 다음 리뷰를 복사하여 붙여넣습니다.

    ```
    Tired hotel with poor service
    The Royal Hotel, London, United Kingdom
    5/6/2018
    This is an old hotel (has been around since 1950's) and the room furnishings are average - becoming a bit old now and require changing. The internet didn't work and had to come to one of their office rooms to check in for my flight home. The website says it's close to the British Museum, but it's too far to walk.
    ```

1. **실행**을 선택합니다. 출력을 검토합니다. *세부 정보* 섹션에서 추출된 엔터티에 유형 및 신뢰도 점수와 같은 추가 정보가 어떻게 제공되는지 확인합니다. 신뢰도 점수는 식별된 형식이 실제로 해당 범주에 속할 가능성을 나타냅니다.

## Azure AI 파운드리 포털에서 Azure AI 언어를 사용하여 핵심 구 추출

*핵심 구*는 텍스트에서 가장 중요한 정보입니다. Azure AI 언어의 핵심 구 추출 기능을 사용하여 리뷰에서 중요한 정보를 추출해 보겠습니다.

1. 언어 플레이그라운드에서 **정보 추출**을 선택합니다. 그런 다음 **핵심 구 추출** 타일을 선택합니다. 

1. *샘플*에서 다음 리뷰를 복사하여 붙여넣습니다.

    ```
    Good Hotel and staff
    The Royal Hotel, London, UK
    3/2/2018
    Clean rooms, good service, great location near Buckingham Palace and Westminster Abbey, and so on. We thoroughly enjoyed our stay. The courtyard is very peaceful and we went to a restaurant which is part of the same group and is Indian ( West coast so plenty of fish) with a Michelin Star. We had the taster menu which was fabulous. The rooms were very well appointed with a kitchen, lounge, bedroom and enormous bathroom. Thoroughly recommended.
    ```

1. **실행**을 선택합니다. 출력을 검토합니다. *세부 정보* 섹션에서 추출된 다양한 구를 확인합니다. 이러한 문구는 텍스트의 의미에 가장 크게 기여합니다.

## Azure AI 파운드리 포털에서 Azure AI 언어를 사용한 텍스트 요약
 
1. Azure AI 언어의 요약 기능을 살펴보겠습니다. 언어 플레이그라운드에서 *정보 요약*을 선택한 다음 **텍스트 요약** 타일을 선택합니다.

1. *샘플*에서 다음 리뷰를 복사하여 붙여넣습니다.
    
    ```
    Very noisy and rooms are tiny
    The Lombard Hotel, San Francisco, USA
    9/5/2018
    Hotel is located on Lombard street which is a very busy SIX lane street directly off the Golden Gate Bridge. Traffic from early morning until late at night especially on weekends. Noise would not be so bad if rooms were better insulated but they are not. Had to put cotton balls in my ears to be able to sleep--was too tired to enjoy the city the next day. Rooms are TINY. I picked the room because it had two queen size beds--but the room barely had space to fit them. With family of four in the room it was tight. With all that said, rooms are clean and they've made an effort to update them. The hotel is in Marina district with lots of good places to eat, within walking distance to Presidio. May be good hotel for young stay-up-late adults on a budget
    ```

1. **실행**을 선택합니다. 출력을 검토합니다. *세부 사항*의 *요약 추출*에서 가장 두드러진 문장에 대한 순위 점수를 확인할 수 있습니다.   

## 정리

실습이 완료되면  더 이상 필요하지 않은 리소스를 삭제합니다. 이렇게 하면 불필요한 비용이 발생하는 것을 방지할 수 있습니다.

1. [https://portal.azure.com](https://portal.azure.com)에서 **Azure Portal**을 열고 생성한 리소스가 포함된 리소스 그룹을 선택합니다.

1. 리소스를 선택하고 **삭제**를 선택한 다음 **예**를 선택하여 확인합니다. 그러면 리소스가 삭제됩니다.

## 자세한 정보

이 서비스를 사용하여 수행할 수 있는 작업을 자세히 알아보려면 [언어 서비스 페이지](https://learn.microsoft.com/azure/ai-services/language-service/overview)를 참조하세요.
