---
title: Verwalten Ihrer Zulassungen und Blöcke in der Mandanten-Zulassungs-/Sperrliste
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
description: Administratoren können im Sicherheitsportal erfahren, wie Sie Zulassungen und Blöcke in der Mandanten-Zulassungs-/Sperrliste konfigurieren.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 12139708fc5cde133819713fd7185435e594a1a9
ms.sourcegitcommit: e1e275eb88153bafddf93327adf8f82318913a8d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2021
ms.locfileid: "52809179"
---
# <a name="manage-the-tenant-allowblock-list"></a><span data-ttu-id="8df29-103">Verwalten der Zulassungs-/Sperrliste des Mandanten</span><span class="sxs-lookup"><span data-stu-id="8df29-103">Manage the Tenant Allow/Block List</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="8df29-104">**Gilt für**</span><span class="sxs-lookup"><span data-stu-id="8df29-104">**Applies to**</span></span>
- [<span data-ttu-id="8df29-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="8df29-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="8df29-106">Microsoft Defender für Office 365 Plan 1 und Plan 2</span><span class="sxs-lookup"><span data-stu-id="8df29-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="8df29-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="8df29-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

> [!NOTE]
>
> <span data-ttu-id="8df29-108">Die in diesem Artikel beschriebenen Features befinden sich in der Vorschau, können geändert werden und sind nicht in allen Organisationen verfügbar.</span><span class="sxs-lookup"><span data-stu-id="8df29-108">The features described in this article are in Preview, are subject to change, and are not available in all organizations.</span></span>  <span data-ttu-id="8df29-109">Wenn Ihre Organisation nicht über die in diesem Artikel beschriebenen Spoofingfeatures verfügt, lesen Sie die ältere Spoofverwaltungserfahrung unter [Verwalten von gefälschten Absendern mithilfe der Spoof Intelligence-Richtlinie und des Einblicks in spoofintelligenz in EOP.](walkthrough-spoof-intelligence-insight.md)</span><span class="sxs-lookup"><span data-stu-id="8df29-109">If your organization does not have the spoof features as described in this article, see the older spoof management experience at [Manage spoofed senders using the spoof intelligence policy and spoof intelligence insight in EOP](walkthrough-spoof-intelligence-insight.md).</span></span>
>
> <span data-ttu-id="8df29-110">Sie können derzeit keine zulässigen URL- oder Dateielemente in der Mandanten-Zulassungs-/Sperrliste **konfigurieren.**</span><span class="sxs-lookup"><span data-stu-id="8df29-110">You can't **configure** allowed URL or file items in the Tenant Allow/Block List at this time.</span></span>

<span data-ttu-id="8df29-111">In Microsoft 365 Organisationen mit Postfächern in Exchange Online oder eigenständigen Exchange Online Protection (EOP)-Organisationen ohne Exchange Online Postfächer, können Sie mit der EOP-Filterbewertung nicht einverstanden sein.</span><span class="sxs-lookup"><span data-stu-id="8df29-111">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, you might disagree with the EOP filtering verdict.</span></span> <span data-ttu-id="8df29-112">Beispielsweise kann eine gute Nachricht als falsch markiert werden (ein falsch positives Ergebnis), oder eine ungültige Nachricht kann durchgelassen werden (ein falsch negativer Wert).</span><span class="sxs-lookup"><span data-stu-id="8df29-112">For example, a good message might be marked as bad (a false positive), or a bad message might be allowed through (a false negative).</span></span>

<span data-ttu-id="8df29-113">Die Mandanten-Zulassungs-/Sperrliste im Security & Compliance Center bietet Ihnen die Möglichkeit, die Microsoft 365 Filterbewertungen manuell zu überschreiben.</span><span class="sxs-lookup"><span data-stu-id="8df29-113">The Tenant Allow/Block List in the Security & Compliance Center gives you a way to manually override the Microsoft 365 filtering verdicts.</span></span> <span data-ttu-id="8df29-114">Die Mandanten-Zulassungs-/Sperrliste wird während des Nachrichtenflusses und zum Zeitpunkt der Benutzerklicks verwendet.</span><span class="sxs-lookup"><span data-stu-id="8df29-114">The Tenant Allow/Block List is used during mail flow and at the time of user clicks.</span></span> <span data-ttu-id="8df29-115">Sie können die folgenden Arten von Außerkraftsetzungen angeben:</span><span class="sxs-lookup"><span data-stu-id="8df29-115">You can specify the following types of overrides:</span></span>

- <span data-ttu-id="8df29-116">Zu blockierende URLs.</span><span class="sxs-lookup"><span data-stu-id="8df29-116">URLs to block.</span></span>
- <span data-ttu-id="8df29-117">Zu blockierende Dateien.</span><span class="sxs-lookup"><span data-stu-id="8df29-117">Files to block.</span></span>
- <span data-ttu-id="8df29-118">Gefälschte Absender, die zugelassen oder blockiert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="8df29-118">Spoofed senders to allow or block.</span></span> <span data-ttu-id="8df29-119">Wenn Sie die Zulassungs- oder Blockbewertung im Einblick in die [Spoofintelligenz](learn-about-spoof-intelligence.md)außer Kraft setzen, wird der gefälschte Absender zu einem manuellen Zulassungs- oder Blockierungseintrag, der nur auf der Registerkarte **"Spoofing"** in der Mandanten-Zulassungs-/Sperrliste angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="8df29-119">If you override the allow or block verdict in the [spoof intelligence insight](learn-about-spoof-intelligence.md), the spoofed sender becomes a manual allow or block entry that only appears on the **Spoof** tab in the Tenant Allow/Block List.</span></span> <span data-ttu-id="8df29-120">Sie können hier auch manuell Zulassungseinträge für gefälschte Absender erstellen oder blockieren, bevor sie durch Spoofintelligenz erkannt werden.</span><span class="sxs-lookup"><span data-stu-id="8df29-120">You can also manually create allow or block entries for spoofed senders here before they're detected by spoof intelligence.</span></span>

<span data-ttu-id="8df29-121">In diesem Artikel wird beschrieben, wie Sie Einträge in der Mandanten-Zulassungs-/Sperrliste im Security & Compliance Center oder in PowerShell (Exchange Online PowerShell für Microsoft 365 Organisationen mit Postfächern in Exchange Online; eigenständige EOP PowerShell für Organisationen ohne Exchange Online Postfächer) konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="8df29-121">This article describes how to configure entries in the Tenant Allow/Block List in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="8df29-122">Was sollten Sie wissen, bevor Sie beginnen?</span><span class="sxs-lookup"><span data-stu-id="8df29-122">What do you need to know before you begin?</span></span>

- <span data-ttu-id="8df29-123">Sie öffnen das Security & Compliance Center unter <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="8df29-123">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="8df29-124">Um direkt zur Seite **"Mandanten-Zulassungs-/Sperrliste"** zu wechseln, verwenden Sie <https://protection.office.com/tenantAllowBlockList> .</span><span class="sxs-lookup"><span data-stu-id="8df29-124">To go directly to the **Tenant Allow/Block List** page, use <https://protection.office.com/tenantAllowBlockList>.</span></span>

- <span data-ttu-id="8df29-125">Sie geben Dateien mithilfe des SHA256-Hashwerts der Datei an.</span><span class="sxs-lookup"><span data-stu-id="8df29-125">You specify files by using the SHA256 hash value of the file.</span></span> <span data-ttu-id="8df29-126">Um den SHA256-Hashwert einer Datei in Windows zu finden, führen Sie den folgenden Befehl an einer Eingabeaufforderung aus:</span><span class="sxs-lookup"><span data-stu-id="8df29-126">To find the SHA256 hash value of a file in Windows, run the following command in a Command Prompt:</span></span>

  ```console
  certutil.exe -hashfile "<Path>\<Filename>" SHA256
  ```

  <span data-ttu-id="8df29-127">Ein Beispielwert ist `768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3a` .</span><span class="sxs-lookup"><span data-stu-id="8df29-127">An example value is `768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3a`.</span></span> <span data-ttu-id="8df29-128">Perceptual Hash (pHash)-Werte werden nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="8df29-128">Perceptual hash (pHash) values are not supported.</span></span>

- <span data-ttu-id="8df29-129">Die verfügbaren URL-Werte werden in der [URL-Syntax für den Abschnitt "Mandanten-Zulassungs-/Sperrliste"](#url-syntax-for-the-tenant-allowblock-list) weiter unten in diesem Artikel beschrieben.</span><span class="sxs-lookup"><span data-stu-id="8df29-129">The available URL values are described in the [URL syntax for the Tenant Allow/Block List](#url-syntax-for-the-tenant-allowblock-list) section later in this article.</span></span>

- <span data-ttu-id="8df29-130">Die Mandanten-Zulassungs-/Sperrliste lässt maximal 500 Einträge für URLs und 500 Einträge für Dateihashes zu.</span><span class="sxs-lookup"><span data-stu-id="8df29-130">The Tenant Allow/Block List allows a maximum of 500 entries for URLs, and 500 entries for file hashes.</span></span>

- <span data-ttu-id="8df29-131">Die maximale Anzahl von Zeichen für jeden Eintrag lautet:</span><span class="sxs-lookup"><span data-stu-id="8df29-131">The maximum number of characters for each entry is:</span></span>
  - <span data-ttu-id="8df29-132">Dateihashes = 64</span><span class="sxs-lookup"><span data-stu-id="8df29-132">File hashes = 64</span></span>
  - <span data-ttu-id="8df29-133">URL = 250</span><span class="sxs-lookup"><span data-stu-id="8df29-133">URL = 250</span></span>

- <span data-ttu-id="8df29-134">Ein Eintrag sollte innerhalb von 30 Minuten aktiv sein.</span><span class="sxs-lookup"><span data-stu-id="8df29-134">An entry should be active within 30 minutes.</span></span>

- <span data-ttu-id="8df29-135">Standardmäßig laufen Einträge in der Mandanten-Zulassungs-/Sperrliste nach 30 Tagen ab.</span><span class="sxs-lookup"><span data-stu-id="8df29-135">By default, entries in the Tenant Allow/Block List will expire after 30 days.</span></span> <span data-ttu-id="8df29-136">Sie können ein Datum angeben oder festlegen, dass es nie abläuft.</span><span class="sxs-lookup"><span data-stu-id="8df29-136">You can specify a date or set them to never expire.</span></span>

- <span data-ttu-id="8df29-137">Wie Sie eine Verbindung mit Exchange Online PowerShell herstellen, finden Sie unter [Herstellen einer Verbindung mit Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="8df29-137">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="8df29-138">Informationen zum Herstellen einer Verbindung mit dem eigenständigen Exchange Online Protection PowerShell finden Sie unter [Verbinden mit PowerShell in Exchange Online Protection](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="8df29-138">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="8df29-139">Sie müssen in Exchange Online Berechtigungen erhalten, bevor Sie die in diesem Artikel beschriebenen Schritte ausführen können:</span><span class="sxs-lookup"><span data-stu-id="8df29-139">You need to be assigned permissions in Exchange Online before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="8df29-140">**URLs und Dateien:**</span><span class="sxs-lookup"><span data-stu-id="8df29-140">**URLs and files**:</span></span>
    - <span data-ttu-id="8df29-141">Um Werte aus der Mandanten-Zulassungs-/Sperrliste hinzuzufügen und zu entfernen, müssen Sie Mitglied der Rollengruppen **"Organisationsverwaltung"** oder **"Sicherheitsadministrator"** sein.</span><span class="sxs-lookup"><span data-stu-id="8df29-141">To add and remove values from the Tenant Allow/Block List, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
    - <span data-ttu-id="8df29-142">Für den schreibgeschützten Zugriff auf die Mandanten-Zulassungs-/Sperrliste müssen Sie Mitglied der Rollengruppe **"Globaler Leser"** oder **"Sicherheitsleseberechtigter"** sein.</span><span class="sxs-lookup"><span data-stu-id="8df29-142">For read-only access to the Tenant Allow/Block List, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>
  - <span data-ttu-id="8df29-143">**Spoofing:** Eine der folgenden Kombinationen:</span><span class="sxs-lookup"><span data-stu-id="8df29-143">**Spoofing**: One of the following combinations:</span></span>
    - <span data-ttu-id="8df29-144">**Organisationsverwaltung**</span><span class="sxs-lookup"><span data-stu-id="8df29-144">**Organization Management**</span></span>
    - <span data-ttu-id="8df29-145">**Sicherheitsadministrator** <u>und</u> **Nur-Ansicht-Konfiguration** oder **Nur-Ansicht-Organisationsverwaltung**.</span><span class="sxs-lookup"><span data-stu-id="8df29-145">**Security Administrator** <u>and</u> **View-Only Configuration** or **View-Only Organization Management**.</span></span>

  <span data-ttu-id="8df29-146">Weitere Informationen finden Sie unter [Berechtigungen in Exchange Online](/exchange/permissions-exo/permissions-exo).</span><span class="sxs-lookup"><span data-stu-id="8df29-146">For more information, see [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo).</span></span>

  > [!NOTE]
  >
  > - <span data-ttu-id="8df29-147">Durch das Hinzufügen von Benutzern zur entsprechenden Azure Active Directory-Rolle im Microsoft 365 Admin Center erhalten Benutzer die erforderlichen Berechtigungen _und_ Berechtigungen für andere Features in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="8df29-147">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="8df29-148">Weitere Informationen finden Sie unter [Informationen zu Administratorrollen](../../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="8df29-148">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  >
  > - <span data-ttu-id="8df29-149">Die Rollengruppe **Organisationsverwaltung mit Leserechten** in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) ermöglicht auch einen schreibgeschützten Zugriff auf das Feature.</span><span class="sxs-lookup"><span data-stu-id="8df29-149">The **View-Only Organization Management** role group in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

## <a name="use-the-security--compliance-center-to-create-block-url-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="8df29-150">Verwenden des Security & Compliance Centers zum Erstellen von Block-URL-Einträgen in der Mandanten-Zulassungs-/Sperrliste</span><span class="sxs-lookup"><span data-stu-id="8df29-150">Use the Security & Compliance Center to create block URL entries in the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="8df29-151">Wechseln Sie im Security & Compliance  Center zu \> "Zulassungs-/Sperrlisten des Mandanten für die Bedrohungsverwaltungsrichtlinie".  \> </span><span class="sxs-lookup"><span data-stu-id="8df29-151">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="8df29-152">Überprüfen Sie auf der Seite **"Mandanten-Zulassungs-/Sperrliste",** ob die Registerkarte **"URLs"** ausgewählt ist, und klicken Sie dann auf **"Blockieren".**</span><span class="sxs-lookup"><span data-stu-id="8df29-152">On the **Tenant Allow/Block List** page, verify that the **URLs** tab is selected, and then click **Block**</span></span>

3. <span data-ttu-id="8df29-153">Konfigurieren Sie im angezeigten Flyout **"URLs blockieren"** die folgenden Einstellungen:</span><span class="sxs-lookup"><span data-stu-id="8df29-153">In the **Block URLs** flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="8df29-154">**Hinzufügen von ZU blockierenden URLs:** Geben Sie eine URL pro Zeile ein, bis maximal 20.</span><span class="sxs-lookup"><span data-stu-id="8df29-154">**Add URLs to block**: Enter one URL per line, up to a maximum of 20.</span></span> <span data-ttu-id="8df29-155">Ausführliche Informationen zur Syntax für URL-Einträge finden Sie in der [URL-Syntax für den Abschnitt "Mandanten-Zulassungs-/Sperrliste"](#url-syntax-for-the-tenant-allowblock-list) weiter unten in diesem Artikel.</span><span class="sxs-lookup"><span data-stu-id="8df29-155">For details about the syntax for URL entries, see the [URL syntax for the Tenant Allow/Block List](#url-syntax-for-the-tenant-allowblock-list) section later in this article.</span></span>

   - <span data-ttu-id="8df29-156">**Läuft nie ab:** Führen Sie einen der folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="8df29-156">**Never expire**: Do one of the following steps:</span></span>

     - <span data-ttu-id="8df29-157">Stellen Sie sicher, dass die Einstellung deaktiviert ist ( ![ Umschalten ](../../media/scc-toggle-off.png) ) und verwenden Sie das Feld **"Läuft ab",** um das Ablaufdatum für die Einträge anzugeben.</span><span class="sxs-lookup"><span data-stu-id="8df29-157">Verify the setting is turned off (![Toggle off](../../media/scc-toggle-off.png)) and use the **Expires on** box to specify the expiration date for the entries.</span></span>

       <span data-ttu-id="8df29-158">oder</span><span class="sxs-lookup"><span data-stu-id="8df29-158">or</span></span>

     - <span data-ttu-id="8df29-159">Verschieben Sie den Umschalter nach rechts, um die Einträge so zu konfigurieren, dass sie nie ablaufen:</span><span class="sxs-lookup"><span data-stu-id="8df29-159">Move the toggle to the right to configure the entries to never expire:</span></span> ![Umschaltfläche ein](../../media/scc-toggle-on.png)<span data-ttu-id="8df29-161">.</span><span class="sxs-lookup"><span data-stu-id="8df29-161">.</span></span>

   - <span data-ttu-id="8df29-162">**Optionaler Hinweis:** Geben Sie beschreibenden Text für die Einträge ein.</span><span class="sxs-lookup"><span data-stu-id="8df29-162">**Optional note**: Enter descriptive text for the entries.</span></span>

4. <span data-ttu-id="8df29-163">Klicken Sie nach Abschluss des Vorgangs auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="8df29-163">When you're finished, click **Add**.</span></span>

## <a name="use-the-security--compliance-center-to-create-block-file-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="8df29-164">Verwenden des Security & Compliance Centers zum Erstellen von Blockierungsdateieinträgen in der Mandanten-Zulassungs-/Sperrliste</span><span class="sxs-lookup"><span data-stu-id="8df29-164">Use the Security & Compliance Center to create block file entries in the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="8df29-165">Wechseln Sie im Security & Compliance  Center zu \> "Zulassungs-/Sperrlisten des Mandanten für die Bedrohungsverwaltungsrichtlinie".  \> </span><span class="sxs-lookup"><span data-stu-id="8df29-165">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="8df29-166">Wählen Sie auf der Seite **"Mandanten-Zulassungs-/Sperrliste"** die Registerkarte **"Dateien"** aus, und klicken Sie dann auf **"Blockieren".**</span><span class="sxs-lookup"><span data-stu-id="8df29-166">On the **Tenant Allow/Block List** page, select the **Files** tab, and then click **Block**.</span></span>

3. <span data-ttu-id="8df29-167">Konfigurieren Sie in den angezeigten **Add-Dateien zum Blockieren** des Flyouts die folgenden Einstellungen:</span><span class="sxs-lookup"><span data-stu-id="8df29-167">In the **Add files to block** flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="8df29-168">**Hinzufügen von Dateihashes:** Geben Sie einen SHA256-Hashwert pro Zeile ein, bis maximal 20.</span><span class="sxs-lookup"><span data-stu-id="8df29-168">**Add file hashes**: Enter one SHA256 hash value per line, up to a maximum of 20.</span></span>

   - <span data-ttu-id="8df29-169">**Läuft nie ab:** Führen Sie einen der folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="8df29-169">**Never expire**: Do one of the following steps:</span></span>

     - <span data-ttu-id="8df29-170">Stellen Sie sicher, dass die Einstellung deaktiviert ist ( ![ Umschalten ](../../media/scc-toggle-off.png) ) und verwenden Sie das Feld **"Läuft ab",** um das Ablaufdatum für die Einträge anzugeben.</span><span class="sxs-lookup"><span data-stu-id="8df29-170">Verify the setting is turned off (![Toggle off](../../media/scc-toggle-off.png)) and use the **Expires on** box to specify the expiration date for the entries.</span></span>

     <span data-ttu-id="8df29-171">oder</span><span class="sxs-lookup"><span data-stu-id="8df29-171">or</span></span>

     - <span data-ttu-id="8df29-172">Verschieben Sie den Umschalter nach rechts, um die Einträge so zu konfigurieren, dass sie nie ablaufen:</span><span class="sxs-lookup"><span data-stu-id="8df29-172">Move the toggle to the right to configure the entries to never expire:</span></span> ![Umschaltfläche ein](../../media/scc-toggle-on.png)<span data-ttu-id="8df29-174">.</span><span class="sxs-lookup"><span data-stu-id="8df29-174">.</span></span>

   - <span data-ttu-id="8df29-175">**Optionaler Hinweis:** Geben Sie beschreibenden Text für die Einträge ein.</span><span class="sxs-lookup"><span data-stu-id="8df29-175">**Optional note**: Enter descriptive text for the entries.</span></span>

4. <span data-ttu-id="8df29-176">Klicken Sie nach Abschluss des Vorgangs auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="8df29-176">When you're finished, click **Add**.</span></span>

## <a name="use-the-security--compliance-center-to-create-allow-or-block-spoofed-sender-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="8df29-177">Verwenden des Security & Compliance Center zum Erstellen oder Blockieren von Spoofing-Absendereinträgen in der Mandanten-Zulassungs-/Sperrliste</span><span class="sxs-lookup"><span data-stu-id="8df29-177">Use the Security & Compliance Center to create allow or block spoofed sender entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="8df29-178">**Hinweise**:</span><span class="sxs-lookup"><span data-stu-id="8df29-178">**Notes**:</span></span>

- <span data-ttu-id="8df29-179">Nur die _Kombination aus_ dem gefälschten Benutzer _und_ der sendenden Infrastruktur, wie im Domänenpaar definiert, ist ausdrücklich zulässig oder am Spoofing gehindert.</span><span class="sxs-lookup"><span data-stu-id="8df29-179">Only the _combination_ of the spoofed user _and_ the sending infrastructure as defined in the domain pair is specifically allowed or blocked from spoofing.</span></span>
- <span data-ttu-id="8df29-180">Wenn Sie einen Zulassungs- oder Blockeintrag für ein Domänenpaar konfigurieren, werden Nachrichten von diesem Domänenpaar nicht mehr in der Spoofintelligenz angezeigt.</span><span class="sxs-lookup"><span data-stu-id="8df29-180">When you configure an allow or block entry for a domain pair, messages from that domain pair no longer appear in the spoof intelligence insight.</span></span>
- <span data-ttu-id="8df29-181">Einträge für gefälschte Absender laufen nie ab.</span><span class="sxs-lookup"><span data-stu-id="8df29-181">Entries for spoofed senders never expire.</span></span>

1. <span data-ttu-id="8df29-182">Wechseln Sie im Security & Compliance  Center zu \> "Zulassungs-/Sperrlisten des Mandanten für die Bedrohungsverwaltungsrichtlinie".  \> </span><span class="sxs-lookup"><span data-stu-id="8df29-182">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="8df29-183">Wählen Sie auf der Seite **"Mandanten-Zulassungs-/Sperrliste"** die Registerkarte **"Spoofing"** aus, und klicken Sie dann auf **"Hinzufügen".**</span><span class="sxs-lookup"><span data-stu-id="8df29-183">On the **Tenant Allow/Block List** page, select the **Spoofing** tab, and then click **Add**.</span></span>

3. <span data-ttu-id="8df29-184">Konfigurieren Sie im angezeigten Flyout **"Neue Domänenpaare hinzufügen"** die folgenden Einstellungen:</span><span class="sxs-lookup"><span data-stu-id="8df29-184">In the **Add new domain pairs** flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="8df29-185">**Hinzufügen neuer Domänenpaare mit Platzhaltern:** Geben Sie ein Domänenpaar pro Zeile ein, maximal 20.</span><span class="sxs-lookup"><span data-stu-id="8df29-185">**Add new domain pairs with wildcards**: Enter one domain pair per line, up to a maximum of 20.</span></span> <span data-ttu-id="8df29-186">Ausführliche Informationen zur Syntax für spoofierte Absendereinträge finden Sie in der [Domänenpaarsyntax für spoofierte Absendereinträge im Abschnitt "Mandanten-Zulassungs-/Sperrliste"](#domain-pair-syntax-for-spoofed-sender-entries-in-the-tenant-allowblock-list) weiter unten in diesem Artikel.</span><span class="sxs-lookup"><span data-stu-id="8df29-186">For details about the syntax for spoofed sender entries, see the [Domain pair syntax for spoofed sender entries in the Tenant Allow/Block List](#domain-pair-syntax-for-spoofed-sender-entries-in-the-tenant-allowblock-list) section later in this article.</span></span>

   - <span data-ttu-id="8df29-187">**Spooftyp:** Wählen Sie einen der folgenden Werte aus:</span><span class="sxs-lookup"><span data-stu-id="8df29-187">**Spoof type**: Select one of the following values:</span></span>
     - <span data-ttu-id="8df29-188">**Intern:** Der gefälschte Absender befindet sich in einer Domäne, die zu Ihrer Organisation gehört (einer [akzeptierten Domäne).](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)</span><span class="sxs-lookup"><span data-stu-id="8df29-188">**Internal**: The spoofed sender is in a domain that belongs to your organization (an [accepted domain](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)).</span></span>
     - <span data-ttu-id="8df29-189">**Extern:** Der gefälschte Absender befindet sich in einer externen Domäne.</span><span class="sxs-lookup"><span data-stu-id="8df29-189">**External**: The spoofed sender is in an external domain.</span></span>

   - <span data-ttu-id="8df29-190">**Aktion:** Wählen Sie **"Zulassen"** oder **"Blockieren"** aus.</span><span class="sxs-lookup"><span data-stu-id="8df29-190">**Action**: Select **Allow** or **Block**.</span></span>

4. <span data-ttu-id="8df29-191">Klicken Sie nach Abschluss des Vorgangs auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="8df29-191">When you're finished, click **Add**.</span></span>

## <a name="use-the-security--compliance-center-to-view-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="8df29-192">Verwenden des Security & Compliance Centers zum Anzeigen von Einträgen in der Mandanten-Zulassungs-/Sperrliste</span><span class="sxs-lookup"><span data-stu-id="8df29-192">Use the Security & Compliance Center to view entries in the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="8df29-193">Wechseln Sie im Security & Compliance  Center zu \> "Zulassungs-/Sperrlisten des Mandanten für die Bedrohungsverwaltungsrichtlinie".  \> </span><span class="sxs-lookup"><span data-stu-id="8df29-193">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="8df29-194">Wählen Sie die gewünschte Registerkarte aus.</span><span class="sxs-lookup"><span data-stu-id="8df29-194">Select the tab you want.</span></span> <span data-ttu-id="8df29-195">Welche Spalten verfügbar sind, hängt von der ausgewählten Registerkarte ab:</span><span class="sxs-lookup"><span data-stu-id="8df29-195">The columns that are available depend on the tab you selected:</span></span>

   - <span data-ttu-id="8df29-196">**URLs:**</span><span class="sxs-lookup"><span data-stu-id="8df29-196">**URLs**:</span></span>
     - <span data-ttu-id="8df29-197">**Wert:** Die URL.</span><span class="sxs-lookup"><span data-stu-id="8df29-197">**Value**: The URL.</span></span>
     - <span data-ttu-id="8df29-198">**Aktion:** Der Wert **Block**.</span><span class="sxs-lookup"><span data-stu-id="8df29-198">**Action**: The value **Block**.</span></span>
     - <span data-ttu-id="8df29-199">**Datum der letzten Aktualisierung**</span><span class="sxs-lookup"><span data-stu-id="8df29-199">**Last updated date**</span></span>
     - <span data-ttu-id="8df29-200">**Ablaufdatum**</span><span class="sxs-lookup"><span data-stu-id="8df29-200">**Expiration date**</span></span>
     - <span data-ttu-id="8df29-201">**Hinweis**</span><span class="sxs-lookup"><span data-stu-id="8df29-201">**Note**</span></span>

   - <span data-ttu-id="8df29-202">**Files**</span><span class="sxs-lookup"><span data-stu-id="8df29-202">**Files**</span></span>
     - <span data-ttu-id="8df29-203">**Wert:** Der Dateihash.</span><span class="sxs-lookup"><span data-stu-id="8df29-203">**Value**: The file hash.</span></span>
     - <span data-ttu-id="8df29-204">**Aktion:** Der Wert **Block**.</span><span class="sxs-lookup"><span data-stu-id="8df29-204">**Action**: The value **Block**.</span></span>
     - <span data-ttu-id="8df29-205">**Datum der letzten Aktualisierung**</span><span class="sxs-lookup"><span data-stu-id="8df29-205">**Last updated date**</span></span>
     - <span data-ttu-id="8df29-206">**Ablaufdatum**</span><span class="sxs-lookup"><span data-stu-id="8df29-206">**Expiration date**</span></span>
     - <span data-ttu-id="8df29-207">**Hinweis**</span><span class="sxs-lookup"><span data-stu-id="8df29-207">**Note**</span></span>

   - <span data-ttu-id="8df29-208">**Spoofing**</span><span class="sxs-lookup"><span data-stu-id="8df29-208">**Spoofing**</span></span>
     - <span data-ttu-id="8df29-209">**Gefälschter Benutzer**</span><span class="sxs-lookup"><span data-stu-id="8df29-209">**Spoofed user**</span></span>
     - <span data-ttu-id="8df29-210">**Senden der Infrastruktur**</span><span class="sxs-lookup"><span data-stu-id="8df29-210">**Sending infrastructure**</span></span>
     - <span data-ttu-id="8df29-211">**Spooftyp:** Der Wert **Internal** oder **External**.</span><span class="sxs-lookup"><span data-stu-id="8df29-211">**Spoof type**: The value **Internal** or **External**.</span></span>
     - <span data-ttu-id="8df29-212">**Aktion:** Der Wert **Block** oder **Allow**.</span><span class="sxs-lookup"><span data-stu-id="8df29-212">**Action**: The value **Block** or **Allow**.</span></span>

   <span data-ttu-id="8df29-213">Sie können auf eine Spaltenüberschrift klicken, um sie in aufsteigender oder absteigender Reihenfolge zu sortieren.</span><span class="sxs-lookup"><span data-stu-id="8df29-213">You can click on a column heading to sort in ascending or descending order.</span></span>

   <span data-ttu-id="8df29-214">Sie können auf **"Gruppieren"** klicken, um die Ergebnisse zu gruppieren.</span><span class="sxs-lookup"><span data-stu-id="8df29-214">You can click **Group** to group the results.</span></span> <span data-ttu-id="8df29-215">Die verfügbaren Werte hängen von der ausgewählten Registerkarte ab:</span><span class="sxs-lookup"><span data-stu-id="8df29-215">The values that are available depend on the tab you selected:</span></span>

   - <span data-ttu-id="8df29-216">**URLs:** Sie können die Ergebnisse nach **Aktion** gruppieren.</span><span class="sxs-lookup"><span data-stu-id="8df29-216">**URLs**: You can group the results by **Action**.</span></span>
   - <span data-ttu-id="8df29-217">**Dateien:** Sie können die Ergebnisse nach **Aktion** gruppieren.</span><span class="sxs-lookup"><span data-stu-id="8df29-217">**Files**: You can group the results by **Action**.</span></span>
   - <span data-ttu-id="8df29-218">**Absenderdomänen für die BCL-Umgehung:** **Die Gruppe** ist auf dieser Registerkarte nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="8df29-218">**Sender domains for BCL bypass**: **Group** is not available on this tab.</span></span>
   - <span data-ttu-id="8df29-219">**Spoofing:** Sie können die Ergebnisse nach **Aktions-** oder **Spooftyp** gruppieren.</span><span class="sxs-lookup"><span data-stu-id="8df29-219">**Spoofing**: You can group the results by **Action** or **Spoof type**.</span></span>

   <span data-ttu-id="8df29-220">Klicken Sie auf **"Suchen",** geben Sie einen Wert ganz oder teilweise ein, und drücken Sie dann die EINGABETASTE, um einen bestimmten Wert zu finden.</span><span class="sxs-lookup"><span data-stu-id="8df29-220">Click **Search**, enter all or part of a value, and then press ENTER to find a specific value.</span></span> <span data-ttu-id="8df29-221">Wenn Sie fertig sind,  klicken Sie auf ![ Suchsymbol löschen ](../../media/b6512677-5e7b-42b0-a8a3-3be1d7fa23ee.gif) .</span><span class="sxs-lookup"><span data-stu-id="8df29-221">When you're finished, click **Clear search** ![Clear search icon](../../media/b6512677-5e7b-42b0-a8a3-3be1d7fa23ee.gif).</span></span>

   <span data-ttu-id="8df29-222">Klicken Sie auf **"Filtern",** um die Ergebnisse zu filtern.</span><span class="sxs-lookup"><span data-stu-id="8df29-222">Click **Filter** to filter the results.</span></span> <span data-ttu-id="8df29-223">Die werte, die  im angezeigten Filter-Flyout verfügbar sind, hängen von der ausgewählten Registerkarte ab:</span><span class="sxs-lookup"><span data-stu-id="8df29-223">The values that are available in **Filter** flyout that appears depend on the tab you selected:</span></span>

   - <span data-ttu-id="8df29-224">**Urls**</span><span class="sxs-lookup"><span data-stu-id="8df29-224">**URLs**</span></span>
     - <span data-ttu-id="8df29-225">**Action**</span><span class="sxs-lookup"><span data-stu-id="8df29-225">**Action**</span></span>
     - <span data-ttu-id="8df29-226">**Nie ablaufen**</span><span class="sxs-lookup"><span data-stu-id="8df29-226">**Never expire**</span></span>
     - <span data-ttu-id="8df29-227">**Datum der letzten Aktualisierung**</span><span class="sxs-lookup"><span data-stu-id="8df29-227">**Last updated date**</span></span>
     - <span data-ttu-id="8df29-228">**Ablaufdatum**</span><span class="sxs-lookup"><span data-stu-id="8df29-228">**Expiration date**</span></span>

   - <span data-ttu-id="8df29-229">**Files**</span><span class="sxs-lookup"><span data-stu-id="8df29-229">**Files**</span></span>
     - <span data-ttu-id="8df29-230">**Action**</span><span class="sxs-lookup"><span data-stu-id="8df29-230">**Action**</span></span>
     - <span data-ttu-id="8df29-231">**Nie ablaufen**</span><span class="sxs-lookup"><span data-stu-id="8df29-231">**Never expire**</span></span>
     - <span data-ttu-id="8df29-232">**Datum der letzten Aktualisierung**</span><span class="sxs-lookup"><span data-stu-id="8df29-232">**Last updated date**</span></span>
     - <span data-ttu-id="8df29-233">**Ablaufdatum**</span><span class="sxs-lookup"><span data-stu-id="8df29-233">**Expiration date**</span></span>

   - <span data-ttu-id="8df29-234">**Absenderdomänen für BCL-Umgehung**</span><span class="sxs-lookup"><span data-stu-id="8df29-234">**Sender domains for BCL bypass**</span></span>
     - <span data-ttu-id="8df29-235">**Nie ablaufen**</span><span class="sxs-lookup"><span data-stu-id="8df29-235">**Never expire**</span></span>
     - <span data-ttu-id="8df29-236">**Datum der letzten Aktualisierung**</span><span class="sxs-lookup"><span data-stu-id="8df29-236">**Last updated date**</span></span>
     - <span data-ttu-id="8df29-237">**Ablaufdatum**</span><span class="sxs-lookup"><span data-stu-id="8df29-237">**Expiration date**</span></span>

   - <span data-ttu-id="8df29-238">**Spoofing**</span><span class="sxs-lookup"><span data-stu-id="8df29-238">**Spoofing**</span></span>
     - <span data-ttu-id="8df29-239">**Action**</span><span class="sxs-lookup"><span data-stu-id="8df29-239">**Action**</span></span>
     - <span data-ttu-id="8df29-240">**Spooftyp**</span><span class="sxs-lookup"><span data-stu-id="8df29-240">**Spoof type**</span></span>

   <span data-ttu-id="8df29-241">Wenn Sie fertig sind, klicken Sie auf **"Übernehmen".**</span><span class="sxs-lookup"><span data-stu-id="8df29-241">When you're finished, click **Apply**.</span></span> <span data-ttu-id="8df29-242">Klicken Sie zum Löschen vorhandener Filter auf **"Filter",** und klicken Sie im angezeigten **Flyout "Filter"** auf **"Filter löschen".**</span><span class="sxs-lookup"><span data-stu-id="8df29-242">To clear existing filters, click **Filter**, and in the **Filter** flyout that appears, click **Clear filters**.</span></span>

## <a name="use-the-security--compliance-center-to-modify-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="8df29-243">Verwenden des Security & Compliance Centers zum Ändern von Einträgen in der Mandanten-Zulassungs-/Sperrliste</span><span class="sxs-lookup"><span data-stu-id="8df29-243">Use the Security & Compliance Center to modify entries in the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="8df29-244">Wechseln Sie im Security & Compliance  Center zu \> "Zulassungs-/Sperrlisten des Mandanten für die Bedrohungsverwaltungsrichtlinie".  \> </span><span class="sxs-lookup"><span data-stu-id="8df29-244">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="8df29-245">Wählen Sie die Registerkarte aus, die den Eintragstyp enthält, den Sie ändern möchten:</span><span class="sxs-lookup"><span data-stu-id="8df29-245">Select the tab that contains the type of entry that you want to modify:</span></span>
   - <span data-ttu-id="8df29-246">**Urls**</span><span class="sxs-lookup"><span data-stu-id="8df29-246">**URLs**</span></span>
   - <span data-ttu-id="8df29-247">**Files**</span><span class="sxs-lookup"><span data-stu-id="8df29-247">**Files**</span></span>
   - <span data-ttu-id="8df29-248">**Absenderdomänen für BCL-Umgehung**</span><span class="sxs-lookup"><span data-stu-id="8df29-248">**Sender domains for BCL bypass**</span></span>
   - <span data-ttu-id="8df29-249">**Spoofing**</span><span class="sxs-lookup"><span data-stu-id="8df29-249">**Spoofing**</span></span>

3. <span data-ttu-id="8df29-250">Wählen Sie den Eintrag aus, den  Sie ändern möchten, und klicken Sie dann auf ![ "Bearbeiten". ](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png)</span><span class="sxs-lookup"><span data-stu-id="8df29-250">Select the entry that you want to modify, and then click **Edit** ![Edit icon](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png).</span></span> <span data-ttu-id="8df29-251">Die Werte, die Sie im angezeigten Flyout ändern können, hängen von der Registerkarte ab, die Sie im vorherigen Schritt ausgewählt haben:</span><span class="sxs-lookup"><span data-stu-id="8df29-251">The values that you are able to modify in the flyout that appears depend on the tab you selected in the previous step:</span></span>

   - <span data-ttu-id="8df29-252">**Urls**</span><span class="sxs-lookup"><span data-stu-id="8df29-252">**URLs**</span></span>
     - <span data-ttu-id="8df29-253">**Nie ablaufen** und/oder Ablaufdatum.</span><span class="sxs-lookup"><span data-stu-id="8df29-253">**Never expire** and/or expiration date.</span></span>
     - <span data-ttu-id="8df29-254">**Optionaler Hinweis**</span><span class="sxs-lookup"><span data-stu-id="8df29-254">**Optional note**</span></span>

   - <span data-ttu-id="8df29-255">**Files**</span><span class="sxs-lookup"><span data-stu-id="8df29-255">**Files**</span></span>
     - <span data-ttu-id="8df29-256">**Nie ablaufen** und/oder Ablaufdatum.</span><span class="sxs-lookup"><span data-stu-id="8df29-256">**Never expire** and/or expiration date.</span></span>
     - <span data-ttu-id="8df29-257">**Optionaler Hinweis**</span><span class="sxs-lookup"><span data-stu-id="8df29-257">**Optional note**</span></span>

   - <span data-ttu-id="8df29-258">**Absenderdomänen für BCL-Umgehung**</span><span class="sxs-lookup"><span data-stu-id="8df29-258">**Sender domains for BCL bypass**</span></span>
     - <span data-ttu-id="8df29-259">**Nie ablaufen** und/oder Ablaufdatum.</span><span class="sxs-lookup"><span data-stu-id="8df29-259">**Never expire** and/or expiration date.</span></span>

   - <span data-ttu-id="8df29-260">**Spoofing**</span><span class="sxs-lookup"><span data-stu-id="8df29-260">**Spoofing**</span></span>
     - <span data-ttu-id="8df29-261">**Aktion:** Sie können den Wert in **Zulassen** oder **Blockieren** ändern.</span><span class="sxs-lookup"><span data-stu-id="8df29-261">**Action**: You can change the value to **Allow** or **Block**.</span></span>

4. <span data-ttu-id="8df29-262">Klicken Sie nach Abschluss des Vorgangs auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="8df29-262">When you're finished, click **Save**.</span></span>

## <a name="use-the-security--compliance-center-to-remove-entries-from-the-tenant-allowblock-list"></a><span data-ttu-id="8df29-263">Verwenden des Security & Compliance Centers zum Entfernen von Einträgen aus der Mandanten-Zulassungs-/Sperrliste</span><span class="sxs-lookup"><span data-stu-id="8df29-263">Use the Security & Compliance Center to remove entries from the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="8df29-264">Wechseln Sie im Security & Compliance  Center zu \> "Zulassungs-/Sperrlisten des Mandanten für die Bedrohungsverwaltungsrichtlinie".  \> </span><span class="sxs-lookup"><span data-stu-id="8df29-264">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="8df29-265">Wählen Sie die Registerkarte aus, die den Eintragstyp enthält, den Sie entfernen möchten:</span><span class="sxs-lookup"><span data-stu-id="8df29-265">Select the tab that contains the type of entry that you want to remove:</span></span>
   - <span data-ttu-id="8df29-266">**Urls**</span><span class="sxs-lookup"><span data-stu-id="8df29-266">**URLs**</span></span>
   - <span data-ttu-id="8df29-267">**Files**</span><span class="sxs-lookup"><span data-stu-id="8df29-267">**Files**</span></span>
   - <span data-ttu-id="8df29-268">**Absenderdomänen für BCL-Umgehung**</span><span class="sxs-lookup"><span data-stu-id="8df29-268">**Sender domains for BCL bypass**</span></span>
   - <span data-ttu-id="8df29-269">**Spoofing**</span><span class="sxs-lookup"><span data-stu-id="8df29-269">**Spoofing**</span></span>

3. <span data-ttu-id="8df29-270">Wählen Sie den Eintrag aus, den  Sie entfernen möchten, und klicken Sie dann auf das Symbol ![ "Löschen". ](../../media/87565fbb-5147-4f22-9ed7-1c18ce664392.png)</span><span class="sxs-lookup"><span data-stu-id="8df29-270">Select the entry that you want to remove, and then click **Delete** ![Delete icon](../../media/87565fbb-5147-4f22-9ed7-1c18ce664392.png).</span></span>

4. <span data-ttu-id="8df29-271">Klicken Sie im angezeigten Warndialogfeld auf **"Löschen".**</span><span class="sxs-lookup"><span data-stu-id="8df29-271">In the warning dialog that appears, click **Delete**.</span></span>

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-the-tenant-allowblock-list"></a><span data-ttu-id="8df29-272">Verwenden Exchange Online PowerShell oder der eigenständigen EOP-PowerShell zum Konfigurieren der Mandanten-Zulassungs-/Sperrliste</span><span class="sxs-lookup"><span data-stu-id="8df29-272">Use Exchange Online PowerShell or standalone EOP PowerShell to configure the Tenant Allow/Block List</span></span>

### <a name="use-powershell-to-add-block-file-or-url-entries-to-the-tenant-allowblock-list"></a><span data-ttu-id="8df29-273">Verwenden von PowerShell zum Hinzufügen von Blockierungsdateien oder URL-Einträgen zur Mandanten-Zulassungs-/Sperrliste</span><span class="sxs-lookup"><span data-stu-id="8df29-273">Use PowerShell to add block file or URL entries to the Tenant Allow/Block List</span></span>

<span data-ttu-id="8df29-274">Verwenden Sie die folgende Syntax, um Blockierungsdateien oder URL-Einträge in der Mandanten-Zulassungs-/Sperrliste hinzuzufügen:</span><span class="sxs-lookup"><span data-stu-id="8df29-274">To add block file or URL entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
New-TenantAllowBlockListItems -ListType <FileHash | Url> -Block -Entries "Value1","Value2",..."ValueN" <-ExpirationDate Date | -NoExpiration> [-Notes <String>]
```

<span data-ttu-id="8df29-275">In diesem Beispiel wird ein Blockdateieintrag für die angegebenen Dateien hinzugefügt, die nie ablaufen.</span><span class="sxs-lookup"><span data-stu-id="8df29-275">This example adds a block file entry for the specified files that never expires.</span></span>

```powershell
New-TenantAllowBlockListItem -ListType FileHash -Block -Entries "768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3","2c0a35409ff0873cfa28b70b8224e9aca2362241c1f0ed6f622fef8d4722fd9a" -NoExpiration
```

<span data-ttu-id="8df29-276">In diesem Beispiel wird ein Block-URL-Eintrag für contoso.com und alle Unterdomänen hinzugefügt (z. B. contoso.com, www.contoso.com und xyz.abc.contoso.com).</span><span class="sxs-lookup"><span data-stu-id="8df29-276">This example adds a block URL entry for contoso.com and all subdomains (for example, contoso.com, www.contoso.com, and xyz.abc.contoso.com).</span></span> <span data-ttu-id="8df29-277">Da wir die Parameter ExpirationDate oder NoExpiration nicht verwendet haben, läuft der Eintrag nach 30 Tagen ab.</span><span class="sxs-lookup"><span data-stu-id="8df29-277">Because we didn't use the ExpirationDate or NoExpiration parameters, the entry expires after 30 days.</span></span>

```powershell
New-TenantAllowBlockListItems -ListType Url -Block -Entries ~contoso.com
```

<span data-ttu-id="8df29-278">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [New-TenantAllowBlockListItems](/powershell/module/exchange/new-tenantallowblocklistitems).</span><span class="sxs-lookup"><span data-stu-id="8df29-278">For detailed syntax and parameter information, see [New-TenantAllowBlockListItems](/powershell/module/exchange/new-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-add-allow-or-block-spoofed-sender-entries-to-the-tenant-allowblock-list"></a><span data-ttu-id="8df29-279">Verwenden von PowerShell zum Hinzufügen oder Blockieren von Spoofing-Absendereinträgen zur Mandanten-Zulassungs-/Sperrliste</span><span class="sxs-lookup"><span data-stu-id="8df29-279">Use PowerShell to add allow or block spoofed sender entries to the Tenant Allow/Block List</span></span>

<span data-ttu-id="8df29-280">Verwenden Sie die folgende Syntax, um gefälschte Absendereinträge in der Mandanten-Zulassungs-/Sperrliste hinzuzufügen:</span><span class="sxs-lookup"><span data-stu-id="8df29-280">To add spoofed sender entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
New-TenantAllowBlockListSpoofItems -SpoofedUser <Domain | EmailAddress | *> -SendingInfrastructure <Domain | IPAddress/24> -SpoofType <External | Internal> -Action <Allow | Block>
```

<span data-ttu-id="8df29-281">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [New-TenantAllowBlockListSpoofItems](/powershell/module/exchange/new-tenantallowblocklistspoofitems).</span><span class="sxs-lookup"><span data-stu-id="8df29-281">For detailed syntax and parameter information, see [New-TenantAllowBlockListSpoofItems](/powershell/module/exchange/new-tenantallowblocklistspoofitems).</span></span>

### <a name="use-powershell-to-view-block-file-or-url-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="8df29-282">Verwenden von PowerShell zum Anzeigen von Blockierungsdateien oder URL-Einträgen in der Mandanten-Zulassungs-/Sperrliste</span><span class="sxs-lookup"><span data-stu-id="8df29-282">Use PowerShell to view block file or URL entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="8df29-283">Verwenden Sie die folgende Syntax, um Blockierungsdateien oder URL-Einträge in der Mandanten-Zulassungs-/Sperrliste anzuzeigen:</span><span class="sxs-lookup"><span data-stu-id="8df29-283">To view block file or URL entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType <FileHash | URL> [-Entry <FileHashValue | URLValue>] [<-ExpirationDate Date | -NoExpiration>]
```

<span data-ttu-id="8df29-284">In diesem Beispiel werden Informationen für den angegebenen Dateihashwert zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="8df29-284">This example returns information for the specified file hash value.</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType FileHash -Entry "9f86d081884c7d659a2feaa0c55ad015a3bf4f1b2b0b822cd15d6c15b0f00a08"
```

<span data-ttu-id="8df29-285">In diesem Beispiel werden alle blockierten URLs zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="8df29-285">This example returns all blocked URLs.</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType Url -Block
```

<span data-ttu-id="8df29-286">Ausführliche Informationen zu Syntax und Parametern finden Sie unter ["Get-TenantAllowBlockListItems".](/powershell/module/exchange/get-tenantallowblocklistitems)</span><span class="sxs-lookup"><span data-stu-id="8df29-286">For detailed syntax and parameter information, see [Get-TenantAllowBlockListItems](/powershell/module/exchange/get-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-view-allow-or-block-spoofed-sender-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="8df29-287">Verwenden von PowerShell zum Anzeigen oder Blockieren von Spoofing-Absendereinträgen in der Mandanten-Zulassungs-/Sperrliste</span><span class="sxs-lookup"><span data-stu-id="8df29-287">Use PowerShell to view allow or block spoofed sender entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="8df29-288">Verwenden Sie die folgende Syntax, um gefälschte Absendereinträge in der Mandanten-Zulassungs-/Sperrliste anzuzeigen:</span><span class="sxs-lookup"><span data-stu-id="8df29-288">To view spoofed sender entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Get-TenantAllowBlockListSpoofItems [-Action <Allow | Block>] [-SpoofType <External | Internal>
```

<span data-ttu-id="8df29-289">In diesem Beispiel werden alle gefälschten Absendereinträge in der Mandanten-Zulassungs-/Sperrliste zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="8df29-289">This example returns all spoofed sender entries in the Tenant Allow/Block List.</span></span>

```powershell
Get-TenantAllowBlockListSpoofItems
```

<span data-ttu-id="8df29-290">This example returns all allow spoofed sender entries that are internal.</span><span class="sxs-lookup"><span data-stu-id="8df29-290">This example returns all allow spoofed sender entries that are internal.</span></span>

```powershell
Get-TenantAllowBlockListSpoofItems -Action Allow -SpoofType Internal
```

<span data-ttu-id="8df29-291">In diesem Beispiel werden alle blockierten spoofierten Absendereinträge zurückgegeben, die extern sind.</span><span class="sxs-lookup"><span data-stu-id="8df29-291">This example returns all blocked spoofed sender entries that are external.</span></span>

```powershell
Get-TenantAllowBlockListSpoofItems -Action Block -SpoofType External
```

<span data-ttu-id="8df29-292">Ausführliche Informationen zu Syntax und Parametern finden Sie unter ["Get-TenantAllowBlockListSpoofItems".](/powershell/module/exchange/get-tenantallowblocklistspoofitems)</span><span class="sxs-lookup"><span data-stu-id="8df29-292">For detailed syntax and parameter information, see [Get-TenantAllowBlockListSpoofItems](/powershell/module/exchange/get-tenantallowblocklistspoofitems).</span></span>

### <a name="use-powershell-to-modify-block-file-and-url-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="8df29-293">Verwenden von PowerShell zum Ändern von Blockdatei- und URL-Einträgen in der Mandanten-Zulassungs-/Sperrliste</span><span class="sxs-lookup"><span data-stu-id="8df29-293">Use PowerShell to modify block file and URL entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="8df29-294">Verwenden Sie die folgende Syntax, um Blockdatei- und URL-Einträge in der Mandanten-Zulassungs-/Sperrliste zu ändern:</span><span class="sxs-lookup"><span data-stu-id="8df29-294">To modify block file and URL entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Set-TenantAllowBlockListItems -ListType <FileHash | Url> -Ids <"Id1","Id2",..."IdN"> [<-ExpirationDate Date | -NoExpiration>] [-Notes <String>]
```

<span data-ttu-id="8df29-295">In diesem Beispiel wird das Ablaufdatum des angegebenen Block-URL-Eintrags geändert.</span><span class="sxs-lookup"><span data-stu-id="8df29-295">This example changes the expiration date of the specified block URL entry.</span></span>

```powershell
Set-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSRAAAA" -ExpirationDate "5/30/2020"
```

<span data-ttu-id="8df29-296">Ausführliche Informationen zu Syntax und Parametern finden Sie unter ["Set-TenantAllowBlockListItems".](/powershell/module/exchange/set-tenantallowblocklistitems)</span><span class="sxs-lookup"><span data-stu-id="8df29-296">For detailed syntax and parameter information, see [Set-TenantAllowBlockListItems](/powershell/module/exchange/set-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-modify-allow-or-block-spoofed-sender-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="8df29-297">Verwenden von PowerShell zum Ändern oder Blockieren von Spoofing-Absendereinträgen in der Mandanten-Zulassungs-/Sperrliste</span><span class="sxs-lookup"><span data-stu-id="8df29-297">Use PowerShell to modify allow or block spoofed sender entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="8df29-298">Verwenden Sie die folgende Syntax, um spoofierte Absendereinträge in der Mandanten-Zulassungs-/Sperrliste zu ändern oder zu blockieren:</span><span class="sxs-lookup"><span data-stu-id="8df29-298">To modify allow or block spoofed sender entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Set-TenantAllowBlockListSpoofItems -Ids <"Id1","Id2",..."IdN"> -Action <Allow | Block>
```

<span data-ttu-id="8df29-299">In diesem Beispiel wird der Spoofing-Absendereintrag von "Blockieren zulassen" geändert.</span><span class="sxs-lookup"><span data-stu-id="8df29-299">This example changes spoofed sender entry from allow to block.</span></span>

```powershell
Set-TenantAllowBlockListItems -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSRAAAA" -Action Block
```

<span data-ttu-id="8df29-300">Ausführliche Informationen zu Syntax und Parametern finden Sie unter ["Set-TenantAllowBlockListSpoofItems".](/powershell/module/exchange/set-tenantallowblocklistspoofitems)</span><span class="sxs-lookup"><span data-stu-id="8df29-300">For detailed syntax and parameter information, see [Set-TenantAllowBlockListSpoofItems](/powershell/module/exchange/set-tenantallowblocklistspoofitems).</span></span>

### <a name="use-powershell-to-remove-url-or-file-entries-from-the-tenant-allowblock-list"></a><span data-ttu-id="8df29-301">Verwenden von PowerShell zum Entfernen von URL- oder Dateieinträgen aus der Mandanten-Zulassungs-/Sperrliste</span><span class="sxs-lookup"><span data-stu-id="8df29-301">Use PowerShell to remove URL or file entries from the Tenant Allow/Block List</span></span>

<span data-ttu-id="8df29-302">Verwenden Sie die folgende Syntax, um Datei- und URL-Einträge aus der Mandanten-Zulassungs-/Sperrliste zu entfernen:</span><span class="sxs-lookup"><span data-stu-id="8df29-302">To remove file and URL entries from the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Remove-TenantAllowBlockListItems -ListType <FileHash | Url> -Ids <"Id1","Id2",..."IdN">
```

<span data-ttu-id="8df29-303">In diesem Beispiel wird der angegebene Block-URL-Eintrag aus der Mandanten-Zulassungs-/Sperrliste entfernt.</span><span class="sxs-lookup"><span data-stu-id="8df29-303">This example removes the specified block URL entry from the Tenant Allow/Block List.</span></span>

```powershell
Remove-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSPAAAA0"
```

<span data-ttu-id="8df29-304">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Remove-TenantAllowBlockListItems](/powershell/module/exchange/remove-tenantallowblocklistitems).</span><span class="sxs-lookup"><span data-stu-id="8df29-304">For detailed syntax and parameter information, see [Remove-TenantAllowBlockListItems](/powershell/module/exchange/remove-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-remove-allow-or-block-spoofed-sender-entries-from-the-tenant-allowblock-list"></a><span data-ttu-id="8df29-305">Verwenden von PowerShell zum Entfernen von Spoofing-Absendereinträgen aus der Mandanten-Zulassungs-/Sperrliste</span><span class="sxs-lookup"><span data-stu-id="8df29-305">Use PowerShell to remove allow or block spoofed sender entries from the Tenant Allow/Block List</span></span>

<span data-ttu-id="8df29-306">Verwenden Sie die folgende Syntax, um Spoofing von Absendereinträgen aus der Mandanten-Zulassungs-/Sperrliste zu entfernen oder zu blockieren:</span><span class="sxs-lookup"><span data-stu-id="8df29-306">To remove allow or block spoof sender entries from the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Remove-TenantAllowBlockListSpoofItems -Ids <"Id1","Id2",..."IdN">
```

<span data-ttu-id="8df29-307">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Remove-TenantAllowBlockListSpoofItems](/powershell/module/exchange/remove-tenantallowblocklistspoofitems).</span><span class="sxs-lookup"><span data-stu-id="8df29-307">For detailed syntax and parameter information, see [Remove-TenantAllowBlockListSpoofItems](/powershell/module/exchange/remove-tenantallowblocklistspoofitems).</span></span>

## <a name="url-syntax-for-the-tenant-allowblock-list"></a><span data-ttu-id="8df29-308">URL-Syntax für die Mandanten-Zulassungs-/Sperrliste</span><span class="sxs-lookup"><span data-stu-id="8df29-308">URL syntax for the Tenant Allow/Block List</span></span>

- <span data-ttu-id="8df29-309">IP4v- und IPv6-Adressen sind zulässig, TCP/UDP-Ports jedoch nicht.</span><span class="sxs-lookup"><span data-stu-id="8df29-309">IP4v and IPv6 addresses are allowed, but TCP/UDP ports are not.</span></span>

- <span data-ttu-id="8df29-310">Dateinamenerweiterungen sind nicht zulässig (z. B. test.pdf).</span><span class="sxs-lookup"><span data-stu-id="8df29-310">Filename extensions are not allowed (for example, test.pdf).</span></span>

- <span data-ttu-id="8df29-311">Unicode wird nicht unterstützt, Punycode jedoch.</span><span class="sxs-lookup"><span data-stu-id="8df29-311">Unicode is not supported, but Punycode is.</span></span>

- <span data-ttu-id="8df29-312">Hostnamen sind zulässig, wenn alle folgenden Anweisungen wahr sind:</span><span class="sxs-lookup"><span data-stu-id="8df29-312">Hostnames are allowed if all of the following statements are true:</span></span>
  - <span data-ttu-id="8df29-313">Der Hostname enthält einen Punkt.</span><span class="sxs-lookup"><span data-stu-id="8df29-313">The hostname contains a period.</span></span>
  - <span data-ttu-id="8df29-314">Links vom Punkt befindet sich mindestens ein Zeichen.</span><span class="sxs-lookup"><span data-stu-id="8df29-314">There is at least one character to the left of the period.</span></span>
  - <span data-ttu-id="8df29-315">Rechts neben dem Punkt befinden sich mindestens zwei Zeichen.</span><span class="sxs-lookup"><span data-stu-id="8df29-315">There are at least two characters to the right of the period.</span></span>

  <span data-ttu-id="8df29-316">Ist beispielsweise `t.co` zulässig `.com` oder nicht `contoso.` zulässig.</span><span class="sxs-lookup"><span data-stu-id="8df29-316">For example, `t.co` is allowed; `.com` or `contoso.` are not allowed.</span></span>

- <span data-ttu-id="8df29-317">Unterpfade werden nicht impliziert.</span><span class="sxs-lookup"><span data-stu-id="8df29-317">Subpaths are not implied.</span></span>

  <span data-ttu-id="8df29-318">Enthält z. B. `contoso.com` nicht `contoso.com/a` .</span><span class="sxs-lookup"><span data-stu-id="8df29-318">For example, `contoso.com` does not include `contoso.com/a`.</span></span>

- <span data-ttu-id="8df29-319">Platzhalter (\*) sind in den folgenden Szenarien zulässig:</span><span class="sxs-lookup"><span data-stu-id="8df29-319">Wildcards (\*) are allowed in the following scenarios:</span></span>

  - <span data-ttu-id="8df29-320">Auf einen linken Platzhalter muss ein Punkt folgen, um eine Unterdomäne anzugeben.</span><span class="sxs-lookup"><span data-stu-id="8df29-320">A left wildcard must be followed by a period to specify a subdomain.</span></span>

    <span data-ttu-id="8df29-321">Ist beispielsweise `*.contoso.com` zulässig; `*contoso.com` ist nicht zulässig.</span><span class="sxs-lookup"><span data-stu-id="8df29-321">For example, `*.contoso.com` is allowed; `*contoso.com` is not allowed.</span></span>

  - <span data-ttu-id="8df29-322">Ein rechter Platzhalter muss einem Schrägstrich (/) folgen, um einen Pfad anzugeben.</span><span class="sxs-lookup"><span data-stu-id="8df29-322">A right wildcard must follow a forward slash (/) to specify a path.</span></span>

    <span data-ttu-id="8df29-323">Ist beispielsweise `contoso.com/*` zulässig `contoso.com*` oder nicht `contoso.com/ab*` zulässig.</span><span class="sxs-lookup"><span data-stu-id="8df29-323">For example, `contoso.com/*` is allowed; `contoso.com*` or `contoso.com/ab*` are not allowed.</span></span>

  - <span data-ttu-id="8df29-324">Alle Unterpfade werden nicht durch einen rechten Platzhalter impliziert.</span><span class="sxs-lookup"><span data-stu-id="8df29-324">All subpaths are not implied by a right wildcard.</span></span>

    <span data-ttu-id="8df29-325">Enthält z. B. `contoso.com/*` nicht `contoso.com/a` .</span><span class="sxs-lookup"><span data-stu-id="8df29-325">For example, `contoso.com/*` does not include `contoso.com/a`.</span></span>

  - <span data-ttu-id="8df29-326">`*.com*` ungültig ist (keine auflösbare Domäne, und der rechte Platzhalter folgt keinem Schrägstrich).</span><span class="sxs-lookup"><span data-stu-id="8df29-326">`*.com*` is invalid (not a resolvable domain and the right wildcard does not follow a forward slash).</span></span>

  - <span data-ttu-id="8df29-327">Platzhalter sind in IP-Adressen nicht zulässig.</span><span class="sxs-lookup"><span data-stu-id="8df29-327">Wildcards are not allowed in IP addresses.</span></span>

- <span data-ttu-id="8df29-328">Das Tildezeichen (~) ist in den folgenden Szenarien verfügbar:</span><span class="sxs-lookup"><span data-stu-id="8df29-328">The tilde (~) character is available in the following scenarios:</span></span>

  - <span data-ttu-id="8df29-329">Eine linke Tilde impliziert eine Domäne und alle Unterdomänen.</span><span class="sxs-lookup"><span data-stu-id="8df29-329">A left tilde implies a domain and all subdomains.</span></span>

    <span data-ttu-id="8df29-330">Beispiel: `~contoso.com` "includes" `contoso.com` und `*.contoso.com` ".</span><span class="sxs-lookup"><span data-stu-id="8df29-330">For example `~contoso.com` includes `contoso.com` and `*.contoso.com`.</span></span>

- <span data-ttu-id="8df29-331">URL-Einträge, die Protokolle enthalten (z. B. `http://` , oder ) schlagen `https://` `ftp://` fehl, da URL-Einträge für alle Protokolle gelten.</span><span class="sxs-lookup"><span data-stu-id="8df29-331">URL entries that contain protocols (for example, `http://`, `https://`, or `ftp://`) will fail, because URL entries apply to all protocols.</span></span>

- <span data-ttu-id="8df29-332">Ein Benutzername oder Kennwort wird nicht unterstützt oder ist nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="8df29-332">A username or password aren't supported or required.</span></span>

- <span data-ttu-id="8df29-333">Anführungszeichen (' oder ") sind ungültige Zeichen.</span><span class="sxs-lookup"><span data-stu-id="8df29-333">Quotes (' or ") are invalid characters.</span></span>

- <span data-ttu-id="8df29-334">Eine URL sollte nach Möglichkeit alle Umleitungen enthalten.</span><span class="sxs-lookup"><span data-stu-id="8df29-334">A URL should include all redirects where possible.</span></span>

### <a name="url-entry-scenarios"></a><span data-ttu-id="8df29-335">URL-Eintragsszenarien</span><span class="sxs-lookup"><span data-stu-id="8df29-335">URL entry scenarios</span></span>

<span data-ttu-id="8df29-336">Gültige URL-Einträge und deren Ergebnisse werden in den folgenden Abschnitten beschrieben.</span><span class="sxs-lookup"><span data-stu-id="8df29-336">Valid URL entries and their results are described in the following sections.</span></span>

#### <a name="scenario-no-wildcards"></a><span data-ttu-id="8df29-337">Szenario: Keine Platzhalter</span><span class="sxs-lookup"><span data-stu-id="8df29-337">Scenario: No wildcards</span></span>

<span data-ttu-id="8df29-338">**Eintrag**: `contoso.com`</span><span class="sxs-lookup"><span data-stu-id="8df29-338">**Entry**: `contoso.com`</span></span>

- <span data-ttu-id="8df29-339">**Übereinstimmung zulassen:** contoso.com</span><span class="sxs-lookup"><span data-stu-id="8df29-339">**Allow match**: contoso.com</span></span>

- <span data-ttu-id="8df29-340">**Nicht übereinstimmend zulassen:**</span><span class="sxs-lookup"><span data-stu-id="8df29-340">**Allow not matched**:</span></span>

  - <span data-ttu-id="8df29-341">abc-contoso.com</span><span class="sxs-lookup"><span data-stu-id="8df29-341">abc-contoso.com</span></span>
  - <span data-ttu-id="8df29-342">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="8df29-342">contoso.com/a</span></span>
  - <span data-ttu-id="8df29-343">payroll.contoso.com</span><span class="sxs-lookup"><span data-stu-id="8df29-343">payroll.contoso.com</span></span>
  - <span data-ttu-id="8df29-344">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="8df29-344">test.com/contoso.com</span></span>
  - <span data-ttu-id="8df29-345">test.com/q=contoso.com</span><span class="sxs-lookup"><span data-stu-id="8df29-345">test.com/q=contoso.com</span></span>
  - <span data-ttu-id="8df29-346">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="8df29-346">www.contoso.com</span></span>
  - <span data-ttu-id="8df29-347">www.contoso.com/q=a@contoso.com</span><span class="sxs-lookup"><span data-stu-id="8df29-347">www.contoso.com/q=a@contoso.com</span></span>

- <span data-ttu-id="8df29-348">**Blocküberstimmung:**</span><span class="sxs-lookup"><span data-stu-id="8df29-348">**Block match**:</span></span>

  - <span data-ttu-id="8df29-349">contoso.com</span><span class="sxs-lookup"><span data-stu-id="8df29-349">contoso.com</span></span>
  - <span data-ttu-id="8df29-350">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="8df29-350">contoso.com/a</span></span>
  - <span data-ttu-id="8df29-351">payroll.contoso.com</span><span class="sxs-lookup"><span data-stu-id="8df29-351">payroll.contoso.com</span></span>
  - <span data-ttu-id="8df29-352">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="8df29-352">test.com/contoso.com</span></span>
  - <span data-ttu-id="8df29-353">test.com/q=contoso.com</span><span class="sxs-lookup"><span data-stu-id="8df29-353">test.com/q=contoso.com</span></span>
  - <span data-ttu-id="8df29-354">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="8df29-354">www.contoso.com</span></span>
  - <span data-ttu-id="8df29-355">www.contoso.com/q=a@contoso.com</span><span class="sxs-lookup"><span data-stu-id="8df29-355">www.contoso.com/q=a@contoso.com</span></span>

- <span data-ttu-id="8df29-356">**Block nicht abgeglichen:** abc-contoso.com</span><span class="sxs-lookup"><span data-stu-id="8df29-356">**Block not matched**: abc-contoso.com</span></span>

#### <a name="scenario-left-wildcard-subdomain"></a><span data-ttu-id="8df29-357">Szenario: Linker Platzhalter (Unterdomäne)</span><span class="sxs-lookup"><span data-stu-id="8df29-357">Scenario: Left wildcard (subdomain)</span></span>

<span data-ttu-id="8df29-358">**Eintrag**: `*.contoso.com`</span><span class="sxs-lookup"><span data-stu-id="8df29-358">**Entry**: `*.contoso.com`</span></span>

- <span data-ttu-id="8df29-359">**Übereinstimmung zulassen** und **Übereinstimmung blockieren:**</span><span class="sxs-lookup"><span data-stu-id="8df29-359">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="8df29-360">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="8df29-360">www.contoso.com</span></span>
  - <span data-ttu-id="8df29-361">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="8df29-361">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="8df29-362">**Nicht übereinstimmende** und **nicht übereinstimmende Blockierung** zulassen:</span><span class="sxs-lookup"><span data-stu-id="8df29-362">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="8df29-363">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="8df29-363">123contoso.com</span></span>
  - <span data-ttu-id="8df29-364">contoso.com</span><span class="sxs-lookup"><span data-stu-id="8df29-364">contoso.com</span></span>
  - <span data-ttu-id="8df29-365">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="8df29-365">test.com/contoso.com</span></span>
  - <span data-ttu-id="8df29-366">www.contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="8df29-366">www.contoso.com/abc</span></span>

#### <a name="scenario-right-wildcard-at-top-of-path"></a><span data-ttu-id="8df29-367">Szenario: Rechter Platzhalter oben im Pfad</span><span class="sxs-lookup"><span data-stu-id="8df29-367">Scenario: Right wildcard at top of path</span></span>

<span data-ttu-id="8df29-368">**Eintrag**: `contoso.com/a/*`</span><span class="sxs-lookup"><span data-stu-id="8df29-368">**Entry**: `contoso.com/a/*`</span></span>

- <span data-ttu-id="8df29-369">**Übereinstimmung zulassen** und **Übereinstimmung blockieren:**</span><span class="sxs-lookup"><span data-stu-id="8df29-369">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="8df29-370">contoso.com/a/b</span><span class="sxs-lookup"><span data-stu-id="8df29-370">contoso.com/a/b</span></span>
  - <span data-ttu-id="8df29-371">contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="8df29-371">contoso.com/a/b/c</span></span>
  - <span data-ttu-id="8df29-372">contoso.com/a/?q=joe@t.com</span><span class="sxs-lookup"><span data-stu-id="8df29-372">contoso.com/a/?q=joe@t.com</span></span>

- <span data-ttu-id="8df29-373">**Nicht übereinstimmende** und **nicht übereinstimmende Blockierung** zulassen:</span><span class="sxs-lookup"><span data-stu-id="8df29-373">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="8df29-374">contoso.com</span><span class="sxs-lookup"><span data-stu-id="8df29-374">contoso.com</span></span>
  - <span data-ttu-id="8df29-375">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="8df29-375">contoso.com/a</span></span>
  - <span data-ttu-id="8df29-376">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="8df29-376">www.contoso.com</span></span>
  - <span data-ttu-id="8df29-377">www.contoso.com/q=a@contoso.com</span><span class="sxs-lookup"><span data-stu-id="8df29-377">www.contoso.com/q=a@contoso.com</span></span>

#### <a name="scenario-left-tilde"></a><span data-ttu-id="8df29-378">Szenario: Linke Tilde</span><span class="sxs-lookup"><span data-stu-id="8df29-378">Scenario: Left tilde</span></span>

<span data-ttu-id="8df29-379">**Eintrag**: `~contoso.com`</span><span class="sxs-lookup"><span data-stu-id="8df29-379">**Entry**: `~contoso.com`</span></span>

- <span data-ttu-id="8df29-380">**Übereinstimmung zulassen** und **Übereinstimmung blockieren:**</span><span class="sxs-lookup"><span data-stu-id="8df29-380">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="8df29-381">contoso.com</span><span class="sxs-lookup"><span data-stu-id="8df29-381">contoso.com</span></span>
  - <span data-ttu-id="8df29-382">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="8df29-382">www.contoso.com</span></span>
  - <span data-ttu-id="8df29-383">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="8df29-383">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="8df29-384">**Nicht übereinstimmende** und **nicht übereinstimmende Blockierung** zulassen:</span><span class="sxs-lookup"><span data-stu-id="8df29-384">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="8df29-385">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="8df29-385">123contoso.com</span></span>
  - <span data-ttu-id="8df29-386">contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="8df29-386">contoso.com/abc</span></span>
  - <span data-ttu-id="8df29-387">www.contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="8df29-387">www.contoso.com/abc</span></span>

#### <a name="scenario-right-wildcard-suffix"></a><span data-ttu-id="8df29-388">Szenario: Rechtes Platzhaltersuffix</span><span class="sxs-lookup"><span data-stu-id="8df29-388">Scenario: Right wildcard suffix</span></span>

<span data-ttu-id="8df29-389">**Eintrag**: `contoso.com/*`</span><span class="sxs-lookup"><span data-stu-id="8df29-389">**Entry**: `contoso.com/*`</span></span>

- <span data-ttu-id="8df29-390">**Übereinstimmung zulassen** und **Übereinstimmung blockieren:**</span><span class="sxs-lookup"><span data-stu-id="8df29-390">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="8df29-391">contoso.com/?q=whatever@fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="8df29-391">contoso.com/?q=whatever@fabrikam.com</span></span>
  - <span data-ttu-id="8df29-392">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="8df29-392">contoso.com/a</span></span>
  - <span data-ttu-id="8df29-393">contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="8df29-393">contoso.com/a/b/c</span></span>
  - <span data-ttu-id="8df29-394">contoso.com/ab</span><span class="sxs-lookup"><span data-stu-id="8df29-394">contoso.com/ab</span></span>
  - <span data-ttu-id="8df29-395">contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="8df29-395">contoso.com/b</span></span>
  - <span data-ttu-id="8df29-396">contoso.com/b/a/c</span><span class="sxs-lookup"><span data-stu-id="8df29-396">contoso.com/b/a/c</span></span>
  - <span data-ttu-id="8df29-397">contoso.com/ba</span><span class="sxs-lookup"><span data-stu-id="8df29-397">contoso.com/ba</span></span>

- <span data-ttu-id="8df29-398">**Nicht übereinstimmende** und **nicht übereinstimmende Blockierung** zulassen: contoso.com</span><span class="sxs-lookup"><span data-stu-id="8df29-398">**Allow not matched** and **Block not matched**: contoso.com</span></span>

#### <a name="scenario-left-wildcard-subdomain-and-right-wildcard-suffix"></a><span data-ttu-id="8df29-399">Szenario: Linke Platzhalterunterdomäne und rechtes Platzhaltersuffix</span><span class="sxs-lookup"><span data-stu-id="8df29-399">Scenario: Left wildcard subdomain and right wildcard suffix</span></span>

<span data-ttu-id="8df29-400">**Eintrag**: `*.contoso.com/*`</span><span class="sxs-lookup"><span data-stu-id="8df29-400">**Entry**: `*.contoso.com/*`</span></span>

- <span data-ttu-id="8df29-401">**Übereinstimmung zulassen** und **Übereinstimmung blockieren:**</span><span class="sxs-lookup"><span data-stu-id="8df29-401">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="8df29-402">abc.contoso.com/ab</span><span class="sxs-lookup"><span data-stu-id="8df29-402">abc.contoso.com/ab</span></span>
  - <span data-ttu-id="8df29-403">abc.xyz.contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="8df29-403">abc.xyz.contoso.com/a/b/c</span></span>
  - <span data-ttu-id="8df29-404">www.contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="8df29-404">www.contoso.com/a</span></span>
  - <span data-ttu-id="8df29-405">www.contoso.com/b/a/c</span><span class="sxs-lookup"><span data-stu-id="8df29-405">www.contoso.com/b/a/c</span></span>
  - <span data-ttu-id="8df29-406">xyz.contoso.com/ba</span><span class="sxs-lookup"><span data-stu-id="8df29-406">xyz.contoso.com/ba</span></span>

- <span data-ttu-id="8df29-407">**Nicht übereinstimmende** und **nicht übereinstimmende Blockierung** zulassen: contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="8df29-407">**Allow not matched** and **Block not matched**: contoso.com/b</span></span>

#### <a name="scenario-left-and-right-tilde"></a><span data-ttu-id="8df29-408">Szenario: Linke und rechte Tilde</span><span class="sxs-lookup"><span data-stu-id="8df29-408">Scenario: Left and right tilde</span></span>

<span data-ttu-id="8df29-409">**Eintrag**: `~contoso.com~`</span><span class="sxs-lookup"><span data-stu-id="8df29-409">**Entry**: `~contoso.com~`</span></span>

- <span data-ttu-id="8df29-410">**Übereinstimmung zulassen** und **Übereinstimmung blockieren:**</span><span class="sxs-lookup"><span data-stu-id="8df29-410">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="8df29-411">contoso.com</span><span class="sxs-lookup"><span data-stu-id="8df29-411">contoso.com</span></span>
  - <span data-ttu-id="8df29-412">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="8df29-412">contoso.com/a</span></span>
  - <span data-ttu-id="8df29-413">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="8df29-413">www.contoso.com</span></span>
  - <span data-ttu-id="8df29-414">www.contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="8df29-414">www.contoso.com/b</span></span>
  - <span data-ttu-id="8df29-415">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="8df29-415">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="8df29-416">**Nicht übereinstimmende** und **nicht übereinstimmende Blockierung** zulassen:</span><span class="sxs-lookup"><span data-stu-id="8df29-416">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="8df29-417">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="8df29-417">123contoso.com</span></span>
  - <span data-ttu-id="8df29-418">contoso.org</span><span class="sxs-lookup"><span data-stu-id="8df29-418">contoso.org</span></span>

#### <a name="scenario-ip-address"></a><span data-ttu-id="8df29-419">Szenario: IP-Adresse</span><span class="sxs-lookup"><span data-stu-id="8df29-419">Scenario: IP address</span></span>

<span data-ttu-id="8df29-420">**Eintrag**: `1.2.3.4`</span><span class="sxs-lookup"><span data-stu-id="8df29-420">**Entry**: `1.2.3.4`</span></span>

- <span data-ttu-id="8df29-421">**Übereinstimmung zulassen** und **Übereinstimmung blockieren:** 1.2.3.4</span><span class="sxs-lookup"><span data-stu-id="8df29-421">**Allow match** and **Block match**: 1.2.3.4</span></span>

- <span data-ttu-id="8df29-422">**Nicht übereinstimmende** und **nicht übereinstimmende Blockierung** zulassen:</span><span class="sxs-lookup"><span data-stu-id="8df29-422">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="8df29-423">1.2.3.4/a</span><span class="sxs-lookup"><span data-stu-id="8df29-423">1.2.3.4/a</span></span>
  - <span data-ttu-id="8df29-424">11.2.3.4/a</span><span class="sxs-lookup"><span data-stu-id="8df29-424">11.2.3.4/a</span></span>

#### <a name="ip-address-with-right-wildcard"></a><span data-ttu-id="8df29-425">IP-Adresse mit rechtem Platzhalter</span><span class="sxs-lookup"><span data-stu-id="8df29-425">IP address with right wildcard</span></span>

<span data-ttu-id="8df29-426">**Eintrag**: `1.2.3.4/*`</span><span class="sxs-lookup"><span data-stu-id="8df29-426">**Entry**: `1.2.3.4/*`</span></span>

- <span data-ttu-id="8df29-427">**Übereinstimmung zulassen** und **Übereinstimmung blockieren:**</span><span class="sxs-lookup"><span data-stu-id="8df29-427">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="8df29-428">1.2.3.4/b</span><span class="sxs-lookup"><span data-stu-id="8df29-428">1.2.3.4/b</span></span>
  - <span data-ttu-id="8df29-429">1.2.3.4/baaaa</span><span class="sxs-lookup"><span data-stu-id="8df29-429">1.2.3.4/baaaa</span></span>

### <a name="examples-of-invalid-entries"></a><span data-ttu-id="8df29-430">Beispiele für ungültige Einträge</span><span class="sxs-lookup"><span data-stu-id="8df29-430">Examples of invalid entries</span></span>

<span data-ttu-id="8df29-431">Die folgenden Einträge sind ungültig:</span><span class="sxs-lookup"><span data-stu-id="8df29-431">The following entries are invalid:</span></span>

- <span data-ttu-id="8df29-432">**Fehlende oder ungültige Domänenwerte:**</span><span class="sxs-lookup"><span data-stu-id="8df29-432">**Missing or invalid domain values**:</span></span>

  - <span data-ttu-id="8df29-433">Contoso</span><span class="sxs-lookup"><span data-stu-id="8df29-433">contoso</span></span>
  - <span data-ttu-id="8df29-434">\*.contoso.\*</span><span class="sxs-lookup"><span data-stu-id="8df29-434">\*.contoso.\*</span></span>
  - <span data-ttu-id="8df29-435">\*.com</span><span class="sxs-lookup"><span data-stu-id="8df29-435">\*.com</span></span>
  - <span data-ttu-id="8df29-436">\*.pdf</span><span class="sxs-lookup"><span data-stu-id="8df29-436">\*.pdf</span></span>

- <span data-ttu-id="8df29-437">**Platzhalter für Text oder ohne Leerzeichen:**</span><span class="sxs-lookup"><span data-stu-id="8df29-437">**Wildcard on text or without spacing characters**:</span></span>

  - <span data-ttu-id="8df29-438">\*contoso.com</span><span class="sxs-lookup"><span data-stu-id="8df29-438">\*contoso.com</span></span>
  - <span data-ttu-id="8df29-439">contoso.com\*</span><span class="sxs-lookup"><span data-stu-id="8df29-439">contoso.com\*</span></span>
  - <span data-ttu-id="8df29-440">\*1.2.3.4</span><span class="sxs-lookup"><span data-stu-id="8df29-440">\*1.2.3.4</span></span>
  - <span data-ttu-id="8df29-441">1.2.3.4\*</span><span class="sxs-lookup"><span data-stu-id="8df29-441">1.2.3.4\*</span></span>
  - <span data-ttu-id="8df29-442">contoso.com/a\*</span><span class="sxs-lookup"><span data-stu-id="8df29-442">contoso.com/a\*</span></span>
  - <span data-ttu-id="8df29-443">contoso.com/ab\*</span><span class="sxs-lookup"><span data-stu-id="8df29-443">contoso.com/ab\*</span></span>

- <span data-ttu-id="8df29-444">**IP-Adressen mit Ports:**</span><span class="sxs-lookup"><span data-stu-id="8df29-444">**IP addresses with ports**:</span></span>

  - <span data-ttu-id="8df29-445">contoso.com:443</span><span class="sxs-lookup"><span data-stu-id="8df29-445">contoso.com:443</span></span>
  - <span data-ttu-id="8df29-446">abc.contoso.com:25</span><span class="sxs-lookup"><span data-stu-id="8df29-446">abc.contoso.com:25</span></span>

- <span data-ttu-id="8df29-447">**Nicht beschreibende Platzhalter:**</span><span class="sxs-lookup"><span data-stu-id="8df29-447">**Non-descriptive wildcards**:</span></span>

  - \*
  - <span data-ttu-id="8df29-448">\*.\*</span><span class="sxs-lookup"><span data-stu-id="8df29-448">\*.\*</span></span>

- <span data-ttu-id="8df29-449">**Mittlere Platzhalter:**</span><span class="sxs-lookup"><span data-stu-id="8df29-449">**Middle wildcards**:</span></span>

  - <span data-ttu-id="8df29-450">conto \* so.com</span><span class="sxs-lookup"><span data-stu-id="8df29-450">conto\*so.com</span></span>
  - <span data-ttu-id="8df29-451">conto~so.com</span><span class="sxs-lookup"><span data-stu-id="8df29-451">conto~so.com</span></span>

- <span data-ttu-id="8df29-452">**Doppelte Platzhalter**</span><span class="sxs-lookup"><span data-stu-id="8df29-452">**Double wildcards**</span></span>

  - <span data-ttu-id="8df29-453">contoso.com/\*\*</span><span class="sxs-lookup"><span data-stu-id="8df29-453">contoso.com/\*\*</span></span>
  - <span data-ttu-id="8df29-454">contoso.com/\*/\*</span><span class="sxs-lookup"><span data-stu-id="8df29-454">contoso.com/\*/\*</span></span>

## <a name="domain-pair-syntax-for-spoofed-sender-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="8df29-455">Domänenpaarsyntax für gefälschte Absendereinträge in der Mandanten-Zulassungs-/Sperrliste</span><span class="sxs-lookup"><span data-stu-id="8df29-455">Domain pair syntax for spoofed sender entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="8df29-456">Ein Domänenpaar für einen gefälschten Absender in der Mandanten-Zulassungs-/Sperrliste verwendet die folgende Syntax: `<Spoofed user>, <Sending infrastructure>` .</span><span class="sxs-lookup"><span data-stu-id="8df29-456">A domain pair for a spoofed sender in the Tenant Allow/Block List uses the following syntax: `<Spoofed user>, <Sending infrastructure>`.</span></span>

- <span data-ttu-id="8df29-457">**Gefälschter Benutzer:** Dieser Wert bezieht sich auf die E-Mail-Adresse des gefälschten Benutzers, der im **Feld "Von"** in E-Mail-Clients angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="8df29-457">**Spoofed user**: This value involves the email address of the spoofed user that's displayed in the **From** box in email clients.</span></span> <span data-ttu-id="8df29-458">Diese Adresse wird auch als `5322.From` Adresse bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="8df29-458">This address is also known as the `5322.From` address.</span></span> <span data-ttu-id="8df29-459">Gültige Werte sind:</span><span class="sxs-lookup"><span data-stu-id="8df29-459">Valid values include:</span></span>
  - <span data-ttu-id="8df29-460">Eine einzelne E-Mail-Adresse (z. B. chris@contoso.com).</span><span class="sxs-lookup"><span data-stu-id="8df29-460">An individual email address (for example, chris@contoso.com).</span></span>
  - <span data-ttu-id="8df29-461">Eine E-Mail-Domäne (z. B. contoso.com).</span><span class="sxs-lookup"><span data-stu-id="8df29-461">An email domain (for example, contoso.com).</span></span>
  - <span data-ttu-id="8df29-462">Das Platzhalterzeichen (z. B. \* ).</span><span class="sxs-lookup"><span data-stu-id="8df29-462">The wildcard character (for example, \*).</span></span>

- <span data-ttu-id="8df29-463">Senden der **Infrastruktur:** Dieser Wert gibt die Quelle von Nachrichten des gefälschten Benutzers an.</span><span class="sxs-lookup"><span data-stu-id="8df29-463">**Sending infrastructure**: This value indicates the source of messages from the spoofed user.</span></span> <span data-ttu-id="8df29-464">Gültige Werte sind:</span><span class="sxs-lookup"><span data-stu-id="8df29-464">Valid values include:</span></span>
  - <span data-ttu-id="8df29-465">Die Domäne in einer reversen DNS-Suche (PTR-Eintrag) der IP-Adresse des Quell-E-Mail-Servers (z. B. fabrikam.com).</span><span class="sxs-lookup"><span data-stu-id="8df29-465">The domain found in a reverse DNS lookup (PTR record) of the source email server's IP address (for example, fabrikam.com).</span></span>
  - <span data-ttu-id="8df29-466">Wenn die Quell-IP-Adresse keinen PTR-Eintrag aufweist, wird die sendende Infrastruktur als \<source IP\> /24 identifiziert (z. B. 192.168.100.100/24).</span><span class="sxs-lookup"><span data-stu-id="8df29-466">If the source IP address has no PTR record, then the sending infrastructure is identified as \<source IP\>/24 (for example, 192.168.100.100/24).</span></span>

<span data-ttu-id="8df29-467">Hier sind einige Beispiele für gültige Domänenpaare zum Identifizieren von gefälschten Absendern:</span><span class="sxs-lookup"><span data-stu-id="8df29-467">Here are some examples of valid domain pairs to identify spoofed senders:</span></span>

- `contoso.com, 192.168.100.100/24`
- `chris@contoso.com, fabrikam.com`
- `*, contoso.net`

<span data-ttu-id="8df29-468">Die maximale Anzahl von gefälschten Absendereinträgen beträgt 1000.</span><span class="sxs-lookup"><span data-stu-id="8df29-468">The maximum number of spoofed sender entries is 1000.</span></span> 

<span data-ttu-id="8df29-469">Das Hinzufügen eines Domänenpaars erlaubt oder blockiert nur die *Kombination aus* dem gefälschten Benutzer *und* der sendenden Infrastruktur.</span><span class="sxs-lookup"><span data-stu-id="8df29-469">Adding a domain pair only allows or blocks the *combination* of the spoofed user *and* the sending infrastructure.</span></span> <span data-ttu-id="8df29-470">Es erlaubt weder E-Mails vom gefälschten Benutzer aus einer Quelle noch E-Mails aus der sendenden Infrastrukturquelle für spoofierte Benutzer.</span><span class="sxs-lookup"><span data-stu-id="8df29-470">It does not allow email from the spoofed user from any source, nor does it allow email from the sending infrastructure source for any spoofed user.</span></span> 

<span data-ttu-id="8df29-471">Beispielsweise fügen Sie einen Zulassungseintrag für das folgende Domänenpaar hinzu:</span><span class="sxs-lookup"><span data-stu-id="8df29-471">For example, you add an allow entry for the following domain pair:</span></span>

- <span data-ttu-id="8df29-472">**Domäne:** gmail.com</span><span class="sxs-lookup"><span data-stu-id="8df29-472">**Domain**: gmail.com</span></span>
- <span data-ttu-id="8df29-473">**Infrastruktur:** tms.mx.com</span><span class="sxs-lookup"><span data-stu-id="8df29-473">**Infrastructure**: tms.mx.com</span></span>

<span data-ttu-id="8df29-474">Nur Nachrichten aus dieser Domäne *und* dem sendenden Infrastrukturpaar dürfen Spoofing ausführen.</span><span class="sxs-lookup"><span data-stu-id="8df29-474">Only messages from that domain *and* sending infrastructure pair are allowed to spoof.</span></span> <span data-ttu-id="8df29-475">Andere Absender, die versuchen, gmail.com zu spoofen, sind nicht zulässig.</span><span class="sxs-lookup"><span data-stu-id="8df29-475">Other senders attempting to spoof gmail.com aren't allowed.</span></span> <span data-ttu-id="8df29-476">Nachrichten von Absendern in anderen Domänen, die von tms.mx.com stammen, werden durch Spoofintelligenz überprüft.</span><span class="sxs-lookup"><span data-stu-id="8df29-476">Messages from senders in other domains originating from tms.mx.com are checked by spoof intelligence.</span></span>
