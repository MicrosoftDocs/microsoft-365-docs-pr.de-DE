---
title: Verwalten Ihrer zulässigen und blockierten URLs und Dateien in der Liste "Mandanten zulassen/blockieren"
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
ROBOTS: NOINDEX, NOFOLLOW
description: Administratoren können erfahren, wie Sie URL-und Dateieinträge in der Liste Mandanten-Allow/Block im Security & Compliance Center konfigurieren.
ms.openlocfilehash: 742a44c7ed63c8a3037e2ada295c94f89afa9c93
ms.sourcegitcommit: df6cc8c2eb2a65c7668f2953b0f7ec783a596d15
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/13/2020
ms.locfileid: "44726816"
---
# <a name="manage-urls-and-files-in-the-tenant-allowblock-list"></a><span data-ttu-id="1cf42-103">Verwalten von URLs und Dateien in der Liste "Mandanten zulassen/blockieren"</span><span class="sxs-lookup"><span data-stu-id="1cf42-103">Manage URLs and files in the Tenant Allow/Block List</span></span>

> [!NOTE]
> <span data-ttu-id="1cf42-104">Die in diesem Thema beschriebenen Funktionen befinden sich in der Vorschau, können sich ändern und sind nicht in allen Organisationen verfügbar.</span><span class="sxs-lookup"><span data-stu-id="1cf42-104">The features described in this topic are in Preview, are subject to change, and are not available in all organizations.</span></span>

<span data-ttu-id="1cf42-105">In Microsoft 365-Organisationen mit Postfächern in Exchange Online-oder eigenständigen Exchange Online Schutzorganisationen (EoP) ohne Exchange Online Postfächer können Sie mit dem EoP-Filter Urteil nicht einverstanden sein.</span><span class="sxs-lookup"><span data-stu-id="1cf42-105">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, you might disagree with the EOP filtering verdict.</span></span> <span data-ttu-id="1cf42-106">Beispielsweise kann eine gute Nachricht als "schlecht" markiert werden (ein falsch positives Ergebnis), oder es ist möglicherweise eine ungültige Meldung zulässig (ein falsches negativ).</span><span class="sxs-lookup"><span data-stu-id="1cf42-106">For example, a good message might be marked as bad (a false positive), or a bad message might be allowed through (a false negative).</span></span>

<span data-ttu-id="1cf42-107">In der Liste Mandanten-Allow/Block im Security & Compliance Center haben Sie die Möglichkeit, die Microsoft 365-Filter Urteile manuell außer Kraft zu setzen.</span><span class="sxs-lookup"><span data-stu-id="1cf42-107">The Tenant Allow/Block List in the Security & Compliance Center gives you a way to manually override the Microsoft 365 filtering verdicts.</span></span> <span data-ttu-id="1cf42-108">Die Mandanten-Zulassungs-und Sperrliste wird während des e-Mail-Flusses und zum Zeitpunkt der Benutzerklicks verwendet.</span><span class="sxs-lookup"><span data-stu-id="1cf42-108">The Tenant Allow/Block List is used during mail flow and at the time of user clicks.</span></span> <span data-ttu-id="1cf42-109">In der Liste Mandanten-Allow/Block können Sie URLs und Dateien angeben, die zugelassen oder blockiert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="1cf42-109">You can specify URLs and files to allow or block in the Tenant Allow/Block List.</span></span>

<span data-ttu-id="1cf42-110">In diesem Thema wird beschrieben, wie Sie Einträge in der Liste "Allow/Block" des Mandanten im Security & Compliance Center oder in PowerShell (Exchange Online PowerShell für Microsoft 365-Organisationen mit Postfächern in Exchange Online; eigenständige EoP PowerShell für Organisationen ohne Exchange Online Postfächer) konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="1cf42-110">This topic describes how to configure entries in the Tenant Allow/Block List in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="1cf42-111">Was sollten Sie wissen, bevor Sie beginnen?</span><span class="sxs-lookup"><span data-stu-id="1cf42-111">What do you need to know before you begin?</span></span>

- <span data-ttu-id="1cf42-112">Sie öffnen das Security & Compliance Center unter <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="1cf42-112">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="1cf42-113">Wenn Sie direkt zur Seite **Mandanten-Zulassungs-und Sperrliste** wechseln möchten, verwenden Sie <https://protection.office.com/tenantAllowBlockList> .</span><span class="sxs-lookup"><span data-stu-id="1cf42-113">To go directly to the **Tenant Allow/Block List** page, use <https://protection.office.com/tenantAllowBlockList>.</span></span>

- <span data-ttu-id="1cf42-114">Sie geben Dateien mithilfe des SHA256-Hash Werts der Datei an.</span><span class="sxs-lookup"><span data-stu-id="1cf42-114">You specify files by using the SHA256 hash value of the file.</span></span> <span data-ttu-id="1cf42-115">Um den SHA256-Hashwert einer Datei in Windows zu suchen, führen Sie den folgenden Befehl an einer Eingabeaufforderung aus:</span><span class="sxs-lookup"><span data-stu-id="1cf42-115">To find the SHA256 hash value of a file in Windows, run the following command in a Command Prompt:</span></span>

  ```dos
  certutil.exe -hashfile "<Path>\<Filename>" SHA256
  ```

  <span data-ttu-id="1cf42-116">Ein Beispielwert ist `768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3a` .</span><span class="sxs-lookup"><span data-stu-id="1cf42-116">An example value is `768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3a`.</span></span> <span data-ttu-id="1cf42-117">PHash-Werte (wahrnehmbarer Hash) sind nicht zulässig.</span><span class="sxs-lookup"><span data-stu-id="1cf42-117">Perceptual hash (pHash) values are not allowed.</span></span>

