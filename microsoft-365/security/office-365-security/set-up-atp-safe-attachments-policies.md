---
title: Einrichten von Richtlinien für sichere Anlagen in Microsoft Defender für Office 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 078eb946-819a-4e13-8673-fe0c0ad3a775
ms.collection:
- M365-security-compliance
description: Erfahren Sie, wie Sie Richtlinien für sichere Anlagen definieren, um Ihre Organisation vor schädlichen Dateien in E-Mails zu schützen.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 9343ce222f1deb84e900f0d6f18e7d55daa73372
ms.sourcegitcommit: 4f40f5be140a23bacff6fd7b85536de14fc7d499
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/03/2021
ms.locfileid: "50084613"
---
# <a name="set-up-safe-attachments-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="9361d-103">Einrichten von Richtlinien für sichere Anlagen in Microsoft Defender für Office 365</span><span class="sxs-lookup"><span data-stu-id="9361d-103">Set up Safe Attachments policies in Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

> [!IMPORTANT]
> <span data-ttu-id="9361d-104">Dieser Artikel richtet sich an Geschäftskunden, die über [Microsoft Defender für Office 365](office-365-atp.md) verfügen.</span><span class="sxs-lookup"><span data-stu-id="9361d-104">This article is intended for business customers who have [Microsoft Defender for Office 365](office-365-atp.md).</span></span> <span data-ttu-id="9361d-105">Informationen zur Anlagenprüfung in Outlook finden Sie unter Advanced [Outlook.com Security](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).</span><span class="sxs-lookup"><span data-stu-id="9361d-105">If you're a home user looking for information about attachment scanning in Outlook, see [Advanced Outlook.com security](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).</span></span>

<span data-ttu-id="9361d-106">Sichere Anlagen ist ein Feature in [Microsoft Defender für Office 365,](office-365-atp.md) das eine virtuelle Umgebung verwendet, um Anlagen in eingehenden [E-Mail-Nachrichten](anti-malware-protection.md)zu überprüfen, nachdem sie vom Schutz vor Schadsoftware in Exchange Online Protection (EOP) überprüft wurden, jedoch vor der Zustellung an Empfänger.</span><span class="sxs-lookup"><span data-stu-id="9361d-106">Safe Attachments is a feature in [Microsoft Defender for Office 365](office-365-atp.md) that uses a virtual environment to check attachments in inbound email messages after they've been scanned by [anti-malware protection in Exchange Online Protection (EOP)](anti-malware-protection.md), but before delivery to recipients.</span></span> <span data-ttu-id="9361d-107">Weitere Informationen finden Sie unter ["Sichere Anlagen" in Microsoft Defender für Office 365.](atp-safe-attachments.md)</span><span class="sxs-lookup"><span data-stu-id="9361d-107">For more information, see [Safe Attachments in Microsoft Defender for Office 365](atp-safe-attachments.md).</span></span>

<span data-ttu-id="9361d-108">Es gibt keine integrierte oder standardmäßige Richtlinie für sichere Anlagen.</span><span class="sxs-lookup"><span data-stu-id="9361d-108">There's no built-in or default Safe Attachments policy.</span></span> <span data-ttu-id="9361d-109">Um die Überprüfung sicherer Anlagen von E-Mail-Nachrichtenanlagen zu erhalten, müssen Sie eine oder mehrere Richtlinien für sichere Anlagen erstellen, wie in diesem Artikel beschrieben.</span><span class="sxs-lookup"><span data-stu-id="9361d-109">To get Safe Attachments scanning of email message attachments, you need to create one or more Safe Attachments policies as described in this article.</span></span>

<span data-ttu-id="9361d-110">Sie können Richtlinien für sichere Anlagen im Security & Compliance Center oder in PowerShell konfigurieren (Exchange Online PowerShell für berechtigte Microsoft 365-Organisationen mit Postfächern in Exchange Online; eigenständige EOP PowerShell für Organisationen ohne Exchange Online-Postfächer, aber mit Defender für Office 365-Add-On-Abonnements).</span><span class="sxs-lookup"><span data-stu-id="9361d-110">You can configure Safe Attachments policies in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for eligible Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes, but with Defender for Office 365 add-on subscriptions).</span></span>

<span data-ttu-id="9361d-111">Die grundlegenden Elemente einer Richtlinie für sichere Anlagen sind:</span><span class="sxs-lookup"><span data-stu-id="9361d-111">The basic elements of a Safe Attachments policy are:</span></span>

- <span data-ttu-id="9361d-112">**Die** Richtlinie für sichere Anlagen: Gibt die Aktionen für unbekannte Schadsoftwareerkennungen an, gibt an, ob Nachrichten mit Anlagen mit Schadsoftware an eine angegebene E-Mail-Adresse gesendet werden sollen und ob Nachrichten zu senden sind, wenn die Überprüfung auf sichere Anlagen nicht abgeschlossen werden kann.</span><span class="sxs-lookup"><span data-stu-id="9361d-112">**The safe attachment policy**: Specifies the actions for unknown malware detections, whether to send messages with malware attachments to a specified email address, and whether to deliver messages if Safe Attachments scanning can't complete.</span></span>
- <span data-ttu-id="9361d-113">**Die Regel für sichere Anlagen:** Gibt die Prioritäts- und Empfängerfilter an (für wen die Richtlinie gilt).</span><span class="sxs-lookup"><span data-stu-id="9361d-113">**The safe attachment rule**: Specifies the priority and recipient filters (who the policy applies to).</span></span>

<span data-ttu-id="9361d-114">Der Unterschied zwischen diesen beiden Elementen ist nicht offensichtlich, wenn Sie Richtlinien für sichere Anlagen im Security & Compliance Center verwalten:</span><span class="sxs-lookup"><span data-stu-id="9361d-114">The difference between these two elements isn't obvious when you manage Safe Attachments polices in the Security & Compliance Center:</span></span>

- <span data-ttu-id="9361d-115">Wenn Sie eine Richtlinie für sichere Anlagen erstellen, erstellen Sie tatsächlich eine sichere Anlagenregel und die zugeordnete Richtlinie für sichere Anlagen gleichzeitig mit demselben Namen für beide.</span><span class="sxs-lookup"><span data-stu-id="9361d-115">When you create a Safe Attachments policy, you're actually creating a safe attachment rule and the associated safe attachment policy at the same time using the same name for both.</span></span>
- <span data-ttu-id="9361d-116">Wenn Sie eine Richtlinie für sichere Anlagen ändern, ändern Einstellungen im Zusammenhang mit Name, Priorität, aktiviert oder deaktiviert und Empfängerfilter die Regel für sichere Anlagen.</span><span class="sxs-lookup"><span data-stu-id="9361d-116">When you modify a Safe Attachments policy, settings related to the name, priority, enabled or disabled, and recipient filters modify the safe attachment rule.</span></span> <span data-ttu-id="9361d-117">Alle anderen Einstellungen ändern die zugeordnete Richtlinie für sichere Anlagen.</span><span class="sxs-lookup"><span data-stu-id="9361d-117">All other settings modify the associated safe attachment policy.</span></span>
- <span data-ttu-id="9361d-118">Wenn Sie eine Richtlinie für sichere Anlagen entfernen, werden die Regel für sichere Anlagen und die zugehörige Richtlinie für sichere Anlagen entfernt.</span><span class="sxs-lookup"><span data-stu-id="9361d-118">When you remove a Safe Attachments policy, the safe attachment rule and the associated safe attachment policy are removed.</span></span>

<span data-ttu-id="9361d-119">In Exchange Online PowerShell oder der eigenständigen EOP PowerShell verwalten Sie die Richtlinie und die Regel getrennt.</span><span class="sxs-lookup"><span data-stu-id="9361d-119">In Exchange Online PowerShell or standalone EOP PowerShell, you manage the policy and the rule separately.</span></span> <span data-ttu-id="9361d-120">Weitere Informationen finden Sie im Abschnitt "Verwenden von Exchange Online PowerShell oder der eigenständigen [EOP PowerShell](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-attachments-policies) zum Konfigurieren von Richtlinien für sichere Anlagen" weiter unten in diesem Artikel.</span><span class="sxs-lookup"><span data-stu-id="9361d-120">For more information, see the [Use Exchange Online PowerShell or standalone EOP PowerShell to configure Safe Attachments policies](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-attachments-policies) section later in this article.</span></span>

