---
title: Übermittlungen von Administratoren in Office 365, O365-Übermittlungen, Office 365 Spam Problem, O365 falsch negativ, Phishing in Office 365, Senden von e-Mails zum Scannen, verdächtige e-Mails in Office 365, e-Mails scannen, Microsoft-Scan für Phishing, Microsoft-Scan für Spam, Submit e-Mail, e-Mail senden, zwielichtige e-Mail, fehlerhafte Darsteller e-Mail, verdächtige, nicht vertrauenswürdige e-Mails, Phishing-e-Mails an Microsoft melden, Phishing-e-Mails an Microsoft melden, böswillige e-Mails an Microsoft melden, Scam-e-Mails an Microsoft melden, Schadsoftware in e-Mail an Microsoft, Spam melden e-Mail im Posteingang Office 365, Virus in e-Mail Office 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: In diesem Artikel erfahren Sie, wie Sie verdächtige e-Mails, verdächtige Phishing-Mails, Spam und andere potenziell schädliche Nachrichten, URLs und Dateien von Ihrem Office 365-Mandanten zur Überprüfung an Microsoft übermitteln.
ms.openlocfilehash: 539d09f03a8a9c5956f2d1e3584f893b0e4ffbb4
ms.sourcegitcommit: d00efe6010185559e742304b55fa2d07127268fa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2020
ms.locfileid: "43033614"
---
# <a name="use-admin-submission-to-submit-suspected-spam-phish-urls-and-files-to-microsoft"></a><span data-ttu-id="5af0f-103">Verwenden der Administrator Übermittlung zum Übermitteln von verdächtigen Spam, Phishing, URLs und Dateien an Microsoft</span><span class="sxs-lookup"><span data-stu-id="5af0f-103">Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft</span></span>

<span data-ttu-id="5af0f-104">Wenn Sie ein Administrator in einer Office 365 Organisation mit Postfächern in Exchange Online sind, können Sie das Übermittlungen-Portal im Office 365 Security & Compliance Center verwenden, um e-Mail-Nachrichten, URLs und Anlagen für die Überprüfung an Microsoft zu übermitteln.</span><span class="sxs-lookup"><span data-stu-id="5af0f-104">If you're an admin in an Office 365 organization with mailboxes in Exchange Online, you can use the Submissions portal in the Office 365 Security & Compliance Center to submit email messages, URLs and attachments to Microsoft for scanning.</span></span>

<span data-ttu-id="5af0f-105">Wenn Sie eine e-Mail übermitteln, erhalten Sie Informationen zu allen Richtlinien, die möglicherweise die eingehenden e-Mails in ihren Mandanten zugelassen haben, sowie über die Untersuchung von URLs und Anlagen in der e-Mail.</span><span class="sxs-lookup"><span data-stu-id="5af0f-105">When you submit an email, you will get information about any policies that may have allowed the incoming email into your tenant, as well as examination of any URLs and attachments in the mail.</span></span> <span data-ttu-id="5af0f-106">Richtlinien, die möglicherweise eine e-Mail erlaubt haben, enthalten die Liste sicherer Absender eines einzelnen Benutzers sowie Richtlinien auf Mandantenebene wie Exchange-Nachrichtenfluss Regeln (auch bekannt als Transportregeln).</span><span class="sxs-lookup"><span data-stu-id="5af0f-106">Policies that may have allowed a mail include an individual user's safe sender list as well as tenant level policies such as Exchange mail flow rules (also known as transport rules).</span></span>

<span data-ttu-id="5af0f-107">Weitere Möglichkeiten zum Übermitteln von e-Mail-Nachrichten, URLs und Anlagen an Microsoft finden Sie unter</span><span class="sxs-lookup"><span data-stu-id="5af0f-107">For other ways to submit email messages, URLs, and attachments to Microsoft, see</span></span> 

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="5af0f-108">Was sollten Sie wissen, bevor Sie beginnen?</span><span class="sxs-lookup"><span data-stu-id="5af0f-108">What do you need to know before you begin?</span></span>

- <span data-ttu-id="5af0f-109">Sie öffnen das Security & Compliance Center unter <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="5af0f-109">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="5af0f-110">Wenn Sie direkt zur **Übermittlungs** Seite wechseln möchten <https://protection.office.com/reportsubmission>, verwenden Sie.</span><span class="sxs-lookup"><span data-stu-id="5af0f-110">To go directly to the **Submission** page, use <https://protection.office.com/reportsubmission>.</span></span>

