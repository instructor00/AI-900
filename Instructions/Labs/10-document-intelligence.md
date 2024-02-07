---
lab:
  title: Document Intelligence Studio에서 양식 데이터 추출
---

# Document Intelligence Studio에서 양식 데이터 추출

Azure AI Document Intelligence는 양식 및 문서에서 정보를 분석 및 추출한 다음 필드 이름과 데이터를 식별할 수 있습니다. 

문서 인텔리전스는 OCR(광학 문자 인식)을 기반으로 어떻게 구축되나요? OCR은 인쇄되거나 필기된 문서를 읽을 수 있지만, OCR은 데이터베이스에 저장하거나 분석하기 어려운 구조화되지 않은 형식으로 텍스트를 추출합니다. 문서 인텔리전스는 테이블의 키/값 쌍 및 정보와 같은 텍스트 구조를 캡처하여 구조화되지 않은 데이터를 이해합니다. 

이 연습에서는 영수증에 대한 데이터를 인식하도록 학습된 문서 인텔리전스의 미리 빌드된 모델을 살펴보겠습니다. 

> **참고** Azure AI Document Intelligence는 Azure Form Recognizer의 새 이름입니다. Azure Portal 또는 Document Intelligence Studio에 Azure Form Recognizer가 계속 표시되어 있을 수 있습니다.

## 문서 인텔리전스* 리소스 만들기 *

Document Intelligence 리소스 또는 Azure AI 서비스 리소스를 *만들어 Azure AI Document Intelligence* 를 *사용할 수 있습니다* . 이 연습에서는 문서 인텔리전스* 리소스가 아직 없는 경우 만듭니*다.

1. 다른 브라우저 탭에서 Document Intelligence Studio[를 열고 ](https://formrecognizer.appliedai.azure.com/studio)Microsoft 계정으로 로그인합니다.
1. 설정 선택하고 리소스** 탭을 **선택합니다. 새 리소스** 만들기를 선택합니다**.** ** 
1. 리소스 만들기 대화 상자에서 다음을 입력합니다.
    - **구독**: *자신의 Azure 구독*.
    - **리소스 그룹**: *고유한 이름이 있는 리소스 그룹을 선택하거나 생성*합니다.
    - **새 리소스 이름**: *고유한 이름을* 입력합니다.
    - **위치**: *지역을* 선택합니다.
    - **가격 책정 계층**: *무료 FO(사용 가능한 경우 표준 SO 선택)*.
1. 계속**을 선택한 다음 **마침**을 선택합니다**. 리소스가 배포될 때까지 기다립니다.

    >**참고** 리소스가 아직 표시되지 않으면 페이지를 새로 고쳐**야 할 **수 있습니다.

Document Intelligence Studio를 열어 두세요.

## Document Intelligence Studio에서 영수증 분석

이제 가상의 Northwind Traders 소매 회사에 대한 영수증을 분석할 준비가 되었습니다.

1. 샘플 문서를 컴퓨터에 다운로드하려면 선택합니다[](https://aka.ms/mslearn-receipt)**https://aka.ms/mslearn-receipt**.  폴더를 엽니다. 
1. Form Recognizer Studio를 선택하여 **문서 인텔리전스 스튜디오**** 시작 페이지로 돌아가**고 영수증 **아래에서 사용해 보세요**.
1. 미리 빌드된 드롭다운 목록에서 영수증이 **선택되어 있는지 확인합니다** .
1. 파일** 찾아보기를 선택하고 **그림을 저장한 폴더로 이동합니다. 영수증 사진을 선택한 다음 **엽니다**. 이미지가 화면 왼쪽에 나타납니다.

    ![노스 윈드 영수증.](media/document-intelligence/northwind-receipt.jpg)

1. 오른쪽에서 분석** 실행을 선택합니다**.
1. 분석이 실행되면 결과가 반환됩니다. 서비스는 판매자의 이름, 주소, 전화 번호, 거래 날짜 및 시간뿐만 아니라 품목, 소계, 세금 및 총 금액과 같은 특정 데이터 필드를 인식했습니다. 각 필드 옆에는 필드가 올바른 백분율 확률이 있습니다.

이 연습에서는 Document Intelligence Studio를 사용하여 문서 인텔리전스 리소스를 만들었습니다. 그런 다음, 서비스를 사용하여 영수증을 분석했습니다. 반환된 결과에서 Document Intelligence에서 특정 필드를 식별하여 일상적인 문서의 데이터를 보다 쉽게 처리할 수 있는 방법을 확인했습니다. Document Intelligence Studio를 닫기 전에 다른 언어의 영수증을 포함하여 일부 샘플 영수증을 사용해 보세요.

## 정리

더 많은 연습을 수행하지 않으려면 더 이상 필요하지 않은 리소스를 삭제합니다. 이렇게 하면 불필요한 비용이 발생하지 않습니다.

1. Azure[ Portal을 ]( https://portal.azure.com)열고 만든 리소스가 포함된 리소스 그룹을 선택합니다.
1. 리소스를 선택하고 삭제**를 선택한 다음 **예(예**)를 선택하여 **확인합니다. 그런 다음 리소스가 삭제됩니다.

## 자세한 정보

이 연습에서는 AI 문서 인텔리전스 서비스의 일부 기능만 보여 줬습니다. 이 서비스를 사용하여 수행할 수 있는 작업을 자세히 알아보려면 문서 인텔리전스[ 페이지를 참조](https://learn.microsoft.com/azure/ai-services/document-intelligence/overview?view=doc-intel-3.1.0)하세요.
