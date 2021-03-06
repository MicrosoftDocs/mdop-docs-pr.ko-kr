---
title: Microsoft User Experience Virtualization(UE-V) 2.1 SP1 릴리스 정보
description: Microsoft User Experience Virtualization(UE-V) 2.1 SP1 릴리스 정보
author: dansimp
ms.assetid: 561988c4-cc5c-4e15-970b-16e942c8f2ef
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 03/30/2017
ms.openlocfilehash: 974914421c61c829b5a32e336bddf8ea1addf514
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/26/2020
ms.locfileid: "10825533"
---
# Microsoft User Experience Virtualization(UE-V) 2.1 SP1 릴리스 정보


Microsoft 사용자 환경 가상화 2.1 SP1 릴리스 정보를 검색 하려면 Ctrl + F를 누릅니다.

UE-V를 설치 하기 전에이 릴리스 노트를 철저히 읽어 보아야 합니다. 릴리스 정보에는 사용자 환경 가상화를 성공적으로 설치 하는 데 필요한 정보와 제품 설명서에서 사용할 수 없는 추가 정보가 포함 되어 있습니다. 이러한 릴리스 정보와 다른 UE-V 문서 사이에 차이가 있는 경우 최신 변경 내용을 정식으로 간주 해야 합니다. 이러한 릴리스 정보는이 제품에 포함 된 콘텐츠를 대체 합니다.

## 사용자 의견 제공


피드백과 설명을 제공 하 여 MDOP에 대 한 설명서에 대 한 의견을 알려주세요. [Mdopdocs@microsoft.com](mailto:mdopdocs@microsoft.com?subject=UE-V%20Documentation)에 게 설명서 피드백을 보냅니다.

## UE-V의 알려진 문제


이 섹션에서는 사용자 환경 가상화 2.1 SP1에 대 한 릴리스 정보를 제공 합니다.

### Skype의 UE-V 설정 위치 서식 파일을 통해 Skype가 작동 중지 됨

사용자가 Skype 데스크톱 응용 프로그램에 대 한 유효한 설정 위치 템플릿을 생성 하 고 등록 한 다음 Skype 데스크톱 응용 프로그램을 시작 하면 Skype가 충돌 합니다. ACCESS \ _VIOLATION는 응용 프로그램 이벤트 로그에 기록 됩니다.

해결 방법: skype 서식 파일을 제거 하거나 등록 취소 하 여 Skype가 다시 작동 하도록 허용 합니다.

### UE-V의 자동 설치에 대 한 기존 스크립트가 실패할 수 있음

UE-V 설치 관리자에 대 한 두 가지 변경 사항으로 인해 UE-V 2.1 SP1을 설치할 때 이전 버전의 UE-V에 대해 작동 하는 자동 설치 스크립트가 실패할 수 있습니다. 첫 번째는 자동 설치 중에도 사용자가 사용 약관에 동의 하 고 CEIP (고객 환경 개선 프로그램)에 동의 하거나 거절 해야 하는 새로운 요구 사항입니다. /Q 매개 변수를 사용 하는 것이 CEIP에 참여할 수 있는 사용 약관 및 규약에 대 한 동의를 나타내는 데 충분 하지 않습니다.

둘째로, 설치 프로그램이 UE-V Agent를 설치한 후 컴퓨터를 강제로 다시 시작 합니다. 이로 인해 다시 시작이 필요 하지 않은 경우 설치 스크립트가 실패할 수 있습니다 (예: UE-V Agent를 먼저 설치한 다음 즉시 생성기를 설치).

해결 방법: UE-V 설치 프로그램 (.msi)에는 자동 설치를 지 원하는 새로운 명령줄 매개 변수 두 개가 있습니다.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">매개 변수</th>
<th align="left">설명</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong>/ACCEPTLICENSETERMS = True</strong></p></td>
<td align="left"><p>이 매개 변수를 <strong> True로 설정 </strong> 하 여 ue-v를 자동으로 설치 합니다. 이 매개 변수를 추가 하면 사용자가 UE-V 사용 조건 (기본적으로 여기에 있음)을 수락 하는 것을 의미 합니다 .%ProgramFiles%\Microsoft 사용자 환경 Virtualization\Agent</p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>/NORESTART</strong></p></td>
<td align="left"><p>이 매개 변수는 UE-V agent가 설치 된 후 필수 다시 시작을 방지 합니다. 3010의 반환 코드는 UE-V를 사용 하기 전에 다시 시작 해야 함을 나타냅니다.</p></td>
</tr>
</tbody>
</table>

 

