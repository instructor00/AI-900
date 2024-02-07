---
lab:
  title: Vision Studio에서 텍스트 읽기
---

# Vision Studio에서 텍스트 읽기

이 연습에서는 Azure AI 서비스를 사용하여 Azure AI Vision의 광학 문자 인식 기능을 살펴봅니다. Vision Studio를 사용하여 코드를 작성하지 않고 이미지에서 텍스트를 추출하는 실험을 수행합니다.

일반적인 컴퓨터 비전 과제는 이미지에 포함된 텍스트를 감지하고 해석하는 것입니다. 이를 OCR(광학 문자 인식)라고 합니다. 이 연습에서는 Azure AI Vision 서비스를 포함하는 Azure AI 서비스 리소스를 사용합니다. 그런 다음 Vision Studio를 사용하여 다양한 유형의 이미지로 OCR을 사용해 봅니다.

## Azure AI 서비스 리소스를 생성합니다

Azure AI Services 다중 서비스 리소스와 함께 **Azure AI Vision의 OCR 기능을 사용할 수 있습니다** . 아직 만들지 않았다면 Azure 구독에서 **Azure AI 언어 서비스** 리소스를 만듭니다.

1. 다른 브라우저 탭에서 Azure Portal을 **[https://portal.azure.com](https://portal.azure.com?azure-portal=true)열고 Azure** 구독과 연결된 Microsoft 계정으로 로그인합니다.

1. **65291을 클릭합니다. 리소스** 단추를 만들고 Azure AI 서비스를 검색*합니다*. Azure AI 서비스 계획 만들기****를** 선택합니다**. 페이지로 이동하여 Azure AI 서비스 리소스를 만듭니다. 다음 설정을 사용하여 PuTTY를 구성합니다.
    - **구독**: *자신의 Azure 구독*.
    - **리소스 그룹**: *고유한 이름이 있는 리소스 그룹을 선택하거나 생성*합니다.
    - **지역**: 미국 동부.
    - **이름**: 고유한 이름을 입력합니다.
    - **가격 책정 계층**: *표준 S0.*
    - **이 상자를 검사 아래의 모든 용어를 읽고 이해했음*을 인정합니다.***

1. 검토 + 만들기**를 선택한 다음 **만들기**를 선택하고 **배포가 완료되기를 기다립니다.

## Azure AI 서비스 리소스를 Vision Studio에 커넥트

다음으로, 위에서 프로비전한 Azure AI 서비스 리소스를 Vision Studio에 연결합니다.

1. 다른 브라우저 탭에서 .에서https://portal.vision.cognitive.azure.com[](https://portal.vision.cognitive.azure.com?azure-portal=true) Vision Studio**로 **이동합니다.

1. 계정으로 로그인하고 Azure AI 서비스 리소스를 만든 디렉터리와 동일한 디렉터리를 사용하고 있는지 확인합니다.

1. Vision Studio 홈페이지의 비전** 시작 제목 아래에서 **모든 리소스** 보기를 선택합니다**.

    ![모든 리소스 보기 링크는 Vision Studio에서 Vision 시작 아래에 강조 표시됩니다.](./media/analyze-images-vision/vision-resources.png)

1. **페이지에서 작업**할 리소스 선택에서 목록에서 위에서 만든 리소스 위에 마우스 커서를 놓고 리소스 이름 왼쪽에 있는 상자를 검사 다음, 기본 리소스**로 선택을 선택합니다**.

    > **참고**: 리소스가 나열되지 않은 경우 페이지를 새로 고쳐**야 할 **수 있습니다.

    ![대화 상자에서 작업할 리소스 선택은 cog-ms-learn-vision-SUFFIX Cognitive Services 리소스가 강조 표시되고 검사 표시됩니다. 기본 리소스로 선택 단추가 강조 표시됩니다.](./media/analyze-images-vision/default-resource.png)

1. 화면 오른쪽 위에 있는 "x"를 선택하여 설정 페이지를 닫습니다.

## Vision Studio의 이미지에서 텍스트 추출
    
1. 웹 브라우저에서 .에서https://portal.vision.cognitive.azure.com[](https://portal.vision.cognitive.azure.com?azure-portal=true) Vision Studio**로 **이동합니다.

1. **Vision** 방문 시작 페이지에서 광학 문자 인식을** 선택한 다음 **이미지** 타일에서 텍스트 추출을 선택합니다**.

1. **Try It Out** 부제목 아래에서 상자를 읽고 검사 리소스 사용 정책을 승인합니다.  

1. ocr-images.zip 다운로드하려면 선택합니다[](https://aka.ms/mslearn-ocr-images)**https://aka.ms/mslearn-ocr-images**.**** 그런 다음 폴더를 엽니다.

1. 포털에서 파일** 찾아보기를 선택하고 **ocr-images.zip** 다운로드한 컴퓨터의 폴더로 **이동합니다. **advert.jpg** 선택하고 열기**를 선택합니다**.

1. 이제 반환되는 내용을 검토합니다.
    - 검색된 특성**에서 **이미지에 있는 모든 텍스트는 영역, 선 및 단어의 계층 구조로 구성됩니다.
    - 이미지에서 텍스트의 위치는 다음과 같이 경계 상자로 표시됩니다.

    ![윤곽선이 있는 이미지의 텍스트 이미지](media/read-text-computer-vision/text-bounding-boxes.png)

1. 이제 다른 이미지를 사용해 볼 수 있습니다. 파일** 찾아보기를 선택하고 **GitHub에서 파일을 저장한 폴더로 이동합니다. letter.jpg** 선택합니다**.

    ![입력된 문자의 이미지입니다.](media/read-text-computer-vision/letter.jpg)

1. 두 번째 이미지의 결과를 검토합니다. 텍스트의 텍스트와 경계 상자를 반환해야 합니다. 시간이 있는 경우 note.jpg** 시도하고 ****receipt.jpg**.

## 정리

더 많은 연습을 수행하지 않으려면 더 이상 필요하지 않은 리소스를 삭제합니다. 이렇게 하면 불필요한 비용이 발생하지 않습니다.

1. Azure Portal을 **[https://portal.azure.com](https://portal.azure.com?azure-portal=true) 열고 만든 리소스가 포함된 리소스 그룹을 선택합니다.**
1. 리소스를 선택하고 삭제**를 선택한 다음 **예(예**)를 선택하여 **확인합니다. 그런 다음 리소스가 삭제됩니다.

## 자세한 정보

이 서비스를 사용하여 수행할 수 있는 작업을 자세히 알아보려면 광학 문자 인식[에 대한 ](https://learn.microsoft.com/azure/ai-services/computer-vision/overview-ocr)Azure AI Vision 설명서를 참조하세요.
