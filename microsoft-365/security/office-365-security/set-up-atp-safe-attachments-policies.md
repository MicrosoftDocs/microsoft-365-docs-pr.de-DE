---
title: Einrichten von Richtlinien für sichere Anlagen in Office 365 ATP
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 078eb946-819a-4e13-8673-fe0c0ad3a775
ms.collection:
- M365-security-compliance
description: In diesem Artikel erfahren Sie, wie Sie Richtlinien für sichere Anlagen zum Schutz Ihrer Organisation vor bösartigen Dateien in e-Mails definieren.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 6794cf72afdb94e587e06319f87a406521ad2710
ms.sourcegitcommit: 3a0accd616ca94d6ba7f50e502552b45e9661a95
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/03/2020
ms.locfileid: "48350373"
---
# <a name="set-up-safe-attachments-policies-in-office-365-atp"></a><span data-ttu-id="95b54-103">Einrichten von Richtlinien für sichere Anlagen in Office 365 ATP</span><span class="sxs-lookup"><span data-stu-id="95b54-103">Set up Safe Attachments policies in Office 365 ATP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

> [!IMPORTANT]
> <span data-ttu-id="95b54-104">Dieser Artikel richtet sich an Geschäftskunden, die [Office 365 Advanced Threat Protection (ATP)](office-365-atp.md)haben.</span><span class="sxs-lookup"><span data-stu-id="95b54-104">This article is intended for business customers who have [Office 365 Advanced Threat Protection (ATP)](office-365-atp.md).</span></span> <span data-ttu-id="95b54-105">Wenn Sie ein Privatbenutzer sind, der nach Informationen zum Anlagen Scan in Outlook sucht, lesen Sie [Erweiterte Outlook.com-Sicherheit](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).</span><span class="sxs-lookup"><span data-stu-id="95b54-105">If you're a home user looking for information about attachment scanning in Outlook, see [Advanced Outlook.com security](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).</span></span>

<span data-ttu-id="95b54-106">Sichere Anlagen ist ein Feature in [Office 365 Advanced Threat Protection (ATP)](office-365-atp.md) , das eine virtuelle Umgebung verwendet, um Anlagen in eingehenden e-Mail-Nachrichten zu überprüfen, nachdem Sie durch den [Schutz vor Schadsoftware in Exchange Online Protection (EoP)](anti-malware-protection.md), jedoch vor der Zustellung an die Empfänger überprüft wurden.</span><span class="sxs-lookup"><span data-stu-id="95b54-106">Safe Attachments is a feature in [Office 365 Advanced Threat Protection (ATP)](office-365-atp.md) that uses a virtual environment to check attachments in inbound email messages after they've been scanned by [anti-malware protection in Exchange Online Protection (EOP)](anti-malware-protection.md), but before delivery to recipients.</span></span> <span data-ttu-id="95b54-107">Weitere Informationen finden Sie unter [sichere Anlagen in Office 365 ATP](atp-safe-attachments.md).</span><span class="sxs-lookup"><span data-stu-id="95b54-107">For more information, see [Safe Attachments in Office 365 ATP](atp-safe-attachments.md).</span></span>

<span data-ttu-id="95b54-108">Es gibt keine Richtlinie für integrierte oder standardmäßige sichere Anlagen.</span><span class="sxs-lookup"><span data-stu-id="95b54-108">There's no built-in or default Safe Attachments policy.</span></span> <span data-ttu-id="95b54-109">Wenn Sie sichere Anlagen überprüfen von e-Mail-Nachrichtenanlagen erhalten möchten, müssen Sie eine oder mehrere Richtlinien für sichere Anlagen wie in diesem Artikel beschrieben erstellen.</span><span class="sxs-lookup"><span data-stu-id="95b54-109">To get Safe Attachments scanning of email message attachments, you need to create one or more Safe Attachments policies as described in this article.</span></span>

<span data-ttu-id="95b54-110">Sie können Richtlinien für sichere Anlagen im Security & Compliance Center oder in PowerShell (Exchange Online PowerShell für berechtigte Microsoft 365-Organisationen mit Postfächern in Exchange Online; eigenständige EoP PowerShell für Organisationen ohne Exchange Online Postfächer, aber mit Office 365 ATP-Add-on-Abonnements) konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="95b54-110">You can configure Safe Attachments policies in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for eligible Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes, but with Office 365 ATP add-on subscriptions).</span></span>

<span data-ttu-id="95b54-111">Die grundlegenden Elemente einer Richtlinie für sichere Anlagen sind:</span><span class="sxs-lookup"><span data-stu-id="95b54-111">The basic elements of a Safe Attachments policy are:</span></span>

- <span data-ttu-id="95b54-112">**Richtlinie für sichere Anlagen**: gibt die Aktionen für unbekannte Malwareerkennungen an, ob Nachrichten mit Schadsoftware-Anlagen an eine angegebene e-Mail-Adresse gesendet werden sollen und ob Nachrichten übermittelt werden können, wenn die Überprüfung durch sichere Anlagen nicht abgeschlossen werden kann</span><span class="sxs-lookup"><span data-stu-id="95b54-112">**The safe attachment policy**: Specifies the actions for unknown malware detections, whether to send messages with malware attachments to a specified email address, and whether to deliver messages if Safe Attachments scanning can't complete.</span></span>
- <span data-ttu-id="95b54-113">**Die Regel für sichere Anlagen**: gibt die Priorität und die Empfängerfilter (für wen die Richtlinie gilt) an.</span><span class="sxs-lookup"><span data-stu-id="95b54-113">**The safe attachment rule**: Specifies the priority and recipient filters (who the policy applies to).</span></span>

<span data-ttu-id="95b54-114">Der Unterschied zwischen diesen beiden Elementen ist nicht offensichtlich, wenn Sie Richtlinien für sichere Anlagen im Security & Compliance Center verwalten:</span><span class="sxs-lookup"><span data-stu-id="95b54-114">The difference between these two elements isn't obvious when you manage Safe Attachments polices in the Security & Compliance Center:</span></span>

- <span data-ttu-id="95b54-115">Wenn Sie eine Richtlinie für sichere Anlagen erstellen, erstellen Sie tatsächlich eine Regel für sichere Anlagen und die zugehörige Richtlinie für sichere Anlagen gleichzeitig mit dem gleichen Namen für beide.</span><span class="sxs-lookup"><span data-stu-id="95b54-115">When you create a Safe Attachments policy, you're actually creating a safe attachment rule and the associated safe attachment policy at the same time using the same name for both.</span></span>
- <span data-ttu-id="95b54-116">Wenn Sie eine Richtlinie für sichere Anlagen ändern, ändern die Einstellungen im Zusammenhang mit dem Namen, der Priorität, den aktivierten oder deaktivierten und den Empfänger filtern die Regel für sichere Anlagen.</span><span class="sxs-lookup"><span data-stu-id="95b54-116">When you modify a Safe Attachments policy, settings related to the name, priority, enabled or disabled, and recipient filters modify the safe attachment rule.</span></span> <span data-ttu-id="95b54-117">Alle anderen Einstellungen ändern die zugehörige Richtlinie für sichere Anlagen.</span><span class="sxs-lookup"><span data-stu-id="95b54-117">All other settings modify the associated safe attachment policy.</span></span>
- <span data-ttu-id="95b54-118">Wenn Sie eine Richtlinie für sichere Anlagen entfernen, werden die Regel für sichere Anlagen und die zugehörige Richtlinie für sichere Anlagen entfernt.</span><span class="sxs-lookup"><span data-stu-id="95b54-118">When you remove a Safe Attachments policy, the safe attachment rule and the associated safe attachment policy are removed.</span></span>

<span data-ttu-id="95b54-119">In Exchange Online PowerShell oder der eigenständigen EOP PowerShell verwalten Sie die Richtlinie und die Regel getrennt.</span><span class="sxs-lookup"><span data-stu-id="95b54-119">In Exchange Online PowerShell or standalone EOP PowerShell, you manage the policy and the rule separately.</span></span> <span data-ttu-id="95b54-120">Weitere Informationen finden Sie im Abschnitt [Verwenden von Exchange Online PowerShell oder eigenständiger EoP PowerShell zum Konfigurieren von Richtlinien für sichere Anlagen](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-attachments-policies) weiter unten in diesem Artikel.</span><span class="sxs-lookup"><span data-stu-id="95b54-120">For more information, see the [Use Exchange Online PowerShell or standalone EOP PowerShell to configure Safe Attachments policies](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-attachments-policies) section later in this article.</span></span>

