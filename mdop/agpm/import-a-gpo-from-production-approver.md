---
title: 프로덕션에서 GPO 가져오기
description: 프로덕션에서 GPO 가져오기
author: dansimp
ms.assetid: 071270fa-1890-40ce-ab89-ce070a54aa59
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 6974edc08805b56a7a69925f4c10233720488314
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/26/2020
ms.locfileid: "10820693"
---
# 프로덕션에서 GPO 가져오기


AGPM (고급 그룹 정책 관리) 외부에서 제어 된 GPO (그룹 정책 개체)를 변경한 경우 프로덕션 환경에서 GPO 복사본을 가져와 보관 저장소에 저장 하 여 보관 및 프로덕션 환경을 일관 된 상태로 만들 수 있습니다. 제어 되지 않은 GPO를 가져오려면 GPO를 제어 합니다. [이전에는 미제어 GPO 제어를](control-a-previously-uncontrolled-gpo.md)참조 하세요.)

이 절차를 완료 하려면 고급 그룹 정책 관리에서 편집자, 승인자 또는 AGPM 관리자 (모든 권한) 역할 또는 필요한 권한이 있는 사용자 계정이 필요 합니다. 이 항목의 "추가 고려 사항"에서 세부 정보를 검토 하세요.

**프로덕션 환경에서 GPO를 가져오려면**

1.  **그룹 정책 관리 콘솔** 트리에서 gpo를 관리 하려는 포리스트와 도메인의 **제어 변경을** 클릭 합니다.

2.  **콘텐츠** 탭에서 **제어** 탭을 클릭 하 여 제어 된 gpo를 표시 합니다.

3.  GPO를 마우스 오른쪽 단추로 클릭 한 다음 **프로덕션에서 가져오기를**클릭 합니다.

4.  GPO의 감사 내역에 대 한 설명을 입력 한 다음 **확인**을 클릭 합니다.

### 추가 고려 사항

-   이 절차를 수행 하려면 기본적으로 편집자, 승인자 또는 AGPM 관리자 (모든 권한) 여야 합니다. 특히 GPO에 대 한 **목록 콘텐츠** 및 **설정 편집**, **gpo 배포**또는 gpo **삭제** 권한이 있어야 합니다.

### 추가 참조

-   [GPO 만들기, 제어 또는 가져오기](creating-controlling-or-importing-a-gpo-approver.md)

 

 