### 레지스트리 설정이 동일한 컴퓨터의 App-v와 네이티브 응용 프로그램 간에 동기화 되지 않음

컴퓨터에 Application Virtualization (App-v) 및 Windows Installer (.msi) 파일을 사용 하 여 로컬에서 설치 하는 응용 프로그램이 있는 경우 레지스트리 기반 설정이 기술 간에 동기화 되지 않습니다.

해결 방법:이 문제를 해결 하려면 두 기술 중 하나를 선택 하 여 응용 프로그램을 실행 합니다.

### Office 2010 및 Office 2013가 설치 된 예기치 않은 결과

사용자에 게 Office 2010 및 Office 2013이 모두 설치 되어 있는 경우 두 Office 버전 간의 일반적인 설정은 UE-V를 사용 하 여 roamed 됩니다. 이로 인해 Office 2010 패키지 크기가 매우 커질 수 있고, 특히 Office 365을 사용 하는 경우에는 2013에서 예기치 않은 충돌을 일으킵니다.

해결 방법: 하나의 Office 버전만 설치 하거나 UE-V를 통해 동기화 되는 설정을 제한할 수 있습니다.

### Windows 8 앱의 제거 및 다시 설치 초기 상태로 설정 되돌리기

Windows 8 앱에 대 한 UE-V 설정 동기화를 사용 하는 경우 사용자가 앱을 제거 하 고 앱을 다시 설치 하면 앱의 설정이 해당 기본값으로 되돌려집니다.이는 제거로 인해 앱 설정의 로컬 (캐시 된) 복사본이 제거 되 고 로컬 UE-V 설정 패키지는 제거 되지 않기 때문에 발생 합니다.앱을 다시 설치 하 고 실행할 때 UE-V는 앱 기본값으로 다시 설정 된 앱 설정을 수집 하 고 기본 설정을 중앙 저장소 위치에 업로드 합니다.앱을 실행 하는 다른 컴퓨터에서 기본 설정을 다운로드 합니다.이 동작은 데스크톱 응용 프로그램의 동작과 동일 합니다.

해결 방법: 없음

### UE-V는 32 비트와 64 비트 버전의 Microsoft Office 간 로밍 설정을 지원 하지 않습니다.

