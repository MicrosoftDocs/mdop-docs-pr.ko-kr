---
title: MED-V 2.0의 새로운 기능
description: MED-V 2.0의 새로운 기능
author: dansimp
ms.assetid: 53b10bff-2b6f-463b-bdc2-5edc56526792
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 78dba25fec7ae2bb41da00902b59dcd15030f2b6
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/26/2020
ms.locfileid: "10823703"
---
# MED-V 2.0의 새로운 기능


Microsoft 엔터프라이즈 데스크톱 가상화 (MED-V) 2.0는 Windows 7에 대 한 응용 프로그램 호환성 지원을 발전 했으며이 시나리오에서는 필요 하지 않은 기능을 제거 했습니다. 예를 들어 MED-V 작업 영역의 암호화, 중앙 집중화 된 MED-V 서버, MED-V 작업 영역 트리밍 전송 등의 기능이 제거 되었습니다.

## 표준 기능 변경


이 섹션에서는 MED-V 2.0 기능이 변경 된 주요 영역에 대해 설명 합니다.

### MED-V 작업 영역 만들기

이제 MED-V 작업 영역에 사용 되는 가상 하드 디스크가 Windows 가상 PC에서 만들어집니다. MED-V 작업 영역을 만드는 데 사용 되는 방법에는 Windows XP SP3 설치, 운영 체제 업데이트, 소프트웨어 관리 인프라를 통해 관리 하도록 준비 등이 포함 됩니다.

전용 MED-V 작업 영역 암호화 및 압축 기능 외에도 오프 라인 관리 및 트리밍 전송 기능이 제거 되었습니다. MED-V 작업 영역을 만들 때 관리자는 MED-V 1.0에서 제공 하는 가상 컴퓨터 준비 도구를 사용 하는 대신 이미지의 적절 한 응용 프로그램 및 관리 도구를 준비 하 고 구성 해야 합니다.

Med-v 작업 영역을 패키지화 하는 동안 MED-V 이미지에서 Sysprep를 실행 하는 것은 이제 필수 이며 유효성을 검사 합니다. MED-V 작업 영역 포장기는 패키지 프로세스를 통해 관리자를 안내 하는 GUI (그래픽 사용자 인터페이스)를 제공 합니다. MED-V 1.0의 콘솔은 이미지 관리 기능, MED-V 작업 영역 프로필 관리, MED-V 작업 영역을 단계별로 진행 하 고 암호화 하는 요구 사항과 함께 제거 되었습니다.

### MED-V 작업 영역 배포

MED-V 작업 영역을 배포 하기 위해 관리자는 이제 전자 소프트웨어 배포 도구를 활용할 수 있습니다. MED-V 1.0에서 사용할 수 있는 클라이언트 pull 메서드가 제거 되었으며 med-v 외부의 메서드를 사용 하 여 MED-V 작업 영역이 전달 됩니다. 관리자는 다른 응용 프로그램 패키지 에서처럼 MED-V 작업 영역을 처리 하 고 기존 도구 및 프로세스를 사용 하 여 MED-V의 배포 및 설치를 예약할 수 있습니다. MED-V 설치는 자동으로 배포 될 수 있으며 기존 소프트웨어 배포 인프라 내에서 쉽게 관리할 수 있습니다.

### MED-V 작업 영역 관리

MED-V 2.0의 MED-V 작업 영역은 Windows 가상 PC 가상 하드 디스크를 기반으로 합니다. MED-V는 MED-V 작업 영역에 액세스 하는 데 암호화 또는 특수 도구가 필요 하지 않은 원활한 환경을 개선 하 여 Windows 가상 PC가 제공 하는 기능을 확장 했습니다.

MED-V가 워크스테이션에 배포 된 후에는 Windows 가상 PC를 사용 하 여 MED-V 작업 영역을 전체 화면 모드로 열 수 있습니다. 이 새로운 기능은 원활한 또는 전체 화면 모드에 대 한 기본 설정을 지정 하 고 진단 및 문제 해결을 위해 전체 화면을 강제로 제거 해야 하는 정책에 대 한 요구 사항을 제거 했습니다.

MED-V 작업 영역에 대 한 응용 프로그램 게시는 프로필을 통해 더 이상 수행 되지 않으며 수동으로 응용 프로그램 경로를 입력 합니다. 대신, 응용 프로그램이 게스트에 설치 되 면 자동으로 발생 합니다. 트리밍 전송을 통해 제공 된 이미지 버전이 포함 된 중앙 이미지 리포지토리가 제거 됩니다. 대신, MED-V는 전용 MED-V 인프라의 복잡성 없이 응용 프로그램 및 업데이트를 배포 하 여 실제 컴퓨터와 마찬가지로 관리자가 MED-V 작업 영역을 관리할 수 있도록 합니다.

## MED-V 기능의 변경 내용


