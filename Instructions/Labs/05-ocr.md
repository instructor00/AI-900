# Vision Studio에서 텍스트 읽기

이 연습에서는 Azure AI 서비스를 사용하여 Azure AI 비전의 광학 인식 기능을 살펴봅니다. Vision Studio를 사용하여 코드를 작성할 필요 없이 이미지에서 텍스트를 추출하는 실험을 합니다.

일반적인 Computer Vision 과제는 이미지에 포함된 텍스트를 검색하고 해석하는 것입니다. 이를 OCR(광학 인식)이라고 합니다. 이 연습에서는 Azure AI 비전 서비스가 포함된 Azure AI 서비스 리소스를 사용합니다. 그런 다음 Vision Studio를 사용하여 다양한 형식의 이미지로 OCR을 시험해 봅니다.

## Azure AI 서비스 리소스를 생성합니다

**Azure AI 서비스** 다중 서비스 리소스와 함께 Azure AI 비전의 OCR 기능을 사용할 수 있습니다. 아직 만들지 않았다면 Azure 구독에서 **Azure AI 언어 서비스** 리소스를 만듭니다.

1. 다른 브라우저 탭에서 [https://portal.azure.com](https://portal.azure.com?azure-portal=true)의 **Azure Portal**을 열고 Azure 구독과 연결된 Microsoft 계정으로 로그인합니다.

1. **65291을 클릭합니다. 리소스** 단추를 만들고 Azure AI 서비스를 검색*합니다*. Azure AI 서비스 계획 만들기****를** 선택합니다**. 페이지로 이동하여 Azure AI 서비스 리소스를 만듭니다. 다음 설정을 사용하여 PuTTY를 구성합니다.
    - **구독**: *자신의 Azure 구독*.
    - **리소스 그룹**: *고유한 이름이 있는 리소스 그룹을 선택하거나 생성*합니다.
    - **지역**: *지리적으로 가장 가까운 지역을 선택합니다. 미국 동부에 있는 경우 "미국 동부 2"를 사용합니다*.
    - **이름**: 고유한 이름을 입력합니다.
    - **가격 책정 계층**: *표준 S0.*
    - **이 상자를 선택함으로써 나는 아래의 모든 용어를 읽고 이해했음을 인정합니다.** *선택됨*.

1. **검토 + 만들기**를 선택한 다음 **만들기**를 선택하고 배포가 완료될 때까지 기다립니다.

## Azure AI 서비스 리소스를 Vision Studio에 연결

그런 다음 위에서 프로비전한 Azure AI 서비스 리소스를 Vision Studio에 연결합니다.

1. 다른 브라우저 탭에서 [https://portal.vision.cognitive.azure.com](https://portal.vision.cognitive.azure.com?azure-portal=true)의 **Vision Studio**로 이동합니다.

1. 계정으로 로그인하고 Azure AI 서비스 리소스를 만든 디렉터리와 동일한 디렉터리를 사용하고 있는지 확인합니다.

1. Vision Studio 홈페이지의 **Vision 시작** 제목 아래에서 **모든 리소스 보기**를 선택합니다.

    ![모든 리소스 보기 링크는 Vision Studio에서 Vision 시작 아래에 강조 표시되어 있습니다.](./media/analyze-images-vision/vision-resources.png)

1. **작업할 리소스 선택** 페이지에서 목록에서 위에서 만든 리소스 위에 마우스 커서를 가리키고 리소스 이름 왼쪽에 있는 확인란을 선택한 다음 **기본 리소스로 선택**을 선택합니다.

    > **참고**: 리소스가 목록에 없으면 페이지를 **새로 고침**해야 할 수도 있습니다.

    ![cog-ms-learn-vision-SUFFIX Cognitive Services 리소스가 강조 표시되고 선택된 상태로 작업할 리소스 선택 대화 상자가 표시됩니다. 기본 리소스로 선택 단추가 강조 표시됩니다.](./media/analyze-images-vision/default-resource.png)

1. 화면 오른쪽 상단의 "x"를 선택하여 설정 페이지를 닫습니다.

## Vision Studio의 이미지에서 텍스트 추출
    
1. 웹브라우저에서 [https://portal.vision.cognitive.azure.com](https://portal.vision.cognitive.azure.com?azure-portal=true)의 **Vision Studio**로 이동합니다.

1. **Vision 시작** 방문 페이지에서 **광학 인식**을 선택한 다음 **이미지에서 텍스트 추출** 타일을 선택합니다.

1. **시도** 부제목 아래에서 확인란의 내용을 읽고 선택하여 리소스 사용 정책을 승인합니다.  

1. [**https://aka.ms/mslearn-ocr-images**](https://aka.ms/mslearn-ocr-images)를 선택하여 **ocr-images.zip**을 다운로드합니다. 그런 다음 폴더를 엽니다.

1. 포털에서 **파일 찾아보기**를 선택하고 **ocr-images.zip**을 다운로드한 컴퓨터의 폴더로 이동합니다. **advert.jpg**를 선택하고 **열기**를 선택합니다.

1. 이제 반환된 내용을 검토합니다.
    - **검색된 특성**에서는 이미지에 있는 모든 텍스트가 영역, 선, 단어의 계층 구조로 구성됩니다.
    - 이미지에서 텍스트의 위치는 다음과 같이 경계 상자로 표시됩니다.

    ![윤곽선이 있는 이미지의 텍스트 이미지.](media/read-text-computer-vision/advert-bounding-boxes.jpg)

1. 이제 다른 이미지를 시도해 볼 수 있습니다. **파일 찾아보기**를 선택하고 GitHub에서 파일을 저장한 폴더로 이동합니다. **letter.jpg**를 선택합니다.

    ![입력된 문자의 이미지입니다.](media/read-text-computer-vision/letter.jpg)

1. 두 번째 이미지의 결과를 검토합니다. 텍스트와 텍스트의 경계 상자를 반환해야 합니다. **note.jpg** 및 **receipt.jpg**를 검토해 보세요.

## 정리

실습이 완료되면  더 이상 필요하지 않은 리소스를 삭제합니다. 이렇게 하면 불필요한 비용이 발생하는 것을 방지할 수 있습니다.

1. [https://portal.azure.com](https://portal.azure.com?azure-portal=true)에서 **Azure Portal**을 열고 만든 리소스가 포함된 리소스 그룹을 선택합니다.
1. 리소스를 선택하고 **삭제**를 선택한 다음 **예**를 선택하여 확인합니다. 그러면 리소스가 삭제됩니다.

## 자세한 정보

이 서비스로 수행할 수 있는 작업에 대해 자세히 알아보려면 [광학 인식](https://learn.microsoft.com/azure/ai-services/computer-vision/overview-ocr)에 대한 Azure AI 비전 설명서를 참조하세요.
