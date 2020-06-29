---
title: 프로덕션 환경에 대한 액세스 권한 위임
description: 프로덕션 환경에 대한 액세스 권한 위임
author: dansimp
ms.assetid: c1ebae2e-909b-4e64-b368-b7d3cc67b1eb
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 4667a23f1584d7aab6143860721e326da6407afb
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/26/2020
ms.locfileid: "10821013"
---
# <span data-ttu-id="ed6c1-103">프로덕션 환경에 대한 액세스 권한 위임</span><span class="sxs-lookup"><span data-stu-id="ed6c1-103">Delegate Access to the Production Environment</span></span>


<span data-ttu-id="ed6c1-104">프로덕션 환경의 Gpo (그룹 정책 개체)에 대 한 액세스를 변경 하 여 해당 Gpo의 기존 사용 권한을 바꿀 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed6c1-104">You can change access to Group Policy Objects (GPOs) in the production environment, replacing any existing permissions on those GPOs.</span></span> <span data-ttu-id="ed6c1-105">사용자가 GPMC (그룹 정책 관리) 콘솔의 **변경 제어** 폴더를 사용 하지 않는 경우 프로덕션 환경에서 gpo의 보안을 편집, 삭제 또는 수정할 수 없도록 도메인 수준에서 사용 권한을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed6c1-105">You can configure permissions at the domain level to either allow or prevent users from editing, deleting, or modifying the security of GPOs in the production environment when they are not using the **Change Control** folder in the Group Policy Management Console (GPMC).</span></span>

**<span data-ttu-id="ed6c1-106">참고</span><span class="sxs-lookup"><span data-stu-id="ed6c1-106">Note</span></span>**  
-   <span data-ttu-id="ed6c1-107">프로덕션 환경에 대 한 액세스 위임은 사용자의 Gpo 연결 기능에 영향을 주지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ed6c1-107">Delegating access to the production environment does not affect users’ ability to link GPOs.</span></span>

-   <span data-ttu-id="ed6c1-108">Gpo를 제어 하거나 배포 하는 경우 **읽기** 및 **적용** 권한이 있는 다른 계정에 대 한 액세스는 제거 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ed6c1-108">When GPOs are controlled or deployed, access for any other accounts except those with **Read** and **Apply** permissions is removed.</span></span>

 

<span data-ttu-id="ed6c1-109">이 절차를 완료 하려면 AGPM (고급 그룹 정책 관리)에서 필요한 사용 권한이 나 AGPM 관리자 (모든 권한)의 역할을 갖는 사용자 계정이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed6c1-109">A user account that has either the necessary permissions in Advanced Group Policy Management (AGPM) or the role of AGPM Administrator (Full Control) is required to complete this procedure.</span></span> <span data-ttu-id="ed6c1-110">이 항목의 "추가 고려 사항"에서 세부 정보를 검토 하세요.</span><span class="sxs-lookup"><span data-stu-id="ed6c1-110">Review the details in "Additional considerations" in this topic.</span></span>

**<span data-ttu-id="ed6c1-111">프로덕션 환경의 Gpo에 대 한 액세스 권한 변경</span><span class="sxs-lookup"><span data-stu-id="ed6c1-111">To change access to GPOs in the production environment</span></span>**

1.  <span data-ttu-id="ed6c1-112">**그룹 정책 관리 콘솔** 트리에서 gpo를 관리 하려는 포리스트와 도메인의 **제어 변경을** 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed6c1-112">In the **Group Policy Management Console** tree, click **Change Control** in the forest and domain in which you want to manage GPOs.</span></span>

2.  <span data-ttu-id="ed6c1-113">**프로덕션 위임** 탭을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed6c1-113">Click the **Production Delegation** tab.</span></span>

3.  <span data-ttu-id="ed6c1-114">프로덕션 환경에 액세스할 수 없는 사용자 또는 그룹에 대 한 사용 권한을 추가 하거나 액세스 권한이 있는 사용자 또는 그룹에 대 한 사용 권한을 바꾸려면 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed6c1-114">To add permissions for a user or group that does not have access to the production environment, or to replace the permissions for a user or group that does have access:</span></span>

    1.  <span data-ttu-id="ed6c1-115">**추가**를 클릭 하 고 사용자 또는 그룹을 선택한 다음 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed6c1-115">Click **Add**, select a user or group, and then click **OK**.</span></span>

    2.  <span data-ttu-id="ed6c1-116">프로덕션 환경을 위해 해당 사용자 또는 그룹에 위임할 권한을 선택 하 고 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed6c1-116">Select permissions to delegate to that user or group for the production environment, and then click **OK**.</span></span>

4.  <span data-ttu-id="ed6c1-117">사용자 또는 그룹의 프로덕션 환경에 대 한 모든 사용 권한을 제거 하려면 사용자 또는 그룹을 선택 하 고 **제거**를 클릭 한 다음 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed6c1-117">To remove all permissions to the production environment for a user or group, select the user or group, click **Remove**, and then click **OK**.</span></span>

### <span data-ttu-id="ed6c1-118">추가 고려 사항</span><span class="sxs-lookup"><span data-stu-id="ed6c1-118">Additional considerations</span></span>