- <span data-ttu-id="1cf42-118">Die verfügbaren URL-Werte werden in der [URL-Syntax für den Abschnitt Mandanten-Zulassungs-und Sperrliste](#url-syntax-for-the-tenant-allowblock-list) weiter unten in diesem Thema beschrieben.</span><span class="sxs-lookup"><span data-stu-id="1cf42-118">The available URL values are described in the [URL syntax for the Tenant Allow/Block List](#url-syntax-for-the-tenant-allowblock-list) section later in this topic.</span></span>

- <span data-ttu-id="1cf42-119">Die Liste Mandanten Allow/Block erlaubt maximal 500 Einträge für URLs und 500 Einträge für Datei Hashs.</span><span class="sxs-lookup"><span data-stu-id="1cf42-119">The Tenant Allow/Block List allows a maximum of 500 entries for URLs, and 500 entries for file hashes.</span></span>

- <span data-ttu-id="1cf42-120">Ein Eintrag sollte innerhalb von 15 Minuten aktiv sein.</span><span class="sxs-lookup"><span data-stu-id="1cf42-120">An entry should be active within 15 minutes.</span></span>

- <span data-ttu-id="1cf42-121">Block Einträge haben Vorrang vor Zulassungs Einträgen.</span><span class="sxs-lookup"><span data-stu-id="1cf42-121">Block entries take precedence over allow entries.</span></span>

- <span data-ttu-id="1cf42-122">Standardmäßig laufen Einträge in der Liste Mandanten-Allow/Block nach 30 Tagen ab.</span><span class="sxs-lookup"><span data-stu-id="1cf42-122">By default, entries in the Tenant Allow/Block List will expire after 30 days.</span></span> <span data-ttu-id="1cf42-123">Sie können ein Datum angeben oder festlegen, dass es nie abläuft.</span><span class="sxs-lookup"><span data-stu-id="1cf42-123">You can specify a date or set them to never expire.</span></span>

- <span data-ttu-id="1cf42-124">Wie Sie eine Verbindung mit Exchange Online PowerShell herstellen, finden Sie unter [Herstellen einer Verbindung mit Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="1cf42-124">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="1cf42-125">Informationen zum Herstellen einer Verbindung mit dem eigenständigen Exchange Online Protection PowerShell finden Sie unter [Verbinden mit PowerShell in Exchange Online Protection](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="1cf42-125">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="1cf42-126">Sie müssen Berechtigungen zugewiesen haben, bevor Sie die Verfahren in diesem Thema ausführen können:</span><span class="sxs-lookup"><span data-stu-id="1cf42-126">You need to be assigned permissions before you can do the procedures in this topic:</span></span>

  - <span data-ttu-id="1cf42-127">Zum Hinzufügen und Entfernen von Werten aus der Liste Mandanten-Allow/Block müssen Sie Mitglied einer der folgenden Rollengruppen sein:</span><span class="sxs-lookup"><span data-stu-id="1cf42-127">To add and remove values from the Tenant Allow/Block List, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="1cf42-128">**Organisationsverwaltung** oder **Sicherheits Administrator** im [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="1cf42-128">**Organization Management** or **Security Administrator** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="1cf42-129">**Organisationsverwaltung** oder **Hygiene Verwaltung** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span><span class="sxs-lookup"><span data-stu-id="1cf42-129">**Organization Management** or **Hygiene Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

  - <span data-ttu-id="1cf42-130">Für den schreibgeschützten Zugriff auf die Liste der Mandanten zulassen/blockieren müssen Sie Mitglied einer der folgenden Rollengruppen sein:</span><span class="sxs-lookup"><span data-stu-id="1cf42-130">For read-only access to the Tenant Allow/Block List, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="1cf42-131">**Sicherheits Leser** im [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="1cf42-131">**Security Reader** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="1cf42-132">**Organisationsverwaltung mit Ansichts** Schutz in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span><span class="sxs-lookup"><span data-stu-id="1cf42-132">**View-Only Organization Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

## <a name="use-the-security--compliance-center-to-create-url-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="1cf42-133">Verwenden Sie das Security & Compliance Center, um URL-Einträge in der Liste Mandanten-Allow/Block zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="1cf42-133">Use the Security & Compliance Center to create URL entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="1cf42-134">Ausführliche Informationen zur Syntax für URL-Einträge finden Sie weiter unten in diesem Thema in der [URL-Syntax für den Abschnitt Allow/Block List für Mandanten](#url-syntax-for-the-tenant-allowblock-list) .</span><span class="sxs-lookup"><span data-stu-id="1cf42-134">For details about the syntax for URL entries, see the [URL syntax for the Tenant Allow/Block List](#url-syntax-for-the-tenant-allowblock-list) section later in this topic.</span></span>

1. <span data-ttu-id="1cf42-135">Wechseln Sie im Security & Compliance Center zu **Bedrohungs Verwaltungs** \> **Richtlinie** \> **Mandanten-Zulassungs-/Sperrlisten**.</span><span class="sxs-lookup"><span data-stu-id="1cf42-135">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="1cf42-136">Überprüfen Sie auf der Seite **Mandantenliste zulassen/blockieren** , dass die Registerkarte **URLs** ausgewählt ist, und klicken Sie dann auf **Hinzufügen** .</span><span class="sxs-lookup"><span data-stu-id="1cf42-136">On the **Tenant Allow/Block List** page, verify that the **URLs** tab is selected, and then click **Add**</span></span>

3. <span data-ttu-id="1cf42-137">Konfigurieren Sie im Flyout **neue URLs hinzufügen** , das angezeigt wird, die folgenden Einstellungen:</span><span class="sxs-lookup"><span data-stu-id="1cf42-137">In the **Add new URLs** flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="1cf42-138">**URLs mit Platzhaltern hinzufügen**: Geben Sie eine URL pro Reihe bis maximal 20 ein.</span><span class="sxs-lookup"><span data-stu-id="1cf42-138">**Add URLs with wildcards**: Enter one URL per line, up to a maximum of 20.</span></span>

   - <span data-ttu-id="1cf42-139">**Block/Allow**: Wählen Sie aus, ob die angegebenen URLs **zugelassen** oder **blockiert** werden sollen.</span><span class="sxs-lookup"><span data-stu-id="1cf42-139">**Block/Allow**: Select whether you want to **Allow** or **Block** the specified URLs.</span></span>

   - <span data-ttu-id="1cf42-140">**Nie ablaufen**: führen Sie einen der folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="1cf42-140">**Never expire**: Do one of the following steps:</span></span>

     - <span data-ttu-id="1cf42-141">Stellen Sie sicher, dass die Einstellung deaktiviert ist (deaktivieren ![ ](../../media/scc-toggle-off.png) ), und verwenden Sie das Feld **expires on** , um das Ablaufdatum für die Einträge anzugeben.</span><span class="sxs-lookup"><span data-stu-id="1cf42-141">Verify the setting is turned off (![Toggle off](../../media/scc-toggle-off.png)) and use the **Expires on** box to specify the expiration date for the entries.</span></span>

     <span data-ttu-id="1cf42-142">oder</span><span class="sxs-lookup"><span data-stu-id="1cf42-142">or</span></span>

     - <span data-ttu-id="1cf42-143">Bewegen Sie die Umschaltfläche nach rechts, um die Einträge so zu konfigurieren, dass Sie nie ablaufen:</span><span class="sxs-lookup"><span data-stu-id="1cf42-143">Move the toggle to the right to configure the entries to never expire:</span></span> ![Umschaltfläche ein](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png)<span data-ttu-id="1cf42-145">.</span><span class="sxs-lookup"><span data-stu-id="1cf42-145">.</span></span>

   - <span data-ttu-id="1cf42-146">**Optional Hinweis**: Geben Sie einen beschreibenden Text für die Einträge ein.</span><span class="sxs-lookup"><span data-stu-id="1cf42-146">**Optional note**: Enter descriptive text for the entries.</span></span>

4. <span data-ttu-id="1cf42-147">Wenn Sie fertig sind, klicken Sie auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="1cf42-147">When you're finished, click **Add**.</span></span>

## <a name="use-the-security--compliance-center-to-create-file-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="1cf42-148">Verwenden des Security & Compliance Center zum Erstellen von Dateieinträgen in der Liste "Mandanten zulassen/blockieren"</span><span class="sxs-lookup"><span data-stu-id="1cf42-148">Use the Security & Compliance Center to create file entries in the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="1cf42-149">Wechseln Sie im Security & Compliance Center zu **Bedrohungs Verwaltungs** \> **Richtlinie** \> **Mandanten-Zulassungs-/Sperrlisten**.</span><span class="sxs-lookup"><span data-stu-id="1cf42-149">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="1cf42-150">Wählen Sie auf der Seite **Mandanten Allow/Block List** die Registerkarte **Dateien** aus, und klicken Sie dann auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="1cf42-150">On the **Tenant Allow/Block List** page, select **Files** tab, and then click **Add**.</span></span>

3. <span data-ttu-id="1cf42-151">Konfigurieren Sie im angezeigten Flyout **neue Dateien hinzufügen** die folgenden Einstellungen:</span><span class="sxs-lookup"><span data-stu-id="1cf42-151">In the **Add new files** flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="1cf42-152">**Datei Hashes hinzufügen**: Geben Sie einen SHA256-Hashwert pro Reihe ein, bis zu einem Maximum von 20.</span><span class="sxs-lookup"><span data-stu-id="1cf42-152">**Add file hashes**: Enter one SHA256 hash value per line, up to a maximum of 20.</span></span>

   - <span data-ttu-id="1cf42-153">**Block/Allow**: Wählen Sie aus, ob die angegebenen Dateien **zugelassen** oder **blockiert** werden sollen.</span><span class="sxs-lookup"><span data-stu-id="1cf42-153">**Block/Allow**: Select whether you want to **Allow** or **Block** the specified files.</span></span>

   - <span data-ttu-id="1cf42-154">**Nie ablaufen**: führen Sie einen der folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="1cf42-154">**Never expire**: Do one of the following steps:</span></span>

     - <span data-ttu-id="1cf42-155">Stellen Sie sicher, dass die Einstellung deaktiviert ist (deaktivieren ![ ](../../media/scc-toggle-off.png) ), und verwenden Sie das Feld **expires on** , um das Ablaufdatum für die Einträge anzugeben.</span><span class="sxs-lookup"><span data-stu-id="1cf42-155">Verify the setting is turned off (![Toggle off](../../media/scc-toggle-off.png)) and use the **Expires on** box to specify the expiration date for the entries.</span></span>

     <span data-ttu-id="1cf42-156">oder</span><span class="sxs-lookup"><span data-stu-id="1cf42-156">or</span></span>

     - <span data-ttu-id="1cf42-157">Bewegen Sie die Umschaltfläche nach rechts, um die Einträge so zu konfigurieren, dass Sie nie ablaufen:</span><span class="sxs-lookup"><span data-stu-id="1cf42-157">Move the toggle to the right to configure the entries to never expire:</span></span> ![Umschaltfläche ein](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png)<span data-ttu-id="1cf42-159">.</span><span class="sxs-lookup"><span data-stu-id="1cf42-159">.</span></span>

   - <span data-ttu-id="1cf42-160">**Optional Hinweis**: Geben Sie einen beschreibenden Text für die Einträge ein.</span><span class="sxs-lookup"><span data-stu-id="1cf42-160">**Optional note**: Enter descriptive text for the entries.</span></span>

4. <span data-ttu-id="1cf42-161">Wenn Sie fertig sind, klicken Sie auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="1cf42-161">When you're finished, click **Add**.</span></span>

## <a name="use-the-security--compliance-center-to-view-url-and-file-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="1cf42-162">Verwenden Sie das Security & Compliance Center, um URL-und Dateieinträge in der Liste Mandanten-Allow/Block anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="1cf42-162">Use the Security & Compliance Center to view URL and file entries in the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="1cf42-163">Wechseln Sie im Security & Compliance Center zu **Bedrohungs Verwaltungs** \> **Richtlinie** \> **Mandanten-Zulassungs-/Sperrlisten**.</span><span class="sxs-lookup"><span data-stu-id="1cf42-163">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="1cf42-164">Wählen Sie die Registerkarte **URLs** oder die Registerkarte **Dateien** aus.</span><span class="sxs-lookup"><span data-stu-id="1cf42-164">Select the **URLs** tab or the **Files** tab.</span></span>

<span data-ttu-id="1cf42-165">Klicken Sie auf die folgenden Spaltenüberschriften, um Sie in aufsteigender oder absteigender Reihenfolge zu sortieren:</span><span class="sxs-lookup"><span data-stu-id="1cf42-165">Click on the following column headings to sort in ascending or descending order:</span></span>

- <span data-ttu-id="1cf42-166">**Wert**: die URL oder der Datei Hash.</span><span class="sxs-lookup"><span data-stu-id="1cf42-166">**Value**: The URL or the file hash.</span></span>
- <span data-ttu-id="1cf42-167">**Aktion**: **blockieren** oder **zulassen**.</span><span class="sxs-lookup"><span data-stu-id="1cf42-167">**Action**: **Block** or **Allow**.</span></span>
- <span data-ttu-id="1cf42-168">**Datum der letzten Aktualisierung**</span><span class="sxs-lookup"><span data-stu-id="1cf42-168">**Last updated date**</span></span>
- <span data-ttu-id="1cf42-169">**Ablaufdatum**</span><span class="sxs-lookup"><span data-stu-id="1cf42-169">**Expiration date**</span></span>
- <span data-ttu-id="1cf42-170">**Hinweis**</span><span class="sxs-lookup"><span data-stu-id="1cf42-170">**Note**</span></span>

<span data-ttu-id="1cf42-171">Klicken Sie auf **Gruppieren** , um die Einträge nach **Aktion** (**blockieren** oder **zulassen**) oder **ohne**zu gruppieren.</span><span class="sxs-lookup"><span data-stu-id="1cf42-171">Click **Group** to group the entries by **Action** (**Block** or **Allow**) or **None**.</span></span>

<span data-ttu-id="1cf42-172">Klicken Sie auf **Suchen**, geben Sie eine URL oder einen Datei Wert ganz oder teilweise ein, und drücken Sie dann die EINGABETASTE, um einen bestimmten Wert zu suchen.</span><span class="sxs-lookup"><span data-stu-id="1cf42-172">Click **Search**, enter all or part of a URL or file value, and then press ENTER to find a specific value.</span></span> <span data-ttu-id="1cf42-173">Wenn Sie fertig sind, klicken Sie auf **Such** ![ Symbol Löschen ](../../media/b6512677-5e7b-42b0-a8a3-3be1d7fa23ee.gif) .</span><span class="sxs-lookup"><span data-stu-id="1cf42-173">When you're finished, click **Clear search** ![Clear search icon](../../media/b6512677-5e7b-42b0-a8a3-3be1d7fa23ee.gif).</span></span>

<span data-ttu-id="1cf42-174">Klicken Sie auf **Filter**.</span><span class="sxs-lookup"><span data-stu-id="1cf42-174">Click **Filter**.</span></span> <span data-ttu-id="1cf42-175">Konfigurieren Sie im angezeigten **Filter** Flyout die folgenden Einstellungen:</span><span class="sxs-lookup"><span data-stu-id="1cf42-175">In the **Filter** flyout that appears, configure any of the following settings:</span></span>

- <span data-ttu-id="1cf42-176">**Aktion**: Wählen Sie **zulassen**, **blockieren** oder beides aus.</span><span class="sxs-lookup"><span data-stu-id="1cf42-176">**Action**: Select **Allow**, **Block** or both.</span></span>

- <span data-ttu-id="1cf42-177">**Läuft nie**ab: Wählen Sie aus (deaktivieren ![ ](../../media/scc-toggle-off.png) ) oder ein (Umschalten ![ ](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png) ) aus.</span><span class="sxs-lookup"><span data-stu-id="1cf42-177">**Never expire**: Select off (![Toggle off](../../media/scc-toggle-off.png)) or on (![Toggle on](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png)).</span></span>

- <span data-ttu-id="1cf42-178">**Letzte Aktualisierung**: Wählen Sie ein Startdatum (von), ein Enddatum (**an**) oder beides**aus**.</span><span class="sxs-lookup"><span data-stu-id="1cf42-178">**Last updated**: Select a start date (**From**), an end date (**To**) or both.</span></span>

- <span data-ttu-id="1cf42-179">**Ablaufdatum**: Wählen Sie ein Startdatum (von), ein Enddatum (**an**) oder beides**aus**.</span><span class="sxs-lookup"><span data-stu-id="1cf42-179">**Expiration date**: Select a start date (**From**), an end date (**To**) or both.</span></span>

<span data-ttu-id="1cf42-180">Wenn Sie fertig sind, klicken Sie auf über **nehmen**.</span><span class="sxs-lookup"><span data-stu-id="1cf42-180">When you're finished, click **Apply**.</span></span>

<span data-ttu-id="1cf42-181">Wenn Sie vorhandene Filter löschen möchten, klicken Sie auf **Filter**, und klicken Sie im daraufhin angezeigten **Filter** Flyout auf Filter **Löschen**.</span><span class="sxs-lookup"><span data-stu-id="1cf42-181">To clear existing filters, click **Filter**, and in the **Filter** flyout that appears, click **Clear filters**.</span></span>

## <a name="use-the-security--compliance-center-to-modify-url-and-file-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="1cf42-182">Verwenden des Security & Compliance Center zum Ändern von URL-und Dateieinträgen in der Liste Mandanten-Allow/Block</span><span class="sxs-lookup"><span data-stu-id="1cf42-182">Use the Security & Compliance Center to modify URL and file entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="1cf42-183">Sie können den URL-Wert oder den Dateiwert selbst nicht ändern.</span><span class="sxs-lookup"><span data-stu-id="1cf42-183">You can't modify the URL or file value itself.</span></span> <span data-ttu-id="1cf42-184">Stattdessen müssen Sie den Eintrag löschen und neu erstellen.</span><span class="sxs-lookup"><span data-stu-id="1cf42-184">Instead, you need to delete the entry and recreate it.</span></span>

1. <span data-ttu-id="1cf42-185">Wechseln Sie im Security & Compliance Center zu **Bedrohungs Verwaltungs** \> **Richtlinie** \> **Mandanten-Zulassungs-/Sperrlisten**.</span><span class="sxs-lookup"><span data-stu-id="1cf42-185">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="1cf42-186">Wählen Sie die Registerkarte **URLs** oder die Registerkarte **Dateien** aus.</span><span class="sxs-lookup"><span data-stu-id="1cf42-186">Select the **URLs** tab or the **Files** tab.</span></span>

3. <span data-ttu-id="1cf42-187">Wählen Sie den Eintrag aus, den Sie ändern möchten, und klicken Sie dann auf Bearbeitungssymbol **Bearbeiten** ![ ](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) .</span><span class="sxs-lookup"><span data-stu-id="1cf42-187">Select the entry that you want to modify, and then click **Edit** ![Edit icon](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png).</span></span>

4. <span data-ttu-id="1cf42-188">Konfigurieren Sie im Flyout, das angezeigt wird, die folgenden Einstellungen:</span><span class="sxs-lookup"><span data-stu-id="1cf42-188">In the flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="1cf42-189">**Blockieren/zulassen**: Wählen Sie **zulassen** oder **blockieren**aus.</span><span class="sxs-lookup"><span data-stu-id="1cf42-189">**Block/Allow**: Select **Allow** or **Block**.</span></span>

   - <span data-ttu-id="1cf42-190">**Nie ablaufen**: führen Sie einen der folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="1cf42-190">**Never expire**: Do one of the following steps:</span></span>

     - <span data-ttu-id="1cf42-191">Stellen Sie sicher, dass die Einstellung deaktiviert ist (deaktivieren ![ ](../../media/scc-toggle-off.png) ), und verwenden Sie das Feld **expires on** , um das Ablaufdatum für den Eintrag anzugeben.</span><span class="sxs-lookup"><span data-stu-id="1cf42-191">Verify the setting is turned off (![Toggle off](../../media/scc-toggle-off.png)) and use the **Expires on** box to specify the expiration date for the entry.</span></span>

     <span data-ttu-id="1cf42-192">oder</span><span class="sxs-lookup"><span data-stu-id="1cf42-192">or</span></span>

     - <span data-ttu-id="1cf42-193">Bewegen Sie die Umschaltfläche nach rechts, um den Eintrag so zu konfigurieren, dass er nie abläuft:</span><span class="sxs-lookup"><span data-stu-id="1cf42-193">Move the toggle to the right to configure the entry to never expire:</span></span> ![Umschaltfläche ein](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png)<span data-ttu-id="1cf42-195">.</span><span class="sxs-lookup"><span data-stu-id="1cf42-195">.</span></span>

   - <span data-ttu-id="1cf42-196">**Optional Hinweis**: Geben Sie einen beschreibenden Text für den Eintrag ein.</span><span class="sxs-lookup"><span data-stu-id="1cf42-196">**Optional note**: Enter descriptive text for the entry.</span></span>

5. <span data-ttu-id="1cf42-197">Klicken Sie nach Abschluss des Vorgangs auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="1cf42-197">When you're finished, click **Save**.</span></span>

## <a name="use-the-security--compliance-center-to-remove-url-and-file-entries-from-the-tenant-allowblock-list"></a><span data-ttu-id="1cf42-198">Verwenden des Security & Compliance Center zum Entfernen von URL-und Dateieinträgen aus der Liste Mandanten-Allow/Block</span><span class="sxs-lookup"><span data-stu-id="1cf42-198">Use the Security & Compliance Center to remove URL and file entries from the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="1cf42-199">Wechseln Sie im Security & Compliance Center zu **Bedrohungs Verwaltungs** \> **Richtlinie** \> **Mandanten-Zulassungs-/Sperrlisten**.</span><span class="sxs-lookup"><span data-stu-id="1cf42-199">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="1cf42-200">Wählen Sie die Registerkarte **URLs** oder die Registerkarte **Dateien** aus.</span><span class="sxs-lookup"><span data-stu-id="1cf42-200">Select the **URLs** tab or the **Files** tab.</span></span>

3. <span data-ttu-id="1cf42-201">Wählen Sie den Eintrag aus, den Sie entfernen möchten, und klicken Sie **dann auf Delete** ![ Delete Icon ](../../media/87565fbb-5147-4f22-9ed7-1c18ce664392.png) .</span><span class="sxs-lookup"><span data-stu-id="1cf42-201">Select the entry that you want to remove, and then click **Delete** ![Delete icon](../../media/87565fbb-5147-4f22-9ed7-1c18ce664392.png).</span></span>

4. <span data-ttu-id="1cf42-202">Klicken Sie im angezeigten Warndialogfeld auf **Löschen**.</span><span class="sxs-lookup"><span data-stu-id="1cf42-202">In the warning dialog that appears, click **Delete**.</span></span>

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-the-tenant-allowblock-list"></a><span data-ttu-id="1cf42-203">Verwenden Exchange Online PowerShell oder eigenständiger EoP PowerShell zum Konfigurieren der Liste "Mandanten zulassen/blockieren"</span><span class="sxs-lookup"><span data-stu-id="1cf42-203">Use Exchange Online PowerShell or standalone EOP PowerShell to configure the Tenant Allow/Block List</span></span>

### <a name="use-powershell-to-add-url-and-file-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="1cf42-204">Verwenden von PowerShell zum Hinzufügen von URL-und Dateieinträgen in der Liste "Mandanten zulassen/blockieren"</span><span class="sxs-lookup"><span data-stu-id="1cf42-204">Use PowerShell to add URL and file entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="1cf42-205">Verwenden Sie die folgende Syntax, um URL-und Dateieinträge in der Liste Mandanten Allow/Block hinzuzufügen:</span><span class="sxs-lookup"><span data-stu-id="1cf42-205">To add URL and file entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
New-TenantAllowBlockListItems -ListType <Url | FileHash> -Action <Allow | Block> -Entries <String[]> [-ExpirationDate <DateTime>] [-NoExpiration] [-Notes <String>]
```

<span data-ttu-id="1cf42-206">In diesem Beispiel wird ein URL-Sperreintrag für contoso.com und alle Unterdomänen hinzugefügt (beispielsweise contoso.com, www.contoso.com und XYZ.ABC.contoso.com).</span><span class="sxs-lookup"><span data-stu-id="1cf42-206">This example adds a URL block entry for contoso.com and all subdomains (for example, contoso.com, www.contoso.com, and xyz.abc.contoso.com).</span></span> <span data-ttu-id="1cf42-207">Da die Parameter ExpirationDate oder NOEXPIRE nicht verwendet wurden, läuft der Eintrag nach 30 Tagen ab.</span><span class="sxs-lookup"><span data-stu-id="1cf42-207">Because we didn't use the ExpirationDate or NoExpiration parameters, the entry expires after 30 days.</span></span>

```powershell
New-TenantAllowBlockListItem -ListType Url -Action Block -Entries ~contoso.com
```

```powershell
New-TenantAllowBlockListItem -ListType FileHash -Action Allow -Entries "768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3","2c0a35409ff0873cfa28b70b8224e9aca2362241c1f0ed6f622fef8d4722fd9a" -NoExpiration
```

<span data-ttu-id="1cf42-208">In diesem Beispiel wird der Eintrag "Datei zulassen" für die angegebenen Dateien hinzugefügt, die nie ablaufen.</span><span class="sxs-lookup"><span data-stu-id="1cf42-208">This example adds a file allow entry for the specified files that never expires.</span></span>

<span data-ttu-id="1cf42-209">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [New-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/new-tenantallowblocklistitems).</span><span class="sxs-lookup"><span data-stu-id="1cf42-209">For detailed syntax and parameter information, see [New-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/new-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-view-url-and-file-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="1cf42-210">Verwenden von PowerShell zum Anzeigen von URL-und Dateieinträgen in der Liste "Mandanten zulassen/blockieren"</span><span class="sxs-lookup"><span data-stu-id="1cf42-210">Use PowerShell to view URL and file entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="1cf42-211">Verwenden Sie die folgende Syntax, um URL-und Dateieinträge in der Liste Mandanten Allow/Block anzuzeigen:</span><span class="sxs-lookup"><span data-stu-id="1cf42-211">To view URL and file entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType <Url | FileHash> [-Entry <URLValue | FileHashValue>] [-Action <Allow | Block>] [-ExpirationDate <DateTime>] [-NoExpiration]
```

<span data-ttu-id="1cf42-212">In diesem Beispiel werden alle blockierten URLs zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="1cf42-212">This example returns all blocked URLs.</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType Url -Action Block
```

<span data-ttu-id="1cf42-213">In diesem Beispiel werden Informationen für den angegebenen Datei Hash Wert zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="1cf42-213">This example returns information for the specified file hash value.</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType FileHash -Entry "9f86d081884c7d659a2feaa0c55ad015a3bf4f1b2b0b822cd15d6c15b0f00a08"
```

<span data-ttu-id="1cf42-214">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Get-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/get-tenantallowblocklistitems).</span><span class="sxs-lookup"><span data-stu-id="1cf42-214">For detailed syntax and parameter information, see [Get-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/get-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-modify-url-and-file-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="1cf42-215">Verwenden von PowerShell zum Ändern von URL-und Dateieinträgen in der Liste "Mandanten zulassen/blockieren"</span><span class="sxs-lookup"><span data-stu-id="1cf42-215">Use PowerShell to modify URL and file entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="1cf42-216">Sie können den URL-Wert oder den Dateiwert selbst nicht ändern.</span><span class="sxs-lookup"><span data-stu-id="1cf42-216">You can't modify the URL or file value itself.</span></span> <span data-ttu-id="1cf42-217">Stattdessen müssen Sie den Eintrag löschen und neu erstellen.</span><span class="sxs-lookup"><span data-stu-id="1cf42-217">Instead, you need to delete the entry and recreate it.</span></span>

<span data-ttu-id="1cf42-218">Verwenden Sie die folgende Syntax, um URL-und Dateieinträge in der Liste Mandanten Allow/Block zu ändern:</span><span class="sxs-lookup"><span data-stu-id="1cf42-218">To modify URL and file entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Set-TenantAllowBlockListItems -ListType <Url | FileHash> -Ids <"Id1","Id2",..."IdN"> [-Action <Allow | Block>] [-ExpirationDate <DateTime>] [-NoExpiration] [-Notes <String>]
```

<span data-ttu-id="1cf42-219">In diesem Beispiel wird das Ablaufdatum des angegebenen Eintrags geändert.</span><span class="sxs-lookup"><span data-stu-id="1cf42-219">This example changes the expiration date of the specified entry.</span></span>

```powershell
Set-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSRAAAA" -ExpirationDate (Get-Date "5/30/2020 9:30 AM").ToUniversalTime()
```

<span data-ttu-id="1cf42-220">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Sets-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/set-tenantallowblocklistitems).</span><span class="sxs-lookup"><span data-stu-id="1cf42-220">For detailed syntax and parameter information, see [Set-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/set-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-remove-url-and-file-entries-from-the-tenant-allowblock-list"></a><span data-ttu-id="1cf42-221">Verwenden von PowerShell zum Entfernen von URL-und Dateieinträgen aus der Liste "Mandanten zulassen/blockieren"</span><span class="sxs-lookup"><span data-stu-id="1cf42-221">Use PowerShell to remove URL and file entries from the Tenant Allow/Block List</span></span>

<span data-ttu-id="1cf42-222">Verwenden Sie die folgende Syntax, um URL-und Dateieinträge aus der Liste Mandanten Allow/Block zu entfernen:</span><span class="sxs-lookup"><span data-stu-id="1cf42-222">To remove URL and file entries from the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Remove-TenantAllowBlockListItems -ListType <Url | FileHash> -Ids <"Id1","Id2",..."IdN">
```

<span data-ttu-id="1cf42-223">In diesem Beispiel wird der angegebene URL-Eintrag aus der Liste Mandanten-Allow/Block entfernt.</span><span class="sxs-lookup"><span data-stu-id="1cf42-223">This example removes the specified URL entry from the Tenant Allow/Block List.</span></span>

```powershell
Remove-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSPAAAA0"
```

<span data-ttu-id="1cf42-224">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Remove-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/remove-tenantallowblocklistitems).</span><span class="sxs-lookup"><span data-stu-id="1cf42-224">For detailed syntax and parameter information, see [Remove-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/remove-tenantallowblocklistitems).</span></span>

## <a name="url-syntax-for-the-tenant-allowblock-list"></a><span data-ttu-id="1cf42-225">URL-Syntax für die Liste "Mandanten zulassen/blockieren"</span><span class="sxs-lookup"><span data-stu-id="1cf42-225">URL syntax for the Tenant Allow/Block List</span></span>

- <span data-ttu-id="1cf42-226">IP4v-und IPv6-Adressen sind zulässig, TCP/UDP-Ports jedoch nicht.</span><span class="sxs-lookup"><span data-stu-id="1cf42-226">IP4v and IPv6 addresses are allowed, but TCP/UDP ports are not.</span></span>

- <span data-ttu-id="1cf42-227">Dateierweiterungen sind nicht zulässig (beispielsweise test.pdf).</span><span class="sxs-lookup"><span data-stu-id="1cf42-227">Filename extensions are not allowed (for example, test.pdf).</span></span>

- <span data-ttu-id="1cf42-228">Unicode wird nicht unterstützt, aber Punycode ist.</span><span class="sxs-lookup"><span data-stu-id="1cf42-228">Unicode is not supported, but Punycode is.</span></span>

- <span data-ttu-id="1cf42-229">Hostnames sind zulässig, wenn alle der folgenden Aussagen zutreffen:</span><span class="sxs-lookup"><span data-stu-id="1cf42-229">Hostnames are allowed if all of the following statements are true:</span></span>

  - <span data-ttu-id="1cf42-230">Der Hostname enthält einen Punkt.</span><span class="sxs-lookup"><span data-stu-id="1cf42-230">The hostname contains a period.</span></span>
  - <span data-ttu-id="1cf42-231">Es gibt mindestens ein Zeichen auf der linken Seite des Punkts.</span><span class="sxs-lookup"><span data-stu-id="1cf42-231">There is at least one character to the left of the period.</span></span>
  - <span data-ttu-id="1cf42-232">Rechts vom Punkt befinden sich mindestens zwei Zeichen.</span><span class="sxs-lookup"><span data-stu-id="1cf42-232">There are at least two characters to the right of the period.</span></span>

  <span data-ttu-id="1cf42-233">Beispielsweise `t.co` ist zulässig; `.com` oder ist `contoso.` nicht zulässig.</span><span class="sxs-lookup"><span data-stu-id="1cf42-233">For example, `t.co` is allowed; `.com` or `contoso.` are not allowed.</span></span>

- <span data-ttu-id="1cf42-234">Unterpfade sind nicht impliziert.</span><span class="sxs-lookup"><span data-stu-id="1cf42-234">Subpaths are not implied.</span></span>

  <span data-ttu-id="1cf42-235">Enthält beispielsweise `contoso.com` nicht `contoso.com/a` .</span><span class="sxs-lookup"><span data-stu-id="1cf42-235">For example, `contoso.com` does not include `contoso.com/a`.</span></span>

- <span data-ttu-id="1cf42-236">Platzhalterzeichen (\*) sind in den folgenden Szenarien zulässig:</span><span class="sxs-lookup"><span data-stu-id="1cf42-236">Wildcards (\*) are allowed in the following scenarios:</span></span>

  - <span data-ttu-id="1cf42-237">Auf einen linken Platzhalter muss ein Punkt folgen, um eine Unterdomäne anzugeben.</span><span class="sxs-lookup"><span data-stu-id="1cf42-237">A left wildcard must be followed by a period to specify a subdomain.</span></span>

    <span data-ttu-id="1cf42-238">Beispielsweise `*.contoso.com` ist zulässig; `*contoso.com` ist nicht zulässig.</span><span class="sxs-lookup"><span data-stu-id="1cf42-238">For example, `*.contoso.com` is allowed; `*contoso.com` is not allowed.</span></span>

  - <span data-ttu-id="1cf42-239">Ein rechter Platzhalter muss einem Schrägstrich (/) entsprechen, um einen Pfad anzugeben.</span><span class="sxs-lookup"><span data-stu-id="1cf42-239">A right wildcard must follow a forward slash (/) to specify a path.</span></span>

    <span data-ttu-id="1cf42-240">Beispielsweise `contoso.com/*` ist zulässig; `contoso.com*` oder ist `contoso.com/ab*` nicht zulässig.</span><span class="sxs-lookup"><span data-stu-id="1cf42-240">For example, `contoso.com/*` is allowed; `contoso.com*` or `contoso.com/ab*` are not allowed.</span></span>

  - <span data-ttu-id="1cf42-241">Alle untergeordneten Pfade sind nicht durch einen richtigen Platzhalter impliziert.</span><span class="sxs-lookup"><span data-stu-id="1cf42-241">All subpaths are not implied by a right wildcard.</span></span>

    <span data-ttu-id="1cf42-242">Enthält beispielsweise `contoso.com/*` nicht `contoso.com/a` .</span><span class="sxs-lookup"><span data-stu-id="1cf42-242">For example, `contoso.com/*` does not include `contoso.com/a`.</span></span>

  - <span data-ttu-id="1cf42-243">`*.com*`ist ungültig (keine auflösbare Domäne, und der Rechte Platzhalter folgt keinem Schrägstrich).</span><span class="sxs-lookup"><span data-stu-id="1cf42-243">`*.com*` is invalid (not a resolvable domain and the right wildcard does not follow a forward slash).</span></span>

  - <span data-ttu-id="1cf42-244">Platzhalter sind in IP-Adressen nicht zulässig.</span><span class="sxs-lookup"><span data-stu-id="1cf42-244">Wildcards are not allowed in IP addresses.</span></span>

- <span data-ttu-id="1cf42-245">Das Tildezeichen (~) steht in den folgenden Szenarien zur Verfügung:</span><span class="sxs-lookup"><span data-stu-id="1cf42-245">The tilde (~) character is available in the following scenarios:</span></span>

  - <span data-ttu-id="1cf42-246">Eine linke Tilde impliziert eine Domäne und alle Unterdomänen.</span><span class="sxs-lookup"><span data-stu-id="1cf42-246">A left tilde implies a domain and all subdomains.</span></span>

    <span data-ttu-id="1cf42-247">Beispielsweise `~contoso.com` enthält `contoso.com` und `*.contoso.com` .</span><span class="sxs-lookup"><span data-stu-id="1cf42-247">For example `~contoso.com` includes `contoso.com` and `*.contoso.com`.</span></span>

- <span data-ttu-id="1cf42-248">URL-Einträge, die Protokolle enthalten (beispielsweise,, `http://` `https://` oder `ftp://` ) schlagen fehl, da URL-Einträge auf alle Protokolle angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="1cf42-248">URL entries that contain protocols (for example, `http://`, `https://`, or `ftp://`) will fail, because URL entries apply to all protocols.</span></span>

- <span data-ttu-id="1cf42-249">Ein Benutzername oder ein Kennwort werden nicht unterstützt oder erforderlich.</span><span class="sxs-lookup"><span data-stu-id="1cf42-249">A username or password aren't supported or required.</span></span>

- <span data-ttu-id="1cf42-250">Anführungszeichen (' oder ') sind ungültige Zeichen.</span><span class="sxs-lookup"><span data-stu-id="1cf42-250">Quotes (' or ") are invalid characters.</span></span>

- <span data-ttu-id="1cf42-251">Eine URL sollte nach Möglichkeit alle Umleitungen enthalten.</span><span class="sxs-lookup"><span data-stu-id="1cf42-251">A URL should include all redirects where possible.</span></span>

### <a name="url-entry-scenarios"></a><span data-ttu-id="1cf42-252">URL-Eintrags Szenarien</span><span class="sxs-lookup"><span data-stu-id="1cf42-252">URL entry scenarios</span></span>

<span data-ttu-id="1cf42-253">In den folgenden Abschnitten werden gültige URL-Einträge und ihre Ergebnisse beschrieben.</span><span class="sxs-lookup"><span data-stu-id="1cf42-253">Valid URL entries and their results are described in the following sections.</span></span>

#### <a name="scenario-no-wildcards"></a><span data-ttu-id="1cf42-254">Szenario: keine Platzhalter</span><span class="sxs-lookup"><span data-stu-id="1cf42-254">Scenario: No wildcards</span></span>

<span data-ttu-id="1cf42-255">**Eintrag**:`contoso.com`</span><span class="sxs-lookup"><span data-stu-id="1cf42-255">**Entry**: `contoso.com`</span></span>

- <span data-ttu-id="1cf42-256">**Übereinstimmung zulassen**: contoso.com</span><span class="sxs-lookup"><span data-stu-id="1cf42-256">**Allow match**: contoso.com</span></span>

- <span data-ttu-id="1cf42-257">**Zulassen nicht abgeglichen**:</span><span class="sxs-lookup"><span data-stu-id="1cf42-257">**Allow not matched**:</span></span>

  - <span data-ttu-id="1cf42-258">abc-contoso.com</span><span class="sxs-lookup"><span data-stu-id="1cf42-258">abc-contoso.com</span></span>
  - <span data-ttu-id="1cf42-259">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="1cf42-259">contoso.com/a</span></span>
  - <span data-ttu-id="1cf42-260">payroll.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1cf42-260">payroll.contoso.com</span></span>
  - <span data-ttu-id="1cf42-261">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="1cf42-261">test.com/contoso.com</span></span>
  - <span data-ttu-id="1cf42-262">test.com/q=contoso.com</span><span class="sxs-lookup"><span data-stu-id="1cf42-262">test.com/q=contoso.com</span></span>
  - <span data-ttu-id="1cf42-263">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1cf42-263">www.contoso.com</span></span>
  - <span data-ttu-id="1cf42-264">www. contoso. com/q = a@contoso. com</span><span class="sxs-lookup"><span data-stu-id="1cf42-264">www.contoso.com/q=a@contoso.com</span></span>
  
- <span data-ttu-id="1cf42-265">**Block Übereinstimmung**:</span><span class="sxs-lookup"><span data-stu-id="1cf42-265">**Block match**:</span></span>

  - <span data-ttu-id="1cf42-266">contoso.com</span><span class="sxs-lookup"><span data-stu-id="1cf42-266">contoso.com</span></span>
  - <span data-ttu-id="1cf42-267">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="1cf42-267">contoso.com/a</span></span>
  - <span data-ttu-id="1cf42-268">payroll.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1cf42-268">payroll.contoso.com</span></span>
  - <span data-ttu-id="1cf42-269">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="1cf42-269">test.com/contoso.com</span></span>
  - <span data-ttu-id="1cf42-270">test.com/q=contoso.com</span><span class="sxs-lookup"><span data-stu-id="1cf42-270">test.com/q=contoso.com</span></span>
  - <span data-ttu-id="1cf42-271">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1cf42-271">www.contoso.com</span></span>
  - <span data-ttu-id="1cf42-272">www. contoso. com/q = a@contoso. com</span><span class="sxs-lookup"><span data-stu-id="1cf42-272">www.contoso.com/q=a@contoso.com</span></span>

- <span data-ttu-id="1cf42-273">**Block nicht abgeglichen**: ABC-contoso.com</span><span class="sxs-lookup"><span data-stu-id="1cf42-273">**Block not matched**: abc-contoso.com</span></span>

#### <a name="scenario-left-wildcard-subdomain"></a><span data-ttu-id="1cf42-274">Szenario: Linker Platzhalter (Unterdomäne)</span><span class="sxs-lookup"><span data-stu-id="1cf42-274">Scenario: Left wildcard (subdomain)</span></span>

<span data-ttu-id="1cf42-275">**Eintrag**:`*.contoso.com`</span><span class="sxs-lookup"><span data-stu-id="1cf42-275">**Entry**: `*.contoso.com`</span></span>

- <span data-ttu-id="1cf42-276">Übereinstimmung und **Block Übereinstimmung** **zulassen** :</span><span class="sxs-lookup"><span data-stu-id="1cf42-276">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="1cf42-277">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1cf42-277">www.contoso.com</span></span>
  - <span data-ttu-id="1cf42-278">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1cf42-278">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="1cf42-279">**Zulassen nicht abgeglichen** und **Block nicht abgeglichen**:</span><span class="sxs-lookup"><span data-stu-id="1cf42-279">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="1cf42-280">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="1cf42-280">123contoso.com</span></span>
  - <span data-ttu-id="1cf42-281">contoso.com</span><span class="sxs-lookup"><span data-stu-id="1cf42-281">contoso.com</span></span>
  - <span data-ttu-id="1cf42-282">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="1cf42-282">test.com/contoso.com</span></span>
  - <span data-ttu-id="1cf42-283">www.contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="1cf42-283">www.contoso.com/abc</span></span>
  
#### <a name="scenario-right-wildcard-at-top-of-path"></a><span data-ttu-id="1cf42-284">Szenario: rechter Platzhalter oben im Pfad</span><span class="sxs-lookup"><span data-stu-id="1cf42-284">Scenario: Right wildcard at top of path</span></span>

<span data-ttu-id="1cf42-285">**Eintrag**:`contoso.com/a/*`</span><span class="sxs-lookup"><span data-stu-id="1cf42-285">**Entry**: `contoso.com/a/*`</span></span>

- <span data-ttu-id="1cf42-286">Übereinstimmung und **Block Übereinstimmung** **zulassen** :</span><span class="sxs-lookup"><span data-stu-id="1cf42-286">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="1cf42-287">contoso.com/a/b</span><span class="sxs-lookup"><span data-stu-id="1cf42-287">contoso.com/a/b</span></span>
  - <span data-ttu-id="1cf42-288">contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="1cf42-288">contoso.com/a/b/c</span></span>
  - <span data-ttu-id="1cf42-289">contoso. com/a/? q = Joe@t. com</span><span class="sxs-lookup"><span data-stu-id="1cf42-289">contoso.com/a/?q=joe@t.com</span></span>

- <span data-ttu-id="1cf42-290">**Zulassen nicht abgeglichen** und **Block nicht abgeglichen**:</span><span class="sxs-lookup"><span data-stu-id="1cf42-290">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="1cf42-291">contoso.com</span><span class="sxs-lookup"><span data-stu-id="1cf42-291">contoso.com</span></span>
  - <span data-ttu-id="1cf42-292">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="1cf42-292">contoso.com/a</span></span>
  - <span data-ttu-id="1cf42-293">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1cf42-293">www.contoso.com</span></span>
  - <span data-ttu-id="1cf42-294">www. contoso. com/q = a@contoso. com</span><span class="sxs-lookup"><span data-stu-id="1cf42-294">www.contoso.com/q=a@contoso.com</span></span>
  
#### <a name="scenario-left-tilde"></a><span data-ttu-id="1cf42-295">Szenario: linke Tilde</span><span class="sxs-lookup"><span data-stu-id="1cf42-295">Scenario: Left tilde</span></span>

<span data-ttu-id="1cf42-296">**Eintrag**:`~contoso.com`</span><span class="sxs-lookup"><span data-stu-id="1cf42-296">**Entry**: `~contoso.com`</span></span>

- <span data-ttu-id="1cf42-297">Übereinstimmung und **Block Übereinstimmung** **zulassen** :</span><span class="sxs-lookup"><span data-stu-id="1cf42-297">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="1cf42-298">contoso.com</span><span class="sxs-lookup"><span data-stu-id="1cf42-298">contoso.com</span></span>
  - <span data-ttu-id="1cf42-299">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1cf42-299">www.contoso.com</span></span>
  - <span data-ttu-id="1cf42-300">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1cf42-300">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="1cf42-301">**Zulassen nicht abgeglichen** und **Block nicht abgeglichen**:</span><span class="sxs-lookup"><span data-stu-id="1cf42-301">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="1cf42-302">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="1cf42-302">123contoso.com</span></span>
  - <span data-ttu-id="1cf42-303">contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="1cf42-303">contoso.com/abc</span></span>
  - <span data-ttu-id="1cf42-304">www.contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="1cf42-304">www.contoso.com/abc</span></span>

#### <a name="scenario-right-wildcard-suffix"></a><span data-ttu-id="1cf42-305">Szenario: Rechtes Platzhalter Suffix</span><span class="sxs-lookup"><span data-stu-id="1cf42-305">Scenario: Right wildcard suffix</span></span>

<span data-ttu-id="1cf42-306">**Eintrag**:`contoso.com/*`</span><span class="sxs-lookup"><span data-stu-id="1cf42-306">**Entry**: `contoso.com/*`</span></span>

- <span data-ttu-id="1cf42-307">Übereinstimmung und **Block Übereinstimmung** **zulassen** :</span><span class="sxs-lookup"><span data-stu-id="1cf42-307">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="1cf42-308">contoso. com/? q = whatever@fabrikam. com</span><span class="sxs-lookup"><span data-stu-id="1cf42-308">contoso.com/?q=whatever@fabrikam.com</span></span>
  - <span data-ttu-id="1cf42-309">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="1cf42-309">contoso.com/a</span></span>
  - <span data-ttu-id="1cf42-310">contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="1cf42-310">contoso.com/a/b/c</span></span>
  - <span data-ttu-id="1cf42-311">contoso.com/ab</span><span class="sxs-lookup"><span data-stu-id="1cf42-311">contoso.com/ab</span></span>
  - <span data-ttu-id="1cf42-312">contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="1cf42-312">contoso.com/b</span></span>
  - <span data-ttu-id="1cf42-313">contoso.com/b/a/c</span><span class="sxs-lookup"><span data-stu-id="1cf42-313">contoso.com/b/a/c</span></span>
  - <span data-ttu-id="1cf42-314">contoso.com/ba</span><span class="sxs-lookup"><span data-stu-id="1cf42-314">contoso.com/ba</span></span>

- <span data-ttu-id="1cf42-315">**Allow NOT MATCHED** and **Block NOT MATCHED**: contoso.com</span><span class="sxs-lookup"><span data-stu-id="1cf42-315">**Allow not matched** and **Block not matched**: contoso.com</span></span>

#### <a name="scenario-left-wildcard-subdomain-and-right-wildcard-suffix"></a><span data-ttu-id="1cf42-316">Szenario: linke Platzhalter-Unterdomäne und Rechte Platzhalter Suffix</span><span class="sxs-lookup"><span data-stu-id="1cf42-316">Scenario: Left wildcard subdomain and right wildcard suffix</span></span>

<span data-ttu-id="1cf42-317">**Eintrag**:`*.contoso.com/*`</span><span class="sxs-lookup"><span data-stu-id="1cf42-317">**Entry**: `*.contoso.com/*`</span></span>

- <span data-ttu-id="1cf42-318">Übereinstimmung und **Block Übereinstimmung** **zulassen** :</span><span class="sxs-lookup"><span data-stu-id="1cf42-318">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="1cf42-319">abc.contoso.com/ab</span><span class="sxs-lookup"><span data-stu-id="1cf42-319">abc.contoso.com/ab</span></span>
  - <span data-ttu-id="1cf42-320">abc.xyz.contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="1cf42-320">abc.xyz.contoso.com/a/b/c</span></span>
  - <span data-ttu-id="1cf42-321">www.contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="1cf42-321">www.contoso.com/a</span></span>
  - <span data-ttu-id="1cf42-322">www.contoso.com/b/a/c</span><span class="sxs-lookup"><span data-stu-id="1cf42-322">www.contoso.com/b/a/c</span></span>
  - <span data-ttu-id="1cf42-323">xyz.contoso.com/ba</span><span class="sxs-lookup"><span data-stu-id="1cf42-323">xyz.contoso.com/ba</span></span>

- <span data-ttu-id="1cf42-324">**Allow NOT MATCHED** and **Block NOT MATCHED**: contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="1cf42-324">**Allow not matched** and **Block not matched**: contoso.com/b</span></span>

#### <a name="scenario-left-and-right-tilde"></a><span data-ttu-id="1cf42-325">Szenario: linke und Rechte Tilde</span><span class="sxs-lookup"><span data-stu-id="1cf42-325">Scenario: Left and right tilde</span></span>

<span data-ttu-id="1cf42-326">**Eintrag**:`~contoso.com~`</span><span class="sxs-lookup"><span data-stu-id="1cf42-326">**Entry**: `~contoso.com~`</span></span>

- <span data-ttu-id="1cf42-327">Übereinstimmung und **Block Übereinstimmung** **zulassen** :</span><span class="sxs-lookup"><span data-stu-id="1cf42-327">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="1cf42-328">contoso.com</span><span class="sxs-lookup"><span data-stu-id="1cf42-328">contoso.com</span></span>
  - <span data-ttu-id="1cf42-329">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="1cf42-329">contoso.com/a</span></span>
  - <span data-ttu-id="1cf42-330">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1cf42-330">www.contoso.com</span></span>
  - <span data-ttu-id="1cf42-331">www.contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="1cf42-331">www.contoso.com/b</span></span>
  - <span data-ttu-id="1cf42-332">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1cf42-332">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="1cf42-333">**Zulassen nicht abgeglichen** und **Block nicht abgeglichen**:</span><span class="sxs-lookup"><span data-stu-id="1cf42-333">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="1cf42-334">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="1cf42-334">123contoso.com</span></span>
  - <span data-ttu-id="1cf42-335">contoso.org</span><span class="sxs-lookup"><span data-stu-id="1cf42-335">contoso.org</span></span>

#### <a name="scenario-ip-address"></a><span data-ttu-id="1cf42-336">Szenario: IP-Adresse</span><span class="sxs-lookup"><span data-stu-id="1cf42-336">Scenario: IP address</span></span>

<span data-ttu-id="1cf42-337">**Eintrag**:`1.2.3.4`</span><span class="sxs-lookup"><span data-stu-id="1cf42-337">**Entry**: `1.2.3.4`</span></span>

- <span data-ttu-id="1cf42-338">Übereinstimmung **zulassen** und **Block Übereinstimmung**: 1.2.3.4</span><span class="sxs-lookup"><span data-stu-id="1cf42-338">**Allow match** and **Block match**: 1.2.3.4</span></span>

- <span data-ttu-id="1cf42-339">**Zulassen nicht abgeglichen** und **Block nicht abgeglichen**:</span><span class="sxs-lookup"><span data-stu-id="1cf42-339">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="1cf42-340">1.2.3.4/a</span><span class="sxs-lookup"><span data-stu-id="1cf42-340">1.2.3.4/a</span></span>
  - <span data-ttu-id="1cf42-341">11.2.3.4/a</span><span class="sxs-lookup"><span data-stu-id="1cf42-341">11.2.3.4/a</span></span>

#### <a name="ip-address-with-right-wildcard"></a><span data-ttu-id="1cf42-342">IP-Adresse mit dem richtigen Platzhalter</span><span class="sxs-lookup"><span data-stu-id="1cf42-342">IP address with right wildcard</span></span>

<span data-ttu-id="1cf42-343">**Eintrag**:`1.2.3.4/*`</span><span class="sxs-lookup"><span data-stu-id="1cf42-343">**Entry**: `1.2.3.4/*`</span></span>

- <span data-ttu-id="1cf42-344">Übereinstimmung und **Block Übereinstimmung** **zulassen** :</span><span class="sxs-lookup"><span data-stu-id="1cf42-344">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="1cf42-345">1.2.3.4/b</span><span class="sxs-lookup"><span data-stu-id="1cf42-345">1.2.3.4/b</span></span>
  - <span data-ttu-id="1cf42-346">1.2.3.4/baaaa</span><span class="sxs-lookup"><span data-stu-id="1cf42-346">1.2.3.4/baaaa</span></span>

### <a name="examples-of-invalid-entries"></a><span data-ttu-id="1cf42-347">Beispiele für ungültige Einträge</span><span class="sxs-lookup"><span data-stu-id="1cf42-347">Examples of invalid entries</span></span>

<span data-ttu-id="1cf42-348">Die folgenden Einträge sind ungültig:</span><span class="sxs-lookup"><span data-stu-id="1cf42-348">The following entries are invalid:</span></span>

- <span data-ttu-id="1cf42-349">**Fehlende oder ungültige Domänenwerte**:</span><span class="sxs-lookup"><span data-stu-id="1cf42-349">**Missing or invalid domain values**:</span></span>

  - <span data-ttu-id="1cf42-350">contoso</span><span class="sxs-lookup"><span data-stu-id="1cf42-350">contoso</span></span>
  - <span data-ttu-id="1cf42-351">\*contoso.\*</span><span class="sxs-lookup"><span data-stu-id="1cf42-351">\*.contoso.\*</span></span>
  - <span data-ttu-id="1cf42-352">\*. com</span><span class="sxs-lookup"><span data-stu-id="1cf42-352">\*.com</span></span>
  - <span data-ttu-id="1cf42-353">\*.PDF</span><span class="sxs-lookup"><span data-stu-id="1cf42-353">\*.pdf</span></span>

- <span data-ttu-id="1cf42-354">**Platzhalter für Text oder ohne Leerzeichen**:</span><span class="sxs-lookup"><span data-stu-id="1cf42-354">**Wildcard on text or without spacing characters**:</span></span>

  - <span data-ttu-id="1cf42-355">\*contoso.com</span><span class="sxs-lookup"><span data-stu-id="1cf42-355">\*contoso.com</span></span>
  - <span data-ttu-id="1cf42-356">contoso.com\*</span><span class="sxs-lookup"><span data-stu-id="1cf42-356">contoso.com\*</span></span>
  - <span data-ttu-id="1cf42-357">\*1.2.3.4</span><span class="sxs-lookup"><span data-stu-id="1cf42-357">\*1.2.3.4</span></span>
  - <span data-ttu-id="1cf42-358">1.2.3.4\*</span><span class="sxs-lookup"><span data-stu-id="1cf42-358">1.2.3.4\*</span></span>
  - <span data-ttu-id="1cf42-359">contoso.com/a\*</span><span class="sxs-lookup"><span data-stu-id="1cf42-359">contoso.com/a\*</span></span>
  - <span data-ttu-id="1cf42-360">contoso.com/ab\*</span><span class="sxs-lookup"><span data-stu-id="1cf42-360">contoso.com/ab\*</span></span>

- <span data-ttu-id="1cf42-361">**IP-Adressen mit Ports**:</span><span class="sxs-lookup"><span data-stu-id="1cf42-361">**IP addresses with ports**:</span></span>

  - <span data-ttu-id="1cf42-362">contoso.com:443</span><span class="sxs-lookup"><span data-stu-id="1cf42-362">contoso.com:443</span></span>
  - <span data-ttu-id="1cf42-363">abc.contoso.com:25</span><span class="sxs-lookup"><span data-stu-id="1cf42-363">abc.contoso.com:25</span></span>

- <span data-ttu-id="1cf42-364">**Nicht beschreibende Platzhalter**:</span><span class="sxs-lookup"><span data-stu-id="1cf42-364">**Non-descriptive wildcards**:</span></span>

  - \*
  - <span data-ttu-id="1cf42-365">\*.\*</span><span class="sxs-lookup"><span data-stu-id="1cf42-365">\*.\*</span></span>

- <span data-ttu-id="1cf42-366">**Mittlere Platzhalter**:</span><span class="sxs-lookup"><span data-stu-id="1cf42-366">**Middle wildcards**:</span></span>

  - <span data-ttu-id="1cf42-367">Conto \* so.com</span><span class="sxs-lookup"><span data-stu-id="1cf42-367">conto\*so.com</span></span>
  - <span data-ttu-id="1cf42-368">Conto ~ so. com</span><span class="sxs-lookup"><span data-stu-id="1cf42-368">conto~so.com</span></span>

- <span data-ttu-id="1cf42-369">**Doppelte Platzhalter**</span><span class="sxs-lookup"><span data-stu-id="1cf42-369">**Double wildcards**</span></span>

  - <span data-ttu-id="1cf42-370">contoso.com/\*\*</span><span class="sxs-lookup"><span data-stu-id="1cf42-370">contoso.com/\*\*</span></span>
  - <span data-ttu-id="1cf42-371">contoso.com/\*/\*</span><span class="sxs-lookup"><span data-stu-id="1cf42-371">contoso.com/\*/\*</span></span>
