---
title: Microsoft User Experience Virtualization(UE-V) 1.0 릴리스 정보
description: Microsoft User Experience Virtualization(UE-V) 1.0 릴리스 정보
author: dansimp
ms.assetid: 920f3fae-e9b5-4b94-beda-32c19d31e94b
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 9f9942eef7ea84cf7010a0c0173427827a512216
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/26/2020
ms.locfileid: "10812489"
---
# Microsoft User Experience Virtualization(UE-V) 1.0 릴리스 정보


Microsoft UE-V (사용자 환경 가상화) 릴리스 정보를 검색 하려면 Ctrl + F를 누릅니다.

UE-V를 설치 하기 전에이 릴리스 노트를 철저히 읽어 보아야 합니다. 릴리스 정보에는 사용자 환경 가상화를 성공적으로 설치 하는 데 필요한 정보와 제품 설명서에서 사용할 수 없는 추가 정보가 포함 되어 있습니다. 이러한 릴리스 정보와 다른 UE-V 문서 사이에 차이가 있는 경우 최신 변경 내용을 정식으로 간주 해야 합니다. 이러한 릴리스 정보는이 제품에 포함 된 콘텐츠를 대체 합니다.

## 사용자 의견 제공


피드백과 설명을 제공 하 여 MDOP에 대 한 설명서에 대 한 의견을 알려주세요. [Mdopdocs@microsoft.com](mailto:mdopdocs@microsoft.com?subject=UE-V%20Documentation)에 게 설명서 피드백을 보냅니다.

## UE-V의 알려진 문제


이 섹션에서는 사용자 환경 가상화에 대 한 릴리스 정보를 제공 합니다.

### 동일한 컴퓨터에서 레지스트리 설정이 App-v와 기본 응용 프로그램 간에 동기화 되지 않음

컴퓨터에 Application Virtualization (App-v) 응용 프로그램과 네이티브 설치 응용 프로그램 (.msi 파일과 함께 설치)을 모두 통해 사용할 수 있는 응용 프로그램이 있는 경우 레지스트리 기반 설정이 기술 간에 동기화 되지 않습니다.

해결 방법:이 문제를 해결 하려면 두 기술 중 하나를 선택 하 여 응용 프로그램을 실행 합니다.

### Windows 8 설정 동기화가 오류로 인해 실패 함: "부스트:: filesystem:: exists:: 잘못 된 사용자 이름 또는 암호"

Windows® 8 운영 체제 설정 동기화는 다음 오류 메시지와 함께 실패 합니다. **부스트:: filesystem:: exists:: 잘못 된 사용자 이름 또는 비밀 번호**입니다. 작동 로그 이벤트를 확인 하려면 **이벤트 뷰어** 를 열고 **응용 프로그램 및 서비스**를 탐색  /  합니다**Microsoft**  /  **사용자 환경 가상화**  /  **로깅이**  /  **작동**하도록 기록 됩니다. UE-V 설정 저장소 위치에 사용 되는 네트워크 공유는 사용자와 동일한 Active Directory 도메인에 있어야 합니다. 그렇지 않으면 "잘못 된 사용자 이름 또는 암호" 오류가 발생할 것입니다.

해결 방법: 사용자와 동일한 Active Directory 도메인의 네트워크 공유를 사용 합니다. .

### Outlook 2010에 대 한 전자 메일 서명 로밍

UE-V는 장치 간에 Outlook 2010 서명 파일을 로밍 합니다. 그러나 새 메시지 및 회신/전달에 대 한 기본 서명 옵션은 그렇지 않습니다.이러한 두 설정은 Outlook 프로필에 저장 되며,이는 UE-V가 로밍되지 않습니다.

해결 방법: 없음

### 느린 연결 모드에서 실행 될 때 동기화 설정이 예상 간격 동안 동기화 되지 않음

일반 조건에서 빠른 연결 네트워크 연결을 통해 설정 저장소 위치를 사용할 수 있어야 합니다. 느린 링크 모드에서는 동기화가 정기적 으로만 이루어집니다. 기본적으로 느린 연결 모드 동기화 일정은 360 분 마다 설정 됩니다.

해결 방법: 느린 연결 모드의 컴퓨터에 대해 백그라운드 동기화 주기를 변경 하려면 **오프 라인 파일**의 백그라운드 동기화 정책에 대 한 그룹 정책을 구성할 수 있습니다.

### 특수 문자는 동기화 되지 않습니다.

통화 기호 등의 특정 문자는 UE-V 에이전트를 실행 하는 windows 7 및 Windows 8 컴퓨터 간에 동기화 되지 않습니다.

해결 방법: 없음

### UE-V는 32 비트와 64 비트 버전의 Microsoft Office 간 로밍 설정을 지원 하지 않습니다.