-   <span data-ttu-id="ed6c1-119">기본적으로이 절차를 수행 하려면 AGPM 관리자 (모든 권한) 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed6c1-119">By default, you must be an AGPM Administrator (Full Control) to perform this procedure.</span></span> <span data-ttu-id="ed6c1-120">특히, 도메인에 대 한 **보안 수정** 권한이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed6c1-120">Specifically, you must have **Modify Security** permission for the domain.</span></span>

-   <span data-ttu-id="ed6c1-121">AGPM 서비스 계정에 대 한 사용 권한은 **프로덕션 위임** 탭에서 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ed6c1-121">Permissions for the AGPM Service Account cannot be changed on the **Production Delegation** tab.</span></span>

-   <span data-ttu-id="ed6c1-122">기본적으로 다음 계정에는 프로덕션 환경의 Gpo에 대 한 사용 권한이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed6c1-122">By default, the following accounts have permissions for GPOs in the production environment:</span></span>

    <table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th align="left"><span data-ttu-id="ed6c1-123">계정</span><span class="sxs-lookup"><span data-stu-id="ed6c1-123">Account</span></span></th>
    <th align="left"><span data-ttu-id="ed6c1-124">Gpo의 기본 사용 권한</span><span class="sxs-lookup"><span data-stu-id="ed6c1-124">Default Permissions for GPOs</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="ed6c1-125">&lt;AGPM 서비스 계정&gt;</span><span class="sxs-lookup"><span data-stu-id="ed6c1-125">&lt;AGPM Service Account&gt;</span></span></p></td>
    <td align="left"><p><span data-ttu-id="ed6c1-126">설정 편집, 삭제, 보안 수정</span><span class="sxs-lookup"><span data-stu-id="ed6c1-126">Edit Settings, Delete, Modify Security</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><span data-ttu-id="ed6c1-127">인증 된 사용자</span><span class="sxs-lookup"><span data-stu-id="ed6c1-127">Authenticated Users</span></span></p></td>
    <td align="left"><p><span data-ttu-id="ed6c1-128">읽기, 적용</span><span class="sxs-lookup"><span data-stu-id="ed6c1-128">Read, Apply</span></span></p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="ed6c1-129">도메인 관리자</span><span class="sxs-lookup"><span data-stu-id="ed6c1-129">Domain Admins</span></span></p></td>
    <td align="left"><p><span data-ttu-id="ed6c1-130">설정 편집, 삭제, 보안 수정</span><span class="sxs-lookup"><span data-stu-id="ed6c1-130">Edit Settings, Delete, Modify Security</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><span data-ttu-id="ed6c1-131">엔터프라이즈 관리자</span><span class="sxs-lookup"><span data-stu-id="ed6c1-131">Enterprise Admins</span></span></p></td>
    <td align="left"><p><span data-ttu-id="ed6c1-132">설정 편집, 삭제, 보안 수정</span><span class="sxs-lookup"><span data-stu-id="ed6c1-132">Edit Settings, Delete, Modify Security</span></span></p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="ed6c1-133">엔터프라이즈 도메인 컨트롤러</span><span class="sxs-lookup"><span data-stu-id="ed6c1-133">Enterprise Domain Controllers</span></span></p></td>
    <td align="left"><p><span data-ttu-id="ed6c1-134">Read</span><span class="sxs-lookup"><span data-stu-id="ed6c1-134">Read</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><span data-ttu-id="ed6c1-135">시스템</span><span class="sxs-lookup"><span data-stu-id="ed6c1-135">System</span></span></p></td>
    <td align="left"><p><span data-ttu-id="ed6c1-136">설정 편집, 삭제, 보안 수정</span><span class="sxs-lookup"><span data-stu-id="ed6c1-136">Edit Settings, Delete, Modify Security</span></span></p></td>
    </tr>
    </tbody>
    </table>

     

-   <span data-ttu-id="ed6c1-137">그룹 정책 작성자 겸 소유자 그룹의 구성원은 제한 되어야 하며, Gpo에 대 한 액세스를 AGPM에서 관리 하는 데 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ed6c1-137">Membership in the Group Policy Creator Owners group should be restricted, soit is not used to circumvent AGPM management of access to GPOs.</span></span> <span data-ttu-id="ed6c1-138">( **그룹 정책 관리 콘솔**에서 gpo를 관리 하려는 포리스트와 도메인의 **그룹 정책 개체** 를 클릭 하 고 **위임을**클릭 한 다음 조직의 요구 사항에 맞게 설정을 구성 합니다.)</span><span class="sxs-lookup"><span data-stu-id="ed6c1-138">(In the **Group Policy Management Console**, click **Group Policy Objects** in the forest and domain in which you want to manage GPOs, click **Delegation**, and then configure the settings to meet the needs of your organization.)</span></span>

### <span data-ttu-id="ed6c1-139">추가 참조</span><span class="sxs-lookup"><span data-stu-id="ed6c1-139">Additional references</span></span>

-   [<span data-ttu-id="ed6c1-140">고급 그룹 정책 관리 구성</span><span class="sxs-lookup"><span data-stu-id="ed6c1-140">Configuring Advanced Group Policy Management</span></span>](configuring-advanced-group-policy-management.md)

 

 




