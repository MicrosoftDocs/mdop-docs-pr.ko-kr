---
title: 명령줄을 사용하여 가상 응용 프로그램을 업그레이드하는 방법
description: 명령줄을 사용하여 가상 응용 프로그램을 업그레이드하는 방법
author: dansimp
ms.assetid: 83c97767-6ea1-42aa-b411-ccc9fa61cf81
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 8612deb31a1692dd85cfee88ca4b18cbc5ac2ab2
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/26/2020
ms.locfileid: "10816463"
---
# 명령줄을 사용하여 가상 응용 프로그램을 업그레이드하는 방법


명령줄을 사용 하 여 가상 응용 프로그램을 업그레이드 하려면 다음 절차를 사용 합니다.

**가상 응용 프로그램을 업그레이드 하려면**

1.  Application Virtualization (App-v) Sequencer를 실행 하는 컴퓨터에서 명령 프롬프트를 열려면 **시작**, **실행**을 선택 하 고 **cmd**를 입력 합니다. **확인**을 클릭합니다.

2.  명령 프롬프트에서 App-v Sequencer가 설치 되어 있는 위치를 지정 합니다. 예를 들어 명령 프롬프트에서 다음을 입력할 수 있습니다. **cd C:\\program files Files\\Microsoft Application Virtualization Sequencer**.

3.  명령 프롬프트에서 다음 명령을 입력 하 고 따옴표 안에 있는 텍스트를 값으로 바꿉니다.

    `SFTSequencer /UPGRADE:"pathtosourceSPRJ" /INSTALLPACKAGE:"pathtoUpgradeInstaller" /DECODEPATH:"pathtodecodefolder" /OUTPUTFILE:"pathtodestinationSPRJ"`

    **참고**  
    업그레이드 하는 응용 프로그램의 복잡도에 따라 명령줄을 사용 하 여 추가 매개 변수를 지정할 수 있습니다. App-v 시퀀서와 함께 사용할 수 있는 전체 매개 변수 목록은 [Sequencer 명령줄 매개 변수](sequencer-command-line-parameters.md)를 참조 하세요.



~~~
Use the value descriptions in the following table to help you determine the actual text you will use in the preceding command.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">Value</th>
<th align="left">Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><em>pathtosourceSPRJ</em></p></td>
<td align="left"><p>Specifies the directory location of the virtual application to be upgraded.</p></td>
</tr>
<tr class="even">
<td align="left"><p><em>pathtoUpgradeInstaller</em></p></td>
<td align="left"><p>Specifies the Windows Installer or a batch file that will be used to install an upgrade to the application.</p></td>
</tr>
<tr class="odd">
<td align="left"><p><em>pathtodecodefolder</em></p></td>
<td align="left"><p>Specify the directory in which to unpack the SFT file.</p></td>
</tr>
<tr class="even">
<td align="left"><p><em>pathtodestinationSPRJ</em></p></td>
<td align="left"><p>Specifies the path and file name of the SPRJ file that will be created.</p></td>
</tr>
</tbody>
</table>
~~~



4. Enter **키를**누릅니다.

## 관련 항목


[앱-V 시퀀서를 사용 하 여 가상 응용 프로그램을 만들거나 업그레이드 하는 방법](how-to-create-or-upgrade-virtual-applications-using--the-app-v-sequencer.md)

[Sequencer 명령줄 오류 코드](sequencer-command-line-error-codes.md)

[Sequencer 명령줄 매개 변수](sequencer-command-line-parameters.md)









