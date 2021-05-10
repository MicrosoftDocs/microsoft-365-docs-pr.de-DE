---
title: Angeben zusätzlicher Definitionssätze für die Netzwerkdatenverkehrsprüfung für Microsoft Defender Antivirus
description: Geben Sie zusätzliche Definitionssätze für die Netzwerkdatenverkehrsprüfung für Microsoft Defender Antivirus.
keywords: Microsoft Defender Antivirus, Antischalware, Sicherheit, Defender, Überprüfung des Netzwerkdatenverkehrs
search.product: eADQiWindows 10XVcnh
ms.pagetype: security
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.date: 05/07/2021
ms.reviewer: ''
manager: dansimp
ms.custom: nextgen
ms.technology: mde
ms.topic: article
ms.openlocfilehash: 82568df0a6ad2225fd31b4c0fa4a654710f1e98b
ms.sourcegitcommit: de5fce90de22ba588e75e1a1d2e87e03b9e25ec7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/10/2021
ms.locfileid: "52300195"
---
# <a name="specify-additional-definition-sets-for-network-traffic-inspection"></a><span data-ttu-id="4cd22-104">Angeben zusätzlicher Definitionssätze für die Überprüfung des Netzwerkdatenverkehrs</span><span class="sxs-lookup"><span data-stu-id="4cd22-104">Specify additional definition sets for network traffic inspection</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="4cd22-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="4cd22-105">**Applies to:**</span></span>

- [<span data-ttu-id="4cd22-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="4cd22-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="4cd22-107">Sie können zusätzliche Definitionssätze für die Überprüfung des Netzwerkdatenverkehrs mithilfe von Gruppenrichtlinien angeben.</span><span class="sxs-lookup"><span data-stu-id="4cd22-107">You can specify additional definition sets for network traffic inspection using Group Policy.</span></span>

## <a name="use-group-policy-to-specify-additional-definition-sets-for-network-traffic-inspection"></a><span data-ttu-id="4cd22-108">Verwenden von Gruppenrichtlinien zum Angeben zusätzlicher Definitionssätze für die Überprüfung des Netzwerkdatenverkehrs</span><span class="sxs-lookup"><span data-stu-id="4cd22-108">Use Group Policy to specify additional definition sets for network traffic inspection</span></span>

1. <span data-ttu-id="4cd22-109">Öffnen Sie auf dem Endpunkt für die Gruppenrichtlinienverwaltung die [Gruppenrichtlinienverwaltungskonsole](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)).</span><span class="sxs-lookup"><span data-stu-id="4cd22-109">On your Group Policy management endpoint, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)).</span></span>

2. <span data-ttu-id="4cd22-110">Wechseln Sie **zu Windows Komponenten**  >  **Microsoft Defender Antivirus**  >  **Netzwerkinspektionssystem**.</span><span class="sxs-lookup"><span data-stu-id="4cd22-110">Go to **Windows Components** > **Microsoft Defender Antivirus** > **Network Inspection System**.</span></span> 

3. <span data-ttu-id="4cd22-111">Wählen **Sie Zusätzliche Definitionssätze für die Überprüfung des Netzwerkdatenverkehrs angeben aus.**</span><span class="sxs-lookup"><span data-stu-id="4cd22-111">Select **Specify additional definition sets for network traffic inspection**.</span></span> <span data-ttu-id="4cd22-112">Standardmäßig ist diese Richtlinie auf **Nicht konfiguriert festgelegt.**</span><span class="sxs-lookup"><span data-stu-id="4cd22-112">By default, this policy is set to **Not configured**.</span></span> 

4. <span data-ttu-id="4cd22-113">Wählen Sie zum Bearbeiten der Richtlinie den **Link Richtlinieneinstellung** bearbeiten aus.</span><span class="sxs-lookup"><span data-stu-id="4cd22-113">To edit the policy, select the **edit policy setting** link.</span></span>

5. <span data-ttu-id="4cd22-114">Wählen **Sie Aktiviert** aus, und wählen Sie dann im Abschnitt **Optionen** die Option **Anzeigen...** aus.</span><span class="sxs-lookup"><span data-stu-id="4cd22-114">Select **Enabled**, and then in the **Options** section, select **Show...**.</span></span>

