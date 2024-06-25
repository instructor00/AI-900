---
lab:
  title: Microsoft 365용 Copilot 살펴보기
---
# Microsoft 365용 Copilot 살펴보기

이 연습에서는 Microsoft Copilot이 생성형 AI를 사용하여 새 콘텐츠를 만들 때 생산성을 높일 수 있는 몇 가지 방법을 살펴보겠습니다. 이 연습의 시나리오에서는 사업 아이디어에 대한 몇 가지 개략적인 메모로 시작하고, 잠재적 투자자를 위한 사업 계획 및 프레젠테이션을 작성하는 데 도움을 얻기 위해 Word, PowerPoint, Excel 등 여러 앱에서 Microsoft 365용 Copilot을 사용합니다.

이 연습을 완료하는 데 약 **40**분 정도 소요됩니다.

> **참고**: 이 연습을 수행하려면 조직의 **Microsoft 365용 Copilot** 라이선스가 필요합니다.

## Copilot을 사용하여 문서 탐색 및 아이디어 조사

생성형 AI 탐색을 시작하려면 Word용 Copilot을 사용하여 기존 문서를 검사하고 여기에서 몇 가지 인사이트를 추출해 보겠습니다.

1. 웹 브라우저에서 `https://github.com/MicrosoftLearning/mslearn-ai-fundamentals/raw/main/data/generative-ai/Business%20Idea.docx`에 있는 [Business Idea.docx](https://github.com/MicrosoftLearning/mslearn-ai-fundamentals/raw/main/data/generative-ai/Business%20Idea.docx) 문서를 엽니다. 
1. **다운로드**를 선택하여 파일을 PC의 **다운로드** 폴더에 저장합니다.
1. 방금 다운로드한 문서를 **OneDrive** 폴더로 **이동**하거나 **복사하여 붙여넣습니다**.
1. **OneDrive** 폴더에서 Microsoft Word의 **Business Idea.docx**를 열고(새로운 기능에 대한 환영 메시지 또는 알림을 닫음), 뉴욕시의 청소 사업에 대한 몇 가지 개략적인 아이디어를 설명하는 문서를 검토합니다. 메시지가 표시되면 상단에서 **편집 사용**을 선택합니다.
1. 다음과 같이 Word 도구 모음에서 **Copilot** 아이콘을 찾아 선택하여 Copilot 창을 엽니다(시각적 테마는 다를 수 있음).

    ![Microsoft Word의 Copilot 창 스크린샷.](./media/generative-ai/copilot-word-pane.png)

1. Copilot 창의 하단 텍스트 영역에 다음 프롬프트를 입력합니다.

    ```
    What is this document about?
    ```

1. 다음과 같이 문서의 주요 사항을 요약하는 Copilot의 응답을 검토합니다.

    ![Word에서 응답이 포함된 Copilot 창 스크린샷.](./media/generative-ai/copilot-response-word.png)

    > 표시되는 구체적인 응답은 생성형 AI의 특성에 따라 달라질 수 있습니다.

1. Copilot 창으로 돌아가서 Copilot에게 다음 질문을 합니다.

    ```
    How do I setup a new business in New York?
    ```

1. 응답을 검토하고 필요에 따라 추가 질문을 합니다. 응답이 만족스러우면 응답 아래에 있는 **복사**(&#128461;) 아이콘을 사용하여 응답을 클립보드에 복사합니다. Word 문서에 붙여넣고 모든 텍스트를 선택한 다음, 선택한 텍스트의 맨 아래에 있는 Copilot 아이콘을 선택하여 텍스트를 테이블로 시각화합니다.

    ![Copilot에게 표 형식으로 시각화하도록 요청하는 것을 보여 주는 스크린샷.](./media/generative-ai/copilot-rewrite-as-table.png)

1. 표를 검토하고 Copilot에게 자세한 내용에 대한 참고 자료 등 추가 정보를 추가하도록 요청합니다.  응답은 다음과 같아야 합니다(**다시 생성** 단추를 사용해야 할 수도 있음).

    ![표 형식의 Copilot 응답 스크린샷.](./media/generative-ai/copilot-rewrite-as-table-response.png)

    > **중요**: AI가 생성한 응답은 웹에 공개된 정보를 기반으로 합니다. 사업체를 설립하는 데 필요한 단계를 이해하는 데 도움이 될 수 있지만 100% 정확하다고 보장할 수 없으며 전문적인 조언의 필요성을 바꿀 수는 없습니다!

1. Copilot이 생성한 표에 만족하면 **보관** 옵션을 선택합니다.

## Copilot을 사용하여 사업 계획용 콘텐츠 만들기

이제 몇 가지 초기 조사를 완료했으므로 Copilot을 통해 청소 회사를 위한 사업 계획을 작성해 보겠습니다.

1. **Business Idea.docx** 문서가 열려 있는 상태에서 Copilot 창에 다음 프롬프트를 입력합니다.

    ```
    Can you suggest a name for my cleaning business?
    ```

1. 제안 사항을 검토하고 청소 회사의 이름을 선택합니다(또는 원하는 이름을 찾으라는 메시지가 계속 표시됨).
1. Word 문서에서 여백에 있는 Copilot 아이콘을 선택하여 새 콘텐츠 초안을 작성합니다. 다음 프롬프트를 입력하고 **Contoso Cleaning**을 원하는 회사 이름으로 바꿉니다.

    ```
    Write a business plan for "Contoso Cleaning" based on the information in this document. Include an executive summary, market overview, and financial projections.
    ```

    ![Copilot이 사업 계획 초안을 작성하는 것을 보여 주는 스크린샷.](./media/generative-ai/copilot-draft-business-plan-prompt.png)

1. Copilot이 작성한 응답을 검토하고 보관하거나 톤, 길이를 조정하거나 Copilot에게 새로운 메시지로 다시 작성하도록 요청합니다. 문서에 적절한 제목과 스타일을 적용하여 전문적으로 보이도록 합니다. 응답은 다음과 같습니다.

    ![Copilot이 생성한 사업 계획이 포함된 Word 문서의 스크린샷.](./media/generative-ai/copilot-draft-business-plan-response.png)

1. 비즈니스 계획의 재무 예측 형식이 테이블로 지정되지 않은 경우 해당 예측을 선택하고 Copilot을 사용하여 예측을 테이블로 시각화합니다.
1. 재무 계획표를 선택하고 클립보드에 복사합니다.
1. Word 문서를 저장한 다음 닫습니다.

## Copilot for Excel에서 재무 계획 시각화

사업 계획이 준비되어 있으면 재무 계획에 대한 데이터 중 일부를 선택하고 Excel의 Copilot에 해당 데이터를 시각화하도록 요청하여 투자자에게 보여 줄 이메일 또는 프레젠테이션에 포함시킬 수 있습니다.

1. **Excel**을 열고 새 빈 통합 문서를 만듭니다. 통합 문서를 **Financial Projections.xlsx**로 OneDrive에 즉시 저장하지 않으면 Copilot이 작동하지 않습니다.
1. **Business Idea.docx**의 판매 계획표를 Excel 스프레드시트에 붙여넣고 **표 형식으로 지정**합니다. 방법:
    1. 데이터 내에서 **셀**을 선택합니다.
    1. **홈**을 선택하고 스타일 아래에서 **표 형식**을 선택합니다. 
    1. 표 스타일을 선택합니다.
    1. **표 만들기** 대화 상자에서 셀 범위를 확인하거나 설정합니다.
    1. 표에 헤더가 있는지 표시하고 **확인**을 선택합니다.
1. 판매 예측을 테이블 형식으로 지정한 상태에서 Excel 리본의 **홈** 탭에서 Copilot 창을 열고 다음 프롬프트를 입력합니다.

    ```
    Suggest ways to visualize these financial projections.
    ```
    
1. Copilot은 데이터를 시각화하는 방법을 제안하고 피벗 차트를 새 시트에 추가할 것을 제안해야 합니다.

    ![Excel의 Copilot에서 재무 계획을 시각화하는 것을 보여 주는 스크린샷.](./media/generative-ai/copilot-excel-visualize-projections.png)

1. 새 시트에 피벗 차트를 추가하고 엽니다. 차트를 선택한 다음 **디자인**을 선택하여 스타일을 적용하고 차트 종류 및 기타 작업을 변경합니다. 결국에는 다음과 유사한 것이 있어야 합니다.

    ![Excel의 Copilot이 피벗 차트를 추가하는 것을 보여 주는 스크린샷.](./media/generative-ai/copilot-excel-chart-design.png)

1. 통합 문서를 저장하고 Excel을 닫습니다.

방금 Word의 Copilot에서 만들어진 데이터를 사용하여 Excel에서 시각화했습니다. 다음 연습에서는 Outlook의 Copilot을 사용하여 수행한 작업에 대한 이메일을 작성하고 보내는 방법을 살펴보겠습니다.

## Copilot을 사용하여 이메일 작성

비즈니스를 시작하는 데 도움이 되는 몇 가지 참고 자료를 만들었습니다. 이제 스타트업 자금을 제공하려는 투자자에게 연락할 시간입니다.

1. **Outlook**을 엽니다. Microsoft 365 계정으로 Outlook을 설정하지 않은 경우 이렇게 합니다.

    > **팁**: 관련 도움말은 [Outlook 설정 및 사용 - Microsoft 지원](https://support.microsoft.com/office/set-up-and-use-outlook-4636f361-d5e3-4a87-9cd4-382858de55fa)을 참조하세요.

1. 도구 모음에서 아직 활성화되지 않은 경우 **새 Outlook** 환경으로 전환합니다.

    > **참고**: Outlook의 최신 Copilot 기능을 얻으려면 "새 Outlook" 환경을 사용해야 합니다. 사용 중인 버전을 확인하려면 [사용 중인 Outlook 버전은 무엇인가요? - Microsoft 지원](https://support.microsoft.com/office/what-version-of-outlook-do-i-have-b3a9568c-edb5-42b9-9825-d48d82b2257c)를 참조하세요..

1. 새 이메일을 작성하고 **받는 사람** 상자에 고유의 이메일 주소를 입력합니다.
1. Copilot 창이나 이메일 본문 내에서 바로 이메일 초안 작성을 시작할 수 있습니다.

    ![Outlook에서 Copilot을 사용하여 이메일 초안을 작성하는 옵션의 스크린샷.](./media/generative-ai/copilot-draft-email-outlook.png)
    
1. 다음 프롬프트를 입력하고 옵션을 조정하여 톤을 "정중한"으로, 길이를 "중간"으로 설정합니다.

    ```
    Request a meeting with an investment bank to discuss funding for a commercial cleaning business.
    ```

    ![Outlook의 Copilot을 사용하여 이메일 초안 작성 스크린샷.](./media/generative-ai/copilot-draft-email-adjust-tone-outlook.png)

1. **초안 생성**을 선택하고 생성된 출력을 검토합니다. 톤을 조정하거나 Copilot에게 이메일에 대해 변경하고 싶은 내용을 알려 줍니다.

    ![Outlook의 Copilot으로 생성된 이메일의 스크린샷.](./media/generative-ai/copilot-draft-email-results-outlook.png)

1. 원하는 경우 이메일을 자신에게 보내도 됩니다.

## Copilot을 사용하여 프레젠테이션용 콘텐츠 만들기

Copilot의 도움으로 청소 사업 아이디어에 대한 사업 계획 초안을 작성하고 몇 가지 재무 계획을 준비했으며 잠재적 투자자와의 모임을 요청하는 이메일을 보냈습니다. 이제 비즈니스의 혜택을 전달하기 위한 효과적인 프레젠테이션이 필요합니다.

1. **PowerPoint**를 열고 **비어 있는 프레젠테이션**을 새로 만듭니다. **디자이너** 창이 자동으로 열리면 닫습니다.

    ![PowerPoint에서 새 빈 프레젠테이션을 만드는 스크린샷.](./media/generative-ai/powerpoint-create-blank-presentation.png)

1. 프레젠테이션을 OneDrive 폴더에 **Cleaning Company.pptx**로 저장합니다.
1. 리본의 **홈 탭**에서 **Copilot 단추**를 선택하고 **프레젠테이션 만들기**를 선택한 후 다음과 같이 Copilot 창에서 프롬프트를 완료합니다.

    ```
    Create a presentation about a corporate cleaning service in New York City.
    ```

1. Copilot은 프레젠테이션에서 슬라이드를 생성합니다.  이 프로세스는 몇 분 정도 걸릴 수 있으며 출력은 다른 테마로 다음과 같아야 합니다.

    ![Word 문서에서 Copilot으로 만든 PowerPoint 프레젠테이션의 스크린샷.](./media/generative-ai/copilot-powerpoint-create-image.png)

1. 프레젠테이션에서 두 번째 마지막 슬라이드를 선택합니다. 그런 다음, Copilot 창에서 **슬라이드 정보 추가...** 프롬프트를 사용하여 `the benefits of an eco-friendly approach to cleaning.`에 대한 새 슬라이드를 만듭니다.

    ![PowerPoint 프레젠테이션의 새 슬라이드를 만드는 방법을 보여 주는 스크린샷.](./media/generative-ai/copilot-powerpoint-add-new-slide.png)

1. 프레젠테이션을 저장합니다.

## 과제

이제 몇 가지 다른 앱에서 Microsoft 365용 Copilot을 사용하여 아이디어를 조사하고 콘텐츠를 생성하는 방법을 살펴보았습니다. 더 자세히 살펴보겠습니다. Copilot을 사용하여 지역 도서관에서 어린이의 읽기 쓰기 능력을 장려하는 이벤트를 계획해 보세요. 사용해 볼 수 있는 프롬프트는 다음과 같습니다.

- 아이들이 어릴 때 책을 읽도록 격려하기 위한 몇 가지 조언을 조사해 줘.
- 행사를 위한 전단지나 포스터를 만들어 줘.
- 지역 아동 작가들을 행사에 초대하여 연설할 수 있도록 캠페인용 이메일을 작성해 줘.
- 이벤트를 시작할 프레젠테이션을 만들어 줘.

원하는 만큼 창의력을 발휘하여, Copilot이 정보 검색, 텍스트 생성 및 구체화, 이미지 만들기, 질문 답변을 통해 어떻게 도움을 줄 수 있는지 알아봅니다.

## 결론

이 연습에서는 [Microsoft 365용 Copilot](https://www.microsoft.com/microsoft-365/enterprise/copilot-for-microsoft-365)을 사용하여 정보를 찾고 콘텐츠를 생성했습니다. Copilot에서 생성형 AI를 사용하는 것이 생산성과 창의성에 어떻게 도움이 될 수 있는지 확인했기를 바랍니다. Microsoft 365를 사용하면 생성형 AI의 강력한 기능을 비즈니스 데이터 및 프로세스에 적용하는 동시에 기존 IT 인프라에 통합하여 관리 가능하고 안전한 솔루션을 보장할 수 있습니다.
