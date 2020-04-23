---
title: Anwenden des Schutzes auf personenbezogene Daten
f1.keywords:
- NOCSH
ms.author: bcarter
author: brendacarter
manager: laurawi
ms.date: 02/07/2018
audience: ITPro
ms.topic: overview
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- GDPR
- M365-security-compliance
- SPO_Content
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
description: Hier erfahren Sie, wie DLP-Richtlinien (Data Loss Prevention, Verhinderung von Datenverlust) zum Schutz personenbezogener Daten in Microsoft 365 verwendet werden.
ms.openlocfilehash: 54bfdd27f5c18d6c145b1e9f13c5e92c1b322048
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/21/2020
ms.locfileid: "43634273"
---
# <a name="apply-protection-to-personal-data"></a><span data-ttu-id="fc6ef-103">Anwenden des Schutzes auf personenbezogene Daten</span><span class="sxs-lookup"><span data-stu-id="fc6ef-103">Apply protection to personal data</span></span>

<span data-ttu-id="fc6ef-104">Zum Schutz von personenbezogenen Informationen in Microsoft 365 gehören Funktionen zur Verhinderung von Datenverlust.</span><span class="sxs-lookup"><span data-stu-id="fc6ef-104">Protection of personal information in Microsoft 365 includes using data loss prevention capabilities.</span></span> <span data-ttu-id="fc6ef-105">Mithilfe von Richtlinien zur Verhinderung von Datenverlust (Data Loss Prevention, DLP) im Compliance Center können Sie vertrauliche Informationen in Microsoft 365 identifizieren, überwachen und automatisch schützen lassen.</span><span class="sxs-lookup"><span data-stu-id="fc6ef-105">With data loss prevention (DLP) policies in the compliance center, you can identify, monitor, and automatically protect sensitive information across Microsoft 365.</span></span>

<span data-ttu-id="fc6ef-p102">In diesem Thema wird die Verwendung von DLP zum Schutz personenbezogener Daten erläutert. Dieses Thema beinhaltet auch andere Schutzfunktionen, die verwendet werden können, um die Einhaltung der DSGVO zu gewährleisten, u. a. Festlegen von Berechtigungen in SharePoint-Bibliotheken und Verwenden von Gerätezugriffsrichtlinien.</span><span class="sxs-lookup"><span data-stu-id="fc6ef-p102">This topic describes how to use DLP to protect personal data. This topic also lists other protection capabilities that can be used to achieve GDPR compliance, including setting permissions in SharePoint libraries and using device access policies.</span></span>

## <a name="apply-protection-using-data-loss-prevention-in-microsoft-365"></a><span data-ttu-id="fc6ef-108">Anwenden des Schutzes mithilfe von DLP in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="fc6ef-108">Apply protection using data loss prevention in Microsoft 365</span></span>

<span data-ttu-id="fc6ef-109">Mit DLP können Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="fc6ef-109">With DLP, you can:</span></span>

-   <span data-ttu-id="fc6ef-110">Vertrauliche Daten über viele Speicherorte hinweg identifizieren</span><span class="sxs-lookup"><span data-stu-id="fc6ef-110">Identify sensitive information across many locations.</span></span>

-   <span data-ttu-id="fc6ef-111">Verhindern, dass vertrauliche Informationen unbeabsichtigt freigegeben werden</span><span class="sxs-lookup"><span data-stu-id="fc6ef-111">Prevent accidental sharing of sensitive information.</span></span>

-   <span data-ttu-id="fc6ef-112">Benutzern dabei helfen, zu erfahren, wie sie die Anforderungen erfüllen, ohne dabei ihren Arbeitsablauf unterbrechen zu müssen</span><span class="sxs-lookup"><span data-stu-id="fc6ef-112">Help users learn how to stay compliant without interrupting their workflow.</span></span>

-   <span data-ttu-id="fc6ef-113">Anzeigen von DLP-Berichten mit Inhalten, die mit den DLP-Richtlinien Ihrer Organisation übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="fc6ef-113">View DLP reports showing content that matches your organization's DLP policies.</span></span>

