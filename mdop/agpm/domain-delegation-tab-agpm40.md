---
title: 도메인 위임 탭
description: 도메인 위임 탭
author: dansimp
ms.assetid: 5be5841e-92fb-4af6-aa68-0ae50f8d5141
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: c5f3b5c3b7d8799b383ab48870fcccad0b0c3f73
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/26/2020
ms.locfileid: "10818638"
---
# 도메인 위임 탭


**변경 제어** 창의 **도메인 위임** 탭에서는 보관 저장소에 대 한 도메인 수준 액세스 권한이 있는 그룹 정책 관리자 목록을 제공 하 고, 각각의 역할을 나타냅니다. 또한이 탭에서는 AGPM 관리자 (모든 권한)에서 편집자, 승인자, 검토자 및 기타 AGPM 관리자에 대 한 도메인 수준 권한을 구성할 수 있습니다. 도메인 **위임** 탭에는 도메인 수준에서 AGPM (고급 그룹 정책 관리)에 대 한 전자 메일 알림 및 역할 기반 위임 구성 이라는 두 가지 섹션이 있습니다.

## 전자 메일 알림 구성


이 탭의 전자 메일 알림 섹션에는 AGPM에서 작업이 보류 중일 때 알림을 받을 승인자가 표시 됩니다.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">설정</th>
<th align="left">설명</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong>전자 메일 주소</strong></p></td>
<td align="left"><p>알림을 승인자에 게 보내는 AGPM 별칭입니다. 여러 도메인이 있는 환경에서이는 환경 전체에서 동일한 별칭 이거나 각 도메인에 대 한 다른 별칭 일 수 있습니다.</p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>전자 메일 주소</strong></p></td>
<td align="left"><p>알림을 보낼 결재자의 전자 메일 주소 목록 (쉼표로 구분)</p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong>SMTP 서버</strong></p></td>
<td align="left"><p>전자 메일 서버의 이름 (예: mail.contoso.com)</p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>사용자 이름</strong></p></td>
<td align="left"><p>SMTP 서버에 대 한 액세스 권한이 있는 사용자</p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong>암호</strong></p></td>
<td align="left"><p>SMTP 서버 인증을 위한 사용자 암호</p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>암호 확인</strong></p></td>
<td align="left"><p>사용자 암호 확인</p></td>
</tr>
</tbody>
</table>

 

## 도메인 수준 역할 기반 위임


이 탭의 역할 기반 위임 섹션은 AGPM 관리자가 보관에 대 한 액세스 권한을 가진 각 그룹 및 사용자에 대해 허용, 거부 및 상속 된 사용 권한을 위임할 수 있도록 합니다. AGPM 관리자는 표준 AGPM 역할 (편집자, 승인자, 검토자, AGPM 관리자) 또는 각 그룹 정책 관리자에 대 한 사용자 지정 된 사용 권한 조합을 사용 하 여 도메인 전체 권한을 구성할 수 있습니다.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">단추</th>
<th align="left">효과</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong>Add</strong></p></td>
<td align="left"><p>보안 설명자에 새 항목을 추가 합니다. Active Directory의 모든 사용자 또는 그룹은 그룹 정책 관리자로 추가할 수 있습니다.</p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>제거</strong></p></td>
<td align="left"><p>선택 된 그룹 정책 관리자를 액세스 제어 목록에서 제거 합니다.</p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong>특성</strong></p></td>
<td align="left"><p>선택한 그룹 정책 관리자의 속성을 표시 합니다.</p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>고급</strong></p></td>
<td align="left"><p><strong>액세스 제어 목록 편집기를 엽니다 </strong> .</p></td>
</tr>
</tbody>
</table>

 

### 추가 고려 사항

-   특정 작업과 관련 된 역할 및 권한에 대 한 자세한 내용은 [AGPM 관리자 작업 수행](performing-agpm-administrator-tasks-agpm40.md), [편집자 작업](performing-editor-tasks-agpm40.md)수행, [승인자 작업 수행](performing-approver-tasks-agpm40.md), [검토자 작업 수행](performing-reviewer-tasks-agpm40.md)의 작업을 참조 하세요.

### 추가 참조

-   [사용자 인터페이스: 고급 그룹 정책 관리](user-interface-advanced-group-policy-management-agpm40.md)

-   [AGPM 관리자 작업 수행](performing-agpm-administrator-tasks-agpm40.md)

 

 





