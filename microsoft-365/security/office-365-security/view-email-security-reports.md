---
title: Anzeigen von e-Mail-Sicherheits &amp; Berichten im Security Compliance Center, kompromittierten Benutzern, Verschlüsselung, Bedrohungsschutz Status, Malwareerkennungen, Top-Schadsoftware, Spam Erkennung, gesendete und empfangene e-Mails, von Benutzern gemeldete Nachrichten, Lesen von Berichten, Erkennung, Sicherheitsdaten, Sicherheitsinformationen
f1.keywords:
- NOCSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
ms.date: 01/16/2020
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 3a137e28-1174-42d5-99af-f18868b43e86
ms.collection:
- M365-security-compliance
description: Hier erfahren Sie, wie Sie e-Mail-Sicherheitsberichte für Ihre Organisation suchen und verwenden. E-Mail-Sicherheitsberichte sind im &amp; Security Compliance Center verfügbar.
ms.openlocfilehash: 59090e53389b4e95d8987989819e71be6fce61e2
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2020
ms.locfileid: "41598112"
---
# <a name="view-email-security-reports-in-the-security-amp-compliance-center"></a><span data-ttu-id="ca539-104">Anzeigen von e-Mail-Sicherheits &amp; Berichten im Security Compliance Center</span><span class="sxs-lookup"><span data-stu-id="ca539-104">View email security reports in the Security &amp; Compliance Center</span></span>

