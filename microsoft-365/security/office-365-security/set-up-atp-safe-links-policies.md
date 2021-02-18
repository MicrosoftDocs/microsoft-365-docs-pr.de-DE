---
title: Einrichten von Richtlinien für sichere Links in Microsoft Defender für Office 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.topic: how-to
ms.date: ''
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: bdd5372d-775e-4442-9c1b-609627b94b5d
ms.collection:
- M365-security-compliance
description: Administratoren können erfahren, wie Sie Richtlinien für sichere Links und globale Einstellungen für sichere Links in Microsoft Defender für Office 365 anzeigen, erstellen, ändern und löschen.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 29d777a7f351b9ab33232cb0136703ce3fa29842
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/18/2021
ms.locfileid: "50290153"
---
# <a name="set-up-safe-links-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="87a94-103">Einrichten von Richtlinien für sichere Links in Microsoft Defender für Office 365</span><span class="sxs-lookup"><span data-stu-id="87a94-103">Set up Safe Links policies in Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="87a94-104">**Gilt für**</span><span class="sxs-lookup"><span data-stu-id="87a94-104">**Applies to**</span></span>
- [<span data-ttu-id="87a94-105">Microsoft Defender für Office 365 Plan 1 und Plan 2</span><span class="sxs-lookup"><span data-stu-id="87a94-105">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="87a94-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="87a94-106">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

> [!IMPORTANT]
> <span data-ttu-id="87a94-107">Dieser Artikel richtet sich an Geschäftskunden, die über [Microsoft Defender für Office 365](office-365-atp.md) verfügen.</span><span class="sxs-lookup"><span data-stu-id="87a94-107">This article is intended for business customers who have [Microsoft Defender for Office 365](office-365-atp.md).</span></span> <span data-ttu-id="87a94-108">Informationen zu Safelinks in Outlook finden Sie unter Advanced [Outlook.com Security](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).</span><span class="sxs-lookup"><span data-stu-id="87a94-108">If you are a home user looking for information about Safelinks in Outlook, see [Advanced Outlook.com security](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).</span></span>

<span data-ttu-id="87a94-109">Sichere Links ist ein Feature in [Microsoft Defender für Office 365,](office-365-atp.md) das die URL-Überprüfung eingehender E-Mail-Nachrichten im Nachrichtenfluss sowie die Zeit der Klicküberprüfung von URLs und Links in E-Mail-Nachrichten und an anderen Speicherorten bietet.</span><span class="sxs-lookup"><span data-stu-id="87a94-109">Safe Links is a feature in [Microsoft Defender for Office 365](office-365-atp.md) that provides URL scanning of inbound email messages in mail flow, and time of click verification of URLs and links in email messages and in other locations.</span></span> <span data-ttu-id="87a94-110">Weitere Informationen finden Sie unter ["Sichere Links" in Microsoft Defender für Office 365.](atp-safe-links.md)</span><span class="sxs-lookup"><span data-stu-id="87a94-110">For more information, see [Safe Links in Microsoft Defender for Office 365](atp-safe-links.md).</span></span>

<span data-ttu-id="87a94-111">Es gibt keine integrierte oder standardmäßige Richtlinie für sichere Links.</span><span class="sxs-lookup"><span data-stu-id="87a94-111">There's no built-in or default Safe Links policy.</span></span> <span data-ttu-id="87a94-112">Um die Überprüfung von URLs auf sichere Links zu erhalten, müssen Sie eine oder mehrere Richtlinien für sichere Links erstellen, wie in diesem Artikel beschrieben.</span><span class="sxs-lookup"><span data-stu-id="87a94-112">To get Safe Links scanning of URLs, you need to create one or more Safe Links policies as described in this article.</span></span>

> [!NOTE]
> <span data-ttu-id="87a94-113">Sie konfigurieren die globalen Einstellungen für den Schutz sicherer Links **außerhalb** von Richtlinien für sichere Links.</span><span class="sxs-lookup"><span data-stu-id="87a94-113">You configure the global settings for Safe Links protection **outside** of Safe Links policies.</span></span> <span data-ttu-id="87a94-114">Anweisungen finden Sie unter ["Konfigurieren globaler Einstellungen für sichere Links in Microsoft Defender für Office 365".](configure-global-settings-for-safe-links.md)</span><span class="sxs-lookup"><span data-stu-id="87a94-114">For instructions, see [Configure global settings for Safe Links in Microsoft Defender for Office 365](configure-global-settings-for-safe-links.md).</span></span>

<span data-ttu-id="87a94-115">Sie können Richtlinien für sichere Links im Security & Compliance Center oder in PowerShell konfigurieren (Exchange Online PowerShell für berechtigte Microsoft 365-Organisationen mit Postfächern in Exchange Online; eigenständige EOP PowerShell für Organisationen ohne Exchange Online-Postfächer, aber mit Microsoft Defender für Office 365-Add-On-Abonnements).</span><span class="sxs-lookup"><span data-stu-id="87a94-115">You can configure Safe Links policies in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for eligible Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes, but with Microsoft Defender for Office 365 add-on subscriptions).</span></span>

<span data-ttu-id="87a94-116">Die grundlegenden Elemente einer Richtlinie für sichere Links sind:</span><span class="sxs-lookup"><span data-stu-id="87a94-116">The basic elements of a Safe Links policy are:</span></span>

- <span data-ttu-id="87a94-117">Die Richtlinie für sichere **Links:** Aktivieren Sie den Schutz sicherer Links, aktivieren Sie die URL-Überprüfung in Echtzeit, geben Sie an, ob die Überprüfung in Echtzeit abgeschlossen ist, bevor die Nachricht zu senden ist, aktivieren Sie die Überprüfung auf interne Nachrichten, geben Sie an, ob Benutzerklicks auf URLs nachverfolgt werden sollen, und geben Sie an, ob Benutzer auf die ursprüngliche URL klicken dürfen.</span><span class="sxs-lookup"><span data-stu-id="87a94-117">**The safe links policy**: Turn on Safe Links protection, turn on real-time URL scanning, specify whether to wait for real-time scanning to complete before delivering the message, turn on scanning for internal messages, specify whether to track user clicks on URLs, and specify whether to allow users to click trough to the original URL.</span></span>
- <span data-ttu-id="87a94-118">**Die Regel für sichere Links:** Gibt die Prioritäts- und Empfängerfilter an (für wen die Richtlinie gilt).</span><span class="sxs-lookup"><span data-stu-id="87a94-118">**The safe links rule**: Specifies the priority and recipient filters (who the policy applies to).</span></span>

<span data-ttu-id="87a94-119">Der Unterschied zwischen diesen beiden Elementen ist nicht offensichtlich, wenn Sie Richtlinien für sichere Links im Security & Compliance Center verwalten:</span><span class="sxs-lookup"><span data-stu-id="87a94-119">The difference between these two elements isn't obvious when you manage Safe Links polices in the Security & Compliance Center:</span></span>

- <span data-ttu-id="87a94-120">Wenn Sie eine Richtlinie für sichere Links erstellen, erstellen Sie tatsächlich eine Regel für sichere Links und die zugehörige Richtlinie für sichere Links gleichzeitig unter Verwendung desselben Namens für beide.</span><span class="sxs-lookup"><span data-stu-id="87a94-120">When you create a Safe Links policy, you're actually creating a safe links rule and the associated safe links policy at the same time using the same name for both.</span></span>
- <span data-ttu-id="87a94-121">Wenn Sie eine Richtlinie für sichere Links ändern, ändern Einstellungen im Zusammenhang mit Name, Priorität, aktiviert oder deaktiviert und Empfängerfilter die Regel für sichere Links.</span><span class="sxs-lookup"><span data-stu-id="87a94-121">When you modify a Safe Links policy, settings related to the name, priority, enabled or disabled, and recipient filters modify the safe links rule.</span></span> <span data-ttu-id="87a94-122">Alle anderen Einstellungen ändern die zugeordnete Richtlinie für sichere Links.</span><span class="sxs-lookup"><span data-stu-id="87a94-122">All other settings modify the associated safe links policy.</span></span>
- <span data-ttu-id="87a94-123">Wenn Sie eine Richtlinie für sichere Links entfernen, werden die Regel für sichere Links und die zugehörige Richtlinie für sichere Links entfernt.</span><span class="sxs-lookup"><span data-stu-id="87a94-123">When you remove a Safe Links policy, the safe links rule and the associated safe links policy are removed.</span></span>

<span data-ttu-id="87a94-124">In Exchange Online PowerShell oder der eigenständigen EOP PowerShell verwalten Sie die Richtlinie und die Regel getrennt.</span><span class="sxs-lookup"><span data-stu-id="87a94-124">In Exchange Online PowerShell or standalone EOP PowerShell, you manage the policy and the rule separately.</span></span> <span data-ttu-id="87a94-125">Weitere Informationen finden Sie im Abschnitt "Verwenden von Exchange Online PowerShell oder der eigenständigen [EOP PowerShell](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-links-policies) zum Konfigurieren von Richtlinien für sichere Links" weiter unten in diesem Artikel.</span><span class="sxs-lookup"><span data-stu-id="87a94-125">For more information, see the [Use Exchange Online PowerShell or standalone EOP PowerShell to configure Safe Links policies](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-links-policies) section later in this article.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="87a94-126">Was sollten Sie wissen, bevor Sie beginnen?</span><span class="sxs-lookup"><span data-stu-id="87a94-126">What do you need to know before you begin?</span></span>

- <span data-ttu-id="87a94-127">Sie öffnen das Security & Compliance Center unter <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="87a94-127">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="87a94-128">Um direkt zur Seite "Sichere **Links" zu** gelangen, verwenden Sie <https://protection.office.com/safelinksv2> .</span><span class="sxs-lookup"><span data-stu-id="87a94-128">To go directly to the **Safe Links** page, use <https://protection.office.com/safelinksv2>.</span></span>

