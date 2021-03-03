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
ms.openlocfilehash: 960fbf26b610485fb46c935b04aedcc593b85752
ms.sourcegitcommit: 070724118be25cd83418d2a56863da95582dae65
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/03/2021
ms.locfileid: "50407250"
---
# <a name="manage-the-tenant-allowblock-list"></a><span data-ttu-id="eb056-103">Verwalten der Zulassungs-/Sperrliste des Mandanten</span><span class="sxs-lookup"><span data-stu-id="eb056-103">Manage the Tenant Allow/Block List</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="eb056-104">**Gilt für**</span><span class="sxs-lookup"><span data-stu-id="eb056-104">**Applies to**</span></span>
- [<span data-ttu-id="eb056-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="eb056-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="eb056-106">Microsoft Defender für Office 365 Plan 1 und Plan 2</span><span class="sxs-lookup"><span data-stu-id="eb056-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="eb056-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="eb056-107">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

> [!NOTE]
>
> <span data-ttu-id="eb056-108">Die in diesem Artikel beschriebenen Features befinden sich in Vorschau, können geändert werden und sind nicht in allen Organisationen verfügbar.</span><span class="sxs-lookup"><span data-stu-id="eb056-108">The features described in this article are in Preview, are subject to change, and are not available in all organizations.</span></span>
>
> <span data-ttu-id="eb056-109">Sie können zu **diesem Zeitpunkt** keine zulässigen Elemente in der Mandanten zulassen/blockieren-Liste konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="eb056-109">You can't **configure** allowed items in the Tenant Allow/Block List at this time.</span></span>

<span data-ttu-id="eb056-110">In Microsoft 365-Organisationen mit Postfächern in Exchange Online oder eigenständigen Exchange Online Protection (EOP)-Organisationen ohne Exchange Online-Postfächer können Sie mit dem EOP-Filterungs-Urteil nicht einverstanden sein.</span><span class="sxs-lookup"><span data-stu-id="eb056-110">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, you might disagree with the EOP filtering verdict.</span></span> <span data-ttu-id="eb056-111">Beispielsweise kann eine gute Nachricht als ungültig (falsch positiv) gekennzeichnet werden, oder eine schlechte Nachricht kann als ungültig (falsch negativ) zugelassen werden.</span><span class="sxs-lookup"><span data-stu-id="eb056-111">For example, a good message might be marked as bad (a false positive), or a bad message might be allowed through (a false negative).</span></span>

<span data-ttu-id="eb056-112">Mit der Liste Mandanten zulassen/blockieren im Security & Compliance Center können Sie die Microsoft 365-Filterungs-Urteile manuell außer Kraft setzen.</span><span class="sxs-lookup"><span data-stu-id="eb056-112">The Tenant Allow/Block List in the Security & Compliance Center gives you a way to manually override the Microsoft 365 filtering verdicts.</span></span> <span data-ttu-id="eb056-113">Die Mandanten zulassen/blockieren Liste wird während des Nachrichtenflusses und zum Zeitpunkt der Benutzerklicks verwendet.</span><span class="sxs-lookup"><span data-stu-id="eb056-113">The Tenant Allow/Block List is used during mail flow and at the time of user clicks.</span></span> <span data-ttu-id="eb056-114">Sie können URLs oder Dateien angeben, die immer blockiert werden.</span><span class="sxs-lookup"><span data-stu-id="eb056-114">You can specify URLs or files to always block.</span></span>

<span data-ttu-id="eb056-115">In diesem Artikel wird beschrieben, wie Sie Einträge in der Mandanten zulassen/blockieren-Liste im Security & Compliance Center oder in PowerShell (Exchange Online PowerShell für Microsoft 365-Organisationen mit Postfächern in Exchange Online; eigenständige EOP PowerShell für Organisationen ohne Exchange &) konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="eb056-115">This article describes how to configure entries in the Tenant Allow/Block List in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="eb056-116">Was sollten Sie wissen, bevor Sie beginnen?</span><span class="sxs-lookup"><span data-stu-id="eb056-116">What do you need to know before you begin?</span></span>

- <span data-ttu-id="eb056-117">Sie öffnen das Security & Compliance Center unter <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="eb056-117">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="eb056-118">Um direkt zur Seite **Mandanten zulassen/blockieren zu** wechseln, verwenden Sie <https://protection.office.com/tenantAllowBlockList> .</span><span class="sxs-lookup"><span data-stu-id="eb056-118">To go directly to the **Tenant Allow/Block List** page, use <https://protection.office.com/tenantAllowBlockList>.</span></span>

- <span data-ttu-id="eb056-119">Sie geben Dateien mithilfe des SHA256-Hashwerts der Datei an.</span><span class="sxs-lookup"><span data-stu-id="eb056-119">You specify files by using the SHA256 hash value of the file.</span></span> <span data-ttu-id="eb056-120">Führen Sie den folgenden Befehl in einer Eingabeaufforderung aus, um den SHA256-Hashwert einer Datei in Windows zu finden:</span><span class="sxs-lookup"><span data-stu-id="eb056-120">To find the SHA256 hash value of a file in Windows, run the following command in a Command Prompt:</span></span>

  ```dos
  certutil.exe -hashfile "<Path>\<Filename>" SHA256
  ```

  <span data-ttu-id="eb056-121">Ein Beispielwert ist `768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3a` .</span><span class="sxs-lookup"><span data-stu-id="eb056-121">An example value is `768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3a`.</span></span> <span data-ttu-id="eb056-122">#A0 (Perceptual Hash) werden nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="eb056-122">Perceptual hash (pHash) values are not supported.</span></span>

- <span data-ttu-id="eb056-123">Die verfügbaren #A0 werden weiter unten in diesem Artikel in der #A1 für den Abschnitt [Mandanten zulassen/blockieren](#url-syntax-for-the-tenant-allowblock-list) beschrieben.</span><span class="sxs-lookup"><span data-stu-id="eb056-123">The available URL values are described in the [URL syntax for the Tenant Allow/Block List](#url-syntax-for-the-tenant-allowblock-list) section later in this article.</span></span>

- <span data-ttu-id="eb056-124">Die Mandantenzu-/-sperrliste ermöglicht maximal 500 Einträge für URLs und 500 Einträge für Dateihashes.</span><span class="sxs-lookup"><span data-stu-id="eb056-124">The Tenant Allow/Block List allows a maximum of 500 entries for URLs, and 500 entries for file hashes.</span></span>

- <span data-ttu-id="eb056-125">Ein Eintrag sollte innerhalb von 15 Minuten aktiv sein.</span><span class="sxs-lookup"><span data-stu-id="eb056-125">An entry should be active within 15 minutes.</span></span>

- <span data-ttu-id="eb056-126">Standardmäßig laufen Einträge in der Mandanten-Zulassen-/Sperrliste nach 30 Tagen ab.</span><span class="sxs-lookup"><span data-stu-id="eb056-126">By default, entries in the Tenant Allow/Block List will expire after 30 days.</span></span> <span data-ttu-id="eb056-127">Sie können ein Datum angeben oder festlegen, dass es nie abläuft.</span><span class="sxs-lookup"><span data-stu-id="eb056-127">You can specify a date or set them to never expire.</span></span>

- <span data-ttu-id="eb056-128">Wie Sie eine Verbindung mit Exchange Online PowerShell herstellen, finden Sie unter [Herstellen einer Verbindung mit Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="eb056-128">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="eb056-129">Informationen zum Herstellen einer Verbindung mit dem eigenständigen Exchange Online Protection PowerShell finden Sie unter [Verbinden mit PowerShell in Exchange Online Protection](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="eb056-129">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="eb056-130">Bevor Sie die Verfahren in diesem Artikel tun können, müssen Ihnen in **Exchange Online** die entsprechenden Berechtigungen zugewiesen werden:</span><span class="sxs-lookup"><span data-stu-id="eb056-130">You need to be assigned permissions in **Exchange Online** before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="eb056-131">Zum Hinzufügen und Entfernen von Werten aus der Mandantenberechtigungs-/Sperrliste müssen Sie Mitglied der Rollengruppen Organisationsverwaltung oder **Sicherheitsadministrator** sein. </span><span class="sxs-lookup"><span data-stu-id="eb056-131">To add and remove values from the Tenant Allow/Block List, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="eb056-132">Für den schreibgeschützten Zugriff auf die Mandantenzugriffs-/Sperrliste müssen Sie Mitglied der Rollengruppen **"Globaler Leser"** oder **"Sicherheitsleser"** sein.</span><span class="sxs-lookup"><span data-stu-id="eb056-132">For read-only access to the Tenant Allow/Block List, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="eb056-133">Weitere Informationen finden Sie unter [Berechtigungen in Exchange Online](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo).</span><span class="sxs-lookup"><span data-stu-id="eb056-133">For more information, see [Permissions in Exchange Online](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo).</span></span>

  <span data-ttu-id="eb056-134">**Hinweise**:</span><span class="sxs-lookup"><span data-stu-id="eb056-134">**Notes**:</span></span>

  - <span data-ttu-id="eb056-135">Durch hinzufügen von Benutzern zur entsprechenden Azure Active Directory-Rolle im Microsoft  365 Admin Center erhalten Benutzer die erforderlichen Berechtigungen und Berechtigungen für andere Features in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="eb056-135">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="eb056-136">Weitere Informationen finden Sie unter [Informationen zu Administratorrollen](../../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="eb056-136">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  - <span data-ttu-id="eb056-137">Die Rollengruppe **Organisationsverwaltung mit Leserechten** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) ermöglicht auch einen schreibgeschützten Zugriff auf das Feature.</span><span class="sxs-lookup"><span data-stu-id="eb056-137">The **View-Only Organization Management** role group in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

## <a name="use-the-security--compliance-center-to-create-url-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="eb056-138">Verwenden des Security & Compliance Center zum Erstellen von URL-Einträgen in der Mandantenzu-/-sperrliste</span><span class="sxs-lookup"><span data-stu-id="eb056-138">Use the Security & Compliance Center to create URL entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="eb056-139">Weitere Informationen zur Syntax für #A0 finden Sie in der URL-Syntax für den Abschnitt [Mandantenzu-/Sperrliste](#url-syntax-for-the-tenant-allowblock-list) weiter unten in diesem Artikel.</span><span class="sxs-lookup"><span data-stu-id="eb056-139">For details about the syntax for URL entries, see the [URL syntax for the Tenant Allow/Block List](#url-syntax-for-the-tenant-allowblock-list) section later in this article.</span></span>

1. <span data-ttu-id="eb056-140">Wechseln Sie im Security & Compliance Center zu Richtlinien für die **Bedrohungsverwaltung** \>  \> **Mandanten zulassen/blockieren Listen**.</span><span class="sxs-lookup"><span data-stu-id="eb056-140">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="eb056-141">Überprüfen Sie auf der Seite Mandanten **zulassen/blockieren,** ob die Registerkarte **URLs** ausgewählt ist, und klicken Sie dann auf **Blockieren.**</span><span class="sxs-lookup"><span data-stu-id="eb056-141">On the **Tenant Allow/Block List** page, verify that the **URLs** tab is selected, and then click **Block**</span></span>

3. <span data-ttu-id="eb056-142">Konfigurieren Sie **im angezeigten** Flyout UrLs blockieren die folgenden Einstellungen:</span><span class="sxs-lookup"><span data-stu-id="eb056-142">In the **Block URLs** flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="eb056-143">**Zu blockierende URLs hinzufügen:** Geben Sie eine URL pro Zeile ein, bis zu maximal 20.</span><span class="sxs-lookup"><span data-stu-id="eb056-143">**Add URLs to block**: Enter one URL per line, up to a maximum of 20.</span></span>

   - <span data-ttu-id="eb056-144">**Nie ablaufen:** Gehen Sie wie folgt vor:</span><span class="sxs-lookup"><span data-stu-id="eb056-144">**Never expire**: Do one of the following steps:</span></span>

     - <span data-ttu-id="eb056-145">Überprüfen Sie, ob die Einstellung deaktiviert ist ( Umschalten ) und verwenden Sie das Feld Läuft auf, um das ![ ](../../media/scc-toggle-off.png) Ablaufdatum für die Einträge anzugeben. </span><span class="sxs-lookup"><span data-stu-id="eb056-145">Verify the setting is turned off (![Toggle off](../../media/scc-toggle-off.png)) and use the **Expires on** box to specify the expiration date for the entries.</span></span>

     <span data-ttu-id="eb056-146">oder</span><span class="sxs-lookup"><span data-stu-id="eb056-146">or</span></span>

     - <span data-ttu-id="eb056-147">Verschieben Sie den Umschalter nach rechts, um die Einträge so zu konfigurieren, dass sie nie ablaufen:</span><span class="sxs-lookup"><span data-stu-id="eb056-147">Move the toggle to the right to configure the entries to never expire:</span></span> ![Umschaltfläche ein](../../media/scc-toggle-on.png)<span data-ttu-id="eb056-149">.</span><span class="sxs-lookup"><span data-stu-id="eb056-149">.</span></span>

   - <span data-ttu-id="eb056-150">**Optionaler Hinweis:** Geben Sie beschreibenden Text für die Einträge ein.</span><span class="sxs-lookup"><span data-stu-id="eb056-150">**Optional note**: Enter descriptive text for the entries.</span></span>

4. <span data-ttu-id="eb056-151">Klicken Sie nach Abschluss des Vorgangs auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="eb056-151">When you're finished, click **Add**.</span></span>

## <a name="use-the-security--compliance-center-to-create-file-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="eb056-152">Verwenden des Security & Compliance Center zum Erstellen von Dateieinträgen in der Mandantenzu-/-sperrliste</span><span class="sxs-lookup"><span data-stu-id="eb056-152">Use the Security & Compliance Center to create file entries in the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="eb056-153">Wechseln Sie im Security & Compliance Center zu Richtlinien für die **Bedrohungsverwaltung** \>  \> **Mandanten zulassen/blockieren Listen**.</span><span class="sxs-lookup"><span data-stu-id="eb056-153">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="eb056-154">Wählen Sie auf der Seite Mandanten **zulassen/blockieren** die Registerkarte **Dateien** aus, und klicken Sie dann auf **Blockieren**.</span><span class="sxs-lookup"><span data-stu-id="eb056-154">On the **Tenant Allow/Block List** page, select **Files** tab, and then click **Block**.</span></span>

3. <span data-ttu-id="eb056-155">Konfigurieren Sie **im angezeigten Flyout** Dateien zum Blockieren von Dateien hinzufügen die folgenden Einstellungen:</span><span class="sxs-lookup"><span data-stu-id="eb056-155">In the **Add files to block** flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="eb056-156">**Hinzufügen von Dateihashes:** Geben Sie einen SHA256-Hashwert pro Zeile ein, bis zu maximal 20.</span><span class="sxs-lookup"><span data-stu-id="eb056-156">**Add file hashes**: Enter one SHA256 hash value per line, up to a maximum of 20.</span></span>

   - <span data-ttu-id="eb056-157">**Nie ablaufen:** Gehen Sie wie folgt vor:</span><span class="sxs-lookup"><span data-stu-id="eb056-157">**Never expire**: Do one of the following steps:</span></span>

     - <span data-ttu-id="eb056-158">Überprüfen Sie, ob die Einstellung deaktiviert ist ( Umschalten ) und verwenden Sie das Feld Läuft auf, um das ![ ](../../media/scc-toggle-off.png) Ablaufdatum für die Einträge anzugeben. </span><span class="sxs-lookup"><span data-stu-id="eb056-158">Verify the setting is turned off (![Toggle off](../../media/scc-toggle-off.png)) and use the **Expires on** box to specify the expiration date for the entries.</span></span>

     <span data-ttu-id="eb056-159">oder</span><span class="sxs-lookup"><span data-stu-id="eb056-159">or</span></span>

     - <span data-ttu-id="eb056-160">Verschieben Sie den Umschalter nach rechts, um die Einträge so zu konfigurieren, dass sie nie ablaufen:</span><span class="sxs-lookup"><span data-stu-id="eb056-160">Move the toggle to the right to configure the entries to never expire:</span></span> ![Umschaltfläche ein](../../media/scc-toggle-on.png)<span data-ttu-id="eb056-162">.</span><span class="sxs-lookup"><span data-stu-id="eb056-162">.</span></span>

   - <span data-ttu-id="eb056-163">**Optionaler Hinweis:** Geben Sie beschreibenden Text für die Einträge ein.</span><span class="sxs-lookup"><span data-stu-id="eb056-163">**Optional note**: Enter descriptive text for the entries.</span></span>

4. <span data-ttu-id="eb056-164">Klicken Sie nach Abschluss des Vorgangs auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="eb056-164">When you're finished, click **Add**.</span></span>

## <a name="use-the-security--compliance-center-to-view-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="eb056-165">Verwenden des Security & Compliance Center zum Anzeigen von Einträgen in der Mandantenzu-/-sperrliste</span><span class="sxs-lookup"><span data-stu-id="eb056-165">Use the Security & Compliance Center to view entries in the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="eb056-166">Wechseln Sie im Security & Compliance Center zu Richtlinien für die **Bedrohungsverwaltung** \>  \> **Mandanten zulassen/blockieren Listen**.</span><span class="sxs-lookup"><span data-stu-id="eb056-166">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="eb056-167">Wählen Sie **die Registerkarte URLs** oder die **Registerkarte Dateien** aus.</span><span class="sxs-lookup"><span data-stu-id="eb056-167">Select the **URLs** tab or the **Files** tab.</span></span>

<span data-ttu-id="eb056-168">Klicken Sie auf die folgenden Spaltenüberschriften, um sie in aufsteigender oder absteigender Reihenfolge zu sortieren:</span><span class="sxs-lookup"><span data-stu-id="eb056-168">Click on the following column headings to sort in ascending or descending order:</span></span>

- <span data-ttu-id="eb056-169">**Wert**: Die URL oder der Dateihash.</span><span class="sxs-lookup"><span data-stu-id="eb056-169">**Value**: The URL or the file hash.</span></span>
- <span data-ttu-id="eb056-170">**Datum der letzten Aktualisierung**</span><span class="sxs-lookup"><span data-stu-id="eb056-170">**Last updated date**</span></span>
- <span data-ttu-id="eb056-171">**Ablaufdatum**</span><span class="sxs-lookup"><span data-stu-id="eb056-171">**Expiration date**</span></span>
- <span data-ttu-id="eb056-172">**Hinweis**</span><span class="sxs-lookup"><span data-stu-id="eb056-172">**Note**</span></span>

<span data-ttu-id="eb056-173">Klicken **Sie auf Suchen,** geben Sie einen Wert ganz oder teilweise ein, und drücken Sie die EINGABETASTE, um einen bestimmten Wert zu finden.</span><span class="sxs-lookup"><span data-stu-id="eb056-173">Click **Search**, enter all or part of a value, and then press ENTER to find a specific value.</span></span> <span data-ttu-id="eb056-174">Wenn Sie fertig sind, klicken Sie auf **Suche löschen Suchsymbol** ![ löschen ](../../media/b6512677-5e7b-42b0-a8a3-3be1d7fa23ee.gif) .</span><span class="sxs-lookup"><span data-stu-id="eb056-174">When you're finished, click **Clear search** ![Clear search icon](../../media/b6512677-5e7b-42b0-a8a3-3be1d7fa23ee.gif).</span></span>

<span data-ttu-id="eb056-175">Klicken Sie **auf Filter**.</span><span class="sxs-lookup"><span data-stu-id="eb056-175">Click **Filter**.</span></span> <span data-ttu-id="eb056-176">Konfigurieren Sie **im angezeigten** Flyout Filter eine der folgenden Einstellungen:</span><span class="sxs-lookup"><span data-stu-id="eb056-176">In the **Filter** flyout that appears, configure any of the following settings:</span></span>

- <span data-ttu-id="eb056-177">**Nie ablaufen:** Wählen Sie aus: ![ Umschalten ](../../media/scc-toggle-off.png) oder Aktivieren: ![ Umschalten auf ](../../media/scc-toggle-on.png) .</span><span class="sxs-lookup"><span data-stu-id="eb056-177">**Never expire**: Select off: ![Toggle off](../../media/scc-toggle-off.png) or on: ![Toggle on](../../media/scc-toggle-on.png).</span></span>

- <span data-ttu-id="eb056-178">**Last updated**: Select a start date (**From**), an end date (**To**) or both.</span><span class="sxs-lookup"><span data-stu-id="eb056-178">**Last updated**: Select a start date (**From**), an end date (**To**) or both.</span></span>

- <span data-ttu-id="eb056-179">**Ablaufdatum**: Wählen Sie ein Startdatum (**Von**), ein Enddatum (**An**) oder beides aus.</span><span class="sxs-lookup"><span data-stu-id="eb056-179">**Expiration date**: Select a start date (**From**), an end date (**To**) or both.</span></span>

<span data-ttu-id="eb056-180">Klicken Sie nach Abschluss des Abschlusses auf **Übernehmen**.</span><span class="sxs-lookup"><span data-stu-id="eb056-180">When you're finished, click **Apply**.</span></span>

<span data-ttu-id="eb056-181">Klicken Sie zum Löschen vorhandener Filter auf **Filter,** und klicken Sie im angezeigten **Flyout** Filter **auf Filter löschen.**</span><span class="sxs-lookup"><span data-stu-id="eb056-181">To clear existing filters, click **Filter**, and in the **Filter** flyout that appears, click **Clear filters**.</span></span>

## <a name="use-the-security--compliance-center-to-modify-block-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="eb056-182">Verwenden des Security & Compliance Center zum Ändern von Blockeinträgen in der Mandantenzu-/-sperrliste</span><span class="sxs-lookup"><span data-stu-id="eb056-182">Use the Security & Compliance Center to modify block entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="eb056-183">Sie können die vorhandenen blockierten URL- oder Dateiwerte in einem Eintrag nicht ändern.</span><span class="sxs-lookup"><span data-stu-id="eb056-183">You can't modify the existing blocked URL or file values within an entry.</span></span> <span data-ttu-id="eb056-184">Um diese Werte zu ändern, müssen Sie den Eintrag löschen und neu erstellen.</span><span class="sxs-lookup"><span data-stu-id="eb056-184">To modify these values, you need to delete and recreate the entry.</span></span>

1. <span data-ttu-id="eb056-185">Wechseln Sie im Security & Compliance Center zu Richtlinien für die **Bedrohungsverwaltung** \>  \> **Mandanten zulassen/blockieren Listen**.</span><span class="sxs-lookup"><span data-stu-id="eb056-185">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="eb056-186">Wählen Sie **die Registerkarte URLs** oder die **Registerkarte Dateien** aus.</span><span class="sxs-lookup"><span data-stu-id="eb056-186">Select the **URLs** tab or the **Files** tab.</span></span>

3. <span data-ttu-id="eb056-187">Wählen Sie den Blockeintrag aus, den Sie ändern möchten, und klicken Sie dann auf **Bearbeiten** ![ (Symbol). ](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png)</span><span class="sxs-lookup"><span data-stu-id="eb056-187">Select the block entry that you want to modify, and then click **Edit** ![Edit icon](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png).</span></span>

4. <span data-ttu-id="eb056-188">Konfigurieren Sie im angezeigten Flyout die folgenden Einstellungen:</span><span class="sxs-lookup"><span data-stu-id="eb056-188">In the flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="eb056-189">**Nie ablaufen:** Gehen Sie wie folgt vor:</span><span class="sxs-lookup"><span data-stu-id="eb056-189">**Never expire**: Do one of the following steps:</span></span>

     - <span data-ttu-id="eb056-190">Überprüfen Sie, ob die Einstellung deaktiviert ist ( Umschalten ) und verwenden Sie das Feld Läuft auf, um das Ablaufdatum für ![ ](../../media/scc-toggle-off.png) den Eintrag anzugeben. </span><span class="sxs-lookup"><span data-stu-id="eb056-190">Verify the setting is turned off (![Toggle off](../../media/scc-toggle-off.png)) and use the **Expires on** box to specify the expiration date for the entry.</span></span>

     <span data-ttu-id="eb056-191">oder</span><span class="sxs-lookup"><span data-stu-id="eb056-191">or</span></span>

     - <span data-ttu-id="eb056-192">Verschieben Sie den Umschalter nach rechts, um den Eintrag so zu konfigurieren, dass er nie abläuft:</span><span class="sxs-lookup"><span data-stu-id="eb056-192">Move the toggle to the right to configure the entry to never expire:</span></span> ![Umschaltfläche ein](../../media/scc-toggle-on.png)<span data-ttu-id="eb056-194">.</span><span class="sxs-lookup"><span data-stu-id="eb056-194">.</span></span>

   - <span data-ttu-id="eb056-195">**Optionaler Hinweis:** Geben Sie beschreibenden Text für den Eintrag ein.</span><span class="sxs-lookup"><span data-stu-id="eb056-195">**Optional note**: Enter descriptive text for the entry.</span></span>

5. <span data-ttu-id="eb056-196">Klicken Sie nach Abschluss des Vorgangs auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="eb056-196">When you're finished, click **Save**.</span></span>

## <a name="use-the-security--compliance-center-to-remove-block-entries-from-the-tenant-allowblock-list"></a><span data-ttu-id="eb056-197">Verwenden des Security & Compliance Center zum Entfernen von Sperreinträgen aus der Mandantenzu-/-sperrliste</span><span class="sxs-lookup"><span data-stu-id="eb056-197">Use the Security & Compliance Center to remove block entries from the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="eb056-198">Wechseln Sie im Security & Compliance Center zu Richtlinien für die **Bedrohungsverwaltung** \>  \> **Mandanten zulassen/blockieren Listen**.</span><span class="sxs-lookup"><span data-stu-id="eb056-198">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="eb056-199">Wählen Sie **die Registerkarte URLs** oder die **Registerkarte Dateien** aus.</span><span class="sxs-lookup"><span data-stu-id="eb056-199">Select the **URLs** tab or the **Files** tab.</span></span>

3. <span data-ttu-id="eb056-200">Wählen Sie den Blockeintrag aus, den Sie entfernen möchten, und klicken Sie dann auf **Löschen** ![ Löschen ](../../media/87565fbb-5147-4f22-9ed7-1c18ce664392.png) (Symbol).</span><span class="sxs-lookup"><span data-stu-id="eb056-200">Select the block entry that you want to remove, and then click **Delete** ![Delete icon](../../media/87565fbb-5147-4f22-9ed7-1c18ce664392.png).</span></span>

4. <span data-ttu-id="eb056-201">Klicken Sie im angezeigten Warnungsdialogfeld auf **Löschen**.</span><span class="sxs-lookup"><span data-stu-id="eb056-201">In the warning dialog that appears, click **Delete**.</span></span>

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-the-tenant-allowblock-list"></a><span data-ttu-id="eb056-202">Verwenden von Exchange Online PowerShell oder eigenständiger EOP PowerShell zum Konfigurieren der Mandanten zulassen/Blockieren-Liste</span><span class="sxs-lookup"><span data-stu-id="eb056-202">Use Exchange Online PowerShell or standalone EOP PowerShell to configure the Tenant Allow/Block List</span></span>

### <a name="use-powershell-to-add-block-entries-to-the-tenant-allowblock-list"></a><span data-ttu-id="eb056-203">Verwenden von PowerShell zum Hinzufügen von Blockeinträgen zur Mandantenzu-/Sperrliste</span><span class="sxs-lookup"><span data-stu-id="eb056-203">Use PowerShell to add block entries to the Tenant Allow/Block List</span></span>

<span data-ttu-id="eb056-204">Verwenden Sie die folgende Syntax, um Blockeinträge in der Mandantenzu-/Sperrliste hinzuzufügen:</span><span class="sxs-lookup"><span data-stu-id="eb056-204">To add block entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
New-TenantAllowBlockListItems -ListType <Url | FileHash> -Block -Entries <String[]> [-ExpirationDate <DateTime>] [-NoExpiration] [-Notes <String>]
```

<span data-ttu-id="eb056-205">In diesem Beispiel wird ein Block-URL-Eintrag für contoso.com und alle Unterdomänen hinzugefügt (z. B. contoso.com, www.contoso.com und xyz.abc.contoso.com).</span><span class="sxs-lookup"><span data-stu-id="eb056-205">This example adds a block URL entry for contoso.com and all subdomains (for example, contoso.com, www.contoso.com, and xyz.abc.contoso.com).</span></span> <span data-ttu-id="eb056-206">Da wir die Parameter ExpirationDate oder NoExpiration nicht verwendet haben, läuft der Eintrag nach 30 Tagen ab.</span><span class="sxs-lookup"><span data-stu-id="eb056-206">Because we didn't use the ExpirationDate or NoExpiration parameters, the entry expires after 30 days.</span></span>

```powershell
New-TenantAllowBlockListItem -ListType Url -Block -Entries ~contoso.com
```

<span data-ttu-id="eb056-207">In diesem Beispiel wird ein Blockdateieintrag für die angegebenen Dateien, die nie abläuft, hinzufügt.</span><span class="sxs-lookup"><span data-stu-id="eb056-207">This example adds a block file entry for the specified files that never expires.</span></span>

```powershell
New-TenantAllowBlockListItem -ListType FileHash -Block -Entries "768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3","2c0a35409ff0873cfa28b70b8224e9aca2362241c1f0ed6f622fef8d4722fd9a" -NoExpiration
```

<span data-ttu-id="eb056-208">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [New-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/new-tenantallowblocklistitems).</span><span class="sxs-lookup"><span data-stu-id="eb056-208">For detailed syntax and parameter information, see [New-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/new-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-view-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="eb056-209">Verwenden von PowerShell zum Anzeigen von Einträgen in der Mandanten-Zulassen-/Sperrliste</span><span class="sxs-lookup"><span data-stu-id="eb056-209">Use PowerShell to view entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="eb056-210">Verwenden Sie die folgende Syntax, um Einträge in der Mandantenzu-/Sperrliste anzeigen zu können:</span><span class="sxs-lookup"><span data-stu-id="eb056-210">To view entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType <Url | FileHash> [-Entry <URLValue | FileHashValue>] [-Block] [-ExpirationDate <DateTime>] [-NoExpiration]
```

<span data-ttu-id="eb056-211">In diesem Beispiel werden alle blockierten URLs zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="eb056-211">This example returns all blocked URLs.</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType Url -Block
```

<span data-ttu-id="eb056-212">In diesem Beispiel werden Informationen für den angegebenen Dateihashwert zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="eb056-212">This example returns information for the specified file hash value.</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType FileHash -Entry "9f86d081884c7d659a2feaa0c55ad015a3bf4f1b2b0b822cd15d6c15b0f00a08"
```

<span data-ttu-id="eb056-213">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Get-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/get-tenantallowblocklistitems).</span><span class="sxs-lookup"><span data-stu-id="eb056-213">For detailed syntax and parameter information, see [Get-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/get-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-modify-block-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="eb056-214">Verwenden von PowerShell zum Ändern von Blockeinträgen in der Mandantenzu-/-sperrliste</span><span class="sxs-lookup"><span data-stu-id="eb056-214">Use PowerShell to modify block entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="eb056-215">Sie können die vorhandenen URL- oder Dateiwerte in einem Blockeintrag nicht ändern.</span><span class="sxs-lookup"><span data-stu-id="eb056-215">You can't modify the existing URL or file values within a block entry.</span></span> <span data-ttu-id="eb056-216">Um diese Werte zu ändern, müssen Sie den Eintrag löschen und neu erstellen.</span><span class="sxs-lookup"><span data-stu-id="eb056-216">To modify these values, you need to delete and recreate the entry.</span></span>

<span data-ttu-id="eb056-217">Verwenden Sie die folgende Syntax, um Blockeinträge in der Mandanten zulassen/blockieren-Liste zu ändern:</span><span class="sxs-lookup"><span data-stu-id="eb056-217">To modify block entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Set-TenantAllowBlockListItems -ListType <Url | FileHash> -Ids <"Id1","Id2",..."IdN"> [-Block] [-ExpirationDate <DateTime>] [-NoExpiration] [-Notes <String>]
```

<span data-ttu-id="eb056-218">In diesem Beispiel wird das Ablaufdatum des angegebenen Blockeintrags geändert.</span><span class="sxs-lookup"><span data-stu-id="eb056-218">This example changes the expiration date of the specified block entry.</span></span>

```powershell
Set-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSRAAAA" -ExpirationDate (Get-Date "5/30/2020 9:30 AM").ToUniversalTime()
```

<span data-ttu-id="eb056-219">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Set-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/set-tenantallowblocklistitems).</span><span class="sxs-lookup"><span data-stu-id="eb056-219">For detailed syntax and parameter information, see [Set-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/set-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-remove-block-entries-from-the-tenant-allowblock-list"></a><span data-ttu-id="eb056-220">Verwenden von PowerShell zum Entfernen von Sperreinträgen aus der Mandanten-Zulassen-/Sperrliste</span><span class="sxs-lookup"><span data-stu-id="eb056-220">Use PowerShell to remove block entries from the Tenant Allow/Block List</span></span>

<span data-ttu-id="eb056-221">Verwenden Sie die folgende Syntax, um Blockeinträge aus der Mandanten zulassen/blockieren-Liste zu entfernen:</span><span class="sxs-lookup"><span data-stu-id="eb056-221">To remove block entries from the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Remove-TenantAllowBlockListItems -ListType <Url | FileHash> -Ids <"Id1","Id2",..."IdN">
```

<span data-ttu-id="eb056-222">In diesem Beispiel wird der angegebene Block-URL-Eintrag aus der Mandanten-Allow/Block List entfernt.</span><span class="sxs-lookup"><span data-stu-id="eb056-222">This example removes the specified block URL entry from the Tenant Allow/Block List.</span></span>

```powershell
Remove-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSPAAAA0"
```

<span data-ttu-id="eb056-223">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Remove-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/remove-tenantallowblocklistitems).</span><span class="sxs-lookup"><span data-stu-id="eb056-223">For detailed syntax and parameter information, see [Remove-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/remove-tenantallowblocklistitems).</span></span>

## <a name="url-syntax-for-the-tenant-allowblock-list"></a><span data-ttu-id="eb056-224">#A0 für die Mandanten-Allow/Block List</span><span class="sxs-lookup"><span data-stu-id="eb056-224">URL syntax for the Tenant Allow/Block List</span></span>

- <span data-ttu-id="eb056-225">IP4v- und IPv6-Adressen sind zulässig, TCP/UDP-Ports jedoch nicht.</span><span class="sxs-lookup"><span data-stu-id="eb056-225">IP4v and IPv6 addresses are allowed, but TCP/UDP ports are not.</span></span>

- <span data-ttu-id="eb056-226">Dateinamenerweiterungen sind nicht zulässig (z. B. test.pdf).</span><span class="sxs-lookup"><span data-stu-id="eb056-226">Filename extensions are not allowed (for example, test.pdf).</span></span>

- <span data-ttu-id="eb056-227">Unicode wird nicht unterstützt, Punycode jedoch.</span><span class="sxs-lookup"><span data-stu-id="eb056-227">Unicode is not supported, but Punycode is.</span></span>

- <span data-ttu-id="eb056-228">Hostnamen sind zulässig, wenn alle folgenden Anweisungen zutreffen:</span><span class="sxs-lookup"><span data-stu-id="eb056-228">Hostnames are allowed if all of the following statements are true:</span></span>
  - <span data-ttu-id="eb056-229">Der Hostname enthält einen Zeitraum.</span><span class="sxs-lookup"><span data-stu-id="eb056-229">The hostname contains a period.</span></span>
  - <span data-ttu-id="eb056-230">Es gibt mindestens ein Zeichen links vom Zeitraum.</span><span class="sxs-lookup"><span data-stu-id="eb056-230">There is at least one character to the left of the period.</span></span>
  - <span data-ttu-id="eb056-231">Rechts neben dem Zeitraum befinden sich mindestens zwei Zeichen.</span><span class="sxs-lookup"><span data-stu-id="eb056-231">There are at least two characters to the right of the period.</span></span>

  <span data-ttu-id="eb056-232">Beispielsweise ist `t.co` zulässig oder nicht `.com` `contoso.` zulässig.</span><span class="sxs-lookup"><span data-stu-id="eb056-232">For example, `t.co` is allowed; `.com` or `contoso.` are not allowed.</span></span>

- <span data-ttu-id="eb056-233">Unterpfade werden nicht impliziert.</span><span class="sxs-lookup"><span data-stu-id="eb056-233">Subpaths are not implied.</span></span>

  <span data-ttu-id="eb056-234">Enthält z. `contoso.com` B. nicht `contoso.com/a` .</span><span class="sxs-lookup"><span data-stu-id="eb056-234">For example, `contoso.com` does not include `contoso.com/a`.</span></span>

- <span data-ttu-id="eb056-235">Platzhalter (\*) sind in den folgenden Szenarien zulässig:</span><span class="sxs-lookup"><span data-stu-id="eb056-235">Wildcards (\*) are allowed in the following scenarios:</span></span>

  - <span data-ttu-id="eb056-236">Auf einen linken Platzhalter muss ein Zeitraum folgen, um eine Unterdomäne anzugeben.</span><span class="sxs-lookup"><span data-stu-id="eb056-236">A left wildcard must be followed by a period to specify a subdomain.</span></span>

    <span data-ttu-id="eb056-237">Ist beispielsweise `*.contoso.com` zulässig; `*contoso.com` ist nicht zulässig.</span><span class="sxs-lookup"><span data-stu-id="eb056-237">For example, `*.contoso.com` is allowed; `*contoso.com` is not allowed.</span></span>

  - <span data-ttu-id="eb056-238">Ein rechter Platzhalter muss einem Schrägstrich (/) folgen, um einen Pfad anzugeben.</span><span class="sxs-lookup"><span data-stu-id="eb056-238">A right wildcard must follow a forward slash (/) to specify a path.</span></span>

    <span data-ttu-id="eb056-239">Beispielsweise ist `contoso.com/*` zulässig oder nicht `contoso.com*` `contoso.com/ab*` zulässig.</span><span class="sxs-lookup"><span data-stu-id="eb056-239">For example, `contoso.com/*` is allowed; `contoso.com*` or `contoso.com/ab*` are not allowed.</span></span>

  - <span data-ttu-id="eb056-240">Alle Unterpfade werden nicht durch einen rechten Platzhalter impliziert.</span><span class="sxs-lookup"><span data-stu-id="eb056-240">All subpaths are not implied by a right wildcard.</span></span>

    <span data-ttu-id="eb056-241">Enthält z. `contoso.com/*` B. nicht `contoso.com/a` .</span><span class="sxs-lookup"><span data-stu-id="eb056-241">For example, `contoso.com/*` does not include `contoso.com/a`.</span></span>

  - <span data-ttu-id="eb056-242">`*.com*` ist ungültig (keine auflösbare Domäne, und der rechte Platzhalter folgt keinem Schrägstrich).</span><span class="sxs-lookup"><span data-stu-id="eb056-242">`*.com*` is invalid (not a resolvable domain and the right wildcard does not follow a forward slash).</span></span>

  - <span data-ttu-id="eb056-243">Platzhalter sind in IP-Adressen nicht zulässig.</span><span class="sxs-lookup"><span data-stu-id="eb056-243">Wildcards are not allowed in IP addresses.</span></span>

- <span data-ttu-id="eb056-244">Das Tildezeichen (~) ist in den folgenden Szenarien verfügbar:</span><span class="sxs-lookup"><span data-stu-id="eb056-244">The tilde (~) character is available in the following scenarios:</span></span>

  - <span data-ttu-id="eb056-245">Eine linke Tilde impliziert eine Domäne und alle Unterdomänen.</span><span class="sxs-lookup"><span data-stu-id="eb056-245">A left tilde implies a domain and all subdomains.</span></span>

    <span data-ttu-id="eb056-246">Enthält `~contoso.com` z. `contoso.com` B. und `*.contoso.com` .</span><span class="sxs-lookup"><span data-stu-id="eb056-246">For example `~contoso.com` includes `contoso.com` and `*.contoso.com`.</span></span>

- <span data-ttu-id="eb056-247">URL-Einträge, die Protokolle (z. B. , oder ) enthalten, werden fehlschlagen, da `http://` URL-Einträge für alle Protokolle `https://` `ftp://` gelten.</span><span class="sxs-lookup"><span data-stu-id="eb056-247">URL entries that contain protocols (for example, `http://`, `https://`, or `ftp://`) will fail, because URL entries apply to all protocols.</span></span>

- <span data-ttu-id="eb056-248">Ein Benutzername oder Kennwort wird nicht unterstützt oder ist nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="eb056-248">A username or password aren't supported or required.</span></span>

- <span data-ttu-id="eb056-249">Anführungszeichen (' oder ") sind ungültige Zeichen.</span><span class="sxs-lookup"><span data-stu-id="eb056-249">Quotes (' or ") are invalid characters.</span></span>

- <span data-ttu-id="eb056-250">Eine URL sollte nach Möglichkeit alle Umleitungen enthalten.</span><span class="sxs-lookup"><span data-stu-id="eb056-250">A URL should include all redirects where possible.</span></span>

### <a name="url-entry-scenarios"></a><span data-ttu-id="eb056-251">Szenarien für den URL-Eintrag</span><span class="sxs-lookup"><span data-stu-id="eb056-251">URL entry scenarios</span></span>

<span data-ttu-id="eb056-252">Gültige URL-Einträge und deren Ergebnisse werden in den folgenden Abschnitten beschrieben.</span><span class="sxs-lookup"><span data-stu-id="eb056-252">Valid URL entries and their results are described in the following sections.</span></span>

#### <a name="scenario-no-wildcards"></a><span data-ttu-id="eb056-253">Szenario: Keine Platzhalter</span><span class="sxs-lookup"><span data-stu-id="eb056-253">Scenario: No wildcards</span></span>

<span data-ttu-id="eb056-254">**Eintrag**: `contoso.com`</span><span class="sxs-lookup"><span data-stu-id="eb056-254">**Entry**: `contoso.com`</span></span>

- <span data-ttu-id="eb056-255">**Übereinstimmung zulassen**: contoso.com</span><span class="sxs-lookup"><span data-stu-id="eb056-255">**Allow match**: contoso.com</span></span>

- <span data-ttu-id="eb056-256">**Nicht übereinstimmend zulassen:**</span><span class="sxs-lookup"><span data-stu-id="eb056-256">**Allow not matched**:</span></span>

  - <span data-ttu-id="eb056-257">abc-contoso.com</span><span class="sxs-lookup"><span data-stu-id="eb056-257">abc-contoso.com</span></span>
  - <span data-ttu-id="eb056-258">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="eb056-258">contoso.com/a</span></span>
  - <span data-ttu-id="eb056-259">payroll.contoso.com</span><span class="sxs-lookup"><span data-stu-id="eb056-259">payroll.contoso.com</span></span>
  - <span data-ttu-id="eb056-260">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="eb056-260">test.com/contoso.com</span></span>
  - <span data-ttu-id="eb056-261">test.com/q=contoso.com</span><span class="sxs-lookup"><span data-stu-id="eb056-261">test.com/q=contoso.com</span></span>
  - <span data-ttu-id="eb056-262">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="eb056-262">www.contoso.com</span></span>
  - <span data-ttu-id="eb056-263">www.contoso.com/q=a@contoso.com</span><span class="sxs-lookup"><span data-stu-id="eb056-263">www.contoso.com/q=a@contoso.com</span></span>

- <span data-ttu-id="eb056-264">**Übereinstimmung blockieren**:</span><span class="sxs-lookup"><span data-stu-id="eb056-264">**Block match**:</span></span>

  - <span data-ttu-id="eb056-265">contoso.com</span><span class="sxs-lookup"><span data-stu-id="eb056-265">contoso.com</span></span>
  - <span data-ttu-id="eb056-266">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="eb056-266">contoso.com/a</span></span>
  - <span data-ttu-id="eb056-267">payroll.contoso.com</span><span class="sxs-lookup"><span data-stu-id="eb056-267">payroll.contoso.com</span></span>
  - <span data-ttu-id="eb056-268">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="eb056-268">test.com/contoso.com</span></span>
  - <span data-ttu-id="eb056-269">test.com/q=contoso.com</span><span class="sxs-lookup"><span data-stu-id="eb056-269">test.com/q=contoso.com</span></span>
  - <span data-ttu-id="eb056-270">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="eb056-270">www.contoso.com</span></span>
  - <span data-ttu-id="eb056-271">www.contoso.com/q=a@contoso.com</span><span class="sxs-lookup"><span data-stu-id="eb056-271">www.contoso.com/q=a@contoso.com</span></span>

- <span data-ttu-id="eb056-272">**Block nicht übereinstimmend**: abc-contoso.com</span><span class="sxs-lookup"><span data-stu-id="eb056-272">**Block not matched**: abc-contoso.com</span></span>

#### <a name="scenario-left-wildcard-subdomain"></a><span data-ttu-id="eb056-273">Szenario: Linker Platzhalter (Unterdomäne)</span><span class="sxs-lookup"><span data-stu-id="eb056-273">Scenario: Left wildcard (subdomain)</span></span>

<span data-ttu-id="eb056-274">**Eintrag**: `*.contoso.com`</span><span class="sxs-lookup"><span data-stu-id="eb056-274">**Entry**: `*.contoso.com`</span></span>

- <span data-ttu-id="eb056-275">**Übereinstimmung zulassen** und **Übereinstimmung blockieren**:</span><span class="sxs-lookup"><span data-stu-id="eb056-275">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="eb056-276">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="eb056-276">www.contoso.com</span></span>
  - <span data-ttu-id="eb056-277">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="eb056-277">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="eb056-278">**Allow not matched** and **Block not matched**:</span><span class="sxs-lookup"><span data-stu-id="eb056-278">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="eb056-279">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="eb056-279">123contoso.com</span></span>
  - <span data-ttu-id="eb056-280">contoso.com</span><span class="sxs-lookup"><span data-stu-id="eb056-280">contoso.com</span></span>
  - <span data-ttu-id="eb056-281">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="eb056-281">test.com/contoso.com</span></span>
  - <span data-ttu-id="eb056-282">www.contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="eb056-282">www.contoso.com/abc</span></span>

#### <a name="scenario-right-wildcard-at-top-of-path"></a><span data-ttu-id="eb056-283">Szenario: Rechter Platzhalter am oberen Rand des Pfads</span><span class="sxs-lookup"><span data-stu-id="eb056-283">Scenario: Right wildcard at top of path</span></span>

<span data-ttu-id="eb056-284">**Eintrag**: `contoso.com/a/*`</span><span class="sxs-lookup"><span data-stu-id="eb056-284">**Entry**: `contoso.com/a/*`</span></span>

- <span data-ttu-id="eb056-285">**Übereinstimmung zulassen** und **Übereinstimmung blockieren**:</span><span class="sxs-lookup"><span data-stu-id="eb056-285">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="eb056-286">contoso.com/a/b</span><span class="sxs-lookup"><span data-stu-id="eb056-286">contoso.com/a/b</span></span>
  - <span data-ttu-id="eb056-287">contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="eb056-287">contoso.com/a/b/c</span></span>
  - <span data-ttu-id="eb056-288">contoso.com/a/?q=joe@t.com</span><span class="sxs-lookup"><span data-stu-id="eb056-288">contoso.com/a/?q=joe@t.com</span></span>

- <span data-ttu-id="eb056-289">**Allow not matched** and **Block not matched**:</span><span class="sxs-lookup"><span data-stu-id="eb056-289">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="eb056-290">contoso.com</span><span class="sxs-lookup"><span data-stu-id="eb056-290">contoso.com</span></span>
  - <span data-ttu-id="eb056-291">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="eb056-291">contoso.com/a</span></span>
  - <span data-ttu-id="eb056-292">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="eb056-292">www.contoso.com</span></span>
  - <span data-ttu-id="eb056-293">www.contoso.com/q=a@contoso.com</span><span class="sxs-lookup"><span data-stu-id="eb056-293">www.contoso.com/q=a@contoso.com</span></span>

#### <a name="scenario-left-tilde"></a><span data-ttu-id="eb056-294">Szenario: Left tilde</span><span class="sxs-lookup"><span data-stu-id="eb056-294">Scenario: Left tilde</span></span>

<span data-ttu-id="eb056-295">**Eintrag**: `~contoso.com`</span><span class="sxs-lookup"><span data-stu-id="eb056-295">**Entry**: `~contoso.com`</span></span>

- <span data-ttu-id="eb056-296">**Übereinstimmung zulassen** und **Übereinstimmung blockieren**:</span><span class="sxs-lookup"><span data-stu-id="eb056-296">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="eb056-297">contoso.com</span><span class="sxs-lookup"><span data-stu-id="eb056-297">contoso.com</span></span>
  - <span data-ttu-id="eb056-298">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="eb056-298">www.contoso.com</span></span>
  - <span data-ttu-id="eb056-299">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="eb056-299">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="eb056-300">**Allow not matched** and **Block not matched**:</span><span class="sxs-lookup"><span data-stu-id="eb056-300">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="eb056-301">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="eb056-301">123contoso.com</span></span>
  - <span data-ttu-id="eb056-302">contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="eb056-302">contoso.com/abc</span></span>
  - <span data-ttu-id="eb056-303">www.contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="eb056-303">www.contoso.com/abc</span></span>

#### <a name="scenario-right-wildcard-suffix"></a><span data-ttu-id="eb056-304">Szenario: Rechtes Platzhaltersuffix</span><span class="sxs-lookup"><span data-stu-id="eb056-304">Scenario: Right wildcard suffix</span></span>

<span data-ttu-id="eb056-305">**Eintrag**: `contoso.com/*`</span><span class="sxs-lookup"><span data-stu-id="eb056-305">**Entry**: `contoso.com/*`</span></span>

- <span data-ttu-id="eb056-306">**Übereinstimmung zulassen** und **Übereinstimmung blockieren**:</span><span class="sxs-lookup"><span data-stu-id="eb056-306">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="eb056-307">contoso.com/?q=whatever@fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="eb056-307">contoso.com/?q=whatever@fabrikam.com</span></span>
  - <span data-ttu-id="eb056-308">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="eb056-308">contoso.com/a</span></span>
  - <span data-ttu-id="eb056-309">contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="eb056-309">contoso.com/a/b/c</span></span>
  - <span data-ttu-id="eb056-310">contoso.com/ab</span><span class="sxs-lookup"><span data-stu-id="eb056-310">contoso.com/ab</span></span>
  - <span data-ttu-id="eb056-311">contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="eb056-311">contoso.com/b</span></span>
  - <span data-ttu-id="eb056-312">contoso.com/b/a/c</span><span class="sxs-lookup"><span data-stu-id="eb056-312">contoso.com/b/a/c</span></span>
  - <span data-ttu-id="eb056-313">contoso.com/ba</span><span class="sxs-lookup"><span data-stu-id="eb056-313">contoso.com/ba</span></span>

- <span data-ttu-id="eb056-314">**Nicht übereinstimmend zulassen und** **Block nicht** übereinstimmen: contoso.com</span><span class="sxs-lookup"><span data-stu-id="eb056-314">**Allow not matched** and **Block not matched**: contoso.com</span></span>

#### <a name="scenario-left-wildcard-subdomain-and-right-wildcard-suffix"></a><span data-ttu-id="eb056-315">Szenario: Linke Platzhalterunterdomäne und rechtes Platzhaltersuffix</span><span class="sxs-lookup"><span data-stu-id="eb056-315">Scenario: Left wildcard subdomain and right wildcard suffix</span></span>

<span data-ttu-id="eb056-316">**Eintrag**: `*.contoso.com/*`</span><span class="sxs-lookup"><span data-stu-id="eb056-316">**Entry**: `*.contoso.com/*`</span></span>

- <span data-ttu-id="eb056-317">**Übereinstimmung zulassen** und **Übereinstimmung blockieren**:</span><span class="sxs-lookup"><span data-stu-id="eb056-317">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="eb056-318">abc.contoso.com/ab</span><span class="sxs-lookup"><span data-stu-id="eb056-318">abc.contoso.com/ab</span></span>
  - <span data-ttu-id="eb056-319">abc.xyz.contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="eb056-319">abc.xyz.contoso.com/a/b/c</span></span>
  - <span data-ttu-id="eb056-320">www.contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="eb056-320">www.contoso.com/a</span></span>
  - <span data-ttu-id="eb056-321">www.contoso.com/b/a/c</span><span class="sxs-lookup"><span data-stu-id="eb056-321">www.contoso.com/b/a/c</span></span>
  - <span data-ttu-id="eb056-322">xyz.contoso.com/ba</span><span class="sxs-lookup"><span data-stu-id="eb056-322">xyz.contoso.com/ba</span></span>

- <span data-ttu-id="eb056-323">**Nicht übereinstimmend zulassen und** **Block nicht** übereinstimmen : contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="eb056-323">**Allow not matched** and **Block not matched**: contoso.com/b</span></span>

#### <a name="scenario-left-and-right-tilde"></a><span data-ttu-id="eb056-324">Szenario: Linker und rechter Tilde</span><span class="sxs-lookup"><span data-stu-id="eb056-324">Scenario: Left and right tilde</span></span>

<span data-ttu-id="eb056-325">**Eintrag**: `~contoso.com~`</span><span class="sxs-lookup"><span data-stu-id="eb056-325">**Entry**: `~contoso.com~`</span></span>

- <span data-ttu-id="eb056-326">**Übereinstimmung zulassen** und **Übereinstimmung blockieren**:</span><span class="sxs-lookup"><span data-stu-id="eb056-326">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="eb056-327">contoso.com</span><span class="sxs-lookup"><span data-stu-id="eb056-327">contoso.com</span></span>
  - <span data-ttu-id="eb056-328">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="eb056-328">contoso.com/a</span></span>
  - <span data-ttu-id="eb056-329">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="eb056-329">www.contoso.com</span></span>
  - <span data-ttu-id="eb056-330">www.contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="eb056-330">www.contoso.com/b</span></span>
  - <span data-ttu-id="eb056-331">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="eb056-331">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="eb056-332">**Allow not matched** and **Block not matched**:</span><span class="sxs-lookup"><span data-stu-id="eb056-332">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="eb056-333">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="eb056-333">123contoso.com</span></span>
  - <span data-ttu-id="eb056-334">contoso.org</span><span class="sxs-lookup"><span data-stu-id="eb056-334">contoso.org</span></span>

#### <a name="scenario-ip-address"></a><span data-ttu-id="eb056-335">Szenario: IP-Adresse</span><span class="sxs-lookup"><span data-stu-id="eb056-335">Scenario: IP address</span></span>

<span data-ttu-id="eb056-336">**Eintrag**: `1.2.3.4`</span><span class="sxs-lookup"><span data-stu-id="eb056-336">**Entry**: `1.2.3.4`</span></span>

- <span data-ttu-id="eb056-337">**Übereinstimmung zulassen** und **Übereinstimmung blockieren**: 1.2.3.4</span><span class="sxs-lookup"><span data-stu-id="eb056-337">**Allow match** and **Block match**: 1.2.3.4</span></span>

- <span data-ttu-id="eb056-338">**Allow not matched** and **Block not matched**:</span><span class="sxs-lookup"><span data-stu-id="eb056-338">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="eb056-339">1.2.3.4/a</span><span class="sxs-lookup"><span data-stu-id="eb056-339">1.2.3.4/a</span></span>
  - <span data-ttu-id="eb056-340">11.2.3.4/a</span><span class="sxs-lookup"><span data-stu-id="eb056-340">11.2.3.4/a</span></span>

#### <a name="ip-address-with-right-wildcard"></a><span data-ttu-id="eb056-341">IP-Adresse mit rechtem Platzhalter</span><span class="sxs-lookup"><span data-stu-id="eb056-341">IP address with right wildcard</span></span>

<span data-ttu-id="eb056-342">**Eintrag**: `1.2.3.4/*`</span><span class="sxs-lookup"><span data-stu-id="eb056-342">**Entry**: `1.2.3.4/*`</span></span>

- <span data-ttu-id="eb056-343">**Übereinstimmung zulassen** und **Übereinstimmung blockieren**:</span><span class="sxs-lookup"><span data-stu-id="eb056-343">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="eb056-344">1.2.3.4/b</span><span class="sxs-lookup"><span data-stu-id="eb056-344">1.2.3.4/b</span></span>
  - <span data-ttu-id="eb056-345">1.2.3.4/baaaa</span><span class="sxs-lookup"><span data-stu-id="eb056-345">1.2.3.4/baaaa</span></span>

### <a name="examples-of-invalid-entries"></a><span data-ttu-id="eb056-346">Beispiele für ungültige Einträge</span><span class="sxs-lookup"><span data-stu-id="eb056-346">Examples of invalid entries</span></span>

<span data-ttu-id="eb056-347">Die folgenden Einträge sind ungültig:</span><span class="sxs-lookup"><span data-stu-id="eb056-347">The following entries are invalid:</span></span>

- <span data-ttu-id="eb056-348">**Fehlende oder ungültige Domänenwerte**:</span><span class="sxs-lookup"><span data-stu-id="eb056-348">**Missing or invalid domain values**:</span></span>

  - <span data-ttu-id="eb056-349">contoso</span><span class="sxs-lookup"><span data-stu-id="eb056-349">contoso</span></span>
  - <span data-ttu-id="eb056-350">\*.contoso.\*</span><span class="sxs-lookup"><span data-stu-id="eb056-350">\*.contoso.\*</span></span>
  - <span data-ttu-id="eb056-351">\*.com</span><span class="sxs-lookup"><span data-stu-id="eb056-351">\*.com</span></span>
  - <span data-ttu-id="eb056-352">\*.pdf</span><span class="sxs-lookup"><span data-stu-id="eb056-352">\*.pdf</span></span>

- <span data-ttu-id="eb056-353">**Platzhalter für Text oder ohne Abstandszeichen**:</span><span class="sxs-lookup"><span data-stu-id="eb056-353">**Wildcard on text or without spacing characters**:</span></span>

  - <span data-ttu-id="eb056-354">\*contoso.com</span><span class="sxs-lookup"><span data-stu-id="eb056-354">\*contoso.com</span></span>
  - <span data-ttu-id="eb056-355">contoso.com\*</span><span class="sxs-lookup"><span data-stu-id="eb056-355">contoso.com\*</span></span>
  - <span data-ttu-id="eb056-356">\*1.2.3.4</span><span class="sxs-lookup"><span data-stu-id="eb056-356">\*1.2.3.4</span></span>
  - <span data-ttu-id="eb056-357">1.2.3.4\*</span><span class="sxs-lookup"><span data-stu-id="eb056-357">1.2.3.4\*</span></span>
  - <span data-ttu-id="eb056-358">contoso.com/a\*</span><span class="sxs-lookup"><span data-stu-id="eb056-358">contoso.com/a\*</span></span>
  - <span data-ttu-id="eb056-359">contoso.com/ab\*</span><span class="sxs-lookup"><span data-stu-id="eb056-359">contoso.com/ab\*</span></span>

- <span data-ttu-id="eb056-360">**IP-Adressen mit Ports**:</span><span class="sxs-lookup"><span data-stu-id="eb056-360">**IP addresses with ports**:</span></span>

  - <span data-ttu-id="eb056-361">contoso.com:443</span><span class="sxs-lookup"><span data-stu-id="eb056-361">contoso.com:443</span></span>
  - <span data-ttu-id="eb056-362">abc.contoso.com:25</span><span class="sxs-lookup"><span data-stu-id="eb056-362">abc.contoso.com:25</span></span>

- <span data-ttu-id="eb056-363">**Nicht beschreibende Platzhalter**:</span><span class="sxs-lookup"><span data-stu-id="eb056-363">**Non-descriptive wildcards**:</span></span>

  - \*
  - <span data-ttu-id="eb056-364">\*.\*</span><span class="sxs-lookup"><span data-stu-id="eb056-364">\*.\*</span></span>

- <span data-ttu-id="eb056-365">**Mittlere Platzhalter**:</span><span class="sxs-lookup"><span data-stu-id="eb056-365">**Middle wildcards**:</span></span>

  - <span data-ttu-id="eb056-366">conto \* so.com</span><span class="sxs-lookup"><span data-stu-id="eb056-366">conto\*so.com</span></span>
  - <span data-ttu-id="eb056-367">conto~so.com</span><span class="sxs-lookup"><span data-stu-id="eb056-367">conto~so.com</span></span>

- <span data-ttu-id="eb056-368">**Doppelte Platzhalter**</span><span class="sxs-lookup"><span data-stu-id="eb056-368">**Double wildcards**</span></span>

  - <span data-ttu-id="eb056-369">contoso.com/\*\*</span><span class="sxs-lookup"><span data-stu-id="eb056-369">contoso.com/\*\*</span></span>
  - <span data-ttu-id="eb056-370">contoso.com/\*/\*</span><span class="sxs-lookup"><span data-stu-id="eb056-370">contoso.com/\*/\*</span></span>
