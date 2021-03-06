---
title: MBAM 2.5 설치 문제 해결
description: MBAM 설치 문제를 해결 하는 방법을 소개 합니다.
author: Deland-Han
ms.reviewer: dcscontentpm
manager: dansimp
ms.author: delhan
ms.sitesec: library
ms.prod: w10
ms.date: 09/16/2019
ms.openlocfilehash: ed56a87496e09601c44028b7f948eda39143e8c0
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/26/2020
ms.locfileid: "10812865"
---
# MBAM 2.5 설치 문제 해결

이 문서에서는 독립 실행형 구성에서 Microsoft BitLocker 관리 및 모니터링 (MBAM) 2.5 설치 문제를 해결 하는 방법을 소개 합니다.

## 문제 해결을 위해 MBAM 로그 파일을 참조 합니다.

MBAM에는 서버 설치, 클라이언트 설치 및 이벤트에 대 한 로깅이 포함 됩니다. 문제 해결을 위해이 로깅을 참조 해야 합니다. 
 
### MBAM 서버 설치 로그 파일

MBAMServerSetup.exe는 MBAM 설치 중 사용자 의% temp% 폴더에 다음 로그 파일을 생성 합니다.<br /> **Microsoft_BitLocker_Administration_and_Monitoring_<14> 번호를 기록 합니다.**

MBAMServerSetup.exe는 MBAM 설정 및 MBAM 서버 기능 설치 중 취한 작업을 기록 합니다.<br /> **Microsoft_BitLocker_Administration_and_Monitoring_<14_numbers # C1_0_MBAMServer.msi. 로그**

MBAMServerSetup.exe 설치 하는 동안 취한 추가 작업을 기록 합니다.

### MBAM 클라이언트 설치 로그 파일

클라이언트 설치 는% temp% 폴더의 다음 로그 파일 또는 클라이언트 설치 방법에 따라 사용자 지정 위치에 기록 됩니다. <br />**MSI \<five random characters\> . 로그**

이 로그는 MBAM 클라이언트 설치 중 수행 되는 작업을 포함 합니다.
 
### MBAM 클라이언트 이벤트-로깅 채널

MBAM에는 별도의 이벤트 로깅 채널이 있습니다. 관리자, 분석 및 운영 로그 파일은 이벤트 뷰어에 있으며, **응용 프로그램 및 서비스 로그**에서  >  **Microsoft**  >  **Windows**  >  **mbam**을 기록 합니다.

다음 표에는 각 이벤트 로그에 대 한 간략 한 설명이 나와 있습니다.
 
|이벤트 로그| 설명|
|----------|-------|
|Microsoft-Windows-MBAM/관리자|  오류 메시지 포함|
|Microsoft-Windows-MBAM/분석|   고급 로깅 정보 포함|
|Microsoft-Windows-MBAM/작동|    성공 메시지 포함|

### MBAM 서버 이벤트-로깅 채널

로그 파일은 이벤트 뷰어에 있으며, **응용 프로그램 및 서비스 로그**에서  >  **Microsoft**  >  **Windows**  >  **mbam**을 기록 합니다. 다음 표에는 MBAM 2.5에 도입 된 서버 이벤트 로그가 나와 있습니다.

|이벤트 로그| 설명|
|--------|-------------|
|Microsoft-Windows-MBAM/관리자|  오류 메시지 포함|
|Microsoft-Windows-MBAM/분석|   고급 로깅 정보 포함|
|Microsoft-Windows-MBAM/작동|    성공 메시지 포함|

### MBAM 웹 서비스 로그

각 MBAM 웹 서비스 로그는 SVCLOG 파일에 로깅 정보를 기록 합니다. 기본적으로 각 웹 서비스는 C:\inetpub\Microsoft BitLocker 관리 솔루션 \ 로그 폴더에서 해당 이름을 사용 하는 폴더 아래에 추적 파일을 기록 합니다.

서비스 추적 뷰어 도구 (Microsoft Visual Studio의 일부)를 사용 하 여 svclog 추적을 검토할 수 있습니다.

## 암호화 및 보고 문제 해결

이 섹션에는 서버 기능, 클라이언트 기능, 구성 설정 및 알려진 문제에 대 한 문제 해결 정보가 포함 되어 있습니다.
 
### MBAM 클라이언트 설치, 그룹 정책 설정

MBAM 에이전트가 클라이언트 컴퓨터에 설치 되어 있는지 여부를 확인 합니다. MBAM이 설치 되 면 BitLocker 관리 클라이언트 서비스 라는 서비스를 만듭니다. 이 서비스는 자동으로 시작 되도록 구성 됩니다. 서비스가 실행 중인지 확인 합니다.

MBAM 그룹 정책 설정이 클라이언트 컴퓨터에 적용 되었는지 확인 합니다. 클라이언트 컴퓨터에 그룹 정책 설정이 적용 된 경우 다음 레지스트리 하위 키가 만들어집니다. **HKEY_LOCAL_MACHINE \software\policies\microsoft\fve\mdopbitlockermanagement**

이 키가 존재 하며 그룹 정책 설정에 따라 값을 사용 하 여 채워졌는지 확인 합니다.

### 초기 지연 기간에는 MBAM 에이전트

