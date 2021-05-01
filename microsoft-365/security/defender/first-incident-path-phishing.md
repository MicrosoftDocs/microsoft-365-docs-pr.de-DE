---
title: Beispiel für einen Phishing-E-Mail-Angriff
description: Gehen Sie durch eine Beispielanalyse eines Phishingangriffs.
keywords: Vorfälle, Warnungen, untersuchen, Korrelation, Angriff, Computer, Geräte, Benutzer, Identitäten, Identität, Postfach, E-Mail, 365, Microsoft, m365
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: fb3656a9d3f67d979c012d9cc316a10e65a72042
ms.sourcegitcommit: 05f40904f8278f53643efa76a907968b5c662d9a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/30/2021
ms.locfileid: "52114642"
---
# <a name="example-of-a-phishing-email-attack"></a><span data-ttu-id="75b76-104">Beispiel für einen Phishing-E-Mail-Angriff</span><span class="sxs-lookup"><span data-stu-id="75b76-104">Example of a phishing email attack</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="75b76-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="75b76-105">**Applies to:**</span></span>
- <span data-ttu-id="75b76-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="75b76-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="75b76-107">Microsoft 365 Defender kann dazu beitragen, schädliche Anlagen zu erkennen, die per E-Mail zugestellt werden.</span><span class="sxs-lookup"><span data-stu-id="75b76-107">Microsoft 365 Defender can help detect malicious attachments delivered via email.</span></span> <span data-ttu-id="75b76-108">Da das [Office 365 Security and Compliance Center](https://protection.office.com/) in Microsoft 365 Defender integriert ist, können Sicherheitsanalysten Einblick in Bedrohungen von Office 365 haben, z. B. über E-Mail-Anlagen.</span><span class="sxs-lookup"><span data-stu-id="75b76-108">Since the [Office 365 Security and Compliance Center](https://protection.office.com/) integrates with Microsoft 365 Defender, security analysts can have visibility on threats coming in from Office 365, such as through email attachments.</span></span>

<span data-ttu-id="75b76-109">Beispielsweise wurde einem Analysten ein mehrstufiger Vorfall zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="75b76-109">For example, an analyst was assigned a multi-stage incident.</span></span>
 
:::image type="content" source="../../media/first-incident-path-phishing/first-incident-phishing-incident.png" alt-text="Beispiel für einen mehrstufigen Vorfall"::: 

<span data-ttu-id="75b76-111">Auf der **Registerkarte Warnungen** des Vorfalls werden Warnungen von Defender für Office 365 und Microsoft Cloud App Security angezeigt.</span><span class="sxs-lookup"><span data-stu-id="75b76-111">In the **Alerts** tab of the incident, alerts from Defender for Office 365 and Microsoft Cloud App Security are displayed.</span></span> <span data-ttu-id="75b76-112">Der Analyst kann einen Drilldown in defender for Office 365, indem er die Warnungen für E-Mail-Nachrichten aus wählt.</span><span class="sxs-lookup"><span data-stu-id="75b76-112">The analyst can drill down into the Defender for Office 365 alerts by selecting the email messages alerts.</span></span> <span data-ttu-id="75b76-113">Die Details der Warnung werden im Seitenbereich angezeigt.</span><span class="sxs-lookup"><span data-stu-id="75b76-113">The details of the alert are displayed on the side pane.</span></span>

:::image type="content" source="../../media/first-incident-path-phishing/first-incident-phishing-alerts.png" alt-text="Beispiel für eine E-Mail-Warnung":::
 
<span data-ttu-id="75b76-115">Durch einen weiteren Bildlauf nach unten werden weitere Informationen angezeigt, in denen die schädlichen Dateien und der Benutzer angezeigt werden, die betroffen waren.</span><span class="sxs-lookup"><span data-stu-id="75b76-115">By scrolling down further, more information is displayed, showing the malicious files and user that was impacted.</span></span>

:::image type="content" source="../../media/first-incident-path-phishing/first-incident-phishing-impact.png" alt-text="Beispiel für die Auswirkungen einer E-Mail-Benachrichtigung auf Benutzer und Dateien":::
  
<span data-ttu-id="75b76-117">Wenn **Sie die Seite Benachrichtigung öffnen** auswählen, gelangen Sie zu der spezifischen Warnung, in der verschiedene Informationen ausführlicher angezeigt werden können, indem Sie den Link auswählen.</span><span class="sxs-lookup"><span data-stu-id="75b76-117">Selecting **Open alert page** takes you to the specific alert where various information can be viewed in greater detail by selecting the link.</span></span> <span data-ttu-id="75b76-118">Die tatsächliche E-Mail-Nachricht kann angezeigt werden, indem Sie nachrichten **im Explorer** am unteren Rand des Panels anzeigen auswählen.</span><span class="sxs-lookup"><span data-stu-id="75b76-118">The actual email message can be viewed by selecting **View messages in Explorer** toward the bottom of the panel.</span></span>
 
:::image type="content" source="../../media/first-incident-path-phishing/first-incident-phishing-event-explorer.png" alt-text="Beispiel für die Details einer Warnung"::: 

<span data-ttu-id="75b76-120">Dies führt den Analysten zur Seite Bedrohungsverwaltung, auf der die E-Mail Betreff, Empfänger, Absender und andere Informationen angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="75b76-120">This takes the analyst to the Threat Management page where the email Subject, Recipient, Sender, and other information are displayed.</span></span> <span data-ttu-id="75b76-121">**Zap** unter **Sonderaktionen** teilt dem Analysten mit, dass das Feature für die automatische Reinigung der Nullstunde implementiert wurde.</span><span class="sxs-lookup"><span data-stu-id="75b76-121">**ZAP** under **Special Actions** tells the analyst that the Zero-hour auto purge feature was implemented.</span></span> <span data-ttu-id="75b76-122">Zap erkennt und entfernt automatisch schädliche Nachrichten und Spamnachrichten aus Postfächern in der gesamten Organisation.</span><span class="sxs-lookup"><span data-stu-id="75b76-122">ZAP automatically detects and removes malicious and spam messages from mailboxes across the organization.</span></span> <span data-ttu-id="75b76-123">Weitere Informationen finden Sie unter [Zero-Hour Auto Purge (ZAP) in Exchange Online](../office-365-security/zero-hour-auto-purge.md).</span><span class="sxs-lookup"><span data-stu-id="75b76-123">For more information, see [Zero-hour auto purge (ZAP) in Exchange Online](../office-365-security/zero-hour-auto-purge.md).</span></span>

<span data-ttu-id="75b76-124">Andere Aktionen können für bestimmte Nachrichten durch Auswählen von **Aktionen ergriffen werden.**</span><span class="sxs-lookup"><span data-stu-id="75b76-124">Other actions can be taken on specific messages by selecting **Actions**.</span></span> 
 
:::image type="content" source="../../media/first-incident-path-phishing/first-incident-phishing-actions.png" alt-text="Beispiel für die anderen Aktionen für E-Mail-Nachrichten"::: 

## <a name="next-step"></a><span data-ttu-id="75b76-126">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="75b76-126">Next step</span></span>

<span data-ttu-id="75b76-127">Weitere Informationen finden Sie [unter Identitätsbasierter](first-incident-path-identity.md) Angriffsuntersuchungspfad.</span><span class="sxs-lookup"><span data-stu-id="75b76-127">See the [identity-based attack](first-incident-path-identity.md) investigation path.</span></span>

## <a name="see-also"></a><span data-ttu-id="75b76-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="75b76-128">See also</span></span>

- [<span data-ttu-id="75b76-129">Übersicht über Vorfälle</span><span class="sxs-lookup"><span data-stu-id="75b76-129">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="75b76-130">Analysieren von Vorfällen</span><span class="sxs-lookup"><span data-stu-id="75b76-130">Analyze incidents</span></span>](investigate-incidents.md)
- [<span data-ttu-id="75b76-131">Verwalten von Vorfällen</span><span class="sxs-lookup"><span data-stu-id="75b76-131">Manage incidents</span></span>](manage-incidents.md)
