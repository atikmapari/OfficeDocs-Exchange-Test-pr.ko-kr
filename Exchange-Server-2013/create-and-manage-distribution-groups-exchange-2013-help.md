﻿---
title: '메일 그룹 만들기 및 관리: Exchange 2013 Help'
TOCTitle: 메일 그룹 만들기 및 관리
ms:assetid: c4c43493-55e1-46d2-bd4b-d6f6cecd747f
ms:mtpsurl: https://technet.microsoft.com/ko-kr/library/Bb124513(v=EXCHG.150)
ms:contentKeyID: 50484110
ms.date: 05/22/2018
mtps_version: v=EXCHG.150
f1_keywords:
- Microsoft.Exchange.Management.SnapIn.Esm.Recipients.CreateDistributionGroupWizardForm.CreateDistributionGroupIntroductionWizardPage
ms.translationtype: MT
---

# 메일 그룹 만들기 및 관리

 

_**적용 대상:** Exchange Online, Exchange Server 2016, Office 365_

_**마지막으로 수정된 항목:** 2016-12-09_

Exchange 조직에서 새 메일 그룹을 만들려면 또는 메일 사용이 가능한 Active Directory 에서 기존 그룹에 Exchange 관리 센터 (EAC) 또는 Exchange 관리 셸을 사용 하 여 합니다.

메시지를 배포하는 데 사용할 수 있는 그룹에는 두 가지 유형이 있습니다.

  - *메일 사용이 가능한 유니버설 메일 그룹*(*메일 그룹*이라고도 함)은 메시지 배포에만 사용할 수 있습니다.

  - *메일 사용이 가능한 유니버설 보안 그룹*(*보안 그룹*이라고도 함)은 메시지 배포 및 Active Directory의 리소스에 대한 액세스 권한 부여에 사용할 수 있습니다. 자세한 내용은 [메일 사용이 가능한 보안 그룹 관리](manage-mail-enabled-security-groups-exchange-2013-help.md)를 참조하십시오.

Active Directory와 Exchange의 용어 차이에 주의해야 합니다. Active Directory에서는 메일 사용이 가능한지 여부에 관계없이 보안 컨텍스트가 없는 모든 그룹을 메일 그룹이라고 합니다. 이와 달리 Exchange에서는 보안 컨텍스트가 있는지 여부에 관계없이 메일 사용이 가능한 모든 그룹을 메일 그룹이라고 합니다.

## 시작하기 전에 알아야 할 내용

  - 예상 완료 시간: 2~5분

  - 이러한 절차를 수행하려면 먼저 사용 권한을 할당받아야 합니다. 필요한 사용 권한을 확인하려면 다음을 참조하세요. [받는 사람에 게 사용 권한](recipients-permissions-exchange-2013-help.md)의 "메일 그룹" 항목

  - 조직에서 그룹 명명 정책을 구성한 경우 이는 사용자가 만드는 그룹에만 적용됩니다. 관리자가 EAC를 사용하여 메일 그룹을 만들 때는 그룹 명명 정책이 무시되며 그룹 이름에 적용되지 않습니다. 그러나 셸을 사용하여 메일 그룹을 만들거나 이름을 바꾸면 *IgnoreNamingPolicy* 매개 변수를 사용하여 그룹 명명 정책을 재정의하지 않는 한 해당 정책이 적용됩니다. 자세한 내용은 다음을 참조하십시오.
    
      - [메일 그룹 명명 정책을 만들려면](create-a-distribution-group-naming-policy-exchange-2013-help.md)
    
      - [메일 그룹 명명 정책을 무시합니다](override-the-distribution-group-naming-policy-exchange-2013-help.md)

## 무슨 작업을 하고 싶으십니까?

## 메일 그룹 만들기

## EAC를 사용하여 메일 그룹 만들기

1.  EAC에서 **받는 사람** \> **그룹**으로 이동합니다.

2.  **새로 만들기** ![아이콘 추가](images/JJ218640.c1e75329-d6d7-4073-a27d-498590bbb558(EXCHG.150).gif "아이콘 추가") \> **메일 그룹**을 클릭합니다.

