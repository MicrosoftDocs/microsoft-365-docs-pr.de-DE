---
title: Funktionsweise sicherer Anlagen in ATP
f1.keywords:
- NOCSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
audience: Admin
ms.date: 05/17/2019
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Erfahren Sie, wie Sie Ihre Organisation vor bösartigen Dateien mit ATP-Tresoranlagen für Office 365 schützen können.
ms.openlocfilehash: d13674a5d3e769fc10a1f5fd2fd80a4f07c063de
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2020
ms.locfileid: "48201473"
---
# <a name="how-atp-safe-attachments-works"></a><span data-ttu-id="646f9-103">Funktionsweise sicherer Anlagen in ATP</span><span class="sxs-lookup"><span data-stu-id="646f9-103">How ATP Safe Attachments works</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="646f9-104">Das Feature "ATP-sichere Anlagen" prüft e-Mail-Anlagen für Personen in Ihrer Organisation.</span><span class="sxs-lookup"><span data-stu-id="646f9-104">The ATP Safe Attachments feature checks email attachments for people in your organization.</span></span> <span data-ttu-id="646f9-105">Wenn eine Richtlinie für ATP-sichere Anlagen vorhanden ist und von dieser Richtlinie erfasste Personen Ihre e-Mails in Office 365 anzeigen, werden Ihre e-Mail-Anlagen überprüft, und es werden entsprechende Aktionen basierend auf Ihren Richtlinien für ATP-sichere Anlagen ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="646f9-105">When an ATP Safe Attachments policy is in place and someone covered by that policy views their email in Office 365, their email attachments are checked and appropriate actions are taken, based on your ATP Safe Attachments policies.</span></span> <span data-ttu-id="646f9-106">Je nachdem, wie Ihre Richtlinien definiert sind, können Personen weiter arbeiten, ohne jemals zu wissen, dass Sie bösartige Dateien gesendet haben.</span><span class="sxs-lookup"><span data-stu-id="646f9-106">Depending on how your policies are defined, people can continue working without ever knowing they were sent malicious files.</span></span>
  
<span data-ttu-id="646f9-107">Hier sind zwei Beispiele für sichere ATP-Anhänge bei der Arbeit.</span><span class="sxs-lookup"><span data-stu-id="646f9-107">Here are two examples of ATP Safe Attachments at work.</span></span>
  
- <span data-ttu-id="646f9-108">**Beispiel 1: e-Mail-Anlage** Angenommen, Lee erhält eine e-Mail-Nachricht mit einer Anlage.</span><span class="sxs-lookup"><span data-stu-id="646f9-108">**Example 1: Email attachment** Suppose that Lee receives an email message that has an attachment.</span></span> <span data-ttu-id="646f9-109">Es ist für Lee nicht offensichtlich, ob diese Anlage sicher ist oder tatsächlich Schadsoftware enthält, die die Benutzeranmeldeinformationen von Lee stehlen soll.</span><span class="sxs-lookup"><span data-stu-id="646f9-109">It is not obvious to Lee whether that attachment is safe or actually contains malware designed to steal Lee's user credentials.</span></span> <span data-ttu-id="646f9-110">In der Organisation von Lees hat ein Sicherheitsadministrator vor einigen Tagen eine Richtlinie für ATP-sichere Anlagen definiert.</span><span class="sxs-lookup"><span data-stu-id="646f9-110">In Lee's organization, a security administrator defined an ATP Safe Attachments policy a few days ago.</span></span> <span data-ttu-id="646f9-111">Mit dem Feature "ATP-sichere Anlagen" wird die e-Mail-Anlage geöffnet und in einer virtuellen Umgebung getestet, bevor Sie von Lee empfangen wird.</span><span class="sxs-lookup"><span data-stu-id="646f9-111">With the ATP Safe Attachments feature, the email attachment is opened and tested in a virtual environment before Lee receives it.</span></span> <span data-ttu-id="646f9-112">Wenn die Anlage als bösartig eingestuft wird, wird Sie automatisch entfernt.</span><span class="sxs-lookup"><span data-stu-id="646f9-112">If the attachment is determined to be malicious, it will be removed automatically.</span></span> <span data-ttu-id="646f9-113">Wenn die Anlage sicher ist, wird sie erwartungsgemäß geöffnet, wenn Lee darauf klickt.</span><span class="sxs-lookup"><span data-stu-id="646f9-113">If the attachment is safe, it will open as expected when Lee clicks on it.</span></span>

