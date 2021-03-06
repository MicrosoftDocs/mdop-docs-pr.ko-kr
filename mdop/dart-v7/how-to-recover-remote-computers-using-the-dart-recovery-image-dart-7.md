---
title: DaRT 복구 이미지를 사용하여 원격 컴퓨터를 복구하는 방법
description: DaRT 복구 이미지를 사용하여 원격 컴퓨터를 복구하는 방법
author: dansimp
ms.assetid: 66bc45fb-dc40-4d47-b583-5bb1ff5c97a7
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: support
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 885ab1d1cf8f51dc4fd4613e41a20a2525ea7d6d
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/26/2020
ms.locfileid: "10822793"
---
# DaRT 복구 이미지를 사용하여 원격 컴퓨터를 복구하는 방법


Microsoft 진단 및 복구 도구 집합 (DaRT) 7의 원격 연결 기능을 사용 하면 IT 관리자가 최종 사용자 컴퓨터에서 DaRT 도구를 원격으로 실행할 수 있습니다. 최종 사용자가 특정 정보를 제공 하거나 (또는 사용자 컴퓨터에서 지원 되는 헬프데스크 전문가 인 경우) IT 관리자 또는 헬프데스크 에이전트는 최종 사용자의 컴퓨터를 제어 하 고 필요한 DaRT 도구를 원격으로 실행할 수 있습니다.

**중요**  
원격 연결을 설정 하는 두 컴퓨터는 동일한 네트워크의 일부 여야 합니다.



**DaRT를 사용 하 여 원격 컴퓨터를 복구 하려면**

1.  DaRT 복구 이미지를 사용 하 여 최종 사용자 컴퓨터를 부팅 합니다.

    일반적으로 dart 복구 이미지를 배포 하는 방법에 따라 다음 방법 중 하나를 사용 하 여 DaRT로 부팅 하 고 원격 컴퓨터를 복구 합니다. DaRT 복구 이미지 배포에 대 한 자세한 내용은 [dart 7.0 복구 이미지 배포](deploying-the-dart-70-recovery-image-dart-7.md)를 참조 하세요.

    -   문제가 있는 컴퓨터의 복구 파티션에서 DaRT로 부팅 합니다.

    -   네트워크의 원격 파티션에서 DaRT로 부팅 합니다.

    각 방법의 장점과 단점에 대 한 자세한 내용은 [DaRT 7.0 복구 이미지를 저장 하 고 배포 하는 방법 계획](planning-how-to-save-and-deploy-the-dart-70-recovery-image.md)을 참조 하세요.

    DaRT로 부팅 하는 데 사용 하는 방법에 관계 없이 부팅 옵션에 대 한 부팅 장치를 사용 하도록 설정 하 고 최종 사용자가 사용할 수 있도록 할 옵션을 선택 해야 합니다.

    **참고**  
    BIOS 구성은 조직에 사용 되는 하드 디스크 드라이브, 네트워크 어댑터 및 기타 하드웨어의 종류에 따라 고유 합니다.



2.  컴퓨터를 DaRT 복구 이미지로 부팅 하면 **Netstart** 대화 상자가 나타납니다. 네트워크 서비스를 초기화할 것인지 묻는 메시지가 표시 됩니다. **예**를 클릭 하면 DHCP 서버가 네트워크에 있고 서버에서 IP 주소를 가져오려고 시도 하는 것으로 간주 됩니다. 네트워크에서 DHCP 대신 고정 IP 주소를 사용 하는 경우, 나중에 DaRT의 **Tcp/ip 구성** 도구를 사용 하 여 고정 ip 주소를 지정할 수 있습니다.

    네트워크 초기화 프로세스를 건너뛰려면 **아니요**를 클릭 합니다.

