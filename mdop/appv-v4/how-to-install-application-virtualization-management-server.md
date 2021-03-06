---
title: Application Virtualization Management Server 설치 방법
description: Application Virtualization Management Server 설치 방법
author: dansimp
ms.assetid: 8184be79-8c27-4328-a3c1-183791b5556c
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: dfd06ee1d2448990d5a740f3d59b0e5e4b45be4d
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/26/2020
ms.locfileid: "10817363"
---
# Application Virtualization Management Server 설치 방법


응용 프로그램 가상화 관리 서버가 클라이언트에 응용 프로그램을 게시 합니다. 대규모 배포에 일반적으로 사용할 수 있는 부하 분산 환경에서는 서버 그룹의 모든 서버가 동일한 응용 프로그램을 스트림 해야 합니다. 응용 프로그램 가상화 관리 서버에서 다른 응용 프로그램을 게시 하려면 서버를 다른 서버 그룹에 할당 합니다. 이 경우에도 서버 그룹의 용량을 늘려야 할 수 있습니다.

네트워크에서 대상 컴퓨터를 지정한 경우 로그인 계정에 로컬 관리자 권한이 있는 경우 다음 절차를 사용 하 여 응용 프로그램 가상화 관리 서버를 설치 하 고 해당 서버 그룹에 할당할 수 있습니다.

**참고**  
서버 그룹 레코드가 없는 경우 설치 마법사에서이 그룹에 대 한 응용 프로그램 가상화 관리 서버의 구성원 자격 기록도 만들 수 있습니다.



설치 과정을 완료 한 후 서버를 다시 부팅 합니다.

**응용 프로그램 가상화 관리 서버를 설치 하려면**

1.  대상 컴퓨터에 설치 된 응용 프로그램 가상화 관리 서버의 이전 버전을 확인 하 고 필요한 경우 제거 합니다.

2.  **Microsoft Application Virtualization Management Server 설치** 마법사를 열려면 네트워크에서 **setup.exe** 프로그램 가상화 시스템의 위치로 이동 하 여 네트워크에서이 프로그램을 실행 하거나 해당 디렉터리를 대상 컴퓨터로 복사한 다음 **Setup.exe** 파일을 두 번 클릭 합니다.

3.  **시작** 페이지에서 **다음**을 클릭 합니다.

4.  사용권 **계약** 페이지에서 사용권 계약을 읽고 사용권 계약에 동의 하는 경우 **동의**함을 선택 합니다. **다음**을 클릭합니다.

5.  **정보 등록** 페이지에서 사용자 이름 및 **조직을**입력 해야 합니다. **다음**을 클릭합니다.

6.  **설치 유형** 페이지에서 **사용자 지정**을 선택 합니다. **다음**을 클릭합니다. **사용자 지정 설정** 페이지에서 **응용 프로그램 가상화 서버**를 제외한 모든 application virtualization 시스템 구성 요소를 선택 취소 하 고 **다음**을 클릭 합니다.

    **주의**  
    컴퓨터에 이미 설치 되어 있는 구성 요소를 **사용자 지정 설정** 창에서 선택 취소 하면 해당 구성 요소가 자동으로 제거 됩니다.



7.  **구성 데이터베이스** 페이지의 사용 가능한 서버 목록에서 데이터베이스 서버를 선택 하거나 **다음 호스트 이름 사용** 을 선택 하 고 **서버 이름** 및 **포트 번호** 데이터를 지정 하 여 서버를 추가 합니다. **다음**을 클릭합니다.

    **참고**  
    Application Virtualization 관리 서버는 대/소문자 구분 SQL을 지원 하지 않습니다.



~~~
If a database is available, click the radio button, select the database from the list, and then click **Next**. Setup will upgrade it to this newer version. If the name does not appear in the list, enter the name in the space provided.

**Note**  
When naming a server, do not use the backslash character (/) in the server name.

If you need to install a database, see [How to Install a Database](how-to-install-a-database.md). If you would like to create a new database for this version, select **Create a new database** and specify the name that will be assigned to the new database. You can also specify a new location for the database by selecting the check box and entering the path.
~~~



8. **연결 보안 모드** 페이지의 드롭다운 목록에서 원하는 인증서를 선택 합니다. **다음**을 클릭합니다.

   **참고**  
   **보안 연결 모드** 를 설정 하려면 공개 키 인프라에서 서버에 서버 인증서를 제공 해야 합니다. 서버에 서버 인증서가 설치 되어 있지 않으면이 옵션을 사용할 수 없으며 선택할 수 없습니다. 네트워크 서비스 계정에 사용 중인 인증서에 대 한 읽기 권한을 부여 해야 합니다.



9. **TCP 포트 구성** 페이지에서 기본 포트 (554)를 사용 하려면 **기본 포트 사용 (554)** 을 선택 합니다. 사용자 지정 포트를 지정 하려면 **사용자 지정 포트 사용** 을 선택 하 고 사용 될 포트 번호를 지정 합니다. **다음**을 클릭합니다.

   **참고**  
   보안 되지 않은 환경에서 서버를 설치 하는 경우 기본 포트 (554)를 사용 하거나 사용자 지정 포트를 정의할 수 있습니다.



10. **관리자 그룹** 페이지에서 **그룹 이름**으로이 서버를 관리 하도록 승인 된 보안 그룹의 이름을 지정 합니다. **다음**을 클릭합니다. 지정 된 그룹을 확인 하 고 **다음**을 클릭 합니다.

11. **기본 공급자 그룹** 페이지에서 기본 공급자 그룹의 이름을 지정 하 고 **다음**을 클릭 합니다.

12. **콘텐츠 경로** 페이지에서 SFT 파일이 저장 되는 대상 컴퓨터의 위치를 지정 하 고 **다음**을 클릭 합니다.

   **참고**  
   관리 서버의 HTTP 또는 RTSP 포트가 이미 할당 된 경우 새 포트를 선택 하 라는 메시지가 표시 됩니다. 원하는 포트를 선택 하 고 **다음**을 클릭 합니다.



13. **프로그램 설치 준비** 페이지에서 응용 프로그램 가상화 관리 서버를 설치 하려면 **설치**를 클릭 합니다.

   **참고**  
   이 단계를 완료 하려고 할 때 오류 25120이 표시 되는 경우 IIS **관리 스크립트와 도구**를 사용 하도록 설정 해야 합니다. 이 Windows 기능을 사용 하도록 설정 하려면 제어판의 **프로그램 및 기능** 을 열고 **Windows 기능 설정/해제**를 선택 하 고 **인터넷 정보 서비스를 탐색 합니다.**

   **웹 관리 도구**에서 **IIS 관리 스크립트와 도구**를 사용 하도록 설정 합니다.



14. **설치 마법사를 완료** 한 화면에서 마법사를 닫으려면 **마침을**클릭 합니다.

   **중요**  
   설치를 완료 하는 데 몇 분 정도 걸릴 수 있습니다. 상태 메시지가 Windows 바탕 화면 알림 영역 위에 깜박입니다. 설치에 성공 했음을 나타냅니다.

   메시지가 표시 되 면 컴퓨터를 재부팅할 필요는 없습니다. 그러나 시스템 성능을 최적화 하기 위해 다시 부팅 하는 것이 좋습니다.



## 관련 항목


[서버 및 시스템 구성 요소 설치 방법](how-to-install-the-servers-and-system-components.md)