> [!NOTE]
> <span data-ttu-id="95b54-121">Im Bereich Globale Einstellungen der Einstellungen für sichere Anlagen konfigurieren Sie Features, die nicht von Richtlinien für sichere Anlagen abhängig sind.</span><span class="sxs-lookup"><span data-stu-id="95b54-121">In the global settings area of Safe Attachments settings, you configure features that are not dependent on Safe Attachments policies.</span></span> <span data-ttu-id="95b54-122">Anweisungen finden Sie unter [Aktivieren von ATP für SharePoint, OneDrive und Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md) und [sichere Dokumente in Microsoft 365 E5](safe-docs.md).</span><span class="sxs-lookup"><span data-stu-id="95b54-122">For instructions see [Turn on ATP for SharePoint, OneDrive, and Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md) and [Safe Documents in Microsoft 365 E5](safe-docs.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="95b54-123">Was sollten Sie wissen, bevor Sie beginnen?</span><span class="sxs-lookup"><span data-stu-id="95b54-123">What do you need to know before you begin?</span></span>

- <span data-ttu-id="95b54-124">Sie öffnen das Security & Compliance Center unter <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="95b54-124">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="95b54-125">Wenn Sie direkt zur Seite **ATP-sichere Anlagen** wechseln möchten, verwenden Sie <https://protection.office.com/safeattachmentv2> .</span><span class="sxs-lookup"><span data-stu-id="95b54-125">To go directly to the **ATP Safe Attachments** page, use <https://protection.office.com/safeattachmentv2>.</span></span>

- <span data-ttu-id="95b54-126">Wie Sie eine Verbindung mit Exchange Online PowerShell herstellen, finden Sie unter [Herstellen einer Verbindung mit Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="95b54-126">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="95b54-127">Informationen zum Herstellen einer Verbindung mit dem eigenständigen Exchange Online Protection PowerShell finden Sie unter [Verbinden mit PowerShell in Exchange Online Protection](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="95b54-127">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="95b54-128">Zum Anzeigen, erstellen, ändern und Löschen von Richtlinien für sichere Anlagen müssen Sie Mitglied einer der folgenden Rollengruppen sein:</span><span class="sxs-lookup"><span data-stu-id="95b54-128">To view, create, modify, and delete Safe Attachments policies, you need to be a member of one of the following role groups:</span></span>

  - <span data-ttu-id="95b54-129">**Organisationsverwaltung** oder **Sicherheitsadministrator** im [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="95b54-129">**Organization Management** or **Security Administrator** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
  - <span data-ttu-id="95b54-130">**Organisationsverwaltung** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span><span class="sxs-lookup"><span data-stu-id="95b54-130">**Organization Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

- <span data-ttu-id="95b54-131">Unsere empfohlenen Einstellungen für Richtlinien zu sicheren Anlagen finden Sie unter [Safe Attachments Settings](recommended-settings-for-eop-and-office365-atp.md#safe-attachments-settings).</span><span class="sxs-lookup"><span data-stu-id="95b54-131">For our recommended settings for Safe Attachments policies, see [Safe Attachments settings](recommended-settings-for-eop-and-office365-atp.md#safe-attachments-settings).</span></span>

- <span data-ttu-id="95b54-132">Erlauben Sie bis zu 30 Minuten, bis eine neue oder aktualisierte Richtlinie angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="95b54-132">Allow up to 30 minutes for a new or updated policy to be applied.</span></span>

## <a name="use-the-security--compliance-center-to-create-safe-attachments-policies"></a><span data-ttu-id="95b54-133">Verwenden des Security & Compliance Center zum Erstellen von Richtlinien für sichere Anlagen</span><span class="sxs-lookup"><span data-stu-id="95b54-133">Use the Security & Compliance Center to create Safe Attachments policies</span></span>

<span data-ttu-id="95b54-134">Durch das Erstellen einer benutzerdefinierten Richtlinie für sichere Anlagen im Security & Compliance Center werden die Regel für sichere Anlagen und die zugeordnete Richtlinie für sichere Anlagen gleichzeitig mit dem gleichen Namen für beide erstellt.</span><span class="sxs-lookup"><span data-stu-id="95b54-134">Creating a custom Safe Attachments policy in the Security & Compliance Center creates the safe attachment rule and the associated safe attachment policy at the same time using the same name for both.</span></span>

1. <span data-ttu-id="95b54-135">Wechseln Sie im Security & Compliance Center zu **Threat Management** \> **Policy** \> **ATP Safe Attachments**.</span><span class="sxs-lookup"><span data-stu-id="95b54-135">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Attachments**.</span></span>

2. <span data-ttu-id="95b54-136">Klicken Sie auf der Seite **sichere Anlagen** auf **Erstellen**.</span><span class="sxs-lookup"><span data-stu-id="95b54-136">On the **Safe Attachments** page, click **Create**.</span></span>

3. <span data-ttu-id="95b54-137">Der Assistent für **neue Richtlinien für sichere Anlagen** wird geöffnet.</span><span class="sxs-lookup"><span data-stu-id="95b54-137">The **New Safe Attachments policy** wizard opens.</span></span> <span data-ttu-id="95b54-138">Konfigurieren Sie auf der Seite **Ihre Richtlinie benennen** die folgenden Einstellungen:</span><span class="sxs-lookup"><span data-stu-id="95b54-138">On the **Name your policy** page, configure the following settings:</span></span>

   - <span data-ttu-id="95b54-139">**Name**: Geben Sie einen eindeutigen, aussagekräftigen Namen für die Richtlinie ein.</span><span class="sxs-lookup"><span data-stu-id="95b54-139">**Name**: Enter a unique, descriptive name for the policy.</span></span>

   - <span data-ttu-id="95b54-140">**Beschreibung**: Geben Sie eine optionale Beschreibung für die Richtlinie ein.</span><span class="sxs-lookup"><span data-stu-id="95b54-140">**Description**: Enter an optional description for the policy.</span></span>

   <span data-ttu-id="95b54-141">Klicken Sie nach Abschluss des Vorgangs auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="95b54-141">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="95b54-142">Konfigurieren Sie auf der angezeigten Seite **Einstellungen** die folgenden Einstellungen:</span><span class="sxs-lookup"><span data-stu-id="95b54-142">On the **Settings** page that appears, configure the following settings:</span></span>

   - <span data-ttu-id="95b54-143">**Sichere Anlagen unbekannte Malware Antwort**: Wählen Sie einen der folgenden Werte aus:</span><span class="sxs-lookup"><span data-stu-id="95b54-143">**Safe Attachments unknown malware response**: Select one of the following values:</span></span>

     - <span data-ttu-id="95b54-144">**Off**: Normalerweise wird dieser Wert nicht empfohlen.</span><span class="sxs-lookup"><span data-stu-id="95b54-144">**Off**: Typically, we don't recommend this value.</span></span>
     - <span data-ttu-id="95b54-145">**Überwachen**</span><span class="sxs-lookup"><span data-stu-id="95b54-145">**Monitor**</span></span>
     - <span data-ttu-id="95b54-146">**Block**: Dies ist der Standardwert und der empfohlene Wert in standardmäßigen und streng [voreingestellten Sicherheitsrichtlinien](preset-security-policies.md).</span><span class="sxs-lookup"><span data-stu-id="95b54-146">**Block**: This is the default value, and the recommended value in Standard and Strict [preset security policies](preset-security-policies.md).</span></span>
     - <span data-ttu-id="95b54-147">**Replace**</span><span class="sxs-lookup"><span data-stu-id="95b54-147">**Replace**</span></span>
     - <span data-ttu-id="95b54-148">**Dynamische Zustellung (Vorschau-Feature)**</span><span class="sxs-lookup"><span data-stu-id="95b54-148">**Dynamic Delivery (Preview Feature)**</span></span>

     <span data-ttu-id="95b54-149">Diese Werte werden unter [Richtlinieneinstellungen für sichere Anlagen](atp-safe-attachments.md#safe-attachments-policy-settings)erläutert.</span><span class="sxs-lookup"><span data-stu-id="95b54-149">These values are explained in [Safe Attachments policy settings](atp-safe-attachments.md#safe-attachments-policy-settings).</span></span>

   - <span data-ttu-id="95b54-150">**Senden Sie die Anlage an die folgende e-Mail-Adresse**: für die Aktionswerte **blockieren**, **überwachen**oder **ersetzen**können Sie die Option **Umleitung aktivieren** auswählen, um Nachrichten mit Schadsoftware-Anlagen zur Analyse und Untersuchung an die angegebene interne oder externe e-Mail-Adresse zu senden.</span><span class="sxs-lookup"><span data-stu-id="95b54-150">**Send the attachment to the following email address**: For the action values **Block**, **Monitor**, or **Replace**, you can select **Enable redirect** to send messages that contain malware attachments to the specified internal or external email address for analysis and investigation.</span></span>

     <span data-ttu-id="95b54-151">Die Empfehlung für Standard mäßige und strenge Richtlinieneinstellungen besteht darin, die Umleitung zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="95b54-151">The recommendation for Standard and Strict policy settings is to enable redirection.</span></span> <span data-ttu-id="95b54-152">Weitere Informationen finden Sie unter [Einstellungen für sichere Anlagen](recommended-settings-for-eop-and-office365-atp.md#safe-attachments-settings).</span><span class="sxs-lookup"><span data-stu-id="95b54-152">For more information, see [Safe Attachments settings](recommended-settings-for-eop-and-office365-atp.md#safe-attachments-settings).</span></span>

   - <span data-ttu-id="95b54-153">**Wenden Sie die obige Auswahl an, wenn bei der Malwareüberprüfung für Anlagen ein Timeout auftritt oder ein Fehler auftritt**: die durch **sichere Anlagen unbekannte Schadsoftware-Antwort** angegebene Aktion wird auf Nachrichten angewendet, auch wenn der sichere Anlagen Scan nicht abgeschlossen werden kann.</span><span class="sxs-lookup"><span data-stu-id="95b54-153">**Apply the above selection if malware scanning for attachments times out or error occurs**: The action specified by **Safe Attachments unknown malware response** is taken on messages even when Safe Attachments scanning can't complete.</span></span> <span data-ttu-id="95b54-154">Wählen Sie diese Option immer aus, wenn Sie **aktivierte Umleitung**auswählen.</span><span class="sxs-lookup"><span data-stu-id="95b54-154">Always select this option if you select **Enabled redirect**.</span></span> <span data-ttu-id="95b54-155">Andernfalls gehen möglicherweise Nachrichten verloren.</span><span class="sxs-lookup"><span data-stu-id="95b54-155">Otherwise, messages might be lost.</span></span>

   <span data-ttu-id="95b54-156">Klicken Sie nach Abschluss des Vorgangs auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="95b54-156">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="95b54-157">Identifizieren Sie auf der Seite **angewendet auf** , die angezeigt wird, die internen Empfänger, auf die die Richtlinie angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="95b54-157">On the **Applied to** page that appears, identify the internal recipients that the policy applies to.</span></span>

   <span data-ttu-id="95b54-158">Sie können eine Bedingung oder Ausnahme nur einmal verwenden, aber Sie können mehrere Werte für die Bedingung oder Ausnahme angeben.</span><span class="sxs-lookup"><span data-stu-id="95b54-158">You can only use a condition or exception once, but you can specify multiple values for the condition or exception.</span></span> <span data-ttu-id="95b54-159">Bei mehreren Werten derselben Bedingung oder Ausnahme wird ODER-Logik verwendet (z. B. _\<recipient1\>_ oder _\<recipient2\>_).</span><span class="sxs-lookup"><span data-stu-id="95b54-159">Multiple values of the same condition or exception use OR logic (for example, _\<recipient1\>_ or _\<recipient2\>_).</span></span> <span data-ttu-id="95b54-160">Bei unterschiedlichen Bedingungen oder Ausnahmen wird UND-Logik verwendet (z. B. _\<recipient1\>_ und _\<member of group 1\>_).</span><span class="sxs-lookup"><span data-stu-id="95b54-160">Different conditions or exceptions use AND logic (for example, _\<recipient1\>_ and _\<member of group 1\>_).</span></span>

   <span data-ttu-id="95b54-161">Klicken Sie auf **Bedingung hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="95b54-161">Click **Add a condition**.</span></span> <span data-ttu-id="95b54-162">Wählen Sie in der Dropdownliste, die angezeigt wird, eine Bedingung unter **angewendet, wenn**:</span><span class="sxs-lookup"><span data-stu-id="95b54-162">In the dropdown that appears, select a condition under **Applied if**:</span></span>

   - <span data-ttu-id="95b54-163">**Der Empfänger lautet**: gibt ein oder mehrere Postfächer, e-Mail-Benutzer oder e-Mail-Kontakte in Ihrer Organisation an.</span><span class="sxs-lookup"><span data-stu-id="95b54-163">**The recipient is**: Specifies one or more mailboxes, mail users, or mail contacts in your organization.</span></span>
   - <span data-ttu-id="95b54-164">**Der Empfänger ist Mitglied von**: gibt eine oder mehrere Gruppen in Ihrer Organisation an.</span><span class="sxs-lookup"><span data-stu-id="95b54-164">**The recipient is a member of**: Specifies one or more groups in your organization.</span></span>
   - <span data-ttu-id="95b54-165">**Die Empfängerdomäne ist**: Gibt Empfänger in einer oder mehreren der konfigurierten akzeptierten Domänen in Ihrer Organisation an.</span><span class="sxs-lookup"><span data-stu-id="95b54-165">**The recipient domain is**: Specifies recipients in one or more of the configured accepted domains in your organization.</span></span>

   <span data-ttu-id="95b54-166">Nachdem Sie die Bedingung ausgewählt haben, wird eine entsprechende Dropdownliste mit einem **der folgenden** Felder angezeigt.</span><span class="sxs-lookup"><span data-stu-id="95b54-166">After you select the condition, a corresponding dropdown appears with an **Any of these** box.</span></span>

   - <span data-ttu-id="95b54-167">Klicken Sie in das Feld, und führen Sie einen Bildlauf durch die Liste der zu markierende Werte durch.</span><span class="sxs-lookup"><span data-stu-id="95b54-167">Click in the box and scroll through the list of values to select.</span></span>
   - <span data-ttu-id="95b54-168">Klicken Sie in das Feld, und beginnen Sie mit der Eingabe, um die Liste zu filtern und einen Wert auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="95b54-168">Click in the box and start typing to filter the list and select a value.</span></span>
   - <span data-ttu-id="95b54-169">Klicken Sie zum Hinzufügen weiterer Werte in einen leeren Bereich des Felds.</span><span class="sxs-lookup"><span data-stu-id="95b54-169">To add additional values, click in an empty area in the box.</span></span>
   - <span data-ttu-id="95b54-170">Wenn Sie einzelne Einträge entfernen möchten **Remove** , klicken Sie auf Entfernen- ![ Symbol ](../../media/scc-remove-icon.png) für den Wert entfernen.</span><span class="sxs-lookup"><span data-stu-id="95b54-170">To remove individual entries, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the value.</span></span>
   - <span data-ttu-id="95b54-171">Wenn Sie die gesamte Bedingung entfernen möchten **, klicken Sie** ![ in der Bedingung auf entfernen-Symbol Entfernen ](../../media/scc-remove-icon.png) .</span><span class="sxs-lookup"><span data-stu-id="95b54-171">To remove the whole condition, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the condition.</span></span>

   <span data-ttu-id="95b54-172">Klicken Sie zum Hinzufügen einer zusätzlichen Bedingung auf **Bedingung hinzufügen** , und wählen Sie einen verbleibenden Wert unter **angewendet bei**aus.</span><span class="sxs-lookup"><span data-stu-id="95b54-172">To add an additional condition, click **Add a condition** and select a remaining value under **Applied if**.</span></span>

   <span data-ttu-id="95b54-173">Wenn Sie Ausnahmen hinzufügen möchten, klicken Sie auf **Bedingung hinzufügen** , und wählen Sie unter **außer if**eine Ausnahme aus.</span><span class="sxs-lookup"><span data-stu-id="95b54-173">To add exceptions, click **Add a condition** and select an exception under **Except if**.</span></span> <span data-ttu-id="95b54-174">Die Einstellungen und das Verhalten entsprechen genau den Bedingungen.</span><span class="sxs-lookup"><span data-stu-id="95b54-174">The settings and behavior are exactly like the conditions.</span></span>

   <span data-ttu-id="95b54-175">Klicken Sie nach Abschluss des Vorgangs auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="95b54-175">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="95b54-176">Überprüfen Sie auf der angezeigten Seite **Ihre Einstellungen überprüfen** Ihre Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="95b54-176">On the **Review your settings** page that appears, review your settings.</span></span> <span data-ttu-id="95b54-177">Sie können auf jeder Einstellung auf **Bearbeiten** klicken, um Sie zu ändern.</span><span class="sxs-lookup"><span data-stu-id="95b54-177">You can click **Edit** on each setting to modify it.</span></span>

   <span data-ttu-id="95b54-178">Klicken Sie nach Abschluss des Vorgangs auf **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="95b54-178">When you're finished, click **Finish**.</span></span>

## <a name="use-the-security--compliance-center-to-view-safe-attachments-policies"></a><span data-ttu-id="95b54-179">Verwenden des Security & Compliance Center zum Anzeigen von Richtlinien für sichere Anlagen</span><span class="sxs-lookup"><span data-stu-id="95b54-179">Use the Security & Compliance Center to view Safe Attachments policies</span></span>

1. <span data-ttu-id="95b54-180">Wechseln Sie im Security & Compliance Center zu **Threat Management** \> **Policy** \> **ATP Safe Attachments**.</span><span class="sxs-lookup"><span data-stu-id="95b54-180">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Attachments**.</span></span>

2. <span data-ttu-id="95b54-181">Wählen Sie auf der Seite **sichere Anlagen** eine Richtlinie aus der Liste aus, und klicken Sie darauf (aktivieren Sie das Kontrollkästchen nicht).</span><span class="sxs-lookup"><span data-stu-id="95b54-181">On the **Safe Attachments** page, select a policy from the list and click on it (don't select the check box).</span></span>

   <span data-ttu-id="95b54-182">Die Richtliniendetails werden in einem Fly Out angezeigt.</span><span class="sxs-lookup"><span data-stu-id="95b54-182">The policy details appear in a fly out</span></span>

## <a name="use-the-security--compliance-center-to-modify-safe-attachments-policies"></a><span data-ttu-id="95b54-183">Verwenden des Security & Compliance Center zum Ändern von Richtlinien für sichere Anlagen</span><span class="sxs-lookup"><span data-stu-id="95b54-183">Use the Security & Compliance Center to modify Safe Attachments policies</span></span>

1. <span data-ttu-id="95b54-184">Wechseln Sie im Security & Compliance Center zu **Threat Management** \> **Policy** \> **ATP Safe Attachments**.</span><span class="sxs-lookup"><span data-stu-id="95b54-184">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Attachments**.</span></span>

2. <span data-ttu-id="95b54-185">Wählen Sie auf der Seite **sichere Anlagen** eine Richtlinie aus der Liste aus, und klicken Sie darauf (aktivieren Sie das Kontrollkästchen nicht).</span><span class="sxs-lookup"><span data-stu-id="95b54-185">On the **Safe Attachments** page, select a policy from the list and click on it (don't select the check box).</span></span>

3. <span data-ttu-id="95b54-186">Klicken Sie in der angezeigten Richtlinie Details ausfliegen, die angezeigt wird, auf **Richtlinie bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="95b54-186">In the policy details fly out that appears, click **Edit policy**.</span></span>

<span data-ttu-id="95b54-187">Die verfügbaren Einstellungen im angezeigten ausfliegen sind mit denen identisch, die im Abschnitt [Verwenden der Sicherheits & Compliance Center zum Erstellen von Richtlinien für sichere Anlagen](#use-the-security--compliance-center-to-create-safe-attachments-policies) beschrieben sind.</span><span class="sxs-lookup"><span data-stu-id="95b54-187">The available settings in the fly out that appears are identical to those described in the [Use the Security & Compliance Center to create Safe Attachments policies](#use-the-security--compliance-center-to-create-safe-attachments-policies) section.</span></span>

<span data-ttu-id="95b54-188">Informationen zum Aktivieren oder Deaktivieren einer Richtlinie oder zum Festlegen der Reihenfolge der Richtlinien Priorität finden Sie in den folgenden Abschnitten.</span><span class="sxs-lookup"><span data-stu-id="95b54-188">To enable or disable a policy or set the policy priority order, see the following sections.</span></span>

### <a name="enable-or-disable-safe-attachments-policies"></a><span data-ttu-id="95b54-189">Aktivieren oder Deaktivieren von Richtlinien für sichere Anlagen</span><span class="sxs-lookup"><span data-stu-id="95b54-189">Enable or disable Safe Attachments policies</span></span>

1. <span data-ttu-id="95b54-190">Wechseln Sie im Security & Compliance Center zu **Threat Management** \> **Policy** \> **ATP Safe Attachments**.</span><span class="sxs-lookup"><span data-stu-id="95b54-190">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Attachments**.</span></span>

2. <span data-ttu-id="95b54-191">Beachten Sie den Wert in der Spalte **Status** :</span><span class="sxs-lookup"><span data-stu-id="95b54-191">Notice the value in the **Status** column:</span></span>

   - <span data-ttu-id="95b54-192">Bewegen der Umschaltfläche nach links</span><span class="sxs-lookup"><span data-stu-id="95b54-192">Move the toggle to the left</span></span> ![Deaktivieren der Richtlinie](../../media/scc-toggle-off.png) <span data-ttu-id="95b54-194">, um die Richtlinie zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="95b54-194">to disable the policy.</span></span>

   - <span data-ttu-id="95b54-195">Bewegen der Umschaltfläche nach rechts</span><span class="sxs-lookup"><span data-stu-id="95b54-195">Move the toggle to the right</span></span> ![Richtlinie aktivieren](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png) <span data-ttu-id="95b54-197">, um die Richtlinie zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="95b54-197">to enable the policy.</span></span>

### <a name="set-the-priority-of-safe-attachments-policies"></a><span data-ttu-id="95b54-198">Festlegen der Priorität von Richtlinien für sichere Anlagen</span><span class="sxs-lookup"><span data-stu-id="95b54-198">Set the priority of Safe Attachments policies</span></span>

<span data-ttu-id="95b54-199">Standardmäßig erhalten Richtlinien für sichere Anlagen eine Priorität, die auf der Reihenfolge basiert, in der Sie erstellt wurden (neuere Policen haben eine niedrigere Priorität als ältere Richtlinien).</span><span class="sxs-lookup"><span data-stu-id="95b54-199">By default, Safe Attachments policies are given a priority that's based on the order they were created in (newer polices are lower priority than older policies).</span></span> <span data-ttu-id="95b54-200">Eine niedrigere Prioritätsnummer gibt eine höhere Priorität für die Richtlinie an (0 ist die höchste), und Richtlinien werden in der Reihenfolge der Priorität verarbeitet (Richtlinien mit einer höheren Priorität werden vor Richtlinien mit einer niedrigeren Priorität verarbeitet).</span><span class="sxs-lookup"><span data-stu-id="95b54-200">A lower priority number indicates a higher priority for the policy (0 is the highest), and policies are processed in priority order (higher priority policies are processed before lower priority policies).</span></span> <span data-ttu-id="95b54-201">Keine zwei Richtlinien können die gleiche Priorität aufweisen, und die Richtlinienverarbeitung endet, nachdem die erste Richtlinie angewendet wurde.</span><span class="sxs-lookup"><span data-stu-id="95b54-201">No two policies can have the same priority, and policy processing stops after the first policy is applied.</span></span>

<span data-ttu-id="95b54-202">Weitere Informationen über die Prioritätsreihenfolge und darüber, wie mehrere Richtlinien ausgewertet und angewendet werden, finden Sie unter [Reihenfolge und Priorität beim E-Mail-Schutz](how-policies-and-protections-are-combined.md).</span><span class="sxs-lookup"><span data-stu-id="95b54-202">For more information about the order of precedence and how multiple policies are evaluated and applied, see [Order and precedence of email protection](how-policies-and-protections-are-combined.md).</span></span>

<span data-ttu-id="95b54-203">Richtlinien für sichere Anlagen werden in der Reihenfolge angezeigt, in der Sie verarbeitet werden (die erste Richtlinie hat den **Prioritäts** Wert 0).</span><span class="sxs-lookup"><span data-stu-id="95b54-203">Safe Attachments policies are displayed in the order they're processed (the first policy has the **Priority** value 0).</span></span>

<span data-ttu-id="95b54-204">**Hinweis**: im Security & Compliance Center können Sie die Priorität der Richtlinie für sichere Anlagen nur ändern, nachdem Sie Sie erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="95b54-204">**Note**: In the Security & Compliance Center, you can only change the priority of the Safe Attachments policy after you create it.</span></span> <span data-ttu-id="95b54-205">In PowerShell können Sie die Standardpriorität außer Kraft setzen, wenn Sie die Regel für sichere Anlagen erstellen (die sich auf die Priorität vorhandener Regeln auswirken kann).</span><span class="sxs-lookup"><span data-stu-id="95b54-205">In PowerShell, you can override the default priority when you create the safe attachment rule (which can affect the priority of existing rules).</span></span>

<span data-ttu-id="95b54-206">Zum Ändern der Priorität einer Richtlinie verschieben Sie die Richtlinie in der Liste nach oben oder unten (Sie können den **Priorität**-Wert im Security & Compliance Center nicht direkt ändern).</span><span class="sxs-lookup"><span data-stu-id="95b54-206">To change the priority of a policy, move the policy up or down in the list (you can't directly modify the **Priority** number in the Security & Compliance Center).</span></span>

1. <span data-ttu-id="95b54-207">Wechseln Sie im Security & Compliance Center zu **Threat Management** \> **Policy** \> **ATP Safe Attachments**.</span><span class="sxs-lookup"><span data-stu-id="95b54-207">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Attachments**.</span></span>

2. <span data-ttu-id="95b54-208">Wählen Sie auf der Seite **sichere Anlagen** eine Richtlinie aus der Liste aus, und klicken Sie darauf (aktivieren Sie das Kontrollkästchen nicht).</span><span class="sxs-lookup"><span data-stu-id="95b54-208">On the **Safe Attachments** page, select a policy from the list and click on it (don't select the check box).</span></span>

3. <span data-ttu-id="95b54-209">Klicken Sie im daraufhin angezeigten Richtliniendetails-Steuerelement auf die Schaltfläche verfügbare Priorität.</span><span class="sxs-lookup"><span data-stu-id="95b54-209">In the policy details fly out that appears, click the available priority button.</span></span>

   - <span data-ttu-id="95b54-210">Für die Richtlinie für sichere Anlagen mit dem **Prioritäts** Wert **0** ist nur die Schaltfläche **Priorität verringern** verfügbar.</span><span class="sxs-lookup"><span data-stu-id="95b54-210">The Safe Attachments policy with the **Priority** value **0** has only the **Decrease priority** button available.</span></span>

   - <span data-ttu-id="95b54-211">Die Richtlinie für sichere Anlagen mit dem niedrigsten **Prioritäts** Wert (beispielsweise **3**) verfügt nur über die Schaltfläche **Priorität verlängern** .</span><span class="sxs-lookup"><span data-stu-id="95b54-211">The Safe Attachments policy with the lowest **Priority** value (for example, **3**) has only the **Increase priority** button available.</span></span>

   - <span data-ttu-id="95b54-212">Wenn Sie drei oder mehr Richtlinien für sichere Anlagen haben, haben Richtlinien zwischen den Werten der höchsten und der niedrigsten Priorität **sowohl die Prioritätsschaltflächen "Priorität"** als auch " **Priorität verringern** " zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="95b54-212">If you have three or more Safe Attachments policies, policies between the highest and lowest priority values have both the **Increase priority** and **Decrease priority** buttons available.</span></span>

4. <span data-ttu-id="95b54-213">Klicken Sie auf Priorität Verb **Essern** oder **Priorität verringern** , um den **Prioritäts** Wert zu ändern.</span><span class="sxs-lookup"><span data-stu-id="95b54-213">Click **Increase priority** or **Decrease priority** to change the **Priority** value.</span></span>

5. <span data-ttu-id="95b54-214">Klicken Sie nach Abschluss des Vorgangs auf **Schließen**.</span><span class="sxs-lookup"><span data-stu-id="95b54-214">When you're finished, click **Close**.</span></span>

## <a name="use-the-security--compliance-center-to-remove-safe-attachments-policies"></a><span data-ttu-id="95b54-215">Verwenden des Security & Compliance Center zum Entfernen von Richtlinien für sichere Anlagen</span><span class="sxs-lookup"><span data-stu-id="95b54-215">Use the Security & Compliance Center to remove Safe Attachments policies</span></span>

1. <span data-ttu-id="95b54-216">Wechseln Sie im Security & Compliance Center zu **Threat Management** \> **Policy** \> **ATP Safe Attachments**.</span><span class="sxs-lookup"><span data-stu-id="95b54-216">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Attachments**.</span></span>

2. <span data-ttu-id="95b54-217">Wählen Sie auf der Seite **sichere Anlagen** eine Richtlinie aus der Liste aus, und klicken Sie darauf (aktivieren Sie das Kontrollkästchen nicht).</span><span class="sxs-lookup"><span data-stu-id="95b54-217">On the **Safe Attachments** page, select a policy from the list and click on it (don't select the check box).</span></span>

3. <span data-ttu-id="95b54-218">Klicken Sie im daraufhin angezeigten Richtliniendetails-Steuerelement auf **Richtlinie löschen**, und klicken Sie dann im angezeigten Warndialogfeld auf **Ja** .</span><span class="sxs-lookup"><span data-stu-id="95b54-218">In the policy details fly out that appears, click **Delete policy**, and then click **Yes** in the warning dialog that appears.</span></span>

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-attachments-policies"></a><span data-ttu-id="95b54-219">Verwenden von Exchange Online PowerShell oder eigenständigen EoP PowerShell zum Konfigurieren von Richtlinien für sichere Anlagen</span><span class="sxs-lookup"><span data-stu-id="95b54-219">Use Exchange Online PowerShell or standalone EOP PowerShell to configure Safe Attachments policies</span></span>

<span data-ttu-id="95b54-220">Wie bereits beschrieben, besteht eine Richtlinie für sichere Anlagen aus einer Richtlinie zu sicheren Anlagen und einer Regel für sichere Anlagen.</span><span class="sxs-lookup"><span data-stu-id="95b54-220">As previously described, a Safe Attachments policy consists of a safe attachment policy and a safe attachment rule.</span></span>

<span data-ttu-id="95b54-221">In PowerShell ist der Unterschied zwischen Richtlinien für sichere Anlagen und Regeln für sichere Anlagen offensichtlich.</span><span class="sxs-lookup"><span data-stu-id="95b54-221">In PowerShell, the difference between safe attachment policies and safe attachment rules is apparent.</span></span> <span data-ttu-id="95b54-222">Sie verwalten Richtlinien für sichere Anlagen mithilfe der \*\* \* -SafeAttachmentPolicy-\*\* Cmdlets und verwalten sichere Anlagenregeln mithilfe der \*\* \* -SafeAttachmentRule-\*\* Cmdlets.</span><span class="sxs-lookup"><span data-stu-id="95b54-222">You manage safe attachment policies by using the **\*-SafeAttachmentPolicy** cmdlets, and you manage safe attachment rules by using the **\*-SafeAttachmentRule** cmdlets.</span></span>

- <span data-ttu-id="95b54-223">In PowerShell erstellen Sie zuerst die Richtlinie für sichere Anlagen, dann erstellen Sie die Regel für sichere Anlagen, die die Richtlinie identifiziert, auf die die Regel angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="95b54-223">In PowerShell, you create the safe attachment policy first, then you create the safe attachment rule that identifies the policy that the rule applies to.</span></span>
- <span data-ttu-id="95b54-224">In PowerShell ändern Sie die Einstellungen in der Richtlinie zu sicheren Anlagen und der Regel für die sichere Anlage separat.</span><span class="sxs-lookup"><span data-stu-id="95b54-224">In PowerShell, you modify the settings in the safe attachment policy and the safe attachment rule separately.</span></span>
- <span data-ttu-id="95b54-225">Wenn Sie eine Richtlinie für sichere Anlagen aus PowerShell entfernen, wird die entsprechende Regel für sichere Anlagen nicht automatisch entfernt und umgekehrt.</span><span class="sxs-lookup"><span data-stu-id="95b54-225">When you remove a safe attachment policy from PowerShell, the corresponding safe attachment rule isn't automatically removed, and vice versa.</span></span>

### <a name="use-powershell-to-create-safe-attachments-policies"></a><span data-ttu-id="95b54-226">Verwenden von PowerShell zum Erstellen von Richtlinien für sichere Anlagen</span><span class="sxs-lookup"><span data-stu-id="95b54-226">Use PowerShell to create Safe Attachments policies</span></span>

<span data-ttu-id="95b54-227">Das Erstellen einer Richtlinie für sichere Anlagen in PowerShell ist ein zweistufiger Prozess:</span><span class="sxs-lookup"><span data-stu-id="95b54-227">Creating a Safe Attachments policy in PowerShell is a two-step process:</span></span>

1. <span data-ttu-id="95b54-228">Erstellen Sie die Richtlinie für sichere Anlagen.</span><span class="sxs-lookup"><span data-stu-id="95b54-228">Create the safe attachment policy.</span></span>
2. <span data-ttu-id="95b54-229">Erstellen Sie die Regel für sichere Anlagen, die die Richtlinie für sichere Anlagen angibt, auf die die Regel angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="95b54-229">Create the safe attachment rule that specifies the safe attachment policy that the rule applies to.</span></span>

 <span data-ttu-id="95b54-230">**Hinweise**:</span><span class="sxs-lookup"><span data-stu-id="95b54-230">**Notes**:</span></span>

- <span data-ttu-id="95b54-231">Sie können eine neue Regel für sichere Anlagen erstellen und ihr eine vorhandene, nicht zugeordnete Richtlinie für sichere Anlagen zuweisen.</span><span class="sxs-lookup"><span data-stu-id="95b54-231">You can create a new safe attachment rule and assign an existing, unassociated safe attachment policy to it.</span></span> <span data-ttu-id="95b54-232">Eine Regel für sichere Anlagen kann nicht mehr als einer Richtlinie für sichere Anlagen zugeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="95b54-232">A safe attachment rule can't be associated with more than one safe attachment policy.</span></span>

- <span data-ttu-id="95b54-233">Sie können die folgenden Einstellungen für neue Richtlinien für sichere Anlagen in PowerShell konfigurieren, die erst nach dem Erstellen der Richtlinie im Security & Compliance Center verfügbar sind:</span><span class="sxs-lookup"><span data-stu-id="95b54-233">You can configure the following settings on new safe attachment policies in PowerShell that aren't available in the Security & Compliance Center until after you create the policy:</span></span>
  - <span data-ttu-id="95b54-234">Erstellen Sie die neue Richtlinie als deaktiviert (_aktiviert_ im `$false` Cmdlet **New-SafeAttachmentRule** ).</span><span class="sxs-lookup"><span data-stu-id="95b54-234">Create the new policy as disabled (_Enabled_ `$false` on the **New-SafeAttachmentRule** cmdlet).</span></span>
  - <span data-ttu-id="95b54-235">Legen Sie die Priorität der Richtlinie während der Erstellung (_Priorität_ _\<Number\>_ ) für das Cmdlet **New-SafeAttachmentRule** fest).</span><span class="sxs-lookup"><span data-stu-id="95b54-235">Set the priority of the policy during creation (_Priority_ _\<Number\>_) on the **New-SafeAttachmentRule** cmdlet).</span></span>

- <span data-ttu-id="95b54-236">Eine neue Richtlinie für sichere Anlagen, die Sie in PowerShell erstellen, ist erst im Security & Compliance Center sichtbar, wenn Sie die Richtlinie einer sicheren Anlage Regel zuweisen.</span><span class="sxs-lookup"><span data-stu-id="95b54-236">A new safe attachment policy that you create in PowerShell isn't visible in the Security & Compliance Center until you assign the policy to a safe attachment rule.</span></span>

#### <a name="step-1-use-powershell-to-create-a-safe-attachment-policy"></a><span data-ttu-id="95b54-237">Schritt 1: Erstellen einer Richtlinie für sichere Anlagen mithilfe von PowerShell</span><span class="sxs-lookup"><span data-stu-id="95b54-237">Step 1: Use PowerShell to create a safe attachment policy</span></span>

<span data-ttu-id="95b54-238">Verwenden Sie die folgende Syntax, um eine Richtlinie für sichere Anlagen zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="95b54-238">To create a safe attachment policy, use this syntax:</span></span>

```PowerShell
New-SafeAttachmentPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] [-Action <Allow | Block | Replace | DynamicDelivery>] [-Redirect <$true | $false>] [-RedirectAddress <SMTPEmailAddress>] [-ActionOnError <$true | $false>]
```

<span data-ttu-id="95b54-239">In diesem Beispiel wird eine Richtlinie für sichere Anlagennamens "Contoso all" mit den folgenden Werten erstellt:</span><span class="sxs-lookup"><span data-stu-id="95b54-239">This example creates a safe attachment policy named Contoso All with the following values:</span></span>

- <span data-ttu-id="95b54-240">Blockieren von Nachrichten, die festgestellt werden, dass Malware durch Scannen sicherer Dokumente enthalten ist (der Parameter _Action_ wird nicht verwendet, und der Standardwert ist `Block` ).</span><span class="sxs-lookup"><span data-stu-id="95b54-240">Block messages that are found to contain malware by Safe Documents scanning (we aren't using the _Action_ parameter, and the default value is `Block`).</span></span>
- <span data-ttu-id="95b54-241">Die Umleitung ist aktiviert, und Nachrichten, die Schadsoftware enthalten, werden zur Analyse und Untersuchung an sec-OPS@contoso.com gesendet.</span><span class="sxs-lookup"><span data-stu-id="95b54-241">Redirection is enabled, and messages that are found to contain malware are sent to sec-ops@contoso.com for analysis and investigation.</span></span>
- <span data-ttu-id="95b54-242">Wenn das Scannen sicherer Anlagen nicht verfügbar ist oder Fehler auftritt, übermittelt die Nachricht nicht (wir verwenden den Parameter _ActionOnError_ nicht, und der Standardwert ist `$true` ).</span><span class="sxs-lookup"><span data-stu-id="95b54-242">If Safe Attachments scanning isn't available or encounters errors, don't deliver the message (we aren't using the _ActionOnError_ parameter, and the default value is `$true`).</span></span>

```PowerShell
New-SafeAttachmentPolicy -Name "Contoso All" -Redirect $true -RedirectAddress sec-ops@contoso.com
```

<span data-ttu-id="95b54-243">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [New-SafeAttachmentPolicy](https://docs.microsoft.com/powershell/module/exchange/new-safeattachmentpolicy).</span><span class="sxs-lookup"><span data-stu-id="95b54-243">For detailed syntax and parameter information, see [New-SafeAttachmentPolicy](https://docs.microsoft.com/powershell/module/exchange/new-safeattachmentpolicy).</span></span>

#### <a name="step-2-use-powershell-to-create-a-safe-attachment-rule"></a><span data-ttu-id="95b54-244">Schritt 2: Verwenden von PowerShell zum Erstellen einer Regel für sichere Anlagen</span><span class="sxs-lookup"><span data-stu-id="95b54-244">Step 2: Use PowerShell to create a safe attachment rule</span></span>

<span data-ttu-id="95b54-245">Verwenden Sie die folgende Syntax, um eine sichere Anlagenregel zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="95b54-245">To create a safe attachment rule, use this syntax:</span></span>

```PowerShell
New-SafeAttachmentRule -Name "<RuleName>" -SafeAttachmentPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"] [-Enabled <$true | $false>]
```

<span data-ttu-id="95b54-246">In diesem Beispiel wird eine sichere Anlagenregel namens "Contoso all" mit den folgenden Bedingungen erstellt:</span><span class="sxs-lookup"><span data-stu-id="95b54-246">This example creates a safe attachment rule named Contoso All with the following conditions:</span></span>

- <span data-ttu-id="95b54-247">Die Regel ist mit der Richtlinie für sichere Anlagennamens "Contoso all" verknüpft.</span><span class="sxs-lookup"><span data-stu-id="95b54-247">The rule is associated with the safe attachment policy named Contoso All.</span></span>
- <span data-ttu-id="95b54-248">Die Regel gilt für alle Empfänger in der contoso.com-Domäne.</span><span class="sxs-lookup"><span data-stu-id="95b54-248">The rule applies to all recipients in the contoso.com domain.</span></span>
- <span data-ttu-id="95b54-249">Da wir den _Priority_ -Parameter nicht verwenden, wird die Standardpriorität verwendet.</span><span class="sxs-lookup"><span data-stu-id="95b54-249">Because we aren't using the _Priority_ parameter, the default priority is used.</span></span>
- <span data-ttu-id="95b54-250">Die Regel ist aktiviert (der Parameter _Enabled_ wird nicht verwendet, und der Standardwert ist `$true` ).</span><span class="sxs-lookup"><span data-stu-id="95b54-250">The rule is enabled (we aren't using the _Enabled_ parameter, and the default value is `$true`).</span></span>

```powershell
New-SafeAttachmentRule -Name "Contoso All" -SafeAttachmentPolicy "Contoso All" -RecipientDomainIs contoso.com
```

<span data-ttu-id="95b54-251">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [New-SafeAttachmentRule](https://docs.microsoft.com/powershell/module/exchange/new-safeattachmentrule).</span><span class="sxs-lookup"><span data-stu-id="95b54-251">For detailed syntax and parameter information, see [New-SafeAttachmentRule](https://docs.microsoft.com/powershell/module/exchange/new-safeattachmentrule).</span></span>

### <a name="use-powershell-to-view-safe-attachment-policies"></a><span data-ttu-id="95b54-252">Verwenden von PowerShell zum Anzeigen von Richtlinien für sichere Anlagen</span><span class="sxs-lookup"><span data-stu-id="95b54-252">Use PowerShell to view safe attachment policies</span></span>

<span data-ttu-id="95b54-253">Verwenden Sie die folgende Syntax, um vorhandene Richtlinien für sichere Anlagen anzuzeigen:</span><span class="sxs-lookup"><span data-stu-id="95b54-253">To view existing safe attachment policies, use the following syntax:</span></span>

```PowerShell
Get-SafeAttachmentPolicy [-Identity "<PolicyIdentity>"] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="95b54-254">In diesem Beispiel wird eine Zusammenfassungsliste aller Richtlinien für sichere Anlagen zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="95b54-254">This example returns a summary list of all safe attachment policies.</span></span>

```PowerShell
Get-SafeAttachmentPolicy
```

<span data-ttu-id="95b54-255">In diesem Beispiel werden detaillierte Informationen für die Richtlinie für sichere Anlagennamens "Contoso Executives" zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="95b54-255">This example returns detailed information for the safe attachment policy named Contoso Executives.</span></span>

```PowerShell
Get-SafeAttachmentPolicy -Identity "Contoso Executives" | Format-List
```

<span data-ttu-id="95b54-256">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Get-SafeAttachmentPolicy](https://docs.microsoft.com/powershell/module/exchange/get-safeattachmentpolicy).</span><span class="sxs-lookup"><span data-stu-id="95b54-256">For detailed syntax and parameter information, see [Get-SafeAttachmentPolicy](https://docs.microsoft.com/powershell/module/exchange/get-safeattachmentpolicy).</span></span>

### <a name="use-powershell-to-view-safe-attachment-rules"></a><span data-ttu-id="95b54-257">Verwenden von PowerShell zum Anzeigen von Regeln für sichere Anlagen</span><span class="sxs-lookup"><span data-stu-id="95b54-257">Use PowerShell to view safe attachment rules</span></span>

<span data-ttu-id="95b54-258">Verwenden Sie die folgende Syntax, um vorhandene Regeln für sichere Anlagen anzuzeigen:</span><span class="sxs-lookup"><span data-stu-id="95b54-258">To view existing safe attachment rules, use the following syntax:</span></span>

```PowerShell
Get-SafeAttachmentRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled>] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="95b54-259">In diesem Beispiel wird eine Zusammenfassungsliste aller Regeln für sichere Anlagen zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="95b54-259">This example returns a summary list of all safe attachment rules.</span></span>

```PowerShell
Get-SafeAttachmentRule
```

<span data-ttu-id="95b54-260">Führen Sie die folgenden Befehle aus, um die Liste nach aktivierten oder deaktivierten Regeln zu filtern:</span><span class="sxs-lookup"><span data-stu-id="95b54-260">To filter the list by enabled or disabled rules, run the following commands:</span></span>

```PowerShell
Get-SafeAttachmentRule -State Disabled
```

```PowerShell
Get-SafeAttachmentRule -State Enabled
```

<span data-ttu-id="95b54-261">In diesem Beispiel werden detaillierte Informationen für die Regel für sichere Anlagennamens "Contoso Executives" zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="95b54-261">This example returns detailed information for the safe attachment rule named Contoso Executives.</span></span>

```PowerShell
Get-SafeAttachmentRule -Identity "Contoso Executives" | Format-List
```

<span data-ttu-id="95b54-262">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Get-SafeAttachmentRule](https://docs.microsoft.com/powershell/module/exchange/get-safeattachmentrule).</span><span class="sxs-lookup"><span data-stu-id="95b54-262">For detailed syntax and parameter information, see [Get-SafeAttachmentRule](https://docs.microsoft.com/powershell/module/exchange/get-safeattachmentrule).</span></span>

### <a name="use-powershell-to-modify-safe-attachment-policies"></a><span data-ttu-id="95b54-263">Verwenden von PowerShell zum Ändern von Richtlinien für sichere Anlagen</span><span class="sxs-lookup"><span data-stu-id="95b54-263">Use PowerShell to modify safe attachment policies</span></span>

<span data-ttu-id="95b54-264">Sie können keine Richtlinie für sichere Anlagen in PowerShell umbenennen (das Cmdlet " **setSafeAttachmentPolicy** " verfügt über keinen Parameter " _Name_ ").</span><span class="sxs-lookup"><span data-stu-id="95b54-264">You can't rename a safe attachment policy in PowerShell (the **Set-SafeAttachmentPolicy** cmdlet has no _Name_ parameter).</span></span> <span data-ttu-id="95b54-265">Wenn Sie eine Richtlinie für sichere Anlagen im Security & Compliance Center umbenennen, benennen Sie die _Regel_für sichere Anlagen nur um.</span><span class="sxs-lookup"><span data-stu-id="95b54-265">When you rename a Safe Attachments policy in the Security & Compliance Center, you're only renaming the safe attachment _rule_.</span></span>

<span data-ttu-id="95b54-266">Andernfalls stehen dieselben Einstellungen zur Verfügung, wenn Sie eine Richtlinie zu sicheren Anlagen erstellen, wie im Abschnitt [Schritt 1: Verwenden von PowerShell zum Erstellen einer Richtlinie zu sicheren Anlagen](#step-1-use-powershell-to-create-a-safe-attachment-policy) weiter oben in diesem Artikel beschrieben.</span><span class="sxs-lookup"><span data-stu-id="95b54-266">Otherwise, the same settings are available when you create a safe attachment policy as described in the [Step 1: Use PowerShell to create a safe attachment policy](#step-1-use-powershell-to-create-a-safe-attachment-policy) section earlier in this article.</span></span>

<span data-ttu-id="95b54-267">Verwenden Sie die folgende Syntax, um eine Richtlinie für sichere Anlagen zu ändern:</span><span class="sxs-lookup"><span data-stu-id="95b54-267">To modify a safe attachment policy, use this syntax:</span></span>

```PowerShell
Set-SafeAttachmentPolicy -Identity "<PolicyName>" <Settings>
```

<span data-ttu-id="95b54-268">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Sets-SafeAttachmentPolicy](https://docs.microsoft.com/powershell/module/exchange/set-safeattachmentpolicy).</span><span class="sxs-lookup"><span data-stu-id="95b54-268">For detailed syntax and parameter information, see [Set-SafeAttachmentPolicy](https://docs.microsoft.com/powershell/module/exchange/set-safeattachmentpolicy).</span></span>

### <a name="use-powershell-to-modify-safe-attachment-rules"></a><span data-ttu-id="95b54-269">Verwenden von PowerShell zum Ändern von Regeln für sichere Anlagen</span><span class="sxs-lookup"><span data-stu-id="95b54-269">Use PowerShell to modify safe attachment rules</span></span>

<span data-ttu-id="95b54-270">Die einzige Einstellung, die nicht verfügbar ist, wenn Sie eine sichere Anlagenregel in PowerShell ändern, ist der Parameter _Enabled_ , mit dem Sie eine deaktivierte Regel erstellen können.</span><span class="sxs-lookup"><span data-stu-id="95b54-270">The only setting that's not available when you modify a safe attachment rule in PowerShell is the _Enabled_ parameter that allows you to create a disabled rule.</span></span> <span data-ttu-id="95b54-271">Informationen zum Aktivieren oder Deaktivieren vorhandener Regeln für sichere Anlagen finden Sie im nächsten Abschnitt.</span><span class="sxs-lookup"><span data-stu-id="95b54-271">To enable or disable existing safe attachment rules, see the next section.</span></span>

<span data-ttu-id="95b54-272">Andernfalls stehen dieselben Einstellungen zur Verfügung, wenn Sie eine Regel erstellen, wie im Abschnitt [Schritt 2: Verwenden von PowerShell zum Erstellen einer Richtlinie zu sicheren Anlagen](#step-2-use-powershell-to-create-a-safe-attachment-rule) weiter oben in diesem Artikel beschrieben.</span><span class="sxs-lookup"><span data-stu-id="95b54-272">Otherwise, the same settings are available when you create a rule as described in the [Step 2: Use PowerShell to create a safe attachment rule](#step-2-use-powershell-to-create-a-safe-attachment-rule) section earlier in this article.</span></span>

<span data-ttu-id="95b54-273">Verwenden Sie die folgende Syntax, um eine sichere Anlagenregel zu ändern:</span><span class="sxs-lookup"><span data-stu-id="95b54-273">To modify a safe attachment rule, use this syntax:</span></span>

```PowerShell
Set-SafeAttachmentRule -Identity "<RuleName>" <Settings>
```

<span data-ttu-id="95b54-274">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Sets-SafeAttachmentRule](https://docs.microsoft.com/powershell/module/exchange/set-safeattachmentrule).</span><span class="sxs-lookup"><span data-stu-id="95b54-274">For detailed syntax and parameter information, see [Set-SafeAttachmentRule](https://docs.microsoft.com/powershell/module/exchange/set-safeattachmentrule).</span></span>

### <a name="use-powershell-to-enable-or-disable-safe-attachment-rules"></a><span data-ttu-id="95b54-275">Verwenden von PowerShell zum Aktivieren oder Deaktivieren von Regeln für sichere Anlagen</span><span class="sxs-lookup"><span data-stu-id="95b54-275">Use PowerShell to enable or disable safe attachment rules</span></span>

<span data-ttu-id="95b54-276">Das Aktivieren oder Deaktivieren einer Regel für sichere Anlagen in PowerShell aktiviert oder deaktiviert die gesamte Richtlinie für sichere Anlagen (die sichere Anlage Regel und die zugewiesene Richtlinie für sichere Anlagen).</span><span class="sxs-lookup"><span data-stu-id="95b54-276">Enabling or disabling a safe attachment rule in PowerShell enables or disables the whole Safe Attachments policy (the safe attachment rule and the assigned safe attachment policy).</span></span>

<span data-ttu-id="95b54-277">Verwenden Sie die folgende Syntax, um eine sichere Anlagenregel in PowerShell zu aktivieren oder zu deaktivieren:</span><span class="sxs-lookup"><span data-stu-id="95b54-277">To enable or disable a safe attachment rule in PowerShell, use this syntax:</span></span>

```PowerShell
<Enable-SafeAttachmentRule | Disable-SafeAttachmentRule> -Identity "<RuleName>"
```

<span data-ttu-id="95b54-278">In diesem Beispiel wird die Richtlinie für sichere Anlagennamens "Marketing Department" deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="95b54-278">This example disables the safe attachment rule named Marketing Department.</span></span>

```PowerShell
Disable-SafeAttachmentRule -Identity "Marketing Department"
```

<span data-ttu-id="95b54-279">In diesem Beispiel wird dieselbe Regel aktiviert.</span><span class="sxs-lookup"><span data-stu-id="95b54-279">This example enables same rule.</span></span>

```PowerShell
Enable-SafeAttachmentRule -Identity "Marketing Department"
```

<span data-ttu-id="95b54-280">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [enable-SafeAttachmentRule](https://docs.microsoft.com/powershell/module/exchange/enable-safeattachmentrule) und [Disable-SafeAttachmentRule](https://docs.microsoft.com/powershell/module/exchange/disable-safeattachmentrule).</span><span class="sxs-lookup"><span data-stu-id="95b54-280">For detailed syntax and parameter information, see [Enable-SafeAttachmentRule](https://docs.microsoft.com/powershell/module/exchange/enable-safeattachmentrule) and [Disable-SafeAttachmentRule](https://docs.microsoft.com/powershell/module/exchange/disable-safeattachmentrule).</span></span>

### <a name="use-powershell-to-set-the-priority-of-safe-attachment-rules"></a><span data-ttu-id="95b54-281">Verwenden von PowerShell zum Festlegen der Priorität von Regeln für sichere Anlagen</span><span class="sxs-lookup"><span data-stu-id="95b54-281">Use PowerShell to set the priority of safe attachment rules</span></span>

<span data-ttu-id="95b54-282">Der höchste Prioritätswert, den Sie für eine Regel festlegen können, ist 0.</span><span class="sxs-lookup"><span data-stu-id="95b54-282">The highest priority value you can set on a rule is 0.</span></span> <span data-ttu-id="95b54-283">Der niedrigste Wert, den Sie festlegen können, hängt von der Anzahl von Regeln ab.</span><span class="sxs-lookup"><span data-stu-id="95b54-283">The lowest value you can set depends on the number of rules.</span></span> <span data-ttu-id="95b54-284">Wenn Sie z. B. fünf Regeln haben, können Sie die Prioritätswerte 0 bis 4 verwenden.</span><span class="sxs-lookup"><span data-stu-id="95b54-284">For example, if you have five rules, you can use the priority values 0 through 4.</span></span> <span data-ttu-id="95b54-285">Das Ändern der Priorität einer vorhandenen Regel kann sich entsprechend auf andere Regeln auswirken.</span><span class="sxs-lookup"><span data-stu-id="95b54-285">Changing the priority of an existing rule can have a cascading effect on other rules.</span></span> <span data-ttu-id="95b54-286">Wenn Sie z. B. fünf benutzerdefinierte Regeln haben (Priorität 0 bis 4) und die Priorität einer Regel in 2 ändern, erhält die vorhandene Regel mit Priorität 2 die Priorität 3, und die Regel mit Priorität 3 erhält Priorität 4.</span><span class="sxs-lookup"><span data-stu-id="95b54-286">For example, if you have five custom rules (priorities 0 through 4), and you change the priority of a rule to 2, the existing rule with priority 2 is changed to priority 3, and the rule with priority 3 is changed to priority 4.</span></span>

<span data-ttu-id="95b54-287">Verwenden Sie die folgende Syntax, um die Priorität einer Regel für sichere Anlagen in PowerShell festzulegen:</span><span class="sxs-lookup"><span data-stu-id="95b54-287">To set the priority of a safe attachment rule in PowerShell, use the following syntax:</span></span>

```PowerShell
Set-SafeAttachmentRule -Identity "<RuleName>" -Priority <Number>
```

<span data-ttu-id="95b54-p123">In diesem Beispiel wird die Priorität der Regel namens „Marketing Department“ auf 2 festgelegt. Alle vorhandenen Regeln mit Priorität kleiner oder gleich 2 werden um 1 verringert (die Prioritätswerte werden um 1 erhöht).</span><span class="sxs-lookup"><span data-stu-id="95b54-p123">This example sets the priority of the rule named Marketing Department to 2. All existing rules that have a priority less than or equal to 2 are decreased by 1 (their priority numbers are increased by 1).</span></span>

```PowerShell
Set-SafeAttachmentRule -Identity "Marketing Department" -Priority 2
```

<span data-ttu-id="95b54-290">**Hinweis**: Wenn Sie die Priorität einer neuen Regel beim Erstellen festlegen möchten, verwenden Sie stattdessen den Parameter _Priority_ für das Cmdlet **New-SafeAttachmentRule** .</span><span class="sxs-lookup"><span data-stu-id="95b54-290">**Note**: To set the priority of a new rule when you create it, use the _Priority_ parameter on the **New-SafeAttachmentRule** cmdlet instead.</span></span>

<span data-ttu-id="95b54-291">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Sets-SafeAttachmentRule](https://docs.microsoft.com/powershell/module/exchange/set-safeattachmentrule).</span><span class="sxs-lookup"><span data-stu-id="95b54-291">For detailed syntax and parameter information, see [Set-SafeAttachmentRule](https://docs.microsoft.com/powershell/module/exchange/set-safeattachmentrule).</span></span>

### <a name="use-powershell-to-remove-safe-attachment-policies"></a><span data-ttu-id="95b54-292">Verwenden von PowerShell zum Entfernen von Richtlinien für sichere Anlagen</span><span class="sxs-lookup"><span data-stu-id="95b54-292">Use PowerShell to remove safe attachment policies</span></span>

<span data-ttu-id="95b54-293">Wenn Sie mithilfe von PowerShell eine Richtlinie für sichere Anlagen entfernen, wird die entsprechende Regel für sichere Anlagen nicht entfernt.</span><span class="sxs-lookup"><span data-stu-id="95b54-293">When you use PowerShell to remove a safe attachment policy, the corresponding safe attachment rule isn't removed.</span></span>

<span data-ttu-id="95b54-294">Verwenden Sie die folgende Syntax, um eine Richtlinie für sichere Anlagen in PowerShell zu entfernen:</span><span class="sxs-lookup"><span data-stu-id="95b54-294">To remove a safe attachment policy in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-SafeAttachmentPolicy -Identity "<PolicyName>"
```

<span data-ttu-id="95b54-295">In diesem Beispiel wird die Richtlinie für sichere Anlagennamens "Marketing Department" entfernt.</span><span class="sxs-lookup"><span data-stu-id="95b54-295">This example removes the safe attachment policy named Marketing Department.</span></span>

```PowerShell
Remove-SafeAttachmentPolicy -Identity "Marketing Department"
```

<span data-ttu-id="95b54-296">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Remove-SafeAttachmentPolicy](https://docs.microsoft.com/powershell/module/exchange/remove-safeattachmentpolicy).</span><span class="sxs-lookup"><span data-stu-id="95b54-296">For detailed syntax and parameter information, see [Remove-SafeAttachmentPolicy](https://docs.microsoft.com/powershell/module/exchange/remove-safeattachmentpolicy).</span></span>

### <a name="use-powershell-to-remove-safe-attachment-rules"></a><span data-ttu-id="95b54-297">Verwenden von PowerShell zum Entfernen von Regeln für sichere Anlagen</span><span class="sxs-lookup"><span data-stu-id="95b54-297">Use PowerShell to remove safe attachment rules</span></span>

<span data-ttu-id="95b54-298">Wenn Sie mithilfe von PowerShell eine Regel für sichere Anlagen entfernen, wird die entsprechende Richtlinie für sichere Anlagen nicht entfernt.</span><span class="sxs-lookup"><span data-stu-id="95b54-298">When you use PowerShell to remove a safe attachment rule, the corresponding safe attachment policy isn't removed.</span></span>

<span data-ttu-id="95b54-299">Verwenden Sie die folgende Syntax, um eine sichere Anlagenregel in PowerShell zu entfernen:</span><span class="sxs-lookup"><span data-stu-id="95b54-299">To remove a safe attachment rule in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-SafeAttachmentRule -Identity "<PolicyName>"
```

<span data-ttu-id="95b54-300">In diesem Beispiel wird die Regel für sichere Anlagennamens "Marketing Department" entfernt.</span><span class="sxs-lookup"><span data-stu-id="95b54-300">This example removes the safe attachment rule named Marketing Department.</span></span>

```PowerShell
Remove-SafeAttachmentRule -Identity "Marketing Department"
```

<span data-ttu-id="95b54-301">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Remove-SafeAttachmentRule](https://docs.microsoft.com/powershell/module/exchange/remove-safeattachmentrule).</span><span class="sxs-lookup"><span data-stu-id="95b54-301">For detailed syntax and parameter information, see [Remove-SafeAttachmentRule](https://docs.microsoft.com/powershell/module/exchange/remove-safeattachmentrule).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="95b54-302">Wie können Sie feststellen, dass diese Verfahren erfolgreich waren?</span><span class="sxs-lookup"><span data-stu-id="95b54-302">How do you know these procedures worked?</span></span>

<span data-ttu-id="95b54-303">Führen Sie einen der folgenden Schritte aus, um zu überprüfen, ob Sie Richtlinien für sichere Anlagen erfolgreich erstellt, geändert oder entfernt haben:</span><span class="sxs-lookup"><span data-stu-id="95b54-303">To verify that you've successfully created, modified, or removed Safe Attachments policies, do any of the following steps:</span></span>

- <span data-ttu-id="95b54-304">Wechseln Sie im Security & Compliance Center zu **Threat Management** \> **Policy** \> **ATP Safe Attachments**.</span><span class="sxs-lookup"><span data-stu-id="95b54-304">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Attachments**.</span></span> <span data-ttu-id="95b54-305">Überprüfen Sie die Liste der Richtlinien, deren **Status** Werte und deren **Prioritäts** Werte.</span><span class="sxs-lookup"><span data-stu-id="95b54-305">Verify the list of policies, their **Status** values, and their **Priority** values.</span></span> <span data-ttu-id="95b54-306">Um weitere Details anzuzeigen, wählen Sie die Richtlinie aus der Liste aus, und zeigen Sie die Details im verfliegt an.</span><span class="sxs-lookup"><span data-stu-id="95b54-306">To view more details, select the policy from the list, and view the details in the fly out.</span></span>

- <span data-ttu-id="95b54-307">Ersetzen Sie in Exchange Online PowerShell oder Exchange Online Protection PowerShell \<Name\> durch den Namen der Richtlinie oder Regel, führen Sie den folgenden Befehl aus, und überprüfen Sie die Einstellungen:</span><span class="sxs-lookup"><span data-stu-id="95b54-307">In Exchange Online PowerShell or Exchange Online Protection PowerShell, replace \<Name\> with the name of the policy or rule, run the following command, and verify the settings:</span></span>

  ```PowerShell
  Get-SafeAttachmentPolicy -Identity "<Name>" | Format-List
  ```

  ```PowerShell
  Get-SafeAttachmentRule -Identity "<Name>" | Format-List
  ```

<span data-ttu-id="95b54-308">Überprüfen Sie die verfügbaren Advanced Threat Protection-Berichte, um zu überprüfen, ob Nachrichten von sicheren Anlagen überprüft werden.</span><span class="sxs-lookup"><span data-stu-id="95b54-308">To verify that Safe Attachments is scanning messages, check the available Advanced Threat Protection reports.</span></span> <span data-ttu-id="95b54-309">Weitere Informationen finden Sie unter [Anzeigen von Berichten für Office 365 ATP](view-reports-for-atp.md) und [Verwenden von Explorer im Security & Compliance Center](threat-explorer.md).</span><span class="sxs-lookup"><span data-stu-id="95b54-309">For more information, see [View reports for Office 365 ATP](view-reports-for-atp.md) and [Use Explorer in the Security & Compliance Center](threat-explorer.md).</span></span>
