---
title: 최종 사용자 컴퓨터 이외의 컴퓨터에서 독립 실행형 모드로 크래시 분석기를 실행하는 방법
description: 최종 사용자 컴퓨터 이외의 컴퓨터에서 독립 실행형 모드로 크래시 분석기를 실행하는 방법
author: dansimp
ms.assetid: 881d573f-2f18-4c5f-838e-2f5320179f94
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: support
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 6f398c56b7c631145388541b71229d69c16bf6f3
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/26/2020
ms.locfileid: "10822788"
---
# 최종 사용자 컴퓨터 이외의 컴퓨터에서 독립 실행형 모드로 크래시 분석기를 실행하는 방법


Windows 용 Microsoft 디버깅 도구 또는 최종 사용자 컴퓨터의 기호 파일에 액세스할 수 없는 경우 문제 컴퓨터에서 덤프 파일을 복사 하 고, 헬프데스크 관리자의 컴퓨터와 같이 독립 실행형 버전의 크래시 분석기가 설치 된 컴퓨터에서이를 분석할 수 있습니다.

**독립 실행형 모드에서 충돌 분석기를 실행 하려면**

1.  DaRT7가 설치 된 컴퓨터에서 **Start**  /  **모든 프로그램**시작  /  **Microsoft DaRT 7**을 클릭 합니다.

2.  다음에 대 한 필수 정보를 제공 합니다.

    -   Windows 용 Microsoft 디버깅 도구

    -   기호 파일

        기호 파일에 대 한 자세한 내용은 [충돌 분석기가 기호 파일에 액세스할 수 있도록 하는 방법](how-to-ensure-that-crash-analyzer-can-access-symbol-files-dart-7.md)을 참조 하세요.

    -   크래시 덤프 파일

        **참고**  DaRT7에서 검색 도구를 사용 하 여 복사 된 크래시 덤프 파일을 찾습니다.

         

3.  **충돌 분석기** 는 크래시 덤프 파일을 검사 하 고 충돌이 발생할 가능성이 있는 경우를 보고 합니다. 충돌에 대 한 자세한 내용, 특정 충돌 메시지, 설명, 충돌 시 로드 되는 드라이버, 분석의 전체 출력 등을 볼 수 있습니다.

4.  적절 한 전략을 결정 하 여 문제를 해결 합니다. 이 경우 DaRT에서 **컴퓨터 관리** 도구의 **서비스 및 드라이버** 노드를 사용 하 여 충돌을 일으킨 장치 드라이버를 사용 하지 않도록 설정 하거나 업데이트 해야 할 수 있습니다.

## 관련 항목


[크래시 분석기를 사용하여 시스템 오류 진단](diagnosing-system-failures-with-crash-analyzer--dart-7.md)

 

 





