---
title: Geben Sie die in der Cloud zugestellte Schutzstufe für Microsoft Defender Antivirus
description: Legen Sie Ihren Grad an Cloud-zugestellten Schutz für Microsoft Defender Antivirus.
keywords: Microsoft Defender Antivirus, Antischalware, Sicherheit, Verteidiger, Cloud, Aggressivität, Schutzstufe
search.product: eADQiWindows 10XVcnh
ms.pagetype: security
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.date: 10/26/2020
ms.reviewer: ''
manager: dansimp
ms.custom: nextgen
ms.technology: mde
ms.topic: article
ms.openlocfilehash: f441b1bd444cd70fb5b00dfcb5ebcddadf62b220
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2021
ms.locfileid: "52274904"
---
# <a name="specify-the-cloud-delivered-protection-level"></a><span data-ttu-id="a9bb6-104">Stufe des über die Cloud bereitgestellten Schutzes festlegen</span><span class="sxs-lookup"><span data-stu-id="a9bb6-104">Specify the cloud-delivered protection level</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="a9bb6-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="a9bb6-105">**Applies to:**</span></span>

- [<span data-ttu-id="a9bb6-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="a9bb6-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="a9bb6-107">Sie können Ihre Von der Cloud übermittelte Schutzstufe angeben, die von Microsoft Defender Antivirus mithilfe von Microsoft Endpoint Manager (empfohlen) oder Gruppenrichtlinien angeboten wird.</span><span class="sxs-lookup"><span data-stu-id="a9bb6-107">You can specify your level of cloud-delivered protection offered by Microsoft Defender Antivirus by using Microsoft Endpoint Manager (recommended) or Group Policy.</span></span>

> [!TIP]
> <span data-ttu-id="a9bb6-108">Cloudschutz ist nicht nur Schutz für Dateien, die in der Cloud gespeichert sind.</span><span class="sxs-lookup"><span data-stu-id="a9bb6-108">Cloud protection is not simply protection for files that are stored in the cloud.</span></span> <span data-ttu-id="a9bb6-109">Der Microsoft Defender Antivirus cloud service ist ein Mechanismus zum Bereitstellen aktualisierten Schutzes für Ihr Netzwerk und Ihre Geräte (auch Endpunkte genannt).</span><span class="sxs-lookup"><span data-stu-id="a9bb6-109">The Microsoft Defender Antivirus cloud service is a mechanism for delivering updated protection to your network and devices (also called endpoints).</span></span> <span data-ttu-id="a9bb6-110">Cloud protection with Microsoft Defender Antivirus uses distributed resources and machine learning to deliver protection to your endpoints at a rate that is far faster than traditional security intelligence updates.</span><span class="sxs-lookup"><span data-stu-id="a9bb6-110">Cloud protection with Microsoft Defender Antivirus uses distributed resources and machine learning to deliver protection to your endpoints at a rate that is far faster than traditional security intelligence updates.</span></span> <span data-ttu-id="a9bb6-111">Microsoft Intune und Microsoft Endpoint Manager sind jetzt Teil von [Microsoft Endpoint Manager](/mem/endpoint-manager-overview).</span><span class="sxs-lookup"><span data-stu-id="a9bb6-111">Microsoft Intune and Microsoft Endpoint Manager are now part of [Microsoft Endpoint Manager](/mem/endpoint-manager-overview).</span></span> 


## <a name="use-microsoft-endpoint-manager-to-specify-the-level-of-cloud-delivered-protection"></a><span data-ttu-id="a9bb6-112">Verwenden Microsoft Endpoint Manager, um die Ebene des in der Cloud zugestellten Schutzes anzugeben</span><span class="sxs-lookup"><span data-stu-id="a9bb6-112">Use Microsoft Endpoint Manager to specify the level of cloud-delivered protection</span></span>

1. <span data-ttu-id="a9bb6-113">Wechseln Sie zum Microsoft Endpoint Manager Admin Center ( [https://endpoint.microsoft.com](https://endpoint.microsoft.com) ) und melden Sie sich an.</span><span class="sxs-lookup"><span data-stu-id="a9bb6-113">Go to the Microsoft Endpoint Manager admin center ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)) and sign in.</span></span>

2. <span data-ttu-id="a9bb6-114">Wählen **Sie Endpoint security**  >  **Antivirus** aus.</span><span class="sxs-lookup"><span data-stu-id="a9bb6-114">Choose **Endpoint security** > **Antivirus**.</span></span>

3. <span data-ttu-id="a9bb6-115">Wählen Sie ein Antivirusprofil aus.</span><span class="sxs-lookup"><span data-stu-id="a9bb6-115">Select an antivirus profile.</span></span> <span data-ttu-id="a9bb6-116">(Wenn Sie noch kein Profil haben oder ein neues Profil erstellen möchten, lesen Sie Konfigurieren von Geräteeinschränkungseinstellungen [in Microsoft Intune](/intune/device-restrictions-configure).</span><span class="sxs-lookup"><span data-stu-id="a9bb6-116">(If you don't have one yet, or if you want to create a new profile, see [Configure device restriction settings in Microsoft Intune](/intune/device-restrictions-configure).</span></span>

4. <span data-ttu-id="a9bb6-117">Wählen Sie **Eigenschaften** aus.</span><span class="sxs-lookup"><span data-stu-id="a9bb6-117">Select **Properties**.</span></span> <span data-ttu-id="a9bb6-118">Wählen Sie dann neben **Konfigurationseinstellungen** bearbeiten **aus.**</span><span class="sxs-lookup"><span data-stu-id="a9bb6-118">Then, next to **Configuration settings**, choose **Edit**.</span></span>

5. <span data-ttu-id="a9bb6-119">Erweitern **Sie den** Cloudschutz, und wählen Sie dann in der Liste der von der Cloud übermittelten **Schutzebenen** eine der folgenden Optionen aus:</span><span class="sxs-lookup"><span data-stu-id="a9bb6-119">Expand **Cloud protection**, and then in the **Cloud-delivered protection level** list, select one of the following:</span></span>

    1. <span data-ttu-id="a9bb6-120">**High**: Wendet eine starke Erkennungsstufe an.</span><span class="sxs-lookup"><span data-stu-id="a9bb6-120">**High**: Applies a strong level of detection.</span></span>
    2. <span data-ttu-id="a9bb6-121">**High plus**: Verwendet die **High-Ebene** und wendet zusätzliche Schutzmaßnahmen an (kann sich auf die Clientleistung auswirken).</span><span class="sxs-lookup"><span data-stu-id="a9bb6-121">**High plus**: Uses the **High** level and applies additional protection measures (may impact client performance).</span></span>
    3. <span data-ttu-id="a9bb6-122">**Nulltoleranz**: Blockiert alle unbekannten ausführbaren Dateien.</span><span class="sxs-lookup"><span data-stu-id="a9bb6-122">**Zero tolerance**: Blocks all unknown executables.</span></span>

6. <span data-ttu-id="a9bb6-123">Wählen **Sie Überprüfen + Speichern** aus, und wählen Sie dann Speichern **aus.**</span><span class="sxs-lookup"><span data-stu-id="a9bb6-123">Choose **Review + save**, and then choose **Save**.</span></span> 

> [!TIP]
> <span data-ttu-id="a9bb6-124">Benötigen Sie Hilfe?</span><span class="sxs-lookup"><span data-stu-id="a9bb6-124">Need some help?</span></span> <span data-ttu-id="a9bb6-125">Informationen finden Sie in den folgenden Ressourcen:</span><span class="sxs-lookup"><span data-stu-id="a9bb6-125">See the following resources:</span></span>
> - [<span data-ttu-id="a9bb6-126">Konfigurieren Endpoint Protection</span><span class="sxs-lookup"><span data-stu-id="a9bb6-126">Configure Endpoint Protection</span></span>](/mem/configmgr/protect/deploy-use/endpoint-protection-configure)
> - [<span data-ttu-id="a9bb6-127">Hinzufügen von Endpunktschutzeinstellungen in Intune</span><span class="sxs-lookup"><span data-stu-id="a9bb6-127">Add endpoint protection settings in Intune</span></span>](/mem/intune/protect/endpoint-protection-configure)
  

## <a name="use-group-policy-to-specify-the-level-of-cloud-delivered-protection"></a><span data-ttu-id="a9bb6-128">Verwenden von Gruppenrichtlinien zum Angeben der Ebene des in der Cloud übermittelten Schutzes</span><span class="sxs-lookup"><span data-stu-id="a9bb6-128">Use Group Policy to specify the level of cloud-delivered protection</span></span>

1.  <span data-ttu-id="a9bb6-129">Öffnen Sie auf dem Computer für die Gruppenrichtlinienverwaltung die [Gruppenrichtlinienverwaltungskonsole](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)).</span><span class="sxs-lookup"><span data-stu-id="a9bb6-129">On your Group Policy management machine, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)).</span></span>

2. <span data-ttu-id="a9bb6-130">Klicken Sie mit der rechten Maustaste auf das Gruppenrichtlinienobjekt, das Sie konfigurieren möchten, und klicken Sie dann auf **Bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="a9bb6-130">Right-click the Group Policy Object you want to configure, and then click **Edit**.</span></span>

3.  <span data-ttu-id="a9bb6-131">Wechseln Sie **im Gruppenrichtlinienverwaltungs-Editor** zu **Computerkonfiguration**  >  **Administrative Vorlagen**.</span><span class="sxs-lookup"><span data-stu-id="a9bb6-131">In the **Group Policy Management Editor** go to **Computer Configuration** > **Administrative templates**.</span></span>

4.  <span data-ttu-id="a9bb6-132">Erweitern Sie die **Struktur, Windows Komponenten**  >  **Microsoft Defender Antivirus**  >  **MpEngine .**</span><span class="sxs-lookup"><span data-stu-id="a9bb6-132">Expand the tree to **Windows Components** > **Microsoft Defender Antivirus** > **MpEngine**.</span></span>

5.  <span data-ttu-id="a9bb6-133">Doppelklicken Sie auf **die Einstellung Cloudschutzstufe auswählen,** und legen Sie sie auf **Aktiviert .**</span><span class="sxs-lookup"><span data-stu-id="a9bb6-133">Double-click the **Select cloud protection level** setting and set it to **Enabled**.</span></span> <span data-ttu-id="a9bb6-134">Wählen Sie die Schutzebene aus:</span><span class="sxs-lookup"><span data-stu-id="a9bb6-134">Select the level of protection:</span></span>
    - <span data-ttu-id="a9bb6-135">**Die Standardblockierstufe** bietet eine starke Erkennung, ohne das Risiko zu erhöhen, legitime Dateien zu erkennen.</span><span class="sxs-lookup"><span data-stu-id="a9bb6-135">**Default blocking level** provides strong detection without increasing the risk of detecting legitimate files.</span></span>
    - <span data-ttu-id="a9bb6-136">**Moderate Sperrstufe bietet** nur moderate Unterstützung für Erkennungen mit hoher Vertrauenssicherheit</span><span class="sxs-lookup"><span data-stu-id="a9bb6-136">**Moderate blocking level** provides moderate only for high confidence detections</span></span>
    - <span data-ttu-id="a9bb6-137">**Bei hoher Blockierungsebene** wird eine starke Erkennungsebene angewendet, während die Clientleistung optimiert wird (sie kann ihnen jedoch auch eine höhere Wahrscheinlichkeit von falsch positiven Ergebnisse bieten).</span><span class="sxs-lookup"><span data-stu-id="a9bb6-137">**High blocking level** applies a strong level of detection while optimizing client performance (but can also give you a greater chance of false positives).</span></span>
    - <span data-ttu-id="a9bb6-138">**Hohe + Blockierungsstufe** wendet zusätzliche Schutzmaßnahmen an (kann sich auf die Clientleistung auswirken und die Wahrscheinlichkeit falsch positiver Ergebnisse erhöhen).</span><span class="sxs-lookup"><span data-stu-id="a9bb6-138">**High + blocking level** applies additional protection measures (might impact client performance and increase your chance of false positives).</span></span>
    - <span data-ttu-id="a9bb6-139">**Die Sperrstufe "Nulltoleranz"** blockiert alle unbekannten ausführbaren Dateien.</span><span class="sxs-lookup"><span data-stu-id="a9bb6-139">**Zero tolerance blocking level** blocks all unknown executables.</span></span>
    
    > [!WARNING]
    > <span data-ttu-id="a9bb6-140">Obwohl es unwahrscheinlich ist, kann das Festlegen dieser Option auf **Hoch** oder **Hoch +** dazu führen, dass einige legitime Dateien erkannt werden (obwohl Sie die Blockierung aufheben oder diese Erkennung in Frage stellen können).</span><span class="sxs-lookup"><span data-stu-id="a9bb6-140">While unlikely, setting this switch to **High** or **High +** may cause some legitimate files to be detected (although you will have the option to unblock or dispute that detection).</span></span>

6. <span data-ttu-id="a9bb6-141">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="a9bb6-141">Click **OK**.</span></span>

7. <span data-ttu-id="a9bb6-142">Stellen Sie ihr aktualisiertes Gruppenrichtlinienobjekt zur Bereitstellung.</span><span class="sxs-lookup"><span data-stu-id="a9bb6-142">Deploy your updated Group Policy Object.</span></span> <span data-ttu-id="a9bb6-143">Siehe [Gruppenrichtlinienverwaltungskonsole](/windows/win32/srvnodes/group-policy)</span><span class="sxs-lookup"><span data-stu-id="a9bb6-143">See [Group Policy Management Console](/windows/win32/srvnodes/group-policy)</span></span>

> [!TIP]
> <span data-ttu-id="a9bb6-144">Verwenden Sie Gruppenrichtlinienobjekte lokal?</span><span class="sxs-lookup"><span data-stu-id="a9bb6-144">Are you using Group Policy Objects on premises?</span></span> <span data-ttu-id="a9bb6-145">Sehen Sie, wie sie in der Cloud übersetzen.</span><span class="sxs-lookup"><span data-stu-id="a9bb6-145">See how they translate in the cloud.</span></span> <span data-ttu-id="a9bb6-146">[Analysieren Sie Ihre lokalen Gruppenrichtlinienobjekte mithilfe der Gruppenrichtlinienanalyse in Microsoft Endpoint Manager – Vorschau](/mem/intune/configuration/group-policy-analytics).</span><span class="sxs-lookup"><span data-stu-id="a9bb6-146">[Analyze your on-premises group policy objects using Group Policy analytics in Microsoft Endpoint Manager - Preview](/mem/intune/configuration/group-policy-analytics).</span></span> 
  
## <a name="related-articles"></a><span data-ttu-id="a9bb6-147">Verwandte Artikel</span><span class="sxs-lookup"><span data-stu-id="a9bb6-147">Related articles</span></span>

- [<span data-ttu-id="a9bb6-148">Microsoft Defender Antivirus in Windows 10</span><span class="sxs-lookup"><span data-stu-id="a9bb6-148">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)
- [<span data-ttu-id="a9bb6-149">Aus der Cloud bereitgestellten Schutz aktivieren</span><span class="sxs-lookup"><span data-stu-id="a9bb6-149">Enable cloud-delivered protection</span></span>](enable-cloud-protection-microsoft-defender-antivirus.md)
- [<span data-ttu-id="a9bb6-150">Erstellen und Bereitstellen von Antischalwarerichtlinien: Cloudschutzdienst</span><span class="sxs-lookup"><span data-stu-id="a9bb6-150">How to create and deploy antimalware policies: Cloud-protection service</span></span>](/configmgr/protect/deploy-use/endpoint-antimalware-policies#cloud-protection-service)