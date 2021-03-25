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
ms.openlocfilehash: e96babff19ea981b953d35929813b1e08c000e32
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/25/2021
ms.locfileid: "51206504"
---
# <a name="set-up-safe-attachments-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="49bc8-103">Einrichten von Richtlinien für sichere Anlagen in Microsoft Defender für Office 365</span><span class="sxs-lookup"><span data-stu-id="49bc8-103">Set up Safe Attachments policies in Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="49bc8-104">**Gilt für**</span><span class="sxs-lookup"><span data-stu-id="49bc8-104">**Applies to**</span></span>
- [<span data-ttu-id="49bc8-105">Microsoft Defender für Office 365 Plan 1 und Plan 2</span><span class="sxs-lookup"><span data-stu-id="49bc8-105">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="49bc8-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="49bc8-106">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

> [!IMPORTANT]
> <span data-ttu-id="49bc8-107">Dieser Artikel richtet sich an Geschäftskunden, die über [Microsoft Defender für Office 365](whats-new-in-defender-for-office-365.md) verfügen.</span><span class="sxs-lookup"><span data-stu-id="49bc8-107">This article is intended for business customers who have [Microsoft Defender for Office 365](whats-new-in-defender-for-office-365.md).</span></span> <span data-ttu-id="49bc8-108">Wenn Sie ein Heimbenutzer sind, der Informationen zur Anlagenprüfung in Outlook sucht, lesen Sie [Advanced Outlook.com Security](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).</span><span class="sxs-lookup"><span data-stu-id="49bc8-108">If you're a home user looking for information about attachment scanning in Outlook, see [Advanced Outlook.com security](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).</span></span>

<span data-ttu-id="49bc8-109">Sichere Anlagen ist ein Feature in [Microsoft Defender für Office 365,](whats-new-in-defender-for-office-365.md) das eine virtuelle Umgebung verwendet, um Anlagen in eingehenden [E-Mail-Nachrichten](anti-malware-protection.md)zu überprüfen, nachdem sie vom Schutz vor Schadsoftware in Exchange Online Protection (EOP) überprüft wurden, jedoch vor der Zustellung an Empfänger.</span><span class="sxs-lookup"><span data-stu-id="49bc8-109">Safe Attachments is a feature in [Microsoft Defender for Office 365](whats-new-in-defender-for-office-365.md) that uses a virtual environment to check attachments in inbound email messages after they've been scanned by [anti-malware protection in Exchange Online Protection (EOP)](anti-malware-protection.md), but before delivery to recipients.</span></span> <span data-ttu-id="49bc8-110">Weitere Informationen finden Sie unter [Sichere Anlagen in Microsoft Defender für Office 365](safe-attachments.md).</span><span class="sxs-lookup"><span data-stu-id="49bc8-110">For more information, see [Safe Attachments in Microsoft Defender for Office 365](safe-attachments.md).</span></span>

<span data-ttu-id="49bc8-111">Es gibt keine integrierte oder standardmäßige Richtlinie für sichere Anlagen.</span><span class="sxs-lookup"><span data-stu-id="49bc8-111">There's no built-in or default Safe Attachments policy.</span></span> <span data-ttu-id="49bc8-112">Um die Überprüfung sicherer Anlagen von E-Mail-Nachrichtenanlagen zu erhalten, müssen Sie eine oder mehrere Richtlinien für sichere Anlagen erstellen, wie in diesem Artikel beschrieben.</span><span class="sxs-lookup"><span data-stu-id="49bc8-112">To get Safe Attachments scanning of email message attachments, you need to create one or more Safe Attachments policies as described in this article.</span></span>

<span data-ttu-id="49bc8-113">Sie können Richtlinien für sichere Anlagen im Security & Compliance Center oder in PowerShell (Exchange Online PowerShell für berechtigte Microsoft 365-Organisationen mit Postfächern in Exchange Online; eigenständige eOP PowerShell für Organisationen ohne Exchange &, aber mit Defender for Office 365-Add-On-Abonnements) konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="49bc8-113">You can configure Safe Attachments policies in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for eligible Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes, but with Defender for Office 365 add-on subscriptions).</span></span>

<span data-ttu-id="49bc8-114">Die grundlegenden Elemente einer Richtlinie für sichere Anlagen sind:</span><span class="sxs-lookup"><span data-stu-id="49bc8-114">The basic elements of a Safe Attachments policy are:</span></span>

- <span data-ttu-id="49bc8-115">**Die Richtlinie** für sichere Anlagen: Gibt die Aktionen für unbekannte Schadsoftwareerkennungen an, ob Nachrichten mit Schadsoftwareanlagen an eine angegebene E-Mail-Adresse gesendet werden sollen und ob Nachrichten zu senden sind, wenn die Überprüfung sicherer Anlagen nicht abgeschlossen werden kann.</span><span class="sxs-lookup"><span data-stu-id="49bc8-115">**The safe attachment policy**: Specifies the actions for unknown malware detections, whether to send messages with malware attachments to a specified email address, and whether to deliver messages if Safe Attachments scanning can't complete.</span></span>
- <span data-ttu-id="49bc8-116">**Die Regel für sichere Anlagen:** Gibt die Prioritäts- und Empfängerfilter an (auf wen die Richtlinie angewendet wird).</span><span class="sxs-lookup"><span data-stu-id="49bc8-116">**The safe attachment rule**: Specifies the priority and recipient filters (who the policy applies to).</span></span>

<span data-ttu-id="49bc8-117">Der Unterschied zwischen diesen beiden Elementen ist nicht offensichtlich, wenn Sie Richtlinien für sichere Anlagen im Security & Compliance Center verwalten:</span><span class="sxs-lookup"><span data-stu-id="49bc8-117">The difference between these two elements isn't obvious when you manage Safe Attachments polices in the Security & Compliance Center:</span></span>

- <span data-ttu-id="49bc8-118">Wenn Sie eine Richtlinie für sichere Anlagen erstellen, erstellen Sie tatsächlich eine sichere Anlagenregel und die zugeordnete richtlinie für sichere Anlagen gleichzeitig mit demselben Namen für beide.</span><span class="sxs-lookup"><span data-stu-id="49bc8-118">When you create a Safe Attachments policy, you're actually creating a safe attachment rule and the associated safe attachment policy at the same time using the same name for both.</span></span>
- <span data-ttu-id="49bc8-119">Wenn Sie eine Richtlinie für sichere Anlagen ändern, ändern Einstellungen im Zusammenhang mit dem Namen, der Priorität, aktiviert oder deaktiviert sowie Empfängerfilter die Regel für sichere Anlagen.</span><span class="sxs-lookup"><span data-stu-id="49bc8-119">When you modify a Safe Attachments policy, settings related to the name, priority, enabled or disabled, and recipient filters modify the safe attachment rule.</span></span> <span data-ttu-id="49bc8-120">Alle anderen Einstellungen ändern die zugeordnete Richtlinie für sichere Anlagen.</span><span class="sxs-lookup"><span data-stu-id="49bc8-120">All other settings modify the associated safe attachment policy.</span></span>
- <span data-ttu-id="49bc8-121">Wenn Sie eine Richtlinie für sichere Anlagen entfernen, werden die Regel für sichere Anlagen und die zugehörige Richtlinie für sichere Anlagen entfernt.</span><span class="sxs-lookup"><span data-stu-id="49bc8-121">When you remove a Safe Attachments policy, the safe attachment rule and the associated safe attachment policy are removed.</span></span>

<span data-ttu-id="49bc8-122">In Exchange Online PowerShell oder der eigenständigen EOP PowerShell verwalten Sie die Richtlinie und die Regel getrennt.</span><span class="sxs-lookup"><span data-stu-id="49bc8-122">In Exchange Online PowerShell or standalone EOP PowerShell, you manage the policy and the rule separately.</span></span> <span data-ttu-id="49bc8-123">Weitere Informationen finden Sie im Abschnitt Verwenden von [Exchange Online PowerShell oder eigenständiger EOP PowerShell](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-attachments-policies) zum Konfigurieren von Richtlinien für sichere Anlagen weiter unten in diesem Artikel.</span><span class="sxs-lookup"><span data-stu-id="49bc8-123">For more information, see the [Use Exchange Online PowerShell or standalone EOP PowerShell to configure Safe Attachments policies](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-attachments-policies) section later in this article.</span></span>

