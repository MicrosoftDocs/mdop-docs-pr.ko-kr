---
title: App-V를 사용하여 Microsoft Office 2013 배포
description: App-V를 사용하여 Microsoft Office 2013 배포
author: dansimp
ms.assetid: 02df5dc8-79e2-4c5c-8398-dbfb23344ab3
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 11/02/2016
ms.openlocfilehash: c57227d531c61949f9160c27fc249db72dbc6523
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/26/2020
ms.locfileid: "10814633"
---
# <span data-ttu-id="a8397-103">App-V를 사용하여 Microsoft Office 2013 배포</span><span class="sxs-lookup"><span data-stu-id="a8397-103">Deploying Microsoft Office 2013 by Using App-V</span></span>


<span data-ttu-id="a8397-104">Microsoft Application Virtualization 5.0 이상 버전을 사용 하 여 조직의 컴퓨터에 Microsoft Office 2013을 가상화 된 응용 프로그램으로 제공 하려면이 문서의 정보를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8397-104">Use the information in this article to use Microsoft Application Virtualization 5.0, or later versions, to deliver Microsoft Office 2013 as a virtualized application to computers in your organization.</span></span> <span data-ttu-id="a8397-105">Office 2010를 제공 하기 위해 App-v를 사용 하는 방법에 대 한 자세한 내용은 [app-v를 사용 하 여 Microsoft Office 2010 배포](deploying-microsoft-office-2010-by-using-app-v.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a8397-105">For information about using App-V to deliver Office 2010, see [Deploying Microsoft Office 2010 by Using App-V](deploying-microsoft-office-2010-by-using-app-v.md).</span></span> <span data-ttu-id="a8397-106">App-v를 사용 하 여 Office 2013를 성공적으로 배포 하려면 Office 2013 및 pp에 대해 잘 알고 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8397-106">To successfully deploy Office 2013 with App-V, you need to be familiar with Office 2013 and pp-V.</span></span>

<span data-ttu-id="a8397-107">이 항목의 섹션:</span><span class="sxs-lookup"><span data-stu-id="a8397-107">This topic contains the following sections:</span></span>