3.  > [!TIP]
    > <IMG title="Office 365 그룹 새로 사용해보기" alt="Office 365 그룹 새로 사용해보기" src="images/Bb124513.3ea82c95-9dda-450f-823b-cd0772249d81(EXCHG.150).png"><BR>사업 계획 또는 Exchange Online 계획에 대 한 Office 365를 설치한 경우에 이제 메일 그룹 대신 Office 365 그룹을 만들 수 있습니다. Office 365 그룹을 사용 하면 메일 그룹 및 더 많은 기능이 있습니다. Office 365 그룹과 그룹에 전자 메일을 보낼, 일반적인 일정 공유를 저장 하 고 작업 그룹 파일 및 폴더에 대 한 라이브러리가 있는 수 있습니다. <STRONG>새로 만들기</STRONG><IMG title="아이콘 추가" alt="아이콘 추가" src="images/JJ218640.c1e75329-d6d7-4073-a27d-498590bbb558(EXCHG.150).gif"> 클릭 &gt; <STRONG>Office 365 그룹</STRONG> 을 시작 하 고 <A href="https://go.microsoft.com/fwlink/p/?linkid=800653">Office 365 그룹-관리 하는 데 도움이</A>체크아웃 합니다.<BR>Office 365 그룹에 마이그레이션할 기존 메일 그룹을 사용 하는 경우 <A href="https://go.microsoft.com/fwlink/p/?linkid=824756">Office 365 그룹-관리자 도움말에 마이그레이션 메일 그룹</A>체크아웃 합니다.<BR>여전히을 하려는 경우 메일 그룹 만들기를 클릭 하거나 <STRONG>새 메일 그룹</STRONG> 마법사를 누릅니다.



4.  **새 메일 그룹** 페이지에서 다음 입력란에 해당 정보를 입력합니다.
    
      - \* **표시 이름**   이 입력란에 표시 이름을 입력합니다. 이 이름은 조직의 주소록, 받는 사람: 줄(이 그룹으로 전자 메일을 보낸 경우), EAC의 그룹 목록에 표시됩니다. 표시 이름은 필수이며 다른 사람들이 알아 볼 수 있도록 친숙한 형태로 지정해야 합니다. 또한 포리스트에서 고유해야 합니다.
    
      - \* **별칭**   이 입력란에 그룹의 별칭 이름을 입력합니다. 별칭은 64자를 초과할 수 없으며 포리스트에서 고유해야 합니다. 전자 메일 메시지의 받는 사람: 줄에 별칭을 입력하면 그룹의 표시 이름으로 확인됩니다.
    
      - **조직 구성 단위**    (만 볼 Exchange 2013 온-프레미스에서이 옵션) 기본값 (즉, 받는 사람 범위) 아닌 다른 조직 구성 단위 (OU)을 선택할 수 있습니다. 받는 사람 범위는 포리스트로 설정 되 면 기본값은 EAC 실행 되 고 있는 컴퓨터를 포함 하는 Active Directory 도메인의 Users 컨테이너에 설정 됩니다. 받는 사람 범위는 특정 도메인으로 설정 된 경우 해당 도메인의 Users 컨테이너는 기본적으로 선택 됩니다. 받는 사람 범위는 특정 OU로 설정 되 면 해당 OU는 기본적으로 선택 됩니다.
        
        다른 OU를 선택하려면 **찾아보기**를 클릭합니다. 이 대화 상자에는 지정된 범위 내에 있는 포리스트의 모든 OU가 표시됩니다. 원하는 OU를 선택한 다음 **확인**을 클릭합니다.
    
      - \* **소유자**   기본적으로 그룹을 만든 사람이 소유자가 됩니다. 모든 그룹에는 한 명 이상의 소유자가 있어야 합니다. **추가**![아이콘 추가](images/JJ218640.c1e75329-d6d7-4073-a27d-498590bbb558(EXCHG.150).gif "아이콘 추가")를 클릭하여 소유자를 추가할 수 있습니다.
    
      - **구성원**   이 섹션을 사용하면 구성원을 추가하고 그룹에 가입하거나 그룹에서 탈퇴하려는 사용자에 대해 승인이 필요한지 여부를 지정할 수 있습니다.
        
        그룹 소유자는 그룹의 구성원이 아니어도 됩니다. **그룹 소유자를 구성원으로 추가**를 사용하면 소유자를 구성원으로 추가하거나 구성원에서 제거할 수 있습니다.
        
        그룹에 구성원을 추가하려면 **추가**![아이콘 추가](images/JJ218640.c1e75329-d6d7-4073-a27d-498590bbb558(EXCHG.150).gif "아이콘 추가")를 클릭합니다. 구성원 추가를 마치면 **확인**을 클릭하여 **새 메일 그룹** 페이지로 돌아갑니다.
        
        **그룹에 가입하는 데 소유자 승인이 필요한지 여부를 선택하십시오.** 에서 사용자가 그룹에 가입하는 데 승인이 필요한지 여부를 지정합니다. 다음 설정 중 하나를 선택합니다.
        
          - **개방 모드: 모든 사용자가 그룹 소유자의 승인 없이 이 그룹에 참가할 수 있음**   기본 설정입니다.
        
          - **폐쇄 모드: 그룹 소유자만이 구성원을 추가할 수 있음. 모든 참가 요청이 자동으로 거부됩니다.**
        
          - **소유자 승인: 모든 요청은 그룹 소유자가 직접 승인 또는 거절합니다.**   이 옵션을 선택하면 그룹 소유자가 그룹 가입 승인을 요청하는 전자 메일 메시지를 받게 됩니다.
        
        **그룹에서 탈퇴할 때 승인 여부를 선택하십시오.** 에서 사용자가 그룹을 탈퇴할 때 승인이 필요한지 여부를 지정합니다. 다음 설정 중 하나를 선택합니다.
        
          - **개방 모드: 모든 사용자가 그룹 소유자의 승인 없이 이 그룹에서 나갈 수 있음**   기본 설정입니다.
        
          - **폐쇄 모드: 그룹 소유자만이 구성원을 제거할 수 있음. 모든 탈퇴 요청은 자동으로 거부됩니다.**

