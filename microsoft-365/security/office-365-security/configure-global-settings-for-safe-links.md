---
title: Konfigurieren globaler Einstellungen für Einstellungen für sichere Links in Defender für Office 365
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
description: Administratoren können erfahren, wie Sie globale Einstellungen (die Liste "Folgende URLs blockieren" und Schutz für Office 365-Apps) für sichere Links in Microsoft Defender für Office 365 anzeigen und konfigurieren.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: d52a4dc5ed35ec73c1410d6428a581b098bf2c52
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/18/2021
ms.locfileid: "50287461"
---
# <a name="configure-global-settings-for-safe-links-in-microsoft-defender-for-office-365"></a><span data-ttu-id="782b6-103">Konfigurieren der globalen Einstellungen für sichere Links in Microsoft Defender für Office 365</span><span class="sxs-lookup"><span data-stu-id="782b6-103">Configure global settings for Safe Links in Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="782b6-104">**Gilt für**</span><span class="sxs-lookup"><span data-stu-id="782b6-104">**Applies to**</span></span>
- [<span data-ttu-id="782b6-105">Microsoft Defender für Office 365 Plan 1 und Plan 2</span><span class="sxs-lookup"><span data-stu-id="782b6-105">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="782b6-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="782b6-106">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

> [!IMPORTANT]
> <span data-ttu-id="782b6-107">Dieser Artikel richtet sich an Geschäftskunden, die über [Microsoft Defender für Office 365](office-365-atp.md) verfügen.</span><span class="sxs-lookup"><span data-stu-id="782b6-107">This article is intended for business customers who have [Microsoft Defender for Office 365](office-365-atp.md).</span></span> <span data-ttu-id="782b6-108">Informationen zu Safelinks in Outlook finden Sie unter Advanced [Outlook.com Security](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).</span><span class="sxs-lookup"><span data-stu-id="782b6-108">If you are a home user looking for information about Safelinks in Outlook, see [Advanced Outlook.com security](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).</span></span>

<span data-ttu-id="782b6-109">Sichere Links ist ein Feature in [Microsoft Defender für Office 365,](office-365-atp.md) das die URL-Überprüfung eingehender E-Mail-Nachrichten im Nachrichtenfluss sowie die Zeit der Klicküberprüfung von URLs und Links in E-Mail-Nachrichten und an anderen Speicherorten ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="782b6-109">Safe Links is a feature in [Microsoft Defender for Office 365](office-365-atp.md) that provides URL scanning of inbound email messages in mail flow, and time of click verification of URLs and links in email messages and in other locations.</span></span> <span data-ttu-id="782b6-110">Weitere Informationen finden Sie unter ["Sichere Links" in Microsoft Defender für Office 365.](atp-safe-links.md)</span><span class="sxs-lookup"><span data-stu-id="782b6-110">For more information, see [Safe Links in Microsoft Defender for Office 365](atp-safe-links.md).</span></span>

<span data-ttu-id="782b6-111">Sie konfigurieren die meisten Einstellungen für sichere Links in Richtlinien für sichere Links.</span><span class="sxs-lookup"><span data-stu-id="782b6-111">You configure most Safe Links settings in Safe Links policies.</span></span> <span data-ttu-id="782b6-112">Anweisungen finden Sie unter [Einrichten von Richtlinien für sichere Links in Microsoft Defender für Office 365.](set-up-atp-safe-links-policies.md)</span><span class="sxs-lookup"><span data-stu-id="782b6-112">For instructions, see [Set up Safe Links policies in Microsoft Defender for Office 365](set-up-atp-safe-links-policies.md).</span></span>

<span data-ttu-id="782b6-113">Sichere Links verwenden jedoch auch globale Einstellungen, die für alle Benutzer gelten, die in aktiven Richtlinien für sichere Links enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="782b6-113">But, Safe Links also uses global settings that apply to all users who are included in any active Safe Links policies.</span></span> <span data-ttu-id="782b6-114">Diese globalen Einstellungsbereich:</span><span class="sxs-lookup"><span data-stu-id="782b6-114">These global settings area:</span></span>

- <span data-ttu-id="782b6-115">Die **Liste der folgenden URLs blockieren.**</span><span class="sxs-lookup"><span data-stu-id="782b6-115">The **Block the following URLs** list.</span></span> <span data-ttu-id="782b6-116">Weitere Informationen finden Sie unter ["Blockieren der folgenden URLs" für sichere Links.](atp-safe-links.md#block-the-following-urls-list-for-safe-links)</span><span class="sxs-lookup"><span data-stu-id="782b6-116">For more information, see ["Block the following URLs" list for Safe Links](atp-safe-links.md#block-the-following-urls-list-for-safe-links)</span></span>
- <span data-ttu-id="782b6-117">Schutz sicherer Links für Office 365-Apps.</span><span class="sxs-lookup"><span data-stu-id="782b6-117">Safe Links protection for Office 365 apps.</span></span> <span data-ttu-id="782b6-118">Weitere Informationen finden Sie unter Einstellungen für [sichere Links für Office 365-Apps.](atp-safe-links.md#safe-links-settings-for-office-365-apps)</span><span class="sxs-lookup"><span data-stu-id="782b6-118">For more information, see [Safe Links settings for Office 365 apps](atp-safe-links.md#safe-links-settings-for-office-365-apps).</span></span>

<span data-ttu-id="782b6-119">Sie können die globalen Einstellungen für sichere Links im Security & Compliance Center oder in PowerShell konfigurieren (Exchange Online PowerShell für berechtigte Microsoft 365-Organisationen mit Postfächern in Exchange Online; eigenständige EOP PowerShell für Organisationen ohne Exchange Online-Postfächer, aber mit Microsoft Defender für Office 365-Add-On-Abonnements).</span><span class="sxs-lookup"><span data-stu-id="782b6-119">You can configure the global Safe Links settings in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for eligible Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes, but with Microsoft Defender for Office 365 add-on subscriptions).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="782b6-120">Was sollten Sie wissen, bevor Sie beginnen?</span><span class="sxs-lookup"><span data-stu-id="782b6-120">What do you need to know before you begin?</span></span>

- <span data-ttu-id="782b6-121">Die von den globalen Einstellungen für sichere Links bereitgestellten Features werden nur auf Benutzer angewendet, die in aktiven Richtlinien für sichere Links enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="782b6-121">The features provided by global settings for Safe Links are only applied to users who are included in active Safe Links policies.</span></span> <span data-ttu-id="782b6-122">Es gibt keine integrierte oder standardmäßige Richtlinie für sichere Links. Daher müssen Sie mindestens eine Richtlinie für sichere Links erstellen, damit diese globalen Einstellungen aktiv sind.</span><span class="sxs-lookup"><span data-stu-id="782b6-122">There is no built-in or default Safe Links policy, so you need to create at least one Safe Links policy in order for these global settings to be active.</span></span> <span data-ttu-id="782b6-123">Anweisungen finden Sie unter [Einrichten von Richtlinien für sichere Links in Microsoft Defender für Office 365.](set-up-atp-safe-links-policies.md)</span><span class="sxs-lookup"><span data-stu-id="782b6-123">For instructions, see [Set up Safe Links policies in Microsoft Defender for Office 365](set-up-atp-safe-links-policies.md).</span></span>

- <span data-ttu-id="782b6-124">Sie öffnen das Security & Compliance Center unter <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="782b6-124">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="782b6-125">Um direkt zur Seite "Sichere **Links" zu** wechseln, verwenden Sie <https://protection.office.com/safelinksv2> .</span><span class="sxs-lookup"><span data-stu-id="782b6-125">To go directly to the **Safe Links** page, use <https://protection.office.com/safelinksv2>.</span></span>

- <span data-ttu-id="782b6-126">Wie Sie eine Verbindung mit Exchange Online PowerShell herstellen, finden Sie unter [Herstellen einer Verbindung mit Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="782b6-126">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="782b6-127">Informationen zum Herstellen einer Verbindung mit dem eigenständigen Exchange Online Protection PowerShell finden Sie unter [Verbinden mit PowerShell in Exchange Online Protection](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="782b6-127">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="782b6-128">Bevor Sie die Verfahren in diesem Artikel ausführen können, müssen Ihnen im Security & Compliance Center Berechtigungen zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="782b6-128">You need to be assigned permissions in the Security & Compliance Center before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="782b6-129">Zum Konfigurieren der globalen Einstellungen für sichere Links müssen Sie Mitglied der Rollengruppe **"Organisationsverwaltung"** oder **"Sicherheitsadministrator"** sein.</span><span class="sxs-lookup"><span data-stu-id="782b6-129">To configure the global settings for Safe Links, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="782b6-130">Für den schreibgeschützten Zugriff auf die globalen Einstellungen für sichere  Links müssen Sie Mitglied der Rollengruppe "Globaler Leser" oder **"Sicherheitsleseprogramm"** sein.</span><span class="sxs-lookup"><span data-stu-id="782b6-130">For read-only access to the global settings for Safe Links, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="782b6-131">Weitere Informationen finden Sie unter [Berechtigungen im Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="782b6-131">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

  <span data-ttu-id="782b6-132">**Hinweise**:</span><span class="sxs-lookup"><span data-stu-id="782b6-132">**Notes**:</span></span>

  - <span data-ttu-id="782b6-133">Durch das Hinzufügen von Benutzern zur entsprechenden Azure Active Directory-Rolle im Microsoft 365 Admin Center erhalten Benutzer die erforderlichen Berechtigungen im Security & Compliance Center _und_ Berechtigungen für andere Features in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="782b6-133">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Security & Compliance Center _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="782b6-134">Weitere Informationen finden Sie unter [Informationen zu Administratorrollen](../../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="782b6-134">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  - <span data-ttu-id="782b6-135">Die Rollengruppe **Organisationsverwaltung mit Leserechten** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) ermöglicht auch einen schreibgeschützten Zugriff auf das Feature.</span><span class="sxs-lookup"><span data-stu-id="782b6-135">The **View-Only Organization Management** role group in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

- <span data-ttu-id="782b6-136">Die empfohlenen Werte für die globalen Einstellungen für sichere Links finden Sie unter "Einstellungen für [sichere Links".](recommended-settings-for-eop-and-office365-atp.md#safe-links-settings)</span><span class="sxs-lookup"><span data-stu-id="782b6-136">For our recommended values for the global settings for Safe Links, see [Safe Links settings](recommended-settings-for-eop-and-office365-atp.md#safe-links-settings).</span></span>

- <span data-ttu-id="782b6-137">Es kann bis zu 30 Minuten dauern, bis eine neue oder aktualisierte Richtlinie angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="782b6-137">Allow up to 30 minutes for a new or updated policy to be applied.</span></span>

- <span data-ttu-id="782b6-138">[Microsoft Defender für Office 365](office-365-atp.md#new-features-in-microsoft-defender-for-office-365)werden ständig neue Features hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="782b6-138">[New features are continually being added to Microsoft Defender for Office 365](office-365-atp.md#new-features-in-microsoft-defender-for-office-365).</span></span> <span data-ttu-id="782b6-139">Wenn neue Features hinzugefügt werden, müssen Sie möglicherweise Anpassungen an Ihren vorhandenen Richtlinien für sichere Links vornehmen.</span><span class="sxs-lookup"><span data-stu-id="782b6-139">As new features are added, you may need to make adjustments to your existing Safe Links policies.</span></span>

## <a name="configure-the-block-the-following-urls-list-in-the-security--compliance-center"></a><span data-ttu-id="782b6-140">Konfigurieren der Liste "Blockieren der folgenden URLs" im Security & Compliance Center</span><span class="sxs-lookup"><span data-stu-id="782b6-140">Configure the "Block the following URLs" list in the Security & Compliance Center</span></span>

<span data-ttu-id="782b6-141">In **der Liste "Blockieren" der folgenden URLs** werden die Links identifiziert, die von der Überprüfung auf sichere Links in unterstützten Apps immer blockiert werden sollten.</span><span class="sxs-lookup"><span data-stu-id="782b6-141">The **Block the following URLs** list identifies the links that should always be blocked by Safe Links scanning in supported apps.</span></span> <span data-ttu-id="782b6-142">Weitere Informationen finden Sie unter ["Blockieren der folgenden URLs" für sichere Links.](atp-safe-links.md#block-the-following-urls-list-for-safe-links)</span><span class="sxs-lookup"><span data-stu-id="782b6-142">For more information, see ["Block the following URLs" list for Safe Links](atp-safe-links.md#block-the-following-urls-list-for-safe-links).</span></span>

1. <span data-ttu-id="782b6-143">Wechseln Sie im Security & Compliance  Center zu "AtP-Sichere Links" für die Bedrohungsverwaltungsrichtlinie, und klicken Sie dann auf \>  \>  **"Globale Einstellungen".**</span><span class="sxs-lookup"><span data-stu-id="782b6-143">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Links**, and then click **Global settings**.</span></span>

2. <span data-ttu-id="782b6-144">Wechseln Sie **in der** angezeigten Richtlinie für sichere Links für Ihre Organisation zum Feld "Folgende **URLs** blockieren".</span><span class="sxs-lookup"><span data-stu-id="782b6-144">In the **Safe Links policy for your organization** fly out that appears, go to the **Block the following URLs** box.</span></span>

3. <span data-ttu-id="782b6-145">Konfigurieren Sie einen oder mehrere Einträge, wie in der Eintragssyntax für die Liste ["Folgende URLs blockieren" beschrieben.](atp-safe-links.md#entry-syntax-for-the-block-the-following-urls-list)</span><span class="sxs-lookup"><span data-stu-id="782b6-145">Configure one or more entries as described in [Entry syntax for the "Block the following URLs" list](atp-safe-links.md#entry-syntax-for-the-block-the-following-urls-list).</span></span>

   <span data-ttu-id="782b6-146">Klicken Sie nach Abschluss des Vorgangs auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="782b6-146">When you're finished, click **Save**.</span></span>

### <a name="configure-the-block-the-following-urls-list-in-powershell"></a><span data-ttu-id="782b6-147">Konfigurieren der Liste "Folgende URLs blockieren" in PowerShell</span><span class="sxs-lookup"><span data-stu-id="782b6-147">Configure the "Block the following URLs" list in PowerShell</span></span>

<span data-ttu-id="782b6-148">Weitere Informationen zur Eintragssyntax finden Sie in der Eintragssyntax für die Liste ["Blockieren der folgenden URLs".](atp-safe-links.md#entry-syntax-for-the-block-the-following-urls-list)</span><span class="sxs-lookup"><span data-stu-id="782b6-148">For details about the entry syntax, see [Entry syntax for the "Block the following URLs" list](atp-safe-links.md#entry-syntax-for-the-block-the-following-urls-list).</span></span>

<span data-ttu-id="782b6-149">Mit dem **Cmdlet "Get-AtpPolicyForO365"** können Sie vorhandene Einträge in der Eigenschaft _"BlockURLs"_ anzeigen.</span><span class="sxs-lookup"><span data-stu-id="782b6-149">You can use the **Get-AtpPolicyForO365** cmdlet to view existing entries in the _BlockURLs_ property.</span></span>

- <span data-ttu-id="782b6-150">Verwenden Sie die folgende Syntax in Exchange Online PowerShell oder Exchange Online Protection PowerShell, um Werte hinzuzufügen, die vorhandene Einträge ersetzen:</span><span class="sxs-lookup"><span data-stu-id="782b6-150">To add values that will replace any existing entries, use the following syntax in Exchange Online PowerShell or Exchange Online Protection PowerShell:</span></span>

  ```powershell
  Set-AtpPolicyForO365 -BlockUrls "Entry1","Entry2",..."EntryN"
  ```

  <span data-ttu-id="782b6-151">In diesem Beispiel werden der Liste die folgenden Einträge hinzugefügt:</span><span class="sxs-lookup"><span data-stu-id="782b6-151">This example adds the following entries to the list:</span></span>

  - <span data-ttu-id="782b6-152">Blockieren Sie die Domäne, Unterdomänen und Pfade für fabrikam.com.</span><span class="sxs-lookup"><span data-stu-id="782b6-152">Block the domain, subdomains, and paths for fabrikam.com.</span></span>
  - <span data-ttu-id="782b6-153">Blockieren der Unterdomänenforschung, aber nicht der übergeordneten Domäne oder anderer Unterdomänen in tailspintoys.com</span><span class="sxs-lookup"><span data-stu-id="782b6-153">Block the subdomain research, but not the parent domain or other subdomains in tailspintoys.com</span></span>

  ```powershell
  Set-AtpPolicyForO365 -BlockUrls "fabrikam.com","https://research.tailspintoys.com*"
  ```

- <span data-ttu-id="782b6-154">Verwenden Sie die folgende Syntax, um Werte ohne Auswirkungen auf andere Einträge hinzuzufügen oder zu entfernen:</span><span class="sxs-lookup"><span data-stu-id="782b6-154">To add or remove values without affecting other existing entries, use the following syntax:</span></span>

  ```powershell
  Set-AtpPolicyForO365 -BlockUrls @{Add="Entry1","Entry2"...; Remove="Entry3","Entry4"...}
  ```

  <span data-ttu-id="782b6-155">In diesem Beispiel wird ein neuer Eintrag für adatum.com und der Eintrag für die fabrikam.com.</span><span class="sxs-lookup"><span data-stu-id="782b6-155">This example adds a new entry for adatum.com, and removes the entry for fabrikam.com.</span></span>

  ```powershell
  Set-AtpPolicyForO365 -BlockUrls @{Add="adatum.com"; Remove="fabrikam"}
  ```

## <a name="configure-safe-links-protection-for-office-365-apps-in-the-security--compliance-center"></a><span data-ttu-id="782b6-156">Konfigurieren des Schutzes sicherer Links für Office 365-Apps im Security & Compliance Center</span><span class="sxs-lookup"><span data-stu-id="782b6-156">Configure Safe Links protection for Office 365 apps in the Security & Compliance Center</span></span>

<span data-ttu-id="782b6-157">Der Schutz sicherer Links für Office 365-Apps gilt für Dokumente in unterstützten Office-Desktop-, Mobile- und Web-Apps.</span><span class="sxs-lookup"><span data-stu-id="782b6-157">Safe Links protection for Office 365 apps applies to documents in supported Office desktop, mobile, and web apps.</span></span> <span data-ttu-id="782b6-158">Weitere Informationen finden Sie unter Einstellungen für [sichere Links für Office 365-Apps.](atp-safe-links.md#safe-links-settings-for-office-365-apps)</span><span class="sxs-lookup"><span data-stu-id="782b6-158">For more information, see [Safe Links settings for Office 365 apps](atp-safe-links.md#safe-links-settings-for-office-365-apps).</span></span>

1. <span data-ttu-id="782b6-159">Wechseln Sie im Security & Compliance  Center zu "AtP-Sichere Links" für die Bedrohungsverwaltungsrichtlinie, und klicken Sie dann auf \>  \>  **"Globale Einstellungen".**</span><span class="sxs-lookup"><span data-stu-id="782b6-159">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Links**, and then click **Global settings**.</span></span>

2. <span data-ttu-id="782b6-160">Konfigurieren Sie **in** der angezeigten Richtlinie für sichere Links für Ihre Organisation die folgenden Einstellungen in den Einstellungen, die für Inhalte außer im Abschnitt "E-Mail" **gelten:**</span><span class="sxs-lookup"><span data-stu-id="782b6-160">In the **Safe Links policy for your organization** fly out that appears, configure the following settings in the **Settings that apply to content except email** section:</span></span>

   - <span data-ttu-id="782b6-161">**Office 365-Anwendungen:** Stellen Sie sicher, dass der Umschalter rechts ist, um sichere Links für unterstützte Office 365-Apps zu aktivieren: ![ Umschalten. ](../../media/scc-toggle-on.png)</span><span class="sxs-lookup"><span data-stu-id="782b6-161">**Office 365 applications**: Verify the toggle is to the right to enable Safe Links for supported Office 365 apps: ![Toggle on](../../media/scc-toggle-on.png).</span></span>

   - <span data-ttu-id="782b6-162">**Nicht nachverfolgen, wenn** Benutzer auf "Sichere Links" klicken: Umschalten nach links, um Benutzerklicks im Zusammenhang mit blockierten URLs in unterstützten Office 365-Apps nachverfolgt: ![ Umschalten ](../../media/scc-toggle-off.png) .</span><span class="sxs-lookup"><span data-stu-id="782b6-162">**Do not track when users click Safe Links**: Move the toggle to the left to track user clicks related to blocked URLs in supported Office 365 apps: ![Toggle off](../../media/scc-toggle-off.png).</span></span>

   - <span data-ttu-id="782b6-163">Benutzer dürfen nicht auf sichere Links zur ursprünglichen **URL** klicken: Überprüfen Sie, ob die Umschalte auf der rechten Seite ist, um zu verhindern, dass Benutzer auf die ursprüngliche blockierte URL in unterstützten Office 365-Apps klicken: ![ Umschalten. ](../../media/scc-toggle-on.png)</span><span class="sxs-lookup"><span data-stu-id="782b6-163">**Do not let users click through Safe Links to the original URL**: Verify the toggle is to the right to prevent users from clicking through to the original blocked URL in supported Office 365 apps: ![Toggle on](../../media/scc-toggle-on.png).</span></span>

   <span data-ttu-id="782b6-164">Klicken Sie nach Abschluss des Vorgangs auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="782b6-164">When you're finished, click **Save**.</span></span>

### <a name="configure-safe-links-protection-for-office-365-apps-in-powershell"></a><span data-ttu-id="782b6-165">Konfigurieren des Schutzes sicherer Links für Office 365-Apps in PowerShell</span><span class="sxs-lookup"><span data-stu-id="782b6-165">Configure Safe Links protection for Office 365 apps in PowerShell</span></span>

<span data-ttu-id="782b6-166">Wenn Sie lieber PowerShell zum Konfigurieren des Schutzes sicherer Links für Office 365-Apps verwenden möchten, verwenden Sie die folgende Syntax in Exchange Online PowerShell oder Exchange Online Protection PowerShell:</span><span class="sxs-lookup"><span data-stu-id="782b6-166">If you'd rather use PowerShell to configure Safe Links protection for Office 365 apps, use the following syntax in Exchange Online PowerShell or Exchange Online Protection PowerShell:</span></span>

```powershell
Set-AtpPolicyForO365 [-EnableSafeLinksForO365Clients <$true | $false> [-AllowClickThrough <$true | $false>] [-TrackClicks <$true | $false>]
```

<span data-ttu-id="782b6-167">In diesem Beispiel werden die folgenden Einstellungen für den Schutz sicherer Links in Office 365-Apps konfiguriert:</span><span class="sxs-lookup"><span data-stu-id="782b6-167">This example configures the following settings for Safe Links protection in Office 365 apps:</span></span>

- <span data-ttu-id="782b6-168">Sichere Links für Office 365-Apps sind aktiviert (der Parameter _"EnableSafeLinksForO365Clients"_ wird nicht verwendet, und der Standardwert ist $true).</span><span class="sxs-lookup"><span data-stu-id="782b6-168">Safe Links for Office 365 apps is turned on (we aren't using the _EnableSafeLinksForO365Clients_ parameter, and the default value is $true).</span></span>
- <span data-ttu-id="782b6-169">Benutzerklicks im Zusammenhang mit blockierten URLs in unterstützten Office 365-Apps werden nachverfolgt.</span><span class="sxs-lookup"><span data-stu-id="782b6-169">User clicks related to blocked URLs in supported Office 365 apps are tracked.</span></span>
- <span data-ttu-id="782b6-170">Benutzer dürfen nicht auf die ursprüngliche blockierte URL in unterstützten Office 365-Apps klicken (wir verwenden den Parameter _"AllowClickThrough"_ nicht, und der Standardwert ist $false).</span><span class="sxs-lookup"><span data-stu-id="782b6-170">Users are not allowed to click through to the original blocked URL in supported Office 365 apps (we aren't using the _AllowClickThrough_ parameter, and the default value is $false).</span></span>

```powershell
Set-AtpPolicyForO365 -TrackClicks $true
```

<span data-ttu-id="782b6-171">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Set-AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/set-atppolicyforo365).</span><span class="sxs-lookup"><span data-stu-id="782b6-171">For detailed syntax and parameter information, see [Set-AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/set-atppolicyforo365).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="782b6-172">Wie können Sie feststellen, dass diese Verfahren erfolgreich waren?</span><span class="sxs-lookup"><span data-stu-id="782b6-172">How do you know these procedures worked?</span></span>

<span data-ttu-id="782b6-173">Gehen Sie wie folgt vor, um sicherzustellen, dass Sie die globalen Einstellungen für sichere Links (die Liste "Folgende **URLs** blockieren" und die Office 365-App-Schutzeinstellungen) erfolgreich konfiguriert haben:</span><span class="sxs-lookup"><span data-stu-id="782b6-173">To verify that you've successfully configured the global settings for Safe Links (the **Block the following URLs** list and the Office 365 app protection settings), do any of the following steps:</span></span>

- <span data-ttu-id="782b6-174">Wechseln Sie im Security & Compliance  Center zu "AtP-Sichere Links" für die Bedrohungsverwaltung, klicken Sie auf "Globale Einstellungen", und überprüfen Sie die angezeigten Einstellungen \>  \> im Flyout. </span><span class="sxs-lookup"><span data-stu-id="782b6-174">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Links**, click **Global settings**, and verify the settings in the fly out that appears.</span></span>

- <span data-ttu-id="782b6-175">Führen Sie in Exchange Online PowerShell oder Exchange Online Protection PowerShell den folgenden Befehl aus, und überprüfen Sie die Einstellungen:</span><span class="sxs-lookup"><span data-stu-id="782b6-175">In Exchange Online PowerShell or Exchange Online Protection PowerShell, run the following command and verify the settings:</span></span>

  ```powershell
  Get-AtpPolicyForO365 | Format-List BlockUrls,EnableSafeLinksForO365Clients,AllowClickThrough,TrackClicks
  ```

  <span data-ttu-id="782b6-176">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Get-AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/get-atppolicyforo365).</span><span class="sxs-lookup"><span data-stu-id="782b6-176">For detailed syntax and parameter information, see [Get-AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/get-atppolicyforo365).</span></span>
