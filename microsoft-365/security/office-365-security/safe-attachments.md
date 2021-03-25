---
title: Sichere Anlagen
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.date: ''
ms.topic: overview
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 6e13311e-92ae-495e-a619-56d770199170
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
- seo-marvel-apr2020
description: Administratoren können sich über das Feature "Sichere Anlagen" in Microsoft Defender für Office 365 informieren.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: a2f097cddce4afe2b3242ae34bbcfa242c3af601
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/25/2021
ms.locfileid: "51206571"
---
# <a name="safe-attachments-in-microsoft-defender-for-office-365"></a><span data-ttu-id="edd5a-103">Sichere Anlagen in Microsoft Defender für Office 365</span><span class="sxs-lookup"><span data-stu-id="edd5a-103">Safe Attachments in Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="edd5a-104">**Gilt für**</span><span class="sxs-lookup"><span data-stu-id="edd5a-104">**Applies to**</span></span>
- [<span data-ttu-id="edd5a-105">Microsoft Defender für Office 365 Plan 1 und Plan 2</span><span class="sxs-lookup"><span data-stu-id="edd5a-105">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="edd5a-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="edd5a-106">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="edd5a-107">Sichere Anlagen in [Microsoft Defender für Office 365](defender-for-office-365.md) bietet eine zusätzliche Schutzebene für E-Mail-Anlagen, die bereits vom Schutz vor Schadsoftware [in Exchange Online Protection (EOP)](anti-malware-protection.md)überprüft wurden.</span><span class="sxs-lookup"><span data-stu-id="edd5a-107">Safe Attachments in [Microsoft Defender for Office 365](defender-for-office-365.md) provides an additional layer of protection for email attachments that have already been scanned by [anti-malware protection in Exchange Online Protection (EOP)](anti-malware-protection.md).</span></span> <span data-ttu-id="edd5a-108">Insbesondere sichere Anlagen verwenden eine virtuelle Umgebung, um Anlagen in E-Mail-Nachrichten zu überprüfen, bevor sie an Empfänger übermittelt werden (ein Prozess, der als _Detonation bekannt ist)._</span><span class="sxs-lookup"><span data-stu-id="edd5a-108">Specifically, Safe Attachments uses a virtual environment to check attachments in email messages before they're delivered to recipients (a process known as _detonation_).</span></span>

<span data-ttu-id="edd5a-109">Der Schutz sicherer Anlagen für E-Mail-Nachrichten wird durch Richtlinien für sichere Anlagen gesteuert.</span><span class="sxs-lookup"><span data-stu-id="edd5a-109">Safe Attachments protection for email messages is controlled by Safe Attachments policies.</span></span> <span data-ttu-id="edd5a-110">Es gibt keine Standardrichtlinie für sichere Anlagen. Um den Schutz sicherer Anlagen zu erhalten, müssen Sie eine oder mehrere Richtlinien für sichere **Anlagen erstellen.**</span><span class="sxs-lookup"><span data-stu-id="edd5a-110">There is no default Safe Attachments policy, **so to get the protection of Safe Attachments, you need to create one or more Safe Attachments policies**.</span></span> <span data-ttu-id="edd5a-111">Anweisungen finden Sie [unter Set up Safe Attachments policies in Defender for Office 365](set-up-safe-attachments-policies.md).</span><span class="sxs-lookup"><span data-stu-id="edd5a-111">For instructions, see [Set up Safe Attachments policies in Defender for Office 365](set-up-safe-attachments-policies.md).</span></span>

<span data-ttu-id="edd5a-112">In der folgenden Tabelle werden Szenarien für sichere Anlagen in Microsoft 365- und Office 365-Organisationen beschrieben, zu denen Microsoft Defender für Office 365 gehört (d. h. fehlende Lizenzierung ist in den Beispielen nie ein Problem).</span><span class="sxs-lookup"><span data-stu-id="edd5a-112">The following table describes scenarios for Safe Attachments in Microsoft 365 and Office 365 organizations that include Microsoft Defender for Office 365 (in other words, lack of licensing is never an issue in the examples).</span></span>

****

|<span data-ttu-id="edd5a-113">Szenario</span><span class="sxs-lookup"><span data-stu-id="edd5a-113">Scenario</span></span>|<span data-ttu-id="edd5a-114">Ergebnis</span><span class="sxs-lookup"><span data-stu-id="edd5a-114">Result</span></span>|
|---|---|
|<span data-ttu-id="edd5a-115">In der Microsoft 365 E5-Organisation von Pat sind keine Richtlinien für sichere Anlagen konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="edd5a-115">Pat's Microsoft 365 E5 organization has no Safe Attachments policies configured.</span></span>|<span data-ttu-id="edd5a-116">Pat ist nicht durch sichere Anlagen geschützt.</span><span class="sxs-lookup"><span data-stu-id="edd5a-116">Pat is not protected by Safe Attachments.</span></span> <p> <span data-ttu-id="edd5a-117">Ein Administrator muss mindestens eine Richtlinie für sichere Anlagen erstellen, damit der Schutz sicherer Anlagen aktiv ist.</span><span class="sxs-lookup"><span data-stu-id="edd5a-117">An admin must create at least one Safe Attachments policy for Safe Attachments protection to be active.</span></span> <span data-ttu-id="edd5a-118">Darüber hinaus müssen die Bedingungen der Richtlinie Pat enthalten, wenn Pat durch sichere Anlagen geschützt werden soll.</span><span class="sxs-lookup"><span data-stu-id="edd5a-118">Furthermore, the conditions of the policy must include Pat if Pat is to be protected by Safe Attachments.</span></span>|
|<span data-ttu-id="edd5a-119">Lees Organisation verfügt über eine Richtlinie für sichere Anlagen, die nur für Finanzmitarbeiter gilt.</span><span class="sxs-lookup"><span data-stu-id="edd5a-119">Lee's organization has a Safe Attachments policy that applies only to finance employees.</span></span> <span data-ttu-id="edd5a-120">Lee ist Mitglied der Vertriebsabteilung.</span><span class="sxs-lookup"><span data-stu-id="edd5a-120">Lee is a member of the sales department.</span></span>|<span data-ttu-id="edd5a-121">Lee ist nicht durch sichere Anlagen geschützt.</span><span class="sxs-lookup"><span data-stu-id="edd5a-121">Lee is not protected by Safe Attachments.</span></span> <p> <span data-ttu-id="edd5a-122">Finanzmitarbeiter sind durch sichere Anlagen geschützt, Vertriebsmitarbeiter (und andere Mitarbeiter) dagegen nicht.</span><span class="sxs-lookup"><span data-stu-id="edd5a-122">Finance employees are protected by Safe Attachments, but sales employees (and other employees) are not.</span></span>|
|<span data-ttu-id="edd5a-123">Gestern hat ein Administrator in Der Organisation von Jean eine Richtlinie für sichere Anlagen erstellt, die für alle Mitarbeiter gilt.</span><span class="sxs-lookup"><span data-stu-id="edd5a-123">Yesterday, an admin in Jean's organization created a Safe Attachments policy that applies to all employees.</span></span> <span data-ttu-id="edd5a-124">Zuvor hat Er eine E-Mail-Nachricht mit einer Anlage erhalten.</span><span class="sxs-lookup"><span data-stu-id="edd5a-124">Earlier today, Jean received an email message that included an attachment.</span></span>|<span data-ttu-id="edd5a-125">"Jean" ist durch sichere Anlagen geschützt.</span><span class="sxs-lookup"><span data-stu-id="edd5a-125">Jean is protected by Safe Attachments.</span></span> <p> <span data-ttu-id="edd5a-126">In der Regel dauert es etwa 30 Minuten, bis eine neue Richtlinie wirksam wird.</span><span class="sxs-lookup"><span data-stu-id="edd5a-126">Typically, it takes about 30 minutes for a new policy to take effect.</span></span>|
|<span data-ttu-id="edd5a-127">Chris' Organisation verfügt über langfristige Richtlinien für sichere Anlagen für alle in der Organisation.</span><span class="sxs-lookup"><span data-stu-id="edd5a-127">Chris's organization has long-standing Safe Attachments policies for everyone in the organization.</span></span> <span data-ttu-id="edd5a-128">Chris empfängt eine E-Mail mit einer Anlage und gibt die Nachricht dann an externe Empfänger weiter.</span><span class="sxs-lookup"><span data-stu-id="edd5a-128">Chris receives an email that has an attachment, and then forwards the message to external recipients.</span></span>|<span data-ttu-id="edd5a-129">Chis ist durch sichere Anlagen geschützt.</span><span class="sxs-lookup"><span data-stu-id="edd5a-129">Chis is protected by Safe Attachments.</span></span> <p> <span data-ttu-id="edd5a-130">Wenn die externen Empfänger auch Richtlinien für sichere Anlagen in ihrer Organisation haben, unterliegen die weitergeleiteten Nachrichten diesen Richtlinien.</span><span class="sxs-lookup"><span data-stu-id="edd5a-130">If the external recipients also have Safe Attachments policies in their organization, then the forwarded messages are subject to those policies.</span></span>|
|

<span data-ttu-id="edd5a-131">Die Überprüfung sicherer Anlagen erfolgt in derselben Region, in der sich Ihre Microsoft 365-Daten befinden.</span><span class="sxs-lookup"><span data-stu-id="edd5a-131">Safe Attachments scanning takes place in the same region where your Microsoft 365 data resides.</span></span> <span data-ttu-id="edd5a-132">Weitere Informationen zur Geografie des Rechenzentrums finden Sie unter [Wo befinden sich Ihre Daten?](https://products.office.com/where-is-your-data-located?geo=All)</span><span class="sxs-lookup"><span data-stu-id="edd5a-132">For more information about datacenter geography, see [Where is your data located?](https://products.office.com/where-is-your-data-located?geo=All)</span></span>

> [!NOTE]
> <span data-ttu-id="edd5a-133">Die folgenden Features befinden sich in den globalen Einstellungen von Richtlinien für sichere Anlagen im Security & Compliance Center.</span><span class="sxs-lookup"><span data-stu-id="edd5a-133">The following features are located in the global settings of Safe Attachments policies in the Security & Compliance Center.</span></span> <span data-ttu-id="edd5a-134">Diese Einstellungen sind jedoch global aktiviert oder deaktiviert und erfordern keine Richtlinien für sichere Anlagen:</span><span class="sxs-lookup"><span data-stu-id="edd5a-134">But, these settings are enabled or disabled globally, and don't require Safe Attachments policies:</span></span>
>
> - <span data-ttu-id="edd5a-135">[Sichere Anlagen für SharePoint, OneDrive und Microsoft Teams](mdo-for-spo-odb-and-teams.md).</span><span class="sxs-lookup"><span data-stu-id="edd5a-135">[Safe Attachments for SharePoint, OneDrive, and Microsoft Teams](mdo-for-spo-odb-and-teams.md).</span></span>
>
> - [<span data-ttu-id="edd5a-136">Sichere Dokumente in Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="edd5a-136">Safe Documents in Microsoft 365 E5</span></span>](safe-docs.md)

## <a name="safe-attachments-policy-settings"></a><span data-ttu-id="edd5a-137">Richtlinieneinstellungen für sichere Anlagen</span><span class="sxs-lookup"><span data-stu-id="edd5a-137">Safe Attachments policy settings</span></span>

<span data-ttu-id="edd5a-138">In diesem Abschnitt werden die Einstellungen in Richtlinien für sichere Anlagen beschrieben:</span><span class="sxs-lookup"><span data-stu-id="edd5a-138">This section describes the settings in Safe Attachments policies:</span></span>

- <span data-ttu-id="edd5a-139">**Antwort auf unbekannte Schadsoftware** für sichere Anlagen: Diese Einstellung steuert die Aktion zum Scannen von Schadsoftware sicherer Anlagen in E-Mail-Nachrichten.</span><span class="sxs-lookup"><span data-stu-id="edd5a-139">**Safe Attachments unknown malware response**: This setting controls the action for Safe Attachments malware scanning in email messages.</span></span> <span data-ttu-id="edd5a-140">Die verfügbaren Optionen werden in der folgenden Tabelle beschrieben:</span><span class="sxs-lookup"><span data-stu-id="edd5a-140">The available options are described in the following table:</span></span>

  ****

  |<span data-ttu-id="edd5a-141">Option</span><span class="sxs-lookup"><span data-stu-id="edd5a-141">Option</span></span>|<span data-ttu-id="edd5a-142">Effekt</span><span class="sxs-lookup"><span data-stu-id="edd5a-142">Effect</span></span>|<span data-ttu-id="edd5a-143">Verwenden Sie, wenn Sie:</span><span class="sxs-lookup"><span data-stu-id="edd5a-143">Use when you want to:</span></span>|
  |---|---|---|
  |<span data-ttu-id="edd5a-144">**Aus**</span><span class="sxs-lookup"><span data-stu-id="edd5a-144">**Off**</span></span>|<span data-ttu-id="edd5a-145">Anlagen werden nicht von sicheren Anlagen auf Schadsoftware überprüft.</span><span class="sxs-lookup"><span data-stu-id="edd5a-145">Attachments aren't scanned for malware by Safe Attachments.</span></span> <span data-ttu-id="edd5a-146">Nachrichten werden weiterhin durch Den Schutz vor Schadsoftware [in EOP auf Schadsoftware überprüft.](anti-malware-protection.md)</span><span class="sxs-lookup"><span data-stu-id="edd5a-146">Messages are still scanned for malware by [anti-malware protection in EOP](anti-malware-protection.md).</span></span>|<span data-ttu-id="edd5a-147">Deaktivieren sie die Überprüfung für ausgewählte Empfänger.</span><span class="sxs-lookup"><span data-stu-id="edd5a-147">Turn scanning off for selected recipients.</span></span> <p> <span data-ttu-id="edd5a-148">Vermeiden Sie unnötige Verzögerungen beim Routing interner E-Mails.</span><span class="sxs-lookup"><span data-stu-id="edd5a-148">Prevent unnecessary delays in routing internal mail.</span></span> <p> <span data-ttu-id="edd5a-149">**Diese Option wird für die meisten Benutzer nicht empfohlen. Sie sollten diese Option nur verwenden, um die Überprüfung sicherer Anlagen für Empfänger zu deaktivieren, die nur Nachrichten von vertrauenswürdigen Absendern empfangen.**</span><span class="sxs-lookup"><span data-stu-id="edd5a-149">**This option is not recommended for most users. You should only use this option to turn off Safe Attachments scanning for recipients who only receive messages from trusted senders.**</span></span>|
  |<span data-ttu-id="edd5a-150">**Überwachen**</span><span class="sxs-lookup"><span data-stu-id="edd5a-150">**Monitor**</span></span>|<span data-ttu-id="edd5a-151">Liefert Nachrichten mit Anlagen und verfolgt dann, was mit erkannter Schadsoftware geschieht.</span><span class="sxs-lookup"><span data-stu-id="edd5a-151">Delivers messages with attachments and then tracks what happens with detected malware.</span></span> <p> <span data-ttu-id="edd5a-152">Die Zustellung sicherer Nachrichten kann aufgrund der Überprüfung sicherer Anlagen verzögert werden.</span><span class="sxs-lookup"><span data-stu-id="edd5a-152">Delivery of safe messages might be delayed due to Safe Attachments scanning.</span></span>|<span data-ttu-id="edd5a-153">Sehen Sie, wo erkannte Schadsoftware in Ihrer Organisation liegt.</span><span class="sxs-lookup"><span data-stu-id="edd5a-153">See where detected malware goes in your organization.</span></span>|
  |<span data-ttu-id="edd5a-154">**Blockieren**</span><span class="sxs-lookup"><span data-stu-id="edd5a-154">**Block**</span></span>|<span data-ttu-id="edd5a-155">Verhindert, dass Nachrichten mit erkannten Schadsoftwareanlagen zugestellt werden.</span><span class="sxs-lookup"><span data-stu-id="edd5a-155">Prevents messages with detected malware attachments from being delivered.</span></span> <p> <span data-ttu-id="edd5a-156">Nachrichten werden [isoliert,](manage-quarantined-messages-and-files.md) wenn nur Administratoren (nicht Endbenutzer) die Nachrichten überprüfen, veröffentlichen oder löschen können.</span><span class="sxs-lookup"><span data-stu-id="edd5a-156">Messages are [quarantined](manage-quarantined-messages-and-files.md) where only admins (not end-users) can review, release, or delete the messages.</span></span> <p> <span data-ttu-id="edd5a-157">Blockiert automatisch zukünftige Instanzen der Nachrichten und Anlagen.</span><span class="sxs-lookup"><span data-stu-id="edd5a-157">Automatically blocks future instances of the messages and attachments.</span></span> <p> <span data-ttu-id="edd5a-158">Die Zustellung sicherer Nachrichten kann aufgrund der Überprüfung sicherer Anlagen verzögert werden.</span><span class="sxs-lookup"><span data-stu-id="edd5a-158">Delivery of safe messages might be delayed due to Safe Attachments scanning.</span></span>|<span data-ttu-id="edd5a-159">Schützt Ihre Organisation vor wiederholten Angriffen mit denselben Schadsoftwareanlagen.</span><span class="sxs-lookup"><span data-stu-id="edd5a-159">Protects your organization from repeated attacks using the same malware attachments.</span></span> <p> <span data-ttu-id="edd5a-160">Dies ist der Standardwert und der empfohlene Wert in standard und Strict [voreingestellte Sicherheitsrichtlinien](preset-security-policies.md).</span><span class="sxs-lookup"><span data-stu-id="edd5a-160">This is the default value, and the recommended value in Standard and Strict [preset security policies](preset-security-policies.md).</span></span>|
  |<span data-ttu-id="edd5a-161">**Replace**</span><span class="sxs-lookup"><span data-stu-id="edd5a-161">**Replace**</span></span>|<span data-ttu-id="edd5a-162">Entfernt erkannte Schadsoftwareanlagen.</span><span class="sxs-lookup"><span data-stu-id="edd5a-162">Removes detected malware attachments.</span></span> <p> <span data-ttu-id="edd5a-163">Benachrichtigt Empfänger, dass Anlagen entfernt wurden.</span><span class="sxs-lookup"><span data-stu-id="edd5a-163">Notifies recipients that attachments have been removed.</span></span> <p>  <span data-ttu-id="edd5a-164">Nachrichten werden [isoliert,](manage-quarantined-messages-and-files.md) wenn nur Administratoren (nicht Endbenutzer) die Nachrichten überprüfen, veröffentlichen oder löschen können.</span><span class="sxs-lookup"><span data-stu-id="edd5a-164">Messages are [quarantined](manage-quarantined-messages-and-files.md) where only admins (not end-users) can review, release, or delete the messages.</span></span> <p> <span data-ttu-id="edd5a-165">Die Zustellung sicherer Nachrichten kann aufgrund der Überprüfung sicherer Anlagen verzögert werden.</span><span class="sxs-lookup"><span data-stu-id="edd5a-165">Delivery of safe messages might be delayed due to Safe Attachments scanning.</span></span>|<span data-ttu-id="edd5a-166">Erhöhen Sie die Sichtbarkeit für Empfänger, dass Anlagen aufgrund erkannter Schadsoftware entfernt wurden.</span><span class="sxs-lookup"><span data-stu-id="edd5a-166">Raise visibility to recipients that attachments were removed because of detected malware.</span></span>|
  |<span data-ttu-id="edd5a-167">**Dynamische Übermittlung**</span><span class="sxs-lookup"><span data-stu-id="edd5a-167">**Dynamic Delivery**</span></span>|<span data-ttu-id="edd5a-168">Übermittelt Nachrichten sofort, ersetzt anlagen jedoch durch Platzhalter, bis die Überprüfung sicherer Anlagen abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="edd5a-168">Delivers messages immediately, but replaces attachments with placeholders until Safe Attachments scanning is complete.</span></span> <p> <span data-ttu-id="edd5a-169">Weitere Informationen finden Sie im Abschnitt Richtlinien für die dynamische [Zustellung in](#dynamic-delivery-in-safe-attachments-policies) sicheren Anlagen weiter weiter weiter in diesem Artikel.</span><span class="sxs-lookup"><span data-stu-id="edd5a-169">For details, see the [Dynamic Delivery in Safe Attachments policies](#dynamic-delivery-in-safe-attachments-policies) section later in this article.</span></span>|<span data-ttu-id="edd5a-170">Vermeiden Von Nachrichtenverzögerungen beim Schutz von Empfängern vor schädlichen Dateien.</span><span class="sxs-lookup"><span data-stu-id="edd5a-170">Avoid message delays while protecting recipients from malicious files.</span></span> <p> <span data-ttu-id="edd5a-171">Ermöglichen Sie Empfängern die Vorschau von Anlagen im abgesicherten Modus, während die Überprüfung stattfindet.</span><span class="sxs-lookup"><span data-stu-id="edd5a-171">Enable recipients to preview attachments in safe mode while scanning is taking place.</span></span>|
  |

- <span data-ttu-id="edd5a-172">Umleitungsanlage bei **Erkennung:** Aktivieren Sie die Umleitung, und senden Sie die Anlage an die folgende E-Mail-Adresse: Senden Sie für Block **-,** **Monitor-** oder **Replace-Aktionen** Nachrichten, die Schadsoftwareanlagen enthalten, zur Analyse und Untersuchung an die angegebene interne oder externe E-Mail-Adresse.</span><span class="sxs-lookup"><span data-stu-id="edd5a-172">**Redirect attachment on detection: Enable redirect** and **Send the attachment to the following email address**: For **Block**, **Monitor**, or **Replace** actions, send messages that contain malware attachments to the specified internal or external email address for analysis and investigation.</span></span>

  <span data-ttu-id="edd5a-173">Die Empfehlung für Standard- und Strict-Richtlinieneinstellungen besteht in der Aktivierung der Umleitung.</span><span class="sxs-lookup"><span data-stu-id="edd5a-173">The recommendation for Standard and Strict policy settings is to enable redirection.</span></span> <span data-ttu-id="edd5a-174">Weitere Informationen finden Sie unter [Einstellungen für sichere Anlagen](recommended-settings-for-eop-and-office365.md#safe-attachments-settings).</span><span class="sxs-lookup"><span data-stu-id="edd5a-174">For more information, see [Safe Attachments settings](recommended-settings-for-eop-and-office365.md#safe-attachments-settings).</span></span>

- <span data-ttu-id="edd5a-175">**Wenden Sie die oben** aufgeführte Auswahl an, wenn die  Schadsoftwareprüfung auf Anlagen ein Zeit- oder Fehlerfehler auftritt: Die durch die unbekannte Schadsoftwareantwort für sichere Anlagen angegebene Aktion wird für Nachrichten ausgeführt, auch wenn die Überprüfung sicherer Anlagen nicht abgeschlossen werden kann.</span><span class="sxs-lookup"><span data-stu-id="edd5a-175">**Apply the above selection if malware scanning for attachments times out or error occurs**: The action specified by **Safe Attachments unknown malware response** is taken on messages even when Safe Attachments scanning can't complete.</span></span> <span data-ttu-id="edd5a-176">Wählen Sie diese Option immer aus, wenn Sie **Umleitung aktivieren auswählen.**</span><span class="sxs-lookup"><span data-stu-id="edd5a-176">Always select this option if you select **Enable redirect**.</span></span> <span data-ttu-id="edd5a-177">Andernfalls gehen Nachrichten möglicherweise verloren.</span><span class="sxs-lookup"><span data-stu-id="edd5a-177">Otherwise, messages might be lost.</span></span>

- <span data-ttu-id="edd5a-178">**Empfängerfilter:** Sie müssen die Empfängerbedingungen und Ausnahmen angeben, die bestimmen, auf wen die Richtlinie angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="edd5a-178">**Recipient filters**: You need to specify the recipient conditions and exceptions that determine who the policy applies to.</span></span> <span data-ttu-id="edd5a-179">Sie können die folgenden Eigenschaften für Bedingungen und Ausnahmen verwenden:</span><span class="sxs-lookup"><span data-stu-id="edd5a-179">You can use these properties for conditions and exceptions:</span></span>

  - <span data-ttu-id="edd5a-180">**Der Empfänger ist**</span><span class="sxs-lookup"><span data-stu-id="edd5a-180">**The recipient is**</span></span>
  - <span data-ttu-id="edd5a-181">**Die Empfängerdomäne ist**</span><span class="sxs-lookup"><span data-stu-id="edd5a-181">**The recipient domain is**</span></span>
  - <span data-ttu-id="edd5a-182">**Der Empfänger ist Mitglied von**</span><span class="sxs-lookup"><span data-stu-id="edd5a-182">**The recipient is a member of**</span></span>

  <span data-ttu-id="edd5a-183">Sie können eine Bedingung oder Ausnahme nur einmal verwenden, die Bedingung oder Ausnahme kann aber mehrere Werte enthalten.</span><span class="sxs-lookup"><span data-stu-id="edd5a-183">You can only use a condition or exception once, but the condition or exception can contain multiple values.</span></span> <span data-ttu-id="edd5a-184">Bei mehreren Werten derselben Bedingung oder Ausnahme wird ODER-Logik verwendet (z. B. _\<recipient1\>_ oder _\<recipient2\>_).</span><span class="sxs-lookup"><span data-stu-id="edd5a-184">Multiple values of the same condition or exception use OR logic (for example, _\<recipient1\>_ or _\<recipient2\>_).</span></span> <span data-ttu-id="edd5a-185">Bei unterschiedlichen Bedingungen oder Ausnahmen wird UND-Logik verwendet (z. B. _\<recipient1\>_ und _\<member of group 1\>_).</span><span class="sxs-lookup"><span data-stu-id="edd5a-185">Different conditions or exceptions use AND logic (for example, _\<recipient1\>_ and _\<member of group 1\>_).</span></span>

- <span data-ttu-id="edd5a-186">**Priorität:** Wenn Sie mehrere Richtlinien erstellen, können Sie die Reihenfolge angeben, in der sie angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="edd5a-186">**Priority**: If you create multiple policies, you can specify the order that they're applied.</span></span> <span data-ttu-id="edd5a-187">Keine zwei Richtlinien können die gleiche Priorität aufweisen, und die Richtlinienverarbeitung endet, nachdem die erste Richtlinie angewendet wurde.</span><span class="sxs-lookup"><span data-stu-id="edd5a-187">No two policies can have the same priority, and policy processing stops after the first policy is applied.</span></span>

  <span data-ttu-id="edd5a-188">Weitere Informationen über die Prioritätsreihenfolge und darüber, wie mehrere Richtlinien ausgewertet und angewendet werden, finden Sie unter [Reihenfolge und Priorität beim E-Mail-Schutz](how-policies-and-protections-are-combined.md).</span><span class="sxs-lookup"><span data-stu-id="edd5a-188">For more information about the order of precedence and how multiple policies are evaluated and applied, see [Order and precedence of email protection](how-policies-and-protections-are-combined.md).</span></span>

### <a name="dynamic-delivery-in-safe-attachments-policies"></a><span data-ttu-id="edd5a-189">Dynamische Übermittlung in Richtlinien für sichere Anlagen</span><span class="sxs-lookup"><span data-stu-id="edd5a-189">Dynamic Delivery in Safe Attachments policies</span></span>

> [!NOTE]
> <span data-ttu-id="edd5a-190">Die dynamische Zustellung funktioniert nur für Exchange Online-Postfächer.</span><span class="sxs-lookup"><span data-stu-id="edd5a-190">Dynamic Delivery works only for Exchange Online mailboxes.</span></span>

<span data-ttu-id="edd5a-191">Die Dynamische Zustellungsaktion in Richtlinien für sichere Anlagen versucht, Verzögerungen bei der E-Mail-Zustellung zu vermeiden, die durch die Überprüfung sicherer Anlagen verursacht werden können.</span><span class="sxs-lookup"><span data-stu-id="edd5a-191">The Dynamic Delivery action in Safe Attachments policies seeks to eliminate any email delivery delays that might be caused by Safe Attachments scanning.</span></span> <span data-ttu-id="edd5a-192">Der Textkörper der E-Mail-Nachricht wird dem Empfänger mit einem Platzhalter für jede Anlage zugestellt.</span><span class="sxs-lookup"><span data-stu-id="edd5a-192">The body of the email message is delivered to the recipient with a placeholder for each attachment.</span></span> <span data-ttu-id="edd5a-193">Der Platzhalter bleibt erhalten, bis die Anlage als sicher eingestuft wird, und dann steht die Anlage zum Öffnen oder Herunterladen zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="edd5a-193">The placeholder remains until the attachment is found to be safe, and then the attachment becomes available to open or download.</span></span>

<span data-ttu-id="edd5a-194">Wenn eine Anlage als schädlich festgestellt wird, wird die Nachricht in Quarantäne gestellt.</span><span class="sxs-lookup"><span data-stu-id="edd5a-194">If an attachment is found to be malicious, the message is quarantined.</span></span> <span data-ttu-id="edd5a-195">Nur Administratoren (nicht Endbenutzer) können Nachrichten überprüfen, veröffentlichen oder löschen, die von der Überprüfung sicherer Anlagen isoliert wurden.</span><span class="sxs-lookup"><span data-stu-id="edd5a-195">Only admins (not end-users) can review, release, or delete messages that were quarantined by Safe Attachments scanning.</span></span> <span data-ttu-id="edd5a-196">Weitere Informationen finden Sie unter [Manage quarantined messages and files as an admin](manage-quarantined-messages-and-files.md).</span><span class="sxs-lookup"><span data-stu-id="edd5a-196">For more information, see [Manage quarantined messages and files as an admin](manage-quarantined-messages-and-files.md).</span></span>

<span data-ttu-id="edd5a-197">Die meisten PDFs und Office-Dokumente können im abgesicherten Modus in der Vorschau angezeigt werden, während die Überprüfung sicherer Anlagen ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="edd5a-197">Most PDFs and Office documents can be previewed in safe mode while Safe Attachments scanning is underway.</span></span> <span data-ttu-id="edd5a-198">Wenn eine Anlage nicht mit der Vorschau für dynamische Übermittlung kompatibel ist, wird den Empfängern ein Platzhalter für die Anlage angezeigt, bis die Überprüfung sicherer Anlagen abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="edd5a-198">If an attachment is not compatible with the Dynamic Delivery previewer, the recipients will see a placeholder for the attachment until Safe Attachments scanning is complete.</span></span>

<span data-ttu-id="edd5a-199">Wenn Sie ein mobiles Gerät verwenden und PDFs nicht im Vorschaufenster für die dynamische Übermittlung auf Ihrem mobilen Gerät gerendert werden, versuchen Sie, die Nachricht in Outlook im Web (früher als Outlook Web App bezeichnet) mit Ihrem mobilen Browser zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="edd5a-199">If you're using a mobile device, and PDFs aren't rendering in the Dynamic Delivery previewer on your mobile device, try opening the message in Outlook on the web (formerly known as Outlook Web App) using your mobile browser.</span></span>

<span data-ttu-id="edd5a-200">Hier sind einige Überlegungen zur dynamischen Übermittlung und weitergeleiteten Nachrichten:</span><span class="sxs-lookup"><span data-stu-id="edd5a-200">Here are some considerations for Dynamic Delivery and forwarded messages:</span></span>

- <span data-ttu-id="edd5a-201">Wenn der weitergeleitete Empfänger durch eine Richtlinie für sichere Anlagen geschützt ist, die die Option Dynamische Übermittlung verwendet, wird dem Empfänger der Platzhalter mit der Möglichkeit angezeigt, eine Vorschau kompatibler Dateien anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="edd5a-201">If the forwarded recipient is protected by a Safe Attachments policy that uses the Dynamic Delivery option, then the recipient sees the placeholder, with the ability to preview compatible files.</span></span>

- <span data-ttu-id="edd5a-202">Wenn der weitergeleitete Empfänger nicht durch eine Richtlinie für sichere Anlagen geschützt ist, werden die Nachricht und Anlagen ohne Überprüfung durch sichere Anlagen oder Anlagenplatzhalter zugestellt.</span><span class="sxs-lookup"><span data-stu-id="edd5a-202">If the forwarded recipient is not protected by a Safe Attachments policy, the message and attachments will be delivered without any Safe Attachments scanning or attachment placeholders.</span></span>

<span data-ttu-id="edd5a-203">Es gibt Szenarien, in denen die dynamische Übermittlung Anlagen in Nachrichten nicht ersetzen kann.</span><span class="sxs-lookup"><span data-stu-id="edd5a-203">There are scenarios where Dynamic Delivery is unable to replace attachments in messages.</span></span> <span data-ttu-id="edd5a-204">Diese Szenarien umfassen:</span><span class="sxs-lookup"><span data-stu-id="edd5a-204">These scenarios include:</span></span>

- <span data-ttu-id="edd5a-205">Nachrichten in öffentlichen Ordnern.</span><span class="sxs-lookup"><span data-stu-id="edd5a-205">Messages in public folders.</span></span>

- <span data-ttu-id="edd5a-206">Nachrichten, die mithilfe von benutzerdefinierten Regeln aus und dann wieder in das Postfach eines Benutzers geroutet werden.</span><span class="sxs-lookup"><span data-stu-id="edd5a-206">Messages that are routed out of and then back into a user's mailbox using custom rules.</span></span>

- <span data-ttu-id="edd5a-207">Nachrichten, die (automatisch oder manuell) aus Cloudpostfächern an andere Speicherorte verschoben werden, einschließlich Archivordnern.</span><span class="sxs-lookup"><span data-stu-id="edd5a-207">Messages that are moved (automatically or manually) out of cloud mailboxes to other locations, including archive folders.</span></span>

- <span data-ttu-id="edd5a-208">Gelöschte Nachrichten.</span><span class="sxs-lookup"><span data-stu-id="edd5a-208">Deleted messages.</span></span>

- <span data-ttu-id="edd5a-209">Der Postfachsuchordner des Benutzers befindet sich im Fehlerstatus.</span><span class="sxs-lookup"><span data-stu-id="edd5a-209">The user's mailbox search folder is in an error state.</span></span>

- <span data-ttu-id="edd5a-210">Exchange Online-Organisationen, in denen Exclaimer aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="edd5a-210">Exchange Online organizations where Exclaimer is enabled.</span></span> <span data-ttu-id="edd5a-211">Informationen dazu finden Sie unter [KB4014438](https://support.microsoft.com/help/4014438).</span><span class="sxs-lookup"><span data-stu-id="edd5a-211">To resolve this, see [KB4014438](https://support.microsoft.com/help/4014438).</span></span>

- <span data-ttu-id="edd5a-212">[S/MIME)](s-mime-for-message-signing-and-encryption.md) verschlüsselte Nachrichten.</span><span class="sxs-lookup"><span data-stu-id="edd5a-212">[S/MIME)](s-mime-for-message-signing-and-encryption.md) encrypted messages.</span></span>

- <span data-ttu-id="edd5a-213">Sie haben die Dynamische Zustellungsaktion in einer Richtlinie für sichere Anlagen konfiguriert, der Empfänger unterstützt jedoch keine dynamische Zustellung (z. B. ist der Empfänger ein Postfach in einer lokalen Exchange-Organisation).</span><span class="sxs-lookup"><span data-stu-id="edd5a-213">You configured the Dynamic Delivery action in a Safe Attachments policy, but the recipient doesn't support Dynamic Delivery (for example, the recipient is a mailbox in an on-premises Exchange organization).</span></span> <span data-ttu-id="edd5a-214">Sichere Links [in Microsoft Defender für Office 365](set-up-safe-links-policies.md) können jedoch Office-Dateianlagen überprüfen, die URLs enthalten (je nachdem, wie die globalen Einstellungen für sichere Links [konfiguriert](configure-global-settings-for-safe-links.md) sind).</span><span class="sxs-lookup"><span data-stu-id="edd5a-214">However, [Safe Links in Microsoft Defender for Office 365](set-up-safe-links-policies.md) is able to scan Office file attachments that contain URLs (depending on how the [global settings for Safe Links](configure-global-settings-for-safe-links.md) are configured).</span></span>

## <a name="submitting-files-for-malware-analysis"></a><span data-ttu-id="edd5a-215">Übermitteln von Dateien für die Schadsoftwareanalyse</span><span class="sxs-lookup"><span data-stu-id="edd5a-215">Submitting files for malware analysis</span></span>

- <span data-ttu-id="edd5a-216">Wenn Sie eine Datei erhalten, die Sie zur Analyse an Microsoft senden möchten, finden Sie unter [Submit malware and non-malware to Microsoft for analysis](submitting-malware-and-non-malware-to-microsoft-for-analysis.md).</span><span class="sxs-lookup"><span data-stu-id="edd5a-216">If you receive a file that you want to send to Microsoft for analysis, see [Submit malware and non-malware to Microsoft for analysis](submitting-malware-and-non-malware-to-microsoft-for-analysis.md).</span></span>

- <span data-ttu-id="edd5a-217">Wenn Sie eine E-Mail-Nachricht (mit oder ohne Anlage) erhalten, die Sie zur Analyse an Microsoft übermitteln möchten, lesen Sie Melden von Nachrichten und Dateien [an Microsoft](report-junk-email-messages-to-microsoft.md).</span><span class="sxs-lookup"><span data-stu-id="edd5a-217">If you receive an email message (with or without an attachment) that you want to submit to Microsoft for analysis, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>