MBAM 클라이언트는 설치 후 바로 작업을 시작 하지 않습니다. 이 경우 MBAM 에이전트는 해당 작업을 시작 하기 전에 1 ~ 18 분의 초기 임의 지연 시간을 갖습니다. 초기 지연 외에 최소 90 분의 지연이 있습니다. 지연 시간은 클라이언트 상태를 확인 하는 빈도에 대해 구성 된 그룹 정책 설정에 따라 달라 집니다. 따라서 클라이언트를 시작 하기 전의 총 지연은 *임의 시작 지연*  +  *클라이언트 검사 주파수 지연을 지연*합니다.

운영 및 관리 이벤트 로그가 비어 있는 경우에는 클라이언트가 작업을 아직 시작 하지 않고 앞에서 설명한 지연 기간에 있습니다. 지연 되지 않도록 하려면 다음 단계를 따르세요.
 
1. BitLocker 관리 클라이언트 서비스 서비스를 중지 합니다.

2. **HKEY_LOCAL_MACHINE \software\microsoft\mbam** 레지스트리 하위 키에서 **nostartupdelay** 레지스트리 값을 만들고 해당 형식을 **REG_DWORD**로 설정한 다음 해당 값을 **1**로 설정 합니다.

3. **HKEY_LOCAL_MACHINE \software\policies\microsoft\fve\mdopbitlockermanagement**에서 **ClientWakeupFrequency** 및 **StatusReportingFrequency** 값을 **1**로 설정 합니다. 이러한 값은 컴퓨터에 그룹 정책 업데이트가 있는 경우 원래 설정으로 돌아갑니다.

4. BitLocker 관리 클라이언트 서비스 서비스를 시작 합니다.

서비스가 시작 된 후 컴퓨터에 로컬로 로그인 하 고 오류가 없는 경우 1 분 내에 컴퓨터를 암호화 하는 요청을 받아야 합니다. 요청을 받지 못하는 경우에는 모든 오류 항목에 대 한 MBAM 관리자 로그를 검토 해야 합니다.

### 컴퓨터에 TPM 장치가 없거나, BIOS에서 TPM 장치를 사용 하도록 설정 되어 있지 않습니다.

MBAM 관리 이벤트 로그를 검토 합니다. MBAM 관리 이벤트 로그에 다음과 유사한 이벤트 항목이 표시 됩니다.

    Log Name:      Microsoft-Windows-MBAM/Admin
    Source:        Microsoft-Windows-MBAM
    Date:          8/3/2013 12:31:10 PM
    Event ID:      9
    Task Category: None
    Level:         Error
    Keywords:      
    User:          SYSTEM
    Computer:      Mbamclient.contoso.com
    Description:
    The TPM hardware is missing.
    TPM is needed to encrypt the operating system drive with any TPM protector.

TPM 관리 (tpm)를 열고 컴퓨터에 TPM 장치가 있는지 확인 합니다. Services.msc에 장치가 표시 되지 않으면 장치 관리자 (devmgmt.msc)를 열고 보안 장치 아래에서 신뢰할 수 있는 플랫폼 모듈을 확인 합니다. 신뢰할 수 있는 플랫폼 모듈 장치가 표시 되지 않는 경우에는 다음 이유 중 하나에 해당할 수 있습니다.

* 시스템에 TPM/보안 (신뢰할 수 있는 플랫폼 모듈) 장치가 없습니다.

* TPM 장치를 BIOS에서 사용할 수 없습니다.

* TPM 장치가 BIOS에서 사용 하도록 설정 되어 있지만 운영 체제 설정에서 TPM 장치 관리를 BIOS에서 사용할 수 없습니다.

* TPM 장치에 대 한 Microsoft 드라이버를 사용 하 고 있지 않습니다. 장치 관리자에 나열 된 장치를 검토 하 여 Microsoft TPM 장치 드라이버를 식별 합니다.

TPM 장치에서 C:\Windows\System32\tpm.sys 드라이버를 사용 하 고 있지 않은 경우에는 c \ \ \ \ \ \ \ \ c h i c 파일을 선택 하 여 드라이버를 업데이트 해야 합니다.

### 컴퓨터에 유효한 시스템 파티션이 없습니다.

MBAM 관리 이벤트 로그를 검토 합니다. MBAM 관리 이벤트 로그에 다음과 유사한 이벤트 항목이 표시 됩니다.

    Log Name:      Microsoft-Windows-MBAM/Admin
    Source:        Microsoft-Windows-MBAM
    Date:          8/3/2013 4:13:37 AM
    Event ID:      8
    Task Category: None
    Level:         Error
    Keywords:      
    User:          SYSTEM
    Computer:      BITTESTVM.xtremelabs.com
    Description:
    The system volume is missing.
    SystemVolume is needed to encrypt the operating system drive.

