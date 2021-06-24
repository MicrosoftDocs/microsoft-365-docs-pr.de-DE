---
title: Konfigurieren globaler Einstellungen für Tresor Links-Einstellungen in Defender für Office 365
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
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: Administratoren erfahren, wie sie globale Einstellungen (die Liste "Die folgenden URLs blockieren" und den Schutz für Office 365-Apps) für Tresor Links in Microsoft Defender für Office 365 anzeigen und konfigurieren.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 46bafd89400dfa551641c055f6f0e208c0ecd49f
ms.sourcegitcommit: ebb1c3b4d94058a58344317beb9475c8a2eae9a7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/24/2021
ms.locfileid: "53108043"
---
# <a name="configure-global-settings-for-safe-links-in-microsoft-defender-for-office-365"></a><span data-ttu-id="29a82-103">Konfigurieren globaler Einstellungen für Tresor Links in Microsoft Defender für Office 365</span><span class="sxs-lookup"><span data-stu-id="29a82-103">Configure global settings for Safe Links in Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="29a82-104">**Gilt für**</span><span class="sxs-lookup"><span data-stu-id="29a82-104">**Applies to**</span></span>
- [<span data-ttu-id="29a82-105">Microsoft Defender für Office 365 Plan 1 und Plan 2</span><span class="sxs-lookup"><span data-stu-id="29a82-105">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="29a82-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="29a82-106">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

> [!IMPORTANT]
> <span data-ttu-id="29a82-107">Dieser Artikel richtet sich an Geschäftskunden, die über [Microsoft Defender für Office 365](defender-for-office-365.md) verfügen.</span><span class="sxs-lookup"><span data-stu-id="29a82-107">This article is intended for business customers who have [Microsoft Defender for Office 365](defender-for-office-365.md).</span></span> <span data-ttu-id="29a82-108">Wenn Sie ein Privatbenutzer sind, der nach Informationen zu Safelinks in Outlook sucht, finden Sie weitere Informationen unter [Advanced Outlook.com Security.](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2)</span><span class="sxs-lookup"><span data-stu-id="29a82-108">If you are a home user looking for information about Safelinks in Outlook, see [Advanced Outlook.com security](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).</span></span>

<span data-ttu-id="29a82-109">Tresor Links ist ein Feature in [Microsoft Defender für Office 365,](defender-for-office-365.md) das die URL-Überprüfung eingehender E-Mail-Nachrichten im E-Mail-Fluss sowie den Zeitpunkt der Klicküberprüfung von URLs und Links in E-Mail-Nachrichten und an anderen Speicherorten ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="29a82-109">Safe Links is a feature in [Microsoft Defender for Office 365](defender-for-office-365.md) that provides URL scanning of inbound email messages in mail flow, and time of click verification of URLs and links in email messages and in other locations.</span></span> <span data-ttu-id="29a82-110">Weitere Informationen finden Sie unter [Tresor Links in Microsoft Defender für Office 365](safe-links.md).</span><span class="sxs-lookup"><span data-stu-id="29a82-110">For more information, see [Safe Links in Microsoft Defender for Office 365](safe-links.md).</span></span>

<span data-ttu-id="29a82-111">Sie konfigurieren die meisten Einstellungen für Tresor Links in Tresor Links-Richtlinien.</span><span class="sxs-lookup"><span data-stu-id="29a82-111">You configure most Safe Links settings in Safe Links policies.</span></span> <span data-ttu-id="29a82-112">Anweisungen finden Sie unter ["Einrichten Tresor Links"-Richtlinien in Microsoft Defender für Office 365.](set-up-safe-links-policies.md)</span><span class="sxs-lookup"><span data-stu-id="29a82-112">For instructions, see [Set up Safe Links policies in Microsoft Defender for Office 365](set-up-safe-links-policies.md).</span></span>

<span data-ttu-id="29a82-113">Tresor Links verwendet jedoch auch die folgenden globalen Einstellungen, die Sie außerhalb der Richtlinien für Tresor Links selbst konfigurieren:</span><span class="sxs-lookup"><span data-stu-id="29a82-113">But, Safe Links also uses the following global settings that you configure outside of the Safe Links policies themselves:</span></span>

- <span data-ttu-id="29a82-114">Die **Liste der folgenden URLs blockieren.**</span><span class="sxs-lookup"><span data-stu-id="29a82-114">The **Block the following URLs** list.</span></span> <span data-ttu-id="29a82-115">Diese Einstellung gilt für alle Benutzer, die in allen aktiven Richtlinien für Tresor Links enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="29a82-115">This setting applies to all users who are included in any active Safe Links policies.</span></span> <span data-ttu-id="29a82-116">Weitere Informationen finden Sie unter ["Blockieren der folgenden URLs" für Tresor Links](safe-links.md#block-the-following-urls-list-for-safe-links)</span><span class="sxs-lookup"><span data-stu-id="29a82-116">For more information, see ["Block the following URLs" list for Safe Links](safe-links.md#block-the-following-urls-list-for-safe-links)</span></span>
- <span data-ttu-id="29a82-117">Tresor Linksschutz für Office 365 Apps.</span><span class="sxs-lookup"><span data-stu-id="29a82-117">Safe Links protection for Office 365 apps.</span></span> <span data-ttu-id="29a82-118">Diese Einstellungen gelten für alle Benutzer in der Organisation, die für Defender für Office 365 lizenziert sind, unabhängig davon, ob die Benutzer in den aktiven Richtlinien für Tresor Links enthalten sind oder nicht.</span><span class="sxs-lookup"><span data-stu-id="29a82-118">These settings apply to all users in the organization who are licensed for Defender for Office 365, regardless of whether the users are included in active Safe Links policies or not.</span></span> <span data-ttu-id="29a82-119">Weitere Informationen finden Sie unter [Tresor Links-Einstellungen für Office 365 Apps.](safe-links.md#safe-links-settings-for-office-365-apps)</span><span class="sxs-lookup"><span data-stu-id="29a82-119">For more information, see [Safe Links settings for Office 365 apps](safe-links.md#safe-links-settings-for-office-365-apps).</span></span>

<span data-ttu-id="29a82-120">Sie können die einstellungen für globale Tresor Links im Microsoft 365 Defender-Portal oder in PowerShell konfigurieren (Exchange Online PowerShell für berechtigte Microsoft 365 Organisationen mit Postfächern in Exchange Online; eigenständige EOP PowerShell für Organisationen ohne Exchange Online Postfächer, aber mit Microsoft Defender für Office 365 Add-On-Abonnements).</span><span class="sxs-lookup"><span data-stu-id="29a82-120">You can configure the global Safe Links settings in the Microsoft 365 Defender portal or in PowerShell (Exchange Online PowerShell for eligible Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes, but with Microsoft Defender for Office 365 add-on subscriptions).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="29a82-121">Was sollten Sie wissen, bevor Sie beginnen?</span><span class="sxs-lookup"><span data-stu-id="29a82-121">What do you need to know before you begin?</span></span>

- <span data-ttu-id="29a82-122">Es gibt keine integrierte oder standardmäßige richtlinie für Tresor Links. Daher müssen Sie mindestens eine Tresor Verknüpfungsrichtlinie erstellen, damit **die Liste der folgenden URLs** blockiert wird.</span><span class="sxs-lookup"><span data-stu-id="29a82-122">There is no built-in or default Safe Links policy, so you need to create at least one Safe Links policy in order for the **Block the following URLs** list to be active.</span></span> <span data-ttu-id="29a82-123">Anweisungen finden Sie unter ["Einrichten Tresor Links"-Richtlinien in Microsoft Defender für Office 365.](set-up-safe-links-policies.md)</span><span class="sxs-lookup"><span data-stu-id="29a82-123">For instructions, see [Set up Safe Links policies in Microsoft Defender for Office 365](set-up-safe-links-policies.md).</span></span>

- <span data-ttu-id="29a82-124">Sie öffnen das Microsoft 365 Defender-Portal unter <https://security.microsoft.com>.</span><span class="sxs-lookup"><span data-stu-id="29a82-124">You open the Microsoft 365 Defender portal at <https://security.microsoft.com>.</span></span> <span data-ttu-id="29a82-125">To go directly to the **Tresor Links** page, use <https://security.microsoft.com/safelinksv2> .</span><span class="sxs-lookup"><span data-stu-id="29a82-125">To go directly to the **Safe Links** page, use <https://security.microsoft.com/safelinksv2>.</span></span>

- <span data-ttu-id="29a82-126">Wie Sie eine Verbindung mit Exchange Online PowerShell herstellen, finden Sie unter [Herstellen einer Verbindung mit Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="29a82-126">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="29a82-127">Informationen zum Herstellen einer Verbindung mit dem eigenständigen Exchange Online Protection PowerShell finden Sie unter [Verbinden mit PowerShell in Exchange Online Protection](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="29a82-127">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="29a82-128">Sie müssen in **Exchange Online** Berechtigungen erhalten, bevor Sie die in diesem Artikel beschriebenen Schritte ausführen können:</span><span class="sxs-lookup"><span data-stu-id="29a82-128">You need to be assigned permissions in **Exchange Online** before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="29a82-129">Um die globalen Einstellungen für Tresor Links zu konfigurieren, müssen Sie Mitglied der Rollengruppen **"Organisationsverwaltung"** oder **"Sicherheitsadministrator"** sein.</span><span class="sxs-lookup"><span data-stu-id="29a82-129">To configure the global settings for Safe Links, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="29a82-130">Für den schreibgeschützten Zugriff auf die globalen Einstellungen für Tresor Links müssen Sie Mitglied der Rollengruppe **"Globaler Leser"** oder **"Sicherheitsleseberechtigter"** sein.</span><span class="sxs-lookup"><span data-stu-id="29a82-130">For read-only access to the global settings for Safe Links, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="29a82-131">Weitere Informationen finden Sie unter [Berechtigungen in Exchange Online](/exchange/permissions-exo/permissions-exo).</span><span class="sxs-lookup"><span data-stu-id="29a82-131">For more information, see [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo).</span></span>

  <span data-ttu-id="29a82-132">**Hinweise**:</span><span class="sxs-lookup"><span data-stu-id="29a82-132">**Notes**:</span></span>

  - <span data-ttu-id="29a82-133">Durch Hinzufügen von Benutzern zur entsprechenden Azure Active Directory-Rolle im Microsoft 365 Admin Center erhalten Benutzer die erforderlichen Berechtigungen _und_ Berechtigungen für andere Features in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="29a82-133">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="29a82-134">Weitere Informationen finden Sie unter [Informationen zu Administratorrollen](../../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="29a82-134">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  - <span data-ttu-id="29a82-135">Die Rollengruppe **Organisationsverwaltung mit Leserechten** in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) ermöglicht auch einen schreibgeschützten Zugriff auf das Feature.</span><span class="sxs-lookup"><span data-stu-id="29a82-135">The **View-Only Organization Management** role group in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

- <span data-ttu-id="29a82-136">Unsere empfohlenen Werte für die globalen Einstellungen für Tresor Links finden Sie unter [Tresor Links settings](recommended-settings-for-eop-and-office365.md#safe-links-settings).</span><span class="sxs-lookup"><span data-stu-id="29a82-136">For our recommended values for the global settings for Safe Links, see [Safe Links settings](recommended-settings-for-eop-and-office365.md#safe-links-settings).</span></span>

- <span data-ttu-id="29a82-137">Es kann bis zu 30 Minuten dauern, bis eine neue oder aktualisierte Richtlinie angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="29a82-137">Allow up to 30 minutes for a new or updated policy to be applied.</span></span>

- <span data-ttu-id="29a82-138">[Microsoft Defender werden kontinuierlich neue Features für Office 365 hinzugefügt.](defender-for-office-365.md#new-features-in-microsoft-defender-for-office-365)</span><span class="sxs-lookup"><span data-stu-id="29a82-138">[New features are continually being added to Microsoft Defender for Office 365](defender-for-office-365.md#new-features-in-microsoft-defender-for-office-365).</span></span> <span data-ttu-id="29a82-139">Wenn neue Features hinzugefügt werden, müssen Sie möglicherweise Anpassungen an Ihren vorhandenen Richtlinien für Tresor Links vornehmen.</span><span class="sxs-lookup"><span data-stu-id="29a82-139">As new features are added, you may need to make adjustments to your existing Safe Links policies.</span></span>

## <a name="configure-the-block-the-following-urls-list-in-the-microsoft-365-defender-portal"></a><span data-ttu-id="29a82-140">Konfigurieren der Liste "Blockieren der folgenden URLs" im Microsoft 365 Defender Portal</span><span class="sxs-lookup"><span data-stu-id="29a82-140">Configure the "Block the following URLs" list in the Microsoft 365 Defender portal</span></span>

<span data-ttu-id="29a82-141">The **Block the following URLs** list identifies the links that should always be blocked by Tresor Links scanning in supported apps.</span><span class="sxs-lookup"><span data-stu-id="29a82-141">The **Block the following URLs** list identifies the links that should always be blocked by Safe Links scanning in supported apps.</span></span> <span data-ttu-id="29a82-142">Weitere Informationen finden Sie in [der Liste "Blockieren der folgenden URLs" für Tresor Links.](safe-links.md#block-the-following-urls-list-for-safe-links)</span><span class="sxs-lookup"><span data-stu-id="29a82-142">For more information, see ["Block the following URLs" list for Safe Links](safe-links.md#block-the-following-urls-list-for-safe-links).</span></span>

1. <span data-ttu-id="29a82-143">Wechseln Sie im Portal Microsoft 365 Defender zu Richtlinien für **die E-Mail-& Zusammenarbeit** & Richtlinien für \> **Bedrohungsregeln** Tresor \>  \>  \> **Links.**</span><span class="sxs-lookup"><span data-stu-id="29a82-143">In the Microsoft 365 Defender portal, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** page \> **Policies** section \> **Safe Links**.</span></span>

2. <span data-ttu-id="29a82-144">Klicken Sie auf der Seite **Tresor Links** auf **globale Einstellungen.**</span><span class="sxs-lookup"><span data-stu-id="29a82-144">On the **Safe Links** page, click **Global settings**.</span></span> <span data-ttu-id="29a82-145">Wechseln Sie in der **angezeigten Tresor-Verknüpfungsrichtlinie für Ihre Organisation** zum **Feld "Folgende URLs blockieren".**</span><span class="sxs-lookup"><span data-stu-id="29a82-145">In the **Safe Links policy for your organization** fly out that appears, go to the **Block the following URLs** box.</span></span>

3. <span data-ttu-id="29a82-146">Konfigurieren Sie einen oder mehrere Einträge, wie in [der Eintragssyntax für die Liste "Blockieren der folgenden URLs"](safe-links.md#entry-syntax-for-the-block-the-following-urls-list)beschrieben.</span><span class="sxs-lookup"><span data-stu-id="29a82-146">Configure one or more entries as described in [Entry syntax for the "Block the following URLs" list](safe-links.md#entry-syntax-for-the-block-the-following-urls-list).</span></span>

   <span data-ttu-id="29a82-147">Klicken Sie nach Abschluss des Vorgangs auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="29a82-147">When you're finished, click **Save**.</span></span>

### <a name="configure-the-block-the-following-urls-list-in-powershell"></a><span data-ttu-id="29a82-148">Konfigurieren der Liste "Blockieren der folgenden URLs" in PowerShell</span><span class="sxs-lookup"><span data-stu-id="29a82-148">Configure the "Block the following URLs" list in PowerShell</span></span>

<span data-ttu-id="29a82-149">Ausführliche Informationen zur Eintragssyntax finden Sie unter [Eintragssyntax für die Liste "Blockieren der folgenden URLs".](safe-links.md#entry-syntax-for-the-block-the-following-urls-list)</span><span class="sxs-lookup"><span data-stu-id="29a82-149">For details about the entry syntax, see [Entry syntax for the "Block the following URLs" list](safe-links.md#entry-syntax-for-the-block-the-following-urls-list).</span></span>

<span data-ttu-id="29a82-150">Sie können das Cmdlet **"Get-AtpPolicyForO365"** verwenden, um vorhandene Einträge in der _BlockURLs-Eigenschaft_ anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="29a82-150">You can use the **Get-AtpPolicyForO365** cmdlet to view existing entries in the _BlockURLs_ property.</span></span>

- <span data-ttu-id="29a82-151">Um Werte hinzuzufügen, die vorhandene Einträge ersetzen, verwenden Sie die folgende Syntax in Exchange Online PowerShell oder Exchange Online Protection PowerShell:</span><span class="sxs-lookup"><span data-stu-id="29a82-151">To add values that will replace any existing entries, use the following syntax in Exchange Online PowerShell or Exchange Online Protection PowerShell:</span></span>

  ```powershell
  Set-AtpPolicyForO365 -BlockUrls "Entry1","Entry2",..."EntryN"
  ```

  <span data-ttu-id="29a82-152">In diesem Beispiel werden der Liste die folgenden Einträge hinzugefügt:</span><span class="sxs-lookup"><span data-stu-id="29a82-152">This example adds the following entries to the list:</span></span>

  - <span data-ttu-id="29a82-153">Blockieren Sie die Domäne, Unterdomänen und Pfade für fabrikam.com.</span><span class="sxs-lookup"><span data-stu-id="29a82-153">Block the domain, subdomains, and paths for fabrikam.com.</span></span>
  - <span data-ttu-id="29a82-154">Blockieren der Unterdomänen-Recherche, aber nicht der übergeordneten Domäne oder anderer Unterdomänen in tailspintoys.com</span><span class="sxs-lookup"><span data-stu-id="29a82-154">Block the subdomain research, but not the parent domain or other subdomains in tailspintoys.com</span></span>

  ```powershell
  Set-AtpPolicyForO365 -BlockUrls "fabrikam.com","https://research.tailspintoys.com*"
  ```

- <span data-ttu-id="29a82-155">Verwenden Sie die folgende Syntax, um Werte hinzuzufügen oder zu entfernen, ohne dass sich dies auf andere Einträge auswirkt:</span><span class="sxs-lookup"><span data-stu-id="29a82-155">To add or remove values without affecting other existing entries, use the following syntax:</span></span>

  ```powershell
  Set-AtpPolicyForO365 -BlockUrls @{Add="Entry1","Entry2"...; Remove="Entry3","Entry4"...}
  ```

  <span data-ttu-id="29a82-156">In diesem Beispiel wird ein neuer Eintrag für adatum.com hinzugefügt und der Eintrag für fabrikam.com entfernt.</span><span class="sxs-lookup"><span data-stu-id="29a82-156">This example adds a new entry for adatum.com, and removes the entry for fabrikam.com.</span></span>

  ```powershell
  Set-AtpPolicyForO365 -BlockUrls @{Add="adatum.com"; Remove="fabrikam"}
  ```

## <a name="configure-safe-links-protection-for-office-365-apps-in-the-microsoft-365-defender-portal"></a><span data-ttu-id="29a82-157">Konfigurieren Tresor Links-Schutzes für Office 365 Apps im Microsoft 365 Defender-Portal</span><span class="sxs-lookup"><span data-stu-id="29a82-157">Configure Safe Links protection for Office 365 apps in the Microsoft 365 Defender portal</span></span>

<span data-ttu-id="29a82-158">Tresor Der Linksschutz für Office 365 Apps gilt für Dokumente in unterstützten Office Desktop-, Mobil- und Web-Apps.</span><span class="sxs-lookup"><span data-stu-id="29a82-158">Safe Links protection for Office 365 apps applies to documents in supported Office desktop, mobile, and web apps.</span></span> <span data-ttu-id="29a82-159">Weitere Informationen finden Sie unter [Tresor Links-Einstellungen für Office 365 Apps.](safe-links.md#safe-links-settings-for-office-365-apps)</span><span class="sxs-lookup"><span data-stu-id="29a82-159">For more information, see [Safe Links settings for Office 365 apps](safe-links.md#safe-links-settings-for-office-365-apps).</span></span>

1. <span data-ttu-id="29a82-160">Wechseln Sie im Portal Microsoft 365 Defender zu Richtlinien für **die E-Mail-& Zusammenarbeit** & Richtlinien für \> **Bedrohungsregeln** Tresor \>  \>  \> **Links.**</span><span class="sxs-lookup"><span data-stu-id="29a82-160">In the Microsoft 365 Defender portal, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** page \> **Policies** section \> **Safe Links**.</span></span>

2. <span data-ttu-id="29a82-161">Klicken Sie auf der Seite **Tresor Links** auf **globale Einstellungen.**</span><span class="sxs-lookup"><span data-stu-id="29a82-161">On the **Safe Links** page, click **Global settings**.</span></span> <span data-ttu-id="29a82-162">Konfigurieren Sie in der **angezeigten Tresor-Verknüpfungsrichtlinie für Ihre Organisation** die folgenden Einstellungen im Einstellungen, die für Inhalte im Abschnitt **"Unterstützte Office 365 Apps" gelten:**</span><span class="sxs-lookup"><span data-stu-id="29a82-162">In the **Safe Links policy for your organization** fly out that appears, configure the following settings in the **Settings that apply to content in supported Office 365 apps** section:</span></span>

   - <span data-ttu-id="29a82-163">**Verwenden Sie Tresor Links in Office 365 Apps:** Überprüfen Sie, ob die Umschaltfläche rechts ist, um Tresor Links für unterstützte Office 365 Apps zu aktivieren: ![ Einschalten. ](../../media/scc-toggle-on.png)</span><span class="sxs-lookup"><span data-stu-id="29a82-163">**Use Safe Links in Office 365 apps**: Verify the toggle is to the right to enable Safe Links for supported Office 365 apps: ![Toggle on](../../media/scc-toggle-on.png).</span></span>

   - <span data-ttu-id="29a82-164">**Nicht nachverfolgen, wenn Benutzer in Office 365 Apps auf geschützte Links klicken:** Verschieben Sie die Umschaltfläche nach links, um Benutzerklicks im Zusammenhang mit blockierten URLs in unterstützten Office 365 Apps nachzuverfolgen: ![ Deaktivieren ](../../media/scc-toggle-off.png) .</span><span class="sxs-lookup"><span data-stu-id="29a82-164">**Do not track when users click protected links in Office 365 apps**: Move the toggle to the left to track user clicks related to blocked URLs in supported Office 365 apps: ![Toggle off](../../media/scc-toggle-off.png).</span></span>

   - <span data-ttu-id="29a82-165">**Benutzer dürfen nicht auf die ursprüngliche URL in Office 365 Apps klicken:** Stellen Sie sicher, dass sich die Umschaltfläche rechts befindet, um zu verhindern, dass Benutzer in unterstützten Office 365 Apps durch die ursprüngliche blockierte URL klicken: ![ Einschalten. ](../../media/scc-toggle-on.png)</span><span class="sxs-lookup"><span data-stu-id="29a82-165">**Do not let users click through to the original URL in Office 365 apps**: Verify the toggle is to the right to prevent users from clicking through to the original blocked URL in supported Office 365 apps: ![Toggle on](../../media/scc-toggle-on.png).</span></span>

   <span data-ttu-id="29a82-166">Klicken Sie nach Abschluss des Vorgangs auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="29a82-166">When you're finished, click **Save**.</span></span>

### <a name="configure-safe-links-protection-for-office-365-apps-in-powershell"></a><span data-ttu-id="29a82-167">Konfigurieren des Tresor Link-Schutzes für Office 365-Apps in PowerShell</span><span class="sxs-lookup"><span data-stu-id="29a82-167">Configure Safe Links protection for Office 365 apps in PowerShell</span></span>

<span data-ttu-id="29a82-168">Wenn Sie lieber PowerShell zum Konfigurieren Tresor Links-Schutzes für Office 365 Apps verwenden möchten, verwenden Sie die folgende Syntax in Exchange Online PowerShell oder Exchange Online Protection PowerShell:</span><span class="sxs-lookup"><span data-stu-id="29a82-168">If you'd rather use PowerShell to configure Safe Links protection for Office 365 apps, use the following syntax in Exchange Online PowerShell or Exchange Online Protection PowerShell:</span></span>

```powershell
Set-AtpPolicyForO365 [-EnableSafeLinksForO365Clients <$true | $false> [-AllowClickThrough <$true | $false>] [-TrackClicks <$true | $false>]
```

<span data-ttu-id="29a82-169">In diesem Beispiel werden die folgenden Einstellungen für den Schutz von Tresor Links in Office 365 Apps konfiguriert:</span><span class="sxs-lookup"><span data-stu-id="29a82-169">This example configures the following settings for Safe Links protection in Office 365 apps:</span></span>

- <span data-ttu-id="29a82-170">Tresor Links für Office 365 Apps sind aktiviert (der _Parameter EnableSafeLinksForO365Clients_ wird nicht verwendet, und der Standardwert ist $true).</span><span class="sxs-lookup"><span data-stu-id="29a82-170">Safe Links for Office 365 apps is turned on (we aren't using the _EnableSafeLinksForO365Clients_ parameter, and the default value is $true).</span></span>
- <span data-ttu-id="29a82-171">Benutzerklicks im Zusammenhang mit blockierten URLs in unterstützten Office 365 Apps werden nachverfolgt.</span><span class="sxs-lookup"><span data-stu-id="29a82-171">User clicks related to blocked URLs in supported Office 365 apps are tracked.</span></span>
- <span data-ttu-id="29a82-172">Benutzer können in unterstützten Office 365 Apps nicht auf die ursprüngliche blockierte URL klicken (wir verwenden nicht den _Parameter "AllowClickThrough",_ und der Standardwert ist $false).</span><span class="sxs-lookup"><span data-stu-id="29a82-172">Users are not allowed to click through to the original blocked URL in supported Office 365 apps (we aren't using the _AllowClickThrough_ parameter, and the default value is $false).</span></span>

```powershell
Set-AtpPolicyForO365 -TrackClicks $true
```

<span data-ttu-id="29a82-173">Ausführliche Informationen zu Syntax und Parametern finden Sie unter ["Set-AtpPolicyForO365".](/powershell/module/exchange/set-atppolicyforo365)</span><span class="sxs-lookup"><span data-stu-id="29a82-173">For detailed syntax and parameter information, see [Set-AtpPolicyForO365](/powershell/module/exchange/set-atppolicyforo365).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="29a82-174">Wie können Sie feststellen, dass diese Verfahren erfolgreich waren?</span><span class="sxs-lookup"><span data-stu-id="29a82-174">How do you know these procedures worked?</span></span>

<span data-ttu-id="29a82-175">Führen Sie einen der folgenden Schritte aus, um zu überprüfen, ob Sie die globalen Einstellungen für Tresor Links (die Liste **der folgenden URLs** blockieren und die Office 365 App-Schutzeinstellungen) erfolgreich konfiguriert haben:</span><span class="sxs-lookup"><span data-stu-id="29a82-175">To verify that you've successfully configured the global settings for Safe Links (the **Block the following URLs** list and the Office 365 app protection settings), do any of the following steps:</span></span>

- <span data-ttu-id="29a82-176">Wechseln Sie im Microsoft 365 Defender Portal zur Seite "Richtlinien für **E-Mail-& Zusammenarbeit** & Richtlinien für \>  \> **Bedrohungsregeln",** \>  \> **Tresor Links** auf \> **"Globale Einstellungen"** klicken, und überprüfen Sie die Einstellungen im angezeigten Flyout.</span><span class="sxs-lookup"><span data-stu-id="29a82-176">In the Microsoft 365 Defender portal, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** page \> **Policies** section \> **Safe Links** \> click **Global settings**, and verify the settings in the fly out that appears.</span></span>

- <span data-ttu-id="29a82-177">Führen Sie in Exchange Online PowerShell oder Exchange Online Protection PowerShell den folgenden Befehl aus, und überprüfen Sie die Einstellungen:</span><span class="sxs-lookup"><span data-stu-id="29a82-177">In Exchange Online PowerShell or Exchange Online Protection PowerShell, run the following command and verify the settings:</span></span>

  ```powershell
  Get-AtpPolicyForO365 | Format-List BlockUrls,EnableSafeLinksForO365Clients,AllowClickThrough,TrackClicks
  ```

  <span data-ttu-id="29a82-178">Ausführliche Informationen zu Syntax und Parametern finden Sie unter ["Get-AtpPolicyForO365".](/powershell/module/exchange/get-atppolicyforo365)</span><span class="sxs-lookup"><span data-stu-id="29a82-178">For detailed syntax and parameter information, see [Get-AtpPolicyForO365](/powershell/module/exchange/get-atppolicyforo365).</span></span>
