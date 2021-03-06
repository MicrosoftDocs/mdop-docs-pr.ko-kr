---
title: MBAM 1.0 클라이언트 배포 계획
description: MBAM 1.0 클라이언트 배포 계획
author: dansimp
ms.assetid: 3af2e7f3-134b-4ab9-9847-b07474ca6ac3
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: d58d6420febd2da9ee9cd4074fc8b5870285b0b4
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/26/2020
ms.locfileid: "10825878"
---
# MBAM 1.0 클라이언트 배포 계획


Microsoft BitLocker 관리 및 모니터링 (MBAM) 클라이언트를 배포 하는 경우 최종 사용자가 컴퓨터를 받거나 나중에 조직의 컴퓨터에서 BitLocker 암호화를 사용 하도록 설정할 수 있습니다. 최종 사용자가 컴퓨터를 받은 후 BitLocker 암호화를 사용 하도록 설정 하려면 그룹 정책을 구성 합니다. 최종 사용자가 컴퓨터를 받기 전에 BitLocker 암호화를 사용 하도록 설정 하려면 엔터프라이즈 소프트웨어 배포 시스템을 사용 하 여 MBAM 클라이언트 소프트웨어를 배포 합니다.

조직에서 하나 또는 두 가지 방법 모두를 사용할 수 있습니다. 두 방법을 모두 사용 하는 경우 준수, 보고 및 키 복구 지원을 향상 시킬 수 있습니다.

**참고**  MBAM 클라이언트 시스템 요구 사항을 검토 하려면 [mbam 1.0 지원 되는 구성을](mbam-10-supported-configurations.md)참조 하세요.

 

## 컴퓨터 배포 후 최종 사용자에 게 BitLocker 암호화를 사용 하도록 MBAM 클라이언트 배포


그룹 정책을 구성한 후에는 Microsoft System Center Configuration Manager 2012 또는 Active Directory 도메인 서비스와 같은 엔터프라이즈 소프트웨어 배포 시스템 제품을 사용 하 여 MBAM 클라이언트 설치 Windows Installer 파일을 대상 컴퓨터에 배포할 수 있습니다. 두 개의 MBAM 클라이언트 설치 Windows Installer 파일은 MBAMClient-64bit.msi 및 MBAMClient-32bit.msi 이며이는 MBAM 소프트웨어와 함께 제공 됩니다. MBAM 그룹 정책 개체를 배포 하는 방법에 대 한 자세한 내용은 [mbam 1.0 그룹 정책 개체 배포](deploying-mbam-10-group-policy-objects.md)를 참조 하세요.

MBAM 클라이언트를 배포 하는 경우 컴퓨터를 최종 사용자에 게 배포 하면 최종 사용자에 게 컴퓨터를 암호화 하 라는 메시지가 표시 됩니다. 이렇게 하면 MBAM이 데이터를 수집 하 고, PIN 및 암호를 포함 하 고, 암호화 프로세스를 시작할 수 있습니다.

**참고**  이 방법에서는 TPM (신뢰할 수 있는 플랫폼 모듈) 칩이 이전에 활성화 되지 않은 경우이를 활성화 하 고 초기화 하 라는 메시지가 표시 됩니다.

 

## 컴퓨터를 최종 사용자에 게 배포 하기 전에 MBAM 클라이언트를 사용 하 여 BitLocker 암호화를 사용 하도록 설정


컴퓨터를 중앙에서 받고 구성 하는 조직에서 MBAM 클라이언트를 설치 하 여 사용자 데이터를 기록 하기 전에 각 컴퓨터에서 BitLocker 암호화를 관리할 수 있습니다. 이 프로세스의 장점은 모든 컴퓨터가 BitLocker 암호화를 준수 하 게 됩니다. 관리자가 이미 컴퓨터를 암호화 했기 때문에이 메서드는 사용자 작업에 의존 하지 않습니다. 이 시나리오의 주요 전제는 사용자에 게 컴퓨터를 전달 하기 전에 조직의 정책이 회사 Windows 이미지를 설치 하는 것입니다.

조직에서 컴퓨터를 암호화 하기 위해 (TPM)을 사용 하려는 경우 관리자는 TPM 보호기를 사용 하 여 컴퓨터의 운영 체제 볼륨을 암호화 해야 합니다. 조직에서 TPM 칩 및 PIN 보호기를 사용 하려는 경우 관리자는 TPM 보호기를 사용 하 여 시스템 볼륨을 암호화 한 다음 사용자가 처음 로그온 할 때 PIN을 선택 해야 합니다. 조직에서 PIN 보호기만 사용 하기로 결정 한 경우 관리자는 먼저 볼륨을 암호화할 필요가 없습니다. 사용자가 컴퓨터에 로그온 할 때 MBAM은 PIN 또는 PIN을 입력 하 라는 메시지를 표시 하 고 나중에 컴퓨터를 다시 시작할 때 사용할 암호를 제공 합니다.

**참고**  TPM 보호기 옵션은 컴퓨터를 사용자에 게 전달 하기 전에 관리자가 BIOS 프롬프트를 수락 하 여 TPM을 정품 인증 하 고 초기화 해야 합니다.

 

## 관련 항목


[MBAM 1.0 배포 계획](planning-to-deploy-mbam-10.md)

[MBAM 1.0 클라이언트 배포](deploying-the-mbam-10-client.md)

 

 





