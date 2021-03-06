---
title: 패키지 가속기를 만드는 방법
description: 패키지 가속기를 만드는 방법
author: dansimp
ms.assetid: b61f3581-7933-443e-b872-a96bed9ff8d7
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 6893f2e9bb9db473d285026015c3399fb0074015
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/26/2020
ms.locfileid: "10814265"
---
# 패키지 가속기를 만드는 방법


App-v 5.1 패키지 가속기가 새 가상 응용 프로그램 패키지를 자동으로 생성 합니다.

**참고**  
PowerShell을 사용 하 여 패키지 가속기를 만들 수 있습니다. 자세한 내용은 [PowerShell을 사용 하 여 패키지 가속기를 만드는 방법을](how-to-create-a-package-accelerator-by-using-powershell51.md)참조 하세요.



패키지 가속기를 만들려면 다음 절차를 사용 합니다.

**중요**  
패키지 가속기에는 암호와 사용자 관련 정보가 포함 될 수 있습니다. 따라서 패키지 가속기 및 관련 설치 미디어를 안전한 위치에 저장 해야 하며, 앱을 만든 후에는 패키지 가속기를 만들고 디지털 서명을 하 여 App-v 5.1 패키지 가속기가 적용 될 때 게시자를 확인할 수 있도록 해야 합니다.



**중요**  
다음 절차를 시작 하기 전에 다음을 수행 해야 합니다.

-   시퀀서를 실행 하는 컴퓨터에 패키지 가속기를 로컬로 만드는 데 사용할 가상 응용 프로그램 패키지를 복사 합니다.

-   가상 응용 프로그램 패키지와 연결 된 필요한 모든 설치 파일을 sequencer를 실행 하는 컴퓨터에 복사 합니다.



**패키지 가속기를 만들려면**

1.  **중요**  
    App-v 5.1 Sequencer는 패키지 가속기를 만드는 데 사용 하는 소프트웨어 응용 프로그램에 대 한 라이선스 권한을 부여 하지 않습니다. 사용 중인 응용 프로그램에 대 한 모든 최종 사용자 사용권 조항을 준수 해야 합니다. 소프트웨어 응용 프로그램의 사용 조건에 따라 App-v 5.1 Sequencer를 사용 하 여 패키지 가속기를 만들 수 있는지를 확인 하는 것은 사용자의 책임입니다.



~~~
To start the App-V 5.1 sequencer, on the computer that is running the sequencer, click **Start** / **All Programs** / **Microsoft Application Virtualization** / **Microsoft Application Virtualization Sequencer**.
~~~

2. App-v 5.1 **패키지 가속기 만들기** 마법사를 시작 하려면 app-v 5.1 sequencer 콘솔에서 **도구**  /  **바로 연결 만들기**를 클릭 합니다.

3. **패키지 선택** 페이지에서 패키지 가속기를 만드는 데 사용할 기존 가상 응용 프로그램 패키지를 지정 하려면 **찾아보기를**클릭 하 고 기존 가상 응용 프로그램 패키지 (appv 파일)를 찾습니다.

   **팁**  
   시퀀서를 실행 하는 컴퓨터에 로컬로 사용할 가상 응용 프로그램 패키지와 연결 된 파일을 복사 합니다.



~~~
Click **Next**.
~~~

4. **설치 파일** 페이지에서 원래 가상 응용 프로그램 패키지를 만드는 데 사용한 설치 파일을 포함 하는 폴더를 지정 하려면 **찾아보기를**클릭 한 다음 설치 파일이 포함 된 디렉터리를 선택 합니다.

   **팁**  
   Sequencer를 실행 하는 컴퓨터에 필요한 설치 파일이 들어 있는 폴더를 복사 합니다.



5. Sequencer를 실행 하는 컴퓨터에 응용 프로그램이 이미 설치 되어 있는 경우 설치 파일을 지정 하려면 **로컬 시스템에 설치 된 파일**을 선택 합니다. 이 옵션을 사용 하려면 응용 프로그램이 기본 설치 위치에 이미 설치 되어 있어야 합니다.

6. **수집 정보** 페이지에서이 마법사의 **설치 파일** 페이지에 지정 된 위치에서 찾을 수 없는 파일을 검토 합니다. 파일이 표시 되지 않으면 **이 파일 제거**를 선택 하 고 **다음**을 클릭 합니다. 파일이 필요한 경우 **이전** 을 클릭 하 고 필요한 파일을 **설치 파일** 페이지에 지정 된 디렉터리에 복사 합니다.

   **참고**  
   필요 없는 파일을 제거 하거나, **이전** 을 클릭 하 고 필요한 파일을 찾아 마법사의 다음 페이지로 이동 해야 합니다.



7. **파일 선택** 페이지에서 검색 된 파일을 신중 하 게 검토 하 고 패키지 가속기에서 제거 해야 하는 파일의 선택을 취소 합니다. 응용 프로그램이 성공적으로 실행 되는 데 필요한 파일만 선택 하 고 **다음**을 클릭 합니다.

8. **응용 프로그램 확인** 페이지에서 패키지를 빌드하는 데 필요한 모든 설치 파일이 표시 되는지 확인 합니다. 패키지 가속기를 사용 하 여 새 패키지를 만드는 경우 패키지를 만들려면 **응용 프로그램** 창에 표시 되는 모든 설치 파일이 필요 합니다.

   필요한 경우 설치 관리자 파일을 추가 하려면 **추가**를 클릭 합니다. 불필요 한 설치 파일을 제거 하려면 설치 관리자 파일을 선택 하 고 **삭제**를 클릭 합니다. 설치 관리자와 연결 된 속성을 편집 하려면 **편집**을 클릭 합니다. 이 단계에서 지정한 설치 파일은 패키지 가속기를 사용 하 여 새 가상 응용 프로그램 패키지를 만들 때 필요 합니다. 표시 된 정보를 확인 한 후 **다음**을 클릭 합니다.

9. **지침 선택** 페이지에서 패키지 가속기에 대 한 정보가 포함 된 파일을 지정 하려면 **찾아보기를**클릭 합니다. 예를 들어이 파일에는 Sequencer를 실행 하는 컴퓨터를 구성 하는 방법, 대상 컴퓨터에 대 한 응용 프로그램 필수 정보, 일반 메모에 대 한 정보가 포함 될 수 있습니다. 패키지 가속기가 성공적으로 적용 되는 데 필요한 모든 정보를 제공 해야 합니다. 선택한 파일은 서식 있는 텍스트 (.rtf) 또는 텍스트 파일 (.txt) 형식 이어야 합니다. **다음**을 클릭합니다.

10. **패키지 가속기 만들기** 페이지에서 패키지 가속기를 저장할 위치를 지정 하려면 **찾아보기를** 클릭 하 고 디렉터리를 선택 합니다.

11. **완료** 페이지에서 **패키지 가속기 만들기** 마법사를 닫으려면 **닫기를**클릭 합니다.

   **중요**  
   패키지 가속기가 최대한 안전한 지 확인 하 고 패키지 가속기가 적용 될 때 게시자를 확인할 수 있도록 하려면 항상 패키지 가속기에 디지털 서명 해야 합니다.



~~~
**Got a suggestion for App-V**? Add or vote on suggestions [here](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization). **Got an App-V issue?** Use the [App-V TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopappv).
~~~

## 관련 항목


[App-V 5.1 작업](operations-for-app-v-51.md)

[App-V 패키지 가속기를 사용하여 가상 응용 프로그램 패키지를 만드는 방법](how-to-create-a-virtual-application-package-using-an-app-v-package-accelerator51.md)