32 비트 및 64 비트 운영 체제 모두에 대해 32 비트 버전의 Microsoft Office를 설치 하는 것이 좋습니다. 필요한 Microsoft Office 버전을 선택 하려면 여기를 클릭 하세요. ([http://office.microsoft.com/word-help/choose-the-32-bit-or-64-bit-version-of-microsoft-office-HA010369476.aspx](https://go.microsoft.com/fwlink/?LinkID=247623)). UE-V는 동일한 아키텍처 버전의 Office 간에 로밍 설정을 지원 합니다. 예를 들어 32 비트 Office 설정은 모든 32 비트 Office 인스턴스 간에 로밍 됩니다. UE-V는 32 비트와 64 비트 버전의 Office 간에 로밍 설정을 지원 하지 않습니다.

해결 방법: 없음

### 느린 연결 모드에서는 설정 저장소 위치가 있는 공유의 다른 폴더를 사용할 수 없습니다.

설정 저장소 공유는 항상 사용할 수 있어야 하는 다른 폴더에 사용 되는 네트워크 공유에 위치 하면 안 됩니다. 설정 저장소 위치를 호스팅하는 네트워크 공유가 느린 연결 모드로 들어가면 설정 저장소 위치 폴더만 사용할 수 있습니다. 느린 연결 모드에서는 공유에 있는 다른 폴더를 사용할 수 없습니다.

해결 방법: 없음

### Internet Explorer 9 즐겨찾기에 연결 된 Favicons는 로밍되지 않습니다.

Internet Explorer 9 즐겨찾기에 연결 된 favicons는 사용자 환경 가상화에 의해 roamed 되지 않으며 즐겨찾기가 새 컴퓨터에 처음 나타날 때 나타나지 않습니다.

해결 방법: Internet Explorer 9 브라우저에서 책갈피를 사용 하 고 캐시 하면 연결 된 즐겨찾기와 함께 Favicons 표시 됩니다.

### 파일 설정 경로가 레지스트리에 저장 됨

일부 응용 프로그램 설정에서는 구성 및 설정 파일의 경로가 레지스트리의 값으로 저장 됩니다. 컴퓨터 간에 설정이 roamed 되는 경우 레지스트리의 경로로 참조 되는 파일을 동기화 해야 합니다.

해결 방법: 폴더 리디렉션 또는 다른 기술을 사용 하 여 파일 설정 경로로 참조 되는 파일이 있고 설정이 로밍 되는 모든 컴퓨터의 동일한 위치에 배치 되었는지 확인 합니다.

### 260 자 보다 긴 경로는 지원 되지 않습니다.

260 자 보다 긴 설정 저장소 경로는 지원 되지 않습니다. 260 자 보다 긴 설정 저장소 경로에 UE-V 설정 패키지를 복사 하면 UE-V 작동 이벤트 로그에서 **\ [부스트:: filesystem:: copy \ _file: 시스템에서 지정 된 경로를 찾을 수 없습니다. \]** 라는 예외 메시지가 발생 합니다. 작동 로그 이벤트를 확인 하려면 **이벤트 뷰어** 를 열고 **응용 프로그램 및 서비스**를 탐색  /  합니다**Microsoft**  /  **사용자 환경 가상화**  /  **로깅이**  /  **작동**하도록 기록 됩니다.

260 자를 초과 하는 파일 설정 경로는 현재 지원 되지 않습니다. UE-V 설정 위치 템플릿에서 참조 되는 파일 설정은 260 자를 초과 하는 디렉터리 경로에 있을 수 없습니다.

해결 방법: 없음

### 로그 아웃 또는 로그인 시 UE-V 에이전트 지연

오프 라인 파일에서 느린 링크가 있는 것으로 확인 한 후에 로그온 또는 로그 아웃이 발생 하는 경우 로그 아웃 또는 로그인이 지연 될 수 있습니다. 오프 라인 파일 기능에서 현재 네트워크 상태를 검색 하는 데 최대 3 분이 걸릴 수 있습니다. 오프 라인 파일이 느린 링크에 연결 되어 있는 것으로 확인 된 후에 로그온 또는 종료가 발생 한 경우, UE-V 설정 패키지는 로컬 캐시 대신 서버로 전송 됩니다.

해결 방법: 없음

### Windows 8에서 운영 체제 설정을 로밍 하려고 할 때 설정이 충돌 함

Windows 8에서 운영 체제 설정에 대해 UE-V를 사용 하 여 Microsoft 계정 동기화를 사용 하도록 설정한 경우 적용 되는 설정이 일관성이 없을 수 있습니다.

해결 방법: 다음 중 하나를 수행 합니다.

-   UE-V를 사용 하 여 운영 체제 설정을 로밍 하는 경우 Microsoft 계정 동기화를 사용 하지 않도록 설정

-   운영 체제 설정에 대해 UE-V 사용 안 함

### 일부 운영 체제 설정은 like 운영 체제 버전 간에만 로밍 됩니다.

로캘과 관련 된 내레이터 및 통화 문자에 대 한 운영 체제 설정은 Windows의 운영 체제 버전과 유사 하 게 로밍 됩니다. 예를 들어 통화 문자는 Windows 7에서 Windows 7으로 로밍 합니다.

해결 방법: 없음

### Internet explorer 책갈피가 Internet Explorer 스마트 막대에 나타나지 않음

Internet Explorer 책갈피가 한 컴퓨터에서 다른 컴퓨터로 로밍 하는 경우 두 번째 컴퓨터의 인덱스가 업데이트 되지 않으므로 주소 표시줄에 입력 하는 경우 즐겨찾기가 컴퓨터 2의 검색 결과로 표시 되지 않습니다.

해결 방법: 없음

 

 