3.  네트워크 초기화 대화 상자를 팔 로우 하는 경우 드라이브 문자를 다시 매핑할 것인지 묻는 메시지가 표시 됩니다. Windows online을 실행 하는 경우 시스템 볼륨은 일반적으로 C 드라이브에 매핑됩니다. 그러나 Windows를 오프 라인으로 WinRE에서 실행 하면 원래 시스템 볼륨이 다른 드라이브에 매핑될 수 있으며이로 인해 혼란이 발생할 수 있습니다. 다시 매핑하려는 경우 DaRT는 온라인 드라이브 문자와 일치 하도록 오프 라인 드라이브 문자를 매핑하려고 시도 합니다. 나중에 시작 프로세스에서 오프 라인 운영 체제를 선택한 경우에만 다시 매핑 처리가 수행 됩니다.

4.  다시 매핑 대화 상자 다음에는 **시스템 복구 옵션** 대화 상자가 나타나고 키보드 레이아웃을 선택 하 라는 메시지가 표시 됩니다. 그러면 시스템 루트 디렉터리, 설치 된 운영 체제 종류 및 파티션 크기가 표시 됩니다. 운영 체제가 나열 되지 않고 드라이버 부족으로 문제가 발생할 수 있다고 의심 되는 경우 **드라이버 로드** 를 클릭 하 여 의심 되는 드라이버를 로드 합니다. 장치에 대 한 설치 미디어를 삽입 하 고 드라이버를 선택 하 라는 메시지가 표시 됩니다. 복구 하거나 진단 하려는 설치를 선택 하 고 **다음**을 클릭 합니다.

    **참고**  
    WinRE (Windows 복구 환경)에서 Windows 7을 마지막으로 시도 했을 때 올바르게 시작 되지 않았다는 것을 감지 하거나 의심 되는 경우 **시동 복구** 는 자동으로 실행 되기 시작 될 수 있습니다. 해결 방법을 비롯 한이 상황에 대 한 자세한 내용은 [DaRT 7.0 문제 해결](troubleshooting-dart-70-new-ia.md)을 참조 하세요.



~~~
If any of the registry hives are corrupted or missing, Registry Editor, and several other DaRT utilities, will have limited functionality. If no operating system is selected, some tools will not be available.

The **System Recovery Options** window appears and lists various recovery tools.
~~~

5. **시스템 복구 옵션** 창에서 **Microsoft 진단 및 복구 도구 집합** 을 선택 하 여 **진단 및 복구 도구 집합** 창을 엽니다.

6. **진단 및 복구 도구 집합** 창에서 **원격 연결** 을 클릭 하 여 **DaRT 원격 연결** 창을 엽니다. 지원 센터 원격 액세스를 제공 하 라는 메시지가 표시 되 면 **확인**을 클릭 합니다.

   DaRT 원격 연결 창이 열리고 티켓 번호, IP 주소 및 포트 정보가 표시 됩니다.

7. 헬프데스크 에이전트 컴퓨터에서 **DaRT 원격 연결 뷰어**를 엽니다.

   **시작**을 클릭 하 고 **모든 프로그램**을 클릭 한 다음 **Microsoft dart 7**을 클릭 한 다음 **DaRT 원격 연결 뷰어**를 클릭 합니다.

8. **DaRT 원격 연결** 창에서 필요한 티켓, IP 주소 및 포트 정보를 입력 합니다.

   **참고**  
   이 정보는 최종 사용자 컴퓨터에서 생성 되며 최종 사용자가 제공 해야 합니다. 최종 사용자 컴퓨터에서 사용할 수 있는 여러 개의 IP 주소를 선택할 수 있습니다.



9. **연결**을 클릭합니다.

IT 관리자는 이제 최종 사용자 컴퓨터의 제어권을가지고 있으며 DaRT 도구를 원격으로 실행할 수 있습니다.

**참고**  
inv32.xml 라는 이름의 파일이 제공 되며, 포트 번호 및 IP 주소와 같은 원격 연결 정보를 포함 합니다. 기본적으로 파일 은%windir%\\system32.에 있습니다.



**원격 연결 프로세스를 사용자 지정 하려면**