32 비트 및 64 비트 운영 체제 모두에 대해 32 비트 버전의 Microsoft Office를 설치 하는 것이 좋습니다. 필요한 Microsoft Office 버전을 선택 하려면 여기를 클릭 하세요. ([http://office.microsoft.com/word-help/choose-the-32-bit-or-64-bit-version-of-microsoft-office-HA010369476.aspx](https://go.microsoft.com/fwlink/?LinkID=247623)). UE-V는 동일한 아키텍처 버전의 Office 간에 로밍 설정을 지원 합니다. 예를 들어 32 비트 Office 설정은 모든 32 비트 Office 인스턴스 간에 로밍 됩니다. UE-V는 32 비트와 64 비트 버전의 Office 간에 로밍 설정을 지원 하지 않습니다.

해결 방법: 없음

### <a href="" id="msi-s-are-not-localized"></a>MSI는 지역화 되어 있지 않습니다.

UE-V는 UE-V Agent와 UE-V 생성기에 대 한 지역화 된 설치 프로그램을 포함 합니다. 이러한 MSI 파일은 계속 사용할 수 있지만 사용자 인터페이스가 최소화 되 고 MSI의 영어로만 표시 됩니다. 파일이 영어로 되어 있더라도 설치 하는 동안 설치 프로그램이 지원 되는 모든 언어를 설치 합니다.

해결 방법: 없음

### Internet Explorer 9 즐겨찾기에 연결 된 Favicons는 로밍되지 않습니다.

Internet Explorer 9 즐겨찾기에 연결 된 favicons는 사용자 환경 가상화에 의해 roamed 되지 않으며 즐겨찾기가 새 컴퓨터에 처음 나타날 때 나타나지 않습니다.

해결 방법: Internet Explorer 9 브라우저에서 책갈피를 사용 하 고 캐시 하면 연결 된 즐겨찾기와 함께 Favicons 표시 됩니다.

### 파일 설정 경로가 레지스트리에 저장 됨

일부 응용 프로그램 설정에서는 구성 및 설정 파일의 경로가 레지스트리의 값으로 저장 됩니다. 컴퓨터 간에 설정이 roamed 되는 경우 레지스트리의 경로로 참조 되는 파일을 동기화 해야 합니다.

해결 방법: 폴더 리디렉션 또는 다른 기술을 사용 하 여 파일 설정 경로로 참조 되는 파일이 있고 설정이 로밍 되는 모든 컴퓨터의 동일한 위치에 배치 되었는지 확인 합니다.

### 긴 설정 저장소 경로로 인해 오류가 발생할 수 있음

설정 저장소 경로를 최대한 짧게 유지 합니다. 경로가 길면 해상도 또는 동기화를 방지할 수 있습니다. UE-V는 설정 저장소 경로를 계산 된 경로의 일부로 사용 하 여 설정을 저장 합니다. 이 경로는 설정 저장소 경로 + "settingspackages" + 패키지 디렉터리 (템플릿 ID) + 패키지 이름 (템플릿 ID) + pkgx로 계산 됩니다. 해당 계산 경로가 260 자를 초과 하는 경우 패키지 저장소에 오류가 발생 하 고 UE-V 작동 이벤트 로그에서 다음 오류 메시지가 생성 됩니다.

`[boost::filesystem::copy_file: The system cannot find the path specified]`

작업 로그 이벤트를 확인 하려면 이벤트 뷰어를 열고 응용 프로그램 및 서비스 로그/Microsoft/사용자 환경 가상화/로깅/작동으로 이동 합니다.

해결 방법: 없음

### 일부 운영 체제 설정은 like 운영 체제 버전 간에만 로밍 됩니다.

로캘과 관련 된 내레이터 및 통화 문자 (즉, 언어 및 국가별 설정)에 대 한 운영 체제 설정은 Windows의 운영 체제 버전과 유사 하 게 로밍 됩니다. 예를 들어 통화 문자는 Windows 7과 Windows 8 사이에서 로밍되지 않습니다.

해결 방법: 없음

### <a href="" id="ue-v-1-agent-generates-errors-when-running-ue-v-2-templates-"></a>UE-V 2 템플릿을 실행 하는 경우 UE-V 1 agent가 오류를 생성 합니다.

Ue-v 1 에이전트를 사용 하 여 설치한 컴퓨터에 UE-V 2 설정 위치 템플릿이 배포 되는 경우 일부 설정이 컴퓨터와 에이전트 오류 보고의 이벤트 로그에 동기화 되지 않습니다.

해결 방법: UE-V 1에서 UE-V 2로 마이그레이션하는 경우 이전 버전의 에이전트를 실행 하는 컴퓨터를 사용 하는 경우 UE-V 2. x 에이전트 및 템플릿을 지원 하기 위해 별도의 UE-V v. x 카탈로그를 만듭니다.

### UE-V 로그 아웃 지연

때때로 로그 오프할 때 UE-V를 통해 설정을 동기화 하는 데 시간이 오래 걸립니다. 일반적으로 대기 시간이 긴 네트워크 또는 Distrubuted 파일 시스템 (DFS)의 잘못 된 사용으로 인해 발생 합니다.
DFS 지원에 대 한 자세한 내용은 [복제 된 사용자 프로필 데이터에 대 한 Microsoft 지원 문의](https://support.microsoft.com/kb/2533009) 를 참조 하세요.

해결 방법: HF03부터 새 레지스트리 키가 도입 되었습니다. 다음 레지스트리 키는 최대 로그 아웃 지연을 지정할 수 있는 메커니즘을 제공 합니다 \\Software\\Microsoft\\UEV\\Agent\\Configuration\\LogOffWaitInterval

자세한 내용은 [ue-v 레지스트리 설정을](https://support.microsoft.com/kb/2770042) 참조 하세요.

## UE-V 2.1 SP1에 대 한 핫픽스 및 지식 기본 문서


이 섹션에서는 UE-V 2.1 SP1에 대 한 핫픽스와 KB 문서를 제공 합니다.

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><strong>기술 자료 문서</strong></th>
<th align="left">제목</th>
<th align="left"><strong>Link</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>3018608</p></td>
<td align="left"><p>UE-V 2.1-UE-V WMI 클래스가 없는 경우 충돌 TemplateConsole.exe</p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/3018608/EN-US" data-raw-source="[support.microsoft.com/kb/3018608/EN-US](https://support.microsoft.com/kb/3018608/EN-US)">support.microsoft.com/kb/3018608/EN-US</a></p></td>
</tr>
<tr class="even">
<td align="left"><p>2903501</p></td>
<td align="left"><p>UE-V: 사용자 프로필과의 사용자 환경 가상화 (UE-V) 호환성</p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2903501/EN-US" data-raw-source="[support.microsoft.com/kb/2903501/EN-US](https://support.microsoft.com/kb/2903501/EN-US)">support.microsoft.com/kb/2903501/EN-US</a></p></td>
</tr>
<tr class="odd">
<td align="left"><p>2770042</p></td>
<td align="left"><p>UE-V 레지스트리 설정</p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2770042/EN-US" data-raw-source="[support.microsoft.com/kb/2770042/EN-US](https://support.microsoft.com/kb/2770042/EN-US)">support.microsoft.com/kb/2770042/EN-US</a></p></td>
</tr>
<tr class="even">
<td align="left"><p>2847017</p></td>
<td align="left"><p>Internet Explorer에서 복제 한 UE-V 설정</p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2847017/EN-US" data-raw-source="[support.microsoft.com/kb/2847017/EN-US](https://support.microsoft.com/kb/2847017/EN-US)">support.microsoft.com/kb/2847017/EN-US</a></p></td>
</tr>
<tr class="odd">
<td align="left"><p>2769631</p></td>
<td align="left"><p>손상 된 UE-V 설치를 복구 하는 방법</p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2769631/EN-US" data-raw-source="[support.microsoft.com/kb/2769631/EN-US](https://support.microsoft.com/kb/2769631/EN-US)">support.microsoft.com/kb/2769631/EN-US</a></p></td>
</tr>
<tr class="even">
<td align="left"><p>2850989</p></td>
<td align="left"><p>Microsoft UE-V를 사용 하 여 MAPI 프로필을 마이그레이션하는 기능은 지원 되지 않음</p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2850989/EN-US" data-raw-source="[support.microsoft.com/kb/2850989/EN-US](https://support.microsoft.com/kb/2850989/EN-US)">support.microsoft.com/kb/2850989/EN-US</a></p></td>
</tr>
<tr class="odd">
<td align="left"><p>2769586</p></td>
<td align="left"><p>UE-V가 빈 폴더 및 레지스트리 키를 로밍 합니다.</p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2769586/EN-US" data-raw-source="[support.microsoft.com/kb/2769586/EN-US](https://support.microsoft.com/kb/2769586/EN-US)">support.microsoft.com/kb/2769586/EN-US</a></p></td>
</tr>
<tr class="even">
<td align="left"><p>2782997</p></td>
<td align="left"><p>Microsoft UE-V (User Experience Virtualization)에서 디버그 로깅을 사용 하도록 설정 하는 방법</p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2782997/EN-US" data-raw-source="[support.microsoft.com/kb/2782997/EN-US](https://support.microsoft.com/kb/2782997/EN-US)">support.microsoft.com/kb/2782997/EN-US</a></p></td>
</tr>
<tr class="odd">
<td align="left"><p>2769570</p></td>
<td align="left"><p>UE-V는 RDS 또는 VDI 세션에서 테마를 업데이트 하지 않습니다.</p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2769570/EN-US" data-raw-source="[support.microsoft.com/kb/2769570/EN-US](https://support.microsoft.com/kb/2769570/EN-US)">support.microsoft.com/kb/2769570/EN-US</a></p></td>
</tr>
<tr class="even">
<td align="left"><p>2850582</p></td>
<td align="left"><p>Microsoft 사용자 환경 가상화를 사용 하는 방법 앱-V 응용 프로그램</p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2850582/EN-US" data-raw-source="[support.microsoft.com/kb/2850582/EN-US](https://support.microsoft.com/kb/2850582/EN-US)">support.microsoft.com/kb/2850582/EN-US</a></p></td>
</tr>
<tr class="odd">
<td align="left"><p>3041879</p></td>
<td align="left"><p>Microsoft 사용자 환경 가상화에 대 한 최신 파일 버전</p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/3041879/EN-US" data-raw-source="[support.microsoft.com/kb/3041879/EN-US](https://support.microsoft.com/kb/3041879/EN-US)">support.microsoft.com/kb/3041879/EN-US</a></p></td>
</tr>
<tr class="even">
<td align="left"><p>2843592</p></td>
<td align="left"><p>사용자 환경 가상화 및 고가용성에 대 한 정보</p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2843592/EN-US" data-raw-source="[support.microsoft.com/kb/2843592/EN-US](https://support.microsoft.com/kb/2843592/EN-US)">support.microsoft.com/kb/2843592/EN-US</a></p></td>
</tr>
</tbody>
</table>

 






 

 





