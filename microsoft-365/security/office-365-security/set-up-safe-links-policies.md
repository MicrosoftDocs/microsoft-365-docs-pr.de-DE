---
title: Einrichten Tresor Links-Richtlinien in Microsoft Defender für Office 365
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
description: Administratoren können erfahren, wie Sie Tresor Links-Richtlinien und globale Einstellungen für Tresor Links in Microsoft Defender für Office 365 anzeigen, erstellen, ändern und löschen.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: b4254d62cfa5844756392c00686e7b93c466d160
ms.sourcegitcommit: cd55fe6abe25b1e4f5fbe8295d3a99aebd97ce66
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/23/2021
ms.locfileid: "53082756"
---
# <a name="set-up-safe-links-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="fbe39-103">Einrichten Tresor Links-Richtlinien in Microsoft Defender für Office 365</span><span class="sxs-lookup"><span data-stu-id="fbe39-103">Set up Safe Links policies in Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="fbe39-104">**Gilt für**</span><span class="sxs-lookup"><span data-stu-id="fbe39-104">**Applies to**</span></span>
- [<span data-ttu-id="fbe39-105">Microsoft Defender für Office 365 Plan 1 und Plan 2</span><span class="sxs-lookup"><span data-stu-id="fbe39-105">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="fbe39-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="fbe39-106">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

> [!IMPORTANT]
> <span data-ttu-id="fbe39-107">Dieser Artikel richtet sich an Geschäftskunden, die über [Microsoft Defender für Office 365](defender-for-office-365.md) verfügen.</span><span class="sxs-lookup"><span data-stu-id="fbe39-107">This article is intended for business customers who have [Microsoft Defender for Office 365](defender-for-office-365.md).</span></span> <span data-ttu-id="fbe39-108">Wenn Sie ein Privatbenutzer sind, der nach Informationen zu Safelinks in Outlook sucht, finden Sie weitere Informationen unter [Advanced Outlook.com Security](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).</span><span class="sxs-lookup"><span data-stu-id="fbe39-108">If you are a home user looking for information about Safelinks in Outlook, see [Advanced Outlook.com security](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).</span></span>

<span data-ttu-id="fbe39-109">Tresor Links in [Microsoft Defender für Office 365](defender-for-office-365.md) bieten URL-Überprüfung eingehender E-Mail-Nachrichten im E-Mail-Fluss und Zeitpunkt der Klicküberprüfung von URLs und Links in E-Mail-Nachrichten und an anderen Speicherorten.</span><span class="sxs-lookup"><span data-stu-id="fbe39-109">Safe Links in [Microsoft Defender for Office 365](defender-for-office-365.md) provides URL scanning of inbound email messages in mail flow, and time of click verification of URLs and links in email messages and in other locations.</span></span> <span data-ttu-id="fbe39-110">Weitere Informationen finden Sie unter [Tresor Links in Microsoft Defender für Office 365](safe-links.md).</span><span class="sxs-lookup"><span data-stu-id="fbe39-110">For more information, see [Safe Links in Microsoft Defender for Office 365](safe-links.md).</span></span>

<span data-ttu-id="fbe39-111">Es gibt keine integrierte oder standardmäßige Richtlinie für Tresor Links.</span><span class="sxs-lookup"><span data-stu-id="fbe39-111">There's no built-in or default Safe Links policy.</span></span> <span data-ttu-id="fbe39-112">Um Tresor Links-Überprüfung von URLs zu erhalten, müssen Sie eine oder mehrere Tresor Linkrichtlinien erstellen, wie in diesem Artikel beschrieben.</span><span class="sxs-lookup"><span data-stu-id="fbe39-112">To get Safe Links scanning of URLs, you need to create one or more Safe Links policies as described in this article.</span></span>

> [!NOTE]
>
> <span data-ttu-id="fbe39-113">Sie konfigurieren die globalen Einstellungen für Tresor Links-Schutz **außerhalb** Tresor Links-Richtlinien.</span><span class="sxs-lookup"><span data-stu-id="fbe39-113">You configure the global settings for Safe Links protection **outside** of Safe Links policies.</span></span> <span data-ttu-id="fbe39-114">Anweisungen finden Sie unter [Konfigurieren globaler Einstellungen für Tresor Links in Microsoft Defender für Office 365.](configure-global-settings-for-safe-links.md)</span><span class="sxs-lookup"><span data-stu-id="fbe39-114">For instructions, see [Configure global settings for Safe Links in Microsoft Defender for Office 365](configure-global-settings-for-safe-links.md).</span></span>
>
> <span data-ttu-id="fbe39-115">Administratoren sollten die unterschiedlichen Konfigurationseinstellungen für Tresor Links berücksichtigen.</span><span class="sxs-lookup"><span data-stu-id="fbe39-115">Admins should consider the different configuration settings for Safe Links.</span></span> <span data-ttu-id="fbe39-116">Eine der verfügbaren Optionen besteht darin, Benutzerinformationen in Tresor Links einzuschließen.</span><span class="sxs-lookup"><span data-stu-id="fbe39-116">One of the available options is to include user identifiable information in Safe Links.</span></span> <span data-ttu-id="fbe39-117">Dieses Feature ermöglicht *es Sicherheitsteams,* potenzielle Benutzerkompromittierungen zu untersuchen, Korrekturmaßnahmen zu ergreifen und kostspielige Verstöße zu begrenzen.</span><span class="sxs-lookup"><span data-stu-id="fbe39-117">This feature enables *Security Ops teams* to investigate potential user compromise, take corrective action, and limit costly breaches.</span></span>

<span data-ttu-id="fbe39-118">Sie können Tresor Verknüpfungsrichtlinien im Microsoft 365 Defender-Portal oder in PowerShell konfigurieren (Exchange Online PowerShell für berechtigte Microsoft 365 Organisationen mit Postfächern in Exchange Online; eigenständige EOP PowerShell für Organisationen ohne Exchange Online Postfächer, aber mit Microsoft Defender für Office 365 Add-On-Abonnements).</span><span class="sxs-lookup"><span data-stu-id="fbe39-118">You can configure Safe Links policies in the Microsoft 365 Defender portal or in PowerShell (Exchange Online PowerShell for eligible Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes, but with Microsoft Defender for Office 365 add-on subscriptions).</span></span>

<span data-ttu-id="fbe39-119">Die grundlegenden Elemente einer Tresor Links-Richtlinie sind:</span><span class="sxs-lookup"><span data-stu-id="fbe39-119">The basic elements of a Safe Links policy are:</span></span>

- <span data-ttu-id="fbe39-120">Die Richtlinie für **sichere Links:** Aktivieren Sie Tresor Linksschutz, aktivieren Sie die URL-Überprüfung in Echtzeit, geben Sie an, ob auf den Abschluss der Echtzeitüberprüfung gewartet werden soll, bevor die Nachricht zuzustellen ist, aktivieren Sie die Überprüfung auf interne Nachrichten, geben Sie an, ob Benutzerklicks auf URLs nachverfolgen sollen, und geben Sie an, ob Benutzer auf die ursprüngliche URL klicken dürfen.</span><span class="sxs-lookup"><span data-stu-id="fbe39-120">**The safe links policy**: Turn on Safe Links protection, turn on real-time URL scanning, specify whether to wait for real-time scanning to complete before delivering the message, turn on scanning for internal messages, specify whether to track user clicks on URLs, and specify whether to allow users to click trough to the original URL.</span></span>
- <span data-ttu-id="fbe39-121">**Die Regel für sichere Verknüpfungen:** Gibt die Prioritäts- und Empfängerfilter an (für wen die Richtlinie gilt).</span><span class="sxs-lookup"><span data-stu-id="fbe39-121">**The safe links rule**: Specifies the priority and recipient filters (who the policy applies to).</span></span>

<span data-ttu-id="fbe39-122">Der Unterschied zwischen diesen beiden Elementen ist nicht offensichtlich, wenn Sie Tresor Links-Richtlinien im Microsoft 365 Defender-Portal verwalten:</span><span class="sxs-lookup"><span data-stu-id="fbe39-122">The difference between these two elements isn't obvious when you manage Safe Links polices in the Microsoft 365 Defender portal:</span></span>

- <span data-ttu-id="fbe39-123">Wenn Sie eine Tresor Verknüpfungsrichtlinie erstellen, erstellen Sie tatsächlich eine Regel für sichere Links und die zugehörige Richtlinie für sichere Links gleichzeitig mit demselben Namen für beide.</span><span class="sxs-lookup"><span data-stu-id="fbe39-123">When you create a Safe Links policy, you're actually creating a safe links rule and the associated safe links policy at the same time using the same name for both.</span></span>
- <span data-ttu-id="fbe39-124">Wenn Sie eine Tresor Verknüpfungsrichtlinie ändern, ändern Einstellungen im Zusammenhang mit Dem Namen, Priorität, aktiviert oder deaktiviert und Empfängerfilter die Regel für sichere Verknüpfungen.</span><span class="sxs-lookup"><span data-stu-id="fbe39-124">When you modify a Safe Links policy, settings related to the name, priority, enabled or disabled, and recipient filters modify the safe links rule.</span></span> <span data-ttu-id="fbe39-125">Alle anderen Einstellungen ändern die zugehörige Richtlinie für sichere Links.</span><span class="sxs-lookup"><span data-stu-id="fbe39-125">All other settings modify the associated safe links policy.</span></span>
- <span data-ttu-id="fbe39-126">Wenn Sie eine Tresor Verknüpfungsrichtlinie entfernen, werden die Regel für sichere Links und die zugehörige Richtlinie für sichere Links entfernt.</span><span class="sxs-lookup"><span data-stu-id="fbe39-126">When you remove a Safe Links policy, the safe links rule and the associated safe links policy are removed.</span></span>

<span data-ttu-id="fbe39-127">In Exchange Online PowerShell oder der eigenständigen EOP PowerShell verwalten Sie die Richtlinie und die Regel getrennt.</span><span class="sxs-lookup"><span data-stu-id="fbe39-127">In Exchange Online PowerShell or standalone EOP PowerShell, you manage the policy and the rule separately.</span></span> <span data-ttu-id="fbe39-128">Weitere Informationen finden Sie im Abschnitt ["Verwenden von Exchange Online PowerShell oder eigenständiger EOP PowerShell" zum Konfigurieren Tresor Richtlinien für Links](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-links-policies) weiter unten in diesem Artikel.</span><span class="sxs-lookup"><span data-stu-id="fbe39-128">For more information, see the [Use Exchange Online PowerShell or standalone EOP PowerShell to configure Safe Links policies](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-links-policies) section later in this article.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="fbe39-129">Was sollten Sie wissen, bevor Sie beginnen?</span><span class="sxs-lookup"><span data-stu-id="fbe39-129">What do you need to know before you begin?</span></span>

- <span data-ttu-id="fbe39-130">Sie öffnen das Microsoft 365 Defender-Portal unter <https://security.microsoft.com/>.</span><span class="sxs-lookup"><span data-stu-id="fbe39-130">You open the Microsoft 365 Defender portal at <https://security.microsoft.com/>.</span></span> <span data-ttu-id="fbe39-131">To go directly to the **Tresor Links** page, use <https://security.microsoft.com/safelinksv2> .</span><span class="sxs-lookup"><span data-stu-id="fbe39-131">To go directly to the **Safe Links** page, use <https://security.microsoft.com/safelinksv2>.</span></span>

- <span data-ttu-id="fbe39-132">Wie Sie eine Verbindung mit Exchange Online PowerShell herstellen, finden Sie unter [Herstellen einer Verbindung mit Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="fbe39-132">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="fbe39-133">Informationen zum Herstellen einer Verbindung mit dem eigenständigen Exchange Online Protection PowerShell finden Sie unter [Verbinden mit PowerShell in Exchange Online Protection](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="fbe39-133">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="fbe39-134">Bevor Sie die Verfahren in diesem Artikel ausführen können, müssen Ihnen Berechtigungen zugewiesen werden:</span><span class="sxs-lookup"><span data-stu-id="fbe39-134">You need to be assigned permissions before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="fbe39-135">Um Tresor Verknüpfungsrichtlinien zu erstellen, zu ändern und zu löschen, müssen Sie Mitglied der Rollengruppen **"Organisationsverwaltung"** oder **"Sicherheitsadministrator"** im Microsoft 365 Defender Portal **und** Mitglied der Rollengruppe **"Organisationsverwaltung"** in Exchange Online sein.</span><span class="sxs-lookup"><span data-stu-id="fbe39-135">To create, modify, and delete Safe Links policies, you need to be a member of the **Organization Management** or **Security Administrator** role groups in the Microsoft 365 Defender portal **and** a member of the **Organization Management** role group in Exchange Online.</span></span>
  - <span data-ttu-id="fbe39-136">Für den schreibgeschützten Zugriff auf Tresor Links-Richtlinien müssen Sie Mitglied der Rollengruppe **"Globaler Leser"** oder **"Sicherheitsleseberechtigter"** sein.</span><span class="sxs-lookup"><span data-stu-id="fbe39-136">For read-only access to Safe Links policies, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="fbe39-137">Weitere Informationen finden Sie unter ["Berechtigungen" im Microsoft 365 Defender-Portal](permissions-microsoft-365-security-center.md) und ["Berechtigungen" in Exchange Online.](/exchange/permissions-exo/permissions-exo)</span><span class="sxs-lookup"><span data-stu-id="fbe39-137">For more information, see [Permissions in the Microsoft 365 Defender portal](permissions-microsoft-365-security-center.md) and [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo).</span></span>

  > [!NOTE]
  >
  > - <span data-ttu-id="fbe39-138">Wenn Sie Benutzer zur entsprechenden Azure Active Directory Rolle im Microsoft 365 Admin Center hinzufügen, erhalten Benutzer die erforderlichen Berechtigungen im Microsoft 365 Defender-Portal _und_ Berechtigungen für andere Features in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="fbe39-138">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Microsoft 365 Defender portal _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="fbe39-139">Weitere Informationen finden Sie unter [Informationen zu Administratorrollen](../../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="fbe39-139">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  <span data-ttu-id="fbe39-140">.</span><span class="sxs-lookup"><span data-stu-id="fbe39-140">.</span></span> <span data-ttu-id="fbe39-141">– Die Rollengruppe **"Organisationsverwaltung nur anzeigen"** in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) bietet auch schreibgeschützten Zugriff auf das Feature.</span><span class="sxs-lookup"><span data-stu-id="fbe39-141">- The **View-Only Organization Management** role group in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

- <span data-ttu-id="fbe39-142">Unsere empfohlenen Einstellungen für Tresor Links-Richtlinien finden Sie unter [Tresor Links Policy Settings](recommended-settings-for-eop-and-office365.md#safe-links-policy-settings).</span><span class="sxs-lookup"><span data-stu-id="fbe39-142">For our recommended settings for Safe Links policies, see [Safe Links policy settings](recommended-settings-for-eop-and-office365.md#safe-links-policy-settings).</span></span>

- <span data-ttu-id="fbe39-143">Es kann bis zu 30 Minuten dauern, bis eine neue oder aktualisierte Richtlinie angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="fbe39-143">Allow up to 30 minutes for a new or updated policy to be applied.</span></span>

- <span data-ttu-id="fbe39-144">[Microsoft Defender werden kontinuierlich neue Features für Office 365 hinzugefügt.](defender-for-office-365.md#new-features-in-microsoft-defender-for-office-365)</span><span class="sxs-lookup"><span data-stu-id="fbe39-144">[New features are continually being added to Microsoft Defender for Office 365](defender-for-office-365.md#new-features-in-microsoft-defender-for-office-365).</span></span> <span data-ttu-id="fbe39-145">Wenn neue Features hinzugefügt werden, müssen Sie möglicherweise Anpassungen an Ihren vorhandenen Richtlinien für Tresor Links vornehmen.</span><span class="sxs-lookup"><span data-stu-id="fbe39-145">As new features are added, you may need to make adjustments to your existing Safe Links policies.</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-create-safe-links-policies"></a><span data-ttu-id="fbe39-146">Verwenden des Microsoft 365 Defender Portals zum Erstellen Tresor Verknüpfungsrichtlinien</span><span class="sxs-lookup"><span data-stu-id="fbe39-146">Use the Microsoft 365 Defender portal to create Safe Links policies</span></span>

<span data-ttu-id="fbe39-147">Beim Erstellen einer benutzerdefinierten richtlinie für Tresor Links im Microsoft 365 Defender Portal werden die Regel für sichere Links und die zugehörige Richtlinie für sichere Links gleichzeitig mit demselben Namen für beide erstellt.</span><span class="sxs-lookup"><span data-stu-id="fbe39-147">Creating a custom Safe Links policy in the Microsoft 365 Defender portal creates the safe links rule and the associated safe links policy at the same time using the same name for both.</span></span>

1. <span data-ttu-id="fbe39-148">Wechseln Sie im Portal Microsoft 365 Defender zu **Richtlinien & Richtlinien** für \>  \> **Bedrohungsrichtlinien** \> **Tresor Links.**</span><span class="sxs-lookup"><span data-stu-id="fbe39-148">In the Microsoft 365 Defender portal, go to **Policies & rules** \> **Threat Policies** \> **Policies** section \> **Safe Links**.</span></span>

2. <span data-ttu-id="fbe39-149">Klicken Sie auf der Seite **Tresor Links** auf das ![ Symbol ](../../media/m365-cc-sc-create-icon.png) **"Erstellen".**</span><span class="sxs-lookup"><span data-stu-id="fbe39-149">On the **Safe Links** page, click ![Create icon](../../media/m365-cc-sc-create-icon.png) **Create**.</span></span>

3. <span data-ttu-id="fbe39-150">Der Assistent **für neue Tresor Verknüpfungsrichtlinien** wird geöffnet.</span><span class="sxs-lookup"><span data-stu-id="fbe39-150">The **New Safe Links policy** wizard opens.</span></span> <span data-ttu-id="fbe39-151">Konfigurieren Sie auf der Seite **"Richtlinie benennen"** die folgenden Einstellungen:</span><span class="sxs-lookup"><span data-stu-id="fbe39-151">On the **Name your policy** page, configure the following settings:</span></span>

   - <span data-ttu-id="fbe39-152">**Name**: Geben Sie einen eindeutigen, aussagekräftigen Namen für die Richtlinie ein.</span><span class="sxs-lookup"><span data-stu-id="fbe39-152">**Name**: Enter a unique, descriptive name for the policy.</span></span>
   - <span data-ttu-id="fbe39-153">**Beschreibung**: Geben Sie eine optionale Beschreibung für die Richtlinie ein.</span><span class="sxs-lookup"><span data-stu-id="fbe39-153">**Description**: Enter an optional description for the policy.</span></span>

   <span data-ttu-id="fbe39-154">Wenn Sie fertig sind, klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="fbe39-154">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="fbe39-155">Identifizieren Sie auf der angezeigten Seite **"Benutzer und Domänen"** die internen Empfänger, für die die Richtlinie gilt (Empfängerbedingungen):</span><span class="sxs-lookup"><span data-stu-id="fbe39-155">On the **Users and domains** page that appears, identify the internal recipients that the policy applies to (recipient conditions):</span></span>
   - <span data-ttu-id="fbe39-156">**Benutzer**: Die angegebenen Postfächer, E-Mail-Benutzer oder E-Mail-Kontakte in Ihrer Organisation.</span><span class="sxs-lookup"><span data-stu-id="fbe39-156">**Users**: The specified mailboxes, mail users, or mail contacts in your organization.</span></span>
   - <span data-ttu-id="fbe39-157">**Gruppen**: Die angegebenen Verteilergruppen, E-Mail-aktivierten Sicherheitsgruppen oder Microsoft 365-Gruppen in Ihrer Organisation.</span><span class="sxs-lookup"><span data-stu-id="fbe39-157">**Groups**: The specified distribution groups, mail-enabled security groups, or Microsoft 365 Groups in your organization.</span></span>
   - <span data-ttu-id="fbe39-158">**Domänen**: Alle Empfänger in der angegebenen [akzeptierten Domäne](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) in Ihrer Organisation.</span><span class="sxs-lookup"><span data-stu-id="fbe39-158">**Domains**: All recipients in the specified [accepted domains](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) in your organization.</span></span>

   <span data-ttu-id="fbe39-159">Klicken Sie auf das entsprechende Feld, beginnen Sie mit der Eingabe eines Wertes, und wählen Sie den gewünschten Wert aus den Ergebnissen aus.</span><span class="sxs-lookup"><span data-stu-id="fbe39-159">Click in the appropriate box, start typing a value, and select the value that you want from the results.</span></span> <span data-ttu-id="fbe39-160">Wiederholen Sie diesen Vorgang so oft wie nötig.</span><span class="sxs-lookup"><span data-stu-id="fbe39-160">Repeat this process as many times as necessary.</span></span> <span data-ttu-id="fbe39-161">Um einen vorhandenen Wert zu entfernen, klicken Sie auf das</span><span class="sxs-lookup"><span data-stu-id="fbe39-161">To remove an existing value, click remove</span></span> ![Symbol „Entfernen“](../../media/m365-cc-sc-remove-selection-icon.png) <span data-ttu-id="fbe39-163">neben dem Wert.</span><span class="sxs-lookup"><span data-stu-id="fbe39-163">next to the value.</span></span>

   <span data-ttu-id="fbe39-164">Für Benutzer oder Gruppen können Sie die meisten Bezeichner verwenden (Name, Anzeigename, Alias, E-Mail-Adresse, Kontoname usw.), aber in den Ergebnissen wird der entsprechende Anzeigename angezeigt.</span><span class="sxs-lookup"><span data-stu-id="fbe39-164">For users or groups, you can use most identifiers (name, display name, alias, email address, account name, etc.), but the corresponding display name is shown in the results.</span></span> <span data-ttu-id="fbe39-165">Geben Sie für Benutzer einen einzelnen Stern (\*) ein, um alle verfügbaren Werte anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="fbe39-165">For users, enter an asterisk (\*) by itself to see all available values.</span></span>

   <span data-ttu-id="fbe39-166">Mehreren Werten in der gleichen Bedingung verwenden die „ODER“-Logik (z. B. _\<recipient1\>_ ODER _\<recipient2\>_).</span><span class="sxs-lookup"><span data-stu-id="fbe39-166">Multiple values in the same condition use OR logic (for example, _\<recipient1\>_ or _\<recipient2\>_).</span></span> <span data-ttu-id="fbe39-167">Unterschiedlichen Bedingungen verwenden die „UND“-Logik (z. B. _\<recipient1\>_ UND _\<member of group 1\>_).</span><span class="sxs-lookup"><span data-stu-id="fbe39-167">Different conditions use AND logic (for example, _\<recipient1\>_ and _\<member of group 1\>_).</span></span>

   - <span data-ttu-id="fbe39-168">**Ausschließen dieser Benutzer, Gruppen und Domänen**: Um Ausnahmen für die internen Empfänger hinzuzufügen, für welche die Richtlinie gilt (Empfängerausnahmen), wählen Sie diese Option und konfigurieren Sie die Ausnahmen.</span><span class="sxs-lookup"><span data-stu-id="fbe39-168">**Exclude these users, groups, and domains**: To add exceptions for the internal recipients that the policy applies to (recpient exceptions), select this option and configure the exceptions.</span></span> <span data-ttu-id="fbe39-169">Die Einstellungen und das Verhalten entsprechen genau den Bedingungen.</span><span class="sxs-lookup"><span data-stu-id="fbe39-169">The settings and behavior are exactly like the conditions.</span></span>

   <span data-ttu-id="fbe39-170">Wenn Sie fertig sind, klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="fbe39-170">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="fbe39-171">Konfigurieren Sie auf der angezeigten Seite **"Schutzeinstellungen"** die folgenden Einstellungen:</span><span class="sxs-lookup"><span data-stu-id="fbe39-171">On the **Protection settings** page that appears, configure the following settings:</span></span>
   - <span data-ttu-id="fbe39-172">**Wählen Sie die Aktion für unbekannte potenziell schädliche URLs in Nachrichten** aus: Aktivieren Sie **"Ein",** um Tresor Linksschutz für Links in E-Mail-Nachrichten zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="fbe39-172">**Select the action for unknown potentially malicious URLs in messages**: Select **On** to enable Safe Links protection for links in email messages.</span></span> <span data-ttu-id="fbe39-173">Wenn Sie diese Einstellung aktivieren, sind die folgenden Einstellungen verfügbar:</span><span class="sxs-lookup"><span data-stu-id="fbe39-173">If you turn this setting on, the following settings are available:</span></span>
     - <span data-ttu-id="fbe39-174">**Anwenden der Echtzeit-URL-Überprüfung auf verdächtige Links und Links, die auf Dateien verweisen:** Wählen Sie diese Option aus, um die Echtzeitüberprüfung von Links in E-Mail-Nachrichten zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="fbe39-174">**Apply real-time URL scanning for suspicious links and links that point to files**: Select this option to enable real-time scanning of links in email messages.</span></span> <span data-ttu-id="fbe39-175">Wenn Sie diese Einstellung aktivieren, ist folgende Einstellung verfügbar:</span><span class="sxs-lookup"><span data-stu-id="fbe39-175">If you turn this setting on the following setting is available:</span></span>
       - <span data-ttu-id="fbe39-176">**Warten Sie, bis die URL-Überprüfung abgeschlossen ist, bevor Sie die Nachricht übermitteln:** Wählen Sie diese Option aus, um auf den Abschluss der URL-Überprüfung in Echtzeit zu warten, bevor Sie die Nachricht übermitteln.</span><span class="sxs-lookup"><span data-stu-id="fbe39-176">**Wait for URL scanning to complete before delivering the message**: Select this option to wait for real-time URL scanning to complete before delivering the message.</span></span>
     - <span data-ttu-id="fbe39-177">**Anwenden Tresor Links auf E-Mail-Nachrichten, die innerhalb der Organisation gesendet werden:** Wählen Sie diese Option aus, um die Richtlinie Tresor Links auf Nachrichten zwischen internen Absendern und internen Empfängern anzuwenden.</span><span class="sxs-lookup"><span data-stu-id="fbe39-177">**Apply Safe Links to email messages sent within the organization**: Select this option to apply the Safe Links policy to messages between internal senders and internal recipients.</span></span>
   - <span data-ttu-id="fbe39-178">**Wählen Sie die Aktion für unbekannte oder potenziell schädliche URLs in Microsoft Teams** aus: Aktivieren Sie **"Ein",** um Tresor Linksschutz für Links in Teams zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="fbe39-178">**Select the action for unknown or potentially malicious URLs within Microsoft Teams**: Select **On** to enable Safe Links protection for links in Teams.</span></span>
   - <span data-ttu-id="fbe39-179">**Benutzerklicks nicht nachverfolgen:** Lassen Sie diese Einstellung deaktiviert, um das Nachverfolgen von Benutzerklicks auf URLs in E-Mail-Nachrichten zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="fbe39-179">**Do not track user clicks**: Leave this setting unselected to enable the tracking user clicks on URLs in email messages.</span></span>
   - <span data-ttu-id="fbe39-180">**Benutzer dürfen nicht zur ursprünglichen URL klicken:** Wählen Sie diese Option aus, um zu verhindern, dass Benutzer auf [Warnseiten](safe-links.md#warning-pages-from-safe-links)zur ursprünglichen URL klicken.</span><span class="sxs-lookup"><span data-stu-id="fbe39-180">**Do not allow users to click through to original URL**: Select this option to block users from clicking through to the original URL in [warning pages](safe-links.md#warning-pages-from-safe-links).</span></span>
   - <span data-ttu-id="fbe39-181">**Schreiben Sie die folgenden URLs nicht neu:** Ermöglicht den Zugriff auf die angegebenen URLs, die andernfalls durch Tresor Links blockiert würden.</span><span class="sxs-lookup"><span data-stu-id="fbe39-181">**Do not rewrite the following URLs**: Allows access the specified URLs that would otherwise be blocked by Safe Links.</span></span>

     <span data-ttu-id="fbe39-182">Geben Sie in das Feld die gewünschte URL oder den gewünschten Wert ein, und klicken Sie dann auf **"Hinzufügen".**</span><span class="sxs-lookup"><span data-stu-id="fbe39-182">In the box, type the URL or value that you want, and then click **Add**.</span></span> <span data-ttu-id="fbe39-183">Wiederholen Sie diesen Schritt so oft wie nötig.</span><span class="sxs-lookup"><span data-stu-id="fbe39-183">Repeat this step as many times as necessary.</span></span>

     <span data-ttu-id="fbe39-184">Um einen vorhandenen Eintrag zu entfernen, klicken Sie auf</span><span class="sxs-lookup"><span data-stu-id="fbe39-184">To remove an existing entry, click</span></span> ![Symbol „Entfernen“](../../media/m365-cc-sc-remove-selection-icon.png) <span data-ttu-id="fbe39-186">neben dem Eintrag.</span><span class="sxs-lookup"><span data-stu-id="fbe39-186">next to the entry.</span></span>

     <span data-ttu-id="fbe39-187">Informationen zur Eintragssyntax finden Sie unter [Eintragssyntax für die Liste "Die folgenden URLs nicht neu schreiben".](safe-links.md#entry-syntax-for-the-do-not-rewrite-the-following-urls-list)</span><span class="sxs-lookup"><span data-stu-id="fbe39-187">For entry syntax, see [Entry syntax for the "Do not rewrite the following URLs" list](safe-links.md#entry-syntax-for-the-do-not-rewrite-the-following-urls-list).</span></span>

   <span data-ttu-id="fbe39-188">Ausführliche Informationen zu diesen Einstellungen finden Sie unter [Tresor Links-Einstellungen für E-Mail-Nachrichten](safe-links.md#safe-links-settings-for-email-messages) und [Tresor Links-Einstellungen für Microsoft Teams](safe-links.md#safe-links-settings-for-microsoft-teams).</span><span class="sxs-lookup"><span data-stu-id="fbe39-188">For detailed information about these settings, see [Safe Links settings for email messages](safe-links.md#safe-links-settings-for-email-messages) and [Safe Links settings for Microsoft Teams](safe-links.md#safe-links-settings-for-microsoft-teams).</span></span>

   <span data-ttu-id="fbe39-189">Weitere informationen zu den empfohlenen Werten für Standard- und Strict-Richtlinieneinstellungen finden Sie unter [Tresor Links Policy Settings](recommended-settings-for-eop-and-office365.md#safe-links-policy-settings).</span><span class="sxs-lookup"><span data-stu-id="fbe39-189">For more the recommended values for Standard and Strict policy settings, see [Safe Links policy settings](recommended-settings-for-eop-and-office365.md#safe-links-policy-settings).</span></span>

   <span data-ttu-id="fbe39-190">Wenn Sie fertig sind, klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="fbe39-190">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="fbe39-191">Wählen Sie auf der **angezeigten Benachrichtigungsseite** einen der folgenden Werte **aus: Wie möchten Sie Ihre Benutzer benachrichtigen?**</span><span class="sxs-lookup"><span data-stu-id="fbe39-191">On the **Notification** page that appears, select one of the following values for **How would you like to notify your users?**:</span></span>
   - <span data-ttu-id="fbe39-192">**Verwenden des Standardmäßigen Benachrichtigungstexts**</span><span class="sxs-lookup"><span data-stu-id="fbe39-192">**Use the default notification text**</span></span>
   - <span data-ttu-id="fbe39-193">**Verwenden Sie benutzerdefinierten Benachrichtigungstext:** Wenn Sie diesen Wert auswählen, werden die folgenden Einstellungen angezeigt:</span><span class="sxs-lookup"><span data-stu-id="fbe39-193">**Use custom notification text**: If you select this value, the following settings appear:</span></span>
     - <span data-ttu-id="fbe39-194">**Verwenden von Microsoft Translator für die automatische Lokalisierung**</span><span class="sxs-lookup"><span data-stu-id="fbe39-194">**Use Microsoft Translator for automatic localization**</span></span>
     - <span data-ttu-id="fbe39-195">**Benutzerdefinierter Benachrichtigungstext:** Geben Sie den benutzerdefinierten Benachrichtigungstext in dieses Feld ein.</span><span class="sxs-lookup"><span data-stu-id="fbe39-195">**Custom notification text**: Enter the custom notification text in this box.</span></span>

   <span data-ttu-id="fbe39-196">Wenn Sie fertig sind, klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="fbe39-196">When you're finished, click **Next**.</span></span>

7. <span data-ttu-id="fbe39-197">Überprüfen Sie auf der angezeigten Seite **Überprüfung** Ihre Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="fbe39-197">On the **Review** page that appears, review your settings.</span></span> <span data-ttu-id="fbe39-198">Sie können in jedem Abschnitt **Bearbeiten** auswählen, um die Einstellungen in diesem Abschnitt zu ändern.</span><span class="sxs-lookup"><span data-stu-id="fbe39-198">You can select **Edit** in each section to modify the settings within the section.</span></span> <span data-ttu-id="fbe39-199">Alternativ können Sie auf **Zurück** klicken oder die entsprechende Seite im Assistenten auswählen.</span><span class="sxs-lookup"><span data-stu-id="fbe39-199">Or you can click **Back** or select the specific page in the wizard.</span></span>

   <span data-ttu-id="fbe39-200">Wenn Sie fertig sind, klicken Sie auf **"Absenden".**</span><span class="sxs-lookup"><span data-stu-id="fbe39-200">When you're finished, click **Submit**.</span></span>

8. <span data-ttu-id="fbe39-201">Klicken Sie in der angezeigten Bestätigungsseite auf **Fertig**.</span><span class="sxs-lookup"><span data-stu-id="fbe39-201">On the confirmation page that appears, click **Done**.</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-view-safe-links-policies"></a><span data-ttu-id="fbe39-202">Verwenden des Microsoft 365 Defender Portals zum Anzeigen Tresor Verknüpfungsrichtlinien</span><span class="sxs-lookup"><span data-stu-id="fbe39-202">Use the Microsoft 365 Defender portal to view Safe Links policies</span></span>

1. <span data-ttu-id="fbe39-203">Wechseln Sie im Portal Microsoft 365 Defender zu **Richtlinien & Richtlinien** für \>  \> **Bedrohungsrichtlinien** \> **Tresor Links.**</span><span class="sxs-lookup"><span data-stu-id="fbe39-203">In the Microsoft 365 Defender portal, go to **Policies & rules** \> **Threat Policies** \> **Policies** section \> **Safe Links**.</span></span>

2. <span data-ttu-id="fbe39-204">Auf der Seite **Tresor Links** werden die folgenden Eigenschaften in der Liste Tresor Verknüpfungsrichtlinien angezeigt:</span><span class="sxs-lookup"><span data-stu-id="fbe39-204">On the **Safe Links** page, the following properties are displayed in the list of Safe Links policies:</span></span>
   - <span data-ttu-id="fbe39-205">**Name**</span><span class="sxs-lookup"><span data-stu-id="fbe39-205">**Name**</span></span>
   - <span data-ttu-id="fbe39-206">**Status**</span><span class="sxs-lookup"><span data-stu-id="fbe39-206">**Status**</span></span>
   - <span data-ttu-id="fbe39-207">**Priorität**</span><span class="sxs-lookup"><span data-stu-id="fbe39-207">**Priority**</span></span>

3. <span data-ttu-id="fbe39-208">Wenn Sie eine Richtlinie auswählen, indem Sie auf den Namen klicken, werden die Richtlinieneinstellungen in einem Flyout angezeigt.</span><span class="sxs-lookup"><span data-stu-id="fbe39-208">When you select a policy by clicking on the name, the policy settings are displayed in a flyout.</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-modify-safe-links-policies"></a><span data-ttu-id="fbe39-209">Verwenden des Microsoft 365 Defender Portals zum Ändern Tresor Verknüpfungsrichtlinien</span><span class="sxs-lookup"><span data-stu-id="fbe39-209">Use the Microsoft 365 Defender portal to modify Safe Links policies</span></span>

1. <span data-ttu-id="fbe39-210">Wechseln Sie im Portal Microsoft 365 Defender zu **Richtlinien & Richtlinien** für \>  \> **Bedrohungsrichtlinien** \> **Tresor Links.**</span><span class="sxs-lookup"><span data-stu-id="fbe39-210">In the Microsoft 365 Defender portal, go to **Policies & rules** \> **Threat Policies** \> **Policies** section \> **Safe Links**.</span></span>

2. <span data-ttu-id="fbe39-211">Wählen Sie auf der Seite **Tresor Links** eine Richtlinie aus der Liste aus, indem Sie auf den Namen klicken.</span><span class="sxs-lookup"><span data-stu-id="fbe39-211">On the **Safe Links** page, select a policy from the list by clicking on the name.</span></span>

3. <span data-ttu-id="fbe39-212">Wählen Sie im angezeigten Flyout für die Richtliniendetails in jedem Abschnitt die Option **Bearbeiten** aus, um die Einstellungen innerhalb des Abschnitts zu ändern.</span><span class="sxs-lookup"><span data-stu-id="fbe39-212">In the policy details flyout that appears, select **Edit** in each section to modify the settings within the section.</span></span> <span data-ttu-id="fbe39-213">Weitere Informationen zu den Einstellungen finden Sie im vorherigen Abschnitt ["Verwenden des Microsoft 365 Defender-Portals zum Erstellen Tresor Verknüpfungsrichtlinien"](#use-the-microsoft-365-defender-portal-to-create-safe-links-policies) in diesem Artikel.</span><span class="sxs-lookup"><span data-stu-id="fbe39-213">For more information about the settings, see the previous [Use the Microsoft 365 Defender portal to create Safe Links policies](#use-the-microsoft-365-defender-portal-to-create-safe-links-policies) section in this article.</span></span>  

<span data-ttu-id="fbe39-214">Informationen zum Aktivieren oder Deaktivieren einer Richtlinie oder zum Festlegen der Reihenfolge der Richtlinienpriorität finden Sie in den folgenden Abschnitten.</span><span class="sxs-lookup"><span data-stu-id="fbe39-214">To enable or disable a policy or set the policy priority order, see the following sections.</span></span>

### <a name="enable-or-disable-safe-links-policies"></a><span data-ttu-id="fbe39-215">Aktivieren oder Deaktivieren Tresor Verknüpfungsrichtlinien</span><span class="sxs-lookup"><span data-stu-id="fbe39-215">Enable or disable Safe Links policies</span></span>

1. <span data-ttu-id="fbe39-216">Wechseln Sie im Portal Microsoft 365 Defender zu **E-Mail-& Richtlinien** für die Zusammenarbeit & Richtlinien für \> **Bedrohungsrichtlinien** für Regeln \>  \>  \> **Tresor Links.**</span><span class="sxs-lookup"><span data-stu-id="fbe39-216">In the Microsoft 365 Defender portal, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** \> **Policies** section \> **Safe Links**.</span></span>

2. <span data-ttu-id="fbe39-217">Wählen Sie auf der Seite **Tresor Links** eine Richtlinie aus der Liste aus, indem Sie auf den Namen klicken.</span><span class="sxs-lookup"><span data-stu-id="fbe39-217">On the **Safe Links** page, select a policy from the list by clicking on the name.</span></span>

3. <span data-ttu-id="fbe39-218">Ganz oben im angezeigten Flyout der Richtliniendetails werden Sie einen der folgenden Werte sehen:</span><span class="sxs-lookup"><span data-stu-id="fbe39-218">At the top of the policy details flyout that appears, you'll see one of the following values:</span></span>
   - <span data-ttu-id="fbe39-219">**Richtlinie deaktiviert**: Um die Richtlinie zu aktivieren, klicken Sie auf ![Symbol „Aktivieren“](../../media/m365-cc-sc-turn-on-off-icon.png) **Aktivieren**.</span><span class="sxs-lookup"><span data-stu-id="fbe39-219">**Policy off**: To turn on the policy, click ![Turn on icon](../../media/m365-cc-sc-turn-on-off-icon.png) **Turn on** .</span></span>
   - <span data-ttu-id="fbe39-220">**Richtlinie aktiviert**: Um die Richtlinie zu deaktivieren, klicken Sie auf ![Symbol „Deaktivieren“](../../media/m365-cc-sc-turn-on-off-icon.png) **Deaktivieren**.</span><span class="sxs-lookup"><span data-stu-id="fbe39-220">**Policy on**: To turn off the policy, click ![Turn off icon](../../media/m365-cc-sc-turn-on-off-icon.png) **Turn off**.</span></span>

4. <span data-ttu-id="fbe39-221">Klicken Sie im angezeigten Bestätigungsdialog auf **Aktivieren** oder **Deaktivieren**.</span><span class="sxs-lookup"><span data-stu-id="fbe39-221">In the confirmation dialog that appears, click **Turn on** or **Turn off**.</span></span>

5. <span data-ttu-id="fbe39-222">Klicken Sie im Flyout der Richtliniendetails auf **Schließen**.</span><span class="sxs-lookup"><span data-stu-id="fbe39-222">Click **Close** in the policy details flyout.</span></span>

<span data-ttu-id="fbe39-223">Zurück auf der Richtlinien-Hauptseite wird der Wert **Status** der Richtlinie **Aktiviert** oder **Deaktiviert** sein.</span><span class="sxs-lookup"><span data-stu-id="fbe39-223">Back on the main policy page, the **Status** value of the policy will be **On** or **Off**.</span></span>

### <a name="set-the-priority-of-safe-links-policies"></a><span data-ttu-id="fbe39-224">Festlegen der Priorität von Richtlinien für Tresor Links</span><span class="sxs-lookup"><span data-stu-id="fbe39-224">Set the priority of Safe Links policies</span></span>

<span data-ttu-id="fbe39-225">Standardmäßig erhalten Tresor Links eine Priorität, die auf der Reihenfolge basiert, in der sie erstellt wurden (neuere Richtlinien haben eine niedrigere Priorität als ältere Richtlinien).</span><span class="sxs-lookup"><span data-stu-id="fbe39-225">By default, Safe Links are given a priority that's based on the order they were created in (newer policies are lower priority than older policies).</span></span> <span data-ttu-id="fbe39-226">Eine niedrigere Prioritätsnummer gibt eine höhere Priorität für die Richtlinie an (0 ist die höchste), und Richtlinien werden in der Reihenfolge der Priorität verarbeitet (Richtlinien mit einer höheren Priorität werden vor Richtlinien mit einer niedrigeren Priorität verarbeitet).</span><span class="sxs-lookup"><span data-stu-id="fbe39-226">A lower priority number indicates a higher priority for the policy (0 is the highest), and policies are processed in priority order (higher priority policies are processed before lower priority policies).</span></span> <span data-ttu-id="fbe39-227">Keine zwei Richtlinien können die gleiche Priorität aufweisen, und die Richtlinienverarbeitung endet, nachdem die erste Richtlinie angewendet wurde.</span><span class="sxs-lookup"><span data-stu-id="fbe39-227">No two policies can have the same priority, and policy processing stops after the first policy is applied.</span></span>

<span data-ttu-id="fbe39-228">Um die Priorität einer Richtlinie zu ändern, klicken Sie in den Eigenschaften einer Richtlinie auf **Priorität erhöhen** oder **Priorität verringern** (Sie können den Zahlenwert der **Priorität** im Microsoft 365 Defender-Portal nicht direkt modifizieren).</span><span class="sxs-lookup"><span data-stu-id="fbe39-228">To change the priority of a policy, you click **Increase priority** or **Decrease priority** in the properties of the policy (you can't directly modify the **Priority** number in the Microsoft 365 Defender portal).</span></span> <span data-ttu-id="fbe39-229">Die Priorität einer Richtlinie zu verändern macht nur Sinn, wenn Sie mehrere Richtlinien haben.</span><span class="sxs-lookup"><span data-stu-id="fbe39-229">Changing the priority of a policy only makes sense if you have multiple policies.</span></span>

<span data-ttu-id="fbe39-230">**Hinweis**:</span><span class="sxs-lookup"><span data-stu-id="fbe39-230">**Note**:</span></span>

- <span data-ttu-id="fbe39-231">Im Microsoft 365 Defender Portal können Sie die Priorität der Richtlinie Tresor Links erst ändern, nachdem Sie sie erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="fbe39-231">In the Microsoft 365 Defender portal, you can only change the priority of the Safe Links policy after you create it.</span></span> <span data-ttu-id="fbe39-232">In PowerShell können Sie die Standardpriorität überschreiben, wenn Sie die Regel für sichere Verknüpfungen erstellen (was sich auf die Priorität vorhandener Regeln auswirken kann).</span><span class="sxs-lookup"><span data-stu-id="fbe39-232">In PowerShell, you can override the default priority when you create the safe links rule (which can affect the priority of existing rules).</span></span>
- <span data-ttu-id="fbe39-233">Tresor Verknüpfungsrichtlinien werden in der Reihenfolge verarbeitet, in der sie angezeigt werden (die erste Richtlinie hat den **Prioritätswert** 0).</span><span class="sxs-lookup"><span data-stu-id="fbe39-233">Safe Links policies are processed in the order that they're displayed (the first policy has the **Priority** value 0).</span></span> <span data-ttu-id="fbe39-234">Weitere Informationen über die Prioritätsreihenfolge und darüber, wie mehrere Richtlinien ausgewertet und angewendet werden, finden Sie unter [Reihenfolge und Priorität beim E-Mail-Schutz](how-policies-and-protections-are-combined.md).</span><span class="sxs-lookup"><span data-stu-id="fbe39-234">For more information about the order of precedence and how multiple policies are evaluated and applied, see [Order and precedence of email protection](how-policies-and-protections-are-combined.md).</span></span>

1. <span data-ttu-id="fbe39-235">Wechseln Sie im Portal Microsoft 365 Defender zu **E-Mail-& Richtlinien** für die Zusammenarbeit & Richtlinien für \> **Bedrohungsrichtlinien** für Regeln \>  \>  \> **Tresor Links.**</span><span class="sxs-lookup"><span data-stu-id="fbe39-235">In the Microsoft 365 Defender portal, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** \> **Policies** section \> **Safe Links**.</span></span>

2. <span data-ttu-id="fbe39-236">Wählen Sie auf der Seite **Tresor Links** eine Richtlinie aus der Liste aus, indem Sie auf den Namen klicken.</span><span class="sxs-lookup"><span data-stu-id="fbe39-236">On the **Safe Links** page, select a policy from the list by clicking on the name.</span></span>

3. <span data-ttu-id="fbe39-237">Ganz oben im angezeigten Flyout der Richtliniendetails werden Sie **Priorität erhöhen** oder **Priorität verringern** sehen, abhängig vom aktuellen Prioritätswert und der Anzahl der benutzerdefinierten Richtlinien:</span><span class="sxs-lookup"><span data-stu-id="fbe39-237">At the top of the policy details flyout that appears, you'll see **Increase priority** or **Decrease priority** based on the current priority value and the number of custom policies:</span></span>
   - <span data-ttu-id="fbe39-238">Für die Richtlinie mit dem **Prioritätswert** **0** ist nur die Option **"Priorität verringern"** verfügbar.</span><span class="sxs-lookup"><span data-stu-id="fbe39-238">The policy with the **Priority** value **0** has only the **Decrease priority** option available.</span></span>
   - <span data-ttu-id="fbe39-239">Für die Richtlinie mit dem niedrigsten **Prioritätswert** (z. B. **3)** ist nur die Option **"Priorität erhöhen"** verfügbar.</span><span class="sxs-lookup"><span data-stu-id="fbe39-239">The policy with the lowest **Priority** value (for example, **3**) has only the **Increase priority** option available.</span></span>
   - <span data-ttu-id="fbe39-240">Wenn Sie über drei oder mehr Richtlinien verfügen, stehen für die Richtlinien zwischen den Werten mit der höchsten und der niedrigsten Priorität die Optionen **"Priorität erhöhen"** und **"Verringern"** zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="fbe39-240">If you have three or more policies, the policies between the highest and lowest priority values have both the **Increase priority** and **Decrease priority** options available.</span></span>

   <span data-ttu-id="fbe39-241">Klicken Sie auf ![Symbol „Priorität erhöhen“](../../media/m365-cc-sc-increase-icon.png) **Priorität erhöhen** oder ![Symbol „Priorität verringern“](../../media/m365-cc-sc-decrease-icon.png) **Priorität verringern**, um den **Prioritätswert** zu ändern.</span><span class="sxs-lookup"><span data-stu-id="fbe39-241">Click ![Increase priority icon](../../media/m365-cc-sc-increase-icon.png) **Increase priority** or ![Decrease priority icon](../../media/m365-cc-sc-decrease-icon.png) **Decrease priority** to change the **Priority** value.</span></span>

4. <span data-ttu-id="fbe39-242">Wenn Sie den Vorgang abgeschlossen haben, klicken Sie im Flyout der Richtliniendetails auf **Schließen**.</span><span class="sxs-lookup"><span data-stu-id="fbe39-242">When you're finished, click **Close** in the policy details flyout.</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-remove-safe-links-policies"></a><span data-ttu-id="fbe39-243">Verwenden sie das Microsoft 365 Defender-Portal, um Tresor Verknüpfungsrichtlinien zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="fbe39-243">Use the Microsoft 365 Defender portal to remove Safe Links policies</span></span>

1. <span data-ttu-id="fbe39-244">Wechseln Sie im Portal Microsoft 365 Defender zu **E-Mail-& Richtlinien** für die Zusammenarbeit & Richtlinien für \> **Bedrohungsrichtlinien** für Regeln \>  \>  \> **Tresor Links.**</span><span class="sxs-lookup"><span data-stu-id="fbe39-244">In the Microsoft 365 Defender portal, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** \> **Policies** section \> **Safe Links**.</span></span>

2. <span data-ttu-id="fbe39-245">Wählen Sie auf der Seite **Tresor Links** eine Richtlinie aus der Liste aus, indem Sie auf den Namen klicken.</span><span class="sxs-lookup"><span data-stu-id="fbe39-245">On the **Safe Links** page, select a policy from the list by clicking on the name.</span></span> <span data-ttu-id="fbe39-246">Ganz oben auf dem angezeigten Flyout der Richtliniendetails klicken Sie auf ![Symbol „Weiter Aktionen“](../../media/m365-cc-sc-more-actions-icon.png) **Weitere Aktionen** \> ![Symbol „Richtlinie löschen“](../../media/m365-cc-sc-delete-icon.png) **Richtlinie löschen**.</span><span class="sxs-lookup"><span data-stu-id="fbe39-246">At the top of the policy details flyout that appears, click ![More actions icon](../../media/m365-cc-sc-more-actions-icon.png) **More actions** \> ![Delete policy icon](../../media/m365-cc-sc-delete-icon.png) **Delete policy**.</span></span>

3. <span data-ttu-id="fbe39-247&quot;>Klicken Sie im angezeigten Bestätigungsdialog auf **Ja**.</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;fbe39-247&quot;>In the confirmation dialog that appears, click **Yes**.</span></span>

## <a name=&quot;use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-links-policies&quot;></a><span data-ttu-id=&quot;fbe39-248&quot;>Verwenden Exchange Online PowerShell oder der eigenständigen EOP PowerShell zum Konfigurieren Tresor Verknüpfungsrichtlinien</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;fbe39-248&quot;>Use Exchange Online PowerShell or standalone EOP PowerShell to configure Safe Links policies</span></span>

<span data-ttu-id=&quot;fbe39-249&quot;>Wie zuvor beschrieben besteht eine richtlinie für Tresor Links aus einer Richtlinie für sichere Links und einer Regel für sichere Links.</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;fbe39-249&quot;>As previously described, a Safe Links policy consists of a safe links policy and a safe links rule.</span></span>

<span data-ttu-id=&quot;fbe39-250&quot;>In PowerShell ist der Unterschied zwischen Richtlinien für sichere Links und Regeln für sichere Links offensichtlich.</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;fbe39-250&quot;>In PowerShell, the difference between safe links policies and safe links rules is apparent.</span></span> <span data-ttu-id=&quot;fbe39-251&quot;>Sie verwalten Richtlinien für sichere Links mithilfe der Cmdlets **\* &quot;-SafeLinksPolicy&quot;,** und Sie verwalten Regeln für sichere Links mithilfe der Cmdlets **\* &quot;-SafeLinksRule&quot;.**</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;fbe39-251&quot;>You manage safe links policies by using the **\*-SafeLinksPolicy** cmdlets, and you manage safe links rules by using the **\*-SafeLinksRule** cmdlets.</span></span>

- <span data-ttu-id=&quot;fbe39-252&quot;>In PowerShell erstellen Sie zuerst die Richtlinie für sichere Links und dann die Regel für sichere Links, die die Richtlinie identifiziert, für die die Regel gilt.</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;fbe39-252&quot;>In PowerShell, you create the safe links policy first, then you create the safe links rule that identifies the policy that the rule applies to.</span></span>
- <span data-ttu-id=&quot;fbe39-253&quot;>In PowerShell ändern Sie die Einstellungen in der Richtlinie für sichere Links und die Regel für sichere Links separat.</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;fbe39-253&quot;>In PowerShell, you modify the settings in the safe links policy and the safe links rule separately.</span></span>
- <span data-ttu-id=&quot;fbe39-254&quot;>Wenn Sie eine Richtlinie für sichere Links aus PowerShell entfernen, wird die entsprechende Regel für sichere Links nicht automatisch entfernt und umgekehrt.</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;fbe39-254&quot;>When you remove a safe links policy from PowerShell, the corresponding safe links rule isn't automatically removed, and vice versa.</span></span>

### <a name=&quot;use-powershell-to-create-safe-links-policies&quot;></a><span data-ttu-id=&quot;fbe39-255&quot;>Verwenden von PowerShell zum Erstellen Tresor Verknüpfungsrichtlinien</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;fbe39-255&quot;>Use PowerShell to create Safe Links policies</span></span>

<span data-ttu-id=&quot;fbe39-256&quot;>Das Erstellen einer richtlinie für Tresor Links in PowerShell besteht aus zwei Schritten:</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;fbe39-256&quot;>Creating a Safe Links policy in PowerShell is a two-step process:</span></span>

1. <span data-ttu-id=&quot;fbe39-257&quot;>Erstellen Sie die Richtlinie für sichere Links.</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;fbe39-257&quot;>Create the safe links policy.</span></span>
2. <span data-ttu-id=&quot;fbe39-258&quot;>Erstellen Sie die Regel für sichere Links, die die Richtlinie für sichere Links angibt, auf die die Regel angewendet wird.</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;fbe39-258&quot;>Create the safe links rule that specifies the safe links policy that the rule applies to.</span></span>

> [!NOTE]
>
> - <span data-ttu-id=&quot;fbe39-259&quot;>Sie können eine neue Regel für sichere Links erstellen und ihr eine vorhandene Richtlinie für nicht zugeordnete sichere Links zuweisen.</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;fbe39-259&quot;>You can create a new safe links rule and assign an existing, unassociated safe links policy to it.</span></span> <span data-ttu-id=&quot;fbe39-260&quot;>Eine Regel für sichere Links kann nicht mehr als einer Richtlinie für sichere Links zugeordnet werden.</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;fbe39-260&quot;>A safe links rule can't be associated with more than one safe links policy.</span></span>
>
> - <span data-ttu-id=&quot;fbe39-261&quot;>Sie können die folgenden Einstellungen für neue Richtlinien für sichere Links in PowerShell konfigurieren, die erst nach dem Erstellen der Richtlinie im Microsoft 365 Defender Portal verfügbar sind:</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;fbe39-261&quot;>You can configure the following settings on new safe links policies in PowerShell that aren't available in the Microsoft 365 Defender portal until after you create the policy:</span></span>
>   - <span data-ttu-id=&quot;fbe39-262&quot;>Erstellen Sie die neue Richtlinie als deaktiviert _(aktiviert_ `$false` für das Cmdlet **&quot;New-SafeLinksRule").**</span><span class="sxs-lookup"><span data-stu-id="fbe39-262">Create the new policy as disabled (_Enabled_ `$false` on the **New-SafeLinksRule** cmdlet).</span></span>
>   - <span data-ttu-id="fbe39-263">Legen Sie die Priorität der Richtlinie während der Erstellung _(Priorität)_ _\<Number\>_ im Cmdlet **"New-SafeLinksRule"** fest.</span><span class="sxs-lookup"><span data-stu-id="fbe39-263">Set the priority of the policy during creation (_Priority_ _\<Number\>_) on the **New-SafeLinksRule** cmdlet).</span></span>
>
> - <span data-ttu-id="fbe39-264">Eine neue Richtlinie für sichere Links, die Sie in PowerShell erstellen, ist erst im Microsoft 365 Defender-Portal sichtbar, wenn Sie die Richtlinie einer Regel für sichere Links zuweisen.</span><span class="sxs-lookup"><span data-stu-id="fbe39-264">A new safe links policy that you create in PowerShell isn't visible in the Microsoft 365 Defender portal until you assign the policy to a safe links rule.</span></span>

#### <a name="step-1-use-powershell-to-create-a-safe-links-policy"></a><span data-ttu-id="fbe39-265">Schritt 1: Verwenden von PowerShell zum Erstellen einer Richtlinie für sichere Links</span><span class="sxs-lookup"><span data-stu-id="fbe39-265">Step 1: Use PowerShell to create a safe links policy</span></span>

<span data-ttu-id="fbe39-266">Verwenden Sie die folgende Syntax, um eine Richtlinie für sichere Links zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="fbe39-266">To create a safe links policy, use this syntax:</span></span>

```PowerShell
New-SafeLinksPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] [-IsEnabled <$true | $false>] [-EnableSafeLinksForTeams <$true | $false>] [-ScanUrls <$true | $false>] [-DeliverMessageAfterScan <$true | $false>] [-EnableForInternalSenders <$true | $false>] [-DoNotAllowClickThrough <$true | $false>] [-DoNotTrackUserClicks <$true | $false>] [-DoNotRewriteUrls "Entry1","Entry2",..."EntryN"]
```

> [!NOTE]
>
> - <span data-ttu-id="fbe39-267">Ausführliche Informationen zur Eintragssyntax, die für den _DoNotRewriteUrls-Parameter_ verwendet werden soll, finden Sie unter [Eintragssyntax für die Liste "Die folgenden URLs nicht neu schreiben".](safe-links.md#entry-syntax-for-the-do-not-rewrite-the-following-urls-list)</span><span class="sxs-lookup"><span data-stu-id="fbe39-267">For details about the entry syntax to use for the _DoNotRewriteUrls_ parameter, see [Entry syntax for the "Do not rewrite the following URLs" list](safe-links.md#entry-syntax-for-the-do-not-rewrite-the-following-urls-list).</span></span>
>
> - <span data-ttu-id="fbe39-268">Eine zusätzliche Syntax, die Sie für den _DoNotRewriteUrls-Parameter_ verwenden können, wenn Sie vorhandene Richtlinien für sichere Links mithilfe des Cmdlets **"Set-SafeLinksPolicy"** ändern, finden Sie im Abschnitt ["Verwenden von PowerShell zum Ändern](#use-powershell-to-modify-safe-links-policies) von Richtlinien für sichere Verknüpfungen" weiter unten in diesem Artikel.</span><span class="sxs-lookup"><span data-stu-id="fbe39-268">For additional syntax that you can use for the _DoNotRewriteUrls_ parameter when you modify existing safe links policies by using the **Set-SafeLinksPolicy** cmdlet, see the [Use PowerShell to modify safe links policies](#use-powershell-to-modify-safe-links-policies) section later in this article.</span></span>

<span data-ttu-id="fbe39-269">In diesem Beispiel wird eine Richtlinie für sichere Verknüpfungen namens "Contoso All" mit den folgenden Werten erstellt:</span><span class="sxs-lookup"><span data-stu-id="fbe39-269">This example creates a safe links policy named Contoso All with the following values:</span></span>

- <span data-ttu-id="fbe39-270">Aktivieren Sie die URL-Überprüfung und -Umschreibung in E-Mail-Nachrichten.</span><span class="sxs-lookup"><span data-stu-id="fbe39-270">Turn on URL scanning and rewriting in email messages.</span></span>
- <span data-ttu-id="fbe39-271">Aktivieren Sie die URL-Überprüfung in Teams (nur TAP Preview).</span><span class="sxs-lookup"><span data-stu-id="fbe39-271">Turn on URL scanning in Teams (TAP Preview only).</span></span>
- <span data-ttu-id="fbe39-272">Aktivieren Sie die Echtzeitüberprüfung von angeklickten URLs, einschließlich angeklickter Links, die auf Dateien verweisen.</span><span class="sxs-lookup"><span data-stu-id="fbe39-272">Turn on real-time scanning of clicked URLs, including clicked links that point to files.</span></span>
- <span data-ttu-id="fbe39-273">Warten Sie, bis die URL-Überprüfung abgeschlossen ist, bevor Sie die Nachricht übermitteln.</span><span class="sxs-lookup"><span data-stu-id="fbe39-273">Wait for URL scanning to complete before delivering the message.</span></span>
- <span data-ttu-id="fbe39-274">Aktivieren Sie die URL-Überprüfung und das Umschreiben für interne Nachrichten.</span><span class="sxs-lookup"><span data-stu-id="fbe39-274">Turn on URL scanning and rewriting for internal messages.</span></span>
- <span data-ttu-id="fbe39-275">Nachverfolgen von Benutzerklicks im Zusammenhang mit Tresor Links-Schutz (wir verwenden nicht den _DoNotTrackUserClicks-Parameter,_ und der Standardwert ist $false, was bedeutet, dass Benutzerklicks nachverfolgt werden).</span><span class="sxs-lookup"><span data-stu-id="fbe39-275">Track user clicks related to Safe Links protection (we aren't using the _DoNotTrackUserClicks_ parameter, and the default value is $false, which means user clicks are tracked).</span></span>
- <span data-ttu-id="fbe39-276">Benutzer dürfen nicht auf die ursprüngliche URL klicken.</span><span class="sxs-lookup"><span data-stu-id="fbe39-276">Do not allow users to click through to the original URL.</span></span>

```PowerShell
New-SafeLinksPolicy -Name "Contoso All" -IsEnabled $true -EnableSafeLinksForTeams $true -ScanUrls $true -DeliverMessageAfterScan $true -EnableForInternalSenders $true -DoNotAllowClickThrough $true
```

<span data-ttu-id="fbe39-277">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [New-SafeLinksPolicy](/powershell/module/exchange/new-safelinkspolicy).</span><span class="sxs-lookup"><span data-stu-id="fbe39-277">For detailed syntax and parameter information, see [New-SafeLinksPolicy](/powershell/module/exchange/new-safelinkspolicy).</span></span>

#### <a name="step-2-use-powershell-to-create-a-safe-links-rule"></a><span data-ttu-id="fbe39-278">Schritt 2: Verwenden von PowerShell zum Erstellen einer Regel für sichere Links</span><span class="sxs-lookup"><span data-stu-id="fbe39-278">Step 2: Use PowerShell to create a safe links rule</span></span>

<span data-ttu-id="fbe39-279">Verwenden Sie diese Syntax, um eine Regel für sichere Links zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="fbe39-279">To create a safe links rule, use this syntax:</span></span>

```PowerShell
New-SafeLinksRule -Name "<RuleName>" -SafeLinksPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"] [-Enabled <$true | $false>]
```

<span data-ttu-id="fbe39-280">In diesem Beispiel wird eine Regel für sichere Verknüpfungen namens "Contoso All" mit den folgenden Bedingungen erstellt:</span><span class="sxs-lookup"><span data-stu-id="fbe39-280">This example creates a safe links rule named Contoso All with the following conditions:</span></span>

- <span data-ttu-id="fbe39-281">Die Regel ist der Richtlinie für sichere Verknüpfungen namens Contoso All zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="fbe39-281">The rule is associated with the safe links policy named Contoso All.</span></span>
- <span data-ttu-id="fbe39-282">Die Regel gilt für alle Empfänger in der contoso.com Domäne.</span><span class="sxs-lookup"><span data-stu-id="fbe39-282">The rule applies to all recipients in the contoso.com domain.</span></span>
- <span data-ttu-id="fbe39-283">Da der Parameter _"Priority"_ nicht verwendet wird, wird die Standardpriorität verwendet.</span><span class="sxs-lookup"><span data-stu-id="fbe39-283">Because we aren't using the _Priority_ parameter, the default priority is used.</span></span>
- <span data-ttu-id="fbe39-284">Die Regel ist aktiviert (wir verwenden nicht den Parameter _Enabled,_ und der Standardwert lautet `$true` ).</span><span class="sxs-lookup"><span data-stu-id="fbe39-284">The rule is enabled (we aren't using the _Enabled_ parameter, and the default value is `$true`).</span></span>

```powershell
New-SafeLinksRule -Name "Contoso All" -SafeLinksPolicy "Contoso All" -RecipientDomainIs contoso.com
```

<span data-ttu-id="fbe39-285">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [New-SafeLinksRule](/powershell/module/exchange/new-safelinksrule).</span><span class="sxs-lookup"><span data-stu-id="fbe39-285">For detailed syntax and parameter information, see [New-SafeLinksRule](/powershell/module/exchange/new-safelinksrule).</span></span>

### <a name="use-powershell-to-view-safe-links-policies"></a><span data-ttu-id="fbe39-286">Verwenden von PowerShell zum Anzeigen von Richtlinien für sichere Links</span><span class="sxs-lookup"><span data-stu-id="fbe39-286">Use PowerShell to view safe links policies</span></span>

<span data-ttu-id="fbe39-287">Verwenden Sie die folgende Syntax, um vorhandene Richtlinien für sichere Links anzuzeigen:</span><span class="sxs-lookup"><span data-stu-id="fbe39-287">To view existing safe links policies, use the following syntax:</span></span>

```PowerShell
Get-SafeLinksPolicy [-Identity "<PolicyIdentity>"] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="fbe39-288">In diesem Beispiel wird eine Zusammenfassungsliste aller Richtlinien für sichere Links zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="fbe39-288">This example returns a summary list of all safe links policies.</span></span>

```PowerShell
Get-SafeLinksPolicy | Format-Table Name
```

<span data-ttu-id="fbe39-289">In diesem Beispiel werden detaillierte Informationen für die Richtlinie für sichere Links namens Contoso Executives zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="fbe39-289">This example returns detailed information for the safe links policy named Contoso Executives.</span></span>

```PowerShell
Get-SafeLinksPolicy -Identity "Contoso Executives"
```

<span data-ttu-id="fbe39-290">Ausführliche Informationen zu Syntax und Parametern finden Sie unter ["Get-SafeLinksPolicy".](/powershell/module/exchange/get-safelinkspolicy)</span><span class="sxs-lookup"><span data-stu-id="fbe39-290">For detailed syntax and parameter information, see [Get-SafeLinksPolicy](/powershell/module/exchange/get-safelinkspolicy).</span></span>

### <a name="use-powershell-to-view-safe-links-rules"></a><span data-ttu-id="fbe39-291">Verwenden von PowerShell zum Anzeigen von Regeln für sichere Links</span><span class="sxs-lookup"><span data-stu-id="fbe39-291">Use PowerShell to view safe links rules</span></span>

<span data-ttu-id="fbe39-292">Verwenden Sie die folgende Syntax, um vorhandene Regeln für sichere Links anzuzeigen:</span><span class="sxs-lookup"><span data-stu-id="fbe39-292">To view existing safe links rules, use the following syntax:</span></span>

```PowerShell
Get-SafeLinksRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="fbe39-293">In diesem Beispiel wird eine Zusammenfassungsliste aller Regeln für sichere Links zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="fbe39-293">This example returns a summary list of all safe links rules.</span></span>

```PowerShell
Get-SafeLinksRule | Format-Table Name,State
```

<span data-ttu-id="fbe39-294">Führen Sie die folgenden Befehle aus, um die Liste nach aktivierten oder deaktivierten Regeln zu filtern:</span><span class="sxs-lookup"><span data-stu-id="fbe39-294">To filter the list by enabled or disabled rules, run the following commands:</span></span>

```PowerShell
Get-SafeLinksRule -State Disabled
```

```PowerShell
Get-SafeLinksRule -State Enabled
```

<span data-ttu-id="fbe39-295">In diesem Beispiel werden detaillierte Informationen für die Regel für sichere Links namens Contoso Executives zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="fbe39-295">This example returns detailed information for the safe links rule named Contoso Executives.</span></span>

```PowerShell
Get-SafeLinksRule -Identity "Contoso Executives"
```

<span data-ttu-id="fbe39-296">Ausführliche Informationen zu Syntax und Parametern finden Sie unter ["Get-SafeLinksRule".](/powershell/module/exchange/get-safelinksrule)</span><span class="sxs-lookup"><span data-stu-id="fbe39-296">For detailed syntax and parameter information, see [Get-SafeLinksRule](/powershell/module/exchange/get-safelinksrule).</span></span>

### <a name="use-powershell-to-modify-safe-links-policies"></a><span data-ttu-id="fbe39-297">Verwenden von PowerShell zum Ändern von Richtlinien für sichere Links</span><span class="sxs-lookup"><span data-stu-id="fbe39-297">Use PowerShell to modify safe links policies</span></span>

<span data-ttu-id="fbe39-298">Sie können eine Richtlinie für sichere Links in PowerShell nicht umbenennen (das Cmdlet **"Set-SafeLinksPolicy"** hat keinen _Name-Parameter)._</span><span class="sxs-lookup"><span data-stu-id="fbe39-298">You can't rename a safe links policy in PowerShell (the **Set-SafeLinksPolicy** cmdlet has no _Name_ parameter).</span></span> <span data-ttu-id="fbe39-299">Wenn Sie eine Tresor Verknüpfungsrichtlinie im Microsoft 365 Defender-Portal umbenennen, benennen Sie nur die _Regel für_ sichere Links um.</span><span class="sxs-lookup"><span data-stu-id="fbe39-299">When you rename a Safe Links policy in the Microsoft 365 Defender portal, you're only renaming the safe links _rule_.</span></span>

<span data-ttu-id="fbe39-300">Die einzige zusätzliche Überlegung zum Ändern von Richtlinien für sichere Links in PowerShell ist die verfügbare Syntax für den _Parameter "DoNotRewriteUrls"_ (die [Liste "Die folgenden URLs nicht umschreiben"):](safe-links.md#do-not-rewrite-the-following-urls-lists-in-safe-links-policies)</span><span class="sxs-lookup"><span data-stu-id="fbe39-300">The only additional consideration for modifying safe links policies in PowerShell is the available syntax for the _DoNotRewriteUrls_ parameter (the ["Do not rewrite the following URLs" list](safe-links.md#do-not-rewrite-the-following-urls-lists-in-safe-links-policies)):</span></span>

- <span data-ttu-id="fbe39-301">Verwenden Sie die folgende Syntax, um Werte hinzuzufügen, die vorhandene Einträge `"Entry1","Entry2,..."EntryN"` ersetzen:</span><span class="sxs-lookup"><span data-stu-id="fbe39-301">To add values that will replace any existing entries, use the following syntax: `"Entry1","Entry2,..."EntryN"`.</span></span>
- <span data-ttu-id="fbe39-302">Verwenden Sie die folgende Syntax, um Werte hinzuzufügen oder zu entfernen, ohne dass sich dies auf andere Einträge auswirkt: `@{Add="Entry1","Entry2"...; Remove="Entry3","Entry4"...}`</span><span class="sxs-lookup"><span data-stu-id="fbe39-302">To add or remove values without affecting other existing entries, use the following syntax: `@{Add="Entry1","Entry2"...; Remove="Entry3","Entry4"...}`</span></span>

<span data-ttu-id="fbe39-303">Andernfalls sind die gleichen Einstellungen verfügbar, wenn Sie eine Richtlinie für sichere Links erstellen, wie im [Abschnitt "Schritt 1: Verwenden von PowerShell zum Erstellen einer Richtlinie für sichere Links"](#step-1-use-powershell-to-create-a-safe-links-policy) weiter oben in diesem Artikel beschrieben.</span><span class="sxs-lookup"><span data-stu-id="fbe39-303">Otherwise, the same settings are available when you create a safe links policy as described in the [Step 1: Use PowerShell to create a safe links policy](#step-1-use-powershell-to-create-a-safe-links-policy) section earlier in this article.</span></span>

<span data-ttu-id="fbe39-304">Verwenden Sie diese Syntax, um eine Richtlinie für sichere Links zu ändern:</span><span class="sxs-lookup"><span data-stu-id="fbe39-304">To modify a safe links policy, use this syntax:</span></span>

```PowerShell
Set-SafeLinksPolicy -Identity "<PolicyName>" <Settings>
```

<span data-ttu-id="fbe39-305">Ausführliche Informationen zu Syntax und Parametern finden Sie unter ["Set-SafeLinksPolicy".](/powershell/module/exchange/set-safelinkspolicy)</span><span class="sxs-lookup"><span data-stu-id="fbe39-305">For detailed syntax and parameter information, see [Set-SafeLinksPolicy](/powershell/module/exchange/set-safelinkspolicy).</span></span>

### <a name="use-powershell-to-modify-safe-links-rules"></a><span data-ttu-id="fbe39-306">Verwenden von PowerShell zum Ändern von Regeln für sichere Links</span><span class="sxs-lookup"><span data-stu-id="fbe39-306">Use PowerShell to modify safe links rules</span></span>

<span data-ttu-id="fbe39-307">Die einzige Einstellung, die beim Ändern einer Regel für sichere Verknüpfungen in PowerShell nicht verfügbar ist, ist der _Parameter "Enabled",_ mit dem Sie eine deaktivierte Regel erstellen können.</span><span class="sxs-lookup"><span data-stu-id="fbe39-307">The only setting that's not available when you modify a safe links rule in PowerShell is the _Enabled_ parameter that allows you to create a disabled rule.</span></span> <span data-ttu-id="fbe39-308">Informationen zum Aktivieren oder Deaktivieren vorhandener Regeln für sichere Links finden Sie im nächsten Abschnitt.</span><span class="sxs-lookup"><span data-stu-id="fbe39-308">To enable or disable existing safe links rules, see the next section.</span></span>

<span data-ttu-id="fbe39-309">Andernfalls sind die gleichen Einstellungen verfügbar, wenn Sie eine Regel erstellen, wie im [Abschnitt "Schritt 2: Verwenden von PowerShell zum Erstellen einer Regel](#step-2-use-powershell-to-create-a-safe-links-rule) für sichere Links" weiter oben in diesem Artikel beschrieben.</span><span class="sxs-lookup"><span data-stu-id="fbe39-309">Otherwise, the same settings are available when you create a rule as described in the [Step 2: Use PowerShell to create a safe links rule](#step-2-use-powershell-to-create-a-safe-links-rule) section earlier in this article.</span></span>

<span data-ttu-id="fbe39-310">Verwenden Sie diese Syntax, um eine Regel für sichere Links zu ändern:</span><span class="sxs-lookup"><span data-stu-id="fbe39-310">To modify a safe links rule, use this syntax:</span></span>

```PowerShell
Set-SafeLinksRule -Identity "<RuleName>" <Settings>
```

<span data-ttu-id="fbe39-311">Ausführliche Informationen zu Syntax und Parametern finden Sie unter ["Set-SafeLinksRule".](/powershell/module/exchange/set-safelinksrule)</span><span class="sxs-lookup"><span data-stu-id="fbe39-311">For detailed syntax and parameter information, see [Set-SafeLinksRule](/powershell/module/exchange/set-safelinksrule).</span></span>

### <a name="use-powershell-to-enable-or-disable-safe-links-rules"></a><span data-ttu-id="fbe39-312">Verwenden von PowerShell zum Aktivieren oder Deaktivieren von Regeln für sichere Links</span><span class="sxs-lookup"><span data-stu-id="fbe39-312">Use PowerShell to enable or disable safe links rules</span></span>

<span data-ttu-id="fbe39-313">Das Aktivieren oder Deaktivieren einer Regel für sichere Links in PowerShell aktiviert oder deaktiviert die gesamte Richtlinie für Tresor Links (die Regel für sichere Links und die Richtlinie für zugewiesene sichere Links).</span><span class="sxs-lookup"><span data-stu-id="fbe39-313">Enabling or disabling a safe links rule in PowerShell enables or disables the whole Safe Links policy (the safe links rule and the assigned safe links policy).</span></span>

<span data-ttu-id="fbe39-314">Verwenden Sie die folgende Syntax, um eine Regel für sichere Links in PowerShell zu aktivieren oder zu deaktivieren:</span><span class="sxs-lookup"><span data-stu-id="fbe39-314">To enable or disable a safe links rule in PowerShell, use this syntax:</span></span>

```PowerShell
<Enable-SafeLinksRule | Disable-SafeLinksRule> -Identity "<RuleName>"
```

<span data-ttu-id="fbe39-315">In diesem Beispiel wird die Regel für sichere Links mit dem Namen "Marketing Department" deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="fbe39-315">This example disables the safe links rule named Marketing Department.</span></span>

```PowerShell
Disable-SafeLinksRule -Identity "Marketing Department"
```

<span data-ttu-id="fbe39-316">In diesem Beispiel wird dieselbe Regel aktiviert.</span><span class="sxs-lookup"><span data-stu-id="fbe39-316">This example enables same rule.</span></span>

```PowerShell
Enable-SafeLinksRule -Identity "Marketing Department"
```

<span data-ttu-id="fbe39-317">Ausführliche Informationen zu Syntax und Parametern finden Sie unter ["Enable-SafeLinksRule"](/powershell/module/exchange/enable-safelinksrule) und ["Disable-SafeLinksRule".](/powershell/module/exchange/disable-safelinksrule)</span><span class="sxs-lookup"><span data-stu-id="fbe39-317">For detailed syntax and parameter information, see [Enable-SafeLinksRule](/powershell/module/exchange/enable-safelinksrule) and [Disable-SafeLinksRule](/powershell/module/exchange/disable-safelinksrule).</span></span>

### <a name="use-powershell-to-set-the-priority-of-safe-links-rules"></a><span data-ttu-id="fbe39-318">Verwenden von PowerShell zum Festlegen der Priorität von Regeln für sichere Links</span><span class="sxs-lookup"><span data-stu-id="fbe39-318">Use PowerShell to set the priority of safe links rules</span></span>

<span data-ttu-id="fbe39-p131">Der höchste Prioritätswert, den Sie für eine Regel festlegen können, ist 0. Der niedrigste Wert, den Sie festlegen können, hängt von der Anzahl von Regeln ab. Wenn Sie z. B. fünf Regeln haben, können Sie die Prioritätswerte 0 bis 4 verwenden. Das Ändern der Priorität einer vorhandenen Regel kann sich entsprechend auf andere Regeln auswirken. Wenn Sie z. B. fünf benutzerdefinierte Regeln haben (Priorität 0 bis 4) und die Priorität einer Regel in 2 ändern, erhält die vorhandene Regel mit Priorität 2 die Priorität 3, und die Regel mit Priorität 3 erhält Priorität 4.</span><span class="sxs-lookup"><span data-stu-id="fbe39-p131">The highest priority value you can set on a rule is 0. The lowest value you can set depends on the number of rules. For example, if you have five rules, you can use the priority values 0 through 4. Changing the priority of an existing rule can have a cascading effect on other rules. For example, if you have five custom rules (priorities 0 through 4), and you change the priority of a rule to 2, the existing rule with priority 2 is changed to priority 3, and the rule with priority 3 is changed to priority 4.</span></span>

<span data-ttu-id="fbe39-324">Verwenden Sie die folgende Syntax, um die Priorität einer Regel für sichere Links in PowerShell festzulegen:</span><span class="sxs-lookup"><span data-stu-id="fbe39-324">To set the priority of a safe links rule in PowerShell, use the following syntax:</span></span>

```PowerShell
Set-SafeLinksRule -Identity "<RuleName>" -Priority <Number>
```

<span data-ttu-id="fbe39-p132">In diesem Beispiel wird die Priorität der Regel namens „Marketing Department“ auf 2 festgelegt. Alle vorhandenen Regeln mit Priorität kleiner oder gleich 2 werden um 1 verringert (die Prioritätswerte werden um 1 erhöht).</span><span class="sxs-lookup"><span data-stu-id="fbe39-p132">This example sets the priority of the rule named Marketing Department to 2. All existing rules that have a priority less than or equal to 2 are decreased by 1 (their priority numbers are increased by 1).</span></span>

```PowerShell
Set-SafeLinksRule -Identity "Marketing Department" -Priority 2
```

> [!NOTE]
> <span data-ttu-id="fbe39-327">Um die Priorität einer neuen Regel beim Erstellen festzulegen, verwenden Sie stattdessen den Parameter _"Priority"_ im Cmdlet **"New-SafeLinksRule".**</span><span class="sxs-lookup"><span data-stu-id="fbe39-327">To set the priority of a new rule when you create it, use the _Priority_ parameter on the **New-SafeLinksRule** cmdlet instead.</span></span>

<span data-ttu-id="fbe39-328">Ausführliche Informationen zu Syntax und Parametern finden Sie unter ["Set-SafeLinksRule".](/powershell/module/exchange/set-safelinksrule)</span><span class="sxs-lookup"><span data-stu-id="fbe39-328">For detailed syntax and parameter information, see [Set-SafeLinksRule](/powershell/module/exchange/set-safelinksrule).</span></span>

### <a name="use-powershell-to-remove-safe-links-policies"></a><span data-ttu-id="fbe39-329">Verwenden von PowerShell zum Entfernen von Richtlinien für sichere Links</span><span class="sxs-lookup"><span data-stu-id="fbe39-329">Use PowerShell to remove safe links policies</span></span>

<span data-ttu-id="fbe39-330">Wenn Sie PowerShell verwenden, um eine Richtlinie für sichere Links zu entfernen, wird die entsprechende Regel für sichere Links nicht entfernt.</span><span class="sxs-lookup"><span data-stu-id="fbe39-330">When you use PowerShell to remove a safe links policy, the corresponding safe links rule isn't removed.</span></span>

<span data-ttu-id="fbe39-331">Verwenden Sie die folgende Syntax, um eine Richtlinie für sichere Links in PowerShell zu entfernen:</span><span class="sxs-lookup"><span data-stu-id="fbe39-331">To remove a safe links policy in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-SafeLinksPolicy -Identity "<PolicyName>"
```

<span data-ttu-id="fbe39-332">In diesem Beispiel wird die Richtlinie für sichere Links mit dem Namen "Marketing Department" entfernt.</span><span class="sxs-lookup"><span data-stu-id="fbe39-332">This example removes the safe links policy named Marketing Department.</span></span>

```PowerShell
Remove-SafeLinksPolicy -Identity "Marketing Department"
```

<span data-ttu-id="fbe39-333">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Remove-SafeLinksPolicy](/powershell/module/exchange/remove-safelinkspolicy).</span><span class="sxs-lookup"><span data-stu-id="fbe39-333">For detailed syntax and parameter information, see [Remove-SafeLinksPolicy](/powershell/module/exchange/remove-safelinkspolicy).</span></span>

### <a name="use-powershell-to-remove-safe-links-rules"></a><span data-ttu-id="fbe39-334">Verwenden von PowerShell zum Entfernen von Regeln für sichere Links</span><span class="sxs-lookup"><span data-stu-id="fbe39-334">Use PowerShell to remove safe links rules</span></span>

<span data-ttu-id="fbe39-335">Wenn Sie PowerShell verwenden, um eine Regel für sichere Links zu entfernen, wird die entsprechende Richtlinie für sichere Links nicht entfernt.</span><span class="sxs-lookup"><span data-stu-id="fbe39-335">When you use PowerShell to remove a safe links rule, the corresponding safe links policy isn't removed.</span></span>

<span data-ttu-id="fbe39-336">Verwenden Sie die folgende Syntax, um eine Regel für sichere Links in PowerShell zu entfernen:</span><span class="sxs-lookup"><span data-stu-id="fbe39-336">To remove a safe links rule in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-SafeLinksRule -Identity "<PolicyName>"
```

<span data-ttu-id="fbe39-337">In diesem Beispiel wird die Regel für sichere Verknüpfungen mit dem Namen "Marketing Department" entfernt.</span><span class="sxs-lookup"><span data-stu-id="fbe39-337">This example removes the safe links rule named Marketing Department.</span></span>

```PowerShell
Remove-SafeLinksRule -Identity "Marketing Department"
```

<span data-ttu-id="fbe39-338">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Remove-SafeLinksRule](/powershell/module/exchange/remove-safelinksrule).</span><span class="sxs-lookup"><span data-stu-id="fbe39-338">For detailed syntax and parameter information, see [Remove-SafeLinksRule](/powershell/module/exchange/remove-safelinksrule).</span></span>

<span data-ttu-id="fbe39-339">Um zu überprüfen, ob Tresor Links Nachrichten überprüft, überprüfen Sie den verfügbaren Microsoft Defender auf Office 365 Berichte.</span><span class="sxs-lookup"><span data-stu-id="fbe39-339">To verify that Safe Links is scanning messages, check the available Microsoft Defender for Office 365 reports.</span></span> <span data-ttu-id="fbe39-340">Weitere Informationen finden Sie unter [Anzeigen von Berichten für Defender für Office 365](view-reports-for-mdo.md) und Verwenden von Explorer im Microsoft 365 Defender [Portal.](threat-explorer.md)</span><span class="sxs-lookup"><span data-stu-id="fbe39-340">For more information, see [View reports for Defender for Office 365](view-reports-for-mdo.md) and [Use Explorer in the Microsoft 365 Defender portal](threat-explorer.md).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="fbe39-341">Wie können Sie feststellen, dass diese Verfahren erfolgreich waren?</span><span class="sxs-lookup"><span data-stu-id="fbe39-341">How do you know these procedures worked?</span></span>

<span data-ttu-id="fbe39-342">Führen Sie einen der folgenden Schritte aus, um zu überprüfen, ob Sie Tresor Verknüpfungsrichtlinien erfolgreich erstellt, geändert oder entfernt haben:</span><span class="sxs-lookup"><span data-stu-id="fbe39-342">To verify that you've successfully created, modified, or removed Safe Links policies, do any of the following steps:</span></span>

- <span data-ttu-id="fbe39-343">Wechseln Sie im portal Microsoft 365 Defender zu **Richtlinien & Regeln** \> **Bedrohungsrichtlinien** Tresor \> **Links**.</span><span class="sxs-lookup"><span data-stu-id="fbe39-343">In the Microsoft 365 Defender portal, go to **Policies & rules** \> **Threat policies** \> **Safe Links**.</span></span> <span data-ttu-id="fbe39-344">Überprüfen Sie die Liste der Richtlinien, ihre **Statuswerte** und ihre **Prioritätswerte.**</span><span class="sxs-lookup"><span data-stu-id="fbe39-344">Verify the list of policies, their **Status** values, and their **Priority** values.</span></span> <span data-ttu-id="fbe39-345">Um weitere Details anzuzeigen, wählen Sie die Richtlinie aus der Liste aus, und zeigen Sie die Details im Flyout an.</span><span class="sxs-lookup"><span data-stu-id="fbe39-345">To view more details, select the policy from the list, and view the details in the fly out.</span></span>

- <span data-ttu-id="fbe39-346">Ersetzen Sie in Exchange Online PowerShell oder Exchange Online Protection PowerShell \<Name\> durch den Namen der Richtlinie oder Regel, führen Sie den folgenden Befehl aus, und überprüfen Sie die Einstellungen:</span><span class="sxs-lookup"><span data-stu-id="fbe39-346">In Exchange Online PowerShell or Exchange Online Protection PowerShell, replace \<Name\> with the name of the policy or rule, run the following command, and verify the settings:</span></span>

  ```PowerShell
  Get-SafeLinksPolicy -Identity "<Name>"
  ```

  ```PowerShell
  Get-SafeLinksRule -Identity "<Name>"
  ```