1. winpeshl.ini 파일을 편집 하 여 원격 연결 프로세스를 사용자 지정할 수 있습니다. winpeshl.ini 파일을 편집 하는 방법에 대 한 자세한 내용은 [Winpeshl.ini 파일](https://go.microsoft.com/fwlink/?LinkId=219413)을 참조 하세요.

   다음 명령과 매개 변수를 지정 하 여 최종 사용자 컴퓨터에서 원격 연결을 설정 하는 방법을 사용자 지정 합니다.

   <table>
   <colgroup>
   <col width="33%" />
   <col width="33%" />
   <col width="33%" />
   </colgroup>
   <thead>
   <tr class="header">
   <th align="left">명령</th>
   <th align="left">매개 변수</th>
   <th align="left">설명</th>
   </tr>
   </thead>
   <tbody>
   <tr class="odd">
   <td align="left"><p><strong>RemoteRecovery.exe</strong></p></td>
   <td align="left"><p>-nomessage</p></td>
   <td align="left"><p>확인 메시지가 표시 되지 않도록 지정 합니다. <strong>원격 연결은 </strong> 최종 사용자가 &quot; 확인 메시지에 Yes로 응답 한 것 처럼 계속 됩니다 &quot; .</p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><strong>WaitForConnection.exe</strong></p></td>
   <td align="left"><p>none</p></td>
   <td align="left"><p><strong>원격 연결이 실행 되 고 </strong> 있지 않거나 최종 사용자 컴퓨터에 유효한 연결이 설정 될 때까지 사용자 지정 스크립트가 계속 진행 되지 않도록 합니다.</p>
   <div class="alert">
   <strong>중요</strong><br/><p>이 명령은 독립적으로 지정 된 경우 기능을 사용 하지 않습니다. 올바르게 작동 하려면 스크립트에서 지정 해야 합니다.</p>
   </div>
   <div>

   </div></td>
   </tr>
   </tbody>
   </table>



2. 다음은 DaRT로 부팅 하려고 하는 즉시 **원격 연결** 도구를 열기 위해 사용자 지정 된 winpeshl.ini 파일의 예입니다.

   ```ini
   [LaunchApps]
   "%windir%\system32\netstart.exe -network -remount"
   "cmd /C start %windir%\system32\RemoteRecovery.exe -nomessage"
   "%windir%\system32\WaitForConnection.exe"
   "%SYSTEMDRIVE%\sources\recovery\recenv.exe"
   ```

**명령 프롬프트에서 원격 연결 뷰어를 실행 하려면**

1.  명령 프롬프트에서 **DartRemoteViewer.exe** 명령을 지정 하 고 다음 매개 변수를 사용 하 여 **DaRT 원격 연결 뷰어** 를 실행할 수 있습니다.

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
    <td align="left"><p>-ticket = &lt; <em> ticketnumber</em>&gt;</p></td>
    <td align="left"><p>여기서 &lt; <em> ticketnumber </em> &gt; 는 대시를 포함 하 여 원격 연결에 의해 생성 되는 티켓 번호입니다.</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p>-ipaddress = &lt; <em> ipaddress</em>&gt;</p></td>
    <td align="left"><p>여기서 &lt; <em> Ipaddress </em> &gt; 는 원격 연결에 의해 생성 되는 IP 주소입니다.</p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p>-port = &lt; <em> port</em>&gt;</p></td>
    <td align="left"><p>여기서 &lt; <em> 포트는 </em> &gt; 지정 된 IP 주소에 해당 하는 포트입니다.</p></td>
    </tr>
    </tbody>
    </table>



~~~
**Note**  
The variables for these parameters are created on the end-user computer and must be provided by the end user.
~~~



2. 세 개의 매개 변수가 모두 지정 되 고 데이터가 유효 하면 프로그램을 시작할 때 즉시 연결을 시도 합니다. 매개 변수가 유효 하지 않은 경우에는 지정 된 매개 변수가 없는 것 처럼 프로그램이 시작 됩니다.

## 관련 항목


[DaRT 7.0를 사용하여 컴퓨터 복구](recovering-computers-using-dart-70-dart-7.md)









