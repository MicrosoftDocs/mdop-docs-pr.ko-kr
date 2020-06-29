---
title: AGPM 서버 연결 구성
description: AGPM 서버 연결 구성
author: dansimp
ms.assetid: bbbb15e8-35e7-403c-b695-7a6ebeb87839
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 9b6b065b9855c6edf44456026baa32e8d9a4674f
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/26/2020
ms.locfileid: "10819073"
---
# AGPM 서버 연결 구성


각 GPO (그룹 정책 개체)의 모든 버전은 중앙 보관 저장소에 저장 되므로 그룹 정책 관리자는 각 GPO의 배포 된 버전에 즉시 영향을 주지 않고 Gpo를 오프 라인으로 보고 수정할 수 있습니다.

AGPM 관리자 (전체 제어) 역할이 있는 사용자 계정이 며,이 절차에 사용 되는 GPO를 만든 승인자의 사용자 계정이 며, AGPM (고급 그룹 정책 관리)에서 필요한 사용 권한이 있는 사용자 계정이 며, 모든 그룹 정책 관리자의 보관 위치를 중앙에서 구성 하는 절차를 완료 해야 합니다. 이 항목의 "추가 고려 사항"에서 세부 정보를 검토 하세요.

## AGPM 서버 연결 구성


AGPM 관리자는 모든 그룹 정책 관리자가 관련 설정을 중앙에서 구성 하 여 동일한 AGPM 서버에 연결 하도록 할 수 있습니다. 환경에 일부 또는 모든 도메인에 대 한 별도의 AGPM 서버가 필요한 경우 해당 추가 AGPM 서버를 기본값에 대 한 예외로 구성 합니다. 사용자가 AGPM 서버 연결을 중앙에서 구성 하지 않는 경우 각 그룹 정책 관리자가 각 도메인에 대해 AGPM 서버를 수동으로 구성 해야 합니다.

