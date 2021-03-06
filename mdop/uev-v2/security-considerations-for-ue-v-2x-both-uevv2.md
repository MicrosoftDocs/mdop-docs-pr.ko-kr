---
title: UE-V 2.x에 대한 보안 고려 사항
description: UE-V 2.x에 대한 보안 고려 사항
author: dansimp
ms.assetid: 9d5c3cae-9fcb-4dea-bd67-741b3dea63be
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 8e24e9e37de11053663bb90974fabf2ff369aeca
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/26/2020
ms.locfileid: "10824663"
---
# UE-V 2.x에 대한 보안 고려 사항


이 항목에는 Microsoft UE-V (User Experience Virtualization) 2.0, 2.1 및 2.1 SP1에 대 한 계정 및 그룹, 로그 파일 및 기타 보안 관련 고려 사항에 대 한 간략 한 개요가 나와 있습니다. 자세한 내용은 여기에 나와 있는 링크를 참조 하세요.

## UE-V 구성에 대 한 보안 고려 사항


**중요**  설정 저장소 공유를 만들 때 액세스 권한이 필요한 사용자에 대 한 공유 액세스를 제한 합니다.

 

설정 패키지에는 개인 정보가 포함 될 수 있기 때문에 가능한 한 안전 하 게 보호 하는 데 주의 해야 합니다. 일반적으로 다음을 수행 합니다.

-   액세스 권한이 필요한 사용자 만으로 공유를 제한 합니다. 특정 공유에서 폴더를 리디렉션하고 해당 사용자 에게만 액세스를 제한 하는 사용자에 대 한 보안 그룹을 만듭니다.

-   공유를 만들 때 공유 이름 뒤에 $를 추가 하 여 공유를 숨깁니다. 이 추가 기능은 일반 브라우저에서 공유를 숨기 며, 네트워크 위치에 공유가 표시 되지 않습니다.

-   사용자에 게 필요한 최소 사용 권한만 제공 합니다. 다음 표에서는 필수 권한을 보여 줍니다.

    1.  설정 저장소 위치 폴더에 대해 다음과 같은 공유 수준 SMB 사용 권한을 설정 합니다.

        | 사용자 계정 | 권장 되는 사용 권한 |
        | - | - |
        | 모두 | 권한 없음 |
        |UE-V의 보안 그룹 | 모든 권한 |

    2.  설정 저장소 위치 폴더에 대해 다음 NTFS 파일 시스템 사용 권한을 설정 합니다.

        | 사용자 계정 | 권장 되는 사용 권한 | Folder |
        | - | - | - |
        | 만든이/소유자 | 모든 권한 | 하위 폴더 및 파일만|
        | 도메인 관리자 | 모든 권한 | 다음 폴더, 하위 폴더 및 파일 |
        | UE-V 사용자의 보안 그룹 | 폴더 목록/데이터 읽기, 폴더 만들기/데이터 추가 | 이 폴더만 |
        | 모두 | 모든 사용 권한 제거 | 권한 없음 |

    3.  설정 템플릿 카탈로그 폴더에 대해 다음과 같은 공유 수준 SMB 사용 권한을 설정 합니다.

        | 사용자 계정 | 권장 권한 |
        | - | - |
        | 모두 | 권한 없음 |
        | 도메인 컴퓨터 | 읽기 사용 권한 수준 |
        | 관리자 | 읽기/쓰기 권한 수준 |
         
    4.  설정 서식 파일 카탈로그 폴더에 대해 다음 NTFS 사용 권한을 설정 합니다.

        | 사용자 계정 | 권장 되는 사용 권한 | 적용 대상 |
        | - | - | - |
        | 만든이/소유자 | 모든 권한 | 다음 폴더, 하위 폴더 및 파일 |
        | 도메인 컴퓨터 | 폴더 내용 목록 및 사용 권한 읽기 | 다음 폴더, 하위 폴더 및 파일|
        | 모두| 권한 없음| 권한 없음|
        | 관리자| 모든 권한| 다음 폴더, 하위 폴더 및 파일|

### WindowsServer2003로 WindowsServer를 사용 하 여 리디렉션 파일 공유 호스팅

사용자 설정 패키지 파일에는 클라이언트 컴퓨터와 설정 패키지를 저장 하는 서버 간에 전송 되는 개인 정보가 포함 됩니다. 이 프로세스 때문에 데이터는 네트워크를 통해 이동 하는 동안 보호 되는지 확인 해야 합니다.

사용자 설정 데이터는 네트워크를 통해 전달 되는 데이터 가로채기, 네트워크를 통해 전달 되는 데이터 훼손, 데이터를 호스팅하는 서버의 스푸핑 등의 잠재적인 위협에 취약해 집니다.

Windows Server2003에서 Windows Server 운영 체제의 여러 기능을 통해 사용자 데이터를 보호할 수 있습니다.

-   **Kerberos** -Kerberos는 WindowsServer2003로 시작 하는 Microsoft Windows2000Server 및 windowsserver의 모든 버전에 대 한 표준입니다. Kerberos는 네트워크 리소스에 가장 높은 수준의 보안을 보장 합니다. NTLM은 클라이언트만 인증 합니다. Kerberos는 서버와 클라이언트를 인증 합니다. NTLM을 사용 하는 경우 클라이언트는 서버가 유효한 지 여부를 알지 못합니다. 이 차이점은 사용자 로밍 프로필의 경우와 마찬가지로 클라이언트가 서버와 개인 파일을 교환 하는 경우 특히 중요 합니다. Kerberos는 NTLM 보다 더 나은 보안을 제공 합니다. Microsoft WindowsNTServer 4.0 또는 이전 버전의 운영 체제에서는 Kerberos를 사용할 수 없습니다.