5.  모든 설정이 끝나면 **저장**을 클릭하여 메일 그룹을 만듭니다.


> [!NOTE]
> 기본적으로 새로운 메일 그룹을 사용하려면 모든 보낸 사람에 대한 인증이 필요합니다. 따라서 외부 보낸 사람은 메일 그룹에 메시지를 보낼 수 없습니다. 모든 보낸 사람의 메시지를 수락하도록 메일 그룹을 구성하려면 해당 메일 그룹에 대한 메시지 배달 제한 설정을 수정해야 합니다.



## 셸을 사용하여 메일 그룹 만들기

이 예에서는 별칭이 **itadmin**이고 이름이 **IT Administrators**인 메일 그룹을 만듭니다. 메일 그룹은 기본 OU에 만들어지며, 누구나 그룹 소유자의 승인 없이 이 그룹에 가입할 수 있습니다.

    New-DistributionGroup -Name "IT Administrators" -Alias itadmin -MemberJoinRestriction open

셸을 사용하여 메일 그룹을 만드는 방법에 대한 자세한 내용은 [New-DistributionGroup](https://technet.microsoft.com/ko-kr/library/aa998856\(v=exchg.150\))을 참조하십시오.

## 작동 여부는 어떻게 확인합니까?

메일 그룹이 성공적으로 만들어졌는지 확인하려면 다음 중 하나를 수행하십시오.

  - EAC에서 **받는 사람** \> **그룹**으로 이동합니다. 새 메일 그룹이 그룹 목록에 표시됩니다. **그룹 종류**에서 종류가 **메일 그룹**으로 표시됩니다.

  - 셸에서 다음 명령을 실행하여 새 메일 그룹에 대한 정보를 표시합니다.
    
        Get-DistributionGroup <Name> | FL Name,RecipientTypeDetails,PrimarySmtpAddress


> [!NOTE]
> 유니버설 메일 그룹만 만들거나 메일을 사용하도록 설정할 수 있습니다. 도메인 로컬 그룹이나 글로벌 그룹을 유니버설 그룹으로 변환하려면 셸에서 <A href="https://technet.microsoft.com/ko-kr/library/bb123770(v=exchg.150)">Set-Group</A> cmdlet을 사용할 수 있습니다. 유니버설 그룹이 아닌 이전 버전의 Exchange에서 마이그레이션된 그룹에 대해 메일을 사용하도록 설정할 수 있습니다. EAC 또는 셸을 사용하여 이러한 그룹을 관리할 수 있습니다.



## 메일 그룹 속성 변경

## EAC를 사용하여 메일 그룹 속성 변경

1.  EAC에서 **받는 사람** \> **그룹**으로 이동합니다.

2.  그룹 목록에서 보거나 변경할 메일 그룹을 클릭한 다음 **편집**![편집 아이콘](images/JJ218640.6f53ccb2-1f13-4c02-bea0-30690e6ea71d(EXCHG.150).gif "편집 아이콘")을 클릭합니다.

3.  그룹 속성 페이지에서 다음 섹션 중 하나를 클릭하여 속성을 보거나 변경합니다.
    
      - General
    
      - Ownership
    
      - Membership
    
      - Membership approval
    
      - Delivery management
    
      - Message approval
    
      - Email options
    
      - MailTip
    
      - Group delegation

## 일반

이 섹션을 사용하여 그룹에 대한 기본 정보를 보거나 변경합니다.

  - \* **표시 이름** 이 이름은 전자 메일의 주소록, 받는 사람: 줄(이 그룹으로 전자 메일을 보낸 경우), 그룹 목록에 표시됩니다. 표시 이름은 필수이며 다른 사람들이 알아 볼 수 있도록 친숙한 형태로 지정해야 합니다. 또한 도메인 내에서 고유해야 합니다.
    
    그룹 명명 규칙을 구현한 경우에는 표시 이름이 정책에 정의된 명명 규칙을 따라야 합니다.

  - \* **별칭**   전자 메일 주소 중에서 @ 기호 왼쪽에 표시되는 부분입니다. 별칭을 변경하면 그룹의 기본 SMTP 주소도 변경되며 새 별칭을 포함하게 됩니다. 또한 이전 별칭을 사용한 전자 메일 주소는 그룹의 프록시 주소로 남아 있습니다.

  - **설명**   이 입력란에는 다른 사람들이 그룹의 용도를 파악할 수 있도록 그룹에 대해 설명합니다. 이 설명은 주소록과 EAC의 세부 정보 창에 나타납니다.

  - **주소록에서 이 그룹 숨기기**   주소록에 이 그룹이 표시되지 않게 하려면 이 확인란을 선택합니다. 이 그룹으로 전자 메일을 보내려면 보내는 사람은 그룹의 별칭이나 전자 메일 주소를 받는 사람: 참조: 줄에 입력해야 합니다.
    

    > [!TIP]
    > 일반적으로 보안 그룹은 전자 메일을 보내는 용도가 아닌 그룹 구성원에게 사용 권한을 할당하는 데 사용되므로 숨기는 것이 좋습니다.



  - **조직 구성 단위**   이 읽기 전용 상자에는 메일 그룹이 있는 OU(조직 구성 단위)가 표시됩니다. 그룹을 다른 OU로 이동하려면 Active Directory 사용자 및 컴퓨터를 사용해야 합니다.

## 소유권

이 섹션을 사용하면 그룹 소유자를 할당할 수 있습니다. 그룹 소유자는 그룹에 구성원을 추가하고, 그룹 가입 또는 탈퇴 요청을 승인하거나 거부하고, 그룹에 전송된 메시지를 승인하거나 거부할 수 있습니다. 기본적으로 그룹을 만든 사람이 소유자가 됩니다. 모든 그룹에는 한 명 이상의 소유자가 있어야 합니다.

**추가** ![아이콘 추가](images/JJ218640.c1e75329-d6d7-4073-a27d-498590bbb558(EXCHG.150).gif "아이콘 추가")를 클릭하여 소유자를 추가할 수 있습니다. 소유자를 선택한 다음 **제거**![아이콘 제거](images/Dd362328.479b6ced-8d64-4277-a725-f17fea202b28(EXCHG.150).gif "아이콘 제거")를 클릭하여 소유자를 제거할 수 있습니다.

## 구성원

이 섹션을 사용하면 구성원을 추가하거나 제거할 수 있습니다. 그룹 소유자는 그룹의 구성원이 아니어도 됩니다. **구성원** 아래에서 **추가**![아이콘 추가](images/JJ218640.c1e75329-d6d7-4073-a27d-498590bbb558(EXCHG.150).gif "아이콘 추가")를 클릭하여 구성원을 추가할 수 있습니다. 구성원 목록에서 사용자를 선택한 다음 **제거**![아이콘 제거](images/Dd362328.479b6ced-8d64-4277-a725-f17fea202b28(EXCHG.150).gif "아이콘 제거")를 클릭하여 구성원을 제거할 수 있습니다.

## 구성원 승인

이 섹션을 사용하여 그룹에 가입하거나 그룹에서 탈퇴하려는 사용자에 대해 승인이 필요한지 여부를 지정할 수 있습니다.

  - **그룹에 가입하는 데 소유자 승인이 필요한지 여부를 선택하십시오.**   다음 설정 중 하나를 선택합니다.
    
      - **개방 모드: 그룹 소유자의 승인 없이 자유롭게 이 그룹에 가입할 수 있습니다.**
    
      - **폐쇄 모드: 그룹 소유자만이 구성원을 추가할 수 있음. 모든 참가 요청이 자동으로 거부됩니다.**
    
      - **소유자 승인: 모든 요청은 그룹 소유자가 직접 승인 또는 거절합니다.**   이 옵션을 선택하면 그룹 소유자가 그룹 가입 승인을 요청하는 전자 메일을 받게 됩니다.

  - **탈퇴할 그룹을 열지 여부를 선택하십시오.**   다음 설정 중 하나를 선택합니다.
    
      - **개방 모드: 누구나 그룹 소유자의 승인 없이 이 그룹을 탈퇴할 수 있습니다.**
    
      - **폐쇄 모드: 그룹 소유자만이 구성원을 제거할 수 있음. 모든 탈퇴 요청은 자동으로 거부됩니다.**

## 배달 관리

이 섹션을 사용하여 이 그룹으로 메일을 보낼 수 있는 사람을 관리합니다.

  - **조직 내부의 보낸 사람만**   조직 내의 보낸 사람만 그룹에 메시지를 보낼 수 있도록 하려면 이 옵션을 선택합니다. 즉, 조직 외부의 사람이 이 그룹에 전자 메일 메시지를 보내면 거부됩니다. 기본 설정입니다.

  - **조직 내부 및 외부의 보낸 사람**   이 옵션을 선택하면 모든 사람이 그룹에 메시지를 보낼 수 있습니다.
    
    특정 보낸 사람만 이 그룹에 메시지를 보낼 수 있도록 하여 메시지를 보낼 수 있는 사람을 추가로 제한할 수 있습니다. **추가**![아이콘 추가](images/JJ218640.c1e75329-d6d7-4073-a27d-498590bbb558(EXCHG.150).gif "아이콘 추가")를 클릭하고 하나 이상의 받는 사람을 선택합니다. 이 목록에 보낸 사람을 추가하면 목록에 있는 사람만 그룹에 메일을 보낼 수 있습니다. 목록에 없는 사람이 보낸 메일은 거부됩니다.
    
    목록에서 사람 또는 그룹을 제거하려면 목록에서 해당 사람 또는 그룹을 선택하고 **제거**![아이콘 제거](images/Dd362328.479b6ced-8d64-4277-a725-f17fea202b28(EXCHG.150).gif "아이콘 제거")를 클릭합니다.
    

    > [!IMPORTANT]
    > 조직 내부의 보낸 사람만 그룹에 메시지를 보낼 수 있도록 하는 그룹을 구성한 경우에는 이 목록에 추가하더라도 메일 연락처에서 보낸 전자 메일이 거부됩니다.



## 메시지 승인

이 섹션을 사용하여 그룹 중재 옵션을 설정합니다. 중재자는 메시지가 그룹 구성원에게 배달되기 전에 그룹으로 전송된 메시지를 승인 또는 거부합니다.

  - **이 그룹에 전송된 메시지는 중재자의 승인을 받아야 합니다.**   이 확인란은 기본적으로 선택되어 있지 않습니다. 이 확인란을 선택하면 그룹 중재자가 들어오는 메시지를 배달하기 전에 검토합니다. 그룹 중재자는 들어오는 메시지를 승인하거나 거부할 수 있습니다.

  - **그룹 중재자**   그룹 중재자를 추가하려면 **추가**![아이콘 추가](images/JJ218640.c1e75329-d6d7-4073-a27d-498590bbb558(EXCHG.150).gif "아이콘 추가")를 클릭합니다. 중재자를 제거하려면 해당 중재자를 선택하고 **제거**![아이콘 제거](images/Dd362328.479b6ced-8d64-4277-a725-f17fea202b28(EXCHG.150).gif "아이콘 제거")를 클릭합니다. "이 그룹에 전송된 메시지는 중재자의 승인을 받아야 합니다." 확인란을 선택하고 중재자를 선택하지 않으면 그룹으로 보내는 메시지는 승인을 위해 그룹 소유자에게 보내집니다.

  - **메시지 승인이 필요 없는 보낸 사람**    이 그룹에 대해 중재를 무시할 수 있는 사람이나 그룹을 추가하려면 **추가**![아이콘 추가](images/JJ218640.c1e75329-d6d7-4073-a27d-498590bbb558(EXCHG.150).gif "아이콘 추가")를 클릭합니다. 사람 또는 그룹을 제거하려면 해당 항목을 선택하고 **제거**![아이콘 제거](images/Dd362328.479b6ced-8d64-4277-a725-f17fea202b28(EXCHG.150).gif "아이콘 제거")를 클릭합니다.

  - **중재 알림 선택**   이 섹션에서는 메시지 승인에 대해 사용자들이 알림을 받는 방법을 설정합니다.
    
      - **모든 사용자에게 메시지가 승인되지 않았음을 알립니다.**   기본 설정입니다. 메시지가 승인되지 않으면 조직 내부 및 외부의 모든 보낸 사람에게 해당 사실을 알립니다.
    
      - **메시지가 승인되지 않았을 경우 조직의 보낸 사람에게 알립니다.**   이 옵션을 선택하면 그룹으로 보낸 메시지를 중재자가 승인하지 않는 경우 조직에 속한 사람이나 그룹에게만 해당 사실을 알립니다.
    
      - **승인 메시지가 아닌 경우 알림을 보내지 않습니다.**   이 옵션을 선택하면 그룹 중재자가 승인하지 않은 메시지를 보낸 사람에게 알림을 보내지 않습니다.

## 전자 메일 옵션

이 섹션을 사용하여 그룹과 연결된 전자 메일 주소를 보거나 변경합니다. 여기에는 그룹의 기본 SMTP 주소와 관련된 프록시 주소가 포함됩니다. 기본 SMTP 주소(*회신 주소*)는 주소록에 굵게 표시되며 대문자로 된 **SMTP** 값이 **유형** 열에 표시됩니다.

  - **추가**   이 사서함에 대해 새 전자 메일 주소를 추가하려면 **추가**![아이콘 추가](images/JJ218640.c1e75329-d6d7-4073-a27d-498590bbb558(EXCHG.150).gif "아이콘 추가")를 클릭합니다. 다음 주소 형식 중 하나를 선택합니다.
    
      - **SMTP**   기본 주소 유형입니다. 이 단추를 클릭하고 \* **전자 메일 주소** 상자에 새 SMTP 주소를 입력합니다.
        

        > [!NOTE]
        > 새 주소를 그룹의 기본 SMTP 주소로 지정하려면 <STRONG>이 주소를 회신 주소로 지정</STRONG> 확인란을 선택합니다.

    
      - **사용자 지정 주소 유형**   이 단추를 클릭하고 \* **전자 메일 주소** 상자에 지원되는 SMTP 이외의 전자 메일 주소 유형 중 하나를 입력합니다.
        

        > [!NOTE]
        > X.400 주소를 제외하고 Exchange는 사용자 지정 주소 형식이 올바른지 확인하지 않습니다. 지정하는 사용자 지정 주소는 해당 주소 유형에 대한 형식 요구 사항을 충족해야 합니다.



  - **편집**   그룹과 연결된 전자 메일 주소를 변경하려면 목록에서 주소를 선택한 다음 **편집**![편집 아이콘](images/JJ218640.6f53ccb2-1f13-4c02-bea0-30690e6ea71d(EXCHG.150).gif "편집 아이콘")을 클릭합니다.
    

    > [!NOTE]
    > 기존 주소를 그룹의 기본 SMTP 주소로 지정하려면 <STRONG>이 주소를 회신 주소로 지정</STRONG> 확인란을 선택합니다.



  - **제거**   그룹과 연결된 전자 메일 주소를 삭제하려면 목록에서 주소를 선택한 다음 **제거**![아이콘 제거](images/Dd362328.479b6ced-8d64-4277-a725-f17fea202b28(EXCHG.150).gif "아이콘 제거")을 클릭합니다.

  - **이 받는 사람에게 적용된 전자 메일 주소 정책에 따라 전자 메일 주소를 자동으로 업데이트**   조직의 전자 메일 주소 정책에 대한 변경 내용에 따라 받는 사람의 전자 메일 주소가 자동으로 업데이트되도록 하려면 이 확인란을 선택합니다. 이 확인란은 기본적으로 선택되어 있습니다.

## MailTip

이 섹션에서는 메일 설명을 추가하여 이 그룹으로 메시지를 보낼 경우 발생할 수 있는 문제를 사용자에게 알릴 수 있습니다. 메일 설명은 새 전자 메일 메시지의 받는 사람, 참조 또는 숨은 참조 필드에 이 그룹이 추가될 때 정보 표시줄에 표시되는 텍스트입니다. 예를 들어 대규모 그룹에 메일 설명을 추가하여 잠재적인 보낸 사람에게 자신의 메시지를 여러 사람에게 보낼 것임을 알려줄 수 있습니다.


> [!NOTE]
> 메일 설명은 HTML 태그를 포함할 수 있지만 스크립트는 사용할 수 없습니다. 표시되는 사용자 지정 메일 설명의 길이는 175자를 초과할 수 없습니다. 단, HTML 태그는 길이 제한 계산에 포함되지 않습니다.



## 그룹 위임

이 섹션에서는 사용자에게 그룹으로 메시지를 보내거나 그룹 대신 메시지를 보내기 위한 권한을 할당합니다(*위임*). 다음 권한을 할당할 수 있습니다.

  - **다른 사람 이름으로 보내기**   이 권한을 사용하면 대리인은 그룹으로서 메시지를 보낼 수 있습니다. 이 권한이 할당되면 대리인에게는 **보낸 사람** 줄에 그룹을 추가하여 해당 메시지를 그룹에서 보낸 것으로 표시할 수 있는 옵션이 제공됩니다.

  - **대신 보내기**   이 권한이 있어도 대리인은 그룹 대신 메시지를 보낼 수 있습니다. 이 사용 권한이 할당된 후 대리인은 **보낸 사람** 줄에 그룹을 추가할 수 있습니다. 메시지는 그룹이 보낸 것으로 나타나며 그룹 대신 대리인이 보낸 것으로 확인됩니다.

대리인에게 권한을 할당하려면 해당 권한 아래의 **추가**를 클릭하여 **받는 사람 선택** 페이지를 표시합니다. 이 페이지에는 해당 권한이 할당될 수 있는 Exchange 조직 내의 모든 받는 사람 목록이 표시됩니다. 원하는 받는 사람을 선택하여 목록에 추가한 다음 **확인**을 클릭합니다. 검색 상자에 받는 사람 이름을 입력한 다음 **검색**을 클릭하여 특정 받는 사람을 검색할 수도 있습니다.

## 셸을 사용하여 메일 그룹 속성 변경

메일 그룹의 속성을 보거나 변경하려면 **Get-DistributionGroup** 및 **Set-DistributionGroup** cmdlet을 사용합니다. 셸을 사용할 경우의 이점은 EAC에서 사용할 수 없는 속성을 변경하는 기능과 여러 그룹의 속성을 변경하는 기능입니다. 메일 그룹 속성에 해당하는 매개 변수에 대한 자세한 내용은 다음 항목을 참조하십시오.

  - [Get-DistributionGroup](https://technet.microsoft.com/ko-kr/library/bb124755\(v=exchg.150\))

  - [Set-DistributionGroup](https://technet.microsoft.com/ko-kr/library/bb124955\(v=exchg.150\))

다음은 셸을 사용하여 메일 그룹 속성을 변경하는 예입니다.

이 예에서는 Seattle Employees 메일 그룹의 기본 SMTP 주소(응답 주소라고도 함)를 employees@contoso.com에서 sea.employees@contoso.com으로 변경합니다. 아울러 이전 응답 주소는 프록시 주소로 유지합니다.

    Set-DistributionGroup "Seattle Employees" -EmailAddresses SMTP:sea.employees@contoso.com,smtp:employees@contoso.com

이 예에서는 조직의 모든 메일 그룹에 보낼 수 있는 최대 메시지 크기를 10MB로 제한합니다.

    Get-DistributionGroup -ResultSize unlimited -Filter {(RecipientTypeDetails -eq 'MailUniversalDistributionGroup')} | Set-DistributionGroup -MaxReceiveSize 10MB

이 예에서는 Customer Support 메일 그룹에 대한 중재를 사용하도록 설정하고 중재자를 Amy로 설정합니다. 또한 이 중재되는 메일 그룹은 메시지가 승인되지 않을 경우 조직 내에서 메일을 보낸 사람에게 이를 알립니다.

    Set-DistributionGroup -Identity "Customer Support" -ModeratedBy "Amy" -ModerationEnabled $true -SendModerationNotifications 'Internal'

이 예에서는 사용자가 만든 메일 그룹인 Dog Lovers를 변경하여 그룹 관리자가 사용자의 그룹 참여 요청을 승인하도록 합니다. 또한 *BypassSecurityGroupManagerCheck* 매개 변수를 사용하여 메일 그룹 설정이 변경되었음을 그룹 관리자에게 알리지 않도록 합니다.

    Set-DistributionGroup -Identity "Dog Lovers" -MemberJoinRestriction 'ApprovalRequired' -BypassSecurityGroupManagerCheck

## 작동 여부는 어떻게 확인합니까?

메일 그룹의 속성이 성공적으로 변경되었는지 확인하려면 다음을 수행하십시오.

  - EAC에서 해당 그룹을 선택하고 **편집**![편집 아이콘](images/JJ218640.6f53ccb2-1f13-4c02-bea0-30690e6ea71d(EXCHG.150).gif "편집 아이콘")을 클릭하여 변경한 속성이나 기능을 확인합니다. 변경한 속성에 따라, 선택한 그룹에 대한 세부 정보 창에 해당 속성 변경 내용이 표시될 수도 있습니다.

  - 셸에서 **Get-DistributionGroup** cmdlet을 사용하여 변경 사항을 확인합니다. 셸을 사용할 때 얻을 수 있는 한 가지 이점은 여러 그룹의 여러 속성을 볼 수 있다는 것입니다. 받는 사람 제한을 변경한 위의 예에서는 다음 명령을 실행하여 새 값을 확인합니다.
    
        Get-Mailbox -ResultSize unlimited -Filter {(RecipientTypeDetails -eq 'UserMailbox')} | fl Name,RecipientLimits
    
    메시지 제한이 변경된 위 예제의 경우 다음 명령을 실행합니다.
    
        Get-Mailbox -OrganizationalUnit "Marketing" | fl Name,IssueWarningQuota,ProhibitSendQuota,ProhibitSendReceiveQuota,UseDatabaseQuotaDefaults