- <span data-ttu-id="646f9-114">**Beispiel 2: Datei in SharePoint Online** Angenommen, Jean hat eine Datei erhalten und in SharePoint Online in eine Bibliothek hochgeladen.</span><span class="sxs-lookup"><span data-stu-id="646f9-114">**Example 2: File in SharePoint Online** Suppose that Jean received a file and uploaded it into a library in SharePoint Online.</span></span> <span data-ttu-id="646f9-115">Jean teilt den Link mit der Datei mit dem Rest des Teams, ohne zu wissen, dass es sich bei der Datei tatsächlich um bösartige Dateien handelt.</span><span class="sxs-lookup"><span data-stu-id="646f9-115">Jean shares the link to the file with the rest of the team, not knowing that the file is actually malicious.</span></span> <span data-ttu-id="646f9-116">Glücklicherweise erkennt [ATP für SharePoint, OneDrive und Microsoft Teams](atp-for-spo-odb-and-teams.md) die bösartige Datei und blockiert Sie.</span><span class="sxs-lookup"><span data-stu-id="646f9-116">Fortunately, [ATP for SharePoint, OneDrive, and Microsoft Teams](atp-for-spo-odb-and-teams.md) detects the malicious file and blocks it.</span></span> <span data-ttu-id="646f9-117">Einige Tage später wechselt Chris zum Öffnen des Dokuments.</span><span class="sxs-lookup"><span data-stu-id="646f9-117">A few days later, Chris goes to open the document.</span></span> <span data-ttu-id="646f9-118">Obwohl Chris sehen kann, dass die Datei vorhanden ist, kann Chris Sie nicht öffnen oder freigeben, wodurch der Computer von Chris und andere Personen vor der schädlichen Datei geschützt werden.</span><span class="sxs-lookup"><span data-stu-id="646f9-118">Although Chris can see the file is there, Chris cannot open or share it, which protects Chris's computer and others from the malicious file.</span></span>

<span data-ttu-id="646f9-119">Richtlinien für ATP-sichere Anlagen können auf bestimmte Personen oder Gruppen in Ihrer Organisation oder auf Ihre gesamte Domäne angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="646f9-119">ATP Safe Attachments policies can be applied to specific people or groups in your organization, or to your entire domain.</span></span> <span data-ttu-id="646f9-120">Darüber hinaus können Richtlinien für ATP-sichere Anlagen so konfiguriert werden, dass Platzhalter Anlagen verwendet werden, während tatsächliche Anlagen gescannt werden.</span><span class="sxs-lookup"><span data-stu-id="646f9-120">In addition, ATP Safe Attachments policies can be configured to use placeholder attachments while actual attachments are being scanned.</span></span> <span data-ttu-id="646f9-121">Weitere Informationen finden Sie unter **[Einrichten von Richtlinien für sichere ATP-Anlagen in Office 365](set-up-atp-safe-attachments-policies.md)**.</span><span class="sxs-lookup"><span data-stu-id="646f9-121">To learn more, see **[Set up ATP Safe Attachments policies in Office 365](set-up-atp-safe-attachments-policies.md)**.</span></span>

> [!NOTE]
> <span data-ttu-id="646f9-122">Die Überprüfung der ATP-Tresoranlagen erfolgt in derselben Region, in der sich Ihre Daten befinden.</span><span class="sxs-lookup"><span data-stu-id="646f9-122">ATP Safe Attachments scanning takes place in the same region where your data resides.</span></span> <span data-ttu-id="646f9-123">Weitere Informationen zur Geografie des Rechenzentrums finden Sie unter [Wo befinden sich Ihre Daten?](https://products.office.com/where-is-your-data-located?geo=All).</span><span class="sxs-lookup"><span data-stu-id="646f9-123">For more information about data center geography, see [Where is your data located?](https://products.office.com/where-is-your-data-located?geo=All)</span></span> 