-   [모든 그룹 정책 관리자를 위한 AGPM 서버 연결 구성](#bkmk-defaultarchiveloc)

-   [모든 그룹 정책 관리자에 대 한 추가 AGPM 서버 연결 구성](#bkmk-additionalarchiveloc)

-   [계정에 대 한 AGPM 서버 연결 수동 구성](#bkmk-manuallyconfigurearchiveloc)

### <a href="" id="bkmk-defaultarchiveloc"></a>

**모든 그룹 정책 관리자에 대해 AGPM 서버 연결을 구성 하려면**

1.  **그룹 정책 관리 콘솔** 트리에서 모든 그룹 정책 관리자에 게 적용 되는 GPO를 편집 합니다. (자세한 내용은 [GPO 편집](editing-a-gpo-agpm40.md)을 참조 하세요.)

2.  **그룹 정책 관리 편집기** 창에서 **사용자 구성**, **정책**, **관리 템플릿**, **Windows 구성 요소**및 **AGPM**을 클릭 합니다.

3.  세부 정보 창에서 **agpm: 기본 Agpm 서버 (모든 도메인) 지정**을 두 번 클릭 합니다.

4.  **속성** 창에서 **사용** 확인란을 선택 하 고 정규화 된 컴퓨터 이름 및 포트 (예: server.contoso.com:4600)를 입력 합니다.

5.  **확인**을 클릭합니다. 추가 AGPM 서버 연결을 구성 하려는 경우가 아니라면 **그룹 정책 관리 편집기** 창을 닫고 GPO를 배포 합니다. (자세한 내용은 [GPO 배포](deploy-a-gpo-agpm40.md)를 참조 하세요.) 그룹 정책이 업데이트 되 면 모든 그룹 정책 관리자에 게 AGPM 서버 연결이 구성 됩니다.

### <a href="" id="bkmk-additionalarchiveloc"></a>

**모든 그룹 정책 관리자에 대해 추가 AGPM 서버 연결을 구성 하려면**

1.  AGPM 서버 연결이 구성 되지 않은 경우 앞의 절차에 따라 모든 도메인에 대 한 기본 AGPM 서버를 구성 합니다.

2.  일부 또는 모든 도메인 (기본 AGPM 서버 재정의)에 대해 별도의 AGPM 서버를 구성 하려면 **그룹 정책 관리 콘솔** 트리에서 모든 그룹 정책 관리자에 게 적용 되는 GPO를 편집 합니다. (자세한 내용은 [GPO 편집](editing-a-gpo-agpm40.md)을 참조 하세요.)

3.  **그룹 정책 관리 편집기** 창에서 **사용자 구성**, **정책**, **관리 템플릿**, **Windows 구성 요소**, **AGPM**을 차례로 클릭 합니다.

4.  세부 정보 창에서 **agpm: Agpm 서버 지정**을 두 번 클릭 합니다.

5.  **속성** 창에서 **사용** 확인란을 선택 하 고 **표시**를 클릭 합니다.

6.  **내용 표시** 창에서 다음을 수행 합니다.

    1.  **추가**를 클릭합니다.

    2.  **값 이름**에 도메인 이름 (예: server1.contoso.com)을 입력 합니다.

    3.  **Value**에 대해이 도메인에 사용할 AGPM 서버 이름 및 포트 (예: server2.contoso.com:4600)를 입력 한 다음 **확인**을 클릭 합니다. (기본적으로 AGPM 서비스는 포트 4600에서 수신 대기 합니다. 다른 포트를 사용 하려면 [AGPM 서비스 수정을](modify-the-agpm-service-agpm40.md)참조 하세요.

    4.  기본 AGPM 서버를 사용 하지 않는 각 도메인에 대해 반복 합니다.

7.  **확인** 을 클릭 하 여 **콘텐츠** 및 **속성** 창 표시를 닫습니다.

8.  **그룹 정책 관리 편집기** 창을 닫습니다. (자세한 내용은 [GPO 배포](deploy-a-gpo-agpm40.md)를 참조 하세요.) 그룹 정책이 업데이트 되 면 모든 그룹 정책 관리자에 대해 새 AGPM 서버 연결이 구성 됩니다.

### <a href="" id="bkmk-manuallyconfigurearchiveloc"></a>

AGPM 서버 연결을 중앙에서 구성한 경우 모든 그룹 정책 관리자가이를 수동으로 구성 하는 옵션을 사용할 수 없습니다.

**계정에 대해 표시할 AGPM 서버를 수동으로 구성 하려면**

1.  **그룹 정책 관리 콘솔** 트리에서 gpo를 관리 하려는 포리스트와 도메인의 **제어 변경을** 클릭 합니다.

2.  세부 정보 창에서 **AGPM 서버** 탭을 클릭 합니다.

3.  이 도메인에 사용 되는 보관 파일 (예: server.contoso.com) 및 AGPM 서비스가 수신 대기 하는 포트 (기본적으로 포트 4600)를 관리 하는 AGPM 서버의 정규화 된 컴퓨터 이름을 입력 합니다.

4.  **적용**을 클릭 한 다음 **예** 를 클릭 하 여 확인 합니다.

### 추가 고려 사항

-   모든 그룹 정책 관리자의 AGPM 서버 연결을 중앙에서 구성 하는 절차를 수행 하려면 GPO를 편집 하 고 배포 해야 합니다. 추가 세부 정보는 [Gpo 편집](editing-a-gpo-agpm40.md) 및 [gpo 배포](deploy-a-gpo-agpm40.md) 를 참조 하세요.

-   선택한 AGPM 서버는 **콘텐츠** 탭에 표시 되는 Gpo와 **도메인 위임** 탭 설정이 적용 되는 위치를 결정 합니다. 관리 템플릿을 통해 중앙에서 관리 되지 않는 경우 각 그룹 정책 관리자는 해당 도메인의 AGPM 서버를 가리키도록이 설정을 구성 해야 합니다.

-   그룹 정책 작성자 겸 소유자 그룹의 구성원은 제한 되어야 하며, Gpo에 대 한 액세스를 AGPM에서 관리 하는 데 사용 되지 않습니다. ( **그룹 정책 관리 콘솔**에서 gpo를 관리 하려는 포리스트와 도메인의 **그룹 정책 개체** 를 클릭 하 고 **위임을**클릭 한 다음 조직의 요구 사항에 맞게 설정을 구성 합니다.)

### 추가 참조

-   [고급 그룹 정책 관리 구성](configuring-advanced-group-policy-management-agpm40.md)

 

 