-   **Ipsec** -IP 보안 프로토콜 (ipsec)은 네트워크 수준 인증, 데이터 무결성 및 암호화를 제공 합니다. IPsec은 다음을 보장 합니다.

    -   Roamed 데이터는 데이터가 회람 되는 동안 데이터를 수정 하는 것이 안전 합니다.

    -   Roamed 데이터는 가로채기, 보기 또는 복사에서 안전 합니다.

    -   Roamed 데이터는 인증 되지 않은 사람이 액세스 하는 것을 안전 하 게 보호 합니다.

-   **Smb 서명** -Smb (서버 메시지 블록) 인증 프로토콜은 활성 메시지와 "중간자" 공격을 차단 하는 메시지 인증을 지원 합니다. SMB 서명은 각 SMB에 디지털 서명을 배치 하 여이 인증을 제공 합니다. 그러면 클라이언트와 서버에서 디지털 서명을 확인 합니다. SMB 서명을 사용 하려면 먼저 사용 하도록 설정 하거나 SMB 클라이언트와 SMB 서버 모두에서 요구 해야 합니다. SMB 서명은 성능 저하를 부과 합니다. 네트워크 대역폭을 더 이상 사용 하지 않지만 클라이언트 및 서버 쪽에서 더 많은 CPU 주기를 사용 합니다.

### 항상 사용자 데이터를 보유 하는 볼륨에 NTFS 파일 시스템 사용

가장 안전한 구성의 경우 NTFS 파일 시스템을 사용 하도록 UE-V 설정 파일을 호스팅하는 서버를 구성 합니다. FAT 파일 시스템과 달리 NTFS는 Dacl (임의 액세스 제어 목록) 및 Sacl (시스템 액세스 제어 목록)을 지원 합니다. Dacl 및 Sacl은 파일에 대 한 작업을 수행할 수 있는 사용자와 파일에서 수행 되는 작업에 대 한 로깅을 트리거하는 이벤트를 제어 합니다.

### 네트워크를 통해 전송 되는 사용자 파일을 암호화 하는 데 EFS에 의존 하지 마세요.

EFS (파일 시스템 암호화)를 사용 하 여 원격 서버에서 파일을 암호화할 때 암호화 된 데이터는 네트워크를 통해 전송 되는 동안 암호화 되지 않습니다. 디스크에 저장 된 경우에만 암호화 됩니다.

시스템에 IPsec (인터넷 프로토콜 보안) 또는 WebDAV (웹 분산 작성 및 버전 관리)가 포함 된 경우에는이 암호화 프로세스가 적용 되지 않습니다. IPsec은 TCP/IP 네트워크를 통해 전송 되는 동안 데이터를 암호화 합니다. 파일을 암호화 하 여 서버의 WebDAV 폴더로 복사 하거나 이동 하면 전송 중에는 암호화 된 상태로 유지 되 고 서버에 저장 됩니다.

### UE-V Agent가 각 사용자에 대 한 폴더를 만들도록 허용

UE-V가 최적으로 작동 하도록 하려면 서버에서 루트 공유만 만들고 UE-V Agent가 각 사용자에 대 한 폴더를 만들도록 합니다. UE-V를 사용 하면 적절 한 보안으로 이러한 사용자 폴더가 만들어집니다.

이 사용 권한 구성에서는 사용자가 설정 저장소에 대 한 폴더를 만들 수 있습니다. UE-V Agent는 사용자 컨텍스트에서 실행 되는 동안 설정 패키지 폴더를 만들고 보안 합니다. 사용자가 설정 패키지 폴더에 대 한 모든 권한을 받습니다. 다른 사용자는이 폴더에 대 한 액세스 권한을 상속 받지 않습니다. 개별 사용자 디렉토리를 생성 하 고 보호할 필요는 없습니다. 사용자 컨텍스트에서 실행 되는 에이전트는 자동으로 수행 됩니다.

**참고**  Windows Server가 설정 저장소 공유에 사용 되는 경우 추가 보안을 구성할 수 있습니다. UE-V를 구성 하 여 로컬 관리자 그룹 또는 현재 사용자가 설정 패키지를 저장 한 폴더의 소유자 인지 확인할 수 있습니다. 추가 보안을 사용 하도록 설정 하려면 다음 명령을 사용 합니다.

1.  REG \ _DWORD 레지스트리 키 RepositoryOwnerCheckEnabled를에 추가 `HKEY_LOCAL_MACHINE\Software\Microsoft\UEV\Agent\Configuration` 합니다.

2.  레지스트리 키 값을 *1*로 설정 합니다.

이 구성 설정이 설정 되어 있으면 UE-V Agent가 로컬 관리자 그룹 또는 현재 사용자가 설정 패키지 폴더의 소유자 인지 확인 합니다. 그렇지 않으면 UE-V Agent가 폴더에 대 한 액세스 권한을 부여 하지 않습니다.

 

사용자에 대 한 폴더를 만들어야 하는 경우 올바른 사용 권한이 설정 되어 있는지 확인 합니다.

폴더를 미리 만들지 않는 것이 좋습니다. 대신, UE-V Agent가 사용자에 대 한 폴더를 만들도록 할 수 있습니다.

### Home directory 또는 사용자 지정 디렉터리에 UE-V 2 설정을 저장 하는 올바른 권한이 있는지 확인

사용자의 홈 디렉터리 또는 사용자 지정 Active Directory (AD) 디렉터리로 UE-V 설정을 리디렉션하면 해당 디렉터리에 대 한 사용 권한이 조직에 맞게 설정 되어 있는지 확인 합니다.






## 관련 항목


[UE-V 2.x에 대한 기술 참조](technical-reference-for-ue-v-2x-both-uevv2.md)

 

 





