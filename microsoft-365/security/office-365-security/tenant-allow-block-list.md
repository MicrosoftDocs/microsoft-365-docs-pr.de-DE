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
ms.openlocfilehash: 0143ee2601a4cb9593c79f8c6c62d1f06914088f
ms.sourcegitcommit: 73b2426001dc5a3f4b857366ef51e877db549098
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/09/2020
ms.locfileid: "44613420"
---
# <a name="manage-urls-and-files-in-the-tenant-allowblock-list"></a><span data-ttu-id="42cc2-103">Verwalten von URLs und Dateien in der Liste "Mandanten zulassen/blockieren"</span><span class="sxs-lookup"><span data-stu-id="42cc2-103">Manage URLs and files in the Tenant Allow/Block List</span></span>

> [!NOTE]
> <span data-ttu-id="42cc2-104">Die in diesem Thema beschriebenen Funktionen befinden sich in der Vorschau, können sich ändern und sind nicht in allen Organisationen verfügbar.</span><span class="sxs-lookup"><span data-stu-id="42cc2-104">The features described in this topic are in Preview, are subject to change, and are not available in all organizations.</span></span>

<span data-ttu-id="42cc2-105">In Microsoft 365-Organisationen mit Postfächern in Exchange Online-oder eigenständigen Exchange Online Schutzorganisationen (EoP) ohne Exchange Online Postfächer können Sie mit dem EoP-Filter Urteil nicht einverstanden sein.</span><span class="sxs-lookup"><span data-stu-id="42cc2-105">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, you might disagree with the EOP filtering verdict.</span></span> <span data-ttu-id="42cc2-106">Beispielsweise kann eine gute Nachricht als "schlecht" markiert werden (ein falsch positives Ergebnis), oder es ist möglicherweise eine ungültige Meldung zulässig (ein falsches negativ).</span><span class="sxs-lookup"><span data-stu-id="42cc2-106">For example, a good message might be marked as bad (a false positive), or a bad message might be allowed through (a false negative).</span></span>

<span data-ttu-id="42cc2-107">In der Liste Mandanten-Allow/Block im Security & Compliance Center haben Sie die Möglichkeit, die Microsoft 365-Filter Urteile manuell außer Kraft zu setzen.</span><span class="sxs-lookup"><span data-stu-id="42cc2-107">The Tenant Allow/Block List in the Security & Compliance Center gives you a way to manually override the Microsoft 365 filtering verdicts.</span></span> <span data-ttu-id="42cc2-108">Die Mandanten-Zulassungs-und Sperrliste wird während des e-Mail-Flusses und zum Zeitpunkt der Benutzerklicks verwendet.</span><span class="sxs-lookup"><span data-stu-id="42cc2-108">The Tenant Allow/Block List is used during mail flow and at the time of user clicks.</span></span> <span data-ttu-id="42cc2-109">In der Liste Mandanten-Allow/Block können Sie URLs und Dateien angeben, die zugelassen oder blockiert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="42cc2-109">You can specify URLs and files to allow or block in the Tenant Allow/Block List.</span></span>

<span data-ttu-id="42cc2-110">In diesem Thema wird beschrieben, wie Sie Einträge in der Liste "Allow/Block" des Mandanten im Security & Compliance Center oder in PowerShell (Exchange Online PowerShell für Microsoft 365-Organisationen mit Postfächern in Exchange Online; eigenständige EoP PowerShell für Organisationen ohne Exchange Online Postfächer) konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="42cc2-110">This topic describes how to configure entries in the Tenant Allow/Block List in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="42cc2-111">Was sollten Sie wissen, bevor Sie beginnen?</span><span class="sxs-lookup"><span data-stu-id="42cc2-111">What do you need to know before you begin?</span></span>

- <span data-ttu-id="42cc2-112">Sie öffnen das Security & Compliance Center unter <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="42cc2-112">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="42cc2-113">Wenn Sie direkt zur Seite **Mandanten-Zulassungs-und Sperrliste** wechseln möchten, verwenden Sie <https://protection.office.com/tenantAllowBlockList> .</span><span class="sxs-lookup"><span data-stu-id="42cc2-113">To go directly to the **Tenant Allow/Block List** page, use <https://protection.office.com/tenantAllowBlockList>.</span></span>

- <span data-ttu-id="42cc2-114">Sie geben Dateien mithilfe des SHA256-Hash Werts der Datei an.</span><span class="sxs-lookup"><span data-stu-id="42cc2-114">You specify files by using the SHA256 hash value of the file.</span></span> <span data-ttu-id="42cc2-115">Um den SHA256-Hashwert einer Datei in Windows zu suchen, führen Sie den folgenden Befehl an einer Eingabeaufforderung aus:</span><span class="sxs-lookup"><span data-stu-id="42cc2-115">To find the SHA256 hash value of a file in Windows, run the following command in a Command Prompt:</span></span>

  ```dos
  certutil.exe -hashfile "<Path>\<Filename>" SHA256
  ```

  <span data-ttu-id="42cc2-116">Ein Beispielwert ist `768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3a` .</span><span class="sxs-lookup"><span data-stu-id="42cc2-116">An example value is `768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3a`.</span></span> <span data-ttu-id="42cc2-117">PHash-Werte (wahrnehmbarer Hash) sind nicht zulässig.</span><span class="sxs-lookup"><span data-stu-id="42cc2-117">Perceptual hash (pHash) values are not allowed.</span></span>

