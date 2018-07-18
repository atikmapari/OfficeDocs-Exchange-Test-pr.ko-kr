﻿---
title: 'Exchange eDiscovery의 검색할 수 없는 항목: Exchange 2013 Help'
TOCTitle: Exchange eDiscovery의 검색할 수 없는 항목
ms:assetid: 32550081-9af9-474b-ae7b-28f1e68cad41
ms:mtpsurl: https://technet.microsoft.com/ko-kr/library/Dn602498(v=EXCHG.150)
ms:contentKeyID: 61071981
ms.date: 05/22/2018
mtps_version: v=EXCHG.150
ms.translationtype: MT
---

# Exchange eDiscovery의 검색할 수 없는 항목

 

_**적용 대상:** Exchange Online, Exchange Server 2013_

_**마지막으로 수정된 항목:** 2016-12-09_

Exchange Server 2013 및 Exchange Online 에 대 한 원본 위치 eDiscovery를 검색할 수 없는 항목에는 Exchange 검색을 통해 인덱싱할 수 없는 또는 있는 부분적 으로만 인덱싱된 사서함 항목은입니다. 검색할 수 없는 항목에는 일반적으로 전자 메일 메시지에 첨부 된 인덱싱할 수 없는 파일을 포함 합니다. 파일 검색용으로 인덱싱할 수 없습니다 및 전자 메일 메시지에 첨부 하는 경우에 검색할 수 없는 항목으로 반환 되는 몇가지 이유는 다음과 같습니다.

  - 파일 형식을 인덱싱하는 데 필요한 검색 필터(*IFilter*라고도 함)가 설치되어 있지 않아 파일 형식을 인덱싱할 수 없습니다.

  - 파일 형식이 인덱싱할 수 없도록 설정되어 있습니다.

  - 파일 형식 인덱싱은 지원되지만 특정 파일에 대해 인덱싱 오류가 발생했습니다.

  - 타사 기술을 사용하여 파일이 암호화되어 있습니다.

  - 파일이 암호로 보호되어 있습니다.

eDiscovery 검색을 정상적으로 수행하려면 조직에서 검색할 수 없는 항목을 검토해야 할 수 있습니다. eDiscovery 검색 결과를 검색 사서함에 복사하거나 PST 파일로 내보낼 때 검색할 수 없는 항목 포함 여부를 지정할 수 있습니다.

## 검색할 수 없는 파일 형식

