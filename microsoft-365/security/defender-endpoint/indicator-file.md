---
title: Erstellen von Indikatoren für Dateien
ms.reviewer: ''
description: Erstellen Sie Indikatoren für einen Dateihash, der die Erkennung, Verhinderung und den Ausschluss von Entitäten definiert.
keywords: datei, hash, manage, allowed, blocked, block, clean, malicious, file hash, ip address, urls, domain
search.product: eADQiWindows 10XVcnh
search.appverid: met150
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
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 35a0b66a4cdc4cf39c15329eda2e0aafced79f34
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/25/2021
ms.locfileid: "51199609"
---
# <a name="create-indicators-for-files"></a><span data-ttu-id="67ef8-104">Erstellen von Indikatoren für Dateien</span><span class="sxs-lookup"><span data-stu-id="67ef8-104">Create indicators for files</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="67ef8-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="67ef8-105">**Applies to:**</span></span>
- [<span data-ttu-id="67ef8-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="67ef8-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="67ef8-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="67ef8-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)



> [!TIP]
> <span data-ttu-id="67ef8-108">Möchten Sie Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="67ef8-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="67ef8-109">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="67ef8-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/en-us/WindowsForBusiness/windows-atp?ocid=docs-wdatp-automationexclusionlist-abovefoldlink)

<span data-ttu-id="67ef8-110">Sie können die weitere Verbreitung eines Angriffs in Ihrer Organisation verhindern, indem Sie potenziell schädliche Dateien oder mutmaßliche Schadsoftware verbieten.</span><span class="sxs-lookup"><span data-stu-id="67ef8-110">You can prevent further propagation of an attack in your organization by banning potentially malicious files or suspected malware.</span></span> <span data-ttu-id="67ef8-111">Wenn Sie eine potenziell schädliche ausführbare Datei (PE) kennen, können Sie sie blockieren.</span><span class="sxs-lookup"><span data-stu-id="67ef8-111">If you know a potentially malicious portable executable (PE) file, you can block it.</span></span> <span data-ttu-id="67ef8-112">Dieser Vorgang verhindert, dass er auf Computern in Ihrer Organisation gelesen, geschrieben oder ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="67ef8-112">This operation will prevent it from being read, written, or executed on machines in your organization.</span></span>

<span data-ttu-id="67ef8-113">Es gibt zwei Möglichkeiten zum Erstellen von Indikatoren für Dateien:</span><span class="sxs-lookup"><span data-stu-id="67ef8-113">There are two ways you can create indicators for files:</span></span>
- <span data-ttu-id="67ef8-114">Durch Erstellen eines Indikators über die Einstellungsseite</span><span class="sxs-lookup"><span data-stu-id="67ef8-114">By creating an indicator through the settings page</span></span>
- <span data-ttu-id="67ef8-115">Durch Erstellen eines kontextbezogenen Indikators mithilfe der Schaltfläche "Indikator hinzufügen" auf der Seite "Dateidetails"</span><span class="sxs-lookup"><span data-stu-id="67ef8-115">By creating a contextual indicator using the add indicator button from the file details page</span></span>

### <a name="before-you-begin"></a><span data-ttu-id="67ef8-116">Bevor Sie beginnen</span><span class="sxs-lookup"><span data-stu-id="67ef8-116">Before you begin</span></span>
<span data-ttu-id="67ef8-117">Es ist wichtig, die folgenden Voraussetzungen zu kennen, bevor Sie Indikatoren für Dateien erstellen:</span><span class="sxs-lookup"><span data-stu-id="67ef8-117">It's important to understand the following prerequisites prior to creating indicators for files:</span></span>

