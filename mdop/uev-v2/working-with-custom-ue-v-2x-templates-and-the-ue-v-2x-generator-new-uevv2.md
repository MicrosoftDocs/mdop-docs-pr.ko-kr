---
title: 사용자 지정 UE-V 2. x 템플릿 및 UE-V 2 .x 생성기 사용
description: 사용자 지정 UE-V 2. x 템플릿 및 UE-V 2 .x 생성기 사용
author: dansimp
ms.assetid: f0bb4920-0132-472c-a564-abf06a884275
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: a8d863896e4ccfa92161f8a8f5e2b8955f139872
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/26/2020
ms.locfileid: "10819293"
---
# 사용자 지정 UE-V 2. x 템플릿 및 UE-V 2 .x 생성기 사용


사용자 컴퓨터 간에 응용 프로그램 설정을 동기화 하려면 Microsoft 사용자 환경 가상화 (UE-V) 2.0, 2.1 및 2.1 SP1에서 *설정 위치 템플릿을*사용 합니다. 일부 설정 위치 템플릿은 사용자 환경 가상화에 포함 되어 있습니다. UE-V 생성기를 사용 하 여 사용자 지정 설정 위치 템플릿을 만들거나 편집 하거나 유효성을 검사할 수도 있습니다.

UE-V 생성기는 Windows 데스크톱 응용 프로그램을 모니터링 하 여 응용 프로그램에서 해당 설정을 저장 하는 위치를 검색 하 고 캡처합니다. 모니터링 되는 응용 프로그램은 데스크톱 응용 프로그램 이어야 합니다. UE-V 생성기는 다음 응용 프로그램 종류에 대 한 설정 위치 템플릿을 만들 수 없습니다.

-   가상화 된 응용 프로그램

-   터미널 서비스를 통해 제공 되는 응용 프로그램

-   Java 응용 프로그램

-   Windows 앱  

이 항목

**표준 및 비표준 설정 위치:** UE-V 생성기는 응용 프로그램이 설정 정보를 저장 하는 데 사용 하는 설정 파일 및 레지스트리 설정을 검색 하는 위치를 식별 하는 데 도움이 됩니다. 생성기는 표준 사용자가 액세스할 수 있는 위치 에서만 설정을 검색 합니다. 다른 위치에 저장 된 설정은 제외 됩니다. 검색 된 설정은 **표준** 및 비표준 **의**두 범주로 그룹화 됩니다. 동기화에는 표준 설정이 권장 되며 UE-V를 통해 쉽게 캡처 및 적용할 수 있습니다. 비 표준 설정은 잠재적으로 설정을 동기화 할 수 있지만, UE-V를 사용 하는 규칙 때문에 이러한 설정이 일관 되지 않거나 dependably 설정이 동기화 되지 않을 수 있습니다. 이러한 설정은 임시 파일에 따라 달라 지 며, 동기화 되지 않는 경우에는 그렇지 않거나, 도움이 되지 않을 수 있습니다. 이러한 설정 위치는 UE-V 생성기에서 제공 됩니다. 대/소문자를 구분 하 여 포함 하거나 제외 하도록 선택할 수 있습니다.

UE-V 생성기가 검색 프로세스의 일부로 응용 프로그램을 엽니다. 생성자는 다음 위치에서 설정을 캡처할 수 있습니다.

-   **레지스트리 설정** – **HKEY \ _CURRENT \ _USER** 아래의 레지스트리 위치

