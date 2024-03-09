---
lab:
  title: Vision Studio에서 얼굴 감지
---

# Vision Studio에서 얼굴 감지

비전 솔루션에는 사람의 얼굴을 감지할 수 있는 AI가 필요한 경우가 많습니다. 가상의 소매 회사 Northwind Traders가 상점에서 고객이 서 있는 위치를 파악하여 고객을 가장 잘 지원하려고 한다고 가정합니다. 이를 수행하는 한 가지 방법은 이미지에 얼굴이 있는지 확인하고, 있는 경우 해당 위치를 표시하는 경계 상자 좌표를 반환하는 것입니다.

Azure AI Face 서비스의 얼굴 감지 기능을 테스트하려면 [Azure Vision Studio](https://portal.vision.cognitive.azure.com/)를 사용합니다. 코드를 작성할 필요 없이 Azure AI 비전 기능을 탐색할 수 있는 UI 기반 플랫폼입니다.

## Azure AI 서비스 리소스를 생성합니다

**Azure AI 서비스** 다중 서비스 리소스와 함께 Azure AI Face 서비스를 사용할 수 있습니다. 아직 만들지 않았다면 Azure 구독에서 **Azure AI 언어 서비스** 리소스를 만듭니다.

1. 다른 브라우저 탭에서 [https://portal.azure.com](https://portal.azure.com?azure-portal=true)의 Azure Portal을 열고 Azure 구독과 연결된 Microsoft 계정으로 로그인합니다.

1. **65291을 클릭합니다. 리소스** 단추를 만들고 Azure AI 서비스를 검색*합니다*. Azure AI 서비스 계획 만들기****를** 선택합니다**. 페이지로 이동하여 Azure AI 서비스 리소스를 만듭니다. 다음 설정을 사용하여 PuTTY를 구성합니다.
    - **구독**: *자신의 Azure 구독*.
    - **리소스 그룹**: *고유한 이름이 있는 리소스 그룹을 선택하거나 생성*합니다.
    - **지역**: 미국 동부
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

## Vision Studio에서 얼굴 감지 

1. 웹브라우저에서 [https://portal.vision.cognitive.azure.com](https://portal.vision.cognitive.azure.com?azure-portal=true)의 **Vision Studio**로 이동합니다.

1. **Vision 시작** 방문 페이지에서 **얼굴** 탭을 선택한 다음 **이미지 타일에서 얼굴 감지**를 선택합니다.

1. **시도** 부제목 아래에서 확인란의 내용을 읽고 선택하여 리소스 사용 정책을 승인합니다.  

1. 각 샘플 이미지를 선택하고 반환되는 얼굴 감지 데이터를 관찰합니다.

1. 이제 일부 이미지를 사용해 보겠습니다. [**https://aka.ms/mslearn-detect-faces**](https://aka.ms/mslearn-detect-faces)을(를) 선택하여 **detect-faces.zip**을 다운로드합니다. 그런 다음 컴퓨터에서 폴더를 엽니다.

1. 다음 이미지를 포함하는 **store-camera-1.jpg**라는 파일을 찾습니다.

    ![스토어에 있는 사람들의 이미지입니다.](./media/create-face-solutions/store-camera-1.jpg)

1. **store-camera-1.jpg**를 업로드하고 반환되는 얼굴 감지 세부 정보를 검토합니다.

1. 다음 이미지를 포함하는 **store-camera-2.jpg**라는 파일을 찾습니다.

    ![스토어에 있는 더 많은 사람들의 이미지입니다.](./media/create-face-solutions/store-camera-2.jpg)

1. **store-camera-2.jpg**를 업로드하고 반환되는 얼굴 감지 세부 정보를 검토합니다.

1. 다음 이미지를 포함하는 **store-camera-3.jpg**라는 파일을 찾습니다.

    ![식물이 얼굴을 가리고 있는 상점에 있는 사람들의 이미지입니다.](./media/create-face-solutions/store-camera-3.jpg)

1. **store-camera-3.jpg**를 업로드하고 반환되는 얼굴 감지 세부 정보를 검토합니다. Azure AI Face가 가려진 얼굴을 어떻게 감지하지 못했는지 확인합니다.

이 연습에서는 Azure AI Services가 이미지에서 얼굴을 감지하는 방법을 살펴보았습니다. 시간이 있는 경우 샘플 이미지 또는 일부 이미지를 자유롭게 사용해 보세요.

## 정리

더 이상 연습할 생각이 없다면 더 이상 필요하지 않은 리소스를 삭제합니다. 이렇게 하면 불필요한 비용이 발생하는 것을 방지할 수 있습니다.

1. [https://portal.azure.com](https://portal.azure.com?azure-portal=true)에서 **Azure Portal**을 열고 만든 리소스가 포함된 리소스 그룹을 선택합니다.
1. 리소스를 선택하고 **삭제**를 선택한 다음 **예**를 선택하여 확인합니다. 그러면 리소스가 삭제됩니다.

## 자세한 정보

이 서비스로 수행할 수 있는 작업에 대해 자세히 알아보려면 [Azure AI Face 서비스 페이지](https://learn.microsoft.com/azure/ai-services/computer-vision/overview-identity)를 참조하세요.
