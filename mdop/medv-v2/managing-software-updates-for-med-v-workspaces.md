---
title: MED-V 작업 영역에 대한 소프트웨어 업데이트 관리
description: MED-V 작업 영역에 대한 소프트웨어 업데이트 관리
author: dansimp
ms.assetid: a28d6dcd-cb9f-46ba-8dac-1d990837a3a3
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 696238a2f5ad9b7e5120f75f6cd09d890d12519b
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/26/2020
ms.locfileid: "10824813"
---
# MED-V 작업 영역에 대한 소프트웨어 업데이트 관리


배포 된 MED-V 작업 영역의 응용 프로그램에 소프트웨어 업데이트를 제공 하는 데 사용할 수 있는 여러 가지 옵션이 있습니다.

**참고**  MED-V가 자동 업데이트를 수신 하는 방법을 정의 하는 구성 설정을 지정 하는 방법에 대 한 자세한 내용은 [Med-v 작업 영역의 자동 업데이트 관리](managing-automatic-updates-for-med-v-workspaces.md)를 참조 하세요.

 

**MED-V 작업 영역의 소프트웨어 업데이트**

1.  **전자 소프트웨어 배포 시스템 사용**

    조직에서 ESD (전자 소프트웨어 배포 시스템) 시스템을 사용 하 여 소프트웨어를 배포 하는 경우 물리적 컴퓨터의 응용 프로그램에 대 한 업데이트를 제공 하는 것 처럼이 기능을 사용 하 여 MED-V 작업 영역의 응용 프로그램에 대 한 소프트웨어 업데이트를 제공할 수 있습니다.

2.  **그룹 정책 사용**

    조직에서 그룹 정책을 사용 하 여 소프트웨어를 배포 하는 경우 물리적 컴퓨터의 응용 프로그램에 대 한 업데이트를 제공 하는 것 처럼이를 사용 하 여 MED-V 작업 영역의 응용 프로그램에 소프트웨어 업데이트를 제공할 수 있습니다.

3.  **Application Virtualization (APP-V) 사용**

    MED-V와 App-v를 함께 사용 하는 경우 소프트웨어 업데이트를 위해 App-v에 필요한 단계에 따라 MED-V 작업 영역의 응용 프로그램에 소프트웨어 업데이트를 제공할 수 있습니다. 자세한 내용은 [응용 프로그램 가상화](https://go.microsoft.com/fwlink/?LinkId=122939) ()를 참조 하세요 https://go.microsoft.com/fwlink/?LinkId=122939) .

4.  **코어 이미지의 소프트웨어 업데이트**

    MED-V 모범 사례로 간주 되지 않더라도 코어 이미지의 응용 프로그램에 소프트웨어 업데이트를 설치할 수 있습니다. 업데이트를 설치한 후에는 원래 배포 하는 것과 동일한 방법으로 엔터프라이즈에 MED-V 작업 영역을 다시 배포할 수 있습니다.

    **중요**  소프트웨어 업데이트를 관리 하는 방법은이 방법을 권장 하지 않습니다. 또한 핵심 이미지의 소프트웨어를 업데이트 하 고 MED-V 작업 영역을 enterprise에 다시 배포 하는 경우 먼저 설치 프로그램이 다시 실행 되어야 하 고 가상 컴퓨터에 저장 된 모든 데이터가 손실 됩니다.

     

## 관련 항목


[MED-V 작업 영역에 대한 자동 업데이트 관리](managing-automatic-updates-for-med-v-workspaces.md)

[응용 프로그램 게시를 테스트하는 방법](how-to-test-application-publishing.md)

[MED-V 작업 영역에서 응용 프로그램을 게시 및 게시 취소하는 방법](how-to-publish-and-unpublish-an-application-on-the-med-v-workspace.md)

 

 