- <span data-ttu-id="67ef8-118">Dieses Feature ist verfügbar, wenn Ihre Organisation Windows Defender Antivirus und cloudbasierter Schutz aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="67ef8-118">This feature is available if your organization uses Windows Defender Antivirus and Cloud-based protection is enabled.</span></span> <span data-ttu-id="67ef8-119">Weitere Informationen finden Sie unter [Use next-generation technologies in Microsoft Defender Antivirus through cloud-delivered protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/utilize-microsoft-cloud-protection-microsoft-defender-antivirus).</span><span class="sxs-lookup"><span data-stu-id="67ef8-119">For more information, see [Use next-generation technologies in Microsoft Defender Antivirus through cloud-delivered protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/utilize-microsoft-cloud-protection-microsoft-defender-antivirus).</span></span>
- <span data-ttu-id="67ef8-120">Die Antischalwareclientversion muss 4.18.1901.x oder höher sein.</span><span class="sxs-lookup"><span data-stu-id="67ef8-120">The Antimalware client version must be 4.18.1901.x or later.</span></span>
- <span data-ttu-id="67ef8-121">Unterstützt auf Computern unter Windows 10, Version 1703 oder höher, Windows Server 2016 und 2019.</span><span class="sxs-lookup"><span data-stu-id="67ef8-121">Supported on machines on Windows 10, version 1703 or later, Windows server 2016 and 2019.</span></span>
- <span data-ttu-id="67ef8-122">Um mit dem Blockieren von Dateien zu beginnen, müssen Sie zunächst das [ **Feature Blockieren**](advanced-features.md) oder Zulassen unter Einstellungen aktivieren.</span><span class="sxs-lookup"><span data-stu-id="67ef8-122">To start blocking files, you first need to [turn the **Block or allow** feature on](advanced-features.md) in Settings.</span></span>
- <span data-ttu-id="67ef8-123">Dieses Feature soll verhindern, dass mutmaßliche Schadsoftware (oder potenziell schädliche Dateien) aus dem Web heruntergeladen werden.</span><span class="sxs-lookup"><span data-stu-id="67ef8-123">This feature is designed to prevent suspected malware (or potentially malicious files) from being downloaded from the web.</span></span> <span data-ttu-id="67ef8-124">Es unterstützt zurzeit portable ausführbare (PE)-Dateien, einschließlich _EXE-_ und _DLL-Dateien._</span><span class="sxs-lookup"><span data-stu-id="67ef8-124">It currently supports portable executable (PE) files, including _.exe_ and _.dll_ files.</span></span> <span data-ttu-id="67ef8-125">Die Abdeckung wird im Laufe der Zeit erweitert.</span><span class="sxs-lookup"><span data-stu-id="67ef8-125">The coverage will be extended over time.</span></span>

<span data-ttu-id="67ef8-126">Die Leistung kann beeinträchtigt werden, wenn Sie große Dateien aus einer Netzwerkfreigabe auf Ihr lokales Gerät kopieren, insbesondere über eine VPN-Verbindung.</span><span class="sxs-lookup"><span data-stu-id="67ef8-126">Performance can be affected if you are copying large files from a network share onto your local device, especially over a VPN connection.</span></span> 

> [!IMPORTANT]
> - <span data-ttu-id="67ef8-127">Die Funktion "Zulassen" oder "Blockieren" kann nicht für Dateien durchgeführt werden, wenn die Dateiklassifizierung im Cache des Geräts vor der Aktion "Zulassen" oder "Blockieren" vorhanden ist</span><span class="sxs-lookup"><span data-stu-id="67ef8-127">The allow or block function cannot be done on files if the file's classification exists on the device's cache prior to the allow or block action</span></span> 
> - <span data-ttu-id="67ef8-128">Vertrauenswürdige signierte Dateien werden unterschiedlich behandelt.</span><span class="sxs-lookup"><span data-stu-id="67ef8-128">Trusted signed files will be treated differently.</span></span> <span data-ttu-id="67ef8-129">Defender for Endpoint ist für die Verarbeitung schädlicher Dateien optimiert.</span><span class="sxs-lookup"><span data-stu-id="67ef8-129">Defender for Endpoint is optimized to handle malicious files.</span></span> <span data-ttu-id="67ef8-130">Der Versuch, vertrauenswürdige signierte Dateien zu blockieren, kann in einigen Fällen Auswirkungen auf die Leistung haben.</span><span class="sxs-lookup"><span data-stu-id="67ef8-130">Trying to block trusted signed files, in some cases, may have performance implications.</span></span>
> - <span data-ttu-id="67ef8-131">In der Regel werden Dateiblöcke innerhalb weniger Minuten erzwungen, können jedoch bis zu 30 Minuten dauern.</span><span class="sxs-lookup"><span data-stu-id="67ef8-131">Typically, file blocks are enforced within a couple of minutes, but can take upwards of 30 minutes.</span></span>
> - <span data-ttu-id="67ef8-132">Wenn Richtlinien für Dateiindikator in Konflikt stehen, wird die Erzwingungsrichtlinie der sichereren Richtlinie angewendet.</span><span class="sxs-lookup"><span data-stu-id="67ef8-132">If there are conflicting file indicator policies, the enforcement policy of the more secure policy is applied.</span></span> <span data-ttu-id="67ef8-133">Beispielsweise hat eine SHA-256-Dateihashindikatorrichtlinie Vorrang vor einer MD5-Dateihashindikatorrichtlinie, wenn beide Hashtypen dieselbe Datei definieren.</span><span class="sxs-lookup"><span data-stu-id="67ef8-133">For example, a SHA-256 file hash indicator policy takes precedence over an MD5 file hash indicator policy if both hash types define the same file.</span></span>

### <a name="create-an-indicator-for-files-from-the-settings-page"></a><span data-ttu-id="67ef8-134">Erstellen eines Indikators für Dateien auf der Einstellungsseite</span><span class="sxs-lookup"><span data-stu-id="67ef8-134">Create an indicator for files from the settings page</span></span>

