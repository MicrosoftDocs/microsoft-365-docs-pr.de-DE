---
title: Einrichten Tresor Anlagenrichtlinien in Microsoft Defender für Office 365
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
description: Erfahren Sie, wie Sie Tresor Anlagenrichtlinien definieren, um Ihre Organisation vor schädlichen Dateien in E-Mails zu schützen.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: e516a16ff28c762e154fd908312df65ea48699bc
ms.sourcegitcommit: ebb1c3b4d94058a58344317beb9475c8a2eae9a7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/24/2021
ms.locfileid: "53108223"
---
# <a name="set-up-safe-attachments-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="1e460-103">Einrichten Tresor Anlagenrichtlinien in Microsoft Defender für Office 365</span><span class="sxs-lookup"><span data-stu-id="1e460-103">Set up Safe Attachments policies in Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="1e460-104">**Gilt für**</span><span class="sxs-lookup"><span data-stu-id="1e460-104">**Applies to**</span></span>
- [<span data-ttu-id="1e460-105">Microsoft Defender für Office 365 Plan 1 und Plan 2</span><span class="sxs-lookup"><span data-stu-id="1e460-105">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="1e460-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="1e460-106">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

> [!IMPORTANT]
> <span data-ttu-id="1e460-107">Dieser Artikel richtet sich an Geschäftskunden, die über [Microsoft Defender für Office 365](whats-new-in-defender-for-office-365.md) verfügen.</span><span class="sxs-lookup"><span data-stu-id="1e460-107">This article is intended for business customers who have [Microsoft Defender for Office 365](whats-new-in-defender-for-office-365.md).</span></span> <span data-ttu-id="1e460-108">Wenn Sie ein Privatbenutzer sind, der nach Informationen zum Scannen von Anlagen in Outlook sucht, finden Sie weitere Informationen unter [Advanced Outlook.com Security](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).</span><span class="sxs-lookup"><span data-stu-id="1e460-108">If you're a home user looking for information about attachment scanning in Outlook, see [Advanced Outlook.com security](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).</span></span>

<span data-ttu-id="1e460-109">Tresor Anlagen ist ein Feature in [Microsoft Defender für Office 365,](whats-new-in-defender-for-office-365.md) das eine virtuelle Umgebung verwendet, um Anlagen in eingehenden E-Mail-Nachrichten zu überprüfen, nachdem sie vom [Antischadsoftwareschutz in Exchange Online Protection (EOP)](anti-malware-protection.md)gescannt wurden, jedoch vor der Übermittlung an Empfänger.</span><span class="sxs-lookup"><span data-stu-id="1e460-109">Safe Attachments is a feature in [Microsoft Defender for Office 365](whats-new-in-defender-for-office-365.md) that uses a virtual environment to check attachments in inbound email messages after they've been scanned by [anti-malware protection in Exchange Online Protection (EOP)](anti-malware-protection.md), but before delivery to recipients.</span></span> <span data-ttu-id="1e460-110">Weitere Informationen finden Sie unter [Tresor Anlagen in Microsoft Defender für Office 365](safe-attachments.md).</span><span class="sxs-lookup"><span data-stu-id="1e460-110">For more information, see [Safe Attachments in Microsoft Defender for Office 365](safe-attachments.md).</span></span>

<span data-ttu-id="1e460-111">Es gibt keine integrierte oder standardmäßige richtlinie für Tresor Anlagen.</span><span class="sxs-lookup"><span data-stu-id="1e460-111">There's no built-in or default Safe Attachments policy.</span></span> <span data-ttu-id="1e460-112">Um Tresor Anlagenüberprüfung von E-Mail-Nachrichtenanlagen zu erhalten, müssen Sie eine oder mehrere Tresor Anlagenrichtlinien erstellen, wie in diesem Artikel beschrieben.</span><span class="sxs-lookup"><span data-stu-id="1e460-112">To get Safe Attachments scanning of email message attachments, you need to create one or more Safe Attachments policies as described in this article.</span></span>

<span data-ttu-id="1e460-113">Sie können Tresor Anlagenrichtlinien im Microsoft 365 Defender Portal oder in PowerShell konfigurieren (Exchange Online PowerShell für berechtigte Microsoft 365 Organisationen mit Postfächern in Exchange Online; eigenständige EOP PowerShell für Organisationen ohne Exchange Online Postfächer, aber mit Defender für Office 365 Add-On-Abonnements).</span><span class="sxs-lookup"><span data-stu-id="1e460-113">You can configure Safe Attachments policies in the Microsoft 365 Defender portal or in PowerShell (Exchange Online PowerShell for eligible Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes, but with Defender for Office 365 add-on subscriptions).</span></span>

<span data-ttu-id="1e460-114">Die grundlegenden Elemente einer Tresor Attachments-Richtlinie sind:</span><span class="sxs-lookup"><span data-stu-id="1e460-114">The basic elements of a Safe Attachments policy are:</span></span>

- <span data-ttu-id="1e460-115">Die Richtlinie für **sichere Anlagen:** Gibt die Aktionen für unbekannte Schadsoftwareerkennungen an, gibt an, ob Nachrichten mit Schadsoftwareanlagen an eine angegebene E-Mail-Adresse gesendet werden sollen und ob Nachrichten übermittelt werden sollen, wenn Tresor Attachments-Überprüfung nicht abgeschlossen werden kann.</span><span class="sxs-lookup"><span data-stu-id="1e460-115">**The safe attachment policy**: Specifies the actions for unknown malware detections, whether to send messages with malware attachments to a specified email address, and whether to deliver messages if Safe Attachments scanning can't complete.</span></span>
- <span data-ttu-id="1e460-116">**Die Regel für sichere Anlagen:** Gibt die Prioritäts- und Empfängerfilter an (für wen die Richtlinie gilt).</span><span class="sxs-lookup"><span data-stu-id="1e460-116">**The safe attachment rule**: Specifies the priority and recipient filters (who the policy applies to).</span></span>

<span data-ttu-id="1e460-117">Der Unterschied zwischen diesen beiden Elementen ist nicht offensichtlich, wenn Sie Tresor Anlagenrichtlinien im Microsoft 365 Defender Portal verwalten:</span><span class="sxs-lookup"><span data-stu-id="1e460-117">The difference between these two elements isn't obvious when you manage Safe Attachments policies in the Microsoft 365 Defender portal:</span></span>

- <span data-ttu-id="1e460-118">Wenn Sie eine Tresor Anlagenrichtlinie erstellen, erstellen Sie tatsächlich eine Regel für sichere Anlagen und die zugeordnete Richtlinie für sichere Anlagen gleichzeitig mit demselben Namen für beide.</span><span class="sxs-lookup"><span data-stu-id="1e460-118">When you create a Safe Attachments policy, you're actually creating a safe attachment rule and the associated safe attachment policy at the same time using the same name for both.</span></span>
- <span data-ttu-id="1e460-119">Wenn Sie eine Tresor Anlagenrichtlinie ändern, ändern Einstellungen im Zusammenhang mit dem Namen, der Priorität, aktiviert oder deaktiviert und empfängerfiltern die Regel für sichere Anlagen.</span><span class="sxs-lookup"><span data-stu-id="1e460-119">When you modify a Safe Attachments policy, settings related to the name, priority, enabled or disabled, and recipient filters modify the safe attachment rule.</span></span> <span data-ttu-id="1e460-120">Alle anderen Einstellungen ändern die zugeordnete Richtlinie für sichere Anlagen.</span><span class="sxs-lookup"><span data-stu-id="1e460-120">All other settings modify the associated safe attachment policy.</span></span>
- <span data-ttu-id="1e460-121">Wenn Sie eine Tresor Anlagenrichtlinie entfernen, werden die Regel für sichere Anlagen und die zugehörige Richtlinie für sichere Anlagen entfernt.</span><span class="sxs-lookup"><span data-stu-id="1e460-121">When you remove a Safe Attachments policy, the safe attachment rule and the associated safe attachment policy are removed.</span></span>

<span data-ttu-id="1e460-122">In Exchange Online PowerShell oder der eigenständigen EOP PowerShell verwalten Sie die Richtlinie und die Regel getrennt.</span><span class="sxs-lookup"><span data-stu-id="1e460-122">In Exchange Online PowerShell or standalone EOP PowerShell, you manage the policy and the rule separately.</span></span> <span data-ttu-id="1e460-123">Weitere Informationen finden Sie im Abschnitt ["Use Exchange Online PowerShell or standalone EOP PowerShell to configure Tresor Attachments policies"](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-attachments-policies) weiter unten in diesem Artikel.</span><span class="sxs-lookup"><span data-stu-id="1e460-123">For more information, see the [Use Exchange Online PowerShell or standalone EOP PowerShell to configure Safe Attachments policies](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-attachments-policies) section later in this article.</span></span>

> [!NOTE]
> <span data-ttu-id="1e460-124">Im globalen Einstellungsbereich von Tresor Anlageneinstellungen konfigurieren Sie Features, die nicht von Tresor Anlagenrichtlinien abhängig sind.</span><span class="sxs-lookup"><span data-stu-id="1e460-124">In the global settings area of Safe Attachments settings, you configure features that are not dependent on Safe Attachments policies.</span></span> <span data-ttu-id="1e460-125">Anweisungen finden Sie unter [Aktivieren von Tresor Anlagen für SharePoint, OneDrive und Microsoft Teams](turn-on-mdo-for-spo-odb-and-teams.md) und Tresor Dokumente in [Microsoft 365 E5](safe-docs.md).</span><span class="sxs-lookup"><span data-stu-id="1e460-125">For instructions see [Turn on Safe Attachments for SharePoint, OneDrive, and Microsoft Teams](turn-on-mdo-for-spo-odb-and-teams.md) and [Safe Documents in Microsoft 365 E5](safe-docs.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="1e460-126">Was sollten Sie wissen, bevor Sie beginnen?</span><span class="sxs-lookup"><span data-stu-id="1e460-126">What do you need to know before you begin?</span></span>

- <span data-ttu-id="1e460-127">Sie öffnen das Microsoft 365 Defender-Portal unter <https://security.microsoft.com>.</span><span class="sxs-lookup"><span data-stu-id="1e460-127">You open the Microsoft 365 Defender portal at <https://security.microsoft.com>.</span></span> <span data-ttu-id="1e460-128">To go directly to the **Tresor Attachments** page, use <https://security.microsoft.com/safeattachmentv2> .</span><span class="sxs-lookup"><span data-stu-id="1e460-128">To go directly to the **Safe Attachments** page, use <https://security.microsoft.com/safeattachmentv2>.</span></span>

- <span data-ttu-id="1e460-129">Wie Sie eine Verbindung mit Exchange Online PowerShell herstellen, finden Sie unter [Herstellen einer Verbindung mit Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="1e460-129">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="1e460-130">Informationen zum Herstellen einer Verbindung mit dem eigenständigen Exchange Online Protection PowerShell finden Sie unter [Verbinden mit PowerShell in Exchange Online Protection](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="1e460-130">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="1e460-131">Sie benötigen Berechtigungen, bevor Sie die Verfahren in diesem Artikel ausführen können:</span><span class="sxs-lookup"><span data-stu-id="1e460-131">You need permissions before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="1e460-132">Um Tresor Anlagenrichtlinien zu erstellen, zu ändern und zu löschen, müssen Sie Mitglied der Rollengruppen **"Organisationsverwaltung"** oder **"Sicherheitsadministrator"** im Microsoft 365 Defender-Portal **und** Mitglied der Rollengruppe **"Organisationsverwaltung"** in Exchange Online sein.</span><span class="sxs-lookup"><span data-stu-id="1e460-132">To create, modify, and delete Safe Attachments policies, you need to be a member of the **Organization Management** or **Security Administrator** role groups in the Microsoft 365 Defender portal **and** a member of the **Organization Management** role group in Exchange Online.</span></span>
  - <span data-ttu-id="1e460-133">Für den schreibgeschützten Zugriff auf Tresor Anlagenrichtlinien müssen Sie Mitglied der Rollengruppen **"Globaler Leser"** oder **"Sicherheitsleseberechtigter"** im Microsoft 365 Defender Portal sein.</span><span class="sxs-lookup"><span data-stu-id="1e460-133">For read-only access to Safe Attachments policies, you need to be a member of the **Global Reader** or **Security Reader** role groups in the Microsoft 365 Defender portal.</span></span>

  <span data-ttu-id="1e460-134">Weitere Informationen finden Sie unter ["Berechtigungen" im Microsoft 365 Defender-Portal](permissions-microsoft-365-security-center.md) und ["Berechtigungen" in Exchange Online.](/exchange/permissions-exo/permissions-exo)</span><span class="sxs-lookup"><span data-stu-id="1e460-134">For more information, see [Permissions in the Microsoft 365 Defender portal](permissions-microsoft-365-security-center.md) and [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo).</span></span>

  <span data-ttu-id="1e460-135">**Hinweise**:</span><span class="sxs-lookup"><span data-stu-id="1e460-135">**Notes**:</span></span>

  - <span data-ttu-id="1e460-136">Wenn Sie Benutzer zur entsprechenden Azure Active Directory Rolle im Microsoft 365 Admin Center hinzufügen, erhalten Benutzer die erforderlichen Berechtigungen im Microsoft 365 Defender-Portal _und_ Berechtigungen für andere Features in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="1e460-136">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Microsoft 365 Defender portal _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="1e460-137">Weitere Informationen finden Sie unter [Informationen zu Administratorrollen](../../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="1e460-137">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  - <span data-ttu-id="1e460-138">Die Rollengruppe **Organisationsverwaltung mit Leserechten** in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) ermöglicht auch einen schreibgeschützten Zugriff auf das Feature.</span><span class="sxs-lookup"><span data-stu-id="1e460-138">The **View-Only Organization Management** role group in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

- <span data-ttu-id="1e460-139">Unsere empfohlenen Einstellungen für Tresor Anlagenrichtlinien finden Sie unter [Tresor Anlageneinstellungen.](recommended-settings-for-eop-and-office365.md#safe-attachments-settings)</span><span class="sxs-lookup"><span data-stu-id="1e460-139">For our recommended settings for Safe Attachments policies, see [Safe Attachments settings](recommended-settings-for-eop-and-office365.md#safe-attachments-settings).</span></span>

- <span data-ttu-id="1e460-140">Es kann bis zu 30 Minuten dauern, bis eine neue oder aktualisierte Richtlinie angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="1e460-140">Allow up to 30 minutes for a new or updated policy to be applied.</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-create-safe-attachments-policies"></a><span data-ttu-id="1e460-141">Verwenden des Microsoft 365 Defender Portals zum Erstellen Tresor Anlagenrichtlinien</span><span class="sxs-lookup"><span data-stu-id="1e460-141">Use the Microsoft 365 Defender portal to create Safe Attachments policies</span></span>

<span data-ttu-id="1e460-142">Beim Erstellen einer benutzerdefinierten Tresor Anlagenrichtlinie im Microsoft 365 Defender Portal werden die Regel für sichere Anlagen und die zugehörige Richtlinie für sichere Anlagen gleichzeitig mit demselben Namen für beide erstellt.</span><span class="sxs-lookup"><span data-stu-id="1e460-142">Creating a custom Safe Attachments policy in the Microsoft 365 Defender portal creates the safe attachment rule and the associated safe attachment policy at the same time using the same name for both.</span></span>

1. <span data-ttu-id="1e460-143">Wechseln Sie im Microsoft 365 Defender Portal zur Seite Richtlinien für **E-Mail-&** \> **Zusammenarbeitsrichtlinien & Richtlinien** für Die \> **Bedrohungsregeln** \>  Tresor \> **Anlagen.**</span><span class="sxs-lookup"><span data-stu-id="1e460-143">In the Microsoft 365 Defender portal, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** page \> **Policies** section \> **Safe Attachments**.</span></span>

2. <span data-ttu-id="1e460-144">Klicken Sie auf der Seite **Tresor Anlagen** auf das ![ Symbol ](../../media/m365-cc-sc-create-icon.png) **"Erstellen".**</span><span class="sxs-lookup"><span data-stu-id="1e460-144">On the **Safe Attachments** page, click ![Create icon](../../media/m365-cc-sc-create-icon.png) **Create**.</span></span>

3. <span data-ttu-id="1e460-145">Der Richtlinienassistent wird geöffnet.</span><span class="sxs-lookup"><span data-stu-id="1e460-145">The policy wizard opens.</span></span> <span data-ttu-id="1e460-146">Konfigurieren Sie auf der Seite **"Richtlinie benennen"** die folgenden Einstellungen:</span><span class="sxs-lookup"><span data-stu-id="1e460-146">On the **Name your policy** page, configure the following settings:</span></span>
   - <span data-ttu-id="1e460-147">**Name**: Geben Sie einen eindeutigen, aussagekräftigen Namen für die Richtlinie ein.</span><span class="sxs-lookup"><span data-stu-id="1e460-147">**Name**: Enter a unique, descriptive name for the policy.</span></span>
   - <span data-ttu-id="1e460-148">**Beschreibung**: Geben Sie eine optionale Beschreibung für die Richtlinie ein.</span><span class="sxs-lookup"><span data-stu-id="1e460-148">**Description**: Enter an optional description for the policy.</span></span>

   <span data-ttu-id="1e460-149">Wenn Sie fertig sind, klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="1e460-149">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="1e460-150">Identifizieren Sie auf der angezeigten Seite **"Benutzer und Domänen"** die internen Empfänger, für die die Richtlinie gilt (Empfängerbedingungen):</span><span class="sxs-lookup"><span data-stu-id="1e460-150">On the **Users and domains** page that appears, identify the internal recipients that the policy applies to (recipient conditions):</span></span>
   - <span data-ttu-id="1e460-151">**Benutzer**: Die angegebenen Postfächer, E-Mail-Benutzer oder E-Mail-Kontakte in Ihrer Organisation.</span><span class="sxs-lookup"><span data-stu-id="1e460-151">**Users**: The specified mailboxes, mail users, or mail contacts in your organization.</span></span>
   - <span data-ttu-id="1e460-152">**Gruppen**: Die angegebenen Verteilergruppen, E-Mail-aktivierten Sicherheitsgruppen oder Microsoft 365-Gruppen in Ihrer Organisation.</span><span class="sxs-lookup"><span data-stu-id="1e460-152">**Groups**: The specified distribution groups, mail-enabled security groups, or Microsoft 365 Groups in your organization.</span></span>
   - <span data-ttu-id="1e460-153">**Domänen**: Alle Empfänger in der angegebenen [akzeptierten Domäne](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) in Ihrer Organisation.</span><span class="sxs-lookup"><span data-stu-id="1e460-153">**Domains**: All recipients in the specified [accepted domains](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) in your organization.</span></span>

   <span data-ttu-id="1e460-154">Klicken Sie auf das entsprechende Feld, beginnen Sie mit der Eingabe eines Wertes, und wählen Sie den gewünschten Wert aus den Ergebnissen aus.</span><span class="sxs-lookup"><span data-stu-id="1e460-154">Click in the appropriate box, start typing a value, and select the value that you want from the results.</span></span> <span data-ttu-id="1e460-155">Wiederholen Sie diesen Vorgang so oft wie nötig.</span><span class="sxs-lookup"><span data-stu-id="1e460-155">Repeat this process as many times as necessary.</span></span> <span data-ttu-id="1e460-156">Um einen vorhandenen Wert zu entfernen, klicken Sie auf das</span><span class="sxs-lookup"><span data-stu-id="1e460-156">To remove an existing value, click remove</span></span> ![Symbol „Entfernen“](../../media/m365-cc-sc-remove-selection-icon.png) <span data-ttu-id="1e460-158">neben dem Wert.</span><span class="sxs-lookup"><span data-stu-id="1e460-158">next to the value.</span></span>

   <span data-ttu-id="1e460-159">Für Benutzer oder Gruppen können Sie die meisten Bezeichner verwenden (Name, Anzeigename, Alias, E-Mail-Adresse, Kontoname usw.), aber in den Ergebnissen wird der entsprechende Anzeigename angezeigt.</span><span class="sxs-lookup"><span data-stu-id="1e460-159">For users or groups, you can use most identifiers (name, display name, alias, email address, account name, etc.), but the corresponding display name is shown in the results.</span></span> <span data-ttu-id="1e460-160">Geben Sie für Benutzer einen einzelnen Stern (\*) ein, um alle verfügbaren Werte anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="1e460-160">For users, enter an asterisk (\*) by itself to see all available values.</span></span>

   <span data-ttu-id="1e460-161">Mehreren Werten in der gleichen Bedingung verwenden die „ODER“-Logik (z. B. _\<recipient1\>_ ODER _\<recipient2\>_).</span><span class="sxs-lookup"><span data-stu-id="1e460-161">Multiple values in the same condition use OR logic (for example, _\<recipient1\>_ or _\<recipient2\>_).</span></span> <span data-ttu-id="1e460-162">Unterschiedlichen Bedingungen verwenden die „UND“-Logik (z. B. _\<recipient1\>_ UND _\<member of group 1\>_).</span><span class="sxs-lookup"><span data-stu-id="1e460-162">Different conditions use AND logic (for example, _\<recipient1\>_ and _\<member of group 1\>_).</span></span>

   - <span data-ttu-id="1e460-163">**Ausschließen dieser Benutzer, Gruppen und Domänen**: Um Ausnahmen für die internen Empfänger hinzuzufügen, für welche die Richtlinie gilt (Empfängerausnahmen), wählen Sie diese Option und konfigurieren Sie die Ausnahmen.</span><span class="sxs-lookup"><span data-stu-id="1e460-163">**Exclude these users, groups, and domains**: To add exceptions for the internal recipients that the policy applies to (recpient exceptions), select this option and configure the exceptions.</span></span> <span data-ttu-id="1e460-164">Die Einstellungen und das Verhalten entsprechen genau den Bedingungen.</span><span class="sxs-lookup"><span data-stu-id="1e460-164">The settings and behavior are exactly like the conditions.</span></span>

   <span data-ttu-id="1e460-165">Wenn Sie fertig sind, klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="1e460-165">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="1e460-166">Konfigurieren Sie auf der **seite Einstellungen** die folgenden Einstellungen:</span><span class="sxs-lookup"><span data-stu-id="1e460-166">On the **Settings** page, configure the following settings:</span></span>

   - <span data-ttu-id="1e460-167">**Tresor Attachments unknown malware response:** Select one of the following values:</span><span class="sxs-lookup"><span data-stu-id="1e460-167">**Safe Attachments unknown malware response**: Select one of the following values:</span></span>
     - <span data-ttu-id="1e460-168">**Aus:** In der Regel wird dieser Wert nicht empfohlen.</span><span class="sxs-lookup"><span data-stu-id="1e460-168">**Off**: Typically, we don't recommend this value.</span></span>
     - <span data-ttu-id="1e460-169">**Überwachen**</span><span class="sxs-lookup"><span data-stu-id="1e460-169">**Monitor**</span></span>
     - <span data-ttu-id="1e460-170">**Block**: Dies ist der Standardwert und der empfohlene Wert in den [voreingestellten Standard- und Strict-Sicherheitsrichtlinien.](preset-security-policies.md)</span><span class="sxs-lookup"><span data-stu-id="1e460-170">**Block**: This is the default value, and the recommended value in Standard and Strict [preset security policies](preset-security-policies.md).</span></span>
     - <span data-ttu-id="1e460-171">**Replace**</span><span class="sxs-lookup"><span data-stu-id="1e460-171">**Replace**</span></span>
     - <span data-ttu-id="1e460-172">**Dynamische Zustellung (Vorschaufeature)**</span><span class="sxs-lookup"><span data-stu-id="1e460-172">**Dynamic Delivery (Preview Feature)**</span></span>

     <span data-ttu-id="1e460-173">Diese Werte werden in [den Richtlinieneinstellungen für Tresor Anlagen](safe-attachments.md#safe-attachments-policy-settings)erläutert.</span><span class="sxs-lookup"><span data-stu-id="1e460-173">These values are explained in [Safe Attachments policy settings](safe-attachments.md#safe-attachments-policy-settings).</span></span>

   - <span data-ttu-id="1e460-174">**Umleiten von Nachrichten mit erkannten Anlagen:** Wenn Sie **"Umleitung aktivieren"** auswählen, können Sie eine E-Mail-Adresse in den **Nachrichten senden angeben, die blockierte, überwachte oder ersetzte Anlagen an das angegebene E-Mail-Adressfeld enthalten,** um Nachrichten zu senden, die Schadsoftwareanlagen zur Analyse und Untersuchung enthalten.</span><span class="sxs-lookup"><span data-stu-id="1e460-174">**Redirect messages with detected attachments**: If you select **Enable redirect**, you can specify an email address in the **Send messages that contain blocked, monitored, or replaced attachments to the specified email address** box to send messages that contain malware attachments for analysis and investigation.</span></span>

     <span data-ttu-id="1e460-175">Die Empfehlung für Standard- und Strict-Richtlinieneinstellungen besteht darin, die Umleitung zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="1e460-175">The recommendation for Standard and Strict policy settings is to enable redirection.</span></span> <span data-ttu-id="1e460-176">Weitere Informationen finden Sie unter [Tresor Anlageneinstellungen.](recommended-settings-for-eop-and-office365.md#safe-attachments-settings)</span><span class="sxs-lookup"><span data-stu-id="1e460-176">For more information, see [Safe Attachments settings](recommended-settings-for-eop-and-office365.md#safe-attachments-settings).</span></span>

   - <span data-ttu-id="1e460-177">**Wenden Sie die Erkennungsantwort Tresor Anlagen an, wenn die Überprüfung nicht abgeschlossen werden kann (Timeout oder Fehler):** Die durch Tresor Anlagen angegebene **Antwort auf unbekannte Schadsoftware** wird für Nachrichten ausgeführt, auch wenn Tresor Attachments-Überprüfung nicht abgeschlossen werden kann.</span><span class="sxs-lookup"><span data-stu-id="1e460-177">**Apply the Safe Attachments detection response if scanning can't complete (timeout or errors)**: The action specified by **Safe Attachments unknown malware response** is taken on messages even when Safe Attachments scanning can't complete.</span></span> <span data-ttu-id="1e460-178">Wenn Sie diese Option ausgewählt haben, wählen Sie immer **Umleitung aktivieren** aus, und geben Sie eine E-Mail-Adresse an, um Nachrichten zu senden, die Schadsoftwareanlagen enthalten.</span><span class="sxs-lookup"><span data-stu-id="1e460-178">If you selected this option, always select **Enable redirect** and specify an email address to send messages that contain malware attachments.</span></span> <span data-ttu-id="1e460-179">Andernfalls können Nachrichten verloren gegangen sein.</span><span class="sxs-lookup"><span data-stu-id="1e460-179">Otherwise, messages might be lost.</span></span>

   <span data-ttu-id="1e460-180">Wenn Sie fertig sind, klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="1e460-180">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="1e460-181">Überprüfen Sie auf der angezeigten Seite **Überprüfung** Ihre Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="1e460-181">On the **Review** page that appears, review your settings.</span></span> <span data-ttu-id="1e460-182">Sie können in jedem Abschnitt **Bearbeiten** auswählen, um die Einstellungen in diesem Abschnitt zu ändern.</span><span class="sxs-lookup"><span data-stu-id="1e460-182">You can select **Edit** in each section to modify the settings within the section.</span></span> <span data-ttu-id="1e460-183">Alternativ können Sie auf **Zurück** klicken oder die entsprechende Seite im Assistenten auswählen.</span><span class="sxs-lookup"><span data-stu-id="1e460-183">Or you can click **Back** or select the specific page in the wizard.</span></span>

   <span data-ttu-id="1e460-184">Klicken Sie nach Abschluss des Vorgangs auf **Senden**.</span><span class="sxs-lookup"><span data-stu-id="1e460-184">When you're finished, click **Submit**.</span></span>

7. <span data-ttu-id="1e460-185">Klicken Sie in der angezeigten Bestätigungsseite auf **Fertig**.</span><span class="sxs-lookup"><span data-stu-id="1e460-185">On the confirmation page that appears, click **Done**.</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-view-safe-attachments-policies"></a><span data-ttu-id="1e460-186">Verwenden des Microsoft 365 Defender Portals zum Anzeigen Tresor Anlagenrichtlinien</span><span class="sxs-lookup"><span data-stu-id="1e460-186">Use the Microsoft 365 Defender portal to view Safe Attachments policies</span></span>

1. <span data-ttu-id="1e460-187">Wechseln Sie im Microsoft 365 Defender Portal zur Seite Richtlinien für **E-Mail-&** \> **Zusammenarbeitsrichtlinien & Richtlinien** für Die \> **Bedrohungsregeln** \>  Tresor \> **Anlagen.**</span><span class="sxs-lookup"><span data-stu-id="1e460-187">In the Microsoft 365 Defender portal, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** page \> **Policies** section \> **Safe Attachments**.</span></span>

2. <span data-ttu-id="1e460-188">Auf der Seite **Tresor Anlagen** werden die folgenden Eigenschaften in der Liste der Richtlinien angezeigt:</span><span class="sxs-lookup"><span data-stu-id="1e460-188">On the **Safe Attachments** page, the following properties are displayed in the list of policies:</span></span>
   - <span data-ttu-id="1e460-189">**Name**</span><span class="sxs-lookup"><span data-stu-id="1e460-189">**Name**</span></span>
   - <span data-ttu-id="1e460-190">**Status**</span><span class="sxs-lookup"><span data-stu-id="1e460-190">**Status**</span></span>
   - <span data-ttu-id="1e460-191">**Priorität**</span><span class="sxs-lookup"><span data-stu-id="1e460-191">**Priority**</span></span>

3. <span data-ttu-id="1e460-192">Wenn Sie eine Richtlinie auswählen, indem Sie auf den Namen klicken, werden die Richtlinieneinstellungen in einem Flyout angezeigt.</span><span class="sxs-lookup"><span data-stu-id="1e460-192">When you select a policy by clicking on the name, the policy settings are displayed in a flyout.</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-modify-safe-attachments-policies"></a><span data-ttu-id="1e460-193">Verwenden des Microsoft 365 Defender Portals zum Ändern Tresor Anlagenrichtlinien</span><span class="sxs-lookup"><span data-stu-id="1e460-193">Use the Microsoft 365 Defender portal to modify Safe Attachments policies</span></span>

1. <span data-ttu-id="1e460-194">Wechseln Sie im Microsoft 365 Defender Portal zur Seite Richtlinien für **E-Mail-&** \> **Zusammenarbeitsrichtlinien & Richtlinien** für Die \> **Bedrohungsregeln** \>  Tresor \> **Anlagen.**</span><span class="sxs-lookup"><span data-stu-id="1e460-194">In the Microsoft 365 Defender portal, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** page \> **Policies** section \> **Safe Attachments**.</span></span>

2. <span data-ttu-id="1e460-195">Wählen Sie auf der Seite **Tresor Anlagen** eine Richtlinie aus der Liste aus, indem Sie auf den Namen klicken.</span><span class="sxs-lookup"><span data-stu-id="1e460-195">On the **Safe Attachments** page, select a policy from the list by clicking on the name.</span></span>

3. <span data-ttu-id="1e460-196">Wählen Sie im angezeigten Flyout für die Richtliniendetails in jedem Abschnitt die Option **Bearbeiten** aus, um die Einstellungen innerhalb des Abschnitts zu ändern.</span><span class="sxs-lookup"><span data-stu-id="1e460-196">In the policy details flyout that appears, select **Edit** in each section to modify the settings within the section.</span></span> <span data-ttu-id="1e460-197">Weitere Informationen zu den Einstellungen finden Sie im Abschnitt ["Verwenden des Microsoft 365 Defender Portals zum Erstellen Tresor Anlagenrichtlinien"](#use-the-microsoft-365-defender-portal-to-create-safe-attachments-policies) weiter oben in diesem Artikel.</span><span class="sxs-lookup"><span data-stu-id="1e460-197">For more information about the settings, see the [Use the Microsoft 365 Defender portal to create Safe Attachments policies](#use-the-microsoft-365-defender-portal-to-create-safe-attachments-policies) section earlier in this article.</span></span>  

<span data-ttu-id="1e460-198">Informationen zum Aktivieren oder Deaktivieren einer Richtlinie oder zum Festlegen der Reihenfolge der Richtlinienpriorität finden Sie in den folgenden Abschnitten.</span><span class="sxs-lookup"><span data-stu-id="1e460-198">To enable or disable a policy or set the policy priority order, see the following sections.</span></span>

### <a name="enable-or-disable-safe-attachments-policies"></a><span data-ttu-id="1e460-199">Aktivieren oder Deaktivieren Tresor Anlagenrichtlinien</span><span class="sxs-lookup"><span data-stu-id="1e460-199">Enable or disable Safe Attachments policies</span></span>

1. <span data-ttu-id="1e460-200">Wechseln Sie im Microsoft 365 Defender Portal zur Seite Richtlinien für **E-Mail-&** \> **Zusammenarbeitsrichtlinien & Richtlinien** für Die \> **Bedrohungsregeln** \>  Tresor \> **Anlagen.**</span><span class="sxs-lookup"><span data-stu-id="1e460-200">In the Microsoft 365 Defender portal, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** page \> **Policies** section \> **Safe Attachments**.</span></span>

2. <span data-ttu-id="1e460-201">Wählen Sie auf der Seite **Tresor Anlagen** eine Richtlinie aus der Liste aus, indem Sie auf den Namen klicken.</span><span class="sxs-lookup"><span data-stu-id="1e460-201">On the **Safe Attachments** page, select a policy from the list by clicking on the name.</span></span>

3. <span data-ttu-id="1e460-202">Ganz oben im angezeigten Flyout der Richtliniendetails werden Sie einen der folgenden Werte sehen:</span><span class="sxs-lookup"><span data-stu-id="1e460-202">At the top of the policy details flyout that appears, you'll see one of the following values:</span></span>
   - <span data-ttu-id="1e460-203">**Richtlinie deaktiviert**: Um die Richtlinie zu aktivieren, klicken Sie auf ![Symbol „Aktivieren“](../../media/m365-cc-sc-turn-on-off-icon.png) **Aktivieren**.</span><span class="sxs-lookup"><span data-stu-id="1e460-203">**Policy off**: To turn on the policy, click ![Turn on icon](../../media/m365-cc-sc-turn-on-off-icon.png) **Turn on** .</span></span>
   - <span data-ttu-id="1e460-204">**Richtlinie aktiviert**: Um die Richtlinie zu deaktivieren, klicken Sie auf ![Symbol „Deaktivieren“](../../media/m365-cc-sc-turn-on-off-icon.png) **Deaktivieren**.</span><span class="sxs-lookup"><span data-stu-id="1e460-204">**Policy on**: To turn off the policy, click ![Turn off icon](../../media/m365-cc-sc-turn-on-off-icon.png) **Turn off**.</span></span>

4. <span data-ttu-id="1e460-205">Klicken Sie im angezeigten Bestätigungsdialog auf **Aktivieren** oder **Deaktivieren**.</span><span class="sxs-lookup"><span data-stu-id="1e460-205">In the confirmation dialog that appears, click **Turn on** or **Turn off**.</span></span>

5. <span data-ttu-id="1e460-206">Klicken Sie im Flyout der Richtliniendetails auf **Schließen**.</span><span class="sxs-lookup"><span data-stu-id="1e460-206">Click **Close** in the policy details flyout.</span></span>

<span data-ttu-id="1e460-207">Zurück auf der Richtlinien-Hauptseite wird der Wert **Status** der Richtlinie **Aktiviert** oder **Deaktiviert** sein.</span><span class="sxs-lookup"><span data-stu-id="1e460-207">Back on the main policy page, the **Status** value of the policy will be **On** or **Off**.</span></span>

### <a name="set-the-priority-of-safe-attachments-policies"></a><span data-ttu-id="1e460-208">Festlegen der Priorität von Tresor Anlagenrichtlinien</span><span class="sxs-lookup"><span data-stu-id="1e460-208">Set the priority of Safe Attachments policies</span></span>

<span data-ttu-id="1e460-209">Standardmäßig erhalten Tresor Anlagenrichtlinien eine Priorität, die auf der Reihenfolge basiert, in der sie erstellt wurden (neuere Richtlinien haben eine niedrigere Priorität als ältere Richtlinien).</span><span class="sxs-lookup"><span data-stu-id="1e460-209">By default, Safe Attachments policies are given a priority that's based on the order they were created in (newer policies are lower priority than older policies).</span></span> <span data-ttu-id="1e460-210">Eine niedrigere Prioritätsnummer gibt eine höhere Priorität für die Richtlinie an (0 ist die höchste), und Richtlinien werden in der Reihenfolge der Priorität verarbeitet (Richtlinien mit einer höheren Priorität werden vor Richtlinien mit einer niedrigeren Priorität verarbeitet).</span><span class="sxs-lookup"><span data-stu-id="1e460-210">A lower priority number indicates a higher priority for the policy (0 is the highest), and policies are processed in priority order (higher priority policies are processed before lower priority policies).</span></span> <span data-ttu-id="1e460-211">Keine zwei Richtlinien können die gleiche Priorität aufweisen, und die Richtlinienverarbeitung endet, nachdem die erste Richtlinie angewendet wurde.</span><span class="sxs-lookup"><span data-stu-id="1e460-211">No two policies can have the same priority, and policy processing stops after the first policy is applied.</span></span>

<span data-ttu-id="1e460-212">Weitere Informationen über die Prioritätsreihenfolge und darüber, wie mehrere Richtlinien ausgewertet und angewendet werden, finden Sie unter [Reihenfolge und Priorität beim E-Mail-Schutz](how-policies-and-protections-are-combined.md).</span><span class="sxs-lookup"><span data-stu-id="1e460-212">For more information about the order of precedence and how multiple policies are evaluated and applied, see [Order and precedence of email protection](how-policies-and-protections-are-combined.md).</span></span>

<span data-ttu-id="1e460-213">Tresor Anlagenrichtlinien werden in der Reihenfolge angezeigt, in der sie verarbeitet werden (die erste Richtlinie hat den **Prioritätswert** 0).</span><span class="sxs-lookup"><span data-stu-id="1e460-213">Safe Attachments policies are displayed in the order they're processed (the first policy has the **Priority** value 0).</span></span>

<span data-ttu-id="1e460-214">**Hinweis:** Im Microsoft 365 Defender Portal können Sie die Priorität der Richtlinie Tresor Anlagen erst ändern, nachdem Sie sie erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="1e460-214">**Note**: In the Microsoft 365 Defender portal, you can only change the priority of the Safe Attachments policy after you create it.</span></span> <span data-ttu-id="1e460-215">In PowerShell können Sie die Standardpriorität überschreiben, wenn Sie die Regel für sichere Anlagen erstellen (was sich auf die Priorität vorhandener Regeln auswirken kann).</span><span class="sxs-lookup"><span data-stu-id="1e460-215">In PowerShell, you can override the default priority when you create the safe attachment rule (which can affect the priority of existing rules).</span></span>

<span data-ttu-id="1e460-216">Um die Priorität einer Richtlinie zu ändern, klicken Sie in den Eigenschaften einer Richtlinie auf **Priorität erhöhen** oder **Priorität verringern** (Sie können den Zahlenwert der **Priorität** im Microsoft 365 Defender-Portal nicht direkt modifizieren).</span><span class="sxs-lookup"><span data-stu-id="1e460-216">To change the priority of a policy, you click **Increase priority** or **Decrease priority** in the properties of the policy (you can't directly modify the **Priority** number in the Microsoft 365 Defender portal).</span></span> <span data-ttu-id="1e460-217">Die Priorität einer Richtlinie zu verändern macht nur Sinn, wenn Sie mehrere Richtlinien haben.</span><span class="sxs-lookup"><span data-stu-id="1e460-217">Changing the priority of a policy only makes sense if you have multiple policies.</span></span>

1. <span data-ttu-id="1e460-218">Wechseln Sie im Portal Microsoft 365 Defender zur Seite Richtlinien für **E-Mail-&** \> **Zusammenarbeitsrichtlinien & Richtlinien** für \> **Bedrohungsregeln** \>  Tresor \> **Anlagen.**</span><span class="sxs-lookup"><span data-stu-id="1e460-218">In the Microsoft 365 Defender portal, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** page \> **Policies** section \> **Safe Attachments**.</span></span>

2. <span data-ttu-id="1e460-219">Wählen Sie auf der Seite **Tresor Anlagen** eine Richtlinie aus der Liste aus, indem Sie auf den Namen klicken.</span><span class="sxs-lookup"><span data-stu-id="1e460-219">On the **Safe Attachments** page, select a policy from the list by clicking on the name.</span></span>

3. <span data-ttu-id="1e460-220">Oben im angezeigten Flyout für Richtliniendetails wird angezeigt, wie Sie die **Priorität** erhöhen oder **verringern,** basierend auf dem aktuellen Prioritätswert und der Anzahl der Richtlinien:</span><span class="sxs-lookup"><span data-stu-id="1e460-220">At the top of the policy details flyout that appears, you'll see **Increase priority** or **Decrease priority** based on the current priority value and the number of policies:</span></span>
   - <span data-ttu-id="1e460-221">Für die Richtlinie mit dem **Prioritätswert** **0** ist nur die Option **"Priorität verringern"** verfügbar.</span><span class="sxs-lookup"><span data-stu-id="1e460-221">The policy with the **Priority** value **0** has only the **Decrease priority** option available.</span></span>
   - <span data-ttu-id="1e460-222">Für die Richtlinie mit dem niedrigsten **Prioritätswert** (z. B. **3)** ist nur die Option **"Priorität erhöhen"** verfügbar.</span><span class="sxs-lookup"><span data-stu-id="1e460-222">The policy with the lowest **Priority** value (for example, **3**) has only the **Increase priority** option available.</span></span>
   - <span data-ttu-id="1e460-223">Wenn Sie über drei oder mehr Richtlinien verfügen, stehen für die Richtlinien zwischen den Werten mit der höchsten und der niedrigsten Priorität die Optionen **"Priorität erhöhen"** und **"Verringern"** zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="1e460-223">If you have three or more policies, the policies between the highest and lowest priority values have both the **Increase priority** and **Decrease priority** options available.</span></span>

   <span data-ttu-id="1e460-224">Klicken Sie auf ![Symbol „Priorität erhöhen“](../../media/m365-cc-sc-increase-icon.png) **Priorität erhöhen** oder ![Symbol „Priorität verringern“](../../media/m365-cc-sc-decrease-icon.png) **Priorität verringern**, um den **Prioritätswert** zu ändern.</span><span class="sxs-lookup"><span data-stu-id="1e460-224">Click ![Increase priority icon](../../media/m365-cc-sc-increase-icon.png) **Increase priority** or ![Decrease priority icon](../../media/m365-cc-sc-decrease-icon.png) **Decrease priority** to change the **Priority** value.</span></span>

4. <span data-ttu-id="1e460-225">Wenn Sie den Vorgang abgeschlossen haben, klicken Sie im Flyout der Richtliniendetails auf **Schließen**.</span><span class="sxs-lookup"><span data-stu-id="1e460-225">When you're finished, click **Close** in the policy details flyout.</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-remove-safe-attachments-policies"></a><span data-ttu-id="1e460-226">Verwenden des Microsoft 365 Defender Portals zum Entfernen Tresor Anlagenrichtlinien</span><span class="sxs-lookup"><span data-stu-id="1e460-226">Use the Microsoft 365 Defender portal to remove Safe Attachments policies</span></span>

1. <span data-ttu-id="1e460-227">Wechseln Sie im Portal Microsoft 365 Defender zur Seite Richtlinien für **E-Mail-&** \> **Zusammenarbeitsrichtlinien & Richtlinien** für \> **Bedrohungsregeln** \>  Tresor \> **Anlagen.**</span><span class="sxs-lookup"><span data-stu-id="1e460-227">In the Microsoft 365 Defender portal, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** page \> **Policies** section \> **Safe Attachments**.</span></span>

2. <span data-ttu-id="1e460-228">Wählen Sie auf der Seite **Tresor Anlagen** eine benutzerdefinierte Richtlinie aus der Liste aus, indem Sie auf den Namen der Richtlinie klicken.</span><span class="sxs-lookup"><span data-stu-id="1e460-228">On the **Safe Attachments** page, select a custom policy from the list by clicking on the name of the policy.</span></span>

3. <span data-ttu-id="1e460-229">Ganz oben auf dem angezeigten Flyout der Richtliniendetails klicken Sie auf ![Symbol „Weiter Aktionen“](../../media/m365-cc-sc-more-actions-icon.png) **Weitere Aktionen** \> ![Symbol „Richtlinie löschen“](../../media/m365-cc-sc-delete-icon.png) **Richtlinie löschen**.</span><span class="sxs-lookup"><span data-stu-id="1e460-229">At the top of the policy details flyout that appears, click ![More actions icon](../../media/m365-cc-sc-more-actions-icon.png) **More actions** \> ![Delete policy icon](../../media/m365-cc-sc-delete-icon.png) **Delete policy**.</span></span>

4. <span data-ttu-id="1e460-230&quot;>Klicken Sie im angezeigten Bestätigungsdialog auf **Ja**.</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;1e460-230&quot;>In the confirmation dialog that appears, click **Yes**.</span></span>

## <a name=&quot;use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-attachments-policies&quot;></a><span data-ttu-id=&quot;1e460-231&quot;>Verwenden Exchange Online PowerShell oder der eigenständigen EOP PowerShell zum Konfigurieren Tresor Anlagenrichtlinien</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;1e460-231&quot;>Use Exchange Online PowerShell or standalone EOP PowerShell to configure Safe Attachments policies</span></span>

<span data-ttu-id=&quot;1e460-232&quot;>Wie zuvor beschrieben besteht eine richtlinie für Tresor Anlagen aus einer Richtlinie für sichere Anlagen und einer Regel für sichere Anlagen.</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;1e460-232&quot;>As previously described, a Safe Attachments policy consists of a safe attachment policy and a safe attachment rule.</span></span>

<span data-ttu-id=&quot;1e460-233&quot;>In PowerShell ist der Unterschied zwischen Richtlinien für sichere Anlagen und Regeln für sichere Anlagen offensichtlich.</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;1e460-233&quot;>In PowerShell, the difference between safe attachment policies and safe attachment rules is apparent.</span></span> <span data-ttu-id=&quot;1e460-234&quot;>Sie verwalten Richtlinien für sichere Anlagen mithilfe der Cmdlets **\* &quot;-SafeAttachmentPolicy&quot;,** und Sie verwalten Regeln für sichere Anlagen mithilfe der Cmdlets **\* &quot;-SafeAttachmentRule&quot;.**</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;1e460-234&quot;>You manage safe attachment policies by using the **\*-SafeAttachmentPolicy** cmdlets, and you manage safe attachment rules by using the **\*-SafeAttachmentRule** cmdlets.</span></span>

- <span data-ttu-id=&quot;1e460-235&quot;>In PowerShell erstellen Sie zuerst die Richtlinie für sichere Anlagen und dann die Regel für sichere Anlagen, die die Richtlinie identifiziert, für die die Regel gilt.</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;1e460-235&quot;>In PowerShell, you create the safe attachment policy first, then you create the safe attachment rule that identifies the policy that the rule applies to.</span></span>
- <span data-ttu-id=&quot;1e460-236&quot;>In PowerShell ändern Sie die Einstellungen in der Richtlinie für sichere Anlagen und die Regel für sichere Anlagen separat.</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;1e460-236&quot;>In PowerShell, you modify the settings in the safe attachment policy and the safe attachment rule separately.</span></span>
- <span data-ttu-id=&quot;1e460-237&quot;>Wenn Sie eine Richtlinie für sichere Anlagen aus PowerShell entfernen, wird die entsprechende Regel für sichere Anlagen nicht automatisch entfernt und umgekehrt.</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;1e460-237&quot;>When you remove a safe attachment policy from PowerShell, the corresponding safe attachment rule isn't automatically removed, and vice versa.</span></span>

### <a name=&quot;use-powershell-to-create-safe-attachments-policies&quot;></a><span data-ttu-id=&quot;1e460-238&quot;>Verwenden von PowerShell zum Erstellen Tresor Anlagenrichtlinien</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;1e460-238&quot;>Use PowerShell to create Safe Attachments policies</span></span>

<span data-ttu-id=&quot;1e460-239&quot;>Das Erstellen einer Tresor Anlagenrichtlinie in PowerShell besteht aus zwei Schritten:</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;1e460-239&quot;>Creating a Safe Attachments policy in PowerShell is a two-step process:</span></span>

1. <span data-ttu-id=&quot;1e460-240&quot;>Erstellen Sie die Richtlinie für sichere Anlagen.</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;1e460-240&quot;>Create the safe attachment policy.</span></span>
2. <span data-ttu-id=&quot;1e460-241&quot;>Erstellen Sie die Regel für sichere Anlagen, die die Richtlinie für sichere Anlagen angibt, auf die die Regel angewendet wird.</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;1e460-241&quot;>Create the safe attachment rule that specifies the safe attachment policy that the rule applies to.</span></span>

 <span data-ttu-id=&quot;1e460-242&quot;>**Hinweise**:</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;1e460-242&quot;>**Notes**:</span></span>

- <span data-ttu-id=&quot;1e460-243&quot;>Sie können eine neue Regel für sichere Anlagen erstellen und ihr eine vorhandene, nicht zugeordnete Richtlinie für sichere Anlagen zuweisen.</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;1e460-243&quot;>You can create a new safe attachment rule and assign an existing, unassociated safe attachment policy to it.</span></span> <span data-ttu-id=&quot;1e460-244&quot;>Eine Regel für sichere Anlagen kann nicht mehr als einer Richtlinie für sichere Anlagen zugeordnet werden.</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;1e460-244&quot;>A safe attachment rule can't be associated with more than one safe attachment policy.</span></span>

- <span data-ttu-id=&quot;1e460-245&quot;>Sie können die folgenden Einstellungen für neue Richtlinien für sichere Anlagen in PowerShell konfigurieren, die erst nach dem Erstellen der Richtlinie im Microsoft 365 Defender Portal verfügbar sind:</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;1e460-245&quot;>You can configure the following settings on new safe attachment policies in PowerShell that aren't available in the Microsoft 365 Defender portal until after you create the policy:</span></span>
  - <span data-ttu-id=&quot;1e460-246&quot;>Erstellen Sie die neue Richtlinie als deaktiviert _(aktiviert_ `$false` im Cmdlet **&quot;New-SafeAttachmentRule").**</span><span class="sxs-lookup"><span data-stu-id="1e460-246">Create the new policy as disabled (_Enabled_ `$false` on the **New-SafeAttachmentRule** cmdlet).</span></span>
  - <span data-ttu-id="1e460-247">Legen Sie die Priorität der Richtlinie während der Erstellung _(Priorität)_ _\<Number\>_ im Cmdlet **"New-SafeAttachmentRule"** fest.</span><span class="sxs-lookup"><span data-stu-id="1e460-247">Set the priority of the policy during creation (_Priority_ _\<Number\>_) on the **New-SafeAttachmentRule** cmdlet).</span></span>

- <span data-ttu-id="1e460-248">Eine neue Richtlinie für sichere Anlagen, die Sie in PowerShell erstellen, ist erst im Microsoft 365 Defender-Portal sichtbar, wenn Sie die Richtlinie einer Regel für sichere Anlagen zuweisen.</span><span class="sxs-lookup"><span data-stu-id="1e460-248">A new safe attachment policy that you create in PowerShell isn't visible in the Microsoft 365 Defender portal until you assign the policy to a safe attachment rule.</span></span>

#### <a name="step-1-use-powershell-to-create-a-safe-attachment-policy"></a><span data-ttu-id="1e460-249">Schritt 1: Verwenden von PowerShell zum Erstellen einer Richtlinie für sichere Anlagen</span><span class="sxs-lookup"><span data-stu-id="1e460-249">Step 1: Use PowerShell to create a safe attachment policy</span></span>

<span data-ttu-id="1e460-250">Verwenden Sie die folgende Syntax, um eine Richtlinie für sichere Anlagen zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="1e460-250">To create a safe attachment policy, use this syntax:</span></span>

```PowerShell
New-SafeAttachmentPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] [-Action <Allow | Block | Replace | DynamicDelivery>] [-Redirect <$true | $false>] [-RedirectAddress <SMTPEmailAddress>] [-ActionOnError <$true | $false>]
```

<span data-ttu-id="1e460-251">In diesem Beispiel wird eine Richtlinie für sichere Anlagen namens "Contoso All" mit den folgenden Werten erstellt:</span><span class="sxs-lookup"><span data-stu-id="1e460-251">This example creates a safe attachment policy named Contoso All with the following values:</span></span>

- <span data-ttu-id="1e460-252">Blockieren Sie Nachrichten, die gefunden werden, dass sie Schadsoftware enthalten, indem Tresor Dokumente scannen (der _Parameter "Action"_ wird nicht verwendet, und der Standardwert lautet `Block` ).</span><span class="sxs-lookup"><span data-stu-id="1e460-252">Block messages that are found to contain malware by Safe Documents scanning (we aren't using the _Action_ parameter, and the default value is `Block`).</span></span>
- <span data-ttu-id="1e460-253">Die Umleitung ist aktiviert, und Nachrichten, die Schadsoftware enthalten, werden zur Analyse und Untersuchung an sec-ops@contoso.com gesendet.</span><span class="sxs-lookup"><span data-stu-id="1e460-253">Redirection is enabled, and messages that are found to contain malware are sent to sec-ops@contoso.com for analysis and investigation.</span></span>
- <span data-ttu-id="1e460-254">Wenn Tresor Attachments-Überprüfung nicht verfügbar ist oder Fehler auftreten, übermitteln Sie die Nachricht nicht (wir verwenden den _Parameter ActionOnError_ nicht und der Standardwert lautet `$true` ).</span><span class="sxs-lookup"><span data-stu-id="1e460-254">If Safe Attachments scanning isn't available or encounters errors, don't deliver the message (we aren't using the _ActionOnError_ parameter, and the default value is `$true`).</span></span>

```PowerShell
New-SafeAttachmentPolicy -Name "Contoso All" -Redirect $true -RedirectAddress sec-ops@contoso.com
```

<span data-ttu-id="1e460-255">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [New-SafeAttachmentPolicy](/powershell/module/exchange/new-safeattachmentpolicy).</span><span class="sxs-lookup"><span data-stu-id="1e460-255">For detailed syntax and parameter information, see [New-SafeAttachmentPolicy](/powershell/module/exchange/new-safeattachmentpolicy).</span></span>

#### <a name="step-2-use-powershell-to-create-a-safe-attachment-rule"></a><span data-ttu-id="1e460-256">Schritt 2: Verwenden von PowerShell zum Erstellen einer Regel für sichere Anlagen</span><span class="sxs-lookup"><span data-stu-id="1e460-256">Step 2: Use PowerShell to create a safe attachment rule</span></span>

<span data-ttu-id="1e460-257">Verwenden Sie die folgende Syntax, um eine Regel für sichere Anlagen zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="1e460-257">To create a safe attachment rule, use this syntax:</span></span>

```PowerShell
New-SafeAttachmentRule -Name "<RuleName>" -SafeAttachmentPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"] [-Enabled <$true | $false>]
```

<span data-ttu-id="1e460-258">In diesem Beispiel wird eine Regel für sichere Anlagen mit dem Namen "Contoso All" mit den folgenden Bedingungen erstellt:</span><span class="sxs-lookup"><span data-stu-id="1e460-258">This example creates a safe attachment rule named Contoso All with the following conditions:</span></span>

- <span data-ttu-id="1e460-259">Die Regel ist der Richtlinie für sichere Anlagen mit dem Namen "Contoso All" zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="1e460-259">The rule is associated with the safe attachment policy named Contoso All.</span></span>
- <span data-ttu-id="1e460-260">Die Regel gilt für alle Empfänger in der contoso.com Domäne.</span><span class="sxs-lookup"><span data-stu-id="1e460-260">The rule applies to all recipients in the contoso.com domain.</span></span>
- <span data-ttu-id="1e460-261">Da der Parameter _"Priority"_ nicht verwendet wird, wird die Standardpriorität verwendet.</span><span class="sxs-lookup"><span data-stu-id="1e460-261">Because we aren't using the _Priority_ parameter, the default priority is used.</span></span>
- <span data-ttu-id="1e460-262">Die Regel ist aktiviert (wir verwenden nicht den Parameter _Enabled,_ und der Standardwert lautet `$true` ).</span><span class="sxs-lookup"><span data-stu-id="1e460-262">The rule is enabled (we aren't using the _Enabled_ parameter, and the default value is `$true`).</span></span>

```powershell
New-SafeAttachmentRule -Name "Contoso All" -SafeAttachmentPolicy "Contoso All" -RecipientDomainIs contoso.com
```

<span data-ttu-id="1e460-263">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [New-SafeAttachmentRule](/powershell/module/exchange/new-safeattachmentrule).</span><span class="sxs-lookup"><span data-stu-id="1e460-263">For detailed syntax and parameter information, see [New-SafeAttachmentRule](/powershell/module/exchange/new-safeattachmentrule).</span></span>

### <a name="use-powershell-to-view-safe-attachment-policies"></a><span data-ttu-id="1e460-264">Verwenden von PowerShell zum Anzeigen von Richtlinien für sichere Anlagen</span><span class="sxs-lookup"><span data-stu-id="1e460-264">Use PowerShell to view safe attachment policies</span></span>

<span data-ttu-id="1e460-265">Verwenden Sie die folgende Syntax, um vorhandene Richtlinien für sichere Anlagen anzuzeigen:</span><span class="sxs-lookup"><span data-stu-id="1e460-265">To view existing safe attachment policies, use the following syntax:</span></span>

```PowerShell
Get-SafeAttachmentPolicy [-Identity "<PolicyIdentity>"] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="1e460-266">In diesem Beispiel wird eine Zusammenfassungsliste aller Richtlinien für sichere Anlagen zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="1e460-266">This example returns a summary list of all safe attachment policies.</span></span>

```PowerShell
Get-SafeAttachmentPolicy
```

<span data-ttu-id="1e460-267">In diesem Beispiel werden detaillierte Informationen für die Richtlinie für sichere Anlagen namens Contoso Executives zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="1e460-267">This example returns detailed information for the safe attachment policy named Contoso Executives.</span></span>

```PowerShell
Get-SafeAttachmentPolicy -Identity "Contoso Executives" | Format-List
```

<span data-ttu-id="1e460-268">Ausführliche Informationen zu Syntax und Parametern finden Sie unter ["Get-SafeAttachmentPolicy".](/powershell/module/exchange/get-safeattachmentpolicy)</span><span class="sxs-lookup"><span data-stu-id="1e460-268">For detailed syntax and parameter information, see [Get-SafeAttachmentPolicy](/powershell/module/exchange/get-safeattachmentpolicy).</span></span>

### <a name="use-powershell-to-view-safe-attachment-rules"></a><span data-ttu-id="1e460-269">Verwenden von PowerShell zum Anzeigen von Regeln für sichere Anlagen</span><span class="sxs-lookup"><span data-stu-id="1e460-269">Use PowerShell to view safe attachment rules</span></span>

<span data-ttu-id="1e460-270">Verwenden Sie die folgende Syntax, um vorhandene Regeln für sichere Anlagen anzuzeigen:</span><span class="sxs-lookup"><span data-stu-id="1e460-270">To view existing safe attachment rules, use the following syntax:</span></span>

```PowerShell
Get-SafeAttachmentRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled>] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="1e460-271">In diesem Beispiel wird eine Zusammenfassungsliste aller Regeln für sichere Anlagen zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="1e460-271">This example returns a summary list of all safe attachment rules.</span></span>

```PowerShell
Get-SafeAttachmentRule
```

<span data-ttu-id="1e460-272">Führen Sie die folgenden Befehle aus, um die Liste nach aktivierten oder deaktivierten Regeln zu filtern:</span><span class="sxs-lookup"><span data-stu-id="1e460-272">To filter the list by enabled or disabled rules, run the following commands:</span></span>

```PowerShell
Get-SafeAttachmentRule -State Disabled
```

```PowerShell
Get-SafeAttachmentRule -State Enabled
```

<span data-ttu-id="1e460-273">In diesem Beispiel werden detaillierte Informationen für die Regel für sichere Anlagen mit dem Namen "Contoso Executives" zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="1e460-273">This example returns detailed information for the safe attachment rule named Contoso Executives.</span></span>

```PowerShell
Get-SafeAttachmentRule -Identity "Contoso Executives" | Format-List
```

<span data-ttu-id="1e460-274">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Get-SafeAttachmentRule](/powershell/module/exchange/get-safeattachmentrule).</span><span class="sxs-lookup"><span data-stu-id="1e460-274">For detailed syntax and parameter information, see [Get-SafeAttachmentRule](/powershell/module/exchange/get-safeattachmentrule).</span></span>

### <a name="use-powershell-to-modify-safe-attachment-policies"></a><span data-ttu-id="1e460-275">Verwenden von PowerShell zum Ändern von Richtlinien für sichere Anlagen</span><span class="sxs-lookup"><span data-stu-id="1e460-275">Use PowerShell to modify safe attachment policies</span></span>

<span data-ttu-id="1e460-276">Sie können eine Richtlinie für sichere Anlagen in PowerShell nicht umbenennen (das Cmdlet **"Set-SafeAttachmentPolicy"** hat keinen _Name-Parameter)._</span><span class="sxs-lookup"><span data-stu-id="1e460-276">You can't rename a safe attachment policy in PowerShell (the **Set-SafeAttachmentPolicy** cmdlet has no _Name_ parameter).</span></span> <span data-ttu-id="1e460-277">Wenn Sie eine Tresor Anlagenrichtlinie im Microsoft 365 Defender-Portal umbenennen, werden Sie nur die _Regel für_ sichere Anlagen umbenennen.</span><span class="sxs-lookup"><span data-stu-id="1e460-277">When you rename a Safe Attachments policy in the Microsoft 365 Defender portal, you're only renaming the safe attachment _rule_.</span></span>

<span data-ttu-id="1e460-278">Andernfalls sind die gleichen Einstellungen verfügbar, wenn Sie eine Richtlinie für sichere Anlagen erstellen, wie im [Abschnitt "Schritt 1: Verwenden von PowerShell zum Erstellen einer Richtlinie für sichere Anlagen"](#step-1-use-powershell-to-create-a-safe-attachment-policy) weiter oben in diesem Artikel beschrieben.</span><span class="sxs-lookup"><span data-stu-id="1e460-278">Otherwise, the same settings are available when you create a safe attachment policy as described in the [Step 1: Use PowerShell to create a safe attachment policy](#step-1-use-powershell-to-create-a-safe-attachment-policy) section earlier in this article.</span></span>

<span data-ttu-id="1e460-279">Verwenden Sie die folgende Syntax, um eine Richtlinie für sichere Anlagen zu ändern:</span><span class="sxs-lookup"><span data-stu-id="1e460-279">To modify a safe attachment policy, use this syntax:</span></span>

```PowerShell
Set-SafeAttachmentPolicy -Identity "<PolicyName>" <Settings>
```

<span data-ttu-id="1e460-280">Ausführliche Informationen zu Syntax und Parametern finden Sie unter ["Set-SafeAttachmentPolicy".](/powershell/module/exchange/set-safeattachmentpolicy)</span><span class="sxs-lookup"><span data-stu-id="1e460-280">For detailed syntax and parameter information, see [Set-SafeAttachmentPolicy](/powershell/module/exchange/set-safeattachmentpolicy).</span></span>

### <a name="use-powershell-to-modify-safe-attachment-rules"></a><span data-ttu-id="1e460-281">Verwenden von PowerShell zum Ändern von Regeln für sichere Anlagen</span><span class="sxs-lookup"><span data-stu-id="1e460-281">Use PowerShell to modify safe attachment rules</span></span>

<span data-ttu-id="1e460-282">Die einzige Einstellung, die beim Ändern einer Regel für sichere Anlagen in PowerShell nicht verfügbar ist, ist der _Parameter "Enabled",_ mit dem Sie eine deaktivierte Regel erstellen können.</span><span class="sxs-lookup"><span data-stu-id="1e460-282">The only setting that's not available when you modify a safe attachment rule in PowerShell is the _Enabled_ parameter that allows you to create a disabled rule.</span></span> <span data-ttu-id="1e460-283">Informationen zum Aktivieren oder Deaktivieren vorhandener Regeln für sichere Anlagen finden Sie im nächsten Abschnitt.</span><span class="sxs-lookup"><span data-stu-id="1e460-283">To enable or disable existing safe attachment rules, see the next section.</span></span>

<span data-ttu-id="1e460-284">Andernfalls sind die gleichen Einstellungen verfügbar, wenn Sie eine Regel wie im [Abschnitt "Schritt 2: Verwenden von PowerShell zum Erstellen einer Regel](#step-2-use-powershell-to-create-a-safe-attachment-rule) für sichere Anlagen" weiter oben in diesem Artikel beschrieben erstellen.</span><span class="sxs-lookup"><span data-stu-id="1e460-284">Otherwise, the same settings are available when you create a rule as described in the [Step 2: Use PowerShell to create a safe attachment rule](#step-2-use-powershell-to-create-a-safe-attachment-rule) section earlier in this article.</span></span>

<span data-ttu-id="1e460-285">Verwenden Sie die folgende Syntax, um eine Regel für sichere Anlagen zu ändern:</span><span class="sxs-lookup"><span data-stu-id="1e460-285">To modify a safe attachment rule, use this syntax:</span></span>

```PowerShell
Set-SafeAttachmentRule -Identity "<RuleName>" <Settings>
```

<span data-ttu-id="1e460-286">Ausführliche Informationen zu Syntax und Parametern finden Sie unter ["Set-SafeAttachmentRule".](/powershell/module/exchange/set-safeattachmentrule)</span><span class="sxs-lookup"><span data-stu-id="1e460-286">For detailed syntax and parameter information, see [Set-SafeAttachmentRule](/powershell/module/exchange/set-safeattachmentrule).</span></span>

### <a name="use-powershell-to-enable-or-disable-safe-attachment-rules"></a><span data-ttu-id="1e460-287">Verwenden von PowerShell zum Aktivieren oder Deaktivieren von Regeln für sichere Anlagen</span><span class="sxs-lookup"><span data-stu-id="1e460-287">Use PowerShell to enable or disable safe attachment rules</span></span>

<span data-ttu-id="1e460-288">Das Aktivieren oder Deaktivieren einer Regel für sichere Anlagen in PowerShell aktiviert oder deaktiviert die gesamte Tresor Anlagenrichtlinie (die Regel für sichere Anlagen und die Richtlinie für zugewiesene sichere Anlagen).</span><span class="sxs-lookup"><span data-stu-id="1e460-288">Enabling or disabling a safe attachment rule in PowerShell enables or disables the whole Safe Attachments policy (the safe attachment rule and the assigned safe attachment policy).</span></span>

<span data-ttu-id="1e460-289">Verwenden Sie die folgende Syntax, um eine Regel für sichere Anlagen in PowerShell zu aktivieren oder zu deaktivieren:</span><span class="sxs-lookup"><span data-stu-id="1e460-289">To enable or disable a safe attachment rule in PowerShell, use this syntax:</span></span>

```PowerShell
<Enable-SafeAttachmentRule | Disable-SafeAttachmentRule> -Identity "<RuleName>"
```

<span data-ttu-id="1e460-290">In diesem Beispiel wird die Regel für sichere Anlagen mit dem Namen "Marketing Department" deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="1e460-290">This example disables the safe attachment rule named Marketing Department.</span></span>

```PowerShell
Disable-SafeAttachmentRule -Identity "Marketing Department"
```

<span data-ttu-id="1e460-291">In diesem Beispiel wird dieselbe Regel aktiviert.</span><span class="sxs-lookup"><span data-stu-id="1e460-291">This example enables same rule.</span></span>

```PowerShell
Enable-SafeAttachmentRule -Identity "Marketing Department"
```

<span data-ttu-id="1e460-292">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Enable-SafeAttachmentRule](/powershell/module/exchange/enable-safeattachmentrule) und [Disable-SafeAttachmentRule](/powershell/module/exchange/disable-safeattachmentrule).</span><span class="sxs-lookup"><span data-stu-id="1e460-292">For detailed syntax and parameter information, see [Enable-SafeAttachmentRule](/powershell/module/exchange/enable-safeattachmentrule) and [Disable-SafeAttachmentRule](/powershell/module/exchange/disable-safeattachmentrule).</span></span>

### <a name="use-powershell-to-set-the-priority-of-safe-attachment-rules"></a><span data-ttu-id="1e460-293">Verwenden von PowerShell zum Festlegen der Priorität von Regeln für sichere Anlagen</span><span class="sxs-lookup"><span data-stu-id="1e460-293">Use PowerShell to set the priority of safe attachment rules</span></span>

<span data-ttu-id="1e460-p126">Der höchste Prioritätswert, den Sie für eine Regel festlegen können, ist 0. Der niedrigste Wert, den Sie festlegen können, hängt von der Anzahl von Regeln ab. Wenn Sie z. B. fünf Regeln haben, können Sie die Prioritätswerte 0 bis 4 verwenden. Das Ändern der Priorität einer vorhandenen Regel kann sich entsprechend auf andere Regeln auswirken. Wenn Sie z. B. fünf benutzerdefinierte Regeln haben (Priorität 0 bis 4) und die Priorität einer Regel in 2 ändern, erhält die vorhandene Regel mit Priorität 2 die Priorität 3, und die Regel mit Priorität 3 erhält Priorität 4.</span><span class="sxs-lookup"><span data-stu-id="1e460-p126">The highest priority value you can set on a rule is 0. The lowest value you can set depends on the number of rules. For example, if you have five rules, you can use the priority values 0 through 4. Changing the priority of an existing rule can have a cascading effect on other rules. For example, if you have five custom rules (priorities 0 through 4), and you change the priority of a rule to 2, the existing rule with priority 2 is changed to priority 3, and the rule with priority 3 is changed to priority 4.</span></span>

<span data-ttu-id="1e460-299">Verwenden Sie die folgende Syntax, um die Priorität einer Regel für sichere Anlagen in PowerShell festzulegen:</span><span class="sxs-lookup"><span data-stu-id="1e460-299">To set the priority of a safe attachment rule in PowerShell, use the following syntax:</span></span>

```PowerShell
Set-SafeAttachmentRule -Identity "<RuleName>" -Priority <Number>
```

<span data-ttu-id="1e460-p127">In diesem Beispiel wird die Priorität der Regel namens „Marketing Department“ auf 2 festgelegt. Alle vorhandenen Regeln mit Priorität kleiner oder gleich 2 werden um 1 verringert (die Prioritätswerte werden um 1 erhöht).</span><span class="sxs-lookup"><span data-stu-id="1e460-p127">This example sets the priority of the rule named Marketing Department to 2. All existing rules that have a priority less than or equal to 2 are decreased by 1 (their priority numbers are increased by 1).</span></span>

```PowerShell
Set-SafeAttachmentRule -Identity "Marketing Department" -Priority 2
```

<span data-ttu-id="1e460-302">**Hinweis:** Um die Priorität einer neuen Regel beim Erstellen festzulegen, verwenden Sie stattdessen den Parameter _"Priority"_ im Cmdlet **"New-SafeAttachmentRule".**</span><span class="sxs-lookup"><span data-stu-id="1e460-302">**Note**: To set the priority of a new rule when you create it, use the _Priority_ parameter on the **New-SafeAttachmentRule** cmdlet instead.</span></span>

<span data-ttu-id="1e460-303">Ausführliche Informationen zu Syntax und Parametern finden Sie unter ["Set-SafeAttachmentRule".](/powershell/module/exchange/set-safeattachmentrule)</span><span class="sxs-lookup"><span data-stu-id="1e460-303">For detailed syntax and parameter information, see [Set-SafeAttachmentRule](/powershell/module/exchange/set-safeattachmentrule).</span></span>

### <a name="use-powershell-to-remove-safe-attachment-policies"></a><span data-ttu-id="1e460-304">Verwenden von PowerShell zum Entfernen sicherer Anlagenrichtlinien</span><span class="sxs-lookup"><span data-stu-id="1e460-304">Use PowerShell to remove safe attachment policies</span></span>

<span data-ttu-id="1e460-305">Wenn Sie PowerShell zum Entfernen einer Richtlinie für sichere Anlagen verwenden, wird die entsprechende Regel für sichere Anlagen nicht entfernt.</span><span class="sxs-lookup"><span data-stu-id="1e460-305">When you use PowerShell to remove a safe attachment policy, the corresponding safe attachment rule isn't removed.</span></span>

<span data-ttu-id="1e460-306">Verwenden Sie die folgende Syntax, um eine Richtlinie für sichere Anlagen in PowerShell zu entfernen:</span><span class="sxs-lookup"><span data-stu-id="1e460-306">To remove a safe attachment policy in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-SafeAttachmentPolicy -Identity "<PolicyName>"
```

<span data-ttu-id="1e460-307">In diesem Beispiel wird die Richtlinie für sichere Anlagen mit dem Namen "Marketing Department" entfernt.</span><span class="sxs-lookup"><span data-stu-id="1e460-307">This example removes the safe attachment policy named Marketing Department.</span></span>

```PowerShell
Remove-SafeAttachmentPolicy -Identity "Marketing Department"
```

<span data-ttu-id="1e460-308">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Remove-SafeAttachmentPolicy](/powershell/module/exchange/remove-safeattachmentpolicy).</span><span class="sxs-lookup"><span data-stu-id="1e460-308">For detailed syntax and parameter information, see [Remove-SafeAttachmentPolicy](/powershell/module/exchange/remove-safeattachmentpolicy).</span></span>

### <a name="use-powershell-to-remove-safe-attachment-rules"></a><span data-ttu-id="1e460-309">Verwenden von PowerShell zum Entfernen von Regeln für sichere Anlagen</span><span class="sxs-lookup"><span data-stu-id="1e460-309">Use PowerShell to remove safe attachment rules</span></span>

<span data-ttu-id="1e460-310">Wenn Sie PowerShell zum Entfernen einer Regel für sichere Anlagen verwenden, wird die entsprechende Richtlinie für sichere Anlagen nicht entfernt.</span><span class="sxs-lookup"><span data-stu-id="1e460-310">When you use PowerShell to remove a safe attachment rule, the corresponding safe attachment policy isn't removed.</span></span>

<span data-ttu-id="1e460-311">Verwenden Sie die folgende Syntax, um eine Regel für sichere Anlagen in PowerShell zu entfernen:</span><span class="sxs-lookup"><span data-stu-id="1e460-311">To remove a safe attachment rule in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-SafeAttachmentRule -Identity "<PolicyName>"
```

<span data-ttu-id="1e460-312">In diesem Beispiel wird die Regel für sichere Anlagen mit dem Namen "Marketing Department" entfernt.</span><span class="sxs-lookup"><span data-stu-id="1e460-312">This example removes the safe attachment rule named Marketing Department.</span></span>

```PowerShell
Remove-SafeAttachmentRule -Identity "Marketing Department"
```

<span data-ttu-id="1e460-313">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Remove-SafeAttachmentRule](/powershell/module/exchange/remove-safeattachmentrule).</span><span class="sxs-lookup"><span data-stu-id="1e460-313">For detailed syntax and parameter information, see [Remove-SafeAttachmentRule](/powershell/module/exchange/remove-safeattachmentrule).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="1e460-314">Wie können Sie feststellen, dass diese Verfahren erfolgreich waren?</span><span class="sxs-lookup"><span data-stu-id="1e460-314">How do you know these procedures worked?</span></span>

<span data-ttu-id="1e460-315">Führen Sie einen der folgenden Schritte aus, um zu überprüfen, ob Sie Tresor Anlagenrichtlinien erfolgreich erstellt, geändert oder entfernt haben:</span><span class="sxs-lookup"><span data-stu-id="1e460-315">To verify that you've successfully created, modified, or removed Safe Attachments policies, do any of the following steps:</span></span>

- <span data-ttu-id="1e460-316">Wechseln Sie im Portal Microsoft 365 Defender zur Seite Richtlinien für **E-Mail-&** \> **Zusammenarbeitsrichtlinien & Richtlinien** für \> **Bedrohungsregeln** \>  Tresor \> **Anlagen.**</span><span class="sxs-lookup"><span data-stu-id="1e460-316">In the Microsoft 365 Defender portal, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** page \> **Policies** section \> **Safe Attachments**.</span></span> <span data-ttu-id="1e460-317">Überprüfen Sie die Liste der Richtlinien, ihre **Statuswerte** und ihre **Prioritätswerte.**</span><span class="sxs-lookup"><span data-stu-id="1e460-317">Verify the list of policies, their **Status** values, and their **Priority** values.</span></span> <span data-ttu-id="1e460-318">Um weitere Details anzuzeigen, wählen Sie die Richtlinie aus der Liste aus, indem Sie auf den Namen klicken, und zeigen Sie die Details im Flyout an.</span><span class="sxs-lookup"><span data-stu-id="1e460-318">To view more details, select the policy from the list by clicking on the name, and view the details in the fly out.</span></span>

- <span data-ttu-id="1e460-319">Ersetzen Sie in Exchange Online PowerShell oder Exchange Online Protection PowerShell \<Name\> durch den Namen der Richtlinie oder Regel, führen Sie den folgenden Befehl aus, und überprüfen Sie die Einstellungen:</span><span class="sxs-lookup"><span data-stu-id="1e460-319">In Exchange Online PowerShell or Exchange Online Protection PowerShell, replace \<Name\> with the name of the policy or rule, run the following command, and verify the settings:</span></span>

  ```PowerShell
  Get-SafeAttachmentPolicy -Identity "<Name>" | Format-List
  ```

  ```PowerShell
  Get-SafeAttachmentRule -Identity "<Name>" | Format-List
  ```

<span data-ttu-id="1e460-320">Um zu überprüfen, ob Tresor Anlagen Nachrichten überprüft, überprüfen Sie den verfügbaren Defender auf Office 365 Berichte.</span><span class="sxs-lookup"><span data-stu-id="1e460-320">To verify that Safe Attachments is scanning messages, check the available Defender for Office 365 reports.</span></span> <span data-ttu-id="1e460-321">Weitere Informationen finden Sie unter [Anzeigen von Berichten für Defender für Office 365](view-reports-for-mdo.md) und Verwenden von Explorer im Microsoft 365 Defender [Portal.](threat-explorer.md)</span><span class="sxs-lookup"><span data-stu-id="1e460-321">For more information, see [View reports for Defender for Office 365](view-reports-for-mdo.md) and [Use Explorer in the Microsoft 365 Defender portal](threat-explorer.md).</span></span>
