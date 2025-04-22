---
lab:
  title: Microsoft Copilot을 통해 생성 AI 살펴보기
---
# Microsoft Copilot을 통해 생성 AI 살펴보기

생성형 AI는 콘텐츠를 생성하는 AI 내 기능 범주를 설명합니다. 사람은 일반적으로 채팅 애플리케이션에 기본 제공된 생성형 AI와 상호 작용합니다. 이러한 애플리케이션의 인기 있는 예로는 실시간 인텔리전스와 지원을 제공하여 업무 환경을 개선하도록 설계된 AI 기반 생산성 도구인 Microsoft Copilot이 있습니다. 

이 연습에서는 Microsoft Copilot을 사용하여 여행 계획을 생성합니다.

> **참고**: 이 연습에서는 [개인 Microsoft 계정](https://signup.live.com)(예: Outlook.com 계정)이 있다고 가정합니다.

## Microsoft Copilot을 사용하여 여행 계획 생성

1. 웹 브라우저에서 [Microsoft Copilot](https://copilot.microsoft.com)(`https://copilot.microsoft.com`)을 엽니다. 화면 오른쪽의 **로그인** 버튼을 클릭합니다. 개인 Microsoft 계정을 사용하여 로그인하고 표시되는 환영 메시지나 제안을 모두 닫습니다.

    >**참고**: **회사** 또는 **개인** 계정으로 계속 진행하라는 메시지가 표시될 수 있습니다. **개인**을 선택하고 로그인합니다. 

1. 다음과 같은 방법으로 생성형 AI 도우미의 응답을 개선할 수 있습니다.
    - 도우미로 수행할 작업에 대한 특정 목적부터 시작
    - 이전 프롬프트와 응답을 기반으로 반복하여 결과 구체화
    - 특정 범위의 정보 내에서 응답의 근거가 되는 출처 제공
    - 컨텍스트를 추가하여 응답의 적절성 및 관련성 극대화
    - 응답에 대한 명확한 기대치 설정

1. 특정 목표가 있는 프롬프트를 사용하여 Microsoft Copilot에서 응답을 생성해 보겠습니다. Copilot 창 하단의 채팅창에 다음 프롬프트를 입력합니다.

    ```prompt
    I'm planning a trip to Paris in September. Can you help me?
    ```

1. Copilot의 응답을 검토합니다. 

    >**참고**: 생성형 AI의 특성상 구체적인 응답은 다를 수 있다는 점에 유의하세요.
 
1. 다른 프롬프트를 사용해 보겠습니다. 다음을 입력합니다.

    ```prompt
    Where's a good location in Paris to stay? 
    ```

1. 답변을 검토하면 파리에서 머무를 수 있는 몇 가지 장소를 알려줄 것입니다.

1. 이전 프롬프트와 응답을 기반으로 반복하여 결과를 개선해 보겠습니다. 다음 프롬프트를 입력합니다.
    
    ```prompt
    Can you give me more information about dining options near the first location?
    ``` 

1. 응답을 검토하여 이전 응답의 위치 근처에 있는 식당 옵션을 제공하게 됩니다. 

1. 이제 특정 정보 범위에서 응답의 근거가 되는 원본을 제공해 보겠습니다. 다음을 입력합니다. 
    
    ```prompt
    Based on the information at https://en.wikipedia.org/wiki/History_of_Paris, what were the key events in the city's history?
    ```

1. 제공된 웹사이트를 기반으로 정보를 제공하는 응답을 검토합니다. 

1. 응답의 관련성을 극대화하기 위해 컨텍스트를 추가해 보겠습니다. 다음 프롬프트를 입력합니다. 

    ```prompt
    What three places do you recommend I stay in Paris to be within walking distance to historical attractions? Explain your reasoning.
    ```

1. 응답과 해당 응답에 대한 이유를 검토합니다.  

1. 이제 응답에 대한 명확한 기대치를 설정합니다. 다음 프롬프트를 입력합니다.
    
    ```prompt
    What are the top 10 sights to see in Paris? Answer with a numbered list in order of popularity.
    ```

1. 응답을 검토하면 파리에서 볼 수 있는 명소의 번호 매기기 목록이 표시됩니다.

1. 진행하기 전에 다시 맨 위로 스크롤하여 채팅 기록을 확인할 수 있다는 점에 유의하세요. 채팅창 옆에 있는 더하기 기호(**+**)를 사용하여 *새* 채팅을 시작하거나, 이미지를 업로드하여 프롬프트에 근거가 되는 원본을 추가할 수도 있습니다.    

1. 완료했으면 브라우저 창을 닫습니다. 