MED-V 2.0의 몇 가지 주요 영역에는 다음 기능에 대 한 개선 사항이 나 추가 내용이 반영 됩니다.

### MED-V 작업 영역 만들기

MED-V 작업 영역은 Windows 가상 PC를 사용 하 여 만들어야 합니다. 기존 Virtual PC 2007 이미지는 마이그레이션해야 합니다. 가상 컴퓨터 준비 도구는 MED-V 2.0에 포함 되어 있지 않으며 관리자는 MED-V 2.0 도움말 파일에 따라 이미지를 구성, 업데이트 및 최적화 해야 합니다. MED-V 이미지에서 Sysprep를 실행 하는 것은 필수 단계 이므로 패키지 하기 전에 수행 해야 합니다.

### MED-V 작업 영역 패키징

Windows PowerShell은 MED-V 작업 영역 포장기의 기반입니다. 이 기능은 MED-V의 중앙 집중화 된 함수를 관리 하는 일부 이전 콘솔 기능을 대체 합니다. MED-V 작업 영역 포장기는 관리자가 쉽게 배포할 수 있도록 적절 한 설정 및 이미지를 사용 하 여 가상 하드 디스크를 패키지화 하기만 합니다. 고급 기능은 Windows PowerShell을 사용 하 여 제공 됩니다.

### MED-V 작업 영역 배포

전용 서버 인프라는 MED-V 2.0에 더 이상 필요 하지 않으며 MED-V 작업 영역을 배포 하기 위한 클라이언트 pull 메서드가 제거 되었습니다. MED-V 작업 영역은 이제 전자 소프트웨어 배포 인프라를 사용 하 여 배포 되며 다른 설치 패키지에 사용 되는 일반 공유에 저장 될 수 있습니다.

### 처음 설치 시

처음으로 설정 프로세스가 Sysprep의 표준 이미징 규칙과 통합 됩니다. 처음에 MED-V 작업 영역 설치 프로세스는 미니 설정 시작 시 MED-V 작업 영역 포장기에 지정 된 설정을 이미지에 동적으로 적용할 수 있습니다. 콘솔의 스크립팅 도구가 제거 되었고, 이제 관리자가 MED-V 작업 영역 포장기에서 구성한 옵션에 따라 설정 프로세스가 시작 됩니다.

### 응용 프로그램 게시

관리자는 MED-V 작업 영역이 배포 된 후 또는 둘 모두의 조합을 사용 하 여 패키지 하기 전에 MED-V 이미지에 응용 프로그램을 설치할 수 있습니다. MED-V는 더 이상 MED-V 작업 영역 정책을 검사 하 여 응용 프로그램을 게시 하지 않고 실제로 게스트에 설치 되어 있는 항목을 나타냅니다. 게스트에 응용 프로그램이 설치 되 면 자동으로 검색 되어 호스트 **시작** 메뉴에 게시 되며 최종 사용자가 시작할 준비가 됩니다.

### URL 리디렉션

MED-V 2.0는 관리자가 구성 하 고 관리 하는 정책에 따라 원활한 호스트 대 게스트 웹 주소 리디렉션을 제공 합니다. URL이 게스트 브라우저로 리디렉션되는 경우 기본 환경은 사용자를 해당 리디렉션된 사이트로 제한 하는 것입니다. 이렇게 하면 관리자가 의도 하지 않은 사용자가 수행할 수 있는 검색 작업이 최소화 됩니다. 게스트-호스트 브라우저 리디렉션이 제거 되었습니다.

### 문제 해결

이제 MED-V는 문제 해결을 위해 표준 호스트 기반 프로세스를 활용 합니다. MED-V 작업 영역은 더 이상 암호화 되지 않으므로 표준 워크스테이션으로 보고 작업할 수 있는 Windows 가상 PC 콘솔 내의 전체 화면 모드로 열 수 있습니다. 또한 로그가 더 이상 로컬로 암호화 되지 않고 중앙에 기록 됩니다. 이제 MED-V는 로컬 이벤트 로그를 광범위 하 게 사용 하 고, 알림에서 디버그 수준 까지의 출력에 대 한 로깅 수준을 쉽게 구성할 수 있습니다. 마지막으로, 문제 해결 도구 키트가 제공 되므로 관리자와 헬프 데스크 직원은 모든 문제 해결 옵션을 그래프로 집계 하 여 볼 수 있으며, 대부분의 요구 사항에 가장 적합 한 작업을 손쉽게 선택할 수 있습니다.

MED-V는 시스템 서비스로 더 이상 실행 되지 않습니다. 대신 사용자가 소유한 프로세스로 실행 되며 사용자가 로그온 할 때만 실행 됩니다.이전에 시스템 소유 서비스에서 제공 했던 기능은 이제 사용자 측 프로세스에서 제공 됩니다.

## 관련 항목


[MED-V 배포](deployment-of-med-v.md)

[MED-V 작업](operations-for-med-v.md)

 

 





