---
lab:
  title: Language Studio에서 대화형 Language Understanding 사용
---

# Language Studio에서 대화형 Language Understanding 사용

점점 더 많은 컴퓨터가 AI를 사용하여 음성 또는 입력된 자연어 명령을 이해할 수 있을 것으로 기대합니다. 예를 들어 홈 자동화 시스템이 "조명 켜기" 또는 "팬 켜기"와 같은 음성 명령을 사용하여 가정에서 디바이스를 제어하도록 할 수 있습니다. AI 기반 디바이스는 이러한 명령을 이해하고 적절한 조치를 취할 수 있습니다.

이 연습에서는 Language Studio를 사용하여 조명 또는 팬과 같은 디바이스에 지침을 보내는 프로젝트를 만들고 테스트합니다. 대화 언어 이해 서비스의 기능을 사용하여 프로젝트를 구성합니다. 

## *Language* 리소스 만들기

**언어** 또는 **Azure AI 서비스** 리소스를 통해 다양한 Azure AI 언어 기능을 사용할 수 있습니다. 언어 리소스만 사용할 수 있는 경우가 있습니다. 아래 연습에서는 **언어** 리소스를 사용합니다. 아직 만들지 않았다면 Azure 구독에서 **Language** 리소스를 만듭니다.

1. 다른 브라우저 탭에서 [https://portal.azure.com](https://portal.azure.com?azure-portal=true)의 Azure Portal을 열고 Azure 구독과 연결된 Microsoft 계정으로 로그인합니다.

1. **&#65291;리소스 만들기** 단추를 클릭하고 *언어 서비스*를 검색합니다. **언어 서비스** 계획 **만들기**를 선택합니다. *추가 기능을 선택**할 수 있는 페이지로 이동됩니다. 기본 선택을 유지하고 **계속하여 리소스 만들기**를 클릭합니다. 

1. **언어 만들기** 페이지에서 다음 설정으로 구성합니다.
    - **구독**: *자신의 Azure 구독*.
    - **리소스 그룹**: *고유한 이름이 있는 리소스 그룹을 선택하거나 생성*합니다.
    - **지역**: *지리적으로 가장 가까운 지역을 선택합니다. 미국 동부에 있는 경우 "미국 동부 2"* 를 사용합니다.
    - **이름**: 고유한 이름을 입력합니다.
    - **가격 책정 계층**: *무료 F0을 사용할 수 없는 경우 무료 F0 또는 S*
    - **이 상자를 선택함으로써 나는 아래의 모든 용어를 읽고 이해했음을 인정합니다.** *선택됨*.

1. **검토 + 만들기**를 선택한 다음 **만들기**를 선택하고 배포가 완료될 때까지 기다립니다.


### Conversational Language Understanding 앱 만들기

Conversational Language Understanding을 통해 자연어 이해를 구현하려면 앱을 만든 다음, 엔터티, 의도, 발화를 추가하여 앱이 실행할 명령을 정의합니다.

1. 새 브라우저 탭에서 [https://language.azure.com](https://language.azure.com?azure-portal=true)의 Language Studio 포털을 열고 Azure 구독과 연결된 Microsoft 계정을 사용하여 로그인합니다.

1. 언어 리소스를 선택하라는 메시지가 표시되면 다음 설정을 선택합니다.
    - **Azure 디렉터리**: *구독이 포함된 Azure 디렉터리입니다*.
    - **Azure 구독**: *사용자의 Azure 구독*.
    - **언어 리소스**: *이전에 만든 언어 리소스.*

   언어 리소스를 선택하라는 메시지가 표시되지 ***않으면*** 구독에 여러 언어 리소스가 있기 때문일 수 있습니다. 이 경우 다음을 수행합니다.
    1. 페이지 상단 표시줄에서 **설정(&#9881;)** 을 선택합니다.
    2. **설정** 페이지에서 **리소스** 탭을 봅니다.
    3. 방금 만든 언어 리소스를 선택하고 **리소스 전환**을 선택합니다.
    4. 페이지 상단에서 **Language Studio**를 선택하여 Language Studio 홈페이지로 돌아갑니다.

1. 포털 위쪽의 **새로 만들기** 메뉴에서 **대화형 언어 이해**을 선택합니다.

1. **기본 정보 입력** 페이지의 **프로젝트 만들기** 대화 상자에 다음 세부 정보를 입력하고 **다음**을 클릭합니다.
    - **이름**: 고유 이름 만들기**
    - **발화 기본 언어**: *English*
    - **프로젝트에서 여러 언어 사용**: 선택하지 마세요.
    - **설명**: `Simple home automation`

    > **팁**: *프로젝트 이름*을 기록해 두면 나중에 사용하게 됩니다.

1. **검토 및 완료** 페이지에서 **만들기**를 선택합니다.

### 의도, 발화 및 엔터티 만들기

의도는 수행하려는 작업입니다. 예를 들어 조명을 켜거나 팬을 끌 수 있습니다.** 이 경우 디바이스 켜기와 디바이스 쓰기의 두 가지 의도를 정의합니다. 각 의도에 대해 의도를 나타내는 데 사용되는 언어의 종류를 나타내는 샘플 *발화*를 지정합니다.

1. **스키마 정의** 창에서 **의도**가 선택되었는지 확인합니다. 그런 다음, **추가**를 선택하고, 이름이 `switch_on`(소문자)인 의도를 추가하고, **의도 추가**를 선택합니다.

    ![빌드 스키마 창의 의도 아래에서 추가를 선택합니다.](media/conversational-language-understanding/build-schema.png)

    ![switch_on 의도를 추가한 다음, 의도 추가를 선택합니다.](media/conversational-language-understanding/add-intent.png)

1. **switch_on** 의도를 선택합니다. **데이터 레이블 지정** 페이지로 이동됩니다. **의도** 드롭다운에서 **switch_on**을 선택합니다. **switch_on** 의도 옆에 발화 `turn the light on`을(를) 입력하고 **Enter**를 눌러 이 발화를 목록에 제출합니다.

    ![발화 아래에 “turn the light on”을 입력하여 학습 집합에 발화를 추가합니다.](media/conversational-language-understanding/add-utterance-on.png)

1. 언어 서비스를 사용하려면 언어 모델을 충분히 학습시키기 위해 각 의도에 대해 5개 이상의 다른 발화 예제가 필요합니다. **switch_on** 의도에 5개의 발화 예제를 더 추가합니다.  
    - `switch on the fan`
    - `put the fan on`
    - `put the light on`
    - `switch on the light`
    - `turn the fan on`

1. 화면 오른쪽의 **학습을 위한 엔터티 레이블 지정** 창에서 **레이블**을 선택한 다음, **엔터티 추가**를 선택합니다. `device`(소문자)를 입력하고, **목록**을 선택하고, **엔터티 추가**를 선택합니다.

    ![학습 패널의 태그 지정 엔터티에서 태그를 선택하여 엔터티를 추가한 다음 엔터티 추가를 선택합니다.](media/conversational-language-understanding/add-entity.png)

    ![엔터티 이름 아래에 device를 입력하고 목록을 선택한 다음, 엔터티 추가를 선택합니다.](media/conversational-language-understanding/add-entity-device.png)

1. ***turn the fan on*** 발화에서 단어 “fan”을 강조 표시합니다. 그런 다음, 표시되는 목록의 엔터티 검색 상자에서 **device**를 선택합니다.

    ![발화에서 단어 fan을 강조 표시하고 device를 선택합니다.](media/conversational-language-understanding/switch-on-entity.png)

1. 모든 발화에 대해 동일한 작업을 수행합니다. 나머지 *fan* 또는 *light* 발화를 **device** 엔터티로 레이블 지정합니다. 작업을 마쳤으면 다음과 같은 발화가 있는지 확인한 후 **변경 내용 저장**을 선택합니다.

    | **의도** | **발화** | **엔터티** |
    | --------------- | ------------------ | ------------------ |
    | switch_on   | Put on the fan      | 디바이스 - 팬 선택** |
    | switch_on   | Put on the light    | 디바이스 - 조명 선택** |
    | switch_on   | Switch on the light | 디바이스 - 조명 선택** |
    | switch_on   | Turn the fan on     | 디바이스 - 팬 선택** |
    | switch_on   | Switch on the fan   | 디바이스 - 팬 선택** |
    | switch_on   | Turn the light on   | 디바이스 - 조명 선택** |

    ![완료되면 변경 내용 저장을 선택합니다.](media/conversational-language-understanding/save-changes.png) 

1. 왼쪽 창에서 **스키마 정의**를 선택하고 **switch_on** 의도가 나열되는지 확인합니다. 그런 다음 **추가**를 선택하고 이름이 `switch_off`인 새 의도를 추가합니다(소문자).

    ![스키마 빌드 화면으로 돌아가서 switch_off 의도를 추가합니다.](media/conversational-language-understanding/add-switch-off.png) 

1. **switch_off** 의도를 선택합니다. **데이터 레이블 지정** 페이지로 이동됩니다. **의도** 드롭다운에서 **switch_off**를 선택합니다. **switch_off** 의도 옆에 `turn the light off` 발화를 추가합니다.

1. **switch_off** 의도에 5개의 발화 예제를 더 추가합니다.
    - `switch off the fan`
    - `put the fan off`
    - `put the light off`
    - `turn off the light`
    - `switch the fan off`

1. 단어 *light* 또는 *fan*을 **device** 엔터티로 레이블 지정합니다. 작업을 마쳤으면 다음과 같은 발화가 있는지 확인한 후 **변경 내용 저장**을 선택합니다.  

    | **의도** | **발화** | **엔터티** | 
    | --------------- | ------------------ | ------------------ |
    | switch_off   | Put the fan off    | 디바이스 - 팬 선택** | 
    | switch_off   | Put the light off  | 디바이스 - 조명 선택** |
    | switch_off   | Turn off the light | 디바이스 - 조명 선택** |
    | switch_off   | Switch the fan off | 디바이스 - 팬 선택** |
    | switch_off   | Switch off the fan | 디바이스 - 팬 선택** |
    | switch_off   | Turn the light off | 디바이스 - 조명 선택** |

### 모델 학습

이제 앱에 Conversational Language 모델을 학습하기 위해 정의한 의도 및 엔터티를 사용할 준비가 되었습니다.

1. Language Studio의 왼쪽에서 **학습 작업**을 선택한 다음, **학습 작업 시작**을 선택합니다. 다음 설정을 사용합니다.
    - **새 모델 학습**: 선택하고 모델 이름을 선택합니다.
    - **학습 모드**: 표준 학습(무료)
    - **데이터 분할**: 학습 데이터에서 테스트 세트 자동 분할 선택, 기본 백분율 유지**
    - 페이지 아래쪽에서 **학습**을 선택합니다.

1. 학습이 완료되기를 기다립니다.

### 모델 배포 및 테스트

클라이언트 애플리케이션에서 학습된 모델을 사용하려면 클라이언트 애플리케이션이 새 발화를 보낼 수 있는 엔드포인트로 배포해야 합니다. 그러면 의도 및 엔터티를 예측할 수 있습니다.

1. Language Studio의 왼쪽에서 **모델 배포**를 선택합니다.

1. 모델 이름을 선택하고 **배포 추가**를 선택합니다. 사용할 설정
    - **기존 배포 이름 만들기 또는 선택**: 새 배포 이름 만들기 선택, 고유한 이름 추가**
    - **배포 이름에 학습된 모델 할당**: 학습된 모델의 이름 선택**
    - **배포**를 선택합니다.

    > **팁**: *배포 이름*을 적어 두면 나중에 사용하게 됩니다. 

1. 모델이 배포되면 페이지 왼쪽에서 **배포 테스트**를 선택한 다음, **배포 이름** 아래에서 배포된 모델을 선택합니다.

1. 다음 텍스트를 입력한 후 **테스트 실행**을 클릭합니다.

    `switch the light on`

    ![배포된 모델을 선택한 다음, 텍스트를 입력하고 테스트 실행을 선택하여 모델을 테스트합니다.](media/conversational-language-understanding/test-model.png) 

    반환되는 결과를 검토합니다. 예측된 의도(**switch_on**) 및 예측된 엔터티(**device**)에 대해 모델이 계산한 확률을 나타내는 신뢰도 점수와 함께 예측된 의도 및 엔터티가 포함되는 것을 알 수 있습니다. JSON 탭은 각 잠재적 의도에 대한 비교 신뢰도를 표시합니다(신뢰도 점수가 가장 높은 것이 예측된 의도임).

1. 텍스트 상자를 지우고 텍스트 입력 또는 텍스트 문서 업로드에서 다음 발화로 모델을 테스트합니다.**
    - `turn off the fan`
    - `put the light on`
    - `put the fan off`

이제 대화 언어 프로젝트를 성공적으로 구성하고 엔터티, 의도 및 발화를 정의했습니다. Language Studio에서 모델을 학습하고 배포하는 방법을 알아보았습니다. 그리고 정의한 발화와 명시적으로 정의하지 않았지만 모델이 결정할 수 있는 일부 발화로 사용해 봤습니다.

> **참고**: 대화 언어 이해는 입력의 의도를 해석하는 인텔리전스를 제공하며 조명 또는 팬 켜기와 같은 작업을 수행하지 않습니다. 개발자는 대화 언어 이해 모델을 사용하여 사용자의 의도를 확인한 다음 적절한 작업을 자동화하는 애플리케이션을 빌드해야 합니다.

## 정리

더 이상 연습할 생각이 없다면 더 이상 필요하지 않은 리소스를 삭제합니다. 이렇게 하면 불필요한 비용이 발생하는 것을 방지할 수 있습니다.

1. [Azure Portal]( https://portal.azure.com)을 열고 만든 리소스가 포함된 리소스 그룹을 선택합니다. 1.리소스를 선택하고 **삭제**를 선택한 다음 **예**를 선택하여 확인합니다. 그러면 리소스가 삭제됩니다.

## 자세한 정보

이 간단한 앱은 언어 서비스의 대화형 언어 이해 기능 중 일부만 보여 줍니다. 이 서비스를 사용하여 수행할 수 있는 작업을 자세히 알아보려면 [Conversational Language Understanding 페이지](https://docs.microsoft.com/azure/cognitive-services/language-service/conversational-language-understanding/overview)를 참조하세요.