BitLocker에는 암호화를 사용 하도록 설정 하는 시스템 파티션이 필요 합니다 ([Windows 7에서 BitLocker 드라이브 암호화: 질문과 대답](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-7/ee449438(v=ws.10)?redirectedfrom=MSDN#bkmk_partitions)).

MBAM은 자동으로 시스템 파티션을 만들지 않습니다. BitLocker 드라이브 준비 유틸리티 (bdehdcfg.exe)를 사용 하 여 시스템 파티션을 만들고 필요한 시작 파일을 이동할 수 있습니다.

예를 들어 드라이브를 암호화 하도록 MBAM을 배포 하기 전에 **% windir% \system32\bdeHdCfg.exe 대상 기본 크기 300 – quiet** 명령을 사용 하 여 드라이브를 자동으로 준비할 수 있습니다. 이 경우 다시 시작 해야 합니다. 필요한 경우 작업을 스크립팅할 수도 있습니다. 다음 문서는 BitLocker 드라이브 준비 도구에 대해 설명 합니다.

[BitLocker 드라이브 준비 도구에 대 한 설명](https://support.microsoft.com/help/933246)

### 드라이브에 호환 되는 파일 시스템을 설정 하지 않은 경우

[BitLocker에 대 한 파일 시스템 요구 사항은 TechNet 문서](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-7/ee449438(v=ws.10)?redirectedfrom=MSDN#bkmk_hsrequirements)를 참조 하세요.

### 그룹 정책 충돌

MBAM 관리 이벤트 로그에 다음과 유사한 이벤트 항목이 표시 됩니다.

    Log Name:      Microsoft-Windows-MBAM/Admin
    Source:        Microsoft-Windows-MBAM
    Date:          7/25/2013 9:27:58 PM
    Event ID:      22
    Task Category: None
    Level:         Error
    Keywords:      
    User:          SYSTEM
    Computer:      Mbamclient.contoso.com
    Description:
    Detected Fixed Data Drive volume encryption policies conflict.
    Check BitLocker and MBAM policies related to FDD drive protectors.

그룹 정책 설정을 확인 하 여 MBAM 그룹 정책 설정 간에 충돌 하는 설정이 없는지 확인 합니다.

BitLocker 드라이브 암호화 템플릿이 아니라 MDOP MBAM 템플릿을 사용 하 여 그룹 정책을 구성 해야 합니다.

예:

운영 체제 드라이브 암호화 설정에서 TPM을 보호기로 선택 했으며, **시작에 대해 향상 된 Pin 허용**을 선택 했습니다. TPM 전용 보호에는 PIN이 필요 하지 않으므로 설정이 충돌 합니다. 따라서 향상 된 Pin 설정을 사용 하지 않도록 설정 해야 합니다.

### 사용자가 예외를 요청 했을 수 있습니다.

컴퓨터 구성 \ 관리 템플릿 \ Components\MDOP MBSAM (BitLocker Management) \Client 관리 \ 사용자 예외 구성 정책 그룹 정책 설정을 사용 하도록 설정한 경우 사용자에 게 예외를 요청할 수 있는 옵션이 제공 됩니다.

기본적으로 사용자가 예외를 요청 하는 경우 예외는 7 일 동안 유효 하며,이 기간 동안 사용자가 암호화할 것인지 묻는 메시지가 표시 되지 않습니다. (정책 구성 중에 기본값을 늘리거나 줄일 수 있습니다.) 예외 기간이 끝나면 사용자에 게 암호를 입력 하 라는 메시지가 표시 됩니다.

컴퓨터가 사용자 예외를 발생 하는 경우 MBAM 관리 이벤트 로그에 다음 항목이 표시 됩니다.

    Log Name:      Microsoft-Windows-MBAM/Admin
    Source:        Microsoft-Windows-MBAM
    Date:          8/3/2013 3:06:40 PM
    Event ID:      13
    Task Category: None
    Level:         Warning
    Keywords:      
    User:          SYSTEM
    Computer:      MBAMCLIENT.contoso.com
    Description:
    The user is exempt from encryption.

컴퓨터에 대 한 사용자 예외를 수동으로 다시 정의 하려면 다음 단계를 따릅니다.
 
1. 다음 레지스트리 하위 키 아래에서 AllowUserExemption 값을 **0** 으로 설정 합니다. <br />
**HKEY_LOCAL_MACHINE \SOFTWARE\Policies\Microsoft\FVE\MDOPBitLockerManagement**

2. 다음 레지스트리 하위 키에서 **Agentversion**, **EncodedComputerName**및 **Installed**를 제외한 모든 레지스트리 값을 삭제 합니다.<br />
**HKEY_LOCAL_MACHINE \SOFTWARE\Microsoft\MBAM**

    **참고** 변경 내용이 적용 되려면 MBAM 에이전트를 다시 시작 해야 합니다.

컴퓨터에 그룹 정책을 적용 하면 이러한 값이 원래 설정으로 돌아갈 수 있다는 점에 주의 하세요.

### WMI 문제

MBAM은 win32_encryptablevolume 클래스의 메서드를 사용 하 여 BitLocker를 관리 합니다. 이 모듈이 등록 되지 않았거나 손상 된 경우 MBAM 클라이언트가 제대로 작동 하지 않으며 MBAM 관리 이벤트 로그에 다음 이벤트 항목이 표시 됩니다.

    Log Name:      Microsoft-Windows-MBAM/Admin
    Source:        Microsoft-Windows-MBAM
    Date:          7/27/2013 11:18:51 PM
    Event ID:      4
    Task Category: None
    Level:         Error
    Keywords:      
    User:          SYSTEM
    Computer:      BITTEST.xtremelabs.com
    Description:
    An error occurred while sending encryption status data.
    Error code:
    0x80041016 
    Details:
    NULL

또한 복구 및 하드웨어 정책이 오류 코드 0x8007007e에 적용 되지 않을 수도 있습니다. "지정 된 모듈을 찾을 수 없습니다."로 변환 됩니다.

이 문제를 해결 하려면 다음 명령을 사용 하 여 **win32_encryptablevolume** 클래스를 다시 등록 해야 합니다.

```cmd
mofcomp c:\Windows\System32\wbem\win32_encryptablevolume.mof
```

## MBAM 통신 문제 해결

이 섹션에는 MBAM 에이전트 통신과 관련 된 다음과 같은 문제에 대 한 문제 해결 정보가 있습니다.

### 잘못 된 MBAM 서비스 URL

MBAM 준수 상태 서비스 또는 복구 및 하드웨어 서비스 값이 올바르지 않으면 클라이언트 컴퓨터의 MBAM 관리 이벤트 로그에 다음과 유사한 이벤트 항목이 표시 됩니다.

    Log Name:      Microsoft-Windows-MBAM/Admin
    Source:        Microsoft-Windows-MBAM
    Date:          8/3/2013 4:13:36 PM
    Event ID:      4
    Task Category: None
    Level:         Error
    Keywords:     
    User:          SYSTEM
    Computer:      Mbamclient.contoso.com
    Description:
    An error occurred while sending encryption status data.
    Error code:
    0x803d0010
    Details:
    The remote endpoint was not reachable.

    Log Name:      Microsoft-Windows-MBAM/Admin
    Source:        Microsoft-Windows-MBAM
    Date:          8/3/2013 4:13:33 PM
    Event ID:      18
    Task Category: None
    Level:         Error
    Keywords:     
    User:          SYSTEM
    Computer:      Mbamclient.contoso.com
    Description:
    Unable to connect to the MBAM Recovery and Hardware service.
    Error code:
    0x803d0010
    Details:
    The remote endpoint was not reachable.

    Log Name:      Microsoft-Windows-MBAM/Admin
    Source:        Microsoft-Windows-MBAM
    Date:          8/3/2013 4:20:32 PM
    Event ID:      4
    Task Category: None
    Level:         Error
    Keywords:     
    User:          SYSTEM
    Computer:      Mbamclient.contoso.com
    Description:
    An error occurred while sending encryption status data.
    Error code:
    0x803d0020
    Details:
    The endpoint address URL is invalid.

    Log Name:      Microsoft-Windows-MBAM/Admin
    Source:        Microsoft-Windows-MBAM
    Date:          8/3/2013 4:20:32 PM
    Event ID:      18
    Task Category: None
    Level:         Error
    Keywords:     
    User:          SYSTEM
    Computer:      Mbamclient.contoso.com
    Description:
    Unable to connect to the MBAM Recovery and Hardware service.
    Error code:
    0x803d0020
    Details:
    The endpoint address URL is invalid.

클라이언트 컴퓨터의 다음 레지스트리 하위 키 아래에서 **KeyRecoveryServiceEndPoint** 및 **StatusReportingServiceEndpoint** 의 값을 확인 합니다. <br />
**HKEY_LOCAL_MACHINE \SOFTWARE\Policies\Microsoft\FVE\MDOPBitLockerManagement**

기본적으로 KeyRecoveryServiceEndPoint (MBAM 복구 및 하드웨어 서비스 끝점)의 URL은 다음과 같은 형식입니다. <br />
**http:// \<servername\> : \<port\> /MBAMRecoveryAndHardwareService/CoreService.svc**

기본적으로 StatusReportingServiceEndpoint (MBAM Status 보고 서비스 끝점)의 URL은 다음과 같은 형식입니다.<br />
**http:// \<servername\> : \<port\> /MBAMComplianceStatusService/StatusReportingService.svc**

> [!Note]
> URL에 공백이 없어야 합니다.

서비스 URL이 잘못 된 경우 다음 그룹 정책 설정에서 서비스 URL을 수정 해야 합니다.

**컴퓨터 구성**  >  **정책**  >  **관리 서식 파일**  >  **Windows 구성 요소**  >  **MDOP MBAM (BitLocker 관리)**  >  **클라이언트 관리**  >  **MBAM 서비스 구성**

### MBAM 관리 서버에 영향을 주는 연결 문제

클라이언트 에이전트와 MBAM 관리 서버 간에 연결 문제가 있는 경우 MBAM 에이전트에서 데이터베이스에 대 한 업데이트를 게시할 수 없게 됩니다. 이 경우 클라이언트 컴퓨터의 MBAM 관리 이벤트 로그에 연결 실패 항목이 표시 됩니다.

    Log Name:      Microsoft-Windows-MBAM/Admin
    Source:        Microsoft-Windows-MBAM
    Date:          29-04-2014 18:21:22
    Event ID:      2
    Task Category: None
    Level:         Error
    Keywords:     
    User:          SYSTEM
    Computer:      TESTLABS.CONTOSO.COM
    Description:
    An error occurred while applying MBAM policies.
    Volume ID:\\?\Volume{871c5858-2467-4d0b-8c83-d68af8ce10e5}\ 
    Error code:
    0x803D0010 
    Details:
    The remote endpoint was not reachable.
 
    Log Name:      Microsoft-Windows-MBAM/Admin
    Source:        Microsoft-Windows-MBAM
    Date:          29-04-2014 23:06:48
    Event ID:      2
    Task Category: None
    Level:         Error
    Keywords:     
    User:          SYSTEM
    Computer:      TESTLABS.CONTOSO.COM
    Description:
    An error occurred while applying MBAM policies.
    Volume ID:\\?\Volume{871c5858-2467-4d0b-8c83-d68af8ce10e5}\ 
    Error code:
    0x803D0006 
    Details:
    The operation did not complete within the time allotted.

    Log Name:      Microsoft-Windows-MBAM/Admin
    Source:        Microsoft-Windows-MBAM
    Date:          02-09-2013 02:02:04
    Event ID:      18
    Task Category: None
    Level:         Error
    Keywords:     
    User:          SYSTEM
    Computer:      TESTLABS.CONTOSO.COM
    Description:
    Unable to connect to the MBAM Recovery and Hardware service.
    Error code:
    0x803D0010 
    Details:
    The remote endpoint was not reachable.

기본 검사:

* MBAM 관리 서버를 이름 및 IP로 ping 하 여 기본 연결을 확인 합니다. Telnet 또는 portqry를 사용 하 여 MBAM 관리 웹 사이트 또는 서비스 포트에 연결할 수 있는지 확인 합니다.

* MBAM 관리 및 모니터링 서버에서 IIS 서비스가 실행 중이 고 MBAM 웹 서비스가 MBAM 클라이언트 컴퓨터 ()에 구성 된 동일한 포트에서 수신 하 고 있는지 확인 `netstat –ano | find "portnumber"` 합니다.

* MBAM 웹 사이트에 대해 구성 된 포트 번호가 IIS 관리자 (inetmgr)를 사용 하 고 있는지 확인 합니다. 포트 번호가 클라이언트가 수신 대기 하는 포트 번호와 같은지 확인 합니다. 다른 응용 프로그램에서 포트 번호를 공유 하 고 있지 않은지 확인 합니다. 예를 들어 서버의 다른 응용 프로그램에서 동일한 포트를 사용 하 고 있지 않아야 합니다.

* 방화벽이 있는 경우 방화벽 또는 프록시 서버에 포트가 열려 있는지 확인 합니다.

* 클라이언트와 서버 간의 통신이 안전한 경우 유효한 SSL 인증서를 사용 하 고 있는지 확인 합니다.

* 웹 서버와 데이터를 삽입 하기 위해 전송 되는 데이터베이스 서버 간의 네트워크 연결을 확인 합니다. ODBC 데이터 원본 관리자를 사용 하 여 웹 서버에서 데이터베이스 서버로의 데이터베이스 연결을 확인할 수 있습니다. Sql [Server 데이터베이스 엔진 연결 문제를 해결 하는 방법에 대](https://social.technet.microsoft.com/wiki/contents/articles/2102.how-to-troubleshoot-connecting-to-the-sql-server-database-engine.aspx)한 자세한 sql Server 연결 문제 해결 정보를 확인할 수 있습니다.

#### 연결 문제 해결

클라이언트에 구성 되어 있는 서비스 URL이 올바른지 확인 하세요. KeyRecoveryServiceEndPoint (**HKEY_LOCAL_MACHINE \software\policies\microsoft\fve\mdopbitlockermanagement**)에 대 한 URL의 값을 레지스트리에서 복사한 다음 Internet Explorer에서 엽니다.

마찬가지로 StatusReportingServiceEndpoint (**HKEY_LOCAL_MACHINE \software\policies\microsoft\fve\mdopbitlockermanagement**)에 대 한 URL의 값을 복사한 다음 Internet Explorer에서 엽니다.

> [!Note]
> 클라이언트 컴퓨터에서 URL을 탐색할 수 없는 경우 클라이언트에서 IIS를 실행 하는 서버로의 기본 네트워크 연결을 테스트 해야 합니다. 이전 섹션의 포인트 1, 2, 3, 4를 참조 하세요.

또한 관리 및 모니터링 서버에서 오류에 대 한 응용 프로그램 로그를 검토 합니다.

클라이언트와 서버 간의 동시 네트워크 추적을 만들고 추적을 검토 하 여 클라이언트 에이전트와 MBAM 관리 서버 간의 연결 실패 원인을 확인할 수 있습니다.

> [!Note]
> 클라이언트 컴퓨터에서 서비스 Url을 탐색할 수 있고, MBAM 관리 이벤트 로그에 연결 오류 항목이 있는 경우 관리 서버와 데이터베이스 서버 간의 연결 오류 때문일 수 있습니다.

두 서비스 Url을 성공적으로 탐색할 수 있으며 클라이언트와 실행 중인 서버가 연결 되어 있으면 IIS가 작동 하는 것입니다. 그러나 IIS를 실행 하는 서버와 데이터베이스 서버 간에 통신 하는 데 문제가 있을 수 있습니다.

네트워크 문제 또는 잘못 된 데이터베이스 연결 문자열 설정으로 인해 MBAM 서비스가 데이터베이스 서버에 연결 하지 못할 수 있습니다. 관리 및 모니터링 서버에서 응용 프로그램 로그를 검토 합니다. 다음 로그 항목과 유사한 원본 ASP.NET 2.0.50727.0의 오류 항목 또는 경고가 표시 될 수 있습니다.

    Log Name:      Application
    Source:        ASP.NET 2.0.50727.0
    Date:          7/11/2013 6:16:34 PM
    Event ID:      1310
    Task Category: Web Event
    Level:         Warning
    Keywords:      Classic
    User:          N/A
    Computer:      MBAM2-Admin.contoso.com
    Description:
    Event code: 100001
    Event message: SQL error occurred
    Event time: 7/11/2013 6:16:34 PM
    Event time (UTC): 7/11/2013 12:46:34 PM
    Event ID: 6615fb8eb9d54e778b933d5bb7ca91ed
    Event sequence: 2
    Event occurrence: 1
    Event detail code: 0 
    Application information:
        Application domain: /LM/W3SVC/2/ROOT/MBAMAdministrationService-1-130180202570338699
        Trust level: Full
        Application Virtual Path: /MBAMAdministrationService
        Application Path: C:\inetpub\Microsoft BitLocker Management Solution\Administration Service\
        Machine name: MBAM2-ADMIN 
    
    Process information:
        Process ID: 1940
        Process name: w3wp.exe
        Account name: NT AUTHORITY\NETWORK SERVICE 
    
    Exception information:
        Exception type: SqlException
        Exception message: A network-related or instance-specific error occurred while establishing a connection to SQL Server. The server was not found or was not accessible. Verify that the instance name is correct and that SQL Server is configured to allow remote connections. (provider: Named Pipes Provider, error: 40 - Could not open a connection to SQL Server) 
    
    Request information:
        Request URL: 
        Request path: 
        User host address: 
        User: 
        Is authenticated: False
        Authentication Type: 
        Thread account name: NT AUTHORITY\NETWORK SERVICE 
    
    Thread information:
        Thread ID: 7
        Thread account name: NT AUTHORITY\NETWORK SERVICE
        Is impersonating: False
        Stack trace:    at System.Data.SqlClient.SqlInternalConnection.OnError(SqlException exception, Boolean breakConnection)
       at System.Data.SqlClient.TdsParser.ThrowExceptionAndWarning(TdsParserStateObject stateObj)
       at System.Data.SqlClient.TdsParser.Connect(ServerInfo serverInfo, SqlInternalConnectionTds connHandler, Boolean ignoreSniOpenTimeout, Int64 timerExpire, Boolean encrypt, Boolean trustServerCert, Boolean integratedSecurity, SqlConnection owningObject)
       at System.Data.SqlClient.SqlInternalConnectionTds.AttemptOneLogin(ServerInfo serverInfo, String newPassword, Boolean ignoreSniOpenTimeout, Int64 timerExpire, SqlConnection owningObject)
       at System.Data.SqlClient.SqlInternalConnectionTds.LoginNoFailover(String host, String newPassword, Boolean redirectedUserInstance, SqlConnection owningObject, SqlConnectionString connectionOptions, Int64 timerStart)
       at System.Data.SqlClient.SqlInternalConnectionTds.OpenLoginEnlist(SqlConnection owningObject, SqlConnectionString connectionOptions, String newPassword, Boolean redirectedUserInstance)
       at System.Data.SqlClient.SqlInternalConnectionTds..ctor(DbConnectionPoolIdentity identity, SqlConnectionString connectionOptions, Object providerInfo, String newPassword, SqlConnection owningObject, Boolean redirectedUserInstance)
       at System.Data.SqlClient.SqlConnectionFactory.CreateConnection(DbConnectionOptions options, Object poolGroupProviderInfo, DbConnectionPool pool, DbConnection owningConnection)
       at System.Data.ProviderBase.DbConnectionFactory.CreatePooledConnection(DbConnection owningConnection, DbConnectionPool pool, DbConnectionOptions options)
       at System.Data.ProviderBase.DbConnectionPool.CreateObject(DbConnection owningObject)
       at System.Data.ProviderBase.DbConnectionPool.UserCreateRequest(DbConnection owningObject)
       at System.Data.ProviderBase.DbConnectionPool.GetConnection(DbConnection owningObject)
       at System.Data.ProviderBase.DbConnectionFactory.GetConnection(DbConnection owningConnection)
       at System.Data.ProviderBase.DbConnectionClosed.OpenConnection(DbConnection outerConnection, DbConnectionFactory connectionFactory)
       at System.Data.SqlClient.SqlConnection.Open()
       at System.Data.Linq.SqlClient.SqlConnectionManager.UseConnection(IConnectionUser user)
       at System.Data.Linq.SqlClient.SqlProvider.get_IsSqlCe()
       at System.Data.Linq.SqlClient.SqlProvider.InitializeProviderMode()
       at System.Data.Linq.SqlClient.SqlProvider.System.Data.Linq.Provider.IProvider.Execute(Expression query)
       at System.Data.Linq.DataContext.ExecuteMethodCall(Object instance, MethodInfo methodInfo, Object[] parameters)
       at Microsoft.Mbam.Server.ServiceCommon.KeyRecoveryModelDataContext.GetRecoveryKeyIds(String partialRecoveryKeyId, String reason)
       at Microsoft.Mbam.ApplicationSupportService.AdministrationService.GetRecoveryKeyIds(String partialRecoveryKeyId, String reasonCode)
    
    Custom event details:
        Application: MBAMAdministrationService
        Sql Server:
        Database: MBAM Recovery and Hardware
        Database: MBAM Compliance Status
        Sql ErrorCode: 5
        Error Message: A network-related or instance-specific error occurred while establishing a connection to SQL Server. The server was not found or was not accessible. Verify that the instance name is correct and that SQL Server is configured to allow remote connections. (provider: Named Pipes Provider, error: 40 - Could not open a connection to SQL Server)

#### 원인

##### 원인 1

관리자가 관리 및 모니터링 서버 구성 요소를 설치 하는 동안 잘못 된 데이터베이스 인스턴스 이름/데이터베이스 이름을 지정 했을 수 있습니다.

IIS 관리 콘솔을 사용 하 여 데이터베이스 연결 문자열을 확인 하 고 수정할 수 있습니다. 이렇게 하려면 IIS 관리자를 열고 Microsoft BitLocker 관리 및 모니터링으로 이동 합니다. 왼쪽에 나열 된 각 서비스에 대해 데이터베이스 연결 문자열을 변경 하려면 다음 단계를 따르세요.

1. **기능 보기**에서 **연결 문자열**을 두 번 선택 합니다.

2. **연결 문자열** 페이지에서 변경 하려는 연결 문자열을 선택 합니다.

3. **작업** 창에서 **편집**을 선택 합니다.

4. **연결 문자열 편집** 대화 상자에서 변경 하려는 속성을 변경 하 고 **확인**을 선택 합니다.

##### 원인 2

방화벽에서 SQL Server 포트가 차단 되었습니다. SQL Server가 수신 하도록 구성 된 포트 번호를 확인 하 고 관리 서버와 데이터베이스 서버 사이에 방화벽에 포트가 열려 있는지 확인 합니다.

##### 원인 3

SQL server TCP/IP 바인딩이 잘못 되었습니다. 데이터베이스 서버의 SQL Server 구성 관리자에서 SQL TCP/IP 바인딩을 확인 합니다. MBAM은 데이터베이스에 연결할 수 있도록 TCP/IP 및 명명 된 파이프 프로토콜을 사용 하도록 설정 해야 합니다.

##### 원인 4

NT Authority\Network 서비스 계정 또는 MBAM 관리 서버의 컴퓨터 계정에는 SQL 데이터베이스에 연결 하는 데 필요한 권한이 없습니다.

데이터베이스 서버에 데이터베이스 구성 요소를 설치 하는 동안 설치 관리자는 MBAM 준수 감사 DB 액세스와 MBAM 복구 및 하드웨어 DB 액세스를 사용 하 여 두 개의 로컬 그룹을 만듭니다.

NT Authority\Network 서비스 계정, MBAM 관리 서버의 컴퓨터 계정, 그리고 데이터베이스 구성 요소를 설치 하는 사용자가 이러한 그룹에 자동으로 추가 됩니다.

이러한 그룹에는 설치 중에 데이터베이스에 대해 필요한 권한이 부여 됩니다. 이 그룹에 속하는 모든 사용자는 데이터베이스에 대해 필요한 사용 권한을 자동으로 받습니다.

다음 조건 중 하나 이상에 해당 하는 경우 사용 권한 문제로 인해 웹 서비스가 데이터베이스 서버에 연결 되지 않을 수 있습니다.

* 앞에서 언급 한 그룹은 데이터베이스 서버의 로컬 그룹에서 제거 됩니다.

* NT Authority\Network 서비스 계정 및 MBAM 관리 서버의 컴퓨터 계정은 이러한 그룹의 구성원이 아닙니다.

* 이러한 그룹에는 데이터베이스에 대해 필요한 권한이 없습니다.

이전 조건 중 하나라도 충족 되는 경우 MBAM 관리 및 모니터링 서버의 응용 프로그램 로그에 사용 권한 관련 오류가 표시 됩니다. 이 경우 NT Authority\Network 서비스 계정 및 MBAM 관리 서버의 컴퓨터 계정을 수동으로 추가 하 고 SQL Server Management Studio ()를 사용 하는 SQL 데이터베이스 서버에서 서버 차원의 공용 역할을 부여 해야 합니다 https://msdn.microsoft.com/library/aa337562.aspx) .

#### 웹 서비스 로그 검토

MBAM 관리 서버의 응용 프로그램 로그에 이벤트가 기록 되어 있지 않으면 MBAM 관리 및 모니터링 서버에서 호스트 되는 MBAM 웹 서비스의 웹 서비스 로그 (svclog)를 검토 해야 합니다. 로그 파일을 보려면 서비스 추적 뷰어 도구 (SvcTraceViewer.exe)를 사용 해야 https://msdn.microsoft.com/library/ms732023.aspx 합니다.

RecoveryandHardwareService 및 ComplianceStatusService의 서비스 추적 로그를 주로 조사 해야 합니다. 기본적으로 웹 서비스 로그는 C:\inetpub\Microsoft BitLocker 관리 솔루션 \ 로그 폴더에 있습니다. 각 서비스는 자신의 폴더 아래에 svclog 파일을 작성 합니다.

오류 또는 경고 항목에 대 한 서비스 추적 로그의 활동을 검토 합니다. 기본적으로 오류 항목은 빨간색으로 강조 표시 됩니다. 추적 뷰어의 오른쪽 창에 있는 오류 설명을 선택 하 여 오류 항목에 대 한 자세한 정보를 확인 합니다. 다음은 추적 로그의 샘플 오류 항목입니다.

    <E2ETraceEvent xmlns="http://schemas.microsoft.com/2004/06/E2ETraceEvent">
    <System xmlns="http://schemas.microsoft.com/2004/06/windows/eventlog/system">
    <EventID>15183</EventID>
    <Type>3</Type>
    <SubType Name="Error">0</SubType>
    <Level>2</Level>
    <TimeCreated SystemTime="2013-07-05T14:48:06.2821550Z" />
    <Source Name="Microsoft.Mbam.CoreService" />
    <Correlation ActivityID="{00000000-0000-0000-0000-000000000000}" />
    <Execution ProcessName="w3wp" ProcessID="4332" ThreadID="11" />
    <Channel />
    <Computer>XXXXXXXXXXX</Computer>
    </System>
    <ApplicationData>AddUpdateVolume: While executing sql transaction for add volume to store exception occurred Key Recovery Data Store processing error: Violation of UNIQUE KEY constraint 'UniqueRecoveryKeyId'. Cannot insert duplicate key in object 'RecoveryAndHardwareCore.Keys'. The duplicate key value is (8637036e-b379-4798-bd9e-5a0b36296de3).
    </ApplicationData>
    </E2ETraceEvent>

## MBAM 인프라 다시 설치 또는 재구성

MBAM 인프라를 다시 설치 하거나 다시 구성 하려면 다음 사항을 알아야 합니다.

* 응용 프로그램 풀 계정

* MBAM 그룹 (헬프데스크, 고급, 보고서 사용자 그룹)

* MBAM 보고서 URL

* SQL Server 이름 및 데이터베이스 이름

* MBAM ReadWrite 및 ReadOnly 계정

### 응용 프로그램 풀 계정

응용 프로그램 풀 계정을 찾으려면 MBAM 웹 서버에 로그온 하 고 **IIS (인터넷 정보 서비스) 관리자**를 연 다음 **응용 프로그램 풀**을 선택 합니다.

![응용 프로그램 풀](images/troubleshooting-MBAM-installation-1.png)

이 계정에 SPN (서비스 사용자 이름)을 설정 해야 합니다. 이 설정은 MBAM의 기능에 매우 중요 합니다.

### MBAM 그룹 (헬프데스크, 고급, 보고서 사용자 그룹 및 보고서 URL)

![MBAM 그룹](images/troubleshooting-MBAM-installation-2.png)

헬프 데스크 그룹, 고급 헬프데스크 그룹, 보고서 사용자 그룹, MBAM 보고서 URL 등의 정보를 제공 합니다. MBAM 보고서 URL은 MBAM 설정에서 제공 해야 하 고 http (s)://servername/ReportServer.로 읽어야 합니다.

### SQL Server 이름 및 데이터베이스 (DB) 이름

MBAM을 호스트 하는 SQL Server 이름 및 인스턴스를 찾으려면 MBAM 웹 (IIS) 서버에 로그온 하 고 folowing registry 하위 키를 찾습니다.

**HKEY_LOCAL_MACHINE \SOFTWARE\Microsoft\MBAM Server\Web**

![차례로](images/troubleshooting-MBAM-installation-3.png)

강조 표시 된 부분은 연결 문자열입니다. 여기에는 SQL Server 이름, 데이터베이스 이름 및 인스턴스 (명명 된 경우)가 있어야 합니다.

### MBAM ReadWrite 및 ReadOnly 계정

이 정보는 SQL Server 데이터베이스에 있으며, 이미 웹 서버에서 해당 이름을 찾았습니다.

#### ReadWrite 계정

1. SQL Management Studio에 로그인 합니다.

2. **Mbam 복구 및 하드웨어**를 마우스 오른쪽 단추로 클릭 하 고 **속성**을 선택한 다음 **사용 권한을**선택 합니다.

예를 들어 랩 계정 이름은 **Mbamwrite**입니다. 응용 프로그램 풀 및 ReadWrite 계정이 동일 하 게 설정 됩니다.

![SQL DB](images/troubleshooting-MBAM-installation-4.png)

![DB 속성](images/troubleshooting-MBAM-installation-5.png)

SQL Management Studio에서 **보안** 을 탐색 한 다음 **로그인** 합니다. 이전 스크린샷에 표시 된 계정으로 이동 합니다.

![SQL 보안](images/troubleshooting-MBAM-installation-6.png)

계정을 마우스 오른쪽 단추로 클릭 하 고 **속성 사용자 매핑으로**이동한 다음 Mbam 복구 및 하드웨어 데이터베이스를 찾습니다.

![사용자 매핑](images/troubleshooting-MBAM-installation-7.png)

#### 읽기 전용 계정

SSRS 서버에서 SQL Server Reporting Services 구성 관리자를 엽니다. **보고서 관리자 URL**을 선택한 다음 **url**을 찾습니다.

![보고서 관리자](images/troubleshooting-MBAM-installation-8.png)

**Microsoft Bitlocker 관리 및 모니터링**선택:

![Bitlocker 관리 및 모니터링](images/troubleshooting-MBAM-installation-9.png)

**MaltaDatasource**선택:

![운영할](images/troubleshooting-MBAM-installation-10.png)

![MaltaDatasource](images/troubleshooting-MBAM-installation-11.png)

MaltaDataSource는 읽기 전용 계정 이름을 포함 해야 하며 MBAM 설정에 사용 해야 합니다.

## 참고자료

자세한 내용은 다음 문서를 참조하세요.

[독립 실행형 구성에서 MBAM 2.5 배포](https://support.microsoft.com/help/3046555)

[Microsoft BitLocker 관리 및 모니터링 2.5](https://docs.microsoft.com/microsoft-desktop-optimization-pack/mbam-v25/)