- <span data-ttu-id="42cc2-118">Die verfügbaren URL-Werte werden in der [URL-Syntax für den Abschnitt Mandanten-Zulassungs-und Sperrliste](#url-syntax-for-the-tenant-allowblock-list) weiter unten in diesem Thema beschrieben.</span><span class="sxs-lookup"><span data-stu-id="42cc2-118">The available URL values are described in the [URL syntax for the Tenant Allow/Block List](#url-syntax-for-the-tenant-allowblock-list) section later in this topic.</span></span>

- <span data-ttu-id="42cc2-119">Die Liste Mandanten Allow/Block erlaubt maximal 500 Einträge für URLs und 500 Einträge für Datei Hashs.</span><span class="sxs-lookup"><span data-stu-id="42cc2-119">The Tenant Allow/Block List allows a maximum of 500 entries for URLs, and 500 entries for file hashes.</span></span>

- <span data-ttu-id="42cc2-120">Ein Eintrag sollte innerhalb von 15 Minuten aktiv sein.</span><span class="sxs-lookup"><span data-stu-id="42cc2-120">An entry should be active within 15 minutes.</span></span>

- <span data-ttu-id="42cc2-121">Block Einträge haben Vorrang vor Zulassungs Einträgen.</span><span class="sxs-lookup"><span data-stu-id="42cc2-121">Block entries take precedence over allow entries.</span></span>

- <span data-ttu-id="42cc2-122">Standardmäßig laufen Einträge in der Liste Mandanten-Allow/Block nach 30 Tagen ab.</span><span class="sxs-lookup"><span data-stu-id="42cc2-122">By default, entries in the Tenant Allow/Block List will expire after 30 days.</span></span> <span data-ttu-id="42cc2-123">Sie können ein Datum angeben oder festlegen, dass es nie abläuft.</span><span class="sxs-lookup"><span data-stu-id="42cc2-123">You can specify a date or set them to never expire.</span></span>

- <span data-ttu-id="42cc2-124">Wie Sie eine Verbindung mit Exchange Online PowerShell herstellen, finden Sie unter [Herstellen einer Verbindung mit Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="42cc2-124">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="42cc2-125">Informationen zum Herstellen einer Verbindung mit dem eigenständigen Exchange Online Protection PowerShell finden Sie unter [Verbinden mit PowerShell in Exchange Online Protection](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="42cc2-125">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="42cc2-126">Bevor Sie diese Verfahren ausführen können, müssen Ihnen die entsprechenden Berechtigungen zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="42cc2-126">You need to be assigned permissions before you can perform these procedures.</span></span> <span data-ttu-id="42cc2-127">Sie müssen Mitglied der Rollengruppen " **Organisationsverwaltung** " oder " **Sicherheits Administrator** " sein, um Werte aus der Liste "Allow/Block" für Mandanten hinzuzufügen und daraus zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="42cc2-127">To add and remove values from the Tenant Allow/Block List, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span> <span data-ttu-id="42cc2-128">Sie müssen ein Mitglied der Rollengruppe **Sicherheits Leser** sein, um den schreibgeschützten Zugriff auf die Liste der zugelassenen und blockierten Mandanten zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="42cc2-128">For read-only access to the Tenant Allow/Block List, you need to be a member of the **Security Reader** role group.</span></span> <span data-ttu-id="42cc2-129">Weitere Informationen zu Rollengruppen im Security & Compliance Center finden Sie unter [Berechtigungen im Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="42cc2-129">For more information about role groups in the Security & Compliance Center, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

## <a name="use-the-security--compliance-center-to-create-url-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="42cc2-130">Verwenden Sie das Security & Compliance Center, um URL-Einträge in der Liste Mandanten-Allow/Block zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="42cc2-130">Use the Security & Compliance Center to create URL entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="42cc2-131">Ausführliche Informationen zur Syntax für URL-Einträge finden Sie weiter unten in diesem Thema in der [URL-Syntax für den Abschnitt Allow/Block List für Mandanten](#url-syntax-for-the-tenant-allowblock-list) .</span><span class="sxs-lookup"><span data-stu-id="42cc2-131">For details about the syntax for URL entries, see the [URL syntax for the Tenant Allow/Block List](#url-syntax-for-the-tenant-allowblock-list) section later in this topic.</span></span>

1. <span data-ttu-id="42cc2-132">Wechseln Sie im Security & Compliance Center zu **Bedrohungs Verwaltungs** \> **Richtlinie** \> **Mandanten-Zulassungs-/Sperrlisten**.</span><span class="sxs-lookup"><span data-stu-id="42cc2-132">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="42cc2-133">Überprüfen Sie auf der Seite **Mandantenliste zulassen/blockieren** , dass die Registerkarte **URLs** ausgewählt ist, und klicken Sie dann auf **Hinzufügen** .</span><span class="sxs-lookup"><span data-stu-id="42cc2-133">On the **Tenant Allow/Block List** page, verify that the **URLs** tab is selected, and then click **Add**</span></span>

3. <span data-ttu-id="42cc2-134">Konfigurieren Sie im Flyout **neue URLs hinzufügen** , das angezeigt wird, die folgenden Einstellungen:</span><span class="sxs-lookup"><span data-stu-id="42cc2-134">In the **Add new URLs** flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="42cc2-135">**URLs mit Platzhaltern hinzufügen**: Geben Sie eine URL pro Reihe bis maximal 20 ein.</span><span class="sxs-lookup"><span data-stu-id="42cc2-135">**Add URLs with wildcards**: Enter one URL per line, up to a maximum of 20.</span></span>

   - <span data-ttu-id="42cc2-136">**Block/Allow**: Wählen Sie aus, ob die angegebenen URLs **zugelassen** oder **blockiert** werden sollen.</span><span class="sxs-lookup"><span data-stu-id="42cc2-136">**Block/Allow**: Select whether you want to **Allow** or **Block** the specified URLs.</span></span>

   - <span data-ttu-id="42cc2-137">**Nie ablaufen**: führen Sie einen der folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="42cc2-137">**Never expire**: Do one of the following steps:</span></span>

     - <span data-ttu-id="42cc2-138">Stellen Sie sicher, dass die Einstellung deaktiviert ist (deaktivieren ![ ](../../media/scc-toggle-off.png) ), und verwenden Sie das Feld **expires on** , um das Ablaufdatum für die Einträge anzugeben.</span><span class="sxs-lookup"><span data-stu-id="42cc2-138">Verify the setting is turned off (![Toggle off](../../media/scc-toggle-off.png)) and use the **Expires on** box to specify the expiration date for the entries.</span></span>

     <span data-ttu-id="42cc2-139">oder</span><span class="sxs-lookup"><span data-stu-id="42cc2-139">or</span></span>

     - <span data-ttu-id="42cc2-140">Bewegen Sie die Umschaltfläche nach rechts, um die Einträge so zu konfigurieren, dass Sie nie ablaufen:</span><span class="sxs-lookup"><span data-stu-id="42cc2-140">Move the toggle to the right to configure the entries to never expire:</span></span> ![Umschaltfläche ein](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png)<span data-ttu-id="42cc2-142">.</span><span class="sxs-lookup"><span data-stu-id="42cc2-142">.</span></span>

   - <span data-ttu-id="42cc2-143">**Optional Hinweis**: Geben Sie einen beschreibenden Text für die Einträge ein.</span><span class="sxs-lookup"><span data-stu-id="42cc2-143">**Optional note**: Enter descriptive text for the entries.</span></span>

4. <span data-ttu-id="42cc2-144">Wenn Sie fertig sind, klicken Sie auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="42cc2-144">When you're finished, click **Add**.</span></span>

## <a name="use-the-security--compliance-center-to-create-file-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="42cc2-145">Verwenden des Security & Compliance Center zum Erstellen von Dateieinträgen in der Liste "Mandanten zulassen/blockieren"</span><span class="sxs-lookup"><span data-stu-id="42cc2-145">Use the Security & Compliance Center to create file entries in the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="42cc2-146">Wechseln Sie im Security & Compliance Center zu **Bedrohungs Verwaltungs** \> **Richtlinie** \> **Mandanten-Zulassungs-/Sperrlisten**.</span><span class="sxs-lookup"><span data-stu-id="42cc2-146">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="42cc2-147">Wählen Sie auf der Seite **Mandanten Allow/Block List** die Registerkarte **Dateien** aus, und klicken Sie dann auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="42cc2-147">On the **Tenant Allow/Block List** page, select **Files** tab, and then click **Add**.</span></span>

3. <span data-ttu-id="42cc2-148">Konfigurieren Sie im angezeigten Flyout **neue Dateien hinzufügen** die folgenden Einstellungen:</span><span class="sxs-lookup"><span data-stu-id="42cc2-148">In the **Add new files** flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="42cc2-149">**Datei Hashes hinzufügen**: Geben Sie einen SHA256-Hashwert pro Reihe ein, bis zu einem Maximum von 20.</span><span class="sxs-lookup"><span data-stu-id="42cc2-149">**Add file hashes**: Enter one SHA256 hash value per line, up to a maximum of 20.</span></span>

   - <span data-ttu-id="42cc2-150">**Block/Allow**: Wählen Sie aus, ob die angegebenen Dateien **zugelassen** oder **blockiert** werden sollen.</span><span class="sxs-lookup"><span data-stu-id="42cc2-150">**Block/Allow**: Select whether you want to **Allow** or **Block** the specified files.</span></span>

   - <span data-ttu-id="42cc2-151">**Nie ablaufen**: führen Sie einen der folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="42cc2-151">**Never expire**: Do one of the following steps:</span></span>

     - <span data-ttu-id="42cc2-152">Stellen Sie sicher, dass die Einstellung deaktiviert ist (deaktivieren ![ ](../../media/scc-toggle-off.png) ), und verwenden Sie das Feld **expires on** , um das Ablaufdatum für die Einträge anzugeben.</span><span class="sxs-lookup"><span data-stu-id="42cc2-152">Verify the setting is turned off (![Toggle off](../../media/scc-toggle-off.png)) and use the **Expires on** box to specify the expiration date for the entries.</span></span>

     <span data-ttu-id="42cc2-153">oder</span><span class="sxs-lookup"><span data-stu-id="42cc2-153">or</span></span>

     - <span data-ttu-id="42cc2-154">Bewegen Sie die Umschaltfläche nach rechts, um die Einträge so zu konfigurieren, dass Sie nie ablaufen:</span><span class="sxs-lookup"><span data-stu-id="42cc2-154">Move the toggle to the right to configure the entries to never expire:</span></span> ![Umschaltfläche ein](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png)<span data-ttu-id="42cc2-156">.</span><span class="sxs-lookup"><span data-stu-id="42cc2-156">.</span></span>

   - <span data-ttu-id="42cc2-157">**Optional Hinweis**: Geben Sie einen beschreibenden Text für die Einträge ein.</span><span class="sxs-lookup"><span data-stu-id="42cc2-157">**Optional note**: Enter descriptive text for the entries.</span></span>

4. <span data-ttu-id="42cc2-158">Wenn Sie fertig sind, klicken Sie auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="42cc2-158">When you're finished, click **Add**.</span></span>

## <a name="use-the-security--compliance-center-to-view-url-and-file-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="42cc2-159">Verwenden Sie das Security & Compliance Center, um URL-und Dateieinträge in der Liste Mandanten-Allow/Block anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="42cc2-159">Use the Security & Compliance Center to view URL and file entries in the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="42cc2-160">Wechseln Sie im Security & Compliance Center zu **Bedrohungs Verwaltungs** \> **Richtlinie** \> **Mandanten-Zulassungs-/Sperrlisten**.</span><span class="sxs-lookup"><span data-stu-id="42cc2-160">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="42cc2-161">Wählen Sie die Registerkarte **URLs** oder die Registerkarte **Dateien** aus.</span><span class="sxs-lookup"><span data-stu-id="42cc2-161">Select the **URLs** tab or the **Files** tab.</span></span>

<span data-ttu-id="42cc2-162">Klicken Sie auf die folgenden Spaltenüberschriften, um Sie in aufsteigender oder absteigender Reihenfolge zu sortieren:</span><span class="sxs-lookup"><span data-stu-id="42cc2-162">Click on the following column headings to sort in ascending or descending order:</span></span>

- <span data-ttu-id="42cc2-163">**Wert**: die URL oder der Datei Hash.</span><span class="sxs-lookup"><span data-stu-id="42cc2-163">**Value**: The URL or the file hash.</span></span>
- <span data-ttu-id="42cc2-164">**Aktion**: **blockieren** oder **zulassen**.</span><span class="sxs-lookup"><span data-stu-id="42cc2-164">**Action**: **Block** or **Allow**.</span></span>
- <span data-ttu-id="42cc2-165">**Datum der letzten Aktualisierung**</span><span class="sxs-lookup"><span data-stu-id="42cc2-165">**Last updated date**</span></span>
- <span data-ttu-id="42cc2-166">**Ablaufdatum**</span><span class="sxs-lookup"><span data-stu-id="42cc2-166">**Expiration date**</span></span>
- <span data-ttu-id="42cc2-167">**Hinweis**</span><span class="sxs-lookup"><span data-stu-id="42cc2-167">**Note**</span></span>

<span data-ttu-id="42cc2-168">Klicken Sie auf **Gruppieren** , um die Einträge nach **Aktion** (**blockieren** oder **zulassen**) oder **ohne**zu gruppieren.</span><span class="sxs-lookup"><span data-stu-id="42cc2-168">Click **Group** to group the entries by **Action** (**Block** or **Allow**) or **None**.</span></span>

<span data-ttu-id="42cc2-169">Klicken Sie auf **Suchen**, geben Sie eine URL oder einen Datei Wert ganz oder teilweise ein, und drücken Sie dann die EINGABETASTE, um einen bestimmten Wert zu suchen.</span><span class="sxs-lookup"><span data-stu-id="42cc2-169">Click **Search**, enter all or part of a URL or file value, and then press ENTER to find a specific value.</span></span> <span data-ttu-id="42cc2-170">Wenn Sie fertig sind, klicken Sie auf **Such** ![ Symbol Löschen ](../../media/b6512677-5e7b-42b0-a8a3-3be1d7fa23ee.gif) .</span><span class="sxs-lookup"><span data-stu-id="42cc2-170">When you're finished, click **Clear search** ![Clear search icon](../../media/b6512677-5e7b-42b0-a8a3-3be1d7fa23ee.gif).</span></span>

<span data-ttu-id="42cc2-171">Klicken Sie auf **Filter**.</span><span class="sxs-lookup"><span data-stu-id="42cc2-171">Click **Filter**.</span></span> <span data-ttu-id="42cc2-172">Konfigurieren Sie im angezeigten **Filter** Flyout die folgenden Einstellungen:</span><span class="sxs-lookup"><span data-stu-id="42cc2-172">In the **Filter** flyout that appears, configure any of the following settings:</span></span>

- <span data-ttu-id="42cc2-173">**Aktion**: Wählen Sie **zulassen**, **blockieren** oder beides aus.</span><span class="sxs-lookup"><span data-stu-id="42cc2-173">**Action**: Select **Allow**, **Block** or both.</span></span>

- <span data-ttu-id="42cc2-174">**Läuft nie**ab: Wählen Sie aus (deaktivieren ![ ](../../media/scc-toggle-off.png) ) oder ein (Umschalten ![ ](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png) ) aus.</span><span class="sxs-lookup"><span data-stu-id="42cc2-174">**Never expire**: Select off (![Toggle off](../../media/scc-toggle-off.png)) or on (![Toggle on](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png)).</span></span>

- <span data-ttu-id="42cc2-175">**Letzte Aktualisierung**: Wählen Sie ein Startdatum (von), ein Enddatum (**an**) oder beides**aus**.</span><span class="sxs-lookup"><span data-stu-id="42cc2-175">**Last updated**: Select a start date (**From**), an end date (**To**) or both.</span></span>

- <span data-ttu-id="42cc2-176">**Ablaufdatum**: Wählen Sie ein Startdatum (von), ein Enddatum (**an**) oder beides**aus**.</span><span class="sxs-lookup"><span data-stu-id="42cc2-176">**Expiration date**: Select a start date (**From**), an end date (**To**) or both.</span></span>

<span data-ttu-id="42cc2-177">Wenn Sie fertig sind, klicken Sie auf über **nehmen**.</span><span class="sxs-lookup"><span data-stu-id="42cc2-177">When you're finished, click **Apply**.</span></span>

<span data-ttu-id="42cc2-178">Wenn Sie vorhandene Filter löschen möchten, klicken Sie auf **Filter**, und klicken Sie im daraufhin angezeigten **Filter** Flyout auf Filter **Löschen**.</span><span class="sxs-lookup"><span data-stu-id="42cc2-178">To clear existing filters, click **Filter**, and in the **Filter** flyout that appears, click **Clear filters**.</span></span>

## <a name="use-the-security--compliance-center-to-modify-url-and-file-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="42cc2-179">Verwenden des Security & Compliance Center zum Ändern von URL-und Dateieinträgen in der Liste Mandanten-Allow/Block</span><span class="sxs-lookup"><span data-stu-id="42cc2-179">Use the Security & Compliance Center to modify URL and file entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="42cc2-180">Sie können den URL-Wert oder den Dateiwert selbst nicht ändern.</span><span class="sxs-lookup"><span data-stu-id="42cc2-180">You can't modify the URL or file value itself.</span></span> <span data-ttu-id="42cc2-181">Stattdessen müssen Sie den Eintrag löschen und neu erstellen.</span><span class="sxs-lookup"><span data-stu-id="42cc2-181">Instead, you need to delete the entry and recreate it.</span></span>

1. <span data-ttu-id="42cc2-182">Wechseln Sie im Security & Compliance Center zu **Bedrohungs Verwaltungs** \> **Richtlinie** \> **Mandanten-Zulassungs-/Sperrlisten**.</span><span class="sxs-lookup"><span data-stu-id="42cc2-182">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="42cc2-183">Wählen Sie die Registerkarte **URLs** oder die Registerkarte **Dateien** aus.</span><span class="sxs-lookup"><span data-stu-id="42cc2-183">Select the **URLs** tab or the **Files** tab.</span></span>

3. <span data-ttu-id="42cc2-184">Wählen Sie den Eintrag aus, den Sie ändern möchten, und klicken Sie dann auf Bearbeitungssymbol **Bearbeiten** ![ ](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) .</span><span class="sxs-lookup"><span data-stu-id="42cc2-184">Select the entry that you want to modify, and then click **Edit** ![Edit icon](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png).</span></span>

4. <span data-ttu-id="42cc2-185">Konfigurieren Sie im Flyout, das angezeigt wird, die folgenden Einstellungen:</span><span class="sxs-lookup"><span data-stu-id="42cc2-185">In the flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="42cc2-186">**Blockieren/zulassen**: Wählen Sie **zulassen** oder **blockieren**aus.</span><span class="sxs-lookup"><span data-stu-id="42cc2-186">**Block/Allow**: Select **Allow** or **Block**.</span></span>

   - <span data-ttu-id="42cc2-187">**Nie ablaufen**: führen Sie einen der folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="42cc2-187">**Never expire**: Do one of the following steps:</span></span>

     - <span data-ttu-id="42cc2-188">Stellen Sie sicher, dass die Einstellung deaktiviert ist (deaktivieren ![ ](../../media/scc-toggle-off.png) ), und verwenden Sie das Feld **expires on** , um das Ablaufdatum für den Eintrag anzugeben.</span><span class="sxs-lookup"><span data-stu-id="42cc2-188">Verify the setting is turned off (![Toggle off](../../media/scc-toggle-off.png)) and use the **Expires on** box to specify the expiration date for the entry.</span></span>

     <span data-ttu-id="42cc2-189">oder</span><span class="sxs-lookup"><span data-stu-id="42cc2-189">or</span></span>

     - <span data-ttu-id="42cc2-190">Bewegen Sie die Umschaltfläche nach rechts, um den Eintrag so zu konfigurieren, dass er nie abläuft:</span><span class="sxs-lookup"><span data-stu-id="42cc2-190">Move the toggle to the right to configure the entry to never expire:</span></span> ![Umschaltfläche ein](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png)<span data-ttu-id="42cc2-192">.</span><span class="sxs-lookup"><span data-stu-id="42cc2-192">.</span></span>

   - <span data-ttu-id="42cc2-193">**Optional Hinweis**: Geben Sie einen beschreibenden Text für den Eintrag ein.</span><span class="sxs-lookup"><span data-stu-id="42cc2-193">**Optional note**: Enter descriptive text for the entry.</span></span>

5. <span data-ttu-id="42cc2-194">Klicken Sie nach Abschluss des Vorgangs auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="42cc2-194">When you're finished, click **Save**.</span></span>

## <a name="use-the-security--compliance-center-to-remove-url-and-file-entries-from-the-tenant-allowblock-list"></a><span data-ttu-id="42cc2-195">Verwenden des Security & Compliance Center zum Entfernen von URL-und Dateieinträgen aus der Liste Mandanten-Allow/Block</span><span class="sxs-lookup"><span data-stu-id="42cc2-195">Use the Security & Compliance Center to remove URL and file entries from the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="42cc2-196">Wechseln Sie im Security & Compliance Center zu **Bedrohungs Verwaltungs** \> **Richtlinie** \> **Mandanten-Zulassungs-/Sperrlisten**.</span><span class="sxs-lookup"><span data-stu-id="42cc2-196">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="42cc2-197">Wählen Sie die Registerkarte **URLs** oder die Registerkarte **Dateien** aus.</span><span class="sxs-lookup"><span data-stu-id="42cc2-197">Select the **URLs** tab or the **Files** tab.</span></span>

3. <span data-ttu-id="42cc2-198">Wählen Sie den Eintrag aus, den Sie entfernen möchten, und klicken Sie **dann auf Delete** ![ Delete Icon ](../../media/87565fbb-5147-4f22-9ed7-1c18ce664392.png) .</span><span class="sxs-lookup"><span data-stu-id="42cc2-198">Select the entry that you want to remove, and then click **Delete** ![Delete icon](../../media/87565fbb-5147-4f22-9ed7-1c18ce664392.png).</span></span>

4. <span data-ttu-id="42cc2-199">Klicken Sie im angezeigten Warndialogfeld auf **Löschen**.</span><span class="sxs-lookup"><span data-stu-id="42cc2-199">In the warning dialog that appears, click **Delete**.</span></span>

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-the-tenant-allowblock-list"></a><span data-ttu-id="42cc2-200">Verwenden Exchange Online PowerShell oder eigenständiger EoP PowerShell zum Konfigurieren der Liste "Mandanten zulassen/blockieren"</span><span class="sxs-lookup"><span data-stu-id="42cc2-200">Use Exchange Online PowerShell or standalone EOP PowerShell to configure the Tenant Allow/Block List</span></span>

### <a name="use-powershell-to-add-url-and-file-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="42cc2-201">Verwenden von PowerShell zum Hinzufügen von URL-und Dateieinträgen in der Liste "Mandanten zulassen/blockieren"</span><span class="sxs-lookup"><span data-stu-id="42cc2-201">Use PowerShell to add URL and file entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="42cc2-202">Verwenden Sie die folgende Syntax, um URL-und Dateieinträge in der Liste Mandanten Allow/Block hinzuzufügen:</span><span class="sxs-lookup"><span data-stu-id="42cc2-202">To add URL and file entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
New-TenantAllowBlockListItems -ListType <Url | FileHash> -Action <Allow | Block> -Entries <String[]> [-ExpirationDate <DateTime>] [-NoExpiration] [-Notes <String>]
```

<span data-ttu-id="42cc2-203">In diesem Beispiel wird ein URL-Sperreintrag für contoso.com und alle Unterdomänen hinzugefügt (beispielsweise contoso.com, www.contoso.com und XYZ.ABC.contoso.com).</span><span class="sxs-lookup"><span data-stu-id="42cc2-203">This example adds a URL block entry for contoso.com and all subdomains (for example, contoso.com, www.contoso.com, and xyz.abc.contoso.com).</span></span> <span data-ttu-id="42cc2-204">Da die Parameter ExpirationDate oder NOEXPIRE nicht verwendet wurden, läuft der Eintrag nach 30 Tagen ab.</span><span class="sxs-lookup"><span data-stu-id="42cc2-204">Because we didn't use the ExpirationDate or NoExpiration parameters, the entry expires after 30 days.</span></span>

```powershell
New-TenantAllowBlockListItem -ListType Url -Action Block -Entries ~contoso.com
```

```powershell
New-TenantAllowBlockListItem -ListType FileHash -Action Allow -Entries "768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3","2c0a35409ff0873cfa28b70b8224e9aca2362241c1f0ed6f622fef8d4722fd9a" -NoExpiration
```

<span data-ttu-id="42cc2-205">In diesem Beispiel wird der Eintrag "Datei zulassen" für die angegebenen Dateien hinzugefügt, die nie ablaufen.</span><span class="sxs-lookup"><span data-stu-id="42cc2-205">This example adds a file allow entry for the specified files that never expires.</span></span>

<span data-ttu-id="42cc2-206">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [New-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/new-tenantallowblocklistitems).</span><span class="sxs-lookup"><span data-stu-id="42cc2-206">For detailed syntax and parameter information, see [New-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/new-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-view-url-and-file-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="42cc2-207">Verwenden von PowerShell zum Anzeigen von URL-und Dateieinträgen in der Liste "Mandanten zulassen/blockieren"</span><span class="sxs-lookup"><span data-stu-id="42cc2-207">Use PowerShell to view URL and file entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="42cc2-208">Verwenden Sie die folgende Syntax, um URL-und Dateieinträge in der Liste Mandanten Allow/Block anzuzeigen:</span><span class="sxs-lookup"><span data-stu-id="42cc2-208">To view URL and file entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType <Url | FileHash> [-Entry <URLValue | FileHashValue>] [-Action <Allow | Block>] [-ExpirationDate <DateTime>] [-NoExpiration]
```

<span data-ttu-id="42cc2-209">In diesem Beispiel werden alle blockierten URLs zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="42cc2-209">This example returns all blocked URLs.</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType Url -Action Block
```

<span data-ttu-id="42cc2-210">In diesem Beispiel werden Informationen für den angegebenen Datei Hash Wert zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="42cc2-210">This example returns information for the specified file hash value.</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType FileHash -Entry "9f86d081884c7d659a2feaa0c55ad015a3bf4f1b2b0b822cd15d6c15b0f00a08"
```

<span data-ttu-id="42cc2-211">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Get-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/get-tenantallowblocklistitems).</span><span class="sxs-lookup"><span data-stu-id="42cc2-211">For detailed syntax and parameter information, see [Get-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/get-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-modify-url-and-file-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="42cc2-212">Verwenden von PowerShell zum Ändern von URL-und Dateieinträgen in der Liste "Mandanten zulassen/blockieren"</span><span class="sxs-lookup"><span data-stu-id="42cc2-212">Use PowerShell to modify URL and file entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="42cc2-213">Sie können den URL-Wert oder den Dateiwert selbst nicht ändern.</span><span class="sxs-lookup"><span data-stu-id="42cc2-213">You can't modify the URL or file value itself.</span></span> <span data-ttu-id="42cc2-214">Stattdessen müssen Sie den Eintrag löschen und neu erstellen.</span><span class="sxs-lookup"><span data-stu-id="42cc2-214">Instead, you need to delete the entry and recreate it.</span></span>

<span data-ttu-id="42cc2-215">Verwenden Sie die folgende Syntax, um URL-und Dateieinträge in der Liste Mandanten Allow/Block zu ändern:</span><span class="sxs-lookup"><span data-stu-id="42cc2-215">To modify URL and file entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Set-TenantAllowBlockListItems -ListType <Url | FileHash> -Ids <"Id1","Id2",..."IdN"> [-Action <Allow | Block>] [-ExpirationDate <DateTime>] [-NoExpiration] [-Notes <String>]
```

<span data-ttu-id="42cc2-216">In diesem Beispiel wird das Ablaufdatum des angegebenen Eintrags geändert.</span><span class="sxs-lookup"><span data-stu-id="42cc2-216">This example changes the expiration date of the specified entry.</span></span>

```powershell
Set-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSRAAAA" -ExpirationDate (Get-Date "5/30/2020 9:30 AM").ToUniversalTime()
```

<span data-ttu-id="42cc2-217">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Sets-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/set-tenantallowblocklistitems).</span><span class="sxs-lookup"><span data-stu-id="42cc2-217">For detailed syntax and parameter information, see [Set-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/set-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-remove-url-and-file-entries-from-the-tenant-allowblock-list"></a><span data-ttu-id="42cc2-218">Verwenden von PowerShell zum Entfernen von URL-und Dateieinträgen aus der Liste "Mandanten zulassen/blockieren"</span><span class="sxs-lookup"><span data-stu-id="42cc2-218">Use PowerShell to remove URL and file entries from the Tenant Allow/Block List</span></span>

<span data-ttu-id="42cc2-219">Verwenden Sie die folgende Syntax, um URL-und Dateieinträge aus der Liste Mandanten Allow/Block zu entfernen:</span><span class="sxs-lookup"><span data-stu-id="42cc2-219">To remove URL and file entries from the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Remove-TenantAllowBlockListItems -ListType <Url | FileHash> -Ids <"Id1","Id2",..."IdN">
```

<span data-ttu-id="42cc2-220">In diesem Beispiel wird der angegebene URL-Eintrag aus der Liste Mandanten-Allow/Block entfernt.</span><span class="sxs-lookup"><span data-stu-id="42cc2-220">This example removes the specified URL entry from the Tenant Allow/Block List.</span></span>

```powershell
Remove-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSPAAAA0"
```

<span data-ttu-id="42cc2-221">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Remove-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/remove-tenantallowblocklistitems).</span><span class="sxs-lookup"><span data-stu-id="42cc2-221">For detailed syntax and parameter information, see [Remove-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/remove-tenantallowblocklistitems).</span></span>

## <a name="url-syntax-for-the-tenant-allowblock-list"></a><span data-ttu-id="42cc2-222">URL-Syntax für die Liste "Mandanten zulassen/blockieren"</span><span class="sxs-lookup"><span data-stu-id="42cc2-222">URL syntax for the Tenant Allow/Block List</span></span>

- <span data-ttu-id="42cc2-223">IP4v-und IPv6-Adressen sind zulässig, TCP/UDP-Ports jedoch nicht.</span><span class="sxs-lookup"><span data-stu-id="42cc2-223">IP4v and IPv6 addresses are allowed, but TCP/UDP ports are not.</span></span>

- <span data-ttu-id="42cc2-224">Dateinamenerweiterungen sind nicht zulässig (beispielsweise Test. pdf).</span><span class="sxs-lookup"><span data-stu-id="42cc2-224">Filename extensions are not allowed (for example, test.pdf).</span></span>

- <span data-ttu-id="42cc2-225">Unicode wird nicht unterstützt, aber Punycode ist.</span><span class="sxs-lookup"><span data-stu-id="42cc2-225">Unicode is not supported, but Punycode is.</span></span>

- <span data-ttu-id="42cc2-226">Hostnames sind zulässig, wenn alle der folgenden Aussagen zutreffen:</span><span class="sxs-lookup"><span data-stu-id="42cc2-226">Hostnames are allowed if all of the following statements are true:</span></span>

  - <span data-ttu-id="42cc2-227">Der Hostname enthält einen Punkt.</span><span class="sxs-lookup"><span data-stu-id="42cc2-227">The hostname contains a period.</span></span>
  - <span data-ttu-id="42cc2-228">Es gibt mindestens ein Zeichen auf der linken Seite des Punkts.</span><span class="sxs-lookup"><span data-stu-id="42cc2-228">There is at least one character to the left of the period.</span></span>
  - <span data-ttu-id="42cc2-229">Rechts vom Punkt befinden sich mindestens zwei Zeichen.</span><span class="sxs-lookup"><span data-stu-id="42cc2-229">There are at least two characters to the right of the period.</span></span>

  <span data-ttu-id="42cc2-230">Beispielsweise `t.co` ist zulässig; `.com` oder ist `contoso.` nicht zulässig.</span><span class="sxs-lookup"><span data-stu-id="42cc2-230">For example, `t.co` is allowed; `.com` or `contoso.` are not allowed.</span></span>

- <span data-ttu-id="42cc2-231">Unterpfade sind nicht impliziert.</span><span class="sxs-lookup"><span data-stu-id="42cc2-231">Subpaths are not implied.</span></span>

  <span data-ttu-id="42cc2-232">Enthält beispielsweise `contoso.com` nicht `contoso.com/a` .</span><span class="sxs-lookup"><span data-stu-id="42cc2-232">For example, `contoso.com` does not include `contoso.com/a`.</span></span>

- <span data-ttu-id="42cc2-233">Platzhalterzeichen (\*) sind in den folgenden Szenarien zulässig:</span><span class="sxs-lookup"><span data-stu-id="42cc2-233">Wildcards (\*) are allowed in the following scenarios:</span></span>

  - <span data-ttu-id="42cc2-234">Auf einen linken Platzhalter muss ein Punkt folgen, um eine Unterdomäne anzugeben.</span><span class="sxs-lookup"><span data-stu-id="42cc2-234">A left wildcard must be followed by a period to specify a subdomain.</span></span>

    <span data-ttu-id="42cc2-235">Beispielsweise `*.contoso.com` ist zulässig; `*contoso.com` ist nicht zulässig.</span><span class="sxs-lookup"><span data-stu-id="42cc2-235">For example, `*.contoso.com` is allowed; `*contoso.com` is not allowed.</span></span>

  - <span data-ttu-id="42cc2-236">Ein rechter Platzhalter muss einem Schrägstrich (/) entsprechen, um einen Pfad anzugeben.</span><span class="sxs-lookup"><span data-stu-id="42cc2-236">A right wildcard must follow a forward slash (/) to specify a path.</span></span>

    <span data-ttu-id="42cc2-237">Beispielsweise `contoso.com/*` ist zulässig; `contoso.com*` oder ist `contoso.com/ab*` nicht zulässig.</span><span class="sxs-lookup"><span data-stu-id="42cc2-237">For example, `contoso.com/*` is allowed; `contoso.com*` or `contoso.com/ab*` are not allowed.</span></span>

  - <span data-ttu-id="42cc2-238">Alle untergeordneten Pfade sind nicht durch einen richtigen Platzhalter impliziert.</span><span class="sxs-lookup"><span data-stu-id="42cc2-238">All subpaths are not implied by a right wildcard.</span></span>

    <span data-ttu-id="42cc2-239">Enthält beispielsweise `contoso.com/*` nicht `contoso.com/a` .</span><span class="sxs-lookup"><span data-stu-id="42cc2-239">For example, `contoso.com/*` does not include `contoso.com/a`.</span></span>

  - <span data-ttu-id="42cc2-240">`*.com*`ist ungültig (keine auflösbare Domäne, und der Rechte Platzhalter folgt keinem Schrägstrich).</span><span class="sxs-lookup"><span data-stu-id="42cc2-240">`*.com*` is invalid (not a resolvable domain and the right wildcard does not follow a forward slash).</span></span>

  - <span data-ttu-id="42cc2-241">Platzhalter sind in IP-Adressen nicht zulässig.</span><span class="sxs-lookup"><span data-stu-id="42cc2-241">Wildcards are not allowed in IP addresses.</span></span>

- <span data-ttu-id="42cc2-242">Das Tildezeichen (~) steht in den folgenden Szenarien zur Verfügung:</span><span class="sxs-lookup"><span data-stu-id="42cc2-242">The tilde (~) character is available in the following scenarios:</span></span>

  - <span data-ttu-id="42cc2-243">Eine linke Tilde impliziert eine Domäne und alle Unterdomänen.</span><span class="sxs-lookup"><span data-stu-id="42cc2-243">A left tilde implies a domain and all subdomains.</span></span>

    <span data-ttu-id="42cc2-244">Beispielsweise `~contoso.com` enthält `contoso.com` und `*.contoso.com` .</span><span class="sxs-lookup"><span data-stu-id="42cc2-244">For example `~contoso.com` includes `contoso.com` and `*.contoso.com`.</span></span>

- <span data-ttu-id="42cc2-245">URL-Einträge, die Protokolle enthalten (beispielsweise,, `http://` `https://` oder `ftp://` ) schlagen fehl, da URL-Einträge auf alle Protokolle angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="42cc2-245">URL entries that contain protocols (for example, `http://`, `https://`, or `ftp://`) will fail, because URL entries apply to all protocols.</span></span>

- <span data-ttu-id="42cc2-246">Ein Benutzername oder ein Kennwort werden nicht unterstützt oder erforderlich.</span><span class="sxs-lookup"><span data-stu-id="42cc2-246">A username or password aren't supported or required.</span></span>

- <span data-ttu-id="42cc2-247">Anführungszeichen (' oder ') sind ungültige Zeichen.</span><span class="sxs-lookup"><span data-stu-id="42cc2-247">Quotes (' or ") are invalid characters.</span></span>

- <span data-ttu-id="42cc2-248">Eine URL sollte nach Möglichkeit alle Umleitungen enthalten.</span><span class="sxs-lookup"><span data-stu-id="42cc2-248">A URL should include all redirects where possible.</span></span>

### <a name="url-entry-scenarios"></a><span data-ttu-id="42cc2-249">URL-Eintrags Szenarien</span><span class="sxs-lookup"><span data-stu-id="42cc2-249">URL entry scenarios</span></span>

<span data-ttu-id="42cc2-250">In den folgenden Abschnitten werden gültige URL-Einträge und ihre Ergebnisse beschrieben.</span><span class="sxs-lookup"><span data-stu-id="42cc2-250">Valid URL entries and their results are described in the following sections.</span></span>

#### <a name="scenario-no-wildcards"></a><span data-ttu-id="42cc2-251">Szenario: keine Platzhalter</span><span class="sxs-lookup"><span data-stu-id="42cc2-251">Scenario: No wildcards</span></span>

<span data-ttu-id="42cc2-252">**Eintrag**:`contoso.com`</span><span class="sxs-lookup"><span data-stu-id="42cc2-252">**Entry**: `contoso.com`</span></span>

- <span data-ttu-id="42cc2-253">**Übereinstimmung zulassen**: contoso.com</span><span class="sxs-lookup"><span data-stu-id="42cc2-253">**Allow match**: contoso.com</span></span>

- <span data-ttu-id="42cc2-254">**Zulassen nicht abgeglichen**:</span><span class="sxs-lookup"><span data-stu-id="42cc2-254">**Allow not matched**:</span></span>

  - <span data-ttu-id="42cc2-255">abc-contoso.com</span><span class="sxs-lookup"><span data-stu-id="42cc2-255">abc-contoso.com</span></span>
  - <span data-ttu-id="42cc2-256">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="42cc2-256">contoso.com/a</span></span>
  - <span data-ttu-id="42cc2-257">payroll.contoso.com</span><span class="sxs-lookup"><span data-stu-id="42cc2-257">payroll.contoso.com</span></span>
  - <span data-ttu-id="42cc2-258">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="42cc2-258">test.com/contoso.com</span></span>
  - <span data-ttu-id="42cc2-259">test.com/q=contoso.com</span><span class="sxs-lookup"><span data-stu-id="42cc2-259">test.com/q=contoso.com</span></span>
  - <span data-ttu-id="42cc2-260">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="42cc2-260">www.contoso.com</span></span>
  - <span data-ttu-id="42cc2-261">www. contoso. com/q = a@contoso. com</span><span class="sxs-lookup"><span data-stu-id="42cc2-261">www.contoso.com/q=a@contoso.com</span></span>
  
- <span data-ttu-id="42cc2-262">**Block Übereinstimmung**:</span><span class="sxs-lookup"><span data-stu-id="42cc2-262">**Block match**:</span></span>

  - <span data-ttu-id="42cc2-263">contoso.com</span><span class="sxs-lookup"><span data-stu-id="42cc2-263">contoso.com</span></span>
  - <span data-ttu-id="42cc2-264">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="42cc2-264">contoso.com/a</span></span>
  - <span data-ttu-id="42cc2-265">payroll.contoso.com</span><span class="sxs-lookup"><span data-stu-id="42cc2-265">payroll.contoso.com</span></span>
  - <span data-ttu-id="42cc2-266">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="42cc2-266">test.com/contoso.com</span></span>
  - <span data-ttu-id="42cc2-267">test.com/q=contoso.com</span><span class="sxs-lookup"><span data-stu-id="42cc2-267">test.com/q=contoso.com</span></span>
  - <span data-ttu-id="42cc2-268">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="42cc2-268">www.contoso.com</span></span>
  - <span data-ttu-id="42cc2-269">www. contoso. com/q = a@contoso. com</span><span class="sxs-lookup"><span data-stu-id="42cc2-269">www.contoso.com/q=a@contoso.com</span></span>

- <span data-ttu-id="42cc2-270">**Block nicht abgeglichen**: ABC-contoso.com</span><span class="sxs-lookup"><span data-stu-id="42cc2-270">**Block not matched**: abc-contoso.com</span></span>

#### <a name="scenario-left-wildcard-subdomain"></a><span data-ttu-id="42cc2-271">Szenario: Linker Platzhalter (Unterdomäne)</span><span class="sxs-lookup"><span data-stu-id="42cc2-271">Scenario: Left wildcard (subdomain)</span></span>

<span data-ttu-id="42cc2-272">**Eintrag**:`*.contoso.com`</span><span class="sxs-lookup"><span data-stu-id="42cc2-272">**Entry**: `*.contoso.com`</span></span>

- <span data-ttu-id="42cc2-273">Übereinstimmung und **Block Übereinstimmung** **zulassen** :</span><span class="sxs-lookup"><span data-stu-id="42cc2-273">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="42cc2-274">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="42cc2-274">www.contoso.com</span></span>
  - <span data-ttu-id="42cc2-275">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="42cc2-275">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="42cc2-276">**Zulassen nicht abgeglichen** und **Block nicht abgeglichen**:</span><span class="sxs-lookup"><span data-stu-id="42cc2-276">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="42cc2-277">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="42cc2-277">123contoso.com</span></span>
  - <span data-ttu-id="42cc2-278">contoso.com</span><span class="sxs-lookup"><span data-stu-id="42cc2-278">contoso.com</span></span>
  - <span data-ttu-id="42cc2-279">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="42cc2-279">test.com/contoso.com</span></span>
  - <span data-ttu-id="42cc2-280">www.contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="42cc2-280">www.contoso.com/abc</span></span>
  
#### <a name="scenario-right-wildcard-at-top-of-path"></a><span data-ttu-id="42cc2-281">Szenario: rechter Platzhalter oben im Pfad</span><span class="sxs-lookup"><span data-stu-id="42cc2-281">Scenario: Right wildcard at top of path</span></span>

<span data-ttu-id="42cc2-282">**Eintrag**:`contoso.com/a/*`</span><span class="sxs-lookup"><span data-stu-id="42cc2-282">**Entry**: `contoso.com/a/*`</span></span>

- <span data-ttu-id="42cc2-283">Übereinstimmung und **Block Übereinstimmung** **zulassen** :</span><span class="sxs-lookup"><span data-stu-id="42cc2-283">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="42cc2-284">contoso.com/a/b</span><span class="sxs-lookup"><span data-stu-id="42cc2-284">contoso.com/a/b</span></span>
  - <span data-ttu-id="42cc2-285">contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="42cc2-285">contoso.com/a/b/c</span></span>
  - <span data-ttu-id="42cc2-286">contoso. com/a/? q = Joe@t. com</span><span class="sxs-lookup"><span data-stu-id="42cc2-286">contoso.com/a/?q=joe@t.com</span></span>

- <span data-ttu-id="42cc2-287">**Zulassen nicht abgeglichen** und **Block nicht abgeglichen**:</span><span class="sxs-lookup"><span data-stu-id="42cc2-287">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="42cc2-288">contoso.com</span><span class="sxs-lookup"><span data-stu-id="42cc2-288">contoso.com</span></span>
  - <span data-ttu-id="42cc2-289">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="42cc2-289">contoso.com/a</span></span>
  - <span data-ttu-id="42cc2-290">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="42cc2-290">www.contoso.com</span></span>
  - <span data-ttu-id="42cc2-291">www. contoso. com/q = a@contoso. com</span><span class="sxs-lookup"><span data-stu-id="42cc2-291">www.contoso.com/q=a@contoso.com</span></span>
  
#### <a name="scenario-left-tilde"></a><span data-ttu-id="42cc2-292">Szenario: linke Tilde</span><span class="sxs-lookup"><span data-stu-id="42cc2-292">Scenario: Left tilde</span></span>

<span data-ttu-id="42cc2-293">**Eintrag**:`~contoso.com`</span><span class="sxs-lookup"><span data-stu-id="42cc2-293">**Entry**: `~contoso.com`</span></span>

- <span data-ttu-id="42cc2-294">Übereinstimmung und **Block Übereinstimmung** **zulassen** :</span><span class="sxs-lookup"><span data-stu-id="42cc2-294">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="42cc2-295">contoso.com</span><span class="sxs-lookup"><span data-stu-id="42cc2-295">contoso.com</span></span>
  - <span data-ttu-id="42cc2-296">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="42cc2-296">www.contoso.com</span></span>
  - <span data-ttu-id="42cc2-297">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="42cc2-297">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="42cc2-298">**Zulassen nicht abgeglichen** und **Block nicht abgeglichen**:</span><span class="sxs-lookup"><span data-stu-id="42cc2-298">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="42cc2-299">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="42cc2-299">123contoso.com</span></span>
  - <span data-ttu-id="42cc2-300">contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="42cc2-300">contoso.com/abc</span></span>
  - <span data-ttu-id="42cc2-301">www.contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="42cc2-301">www.contoso.com/abc</span></span>

#### <a name="scenario-right-wildcard-suffix"></a><span data-ttu-id="42cc2-302">Szenario: Rechtes Platzhalter Suffix</span><span class="sxs-lookup"><span data-stu-id="42cc2-302">Scenario: Right wildcard suffix</span></span>

<span data-ttu-id="42cc2-303">**Eintrag**:`contoso.com/*`</span><span class="sxs-lookup"><span data-stu-id="42cc2-303">**Entry**: `contoso.com/*`</span></span>

- <span data-ttu-id="42cc2-304">Übereinstimmung und **Block Übereinstimmung** **zulassen** :</span><span class="sxs-lookup"><span data-stu-id="42cc2-304">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="42cc2-305">contoso. com/? q = whatever@fabrikam. com</span><span class="sxs-lookup"><span data-stu-id="42cc2-305">contoso.com/?q=whatever@fabrikam.com</span></span>
  - <span data-ttu-id="42cc2-306">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="42cc2-306">contoso.com/a</span></span>
  - <span data-ttu-id="42cc2-307">contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="42cc2-307">contoso.com/a/b/c</span></span>
  - <span data-ttu-id="42cc2-308">contoso.com/ab</span><span class="sxs-lookup"><span data-stu-id="42cc2-308">contoso.com/ab</span></span>
  - <span data-ttu-id="42cc2-309">contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="42cc2-309">contoso.com/b</span></span>
  - <span data-ttu-id="42cc2-310">contoso.com/b/a/c</span><span class="sxs-lookup"><span data-stu-id="42cc2-310">contoso.com/b/a/c</span></span>
  - <span data-ttu-id="42cc2-311">contoso.com/ba</span><span class="sxs-lookup"><span data-stu-id="42cc2-311">contoso.com/ba</span></span>

- <span data-ttu-id="42cc2-312">**Allow NOT MATCHED** and **Block NOT MATCHED**: contoso.com</span><span class="sxs-lookup"><span data-stu-id="42cc2-312">**Allow not matched** and **Block not matched**: contoso.com</span></span>

#### <a name="scenario-left-wildcard-subdomain-and-right-wildcard-suffix"></a><span data-ttu-id="42cc2-313">Szenario: linke Platzhalter-Unterdomäne und Rechte Platzhalter Suffix</span><span class="sxs-lookup"><span data-stu-id="42cc2-313">Scenario: Left wildcard subdomain and right wildcard suffix</span></span>

<span data-ttu-id="42cc2-314">**Eintrag**:`*.contoso.com/*`</span><span class="sxs-lookup"><span data-stu-id="42cc2-314">**Entry**: `*.contoso.com/*`</span></span>

- <span data-ttu-id="42cc2-315">Übereinstimmung und **Block Übereinstimmung** **zulassen** :</span><span class="sxs-lookup"><span data-stu-id="42cc2-315">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="42cc2-316">abc.contoso.com/ab</span><span class="sxs-lookup"><span data-stu-id="42cc2-316">abc.contoso.com/ab</span></span>
  - <span data-ttu-id="42cc2-317">abc.xyz.contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="42cc2-317">abc.xyz.contoso.com/a/b/c</span></span>
  - <span data-ttu-id="42cc2-318">www.contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="42cc2-318">www.contoso.com/a</span></span>
  - <span data-ttu-id="42cc2-319">www.contoso.com/b/a/c</span><span class="sxs-lookup"><span data-stu-id="42cc2-319">www.contoso.com/b/a/c</span></span>
  - <span data-ttu-id="42cc2-320">xyz.contoso.com/ba</span><span class="sxs-lookup"><span data-stu-id="42cc2-320">xyz.contoso.com/ba</span></span>

- <span data-ttu-id="42cc2-321">**Allow NOT MATCHED** and **Block NOT MATCHED**: contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="42cc2-321">**Allow not matched** and **Block not matched**: contoso.com/b</span></span>

#### <a name="scenario-left-and-right-tilde"></a><span data-ttu-id="42cc2-322">Szenario: linke und Rechte Tilde</span><span class="sxs-lookup"><span data-stu-id="42cc2-322">Scenario: Left and right tilde</span></span>

<span data-ttu-id="42cc2-323">**Eintrag**:`~contoso.com~`</span><span class="sxs-lookup"><span data-stu-id="42cc2-323">**Entry**: `~contoso.com~`</span></span>

- <span data-ttu-id="42cc2-324">Übereinstimmung und **Block Übereinstimmung** **zulassen** :</span><span class="sxs-lookup"><span data-stu-id="42cc2-324">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="42cc2-325">contoso.com</span><span class="sxs-lookup"><span data-stu-id="42cc2-325">contoso.com</span></span>
  - <span data-ttu-id="42cc2-326">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="42cc2-326">contoso.com/a</span></span>
  - <span data-ttu-id="42cc2-327">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="42cc2-327">www.contoso.com</span></span>
  - <span data-ttu-id="42cc2-328">www.contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="42cc2-328">www.contoso.com/b</span></span>
  - <span data-ttu-id="42cc2-329">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="42cc2-329">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="42cc2-330">**Zulassen nicht abgeglichen** und **Block nicht abgeglichen**:</span><span class="sxs-lookup"><span data-stu-id="42cc2-330">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="42cc2-331">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="42cc2-331">123contoso.com</span></span>
  - <span data-ttu-id="42cc2-332">contoso.org</span><span class="sxs-lookup"><span data-stu-id="42cc2-332">contoso.org</span></span>

#### <a name="scenario-ip-address"></a><span data-ttu-id="42cc2-333">Szenario: IP-Adresse</span><span class="sxs-lookup"><span data-stu-id="42cc2-333">Scenario: IP address</span></span>

<span data-ttu-id="42cc2-334">**Eintrag**:`1.2.3.4`</span><span class="sxs-lookup"><span data-stu-id="42cc2-334">**Entry**: `1.2.3.4`</span></span>

- <span data-ttu-id="42cc2-335">Übereinstimmung **zulassen** und **Block Übereinstimmung**: 1.2.3.4</span><span class="sxs-lookup"><span data-stu-id="42cc2-335">**Allow match** and **Block match**: 1.2.3.4</span></span>

- <span data-ttu-id="42cc2-336">**Zulassen nicht abgeglichen** und **Block nicht abgeglichen**:</span><span class="sxs-lookup"><span data-stu-id="42cc2-336">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="42cc2-337">1.2.3.4/a</span><span class="sxs-lookup"><span data-stu-id="42cc2-337">1.2.3.4/a</span></span>
  - <span data-ttu-id="42cc2-338">11.2.3.4/a</span><span class="sxs-lookup"><span data-stu-id="42cc2-338">11.2.3.4/a</span></span>

#### <a name="ip-address-with-right-wildcard"></a><span data-ttu-id="42cc2-339">IP-Adresse mit dem richtigen Platzhalter</span><span class="sxs-lookup"><span data-stu-id="42cc2-339">IP address with right wildcard</span></span>

<span data-ttu-id="42cc2-340">**Eintrag**:`1.2.3.4/*`</span><span class="sxs-lookup"><span data-stu-id="42cc2-340">**Entry**: `1.2.3.4/*`</span></span>

- <span data-ttu-id="42cc2-341">Übereinstimmung und **Block Übereinstimmung** **zulassen** :</span><span class="sxs-lookup"><span data-stu-id="42cc2-341">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="42cc2-342">1.2.3.4/b</span><span class="sxs-lookup"><span data-stu-id="42cc2-342">1.2.3.4/b</span></span>
  - <span data-ttu-id="42cc2-343">1.2.3.4/baaaa</span><span class="sxs-lookup"><span data-stu-id="42cc2-343">1.2.3.4/baaaa</span></span>

### <a name="examples-of-invalid-entries"></a><span data-ttu-id="42cc2-344">Beispiele für ungültige Einträge</span><span class="sxs-lookup"><span data-stu-id="42cc2-344">Examples of invalid entries</span></span>

<span data-ttu-id="42cc2-345">Die folgenden Einträge sind ungültig:</span><span class="sxs-lookup"><span data-stu-id="42cc2-345">The following entries are invalid:</span></span>

- <span data-ttu-id="42cc2-346">**Fehlende oder ungültige Domänenwerte**:</span><span class="sxs-lookup"><span data-stu-id="42cc2-346">**Missing or invalid domain values**:</span></span>

  - <span data-ttu-id="42cc2-347">contoso</span><span class="sxs-lookup"><span data-stu-id="42cc2-347">contoso</span></span>
  - <span data-ttu-id="42cc2-348">\*contoso.\*</span><span class="sxs-lookup"><span data-stu-id="42cc2-348">\*.contoso.\*</span></span>
  - <span data-ttu-id="42cc2-349">\*. com</span><span class="sxs-lookup"><span data-stu-id="42cc2-349">\*.com</span></span>
  - <span data-ttu-id="42cc2-350">\*.PDF</span><span class="sxs-lookup"><span data-stu-id="42cc2-350">\*.pdf</span></span>

- <span data-ttu-id="42cc2-351">**Platzhalter für Text oder ohne Leerzeichen**:</span><span class="sxs-lookup"><span data-stu-id="42cc2-351">**Wildcard on text or without spacing characters**:</span></span>

  - <span data-ttu-id="42cc2-352">\*contoso.com</span><span class="sxs-lookup"><span data-stu-id="42cc2-352">\*contoso.com</span></span>
  - <span data-ttu-id="42cc2-353">contoso.com\*</span><span class="sxs-lookup"><span data-stu-id="42cc2-353">contoso.com\*</span></span>
  - <span data-ttu-id="42cc2-354">\*1.2.3.4</span><span class="sxs-lookup"><span data-stu-id="42cc2-354">\*1.2.3.4</span></span>
  - <span data-ttu-id="42cc2-355">1.2.3.4\*</span><span class="sxs-lookup"><span data-stu-id="42cc2-355">1.2.3.4\*</span></span>
  - <span data-ttu-id="42cc2-356">contoso.com/a\*</span><span class="sxs-lookup"><span data-stu-id="42cc2-356">contoso.com/a\*</span></span>
  - <span data-ttu-id="42cc2-357">contoso.com/ab\*</span><span class="sxs-lookup"><span data-stu-id="42cc2-357">contoso.com/ab\*</span></span>

- <span data-ttu-id="42cc2-358">**IP-Adressen mit Ports**:</span><span class="sxs-lookup"><span data-stu-id="42cc2-358">**IP addresses with ports**:</span></span>

  - <span data-ttu-id="42cc2-359">contoso.com:443</span><span class="sxs-lookup"><span data-stu-id="42cc2-359">contoso.com:443</span></span>
  - <span data-ttu-id="42cc2-360">abc.contoso.com:25</span><span class="sxs-lookup"><span data-stu-id="42cc2-360">abc.contoso.com:25</span></span>

- <span data-ttu-id="42cc2-361">**Nicht beschreibende Platzhalter**:</span><span class="sxs-lookup"><span data-stu-id="42cc2-361">**Non-descriptive wildcards**:</span></span>

  - \*
  - <span data-ttu-id="42cc2-362">\*.\*</span><span class="sxs-lookup"><span data-stu-id="42cc2-362">\*.\*</span></span>

- <span data-ttu-id="42cc2-363">**Mittlere Platzhalter**:</span><span class="sxs-lookup"><span data-stu-id="42cc2-363">**Middle wildcards**:</span></span>

  - <span data-ttu-id="42cc2-364">Conto \* so.com</span><span class="sxs-lookup"><span data-stu-id="42cc2-364">conto\*so.com</span></span>
  - <span data-ttu-id="42cc2-365">Conto ~ so. com</span><span class="sxs-lookup"><span data-stu-id="42cc2-365">conto~so.com</span></span>

- <span data-ttu-id="42cc2-366">**Doppelte Platzhalter**</span><span class="sxs-lookup"><span data-stu-id="42cc2-366">**Double wildcards**</span></span>

  - <span data-ttu-id="42cc2-367">contoso.com/\*\*</span><span class="sxs-lookup"><span data-stu-id="42cc2-367">contoso.com/\*\*</span></span>
  - <span data-ttu-id="42cc2-368">contoso.com/\*/\*</span><span class="sxs-lookup"><span data-stu-id="42cc2-368">contoso.com/\*/\*</span></span>