> [!NOTE]
> <span data-ttu-id="9361d-121">Im globalen Einstellungsbereich der Einstellungen für sichere Anlagen konfigurieren Sie Features, die nicht von Richtlinien für sichere Anlagen abhängig sind.</span><span class="sxs-lookup"><span data-stu-id="9361d-121">In the global settings area of Safe Attachments settings, you configure features that are not dependent on Safe Attachments policies.</span></span> <span data-ttu-id="9361d-122">Anweisungen finden [Sie unter "Aktivieren sicherer Anlagen für SharePoint, OneDrive und Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md) und sichere Dokumente in Microsoft [365 E5".](safe-docs.md)</span><span class="sxs-lookup"><span data-stu-id="9361d-122">For instructions see [Turn on Safe Attachments for SharePoint, OneDrive, and Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md) and [Safe Documents in Microsoft 365 E5](safe-docs.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="9361d-123">Was sollten Sie wissen, bevor Sie beginnen?</span><span class="sxs-lookup"><span data-stu-id="9361d-123">What do you need to know before you begin?</span></span>

- <span data-ttu-id="9361d-124">Sie öffnen das Security & Compliance Center unter <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="9361d-124">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="9361d-125">Um direkt zur Seite **"Sichere Anlagen" zu** wechseln, verwenden Sie <https://protection.office.com/safeattachmentv2> .</span><span class="sxs-lookup"><span data-stu-id="9361d-125">To go directly to the **Safe Attachments** page, use <https://protection.office.com/safeattachmentv2>.</span></span>

- <span data-ttu-id="9361d-126">Wie Sie eine Verbindung mit Exchange Online PowerShell herstellen, finden Sie unter [Herstellen einer Verbindung mit Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="9361d-126">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="9361d-127">Informationen zum Herstellen einer Verbindung mit dem eigenständigen Exchange Online Protection PowerShell finden Sie unter [Verbinden mit PowerShell in Exchange Online Protection](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="9361d-127">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="9361d-128">Bevor Sie die Verfahren in diesem Artikel tun können, müssen Ihnen die entsprechenden Berechtigungen zugewiesen werden:</span><span class="sxs-lookup"><span data-stu-id="9361d-128">You need to be assigned permissions before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="9361d-129">Zum Erstellen, Ändern und Löschen von Richtlinien für sichere  Anlagen müssen Sie Mitglied der Rollengruppe "Organisationsverwaltung" oder  "Sicherheitsadministrator" im Security & Compliance **Center** und Mitglied der Rollengruppe "Organisationsverwaltung" in Exchange Online sein. </span><span class="sxs-lookup"><span data-stu-id="9361d-129">To create, modify, and delete Safe Attachments policies, you need to be a member of the **Organization Management** or **Security Administrator** role groups in the Security & Compliance Center **and** a member of the **Organization Management** role group in Exchange Online.</span></span>
  - <span data-ttu-id="9361d-130">Für den schreibgeschützten Zugriff auf Richtlinien für sichere  Anlagen müssen  Sie Mitglied der Rollengruppe "Globaler Leser" oder "Sicherheitsleser" im Security & Compliance Center sein.</span><span class="sxs-lookup"><span data-stu-id="9361d-130">For read-only access to Safe Attachments policies, you need to be a member of the **Global Reader** or **Security Reader** role groups in the Security & Compliance Center.</span></span>

  <span data-ttu-id="9361d-131">Weitere Informationen finden Sie unter ["Berechtigungen" im Security & Compliance Center](permissions-in-the-security-and-compliance-center.md) und in Exchange [Online](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo).</span><span class="sxs-lookup"><span data-stu-id="9361d-131">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md) and [Permissions in Exchange Online](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo).</span></span>

  <span data-ttu-id="9361d-132">**Hinweise**:</span><span class="sxs-lookup"><span data-stu-id="9361d-132">**Notes**:</span></span>

  - <span data-ttu-id="9361d-133">Durch das Hinzufügen von Benutzern zur entsprechenden Azure Active Directory-Rolle im Microsoft 365 Admin Center erhalten Benutzer die erforderlichen Berechtigungen im Security & Compliance Center _und_ Berechtigungen für andere Features in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="9361d-133">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Security & Compliance Center _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="9361d-134">Weitere Informationen finden Sie unter [Informationen zu Administratorrollen](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).</span><span class="sxs-lookup"><span data-stu-id="9361d-134">For more information, see [About admin roles](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).</span></span>
  - <span data-ttu-id="9361d-135">Die Rollengruppe **Organisationsverwaltung mit Leserechten** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) ermöglicht auch einen schreibgeschützten Zugriff auf das Feature.</span><span class="sxs-lookup"><span data-stu-id="9361d-135">The **View-Only Organization Management** role group in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

- <span data-ttu-id="9361d-136">Die empfohlenen Einstellungen für Richtlinien für sichere Anlagen finden Sie unter ["Einstellungen für sichere Anlagen".](recommended-settings-for-eop-and-office365-atp.md#safe-attachments-settings)</span><span class="sxs-lookup"><span data-stu-id="9361d-136">For our recommended settings for Safe Attachments policies, see [Safe Attachments settings](recommended-settings-for-eop-and-office365-atp.md#safe-attachments-settings).</span></span>

- <span data-ttu-id="9361d-137">Es kann bis zu 30 Minuten dauern, bis eine neue oder aktualisierte Richtlinie angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="9361d-137">Allow up to 30 minutes for a new or updated policy to be applied.</span></span>

## <a name="use-the-security--compliance-center-to-create-safe-attachments-policies"></a><span data-ttu-id="9361d-138">Verwenden des Security & Compliance Center zum Erstellen von Richtlinien für sichere Anlagen</span><span class="sxs-lookup"><span data-stu-id="9361d-138">Use the Security & Compliance Center to create Safe Attachments policies</span></span>

<span data-ttu-id="9361d-139">Beim Erstellen einer benutzerdefinierten Richtlinie für sichere Anlagen im Security & Compliance Center werden die Regel für sichere Anlagen und die zugehörige Richtlinie für sichere Anlagen gleichzeitig mit demselben Namen für beide erstellt.</span><span class="sxs-lookup"><span data-stu-id="9361d-139">Creating a custom Safe Attachments policy in the Security & Compliance Center creates the safe attachment rule and the associated safe attachment policy at the same time using the same name for both.</span></span>

1. <span data-ttu-id="9361d-140">Wechseln Sie im Security & Compliance  Center zu "AtP-sichere Anlagen" zur Richtlinie zur \>  \> **Bedrohungsverwaltung.**</span><span class="sxs-lookup"><span data-stu-id="9361d-140">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Attachments**.</span></span>

2. <span data-ttu-id="9361d-141">Klicken Sie **auf der Seite "Sichere Anlagen"** auf **"Erstellen".**</span><span class="sxs-lookup"><span data-stu-id="9361d-141">On the **Safe Attachments** page, click **Create**.</span></span>

3. <span data-ttu-id="9361d-142">Der **Assistent für neue Richtlinien für sichere** Anlagen wird geöffnet.</span><span class="sxs-lookup"><span data-stu-id="9361d-142">The **New Safe Attachments policy** wizard opens.</span></span> <span data-ttu-id="9361d-143">Konfigurieren Sie **auf der Seite "Ihre Richtlinie benennen"** die folgenden Einstellungen:</span><span class="sxs-lookup"><span data-stu-id="9361d-143">On the **Name your policy** page, configure the following settings:</span></span>

   - <span data-ttu-id="9361d-144">**Name**: Geben Sie einen eindeutigen, aussagekräftigen Namen für die Richtlinie ein.</span><span class="sxs-lookup"><span data-stu-id="9361d-144">**Name**: Enter a unique, descriptive name for the policy.</span></span>

   - <span data-ttu-id="9361d-145">**Beschreibung**: Geben Sie eine optionale Beschreibung für die Richtlinie ein.</span><span class="sxs-lookup"><span data-stu-id="9361d-145">**Description**: Enter an optional description for the policy.</span></span>

   <span data-ttu-id="9361d-146">Klicken Sie nach Abschluss des Vorgangs auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="9361d-146">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="9361d-147">Konfigurieren Sie **auf** der angezeigten Seite "Einstellungen" die folgenden Einstellungen:</span><span class="sxs-lookup"><span data-stu-id="9361d-147">On the **Settings** page that appears, configure the following settings:</span></span>

   - <span data-ttu-id="9361d-148">**Sichere Anlagen – Unbekannte Schadsoftwareantwort:** Wählen Sie einen der folgenden Werte aus:</span><span class="sxs-lookup"><span data-stu-id="9361d-148">**Safe Attachments unknown malware response**: Select one of the following values:</span></span>

     - <span data-ttu-id="9361d-149">**Aus**: In der Regel wird dieser Wert nicht empfohlen.</span><span class="sxs-lookup"><span data-stu-id="9361d-149">**Off**: Typically, we don't recommend this value.</span></span>
     - <span data-ttu-id="9361d-150">**Überwachen**</span><span class="sxs-lookup"><span data-stu-id="9361d-150">**Monitor**</span></span>
     - <span data-ttu-id="9361d-151">**Block:** Dies ist der Standardwert und der empfohlene Wert in den voreingestellten Standard- und [Strict-Sicherheitsrichtlinien.](preset-security-policies.md)</span><span class="sxs-lookup"><span data-stu-id="9361d-151">**Block**: This is the default value, and the recommended value in Standard and Strict [preset security policies](preset-security-policies.md).</span></span>
     - <span data-ttu-id="9361d-152">**Replace**</span><span class="sxs-lookup"><span data-stu-id="9361d-152">**Replace**</span></span>
     - <span data-ttu-id="9361d-153">**Dynamische Übermittlung (Vorschaufeature)**</span><span class="sxs-lookup"><span data-stu-id="9361d-153">**Dynamic Delivery (Preview Feature)**</span></span>

     <span data-ttu-id="9361d-154">Diese Werte werden in den Richtlinieneinstellungen für [sichere Anlagen erläutert.](atp-safe-attachments.md#safe-attachments-policy-settings)</span><span class="sxs-lookup"><span data-stu-id="9361d-154">These values are explained in [Safe Attachments policy settings](atp-safe-attachments.md#safe-attachments-policy-settings).</span></span>

   - <span data-ttu-id="9361d-155">Senden Sie die Anlage an die folgende E-Mail-Adresse: Für  die Aktionswerte **"Blockieren",** **"Überwachen"** oder "Ersetzen" können Sie "Umleitung aktivieren" auswählen, um Nachrichten mit Schadsoftwareanlagen zur Analyse und Untersuchung an die angegebene interne oder externe E-Mail-Adresse zu senden.  </span><span class="sxs-lookup"><span data-stu-id="9361d-155">**Send the attachment to the following email address**: For the action values **Block**, **Monitor**, or **Replace**, you can select **Enable redirect** to send messages that contain malware attachments to the specified internal or external email address for analysis and investigation.</span></span>

     <span data-ttu-id="9361d-156">Die Empfehlung für Standard- und Strict-Richtlinieneinstellungen besteht in der Aktivierung der Umleitung.</span><span class="sxs-lookup"><span data-stu-id="9361d-156">The recommendation for Standard and Strict policy settings is to enable redirection.</span></span> <span data-ttu-id="9361d-157">Weitere Informationen finden Sie unter Einstellungen [für sichere Anlagen.](recommended-settings-for-eop-and-office365-atp.md#safe-attachments-settings)</span><span class="sxs-lookup"><span data-stu-id="9361d-157">For more information, see [Safe Attachments settings](recommended-settings-for-eop-and-office365-atp.md#safe-attachments-settings).</span></span>

   - <span data-ttu-id="9361d-158">**Wenden Sie** die oben aufgeführte Auswahl an, wenn bei  der Schadsoftwareprüfung auf Anlagen ein Zeitfehler auftritt oder ein Fehler auftritt: Die von "Sichere Anlagen" angegebene Aktion wird auf Nachrichten angewendet, auch wenn die Überprüfung auf sichere Anlagen nicht abgeschlossen werden kann.</span><span class="sxs-lookup"><span data-stu-id="9361d-158">**Apply the above selection if malware scanning for attachments times out or error occurs**: The action specified by **Safe Attachments unknown malware response** is taken on messages even when Safe Attachments scanning can't complete.</span></span> <span data-ttu-id="9361d-159">Wenn Sie diese Option ausgewählt haben, wählen Sie immer **"Umleitung aktiviert" aus.**</span><span class="sxs-lookup"><span data-stu-id="9361d-159">If you selected this option, always select **Enabled redirect**.</span></span> <span data-ttu-id="9361d-160">Andernfalls gehen Nachrichten möglicherweise verloren.</span><span class="sxs-lookup"><span data-stu-id="9361d-160">Otherwise, messages might be lost.</span></span>

   <span data-ttu-id="9361d-161">Klicken Sie nach Abschluss des Vorgangs auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="9361d-161">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="9361d-162">Identifizieren Sie auf der angezeigten Seite "Angewendet **auf"** die internen Empfänger, auf die die Richtlinie angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="9361d-162">On the **Applied to** page that appears, identify the internal recipients that the policy applies to.</span></span>

   <span data-ttu-id="9361d-163">Sie können eine Bedingung oder Ausnahme nur einmal verwenden, aber Sie können mehrere Werte für die Bedingung oder Ausnahme angeben.</span><span class="sxs-lookup"><span data-stu-id="9361d-163">You can only use a condition or exception once, but you can specify multiple values for the condition or exception.</span></span> <span data-ttu-id="9361d-164">Bei mehreren Werten derselben Bedingung oder Ausnahme wird ODER-Logik verwendet (z. B. _\<recipient1\>_ oder _\<recipient2\>_).</span><span class="sxs-lookup"><span data-stu-id="9361d-164">Multiple values of the same condition or exception use OR logic (for example, _\<recipient1\>_ or _\<recipient2\>_).</span></span> <span data-ttu-id="9361d-165">Bei unterschiedlichen Bedingungen oder Ausnahmen wird UND-Logik verwendet (z. B. _\<recipient1\>_ und _\<member of group 1\>_).</span><span class="sxs-lookup"><span data-stu-id="9361d-165">Different conditions or exceptions use AND logic (for example, _\<recipient1\>_ and _\<member of group 1\>_).</span></span>

   <span data-ttu-id="9361d-166">Klicken **Sie auf Bedingung hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="9361d-166">Click **Add a condition**.</span></span> <span data-ttu-id="9361d-167">Wählen Sie in der angezeigten Dropdownliste eine Bedingung unter **"Angewendet" aus, wenn:**</span><span class="sxs-lookup"><span data-stu-id="9361d-167">In the dropdown that appears, select a condition under **Applied if**:</span></span>

   - <span data-ttu-id="9361d-168">**Der Empfänger ist:** Gibt ein oder mehrere Postfächer, E-Mail-Benutzer oder E-Mail-Kontakte in Ihrer Organisation an.</span><span class="sxs-lookup"><span data-stu-id="9361d-168">**The recipient is**: Specifies one or more mailboxes, mail users, or mail contacts in your organization.</span></span>
   - <span data-ttu-id="9361d-169">**Der Empfänger ist Mitglied von**: Gibt eine oder mehrere Gruppen in Ihrer Organisation an.</span><span class="sxs-lookup"><span data-stu-id="9361d-169">**The recipient is a member of**: Specifies one or more groups in your organization.</span></span>
   - <span data-ttu-id="9361d-170">**Die Empfängerdomäne ist**: Gibt Empfänger in einer oder mehreren der konfigurierten akzeptierten Domänen in Ihrer Organisation an.</span><span class="sxs-lookup"><span data-stu-id="9361d-170">**The recipient domain is**: Specifies recipients in one or more of the configured accepted domains in your organization.</span></span>

   <span data-ttu-id="9361d-171">Nachdem Sie die Bedingung ausgewählt haben, wird eine entsprechende Dropdownliste mit einem **Beliebigen dieser Kontrollkästchen** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="9361d-171">After you select the condition, a corresponding dropdown appears with an **Any of these** box.</span></span>

   - <span data-ttu-id="9361d-172">Klicken Sie in das Feld, und führen Sie einen Bildlauf durch die Liste der werte aus.</span><span class="sxs-lookup"><span data-stu-id="9361d-172">Click in the box and scroll through the list of values to select.</span></span>
   - <span data-ttu-id="9361d-173">Klicken Sie in das Feld, und beginnen Sie mit der Eingabe, um die Liste zu filtern und einen Wert auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="9361d-173">Click in the box and start typing to filter the list and select a value.</span></span>
   - <span data-ttu-id="9361d-174">Wenn Sie weitere Werte hinzufügen möchten, klicken Sie in einen leeren Bereich des Felds.</span><span class="sxs-lookup"><span data-stu-id="9361d-174">To add additional values, click in an empty area in the box.</span></span>
   - <span data-ttu-id="9361d-175">Klicken Sie zum Entfernen einzelner Einträge **auf** das Symbol ![ ](../../media/scc-remove-icon.png) "Entfernen" für den Wert.</span><span class="sxs-lookup"><span data-stu-id="9361d-175">To remove individual entries, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the value.</span></span>
   - <span data-ttu-id="9361d-176">Um die gesamte Bedingung zu entfernen, **klicken** Sie in der Bedingung ![ auf ](../../media/scc-remove-icon.png) "Entfernen".</span><span class="sxs-lookup"><span data-stu-id="9361d-176">To remove the whole condition, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the condition.</span></span>

   <span data-ttu-id="9361d-177">Klicken Sie zum Hinzufügen einer zusätzlichen Bedingung auf "Bedingung **hinzufügen",** und wählen Sie unter **"Angewendet"** einen verbleibenden Wert aus, wenn .</span><span class="sxs-lookup"><span data-stu-id="9361d-177">To add an additional condition, click **Add a condition** and select a remaining value under **Applied if**.</span></span>

   <span data-ttu-id="9361d-178">Klicken Sie zum Hinzufügen von Ausnahmen auf **"Bedingung hinzufügen",** und wählen Sie unter "Außer wenn" **eine Ausnahme aus.**</span><span class="sxs-lookup"><span data-stu-id="9361d-178">To add exceptions, click **Add a condition** and select an exception under **Except if**.</span></span> <span data-ttu-id="9361d-179">Die Einstellungen und das Verhalten entsprechen genau den Bedingungen.</span><span class="sxs-lookup"><span data-stu-id="9361d-179">The settings and behavior are exactly like the conditions.</span></span>

   <span data-ttu-id="9361d-180">Klicken Sie nach Abschluss des Vorgangs auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="9361d-180">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="9361d-181">Überprüfen Sie **ihre Einstellungen auf** der angezeigten Seite "Einstellungen überprüfen".</span><span class="sxs-lookup"><span data-stu-id="9361d-181">On the **Review your settings** page that appears, review your settings.</span></span> <span data-ttu-id="9361d-182">Sie können **in** jeder Einstellung auf "Bearbeiten" klicken, um sie zu ändern.</span><span class="sxs-lookup"><span data-stu-id="9361d-182">You can click **Edit** on each setting to modify it.</span></span>

   <span data-ttu-id="9361d-183">Klicken Sie nach Abschluss des Vorgangs auf **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="9361d-183">When you're finished, click **Finish**.</span></span>

## <a name="use-the-security--compliance-center-to-view-safe-attachments-policies"></a><span data-ttu-id="9361d-184">Verwenden des Security & Compliance Center zum Anzeigen von Richtlinien für sichere Anlagen</span><span class="sxs-lookup"><span data-stu-id="9361d-184">Use the Security & Compliance Center to view Safe Attachments policies</span></span>

1. <span data-ttu-id="9361d-185">Wechseln Sie im Security & Compliance  Center zu "AtP-sichere Anlagen" zur Richtlinie zur \>  \> **Bedrohungsverwaltung.**</span><span class="sxs-lookup"><span data-stu-id="9361d-185">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Attachments**.</span></span>

2. <span data-ttu-id="9361d-186">Wählen Sie **auf der** Seite "Sichere Anlagen" eine Richtlinie aus der Liste aus, und klicken Sie darauf (aktivieren Sie nicht das Kontrollkästchen).</span><span class="sxs-lookup"><span data-stu-id="9361d-186">On the **Safe Attachments** page, select a policy from the list and click on it (don't select the check box).</span></span>

   <span data-ttu-id="9361d-187">Die Richtliniendetails werden in einem Flyout angezeigt.</span><span class="sxs-lookup"><span data-stu-id="9361d-187">The policy details appear in a fly out</span></span>

## <a name="use-the-security--compliance-center-to-modify-safe-attachments-policies"></a><span data-ttu-id="9361d-188">Verwenden des Security & Compliance Center zum Ändern von Richtlinien für sichere Anlagen</span><span class="sxs-lookup"><span data-stu-id="9361d-188">Use the Security & Compliance Center to modify Safe Attachments policies</span></span>

1. <span data-ttu-id="9361d-189">Wechseln Sie im Security & Compliance  Center zu "AtP-sichere Anlagen" zur Richtlinie zur \>  \> **Bedrohungsverwaltung.**</span><span class="sxs-lookup"><span data-stu-id="9361d-189">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Attachments**.</span></span>

2. <span data-ttu-id="9361d-190">Wählen Sie **auf der** Seite "Sichere Anlagen" eine Richtlinie aus der Liste aus, und klicken Sie darauf (aktivieren Sie nicht das Kontrollkästchen).</span><span class="sxs-lookup"><span data-stu-id="9361d-190">On the **Safe Attachments** page, select a policy from the list and click on it (don't select the check box).</span></span>

3. <span data-ttu-id="9361d-191">Klicken Sie in den angezeigten Richtliniendetails auf **"Richtlinie bearbeiten".**</span><span class="sxs-lookup"><span data-stu-id="9361d-191">In the policy details fly out that appears, click **Edit policy**.</span></span>

<span data-ttu-id="9361d-192">Die verfügbaren Einstellungen im angezeigten Flyout sind identisch mit den einstellungen, die im Abschnitt "Verwenden des [Security & Compliance Center](#use-the-security--compliance-center-to-create-safe-attachments-policies) zum Erstellen von Richtlinien für sichere Anlagen" beschrieben sind.</span><span class="sxs-lookup"><span data-stu-id="9361d-192">The available settings in the fly out that appears are identical to those described in the [Use the Security & Compliance Center to create Safe Attachments policies](#use-the-security--compliance-center-to-create-safe-attachments-policies) section.</span></span>

<span data-ttu-id="9361d-193">Informationen zum Aktivieren oder Deaktivieren einer Richtlinie oder zum Festlegen der Prioritätsreihenfolge der Richtlinie finden Sie in den folgenden Abschnitten.</span><span class="sxs-lookup"><span data-stu-id="9361d-193">To enable or disable a policy or set the policy priority order, see the following sections.</span></span>

### <a name="enable-or-disable-safe-attachments-policies"></a><span data-ttu-id="9361d-194">Aktivieren oder Deaktivieren von Richtlinien für sichere Anlagen</span><span class="sxs-lookup"><span data-stu-id="9361d-194">Enable or disable Safe Attachments policies</span></span>

1. <span data-ttu-id="9361d-195">Wechseln Sie im Security & Compliance  Center zu "AtP-sichere Anlagen" zur Richtlinie zur \>  \> **Bedrohungsverwaltung.**</span><span class="sxs-lookup"><span data-stu-id="9361d-195">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Attachments**.</span></span>

2. <span data-ttu-id="9361d-196">Beachten Sie den  Wert in der Statusspalte:</span><span class="sxs-lookup"><span data-stu-id="9361d-196">Notice the value in the **Status** column:</span></span>

   - <span data-ttu-id="9361d-197">Umschalten nach links</span><span class="sxs-lookup"><span data-stu-id="9361d-197">Move the toggle to the left</span></span> ![Richtlinie deaktivieren](../../media/scc-toggle-off.png) <span data-ttu-id="9361d-199">, um die Richtlinie zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="9361d-199">to disable the policy.</span></span>

   - <span data-ttu-id="9361d-200">Umschalten nach rechts</span><span class="sxs-lookup"><span data-stu-id="9361d-200">Move the toggle to the right</span></span> ![Richtlinie aktivieren](../../media/scc-toggle-on.png) <span data-ttu-id="9361d-202">, um die Richtlinie zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="9361d-202">to enable the policy.</span></span>

### <a name="set-the-priority-of-safe-attachments-policies"></a><span data-ttu-id="9361d-203">Festlegen der Priorität von Richtlinien für sichere Anlagen</span><span class="sxs-lookup"><span data-stu-id="9361d-203">Set the priority of Safe Attachments policies</span></span>

<span data-ttu-id="9361d-204">Standardmäßig erhalten Richtlinien für sichere Anlagen eine Priorität, die auf der Reihenfolge basiert, in der sie erstellt wurden (neuere Richtlinien haben eine niedrigere Priorität als ältere Richtlinien).</span><span class="sxs-lookup"><span data-stu-id="9361d-204">By default, Safe Attachments policies are given a priority that's based on the order they were created in (newer polices are lower priority than older policies).</span></span> <span data-ttu-id="9361d-205">Eine niedrigere Prioritätsnummer gibt eine höhere Priorität für die Richtlinie an (0 ist die höchste), und Richtlinien werden in der Reihenfolge der Priorität verarbeitet (Richtlinien mit einer höheren Priorität werden vor Richtlinien mit einer niedrigeren Priorität verarbeitet).</span><span class="sxs-lookup"><span data-stu-id="9361d-205">A lower priority number indicates a higher priority for the policy (0 is the highest), and policies are processed in priority order (higher priority policies are processed before lower priority policies).</span></span> <span data-ttu-id="9361d-206">Keine zwei Richtlinien können die gleiche Priorität aufweisen, und die Richtlinienverarbeitung endet, nachdem die erste Richtlinie angewendet wurde.</span><span class="sxs-lookup"><span data-stu-id="9361d-206">No two policies can have the same priority, and policy processing stops after the first policy is applied.</span></span>

<span data-ttu-id="9361d-207">Weitere Informationen über die Prioritätsreihenfolge und darüber, wie mehrere Richtlinien ausgewertet und angewendet werden, finden Sie unter [Reihenfolge und Priorität beim E-Mail-Schutz](how-policies-and-protections-are-combined.md).</span><span class="sxs-lookup"><span data-stu-id="9361d-207">For more information about the order of precedence and how multiple policies are evaluated and applied, see [Order and precedence of email protection](how-policies-and-protections-are-combined.md).</span></span>

<span data-ttu-id="9361d-208">Richtlinien für sichere Anlagen werden in der Reihenfolge angezeigt, in der sie verarbeitet werden (die erste Richtlinie hat den **Prioritätswert** 0).</span><span class="sxs-lookup"><span data-stu-id="9361d-208">Safe Attachments policies are displayed in the order they're processed (the first policy has the **Priority** value 0).</span></span>

<span data-ttu-id="9361d-209">**Hinweis:** Im Security & Compliance Center können Sie die Priorität der Richtlinie für sichere Anlagen erst ändern, nachdem Sie sie erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="9361d-209">**Note**: In the Security & Compliance Center, you can only change the priority of the Safe Attachments policy after you create it.</span></span> <span data-ttu-id="9361d-210">In PowerShell können Sie die Standardpriorität überschreiben, wenn Sie die Regel für sichere Anlagen erstellen (was sich auf die Priorität vorhandener Regeln auswirken kann).</span><span class="sxs-lookup"><span data-stu-id="9361d-210">In PowerShell, you can override the default priority when you create the safe attachment rule (which can affect the priority of existing rules).</span></span>

<span data-ttu-id="9361d-211">Zum Ändern der Priorität einer Richtlinie verschieben Sie die Richtlinie in der Liste nach oben oder unten (Sie können den **Priorität**-Wert im Security & Compliance Center nicht direkt ändern).</span><span class="sxs-lookup"><span data-stu-id="9361d-211">To change the priority of a policy, move the policy up or down in the list (you can't directly modify the **Priority** number in the Security & Compliance Center).</span></span>

1. <span data-ttu-id="9361d-212">Wechseln Sie im Security & Compliance  Center zu "AtP-sichere Anlagen" zur Richtlinie zur \>  \> **Bedrohungsverwaltung.**</span><span class="sxs-lookup"><span data-stu-id="9361d-212">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Attachments**.</span></span>

2. <span data-ttu-id="9361d-213">Wählen Sie **auf der** Seite "Sichere Anlagen" eine Richtlinie aus der Liste aus, und klicken Sie darauf (aktivieren Sie nicht das Kontrollkästchen).</span><span class="sxs-lookup"><span data-stu-id="9361d-213">On the **Safe Attachments** page, select a policy from the list and click on it (don't select the check box).</span></span>

3. <span data-ttu-id="9361d-214">Klicken Sie in den angezeigten Richtliniendetails auf die Schaltfläche "Verfügbare Priorität".</span><span class="sxs-lookup"><span data-stu-id="9361d-214">In the policy details fly out that appears, click the available priority button.</span></span>

   - <span data-ttu-id="9361d-215">Die Richtlinie für sichere Anlagen mit dem **Prioritätswert** **0** verfügt nur über die Schaltfläche "Priorität **verringern".**</span><span class="sxs-lookup"><span data-stu-id="9361d-215">The Safe Attachments policy with the **Priority** value **0** has only the **Decrease priority** button available.</span></span>

   - <span data-ttu-id="9361d-216">Für die Richtlinie für sichere Anlagen mit dem **niedrigsten** Prioritätswert (z. B. **3)** ist nur die Schaltfläche "Priorität **erhöhen"** verfügbar.</span><span class="sxs-lookup"><span data-stu-id="9361d-216">The Safe Attachments policy with the lowest **Priority** value (for example, **3**) has only the **Increase priority** button available.</span></span>

   - <span data-ttu-id="9361d-217">Wenn Sie über drei oder mehr Richtlinien für sichere Anlagen verfügen, stehen richtlinien zwischen dem höchsten und dem niedrigsten Prioritätswert sowohl die Schaltflächen "Priorität erhöhen" als auch **"Priorität verringern"** zur Verfügung. </span><span class="sxs-lookup"><span data-stu-id="9361d-217">If you have three or more Safe Attachments policies, policies between the highest and lowest priority values have both the **Increase priority** and **Decrease priority** buttons available.</span></span>

4. <span data-ttu-id="9361d-218">Klicken **Sie auf "Priorität erhöhen"** **oder "Priorität verringern",** um den **Prioritätswert zu** ändern.</span><span class="sxs-lookup"><span data-stu-id="9361d-218">Click **Increase priority** or **Decrease priority** to change the **Priority** value.</span></span>

5. <span data-ttu-id="9361d-219">Klicken Sie nach Abschluss des Vorgangs auf **Schließen**.</span><span class="sxs-lookup"><span data-stu-id="9361d-219">When you're finished, click **Close**.</span></span>

## <a name="use-the-security--compliance-center-to-remove-safe-attachments-policies"></a><span data-ttu-id="9361d-220">Verwenden des Security & Compliance Center zum Entfernen von Richtlinien für sichere Anlagen</span><span class="sxs-lookup"><span data-stu-id="9361d-220">Use the Security & Compliance Center to remove Safe Attachments policies</span></span>

1. <span data-ttu-id="9361d-221">Wechseln Sie im Security & Compliance  Center zu "AtP-sichere Anlagen" zur Richtlinie zur \>  \> **Bedrohungsverwaltung.**</span><span class="sxs-lookup"><span data-stu-id="9361d-221">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Attachments**.</span></span>

2. <span data-ttu-id="9361d-222">Wählen Sie **auf der** Seite "Sichere Anlagen" eine Richtlinie aus der Liste aus, und klicken Sie darauf (aktivieren Sie nicht das Kontrollkästchen).</span><span class="sxs-lookup"><span data-stu-id="9361d-222">On the **Safe Attachments** page, select a policy from the list and click on it (don't select the check box).</span></span>

3. <span data-ttu-id="9361d-223">Klicken Sie in den angezeigten Richtliniendetails auf "Richtlinie löschen", und klicken Sie dann **im** angezeigten Warndialogfeld auf "Ja".</span><span class="sxs-lookup"><span data-stu-id="9361d-223">In the policy details fly out that appears, click **Delete policy**, and then click **Yes** in the warning dialog that appears.</span></span>

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-attachments-policies"></a><span data-ttu-id="9361d-224">Verwenden von Exchange Online PowerShell oder eigenständiger EOP PowerShell zum Konfigurieren von Richtlinien für sichere Anlagen</span><span class="sxs-lookup"><span data-stu-id="9361d-224">Use Exchange Online PowerShell or standalone EOP PowerShell to configure Safe Attachments policies</span></span>

<span data-ttu-id="9361d-225">Wie zuvor beschrieben, besteht eine Richtlinie für sichere Anlagen aus einer Richtlinie für sichere Anlagen und einer Regel für sichere Anlagen.</span><span class="sxs-lookup"><span data-stu-id="9361d-225">As previously described, a Safe Attachments policy consists of a safe attachment policy and a safe attachment rule.</span></span>

<span data-ttu-id="9361d-226">In PowerShell ist der Unterschied zwischen sicheren Anlagenrichtlinien und Regeln für sichere Anlagen offensichtlich.</span><span class="sxs-lookup"><span data-stu-id="9361d-226">In PowerShell, the difference between safe attachment policies and safe attachment rules is apparent.</span></span> <span data-ttu-id="9361d-227">Sie verwalten sichere Anlagenrichtlinien mithilfe der **\* Cmdlets "-SafeAttachmentPolicy",** und Sie verwalten regeln sichere Anlagen mithilfe der **\* Cmdlets "-SafeAttachmentRule".**</span><span class="sxs-lookup"><span data-stu-id="9361d-227">You manage safe attachment policies by using the **\*-SafeAttachmentPolicy** cmdlets, and you manage safe attachment rules by using the **\*-SafeAttachmentRule** cmdlets.</span></span>

- <span data-ttu-id="9361d-228">In PowerShell erstellen Sie zuerst die Richtlinie für sichere Anlagen und dann die Regel für sichere Anlagen, die die Richtlinie identifiziert, auf die die Regel angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="9361d-228">In PowerShell, you create the safe attachment policy first, then you create the safe attachment rule that identifies the policy that the rule applies to.</span></span>
- <span data-ttu-id="9361d-229">In PowerShell ändern Sie die Einstellungen in der Richtlinie für sichere Anlagen und die Regel für sichere Anlagen separat.</span><span class="sxs-lookup"><span data-stu-id="9361d-229">In PowerShell, you modify the settings in the safe attachment policy and the safe attachment rule separately.</span></span>
- <span data-ttu-id="9361d-230">Wenn Sie eine Richtlinie für sichere Anlagen aus PowerShell entfernen, wird die entsprechende Regel für sichere Anlagen nicht automatisch entfernt und umgekehrt.</span><span class="sxs-lookup"><span data-stu-id="9361d-230">When you remove a safe attachment policy from PowerShell, the corresponding safe attachment rule isn't automatically removed, and vice versa.</span></span>

### <a name="use-powershell-to-create-safe-attachments-policies"></a><span data-ttu-id="9361d-231">Verwenden von PowerShell zum Erstellen von Richtlinien für sichere Anlagen</span><span class="sxs-lookup"><span data-stu-id="9361d-231">Use PowerShell to create Safe Attachments policies</span></span>

<span data-ttu-id="9361d-232">Das Erstellen einer Richtlinie für sichere Anlagen in PowerShell besteht aus zwei Schritte:</span><span class="sxs-lookup"><span data-stu-id="9361d-232">Creating a Safe Attachments policy in PowerShell is a two-step process:</span></span>

1. <span data-ttu-id="9361d-233">Erstellen Sie die Richtlinie für sichere Anlagen.</span><span class="sxs-lookup"><span data-stu-id="9361d-233">Create the safe attachment policy.</span></span>
2. <span data-ttu-id="9361d-234">Erstellen Sie die Regel für sichere Anlagen, die die Richtlinie für sichere Anlagen angibt, auf die die Regel angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="9361d-234">Create the safe attachment rule that specifies the safe attachment policy that the rule applies to.</span></span>

 <span data-ttu-id="9361d-235">**Hinweise**:</span><span class="sxs-lookup"><span data-stu-id="9361d-235">**Notes**:</span></span>

- <span data-ttu-id="9361d-236">Sie können eine neue Regel für sichere Anlagen erstellen und ihr eine vorhandene, nicht zugeordnete Richtlinie für sichere Anlagen zuweisen.</span><span class="sxs-lookup"><span data-stu-id="9361d-236">You can create a new safe attachment rule and assign an existing, unassociated safe attachment policy to it.</span></span> <span data-ttu-id="9361d-237">Eine Regel für sichere Anlagen kann nicht mehr als einer Richtlinie für sichere Anlagen zugeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="9361d-237">A safe attachment rule can't be associated with more than one safe attachment policy.</span></span>

- <span data-ttu-id="9361d-238">Sie können die folgenden Einstellungen für neue Richtlinien für sichere Anlagen in PowerShell konfigurieren, die im Security & Compliance Center erst nach dem Erstellen der Richtlinie verfügbar sind:</span><span class="sxs-lookup"><span data-stu-id="9361d-238">You can configure the following settings on new safe attachment policies in PowerShell that aren't available in the Security & Compliance Center until after you create the policy:</span></span>
  - <span data-ttu-id="9361d-239">Erstellen Sie die neue Richtlinie als deaktiviert _(aktiviert_ `$false` im **Cmdlet "New-SafeAttachmentRule").**</span><span class="sxs-lookup"><span data-stu-id="9361d-239">Create the new policy as disabled (_Enabled_ `$false` on the **New-SafeAttachmentRule** cmdlet).</span></span>
  - <span data-ttu-id="9361d-240">Legen Sie die Priorität der Richtlinie während der Erstellung (_Priorität_ ) im _\<Number\>_ **Cmdlet "New-SafeAttachmentRule"** festgelegt.</span><span class="sxs-lookup"><span data-stu-id="9361d-240">Set the priority of the policy during creation (_Priority_ _\<Number\>_) on the **New-SafeAttachmentRule** cmdlet).</span></span>

- <span data-ttu-id="9361d-241">Eine neue Richtlinie für sichere Anlagen, die Sie in PowerShell erstellen, wird erst im Security & Compliance Center angezeigt, wenn Sie die Richtlinie einer Regel für sichere Anlagen zuweisen.</span><span class="sxs-lookup"><span data-stu-id="9361d-241">A new safe attachment policy that you create in PowerShell isn't visible in the Security & Compliance Center until you assign the policy to a safe attachment rule.</span></span>

#### <a name="step-1-use-powershell-to-create-a-safe-attachment-policy"></a><span data-ttu-id="9361d-242">Schritt 1: Erstellen einer sicheren Anlagenrichtlinie mithilfe von PowerShell</span><span class="sxs-lookup"><span data-stu-id="9361d-242">Step 1: Use PowerShell to create a safe attachment policy</span></span>

<span data-ttu-id="9361d-243">Verwenden Sie die folgende Syntax, um eine richtlinie für sichere Anlagen zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="9361d-243">To create a safe attachment policy, use this syntax:</span></span>

```PowerShell
New-SafeAttachmentPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] [-Action <Allow | Block | Replace | DynamicDelivery>] [-Redirect <$true | $false>] [-RedirectAddress <SMTPEmailAddress>] [-ActionOnError <$true | $false>]
```

<span data-ttu-id="9361d-244">In diesem Beispiel wird eine Richtlinie für sichere Anlagen namens "Contoso All" mit den folgenden Werten erstellt:</span><span class="sxs-lookup"><span data-stu-id="9361d-244">This example creates a safe attachment policy named Contoso All with the following values:</span></span>

- <span data-ttu-id="9361d-245">Blockieren von Nachrichten, die Schadsoftware enthalten, indem Sie die Überprüfung auf sichere Dokumente (der Parameter _"Action"_ wird nicht verwendet, und der Standardwert ist ) `Block` blockieren.</span><span class="sxs-lookup"><span data-stu-id="9361d-245">Block messages that are found to contain malware by Safe Documents scanning (we aren't using the _Action_ parameter, and the default value is `Block`).</span></span>
- <span data-ttu-id="9361d-246">Die Umleitung ist aktiviert, und Nachrichten, die Schadsoftware enthalten, werden sec-ops@contoso.com Analyse- und Untersuchungsnachrichten gesendet.</span><span class="sxs-lookup"><span data-stu-id="9361d-246">Redirection is enabled, and messages that are found to contain malware are sent to sec-ops@contoso.com for analysis and investigation.</span></span>
- <span data-ttu-id="9361d-247">Wenn die Überprüfung auf sichere Anlagen nicht verfügbar ist oder Fehler auftreten, senden Sie die Nachricht nicht zu (wir verwenden den _Parameter "ActionOnError"_ nicht, und der Standardwert ist `$true` ).</span><span class="sxs-lookup"><span data-stu-id="9361d-247">If Safe Attachments scanning isn't available or encounters errors, don't deliver the message (we aren't using the _ActionOnError_ parameter, and the default value is `$true`).</span></span>

```PowerShell
New-SafeAttachmentPolicy -Name "Contoso All" -Redirect $true -RedirectAddress sec-ops@contoso.com
```

<span data-ttu-id="9361d-248">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [New-SafeAttachmentPolicy](https://docs.microsoft.com/powershell/module/exchange/new-safeattachmentpolicy).</span><span class="sxs-lookup"><span data-stu-id="9361d-248">For detailed syntax and parameter information, see [New-SafeAttachmentPolicy](https://docs.microsoft.com/powershell/module/exchange/new-safeattachmentpolicy).</span></span>

#### <a name="step-2-use-powershell-to-create-a-safe-attachment-rule"></a><span data-ttu-id="9361d-249">Schritt 2: Verwenden von PowerShell zum Erstellen einer sicheren Anlagenregel</span><span class="sxs-lookup"><span data-stu-id="9361d-249">Step 2: Use PowerShell to create a safe attachment rule</span></span>

<span data-ttu-id="9361d-250">Verwenden Sie die folgende Syntax, um eine sichere Anlagenregel zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="9361d-250">To create a safe attachment rule, use this syntax:</span></span>

```PowerShell
New-SafeAttachmentRule -Name "<RuleName>" -SafeAttachmentPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"] [-Enabled <$true | $false>]
```

<span data-ttu-id="9361d-251">In diesem Beispiel wird eine regel für sichere Anlagen namens "Contoso All" mit den folgenden Bedingungen erstellt:</span><span class="sxs-lookup"><span data-stu-id="9361d-251">This example creates a safe attachment rule named Contoso All with the following conditions:</span></span>

- <span data-ttu-id="9361d-252">Die Regel ist der Richtlinie für sichere Anlagen namens "Contoso All" zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="9361d-252">The rule is associated with the safe attachment policy named Contoso All.</span></span>
- <span data-ttu-id="9361d-253">Die Regel gilt für alle Empfänger in der contoso.com Domäne.</span><span class="sxs-lookup"><span data-stu-id="9361d-253">The rule applies to all recipients in the contoso.com domain.</span></span>
- <span data-ttu-id="9361d-254">Da der Parameter _"Priority"_ nicht verwendet wird, wird die Standardpriorität verwendet.</span><span class="sxs-lookup"><span data-stu-id="9361d-254">Because we aren't using the _Priority_ parameter, the default priority is used.</span></span>
- <span data-ttu-id="9361d-255">Die Regel ist aktiviert (der Parameter _"Enabled"_ wird nicht verwendet, und der Standardwert ist `$true` " ).</span><span class="sxs-lookup"><span data-stu-id="9361d-255">The rule is enabled (we aren't using the _Enabled_ parameter, and the default value is `$true`).</span></span>

```powershell
New-SafeAttachmentRule -Name "Contoso All" -SafeAttachmentPolicy "Contoso All" -RecipientDomainIs contoso.com
```

<span data-ttu-id="9361d-256">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [New-SafeAttachmentRule](https://docs.microsoft.com/powershell/module/exchange/new-safeattachmentrule).</span><span class="sxs-lookup"><span data-stu-id="9361d-256">For detailed syntax and parameter information, see [New-SafeAttachmentRule](https://docs.microsoft.com/powershell/module/exchange/new-safeattachmentrule).</span></span>

### <a name="use-powershell-to-view-safe-attachment-policies"></a><span data-ttu-id="9361d-257">Verwenden von PowerShell zum Anzeigen sicherer Anlagenrichtlinien</span><span class="sxs-lookup"><span data-stu-id="9361d-257">Use PowerShell to view safe attachment policies</span></span>

<span data-ttu-id="9361d-258">Verwenden Sie die folgende Syntax, um vorhandene Richtlinien für sichere Anlagen anzeigen zu können:</span><span class="sxs-lookup"><span data-stu-id="9361d-258">To view existing safe attachment policies, use the following syntax:</span></span>

```PowerShell
Get-SafeAttachmentPolicy [-Identity "<PolicyIdentity>"] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="9361d-259">In diesem Beispiel wird eine Übersichtsliste aller Richtlinien für sichere Anlagen zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="9361d-259">This example returns a summary list of all safe attachment policies.</span></span>

```PowerShell
Get-SafeAttachmentPolicy
```

<span data-ttu-id="9361d-260">In diesem Beispiel werden detaillierte Informationen für die Richtlinie für sichere Anlagen namens "Contoso Executives" zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="9361d-260">This example returns detailed information for the safe attachment policy named Contoso Executives.</span></span>

```PowerShell
Get-SafeAttachmentPolicy -Identity "Contoso Executives" | Format-List
```

<span data-ttu-id="9361d-261">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Get-SafeAttachmentPolicy](https://docs.microsoft.com/powershell/module/exchange/get-safeattachmentpolicy).</span><span class="sxs-lookup"><span data-stu-id="9361d-261">For detailed syntax and parameter information, see [Get-SafeAttachmentPolicy](https://docs.microsoft.com/powershell/module/exchange/get-safeattachmentpolicy).</span></span>

### <a name="use-powershell-to-view-safe-attachment-rules"></a><span data-ttu-id="9361d-262">Verwenden von PowerShell zum Anzeigen sicherer Anlagenregeln</span><span class="sxs-lookup"><span data-stu-id="9361d-262">Use PowerShell to view safe attachment rules</span></span>

<span data-ttu-id="9361d-263">Verwenden Sie die folgende Syntax, um vorhandene Regeln für sichere Anlagen anzeigen zu können:</span><span class="sxs-lookup"><span data-stu-id="9361d-263">To view existing safe attachment rules, use the following syntax:</span></span>

```PowerShell
Get-SafeAttachmentRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled>] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="9361d-264">In diesem Beispiel wird eine Zusammenfassungsliste aller Regeln für sichere Anlagen zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="9361d-264">This example returns a summary list of all safe attachment rules.</span></span>

```PowerShell
Get-SafeAttachmentRule
```

<span data-ttu-id="9361d-265">Führen Sie die folgenden Befehle aus, um die Liste nach aktivierten oder deaktivierten Regeln zu filtern:</span><span class="sxs-lookup"><span data-stu-id="9361d-265">To filter the list by enabled or disabled rules, run the following commands:</span></span>

```PowerShell
Get-SafeAttachmentRule -State Disabled
```

```PowerShell
Get-SafeAttachmentRule -State Enabled
```

<span data-ttu-id="9361d-266">In diesem Beispiel werden detaillierte Informationen für die Regel für sichere Anlagen namens "Contoso Executives" zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="9361d-266">This example returns detailed information for the safe attachment rule named Contoso Executives.</span></span>

```PowerShell
Get-SafeAttachmentRule -Identity "Contoso Executives" | Format-List
```

<span data-ttu-id="9361d-267">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Get-SafeAttachmentRule](https://docs.microsoft.com/powershell/module/exchange/get-safeattachmentrule).</span><span class="sxs-lookup"><span data-stu-id="9361d-267">For detailed syntax and parameter information, see [Get-SafeAttachmentRule](https://docs.microsoft.com/powershell/module/exchange/get-safeattachmentrule).</span></span>

### <a name="use-powershell-to-modify-safe-attachment-policies"></a><span data-ttu-id="9361d-268">Verwenden von PowerShell zum Ändern sicherer Anlagenrichtlinien</span><span class="sxs-lookup"><span data-stu-id="9361d-268">Use PowerShell to modify safe attachment policies</span></span>

<span data-ttu-id="9361d-269">Sie können eine Richtlinie für sichere Anlagen in PowerShell nicht umbenennen (das **Cmdlet "Set-SafeAttachmentPolicy"** hat keinen _Parameter "Name")._</span><span class="sxs-lookup"><span data-stu-id="9361d-269">You can't rename a safe attachment policy in PowerShell (the **Set-SafeAttachmentPolicy** cmdlet has no _Name_ parameter).</span></span> <span data-ttu-id="9361d-270">Wenn Sie eine Richtlinie für sichere Anlagen im Security & Compliance Center umbenennen, benennen Sie nur die Regel für sichere Anlagen _um._</span><span class="sxs-lookup"><span data-stu-id="9361d-270">When you rename a Safe Attachments policy in the Security & Compliance Center, you're only renaming the safe attachment _rule_.</span></span>

<span data-ttu-id="9361d-271">Andernfalls sind dieselben Einstellungen verfügbar, wenn Sie eine richtlinie für sichere Anlagen erstellen, wie in Schritt [1 beschrieben:](#step-1-use-powershell-to-create-a-safe-attachment-policy) Verwenden von PowerShell zum Erstellen einer Richtlinie für sichere Anlagen weiter oben in diesem Artikel.</span><span class="sxs-lookup"><span data-stu-id="9361d-271">Otherwise, the same settings are available when you create a safe attachment policy as described in the [Step 1: Use PowerShell to create a safe attachment policy](#step-1-use-powershell-to-create-a-safe-attachment-policy) section earlier in this article.</span></span>

<span data-ttu-id="9361d-272">Verwenden Sie folgende Syntax, um eine Richtlinie für sichere Anlagen zu ändern:</span><span class="sxs-lookup"><span data-stu-id="9361d-272">To modify a safe attachment policy, use this syntax:</span></span>

```PowerShell
Set-SafeAttachmentPolicy -Identity "<PolicyName>" <Settings>
```

<span data-ttu-id="9361d-273">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Set-SafeAttachmentPolicy](https://docs.microsoft.com/powershell/module/exchange/set-safeattachmentpolicy).</span><span class="sxs-lookup"><span data-stu-id="9361d-273">For detailed syntax and parameter information, see [Set-SafeAttachmentPolicy](https://docs.microsoft.com/powershell/module/exchange/set-safeattachmentpolicy).</span></span>

### <a name="use-powershell-to-modify-safe-attachment-rules"></a><span data-ttu-id="9361d-274">Verwenden von PowerShell zum Ändern sicherer Anlagenregeln</span><span class="sxs-lookup"><span data-stu-id="9361d-274">Use PowerShell to modify safe attachment rules</span></span>

<span data-ttu-id="9361d-275">Die einzige Einstellung, die nicht verfügbar ist, wenn Sie eine sichere Anlagenregel in PowerShell ändern, ist der Parameter _"Enabled",_ mit dem Sie eine deaktivierte Regel erstellen können.</span><span class="sxs-lookup"><span data-stu-id="9361d-275">The only setting that's not available when you modify a safe attachment rule in PowerShell is the _Enabled_ parameter that allows you to create a disabled rule.</span></span> <span data-ttu-id="9361d-276">Informationen zum Aktivieren oder Deaktivieren vorhandener Regeln für sichere Anlagen finden Sie im nächsten Abschnitt.</span><span class="sxs-lookup"><span data-stu-id="9361d-276">To enable or disable existing safe attachment rules, see the next section.</span></span>

<span data-ttu-id="9361d-277">Andernfalls sind dieselben Einstellungen verfügbar, wenn Sie eine Regel erstellen, wie in Schritt [2 beschrieben:](#step-2-use-powershell-to-create-a-safe-attachment-rule) Verwenden von PowerShell zum Erstellen eines Abschnitts mit sicheren Anlagenregel weiter oben in diesem Artikel.</span><span class="sxs-lookup"><span data-stu-id="9361d-277">Otherwise, the same settings are available when you create a rule as described in the [Step 2: Use PowerShell to create a safe attachment rule](#step-2-use-powershell-to-create-a-safe-attachment-rule) section earlier in this article.</span></span>

<span data-ttu-id="9361d-278">Verwenden Sie die folgende Syntax, um eine Regel für sichere Anlagen zu ändern:</span><span class="sxs-lookup"><span data-stu-id="9361d-278">To modify a safe attachment rule, use this syntax:</span></span>

```PowerShell
Set-SafeAttachmentRule -Identity "<RuleName>" <Settings>
```

<span data-ttu-id="9361d-279">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Set-SafeAttachmentRule](https://docs.microsoft.com/powershell/module/exchange/set-safeattachmentrule).</span><span class="sxs-lookup"><span data-stu-id="9361d-279">For detailed syntax and parameter information, see [Set-SafeAttachmentRule](https://docs.microsoft.com/powershell/module/exchange/set-safeattachmentrule).</span></span>

### <a name="use-powershell-to-enable-or-disable-safe-attachment-rules"></a><span data-ttu-id="9361d-280">Verwenden von PowerShell zum Aktivieren oder Deaktivieren sicherer Anlagenregeln</span><span class="sxs-lookup"><span data-stu-id="9361d-280">Use PowerShell to enable or disable safe attachment rules</span></span>

<span data-ttu-id="9361d-281">Durch Aktivieren oder Deaktivieren einer Regel für sichere Anlagen in PowerShell wird die gesamte Richtlinie für sichere Anlagen (die Regel für sichere Anlagen und die zugewiesene Richtlinie für sichere Anlagen) aktiviert oder deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="9361d-281">Enabling or disabling a safe attachment rule in PowerShell enables or disables the whole Safe Attachments policy (the safe attachment rule and the assigned safe attachment policy).</span></span>

<span data-ttu-id="9361d-282">Verwenden Sie folgende Syntax, um eine sichere Anlagenregel in PowerShell zu aktivieren oder zu deaktivieren:</span><span class="sxs-lookup"><span data-stu-id="9361d-282">To enable or disable a safe attachment rule in PowerShell, use this syntax:</span></span>

```PowerShell
<Enable-SafeAttachmentRule | Disable-SafeAttachmentRule> -Identity "<RuleName>"
```

<span data-ttu-id="9361d-283">In diesem Beispiel wird die Regel für sichere Anlagen namens "Marketing Department" deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="9361d-283">This example disables the safe attachment rule named Marketing Department.</span></span>

```PowerShell
Disable-SafeAttachmentRule -Identity "Marketing Department"
```

<span data-ttu-id="9361d-284">In diesem Beispiel wird dieselbe Regel aktiviert.</span><span class="sxs-lookup"><span data-stu-id="9361d-284">This example enables same rule.</span></span>

```PowerShell
Enable-SafeAttachmentRule -Identity "Marketing Department"
```

<span data-ttu-id="9361d-285">Ausführliche Informationen zu Syntax und Parametern finden Sie unter ["Enable-SafeAttachmentRule"](https://docs.microsoft.com/powershell/module/exchange/enable-safeattachmentrule) und ["Disable-SafeAttachmentRule".](https://docs.microsoft.com/powershell/module/exchange/disable-safeattachmentrule)</span><span class="sxs-lookup"><span data-stu-id="9361d-285">For detailed syntax and parameter information, see [Enable-SafeAttachmentRule](https://docs.microsoft.com/powershell/module/exchange/enable-safeattachmentrule) and [Disable-SafeAttachmentRule](https://docs.microsoft.com/powershell/module/exchange/disable-safeattachmentrule).</span></span>

### <a name="use-powershell-to-set-the-priority-of-safe-attachment-rules"></a><span data-ttu-id="9361d-286">Verwenden von PowerShell zum Festlegen der Priorität sicherer Anlagenregeln</span><span class="sxs-lookup"><span data-stu-id="9361d-286">Use PowerShell to set the priority of safe attachment rules</span></span>

<span data-ttu-id="9361d-287">Der höchste Prioritätswert, den Sie für eine Regel festlegen können, ist 0.</span><span class="sxs-lookup"><span data-stu-id="9361d-287">The highest priority value you can set on a rule is 0.</span></span> <span data-ttu-id="9361d-288">Der niedrigste Wert, den Sie festlegen können, hängt von der Anzahl von Regeln ab.</span><span class="sxs-lookup"><span data-stu-id="9361d-288">The lowest value you can set depends on the number of rules.</span></span> <span data-ttu-id="9361d-289">Wenn Sie z. B. fünf Regeln haben, können Sie die Prioritätswerte 0 bis 4 verwenden.</span><span class="sxs-lookup"><span data-stu-id="9361d-289">For example, if you have five rules, you can use the priority values 0 through 4.</span></span> <span data-ttu-id="9361d-290">Das Ändern der Priorität einer vorhandenen Regel kann sich entsprechend auf andere Regeln auswirken.</span><span class="sxs-lookup"><span data-stu-id="9361d-290">Changing the priority of an existing rule can have a cascading effect on other rules.</span></span> <span data-ttu-id="9361d-291">Wenn Sie z. B. fünf benutzerdefinierte Regeln haben (Priorität 0 bis 4) und die Priorität einer Regel in 2 ändern, erhält die vorhandene Regel mit Priorität 2 die Priorität 3, und die Regel mit Priorität 3 erhält Priorität 4.</span><span class="sxs-lookup"><span data-stu-id="9361d-291">For example, if you have five custom rules (priorities 0 through 4), and you change the priority of a rule to 2, the existing rule with priority 2 is changed to priority 3, and the rule with priority 3 is changed to priority 4.</span></span>

<span data-ttu-id="9361d-292">Verwenden Sie die folgende Syntax, um die Priorität einer sicheren Anlagenregel in PowerShell zu setzen:</span><span class="sxs-lookup"><span data-stu-id="9361d-292">To set the priority of a safe attachment rule in PowerShell, use the following syntax:</span></span>

```PowerShell
Set-SafeAttachmentRule -Identity "<RuleName>" -Priority <Number>
```

<span data-ttu-id="9361d-p124">In diesem Beispiel wird die Priorität der Regel namens „Marketing Department“ auf 2 festgelegt. Alle vorhandenen Regeln mit Priorität kleiner oder gleich 2 werden um 1 verringert (die Prioritätswerte werden um 1 erhöht).</span><span class="sxs-lookup"><span data-stu-id="9361d-p124">This example sets the priority of the rule named Marketing Department to 2. All existing rules that have a priority less than or equal to 2 are decreased by 1 (their priority numbers are increased by 1).</span></span>

```PowerShell
Set-SafeAttachmentRule -Identity "Marketing Department" -Priority 2
```

<span data-ttu-id="9361d-295">**Hinweis:** Verwenden Sie zum Festlegen der Priorität einer neuen Regel beim Erstellen stattdessen den Parameter _"Priority"_ im **Cmdlet "New-SafeAttachmentRule".**</span><span class="sxs-lookup"><span data-stu-id="9361d-295">**Note**: To set the priority of a new rule when you create it, use the _Priority_ parameter on the **New-SafeAttachmentRule** cmdlet instead.</span></span>

<span data-ttu-id="9361d-296">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Set-SafeAttachmentRule](https://docs.microsoft.com/powershell/module/exchange/set-safeattachmentrule).</span><span class="sxs-lookup"><span data-stu-id="9361d-296">For detailed syntax and parameter information, see [Set-SafeAttachmentRule](https://docs.microsoft.com/powershell/module/exchange/set-safeattachmentrule).</span></span>

### <a name="use-powershell-to-remove-safe-attachment-policies"></a><span data-ttu-id="9361d-297">Verwenden von PowerShell zum Entfernen sicherer Anlagenrichtlinien</span><span class="sxs-lookup"><span data-stu-id="9361d-297">Use PowerShell to remove safe attachment policies</span></span>

<span data-ttu-id="9361d-298">Wenn Sie PowerShell verwenden, um eine Richtlinie für sichere Anlagen zu entfernen, wird die entsprechende Regel für sichere Anlagen nicht entfernt.</span><span class="sxs-lookup"><span data-stu-id="9361d-298">When you use PowerShell to remove a safe attachment policy, the corresponding safe attachment rule isn't removed.</span></span>

<span data-ttu-id="9361d-299">Verwenden Sie folgende Syntax, um eine Richtlinie für sichere Anlagen in PowerShell zu entfernen:</span><span class="sxs-lookup"><span data-stu-id="9361d-299">To remove a safe attachment policy in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-SafeAttachmentPolicy -Identity "<PolicyName>"
```

<span data-ttu-id="9361d-300">In diesem Beispiel wird die Richtlinie für sichere Anlagen namens "Marketing Department" entfernt.</span><span class="sxs-lookup"><span data-stu-id="9361d-300">This example removes the safe attachment policy named Marketing Department.</span></span>

```PowerShell
Remove-SafeAttachmentPolicy -Identity "Marketing Department"
```

<span data-ttu-id="9361d-301">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Remove-SafeAttachmentPolicy](https://docs.microsoft.com/powershell/module/exchange/remove-safeattachmentpolicy).</span><span class="sxs-lookup"><span data-stu-id="9361d-301">For detailed syntax and parameter information, see [Remove-SafeAttachmentPolicy](https://docs.microsoft.com/powershell/module/exchange/remove-safeattachmentpolicy).</span></span>

### <a name="use-powershell-to-remove-safe-attachment-rules"></a><span data-ttu-id="9361d-302">Verwenden von PowerShell zum Entfernen sicherer Anlagenregeln</span><span class="sxs-lookup"><span data-stu-id="9361d-302">Use PowerShell to remove safe attachment rules</span></span>

<span data-ttu-id="9361d-303">Wenn Sie PowerShell verwenden, um eine sichere Anlagenregel zu entfernen, wird die entsprechende Richtlinie für sichere Anlagen nicht entfernt.</span><span class="sxs-lookup"><span data-stu-id="9361d-303">When you use PowerShell to remove a safe attachment rule, the corresponding safe attachment policy isn't removed.</span></span>

<span data-ttu-id="9361d-304">Verwenden Sie folgende Syntax, um eine sichere Anlagenregel in PowerShell zu entfernen:</span><span class="sxs-lookup"><span data-stu-id="9361d-304">To remove a safe attachment rule in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-SafeAttachmentRule -Identity "<PolicyName>"
```

<span data-ttu-id="9361d-305">In diesem Beispiel wird die Regel für sichere Anlagen namens "Marketing Department" entfernt.</span><span class="sxs-lookup"><span data-stu-id="9361d-305">This example removes the safe attachment rule named Marketing Department.</span></span>

```PowerShell
Remove-SafeAttachmentRule -Identity "Marketing Department"
```

<span data-ttu-id="9361d-306">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Remove-SafeAttachmentRule](https://docs.microsoft.com/powershell/module/exchange/remove-safeattachmentrule).</span><span class="sxs-lookup"><span data-stu-id="9361d-306">For detailed syntax and parameter information, see [Remove-SafeAttachmentRule](https://docs.microsoft.com/powershell/module/exchange/remove-safeattachmentrule).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="9361d-307">Wie können Sie feststellen, dass diese Verfahren erfolgreich waren?</span><span class="sxs-lookup"><span data-stu-id="9361d-307">How do you know these procedures worked?</span></span>

<span data-ttu-id="9361d-308">Gehen Sie wie folgt vor, um sicherzustellen, dass Richtlinien für sichere Anlagen erfolgreich erstellt, geändert oder entfernt wurden:</span><span class="sxs-lookup"><span data-stu-id="9361d-308">To verify that you've successfully created, modified, or removed Safe Attachments policies, do any of the following steps:</span></span>

- <span data-ttu-id="9361d-309">Wechseln Sie im Security & Compliance  Center zu "AtP-sichere Anlagen" zur Richtlinie zur \>  \> **Bedrohungsverwaltung.**</span><span class="sxs-lookup"><span data-stu-id="9361d-309">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Attachments**.</span></span> <span data-ttu-id="9361d-310">Überprüfen Sie die Liste der Richtlinien, **deren Statuswerte** und ihre **Prioritätswerte.**</span><span class="sxs-lookup"><span data-stu-id="9361d-310">Verify the list of policies, their **Status** values, and their **Priority** values.</span></span> <span data-ttu-id="9361d-311">Um weitere Details anzuzeigen, wählen Sie die Richtlinie aus der Liste aus, und zeigen Sie die Details im Flyout an.</span><span class="sxs-lookup"><span data-stu-id="9361d-311">To view more details, select the policy from the list, and view the details in the fly out.</span></span>

- <span data-ttu-id="9361d-312">Ersetzen Sie in Exchange Online PowerShell oder Exchange Online Protection PowerShell durch den Namen der Richtlinie oder Regel, führen Sie den folgenden Befehl aus, und überprüfen Sie \<Name\> die Einstellungen:</span><span class="sxs-lookup"><span data-stu-id="9361d-312">In Exchange Online PowerShell or Exchange Online Protection PowerShell, replace \<Name\> with the name of the policy or rule, run the following command, and verify the settings:</span></span>

  ```PowerShell
  Get-SafeAttachmentPolicy -Identity "<Name>" | Format-List
  ```

  ```PowerShell
  Get-SafeAttachmentRule -Identity "<Name>" | Format-List
  ```

<span data-ttu-id="9361d-313">Überprüfen Sie die verfügbaren Defender für Office 365-Berichte, um sicherzustellen, dass sichere Anlagen Nachrichten überprüfen.</span><span class="sxs-lookup"><span data-stu-id="9361d-313">To verify that Safe Attachments is scanning messages, check the available Defender for Office 365 reports.</span></span> <span data-ttu-id="9361d-314">Weitere Informationen finden Sie unter [Anzeigen von Berichten für Defender für Office 365](view-reports-for-atp.md) und Verwenden von Explorer im Security & Compliance [Center](threat-explorer.md).</span><span class="sxs-lookup"><span data-stu-id="9361d-314">For more information, see [View reports for Defender for Office 365](view-reports-for-atp.md) and [Use Explorer in the Security & Compliance Center](threat-explorer.md).</span></span>
