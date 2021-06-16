---
title: Beispiel für die erweiterte Suche für Microsoft Defender für Office 365
description: Erste Schritte bei der Suche nach E-Mail-Bedrohungen mithilfe der erweiterten Suche
keywords: Erweiterte Suche, Bedrohungssuche, Cyber-Bedrohungssuche, Microsoft 365 Defender, Microsoft 365, m365, Suche, Abfrage, Telemetrie, benutzerdefinierte Erkennungen, Schema, kusto
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: d3ac49b4afde0951e7a034c5c11114afbc52c293
ms.sourcegitcommit: 1c11035dd4432e34603022740baef0c8f7ff4425
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/16/2021
ms.locfileid: "52965144"
---
# <a name="advanced-hunting-example-for-microsoft-defender-for-office-365"></a><span data-ttu-id="db452-104">Beispiel für die erweiterte Suche für Microsoft Defender für Office 365</span><span class="sxs-lookup"><span data-stu-id="db452-104">Advanced hunting example for Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="db452-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="db452-105">**Applies to:**</span></span>
- <span data-ttu-id="db452-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="db452-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="db452-107">Möchten Sie mit der erweiterten Bedrohungssuche nach E-Mail-Bedrohungen beginnen?</span><span class="sxs-lookup"><span data-stu-id="db452-107">Want to get started searching for email threats using advanced hunting?</span></span> <span data-ttu-id="db452-108">Dann probieren Sie Folgendes aus:</span><span class="sxs-lookup"><span data-stu-id="db452-108">Try this:</span></span>

