---
title: Verwalten Ihrer zulässigen und blockierten URLs in der Liste "Mandanten zulassen/blockieren"
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
description: Administratoren können erfahren, wie Sie URL-Einträge in der Liste Mandanten-Allow/Block im Security & Compliance Center konfigurieren.
ms.openlocfilehash: 5ff34cca922f18a015bd9da847facc8177cf8790
ms.sourcegitcommit: 89178b8f20d59ca88cfca303a13062b91fbeae9d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "46552550"
---
# <a name="manage-urls-in-the-tenant-allowblock-list"></a><span data-ttu-id="f4e33-103">Verwalten von URLs in der Liste "Mandanten zulassen/blockieren"</span><span class="sxs-lookup"><span data-stu-id="f4e33-103">Manage URLs in the Tenant Allow/Block List</span></span>

> [!NOTE]
> <span data-ttu-id="f4e33-104">Die in diesem Thema beschriebenen Funktionen befinden sich in der Vorschau, können sich ändern und sind nicht in allen Organisationen verfügbar.</span><span class="sxs-lookup"><span data-stu-id="f4e33-104">The features described in this topic are in Preview, are subject to change, and are not available in all organizations.</span></span>

<span data-ttu-id="f4e33-105">In Microsoft 365-Organisationen mit Postfächern in Exchange Online-oder eigenständigen Exchange Online Schutzorganisationen (EoP) ohne Exchange Online Postfächer können Sie mit dem EoP-Filter Urteil nicht einverstanden sein.</span><span class="sxs-lookup"><span data-stu-id="f4e33-105">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, you might disagree with the EOP filtering verdict.</span></span> <span data-ttu-id="f4e33-106">Beispielsweise kann eine gute Nachricht als "schlecht" markiert werden (ein falsch positives Ergebnis), oder es ist möglicherweise eine ungültige Meldung zulässig (ein falsches negativ).</span><span class="sxs-lookup"><span data-stu-id="f4e33-106">For example, a good message might be marked as bad (a false positive), or a bad message might be allowed through (a false negative).</span></span>

<span data-ttu-id="f4e33-107">In der Liste Mandanten-Allow/Block im Security & Compliance Center haben Sie die Möglichkeit, die Microsoft 365-Filter Urteile manuell außer Kraft zu setzen.</span><span class="sxs-lookup"><span data-stu-id="f4e33-107">The Tenant Allow/Block List in the Security & Compliance Center gives you a way to manually override the Microsoft 365 filtering verdicts.</span></span> <span data-ttu-id="f4e33-108">Die Mandanten-Zulassungs-und Sperrliste wird während des e-Mail-Flusses und zum Zeitpunkt der Benutzerklicks verwendet.</span><span class="sxs-lookup"><span data-stu-id="f4e33-108">The Tenant Allow/Block List is used during mail flow and at the time of user clicks.</span></span> <span data-ttu-id="f4e33-109">In der Liste Mandanten-Allow/Block können Sie URLs angeben, die zugelassen oder blockiert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="f4e33-109">You can specify URLs to allow or block in the Tenant Allow/Block List.</span></span>

<span data-ttu-id="f4e33-110">In diesem Thema wird beschrieben, wie Sie Einträge in der Liste "Allow/Block" des Mandanten im Security & Compliance Center oder in PowerShell (Exchange Online PowerShell für Microsoft 365-Organisationen mit Postfächern in Exchange Online; eigenständige EoP PowerShell für Organisationen ohne Exchange Online Postfächer) konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="f4e33-110">This topic describes how to configure entries in the Tenant Allow/Block List in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="f4e33-111">Was sollten Sie wissen, bevor Sie beginnen?</span><span class="sxs-lookup"><span data-stu-id="f4e33-111">What do you need to know before you begin?</span></span>

- <span data-ttu-id="f4e33-112">Sie öffnen das Security & Compliance Center unter <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="f4e33-112">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="f4e33-113">Wenn Sie direkt zur Seite **Mandanten-Zulassungs-und Sperrliste** wechseln möchten, verwenden Sie <https://protection.office.com/tenantAllowBlockList> .</span><span class="sxs-lookup"><span data-stu-id="f4e33-113">To go directly to the **Tenant Allow/Block List** page, use <https://protection.office.com/tenantAllowBlockList>.</span></span>

