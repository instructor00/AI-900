# Azure OpenAI 살펴보기

Azure OpenAI Service는 OpenAI에서 개발한 생성 AI 모델을 Azure 플랫폼에 제공하여 Azure 클라우드 플랫폼에서 제공하는 서비스의 보안, 확장성 및 통합의 이점을 활용하는 강력한 AI 솔루션을 개발할 수 있도록 합니다.

이 실습에서는 Azure OpenAI Service를 살펴보고 이를 사용하여 생성 AI 모델을 배포하고 실험합니다.

이 실습은 약 **25**분 정도 소요됩니다.

## 시작하기 전에

텍스트 및 코드 모델과 DALL-E 이미지 생성 모델 모두에 대해 Azure OpenAI 서비스에 액세스하려면 승인된 Azure 구독이 필요합니다.

- 무료 Azure 구독에 등록하려면 [https://azure.microsoft.com/free](https://azure.microsoft.com/free)를 참조하세요.
- Azure OpenAI 서비스에 대한 액세스를 요청하려면 [https://aka.ms/oaiapply](https://aka.ms/oaiapply)를 참조하세요.

## Azure OpenAI 리소스 프로비전

Azure OpenAI 모델을 사용하려면 먼저 Azure 구독에서 Azure OpenAI 리소스를 프로비전해야 합니다.

1. [Azure Portal](https://portal.azure.com)에 로그인합니다.
2. 다음 설정을 사용하여 **Azure OpenAI** 리소스를 만듭니다.
    - **구독**: *Azure OpenAI 서비스에 대한 액세스가 승인된 Azure 구독입니다.*
    - **리소스 그룹**: *기존 리소스 그룹을 선택하거나 원하는 이름으로 새 리소스 그룹을 만듭니다.*
    - **지역**: 미국 동부\*
    - **이름**: ‘원하는 고유한 이름’**
    - **가격 책정 계층**: 표준 S0

    > \* 지역마다 모델 가용성과 할당량이 다릅니다. 이 연습에서는 텍스트 생성에 GPT-35-Turbo 모델, 이미지 생성에 DALL-E 모델을 사용하게 되며, 둘 다 미국 동부에서 지원됩니다.

3. 배포가 완료될 때까지 기다립니다. 그런 다음, Azure Portal에서 배포된 Azure OpenAI 리소스로 이동합니다.

## Azure OpenAI Studio 살펴보기

Azure OpenAI Studio를 사용하여 Azure OpenAI Service에서 모델을 배포, 관리 및 탐색할 수 있습니다.

1. Azure OpenAI 리소스의 **개요** 페이지에서 **탐색** 단추를 사용하여 새 브라우저 탭에서 Azure OpenAI Studio를 엽니다. 또는 [Azure OpenAI Studio](https://oai.azure.com/)로 직접 이동합니다.

    Azure OpenAI Studio를 처음 열면 다음과 유사하게 표시됩니다.

    ![Azure OpenAI Studio의 스크린샷.](./media/generative-ai/ai-studio.png)

1. 왼쪽 창에서 사용 가능한 페이지를 봅니다. 언제든지 상단의 홈페이지로 돌아갈 수 있습니다. 또한 OpenAI Studio는 다음을 수행할 수 있는 여러 페이지를 제공합니다.
    - *플레이그라운드*에서 모델을 실험해 보세요.
    - 모델 배포 및 데이터를 관리합니다.

## 언어 생성을 위한 모델 배포

자연어 생성을 실험하려면 먼저 모델을 배포해야 합니다.

1. **모델** 페이지에서 Azure OpenAI 서비스 인스턴스에서 사용 가능한 모델을 확인합니다.
1. **배포 가능** 상태가 **예**인 **gpt-35-turbo** 모델을 선택한 다음 **배포**를 선택합니다.

    ![Azure AI Studio의 모델 페이지 스크린샷.](./media/generative-ai/deploy-model.png)

1. 다음 설정을 사용하여 새 배포를 만듭니다.
    - **모델**: gpt-35-turbo
    - **모델 버전**: 기본값으로 자동 업데이트
    - **배포 이름**: *모델 배포에 대한 고유한 이름*
    - **고급 옵션**
        - **콘텐츠 필터**: 기본값
        - **배포 유형**: 표준
        - **분당 토큰 속도 제한**: 5K\*
        - **동적 할당량 사용**: 사용

    > \* 분당 5,000개 토큰의 속도를 제한하더라도 동일한 구독을 사용하는 다른 사용자에게 용량을 남겨두면서 이 연습을 충분히 완료할 수 있습니다.

## *채팅* 플레이그라운드를 사용하여 모델 작업

이제 모델을 배포했으므로 이를 *채팅* 플레이그라운드에서 사용하여 채팅 인터페이스에 제출한 프롬프트에서 자연어 출력을 생성할 수 있습니다.

1. [Azure OpenAI Studio](https://oai.azure.com/)에서 왼쪽 창에 있는 **채팅** 플레이그라운드로 이동합니다.

    *채팅* 플레이그라운드는 다음과 같이 배포된 모델과 상호 작용할 수 있는 챗봇 인터페이스를 제공합니다.

    ![Azure OpenAI Studio의 채팅 플레이그라운드 스크린샷.](./media/generative-ai/chat-playground.png)

1. **구성** 창에서 모델 배포가 선택되었는지 확인합니다.
1. **도우미 설정** 창에서 **기본** 시스템 메시지 템플릿을 선택하고 이 템플릿이 만드는 시스템 메시지를 확인합니다. 시스템 메시지는 채팅 세션에서 모델이 작동하는 방식을 정의합니다.
1. **채팅 세션** 섹션에 다음 사용자 메시지를 입력합니다.

    ```
   What is generative AI?
    ```

1. 생성 AI의 정의를 제공해야 하는 모델에서 반환된 출력을 관찰합니다.
1. 후속 질문으로 다음 사용자 메시지를 입력합니다.

    ```
   What are three benefits it provides?
    ```

1. 출력을 검토하여 채팅 세션이 이전 입력 및 응답을 추적하여 컨텍스트를 제공하고(따라서 "it"을 "생성 AI"를 지칭하는 것으로 올바르게 해석함) 요청된 내용에 따라 적절한 응답을 제공하는지 확인합니다(생성 AI의 세 가지 이점을 반환해야 함).

## *DALL-E* 플레이그라운드를 사용하여 이미지 생성

Azure OpenAI Service는 언어 생성 모델 외에도 이미지 생성을 위한 DALL-E 2 모델을 지원합니다.

> **참고**: 이 연습 섹션을 완료하려면 Azure OpenAI 서비스 액세스 애플리케이션에서 DALL-E 기능에 대한 액세스를 애플리케이션하고 받아야 합니다.

1. [Azure OpenAI Studio](https://oai.azure.com/)에서 왼쪽 창에 있는 **DALL-E** 플레이그라운드로 이동합니다.
1. 다음 프롬프트를 입력합니다.

    ```
    A robot eating spaghetti
    ```

1. **생성**을 선택하고 다음과 유사하게 프롬프트에 제공한 설명을 기반으로 한 이미지로 구성된 결과를 확인합니다.

    ![Azure OpenAI Studio의 DALL-E 플레이그라운드 스크린샷.](./media/generative-ai/dall-e-playground.png)

1. 프롬프트를 다음과 같이 수정하여 두 번째 이미지를 생성합니다.

    ```
    A robot eating spaghetti in the style of Rembrandt
    ```
1. 다음과 유사하게 새 이미지가 프롬프트의 요구 사항과 일치하는지 확인합니다.

    ![Azure OpenAI Studio에서 DALL-E가 생성한 이미지의 스크린샷.](./media/generative-ai/dall-e-results.png)

## 정리

Azure OpenAI 리소스 사용이 완료되면 [Azure Portal](https://portal.azure.com/?azure-portal=true)에서 배포 또는 전체 리소스를 삭제해야 합니다.
