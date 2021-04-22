---
title: Übersicht über den Informationsschutz in Windows
ms.reviewer: ''
description: Informationen zur Funktionsweise des Informationsschutzes in Windows zum Identifizieren und Schützen vertraulicher Informationen
keywords: Informationen, Schutz, dlp, Daten, Verlust, Verhinderung, Schutz
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 65c5161f110e95008f2dc56aa3a2d17266ac1cb1
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933349"
---
# <a name="information-protection-in-windows-overview"></a><span data-ttu-id="e92d9-104">Übersicht über den Informationsschutz in Windows</span><span class="sxs-lookup"><span data-stu-id="e92d9-104">Information protection in Windows overview</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="e92d9-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="e92d9-105">**Applies to:**</span></span>

- [<span data-ttu-id="e92d9-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="e92d9-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="e92d9-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e92d9-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="e92d9-108">Möchten Sie Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="e92d9-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="e92d9-109">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="e92d9-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 


[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="e92d9-110">Der Informationsschutz ist ein integraler Bestandteil der Microsoft 365 Enterprise-Suite und bietet intelligenten Schutz, um vertrauliche Daten zu schützen und gleichzeitig die Produktivität am Arbeitsplatz zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="e92d9-110">Information protection is an integral part of Microsoft 365 Enterprise suite, providing intelligent protection to keep sensitive data secure while enabling productivity in the workplace.</span></span>


>[!TIP]
> <span data-ttu-id="e92d9-111">Lesen Sie unseren Blogbeitrag zur Integration von Microsoft Defender for Endpoint in Microsoft Information Protection, um vertrauliche Daten auf Windows-Geräten zu ermitteln, zu schützen und [zu überwachen.](https://cloudblogs.microsoft.com/microsoftsecure/2019/01/17/windows-defender-atp-integrates-with-microsoft-information-protection-to-discover-protect-and-monitor-sensitive-data-on-windows-devices/)</span><span class="sxs-lookup"><span data-stu-id="e92d9-111">Read our blog post about how Microsoft Defender for Endpoint integrates with Microsoft Information Protection to [discover, protect, and monitor sensitive data on Windows devices](https://cloudblogs.microsoft.com/microsoftsecure/2019/01/17/windows-defender-atp-integrates-with-microsoft-information-protection-to-discover-protect-and-monitor-sensitive-data-on-windows-devices/).</span></span>

<span data-ttu-id="e92d9-112">Defender for Endpoint wendet die folgenden Methoden zum Ermitteln, Klassifizieren und Schützen von Daten an:</span><span class="sxs-lookup"><span data-stu-id="e92d9-112">Defender for Endpoint applies the following methods to discover, classify, and protect data:</span></span>

- <span data-ttu-id="e92d9-113">**Datenermittlung** – Identifizieren vertraulicher Daten auf gefährdeten Windows-Geräten</span><span class="sxs-lookup"><span data-stu-id="e92d9-113">**Data discovery** - Identify sensitive data on Windows devices at risk</span></span>
- <span data-ttu-id="e92d9-114">**Datenklassifizierung** – Automatische Klassifizierung von Daten basierend auf gängigen Microsoft Information Protection (MIP)-Richtlinien, die in Office 365 Security & Compliance Center verwaltet werden.</span><span class="sxs-lookup"><span data-stu-id="e92d9-114">**Data classification** - Automatically classify data based on common Microsoft Information Protection (MIP) policies managed in Office 365 Security & Compliance Center.</span></span> <span data-ttu-id="e92d9-115">Mit der automatischen Klassifizierung können Sie vertrauliche Daten auch dann schützen, wenn der Endbenutzer sie nicht manuell klassifiziert hat.</span><span class="sxs-lookup"><span data-stu-id="e92d9-115">Auto-classification allows you to protect sensitive data even if the end user hasn’t manually classified it.</span></span>


## <a name="data-discovery-and-data-classification"></a><span data-ttu-id="e92d9-116">Datenermittlung und Datenklassifizierung</span><span class="sxs-lookup"><span data-stu-id="e92d9-116">Data discovery and data classification</span></span>

<span data-ttu-id="e92d9-117">Defender for Endpoint ermittelt Automatisch Dateien mit Vertraulichkeitsbezeichnungen und Dateien, die vertrauliche Informationstypen enthalten.</span><span class="sxs-lookup"><span data-stu-id="e92d9-117">Defender for Endpoint automatically discovers files with sensitivity labels and files that contain sensitive information types.</span></span>

<span data-ttu-id="e92d9-118">Vertraulichkeitsbezeichnungen klassifizieren und schützen vertrauliche Inhalte.</span><span class="sxs-lookup"><span data-stu-id="e92d9-118">Sensitivity labels classify and help protect sensitive content.</span></span>

<span data-ttu-id="e92d9-119">Typen vertraulicher Informationen in der Office 365 Data Loss Prevention (DLP)-Implementierung fallen in zwei Kategorien:</span><span class="sxs-lookup"><span data-stu-id="e92d9-119">Sensitive information types in the Office 365 data loss prevention (DLP) implementation fall under two categories:</span></span>

- <span data-ttu-id="e92d9-120">Standard</span><span class="sxs-lookup"><span data-stu-id="e92d9-120">Default</span></span>
- <span data-ttu-id="e92d9-121">Benutzerdefiniert</span><span class="sxs-lookup"><span data-stu-id="e92d9-121">Custom</span></span>

<span data-ttu-id="e92d9-122">Zu den standardmäßigen vertraulichen Informationstypen gehören Informationen wie Bankkontonummern, Sozialversicherungsnummern oder nationale IDs.</span><span class="sxs-lookup"><span data-stu-id="e92d9-122">Default sensitive information types include information such as bank account numbers, social security numbers, or national IDs.</span></span> <span data-ttu-id="e92d9-123">Weitere Informationen finden Sie unter [What the sensitive information type look for](https://docs.microsoft.com/office365/securitycompliance/what-the-sensitive-information-types-look-for).</span><span class="sxs-lookup"><span data-stu-id="e92d9-123">For more information, see [What the sensitive information type look for](https://docs.microsoft.com/office365/securitycompliance/what-the-sensitive-information-types-look-for).</span></span>

<span data-ttu-id="e92d9-124">Benutzerdefinierte Typen sind diejenigen, die Sie definieren und zum Schutz einer anderen Art vertraulicher Informationen (z. B. Mitarbeiter-IDs oder Projektnummern) entworfen haben.</span><span class="sxs-lookup"><span data-stu-id="e92d9-124">Custom types are ones that you define and is designed to protect a different type of sensitive information (for example, employee IDs or project numbers).</span></span> <span data-ttu-id="e92d9-125">Weitere Informationen finden Sie unter [Create a custom sensitive information type](https://docs.microsoft.com/office365/securitycompliance/create-a-custom-sensitive-information-type).</span><span class="sxs-lookup"><span data-stu-id="e92d9-125">For more information see, [Create a custom sensitive information type](https://docs.microsoft.com/office365/securitycompliance/create-a-custom-sensitive-information-type).</span></span>

<span data-ttu-id="e92d9-126">Wenn eine Datei auf einem Windows-Gerät erstellt oder bearbeitet wird, überprüft Defender for Endpoint den Inhalt, um zu bewerten, ob sie vertrauliche Informationen enthält.</span><span class="sxs-lookup"><span data-stu-id="e92d9-126">When a file is created or edited on a  Windows device, Defender for Endpoint scans the content to evaluate if it contains sensitive information.</span></span>

<span data-ttu-id="e92d9-127">Aktivieren Sie die Azure Information Protection-Integration, sodass eine Datei, die vertrauliche Informationen enthält, von Defender for Endpoint mit Bezeichnungen oder Informationstypen erkannt wird, automatisch vom Gerät an Azure Information Protection weitergeleitet wird.</span><span class="sxs-lookup"><span data-stu-id="e92d9-127">Turn on the Azure Information Protection integration so that when a file that contains sensitive information is discovered by Defender for Endpoint though labels or information types, it is automatically forwarded to Azure Information Protection from the device.</span></span>

![Abbildung der Einstellungsseite mit Azure Information Protection](images/atp-settings-aip.png)

<span data-ttu-id="e92d9-129">Die gemeldeten Signale können im Azure Information Protection – Data Discovery Dashboard angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="e92d9-129">The reported signals can be viewed on the Azure Information Protection – Data discovery dashboard.</span></span>

## <a name="azure-information-protection---data-discovery-dashboard"></a><span data-ttu-id="e92d9-130">Azure Information Protection – Datenermittlungsdashboard</span><span class="sxs-lookup"><span data-stu-id="e92d9-130">Azure Information Protection - Data discovery dashboard</span></span>

<span data-ttu-id="e92d9-131">Dieses Dashboard enthält eine Zusammenfassung der Ermittlungsinformationen von Daten, die sowohl von Defender for Endpoint als auch von Azure Information Protection entdeckt wurden.</span><span class="sxs-lookup"><span data-stu-id="e92d9-131">This dashboard presents a summarized discovery information of data discovered by both Defender for Endpoint and Azure Information Protection.</span></span> <span data-ttu-id="e92d9-132">Daten von Defender for Endpoint sind mit Location Type - Endpoint gekennzeichnet.</span><span class="sxs-lookup"><span data-stu-id="e92d9-132">Data from Defender for Endpoint is marked with Location Type - Endpoint.</span></span>

![Abbildung von Azure Information Protection – Datenermittlung](images/azure-data-discovery.png)

<span data-ttu-id="e92d9-134">Beachten Sie die Spalte Geräterisiko auf der rechten Seite, dieses Geräterisiko wird direkt von Defender for Endpoint abgeleitet und gibt die Risikostufe des Sicherheitsgeräts an, auf dem die Datei gefunden wurde, basierend auf den aktiven Sicherheitsbedrohungen, die von Defender for Endpoint erkannt wurden.</span><span class="sxs-lookup"><span data-stu-id="e92d9-134">Notice the Device Risk column on the right, this device risk is derived directly from Defender for Endpoint, indicating the risk level of the security device where the file was discovered, based on the active security threats detected by Defender for Endpoint.</span></span>

<span data-ttu-id="e92d9-135">Klicken Sie auf ein Gerät, um eine Liste der auf diesem Gerät beobachteten Dateien mit ihren Vertraulichkeitsbezeichnungen und Informationstypen zu sehen.</span><span class="sxs-lookup"><span data-stu-id="e92d9-135">Click on a device to view a list of files observed on this device, with their sensitivity labels and information types.</span></span>

>[!NOTE]
><span data-ttu-id="e92d9-136">Bitte lassen Sie ungefähr 15 bis 20 Minuten zu, damit die Azure Information Protection Dashboard Discovery ermittelte Dateien wiederspiegelt.</span><span class="sxs-lookup"><span data-stu-id="e92d9-136">Please allow approximately 15-20 minutes for the Azure Information Protection Dashboard Discovery to reflect discovered files.</span></span>

## <a name="log-analytics"></a><span data-ttu-id="e92d9-137">Log Analytics</span><span class="sxs-lookup"><span data-stu-id="e92d9-137">Log Analytics</span></span>

<span data-ttu-id="e92d9-138">Die auf Defender for Endpoint basierende Datenermittlung ist auch in [Azure Log Analytics](https://docs.microsoft.com/azure/log-analytics/log-analytics-overview)verfügbar, wo Sie komplexe Abfragen über die Rohdaten ausführen können.</span><span class="sxs-lookup"><span data-stu-id="e92d9-138">Data discovery based on Defender for Endpoint is also available in [Azure Log Analytics](https://docs.microsoft.com/azure/log-analytics/log-analytics-overview), where you can perform complex queries over the raw data.</span></span>

<span data-ttu-id="e92d9-139">Weitere Informationen zur Azure Information Protection-Analyse finden Sie unter [Zentrale Berichterstellung für Azure Information Protection](https://docs.microsoft.com/azure/information-protection/reports-aip).</span><span class="sxs-lookup"><span data-stu-id="e92d9-139">For more information on Azure Information Protection analytics, see [Central reporting for Azure Information Protection](https://docs.microsoft.com/azure/information-protection/reports-aip).</span></span>

<span data-ttu-id="e92d9-140">Öffnen Sie Azure Log Analytics im Azure-Portal, und öffnen Sie einen Abfrage-Generator (standard oder klassisch).</span><span class="sxs-lookup"><span data-stu-id="e92d9-140">Open Azure Log Analytics in Azure portal and open a query builder (standard or classic).</span></span>

<span data-ttu-id="e92d9-141">Führen Sie zum Anzeigen von Defender for Endpoint-Daten eine Abfrage aus, die die folgenden Informationen enthält:</span><span class="sxs-lookup"><span data-stu-id="e92d9-141">To view Defender for Endpoint data, perform a query that contains:</span></span>

```
InformationProtectionLogs_CL
| where Workload_s == "Windows Defender"
```

<span data-ttu-id="e92d9-142">**Voraussetzungen:**</span><span class="sxs-lookup"><span data-stu-id="e92d9-142">**Prerequisites:**</span></span>

- <span data-ttu-id="e92d9-143">Kunden müssen über ein Abonnement für Azure Information Protection verfügen.</span><span class="sxs-lookup"><span data-stu-id="e92d9-143">Customers must have a subscription for Azure Information Protection.</span></span>
- <span data-ttu-id="e92d9-144">Aktivieren der Azure Information Protection-Integration in Microsoft Defender Security Center:</span><span class="sxs-lookup"><span data-stu-id="e92d9-144">Enable Azure Information Protection integration in Microsoft Defender Security Center:</span></span>
    - <span data-ttu-id="e92d9-145">Wechseln Sie **zu Einstellungen** im Microsoft Defender Security Center, klicken Sie unter Allgemein **auf Erweiterte** **Einstellungen.**</span><span class="sxs-lookup"><span data-stu-id="e92d9-145">Go to **Settings** in Microsoft Defender Security Center, click on **Advanced Settings** under **General**.</span></span>