6. <span data-ttu-id="4cd22-115">Fügen Sie der Liste Einträge hinzu, und wählen Sie dann **OK aus.**</span><span class="sxs-lookup"><span data-stu-id="4cd22-115">Add entries to the list, and then select **OK**.</span></span> 

   <span data-ttu-id="4cd22-116">Jeder Eintrag muss als Name-Wert-Paar aufgeführt werden, wobei der Name eine Zeichenfolgendarstellung einer GUID für Definitionssatz ist.</span><span class="sxs-lookup"><span data-stu-id="4cd22-116">Each entry must be listed as a name-value pair, where the name is a string representation of a definition set GUID.</span></span> <span data-ttu-id="4cd22-117">Die GUID des Definitionssatz zum Aktivieren der Testsicherheitsintelligenz ist beispielsweise wie folgt definiert: `{b54b6ac9-a737-498e-9120-6616ad3bf590}` .</span><span class="sxs-lookup"><span data-stu-id="4cd22-117">As an example, the definition set GUID to enable test security intelligence is defined as: `{b54b6ac9-a737-498e-9120-6616ad3bf590}`.</span></span> <span data-ttu-id="4cd22-118">Der Wert wird nicht verwendet, daher wird empfohlen, ihn auf zu `0` setzen.</span><span class="sxs-lookup"><span data-stu-id="4cd22-118">The value is not used, so we recommend setting it to `0`.</span></span> 

7. <span data-ttu-id="4cd22-119">Wählen **Sie OK** aus, und stellen Sie dann das aktualisierte Gruppenrichtlinienobjekt aus.</span><span class="sxs-lookup"><span data-stu-id="4cd22-119">Select **OK**, and then deploy your updated Group Policy Object.</span></span> <span data-ttu-id="4cd22-120">Weitere [Informationen finden Sie unter Gruppenrichtlinienverwaltungskonsole](/windows/win32/srvnodes/group-policy).</span><span class="sxs-lookup"><span data-stu-id="4cd22-120">See [Group Policy Management Console](/windows/win32/srvnodes/group-policy).</span></span>

> [!TIP]
> <span data-ttu-id="4cd22-121">Verwenden Sie Gruppenrichtlinienobjekte lokal?</span><span class="sxs-lookup"><span data-stu-id="4cd22-121">Are you using Group Policy Objects on premises?</span></span> <span data-ttu-id="4cd22-122">Sehen Sie, wie sie in der Cloud übersetzen.</span><span class="sxs-lookup"><span data-stu-id="4cd22-122">See how they translate in the cloud.</span></span> <span data-ttu-id="4cd22-123">[Analysieren Sie Ihre lokalen Gruppenrichtlinienobjekte mithilfe der Gruppenrichtlinienanalyse in Microsoft Endpoint Manager – Vorschau](/mem/intune/configuration/group-policy-analytics).</span><span class="sxs-lookup"><span data-stu-id="4cd22-123">[Analyze your on-premises group policy objects using Group Policy analytics in Microsoft Endpoint Manager - Preview](/mem/intune/configuration/group-policy-analytics).</span></span> 
  
## <a name="related-articles"></a><span data-ttu-id="4cd22-124">Verwandte Artikel</span><span class="sxs-lookup"><span data-stu-id="4cd22-124">Related articles</span></span>

- [<span data-ttu-id="4cd22-125">Microsoft Defender Antivirus in Windows 10</span><span class="sxs-lookup"><span data-stu-id="4cd22-125">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)
 
- [<span data-ttu-id="4cd22-126">Aus der Cloud bereitgestellten Schutz aktivieren</span><span class="sxs-lookup"><span data-stu-id="4cd22-126">Enable cloud-delivered protection</span></span>](enable-cloud-protection-microsoft-defender-antivirus.md)

- [<span data-ttu-id="4cd22-127">Erstellen und Bereitstellen von Antischalwarerichtlinien: Cloudschutzdienst</span><span class="sxs-lookup"><span data-stu-id="4cd22-127">How to create and deploy antimalware policies: Cloud-protection service</span></span>](/configmgr/protect/deploy-use/endpoint-antimalware-policies#cloud-protection-service)