- <span data-ttu-id="5af0f-111">Wie Sie eine Verbindung mit Exchange Online PowerShell herstellen, finden Sie unter [Herstellen einer Verbindung mit Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="5af0f-111">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="5af0f-112">Informationen zum Herstellen einer Verbindung mit dem eigenständigen Exchange Online Protection PowerShell finden Sie unter [Verbinden mit PowerShell in Exchange Online Protection](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="5af0f-112">To connect to standalone Exchange Online Protection PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="5af0f-113">Bevor Sie diese Verfahren ausführen können, müssen Ihnen die entsprechenden Berechtigungen zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="5af0f-113">You need to be assigned permissions before you can perform these procedures.</span></span> <span data-ttu-id="5af0f-114">Zum Hinzufügen, ändern und Löschen von Anti-Spam-Richtlinien müssen Sie Mitglied der Rollengruppen " **Organisationsverwaltung**", " **Sicherheits Administrator**" oder " **Sicherheits Leser** " sein.</span><span class="sxs-lookup"><span data-stu-id="5af0f-114">To add, modify, and delete anti-spam policies, you need to be a member of the **Organization Management**, **Security Administrator**, or **Security Reader** role groups.</span></span> <span data-ttu-id="5af0f-115">Weitere Informationen zu Rollengruppen im Security & Compliance Center finden Sie unter [Berechtigungen im Office 365 Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="5af0f-115">For more information about role groups in the Security & Compliance Center, see [Permissions in the Office 365 Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

- <span data-ttu-id="5af0f-116">Weitere Informationen darüber, wie Benutzer Nachrichten und Dateien an Microsoft übermitteln können, finden Sie unter [Report Messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span><span class="sxs-lookup"><span data-stu-id="5af0f-116">For more information about how users can submit messages and files to Microsoft see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="how-to-direct-suspicious-content-to-microsoft-for-office-365-scanning"></a><span data-ttu-id="5af0f-117">Vorgehensweise zum direkten verdächtigen von Inhalten an Microsoft für Office 365-Scans</span><span class="sxs-lookup"><span data-stu-id="5af0f-117">How to direct suspicious content to Microsoft for Office 365 scanning</span></span>

<span data-ttu-id="5af0f-118">Um Inhalte an Microsoft zu übermitteln, klicken Sie auf die Schaltfläche **neue Übermittlung** in der linken oberen Ecke der Seite Übermittlungen.</span><span class="sxs-lookup"><span data-stu-id="5af0f-118">To submit content to Microsoft click the **New submission** button in the top left hand side of the submissions page.</span></span> <span data-ttu-id="5af0f-119">Ein Flyout auf der rechten Seite der Seite wird mit der Option zum Senden einer e-Mail, einer URL oder einer Datei angezeigt.</span><span class="sxs-lookup"><span data-stu-id="5af0f-119">A flyout on the right side of the page appears with the option to submit either an email, URL, or file.</span></span>

### <a name="submit-a-questionable-email-to-microsoft"></a><span data-ttu-id="5af0f-120">Senden einer fragwürdigen e-Mail an Microsoft</span><span class="sxs-lookup"><span data-stu-id="5af0f-120">Submit a questionable email to Microsoft</span></span>

![Beispiel für eine e-Mail-Übermittlung](../../media/submission-flyout-email.PNG)

1. <span data-ttu-id="5af0f-122">Um eine e-Mail zu senden, wählen Sie **e-Mail** und geben Sie die e-Mail- **Netzwerknachrichten-ID** an, oder laden Sie die e-Mail-Datei</span><span class="sxs-lookup"><span data-stu-id="5af0f-122">To submit an email, select **email** and specify the email **network message ID** or upload the email file.</span></span>

2. <span data-ttu-id="5af0f-123">Geben Sie die Empfänger an, für die Sie die Richtlinienüberprüfung ausführen möchten.</span><span class="sxs-lookup"><span data-stu-id="5af0f-123">Specify the recipient(s) that you would like to run the policy check against.</span></span> <span data-ttu-id="5af0f-124">Durch die Richtlinienüberprüfung wird ermittelt, ob die e-Mail-Überprüfung aufgrund von Richtlinien auf Benutzer-oder Mandantenebene umgangen wurde.</span><span class="sxs-lookup"><span data-stu-id="5af0f-124">The policy check will determine if the email bypassed scanning due to user or tenant level policies.</span></span>

3. <span data-ttu-id="5af0f-125">Geben Sie an, ob die e-Mail-Nachricht blockiert werden sollte.</span><span class="sxs-lookup"><span data-stu-id="5af0f-125">Specify if the email should have been blocked or not.</span></span> <span data-ttu-id="5af0f-126">Wenn die e-Mail blockiert wurde, geben Sie an, ob Sie als Spam, Phishing oder Schadsoftware blockiert werden soll.</span><span class="sxs-lookup"><span data-stu-id="5af0f-126">If the email should have been blocked, specify if it should have been blocked as Spam, Phishing, or Malware.</span></span> <span data-ttu-id="5af0f-127">Wenn Sie nicht sicher sind, welche Art Sie haben könnten, verwenden Sie Ihr Bestes Urteil.</span><span class="sxs-lookup"><span data-stu-id="5af0f-127">If you are not sure what type it might be, use your best judgment.</span></span>

   - <span data-ttu-id="5af0f-128">Wenn der Filter aufgrund von Richtlinien bei der Übermittlung umgangen wurde, werden Informationen zu dieser Richtlinie angezeigt.</span><span class="sxs-lookup"><span data-stu-id="5af0f-128">If the filter was bypassed due to policies upon submission, you'll see information about that policy.</span></span>

   - <span data-ttu-id="5af0f-129">Wenn der Filter aufgrund einer oder mehrerer Richtlinien nicht umgangen wurde, wird die Überprüfung in einigen Minuten abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="5af0f-129">If the filter was not bypassed due to one or more policies, the scan will complete in several minutes.</span></span> <span data-ttu-id="5af0f-130">Sie erhalten zusätzliche Informationen über die Übermittlung, indem Sie auf den Link Status klicken.</span><span class="sxs-lookup"><span data-stu-id="5af0f-130">You'll see additional information about the submission by clicking on the status link.</span></span> <span data-ttu-id="5af0f-131">Dies beinhaltet die Ergebnisse der Richtlinienüberprüfung und das Ergebnis der erneuten Überprüfung.</span><span class="sxs-lookup"><span data-stu-id="5af0f-131">This includes the results of the policy check and the rescan verdict.</span></span> <span data-ttu-id="5af0f-132">Hinweis Dadurch wird die e-Mail-Nachricht nicht über den Office 365 ATP-voll Filter Stapel erneut ausgeführt, es wird jedoch ein partieller erneuter Scan auf der Grundlage bestimmter Attribute der e-Mail, der URL oder der Datei ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="5af0f-132">Note this does not run the email through the Office 365 ATP full filtering stack again but runs a partial rescan based on certain attributes of the mail, URL, or file.</span></span>

4. <span data-ttu-id="5af0f-133">Klicken Sie auf die Schaltfläche **Absenden** .</span><span class="sxs-lookup"><span data-stu-id="5af0f-133">Click the **Submit** button.</span></span>

### <a name="send-a-suspect-url-to-microsoft"></a><span data-ttu-id="5af0f-134">Senden einer verdächtigen URL an Microsoft</span><span class="sxs-lookup"><span data-stu-id="5af0f-134">Send a suspect URL to Microsoft</span></span>

![Beispiel für eine e-Mail-Übermittlung](../../media/submission-url-flyout.png)

1. <span data-ttu-id="5af0f-136">So übermitteln Sie eine URL wählen Sie **URL** aus dem Flyout aus.</span><span class="sxs-lookup"><span data-stu-id="5af0f-136">To submit a URL select **URL** from the flyout.</span></span> <span data-ttu-id="5af0f-137">Geben Sie die vollständige URL einschließlich des Protokolls (**https://**) ein.</span><span class="sxs-lookup"><span data-stu-id="5af0f-137">Type in the full URL including the protocol (**https://**).</span></span>

   <span data-ttu-id="5af0f-138">Wenn Sie die Option **gefiltert haben ausgewählt haben**, geben Sie an, ob die URL Phishing oder Schadsoftware ist.</span><span class="sxs-lookup"><span data-stu-id="5af0f-138">If you selected **Should have been filtered**, specify if the URL is phishing or malware.</span></span>

2. <span data-ttu-id="5af0f-139">Klicken Sie auf die Schaltfläche **Absenden** .</span><span class="sxs-lookup"><span data-stu-id="5af0f-139">Click the **Submit** button.</span></span>

### <a name="submit-a-suspected-file-to-microsoft"></a><span data-ttu-id="5af0f-140">Übermitteln einer vermuteten Datei an Microsoft</span><span class="sxs-lookup"><span data-stu-id="5af0f-140">Submit a suspected file to Microsoft</span></span>

![Beispiel für eine e-Mail-Übermittlung](../../media/submission-file-flyout.PNG)

1. <span data-ttu-id="5af0f-142">Um eine Datei zu übermitteln, wählen Sie **Datei** aus dem Flyout aus, und laden Sie die Datei hoch, die Sie überprüfen möchten.</span><span class="sxs-lookup"><span data-stu-id="5af0f-142">To submit a file select **File** from the flyout and upload the file you would like to scan.</span></span>

2. <span data-ttu-id="5af0f-143">Klicken Sie auf die Schaltfläche **Absenden** .</span><span class="sxs-lookup"><span data-stu-id="5af0f-143">Click the **Submit** button.</span></span>