- <span data-ttu-id="f4e33-114">Die verfügbaren URL-Werte werden in der [URL-Syntax für den Abschnitt Mandanten-Zulassungs-und Sperrliste](#url-syntax-for-the-tenant-allowblock-list) weiter unten in diesem Thema beschrieben.</span><span class="sxs-lookup"><span data-stu-id="f4e33-114">The available URL values are described in the [URL syntax for the Tenant Allow/Block List](#url-syntax-for-the-tenant-allowblock-list) section later in this topic.</span></span>

- <span data-ttu-id="f4e33-115">Die Liste Mandanten Allow/Block erlaubt maximal 500 Einträge für URLs.</span><span class="sxs-lookup"><span data-stu-id="f4e33-115">The Tenant Allow/Block List allows a maximum of 500 entries for URLss.</span></span>

- <span data-ttu-id="f4e33-116">Ein Eintrag sollte innerhalb von 15 Minuten aktiv sein.</span><span class="sxs-lookup"><span data-stu-id="f4e33-116">An entry should be active within 15 minutes.</span></span>

- <span data-ttu-id="f4e33-117">Block Einträge haben Vorrang vor Zulassungs Einträgen.</span><span class="sxs-lookup"><span data-stu-id="f4e33-117">Block entries take precedence over allow entries.</span></span>

- <span data-ttu-id="f4e33-118">Standardmäßig laufen Einträge in der Liste Mandanten-Allow/Block nach 30 Tagen ab.</span><span class="sxs-lookup"><span data-stu-id="f4e33-118">By default, entries in the Tenant Allow/Block List will expire after 30 days.</span></span> <span data-ttu-id="f4e33-119">Sie können ein Datum angeben oder festlegen, dass es nie abläuft.</span><span class="sxs-lookup"><span data-stu-id="f4e33-119">You can specify a date or set them to never expire.</span></span>

- <span data-ttu-id="f4e33-120">Wie Sie eine Verbindung mit Exchange Online PowerShell herstellen, finden Sie unter [Herstellen einer Verbindung mit Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="f4e33-120">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="f4e33-121">Informationen zum Herstellen einer Verbindung mit dem eigenständigen Exchange Online Protection PowerShell finden Sie unter [Verbinden mit PowerShell in Exchange Online Protection](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="f4e33-121">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="f4e33-122">Bevor Sie die in diesem Artikel besprochenen Verfahren ausführen können, müssen Ihnen Berechtigungen zugewiesen werden:</span><span class="sxs-lookup"><span data-stu-id="f4e33-122">You need to be assigned permissions before you can do the procedures in this topic:</span></span>

  - <span data-ttu-id="f4e33-123">Zum Hinzufügen und Entfernen von Werten aus der Liste Mandanten-Allow/Block müssen Sie Mitglied einer der folgenden Rollengruppen sein:</span><span class="sxs-lookup"><span data-stu-id="f4e33-123">To add and remove values from the Tenant Allow/Block List, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="f4e33-124">**Organisationsverwaltung** oder **Sicherheitsadministrator** im [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="f4e33-124">**Organization Management** or **Security Administrator** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="f4e33-125">**Organisationsverwaltung** oder **Nachrichtenschutz** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span><span class="sxs-lookup"><span data-stu-id="f4e33-125">**Organization Management** or **Hygiene Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

  - <span data-ttu-id="f4e33-126">Für den schreibgeschützten Zugriff auf die Liste der Mandanten zulassen/blockieren müssen Sie Mitglied einer der folgenden Rollengruppen sein:</span><span class="sxs-lookup"><span data-stu-id="f4e33-126">For read-only access to the Tenant Allow/Block List, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="f4e33-127">**Security Reader** im [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="f4e33-127">**Security Reader** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="f4e33-128">**Schreibgeschützte Organisationsverwaltung** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span><span class="sxs-lookup"><span data-stu-id="f4e33-128">**View-Only Organization Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

## <a name="use-the-security--compliance-center-to-create-url-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="f4e33-129">Verwenden Sie das Security & Compliance Center, um URL-Einträge in der Liste Mandanten-Allow/Block zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="f4e33-129">Use the Security & Compliance Center to create URL entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="f4e33-130">Ausführliche Informationen zur Syntax für URL-Einträge finden Sie weiter unten in diesem Thema in der [URL-Syntax für den Abschnitt Allow/Block List für Mandanten](#url-syntax-for-the-tenant-allowblock-list) .</span><span class="sxs-lookup"><span data-stu-id="f4e33-130">For details about the syntax for URL entries, see the [URL syntax for the Tenant Allow/Block List](#url-syntax-for-the-tenant-allowblock-list) section later in this topic.</span></span>

1. <span data-ttu-id="f4e33-131">Wechseln Sie im Security & Compliance Center zu **Bedrohungs Verwaltungs** \> **Richtlinie** \> **Mandanten-Zulassungs-/Sperrlisten**.</span><span class="sxs-lookup"><span data-stu-id="f4e33-131">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="f4e33-132">Überprüfen Sie auf der Seite **Mandantenliste zulassen/blockieren** , dass die Registerkarte **URLs** ausgewählt ist, und klicken Sie dann auf **Hinzufügen** .</span><span class="sxs-lookup"><span data-stu-id="f4e33-132">On the **Tenant Allow/Block List** page, verify that the **URLs** tab is selected, and then click **Add**</span></span>

3. <span data-ttu-id="f4e33-133">Konfigurieren Sie im Flyout **neue URLs hinzufügen** , das angezeigt wird, die folgenden Einstellungen:</span><span class="sxs-lookup"><span data-stu-id="f4e33-133">In the **Add new URLs** flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="f4e33-134">**URLs mit Platzhaltern hinzufügen**: Geben Sie eine URL pro Reihe bis maximal 20 ein.</span><span class="sxs-lookup"><span data-stu-id="f4e33-134">**Add URLs with wildcards**: Enter one URL per line, up to a maximum of 20.</span></span>

   - <span data-ttu-id="f4e33-135">**Block/Allow**: Wählen Sie aus, ob die angegebenen URLs **zugelassen** oder **blockiert** werden sollen.</span><span class="sxs-lookup"><span data-stu-id="f4e33-135">**Block/Allow**: Select whether you want to **Allow** or **Block** the specified URLs.</span></span>

   - <span data-ttu-id="f4e33-136">**Nie ablaufen**: führen Sie einen der folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="f4e33-136">**Never expire**: Do one of the following steps:</span></span>

     - <span data-ttu-id="f4e33-137">Stellen Sie sicher, dass die Einstellung deaktiviert ist (deaktivieren ![ ](../../media/scc-toggle-off.png) ), und verwenden Sie das Feld **expires on** , um das Ablaufdatum für die Einträge anzugeben.</span><span class="sxs-lookup"><span data-stu-id="f4e33-137">Verify the setting is turned off (![Toggle off](../../media/scc-toggle-off.png)) and use the **Expires on** box to specify the expiration date for the entries.</span></span>

     <span data-ttu-id="f4e33-138">oder</span><span class="sxs-lookup"><span data-stu-id="f4e33-138">or</span></span>

     - <span data-ttu-id="f4e33-139">Bewegen Sie die Umschaltfläche nach rechts, um die Einträge so zu konfigurieren, dass Sie nie ablaufen:</span><span class="sxs-lookup"><span data-stu-id="f4e33-139">Move the toggle to the right to configure the entries to never expire:</span></span> ![Umschaltfläche ein](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png)<span data-ttu-id="f4e33-141">.</span><span class="sxs-lookup"><span data-stu-id="f4e33-141">.</span></span>

   - <span data-ttu-id="f4e33-142">**Optional Hinweis**: Geben Sie einen beschreibenden Text für die Einträge ein.</span><span class="sxs-lookup"><span data-stu-id="f4e33-142">**Optional note**: Enter descriptive text for the entries.</span></span>

4. <span data-ttu-id="f4e33-143">Wenn Sie fertig sind, klicken Sie auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="f4e33-143">When you're finished, click **Add**.</span></span>

## <a name="use-the-security--compliance-center-to-view-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="f4e33-144">Verwenden Sie das Security & Compliance Center, um Einträge in der Liste Mandanten-Allow/Block anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="f4e33-144">Use the Security & Compliance Center to view entries in the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="f4e33-145">Wechseln Sie im Security & Compliance Center zu **Bedrohungs Verwaltungs** \> **Richtlinie** \> **Mandanten-Zulassungs-/Sperrlisten**.</span><span class="sxs-lookup"><span data-stu-id="f4e33-145">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="f4e33-146">Wählen Sie die Registerkarte **URLs** aus.</span><span class="sxs-lookup"><span data-stu-id="f4e33-146">Select the **URLs** tab.</span></span>

<span data-ttu-id="f4e33-147">Klicken Sie auf die folgenden Spaltenüberschriften, um Sie in aufsteigender oder absteigender Reihenfolge zu sortieren:</span><span class="sxs-lookup"><span data-stu-id="f4e33-147">Click on the following column headings to sort in ascending or descending order:</span></span>

- <span data-ttu-id="f4e33-148">**Wert**</span><span class="sxs-lookup"><span data-stu-id="f4e33-148">**Value**</span></span>
- <span data-ttu-id="f4e33-149">**Aktion**: **blockieren** oder **zulassen**.</span><span class="sxs-lookup"><span data-stu-id="f4e33-149">**Action**: **Block** or **Allow**.</span></span>
- <span data-ttu-id="f4e33-150">**Datum der letzten Aktualisierung**</span><span class="sxs-lookup"><span data-stu-id="f4e33-150">**Last updated date**</span></span>
- <span data-ttu-id="f4e33-151">**Ablaufdatum**</span><span class="sxs-lookup"><span data-stu-id="f4e33-151">**Expiration date**</span></span>
- <span data-ttu-id="f4e33-152">**Hinweis**</span><span class="sxs-lookup"><span data-stu-id="f4e33-152">**Note**</span></span>

<span data-ttu-id="f4e33-153">Klicken Sie auf **Gruppieren** , um die Einträge nach **Aktion** (**blockieren** oder **zulassen**) oder **ohne**zu gruppieren.</span><span class="sxs-lookup"><span data-stu-id="f4e33-153">Click **Group** to group the entries by **Action** (**Block** or **Allow**) or **None**.</span></span>

<span data-ttu-id="f4e33-154">Klicken Sie auf **Suchen**, geben Sie einen Wert ganz oder teilweise ein, und drücken Sie dann die EINGABETASTE, um einen bestimmten Wert zu suchen.</span><span class="sxs-lookup"><span data-stu-id="f4e33-154">Click **Search**, enter all or part of a value, and then press ENTER to find a specific value.</span></span> <span data-ttu-id="f4e33-155">Wenn Sie fertig sind, klicken Sie auf **Such** ![ Symbol Löschen ](../../media/b6512677-5e7b-42b0-a8a3-3be1d7fa23ee.gif) .</span><span class="sxs-lookup"><span data-stu-id="f4e33-155">When you're finished, click **Clear search** ![Clear search icon](../../media/b6512677-5e7b-42b0-a8a3-3be1d7fa23ee.gif).</span></span>

<span data-ttu-id="f4e33-156">Klicken Sie auf **Filter**.</span><span class="sxs-lookup"><span data-stu-id="f4e33-156">Click **Filter**.</span></span> <span data-ttu-id="f4e33-157">Konfigurieren Sie im angezeigten **Filter** Flyout die folgenden Einstellungen:</span><span class="sxs-lookup"><span data-stu-id="f4e33-157">In the **Filter** flyout that appears, configure any of the following settings:</span></span>

- <span data-ttu-id="f4e33-158">**Aktion**: Wählen Sie **zulassen**, **blockieren** oder beides aus.</span><span class="sxs-lookup"><span data-stu-id="f4e33-158">**Action**: Select **Allow**, **Block** or both.</span></span>

- <span data-ttu-id="f4e33-159">**Läuft nie**ab: Wählen Sie aus (deaktivieren ![ ](../../media/scc-toggle-off.png) ) oder ein (Umschalten ![ ](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png) ) aus.</span><span class="sxs-lookup"><span data-stu-id="f4e33-159">**Never expire**: Select off (![Toggle off](../../media/scc-toggle-off.png)) or on (![Toggle on](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png)).</span></span>

- <span data-ttu-id="f4e33-160">**Letzte Aktualisierung**: Wählen Sie ein Startdatum (von), ein Enddatum (**an**) oder beides**aus**.</span><span class="sxs-lookup"><span data-stu-id="f4e33-160">**Last updated**: Select a start date (**From**), an end date (**To**) or both.</span></span>

- <span data-ttu-id="f4e33-161">**Ablaufdatum**: Wählen Sie ein Startdatum (von), ein Enddatum (**an**) oder beides**aus**.</span><span class="sxs-lookup"><span data-stu-id="f4e33-161">**Expiration date**: Select a start date (**From**), an end date (**To**) or both.</span></span>

<span data-ttu-id="f4e33-162">Wenn Sie fertig sind, klicken Sie auf über **nehmen**.</span><span class="sxs-lookup"><span data-stu-id="f4e33-162">When you're finished, click **Apply**.</span></span>

<span data-ttu-id="f4e33-163">Wenn Sie vorhandene Filter löschen möchten, klicken Sie auf **Filter**, und klicken Sie im daraufhin angezeigten **Filter** Flyout auf Filter **Löschen**.</span><span class="sxs-lookup"><span data-stu-id="f4e33-163">To clear existing filters, click **Filter**, and in the **Filter** flyout that appears, click **Clear filters**.</span></span>

## <a name="use-the-security--compliance-center-to-modify-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="f4e33-164">Verwenden des Security & Compliance Center zum Ändern von Einträgen in der Liste "Mandanten zulassen/blockieren"</span><span class="sxs-lookup"><span data-stu-id="f4e33-164">Use the Security & Compliance Center to modify entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="f4e33-165">Sie können den URL-Wert selbst nicht ändern.</span><span class="sxs-lookup"><span data-stu-id="f4e33-165">You can't modify the URL value itself.</span></span> <span data-ttu-id="f4e33-166">Stattdessen müssen Sie den Eintrag löschen und neu erstellen.</span><span class="sxs-lookup"><span data-stu-id="f4e33-166">Instead, you need to delete the entry and recreate it.</span></span>

1. <span data-ttu-id="f4e33-167">Wechseln Sie im Security & Compliance Center zu **Bedrohungs Verwaltungs** \> **Richtlinie** \> **Mandanten-Zulassungs-/Sperrlisten**.</span><span class="sxs-lookup"><span data-stu-id="f4e33-167">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="f4e33-168">Wählen Sie die Registerkarte **URLs** aus.</span><span class="sxs-lookup"><span data-stu-id="f4e33-168">Select the **URLs** tab.</span></span>

3. <span data-ttu-id="f4e33-169">Wählen Sie den Eintrag aus, den Sie ändern möchten, und klicken Sie dann auf Bearbeitungssymbol **Bearbeiten** ![ ](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) .</span><span class="sxs-lookup"><span data-stu-id="f4e33-169">Select the entry that you want to modify, and then click **Edit** ![Edit icon](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png).</span></span>

4. <span data-ttu-id="f4e33-170">Konfigurieren Sie im Flyout, das angezeigt wird, die folgenden Einstellungen:</span><span class="sxs-lookup"><span data-stu-id="f4e33-170">In the flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="f4e33-171">**Blockieren/zulassen**: Wählen Sie **zulassen** oder **blockieren**aus.</span><span class="sxs-lookup"><span data-stu-id="f4e33-171">**Block/Allow**: Select **Allow** or **Block**.</span></span>

   - <span data-ttu-id="f4e33-172">**Nie ablaufen**: führen Sie einen der folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="f4e33-172">**Never expire**: Do one of the following steps:</span></span>

     - <span data-ttu-id="f4e33-173">Stellen Sie sicher, dass die Einstellung deaktiviert ist (deaktivieren ![ ](../../media/scc-toggle-off.png) ), und verwenden Sie das Feld **expires on** , um das Ablaufdatum für den Eintrag anzugeben.</span><span class="sxs-lookup"><span data-stu-id="f4e33-173">Verify the setting is turned off (![Toggle off](../../media/scc-toggle-off.png)) and use the **Expires on** box to specify the expiration date for the entry.</span></span>

     <span data-ttu-id="f4e33-174">oder</span><span class="sxs-lookup"><span data-stu-id="f4e33-174">or</span></span>

     - <span data-ttu-id="f4e33-175">Bewegen Sie die Umschaltfläche nach rechts, um den Eintrag so zu konfigurieren, dass er nie abläuft:</span><span class="sxs-lookup"><span data-stu-id="f4e33-175">Move the toggle to the right to configure the entry to never expire:</span></span> ![Umschaltfläche ein](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png)<span data-ttu-id="f4e33-177">.</span><span class="sxs-lookup"><span data-stu-id="f4e33-177">.</span></span>

   - <span data-ttu-id="f4e33-178">**Optional Hinweis**: Geben Sie einen beschreibenden Text für den Eintrag ein.</span><span class="sxs-lookup"><span data-stu-id="f4e33-178">**Optional note**: Enter descriptive text for the entry.</span></span>

5. <span data-ttu-id="f4e33-179">Klicken Sie nach Abschluss des Vorgangs auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="f4e33-179">When you're finished, click **Save**.</span></span>

## <a name="use-the-security--compliance-center-to-remove-entries-from-the-tenant-allowblock-list"></a><span data-ttu-id="f4e33-180">Verwenden des Security & Compliance Center zum Entfernen von Einträgen aus der Liste "Mandanten zulassen/blockieren"</span><span class="sxs-lookup"><span data-stu-id="f4e33-180">Use the Security & Compliance Center to remove entries from the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="f4e33-181">Wechseln Sie im Security & Compliance Center zu **Bedrohungs Verwaltungs** \> **Richtlinie** \> **Mandanten-Zulassungs-/Sperrlisten**.</span><span class="sxs-lookup"><span data-stu-id="f4e33-181">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="f4e33-182">Wählen Sie die Registerkarte **URLs** aus.</span><span class="sxs-lookup"><span data-stu-id="f4e33-182">Select the **URLs** tab.</span></span>

3. <span data-ttu-id="f4e33-183">Wählen Sie den Eintrag aus, den Sie entfernen möchten, und klicken Sie **dann auf Delete** ![ Delete Icon ](../../media/87565fbb-5147-4f22-9ed7-1c18ce664392.png) .</span><span class="sxs-lookup"><span data-stu-id="f4e33-183">Select the entry that you want to remove, and then click **Delete** ![Delete icon](../../media/87565fbb-5147-4f22-9ed7-1c18ce664392.png).</span></span>

4. <span data-ttu-id="f4e33-184">Klicken Sie im angezeigten Warndialogfeld auf **Löschen**.</span><span class="sxs-lookup"><span data-stu-id="f4e33-184">In the warning dialog that appears, click **Delete**.</span></span>

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-the-tenant-allowblock-list"></a><span data-ttu-id="f4e33-185">Verwenden Exchange Online PowerShell oder eigenständiger EoP PowerShell zum Konfigurieren der Liste "Mandanten zulassen/blockieren"</span><span class="sxs-lookup"><span data-stu-id="f4e33-185">Use Exchange Online PowerShell or standalone EOP PowerShell to configure the Tenant Allow/Block List</span></span>

### <a name="use-powershell-to-add-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="f4e33-186">Verwenden von PowerShell zum Hinzufügen von Einträgen in der Liste "Mandanten zulassen/blockieren"</span><span class="sxs-lookup"><span data-stu-id="f4e33-186">Use PowerShell to add entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="f4e33-187">Verwenden Sie die folgende Syntax, um Einträge in der Liste Mandanten Allow/Block hinzuzufügen:</span><span class="sxs-lookup"><span data-stu-id="f4e33-187">To add entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
New-TenantAllowBlockListItems -ListType Url -Action <Allow | Block> -Entries <String[]> [-ExpirationDate <DateTime>] [-NoExpiration] [-Notes <String>]
```

<span data-ttu-id="f4e33-188">In diesem Beispiel wird ein URL-Sperreintrag für contoso.com und alle Unterdomänen hinzugefügt (beispielsweise contoso.com, www.contoso.com und XYZ.ABC.contoso.com).</span><span class="sxs-lookup"><span data-stu-id="f4e33-188">This example adds a URL block entry for contoso.com and all subdomains (for example, contoso.com, www.contoso.com, and xyz.abc.contoso.com).</span></span> <span data-ttu-id="f4e33-189">Da die Parameter ExpirationDate oder NOEXPIRE nicht verwendet wurden, läuft der Eintrag nach 30 Tagen ab.</span><span class="sxs-lookup"><span data-stu-id="f4e33-189">Because we didn't use the ExpirationDate or NoExpiration parameters, the entry expires after 30 days.</span></span>

```powershell
New-TenantAllowBlockListItem -ListType Url -Action Block -Entries ~contoso.com
```

<span data-ttu-id="f4e33-190">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [New-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/new-tenantallowblocklistitems).</span><span class="sxs-lookup"><span data-stu-id="f4e33-190">For detailed syntax and parameter information, see [New-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/new-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-view-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="f4e33-191">Verwenden von PowerShell zum Anzeigen von Einträgen in der Liste "Mandanten zulassen/blockieren"</span><span class="sxs-lookup"><span data-stu-id="f4e33-191">Use PowerShell to view entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="f4e33-192">Verwenden Sie die folgende Syntax, um Einträge in der Liste Mandanten Allow/Block anzuzeigen:</span><span class="sxs-lookup"><span data-stu-id="f4e33-192">To view entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType Url [-Entry <URLValue>] [-Action <Allow | Block>] [-ExpirationDate <DateTime>] [-NoExpiration]
```

<span data-ttu-id="f4e33-193">In diesem Beispiel werden alle blockierten URLs zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="f4e33-193">This example returns all blocked URLs.</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType Url -Action Block
```

<span data-ttu-id="f4e33-194">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Get-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/get-tenantallowblocklistitems).</span><span class="sxs-lookup"><span data-stu-id="f4e33-194">For detailed syntax and parameter information, see [Get-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/get-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-modify-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="f4e33-195">Verwenden von PowerShell zum Ändern von Einträgen in der Liste "Mandanten zulassen/blockieren"</span><span class="sxs-lookup"><span data-stu-id="f4e33-195">Use PowerShell to modify entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="f4e33-196">Sie können den URL-Wert selbst nicht ändern.</span><span class="sxs-lookup"><span data-stu-id="f4e33-196">You can't modify the URL value itself.</span></span> <span data-ttu-id="f4e33-197">Stattdessen müssen Sie den Eintrag löschen und neu erstellen.</span><span class="sxs-lookup"><span data-stu-id="f4e33-197">Instead, you need to delete the entry and recreate it.</span></span>

<span data-ttu-id="f4e33-198">Verwenden Sie die folgende Syntax, um Einträge in der Liste Mandanten Allow/Block zu ändern:</span><span class="sxs-lookup"><span data-stu-id="f4e33-198">To modify entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Set-TenantAllowBlockListItems -ListType Url -Ids <"Id1","Id2",..."IdN"> [-Action <Allow | Block>] [-ExpirationDate <DateTime>] [-NoExpiration] [-Notes <String>]
```

<span data-ttu-id="f4e33-199">In diesem Beispiel wird das Ablaufdatum des angegebenen Eintrags geändert.</span><span class="sxs-lookup"><span data-stu-id="f4e33-199">This example changes the expiration date of the specified entry.</span></span>

```powershell
Set-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSRAAAA" -ExpirationDate (Get-Date "5/30/2020 9:30 AM").ToUniversalTime()
```

<span data-ttu-id="f4e33-200">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Sets-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/set-tenantallowblocklistitems).</span><span class="sxs-lookup"><span data-stu-id="f4e33-200">For detailed syntax and parameter information, see [Set-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/set-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-remove-entries-from-the-tenant-allowblock-list"></a><span data-ttu-id="f4e33-201">Verwenden von PowerShell zum Entfernen von Einträgen aus der Liste "Mandanten zulassen/blockieren"</span><span class="sxs-lookup"><span data-stu-id="f4e33-201">Use PowerShell to remove entries from the Tenant Allow/Block List</span></span>

<span data-ttu-id="f4e33-202">Verwenden Sie die folgende Syntax, um Einträge aus der Liste Mandanten Allow/Block zu entfernen:</span><span class="sxs-lookup"><span data-stu-id="f4e33-202">To remove entries from the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Remove-TenantAllowBlockListItems -ListType Url -Ids <"Id1","Id2",..."IdN">
```

<span data-ttu-id="f4e33-203">In diesem Beispiel wird der angegebene URL-Eintrag aus der Liste Mandanten-Allow/Block entfernt.</span><span class="sxs-lookup"><span data-stu-id="f4e33-203">This example removes the specified URL entry from the Tenant Allow/Block List.</span></span>

```powershell
Remove-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSPAAAA0"
```

<span data-ttu-id="f4e33-204">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Remove-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/remove-tenantallowblocklistitems).</span><span class="sxs-lookup"><span data-stu-id="f4e33-204">For detailed syntax and parameter information, see [Remove-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/remove-tenantallowblocklistitems).</span></span>

## <a name="url-syntax-for-the-tenant-allowblock-list"></a><span data-ttu-id="f4e33-205">URL-Syntax für die Liste "Mandanten zulassen/blockieren"</span><span class="sxs-lookup"><span data-stu-id="f4e33-205">URL syntax for the Tenant Allow/Block List</span></span>

- <span data-ttu-id="f4e33-206">IP4v-und IPv6-Adressen sind zulässig, TCP/UDP-Ports jedoch nicht.</span><span class="sxs-lookup"><span data-stu-id="f4e33-206">IP4v and IPv6 addresses are allowed, but TCP/UDP ports are not.</span></span>

- <span data-ttu-id="f4e33-207">Dateierweiterungen sind nicht zulässig (beispielsweise test.pdf).</span><span class="sxs-lookup"><span data-stu-id="f4e33-207">Filename extensions are not allowed (for example, test.pdf).</span></span>

- <span data-ttu-id="f4e33-208">Unicode wird nicht unterstützt, aber Punycode ist.</span><span class="sxs-lookup"><span data-stu-id="f4e33-208">Unicode is not supported, but Punycode is.</span></span>

- <span data-ttu-id="f4e33-209">Hostnames sind zulässig, wenn alle der folgenden Aussagen zutreffen:</span><span class="sxs-lookup"><span data-stu-id="f4e33-209">Hostnames are allowed if all of the following statements are true:</span></span>

  - <span data-ttu-id="f4e33-210">Der Hostname enthält einen Punkt.</span><span class="sxs-lookup"><span data-stu-id="f4e33-210">The hostname contains a period.</span></span>
  - <span data-ttu-id="f4e33-211">Es gibt mindestens ein Zeichen auf der linken Seite des Punkts.</span><span class="sxs-lookup"><span data-stu-id="f4e33-211">There is at least one character to the left of the period.</span></span>
  - <span data-ttu-id="f4e33-212">Rechts vom Punkt befinden sich mindestens zwei Zeichen.</span><span class="sxs-lookup"><span data-stu-id="f4e33-212">There are at least two characters to the right of the period.</span></span>

  <span data-ttu-id="f4e33-213">Beispielsweise `t.co` ist zulässig; `.com` oder ist `contoso.` nicht zulässig.</span><span class="sxs-lookup"><span data-stu-id="f4e33-213">For example, `t.co` is allowed; `.com` or `contoso.` are not allowed.</span></span>

- <span data-ttu-id="f4e33-214">Unterpfade sind nicht impliziert.</span><span class="sxs-lookup"><span data-stu-id="f4e33-214">Subpaths are not implied.</span></span>

  <span data-ttu-id="f4e33-215">Enthält beispielsweise `contoso.com` nicht `contoso.com/a` .</span><span class="sxs-lookup"><span data-stu-id="f4e33-215">For example, `contoso.com` does not include `contoso.com/a`.</span></span>

- <span data-ttu-id="f4e33-216">Platzhalterzeichen (\*) sind in den folgenden Szenarien zulässig:</span><span class="sxs-lookup"><span data-stu-id="f4e33-216">Wildcards (\*) are allowed in the following scenarios:</span></span>

  - <span data-ttu-id="f4e33-217">Auf einen linken Platzhalter muss ein Punkt folgen, um eine Unterdomäne anzugeben.</span><span class="sxs-lookup"><span data-stu-id="f4e33-217">A left wildcard must be followed by a period to specify a subdomain.</span></span>

    <span data-ttu-id="f4e33-218">Beispielsweise `*.contoso.com` ist zulässig; `*contoso.com` ist nicht zulässig.</span><span class="sxs-lookup"><span data-stu-id="f4e33-218">For example, `*.contoso.com` is allowed; `*contoso.com` is not allowed.</span></span>

  - <span data-ttu-id="f4e33-219">Ein rechter Platzhalter muss einem Schrägstrich (/) entsprechen, um einen Pfad anzugeben.</span><span class="sxs-lookup"><span data-stu-id="f4e33-219">A right wildcard must follow a forward slash (/) to specify a path.</span></span>

    <span data-ttu-id="f4e33-220">Beispielsweise `contoso.com/*` ist zulässig; `contoso.com*` oder ist `contoso.com/ab*` nicht zulässig.</span><span class="sxs-lookup"><span data-stu-id="f4e33-220">For example, `contoso.com/*` is allowed; `contoso.com*` or `contoso.com/ab*` are not allowed.</span></span>

  - <span data-ttu-id="f4e33-221">Alle untergeordneten Pfade sind nicht durch einen richtigen Platzhalter impliziert.</span><span class="sxs-lookup"><span data-stu-id="f4e33-221">All subpaths are not implied by a right wildcard.</span></span>

    <span data-ttu-id="f4e33-222">Enthält beispielsweise `contoso.com/*` nicht `contoso.com/a` .</span><span class="sxs-lookup"><span data-stu-id="f4e33-222">For example, `contoso.com/*` does not include `contoso.com/a`.</span></span>

  - <span data-ttu-id="f4e33-223">`*.com*`ist ungültig (keine auflösbare Domäne, und der Rechte Platzhalter folgt keinem Schrägstrich).</span><span class="sxs-lookup"><span data-stu-id="f4e33-223">`*.com*` is invalid (not a resolvable domain and the right wildcard does not follow a forward slash).</span></span>

  - <span data-ttu-id="f4e33-224">Platzhalter sind in IP-Adressen nicht zulässig.</span><span class="sxs-lookup"><span data-stu-id="f4e33-224">Wildcards are not allowed in IP addresses.</span></span>

- <span data-ttu-id="f4e33-225">Das Tildezeichen (~) steht in den folgenden Szenarien zur Verfügung:</span><span class="sxs-lookup"><span data-stu-id="f4e33-225">The tilde (~) character is available in the following scenarios:</span></span>

  - <span data-ttu-id="f4e33-226">Eine linke Tilde impliziert eine Domäne und alle Unterdomänen.</span><span class="sxs-lookup"><span data-stu-id="f4e33-226">A left tilde implies a domain and all subdomains.</span></span>

    <span data-ttu-id="f4e33-227">Beispielsweise `~contoso.com` enthält `contoso.com` und `*.contoso.com` .</span><span class="sxs-lookup"><span data-stu-id="f4e33-227">For example `~contoso.com` includes `contoso.com` and `*.contoso.com`.</span></span>

- <span data-ttu-id="f4e33-228">URL-Einträge, die Protokolle enthalten (beispielsweise,, `http://` `https://` oder `ftp://` ) schlagen fehl, da URL-Einträge auf alle Protokolle angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="f4e33-228">URL entries that contain protocols (for example, `http://`, `https://`, or `ftp://`) will fail, because URL entries apply to all protocols.</span></span>

- <span data-ttu-id="f4e33-229">Ein Benutzername oder ein Kennwort werden nicht unterstützt oder erforderlich.</span><span class="sxs-lookup"><span data-stu-id="f4e33-229">A username or password aren't supported or required.</span></span>

- <span data-ttu-id="f4e33-230">Anführungszeichen (' oder ') sind ungültige Zeichen.</span><span class="sxs-lookup"><span data-stu-id="f4e33-230">Quotes (' or ") are invalid characters.</span></span>

- <span data-ttu-id="f4e33-231">Eine URL sollte nach Möglichkeit alle Umleitungen enthalten.</span><span class="sxs-lookup"><span data-stu-id="f4e33-231">A URL should include all redirects where possible.</span></span>

### <a name="url-entry-scenarios"></a><span data-ttu-id="f4e33-232">URL-Eintrags Szenarien</span><span class="sxs-lookup"><span data-stu-id="f4e33-232">URL entry scenarios</span></span>

<span data-ttu-id="f4e33-233">In den folgenden Abschnitten werden gültige URL-Einträge und ihre Ergebnisse beschrieben.</span><span class="sxs-lookup"><span data-stu-id="f4e33-233">Valid URL entries and their results are described in the following sections.</span></span>

#### <a name="scenario-no-wildcards"></a><span data-ttu-id="f4e33-234">Szenario: keine Platzhalter</span><span class="sxs-lookup"><span data-stu-id="f4e33-234">Scenario: No wildcards</span></span>

<span data-ttu-id="f4e33-235">**Eintrag**:`contoso.com`</span><span class="sxs-lookup"><span data-stu-id="f4e33-235">**Entry**: `contoso.com`</span></span>

- <span data-ttu-id="f4e33-236">**Übereinstimmung zulassen**: contoso.com</span><span class="sxs-lookup"><span data-stu-id="f4e33-236">**Allow match**: contoso.com</span></span>

- <span data-ttu-id="f4e33-237">**Zulassen nicht abgeglichen**:</span><span class="sxs-lookup"><span data-stu-id="f4e33-237">**Allow not matched**:</span></span>

  - <span data-ttu-id="f4e33-238">abc-contoso.com</span><span class="sxs-lookup"><span data-stu-id="f4e33-238">abc-contoso.com</span></span>
  - <span data-ttu-id="f4e33-239">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="f4e33-239">contoso.com/a</span></span>
  - <span data-ttu-id="f4e33-240">payroll.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f4e33-240">payroll.contoso.com</span></span>
  - <span data-ttu-id="f4e33-241">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="f4e33-241">test.com/contoso.com</span></span>
  - <span data-ttu-id="f4e33-242">test.com/q=contoso.com</span><span class="sxs-lookup"><span data-stu-id="f4e33-242">test.com/q=contoso.com</span></span>
  - <span data-ttu-id="f4e33-243">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f4e33-243">www.contoso.com</span></span>
  - <span data-ttu-id="f4e33-244">www. contoso. com/q = a@contoso. com</span><span class="sxs-lookup"><span data-stu-id="f4e33-244">www.contoso.com/q=a@contoso.com</span></span>
  
- <span data-ttu-id="f4e33-245">**Block Übereinstimmung**:</span><span class="sxs-lookup"><span data-stu-id="f4e33-245">**Block match**:</span></span>

  - <span data-ttu-id="f4e33-246">contoso.com</span><span class="sxs-lookup"><span data-stu-id="f4e33-246">contoso.com</span></span>
  - <span data-ttu-id="f4e33-247">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="f4e33-247">contoso.com/a</span></span>
  - <span data-ttu-id="f4e33-248">payroll.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f4e33-248">payroll.contoso.com</span></span>
  - <span data-ttu-id="f4e33-249">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="f4e33-249">test.com/contoso.com</span></span>
  - <span data-ttu-id="f4e33-250">test.com/q=contoso.com</span><span class="sxs-lookup"><span data-stu-id="f4e33-250">test.com/q=contoso.com</span></span>
  - <span data-ttu-id="f4e33-251">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f4e33-251">www.contoso.com</span></span>
  - <span data-ttu-id="f4e33-252">www. contoso. com/q = a@contoso. com</span><span class="sxs-lookup"><span data-stu-id="f4e33-252">www.contoso.com/q=a@contoso.com</span></span>

- <span data-ttu-id="f4e33-253">**Block nicht abgeglichen**: ABC-contoso.com</span><span class="sxs-lookup"><span data-stu-id="f4e33-253">**Block not matched**: abc-contoso.com</span></span>

#### <a name="scenario-left-wildcard-subdomain"></a><span data-ttu-id="f4e33-254">Szenario: Linker Platzhalter (Unterdomäne)</span><span class="sxs-lookup"><span data-stu-id="f4e33-254">Scenario: Left wildcard (subdomain)</span></span>

<span data-ttu-id="f4e33-255">**Eintrag**:`*.contoso.com`</span><span class="sxs-lookup"><span data-stu-id="f4e33-255">**Entry**: `*.contoso.com`</span></span>

- <span data-ttu-id="f4e33-256">Übereinstimmung und **Block Übereinstimmung** **zulassen** :</span><span class="sxs-lookup"><span data-stu-id="f4e33-256">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="f4e33-257">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f4e33-257">www.contoso.com</span></span>
  - <span data-ttu-id="f4e33-258">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f4e33-258">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="f4e33-259">**Zulassen nicht abgeglichen** und **Block nicht abgeglichen**:</span><span class="sxs-lookup"><span data-stu-id="f4e33-259">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="f4e33-260">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="f4e33-260">123contoso.com</span></span>
  - <span data-ttu-id="f4e33-261">contoso.com</span><span class="sxs-lookup"><span data-stu-id="f4e33-261">contoso.com</span></span>
  - <span data-ttu-id="f4e33-262">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="f4e33-262">test.com/contoso.com</span></span>
  - <span data-ttu-id="f4e33-263">www.contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="f4e33-263">www.contoso.com/abc</span></span>
  
#### <a name="scenario-right-wildcard-at-top-of-path"></a><span data-ttu-id="f4e33-264">Szenario: rechter Platzhalter oben im Pfad</span><span class="sxs-lookup"><span data-stu-id="f4e33-264">Scenario: Right wildcard at top of path</span></span>

<span data-ttu-id="f4e33-265">**Eintrag**:`contoso.com/a/*`</span><span class="sxs-lookup"><span data-stu-id="f4e33-265">**Entry**: `contoso.com/a/*`</span></span>

- <span data-ttu-id="f4e33-266">Übereinstimmung und **Block Übereinstimmung** **zulassen** :</span><span class="sxs-lookup"><span data-stu-id="f4e33-266">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="f4e33-267">contoso.com/a/b</span><span class="sxs-lookup"><span data-stu-id="f4e33-267">contoso.com/a/b</span></span>
  - <span data-ttu-id="f4e33-268">contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="f4e33-268">contoso.com/a/b/c</span></span>
  - <span data-ttu-id="f4e33-269">contoso. com/a/? q = Joe@t. com</span><span class="sxs-lookup"><span data-stu-id="f4e33-269">contoso.com/a/?q=joe@t.com</span></span>

- <span data-ttu-id="f4e33-270">**Zulassen nicht abgeglichen** und **Block nicht abgeglichen**:</span><span class="sxs-lookup"><span data-stu-id="f4e33-270">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="f4e33-271">contoso.com</span><span class="sxs-lookup"><span data-stu-id="f4e33-271">contoso.com</span></span>
  - <span data-ttu-id="f4e33-272">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="f4e33-272">contoso.com/a</span></span>
  - <span data-ttu-id="f4e33-273">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f4e33-273">www.contoso.com</span></span>
  - <span data-ttu-id="f4e33-274">www. contoso. com/q = a@contoso. com</span><span class="sxs-lookup"><span data-stu-id="f4e33-274">www.contoso.com/q=a@contoso.com</span></span>
  
#### <a name="scenario-left-tilde"></a><span data-ttu-id="f4e33-275">Szenario: linke Tilde</span><span class="sxs-lookup"><span data-stu-id="f4e33-275">Scenario: Left tilde</span></span>

<span data-ttu-id="f4e33-276">**Eintrag**:`~contoso.com`</span><span class="sxs-lookup"><span data-stu-id="f4e33-276">**Entry**: `~contoso.com`</span></span>

- <span data-ttu-id="f4e33-277">Übereinstimmung und **Block Übereinstimmung** **zulassen** :</span><span class="sxs-lookup"><span data-stu-id="f4e33-277">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="f4e33-278">contoso.com</span><span class="sxs-lookup"><span data-stu-id="f4e33-278">contoso.com</span></span>
  - <span data-ttu-id="f4e33-279">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f4e33-279">www.contoso.com</span></span>
  - <span data-ttu-id="f4e33-280">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f4e33-280">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="f4e33-281">**Zulassen nicht abgeglichen** und **Block nicht abgeglichen**:</span><span class="sxs-lookup"><span data-stu-id="f4e33-281">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="f4e33-282">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="f4e33-282">123contoso.com</span></span>
  - <span data-ttu-id="f4e33-283">contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="f4e33-283">contoso.com/abc</span></span>
  - <span data-ttu-id="f4e33-284">www.contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="f4e33-284">www.contoso.com/abc</span></span>

#### <a name="scenario-right-wildcard-suffix"></a><span data-ttu-id="f4e33-285">Szenario: Rechtes Platzhalter Suffix</span><span class="sxs-lookup"><span data-stu-id="f4e33-285">Scenario: Right wildcard suffix</span></span>

<span data-ttu-id="f4e33-286">**Eintrag**:`contoso.com/*`</span><span class="sxs-lookup"><span data-stu-id="f4e33-286">**Entry**: `contoso.com/*`</span></span>

- <span data-ttu-id="f4e33-287">Übereinstimmung und **Block Übereinstimmung** **zulassen** :</span><span class="sxs-lookup"><span data-stu-id="f4e33-287">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="f4e33-288">contoso. com/? q = whatever@fabrikam. com</span><span class="sxs-lookup"><span data-stu-id="f4e33-288">contoso.com/?q=whatever@fabrikam.com</span></span>
  - <span data-ttu-id="f4e33-289">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="f4e33-289">contoso.com/a</span></span>
  - <span data-ttu-id="f4e33-290">contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="f4e33-290">contoso.com/a/b/c</span></span>
  - <span data-ttu-id="f4e33-291">contoso.com/ab</span><span class="sxs-lookup"><span data-stu-id="f4e33-291">contoso.com/ab</span></span>
  - <span data-ttu-id="f4e33-292">contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="f4e33-292">contoso.com/b</span></span>
  - <span data-ttu-id="f4e33-293">contoso.com/b/a/c</span><span class="sxs-lookup"><span data-stu-id="f4e33-293">contoso.com/b/a/c</span></span>
  - <span data-ttu-id="f4e33-294">contoso.com/ba</span><span class="sxs-lookup"><span data-stu-id="f4e33-294">contoso.com/ba</span></span>

- <span data-ttu-id="f4e33-295">**Allow NOT MATCHED** and **Block NOT MATCHED**: contoso.com</span><span class="sxs-lookup"><span data-stu-id="f4e33-295">**Allow not matched** and **Block not matched**: contoso.com</span></span>

#### <a name="scenario-left-wildcard-subdomain-and-right-wildcard-suffix"></a><span data-ttu-id="f4e33-296">Szenario: linke Platzhalter-Unterdomäne und Rechte Platzhalter Suffix</span><span class="sxs-lookup"><span data-stu-id="f4e33-296">Scenario: Left wildcard subdomain and right wildcard suffix</span></span>

<span data-ttu-id="f4e33-297">**Eintrag**:`*.contoso.com/*`</span><span class="sxs-lookup"><span data-stu-id="f4e33-297">**Entry**: `*.contoso.com/*`</span></span>

- <span data-ttu-id="f4e33-298">Übereinstimmung und **Block Übereinstimmung** **zulassen** :</span><span class="sxs-lookup"><span data-stu-id="f4e33-298">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="f4e33-299">abc.contoso.com/ab</span><span class="sxs-lookup"><span data-stu-id="f4e33-299">abc.contoso.com/ab</span></span>
  - <span data-ttu-id="f4e33-300">abc.xyz.contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="f4e33-300">abc.xyz.contoso.com/a/b/c</span></span>
  - <span data-ttu-id="f4e33-301">www.contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="f4e33-301">www.contoso.com/a</span></span>
  - <span data-ttu-id="f4e33-302">www.contoso.com/b/a/c</span><span class="sxs-lookup"><span data-stu-id="f4e33-302">www.contoso.com/b/a/c</span></span>
  - <span data-ttu-id="f4e33-303">xyz.contoso.com/ba</span><span class="sxs-lookup"><span data-stu-id="f4e33-303">xyz.contoso.com/ba</span></span>

- <span data-ttu-id="f4e33-304">**Allow NOT MATCHED** and **Block NOT MATCHED**: contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="f4e33-304">**Allow not matched** and **Block not matched**: contoso.com/b</span></span>

#### <a name="scenario-left-and-right-tilde"></a><span data-ttu-id="f4e33-305">Szenario: linke und Rechte Tilde</span><span class="sxs-lookup"><span data-stu-id="f4e33-305">Scenario: Left and right tilde</span></span>

<span data-ttu-id="f4e33-306">**Eintrag**:`~contoso.com~`</span><span class="sxs-lookup"><span data-stu-id="f4e33-306">**Entry**: `~contoso.com~`</span></span>

- <span data-ttu-id="f4e33-307">Übereinstimmung und **Block Übereinstimmung** **zulassen** :</span><span class="sxs-lookup"><span data-stu-id="f4e33-307">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="f4e33-308">contoso.com</span><span class="sxs-lookup"><span data-stu-id="f4e33-308">contoso.com</span></span>
  - <span data-ttu-id="f4e33-309">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="f4e33-309">contoso.com/a</span></span>
  - <span data-ttu-id="f4e33-310">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f4e33-310">www.contoso.com</span></span>
  - <span data-ttu-id="f4e33-311">www.contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="f4e33-311">www.contoso.com/b</span></span>
  - <span data-ttu-id="f4e33-312">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f4e33-312">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="f4e33-313">**Zulassen nicht abgeglichen** und **Block nicht abgeglichen**:</span><span class="sxs-lookup"><span data-stu-id="f4e33-313">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="f4e33-314">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="f4e33-314">123contoso.com</span></span>
  - <span data-ttu-id="f4e33-315">contoso.org</span><span class="sxs-lookup"><span data-stu-id="f4e33-315">contoso.org</span></span>

#### <a name="scenario-ip-address"></a><span data-ttu-id="f4e33-316">Szenario: IP-Adresse</span><span class="sxs-lookup"><span data-stu-id="f4e33-316">Scenario: IP address</span></span>

<span data-ttu-id="f4e33-317">**Eintrag**:`1.2.3.4`</span><span class="sxs-lookup"><span data-stu-id="f4e33-317">**Entry**: `1.2.3.4`</span></span>

- <span data-ttu-id="f4e33-318">Übereinstimmung **zulassen** und **Block Übereinstimmung**: 1.2.3.4</span><span class="sxs-lookup"><span data-stu-id="f4e33-318">**Allow match** and **Block match**: 1.2.3.4</span></span>

- <span data-ttu-id="f4e33-319">**Zulassen nicht abgeglichen** und **Block nicht abgeglichen**:</span><span class="sxs-lookup"><span data-stu-id="f4e33-319">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="f4e33-320">1.2.3.4/a</span><span class="sxs-lookup"><span data-stu-id="f4e33-320">1.2.3.4/a</span></span>
  - <span data-ttu-id="f4e33-321">11.2.3.4/a</span><span class="sxs-lookup"><span data-stu-id="f4e33-321">11.2.3.4/a</span></span>

#### <a name="ip-address-with-right-wildcard"></a><span data-ttu-id="f4e33-322">IP-Adresse mit dem richtigen Platzhalter</span><span class="sxs-lookup"><span data-stu-id="f4e33-322">IP address with right wildcard</span></span>

<span data-ttu-id="f4e33-323">**Eintrag**:`1.2.3.4/*`</span><span class="sxs-lookup"><span data-stu-id="f4e33-323">**Entry**: `1.2.3.4/*`</span></span>

- <span data-ttu-id="f4e33-324">Übereinstimmung und **Block Übereinstimmung** **zulassen** :</span><span class="sxs-lookup"><span data-stu-id="f4e33-324">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="f4e33-325">1.2.3.4/b</span><span class="sxs-lookup"><span data-stu-id="f4e33-325">1.2.3.4/b</span></span>
  - <span data-ttu-id="f4e33-326">1.2.3.4/baaaa</span><span class="sxs-lookup"><span data-stu-id="f4e33-326">1.2.3.4/baaaa</span></span>

### <a name="examples-of-invalid-entries"></a><span data-ttu-id="f4e33-327">Beispiele für ungültige Einträge</span><span class="sxs-lookup"><span data-stu-id="f4e33-327">Examples of invalid entries</span></span>

<span data-ttu-id="f4e33-328">Die folgenden Einträge sind ungültig:</span><span class="sxs-lookup"><span data-stu-id="f4e33-328">The following entries are invalid:</span></span>

- <span data-ttu-id="f4e33-329">**Fehlende oder ungültige Domänenwerte**:</span><span class="sxs-lookup"><span data-stu-id="f4e33-329">**Missing or invalid domain values**:</span></span>

  - <span data-ttu-id="f4e33-330">contoso</span><span class="sxs-lookup"><span data-stu-id="f4e33-330">contoso</span></span>
  - <span data-ttu-id="f4e33-331">\*contoso.\*</span><span class="sxs-lookup"><span data-stu-id="f4e33-331">\*.contoso.\*</span></span>
  - <span data-ttu-id="f4e33-332">\*. com</span><span class="sxs-lookup"><span data-stu-id="f4e33-332">\*.com</span></span>
  - <span data-ttu-id="f4e33-333">\*.PDF</span><span class="sxs-lookup"><span data-stu-id="f4e33-333">\*.pdf</span></span>

- <span data-ttu-id="f4e33-334">**Platzhalter für Text oder ohne Leerzeichen**:</span><span class="sxs-lookup"><span data-stu-id="f4e33-334">**Wildcard on text or without spacing characters**:</span></span>

  - <span data-ttu-id="f4e33-335">\*contoso.com</span><span class="sxs-lookup"><span data-stu-id="f4e33-335">\*contoso.com</span></span>
  - <span data-ttu-id="f4e33-336">contoso.com\*</span><span class="sxs-lookup"><span data-stu-id="f4e33-336">contoso.com\*</span></span>
  - <span data-ttu-id="f4e33-337">\*1.2.3.4</span><span class="sxs-lookup"><span data-stu-id="f4e33-337">\*1.2.3.4</span></span>
  - <span data-ttu-id="f4e33-338">1.2.3.4\*</span><span class="sxs-lookup"><span data-stu-id="f4e33-338">1.2.3.4\*</span></span>
  - <span data-ttu-id="f4e33-339">contoso.com/a\*</span><span class="sxs-lookup"><span data-stu-id="f4e33-339">contoso.com/a\*</span></span>
  - <span data-ttu-id="f4e33-340">contoso.com/ab\*</span><span class="sxs-lookup"><span data-stu-id="f4e33-340">contoso.com/ab\*</span></span>

- <span data-ttu-id="f4e33-341">**IP-Adressen mit Ports**:</span><span class="sxs-lookup"><span data-stu-id="f4e33-341">**IP addresses with ports**:</span></span>

  - <span data-ttu-id="f4e33-342">contoso.com:443</span><span class="sxs-lookup"><span data-stu-id="f4e33-342">contoso.com:443</span></span>
  - <span data-ttu-id="f4e33-343">abc.contoso.com:25</span><span class="sxs-lookup"><span data-stu-id="f4e33-343">abc.contoso.com:25</span></span>

- <span data-ttu-id="f4e33-344">**Nicht beschreibende Platzhalter**:</span><span class="sxs-lookup"><span data-stu-id="f4e33-344">**Non-descriptive wildcards**:</span></span>

  - \*
  - <span data-ttu-id="f4e33-345">\*.\*</span><span class="sxs-lookup"><span data-stu-id="f4e33-345">\*.\*</span></span>

- <span data-ttu-id="f4e33-346">**Mittlere Platzhalter**:</span><span class="sxs-lookup"><span data-stu-id="f4e33-346">**Middle wildcards**:</span></span>

  - <span data-ttu-id="f4e33-347">Conto \* so.com</span><span class="sxs-lookup"><span data-stu-id="f4e33-347">conto\*so.com</span></span>
  - <span data-ttu-id="f4e33-348">Conto ~ so. com</span><span class="sxs-lookup"><span data-stu-id="f4e33-348">conto~so.com</span></span>

- <span data-ttu-id="f4e33-349">**Doppelte Platzhalter**</span><span class="sxs-lookup"><span data-stu-id="f4e33-349">**Double wildcards**</span></span>

  - <span data-ttu-id="f4e33-350">contoso.com/\*\*</span><span class="sxs-lookup"><span data-stu-id="f4e33-350">contoso.com/\*\*</span></span>
  - <span data-ttu-id="f4e33-351">contoso.com/\*/\*</span><span class="sxs-lookup"><span data-stu-id="f4e33-351">contoso.com/\*/\*</span></span>
