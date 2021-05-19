---
title: Verwalten Ihrer Zulässigen und Blöcke in der Liste "Mandanten zulassen/blockieren"
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: Administratoren können erfahren, wie Sie im Sicherheitsportal in der Liste "Mandanten zulassen/blockieren" Zulassen und Blockieren von Zulassen und Blockieren konfigurieren.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 270e38d65857de2f4d06460fb3bb77f72a165ecf
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2021
ms.locfileid: "52538963"
---
# <a name="manage-the-tenant-allowblock-list"></a><span data-ttu-id="0b3a8-103">Verwalten der Zulassungs-/Sperrliste des Mandanten</span><span class="sxs-lookup"><span data-stu-id="0b3a8-103">Manage the Tenant Allow/Block List</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="0b3a8-104">**Gilt für**</span><span class="sxs-lookup"><span data-stu-id="0b3a8-104">**Applies to**</span></span>
- [<span data-ttu-id="0b3a8-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="0b3a8-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="0b3a8-106">Microsoft Defender für Office 365 Plan 1 und Plan 2</span><span class="sxs-lookup"><span data-stu-id="0b3a8-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="0b3a8-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="0b3a8-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

> [!NOTE]
>
> <span data-ttu-id="0b3a8-108">Die in diesem Artikel beschriebenen Features befinden sich in Vorschau, können geändert werden und sind nicht in allen Organisationen verfügbar.</span><span class="sxs-lookup"><span data-stu-id="0b3a8-108">The features described in this article are in Preview, are subject to change, and are not available in all organizations.</span></span>  <span data-ttu-id="0b3a8-109">Wenn Ihre Organisation nicht über die in diesem Artikel beschriebenen Spooffunktionen verfügt, lesen Sie die ältere [Spoofverwaltungserfahrung unter Manage spoofed senders using the spoof intelligence policy and spoof intelligence insight in EOP](walkthrough-spoof-intelligence-insight.md).</span><span class="sxs-lookup"><span data-stu-id="0b3a8-109">If your organization does not have the spoof features as described in this article, see the older spoof management experience at [Manage spoofed senders using the spoof intelligence policy and spoof intelligence insight in EOP](walkthrough-spoof-intelligence-insight.md).</span></span>
>
> <span data-ttu-id="0b3a8-110">Sie können zu **diesem** Zeitpunkt keine zulässigen URL- oder Dateielemente in der Mandanten zulassen/blockieren-Liste konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="0b3a8-110">You can't **configure** allowed URL or file items in the Tenant Allow/Block List at this time.</span></span>

<span data-ttu-id="0b3a8-111">In Microsoft 365 Organisationen mit Postfächern in Exchange Online oder eigenständigen Exchange Online Protection (EOP)-Organisationen ohne Exchange Online Postfächer können Sie mit dem EOP-Filter-Urteil nicht einverstanden sein.</span><span class="sxs-lookup"><span data-stu-id="0b3a8-111">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, you might disagree with the EOP filtering verdict.</span></span> <span data-ttu-id="0b3a8-112">Beispielsweise kann eine gute Nachricht als ungültig (falsch positiv) gekennzeichnet werden, oder eine schlechte Nachricht kann als ungültig (falsch negativ) zugelassen werden.</span><span class="sxs-lookup"><span data-stu-id="0b3a8-112">For example, a good message might be marked as bad (a false positive), or a bad message might be allowed through (a false negative).</span></span>

<span data-ttu-id="0b3a8-113">Mit der Mandanten-Allow/Block-Liste im Security & Compliance Center können Sie die Filterungs-Microsoft 365 manuell außer Kraft setzen.</span><span class="sxs-lookup"><span data-stu-id="0b3a8-113">The Tenant Allow/Block List in the Security & Compliance Center gives you a way to manually override the Microsoft 365 filtering verdicts.</span></span> <span data-ttu-id="0b3a8-114">Die Mandanten zulassen/blockieren Liste wird während des Nachrichtenflusses und zum Zeitpunkt der Benutzerklicks verwendet.</span><span class="sxs-lookup"><span data-stu-id="0b3a8-114">The Tenant Allow/Block List is used during mail flow and at the time of user clicks.</span></span> <span data-ttu-id="0b3a8-115">Sie können die folgenden Arten von Außerkraftsetzungen angeben:</span><span class="sxs-lookup"><span data-stu-id="0b3a8-115">You can specify the following types of overrides:</span></span>

- <span data-ttu-id="0b3a8-116">ZU blockierende URLs.</span><span class="sxs-lookup"><span data-stu-id="0b3a8-116">URLs to block.</span></span>
- <span data-ttu-id="0b3a8-117">Zu blockierende Dateien.</span><span class="sxs-lookup"><span data-stu-id="0b3a8-117">Files to block.</span></span>
- <span data-ttu-id="0b3a8-118">Zu erlaubende Massen-E-Mail-Absenderdomänen.</span><span class="sxs-lookup"><span data-stu-id="0b3a8-118">Bulk mail sender domains to allow.</span></span> <span data-ttu-id="0b3a8-119">Weitere Informationen zu Massen-E-Mails, der Massenvertrauensstufe (Bulk Confidence Level, BCL) und der Massen-E-Mail-Filterung nach Antispamrichtlinien finden Sie unter [Bulk Complaint Level (BCL) in EOP](bulk-complaint-level-values.md).</span><span class="sxs-lookup"><span data-stu-id="0b3a8-119">For more information about bulk mail, the bulk confidence level (BCL), and bulk mail filtering by anti-spam policies, see [Bulk complaint level (BCL) in EOP](bulk-complaint-level-values.md).</span></span>
- <span data-ttu-id="0b3a8-120">Spoofed senders to allow or block.</span><span class="sxs-lookup"><span data-stu-id="0b3a8-120">Spoofed senders to allow or block.</span></span> <span data-ttu-id="0b3a8-121">Wenn Sie das Allow- oder Block-Urteil in der [Spoof Intelligence-Einsicht](learn-about-spoof-intelligence.md)außer Kraft setzen, wird der gefälschte Absender zu einem manuellen Zulassen- oder Blockiereneintrag, der nur auf der Registerkarte **Spoof** in der Mandanten-Zulassen-/Sperrliste angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="0b3a8-121">If you override the allow or block verdict in the [spoof intelligence insight](learn-about-spoof-intelligence.md), the spoofed sender becomes a manual allow or block entry that only appears on the **Spoof** tab in the Tenant Allow/Block List.</span></span> <span data-ttu-id="0b3a8-122">Sie können hier auch manuell Zulassen oder Blockieren von Einträgen für spoofierte Absender erstellen, bevor sie von Spoof Intelligence erkannt werden.</span><span class="sxs-lookup"><span data-stu-id="0b3a8-122">You can also manually create allow or block entries for spoofed senders here before they're detected by spoof intelligence.</span></span>

<span data-ttu-id="0b3a8-123">In diesem Artikel wird beschrieben, wie Sie Einträge in der Mandanten zulassen/blockieren-Liste im Security & Compliance Center oder in PowerShell (Exchange Online PowerShell für Microsoft 365-Organisationen mit Postfächern in Exchange Online; eigenständige EOP PowerShell für Organisationen ohne Exchange Online-Postfächer) konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="0b3a8-123">This article describes how to configure entries in the Tenant Allow/Block List in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="0b3a8-124">Was sollten Sie wissen, bevor Sie beginnen?</span><span class="sxs-lookup"><span data-stu-id="0b3a8-124">What do you need to know before you begin?</span></span>

- <span data-ttu-id="0b3a8-125">Sie öffnen das Security & Compliance Center unter <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="0b3a8-125">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="0b3a8-126">Um direkt zur Seite **Mandanten zulassen/blockieren zu** wechseln, verwenden Sie <https://protection.office.com/tenantAllowBlockList> .</span><span class="sxs-lookup"><span data-stu-id="0b3a8-126">To go directly to the **Tenant Allow/Block List** page, use <https://protection.office.com/tenantAllowBlockList>.</span></span>

- <span data-ttu-id="0b3a8-127">Sie geben Dateien mithilfe des SHA256-Hashwerts der Datei an.</span><span class="sxs-lookup"><span data-stu-id="0b3a8-127">You specify files by using the SHA256 hash value of the file.</span></span> <span data-ttu-id="0b3a8-128">Führen Sie den folgenden Befehl in einer Eingabeaufforderung aus, um den SHA256-Hashwert einer Datei in Windows zu finden:</span><span class="sxs-lookup"><span data-stu-id="0b3a8-128">To find the SHA256 hash value of a file in Windows, run the following command in a Command Prompt:</span></span>

  ```console
  certutil.exe -hashfile "<Path>\<Filename>" SHA256
  ```

  <span data-ttu-id="0b3a8-129">Ein Beispielwert ist `768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3a` .</span><span class="sxs-lookup"><span data-stu-id="0b3a8-129">An example value is `768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3a`.</span></span> <span data-ttu-id="0b3a8-130">#A0 (Perceptual Hash) werden nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="0b3a8-130">Perceptual hash (pHash) values are not supported.</span></span>

- <span data-ttu-id="0b3a8-131">Die verfügbaren #A0 werden weiter unten in diesem Artikel in der #A1 für den Abschnitt [Mandanten zulassen/blockieren](#url-syntax-for-the-tenant-allowblock-list) beschrieben.</span><span class="sxs-lookup"><span data-stu-id="0b3a8-131">The available URL values are described in the [URL syntax for the Tenant Allow/Block List](#url-syntax-for-the-tenant-allowblock-list) section later in this article.</span></span>

- <span data-ttu-id="0b3a8-132">Die Mandantenzu-/-sperrliste ermöglicht maximal 500 Einträge für URLs und 500 Einträge für Dateihashes.</span><span class="sxs-lookup"><span data-stu-id="0b3a8-132">The Tenant Allow/Block List allows a maximum of 500 entries for URLs, and 500 entries for file hashes.</span></span>

- <span data-ttu-id="0b3a8-133">Die maximale Anzahl von Zeichen für jeden Eintrag ist:</span><span class="sxs-lookup"><span data-stu-id="0b3a8-133">The maximum number of characters for each entry is:</span></span>
  - <span data-ttu-id="0b3a8-134">Dateihashes = 64</span><span class="sxs-lookup"><span data-stu-id="0b3a8-134">File hashes = 64</span></span>
  - <span data-ttu-id="0b3a8-135">URL = 250</span><span class="sxs-lookup"><span data-stu-id="0b3a8-135">URL = 250</span></span>

- <span data-ttu-id="0b3a8-136">Ein Eintrag sollte innerhalb von 30 Minuten aktiv sein.</span><span class="sxs-lookup"><span data-stu-id="0b3a8-136">An entry should be active within 30 minutes.</span></span>

- <span data-ttu-id="0b3a8-137">Standardmäßig laufen Einträge in der Mandanten-Zulassen-/Sperrliste nach 30 Tagen ab.</span><span class="sxs-lookup"><span data-stu-id="0b3a8-137">By default, entries in the Tenant Allow/Block List will expire after 30 days.</span></span> <span data-ttu-id="0b3a8-138">Sie können ein Datum angeben oder festlegen, dass es nie abläuft.</span><span class="sxs-lookup"><span data-stu-id="0b3a8-138">You can specify a date or set them to never expire.</span></span>

- <span data-ttu-id="0b3a8-139">Wie Sie eine Verbindung mit Exchange Online PowerShell herstellen, finden Sie unter [Herstellen einer Verbindung mit Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="0b3a8-139">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="0b3a8-140">Informationen zum Herstellen einer Verbindung mit dem eigenständigen Exchange Online Protection PowerShell finden Sie unter [Verbinden mit PowerShell in Exchange Online Protection](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="0b3a8-140">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="0b3a8-141">Sie müssen in Exchange Online Berechtigungen erhalten, bevor Sie die in diesem Artikel beschriebenen Schritte ausführen können:</span><span class="sxs-lookup"><span data-stu-id="0b3a8-141">You need to be assigned permissions in Exchange Online before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="0b3a8-142">**URLs, Dateien und Zulassen von Massensendern**:</span><span class="sxs-lookup"><span data-stu-id="0b3a8-142">**URLs, files, and allow bulk senders**:</span></span>
    - <span data-ttu-id="0b3a8-143">Zum Hinzufügen und Entfernen von Werten aus der Mandantenberechtigungs-/Sperrliste müssen Sie Mitglied der Rollengruppen Organisationsverwaltung oder **Sicherheitsadministrator** sein. </span><span class="sxs-lookup"><span data-stu-id="0b3a8-143">To add and remove values from the Tenant Allow/Block List, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
    - <span data-ttu-id="0b3a8-144">Für den schreibgeschützten Zugriff auf die Mandantenzugriffs-/Sperrliste müssen Sie Mitglied der Rollengruppen **"Globaler Leser"** oder **"Sicherheitsleser"** sein.</span><span class="sxs-lookup"><span data-stu-id="0b3a8-144">For read-only access to the Tenant Allow/Block List, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>
  - <span data-ttu-id="0b3a8-145">**Spoofing**: Eine der folgenden Kombinationen:</span><span class="sxs-lookup"><span data-stu-id="0b3a8-145">**Spoofing**: One of the following combinations:</span></span>
    - <span data-ttu-id="0b3a8-146">**Organisationsverwaltung**</span><span class="sxs-lookup"><span data-stu-id="0b3a8-146">**Organization Management**</span></span>
    - <span data-ttu-id="0b3a8-147">**Sicherheitsadministrator** und **Nur-Ansicht-Konfiguration** oder **Nur-Ansicht-Organisationsverwaltung**. <u></u></span><span class="sxs-lookup"><span data-stu-id="0b3a8-147">**Security Administrator** <u>and</u> **View-Only Configuration** or **View-Only Organization Management**.</span></span>

  <span data-ttu-id="0b3a8-148">Weitere Informationen finden Sie unter [Berechtigungen in Exchange Online](/exchange/permissions-exo/permissions-exo).</span><span class="sxs-lookup"><span data-stu-id="0b3a8-148">For more information, see [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo).</span></span>

  > [!NOTE]
  >
  > - <span data-ttu-id="0b3a8-149">Durch das Hinzufügen von Benutzern zur entsprechenden Azure Active Directory-Rolle im Microsoft 365 Admin Center erhalten Benutzer die erforderlichen Berechtigungen _und_ Berechtigungen für andere Features in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="0b3a8-149">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="0b3a8-150">Weitere Informationen finden Sie unter [Informationen zu Administratorrollen](../../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="0b3a8-150">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  >
  > - <span data-ttu-id="0b3a8-151">Die Rollengruppe **Organisationsverwaltung mit Leserechten** in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) ermöglicht auch einen schreibgeschützten Zugriff auf das Feature.</span><span class="sxs-lookup"><span data-stu-id="0b3a8-151">The **View-Only Organization Management** role group in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

## <a name="use-the-security--compliance-center-to-create-block-url-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="0b3a8-152">Verwenden des Security & Compliance Center zum Erstellen von Block-URL-Einträgen in der Mandantenzu-/-sperrliste</span><span class="sxs-lookup"><span data-stu-id="0b3a8-152">Use the Security & Compliance Center to create block URL entries in the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="0b3a8-153">Wechseln Sie im Security & Compliance Center zu Richtlinien für die **Bedrohungsverwaltung** \>  \> **Mandanten zulassen/blockieren Listen**.</span><span class="sxs-lookup"><span data-stu-id="0b3a8-153">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="0b3a8-154">Überprüfen Sie auf der Seite Mandanten **zulassen/blockieren,** ob die Registerkarte **URLs** ausgewählt ist, und klicken Sie dann auf **Blockieren.**</span><span class="sxs-lookup"><span data-stu-id="0b3a8-154">On the **Tenant Allow/Block List** page, verify that the **URLs** tab is selected, and then click **Block**</span></span>

3. <span data-ttu-id="0b3a8-155">Konfigurieren Sie **im angezeigten** Flyout UrLs blockieren die folgenden Einstellungen:</span><span class="sxs-lookup"><span data-stu-id="0b3a8-155">In the **Block URLs** flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="0b3a8-156">**Zu blockierende URLs hinzufügen:** Geben Sie eine URL pro Zeile ein, bis zu maximal 20.</span><span class="sxs-lookup"><span data-stu-id="0b3a8-156">**Add URLs to block**: Enter one URL per line, up to a maximum of 20.</span></span> <span data-ttu-id="0b3a8-157">Weitere Informationen zur Syntax für #A0 finden Sie in der URL-Syntax für den Abschnitt [Mandantenzu-/Sperrliste](#url-syntax-for-the-tenant-allowblock-list) weiter unten in diesem Artikel.</span><span class="sxs-lookup"><span data-stu-id="0b3a8-157">For details about the syntax for URL entries, see the [URL syntax for the Tenant Allow/Block List](#url-syntax-for-the-tenant-allowblock-list) section later in this article.</span></span>

   - <span data-ttu-id="0b3a8-158">**Nie ablaufen:** Gehen Sie wie folgt vor:</span><span class="sxs-lookup"><span data-stu-id="0b3a8-158">**Never expire**: Do one of the following steps:</span></span>

     - <span data-ttu-id="0b3a8-159">Überprüfen Sie, ob die Einstellung deaktiviert ist ( Umschalten ) und verwenden Sie das Feld Läuft auf, um das ![ ](../../media/scc-toggle-off.png) Ablaufdatum für die Einträge anzugeben. </span><span class="sxs-lookup"><span data-stu-id="0b3a8-159">Verify the setting is turned off (![Toggle off](../../media/scc-toggle-off.png)) and use the **Expires on** box to specify the expiration date for the entries.</span></span>

       <span data-ttu-id="0b3a8-160">oder</span><span class="sxs-lookup"><span data-stu-id="0b3a8-160">or</span></span>

     - <span data-ttu-id="0b3a8-161">Verschieben Sie den Umschalter nach rechts, um die Einträge so zu konfigurieren, dass sie nie ablaufen:</span><span class="sxs-lookup"><span data-stu-id="0b3a8-161">Move the toggle to the right to configure the entries to never expire:</span></span> ![Umschaltfläche ein](../../media/scc-toggle-on.png)<span data-ttu-id="0b3a8-163">.</span><span class="sxs-lookup"><span data-stu-id="0b3a8-163">.</span></span>

   - <span data-ttu-id="0b3a8-164">**Optionaler Hinweis:** Geben Sie beschreibenden Text für die Einträge ein.</span><span class="sxs-lookup"><span data-stu-id="0b3a8-164">**Optional note**: Enter descriptive text for the entries.</span></span>

4. <span data-ttu-id="0b3a8-165">Klicken Sie nach Abschluss des Vorgangs auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="0b3a8-165">When you're finished, click **Add**.</span></span>

## <a name="use-the-security--compliance-center-to-create-block-file-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="0b3a8-166">Verwenden des Security & Compliance Center zum Erstellen von Blockdateieinträgen in der Mandantenzu-/-sperrliste</span><span class="sxs-lookup"><span data-stu-id="0b3a8-166">Use the Security & Compliance Center to create block file entries in the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="0b3a8-167">Wechseln Sie im Security & Compliance Center zu Richtlinien für die **Bedrohungsverwaltung** \>  \> **Mandanten zulassen/blockieren Listen**.</span><span class="sxs-lookup"><span data-stu-id="0b3a8-167">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="0b3a8-168">Wählen Sie auf der Seite Mandanten **zulassen/blockieren** die Registerkarte **Dateien** aus, und klicken Sie dann auf **Blockieren**.</span><span class="sxs-lookup"><span data-stu-id="0b3a8-168">On the **Tenant Allow/Block List** page, select the **Files** tab, and then click **Block**.</span></span>

3. <span data-ttu-id="0b3a8-169">Konfigurieren Sie **im angezeigten Flyout** Dateien zum Blockieren von Dateien hinzufügen die folgenden Einstellungen:</span><span class="sxs-lookup"><span data-stu-id="0b3a8-169">In the **Add files to block** flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="0b3a8-170">**Hinzufügen von Dateihashes:** Geben Sie einen SHA256-Hashwert pro Zeile ein, bis zu maximal 20.</span><span class="sxs-lookup"><span data-stu-id="0b3a8-170">**Add file hashes**: Enter one SHA256 hash value per line, up to a maximum of 20.</span></span>

   - <span data-ttu-id="0b3a8-171">**Nie ablaufen:** Gehen Sie wie folgt vor:</span><span class="sxs-lookup"><span data-stu-id="0b3a8-171">**Never expire**: Do one of the following steps:</span></span>

     - <span data-ttu-id="0b3a8-172">Überprüfen Sie, ob die Einstellung deaktiviert ist ( Umschalten ) und verwenden Sie das Feld Läuft auf, um das ![ ](../../media/scc-toggle-off.png) Ablaufdatum für die Einträge anzugeben. </span><span class="sxs-lookup"><span data-stu-id="0b3a8-172">Verify the setting is turned off (![Toggle off](../../media/scc-toggle-off.png)) and use the **Expires on** box to specify the expiration date for the entries.</span></span>

     <span data-ttu-id="0b3a8-173">oder</span><span class="sxs-lookup"><span data-stu-id="0b3a8-173">or</span></span>

     - <span data-ttu-id="0b3a8-174">Verschieben Sie den Umschalter nach rechts, um die Einträge so zu konfigurieren, dass sie nie ablaufen:</span><span class="sxs-lookup"><span data-stu-id="0b3a8-174">Move the toggle to the right to configure the entries to never expire:</span></span> ![Umschaltfläche ein](../../media/scc-toggle-on.png)<span data-ttu-id="0b3a8-176">.</span><span class="sxs-lookup"><span data-stu-id="0b3a8-176">.</span></span>

   - <span data-ttu-id="0b3a8-177">**Optionaler Hinweis:** Geben Sie beschreibenden Text für die Einträge ein.</span><span class="sxs-lookup"><span data-stu-id="0b3a8-177">**Optional note**: Enter descriptive text for the entries.</span></span>

4. <span data-ttu-id="0b3a8-178">Klicken Sie nach Abschluss des Vorgangs auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="0b3a8-178">When you're finished, click **Add**.</span></span>

## <a name="use-the-security--compliance-center-to-create-allow-bulk-mail-sender-domain-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="0b3a8-179">Verwenden des Security & Compliance Center zum Erstellen zulässiger Domäneneinträge für Massen-E-Mail-Absender in der Mandantenzu-/Sperrliste</span><span class="sxs-lookup"><span data-stu-id="0b3a8-179">Use the Security & Compliance Center to create allow bulk mail sender domain entries in the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="0b3a8-180">Wechseln Sie im Security & Compliance Center zu Richtlinien für die **Bedrohungsverwaltung** \>  \> **Mandanten zulassen/blockieren Listen**.</span><span class="sxs-lookup"><span data-stu-id="0b3a8-180">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="0b3a8-181">Wählen Sie auf der Seite Mandanten **zulassen/blockieren** die Registerkarte **Absenderdomänen für die BCL-Umgehung** aus, und klicken Sie dann auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="0b3a8-181">On the **Tenant Allow/Block List** page, select the **Sender domains for BCL bypass** tab, and then click **Add**.</span></span>

3. <span data-ttu-id="0b3a8-182">Konfigurieren Sie **im angezeigten Flyout Absenderdomäne** für die BCL-Umgehung hinzufügen die folgenden Einstellungen:</span><span class="sxs-lookup"><span data-stu-id="0b3a8-182">In the **Add sender domain for BCL bypass** flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="0b3a8-183">**Hinzufügen von Absenderdomänen für die BCL-Umgehung:** Geben Sie eine Quelldomäne mit guten Massen-E-Mails pro Zeile ein, bis zu maximal 20.</span><span class="sxs-lookup"><span data-stu-id="0b3a8-183">**Add sender domains for BCL bypass**: Enter one source domain of good bulk mail per line, up to a maximum of 20.</span></span>

   - <span data-ttu-id="0b3a8-184">**Nie ablaufen:** Gehen Sie wie folgt vor:</span><span class="sxs-lookup"><span data-stu-id="0b3a8-184">**Never expire**: Do one of the following steps:</span></span>

     - <span data-ttu-id="0b3a8-185">Überprüfen Sie, ob die Einstellung deaktiviert ist ( Umschalten ) und verwenden Sie das Feld Läuft auf, um das ![ ](../../media/scc-toggle-off.png) Ablaufdatum für die Einträge anzugeben. </span><span class="sxs-lookup"><span data-stu-id="0b3a8-185">Verify the setting is turned off (![Toggle off](../../media/scc-toggle-off.png)) and use the **Expires on** box to specify the expiration date for the entries.</span></span>

     <span data-ttu-id="0b3a8-186">oder</span><span class="sxs-lookup"><span data-stu-id="0b3a8-186">or</span></span>

     - <span data-ttu-id="0b3a8-187">Verschieben Sie den Umschalter nach rechts, um die Einträge so zu konfigurieren, dass sie nie ablaufen:</span><span class="sxs-lookup"><span data-stu-id="0b3a8-187">Move the toggle to the right to configure the entries to never expire:</span></span> ![Umschaltfläche ein](../../media/scc-toggle-on.png)<span data-ttu-id="0b3a8-189">.</span><span class="sxs-lookup"><span data-stu-id="0b3a8-189">.</span></span>

4. <span data-ttu-id="0b3a8-190">Klicken Sie nach Abschluss des Vorgangs auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="0b3a8-190">When you're finished, click **Add**.</span></span>

## <a name="use-the-security--compliance-center-to-create-allow-or-block-spoofed-sender-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="0b3a8-191">Verwenden des Security & Compliance Center zum Erstellen oder Blockieren gefälschter Absendereinträge in der Mandantenzu-/Sperrliste</span><span class="sxs-lookup"><span data-stu-id="0b3a8-191">Use the Security & Compliance Center to create allow or block spoofed sender entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="0b3a8-192">**Hinweise**:</span><span class="sxs-lookup"><span data-stu-id="0b3a8-192">**Notes**:</span></span>

- <span data-ttu-id="0b3a8-193">Nur die _Kombination_ aus dem  spoofierten Benutzer und der sendenden Infrastruktur, wie im Domänenpaar definiert, ist ausdrücklich zulässig oder von Spoofing blockiert.</span><span class="sxs-lookup"><span data-stu-id="0b3a8-193">Only the _combination_ of the spoofed user _and_ the sending infrastructure as defined in the domain pair is specifically allowed or blocked from spoofing.</span></span>
- <span data-ttu-id="0b3a8-194">Wenn Sie einen zulässigen oder blockierten Eintrag für ein Domänenpaar konfigurieren, werden Nachrichten dieses Domänenpaars nicht mehr in der Spoof Intelligence-Einsicht angezeigt.</span><span class="sxs-lookup"><span data-stu-id="0b3a8-194">When you configure an allow or block entry for a domain pair, messages from that domain pair no longer appear in the spoof intelligence insight.</span></span>
- <span data-ttu-id="0b3a8-195">Einträge für spoofierte Absender laufen nie ab.</span><span class="sxs-lookup"><span data-stu-id="0b3a8-195">Entries for spoofed senders never expire.</span></span>

1. <span data-ttu-id="0b3a8-196">Wechseln Sie im Security & Compliance Center zu Richtlinien für die **Bedrohungsverwaltung** \>  \> **Mandanten zulassen/blockieren Listen**.</span><span class="sxs-lookup"><span data-stu-id="0b3a8-196">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="0b3a8-197">Wählen Sie auf der Seite Mandanten **zulassen/blockieren** die Registerkarte **Spoofing** aus, und klicken Sie dann auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="0b3a8-197">On the **Tenant Allow/Block List** page, select the **Spoofing** tab, and then click **Add**.</span></span>

3. <span data-ttu-id="0b3a8-198">Konfigurieren Sie **im angezeigten** Flyout Neue Domänenpaare hinzufügen die folgenden Einstellungen:</span><span class="sxs-lookup"><span data-stu-id="0b3a8-198">In the **Add new domain pairs** flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="0b3a8-199">**Hinzufügen neuer Domänenpaare mit Platzhaltern:** Geben Sie ein Domänenpaar pro Zeile ein, bis maximal 20.</span><span class="sxs-lookup"><span data-stu-id="0b3a8-199">**Add new domain pairs with wildcards**: Enter one domain pair per line, up to a maximum of 20.</span></span> <span data-ttu-id="0b3a8-200">Weitere Informationen zur Syntax für spoofierte Absendereinträge finden Sie in der Syntax des Domänenpaars für spoofierte Absendereinträge im Abschnitt [Mandantenzu-/-sperrliste](#domain-pair-syntax-for-spoofed-sender-entries-in-the-tenant-allowblock-list) weiter unten in diesem Artikel.</span><span class="sxs-lookup"><span data-stu-id="0b3a8-200">For details about the syntax for spoofed sender entries, see the [Domain pair syntax for spoofed sender entries in the Tenant Allow/Block List](#domain-pair-syntax-for-spoofed-sender-entries-in-the-tenant-allowblock-list) section later in this article.</span></span>

   - <span data-ttu-id="0b3a8-201">**Spooftyp**: Wählen Sie einen der folgenden Werte aus:</span><span class="sxs-lookup"><span data-stu-id="0b3a8-201">**Spoof type**: Select one of the following values:</span></span>
     - <span data-ttu-id="0b3a8-202">**Intern:** Der gefälschte Absender befindet sich in einer Domäne, die zu Ihrer Organisation gehört (eine [akzeptierte Domäne](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)).</span><span class="sxs-lookup"><span data-stu-id="0b3a8-202">**Internal**: The spoofed sender is in a domain that belongs to your organization (an [accepted domain](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)).</span></span>
     - <span data-ttu-id="0b3a8-203">**Extern:** Der gefälschte Absender befindet sich in einer externen Domäne.</span><span class="sxs-lookup"><span data-stu-id="0b3a8-203">**External**: The spoofed sender is in an external domain.</span></span>

   - <span data-ttu-id="0b3a8-204">**Aktion**: Wählen Sie **Zulassen** oder **Blockieren aus.**</span><span class="sxs-lookup"><span data-stu-id="0b3a8-204">**Action**: Select **Allow** or **Block**.</span></span>

4. <span data-ttu-id="0b3a8-205">Klicken Sie nach Abschluss des Vorgangs auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="0b3a8-205">When you're finished, click **Add**.</span></span>

## <a name="use-the-security--compliance-center-to-view-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="0b3a8-206">Verwenden des Security & Compliance Center zum Anzeigen von Einträgen in der Mandantenzu-/-sperrliste</span><span class="sxs-lookup"><span data-stu-id="0b3a8-206">Use the Security & Compliance Center to view entries in the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="0b3a8-207">Wechseln Sie im Security & Compliance Center zu Richtlinien für die **Bedrohungsverwaltung** \>  \> **Mandanten zulassen/blockieren Listen**.</span><span class="sxs-lookup"><span data-stu-id="0b3a8-207">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="0b3a8-208">Wählen Sie die registerkarte aus, die Sie möchten.</span><span class="sxs-lookup"><span data-stu-id="0b3a8-208">Select the tab you want.</span></span> <span data-ttu-id="0b3a8-209">Die verfügbaren Spalten hängen von der ausgewählten Registerkarte ab:</span><span class="sxs-lookup"><span data-stu-id="0b3a8-209">The columns that are available depend on the tab you selected:</span></span>

   - <span data-ttu-id="0b3a8-210">**URLs**:</span><span class="sxs-lookup"><span data-stu-id="0b3a8-210">**URLs**:</span></span>
     - <span data-ttu-id="0b3a8-211">**Wert**: Die URL.</span><span class="sxs-lookup"><span data-stu-id="0b3a8-211">**Value**: The URL.</span></span>
     - <span data-ttu-id="0b3a8-212">**Aktion**: Der Wert **Block**.</span><span class="sxs-lookup"><span data-stu-id="0b3a8-212">**Action**: The value **Block**.</span></span>
     - <span data-ttu-id="0b3a8-213">**Datum der letzten Aktualisierung**</span><span class="sxs-lookup"><span data-stu-id="0b3a8-213">**Last updated date**</span></span>
     - <span data-ttu-id="0b3a8-214">**Ablaufdatum**</span><span class="sxs-lookup"><span data-stu-id="0b3a8-214">**Expiration date**</span></span>
     - <span data-ttu-id="0b3a8-215">**Hinweis**</span><span class="sxs-lookup"><span data-stu-id="0b3a8-215">**Note**</span></span>

   - <span data-ttu-id="0b3a8-216">**Files**</span><span class="sxs-lookup"><span data-stu-id="0b3a8-216">**Files**</span></span>
     - <span data-ttu-id="0b3a8-217">**Wert**: Der Dateihash.</span><span class="sxs-lookup"><span data-stu-id="0b3a8-217">**Value**: The file hash.</span></span>
     - <span data-ttu-id="0b3a8-218">**Aktion**: Der Wert **Block**.</span><span class="sxs-lookup"><span data-stu-id="0b3a8-218">**Action**: The value **Block**.</span></span>
     - <span data-ttu-id="0b3a8-219">**Datum der letzten Aktualisierung**</span><span class="sxs-lookup"><span data-stu-id="0b3a8-219">**Last updated date**</span></span>
     - <span data-ttu-id="0b3a8-220">**Ablaufdatum**</span><span class="sxs-lookup"><span data-stu-id="0b3a8-220">**Expiration date**</span></span>
     - <span data-ttu-id="0b3a8-221">**Hinweis**</span><span class="sxs-lookup"><span data-stu-id="0b3a8-221">**Note**</span></span>

   - <span data-ttu-id="0b3a8-222">**Absenderdomänen für die BCL-Umgehung**</span><span class="sxs-lookup"><span data-stu-id="0b3a8-222">**Sender domains for BCL bypass**</span></span>
     - <span data-ttu-id="0b3a8-223">**Wert:** Die Domäne des Massen-E-Mail-Absenders.</span><span class="sxs-lookup"><span data-stu-id="0b3a8-223">**Value**: The bulk mail sender's domain.</span></span>
     - <span data-ttu-id="0b3a8-224">**Datum der letzten Aktualisierung**</span><span class="sxs-lookup"><span data-stu-id="0b3a8-224">**Last updated date**</span></span>
     - <span data-ttu-id="0b3a8-225">**Ablaufdatum**</span><span class="sxs-lookup"><span data-stu-id="0b3a8-225">**Expiration date**</span></span>

   - <span data-ttu-id="0b3a8-226">**Spoofing**</span><span class="sxs-lookup"><span data-stu-id="0b3a8-226">**Spoofing**</span></span>
     - <span data-ttu-id="0b3a8-227">**Spoofed user**</span><span class="sxs-lookup"><span data-stu-id="0b3a8-227">**Spoofed user**</span></span>
     - <span data-ttu-id="0b3a8-228">**Senden von Infrastruktur**</span><span class="sxs-lookup"><span data-stu-id="0b3a8-228">**Sending infrastructure**</span></span>
     - <span data-ttu-id="0b3a8-229">**Spooftyp**: Der Wert **Internal** oder **External**.</span><span class="sxs-lookup"><span data-stu-id="0b3a8-229">**Spoof type**: The value **Internal** or **External**.</span></span>
     - <span data-ttu-id="0b3a8-230">**Aktion**: Der Wert **Block** oder **Allow**.</span><span class="sxs-lookup"><span data-stu-id="0b3a8-230">**Action**: The value **Block** or **Allow**.</span></span>

   <span data-ttu-id="0b3a8-231">Sie können auf eine Spaltenüberschrift klicken, um in aufsteigender oder absteigender Reihenfolge zu sortieren.</span><span class="sxs-lookup"><span data-stu-id="0b3a8-231">You can click on a column heading to sort in ascending or descending order.</span></span>

   <span data-ttu-id="0b3a8-232">Sie können auf **Gruppe klicken,** um die Ergebnisse zu gruppieren.</span><span class="sxs-lookup"><span data-stu-id="0b3a8-232">You can click **Group** to group the results.</span></span> <span data-ttu-id="0b3a8-233">Die verfügbaren Werte hängen von der ausgewählten Registerkarte ab:</span><span class="sxs-lookup"><span data-stu-id="0b3a8-233">The values that are available depend on the tab you selected:</span></span>

   - <span data-ttu-id="0b3a8-234">**URLs**: Sie können die Ergebnisse nach **Aktion gruppieren.**</span><span class="sxs-lookup"><span data-stu-id="0b3a8-234">**URLs**: You can group the results by **Action**.</span></span>
   - <span data-ttu-id="0b3a8-235">**Dateien**: Sie können die Ergebnisse nach **Aktion gruppieren.**</span><span class="sxs-lookup"><span data-stu-id="0b3a8-235">**Files**: You can group the results by **Action**.</span></span>
   - <span data-ttu-id="0b3a8-236">**Absenderdomänen für die BCL-Umgehung:** **Die Gruppe** ist auf dieser Registerkarte nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="0b3a8-236">**Sender domains for BCL bypass**: **Group** is not available on this tab.</span></span>
   - <span data-ttu-id="0b3a8-237">**Spoofing**: Sie können die Ergebnisse nach **Aktions-** oder **Spooftyp gruppieren.**</span><span class="sxs-lookup"><span data-stu-id="0b3a8-237">**Spoofing**: You can group the results by **Action** or **Spoof type**.</span></span>

   <span data-ttu-id="0b3a8-238">Klicken **Sie auf Suchen,** geben Sie einen Wert ganz oder teilweise ein, und drücken Sie die EINGABETASTE, um einen bestimmten Wert zu finden.</span><span class="sxs-lookup"><span data-stu-id="0b3a8-238">Click **Search**, enter all or part of a value, and then press ENTER to find a specific value.</span></span> <span data-ttu-id="0b3a8-239">Wenn Sie fertig sind, klicken Sie auf **Suche löschen Suchsymbol** ![ löschen ](../../media/b6512677-5e7b-42b0-a8a3-3be1d7fa23ee.gif) .</span><span class="sxs-lookup"><span data-stu-id="0b3a8-239">When you're finished, click **Clear search** ![Clear search icon](../../media/b6512677-5e7b-42b0-a8a3-3be1d7fa23ee.gif).</span></span>

   <span data-ttu-id="0b3a8-240">Klicken **Sie auf Filtern,** um die Ergebnisse zu filtern.</span><span class="sxs-lookup"><span data-stu-id="0b3a8-240">Click **Filter** to filter the results.</span></span> <span data-ttu-id="0b3a8-241">Die im angezeigten **Filterf** flyout verfügbaren Werte hängen von der ausgewählten Registerkarte ab:</span><span class="sxs-lookup"><span data-stu-id="0b3a8-241">The values that are available in **Filter** flyout that appears depend on the tab you selected:</span></span>

   - <span data-ttu-id="0b3a8-242">**URLs**</span><span class="sxs-lookup"><span data-stu-id="0b3a8-242">**URLs**</span></span>
     - <span data-ttu-id="0b3a8-243">**Action**</span><span class="sxs-lookup"><span data-stu-id="0b3a8-243">**Action**</span></span>
     - <span data-ttu-id="0b3a8-244">**Nie ablaufen**</span><span class="sxs-lookup"><span data-stu-id="0b3a8-244">**Never expire**</span></span>
     - <span data-ttu-id="0b3a8-245">**Datum der letzten Aktualisierung**</span><span class="sxs-lookup"><span data-stu-id="0b3a8-245">**Last updated date**</span></span>
     - <span data-ttu-id="0b3a8-246">**Ablaufdatum**</span><span class="sxs-lookup"><span data-stu-id="0b3a8-246">**Expiration date**</span></span>

   - <span data-ttu-id="0b3a8-247">**Files**</span><span class="sxs-lookup"><span data-stu-id="0b3a8-247">**Files**</span></span>
     - <span data-ttu-id="0b3a8-248">**Action**</span><span class="sxs-lookup"><span data-stu-id="0b3a8-248">**Action**</span></span>
     - <span data-ttu-id="0b3a8-249">**Nie ablaufen**</span><span class="sxs-lookup"><span data-stu-id="0b3a8-249">**Never expire**</span></span>
     - <span data-ttu-id="0b3a8-250">**Datum der letzten Aktualisierung**</span><span class="sxs-lookup"><span data-stu-id="0b3a8-250">**Last updated date**</span></span>
     - <span data-ttu-id="0b3a8-251">**Ablaufdatum**</span><span class="sxs-lookup"><span data-stu-id="0b3a8-251">**Expiration date**</span></span>

   - <span data-ttu-id="0b3a8-252">**Absenderdomänen für die BCL-Umgehung**</span><span class="sxs-lookup"><span data-stu-id="0b3a8-252">**Sender domains for BCL bypass**</span></span>
     - <span data-ttu-id="0b3a8-253">**Nie ablaufen**</span><span class="sxs-lookup"><span data-stu-id="0b3a8-253">**Never expire**</span></span>
     - <span data-ttu-id="0b3a8-254">**Datum der letzten Aktualisierung**</span><span class="sxs-lookup"><span data-stu-id="0b3a8-254">**Last updated date**</span></span>
     - <span data-ttu-id="0b3a8-255">**Ablaufdatum**</span><span class="sxs-lookup"><span data-stu-id="0b3a8-255">**Expiration date**</span></span>

   - <span data-ttu-id="0b3a8-256">**Spoofing**</span><span class="sxs-lookup"><span data-stu-id="0b3a8-256">**Spoofing**</span></span>
     - <span data-ttu-id="0b3a8-257">**Action**</span><span class="sxs-lookup"><span data-stu-id="0b3a8-257">**Action**</span></span>
     - <span data-ttu-id="0b3a8-258">**Spooftyp**</span><span class="sxs-lookup"><span data-stu-id="0b3a8-258">**Spoof type**</span></span>

   <span data-ttu-id="0b3a8-259">Klicken Sie nach Abschluss des Abschlusses auf **Übernehmen**.</span><span class="sxs-lookup"><span data-stu-id="0b3a8-259">When you're finished, click **Apply**.</span></span> <span data-ttu-id="0b3a8-260">Klicken Sie zum Löschen vorhandener Filter auf **Filter,** und klicken Sie im angezeigten **Flyout** Filter **auf Filter löschen.**</span><span class="sxs-lookup"><span data-stu-id="0b3a8-260">To clear existing filters, click **Filter**, and in the **Filter** flyout that appears, click **Clear filters**.</span></span>

## <a name="use-the-security--compliance-center-to-modify-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="0b3a8-261">Verwenden des Security & Compliance Center zum Ändern von Einträgen in der Mandantenzu-/-sperrliste</span><span class="sxs-lookup"><span data-stu-id="0b3a8-261">Use the Security & Compliance Center to modify entries in the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="0b3a8-262">Wechseln Sie im Security & Compliance Center zu Richtlinien für die **Bedrohungsverwaltung** \>  \> **Mandanten zulassen/blockieren Listen**.</span><span class="sxs-lookup"><span data-stu-id="0b3a8-262">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="0b3a8-263">Wählen Sie die Registerkarte aus, die den Typ des Eintrags enthält, den Sie ändern möchten:</span><span class="sxs-lookup"><span data-stu-id="0b3a8-263">Select the tab that contains the type of entry that you want to modify:</span></span>
   - <span data-ttu-id="0b3a8-264">**URLs**</span><span class="sxs-lookup"><span data-stu-id="0b3a8-264">**URLs**</span></span>
   - <span data-ttu-id="0b3a8-265">**Files**</span><span class="sxs-lookup"><span data-stu-id="0b3a8-265">**Files**</span></span>
   - <span data-ttu-id="0b3a8-266">**Absenderdomänen für die BCL-Umgehung**</span><span class="sxs-lookup"><span data-stu-id="0b3a8-266">**Sender domains for BCL bypass**</span></span>
   - <span data-ttu-id="0b3a8-267">**Spoofing**</span><span class="sxs-lookup"><span data-stu-id="0b3a8-267">**Spoofing**</span></span>

3. <span data-ttu-id="0b3a8-268">Wählen Sie den Eintrag aus, den Sie ändern möchten, und klicken Sie dann auf **Bearbeiten** ![ (Symbol). ](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png)</span><span class="sxs-lookup"><span data-stu-id="0b3a8-268">Select the entry that you want to modify, and then click **Edit** ![Edit icon](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png).</span></span> <span data-ttu-id="0b3a8-269">Die Werte, die Sie im angezeigten Flyout ändern können, hängen von der Registerkarte ab, die Sie im vorherigen Schritt ausgewählt haben:</span><span class="sxs-lookup"><span data-stu-id="0b3a8-269">The values that you are able to modify in the flyout that appears depend on the tab you selected in the previous step:</span></span>

   - <span data-ttu-id="0b3a8-270">**URLs**</span><span class="sxs-lookup"><span data-stu-id="0b3a8-270">**URLs**</span></span>
     - <span data-ttu-id="0b3a8-271">**Niemals ablaufen** und/oder Ablaufdatum.</span><span class="sxs-lookup"><span data-stu-id="0b3a8-271">**Never expire** and/or expiration date.</span></span>
     - <span data-ttu-id="0b3a8-272">**Optionaler Hinweis**</span><span class="sxs-lookup"><span data-stu-id="0b3a8-272">**Optional note**</span></span>

   - <span data-ttu-id="0b3a8-273">**Files**</span><span class="sxs-lookup"><span data-stu-id="0b3a8-273">**Files**</span></span>
     - <span data-ttu-id="0b3a8-274">**Niemals ablaufen** und/oder Ablaufdatum.</span><span class="sxs-lookup"><span data-stu-id="0b3a8-274">**Never expire** and/or expiration date.</span></span>
     - <span data-ttu-id="0b3a8-275">**Optionaler Hinweis**</span><span class="sxs-lookup"><span data-stu-id="0b3a8-275">**Optional note**</span></span>

   - <span data-ttu-id="0b3a8-276">**Absenderdomänen für die BCL-Umgehung**</span><span class="sxs-lookup"><span data-stu-id="0b3a8-276">**Sender domains for BCL bypass**</span></span>
     - <span data-ttu-id="0b3a8-277">**Niemals ablaufen** und/oder Ablaufdatum.</span><span class="sxs-lookup"><span data-stu-id="0b3a8-277">**Never expire** and/or expiration date.</span></span>

   - <span data-ttu-id="0b3a8-278">**Spoofing**</span><span class="sxs-lookup"><span data-stu-id="0b3a8-278">**Spoofing**</span></span>
     - <span data-ttu-id="0b3a8-279">**Aktion**: Sie können den Wert in **Zulassen oder** **Blockieren ändern.**</span><span class="sxs-lookup"><span data-stu-id="0b3a8-279">**Action**: You can change the value to **Allow** or **Block**.</span></span>

4. <span data-ttu-id="0b3a8-280">Klicken Sie nach Abschluss des Vorgangs auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="0b3a8-280">When you're finished, click **Save**.</span></span>

## <a name="use-the-security--compliance-center-to-remove-entries-from-the-tenant-allowblock-list"></a><span data-ttu-id="0b3a8-281">Verwenden des Security & Compliance Center zum Entfernen von Einträgen aus der Mandantenzu-/-sperrliste</span><span class="sxs-lookup"><span data-stu-id="0b3a8-281">Use the Security & Compliance Center to remove entries from the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="0b3a8-282">Wechseln Sie im Security & Compliance Center zu Richtlinien für die **Bedrohungsverwaltung** \>  \> **Mandanten zulassen/blockieren Listen**.</span><span class="sxs-lookup"><span data-stu-id="0b3a8-282">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="0b3a8-283">Wählen Sie die Registerkarte aus, die den Typ des Eintrags enthält, den Sie entfernen möchten:</span><span class="sxs-lookup"><span data-stu-id="0b3a8-283">Select the tab that contains the type of entry that you want to remove:</span></span>
   - <span data-ttu-id="0b3a8-284">**URLs**</span><span class="sxs-lookup"><span data-stu-id="0b3a8-284">**URLs**</span></span>
   - <span data-ttu-id="0b3a8-285">**Files**</span><span class="sxs-lookup"><span data-stu-id="0b3a8-285">**Files**</span></span>
   - <span data-ttu-id="0b3a8-286">**Absenderdomänen für die BCL-Umgehung**</span><span class="sxs-lookup"><span data-stu-id="0b3a8-286">**Sender domains for BCL bypass**</span></span>
   - <span data-ttu-id="0b3a8-287">**Spoofing**</span><span class="sxs-lookup"><span data-stu-id="0b3a8-287">**Spoofing**</span></span>

3. <span data-ttu-id="0b3a8-288">Wählen Sie den Eintrag aus, den Sie entfernen möchten, und klicken Sie dann **auf Löschen** ![ -Symbol ](../../media/87565fbb-5147-4f22-9ed7-1c18ce664392.png) .</span><span class="sxs-lookup"><span data-stu-id="0b3a8-288">Select the entry that you want to remove, and then click **Delete** ![Delete icon](../../media/87565fbb-5147-4f22-9ed7-1c18ce664392.png).</span></span>

4. <span data-ttu-id="0b3a8-289">Klicken Sie im angezeigten Warnungsdialogfeld auf **Löschen**.</span><span class="sxs-lookup"><span data-stu-id="0b3a8-289">In the warning dialog that appears, click **Delete**.</span></span>

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-the-tenant-allowblock-list"></a><span data-ttu-id="0b3a8-290">Verwenden Exchange Online PowerShell oder eigenständiger EOP PowerShell zum Konfigurieren der Mandanten zulassen/Blockieren-Liste</span><span class="sxs-lookup"><span data-stu-id="0b3a8-290">Use Exchange Online PowerShell or standalone EOP PowerShell to configure the Tenant Allow/Block List</span></span>

### <a name="use-powershell-to-add-block-file-or-url-entries-to-the-tenant-allowblock-list"></a><span data-ttu-id="0b3a8-291">Verwenden von PowerShell zum Hinzufügen von Blockdatei- oder URL-Einträgen zur Mandantenzu-/Sperrliste</span><span class="sxs-lookup"><span data-stu-id="0b3a8-291">Use PowerShell to add block file or URL entries to the Tenant Allow/Block List</span></span>

<span data-ttu-id="0b3a8-292">Verwenden Sie die folgende Syntax, um Blockdatei- oder #A0 in der Mandanten zulassen/blockieren-Liste hinzuzufügen:</span><span class="sxs-lookup"><span data-stu-id="0b3a8-292">To add block file or URL entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
New-TenantAllowBlockListItems -ListType <FileHash | Url> -Block -Entries "Value1","Value2",..."ValueN" <-ExpirationDate Date | -NoExpiration> [-Notes <String>]
```

<span data-ttu-id="0b3a8-293">In diesem Beispiel wird ein Blockdateieintrag für die angegebenen Dateien, die nie abläuft, hinzufügt.</span><span class="sxs-lookup"><span data-stu-id="0b3a8-293">This example adds a block file entry for the specified files that never expires.</span></span>

```powershell
New-TenantAllowBlockListItem -ListType FileHash -Block -Entries "768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3","2c0a35409ff0873cfa28b70b8224e9aca2362241c1f0ed6f622fef8d4722fd9a" -NoExpiration
```

<span data-ttu-id="0b3a8-294">In diesem Beispiel wird ein Block-URL-Eintrag für contoso.com und alle Unterdomänen hinzugefügt (z. B. contoso.com, www.contoso.com und xyz.abc.contoso.com).</span><span class="sxs-lookup"><span data-stu-id="0b3a8-294">This example adds a block URL entry for contoso.com and all subdomains (for example, contoso.com, www.contoso.com, and xyz.abc.contoso.com).</span></span> <span data-ttu-id="0b3a8-295">Da wir die Parameter ExpirationDate oder NoExpiration nicht verwendet haben, läuft der Eintrag nach 30 Tagen ab.</span><span class="sxs-lookup"><span data-stu-id="0b3a8-295">Because we didn't use the ExpirationDate or NoExpiration parameters, the entry expires after 30 days.</span></span>

```powershell
New-TenantAllowBlockListItems -ListType Url -Block -Entries ~contoso.com
```

<span data-ttu-id="0b3a8-296">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [New-TenantAllowBlockListItems](/powershell/module/exchange/new-tenantallowblocklistitems).</span><span class="sxs-lookup"><span data-stu-id="0b3a8-296">For detailed syntax and parameter information, see [New-TenantAllowBlockListItems](/powershell/module/exchange/new-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-add-allow-bulk-mail-sender-domain-entries-to-the-tenant-allowblock-list"></a><span data-ttu-id="0b3a8-297">Verwenden von PowerShell zum Hinzufügen zulässiger Domäneneinträge für Massen-E-Mail-Absender zur Mandantenzu-/Sperrliste</span><span class="sxs-lookup"><span data-stu-id="0b3a8-297">Use PowerShell to add allow bulk mail sender domain entries to the Tenant Allow/Block List</span></span>

<span data-ttu-id="0b3a8-298">Verwenden Sie die folgende Syntax, um #A0 in der Mandanten zulassen/blockieren-Liste hinzuzufügen:</span><span class="sxs-lookup"><span data-stu-id="0b3a8-298">To add allow bulk mail sender domain entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
New-TenantAllowBlockListItems -ListType BulkSender -Block:$false -Entries "Value1","Value2",..."ValueN" <-ExpirationDate Date | -NoExpiration> [-Notes <String>]
```

<span data-ttu-id="0b3a8-299">In diesem Beispiel wird ein zulässiger Massensendereintrag für die angegebene Domäne, der nie abläuft, hinzufügt.</span><span class="sxs-lookup"><span data-stu-id="0b3a8-299">This example adds an allowed bulk sender entry for the specified domain that never expires.</span></span>

```powershell
New-TenantAllowBlockListItem -ListType BulkSender -Block:$false -Entries contosodailydeals.com
New-TenantAllowBlockListItems -ListType FileHash -Block -Entries "768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3","2c0a35409ff0873cfa28b70b8224e9aca2362241c1f0ed6f622fef8d4722fd9a" -NoExpiration
```

<span data-ttu-id="0b3a8-300">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [New-TenantAllowBlockListItems](/powershell/module/exchange/new-tenantallowblocklistitems).</span><span class="sxs-lookup"><span data-stu-id="0b3a8-300">For detailed syntax and parameter information, see [New-TenantAllowBlockListItems](/powershell/module/exchange/new-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-add-allow-or-block-spoofed-sender-entries-to-the-tenant-allowblock-list"></a><span data-ttu-id="0b3a8-301">Verwenden von PowerShell zum Hinzufügen zulässiger oder blockieren von gefälschten Absendereinträgen zur Mandantenzu-/Sperrliste</span><span class="sxs-lookup"><span data-stu-id="0b3a8-301">Use PowerShell to add allow or block spoofed sender entries to the Tenant Allow/Block List</span></span>

<span data-ttu-id="0b3a8-302">Verwenden Sie die folgende Syntax, um spoofierte Absendereinträge in der Mandanten zulassen/blockieren-Liste hinzuzufügen:</span><span class="sxs-lookup"><span data-stu-id="0b3a8-302">To add spoofed sender entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
New-TenantAllowBlockListSpoofItems -SpoofedUser <Domain | EmailAddress | *> -SendingInfrastructure <Domain | IPAddress/24> -SpoofType <External | Internal> -Action <Allow | Block>
```

<span data-ttu-id="0b3a8-303">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [New-TenantAllowBlockListSpoofItems](/powershell/module/exchange/new-tenantallowblocklistspoofitems).</span><span class="sxs-lookup"><span data-stu-id="0b3a8-303">For detailed syntax and parameter information, see [New-TenantAllowBlockListSpoofItems](/powershell/module/exchange/new-tenantallowblocklistspoofitems).</span></span>

### <a name="use-powershell-to-view-block-file-or-url-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="0b3a8-304">Verwenden von PowerShell zum Anzeigen von Blockdatei- oder URL-Einträgen in der Mandantenzu-/-sperrliste</span><span class="sxs-lookup"><span data-stu-id="0b3a8-304">Use PowerShell to view block file or URL entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="0b3a8-305">Verwenden Sie die folgende Syntax, um Blockdatei- oder #A0 in der Mandanten zulassen/blockieren-Liste anzeigen zu können:</span><span class="sxs-lookup"><span data-stu-id="0b3a8-305">To view block file or URL entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType <FileHash | URL> [-Entry <FileHashValue | URLValue>] [<-ExpirationDate Date | -NoExpiration>]
```

<span data-ttu-id="0b3a8-306">In diesem Beispiel werden Informationen für den angegebenen Dateihashwert zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="0b3a8-306">This example returns information for the specified file hash value.</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType FileHash -Entry "9f86d081884c7d659a2feaa0c55ad015a3bf4f1b2b0b822cd15d6c15b0f00a08"
```

<span data-ttu-id="0b3a8-307">In diesem Beispiel werden alle blockierten URLs zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="0b3a8-307">This example returns all blocked URLs.</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType Url -Block
```

<span data-ttu-id="0b3a8-308">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Get-TenantAllowBlockListItems](/powershell/module/exchange/get-tenantallowblocklistitems).</span><span class="sxs-lookup"><span data-stu-id="0b3a8-308">For detailed syntax and parameter information, see [Get-TenantAllowBlockListItems](/powershell/module/exchange/get-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-view-allow-bulk-mail-sender-domain-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="0b3a8-309">Verwenden von PowerShell zum Anzeigen von Domäneneinträgen für Massen-E-Mail-Absender in der Mandantenzu-/-sperrliste</span><span class="sxs-lookup"><span data-stu-id="0b3a8-309">Use PowerShell to view allow bulk mail sender domain entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="0b3a8-310">Verwenden Sie die folgende Syntax, um Domäneneinträge für Massen-E-Mail-Absender in der Mandanten zulassen/blockieren-Liste anzeigen zu können:</span><span class="sxs-lookup"><span data-stu-id="0b3a8-310">To view allow bulk mail sender domain entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType BulkSender [-Entry <BulkSenderDomainValue>] [<-ExpirationDate Date | -NoExpiration>]
```

<span data-ttu-id="0b3a8-311">In diesem Beispiel werden alle zulässigen Massen-E-Mail-Absenderdomänen zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="0b3a8-311">This example returns all allowed bulk mail sender domains.</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType BulkSender
```

<span data-ttu-id="0b3a8-312">In diesem Beispiel werden Informationen für die angegebene Massensenderdomäne zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="0b3a8-312">This example returns information for the specified bulk sender domain.</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType FileHash -Entry "contosodailydeals.com"
```

<span data-ttu-id="0b3a8-313">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Get-TenantAllowBlockListItems](/powershell/module/exchange/get-tenantallowblocklistitems).</span><span class="sxs-lookup"><span data-stu-id="0b3a8-313">For detailed syntax and parameter information, see [Get-TenantAllowBlockListItems](/powershell/module/exchange/get-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-view-allow-or-block-spoofed-sender-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="0b3a8-314">Verwenden von PowerShell zum Anzeigen zulässiger oder blockierter Absendereinträge in der Mandantenzu-/Sperrliste</span><span class="sxs-lookup"><span data-stu-id="0b3a8-314">Use PowerShell to view allow or block spoofed sender entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="0b3a8-315">Verwenden Sie die folgende Syntax, um spoofierte Absendereinträge in der Mandantenzu-/Sperrliste anzeigen zu können:</span><span class="sxs-lookup"><span data-stu-id="0b3a8-315">To view spoofed sender entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Get-TenantAllowBlockListSpoofItems [-Action <Allow | Block>] [-SpoofType <External | Internal>
```

<span data-ttu-id="0b3a8-316">In diesem Beispiel werden alle spoofierten Absendereinträge in der Mandanten zulassen/blockieren-Liste zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="0b3a8-316">This example returns all spoofed sender entries in the Tenant Allow/Block List.</span></span>

```powershell
Get-TenantAllowBlockListSpoofItems
```

<span data-ttu-id="0b3a8-317">In diesem Beispiel werden alle zulässigen spoofierten Absendereinträge zurückgegeben, die intern sind.</span><span class="sxs-lookup"><span data-stu-id="0b3a8-317">This example returns all allow spoofed sender entries that are internal.</span></span>

```powershell
Get-TenantAllowBlockListSpoofItems -Action Allow -SpoofType Internal
```

<span data-ttu-id="0b3a8-318">In diesem Beispiel werden alle blockierten spoofierten Absendereinträge zurückgegeben, die extern sind.</span><span class="sxs-lookup"><span data-stu-id="0b3a8-318">This example returns all blocked spoofed sender entries that are external.</span></span>

```powershell
Get-TenantAllowBlockListSpoofItems -Action Block -SpoofType External
```

<span data-ttu-id="0b3a8-319">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Get-TenantAllowBlockListSpoofItems](/powershell/module/exchange/get-tenantallowblocklistspoofitems).</span><span class="sxs-lookup"><span data-stu-id="0b3a8-319">For detailed syntax and parameter information, see [Get-TenantAllowBlockListSpoofItems](/powershell/module/exchange/get-tenantallowblocklistspoofitems).</span></span>

### <a name="use-powershell-to-modify-block-file-and-url-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="0b3a8-320">Verwenden von PowerShell zum Ändern von Blockdatei- und URL-Einträgen in der Mandantenzu-/Sperrliste</span><span class="sxs-lookup"><span data-stu-id="0b3a8-320">Use PowerShell to modify block file and URL entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="0b3a8-321">Verwenden Sie die folgende Syntax, um Blockdatei- und #A0 in der Mandanten-Allow/Block List zu ändern:</span><span class="sxs-lookup"><span data-stu-id="0b3a8-321">To modify block file and URL entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Set-TenantAllowBlockListItems -ListType <FileHash | Url> -Ids <"Id1","Id2",..."IdN"> [<-ExpirationDate Date | -NoExpiration>] [-Notes <String>]
```

<span data-ttu-id="0b3a8-322">In diesem Beispiel wird das Ablaufdatum des angegebenen Block-URL-Eintrags geändert.</span><span class="sxs-lookup"><span data-stu-id="0b3a8-322">This example changes the expiration date of the specified block URL entry.</span></span>

```powershell
Set-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSRAAAA" -ExpirationDate "5/30/2020"
```

<span data-ttu-id="0b3a8-323">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Set-TenantAllowBlockListItems](/powershell/module/exchange/set-tenantallowblocklistitems).</span><span class="sxs-lookup"><span data-stu-id="0b3a8-323">For detailed syntax and parameter information, see [Set-TenantAllowBlockListItems](/powershell/module/exchange/set-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-modify-allow-bulk-mail-sender-domain-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="0b3a8-324">Verwenden von PowerShell zum Ändern zulässiger Domäneneinträge für Massen-E-Mail-Absender in der Mandantenzu-/Sperrliste</span><span class="sxs-lookup"><span data-stu-id="0b3a8-324">Use PowerShell to modify allow bulk mail sender domain entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="0b3a8-325">Verwenden Sie die folgende Syntax, um Domäneneinträge für Massen-E-Mail-Absender in der Mandanten zulassen/blockieren-Liste zu ändern:</span><span class="sxs-lookup"><span data-stu-id="0b3a8-325">To modify allow bulk mail sender domain entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType BulkSender -Ids <"Id1","Id2",..."IdN"> [<-ExpirationDate Date | -NoExpiration>] [-Notes <String>]
```

<span data-ttu-id="0b3a8-326">In diesem Beispiel wird der Ablauf des angegebenen Domäneneintrags "Massen-E-Mail-Absender zulassen" so geändert, dass er nie abläuft.</span><span class="sxs-lookup"><span data-stu-id="0b3a8-326">This example changes the expiration of the specified allow bulk mail sender domain entry to never expire.</span></span>

```powershell
Set-TenantAllowBlockListItems -ListType BulkSender -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSRAAAA" -NoExpiration
```

<span data-ttu-id="0b3a8-327">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Get-TenantAllowBlockListItems](/powershell/module/exchange/get-tenantallowblocklistitems).</span><span class="sxs-lookup"><span data-stu-id="0b3a8-327">For detailed syntax and parameter information, see [Get-TenantAllowBlockListItems](/powershell/module/exchange/get-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-modify-allow-or-block-spoofed-sender-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="0b3a8-328">Verwenden von PowerShell zum Ändern zulässiger oder blockierter Absendereinträge in der Mandantenzu-/Sperrliste</span><span class="sxs-lookup"><span data-stu-id="0b3a8-328">Use PowerShell to modify allow or block spoofed sender entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="0b3a8-329">Verwenden Sie die folgende Syntax, um gefälschte Absendereinträge in der Mandanten zulassen/blockieren-Liste zu ändern oder zu blockieren:</span><span class="sxs-lookup"><span data-stu-id="0b3a8-329">To modify allow or block spoofed sender entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Set-TenantAllowBlockListSpoofItems -Ids <"Id1","Id2",..."IdN"> -Action <Allow | Block>
```

<span data-ttu-id="0b3a8-330">In diesem Beispiel wird der Spoofing-Absendereintrag von "Blockieren" geändert.</span><span class="sxs-lookup"><span data-stu-id="0b3a8-330">This example changes spoofed sender entry from allow to block.</span></span>

```powershell
Set-TenantAllowBlockListItems -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSRAAAA" -Action Block
```

<span data-ttu-id="0b3a8-331">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Set-TenantAllowBlockListSpoofItems](/powershell/module/exchange/set-tenantallowblocklistspoofitems).</span><span class="sxs-lookup"><span data-stu-id="0b3a8-331">For detailed syntax and parameter information, see [Set-TenantAllowBlockListSpoofItems](/powershell/module/exchange/set-tenantallowblocklistspoofitems).</span></span>

### <a name="use-powershell-to-remove-bulk-mail-sender-domain-file-and-domain-entries-from-the-tenant-allowblock-list"></a><span data-ttu-id="0b3a8-332">Verwenden von PowerShell zum Entfernen von Domänen-, Datei- und Domäneneinträgen von Massen-E-Mail-Absendern aus der Mandantenzu-/Sperrliste</span><span class="sxs-lookup"><span data-stu-id="0b3a8-332">Use PowerShell to remove bulk mail sender domain, file, and domain entries from the Tenant Allow/Block List</span></span>

<span data-ttu-id="0b3a8-333">Verwenden Sie die folgende Syntax, um Domäneneinträge für Massen-E-Mail-Absender zu entfernen, Dateieinträge zu blockieren und #A0 aus der Mandantenzu-/Sperrliste zu blockieren:</span><span class="sxs-lookup"><span data-stu-id="0b3a8-333">To remove allow bulk mail sender domain entries, block file entries, and block URL entries from the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Remove-TenantAllowBlockListItems -ListType <BulkSender | FileHash | Url> -Ids <"Id1","Id2",..."IdN">
```

<span data-ttu-id="0b3a8-334">In diesem Beispiel wird der angegebene Block-URL-Eintrag aus der Mandanten-Allow/Block List entfernt.</span><span class="sxs-lookup"><span data-stu-id="0b3a8-334">This example removes the specified block URL entry from the Tenant Allow/Block List.</span></span>

```powershell
Remove-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSPAAAA0"
```

<span data-ttu-id="0b3a8-335">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Remove-TenantAllowBlockListItems](/powershell/module/exchange/remove-tenantallowblocklistitems).</span><span class="sxs-lookup"><span data-stu-id="0b3a8-335">For detailed syntax and parameter information, see [Remove-TenantAllowBlockListItems](/powershell/module/exchange/remove-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-remove-allow-or-block-spoofed-sender-entries-from-the-tenant-allowblock-list"></a><span data-ttu-id="0b3a8-336">Verwenden von PowerShell zum Entfernen zulässiger oder blockierter Gefälschter Absendereinträge aus der Mandantenzu-/Sperrliste</span><span class="sxs-lookup"><span data-stu-id="0b3a8-336">Use PowerShell to remove allow or block spoofed sender entries from the Tenant Allow/Block List</span></span>

<span data-ttu-id="0b3a8-337">Verwenden Sie die folgende Syntax, um Spoof-Absendereinträge aus der Mandanten zulassen/blockieren-Liste zu entfernen oder zu blockieren:</span><span class="sxs-lookup"><span data-stu-id="0b3a8-337">To remove allow or block spoof sender entries from the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Remove-TenantAllowBlockListSpoofItems -Ids <"Id1","Id2",..."IdN">
```

<span data-ttu-id="0b3a8-338">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Remove-TenantAllowBlockListSpoofItems](/powershell/module/exchange/remove-tenantallowblocklistspoofitems).</span><span class="sxs-lookup"><span data-stu-id="0b3a8-338">For detailed syntax and parameter information, see [Remove-TenantAllowBlockListSpoofItems](/powershell/module/exchange/remove-tenantallowblocklistspoofitems).</span></span>

## <a name="url-syntax-for-the-tenant-allowblock-list"></a><span data-ttu-id="0b3a8-339">#A0 für die Mandanten-Allow/Block List</span><span class="sxs-lookup"><span data-stu-id="0b3a8-339">URL syntax for the Tenant Allow/Block List</span></span>

- <span data-ttu-id="0b3a8-340">IP4v- und IPv6-Adressen sind zulässig, TCP/UDP-Ports jedoch nicht.</span><span class="sxs-lookup"><span data-stu-id="0b3a8-340">IP4v and IPv6 addresses are allowed, but TCP/UDP ports are not.</span></span>

- <span data-ttu-id="0b3a8-341">Dateinamenerweiterungen sind nicht zulässig (z. B. test.pdf).</span><span class="sxs-lookup"><span data-stu-id="0b3a8-341">Filename extensions are not allowed (for example, test.pdf).</span></span>

- <span data-ttu-id="0b3a8-342">Unicode wird nicht unterstützt, Punycode jedoch.</span><span class="sxs-lookup"><span data-stu-id="0b3a8-342">Unicode is not supported, but Punycode is.</span></span>

- <span data-ttu-id="0b3a8-343">Hostnamen sind zulässig, wenn alle folgenden Anweisungen zutreffen:</span><span class="sxs-lookup"><span data-stu-id="0b3a8-343">Hostnames are allowed if all of the following statements are true:</span></span>
  - <span data-ttu-id="0b3a8-344">Der Hostname enthält einen Zeitraum.</span><span class="sxs-lookup"><span data-stu-id="0b3a8-344">The hostname contains a period.</span></span>
  - <span data-ttu-id="0b3a8-345">Es gibt mindestens ein Zeichen links vom Zeitraum.</span><span class="sxs-lookup"><span data-stu-id="0b3a8-345">There is at least one character to the left of the period.</span></span>
  - <span data-ttu-id="0b3a8-346">Rechts neben dem Zeitraum befinden sich mindestens zwei Zeichen.</span><span class="sxs-lookup"><span data-stu-id="0b3a8-346">There are at least two characters to the right of the period.</span></span>

  <span data-ttu-id="0b3a8-347">Beispielsweise ist `t.co` zulässig oder nicht `.com` `contoso.` zulässig.</span><span class="sxs-lookup"><span data-stu-id="0b3a8-347">For example, `t.co` is allowed; `.com` or `contoso.` are not allowed.</span></span>

- <span data-ttu-id="0b3a8-348">Unterpfade werden nicht impliziert.</span><span class="sxs-lookup"><span data-stu-id="0b3a8-348">Subpaths are not implied.</span></span>

  <span data-ttu-id="0b3a8-349">Enthält z. `contoso.com` B. nicht `contoso.com/a` .</span><span class="sxs-lookup"><span data-stu-id="0b3a8-349">For example, `contoso.com` does not include `contoso.com/a`.</span></span>

- <span data-ttu-id="0b3a8-350">Platzhalter (\*) sind in den folgenden Szenarien zulässig:</span><span class="sxs-lookup"><span data-stu-id="0b3a8-350">Wildcards (\*) are allowed in the following scenarios:</span></span>

  - <span data-ttu-id="0b3a8-351">Auf einen linken Platzhalter muss ein Zeitraum folgen, um eine Unterdomäne anzugeben.</span><span class="sxs-lookup"><span data-stu-id="0b3a8-351">A left wildcard must be followed by a period to specify a subdomain.</span></span>

    <span data-ttu-id="0b3a8-352">Ist beispielsweise `*.contoso.com` zulässig; `*contoso.com` ist nicht zulässig.</span><span class="sxs-lookup"><span data-stu-id="0b3a8-352">For example, `*.contoso.com` is allowed; `*contoso.com` is not allowed.</span></span>

  - <span data-ttu-id="0b3a8-353">Ein rechter Platzhalter muss einem Schrägstrich (/) folgen, um einen Pfad anzugeben.</span><span class="sxs-lookup"><span data-stu-id="0b3a8-353">A right wildcard must follow a forward slash (/) to specify a path.</span></span>

    <span data-ttu-id="0b3a8-354">Beispielsweise ist `contoso.com/*` zulässig oder nicht `contoso.com*` `contoso.com/ab*` zulässig.</span><span class="sxs-lookup"><span data-stu-id="0b3a8-354">For example, `contoso.com/*` is allowed; `contoso.com*` or `contoso.com/ab*` are not allowed.</span></span>

  - <span data-ttu-id="0b3a8-355">Alle Unterpfade werden nicht durch einen rechten Platzhalter impliziert.</span><span class="sxs-lookup"><span data-stu-id="0b3a8-355">All subpaths are not implied by a right wildcard.</span></span>

    <span data-ttu-id="0b3a8-356">Enthält z. `contoso.com/*` B. nicht `contoso.com/a` .</span><span class="sxs-lookup"><span data-stu-id="0b3a8-356">For example, `contoso.com/*` does not include `contoso.com/a`.</span></span>

  - <span data-ttu-id="0b3a8-357">`*.com*` ist ungültig (keine auflösbare Domäne, und der rechte Platzhalter folgt keinem Schrägstrich).</span><span class="sxs-lookup"><span data-stu-id="0b3a8-357">`*.com*` is invalid (not a resolvable domain and the right wildcard does not follow a forward slash).</span></span>

  - <span data-ttu-id="0b3a8-358">Platzhalter sind in IP-Adressen nicht zulässig.</span><span class="sxs-lookup"><span data-stu-id="0b3a8-358">Wildcards are not allowed in IP addresses.</span></span>

- <span data-ttu-id="0b3a8-359">Das Tildezeichen (~) ist in den folgenden Szenarien verfügbar:</span><span class="sxs-lookup"><span data-stu-id="0b3a8-359">The tilde (~) character is available in the following scenarios:</span></span>

  - <span data-ttu-id="0b3a8-360">Eine linke Tilde impliziert eine Domäne und alle Unterdomänen.</span><span class="sxs-lookup"><span data-stu-id="0b3a8-360">A left tilde implies a domain and all subdomains.</span></span>

    <span data-ttu-id="0b3a8-361">Enthält `~contoso.com` z. `contoso.com` B. und `*.contoso.com` .</span><span class="sxs-lookup"><span data-stu-id="0b3a8-361">For example `~contoso.com` includes `contoso.com` and `*.contoso.com`.</span></span>

- <span data-ttu-id="0b3a8-362">URL-Einträge, die Protokolle (z. B. , oder ) enthalten, werden fehlschlagen, da `http://` URL-Einträge für alle Protokolle `https://` `ftp://` gelten.</span><span class="sxs-lookup"><span data-stu-id="0b3a8-362">URL entries that contain protocols (for example, `http://`, `https://`, or `ftp://`) will fail, because URL entries apply to all protocols.</span></span>

- <span data-ttu-id="0b3a8-363">Ein Benutzername oder Kennwort wird nicht unterstützt oder ist nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="0b3a8-363">A username or password aren't supported or required.</span></span>

- <span data-ttu-id="0b3a8-364">Anführungszeichen (' oder ") sind ungültige Zeichen.</span><span class="sxs-lookup"><span data-stu-id="0b3a8-364">Quotes (' or ") are invalid characters.</span></span>

- <span data-ttu-id="0b3a8-365">Eine URL sollte nach Möglichkeit alle Umleitungen enthalten.</span><span class="sxs-lookup"><span data-stu-id="0b3a8-365">A URL should include all redirects where possible.</span></span>

### <a name="url-entry-scenarios"></a><span data-ttu-id="0b3a8-366">Szenarien für den URL-Eintrag</span><span class="sxs-lookup"><span data-stu-id="0b3a8-366">URL entry scenarios</span></span>

<span data-ttu-id="0b3a8-367">Gültige URL-Einträge und deren Ergebnisse werden in den folgenden Abschnitten beschrieben.</span><span class="sxs-lookup"><span data-stu-id="0b3a8-367">Valid URL entries and their results are described in the following sections.</span></span>

#### <a name="scenario-no-wildcards"></a><span data-ttu-id="0b3a8-368">Szenario: Keine Platzhalter</span><span class="sxs-lookup"><span data-stu-id="0b3a8-368">Scenario: No wildcards</span></span>

<span data-ttu-id="0b3a8-369">**Eintrag**: `contoso.com`</span><span class="sxs-lookup"><span data-stu-id="0b3a8-369">**Entry**: `contoso.com`</span></span>

- <span data-ttu-id="0b3a8-370">**Übereinstimmung zulassen**: contoso.com</span><span class="sxs-lookup"><span data-stu-id="0b3a8-370">**Allow match**: contoso.com</span></span>

- <span data-ttu-id="0b3a8-371">**Nicht übereinstimmend zulassen:**</span><span class="sxs-lookup"><span data-stu-id="0b3a8-371">**Allow not matched**:</span></span>

  - <span data-ttu-id="0b3a8-372">abc-contoso.com</span><span class="sxs-lookup"><span data-stu-id="0b3a8-372">abc-contoso.com</span></span>
  - <span data-ttu-id="0b3a8-373">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="0b3a8-373">contoso.com/a</span></span>
  - <span data-ttu-id="0b3a8-374">payroll.contoso.com</span><span class="sxs-lookup"><span data-stu-id="0b3a8-374">payroll.contoso.com</span></span>
  - <span data-ttu-id="0b3a8-375">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="0b3a8-375">test.com/contoso.com</span></span>
  - <span data-ttu-id="0b3a8-376">test.com/q=contoso.com</span><span class="sxs-lookup"><span data-stu-id="0b3a8-376">test.com/q=contoso.com</span></span>
  - <span data-ttu-id="0b3a8-377">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="0b3a8-377">www.contoso.com</span></span>
  - <span data-ttu-id="0b3a8-378">www.contoso.com/q=a@contoso.com</span><span class="sxs-lookup"><span data-stu-id="0b3a8-378">www.contoso.com/q=a@contoso.com</span></span>

- <span data-ttu-id="0b3a8-379">**Übereinstimmung blockieren**:</span><span class="sxs-lookup"><span data-stu-id="0b3a8-379">**Block match**:</span></span>

  - <span data-ttu-id="0b3a8-380">contoso.com</span><span class="sxs-lookup"><span data-stu-id="0b3a8-380">contoso.com</span></span>
  - <span data-ttu-id="0b3a8-381">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="0b3a8-381">contoso.com/a</span></span>
  - <span data-ttu-id="0b3a8-382">payroll.contoso.com</span><span class="sxs-lookup"><span data-stu-id="0b3a8-382">payroll.contoso.com</span></span>
  - <span data-ttu-id="0b3a8-383">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="0b3a8-383">test.com/contoso.com</span></span>
  - <span data-ttu-id="0b3a8-384">test.com/q=contoso.com</span><span class="sxs-lookup"><span data-stu-id="0b3a8-384">test.com/q=contoso.com</span></span>
  - <span data-ttu-id="0b3a8-385">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="0b3a8-385">www.contoso.com</span></span>
  - <span data-ttu-id="0b3a8-386">www.contoso.com/q=a@contoso.com</span><span class="sxs-lookup"><span data-stu-id="0b3a8-386">www.contoso.com/q=a@contoso.com</span></span>

- <span data-ttu-id="0b3a8-387">**Block nicht übereinstimmend**: abc-contoso.com</span><span class="sxs-lookup"><span data-stu-id="0b3a8-387">**Block not matched**: abc-contoso.com</span></span>

#### <a name="scenario-left-wildcard-subdomain"></a><span data-ttu-id="0b3a8-388">Szenario: Linker Platzhalter (Unterdomäne)</span><span class="sxs-lookup"><span data-stu-id="0b3a8-388">Scenario: Left wildcard (subdomain)</span></span>

<span data-ttu-id="0b3a8-389">**Eintrag**: `*.contoso.com`</span><span class="sxs-lookup"><span data-stu-id="0b3a8-389">**Entry**: `*.contoso.com`</span></span>

- <span data-ttu-id="0b3a8-390">**Übereinstimmung zulassen** und **Übereinstimmung blockieren**:</span><span class="sxs-lookup"><span data-stu-id="0b3a8-390">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="0b3a8-391">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="0b3a8-391">www.contoso.com</span></span>
  - <span data-ttu-id="0b3a8-392">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="0b3a8-392">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="0b3a8-393">**Allow not matched** and **Block not matched**:</span><span class="sxs-lookup"><span data-stu-id="0b3a8-393">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="0b3a8-394">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="0b3a8-394">123contoso.com</span></span>
  - <span data-ttu-id="0b3a8-395">contoso.com</span><span class="sxs-lookup"><span data-stu-id="0b3a8-395">contoso.com</span></span>
  - <span data-ttu-id="0b3a8-396">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="0b3a8-396">test.com/contoso.com</span></span>
  - <span data-ttu-id="0b3a8-397">www.contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="0b3a8-397">www.contoso.com/abc</span></span>

#### <a name="scenario-right-wildcard-at-top-of-path"></a><span data-ttu-id="0b3a8-398">Szenario: Rechter Platzhalter am oberen Rand des Pfads</span><span class="sxs-lookup"><span data-stu-id="0b3a8-398">Scenario: Right wildcard at top of path</span></span>

<span data-ttu-id="0b3a8-399">**Eintrag**: `contoso.com/a/*`</span><span class="sxs-lookup"><span data-stu-id="0b3a8-399">**Entry**: `contoso.com/a/*`</span></span>

- <span data-ttu-id="0b3a8-400">**Übereinstimmung zulassen** und **Übereinstimmung blockieren**:</span><span class="sxs-lookup"><span data-stu-id="0b3a8-400">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="0b3a8-401">contoso.com/a/b</span><span class="sxs-lookup"><span data-stu-id="0b3a8-401">contoso.com/a/b</span></span>
  - <span data-ttu-id="0b3a8-402">contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="0b3a8-402">contoso.com/a/b/c</span></span>
  - <span data-ttu-id="0b3a8-403">contoso.com/a/?q=joe@t.com</span><span class="sxs-lookup"><span data-stu-id="0b3a8-403">contoso.com/a/?q=joe@t.com</span></span>

- <span data-ttu-id="0b3a8-404">**Allow not matched** and **Block not matched**:</span><span class="sxs-lookup"><span data-stu-id="0b3a8-404">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="0b3a8-405">contoso.com</span><span class="sxs-lookup"><span data-stu-id="0b3a8-405">contoso.com</span></span>
  - <span data-ttu-id="0b3a8-406">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="0b3a8-406">contoso.com/a</span></span>
  - <span data-ttu-id="0b3a8-407">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="0b3a8-407">www.contoso.com</span></span>
  - <span data-ttu-id="0b3a8-408">www.contoso.com/q=a@contoso.com</span><span class="sxs-lookup"><span data-stu-id="0b3a8-408">www.contoso.com/q=a@contoso.com</span></span>

#### <a name="scenario-left-tilde"></a><span data-ttu-id="0b3a8-409">Szenario: Left tilde</span><span class="sxs-lookup"><span data-stu-id="0b3a8-409">Scenario: Left tilde</span></span>

<span data-ttu-id="0b3a8-410">**Eintrag**: `~contoso.com`</span><span class="sxs-lookup"><span data-stu-id="0b3a8-410">**Entry**: `~contoso.com`</span></span>

- <span data-ttu-id="0b3a8-411">**Übereinstimmung zulassen** und **Übereinstimmung blockieren**:</span><span class="sxs-lookup"><span data-stu-id="0b3a8-411">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="0b3a8-412">contoso.com</span><span class="sxs-lookup"><span data-stu-id="0b3a8-412">contoso.com</span></span>
  - <span data-ttu-id="0b3a8-413">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="0b3a8-413">www.contoso.com</span></span>
  - <span data-ttu-id="0b3a8-414">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="0b3a8-414">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="0b3a8-415">**Allow not matched** and **Block not matched**:</span><span class="sxs-lookup"><span data-stu-id="0b3a8-415">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="0b3a8-416">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="0b3a8-416">123contoso.com</span></span>
  - <span data-ttu-id="0b3a8-417">contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="0b3a8-417">contoso.com/abc</span></span>
  - <span data-ttu-id="0b3a8-418">www.contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="0b3a8-418">www.contoso.com/abc</span></span>

#### <a name="scenario-right-wildcard-suffix"></a><span data-ttu-id="0b3a8-419">Szenario: Rechtes Platzhaltersuffix</span><span class="sxs-lookup"><span data-stu-id="0b3a8-419">Scenario: Right wildcard suffix</span></span>

<span data-ttu-id="0b3a8-420">**Eintrag**: `contoso.com/*`</span><span class="sxs-lookup"><span data-stu-id="0b3a8-420">**Entry**: `contoso.com/*`</span></span>

- <span data-ttu-id="0b3a8-421">**Übereinstimmung zulassen** und **Übereinstimmung blockieren**:</span><span class="sxs-lookup"><span data-stu-id="0b3a8-421">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="0b3a8-422">contoso.com/?q=whatever@fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="0b3a8-422">contoso.com/?q=whatever@fabrikam.com</span></span>
  - <span data-ttu-id="0b3a8-423">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="0b3a8-423">contoso.com/a</span></span>
  - <span data-ttu-id="0b3a8-424">contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="0b3a8-424">contoso.com/a/b/c</span></span>
  - <span data-ttu-id="0b3a8-425">contoso.com/ab</span><span class="sxs-lookup"><span data-stu-id="0b3a8-425">contoso.com/ab</span></span>
  - <span data-ttu-id="0b3a8-426">contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="0b3a8-426">contoso.com/b</span></span>
  - <span data-ttu-id="0b3a8-427">contoso.com/b/a/c</span><span class="sxs-lookup"><span data-stu-id="0b3a8-427">contoso.com/b/a/c</span></span>
  - <span data-ttu-id="0b3a8-428">contoso.com/ba</span><span class="sxs-lookup"><span data-stu-id="0b3a8-428">contoso.com/ba</span></span>

- <span data-ttu-id="0b3a8-429">**Nicht übereinstimmend zulassen und** **Block nicht** übereinstimmen: contoso.com</span><span class="sxs-lookup"><span data-stu-id="0b3a8-429">**Allow not matched** and **Block not matched**: contoso.com</span></span>

#### <a name="scenario-left-wildcard-subdomain-and-right-wildcard-suffix"></a><span data-ttu-id="0b3a8-430">Szenario: Linke Platzhalterunterdomäne und rechtes Platzhaltersuffix</span><span class="sxs-lookup"><span data-stu-id="0b3a8-430">Scenario: Left wildcard subdomain and right wildcard suffix</span></span>

<span data-ttu-id="0b3a8-431">**Eintrag**: `*.contoso.com/*`</span><span class="sxs-lookup"><span data-stu-id="0b3a8-431">**Entry**: `*.contoso.com/*`</span></span>

- <span data-ttu-id="0b3a8-432">**Übereinstimmung zulassen** und **Übereinstimmung blockieren**:</span><span class="sxs-lookup"><span data-stu-id="0b3a8-432">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="0b3a8-433">abc.contoso.com/ab</span><span class="sxs-lookup"><span data-stu-id="0b3a8-433">abc.contoso.com/ab</span></span>
  - <span data-ttu-id="0b3a8-434">abc.xyz.contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="0b3a8-434">abc.xyz.contoso.com/a/b/c</span></span>
  - <span data-ttu-id="0b3a8-435">www.contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="0b3a8-435">www.contoso.com/a</span></span>
  - <span data-ttu-id="0b3a8-436">www.contoso.com/b/a/c</span><span class="sxs-lookup"><span data-stu-id="0b3a8-436">www.contoso.com/b/a/c</span></span>
  - <span data-ttu-id="0b3a8-437">xyz.contoso.com/ba</span><span class="sxs-lookup"><span data-stu-id="0b3a8-437">xyz.contoso.com/ba</span></span>

- <span data-ttu-id="0b3a8-438">**Nicht übereinstimmend zulassen und** **Block nicht** übereinstimmen : contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="0b3a8-438">**Allow not matched** and **Block not matched**: contoso.com/b</span></span>

#### <a name="scenario-left-and-right-tilde"></a><span data-ttu-id="0b3a8-439">Szenario: Linker und rechter Tilde</span><span class="sxs-lookup"><span data-stu-id="0b3a8-439">Scenario: Left and right tilde</span></span>

<span data-ttu-id="0b3a8-440">**Eintrag**: `~contoso.com~`</span><span class="sxs-lookup"><span data-stu-id="0b3a8-440">**Entry**: `~contoso.com~`</span></span>

- <span data-ttu-id="0b3a8-441">**Übereinstimmung zulassen** und **Übereinstimmung blockieren**:</span><span class="sxs-lookup"><span data-stu-id="0b3a8-441">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="0b3a8-442">contoso.com</span><span class="sxs-lookup"><span data-stu-id="0b3a8-442">contoso.com</span></span>
  - <span data-ttu-id="0b3a8-443">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="0b3a8-443">contoso.com/a</span></span>
  - <span data-ttu-id="0b3a8-444">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="0b3a8-444">www.contoso.com</span></span>
  - <span data-ttu-id="0b3a8-445">www.contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="0b3a8-445">www.contoso.com/b</span></span>
  - <span data-ttu-id="0b3a8-446">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="0b3a8-446">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="0b3a8-447">**Allow not matched** and **Block not matched**:</span><span class="sxs-lookup"><span data-stu-id="0b3a8-447">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="0b3a8-448">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="0b3a8-448">123contoso.com</span></span>
  - <span data-ttu-id="0b3a8-449">contoso.org</span><span class="sxs-lookup"><span data-stu-id="0b3a8-449">contoso.org</span></span>

#### <a name="scenario-ip-address"></a><span data-ttu-id="0b3a8-450">Szenario: IP-Adresse</span><span class="sxs-lookup"><span data-stu-id="0b3a8-450">Scenario: IP address</span></span>

<span data-ttu-id="0b3a8-451">**Eintrag**: `1.2.3.4`</span><span class="sxs-lookup"><span data-stu-id="0b3a8-451">**Entry**: `1.2.3.4`</span></span>

- <span data-ttu-id="0b3a8-452">**Übereinstimmung zulassen** und **Übereinstimmung blockieren**: 1.2.3.4</span><span class="sxs-lookup"><span data-stu-id="0b3a8-452">**Allow match** and **Block match**: 1.2.3.4</span></span>

- <span data-ttu-id="0b3a8-453">**Allow not matched** and **Block not matched**:</span><span class="sxs-lookup"><span data-stu-id="0b3a8-453">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="0b3a8-454">1.2.3.4/a</span><span class="sxs-lookup"><span data-stu-id="0b3a8-454">1.2.3.4/a</span></span>
  - <span data-ttu-id="0b3a8-455">11.2.3.4/a</span><span class="sxs-lookup"><span data-stu-id="0b3a8-455">11.2.3.4/a</span></span>

#### <a name="ip-address-with-right-wildcard"></a><span data-ttu-id="0b3a8-456">IP-Adresse mit rechtem Platzhalter</span><span class="sxs-lookup"><span data-stu-id="0b3a8-456">IP address with right wildcard</span></span>

<span data-ttu-id="0b3a8-457">**Eintrag**: `1.2.3.4/*`</span><span class="sxs-lookup"><span data-stu-id="0b3a8-457">**Entry**: `1.2.3.4/*`</span></span>

- <span data-ttu-id="0b3a8-458">**Übereinstimmung zulassen** und **Übereinstimmung blockieren**:</span><span class="sxs-lookup"><span data-stu-id="0b3a8-458">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="0b3a8-459">1.2.3.4/b</span><span class="sxs-lookup"><span data-stu-id="0b3a8-459">1.2.3.4/b</span></span>
  - <span data-ttu-id="0b3a8-460">1.2.3.4/baaaa</span><span class="sxs-lookup"><span data-stu-id="0b3a8-460">1.2.3.4/baaaa</span></span>

### <a name="examples-of-invalid-entries"></a><span data-ttu-id="0b3a8-461">Beispiele für ungültige Einträge</span><span class="sxs-lookup"><span data-stu-id="0b3a8-461">Examples of invalid entries</span></span>

<span data-ttu-id="0b3a8-462">Die folgenden Einträge sind ungültig:</span><span class="sxs-lookup"><span data-stu-id="0b3a8-462">The following entries are invalid:</span></span>

- <span data-ttu-id="0b3a8-463">**Fehlende oder ungültige Domänenwerte**:</span><span class="sxs-lookup"><span data-stu-id="0b3a8-463">**Missing or invalid domain values**:</span></span>

  - <span data-ttu-id="0b3a8-464">contoso</span><span class="sxs-lookup"><span data-stu-id="0b3a8-464">contoso</span></span>
  - <span data-ttu-id="0b3a8-465">\*.contoso.\*</span><span class="sxs-lookup"><span data-stu-id="0b3a8-465">\*.contoso.\*</span></span>
  - <span data-ttu-id="0b3a8-466">\*.com</span><span class="sxs-lookup"><span data-stu-id="0b3a8-466">\*.com</span></span>
  - <span data-ttu-id="0b3a8-467">\*.PDF</span><span class="sxs-lookup"><span data-stu-id="0b3a8-467">\*.pdf</span></span>

- <span data-ttu-id="0b3a8-468">**Platzhalter für Text oder ohne Abstandszeichen**:</span><span class="sxs-lookup"><span data-stu-id="0b3a8-468">**Wildcard on text or without spacing characters**:</span></span>

  - <span data-ttu-id="0b3a8-469">\*contoso.com</span><span class="sxs-lookup"><span data-stu-id="0b3a8-469">\*contoso.com</span></span>
  - <span data-ttu-id="0b3a8-470">contoso.com\*</span><span class="sxs-lookup"><span data-stu-id="0b3a8-470">contoso.com\*</span></span>
  - <span data-ttu-id="0b3a8-471">\*1.2.3.4</span><span class="sxs-lookup"><span data-stu-id="0b3a8-471">\*1.2.3.4</span></span>
  - <span data-ttu-id="0b3a8-472">1.2.3.4\*</span><span class="sxs-lookup"><span data-stu-id="0b3a8-472">1.2.3.4\*</span></span>
  - <span data-ttu-id="0b3a8-473">contoso.com/a\*</span><span class="sxs-lookup"><span data-stu-id="0b3a8-473">contoso.com/a\*</span></span>
  - <span data-ttu-id="0b3a8-474">contoso.com/ab\*</span><span class="sxs-lookup"><span data-stu-id="0b3a8-474">contoso.com/ab\*</span></span>

- <span data-ttu-id="0b3a8-475">**IP-Adressen mit Ports**:</span><span class="sxs-lookup"><span data-stu-id="0b3a8-475">**IP addresses with ports**:</span></span>

  - <span data-ttu-id="0b3a8-476">contoso.com:443</span><span class="sxs-lookup"><span data-stu-id="0b3a8-476">contoso.com:443</span></span>
  - <span data-ttu-id="0b3a8-477">abc.contoso.com:25</span><span class="sxs-lookup"><span data-stu-id="0b3a8-477">abc.contoso.com:25</span></span>

- <span data-ttu-id="0b3a8-478">**Nicht beschreibende Platzhalter**:</span><span class="sxs-lookup"><span data-stu-id="0b3a8-478">**Non-descriptive wildcards**:</span></span>

  - \*
  - <span data-ttu-id="0b3a8-479">\*.\*</span><span class="sxs-lookup"><span data-stu-id="0b3a8-479">\*.\*</span></span>

- <span data-ttu-id="0b3a8-480">**Mittlere Platzhalter**:</span><span class="sxs-lookup"><span data-stu-id="0b3a8-480">**Middle wildcards**:</span></span>

  - <span data-ttu-id="0b3a8-481">conto \* so.com</span><span class="sxs-lookup"><span data-stu-id="0b3a8-481">conto\*so.com</span></span>
  - <span data-ttu-id="0b3a8-482">conto~so.com</span><span class="sxs-lookup"><span data-stu-id="0b3a8-482">conto~so.com</span></span>

- <span data-ttu-id="0b3a8-483">**Doppelte Platzhalter**</span><span class="sxs-lookup"><span data-stu-id="0b3a8-483">**Double wildcards**</span></span>

  - <span data-ttu-id="0b3a8-484">contoso.com/\*\*</span><span class="sxs-lookup"><span data-stu-id="0b3a8-484">contoso.com/\*\*</span></span>
  - <span data-ttu-id="0b3a8-485">contoso.com/\*/\*</span><span class="sxs-lookup"><span data-stu-id="0b3a8-485">contoso.com/\*/\*</span></span>

## <a name="domain-pair-syntax-for-spoofed-sender-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="0b3a8-486">Domänenpaarsyntax für spoofierte Absendereinträge in der Mandantenzu-/-sperrliste</span><span class="sxs-lookup"><span data-stu-id="0b3a8-486">Domain pair syntax for spoofed sender entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="0b3a8-487">Ein Domänenpaar für einen gefälschten Absender in der Mandanten-Allow/Block List verwendet die folgende Syntax: `<Spoofed user>, <Sending infrastructure>` .</span><span class="sxs-lookup"><span data-stu-id="0b3a8-487">A domain pair for a spoofed sender in the Tenant Allow/Block List uses the following syntax: `<Spoofed user>, <Sending infrastructure>`.</span></span>

- <span data-ttu-id="0b3a8-488">**Spoofed user**: Dieser Wert umfasst die E-Mail-Adresse des spoofierten Benutzers, der im Feld **Von** in E-Mail-Clients angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="0b3a8-488">**Spoofed user**: This value involves the email address of the spoofed user that's displayed in the **From** box in email clients.</span></span> <span data-ttu-id="0b3a8-489">Diese Adresse wird auch als Adresse `5322.From` bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="0b3a8-489">This address is also known as the `5322.From` address.</span></span> <span data-ttu-id="0b3a8-490">Gültige Werte sind:</span><span class="sxs-lookup"><span data-stu-id="0b3a8-490">Valid values include:</span></span>
  - <span data-ttu-id="0b3a8-491">Eine einzelne E-Mail-Adresse (z. B. chris@contoso.com).</span><span class="sxs-lookup"><span data-stu-id="0b3a8-491">An individual email address (for example, chris@contoso.com).</span></span>
  - <span data-ttu-id="0b3a8-492">Eine E-Mail-Domäne (z. B. contoso.com).</span><span class="sxs-lookup"><span data-stu-id="0b3a8-492">An email domain (for example, contoso.com).</span></span>
  - <span data-ttu-id="0b3a8-493">Das Platzhalterzeichen (z. B. \* ).</span><span class="sxs-lookup"><span data-stu-id="0b3a8-493">The wildcard character (for example, \*).</span></span>

- <span data-ttu-id="0b3a8-494">**Sendende Infrastruktur:** Dieser Wert gibt die Quelle von Nachrichten des spoofierten Benutzers an.</span><span class="sxs-lookup"><span data-stu-id="0b3a8-494">**Sending infrastructure**: This value indicates the source of messages from the spoofed user.</span></span> <span data-ttu-id="0b3a8-495">Gültige Werte sind:</span><span class="sxs-lookup"><span data-stu-id="0b3a8-495">Valid values include:</span></span>
  - <span data-ttu-id="0b3a8-496">Die Domäne in einer Reverse-DNS-Suche (PTR-Eintrag) der IP-Adresse des Quell-E-Mail-Servers (z. B. fabrikam.com).</span><span class="sxs-lookup"><span data-stu-id="0b3a8-496">The domain found in a reverse DNS lookup (PTR record) of the source email server's IP address (for example, fabrikam.com).</span></span>
  - <span data-ttu-id="0b3a8-497">Wenn die Quell-IP-Adresse keinen PTR-Eintrag enthält, wird die sendende Infrastruktur als \<source IP\> /24 identifiziert (z. B. 192.168.100.100/24).</span><span class="sxs-lookup"><span data-stu-id="0b3a8-497">If the source IP address has no PTR record, then the sending infrastructure is identified as \<source IP\>/24 (for example, 192.168.100.100/24).</span></span>

<span data-ttu-id="0b3a8-498">Im Folgenden finden Sie einige Beispiele für gültige Domänenpaare zum Identifizieren gefälschter Absender:</span><span class="sxs-lookup"><span data-stu-id="0b3a8-498">Here are some examples of valid domain pairs to identify spoofed senders:</span></span>

- `contoso.com, 192.168.100.100/24`
- `chris@contoso.com, fabrikam.com`
- `*, contoso.net`

<span data-ttu-id="0b3a8-499">Das Hinzufügen eines Domänenpaars ermöglicht oder blockiert nur die *Kombination* des spoofierten Benutzers *und der sendenden* Infrastruktur.</span><span class="sxs-lookup"><span data-stu-id="0b3a8-499">Adding a domain pair only allows or blocks the *combination* of the spoofed user *and* the sending infrastructure.</span></span> <span data-ttu-id="0b3a8-500">E-Mails vom spoofierten Benutzer aus einer Beliebigen Quelle werden nicht zulässig, und es werden auch keine E-Mails aus der sendenden Infrastrukturquelle für spoofierte Benutzer zulässig.</span><span class="sxs-lookup"><span data-stu-id="0b3a8-500">It does not allow email from the spoofed user from any source, nor does it allow email from the sending infrastructure source for any spoofed user.</span></span>

<span data-ttu-id="0b3a8-501">Beispielsweise fügen Sie einen zulässigen Eintrag für das folgende Domänenpaar hinzu:</span><span class="sxs-lookup"><span data-stu-id="0b3a8-501">For example, you add an allow entry for the following domain pair:</span></span>

- <span data-ttu-id="0b3a8-502">**Domäne**: gmail.com</span><span class="sxs-lookup"><span data-stu-id="0b3a8-502">**Domain**: gmail.com</span></span>
- <span data-ttu-id="0b3a8-503">**Infrastruktur**: tms.mx.com</span><span class="sxs-lookup"><span data-stu-id="0b3a8-503">**Infrastructure**: tms.mx.com</span></span>

<span data-ttu-id="0b3a8-504">Nur Nachrichten von dieser Domäne und *dem sendenden* Infrastrukturpaar dürfen spoofen.</span><span class="sxs-lookup"><span data-stu-id="0b3a8-504">Only messages from that domain *and* sending infrastructure pair are allowed to spoof.</span></span> <span data-ttu-id="0b3a8-505">Andere Absender, die versuchen, gmail.com zu spoofen, sind nicht zulässig.</span><span class="sxs-lookup"><span data-stu-id="0b3a8-505">Other senders attempting to spoof gmail.com aren't allowed.</span></span> <span data-ttu-id="0b3a8-506">Nachrichten von Absendern in anderen Domänen, die von tms.mx.com stammen, werden durch Spoof intelligence überprüft.</span><span class="sxs-lookup"><span data-stu-id="0b3a8-506">Messages from senders in other domains originating from tms.mx.com are checked by spoof intelligence.</span></span>