<span data-ttu-id="ca539-105">Im [ &amp; Security Compliance Center](https://protection.office.com) steht eine Vielzahl von Berichten zur Verfügung, mit denen Sie sehen können, wie e-Mail-Sicherheitsfunktionen wie Antispam-, Antischadsoftware-und Verschlüsselungsfunktionen in Office 365 Ihre Organisation schützen.</span><span class="sxs-lookup"><span data-stu-id="ca539-105">A variety of reports are available in the [Security &amp; Compliance Center](https://protection.office.com) to help you see how email security features, such as anti-spam, anti-malware, and encryption features in Office 365 are protecting your organization.</span></span> <span data-ttu-id="ca539-106">Wenn Sie über die [erforderlichen Berechtigungen](#what-permissions-are-needed-to-view-these-reports)verfügen, können Sie diese Berichte &amp; im Security Compliance Center anzeigen, indem Sie zum **Dashboard** **Berichte** \> wechseln.</span><span class="sxs-lookup"><span data-stu-id="ca539-106">If you have the [necessary permissions](#what-permissions-are-needed-to-view-these-reports), you can view these reports in the Security &amp; Compliance Center by going to **Reports** \> **Dashboard**.</span></span>
  
![Dashboard, in dem Sie sehen, wie Advanced Threat Protection funktioniert](../media/6b213d34-adbb-44af-8549-be9a7e2db087.png)
  
<span data-ttu-id="ca539-108">Ihre e-Mail-Sicherheitsberichte umfassen Folgendes:</span><span class="sxs-lookup"><span data-stu-id="ca539-108">Your email security reports include the following:</span></span>
- [<span data-ttu-id="ca539-109">Bericht "kompromittierte Benutzer" (**neu!**)</span><span class="sxs-lookup"><span data-stu-id="ca539-109">Compromised Users report (**NEW!**)</span></span>](#compromised-users-report-new)
- [<span data-ttu-id="ca539-110">Verschlüsselungs Bericht</span><span class="sxs-lookup"><span data-stu-id="ca539-110">Encryption report</span></span>](#encryption-report)
- [<span data-ttu-id="ca539-111">Threat Protection-Statusbericht</span><span class="sxs-lookup"><span data-stu-id="ca539-111">Threat Protection Status report</span></span>](#threat-protection-status-report) 
- [<span data-ttu-id="ca539-112">Bericht über Schadsoftware-Erkennungen</span><span class="sxs-lookup"><span data-stu-id="ca539-112">Malware Detections report</span></span>](#malware-detections-report) 
- [<span data-ttu-id="ca539-113">Höchst schädlicher Bericht</span><span class="sxs-lookup"><span data-stu-id="ca539-113">Top Malware report</span></span>](#top-malware-report)
- [<span data-ttu-id="ca539-114">Bericht über die häufigsten Absender und Empfänger</span><span class="sxs-lookup"><span data-stu-id="ca539-114">Top Senders and Recipients report</span></span>](#top-senders-and-recipients-report)
- [<span data-ttu-id="ca539-115">Spoofing-Erkennungs Bericht</span><span class="sxs-lookup"><span data-stu-id="ca539-115">Spoof Detections report</span></span>](#spoof-detections-report)
- [<span data-ttu-id="ca539-116">Spam Erkennungs Bericht</span><span class="sxs-lookup"><span data-stu-id="ca539-116">Spam Detections report</span></span>](#spam-detections-report)
- [<span data-ttu-id="ca539-117">Gesendete und empfangene e-Mail-Berichte</span><span class="sxs-lookup"><span data-stu-id="ca539-117">Sent and received email report</span></span>](#sent-and-received-email-report)
- [<span data-ttu-id="ca539-118">Bericht über vom Benutzer gemeldete Nachrichten</span><span class="sxs-lookup"><span data-stu-id="ca539-118">User-reported messages report</span></span>](#user-reported-messages-report)


## <a name="compromised-users-report-new"></a><span data-ttu-id="ca539-119">Bericht "kompromittierte Benutzer" (**neu!**)</span><span class="sxs-lookup"><span data-stu-id="ca539-119">Compromised Users report (**NEW!**)</span></span> 

<span data-ttu-id="ca539-120">Dieser Bericht, der für alle Personen mit Exchange Online Schutz verfügbar ist, zeigt die Anzahl der Benutzerkonten, die als verdächtige oder eingeschränkte Benutzer gekennzeichnet sind, Daten, die besonders nützlich sind, wenn Konten in einen der Zustände eingeben, die darauf hindeuten, dass das Benutzerkonto problematisch sein kann, oder sogar gefährdet.</span><span class="sxs-lookup"><span data-stu-id="ca539-120">This report, available to anyone with Exchange Online Protection, shows the number of user accounts marked as Suspicious or Restricted users, data particularly useful as accounts enter either of the states that indicate the user account may be problematic, or even compromised.</span></span> <span data-ttu-id="ca539-121">Bei häufiger Verwendung kann der kompromittierte Benutzerbericht Spitzen und sogar Trends in Konten erkennen, die in verdächtigen oder eingeschränkten Zuständen markiert sind, was Hinweise gibt, dass ein Problem mit Sicherheit und dem Wohlbefinden Ihres Mandanten auftreten kann.</span><span class="sxs-lookup"><span data-stu-id="ca539-121">With frequent use, the Compromised User report can spot spikes, and even trends, in accounts marked in suspicious or restricted states, giving evidence there could be an issue with security and the wellness of your tenant.</span></span>

![Der Bericht "kompromittierte Benutzer" wird in Office 365 angezeigt.](../media/tp-threatProtectStatRpt-CompromisedUserRpt.png)

## <a name="encryption-report"></a><span data-ttu-id="ca539-123">Verschlüsselungs Bericht</span><span class="sxs-lookup"><span data-stu-id="ca539-123">Encryption report</span></span>

<span data-ttu-id="ca539-124">Im **Verschlüsselungs Bericht** werden Informationen über e-Mail-Nachrichten angezeigt, die entweder über die Richtlinien Ihrer Organisation oder durch Endbenutzer Steuerelemente verschlüsselt wurden.</span><span class="sxs-lookup"><span data-stu-id="ca539-124">The **Encryption report** shows information about email messages that were encrypted, either through your organization's policies, or through end-user controls.</span></span> <span data-ttu-id="ca539-125">Das Sicherheitsteam Ihrer Organisation kann Informationen in diesem Bericht verwenden, um Muster zu identifizieren und Richtlinien für vertrauliche e-Mail-Nachrichten proaktiv anzuwenden oder anzupassen.</span><span class="sxs-lookup"><span data-stu-id="ca539-125">Your organization's security team can use information in this report to identify patterns and proactively apply or adjust policies for sensitive email messages.</span></span>

<span data-ttu-id="ca539-126">Um diesen Bericht anzuzeigen, wechseln Sie im Security #a0 Compliance Center zu **Berichte** \> - **Dashboard** \> - **Verschlüsselungs Bericht**.</span><span class="sxs-lookup"><span data-stu-id="ca539-126">To view this report, in the Security & Compliance Center, go to **Reports** \> **Dashboard** \> **Encryption report**.</span></span>

![Verschlüsselungs Bericht](../media/encryptionreport-defaultview.png) 

<span data-ttu-id="ca539-128">Wenn der Bericht zuerst geöffnet wird, werden Daten zu Verschlüsselungsmethoden angezeigt, die für e-Mail-Nachrichten in den letzten sieben (7) Tagen verwendet wurden.</span><span class="sxs-lookup"><span data-stu-id="ca539-128">When the report first opens, you'll see data about encryption methods used on email messages for the past seven (7) days.</span></span> <span data-ttu-id="ca539-129">Sie können den Datumsbereich und die Details ändern, die im Bericht angezeigt werden, indem Sie in der oberen rechten Ecke des Bildschirms auf **Filter** klicken.</span><span class="sxs-lookup"><span data-stu-id="ca539-129">You can change the date range and the details that are displayed in the report by clicking **Filters** in the upper right corner of the screen.</span></span>

![Filter für Verschlüsselungs Berichte](../media/encryptionreport-filters.png)   

<span data-ttu-id="ca539-131">Sie können auch das Menü **aufschlüsseln** nach verwenden, um Daten nach Verschlüsselungs Vorlage (oder Methode) anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="ca539-131">You can also use the **Break down by** menu to view data by encryption template (or method).</span></span>

![Verschlüsselungsmethode oder-Vorlage](../media/encryptionreport-breakdownby.png)

<span data-ttu-id="ca539-133">Mit dem Menü **Daten anzeigen nach** können Sie die Ansicht so ändern, dass die Anzahl der verschlüsselten Nachrichten in den obersten fünf Empfängerdomänen angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="ca539-133">And, you can use the **View data by** menu to change the view to see counts of encrypted messages to the top five recipient domains.</span></span>

![Verschlüsselungs Bericht anzeigen von Daten nach Menü](../media/encryptionreport-viewdataby.png)

<span data-ttu-id="ca539-135">Durch die Flexibilität des neuen Verschlüsselungs Berichts können Sie Trends anzeigen und entsprechende Aktionen durchführen.</span><span class="sxs-lookup"><span data-stu-id="ca539-135">With the flexibility of the new Encryption report, you can view trends and take appropriate actions.</span></span> <span data-ttu-id="ca539-136">Wenn beispielsweise eine hohe Anzahl von von Benutzern verschlüsselten e-Mail-Nachrichten angezeigt wird, möchten Sie möglicherweise eine Verschlüsselungsrichtlinie zum Automatisieren der Verschlüsselung für bestimmte Anwendungsfälle hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="ca539-136">For example, if you see a high number of email messages encrypted by users, you might want to add an encryption policy to automate encryption for certain use cases.</span></span> <span data-ttu-id="ca539-137">(Weitere Informationen dazu finden Sie unter [Definieren von Nachrichtenfluss Regeln zum Verschlüsseln von e-Mail-Nachrichten in Office 365](../../compliance/define-mail-flow-rules-to-encrypt-email.md).) Wenn Sie beispielsweise eine Reihe von Verschlüsselungs Vorlagen verfügbar haben, die von keiner verwendet werden, können Sie untersuchen, ob Benutzer eine Schulung für diese Funktion benötigen.</span><span class="sxs-lookup"><span data-stu-id="ca539-137">(To get help with that, see [Define mail flow rules to encrypt email messages in Office 365](../../compliance/define-mail-flow-rules-to-encrypt-email.md).) As another example, if you have a number of encryption templates available but no one is using them, you might explore whether users need training for that feature.</span></span> 

<span data-ttu-id="ca539-138">Mithilfe dieses Berichts kann das Sicherheits-und Compliance-Team Ihrer Organisation überwachen, wie die Nachrichtenverschlüsselung verwendet wird und ob weitere Aktionen erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="ca539-138">Use this report enables your organization's security and compliance team to monitor how message encryption is being used, and whether further actions are needed.</span></span> <span data-ttu-id="ca539-139">Weitere Informationen zur Verschlüsselung finden Sie unter [e-Mail-Verschlüsselung in Office 365](../../compliance/email-encryption.md).</span><span class="sxs-lookup"><span data-stu-id="ca539-139">To learn more about encryption, see [Email encryption in Office 365](../../compliance/email-encryption.md).</span></span>

## <a name="threat-protection-status-report"></a><span data-ttu-id="ca539-140">Threat Protection-Statusbericht</span><span class="sxs-lookup"><span data-stu-id="ca539-140">Threat Protection Status report</span></span>

<span data-ttu-id="ca539-141">Der **Status Bericht zum Bedrohungsschutz** ist ein intelligenter Bericht, in dem böswillige e-Mails angezeigt werden, die durch Exchange Online Schutz erkannt und blockiert wurden.</span><span class="sxs-lookup"><span data-stu-id="ca539-141">The **Threat Protection Status** report is a smart report that shows malicious email that was detected and blocked by Exchange Online Protection.</span></span> <span data-ttu-id="ca539-142">Dieser Bericht ist hilfreich, um e-Mails anzuzeigen, die als Schadsoftware oder als Phishing-Versuch im Laufe der Zeit identifiziert wurden (bis zu 90 Tage), und es ermöglicht Sicherheitsadministratoren, Trends zu identifizieren oder zu bestimmen, ob Richtlinien angepasst werden müssen.</span><span class="sxs-lookup"><span data-stu-id="ca539-142">This report is useful for viewing email identified as malware or a phishing attempt over time (up to 90 days), and it enables security administrators to identify trends or determine whether policies need adjustments.</span></span>

> [!NOTE]
> <span data-ttu-id="ca539-143">Ein Status Bericht über den Bedrohungsschutz steht Kunden zur Verfügung, die entweder [Office 365 ATP](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp) oder [Exchange Online Protection](https://docs.microsoft.com/microsoft-365/security/office-365-security/what-is-eop) (EoP) haben; die Informationen, die im Threat Protection-Status Bericht für ATP-Kunden angezeigt werden, enthalten jedoch wahrscheinlich unterschiedliche Daten, als EoP-Kunden möglicherweise sehen.</span><span class="sxs-lookup"><span data-stu-id="ca539-143">A Threat Protection Status report is available to customers who have either [Office 365 ATP](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp) or [Exchange Online Protection](https://docs.microsoft.com/microsoft-365/security/office-365-security/what-is-eop) (EOP); however, the information that is displayed in the Threat Protection Status report for ATP customers will likely contain different data than what EOP customers might see.</span></span> <span data-ttu-id="ca539-144">EoP-Kunden können beispielsweise Informationen über in e-Mails erkannte Schadsoftware anzeigen, aber keine Informationen zu [schädlichen Dateien, die in SharePoint Online, OneDrive oder Microsoft Teams erkannt](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-for-spo-odb-and-teams)wurden, eine ATP-spezifische Funktion.</span><span class="sxs-lookup"><span data-stu-id="ca539-144">For example, EOP customers can view information about malware detected in email, but not information about [malicious files detected in SharePoint Online, OneDrive, or Microsoft Teams](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-for-spo-odb-and-teams), an ATP-specific capability.</span></span> <span data-ttu-id="ca539-145">([Weitere Informationen zu ATP-Berichten](https://docs.microsoft.com/microsoft-365/security/office-365-security/view-reports-for-atp).)</span><span class="sxs-lookup"><span data-stu-id="ca539-145">([Learn more about ATP reports](https://docs.microsoft.com/microsoft-365/security/office-365-security/view-reports-for-atp).)</span></span>
  
<span data-ttu-id="ca539-146">Um diesen Bericht anzuzeigen, wechseln Sie [im &amp; Security Compliance Center](https://protection.office.com)zu **Reports** \> **Dashboard** \> **Threat Protection Status**.</span><span class="sxs-lookup"><span data-stu-id="ca539-146">To view this report, in the [Security &amp; Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** \> **Threat Protection Status**.</span></span>
  
![Threat Protection-Statusbericht](../media/0ff86e12-c2b2-4d89-92a5-cefb054dc070.png)
  
<span data-ttu-id="ca539-148">Wenn Sie den Threat Protection-Status Bericht zum ersten Mal öffnen, zeigt der Bericht standardmäßig Daten für die letzten sieben Tage an. Sie können jedoch auf **Filter** klicken und den Datumsbereich für bis zu 90 Tage mit Details ändern.</span><span class="sxs-lookup"><span data-stu-id="ca539-148">When you first open the Threat Protection Status report, the report shows data for the past seven days by default; however, you can click **Filters** and change the date range for up to 90 days of detail.</span></span> <span data-ttu-id="ca539-149">(Wenn Sie ein Testabonnement verwenden, sind die Daten möglicherweise auf 30 Tage eingeschränkt.)</span><span class="sxs-lookup"><span data-stu-id="ca539-149">(If you are using a trial subscription, you might be limited to 30 days' of data.)</span></span>

<span data-ttu-id="ca539-150">Dieser Bericht ist hilfreich, um die Effektivität und Auswirkungen der [Exchange Online Schutzfunktionen](https://docs.microsoft.com/microsoft-365/security/office-365-security/eop-features)Ihrer Organisation und die längerfristige Trendentwicklung anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="ca539-150">This report is useful for viewing the effectiveness and impact of your organization's [Exchange Online Protection features](https://docs.microsoft.com/microsoft-365/security/office-365-security/eop-features), and for longer-term trending.</span></span> 
  
![Status Berichtsfilter für den Bedrohungsschutz](../media/ab6b6b8d-e97a-4c3a-8fb1-c4940dcb7a07.png)
  
<span data-ttu-id="ca539-152">Sie können auch auswählen, ob Daten für als bösartig identifizierte e-Mails, als Phishing-Versuche identifizierte e-Mails oder als Schadsoftware identifizierte e-Mails angezeigt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="ca539-152">You can also choose whether to view data for email identified as malicious, email identified as a phishing attempts, or email identified as containing malware.</span></span>
  
![Status Bericht-Ansichtsoptionen für den Bedrohungsschutz](../media/d429ecd7-cb7a-4c99-8d27-79a2832cf467.png)
  
## <a name="malware-detections-report"></a><span data-ttu-id="ca539-154">Bericht über Schadsoftware-Erkennungen</span><span class="sxs-lookup"><span data-stu-id="ca539-154">Malware Detections report</span></span>

<span data-ttu-id="ca539-155">Der Bericht über **Malwareerkennungen** zeigt, wie viele eingehende und ausgehende Nachrichten als Schadsoftware für Ihre Organisation erkannt wurden.</span><span class="sxs-lookup"><span data-stu-id="ca539-155">The **Malware Detections** report shows how many incoming and outgoing messages were detected as containing malware for your organization.</span></span> 
  
<span data-ttu-id="ca539-156">Um diesen Bericht anzuzeigen, wechseln Sie [im &amp; Security Compliance Center](https://protection.office.com)zu **Reports** \> **-Dashboard** \> - **Malware Erkennungen**.</span><span class="sxs-lookup"><span data-stu-id="ca539-156">To view this report, in the [Security &amp; Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** \> **Malware Detections**.</span></span>
  
![Beispiel für Malware Erkennungsberichte](../media/a1ba61a3-565a-46d6-b0d5-6a6cff6b31d7.png)
  
<span data-ttu-id="ca539-158">Ähnlich wie bei anderen Berichten, wie dem [Threat Protection-Status Bericht](#threat-protection-status-report), zeigt der Bericht standardmäßig Daten für die letzten sieben Tage an.</span><span class="sxs-lookup"><span data-stu-id="ca539-158">Similar to other reports, like the [Threat Protection Status report](#threat-protection-status-report), the report displays data for the past seven days by default.</span></span> <span data-ttu-id="ca539-159">Sie können jedoch **Filter** auswählen, um den Datumsbereich zu ändern.</span><span class="sxs-lookup"><span data-stu-id="ca539-159">However, you can choose **Filters** to change the date range.</span></span> 
  
## <a name="top-malware-report"></a><span data-ttu-id="ca539-160">Höchst schädlicher Bericht</span><span class="sxs-lookup"><span data-stu-id="ca539-160">Top Malware report</span></span>

<span data-ttu-id="ca539-161">Der **oberste Schadsoftware** -Bericht zeigt die verschiedenen Arten von Schadsoftware, die von [Exchange Online](https://docs.microsoft.com/microsoft-365/security/office-365-security/eop-features)erkannt wurde.</span><span class="sxs-lookup"><span data-stu-id="ca539-161">The **Top Malware** report shows the various kinds of malware that was detected by [Exchange Online](https://docs.microsoft.com/microsoft-365/security/office-365-security/eop-features).</span></span> 
  
<span data-ttu-id="ca539-162">Um diesen Bericht anzuzeigen, wechseln Sie [im &amp; Security Compliance Center](https://protection.office.com)zu **Reports** \> **Dashboard** \> **Top Malware**.</span><span class="sxs-lookup"><span data-stu-id="ca539-162">To view this report, in the [Security &amp; Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** \> **Top Malware**.</span></span>
  
![SCC-EoP Top-Schadsoftware](../media/763330b3-f56e-4ba4-b0bb-051500ae950a.png)
  
<span data-ttu-id="ca539-164">Wenn Sie mit dem Mauszeiger auf einen Keil im Kreisdiagramm zeigen, sehen Sie den Namen einer Art von Schadsoftware und wie viele Nachrichten mit dieser Schadsoftware erkannt wurden.</span><span class="sxs-lookup"><span data-stu-id="ca539-164">When you hover over a wedge in the pie chart, you can see the name of a kind of malware and how many messages were detected as having that malware.</span></span>
  
<span data-ttu-id="ca539-165">Klicken (oder tippen) Sie auf den Bericht, um ihn in einem neuen Browserfenster zu öffnen, in dem Sie eine detailliertere Ansicht des Berichts erhalten können.</span><span class="sxs-lookup"><span data-stu-id="ca539-165">Click (or tap) the report to open it in a new browser window, where you can get a more detailed view of the report.</span></span>
  
![Dieser Bericht zeigt die wichtigste für Ihre Organisation erkannte Malware](../media/3fded224-fb31-4713-86f2-8afce5ce2991.png)
  
<span data-ttu-id="ca539-167">Unter dem Diagramm sehen Sie eine Liste der erkannten Schadsoftware und wie viele Nachrichten mit dieser Schadsoftware erkannt wurden.</span><span class="sxs-lookup"><span data-stu-id="ca539-167">Below the chart, you'll see a list of detected malware and how many messages were detected as having that malware.</span></span>
  
## <a name="top-senders-and-recipients-report"></a><span data-ttu-id="ca539-168">Bericht über die häufigsten Absender und Empfänger</span><span class="sxs-lookup"><span data-stu-id="ca539-168">Top Senders and Recipients report</span></span>

<span data-ttu-id="ca539-169">Der Bericht " **Top Senders and recipients** " ist ein Kreisdiagramm mit Ihren oberen e-Mail-Absendern.</span><span class="sxs-lookup"><span data-stu-id="ca539-169">The **Top Senders and Recipients** report is a pie chart showing your top email senders.</span></span> 
  
<span data-ttu-id="ca539-170">Um diesen Bericht anzuzeigen, wechseln Sie [im &amp; Security Compliance Center](https://protection.office.com)zu **Reports** \> **Dashboard** \> **Top-Absender und-Empfänger**.</span><span class="sxs-lookup"><span data-stu-id="ca539-170">To view this report, in the [Security &amp; Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** \> **Top Senders and Recipients**.</span></span>
  
![Um diesen Bericht anzuzeigen, wechseln Sie im &amp; Security Compliance Center zu Reports \> Dashboard \> Top Sender und Empfänger](../media/b5506b5c-2420-4a5a-9ea3-d654294ac838.png)
  
<span data-ttu-id="ca539-172">Wenn Sie mit dem Mauszeiger auf einen Keil im Kreisdiagramm zeigen, wird die Anzahl der gesendeten oder empfangenen Nachrichten angezeigt.</span><span class="sxs-lookup"><span data-stu-id="ca539-172">When you hover over a wedge in the pie chart, you can see a count of messages sent or received.</span></span>
  
<span data-ttu-id="ca539-173">Klicken (oder tippen) Sie auf den Bericht, um ihn in einem neuen Browserfenster zu öffnen, in dem Sie eine detailliertere Ansicht des Berichts erhalten können.</span><span class="sxs-lookup"><span data-stu-id="ca539-173">Click (or tap) the report to open it in a new browser window, where you can get a more detailed view of the report.</span></span>
  
<span data-ttu-id="ca539-174">Verwenden Sie die Liste **Daten für anzeigen** , um festzustellen, ob Daten für die wichtigsten Absender, Empfänger, Spamempfänger und Schadsoftware-Empfänger angezeigt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="ca539-174">Use the **Show data for** list to choose whether to view data for top senders, receivers, spam recipients, and malware recipients.</span></span> <span data-ttu-id="ca539-175">Sie können auch sehen, wer die Malware empfangen hat, die von [Exchange Online Protection](https://docs.microsoft.com/microsoft-365/security/office-365-security/what-is-eop)erkannt wurde.</span><span class="sxs-lookup"><span data-stu-id="ca539-175">You can also see who received malware that was detected by [Exchange Online Protection](https://docs.microsoft.com/microsoft-365/security/office-365-security/what-is-eop).</span></span> 
  
![Verwenden der Liste "Daten für anzeigen" zum Anzeigen bestimmter Informationen](../media/bd91449f-7d42-4749-8666-7b44044049b8.png)
  
<span data-ttu-id="ca539-177">Unter dem Diagramm sehen Sie, wer die häufigsten e-Mail-Absender oder Empfänger waren, zusammen mit der Anzahl der Nachrichten, die für den angegebenen Zeitraum gesendet oder empfangen wurden.</span><span class="sxs-lookup"><span data-stu-id="ca539-177">Below the chart, you'll see who the top email senders or recipients were, along with a count of messages sent or received for the given time period.</span></span>
  
## <a name="spoof-detections-report"></a><span data-ttu-id="ca539-178">Spoofing-Erkennungs Bericht</span><span class="sxs-lookup"><span data-stu-id="ca539-178">Spoof Detections report</span></span>

<span data-ttu-id="ca539-179">Der Bericht **Spoof-Erkennungen** zeigt, wie viele gefälschte e-Mail-Nachrichten erkannt wurden und von denen, die als "gut" eingestuft wurden (Spoof-e-Mails wurden aus legitimen geschäftlichen Gründen ausgeführt).</span><span class="sxs-lookup"><span data-stu-id="ca539-179">The **Spoof Detections** report shows how many spoof mail messages were detected, and of those, which ones were considered "good" (spoof mail done for legitimate business reasons).</span></span> 
  
<span data-ttu-id="ca539-180">Um diesen Bericht anzuzeigen, wechseln Sie [im &amp; Security Compliance Center](https://protection.office.com)zu **Berichte** \> \*\*\*\* \> **-Spoofing-e-Mail-** Benachrichtigungen.</span><span class="sxs-lookup"><span data-stu-id="ca539-180">To view this report, in the [Security &amp; Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** \> **Spoof Mail**.</span></span>
  
![Wechseln Sie im &amp; Security Compliance Center zu Berichte \> -Spoof \> -e-Mail des Dashboards](../media/0427e85c-9e40-4225-a0f0-e21a4e8b0e44.png)
  
<span data-ttu-id="ca539-182">Wenn Sie den Mauszeiger über einen Tag im Diagramm bewegen, können Sie sehen, wie viele Spoof-e-Mail-Nachrichten eingingen.</span><span class="sxs-lookup"><span data-stu-id="ca539-182">When you hover over a day in the chart, you can see how many spoof mail messages came through.</span></span>
  
<span data-ttu-id="ca539-183">Klicken (oder tippen) Sie auf den Bericht, um ihn in einem neuen Browserfenster zu öffnen, in dem Sie eine detailliertere Ansicht des Berichts erhalten können.</span><span class="sxs-lookup"><span data-stu-id="ca539-183">Click (or tap) the report to open it in a new browser window, where you can get a more detailed view of the report.</span></span> <span data-ttu-id="ca539-184">Weitere Informationen zum Schutz vor Spoofing finden Sie unter [Anti-Spoofing Protection in Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/anti-spoofing-protection).</span><span class="sxs-lookup"><span data-stu-id="ca539-184">To learn more about anti-spoof protection, see [Anti-spoofing protection in Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/anti-spoofing-protection).</span></span>
  
## <a name="spam-detections-report"></a><span data-ttu-id="ca539-185">Spam Erkennungs Bericht</span><span class="sxs-lookup"><span data-stu-id="ca539-185">Spam Detections report</span></span>

<span data-ttu-id="ca539-186">Der **Spam Erkennungs** Bericht zeigt alle von Exchange Online blockierten Spam Inhalte an.</span><span class="sxs-lookup"><span data-stu-id="ca539-186">The **Spam Detections** report shows all the spam content blocked by Exchange Online.</span></span> <span data-ttu-id="ca539-187">Nachrichten werden pro Nachricht und nicht pro Empfänger gezählt.</span><span class="sxs-lookup"><span data-stu-id="ca539-187">Messages are counted per message, and not per recipient.</span></span> <span data-ttu-id="ca539-188">Wenn beispielsweise eine e-Mail-Nachricht an 100-Empfänger in Ihrer Organisation gesendet wurde, wird Sie als eine Nachricht gezählt.</span><span class="sxs-lookup"><span data-stu-id="ca539-188">For example, if an email message was sent to 100 recipients in your organization, it is counted as one message.</span></span>
  
<span data-ttu-id="ca539-189">Um diesen Bericht anzuzeigen, wechseln Sie [im &amp; Security Compliance Center](https://protection.office.com)zu **Reports** \> **Dashboard** \> - **Spam Erkennungen**.</span><span class="sxs-lookup"><span data-stu-id="ca539-189">To view this report, in the [Security &amp; Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** \> **Spam Detections**.</span></span>
  
![Um diesen Bericht anzuzeigen, wechseln Sie im &amp; Security Compliance Center zu Berichte \> Dashboard \> EoP Spam Erkennungen](../media/028cff3c-79ce-4ec0-8f0f-ec32ac28243a.png)
  
<span data-ttu-id="ca539-191">Wenn Sie den Mauszeiger über einen Tag im Diagramm bewegen, können Sie sehen, wie viele Elemente an diesem Tag blockiert wurden, und wie diese Elemente kategorisiert werden.</span><span class="sxs-lookup"><span data-stu-id="ca539-191">When you hover over a day in the chart, you can see how many items were blocked that day, as well as how those items are categorized.</span></span> <span data-ttu-id="ca539-192">Beispielsweise können Sie sehen, wie viele Spamnachrichten gefiltert wurden und wie viele Elemente von einer blockierten Internetprotokoll (IP) Adresse stammen.</span><span class="sxs-lookup"><span data-stu-id="ca539-192">For example, you can see how many spam messages were filtered, and how many items came from a blocked Internet Protocol (IP) address.</span></span>
  
<span data-ttu-id="ca539-193">Klicken (oder tippen) Sie auf den Bericht, um ihn in einem neuen Browserfenster zu öffnen, in dem Sie eine detailliertere Ansicht des Berichts erhalten können.</span><span class="sxs-lookup"><span data-stu-id="ca539-193">Click (or tap) the report to open it in a new browser window, where you can get a more detailed view of the report.</span></span>
  
![Der Spam Erkennungs Bericht gibt an, wie viele Spamnachrichten blockiert oder herausgefiltert wurden.](../media/370ec67d-eb30-4863-bfcf-68a41be02295.png)
  
<span data-ttu-id="ca539-195">Unter dem Diagramm sehen Sie eine Liste mit Spam Elementen, die erkannt wurden.</span><span class="sxs-lookup"><span data-stu-id="ca539-195">Below the chart, you'll see a list of spam items that were detected.</span></span> <span data-ttu-id="ca539-196">Wählen Sie ein Element aus, um zusätzliche Informationen anzuzeigen, beispielsweise, ob das Spam Element eingehend oder ausgehend war, seine Nachrichten ID und seinen Empfänger.</span><span class="sxs-lookup"><span data-stu-id="ca539-196">Select an item to view additional information, such as whether the spam item was inbound or outbound, its message ID, and its recipient.</span></span> <span data-ttu-id="ca539-197">Weitere Informationen zum Antispamschutz finden Sie unter [Office 365 Email Anti-Spam Protection](https://docs.microsoft.com/microsoft-365/security/office-365-security/anti-spam-and-anti-malware-protection).</span><span class="sxs-lookup"><span data-stu-id="ca539-197">To learn more about anti-spam protection, see [Office 365 email anti-spam protection](https://docs.microsoft.com/microsoft-365/security/office-365-security/anti-spam-and-anti-malware-protection).</span></span>
  
## <a name="sent-and-received-email-report"></a><span data-ttu-id="ca539-198">Gesendete und empfangene e-Mail-Berichte</span><span class="sxs-lookup"><span data-stu-id="ca539-198">Sent and received email report</span></span>

<span data-ttu-id="ca539-199">Der Bericht **gesendeten und empfangenen e-Mail-Nachrichten** ist ein intelligenter Bericht, in dem Informationen zu eingehenden und ausgehenden e-Mails angezeigt werden, einschließlich Spamerkennungen, Schadsoftware und als "gut" identifizierte e-Mails.</span><span class="sxs-lookup"><span data-stu-id="ca539-199">The **Sent and received email** report is a smart report that shows information about incoming and outgoing email, including spam detections, malware, and email identified as "good."</span></span> 
  
<span data-ttu-id="ca539-200">Um diesen Bericht anzuzeigen, wechseln Sie [im &amp; Security Compliance Center](https://protection.office.com)zu **Berichte** \> - **Dashboard** \> **gesendete und empfangene e-Mails**.</span><span class="sxs-lookup"><span data-stu-id="ca539-200">To view this report, in the [Security &amp; Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** \> **Sent and received email**.</span></span>
  
![Um diesen Bericht anzuzeigen, wechseln Sie im &amp; Security Compliance Center zu Berichte \> -Dashboard \> gesendete und empfangene e-Mails](../media/0e710ed0-1b0e-4dac-8796-94a01a710f3a.png)
  
<span data-ttu-id="ca539-202">Wenn Sie den Mauszeiger über einen Tag im Diagramm bewegen, können Sie sehen, wie viele Nachrichten eingingen und wie diese Nachrichten kategorisiert werden.</span><span class="sxs-lookup"><span data-stu-id="ca539-202">When you hover over a day in the chart, you can see how many messages came in, and how those messages are categorized.</span></span> <span data-ttu-id="ca539-203">Beispielsweise können Sie sehen, wie viele Nachrichten erkannt wurden, die Malware enthalten und wie viele als Spam identifiziert wurden.</span><span class="sxs-lookup"><span data-stu-id="ca539-203">For example, you can see how many messages were detected as containing malware, and how many were identified as spam.</span></span>
  
<span data-ttu-id="ca539-204">Klicken (oder tippen) Sie auf den Bericht, um ihn in einem neuen Browserfenster zu öffnen, in dem Sie eine detailliertere Ansicht des Berichts erhalten können.</span><span class="sxs-lookup"><span data-stu-id="ca539-204">Click (or tap) the report to open it in a new browser window, where you can get a more detailed view of the report.</span></span>
  
<span data-ttu-id="ca539-205">Sie können die **aufschlüsseln** nach Liste verwenden, um Informationen nach Typ oder Richtung anzuzeigen (ein-und ausgehende).</span><span class="sxs-lookup"><span data-stu-id="ca539-205">You can use the **Break down by** list to view information by type or by direction (incoming and outgoing).</span></span> 
  
![Verwenden der Aufschlüsselung nach Liste zum Anzeigen von Informationen nach Typ oder Richtung](../media/a5b30c94-d75f-4bfc-851a-cb155685b177.png)
  
<span data-ttu-id="ca539-207">Unter dem Diagramm sehen Sie eine Liste mit e-Mail-Kategorien wie **GoodMail**, **SpamContentFiltered**usw.</span><span class="sxs-lookup"><span data-stu-id="ca539-207">Below the chart, you'll see a list of email categories, such as **GoodMail**, **SpamContentFiltered**, and so on.</span></span> <span data-ttu-id="ca539-208">Wählen Sie eine Kategorie aus, um zusätzliche Informationen anzuzeigen, wie beispielsweise Aktionen, die für Schadsoftware ergriffen wurden, und ob e-Mails eingehende oder ausgehende e-Mail waren.</span><span class="sxs-lookup"><span data-stu-id="ca539-208">Select a category to view additional information, such as actions that were taken for malware, and whether email was incoming or outgoing.</span></span>
  
![In diesem Bericht erfahren Sie mehr über Antischadsoftware, Antispam und andere Nachrichten Erkennungen.](../media/9ea4b606-f27a-46ee-97a7-be018e2b839c.png)

<span data-ttu-id="ca539-210">Weitere Informationen zu e-Mail-Informationen finden Sie unter Nachrichten [Fluss Intelligence in Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/mail-flow-intelligence-in-office-365).</span><span class="sxs-lookup"><span data-stu-id="ca539-210">To learn more about email intelligence, see [Mail flow intelligence in Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/mail-flow-intelligence-in-office-365).</span></span>
  
## <a name="user-reported-messages-report"></a><span data-ttu-id="ca539-211">Bericht über vom Benutzer gemeldete Nachrichten</span><span class="sxs-lookup"><span data-stu-id="ca539-211">User-reported messages report</span></span>

<span data-ttu-id="ca539-212">Der Bericht "vom **Benutzer gemeldete Nachrichten** " zeigt Informationen über e-Mail-Nachrichten an, die von Benutzern mithilfe des [Berichtsnachrichten-Add-ins](https://docs.microsoft.com/microsoft-365/security/office-365-security/enable-the-report-message-add-in)als Junk-oder Phishing-Versuche oder als gute e-Mail gemeldet wurden.</span><span class="sxs-lookup"><span data-stu-id="ca539-212">The **User-reported messages** report shows information about email messages that users have reported as junk, phishing attempts, or good mail by using the [Report Message add-in](https://docs.microsoft.com/microsoft-365/security/office-365-security/enable-the-report-message-add-in).</span></span>
  
<span data-ttu-id="ca539-213">Für jede Nachricht stehen Details zur Verfügung, einschließlich des Zustellungs Grundes, einer solchen Spam Richtlinienausnahme oder Nachrichtenfluss Regel, die für Ihre Organisation konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="ca539-213">Details are available for each message, including the delivery reason, such a spam policy exception or mail flow rule configured for your organization.</span></span> <span data-ttu-id="ca539-214">Um Details anzuzeigen, wählen Sie ein Element in der Liste Benutzer Berichte aus, und zeigen Sie dann die Informationen auf den Registerkarten **Zusammenfassung** und **Details** an.</span><span class="sxs-lookup"><span data-stu-id="ca539-214">To view details, select an item in the user-reports list, and then view the information on the **Summary** and **Details** tabs.</span></span> 
  
![Der Bericht über Benutzer Berichte zeigt Nachrichten an, die als Junk-, nicht als Junk-oder Phishing-Versuche bezeichnet werden.](../media/ad5e9a3d-b833-419c-bcc9-3425d9604ead.png)
  
<span data-ttu-id="ca539-216">Führen Sie einen der folgenden Schritte aus, um diesen Bericht im [ &amp; Security Compliance Center](https://protection.office.com)anzuzeigen:</span><span class="sxs-lookup"><span data-stu-id="ca539-216">To view this report, in the [Security &amp; Compliance Center](https://protection.office.com), do one of the following:</span></span>
  
- <span data-ttu-id="ca539-217">Wechseln Sie zu **Threat Management** \> **Dashboard** \> von **Benutzern gemeldete Nachrichten**.</span><span class="sxs-lookup"><span data-stu-id="ca539-217">Go to **Threat management** \> **Dashboard** \> **User-reported messages**.</span></span>
    
- <span data-ttu-id="ca539-218">Wechseln Sie zu **Threat Management** \> **überprüfen** \> von **Benutzern gemeldeten Nachrichten**.</span><span class="sxs-lookup"><span data-stu-id="ca539-218">Go to **Threat management** \> **Review** \> **User-reported messages**.</span></span>
    
![Wählen Sie im &amp; Security Compliance Center die Option Threat \> Management \> Review User gemeldete Nachrichten aus.](../media/e372c57c-1414-4616-957b-bc933b8c8711.png)
  
> [!IMPORTANT]
> <span data-ttu-id="ca539-220">Damit der Bericht über vom Benutzer gemeldete Nachrichten ordnungsgemäß funktioniert, **muss die Überwachungsprotokollierung** für Ihre Office 365 Umgebung aktiviert sein.</span><span class="sxs-lookup"><span data-stu-id="ca539-220">In order for the User-reported messages report to work correctly, **audit logging must be turned on** for your Office 365 environment.</span></span> <span data-ttu-id="ca539-221">Dies erfolgt in der Regel durch eine Person, der die Rolle "Überwachungsprotokolle" in Exchange Online zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="ca539-221">This is typically done by someone who has the Audit Logs role assigned in Exchange Online.</span></span> <span data-ttu-id="ca539-222">Weitere Informationen finden Sie unter [Aktivieren oder Deaktivieren von Office 365 Überwachungsprotokoll Suche](https://docs.microsoft.com/microsoft-365/compliance/turn-audit-log-search-on-or-off).</span><span class="sxs-lookup"><span data-stu-id="ca539-222">For more information, see [Turn Office 365 audit log search on or off](https://docs.microsoft.com/microsoft-365/compliance/turn-audit-log-search-on-or-off).</span></span> 
  
## <a name="what-permissions-are-needed-to-view-these-reports"></a><span data-ttu-id="ca539-223">Welche Berechtigungen sind zum Anzeigen dieser Berichte erforderlich?</span><span class="sxs-lookup"><span data-stu-id="ca539-223">What permissions are needed to view these reports?</span></span>

<span data-ttu-id="ca539-224">Damit Sie die in diesem Artikel beschriebenen Berichte anzeigen und verwenden können, **muss Ihnen eine entsprechende Rolle sowohl für das Security &amp; Compliance Center als auch für das Exchange Admin Center zugewiesen sein**.</span><span class="sxs-lookup"><span data-stu-id="ca539-224">In order to view and use the reports described in this article, **you must have an appropriate role assigned for both the Security &amp; Compliance Center and the Exchange admin center**.</span></span>

- <span data-ttu-id="ca539-225">Für das Security &amp; Compliance Center müssen Sie eine der folgenden Rollen zugewiesen haben:</span><span class="sxs-lookup"><span data-stu-id="ca539-225">For the Security &amp; Compliance Center, you must have one of the following roles assigned:</span></span>
    - <span data-ttu-id="ca539-226">Organisationsverwaltung</span><span class="sxs-lookup"><span data-stu-id="ca539-226">Organization Management</span></span>
    - <span data-ttu-id="ca539-227">Sicherheits Administrator (Dies kann im Azure Active Directory Admin Center zugewiesen werden ([https://aad.portal.azure.com](https://aad.portal.azure.com))</span><span class="sxs-lookup"><span data-stu-id="ca539-227">Security Administrator (this can be assigned in the Azure Active Directory admin center ([https://aad.portal.azure.com](https://aad.portal.azure.com))</span></span>
    - <span data-ttu-id="ca539-228">Sicherheitsleseberechtigter</span><span class="sxs-lookup"><span data-stu-id="ca539-228">Security Reader</span></span>

- <span data-ttu-id="ca539-229">Für Exchange Online müssen Sie eine der folgenden Rollen entweder in der Exchange-Verwaltungskonsole ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp)) oder mit PowerShell-Cmdlets zugewiesen haben (siehe [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps)):</span><span class="sxs-lookup"><span data-stu-id="ca539-229">For Exchange Online, you must have one of the following roles assigned in either the Exchange admin center ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp)) or with PowerShell cmdlets (See [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps)):</span></span>
    - <span data-ttu-id="ca539-230">Organisationsverwaltung</span><span class="sxs-lookup"><span data-stu-id="ca539-230">Organization Management</span></span>
    - <span data-ttu-id="ca539-231">Organisationsverwaltung mit Leserechten</span><span class="sxs-lookup"><span data-stu-id="ca539-231">View-only Organization Management</span></span>
    - <span data-ttu-id="ca539-232">Rolle „Empfänger mit Leserechten“</span><span class="sxs-lookup"><span data-stu-id="ca539-232">View-Only Recipients role</span></span>
    - <span data-ttu-id="ca539-233">Verwaltung der Richtlinientreue</span><span class="sxs-lookup"><span data-stu-id="ca539-233">Compliance Management</span></span>

<span data-ttu-id="ca539-234">Weitere Informationen hierzu finden Sie in den folgenden Ressourcen:</span><span class="sxs-lookup"><span data-stu-id="ca539-234">To learn more, see the following resources:</span></span>

- [<span data-ttu-id="ca539-235">Berechtigungen im Office 365 Security &amp; Compliance Center</span><span class="sxs-lookup"><span data-stu-id="ca539-235">Permissions in the Office 365 Security &amp; Compliance Center</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center)

- [<span data-ttu-id="ca539-236">Featureberechtigungen in Exchange Online</span><span class="sxs-lookup"><span data-stu-id="ca539-236">Feature permissions in Exchange Online</span></span>](https://docs.microsoft.com/exchange/permissions-exo/feature-permissions)
   
   
## <a name="what-if-the-reports-arent-showing-data"></a><span data-ttu-id="ca539-237">Was geschieht, wenn die Berichte keine Daten anzeigen?</span><span class="sxs-lookup"><span data-stu-id="ca539-237">What if the reports aren't showing data?</span></span>

<span data-ttu-id="ca539-238">Wenn Sie keine Daten in ihren Berichten sehen, überprüfen Sie, ob Ihre Richtlinien ordnungsgemäß eingerichtet sind.</span><span class="sxs-lookup"><span data-stu-id="ca539-238">If you are not seeing data in your reports, double-check that your policies are set up correctly.</span></span> <span data-ttu-id="ca539-239">Weitere Informationen finden Sie unter [Protect Against Threats in Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats).</span><span class="sxs-lookup"><span data-stu-id="ca539-239">To learn more, see [Protect against threats in Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats).</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="ca539-240">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="ca539-240">Related topics</span></span>

[<span data-ttu-id="ca539-241">Antispamschutz für Office 365-E-Mails</span><span class="sxs-lookup"><span data-stu-id="ca539-241">Office 365 Email Anti-Spam Protection</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/anti-spam-and-anti-malware-protection)
  
[<span data-ttu-id="ca539-242">Berichte und Einblicke im Office 365 &amp; Security Compliance Center</span><span class="sxs-lookup"><span data-stu-id="ca539-242">Reports and insights in the Office 365 Security &amp; Compliance Center</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/reports-and-insights-in-security-and-compliance)
  
[<span data-ttu-id="ca539-243">Erstellen eines Zeitplans für einen Bericht im &amp; Security Compliance Center</span><span class="sxs-lookup"><span data-stu-id="ca539-243">Create a schedule for a report in the Security &amp; Compliance Center</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/create-a-schedule-for-a-report)
  
[<span data-ttu-id="ca539-244">Einrichten und Herunterladen eines benutzerdefinierten Berichts im Security &amp; Compliance Center</span><span class="sxs-lookup"><span data-stu-id="ca539-244">Set up and download a custom report in the Security &amp; Compliance Center</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/set-up-and-download-a-custom-report)
  