> [!NOTE]
> <span data-ttu-id="49bc8-124">Im Bereich "Globale Einstellungen" der Einstellungen für sichere Anlagen konfigurieren Sie Features, die nicht von Richtlinien für sichere Anlagen abhängig sind.</span><span class="sxs-lookup"><span data-stu-id="49bc8-124">In the global settings area of Safe Attachments settings, you configure features that are not dependent on Safe Attachments policies.</span></span> <span data-ttu-id="49bc8-125">Anweisungen finden [Sie unter Turn on Safe Attachments for SharePoint, OneDrive, and Microsoft Teams](turn-on-mdo-for-spo-odb-and-teams.md) and Safe Documents in Microsoft [365 E5](safe-docs.md).</span><span class="sxs-lookup"><span data-stu-id="49bc8-125">For instructions see [Turn on Safe Attachments for SharePoint, OneDrive, and Microsoft Teams](turn-on-mdo-for-spo-odb-and-teams.md) and [Safe Documents in Microsoft 365 E5](safe-docs.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="49bc8-126">Was sollten Sie wissen, bevor Sie beginnen?</span><span class="sxs-lookup"><span data-stu-id="49bc8-126">What do you need to know before you begin?</span></span>

- <span data-ttu-id="49bc8-127">Sie öffnen das Security & Compliance Center unter <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="49bc8-127">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="49bc8-128">Um direkt zur Seite Sichere **Anlagen zu** wechseln, verwenden Sie <https://protection.office.com/safeattachmentv2> .</span><span class="sxs-lookup"><span data-stu-id="49bc8-128">To go directly to the **Safe Attachments** page, use <https://protection.office.com/safeattachmentv2>.</span></span>

- <span data-ttu-id="49bc8-129">Wie Sie eine Verbindung mit Exchange Online PowerShell herstellen, finden Sie unter [Herstellen einer Verbindung mit Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="49bc8-129">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="49bc8-130">Informationen zum Herstellen einer Verbindung mit dem eigenständigen Exchange Online Protection PowerShell finden Sie unter [Verbinden mit PowerShell in Exchange Online Protection](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="49bc8-130">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="49bc8-131">Bevor Sie die Verfahren in diesem Artikel tun können, müssen Ihnen die entsprechenden Berechtigungen zugewiesen werden:</span><span class="sxs-lookup"><span data-stu-id="49bc8-131">You need to be assigned permissions before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="49bc8-132">Zum Erstellen, Ändern und Löschen von Richtlinien für sichere Anlagen müssen  Sie Mitglied der Rollengruppen Organisationsverwaltung oder Sicherheitsadministrator  im Security & Compliance **Center** und Mitglied der Rollengruppe Organisationsverwaltung in Exchange Online sein. </span><span class="sxs-lookup"><span data-stu-id="49bc8-132">To create, modify, and delete Safe Attachments policies, you need to be a member of the **Organization Management** or **Security Administrator** role groups in the Security & Compliance Center **and** a member of the **Organization Management** role group in Exchange Online.</span></span>
  - <span data-ttu-id="49bc8-133">Für den schreibgeschützten Zugriff auf Richtlinien für sichere Anlagen müssen  Sie Mitglied der Rollengruppen **"Globaler** Leser" oder "Sicherheitsleser" im Security & Compliance Center sein.</span><span class="sxs-lookup"><span data-stu-id="49bc8-133">For read-only access to Safe Attachments policies, you need to be a member of the **Global Reader** or **Security Reader** role groups in the Security & Compliance Center.</span></span>

  <span data-ttu-id="49bc8-134">Weitere Informationen finden Sie unter [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md) and Permissions in Exchange [Online](/exchange/permissions-exo/permissions-exo).</span><span class="sxs-lookup"><span data-stu-id="49bc8-134">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md) and [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo).</span></span>

  <span data-ttu-id="49bc8-135">**Hinweise**:</span><span class="sxs-lookup"><span data-stu-id="49bc8-135">**Notes**:</span></span>

  - <span data-ttu-id="49bc8-136">Durch das Hinzufügen von Benutzern zur entsprechenden Azure Active Directory-Rolle im Microsoft 365 Admin Center erhalten Benutzer die erforderlichen Berechtigungen im Security & Compliance Center _und_ Berechtigungen für andere Features in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="49bc8-136">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Security & Compliance Center _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="49bc8-137">Weitere Informationen finden Sie unter [Informationen zu Administratorrollen](../../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="49bc8-137">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  - <span data-ttu-id="49bc8-138">Die Rollengruppe **Organisationsverwaltung mit Leserechten** in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) ermöglicht auch einen schreibgeschützten Zugriff auf das Feature.</span><span class="sxs-lookup"><span data-stu-id="49bc8-138">The **View-Only Organization Management** role group in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

- <span data-ttu-id="49bc8-139">Unsere empfohlenen Einstellungen für Richtlinien für sichere Anlagen finden Sie unter [Einstellungen für sichere Anlagen](recommended-settings-for-eop-and-office365.md#safe-attachments-settings).</span><span class="sxs-lookup"><span data-stu-id="49bc8-139">For our recommended settings for Safe Attachments policies, see [Safe Attachments settings](recommended-settings-for-eop-and-office365.md#safe-attachments-settings).</span></span>

- <span data-ttu-id="49bc8-140">Es ist bis zu 30 Minuten zulässig, bis eine neue oder aktualisierte Richtlinie angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="49bc8-140">Allow up to 30 minutes for a new or updated policy to be applied.</span></span>

## <a name="use-the-security--compliance-center-to-create-safe-attachments-policies"></a><span data-ttu-id="49bc8-141">Erstellen von Richtlinien für & Anlagen mithilfe des Security & Compliance Centers</span><span class="sxs-lookup"><span data-stu-id="49bc8-141">Use the Security & Compliance Center to create Safe Attachments policies</span></span>

<span data-ttu-id="49bc8-142">Beim Erstellen einer benutzerdefinierten Richtlinie für sichere Anlagen im Security & Compliance Center werden die Regel für sichere Anlagen und die zugeordnete richtlinie für sichere Anlagen gleichzeitig mit demselben Namen für beide erstellt.</span><span class="sxs-lookup"><span data-stu-id="49bc8-142">Creating a custom Safe Attachments policy in the Security & Compliance Center creates the safe attachment rule and the associated safe attachment policy at the same time using the same name for both.</span></span>

1. <span data-ttu-id="49bc8-143">Wechseln Sie im Security & Compliance Center zu Richtlinie für die **Bedrohungsverwaltung** \>  \> **ATP Sichere Anlagen**.</span><span class="sxs-lookup"><span data-stu-id="49bc8-143">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Attachments**.</span></span>

2. <span data-ttu-id="49bc8-144">Klicken Sie **auf der** Seite Sichere Anlagen auf **Erstellen**.</span><span class="sxs-lookup"><span data-stu-id="49bc8-144">On the **Safe Attachments** page, click **Create**.</span></span>

3. <span data-ttu-id="49bc8-145">Der **Richtlinien-Assistent für neue sichere** Anlagen wird geöffnet.</span><span class="sxs-lookup"><span data-stu-id="49bc8-145">The **New Safe Attachments policy** wizard opens.</span></span> <span data-ttu-id="49bc8-146">Konfigurieren Sie **auf der Seite** Ihre Richtlinie benennen die folgenden Einstellungen:</span><span class="sxs-lookup"><span data-stu-id="49bc8-146">On the **Name your policy** page, configure the following settings:</span></span>

   - <span data-ttu-id="49bc8-147">**Name**: Geben Sie einen eindeutigen, aussagekräftigen Namen für die Richtlinie ein.</span><span class="sxs-lookup"><span data-stu-id="49bc8-147">**Name**: Enter a unique, descriptive name for the policy.</span></span>

   - <span data-ttu-id="49bc8-148">**Beschreibung**: Geben Sie eine optionale Beschreibung für die Richtlinie ein.</span><span class="sxs-lookup"><span data-stu-id="49bc8-148">**Description**: Enter an optional description for the policy.</span></span>

   <span data-ttu-id="49bc8-149">Klicken Sie nach Abschluss des Vorgangs auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="49bc8-149">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="49bc8-150">Konfigurieren Sie **auf** der angezeigten Seite Einstellungen die folgenden Einstellungen:</span><span class="sxs-lookup"><span data-stu-id="49bc8-150">On the **Settings** page that appears, configure the following settings:</span></span>

   - <span data-ttu-id="49bc8-151">**Sichere Anlagen unbekannte Schadsoftwareantwort:** Wählen Sie einen der folgenden Werte aus:</span><span class="sxs-lookup"><span data-stu-id="49bc8-151">**Safe Attachments unknown malware response**: Select one of the following values:</span></span>

     - <span data-ttu-id="49bc8-152">**Off**: In der Regel wird dieser Wert nicht empfohlen.</span><span class="sxs-lookup"><span data-stu-id="49bc8-152">**Off**: Typically, we don't recommend this value.</span></span>
     - <span data-ttu-id="49bc8-153">**Überwachen**</span><span class="sxs-lookup"><span data-stu-id="49bc8-153">**Monitor**</span></span>
     - <span data-ttu-id="49bc8-154">**Block**: Dies ist der Standardwert und der empfohlene Wert in standard und Strict [voreingestellte Sicherheitsrichtlinien](preset-security-policies.md).</span><span class="sxs-lookup"><span data-stu-id="49bc8-154">**Block**: This is the default value, and the recommended value in Standard and Strict [preset security policies](preset-security-policies.md).</span></span>
     - <span data-ttu-id="49bc8-155">**Replace**</span><span class="sxs-lookup"><span data-stu-id="49bc8-155">**Replace**</span></span>
     - <span data-ttu-id="49bc8-156">**Dynamische Übermittlung (Vorschaufeature)**</span><span class="sxs-lookup"><span data-stu-id="49bc8-156">**Dynamic Delivery (Preview Feature)**</span></span>

     <span data-ttu-id="49bc8-157">Diese Werte werden unter Richtlinieneinstellungen für sichere [Anlagen erläutert.](safe-attachments.md#safe-attachments-policy-settings)</span><span class="sxs-lookup"><span data-stu-id="49bc8-157">These values are explained in [Safe Attachments policy settings](safe-attachments.md#safe-attachments-policy-settings).</span></span>

   - <span data-ttu-id="49bc8-158">Senden Sie die Anlage an die folgende E-Mail-Adresse: Für  die Aktionswerte **Block,** **Monitor** oder **Replace** können Sie Umleitung aktivieren auswählen, um Nachrichten mit Schadsoftwareanlagen zur Analyse und Untersuchung an die angegebene interne oder externe E-Mail-Adresse zu senden. </span><span class="sxs-lookup"><span data-stu-id="49bc8-158">**Send the attachment to the following email address**: For the action values **Block**, **Monitor**, or **Replace**, you can select **Enable redirect** to send messages that contain malware attachments to the specified internal or external email address for analysis and investigation.</span></span>

     <span data-ttu-id="49bc8-159">Die Empfehlung für Standard- und Strict-Richtlinieneinstellungen besteht in der Aktivierung der Umleitung.</span><span class="sxs-lookup"><span data-stu-id="49bc8-159">The recommendation for Standard and Strict policy settings is to enable redirection.</span></span> <span data-ttu-id="49bc8-160">Weitere Informationen finden Sie unter [Einstellungen für sichere Anlagen](recommended-settings-for-eop-and-office365.md#safe-attachments-settings).</span><span class="sxs-lookup"><span data-stu-id="49bc8-160">For more information, see [Safe Attachments settings](recommended-settings-for-eop-and-office365.md#safe-attachments-settings).</span></span>

   - <span data-ttu-id="49bc8-161">**Wenden Sie die oben** aufgeführte Auswahl an, wenn die  Schadsoftwareprüfung auf Anlagen ein Zeit- oder Fehlerfehler auftritt: Die durch die unbekannte Schadsoftwareantwort für sichere Anlagen angegebene Aktion wird für Nachrichten ausgeführt, auch wenn die Überprüfung sicherer Anlagen nicht abgeschlossen werden kann.</span><span class="sxs-lookup"><span data-stu-id="49bc8-161">**Apply the above selection if malware scanning for attachments times out or error occurs**: The action specified by **Safe Attachments unknown malware response** is taken on messages even when Safe Attachments scanning can't complete.</span></span> <span data-ttu-id="49bc8-162">Wenn Sie diese Option ausgewählt haben, wählen Sie immer **Umleitung aktiviert aus.**</span><span class="sxs-lookup"><span data-stu-id="49bc8-162">If you selected this option, always select **Enabled redirect**.</span></span> <span data-ttu-id="49bc8-163">Andernfalls gehen Nachrichten möglicherweise verloren.</span><span class="sxs-lookup"><span data-stu-id="49bc8-163">Otherwise, messages might be lost.</span></span>

   <span data-ttu-id="49bc8-164">Klicken Sie nach Abschluss des Vorgangs auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="49bc8-164">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="49bc8-165">Identifizieren Sie **auf der angezeigten** Seite Angewendet auf die internen Empfänger, auf die die Richtlinie angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="49bc8-165">On the **Applied to** page that appears, identify the internal recipients that the policy applies to.</span></span>

   <span data-ttu-id="49bc8-166">Sie können eine Bedingung oder Ausnahme nur einmal verwenden, aber Sie können mehrere Werte für die Bedingung oder Ausnahme angeben.</span><span class="sxs-lookup"><span data-stu-id="49bc8-166">You can only use a condition or exception once, but you can specify multiple values for the condition or exception.</span></span> <span data-ttu-id="49bc8-167">Bei mehreren Werten derselben Bedingung oder Ausnahme wird ODER-Logik verwendet (z. B. _\<recipient1\>_ oder _\<recipient2\>_).</span><span class="sxs-lookup"><span data-stu-id="49bc8-167">Multiple values of the same condition or exception use OR logic (for example, _\<recipient1\>_ or _\<recipient2\>_).</span></span> <span data-ttu-id="49bc8-168">Bei unterschiedlichen Bedingungen oder Ausnahmen wird UND-Logik verwendet (z. B. _\<recipient1\>_ und _\<member of group 1\>_).</span><span class="sxs-lookup"><span data-stu-id="49bc8-168">Different conditions or exceptions use AND logic (for example, _\<recipient1\>_ and _\<member of group 1\>_).</span></span>

   <span data-ttu-id="49bc8-169">Klicken **Sie auf Bedingung hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="49bc8-169">Click **Add a condition**.</span></span> <span data-ttu-id="49bc8-170">Wählen Sie in der angezeigten Dropdownliste unter Angewendet eine **Bedingung aus, wenn**:</span><span class="sxs-lookup"><span data-stu-id="49bc8-170">In the dropdown that appears, select a condition under **Applied if**:</span></span>

   - <span data-ttu-id="49bc8-171">**Der Empfänger ist**: Gibt ein oder mehrere Postfächer, E-Mail-Benutzer oder E-Mail-Kontakte in Ihrer Organisation an.</span><span class="sxs-lookup"><span data-stu-id="49bc8-171">**The recipient is**: Specifies one or more mailboxes, mail users, or mail contacts in your organization.</span></span>
   - <span data-ttu-id="49bc8-172">**Der Empfänger ist Mitglied von**: Gibt eine oder mehrere Gruppen in Ihrer Organisation an.</span><span class="sxs-lookup"><span data-stu-id="49bc8-172">**The recipient is a member of**: Specifies one or more groups in your organization.</span></span>
   - <span data-ttu-id="49bc8-173">**Die Empfängerdomäne ist**: Gibt Empfänger in einer oder mehreren der konfigurierten akzeptierten Domänen in Ihrer Organisation an.</span><span class="sxs-lookup"><span data-stu-id="49bc8-173">**The recipient domain is**: Specifies recipients in one or more of the configured accepted domains in your organization.</span></span>

   <span data-ttu-id="49bc8-174">Nachdem Sie die Bedingung ausgewählt haben, wird ein entsprechendes Dropdownfeld mit einem **Beliebigen dieser Kontrollkästchen** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="49bc8-174">After you select the condition, a corresponding dropdown appears with an **Any of these** box.</span></span>

   - <span data-ttu-id="49bc8-175">Klicken Sie in das Feld, und scrollen Sie durch die Liste der auszuwählende Werte.</span><span class="sxs-lookup"><span data-stu-id="49bc8-175">Click in the box and scroll through the list of values to select.</span></span>
   - <span data-ttu-id="49bc8-176">Klicken Sie in das Feld, und beginnen Sie mit der Eingabe, um die Liste zu filtern und einen Wert auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="49bc8-176">Click in the box and start typing to filter the list and select a value.</span></span>
   - <span data-ttu-id="49bc8-177">Klicken Sie auf einen leeren Bereich im Feld, um weitere Werte hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="49bc8-177">To add additional values, click in an empty area in the box.</span></span>
   - <span data-ttu-id="49bc8-178">Klicken Sie zum Entfernen einzelner Einträge **auf Entfernen** ![ ](../../media/scc-remove-icon.png) (Symbol) für den Wert.</span><span class="sxs-lookup"><span data-stu-id="49bc8-178">To remove individual entries, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the value.</span></span>
   - <span data-ttu-id="49bc8-179">Klicken Sie zum Entfernen der gesamten Bedingung auf **Entfernen** ![ ](../../media/scc-remove-icon.png) (Symbol) für die Bedingung.</span><span class="sxs-lookup"><span data-stu-id="49bc8-179">To remove the whole condition, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the condition.</span></span>

   <span data-ttu-id="49bc8-180">Klicken Sie zum Hinzufügen einer zusätzlichen Bedingung auf **Bedingung hinzufügen,** und wählen Sie einen verbleibenden Wert unter **Angewendet wenn aus.**</span><span class="sxs-lookup"><span data-stu-id="49bc8-180">To add an additional condition, click **Add a condition** and select a remaining value under **Applied if**.</span></span>

   <span data-ttu-id="49bc8-181">Klicken Sie zum Hinzufügen von Ausnahmen auf **Bedingung hinzufügen,** und wählen Sie unter **Except if eine Ausnahme aus.**</span><span class="sxs-lookup"><span data-stu-id="49bc8-181">To add exceptions, click **Add a condition** and select an exception under **Except if**.</span></span> <span data-ttu-id="49bc8-182">Die Einstellungen und das Verhalten entsprechen genau den Bedingungen.</span><span class="sxs-lookup"><span data-stu-id="49bc8-182">The settings and behavior are exactly like the conditions.</span></span>

   <span data-ttu-id="49bc8-183">Klicken Sie nach Abschluss des Vorgangs auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="49bc8-183">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="49bc8-184">Überprüfen Sie **auf der angezeigten** Seite Einstellungen überprüfen Ihre Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="49bc8-184">On the **Review your settings** page that appears, review your settings.</span></span> <span data-ttu-id="49bc8-185">Sie können **für** jede Einstellung auf Bearbeiten klicken, um sie zu ändern.</span><span class="sxs-lookup"><span data-stu-id="49bc8-185">You can click **Edit** on each setting to modify it.</span></span>

   <span data-ttu-id="49bc8-186">Klicken Sie nach Abschluss des Vorgangs auf **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="49bc8-186">When you're finished, click **Finish**.</span></span>

## <a name="use-the-security--compliance-center-to-view-safe-attachments-policies"></a><span data-ttu-id="49bc8-187">Verwenden des Security & Compliance Center zum Anzeigen von Richtlinien für sichere Anlagen</span><span class="sxs-lookup"><span data-stu-id="49bc8-187">Use the Security & Compliance Center to view Safe Attachments policies</span></span>

1. <span data-ttu-id="49bc8-188">Wechseln Sie im Security & Compliance Center zu Richtlinie für die **Bedrohungsverwaltung** \>  \> **ATP Sichere Anlagen**.</span><span class="sxs-lookup"><span data-stu-id="49bc8-188">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Attachments**.</span></span>

2. <span data-ttu-id="49bc8-189">Wählen Sie **auf** der Seite Sichere Anlagen eine Richtlinie aus der Liste aus, und klicken Sie darauf (aktivieren Sie nicht das Kontrollkästchen).</span><span class="sxs-lookup"><span data-stu-id="49bc8-189">On the **Safe Attachments** page, select a policy from the list and click on it (don't select the check box).</span></span>

   <span data-ttu-id="49bc8-190">Die Richtliniendetails werden in einem Fly-Out angezeigt.</span><span class="sxs-lookup"><span data-stu-id="49bc8-190">The policy details appear in a fly out</span></span>

## <a name="use-the-security--compliance-center-to-modify-safe-attachments-policies"></a><span data-ttu-id="49bc8-191">Verwenden des Security & Compliance Center zum Ändern von Richtlinien für sichere Anlagen</span><span class="sxs-lookup"><span data-stu-id="49bc8-191">Use the Security & Compliance Center to modify Safe Attachments policies</span></span>

1. <span data-ttu-id="49bc8-192">Wechseln Sie im Security & Compliance Center zu Richtlinie für die **Bedrohungsverwaltung** \>  \> **ATP Sichere Anlagen**.</span><span class="sxs-lookup"><span data-stu-id="49bc8-192">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Attachments**.</span></span>

2. <span data-ttu-id="49bc8-193">Wählen Sie **auf** der Seite Sichere Anlagen eine Richtlinie aus der Liste aus, und klicken Sie darauf (aktivieren Sie nicht das Kontrollkästchen).</span><span class="sxs-lookup"><span data-stu-id="49bc8-193">On the **Safe Attachments** page, select a policy from the list and click on it (don't select the check box).</span></span>

3. <span data-ttu-id="49bc8-194">Klicken Sie in den angezeigten Richtliniendetails auf **Richtlinie bearbeiten.**</span><span class="sxs-lookup"><span data-stu-id="49bc8-194">In the policy details fly out that appears, click **Edit policy**.</span></span>

<span data-ttu-id="49bc8-195">Die verfügbaren Einstellungen im fly-out, die angezeigt werden, sind mit denen identisch, die im Abschnitt Verwenden des Security [& Compliance Center](#use-the-security--compliance-center-to-create-safe-attachments-policies) zum Erstellen von Richtlinien für sichere Anlagen beschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="49bc8-195">The available settings in the fly out that appears are identical to those described in the [Use the Security & Compliance Center to create Safe Attachments policies](#use-the-security--compliance-center-to-create-safe-attachments-policies) section.</span></span>

<span data-ttu-id="49bc8-196">Informationen zum Aktivieren oder Deaktivieren einer Richtlinie oder zum Festlegen der Richtlinienprioritätsreihenfolge finden Sie in den folgenden Abschnitten.</span><span class="sxs-lookup"><span data-stu-id="49bc8-196">To enable or disable a policy or set the policy priority order, see the following sections.</span></span>

### <a name="enable-or-disable-safe-attachments-policies"></a><span data-ttu-id="49bc8-197">Aktivieren oder Deaktivieren von Richtlinien für sichere Anlagen</span><span class="sxs-lookup"><span data-stu-id="49bc8-197">Enable or disable Safe Attachments policies</span></span>

1. <span data-ttu-id="49bc8-198">Wechseln Sie im Security & Compliance Center zu Richtlinie für die **Bedrohungsverwaltung** \>  \> **ATP Sichere Anlagen**.</span><span class="sxs-lookup"><span data-stu-id="49bc8-198">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Attachments**.</span></span>

2. <span data-ttu-id="49bc8-199">Beachten Sie den Wert in der **Spalte Status:**</span><span class="sxs-lookup"><span data-stu-id="49bc8-199">Notice the value in the **Status** column:</span></span>

   - <span data-ttu-id="49bc8-200">Verschieben des Umschalters nach links</span><span class="sxs-lookup"><span data-stu-id="49bc8-200">Move the toggle to the left</span></span> ![Deaktivieren der Richtlinie](../../media/scc-toggle-off.png) <span data-ttu-id="49bc8-202">, um die Richtlinie zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="49bc8-202">to disable the policy.</span></span>

   - <span data-ttu-id="49bc8-203">Verschieben des Umschalters nach rechts</span><span class="sxs-lookup"><span data-stu-id="49bc8-203">Move the toggle to the right</span></span> ![Aktivieren der Richtlinie](../../media/scc-toggle-on.png) <span data-ttu-id="49bc8-205">, um die Richtlinie zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="49bc8-205">to enable the policy.</span></span>

### <a name="set-the-priority-of-safe-attachments-policies"></a><span data-ttu-id="49bc8-206">Festlegen der Priorität von Richtlinien für sichere Anlagen</span><span class="sxs-lookup"><span data-stu-id="49bc8-206">Set the priority of Safe Attachments policies</span></span>

<span data-ttu-id="49bc8-207">Standardmäßig erhalten Richtlinien für sichere Anlagen eine Priorität, die auf der Reihenfolge basiert, in der sie erstellt wurden (neuere Richtlinien haben niedrigere Priorität als ältere Richtlinien).</span><span class="sxs-lookup"><span data-stu-id="49bc8-207">By default, Safe Attachments policies are given a priority that's based on the order they were created in (newer polices are lower priority than older policies).</span></span> <span data-ttu-id="49bc8-208">Eine niedrigere Prioritätsnummer gibt eine höhere Priorität für die Richtlinie an (0 ist die höchste), und Richtlinien werden in der Reihenfolge der Priorität verarbeitet (Richtlinien mit einer höheren Priorität werden vor Richtlinien mit einer niedrigeren Priorität verarbeitet).</span><span class="sxs-lookup"><span data-stu-id="49bc8-208">A lower priority number indicates a higher priority for the policy (0 is the highest), and policies are processed in priority order (higher priority policies are processed before lower priority policies).</span></span> <span data-ttu-id="49bc8-209">Keine zwei Richtlinien können die gleiche Priorität aufweisen, und die Richtlinienverarbeitung endet, nachdem die erste Richtlinie angewendet wurde.</span><span class="sxs-lookup"><span data-stu-id="49bc8-209">No two policies can have the same priority, and policy processing stops after the first policy is applied.</span></span>

<span data-ttu-id="49bc8-210">Weitere Informationen über die Prioritätsreihenfolge und darüber, wie mehrere Richtlinien ausgewertet und angewendet werden, finden Sie unter [Reihenfolge und Priorität beim E-Mail-Schutz](how-policies-and-protections-are-combined.md).</span><span class="sxs-lookup"><span data-stu-id="49bc8-210">For more information about the order of precedence and how multiple policies are evaluated and applied, see [Order and precedence of email protection](how-policies-and-protections-are-combined.md).</span></span>

<span data-ttu-id="49bc8-211">Richtlinien für sichere Anlagen werden in der Reihenfolge angezeigt, in der sie verarbeitet werden (die erste Richtlinie hat den **Prioritätswert** 0).</span><span class="sxs-lookup"><span data-stu-id="49bc8-211">Safe Attachments policies are displayed in the order they're processed (the first policy has the **Priority** value 0).</span></span>

<span data-ttu-id="49bc8-212">**Hinweis:** Im Security & Compliance Center können Sie die Priorität der Richtlinie für sichere Anlagen nur ändern, nachdem Sie sie erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="49bc8-212">**Note**: In the Security & Compliance Center, you can only change the priority of the Safe Attachments policy after you create it.</span></span> <span data-ttu-id="49bc8-213">In PowerShell können Sie die Standardpriorität überschreiben, wenn Sie die Regel für sichere Anlagen erstellen (was sich auf die Priorität vorhandener Regeln auswirken kann).</span><span class="sxs-lookup"><span data-stu-id="49bc8-213">In PowerShell, you can override the default priority when you create the safe attachment rule (which can affect the priority of existing rules).</span></span>

<span data-ttu-id="49bc8-214">Zum Ändern der Priorität einer Richtlinie verschieben Sie die Richtlinie in der Liste nach oben oder unten (Sie können den **Priorität**-Wert im Security & Compliance Center nicht direkt ändern).</span><span class="sxs-lookup"><span data-stu-id="49bc8-214">To change the priority of a policy, move the policy up or down in the list (you can't directly modify the **Priority** number in the Security & Compliance Center).</span></span>

1. <span data-ttu-id="49bc8-215">Wechseln Sie im Security & Compliance Center zu Richtlinie für die **Bedrohungsverwaltung** \>  \> **ATP Sichere Anlagen**.</span><span class="sxs-lookup"><span data-stu-id="49bc8-215">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Attachments**.</span></span>

2. <span data-ttu-id="49bc8-216">Wählen Sie **auf** der Seite Sichere Anlagen eine Richtlinie aus der Liste aus, und klicken Sie darauf (aktivieren Sie nicht das Kontrollkästchen).</span><span class="sxs-lookup"><span data-stu-id="49bc8-216">On the **Safe Attachments** page, select a policy from the list and click on it (don't select the check box).</span></span>

3. <span data-ttu-id="49bc8-217">Klicken Sie in den angezeigten Richtliniendetails auf die Schaltfläche verfügbare Priorität.</span><span class="sxs-lookup"><span data-stu-id="49bc8-217">In the policy details fly out that appears, click the available priority button.</span></span>

   - <span data-ttu-id="49bc8-218">Die Richtlinie Für sichere Anlagen mit dem **Prioritätswert** **0** ist nur die Schaltfläche Priorität **verringern** verfügbar.</span><span class="sxs-lookup"><span data-stu-id="49bc8-218">The Safe Attachments policy with the **Priority** value **0** has only the **Decrease priority** button available.</span></span>

   - <span data-ttu-id="49bc8-219">Die Richtlinie für sichere Anlagen mit dem niedrigsten **Prioritätswert** (z. B. **3**) verfügt nur über die **Schaltfläche Priorität erhöhen.**</span><span class="sxs-lookup"><span data-stu-id="49bc8-219">The Safe Attachments policy with the lowest **Priority** value (for example, **3**) has only the **Increase priority** button available.</span></span>

   - <span data-ttu-id="49bc8-220">Wenn Sie über drei oder mehr Richtlinien für sichere Anlagen verfügen, stehen Richtlinien zwischen den höchsten und niedrigsten Prioritätswerten sowohl die Schaltflächen **Priorität** erhöhen als auch **Priorität verringern** zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="49bc8-220">If you have three or more Safe Attachments policies, policies between the highest and lowest priority values have both the **Increase priority** and **Decrease priority** buttons available.</span></span>

4. <span data-ttu-id="49bc8-221">Klicken **Sie auf Priorität erhöhen** oder Priorität **verringern,** um den **Prioritätswert zu** ändern.</span><span class="sxs-lookup"><span data-stu-id="49bc8-221">Click **Increase priority** or **Decrease priority** to change the **Priority** value.</span></span>

5. <span data-ttu-id="49bc8-222">Klicken Sie nach Abschluss des Vorgangs auf **Schließen**.</span><span class="sxs-lookup"><span data-stu-id="49bc8-222">When you're finished, click **Close**.</span></span>

## <a name="use-the-security--compliance-center-to-remove-safe-attachments-policies"></a><span data-ttu-id="49bc8-223">Verwenden des Security & Compliance Center zum Entfernen von Richtlinien für sichere Anlagen</span><span class="sxs-lookup"><span data-stu-id="49bc8-223">Use the Security & Compliance Center to remove Safe Attachments policies</span></span>

1. <span data-ttu-id="49bc8-224">Wechseln Sie im Security & Compliance Center zu Richtlinie für die **Bedrohungsverwaltung** \>  \> **ATP Sichere Anlagen**.</span><span class="sxs-lookup"><span data-stu-id="49bc8-224">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Attachments**.</span></span>

2. <span data-ttu-id="49bc8-225">Wählen Sie **auf** der Seite Sichere Anlagen eine Richtlinie aus der Liste aus, und klicken Sie darauf (aktivieren Sie nicht das Kontrollkästchen).</span><span class="sxs-lookup"><span data-stu-id="49bc8-225">On the **Safe Attachments** page, select a policy from the list and click on it (don't select the check box).</span></span>

3. <span data-ttu-id="49bc8-226">Klicken Sie in den angezeigten Richtliniendetails auf Richtlinie **löschen,** und klicken Sie **dann** im angezeigten Warndialogfeld auf Ja.</span><span class="sxs-lookup"><span data-stu-id="49bc8-226">In the policy details fly out that appears, click **Delete policy**, and then click **Yes** in the warning dialog that appears.</span></span>

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-attachments-policies"></a><span data-ttu-id="49bc8-227">Konfigurieren von Richtlinien für sichere Anlagen mithilfe von Exchange Online PowerShell oder eigenständiger EOP PowerShell</span><span class="sxs-lookup"><span data-stu-id="49bc8-227">Use Exchange Online PowerShell or standalone EOP PowerShell to configure Safe Attachments policies</span></span>

<span data-ttu-id="49bc8-228">Wie bereits beschrieben, besteht eine Richtlinie für sichere Anlagen aus einer sicheren Anlagenrichtlinie und einer sicheren Anlagenregel.</span><span class="sxs-lookup"><span data-stu-id="49bc8-228">As previously described, a Safe Attachments policy consists of a safe attachment policy and a safe attachment rule.</span></span>

<span data-ttu-id="49bc8-229">In PowerShell ist der Unterschied zwischen sicheren Anlagenrichtlinien und regeln für sichere Anlagen offensichtlich.</span><span class="sxs-lookup"><span data-stu-id="49bc8-229">In PowerShell, the difference between safe attachment policies and safe attachment rules is apparent.</span></span> <span data-ttu-id="49bc8-230">Sie verwalten sichere Anlagenrichtlinien mithilfe der **\* -SafeAttachmentPolicy-Cmdlets,** und Sie verwalten sichere Anlagenregeln mithilfe der **\* -SafeAttachmentRule-Cmdlets.**</span><span class="sxs-lookup"><span data-stu-id="49bc8-230">You manage safe attachment policies by using the **\*-SafeAttachmentPolicy** cmdlets, and you manage safe attachment rules by using the **\*-SafeAttachmentRule** cmdlets.</span></span>

- <span data-ttu-id="49bc8-231">In PowerShell erstellen Sie zuerst die Richtlinie für sichere Anlagen und dann die Regel für sichere Anlagen, die die Richtlinie identifiziert, auf die die Regel angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="49bc8-231">In PowerShell, you create the safe attachment policy first, then you create the safe attachment rule that identifies the policy that the rule applies to.</span></span>
- <span data-ttu-id="49bc8-232">In PowerShell ändern Sie die Einstellungen in der Richtlinie für sichere Anlagen und die Regel für sichere Anlagen separat.</span><span class="sxs-lookup"><span data-stu-id="49bc8-232">In PowerShell, you modify the settings in the safe attachment policy and the safe attachment rule separately.</span></span>
- <span data-ttu-id="49bc8-233">Wenn Sie eine richtlinie für sichere Anlagen aus PowerShell entfernen, wird die entsprechende Regel für sichere Anlagen nicht automatisch entfernt und umgekehrt.</span><span class="sxs-lookup"><span data-stu-id="49bc8-233">When you remove a safe attachment policy from PowerShell, the corresponding safe attachment rule isn't automatically removed, and vice versa.</span></span>

### <a name="use-powershell-to-create-safe-attachments-policies"></a><span data-ttu-id="49bc8-234">Erstellen von Richtlinien für sichere Anlagen mithilfe von PowerShell</span><span class="sxs-lookup"><span data-stu-id="49bc8-234">Use PowerShell to create Safe Attachments policies</span></span>

<span data-ttu-id="49bc8-235">Das Erstellen einer Richtlinie für sichere Anlagen in PowerShell besteht aus zwei Stufen:</span><span class="sxs-lookup"><span data-stu-id="49bc8-235">Creating a Safe Attachments policy in PowerShell is a two-step process:</span></span>

1. <span data-ttu-id="49bc8-236">Erstellen Sie die Richtlinie für sichere Anlagen.</span><span class="sxs-lookup"><span data-stu-id="49bc8-236">Create the safe attachment policy.</span></span>
2. <span data-ttu-id="49bc8-237">Erstellen Sie die Regel für sichere Anlagen, die die richtlinie für sichere Anlagen angibt, auf die die Regel angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="49bc8-237">Create the safe attachment rule that specifies the safe attachment policy that the rule applies to.</span></span>

 <span data-ttu-id="49bc8-238">**Hinweise**:</span><span class="sxs-lookup"><span data-stu-id="49bc8-238">**Notes**:</span></span>

- <span data-ttu-id="49bc8-239">Sie können eine neue Regel für sichere Anlagen erstellen und ihr eine vorhandene, nicht zugeordnete richtlinie für sichere Anlagen zuweisen.</span><span class="sxs-lookup"><span data-stu-id="49bc8-239">You can create a new safe attachment rule and assign an existing, unassociated safe attachment policy to it.</span></span> <span data-ttu-id="49bc8-240">Eine sichere Anlagenregel kann nicht mehr als einer sicheren Anlagenrichtlinie zugeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="49bc8-240">A safe attachment rule can't be associated with more than one safe attachment policy.</span></span>

- <span data-ttu-id="49bc8-241">Sie können die folgenden Einstellungen für neue Richtlinien für sichere Anlagen in PowerShell konfigurieren, die im Security & Compliance Center erst nach dem Erstellen der Richtlinie verfügbar sind:</span><span class="sxs-lookup"><span data-stu-id="49bc8-241">You can configure the following settings on new safe attachment policies in PowerShell that aren't available in the Security & Compliance Center until after you create the policy:</span></span>
  - <span data-ttu-id="49bc8-242">Erstellen Sie die neue Richtlinie als deaktiviert (_Aktiviert_ `$false` im Cmdlet **New-SafeAttachmentRule).**</span><span class="sxs-lookup"><span data-stu-id="49bc8-242">Create the new policy as disabled (_Enabled_ `$false` on the **New-SafeAttachmentRule** cmdlet).</span></span>
  - <span data-ttu-id="49bc8-243">Legen Sie die Priorität der Richtlinie während der Erstellung (_Priorität_ _\<Number\>_ ) im Cmdlet **New-SafeAttachmentRule.**</span><span class="sxs-lookup"><span data-stu-id="49bc8-243">Set the priority of the policy during creation (_Priority_ _\<Number\>_) on the **New-SafeAttachmentRule** cmdlet).</span></span>

- <span data-ttu-id="49bc8-244">Eine neue richtlinie für sichere Anlagen, die Sie in PowerShell erstellen, wird erst im Security & Compliance Center angezeigt, wenn Sie die Richtlinie einer Regel für sichere Anlagen zuweisen.</span><span class="sxs-lookup"><span data-stu-id="49bc8-244">A new safe attachment policy that you create in PowerShell isn't visible in the Security & Compliance Center until you assign the policy to a safe attachment rule.</span></span>

#### <a name="step-1-use-powershell-to-create-a-safe-attachment-policy"></a><span data-ttu-id="49bc8-245">Schritt 1: Erstellen einer sicheren Anlagenrichtlinie mithilfe von PowerShell</span><span class="sxs-lookup"><span data-stu-id="49bc8-245">Step 1: Use PowerShell to create a safe attachment policy</span></span>

<span data-ttu-id="49bc8-246">Verwenden Sie die folgende Syntax, um eine sichere Anlagenrichtlinie zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="49bc8-246">To create a safe attachment policy, use this syntax:</span></span>

```PowerShell
New-SafeAttachmentPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] [-Action <Allow | Block | Replace | DynamicDelivery>] [-Redirect <$true | $false>] [-RedirectAddress <SMTPEmailAddress>] [-ActionOnError <$true | $false>]
```

<span data-ttu-id="49bc8-247">In diesem Beispiel wird eine sichere Anlagenrichtlinie namens Contoso All mit den folgenden Werten erstellt:</span><span class="sxs-lookup"><span data-stu-id="49bc8-247">This example creates a safe attachment policy named Contoso All with the following values:</span></span>

- <span data-ttu-id="49bc8-248">Blockieren von Nachrichten, die bei der Überprüfung sicherer Dokumente Schadsoftware enthalten (wir verwenden den _Action-Parameter_ nicht, und der Standardwert ist `Block` ).</span><span class="sxs-lookup"><span data-stu-id="49bc8-248">Block messages that are found to contain malware by Safe Documents scanning (we aren't using the _Action_ parameter, and the default value is `Block`).</span></span>
- <span data-ttu-id="49bc8-249">Die Umleitung ist aktiviert, und Nachrichten, die Schadsoftware enthalten, werden an sec-ops@contoso.com Analyse und Untersuchung gesendet.</span><span class="sxs-lookup"><span data-stu-id="49bc8-249">Redirection is enabled, and messages that are found to contain malware are sent to sec-ops@contoso.com for analysis and investigation.</span></span>
- <span data-ttu-id="49bc8-250">Wenn die Überprüfung sicherer Anlagen nicht verfügbar ist oder Fehler auftreten, senden Sie die Nachricht nicht (wir verwenden den _ActionOnError-Parameter_ nicht, und der Standardwert ist `$true` ).</span><span class="sxs-lookup"><span data-stu-id="49bc8-250">If Safe Attachments scanning isn't available or encounters errors, don't deliver the message (we aren't using the _ActionOnError_ parameter, and the default value is `$true`).</span></span>

```PowerShell
New-SafeAttachmentPolicy -Name "Contoso All" -Redirect $true -RedirectAddress sec-ops@contoso.com
```

<span data-ttu-id="49bc8-251">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [New-SafeAttachmentPolicy](/powershell/module/exchange/new-safeattachmentpolicy).</span><span class="sxs-lookup"><span data-stu-id="49bc8-251">For detailed syntax and parameter information, see [New-SafeAttachmentPolicy](/powershell/module/exchange/new-safeattachmentpolicy).</span></span>

#### <a name="step-2-use-powershell-to-create-a-safe-attachment-rule"></a><span data-ttu-id="49bc8-252">Schritt 2: Erstellen einer sicheren Anlagenregel mithilfe von PowerShell</span><span class="sxs-lookup"><span data-stu-id="49bc8-252">Step 2: Use PowerShell to create a safe attachment rule</span></span>

<span data-ttu-id="49bc8-253">Verwenden Sie die folgende Syntax, um eine sichere Anlagenregel zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="49bc8-253">To create a safe attachment rule, use this syntax:</span></span>

```PowerShell
New-SafeAttachmentRule -Name "<RuleName>" -SafeAttachmentPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"] [-Enabled <$true | $false>]
```

<span data-ttu-id="49bc8-254">In diesem Beispiel wird eine sichere Anlagenregel namens Contoso All mit den folgenden Bedingungen erstellt:</span><span class="sxs-lookup"><span data-stu-id="49bc8-254">This example creates a safe attachment rule named Contoso All with the following conditions:</span></span>

- <span data-ttu-id="49bc8-255">Die Regel ist der Richtlinie für sichere Anlagen namens Contoso All zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="49bc8-255">The rule is associated with the safe attachment policy named Contoso All.</span></span>
- <span data-ttu-id="49bc8-256">Die Regel gilt für alle Empfänger in der contoso.com Domäne.</span><span class="sxs-lookup"><span data-stu-id="49bc8-256">The rule applies to all recipients in the contoso.com domain.</span></span>
- <span data-ttu-id="49bc8-257">Da wir den Parameter _Priority_ nicht verwenden, wird die Standardpriorität verwendet.</span><span class="sxs-lookup"><span data-stu-id="49bc8-257">Because we aren't using the _Priority_ parameter, the default priority is used.</span></span>
- <span data-ttu-id="49bc8-258">Die Regel ist aktiviert (der Parameter _Enabled_ wird nicht verwendet, und der Standardwert ist `$true` ).</span><span class="sxs-lookup"><span data-stu-id="49bc8-258">The rule is enabled (we aren't using the _Enabled_ parameter, and the default value is `$true`).</span></span>

```powershell
New-SafeAttachmentRule -Name "Contoso All" -SafeAttachmentPolicy "Contoso All" -RecipientDomainIs contoso.com
```

<span data-ttu-id="49bc8-259">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [New-SafeAttachmentRule](/powershell/module/exchange/new-safeattachmentrule).</span><span class="sxs-lookup"><span data-stu-id="49bc8-259">For detailed syntax and parameter information, see [New-SafeAttachmentRule](/powershell/module/exchange/new-safeattachmentrule).</span></span>

### <a name="use-powershell-to-view-safe-attachment-policies"></a><span data-ttu-id="49bc8-260">Anzeigen sicherer Anlagenrichtlinien mithilfe von PowerShell</span><span class="sxs-lookup"><span data-stu-id="49bc8-260">Use PowerShell to view safe attachment policies</span></span>

<span data-ttu-id="49bc8-261">Verwenden Sie die folgende Syntax, um vorhandene Richtlinien für sichere Anlagen anzeigen zu können:</span><span class="sxs-lookup"><span data-stu-id="49bc8-261">To view existing safe attachment policies, use the following syntax:</span></span>

```PowerShell
Get-SafeAttachmentPolicy [-Identity "<PolicyIdentity>"] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="49bc8-262">In diesem Beispiel wird eine Zusammenfassungsliste aller Richtlinien für sichere Anlagen zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="49bc8-262">This example returns a summary list of all safe attachment policies.</span></span>

```PowerShell
Get-SafeAttachmentPolicy
```

<span data-ttu-id="49bc8-263">In diesem Beispiel werden detaillierte Informationen für die Richtlinie für sichere Anlagen namens Contoso Executives zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="49bc8-263">This example returns detailed information for the safe attachment policy named Contoso Executives.</span></span>

```PowerShell
Get-SafeAttachmentPolicy -Identity "Contoso Executives" | Format-List
```

<span data-ttu-id="49bc8-264">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Get-SafeAttachmentPolicy](/powershell/module/exchange/get-safeattachmentpolicy).</span><span class="sxs-lookup"><span data-stu-id="49bc8-264">For detailed syntax and parameter information, see [Get-SafeAttachmentPolicy](/powershell/module/exchange/get-safeattachmentpolicy).</span></span>

### <a name="use-powershell-to-view-safe-attachment-rules"></a><span data-ttu-id="49bc8-265">Anzeigen sicherer Anlagenregeln mithilfe von PowerShell</span><span class="sxs-lookup"><span data-stu-id="49bc8-265">Use PowerShell to view safe attachment rules</span></span>

<span data-ttu-id="49bc8-266">Verwenden Sie die folgende Syntax, um vorhandene regeln für sichere Anlagen anzeigen zu können:</span><span class="sxs-lookup"><span data-stu-id="49bc8-266">To view existing safe attachment rules, use the following syntax:</span></span>

```PowerShell
Get-SafeAttachmentRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled>] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="49bc8-267">In diesem Beispiel wird eine Zusammenfassungsliste aller regeln für sichere Anlagen zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="49bc8-267">This example returns a summary list of all safe attachment rules.</span></span>

```PowerShell
Get-SafeAttachmentRule
```

<span data-ttu-id="49bc8-268">Führen Sie die folgenden Befehle aus, um die Liste nach aktivierten oder deaktivierten Regeln zu filtern:</span><span class="sxs-lookup"><span data-stu-id="49bc8-268">To filter the list by enabled or disabled rules, run the following commands:</span></span>

```PowerShell
Get-SafeAttachmentRule -State Disabled
```

```PowerShell
Get-SafeAttachmentRule -State Enabled
```

<span data-ttu-id="49bc8-269">In diesem Beispiel werden detaillierte Informationen für die Regel für sichere Anlagen namens Contoso Executives zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="49bc8-269">This example returns detailed information for the safe attachment rule named Contoso Executives.</span></span>

```PowerShell
Get-SafeAttachmentRule -Identity "Contoso Executives" | Format-List
```

<span data-ttu-id="49bc8-270">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Get-SafeAttachmentRule](/powershell/module/exchange/get-safeattachmentrule).</span><span class="sxs-lookup"><span data-stu-id="49bc8-270">For detailed syntax and parameter information, see [Get-SafeAttachmentRule](/powershell/module/exchange/get-safeattachmentrule).</span></span>

### <a name="use-powershell-to-modify-safe-attachment-policies"></a><span data-ttu-id="49bc8-271">Verwenden von PowerShell zum Ändern sicherer Anlagenrichtlinien</span><span class="sxs-lookup"><span data-stu-id="49bc8-271">Use PowerShell to modify safe attachment policies</span></span>

<span data-ttu-id="49bc8-272">Sie können eine sichere Anlagenrichtlinie in PowerShell nicht umbenennen (das **Cmdlet Set-SafeAttachmentPolicy** hat keinen _Name-Parameter)._</span><span class="sxs-lookup"><span data-stu-id="49bc8-272">You can't rename a safe attachment policy in PowerShell (the **Set-SafeAttachmentPolicy** cmdlet has no _Name_ parameter).</span></span> <span data-ttu-id="49bc8-273">Wenn Sie eine Richtlinie für sichere Anlagen im Security & Compliance Center umbenennen, benennen Sie nur die Regel für sichere Anlagen _um._</span><span class="sxs-lookup"><span data-stu-id="49bc8-273">When you rename a Safe Attachments policy in the Security & Compliance Center, you're only renaming the safe attachment _rule_.</span></span>

<span data-ttu-id="49bc8-274">Andernfalls sind dieselben Einstellungen verfügbar, wenn Sie eine sichere Anlagenrichtlinie erstellen, wie im Abschnitt [Schritt 1:](#step-1-use-powershell-to-create-a-safe-attachment-policy) Verwenden von PowerShell beschrieben, um eine sichere Anlagenrichtlinie weiter oben in diesem Artikel zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="49bc8-274">Otherwise, the same settings are available when you create a safe attachment policy as described in the [Step 1: Use PowerShell to create a safe attachment policy](#step-1-use-powershell-to-create-a-safe-attachment-policy) section earlier in this article.</span></span>

<span data-ttu-id="49bc8-275">Verwenden Sie die folgende Syntax, um eine richtlinie für sichere Anlagen zu ändern:</span><span class="sxs-lookup"><span data-stu-id="49bc8-275">To modify a safe attachment policy, use this syntax:</span></span>

```PowerShell
Set-SafeAttachmentPolicy -Identity "<PolicyName>" <Settings>
```

<span data-ttu-id="49bc8-276">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Set-SafeAttachmentPolicy](/powershell/module/exchange/set-safeattachmentpolicy).</span><span class="sxs-lookup"><span data-stu-id="49bc8-276">For detailed syntax and parameter information, see [Set-SafeAttachmentPolicy](/powershell/module/exchange/set-safeattachmentpolicy).</span></span>

### <a name="use-powershell-to-modify-safe-attachment-rules"></a><span data-ttu-id="49bc8-277">Verwenden von PowerShell zum Ändern sicherer Anlagenregeln</span><span class="sxs-lookup"><span data-stu-id="49bc8-277">Use PowerShell to modify safe attachment rules</span></span>

<span data-ttu-id="49bc8-278">Die einzige Einstellung, die nicht verfügbar ist, wenn Sie eine sichere Anlagenregel in PowerShell ändern, ist der _Parameter Enabled,_ mit dem Sie eine deaktivierte Regel erstellen können.</span><span class="sxs-lookup"><span data-stu-id="49bc8-278">The only setting that's not available when you modify a safe attachment rule in PowerShell is the _Enabled_ parameter that allows you to create a disabled rule.</span></span> <span data-ttu-id="49bc8-279">Informationen zum Aktivieren oder Deaktivieren vorhandener Regeln für sichere Anlagen finden Sie im nächsten Abschnitt.</span><span class="sxs-lookup"><span data-stu-id="49bc8-279">To enable or disable existing safe attachment rules, see the next section.</span></span>

<span data-ttu-id="49bc8-280">Andernfalls sind dieselben Einstellungen verfügbar, wenn Sie eine Regel wie im Abschnitt [Schritt 2:](#step-2-use-powershell-to-create-a-safe-attachment-rule) Verwenden von PowerShell beschrieben erstellen, um eine sichere Anlagenregel weiter oben in diesem Artikel zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="49bc8-280">Otherwise, the same settings are available when you create a rule as described in the [Step 2: Use PowerShell to create a safe attachment rule](#step-2-use-powershell-to-create-a-safe-attachment-rule) section earlier in this article.</span></span>

<span data-ttu-id="49bc8-281">Verwenden Sie die folgende Syntax, um eine sichere Anlagenregel zu ändern:</span><span class="sxs-lookup"><span data-stu-id="49bc8-281">To modify a safe attachment rule, use this syntax:</span></span>

```PowerShell
Set-SafeAttachmentRule -Identity "<RuleName>" <Settings>
```

<span data-ttu-id="49bc8-282">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Set-SafeAttachmentRule](/powershell/module/exchange/set-safeattachmentrule).</span><span class="sxs-lookup"><span data-stu-id="49bc8-282">For detailed syntax and parameter information, see [Set-SafeAttachmentRule](/powershell/module/exchange/set-safeattachmentrule).</span></span>

### <a name="use-powershell-to-enable-or-disable-safe-attachment-rules"></a><span data-ttu-id="49bc8-283">Aktivieren oder Deaktivieren sicherer Anlagenregeln mithilfe von PowerShell</span><span class="sxs-lookup"><span data-stu-id="49bc8-283">Use PowerShell to enable or disable safe attachment rules</span></span>

<span data-ttu-id="49bc8-284">Durch Aktivieren oder Deaktivieren einer Regel für sichere Anlagen in PowerShell wird die gesamte Richtlinie für sichere Anlagen (die Regel für sichere Anlagen und die zugewiesene Richtlinie für sichere Anlagen) aktiviert oder deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="49bc8-284">Enabling or disabling a safe attachment rule in PowerShell enables or disables the whole Safe Attachments policy (the safe attachment rule and the assigned safe attachment policy).</span></span>

<span data-ttu-id="49bc8-285">Verwenden Sie die folgende Syntax, um eine sichere Anlagenregel in PowerShell zu aktivieren oder zu deaktivieren:</span><span class="sxs-lookup"><span data-stu-id="49bc8-285">To enable or disable a safe attachment rule in PowerShell, use this syntax:</span></span>

```PowerShell
<Enable-SafeAttachmentRule | Disable-SafeAttachmentRule> -Identity "<RuleName>"
```

<span data-ttu-id="49bc8-286">In diesem Beispiel wird die Regel für sichere Anlagen mit dem Namen Marketing Department deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="49bc8-286">This example disables the safe attachment rule named Marketing Department.</span></span>

```PowerShell
Disable-SafeAttachmentRule -Identity "Marketing Department"
```

<span data-ttu-id="49bc8-287">In diesem Beispiel wird dieselbe Regel aktiviert.</span><span class="sxs-lookup"><span data-stu-id="49bc8-287">This example enables same rule.</span></span>

```PowerShell
Enable-SafeAttachmentRule -Identity "Marketing Department"
```

<span data-ttu-id="49bc8-288">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Enable-SafeAttachmentRule](/powershell/module/exchange/enable-safeattachmentrule) und [Disable-SafeAttachmentRule](/powershell/module/exchange/disable-safeattachmentrule).</span><span class="sxs-lookup"><span data-stu-id="49bc8-288">For detailed syntax and parameter information, see [Enable-SafeAttachmentRule](/powershell/module/exchange/enable-safeattachmentrule) and [Disable-SafeAttachmentRule](/powershell/module/exchange/disable-safeattachmentrule).</span></span>

### <a name="use-powershell-to-set-the-priority-of-safe-attachment-rules"></a><span data-ttu-id="49bc8-289">Festlegen der Priorität sicherer Anlagenregeln mithilfe von PowerShell</span><span class="sxs-lookup"><span data-stu-id="49bc8-289">Use PowerShell to set the priority of safe attachment rules</span></span>

<span data-ttu-id="49bc8-290">Der höchste Prioritätswert, den Sie für eine Regel festlegen können, ist 0.</span><span class="sxs-lookup"><span data-stu-id="49bc8-290">The highest priority value you can set on a rule is 0.</span></span> <span data-ttu-id="49bc8-291">Der niedrigste Wert, den Sie festlegen können, hängt von der Anzahl von Regeln ab.</span><span class="sxs-lookup"><span data-stu-id="49bc8-291">The lowest value you can set depends on the number of rules.</span></span> <span data-ttu-id="49bc8-292">Wenn Sie z. B. fünf Regeln haben, können Sie die Prioritätswerte 0 bis 4 verwenden.</span><span class="sxs-lookup"><span data-stu-id="49bc8-292">For example, if you have five rules, you can use the priority values 0 through 4.</span></span> <span data-ttu-id="49bc8-293">Das Ändern der Priorität einer vorhandenen Regel kann sich entsprechend auf andere Regeln auswirken.</span><span class="sxs-lookup"><span data-stu-id="49bc8-293">Changing the priority of an existing rule can have a cascading effect on other rules.</span></span> <span data-ttu-id="49bc8-294">Wenn Sie z. B. fünf benutzerdefinierte Regeln haben (Priorität 0 bis 4) und die Priorität einer Regel in 2 ändern, erhält die vorhandene Regel mit Priorität 2 die Priorität 3, und die Regel mit Priorität 3 erhält Priorität 4.</span><span class="sxs-lookup"><span data-stu-id="49bc8-294">For example, if you have five custom rules (priorities 0 through 4), and you change the priority of a rule to 2, the existing rule with priority 2 is changed to priority 3, and the rule with priority 3 is changed to priority 4.</span></span>

<span data-ttu-id="49bc8-295">Verwenden Sie die folgende Syntax, um die Priorität einer sicheren Anlagenregel in PowerShell zu setzen:</span><span class="sxs-lookup"><span data-stu-id="49bc8-295">To set the priority of a safe attachment rule in PowerShell, use the following syntax:</span></span>

```PowerShell
Set-SafeAttachmentRule -Identity "<RuleName>" -Priority <Number>
```

<span data-ttu-id="49bc8-p124">In diesem Beispiel wird die Priorität der Regel namens „Marketing Department“ auf 2 festgelegt. Alle vorhandenen Regeln mit Priorität kleiner oder gleich 2 werden um 1 verringert (die Prioritätswerte werden um 1 erhöht).</span><span class="sxs-lookup"><span data-stu-id="49bc8-p124">This example sets the priority of the rule named Marketing Department to 2. All existing rules that have a priority less than or equal to 2 are decreased by 1 (their priority numbers are increased by 1).</span></span>

```PowerShell
Set-SafeAttachmentRule -Identity "Marketing Department" -Priority 2
```

<span data-ttu-id="49bc8-298">**Hinweis**: Verwenden Sie zum Festlegen der Priorität einer neuen Regel beim Erstellen stattdessen den _Parameter Priority_ im Cmdlet **New-SafeAttachmentRule.**</span><span class="sxs-lookup"><span data-stu-id="49bc8-298">**Note**: To set the priority of a new rule when you create it, use the _Priority_ parameter on the **New-SafeAttachmentRule** cmdlet instead.</span></span>

<span data-ttu-id="49bc8-299">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Set-SafeAttachmentRule](/powershell/module/exchange/set-safeattachmentrule).</span><span class="sxs-lookup"><span data-stu-id="49bc8-299">For detailed syntax and parameter information, see [Set-SafeAttachmentRule](/powershell/module/exchange/set-safeattachmentrule).</span></span>

### <a name="use-powershell-to-remove-safe-attachment-policies"></a><span data-ttu-id="49bc8-300">Verwenden von PowerShell zum Entfernen sicherer Anlagenrichtlinien</span><span class="sxs-lookup"><span data-stu-id="49bc8-300">Use PowerShell to remove safe attachment policies</span></span>

<span data-ttu-id="49bc8-301">Wenn Sie PowerShell verwenden, um eine sichere Anlagenrichtlinie zu entfernen, wird die entsprechende Regel für sichere Anlagen nicht entfernt.</span><span class="sxs-lookup"><span data-stu-id="49bc8-301">When you use PowerShell to remove a safe attachment policy, the corresponding safe attachment rule isn't removed.</span></span>

<span data-ttu-id="49bc8-302">Verwenden Sie die folgende Syntax, um eine sichere Anlagenrichtlinie in PowerShell zu entfernen:</span><span class="sxs-lookup"><span data-stu-id="49bc8-302">To remove a safe attachment policy in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-SafeAttachmentPolicy -Identity "<PolicyName>"
```

<span data-ttu-id="49bc8-303">In diesem Beispiel wird die Richtlinie für sichere Anlagen mit dem Namen Marketing Department entfernt.</span><span class="sxs-lookup"><span data-stu-id="49bc8-303">This example removes the safe attachment policy named Marketing Department.</span></span>

```PowerShell
Remove-SafeAttachmentPolicy -Identity "Marketing Department"
```

<span data-ttu-id="49bc8-304">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Remove-SafeAttachmentPolicy](/powershell/module/exchange/remove-safeattachmentpolicy).</span><span class="sxs-lookup"><span data-stu-id="49bc8-304">For detailed syntax and parameter information, see [Remove-SafeAttachmentPolicy](/powershell/module/exchange/remove-safeattachmentpolicy).</span></span>

### <a name="use-powershell-to-remove-safe-attachment-rules"></a><span data-ttu-id="49bc8-305">Verwenden von PowerShell zum Entfernen sicherer Anlagenregeln</span><span class="sxs-lookup"><span data-stu-id="49bc8-305">Use PowerShell to remove safe attachment rules</span></span>

<span data-ttu-id="49bc8-306">Wenn Sie PowerShell verwenden, um eine sichere Anlagenregel zu entfernen, wird die entsprechende Richtlinie für sichere Anlagen nicht entfernt.</span><span class="sxs-lookup"><span data-stu-id="49bc8-306">When you use PowerShell to remove a safe attachment rule, the corresponding safe attachment policy isn't removed.</span></span>

<span data-ttu-id="49bc8-307">Verwenden Sie die folgende Syntax, um eine sichere Anlagenregel in PowerShell zu entfernen:</span><span class="sxs-lookup"><span data-stu-id="49bc8-307">To remove a safe attachment rule in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-SafeAttachmentRule -Identity "<PolicyName>"
```

<span data-ttu-id="49bc8-308">In diesem Beispiel wird die Regel für sichere Anlagen mit dem Namen Marketing Department entfernt.</span><span class="sxs-lookup"><span data-stu-id="49bc8-308">This example removes the safe attachment rule named Marketing Department.</span></span>

```PowerShell
Remove-SafeAttachmentRule -Identity "Marketing Department"
```

<span data-ttu-id="49bc8-309">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Remove-SafeAttachmentRule](/powershell/module/exchange/remove-safeattachmentrule).</span><span class="sxs-lookup"><span data-stu-id="49bc8-309">For detailed syntax and parameter information, see [Remove-SafeAttachmentRule](/powershell/module/exchange/remove-safeattachmentrule).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="49bc8-310">Wie können Sie feststellen, dass diese Verfahren erfolgreich waren?</span><span class="sxs-lookup"><span data-stu-id="49bc8-310">How do you know these procedures worked?</span></span>

<span data-ttu-id="49bc8-311">Gehen Sie wie folgt vor, um zu überprüfen, ob Richtlinien für sichere Anlagen erfolgreich erstellt, geändert oder entfernt wurden:</span><span class="sxs-lookup"><span data-stu-id="49bc8-311">To verify that you've successfully created, modified, or removed Safe Attachments policies, do any of the following steps:</span></span>

- <span data-ttu-id="49bc8-312">Wechseln Sie im Security & Compliance Center zu Richtlinie für die **Bedrohungsverwaltung** \>  \> **ATP Sichere Anlagen**.</span><span class="sxs-lookup"><span data-stu-id="49bc8-312">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Attachments**.</span></span> <span data-ttu-id="49bc8-313">Überprüfen Sie die Liste der Richtlinien, ihre **Statuswerte** und ihre **Priority-Werte.**</span><span class="sxs-lookup"><span data-stu-id="49bc8-313">Verify the list of policies, their **Status** values, and their **Priority** values.</span></span> <span data-ttu-id="49bc8-314">Um weitere Details anzuzeigen, wählen Sie die Richtlinie aus der Liste aus, und zeigen Sie die Details im Fly-Out an.</span><span class="sxs-lookup"><span data-stu-id="49bc8-314">To view more details, select the policy from the list, and view the details in the fly out.</span></span>

- <span data-ttu-id="49bc8-315">Ersetzen Sie in Exchange Online PowerShell oder Exchange Online Protection PowerShell durch den Namen der Richtlinie oder Regel, führen Sie den folgenden Befehl aus, und überprüfen Sie \<Name\> die Einstellungen:</span><span class="sxs-lookup"><span data-stu-id="49bc8-315">In Exchange Online PowerShell or Exchange Online Protection PowerShell, replace \<Name\> with the name of the policy or rule, run the following command, and verify the settings:</span></span>

  ```PowerShell
  Get-SafeAttachmentPolicy -Identity "<Name>" | Format-List
  ```

  ```PowerShell
  Get-SafeAttachmentRule -Identity "<Name>" | Format-List
  ```

<span data-ttu-id="49bc8-316">Überprüfen Sie die verfügbaren Defender for Office 365-Berichte, um zu überprüfen, ob nachrichtensichere Anlagen überprüft werden.</span><span class="sxs-lookup"><span data-stu-id="49bc8-316">To verify that Safe Attachments is scanning messages, check the available Defender for Office 365 reports.</span></span> <span data-ttu-id="49bc8-317">Weitere Informationen finden Sie unter Anzeigen von Berichten [für Defender für Office 365](view-reports-for-mdo.md) und Verwenden von Explorer im Security & Compliance [Center](threat-explorer.md).</span><span class="sxs-lookup"><span data-stu-id="49bc8-317">For more information, see [View reports for Defender for Office 365](view-reports-for-mdo.md) and [Use Explorer in the Security & Compliance Center](threat-explorer.md).</span></span>
