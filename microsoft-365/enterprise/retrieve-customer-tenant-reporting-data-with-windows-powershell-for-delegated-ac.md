---
title: Abrufen von Kunden-Mandantenberichtsdaten mit Windows PowerShell für DAP-Partner
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
ms.openlocfilehash: 8ea5f9834bfcc0d517fc1e0938c3547d88d1d8a8
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50927216"
---
# <a name="retrieve-customer-tenant-reporting-data-with-windows-powershell-for-delegated-access-permissions-dap-partners"></a><span data-ttu-id="f3177-103">Abrufen von Kundenberichtsdaten über Windows PowerShell für Partner mit delegierten Zugriffsberechtigungen (Delegated Access Permission, DAP)</span><span class="sxs-lookup"><span data-stu-id="f3177-103">Retrieve customer tenant reporting data with Windows PowerShell for Delegated Access Permissions (DAP) partners</span></span>

<span data-ttu-id="f3177-104">*Dieser Artikel gilt sowohl für Microsoft 365 Enterprise als auch für Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="f3177-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="f3177-105">Verwenden Sie remote Windows PowerShell für Microsoft Exchange Online, um Berichte von einzelnen Kunden mandanten abzurufen.</span><span class="sxs-lookup"><span data-stu-id="f3177-105">Use remote Windows PowerShell for Microsoft Exchange Online to retrieve reports from individual customer tenants.</span></span>
  
<span data-ttu-id="f3177-106">Partner von Syndication und Cloud Solution Provider (CSP) können direkt über remote Windows PowerShell Exchange Online PowerShell auf die Daten zugreifen, aus denen Kunden-Mandantenberichte besteht.</span><span class="sxs-lookup"><span data-stu-id="f3177-106">Syndication and Cloud Solution Provider (CSP) partners can access the data that makes up customer tenant reports directly via remote Windows PowerShell for Exchange Online PowerShell.</span></span> <span data-ttu-id="f3177-107">Auf diese Weise können Partner die Berichtsdaten sammeln und speichern und anschließend andere Vorgänge damit durchführen.</span><span class="sxs-lookup"><span data-stu-id="f3177-107">This lets partners collect and save the reporting data and then perform other operations on it.</span></span> <span data-ttu-id="f3177-108">Nachdem Sie eine Remoteverbindung hergestellt haben, entspricht das Abrufen von Berichtsdaten zu einem Kundenmandanten dem Ausführen eines Cmdlets für einen Kundenmandanten.</span><span class="sxs-lookup"><span data-stu-id="f3177-108">After you open a remote connection, retrieving reporting data about a customer tenancy is identical to running any cmdlet against a customer tenancy.</span></span>
  
<span data-ttu-id="f3177-109">In diesem Artikel verwenden Sie remote Windows PowerShell Exchange Online, um eine Verbindung mit einem einzelnen Kundenwarte zu herstellen und einen Bericht abzurufen.</span><span class="sxs-lookup"><span data-stu-id="f3177-109">In this article, you use remote Windows PowerShell for Exchange Online to connect to a single customer tenancy and retrieve a report.</span></span> <span data-ttu-id="f3177-110">In der Standardeinstellung unterstützt Windows PowerShell das Aggregieren von Daten aus mehreren Kundenmandanten nicht.</span><span class="sxs-lookup"><span data-stu-id="f3177-110">By default, Windows PowerShell does not support aggregating reporting data from multiple customer tenancies.</span></span> <span data-ttu-id="f3177-111">Die mit diesem Verfahren abgerufenen Berichte sind nur für die  _DelegatedOrg_ bestimmt, mit er Sie eine Verbindung herstellen.</span><span class="sxs-lookup"><span data-stu-id="f3177-111">The reports you retrieve with this procedure are only for the  _DelegatedOrg_ that you connect to.</span></span>
  
 
## <a name="before-you-begin"></a><span data-ttu-id="f3177-112">Bevor Sie beginnen</span><span class="sxs-lookup"><span data-stu-id="f3177-112">Before you begin</span></span>

- <span data-ttu-id="f3177-p103">Sie müssen eine Verbindung zu Ihrem Exchange Online-Mandanten mithilfe von Windows PowerShell remote erstellen. Anweisungen hierzu finden Sie unter [Verbinden mit Exchange Online-Mandanten über eine Remotesitzung von Windows PowerShell für Partner mit delegierten Zugriffsberechtigungen (Delegated Access Permissions, DAP)](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="f3177-p103">You need to connect to your Exchange Online tenant by using remote Windows PowerShell. For instructions, see [Connect to Exchange Online tenants with remote Windows PowerShell for Delegated Access Permissions (DAP) partners](/powershell/exchange/connect-to-exchange-online-powershell)</span></span>
    
## <a name="run-the-get-stalemailboxreport-sample"></a><span data-ttu-id="f3177-115">Ausführen des Get-StaleMailboxReport-Beispiels</span><span class="sxs-lookup"><span data-stu-id="f3177-115">Run the Get-StaleMailboxReport sample</span></span>

<span data-ttu-id="f3177-116">Führen Sie nach dem Öffnen einer Remotesitzung mit Exchange Online diesen Befehl zum Abrufen von **Get-StaleMailboxReport** für den Datumsbereich 25.03.2015 bis 31.03.2015 aus.</span><span class="sxs-lookup"><span data-stu-id="f3177-116">After you have opened a remote session to Exchange Online, run this command to retrieve the **Get-StaleMailboxReport** for the date range 03/25/2015 through 03/31/2015.</span></span>
  
```
Get-StaleMailboxReport -StartDate 03/25/2015 -EndDate 03/31/2015
```

<span data-ttu-id="f3177-p104">Es stehen zahlreiche andere Berichterstellungs-Cmdlets für Exchange Online, Lync Online und SharePoint Online sowie andere für die Verfolgung von Nachrichten zur Verfügung, die Sie verwenden können. Weitere Informationen zu den verfügbaren Berichterstellungs-Cmdlets und zum Office 365 Reporting-Webdienst finden Sie in den Themen des folgenden Abschnitts.</span><span class="sxs-lookup"><span data-stu-id="f3177-p104">There are many other reporting cmdlets available for Exchange Online, Lync Online, and SharePoint Online as well as others for message tracing that you can use. To find out more about the available reporting cmdlets and the Office 365 Reporting web service, see the topics in the following section.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="f3177-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f3177-119">See also</span></span>

#### 

<span data-ttu-id="f3177-120">[Office 365-Berichterstattungswebdienst](/previous-versions/office/developer/o365-enterprise-developers/jj984325(v=office.15))</span><span class="sxs-lookup"><span data-stu-id="f3177-120">[Office 365 Reporting web service](/previous-versions/office/developer/o365-enterprise-developers/jj984325(v=office.15))</span></span>
  
[<span data-ttu-id="f3177-121">Cmdlets für die Berichterstellung in Exchange Online</span><span class="sxs-lookup"><span data-stu-id="f3177-121">Reporting cmdlets in Exchange Online</span></span>](/powershell/module/exchange/get-csclientdevicedetailreport)
  
[<span data-ttu-id="f3177-122">Hilfe für Partner</span><span class="sxs-lookup"><span data-stu-id="f3177-122">Help for partners</span></span>](https://go.microsoft.com/fwlink/p/?LinkID=533477)