-   **응용 프로그램 설정 파일** – \\ **사용자** \\ [사용자 이름 \ \ **AppData**  \\  **로밍** '에 저장 되는 파일

UE-V 생성기는 일반적으로 응용 프로그램 소프트웨어 파일을 저장 하지만 사용자 컴퓨터와 환경 간에는 동기화 되지 않는 위치를 제외 합니다. UE-V 생성기는 이러한 위치를 제외 합니다. 제외 된 위치는 다음과 같습니다.

-   HKEY \ _CURRENT \ _USER 로그온 한 사용자가 값을 쓸 수 없는 레지스트리 키 및 파일

-   HKEY _CURRENT \ _USER Windows 운영 체제의 핵심 기능과 연결 된 레지스트리 키 및 파일

-   HKEY \ _LOCAL \ _MACHINE hive에 있는 모든 레지스트리 키 (관리자 권한이 필요 하며 UAC (사용자 계정 컨트롤) 계약을 설정 해야 할 수 있음)

-   관리자 권한이 필요 하며 UAC 규약을 설정 해야 할 수 있는 Program Files 디렉터리에 있는 파일

-   사용자 \\ [사용자 이름 \] \\ AppData에 있는 파일에는 다음이 허용 됩니다.

-   관리자 권한이 필요 하며 UAC 계약을 설정 해야 하는 경우% Systemroot%에 있는 Windows 운영 체제 파일

이러한 위치에 저장 된 레지스트리 키 및 파일이 응용 프로그램 설정을 동기화 하는 데 필요한 경우 템플릿 만들기 프로세스 중에 제외 된 위치를 설정 위치 템플릿에 수동으로 추가할 수 있습니다 (HKEY \ _LOCAL \ _MACHINE hive의 레지스트리 항목 제외).

## <a href="" id="edit"></a>UE-V 생성기를 사용 하 여 설정 위치 템플릿 편집


UE-V 생성기를 사용 하 여 설정 위치 템플릿을 편집 합니다. UE-V 생성기를 사용 하 여 수정 된 설정이 서식 파일에 추가 되 면 해당 서식 파일의 버전 정보가 자동으로 업데이트 되어 엔터프라이즈에 배포 된 기존 서식 파일이 제대로 업데이트 되도록 합니다.

**참고**  Ue-v 2 생성기를 사용 하 여 UE-V 1.0 서식 파일을 편집 하는 경우에는 템플릿이 UE-V 2 템플릿으로 자동 변환 됩니다. UE-V 1.0 에이전트는 편집 된 템플릿을 더 이상 사용할 수 없습니다.

 

**UE-V 생성기를 사용 하 여 UE-V 설정 위치 템플릿을 편집 하려면**

1.  **시작**을 클릭 하 고 **모든 프로그램**, **microsoft 사용자 환경 가상화**를 차례로 클릭 한 다음 **microsoft 사용자 환경 가상화 생성기**를 클릭 합니다.

2.  **설정 위치 서식 파일 편집을**클릭 합니다.

3.  최근에 사용한 서식 파일 목록에서 편집할 서식 파일을 선택 합니다. 또는 **찾아보기를** 클릭 하 여 설정 템플릿 파일을 검색 합니다. **Next**(다음)를 클릭하여 계속합니다.

4.  설정 템플릿의 **속성**, **레지스트리** 위치 및 **파일** 위치를 검토 합니다. 필요에 따라 편집 합니다.

    -   **속성** 탭에서 다음 속성을 보고 편집할 수 있습니다.

        -   **응용 프로그램 이름**: 프로그램 파일 속성에 대 한 설명으로 작성 되는 응용 프로그램 이름입니다.

        -   **프로그램 이름**: 프로그램 파일 속성에서 가져온 프로그램의 이름입니다. 일반적으로이 이름은 .exe 파일 이름 확장명을 갖습니다.

        -   **제품 버전**: 응용 프로그램의 .exe 파일에 대 한 제품 버전 번호입니다. 이 속성은 **파일 버전과**함께 설정 위치 템플릿에서 대상으로 하는 응용 프로그램을 확인 하는 데 도움이 됩니다. 이 속성은 주 버전 번호를 받아들입니다. 이 속성이 비어 있으면 설정 위치 템플릿이 모든 제품 버전에 적용 됩니다.

        -   **파일 버전**: 응용 프로그램의 .exe 파일에 대 한 파일 버전 번호입니다. 이 속성은 **제품 버전과**함께 설정 위치 템플릿에서 대상으로 하는 응용 프로그램을 결정 하는 데 도움이 됩니다. 이 속성은 주 버전 번호를 받아들입니다. 이 속성이 비어 있으면 설정 위치 템플릿이 모든 버전의 프로그램에 적용 됩니다.

        -   **서식 파일 만든이 이름** (선택 사항): 설정 서식 파일 작성자의 이름입니다.

        -   **서식 파일 저자 전자 메일** (선택 사항): 설정 위치 템플릿 작성자의 전자 메일 주소입니다.

    -   **레지스트리** 탭에는 설정 위치 템플릿에 포함 된 레지스트리 위치의 **키** 와 **범위가** 나열 됩니다. **작업** 드롭다운 메뉴를 사용 하 여 레지스트리 위치를 편집할 수 있습니다. 작업 메뉴에서 새 키를 추가 하 고, 기존 키의 이름 또는 범위를 편집 하 고, 키를 삭제 하 고, 키가 있는 레지스트리를 찾아볼 수 있습니다. 레지스트리의 범위를 정의할 때 **모든 설정** 범위를 사용 하 여 지정 된 키 아래에 모든 레지스트리 설정을 포함할 수 있습니다. **모든 설정** 및 **하위 키** 를 사용 하 여 지정 된 키, 하위 키 및 하위 키 설정의 모든 레지스트리 설정을 포함 합니다.

    -   **파일** 탭에는 설정 위치 템플릿에 포함 된 파일 위치의 파일 경로 및 파일 마스크가 나열 됩니다. **작업** 드롭다운 메뉴를 사용 하 여 파일 위치를 편집할 수 있습니다. 파일 위치에 대 한 **작업** 메뉴에서 새 파일 또는 폴더 위치를 추가 하 고, 기존 파일 또는 폴더의 범위를 편집 하 고, 파일이 나 폴더를 삭제 하 고, Windows 탐색기에서 선택한 위치를 열 수 있습니다. 지정 된 폴더의 모든 파일을 포함 하려면 파일 마스크를 비워 둡니다.

5.  **저장** 을 클릭 하 여 설정 위치 템플릿에 대 한 변경 내용을 저장 합니다.

6.  **닫기를** 클릭 하 여 설정 템플릿 마법사를 닫습니다. UE-V 생성기 응용 프로그램을 종료 합니다.

    응용 프로그램의 설정 위치 템플릿을 편집한 후에는 서식 파일을 테스트 해야 합니다. 엔터프라이즈에서 프로덕션에 배치 하기 전에 먼저 랩 환경에서 수정 된 설정 위치 템플릿을 배포 합니다.

**설정 위치 템플릿을 수동으로 편집 하는 방법**

1.  설정 위치 템플릿 .xml 파일의 로컬 복사본을 만듭니다. UE-V 설정 위치 템플릿은 응용 프로그램에서 설정 값을 저장 하는 위치를 식별 하는 .xml 파일입니다.

    **참고**  서식 파일 **ID**때문에 설정 위치 템플릿이 고유 합니다. 서식 파일을 복사 하 고 .xml 파일의 이름을 바꾸면 UE-V 파일에서 서식 파일 **ID** 태그를 읽어 .xml 파일의 이름이 아닌 이름을 확인 하기 때문에 서식 파일 등록이 실패 합니다. 또한 UE-V는 변경 내용이 있는지 확인 하기 위해 **버전** 번호를 읽습니다. 버전 번호가 더 상위 이면 UE-V가 서식 파일을 업데이트 합니다.

     

2.  XML 편집기를 사용 하 여 설정 위치 템플릿 파일을 엽니다.

3.  설정 위치 템플릿 파일을 편집 합니다. 모든 변경 내용은 [Settingslocationtempate](https://technet.microsoft.com/library/dn763947.aspx)에 정의 된 ue-v 스키마 파일을 준수 해야 합니다. 기본적으로 .xsd 파일의 복사본은 \\ProgramData\\Microsoft\\UEV\\Templates.에 있습니다.

4.  설정 위치 템플릿의 **버전** 번호를 늘립니다.

5.  설정 위치 템플릿 파일을 저장 한 다음 XML 편집기를 닫습니다.

6.  UE-V 생성기를 사용 하 여 수정 된 설정 위치 템플릿 파일의 유효성을 검사 합니다.

7.  클라이언트 컴퓨터 간 설정을 동기화 하려면 먼저 편집 된 UE-V 설정 위치 템플릿을 등록 해야 합니다. 템플릿을 등록 하려면 Windows PowerShell을 열고 다음 cmdlet을 실행 합니다 `update-uevtemplate [templatefilename]` . 그런 다음 설정 저장소 카탈로그에 파일을 복사할 수 있습니다. 그러면 사용자의 컴퓨터에 대 한 UE-V Agent가 예약 된 작업에서 일정 대로 업데이트 되어야 합니다.

## <a href="" id="validate"></a>UE-V 생성기를 사용 하 여 설정 위치 템플릿 유효성 검사


UE-V 생성기를 사용 하지 않고 XML 편집기에서 설정 위치 템플릿을 만들거나 편집할 수 있습니다. 이렇게 하는 경우 UE-V 생성기를 사용 하 여 새 XML 또는 수정 된 XML이 서식 파일에 대해 정의 된 스키마와 일치 하는지 확인할 수 있습니다.

**UE-V 생성기를 사용 하 여 UE-V 설정 위치 템플릿의 유효성을 검사 하려면**

1.  **시작**을 클릭 하 고 **모든 프로그램**을 가리킨 다음 **microsoft 사용자 환경 가상화**를 클릭 하 고 **microsoft 사용자 환경 가상화 생성기**를 클릭 합니다.

2.  **설정 위치 서식 파일의 유효성 검사를**클릭 합니다.

3.  최근에 사용한 서식 파일 목록에서 편집할 서식 파일을 선택 합니다. 또는 설정 템플릿 파일을 **탐색할** 수 있습니다. **Next**(다음)를 클릭하여 계속합니다.

4.  **확인** 을 클릭 하 여 계속 합니다.

5.  **닫기를** 클릭 하 여 설정 템플릿 마법사를 닫습니다. UE-V 생성기 응용 프로그램을 종료 합니다.

    응용 프로그램에 대 한 설정 위치 템플릿의 유효성을 검사 한 후에는 서식 파일을 테스트 해야 합니다. 엔터프라이즈의 프로덕션 환경에 배치 하기 전에 먼저 템플릿을 랩 환경에 배포 합니다.

## <a href="" id="share"></a>서식 파일 갤러리를 사용 하 여 설정 위치 서식 파일 공유


Microsoft UE-V (User Experience Virtualization) 2.0 서식 파일 갤러리를 통해 관리자는 UE-V 설정 위치 템플릿을 공유할 수 있습니다. 갤러리에서 다른 사용자가 사용할 수 있도록 설정 위치 템플릿을 업로드 하 고 다른 사용자가 만든 서식 파일을 다운로드할 수 있습니다. UE-V 서식 파일 갤러리는 [Microsoft TechNet에 있습니다.](https://go.microsoft.com/fwlink/p/?LinkId=246589)

UE-V 템플릿 갤러리에서 설정 위치 템플릿을 공유 하기 전에 개인 정보나 회사 정보가 포함 되어 있지 않은지 확인 합니다. XML 뷰어를 사용 하 여 설정 위치 템플릿 파일의 내용을 열고 볼 수 있습니다. 서식 파일을 회사 외부의 모든 사용자와 공유 하기 전에 다음 서식 파일 값을 검토 해야 합니다.

-   서식 파일 작성자 이름-서식 파일 작성자 이름에 대해 식별 되지 않는 일반 이름을 지정 하거나 템플릿에서이 데이터를 제외 합니다.

-   서식 파일 저자 전자 메일 – 식별이 불가능 한 일반 서식 파일 작성 전자 메일을 지정 하거나 템플릿에서이 데이터를 제외 합니다.

UE-V 갤러리에서 다운로드 한 설정 위치 서식 파일을 배포 하기 전에 먼저 템플릿을 테스트 하 여 응용 프로그램 설정이 테스트 환경에서 올바르게 설정 되어 있는지 확인 해야 합니다.






## 관련 항목


[UE-V on-V 2. x 관리](administering-ue-v-2x-new-uevv2.md)

[사용자 지정 응용 프로그램에 대 한 UE-V 2. x 배포](deploy-ue-v-2x-for-custom-applications-new-uevv2.md)

 

 




