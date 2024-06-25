---
lab:
  title: Microsoft Edge의 Copilot 살펴보기
---
# Microsoft Edge의 Microsoft Copilot 살펴보기

이 연습에서는 Microsoft Copilot이 생성형 AI를 사용하여 새 콘텐츠를 만들 때 생산성을 높일 수 있는 몇 가지 방법을 살펴보겠습니다. 이 연습의 시나리오에서는 사업 아이디어에 대한 몇 가지 고급 노트로 시작하고 Microsoft Edge의 Copilot을 사용하여 잠재적 투자자를 위한 사업 계획 및 프레젠테이션을 개발하는 데 도움을 줍니다.

이 연습을 완료하는 데 약 **40**분 정도 소요됩니다.

> **참고**: 이 연습에서는 컴퓨터에서 [Microsoft Edge](https://www.microsoft.com/edge/download)에 로그인하는 데 사용되는 [개인 Microsoft 계정](https://signup.live.com)(예: outlook.com 계정)이 있다고 가정합니다.

## Copilot을 사용하여 문서 탐색 및 아이디어 조사

생성형 AI 탐색을 시작하려면 Edge에서 Microsoft Copilot을 사용하여 기존 문서를 검사하고 여기에서 몇 가지 인사이트를 추출해 보겠습니다.

1. Microsoft Edge에서 `https://onedrive.live.com`의 [OneDrive](https://onedrive.live.com)로 이동하여 개인 Microsoft 계정을 사용하여 로그인합니다. 표시된 환영 메시지나 제안을 닫습니다.
1. 다른 브라우저 탭에서 `https://github.com/MicrosoftLearning/mslearn-ai-fundamentals/raw/main/data/generative-ai/Business%20Idea.docx`의 [Business Idea.docx](https://github.com/MicrosoftLearning/mslearn-ai-fundamentals/raw/main/data/generative-ai/Business%20Idea.docx) 문서를 엽니다. 그런 다음 문서가 Edge에서 열리면 **OneDrive에 복사본 저장** 옵션을 선택하고 문서를 OneDrive의 **문서** 폴더에 저장합니다. 그러면 문서가 Microsoft Word 온라인에서 자동으로 열립니다.

    > **팁**: 파일 복사본을 OneDrive에 저장하는 옵션이 표시되지 않으면 해당 파일을 로컬 컴퓨터에 다운로드합니다. 그런 다음 OneDrive에서 **문서** 폴더를 열고 **+ 새로 추가** 단추를 사용하여 로컬 컴퓨터의 **Business Idea.docx** 파일을 OneDrive에 업로드합니다.

1. 뉴욕시의 청소 사업에 대한 몇 가지 고급 아이디어를 설명하는 **Business Idea.docx**의 텍스트를 확인합니다.
1. 다음과 같이 Edge 도구 모음의 **Copilot** 아이콘을 사용하여 Copilot 창을 엽니다.

    ![Microsoft Edge의 Copilot 창 스크린샷.](./media/generative-ai/edge-copilot.png)

1. Copilot 창에서 아래로 스크롤하여 필요한 모든 콘텐츠를 확인하고, **채팅** 탭이 선택되어 있고 대화 스타일이 **더 균형 잡힌**으로 설정되어 있는지 확인합니다. Copilot은 창의성과 실제 정밀도의 균형을 유지하면서 대응합니다.
1. Copilot 창 하단에 있는 채팅 상자에 다음 프롬프트를 입력합니다.

    ```
    What is this document about?
    ```

    메시지가 표시되면 Copilot이 페이지에 액세스하도록 허용할지 확인합니다.

1. 다음과 같이 문서의 주요 사항을 요약하는 Copilot의 응답을 검토합니다.

    ![응답이 포함된 Copilot 창의 스크린샷.](./media/generative-ai/copilot-response.png)

    > **참고**: 구체적인 응답은 다를 수 있습니다.

1. 다음 프롬프트를 입력합니다.

    ```
    How do I go about setting up a business in New York?
    ```

1. 응답을 검토합니다. 여기에는 뉴욕에서 비즈니스를 시작하는 데 도움이 되는 몇 가지 조언과 리소스 링크가 포함되어 있으며, 더 많은 정보를 가져오기 위해 제안된 후속 프롬프트가 포함될 수도 있습니다.

    > **중요**: AI가 생성한 응답은 웹에 공개된 정보를 기반으로 합니다. 사업체를 설립하는 데 필요한 단계를 이해하는 데 도움이 될 수 있지만 100% 정확하다고 보장할 수 없으며 전문적인 조언의 필요성을 바꿀 수는 없습니다!

## Copilot을 사용하여 사업 계획용 콘텐츠 만들기

이제 몇 가지 초기 조사를 완료했으므로 Copilot을 통해 청소 회사를 위한 사업 계획을 작성해 보겠습니다.

1. Microsoft Edge에 **Business Idea.docx** 문서가 열려 있는 상태에서 Copilot 창에 다음 프롬프트를 입력합니다.

    ```
    Suggest a name for my cleaning business
    ```

1. 제안 사항을 검토하고 청소 회사의 이름을 선택합니다(또는 원하는 이름을 찾으라는 메시지가 계속 표시됨).
1. 다음 프롬프트를 입력하고 *Contoso Cleaning*을 원하는 회사 이름으로 바꿉니다.

    ```
    Write a business plan for "Contoso Cleaning" based on the information in this document. Include an executive summary, market overview, and financial projections.
    ```

1. 응답을 검토하고 출력 아래에서 **복사**(&#128461;) 아이콘을 사용하여 응답을 클립보드에 복사합니다. 그런 다음 **Business Ideas.docx** 문서의 모든 텍스트를 선택하고 복사한 텍스트를 문서에 붙여넣어 바꿉니다. 마지막으로, 응답의 초기 텍스트(Copilot이 명령을 승인한 응답)를 청소 회사 이름에 대한 제목으로 바꿔 붙여넣은 텍스트를 정리합니다. 다음과 유사한 사업 계획 문서가 완성되어야 합니다.

    ![Copilot이 생성한 사업 계획이 포함된 Word 문서의 스크린샷.](./media/generative-ai/generated-content.png)

1. Copilot 창에서 다음 프롬프트를 입력합니다.

    ```
    Create a corporate logo for the cleaning company. The logo should be round and include an iconic New York landmark.
    ```

1. Microsoft Designer에서 만든 로고에 대한 네 가지 옵션을 표시하는 응답을 검토합니다.
1. 만족스러운 로고가 나올 때까지 더 많은 프롬프트를 사용하여 디자인(예: `Make it green and blue`)을 반복합니다.
1. 원하는 로고 디자인을 마우스 오른쪽 단추로 클릭하고 클립보드에 복사합니다. 그리고 다음과 같이 사업 계획 문서 상단에 붙여넣습니다.

    ![Copilot에서 생성된 이미지가 포함된 Word 문서의 스크린샷.](./media/generative-ai/generated-image.png)

1. Microsoft Word 탭을 닫고 OneDrive의 **문서** 폴더로 돌아갑니다.

## Copilot을 사용하여 프레젠테이션용 콘텐츠 만들기

Copilot의 도움으로 청소 사업 아이디어에 대한 사업 계획 초안을 작성했습니다. 이제 투자자가 사업을 시작하기 위한 자금을 빌려줄 수 있도록 설득하려면 효과적인 프레젠테이션이 필요합니다.

1. OneDrive의 **문서** 폴더에 새 **PowerPoint 프리젠테이션**을 추가합니다.

    **디자이너** 창이 자동으로 열리면 닫습니다.

1. 프레젠테이션 제목 슬라이드의 제목에 청소 회사 이름을 입력하고 자막에 `Investor Opportunity`를 입력합니다.
1. **두 개의 콘텐츠** 슬라이드 레이아웃(제목과 콘텐츠에 대한 두 개의 자리 표시자 포함)을 사용하여 새 슬라이드를 추가합니다.
1. 슬라이드 제목을 `Benefits of Hiring a Commercial Cleaner`로 변경합니다.
1. Copilot 창에서 다음 프롬프트를 입력합니다.

    ```
    Write a summary of the benefits of using a corporate cleaning company for your business. The summary should consist of five short bullet points.
    ```

1. Copilot의 응답을 클립보드에 복사하고 왼쪽 콘텐츠 자리 표시자에 붙여넣습니다. 그런 다음 요청을 승인하는 첫 문장을 삭제하고 만족스러울 때까지 자리 표시자의 텍스트 형식을 다시 지정합니다.
1. Copilot 창에서 다음 프롬프트를 입력합니다.

    ```
    Create a photorealistic image of a clean office.
    ```

1. Copilot에서 원하는 이미지를 생성하면 이를 클립보드에 복사하고 슬라이드 오른쪽에 있는 콘텐츠 자리 표시자에 붙여넣습니다.

    **디자이너** 창이 자동으로 열리면 원하는 슬라이드 디자인을 선택합니다. 그런 다음 **디자이너** 창을 닫습니다.

1. 다음과 유사한 슬라이드가 나올 때까지 필요하다고 생각되는 추가 서식 변경을 적용합니다.

    ![Copilot에서 생성된 콘텐츠가 포함된 PowerPoint 프레젠테이션의 스크린샷.](./media/generative-ai/powerpoint-slide.png)

1. PowerPoint 제목 표시줄에서 기본 프리젠테이션 이름(**프레젠테이션**)을 선택하고 이름을 `Business Presentation.pptx`로 바꿉니다.
1. PowerPoint 탭을 닫고 OneDrive의 **문서** 폴더로 돌아갑니다.

## Copilot을 사용하여 이메일 작성

비즈니스를 시작하는 데 도움이 되는 몇 가지 참고 자료를 만들었습니다. 이제 스타트업 자금을 제공하려는 투자자에게 연락할 시간입니다.

1. OneDrive 제목 표시줄 왼쪽 끝에 있는 **앱 시작 관리자**를 사용하여 **Outlook**을 엽니다.
1. 새 이메일을 작성하고 **받는 사람** 상자에 고유의 이메일 주소를 입력합니다.
1. Copilot 창에서 **작성** 탭을 선택합니다. 그리고 다음 옵션을 설정하여 새 콘텐츠를 작성합니다.
    - **작성 내용**: `Request a meeting with an investment bank to discuss funding for a commercial cleaning business.`
    - **톤**: 전문가
    - **Format**: 메일
    - **길이**: 중간
1. **초안 생성**을 선택하고 생성된 출력을 검토합니다.
1. 생성된 콘텐츠를 사용하여 여기에 표시된 대로 이메일을 완료합니다.

    ![Copilot에서 생성된 이메일 메시지의 스크린샷.](./media/generative-ai/generated-email.png)

    원하는 경우 이메일을 자신에게 보내도 됩니다.

## 과제

이제 Copilot을 사용하여 아이디어를 조사하고 콘텐츠를 생성하는 방법을 살펴보았습니다. 더 자세히 살펴보겠습니다. 새로운 Copilot 세션을 시작하려면 **채팅** 탭에서 프롬프트 상자 옆에 있는 **새 항목** 아이콘을 선택한 다음 Copilot을 사용하여 지역 도서관에서 어린이의 읽기 쓰기 능력을 장려하는 이벤트를 계획해 보세요. 사용해 볼 수 있는 프롬프트는 다음과 같습니다.

- 아이들이 어릴 때 책을 읽도록 격려하기 위한 몇 가지 조언을 조사해 줘.
- 행사를 위한 전단지나 포스터를 만들어 줘.
- 지역 아동 작가들을 행사에 초대하여 연설할 수 있도록 캠페인용 이메일을 작성해 줘.
- 이벤트를 시작할 프레젠테이션을 만들어 줘.

원하는 만큼 창의력을 발휘하여, Copilot이 정보 검색, 텍스트 생성 및 구체화, 이미지 만들기, 질문 답변을 통해 어떻게 도움을 줄 수 있는지 알아봅니다.


## 결론

이 연습에서는 Microsoft Edge의 Copilot을 사용하여 정보를 찾고 콘텐츠를 생성했습니다. Copilot에서 생성형 AI를 사용하는 것이 생산성과 창의성에 어떻게 도움이 될 수 있는지 확인했기를 바랍니다.

이 연습에 사용된 무료 서비스는 의심의 여지 없이 매우 강력하지만, Microsoft Copilot이 Windows 및 Microsoft Office 생산성 애플리케이션에 통합되어 일반적인 작업에 대해 고도로 상황에 맞는 도움말을 제공하는 [Microsoft 365용 Copilot](https://www.microsoft.com/microsoft-365/enterprise/copilot-for-microsoft-365)과 같은 서비스를 통해 더 많은 것을 달성할 수 있습니다. Microsoft 365를 사용하면 생성형 AI의 강력한 기능을 비즈니스 데이터 및 프로세스에 적용하는 동시에 기존 IT 인프라에 통합하여 관리 가능하고 안전한 솔루션을 보장할 수 있습니다.