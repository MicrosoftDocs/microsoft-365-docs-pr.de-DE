---
title: Verwenden des lokalen Microsoft 365-DLP-Scanners (Data Loss Prevention, Verhinderung von Datenverlust) (Vorschau)
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 07/21/2020
audience: ITPro
ms.topic: conceptual
f1_keywords:
- ms.o365.cc.DLPLandingPage
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- m365solution-mip
- m365initiative-compliance
search.appverid:
- MET150
description: Erfahren Sie, wie Sie den Microsoft 365-Scanner zur Verhinderung von Datenverlust vor Ort verwenden, um ruhende Daten zu scannen und Schutzmaßnahmen für lokale Dateifreigaben sowie lokale SharePoint-Ordner und Dokumentbibliotheken zu implementieren.
ms.openlocfilehash: 34be93f5c9980a7f8ea8ad31b708af14a8725f73
ms.sourcegitcommit: 070724118be25cd83418d2a56863da95582dae65
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/03/2021
ms.locfileid: "50417364"
---
# <a name="use-the-microsoft-365-data-loss-prevention-on-premises-scanner-preview"></a><span data-ttu-id="4e7e8-103">Verwenden Sie den lokalen Microsoft 365-Scanner zur Verhinderung von Datenverlust (Vorschau).</span><span class="sxs-lookup"><span data-stu-id="4e7e8-103">Use the Microsoft 365 data loss prevention on-premises scanner (preview)</span></span>

<span data-ttu-id="4e7e8-104">Um Sie mit den lokalen DLP-Funktionen und deren Darstellung in DLP-Richtlinien vertraut zu machen, haben wir einige Szenarien zusammengestellt, die Sie befolgen können.</span><span class="sxs-lookup"><span data-stu-id="4e7e8-104">To help familiarize you with DLP on-premises features and how they surface in DLP policies, we've put together some scenarios for you to follow.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="4e7e8-105">Diese lokalen DLP-Szenarien sind nicht die offiziellen Verfahren zum Erstellen und Optimieren von DLP-Richtlinien.</span><span class="sxs-lookup"><span data-stu-id="4e7e8-105">These DLP on-premises scenarios are not the official procedures for creating and tuning DLP policies.</span></span> <span data-ttu-id="4e7e8-106">In den folgenden Beiträgen finden Sie Informationen zum Arbeiten mit DLP-Richtlinien in Situationen allgemeiner Art:</span><span class="sxs-lookup"><span data-stu-id="4e7e8-106">Refer to the below topics when you need to work with DLP policies in general situations:</span></span>
>- [<span data-ttu-id="4e7e8-107">Verhinderung von Datenverlust – Übersicht</span><span class="sxs-lookup"><span data-stu-id="4e7e8-107">Overview of data loss prevention</span></span>](data-loss-prevention-policies.md)
>- [<span data-ttu-id="4e7e8-108">Erste Schritte mit der standardmäßigen DLP-Richtlinie</span><span class="sxs-lookup"><span data-stu-id="4e7e8-108">Get started with the default DLP policy</span></span>](get-started-with-the-default-dlp-policy.md)
>- [<span data-ttu-id="4e7e8-109">Erstellen einer DLP-Richtlinie aus einer Vorlage</span><span class="sxs-lookup"><span data-stu-id="4e7e8-109">Create a DLP policy from a template</span></span>](create-a-dlp-policy-from-a-template.md)
>- [<span data-ttu-id="4e7e8-110">Erstellen, Testen und Optimieren einer DLP-Richtlinie</span><span class="sxs-lookup"><span data-stu-id="4e7e8-110">Create, test, and tune a DLP policy</span></span>](create-test-tune-dlp-policy.md)

### <a name="scenario-discover-files-matching-dlp-rules"></a><span data-ttu-id="4e7e8-111">Diese lokalen DLP-Szenarien sind nicht die offiziellen Verfahren zum Erstellen und Optimieren von DLP-Richtlinien.</span><span class="sxs-lookup"><span data-stu-id="4e7e8-111">Scenario: Discover files matching DLP rules</span></span>

<span data-ttu-id="4e7e8-112">Daten von lokalen DLP-Scanneroberflächen in mehreren Bereichen</span><span class="sxs-lookup"><span data-stu-id="4e7e8-112">Data from DLP on-premises scanner surfaces in several areas</span></span>