비트맵 등의 파일 또는 MP3 파일을 특정 유형의 콘텐츠를 인덱싱할 수를 포함 되어있지 않습니다. 결과적으로, Exchange 검색 이러한 종류의 파일에 전체 텍스트 인덱싱을 수행 하지 않습니다. 이러한 종류의 파일은 지원 하지 않는 파일 형식으로 간주 됩니다. 파일 형식에는 전체 텍스트 인덱스를 비활성화 기본적으로 또는 관리자가 있습니다. 지원 되지않는 및 사용할 수 없는 파일 형식에는 eDiscovery 검색에서 검색할 수 없는 항목으로 간주 됩니다. 이러한 유형의 파일을 일반적으로 전자 메일 메시지에 연결 된 결과 집합을 검색할 수 없는 항목을 복사 하거나 검색 결과 내보낼 때를 포함 하는 경우에 포함 됩니다. 지원 되는 항목과 사용할 수 없는 파일 형식 목록이 [Exchange 검색에서 인덱싱하는 파일 형식](file-formats-indexed-by-exchange-search-exchange-2013-help.md)를 참조 하십시오. Exchange Server 2013 관리자는 [Set-SearchDocumentFormat](https://technet.microsoft.com/ko-kr/library/jj873756\(v=exchg.150\)) cmdlet을 사용 하 여 지원 되는 파일 형식에 대 한 인덱싱 해제할 수 있습니다. 이 cmdlet Exchange Online 에서 사용할 수 없습니다.

특정 사서함에서 검색할 수 없는 항목을 식별하려면 [Get-FailedContentIndexDocuments](https://technet.microsoft.com/ko-kr/library/dd351154\(v=exchg.150\)) cmdlet을 실행하여 검색 결과에 검색할 수 없는 항목을 포함하도록 선택하는 경우 복사되거나 내보낼 항목의 목록을 가져올 수 있습니다.

## 검색 결과에서 반환되는 지원되지 않는 파일 형식이 포함된 메시지

지원되지 않는 첨부 파일이 포함된 모든 메시지가 검색할 수 없는 항목으로 자동 반환되는 것은 아닙니다. 파일 이름 등의 다른 파일 속성은 인덱싱되어 검색 가능하기 때문입니다. 예를 들어 "재무" 키워드를 사용하여 검색하는 경우 해당 키워드가 파일 이름에 있으면 지원되지 않는 첨부 파일이 포함된 메시지가 반환됩니다. 키워드가 첨부된 파일 본문에만 있는 경우에는 메시지가 검색할 수 없는 항목으로 반환됩니다.

마찬가지로 인덱싱되어 검색할 수 있는 사서함 항목의 기타 속성이 검색 조건을 충족하면 지원되지 않는 첨부 파일이 포함된 메시지가 검색 결과에 포함됩니다. 검색을 위해 인덱싱되는 메시지 속성에는 보낸 날짜와 받은 날짜, 보낸 사람과 받은 사람, 첨부 파일의 이름, 메시지 본문의 텍스트 등이 있습니다. 따라서 메시지 첨부 파일을 검색할 수 없더라도 다른 메시지 속성의 값이 검색 조건과 일치하면 해당 메시지는 일반 검색 결과에 포함됩니다. 실제로 검색할 수 없는 첨부 파일이 포함된 메시지가 일반 검색 결과에 포함되는 경우를 흔히 볼 수 있습니다.

검색을 위해 인덱싱되는 전자 메일 메시지 속성의 목록은 [Exchange 검색에서 인덱싱하는 메시지 속성](message-properties-indexed-by-exchange-search-exchange-2013-help.md)을 참조하세요.

## 검색 결과에 검색할 수 없는 항목 포함

조직에서 검색할 수 없는 항목을 식별하고 추가 처리를 수행하여 해당 항목, 해당 항목에 포함된 내용 및 해당 항목의 관련성 여부를 확인해야 할 수 있습니다. eDiscovery 검색 결과에 검색할 수 없는 항목을 포함하려면 검색 결과를 복사하거나 내보낼 때 검색할 수 없는 항목 옵션을 사용할 수 있습니다. Exchange 또는 Exchange Online에서 원본 위치 eDiscovery를 사용할 때 검색할 수 없는 항목을 포함하려면 검색 결과를 검색 사서함에 복사하거나 PST 파일로 내보낼 때 **검색할 수 없는 항목 포함** 옵션을 선택합니다. SharePoint 또는 SharePoint Online에서 eDiscovery 센터를 사용할 때 검색할 수 없는 항목을 포함하려면 **암호화되거나 형식을 인식할 수 없는 항목 포함** 옵션을 선택합니다.

검색할 수 없는 항목을 복사하거나 내보낼 때는 다음 사항을 고려합니다.

  - 검색할 수 없는 항목을 검색 사서함에 복사할 때는 모든 검색할 수 없는 항목이 **Unsearchable**이라는 별도의 폴더에 복사됩니다. 이 폴더는 검색 결과가 포함된 폴더 아래에 있습니다. 검색 결과를 내보낼 때 검색할 수 없는 항목이 포함된 경우 별도의 PST 파일로 검색할 수 없는 항목을 내보냅니다.

  - 검색 결과에 검색할 수 없는 항목을 포함하면 검색 조건에 관계없이 검색되는 사서함의 모든 검색할 수 없는 항목이 반환됩니다.

  - 검색 결과에 모든 사서함 항목이 포함되도록 선택하는 경우 또는 검색 쿼리가 키워드를 지정하지 않거나 날짜 범위만 지정하는 경우에는 검색할 수 없는 항목이 포함된 옵션을 선택해도 검색할 수 없는 항목이 **Unsearchable** 폴더로 복사되지 않을 수 있습니다. 검색할 수 없는 항목을 비롯한 모든 항목이 일반 검색 결과에 자동으로 포함되기 때문입니다.

  - 앞에서 설명한 것처럼 메시지 속성과 메타데이터는 인덱싱되므로, 검색할 수 없는 파일이 첨부된 메시지의 속성이나 메타데이터에 특정 키워드가 나오는 경우 해당 키워드를 사용한 검색에서 결과가 반환될 수 있습니다. 또한 이 경우에는 같은 사서함 항목의 두 복사본이 검색 결과에 포함됩니다. 이러한 유형의 중복 결과를 방지하고 항목 복사본 하나만 일반 검색 결과에 포함하려면 검색 결과를 복사하거나 내보낼 때 **중복 제거 사용** 옵션을 선택하면 됩니다.

  - 검색 결과에 검색할 수 없는 항목을 포함하는 경우 표시되는 예상 검색 결과 수에도 영향을 줄 수 있습니다. 검색 결과를 복사할 때 검색할 수 없는 항목을 포함하면 총 예상 항목 수 및 총 예상 크기에 검색할 수 없는 항목이 포함됩니다.

검색할 수 없는 항목을 검색 결과에 포함하는 방법에 대한 자세한 내용은 다음 항목을 참조하세요.

  - [원본 위치 eDiscovery 검색 만들기](create-an-in-place-ediscovery-search-exchange-2013-help.md)

  - [PST 파일로 eDiscovery 검색 결과 내보내기](export-ediscovery-search-results-to-a-pst-file-exchange-2013-help.md)

  - [SharePoint: eDiscovery 콘텐츠 내보내기 및 보고서를 만들](https://go.microsoft.com/fwlink/p/?linkid=324757)

## 검색할 수 없는 항목에 대한 자세한 내용

  - 파일 형식이 Exchange Search에서 지원되며 전체 텍스트가 인덱싱되더라도 인덱싱 또는 검색 오류로 인해 파일이 검색할 수 없는 항목으로 반환될 수 있습니다. 예를 들어 매우 큰 Excel 파일 검색은 일부분은 정상적으로 진행될 수 있지만 크기 제한이 초과하면 실패합니다. 이 경우에는 동일한 파일이 검색 결과에서도 반환되고 검색할 수 없는 항목으로도 반환될 수 있습니다.

  - Microsoft 기술을 통해 암호화된 첨부 파일은 Exchange Search에서 인덱싱되며 검색됩니다. 타사 기술을 사용하여 암호화된 파일은 검색할 수 없는 항목으로 반환됩니다.

  - S/MIME으로 암호화된 전자 메일 메시지는 인덱싱되지 않으며 검색할 수 없는 항목으로 간주됩니다. 여기에는 암호화된 메시지가 포함됩니다(첨부 파일 포함 여부는 관계없음).

  - IRM(정보 권한 관리)을 사용하여 보호된 메시지는 Exchange Search에서 인덱싱되며 쿼리 매개 변수와 일치할 경우 검색 결과에 포함됩니다. IRM에 대한 자세한 내용은 [정보 권한 관리](information-rights-management-exchange-2013-help.md)를 참조하세요.

  - 앞에서 설명한 것처럼 메시지 속성과 메타데이터는 인덱싱되므로, 인덱싱된 메타데이터에 특정 키워드가 나오는 경우 해당 키워드를 사용한 검색에서 결과가 반환될 수 있습니다. 그러나 지원되지 않는 파일 형식의 첨부 항목 콘텐츠에만 키워드가 나오는 경우에는 같은 키워드 검색에서 동일 항목이 반환되지 않을 수 있습니다. 이 경우 항목은 검색할 수 없는 항목으로 반환됩니다.

  - Exchange 2010의 eDiscovery에는 *수신 허용 목록*이라는 개념이 있습니다. 수신 허용 목록에는 Windows Media 비디오(.wmv), 웨이브폼 오디오(.wav) 파일 등 검색할 수 없으므로 Exchange Search에서 인덱싱하지 않는 파일 형식이 포함됩니다. 이러한 파일 형식은 검색 가능한 콘텐츠가 포함되지 않으므로 Exchange 2010에서 검색할 수 없는 항목으로 간주되지 않습니다. 이러한 파일 형식이 포함된 사서함 항목은 검색할 수 없는 항목으로 반환되지 않으며 검색 사서함에 복사되지 않습니다.
    
    Exchange 2013 또는 Exchange Online에서는 수신 허용 목록이 더 이상 제공되지 않습니다. 파일 형식은 사용하거나 사용하지 않도록 설정되며, 그렇지 않으면 지원되지 않습니다. 사용하지 않도록 설정된 파일 형식과 지원되지 않는 파일 형식이 검색할 수 없는 항목으로 간주됩니다.