<span data-ttu-id="fc6ef-114">Weitere Informationen finden Sie unter [Übersicht über die Richtlinien zur Verhinderung von Datenverlust](https://support.office.com/article/Overview-of-data-loss-prevention-policies-1966b2a7-d1e2-4d92-ab61-42efbb137f5e).</span><span class="sxs-lookup"><span data-stu-id="fc6ef-114">For more information, see [Overview of data loss prevention policies](https://support.office.com/article/Overview-of-data-loss-prevention-policies-1966b2a7-d1e2-4d92-ab61-42efbb137f5e).</span></span>

![Optionen zum Erstellen einer DLP-Richtlinie](../media/Apply-protection-to-personal-data-in-Office-365-image1.png)

<span data-ttu-id="fc6ef-116">Diese Abbildung zeigt die Optionen für das Erstellen einer DLP-Richtlinie:</span><span class="sxs-lookup"><span data-stu-id="fc6ef-116">This illustration shows the options for creating a DLP policy:</span></span>

-   <span data-ttu-id="fc6ef-p103">Wählen Sie Schutz, den Sie anwenden möchten. Schutz kann Folgendes umfassen:</span><span class="sxs-lookup"><span data-stu-id="fc6ef-p103">Choose the protection to apply. Protection can include:</span></span>

    -   <span data-ttu-id="fc6ef-119">Richtlinientipps für Benutzer</span><span class="sxs-lookup"><span data-stu-id="fc6ef-119">Policy tips for users</span></span>

    -   <span data-ttu-id="fc6ef-120">E-Mail-Bericht für Administratoren</span><span class="sxs-lookup"><span data-stu-id="fc6ef-120">Email report for admins</span></span>

    -   <span data-ttu-id="fc6ef-121">Verhindern der externen und/oder internen Freigabe von Daten</span><span class="sxs-lookup"><span data-stu-id="fc6ef-121">Prevent sharing externally, internally, or both</span></span>

-   <span data-ttu-id="fc6ef-p104">Wählen Sie die Kriterien zum Anwenden des Schutzes. Wenden Sie den Schutz auf Dokumente mit diesem Inhaltstyp an: Sie können die Richtlinie für die Verwendung vertraulicher Informationstypen und/oder -bezeichnungen verwenden.</span><span class="sxs-lookup"><span data-stu-id="fc6ef-p104">Choose the criteria for applying the protection. Apply the protection to documents with this type of content: you can configure the policy to use sensitive information types and/or labels.</span></span>

### <a name="using-dlp-for-gdpr-compliance"></a><span data-ttu-id="fc6ef-124">Verwenden von DLP für die Einhaltung der DSGVO</span><span class="sxs-lookup"><span data-stu-id="fc6ef-124">Using DLP for GDPR compliance</span></span>

<span data-ttu-id="fc6ef-p105">Einer der primären Verwendungszwecke von Microsoft 365 DLP besteht darin, personenbezogene Daten, die Personen innerhalb der EU betreffen, in Ihrer Microsoft 365-Umgebung zu identifizieren. Microsoft 365 DLP kann Ihren Complianceteams melden, wo personenbezogene Informationen in SharePoint Online und OneDrive for Business gespeichert wurden oder wenn Benutzer E-Mails senden, die personenbezogene Informationen enthalten. DLP kann auch Richtlinientipps für Ihre Mitarbeiter bei der Arbeit mit personenbezogenen Informationen bereitstellen, die EU-Bürger betreffen.</span><span class="sxs-lookup"><span data-stu-id="fc6ef-p105">One of the primary uses of Microsoft 365 DLP is to identify personal data related to EU data subjects in your Microsoft 365 environment. Microsoft 365 DLP can notify your compliance teams of where personal information is stored in SharePoint Online and OneDrive for Business, or when users send email containing personal information. DLP can also provide policy tips to your employees when working with personal information related to EU residents.</span></span>

<span data-ttu-id="fc6ef-p106">Die Aufklärung und Bewusstseinsbildung in Bezug auf Daten von EU-Bürgern, die in Ihrer Umgebung gespeichert werden, sowie den Umgang Ihrer Mitarbeiter damit stellen eine Ebene des Informationsschutzes unter Verwendung von Office 365 DLP dar. In vielen Fällen benötigen Mitarbeiter, die bereits Zugriff auf diese Informationsart haben, diesen Zugriff für ihre täglichen Aufgaben. Für die Erzwingung von DLP-Richtlinien zur Einhaltung der DSGVO ist nicht unbedingt eine Einschränkung des Zugriffs erforderlich.</span><span class="sxs-lookup"><span data-stu-id="fc6ef-p106">Educating and raising awareness to where EU resident data is stored in your environment and how your employees are permitted to handle it represents one level of information protection using Microsoft 365 DLP. Often, employees who already have access to this type of information require this access to do their day to day work. Enforcing DLP policies to help comply with GDPR may not require restricting access.</span></span>

<span data-ttu-id="fc6ef-p107">Jedoch beinhaltet die Einhaltung der DSGVO in der Regel eine Risikobewertung der Organisation, sowohl aus rechtlicher Sicht als auch aus der Sicht der Informationssicherheit, die Identifizierung von Typen und Speicherorten von personenbezogenen Informationen, sowie, ob es eine Rechtsgrundlage für die Speicherung und Verarbeitung dieser Informationen gibt. Basierend auf dieser Bewertung, kann es für die Implementierung von Richtlinien zum Schutz der Organisation und zur Einhaltung der DSGVO erforderlich sein, den Zugriff von Mitarbeitern auf Dokumente mit personenbezogenen Daten zu entfernen, die EU-Bürger betreffen. In Fällen, in denen weiterer Schutz erforderlich ist, kann zusätzlicher DLP-Schutz konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="fc6ef-p107">However, complying with GDPR typically involves a risk-based assessment of the organization from both a legal and information security perspective, identification of what type and where personal information is stored, as well as if there's a legal justification to store and process that information. Based on this assessment, implementing policies to protect the organization and comply with GDPR might require removing access for employees to documents that contain personal information for EU data subjects. In cases where further protection is required, additional DLP protection can be configured.</span></span>

<span data-ttu-id="fc6ef-p108">Die folgende Tabelle enthält drei Konfigurationen des zunehmenden Schutzes mithilfe von DLP. Die erste Konfiguration, Bewusstsein, kann als Ausgangspunkt und Mindestmaß an Schutz für die DSGVO verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="fc6ef-p108">The following table lists three configurations of increasing protection using DLP. The first configuration, awareness, can be used as a starting point and minimum level of protection for GDPR.</span></span>

### <a name="example-protection-levels-that-can-be-configured-with-dlp-policies-and-used-for-gdpr-compliance"></a><span data-ttu-id="fc6ef-136">Beispielschutzebenen, die mit DLP-Richtlinien konfiguriert und zur Einhaltung der DSGVO verwendet werden</span><span class="sxs-lookup"><span data-stu-id="fc6ef-136">Example protection levels that can be configured with DLP policies and used for GDPR compliance</span></span>

<table>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="fc6ef-137"><strong>Schutzebene</strong></span><span class="sxs-lookup"><span data-stu-id="fc6ef-137"><strong>Protection level</strong></span></span></th>
<th align="left"><span data-ttu-id="fc6ef-138"><strong>DLP-Konfiguration für Dokumente mit personenbezogenen Informationen im Zusammenhang mit EU-Bürgern</strong></span><span class="sxs-lookup"><span data-stu-id="fc6ef-138"><strong>DLP configuration for documents with personal information related to EU data subjects</strong></span></span></th>
<th align="left"><span data-ttu-id="fc6ef-139"><strong>Vorteile und Risiken</strong></span><span class="sxs-lookup"><span data-stu-id="fc6ef-139"><strong>Benefits and risks</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><span data-ttu-id="fc6ef-140">Bewusstsein</span><span class="sxs-lookup"><span data-stu-id="fc6ef-140">Awareness</span></span></td>
<td align="left"><p><span data-ttu-id="fc6ef-141">Senden von E-Mail-Benachrichtigungen an Complianceteams, wenn diese Daten in Dokumenten in SharePoint Online und OneDrive for Business erkannt werden.</span><span class="sxs-lookup"><span data-stu-id="fc6ef-141">Send email notifications to compliance teams when this data is found in documents in SharePoint Online and OneDrive for Business.</span></span></p>
<p><span data-ttu-id="fc6ef-142">Anpassen und Anzeigen von Richtlinientipps für Mitarbeiter in SharePoint und OneDrive for Business, wenn auf Dokumente mit diesen Daten zugegriffen wird.</span><span class="sxs-lookup"><span data-stu-id="fc6ef-142">Customize and display Policy Tips to employees in SharePoint and OneDrive for Business when accessing documents containing this data.</span></span></p>
<p><span data-ttu-id="fc6ef-143">Erkennen und melden, wenn diese Daten freigegeben werden.</span><span class="sxs-lookup"><span data-stu-id="fc6ef-143">Detect and report when this data is being shared.</span></span></p></td>
<td align="left"><p><span data-ttu-id="fc6ef-144">Bewusstseinsbildung bei Complianceteams und Mitarbeitern im Hinblick darauf, wo diese Daten gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="fc6ef-144">Raise awareness with compliance teams and employees about where this data is stored.</span></span></p>
<p><span data-ttu-id="fc6ef-145">Aufklärung von Mitarbeitern im Hinblick auf die Unternehmensrichtlinie zur Verarbeitung von Dokumenten, die diese Daten enthalten.</span><span class="sxs-lookup"><span data-stu-id="fc6ef-145">Educate employees on corporate policy for handling documents containing this data.</span></span></p>
<p><span data-ttu-id="fc6ef-146">Verhindert nicht, dass Mitarbeiter diese Daten intern oder extern freigeben.</span><span class="sxs-lookup"><span data-stu-id="fc6ef-146">Does not prevent employees from sharing this data internally or externally.</span></span></p>
<p><span data-ttu-id="fc6ef-147">Sie können DLP-Berichte für freigegebene Daten überprüfen und entscheiden, ob Sie den Schutz erhöhen müssen.</span><span class="sxs-lookup"><span data-stu-id="fc6ef-147">You can review DLP reports for shared data and decide if you need to increase the protection.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="fc6ef-148">Verhindern der externen Freigabe</span><span class="sxs-lookup"><span data-stu-id="fc6ef-148">Prevent external sharing</span></span></td>
<td align="left"><p><span data-ttu-id="fc6ef-149">Beschränken des Zugriffs auf Dokumente, die diese Daten in SharePoint Online und OneDrive for Business enthalten, wenn diese Inhalte für externe Benutzer freigegeben werden.</span><span class="sxs-lookup"><span data-stu-id="fc6ef-149">Restrict access to documents that contain this data in SharePoint Online and OneDrive for Business when that content is shared with external users.</span></span></p>
<p><span data-ttu-id="fc6ef-150">Verhindern, dass E-Mails mit Dokumenten mit diesen Daten an externe Empfänger gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="fc6ef-150">Prevent sending emails with documents that contain this data to external recipients.</span></span></p>
<p><span data-ttu-id="fc6ef-151">Erkennen und melden, wenn diese Daten freigegeben werden.</span><span class="sxs-lookup"><span data-stu-id="fc6ef-151">Detect and report when this data is being shared.</span></span></p></td>
<td align="left"><p><span data-ttu-id="fc6ef-152">Verhindert die externe Freigabe von Daten und ermöglicht Mitarbeitern, intern mit diesen Daten zu arbeiten.</span><span class="sxs-lookup"><span data-stu-id="fc6ef-152">Prevents external sharing of this data while allowing for employees to work with this data internally.</span></span></p>
<p><span data-ttu-id="fc6ef-153">Sie können DLP-Berichte für intern freigegebene Daten überprüfen und entscheiden, ob Sie den Schutz erhöhen müssen.</span><span class="sxs-lookup"><span data-stu-id="fc6ef-153">You can review DLP reports for internally shared data and decide if you need to increase this protection.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="fc6ef-154">Verhindern der internen und externen Freigabe</span><span class="sxs-lookup"><span data-stu-id="fc6ef-154">Prevent internal and external sharing</span></span></td>
<td align="left"><p><span data-ttu-id="fc6ef-155">Beschränken des Zugriffs auf Dokumente, die diese Daten in SharePoint Online und OneDrive for Business enthalten, wenn diese Inhalte intern oder extern freigegeben werden.</span><span class="sxs-lookup"><span data-stu-id="fc6ef-155">Restrict access to documents that contain this data in SharePoint Online and OneDrive for Business when that content is shared internally or externally.</span></span></p>
<p><span data-ttu-id="fc6ef-156">Verhindern, dass E-Mails mit diesen Daten an interne und externe Empfänger gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="fc6ef-156">Prevent sending emails that contain this data to both internal and external recipients.</span></span></p></td>
<td align="left"><p><span data-ttu-id="fc6ef-157">Verhindern der internen und externen Freigabe dieser Daten.</span><span class="sxs-lookup"><span data-stu-id="fc6ef-157">Prevents internal and external sharing of this data.</span></span></p>
<p><span data-ttu-id="fc6ef-158">Mitarbeiter können möglicherweise nicht die Aufgaben ausführen, für die die Arbeit mit diesen Daten erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="fc6ef-158">Employees might not be able to complete tasks that require working with this data.</span></span></p>
<p><span data-ttu-id="fc6ef-159">Sie können DLP-Berichte für intern oder extern freigegebene Daten überprüfen und entscheiden, ob ein Training für Endbenutzer erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="fc6ef-159">You can review DLP reports for internally or externally shared data and decide if end-user training is needed.</span></span></p></td>
</tr>
</tbody>
</table>

<span data-ttu-id="fc6ef-p109">Hinweis: Mit zunehmender Schutzebene nimmt bei Benutzern die Möglichkeit ab, auf Informationen zuzugreifen, und könnte potenziell ihre Produktivität oder die Ausführung der täglichen Aufgaben beeinträchtigen. Die Erhöhung der Schutzebenen durch die Implementierung von Richtlinien, die sich auf Mitarbeiter auswirken, wird in der Regel von einer Endbenutzerschulung und Schulung von Benutzern zu neuen Sicherheitsrichtlinien und Vorgehensweisen begleitet, damit diese in einer sicheren Umgebung weiterhin produktiv sein können.</span><span class="sxs-lookup"><span data-stu-id="fc6ef-p109">Note: As the levels of protection increase, the ability of users to access information will decrease in some cases, and could potentially impact their productivity or ability to complete day to day tasks. Increasing protection levels by implementing policies that impact employees is typically accompanied by end-user training, educating users on new security policies and procedures to help them continue to be productive in a more secure environment.</span></span>

### <a name="example-dlp-policy-for-gdpr--awareness"></a><span data-ttu-id="fc6ef-162">Beispiel für DLP-Richtlinie für DSGVO – Bewusstsein</span><span class="sxs-lookup"><span data-stu-id="fc6ef-162">Example DLP policy for GDPR — Awareness</span></span> 

<span data-ttu-id="fc6ef-163">Name: Bewusstsein für personenbezogene Daten, die der DSGVO unterliegen.</span><span class="sxs-lookup"><span data-stu-id="fc6ef-163">Name: Awareness for personal data that is subject to GDPR.</span></span>

<span data-ttu-id="fc6ef-164">Beschreibung: Anzeigen von Richtlinientipps für Mitarbeiter, Benachrichtigen von Complianceteams, wenn diese Daten in Dokumenten in SharePoint Online und OneDrive for Business gefunden werden, Ermitteln und Melden, wenn diese Daten außerhalb Ihrer Organisation freigegeben werden.</span><span class="sxs-lookup"><span data-stu-id="fc6ef-164">Description: Display policy tips to employees, notify compliance teams when this data is found in documents in SharePoint Online and OneDrive for Business, detect and report when this data is being shared outside your organization.</span></span>

<table>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="fc6ef-165"><strong>Steuerelement</strong></span><span class="sxs-lookup"><span data-stu-id="fc6ef-165"><strong>Control</strong></span></span></th>
<th align="left"><span data-ttu-id="fc6ef-166"><strong>Einstellungen</strong></span><span class="sxs-lookup"><span data-stu-id="fc6ef-166"><strong>Settings</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><span data-ttu-id="fc6ef-167">Die zu schützenden Informationen auswählen</span><span class="sxs-lookup"><span data-stu-id="fc6ef-167">Choose information to protect</span></span></td>
<td align="left"><span data-ttu-id="fc6ef-168">Wählen Sie eine benutzerdefinierte Richtlinienvorlage.</span><span class="sxs-lookup"><span data-stu-id="fc6ef-168">Select a Custom policy template.</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="fc6ef-169">Standorte</span><span class="sxs-lookup"><span data-stu-id="fc6ef-169">Locations</span></span></td>
<td align="left"><span data-ttu-id="fc6ef-170">Alle Speicherorte in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="fc6ef-170">All locations in Microsoft 365</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="fc6ef-171">Nach Inhalten suchen, die Folgendes enthalten</span><span class="sxs-lookup"><span data-stu-id="fc6ef-171">Find content that contains</span></span></td>
<td align="left"><span data-ttu-id="fc6ef-172">Klicken Sie auf „Bearbeiten“, und fügen Sie alle Typen von vertraulichen Informationen hinzu, die Sie für Ihre Umgebung zusammengestellt haben.</span><span class="sxs-lookup"><span data-stu-id="fc6ef-172">Click 'Edit' and add all the sensitive information types you curated for your environment.</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="fc6ef-173">Erkennen, wenn diese Inhalte freigegeben werden</span><span class="sxs-lookup"><span data-stu-id="fc6ef-173">Detect when this content is shared</span></span></td>
<td align="left"><span data-ttu-id="fc6ef-174">Aktivieren Sie dieses Kontrollkästchen, und wählen Sie „Für Personen außerhalb meiner Organisation“ aus.</span><span class="sxs-lookup"><span data-stu-id="fc6ef-174">Check this box and select 'with people outside my organization.'</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="fc6ef-175">Benutzer benachrichtigen, wenn Inhalte den Richtlinieneinstellungen entsprechen</span><span class="sxs-lookup"><span data-stu-id="fc6ef-175">Notify users when content matches the policy settings</span></span></td>
<td align="left"><p><span data-ttu-id="fc6ef-176">Aktivieren Sie dieses Kontrollkästchen („Richtlinientipps für Benutzer anzeigen und eine E-Mail-Benachrichtigung senden“.).</span><span class="sxs-lookup"><span data-stu-id="fc6ef-176">Check this box ("Show policy tips to users and send them an email notification.")</span></span></p>
<p><span data-ttu-id="fc6ef-p110">Klicken Sie auf „Tipp und E-Mail anpassen“, und aktualisieren Sie sie für Ihre Umgebung. Die standardmäßigen Benachrichtigungen finden Sie in diesem Artikel: <a href="https://support.office.com/article/Send-email-notifications-and-show-policy-tips-for-DLP-policies-87496bc5-9601-4473-8021-cb05c71369c1?ui=en-US&amp;rs=en-US&amp;ad=US">Senden von E-Mail-Benachrichtigungen und Anzeigen von Richtlinientipps für DLP-Richtlinien</a>.</span><span class="sxs-lookup"><span data-stu-id="fc6ef-p110">Click 'Customize the tip and email' and update these for your environment. See the default notifications in this article: <a href="https://support.office.com/article/Send-email-notifications-and-show-policy-tips-for-DLP-policies-87496bc5-9601-4473-8021-cb05c71369c1?ui=en-US&amp;rs=en-US&amp;ad=US">Send email notifications and show policy tips for DLP policies</a>.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="fc6ef-179">Erkennen, wenn eine bestimmte Menge personenbezogener Informationen auf einmal freigegeben wird</span><span class="sxs-lookup"><span data-stu-id="fc6ef-179">Detect when a specific amount of sensitive info is being shared at one time</span></span></td>
<td align="left"><p><span data-ttu-id="fc6ef-180">„Erkennen, wenn Inhalte, die freigegeben werden Folgendes enthalten: Mindestens ____ Instanzen desselben Typs vertraulicher Informationen“ – Legen Sie diese Einstellung auf „1“ fest.</span><span class="sxs-lookup"><span data-stu-id="fc6ef-180">'Detect when content that's being shared contains: At least ____ instances of the same sensitive info type' — Set this to 1.</span></span></p>
<p><span data-ttu-id="fc6ef-p111">„Schadensberichte per E-Mail senden“ – Aktivieren Sie dieses Kontrollkästchen. Klicken Sie auf „Auswählen, was der Bericht enthalten und an wen er gesendet werden soll“. Außerdem müssen Sie Ihr Complianceteam hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="fc6ef-p111">'Send incident reports in email' — check this box. Click 'Choose what to include in the report and who receives it.' Be sure to add your compliance team.</span></span></p>
<p><span data-ttu-id="fc6ef-184">„Zugriff auf Inhalte einschränken und die Richtlinie außer Kraft setzen“ – Deaktivieren Sie dieses Kontrollkästchen, um Benachrichtigungen zu vertraulichen Informationen zu erhalten, ohne dass Benutzer am Zugriff darauf gehindert werden.</span><span class="sxs-lookup"><span data-stu-id="fc6ef-184">'Restrict who can access the content and override the policy' — clear this checkbox to receive notifications about sensitive information without preventing users from access that information.</span></span></p></td>
</tr>
</tbody>
</table>

<span data-ttu-id="fc6ef-185">Alle Speicherorte umfasst:</span><span class="sxs-lookup"><span data-stu-id="fc6ef-185">All locations includes:</span></span>

- <span data-ttu-id="fc6ef-186">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="fc6ef-186">SharePoint Online</span></span>

- <span data-ttu-id="fc6ef-187">OneDrive for Business-Konten</span><span class="sxs-lookup"><span data-stu-id="fc6ef-187">OneDrive for Business accounts</span></span>

- <span data-ttu-id="fc6ef-188">Exchange-Postfächer</span><span class="sxs-lookup"><span data-stu-id="fc6ef-188">Exchange mailboxes</span></span>

<span data-ttu-id="fc6ef-189">Weil die Inhaltssuche das Testen vertraulicher Informationstypen mit E-Mails derzeit nicht unterstützt, sollten Sie ggf. separate Richtlinien für Exchange mit einer Teilmenge von vertraulichen Informationstypen in jeder Richtlinie erstellen und die Einführung dieser Richtlinien überwachen.</span><span class="sxs-lookup"><span data-stu-id="fc6ef-189">Because Content Search doesn't currently let you test sensitive information types with email, consider creating separate policies for Exchange with a subset of sensitive information types in each policy and monitoring the rollout of these policies.</span></span>

## <a name="additional-protection-you-can-apply-to-protect-personal-data-in-microsoft-365"></a><span data-ttu-id="fc6ef-190">Zusätzlicher Schutz, den Sie zum Schutz personenbezogener Daten in Microsoft 365 anwenden können</span><span class="sxs-lookup"><span data-stu-id="fc6ef-190">Additional protection you can apply to protect personal data in Microsoft 365</span></span>

<span data-ttu-id="fc6ef-p112">Mit vertraulichen Informationstypen, Bezeichnungen und DLP-Richtlinien können Dokumente mit bestimmten Daten erkannt und entsprechender Schutz für diese angewendet werden. Diese Schutzfunktionen hängen jedoch von geeigneten Berechtigungen ab, die für den Zugriff auf Daten festgelegt sind, von Benutzern mit Konten, die nicht kompromittiert sind, und Geräten, die ordnungsgemäß ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="fc6ef-p112">Sensitive information types, labels, and data loss protection policies help you identify documents containing specific data and apply protection. However, these protections depend on appropriate permissions being set for access to data, users with accounts that aren't compromised, and devices that are healthy.</span></span>

<span data-ttu-id="fc6ef-193">Die folgende Abbildung zeigt zusätzliche Schutzfunktionen im Detail, die Sie zum Schutz personenbezogener Daten anwenden können.</span><span class="sxs-lookup"><span data-stu-id="fc6ef-193">The following illustration details additional protection you can apply to protect access to personal data.</span></span>

![Zusätzlicher Schutz für geschützten Zugriff auf personenbezogene Daten](../media/Apply-protection-to-personal-data-in-Office-365-image2.png)

<span data-ttu-id="fc6ef-195">Für Zwecke der Barrierefreiheit enthält die folgende Tabelle die gleichen Informationen wie die Abbildung.</span><span class="sxs-lookup"><span data-stu-id="fc6ef-195">For accessibility, the following table provides the same information in the illustration.</span></span>

<table>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="fc6ef-196"><strong>Umfang des Schutzes</strong></span><span class="sxs-lookup"><span data-stu-id="fc6ef-196"><strong>Scope of protection</strong></span></span></th>
<th align="left"><span data-ttu-id="fc6ef-197"><strong>Funktionen</strong></span><span class="sxs-lookup"><span data-stu-id="fc6ef-197"><strong>Capabilities</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><span data-ttu-id="fc6ef-198">Schutz auf Dokument- und E-Mail-Ebene (darunter E-Mails während der Übertragung, jedoch nicht derzeit ruhende Postfächer)</span><span class="sxs-lookup"><span data-stu-id="fc6ef-198">Document and email-level protection (includes mail in transit, but not currently mailboxes at rest)</span></span></td>
<td align="left"><p><span data-ttu-id="fc6ef-199">Typen vertraulicher Informationen</span><span class="sxs-lookup"><span data-stu-id="fc6ef-199">Sensitive information types</span></span></p>
<p><span data-ttu-id="fc6ef-200">Office-Bezeichnungen</span><span class="sxs-lookup"><span data-stu-id="fc6ef-200">Office labels</span></span></p>
<p><span data-ttu-id="fc6ef-201">Richtlinien zur Verhinderung von Datenverlust</span><span class="sxs-lookup"><span data-stu-id="fc6ef-201">Data loss prevention policies</span></span></p>
<p><span data-ttu-id="fc6ef-202">Microsoft 365-Nachrichtenverschlüsselung für E-Mails</span><span class="sxs-lookup"><span data-stu-id="fc6ef-202">Microsoft 365 Message Encryption for email</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="fc6ef-203">Schutz auf Website- und Bibliotheksebene (darunter SharePoint Online- und OneDrive for Business-Websites)</span><span class="sxs-lookup"><span data-stu-id="fc6ef-203">Site and library-level protection (includes SharePoint Online and OneDrive for Business sites)</span></span></td>
<td align="left"><p><span data-ttu-id="fc6ef-204">Berechtigungen für SharePoint Online- und OneDrive for Business-Websites und -Bibliotheken</span><span class="sxs-lookup"><span data-stu-id="fc6ef-204">Permissions for SharePoint Online and OneDrive for Business sites and libraries</span></span></p>
<p><span data-ttu-id="fc6ef-205">Richtlinien für externe Freigabe für SharePoint Online und OneDrive for Business (Website-Ebene)</span><span class="sxs-lookup"><span data-stu-id="fc6ef-205">External sharing policies for SharePoint Online and OneDrive for Business (site-level)</span></span></p>
<p><span data-ttu-id="fc6ef-206">Gerätezugriffsrichtlinien auf Websiteebene</span><span class="sxs-lookup"><span data-stu-id="fc6ef-206">Site-level device access policies</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="fc6ef-207">Dienstzugriffsschutz (darunter Zugriff auf alle Dienste in Microsoft 365)</span><span class="sxs-lookup"><span data-stu-id="fc6ef-207">Service access protection (includes access to all services in Microsoft 365)</span></span></td>
<td align="left"><p><span data-ttu-id="fc6ef-208">Identitäts- und Gerätezugriffsschutz in Enterprise Mobility + Security (EMS) Suite</span><span class="sxs-lookup"><span data-stu-id="fc6ef-208">Identity and device access protection in Enterprise Mobility + Security (EMS) suite</span></span></p>
<p><span data-ttu-id="fc6ef-209">Privileged Access Management</span><span class="sxs-lookup"><span data-stu-id="fc6ef-209">Privileged access management</span></span></p>
<p><span data-ttu-id="fc6ef-210">Windows 10-Sicherheitsfunktionen</span><span class="sxs-lookup"><span data-stu-id="fc6ef-210">Windows 10 security capabilities</span></span></p></td>
</tr>
</tbody>
</table>

<span data-ttu-id="fc6ef-211">Im restlichen Teil dieses Artikels finden Sie weitere Informationen über jede dieser Schutzkategorien.</span><span class="sxs-lookup"><span data-stu-id="fc6ef-211">The rest of this article provides more information on each of these categories of protection.</span></span>

### <a name="capabilities-that-are-ok-to-use-with-gdpr"></a><span data-ttu-id="fc6ef-212">Funktionen, die mit der DSGVO verwendet werden können</span><span class="sxs-lookup"><span data-stu-id="fc6ef-212">Capabilities that are OK to use with GDPR</span></span>

<span data-ttu-id="fc6ef-p113">Sie können die folgenden Funktionen in einer Umgebung verwenden, die für die Einhaltung der DSGVO konfiguriert ist. Diese Funktionen sind nicht für die Einhaltung der DSGVO erforderlich, sie können jedoch verwendet werden, ohne dass Ihre Möglichkeiten für die Ermittlung, für den Schutz, für die Überwachung und für die Benachrichtigungen zu Daten im Zusammenhang mit der Einhaltung der DSGVO beeinträchtigt werden.</span><span class="sxs-lookup"><span data-stu-id="fc6ef-p113">You can use the following capabilities in an environment configured for GDPR compliance. These capabilities are not necessary for GDPR compliance, but they can be used without adversely affecting your ability to discover, protect, monitor, and report on data related to GDPR compliance.</span></span>

<span data-ttu-id="fc6ef-p114">Kundenschlüssel – Ermöglicht Kunden Kontrolle über die Verschlüsselungsschlüssel, die für die Verschlüsselung von ruhenden Daten in Microsoft 365 verwendet werden. Empfohlen nur für Kunden mit gesetzlichen Anforderungen, eigene Verschlüsselungsschlüssel zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="fc6ef-p114">Customer Key — Allows customers to provide and retain control over the encryption keys that are used to encrypt data at rest within Microsoft 365. Recommended only for customers with a regulatory need to manage their own encryption keys.</span></span>

<span data-ttu-id="fc6ef-p115">Kunden-Lockbox – Mit Kunden-Lockbox können Sie den Zugriff auf Ihre Daten durch einen Microsoft-Supporttechniker fallbasiert steuern, wenn dies zur Behebung eines technischen Problems erforderlich ist. Sie können steuern, ob der Supporttechniker Zugriff auf Ihre Daten erhält oder nicht. Ein Ablaufdatum wird bei jeder Anforderung bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="fc6ef-p115">Customer Lockbox — Customer lockbox allows you to control how a Microsoft support engineer accesses your data, if needed, to fix a technical issue on a case by case basis. You can control whether to give the support engineer access to your data or not. An expiration time is provided with each request.</span></span>

## <a name="site-and-library-level-protection"></a><span data-ttu-id="fc6ef-220">Schutz auf Website- und Bibliotheksebene</span><span class="sxs-lookup"><span data-stu-id="fc6ef-220">Site and library-level protection</span></span>

### <a name="permissions-for-sharepoint-and-onedrive-for-business-libraries"></a><span data-ttu-id="fc6ef-221">Berechtigungen für SharePoint und OneDrive for Business-Bibliotheken</span><span class="sxs-lookup"><span data-stu-id="fc6ef-221">Permissions for SharePoint and OneDrive for Business libraries</span></span>

<span data-ttu-id="fc6ef-p116">Verwenden Sie Berechtigungen in SharePoint, um Benutzerzugriff auf die Website oder deren Inhalte zu gewähren bzw. einzuschränken. Fügen Sie einzelne Benutzer oder Azure Active Directory-Gruppen zu standardmäßigen SharePoint-Gruppen hinzu. Sie können auch eine benutzerdefinierte Gruppe für differenziertere Steuerung erstellen.</span><span class="sxs-lookup"><span data-stu-id="fc6ef-p116">Use permissions in SharePoint to provide or restrict user access to the site or its contents. Add individual users or Azure Active Directory groups to the default SharePoint groups. Or, create a custom group for finer-grain control.</span></span>

![Berechtigungsstufen von „Vollzugriff“ bis zu „Nur anzeigen“](../media/Apply-protection-to-personal-data-in-Office-365-image3.png)

<span data-ttu-id="fc6ef-p117">Die Abbildung enthält die Berechtigungsstufen von „Vollzugriff“ bis hin zu „Nur anzeigen“. Die folgende Tabelle enthält die gleichen Informationen.</span><span class="sxs-lookup"><span data-stu-id="fc6ef-p117">The illustration plots permission levels from Full control to View Only. The following table includes the same information.</span></span>

<table>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="fc6ef-228"><strong>Vollzugriff</strong></span><span class="sxs-lookup"><span data-stu-id="fc6ef-228"><strong>Full Control</strong></span></span></th>
<th align="left"><span data-ttu-id="fc6ef-229"><strong>Entwerfen</strong></span><span class="sxs-lookup"><span data-stu-id="fc6ef-229"><strong>Design</strong></span></span></th>
<th align="left"><span data-ttu-id="fc6ef-230"><strong>Bearbeiten</strong></span><span class="sxs-lookup"><span data-stu-id="fc6ef-230"><strong>Edit</strong></span></span></th>
<th align="left"><span data-ttu-id="fc6ef-231"><strong>Mitwirken</strong></span><span class="sxs-lookup"><span data-stu-id="fc6ef-231"><strong>Contribute</strong></span></span></th>
<th align="left"><span data-ttu-id="fc6ef-232"><strong>Lesen</strong></span><span class="sxs-lookup"><span data-stu-id="fc6ef-232"><strong>Read</strong></span></span></th>
<th align="left"><span data-ttu-id="fc6ef-233"><strong>Nur Anzeigen</strong></span><span class="sxs-lookup"><span data-stu-id="fc6ef-233"><strong>View Only</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"></td>
<td align="left"><span data-ttu-id="fc6ef-234">Mitwirken + genehmigen und anpassen</span><span class="sxs-lookup"><span data-stu-id="fc6ef-234">Contribute + approve and customize</span></span></td>
<td align="left"><span data-ttu-id="fc6ef-235">Mitwirken + Listen hinzufügen, bearbeiten und löschen (nicht nur Listenelemente)</span><span class="sxs-lookup"><span data-stu-id="fc6ef-235">Contribute + add, edit, and delete lists (not just list items)</span></span></td>
<td align="left"><span data-ttu-id="fc6ef-236">Listenelemente und Dokumente anzeigen, hinzufügen, aktualisieren und löschen</span><span class="sxs-lookup"><span data-stu-id="fc6ef-236">View, add, update, delete list items and documents</span></span></td>
<td align="left"><span data-ttu-id="fc6ef-237">Anzeigen und herunterladen</span><span class="sxs-lookup"><span data-stu-id="fc6ef-237">View and download</span></span></td>
<td align="left"><span data-ttu-id="fc6ef-238">Anzeigen, kein Herunterladen</span><span class="sxs-lookup"><span data-stu-id="fc6ef-238">View, no download</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="fc6ef-239">Weitere Informationen:</span><span class="sxs-lookup"><span data-stu-id="fc6ef-239">More information:</span></span>

-   [<span data-ttu-id="fc6ef-240">Grundlegendes zu Berechtigungsstufen in SharePoint</span><span class="sxs-lookup"><span data-stu-id="fc6ef-240">Understanding permission levels in SharePoint</span></span>](https://support.office.com/en-US/article/Understanding-permission-levels-in-SharePoint-87ecbb0e-6550-491a-8826-c075e4859848)

-   [<span data-ttu-id="fc6ef-241">Grundlegendes zu SharePoint-Gruppen</span><span class="sxs-lookup"><span data-stu-id="fc6ef-241">Understanding SharePoint groups</span></span>](https://support.office.com/en-US/article/Understanding-SharePoint-groups-94d9b261-161e-4ace-829e-eca1c8cd2eb8)

### <a name="external-sharing-policies-for-sharepoint-and-onedrive-for-business-libraries"></a><span data-ttu-id="fc6ef-242">Richtlinien für externe Freigabe für SharePoint- und OneDrive for Business-Bibliotheken</span><span class="sxs-lookup"><span data-stu-id="fc6ef-242">External sharing policies for SharePoint and OneDrive for Business libraries</span></span>

<span data-ttu-id="fc6ef-p118">In vielen Organisationen ist die externe Freigabe für die Zusammenarbeit zulässig. Erfahren Sie, wie Ihre mandantenweiten Einstellungen konfiguriert werden. Überprüfen Sie dann die Einstellungen für externe Freigaben für Websites, die personenbezogene Daten enthalten.</span><span class="sxs-lookup"><span data-stu-id="fc6ef-p118">Many organizations allow external sharing to support collaboration. Find out how your tenant-wide settings are configured. Then review the external sharing settings for sites that contain personal data.</span></span>

<span data-ttu-id="fc6ef-246">Ein externer Benutzer ist eine Person außerhalb Ihrer Organisation, die eingeladen wird, auf Ihre SharePoint Online-Websites und -Dokumente zuzugreifen, die jedoch keine Lizenz für Ihr SharePoint Online- oder Microsoft 365-Abonnement hat.</span><span class="sxs-lookup"><span data-stu-id="fc6ef-246">An external user is someone outside of your organization who is invited to access your SharePoint Online sites and documents but doesn't have a license for your SharePoint Online or Microsoft Microsoft 365 subscription.</span></span>

<span data-ttu-id="fc6ef-247">Richtlinien für externe Freigabe gelten sowohl für SharePoint Online als auch OneDrive for Business.</span><span class="sxs-lookup"><span data-stu-id="fc6ef-247">External sharing policies apply to both SharePoint Online and OneDrive for Business.</span></span>

-   <span data-ttu-id="fc6ef-248">Sie müssen ein SharePoint Online-Administrator sein, um die Freigaberichtlinien zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="fc6ef-248">You must be a SharePoint Online admin to configure sharing policies.</span></span>

-   <span data-ttu-id="fc6ef-249">Sie müssen der Websitebesitzer sein oder über Berechtigungen für den Vollzugriff verfügen, um eine Website oder ein Dokument für externe Benutzer freizugeben.</span><span class="sxs-lookup"><span data-stu-id="fc6ef-249">You must be a Site Owner or have full control permissions to share a site or document with external users.</span></span>

<span data-ttu-id="fc6ef-250">Die folgende Tabelle enthält die Steuerelemente, die Sie konfigurieren können.</span><span class="sxs-lookup"><span data-stu-id="fc6ef-250">The following table summarizes the controls you can configure.</span></span>

<table>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="fc6ef-251"><strong>Steuerelementkategorie</strong></span><span class="sxs-lookup"><span data-stu-id="fc6ef-251"><strong>Control category</strong></span></span></th>
<th align="left"><span data-ttu-id="fc6ef-252"><strong>Optionen</strong></span><span class="sxs-lookup"><span data-stu-id="fc6ef-252"><strong>Options</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><span data-ttu-id="fc6ef-253">Art der Freigabe</span><span class="sxs-lookup"><span data-stu-id="fc6ef-253">Type of sharing</span></span></td>
<td align="left"><p><span data-ttu-id="fc6ef-254">Freigabe außerhalb Ihrer Organisation nicht zulassen (kann für einzelne Websitesammlungen festgelegt werden)</span><span class="sxs-lookup"><span data-stu-id="fc6ef-254">Don't allow sharing outside your organization (can be set for individual site collections)</span></span></p>
<p><span data-ttu-id="fc6ef-255">Freigabe nur für authentifizierte externe Benutzer zulassen (neue zulassen oder vorhandene einschränken, kann für einzelne Websitesammlungen festgelegt werden)\*</span><span class="sxs-lookup"><span data-stu-id="fc6ef-255">Allow sharing to authenticated external users only (allow new or limit to existing, can be set for individual site collections)\*</span></span></p>
<p><span data-ttu-id="fc6ef-256">Freigabe für externe Benutzer mit einem Link für anonymen Zugriff zulassen (kann für einzelne Websitesammlungen festgelegt werden)</span><span class="sxs-lookup"><span data-stu-id="fc6ef-256">Allow sharing to external users with an anonymous access link (can be set for individual site collections)</span></span></p>
<p><span data-ttu-id="fc6ef-257">Externe Freigabe mithilfe von Domänen einschränken (Liste „Zulassen“ und „Verweigern“)</span><span class="sxs-lookup"><span data-stu-id="fc6ef-257">Limit external sharing using domains (allow and deny list)</span></span></p>
<p><span data-ttu-id="fc6ef-258">Standardlinktyp auswählen (anonym, Freigabe im Unternehmen möglich oder eingeschränkt)</span><span class="sxs-lookup"><span data-stu-id="fc6ef-258">Choose the default link type (anonymous, company shareable, or restricted)</span></span></p>
</td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="fc6ef-259">Aktionen, die externe Benutzer ausführen können</span><span class="sxs-lookup"><span data-stu-id="fc6ef-259">What external users can do</span></span></td>
<td align="left"><p><span data-ttu-id="fc6ef-260">Verhindern, dass externe Benutzer Dateien, Ordner und Websites freigeben, die sie nicht besitzen</span><span class="sxs-lookup"><span data-stu-id="fc6ef-260">Prevent external users from sharing files, folders, sites they don't own</span></span></p>
<p><span data-ttu-id="fc6ef-261">Festlegen, dass externe Benutzer Freigabeeinladungen mit demselben Konto akzeptieren müssen, an das die Einladung gesendet wurde</span><span class="sxs-lookup"><span data-stu-id="fc6ef-261">Require external users to accept sharing invitations with the same account the invitation was sent to</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="fc6ef-262">Benachrichtigungen</span><span class="sxs-lookup"><span data-stu-id="fc6ef-262">Notifications</span></span></td>
<td align="left"><p><span data-ttu-id="fc6ef-p119">Zurzeit nur in OneDrive for Business verfügbar. Besitzer benachrichtigen, wenn:</span><span class="sxs-lookup"><span data-stu-id="fc6ef-p119">Currently only available in OneDrive for Business. Notify owners when:</span></span></p>
- <p><span data-ttu-id="fc6ef-265">Benutzer weitere externe Benutzer für freigegebene Dateien einladen</span><span class="sxs-lookup"><span data-stu-id="fc6ef-265">Users invite additional external users to shared files</span></span></p>
- <p><span data-ttu-id="fc6ef-266">Externe Benutzer Einladungen für den Zugriff auf Dateien akzeptieren</span><span class="sxs-lookup"><span data-stu-id="fc6ef-266">External users accept invitations to access files</span></span></p>
- <p><span data-ttu-id="fc6ef-267">Ein Link für anonymen Zugriff erstellt oder geändert wird</span><span class="sxs-lookup"><span data-stu-id="fc6ef-267">An anonymous access link is created or changed</span></span></p></td>
</tr>
</tbody>
</table>

<span data-ttu-id="fc6ef-268">Weitere Informationen:</span><span class="sxs-lookup"><span data-stu-id="fc6ef-268">More information:</span></span>

-   [<span data-ttu-id="fc6ef-269">Verwalten der externen Freigabe für Ihre SharePoint-Online-Umgebung</span><span class="sxs-lookup"><span data-stu-id="fc6ef-269">Manage external sharing for your SharePoint Online environment</span></span>](https://support.office.com/article/Manage-external-sharing-for-your-SharePoint-Online-environment-C8A462EB-0723-4B0B-8D0A-70FEAFE4BE85?ui=en-US&rs=en-US&ad=US)

-   [<span data-ttu-id="fc6ef-270">Freigeben von Websites oder Dokumenten für Personen außerhalb Ihrer Organisation</span><span class="sxs-lookup"><span data-stu-id="fc6ef-270">Share sites or documents with people outside your organization</span></span>](https://support.office.com/en-US/article/Share-sites-or-documents-with-people-outside-your-organization-80e49744-e30f-44db-8d51-16661b1d4232)

### <a name="site-level-device-access-policies"></a><span data-ttu-id="fc6ef-271">Gerätezugriffsrichtlinien auf Websiteebene</span><span class="sxs-lookup"><span data-stu-id="fc6ef-271">Site-level device access policies</span></span>

<span data-ttu-id="fc6ef-p120">In SharePoint Online und OneDrive for Business können Sie Richtlinien für de Gerätezugriff konfigurieren. Damit können Sie höheren Schutz für Websites mit vertraulichen Daten konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="fc6ef-p120">SharePoint Online and OneDrive for Business let you configure device access policies at the site level. This lets you configure more protection for sites with sensitive data.</span></span>

<span data-ttu-id="fc6ef-274">Wenn Sie Richtlinien für Gerätezugriff auf Websiteebene konfigurieren, sollten Sie unbedingt diese mit Richtlinien auf Mandantenebene und mit Zugriffsrichtlinien koordinieren, die in Azure Active Directory, Intune und Intune App Management konfiguriert sind.</span><span class="sxs-lookup"><span data-stu-id="fc6ef-274">If you configure site-level device access policies, be sure to coordinate these with tenant-level policies and also with access policies that are configured in Azure Active Directory, Intune, and Intune App Management.</span></span>

<span data-ttu-id="fc6ef-p121">Für Gerätezugriffsrichtlinien für SharePoint und OneDrive for Business sind je nach implementiertem Szenario unterstützende Richtlinien in Azure Active Directory und Microsoft Intune erforderlich. Die folgenden Tabelle enthält eine Zusammenfassung der Ziele, die Sie mit Gerätezugriffsrichtlinien erreichen können, und gibt an, welche Produkte unterstützende Richtlinien erfordern.</span><span class="sxs-lookup"><span data-stu-id="fc6ef-p121">Device access policies for SharePoint and OneDrive for Business require supporting policies in Azure Active Directory and Microsoft Intune depending on the scenario you're implementing. The following table summarizes objectives you can achieve with device access policies and indicates which products require supporting policies.</span></span>

<table>
<thead>
<tr class="header">
<th align="left"></th>
<th align="left"><span data-ttu-id="fc6ef-277">Nur Zugriff von bestimmten IP-Adressen zulassen</span><span class="sxs-lookup"><span data-stu-id="fc6ef-277">Only allow access from specific IP address locations</span></span></th>
<th align="left"><span data-ttu-id="fc6ef-278">Verhindern, dass Benutzer Dateien auf nicht der Domäne beigetretene Geräte herunterladen</span><span class="sxs-lookup"><span data-stu-id="fc6ef-278">Prevent users from downloading files to non-domain joined devices</span></span></th>
<th align="left"><span data-ttu-id="fc6ef-279">Zugriff auf nicht der Domäne beigetretenen Geräten blockieren</span><span class="sxs-lookup"><span data-stu-id="fc6ef-279">Block access on non-domain joined devices</span></span></th>
<th align="left"><span data-ttu-id="fc6ef-280">Verhindern, dass Benutzer Dateien auf nicht kompatiblen Geräten herunterladen</span><span class="sxs-lookup"><span data-stu-id="fc6ef-280">Prevent users from downloading files to non-compliant devices</span></span></th>
<th align="left"><span data-ttu-id="fc6ef-281">Zugriff auf nicht kompatiblen Geräten blockieren</span><span class="sxs-lookup"><span data-stu-id="fc6ef-281">Block access on non-compliant devices</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><span data-ttu-id="fc6ef-282">SharePoint Admin Center</span><span class="sxs-lookup"><span data-stu-id="fc6ef-282">SharePoint admin center</span></span></td>
<td align="left"><span data-ttu-id="fc6ef-283">Ja</span><span class="sxs-lookup"><span data-stu-id="fc6ef-283">Yes</span></span></td>
<td align="left"><span data-ttu-id="fc6ef-284">Ja</span><span class="sxs-lookup"><span data-stu-id="fc6ef-284">Yes</span></span></td>
<td align="left"><span data-ttu-id="fc6ef-285">Ja</span><span class="sxs-lookup"><span data-stu-id="fc6ef-285">Yes</span></span></td>
<td align="left"><span data-ttu-id="fc6ef-286">Ja</span><span class="sxs-lookup"><span data-stu-id="fc6ef-286">Yes</span></span></td>
<td align="left"><span data-ttu-id="fc6ef-287">Ja</span><span class="sxs-lookup"><span data-stu-id="fc6ef-287">Yes</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="fc6ef-288">Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="fc6ef-288">Azure Active Directory</span></span></td>
<td align="left"></td>
<td align="left"><span data-ttu-id="fc6ef-289">Ja</span><span class="sxs-lookup"><span data-stu-id="fc6ef-289">Yes</span></span></td>
<td align="left"><span data-ttu-id="fc6ef-290">Ja</span><span class="sxs-lookup"><span data-stu-id="fc6ef-290">Yes</span></span></td>
<td align="left"><span data-ttu-id="fc6ef-291">Ja</span><span class="sxs-lookup"><span data-stu-id="fc6ef-291">Yes</span></span></td>
<td align="left"><span data-ttu-id="fc6ef-292">Ja</span><span class="sxs-lookup"><span data-stu-id="fc6ef-292">Yes</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="fc6ef-293">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="fc6ef-293">Microsoft Intune</span></span></td>
<td align="left"></td>
<td align="left"></td>
<td align="left"></td>
<td align="left"><span data-ttu-id="fc6ef-294">Ja</span><span class="sxs-lookup"><span data-stu-id="fc6ef-294">Yes</span></span></td>
<td align="left"><span data-ttu-id="fc6ef-295">Ja</span><span class="sxs-lookup"><span data-stu-id="fc6ef-295">Yes</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="fc6ef-296">Weitere Informationen: [SharePoint Online Admin Center: Steuern des Zugriffs von nicht verwalteten Geräten](https://support.office.com/article/Control-access-from-unmanaged-devices-5ae550c4-bd20-4257-847b-5c20fb053622?ui=en-US&rs=en-US&ad=US).</span><span class="sxs-lookup"><span data-stu-id="fc6ef-296">More information: [SharePoint Online admin center: Control access from unmanaged devices](https://support.office.com/article/Control-access-from-unmanaged-devices-5ae550c4-bd20-4257-847b-5c20fb053622?ui=en-US&rs=en-US&ad=US).</span></span>

## <a name="service-access-protection-for-identities-and-devices"></a><span data-ttu-id="fc6ef-297">Dienstzugriffsschutz für Identitäten und Geräte</span><span class="sxs-lookup"><span data-stu-id="fc6ef-297">Service access protection for identities and devices</span></span>

<span data-ttu-id="fc6ef-p122">Microsoft empfiehlt, den Schutz für Identitäten und Geräte zu konfigurieren, die auf den Dienst zugreifen. Die Arbeit, die Sie in den Schutz des Zugriffs auf Microsoft 365-Dienste gesteckt haben, kann auch für den Schutz des Zugriffs auf andere SaaS-Dienste, PaaS-Dienste und sogar Apps anderer Cloudanbieter genutzt werden.</span><span class="sxs-lookup"><span data-stu-id="fc6ef-p122">Microsoft recommends you configure protection for identities and devices that access the service. The work you put into protecting access to Microsoft 365 services can also be used to protect access to other SaaS services, PaaS services, and even apps in other cloud providers.</span></span>

<span data-ttu-id="fc6ef-300">Zugriffsschutz für Identitäten und Geräte bietet einen Basisschutz, um sicherzustellen, dass Identitäten nicht kompromittiert werden, Geräte sicher und Unternehmensdaten, auf die auf Geräten zugegriffen wird, isoliert und geschützt sind.</span><span class="sxs-lookup"><span data-stu-id="fc6ef-300">Access protection for identities and devices provides a baseline of protection to ensure that identities aren't compromised, devices are safe, and organization data that is accessed on devices is isolated and protected.</span></span>

<span data-ttu-id="fc6ef-301">Empfehlungen zu den Ansatzpunkten und Konfigurationsanweisungen finden Sie unter [Microsoft-Sicherheitsleitfaden für politische Kampagnen, gemeinnützige Organisationen und andere agile Organisationen](https://docs.microsoft.com/microsoft-365-enterprise/microsoft-security-guidance).</span><span class="sxs-lookup"><span data-stu-id="fc6ef-301">For starting point recommendations and configuration guidance, see [Microsoft security guidance for political campaigns, nonprofits, and other agile organizations](https://docs.microsoft.com/microsoft-365-enterprise/microsoft-security-guidance).</span></span>

<span data-ttu-id="fc6ef-302">Informationen zu Hybrididentitätsumgebungen mit AD FS finden Sie unter [Empfohlene Sicherheitsrichtlinien und Konfigurationen](https://docs.microsoft.com/microsoft-365-enterprise/microsoft-security-guidance).</span><span class="sxs-lookup"><span data-stu-id="fc6ef-302">For hybrid identity environments with AD FS, see [Recommended security policies and configurations](https://docs.microsoft.com/microsoft-365-enterprise/microsoft-security-guidance).</span></span>

<span data-ttu-id="fc6ef-p123">Die folgende Abbildung zeigt die Beziehungen zwischen Clouddiensten (SaaS, PaaS), Kontotypen (Mandantendomänenkonten und B2B-Konten) sowie Funktionen für den Dienstzugriff. Es ist wichtig zu wissen, welche Funktionen bei B2B-Konten verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="fc6ef-p123">The following illustration describes how cloud services (SaaS, PaaS), account types (tenant domain accounts vs. B2B accounts), and service access capabilities relate. It's important to note which capabilities can be used with B2B accounts.</span></span>

![Clouddienste, Kontotypen und Zugriffsfunktionen](../media/Apply-protection-to-personal-data-in-Office-365-image4.png)

<span data-ttu-id="fc6ef-306">Für Zwecke der Barrierefreiheit wird im übrigen Teil dieses Abschnitts die obige Abbildung beschrieben.</span><span class="sxs-lookup"><span data-stu-id="fc6ef-306">For accessibility, the rest of this section describes this illustration.</span></span>

### <a name="cloud-services"></a><span data-ttu-id="fc6ef-307">Clouddienste</span><span class="sxs-lookup"><span data-stu-id="fc6ef-307">Cloud services</span></span>

<span data-ttu-id="fc6ef-p124">Azure Active Directory bietet Identitätszugriff auf jeden beliebigen Clouddienst, darunter auch andere Anbieter als Microsoft wie z. B. Amazon Web Services. Die Abbildung zeigt Microsoft 365, „Andere SaaS-App“ und „PaaS-App“. Die Pfeile zeigen von Azure Active Directory auf jeden dieser Dienste und geben somit an, dass Azure Active Directory für die Authentifizierung für alle diese App-Typen verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="fc6ef-p124">Azure Active Directory provides identity access to any cloud service, including non-Microsoft providers such as Amazon Web Services. The illustration shows Microsoft 365, "Other SaaS app," and "PaaS app." Arrows point from Azure Active Directory to each of these services, showing that Azure Active Directory can be used for authentication to all of these app types.</span></span>

### <a name="types-of-accounts"></a><span data-ttu-id="fc6ef-311">Kontentypen</span><span class="sxs-lookup"><span data-stu-id="fc6ef-311">Types of accounts</span></span>

<span data-ttu-id="fc6ef-p125">Mandantendomänenkonten sind Konten, die Sie zu Ihrem Mandanten hinzufügen und direkt verwalten. B2B-Konten sind Konten für Benutzer außerhalb Ihrer Organisation, die Sie zur Zusammenarbeit einladen. Dies können andere Microsoft 365-Konten, andere Organisationskonten oder Endbenutzerkonten (z. B. Gmail) sein. Die Abbildung zeigt die beiden Kontotypen in Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="fc6ef-p125">Tenant domain accounts are account you add to your tenant and manage directly. B2B accounts are accounts for users outside your organization you invite to collaborate with. These can be other Microsoft 365 accounts, other organization accounts, or consumer accounts (such as Gmail). The illustration shows both account types within Azure Active Directory.</span></span>

### <a name="capabilities"></a><span data-ttu-id="fc6ef-316">Funktionen</span><span class="sxs-lookup"><span data-stu-id="fc6ef-316">Capabilities</span></span>

<span data-ttu-id="fc6ef-p126">Die Funktionen in der folgenden Tabelle schützen Identitäten und Geräte. Die Tabelle zeigt, welche Funktionen auch mit B2B-Konten verwendet werden können, ähnlich wie in der Abbildung.</span><span class="sxs-lookup"><span data-stu-id="fc6ef-p126">The capabilities in the following table protect identities and devices. The table indicates which capabilities can also be used with B2B accounts, similar to the illustration.</span></span>

<table>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="fc6ef-319"><strong>Funktion</strong></span><span class="sxs-lookup"><span data-stu-id="fc6ef-319"><strong>Capability</strong></span></span></th>
<th align="left"><span data-ttu-id="fc6ef-320"><strong>Für Mandantendomänenkonten geeignet</strong></span><span class="sxs-lookup"><span data-stu-id="fc6ef-320"><strong>Works with tenant domain accounts</strong></span></span></th>
<th align="left"><span data-ttu-id="fc6ef-321"><strong>Für Azure-B2B-Konten geeignet (ohne zusätzliche Lizenzierung)</strong></span><span class="sxs-lookup"><span data-stu-id="fc6ef-321"><strong>Works with Azure B2B accounts (without additional licensing)</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><span data-ttu-id="fc6ef-322">Mehrstufige Authentifizierung und bedingter Zugriff</span><span class="sxs-lookup"><span data-stu-id="fc6ef-322">Multi-factor authentication and conditional access</span></span></td>
<td align="left"><span data-ttu-id="fc6ef-323">Ja</span><span class="sxs-lookup"><span data-stu-id="fc6ef-323">Yes</span></span></td>
<td align="left"><span data-ttu-id="fc6ef-324">Ja</span><span class="sxs-lookup"><span data-stu-id="fc6ef-324">Yes</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="fc6ef-325">Azure AD Identity Protection</span><span class="sxs-lookup"><span data-stu-id="fc6ef-325">Azure AD Identity Protection</span></span></td>
<td align="left"><span data-ttu-id="fc6ef-326">Ja</span><span class="sxs-lookup"><span data-stu-id="fc6ef-326">Yes</span></span></td>
<td align="left"><span data-ttu-id="fc6ef-327">Ja</span><span class="sxs-lookup"><span data-stu-id="fc6ef-327">Yes</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="fc6ef-328">Azure AD Privileged Identity Management</span><span class="sxs-lookup"><span data-stu-id="fc6ef-328">Azure AD Privileged Identity Management</span></span></td>
<td align="left"><span data-ttu-id="fc6ef-329">Ja</span><span class="sxs-lookup"><span data-stu-id="fc6ef-329">Yes</span></span></td>
<td align="left"></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="fc6ef-330">Mobile Anwendungsverwaltung (Mobile Application Management, MAM)</span><span class="sxs-lookup"><span data-stu-id="fc6ef-330">Mobile Application Management (MAM)</span></span></td>
<td align="left"><span data-ttu-id="fc6ef-331">Ja</span><span class="sxs-lookup"><span data-stu-id="fc6ef-331">Yes</span></span></td>
<td align="left"></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="fc6ef-332">Geräteregistrierung und -verwaltung</span><span class="sxs-lookup"><span data-stu-id="fc6ef-332">Device enrollment and management</span></span></td>
<td align="left"><span data-ttu-id="fc6ef-333">Ja</span><span class="sxs-lookup"><span data-stu-id="fc6ef-333">Yes</span></span></td>
<td align="left"><span data-ttu-id="fc6ef-334">Nur eine Organisation kann ein Gerät verwalten</span><span class="sxs-lookup"><span data-stu-id="fc6ef-334">Only one organization can manage a device</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="fc6ef-335">Windows 10-Sicherheitsfunktionen (für bedingten Zugriff auf Grundlage der Gerätekompatibilität ist Geräteverwaltung erforderlich)</span><span class="sxs-lookup"><span data-stu-id="fc6ef-335">Windows 10 security capabilities (conditional access based on device compliance requires device management)</span></span></td>
<td align="left"><span data-ttu-id="fc6ef-336">Ja</span><span class="sxs-lookup"><span data-stu-id="fc6ef-336">Yes</span></span></td>
<td align="left"><span data-ttu-id="fc6ef-337">Ja</span><span class="sxs-lookup"><span data-stu-id="fc6ef-337">Yes</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="fc6ef-338">Sie können Lizenzen zu B2B-Konten hinzufügen, um diesen Benutzern bei Bedarf zusätzliche Funktionen bereitzustellen, um den Zugriff auf personenbezogene Daten in Ihrer Umgebung zu schützen.</span><span class="sxs-lookup"><span data-stu-id="fc6ef-338">You can add licenses to B2B accounts to give these users additional capabilities, if needed, to protect access to personal data in your environment.</span></span>