#### <a name="activity-explorer"></a><span data-ttu-id="4e7e8-113">Aktivitäten-Explorer</span><span class="sxs-lookup"><span data-stu-id="4e7e8-113">Activity explorer</span></span>

 <span data-ttu-id="4e7e8-114">Lokaler Microsoft DLP erkennt DLP-Regelübereinstimmungen und meldet sie an [Aktivitäten-Explorer](https://compliance.microsoft.com/dataclassification?viewid=activitiesexplorer).</span><span class="sxs-lookup"><span data-stu-id="4e7e8-114">Microsoft DLP for on-premises detects DLP rule matches and reports them to [Activity Explorer](https://compliance.microsoft.com/dataclassification?viewid=activitiesexplorer).</span></span> 
 
#### <a name="microsoft-365-audit-log"></a><span data-ttu-id="4e7e8-115">Microsoft 365-Überwachungsprotokoll</span><span class="sxs-lookup"><span data-stu-id="4e7e8-115">Microsoft 365 Audit log</span></span>

<span data-ttu-id="4e7e8-116">Während der öffentlichen Vorschau sind die DLP-Regelübereinstimmungen in der Benutzeroberfläche des Überwachungsprotokolls verfügbar. Weitere Informationen finden Sie unter [Durchsuchen des Überwachungsprotokolls im Compliance Center](search-the-audit-log-in-security-and-compliance.md) oder bei  [Search-UnifiedAuditLog](https://docs.microsoft.com/powershell/module/exchange/search-unifiedauditlog?view=exchange-ps) PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4e7e8-116">During the public preview the DLP rule matches are available in Audit log UI, see [Search the audit log in the compliance center](search-the-audit-log-in-security-and-compliance.md)  or accessible by [Search-UnifiedAuditLog](https://docs.microsoft.com/powershell/module/exchange/search-unifiedauditlog?view=exchange-ps) PowerShell.</span></span>

#### <a name="aip"></a><span data-ttu-id="4e7e8-117">AIP</span><span class="sxs-lookup"><span data-stu-id="4e7e8-117">AIP</span></span>

<span data-ttu-id="4e7e8-118">Erkennungsdaten sind in einem lokalen Bericht im CSV-Format verfügbar, der gespeichert ist unter:</span><span class="sxs-lookup"><span data-stu-id="4e7e8-118">Discovery data is available in a local report in csv format which is stored under:</span></span>

<span data-ttu-id="4e7e8-119">**%localappdata%\Microsoft\MSIP\Scanner\Reports\DetailedReport_%timestamp%.csv report**.</span><span class="sxs-lookup"><span data-stu-id="4e7e8-119">**%localappdata%\Microsoft\MSIP\Scanner\Reports\DetailedReport_%timestamp%.csv report**.</span></span>

 <span data-ttu-id="4e7e8-120">Suchen Sie nach den folgenden Spalten:</span><span class="sxs-lookup"><span data-stu-id="4e7e8-120">Look for the following columns:</span></span>
- <span data-ttu-id="4e7e8-121">DLP-Modus</span><span class="sxs-lookup"><span data-stu-id="4e7e8-121">DLP Mode</span></span>
- <span data-ttu-id="4e7e8-122">DLP-Status</span><span class="sxs-lookup"><span data-stu-id="4e7e8-122">DLP Status</span></span>
- <span data-ttu-id="4e7e8-123">DLP-Kommentar</span><span class="sxs-lookup"><span data-stu-id="4e7e8-123">DLP Comment</span></span>
- <span data-ttu-id="4e7e8-124">DLP-Regelname DLP-Aktionen</span><span class="sxs-lookup"><span data-stu-id="4e7e8-124">DLP Rule Name DLP Actions</span></span>
- <span data-ttu-id="4e7e8-125">Besitzer</span><span class="sxs-lookup"><span data-stu-id="4e7e8-125">Owner</span></span>
- <span data-ttu-id="4e7e8-126">Aktuelle NTFS-Berechtigungen (SDDL)</span><span class="sxs-lookup"><span data-stu-id="4e7e8-126">Current NTFS Permissions (SDDL)</span></span>
- <span data-ttu-id="4e7e8-127">Angewandte NTFS-Berechtigungen (SDDL)</span><span class="sxs-lookup"><span data-stu-id="4e7e8-127">Applied NTFS Permissions (SDDL)</span></span>
- <span data-ttu-id="4e7e8-128">NTFS-Berechtigungstyp</span><span class="sxs-lookup"><span data-stu-id="4e7e8-128">NTFS permissions type</span></span>
 
### <a name="scenario-enforce-dlp-rule"></a><span data-ttu-id="4e7e8-129">Szenario: DLP-Regel erzwingen</span><span class="sxs-lookup"><span data-stu-id="4e7e8-129">Scenario: Enforce DLP rule</span></span> 

<span data-ttu-id="4e7e8-130">Wenn Sie DLP-Regeln für die gescannten Dateien erzwingen möchten, muss die Durchsetzung sowohl für den Inhaltsscanauftrag in AIP als auch auf Richtlinienebene in DLP aktiviert sein.</span><span class="sxs-lookup"><span data-stu-id="4e7e8-130">If you want to enforce DLP rules on the scanned files, enforcement must be enabled on both the content scan job in AIP and at the policy level in DLP.</span></span>


#### <a name="configure-dlp-to-enforce-policy-actions"></a><span data-ttu-id="4e7e8-131">Konfigurieren Sie DLP, um Richtlinienaktionen zu erzwingen</span><span class="sxs-lookup"><span data-stu-id="4e7e8-131">Configure DLP to enforce policy actions</span></span>

1. <span data-ttu-id="4e7e8-132">Öffnen Sie die [Seite zur Verhinderung von Datenverlust](https://compliance.microsoft.com/datalossprevention?viewid=policies) und wählen Sie die DLP-Richtlinie aus, die auf die lokalen Standortrepositorys ausgerichtet ist, die Sie in AIP konfiguriert haben.</span><span class="sxs-lookup"><span data-stu-id="4e7e8-132">Open the [Data loss prevention page](https://compliance.microsoft.com/datalossprevention?viewid=policies) and select the DLP policy that is targeted to the on-premises location repositories you have configured in AIP.</span></span> 
2. <span data-ttu-id="4e7e8-133">Bearbeiten Sie die Richtlinie.</span><span class="sxs-lookup"><span data-stu-id="4e7e8-133">Edit the policy.</span></span>
3. <span data-ttu-id="4e7e8-134">Wählen Sie auf der Seite **Testen oder Aktivieren der Richtlinie** die Option **Ja, sofort aktivieren**.</span><span class="sxs-lookup"><span data-stu-id="4e7e8-134">On the **Test or turn on the policy** page, select **Yes, turn it on right away**.</span></span> 

## <a name="see-also"></a><span data-ttu-id="4e7e8-135">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4e7e8-135">See also</span></span>

- [<span data-ttu-id="4e7e8-136">Erfahren Sie mehr über den lokalen DLP-Scanner (Vorschau)</span><span class="sxs-lookup"><span data-stu-id="4e7e8-136">Learn about DLP on-premises scanner (preview)</span></span>](dlp-on-premises-scanner-learn.md)
- [<span data-ttu-id="4e7e8-137">Erste Schritte mit dem lokalen DLP-Scanner (Vorschau)</span><span class="sxs-lookup"><span data-stu-id="4e7e8-137">Get started with  DLP on-premises scanner (preview)</span></span>](dlp-on-premises-scanner-get-started.md)
- [<span data-ttu-id="4e7e8-138">Verhinderung von Datenverlust – Übersicht</span><span class="sxs-lookup"><span data-stu-id="4e7e8-138">Overview of data loss prevention</span></span>](data-loss-prevention-policies.md)
- [<span data-ttu-id="4e7e8-139">Erstellen, Testen und Optimieren einer DLP-Richtlinie</span><span class="sxs-lookup"><span data-stu-id="4e7e8-139">Create, test, and tune a DLP policy</span></span>](create-test-tune-dlp-policy.md)
- [<span data-ttu-id="4e7e8-140">Erste Schritte mit dem Aktivitäten-Explorer</span><span class="sxs-lookup"><span data-stu-id="4e7e8-140">Get started with Activity explorer</span></span>](data-classification-activity-explorer.md)