1. <span data-ttu-id="67ef8-135">Wählen Sie im Navigationsbereich **Einstellungsindikatoren**  >  **aus.**</span><span class="sxs-lookup"><span data-stu-id="67ef8-135">In the navigation pane, select **Settings** > **Indicators**.</span></span>  

2. <span data-ttu-id="67ef8-136">Wählen Sie die **Registerkarte Dateihash** aus.</span><span class="sxs-lookup"><span data-stu-id="67ef8-136">Select the **File hash** tab.</span></span>

3. <span data-ttu-id="67ef8-137">Wählen **Sie Indikator hinzufügen aus.**</span><span class="sxs-lookup"><span data-stu-id="67ef8-137">Select **Add indicator**.</span></span>

4. <span data-ttu-id="67ef8-138">Geben Sie die folgenden Details an:</span><span class="sxs-lookup"><span data-stu-id="67ef8-138">Specify the following details:</span></span>
   - <span data-ttu-id="67ef8-139">Indikator – Geben Sie die Entitätsdetails an, und definieren Sie den Ablauf des Indikators.</span><span class="sxs-lookup"><span data-stu-id="67ef8-139">Indicator - Specify the entity details and define the expiration of the indicator.</span></span>
   - <span data-ttu-id="67ef8-140">Aktion – Geben Sie die zu ergreifende Aktion an, und geben Sie eine Beschreibung an.</span><span class="sxs-lookup"><span data-stu-id="67ef8-140">Action - Specify the action to be taken and provide a description.</span></span>
   - <span data-ttu-id="67ef8-141">Bereich : Definieren Sie den Bereich der Computergruppe.</span><span class="sxs-lookup"><span data-stu-id="67ef8-141">Scope - Define the scope of the machine group.</span></span>

5. <span data-ttu-id="67ef8-142">Überprüfen Sie die Details auf der Registerkarte Zusammenfassung, und klicken Sie dann auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="67ef8-142">Review the details in the Summary tab, then click **Save**.</span></span>

### <a name="create-a-contextual-indicator-from-the-file-details-page"></a><span data-ttu-id="67ef8-143">Erstellen eines Kontextindikators auf der Seite mit den Dateidetails</span><span class="sxs-lookup"><span data-stu-id="67ef8-143">Create a contextual indicator from the file details page</span></span>
<span data-ttu-id="67ef8-144">Eine der Optionen beim Ausführen von [Reaktionsaktionen für eine](respond-file-alerts.md) Datei ist das Hinzufügen eines Indikators für die Datei.</span><span class="sxs-lookup"><span data-stu-id="67ef8-144">One of the options when taking [response actions on a file](respond-file-alerts.md) is adding an indicator for the file.</span></span> 

<span data-ttu-id="67ef8-145">Wenn Sie einen Indikatorhash für eine Datei hinzufügen, können Sie eine Warnung ausgelöst und die Datei blockieren, wenn ein Computer in Ihrer Organisation versucht, sie zu ausführen.</span><span class="sxs-lookup"><span data-stu-id="67ef8-145">When you add an indicator hash for a file, you can choose to raise an alert and block the file whenever a machine in your organization attempts to run it.</span></span>

<span data-ttu-id="67ef8-146">Dateien, die automatisch von einem Indikator blockiert werden, werden nicht im Aktionscenter der Datei angezeigt, aber die Warnungen werden weiterhin in der Warnungswarteschlange angezeigt.</span><span class="sxs-lookup"><span data-stu-id="67ef8-146">Files automatically blocked by an indicator won't show up in the file's Action center, but the alerts will still be visible in the Alerts queue.</span></span>


## <a name="related-topics"></a><span data-ttu-id="67ef8-147">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="67ef8-147">Related topics</span></span>
- [<span data-ttu-id="67ef8-148">Erstellen von Indikatoren</span><span class="sxs-lookup"><span data-stu-id="67ef8-148">Create indicators</span></span>](manage-indicators.md)
- [<span data-ttu-id="67ef8-149">Erstellen von Indikatoren für IPs und URLs/Domänen</span><span class="sxs-lookup"><span data-stu-id="67ef8-149">Create indicators for IPs and URLs/domains</span></span>](indicator-ip-domain.md)
- [<span data-ttu-id="67ef8-150">Erstellen von Indikatoren basierend auf Zertifikaten</span><span class="sxs-lookup"><span data-stu-id="67ef8-150">Create indicators based on certificates</span></span>](indicator-certificates.md)
- [<span data-ttu-id="67ef8-151">Verwalten von Indikatoren</span><span class="sxs-lookup"><span data-stu-id="67ef8-151">Manage indicators</span></span>](indicator-manage.md)