-   [<span data-ttu-id="a8397-108">시작 하기 전에 알아야 할 사항</span><span class="sxs-lookup"><span data-stu-id="a8397-108">What to know before you start</span></span>](#bkmk-before-you-start)

-   [<span data-ttu-id="a8397-109">Office 배포 도구를 사용 하 여 App-v 용 Office 2013 패키지 만들기</span><span class="sxs-lookup"><span data-stu-id="a8397-109">Creating an Office 2013 package for App-V with the Office Deployment Tool</span></span>](#bkmk-create-office-pkg)

-   [<span data-ttu-id="a8397-110">앱에 대 한 Office 패키지 게시-V 5.0</span><span class="sxs-lookup"><span data-stu-id="a8397-110">Publishing the Office package for App-V 5.0</span></span>](#bkmk-pub-pkg-office)

-   [<span data-ttu-id="a8397-111">Office 앱-V 패키지 사용자 지정 및 관리</span><span class="sxs-lookup"><span data-stu-id="a8397-111">Customizing and managing Office App-V packages</span></span>](#bkmk-custmz-manage-office-pkgs)

## <a href="" id="bkmk-before-you-start"></a><span data-ttu-id="a8397-112">시작 하기 전에 알아야 할 사항</span><span class="sxs-lookup"><span data-stu-id="a8397-112">What to know before you start</span></span>


<span data-ttu-id="a8397-113">App-v를 사용 하 여 Office 2013를 배포 하기 전에 다음 계획 정보를 검토 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8397-113">Before you deploy Office 2013 by using App-V, review the following planning information.</span></span>

### <a href="" id="bkmk-supp-vers-coexist"></a><span data-ttu-id="a8397-114">지원 되는 Office 버전 및 Office 공존</span><span class="sxs-lookup"><span data-stu-id="a8397-114">Supported Office versions and Office coexistence</span></span>

<span data-ttu-id="a8397-115">다음 표를 사용 하 여 지원 되는 Office 버전에 대 한 정보를 확인 하 고 공존할 수 있는 Office 버전을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8397-115">Use the following table to get information about supported versions of Office and about running coexisting versions of Office.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="a8397-116">검토할 정보</span><span class="sxs-lookup"><span data-stu-id="a8397-116">Information to review</span></span></th>
<th align="left"><span data-ttu-id="a8397-117">설명</span><span class="sxs-lookup"><span data-stu-id="a8397-117">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><a href="planning-for-using-app-v-with-office.md#bkmk-office-vers-supp-appv" data-raw-source="[Planning for Using App-V with Office](planning-for-using-app-v-with-office.md#bkmk-office-vers-supp-appv)"><span data-ttu-id="a8397-118">Office와 App-V 사용 계획</span><span class="sxs-lookup"><span data-stu-id="a8397-118">Planning for Using App-V with Office</span></span></a></p></td>
<td align="left"><ul>
<li><p><span data-ttu-id="a8397-119">지원 되는 Office 버전</span><span class="sxs-lookup"><span data-stu-id="a8397-119">Supported versions of Office</span></span></p></li>
<li><p><span data-ttu-id="a8397-120">지원 되는 배포 유형 (예: 데스크톱, VDI (개인용 가상 데스크톱 인프라), 풀링된 VDI)</span><span class="sxs-lookup"><span data-stu-id="a8397-120">Supported deployment types (for example, desktop, personal Virtual Desktop Infrastructure (VDI), pooled VDI)</span></span></p></li>
<li><p><span data-ttu-id="a8397-121">Office 라이선스 옵션</span><span class="sxs-lookup"><span data-stu-id="a8397-121">Office licensing options</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p><a href="planning-for-using-app-v-with-office.md#bkmk-plan-coexisting" data-raw-source="[Planning for Using App-V with Office](planning-for-using-app-v-with-office.md#bkmk-plan-coexisting)"><span data-ttu-id="a8397-122">Office와 App-V 사용 계획</span><span class="sxs-lookup"><span data-stu-id="a8397-122">Planning for Using App-V with Office</span></span></a></p></td>
<td align="left"><p><span data-ttu-id="a8397-123">같은 컴퓨터에 여러 버전의 Office를 설치할 때의 고려 사항</span><span class="sxs-lookup"><span data-stu-id="a8397-123">Considerations for installing different versions of Office on the same computer</span></span></p></td>
</tr>
</tbody>
</table>



### <a href="" id="bkmk-pkg-pub-reqs"></a><span data-ttu-id="a8397-124">패키징, 게시 및 배포 요구 사항</span><span class="sxs-lookup"><span data-stu-id="a8397-124">Packaging, publishing, and deployment requirements</span></span>

<span data-ttu-id="a8397-125">App-v를 사용 하 여 Office를 배포 하기 전에 다음 요구 사항을 검토 하세요.</span><span class="sxs-lookup"><span data-stu-id="a8397-125">Before you deploy Office by using App-V, review the following requirements.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="a8397-126">작업</span><span class="sxs-lookup"><span data-stu-id="a8397-126">Task</span></span></th>
<th align="left"><span data-ttu-id="a8397-127">요구 사항</span><span class="sxs-lookup"><span data-stu-id="a8397-127">Requirement</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="a8397-128">패키징</span><span class="sxs-lookup"><span data-stu-id="a8397-128">Packaging</span></span></p></td>
<td align="left"><ul>
<li><p><span data-ttu-id="a8397-129">사용자에 게 배포 하려는 모든 Office 응용 프로그램은 단일 패키지에 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8397-129">All of the Office applications that you want to deploy to users must be in a single package.</span></span></p></li>
<li><p><span data-ttu-id="a8397-130">App-v 5.0 이상에서는 Office 배포 도구를 사용 하 여 패키지를 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8397-130">In App-V 5.0 and later, you must use the Office Deployment Tool to create packages.</span></span> <span data-ttu-id="a8397-131">Sequencer는 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a8397-131">You cannot use the Sequencer.</span></span></p></li>
<li><p><span data-ttu-id="a8397-132">Office와 함께 Microsoft Visio 2013 및 Microsoft Project 2013을 배포 하는 경우 Office와 동일한 패키지에 포함 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8397-132">If you are deploying Microsoft Visio 2013 and Microsoft Project 2013 along with Office, you must include them in the same package with Office.</span></span> <span data-ttu-id="a8397-133">자세한 내용은 <a href="#bkmk-deploy-visio-project" data-raw-source="[Deploying Visio 2013 and Project 2013 with Office](#bkmk-deploy-visio-project)"> Office를 사용 하 여 Visio 2013 및 Project 2013 배포를 참조 하세요 </a> .</span><span class="sxs-lookup"><span data-stu-id="a8397-133">For more information, see <a href="#bkmk-deploy-visio-project" data-raw-source="[Deploying Visio 2013 and Project 2013 with Office](#bkmk-deploy-visio-project)">Deploying Visio 2013 and Project 2013 with Office</a>.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="a8397-134">게시</span><span class="sxs-lookup"><span data-stu-id="a8397-134">Publishing</span></span></p></td>
<td align="left"><ul>
<li><p><span data-ttu-id="a8397-135">각 클라이언트 컴퓨터에 하나의 Office 패키지만 게시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a8397-135">You can publish only one Office package to each client computer.</span></span></p></li>
<li><p><span data-ttu-id="a8397-136">Office 패키지를 전역적으로 게시 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8397-136">You must publish the Office package globally.</span></span> <span data-ttu-id="a8397-137">사용자에 게 게시할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a8397-137">You cannot publish to the user.</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="a8397-138">예를 들어 원격 데스크톱 서비스를 사용 하 여 다음 제품을 공유 컴퓨터에 배포 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8397-138">Deploying any of the following products to a shared computer, for example, by using Remote Desktop Services:</span></span></p>
<ul>
<li><p><span data-ttu-id="a8397-139">엔터프라이즈 용 Microsoft 365 앱</span><span class="sxs-lookup"><span data-stu-id="a8397-139">Microsoft 365 Apps for enterprise</span></span></p></li>
<li><p><span data-ttu-id="a8397-140">Visio Pro for Office 365</span><span class="sxs-lookup"><span data-stu-id="a8397-140">Visio Pro for Office 365</span></span></p></li>
<li><p><span data-ttu-id="a8397-141">Project Pro for Office 365</span><span class="sxs-lookup"><span data-stu-id="a8397-141">Project Pro for Office 365</span></span></p></li>
</ul></td>
<td align="left"><p><span data-ttu-id="a8397-142">공유 컴퓨터 정품 인증을 사용 하도록 설정 해야 합니다 <a href="https://technet.microsoft.com/library/dn782860.aspx" data-raw-source="[shared computer activation](https://technet.microsoft.com/library/dn782860.aspx)"> </a> .</span><span class="sxs-lookup"><span data-stu-id="a8397-142">You must enable <a href="https://technet.microsoft.com/library/dn782860.aspx" data-raw-source="[shared computer activation](https://technet.microsoft.com/library/dn782860.aspx)">shared computer activation</a>.</span></span></p>
<p><span data-ttu-id="a8397-143">다음과 같이 볼륨 라이선스가 있는 제품을 배포 하는 경우 공유 컴퓨터 정품 인증을 사용 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a8397-143">You don’t use shared computer activation if you’re deploying a volume licensed product, such as:</span></span></p>
<ul>
<li><p><span data-ttu-id="a8397-144">Office Professional Plus 2013</span><span class="sxs-lookup"><span data-stu-id="a8397-144">Office Professional Plus 2013</span></span></p></li>
<li><p><span data-ttu-id="a8397-145">Visio Professional 2013</span><span class="sxs-lookup"><span data-stu-id="a8397-145">Visio Professional 2013</span></span></p></li>
<li><p><span data-ttu-id="a8397-146">Project Professional 2013</span><span class="sxs-lookup"><span data-stu-id="a8397-146">Project Professional 2013</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>



### <span data-ttu-id="a8397-147">패키지에서 Office 응용 프로그램 제외</span><span class="sxs-lookup"><span data-stu-id="a8397-147">Excluding Office applications from a package</span></span>

<span data-ttu-id="a8397-148">다음 표에서는 패키지에서 특정 Office 응용 프로그램을 제외 하기 위해 권장 되는 방법에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8397-148">The following table describes the recommended methods for excluding specific Office applications from a package.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="a8397-149">작업</span><span class="sxs-lookup"><span data-stu-id="a8397-149">Task</span></span></th>
<th align="left"><span data-ttu-id="a8397-150">세부 정보</span><span class="sxs-lookup"><span data-stu-id="a8397-150">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="a8397-151"><strong> </strong> Office 배포 도구를 사용 하 여 패키지를 만들 때 excludeapp 설정을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8397-151">Use the <strong>ExcludeApp</strong> setting when you create the package by using the Office Deployment Tool.</span></span></p></td>
<td align="left"><ul>
<li><p><span data-ttu-id="a8397-152">Office 배포 도구가 패키지를 만들 때 패키지에서 특정 Office 응용 프로그램을 제외할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a8397-152">Enables you to exclude specific Office applications from the package when the Office Deployment Tool creates the package.</span></span> <span data-ttu-id="a8397-153">예를 들어이 설정을 사용 하 여 Microsoft 단어만 포함 된 패키지를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a8397-153">For example, you can use this setting to create a package that contains only Microsoft Word.</span></span></p></li>
<li><p><span data-ttu-id="a8397-154">자세한 내용은 <a href="https://technet.microsoft.com/library/jj219426.aspx#bkmk-excludeappelement" data-raw-source="[ExcludeApp element](https://technet.microsoft.com/library/jj219426.aspx#bkmk-excludeappelement)"> excludeapp 요소를 참조 하세요 </a> .</span><span class="sxs-lookup"><span data-stu-id="a8397-154">For more information, see <a href="https://technet.microsoft.com/library/jj219426.aspx#bkmk-excludeappelement" data-raw-source="[ExcludeApp element](https://technet.microsoft.com/library/jj219426.aspx#bkmk-excludeappelement)">ExcludeApp element</a>.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="a8397-155">DeploymentConfig.xml 파일 수정</span><span class="sxs-lookup"><span data-stu-id="a8397-155">Modify the DeploymentConfig.xml file</span></span></p></td>
<td align="left"><ul>
<li><p><span data-ttu-id="a8397-156">패키지를 만든 후 DeploymentConfig.xml 파일을 수정 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8397-156">Modify the DeploymentConfig.xml file after the package has been created.</span></span> <span data-ttu-id="a8397-157">이 파일에는 App-v 클라이언트를 실행 하는 컴퓨터의 모든 사용자에 대 한 기본 패키지 설정이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a8397-157">This file contains the default package settings for all users on a computer that is running the App-V Client.</span></span></p></li>
<li><p><span data-ttu-id="a8397-158">자세한 내용은 <a href="#bkmk-disable-office-apps" data-raw-source="[Disabling Office 2013 applications](#bkmk-disable-office-apps)"> Office 2013 응용 프로그램 사용 안 함을 참조 하세요 </a> .</span><span class="sxs-lookup"><span data-stu-id="a8397-158">For more information, see <a href="#bkmk-disable-office-apps" data-raw-source="[Disabling Office 2013 applications](#bkmk-disable-office-apps)">Disabling Office 2013 applications</a>.</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>



## <a href="" id="bkmk-create-office-pkg"></a><span data-ttu-id="a8397-159">Office 배포 도구를 사용 하 여 App-v 용 Office 2013 패키지 만들기</span><span class="sxs-lookup"><span data-stu-id="a8397-159">Creating an Office 2013 package for App-V with the Office Deployment Tool</span></span>


<span data-ttu-id="a8397-160">App-v 5.0 이상 버전의 Office 2013 패키지를 만들려면 다음 단계를 완료 하세요.</span><span class="sxs-lookup"><span data-stu-id="a8397-160">Complete the following steps to create an Office 2013 package for App-V 5.0 or later.</span></span>

**<span data-ttu-id="a8397-161">중요</span><span class="sxs-lookup"><span data-stu-id="a8397-161">Important</span></span>**  
<span data-ttu-id="a8397-162">App-v 5.0 이상에서는 패키지를 만들기 위한 Office 배포 도구가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8397-162">In App-V 5.0 and later, you must the Office Deployment Tool to create a package.</span></span> <span data-ttu-id="a8397-163">Sequencer를 사용 하 여 패키지를 만들 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a8397-163">You cannot use the Sequencer to create packages.</span></span>


### <span data-ttu-id="a8397-164">Office 배포 도구를 사용 하기 위한 필수 구성 요소 검토</span><span class="sxs-lookup"><span data-stu-id="a8397-164">Review prerequisites for using the Office Deployment Tool</span></span>

<span data-ttu-id="a8397-165">Office 배포 도구를 설치 하는 컴퓨터에는 다음이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8397-165">The computer on which you are installing the Office Deployment Tool must have:</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="a8397-166">요소일</span><span class="sxs-lookup"><span data-stu-id="a8397-166">Prerequisite</span></span></th>
<th align="left"><span data-ttu-id="a8397-167">설명</span><span class="sxs-lookup"><span data-stu-id="a8397-167">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="a8397-168">필수 구성 요소 소프트웨어</span><span class="sxs-lookup"><span data-stu-id="a8397-168">Prerequisite software</span></span></p></td>
<td align="left"><p><span data-ttu-id="a8397-169">.Net Framework 4</span><span class="sxs-lookup"><span data-stu-id="a8397-169">.Net Framework 4</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="a8397-170">지원되는 운영 체제</span><span class="sxs-lookup"><span data-stu-id="a8397-170">Supported operating systems</span></span></p></td>
<td align="left"><ul>
<li><p><span data-ttu-id="a8397-171">64 비트 버전의 Windows 8</span><span class="sxs-lookup"><span data-stu-id="a8397-171">64-bit version of Windows 8</span></span></p></li>
<li><p><span data-ttu-id="a8397-172">64 비트 버전의 Windows 7</span><span class="sxs-lookup"><span data-stu-id="a8397-172">64-bit version of Windows 7</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


**<span data-ttu-id="a8397-173">참고</span><span class="sxs-lookup"><span data-stu-id="a8397-173">Note</span></span>**  
<span data-ttu-id="a8397-174">이 항목에서 "Office 2013 App-v 패키지" 라는 용어는 구독 라이선스 및 볼륨 라이선스를 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8397-174">In this topic, the term “Office 2013 App-V package” refers to subscription licensing and volume licensing.</span></span>


### <span data-ttu-id="a8397-175">Office 배포 도구를 사용 하 여 Office 2013 앱-V 패키지 만들기</span><span class="sxs-lookup"><span data-stu-id="a8397-175">Create Office 2013 App-V Packages Using Office Deployment Tool</span></span>

<span data-ttu-id="a8397-176">Office 배포 도구를 사용 하 여 Office 2013 앱-V 패키지를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="a8397-176">You create Office 2013 App-V packages by using the Office Deployment Tool.</span></span> <span data-ttu-id="a8397-177">다음 지침에서는 볼륨 라이선스 또는 구독 라이선스를 사용 하 여 Office 2013 App-v 패키지를 만드는 방법에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8397-177">The following instructions explain how to create an Office 2013 App-V package with Volume Licensing or Subscription Licensing.</span></span>

<span data-ttu-id="a8397-178">64 비트 Windows 컴퓨터에서 Office 2013 앱-V 패키지를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="a8397-178">Create Office 2013 App-V packages on 64-bit Windows computers.</span></span> <span data-ttu-id="a8397-179">Office 2013 앱-V 패키지는 일단 만들어지면 32 비트 및 64 비트 Windows 7 및 Windows 8 컴퓨터에서 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a8397-179">Once created, the Office 2013 App-V package will run on 32-bit and 64-bit Windows 7 and Windows 8 computers.</span></span>

### <span data-ttu-id="a8397-180">Office 배포 도구 다운로드</span><span class="sxs-lookup"><span data-stu-id="a8397-180">Download the Office Deployment Tool</span></span>

<span data-ttu-id="a8397-181">Office 2013 앱-V 패키지는 office 2013 App-v 패키지를 생성 하는 Office 배포 도구를 사용 하 여 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="a8397-181">Office 2013 App-V Packages are created using the Office Deployment Tool, which generates an Office 2013 App-V Package.</span></span> <span data-ttu-id="a8397-182">앱-V 시퀀서를 통해 패키지를 만들거나 수정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a8397-182">The package cannot be created or modified through the App-V sequencer.</span></span> <span data-ttu-id="a8397-183">패키지 만들기를 시작 하려면 다음을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8397-183">To begin package creation:</span></span>

1.  <span data-ttu-id="a8397-184">[간편 실행을 위한 Office 배포 도구](https://www.microsoft.com/download/details.aspx?id=36778)를 다운로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8397-184">Download the [Office Deployment Tool for Click-to-Run](https://www.microsoft.com/download/details.aspx?id=36778).</span></span>

2.  <span data-ttu-id="a8397-185">.Exe 파일을 실행 하 고 원하는 위치에 해당 기능을 추출 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8397-185">Run the .exe file and extract its features into the desired location.</span></span> <span data-ttu-id="a8397-186">이 프로세스를 더 쉽게 하려면 기능을 저장할 공유 네트워크 폴더를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a8397-186">To make this process easier, you can create a shared network folder where the features will be saved.</span></span>

    <span data-ttu-id="a8397-187">예: \\\\Server\\오피스 2013</span><span class="sxs-lookup"><span data-stu-id="a8397-187">Example: \\\\Server\\Office2013</span></span>

3.  <span data-ttu-id="a8397-188">setup.exe 및 configuration.xml 파일이 존재 하며 지정한 위치에 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8397-188">Check that a setup.exe and a configuration.xml file exist and are in the location you specified.</span></span>

### <span data-ttu-id="a8397-189">Office 2013 응용 프로그램 다운로드</span><span class="sxs-lookup"><span data-stu-id="a8397-189">Download Office 2013 applications</span></span>

<span data-ttu-id="a8397-190">Office 배포 도구를 다운로드 한 후에이를 사용 하 여 최신 Office 2013 응용 프로그램을 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a8397-190">After you download the Office Deployment Tool, you can use it to get the latest Office 2013 applications.</span></span> <span data-ttu-id="a8397-191">Office 응용 프로그램을 가져온 후 Office 2013 App-v 패키지를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="a8397-191">After getting the Office applications, you create the Office 2013 App-V package.</span></span>

<span data-ttu-id="a8397-192">Office 배포 도구에 포함 된 XML 파일은 포함 된 언어 및 Office 응용 프로그램과 같은 제품 세부 정보를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8397-192">The XML file that is included in the Office Deployment Tool specifies the product details, such as the languages and Office applications included.</span></span>

1. <span data-ttu-id="a8397-193">**예제 XML 구성 파일을 사용자 지정 합니다.** Office 배포 도구를 사용 하 여 다운로드 한 샘플 XML 구성 파일을 사용 하 여 Office 응용 프로그램을 사용자 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8397-193">**Customize the sample XML configuration file:** Use the sample XML configuration file that you downloaded with the Office Deployment Tool to customize the Office applications:</span></span>

   1. <span data-ttu-id="a8397-194">메모장 또는 즐겨 찾는 텍스트 편집기에서 샘플 XML 파일을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="a8397-194">Open the sample XML file in Notepad or your favorite text editor.</span></span>

   2. <span data-ttu-id="a8397-195">샘플 configuration.xml 파일을 열어 편집할 수 있는 상태에서 Office 2013 응용 프로그램을 저장 하는 제품, 언어, 경로를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8397-195">With the sample configuration.xml file open and ready for editing, you can specify products, languages, and the path to which you save the Office 2013 applications.</span></span> <span data-ttu-id="a8397-196">다음은 configuration.xml 파일의 기본 예입니다.</span><span class="sxs-lookup"><span data-stu-id="a8397-196">The following is a basic example of the configuration.xml file:</span></span>

      ```xml
      <Configuration>
         <Add SourcePath= ”\\Server\Office2013” OfficeClientEdition="32" >
          <Product ID="O365ProPlusRetail ">
            <Language ID="en-us" />
          </Product>
          <Product ID="VisioProRetail">
            <Language ID="en-us" />
          </Product>
        </Add>
      </Configuration>
      ```

      **<span data-ttu-id="a8397-197">참고</span><span class="sxs-lookup"><span data-stu-id="a8397-197">Note</span></span>**  
      <span data-ttu-id="a8397-198">구성 XML은 샘플 XML 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="a8397-198">The configuration XML is a sample XML file.</span></span> <span data-ttu-id="a8397-199">파일에는 주석 처리 된 줄이 포함 됩니다. 이러한 줄을 "주석 처리" 하 여 파일에 대 한 추가 설정을 사용자 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a8397-199">The file includes lines that are commented out. You can “uncomment” these lines to customize additional settings with the file.</span></span>

      <span data-ttu-id="a8397-200">위의 XML 구성 파일은 Visio ProPlus를 포함 하 여 Office 2013 ProPlus 32 비트 에디션을 영어로 다운로드 하 여 Office 응용 프로그램이 저장 되는 위치인 \\\\server\\Office 2013에이를 설치 하도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8397-200">The above XML configuration file specifies that Office 2013 ProPlus 32-bit edition, including Visio ProPlus, will be downloaded in English to the \\\\server\\Office 2013, which is the location where Office applications will be saved to.</span></span> <span data-ttu-id="a8397-201">응용 프로그램의 제품 ID는 Office의 최종 라이선스에 영향을 주지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a8397-201">Note that the Product ID of the applications will not affect the final licensing of Office.</span></span> <span data-ttu-id="a8397-202">이후 단계에서 라이선스를 지정 하 여 다양 한 라이선스를 포함 하는 Office 2013 앱-V 패키지를 같은 응용 프로그램에서 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a8397-202">Office 2013 App-V packages with various licensing can be created from the same applications through specifying licensing in a later stage.</span></span> <span data-ttu-id="a8397-203">아래 표에는 XML 파일의 사용자 지정 가능한 특성 및 요소가 요약 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a8397-203">The table below summarizes the customizable attributes and elements of XML file:</span></span>

      <table>
      <colgroup>
      <col width="33%" />
      <col width="33%" />
      <col width="33%" />
      </colgroup>
      <thead>
      <tr class="header">
      <th align="left"><span data-ttu-id="a8397-204">입력</span><span class="sxs-lookup"><span data-stu-id="a8397-204">Input</span></span></th>
      <th align="left"><span data-ttu-id="a8397-205">설명</span><span class="sxs-lookup"><span data-stu-id="a8397-205">Description</span></span></th>
      <th align="left"><span data-ttu-id="a8397-206">예</span><span class="sxs-lookup"><span data-stu-id="a8397-206">Example</span></span></th>
      </tr>
      </thead>
      <tbody>
      <tr class="odd">
      <td align="left"><p><span data-ttu-id="a8397-207">요소 추가</span><span class="sxs-lookup"><span data-stu-id="a8397-207">Add element</span></span></p></td>
      <td align="left"><p><span data-ttu-id="a8397-208">패키지에 포함할 제품 및 언어를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8397-208">Specifies the products and languages to include in the package.</span></span></p></td>
      <td align="left"><p><span data-ttu-id="a8397-209">해당 없음</span><span class="sxs-lookup"><span data-stu-id="a8397-209">N/A</span></span></p></td>
      </tr>
      <tr class="even">
      <td align="left"><p><span data-ttu-id="a8397-210">OfficeClientEdition (Add 요소의 특성)</span><span class="sxs-lookup"><span data-stu-id="a8397-210">OfficeClientEdition (attribute of Add element)</span></span></p></td>
      <td align="left"><p><span data-ttu-id="a8397-211">사용할 Office 2013 제품 버전 (32 비트 또는 64-비트)을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8397-211">Specifies the edition of Office 2013 product to use: 32-bit or 64-bit.</span></span> <span data-ttu-id="a8397-212"><strong>OfficeClientEdition </strong> 가 유효한 값으로 설정 되지 않은 경우 작업이 실패 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8397-212">The operation fails if <strong>OfficeClientEdition</strong> is not set to a valid value.</span></span></p></td>
      <td align="left"><p><strong><span data-ttu-id="a8397-213">OfficeClientEdition </strong> = &quot; 32&quot;</span><span class="sxs-lookup"><span data-stu-id="a8397-213">OfficeClientEdition</strong>=&quot;32&quot;</span></span></p>
      <p><strong><span data-ttu-id="a8397-214">OfficeClientEdition </strong> = &quot; 64&quot;</span><span class="sxs-lookup"><span data-stu-id="a8397-214">OfficeClientEdition</strong>=&quot;64&quot;</span></span></p></td>
      </tr>
      <tr class="odd">
      <td align="left"><p><span data-ttu-id="a8397-215">Product 요소</span><span class="sxs-lookup"><span data-stu-id="a8397-215">Product element</span></span></p></td>
      <td align="left"><p><span data-ttu-id="a8397-216">응용 프로그램을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8397-216">Specifies the application.</span></span> <span data-ttu-id="a8397-217">여기에 프로젝트 2013 및 Visio 2013을 여기에 지정 하 여 응용 프로그램에 포함 시킬 추가 된 제품이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8397-217">Project 2013 and Visio 2013 must be specified here as an added product to be included in the applications.</span></span></p></td>
      <td align="left"><p><code>Product ID =&quot;O365ProPlusRetail &quot;</code></p>
      <p><code>Product ID =&quot;VisioProRetail&quot;</code></p>
      <p><code>Product ID =&quot;ProjectProRetail&quot;</code></p>
      <p><code>Product ID =&quot;ProPlusVolume&quot;</code></p>
      <p><code>Product ID =&quot;VisioProVolume&quot;</code></p>
      <p><code>Product ID = &quot;ProjectProVolume&quot;</code></p></td>
      </tr>
      <tr class="even">
      <td align="left"><p><span data-ttu-id="a8397-218">Language 요소</span><span class="sxs-lookup"><span data-stu-id="a8397-218">Language element</span></span></p></td>
      <td align="left"><p><span data-ttu-id="a8397-219">응용 프로그램에서 지원 되는 언어를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8397-219">Specifies the language supported in the applications</span></span></p></td>
      <td align="left"><p><code>Language ID=&quot;en-us&quot;</code></p></td>
      </tr>
      <tr class="odd">
      <td align="left"><p><span data-ttu-id="a8397-220">버전 (요소 추가의 특성)</span><span class="sxs-lookup"><span data-stu-id="a8397-220">Version (attribute of Add element)</span></span></p></td>
      <td align="left"><p><span data-ttu-id="a8397-221">선택 사항.</span><span class="sxs-lookup"><span data-stu-id="a8397-221">Optional.</span></span> <span data-ttu-id="a8397-222">패키지에 사용할 빌드를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8397-222">Specifies a build to use for the package</span></span></p>
      <p><span data-ttu-id="a8397-223">Office 원본의 v32.CAB에 정의 된 최신 광고 빌드를 기본값으로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8397-223">Defaults to latest advertised build (as defined in v32.CAB at the Office source).</span></span></p></td>
      <td align="left"><p><code>15.1.2.3</code></p></td>
      </tr>
      <tr class="even">
      <td align="left"><p><span data-ttu-id="a8397-224">SourcePath (Add 요소의 특성)</span><span class="sxs-lookup"><span data-stu-id="a8397-224">SourcePath (attribute of Add element)</span></span></p></td>
      <td align="left"><p><span data-ttu-id="a8397-225">응용 프로그램이 저장 되는 위치를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8397-225">Specifies the location in which the applications will be saved to.</span></span></p></td>
      <td align="left"><p><code>Sourcepath = &quot;\Server\Office2013”</code></p></td>
      </tr>
      </tbody>
      </table>

      <span data-ttu-id="a8397-226">원하는 제품, 언어, 그리고 Office 2013 응용 프로그램이 저장 되는 위치를 지정 하도록 configuration.xml 파일을 편집한 후에는 구성 파일 (예: Customconfig.xml)을 저장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a8397-226">After editing the configuration.xml file to specify the desired product, languages, and also the location which the Office 2013 applications will be saved onto, you can save the configuration file, for example, as Customconfig.xml.</span></span>

2. <span data-ttu-id="a8397-227">**지정 된 위치에 응용 프로그램을 다운로드 합니다.** 관리자 권한 명령 프롬프트 및 64 비트 운영 체제를 사용 하 여 나중에 App-v 패키지로 변환 될 Office 2013 응용 프로그램을 다운로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8397-227">**Download the applications into the specified location:** Use an elevated command prompt and a 64 bit operating system to download the Office 2013 applications that will later be converted into an App-V package.</span></span> <span data-ttu-id="a8397-228">다음은 세부 정보에 대 한 설명이 포함 된 예제 명령입니다.</span><span class="sxs-lookup"><span data-stu-id="a8397-228">Below is an example command with description of details:</span></span>

   ``` syntax
   \\server\Office2013\setup.exe /download \\server\Office2013\Customconfig.xml
   ```

   <span data-ttu-id="a8397-229">예제:</span><span class="sxs-lookup"><span data-stu-id="a8397-229">In the example:</span></span>

   <table>
   <colgroup>
   <col width="50%" />
   <col width="50%" />
   </colgroup>
   <tbody>
   <tr class="odd">
   <td align="left"><p><strong><span data-ttu-id="a8397-230">\server\Office2013</span><span class="sxs-lookup"><span data-stu-id="a8397-230">\server\Office2013</span></span></strong></p></td>
   <td align="left"><p><span data-ttu-id="a8397-231">은 Office 배포 도구와 사용자 지정 Configuration.xml 파일 Customconfig.xml 포함 하는 네트워크 공유 위치입니다.</span><span class="sxs-lookup"><span data-stu-id="a8397-231">is the network share location that contains the Office Deployment Tool and the custom Configuration.xml file, Customconfig.xml.</span></span></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><strong><span data-ttu-id="a8397-232">Setup.exe</span><span class="sxs-lookup"><span data-stu-id="a8397-232">Setup.exe</span></span></strong></p></td>
   <td align="left"><p><span data-ttu-id="a8397-233">Office 배포 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="a8397-233">is the Office Deployment Tool.</span></span></p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><strong><span data-ttu-id="a8397-234">/download</span><span class="sxs-lookup"><span data-stu-id="a8397-234">/download</span></span></strong></p></td>
   <td align="left"><p><span data-ttu-id="a8397-235">customConfig.xml 파일에서 지정 하는 Office 2013 응용 프로그램을 다운로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8397-235">downloads the Office 2013 applications that you specify in the customConfig.xml file.</span></span> <span data-ttu-id="a8397-236">나중에 볼륨 라이선스를 사용 하 여 Office 2013 앱-V 패키지에서 이러한 비트를 변환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a8397-236">These bits can be later converted in an Office 2013 App-V package with Volume Licensing.</span></span></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><strong><span data-ttu-id="a8397-237">\server\Office2013\Customconfig.xml</span><span class="sxs-lookup"><span data-stu-id="a8397-237">\server\Office2013\Customconfig.xml</span></span></strong></p></td>
   <td align="left"><p><span data-ttu-id="a8397-238">다운로드 프로세스를 완료 하는 데 필요한 XML 구성 파일을 전달 합니다 (이 예제에서는 customconfig.xml.</span><span class="sxs-lookup"><span data-stu-id="a8397-238">passes the XML configuration file required to complete the download process, in this example, customconfig.xml.</span></span> <span data-ttu-id="a8397-239">다운로드 명령을 사용한 후에는 구성 xml 파일에 지정 된 위치에서 Office 응용 프로그램을 찾을 수 있습니다 (이 예제에서는 \Server\Office2013.).</span><span class="sxs-lookup"><span data-stu-id="a8397-239">After using the download command, Office applications should be found in the location specified in the configuration xml file, in this example \Server\Office2013.</span></span></p></td>
   </tr>
   </tbody>
   </table>



### <span data-ttu-id="a8397-240">Office 응용 프로그램을 앱-V 패키지로 변환</span><span class="sxs-lookup"><span data-stu-id="a8397-240">Convert the Office applications into an App-V package</span></span>

<span data-ttu-id="a8397-241">Office 배포 도구를 통해 Office 2013 응용 프로그램을 다운로드 한 후 office 배포 도구를 사용 하 여 office 2013 App-v 패키지로 전환 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8397-241">After you download the Office 2013 applications through the Office Deployment Tool, use the Office Deployment Tool to convert them into an Office 2013 App-V package.</span></span> <span data-ttu-id="a8397-242">라이선스 모델에 해당 하는 단계를 완료 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8397-242">Complete the steps that correspond to your licensing model.</span></span>

**<span data-ttu-id="a8397-243">수행 해야 하는 작업에 대 한 요약:</span><span class="sxs-lookup"><span data-stu-id="a8397-243">Summary of what you’ll need to do:</span></span>**

-   <span data-ttu-id="a8397-244">64 비트 Windows 컴퓨터에서 Office 2013 앱-V 패키지를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="a8397-244">Create the Office 2013 App-V packages on 64-bit Windows computers.</span></span> <span data-ttu-id="a8397-245">그러나 패키지는 32 비트 및 64 비트 Windows 7 및 Windows 8 컴퓨터에서 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a8397-245">However, the package will run on 32-bit and 64-bit Windows 7 and Windows 8 computers.</span></span>

-   <span data-ttu-id="a8397-246">Office 배포 도구를 사용 하 여 구독 라이선스 패키지 또는 볼륨 라이선스에 대 한 Office 앱-V 패키지를 만든 다음 CustomConfig.xml 구성 파일을 수정 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8397-246">Create an Office App-V package for either Subscription Licensing package or Volume Licensing by using the Office Deployment Tool, and then modify the CustomConfig.xml configuration file.</span></span>

    <span data-ttu-id="a8397-247">다음 표에는 사용 중인 라이선스 모델의 CustomConfig.xml 파일에 입력 해야 하는 값이 요약 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a8397-247">The following table summarizes the values you need to enter in the CustomConfig.xml file for the licensing model you’re using.</span></span> <span data-ttu-id="a8397-248">표 다음에 나오는 섹션의 단계에서는 필요한 정확한 항목을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8397-248">The steps in the sections that follow the table will specify the exact entries you need to make.</span></span>

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="a8397-249">제품 ID</span><span class="sxs-lookup"><span data-stu-id="a8397-249">Product ID</span></span></th>
<th align="left"><span data-ttu-id="a8397-250">볼륨 라이선스</span><span class="sxs-lookup"><span data-stu-id="a8397-250">Volume Licensing</span></span></th>
<th align="left"><span data-ttu-id="a8397-251">구독 라이선스</span><span class="sxs-lookup"><span data-stu-id="a8397-251">Subscription Licensing</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="a8397-252">Office 2013</span><span class="sxs-lookup"><span data-stu-id="a8397-252">Office 2013</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="a8397-253">ProPlusVolume</span><span class="sxs-lookup"><span data-stu-id="a8397-253">ProPlusVolume</span></span></p></td>
<td align="left"><p><span data-ttu-id="a8397-254">O365ProPlusRetail</span><span class="sxs-lookup"><span data-stu-id="a8397-254">O365ProPlusRetail</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="a8397-255">Office 2013 (Visio 2013)</span><span class="sxs-lookup"><span data-stu-id="a8397-255">Office 2013 with Visio 2013</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="a8397-256">ProPlusVolume</span><span class="sxs-lookup"><span data-stu-id="a8397-256">ProPlusVolume</span></span></p>
<p><span data-ttu-id="a8397-257">VisioProVolume</span><span class="sxs-lookup"><span data-stu-id="a8397-257">VisioProVolume</span></span></p></td>
<td align="left"><p><span data-ttu-id="a8397-258">O365ProPlusRetail</span><span class="sxs-lookup"><span data-stu-id="a8397-258">O365ProPlusRetail</span></span></p>
<p><span data-ttu-id="a8397-259">VisioProRetail</span><span class="sxs-lookup"><span data-stu-id="a8397-259">VisioProRetail</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="a8397-260">Office 2013 (Visio 2013 및 Project 2013)</span><span class="sxs-lookup"><span data-stu-id="a8397-260">Office 2013 with Visio 2013 and Project 2013</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="a8397-261">ProPlusVolume</span><span class="sxs-lookup"><span data-stu-id="a8397-261">ProPlusVolume</span></span></p>
<p><span data-ttu-id="a8397-262">VisioProVolume</span><span class="sxs-lookup"><span data-stu-id="a8397-262">VisioProVolume</span></span></p>
<p><span data-ttu-id="a8397-263">ProjectProVolume</span><span class="sxs-lookup"><span data-stu-id="a8397-263">ProjectProVolume</span></span></p></td>
<td align="left"><p><span data-ttu-id="a8397-264">O365ProPlusRetail</span><span class="sxs-lookup"><span data-stu-id="a8397-264">O365ProPlusRetail</span></span></p>
<p><span data-ttu-id="a8397-265">VisioProRetail</span><span class="sxs-lookup"><span data-stu-id="a8397-265">VisioProRetail</span></span></p>
<p><span data-ttu-id="a8397-266">ProjectProRetail</span><span class="sxs-lookup"><span data-stu-id="a8397-266">ProjectProRetail</span></span></p></td>
</tr>
</tbody>
</table>



**<span data-ttu-id="a8397-267">Office 응용 프로그램을 앱-V 패키지로 변환 하는 방법</span><span class="sxs-lookup"><span data-stu-id="a8397-267">How to convert the Office applications into an App-V package</span></span>**

1. <span data-ttu-id="a8397-268">메모장에서 CustomConfig.xml 파일을 다시 열고 파일을 다음과 같이 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8397-268">In Notepad, reopen the CustomConfig.xml file, and make the following changes to the file:</span></span>

   <table>
   <colgroup>
   <col width="50%" />
   <col width="50%" />
   </colgroup>
   <thead>
   <tr class="header">
   <th align="left"><span data-ttu-id="a8397-269">매개 변수</span><span class="sxs-lookup"><span data-stu-id="a8397-269">Parameter</span></span></th>
   <th align="left"><span data-ttu-id="a8397-270">값을 변경할 대상</span><span class="sxs-lookup"><span data-stu-id="a8397-270">What to change the value to</span></span></th>
   </tr>
   </thead>
   <tbody>
   <tr class="odd">
   <td align="left"><p><span data-ttu-id="a8397-271">SourcePath</span><span class="sxs-lookup"><span data-stu-id="a8397-271">SourcePath</span></span></p></td>
   <td align="left"><p><span data-ttu-id="a8397-272">이전에 다운로드 한 Office 응용 프로그램을 가리킵니다.</span><span class="sxs-lookup"><span data-stu-id="a8397-272">Point to the Office applications downloaded earlier.</span></span></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><span data-ttu-id="a8397-273">ProductID</span><span class="sxs-lookup"><span data-stu-id="a8397-273">ProductID</span></span></p></td>
   <td align="left"><p><span data-ttu-id="a8397-274">다음 예와 같이 라이선스 유형을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8397-274">Specify the type of licensing, as shown in the following examples:</span></span></p>
   <ul>
   <li><p><span data-ttu-id="a8397-275">구독 라이선스</span><span class="sxs-lookup"><span data-stu-id="a8397-275">Subscription Licensing</span></span></p>
   <pre class="syntax" space="preserve"><code>&lt;Configuration&gt;
      &lt;Add SourcePath= &quot;\server\Office 2013&quot; OfficeClientEdition=&quot;32&quot; &gt;
       &lt;Product ID=&quot;O365ProPlusRetail&quot;&gt;
         &lt;Language ID=&quot;en-us&quot; /&gt;
       &lt;/Product&gt;
       &lt;Product ID=&quot;VisioProRetail&quot;&gt;
         &lt;Language ID=&quot;en-us&quot; /&gt;
       &lt;/Product&gt;
     &lt;/Add&gt;
   &lt;/Configuration&gt; </code></pre>
   <p><span data-ttu-id="a8397-276">이 예제에서는 구독 라이선스를 사용 하 여 패키지를 만들기 위해 다음과 같이 변경 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="a8397-276">In this example, the following changes were made to create a package with Subscription licensing:</span></span></p>
   <table>
   <colgroup>
   <col width="50%" />
   <col width="50%" />
   </colgroup>
   <tbody>
   <tr class="odd">
   <td align="left"><p><strong><span data-ttu-id="a8397-277">SourcePath</span><span class="sxs-lookup"><span data-stu-id="a8397-277">SourcePath</span></span></strong></p></td>
   <td align="left"><p><span data-ttu-id="a8397-278">는 이전에 다운로드 된 Office 응용 프로그램을 가리키도록 변경 된 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="a8397-278">is the path, which was changed to point to the Office applications that were downloaded earlier.</span></span></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><strong><span data-ttu-id="a8397-279">제품 ID</span><span class="sxs-lookup"><span data-stu-id="a8397-279">Product ID</span></span></strong></p></td>
   <td align="left"><p><span data-ttu-id="a8397-280">(으)로 변경 되었습니다 <code>O365ProPlusRetail</code> .</span><span class="sxs-lookup"><span data-stu-id="a8397-280">for Office was changed to <code>O365ProPlusRetail</code>.</span></span></p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><strong><span data-ttu-id="a8397-281">제품 ID</span><span class="sxs-lookup"><span data-stu-id="a8397-281">Product ID</span></span></strong></p></td>
   <td align="left"><p><span data-ttu-id="a8397-282">Visio는으로 변경 되었습니다 <code>VisioProRetail</code> .</span><span class="sxs-lookup"><span data-stu-id="a8397-282">for Visio was changed to <code>VisioProRetail</code>.</span></span></p></td>
   </tr>
   </tbody>
   </table>
   <p> </p>
   <p></p></li>
   <li><p><span data-ttu-id="a8397-283">볼륨 라이선스</span><span class="sxs-lookup"><span data-stu-id="a8397-283">Volume Licensing</span></span></p>
   <pre class="syntax" space="preserve"><code>&lt;Configuration&gt;
      &lt;Add SourcePath= &quot;\Server\Office2013&quot; OfficeClientEdition=&quot;32&quot; &gt;
       &lt;Product ID=&quot;ProPlusVolume&quot;&gt;
         &lt;Language ID=&quot;en-us&quot; /&gt;
       &lt;/Product&gt;
       &lt;Product ID=&quot;VisioProVolume&quot;&gt;
         &lt;Language ID=&quot;en-us&quot; /&gt;
       &lt;/Product&gt;
     &lt;/Add&gt;
   &lt;/Configuration&gt;</code></pre>
   <p><span data-ttu-id="a8397-284">이 예제에서는 볼륨 라이선스를 사용 하 여 패키지를 만들기 위해 다음과 같이 변경 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="a8397-284">In this example, the following changes were made to create a package with Volume licensing:</span></span></p>
   <table>
   <colgroup>
   <col width="50%" />
   <col width="50%" />
   </colgroup>
   <tbody>
   <tr class="odd">
   <td align="left"><p><strong><span data-ttu-id="a8397-285">SourcePath</span><span class="sxs-lookup"><span data-stu-id="a8397-285">SourcePath</span></span></strong></p></td>
   <td align="left"><p><span data-ttu-id="a8397-286">는 이전에 다운로드 된 Office 응용 프로그램을 가리키도록 변경 된 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="a8397-286">is the path, which was changed to point to the Office applications that were downloaded earlier.</span></span></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><strong><span data-ttu-id="a8397-287">제품 ID</span><span class="sxs-lookup"><span data-stu-id="a8397-287">Product ID</span></span></strong></p></td>
   <td align="left"><p><span data-ttu-id="a8397-288">(으)로 변경 되었습니다 <code>ProPlusVolume</code> .</span><span class="sxs-lookup"><span data-stu-id="a8397-288">for Office was changed to <code>ProPlusVolume</code>.</span></span></p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><strong><span data-ttu-id="a8397-289">제품 ID</span><span class="sxs-lookup"><span data-stu-id="a8397-289">Product ID</span></span></strong></p></td>
   <td align="left"><p><span data-ttu-id="a8397-290">Visio는으로 변경 되었습니다 <code>VisioProVolume</code> .</span><span class="sxs-lookup"><span data-stu-id="a8397-290">for Visio was changed to <code>VisioProVolume</code>.</span></span></p></td>
   </tr>
   </tbody>
   </table>
   <p> </p>
   <p></p></li>
   </ul></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><span data-ttu-id="a8397-291">ExcludeApp (선택 사항)</span><span class="sxs-lookup"><span data-stu-id="a8397-291">ExcludeApp (optional)</span></span></p></td>
   <td align="left"><p><span data-ttu-id="a8397-292">Office 배포 도구가 만드는 App-v 패키지에 포함 하지 않을 Office 프로그램을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a8397-292">Lets you specify Office programs that you don’t want included in the App-V package that the Office Deployment Tool creates.</span></span> <span data-ttu-id="a8397-293">예를 들어 Access 및 InfoPath는 제외할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a8397-293">For example, you can exclude Access and InfoPath.</span></span></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><span data-ttu-id="a8397-294">PACKAGEGUID (선택 사항)</span><span class="sxs-lookup"><span data-stu-id="a8397-294">PACKAGEGUID (optional)</span></span></p></td>
   <td align="left"><p><span data-ttu-id="a8397-295">기본적으로 Office 배포 도구에서 만든 모든 App-v 패키지는 동일한 App-v 패키지 ID를 공유 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8397-295">By default, all App-V packages created by the Office Deployment Tool share the same App-V Package ID.</span></span> <span data-ttu-id="a8397-296">PACKAGEGUID를 사용 하 여 각 패키지에 대해 다른 패키지 ID를 지정할 수 있으며,이를 통해 Office 배포 도구에서 만든 여러 App-v 패키지를 게시 하 고 App-v 서버를 사용 하 여 관리 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8397-296">You can use PACKAGEGUID to specify a different package ID for each package, which allows you to publish multiple App-V packages, created by the Office Deployment Tool, and manage them by using the App-V Server.</span></span></p>
   <p><span data-ttu-id="a8397-297">이 매개 변수를 사용 하는 경우 사용자 마다 다른 패키지를 만드는 경우를 예로 들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a8397-297">An example of when to use this parameter is if you create different packages for different users.</span></span> <span data-ttu-id="a8397-298">예를 들어 일부 사용자를 위해 Office 2013만 사용 하 여 패키지를 만들고 다른 사용자 집합에 대해 Office 2013 및 Visio 2013을 사용 하 여 다른 패키지를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a8397-298">For example, you can create a package with just Office 2013 for some users, and create another package with Office 2013 and Visio 2013 for another set of users.</span></span></p>
   <div class="alert">
   <strong><span data-ttu-id="a8397-299">참고</span><span class="sxs-lookup"><span data-stu-id="a8397-299">Note</span></span></strong><br/><p><span data-ttu-id="a8397-300">고유한 패키지 Id를 사용 하는 경우에도 단일 장치에 하나의 앱 V 패키지만 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a8397-300">Even if you use unique package IDs, you can still deploy only one App-V package to a single device.</span></span></p>
   </div>
   <div>

   </div></td>
   </tr>
   </tbody>
   </table>



2. <span data-ttu-id="a8397-301">/Packager 명령을 사용 하 여 Office 응용 프로그램을 Office 2013 App-v 패키지로 변환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a8397-301">Use the /packager command to convert the Office applications to an Office 2013 App-V package.</span></span>

   <span data-ttu-id="a8397-302">예:</span><span class="sxs-lookup"><span data-stu-id="a8397-302">For example:</span></span>

   ``` syntax
   \\server\Office2013\setup.exe /packager \\server\Office2013\Customconfig.xml  \\server\share\Office2013AppV
   ```

   <span data-ttu-id="a8397-303">예제:</span><span class="sxs-lookup"><span data-stu-id="a8397-303">In the example:</span></span>

   <table>
   <colgroup>
   <col width="50%" />
   <col width="50%" />
   </colgroup>
   <tbody>
   <tr class="odd">
   <td align="left"><p><strong><span data-ttu-id="a8397-304">\server\Office2013</span><span class="sxs-lookup"><span data-stu-id="a8397-304">\server\Office2013</span></span></strong></p></td>
   <td align="left"><p><span data-ttu-id="a8397-305">은 Office 배포 도구와 사용자 지정 Configuration.xml 파일 Customconfig.xml 포함 하는 네트워크 공유 위치입니다.</span><span class="sxs-lookup"><span data-stu-id="a8397-305">is the network share location that contains the Office Deployment Tool and the custom Configuration.xml file, Customconfig.xml.</span></span></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><strong><span data-ttu-id="a8397-306">Setup.exe</span><span class="sxs-lookup"><span data-stu-id="a8397-306">Setup.exe</span></span></strong></p></td>
   <td align="left"><p><span data-ttu-id="a8397-307">Office 배포 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="a8397-307">is the Office Deployment Tool.</span></span></p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><strong><span data-ttu-id="a8397-308">/packager</span><span class="sxs-lookup"><span data-stu-id="a8397-308">/packager</span></span></strong></p></td>
   <td align="left"><p><span data-ttu-id="a8397-309">customConfig.xml 파일에 지정 된 대로 볼륨 라이선스를 사용 하 여 Office 2013 앱-V 패키지를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="a8397-309">creates the Office 2013 App-V package with Volume Licensing as specified in the customConfig.xml file.</span></span></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><strong><span data-ttu-id="a8397-310">\server\Office2013\Customconfig.xml</span><span class="sxs-lookup"><span data-stu-id="a8397-310">\server\Office2013\Customconfig.xml</span></span></strong></p></td>
   <td align="left"><p><span data-ttu-id="a8397-311">패키징 단계에 대해 준비한 구성 XML 파일 (이 경우 customConfig)을 전달 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8397-311">passes the configuration XML file (in this case customConfig) that has been prepared for the packaging stage.</span></span></p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><strong><span data-ttu-id="a8397-312">\server\share\Office 2013AppV</span><span class="sxs-lookup"><span data-stu-id="a8397-312">\server\share\Office 2013AppV</span></span></strong></p></td>
   <td align="left"><p><span data-ttu-id="a8397-313">새로 만든 Office App-v 패키지의 위치를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8397-313">specifies the location of the newly created Office App-V package.</span></span></p></td>
   </tr>
   </tbody>
   </table>



~~~
After you run the **/packager** command, the following folders appear up in the directory where you specified the package should be saved:

-   **App-V Packages** – contains an Office 2013 App-V package and two deployment configuration files.

-   **WorkingDir**

**Note**  
To troubleshoot any issues, see the log files in the %temp% directory (default).
~~~



3. <span data-ttu-id="a8397-314">Office 2013 App-v 패키지가 올바르게 작동 하는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8397-314">Verify that the Office 2013 App-V package works correctly:</span></span>

   1.  <span data-ttu-id="a8397-315">전역으로 만든 Office 2013 App-v 패키지를 테스트 컴퓨터에 게시 하 고 Office 2013 바로 가기가 표시 되는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8397-315">Publish the Office 2013 App-V package, which you created globally, to a test computer, and verify that the Office 2013 shortcuts appear.</span></span>

   2.  <span data-ttu-id="a8397-316">Excel 또는 Word 등의 몇 가지 Office 2013 응용 프로그램을 시작 하 여 패키지가 예상 대로 작동 하는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8397-316">Start a few Office 2013 applications, such as Excel or Word, to ensure that your package is working as expected.</span></span>

## <a href="" id="bkmk-pub-pkg-office"></a><span data-ttu-id="a8397-317">앱에 대 한 Office 패키지 게시-V 5.0</span><span class="sxs-lookup"><span data-stu-id="a8397-317">Publishing the Office package for App-V 5.0</span></span>


<span data-ttu-id="a8397-318">다음 정보를 사용 하 여 Office 패키지를 게시 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8397-318">Use the following information to publish an Office package.</span></span>

### <span data-ttu-id="a8397-319">Office 앱-V 패키지 게시 방법</span><span class="sxs-lookup"><span data-stu-id="a8397-319">Methods for publishing Office App-V packages</span></span>

<span data-ttu-id="a8397-320">다른 패키지에 사용 하는 것과 동일한 방법을 사용 하 여 Office 2013의 App-v 패키지를 배포 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8397-320">Deploy the App-V package for Office 2013 by using the same methods you use for any other package:</span></span>

-   <span data-ttu-id="a8397-321">System Center Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="a8397-321">System Center Configuration Manager</span></span>

-   <span data-ttu-id="a8397-322">App-v Server</span><span class="sxs-lookup"><span data-stu-id="a8397-322">App-V Server</span></span>

-   <span data-ttu-id="a8397-323">독립 실행형-PowerShell 명령</span><span class="sxs-lookup"><span data-stu-id="a8397-323">Stand-alone through PowerShell commands</span></span>

### <span data-ttu-id="a8397-324">필수 구성 요소 및 요구 사항 게시</span><span class="sxs-lookup"><span data-stu-id="a8397-324">Publishing prerequisites and requirements</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="a8397-325">필수 구성 요소 또는 요구 사항</span><span class="sxs-lookup"><span data-stu-id="a8397-325">Prerequisite or requirement</span></span></th>
<th align="left"><span data-ttu-id="a8397-326">세부 정보</span><span class="sxs-lookup"><span data-stu-id="a8397-326">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="a8397-327">App-v 클라이언트에서 PowerShell 스크립트 사용</span><span class="sxs-lookup"><span data-stu-id="a8397-327">Enable PowerShell scripting on the App-V clients</span></span></p></td>
<td align="left"><p><span data-ttu-id="a8397-328">Office 2013 패키지를 게시 하려면 스크립트를 실행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8397-328">To publish Office 2013 packages, you must run a script.</span></span></p>
<p><span data-ttu-id="a8397-329">앱-V 클라이언트에서는 패키지 스크립트를 기본적으로 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a8397-329">Package scripts are disabled by default on App-V clients.</span></span> <span data-ttu-id="a8397-330">스크립팅을 사용 하도록 설정 하려면 다음 PowerShell 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8397-330">To enable scripting, run the following PowerShell command:</span></span></p>
<pre class="syntax" space="preserve"><code>Set-AppvClientConfiguration –EnablePackageScripts 1</code></pre></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="a8397-331">전체적으로 Office 2013 패키지 게시</span><span class="sxs-lookup"><span data-stu-id="a8397-331">Publish the Office 2013 package globally</span></span></p></td>
<td align="left"><p><span data-ttu-id="a8397-332">Office App-v 패키지의 확장 지점은 컴퓨터 수준에서 설치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8397-332">Extension points in the Office App-V package require installation at the computer level.</span></span></p>
<p><span data-ttu-id="a8397-333">컴퓨터 수준에서 게시 하는 경우 필수 작업 또는 재배포 가능이 필요 하지 않으며 Office 2013 패키지를 전역적으로 응용 프로그램이 기본적으로 설치 된 Office와 동일 하 게 작동 하므로 관리자가 패키지를 사용자 지정할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a8397-333">When you publish at the computer level, no prerequisite actions or redistributables are needed, and the Office 2013 package globally enables its applications to work like natively installed Office, eliminating the need for administrators to customize packages.</span></span></p></td>
</tr>
</tbody>
</table>



### <span data-ttu-id="a8397-334">Office 패키지를 게시 하는 방법</span><span class="sxs-lookup"><span data-stu-id="a8397-334">How to publish an Office package</span></span>

<span data-ttu-id="a8397-335">다음 명령을 실행 하 여 Office 패키지를 전역적으로 게시 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8397-335">Run the following command to publish an Office package globally:</span></span>

-   `Add-AppvClientPackage <Path_to_AppV_Package> | Publish-AppvClientPackage –global`

-   <span data-ttu-id="a8397-336">App-v 서버의 웹 관리 콘솔에서 사용자 그룹을 사용 하는 대신 컴퓨터 그룹에 대 한 사용 권한을 추가 하 여 패키지를 해당 그룹의 컴퓨터에 전역으로 게시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a8397-336">From the Web Management Console on the App-V Server, you can add permissions to a group of computers instead of to a user group to enable packages to be published globally to the computers in the corresponding group.</span></span>

## <a href="" id="bkmk-custmz-manage-office-pkgs"></a><span data-ttu-id="a8397-337">Office 앱-V 패키지 사용자 지정 및 관리</span><span class="sxs-lookup"><span data-stu-id="a8397-337">Customizing and managing Office App-V packages</span></span>


<span data-ttu-id="a8397-338">Office App-v 패키지를 관리 하려면 다른 패키지에 대해 수행 하는 것과 동일한 작업을 사용 하지만 다음 섹션에서 설명 하는 몇 가지 예외가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a8397-338">To manage your Office App-V packages, use the same operations as you would for any other package, but there are a few exceptions, as outlined in the following sections.</span></span>

-   [<span data-ttu-id="a8397-339">연결 그룹을 사용 하 여 Office 플러그 인 사용</span><span class="sxs-lookup"><span data-stu-id="a8397-339">Enabling Office plug-ins by using connection groups</span></span>](#bkmk-enable-office-plugins)

-   [<span data-ttu-id="a8397-340">Office 2013 응용 프로그램을 사용 하지 않도록 설정</span><span class="sxs-lookup"><span data-stu-id="a8397-340">Disabling Office 2013 applications</span></span>](#bkmk-disable-office-apps)

-   [<span data-ttu-id="a8397-341">Office 2013 바로 가기를 사용 하지 않도록 설정</span><span class="sxs-lookup"><span data-stu-id="a8397-341">Disabling Office 2013 shortcuts</span></span>](#bkmk-disable-shortcuts)

-   [<span data-ttu-id="a8397-342">Office 2013 패키지 업그레이드 관리</span><span class="sxs-lookup"><span data-stu-id="a8397-342">Managing Office 2013 package upgrades</span></span>](#bkmk-manage-office-pkg-upgrd)

-   [<span data-ttu-id="a8397-343">Office 2013 라이선스 업그레이드 관리</span><span class="sxs-lookup"><span data-stu-id="a8397-343">Managing Office 2013 licensing upgrades</span></span>](#bkmk-manage-office-lic-upgrd)

-   [<span data-ttu-id="a8397-344">Visio 2013 및 Project 2013을 Office와 함께 배포</span><span class="sxs-lookup"><span data-stu-id="a8397-344">Deploying Visio 2013 and Project 2013 with Office</span></span>](#bkmk-deploy-visio-project)

### <a href="" id="bkmk-enable-office-plugins"></a><span data-ttu-id="a8397-345">연결 그룹을 사용 하 여 Office 플러그 인 사용</span><span class="sxs-lookup"><span data-stu-id="a8397-345">Enabling Office plug-ins by using connection groups</span></span>

<span data-ttu-id="a8397-346">이 섹션의 단계를 사용 하 여 office 플러그 인을 Office 패키지와 함께 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8397-346">Use the steps in this section to enable Office plug-ins with your Office package.</span></span> <span data-ttu-id="a8397-347">Office 플러그 인을 사용 하려면 App-v 시퀀서를 사용 하 여 플러그 인만 포함 된 별도의 패키지를 만들어야 합니다. Office 배포 도구를 사용 하 여 플러그 인 패키지를 만들 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a8397-347">To use Office plug-ins, you must use the App-V Sequencer to create a separate package that contains just the plug-ins. You cannot use the Office Deployment Tool to create the plug-ins package.</span></span> <span data-ttu-id="a8397-348">그런 다음 다음 단계에 설명 된 대로 Office 패키지 및 플러그 인 패키지를 포함 하는 연결 그룹을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="a8397-348">You then create a connection group that contains the Office package and the plug-ins package, as described in the following steps.</span></span>

**<span data-ttu-id="a8397-349">Office 앱-V 패키지에 대 한 플러그 인을 사용 하도록 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="a8397-349">To enable plug-ins for Office App-V packages</span></span>**

1.  <span data-ttu-id="a8397-350">App-v Server, System Center Configuration Manager 또는 PowerShell cmdlet을 통해 연결 그룹을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8397-350">Add a Connection Group through App-V Server, System Center Configuration Manager, or a PowerShell cmdlet.</span></span>

2.  <span data-ttu-id="a8397-351">App-v 5.0 Sequencer를 사용 하 여 플러그 인을 시퀀싱 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8397-351">Sequence your plug-ins using the App-V 5.0 Sequencer.</span></span> <span data-ttu-id="a8397-352">플러그 인을 시퀀싱 하는 데 사용 되는 컴퓨터에 Office 2013이 설치 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8397-352">Ensure that Office 2013 is installed on the computer being used to sequence the plug-in.</span></span> <span data-ttu-id="a8397-353">Office 2013 플러그 인을 순서 대로 시퀀싱 하는 컴퓨터에서 Microsoft 365 앱 (비가상)을 사용 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="a8397-353">It is recommended you use Microsoft 365 Apps for enterprise(non-virtual) on the sequencing computer when you sequence Office 2013 plug-ins.</span></span>

3.  <span data-ttu-id="a8397-354">원하는 플러그 인을 포함 하는 App-v 5.0 패키지를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="a8397-354">Create an App-V 5.0 package that includes the desired plug-ins.</span></span>

4.  <span data-ttu-id="a8397-355">App-v server, System Center Configuration Manager 또는 PowerShell cmdlet을 통해 연결 그룹을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8397-355">Add a Connection Group through App-V server, System Center Configuration Manager, or a PowerShell cmdlet.</span></span>

5.  <span data-ttu-id="a8397-356">만든 연결 그룹에 Office 2013 앱-V 패키지와 시퀀싱 한 플러그 인 패키지를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8397-356">Add the Office 2013 App-V package and the plug-ins package you sequenced to the Connection Group you created.</span></span>

    **<span data-ttu-id="a8397-357">중요</span><span class="sxs-lookup"><span data-stu-id="a8397-357">Important</span></span>**  
    <span data-ttu-id="a8397-358">연결 그룹의 패키지 순서에 따라 패키지 콘텐츠가 병합 되는 순서가 결정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a8397-358">The order of the packages in the Connection Group determines the order in which the package contents are merged.</span></span> <span data-ttu-id="a8397-359">연결 그룹 설명자 파일에서 Office 2013 App-v 패키지를 먼저 추가한 다음 플러그인 App-v 패키지를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8397-359">In your Connection group descriptor file, add the Office 2013 App-V package first, and then add the plug-in App-V package.</span></span>



6.  <span data-ttu-id="a8397-360">두 패키지가 모두 대상 컴퓨터에 게시 되 고 게시 된 Office 2013 App-v 패키지의 전역 설정에 맞게 플러그 인 패키지가 전역으로 게시 되었는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8397-360">Ensure that both packages are published to the target computer and that the plug-in package is published globally to match the global settings of the published Office 2013 App-V package.</span></span>

7.  <span data-ttu-id="a8397-361">플러그 인 패키지의 배포 구성 파일에 Office 2013 App-v 패키지와 동일한 설정이 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8397-361">Verify that the Deployment Configuration File of the plug-in package has the same settings that the Office 2013 App-V package has.</span></span>

    <span data-ttu-id="a8397-362">Office 2013 App-v 패키지가 운영 체제와 통합 되어 있기 때문에 플러그 인 패키지 설정이 일치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8397-362">Since the Office 2013 App-V package is integrated with the operating system, the plug-in package settings should match.</span></span> <span data-ttu-id="a8397-363">배포 구성 파일에서 "COM 모드"를 검색 하 고 플러그 인 패키지에 "통합 됨"으로 설정 되어 있는지 확인 하 고 "InProcessEnabled" 및 "OutOfProcessEnabled"이 모두 게시 한 Office 2013 App-v 패키지의 설정과 일치 하도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a8397-363">You can search the Deployment Configuration File for “COM Mode” and ensure that your plug-ins package has that value set as “Integrated” and that both "InProcessEnabled" and "OutOfProcessEnabled" match the settings of the Office 2013 App-V package you published.</span></span>

8.  <span data-ttu-id="a8397-364">배포 구성 파일을 열고 **사용할 수 있는 개체** 값을 **false**로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8397-364">Open the Deployment Configuration File and set the value for **Objects Enabled** to **false**.</span></span>

9.  <span data-ttu-id="a8397-365">시퀀싱 한 후에 배포 구성 파일을 변경한 경우 플러그 인 패키지가 파일과 함께 게시 되었는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8397-365">If you made any changes to the Deployment Configuration file after sequencing, ensure that the plug-in package is published with the file.</span></span>

10. <span data-ttu-id="a8397-366">만든 연결 그룹이 원하는 컴퓨터에 설정 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8397-366">Ensure that the Connection Group you created is enabled onto your desired computer.</span></span> <span data-ttu-id="a8397-367">연결 그룹을 사용 하는 경우 Office 2013 App-v 패키지를 사용 하는 경우 생성 되는 연결 그룹은 "보류" 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a8397-367">The Connection Group created will likely “pend” if the Office 2013 App-V package is in use when the Connection Group is enabled.</span></span> <span data-ttu-id="a8397-368">이 문제가 발생 하면 다시 부팅 하 여 연결 그룹을 사용 하도록 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8397-368">If that happens, you have to reboot to successfully enable the Connection Group.</span></span>

11. <span data-ttu-id="a8397-369">두 패키지를 성공적으로 게시 하 고 연결 그룹을 사용 하도록 설정한 후에는 대상 Office 2013 응용 프로그램을 시작 하 고, 게시 하 고 추가한 플러그 인이 필요한 대로 작동 하는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8397-369">After you successfully publish both packages and enable the Connection Group, start the target Office 2013 application and verify that the plug-in you published and added to the connection group works as expected.</span></span>

### <a href="" id="bkmk-disable-office-apps"></a><span data-ttu-id="a8397-370">Office 2013 응용 프로그램을 사용 하지 않도록 설정</span><span class="sxs-lookup"><span data-stu-id="a8397-370">Disabling Office 2013 applications</span></span>

<span data-ttu-id="a8397-371">Office 앱-V 패키지에서 특정 응용 프로그램을 사용 하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a8397-371">You may want to disable specific applications in your Office App-V package.</span></span> <span data-ttu-id="a8397-372">예를 들어 Access를 사용 하지 않도록 설정할 수 있지만 다른 모든 Office 응용 프로그램의 기본은 사용할 수 있는 상태로 유지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a8397-372">For instance, you can disable Access, but leave all other Office application main available.</span></span> <span data-ttu-id="a8397-373">응용 프로그램을 사용 하지 않도록 설정 하면 최종 사용자가 더 이상 해당 응용 프로그램의 바로 가기를 볼 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a8397-373">When you disable an application, the end user will no longer see the shortcut for that application.</span></span> <span data-ttu-id="a8397-374">응용 프로그램을 다시 시퀀싱 하지 않아도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a8397-374">You do not have to re-sequence the application.</span></span> <span data-ttu-id="a8397-375">Office 2013 앱-V 패키지를 게시 한 후 배포 구성 파일을 변경 하는 경우 변경 내용을 저장 하 고 Office 2013 App-v 패키지를 추가한 다음 새 배포 구성 파일을 사용 하 여 새 설정을 적용 하는 Office 2013 App-v 패키지 응용 프로그램에 다시 게시 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8397-375">When you change the Deployment Configuration File after the Office 2013 App-V package has been published, you will save the changes, add the Office 2013 App-V package, and then republish it with the new Deployment Configuration File to apply the new settings to Office 2013 App-V Package applications.</span></span>

**<span data-ttu-id="a8397-376">참고</span><span class="sxs-lookup"><span data-stu-id="a8397-376">Note</span></span>**  
<span data-ttu-id="a8397-377">Office 배포 도구를 사용 하 여 앱-V 패키지를 만들 때 특정 Office 응용 프로그램 (예: Access 및 InfoPath)을 제외 하려면 **Excludeapp** 설정을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8397-377">To exclude specific Office applications (for example, Access and InfoPath) when you create the App-V package with the Office Deployment Tool, use the **ExcludeApp** setting.</span></span> <span data-ttu-id="a8397-378">자세한 내용은 간편 [실행 configuration.xml 파일에 대 한 참조](https://technet.microsoft.com/library/jj219426.aspx)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a8397-378">For more information, see [Reference for Click-to-Run configuration.xml file](https://technet.microsoft.com/library/jj219426.aspx).</span></span>



**<span data-ttu-id="a8397-379">Office 2013 응용 프로그램을 사용 하지 않도록 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="a8397-379">To disable an Office 2013 application</span></span>**

1.  <span data-ttu-id="a8397-380">**메모장과** 같은 텍스트 편집기를 사용 하 여 배포 구성 파일을 열고 "응용 프로그램"을 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8397-380">Open a Deployment Configuration File with a text editor such as **Notepad** and search for “Applications."</span></span>

2.  <span data-ttu-id="a8397-381">사용 하지 않으려는 Office 응용 프로그램 (예: Access 2013)을 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8397-381">Search for the Office application you want to disable, for example, Access 2013.</span></span>

3.  <span data-ttu-id="a8397-382">"사용" 값을 "true"에서 "false"로 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8397-382">Change the value of "Enabled" from "true" to "false."</span></span>

4.  <span data-ttu-id="a8397-383">배포 구성 파일을 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8397-383">Save the Deployment Configuration File.</span></span>

5.  <span data-ttu-id="a8397-384">새 배포 구성 파일을 사용 하 여 Office 2013 App-v 패키지를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8397-384">Add the Office 2013 App-V Package with the new Deployment Configuration File.</span></span>

    ```xml
    <Application Id="[{AppVPackageRoot)]\officefl5\INFOPATH.EXE" Enabled="true">
      <VisualElements>
        <Name>InfoPath Filler 2013</Name>
        <Icon />
        <Description />
      </VisualElements>
    </Application>
    <Application Id="[{AppVPackageRoot}]\office15\lync.exe" Enabled="true">
      <VisualElements>
        <Name>Lync 2013</Name>
        <Icon />
        <Description />
      </VisualElements>
    </Application>
    <Application Id="[(AppVPackageRoot}]\office15\MSACCESS.EXE" Enabled="true">
      <VisualElements>
        <Name>Access 2013</Name>
        <Icon />
        <Description />
      </VisualElements>
    </Application>
    ```

6.  <span data-ttu-id="a8397-385">Office 2013 App-v 패키지를 다시 추가한 다음 새 배포 구성 파일을 사용 하 여 Office 2013 앱-V 패키지 응용 프로그램에 새 설정을 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8397-385">Re-add the Office 2013 App-V package, and then republish it with the new Deployment Configuration File to apply the new settings to Office 2013 App-V Package applications.</span></span>

### <a href="" id="bkmk-disable-shortcuts"></a><span data-ttu-id="a8397-386">Office 2013 바로 가기를 사용 하지 않도록 설정</span><span class="sxs-lookup"><span data-stu-id="a8397-386">Disabling Office 2013 shortcuts</span></span>

<span data-ttu-id="a8397-387">패키지를 게시 취소 하거나 제거 하는 대신 특정 Office 응용 프로그램의 바로 가기를 사용 하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a8397-387">You may want to disable shortcuts for certain Office applications instead of unpublishing or removing the package.</span></span> <span data-ttu-id="a8397-388">다음 예제에서는 Microsoft Access의 바로 가기를 사용 하지 않도록 설정 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a8397-388">The following example shows how to disable shortcuts for Microsoft Access.</span></span>

**<span data-ttu-id="a8397-389">Office 2013 응용 프로그램의 바로 가기를 사용 하지 않도록 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="a8397-389">To disable shortcuts for Office 2013 applications</span></span>**

1.  <span data-ttu-id="a8397-390">메모장에서 배포 구성 파일을 열고 "바로 가기"를 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8397-390">Open a Deployment Configuration File in Notepad and search for “Shortcuts”.</span></span>

2.  <span data-ttu-id="a8397-391">특정 바로 가기를 사용 하지 않도록 설정 하려면 원하지 않는 특정 바로 가기를 삭제 하거나 주석으로 처리 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8397-391">To disable certain shortcuts, delete or comment out the specific shortcuts you don’t want.</span></span> <span data-ttu-id="a8397-392">하위 시스템을 표시 하 고 사용 하도록 유지 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8397-392">You must keep the subsystem present and enabled.</span></span> <span data-ttu-id="a8397-393">예를 들어 아래 예제에서는 Microsoft Access 바로 가기를 삭제 하 고, 하위 시스템 바로 가기 &lt; &gt; &lt; /바로 가기는 &gt; 그대로 유지 하 여 microsoft access 바로 가기를 사용 하지 않도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8397-393">For example, in the example below, delete the Microsoft Access shortcuts, while keeping the subsystems &lt;shortcut&gt; &lt;/shortcut&gt; intact to disable the Microsoft Access shortcut.</span></span>

    ``` syntax
    Shortcuts

    -->
     <Shortcuts Enabled="true">
      <Extensions>
        <Extension Category="AppV.Shortcut">
          <Shortcut>
           <File>[{Common Programs}]\Microsoft Office 2013\Access 2013.lnk</File>
           <Target>[{AppvPackageRoot}])office15\MSACCESS.EXE</Target>
           <Icon>[{Windows}]\Installer\{90150000-000F-0000-0000-000000FF1CE)\accicons.exe.Ø.ico</Icon>
           <Arguments />
           <WorkingDirectory />
           <AppuserModelId>Microsoft.Office.MSACCESS.EXE.15</AppUserModelId>
           <AppUserModelExcludeFromShowInNewInstall>true</AppUserModelExcludeFromShowInNewInstall>
           <Description>Build a professional app quickly to manage data.</Description>
           <ShowCommand>l</ShowCommand>
           <ApplicationId>[{AppVPackageRoot}]\office15\MSACCESS.EXE</ApplicationId>
        </Shortcut>
    ```

3.  <span data-ttu-id="a8397-394">배포 구성 파일을 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8397-394">Save the Deployment Configuration File.</span></span>

4.  <span data-ttu-id="a8397-395">새 배포 구성 파일을 사용 하 여 Office 2013 App-v 패키지를 다시 게시 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8397-395">Republish Office 2013 App-V Package with new Deployment Configuration File.</span></span>

<span data-ttu-id="a8397-396">앱-V 패키지에 대 한 배포 구성 (예: 파일 형식 연결, 가상 파일 시스템 등)을 수정 하 여 다양 한 추가 설정을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a8397-396">Many additional settings can be changed through modifying the Deployment Configuration for App-V packages, for example, file type associations, Virtual File System, and more.</span></span> <span data-ttu-id="a8397-397">배포 구성 파일을 사용 하 여 App-v 패키지 설정을 변경 하는 방법에 대 한 자세한 내용은이 문서의 뒷부분에 나오는 추가 리소스 섹션을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a8397-397">For additional information on how to use Deployment Configuration Files to change App-V package settings, refer to the additional resources section at the end of this document.</span></span>

### <a href="" id="bkmk-manage-office-pkg-upgrd"></a><span data-ttu-id="a8397-398">Office 2013 패키지 업그레이드 관리</span><span class="sxs-lookup"><span data-stu-id="a8397-398">Managing Office 2013 package upgrades</span></span>

<span data-ttu-id="a8397-399">Office 2013 패키지를 업그레이드 하려면 Office 배포 도구를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8397-399">To upgrade an Office 2013 package, use the Office Deployment Tool.</span></span> <span data-ttu-id="a8397-400">이전에 배포 된 Office 2013 패키지를 업그레이드 하려면 다음 단계를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8397-400">To upgrade a previously deployed Office 2013 package, perform the following steps.</span></span>

**<span data-ttu-id="a8397-401">이전에 배포 된 Office 2013 패키지를 업그레이드 하는 방법</span><span class="sxs-lookup"><span data-stu-id="a8397-401">How to upgrade a previously deployed Office 2013 package</span></span>**

1.  <span data-ttu-id="a8397-402">최신 Office 2013 응용 프로그램 소프트웨어를 사용 하는 Office 배포 도구를 통해 새 Office 2013 패키지를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="a8397-402">Create a new Office 2013 package through the Office Deployment Tool that uses the most recent Office 2013 application software.</span></span> <span data-ttu-id="a8397-403">가장 최근의 Office 2013 비트는 Office 2013 App-v 패키지를 만드는 다운로드 단계를 통해 언제 든 지 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a8397-403">The most recent Office 2013 bits can always be obtained through the download stage of creating an Office 2013 App-V Package.</span></span> <span data-ttu-id="a8397-404">새로 생성 된 Office 2013 패키지에는 최신 업데이트와 새 버전 ID가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a8397-404">The newly created Office 2013 package will have the most recent updates and a new Version ID.</span></span> <span data-ttu-id="a8397-405">Office 배포 도구를 사용 하 여 만든 모든 패키지에는 동일한 계보가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a8397-405">All packages created using the Office Deployment Tool have the same lineage.</span></span>

    **<span data-ttu-id="a8397-406">참고</span><span class="sxs-lookup"><span data-stu-id="a8397-406">Note</span></span>**  
    <span data-ttu-id="a8397-407">Office 앱-V 패키지에는 두 가지 버전 Id가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a8397-407">Office App-V packages have two Version IDs:</span></span>

    -   <span data-ttu-id="a8397-408">Office 배포 도구를 사용 하 여 만든 모든 패키지에서 고유한 Office 2013 App-v 패키지 버전 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="a8397-408">An Office 2013 App-V Package Version ID that is unique across all packages created using the Office Deployment Tool.</span></span>

    -   <span data-ttu-id="a8397-409">새 버전의 Office가 있는 경우에만 변경 되는 두 번째 App-v 패키지 버전 ID, x.x. x 예: AppX 매니페스트</span><span class="sxs-lookup"><span data-stu-id="a8397-409">A second App-V Package Version ID, x.x.x.x for example, in the AppX manifest that will only change if there is a new version of Office itself.</span></span> <span data-ttu-id="a8397-410">예를 들어 업그레이드 된 새 Office 2013 릴리스를 사용할 수 있고 이러한 업그레이드를 통합 하기 위해 Office 배포 도구를 통해 패키지를 만들면 X.x.x.x 버전 ID가 변경 되어 Office 버전 자체가 변경 되었음을 반영 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8397-410">For example, if a new Office 2013 release with upgrades is available, and a package is created through the Office Deployment Tool to incorporate these upgrades, the X.X.X.X version ID will change to reflect that the Office version itself has changed.</span></span> <span data-ttu-id="a8397-411">App-v 서버는이 패키지를 구분 하는 데 x.x 버전 ID를 사용 하 고 이전에 게시 된 패키지에 대 한 새 업그레이드가 포함 되어 있음을 인식 하 고, 결과적으로 기존 Office 2013 패키지에 대 한 업그레이드로 게시 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8397-411">The App-V server will use the X.X.X.X version ID to differentiate this package and recognize that it contains new upgrades to the previously published package, and as a result, publish it as an upgrade to the existing Office 2013 package.</span></span>



2.  <span data-ttu-id="a8397-412">새로 만든 Office 2013 App-v 패키지를 새 업데이트를 적용 하려는 컴퓨터에 전역적으로 게시 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8397-412">Globally publish the newly created Office 2013 App-V Packages onto computers where you would like to apply the new updates.</span></span> <span data-ttu-id="a8397-413">새 패키지에는 이전 Office 2013 App-v 패키지의 계보가 있으므로 업데이트를 사용 하 여 새 패키지를 게시 하면 이전 패키지에 새 변경 내용만 적용 되므로 속도가 빠릅니다.</span><span class="sxs-lookup"><span data-stu-id="a8397-413">Since the new package has the same lineage of the older Office 2013 App-V Package, publishing the new package with the updates will only apply the new changes to the old package, and thus will be fast.</span></span>

3.  <span data-ttu-id="a8397-414">업그레이드는 전역적으로 게시 된 모든 앱-V 패키지와 동일한 방식으로 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a8397-414">Upgrades will be applied in the same manner of any globally published App-V Packages.</span></span> <span data-ttu-id="a8397-415">응용 프로그램을 사용 중일 수 있으므로 컴퓨터를 다시 부팅할 때까지 업그레이드가 지연 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a8397-415">Because applications will probably be in use, upgrades might be delayed until the computer is rebooted.</span></span>

### <a href="" id="bkmk-manage-office-lic-upgrd"></a><span data-ttu-id="a8397-416">Office 2013 라이선스 업그레이드 관리</span><span class="sxs-lookup"><span data-stu-id="a8397-416">Managing Office 2013 licensing upgrades</span></span>

<span data-ttu-id="a8397-417">새 Office 2013 App-v 패키지에 현재 배포 된 Office 2013 App-v 패키지와 다른 라이선스가 있는 경우</span><span class="sxs-lookup"><span data-stu-id="a8397-417">If a new Office 2013 App-V Package has a different license than the Office 2013 App-V Package currently deployed.</span></span> <span data-ttu-id="a8397-418">예를 들어 배포 된 Office 2013 패키지는 구독 기반 Office 2013이 고 새 Office 2013 패키지는 볼륨 라이선스 기반 이므로 원활한 라이선스 업그레이드를 위해 다음 지침을 따라야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8397-418">For instance, the Office 2013 package deployed is a subscription based Office 2013 and the new Office 2013 package is Volume Licensing based, the following instructions must be followed to ensure smooth licensing upgrade:</span></span>

**<span data-ttu-id="a8397-419">Office 2013 라이선스를 업그레이드 하는 방법</span><span class="sxs-lookup"><span data-stu-id="a8397-419">How to upgrade an Office 2013 License</span></span>**

1.  <span data-ttu-id="a8397-420">이미 배포 된 Office 2013 구독 라이선스 앱-V 패키지의 게시를 취소 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8397-420">Unpublish the already deployed Office 2013 Subscription Licensing App-V package.</span></span>

2.  <span data-ttu-id="a8397-421">게시 되지 않은 Office 2013 구독 라이선스 앱-V 패키지를 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8397-421">Remove the unpublished Office 2013 Subscription Licensing App-V package.</span></span>

3.  <span data-ttu-id="a8397-422">컴퓨터를 다시 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8397-422">Restart the computer.</span></span>

4.  <span data-ttu-id="a8397-423">새 Office 2013 App-v 패키지 볼륨 라이선스를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8397-423">Add the new Office 2013 App-V Package Volume Licensing.</span></span>

5.  <span data-ttu-id="a8397-424">추가 된 Office 2013 App-v 패키지를 볼륨 라이선스와 함께 게시 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8397-424">Publish the added Office 2013 App-V Package with Volume Licensing.</span></span>

<span data-ttu-id="a8397-425">선택한 라이선스를 포함 하는 Office 2013 App-v 패키지가 성공적으로 배포 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a8397-425">An Office 2013 App-V Package with your chosen licensing will be successfully deployed.</span></span>

### <a href="" id="bkmk-deploy-visio-project"></a><span data-ttu-id="a8397-426">Visio 2013 및 Project 2013을 Office와 함께 배포</span><span class="sxs-lookup"><span data-stu-id="a8397-426">Deploying Visio 2013 and Project 2013 with Office</span></span>

<span data-ttu-id="a8397-427">다음 표에서는 Visio 2013 및 Project 2013을 Office와 함께 배포 하기 위한 요구 사항 및 옵션에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8397-427">The following table describes the requirements and options for deploying Visio 2013 and Project 2013 with Office.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="a8397-428">작업</span><span class="sxs-lookup"><span data-stu-id="a8397-428">Task</span></span></th>
<th align="left"><span data-ttu-id="a8397-429">세부 정보</span><span class="sxs-lookup"><span data-stu-id="a8397-429">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="a8397-430">Visio 2013 및 Project 2013을 Office와 함께 패키지 하 고 게시 하려면 어떻게 하나요?</span><span class="sxs-lookup"><span data-stu-id="a8397-430">How do I package and publish Visio 2013 and Project 2013 with Office?</span></span></p></td>
<td align="left"><p><span data-ttu-id="a8397-431">Visio 2013 및 Project 2013을 Office와 동일한 패키지에 포함 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8397-431">You must include Visio 2013 and Project 2013 in the same package with Office.</span></span></p>
<p><span data-ttu-id="a8397-432">Office를 배포 하지 않는 경우 <a href="../appv-v5/deploying-microsoft-office-2010-by-using-app-v.md" data-raw-source="[Deploying Microsoft Office 2010 by Using App-V](../appv-v5/deploying-microsoft-office-2010-by-using-app-v.md)"> app-v를 사용 하 여 Microsoft Office 2010 배포를 팔 로우 하는 경우 Visio 및/또는 프로젝트를 포함 하는 패키지를 만들 수 있습니다 </a> .</span><span class="sxs-lookup"><span data-stu-id="a8397-432">If you aren’t deploying Office, you can create a package that contains Visio and/or Project, as long as you follow <a href="../appv-v5/deploying-microsoft-office-2010-by-using-app-v.md" data-raw-source="[Deploying Microsoft Office 2010 by Using App-V](../appv-v5/deploying-microsoft-office-2010-by-using-app-v.md)">Deploying Microsoft Office 2010 by Using App-V</a>.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="a8397-433">Visio 2013 및 Project 2013을 특정 사용자에 게 어떻게 배포할 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="a8397-433">How can I deploy Visio 2013 and Project 2013 to specific users?</span></span></p></td>
<td align="left"><p><span data-ttu-id="a8397-434">다음 방법 중 하나를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="a8397-434">Use one of the following methods:</span></span></p>
<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="a8397-435">원하는 경우</span><span class="sxs-lookup"><span data-stu-id="a8397-435">If you want to...</span></span></th>
<th align="left"><span data-ttu-id="a8397-436">... 그런 다음이 방법을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8397-436">...then use this method</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="a8397-437">두 개의 다른 패키지를 만들어 각각 다른 사용자 그룹에 배포</span><span class="sxs-lookup"><span data-stu-id="a8397-437">Create two different packages and deploy each one to a different group of users</span></span></p></td>
<td align="left"><p><span data-ttu-id="a8397-438">다음 패키지를 만들고 배포 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8397-438">Create and deploy the following packages:</span></span></p>
<ul>
<li><p><span data-ttu-id="a8397-439">사용자가 Office만 필요로 하는 컴퓨터에는 Office 배포만 포함 된 패키지입니다.</span><span class="sxs-lookup"><span data-stu-id="a8397-439">A package that contains only Office - deploy to computers whose users need only Office.</span></span></p></li>
<li><p><span data-ttu-id="a8397-440">사용자가 세 가지 응용 프로그램을 모두 필요로 하는 컴퓨터에 Office, Visio, 프로젝트 배포가 포함 된 패키지입니다.</span><span class="sxs-lookup"><span data-stu-id="a8397-440">A package that contains Office, Visio, and Project - deploy to computers whose users need all three applications.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="a8397-441">전체 조직에 대해 하나의 패키지만 사용 하려는 경우 또는 컴퓨터를 공유 하는 사용자가 있는 경우:</span><span class="sxs-lookup"><span data-stu-id="a8397-441">If you want only one package for the whole organization, or if you have users who share computers:</span></span></p></td>
<td align="left"><p><span data-ttu-id="a8397-442">다음 단계를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="a8397-442">Follows these steps:</span></span></p>
<ol>
<li><p><span data-ttu-id="a8397-443">Office, Visio, 프로젝트를 포함 하는 패키지를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="a8397-443">Create a package that contains Office, Visio, and Project.</span></span></p></li>
<li><p><span data-ttu-id="a8397-444">패키지를 모든 사용자에 게 배포 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8397-444">Deploy the package to all users.</span></span></p></li>
<li><p><span data-ttu-id="a8397-445"><a href="https://technet.microsoft.com/library/dd723678.aspx" data-raw-source="[Microsoft AppLocker](https://technet.microsoft.com/library/dd723678.aspx)">Microsoft AppLocker </a> 를 사용 하 여 특정 사용자가 Visio 및 Project를 사용 하지 못하도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a8397-445">Use <a href="https://technet.microsoft.com/library/dd723678.aspx" data-raw-source="[Microsoft AppLocker](https://technet.microsoft.com/library/dd723678.aspx)">Microsoft AppLocker</a> to prevent specific users from using Visio and Project.</span></span></p></li>
</ol></td>
</tr>
</tbody>
</table>
<p> </p></td>
</tr>
</tbody>
</table>



## <span data-ttu-id="a8397-446">추가 리소스</span><span class="sxs-lookup"><span data-stu-id="a8397-446">Additional resources</span></span>


**<span data-ttu-id="a8397-447">Office 2013 앱-V 5.0 패키지 5.0 추가 리소스</span><span class="sxs-lookup"><span data-stu-id="a8397-447">Office 2013 App-V 5.0 Packages 5.0 Additional Resources</span></span>**

[<span data-ttu-id="a8397-448">간편 실행을 위한 Office 배포 도구</span><span class="sxs-lookup"><span data-stu-id="a8397-448">Office Deployment Tool for Click-to-Run</span></span>](https://go.microsoft.com/fwlink/p/?LinkID=330672)

[<span data-ttu-id="a8397-449">Microsoft Office를 시퀀싱 된 앱으로 배포 하는 데 지원 되는 시나리오-V 패키지</span><span class="sxs-lookup"><span data-stu-id="a8397-449">Supported scenarios for deploying Microsoft Office as a sequenced App-V Package</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=330680)

**<span data-ttu-id="a8397-450">Office 2010 App-V 5.0 패키지</span><span class="sxs-lookup"><span data-stu-id="a8397-450">Office 2010 App-V 5.0 Packages</span></span>**

[<span data-ttu-id="a8397-451">Microsoft Application Virtualization 5.0 용 microsoft Office 2010 시퀀싱 키트</span><span class="sxs-lookup"><span data-stu-id="a8397-451">Microsoft Office 2010 Sequencing Kit for Microsoft Application Virtualization 5.0</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=330681)

[<span data-ttu-id="a8397-452">앱-V 5.0 Office 2010 패키지를 만들거나 사용할 때의 알려진 문제</span><span class="sxs-lookup"><span data-stu-id="a8397-452">Known issues when you create or use an App-V 5.0 Office 2010 package</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=330682)

[<span data-ttu-id="a8397-453">Microsoft Application Virtualization 5.0에서 Microsoft Office 2010을 시퀀싱 하는 방법</span><span class="sxs-lookup"><span data-stu-id="a8397-453">How to sequence Microsoft Office 2010 in Microsoft Application Virtualization 5.0</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=330676)

**<span data-ttu-id="a8397-454">연결 그룹</span><span class="sxs-lookup"><span data-stu-id="a8397-454">Connection Groups</span></span>**

[<span data-ttu-id="a8397-455">Microsoft App-V v5에 연결 그룹 배포</span><span class="sxs-lookup"><span data-stu-id="a8397-455">Deploying Connection Groups in Microsoft App-V v5</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=330683)

[<span data-ttu-id="a8397-456">연결 그룹 관리</span><span class="sxs-lookup"><span data-stu-id="a8397-456">Managing Connection Groups</span></span>](managing-connection-groups.md)

**<span data-ttu-id="a8397-457">동적 구성</span><span class="sxs-lookup"><span data-stu-id="a8397-457">Dynamic Configuration</span></span>**

[<span data-ttu-id="a8397-458">App-V 5.0 동적 구성 정보</span><span class="sxs-lookup"><span data-stu-id="a8397-458">About App-V 5.0 Dynamic Configuration</span></span>](about-app-v-50-dynamic-configuration.md)













