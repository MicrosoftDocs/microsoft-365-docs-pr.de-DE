---
title: Überprüfen von Warnungen in Microsoft Defender für Endpunkt
description: Überprüfen Sie warnungsinformationen, einschließlich einer visualisierten Warnung und Details für jeden Schritt der Kette.
keywords: Vorfall, Vorfälle, Computer, Geräte, Benutzer, Warnungen, Warnung, Untersuchung, Diagramm, Nachweise
ms.prod: m365-security
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: daniha
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.date: 5/1/2020
ms.technology: mde
ms.openlocfilehash: b17af7931b181a5fa30271a3eee07c7abf10a010
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2021
ms.locfileid: "52844022"
---
# <a name="review-alerts-in-microsoft-defender-for-endpoint"></a><span data-ttu-id="4decb-104">Überprüfen von Warnungen in Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="4decb-104">Review alerts in Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="4decb-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="4decb-105">**Applies to:**</span></span>
- [<span data-ttu-id="4decb-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="4decb-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)

><span data-ttu-id="4decb-107">Möchten Sie Defender für Endpunkt erleben?</span><span class="sxs-lookup"><span data-stu-id="4decb-107">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="4decb-108">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="4decb-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-managealerts-abovefoldlink)

<span data-ttu-id="4decb-109">Die Warnungsseite in Microsoft Defender für Endpunkt bietet den vollständigen Kontext der Warnung, indem Angriffssignale und Warnungen im Zusammenhang mit der ausgewählten Warnung kombiniert werden, um eine detaillierte Warnung zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="4decb-109">The alert page in Microsoft Defender for Endpoint provides full context to the alert, by combining attack signals and alerts related to the selected alert, to construct a detailed alert story.</span></span>

<span data-ttu-id="4decb-110">Schnelles Selektieren, Untersuchen und Ergreifen effektiver Maßnahmen bei Warnungen, die Sich auf Ihre Organisation auswirken.</span><span class="sxs-lookup"><span data-stu-id="4decb-110">Quickly triage, investigate, and take effective action on alerts that affect your organization.</span></span> <span data-ttu-id="4decb-111">Verstehen Sie, warum sie ausgelöst wurden, und ihre Auswirkungen von einem Ort aus.</span><span class="sxs-lookup"><span data-stu-id="4decb-111">Understand why they were triggered, and their impact from one location.</span></span> <span data-ttu-id="4decb-112">Weitere Informationen finden Sie in dieser Übersicht.</span><span class="sxs-lookup"><span data-stu-id="4decb-112">Learn more in this overview.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4yiO5]

## <a name="getting-started-with-an-alert"></a><span data-ttu-id="4decb-113">Erste Schritte mit einer Warnung</span><span class="sxs-lookup"><span data-stu-id="4decb-113">Getting started with an alert</span></span>

<span data-ttu-id="4decb-114">Wenn Sie den Namen einer Warnung in Defender für Endpunkt auswählen, gelangen Sie auf der Warnungsseite.</span><span class="sxs-lookup"><span data-stu-id="4decb-114">Selecting an alert's name in Defender for Endpoint will land you on its alert page.</span></span> <span data-ttu-id="4decb-115">Auf der Warnungsseite werden alle Informationen im Kontext der ausgewählten Warnung angezeigt.</span><span class="sxs-lookup"><span data-stu-id="4decb-115">On the alert page, all the information will be shown in context of the selected alert.</span></span> <span data-ttu-id="4decb-116">Jede Warnungsseite besteht aus vier Abschnitten:</span><span class="sxs-lookup"><span data-stu-id="4decb-116">Each alert page consists of 4 sections:</span></span>

