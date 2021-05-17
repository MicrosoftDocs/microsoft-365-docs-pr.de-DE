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
ms.openlocfilehash: 103ddc9aa0858f9203582ac07a655fd7f5506cf3
ms.sourcegitcommit: 987f70e44e406ab6b1dd35f336a9d0c228032794
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/05/2021
ms.locfileid: "51587587"
---
# <a name="manage-the-tenant-allowblock-list"></a><span data-ttu-id="c62b5-103">Verwalten der Zulassungs-/Sperrliste des Mandanten</span><span class="sxs-lookup"><span data-stu-id="c62b5-103">Manage the Tenant Allow/Block List</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="c62b5-104">**Gilt für**</span><span class="sxs-lookup"><span data-stu-id="c62b5-104">**Applies to**</span></span>
- [<span data-ttu-id="c62b5-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="c62b5-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="c62b5-106">Microsoft Defender für Office 365 Plan 1 und Plan 2</span><span class="sxs-lookup"><span data-stu-id="c62b5-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="c62b5-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c62b5-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

> [!NOTE]
> <span data-ttu-id="c62b5-108">Sie können zu **diesem Zeitpunkt** keine zulässigen Elemente in der Mandanten zulassen/blockieren-Liste konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="c62b5-108">You can't **configure** allowed items in the Tenant Allow/Block List at this time.</span></span>

<span data-ttu-id="c62b5-109">In Microsoft 365 Organisationen mit Postfächern in Exchange Online oder eigenständigen Exchange Online Protection (EOP)-Organisationen ohne Exchange Online Postfächer können Sie mit dem EOP-Filter-Urteil nicht einverstanden sein.</span><span class="sxs-lookup"><span data-stu-id="c62b5-109">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, you might disagree with the EOP filtering verdict.</span></span> <span data-ttu-id="c62b5-110">Beispielsweise kann eine gute Nachricht als ungültig (falsch positiv) gekennzeichnet werden, oder eine schlechte Nachricht kann als ungültig (falsch negativ) zugelassen werden.</span><span class="sxs-lookup"><span data-stu-id="c62b5-110">For example, a good message might be marked as bad (a false positive), or a bad message might be allowed through (a false negative).</span></span>

<span data-ttu-id="c62b5-111">Mit der Mandanten-Allow/Block-Liste im Security & Compliance Center können Sie die Filterungs-Microsoft 365 manuell außer Kraft setzen.</span><span class="sxs-lookup"><span data-stu-id="c62b5-111">The Tenant Allow/Block List in the Security & Compliance Center gives you a way to manually override the Microsoft 365 filtering verdicts.</span></span> <span data-ttu-id="c62b5-112">Die Mandanten zulassen/blockieren Liste wird während des Nachrichtenflusses und zum Zeitpunkt der Benutzerklicks verwendet.</span><span class="sxs-lookup"><span data-stu-id="c62b5-112">The Tenant Allow/Block List is used during mail flow and at the time of user clicks.</span></span> <span data-ttu-id="c62b5-113">Sie können URLs oder Dateien angeben, die immer blockiert werden.</span><span class="sxs-lookup"><span data-stu-id="c62b5-113">You can specify URLs or files to always block.</span></span>

<span data-ttu-id="c62b5-114">In diesem Artikel wird beschrieben, wie Sie Einträge in der Mandanten zulassen/blockieren-Liste im Security & Compliance Center oder in PowerShell (Exchange Online PowerShell für Microsoft 365-Organisationen mit Postfächern in Exchange Online; eigenständige EOP PowerShell für Organisationen ohne Exchange Online-Postfächer) konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="c62b5-114">This article describes how to configure entries in the Tenant Allow/Block List in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="c62b5-115">Was sollten Sie wissen, bevor Sie beginnen?</span><span class="sxs-lookup"><span data-stu-id="c62b5-115">What do you need to know before you begin?</span></span>

- <span data-ttu-id="c62b5-116">Sie öffnen das Security & Compliance Center unter <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="c62b5-116">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="c62b5-117">Um direkt zur Seite **Mandanten zulassen/blockieren zu** wechseln, verwenden Sie <https://protection.office.com/tenantAllowBlockList> .</span><span class="sxs-lookup"><span data-stu-id="c62b5-117">To go directly to the **Tenant Allow/Block List** page, use <https://protection.office.com/tenantAllowBlockList>.</span></span>

- <span data-ttu-id="c62b5-118">Sie geben Dateien mithilfe des SHA256-Hashwerts der Datei an.</span><span class="sxs-lookup"><span data-stu-id="c62b5-118">You specify files by using the SHA256 hash value of the file.</span></span> <span data-ttu-id="c62b5-119">Führen Sie den folgenden Befehl in einer Eingabeaufforderung aus, um den SHA256-Hashwert einer Datei in Windows zu finden:</span><span class="sxs-lookup"><span data-stu-id="c62b5-119">To find the SHA256 hash value of a file in Windows, run the following command in a Command Prompt:</span></span>

  ```console
  certutil.exe -hashfile "<Path>\<Filename>" SHA256
  ```

  <span data-ttu-id="c62b5-120">Ein Beispielwert ist `768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3a` .</span><span class="sxs-lookup"><span data-stu-id="c62b5-120">An example value is `768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3a`.</span></span> <span data-ttu-id="c62b5-121">#A0 (Perceptual Hash) werden nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="c62b5-121">Perceptual hash (pHash) values are not supported.</span></span>

- <span data-ttu-id="c62b5-122">Die verfügbaren #A0 werden weiter unten in diesem Artikel in der #A1 für den Abschnitt [Mandanten zulassen/blockieren](#url-syntax-for-the-tenant-allowblock-list) beschrieben.</span><span class="sxs-lookup"><span data-stu-id="c62b5-122">The available URL values are described in the [URL syntax for the Tenant Allow/Block List](#url-syntax-for-the-tenant-allowblock-list) section later in this article.</span></span>

- <span data-ttu-id="c62b5-123">Die Mandantenzu-/-sperrliste ermöglicht maximal 500 Einträge für URLs und 500 Einträge für Dateihashes.</span><span class="sxs-lookup"><span data-stu-id="c62b5-123">The Tenant Allow/Block List allows a maximum of 500 entries for URLs, and 500 entries for file hashes.</span></span>

- <span data-ttu-id="c62b5-124">Die maximale Anzahl von Zeichen für jeden Eintrag ist:</span><span class="sxs-lookup"><span data-stu-id="c62b5-124">The maximum number of characters for each entry is:</span></span>
  - <span data-ttu-id="c62b5-125">Dateihashes = 64</span><span class="sxs-lookup"><span data-stu-id="c62b5-125">File hashes = 64</span></span>
  - <span data-ttu-id="c62b5-126">URL = 250</span><span class="sxs-lookup"><span data-stu-id="c62b5-126">URL = 250</span></span>

- <span data-ttu-id="c62b5-127">Ein Eintrag sollte innerhalb von 30 Minuten aktiv sein.</span><span class="sxs-lookup"><span data-stu-id="c62b5-127">An entry should be active within 30 minutes.</span></span>

- <span data-ttu-id="c62b5-128">Standardmäßig laufen Einträge in der Mandanten-Zulassen-/Sperrliste nach 30 Tagen ab.</span><span class="sxs-lookup"><span data-stu-id="c62b5-128">By default, entries in the Tenant Allow/Block List will expire after 30 days.</span></span> <span data-ttu-id="c62b5-129">Sie können ein Datum angeben oder festlegen, dass es nie abläuft.</span><span class="sxs-lookup"><span data-stu-id="c62b5-129">You can specify a date or set them to never expire.</span></span>

- <span data-ttu-id="c62b5-130">Wie Sie eine Verbindung mit Exchange Online PowerShell herstellen, finden Sie unter [Herstellen einer Verbindung mit Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="c62b5-130">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="c62b5-131">Informationen zum Herstellen einer Verbindung mit dem eigenständigen Exchange Online Protection PowerShell finden Sie unter [Verbinden mit PowerShell in Exchange Online Protection](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="c62b5-131">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="c62b5-132">Sie müssen in **Exchange Online** Berechtigungen erhalten, bevor Sie die in diesem Artikel beschriebenen Schritte ausführen können:</span><span class="sxs-lookup"><span data-stu-id="c62b5-132">You need to be assigned permissions in **Exchange Online** before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="c62b5-133">Zum Hinzufügen und Entfernen von Werten aus der Mandantenberechtigungs-/Sperrliste müssen Sie Mitglied der Rollengruppen Organisationsverwaltung oder **Sicherheitsadministrator** sein. </span><span class="sxs-lookup"><span data-stu-id="c62b5-133">To add and remove values from the Tenant Allow/Block List, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="c62b5-134">Für den schreibgeschützten Zugriff auf die Mandantenzugriffs-/Sperrliste müssen Sie Mitglied der Rollengruppen **"Globaler Leser"** oder **"Sicherheitsleser"** sein.</span><span class="sxs-lookup"><span data-stu-id="c62b5-134">For read-only access to the Tenant Allow/Block List, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="c62b5-135">Weitere Informationen finden Sie unter [Berechtigungen in Exchange Online](/exchange/permissions-exo/permissions-exo).</span><span class="sxs-lookup"><span data-stu-id="c62b5-135">For more information, see [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo).</span></span>

  > [!NOTE]
  > 
  > - <span data-ttu-id="c62b5-136">Durch das Hinzufügen von Benutzern zur entsprechenden Azure Active Directory-Rolle im Microsoft 365 Admin Center erhalten Benutzer die erforderlichen Berechtigungen _und_ Berechtigungen für andere Features in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="c62b5-136">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="c62b5-137">Weitere Informationen finden Sie unter [Informationen zu Administratorrollen](../../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="c62b5-137">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  > - <span data-ttu-id="c62b5-138">Die Rollengruppe **Organisationsverwaltung mit Leserechten** in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) ermöglicht auch einen schreibgeschützten Zugriff auf das Feature.</span><span class="sxs-lookup"><span data-stu-id="c62b5-138">The **View-Only Organization Management** role group in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

## <a name="use-the-security--compliance-center-to-create-url-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="c62b5-139">Verwenden des Security & Compliance Center zum Erstellen von URL-Einträgen in der Mandantenzu-/-sperrliste</span><span class="sxs-lookup"><span data-stu-id="c62b5-139">Use the Security & Compliance Center to create URL entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="c62b5-140">Weitere Informationen zur Syntax für #A0 finden Sie in der URL-Syntax für den Abschnitt [Mandantenzu-/Sperrliste](#url-syntax-for-the-tenant-allowblock-list) weiter unten in diesem Artikel.</span><span class="sxs-lookup"><span data-stu-id="c62b5-140">For details about the syntax for URL entries, see the [URL syntax for the Tenant Allow/Block List](#url-syntax-for-the-tenant-allowblock-list) section later in this article.</span></span>

1. <span data-ttu-id="c62b5-141">Wechseln Sie im Security & Compliance Center zu Richtlinien für die **Bedrohungsverwaltung** \>  \> **Mandanten zulassen/blockieren Listen**.</span><span class="sxs-lookup"><span data-stu-id="c62b5-141">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="c62b5-142">Überprüfen Sie auf der Seite Mandanten **zulassen/blockieren,** ob die Registerkarte **URLs** ausgewählt ist, und klicken Sie dann auf **Blockieren.**</span><span class="sxs-lookup"><span data-stu-id="c62b5-142">On the **Tenant Allow/Block List** page, verify that the **URLs** tab is selected, and then click **Block**</span></span>

3. <span data-ttu-id="c62b5-143">Konfigurieren Sie **im angezeigten** Flyout UrLs blockieren die folgenden Einstellungen:</span><span class="sxs-lookup"><span data-stu-id="c62b5-143">In the **Block URLs** flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="c62b5-144">**Zu blockierende URLs hinzufügen:** Geben Sie eine URL pro Zeile ein, bis zu maximal 20.</span><span class="sxs-lookup"><span data-stu-id="c62b5-144">**Add URLs to block**: Enter one URL per line, up to a maximum of 20.</span></span>

   - <span data-ttu-id="c62b5-145">**Nie ablaufen:** Gehen Sie wie folgt vor:</span><span class="sxs-lookup"><span data-stu-id="c62b5-145">**Never expire**: Do one of the following steps:</span></span>

     - <span data-ttu-id="c62b5-146">Überprüfen Sie, ob die Einstellung deaktiviert ist ( Umschalten ) und verwenden Sie das Feld Läuft auf, um das ![ ](../../media/scc-toggle-off.png) Ablaufdatum für die Einträge anzugeben. </span><span class="sxs-lookup"><span data-stu-id="c62b5-146">Verify the setting is turned off (![Toggle off](../../media/scc-toggle-off.png)) and use the **Expires on** box to specify the expiration date for the entries.</span></span>

       <span data-ttu-id="c62b5-147">oder</span><span class="sxs-lookup"><span data-stu-id="c62b5-147">or</span></span>

     - <span data-ttu-id="c62b5-148">Verschieben Sie den Umschalter nach rechts, um die Einträge so zu konfigurieren, dass sie nie ablaufen:</span><span class="sxs-lookup"><span data-stu-id="c62b5-148">Move the toggle to the right to configure the entries to never expire:</span></span> ![Umschaltfläche ein](../../media/scc-toggle-on.png)<span data-ttu-id="c62b5-150">.</span><span class="sxs-lookup"><span data-stu-id="c62b5-150">.</span></span>

   - <span data-ttu-id="c62b5-151">**Optionaler Hinweis:** Geben Sie beschreibenden Text für die Einträge ein.</span><span class="sxs-lookup"><span data-stu-id="c62b5-151">**Optional note**: Enter descriptive text for the entries.</span></span>

4. <span data-ttu-id="c62b5-152">Klicken Sie nach Abschluss des Vorgangs auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="c62b5-152">When you're finished, click **Add**.</span></span>

## <a name="use-the-security--compliance-center-to-create-file-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="c62b5-153">Verwenden des Security & Compliance Center zum Erstellen von Dateieinträgen in der Mandantenzu-/-sperrliste</span><span class="sxs-lookup"><span data-stu-id="c62b5-153">Use the Security & Compliance Center to create file entries in the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="c62b5-154">Wechseln Sie im Security & Compliance Center zu Richtlinien für die **Bedrohungsverwaltung** \>  \> **Mandanten zulassen/blockieren Listen**.</span><span class="sxs-lookup"><span data-stu-id="c62b5-154">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="c62b5-155">Wählen Sie auf der Seite Mandanten **zulassen/blockieren** die Registerkarte **Dateien** aus, und klicken Sie dann auf **Blockieren**.</span><span class="sxs-lookup"><span data-stu-id="c62b5-155">On the **Tenant Allow/Block List** page, select **Files** tab, and then click **Block**.</span></span>

3. <span data-ttu-id="c62b5-156">Konfigurieren Sie **im angezeigten Flyout** Dateien zum Blockieren von Dateien hinzufügen die folgenden Einstellungen:</span><span class="sxs-lookup"><span data-stu-id="c62b5-156">In the **Add files to block** flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="c62b5-157">**Hinzufügen von Dateihashes:** Geben Sie einen SHA256-Hashwert pro Zeile ein, bis zu maximal 20.</span><span class="sxs-lookup"><span data-stu-id="c62b5-157">**Add file hashes**: Enter one SHA256 hash value per line, up to a maximum of 20.</span></span>

   - <span data-ttu-id="c62b5-158">**Nie ablaufen:** Gehen Sie wie folgt vor:</span><span class="sxs-lookup"><span data-stu-id="c62b5-158">**Never expire**: Do one of the following steps:</span></span>

     - <span data-ttu-id="c62b5-159">Überprüfen Sie, ob die Einstellung deaktiviert ist ( Umschalten ) und verwenden Sie das Feld Läuft auf, um das ![ ](../../media/scc-toggle-off.png) Ablaufdatum für die Einträge anzugeben. </span><span class="sxs-lookup"><span data-stu-id="c62b5-159">Verify the setting is turned off (![Toggle off](../../media/scc-toggle-off.png)) and use the **Expires on** box to specify the expiration date for the entries.</span></span>

     <span data-ttu-id="c62b5-160">oder</span><span class="sxs-lookup"><span data-stu-id="c62b5-160">or</span></span>

     - <span data-ttu-id="c62b5-161">Verschieben Sie den Umschalter nach rechts, um die Einträge so zu konfigurieren, dass sie nie ablaufen:</span><span class="sxs-lookup"><span data-stu-id="c62b5-161">Move the toggle to the right to configure the entries to never expire:</span></span> ![Umschaltfläche ein](../../media/scc-toggle-on.png)<span data-ttu-id="c62b5-163">.</span><span class="sxs-lookup"><span data-stu-id="c62b5-163">.</span></span>

   - <span data-ttu-id="c62b5-164">**Optionaler Hinweis:** Geben Sie beschreibenden Text für die Einträge ein.</span><span class="sxs-lookup"><span data-stu-id="c62b5-164">**Optional note**: Enter descriptive text for the entries.</span></span>

4. <span data-ttu-id="c62b5-165">Klicken Sie nach Abschluss des Vorgangs auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="c62b5-165">When you're finished, click **Add**.</span></span>

## <a name="use-the-security--compliance-center-to-view-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="c62b5-166">Verwenden des Security & Compliance Center zum Anzeigen von Einträgen in der Mandantenzu-/-sperrliste</span><span class="sxs-lookup"><span data-stu-id="c62b5-166">Use the Security & Compliance Center to view entries in the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="c62b5-167">Wechseln Sie im Security & Compliance Center zu Richtlinien für die **Bedrohungsverwaltung** \>  \> **Mandanten zulassen/blockieren Listen**.</span><span class="sxs-lookup"><span data-stu-id="c62b5-167">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="c62b5-168">Wählen Sie **die Registerkarte URLs** oder die **Registerkarte Dateien** aus.</span><span class="sxs-lookup"><span data-stu-id="c62b5-168">Select the **URLs** tab or the **Files** tab.</span></span>

<span data-ttu-id="c62b5-169">Klicken Sie auf die folgenden Spaltenüberschriften, um sie in aufsteigender oder absteigender Reihenfolge zu sortieren:</span><span class="sxs-lookup"><span data-stu-id="c62b5-169">Click on the following column headings to sort in ascending or descending order:</span></span>

- <span data-ttu-id="c62b5-170">**Wert**: Die URL oder der Dateihash.</span><span class="sxs-lookup"><span data-stu-id="c62b5-170">**Value**: The URL or the file hash.</span></span>
- <span data-ttu-id="c62b5-171">**Datum der letzten Aktualisierung**</span><span class="sxs-lookup"><span data-stu-id="c62b5-171">**Last updated date**</span></span>
- <span data-ttu-id="c62b5-172">**Ablaufdatum**</span><span class="sxs-lookup"><span data-stu-id="c62b5-172">**Expiration date**</span></span>
- <span data-ttu-id="c62b5-173">**Hinweis**</span><span class="sxs-lookup"><span data-stu-id="c62b5-173">**Note**</span></span>

<span data-ttu-id="c62b5-174">Klicken **Sie auf Suchen,** geben Sie einen Wert ganz oder teilweise ein, und drücken Sie die EINGABETASTE, um einen bestimmten Wert zu finden.</span><span class="sxs-lookup"><span data-stu-id="c62b5-174">Click **Search**, enter all or part of a value, and then press ENTER to find a specific value.</span></span> <span data-ttu-id="c62b5-175">Wenn Sie fertig sind, klicken Sie auf **Suche löschen Suchsymbol** ![ löschen ](../../media/b6512677-5e7b-42b0-a8a3-3be1d7fa23ee.gif) .</span><span class="sxs-lookup"><span data-stu-id="c62b5-175">When you're finished, click **Clear search** ![Clear search icon](../../media/b6512677-5e7b-42b0-a8a3-3be1d7fa23ee.gif).</span></span>

<span data-ttu-id="c62b5-176">Klicken Sie **auf Filter**.</span><span class="sxs-lookup"><span data-stu-id="c62b5-176">Click **Filter**.</span></span> <span data-ttu-id="c62b5-177">Konfigurieren Sie **im angezeigten** Flyout Filter eine der folgenden Einstellungen:</span><span class="sxs-lookup"><span data-stu-id="c62b5-177">In the **Filter** flyout that appears, configure any of the following settings:</span></span>

- <span data-ttu-id="c62b5-178">**Nie ablaufen:** Wählen Sie aus: ![ Umschalten ](../../media/scc-toggle-off.png) oder Aktivieren: ![ Umschalten auf ](../../media/scc-toggle-on.png) .</span><span class="sxs-lookup"><span data-stu-id="c62b5-178">**Never expire**: Select off: ![Toggle off](../../media/scc-toggle-off.png) or on: ![Toggle on](../../media/scc-toggle-on.png).</span></span>

- <span data-ttu-id="c62b5-179">**Last updated**: Select a start date (**From**), an end date (**To**) or both.</span><span class="sxs-lookup"><span data-stu-id="c62b5-179">**Last updated**: Select a start date (**From**), an end date (**To**) or both.</span></span>

- <span data-ttu-id="c62b5-180">**Ablaufdatum**: Wählen Sie ein Startdatum (**Von**), ein Enddatum (**An**) oder beides aus.</span><span class="sxs-lookup"><span data-stu-id="c62b5-180">**Expiration date**: Select a start date (**From**), an end date (**To**) or both.</span></span>

<span data-ttu-id="c62b5-181">Klicken Sie nach Abschluss des Abschlusses auf **Übernehmen**.</span><span class="sxs-lookup"><span data-stu-id="c62b5-181">When you're finished, click **Apply**.</span></span>

<span data-ttu-id="c62b5-182">Klicken Sie zum Löschen vorhandener Filter auf **Filter,** und klicken Sie im angezeigten **Flyout** Filter **auf Filter löschen.**</span><span class="sxs-lookup"><span data-stu-id="c62b5-182">To clear existing filters, click **Filter**, and in the **Filter** flyout that appears, click **Clear filters**.</span></span>

## <a name="use-the-security--compliance-center-to-modify-block-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="c62b5-183">Verwenden des Security & Compliance Center zum Ändern von Blockeinträgen in der Mandantenzu-/-sperrliste</span><span class="sxs-lookup"><span data-stu-id="c62b5-183">Use the Security & Compliance Center to modify block entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="c62b5-184">Sie können die vorhandenen blockierten URL- oder Dateiwerte in einem Eintrag nicht ändern.</span><span class="sxs-lookup"><span data-stu-id="c62b5-184">You can't modify the existing blocked URL or file values within an entry.</span></span> <span data-ttu-id="c62b5-185">Um diese Werte zu ändern, müssen Sie den Eintrag löschen und neu erstellen.</span><span class="sxs-lookup"><span data-stu-id="c62b5-185">To modify these values, you need to delete and recreate the entry.</span></span>

1. <span data-ttu-id="c62b5-186">Wechseln Sie im Security & Compliance Center zu Richtlinien für die **Bedrohungsverwaltung** \>  \> **Mandanten zulassen/blockieren Listen**.</span><span class="sxs-lookup"><span data-stu-id="c62b5-186">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="c62b5-187">Wählen Sie **die Registerkarte URLs** oder die **Registerkarte Dateien** aus.</span><span class="sxs-lookup"><span data-stu-id="c62b5-187">Select the **URLs** tab or the **Files** tab.</span></span>

3. <span data-ttu-id="c62b5-188">Wählen Sie den Blockeintrag aus, den Sie ändern möchten, und klicken Sie dann auf **Bearbeiten** ![ (Symbol). ](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png)</span><span class="sxs-lookup"><span data-stu-id="c62b5-188">Select the block entry that you want to modify, and then click **Edit** ![Edit icon](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png).</span></span>

4. <span data-ttu-id="c62b5-189">Konfigurieren Sie im angezeigten Flyout die folgenden Einstellungen:</span><span class="sxs-lookup"><span data-stu-id="c62b5-189">In the flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="c62b5-190">**Nie ablaufen:** Gehen Sie wie folgt vor:</span><span class="sxs-lookup"><span data-stu-id="c62b5-190">**Never expire**: Do one of the following steps:</span></span>

     - <span data-ttu-id="c62b5-191">Überprüfen Sie, ob die Einstellung deaktiviert ist ( Umschalten ) und verwenden Sie das Feld Läuft auf, um das Ablaufdatum für ![ ](../../media/scc-toggle-off.png) den Eintrag anzugeben. </span><span class="sxs-lookup"><span data-stu-id="c62b5-191">Verify the setting is turned off (![Toggle off](../../media/scc-toggle-off.png)) and use the **Expires on** box to specify the expiration date for the entry.</span></span>

       <span data-ttu-id="c62b5-192">oder</span><span class="sxs-lookup"><span data-stu-id="c62b5-192">or</span></span>

     - <span data-ttu-id="c62b5-193">Verschieben Sie den Umschalter nach rechts, um den Eintrag so zu konfigurieren, dass er nie abläuft:</span><span class="sxs-lookup"><span data-stu-id="c62b5-193">Move the toggle to the right to configure the entry to never expire:</span></span> ![Umschaltfläche ein](../../media/scc-toggle-on.png)<span data-ttu-id="c62b5-195">.</span><span class="sxs-lookup"><span data-stu-id="c62b5-195">.</span></span>

   - <span data-ttu-id="c62b5-196">**Optionaler Hinweis:** Geben Sie beschreibenden Text für den Eintrag ein.</span><span class="sxs-lookup"><span data-stu-id="c62b5-196">**Optional note**: Enter descriptive text for the entry.</span></span>

5. <span data-ttu-id="c62b5-197">Klicken Sie nach Abschluss des Vorgangs auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="c62b5-197">When you're finished, click **Save**.</span></span>

## <a name="use-the-security--compliance-center-to-remove-block-entries-from-the-tenant-allowblock-list"></a><span data-ttu-id="c62b5-198">Verwenden des Security & Compliance Center zum Entfernen von Sperreinträgen aus der Mandantenzu-/-sperrliste</span><span class="sxs-lookup"><span data-stu-id="c62b5-198">Use the Security & Compliance Center to remove block entries from the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="c62b5-199">Wechseln Sie im Security & Compliance Center zu Richtlinien für die **Bedrohungsverwaltung** \>  \> **Mandanten zulassen/blockieren Listen**.</span><span class="sxs-lookup"><span data-stu-id="c62b5-199">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="c62b5-200">Wählen Sie **die Registerkarte URLs** oder die **Registerkarte Dateien** aus.</span><span class="sxs-lookup"><span data-stu-id="c62b5-200">Select the **URLs** tab or the **Files** tab.</span></span>

3. <span data-ttu-id="c62b5-201">Wählen Sie den Blockeintrag aus, den Sie entfernen möchten, und klicken Sie dann auf **Löschen** ![ Löschen ](../../media/87565fbb-5147-4f22-9ed7-1c18ce664392.png) (Symbol).</span><span class="sxs-lookup"><span data-stu-id="c62b5-201">Select the block entry that you want to remove, and then click **Delete** ![Delete icon](../../media/87565fbb-5147-4f22-9ed7-1c18ce664392.png).</span></span>

4. <span data-ttu-id="c62b5-202">Klicken Sie im angezeigten Warnungsdialogfeld auf **Löschen**.</span><span class="sxs-lookup"><span data-stu-id="c62b5-202">In the warning dialog that appears, click **Delete**.</span></span>

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-the-tenant-allowblock-list"></a><span data-ttu-id="c62b5-203">Verwenden Exchange Online PowerShell oder eigenständiger EOP PowerShell zum Konfigurieren der Mandanten zulassen/Blockieren-Liste</span><span class="sxs-lookup"><span data-stu-id="c62b5-203">Use Exchange Online PowerShell or standalone EOP PowerShell to configure the Tenant Allow/Block List</span></span>

### <a name="use-powershell-to-add-block-entries-to-the-tenant-allowblock-list"></a><span data-ttu-id="c62b5-204">Verwenden von PowerShell zum Hinzufügen von Blockeinträgen zur Mandantenzu-/Sperrliste</span><span class="sxs-lookup"><span data-stu-id="c62b5-204">Use PowerShell to add block entries to the Tenant Allow/Block List</span></span>

<span data-ttu-id="c62b5-205">Verwenden Sie die folgende Syntax, um Blockeinträge in der Mandantenzu-/Sperrliste hinzuzufügen:</span><span class="sxs-lookup"><span data-stu-id="c62b5-205">To add block entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
New-TenantAllowBlockListItems -ListType <Url | FileHash> -Block -Entries <String[]> [-ExpirationDate <DateTime>] [-NoExpiration] [-Notes <String>]
```

<span data-ttu-id="c62b5-206">In diesem Beispiel wird ein Block-URL-Eintrag für contoso.com und alle Unterdomänen hinzugefügt (z. B. contoso.com, www.contoso.com und xyz.abc.contoso.com).</span><span class="sxs-lookup"><span data-stu-id="c62b5-206">This example adds a block URL entry for contoso.com and all subdomains (for example, contoso.com, www.contoso.com, and xyz.abc.contoso.com).</span></span> <span data-ttu-id="c62b5-207">Da wir die Parameter ExpirationDate oder NoExpiration nicht verwendet haben, läuft der Eintrag nach 30 Tagen ab.</span><span class="sxs-lookup"><span data-stu-id="c62b5-207">Because we didn't use the ExpirationDate or NoExpiration parameters, the entry expires after 30 days.</span></span>

```powershell
New-TenantAllowBlockListItems -ListType Url -Block -Entries ~contoso.com
```

<span data-ttu-id="c62b5-208">In diesem Beispiel wird ein Blockdateieintrag für die angegebenen Dateien, die nie abläuft, hinzufügt.</span><span class="sxs-lookup"><span data-stu-id="c62b5-208">This example adds a block file entry for the specified files that never expires.</span></span>

```powershell
New-TenantAllowBlockListItems -ListType FileHash -Block -Entries "768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3","2c0a35409ff0873cfa28b70b8224e9aca2362241c1f0ed6f622fef8d4722fd9a" -NoExpiration
```

<span data-ttu-id="c62b5-209">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [New-TenantAllowBlockListItems](/powershell/module/exchange/new-tenantallowblocklistitems).</span><span class="sxs-lookup"><span data-stu-id="c62b5-209">For detailed syntax and parameter information, see [New-TenantAllowBlockListItems](/powershell/module/exchange/new-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-view-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="c62b5-210">Verwenden von PowerShell zum Anzeigen von Einträgen in der Mandanten-Zulassen-/Sperrliste</span><span class="sxs-lookup"><span data-stu-id="c62b5-210">Use PowerShell to view entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="c62b5-211">Verwenden Sie die folgende Syntax, um Einträge in der Mandantenzu-/Sperrliste anzeigen zu können:</span><span class="sxs-lookup"><span data-stu-id="c62b5-211">To view entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType <Url | FileHash> [-Entry <URLValue | FileHashValue>] [-Block] [-ExpirationDate <DateTime>] [-NoExpiration]
```

<span data-ttu-id="c62b5-212">In diesem Beispiel werden alle blockierten URLs zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="c62b5-212">This example returns all blocked URLs.</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType Url -Block
```

<span data-ttu-id="c62b5-213">In diesem Beispiel werden Informationen für den angegebenen Dateihashwert zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="c62b5-213">This example returns information for the specified file hash value.</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType FileHash -Entry "9f86d081884c7d659a2feaa0c55ad015a3bf4f1b2b0b822cd15d6c15b0f00a08"
```

<span data-ttu-id="c62b5-214">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Get-TenantAllowBlockListItems](/powershell/module/exchange/get-tenantallowblocklistitems).</span><span class="sxs-lookup"><span data-stu-id="c62b5-214">For detailed syntax and parameter information, see [Get-TenantAllowBlockListItems](/powershell/module/exchange/get-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-modify-block-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="c62b5-215">Verwenden von PowerShell zum Ändern von Blockeinträgen in der Mandantenzu-/-sperrliste</span><span class="sxs-lookup"><span data-stu-id="c62b5-215">Use PowerShell to modify block entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="c62b5-216">Sie können die vorhandenen URL- oder Dateiwerte in einem Blockeintrag nicht ändern.</span><span class="sxs-lookup"><span data-stu-id="c62b5-216">You can't modify the existing URL or file values within a block entry.</span></span> <span data-ttu-id="c62b5-217">Um diese Werte zu ändern, müssen Sie den Eintrag löschen und neu erstellen.</span><span class="sxs-lookup"><span data-stu-id="c62b5-217">To modify these values, you need to delete and recreate the entry.</span></span>

<span data-ttu-id="c62b5-218">Verwenden Sie die folgende Syntax, um Blockeinträge in der Mandanten zulassen/blockieren-Liste zu ändern:</span><span class="sxs-lookup"><span data-stu-id="c62b5-218">To modify block entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Set-TenantAllowBlockListItems -ListType <Url | FileHash> -Ids <"Id1","Id2",..."IdN"> [-Block] [-ExpirationDate <DateTime>] [-NoExpiration] [-Notes <String>]
```

<span data-ttu-id="c62b5-219">In diesem Beispiel wird das Ablaufdatum des angegebenen Blockeintrags geändert.</span><span class="sxs-lookup"><span data-stu-id="c62b5-219">This example changes the expiration date of the specified block entry.</span></span>

```powershell
Set-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSRAAAA" -ExpirationDate (Get-Date "5/30/2020 9:30 AM").ToUniversalTime()
```

<span data-ttu-id="c62b5-220">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Set-TenantAllowBlockListItems](/powershell/module/exchange/set-tenantallowblocklistitems).</span><span class="sxs-lookup"><span data-stu-id="c62b5-220">For detailed syntax and parameter information, see [Set-TenantAllowBlockListItems](/powershell/module/exchange/set-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-remove-block-entries-from-the-tenant-allowblock-list"></a><span data-ttu-id="c62b5-221">Verwenden von PowerShell zum Entfernen von Sperreinträgen aus der Mandanten-Zulassen-/Sperrliste</span><span class="sxs-lookup"><span data-stu-id="c62b5-221">Use PowerShell to remove block entries from the Tenant Allow/Block List</span></span>

<span data-ttu-id="c62b5-222">Verwenden Sie die folgende Syntax, um Blockeinträge aus der Mandanten zulassen/blockieren-Liste zu entfernen:</span><span class="sxs-lookup"><span data-stu-id="c62b5-222">To remove block entries from the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Remove-TenantAllowBlockListItems -ListType <Url | FileHash> -Ids <"Id1","Id2",..."IdN">
```

<span data-ttu-id="c62b5-223">In diesem Beispiel wird der angegebene Block-URL-Eintrag aus der Mandanten-Allow/Block List entfernt.</span><span class="sxs-lookup"><span data-stu-id="c62b5-223">This example removes the specified block URL entry from the Tenant Allow/Block List.</span></span>

```powershell
Remove-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSPAAAA0"
```

<span data-ttu-id="c62b5-224">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Remove-TenantAllowBlockListItems](/powershell/module/exchange/remove-tenantallowblocklistitems).</span><span class="sxs-lookup"><span data-stu-id="c62b5-224">For detailed syntax and parameter information, see [Remove-TenantAllowBlockListItems](/powershell/module/exchange/remove-tenantallowblocklistitems).</span></span>

## <a name="url-syntax-for-the-tenant-allowblock-list"></a><span data-ttu-id="c62b5-225">#A0 für die Mandanten-Allow/Block List</span><span class="sxs-lookup"><span data-stu-id="c62b5-225">URL syntax for the Tenant Allow/Block List</span></span>

- <span data-ttu-id="c62b5-226">IP4v- und IPv6-Adressen sind zulässig, TCP/UDP-Ports jedoch nicht.</span><span class="sxs-lookup"><span data-stu-id="c62b5-226">IP4v and IPv6 addresses are allowed, but TCP/UDP ports are not.</span></span>

- <span data-ttu-id="c62b5-227">Dateinamenerweiterungen sind nicht zulässig (z. B. test.pdf).</span><span class="sxs-lookup"><span data-stu-id="c62b5-227">Filename extensions are not allowed (for example, test.pdf).</span></span>

- <span data-ttu-id="c62b5-228">Unicode wird nicht unterstützt, Punycode jedoch.</span><span class="sxs-lookup"><span data-stu-id="c62b5-228">Unicode is not supported, but Punycode is.</span></span>

- <span data-ttu-id="c62b5-229">Hostnamen sind zulässig, wenn alle folgenden Anweisungen zutreffen:</span><span class="sxs-lookup"><span data-stu-id="c62b5-229">Hostnames are allowed if all of the following statements are true:</span></span>
  - <span data-ttu-id="c62b5-230">Der Hostname enthält einen Zeitraum.</span><span class="sxs-lookup"><span data-stu-id="c62b5-230">The hostname contains a period.</span></span>
  - <span data-ttu-id="c62b5-231">Es gibt mindestens ein Zeichen links vom Zeitraum.</span><span class="sxs-lookup"><span data-stu-id="c62b5-231">There is at least one character to the left of the period.</span></span>
  - <span data-ttu-id="c62b5-232">Rechts neben dem Zeitraum befinden sich mindestens zwei Zeichen.</span><span class="sxs-lookup"><span data-stu-id="c62b5-232">There are at least two characters to the right of the period.</span></span>

  <span data-ttu-id="c62b5-233">Beispielsweise ist `t.co` zulässig oder nicht `.com` `contoso.` zulässig.</span><span class="sxs-lookup"><span data-stu-id="c62b5-233">For example, `t.co` is allowed; `.com` or `contoso.` are not allowed.</span></span>

- <span data-ttu-id="c62b5-234">Unterpfade werden nicht impliziert.</span><span class="sxs-lookup"><span data-stu-id="c62b5-234">Subpaths are not implied.</span></span>

  <span data-ttu-id="c62b5-235">Enthält z. `contoso.com` B. nicht `contoso.com/a` .</span><span class="sxs-lookup"><span data-stu-id="c62b5-235">For example, `contoso.com` does not include `contoso.com/a`.</span></span>

- <span data-ttu-id="c62b5-236">Platzhalter (\*) sind in den folgenden Szenarien zulässig:</span><span class="sxs-lookup"><span data-stu-id="c62b5-236">Wildcards (\*) are allowed in the following scenarios:</span></span>

  - <span data-ttu-id="c62b5-237">Auf einen linken Platzhalter muss ein Zeitraum folgen, um eine Unterdomäne anzugeben.</span><span class="sxs-lookup"><span data-stu-id="c62b5-237">A left wildcard must be followed by a period to specify a subdomain.</span></span>

    <span data-ttu-id="c62b5-238">Ist beispielsweise `*.contoso.com` zulässig; `*contoso.com` ist nicht zulässig.</span><span class="sxs-lookup"><span data-stu-id="c62b5-238">For example, `*.contoso.com` is allowed; `*contoso.com` is not allowed.</span></span>

  - <span data-ttu-id="c62b5-239">Ein rechter Platzhalter muss einem Schrägstrich (/) folgen, um einen Pfad anzugeben.</span><span class="sxs-lookup"><span data-stu-id="c62b5-239">A right wildcard must follow a forward slash (/) to specify a path.</span></span>

    <span data-ttu-id="c62b5-240">Beispielsweise ist `contoso.com/*` zulässig oder nicht `contoso.com*` `contoso.com/ab*` zulässig.</span><span class="sxs-lookup"><span data-stu-id="c62b5-240">For example, `contoso.com/*` is allowed; `contoso.com*` or `contoso.com/ab*` are not allowed.</span></span>

  - <span data-ttu-id="c62b5-241">Alle Unterpfade werden nicht durch einen rechten Platzhalter impliziert.</span><span class="sxs-lookup"><span data-stu-id="c62b5-241">All subpaths are not implied by a right wildcard.</span></span>

    <span data-ttu-id="c62b5-242">Enthält z. `contoso.com/*` B. nicht `contoso.com/a` .</span><span class="sxs-lookup"><span data-stu-id="c62b5-242">For example, `contoso.com/*` does not include `contoso.com/a`.</span></span>

  - <span data-ttu-id="c62b5-243">`*.com*` ist ungültig (keine auflösbare Domäne, und der rechte Platzhalter folgt keinem Schrägstrich).</span><span class="sxs-lookup"><span data-stu-id="c62b5-243">`*.com*` is invalid (not a resolvable domain and the right wildcard does not follow a forward slash).</span></span>

  - <span data-ttu-id="c62b5-244">Platzhalter sind in IP-Adressen nicht zulässig.</span><span class="sxs-lookup"><span data-stu-id="c62b5-244">Wildcards are not allowed in IP addresses.</span></span>

- <span data-ttu-id="c62b5-245">Das Tildezeichen (~) ist in den folgenden Szenarien verfügbar:</span><span class="sxs-lookup"><span data-stu-id="c62b5-245">The tilde (~) character is available in the following scenarios:</span></span>

  - <span data-ttu-id="c62b5-246">Eine linke Tilde impliziert eine Domäne und alle Unterdomänen.</span><span class="sxs-lookup"><span data-stu-id="c62b5-246">A left tilde implies a domain and all subdomains.</span></span>

    <span data-ttu-id="c62b5-247">Enthält `~contoso.com` z. `contoso.com` B. und `*.contoso.com` .</span><span class="sxs-lookup"><span data-stu-id="c62b5-247">For example `~contoso.com` includes `contoso.com` and `*.contoso.com`.</span></span>

- <span data-ttu-id="c62b5-248">URL-Einträge, die Protokolle (z. B. , oder ) enthalten, werden fehlschlagen, da `http://` URL-Einträge für alle Protokolle `https://` `ftp://` gelten.</span><span class="sxs-lookup"><span data-stu-id="c62b5-248">URL entries that contain protocols (for example, `http://`, `https://`, or `ftp://`) will fail, because URL entries apply to all protocols.</span></span>

- <span data-ttu-id="c62b5-249">Ein Benutzername oder Kennwort wird nicht unterstützt oder ist nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="c62b5-249">A username or password aren't supported or required.</span></span>

- <span data-ttu-id="c62b5-250">Anführungszeichen (' oder ") sind ungültige Zeichen.</span><span class="sxs-lookup"><span data-stu-id="c62b5-250">Quotes (' or ") are invalid characters.</span></span>

- <span data-ttu-id="c62b5-251">Eine URL sollte nach Möglichkeit alle Umleitungen enthalten.</span><span class="sxs-lookup"><span data-stu-id="c62b5-251">A URL should include all redirects where possible.</span></span>

### <a name="url-entry-scenarios"></a><span data-ttu-id="c62b5-252">Szenarien für den URL-Eintrag</span><span class="sxs-lookup"><span data-stu-id="c62b5-252">URL entry scenarios</span></span>

<span data-ttu-id="c62b5-253">Gültige URL-Einträge und deren Ergebnisse werden in den folgenden Abschnitten beschrieben.</span><span class="sxs-lookup"><span data-stu-id="c62b5-253">Valid URL entries and their results are described in the following sections.</span></span>

#### <a name="scenario-no-wildcards"></a><span data-ttu-id="c62b5-254">Szenario: Keine Platzhalter</span><span class="sxs-lookup"><span data-stu-id="c62b5-254">Scenario: No wildcards</span></span>

<span data-ttu-id="c62b5-255">**Eintrag**: `contoso.com`</span><span class="sxs-lookup"><span data-stu-id="c62b5-255">**Entry**: `contoso.com`</span></span>

- <span data-ttu-id="c62b5-256">**Übereinstimmung zulassen**: contoso.com</span><span class="sxs-lookup"><span data-stu-id="c62b5-256">**Allow match**: contoso.com</span></span>

- <span data-ttu-id="c62b5-257">**Nicht übereinstimmend zulassen:**</span><span class="sxs-lookup"><span data-stu-id="c62b5-257">**Allow not matched**:</span></span>

  - <span data-ttu-id="c62b5-258">abc-contoso.com</span><span class="sxs-lookup"><span data-stu-id="c62b5-258">abc-contoso.com</span></span>
  - <span data-ttu-id="c62b5-259">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="c62b5-259">contoso.com/a</span></span>
  - <span data-ttu-id="c62b5-260">payroll.contoso.com</span><span class="sxs-lookup"><span data-stu-id="c62b5-260">payroll.contoso.com</span></span>
  - <span data-ttu-id="c62b5-261">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="c62b5-261">test.com/contoso.com</span></span>
  - <span data-ttu-id="c62b5-262">test.com/q=contoso.com</span><span class="sxs-lookup"><span data-stu-id="c62b5-262">test.com/q=contoso.com</span></span>
  - <span data-ttu-id="c62b5-263">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="c62b5-263">www.contoso.com</span></span>
  - <span data-ttu-id="c62b5-264">www.contoso.com/q=a@contoso.com</span><span class="sxs-lookup"><span data-stu-id="c62b5-264">www.contoso.com/q=a@contoso.com</span></span>

- <span data-ttu-id="c62b5-265">**Übereinstimmung blockieren**:</span><span class="sxs-lookup"><span data-stu-id="c62b5-265">**Block match**:</span></span>

  - <span data-ttu-id="c62b5-266">contoso.com</span><span class="sxs-lookup"><span data-stu-id="c62b5-266">contoso.com</span></span>
  - <span data-ttu-id="c62b5-267">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="c62b5-267">contoso.com/a</span></span>
  - <span data-ttu-id="c62b5-268">payroll.contoso.com</span><span class="sxs-lookup"><span data-stu-id="c62b5-268">payroll.contoso.com</span></span>
  - <span data-ttu-id="c62b5-269">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="c62b5-269">test.com/contoso.com</span></span>
  - <span data-ttu-id="c62b5-270">test.com/q=contoso.com</span><span class="sxs-lookup"><span data-stu-id="c62b5-270">test.com/q=contoso.com</span></span>
  - <span data-ttu-id="c62b5-271">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="c62b5-271">www.contoso.com</span></span>
  - <span data-ttu-id="c62b5-272">www.contoso.com/q=a@contoso.com</span><span class="sxs-lookup"><span data-stu-id="c62b5-272">www.contoso.com/q=a@contoso.com</span></span>

- <span data-ttu-id="c62b5-273">**Block nicht übereinstimmend**: abc-contoso.com</span><span class="sxs-lookup"><span data-stu-id="c62b5-273">**Block not matched**: abc-contoso.com</span></span>

#### <a name="scenario-left-wildcard-subdomain"></a><span data-ttu-id="c62b5-274">Szenario: Linker Platzhalter (Unterdomäne)</span><span class="sxs-lookup"><span data-stu-id="c62b5-274">Scenario: Left wildcard (subdomain)</span></span>

<span data-ttu-id="c62b5-275">**Eintrag**: `*.contoso.com`</span><span class="sxs-lookup"><span data-stu-id="c62b5-275">**Entry**: `*.contoso.com`</span></span>

- <span data-ttu-id="c62b5-276">**Übereinstimmung zulassen** und **Übereinstimmung blockieren**:</span><span class="sxs-lookup"><span data-stu-id="c62b5-276">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="c62b5-277">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="c62b5-277">www.contoso.com</span></span>
  - <span data-ttu-id="c62b5-278">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="c62b5-278">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="c62b5-279">**Allow not matched** and **Block not matched**:</span><span class="sxs-lookup"><span data-stu-id="c62b5-279">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="c62b5-280">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="c62b5-280">123contoso.com</span></span>
  - <span data-ttu-id="c62b5-281">contoso.com</span><span class="sxs-lookup"><span data-stu-id="c62b5-281">contoso.com</span></span>
  - <span data-ttu-id="c62b5-282">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="c62b5-282">test.com/contoso.com</span></span>
  - <span data-ttu-id="c62b5-283">www.contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="c62b5-283">www.contoso.com/abc</span></span>

#### <a name="scenario-right-wildcard-at-top-of-path"></a><span data-ttu-id="c62b5-284">Szenario: Rechter Platzhalter am oberen Rand des Pfads</span><span class="sxs-lookup"><span data-stu-id="c62b5-284">Scenario: Right wildcard at top of path</span></span>

<span data-ttu-id="c62b5-285">**Eintrag**: `contoso.com/a/*`</span><span class="sxs-lookup"><span data-stu-id="c62b5-285">**Entry**: `contoso.com/a/*`</span></span>

- <span data-ttu-id="c62b5-286">**Übereinstimmung zulassen** und **Übereinstimmung blockieren**:</span><span class="sxs-lookup"><span data-stu-id="c62b5-286">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="c62b5-287">contoso.com/a/b</span><span class="sxs-lookup"><span data-stu-id="c62b5-287">contoso.com/a/b</span></span>
  - <span data-ttu-id="c62b5-288">contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="c62b5-288">contoso.com/a/b/c</span></span>
  - <span data-ttu-id="c62b5-289">contoso.com/a/?q=joe@t.com</span><span class="sxs-lookup"><span data-stu-id="c62b5-289">contoso.com/a/?q=joe@t.com</span></span>

- <span data-ttu-id="c62b5-290">**Allow not matched** and **Block not matched**:</span><span class="sxs-lookup"><span data-stu-id="c62b5-290">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="c62b5-291">contoso.com</span><span class="sxs-lookup"><span data-stu-id="c62b5-291">contoso.com</span></span>
  - <span data-ttu-id="c62b5-292">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="c62b5-292">contoso.com/a</span></span>
  - <span data-ttu-id="c62b5-293">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="c62b5-293">www.contoso.com</span></span>
  - <span data-ttu-id="c62b5-294">www.contoso.com/q=a@contoso.com</span><span class="sxs-lookup"><span data-stu-id="c62b5-294">www.contoso.com/q=a@contoso.com</span></span>

#### <a name="scenario-left-tilde"></a><span data-ttu-id="c62b5-295">Szenario: Left tilde</span><span class="sxs-lookup"><span data-stu-id="c62b5-295">Scenario: Left tilde</span></span>

<span data-ttu-id="c62b5-296">**Eintrag**: `~contoso.com`</span><span class="sxs-lookup"><span data-stu-id="c62b5-296">**Entry**: `~contoso.com`</span></span>

- <span data-ttu-id="c62b5-297">**Übereinstimmung zulassen** und **Übereinstimmung blockieren**:</span><span class="sxs-lookup"><span data-stu-id="c62b5-297">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="c62b5-298">contoso.com</span><span class="sxs-lookup"><span data-stu-id="c62b5-298">contoso.com</span></span>
  - <span data-ttu-id="c62b5-299">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="c62b5-299">www.contoso.com</span></span>
  - <span data-ttu-id="c62b5-300">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="c62b5-300">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="c62b5-301">**Allow not matched** and **Block not matched**:</span><span class="sxs-lookup"><span data-stu-id="c62b5-301">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="c62b5-302">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="c62b5-302">123contoso.com</span></span>
  - <span data-ttu-id="c62b5-303">contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="c62b5-303">contoso.com/abc</span></span>
  - <span data-ttu-id="c62b5-304">www.contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="c62b5-304">www.contoso.com/abc</span></span>

#### <a name="scenario-right-wildcard-suffix"></a><span data-ttu-id="c62b5-305">Szenario: Rechtes Platzhaltersuffix</span><span class="sxs-lookup"><span data-stu-id="c62b5-305">Scenario: Right wildcard suffix</span></span>

<span data-ttu-id="c62b5-306">**Eintrag**: `contoso.com/*`</span><span class="sxs-lookup"><span data-stu-id="c62b5-306">**Entry**: `contoso.com/*`</span></span>

- <span data-ttu-id="c62b5-307">**Übereinstimmung zulassen** und **Übereinstimmung blockieren**:</span><span class="sxs-lookup"><span data-stu-id="c62b5-307">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="c62b5-308">contoso.com/?q=whatever@fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="c62b5-308">contoso.com/?q=whatever@fabrikam.com</span></span>
  - <span data-ttu-id="c62b5-309">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="c62b5-309">contoso.com/a</span></span>
  - <span data-ttu-id="c62b5-310">contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="c62b5-310">contoso.com/a/b/c</span></span>
  - <span data-ttu-id="c62b5-311">contoso.com/ab</span><span class="sxs-lookup"><span data-stu-id="c62b5-311">contoso.com/ab</span></span>
  - <span data-ttu-id="c62b5-312">contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="c62b5-312">contoso.com/b</span></span>
  - <span data-ttu-id="c62b5-313">contoso.com/b/a/c</span><span class="sxs-lookup"><span data-stu-id="c62b5-313">contoso.com/b/a/c</span></span>
  - <span data-ttu-id="c62b5-314">contoso.com/ba</span><span class="sxs-lookup"><span data-stu-id="c62b5-314">contoso.com/ba</span></span>

- <span data-ttu-id="c62b5-315">**Nicht übereinstimmend zulassen und** **Block nicht** übereinstimmen: contoso.com</span><span class="sxs-lookup"><span data-stu-id="c62b5-315">**Allow not matched** and **Block not matched**: contoso.com</span></span>

#### <a name="scenario-left-wildcard-subdomain-and-right-wildcard-suffix"></a><span data-ttu-id="c62b5-316">Szenario: Linke Platzhalterunterdomäne und rechtes Platzhaltersuffix</span><span class="sxs-lookup"><span data-stu-id="c62b5-316">Scenario: Left wildcard subdomain and right wildcard suffix</span></span>

<span data-ttu-id="c62b5-317">**Eintrag**: `*.contoso.com/*`</span><span class="sxs-lookup"><span data-stu-id="c62b5-317">**Entry**: `*.contoso.com/*`</span></span>

- <span data-ttu-id="c62b5-318">**Übereinstimmung zulassen** und **Übereinstimmung blockieren**:</span><span class="sxs-lookup"><span data-stu-id="c62b5-318">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="c62b5-319">abc.contoso.com/ab</span><span class="sxs-lookup"><span data-stu-id="c62b5-319">abc.contoso.com/ab</span></span>
  - <span data-ttu-id="c62b5-320">abc.xyz.contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="c62b5-320">abc.xyz.contoso.com/a/b/c</span></span>
  - <span data-ttu-id="c62b5-321">www.contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="c62b5-321">www.contoso.com/a</span></span>
  - <span data-ttu-id="c62b5-322">www.contoso.com/b/a/c</span><span class="sxs-lookup"><span data-stu-id="c62b5-322">www.contoso.com/b/a/c</span></span>
  - <span data-ttu-id="c62b5-323">xyz.contoso.com/ba</span><span class="sxs-lookup"><span data-stu-id="c62b5-323">xyz.contoso.com/ba</span></span>

- <span data-ttu-id="c62b5-324">**Nicht übereinstimmend zulassen und** **Block nicht** übereinstimmen : contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="c62b5-324">**Allow not matched** and **Block not matched**: contoso.com/b</span></span>

#### <a name="scenario-left-and-right-tilde"></a><span data-ttu-id="c62b5-325">Szenario: Linker und rechter Tilde</span><span class="sxs-lookup"><span data-stu-id="c62b5-325">Scenario: Left and right tilde</span></span>

<span data-ttu-id="c62b5-326">**Eintrag**: `~contoso.com~`</span><span class="sxs-lookup"><span data-stu-id="c62b5-326">**Entry**: `~contoso.com~`</span></span>

- <span data-ttu-id="c62b5-327">**Übereinstimmung zulassen** und **Übereinstimmung blockieren**:</span><span class="sxs-lookup"><span data-stu-id="c62b5-327">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="c62b5-328">contoso.com</span><span class="sxs-lookup"><span data-stu-id="c62b5-328">contoso.com</span></span>
  - <span data-ttu-id="c62b5-329">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="c62b5-329">contoso.com/a</span></span>
  - <span data-ttu-id="c62b5-330">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="c62b5-330">www.contoso.com</span></span>
  - <span data-ttu-id="c62b5-331">www.contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="c62b5-331">www.contoso.com/b</span></span>
  - <span data-ttu-id="c62b5-332">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="c62b5-332">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="c62b5-333">**Allow not matched** and **Block not matched**:</span><span class="sxs-lookup"><span data-stu-id="c62b5-333">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="c62b5-334">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="c62b5-334">123contoso.com</span></span>
  - <span data-ttu-id="c62b5-335">contoso.org</span><span class="sxs-lookup"><span data-stu-id="c62b5-335">contoso.org</span></span>

#### <a name="scenario-ip-address"></a><span data-ttu-id="c62b5-336">Szenario: IP-Adresse</span><span class="sxs-lookup"><span data-stu-id="c62b5-336">Scenario: IP address</span></span>

<span data-ttu-id="c62b5-337">**Eintrag**: `1.2.3.4`</span><span class="sxs-lookup"><span data-stu-id="c62b5-337">**Entry**: `1.2.3.4`</span></span>

- <span data-ttu-id="c62b5-338">**Übereinstimmung zulassen** und **Übereinstimmung blockieren**: 1.2.3.4</span><span class="sxs-lookup"><span data-stu-id="c62b5-338">**Allow match** and **Block match**: 1.2.3.4</span></span>

- <span data-ttu-id="c62b5-339">**Allow not matched** and **Block not matched**:</span><span class="sxs-lookup"><span data-stu-id="c62b5-339">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="c62b5-340">1.2.3.4/a</span><span class="sxs-lookup"><span data-stu-id="c62b5-340">1.2.3.4/a</span></span>
  - <span data-ttu-id="c62b5-341">11.2.3.4/a</span><span class="sxs-lookup"><span data-stu-id="c62b5-341">11.2.3.4/a</span></span>

#### <a name="ip-address-with-right-wildcard"></a><span data-ttu-id="c62b5-342">IP-Adresse mit rechtem Platzhalter</span><span class="sxs-lookup"><span data-stu-id="c62b5-342">IP address with right wildcard</span></span>

<span data-ttu-id="c62b5-343">**Eintrag**: `1.2.3.4/*`</span><span class="sxs-lookup"><span data-stu-id="c62b5-343">**Entry**: `1.2.3.4/*`</span></span>

- <span data-ttu-id="c62b5-344">**Übereinstimmung zulassen** und **Übereinstimmung blockieren**:</span><span class="sxs-lookup"><span data-stu-id="c62b5-344">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="c62b5-345">1.2.3.4/b</span><span class="sxs-lookup"><span data-stu-id="c62b5-345">1.2.3.4/b</span></span>
  - <span data-ttu-id="c62b5-346">1.2.3.4/baaaa</span><span class="sxs-lookup"><span data-stu-id="c62b5-346">1.2.3.4/baaaa</span></span>

### <a name="examples-of-invalid-entries"></a><span data-ttu-id="c62b5-347">Beispiele für ungültige Einträge</span><span class="sxs-lookup"><span data-stu-id="c62b5-347">Examples of invalid entries</span></span>

<span data-ttu-id="c62b5-348">Die folgenden Einträge sind ungültig:</span><span class="sxs-lookup"><span data-stu-id="c62b5-348">The following entries are invalid:</span></span>

- <span data-ttu-id="c62b5-349">**Fehlende oder ungültige Domänenwerte**:</span><span class="sxs-lookup"><span data-stu-id="c62b5-349">**Missing or invalid domain values**:</span></span>

  - <span data-ttu-id="c62b5-350">contoso</span><span class="sxs-lookup"><span data-stu-id="c62b5-350">contoso</span></span>
  - <span data-ttu-id="c62b5-351">\*.contoso.\*</span><span class="sxs-lookup"><span data-stu-id="c62b5-351">\*.contoso.\*</span></span>
  - <span data-ttu-id="c62b5-352">\*.com</span><span class="sxs-lookup"><span data-stu-id="c62b5-352">\*.com</span></span>
  - <span data-ttu-id="c62b5-353">\*.PDF</span><span class="sxs-lookup"><span data-stu-id="c62b5-353">\*.pdf</span></span>

- <span data-ttu-id="c62b5-354">**Platzhalter für Text oder ohne Abstandszeichen**:</span><span class="sxs-lookup"><span data-stu-id="c62b5-354">**Wildcard on text or without spacing characters**:</span></span>

  - <span data-ttu-id="c62b5-355">\*contoso.com</span><span class="sxs-lookup"><span data-stu-id="c62b5-355">\*contoso.com</span></span>
  - <span data-ttu-id="c62b5-356">contoso.com\*</span><span class="sxs-lookup"><span data-stu-id="c62b5-356">contoso.com\*</span></span>
  - <span data-ttu-id="c62b5-357">\*1.2.3.4</span><span class="sxs-lookup"><span data-stu-id="c62b5-357">\*1.2.3.4</span></span>
  - <span data-ttu-id="c62b5-358">1.2.3.4\*</span><span class="sxs-lookup"><span data-stu-id="c62b5-358">1.2.3.4\*</span></span>
  - <span data-ttu-id="c62b5-359">contoso.com/a\*</span><span class="sxs-lookup"><span data-stu-id="c62b5-359">contoso.com/a\*</span></span>
  - <span data-ttu-id="c62b5-360">contoso.com/ab\*</span><span class="sxs-lookup"><span data-stu-id="c62b5-360">contoso.com/ab\*</span></span>

- <span data-ttu-id="c62b5-361">**IP-Adressen mit Ports**:</span><span class="sxs-lookup"><span data-stu-id="c62b5-361">**IP addresses with ports**:</span></span>

  - <span data-ttu-id="c62b5-362">contoso.com:443</span><span class="sxs-lookup"><span data-stu-id="c62b5-362">contoso.com:443</span></span>
  - <span data-ttu-id="c62b5-363">abc.contoso.com:25</span><span class="sxs-lookup"><span data-stu-id="c62b5-363">abc.contoso.com:25</span></span>

- <span data-ttu-id="c62b5-364">**Nicht beschreibende Platzhalter**:</span><span class="sxs-lookup"><span data-stu-id="c62b5-364">**Non-descriptive wildcards**:</span></span>

  - \*
  - <span data-ttu-id="c62b5-365">\*.\*</span><span class="sxs-lookup"><span data-stu-id="c62b5-365">\*.\*</span></span>

- <span data-ttu-id="c62b5-366">**Mittlere Platzhalter**:</span><span class="sxs-lookup"><span data-stu-id="c62b5-366">**Middle wildcards**:</span></span>

  - <span data-ttu-id="c62b5-367">conto \* so.com</span><span class="sxs-lookup"><span data-stu-id="c62b5-367">conto\*so.com</span></span>
  - <span data-ttu-id="c62b5-368">conto~so.com</span><span class="sxs-lookup"><span data-stu-id="c62b5-368">conto~so.com</span></span>

- <span data-ttu-id="c62b5-369">**Doppelte Platzhalter**</span><span class="sxs-lookup"><span data-stu-id="c62b5-369">**Double wildcards**</span></span>

  - <span data-ttu-id="c62b5-370">contoso.com/\*\*</span><span class="sxs-lookup"><span data-stu-id="c62b5-370">contoso.com/\*\*</span></span>
  - <span data-ttu-id="c62b5-371">contoso.com/\*/\*</span><span class="sxs-lookup"><span data-stu-id="c62b5-371">contoso.com/\*/\*</span></span>
