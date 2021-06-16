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
ms.openlocfilehash: 4228bb8abb70bbd96605a7d0f021a1a483e8715c
ms.sourcegitcommit: 3d30ec03628870a22c54b6ec5d865cbe94f34245
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/14/2021
ms.locfileid: "52929731"
---
# <a name="manage-the-tenant-allowblock-list"></a><span data-ttu-id="dc60f-103">Verwalten der Zulassungs-/Sperrliste des Mandanten</span><span class="sxs-lookup"><span data-stu-id="dc60f-103">Manage the Tenant Allow/Block List</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="dc60f-104">**Gilt für**</span><span class="sxs-lookup"><span data-stu-id="dc60f-104">**Applies to**</span></span>
- [<span data-ttu-id="dc60f-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="dc60f-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="dc60f-106">Microsoft Defender für Office 365 Plan 1 und Plan 2</span><span class="sxs-lookup"><span data-stu-id="dc60f-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="dc60f-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="dc60f-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

> [!NOTE]
>
> <span data-ttu-id="dc60f-108">Die in diesem Artikel beschriebenen Features befinden sich in der Vorschau, können geändert werden und sind nicht in allen Organisationen verfügbar.</span><span class="sxs-lookup"><span data-stu-id="dc60f-108">The features described in this article are in Preview, are subject to change, and are not available in all organizations.</span></span>  <span data-ttu-id="dc60f-109">Wenn Ihre Organisation nicht über die in diesem Artikel beschriebenen Spoofingfeatures verfügt, lesen Sie die ältere Spoofverwaltungserfahrung unter [Verwalten von gefälschten Absendern mithilfe der Spoof Intelligence-Richtlinie und des Einblicks in spoofintelligenz in EOP.](walkthrough-spoof-intelligence-insight.md)</span><span class="sxs-lookup"><span data-stu-id="dc60f-109">If your organization does not have the spoof features as described in this article, see the older spoof management experience at [Manage spoofed senders using the spoof intelligence policy and spoof intelligence insight in EOP](walkthrough-spoof-intelligence-insight.md).</span></span>
>
> <span data-ttu-id="dc60f-110">Sie können derzeit keine zulässigen URL- oder Dateielemente in der Mandanten-Zulassungs-/Sperrliste **konfigurieren.**</span><span class="sxs-lookup"><span data-stu-id="dc60f-110">You can't **configure** allowed URL or file items in the Tenant Allow/Block List at this time.</span></span>

<span data-ttu-id="dc60f-111">In Microsoft 365 Organisationen mit Postfächern in Exchange Online oder eigenständigen Exchange Online Protection (EOP)-Organisationen ohne Exchange Online Postfächer, können Sie mit der EOP-Filterbewertung nicht einverstanden sein.</span><span class="sxs-lookup"><span data-stu-id="dc60f-111">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, you might disagree with the EOP filtering verdict.</span></span> <span data-ttu-id="dc60f-112">Beispielsweise kann eine gute Nachricht als falsch markiert werden (ein falsch positives Ergebnis), oder eine ungültige Nachricht kann durchgelassen werden (ein falsch negativer Wert).</span><span class="sxs-lookup"><span data-stu-id="dc60f-112">For example, a good message might be marked as bad (a false positive), or a bad message might be allowed through (a false negative).</span></span>

<span data-ttu-id="dc60f-113">Die Mandanten-Zulassungs-/Sperrliste im Microsoft 365 Defender-Portal bietet Ihnen die Möglichkeit, die Microsoft 365 Filterbewertungen manuell zu überschreiben.</span><span class="sxs-lookup"><span data-stu-id="dc60f-113">The Tenant Allow/Block List in the Microsoft 365 Defender portal gives you a way to manually override the Microsoft 365 filtering verdicts.</span></span> <span data-ttu-id="dc60f-114">Die Mandanten-Zulassungs-/Sperrliste wird während des Nachrichtenflusses und zum Zeitpunkt der Benutzerklicks verwendet.</span><span class="sxs-lookup"><span data-stu-id="dc60f-114">The Tenant Allow/Block List is used during mail flow and at the time of user clicks.</span></span> <span data-ttu-id="dc60f-115">Sie können die folgenden Arten von Außerkraftsetzungen angeben:</span><span class="sxs-lookup"><span data-stu-id="dc60f-115">You can specify the following types of overrides:</span></span>

- <span data-ttu-id="dc60f-116">Zu blockierende URLs.</span><span class="sxs-lookup"><span data-stu-id="dc60f-116">URLs to block.</span></span>
- <span data-ttu-id="dc60f-117">Zu blockierende Dateien.</span><span class="sxs-lookup"><span data-stu-id="dc60f-117">Files to block.</span></span>
- <span data-ttu-id="dc60f-118">Gefälschte Absender, die zugelassen oder blockiert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="dc60f-118">Spoofed senders to allow or block.</span></span> <span data-ttu-id="dc60f-119">Wenn Sie die Zulassungs- oder Blockbewertung im Einblick in die [Spoofintelligenz](learn-about-spoof-intelligence.md)außer Kraft setzen, wird der gefälschte Absender zu einem manuellen Zulassungs- oder Blockierungseintrag, der nur auf der Registerkarte **"Spoofing"** in der Mandanten-Zulassungs-/Sperrliste angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="dc60f-119">If you override the allow or block verdict in the [spoof intelligence insight](learn-about-spoof-intelligence.md), the spoofed sender becomes a manual allow or block entry that only appears on the **Spoof** tab in the Tenant Allow/Block List.</span></span> <span data-ttu-id="dc60f-120">Sie können hier auch manuell Zulassungseinträge für gefälschte Absender erstellen oder blockieren, bevor sie durch Spoofintelligenz erkannt werden.</span><span class="sxs-lookup"><span data-stu-id="dc60f-120">You can also manually create allow or block entries for spoofed senders here before they're detected by spoof intelligence.</span></span>

<span data-ttu-id="dc60f-121">In diesem Artikel wird beschrieben, wie Sie Einträge in der Mandanten-Zulassungs-/Sperrliste im Microsoft 365 Defender-Portal oder in PowerShell (Exchange Online PowerShell für Microsoft 365 Organisationen mit Postfächern in Exchange Online; eigenständige EOP PowerShell für Organisationen ohne Exchange Online Postfächer) konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="dc60f-121">This article describes how to configure entries in the Tenant Allow/Block List in the Microsoft 365 Defender portal or in PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="dc60f-122">Was sollten Sie wissen, bevor Sie beginnen?</span><span class="sxs-lookup"><span data-stu-id="dc60f-122">What do you need to know before you begin?</span></span>

- <span data-ttu-id="dc60f-123">Sie öffnen das Microsoft 365 Defender-Portal unter <https://security.microsoft.com/>.</span><span class="sxs-lookup"><span data-stu-id="dc60f-123">You open the Microsoft 365 Defender portal at <https://security.microsoft.com/>.</span></span> <span data-ttu-id="dc60f-124">Um direkt zur Seite **"Mandanten-Zulassungs-/Sperrlisten"** zu wechseln, verwenden Sie <https://security.microsoft.com/tenantAllowBlockList> .</span><span class="sxs-lookup"><span data-stu-id="dc60f-124">To go directly to the **Tenant Allow/Block Lists** page, use <https://security.microsoft.com/tenantAllowBlockList>.</span></span>

- <span data-ttu-id="dc60f-125">Sie geben Dateien mithilfe des SHA256-Hashwerts der Datei an.</span><span class="sxs-lookup"><span data-stu-id="dc60f-125">You specify files by using the SHA256 hash value of the file.</span></span> <span data-ttu-id="dc60f-126">Um den SHA256-Hashwert einer Datei in Windows zu finden, führen Sie den folgenden Befehl an einer Eingabeaufforderung aus:</span><span class="sxs-lookup"><span data-stu-id="dc60f-126">To find the SHA256 hash value of a file in Windows, run the following command in a Command Prompt:</span></span>

  ```console
  certutil.exe -hashfile "<Path>\<Filename>" SHA256
  ```

  <span data-ttu-id="dc60f-127">Ein Beispielwert ist `768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3a` .</span><span class="sxs-lookup"><span data-stu-id="dc60f-127">An example value is `768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3a`.</span></span> <span data-ttu-id="dc60f-128">Perceptual Hash (pHash)-Werte werden nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="dc60f-128">Perceptual hash (pHash) values are not supported.</span></span>

- <span data-ttu-id="dc60f-129">Die verfügbaren URL-Werte werden in der [URL-Syntax für den Abschnitt "Mandanten zulassen/blockieren"](#url-syntax-for-the-tenant-allowblock-list) weiter unten in diesem Artikel beschrieben.</span><span class="sxs-lookup"><span data-stu-id="dc60f-129">The available URL values are described in the [URL syntax for the Tenant Allow/Block List](#url-syntax-for-the-tenant-allowblock-list) section later in this article.</span></span>

- <span data-ttu-id="dc60f-130">Die Mandanten-Zulassungs-/Sperrliste lässt maximal 500 Einträge für URLs und 500 Einträge für Dateihashes zu.</span><span class="sxs-lookup"><span data-stu-id="dc60f-130">The Tenant Allow/Block List allows a maximum of 500 entries for URLs, and 500 entries for file hashes.</span></span>

- <span data-ttu-id="dc60f-131">Die maximale Anzahl von Zeichen für jeden Eintrag lautet:</span><span class="sxs-lookup"><span data-stu-id="dc60f-131">The maximum number of characters for each entry is:</span></span>
  - <span data-ttu-id="dc60f-132">Dateihashes = 64</span><span class="sxs-lookup"><span data-stu-id="dc60f-132">File hashes = 64</span></span>
  - <span data-ttu-id="dc60f-133">URL = 250</span><span class="sxs-lookup"><span data-stu-id="dc60f-133">URL = 250</span></span>

- <span data-ttu-id="dc60f-134">Ein Eintrag sollte innerhalb von 30 Minuten aktiv sein.</span><span class="sxs-lookup"><span data-stu-id="dc60f-134">An entry should be active within 30 minutes.</span></span>

- <span data-ttu-id="dc60f-135">Standardmäßig laufen Einträge in der Mandanten-Zulassungs-/Sperrliste nach 30 Tagen ab.</span><span class="sxs-lookup"><span data-stu-id="dc60f-135">By default, entries in the Tenant Allow/Block List will expire after 30 days.</span></span> <span data-ttu-id="dc60f-136">Sie können ein Datum angeben oder festlegen, dass es nie abläuft.</span><span class="sxs-lookup"><span data-stu-id="dc60f-136">You can specify a date or set them to never expire.</span></span>

- <span data-ttu-id="dc60f-137">Wie Sie eine Verbindung mit Exchange Online PowerShell herstellen, finden Sie unter [Herstellen einer Verbindung mit Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="dc60f-137">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="dc60f-138">Informationen zum Herstellen einer Verbindung mit dem eigenständigen Exchange Online Protection PowerShell finden Sie unter [Verbinden mit PowerShell in Exchange Online Protection](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="dc60f-138">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="dc60f-139">Sie müssen in Exchange Online Berechtigungen erhalten, bevor Sie die in diesem Artikel beschriebenen Schritte ausführen können:</span><span class="sxs-lookup"><span data-stu-id="dc60f-139">You need to be assigned permissions in Exchange Online before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="dc60f-140">**URLs und Dateien:**</span><span class="sxs-lookup"><span data-stu-id="dc60f-140">**URLs and files**:</span></span>
    - <span data-ttu-id="dc60f-141">Um Werte aus der Mandanten-Zulassungs-/Sperrliste hinzuzufügen und zu entfernen, müssen Sie Mitglied der Rollengruppen **"Organisationsverwaltung"** oder **"Sicherheitsadministrator"** sein.</span><span class="sxs-lookup"><span data-stu-id="dc60f-141">To add and remove values from the Tenant Allow/Block List, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
    - <span data-ttu-id="dc60f-142">Für den schreibgeschützten Zugriff auf die Mandanten-Zulassungs-/Sperrliste müssen Sie Mitglied der Rollengruppe **"Globaler Leser"** oder **"Sicherheitsleseberechtigter"** sein.</span><span class="sxs-lookup"><span data-stu-id="dc60f-142">For read-only access to the Tenant Allow/Block List, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>
  - <span data-ttu-id="dc60f-143">**Spoofing:** Eine der folgenden Kombinationen:</span><span class="sxs-lookup"><span data-stu-id="dc60f-143">**Spoofing**: One of the following combinations:</span></span>
    - <span data-ttu-id="dc60f-144">**Organisationsverwaltung**</span><span class="sxs-lookup"><span data-stu-id="dc60f-144">**Organization Management**</span></span>
    - <span data-ttu-id="dc60f-145">**Sicherheitsadministrator** <u>und</u> **Nur-Ansicht-Konfiguration** oder **Nur-Ansicht-Organisationsverwaltung**.</span><span class="sxs-lookup"><span data-stu-id="dc60f-145">**Security Administrator** <u>and</u> **View-Only Configuration** or **View-Only Organization Management**.</span></span>

  <span data-ttu-id="dc60f-146">Weitere Informationen finden Sie unter [Berechtigungen in Exchange Online](/exchange/permissions-exo/permissions-exo).</span><span class="sxs-lookup"><span data-stu-id="dc60f-146">For more information, see [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo).</span></span>

  > [!NOTE]
  >
  > - <span data-ttu-id="dc60f-147">Durch das Hinzufügen von Benutzern zur entsprechenden Azure Active Directory-Rolle im Microsoft 365 Admin Center erhalten Benutzer die erforderlichen Berechtigungen _und_ Berechtigungen für andere Features in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="dc60f-147">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="dc60f-148">Weitere Informationen finden Sie unter [Informationen zu Administratorrollen](../../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="dc60f-148">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  >
  > - <span data-ttu-id="dc60f-149">Die Rollengruppe **Organisationsverwaltung mit Leserechten** in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) ermöglicht auch einen schreibgeschützten Zugriff auf das Feature.</span><span class="sxs-lookup"><span data-stu-id="dc60f-149">The **View-Only Organization Management** role group in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-create-block-url-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="dc60f-150">Verwenden des Microsoft 365 Defender-Portals zum Erstellen von Block-URL-Einträgen in der Mandanten-Zulassungs-/Sperrliste</span><span class="sxs-lookup"><span data-stu-id="dc60f-150">Use the Microsoft 365 Defender portal to create block URL entries in the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="dc60f-151">Wechseln Sie im Microsoft 365 Defender-Portal zu **Richtlinien & Regeln** \> **Bedrohungsrichtlinien** \> **Mandanten-Zulassungs-/Sperrlisten.**</span><span class="sxs-lookup"><span data-stu-id="dc60f-151">In the Microsoft 365 Defender portal, go to **Policies & rules** \> **Threat Policies** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="dc60f-152">Überprüfen Sie auf der Seite **"Mandanten-Zulassungs-/Sperrliste",** ob die Registerkarte **"URLs"** ausgewählt ist, und klicken Sie dann auf **"Blockieren".**</span><span class="sxs-lookup"><span data-stu-id="dc60f-152">On the **Tenant Allow/Block List** page, verify that the **URLs** tab is selected, and then click **Block**</span></span>

3. <span data-ttu-id="dc60f-153">Konfigurieren Sie im angezeigten Flyout **"URLs blockieren"** die folgenden Einstellungen:</span><span class="sxs-lookup"><span data-stu-id="dc60f-153">In the **Block URLs** flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="dc60f-154">**Hinzufügen von ZU blockierenden URLs:** Geben Sie eine URL pro Zeile ein, bis maximal 20.</span><span class="sxs-lookup"><span data-stu-id="dc60f-154">**Add URLs to block**: Enter one URL per line, up to a maximum of 20.</span></span> <span data-ttu-id="dc60f-155">Ausführliche Informationen zur Syntax für URL-Einträge finden Sie in der [URL-Syntax für den Abschnitt "Mandanten-Zulassungs-/Sperrliste"](#url-syntax-for-the-tenant-allowblock-list) weiter unten in diesem Artikel.</span><span class="sxs-lookup"><span data-stu-id="dc60f-155">For details about the syntax for URL entries, see the [URL syntax for the Tenant Allow/Block List](#url-syntax-for-the-tenant-allowblock-list) section later in this article.</span></span>

   - <span data-ttu-id="dc60f-156">**Läuft nie ab:** Führen Sie einen der folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="dc60f-156">**Never expire**: Do one of the following steps:</span></span>

     - <span data-ttu-id="dc60f-157">Stellen Sie sicher, dass die Einstellung deaktiviert ist ( ![ Umschalten ](../../media/scc-toggle-off.png) ) und verwenden Sie das Feld **"Läuft ab",** um das Ablaufdatum für die Einträge anzugeben.</span><span class="sxs-lookup"><span data-stu-id="dc60f-157">Verify the setting is turned off (![Toggle off](../../media/scc-toggle-off.png)) and use the **Expires on** box to specify the expiration date for the entries.</span></span>

       <span data-ttu-id="dc60f-158">oder</span><span class="sxs-lookup"><span data-stu-id="dc60f-158">or</span></span>

     - <span data-ttu-id="dc60f-159">Verschieben Sie den Umschalter nach rechts, um die Einträge so zu konfigurieren, dass sie nie ablaufen:</span><span class="sxs-lookup"><span data-stu-id="dc60f-159">Move the toggle to the right to configure the entries to never expire:</span></span> ![Umschaltfläche ein](../../media/scc-toggle-on.png)<span data-ttu-id="dc60f-161">.</span><span class="sxs-lookup"><span data-stu-id="dc60f-161">.</span></span>

   - <span data-ttu-id="dc60f-162">**Optionaler Hinweis:** Geben Sie beschreibenden Text für die Einträge ein.</span><span class="sxs-lookup"><span data-stu-id="dc60f-162">**Optional note**: Enter descriptive text for the entries.</span></span>

4. <span data-ttu-id="dc60f-163">Klicken Sie nach Abschluss des Vorgangs auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="dc60f-163">When you're finished, click **Add**.</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-create-block-file-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="dc60f-164">Verwenden des Microsoft 365 Defender-Portals zum Erstellen von Blockierungsdateieinträgen in der Mandanten-Zulassungs-/Sperrliste</span><span class="sxs-lookup"><span data-stu-id="dc60f-164">Use the Microsoft 365 Defender portal to create block file entries in the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="dc60f-165">Wechseln Sie im Microsoft 365 Defender-Portal zu **Richtlinien & Regeln** \> **Bedrohungsrichtlinien** \> **Mandanten-Zulassungs-/Sperrlisten.**</span><span class="sxs-lookup"><span data-stu-id="dc60f-165">In the Microsoft 365 Defender portal, go to **Policies & rules** \> **Threat policies** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="dc60f-166">Wählen Sie auf der Seite **"Mandanten-Zulassungs-/Sperrliste"** die Registerkarte **"Dateien"** aus, und klicken Sie dann auf **"Blockieren".**</span><span class="sxs-lookup"><span data-stu-id="dc60f-166">On the **Tenant Allow/Block List** page, select the **Files** tab, and then click **Block**.</span></span>

3. <span data-ttu-id="dc60f-167">Konfigurieren Sie in den angezeigten **Add-Dateien zum Blockieren** des Flyouts die folgenden Einstellungen:</span><span class="sxs-lookup"><span data-stu-id="dc60f-167">In the **Add files to block** flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="dc60f-168">**Hinzufügen von Dateihashes:** Geben Sie einen SHA256-Hashwert pro Zeile ein, bis maximal 20.</span><span class="sxs-lookup"><span data-stu-id="dc60f-168">**Add file hashes**: Enter one SHA256 hash value per line, up to a maximum of 20.</span></span>

   - <span data-ttu-id="dc60f-169">**Läuft nie ab:** Führen Sie einen der folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="dc60f-169">**Never expire**: Do one of the following steps:</span></span>

     - <span data-ttu-id="dc60f-170">Stellen Sie sicher, dass die Einstellung deaktiviert ist ( ![ Umschalten ](../../media/scc-toggle-off.png) ) und verwenden Sie das Feld **"Läuft ab",** um das Ablaufdatum für die Einträge anzugeben.</span><span class="sxs-lookup"><span data-stu-id="dc60f-170">Verify the setting is turned off (![Toggle off](../../media/scc-toggle-off.png)) and use the **Expires on** box to specify the expiration date for the entries.</span></span>

     <span data-ttu-id="dc60f-171">oder</span><span class="sxs-lookup"><span data-stu-id="dc60f-171">or</span></span>

     - <span data-ttu-id="dc60f-172">Verschieben Sie den Umschalter nach rechts, um die Einträge so zu konfigurieren, dass sie nie ablaufen:</span><span class="sxs-lookup"><span data-stu-id="dc60f-172">Move the toggle to the right to configure the entries to never expire:</span></span> ![Umschaltfläche ein](../../media/scc-toggle-on.png)<span data-ttu-id="dc60f-174">.</span><span class="sxs-lookup"><span data-stu-id="dc60f-174">.</span></span>

   - <span data-ttu-id="dc60f-175">**Optionaler Hinweis:** Geben Sie beschreibenden Text für die Einträge ein.</span><span class="sxs-lookup"><span data-stu-id="dc60f-175">**Optional note**: Enter descriptive text for the entries.</span></span>

4. <span data-ttu-id="dc60f-176">Klicken Sie nach Abschluss des Vorgangs auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="dc60f-176">When you're finished, click **Add**.</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-create-allow-or-block-spoofed-sender-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="dc60f-177">Verwenden sie das Microsoft 365 Defender-Portal, um Gefälschte Absendereinträge in der Mandanten-Zulassungs-/Sperrliste zu erstellen oder zu blockieren.</span><span class="sxs-lookup"><span data-stu-id="dc60f-177">Use the Microsoft 365 Defender portal to create allow or block spoofed sender entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="dc60f-178">**Hinweise**:</span><span class="sxs-lookup"><span data-stu-id="dc60f-178">**Notes**:</span></span>

- <span data-ttu-id="dc60f-179">Nur die _Kombination aus_ dem gefälschten Benutzer _und_ der sendenden Infrastruktur, wie im Domänenpaar definiert, ist ausdrücklich zulässig oder am Spoofing gehindert.</span><span class="sxs-lookup"><span data-stu-id="dc60f-179">Only the _combination_ of the spoofed user _and_ the sending infrastructure as defined in the domain pair is specifically allowed or blocked from spoofing.</span></span>
- <span data-ttu-id="dc60f-180">Wenn Sie einen Zulassungs- oder Blockeintrag für ein Domänenpaar konfigurieren, werden Nachrichten von diesem Domänenpaar nicht mehr in der Spoofintelligenz angezeigt.</span><span class="sxs-lookup"><span data-stu-id="dc60f-180">When you configure an allow or block entry for a domain pair, messages from that domain pair no longer appear in the spoof intelligence insight.</span></span>
- <span data-ttu-id="dc60f-181">Einträge für gefälschte Absender laufen nie ab.</span><span class="sxs-lookup"><span data-stu-id="dc60f-181">Entries for spoofed senders never expire.</span></span>

1. <span data-ttu-id="dc60f-182">Wechseln Sie im Microsoft 365 Defender-Portal zu **Richtlinien & Regeln** \> **Bedrohungsrichtlinien** \> **Mandanten-Zulassungs-/Sperrlisten.**</span><span class="sxs-lookup"><span data-stu-id="dc60f-182">In the Microsoft 365 Defender portal, go to **Policies & rules** \> **Threat policies** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="dc60f-183">Wählen Sie auf der Seite **"Mandanten-Zulassungs-/Sperrliste"** die Registerkarte **"Spoofing"** aus, und klicken Sie dann auf **"Hinzufügen".**</span><span class="sxs-lookup"><span data-stu-id="dc60f-183">On the **Tenant Allow/Block List** page, select the **Spoofing** tab, and then click **Add**.</span></span>

3. <span data-ttu-id="dc60f-184">Konfigurieren Sie im angezeigten Flyout **"Neue Domänenpaare hinzufügen"** die folgenden Einstellungen:</span><span class="sxs-lookup"><span data-stu-id="dc60f-184">In the **Add new domain pairs** flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="dc60f-185">**Hinzufügen neuer Domänenpaare mit Platzhaltern:** Geben Sie ein Domänenpaar pro Zeile ein, maximal 20.</span><span class="sxs-lookup"><span data-stu-id="dc60f-185">**Add new domain pairs with wildcards**: Enter one domain pair per line, up to a maximum of 20.</span></span> <span data-ttu-id="dc60f-186">Ausführliche Informationen zur Syntax für spoofierte Absendereinträge finden Sie in der [Domänenpaarsyntax für spoofierte Absendereinträge im Abschnitt "Mandanten-Zulassungs-/Sperrliste"](#domain-pair-syntax-for-spoofed-sender-entries-in-the-tenant-allowblock-list) weiter unten in diesem Artikel.</span><span class="sxs-lookup"><span data-stu-id="dc60f-186">For details about the syntax for spoofed sender entries, see the [Domain pair syntax for spoofed sender entries in the Tenant Allow/Block List](#domain-pair-syntax-for-spoofed-sender-entries-in-the-tenant-allowblock-list) section later in this article.</span></span>

   - <span data-ttu-id="dc60f-187">**Spooftyp:** Wählen Sie einen der folgenden Werte aus:</span><span class="sxs-lookup"><span data-stu-id="dc60f-187">**Spoof type**: Select one of the following values:</span></span>
     - <span data-ttu-id="dc60f-188">**Intern:** Der gefälschte Absender befindet sich in einer Domäne, die zu Ihrer Organisation gehört (einer [akzeptierten Domäne).](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)</span><span class="sxs-lookup"><span data-stu-id="dc60f-188">**Internal**: The spoofed sender is in a domain that belongs to your organization (an [accepted domain](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)).</span></span>
     - <span data-ttu-id="dc60f-189">**Extern:** Der gefälschte Absender befindet sich in einer externen Domäne.</span><span class="sxs-lookup"><span data-stu-id="dc60f-189">**External**: The spoofed sender is in an external domain.</span></span>

   - <span data-ttu-id="dc60f-190">**Aktion:** Wählen Sie **"Zulassen"** oder **"Blockieren"** aus.</span><span class="sxs-lookup"><span data-stu-id="dc60f-190">**Action**: Select **Allow** or **Block**.</span></span>

4. <span data-ttu-id="dc60f-191">Klicken Sie nach Abschluss des Vorgangs auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="dc60f-191">When you're finished, click **Add**.</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-view-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="dc60f-192">Verwenden des Microsoft 365 Defender-Portals zum Anzeigen von Einträgen in der Mandanten-Zulassungs-/Sperrliste</span><span class="sxs-lookup"><span data-stu-id="dc60f-192">Use the Microsoft 365 Defender portal to view entries in the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="dc60f-193">Wechseln Sie im Microsoft 365 Defender-Portal zu **Richtlinien & Regeln** \> **Bedrohungsrichtlinien** \> **Mandanten-Zulassungs-/Sperrlisten.**</span><span class="sxs-lookup"><span data-stu-id="dc60f-193">In the Microsoft 365 Defender portal, go to **Policies & rules** \> **Threat policies** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="dc60f-194">Wählen Sie die gewünschte Registerkarte aus.</span><span class="sxs-lookup"><span data-stu-id="dc60f-194">Select the tab you want.</span></span> <span data-ttu-id="dc60f-195">Welche Spalten verfügbar sind, hängt von der ausgewählten Registerkarte ab:</span><span class="sxs-lookup"><span data-stu-id="dc60f-195">The columns that are available depend on the tab you selected:</span></span>

   - <span data-ttu-id="dc60f-196">**URLs:**</span><span class="sxs-lookup"><span data-stu-id="dc60f-196">**URLs**:</span></span>
     - <span data-ttu-id="dc60f-197">**Wert:** Die URL.</span><span class="sxs-lookup"><span data-stu-id="dc60f-197">**Value**: The URL.</span></span>
     - <span data-ttu-id="dc60f-198">**Aktion:** Der Wert **Block**.</span><span class="sxs-lookup"><span data-stu-id="dc60f-198">**Action**: The value **Block**.</span></span>
     - <span data-ttu-id="dc60f-199">**Datum der letzten Aktualisierung**</span><span class="sxs-lookup"><span data-stu-id="dc60f-199">**Last updated date**</span></span>
     - <span data-ttu-id="dc60f-200">**Ablaufdatum**</span><span class="sxs-lookup"><span data-stu-id="dc60f-200">**Expiration date**</span></span>
     - <span data-ttu-id="dc60f-201">**Hinweis**</span><span class="sxs-lookup"><span data-stu-id="dc60f-201">**Note**</span></span>

   - <span data-ttu-id="dc60f-202">**Files**</span><span class="sxs-lookup"><span data-stu-id="dc60f-202">**Files**</span></span>
     - <span data-ttu-id="dc60f-203">**Wert:** Der Dateihash.</span><span class="sxs-lookup"><span data-stu-id="dc60f-203">**Value**: The file hash.</span></span>
     - <span data-ttu-id="dc60f-204">**Aktion:** Der Wert **Block**.</span><span class="sxs-lookup"><span data-stu-id="dc60f-204">**Action**: The value **Block**.</span></span>
     - <span data-ttu-id="dc60f-205">**Datum der letzten Aktualisierung**</span><span class="sxs-lookup"><span data-stu-id="dc60f-205">**Last updated date**</span></span>
     - <span data-ttu-id="dc60f-206">**Ablaufdatum**</span><span class="sxs-lookup"><span data-stu-id="dc60f-206">**Expiration date**</span></span>
     - <span data-ttu-id="dc60f-207">**Hinweis**</span><span class="sxs-lookup"><span data-stu-id="dc60f-207">**Note**</span></span>

   - <span data-ttu-id="dc60f-208">**Spoofing**</span><span class="sxs-lookup"><span data-stu-id="dc60f-208">**Spoofing**</span></span>
     - <span data-ttu-id="dc60f-209">**Gefälschter Benutzer**</span><span class="sxs-lookup"><span data-stu-id="dc60f-209">**Spoofed user**</span></span>
     - <span data-ttu-id="dc60f-210">**Senden der Infrastruktur**</span><span class="sxs-lookup"><span data-stu-id="dc60f-210">**Sending infrastructure**</span></span>
     - <span data-ttu-id="dc60f-211">**Spooftyp:** Der Wert **Internal** oder **External**.</span><span class="sxs-lookup"><span data-stu-id="dc60f-211">**Spoof type**: The value **Internal** or **External**.</span></span>
     - <span data-ttu-id="dc60f-212">**Aktion:** Der Wert **Block** oder **Allow**.</span><span class="sxs-lookup"><span data-stu-id="dc60f-212">**Action**: The value **Block** or **Allow**.</span></span>

   <span data-ttu-id="dc60f-213">Sie können auf eine Spaltenüberschrift klicken, um sie in aufsteigender oder absteigender Reihenfolge zu sortieren.</span><span class="sxs-lookup"><span data-stu-id="dc60f-213">You can click on a column heading to sort in ascending or descending order.</span></span>

   <span data-ttu-id="dc60f-214">Sie können auf **"Gruppieren"** klicken, um die Ergebnisse zu gruppieren.</span><span class="sxs-lookup"><span data-stu-id="dc60f-214">You can click **Group** to group the results.</span></span> <span data-ttu-id="dc60f-215">Die verfügbaren Werte hängen von der ausgewählten Registerkarte ab:</span><span class="sxs-lookup"><span data-stu-id="dc60f-215">The values that are available depend on the tab you selected:</span></span>

   - <span data-ttu-id="dc60f-216">**URLs:** Sie können die Ergebnisse nach **Aktion** gruppieren.</span><span class="sxs-lookup"><span data-stu-id="dc60f-216">**URLs**: You can group the results by **Action**.</span></span>
   - <span data-ttu-id="dc60f-217">**Dateien:** Sie können die Ergebnisse nach **Aktion** gruppieren.</span><span class="sxs-lookup"><span data-stu-id="dc60f-217">**Files**: You can group the results by **Action**.</span></span>
   - <span data-ttu-id="dc60f-218">**Absenderdomänen für die BCL-Umgehung:** **Die Gruppe** ist auf dieser Registerkarte nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="dc60f-218">**Sender domains for BCL bypass**: **Group** is not available on this tab.</span></span>
   - <span data-ttu-id="dc60f-219">**Spoofing:** Sie können die Ergebnisse nach **Aktions-** oder **Spooftyp** gruppieren.</span><span class="sxs-lookup"><span data-stu-id="dc60f-219">**Spoofing**: You can group the results by **Action** or **Spoof type**.</span></span>

   <span data-ttu-id="dc60f-220">Klicken Sie auf **"Suchen",** geben Sie einen Wert ganz oder teilweise ein, und drücken Sie dann die EINGABETASTE, um einen bestimmten Wert zu finden.</span><span class="sxs-lookup"><span data-stu-id="dc60f-220">Click **Search**, enter all or part of a value, and then press ENTER to find a specific value.</span></span> <span data-ttu-id="dc60f-221">Wenn Sie fertig sind,  klicken Sie auf ![ Suchsymbol löschen ](../../media/b6512677-5e7b-42b0-a8a3-3be1d7fa23ee.gif) .</span><span class="sxs-lookup"><span data-stu-id="dc60f-221">When you're finished, click **Clear search** ![Clear search icon](../../media/b6512677-5e7b-42b0-a8a3-3be1d7fa23ee.gif).</span></span>

   <span data-ttu-id="dc60f-222">Klicken Sie auf **"Filtern",** um die Ergebnisse zu filtern.</span><span class="sxs-lookup"><span data-stu-id="dc60f-222">Click **Filter** to filter the results.</span></span> <span data-ttu-id="dc60f-223">Die werte, die  im angezeigten Filter-Flyout verfügbar sind, hängen von der ausgewählten Registerkarte ab:</span><span class="sxs-lookup"><span data-stu-id="dc60f-223">The values that are available in **Filter** flyout that appears depend on the tab you selected:</span></span>

   - <span data-ttu-id="dc60f-224">**Urls**</span><span class="sxs-lookup"><span data-stu-id="dc60f-224">**URLs**</span></span>
     - <span data-ttu-id="dc60f-225">**Action**</span><span class="sxs-lookup"><span data-stu-id="dc60f-225">**Action**</span></span>
     - <span data-ttu-id="dc60f-226">**Nie ablaufen**</span><span class="sxs-lookup"><span data-stu-id="dc60f-226">**Never expire**</span></span>
     - <span data-ttu-id="dc60f-227">**Datum der letzten Aktualisierung**</span><span class="sxs-lookup"><span data-stu-id="dc60f-227">**Last updated date**</span></span>
     - <span data-ttu-id="dc60f-228">**Ablaufdatum**</span><span class="sxs-lookup"><span data-stu-id="dc60f-228">**Expiration date**</span></span>

   - <span data-ttu-id="dc60f-229">**Files**</span><span class="sxs-lookup"><span data-stu-id="dc60f-229">**Files**</span></span>
     - <span data-ttu-id="dc60f-230">**Action**</span><span class="sxs-lookup"><span data-stu-id="dc60f-230">**Action**</span></span>
     - <span data-ttu-id="dc60f-231">**Nie ablaufen**</span><span class="sxs-lookup"><span data-stu-id="dc60f-231">**Never expire**</span></span>
     - <span data-ttu-id="dc60f-232">**Datum der letzten Aktualisierung**</span><span class="sxs-lookup"><span data-stu-id="dc60f-232">**Last updated date**</span></span>
     - <span data-ttu-id="dc60f-233">**Ablaufdatum**</span><span class="sxs-lookup"><span data-stu-id="dc60f-233">**Expiration date**</span></span>

   - <span data-ttu-id="dc60f-234">**Absenderdomänen für BCL-Umgehung**</span><span class="sxs-lookup"><span data-stu-id="dc60f-234">**Sender domains for BCL bypass**</span></span>
     - <span data-ttu-id="dc60f-235">**Nie ablaufen**</span><span class="sxs-lookup"><span data-stu-id="dc60f-235">**Never expire**</span></span>
     - <span data-ttu-id="dc60f-236">**Datum der letzten Aktualisierung**</span><span class="sxs-lookup"><span data-stu-id="dc60f-236">**Last updated date**</span></span>
     - <span data-ttu-id="dc60f-237">**Ablaufdatum**</span><span class="sxs-lookup"><span data-stu-id="dc60f-237">**Expiration date**</span></span>

   - <span data-ttu-id="dc60f-238">**Spoofing**</span><span class="sxs-lookup"><span data-stu-id="dc60f-238">**Spoofing**</span></span>
     - <span data-ttu-id="dc60f-239">**Action**</span><span class="sxs-lookup"><span data-stu-id="dc60f-239">**Action**</span></span>
     - <span data-ttu-id="dc60f-240">**Spooftyp**</span><span class="sxs-lookup"><span data-stu-id="dc60f-240">**Spoof type**</span></span>

   <span data-ttu-id="dc60f-241">Wenn Sie fertig sind, klicken Sie auf **"Übernehmen".**</span><span class="sxs-lookup"><span data-stu-id="dc60f-241">When you're finished, click **Apply**.</span></span> <span data-ttu-id="dc60f-242">Klicken Sie zum Löschen vorhandener Filter auf **"Filter",** und klicken Sie im angezeigten **Flyout "Filter"** auf **"Filter löschen".**</span><span class="sxs-lookup"><span data-stu-id="dc60f-242">To clear existing filters, click **Filter**, and in the **Filter** flyout that appears, click **Clear filters**.</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-modify-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="dc60f-243">Verwenden des Microsoft 365 Defender-Portals zum Ändern von Einträgen in der Mandanten-Zulassungs-/Sperrliste</span><span class="sxs-lookup"><span data-stu-id="dc60f-243">Use the Microsoft 365 Defender portal to modify entries in the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="dc60f-244">Wechseln Sie im Microsoft 365 Defender-Portal zu **Richtlinien & Regeln** \> **Bedrohungsrichtlinien** \> **Mandanten-Zulassungs-/Sperrlisten.**</span><span class="sxs-lookup"><span data-stu-id="dc60f-244">In the Microsoft 365 Defender portal, go to **Policies & rules** \> **Threat policies** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="dc60f-245">Wählen Sie die Registerkarte aus, die den Eintragstyp enthält, den Sie ändern möchten:</span><span class="sxs-lookup"><span data-stu-id="dc60f-245">Select the tab that contains the type of entry that you want to modify:</span></span>
   - <span data-ttu-id="dc60f-246">**Urls**</span><span class="sxs-lookup"><span data-stu-id="dc60f-246">**URLs**</span></span>
   - <span data-ttu-id="dc60f-247">**Files**</span><span class="sxs-lookup"><span data-stu-id="dc60f-247">**Files**</span></span>
   - <span data-ttu-id="dc60f-248">**Absenderdomänen für BCL-Umgehung**</span><span class="sxs-lookup"><span data-stu-id="dc60f-248">**Sender domains for BCL bypass**</span></span>
   - <span data-ttu-id="dc60f-249">**Spoofing**</span><span class="sxs-lookup"><span data-stu-id="dc60f-249">**Spoofing**</span></span>

3. <span data-ttu-id="dc60f-250">Wählen Sie den Eintrag aus, den  Sie ändern möchten, und klicken Sie dann auf ![ "Bearbeiten". ](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png)</span><span class="sxs-lookup"><span data-stu-id="dc60f-250">Select the entry that you want to modify, and then click **Edit** ![Edit icon](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png).</span></span> <span data-ttu-id="dc60f-251">Die Werte, die Sie im angezeigten Flyout ändern können, hängen von der Registerkarte ab, die Sie im vorherigen Schritt ausgewählt haben:</span><span class="sxs-lookup"><span data-stu-id="dc60f-251">The values that you are able to modify in the flyout that appears depend on the tab you selected in the previous step:</span></span>

   - <span data-ttu-id="dc60f-252">**Urls**</span><span class="sxs-lookup"><span data-stu-id="dc60f-252">**URLs**</span></span>
     - <span data-ttu-id="dc60f-253">**Nie ablaufen** und/oder Ablaufdatum.</span><span class="sxs-lookup"><span data-stu-id="dc60f-253">**Never expire** and/or expiration date.</span></span>
     - <span data-ttu-id="dc60f-254">**Optionaler Hinweis**</span><span class="sxs-lookup"><span data-stu-id="dc60f-254">**Optional note**</span></span>

   - <span data-ttu-id="dc60f-255">**Files**</span><span class="sxs-lookup"><span data-stu-id="dc60f-255">**Files**</span></span>
     - <span data-ttu-id="dc60f-256">**Nie ablaufen** und/oder Ablaufdatum.</span><span class="sxs-lookup"><span data-stu-id="dc60f-256">**Never expire** and/or expiration date.</span></span>
     - <span data-ttu-id="dc60f-257">**Optionaler Hinweis**</span><span class="sxs-lookup"><span data-stu-id="dc60f-257">**Optional note**</span></span>

   - <span data-ttu-id="dc60f-258">**Absenderdomänen für BCL-Umgehung**</span><span class="sxs-lookup"><span data-stu-id="dc60f-258">**Sender domains for BCL bypass**</span></span>
     - <span data-ttu-id="dc60f-259">**Nie ablaufen** und/oder Ablaufdatum.</span><span class="sxs-lookup"><span data-stu-id="dc60f-259">**Never expire** and/or expiration date.</span></span>

   - <span data-ttu-id="dc60f-260">**Spoofing**</span><span class="sxs-lookup"><span data-stu-id="dc60f-260">**Spoofing**</span></span>
     - <span data-ttu-id="dc60f-261">**Aktion:** Sie können den Wert in **Zulassen** oder **Blockieren** ändern.</span><span class="sxs-lookup"><span data-stu-id="dc60f-261">**Action**: You can change the value to **Allow** or **Block**.</span></span>

4. <span data-ttu-id="dc60f-262">Klicken Sie nach Abschluss des Vorgangs auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="dc60f-262">When you're finished, click **Save**.</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-remove-entries-from-the-tenant-allowblock-list"></a><span data-ttu-id="dc60f-263">Verwenden des Microsoft 365 Defender-Portals zum Entfernen von Einträgen aus der Mandanten-Zulassungs-/Sperrliste</span><span class="sxs-lookup"><span data-stu-id="dc60f-263">Use the Microsoft 365 Defender portal to remove entries from the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="dc60f-264">Wechseln Sie im Microsoft 365 Defender-Portal  zu \> "Zulassungs-/Sperrlisten des Mandanten für die Bedrohungsverwaltungsrichtlinie".  \> </span><span class="sxs-lookup"><span data-stu-id="dc60f-264">In the Microsoft 365 Defender portal, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="dc60f-265">Wählen Sie die Registerkarte aus, die den Eintragstyp enthält, den Sie entfernen möchten:</span><span class="sxs-lookup"><span data-stu-id="dc60f-265">Select the tab that contains the type of entry that you want to remove:</span></span>
   - <span data-ttu-id="dc60f-266">**Urls**</span><span class="sxs-lookup"><span data-stu-id="dc60f-266">**URLs**</span></span>
   - <span data-ttu-id="dc60f-267">**Files**</span><span class="sxs-lookup"><span data-stu-id="dc60f-267">**Files**</span></span>
   - <span data-ttu-id="dc60f-268">**Absenderdomänen für BCL-Umgehung**</span><span class="sxs-lookup"><span data-stu-id="dc60f-268">**Sender domains for BCL bypass**</span></span>
   - <span data-ttu-id="dc60f-269">**Spoofing**</span><span class="sxs-lookup"><span data-stu-id="dc60f-269">**Spoofing**</span></span>

3. <span data-ttu-id="dc60f-270">Wählen Sie den Eintrag aus, den  Sie entfernen möchten, und klicken Sie dann auf das Symbol ![ "Löschen". ](../../media/87565fbb-5147-4f22-9ed7-1c18ce664392.png)</span><span class="sxs-lookup"><span data-stu-id="dc60f-270">Select the entry that you want to remove, and then click **Delete** ![Delete icon](../../media/87565fbb-5147-4f22-9ed7-1c18ce664392.png).</span></span>

4. <span data-ttu-id="dc60f-271">Klicken Sie im angezeigten Warndialogfeld auf **"Löschen".**</span><span class="sxs-lookup"><span data-stu-id="dc60f-271">In the warning dialog that appears, click **Delete**.</span></span>

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-the-tenant-allowblock-list"></a><span data-ttu-id="dc60f-272">Verwenden Exchange Online PowerShell oder der eigenständigen EOP PowerShell zum Konfigurieren der Mandanten-Zulassungs-/Sperrliste</span><span class="sxs-lookup"><span data-stu-id="dc60f-272">Use Exchange Online PowerShell or standalone EOP PowerShell to configure the Tenant Allow/Block List</span></span>

### <a name="use-powershell-to-add-block-file-or-url-entries-to-the-tenant-allowblock-list"></a><span data-ttu-id="dc60f-273">Verwenden von PowerShell zum Hinzufügen von Blockierungsdateien oder URL-Einträgen zur Mandanten-Zulassungs-/Sperrliste</span><span class="sxs-lookup"><span data-stu-id="dc60f-273">Use PowerShell to add block file or URL entries to the Tenant Allow/Block List</span></span>

<span data-ttu-id="dc60f-274">Verwenden Sie die folgende Syntax, um Blockierungsdateien oder URL-Einträge in der Mandanten-Zulassungs-/Sperrliste hinzuzufügen:</span><span class="sxs-lookup"><span data-stu-id="dc60f-274">To add block file or URL entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
New-TenantAllowBlockListItems -ListType <FileHash | Url> -Block -Entries "Value1","Value2",..."ValueN" <-ExpirationDate Date | -NoExpiration> [-Notes <String>]
```

<span data-ttu-id="dc60f-275">In diesem Beispiel wird ein Blockdateieintrag für die angegebenen Dateien hinzugefügt, die nie ablaufen.</span><span class="sxs-lookup"><span data-stu-id="dc60f-275">This example adds a block file entry for the specified files that never expires.</span></span>

```powershell
New-TenantAllowBlockListItem -ListType FileHash -Block -Entries "768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3","2c0a35409ff0873cfa28b70b8224e9aca2362241c1f0ed6f622fef8d4722fd9a" -NoExpiration
```

<span data-ttu-id="dc60f-276">In diesem Beispiel wird ein Block-URL-Eintrag für contoso.com und alle Unterdomänen hinzugefügt (z. B. contoso.com, www.contoso.com und xyz.abc.contoso.com).</span><span class="sxs-lookup"><span data-stu-id="dc60f-276">This example adds a block URL entry for contoso.com and all subdomains (for example, contoso.com, www.contoso.com, and xyz.abc.contoso.com).</span></span> <span data-ttu-id="dc60f-277">Da wir die Parameter ExpirationDate oder NoExpiration nicht verwendet haben, läuft der Eintrag nach 30 Tagen ab.</span><span class="sxs-lookup"><span data-stu-id="dc60f-277">Because we didn't use the ExpirationDate or NoExpiration parameters, the entry expires after 30 days.</span></span>

```powershell
New-TenantAllowBlockListItems -ListType Url -Block -Entries ~contoso.com
```

<span data-ttu-id="dc60f-278">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [New-TenantAllowBlockListItems](/powershell/module/exchange/new-tenantallowblocklistitems).</span><span class="sxs-lookup"><span data-stu-id="dc60f-278">For detailed syntax and parameter information, see [New-TenantAllowBlockListItems](/powershell/module/exchange/new-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-add-allow-or-block-spoofed-sender-entries-to-the-tenant-allowblock-list"></a><span data-ttu-id="dc60f-279">Verwenden von PowerShell zum Hinzufügen oder Blockieren von Spoofing-Absendereinträgen zur Mandanten-Zulassungs-/Sperrliste</span><span class="sxs-lookup"><span data-stu-id="dc60f-279">Use PowerShell to add allow or block spoofed sender entries to the Tenant Allow/Block List</span></span>

<span data-ttu-id="dc60f-280">Verwenden Sie die folgende Syntax, um gefälschte Absendereinträge in der Mandanten-Zulassungs-/Sperrliste hinzuzufügen:</span><span class="sxs-lookup"><span data-stu-id="dc60f-280">To add spoofed sender entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
New-TenantAllowBlockListSpoofItems -SpoofedUser <Domain | EmailAddress | *> -SendingInfrastructure <Domain | IPAddress/24> -SpoofType <External | Internal> -Action <Allow | Block>
```

<span data-ttu-id="dc60f-281">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [New-TenantAllowBlockListSpoofItems](/powershell/module/exchange/new-tenantallowblocklistspoofitems).</span><span class="sxs-lookup"><span data-stu-id="dc60f-281">For detailed syntax and parameter information, see [New-TenantAllowBlockListSpoofItems](/powershell/module/exchange/new-tenantallowblocklistspoofitems).</span></span>

### <a name="use-powershell-to-view-block-file-or-url-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="dc60f-282">Verwenden von PowerShell zum Anzeigen von Blockierungsdateien oder URL-Einträgen in der Mandanten-Zulassungs-/Sperrliste</span><span class="sxs-lookup"><span data-stu-id="dc60f-282">Use PowerShell to view block file or URL entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="dc60f-283">Verwenden Sie die folgende Syntax, um Blockierungsdateien oder URL-Einträge in der Mandanten-Zulassungs-/Sperrliste anzuzeigen:</span><span class="sxs-lookup"><span data-stu-id="dc60f-283">To view block file or URL entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType <FileHash | URL> [-Entry <FileHashValue | URLValue>] [<-ExpirationDate Date | -NoExpiration>]
```

<span data-ttu-id="dc60f-284">In diesem Beispiel werden Informationen für den angegebenen Dateihashwert zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="dc60f-284">This example returns information for the specified file hash value.</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType FileHash -Entry "9f86d081884c7d659a2feaa0c55ad015a3bf4f1b2b0b822cd15d6c15b0f00a08"
```

<span data-ttu-id="dc60f-285">In diesem Beispiel werden alle blockierten URLs zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="dc60f-285">This example returns all blocked URLs.</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType Url -Block
```

<span data-ttu-id="dc60f-286">Ausführliche Informationen zu Syntax und Parametern finden Sie unter ["Get-TenantAllowBlockListItems".](/powershell/module/exchange/get-tenantallowblocklistitems)</span><span class="sxs-lookup"><span data-stu-id="dc60f-286">For detailed syntax and parameter information, see [Get-TenantAllowBlockListItems](/powershell/module/exchange/get-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-view-allow-or-block-spoofed-sender-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="dc60f-287">Verwenden von PowerShell zum Anzeigen oder Blockieren von Spoofing-Absendereinträgen in der Mandanten-Zulassungs-/Sperrliste</span><span class="sxs-lookup"><span data-stu-id="dc60f-287">Use PowerShell to view allow or block spoofed sender entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="dc60f-288">Verwenden Sie die folgende Syntax, um gefälschte Absendereinträge in der Mandanten-Zulassungs-/Sperrliste anzuzeigen:</span><span class="sxs-lookup"><span data-stu-id="dc60f-288">To view spoofed sender entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Get-TenantAllowBlockListSpoofItems [-Action <Allow | Block>] [-SpoofType <External | Internal>
```

<span data-ttu-id="dc60f-289">In diesem Beispiel werden alle gefälschten Absendereinträge in der Mandanten-Zulassungs-/Sperrliste zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="dc60f-289">This example returns all spoofed sender entries in the Tenant Allow/Block List.</span></span>

```powershell
Get-TenantAllowBlockListSpoofItems
```

<span data-ttu-id="dc60f-290">This example returns all allow spoofed sender entries that are internal.</span><span class="sxs-lookup"><span data-stu-id="dc60f-290">This example returns all allow spoofed sender entries that are internal.</span></span>

```powershell
Get-TenantAllowBlockListSpoofItems -Action Allow -SpoofType Internal
```

<span data-ttu-id="dc60f-291">In diesem Beispiel werden alle blockierten spoofierten Absendereinträge zurückgegeben, die extern sind.</span><span class="sxs-lookup"><span data-stu-id="dc60f-291">This example returns all blocked spoofed sender entries that are external.</span></span>

```powershell
Get-TenantAllowBlockListSpoofItems -Action Block -SpoofType External
```

<span data-ttu-id="dc60f-292">Ausführliche Informationen zu Syntax und Parametern finden Sie unter ["Get-TenantAllowBlockListSpoofItems".](/powershell/module/exchange/get-tenantallowblocklistspoofitems)</span><span class="sxs-lookup"><span data-stu-id="dc60f-292">For detailed syntax and parameter information, see [Get-TenantAllowBlockListSpoofItems](/powershell/module/exchange/get-tenantallowblocklistspoofitems).</span></span>

### <a name="use-powershell-to-modify-block-file-and-url-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="dc60f-293">Verwenden von PowerShell zum Ändern von Blockdatei- und URL-Einträgen in der Mandanten-Zulassungs-/Sperrliste</span><span class="sxs-lookup"><span data-stu-id="dc60f-293">Use PowerShell to modify block file and URL entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="dc60f-294">Verwenden Sie die folgende Syntax, um Blockdatei- und URL-Einträge in der Mandanten-Zulassungs-/Sperrliste zu ändern:</span><span class="sxs-lookup"><span data-stu-id="dc60f-294">To modify block file and URL entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Set-TenantAllowBlockListItems -ListType <FileHash | Url> -Ids <"Id1","Id2",..."IdN"> [<-ExpirationDate Date | -NoExpiration>] [-Notes <String>]
```

<span data-ttu-id="dc60f-295">In diesem Beispiel wird das Ablaufdatum des angegebenen Block-URL-Eintrags geändert.</span><span class="sxs-lookup"><span data-stu-id="dc60f-295">This example changes the expiration date of the specified block URL entry.</span></span>

```powershell
Set-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSRAAAA" -ExpirationDate "5/30/2020"
```

<span data-ttu-id="dc60f-296">Ausführliche Informationen zu Syntax und Parametern finden Sie unter ["Set-TenantAllowBlockListItems".](/powershell/module/exchange/set-tenantallowblocklistitems)</span><span class="sxs-lookup"><span data-stu-id="dc60f-296">For detailed syntax and parameter information, see [Set-TenantAllowBlockListItems](/powershell/module/exchange/set-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-modify-allow-or-block-spoofed-sender-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="dc60f-297">Verwenden von PowerShell zum Ändern oder Blockieren von Spoofing-Absendereinträgen in der Mandanten-Zulassungs-/Sperrliste</span><span class="sxs-lookup"><span data-stu-id="dc60f-297">Use PowerShell to modify allow or block spoofed sender entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="dc60f-298">Verwenden Sie die folgende Syntax, um spoofierte Absendereinträge in der Mandanten-Zulassungs-/Sperrliste zu ändern oder zu blockieren:</span><span class="sxs-lookup"><span data-stu-id="dc60f-298">To modify allow or block spoofed sender entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Set-TenantAllowBlockListSpoofItems -Ids <"Id1","Id2",..."IdN"> -Action <Allow | Block>
```

<span data-ttu-id="dc60f-299">In diesem Beispiel wird der Spoofing-Absendereintrag von "Blockieren zulassen" geändert.</span><span class="sxs-lookup"><span data-stu-id="dc60f-299">This example changes spoofed sender entry from allow to block.</span></span>

```powershell
Set-TenantAllowBlockListItems -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSRAAAA" -Action Block
```

<span data-ttu-id="dc60f-300">Ausführliche Informationen zu Syntax und Parametern finden Sie unter ["Set-TenantAllowBlockListSpoofItems".](/powershell/module/exchange/set-tenantallowblocklistspoofitems)</span><span class="sxs-lookup"><span data-stu-id="dc60f-300">For detailed syntax and parameter information, see [Set-TenantAllowBlockListSpoofItems](/powershell/module/exchange/set-tenantallowblocklistspoofitems).</span></span>

### <a name="use-powershell-to-remove-url-or-file-entries-from-the-tenant-allowblock-list"></a><span data-ttu-id="dc60f-301">Verwenden von PowerShell zum Entfernen von URL- oder Dateieinträgen aus der Mandanten-Zulassungs-/Sperrliste</span><span class="sxs-lookup"><span data-stu-id="dc60f-301">Use PowerShell to remove URL or file entries from the Tenant Allow/Block List</span></span>

<span data-ttu-id="dc60f-302">Verwenden Sie die folgende Syntax, um Datei- und URL-Einträge aus der Mandanten-Zulassungs-/Sperrliste zu entfernen:</span><span class="sxs-lookup"><span data-stu-id="dc60f-302">To remove file and URL entries from the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Remove-TenantAllowBlockListItems -ListType <FileHash | Url> -Ids <"Id1","Id2",..."IdN">
```

<span data-ttu-id="dc60f-303">In diesem Beispiel wird der angegebene Block-URL-Eintrag aus der Mandanten-Zulassungs-/Sperrliste entfernt.</span><span class="sxs-lookup"><span data-stu-id="dc60f-303">This example removes the specified block URL entry from the Tenant Allow/Block List.</span></span>

```powershell
Remove-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSPAAAA0"
```

<span data-ttu-id="dc60f-304">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Remove-TenantAllowBlockListItems](/powershell/module/exchange/remove-tenantallowblocklistitems).</span><span class="sxs-lookup"><span data-stu-id="dc60f-304">For detailed syntax and parameter information, see [Remove-TenantAllowBlockListItems](/powershell/module/exchange/remove-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-remove-allow-or-block-spoofed-sender-entries-from-the-tenant-allowblock-list"></a><span data-ttu-id="dc60f-305">Verwenden von PowerShell zum Entfernen von Spoofing-Absendereinträgen aus der Mandanten-Zulassungs-/Sperrliste</span><span class="sxs-lookup"><span data-stu-id="dc60f-305">Use PowerShell to remove allow or block spoofed sender entries from the Tenant Allow/Block List</span></span>

<span data-ttu-id="dc60f-306">Verwenden Sie die folgende Syntax, um Spoofing von Absendereinträgen aus der Mandanten-Zulassungs-/Sperrliste zu entfernen oder zu blockieren:</span><span class="sxs-lookup"><span data-stu-id="dc60f-306">To remove allow or block spoof sender entries from the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Remove-TenantAllowBlockListSpoofItems -Ids <"Id1","Id2",..."IdN">
```

<span data-ttu-id="dc60f-307">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Remove-TenantAllowBlockListSpoofItems](/powershell/module/exchange/remove-tenantallowblocklistspoofitems).</span><span class="sxs-lookup"><span data-stu-id="dc60f-307">For detailed syntax and parameter information, see [Remove-TenantAllowBlockListSpoofItems](/powershell/module/exchange/remove-tenantallowblocklistspoofitems).</span></span>

## <a name="url-syntax-for-the-tenant-allowblock-list"></a><span data-ttu-id="dc60f-308">URL-Syntax für die Mandanten-Zulassungs-/Sperrliste</span><span class="sxs-lookup"><span data-stu-id="dc60f-308">URL syntax for the Tenant Allow/Block List</span></span>

- <span data-ttu-id="dc60f-309">IP4v- und IPv6-Adressen sind zulässig, TCP/UDP-Ports jedoch nicht.</span><span class="sxs-lookup"><span data-stu-id="dc60f-309">IP4v and IPv6 addresses are allowed, but TCP/UDP ports are not.</span></span>

- <span data-ttu-id="dc60f-310">Dateinamenerweiterungen sind nicht zulässig (z. B. test.pdf).</span><span class="sxs-lookup"><span data-stu-id="dc60f-310">Filename extensions are not allowed (for example, test.pdf).</span></span>

- <span data-ttu-id="dc60f-311">Unicode wird nicht unterstützt, Punycode jedoch.</span><span class="sxs-lookup"><span data-stu-id="dc60f-311">Unicode is not supported, but Punycode is.</span></span>

- <span data-ttu-id="dc60f-312">Hostnamen sind zulässig, wenn alle folgenden Anweisungen wahr sind:</span><span class="sxs-lookup"><span data-stu-id="dc60f-312">Hostnames are allowed if all of the following statements are true:</span></span>
  - <span data-ttu-id="dc60f-313">Der Hostname enthält einen Punkt.</span><span class="sxs-lookup"><span data-stu-id="dc60f-313">The hostname contains a period.</span></span>
  - <span data-ttu-id="dc60f-314">Links vom Punkt befindet sich mindestens ein Zeichen.</span><span class="sxs-lookup"><span data-stu-id="dc60f-314">There is at least one character to the left of the period.</span></span>
  - <span data-ttu-id="dc60f-315">Rechts neben dem Punkt befinden sich mindestens zwei Zeichen.</span><span class="sxs-lookup"><span data-stu-id="dc60f-315">There are at least two characters to the right of the period.</span></span>

  <span data-ttu-id="dc60f-316">Ist beispielsweise `t.co` zulässig `.com` oder nicht `contoso.` zulässig.</span><span class="sxs-lookup"><span data-stu-id="dc60f-316">For example, `t.co` is allowed; `.com` or `contoso.` are not allowed.</span></span>

- <span data-ttu-id="dc60f-317">Unterpfade werden nicht impliziert.</span><span class="sxs-lookup"><span data-stu-id="dc60f-317">Subpaths are not implied.</span></span>

  <span data-ttu-id="dc60f-318">Enthält z. B. `contoso.com` nicht `contoso.com/a` .</span><span class="sxs-lookup"><span data-stu-id="dc60f-318">For example, `contoso.com` does not include `contoso.com/a`.</span></span>

- <span data-ttu-id="dc60f-319">Platzhalter (\*) sind in den folgenden Szenarien zulässig:</span><span class="sxs-lookup"><span data-stu-id="dc60f-319">Wildcards (\*) are allowed in the following scenarios:</span></span>

  - <span data-ttu-id="dc60f-320">Auf einen linken Platzhalter muss ein Punkt folgen, um eine Unterdomäne anzugeben.</span><span class="sxs-lookup"><span data-stu-id="dc60f-320">A left wildcard must be followed by a period to specify a subdomain.</span></span>

    <span data-ttu-id="dc60f-321">Ist beispielsweise `*.contoso.com` zulässig; `*contoso.com` ist nicht zulässig.</span><span class="sxs-lookup"><span data-stu-id="dc60f-321">For example, `*.contoso.com` is allowed; `*contoso.com` is not allowed.</span></span>

  - <span data-ttu-id="dc60f-322">Ein rechter Platzhalter muss einem Schrägstrich (/) folgen, um einen Pfad anzugeben.</span><span class="sxs-lookup"><span data-stu-id="dc60f-322">A right wildcard must follow a forward slash (/) to specify a path.</span></span>

    <span data-ttu-id="dc60f-323">Ist beispielsweise `contoso.com/*` zulässig `contoso.com*` oder nicht `contoso.com/ab*` zulässig.</span><span class="sxs-lookup"><span data-stu-id="dc60f-323">For example, `contoso.com/*` is allowed; `contoso.com*` or `contoso.com/ab*` are not allowed.</span></span>

  - <span data-ttu-id="dc60f-324">Alle Unterpfade werden nicht durch einen rechten Platzhalter impliziert.</span><span class="sxs-lookup"><span data-stu-id="dc60f-324">All subpaths are not implied by a right wildcard.</span></span>

    <span data-ttu-id="dc60f-325">Enthält z. B. `contoso.com/*` nicht `contoso.com/a` .</span><span class="sxs-lookup"><span data-stu-id="dc60f-325">For example, `contoso.com/*` does not include `contoso.com/a`.</span></span>

  - <span data-ttu-id="dc60f-326">`*.com*` ungültig ist (keine auflösbare Domäne, und der rechte Platzhalter folgt keinem Schrägstrich).</span><span class="sxs-lookup"><span data-stu-id="dc60f-326">`*.com*` is invalid (not a resolvable domain and the right wildcard does not follow a forward slash).</span></span>

  - <span data-ttu-id="dc60f-327">Platzhalter sind in IP-Adressen nicht zulässig.</span><span class="sxs-lookup"><span data-stu-id="dc60f-327">Wildcards are not allowed in IP addresses.</span></span>

- <span data-ttu-id="dc60f-328">Das Tildezeichen (~) ist in den folgenden Szenarien verfügbar:</span><span class="sxs-lookup"><span data-stu-id="dc60f-328">The tilde (~) character is available in the following scenarios:</span></span>

  - <span data-ttu-id="dc60f-329">Eine linke Tilde impliziert eine Domäne und alle Unterdomänen.</span><span class="sxs-lookup"><span data-stu-id="dc60f-329">A left tilde implies a domain and all subdomains.</span></span>

    <span data-ttu-id="dc60f-330">Beispiel: `~contoso.com` "includes" `contoso.com` und `*.contoso.com` ".</span><span class="sxs-lookup"><span data-stu-id="dc60f-330">For example `~contoso.com` includes `contoso.com` and `*.contoso.com`.</span></span>

- <span data-ttu-id="dc60f-331">URL-Einträge, die Protokolle enthalten (z. B. `http://` , oder ) schlagen `https://` `ftp://` fehl, da URL-Einträge für alle Protokolle gelten.</span><span class="sxs-lookup"><span data-stu-id="dc60f-331">URL entries that contain protocols (for example, `http://`, `https://`, or `ftp://`) will fail, because URL entries apply to all protocols.</span></span>

- <span data-ttu-id="dc60f-332">Ein Benutzername oder Kennwort wird nicht unterstützt oder ist nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="dc60f-332">A username or password aren't supported or required.</span></span>

- <span data-ttu-id="dc60f-333">Anführungszeichen (' oder ") sind ungültige Zeichen.</span><span class="sxs-lookup"><span data-stu-id="dc60f-333">Quotes (' or ") are invalid characters.</span></span>

- <span data-ttu-id="dc60f-334">Eine URL sollte nach Möglichkeit alle Umleitungen enthalten.</span><span class="sxs-lookup"><span data-stu-id="dc60f-334">A URL should include all redirects where possible.</span></span>

### <a name="url-entry-scenarios"></a><span data-ttu-id="dc60f-335">URL-Eintragsszenarien</span><span class="sxs-lookup"><span data-stu-id="dc60f-335">URL entry scenarios</span></span>

<span data-ttu-id="dc60f-336">Gültige URL-Einträge und deren Ergebnisse werden in den folgenden Abschnitten beschrieben.</span><span class="sxs-lookup"><span data-stu-id="dc60f-336">Valid URL entries and their results are described in the following sections.</span></span>

#### <a name="scenario-no-wildcards"></a><span data-ttu-id="dc60f-337">Szenario: Keine Platzhalter</span><span class="sxs-lookup"><span data-stu-id="dc60f-337">Scenario: No wildcards</span></span>

<span data-ttu-id="dc60f-338">**Eintrag**: `contoso.com`</span><span class="sxs-lookup"><span data-stu-id="dc60f-338">**Entry**: `contoso.com`</span></span>

- <span data-ttu-id="dc60f-339">**Übereinstimmung zulassen:** contoso.com</span><span class="sxs-lookup"><span data-stu-id="dc60f-339">**Allow match**: contoso.com</span></span>

- <span data-ttu-id="dc60f-340">**Nicht übereinstimmend zulassen:**</span><span class="sxs-lookup"><span data-stu-id="dc60f-340">**Allow not matched**:</span></span>

  - <span data-ttu-id="dc60f-341">abc-contoso.com</span><span class="sxs-lookup"><span data-stu-id="dc60f-341">abc-contoso.com</span></span>
  - <span data-ttu-id="dc60f-342">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="dc60f-342">contoso.com/a</span></span>
  - <span data-ttu-id="dc60f-343">payroll.contoso.com</span><span class="sxs-lookup"><span data-stu-id="dc60f-343">payroll.contoso.com</span></span>
  - <span data-ttu-id="dc60f-344">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="dc60f-344">test.com/contoso.com</span></span>
  - <span data-ttu-id="dc60f-345">test.com/q=contoso.com</span><span class="sxs-lookup"><span data-stu-id="dc60f-345">test.com/q=contoso.com</span></span>
  - <span data-ttu-id="dc60f-346">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="dc60f-346">www.contoso.com</span></span>
  - <span data-ttu-id="dc60f-347">www.contoso.com/q=a@contoso.com</span><span class="sxs-lookup"><span data-stu-id="dc60f-347">www.contoso.com/q=a@contoso.com</span></span>

- <span data-ttu-id="dc60f-348">**Blocküberstimmung:**</span><span class="sxs-lookup"><span data-stu-id="dc60f-348">**Block match**:</span></span>

  - <span data-ttu-id="dc60f-349">contoso.com</span><span class="sxs-lookup"><span data-stu-id="dc60f-349">contoso.com</span></span>
  - <span data-ttu-id="dc60f-350">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="dc60f-350">contoso.com/a</span></span>
  - <span data-ttu-id="dc60f-351">payroll.contoso.com</span><span class="sxs-lookup"><span data-stu-id="dc60f-351">payroll.contoso.com</span></span>
  - <span data-ttu-id="dc60f-352">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="dc60f-352">test.com/contoso.com</span></span>
  - <span data-ttu-id="dc60f-353">test.com/q=contoso.com</span><span class="sxs-lookup"><span data-stu-id="dc60f-353">test.com/q=contoso.com</span></span>
  - <span data-ttu-id="dc60f-354">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="dc60f-354">www.contoso.com</span></span>
  - <span data-ttu-id="dc60f-355">www.contoso.com/q=a@contoso.com</span><span class="sxs-lookup"><span data-stu-id="dc60f-355">www.contoso.com/q=a@contoso.com</span></span>

- <span data-ttu-id="dc60f-356">**Block nicht abgeglichen:** abc-contoso.com</span><span class="sxs-lookup"><span data-stu-id="dc60f-356">**Block not matched**: abc-contoso.com</span></span>

#### <a name="scenario-left-wildcard-subdomain"></a><span data-ttu-id="dc60f-357">Szenario: Linker Platzhalter (Unterdomäne)</span><span class="sxs-lookup"><span data-stu-id="dc60f-357">Scenario: Left wildcard (subdomain)</span></span>

<span data-ttu-id="dc60f-358">**Eintrag**: `*.contoso.com`</span><span class="sxs-lookup"><span data-stu-id="dc60f-358">**Entry**: `*.contoso.com`</span></span>

- <span data-ttu-id="dc60f-359">**Übereinstimmung zulassen** und **Übereinstimmung blockieren:**</span><span class="sxs-lookup"><span data-stu-id="dc60f-359">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="dc60f-360">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="dc60f-360">www.contoso.com</span></span>
  - <span data-ttu-id="dc60f-361">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="dc60f-361">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="dc60f-362">**Nicht übereinstimmende** und **nicht übereinstimmende Blockierung** zulassen:</span><span class="sxs-lookup"><span data-stu-id="dc60f-362">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="dc60f-363">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="dc60f-363">123contoso.com</span></span>
  - <span data-ttu-id="dc60f-364">contoso.com</span><span class="sxs-lookup"><span data-stu-id="dc60f-364">contoso.com</span></span>
  - <span data-ttu-id="dc60f-365">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="dc60f-365">test.com/contoso.com</span></span>
  - <span data-ttu-id="dc60f-366">www.contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="dc60f-366">www.contoso.com/abc</span></span>

#### <a name="scenario-right-wildcard-at-top-of-path"></a><span data-ttu-id="dc60f-367">Szenario: Rechter Platzhalter oben im Pfad</span><span class="sxs-lookup"><span data-stu-id="dc60f-367">Scenario: Right wildcard at top of path</span></span>

<span data-ttu-id="dc60f-368">**Eintrag**: `contoso.com/a/*`</span><span class="sxs-lookup"><span data-stu-id="dc60f-368">**Entry**: `contoso.com/a/*`</span></span>

- <span data-ttu-id="dc60f-369">**Übereinstimmung zulassen** und **Übereinstimmung blockieren:**</span><span class="sxs-lookup"><span data-stu-id="dc60f-369">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="dc60f-370">contoso.com/a/b</span><span class="sxs-lookup"><span data-stu-id="dc60f-370">contoso.com/a/b</span></span>
  - <span data-ttu-id="dc60f-371">contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="dc60f-371">contoso.com/a/b/c</span></span>
  - <span data-ttu-id="dc60f-372">contoso.com/a/?q=joe@t.com</span><span class="sxs-lookup"><span data-stu-id="dc60f-372">contoso.com/a/?q=joe@t.com</span></span>

- <span data-ttu-id="dc60f-373">**Nicht übereinstimmende** und **nicht übereinstimmende Blockierung** zulassen:</span><span class="sxs-lookup"><span data-stu-id="dc60f-373">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="dc60f-374">contoso.com</span><span class="sxs-lookup"><span data-stu-id="dc60f-374">contoso.com</span></span>
  - <span data-ttu-id="dc60f-375">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="dc60f-375">contoso.com/a</span></span>
  - <span data-ttu-id="dc60f-376">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="dc60f-376">www.contoso.com</span></span>
  - <span data-ttu-id="dc60f-377">www.contoso.com/q=a@contoso.com</span><span class="sxs-lookup"><span data-stu-id="dc60f-377">www.contoso.com/q=a@contoso.com</span></span>

#### <a name="scenario-left-tilde"></a><span data-ttu-id="dc60f-378">Szenario: Linke Tilde</span><span class="sxs-lookup"><span data-stu-id="dc60f-378">Scenario: Left tilde</span></span>

<span data-ttu-id="dc60f-379">**Eintrag**: `~contoso.com`</span><span class="sxs-lookup"><span data-stu-id="dc60f-379">**Entry**: `~contoso.com`</span></span>

- <span data-ttu-id="dc60f-380">**Übereinstimmung zulassen** und **Übereinstimmung blockieren:**</span><span class="sxs-lookup"><span data-stu-id="dc60f-380">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="dc60f-381">contoso.com</span><span class="sxs-lookup"><span data-stu-id="dc60f-381">contoso.com</span></span>
  - <span data-ttu-id="dc60f-382">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="dc60f-382">www.contoso.com</span></span>
  - <span data-ttu-id="dc60f-383">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="dc60f-383">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="dc60f-384">**Nicht übereinstimmende** und **nicht übereinstimmende Blockierung** zulassen:</span><span class="sxs-lookup"><span data-stu-id="dc60f-384">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="dc60f-385">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="dc60f-385">123contoso.com</span></span>
  - <span data-ttu-id="dc60f-386">contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="dc60f-386">contoso.com/abc</span></span>
  - <span data-ttu-id="dc60f-387">www.contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="dc60f-387">www.contoso.com/abc</span></span>

#### <a name="scenario-right-wildcard-suffix"></a><span data-ttu-id="dc60f-388">Szenario: Rechtes Platzhaltersuffix</span><span class="sxs-lookup"><span data-stu-id="dc60f-388">Scenario: Right wildcard suffix</span></span>

<span data-ttu-id="dc60f-389">**Eintrag**: `contoso.com/*`</span><span class="sxs-lookup"><span data-stu-id="dc60f-389">**Entry**: `contoso.com/*`</span></span>

- <span data-ttu-id="dc60f-390">**Übereinstimmung zulassen** und **Übereinstimmung blockieren:**</span><span class="sxs-lookup"><span data-stu-id="dc60f-390">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="dc60f-391">contoso.com/?q=whatever@fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="dc60f-391">contoso.com/?q=whatever@fabrikam.com</span></span>
  - <span data-ttu-id="dc60f-392">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="dc60f-392">contoso.com/a</span></span>
  - <span data-ttu-id="dc60f-393">contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="dc60f-393">contoso.com/a/b/c</span></span>
  - <span data-ttu-id="dc60f-394">contoso.com/ab</span><span class="sxs-lookup"><span data-stu-id="dc60f-394">contoso.com/ab</span></span>
  - <span data-ttu-id="dc60f-395">contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="dc60f-395">contoso.com/b</span></span>
  - <span data-ttu-id="dc60f-396">contoso.com/b/a/c</span><span class="sxs-lookup"><span data-stu-id="dc60f-396">contoso.com/b/a/c</span></span>
  - <span data-ttu-id="dc60f-397">contoso.com/ba</span><span class="sxs-lookup"><span data-stu-id="dc60f-397">contoso.com/ba</span></span>

- <span data-ttu-id="dc60f-398">**Nicht übereinstimmende** und **nicht übereinstimmende Blockierung** zulassen: contoso.com</span><span class="sxs-lookup"><span data-stu-id="dc60f-398">**Allow not matched** and **Block not matched**: contoso.com</span></span>

#### <a name="scenario-left-wildcard-subdomain-and-right-wildcard-suffix"></a><span data-ttu-id="dc60f-399">Szenario: Linke Platzhalterunterdomäne und rechtes Platzhaltersuffix</span><span class="sxs-lookup"><span data-stu-id="dc60f-399">Scenario: Left wildcard subdomain and right wildcard suffix</span></span>

<span data-ttu-id="dc60f-400">**Eintrag**: `*.contoso.com/*`</span><span class="sxs-lookup"><span data-stu-id="dc60f-400">**Entry**: `*.contoso.com/*`</span></span>

- <span data-ttu-id="dc60f-401">**Übereinstimmung zulassen** und **Übereinstimmung blockieren:**</span><span class="sxs-lookup"><span data-stu-id="dc60f-401">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="dc60f-402">abc.contoso.com/ab</span><span class="sxs-lookup"><span data-stu-id="dc60f-402">abc.contoso.com/ab</span></span>
  - <span data-ttu-id="dc60f-403">abc.xyz.contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="dc60f-403">abc.xyz.contoso.com/a/b/c</span></span>
  - <span data-ttu-id="dc60f-404">www.contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="dc60f-404">www.contoso.com/a</span></span>
  - <span data-ttu-id="dc60f-405">www.contoso.com/b/a/c</span><span class="sxs-lookup"><span data-stu-id="dc60f-405">www.contoso.com/b/a/c</span></span>
  - <span data-ttu-id="dc60f-406">xyz.contoso.com/ba</span><span class="sxs-lookup"><span data-stu-id="dc60f-406">xyz.contoso.com/ba</span></span>

- <span data-ttu-id="dc60f-407">**Nicht übereinstimmende** und **nicht übereinstimmende Blockierung** zulassen: contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="dc60f-407">**Allow not matched** and **Block not matched**: contoso.com/b</span></span>

#### <a name="scenario-left-and-right-tilde"></a><span data-ttu-id="dc60f-408">Szenario: Linke und rechte Tilde</span><span class="sxs-lookup"><span data-stu-id="dc60f-408">Scenario: Left and right tilde</span></span>

<span data-ttu-id="dc60f-409">**Eintrag**: `~contoso.com~`</span><span class="sxs-lookup"><span data-stu-id="dc60f-409">**Entry**: `~contoso.com~`</span></span>

- <span data-ttu-id="dc60f-410">**Übereinstimmung zulassen** und **Übereinstimmung blockieren:**</span><span class="sxs-lookup"><span data-stu-id="dc60f-410">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="dc60f-411">contoso.com</span><span class="sxs-lookup"><span data-stu-id="dc60f-411">contoso.com</span></span>
  - <span data-ttu-id="dc60f-412">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="dc60f-412">contoso.com/a</span></span>
  - <span data-ttu-id="dc60f-413">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="dc60f-413">www.contoso.com</span></span>
  - <span data-ttu-id="dc60f-414">www.contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="dc60f-414">www.contoso.com/b</span></span>
  - <span data-ttu-id="dc60f-415">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="dc60f-415">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="dc60f-416">**Nicht übereinstimmende** und **nicht übereinstimmende Blockierung** zulassen:</span><span class="sxs-lookup"><span data-stu-id="dc60f-416">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="dc60f-417">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="dc60f-417">123contoso.com</span></span>
  - <span data-ttu-id="dc60f-418">contoso.org</span><span class="sxs-lookup"><span data-stu-id="dc60f-418">contoso.org</span></span>

#### <a name="scenario-ip-address"></a><span data-ttu-id="dc60f-419">Szenario: IP-Adresse</span><span class="sxs-lookup"><span data-stu-id="dc60f-419">Scenario: IP address</span></span>

<span data-ttu-id="dc60f-420">**Eintrag**: `1.2.3.4`</span><span class="sxs-lookup"><span data-stu-id="dc60f-420">**Entry**: `1.2.3.4`</span></span>

- <span data-ttu-id="dc60f-421">**Übereinstimmung zulassen** und **Übereinstimmung blockieren:** 1.2.3.4</span><span class="sxs-lookup"><span data-stu-id="dc60f-421">**Allow match** and **Block match**: 1.2.3.4</span></span>

- <span data-ttu-id="dc60f-422">**Nicht übereinstimmende** und **nicht übereinstimmende Blockierung** zulassen:</span><span class="sxs-lookup"><span data-stu-id="dc60f-422">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="dc60f-423">1.2.3.4/a</span><span class="sxs-lookup"><span data-stu-id="dc60f-423">1.2.3.4/a</span></span>
  - <span data-ttu-id="dc60f-424">11.2.3.4/a</span><span class="sxs-lookup"><span data-stu-id="dc60f-424">11.2.3.4/a</span></span>

#### <a name="ip-address-with-right-wildcard"></a><span data-ttu-id="dc60f-425">IP-Adresse mit rechtem Platzhalter</span><span class="sxs-lookup"><span data-stu-id="dc60f-425">IP address with right wildcard</span></span>

<span data-ttu-id="dc60f-426">**Eintrag**: `1.2.3.4/*`</span><span class="sxs-lookup"><span data-stu-id="dc60f-426">**Entry**: `1.2.3.4/*`</span></span>

- <span data-ttu-id="dc60f-427">**Übereinstimmung zulassen** und **Übereinstimmung blockieren:**</span><span class="sxs-lookup"><span data-stu-id="dc60f-427">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="dc60f-428">1.2.3.4/b</span><span class="sxs-lookup"><span data-stu-id="dc60f-428">1.2.3.4/b</span></span>
  - <span data-ttu-id="dc60f-429">1.2.3.4/baaaa</span><span class="sxs-lookup"><span data-stu-id="dc60f-429">1.2.3.4/baaaa</span></span>

### <a name="examples-of-invalid-entries"></a><span data-ttu-id="dc60f-430">Beispiele für ungültige Einträge</span><span class="sxs-lookup"><span data-stu-id="dc60f-430">Examples of invalid entries</span></span>

<span data-ttu-id="dc60f-431">Die folgenden Einträge sind ungültig:</span><span class="sxs-lookup"><span data-stu-id="dc60f-431">The following entries are invalid:</span></span>

- <span data-ttu-id="dc60f-432">**Fehlende oder ungültige Domänenwerte:**</span><span class="sxs-lookup"><span data-stu-id="dc60f-432">**Missing or invalid domain values**:</span></span>

  - <span data-ttu-id="dc60f-433">Contoso</span><span class="sxs-lookup"><span data-stu-id="dc60f-433">contoso</span></span>
  - <span data-ttu-id="dc60f-434">\*.contoso.\*</span><span class="sxs-lookup"><span data-stu-id="dc60f-434">\*.contoso.\*</span></span>
  - <span data-ttu-id="dc60f-435">\*.com</span><span class="sxs-lookup"><span data-stu-id="dc60f-435">\*.com</span></span>
  - <span data-ttu-id="dc60f-436">\*.pdf</span><span class="sxs-lookup"><span data-stu-id="dc60f-436">\*.pdf</span></span>

- <span data-ttu-id="dc60f-437">**Platzhalter für Text oder ohne Leerzeichen:**</span><span class="sxs-lookup"><span data-stu-id="dc60f-437">**Wildcard on text or without spacing characters**:</span></span>

  - <span data-ttu-id="dc60f-438">\*contoso.com</span><span class="sxs-lookup"><span data-stu-id="dc60f-438">\*contoso.com</span></span>
  - <span data-ttu-id="dc60f-439">contoso.com\*</span><span class="sxs-lookup"><span data-stu-id="dc60f-439">contoso.com\*</span></span>
  - <span data-ttu-id="dc60f-440">\*1.2.3.4</span><span class="sxs-lookup"><span data-stu-id="dc60f-440">\*1.2.3.4</span></span>
  - <span data-ttu-id="dc60f-441">1.2.3.4\*</span><span class="sxs-lookup"><span data-stu-id="dc60f-441">1.2.3.4\*</span></span>
  - <span data-ttu-id="dc60f-442">contoso.com/a\*</span><span class="sxs-lookup"><span data-stu-id="dc60f-442">contoso.com/a\*</span></span>
  - <span data-ttu-id="dc60f-443">contoso.com/ab\*</span><span class="sxs-lookup"><span data-stu-id="dc60f-443">contoso.com/ab\*</span></span>

- <span data-ttu-id="dc60f-444">**IP-Adressen mit Ports:**</span><span class="sxs-lookup"><span data-stu-id="dc60f-444">**IP addresses with ports**:</span></span>

  - <span data-ttu-id="dc60f-445">contoso.com:443</span><span class="sxs-lookup"><span data-stu-id="dc60f-445">contoso.com:443</span></span>
  - <span data-ttu-id="dc60f-446">abc.contoso.com:25</span><span class="sxs-lookup"><span data-stu-id="dc60f-446">abc.contoso.com:25</span></span>

- <span data-ttu-id="dc60f-447">**Nicht beschreibende Platzhalter:**</span><span class="sxs-lookup"><span data-stu-id="dc60f-447">**Non-descriptive wildcards**:</span></span>

  - \*
  - <span data-ttu-id="dc60f-448">\*.\*</span><span class="sxs-lookup"><span data-stu-id="dc60f-448">\*.\*</span></span>

- <span data-ttu-id="dc60f-449">**Mittlere Platzhalter:**</span><span class="sxs-lookup"><span data-stu-id="dc60f-449">**Middle wildcards**:</span></span>

  - <span data-ttu-id="dc60f-450">conto \* so.com</span><span class="sxs-lookup"><span data-stu-id="dc60f-450">conto\*so.com</span></span>
  - <span data-ttu-id="dc60f-451">conto~so.com</span><span class="sxs-lookup"><span data-stu-id="dc60f-451">conto~so.com</span></span>

- <span data-ttu-id="dc60f-452">**Doppelte Platzhalter**</span><span class="sxs-lookup"><span data-stu-id="dc60f-452">**Double wildcards**</span></span>

  - <span data-ttu-id="dc60f-453">contoso.com/\*\*</span><span class="sxs-lookup"><span data-stu-id="dc60f-453">contoso.com/\*\*</span></span>
  - <span data-ttu-id="dc60f-454">contoso.com/\*/\*</span><span class="sxs-lookup"><span data-stu-id="dc60f-454">contoso.com/\*/\*</span></span>

## <a name="domain-pair-syntax-for-spoofed-sender-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="dc60f-455">Domänenpaarsyntax für gefälschte Absendereinträge in der Mandanten-Zulassungs-/Sperrliste</span><span class="sxs-lookup"><span data-stu-id="dc60f-455">Domain pair syntax for spoofed sender entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="dc60f-456">Ein Domänenpaar für einen gefälschten Absender in der Mandanten-Zulassungs-/Sperrliste verwendet die folgende Syntax: `<Spoofed user>, <Sending infrastructure>` .</span><span class="sxs-lookup"><span data-stu-id="dc60f-456">A domain pair for a spoofed sender in the Tenant Allow/Block List uses the following syntax: `<Spoofed user>, <Sending infrastructure>`.</span></span>

- <span data-ttu-id="dc60f-457">**Gefälschter Benutzer:** Dieser Wert bezieht sich auf die E-Mail-Adresse des gefälschten Benutzers, der im **Feld "Von"** in E-Mail-Clients angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="dc60f-457">**Spoofed user**: This value involves the email address of the spoofed user that's displayed in the **From** box in email clients.</span></span> <span data-ttu-id="dc60f-458">Diese Adresse wird auch als `5322.From` Adresse bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="dc60f-458">This address is also known as the `5322.From` address.</span></span> <span data-ttu-id="dc60f-459">Gültige Werte sind:</span><span class="sxs-lookup"><span data-stu-id="dc60f-459">Valid values include:</span></span>
  - <span data-ttu-id="dc60f-460">Eine einzelne E-Mail-Adresse (z. B. chris@contoso.com).</span><span class="sxs-lookup"><span data-stu-id="dc60f-460">An individual email address (for example, chris@contoso.com).</span></span>
  - <span data-ttu-id="dc60f-461">Eine E-Mail-Domäne (z. B. contoso.com).</span><span class="sxs-lookup"><span data-stu-id="dc60f-461">An email domain (for example, contoso.com).</span></span>
  - <span data-ttu-id="dc60f-462">Das Platzhalterzeichen (z. B. \* ).</span><span class="sxs-lookup"><span data-stu-id="dc60f-462">The wildcard character (for example, \*).</span></span>

- <span data-ttu-id="dc60f-463">Senden der **Infrastruktur:** Dieser Wert gibt die Quelle von Nachrichten des gefälschten Benutzers an.</span><span class="sxs-lookup"><span data-stu-id="dc60f-463">**Sending infrastructure**: This value indicates the source of messages from the spoofed user.</span></span> <span data-ttu-id="dc60f-464">Gültige Werte sind:</span><span class="sxs-lookup"><span data-stu-id="dc60f-464">Valid values include:</span></span>
  - <span data-ttu-id="dc60f-465">Die Domäne in einer reversen DNS-Suche (PTR-Eintrag) der IP-Adresse des Quell-E-Mail-Servers (z. B. fabrikam.com).</span><span class="sxs-lookup"><span data-stu-id="dc60f-465">The domain found in a reverse DNS lookup (PTR record) of the source email server's IP address (for example, fabrikam.com).</span></span>
  - <span data-ttu-id="dc60f-466">Wenn die Quell-IP-Adresse keinen PTR-Eintrag aufweist, wird die sendende Infrastruktur als \<source IP\> /24 identifiziert (z. B. 192.168.100.100/24).</span><span class="sxs-lookup"><span data-stu-id="dc60f-466">If the source IP address has no PTR record, then the sending infrastructure is identified as \<source IP\>/24 (for example, 192.168.100.100/24).</span></span>

<span data-ttu-id="dc60f-467">Hier sind einige Beispiele für gültige Domänenpaare zum Identifizieren von gefälschten Absendern:</span><span class="sxs-lookup"><span data-stu-id="dc60f-467">Here are some examples of valid domain pairs to identify spoofed senders:</span></span>

- `contoso.com, 192.168.100.100/24`
- `chris@contoso.com, fabrikam.com`
- `*, contoso.net`

<span data-ttu-id="dc60f-468">Die maximale Anzahl von gefälschten Absendereinträgen beträgt 1000.</span><span class="sxs-lookup"><span data-stu-id="dc60f-468">The maximum number of spoofed sender entries is 1000.</span></span> 

<span data-ttu-id="dc60f-469">Das Hinzufügen eines Domänenpaars erlaubt oder blockiert nur die *Kombination aus* dem gefälschten Benutzer *und* der sendenden Infrastruktur.</span><span class="sxs-lookup"><span data-stu-id="dc60f-469">Adding a domain pair only allows or blocks the *combination* of the spoofed user *and* the sending infrastructure.</span></span> <span data-ttu-id="dc60f-470">Es erlaubt weder E-Mails vom gefälschten Benutzer aus einer Quelle noch E-Mails aus der sendenden Infrastrukturquelle für spoofierte Benutzer.</span><span class="sxs-lookup"><span data-stu-id="dc60f-470">It does not allow email from the spoofed user from any source, nor does it allow email from the sending infrastructure source for any spoofed user.</span></span> 

<span data-ttu-id="dc60f-471">Beispielsweise fügen Sie einen Zulassungseintrag für das folgende Domänenpaar hinzu:</span><span class="sxs-lookup"><span data-stu-id="dc60f-471">For example, you add an allow entry for the following domain pair:</span></span>

- <span data-ttu-id="dc60f-472">**Domäne:** gmail.com</span><span class="sxs-lookup"><span data-stu-id="dc60f-472">**Domain**: gmail.com</span></span>
- <span data-ttu-id="dc60f-473">**Infrastruktur:** tms.mx.com</span><span class="sxs-lookup"><span data-stu-id="dc60f-473">**Infrastructure**: tms.mx.com</span></span>

<span data-ttu-id="dc60f-474">Nur Nachrichten aus dieser Domäne *und* dem sendenden Infrastrukturpaar dürfen Spoofing ausführen.</span><span class="sxs-lookup"><span data-stu-id="dc60f-474">Only messages from that domain *and* sending infrastructure pair are allowed to spoof.</span></span> <span data-ttu-id="dc60f-475">Andere Absender, die versuchen, gmail.com zu spoofen, sind nicht zulässig.</span><span class="sxs-lookup"><span data-stu-id="dc60f-475">Other senders attempting to spoof gmail.com aren't allowed.</span></span> <span data-ttu-id="dc60f-476">Nachrichten von Absendern in anderen Domänen, die von tms.mx.com stammen, werden durch Spoofintelligenz überprüft.</span><span class="sxs-lookup"><span data-stu-id="dc60f-476">Messages from senders in other domains originating from tms.mx.com are checked by spoof intelligence.</span></span>
