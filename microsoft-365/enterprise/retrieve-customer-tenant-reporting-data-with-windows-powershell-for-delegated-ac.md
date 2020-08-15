---
title: Abrufen von Kundenmandanten Berichtsdaten mit Windows PowerShell für DAP-Partner
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection: Ent_O365
f1.keywords:
- NOCSH
ms.custom: seo-marvel-apr2020
ms.assetid: 893e5275-30b3-433f-8ecd-644f78f513e2
description: 'Zusammenfassung: Verwenden Sie Windows PowerShell für Microsoft Exchange Online remote, um Berichte von einzelnen Kundenmandanten abzurufen.'
ms.openlocfilehash: 24d56fffa60232c4ea39f4fe7769131cab23be2f
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46690349"
---
# <a name="retrieve-customer-tenant-reporting-data-with-windows-powershell-for-delegated-access-permissions-dap-partners"></a>Abrufen von Kundenberichtsdaten über Windows PowerShell für Partner mit delegierten Zugriffsberechtigungen (Delegated Access Permission, DAP)

*Dieser Artikel gilt sowohl für Microsoft 365 Enterprise als auch für Office 365 Enterprise.*

Verwenden Sie Remote Windows PowerShell für Microsoft Exchange Online, um Berichte von einzelnen Kundenmandanten abzurufen.
  
Partner für Syndication und Cloud Solution Provider (CSP) können auf die Daten zugreifen, aus denen Kundenmandanten Berichte direkt über Remote Windows PowerShell für Exchange Online PowerShell erstellt werden. Auf diese Weise können Partner die Berichtsdaten sammeln und speichern und anschließend andere Vorgänge damit durchführen. Nachdem Sie eine Remoteverbindung hergestellt haben, entspricht das Abrufen von Berichtsdaten zu einem Kundenmandanten dem Ausführen eines Cmdlets für einen Kundenmandanten.
  
In diesem Artikel verwenden Sie die Remote Windows PowerShell für Exchange Online, um eine Verbindung mit einer einzelnen Kunden Mandantschaft herzustellen und einen Bericht abzurufen. In der Standardeinstellung unterstützt Windows PowerShell das Aggregieren von Daten aus mehreren Kundenmandanten nicht. Die mit diesem Verfahren abgerufenen Berichte sind nur für die  _DelegatedOrg_ bestimmt, mit er Sie eine Verbindung herstellen.
  
 
## <a name="before-you-begin"></a>Bevor Sie beginnen

- Sie müssen eine Verbindung zu Ihrem Exchange Online-Mandanten mithilfe von Windows PowerShell remote erstellen. Anweisungen hierzu finden Sie unter [Verbinden mit Exchange Online-Mandanten über eine Remotesitzung von Windows PowerShell für Partner mit delegierten Zugriffsberechtigungen (Delegated Access Permissions, DAP)](connect-to-exchange-online-tenants-with-remote-windows-powershell-for-delegated.md).
    
## <a name="run-the-get-stalemailboxreport-sample"></a>Ausführen des Get-StaleMailboxReport-Beispiels

Führen Sie nach dem Öffnen einer Remotesitzung mit Exchange Online diesen Befehl zum Abrufen von **Get-StaleMailboxReport** für den Datumsbereich 25.03.2015 bis 31.03.2015 aus.
  
```
Get-StaleMailboxReport -StartDate 03/25/2015 -EndDate 03/31/2015
```

Es stehen zahlreiche andere Berichterstellungs-Cmdlets für Exchange Online, Lync Online und SharePoint Online sowie andere für die Verfolgung von Nachrichten zur Verfügung, die Sie verwenden können. Weitere Informationen zu den verfügbaren Berichterstellungs-Cmdlets und zum Office 365 Reporting-Webdienst finden Sie in den Themen des folgenden Abschnitts.
  
## <a name="see-also"></a>Siehe auch

#### 

[Office 365-Berichterstattungswebdienst](https://go.microsoft.com/fwlink/p/?LinkId=532777)
  
[Cmdlets für die Berichterstellung in Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=526430)
  
[Hilfe für Partner](https://go.microsoft.com/fwlink/p/?LinkID=533477)