- <span data-ttu-id="87a94-129">Wie Sie eine Verbindung mit Exchange Online PowerShell herstellen, finden Sie unter [Herstellen einer Verbindung mit Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="87a94-129">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="87a94-130">Informationen zum Herstellen einer Verbindung mit dem eigenständigen Exchange Online Protection PowerShell finden Sie unter [Verbinden mit PowerShell in Exchange Online Protection](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="87a94-130">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="87a94-131">Bevor Sie die Verfahren in diesem Artikel tun können, müssen Ihnen die entsprechenden Berechtigungen zugewiesen werden:</span><span class="sxs-lookup"><span data-stu-id="87a94-131">You need to be assigned permissions before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="87a94-132">Zum Erstellen, Ändern und Löschen von Richtlinien für sichere  Links müssen  Sie Mitglied der Rollengruppe "Organisationsverwaltung" oder "Sicherheitsadministrator" im Security & Compliance **Center** und Mitglied der Rollengruppe "Organisationsverwaltung" in Exchange Online sein. </span><span class="sxs-lookup"><span data-stu-id="87a94-132">To create, modify, and delete Safe Links policies, you need to be a member of the **Organization Management** or **Security Administrator** role groups in the Security & Compliance Center **and** a member of the **Organization Management** role group in Exchange Online.</span></span>
  - <span data-ttu-id="87a94-133">Für den schreibgeschützten Zugriff auf Richtlinien für sichere  Links müssen Sie Mitglied der Rollengruppe "Globaler Leser" oder **"Sicherheitsleser"** sein.</span><span class="sxs-lookup"><span data-stu-id="87a94-133">For read-only access to Safe Links policies, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="87a94-134">Weitere Informationen finden Sie unter ["Berechtigungen" im Security & Compliance Center](permissions-in-the-security-and-compliance-center.md) und in Exchange [Online](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo).</span><span class="sxs-lookup"><span data-stu-id="87a94-134">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md) and [Permissions in Exchange Online](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo).</span></span>

  > [!NOTE]
  > 
  > - <span data-ttu-id="87a94-135">Durch das Hinzufügen von Benutzern zur entsprechenden Azure Active Directory-Rolle im Microsoft 365 Admin Center erhalten Benutzer die erforderlichen Berechtigungen im Security & Compliance Center _und_ Berechtigungen für andere Features in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="87a94-135">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Security & Compliance Center _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="87a94-136">Weitere Informationen finden Sie unter [Informationen zu Administratorrollen](../../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="87a94-136">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  <span data-ttu-id="87a94-137">.</span><span class="sxs-lookup"><span data-stu-id="87a94-137">.</span></span> <span data-ttu-id="87a94-138">- Die **Rollengruppe "Organisationsverwaltung** nur anzeigen" in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) ermöglicht auch den schreibgeschützten Zugriff auf das Feature.</span><span class="sxs-lookup"><span data-stu-id="87a94-138">- The **View-Only Organization Management** role group in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

- <span data-ttu-id="87a94-139">Die empfohlenen Einstellungen für Richtlinien für sichere Links finden Sie unter Richtlinieneinstellungen für [sichere Links.](recommended-settings-for-eop-and-office365-atp.md#safe-links-policy-settings)</span><span class="sxs-lookup"><span data-stu-id="87a94-139">For our recommended settings for Safe Links policies, see [Safe Links policy settings](recommended-settings-for-eop-and-office365-atp.md#safe-links-policy-settings).</span></span>

- <span data-ttu-id="87a94-140">Es kann bis zu 30 Minuten dauern, bis eine neue oder aktualisierte Richtlinie angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="87a94-140">Allow up to 30 minutes for a new or updated policy to be applied.</span></span>

- <span data-ttu-id="87a94-141">[Microsoft Defender für Office 365](office-365-atp.md#new-features-in-microsoft-defender-for-office-365)werden ständig neue Features hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="87a94-141">[New features are continually being added to Microsoft Defender for Office 365](office-365-atp.md#new-features-in-microsoft-defender-for-office-365).</span></span> <span data-ttu-id="87a94-142">Wenn neue Features hinzugefügt werden, müssen Sie möglicherweise Anpassungen an Ihren vorhandenen Richtlinien für sichere Links vornehmen.</span><span class="sxs-lookup"><span data-stu-id="87a94-142">As new features are added, you may need to make adjustments to your existing Safe Links policies.</span></span>

## <a name="use-the-security--compliance-center-to-create-safe-links-policies"></a><span data-ttu-id="87a94-143">Verwenden des Security & Compliance Center zum Erstellen von Richtlinien für sichere Links</span><span class="sxs-lookup"><span data-stu-id="87a94-143">Use the Security & Compliance Center to create Safe Links policies</span></span>

<span data-ttu-id="87a94-144">Beim Erstellen einer benutzerdefinierten Richtlinie für sichere Links im Security & Compliance Center werden die Regel für sichere Links und die zugehörige Richtlinie für sichere Links gleichzeitig mit demselben Namen für beide erstellt.</span><span class="sxs-lookup"><span data-stu-id="87a94-144">Creating a custom Safe Links policy in the Security & Compliance Center creates the safe links rule and the associated safe links policy at the same time using the same name for both.</span></span>

1. <span data-ttu-id="87a94-145">Wechseln Sie im Security & Compliance Center zu **"AtP-sichere** Links" zur Richtlinie zur \>  \> **Bedrohungsverwaltung.**</span><span class="sxs-lookup"><span data-stu-id="87a94-145">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Links**.</span></span>

2. <span data-ttu-id="87a94-146">Klicken Sie **auf der Seite "Sichere Links"** auf **"Erstellen".**</span><span class="sxs-lookup"><span data-stu-id="87a94-146">On the **Safe Links** page, click **Create**.</span></span>

3. <span data-ttu-id="87a94-147">Der **Assistent für neue Richtlinien für sichere** Links wird geöffnet.</span><span class="sxs-lookup"><span data-stu-id="87a94-147">The **New Safe Links policy** wizard opens.</span></span> <span data-ttu-id="87a94-148">Konfigurieren Sie **auf der Seite "Ihre Richtlinie benennen"** die folgenden Einstellungen:</span><span class="sxs-lookup"><span data-stu-id="87a94-148">On the **Name your policy** page, configure the following settings:</span></span>

   - <span data-ttu-id="87a94-149">**Name**: Geben Sie einen eindeutigen, aussagekräftigen Namen für die Richtlinie ein.</span><span class="sxs-lookup"><span data-stu-id="87a94-149">**Name**: Enter a unique, descriptive name for the policy.</span></span>

   - <span data-ttu-id="87a94-150">**Beschreibung**: Geben Sie eine optionale Beschreibung für die Richtlinie ein.</span><span class="sxs-lookup"><span data-stu-id="87a94-150">**Description**: Enter an optional description for the policy.</span></span>

   <span data-ttu-id="87a94-151">Klicken Sie nach Abschluss des Vorgangs auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="87a94-151">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="87a94-152">Konfigurieren Sie **auf** der angezeigten Seite "Einstellungen" die folgenden Einstellungen:</span><span class="sxs-lookup"><span data-stu-id="87a94-152">On the **Settings** page that appears, configure the following settings:</span></span>

   - <span data-ttu-id="87a94-153">**Wählen Sie die Aktion für unbekannte potenziell schädliche URLs in** Nachrichten aus: Aktivieren Sie **diese Option,** um den Schutz sicherer Links für Links in E-Mail-Nachrichten zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="87a94-153">**Select the action for unknown potentially malicious URLs in messages**: Select **On** to enable Safe Links protection for links in email messages.</span></span>

   - <span data-ttu-id="87a94-154">**Wählen Sie die Aktion für unbekannte oder potenziell** schädliche URLs in Microsoft Teams aus: Aktivieren Sie **diese** Option, um den Schutz sicherer Links für Links in Teams zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="87a94-154">**Select the action for unknown or potentially malicious URLs within Microsoft Teams**: Select **On** to enable Safe Links protection for links in Teams.</span></span>

   - <span data-ttu-id="87a94-155">**Anwenden der Echtzeit-URL-Überprüfung** auf verdächtige Links und Links, die auf Dateien verweisen: Wählen Sie diese Einstellung aus, um das Scannen von Links in E-Mail-Nachrichten in Echtzeit zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="87a94-155">**Apply real-time URL scanning for suspicious links and links that point to files**: Select this setting to enable real-time scanning of links in email messages.</span></span>

   - <span data-ttu-id="87a94-156">**Warten Sie, bis die URL-Überprüfung** abgeschlossen ist, bevor Sie die Nachricht zustellen: Wählen Sie diese Einstellung aus, um auf den Abschluss der Echtzeit-URL-Überprüfung zu warten, bevor Sie die Nachricht zustellen.</span><span class="sxs-lookup"><span data-stu-id="87a94-156">**Wait for URL scanning to complete before delivering the message**: Select this setting to wait for real-time URL scanning to complete before delivering the message.</span></span>

   - <span data-ttu-id="87a94-157">**Sichere Links auf** E-Mail-Nachrichten anwenden, die innerhalb der Organisation gesendet werden: Wählen Sie diese Einstellung aus, um die Richtlinie für sichere Links auf Nachrichten zwischen internen Absendern und internen Empfängern anzuwenden.</span><span class="sxs-lookup"><span data-stu-id="87a94-157">**Apply Safe Links to email messages sent within the organization**: Select this setting to apply the Safe Links policy to messages between internal senders and internal recipients.</span></span>

   - <span data-ttu-id="87a94-158">**Benutzerklicks nicht nachverfolgen:** Lassen Sie diese Einstellung deaktiviert, damit der Nachverfolgungsbenutzer auf URLs in E-Mail-Nachrichten klickt.</span><span class="sxs-lookup"><span data-stu-id="87a94-158">**Do not track user clicks**: Leave this setting unselected to enable the tracking user clicks on URLs in email messages.</span></span>

   - <span data-ttu-id="87a94-159">**Benutzer dürfen nicht zur** ursprünglichen URL klicken: Wählen Sie diese Einstellung aus, um zu blockieren, dass Benutzer auf Warnseiten auf die ursprüngliche URL [klicken.](atp-safe-links.md#warning-pages-from-safe-links)</span><span class="sxs-lookup"><span data-stu-id="87a94-159">**Do not allow users to click through to original URL**: Select this setting to block users from clicking through to the original URL in [warning pages](atp-safe-links.md#warning-pages-from-safe-links).</span></span>

   - <span data-ttu-id="87a94-160">**Schreiben Sie die folgenden URLs** nicht neu: Ermöglicht den Zugriff auf die angegebenen URLs, die andernfalls durch sichere Links blockiert würden.</span><span class="sxs-lookup"><span data-stu-id="87a94-160">**Do not rewrite the following URLs**: Allows access the specified URLs that would otherwise be blocked by Safe Links.</span></span>

     <span data-ttu-id="87a94-161">Geben Sie in das Feld die URL oder den Wert ein, die Sie verwenden möchten, und klicken Sie dann auf</span><span class="sxs-lookup"><span data-stu-id="87a94-161">In the box, type the URL or value that you want, and then click</span></span> ![Schaltflächensymbol hinzufügen](../../media/ITPro-EAC-AddIcon.png)<span data-ttu-id="87a94-163">.</span><span class="sxs-lookup"><span data-stu-id="87a94-163">.</span></span>

     <span data-ttu-id="87a94-164">Um einen vorhandenen Eintrag zu entfernen, wählen Sie ihn aus, und klicken Sie dann auf</span><span class="sxs-lookup"><span data-stu-id="87a94-164">To remove an existing entry, select it and then click</span></span> ![Schaltflächensymbol löschen](../../media/ITPro-EAC-DeleteIcon.png)<span data-ttu-id="87a94-166">.</span><span class="sxs-lookup"><span data-stu-id="87a94-166">.</span></span>

     <span data-ttu-id="87a94-167">Informationen zur Eintragssyntax finden Sie in der Eintragssyntax für die Liste ["Die folgenden URLs dürfen](atp-safe-links.md#entry-syntax-for-the-do-not-rewrite-the-following-urls-list)nicht neu geschrieben werden".</span><span class="sxs-lookup"><span data-stu-id="87a94-167">For entry syntax, see [Entry syntax for the "Do not rewrite the following URLs" list](atp-safe-links.md#entry-syntax-for-the-do-not-rewrite-the-following-urls-list).</span></span>

   <span data-ttu-id="87a94-168">Ausführliche Informationen zu diesen Einstellungen finden Sie unter Einstellungen für sichere [Links für](atp-safe-links.md#safe-links-settings-for-email-messages) E-Mail-Nachrichten und Einstellungen für sichere Links für [Microsoft Teams.](atp-safe-links.md#safe-links-settings-for-microsoft-teams)</span><span class="sxs-lookup"><span data-stu-id="87a94-168">For detailed information about these settings, see [Safe Links settings for email messages](atp-safe-links.md#safe-links-settings-for-email-messages) and [Safe Links settings for Microsoft Teams](atp-safe-links.md#safe-links-settings-for-microsoft-teams).</span></span>

   <span data-ttu-id="87a94-169">Weitere Informationen zu den empfohlenen Werten für Standard- und Strikte Richtlinieneinstellungen finden Sie unter Richtlinieneinstellungen für [sichere Links.](recommended-settings-for-eop-and-office365-atp.md#safe-links-policy-settings)</span><span class="sxs-lookup"><span data-stu-id="87a94-169">For more the recommended values for Standard and Strict policy settings, see [Safe Links policy settings](recommended-settings-for-eop-and-office365-atp.md#safe-links-policy-settings).</span></span>

   <span data-ttu-id="87a94-170">Klicken Sie nach Abschluss des Vorgangs auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="87a94-170">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="87a94-171">Identifizieren Sie **auf der angezeigten** Seite "Angewendet auf" die internen Empfänger, auf die die Richtlinie angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="87a94-171">On the **Applied to** page that appears, identify the internal recipients that the policy applies to.</span></span>

   <span data-ttu-id="87a94-172">Sie können eine Bedingung oder Ausnahme nur einmal verwenden, aber Sie können mehrere Werte für die Bedingung oder Ausnahme angeben.</span><span class="sxs-lookup"><span data-stu-id="87a94-172">You can only use a condition or exception once, but you can specify multiple values for the condition or exception.</span></span> <span data-ttu-id="87a94-173">Bei mehreren Werten derselben Bedingung oder Ausnahme wird ODER-Logik verwendet (z. B. _\<recipient1\>_ oder _\<recipient2\>_).</span><span class="sxs-lookup"><span data-stu-id="87a94-173">Multiple values of the same condition or exception use OR logic (for example, _\<recipient1\>_ or _\<recipient2\>_).</span></span> <span data-ttu-id="87a94-174">Bei unterschiedlichen Bedingungen oder Ausnahmen wird UND-Logik verwendet (z. B. _\<recipient1\>_ und _\<member of group 1\>_).</span><span class="sxs-lookup"><span data-stu-id="87a94-174">Different conditions or exceptions use AND logic (for example, _\<recipient1\>_ and _\<member of group 1\>_).</span></span>

   <span data-ttu-id="87a94-175">Klicken **Sie auf Bedingung hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="87a94-175">Click **Add a condition**.</span></span> <span data-ttu-id="87a94-176">Wählen Sie in der angezeigten Dropdownliste eine Bedingung unter **"Angewendet" aus, wenn:**</span><span class="sxs-lookup"><span data-stu-id="87a94-176">In the dropdown that appears, select a condition under **Applied if**:</span></span>

   - <span data-ttu-id="87a94-177">**Der Empfänger ist:** Gibt ein oder mehrere Postfächer, E-Mail-Benutzer oder E-Mail-Kontakte in Ihrer Organisation an.</span><span class="sxs-lookup"><span data-stu-id="87a94-177">**The recipient is**: Specifies one or more mailboxes, mail users, or mail contacts in your organization.</span></span>
   - <span data-ttu-id="87a94-178">**Der Empfänger ist Mitglied von**: Gibt eine oder mehrere Gruppen in Ihrer Organisation an.</span><span class="sxs-lookup"><span data-stu-id="87a94-178">**The recipient is a member of**: Specifies one or more groups in your organization.</span></span>
   - <span data-ttu-id="87a94-179">**Die Empfängerdomäne ist**: Gibt Empfänger in einer oder mehreren der konfigurierten akzeptierten Domänen in Ihrer Organisation an.</span><span class="sxs-lookup"><span data-stu-id="87a94-179">**The recipient domain is**: Specifies recipients in one or more of the configured accepted domains in your organization.</span></span>

   <span data-ttu-id="87a94-180">Nachdem Sie die Bedingung ausgewählt haben, wird eine entsprechende Dropdownliste mit einem **Beliebigen dieser Kontrollkästchen** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="87a94-180">After you select the condition, a corresponding dropdown appears with an **Any of these** box.</span></span>

   - <span data-ttu-id="87a94-181">Klicken Sie in das Feld, und führen Sie einen Bildlauf durch die Liste der werte aus.</span><span class="sxs-lookup"><span data-stu-id="87a94-181">Click in the box and scroll through the list of values to select.</span></span>
   - <span data-ttu-id="87a94-182">Klicken Sie in das Feld, und beginnen Sie mit der Eingabe, um die Liste zu filtern und einen Wert auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="87a94-182">Click in the box and start typing to filter the list and select a value.</span></span>
   - <span data-ttu-id="87a94-183">Wenn Sie weitere Werte hinzufügen möchten, klicken Sie in einen leeren Bereich des Felds.</span><span class="sxs-lookup"><span data-stu-id="87a94-183">To add additional values, click in an empty area in the box.</span></span>
   - <span data-ttu-id="87a94-184">Klicken Sie zum Entfernen einzelner Einträge **auf** das Symbol ![ ](../../media/scc-remove-icon.png) "Entfernen" für den Wert.</span><span class="sxs-lookup"><span data-stu-id="87a94-184">To remove individual entries, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the value.</span></span>
   - <span data-ttu-id="87a94-185">Um die gesamte Bedingung zu entfernen, **klicken** Sie in der Bedingung ![ auf ](../../media/scc-remove-icon.png) "Entfernen".</span><span class="sxs-lookup"><span data-stu-id="87a94-185">To remove the whole condition, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the condition.</span></span>

   <span data-ttu-id="87a94-186">Klicken Sie zum Hinzufügen einer zusätzlichen Bedingung auf "Bedingung **hinzufügen",** und wählen Sie unter "Angewendet" einen verbleibenden Wert **aus, wenn**.</span><span class="sxs-lookup"><span data-stu-id="87a94-186">To add an additional condition, click **Add a condition** and select a remaining value under **Applied if**.</span></span>

   <span data-ttu-id="87a94-187">Klicken Sie zum Hinzufügen von Ausnahmen auf **"Bedingung hinzufügen",** und wählen Sie unter "Außer wenn" **eine Ausnahme aus.**</span><span class="sxs-lookup"><span data-stu-id="87a94-187">To add exceptions, click **Add a condition** and select an exception under **Except if**.</span></span> <span data-ttu-id="87a94-188">Die Einstellungen und das Verhalten entsprechen genau den Bedingungen.</span><span class="sxs-lookup"><span data-stu-id="87a94-188">The settings and behavior are exactly like the conditions.</span></span>

   <span data-ttu-id="87a94-189">Klicken Sie nach Abschluss des Vorgangs auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="87a94-189">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="87a94-190">Überprüfen Sie **ihre Einstellungen auf** der angezeigten Seite "Einstellungen überprüfen".</span><span class="sxs-lookup"><span data-stu-id="87a94-190">On the **Review your settings** page that appears, review your settings.</span></span> <span data-ttu-id="87a94-191">Sie können **in** jeder Einstellung auf "Bearbeiten" klicken, um sie zu ändern.</span><span class="sxs-lookup"><span data-stu-id="87a94-191">You can click **Edit** on each setting to modify it.</span></span>

   <span data-ttu-id="87a94-192">Klicken Sie nach Abschluss des Vorgangs auf **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="87a94-192">When you're finished, click **Finish**.</span></span>

## <a name="use-the-security--compliance-center-to-view-safe-links-policies"></a><span data-ttu-id="87a94-193">Verwenden des Security & Compliance Center zum Anzeigen von Richtlinien für sichere Links</span><span class="sxs-lookup"><span data-stu-id="87a94-193">Use the Security & Compliance Center to view Safe Links policies</span></span>

1. <span data-ttu-id="87a94-194">Wechseln Sie im Security & Compliance Center zu **"AtP-sichere** Links" zur Richtlinie zur \>  \> **Bedrohungsverwaltung.**</span><span class="sxs-lookup"><span data-stu-id="87a94-194">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Links**.</span></span>

2. <span data-ttu-id="87a94-195">Wählen Sie **auf der Seite "Sichere** Links" eine Richtlinie aus der Liste aus, und klicken Sie darauf (aktivieren Sie nicht das Kontrollkästchen).</span><span class="sxs-lookup"><span data-stu-id="87a94-195">On the **Safe Links** page, select a policy from the list and click on it (don't select the check box).</span></span>

   <span data-ttu-id="87a94-196">Die Richtliniendetails werden in einem Flyout angezeigt.</span><span class="sxs-lookup"><span data-stu-id="87a94-196">The policy details appear in a fly out</span></span>

## <a name="use-the-security--compliance-center-to-modify-safe-links-policies"></a><span data-ttu-id="87a94-197">Verwenden des Security & Compliance Center zum Ändern von Richtlinien für sichere Links</span><span class="sxs-lookup"><span data-stu-id="87a94-197">Use the Security & Compliance Center to modify Safe Links policies</span></span>

1. <span data-ttu-id="87a94-198">Wechseln Sie im Security & Compliance Center zu **"AtP-sichere** Links" zur Richtlinie zur \>  \> **Bedrohungsverwaltung.**</span><span class="sxs-lookup"><span data-stu-id="87a94-198">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Links**.</span></span>

2. <span data-ttu-id="87a94-199">Wählen Sie auf der Seite **"Sichere** Links" eine Richtlinie aus der Liste aus, und klicken Sie darauf (aktivieren Sie nicht das Kontrollkästchen).</span><span class="sxs-lookup"><span data-stu-id="87a94-199">On the **Safe Links** page, select a policy from the list and click on it (don't select the check box).</span></span>

3. <span data-ttu-id="87a94-200">Klicken Sie in den angezeigten Richtliniendetails auf **"Richtlinie bearbeiten".**</span><span class="sxs-lookup"><span data-stu-id="87a94-200">In the policy details fly out that appears, click **Edit policy**.</span></span>

<span data-ttu-id="87a94-201">Die verfügbaren Einstellungen im angezeigten Flyout sind identisch mit den einstellungen, die im Abschnitt "Verwenden des Security & Compliance Center zum Erstellen von Richtlinien für sichere [Links" beschrieben](#use-the-security--compliance-center-to-create-safe-links-policies) sind.</span><span class="sxs-lookup"><span data-stu-id="87a94-201">The available settings in the fly out that appears are identical to those described in the [Use the Security & Compliance Center to create Safe Links policies](#use-the-security--compliance-center-to-create-safe-links-policies) section.</span></span>

<span data-ttu-id="87a94-202">Informationen zum Aktivieren oder Deaktivieren einer Richtlinie oder zum Festlegen der Prioritätsreihenfolge der Richtlinie finden Sie in den folgenden Abschnitten.</span><span class="sxs-lookup"><span data-stu-id="87a94-202">To enable or disable a policy or set the policy priority order, see the following sections.</span></span>

### <a name="enable-or-disable-safe-links-policies"></a><span data-ttu-id="87a94-203">Aktivieren oder Deaktivieren von Richtlinien für sichere Links</span><span class="sxs-lookup"><span data-stu-id="87a94-203">Enable or disable Safe Links policies</span></span>

1. <span data-ttu-id="87a94-204">Wechseln Sie im Security & Compliance Center zu **"AtP-sichere** Links" zur Richtlinie zur \>  \> **Bedrohungsverwaltung.**</span><span class="sxs-lookup"><span data-stu-id="87a94-204">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Links**.</span></span>

2. <span data-ttu-id="87a94-205">Beachten Sie den  Wert in der Statusspalte:</span><span class="sxs-lookup"><span data-stu-id="87a94-205">Notice the value in the **Status** column:</span></span>

   - <span data-ttu-id="87a94-206">Schieben Sie die Umschaltfläche nach links, um die Richtlinie zu deaktivieren:</span><span class="sxs-lookup"><span data-stu-id="87a94-206">Move the toggle to the left to disable the policy:</span></span> ![Richtlinie deaktivieren](../../media/scc-toggle-off.png)<span data-ttu-id="87a94-208">.</span><span class="sxs-lookup"><span data-stu-id="87a94-208">.</span></span>

   - <span data-ttu-id="87a94-209">Schieben Sie die Umschaltfläche nach rechts, um die Richtlinie zu aktivieren:</span><span class="sxs-lookup"><span data-stu-id="87a94-209">Move the toggle to the right to enable the policy:</span></span> ![Richtlinie aktivieren](../../media/scc-toggle-on.png)<span data-ttu-id="87a94-211">.</span><span class="sxs-lookup"><span data-stu-id="87a94-211">.</span></span>

### <a name="set-the-priority-of-safe-links-policies"></a><span data-ttu-id="87a94-212">Festlegen der Priorität von Richtlinien für sichere Links</span><span class="sxs-lookup"><span data-stu-id="87a94-212">Set the priority of Safe Links policies</span></span>

<span data-ttu-id="87a94-213">Standardmäßig erhalten Richtlinien für sichere Links eine Priorität, die auf der Reihenfolge basiert, in der sie erstellt wurden (neuere Richtlinien haben eine niedrigere Priorität als ältere Richtlinien).</span><span class="sxs-lookup"><span data-stu-id="87a94-213">By default, Safe Links policies are given a priority that's based on the order they were created in (newer polices are lower priority than older policies).</span></span> <span data-ttu-id="87a94-214">Eine niedrigere Prioritätsnummer gibt eine höhere Priorität für die Richtlinie an (0 ist die höchste), und Richtlinien werden in der Reihenfolge der Priorität verarbeitet (Richtlinien mit einer höheren Priorität werden vor Richtlinien mit einer niedrigeren Priorität verarbeitet).</span><span class="sxs-lookup"><span data-stu-id="87a94-214">A lower priority number indicates a higher priority for the policy (0 is the highest), and policies are processed in priority order (higher priority policies are processed before lower priority policies).</span></span> <span data-ttu-id="87a94-215">Keine zwei Richtlinien können die gleiche Priorität aufweisen, und die Richtlinienverarbeitung endet, nachdem die erste Richtlinie angewendet wurde.</span><span class="sxs-lookup"><span data-stu-id="87a94-215">No two policies can have the same priority, and policy processing stops after the first policy is applied.</span></span>

<span data-ttu-id="87a94-216">Weitere Informationen über die Prioritätsreihenfolge und darüber, wie mehrere Richtlinien ausgewertet und angewendet werden, finden Sie unter [Reihenfolge und Priorität beim E-Mail-Schutz](how-policies-and-protections-are-combined.md).</span><span class="sxs-lookup"><span data-stu-id="87a94-216">For more information about the order of precedence and how multiple policies are evaluated and applied, see [Order and precedence of email protection](how-policies-and-protections-are-combined.md).</span></span>

<span data-ttu-id="87a94-217">Richtlinien für sichere Links werden in der Reihenfolge angezeigt, in der sie verarbeitet werden (die erste Richtlinie hat den **Prioritätswert** 0).</span><span class="sxs-lookup"><span data-stu-id="87a94-217">Safe Links policies are displayed in the order they're processed (the first policy has the **Priority** value 0).</span></span>

> [!NOTE]
> <span data-ttu-id="87a94-218">Im Security & Compliance Center können Sie die Priorität der Richtlinie für sichere Links erst ändern, nachdem Sie sie erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="87a94-218">In the Security & Compliance Center, you can only change the priority of the Safe Links policy after you create it.</span></span> <span data-ttu-id="87a94-219">In PowerShell können Sie die Standardpriorität überschreiben, wenn Sie die Regel für sichere Links erstellen (die sich auf die Priorität vorhandener Regeln auswirken kann).</span><span class="sxs-lookup"><span data-stu-id="87a94-219">In PowerShell, you can override the default priority when you create the safe links rule (which can affect the priority of existing rules).</span></span>

<span data-ttu-id="87a94-220">Zum Ändern der Priorität einer Richtlinie verschieben Sie die Richtlinie in der Liste nach oben oder unten (Sie können den **Priorität**-Wert im Security & Compliance Center nicht direkt ändern).</span><span class="sxs-lookup"><span data-stu-id="87a94-220">To change the priority of a policy, move the policy up or down in the list (you can't directly modify the **Priority** number in the Security & Compliance Center).</span></span>

1. <span data-ttu-id="87a94-221">Wechseln Sie im Security & Compliance Center zu **"AtP-sichere** Links" zur Richtlinie zur \>  \> **Bedrohungsverwaltung.**</span><span class="sxs-lookup"><span data-stu-id="87a94-221">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Links**.</span></span>

2. <span data-ttu-id="87a94-222">Wählen Sie **auf der Seite "Sichere** Links" eine Richtlinie aus der Liste aus, und klicken Sie darauf (aktivieren Sie nicht das Kontrollkästchen).</span><span class="sxs-lookup"><span data-stu-id="87a94-222">On the **Safe Links** page, select a policy from the list and click on it (don't select the check box).</span></span>

3. <span data-ttu-id="87a94-223">Klicken Sie in den angezeigten Richtliniendetails auf die Schaltfläche "Verfügbare Priorität":</span><span class="sxs-lookup"><span data-stu-id="87a94-223">In the policy details fly out that appears, click the available priority button:</span></span>

   - <span data-ttu-id="87a94-224">Die Richtlinie für sichere Links mit dem **Prioritätswert** **0** verfügt nur über die Schaltfläche "Priorität **verringern".**</span><span class="sxs-lookup"><span data-stu-id="87a94-224">The Safe Links policy with the **Priority** value **0** has only the **Decrease priority** button available.</span></span>

   - <span data-ttu-id="87a94-225">Für die Richtlinie für sichere Links mit dem niedrigsten **Prioritätswert** (z. B. **3)** ist nur die Schaltfläche "Priorität **erhöhen"** verfügbar.</span><span class="sxs-lookup"><span data-stu-id="87a94-225">The Safe Links policy with the lowest **Priority** value (for example, **3**) has only the **Increase priority** button available.</span></span>

   - <span data-ttu-id="87a94-226">Wenn Sie über drei oder mehr Richtlinien für sichere Links verfügen, stehen richtlinien zwischen dem höchsten und dem niedrigsten Prioritätswert sowohl die Schaltflächen "Priorität erhöhen" als auch **"Priorität verringern"** zur Verfügung. </span><span class="sxs-lookup"><span data-stu-id="87a94-226">If you have three or more Safe Links policies, policies between the highest and lowest priority values have both the **Increase priority** and **Decrease priority** buttons available.</span></span>

4. <span data-ttu-id="87a94-227">Klicken **Sie auf "Priorität erhöhen"** **oder "Priorität verringern",** um den **Prioritätswert zu** ändern.</span><span class="sxs-lookup"><span data-stu-id="87a94-227">Click **Increase priority** or **Decrease priority** to change the **Priority** value.</span></span>

5. <span data-ttu-id="87a94-228">Klicken Sie nach Abschluss des Vorgangs auf **Schließen**.</span><span class="sxs-lookup"><span data-stu-id="87a94-228">When you're finished, click **Close**.</span></span>

## <a name="use-the-security--compliance-center-to-remove-safe-links-policies"></a><span data-ttu-id="87a94-229">Verwenden des Security & Compliance Center zum Entfernen von Richtlinien für sichere Links</span><span class="sxs-lookup"><span data-stu-id="87a94-229">Use the Security & Compliance Center to remove Safe Links policies</span></span>

1. <span data-ttu-id="87a94-230">Wechseln Sie im Security & Compliance Center zu **"AtP-sichere** Links" zur Richtlinie zur \>  \> **Bedrohungsverwaltung.**</span><span class="sxs-lookup"><span data-stu-id="87a94-230">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Links**.</span></span>

2. <span data-ttu-id="87a94-231">Wählen Sie **auf der Seite "Sichere** Links" eine Richtlinie aus der Liste aus, und klicken Sie darauf (aktivieren Sie nicht das Kontrollkästchen).</span><span class="sxs-lookup"><span data-stu-id="87a94-231">On the **Safe Links** page, select a policy from the list and click on it (don't select the check box).</span></span>

3. <span data-ttu-id="87a94-232">Klicken Sie in den angezeigten Richtliniendetails auf "Richtlinie löschen", und klicken Sie dann **im** angezeigten Warndialogfeld auf "Ja".</span><span class="sxs-lookup"><span data-stu-id="87a94-232">In the policy details fly out that appears, click **Delete policy**, and then click **Yes** in the warning dialog that appears.</span></span>

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-links-policies"></a><span data-ttu-id="87a94-233">Verwenden von Exchange Online PowerShell oder der eigenständigen EOP PowerShell zum Konfigurieren von Richtlinien für sichere Links</span><span class="sxs-lookup"><span data-stu-id="87a94-233">Use Exchange Online PowerShell or standalone EOP PowerShell to configure Safe Links policies</span></span>

<span data-ttu-id="87a94-234">Wie zuvor beschrieben, besteht eine Richtlinie für sichere Links aus einer Richtlinie für sichere Links und einer Regel für sichere Links.</span><span class="sxs-lookup"><span data-stu-id="87a94-234">As previously described, a Safe Links policy consists of a safe links policy and a safe links rule.</span></span>

<span data-ttu-id="87a94-235">In PowerShell ist der Unterschied zwischen Richtlinien für sichere Links und Regeln für sichere Links offensichtlich.</span><span class="sxs-lookup"><span data-stu-id="87a94-235">In PowerShell, the difference between safe links policies and safe links rules is apparent.</span></span> <span data-ttu-id="87a94-236">Richtlinien für sichere Links werden mithilfe der **\* Cmdlets "-SafeLinksPolicy"** und Regeln für sichere Links mithilfe der **\* Cmdlets "-SafeLinksRule"** verwaltet.</span><span class="sxs-lookup"><span data-stu-id="87a94-236">You manage safe links policies by using the **\*-SafeLinksPolicy** cmdlets, and you manage safe links rules by using the **\*-SafeLinksRule** cmdlets.</span></span>

- <span data-ttu-id="87a94-237">In PowerShell erstellen Sie zuerst die Richtlinie für sichere Links und dann die Regel für sichere Links, die die Richtlinie identifiziert, auf die die Regel angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="87a94-237">In PowerShell, you create the safe links policy first, then you create the safe links rule that identifies the policy that the rule applies to.</span></span>
- <span data-ttu-id="87a94-238">In PowerShell ändern Sie die Einstellungen in der Richtlinie für sichere Links und die Regel für sichere Links separat.</span><span class="sxs-lookup"><span data-stu-id="87a94-238">In PowerShell, you modify the settings in the safe links policy and the safe links rule separately.</span></span>
- <span data-ttu-id="87a94-239">Wenn Sie eine Richtlinie für sichere Links aus PowerShell entfernen, wird die entsprechende Regel für sichere Links nicht automatisch entfernt und umgekehrt.</span><span class="sxs-lookup"><span data-stu-id="87a94-239">When you remove a safe links policy from PowerShell, the corresponding safe links rule isn't automatically removed, and vice versa.</span></span>

### <a name="use-powershell-to-create-safe-links-policies"></a><span data-ttu-id="87a94-240">Verwenden von PowerShell zum Erstellen von Richtlinien für sichere Links</span><span class="sxs-lookup"><span data-stu-id="87a94-240">Use PowerShell to create Safe Links policies</span></span>

<span data-ttu-id="87a94-241">Das Erstellen einer Richtlinie für sichere Links in PowerShell besteht aus zwei Schritte:</span><span class="sxs-lookup"><span data-stu-id="87a94-241">Creating a Safe Links policy in PowerShell is a two-step process:</span></span>

1. <span data-ttu-id="87a94-242">Erstellen Sie die Richtlinie für sichere Links.</span><span class="sxs-lookup"><span data-stu-id="87a94-242">Create the safe links policy.</span></span>
2. <span data-ttu-id="87a94-243">Erstellen Sie die Regel für sichere Links, die die Richtlinie für sichere Links angibt, auf die die Regel angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="87a94-243">Create the safe links rule that specifies the safe links policy that the rule applies to.</span></span>

> [!NOTE]
> 
> - <span data-ttu-id="87a94-244">Sie können eine neue Regel für sichere Links erstellen und ihr eine vorhandene, nicht zugeordnete Richtlinie für sichere Links zuweisen.</span><span class="sxs-lookup"><span data-stu-id="87a94-244">You can create a new safe links rule and assign an existing, unassociated safe links policy to it.</span></span> <span data-ttu-id="87a94-245">Eine Regel für sichere Links kann nicht mehreren Richtlinien für sichere Links zugeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="87a94-245">A safe links rule can't be associated with more than one safe links policy.</span></span>
> 
> - <span data-ttu-id="87a94-246">Sie können die folgenden Einstellungen für neue Richtlinien für sichere Links in PowerShell konfigurieren, die im Security & Compliance Center erst nach dem Erstellen der Richtlinie verfügbar sind:</span><span class="sxs-lookup"><span data-stu-id="87a94-246">You can configure the following settings on new safe links policies in PowerShell that aren't available in the Security & Compliance Center until after you create the policy:</span></span>
> 
>   - <span data-ttu-id="87a94-247">Erstellen Sie die neue Richtlinie als deaktiviert _(aktiviert_ `$false` im **Cmdlet "New-SafeLinksRule").**</span><span class="sxs-lookup"><span data-stu-id="87a94-247">Create the new policy as disabled (_Enabled_ `$false` on the **New-SafeLinksRule** cmdlet).</span></span>
>   - <span data-ttu-id="87a94-248">Legen Sie die Priorität der Richtlinie während der Erstellung (_Priorität_ ) im _\<Number\>_ **Cmdlet "New-SafeLinksRule"** festgelegt.</span><span class="sxs-lookup"><span data-stu-id="87a94-248">Set the priority of the policy during creation (_Priority_ _\<Number\>_) on the **New-SafeLinksRule** cmdlet).</span></span>
> 
> - <span data-ttu-id="87a94-249">Eine neue Richtlinie für sichere Links, die Sie in PowerShell erstellen, wird erst im Security & Compliance Center angezeigt, wenn Sie die Richtlinie einer Regel für sichere Links zuweisen.</span><span class="sxs-lookup"><span data-stu-id="87a94-249">A new safe links policy that you create in PowerShell isn't visible in the Security & Compliance Center until you assign the policy to a safe links rule.</span></span>

#### <a name="step-1-use-powershell-to-create-a-safe-links-policy"></a><span data-ttu-id="87a94-250">Schritt 1: Erstellen einer Richtlinie für sichere Links mithilfe von PowerShell</span><span class="sxs-lookup"><span data-stu-id="87a94-250">Step 1: Use PowerShell to create a safe links policy</span></span>

<span data-ttu-id="87a94-251">Verwenden Sie die folgende Syntax, um eine Richtlinie für sichere Links zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="87a94-251">To create a safe links policy, use this syntax:</span></span>

```PowerShell
New-SafeLinksPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] [-IsEnabled <$true | $false>] [-EnableSafeLinksForTeams <$true | $false>] [-ScanUrls <$true | $false>] [-DeliverMessageAfterScan <$true | $false>] [-EnableForInternalSenders <$true | $false>] [-DoNotAllowClickThrough <$true | $false>] [-DoNotTrackUserClicks <$true | $false>] [-DoNotRewriteUrls "Entry1","Entry2",..."EntryN"]
```

> [!NOTE]
> 
> - <span data-ttu-id="87a94-252">Details zur Eintragssyntax, die für den Parameter _"DoNotRewriteUrls"_ verwendet werden soll, finden Sie in der Eintragssyntax für die Liste ["Folgende URLs nicht umschreiben".](atp-safe-links.md#entry-syntax-for-the-do-not-rewrite-the-following-urls-list)</span><span class="sxs-lookup"><span data-stu-id="87a94-252">For details about the entry syntax to use for the _DoNotRewriteUrls_ parameter, see [Entry syntax for the "Do not rewrite the following URLs" list](atp-safe-links.md#entry-syntax-for-the-do-not-rewrite-the-following-urls-list).</span></span>
> 
> - <span data-ttu-id="87a94-253">Weitere Syntax, die Sie für den Parameter _"DoNotRewriteUrls"_ verwenden können, wenn Sie vorhandene Richtlinien für sichere Links mithilfe des Cmdlets **"Set-SafeLinksPolicy"** ändern, finden Sie im Abschnitt "Verwenden von [PowerShell](#use-powershell-to-modify-safe-links-policies) zum Ändern von Richtlinien für sichere Links" weiter unten in diesem Artikel.</span><span class="sxs-lookup"><span data-stu-id="87a94-253">For additional syntax that you can use for the _DoNotRewriteUrls_ parameter when you modify existing safe links policies by using the **Set-SafeLinksPolicy** cmdlet, see the [Use PowerShell to modify safe links policies](#use-powershell-to-modify-safe-links-policies) section later in this article.</span></span>

<span data-ttu-id="87a94-254">In diesem Beispiel wird eine Richtlinie für sichere Links namens "Contoso All" mit den folgenden Werten erstellt:</span><span class="sxs-lookup"><span data-stu-id="87a94-254">This example creates a safe links policy named Contoso All with the following values:</span></span>

- <span data-ttu-id="87a94-255">Aktivieren sie die URL-Überprüfung und -Umschreibung in E-Mail-Nachrichten.</span><span class="sxs-lookup"><span data-stu-id="87a94-255">Turn on URL scanning and rewriting in email messages.</span></span>
- <span data-ttu-id="87a94-256">Aktivieren sie die URL-Überprüfung in Teams (nur TAP-Vorschau).</span><span class="sxs-lookup"><span data-stu-id="87a94-256">Turn on URL scanning in Teams (TAP Preview only).</span></span>
- <span data-ttu-id="87a94-257">Aktivieren Sie die Echtzeitprüfung von angeklickten URLs, einschließlich angeklickter Links, die auf Dateien verweisen.</span><span class="sxs-lookup"><span data-stu-id="87a94-257">Turn on real-time scanning of clicked URLs, including clicked links that point to files.</span></span>
- <span data-ttu-id="87a94-258">Warten Sie, bis die URL-Überprüfung abgeschlossen ist, bevor Sie die Nachricht zu senden.</span><span class="sxs-lookup"><span data-stu-id="87a94-258">Wait for URL scanning to complete before delivering the message.</span></span>
- <span data-ttu-id="87a94-259">Aktivieren Sie die URL-Überprüfung und -Umschreibung für interne Nachrichten.</span><span class="sxs-lookup"><span data-stu-id="87a94-259">Turn on URL scanning and rewriting for internal messages.</span></span>
- <span data-ttu-id="87a94-260">Nachverfolgen von Benutzerklicks im Zusammenhang mit dem Schutz sicherer Links (der Parameter _"DoNotTrackUserClicks"_ wird nicht verwendet, und der Standardwert ist $false, was bedeutet, dass Benutzerklicks nachverfolgt werden).</span><span class="sxs-lookup"><span data-stu-id="87a94-260">Track user clicks related to Safe Links protection (we aren't using the _DoNotTrackUserClicks_ parameter, and the default value is $false, which means user clicks are tracked).</span></span>
- <span data-ttu-id="87a94-261">Lassen Sie nicht zu, dass Benutzer auf die ursprüngliche URL klicken.</span><span class="sxs-lookup"><span data-stu-id="87a94-261">Do not allow users to click through to the original URL.</span></span>

```PowerShell
New-SafeLinksPolicy -Name "Contoso All" -IsEnabled $true -EnableSafeLinksForTeams $true -ScanUrls $true -DeliverMessageAfterScan $true -EnableForInternalSenders $true -DoNotAllowClickThrough $true
```

<span data-ttu-id="87a94-262">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [New-SafeLinksPolicy](https://docs.microsoft.com/powershell/module/exchange/new-safelinkspolicy).</span><span class="sxs-lookup"><span data-stu-id="87a94-262">For detailed syntax and parameter information, see [New-SafeLinksPolicy](https://docs.microsoft.com/powershell/module/exchange/new-safelinkspolicy).</span></span>

#### <a name="step-2-use-powershell-to-create-a-safe-links-rule"></a><span data-ttu-id="87a94-263">Schritt 2: Erstellen einer Regel für sichere Links mithilfe von PowerShell</span><span class="sxs-lookup"><span data-stu-id="87a94-263">Step 2: Use PowerShell to create a safe links rule</span></span>

<span data-ttu-id="87a94-264">Verwenden Sie folgende Syntax, um eine Regel für sichere Links zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="87a94-264">To create a safe links rule, use this syntax:</span></span>

```PowerShell
New-SafeLinksRule -Name "<RuleName>" -SafeLinksPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"] [-Enabled <$true | $false>]
```

<span data-ttu-id="87a94-265">In diesem Beispiel wird eine Regel für sichere Links namens "Contoso All" mit den folgenden Bedingungen erstellt:</span><span class="sxs-lookup"><span data-stu-id="87a94-265">This example creates a safe links rule named Contoso All with the following conditions:</span></span>

- <span data-ttu-id="87a94-266">Die Regel ist der Richtlinie für sichere Links namens "Contoso All" zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="87a94-266">The rule is associated with the safe links policy named Contoso All.</span></span>
- <span data-ttu-id="87a94-267">Die Regel gilt für alle Empfänger in der contoso.com Domäne.</span><span class="sxs-lookup"><span data-stu-id="87a94-267">The rule applies to all recipients in the contoso.com domain.</span></span>
- <span data-ttu-id="87a94-268">Da der Parameter _"Priority"_ nicht verwendet wird, wird die Standardpriorität verwendet.</span><span class="sxs-lookup"><span data-stu-id="87a94-268">Because we aren't using the _Priority_ parameter, the default priority is used.</span></span>
- <span data-ttu-id="87a94-269">Die Regel ist aktiviert (der Parameter _"Enabled"_ wird nicht verwendet, und der Standardwert ist `$true` " ).</span><span class="sxs-lookup"><span data-stu-id="87a94-269">The rule is enabled (we aren't using the _Enabled_ parameter, and the default value is `$true`).</span></span>

```powershell
New-SafeLinksRule -Name "Contoso All" -SafeLinksPolicy "Contoso All" -RecipientDomainIs contoso.com
```

<span data-ttu-id="87a94-270">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [New-SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/new-safelinksrule).</span><span class="sxs-lookup"><span data-stu-id="87a94-270">For detailed syntax and parameter information, see [New-SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/new-safelinksrule).</span></span>

### <a name="use-powershell-to-view-safe-links-policies"></a><span data-ttu-id="87a94-271">Anzeigen von Richtlinien für sichere Links mithilfe von PowerShell</span><span class="sxs-lookup"><span data-stu-id="87a94-271">Use PowerShell to view safe links policies</span></span>

<span data-ttu-id="87a94-272">Verwenden Sie die folgende Syntax, um vorhandene Richtlinien für sichere Links anzeigen zu können:</span><span class="sxs-lookup"><span data-stu-id="87a94-272">To view existing safe links policies, use the following syntax:</span></span>

```PowerShell
Get-SafeLinksPolicy [-Identity "<PolicyIdentity>"] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="87a94-273">In diesem Beispiel wird eine Übersichtsliste aller Richtlinien für sichere Links zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="87a94-273">This example returns a summary list of all safe links policies.</span></span>

```PowerShell
Get-SafeLinksPolicy | Format-Table Name
```

<span data-ttu-id="87a94-274">In diesem Beispiel werden detaillierte Informationen für die Richtlinie für sichere Links namens "Contoso Executives" zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="87a94-274">This example returns detailed information for the safe links policy named Contoso Executives.</span></span>

```PowerShell
Get-SafeLinksPolicy -Identity "Contoso Executives"
```

<span data-ttu-id="87a94-275">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Get-SafeLinksPolicy](https://docs.microsoft.com/powershell/module/exchange/get-safelinkspolicy).</span><span class="sxs-lookup"><span data-stu-id="87a94-275">For detailed syntax and parameter information, see [Get-SafeLinksPolicy](https://docs.microsoft.com/powershell/module/exchange/get-safelinkspolicy).</span></span>

### <a name="use-powershell-to-view-safe-links-rules"></a><span data-ttu-id="87a94-276">Verwenden von PowerShell zum Anzeigen von Regeln für sichere Links</span><span class="sxs-lookup"><span data-stu-id="87a94-276">Use PowerShell to view safe links rules</span></span>

<span data-ttu-id="87a94-277">Verwenden Sie die folgende Syntax, um vorhandene Regeln für sichere Links anzeigen zu können:</span><span class="sxs-lookup"><span data-stu-id="87a94-277">To view existing safe links rules, use the following syntax:</span></span>

```PowerShell
Get-SafeLinksRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="87a94-278">In diesem Beispiel wird eine Übersichtsliste aller Regeln für sichere Links zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="87a94-278">This example returns a summary list of all safe links rules.</span></span>

```PowerShell
Get-SafeLinksRule | Format-Table Name,State
```

<span data-ttu-id="87a94-279">Führen Sie die folgenden Befehle aus, um die Liste nach aktivierten oder deaktivierten Regeln zu filtern:</span><span class="sxs-lookup"><span data-stu-id="87a94-279">To filter the list by enabled or disabled rules, run the following commands:</span></span>

```PowerShell
Get-SafeLinksRule -State Disabled
```

```PowerShell
Get-SafeLinksRule -State Enabled
```

<span data-ttu-id="87a94-280">In diesem Beispiel werden detaillierte Informationen für die Regel für sichere Links namens "Contoso Executives" zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="87a94-280">This example returns detailed information for the safe links rule named Contoso Executives.</span></span>

```PowerShell
Get-SafeLinksRule -Identity "Contoso Executives"
```

<span data-ttu-id="87a94-281">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Get-SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/get-safelinksrule).</span><span class="sxs-lookup"><span data-stu-id="87a94-281">For detailed syntax and parameter information, see [Get-SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/get-safelinksrule).</span></span>

### <a name="use-powershell-to-modify-safe-links-policies"></a><span data-ttu-id="87a94-282">Verwenden von PowerShell zum Ändern von Richtlinien für sichere Links</span><span class="sxs-lookup"><span data-stu-id="87a94-282">Use PowerShell to modify safe links policies</span></span>

<span data-ttu-id="87a94-283">Sie können eine Richtlinie für sichere Links in PowerShell nicht umbenennen (das **Cmdlet "Set-SafeLinksPolicy"** hat keinen _Parameter "Name")._</span><span class="sxs-lookup"><span data-stu-id="87a94-283">You can't rename a safe links policy in PowerShell (the **Set-SafeLinksPolicy** cmdlet has no _Name_ parameter).</span></span> <span data-ttu-id="87a94-284">Wenn Sie eine Richtlinie für sichere Links im Security & Compliance Center umbenennen, benennen Sie nur die Regel für sichere Links _um._</span><span class="sxs-lookup"><span data-stu-id="87a94-284">When you rename a Safe Links policy in the Security & Compliance Center, you're only renaming the safe links _rule_.</span></span>

<span data-ttu-id="87a94-285">Die einzige zusätzliche Überlegung zum Ändern von Richtlinien für sichere Links in PowerShell ist die verfügbare Syntax für den Parameter _"DoNotRewriteUrls"_ (die Liste ["Folgende URLs](atp-safe-links.md#do-not-rewrite-the-following-urls-lists-in-safe-links-policies)dürfen nicht neu geschrieben werden" ):</span><span class="sxs-lookup"><span data-stu-id="87a94-285">The only additional consideration for modifying safe links policies in PowerShell is the available syntax for the _DoNotRewriteUrls_ parameter (the ["Do not rewrite the following URLs" list](atp-safe-links.md#do-not-rewrite-the-following-urls-lists-in-safe-links-policies)):</span></span>

- <span data-ttu-id="87a94-286">Verwenden Sie die folgende Syntax, um Werte hinzuzufügen, die vorhandene Einträge `"Entry1","Entry2,..."EntryN"` ersetzen:</span><span class="sxs-lookup"><span data-stu-id="87a94-286">To add values that will replace any existing entries, use the following syntax: `"Entry1","Entry2,..."EntryN"`.</span></span>
- <span data-ttu-id="87a94-287">Verwenden Sie die folgende Syntax, um Werte ohne Auswirkungen auf andere Einträge hinzuzufügen oder zu entfernen: `@{Add="Entry1","Entry2"...; Remove="Entry3","Entry4"...}`</span><span class="sxs-lookup"><span data-stu-id="87a94-287">To add or remove values without affecting other existing entries, use the following syntax: `@{Add="Entry1","Entry2"...; Remove="Entry3","Entry4"...}`</span></span>

<span data-ttu-id="87a94-288">Andernfalls sind dieselben Einstellungen verfügbar, wenn Sie eine Richtlinie für sichere Links erstellen, wie in Schritt [1 beschrieben:](#step-1-use-powershell-to-create-a-safe-links-policy) Verwenden von PowerShell zum Erstellen eines Richtlinienabschnitts für sichere Links weiter oben in diesem Artikel.</span><span class="sxs-lookup"><span data-stu-id="87a94-288">Otherwise, the same settings are available when you create a safe links policy as described in the [Step 1: Use PowerShell to create a safe links policy](#step-1-use-powershell-to-create-a-safe-links-policy) section earlier in this article.</span></span>

<span data-ttu-id="87a94-289">Verwenden Sie folgende Syntax, um eine Richtlinie für sichere Links zu ändern:</span><span class="sxs-lookup"><span data-stu-id="87a94-289">To modify a safe links policy, use this syntax:</span></span>

```PowerShell
Set-SafeLinksPolicy -Identity "<PolicyName>" <Settings>
```

<span data-ttu-id="87a94-290">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Set-SafeLinksPolicy](https://docs.microsoft.com/powershell/module/exchange/set-safelinkspolicy).</span><span class="sxs-lookup"><span data-stu-id="87a94-290">For detailed syntax and parameter information, see [Set-SafeLinksPolicy](https://docs.microsoft.com/powershell/module/exchange/set-safelinkspolicy).</span></span>

### <a name="use-powershell-to-modify-safe-links-rules"></a><span data-ttu-id="87a94-291">Verwenden von PowerShell zum Ändern von Regeln für sichere Links</span><span class="sxs-lookup"><span data-stu-id="87a94-291">Use PowerShell to modify safe links rules</span></span>

<span data-ttu-id="87a94-292">Die einzige Einstellung, die nicht verfügbar ist, wenn Sie eine Regel für sichere Links in PowerShell ändern, ist der Parameter _"Enabled",_ mit dem Sie eine deaktivierte Regel erstellen können.</span><span class="sxs-lookup"><span data-stu-id="87a94-292">The only setting that's not available when you modify a safe links rule in PowerShell is the _Enabled_ parameter that allows you to create a disabled rule.</span></span> <span data-ttu-id="87a94-293">Informationen zum Aktivieren oder Deaktivieren vorhandener Regeln für sichere Links finden Sie im nächsten Abschnitt.</span><span class="sxs-lookup"><span data-stu-id="87a94-293">To enable or disable existing safe links rules, see the next section.</span></span>

<span data-ttu-id="87a94-294">Andernfalls sind dieselben Einstellungen verfügbar, wenn Sie eine Regel erstellen, wie in Schritt [2 beschrieben:](#step-2-use-powershell-to-create-a-safe-links-rule) Verwenden von PowerShell zum Erstellen eines Regelabschnitts für sichere Links weiter oben in diesem Artikel.</span><span class="sxs-lookup"><span data-stu-id="87a94-294">Otherwise, the same settings are available when you create a rule as described in the [Step 2: Use PowerShell to create a safe links rule](#step-2-use-powershell-to-create-a-safe-links-rule) section earlier in this article.</span></span>

<span data-ttu-id="87a94-295">Verwenden Sie die folgende Syntax, um eine Regel für sichere Links zu ändern:</span><span class="sxs-lookup"><span data-stu-id="87a94-295">To modify a safe links rule, use this syntax:</span></span>

```PowerShell
Set-SafeLinksRule -Identity "<RuleName>" <Settings>
```

<span data-ttu-id="87a94-296">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Set-SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/set-safelinksrule).</span><span class="sxs-lookup"><span data-stu-id="87a94-296">For detailed syntax and parameter information, see [Set-SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/set-safelinksrule).</span></span>

### <a name="use-powershell-to-enable-or-disable-safe-links-rules"></a><span data-ttu-id="87a94-297">Verwenden von PowerShell zum Aktivieren oder Deaktivieren von Regeln für sichere Links</span><span class="sxs-lookup"><span data-stu-id="87a94-297">Use PowerShell to enable or disable safe links rules</span></span>

<span data-ttu-id="87a94-298">Durch Aktivieren oder Deaktivieren einer Regel für sichere Links in PowerShell wird die gesamte Richtlinie für sichere Links (die Regel für sichere Links und die zugewiesene Richtlinie für sichere Links) aktiviert oder deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="87a94-298">Enabling or disabling a safe links rule in PowerShell enables or disables the whole Safe Links policy (the safe links rule and the assigned safe links policy).</span></span>

<span data-ttu-id="87a94-299">Verwenden Sie folgende Syntax, um eine Regel für sichere Links in PowerShell zu aktivieren oder zu deaktivieren:</span><span class="sxs-lookup"><span data-stu-id="87a94-299">To enable or disable a safe links rule in PowerShell, use this syntax:</span></span>

```PowerShell
<Enable-SafeLinksRule | Disable-SafeLinksRule> -Identity "<RuleName>"
```

<span data-ttu-id="87a94-300">In diesem Beispiel wird die Regel für sichere Links namens "Marketing Department" deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="87a94-300">This example disables the safe links rule named Marketing Department.</span></span>

```PowerShell
Disable-SafeLinksRule -Identity "Marketing Department"
```

<span data-ttu-id="87a94-301">In diesem Beispiel wird dieselbe Regel aktiviert.</span><span class="sxs-lookup"><span data-stu-id="87a94-301">This example enables same rule.</span></span>

```PowerShell
Enable-SafeLinksRule -Identity "Marketing Department"
```

<span data-ttu-id="87a94-302">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Enable-SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/enable-safelinksrule) und [Disable-SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/disable-safelinksrule).</span><span class="sxs-lookup"><span data-stu-id="87a94-302">For detailed syntax and parameter information, see [Enable-SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/enable-safelinksrule) and [Disable-SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/disable-safelinksrule).</span></span>

### <a name="use-powershell-to-set-the-priority-of-safe-links-rules"></a><span data-ttu-id="87a94-303">Verwenden von PowerShell zum Festlegen der Priorität von Regeln für sichere Links</span><span class="sxs-lookup"><span data-stu-id="87a94-303">Use PowerShell to set the priority of safe links rules</span></span>

<span data-ttu-id="87a94-304">Der höchste Prioritätswert, den Sie für eine Regel festlegen können, ist 0.</span><span class="sxs-lookup"><span data-stu-id="87a94-304">The highest priority value you can set on a rule is 0.</span></span> <span data-ttu-id="87a94-305">Der niedrigste Wert, den Sie festlegen können, hängt von der Anzahl von Regeln ab.</span><span class="sxs-lookup"><span data-stu-id="87a94-305">The lowest value you can set depends on the number of rules.</span></span> <span data-ttu-id="87a94-306">Wenn Sie z. B. fünf Regeln haben, können Sie die Prioritätswerte 0 bis 4 verwenden.</span><span class="sxs-lookup"><span data-stu-id="87a94-306">For example, if you have five rules, you can use the priority values 0 through 4.</span></span> <span data-ttu-id="87a94-307">Das Ändern der Priorität einer vorhandenen Regel kann sich entsprechend auf andere Regeln auswirken.</span><span class="sxs-lookup"><span data-stu-id="87a94-307">Changing the priority of an existing rule can have a cascading effect on other rules.</span></span> <span data-ttu-id="87a94-308">Wenn Sie z. B. fünf benutzerdefinierte Regeln haben (Priorität 0 bis 4) und die Priorität einer Regel in 2 ändern, erhält die vorhandene Regel mit Priorität 2 die Priorität 3, und die Regel mit Priorität 3 erhält Priorität 4.</span><span class="sxs-lookup"><span data-stu-id="87a94-308">For example, if you have five custom rules (priorities 0 through 4), and you change the priority of a rule to 2, the existing rule with priority 2 is changed to priority 3, and the rule with priority 3 is changed to priority 4.</span></span>

<span data-ttu-id="87a94-309">Verwenden Sie die folgende Syntax, um die Priorität einer Regel für sichere Links in PowerShell zu festlegen:</span><span class="sxs-lookup"><span data-stu-id="87a94-309">To set the priority of a safe links rule in PowerShell, use the following syntax:</span></span>

```PowerShell
Set-SafeLinksRule -Identity "<RuleName>" -Priority <Number>
```

<span data-ttu-id="87a94-p123">In diesem Beispiel wird die Priorität der Regel namens „Marketing Department“ auf 2 festgelegt. Alle vorhandenen Regeln mit Priorität kleiner oder gleich 2 werden um 1 verringert (die Prioritätswerte werden um 1 erhöht).</span><span class="sxs-lookup"><span data-stu-id="87a94-p123">This example sets the priority of the rule named Marketing Department to 2. All existing rules that have a priority less than or equal to 2 are decreased by 1 (their priority numbers are increased by 1).</span></span>

```PowerShell
Set-SafeLinksRule -Identity "Marketing Department" -Priority 2
```

> [!NOTE]
> <span data-ttu-id="87a94-312">Verwenden Sie zum Festlegen der Priorität einer neuen Regel beim Erstellen stattdessen den Parameter _"Priority"_ im **Cmdlet "New-SafeLinksRule".**</span><span class="sxs-lookup"><span data-stu-id="87a94-312">To set the priority of a new rule when you create it, use the _Priority_ parameter on the **New-SafeLinksRule** cmdlet instead.</span></span>

<span data-ttu-id="87a94-313">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Set-SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/set-safelinksrule).</span><span class="sxs-lookup"><span data-stu-id="87a94-313">For detailed syntax and parameter information, see [Set-SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/set-safelinksrule).</span></span>

### <a name="use-powershell-to-remove-safe-links-policies"></a><span data-ttu-id="87a94-314">Verwenden von PowerShell zum Entfernen von Richtlinien für sichere Links</span><span class="sxs-lookup"><span data-stu-id="87a94-314">Use PowerShell to remove safe links policies</span></span>

<span data-ttu-id="87a94-315">Wenn Sie PowerShell verwenden, um eine Richtlinie für sichere Links zu entfernen, wird die entsprechende Regel für sichere Links nicht entfernt.</span><span class="sxs-lookup"><span data-stu-id="87a94-315">When you use PowerShell to remove a safe links policy, the corresponding safe links rule isn't removed.</span></span>

<span data-ttu-id="87a94-316">Verwenden Sie folgende Syntax, um eine Richtlinie für sichere Links in PowerShell zu entfernen:</span><span class="sxs-lookup"><span data-stu-id="87a94-316">To remove a safe links policy in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-SafeLinksPolicy -Identity "<PolicyName>"
```

<span data-ttu-id="87a94-317">In diesem Beispiel wird die Richtlinie für sichere Links namens "Marketing Department" entfernt.</span><span class="sxs-lookup"><span data-stu-id="87a94-317">This example removes the safe links policy named Marketing Department.</span></span>

```PowerShell
Remove-SafeLinksPolicy -Identity "Marketing Department"
```

<span data-ttu-id="87a94-318">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Remove-SafeLinksPolicy](https://docs.microsoft.com/powershell/module/exchange/remove-safelinkspolicy).</span><span class="sxs-lookup"><span data-stu-id="87a94-318">For detailed syntax and parameter information, see [Remove-SafeLinksPolicy](https://docs.microsoft.com/powershell/module/exchange/remove-safelinkspolicy).</span></span>

### <a name="use-powershell-to-remove-safe-links-rules"></a><span data-ttu-id="87a94-319">Verwenden von PowerShell zum Entfernen von Regeln für sichere Links</span><span class="sxs-lookup"><span data-stu-id="87a94-319">Use PowerShell to remove safe links rules</span></span>

<span data-ttu-id="87a94-320">Wenn Sie PowerShell verwenden, um eine Regel für sichere Links zu entfernen, wird die entsprechende Richtlinie für sichere Links nicht entfernt.</span><span class="sxs-lookup"><span data-stu-id="87a94-320">When you use PowerShell to remove a safe links rule, the corresponding safe links policy isn't removed.</span></span>

<span data-ttu-id="87a94-321">Verwenden Sie folgende Syntax, um eine Regel für sichere Links in PowerShell zu entfernen:</span><span class="sxs-lookup"><span data-stu-id="87a94-321">To remove a safe links rule in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-SafeLinksRule -Identity "<PolicyName>"
```

<span data-ttu-id="87a94-322">In diesem Beispiel wird die Regel für sichere Links namens "Marketing Department" entfernt.</span><span class="sxs-lookup"><span data-stu-id="87a94-322">This example removes the safe links rule named Marketing Department.</span></span>

```PowerShell
Remove-SafeLinksRule -Identity "Marketing Department"
```

<span data-ttu-id="87a94-323">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Remove-SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/remove-safelinksrule).</span><span class="sxs-lookup"><span data-stu-id="87a94-323">For detailed syntax and parameter information, see [Remove-SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/remove-safelinksrule).</span></span>

<span data-ttu-id="87a94-324">Überprüfen Sie die verfügbaren Microsoft Defender für Office 365-Berichte, um sicherzustellen, dass sichere Links Nachrichten überprüfen.</span><span class="sxs-lookup"><span data-stu-id="87a94-324">To verify that Safe Links is scanning messages, check the available Microsoft Defender for Office 365 reports.</span></span> <span data-ttu-id="87a94-325">Weitere Informationen finden Sie unter [Anzeigen von Berichten für Defender für Office 365](view-reports-for-atp.md) und Verwenden von Explorer im Security & Compliance [Center](threat-explorer.md).</span><span class="sxs-lookup"><span data-stu-id="87a94-325">For more information, see [View reports for Defender for Office 365](view-reports-for-atp.md) and [Use Explorer in the Security & Compliance Center](threat-explorer.md).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="87a94-326">Wie können Sie feststellen, dass diese Verfahren erfolgreich waren?</span><span class="sxs-lookup"><span data-stu-id="87a94-326">How do you know these procedures worked?</span></span>

<span data-ttu-id="87a94-327">Gehen Sie wie folgt vor, um sicherzustellen, dass Richtlinien für sichere Links erfolgreich erstellt, geändert oder entfernt wurden:</span><span class="sxs-lookup"><span data-stu-id="87a94-327">To verify that you've successfully created, modified, or removed Safe Links policies, do any of the following steps:</span></span>

- <span data-ttu-id="87a94-328">Wechseln Sie im Security & Compliance Center zu **"AtP-sichere** Links" zur Richtlinie zur \>  \> **Bedrohungsverwaltung.**</span><span class="sxs-lookup"><span data-stu-id="87a94-328">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Links**.</span></span> <span data-ttu-id="87a94-329">Überprüfen Sie die Liste der Richtlinien, deren **Statuswerte** und ihre **Prioritätswerte.**</span><span class="sxs-lookup"><span data-stu-id="87a94-329">Verify the list of policies, their **Status** values, and their **Priority** values.</span></span> <span data-ttu-id="87a94-330">Um weitere Details anzuzeigen, wählen Sie die Richtlinie aus der Liste aus, und zeigen Sie die Details im Flyout an.</span><span class="sxs-lookup"><span data-stu-id="87a94-330">To view more details, select the policy from the list, and view the details in the fly out.</span></span>

- <span data-ttu-id="87a94-331">Ersetzen Sie in Exchange Online PowerShell oder Exchange Online Protection PowerShell durch den Namen der Richtlinie oder Regel, führen Sie den folgenden Befehl aus, und überprüfen Sie \<Name\> die Einstellungen:</span><span class="sxs-lookup"><span data-stu-id="87a94-331">In Exchange Online PowerShell or Exchange Online Protection PowerShell, replace \<Name\> with the name of the policy or rule, run the following command, and verify the settings:</span></span>

  ```PowerShell
  Get-SafeLinksPolicy -Identity "<Name>"
  ```

  ```PowerShell
  Get-SafeLinksRule -Identity "<Name>"
  ```
