---
title: Angeben der über die Cloud bereitgestellten Schutzebene für Microsoft Defender Antivirus
description: Legen Sie die Ebene des über die Cloud bereitgestellten Schutzes für Microsoft Defender Antivirus fest.
keywords: Microsoft Defender Antivirus, Antischadsoftware, Sicherheit, Defender, Cloud, Aggressivität, Schutzebene
search.product: eADQiWindows 10XVcnh
ms.pagetype: security
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: normal
ms.topic: article
author: denisebmsft
ms.author: deniseb
ms.date: 10/26/2020
ms.reviewer: ''
manager: dansimp
ms.custom: nextgen
ms.technology: mde
ms.openlocfilehash: fb4dd3114c411385f1a38cf7b0fd391a1b159b99
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/14/2021
ms.locfileid: "52924471"
---
# <a name="specify-the-cloud-delivered-protection-level"></a><span data-ttu-id="02e9f-104">Stufe des über die Cloud bereitgestellten Schutzes festlegen</span><span class="sxs-lookup"><span data-stu-id="02e9f-104">Specify the cloud-delivered protection level</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="02e9f-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="02e9f-105">**Applies to:**</span></span>

- [<span data-ttu-id="02e9f-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="02e9f-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="02e9f-107">Mit Microsoft Endpoint Manager (empfohlen) oder Gruppenrichtlinien können Sie den von Microsoft Defender Antivirus bereitgestellten Schutz in der Cloud angeben.</span><span class="sxs-lookup"><span data-stu-id="02e9f-107">You can specify your level of cloud-delivered protection offered by Microsoft Defender Antivirus by using Microsoft Endpoint Manager (recommended) or Group Policy.</span></span>

> [!TIP]
> <span data-ttu-id="02e9f-108">Cloudschutz ist nicht nur Schutz für Dateien, die in der Cloud gespeichert sind.</span><span class="sxs-lookup"><span data-stu-id="02e9f-108">Cloud protection is not simply protection for files that are stored in the cloud.</span></span> <span data-ttu-id="02e9f-109">Der Microsoft Defender Antivirus Clouddienst ist ein Mechanismus zum Bereitstellen eines aktualisierten Schutzes für Ihr Netzwerk und Ihre Geräte (auch endpunkte genannt).</span><span class="sxs-lookup"><span data-stu-id="02e9f-109">The Microsoft Defender Antivirus cloud service is a mechanism for delivering updated protection to your network and devices (also called endpoints).</span></span> <span data-ttu-id="02e9f-110">Der Cloudschutz mit Microsoft Defender Antivirus verwendet verteilte Ressourcen und maschinelles Lernen, um Ihren Endpunkten einen Schutz zu bieten, der wesentlich schneller als herkömmliche Security Intelligence-Updates ist.</span><span class="sxs-lookup"><span data-stu-id="02e9f-110">Cloud protection with Microsoft Defender Antivirus uses distributed resources and machine learning to deliver protection to your endpoints at a rate that is far faster than traditional security intelligence updates.</span></span> <span data-ttu-id="02e9f-111">Microsoft Intune und Microsoft Endpoint Manager sind jetzt Teil von [Microsoft Endpoint Manager.](/mem/endpoint-manager-overview)</span><span class="sxs-lookup"><span data-stu-id="02e9f-111">Microsoft Intune and Microsoft Endpoint Manager are now part of [Microsoft Endpoint Manager](/mem/endpoint-manager-overview).</span></span> 


## <a name="use-microsoft-endpoint-manager-to-specify-the-level-of-cloud-delivered-protection"></a><span data-ttu-id="02e9f-112">Verwenden sie Microsoft Endpoint Manager, um die Ebene des über die Cloud bereitgestellten Schutzes anzugeben.</span><span class="sxs-lookup"><span data-stu-id="02e9f-112">Use Microsoft Endpoint Manager to specify the level of cloud-delivered protection</span></span>

1. <span data-ttu-id="02e9f-113">Wechseln Sie zum Microsoft Endpoint Manager Admin Center ( [https://endpoint.microsoft.com](https://endpoint.microsoft.com) ), und melden Sie sich an.</span><span class="sxs-lookup"><span data-stu-id="02e9f-113">Go to the Microsoft Endpoint Manager admin center ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)) and sign in.</span></span>

2. <span data-ttu-id="02e9f-114">Wählen Sie **Endpunktsicherheits-Antivirus**  >  aus.</span><span class="sxs-lookup"><span data-stu-id="02e9f-114">Choose **Endpoint security** > **Antivirus**.</span></span>

3. <span data-ttu-id="02e9f-115">Wählen Sie ein Antivirusprofil aus.</span><span class="sxs-lookup"><span data-stu-id="02e9f-115">Select an antivirus profile.</span></span> <span data-ttu-id="02e9f-116">(Wenn Sie noch kein Profil haben oder ein neues Profil erstellen möchten, lesen Sie die Informationen unter [Konfigurieren von Einstellungen für Geräteeinschränkungen in Microsoft Intune.](/intune/device-restrictions-configure)</span><span class="sxs-lookup"><span data-stu-id="02e9f-116">(If you don't have one yet, or if you want to create a new profile, see [Configure device restriction settings in Microsoft Intune](/intune/device-restrictions-configure).</span></span>

4. <span data-ttu-id="02e9f-117">Wählen Sie **Eigenschaften** aus.</span><span class="sxs-lookup"><span data-stu-id="02e9f-117">Select **Properties**.</span></span> <span data-ttu-id="02e9f-118">Wählen Sie dann neben den **Konfigurationseinstellungen** **"Bearbeiten"** aus.</span><span class="sxs-lookup"><span data-stu-id="02e9f-118">Then, next to **Configuration settings**, choose **Edit**.</span></span>

5. <span data-ttu-id="02e9f-119">Erweitern Sie den **Cloudschutz,** und wählen Sie dann in der Liste der über die **Cloud bereitgestellten Schutzebene** eine der folgenden Optionen aus:</span><span class="sxs-lookup"><span data-stu-id="02e9f-119">Expand **Cloud protection**, and then in the **Cloud-delivered protection level** list, select one of the following:</span></span>

    1. <span data-ttu-id="02e9f-120">**Hoch:** Wendet eine starke Erkennungsstufe an.</span><span class="sxs-lookup"><span data-stu-id="02e9f-120">**High**: Applies a strong level of detection.</span></span>
    2. <span data-ttu-id="02e9f-121">**Hoch plus:** Verwendet die **Stufe "High"** und wendet zusätzliche Schutzmaßnahmen an (kann sich auf die Clientleistung auswirken).</span><span class="sxs-lookup"><span data-stu-id="02e9f-121">**High plus**: Uses the **High** level and applies additional protection measures (may impact client performance).</span></span>
    3. <span data-ttu-id="02e9f-122">**Nulltoleranz:** Blockiert alle unbekannten ausführbaren Dateien.</span><span class="sxs-lookup"><span data-stu-id="02e9f-122">**Zero tolerance**: Blocks all unknown executables.</span></span>

6. <span data-ttu-id="02e9f-123">Wählen Sie **"Überprüfen" und "Speichern"** und dann **"Speichern"** aus.</span><span class="sxs-lookup"><span data-stu-id="02e9f-123">Choose **Review + save**, and then choose **Save**.</span></span> 

> [!TIP]
> <span data-ttu-id="02e9f-124">Benötigen Sie Hilfe?</span><span class="sxs-lookup"><span data-stu-id="02e9f-124">Need some help?</span></span> <span data-ttu-id="02e9f-125">Informationen finden Sie in den folgenden Ressourcen:</span><span class="sxs-lookup"><span data-stu-id="02e9f-125">See the following resources:</span></span>
> - [<span data-ttu-id="02e9f-126">Konfigurieren Endpoint Protection</span><span class="sxs-lookup"><span data-stu-id="02e9f-126">Configure Endpoint Protection</span></span>](/mem/configmgr/protect/deploy-use/endpoint-protection-configure)
> - [<span data-ttu-id="02e9f-127">Hinzufügen von Endpunktschutzeinstellungen in Intune</span><span class="sxs-lookup"><span data-stu-id="02e9f-127">Add endpoint protection settings in Intune</span></span>](/mem/intune/protect/endpoint-protection-configure)
  

## <a name="use-group-policy-to-specify-the-level-of-cloud-delivered-protection"></a><span data-ttu-id="02e9f-128">Verwenden von Gruppenrichtlinien zum Angeben der Ebene des über die Cloud bereitgestellten Schutzes</span><span class="sxs-lookup"><span data-stu-id="02e9f-128">Use Group Policy to specify the level of cloud-delivered protection</span></span>

1.  <span data-ttu-id="02e9f-129">Öffnen Sie auf dem Computer für die Gruppenrichtlinienverwaltung die [Gruppenrichtlinien-Verwaltungskonsole.](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))</span><span class="sxs-lookup"><span data-stu-id="02e9f-129">On your Group Policy management machine, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)).</span></span>

2. <span data-ttu-id="02e9f-130">Klicken Sie mit der rechten Maustaste auf das Gruppenrichtlinienobjekt, das Sie konfigurieren möchten, und klicken Sie dann auf **"Bearbeiten".**</span><span class="sxs-lookup"><span data-stu-id="02e9f-130">Right-click the Group Policy Object you want to configure, and then click **Edit**.</span></span>

3.  <span data-ttu-id="02e9f-131">Wechseln Sie im **Gruppenrichtlinienverwaltungs-Editor** zu administrativen Vorlagen für die **Computerkonfiguration.**  >  </span><span class="sxs-lookup"><span data-stu-id="02e9f-131">In the **Group Policy Management Editor** go to **Computer Configuration** > **Administrative templates**.</span></span>

4.  <span data-ttu-id="02e9f-132">Erweitern Sie die Struktur bis **Windows Komponenten**  >  **Microsoft Defender Antivirus**  >  **MpEngine**.</span><span class="sxs-lookup"><span data-stu-id="02e9f-132">Expand the tree to **Windows Components** > **Microsoft Defender Antivirus** > **MpEngine**.</span></span>

5.  <span data-ttu-id="02e9f-133">Doppelklicken Sie auf die Einstellung **"Cloudschutzebene auswählen",** und legen Sie sie auf **"Aktiviert"** fest.</span><span class="sxs-lookup"><span data-stu-id="02e9f-133">Double-click the **Select cloud protection level** setting and set it to **Enabled**.</span></span> <span data-ttu-id="02e9f-134">Wählen Sie die Schutzebene aus:</span><span class="sxs-lookup"><span data-stu-id="02e9f-134">Select the level of protection:</span></span>
    - <span data-ttu-id="02e9f-135">**Die Standardblockierungsstufe** bietet eine starke Erkennung, ohne das Risiko zu erhöhen, dass seriöse Dateien erkannt werden.</span><span class="sxs-lookup"><span data-stu-id="02e9f-135">**Default blocking level** provides strong detection without increasing the risk of detecting legitimate files.</span></span>
    - <span data-ttu-id="02e9f-136">**Moderate Blockierungsstufe** bietet nur für Erkennungen mit hoher Konfidenz moderat</span><span class="sxs-lookup"><span data-stu-id="02e9f-136">**Moderate blocking level** provides moderate only for high confidence detections</span></span>
    - <span data-ttu-id="02e9f-137">**Die hohe Blockierungsebene** wendet eine starke Erkennungsstufe bei gleichzeitiger Optimierung der Clientleistung an (kann aber auch eine höhere Wahrscheinlichkeit für falsch positive Ergebnisse bieten).</span><span class="sxs-lookup"><span data-stu-id="02e9f-137">**High blocking level** applies a strong level of detection while optimizing client performance (but can also give you a greater chance of false positives).</span></span>
    - <span data-ttu-id="02e9f-138">**Hohe + Blockierungsebene** wendet zusätzliche Schutzmaßnahmen an (kann sich auf die Clientleistung auswirken und Ihre Wahrscheinlichkeit falsch positiver Ergebnisse erhöhen).</span><span class="sxs-lookup"><span data-stu-id="02e9f-138">**High + blocking level** applies additional protection measures (might impact client performance and increase your chance of false positives).</span></span>
    - <span data-ttu-id="02e9f-139">**Die Blockierungsstufe Nulltoleranz** blockiert alle unbekannten ausführbaren Dateien.</span><span class="sxs-lookup"><span data-stu-id="02e9f-139">**Zero tolerance blocking level** blocks all unknown executables.</span></span>
    
    > [!WARNING]
    > <span data-ttu-id="02e9f-140">Obwohl dies unwahrscheinlich ist, kann das Festlegen dieses Schalters auf **"Hoch"** oder **"Hoch +"** dazu führen, dass einige legitime Dateien erkannt werden (obwohl Sie die Möglichkeit haben, diese Erkennung aufzuheben oder zu infrage zu stellen).</span><span class="sxs-lookup"><span data-stu-id="02e9f-140">While unlikely, setting this switch to **High** or **High +** may cause some legitimate files to be detected (although you will have the option to unblock or dispute that detection).</span></span>

6. <span data-ttu-id="02e9f-141">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="02e9f-141">Click **OK**.</span></span>

7. <span data-ttu-id="02e9f-142">Stellen Sie das aktualisierte Gruppenrichtlinienobjekt bereit.</span><span class="sxs-lookup"><span data-stu-id="02e9f-142">Deploy your updated Group Policy Object.</span></span> <span data-ttu-id="02e9f-143">Siehe [Gruppenrichtlinien-Verwaltungskonsole](/windows/win32/srvnodes/group-policy)</span><span class="sxs-lookup"><span data-stu-id="02e9f-143">See [Group Policy Management Console](/windows/win32/srvnodes/group-policy)</span></span>

> [!TIP]
> <span data-ttu-id="02e9f-144">Verwenden Sie gruppenrichtlinienobjekte lokal?</span><span class="sxs-lookup"><span data-stu-id="02e9f-144">Are you using Group Policy Objects on premises?</span></span> <span data-ttu-id="02e9f-145">Erfahren Sie, wie sie in der Cloud übersetzt werden.</span><span class="sxs-lookup"><span data-stu-id="02e9f-145">See how they translate in the cloud.</span></span> <span data-ttu-id="02e9f-146">[Analysieren Sie Ihre lokalen Gruppenrichtlinienobjekte mithilfe von Gruppenrichtlinienanalysen in Microsoft Endpoint Manager – Vorschau](/mem/intune/configuration/group-policy-analytics).</span><span class="sxs-lookup"><span data-stu-id="02e9f-146">[Analyze your on-premises group policy objects using Group Policy analytics in Microsoft Endpoint Manager - Preview](/mem/intune/configuration/group-policy-analytics).</span></span> 
  
## <a name="related-articles"></a><span data-ttu-id="02e9f-147">Verwandte Artikel</span><span class="sxs-lookup"><span data-stu-id="02e9f-147">Related articles</span></span>

- [<span data-ttu-id="02e9f-148">Microsoft Defender Antivirus in Windows 10</span><span class="sxs-lookup"><span data-stu-id="02e9f-148">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)
- [<span data-ttu-id="02e9f-149">Aus der Cloud bereitgestellten Schutz aktivieren</span><span class="sxs-lookup"><span data-stu-id="02e9f-149">Enable cloud-delivered protection</span></span>](enable-cloud-protection-microsoft-defender-antivirus.md)
- [<span data-ttu-id="02e9f-150">Erstellen und Bereitstellen von Antischadsoftwarerichtlinien: Cloud-Schutzdienst</span><span class="sxs-lookup"><span data-stu-id="02e9f-150">How to create and deploy antimalware policies: Cloud-protection service</span></span>](/configmgr/protect/deploy-use/endpoint-antimalware-policies#cloud-protection-service)