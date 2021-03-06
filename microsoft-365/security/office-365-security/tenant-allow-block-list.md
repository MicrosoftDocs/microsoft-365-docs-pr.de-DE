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
ms.openlocfilehash: 20e460f4e93f7b87faaead8b87ba561224e38938
ms.sourcegitcommit: babbba2b5bf69fd3facde2905ec024b753dcd1b3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2021
ms.locfileid: "50515208"
---
# <a name="manage-the-tenant-allowblock-list"></a><span data-ttu-id="2b56d-103">Verwalten der Zulassungs-/Sperrliste des Mandanten</span><span class="sxs-lookup"><span data-stu-id="2b56d-103">Manage the Tenant Allow/Block List</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="2b56d-104">**Gilt für**</span><span class="sxs-lookup"><span data-stu-id="2b56d-104">**Applies to**</span></span>
- [<span data-ttu-id="2b56d-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="2b56d-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="2b56d-106">Microsoft Defender für Office 365 Plan 1 und Plan 2</span><span class="sxs-lookup"><span data-stu-id="2b56d-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="2b56d-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="2b56d-107">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

> [!NOTE]
>
> <span data-ttu-id="2b56d-108">Die in diesem Artikel beschriebenen Features befinden sich in Vorschau, können geändert werden und sind nicht in allen Organisationen verfügbar.</span><span class="sxs-lookup"><span data-stu-id="2b56d-108">The features described in this article are in Preview, are subject to change, and are not available in all organizations.</span></span>
>
> <span data-ttu-id="2b56d-109">Sie können zu **diesem Zeitpunkt** keine zulässigen Elemente in der Mandanten zulassen/blockieren-Liste konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="2b56d-109">You can't **configure** allowed items in the Tenant Allow/Block List at this time.</span></span>

<span data-ttu-id="2b56d-110">In Microsoft 365-Organisationen mit Postfächern in Exchange Online oder eigenständigen Exchange Online Protection (EOP)-Organisationen ohne Exchange Online-Postfächer können Sie mit dem EOP-Filterungs-Urteil nicht einverstanden sein.</span><span class="sxs-lookup"><span data-stu-id="2b56d-110">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, you might disagree with the EOP filtering verdict.</span></span> <span data-ttu-id="2b56d-111">Beispielsweise kann eine gute Nachricht als ungültig (falsch positiv) gekennzeichnet werden, oder eine schlechte Nachricht kann als ungültig (falsch negativ) zugelassen werden.</span><span class="sxs-lookup"><span data-stu-id="2b56d-111">For example, a good message might be marked as bad (a false positive), or a bad message might be allowed through (a false negative).</span></span>

<span data-ttu-id="2b56d-112">Mit der Liste Mandanten zulassen/blockieren im Security & Compliance Center können Sie die Microsoft 365-Filterungs-Urteile manuell außer Kraft setzen.</span><span class="sxs-lookup"><span data-stu-id="2b56d-112">The Tenant Allow/Block List in the Security & Compliance Center gives you a way to manually override the Microsoft 365 filtering verdicts.</span></span> <span data-ttu-id="2b56d-113">Die Mandanten zulassen/blockieren Liste wird während des Nachrichtenflusses und zum Zeitpunkt der Benutzerklicks verwendet.</span><span class="sxs-lookup"><span data-stu-id="2b56d-113">The Tenant Allow/Block List is used during mail flow and at the time of user clicks.</span></span> <span data-ttu-id="2b56d-114">Sie können URLs oder Dateien angeben, die immer blockiert werden.</span><span class="sxs-lookup"><span data-stu-id="2b56d-114">You can specify URLs or files to always block.</span></span>

<span data-ttu-id="2b56d-115">In diesem Artikel wird beschrieben, wie Sie Einträge in der Mandanten zulassen/blockieren-Liste im Security & Compliance Center oder in PowerShell (Exchange Online PowerShell für Microsoft 365-Organisationen mit Postfächern in Exchange Online; eigenständige EOP PowerShell für Organisationen ohne Exchange &) konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="2b56d-115">This article describes how to configure entries in the Tenant Allow/Block List in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="2b56d-116">Was sollten Sie wissen, bevor Sie beginnen?</span><span class="sxs-lookup"><span data-stu-id="2b56d-116">What do you need to know before you begin?</span></span>

- <span data-ttu-id="2b56d-117">Sie öffnen das Security & Compliance Center unter <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="2b56d-117">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="2b56d-118">Um direkt zur Seite **Mandanten zulassen/blockieren zu** wechseln, verwenden Sie <https://protection.office.com/tenantAllowBlockList> .</span><span class="sxs-lookup"><span data-stu-id="2b56d-118">To go directly to the **Tenant Allow/Block List** page, use <https://protection.office.com/tenantAllowBlockList>.</span></span>

- <span data-ttu-id="2b56d-119">Sie geben Dateien mithilfe des SHA256-Hashwerts der Datei an.</span><span class="sxs-lookup"><span data-stu-id="2b56d-119">You specify files by using the SHA256 hash value of the file.</span></span> <span data-ttu-id="2b56d-120">Führen Sie den folgenden Befehl in einer Eingabeaufforderung aus, um den SHA256-Hashwert einer Datei in Windows zu finden:</span><span class="sxs-lookup"><span data-stu-id="2b56d-120">To find the SHA256 hash value of a file in Windows, run the following command in a Command Prompt:</span></span>

  ```console
  certutil.exe -hashfile "<Path>\<Filename>" SHA256
  ```

  <span data-ttu-id="2b56d-121">Ein Beispielwert ist `768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3a` .</span><span class="sxs-lookup"><span data-stu-id="2b56d-121">An example value is `768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3a`.</span></span> <span data-ttu-id="2b56d-122">#A0 (Perceptual Hash) werden nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="2b56d-122">Perceptual hash (pHash) values are not supported.</span></span>

- <span data-ttu-id="2b56d-123">Die verfügbaren #A0 werden weiter unten in diesem Artikel in der #A1 für den Abschnitt [Mandanten zulassen/blockieren](#url-syntax-for-the-tenant-allowblock-list) beschrieben.</span><span class="sxs-lookup"><span data-stu-id="2b56d-123">The available URL values are described in the [URL syntax for the Tenant Allow/Block List](#url-syntax-for-the-tenant-allowblock-list) section later in this article.</span></span>

- <span data-ttu-id="2b56d-124">Die Mandantenzu-/-sperrliste ermöglicht maximal 500 Einträge für URLs und 500 Einträge für Dateihashes.</span><span class="sxs-lookup"><span data-stu-id="2b56d-124">The Tenant Allow/Block List allows a maximum of 500 entries for URLs, and 500 entries for file hashes.</span></span>

- <span data-ttu-id="2b56d-125">Die maximale Anzahl von Zeichen für jeden Eintrag ist:</span><span class="sxs-lookup"><span data-stu-id="2b56d-125">The maximum number of characters for each entry is:</span></span>
  - <span data-ttu-id="2b56d-126">Dateihashes = 64</span><span class="sxs-lookup"><span data-stu-id="2b56d-126">File hashes = 64</span></span>
  - <span data-ttu-id="2b56d-127">URL = 250</span><span class="sxs-lookup"><span data-stu-id="2b56d-127">URL = 250</span></span>

- <span data-ttu-id="2b56d-128">Ein Eintrag sollte innerhalb von 30 Minuten aktiv sein.</span><span class="sxs-lookup"><span data-stu-id="2b56d-128">An entry should be active within 30 minutes.</span></span>

- <span data-ttu-id="2b56d-129">Standardmäßig laufen Einträge in der Mandanten-Zulassen-/Sperrliste nach 30 Tagen ab.</span><span class="sxs-lookup"><span data-stu-id="2b56d-129">By default, entries in the Tenant Allow/Block List will expire after 30 days.</span></span> <span data-ttu-id="2b56d-130">Sie können ein Datum angeben oder festlegen, dass es nie abläuft.</span><span class="sxs-lookup"><span data-stu-id="2b56d-130">You can specify a date or set them to never expire.</span></span>

- <span data-ttu-id="2b56d-131">Wie Sie eine Verbindung mit Exchange Online PowerShell herstellen, finden Sie unter [Herstellen einer Verbindung mit Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="2b56d-131">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="2b56d-132">Informationen zum Herstellen einer Verbindung mit dem eigenständigen Exchange Online Protection PowerShell finden Sie unter [Verbinden mit PowerShell in Exchange Online Protection](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="2b56d-132">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="2b56d-133">Sie müssen in **Exchange Online** Berechtigungen erhalten, bevor Sie die in diesem Artikel beschriebenen Schritte ausführen können:</span><span class="sxs-lookup"><span data-stu-id="2b56d-133">You need to be assigned permissions in **Exchange Online** before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="2b56d-134">Zum Hinzufügen und Entfernen von Werten aus der Mandantenberechtigungs-/Sperrliste müssen Sie Mitglied der Rollengruppen Organisationsverwaltung oder **Sicherheitsadministrator** sein. </span><span class="sxs-lookup"><span data-stu-id="2b56d-134">To add and remove values from the Tenant Allow/Block List, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="2b56d-135">Für den schreibgeschützten Zugriff auf die Mandantenzugriffs-/Sperrliste müssen Sie Mitglied der Rollengruppen **"Globaler Leser"** oder **"Sicherheitsleser"** sein.</span><span class="sxs-lookup"><span data-stu-id="2b56d-135">For read-only access to the Tenant Allow/Block List, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="2b56d-136">Weitere Informationen finden Sie unter [Berechtigungen in Exchange Online](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo).</span><span class="sxs-lookup"><span data-stu-id="2b56d-136">For more information, see [Permissions in Exchange Online](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo).</span></span>

  > [!NOTE]
  > 
  > - <span data-ttu-id="2b56d-137">Durch das Hinzufügen von Benutzern zur entsprechenden Azure Active Directory-Rolle im Microsoft 365 Admin Center erhalten Benutzer die erforderlichen Berechtigungen _und_ Berechtigungen für andere Features in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="2b56d-137">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="2b56d-138">Weitere Informationen finden Sie unter [Informationen zu Administratorrollen](../../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="2b56d-138">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  > - <span data-ttu-id="2b56d-139">Die Rollengruppe **Organisationsverwaltung mit Leserechten** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) ermöglicht auch einen schreibgeschützten Zugriff auf das Feature.</span><span class="sxs-lookup"><span data-stu-id="2b56d-139">The **View-Only Organization Management** role group in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

## <a name="use-the-security--compliance-center-to-create-url-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="2b56d-140">Verwenden des Security & Compliance Center zum Erstellen von URL-Einträgen in der Mandantenzu-/-sperrliste</span><span class="sxs-lookup"><span data-stu-id="2b56d-140">Use the Security & Compliance Center to create URL entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="2b56d-141">Weitere Informationen zur Syntax für #A0 finden Sie in der URL-Syntax für den Abschnitt [Mandantenzu-/Sperrliste](#url-syntax-for-the-tenant-allowblock-list) weiter unten in diesem Artikel.</span><span class="sxs-lookup"><span data-stu-id="2b56d-141">For details about the syntax for URL entries, see the [URL syntax for the Tenant Allow/Block List](#url-syntax-for-the-tenant-allowblock-list) section later in this article.</span></span>

1. <span data-ttu-id="2b56d-142">Wechseln Sie im Security & Compliance Center zu Richtlinien für die **Bedrohungsverwaltung** \>  \> **Mandanten zulassen/blockieren Listen**.</span><span class="sxs-lookup"><span data-stu-id="2b56d-142">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="2b56d-143">Überprüfen Sie auf der Seite Mandanten **zulassen/blockieren,** ob die Registerkarte **URLs** ausgewählt ist, und klicken Sie dann auf **Blockieren.**</span><span class="sxs-lookup"><span data-stu-id="2b56d-143">On the **Tenant Allow/Block List** page, verify that the **URLs** tab is selected, and then click **Block**</span></span>

3. <span data-ttu-id="2b56d-144">Konfigurieren Sie **im angezeigten** Flyout UrLs blockieren die folgenden Einstellungen:</span><span class="sxs-lookup"><span data-stu-id="2b56d-144">In the **Block URLs** flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="2b56d-145">**Zu blockierende URLs hinzufügen:** Geben Sie eine URL pro Zeile ein, bis zu maximal 20.</span><span class="sxs-lookup"><span data-stu-id="2b56d-145">**Add URLs to block**: Enter one URL per line, up to a maximum of 20.</span></span>

   - <span data-ttu-id="2b56d-146">**Nie ablaufen:** Gehen Sie wie folgt vor:</span><span class="sxs-lookup"><span data-stu-id="2b56d-146">**Never expire**: Do one of the following steps:</span></span>

     - <span data-ttu-id="2b56d-147">Überprüfen Sie, ob die Einstellung deaktiviert ist ( Umschalten ) und verwenden Sie das Feld Läuft auf, um das ![ ](../../media/scc-toggle-off.png) Ablaufdatum für die Einträge anzugeben. </span><span class="sxs-lookup"><span data-stu-id="2b56d-147">Verify the setting is turned off (![Toggle off](../../media/scc-toggle-off.png)) and use the **Expires on** box to specify the expiration date for the entries.</span></span>

       <span data-ttu-id="2b56d-148">oder</span><span class="sxs-lookup"><span data-stu-id="2b56d-148">or</span></span>

     - <span data-ttu-id="2b56d-149">Verschieben Sie den Umschalter nach rechts, um die Einträge so zu konfigurieren, dass sie nie ablaufen:</span><span class="sxs-lookup"><span data-stu-id="2b56d-149">Move the toggle to the right to configure the entries to never expire:</span></span> ![Umschaltfläche ein](../../media/scc-toggle-on.png)<span data-ttu-id="2b56d-151">.</span><span class="sxs-lookup"><span data-stu-id="2b56d-151">.</span></span>

   - <span data-ttu-id="2b56d-152">**Optionaler Hinweis:** Geben Sie beschreibenden Text für die Einträge ein.</span><span class="sxs-lookup"><span data-stu-id="2b56d-152">**Optional note**: Enter descriptive text for the entries.</span></span>

4. <span data-ttu-id="2b56d-153">Klicken Sie nach Abschluss des Vorgangs auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="2b56d-153">When you're finished, click **Add**.</span></span>

## <a name="use-the-security--compliance-center-to-create-file-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="2b56d-154">Verwenden des Security & Compliance Center zum Erstellen von Dateieinträgen in der Mandantenzu-/-sperrliste</span><span class="sxs-lookup"><span data-stu-id="2b56d-154">Use the Security & Compliance Center to create file entries in the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="2b56d-155">Wechseln Sie im Security & Compliance Center zu Richtlinien für die **Bedrohungsverwaltung** \>  \> **Mandanten zulassen/blockieren Listen**.</span><span class="sxs-lookup"><span data-stu-id="2b56d-155">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="2b56d-156">Wählen Sie auf der Seite Mandanten **zulassen/blockieren** die Registerkarte **Dateien** aus, und klicken Sie dann auf **Blockieren**.</span><span class="sxs-lookup"><span data-stu-id="2b56d-156">On the **Tenant Allow/Block List** page, select **Files** tab, and then click **Block**.</span></span>

3. <span data-ttu-id="2b56d-157">Konfigurieren Sie **im angezeigten Flyout** Dateien zum Blockieren von Dateien hinzufügen die folgenden Einstellungen:</span><span class="sxs-lookup"><span data-stu-id="2b56d-157">In the **Add files to block** flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="2b56d-158">**Hinzufügen von Dateihashes:** Geben Sie einen SHA256-Hashwert pro Zeile ein, bis zu maximal 20.</span><span class="sxs-lookup"><span data-stu-id="2b56d-158">**Add file hashes**: Enter one SHA256 hash value per line, up to a maximum of 20.</span></span>

   - <span data-ttu-id="2b56d-159">**Nie ablaufen:** Gehen Sie wie folgt vor:</span><span class="sxs-lookup"><span data-stu-id="2b56d-159">**Never expire**: Do one of the following steps:</span></span>

     - <span data-ttu-id="2b56d-160">Überprüfen Sie, ob die Einstellung deaktiviert ist ( Umschalten ) und verwenden Sie das Feld Läuft auf, um das ![ ](../../media/scc-toggle-off.png) Ablaufdatum für die Einträge anzugeben. </span><span class="sxs-lookup"><span data-stu-id="2b56d-160">Verify the setting is turned off (![Toggle off](../../media/scc-toggle-off.png)) and use the **Expires on** box to specify the expiration date for the entries.</span></span>

     <span data-ttu-id="2b56d-161">oder</span><span class="sxs-lookup"><span data-stu-id="2b56d-161">or</span></span>

     - <span data-ttu-id="2b56d-162">Verschieben Sie den Umschalter nach rechts, um die Einträge so zu konfigurieren, dass sie nie ablaufen:</span><span class="sxs-lookup"><span data-stu-id="2b56d-162">Move the toggle to the right to configure the entries to never expire:</span></span> ![Umschaltfläche ein](../../media/scc-toggle-on.png)<span data-ttu-id="2b56d-164">.</span><span class="sxs-lookup"><span data-stu-id="2b56d-164">.</span></span>

   - <span data-ttu-id="2b56d-165">**Optionaler Hinweis:** Geben Sie beschreibenden Text für die Einträge ein.</span><span class="sxs-lookup"><span data-stu-id="2b56d-165">**Optional note**: Enter descriptive text for the entries.</span></span>

4. <span data-ttu-id="2b56d-166">Klicken Sie nach Abschluss des Vorgangs auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="2b56d-166">When you're finished, click **Add**.</span></span>

## <a name="use-the-security--compliance-center-to-view-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="2b56d-167">Verwenden des Security & Compliance Center zum Anzeigen von Einträgen in der Mandantenzu-/-sperrliste</span><span class="sxs-lookup"><span data-stu-id="2b56d-167">Use the Security & Compliance Center to view entries in the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="2b56d-168">Wechseln Sie im Security & Compliance Center zu Richtlinien für die **Bedrohungsverwaltung** \>  \> **Mandanten zulassen/blockieren Listen**.</span><span class="sxs-lookup"><span data-stu-id="2b56d-168">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="2b56d-169">Wählen Sie **die Registerkarte URLs** oder die **Registerkarte Dateien** aus.</span><span class="sxs-lookup"><span data-stu-id="2b56d-169">Select the **URLs** tab or the **Files** tab.</span></span>

<span data-ttu-id="2b56d-170">Klicken Sie auf die folgenden Spaltenüberschriften, um sie in aufsteigender oder absteigender Reihenfolge zu sortieren:</span><span class="sxs-lookup"><span data-stu-id="2b56d-170">Click on the following column headings to sort in ascending or descending order:</span></span>

- <span data-ttu-id="2b56d-171">**Wert**: Die URL oder der Dateihash.</span><span class="sxs-lookup"><span data-stu-id="2b56d-171">**Value**: The URL or the file hash.</span></span>
- <span data-ttu-id="2b56d-172">**Datum der letzten Aktualisierung**</span><span class="sxs-lookup"><span data-stu-id="2b56d-172">**Last updated date**</span></span>
- <span data-ttu-id="2b56d-173">**Ablaufdatum**</span><span class="sxs-lookup"><span data-stu-id="2b56d-173">**Expiration date**</span></span>
- <span data-ttu-id="2b56d-174">**Hinweis**</span><span class="sxs-lookup"><span data-stu-id="2b56d-174">**Note**</span></span>

<span data-ttu-id="2b56d-175">Klicken **Sie auf Suchen,** geben Sie einen Wert ganz oder teilweise ein, und drücken Sie die EINGABETASTE, um einen bestimmten Wert zu finden.</span><span class="sxs-lookup"><span data-stu-id="2b56d-175">Click **Search**, enter all or part of a value, and then press ENTER to find a specific value.</span></span> <span data-ttu-id="2b56d-176">Wenn Sie fertig sind, klicken Sie auf **Suche löschen Suchsymbol** ![ löschen ](../../media/b6512677-5e7b-42b0-a8a3-3be1d7fa23ee.gif) .</span><span class="sxs-lookup"><span data-stu-id="2b56d-176">When you're finished, click **Clear search** ![Clear search icon](../../media/b6512677-5e7b-42b0-a8a3-3be1d7fa23ee.gif).</span></span>

<span data-ttu-id="2b56d-177">Klicken Sie **auf Filter**.</span><span class="sxs-lookup"><span data-stu-id="2b56d-177">Click **Filter**.</span></span> <span data-ttu-id="2b56d-178">Konfigurieren Sie **im angezeigten** Flyout Filter eine der folgenden Einstellungen:</span><span class="sxs-lookup"><span data-stu-id="2b56d-178">In the **Filter** flyout that appears, configure any of the following settings:</span></span>

- <span data-ttu-id="2b56d-179">**Nie ablaufen:** Wählen Sie aus: ![ Umschalten ](../../media/scc-toggle-off.png) oder Aktivieren: ![ Umschalten auf ](../../media/scc-toggle-on.png) .</span><span class="sxs-lookup"><span data-stu-id="2b56d-179">**Never expire**: Select off: ![Toggle off](../../media/scc-toggle-off.png) or on: ![Toggle on](../../media/scc-toggle-on.png).</span></span>

- <span data-ttu-id="2b56d-180">**Last updated**: Select a start date (**From**), an end date (**To**) or both.</span><span class="sxs-lookup"><span data-stu-id="2b56d-180">**Last updated**: Select a start date (**From**), an end date (**To**) or both.</span></span>

- <span data-ttu-id="2b56d-181">**Ablaufdatum**: Wählen Sie ein Startdatum (**Von**), ein Enddatum (**An**) oder beides aus.</span><span class="sxs-lookup"><span data-stu-id="2b56d-181">**Expiration date**: Select a start date (**From**), an end date (**To**) or both.</span></span>

<span data-ttu-id="2b56d-182">Klicken Sie nach Abschluss des Abschlusses auf **Übernehmen**.</span><span class="sxs-lookup"><span data-stu-id="2b56d-182">When you're finished, click **Apply**.</span></span>

<span data-ttu-id="2b56d-183">Klicken Sie zum Löschen vorhandener Filter auf **Filter,** und klicken Sie im angezeigten **Flyout** Filter **auf Filter löschen.**</span><span class="sxs-lookup"><span data-stu-id="2b56d-183">To clear existing filters, click **Filter**, and in the **Filter** flyout that appears, click **Clear filters**.</span></span>

## <a name="use-the-security--compliance-center-to-modify-block-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="2b56d-184">Verwenden des Security & Compliance Center zum Ändern von Blockeinträgen in der Mandantenzu-/-sperrliste</span><span class="sxs-lookup"><span data-stu-id="2b56d-184">Use the Security & Compliance Center to modify block entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="2b56d-185">Sie können die vorhandenen blockierten URL- oder Dateiwerte in einem Eintrag nicht ändern.</span><span class="sxs-lookup"><span data-stu-id="2b56d-185">You can't modify the existing blocked URL or file values within an entry.</span></span> <span data-ttu-id="2b56d-186">Um diese Werte zu ändern, müssen Sie den Eintrag löschen und neu erstellen.</span><span class="sxs-lookup"><span data-stu-id="2b56d-186">To modify these values, you need to delete and recreate the entry.</span></span>

1. <span data-ttu-id="2b56d-187">Wechseln Sie im Security & Compliance Center zu Richtlinien für die **Bedrohungsverwaltung** \>  \> **Mandanten zulassen/blockieren Listen**.</span><span class="sxs-lookup"><span data-stu-id="2b56d-187">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="2b56d-188">Wählen Sie **die Registerkarte URLs** oder die **Registerkarte Dateien** aus.</span><span class="sxs-lookup"><span data-stu-id="2b56d-188">Select the **URLs** tab or the **Files** tab.</span></span>

3. <span data-ttu-id="2b56d-189">Wählen Sie den Blockeintrag aus, den Sie ändern möchten, und klicken Sie dann auf **Bearbeiten** ![ (Symbol). ](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png)</span><span class="sxs-lookup"><span data-stu-id="2b56d-189">Select the block entry that you want to modify, and then click **Edit** ![Edit icon](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png).</span></span>

4. <span data-ttu-id="2b56d-190">Konfigurieren Sie im angezeigten Flyout die folgenden Einstellungen:</span><span class="sxs-lookup"><span data-stu-id="2b56d-190">In the flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="2b56d-191">**Nie ablaufen:** Gehen Sie wie folgt vor:</span><span class="sxs-lookup"><span data-stu-id="2b56d-191">**Never expire**: Do one of the following steps:</span></span>

     - <span data-ttu-id="2b56d-192">Überprüfen Sie, ob die Einstellung deaktiviert ist ( Umschalten ) und verwenden Sie das Feld Läuft auf, um das Ablaufdatum für ![ ](../../media/scc-toggle-off.png) den Eintrag anzugeben. </span><span class="sxs-lookup"><span data-stu-id="2b56d-192">Verify the setting is turned off (![Toggle off](../../media/scc-toggle-off.png)) and use the **Expires on** box to specify the expiration date for the entry.</span></span>

       <span data-ttu-id="2b56d-193">oder</span><span class="sxs-lookup"><span data-stu-id="2b56d-193">or</span></span>

     - <span data-ttu-id="2b56d-194">Verschieben Sie den Umschalter nach rechts, um den Eintrag so zu konfigurieren, dass er nie abläuft:</span><span class="sxs-lookup"><span data-stu-id="2b56d-194">Move the toggle to the right to configure the entry to never expire:</span></span> ![Umschaltfläche ein](../../media/scc-toggle-on.png)<span data-ttu-id="2b56d-196">.</span><span class="sxs-lookup"><span data-stu-id="2b56d-196">.</span></span>

   - <span data-ttu-id="2b56d-197">**Optionaler Hinweis:** Geben Sie beschreibenden Text für den Eintrag ein.</span><span class="sxs-lookup"><span data-stu-id="2b56d-197">**Optional note**: Enter descriptive text for the entry.</span></span>

5. <span data-ttu-id="2b56d-198">Klicken Sie nach Abschluss des Vorgangs auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="2b56d-198">When you're finished, click **Save**.</span></span>

## <a name="use-the-security--compliance-center-to-remove-block-entries-from-the-tenant-allowblock-list"></a><span data-ttu-id="2b56d-199">Verwenden des Security & Compliance Center zum Entfernen von Sperreinträgen aus der Mandantenzu-/-sperrliste</span><span class="sxs-lookup"><span data-stu-id="2b56d-199">Use the Security & Compliance Center to remove block entries from the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="2b56d-200">Wechseln Sie im Security & Compliance Center zu Richtlinien für die **Bedrohungsverwaltung** \>  \> **Mandanten zulassen/blockieren Listen**.</span><span class="sxs-lookup"><span data-stu-id="2b56d-200">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="2b56d-201">Wählen Sie **die Registerkarte URLs** oder die **Registerkarte Dateien** aus.</span><span class="sxs-lookup"><span data-stu-id="2b56d-201">Select the **URLs** tab or the **Files** tab.</span></span>

3. <span data-ttu-id="2b56d-202">Wählen Sie den Blockeintrag aus, den Sie entfernen möchten, und klicken Sie dann auf **Löschen** ![ Löschen ](../../media/87565fbb-5147-4f22-9ed7-1c18ce664392.png) (Symbol).</span><span class="sxs-lookup"><span data-stu-id="2b56d-202">Select the block entry that you want to remove, and then click **Delete** ![Delete icon](../../media/87565fbb-5147-4f22-9ed7-1c18ce664392.png).</span></span>

4. <span data-ttu-id="2b56d-203">Klicken Sie im angezeigten Warnungsdialogfeld auf **Löschen**.</span><span class="sxs-lookup"><span data-stu-id="2b56d-203">In the warning dialog that appears, click **Delete**.</span></span>

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-the-tenant-allowblock-list"></a><span data-ttu-id="2b56d-204">Verwenden von Exchange Online PowerShell oder eigenständiger EOP PowerShell zum Konfigurieren der Mandanten zulassen/Blockieren-Liste</span><span class="sxs-lookup"><span data-stu-id="2b56d-204">Use Exchange Online PowerShell or standalone EOP PowerShell to configure the Tenant Allow/Block List</span></span>

### <a name="use-powershell-to-add-block-entries-to-the-tenant-allowblock-list"></a><span data-ttu-id="2b56d-205">Verwenden von PowerShell zum Hinzufügen von Blockeinträgen zur Mandantenzu-/Sperrliste</span><span class="sxs-lookup"><span data-stu-id="2b56d-205">Use PowerShell to add block entries to the Tenant Allow/Block List</span></span>

<span data-ttu-id="2b56d-206">Verwenden Sie die folgende Syntax, um Blockeinträge in der Mandantenzu-/Sperrliste hinzuzufügen:</span><span class="sxs-lookup"><span data-stu-id="2b56d-206">To add block entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
New-TenantAllowBlockListItems -ListType <Url | FileHash> -Block -Entries <String[]> [-ExpirationDate <DateTime>] [-NoExpiration] [-Notes <String>]
```

<span data-ttu-id="2b56d-207">In diesem Beispiel wird ein Block-URL-Eintrag für contoso.com und alle Unterdomänen hinzugefügt (z. B. contoso.com, www.contoso.com und xyz.abc.contoso.com).</span><span class="sxs-lookup"><span data-stu-id="2b56d-207">This example adds a block URL entry for contoso.com and all subdomains (for example, contoso.com, www.contoso.com, and xyz.abc.contoso.com).</span></span> <span data-ttu-id="2b56d-208">Da wir die Parameter ExpirationDate oder NoExpiration nicht verwendet haben, läuft der Eintrag nach 30 Tagen ab.</span><span class="sxs-lookup"><span data-stu-id="2b56d-208">Because we didn't use the ExpirationDate or NoExpiration parameters, the entry expires after 30 days.</span></span>

```powershell
New-TenantAllowBlockListItems -ListType Url -Block -Entries ~contoso.com
```

<span data-ttu-id="2b56d-209">In diesem Beispiel wird ein Blockdateieintrag für die angegebenen Dateien, die nie abläuft, hinzufügt.</span><span class="sxs-lookup"><span data-stu-id="2b56d-209">This example adds a block file entry for the specified files that never expires.</span></span>

```powershell
New-TenantAllowBlockListItems -ListType FileHash -Block -Entries "768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3","2c0a35409ff0873cfa28b70b8224e9aca2362241c1f0ed6f622fef8d4722fd9a" -NoExpiration
```

<span data-ttu-id="2b56d-210">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [New-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/new-tenantallowblocklistitems).</span><span class="sxs-lookup"><span data-stu-id="2b56d-210">For detailed syntax and parameter information, see [New-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/new-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-view-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="2b56d-211">Verwenden von PowerShell zum Anzeigen von Einträgen in der Mandanten-Zulassen-/Sperrliste</span><span class="sxs-lookup"><span data-stu-id="2b56d-211">Use PowerShell to view entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="2b56d-212">Verwenden Sie die folgende Syntax, um Einträge in der Mandantenzu-/Sperrliste anzeigen zu können:</span><span class="sxs-lookup"><span data-stu-id="2b56d-212">To view entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType <Url | FileHash> [-Entry <URLValue | FileHashValue>] [-Block] [-ExpirationDate <DateTime>] [-NoExpiration]
```

<span data-ttu-id="2b56d-213">In diesem Beispiel werden alle blockierten URLs zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="2b56d-213">This example returns all blocked URLs.</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType Url -Block
```

<span data-ttu-id="2b56d-214">In diesem Beispiel werden Informationen für den angegebenen Dateihashwert zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="2b56d-214">This example returns information for the specified file hash value.</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType FileHash -Entry "9f86d081884c7d659a2feaa0c55ad015a3bf4f1b2b0b822cd15d6c15b0f00a08"
```

<span data-ttu-id="2b56d-215">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Get-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/get-tenantallowblocklistitems).</span><span class="sxs-lookup"><span data-stu-id="2b56d-215">For detailed syntax and parameter information, see [Get-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/get-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-modify-block-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="2b56d-216">Verwenden von PowerShell zum Ändern von Blockeinträgen in der Mandantenzu-/-sperrliste</span><span class="sxs-lookup"><span data-stu-id="2b56d-216">Use PowerShell to modify block entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="2b56d-217">Sie können die vorhandenen URL- oder Dateiwerte in einem Blockeintrag nicht ändern.</span><span class="sxs-lookup"><span data-stu-id="2b56d-217">You can't modify the existing URL or file values within a block entry.</span></span> <span data-ttu-id="2b56d-218">Um diese Werte zu ändern, müssen Sie den Eintrag löschen und neu erstellen.</span><span class="sxs-lookup"><span data-stu-id="2b56d-218">To modify these values, you need to delete and recreate the entry.</span></span>

<span data-ttu-id="2b56d-219">Verwenden Sie die folgende Syntax, um Blockeinträge in der Mandanten zulassen/blockieren-Liste zu ändern:</span><span class="sxs-lookup"><span data-stu-id="2b56d-219">To modify block entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Set-TenantAllowBlockListItems -ListType <Url | FileHash> -Ids <"Id1","Id2",..."IdN"> [-Block] [-ExpirationDate <DateTime>] [-NoExpiration] [-Notes <String>]
```

<span data-ttu-id="2b56d-220">In diesem Beispiel wird das Ablaufdatum des angegebenen Blockeintrags geändert.</span><span class="sxs-lookup"><span data-stu-id="2b56d-220">This example changes the expiration date of the specified block entry.</span></span>

```powershell
Set-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSRAAAA" -ExpirationDate (Get-Date "5/30/2020 9:30 AM").ToUniversalTime()
```

<span data-ttu-id="2b56d-221">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Set-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/set-tenantallowblocklistitems).</span><span class="sxs-lookup"><span data-stu-id="2b56d-221">For detailed syntax and parameter information, see [Set-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/set-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-remove-block-entries-from-the-tenant-allowblock-list"></a><span data-ttu-id="2b56d-222">Verwenden von PowerShell zum Entfernen von Sperreinträgen aus der Mandanten-Zulassen-/Sperrliste</span><span class="sxs-lookup"><span data-stu-id="2b56d-222">Use PowerShell to remove block entries from the Tenant Allow/Block List</span></span>

<span data-ttu-id="2b56d-223">Verwenden Sie die folgende Syntax, um Blockeinträge aus der Mandanten zulassen/blockieren-Liste zu entfernen:</span><span class="sxs-lookup"><span data-stu-id="2b56d-223">To remove block entries from the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Remove-TenantAllowBlockListItems -ListType <Url | FileHash> -Ids <"Id1","Id2",..."IdN">
```

<span data-ttu-id="2b56d-224">In diesem Beispiel wird der angegebene Block-URL-Eintrag aus der Mandanten-Allow/Block List entfernt.</span><span class="sxs-lookup"><span data-stu-id="2b56d-224">This example removes the specified block URL entry from the Tenant Allow/Block List.</span></span>

```powershell
Remove-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSPAAAA0"
```

<span data-ttu-id="2b56d-225">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Remove-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/remove-tenantallowblocklistitems).</span><span class="sxs-lookup"><span data-stu-id="2b56d-225">For detailed syntax and parameter information, see [Remove-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/remove-tenantallowblocklistitems).</span></span>

## <a name="url-syntax-for-the-tenant-allowblock-list"></a><span data-ttu-id="2b56d-226">#A0 für die Mandanten-Allow/Block List</span><span class="sxs-lookup"><span data-stu-id="2b56d-226">URL syntax for the Tenant Allow/Block List</span></span>

- <span data-ttu-id="2b56d-227">IP4v- und IPv6-Adressen sind zulässig, TCP/UDP-Ports jedoch nicht.</span><span class="sxs-lookup"><span data-stu-id="2b56d-227">IP4v and IPv6 addresses are allowed, but TCP/UDP ports are not.</span></span>

- <span data-ttu-id="2b56d-228">Dateinamenerweiterungen sind nicht zulässig (z. B. test.pdf).</span><span class="sxs-lookup"><span data-stu-id="2b56d-228">Filename extensions are not allowed (for example, test.pdf).</span></span>

- <span data-ttu-id="2b56d-229">Unicode wird nicht unterstützt, Punycode jedoch.</span><span class="sxs-lookup"><span data-stu-id="2b56d-229">Unicode is not supported, but Punycode is.</span></span>

- <span data-ttu-id="2b56d-230">Hostnamen sind zulässig, wenn alle folgenden Anweisungen zutreffen:</span><span class="sxs-lookup"><span data-stu-id="2b56d-230">Hostnames are allowed if all of the following statements are true:</span></span>
  - <span data-ttu-id="2b56d-231">Der Hostname enthält einen Zeitraum.</span><span class="sxs-lookup"><span data-stu-id="2b56d-231">The hostname contains a period.</span></span>
  - <span data-ttu-id="2b56d-232">Es gibt mindestens ein Zeichen links vom Zeitraum.</span><span class="sxs-lookup"><span data-stu-id="2b56d-232">There is at least one character to the left of the period.</span></span>
  - <span data-ttu-id="2b56d-233">Rechts neben dem Zeitraum befinden sich mindestens zwei Zeichen.</span><span class="sxs-lookup"><span data-stu-id="2b56d-233">There are at least two characters to the right of the period.</span></span>

  <span data-ttu-id="2b56d-234">Beispielsweise ist `t.co` zulässig oder nicht `.com` `contoso.` zulässig.</span><span class="sxs-lookup"><span data-stu-id="2b56d-234">For example, `t.co` is allowed; `.com` or `contoso.` are not allowed.</span></span>

- <span data-ttu-id="2b56d-235">Unterpfade werden nicht impliziert.</span><span class="sxs-lookup"><span data-stu-id="2b56d-235">Subpaths are not implied.</span></span>

  <span data-ttu-id="2b56d-236">Enthält z. `contoso.com` B. nicht `contoso.com/a` .</span><span class="sxs-lookup"><span data-stu-id="2b56d-236">For example, `contoso.com` does not include `contoso.com/a`.</span></span>

- <span data-ttu-id="2b56d-237">Platzhalter (\*) sind in den folgenden Szenarien zulässig:</span><span class="sxs-lookup"><span data-stu-id="2b56d-237">Wildcards (\*) are allowed in the following scenarios:</span></span>

  - <span data-ttu-id="2b56d-238">Auf einen linken Platzhalter muss ein Zeitraum folgen, um eine Unterdomäne anzugeben.</span><span class="sxs-lookup"><span data-stu-id="2b56d-238">A left wildcard must be followed by a period to specify a subdomain.</span></span>

    <span data-ttu-id="2b56d-239">Ist beispielsweise `*.contoso.com` zulässig; `*contoso.com` ist nicht zulässig.</span><span class="sxs-lookup"><span data-stu-id="2b56d-239">For example, `*.contoso.com` is allowed; `*contoso.com` is not allowed.</span></span>

  - <span data-ttu-id="2b56d-240">Ein rechter Platzhalter muss einem Schrägstrich (/) folgen, um einen Pfad anzugeben.</span><span class="sxs-lookup"><span data-stu-id="2b56d-240">A right wildcard must follow a forward slash (/) to specify a path.</span></span>

    <span data-ttu-id="2b56d-241">Beispielsweise ist `contoso.com/*` zulässig oder nicht `contoso.com*` `contoso.com/ab*` zulässig.</span><span class="sxs-lookup"><span data-stu-id="2b56d-241">For example, `contoso.com/*` is allowed; `contoso.com*` or `contoso.com/ab*` are not allowed.</span></span>

  - <span data-ttu-id="2b56d-242">Alle Unterpfade werden nicht durch einen rechten Platzhalter impliziert.</span><span class="sxs-lookup"><span data-stu-id="2b56d-242">All subpaths are not implied by a right wildcard.</span></span>

    <span data-ttu-id="2b56d-243">Enthält z. `contoso.com/*` B. nicht `contoso.com/a` .</span><span class="sxs-lookup"><span data-stu-id="2b56d-243">For example, `contoso.com/*` does not include `contoso.com/a`.</span></span>

  - <span data-ttu-id="2b56d-244">`*.com*` ist ungültig (keine auflösbare Domäne, und der rechte Platzhalter folgt keinem Schrägstrich).</span><span class="sxs-lookup"><span data-stu-id="2b56d-244">`*.com*` is invalid (not a resolvable domain and the right wildcard does not follow a forward slash).</span></span>

  - <span data-ttu-id="2b56d-245">Platzhalter sind in IP-Adressen nicht zulässig.</span><span class="sxs-lookup"><span data-stu-id="2b56d-245">Wildcards are not allowed in IP addresses.</span></span>

- <span data-ttu-id="2b56d-246">Das Tildezeichen (~) ist in den folgenden Szenarien verfügbar:</span><span class="sxs-lookup"><span data-stu-id="2b56d-246">The tilde (~) character is available in the following scenarios:</span></span>

  - <span data-ttu-id="2b56d-247">Eine linke Tilde impliziert eine Domäne und alle Unterdomänen.</span><span class="sxs-lookup"><span data-stu-id="2b56d-247">A left tilde implies a domain and all subdomains.</span></span>

    <span data-ttu-id="2b56d-248">Enthält `~contoso.com` z. `contoso.com` B. und `*.contoso.com` .</span><span class="sxs-lookup"><span data-stu-id="2b56d-248">For example `~contoso.com` includes `contoso.com` and `*.contoso.com`.</span></span>

- <span data-ttu-id="2b56d-249">URL-Einträge, die Protokolle (z. B. , oder ) enthalten, werden fehlschlagen, da `http://` URL-Einträge für alle Protokolle `https://` `ftp://` gelten.</span><span class="sxs-lookup"><span data-stu-id="2b56d-249">URL entries that contain protocols (for example, `http://`, `https://`, or `ftp://`) will fail, because URL entries apply to all protocols.</span></span>

- <span data-ttu-id="2b56d-250">Ein Benutzername oder Kennwort wird nicht unterstützt oder ist nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="2b56d-250">A username or password aren't supported or required.</span></span>

- <span data-ttu-id="2b56d-251">Anführungszeichen (' oder ") sind ungültige Zeichen.</span><span class="sxs-lookup"><span data-stu-id="2b56d-251">Quotes (' or ") are invalid characters.</span></span>

- <span data-ttu-id="2b56d-252">Eine URL sollte nach Möglichkeit alle Umleitungen enthalten.</span><span class="sxs-lookup"><span data-stu-id="2b56d-252">A URL should include all redirects where possible.</span></span>

### <a name="url-entry-scenarios"></a><span data-ttu-id="2b56d-253">Szenarien für den URL-Eintrag</span><span class="sxs-lookup"><span data-stu-id="2b56d-253">URL entry scenarios</span></span>

<span data-ttu-id="2b56d-254">Gültige URL-Einträge und deren Ergebnisse werden in den folgenden Abschnitten beschrieben.</span><span class="sxs-lookup"><span data-stu-id="2b56d-254">Valid URL entries and their results are described in the following sections.</span></span>

#### <a name="scenario-no-wildcards"></a><span data-ttu-id="2b56d-255">Szenario: Keine Platzhalter</span><span class="sxs-lookup"><span data-stu-id="2b56d-255">Scenario: No wildcards</span></span>

<span data-ttu-id="2b56d-256">**Eintrag**: `contoso.com`</span><span class="sxs-lookup"><span data-stu-id="2b56d-256">**Entry**: `contoso.com`</span></span>

- <span data-ttu-id="2b56d-257">**Übereinstimmung zulassen**: contoso.com</span><span class="sxs-lookup"><span data-stu-id="2b56d-257">**Allow match**: contoso.com</span></span>

- <span data-ttu-id="2b56d-258">**Nicht übereinstimmend zulassen:**</span><span class="sxs-lookup"><span data-stu-id="2b56d-258">**Allow not matched**:</span></span>

  - <span data-ttu-id="2b56d-259">abc-contoso.com</span><span class="sxs-lookup"><span data-stu-id="2b56d-259">abc-contoso.com</span></span>
  - <span data-ttu-id="2b56d-260">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="2b56d-260">contoso.com/a</span></span>
  - <span data-ttu-id="2b56d-261">payroll.contoso.com</span><span class="sxs-lookup"><span data-stu-id="2b56d-261">payroll.contoso.com</span></span>
  - <span data-ttu-id="2b56d-262">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="2b56d-262">test.com/contoso.com</span></span>
  - <span data-ttu-id="2b56d-263">test.com/q=contoso.com</span><span class="sxs-lookup"><span data-stu-id="2b56d-263">test.com/q=contoso.com</span></span>
  - <span data-ttu-id="2b56d-264">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="2b56d-264">www.contoso.com</span></span>
  - <span data-ttu-id="2b56d-265">www.contoso.com/q=a@contoso.com</span><span class="sxs-lookup"><span data-stu-id="2b56d-265">www.contoso.com/q=a@contoso.com</span></span>

- <span data-ttu-id="2b56d-266">**Übereinstimmung blockieren**:</span><span class="sxs-lookup"><span data-stu-id="2b56d-266">**Block match**:</span></span>

  - <span data-ttu-id="2b56d-267">contoso.com</span><span class="sxs-lookup"><span data-stu-id="2b56d-267">contoso.com</span></span>
  - <span data-ttu-id="2b56d-268">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="2b56d-268">contoso.com/a</span></span>
  - <span data-ttu-id="2b56d-269">payroll.contoso.com</span><span class="sxs-lookup"><span data-stu-id="2b56d-269">payroll.contoso.com</span></span>
  - <span data-ttu-id="2b56d-270">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="2b56d-270">test.com/contoso.com</span></span>
  - <span data-ttu-id="2b56d-271">test.com/q=contoso.com</span><span class="sxs-lookup"><span data-stu-id="2b56d-271">test.com/q=contoso.com</span></span>
  - <span data-ttu-id="2b56d-272">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="2b56d-272">www.contoso.com</span></span>
  - <span data-ttu-id="2b56d-273">www.contoso.com/q=a@contoso.com</span><span class="sxs-lookup"><span data-stu-id="2b56d-273">www.contoso.com/q=a@contoso.com</span></span>

- <span data-ttu-id="2b56d-274">**Block nicht übereinstimmend**: abc-contoso.com</span><span class="sxs-lookup"><span data-stu-id="2b56d-274">**Block not matched**: abc-contoso.com</span></span>

#### <a name="scenario-left-wildcard-subdomain"></a><span data-ttu-id="2b56d-275">Szenario: Linker Platzhalter (Unterdomäne)</span><span class="sxs-lookup"><span data-stu-id="2b56d-275">Scenario: Left wildcard (subdomain)</span></span>

<span data-ttu-id="2b56d-276">**Eintrag**: `*.contoso.com`</span><span class="sxs-lookup"><span data-stu-id="2b56d-276">**Entry**: `*.contoso.com`</span></span>

- <span data-ttu-id="2b56d-277">**Übereinstimmung zulassen** und **Übereinstimmung blockieren**:</span><span class="sxs-lookup"><span data-stu-id="2b56d-277">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="2b56d-278">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="2b56d-278">www.contoso.com</span></span>
  - <span data-ttu-id="2b56d-279">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="2b56d-279">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="2b56d-280">**Allow not matched** and **Block not matched**:</span><span class="sxs-lookup"><span data-stu-id="2b56d-280">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="2b56d-281">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="2b56d-281">123contoso.com</span></span>
  - <span data-ttu-id="2b56d-282">contoso.com</span><span class="sxs-lookup"><span data-stu-id="2b56d-282">contoso.com</span></span>
  - <span data-ttu-id="2b56d-283">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="2b56d-283">test.com/contoso.com</span></span>
  - <span data-ttu-id="2b56d-284">www.contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="2b56d-284">www.contoso.com/abc</span></span>

#### <a name="scenario-right-wildcard-at-top-of-path"></a><span data-ttu-id="2b56d-285">Szenario: Rechter Platzhalter am oberen Rand des Pfads</span><span class="sxs-lookup"><span data-stu-id="2b56d-285">Scenario: Right wildcard at top of path</span></span>

<span data-ttu-id="2b56d-286">**Eintrag**: `contoso.com/a/*`</span><span class="sxs-lookup"><span data-stu-id="2b56d-286">**Entry**: `contoso.com/a/*`</span></span>

- <span data-ttu-id="2b56d-287">**Übereinstimmung zulassen** und **Übereinstimmung blockieren**:</span><span class="sxs-lookup"><span data-stu-id="2b56d-287">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="2b56d-288">contoso.com/a/b</span><span class="sxs-lookup"><span data-stu-id="2b56d-288">contoso.com/a/b</span></span>
  - <span data-ttu-id="2b56d-289">contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="2b56d-289">contoso.com/a/b/c</span></span>
  - <span data-ttu-id="2b56d-290">contoso.com/a/?q=joe@t.com</span><span class="sxs-lookup"><span data-stu-id="2b56d-290">contoso.com/a/?q=joe@t.com</span></span>

- <span data-ttu-id="2b56d-291">**Allow not matched** and **Block not matched**:</span><span class="sxs-lookup"><span data-stu-id="2b56d-291">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="2b56d-292">contoso.com</span><span class="sxs-lookup"><span data-stu-id="2b56d-292">contoso.com</span></span>
  - <span data-ttu-id="2b56d-293">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="2b56d-293">contoso.com/a</span></span>
  - <span data-ttu-id="2b56d-294">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="2b56d-294">www.contoso.com</span></span>
  - <span data-ttu-id="2b56d-295">www.contoso.com/q=a@contoso.com</span><span class="sxs-lookup"><span data-stu-id="2b56d-295">www.contoso.com/q=a@contoso.com</span></span>

#### <a name="scenario-left-tilde"></a><span data-ttu-id="2b56d-296">Szenario: Left tilde</span><span class="sxs-lookup"><span data-stu-id="2b56d-296">Scenario: Left tilde</span></span>

<span data-ttu-id="2b56d-297">**Eintrag**: `~contoso.com`</span><span class="sxs-lookup"><span data-stu-id="2b56d-297">**Entry**: `~contoso.com`</span></span>

- <span data-ttu-id="2b56d-298">**Übereinstimmung zulassen** und **Übereinstimmung blockieren**:</span><span class="sxs-lookup"><span data-stu-id="2b56d-298">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="2b56d-299">contoso.com</span><span class="sxs-lookup"><span data-stu-id="2b56d-299">contoso.com</span></span>
  - <span data-ttu-id="2b56d-300">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="2b56d-300">www.contoso.com</span></span>
  - <span data-ttu-id="2b56d-301">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="2b56d-301">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="2b56d-302">**Allow not matched** and **Block not matched**:</span><span class="sxs-lookup"><span data-stu-id="2b56d-302">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="2b56d-303">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="2b56d-303">123contoso.com</span></span>
  - <span data-ttu-id="2b56d-304">contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="2b56d-304">contoso.com/abc</span></span>
  - <span data-ttu-id="2b56d-305">www.contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="2b56d-305">www.contoso.com/abc</span></span>

#### <a name="scenario-right-wildcard-suffix"></a><span data-ttu-id="2b56d-306">Szenario: Rechtes Platzhaltersuffix</span><span class="sxs-lookup"><span data-stu-id="2b56d-306">Scenario: Right wildcard suffix</span></span>

<span data-ttu-id="2b56d-307">**Eintrag**: `contoso.com/*`</span><span class="sxs-lookup"><span data-stu-id="2b56d-307">**Entry**: `contoso.com/*`</span></span>

- <span data-ttu-id="2b56d-308">**Übereinstimmung zulassen** und **Übereinstimmung blockieren**:</span><span class="sxs-lookup"><span data-stu-id="2b56d-308">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="2b56d-309">contoso.com/?q=whatever@fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="2b56d-309">contoso.com/?q=whatever@fabrikam.com</span></span>
  - <span data-ttu-id="2b56d-310">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="2b56d-310">contoso.com/a</span></span>
  - <span data-ttu-id="2b56d-311">contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="2b56d-311">contoso.com/a/b/c</span></span>
  - <span data-ttu-id="2b56d-312">contoso.com/ab</span><span class="sxs-lookup"><span data-stu-id="2b56d-312">contoso.com/ab</span></span>
  - <span data-ttu-id="2b56d-313">contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="2b56d-313">contoso.com/b</span></span>
  - <span data-ttu-id="2b56d-314">contoso.com/b/a/c</span><span class="sxs-lookup"><span data-stu-id="2b56d-314">contoso.com/b/a/c</span></span>
  - <span data-ttu-id="2b56d-315">contoso.com/ba</span><span class="sxs-lookup"><span data-stu-id="2b56d-315">contoso.com/ba</span></span>

- <span data-ttu-id="2b56d-316">**Nicht übereinstimmend zulassen und** **Block nicht** übereinstimmen: contoso.com</span><span class="sxs-lookup"><span data-stu-id="2b56d-316">**Allow not matched** and **Block not matched**: contoso.com</span></span>

#### <a name="scenario-left-wildcard-subdomain-and-right-wildcard-suffix"></a><span data-ttu-id="2b56d-317">Szenario: Linke Platzhalterunterdomäne und rechtes Platzhaltersuffix</span><span class="sxs-lookup"><span data-stu-id="2b56d-317">Scenario: Left wildcard subdomain and right wildcard suffix</span></span>

<span data-ttu-id="2b56d-318">**Eintrag**: `*.contoso.com/*`</span><span class="sxs-lookup"><span data-stu-id="2b56d-318">**Entry**: `*.contoso.com/*`</span></span>

- <span data-ttu-id="2b56d-319">**Übereinstimmung zulassen** und **Übereinstimmung blockieren**:</span><span class="sxs-lookup"><span data-stu-id="2b56d-319">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="2b56d-320">abc.contoso.com/ab</span><span class="sxs-lookup"><span data-stu-id="2b56d-320">abc.contoso.com/ab</span></span>
  - <span data-ttu-id="2b56d-321">abc.xyz.contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="2b56d-321">abc.xyz.contoso.com/a/b/c</span></span>
  - <span data-ttu-id="2b56d-322">www.contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="2b56d-322">www.contoso.com/a</span></span>
  - <span data-ttu-id="2b56d-323">www.contoso.com/b/a/c</span><span class="sxs-lookup"><span data-stu-id="2b56d-323">www.contoso.com/b/a/c</span></span>
  - <span data-ttu-id="2b56d-324">xyz.contoso.com/ba</span><span class="sxs-lookup"><span data-stu-id="2b56d-324">xyz.contoso.com/ba</span></span>

- <span data-ttu-id="2b56d-325">**Nicht übereinstimmend zulassen und** **Block nicht** übereinstimmen : contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="2b56d-325">**Allow not matched** and **Block not matched**: contoso.com/b</span></span>

#### <a name="scenario-left-and-right-tilde"></a><span data-ttu-id="2b56d-326">Szenario: Linker und rechter Tilde</span><span class="sxs-lookup"><span data-stu-id="2b56d-326">Scenario: Left and right tilde</span></span>

<span data-ttu-id="2b56d-327">**Eintrag**: `~contoso.com~`</span><span class="sxs-lookup"><span data-stu-id="2b56d-327">**Entry**: `~contoso.com~`</span></span>

- <span data-ttu-id="2b56d-328">**Übereinstimmung zulassen** und **Übereinstimmung blockieren**:</span><span class="sxs-lookup"><span data-stu-id="2b56d-328">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="2b56d-329">contoso.com</span><span class="sxs-lookup"><span data-stu-id="2b56d-329">contoso.com</span></span>
  - <span data-ttu-id="2b56d-330">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="2b56d-330">contoso.com/a</span></span>
  - <span data-ttu-id="2b56d-331">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="2b56d-331">www.contoso.com</span></span>
  - <span data-ttu-id="2b56d-332">www.contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="2b56d-332">www.contoso.com/b</span></span>
  - <span data-ttu-id="2b56d-333">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="2b56d-333">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="2b56d-334">**Allow not matched** and **Block not matched**:</span><span class="sxs-lookup"><span data-stu-id="2b56d-334">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="2b56d-335">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="2b56d-335">123contoso.com</span></span>
  - <span data-ttu-id="2b56d-336">contoso.org</span><span class="sxs-lookup"><span data-stu-id="2b56d-336">contoso.org</span></span>

#### <a name="scenario-ip-address"></a><span data-ttu-id="2b56d-337">Szenario: IP-Adresse</span><span class="sxs-lookup"><span data-stu-id="2b56d-337">Scenario: IP address</span></span>

<span data-ttu-id="2b56d-338">**Eintrag**: `1.2.3.4`</span><span class="sxs-lookup"><span data-stu-id="2b56d-338">**Entry**: `1.2.3.4`</span></span>

- <span data-ttu-id="2b56d-339">**Übereinstimmung zulassen** und **Übereinstimmung blockieren**: 1.2.3.4</span><span class="sxs-lookup"><span data-stu-id="2b56d-339">**Allow match** and **Block match**: 1.2.3.4</span></span>

- <span data-ttu-id="2b56d-340">**Allow not matched** and **Block not matched**:</span><span class="sxs-lookup"><span data-stu-id="2b56d-340">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="2b56d-341">1.2.3.4/a</span><span class="sxs-lookup"><span data-stu-id="2b56d-341">1.2.3.4/a</span></span>
  - <span data-ttu-id="2b56d-342">11.2.3.4/a</span><span class="sxs-lookup"><span data-stu-id="2b56d-342">11.2.3.4/a</span></span>

#### <a name="ip-address-with-right-wildcard"></a><span data-ttu-id="2b56d-343">IP-Adresse mit rechtem Platzhalter</span><span class="sxs-lookup"><span data-stu-id="2b56d-343">IP address with right wildcard</span></span>

<span data-ttu-id="2b56d-344">**Eintrag**: `1.2.3.4/*`</span><span class="sxs-lookup"><span data-stu-id="2b56d-344">**Entry**: `1.2.3.4/*`</span></span>

- <span data-ttu-id="2b56d-345">**Übereinstimmung zulassen** und **Übereinstimmung blockieren**:</span><span class="sxs-lookup"><span data-stu-id="2b56d-345">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="2b56d-346">1.2.3.4/b</span><span class="sxs-lookup"><span data-stu-id="2b56d-346">1.2.3.4/b</span></span>
  - <span data-ttu-id="2b56d-347">1.2.3.4/baaaa</span><span class="sxs-lookup"><span data-stu-id="2b56d-347">1.2.3.4/baaaa</span></span>

### <a name="examples-of-invalid-entries"></a><span data-ttu-id="2b56d-348">Beispiele für ungültige Einträge</span><span class="sxs-lookup"><span data-stu-id="2b56d-348">Examples of invalid entries</span></span>

<span data-ttu-id="2b56d-349">Die folgenden Einträge sind ungültig:</span><span class="sxs-lookup"><span data-stu-id="2b56d-349">The following entries are invalid:</span></span>

- <span data-ttu-id="2b56d-350">**Fehlende oder ungültige Domänenwerte**:</span><span class="sxs-lookup"><span data-stu-id="2b56d-350">**Missing or invalid domain values**:</span></span>

  - <span data-ttu-id="2b56d-351">contoso</span><span class="sxs-lookup"><span data-stu-id="2b56d-351">contoso</span></span>
  - <span data-ttu-id="2b56d-352">\*.contoso.\*</span><span class="sxs-lookup"><span data-stu-id="2b56d-352">\*.contoso.\*</span></span>
  - <span data-ttu-id="2b56d-353">\*.com</span><span class="sxs-lookup"><span data-stu-id="2b56d-353">\*.com</span></span>
  - <span data-ttu-id="2b56d-354">\*.pdf</span><span class="sxs-lookup"><span data-stu-id="2b56d-354">\*.pdf</span></span>

- <span data-ttu-id="2b56d-355">**Platzhalter für Text oder ohne Abstandszeichen**:</span><span class="sxs-lookup"><span data-stu-id="2b56d-355">**Wildcard on text or without spacing characters**:</span></span>

  - <span data-ttu-id="2b56d-356">\*contoso.com</span><span class="sxs-lookup"><span data-stu-id="2b56d-356">\*contoso.com</span></span>
  - <span data-ttu-id="2b56d-357">contoso.com\*</span><span class="sxs-lookup"><span data-stu-id="2b56d-357">contoso.com\*</span></span>
  - <span data-ttu-id="2b56d-358">\*1.2.3.4</span><span class="sxs-lookup"><span data-stu-id="2b56d-358">\*1.2.3.4</span></span>
  - <span data-ttu-id="2b56d-359">1.2.3.4\*</span><span class="sxs-lookup"><span data-stu-id="2b56d-359">1.2.3.4\*</span></span>
  - <span data-ttu-id="2b56d-360">contoso.com/a\*</span><span class="sxs-lookup"><span data-stu-id="2b56d-360">contoso.com/a\*</span></span>
  - <span data-ttu-id="2b56d-361">contoso.com/ab\*</span><span class="sxs-lookup"><span data-stu-id="2b56d-361">contoso.com/ab\*</span></span>

- <span data-ttu-id="2b56d-362">**IP-Adressen mit Ports**:</span><span class="sxs-lookup"><span data-stu-id="2b56d-362">**IP addresses with ports**:</span></span>

  - <span data-ttu-id="2b56d-363">contoso.com:443</span><span class="sxs-lookup"><span data-stu-id="2b56d-363">contoso.com:443</span></span>
  - <span data-ttu-id="2b56d-364">abc.contoso.com:25</span><span class="sxs-lookup"><span data-stu-id="2b56d-364">abc.contoso.com:25</span></span>

- <span data-ttu-id="2b56d-365">**Nicht beschreibende Platzhalter**:</span><span class="sxs-lookup"><span data-stu-id="2b56d-365">**Non-descriptive wildcards**:</span></span>

  - \*
  - <span data-ttu-id="2b56d-366">\*.\*</span><span class="sxs-lookup"><span data-stu-id="2b56d-366">\*.\*</span></span>

- <span data-ttu-id="2b56d-367">**Mittlere Platzhalter**:</span><span class="sxs-lookup"><span data-stu-id="2b56d-367">**Middle wildcards**:</span></span>

  - <span data-ttu-id="2b56d-368">conto \* so.com</span><span class="sxs-lookup"><span data-stu-id="2b56d-368">conto\*so.com</span></span>
  - <span data-ttu-id="2b56d-369">conto~so.com</span><span class="sxs-lookup"><span data-stu-id="2b56d-369">conto~so.com</span></span>

- <span data-ttu-id="2b56d-370">**Doppelte Platzhalter**</span><span class="sxs-lookup"><span data-stu-id="2b56d-370">**Double wildcards**</span></span>

  - <span data-ttu-id="2b56d-371">contoso.com/\*\*</span><span class="sxs-lookup"><span data-stu-id="2b56d-371">contoso.com/\*\*</span></span>
  - <span data-ttu-id="2b56d-372">contoso.com/\*/\*</span><span class="sxs-lookup"><span data-stu-id="2b56d-372">contoso.com/\*/\*</span></span>