<span data-ttu-id="db452-109">Der Abschnitt [Erste Schritte](/microsoft-365/security/office-365-security/defender-for-office-365#getting-started) im Artikel [Microsoft Defender für Office 365](/microsoft-365/security/office-365-security/defender-for-office-365) enthält logische erste Konfigurationsblöcke, die so aussehen:</span><span class="sxs-lookup"><span data-stu-id="db452-109">The [Getting Started](/microsoft-365/security/office-365-security/defender-for-office-365#getting-started) section of the [Microsoft Defender for Office 365 article](/microsoft-365/security/office-365-security/defender-for-office-365) has logical early configuration chunks that look like this:</span></span>

1. <span data-ttu-id="db452-110">Konfigurieren Sie alles mit "Anti" im Namen.</span><span class="sxs-lookup"><span data-stu-id="db452-110">Configure everything with 'Anti' in the name.</span></span>
   - <span data-ttu-id="db452-111">Antischadsoftware</span><span class="sxs-lookup"><span data-stu-id="db452-111">Anti-malware</span></span>
   - <span data-ttu-id="db452-112">Antiphishing</span><span class="sxs-lookup"><span data-stu-id="db452-112">Anti-phishing</span></span>
   - <span data-ttu-id="db452-113">Antispam</span><span class="sxs-lookup"><span data-stu-id="db452-113">Anti-spam</span></span>
2. <span data-ttu-id="db452-114">Richten Sie alles mit "Safe" im Namen ein.</span><span class="sxs-lookup"><span data-stu-id="db452-114">Set up everything with 'Safe' in the name.</span></span>
   - <span data-ttu-id="db452-115">Sichere Links</span><span class="sxs-lookup"><span data-stu-id="db452-115">Safe Links</span></span>
   - <span data-ttu-id="db452-116">Sichere Anlagen</span><span class="sxs-lookup"><span data-stu-id="db452-116">Safe Attachments</span></span>
3. <span data-ttu-id="db452-117">Sichern Sie die Workloads (z. B.</span><span class="sxs-lookup"><span data-stu-id="db452-117">Defend the workloads (ex.</span></span> <span data-ttu-id="db452-118">SharePoint Online, OneDrive und Teams).</span><span class="sxs-lookup"><span data-stu-id="db452-118">SharePoint Online, OneDrive, and Teams).</span></span>
4. <span data-ttu-id="db452-119">Schützen Mit automatischer Nullstunde-Bereinigung.</span><span class="sxs-lookup"><span data-stu-id="db452-119">Protect with zero-Hour auto purge.</span></span>

<span data-ttu-id="db452-120">Zusammen mit einem [Link](../office-365-security/protect-against-threats.md) für den Sofortstart und um schon am ersten Tag mit der Konfiguration zu beginnen.</span><span class="sxs-lookup"><span data-stu-id="db452-120">Along with a [link](../office-365-security/protect-against-threats.md) to jump right in and get configuration going on Day 1.</span></span>

<span data-ttu-id="db452-121">Der letzte Schritt in **Erste Schritte** dient dem Schutz von Benutzern mittels **automatischer Bereinigung zur Nullstunde**, auch bekannt als ZAP (Zero-Hour auto purge).</span><span class="sxs-lookup"><span data-stu-id="db452-121">The last step in **Getting Started** is protecting users with **Zero-Hour auto purge**, also known as ZAP.</span></span> <span data-ttu-id="db452-122">Es kann sehr wichtig sein zu wissen, ob Ihre Bemühungen, ZAP auf verdächtige oder schädliche E-Mails nach der Zustellung anzuwenden, erfolgreich waren.</span><span class="sxs-lookup"><span data-stu-id="db452-122">Knowing if your efforts to ZAP a suspicious or malicious mail, post-delivery, were successful can be very important.</span></span>

<span data-ttu-id="db452-123">Der schnelle Wechsel zur Kusto-Abfragesprache, um nach Problemen zu suchen, stellt einen Vorteil der Zusammenführung dieser beiden Sicherheitscenter dar.</span><span class="sxs-lookup"><span data-stu-id="db452-123">Quickly navigating to Kusto query language to hunt for issues is an advantage of converging these two security centers.</span></span> <span data-ttu-id="db452-124">Sicherheitsteams können ZAP-Fehler überwachen, indem sie [hier](https://security.microsoft.com/advanced-hunting)unter **"Erweiterte Suche"** die nächsten Schritte \> ausführen.</span><span class="sxs-lookup"><span data-stu-id="db452-124">Security teams can monitor ZAP misses by taking their next steps [here](https://security.microsoft.com/advanced-hunting), under **Hunting** \> **Advanced Hunting**.</span></span>

1. <span data-ttu-id="db452-125">Klicken Sie auf der Seite "Erweiterte Suche" auf **"Abfrage".**</span><span class="sxs-lookup"><span data-stu-id="db452-125">On the Advanced Hunting page, click **Query**.</span></span>
1. <span data-ttu-id="db452-126">Kopieren Sie die nachstehende Abfrage in das Abfragefenster.</span><span class="sxs-lookup"><span data-stu-id="db452-126">Copy the query below into the query window.</span></span>
1. <span data-ttu-id="db452-127">Wählen Sie **Abfrage ausführen** aus.</span><span class="sxs-lookup"><span data-stu-id="db452-127">Select **Run query**.</span></span>

```kusto
EmailPostDeliveryEvents 
| where Timestamp > ago(7d)
//List malicious emails that were not zapped successfullyconverge-2-endpoints-new.png
| where ActionType has "ZAP" and ActionResult == "Error"
| project ZapTime = Timestamp, ActionType, NetworkMessageId , RecipientEmailAddress 
//Get logon activity of recipients using RecipientEmailAddress and AccountUpn
| join kind=inner IdentityLogonEvents on $left.RecipientEmailAddress == $right.AccountUpn
| where Timestamp between ((ZapTime-24h) .. (ZapTime+24h))
//Show only pertinent info, such as account name, the app or service, protocol, the target device, and type of logon
| project ZapTime, ActionType, NetworkMessageId , RecipientEmailAddress, AccountUpn, 
LogonTime = Timestamp, AccountDisplayName, Application, Protocol, DeviceName, LogonType
```

:::image type="content" source="../../media/converge-13-advanced-hunt-an-email-zap-new.png" alt-text="Die Seite &quot;Erweiterte Suche&quot; (unter &quot;Suche&quot;) mit ausgewählter Abfrage am oberen Rand des Abfragebereichs und ausführen einer Kusto-Abfrage, um ZAP-Aktionen in den letzten 7 Tagen zu erfassen.":::

<span data-ttu-id="db452-129">Die Daten aus dieser Abfrage werden im Ergebnisbereich unterhalb der Abfrage selbst angezeigt.</span><span class="sxs-lookup"><span data-stu-id="db452-129">The data from this query will appear in the results panel below the query itself.</span></span> <span data-ttu-id="db452-130">Die Ergebnisse enthalten Informationen wie "DeviceName", "AccountDisplayName" und "ZapTime" in einem anpassbaren Ergebnisset.</span><span class="sxs-lookup"><span data-stu-id="db452-130">Results include information like 'DeviceName', 'AccountDisplayName', and 'ZapTime' in a customizable result set.</span></span> <span data-ttu-id="db452-131">Die Ergebnisse können auch zur Dokumentation exportiert werden.</span><span class="sxs-lookup"><span data-stu-id="db452-131">Results can also be exported for your records.</span></span> <span data-ttu-id="db452-132">Wenn die Abfrage später erneut benötigt wird, wählen Sie **Speichern** > **Speichern unter**, und fügen Sie die Abfrage Ihrer Liste von Abfragen, freigegebenen oder Communityabfragen hinzu.</span><span class="sxs-lookup"><span data-stu-id="db452-132">If the query is one you'll need again, select **Save** > **Save As** and add the query to your list of queries, shared, or community queries.</span></span>

## <a name="related-information"></a><span data-ttu-id="db452-133">Verwandte Informationen</span><span class="sxs-lookup"><span data-stu-id="db452-133">Related information</span></span>
- [<span data-ttu-id="db452-134">Bewährte Methoden für die erweiterte Suche</span><span class="sxs-lookup"><span data-stu-id="db452-134">Advanced hunting best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="db452-135">Übersicht – Erweiterte Suche</span><span class="sxs-lookup"><span data-stu-id="db452-135">Overview - Advanced hunting</span></span>](advanced-hunting-overview.md)
