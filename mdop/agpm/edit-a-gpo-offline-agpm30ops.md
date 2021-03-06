---
title: 오프라인에서 GPO 편집
description: 오프라인에서 GPO 편집
author: dansimp
ms.assetid: 51677d8a-6209-41b5-82ed-4f3be817abc0
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 74b6ae9fdf11456a9a45cb5504ed97a9bc6aecb4
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/26/2020
ms.locfileid: "10818623"
---
# 오프라인에서 GPO 편집


제어 된 GPO (그룹 정책 개체)를 변경 하려면 먼저 보관 저장소에서 GPO 복사본을 체크 아웃 해야 합니다. 다른 사용자는 다시 체크 인 될 때까지 GPO를 수정 하 여 여러 그룹 정책 관리자가 충돌 하는 변경 내용을 적용 하지 않도록 할 수 있습니다. GPO 수정을 완료 하면 프로덕션 환경에 검토 하 고 배포할 수 있도록 보관 저장소에 체크 인 합니다.

이 절차를 완료 하려면 편집기 또는 AGPM 관리자 (모든 권한) 역할이 있는 사용자 계정, GPO를 만든 승인자의 사용자 계정 또는 AGPM (고급 그룹 정책 관리)에서 필요한 권한이 있는 사용자 계정이 필요 합니다. 이 항목의 "추가 고려 사항"에서 세부 정보를 검토 하세요.

## 오프 라인으로 GPO 편집


GPO를 편집 하려면 보관 파일에서 GPO를 체크 아웃 하 고, gpo를 오프 라인으로 편집한 다음, 해당 GPO를 검토 및 배포 하거나 다른 편집기에서 수정할 수 있도록 보관 저장소에 체크 인 합니다.

-   [편집을 위해 아카이브에 대해 GPO 체크 아웃](#bkmk-checkout)

-   [오프 라인으로 GPO 편집](#bkmk-edit)

-   [보관 함에 있는 GPO 확인](#bkmk-checkin)

### <a href="" id="bkmk-checkout"></a>

**편집을 위해 아카이브에 대해 GPO를 체크 아웃 하려면**

1.  **그룹 정책 관리 콘솔** 트리에서 gpo를 관리 하려는 포리스트와 도메인의 **제어 변경을** 클릭 합니다.

2.  **콘텐츠** 탭에서 **제어** 탭을 클릭 하 여 제어 된 gpo를 표시 합니다.

3.  편집할 GPO를 마우스 오른쪽 단추로 클릭 한 다음 **체크 아웃**을 클릭 합니다.

4.  체크 아웃 된 동안 GPO 기록에 표시할 메모를 입력 한 다음 **확인**을 클릭 합니다.

5.  **진행률** 창에 전체 진행률이 완료 됨이 표시 되 면 **닫기를**클릭 합니다. 이제 **제어** 탭에서 GPO 상태가 **체크 아웃**으로 식별 됩니다.

### <a href="" id="bkmk-edit"></a>

**오프 라인으로 GPO 편집**

1.  **제어** 탭에서 편집할 GPO를 마우스 오른쪽 단추로 클릭 한 다음 **편집**을 클릭 합니다.

2.  **그룹 정책 관리 편집기** 창에서 GPO의 오프 라인 복사본을 변경 합니다.

    **참고**  모든 컴퓨터 구성 설정 또는 모든 사용자 구성 설정을 사용 하지 않도록 설정 하려면 **그룹 정책 관리 편집기** 창에서 GPO를 마우스 오른쪽 단추로 클릭 하 고 **속성**을 클릭 합니다. **컴퓨터 구성 설정 사용 안 함을** 선택 하거나 필요에 따라 **사용자 구성 설정을 사용 하지 않도록** 설정 합니다.

     

3.  GPO 수정을 마쳤으면 **그룹 정책 관리 편집기** 창을 닫습니다.

### <a href="" id="bkmk-checkin"></a>

**GPO를 보관 함으로 확인 하려면**

1.  **제어** 탭에서 다음을 수행 합니다.

    -   GPO를 변경 하지 않은 경우 GPO를 마우스 오른쪽 단추로 클릭 하 고 **체크 아웃 취소**를 클릭 한 다음 **예** 를 클릭 하 여 확인 합니다.

    -   GPO를 변경한 경우 GPO를 마우스 오른쪽 단추로 클릭 하 고 **체크 인**을 클릭 합니다.

2.  GPO의 감사 추적에 표시할 메모를 입력 한 다음 **확인**을 클릭 합니다.

3.  **진행률** 창에 전체 진행률이 완료 됨이 표시 되 면 **닫기를**클릭 합니다. **제어** 탭에서 GPO의 상태가 **체크 인**으로 식별 됩니다.

### 추가 고려 사항

-   GPO를 체크 아웃 하 고 편집 하려면 기본적으로 GPO, 편집기 또는 AGPM 관리자 (모든 권한)를 만들거나 제어 하는 승인자 여야 합니다. 특히 GPO에 대 한 **목록 콘텐츠** 및 **설정 편집** 권한이 있어야 합니다. 또한 GPO를 편집 하려면 해당 GPO를 체크 아웃 한 개인 이어야 합니다.

-   GPO를 체크 인하려면 기본적으로 편집자, 승인자 또는 AGPM 관리자 (모든 권한) 여야 합니다. 특히 GPO에 대 한 **목록 콘텐츠** 및 **설정 편집** 또는 **gpo 배포** 권한이 있어야 합니다. 승인자 또는 AGPM 관리자 (또는 **GPO 배포** 권한이 있는 다른 그룹 정책 관리자)가 아닌 경우 gpo를 체크 아웃 한 편집기 여야 합니다.

-   GPO를 편집할 때 다른 GPO에 있는 패키지의 그룹 정책 소프트웨어 설치 업그레이드는 체크 아웃 된 복사본이 아니라 배포 된 GPO를 참조 해야 합니다.

### 추가 참조

-   [GPO 편집](editing-a-gpo-agpm30ops.md)

-   GPO 검토

    -   [GPO 설정 검토](review-gpo-settings-agpm30ops.md)

    -   [GPO 링크 검토](review-gpo-links-agpm30ops.md)

    -   [GPO, GPO 버전 또는 템플릿 간의 차이점 식별](identify-differences-between-gpos-gpo-versions-or-templates-agpm30ops.md)

-   GPO 배포

    -   [GPO의 배포 요청](request-deployment-of-a-gpo-agpm30ops.md)

    -   [GPO 배포](deploy-a-gpo-agpm30ops.md)

 

 