1. <span data-ttu-id="4decb-117">**Der Titel** der Warnung zeigt den Namen der Warnung und ist vorhanden, um Sie daran zu erinnern, welche Warnung Ihre aktuelle Untersuchung gestartet hat, unabhängig davon, was Sie auf der Seite ausgewählt haben.</span><span class="sxs-lookup"><span data-stu-id="4decb-117">**The alert title** shows the alert's name and is there to remind you which alert started your current investigation regardless of what you have selected on the page.</span></span>
2. <span data-ttu-id="4decb-118">[**Betroffene Objekte**](#review-affected-assets) listet Karten von Geräten und Benutzern auf, die von dieser Warnung betroffen sind und auf die geklickt werden kann, um weitere Informationen und Aktionen zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="4decb-118">[**Affected assets**](#review-affected-assets) lists cards of devices and users affected by this alert that are clickable for further information and actions.</span></span>
3. <span data-ttu-id="4decb-119">Der **Warnungsabschnitt** zeigt alle Entitäten im Zusammenhang mit der Warnung an, die durch eine Strukturansicht miteinander verbunden sind.</span><span class="sxs-lookup"><span data-stu-id="4decb-119">The **alert story** displays all entities related to the alert, interconnected by a tree view.</span></span> <span data-ttu-id="4decb-120">Die Warnung im Titel steht im Fokus, wenn Sie zum ersten Mal auf der Seite der ausgewählten Warnung landen.</span><span class="sxs-lookup"><span data-stu-id="4decb-120">The alert in the title will be the one in focus when you first land on your selected alert's page.</span></span> <span data-ttu-id="4decb-121">Entitäten im Warnungsartikel können erweitert und angeklickt werden, um zusätzliche Informationen bereitzustellen und die Reaktion zu beschleunigen, indem Sie Aktionen direkt im Kontext der Warnungsseite ausführen können.</span><span class="sxs-lookup"><span data-stu-id="4decb-121">Entities in the alert story are expandable and clickable, to provide additional information and expedite response by allowing you to take actions right in the context of the alert page.</span></span> <span data-ttu-id="4decb-122">Verwenden Sie den Warnungsartikel, um Ihre Untersuchung zu starten.</span><span class="sxs-lookup"><span data-stu-id="4decb-122">Use the alert story to start your investigation.</span></span> <span data-ttu-id="4decb-123">Erfahren Sie, wie Sie [Warnungen in Microsoft Defender für Endpunkt untersuchen.](/microsoft-365/security/defender-endpoint/investigate-alerts)</span><span class="sxs-lookup"><span data-stu-id="4decb-123">Learn how in [Investigate alerts in Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint/investigate-alerts).</span></span>
4. <span data-ttu-id="4decb-124">Im **Detailbereich** werden zunächst die Details der ausgewählten Warnung mit Details und Aktionen im Zusammenhang mit dieser Warnung angezeigt.</span><span class="sxs-lookup"><span data-stu-id="4decb-124">The **details pane** will show the details of the selected alert at first, with details and actions related to this alert.</span></span> <span data-ttu-id="4decb-125">Wenn Sie eine der betroffenen Ressourcen oder Entitäten im Warnungsartikel auswählen, ändert sich der Detailbereich, um Kontextinformationen und Aktionen für das ausgewählte Objekt bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="4decb-125">If you select any of the affected assets or entities in the alert story, the details pane will change to provide contextual information and actions for the selected object.</span></span>

<span data-ttu-id="4decb-126">Notieren Sie sich den Erkennungsstatus für Ihre Warnung.</span><span class="sxs-lookup"><span data-stu-id="4decb-126">Note the detection status for your alert.</span></span> 
- <span data-ttu-id="4decb-127">Verhindert – Die versuchte verdächtige Aktion wurde vermieden.</span><span class="sxs-lookup"><span data-stu-id="4decb-127">Prevented – The attempted suspicious action was avoided.</span></span> <span data-ttu-id="4decb-128">Beispielsweise wurde eine Datei nicht auf den Datenträger geschrieben oder ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="4decb-128">For example, a file either wasn’t written to disk or executed.</span></span>
<span data-ttu-id="4decb-129">![Eine Warnungsseite, auf der die Bedrohung angezeigt wird, wurde verhindert](images/detstat-prevented.png)</span><span class="sxs-lookup"><span data-stu-id="4decb-129">![An alert page showing threat was prevented](images/detstat-prevented.png)</span></span>
- <span data-ttu-id="4decb-130">Blockiert – Verdächtiges Verhalten wurde ausgeführt und dann blockiert.</span><span class="sxs-lookup"><span data-stu-id="4decb-130">Blocked – Suspicious behavior was executed and then blocked.</span></span> <span data-ttu-id="4decb-131">Beispielsweise wurde ein Prozess ausgeführt, aber da er anschließend verdächtige Verhaltensweisen aufweist, wurde der Prozess beendet.</span><span class="sxs-lookup"><span data-stu-id="4decb-131">For example, a process was executed but because it subsequently exhibited suspicious behaviors, the process was terminated.</span></span>
<span data-ttu-id="4decb-132">![Eine Warnungsseite, auf der die Bedrohung angezeigt wird, wurde blockiert](images/detstat-blocked.png)</span><span class="sxs-lookup"><span data-stu-id="4decb-132">![An alert page showing threat was blocked](images/detstat-blocked.png)</span></span>
- <span data-ttu-id="4decb-133">Erkannt – Ein Angriff wurde erkannt und ist möglicherweise noch aktiv.</span><span class="sxs-lookup"><span data-stu-id="4decb-133">Detected – An attack was detected and is possibly still active.</span></span>
<span data-ttu-id="4decb-134">![Eine Warnungsseite, auf der die Bedrohung erkannt wurde](images/detstat-detected.png)</span><span class="sxs-lookup"><span data-stu-id="4decb-134">![An alert page showing threat was detected](images/detstat-detected.png)</span></span>




<span data-ttu-id="4decb-135">Sie können dann auch die Details der *automatischen Untersuchung* im Detailbereich Ihrer Warnung überprüfen, um zu sehen, welche Aktionen bereits ausgeführt wurden, sowie die Beschreibung der Warnung für empfohlene Aktionen lesen.</span><span class="sxs-lookup"><span data-stu-id="4decb-135">You can then also review the *automated investigation details* in your alert's details pane, to see which actions were already taken, as well as reading the alert's description for recommended actions.</span></span>

![Ein Codeausschnitt des Detailbereichs mit hervorgehobener Warnungsbeschreibung und automatischen Untersuchungsabschnitten](images/alert-air-and-alert-description.png)

<span data-ttu-id="4decb-137">Weitere Informationen, die im Detailbereich verfügbar sind, wenn die Warnung geöffnet wird, umfassen MITRE-Techniken, Quelle und zusätzliche kontextbezogene Details.</span><span class="sxs-lookup"><span data-stu-id="4decb-137">Other information available in the details pane when the alert opens includes MITRE techniques, source, and additional contextual details.</span></span>




## <a name="review-affected-assets"></a><span data-ttu-id="4decb-138">Überprüfen betroffener Ressourcen</span><span class="sxs-lookup"><span data-stu-id="4decb-138">Review affected assets</span></span>

<span data-ttu-id="4decb-139">Wenn Sie ein Gerät oder eine Benutzerkarte in den Abschnitten der betroffenen Objekte auswählen, wechseln Sie zu den Details des Geräts oder Benutzers im Detailbereich.</span><span class="sxs-lookup"><span data-stu-id="4decb-139">Selecting a device or a user card in the affected assets sections will switch to the details of the device or user in the details pane.</span></span>

- <span data-ttu-id="4decb-140">**Bei Geräten** werden im Detailbereich Informationen über das Gerät selbst angezeigt, z. B. Domäne, Betriebssystem und IP.</span><span class="sxs-lookup"><span data-stu-id="4decb-140">**For devices**, the details pane will display information about the device itself, like Domain, Operating System, and IP.</span></span> <span data-ttu-id="4decb-141">Aktive Warnungen und die angemeldeten Benutzer auf diesem Gerät sind ebenfalls verfügbar.</span><span class="sxs-lookup"><span data-stu-id="4decb-141">Active alerts and the logged on users on that device are also available.</span></span> <span data-ttu-id="4decb-142">Sie können sofortige Maßnahmen ergreifen, indem Sie das Gerät isolieren, die App-Ausführung einschränken oder eine Antivirenüberprüfung ausführen.</span><span class="sxs-lookup"><span data-stu-id="4decb-142">You can take immediate action by isolating the device, restricting app execution, or running an antivirus scan.</span></span> <span data-ttu-id="4decb-143">Alternativ können Sie ein Untersuchungspaket erfassen, eine automatisierte Untersuchung initiieren oder zur Geräteseite wechseln, um die Untersuchung aus der Sicht des Geräts durchzuführen.</span><span class="sxs-lookup"><span data-stu-id="4decb-143">Alternatively, you could collect an investigation package, initiate an automated investigation, or go to the device page to investigate from the device's point of view.</span></span>

   ![Ein Codeausschnitt des Detailbereichs, wenn ein Gerät ausgewählt wird](images/device-page-details.png)

- <span data-ttu-id="4decb-145">**Für Benutzer** werden im Detailbereich detaillierte Benutzerinformationen angezeigt, z. B. SAM-Name und SID des Benutzers sowie von diesem Benutzer ausgeführte Anmeldetypen sowie alle warnungen und Vorfälle im Zusammenhang damit.</span><span class="sxs-lookup"><span data-stu-id="4decb-145">**For users**, the details pane will display detailed user information, such as the user's SAM name and SID, as well as logon types performed by this user and any alerts and incidents related to it.</span></span> <span data-ttu-id="4decb-146">Sie können die *Seite "Benutzer öffnen"* auswählen, um die Untersuchung aus der Sicht dieses Benutzers fortzusetzen.</span><span class="sxs-lookup"><span data-stu-id="4decb-146">You can select *Open user page* to continue the investigation from that user's point of view.</span></span>

   ![Ein Codeausschnitt des Detailbereichs, wenn ein Benutzer ausgewählt wird](images/user-page-details.png)


## <a name="related-topics"></a><span data-ttu-id="4decb-148">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="4decb-148">Related topics</span></span>

- [<span data-ttu-id="4decb-149">Anzeigen und Organisieren der Vorfallwarteschlange</span><span class="sxs-lookup"><span data-stu-id="4decb-149">View and organize the incidents queue</span></span>](view-incidents-queue.md)
- [<span data-ttu-id="4decb-150">Untersuchen von Vorfällen</span><span class="sxs-lookup"><span data-stu-id="4decb-150">Investigate incidents</span></span>](investigate-incidents.md)
- [<span data-ttu-id="4decb-151">Verwalten von Vorfällen</span><span class="sxs-lookup"><span data-stu-id="4decb-151">Manage incidents</span></span>](manage-incidents.md)
