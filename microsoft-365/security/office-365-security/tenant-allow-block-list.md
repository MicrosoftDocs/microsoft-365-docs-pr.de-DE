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
ms.openlocfilehash: 1548eda760b7b6b19214cb834d7fc43357dc0357
ms.sourcegitcommit: 34c06715e036255faa75c66ebf95c12a85f8ef42
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/17/2021
ms.locfileid: "52985492"
---
# <a name="manage-the-tenant-allowblock-list"></a><span data-ttu-id="ead22-103">Verwalten der Zulassungs-/Sperrliste des Mandanten</span><span class="sxs-lookup"><span data-stu-id="ead22-103">Manage the Tenant Allow/Block List</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="ead22-104">**Gilt für**</span><span class="sxs-lookup"><span data-stu-id="ead22-104">**Applies to**</span></span>
- [<span data-ttu-id="ead22-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="ead22-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="ead22-106">Microsoft Defender für Office 365 Plan 1 und Plan 2</span><span class="sxs-lookup"><span data-stu-id="ead22-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="ead22-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ead22-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

> [!NOTE]
>
> <span data-ttu-id="ead22-108">Die in diesem Artikel beschriebenen Features befinden sich in der Vorschau, können geändert werden und sind nicht in allen Organisationen verfügbar.</span><span class="sxs-lookup"><span data-stu-id="ead22-108">The features described in this article are in Preview, are subject to change, and are not available in all organizations.</span></span>  <span data-ttu-id="ead22-109">Wenn Ihre Organisation nicht über die in diesem Artikel beschriebenen Spoofingfeatures verfügt, lesen Sie die ältere Spoofverwaltungserfahrung unter [Verwalten von gefälschten Absendern mithilfe der Spoof Intelligence-Richtlinie und des Einblicks in spoofintelligenz in EOP.](walkthrough-spoof-intelligence-insight.md)</span><span class="sxs-lookup"><span data-stu-id="ead22-109">If your organization does not have the spoof features as described in this article, see the older spoof management experience at [Manage spoofed senders using the spoof intelligence policy and spoof intelligence insight in EOP](walkthrough-spoof-intelligence-insight.md).</span></span>
>
> <span data-ttu-id="ead22-110">Sie können derzeit keine zulässigen URL- oder Dateielemente in der Mandanten-Zulassungs-/Sperrliste **konfigurieren.**</span><span class="sxs-lookup"><span data-stu-id="ead22-110">You can't **configure** allowed URL or file items in the Tenant Allow/Block List at this time.</span></span>

<span data-ttu-id="ead22-111">In Microsoft 365 Organisationen mit Postfächern in Exchange Online oder eigenständigen Exchange Online Protection (EOP)-Organisationen ohne Exchange Online Postfächer, können Sie mit der EOP-Filterbewertung nicht einverstanden sein.</span><span class="sxs-lookup"><span data-stu-id="ead22-111">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, you might disagree with the EOP filtering verdict.</span></span> <span data-ttu-id="ead22-112">Beispielsweise kann eine gute Nachricht als falsch markiert werden (ein falsch positives Ergebnis), oder eine ungültige Nachricht kann durchgelassen werden (ein falsch negativer Wert).</span><span class="sxs-lookup"><span data-stu-id="ead22-112">For example, a good message might be marked as bad (a false positive), or a bad message might be allowed through (a false negative).</span></span>

<span data-ttu-id="ead22-113">Die Mandanten-Zulassungs-/Sperrliste im Microsoft 365 Defender-Portal bietet Ihnen die Möglichkeit, die Microsoft 365 Filterbewertungen manuell zu überschreiben.</span><span class="sxs-lookup"><span data-stu-id="ead22-113">The Tenant Allow/Block List in the Microsoft 365 Defender portal gives you a way to manually override the Microsoft 365 filtering verdicts.</span></span> <span data-ttu-id="ead22-114">Die Mandanten-Zulassungs-/Sperrliste wird während des Nachrichtenflusses und zum Zeitpunkt der Benutzerklicks verwendet.</span><span class="sxs-lookup"><span data-stu-id="ead22-114">The Tenant Allow/Block List is used during mail flow and at the time of user clicks.</span></span> <span data-ttu-id="ead22-115">Sie können die folgenden Arten von Außerkraftsetzungen angeben:</span><span class="sxs-lookup"><span data-stu-id="ead22-115">You can specify the following types of overrides:</span></span>

- <span data-ttu-id="ead22-116">Zu blockierende URLs.</span><span class="sxs-lookup"><span data-stu-id="ead22-116">URLs to block.</span></span>
- <span data-ttu-id="ead22-117">Zu blockierende Dateien.</span><span class="sxs-lookup"><span data-stu-id="ead22-117">Files to block.</span></span>
- <span data-ttu-id="ead22-118">Gefälschte Absender, die zugelassen oder blockiert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="ead22-118">Spoofed senders to allow or block.</span></span> <span data-ttu-id="ead22-119">Wenn Sie die Zulassungs- oder Blockbewertung im Einblick in die [Spoofintelligenz](learn-about-spoof-intelligence.md)außer Kraft setzen, wird der gefälschte Absender zu einem manuellen Zulassungs- oder Blockierungseintrag, der nur auf der Registerkarte **"Spoofing"** in der Mandanten-Zulassungs-/Sperrliste angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="ead22-119">If you override the allow or block verdict in the [spoof intelligence insight](learn-about-spoof-intelligence.md), the spoofed sender becomes a manual allow or block entry that only appears on the **Spoof** tab in the Tenant Allow/Block List.</span></span> <span data-ttu-id="ead22-120">Sie können hier auch manuell Zulassungseinträge für gefälschte Absender erstellen oder blockieren, bevor sie durch Spoofintelligenz erkannt werden.</span><span class="sxs-lookup"><span data-stu-id="ead22-120">You can also manually create allow or block entries for spoofed senders here before they're detected by spoof intelligence.</span></span>

<span data-ttu-id="ead22-121">In diesem Artikel wird beschrieben, wie Sie Einträge in der Mandanten-Zulassungs-/Sperrliste im Microsoft 365 Defender-Portal oder in PowerShell konfigurieren (Exchange Online PowerShell für Microsoft 365 Organisationen mit Postfächern in Exchange Online; eigenständige EOP PowerShell für Organisationen ohne Exchange Online Postfächer).</span><span class="sxs-lookup"><span data-stu-id="ead22-121">This article describes how to configure entries in the Tenant Allow/Block List in the Microsoft 365 Defender portal or in PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="ead22-122">Was sollten Sie wissen, bevor Sie beginnen?</span><span class="sxs-lookup"><span data-stu-id="ead22-122">What do you need to know before you begin?</span></span>

- <span data-ttu-id="ead22-123">Sie öffnen das Microsoft 365 Defender-Portal unter <https://security.microsoft.com/>.</span><span class="sxs-lookup"><span data-stu-id="ead22-123">You open the Microsoft 365 Defender portal at <https://security.microsoft.com/>.</span></span> <span data-ttu-id="ead22-124">Um direkt zur Seite **"Mandanten-Zulassungs-/Sperrlisten"** zu wechseln, verwenden Sie <https://security.microsoft.com/tenantAllowBlockList> .</span><span class="sxs-lookup"><span data-stu-id="ead22-124">To go directly to the **Tenant Allow/Block Lists** page, use <https://security.microsoft.com/tenantAllowBlockList>.</span></span>

- <span data-ttu-id="ead22-125">Sie geben Dateien mithilfe des SHA256-Hashwerts der Datei an.</span><span class="sxs-lookup"><span data-stu-id="ead22-125">You specify files by using the SHA256 hash value of the file.</span></span> <span data-ttu-id="ead22-126">Um den SHA256-Hashwert einer Datei in Windows zu finden, führen Sie den folgenden Befehl an einer Eingabeaufforderung aus:</span><span class="sxs-lookup"><span data-stu-id="ead22-126">To find the SHA256 hash value of a file in Windows, run the following command in a Command Prompt:</span></span>

  ```console
  certutil.exe -hashfile "<Path>\<Filename>" SHA256
  ```

  <span data-ttu-id="ead22-127">Ein Beispielwert ist `768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3a` .</span><span class="sxs-lookup"><span data-stu-id="ead22-127">An example value is `768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3a`.</span></span> <span data-ttu-id="ead22-128">Perceptual Hash (pHash)-Werte werden nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="ead22-128">Perceptual hash (pHash) values are not supported.</span></span>

- <span data-ttu-id="ead22-129">Die verfügbaren URL-Werte werden in der [URL-Syntax für den Abschnitt "Mandanten zulassen/blockieren"](#url-syntax-for-the-tenant-allowblock-list) weiter unten in diesem Artikel beschrieben.</span><span class="sxs-lookup"><span data-stu-id="ead22-129">The available URL values are described in the [URL syntax for the Tenant Allow/Block List](#url-syntax-for-the-tenant-allowblock-list) section later in this article.</span></span>

- <span data-ttu-id="ead22-130">Die Mandanten-Zulassungs-/Sperrliste lässt maximal 500 Einträge für URLs und 500 Einträge für Dateihashes zu.</span><span class="sxs-lookup"><span data-stu-id="ead22-130">The Tenant Allow/Block List allows a maximum of 500 entries for URLs, and 500 entries for file hashes.</span></span>

- <span data-ttu-id="ead22-131">Die maximale Anzahl von Zeichen für jeden Eintrag lautet:</span><span class="sxs-lookup"><span data-stu-id="ead22-131">The maximum number of characters for each entry is:</span></span>
  - <span data-ttu-id="ead22-132">Dateihashes = 64</span><span class="sxs-lookup"><span data-stu-id="ead22-132">File hashes = 64</span></span>
  - <span data-ttu-id="ead22-133">URL = 250</span><span class="sxs-lookup"><span data-stu-id="ead22-133">URL = 250</span></span>

- <span data-ttu-id="ead22-134">Ein Eintrag sollte innerhalb von 30 Minuten aktiv sein.</span><span class="sxs-lookup"><span data-stu-id="ead22-134">An entry should be active within 30 minutes.</span></span>

- <span data-ttu-id="ead22-135">Standardmäßig laufen Einträge in der Mandanten-Zulassungs-/Sperrliste nach 30 Tagen ab.</span><span class="sxs-lookup"><span data-stu-id="ead22-135">By default, entries in the Tenant Allow/Block List will expire after 30 days.</span></span> <span data-ttu-id="ead22-136">Sie können ein Datum angeben oder festlegen, dass es nie abläuft.</span><span class="sxs-lookup"><span data-stu-id="ead22-136">You can specify a date or set them to never expire.</span></span>

- <span data-ttu-id="ead22-137">Wie Sie eine Verbindung mit Exchange Online PowerShell herstellen, finden Sie unter [Herstellen einer Verbindung mit Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="ead22-137">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="ead22-138">Informationen zum Herstellen einer Verbindung mit dem eigenständigen Exchange Online Protection PowerShell finden Sie unter [Verbinden mit PowerShell in Exchange Online Protection](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="ead22-138">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="ead22-139">Sie müssen in Exchange Online Berechtigungen erhalten, bevor Sie die in diesem Artikel beschriebenen Schritte ausführen können:</span><span class="sxs-lookup"><span data-stu-id="ead22-139">You need to be assigned permissions in Exchange Online before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="ead22-140">**URLs und Dateien:**</span><span class="sxs-lookup"><span data-stu-id="ead22-140">**URLs and files**:</span></span>
    - <span data-ttu-id="ead22-141">Um Werte aus der Mandanten-Zulassungs-/Sperrliste hinzuzufügen und zu entfernen, müssen Sie Mitglied der Rollengruppen **"Organisationsverwaltung"** oder **"Sicherheitsadministrator"** sein.</span><span class="sxs-lookup"><span data-stu-id="ead22-141">To add and remove values from the Tenant Allow/Block List, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
    - <span data-ttu-id="ead22-142">Für den schreibgeschützten Zugriff auf die Mandanten-Zulassungs-/Sperrliste müssen Sie Mitglied der Rollengruppe **"Globaler Leser"** oder **"Sicherheitsleseberechtigter"** sein.</span><span class="sxs-lookup"><span data-stu-id="ead22-142">For read-only access to the Tenant Allow/Block List, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>
  - <span data-ttu-id="ead22-143">**Spoofing:** Eine der folgenden Kombinationen:</span><span class="sxs-lookup"><span data-stu-id="ead22-143">**Spoofing**: One of the following combinations:</span></span>
    - <span data-ttu-id="ead22-144">**Organisationsverwaltung**</span><span class="sxs-lookup"><span data-stu-id="ead22-144">**Organization Management**</span></span>
    - <span data-ttu-id="ead22-145">**Sicherheitsadministrator** <u>und</u> **Nur-Ansicht-Konfiguration** oder **Nur-Ansicht-Organisationsverwaltung**.</span><span class="sxs-lookup"><span data-stu-id="ead22-145">**Security Administrator** <u>and</u> **View-Only Configuration** or **View-Only Organization Management**.</span></span>

  <span data-ttu-id="ead22-146">Weitere Informationen finden Sie unter [Berechtigungen in Exchange Online](/exchange/permissions-exo/permissions-exo).</span><span class="sxs-lookup"><span data-stu-id="ead22-146">For more information, see [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo).</span></span>

  > [!NOTE]
  >
  > - <span data-ttu-id="ead22-147">Durch das Hinzufügen von Benutzern zur entsprechenden Azure Active Directory-Rolle im Microsoft 365 Admin Center erhalten Benutzer die erforderlichen Berechtigungen _und_ Berechtigungen für andere Features in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="ead22-147">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="ead22-148">Weitere Informationen finden Sie unter [Informationen zu Administratorrollen](../../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="ead22-148">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  >
  > - <span data-ttu-id="ead22-149">Die Rollengruppe **Organisationsverwaltung mit Leserechten** in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) ermöglicht auch einen schreibgeschützten Zugriff auf das Feature.</span><span class="sxs-lookup"><span data-stu-id="ead22-149">The **View-Only Organization Management** role group in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-create-block-url-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="ead22-150">Verwenden des Microsoft 365 Defender Portals zum Erstellen von Block-URL-Einträgen in der Mandanten-Zulassungs-/Sperrliste</span><span class="sxs-lookup"><span data-stu-id="ead22-150">Use the Microsoft 365 Defender portal to create block URL entries in the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="ead22-151">Wechseln Sie im Portal Microsoft 365 Defender zu **Richtlinien & Regel** \> **für Bedrohungsrichtlinien** \>  Abschnitt \> **"Mandanten-Zulassungs-/Sperrlisten".**</span><span class="sxs-lookup"><span data-stu-id="ead22-151">In the Microsoft 365 Defender portal, go to **Policies & rules** \> **Threat Policies** \> **Rules** section \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="ead22-152">Überprüfen Sie auf der Seite **"Mandanten-Zulassungs-/Sperrliste",** ob die Registerkarte **"URLs"** ausgewählt ist, und klicken Sie dann auf ![ das Symbol ](../../media/m365-cc-sc-create-icon.png) **"Blockieren".**</span><span class="sxs-lookup"><span data-stu-id="ead22-152">On the **Tenant Allow/Block List** page, verify that the **URLs** tab is selected, and then click ![Block icon](../../media/m365-cc-sc-create-icon.png) **Block**.</span></span>

3. <span data-ttu-id="ead22-153">Konfigurieren Sie im angezeigten Flyout **"URLs blockieren"** die folgenden Einstellungen:</span><span class="sxs-lookup"><span data-stu-id="ead22-153">In the **Block URLs** flyout that appears, configure the following settings:</span></span>
   - <span data-ttu-id="ead22-154">**Hinzufügen von URLs mit Platzhaltern:** Geben Sie eine URL pro Zeile ein, maximal 20.</span><span class="sxs-lookup"><span data-stu-id="ead22-154">**Add URLs with wildcards**: Enter one URL per line, up to a maximum of 20.</span></span> <span data-ttu-id="ead22-155">Ausführliche Informationen zur Syntax für URL-Einträge finden Sie in der [URL-Syntax für den Abschnitt "Mandanten-Zulassungs-/Sperrliste"](#url-syntax-for-the-tenant-allowblock-list) weiter unten in diesem Artikel.</span><span class="sxs-lookup"><span data-stu-id="ead22-155">For details about the syntax for URL entries, see the [URL syntax for the Tenant Allow/Block List](#url-syntax-for-the-tenant-allowblock-list) section later in this article.</span></span>
   - <span data-ttu-id="ead22-156">**Läuft nie ab:** Führen Sie einen der folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="ead22-156">**Never expire**: Do one of the following steps:</span></span>
     - <span data-ttu-id="ead22-157">Stellen Sie sicher, dass die Einstellung deaktiviert ist ( ![ Umschalten ](../../media/scc-toggle-off.png) ) und verwenden Sie das Feld **"Entfernen** auf", um das Ablaufdatum für die Einträge anzugeben.</span><span class="sxs-lookup"><span data-stu-id="ead22-157">Verify the setting is turned off (![Toggle off](../../media/scc-toggle-off.png)) and use the **Remove on** box to specify the expiration date for the entries.</span></span>

       <span data-ttu-id="ead22-158">oder</span><span class="sxs-lookup"><span data-stu-id="ead22-158">or</span></span>

     - <span data-ttu-id="ead22-159">Verschieben Sie den Umschalter nach rechts, um die Einträge so zu konfigurieren, dass sie nie ablaufen:</span><span class="sxs-lookup"><span data-stu-id="ead22-159">Move the toggle to the right to configure the entries to never expire:</span></span> ![Umschaltfläche ein](../../media/scc-toggle-on.png)<span data-ttu-id="ead22-161">.</span><span class="sxs-lookup"><span data-stu-id="ead22-161">.</span></span>
   - <span data-ttu-id="ead22-162">**Optionaler Hinweis:** Geben Sie beschreibenden Text für die Einträge ein.</span><span class="sxs-lookup"><span data-stu-id="ead22-162">**Optional note**: Enter descriptive text for the entries.</span></span>

4. <span data-ttu-id="ead22-163">Klicken Sie nach Abschluss des Vorgangs auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="ead22-163">When you're finished, click **Add**.</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-create-block-file-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="ead22-164">Verwenden des Microsoft 365 Defender-Portals zum Erstellen von Blockierungsdateieinträgen in der Mandanten-Zulassungs-/Sperrliste</span><span class="sxs-lookup"><span data-stu-id="ead22-164">Use the Microsoft 365 Defender portal to create block file entries in the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="ead22-165">Wechseln Sie im Portal Microsoft 365 Defender zu **Richtlinien & Regel** \> **für Bedrohungsrichtlinien** \>  Abschnitt \> **"Mandanten-Zulassungs-/Sperrlisten".**</span><span class="sxs-lookup"><span data-stu-id="ead22-165">In the Microsoft 365 Defender portal, go to **Policies & rules** \> **Threat Policies** \> **Rules** section \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="ead22-166">Wählen Sie auf der Seite **"Mandanten-Zulassungs-/Sperrliste"** die Registerkarte **"Dateien"** aus, und klicken Sie dann auf ![ das Symbol ](../../media/m365-cc-sc-create-icon.png) **"Blockieren".**</span><span class="sxs-lookup"><span data-stu-id="ead22-166">On the **Tenant Allow/Block List** page, select the **Files** tab, and then click ![Block icon](../../media/m365-cc-sc-create-icon.png) **Block**.</span></span>

3. <span data-ttu-id="ead22-167">Konfigurieren Sie im angezeigten Flyout **"Dateien blockieren"** die folgenden Einstellungen:</span><span class="sxs-lookup"><span data-stu-id="ead22-167">In the **Block files** flyout that appears, configure the following settings:</span></span>
   - <span data-ttu-id="ead22-168">**Hinzufügen von Dateihashes:** Geben Sie einen SHA256-Hashwert pro Zeile ein, bis maximal 20.</span><span class="sxs-lookup"><span data-stu-id="ead22-168">**Add file hashes**: Enter one SHA256 hash value per line, up to a maximum of 20.</span></span>
   - <span data-ttu-id="ead22-169">**Läuft nie ab:** Führen Sie einen der folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="ead22-169">**Never expire**: Do one of the following steps:</span></span>
     - <span data-ttu-id="ead22-170">Stellen Sie sicher, dass die Einstellung deaktiviert ist ( ![ Umschalten ](../../media/scc-toggle-off.png) ) und verwenden Sie das Feld **"Entfernen** auf", um das Ablaufdatum für die Einträge anzugeben.</span><span class="sxs-lookup"><span data-stu-id="ead22-170">Verify the setting is turned off (![Toggle off](../../media/scc-toggle-off.png)) and use the **Remove on** box to specify the expiration date for the entries.</span></span>

     <span data-ttu-id="ead22-171">oder</span><span class="sxs-lookup"><span data-stu-id="ead22-171">or</span></span>

     - <span data-ttu-id="ead22-172">Verschieben Sie den Umschalter nach rechts, um die Einträge so zu konfigurieren, dass sie nie ablaufen:</span><span class="sxs-lookup"><span data-stu-id="ead22-172">Move the toggle to the right to configure the entries to never expire:</span></span> ![Umschaltfläche ein](../../media/scc-toggle-on.png)<span data-ttu-id="ead22-174">.</span><span class="sxs-lookup"><span data-stu-id="ead22-174">.</span></span>
   - <span data-ttu-id="ead22-175">**Optionaler Hinweis:** Geben Sie beschreibenden Text für die Einträge ein.</span><span class="sxs-lookup"><span data-stu-id="ead22-175">**Optional note**: Enter descriptive text for the entries.</span></span>

4. <span data-ttu-id="ead22-176">Klicken Sie nach Abschluss des Vorgangs auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="ead22-176">When you're finished, click **Add**.</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-create-allow-or-block-spoofed-sender-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="ead22-177">Verwenden sie das Microsoft 365 Defender Portal, um Zulassungs- oder Sperreinträge von gefälschten Absendern in der Mandanten-Zulassungs-/Sperrliste zu erstellen oder zu blockieren.</span><span class="sxs-lookup"><span data-stu-id="ead22-177">Use the Microsoft 365 Defender portal to create allow or block spoofed sender entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="ead22-178">**Hinweise**:</span><span class="sxs-lookup"><span data-stu-id="ead22-178">**Notes**:</span></span>

- <span data-ttu-id="ead22-179">Nur die _Kombination aus_ dem gefälschten Benutzer _und_ der sendenden Infrastruktur, wie im Domänenpaar definiert, ist ausdrücklich zulässig oder am Spoofing gehindert.</span><span class="sxs-lookup"><span data-stu-id="ead22-179">Only the _combination_ of the spoofed user _and_ the sending infrastructure as defined in the domain pair is specifically allowed or blocked from spoofing.</span></span>
- <span data-ttu-id="ead22-180">Wenn Sie einen Zulassungs- oder Blockeintrag für ein Domänenpaar konfigurieren, werden Nachrichten von diesem Domänenpaar nicht mehr in der Spoofintelligenz angezeigt.</span><span class="sxs-lookup"><span data-stu-id="ead22-180">When you configure an allow or block entry for a domain pair, messages from that domain pair no longer appear in the spoof intelligence insight.</span></span>
- <span data-ttu-id="ead22-181">Einträge für gefälschte Absender laufen nie ab.</span><span class="sxs-lookup"><span data-stu-id="ead22-181">Entries for spoofed senders never expire.</span></span>

1. <span data-ttu-id="ead22-182">Wechseln Sie im Portal Microsoft 365 Defender zu **Richtlinien & Regel** \> **für Bedrohungsrichtlinien** \>  Abschnitt \> **"Mandanten-Zulassungs-/Sperrlisten".**</span><span class="sxs-lookup"><span data-stu-id="ead22-182">In the Microsoft 365 Defender portal, go to **Policies & rules** \> **Threat Policies** \> **Rules** section \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="ead22-183">Wählen Sie auf der Seite **"Mandanten-Zulassungs-/Sperrliste"** die Registerkarte **"Spoofing"** aus, und klicken Sie dann auf ![ das Symbol ](../../media/m365-cc-sc-create-icon.png) **"Blockieren" hinzufügen.**</span><span class="sxs-lookup"><span data-stu-id="ead22-183">On the **Tenant Allow/Block List** page, select the **Spoofing** tab, and then click ![Block icon](../../media/m365-cc-sc-create-icon.png) **Add**.</span></span>

3. <span data-ttu-id="ead22-184">Konfigurieren Sie im angezeigten Flyout **"Neue Domänenpaare hinzufügen"** die folgenden Einstellungen:</span><span class="sxs-lookup"><span data-stu-id="ead22-184">In the **Add new domain pairs** flyout that appears, configure the following settings:</span></span>
   - <span data-ttu-id="ead22-185">**Hinzufügen neuer Domänenpaare mit Platzhaltern:** Geben Sie ein Domänenpaar pro Zeile ein, maximal 20.</span><span class="sxs-lookup"><span data-stu-id="ead22-185">**Add new domain pairs with wildcards**: Enter one domain pair per line, up to a maximum of 20.</span></span> <span data-ttu-id="ead22-186">Ausführliche Informationen zur Syntax für spoofierte Absendereinträge finden Sie in der [Domänenpaarsyntax für spoofierte Absendereinträge im Abschnitt "Mandanten-Zulassungs-/Sperrliste"](#domain-pair-syntax-for-spoofed-sender-entries-in-the-tenant-allowblock-list) weiter unten in diesem Artikel.</span><span class="sxs-lookup"><span data-stu-id="ead22-186">For details about the syntax for spoofed sender entries, see the [Domain pair syntax for spoofed sender entries in the Tenant Allow/Block List](#domain-pair-syntax-for-spoofed-sender-entries-in-the-tenant-allowblock-list) section later in this article.</span></span>
   - <span data-ttu-id="ead22-187">**Spooftyp:** Wählen Sie einen der folgenden Werte aus:</span><span class="sxs-lookup"><span data-stu-id="ead22-187">**Spoof type**: Select one of the following values:</span></span>
     - <span data-ttu-id="ead22-188">**Intern:** Der gefälschte Absender befindet sich in einer Domäne, die zu Ihrer Organisation gehört (einer [akzeptierten Domäne).](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)</span><span class="sxs-lookup"><span data-stu-id="ead22-188">**Internal**: The spoofed sender is in a domain that belongs to your organization (an [accepted domain](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)).</span></span>
     - <span data-ttu-id="ead22-189">**Extern:** Der gefälschte Absender befindet sich in einer externen Domäne.</span><span class="sxs-lookup"><span data-stu-id="ead22-189">**External**: The spoofed sender is in an external domain.</span></span>
   - <span data-ttu-id="ead22-190">**Aktion:** Wählen Sie **"Zulassen"** oder **"Blockieren"** aus.</span><span class="sxs-lookup"><span data-stu-id="ead22-190">**Action**: Select **Allow** or **Block**.</span></span>

4. <span data-ttu-id="ead22-191">Klicken Sie nach Abschluss des Vorgangs auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="ead22-191">When you're finished, click **Add**.</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-view-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="ead22-192">Verwenden des Microsoft 365 Defender Portals zum Anzeigen von Einträgen in der Mandanten-Zulassungs-/Sperrliste</span><span class="sxs-lookup"><span data-stu-id="ead22-192">Use the Microsoft 365 Defender portal to view entries in the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="ead22-193">Wechseln Sie im Portal Microsoft 365 Defender zu **Richtlinien & Regel** \> **für Bedrohungsrichtlinien** \>  Abschnitt \> **"Mandanten-Zulassungs-/Sperrlisten".**</span><span class="sxs-lookup"><span data-stu-id="ead22-193">In the Microsoft 365 Defender portal, go to **Policies & rules** \> **Threat Policies** \> **Rules** section \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="ead22-194">Wählen Sie die gewünschte Registerkarte aus.</span><span class="sxs-lookup"><span data-stu-id="ead22-194">Select the tab you want.</span></span> <span data-ttu-id="ead22-195">Welche Spalten verfügbar sind, hängt von der ausgewählten Registerkarte ab:</span><span class="sxs-lookup"><span data-stu-id="ead22-195">The columns that are available depend on the tab you selected:</span></span>

   - <span data-ttu-id="ead22-196">**URLs:**</span><span class="sxs-lookup"><span data-stu-id="ead22-196">**URLs**:</span></span>
     - <span data-ttu-id="ead22-197">**Wert:** Die URL.</span><span class="sxs-lookup"><span data-stu-id="ead22-197">**Value**: The URL.</span></span>
     - <span data-ttu-id="ead22-198">**Aktion:** Der Wert **Block**.</span><span class="sxs-lookup"><span data-stu-id="ead22-198">**Action**: The value **Block**.</span></span>
     - <span data-ttu-id="ead22-199">**Zuletzt aktualisiert**</span><span class="sxs-lookup"><span data-stu-id="ead22-199">**Last updated**</span></span>
     - <span data-ttu-id="ead22-200">**Entfernen von "On"**</span><span class="sxs-lookup"><span data-stu-id="ead22-200">**Remove on**</span></span>
     - <span data-ttu-id="ead22-201">**Notizen**</span><span class="sxs-lookup"><span data-stu-id="ead22-201">**Notes**</span></span>
   - <span data-ttu-id="ead22-202">**Files**</span><span class="sxs-lookup"><span data-stu-id="ead22-202">**Files**</span></span>
     - <span data-ttu-id="ead22-203">**Wert:** Der Dateihash.</span><span class="sxs-lookup"><span data-stu-id="ead22-203">**Value**: The file hash.</span></span>
     - <span data-ttu-id="ead22-204">**Aktion:** Der Wert **Block**.</span><span class="sxs-lookup"><span data-stu-id="ead22-204">**Action**: The value **Block**.</span></span>
     - <span data-ttu-id="ead22-205">**Zuletzt aktualisiert**</span><span class="sxs-lookup"><span data-stu-id="ead22-205">**Last updated**</span></span>
     - <span data-ttu-id="ead22-206">**Entfernen von "On"**</span><span class="sxs-lookup"><span data-stu-id="ead22-206">**Remove on**</span></span>
     - <span data-ttu-id="ead22-207">**Notizen**</span><span class="sxs-lookup"><span data-stu-id="ead22-207">**Notes**</span></span>
   - <span data-ttu-id="ead22-208">**Spoofing**</span><span class="sxs-lookup"><span data-stu-id="ead22-208">**Spoofing**</span></span>
     - <span data-ttu-id="ead22-209">**Gefälschter Benutzer**</span><span class="sxs-lookup"><span data-stu-id="ead22-209">**Spoofed user**</span></span>
     - <span data-ttu-id="ead22-210">**Senden der Infrastruktur**</span><span class="sxs-lookup"><span data-stu-id="ead22-210">**Sending infrastructure**</span></span>
     - <span data-ttu-id="ead22-211">**Spooftyp:** Der Wert **Internal** oder **External**.</span><span class="sxs-lookup"><span data-stu-id="ead22-211">**Spoof type**: The value **Internal** or **External**.</span></span>
     - <span data-ttu-id="ead22-212">**Aktion:** Der Wert **Block** oder **Allow**.</span><span class="sxs-lookup"><span data-stu-id="ead22-212">**Action**: The value **Block** or **Allow**.</span></span>

   <span data-ttu-id="ead22-213">Sie können auf eine Spaltenüberschrift klicken, um sie in aufsteigender oder absteigender Reihenfolge zu sortieren.</span><span class="sxs-lookup"><span data-stu-id="ead22-213">You can click on a column heading to sort in ascending or descending order.</span></span>

   <span data-ttu-id="ead22-214">Sie können auf **"Gruppieren"** klicken, um die Ergebnisse zu gruppieren.</span><span class="sxs-lookup"><span data-stu-id="ead22-214">You can click **Group** to group the results.</span></span> <span data-ttu-id="ead22-215">Die verfügbaren Werte hängen von der ausgewählten Registerkarte ab:</span><span class="sxs-lookup"><span data-stu-id="ead22-215">The values that are available depend on the tab you selected:</span></span>

   - <span data-ttu-id="ead22-216">**URLs:** Sie können die Ergebnisse nach **Aktion** gruppieren.</span><span class="sxs-lookup"><span data-stu-id="ead22-216">**URLs**: You can group the results by **Action**.</span></span>
   - <span data-ttu-id="ead22-217">**Dateien:** Sie können die Ergebnisse nach **Aktion** gruppieren.</span><span class="sxs-lookup"><span data-stu-id="ead22-217">**Files**: You can group the results by **Action**.</span></span>
   - <span data-ttu-id="ead22-218">**Spoofing:** Sie können die Ergebnisse nach **Aktions-** oder **Spooftyp** gruppieren.</span><span class="sxs-lookup"><span data-stu-id="ead22-218">**Spoofing**: You can group the results by **Action** or **Spoof type**.</span></span>

   <span data-ttu-id="ead22-219">Klicken Sie auf **"Suchen",** geben Sie einen Wert ganz oder teilweise ein, und drücken Sie dann die EINGABETASTE, um einen bestimmten Wert zu finden.</span><span class="sxs-lookup"><span data-stu-id="ead22-219">Click **Search**, enter all or part of a value, and then press ENTER to find a specific value.</span></span> <span data-ttu-id="ead22-220">Wenn Sie fertig sind, klicken Sie auf ![ Suchsymbol löschen ](../../media/m365-cc-sc-close-icon.png) **.**</span><span class="sxs-lookup"><span data-stu-id="ead22-220">When you're finished, click ![Clear search icon](../../media/m365-cc-sc-close-icon.png) **Clear search**.</span></span>

   <span data-ttu-id="ead22-221">Klicken Sie auf **"Filtern",** um die Ergebnisse zu filtern.</span><span class="sxs-lookup"><span data-stu-id="ead22-221">Click **Filter** to filter the results.</span></span> <span data-ttu-id="ead22-222">Die werte, die  im angezeigten Filter-Flyout verfügbar sind, hängen von der ausgewählten Registerkarte ab:</span><span class="sxs-lookup"><span data-stu-id="ead22-222">The values that are available in **Filter** flyout that appears depend on the tab you selected:</span></span>

   - <span data-ttu-id="ead22-223">**Urls**</span><span class="sxs-lookup"><span data-stu-id="ead22-223">**URLs**</span></span>
     - <span data-ttu-id="ead22-224">**Action**</span><span class="sxs-lookup"><span data-stu-id="ead22-224">**Action**</span></span>
     - <span data-ttu-id="ead22-225">**Nie ablaufen**</span><span class="sxs-lookup"><span data-stu-id="ead22-225">**Never expire**</span></span>
     - <span data-ttu-id="ead22-226">**Datum der letzten Aktualisierung**</span><span class="sxs-lookup"><span data-stu-id="ead22-226">**Last updated date**</span></span>
     - <span data-ttu-id="ead22-227">**Entfernen von "On"**</span><span class="sxs-lookup"><span data-stu-id="ead22-227">**Remove on**</span></span>
   - <span data-ttu-id="ead22-228">**Files**</span><span class="sxs-lookup"><span data-stu-id="ead22-228">**Files**</span></span>
     - <span data-ttu-id="ead22-229">**Action**</span><span class="sxs-lookup"><span data-stu-id="ead22-229">**Action**</span></span>
     - <span data-ttu-id="ead22-230">**Nie ablaufen**</span><span class="sxs-lookup"><span data-stu-id="ead22-230">**Never expire**</span></span>
     - <span data-ttu-id="ead22-231">**Zuletzt aktualisiert**</span><span class="sxs-lookup"><span data-stu-id="ead22-231">**Last updated**</span></span>
     - <span data-ttu-id="ead22-232">**Entfernen von "On"**</span><span class="sxs-lookup"><span data-stu-id="ead22-232">**Remove on**</span></span>
   - <span data-ttu-id="ead22-233">**Spoofing**</span><span class="sxs-lookup"><span data-stu-id="ead22-233">**Spoofing**</span></span>
     - <span data-ttu-id="ead22-234">**Action**</span><span class="sxs-lookup"><span data-stu-id="ead22-234">**Action**</span></span>
     - <span data-ttu-id="ead22-235">**Spooftyp**</span><span class="sxs-lookup"><span data-stu-id="ead22-235">**Spoof type**</span></span>

   <span data-ttu-id="ead22-236">Wenn Sie fertig sind, klicken Sie auf **"Übernehmen".**</span><span class="sxs-lookup"><span data-stu-id="ead22-236">When you're finished, click **Apply**.</span></span> <span data-ttu-id="ead22-237">Klicken Sie zum Löschen vorhandener Filter auf **"Filter",** und klicken Sie im angezeigten **Flyout "Filter"** auf **"Filter löschen".**</span><span class="sxs-lookup"><span data-stu-id="ead22-237">To clear existing filters, click **Filter**, and in the **Filter** flyout that appears, click **Clear filters**.</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-modify-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="ead22-238">Verwenden des Microsoft 365 Defender Portals zum Ändern von Einträgen in der Mandanten-Zulassungs-/Sperrliste</span><span class="sxs-lookup"><span data-stu-id="ead22-238">Use the Microsoft 365 Defender portal to modify entries in the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="ead22-239">Wechseln Sie im Portal Microsoft 365 Defender zu **Richtlinien & Regel** \> **für Bedrohungsrichtlinien** \>  Abschnitt \> **"Mandanten-Zulassungs-/Sperrlisten".**</span><span class="sxs-lookup"><span data-stu-id="ead22-239">In the Microsoft 365 Defender portal, go to **Policies & rules** \> **Threat Policies** \> **Rules** section \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="ead22-240">Wählen Sie die Registerkarte aus, die den Eintragstyp enthält, den Sie ändern möchten:</span><span class="sxs-lookup"><span data-stu-id="ead22-240">Select the tab that contains the type of entry that you want to modify:</span></span>
   - <span data-ttu-id="ead22-241">**Urls**</span><span class="sxs-lookup"><span data-stu-id="ead22-241">**URLs**</span></span>
   - <span data-ttu-id="ead22-242">**Files**</span><span class="sxs-lookup"><span data-stu-id="ead22-242">**Files**</span></span>
   - <span data-ttu-id="ead22-243">**Spoofing**</span><span class="sxs-lookup"><span data-stu-id="ead22-243">**Spoofing**</span></span>

3. <span data-ttu-id="ead22-244">Wählen Sie den Eintrag aus, den Sie ändern möchten, und klicken Sie dann auf ![ ](../../media/m365-cc-sc-edit-icon.png) **"Bearbeiten".**</span><span class="sxs-lookup"><span data-stu-id="ead22-244">Select the entry that you want to modify, and then click ![Edit icon](../../media/m365-cc-sc-edit-icon.png) **Edit**.</span></span> <span data-ttu-id="ead22-245">Die Werte, die Sie im angezeigten Flyout ändern können, hängen von der Registerkarte ab, die Sie im vorherigen Schritt ausgewählt haben:</span><span class="sxs-lookup"><span data-stu-id="ead22-245">The values that you are able to modify in the flyout that appears depend on the tab you selected in the previous step:</span></span>
   - <span data-ttu-id="ead22-246">**Urls**</span><span class="sxs-lookup"><span data-stu-id="ead22-246">**URLs**</span></span>
     - <span data-ttu-id="ead22-247">**Nie ablaufen** und/oder Ablaufdatum.</span><span class="sxs-lookup"><span data-stu-id="ead22-247">**Never expire** and/or expiration date.</span></span>
     - <span data-ttu-id="ead22-248">**Optionaler Hinweis**</span><span class="sxs-lookup"><span data-stu-id="ead22-248">**Optional note**</span></span>
   - <span data-ttu-id="ead22-249">**Files**</span><span class="sxs-lookup"><span data-stu-id="ead22-249">**Files**</span></span>
     - <span data-ttu-id="ead22-250">**Nie ablaufen** und/oder Ablaufdatum.</span><span class="sxs-lookup"><span data-stu-id="ead22-250">**Never expire** and/or expiration date.</span></span>
     - <span data-ttu-id="ead22-251">**Optionaler Hinweis**</span><span class="sxs-lookup"><span data-stu-id="ead22-251">**Optional note**</span></span>
   - <span data-ttu-id="ead22-252">**Spoofing**</span><span class="sxs-lookup"><span data-stu-id="ead22-252">**Spoofing**</span></span>
     - <span data-ttu-id="ead22-253">**Aktion:** Sie können den Wert in **Zulassen** oder **Blockieren** ändern.</span><span class="sxs-lookup"><span data-stu-id="ead22-253">**Action**: You can change the value to **Allow** or **Block**.</span></span>
4. <span data-ttu-id="ead22-254">Klicken Sie nach Abschluss des Vorgangs auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="ead22-254">When you're finished, click **Save**.</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-remove-entries-from-the-tenant-allowblock-list"></a><span data-ttu-id="ead22-255">Verwenden des Microsoft 365 Defender Portals zum Entfernen von Einträgen aus der Mandanten-Zulassungs-/Sperrliste</span><span class="sxs-lookup"><span data-stu-id="ead22-255">Use the Microsoft 365 Defender portal to remove entries from the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="ead22-256">Wechseln Sie im Portal Microsoft 365 Defender zu **Richtlinien & Regel** \> **für Bedrohungsrichtlinien** \>  Abschnitt \> **"Mandanten-Zulassungs-/Sperrlisten".**</span><span class="sxs-lookup"><span data-stu-id="ead22-256">In the Microsoft 365 Defender portal, go to **Policies & rules** \> **Threat Policies** \> **Rules** section \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="ead22-257">Wählen Sie die Registerkarte aus, die den Eintragstyp enthält, den Sie entfernen möchten:</span><span class="sxs-lookup"><span data-stu-id="ead22-257">Select the tab that contains the type of entry that you want to remove:</span></span>
   - <span data-ttu-id="ead22-258">**Urls**</span><span class="sxs-lookup"><span data-stu-id="ead22-258">**URLs**</span></span>
   - <span data-ttu-id="ead22-259">**Files**</span><span class="sxs-lookup"><span data-stu-id="ead22-259">**Files**</span></span>
   - <span data-ttu-id="ead22-260">**Spoofing**</span><span class="sxs-lookup"><span data-stu-id="ead22-260">**Spoofing**</span></span>

3. <span data-ttu-id="ead22-261">Wählen Sie den Eintrag aus, den Sie entfernen möchten, und klicken Sie dann auf ![ ](../../media/m365-cc-sc-delete-icon.png) **"Löschen".**</span><span class="sxs-lookup"><span data-stu-id="ead22-261">Select the entry that you want to remove, and then click ![Delete icon](../../media/m365-cc-sc-delete-icon.png) **Delete**.</span></span>

4. <span data-ttu-id="ead22-262">Klicken Sie im angezeigten Warndialogfeld auf **"Löschen".**</span><span class="sxs-lookup"><span data-stu-id="ead22-262">In the warning dialog that appears, click **Delete**.</span></span>

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-the-tenant-allowblock-list"></a><span data-ttu-id="ead22-263">Verwenden Exchange Online PowerShell oder der eigenständigen EOP PowerShell zum Konfigurieren der Mandanten-Zulassungs-/Sperrliste</span><span class="sxs-lookup"><span data-stu-id="ead22-263">Use Exchange Online PowerShell or standalone EOP PowerShell to configure the Tenant Allow/Block List</span></span>

### <a name="use-powershell-to-add-block-file-or-url-entries-to-the-tenant-allowblock-list"></a><span data-ttu-id="ead22-264">Verwenden von PowerShell zum Hinzufügen von Blockierungsdateien oder URL-Einträgen zur Mandanten-Zulassungs-/Sperrliste</span><span class="sxs-lookup"><span data-stu-id="ead22-264">Use PowerShell to add block file or URL entries to the Tenant Allow/Block List</span></span>

<span data-ttu-id="ead22-265">Verwenden Sie die folgende Syntax, um Blockierungsdateien oder URL-Einträge in der Mandanten-Zulassungs-/Sperrliste hinzuzufügen:</span><span class="sxs-lookup"><span data-stu-id="ead22-265">To add block file or URL entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
New-TenantAllowBlockListItems -ListType <FileHash | Url> -Block -Entries "Value1","Value2",..."ValueN" <-ExpirationDate Date | -NoExpiration> [-Notes <String>]
```

<span data-ttu-id="ead22-266">In diesem Beispiel wird ein Blockdateieintrag für die angegebenen Dateien hinzugefügt, die nie ablaufen.</span><span class="sxs-lookup"><span data-stu-id="ead22-266">This example adds a block file entry for the specified files that never expires.</span></span>

```powershell
New-TenantAllowBlockListItems -ListType FileHash -Block -Entries "768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3","2c0a35409ff0873cfa28b70b8224e9aca2362241c1f0ed6f622fef8d4722fd9a" -NoExpiration
```

<span data-ttu-id="ead22-267">In diesem Beispiel wird ein Block-URL-Eintrag für contoso.com und alle Unterdomänen hinzugefügt (z. B. contoso.com, www.contoso.com und xyz.abc.contoso.com).</span><span class="sxs-lookup"><span data-stu-id="ead22-267">This example adds a block URL entry for contoso.com and all subdomains (for example, contoso.com, www.contoso.com, and xyz.abc.contoso.com).</span></span> <span data-ttu-id="ead22-268">Da wir die Parameter ExpirationDate oder NoExpiration nicht verwendet haben, läuft der Eintrag nach 30 Tagen ab.</span><span class="sxs-lookup"><span data-stu-id="ead22-268">Because we didn't use the ExpirationDate or NoExpiration parameters, the entry expires after 30 days.</span></span>

```powershell
New-TenantAllowBlockListItems -ListType Url -Block -Entries ~contoso.com
```

<span data-ttu-id="ead22-269">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [New-TenantAllowBlockListItems](/powershell/module/exchange/new-tenantallowblocklistitems).</span><span class="sxs-lookup"><span data-stu-id="ead22-269">For detailed syntax and parameter information, see [New-TenantAllowBlockListItems](/powershell/module/exchange/new-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-add-allow-or-block-spoofed-sender-entries-to-the-tenant-allowblock-list"></a><span data-ttu-id="ead22-270">Verwenden von PowerShell zum Hinzufügen oder Blockieren von Spoofing-Absendereinträgen zur Mandanten-Zulassungs-/Sperrliste</span><span class="sxs-lookup"><span data-stu-id="ead22-270">Use PowerShell to add allow or block spoofed sender entries to the Tenant Allow/Block List</span></span>

<span data-ttu-id="ead22-271">Verwenden Sie die folgende Syntax, um gefälschte Absendereinträge in der Mandanten-Zulassungs-/Sperrliste hinzuzufügen:</span><span class="sxs-lookup"><span data-stu-id="ead22-271">To add spoofed sender entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
New-TenantAllowBlockListSpoofItems -SpoofedUser <Domain | EmailAddress | *> -SendingInfrastructure <Domain | IPAddress/24> -SpoofType <External | Internal> -Action <Allow | Block>
```

<span data-ttu-id="ead22-272">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [New-TenantAllowBlockListSpoofItems](/powershell/module/exchange/new-tenantallowblocklistspoofitems).</span><span class="sxs-lookup"><span data-stu-id="ead22-272">For detailed syntax and parameter information, see [New-TenantAllowBlockListSpoofItems](/powershell/module/exchange/new-tenantallowblocklistspoofitems).</span></span>

### <a name="use-powershell-to-view-block-file-or-url-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="ead22-273">Verwenden von PowerShell zum Anzeigen von Blockierungsdateien oder URL-Einträgen in der Mandanten-Zulassungs-/Sperrliste</span><span class="sxs-lookup"><span data-stu-id="ead22-273">Use PowerShell to view block file or URL entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="ead22-274">Verwenden Sie die folgende Syntax, um Blockierungsdateien oder URL-Einträge in der Mandanten-Zulassungs-/Sperrliste anzuzeigen:</span><span class="sxs-lookup"><span data-stu-id="ead22-274">To view block file or URL entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType <FileHash | URL> [-Entry <FileHashValue | URLValue>] [<-ExpirationDate Date | -NoExpiration>]
```

<span data-ttu-id="ead22-275">In diesem Beispiel werden Informationen für den angegebenen Dateihashwert zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="ead22-275">This example returns information for the specified file hash value.</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType FileHash -Entry "9f86d081884c7d659a2feaa0c55ad015a3bf4f1b2b0b822cd15d6c15b0f00a08"
```

<span data-ttu-id="ead22-276">In diesem Beispiel werden alle blockierten URLs zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="ead22-276">This example returns all blocked URLs.</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType Url -Block
```

<span data-ttu-id="ead22-277">Ausführliche Informationen zu Syntax und Parametern finden Sie unter ["Get-TenantAllowBlockListItems".](/powershell/module/exchange/get-tenantallowblocklistitems)</span><span class="sxs-lookup"><span data-stu-id="ead22-277">For detailed syntax and parameter information, see [Get-TenantAllowBlockListItems](/powershell/module/exchange/get-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-view-allow-or-block-spoofed-sender-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="ead22-278">Verwenden von PowerShell zum Anzeigen oder Blockieren von Spoofing-Absendereinträgen in der Mandanten-Zulassungs-/Sperrliste</span><span class="sxs-lookup"><span data-stu-id="ead22-278">Use PowerShell to view allow or block spoofed sender entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="ead22-279">Verwenden Sie die folgende Syntax, um gefälschte Absendereinträge in der Mandanten-Zulassungs-/Sperrliste anzuzeigen:</span><span class="sxs-lookup"><span data-stu-id="ead22-279">To view spoofed sender entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Get-TenantAllowBlockListSpoofItems [-Action <Allow | Block>] [-SpoofType <External | Internal>
```

<span data-ttu-id="ead22-280">In diesem Beispiel werden alle gefälschten Absendereinträge in der Mandanten-Zulassungs-/Sperrliste zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="ead22-280">This example returns all spoofed sender entries in the Tenant Allow/Block List.</span></span>

```powershell
Get-TenantAllowBlockListSpoofItems
```

<span data-ttu-id="ead22-281">This example returns all allow spoofed sender entries that are internal.</span><span class="sxs-lookup"><span data-stu-id="ead22-281">This example returns all allow spoofed sender entries that are internal.</span></span>

```powershell
Get-TenantAllowBlockListSpoofItems -Action Allow -SpoofType Internal
```

<span data-ttu-id="ead22-282">In diesem Beispiel werden alle blockierten spoofierten Absendereinträge zurückgegeben, die extern sind.</span><span class="sxs-lookup"><span data-stu-id="ead22-282">This example returns all blocked spoofed sender entries that are external.</span></span>

```powershell
Get-TenantAllowBlockListSpoofItems -Action Block -SpoofType External
```

<span data-ttu-id="ead22-283">Ausführliche Informationen zu Syntax und Parametern finden Sie unter ["Get-TenantAllowBlockListSpoofItems".](/powershell/module/exchange/get-tenantallowblocklistspoofitems)</span><span class="sxs-lookup"><span data-stu-id="ead22-283">For detailed syntax and parameter information, see [Get-TenantAllowBlockListSpoofItems](/powershell/module/exchange/get-tenantallowblocklistspoofitems).</span></span>

### <a name="use-powershell-to-modify-block-file-and-url-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="ead22-284">Verwenden von PowerShell zum Ändern von Blockdatei- und URL-Einträgen in der Mandanten-Zulassungs-/Sperrliste</span><span class="sxs-lookup"><span data-stu-id="ead22-284">Use PowerShell to modify block file and URL entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="ead22-285">Verwenden Sie die folgende Syntax, um Blockdatei- und URL-Einträge in der Mandanten-Zulassungs-/Sperrliste zu ändern:</span><span class="sxs-lookup"><span data-stu-id="ead22-285">To modify block file and URL entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Set-TenantAllowBlockListItems -ListType <FileHash | Url> -Ids <"Id1","Id2",..."IdN"> [<-ExpirationDate Date | -NoExpiration>] [-Notes <String>]
```

<span data-ttu-id="ead22-286">In diesem Beispiel wird das Ablaufdatum des angegebenen Block-URL-Eintrags geändert.</span><span class="sxs-lookup"><span data-stu-id="ead22-286">This example changes the expiration date of the specified block URL entry.</span></span>

```powershell
Set-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSRAAAA" -ExpirationDate "5/30/2020"
```

<span data-ttu-id="ead22-287">Ausführliche Informationen zu Syntax und Parametern finden Sie unter ["Set-TenantAllowBlockListItems".](/powershell/module/exchange/set-tenantallowblocklistitems)</span><span class="sxs-lookup"><span data-stu-id="ead22-287">For detailed syntax and parameter information, see [Set-TenantAllowBlockListItems](/powershell/module/exchange/set-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-modify-allow-or-block-spoofed-sender-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="ead22-288">Verwenden von PowerShell zum Ändern oder Blockieren von Spoofing-Absendereinträgen in der Mandanten-Zulassungs-/Sperrliste</span><span class="sxs-lookup"><span data-stu-id="ead22-288">Use PowerShell to modify allow or block spoofed sender entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="ead22-289">Verwenden Sie die folgende Syntax, um spoofierte Absendereinträge in der Mandanten-Zulassungs-/Sperrliste zu ändern oder zu blockieren:</span><span class="sxs-lookup"><span data-stu-id="ead22-289">To modify allow or block spoofed sender entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Set-TenantAllowBlockListSpoofItems -Ids <"Id1","Id2",..."IdN"> -Action <Allow | Block>
```

<span data-ttu-id="ead22-290">In diesem Beispiel wird der Spoofing-Absendereintrag von "Blockieren zulassen" geändert.</span><span class="sxs-lookup"><span data-stu-id="ead22-290">This example changes spoofed sender entry from allow to block.</span></span>

```powershell
Set-TenantAllowBlockListItems -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSRAAAA" -Action Block
```

<span data-ttu-id="ead22-291">Ausführliche Informationen zu Syntax und Parametern finden Sie unter ["Set-TenantAllowBlockListSpoofItems".](/powershell/module/exchange/set-tenantallowblocklistspoofitems)</span><span class="sxs-lookup"><span data-stu-id="ead22-291">For detailed syntax and parameter information, see [Set-TenantAllowBlockListSpoofItems](/powershell/module/exchange/set-tenantallowblocklistspoofitems).</span></span>

### <a name="use-powershell-to-remove-url-or-file-entries-from-the-tenant-allowblock-list"></a><span data-ttu-id="ead22-292">Verwenden von PowerShell zum Entfernen von URL- oder Dateieinträgen aus der Mandanten-Zulassungs-/Sperrliste</span><span class="sxs-lookup"><span data-stu-id="ead22-292">Use PowerShell to remove URL or file entries from the Tenant Allow/Block List</span></span>

<span data-ttu-id="ead22-293">Verwenden Sie die folgende Syntax, um Datei- und URL-Einträge aus der Mandanten-Zulassungs-/Sperrliste zu entfernen:</span><span class="sxs-lookup"><span data-stu-id="ead22-293">To remove file and URL entries from the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Remove-TenantAllowBlockListItems -ListType <FileHash | Url> -Ids <"Id1","Id2",..."IdN">
```

<span data-ttu-id="ead22-294">In diesem Beispiel wird der angegebene Block-URL-Eintrag aus der Mandanten-Zulassungs-/Sperrliste entfernt.</span><span class="sxs-lookup"><span data-stu-id="ead22-294">This example removes the specified block URL entry from the Tenant Allow/Block List.</span></span>

```powershell
Remove-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSPAAAA0"
```

<span data-ttu-id="ead22-295">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Remove-TenantAllowBlockListItems](/powershell/module/exchange/remove-tenantallowblocklistitems).</span><span class="sxs-lookup"><span data-stu-id="ead22-295">For detailed syntax and parameter information, see [Remove-TenantAllowBlockListItems](/powershell/module/exchange/remove-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-remove-allow-or-block-spoofed-sender-entries-from-the-tenant-allowblock-list"></a><span data-ttu-id="ead22-296">Verwenden von PowerShell zum Entfernen von Spoofing-Absendereinträgen aus der Mandanten-Zulassungs-/Sperrliste</span><span class="sxs-lookup"><span data-stu-id="ead22-296">Use PowerShell to remove allow or block spoofed sender entries from the Tenant Allow/Block List</span></span>

<span data-ttu-id="ead22-297">Verwenden Sie die folgende Syntax, um Spoofing von Absendereinträgen aus der Mandanten-Zulassungs-/Sperrliste zu entfernen oder zu blockieren:</span><span class="sxs-lookup"><span data-stu-id="ead22-297">To remove allow or block spoof sender entries from the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Remove-TenantAllowBlockListSpoofItems -Ids <"Id1","Id2",..."IdN">
```

<span data-ttu-id="ead22-298">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Remove-TenantAllowBlockListSpoofItems](/powershell/module/exchange/remove-tenantallowblocklistspoofitems).</span><span class="sxs-lookup"><span data-stu-id="ead22-298">For detailed syntax and parameter information, see [Remove-TenantAllowBlockListSpoofItems](/powershell/module/exchange/remove-tenantallowblocklistspoofitems).</span></span>

## <a name="url-syntax-for-the-tenant-allowblock-list"></a><span data-ttu-id="ead22-299">URL-Syntax für die Mandanten-Zulassungs-/Sperrliste</span><span class="sxs-lookup"><span data-stu-id="ead22-299">URL syntax for the Tenant Allow/Block List</span></span>

- <span data-ttu-id="ead22-300">IP4v- und IPv6-Adressen sind zulässig, TCP/UDP-Ports jedoch nicht.</span><span class="sxs-lookup"><span data-stu-id="ead22-300">IP4v and IPv6 addresses are allowed, but TCP/UDP ports are not.</span></span>

- <span data-ttu-id="ead22-301">Dateinamenerweiterungen sind nicht zulässig (z. B. test.pdf).</span><span class="sxs-lookup"><span data-stu-id="ead22-301">Filename extensions are not allowed (for example, test.pdf).</span></span>

- <span data-ttu-id="ead22-302">Unicode wird nicht unterstützt, Punycode jedoch.</span><span class="sxs-lookup"><span data-stu-id="ead22-302">Unicode is not supported, but Punycode is.</span></span>

- <span data-ttu-id="ead22-303">Hostnamen sind zulässig, wenn alle folgenden Anweisungen wahr sind:</span><span class="sxs-lookup"><span data-stu-id="ead22-303">Hostnames are allowed if all of the following statements are true:</span></span>
  - <span data-ttu-id="ead22-304">Der Hostname enthält einen Punkt.</span><span class="sxs-lookup"><span data-stu-id="ead22-304">The hostname contains a period.</span></span>
  - <span data-ttu-id="ead22-305">Links vom Punkt befindet sich mindestens ein Zeichen.</span><span class="sxs-lookup"><span data-stu-id="ead22-305">There is at least one character to the left of the period.</span></span>
  - <span data-ttu-id="ead22-306">Rechts neben dem Punkt befinden sich mindestens zwei Zeichen.</span><span class="sxs-lookup"><span data-stu-id="ead22-306">There are at least two characters to the right of the period.</span></span>

  <span data-ttu-id="ead22-307">Ist beispielsweise `t.co` zulässig `.com` oder nicht `contoso.` zulässig.</span><span class="sxs-lookup"><span data-stu-id="ead22-307">For example, `t.co` is allowed; `.com` or `contoso.` are not allowed.</span></span>

- <span data-ttu-id="ead22-308">Unterpfade werden nicht impliziert.</span><span class="sxs-lookup"><span data-stu-id="ead22-308">Subpaths are not implied.</span></span>

  <span data-ttu-id="ead22-309">Enthält z. B. `contoso.com` nicht `contoso.com/a` .</span><span class="sxs-lookup"><span data-stu-id="ead22-309">For example, `contoso.com` does not include `contoso.com/a`.</span></span>

- <span data-ttu-id="ead22-310">Platzhalter (\*) sind in den folgenden Szenarien zulässig:</span><span class="sxs-lookup"><span data-stu-id="ead22-310">Wildcards (\*) are allowed in the following scenarios:</span></span>

  - <span data-ttu-id="ead22-311">Auf einen linken Platzhalter muss ein Punkt folgen, um eine Unterdomäne anzugeben.</span><span class="sxs-lookup"><span data-stu-id="ead22-311">A left wildcard must be followed by a period to specify a subdomain.</span></span>

    <span data-ttu-id="ead22-312">Ist beispielsweise `*.contoso.com` zulässig; `*contoso.com` ist nicht zulässig.</span><span class="sxs-lookup"><span data-stu-id="ead22-312">For example, `*.contoso.com` is allowed; `*contoso.com` is not allowed.</span></span>

  - <span data-ttu-id="ead22-313">Ein rechter Platzhalter muss einem Schrägstrich (/) folgen, um einen Pfad anzugeben.</span><span class="sxs-lookup"><span data-stu-id="ead22-313">A right wildcard must follow a forward slash (/) to specify a path.</span></span>

    <span data-ttu-id="ead22-314">Ist beispielsweise `contoso.com/*` zulässig `contoso.com*` oder nicht `contoso.com/ab*` zulässig.</span><span class="sxs-lookup"><span data-stu-id="ead22-314">For example, `contoso.com/*` is allowed; `contoso.com*` or `contoso.com/ab*` are not allowed.</span></span>

  - <span data-ttu-id="ead22-315">Alle Unterpfade werden nicht durch einen rechten Platzhalter impliziert.</span><span class="sxs-lookup"><span data-stu-id="ead22-315">All subpaths are not implied by a right wildcard.</span></span>

    <span data-ttu-id="ead22-316">Enthält z. B. `contoso.com/*` nicht `contoso.com/a` .</span><span class="sxs-lookup"><span data-stu-id="ead22-316">For example, `contoso.com/*` does not include `contoso.com/a`.</span></span>

  - <span data-ttu-id="ead22-317">`*.com*` ungültig ist (keine auflösbare Domäne, und der rechte Platzhalter folgt keinem Schrägstrich).</span><span class="sxs-lookup"><span data-stu-id="ead22-317">`*.com*` is invalid (not a resolvable domain and the right wildcard does not follow a forward slash).</span></span>

  - <span data-ttu-id="ead22-318">Platzhalter sind in IP-Adressen nicht zulässig.</span><span class="sxs-lookup"><span data-stu-id="ead22-318">Wildcards are not allowed in IP addresses.</span></span>

- <span data-ttu-id="ead22-319">Das Tildezeichen (~) ist in den folgenden Szenarien verfügbar:</span><span class="sxs-lookup"><span data-stu-id="ead22-319">The tilde (~) character is available in the following scenarios:</span></span>

  - <span data-ttu-id="ead22-320">Eine linke Tilde impliziert eine Domäne und alle Unterdomänen.</span><span class="sxs-lookup"><span data-stu-id="ead22-320">A left tilde implies a domain and all subdomains.</span></span>

    <span data-ttu-id="ead22-321">Beispiel: `~contoso.com` "includes" `contoso.com` und `*.contoso.com` ".</span><span class="sxs-lookup"><span data-stu-id="ead22-321">For example `~contoso.com` includes `contoso.com` and `*.contoso.com`.</span></span>

- <span data-ttu-id="ead22-322">URL-Einträge, die Protokolle enthalten (z. B. `http://` , oder ) schlagen `https://` `ftp://` fehl, da URL-Einträge für alle Protokolle gelten.</span><span class="sxs-lookup"><span data-stu-id="ead22-322">URL entries that contain protocols (for example, `http://`, `https://`, or `ftp://`) will fail, because URL entries apply to all protocols.</span></span>

- <span data-ttu-id="ead22-323">Ein Benutzername oder Kennwort wird nicht unterstützt oder ist nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="ead22-323">A username or password aren't supported or required.</span></span>

- <span data-ttu-id="ead22-324">Anführungszeichen (' oder ") sind ungültige Zeichen.</span><span class="sxs-lookup"><span data-stu-id="ead22-324">Quotes (' or ") are invalid characters.</span></span>

- <span data-ttu-id="ead22-325">Eine URL sollte nach Möglichkeit alle Umleitungen enthalten.</span><span class="sxs-lookup"><span data-stu-id="ead22-325">A URL should include all redirects where possible.</span></span>

### <a name="url-entry-scenarios"></a><span data-ttu-id="ead22-326">URL-Eintragsszenarien</span><span class="sxs-lookup"><span data-stu-id="ead22-326">URL entry scenarios</span></span>

<span data-ttu-id="ead22-327">Gültige URL-Einträge und deren Ergebnisse werden in den folgenden Abschnitten beschrieben.</span><span class="sxs-lookup"><span data-stu-id="ead22-327">Valid URL entries and their results are described in the following sections.</span></span>

#### <a name="scenario-no-wildcards"></a><span data-ttu-id="ead22-328">Szenario: Keine Platzhalter</span><span class="sxs-lookup"><span data-stu-id="ead22-328">Scenario: No wildcards</span></span>

<span data-ttu-id="ead22-329">**Eintrag**: `contoso.com`</span><span class="sxs-lookup"><span data-stu-id="ead22-329">**Entry**: `contoso.com`</span></span>

- <span data-ttu-id="ead22-330">**Übereinstimmung zulassen:** contoso.com</span><span class="sxs-lookup"><span data-stu-id="ead22-330">**Allow match**: contoso.com</span></span>

- <span data-ttu-id="ead22-331">**Nicht übereinstimmend zulassen:**</span><span class="sxs-lookup"><span data-stu-id="ead22-331">**Allow not matched**:</span></span>

  - <span data-ttu-id="ead22-332">abc-contoso.com</span><span class="sxs-lookup"><span data-stu-id="ead22-332">abc-contoso.com</span></span>
  - <span data-ttu-id="ead22-333">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="ead22-333">contoso.com/a</span></span>
  - <span data-ttu-id="ead22-334">payroll.contoso.com</span><span class="sxs-lookup"><span data-stu-id="ead22-334">payroll.contoso.com</span></span>
  - <span data-ttu-id="ead22-335">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="ead22-335">test.com/contoso.com</span></span>
  - <span data-ttu-id="ead22-336">test.com/q=contoso.com</span><span class="sxs-lookup"><span data-stu-id="ead22-336">test.com/q=contoso.com</span></span>
  - <span data-ttu-id="ead22-337">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="ead22-337">www.contoso.com</span></span>
  - <span data-ttu-id="ead22-338">www.contoso.com/q=a@contoso.com</span><span class="sxs-lookup"><span data-stu-id="ead22-338">www.contoso.com/q=a@contoso.com</span></span>

- <span data-ttu-id="ead22-339">**Blocküberstimmung:**</span><span class="sxs-lookup"><span data-stu-id="ead22-339">**Block match**:</span></span>

  - <span data-ttu-id="ead22-340">contoso.com</span><span class="sxs-lookup"><span data-stu-id="ead22-340">contoso.com</span></span>
  - <span data-ttu-id="ead22-341">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="ead22-341">contoso.com/a</span></span>
  - <span data-ttu-id="ead22-342">payroll.contoso.com</span><span class="sxs-lookup"><span data-stu-id="ead22-342">payroll.contoso.com</span></span>
  - <span data-ttu-id="ead22-343">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="ead22-343">test.com/contoso.com</span></span>
  - <span data-ttu-id="ead22-344">test.com/q=contoso.com</span><span class="sxs-lookup"><span data-stu-id="ead22-344">test.com/q=contoso.com</span></span>
  - <span data-ttu-id="ead22-345">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="ead22-345">www.contoso.com</span></span>
  - <span data-ttu-id="ead22-346">www.contoso.com/q=a@contoso.com</span><span class="sxs-lookup"><span data-stu-id="ead22-346">www.contoso.com/q=a@contoso.com</span></span>

- <span data-ttu-id="ead22-347">**Block nicht abgeglichen:** abc-contoso.com</span><span class="sxs-lookup"><span data-stu-id="ead22-347">**Block not matched**: abc-contoso.com</span></span>

#### <a name="scenario-left-wildcard-subdomain"></a><span data-ttu-id="ead22-348">Szenario: Linker Platzhalter (Unterdomäne)</span><span class="sxs-lookup"><span data-stu-id="ead22-348">Scenario: Left wildcard (subdomain)</span></span>

<span data-ttu-id="ead22-349">**Eintrag**: `*.contoso.com`</span><span class="sxs-lookup"><span data-stu-id="ead22-349">**Entry**: `*.contoso.com`</span></span>

- <span data-ttu-id="ead22-350">**Übereinstimmung zulassen** und **Übereinstimmung blockieren:**</span><span class="sxs-lookup"><span data-stu-id="ead22-350">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="ead22-351">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="ead22-351">www.contoso.com</span></span>
  - <span data-ttu-id="ead22-352">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="ead22-352">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="ead22-353">**Nicht übereinstimmende** und **nicht übereinstimmende Blockierung** zulassen:</span><span class="sxs-lookup"><span data-stu-id="ead22-353">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="ead22-354">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="ead22-354">123contoso.com</span></span>
  - <span data-ttu-id="ead22-355">contoso.com</span><span class="sxs-lookup"><span data-stu-id="ead22-355">contoso.com</span></span>
  - <span data-ttu-id="ead22-356">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="ead22-356">test.com/contoso.com</span></span>
  - <span data-ttu-id="ead22-357">www.contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="ead22-357">www.contoso.com/abc</span></span>

#### <a name="scenario-right-wildcard-at-top-of-path"></a><span data-ttu-id="ead22-358">Szenario: Rechter Platzhalter oben im Pfad</span><span class="sxs-lookup"><span data-stu-id="ead22-358">Scenario: Right wildcard at top of path</span></span>

<span data-ttu-id="ead22-359">**Eintrag**: `contoso.com/a/*`</span><span class="sxs-lookup"><span data-stu-id="ead22-359">**Entry**: `contoso.com/a/*`</span></span>

- <span data-ttu-id="ead22-360">**Übereinstimmung zulassen** und **Übereinstimmung blockieren:**</span><span class="sxs-lookup"><span data-stu-id="ead22-360">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="ead22-361">contoso.com/a/b</span><span class="sxs-lookup"><span data-stu-id="ead22-361">contoso.com/a/b</span></span>
  - <span data-ttu-id="ead22-362">contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="ead22-362">contoso.com/a/b/c</span></span>
  - <span data-ttu-id="ead22-363">contoso.com/a/?q=joe@t.com</span><span class="sxs-lookup"><span data-stu-id="ead22-363">contoso.com/a/?q=joe@t.com</span></span>

- <span data-ttu-id="ead22-364">**Nicht übereinstimmende** und **nicht übereinstimmende Blockierung** zulassen:</span><span class="sxs-lookup"><span data-stu-id="ead22-364">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="ead22-365">contoso.com</span><span class="sxs-lookup"><span data-stu-id="ead22-365">contoso.com</span></span>
  - <span data-ttu-id="ead22-366">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="ead22-366">contoso.com/a</span></span>
  - <span data-ttu-id="ead22-367">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="ead22-367">www.contoso.com</span></span>
  - <span data-ttu-id="ead22-368">www.contoso.com/q=a@contoso.com</span><span class="sxs-lookup"><span data-stu-id="ead22-368">www.contoso.com/q=a@contoso.com</span></span>

#### <a name="scenario-left-tilde"></a><span data-ttu-id="ead22-369">Szenario: Linke Tilde</span><span class="sxs-lookup"><span data-stu-id="ead22-369">Scenario: Left tilde</span></span>

<span data-ttu-id="ead22-370">**Eintrag**: `~contoso.com`</span><span class="sxs-lookup"><span data-stu-id="ead22-370">**Entry**: `~contoso.com`</span></span>

- <span data-ttu-id="ead22-371">**Übereinstimmung zulassen** und **Übereinstimmung blockieren:**</span><span class="sxs-lookup"><span data-stu-id="ead22-371">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="ead22-372">contoso.com</span><span class="sxs-lookup"><span data-stu-id="ead22-372">contoso.com</span></span>
  - <span data-ttu-id="ead22-373">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="ead22-373">www.contoso.com</span></span>
  - <span data-ttu-id="ead22-374">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="ead22-374">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="ead22-375">**Nicht übereinstimmende** und **nicht übereinstimmende Blockierung** zulassen:</span><span class="sxs-lookup"><span data-stu-id="ead22-375">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="ead22-376">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="ead22-376">123contoso.com</span></span>
  - <span data-ttu-id="ead22-377">contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="ead22-377">contoso.com/abc</span></span>
  - <span data-ttu-id="ead22-378">www.contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="ead22-378">www.contoso.com/abc</span></span>

#### <a name="scenario-right-wildcard-suffix"></a><span data-ttu-id="ead22-379">Szenario: Rechtes Platzhaltersuffix</span><span class="sxs-lookup"><span data-stu-id="ead22-379">Scenario: Right wildcard suffix</span></span>

<span data-ttu-id="ead22-380">**Eintrag**: `contoso.com/*`</span><span class="sxs-lookup"><span data-stu-id="ead22-380">**Entry**: `contoso.com/*`</span></span>

- <span data-ttu-id="ead22-381">**Übereinstimmung zulassen** und **Übereinstimmung blockieren:**</span><span class="sxs-lookup"><span data-stu-id="ead22-381">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="ead22-382">contoso.com/?q=whatever@fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="ead22-382">contoso.com/?q=whatever@fabrikam.com</span></span>
  - <span data-ttu-id="ead22-383">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="ead22-383">contoso.com/a</span></span>
  - <span data-ttu-id="ead22-384">contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="ead22-384">contoso.com/a/b/c</span></span>
  - <span data-ttu-id="ead22-385">contoso.com/ab</span><span class="sxs-lookup"><span data-stu-id="ead22-385">contoso.com/ab</span></span>
  - <span data-ttu-id="ead22-386">contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="ead22-386">contoso.com/b</span></span>
  - <span data-ttu-id="ead22-387">contoso.com/b/a/c</span><span class="sxs-lookup"><span data-stu-id="ead22-387">contoso.com/b/a/c</span></span>
  - <span data-ttu-id="ead22-388">contoso.com/ba</span><span class="sxs-lookup"><span data-stu-id="ead22-388">contoso.com/ba</span></span>

- <span data-ttu-id="ead22-389">**Nicht übereinstimmende** und **nicht übereinstimmende Blockierung** zulassen: contoso.com</span><span class="sxs-lookup"><span data-stu-id="ead22-389">**Allow not matched** and **Block not matched**: contoso.com</span></span>

#### <a name="scenario-left-wildcard-subdomain-and-right-wildcard-suffix"></a><span data-ttu-id="ead22-390">Szenario: Linke Platzhalterunterdomäne und rechtes Platzhaltersuffix</span><span class="sxs-lookup"><span data-stu-id="ead22-390">Scenario: Left wildcard subdomain and right wildcard suffix</span></span>

<span data-ttu-id="ead22-391">**Eintrag**: `*.contoso.com/*`</span><span class="sxs-lookup"><span data-stu-id="ead22-391">**Entry**: `*.contoso.com/*`</span></span>

- <span data-ttu-id="ead22-392">**Übereinstimmung zulassen** und **Übereinstimmung blockieren:**</span><span class="sxs-lookup"><span data-stu-id="ead22-392">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="ead22-393">abc.contoso.com/ab</span><span class="sxs-lookup"><span data-stu-id="ead22-393">abc.contoso.com/ab</span></span>
  - <span data-ttu-id="ead22-394">abc.xyz.contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="ead22-394">abc.xyz.contoso.com/a/b/c</span></span>
  - <span data-ttu-id="ead22-395">www.contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="ead22-395">www.contoso.com/a</span></span>
  - <span data-ttu-id="ead22-396">www.contoso.com/b/a/c</span><span class="sxs-lookup"><span data-stu-id="ead22-396">www.contoso.com/b/a/c</span></span>
  - <span data-ttu-id="ead22-397">xyz.contoso.com/ba</span><span class="sxs-lookup"><span data-stu-id="ead22-397">xyz.contoso.com/ba</span></span>

- <span data-ttu-id="ead22-398">**Nicht übereinstimmende** und **nicht übereinstimmende Blockierung** zulassen: contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="ead22-398">**Allow not matched** and **Block not matched**: contoso.com/b</span></span>

#### <a name="scenario-left-and-right-tilde"></a><span data-ttu-id="ead22-399">Szenario: Linke und rechte Tilde</span><span class="sxs-lookup"><span data-stu-id="ead22-399">Scenario: Left and right tilde</span></span>

<span data-ttu-id="ead22-400">**Eintrag**: `~contoso.com~`</span><span class="sxs-lookup"><span data-stu-id="ead22-400">**Entry**: `~contoso.com~`</span></span>

- <span data-ttu-id="ead22-401">**Übereinstimmung zulassen** und **Übereinstimmung blockieren:**</span><span class="sxs-lookup"><span data-stu-id="ead22-401">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="ead22-402">contoso.com</span><span class="sxs-lookup"><span data-stu-id="ead22-402">contoso.com</span></span>
  - <span data-ttu-id="ead22-403">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="ead22-403">contoso.com/a</span></span>
  - <span data-ttu-id="ead22-404">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="ead22-404">www.contoso.com</span></span>
  - <span data-ttu-id="ead22-405">www.contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="ead22-405">www.contoso.com/b</span></span>
  - <span data-ttu-id="ead22-406">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="ead22-406">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="ead22-407">**Nicht übereinstimmende** und **nicht übereinstimmende Blockierung** zulassen:</span><span class="sxs-lookup"><span data-stu-id="ead22-407">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="ead22-408">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="ead22-408">123contoso.com</span></span>
  - <span data-ttu-id="ead22-409">contoso.org</span><span class="sxs-lookup"><span data-stu-id="ead22-409">contoso.org</span></span>

#### <a name="scenario-ip-address"></a><span data-ttu-id="ead22-410">Szenario: IP-Adresse</span><span class="sxs-lookup"><span data-stu-id="ead22-410">Scenario: IP address</span></span>

<span data-ttu-id="ead22-411">**Eintrag**: `1.2.3.4`</span><span class="sxs-lookup"><span data-stu-id="ead22-411">**Entry**: `1.2.3.4`</span></span>

- <span data-ttu-id="ead22-412">**Übereinstimmung zulassen** und **Übereinstimmung blockieren:** 1.2.3.4</span><span class="sxs-lookup"><span data-stu-id="ead22-412">**Allow match** and **Block match**: 1.2.3.4</span></span>

- <span data-ttu-id="ead22-413">**Nicht übereinstimmende** und **nicht übereinstimmende Blockierung** zulassen:</span><span class="sxs-lookup"><span data-stu-id="ead22-413">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="ead22-414">1.2.3.4/a</span><span class="sxs-lookup"><span data-stu-id="ead22-414">1.2.3.4/a</span></span>
  - <span data-ttu-id="ead22-415">11.2.3.4/a</span><span class="sxs-lookup"><span data-stu-id="ead22-415">11.2.3.4/a</span></span>

#### <a name="ip-address-with-right-wildcard"></a><span data-ttu-id="ead22-416">IP-Adresse mit rechtem Platzhalter</span><span class="sxs-lookup"><span data-stu-id="ead22-416">IP address with right wildcard</span></span>

<span data-ttu-id="ead22-417">**Eintrag**: `1.2.3.4/*`</span><span class="sxs-lookup"><span data-stu-id="ead22-417">**Entry**: `1.2.3.4/*`</span></span>

- <span data-ttu-id="ead22-418">**Übereinstimmung zulassen** und **Übereinstimmung blockieren:**</span><span class="sxs-lookup"><span data-stu-id="ead22-418">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="ead22-419">1.2.3.4/b</span><span class="sxs-lookup"><span data-stu-id="ead22-419">1.2.3.4/b</span></span>
  - <span data-ttu-id="ead22-420">1.2.3.4/baaaa</span><span class="sxs-lookup"><span data-stu-id="ead22-420">1.2.3.4/baaaa</span></span>

### <a name="examples-of-invalid-entries"></a><span data-ttu-id="ead22-421">Beispiele für ungültige Einträge</span><span class="sxs-lookup"><span data-stu-id="ead22-421">Examples of invalid entries</span></span>

<span data-ttu-id="ead22-422">Die folgenden Einträge sind ungültig:</span><span class="sxs-lookup"><span data-stu-id="ead22-422">The following entries are invalid:</span></span>

- <span data-ttu-id="ead22-423">**Fehlende oder ungültige Domänenwerte:**</span><span class="sxs-lookup"><span data-stu-id="ead22-423">**Missing or invalid domain values**:</span></span>

  - <span data-ttu-id="ead22-424">Contoso</span><span class="sxs-lookup"><span data-stu-id="ead22-424">contoso</span></span>
  - <span data-ttu-id="ead22-425">\*.contoso.\*</span><span class="sxs-lookup"><span data-stu-id="ead22-425">\*.contoso.\*</span></span>
  - <span data-ttu-id="ead22-426">\*.com</span><span class="sxs-lookup"><span data-stu-id="ead22-426">\*.com</span></span>
  - <span data-ttu-id="ead22-427">\*.pdf</span><span class="sxs-lookup"><span data-stu-id="ead22-427">\*.pdf</span></span>

- <span data-ttu-id="ead22-428">**Platzhalter für Text oder ohne Leerzeichen:**</span><span class="sxs-lookup"><span data-stu-id="ead22-428">**Wildcard on text or without spacing characters**:</span></span>

  - <span data-ttu-id="ead22-429">\*contoso.com</span><span class="sxs-lookup"><span data-stu-id="ead22-429">\*contoso.com</span></span>
  - <span data-ttu-id="ead22-430">contoso.com\*</span><span class="sxs-lookup"><span data-stu-id="ead22-430">contoso.com\*</span></span>
  - <span data-ttu-id="ead22-431">\*1.2.3.4</span><span class="sxs-lookup"><span data-stu-id="ead22-431">\*1.2.3.4</span></span>
  - <span data-ttu-id="ead22-432">1.2.3.4\*</span><span class="sxs-lookup"><span data-stu-id="ead22-432">1.2.3.4\*</span></span>
  - <span data-ttu-id="ead22-433">contoso.com/a\*</span><span class="sxs-lookup"><span data-stu-id="ead22-433">contoso.com/a\*</span></span>
  - <span data-ttu-id="ead22-434">contoso.com/ab\*</span><span class="sxs-lookup"><span data-stu-id="ead22-434">contoso.com/ab\*</span></span>

- <span data-ttu-id="ead22-435">**IP-Adressen mit Ports:**</span><span class="sxs-lookup"><span data-stu-id="ead22-435">**IP addresses with ports**:</span></span>

  - <span data-ttu-id="ead22-436">contoso.com:443</span><span class="sxs-lookup"><span data-stu-id="ead22-436">contoso.com:443</span></span>
  - <span data-ttu-id="ead22-437">abc.contoso.com:25</span><span class="sxs-lookup"><span data-stu-id="ead22-437">abc.contoso.com:25</span></span>

- <span data-ttu-id="ead22-438">**Nicht beschreibende Platzhalter:**</span><span class="sxs-lookup"><span data-stu-id="ead22-438">**Non-descriptive wildcards**:</span></span>

  - \*
  - <span data-ttu-id="ead22-439">\*.\*</span><span class="sxs-lookup"><span data-stu-id="ead22-439">\*.\*</span></span>

- <span data-ttu-id="ead22-440">**Mittlere Platzhalter:**</span><span class="sxs-lookup"><span data-stu-id="ead22-440">**Middle wildcards**:</span></span>

  - <span data-ttu-id="ead22-441">conto \* so.com</span><span class="sxs-lookup"><span data-stu-id="ead22-441">conto\*so.com</span></span>
  - <span data-ttu-id="ead22-442">conto~so.com</span><span class="sxs-lookup"><span data-stu-id="ead22-442">conto~so.com</span></span>

- <span data-ttu-id="ead22-443">**Doppelte Platzhalter**</span><span class="sxs-lookup"><span data-stu-id="ead22-443">**Double wildcards**</span></span>

  - <span data-ttu-id="ead22-444">contoso.com/\*\*</span><span class="sxs-lookup"><span data-stu-id="ead22-444">contoso.com/\*\*</span></span>
  - <span data-ttu-id="ead22-445">contoso.com/\*/\*</span><span class="sxs-lookup"><span data-stu-id="ead22-445">contoso.com/\*/\*</span></span>

## <a name="domain-pair-syntax-for-spoofed-sender-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="ead22-446">Domänenpaarsyntax für gefälschte Absendereinträge in der Mandanten-Zulassungs-/Sperrliste</span><span class="sxs-lookup"><span data-stu-id="ead22-446">Domain pair syntax for spoofed sender entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="ead22-447">Ein Domänenpaar für einen gefälschten Absender in der Mandanten-Zulassungs-/Sperrliste verwendet die folgende Syntax: `<Spoofed user>, <Sending infrastructure>` .</span><span class="sxs-lookup"><span data-stu-id="ead22-447">A domain pair for a spoofed sender in the Tenant Allow/Block List uses the following syntax: `<Spoofed user>, <Sending infrastructure>`.</span></span>

- <span data-ttu-id="ead22-448">**Gefälschter Benutzer:** Dieser Wert bezieht sich auf die E-Mail-Adresse des gefälschten Benutzers, der im **Feld "Von"** in E-Mail-Clients angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="ead22-448">**Spoofed user**: This value involves the email address of the spoofed user that's displayed in the **From** box in email clients.</span></span> <span data-ttu-id="ead22-449">Diese Adresse wird auch als `5322.From` Adresse bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="ead22-449">This address is also known as the `5322.From` address.</span></span> <span data-ttu-id="ead22-450">Gültige Werte sind:</span><span class="sxs-lookup"><span data-stu-id="ead22-450">Valid values include:</span></span>
  - <span data-ttu-id="ead22-451">Eine einzelne E-Mail-Adresse (z. B. chris@contoso.com).</span><span class="sxs-lookup"><span data-stu-id="ead22-451">An individual email address (for example, chris@contoso.com).</span></span>
  - <span data-ttu-id="ead22-452">Eine E-Mail-Domäne (z. B. contoso.com).</span><span class="sxs-lookup"><span data-stu-id="ead22-452">An email domain (for example, contoso.com).</span></span>
  - <span data-ttu-id="ead22-453">Das Platzhalterzeichen (z. B. \* ).</span><span class="sxs-lookup"><span data-stu-id="ead22-453">The wildcard character (for example, \*).</span></span>

- <span data-ttu-id="ead22-454">Senden der **Infrastruktur:** Dieser Wert gibt die Quelle von Nachrichten des gefälschten Benutzers an.</span><span class="sxs-lookup"><span data-stu-id="ead22-454">**Sending infrastructure**: This value indicates the source of messages from the spoofed user.</span></span> <span data-ttu-id="ead22-455">Gültige Werte sind:</span><span class="sxs-lookup"><span data-stu-id="ead22-455">Valid values include:</span></span>
  - <span data-ttu-id="ead22-456">Die Domäne in einer Reverse-DNS-Suche (PTR-Eintrag) der IP-Adresse des Quell-E-Mail-Servers (z. B. fabrikam.com).</span><span class="sxs-lookup"><span data-stu-id="ead22-456">The domain found in a reverse DNS lookup (PTR record) of the source email server's IP address (for example, fabrikam.com).</span></span>
  - <span data-ttu-id="ead22-457">Wenn die Quell-IP-Adresse keinen PTR-Eintrag aufweist, wird die sendende Infrastruktur als \<source IP\> /24 identifiziert (z. B. 192.168.100.100/24).</span><span class="sxs-lookup"><span data-stu-id="ead22-457">If the source IP address has no PTR record, then the sending infrastructure is identified as \<source IP\>/24 (for example, 192.168.100.100/24).</span></span>

<span data-ttu-id="ead22-458">Hier sind einige Beispiele für gültige Domänenpaare zum Identifizieren von gefälschten Absendern:</span><span class="sxs-lookup"><span data-stu-id="ead22-458">Here are some examples of valid domain pairs to identify spoofed senders:</span></span>

- `contoso.com, 192.168.100.100/24`
- `chris@contoso.com, fabrikam.com`
- `*, contoso.net`

<span data-ttu-id="ead22-459">Die maximale Anzahl von gefälschten Absendereinträgen beträgt 1000.</span><span class="sxs-lookup"><span data-stu-id="ead22-459">The maximum number of spoofed sender entries is 1000.</span></span>

<span data-ttu-id="ead22-460">Das Hinzufügen eines Domänenpaars erlaubt oder blockiert nur die *Kombination aus* dem gefälschten Benutzer *und* der sendenden Infrastruktur.</span><span class="sxs-lookup"><span data-stu-id="ead22-460">Adding a domain pair only allows or blocks the *combination* of the spoofed user *and* the sending infrastructure.</span></span> <span data-ttu-id="ead22-461">Es erlaubt weder E-Mails vom gefälschten Benutzer aus einer Quelle noch E-Mails aus der sendenden Infrastrukturquelle für spoofierte Benutzer.</span><span class="sxs-lookup"><span data-stu-id="ead22-461">It does not allow email from the spoofed user from any source, nor does it allow email from the sending infrastructure source for any spoofed user.</span></span> 

<span data-ttu-id="ead22-462">Beispielsweise fügen Sie einen Zulassungseintrag für das folgende Domänenpaar hinzu:</span><span class="sxs-lookup"><span data-stu-id="ead22-462">For example, you add an allow entry for the following domain pair:</span></span>

- <span data-ttu-id="ead22-463">**Domäne:** gmail.com</span><span class="sxs-lookup"><span data-stu-id="ead22-463">**Domain**: gmail.com</span></span>
- <span data-ttu-id="ead22-464">**Infrastruktur:** tms.mx.com</span><span class="sxs-lookup"><span data-stu-id="ead22-464">**Infrastructure**: tms.mx.com</span></span>

<span data-ttu-id="ead22-465">Nur Nachrichten aus dieser Domäne *und* dem sendenden Infrastrukturpaar dürfen Spoofing ausführen.</span><span class="sxs-lookup"><span data-stu-id="ead22-465">Only messages from that domain *and* sending infrastructure pair are allowed to spoof.</span></span> <span data-ttu-id="ead22-466">Andere Absender, die versuchen, gmail.com zu spoofen, sind nicht zulässig.</span><span class="sxs-lookup"><span data-stu-id="ead22-466">Other senders attempting to spoof gmail.com aren't allowed.</span></span> <span data-ttu-id="ead22-467">Nachrichten von Absendern in anderen Domänen, die von tms.mx.com stammen, werden durch Spoofintelligenz überprüft.</span><span class="sxs-lookup"><span data-stu-id="ead22-467">Messages from senders in other domains originating from tms.mx.com are checked by spoof intelligence.</span></span>
