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
ms.openlocfilehash: 636114180a1814f5ef842b2a704f2df98488f46e
ms.sourcegitcommit: 5377b00703b6f559092afe44fb61462e97968a60
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/27/2021
ms.locfileid: "52694485"
---
# <a name="manage-the-tenant-allowblock-list"></a><span data-ttu-id="90e66-103">Verwalten der Zulassungs-/Sperrliste des Mandanten</span><span class="sxs-lookup"><span data-stu-id="90e66-103">Manage the Tenant Allow/Block List</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="90e66-104">**Gilt für**</span><span class="sxs-lookup"><span data-stu-id="90e66-104">**Applies to**</span></span>
- [<span data-ttu-id="90e66-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="90e66-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="90e66-106">Microsoft Defender für Office 365 Plan 1 und Plan 2</span><span class="sxs-lookup"><span data-stu-id="90e66-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="90e66-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="90e66-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

> [!NOTE]
>
> <span data-ttu-id="90e66-108">Die in diesem Artikel beschriebenen Features befinden sich in Vorschau, können geändert werden und sind nicht in allen Organisationen verfügbar.</span><span class="sxs-lookup"><span data-stu-id="90e66-108">The features described in this article are in Preview, are subject to change, and are not available in all organizations.</span></span>  <span data-ttu-id="90e66-109">Wenn Ihre Organisation nicht über die in diesem Artikel beschriebenen Spooffunktionen verfügt, lesen Sie die ältere [Spoofverwaltungserfahrung unter Manage spoofed senders using the spoof intelligence policy and spoof intelligence insight in EOP](walkthrough-spoof-intelligence-insight.md).</span><span class="sxs-lookup"><span data-stu-id="90e66-109">If your organization does not have the spoof features as described in this article, see the older spoof management experience at [Manage spoofed senders using the spoof intelligence policy and spoof intelligence insight in EOP](walkthrough-spoof-intelligence-insight.md).</span></span>
>
> <span data-ttu-id="90e66-110">Sie können zu **diesem** Zeitpunkt keine zulässigen URL- oder Dateielemente in der Mandanten zulassen/blockieren-Liste konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="90e66-110">You can't **configure** allowed URL or file items in the Tenant Allow/Block List at this time.</span></span>

<span data-ttu-id="90e66-111">In Microsoft 365 Organisationen mit Postfächern in Exchange Online oder eigenständigen Exchange Online Protection (EOP)-Organisationen ohne Exchange Online Postfächer können Sie mit dem EOP-Filter-Urteil nicht einverstanden sein.</span><span class="sxs-lookup"><span data-stu-id="90e66-111">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, you might disagree with the EOP filtering verdict.</span></span> <span data-ttu-id="90e66-112">Beispielsweise kann eine gute Nachricht als ungültig (falsch positiv) gekennzeichnet werden, oder eine schlechte Nachricht kann als ungültig (falsch negativ) zugelassen werden.</span><span class="sxs-lookup"><span data-stu-id="90e66-112">For example, a good message might be marked as bad (a false positive), or a bad message might be allowed through (a false negative).</span></span>

<span data-ttu-id="90e66-113">Mit der Mandanten-Allow/Block-Liste im Security & Compliance Center können Sie die Filterungs-Microsoft 365 manuell außer Kraft setzen.</span><span class="sxs-lookup"><span data-stu-id="90e66-113">The Tenant Allow/Block List in the Security & Compliance Center gives you a way to manually override the Microsoft 365 filtering verdicts.</span></span> <span data-ttu-id="90e66-114">Die Mandanten zulassen/blockieren Liste wird während des Nachrichtenflusses und zum Zeitpunkt der Benutzerklicks verwendet.</span><span class="sxs-lookup"><span data-stu-id="90e66-114">The Tenant Allow/Block List is used during mail flow and at the time of user clicks.</span></span> <span data-ttu-id="90e66-115">Sie können die folgenden Arten von Außerkraftsetzungen angeben:</span><span class="sxs-lookup"><span data-stu-id="90e66-115">You can specify the following types of overrides:</span></span>

- <span data-ttu-id="90e66-116">ZU blockierende URLs.</span><span class="sxs-lookup"><span data-stu-id="90e66-116">URLs to block.</span></span>
- <span data-ttu-id="90e66-117">Zu blockierende Dateien.</span><span class="sxs-lookup"><span data-stu-id="90e66-117">Files to block.</span></span>
- <span data-ttu-id="90e66-118">Spoofed senders to allow or block.</span><span class="sxs-lookup"><span data-stu-id="90e66-118">Spoofed senders to allow or block.</span></span> <span data-ttu-id="90e66-119">Wenn Sie das Allow- oder Block-Urteil in der [Spoof Intelligence-Einsicht](learn-about-spoof-intelligence.md)außer Kraft setzen, wird der gefälschte Absender zu einem manuellen Zulassen- oder Blockiereneintrag, der nur auf der Registerkarte **Spoof** in der Mandanten-Zulassen-/Sperrliste angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="90e66-119">If you override the allow or block verdict in the [spoof intelligence insight](learn-about-spoof-intelligence.md), the spoofed sender becomes a manual allow or block entry that only appears on the **Spoof** tab in the Tenant Allow/Block List.</span></span> <span data-ttu-id="90e66-120">Sie können hier auch manuell Zulassen oder Blockieren von Einträgen für spoofierte Absender erstellen, bevor sie von Spoof Intelligence erkannt werden.</span><span class="sxs-lookup"><span data-stu-id="90e66-120">You can also manually create allow or block entries for spoofed senders here before they're detected by spoof intelligence.</span></span>

<span data-ttu-id="90e66-121">In diesem Artikel wird beschrieben, wie Sie Einträge in der Mandanten zulassen/blockieren-Liste im Security & Compliance Center oder in PowerShell (Exchange Online PowerShell für Microsoft 365-Organisationen mit Postfächern in Exchange Online; eigenständige EOP PowerShell für Organisationen ohne Exchange Online-Postfächer) konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="90e66-121">This article describes how to configure entries in the Tenant Allow/Block List in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="90e66-122">Was sollten Sie wissen, bevor Sie beginnen?</span><span class="sxs-lookup"><span data-stu-id="90e66-122">What do you need to know before you begin?</span></span>

- <span data-ttu-id="90e66-123">Sie öffnen das Security & Compliance Center unter <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="90e66-123">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="90e66-124">Um direkt zur Seite **Mandanten zulassen/blockieren zu** wechseln, verwenden Sie <https://protection.office.com/tenantAllowBlockList> .</span><span class="sxs-lookup"><span data-stu-id="90e66-124">To go directly to the **Tenant Allow/Block List** page, use <https://protection.office.com/tenantAllowBlockList>.</span></span>

- <span data-ttu-id="90e66-125">Sie geben Dateien mithilfe des SHA256-Hashwerts der Datei an.</span><span class="sxs-lookup"><span data-stu-id="90e66-125">You specify files by using the SHA256 hash value of the file.</span></span> <span data-ttu-id="90e66-126">Führen Sie den folgenden Befehl in einer Eingabeaufforderung aus, um den SHA256-Hashwert einer Datei in Windows zu finden:</span><span class="sxs-lookup"><span data-stu-id="90e66-126">To find the SHA256 hash value of a file in Windows, run the following command in a Command Prompt:</span></span>

  ```console
  certutil.exe -hashfile "<Path>\<Filename>" SHA256
  ```

  <span data-ttu-id="90e66-127">Ein Beispielwert ist `768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3a` .</span><span class="sxs-lookup"><span data-stu-id="90e66-127">An example value is `768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3a`.</span></span> <span data-ttu-id="90e66-128">#A0 (Perceptual Hash) werden nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="90e66-128">Perceptual hash (pHash) values are not supported.</span></span>

- <span data-ttu-id="90e66-129">Die verfügbaren #A0 werden weiter unten in diesem Artikel in der #A1 für den Abschnitt [Mandanten zulassen/blockieren](#url-syntax-for-the-tenant-allowblock-list) beschrieben.</span><span class="sxs-lookup"><span data-stu-id="90e66-129">The available URL values are described in the [URL syntax for the Tenant Allow/Block List](#url-syntax-for-the-tenant-allowblock-list) section later in this article.</span></span>

- <span data-ttu-id="90e66-130">Die Mandantenzu-/-sperrliste ermöglicht maximal 500 Einträge für URLs und 500 Einträge für Dateihashes.</span><span class="sxs-lookup"><span data-stu-id="90e66-130">The Tenant Allow/Block List allows a maximum of 500 entries for URLs, and 500 entries for file hashes.</span></span>

- <span data-ttu-id="90e66-131">Die maximale Anzahl von Zeichen für jeden Eintrag ist:</span><span class="sxs-lookup"><span data-stu-id="90e66-131">The maximum number of characters for each entry is:</span></span>
  - <span data-ttu-id="90e66-132">Dateihashes = 64</span><span class="sxs-lookup"><span data-stu-id="90e66-132">File hashes = 64</span></span>
  - <span data-ttu-id="90e66-133">URL = 250</span><span class="sxs-lookup"><span data-stu-id="90e66-133">URL = 250</span></span>

- <span data-ttu-id="90e66-134">Ein Eintrag sollte innerhalb von 30 Minuten aktiv sein.</span><span class="sxs-lookup"><span data-stu-id="90e66-134">An entry should be active within 30 minutes.</span></span>

- <span data-ttu-id="90e66-135">Standardmäßig laufen Einträge in der Mandanten-Zulassen-/Sperrliste nach 30 Tagen ab.</span><span class="sxs-lookup"><span data-stu-id="90e66-135">By default, entries in the Tenant Allow/Block List will expire after 30 days.</span></span> <span data-ttu-id="90e66-136">Sie können ein Datum angeben oder festlegen, dass es nie abläuft.</span><span class="sxs-lookup"><span data-stu-id="90e66-136">You can specify a date or set them to never expire.</span></span>

- <span data-ttu-id="90e66-137">Wie Sie eine Verbindung mit Exchange Online PowerShell herstellen, finden Sie unter [Herstellen einer Verbindung mit Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="90e66-137">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="90e66-138">Informationen zum Herstellen einer Verbindung mit dem eigenständigen Exchange Online Protection PowerShell finden Sie unter [Verbinden mit PowerShell in Exchange Online Protection](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="90e66-138">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="90e66-139">Sie müssen in Exchange Online Berechtigungen erhalten, bevor Sie die in diesem Artikel beschriebenen Schritte ausführen können:</span><span class="sxs-lookup"><span data-stu-id="90e66-139">You need to be assigned permissions in Exchange Online before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="90e66-140">**URLs und Dateien**:</span><span class="sxs-lookup"><span data-stu-id="90e66-140">**URLs and files**:</span></span>
    - <span data-ttu-id="90e66-141">Zum Hinzufügen und Entfernen von Werten aus der Mandantenberechtigungs-/Sperrliste müssen Sie Mitglied der Rollengruppen Organisationsverwaltung oder **Sicherheitsadministrator** sein. </span><span class="sxs-lookup"><span data-stu-id="90e66-141">To add and remove values from the Tenant Allow/Block List, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
    - <span data-ttu-id="90e66-142">Für den schreibgeschützten Zugriff auf die Mandantenzugriffs-/Sperrliste müssen Sie Mitglied der Rollengruppen **"Globaler Leser"** oder **"Sicherheitsleser"** sein.</span><span class="sxs-lookup"><span data-stu-id="90e66-142">For read-only access to the Tenant Allow/Block List, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>
  - <span data-ttu-id="90e66-143">**Spoofing**: Eine der folgenden Kombinationen:</span><span class="sxs-lookup"><span data-stu-id="90e66-143">**Spoofing**: One of the following combinations:</span></span>
    - <span data-ttu-id="90e66-144">**Organisationsverwaltung**</span><span class="sxs-lookup"><span data-stu-id="90e66-144">**Organization Management**</span></span>
    - <span data-ttu-id="90e66-145">**Sicherheitsadministrator** und **Nur-Ansicht-Konfiguration** oder **Nur-Ansicht-Organisationsverwaltung**. <u></u></span><span class="sxs-lookup"><span data-stu-id="90e66-145">**Security Administrator** <u>and</u> **View-Only Configuration** or **View-Only Organization Management**.</span></span>

  <span data-ttu-id="90e66-146">Weitere Informationen finden Sie unter [Berechtigungen in Exchange Online](/exchange/permissions-exo/permissions-exo).</span><span class="sxs-lookup"><span data-stu-id="90e66-146">For more information, see [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo).</span></span>

  > [!NOTE]
  >
  > - <span data-ttu-id="90e66-147">Durch das Hinzufügen von Benutzern zur entsprechenden Azure Active Directory-Rolle im Microsoft 365 Admin Center erhalten Benutzer die erforderlichen Berechtigungen _und_ Berechtigungen für andere Features in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="90e66-147">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="90e66-148">Weitere Informationen finden Sie unter [Informationen zu Administratorrollen](../../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="90e66-148">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  >
  > - <span data-ttu-id="90e66-149">Die Rollengruppe **Organisationsverwaltung mit Leserechten** in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) ermöglicht auch einen schreibgeschützten Zugriff auf das Feature.</span><span class="sxs-lookup"><span data-stu-id="90e66-149">The **View-Only Organization Management** role group in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

## <a name="use-the-security--compliance-center-to-create-block-url-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="90e66-150">Verwenden des Security & Compliance Center zum Erstellen von Block-URL-Einträgen in der Mandantenzu-/-sperrliste</span><span class="sxs-lookup"><span data-stu-id="90e66-150">Use the Security & Compliance Center to create block URL entries in the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="90e66-151">Wechseln Sie im Security & Compliance Center zu Richtlinien für die **Bedrohungsverwaltung** \>  \> **Mandanten zulassen/blockieren Listen**.</span><span class="sxs-lookup"><span data-stu-id="90e66-151">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="90e66-152">Überprüfen Sie auf der Seite Mandanten **zulassen/blockieren,** ob die Registerkarte **URLs** ausgewählt ist, und klicken Sie dann auf **Blockieren.**</span><span class="sxs-lookup"><span data-stu-id="90e66-152">On the **Tenant Allow/Block List** page, verify that the **URLs** tab is selected, and then click **Block**</span></span>

3. <span data-ttu-id="90e66-153">Konfigurieren Sie **im angezeigten** Flyout UrLs blockieren die folgenden Einstellungen:</span><span class="sxs-lookup"><span data-stu-id="90e66-153">In the **Block URLs** flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="90e66-154">**Zu blockierende URLs hinzufügen:** Geben Sie eine URL pro Zeile ein, bis zu maximal 20.</span><span class="sxs-lookup"><span data-stu-id="90e66-154">**Add URLs to block**: Enter one URL per line, up to a maximum of 20.</span></span> <span data-ttu-id="90e66-155">Weitere Informationen zur Syntax für #A0 finden Sie in der URL-Syntax für den Abschnitt [Mandantenzu-/Sperrliste](#url-syntax-for-the-tenant-allowblock-list) weiter unten in diesem Artikel.</span><span class="sxs-lookup"><span data-stu-id="90e66-155">For details about the syntax for URL entries, see the [URL syntax for the Tenant Allow/Block List](#url-syntax-for-the-tenant-allowblock-list) section later in this article.</span></span>

   - <span data-ttu-id="90e66-156">**Nie ablaufen:** Gehen Sie wie folgt vor:</span><span class="sxs-lookup"><span data-stu-id="90e66-156">**Never expire**: Do one of the following steps:</span></span>

     - <span data-ttu-id="90e66-157">Überprüfen Sie, ob die Einstellung deaktiviert ist ( Umschalten ) und verwenden Sie das Feld Läuft auf, um das ![ ](../../media/scc-toggle-off.png) Ablaufdatum für die Einträge anzugeben. </span><span class="sxs-lookup"><span data-stu-id="90e66-157">Verify the setting is turned off (![Toggle off](../../media/scc-toggle-off.png)) and use the **Expires on** box to specify the expiration date for the entries.</span></span>

       <span data-ttu-id="90e66-158">oder</span><span class="sxs-lookup"><span data-stu-id="90e66-158">or</span></span>

     - <span data-ttu-id="90e66-159">Verschieben Sie den Umschalter nach rechts, um die Einträge so zu konfigurieren, dass sie nie ablaufen:</span><span class="sxs-lookup"><span data-stu-id="90e66-159">Move the toggle to the right to configure the entries to never expire:</span></span> ![Umschaltfläche ein](../../media/scc-toggle-on.png)<span data-ttu-id="90e66-161">.</span><span class="sxs-lookup"><span data-stu-id="90e66-161">.</span></span>

   - <span data-ttu-id="90e66-162">**Optionaler Hinweis:** Geben Sie beschreibenden Text für die Einträge ein.</span><span class="sxs-lookup"><span data-stu-id="90e66-162">**Optional note**: Enter descriptive text for the entries.</span></span>

4. <span data-ttu-id="90e66-163">Klicken Sie nach Abschluss des Vorgangs auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="90e66-163">When you're finished, click **Add**.</span></span>

## <a name="use-the-security--compliance-center-to-create-block-file-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="90e66-164">Verwenden des Security & Compliance Center zum Erstellen von Blockdateieinträgen in der Mandantenzu-/-sperrliste</span><span class="sxs-lookup"><span data-stu-id="90e66-164">Use the Security & Compliance Center to create block file entries in the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="90e66-165">Wechseln Sie im Security & Compliance Center zu Richtlinien für die **Bedrohungsverwaltung** \>  \> **Mandanten zulassen/blockieren Listen**.</span><span class="sxs-lookup"><span data-stu-id="90e66-165">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="90e66-166">Wählen Sie auf der Seite Mandanten **zulassen/blockieren** die Registerkarte **Dateien** aus, und klicken Sie dann auf **Blockieren**.</span><span class="sxs-lookup"><span data-stu-id="90e66-166">On the **Tenant Allow/Block List** page, select the **Files** tab, and then click **Block**.</span></span>

3. <span data-ttu-id="90e66-167">Konfigurieren Sie **im angezeigten Flyout** Dateien zum Blockieren von Dateien hinzufügen die folgenden Einstellungen:</span><span class="sxs-lookup"><span data-stu-id="90e66-167">In the **Add files to block** flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="90e66-168">**Hinzufügen von Dateihashes:** Geben Sie einen SHA256-Hashwert pro Zeile ein, bis zu maximal 20.</span><span class="sxs-lookup"><span data-stu-id="90e66-168">**Add file hashes**: Enter one SHA256 hash value per line, up to a maximum of 20.</span></span>

   - <span data-ttu-id="90e66-169">**Nie ablaufen:** Gehen Sie wie folgt vor:</span><span class="sxs-lookup"><span data-stu-id="90e66-169">**Never expire**: Do one of the following steps:</span></span>

     - <span data-ttu-id="90e66-170">Überprüfen Sie, ob die Einstellung deaktiviert ist ( Umschalten ) und verwenden Sie das Feld Läuft auf, um das ![ ](../../media/scc-toggle-off.png) Ablaufdatum für die Einträge anzugeben. </span><span class="sxs-lookup"><span data-stu-id="90e66-170">Verify the setting is turned off (![Toggle off](../../media/scc-toggle-off.png)) and use the **Expires on** box to specify the expiration date for the entries.</span></span>

     <span data-ttu-id="90e66-171">oder</span><span class="sxs-lookup"><span data-stu-id="90e66-171">or</span></span>

     - <span data-ttu-id="90e66-172">Verschieben Sie den Umschalter nach rechts, um die Einträge so zu konfigurieren, dass sie nie ablaufen:</span><span class="sxs-lookup"><span data-stu-id="90e66-172">Move the toggle to the right to configure the entries to never expire:</span></span> ![Umschaltfläche ein](../../media/scc-toggle-on.png)<span data-ttu-id="90e66-174">.</span><span class="sxs-lookup"><span data-stu-id="90e66-174">.</span></span>

   - <span data-ttu-id="90e66-175">**Optionaler Hinweis:** Geben Sie beschreibenden Text für die Einträge ein.</span><span class="sxs-lookup"><span data-stu-id="90e66-175">**Optional note**: Enter descriptive text for the entries.</span></span>

4. <span data-ttu-id="90e66-176">Klicken Sie nach Abschluss des Vorgangs auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="90e66-176">When you're finished, click **Add**.</span></span>

## <a name="use-the-security--compliance-center-to-create-allow-or-block-spoofed-sender-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="90e66-177">Verwenden des Security & Compliance Center zum Erstellen oder Blockieren gefälschter Absendereinträge in der Mandantenzu-/Sperrliste</span><span class="sxs-lookup"><span data-stu-id="90e66-177">Use the Security & Compliance Center to create allow or block spoofed sender entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="90e66-178">**Hinweise**:</span><span class="sxs-lookup"><span data-stu-id="90e66-178">**Notes**:</span></span>

- <span data-ttu-id="90e66-179">Nur die _Kombination_ aus dem  spoofierten Benutzer und der sendenden Infrastruktur, wie im Domänenpaar definiert, ist ausdrücklich zulässig oder von Spoofing blockiert.</span><span class="sxs-lookup"><span data-stu-id="90e66-179">Only the _combination_ of the spoofed user _and_ the sending infrastructure as defined in the domain pair is specifically allowed or blocked from spoofing.</span></span>
- <span data-ttu-id="90e66-180">Wenn Sie einen zulässigen oder blockierten Eintrag für ein Domänenpaar konfigurieren, werden Nachrichten dieses Domänenpaars nicht mehr in der Spoof Intelligence-Einsicht angezeigt.</span><span class="sxs-lookup"><span data-stu-id="90e66-180">When you configure an allow or block entry for a domain pair, messages from that domain pair no longer appear in the spoof intelligence insight.</span></span>
- <span data-ttu-id="90e66-181">Einträge für spoofierte Absender laufen nie ab.</span><span class="sxs-lookup"><span data-stu-id="90e66-181">Entries for spoofed senders never expire.</span></span>

1. <span data-ttu-id="90e66-182">Wechseln Sie im Security & Compliance Center zu Richtlinien für die **Bedrohungsverwaltung** \>  \> **Mandanten zulassen/blockieren Listen**.</span><span class="sxs-lookup"><span data-stu-id="90e66-182">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="90e66-183">Wählen Sie auf der Seite Mandanten **zulassen/blockieren** die Registerkarte **Spoofing** aus, und klicken Sie dann auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="90e66-183">On the **Tenant Allow/Block List** page, select the **Spoofing** tab, and then click **Add**.</span></span>

3. <span data-ttu-id="90e66-184">Konfigurieren Sie **im angezeigten** Flyout Neue Domänenpaare hinzufügen die folgenden Einstellungen:</span><span class="sxs-lookup"><span data-stu-id="90e66-184">In the **Add new domain pairs** flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="90e66-185">**Hinzufügen neuer Domänenpaare mit Platzhaltern:** Geben Sie ein Domänenpaar pro Zeile ein, bis maximal 20.</span><span class="sxs-lookup"><span data-stu-id="90e66-185">**Add new domain pairs with wildcards**: Enter one domain pair per line, up to a maximum of 20.</span></span> <span data-ttu-id="90e66-186">Weitere Informationen zur Syntax für spoofierte Absendereinträge finden Sie in der Syntax des Domänenpaars für spoofierte Absendereinträge im Abschnitt [Mandantenzu-/-sperrliste](#domain-pair-syntax-for-spoofed-sender-entries-in-the-tenant-allowblock-list) weiter unten in diesem Artikel.</span><span class="sxs-lookup"><span data-stu-id="90e66-186">For details about the syntax for spoofed sender entries, see the [Domain pair syntax for spoofed sender entries in the Tenant Allow/Block List](#domain-pair-syntax-for-spoofed-sender-entries-in-the-tenant-allowblock-list) section later in this article.</span></span>

   - <span data-ttu-id="90e66-187">**Spooftyp**: Wählen Sie einen der folgenden Werte aus:</span><span class="sxs-lookup"><span data-stu-id="90e66-187">**Spoof type**: Select one of the following values:</span></span>
     - <span data-ttu-id="90e66-188">**Intern:** Der gefälschte Absender befindet sich in einer Domäne, die zu Ihrer Organisation gehört (eine [akzeptierte Domäne](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)).</span><span class="sxs-lookup"><span data-stu-id="90e66-188">**Internal**: The spoofed sender is in a domain that belongs to your organization (an [accepted domain](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)).</span></span>
     - <span data-ttu-id="90e66-189">**Extern:** Der gefälschte Absender befindet sich in einer externen Domäne.</span><span class="sxs-lookup"><span data-stu-id="90e66-189">**External**: The spoofed sender is in an external domain.</span></span>

   - <span data-ttu-id="90e66-190">**Aktion**: Wählen Sie **Zulassen** oder **Blockieren aus.**</span><span class="sxs-lookup"><span data-stu-id="90e66-190">**Action**: Select **Allow** or **Block**.</span></span>

4. <span data-ttu-id="90e66-191">Klicken Sie nach Abschluss des Vorgangs auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="90e66-191">When you're finished, click **Add**.</span></span>

## <a name="use-the-security--compliance-center-to-view-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="90e66-192">Verwenden des Security & Compliance Center zum Anzeigen von Einträgen in der Mandantenzu-/-sperrliste</span><span class="sxs-lookup"><span data-stu-id="90e66-192">Use the Security & Compliance Center to view entries in the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="90e66-193">Wechseln Sie im Security & Compliance Center zu Richtlinien für die **Bedrohungsverwaltung** \>  \> **Mandanten zulassen/blockieren Listen**.</span><span class="sxs-lookup"><span data-stu-id="90e66-193">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="90e66-194">Wählen Sie die registerkarte aus, die Sie möchten.</span><span class="sxs-lookup"><span data-stu-id="90e66-194">Select the tab you want.</span></span> <span data-ttu-id="90e66-195">Die verfügbaren Spalten hängen von der ausgewählten Registerkarte ab:</span><span class="sxs-lookup"><span data-stu-id="90e66-195">The columns that are available depend on the tab you selected:</span></span>

   - <span data-ttu-id="90e66-196">**URLs**:</span><span class="sxs-lookup"><span data-stu-id="90e66-196">**URLs**:</span></span>
     - <span data-ttu-id="90e66-197">**Wert**: Die URL.</span><span class="sxs-lookup"><span data-stu-id="90e66-197">**Value**: The URL.</span></span>
     - <span data-ttu-id="90e66-198">**Aktion**: Der Wert **Block**.</span><span class="sxs-lookup"><span data-stu-id="90e66-198">**Action**: The value **Block**.</span></span>
     - <span data-ttu-id="90e66-199">**Datum der letzten Aktualisierung**</span><span class="sxs-lookup"><span data-stu-id="90e66-199">**Last updated date**</span></span>
     - <span data-ttu-id="90e66-200">**Ablaufdatum**</span><span class="sxs-lookup"><span data-stu-id="90e66-200">**Expiration date**</span></span>
     - <span data-ttu-id="90e66-201">**Hinweis**</span><span class="sxs-lookup"><span data-stu-id="90e66-201">**Note**</span></span>

   - <span data-ttu-id="90e66-202">**Files**</span><span class="sxs-lookup"><span data-stu-id="90e66-202">**Files**</span></span>
     - <span data-ttu-id="90e66-203">**Wert**: Der Dateihash.</span><span class="sxs-lookup"><span data-stu-id="90e66-203">**Value**: The file hash.</span></span>
     - <span data-ttu-id="90e66-204">**Aktion**: Der Wert **Block**.</span><span class="sxs-lookup"><span data-stu-id="90e66-204">**Action**: The value **Block**.</span></span>
     - <span data-ttu-id="90e66-205">**Datum der letzten Aktualisierung**</span><span class="sxs-lookup"><span data-stu-id="90e66-205">**Last updated date**</span></span>
     - <span data-ttu-id="90e66-206">**Ablaufdatum**</span><span class="sxs-lookup"><span data-stu-id="90e66-206">**Expiration date**</span></span>
     - <span data-ttu-id="90e66-207">**Hinweis**</span><span class="sxs-lookup"><span data-stu-id="90e66-207">**Note**</span></span>

   - <span data-ttu-id="90e66-208">**Spoofing**</span><span class="sxs-lookup"><span data-stu-id="90e66-208">**Spoofing**</span></span>
     - <span data-ttu-id="90e66-209">**Spoofed user**</span><span class="sxs-lookup"><span data-stu-id="90e66-209">**Spoofed user**</span></span>
     - <span data-ttu-id="90e66-210">**Senden von Infrastruktur**</span><span class="sxs-lookup"><span data-stu-id="90e66-210">**Sending infrastructure**</span></span>
     - <span data-ttu-id="90e66-211">**Spooftyp**: Der Wert **Internal** oder **External**.</span><span class="sxs-lookup"><span data-stu-id="90e66-211">**Spoof type**: The value **Internal** or **External**.</span></span>
     - <span data-ttu-id="90e66-212">**Aktion**: Der Wert **Block** oder **Allow**.</span><span class="sxs-lookup"><span data-stu-id="90e66-212">**Action**: The value **Block** or **Allow**.</span></span>

   <span data-ttu-id="90e66-213">Sie können auf eine Spaltenüberschrift klicken, um in aufsteigender oder absteigender Reihenfolge zu sortieren.</span><span class="sxs-lookup"><span data-stu-id="90e66-213">You can click on a column heading to sort in ascending or descending order.</span></span>

   <span data-ttu-id="90e66-214">Sie können auf **Gruppe klicken,** um die Ergebnisse zu gruppieren.</span><span class="sxs-lookup"><span data-stu-id="90e66-214">You can click **Group** to group the results.</span></span> <span data-ttu-id="90e66-215">Die verfügbaren Werte hängen von der ausgewählten Registerkarte ab:</span><span class="sxs-lookup"><span data-stu-id="90e66-215">The values that are available depend on the tab you selected:</span></span>

   - <span data-ttu-id="90e66-216">**URLs**: Sie können die Ergebnisse nach **Aktion gruppieren.**</span><span class="sxs-lookup"><span data-stu-id="90e66-216">**URLs**: You can group the results by **Action**.</span></span>
   - <span data-ttu-id="90e66-217">**Dateien**: Sie können die Ergebnisse nach **Aktion gruppieren.**</span><span class="sxs-lookup"><span data-stu-id="90e66-217">**Files**: You can group the results by **Action**.</span></span>
   - <span data-ttu-id="90e66-218">**Absenderdomänen für die BCL-Umgehung:** **Die Gruppe** ist auf dieser Registerkarte nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="90e66-218">**Sender domains for BCL bypass**: **Group** is not available on this tab.</span></span>
   - <span data-ttu-id="90e66-219">**Spoofing**: Sie können die Ergebnisse nach **Aktions-** oder **Spooftyp gruppieren.**</span><span class="sxs-lookup"><span data-stu-id="90e66-219">**Spoofing**: You can group the results by **Action** or **Spoof type**.</span></span>

   <span data-ttu-id="90e66-220">Klicken **Sie auf Suchen,** geben Sie einen Wert ganz oder teilweise ein, und drücken Sie die EINGABETASTE, um einen bestimmten Wert zu finden.</span><span class="sxs-lookup"><span data-stu-id="90e66-220">Click **Search**, enter all or part of a value, and then press ENTER to find a specific value.</span></span> <span data-ttu-id="90e66-221">Wenn Sie fertig sind, klicken Sie auf **Suche löschen Suchsymbol** ![ löschen ](../../media/b6512677-5e7b-42b0-a8a3-3be1d7fa23ee.gif) .</span><span class="sxs-lookup"><span data-stu-id="90e66-221">When you're finished, click **Clear search** ![Clear search icon](../../media/b6512677-5e7b-42b0-a8a3-3be1d7fa23ee.gif).</span></span>

   <span data-ttu-id="90e66-222">Klicken **Sie auf Filtern,** um die Ergebnisse zu filtern.</span><span class="sxs-lookup"><span data-stu-id="90e66-222">Click **Filter** to filter the results.</span></span> <span data-ttu-id="90e66-223">Die im angezeigten **Filterf** flyout verfügbaren Werte hängen von der ausgewählten Registerkarte ab:</span><span class="sxs-lookup"><span data-stu-id="90e66-223">The values that are available in **Filter** flyout that appears depend on the tab you selected:</span></span>

   - <span data-ttu-id="90e66-224">**URLs**</span><span class="sxs-lookup"><span data-stu-id="90e66-224">**URLs**</span></span>
     - <span data-ttu-id="90e66-225">**Action**</span><span class="sxs-lookup"><span data-stu-id="90e66-225">**Action**</span></span>
     - <span data-ttu-id="90e66-226">**Nie ablaufen**</span><span class="sxs-lookup"><span data-stu-id="90e66-226">**Never expire**</span></span>
     - <span data-ttu-id="90e66-227">**Datum der letzten Aktualisierung**</span><span class="sxs-lookup"><span data-stu-id="90e66-227">**Last updated date**</span></span>
     - <span data-ttu-id="90e66-228">**Ablaufdatum**</span><span class="sxs-lookup"><span data-stu-id="90e66-228">**Expiration date**</span></span>

   - <span data-ttu-id="90e66-229">**Files**</span><span class="sxs-lookup"><span data-stu-id="90e66-229">**Files**</span></span>
     - <span data-ttu-id="90e66-230">**Action**</span><span class="sxs-lookup"><span data-stu-id="90e66-230">**Action**</span></span>
     - <span data-ttu-id="90e66-231">**Nie ablaufen**</span><span class="sxs-lookup"><span data-stu-id="90e66-231">**Never expire**</span></span>
     - <span data-ttu-id="90e66-232">**Datum der letzten Aktualisierung**</span><span class="sxs-lookup"><span data-stu-id="90e66-232">**Last updated date**</span></span>
     - <span data-ttu-id="90e66-233">**Ablaufdatum**</span><span class="sxs-lookup"><span data-stu-id="90e66-233">**Expiration date**</span></span>

   - <span data-ttu-id="90e66-234">**Absenderdomänen für die BCL-Umgehung**</span><span class="sxs-lookup"><span data-stu-id="90e66-234">**Sender domains for BCL bypass**</span></span>
     - <span data-ttu-id="90e66-235">**Nie ablaufen**</span><span class="sxs-lookup"><span data-stu-id="90e66-235">**Never expire**</span></span>
     - <span data-ttu-id="90e66-236">**Datum der letzten Aktualisierung**</span><span class="sxs-lookup"><span data-stu-id="90e66-236">**Last updated date**</span></span>
     - <span data-ttu-id="90e66-237">**Ablaufdatum**</span><span class="sxs-lookup"><span data-stu-id="90e66-237">**Expiration date**</span></span>

   - <span data-ttu-id="90e66-238">**Spoofing**</span><span class="sxs-lookup"><span data-stu-id="90e66-238">**Spoofing**</span></span>
     - <span data-ttu-id="90e66-239">**Action**</span><span class="sxs-lookup"><span data-stu-id="90e66-239">**Action**</span></span>
     - <span data-ttu-id="90e66-240">**Spooftyp**</span><span class="sxs-lookup"><span data-stu-id="90e66-240">**Spoof type**</span></span>

   <span data-ttu-id="90e66-241">Klicken Sie nach Abschluss des Abschlusses auf **Übernehmen**.</span><span class="sxs-lookup"><span data-stu-id="90e66-241">When you're finished, click **Apply**.</span></span> <span data-ttu-id="90e66-242">Klicken Sie zum Löschen vorhandener Filter auf **Filter,** und klicken Sie im angezeigten **Flyout** Filter **auf Filter löschen.**</span><span class="sxs-lookup"><span data-stu-id="90e66-242">To clear existing filters, click **Filter**, and in the **Filter** flyout that appears, click **Clear filters**.</span></span>

## <a name="use-the-security--compliance-center-to-modify-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="90e66-243">Verwenden des Security & Compliance Center zum Ändern von Einträgen in der Mandantenzu-/-sperrliste</span><span class="sxs-lookup"><span data-stu-id="90e66-243">Use the Security & Compliance Center to modify entries in the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="90e66-244">Wechseln Sie im Security & Compliance Center zu Richtlinien für die **Bedrohungsverwaltung** \>  \> **Mandanten zulassen/blockieren Listen**.</span><span class="sxs-lookup"><span data-stu-id="90e66-244">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="90e66-245">Wählen Sie die Registerkarte aus, die den Typ des Eintrags enthält, den Sie ändern möchten:</span><span class="sxs-lookup"><span data-stu-id="90e66-245">Select the tab that contains the type of entry that you want to modify:</span></span>
   - <span data-ttu-id="90e66-246">**URLs**</span><span class="sxs-lookup"><span data-stu-id="90e66-246">**URLs**</span></span>
   - <span data-ttu-id="90e66-247">**Files**</span><span class="sxs-lookup"><span data-stu-id="90e66-247">**Files**</span></span>
   - <span data-ttu-id="90e66-248">**Absenderdomänen für die BCL-Umgehung**</span><span class="sxs-lookup"><span data-stu-id="90e66-248">**Sender domains for BCL bypass**</span></span>
   - <span data-ttu-id="90e66-249">**Spoofing**</span><span class="sxs-lookup"><span data-stu-id="90e66-249">**Spoofing**</span></span>

3. <span data-ttu-id="90e66-250">Wählen Sie den Eintrag aus, den Sie ändern möchten, und klicken Sie dann auf **Bearbeiten** ![ (Symbol). ](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png)</span><span class="sxs-lookup"><span data-stu-id="90e66-250">Select the entry that you want to modify, and then click **Edit** ![Edit icon](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png).</span></span> <span data-ttu-id="90e66-251">Die Werte, die Sie im angezeigten Flyout ändern können, hängen von der Registerkarte ab, die Sie im vorherigen Schritt ausgewählt haben:</span><span class="sxs-lookup"><span data-stu-id="90e66-251">The values that you are able to modify in the flyout that appears depend on the tab you selected in the previous step:</span></span>

   - <span data-ttu-id="90e66-252">**URLs**</span><span class="sxs-lookup"><span data-stu-id="90e66-252">**URLs**</span></span>
     - <span data-ttu-id="90e66-253">**Niemals ablaufen** und/oder Ablaufdatum.</span><span class="sxs-lookup"><span data-stu-id="90e66-253">**Never expire** and/or expiration date.</span></span>
     - <span data-ttu-id="90e66-254">**Optionaler Hinweis**</span><span class="sxs-lookup"><span data-stu-id="90e66-254">**Optional note**</span></span>

   - <span data-ttu-id="90e66-255">**Files**</span><span class="sxs-lookup"><span data-stu-id="90e66-255">**Files**</span></span>
     - <span data-ttu-id="90e66-256">**Niemals ablaufen** und/oder Ablaufdatum.</span><span class="sxs-lookup"><span data-stu-id="90e66-256">**Never expire** and/or expiration date.</span></span>
     - <span data-ttu-id="90e66-257">**Optionaler Hinweis**</span><span class="sxs-lookup"><span data-stu-id="90e66-257">**Optional note**</span></span>

   - <span data-ttu-id="90e66-258">**Absenderdomänen für die BCL-Umgehung**</span><span class="sxs-lookup"><span data-stu-id="90e66-258">**Sender domains for BCL bypass**</span></span>
     - <span data-ttu-id="90e66-259">**Niemals ablaufen** und/oder Ablaufdatum.</span><span class="sxs-lookup"><span data-stu-id="90e66-259">**Never expire** and/or expiration date.</span></span>

   - <span data-ttu-id="90e66-260">**Spoofing**</span><span class="sxs-lookup"><span data-stu-id="90e66-260">**Spoofing**</span></span>
     - <span data-ttu-id="90e66-261">**Aktion**: Sie können den Wert in **Zulassen oder** **Blockieren ändern.**</span><span class="sxs-lookup"><span data-stu-id="90e66-261">**Action**: You can change the value to **Allow** or **Block**.</span></span>

4. <span data-ttu-id="90e66-262">Klicken Sie nach Abschluss des Vorgangs auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="90e66-262">When you're finished, click **Save**.</span></span>

## <a name="use-the-security--compliance-center-to-remove-entries-from-the-tenant-allowblock-list"></a><span data-ttu-id="90e66-263">Verwenden des Security & Compliance Center zum Entfernen von Einträgen aus der Mandantenzu-/-sperrliste</span><span class="sxs-lookup"><span data-stu-id="90e66-263">Use the Security & Compliance Center to remove entries from the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="90e66-264">Wechseln Sie im Security & Compliance Center zu Richtlinien für die **Bedrohungsverwaltung** \>  \> **Mandanten zulassen/blockieren Listen**.</span><span class="sxs-lookup"><span data-stu-id="90e66-264">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="90e66-265">Wählen Sie die Registerkarte aus, die den Typ des Eintrags enthält, den Sie entfernen möchten:</span><span class="sxs-lookup"><span data-stu-id="90e66-265">Select the tab that contains the type of entry that you want to remove:</span></span>
   - <span data-ttu-id="90e66-266">**URLs**</span><span class="sxs-lookup"><span data-stu-id="90e66-266">**URLs**</span></span>
   - <span data-ttu-id="90e66-267">**Files**</span><span class="sxs-lookup"><span data-stu-id="90e66-267">**Files**</span></span>
   - <span data-ttu-id="90e66-268">**Absenderdomänen für die BCL-Umgehung**</span><span class="sxs-lookup"><span data-stu-id="90e66-268">**Sender domains for BCL bypass**</span></span>
   - <span data-ttu-id="90e66-269">**Spoofing**</span><span class="sxs-lookup"><span data-stu-id="90e66-269">**Spoofing**</span></span>

3. <span data-ttu-id="90e66-270">Wählen Sie den Eintrag aus, den Sie entfernen möchten, und klicken Sie dann **auf Löschen** ![ -Symbol ](../../media/87565fbb-5147-4f22-9ed7-1c18ce664392.png) .</span><span class="sxs-lookup"><span data-stu-id="90e66-270">Select the entry that you want to remove, and then click **Delete** ![Delete icon](../../media/87565fbb-5147-4f22-9ed7-1c18ce664392.png).</span></span>

4. <span data-ttu-id="90e66-271">Klicken Sie im angezeigten Warnungsdialogfeld auf **Löschen**.</span><span class="sxs-lookup"><span data-stu-id="90e66-271">In the warning dialog that appears, click **Delete**.</span></span>

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-the-tenant-allowblock-list"></a><span data-ttu-id="90e66-272">Verwenden Exchange Online PowerShell oder eigenständiger EOP PowerShell zum Konfigurieren der Mandanten zulassen/Blockieren-Liste</span><span class="sxs-lookup"><span data-stu-id="90e66-272">Use Exchange Online PowerShell or standalone EOP PowerShell to configure the Tenant Allow/Block List</span></span>

### <a name="use-powershell-to-add-block-file-or-url-entries-to-the-tenant-allowblock-list"></a><span data-ttu-id="90e66-273">Verwenden von PowerShell zum Hinzufügen von Blockdatei- oder URL-Einträgen zur Mandantenzu-/Sperrliste</span><span class="sxs-lookup"><span data-stu-id="90e66-273">Use PowerShell to add block file or URL entries to the Tenant Allow/Block List</span></span>

<span data-ttu-id="90e66-274">Verwenden Sie die folgende Syntax, um Blockdatei- oder #A0 in der Mandanten zulassen/blockieren-Liste hinzuzufügen:</span><span class="sxs-lookup"><span data-stu-id="90e66-274">To add block file or URL entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
New-TenantAllowBlockListItems -ListType <FileHash | Url> -Block -Entries "Value1","Value2",..."ValueN" <-ExpirationDate Date | -NoExpiration> [-Notes <String>]
```

<span data-ttu-id="90e66-275">In diesem Beispiel wird ein Blockdateieintrag für die angegebenen Dateien, die nie abläuft, hinzufügt.</span><span class="sxs-lookup"><span data-stu-id="90e66-275">This example adds a block file entry for the specified files that never expires.</span></span>

```powershell
New-TenantAllowBlockListItem -ListType FileHash -Block -Entries "768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3","2c0a35409ff0873cfa28b70b8224e9aca2362241c1f0ed6f622fef8d4722fd9a" -NoExpiration
```

<span data-ttu-id="90e66-276">In diesem Beispiel wird ein Block-URL-Eintrag für contoso.com und alle Unterdomänen hinzugefügt (z. B. contoso.com, www.contoso.com und xyz.abc.contoso.com).</span><span class="sxs-lookup"><span data-stu-id="90e66-276">This example adds a block URL entry for contoso.com and all subdomains (for example, contoso.com, www.contoso.com, and xyz.abc.contoso.com).</span></span> <span data-ttu-id="90e66-277">Da wir die Parameter ExpirationDate oder NoExpiration nicht verwendet haben, läuft der Eintrag nach 30 Tagen ab.</span><span class="sxs-lookup"><span data-stu-id="90e66-277">Because we didn't use the ExpirationDate or NoExpiration parameters, the entry expires after 30 days.</span></span>

```powershell
New-TenantAllowBlockListItems -ListType Url -Block -Entries ~contoso.com
```

<span data-ttu-id="90e66-278">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [New-TenantAllowBlockListItems](/powershell/module/exchange/new-tenantallowblocklistitems).</span><span class="sxs-lookup"><span data-stu-id="90e66-278">For detailed syntax and parameter information, see [New-TenantAllowBlockListItems](/powershell/module/exchange/new-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-add-allow-or-block-spoofed-sender-entries-to-the-tenant-allowblock-list"></a><span data-ttu-id="90e66-279">Verwenden von PowerShell zum Hinzufügen zulässiger oder blockieren von gefälschten Absendereinträgen zur Mandantenzu-/Sperrliste</span><span class="sxs-lookup"><span data-stu-id="90e66-279">Use PowerShell to add allow or block spoofed sender entries to the Tenant Allow/Block List</span></span>

<span data-ttu-id="90e66-280">Verwenden Sie die folgende Syntax, um spoofierte Absendereinträge in der Mandanten zulassen/blockieren-Liste hinzuzufügen:</span><span class="sxs-lookup"><span data-stu-id="90e66-280">To add spoofed sender entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
New-TenantAllowBlockListSpoofItems -SpoofedUser <Domain | EmailAddress | *> -SendingInfrastructure <Domain | IPAddress/24> -SpoofType <External | Internal> -Action <Allow | Block>
```

<span data-ttu-id="90e66-281">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [New-TenantAllowBlockListSpoofItems](/powershell/module/exchange/new-tenantallowblocklistspoofitems).</span><span class="sxs-lookup"><span data-stu-id="90e66-281">For detailed syntax and parameter information, see [New-TenantAllowBlockListSpoofItems](/powershell/module/exchange/new-tenantallowblocklistspoofitems).</span></span>

### <a name="use-powershell-to-view-block-file-or-url-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="90e66-282">Verwenden von PowerShell zum Anzeigen von Blockdatei- oder URL-Einträgen in der Mandantenzu-/-sperrliste</span><span class="sxs-lookup"><span data-stu-id="90e66-282">Use PowerShell to view block file or URL entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="90e66-283">Verwenden Sie die folgende Syntax, um Blockdatei- oder #A0 in der Mandanten zulassen/blockieren-Liste anzeigen zu können:</span><span class="sxs-lookup"><span data-stu-id="90e66-283">To view block file or URL entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType <FileHash | URL> [-Entry <FileHashValue | URLValue>] [<-ExpirationDate Date | -NoExpiration>]
```

<span data-ttu-id="90e66-284">In diesem Beispiel werden Informationen für den angegebenen Dateihashwert zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="90e66-284">This example returns information for the specified file hash value.</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType FileHash -Entry "9f86d081884c7d659a2feaa0c55ad015a3bf4f1b2b0b822cd15d6c15b0f00a08"
```

<span data-ttu-id="90e66-285">In diesem Beispiel werden alle blockierten URLs zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="90e66-285">This example returns all blocked URLs.</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType Url -Block
```

<span data-ttu-id="90e66-286">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Get-TenantAllowBlockListItems](/powershell/module/exchange/get-tenantallowblocklistitems).</span><span class="sxs-lookup"><span data-stu-id="90e66-286">For detailed syntax and parameter information, see [Get-TenantAllowBlockListItems](/powershell/module/exchange/get-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-view-allow-or-block-spoofed-sender-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="90e66-287">Verwenden von PowerShell zum Anzeigen zulässiger oder blockierter Absendereinträge in der Mandantenzu-/Sperrliste</span><span class="sxs-lookup"><span data-stu-id="90e66-287">Use PowerShell to view allow or block spoofed sender entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="90e66-288">Verwenden Sie die folgende Syntax, um spoofierte Absendereinträge in der Mandantenzu-/Sperrliste anzeigen zu können:</span><span class="sxs-lookup"><span data-stu-id="90e66-288">To view spoofed sender entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Get-TenantAllowBlockListSpoofItems [-Action <Allow | Block>] [-SpoofType <External | Internal>
```

<span data-ttu-id="90e66-289">In diesem Beispiel werden alle spoofierten Absendereinträge in der Mandanten zulassen/blockieren-Liste zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="90e66-289">This example returns all spoofed sender entries in the Tenant Allow/Block List.</span></span>

```powershell
Get-TenantAllowBlockListSpoofItems
```

<span data-ttu-id="90e66-290">In diesem Beispiel werden alle zulässigen spoofierten Absendereinträge zurückgegeben, die intern sind.</span><span class="sxs-lookup"><span data-stu-id="90e66-290">This example returns all allow spoofed sender entries that are internal.</span></span>

```powershell
Get-TenantAllowBlockListSpoofItems -Action Allow -SpoofType Internal
```

<span data-ttu-id="90e66-291">In diesem Beispiel werden alle blockierten spoofierten Absendereinträge zurückgegeben, die extern sind.</span><span class="sxs-lookup"><span data-stu-id="90e66-291">This example returns all blocked spoofed sender entries that are external.</span></span>

```powershell
Get-TenantAllowBlockListSpoofItems -Action Block -SpoofType External
```

<span data-ttu-id="90e66-292">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Get-TenantAllowBlockListSpoofItems](/powershell/module/exchange/get-tenantallowblocklistspoofitems).</span><span class="sxs-lookup"><span data-stu-id="90e66-292">For detailed syntax and parameter information, see [Get-TenantAllowBlockListSpoofItems](/powershell/module/exchange/get-tenantallowblocklistspoofitems).</span></span>

### <a name="use-powershell-to-modify-block-file-and-url-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="90e66-293">Verwenden von PowerShell zum Ändern von Blockdatei- und URL-Einträgen in der Mandantenzu-/Sperrliste</span><span class="sxs-lookup"><span data-stu-id="90e66-293">Use PowerShell to modify block file and URL entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="90e66-294">Verwenden Sie die folgende Syntax, um Blockdatei- und #A0 in der Mandanten-Allow/Block List zu ändern:</span><span class="sxs-lookup"><span data-stu-id="90e66-294">To modify block file and URL entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Set-TenantAllowBlockListItems -ListType <FileHash | Url> -Ids <"Id1","Id2",..."IdN"> [<-ExpirationDate Date | -NoExpiration>] [-Notes <String>]
```

<span data-ttu-id="90e66-295">In diesem Beispiel wird das Ablaufdatum des angegebenen Block-URL-Eintrags geändert.</span><span class="sxs-lookup"><span data-stu-id="90e66-295">This example changes the expiration date of the specified block URL entry.</span></span>

```powershell
Set-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSRAAAA" -ExpirationDate "5/30/2020"
```

<span data-ttu-id="90e66-296">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Set-TenantAllowBlockListItems](/powershell/module/exchange/set-tenantallowblocklistitems).</span><span class="sxs-lookup"><span data-stu-id="90e66-296">For detailed syntax and parameter information, see [Set-TenantAllowBlockListItems](/powershell/module/exchange/set-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-modify-allow-or-block-spoofed-sender-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="90e66-297">Verwenden von PowerShell zum Ändern zulässiger oder blockierter Absendereinträge in der Mandantenzu-/Sperrliste</span><span class="sxs-lookup"><span data-stu-id="90e66-297">Use PowerShell to modify allow or block spoofed sender entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="90e66-298">Verwenden Sie die folgende Syntax, um gefälschte Absendereinträge in der Mandanten zulassen/blockieren-Liste zu ändern oder zu blockieren:</span><span class="sxs-lookup"><span data-stu-id="90e66-298">To modify allow or block spoofed sender entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Set-TenantAllowBlockListSpoofItems -Ids <"Id1","Id2",..."IdN"> -Action <Allow | Block>
```

<span data-ttu-id="90e66-299">In diesem Beispiel wird der Spoofing-Absendereintrag von "Blockieren" geändert.</span><span class="sxs-lookup"><span data-stu-id="90e66-299">This example changes spoofed sender entry from allow to block.</span></span>

```powershell
Set-TenantAllowBlockListItems -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSRAAAA" -Action Block
```

<span data-ttu-id="90e66-300">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Set-TenantAllowBlockListSpoofItems](/powershell/module/exchange/set-tenantallowblocklistspoofitems).</span><span class="sxs-lookup"><span data-stu-id="90e66-300">For detailed syntax and parameter information, see [Set-TenantAllowBlockListSpoofItems](/powershell/module/exchange/set-tenantallowblocklistspoofitems).</span></span>

### <a name="use-powershell-to-remove-url-or-file-entries-from-the-tenant-allowblock-list"></a><span data-ttu-id="90e66-301">Verwenden von PowerShell zum Entfernen von URL- oder Dateieinträgen aus der Liste mandanten zulassen/blockieren</span><span class="sxs-lookup"><span data-stu-id="90e66-301">Use PowerShell to remove URL or file entries from the Tenant Allow/Block List</span></span>

<span data-ttu-id="90e66-302">Verwenden Sie die folgende Syntax, um Datei- und URL-Einträge aus der Mandantenzu-/Sperrliste zu entfernen:</span><span class="sxs-lookup"><span data-stu-id="90e66-302">To remove file and URL entries from the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Remove-TenantAllowBlockListItems -ListType <FileHash | Url> -Ids <"Id1","Id2",..."IdN">
```

<span data-ttu-id="90e66-303">In diesem Beispiel wird der angegebene Block-URL-Eintrag aus der Mandanten-Allow/Block List entfernt.</span><span class="sxs-lookup"><span data-stu-id="90e66-303">This example removes the specified block URL entry from the Tenant Allow/Block List.</span></span>

```powershell
Remove-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSPAAAA0"
```

<span data-ttu-id="90e66-304">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Remove-TenantAllowBlockListItems](/powershell/module/exchange/remove-tenantallowblocklistitems).</span><span class="sxs-lookup"><span data-stu-id="90e66-304">For detailed syntax and parameter information, see [Remove-TenantAllowBlockListItems](/powershell/module/exchange/remove-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-remove-allow-or-block-spoofed-sender-entries-from-the-tenant-allowblock-list"></a><span data-ttu-id="90e66-305">Verwenden von PowerShell zum Entfernen zulässiger oder blockierter Gefälschter Absendereinträge aus der Mandantenzu-/Sperrliste</span><span class="sxs-lookup"><span data-stu-id="90e66-305">Use PowerShell to remove allow or block spoofed sender entries from the Tenant Allow/Block List</span></span>

<span data-ttu-id="90e66-306">Verwenden Sie die folgende Syntax, um Spoof-Absendereinträge aus der Mandanten zulassen/blockieren-Liste zu entfernen oder zu blockieren:</span><span class="sxs-lookup"><span data-stu-id="90e66-306">To remove allow or block spoof sender entries from the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Remove-TenantAllowBlockListSpoofItems -Ids <"Id1","Id2",..."IdN">
```

<span data-ttu-id="90e66-307">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Remove-TenantAllowBlockListSpoofItems](/powershell/module/exchange/remove-tenantallowblocklistspoofitems).</span><span class="sxs-lookup"><span data-stu-id="90e66-307">For detailed syntax and parameter information, see [Remove-TenantAllowBlockListSpoofItems](/powershell/module/exchange/remove-tenantallowblocklistspoofitems).</span></span>

## <a name="url-syntax-for-the-tenant-allowblock-list"></a><span data-ttu-id="90e66-308">#A0 für die Mandanten-Allow/Block List</span><span class="sxs-lookup"><span data-stu-id="90e66-308">URL syntax for the Tenant Allow/Block List</span></span>

- <span data-ttu-id="90e66-309">IP4v- und IPv6-Adressen sind zulässig, TCP/UDP-Ports jedoch nicht.</span><span class="sxs-lookup"><span data-stu-id="90e66-309">IP4v and IPv6 addresses are allowed, but TCP/UDP ports are not.</span></span>

- <span data-ttu-id="90e66-310">Dateinamenerweiterungen sind nicht zulässig (z. B. test.pdf).</span><span class="sxs-lookup"><span data-stu-id="90e66-310">Filename extensions are not allowed (for example, test.pdf).</span></span>

- <span data-ttu-id="90e66-311">Unicode wird nicht unterstützt, Punycode jedoch.</span><span class="sxs-lookup"><span data-stu-id="90e66-311">Unicode is not supported, but Punycode is.</span></span>

- <span data-ttu-id="90e66-312">Hostnamen sind zulässig, wenn alle folgenden Anweisungen zutreffen:</span><span class="sxs-lookup"><span data-stu-id="90e66-312">Hostnames are allowed if all of the following statements are true:</span></span>
  - <span data-ttu-id="90e66-313">Der Hostname enthält einen Zeitraum.</span><span class="sxs-lookup"><span data-stu-id="90e66-313">The hostname contains a period.</span></span>
  - <span data-ttu-id="90e66-314">Es gibt mindestens ein Zeichen links vom Zeitraum.</span><span class="sxs-lookup"><span data-stu-id="90e66-314">There is at least one character to the left of the period.</span></span>
  - <span data-ttu-id="90e66-315">Rechts neben dem Zeitraum befinden sich mindestens zwei Zeichen.</span><span class="sxs-lookup"><span data-stu-id="90e66-315">There are at least two characters to the right of the period.</span></span>

  <span data-ttu-id="90e66-316">Beispielsweise ist `t.co` zulässig oder nicht `.com` `contoso.` zulässig.</span><span class="sxs-lookup"><span data-stu-id="90e66-316">For example, `t.co` is allowed; `.com` or `contoso.` are not allowed.</span></span>

- <span data-ttu-id="90e66-317">Unterpfade werden nicht impliziert.</span><span class="sxs-lookup"><span data-stu-id="90e66-317">Subpaths are not implied.</span></span>

  <span data-ttu-id="90e66-318">Enthält z. `contoso.com` B. nicht `contoso.com/a` .</span><span class="sxs-lookup"><span data-stu-id="90e66-318">For example, `contoso.com` does not include `contoso.com/a`.</span></span>

- <span data-ttu-id="90e66-319">Platzhalter (\*) sind in den folgenden Szenarien zulässig:</span><span class="sxs-lookup"><span data-stu-id="90e66-319">Wildcards (\*) are allowed in the following scenarios:</span></span>

  - <span data-ttu-id="90e66-320">Auf einen linken Platzhalter muss ein Zeitraum folgen, um eine Unterdomäne anzugeben.</span><span class="sxs-lookup"><span data-stu-id="90e66-320">A left wildcard must be followed by a period to specify a subdomain.</span></span>

    <span data-ttu-id="90e66-321">Ist beispielsweise `*.contoso.com` zulässig; `*contoso.com` ist nicht zulässig.</span><span class="sxs-lookup"><span data-stu-id="90e66-321">For example, `*.contoso.com` is allowed; `*contoso.com` is not allowed.</span></span>

  - <span data-ttu-id="90e66-322">Ein rechter Platzhalter muss einem Schrägstrich (/) folgen, um einen Pfad anzugeben.</span><span class="sxs-lookup"><span data-stu-id="90e66-322">A right wildcard must follow a forward slash (/) to specify a path.</span></span>

    <span data-ttu-id="90e66-323">Beispielsweise ist `contoso.com/*` zulässig oder nicht `contoso.com*` `contoso.com/ab*` zulässig.</span><span class="sxs-lookup"><span data-stu-id="90e66-323">For example, `contoso.com/*` is allowed; `contoso.com*` or `contoso.com/ab*` are not allowed.</span></span>

  - <span data-ttu-id="90e66-324">Alle Unterpfade werden nicht durch einen rechten Platzhalter impliziert.</span><span class="sxs-lookup"><span data-stu-id="90e66-324">All subpaths are not implied by a right wildcard.</span></span>

    <span data-ttu-id="90e66-325">Enthält z. `contoso.com/*` B. nicht `contoso.com/a` .</span><span class="sxs-lookup"><span data-stu-id="90e66-325">For example, `contoso.com/*` does not include `contoso.com/a`.</span></span>

  - <span data-ttu-id="90e66-326">`*.com*` ist ungültig (keine auflösbare Domäne, und der rechte Platzhalter folgt keinem Schrägstrich).</span><span class="sxs-lookup"><span data-stu-id="90e66-326">`*.com*` is invalid (not a resolvable domain and the right wildcard does not follow a forward slash).</span></span>

  - <span data-ttu-id="90e66-327">Platzhalter sind in IP-Adressen nicht zulässig.</span><span class="sxs-lookup"><span data-stu-id="90e66-327">Wildcards are not allowed in IP addresses.</span></span>

- <span data-ttu-id="90e66-328">Das Tildezeichen (~) ist in den folgenden Szenarien verfügbar:</span><span class="sxs-lookup"><span data-stu-id="90e66-328">The tilde (~) character is available in the following scenarios:</span></span>

  - <span data-ttu-id="90e66-329">Eine linke Tilde impliziert eine Domäne und alle Unterdomänen.</span><span class="sxs-lookup"><span data-stu-id="90e66-329">A left tilde implies a domain and all subdomains.</span></span>

    <span data-ttu-id="90e66-330">Enthält `~contoso.com` z. `contoso.com` B. und `*.contoso.com` .</span><span class="sxs-lookup"><span data-stu-id="90e66-330">For example `~contoso.com` includes `contoso.com` and `*.contoso.com`.</span></span>

- <span data-ttu-id="90e66-331">URL-Einträge, die Protokolle (z. B. , oder ) enthalten, werden fehlschlagen, da `http://` URL-Einträge für alle Protokolle `https://` `ftp://` gelten.</span><span class="sxs-lookup"><span data-stu-id="90e66-331">URL entries that contain protocols (for example, `http://`, `https://`, or `ftp://`) will fail, because URL entries apply to all protocols.</span></span>

- <span data-ttu-id="90e66-332">Ein Benutzername oder Kennwort wird nicht unterstützt oder ist nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="90e66-332">A username or password aren't supported or required.</span></span>

- <span data-ttu-id="90e66-333">Anführungszeichen (' oder ") sind ungültige Zeichen.</span><span class="sxs-lookup"><span data-stu-id="90e66-333">Quotes (' or ") are invalid characters.</span></span>

- <span data-ttu-id="90e66-334">Eine URL sollte nach Möglichkeit alle Umleitungen enthalten.</span><span class="sxs-lookup"><span data-stu-id="90e66-334">A URL should include all redirects where possible.</span></span>

### <a name="url-entry-scenarios"></a><span data-ttu-id="90e66-335">Szenarien für den URL-Eintrag</span><span class="sxs-lookup"><span data-stu-id="90e66-335">URL entry scenarios</span></span>

<span data-ttu-id="90e66-336">Gültige URL-Einträge und deren Ergebnisse werden in den folgenden Abschnitten beschrieben.</span><span class="sxs-lookup"><span data-stu-id="90e66-336">Valid URL entries and their results are described in the following sections.</span></span>

#### <a name="scenario-no-wildcards"></a><span data-ttu-id="90e66-337">Szenario: Keine Platzhalter</span><span class="sxs-lookup"><span data-stu-id="90e66-337">Scenario: No wildcards</span></span>

<span data-ttu-id="90e66-338">**Eintrag**: `contoso.com`</span><span class="sxs-lookup"><span data-stu-id="90e66-338">**Entry**: `contoso.com`</span></span>

- <span data-ttu-id="90e66-339">**Übereinstimmung zulassen**: contoso.com</span><span class="sxs-lookup"><span data-stu-id="90e66-339">**Allow match**: contoso.com</span></span>

- <span data-ttu-id="90e66-340">**Nicht übereinstimmend zulassen:**</span><span class="sxs-lookup"><span data-stu-id="90e66-340">**Allow not matched**:</span></span>

  - <span data-ttu-id="90e66-341">abc-contoso.com</span><span class="sxs-lookup"><span data-stu-id="90e66-341">abc-contoso.com</span></span>
  - <span data-ttu-id="90e66-342">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="90e66-342">contoso.com/a</span></span>
  - <span data-ttu-id="90e66-343">payroll.contoso.com</span><span class="sxs-lookup"><span data-stu-id="90e66-343">payroll.contoso.com</span></span>
  - <span data-ttu-id="90e66-344">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="90e66-344">test.com/contoso.com</span></span>
  - <span data-ttu-id="90e66-345">test.com/q=contoso.com</span><span class="sxs-lookup"><span data-stu-id="90e66-345">test.com/q=contoso.com</span></span>
  - <span data-ttu-id="90e66-346">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="90e66-346">www.contoso.com</span></span>
  - <span data-ttu-id="90e66-347">www.contoso.com/q=a@contoso.com</span><span class="sxs-lookup"><span data-stu-id="90e66-347">www.contoso.com/q=a@contoso.com</span></span>

- <span data-ttu-id="90e66-348">**Übereinstimmung blockieren**:</span><span class="sxs-lookup"><span data-stu-id="90e66-348">**Block match**:</span></span>

  - <span data-ttu-id="90e66-349">contoso.com</span><span class="sxs-lookup"><span data-stu-id="90e66-349">contoso.com</span></span>
  - <span data-ttu-id="90e66-350">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="90e66-350">contoso.com/a</span></span>
  - <span data-ttu-id="90e66-351">payroll.contoso.com</span><span class="sxs-lookup"><span data-stu-id="90e66-351">payroll.contoso.com</span></span>
  - <span data-ttu-id="90e66-352">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="90e66-352">test.com/contoso.com</span></span>
  - <span data-ttu-id="90e66-353">test.com/q=contoso.com</span><span class="sxs-lookup"><span data-stu-id="90e66-353">test.com/q=contoso.com</span></span>
  - <span data-ttu-id="90e66-354">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="90e66-354">www.contoso.com</span></span>
  - <span data-ttu-id="90e66-355">www.contoso.com/q=a@contoso.com</span><span class="sxs-lookup"><span data-stu-id="90e66-355">www.contoso.com/q=a@contoso.com</span></span>

- <span data-ttu-id="90e66-356">**Block nicht übereinstimmend**: abc-contoso.com</span><span class="sxs-lookup"><span data-stu-id="90e66-356">**Block not matched**: abc-contoso.com</span></span>

#### <a name="scenario-left-wildcard-subdomain"></a><span data-ttu-id="90e66-357">Szenario: Linker Platzhalter (Unterdomäne)</span><span class="sxs-lookup"><span data-stu-id="90e66-357">Scenario: Left wildcard (subdomain)</span></span>

<span data-ttu-id="90e66-358">**Eintrag**: `*.contoso.com`</span><span class="sxs-lookup"><span data-stu-id="90e66-358">**Entry**: `*.contoso.com`</span></span>

- <span data-ttu-id="90e66-359">**Übereinstimmung zulassen** und **Übereinstimmung blockieren**:</span><span class="sxs-lookup"><span data-stu-id="90e66-359">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="90e66-360">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="90e66-360">www.contoso.com</span></span>
  - <span data-ttu-id="90e66-361">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="90e66-361">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="90e66-362">**Allow not matched** and **Block not matched**:</span><span class="sxs-lookup"><span data-stu-id="90e66-362">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="90e66-363">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="90e66-363">123contoso.com</span></span>
  - <span data-ttu-id="90e66-364">contoso.com</span><span class="sxs-lookup"><span data-stu-id="90e66-364">contoso.com</span></span>
  - <span data-ttu-id="90e66-365">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="90e66-365">test.com/contoso.com</span></span>
  - <span data-ttu-id="90e66-366">www.contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="90e66-366">www.contoso.com/abc</span></span>

#### <a name="scenario-right-wildcard-at-top-of-path"></a><span data-ttu-id="90e66-367">Szenario: Rechter Platzhalter am oberen Rand des Pfads</span><span class="sxs-lookup"><span data-stu-id="90e66-367">Scenario: Right wildcard at top of path</span></span>

<span data-ttu-id="90e66-368">**Eintrag**: `contoso.com/a/*`</span><span class="sxs-lookup"><span data-stu-id="90e66-368">**Entry**: `contoso.com/a/*`</span></span>

- <span data-ttu-id="90e66-369">**Übereinstimmung zulassen** und **Übereinstimmung blockieren**:</span><span class="sxs-lookup"><span data-stu-id="90e66-369">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="90e66-370">contoso.com/a/b</span><span class="sxs-lookup"><span data-stu-id="90e66-370">contoso.com/a/b</span></span>
  - <span data-ttu-id="90e66-371">contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="90e66-371">contoso.com/a/b/c</span></span>
  - <span data-ttu-id="90e66-372">contoso.com/a/?q=joe@t.com</span><span class="sxs-lookup"><span data-stu-id="90e66-372">contoso.com/a/?q=joe@t.com</span></span>

- <span data-ttu-id="90e66-373">**Allow not matched** and **Block not matched**:</span><span class="sxs-lookup"><span data-stu-id="90e66-373">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="90e66-374">contoso.com</span><span class="sxs-lookup"><span data-stu-id="90e66-374">contoso.com</span></span>
  - <span data-ttu-id="90e66-375">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="90e66-375">contoso.com/a</span></span>
  - <span data-ttu-id="90e66-376">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="90e66-376">www.contoso.com</span></span>
  - <span data-ttu-id="90e66-377">www.contoso.com/q=a@contoso.com</span><span class="sxs-lookup"><span data-stu-id="90e66-377">www.contoso.com/q=a@contoso.com</span></span>

#### <a name="scenario-left-tilde"></a><span data-ttu-id="90e66-378">Szenario: Left tilde</span><span class="sxs-lookup"><span data-stu-id="90e66-378">Scenario: Left tilde</span></span>

<span data-ttu-id="90e66-379">**Eintrag**: `~contoso.com`</span><span class="sxs-lookup"><span data-stu-id="90e66-379">**Entry**: `~contoso.com`</span></span>

- <span data-ttu-id="90e66-380">**Übereinstimmung zulassen** und **Übereinstimmung blockieren**:</span><span class="sxs-lookup"><span data-stu-id="90e66-380">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="90e66-381">contoso.com</span><span class="sxs-lookup"><span data-stu-id="90e66-381">contoso.com</span></span>
  - <span data-ttu-id="90e66-382">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="90e66-382">www.contoso.com</span></span>
  - <span data-ttu-id="90e66-383">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="90e66-383">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="90e66-384">**Allow not matched** and **Block not matched**:</span><span class="sxs-lookup"><span data-stu-id="90e66-384">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="90e66-385">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="90e66-385">123contoso.com</span></span>
  - <span data-ttu-id="90e66-386">contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="90e66-386">contoso.com/abc</span></span>
  - <span data-ttu-id="90e66-387">www.contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="90e66-387">www.contoso.com/abc</span></span>

#### <a name="scenario-right-wildcard-suffix"></a><span data-ttu-id="90e66-388">Szenario: Rechtes Platzhaltersuffix</span><span class="sxs-lookup"><span data-stu-id="90e66-388">Scenario: Right wildcard suffix</span></span>

<span data-ttu-id="90e66-389">**Eintrag**: `contoso.com/*`</span><span class="sxs-lookup"><span data-stu-id="90e66-389">**Entry**: `contoso.com/*`</span></span>

- <span data-ttu-id="90e66-390">**Übereinstimmung zulassen** und **Übereinstimmung blockieren**:</span><span class="sxs-lookup"><span data-stu-id="90e66-390">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="90e66-391">contoso.com/?q=whatever@fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="90e66-391">contoso.com/?q=whatever@fabrikam.com</span></span>
  - <span data-ttu-id="90e66-392">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="90e66-392">contoso.com/a</span></span>
  - <span data-ttu-id="90e66-393">contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="90e66-393">contoso.com/a/b/c</span></span>
  - <span data-ttu-id="90e66-394">contoso.com/ab</span><span class="sxs-lookup"><span data-stu-id="90e66-394">contoso.com/ab</span></span>
  - <span data-ttu-id="90e66-395">contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="90e66-395">contoso.com/b</span></span>
  - <span data-ttu-id="90e66-396">contoso.com/b/a/c</span><span class="sxs-lookup"><span data-stu-id="90e66-396">contoso.com/b/a/c</span></span>
  - <span data-ttu-id="90e66-397">contoso.com/ba</span><span class="sxs-lookup"><span data-stu-id="90e66-397">contoso.com/ba</span></span>

- <span data-ttu-id="90e66-398">**Nicht übereinstimmend zulassen und** **Block nicht** übereinstimmen: contoso.com</span><span class="sxs-lookup"><span data-stu-id="90e66-398">**Allow not matched** and **Block not matched**: contoso.com</span></span>

#### <a name="scenario-left-wildcard-subdomain-and-right-wildcard-suffix"></a><span data-ttu-id="90e66-399">Szenario: Linke Platzhalterunterdomäne und rechtes Platzhaltersuffix</span><span class="sxs-lookup"><span data-stu-id="90e66-399">Scenario: Left wildcard subdomain and right wildcard suffix</span></span>

<span data-ttu-id="90e66-400">**Eintrag**: `*.contoso.com/*`</span><span class="sxs-lookup"><span data-stu-id="90e66-400">**Entry**: `*.contoso.com/*`</span></span>

- <span data-ttu-id="90e66-401">**Übereinstimmung zulassen** und **Übereinstimmung blockieren**:</span><span class="sxs-lookup"><span data-stu-id="90e66-401">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="90e66-402">abc.contoso.com/ab</span><span class="sxs-lookup"><span data-stu-id="90e66-402">abc.contoso.com/ab</span></span>
  - <span data-ttu-id="90e66-403">abc.xyz.contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="90e66-403">abc.xyz.contoso.com/a/b/c</span></span>
  - <span data-ttu-id="90e66-404">www.contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="90e66-404">www.contoso.com/a</span></span>
  - <span data-ttu-id="90e66-405">www.contoso.com/b/a/c</span><span class="sxs-lookup"><span data-stu-id="90e66-405">www.contoso.com/b/a/c</span></span>
  - <span data-ttu-id="90e66-406">xyz.contoso.com/ba</span><span class="sxs-lookup"><span data-stu-id="90e66-406">xyz.contoso.com/ba</span></span>

- <span data-ttu-id="90e66-407">**Nicht übereinstimmend zulassen und** **Block nicht** übereinstimmen : contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="90e66-407">**Allow not matched** and **Block not matched**: contoso.com/b</span></span>

#### <a name="scenario-left-and-right-tilde"></a><span data-ttu-id="90e66-408">Szenario: Linker und rechter Tilde</span><span class="sxs-lookup"><span data-stu-id="90e66-408">Scenario: Left and right tilde</span></span>

<span data-ttu-id="90e66-409">**Eintrag**: `~contoso.com~`</span><span class="sxs-lookup"><span data-stu-id="90e66-409">**Entry**: `~contoso.com~`</span></span>

- <span data-ttu-id="90e66-410">**Übereinstimmung zulassen** und **Übereinstimmung blockieren**:</span><span class="sxs-lookup"><span data-stu-id="90e66-410">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="90e66-411">contoso.com</span><span class="sxs-lookup"><span data-stu-id="90e66-411">contoso.com</span></span>
  - <span data-ttu-id="90e66-412">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="90e66-412">contoso.com/a</span></span>
  - <span data-ttu-id="90e66-413">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="90e66-413">www.contoso.com</span></span>
  - <span data-ttu-id="90e66-414">www.contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="90e66-414">www.contoso.com/b</span></span>
  - <span data-ttu-id="90e66-415">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="90e66-415">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="90e66-416">**Allow not matched** and **Block not matched**:</span><span class="sxs-lookup"><span data-stu-id="90e66-416">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="90e66-417">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="90e66-417">123contoso.com</span></span>
  - <span data-ttu-id="90e66-418">contoso.org</span><span class="sxs-lookup"><span data-stu-id="90e66-418">contoso.org</span></span>

#### <a name="scenario-ip-address"></a><span data-ttu-id="90e66-419">Szenario: IP-Adresse</span><span class="sxs-lookup"><span data-stu-id="90e66-419">Scenario: IP address</span></span>

<span data-ttu-id="90e66-420">**Eintrag**: `1.2.3.4`</span><span class="sxs-lookup"><span data-stu-id="90e66-420">**Entry**: `1.2.3.4`</span></span>

- <span data-ttu-id="90e66-421">**Übereinstimmung zulassen** und **Übereinstimmung blockieren**: 1.2.3.4</span><span class="sxs-lookup"><span data-stu-id="90e66-421">**Allow match** and **Block match**: 1.2.3.4</span></span>

- <span data-ttu-id="90e66-422">**Allow not matched** and **Block not matched**:</span><span class="sxs-lookup"><span data-stu-id="90e66-422">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="90e66-423">1.2.3.4/a</span><span class="sxs-lookup"><span data-stu-id="90e66-423">1.2.3.4/a</span></span>
  - <span data-ttu-id="90e66-424">11.2.3.4/a</span><span class="sxs-lookup"><span data-stu-id="90e66-424">11.2.3.4/a</span></span>

#### <a name="ip-address-with-right-wildcard"></a><span data-ttu-id="90e66-425">IP-Adresse mit rechtem Platzhalter</span><span class="sxs-lookup"><span data-stu-id="90e66-425">IP address with right wildcard</span></span>

<span data-ttu-id="90e66-426">**Eintrag**: `1.2.3.4/*`</span><span class="sxs-lookup"><span data-stu-id="90e66-426">**Entry**: `1.2.3.4/*`</span></span>

- <span data-ttu-id="90e66-427">**Übereinstimmung zulassen** und **Übereinstimmung blockieren**:</span><span class="sxs-lookup"><span data-stu-id="90e66-427">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="90e66-428">1.2.3.4/b</span><span class="sxs-lookup"><span data-stu-id="90e66-428">1.2.3.4/b</span></span>
  - <span data-ttu-id="90e66-429">1.2.3.4/baaaa</span><span class="sxs-lookup"><span data-stu-id="90e66-429">1.2.3.4/baaaa</span></span>

### <a name="examples-of-invalid-entries"></a><span data-ttu-id="90e66-430">Beispiele für ungültige Einträge</span><span class="sxs-lookup"><span data-stu-id="90e66-430">Examples of invalid entries</span></span>

<span data-ttu-id="90e66-431">Die folgenden Einträge sind ungültig:</span><span class="sxs-lookup"><span data-stu-id="90e66-431">The following entries are invalid:</span></span>

- <span data-ttu-id="90e66-432">**Fehlende oder ungültige Domänenwerte**:</span><span class="sxs-lookup"><span data-stu-id="90e66-432">**Missing or invalid domain values**:</span></span>

  - <span data-ttu-id="90e66-433">contoso</span><span class="sxs-lookup"><span data-stu-id="90e66-433">contoso</span></span>
  - <span data-ttu-id="90e66-434">\*.contoso.\*</span><span class="sxs-lookup"><span data-stu-id="90e66-434">\*.contoso.\*</span></span>
  - <span data-ttu-id="90e66-435">\*.com</span><span class="sxs-lookup"><span data-stu-id="90e66-435">\*.com</span></span>
  - <span data-ttu-id="90e66-436">\*.PDF</span><span class="sxs-lookup"><span data-stu-id="90e66-436">\*.pdf</span></span>

- <span data-ttu-id="90e66-437">**Platzhalter für Text oder ohne Abstandszeichen**:</span><span class="sxs-lookup"><span data-stu-id="90e66-437">**Wildcard on text or without spacing characters**:</span></span>

  - <span data-ttu-id="90e66-438">\*contoso.com</span><span class="sxs-lookup"><span data-stu-id="90e66-438">\*contoso.com</span></span>
  - <span data-ttu-id="90e66-439">contoso.com\*</span><span class="sxs-lookup"><span data-stu-id="90e66-439">contoso.com\*</span></span>
  - <span data-ttu-id="90e66-440">\*1.2.3.4</span><span class="sxs-lookup"><span data-stu-id="90e66-440">\*1.2.3.4</span></span>
  - <span data-ttu-id="90e66-441">1.2.3.4\*</span><span class="sxs-lookup"><span data-stu-id="90e66-441">1.2.3.4\*</span></span>
  - <span data-ttu-id="90e66-442">contoso.com/a\*</span><span class="sxs-lookup"><span data-stu-id="90e66-442">contoso.com/a\*</span></span>
  - <span data-ttu-id="90e66-443">contoso.com/ab\*</span><span class="sxs-lookup"><span data-stu-id="90e66-443">contoso.com/ab\*</span></span>

- <span data-ttu-id="90e66-444">**IP-Adressen mit Ports**:</span><span class="sxs-lookup"><span data-stu-id="90e66-444">**IP addresses with ports**:</span></span>

  - <span data-ttu-id="90e66-445">contoso.com:443</span><span class="sxs-lookup"><span data-stu-id="90e66-445">contoso.com:443</span></span>
  - <span data-ttu-id="90e66-446">abc.contoso.com:25</span><span class="sxs-lookup"><span data-stu-id="90e66-446">abc.contoso.com:25</span></span>

- <span data-ttu-id="90e66-447">**Nicht beschreibende Platzhalter**:</span><span class="sxs-lookup"><span data-stu-id="90e66-447">**Non-descriptive wildcards**:</span></span>

  - \*
  - <span data-ttu-id="90e66-448">\*.\*</span><span class="sxs-lookup"><span data-stu-id="90e66-448">\*.\*</span></span>

- <span data-ttu-id="90e66-449">**Mittlere Platzhalter**:</span><span class="sxs-lookup"><span data-stu-id="90e66-449">**Middle wildcards**:</span></span>

  - <span data-ttu-id="90e66-450">conto \* so.com</span><span class="sxs-lookup"><span data-stu-id="90e66-450">conto\*so.com</span></span>
  - <span data-ttu-id="90e66-451">conto~so.com</span><span class="sxs-lookup"><span data-stu-id="90e66-451">conto~so.com</span></span>

- <span data-ttu-id="90e66-452">**Doppelte Platzhalter**</span><span class="sxs-lookup"><span data-stu-id="90e66-452">**Double wildcards**</span></span>

  - <span data-ttu-id="90e66-453">contoso.com/\*\*</span><span class="sxs-lookup"><span data-stu-id="90e66-453">contoso.com/\*\*</span></span>
  - <span data-ttu-id="90e66-454">contoso.com/\*/\*</span><span class="sxs-lookup"><span data-stu-id="90e66-454">contoso.com/\*/\*</span></span>

## <a name="domain-pair-syntax-for-spoofed-sender-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="90e66-455">Domänenpaarsyntax für spoofierte Absendereinträge in der Mandantenzu-/-sperrliste</span><span class="sxs-lookup"><span data-stu-id="90e66-455">Domain pair syntax for spoofed sender entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="90e66-456">Ein Domänenpaar für einen gefälschten Absender in der Mandanten-Allow/Block List verwendet die folgende Syntax: `<Spoofed user>, <Sending infrastructure>` .</span><span class="sxs-lookup"><span data-stu-id="90e66-456">A domain pair for a spoofed sender in the Tenant Allow/Block List uses the following syntax: `<Spoofed user>, <Sending infrastructure>`.</span></span>

- <span data-ttu-id="90e66-457">**Spoofed user**: Dieser Wert umfasst die E-Mail-Adresse des spoofierten Benutzers, der im Feld **Von** in E-Mail-Clients angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="90e66-457">**Spoofed user**: This value involves the email address of the spoofed user that's displayed in the **From** box in email clients.</span></span> <span data-ttu-id="90e66-458">Diese Adresse wird auch als Adresse `5322.From` bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="90e66-458">This address is also known as the `5322.From` address.</span></span> <span data-ttu-id="90e66-459">Gültige Werte sind:</span><span class="sxs-lookup"><span data-stu-id="90e66-459">Valid values include:</span></span>
  - <span data-ttu-id="90e66-460">Eine einzelne E-Mail-Adresse (z. B. chris@contoso.com).</span><span class="sxs-lookup"><span data-stu-id="90e66-460">An individual email address (for example, chris@contoso.com).</span></span>
  - <span data-ttu-id="90e66-461">Eine E-Mail-Domäne (z. B. contoso.com).</span><span class="sxs-lookup"><span data-stu-id="90e66-461">An email domain (for example, contoso.com).</span></span>
  - <span data-ttu-id="90e66-462">Das Platzhalterzeichen (z. B. \* ).</span><span class="sxs-lookup"><span data-stu-id="90e66-462">The wildcard character (for example, \*).</span></span>

- <span data-ttu-id="90e66-463">**Sendende Infrastruktur:** Dieser Wert gibt die Quelle von Nachrichten des spoofierten Benutzers an.</span><span class="sxs-lookup"><span data-stu-id="90e66-463">**Sending infrastructure**: This value indicates the source of messages from the spoofed user.</span></span> <span data-ttu-id="90e66-464">Gültige Werte sind:</span><span class="sxs-lookup"><span data-stu-id="90e66-464">Valid values include:</span></span>
  - <span data-ttu-id="90e66-465">Die Domäne in einer Reverse-DNS-Suche (PTR-Eintrag) der IP-Adresse des Quell-E-Mail-Servers (z. B. fabrikam.com).</span><span class="sxs-lookup"><span data-stu-id="90e66-465">The domain found in a reverse DNS lookup (PTR record) of the source email server's IP address (for example, fabrikam.com).</span></span>
  - <span data-ttu-id="90e66-466">Wenn die Quell-IP-Adresse keinen PTR-Eintrag enthält, wird die sendende Infrastruktur als \<source IP\> /24 identifiziert (z. B. 192.168.100.100/24).</span><span class="sxs-lookup"><span data-stu-id="90e66-466">If the source IP address has no PTR record, then the sending infrastructure is identified as \<source IP\>/24 (for example, 192.168.100.100/24).</span></span>

<span data-ttu-id="90e66-467">Im Folgenden finden Sie einige Beispiele für gültige Domänenpaare zum Identifizieren gefälschter Absender:</span><span class="sxs-lookup"><span data-stu-id="90e66-467">Here are some examples of valid domain pairs to identify spoofed senders:</span></span>

- `contoso.com, 192.168.100.100/24`
- `chris@contoso.com, fabrikam.com`
- `*, contoso.net`

<span data-ttu-id="90e66-468">Das Hinzufügen eines Domänenpaars ermöglicht oder blockiert nur die *Kombination* des spoofierten Benutzers *und der sendenden* Infrastruktur.</span><span class="sxs-lookup"><span data-stu-id="90e66-468">Adding a domain pair only allows or blocks the *combination* of the spoofed user *and* the sending infrastructure.</span></span> <span data-ttu-id="90e66-469">E-Mails vom spoofierten Benutzer aus einer Beliebigen Quelle werden nicht zulässig, und es werden auch keine E-Mails aus der sendenden Infrastrukturquelle für spoofierte Benutzer zulässig.</span><span class="sxs-lookup"><span data-stu-id="90e66-469">It does not allow email from the spoofed user from any source, nor does it allow email from the sending infrastructure source for any spoofed user.</span></span>

<span data-ttu-id="90e66-470">Beispielsweise fügen Sie einen zulässigen Eintrag für das folgende Domänenpaar hinzu:</span><span class="sxs-lookup"><span data-stu-id="90e66-470">For example, you add an allow entry for the following domain pair:</span></span>

- <span data-ttu-id="90e66-471">**Domäne**: gmail.com</span><span class="sxs-lookup"><span data-stu-id="90e66-471">**Domain**: gmail.com</span></span>
- <span data-ttu-id="90e66-472">**Infrastruktur**: tms.mx.com</span><span class="sxs-lookup"><span data-stu-id="90e66-472">**Infrastructure**: tms.mx.com</span></span>

<span data-ttu-id="90e66-473">Nur Nachrichten von dieser Domäne und *dem sendenden* Infrastrukturpaar dürfen spoofen.</span><span class="sxs-lookup"><span data-stu-id="90e66-473">Only messages from that domain *and* sending infrastructure pair are allowed to spoof.</span></span> <span data-ttu-id="90e66-474">Andere Absender, die versuchen, gmail.com zu spoofen, sind nicht zulässig.</span><span class="sxs-lookup"><span data-stu-id="90e66-474">Other senders attempting to spoof gmail.com aren't allowed.</span></span> <span data-ttu-id="90e66-475">Nachrichten von Absendern in anderen Domänen, die von tms.mx.com stammen, werden durch Spoof intelligence überprüft.</span><span class="sxs-lookup"><span data-stu-id="90e66-475">Messages from senders in other domains originating from tms.mx.com are checked by spoof intelligence.</span></span>
