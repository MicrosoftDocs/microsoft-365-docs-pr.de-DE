---
title: Verwalten Ihrer zulässigen und blockierten URLs in der Liste "Mandanten zulassen/blockieren"
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: Administratoren können erfahren, wie Sie URL-Einträge in der Liste Mandanten-Allow/Block im Security & Compliance Center konfigurieren.
ms.openlocfilehash: 0fdfa23ba22b240032e7a6888948de180aa0f6ae
ms.sourcegitcommit: ee39faf3507d0edc9497117b3b2854955c959c6c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "49614964"
---
# <a name="manage-urls-in-the-tenant-allowblock-list"></a><span data-ttu-id="ea6c7-103">Verwalten von URLs in der Zulassungs-/Sperrliste des Mandanten</span><span class="sxs-lookup"><span data-stu-id="ea6c7-103">Manage URLs in the Tenant Allow/Block List</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


> [!NOTE]
> <span data-ttu-id="ea6c7-104">Die in diesem Thema beschriebenen Funktionen befinden sich in der Vorschau, können sich ändern und sind nicht in allen Organisationen verfügbar.</span><span class="sxs-lookup"><span data-stu-id="ea6c7-104">The features described in this topic are in Preview, are subject to change, and are not available in all organizations.</span></span>

<span data-ttu-id="ea6c7-105">In Microsoft 365-Organisationen mit Postfächern in Exchange Online-oder eigenständigen Exchange Online Schutzorganisationen (EoP) ohne Exchange Online Postfächer können Sie mit dem EoP-Filter Urteil nicht einverstanden sein.</span><span class="sxs-lookup"><span data-stu-id="ea6c7-105">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, you might disagree with the EOP filtering verdict.</span></span> <span data-ttu-id="ea6c7-106">Beispielsweise kann eine gute Nachricht als "schlecht" markiert werden (ein falsch positives Ergebnis), oder es ist möglicherweise eine ungültige Meldung zulässig (ein falsches negativ).</span><span class="sxs-lookup"><span data-stu-id="ea6c7-106">For example, a good message might be marked as bad (a false positive), or a bad message might be allowed through (a false negative).</span></span>

<span data-ttu-id="ea6c7-107">In der Liste Mandanten-Allow/Block im Security & Compliance Center haben Sie die Möglichkeit, die Microsoft 365-Filter Urteile manuell außer Kraft zu setzen.</span><span class="sxs-lookup"><span data-stu-id="ea6c7-107">The Tenant Allow/Block List in the Security & Compliance Center gives you a way to manually override the Microsoft 365 filtering verdicts.</span></span> <span data-ttu-id="ea6c7-108">Die Mandanten-Zulassungs-und Sperrliste wird während des e-Mail-Flusses und zum Zeitpunkt der Benutzerklicks verwendet.</span><span class="sxs-lookup"><span data-stu-id="ea6c7-108">The Tenant Allow/Block List is used during mail flow and at the time of user clicks.</span></span> <span data-ttu-id="ea6c7-109">In der Liste Mandanten-Allow/Block können Sie URLs angeben, die zugelassen oder blockiert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="ea6c7-109">You can specify URLs to allow or block in the Tenant Allow/Block List.</span></span>

<span data-ttu-id="ea6c7-110">In diesem Thema wird beschrieben, wie Sie Einträge in der Liste "Allow/Block" des Mandanten im Security & Compliance Center oder in PowerShell (Exchange Online PowerShell für Microsoft 365-Organisationen mit Postfächern in Exchange Online; eigenständige EoP PowerShell für Organisationen ohne Exchange Online Postfächer) konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="ea6c7-110">This topic describes how to configure entries in the Tenant Allow/Block List in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="ea6c7-111">Was sollten Sie wissen, bevor Sie beginnen?</span><span class="sxs-lookup"><span data-stu-id="ea6c7-111">What do you need to know before you begin?</span></span>

- <span data-ttu-id="ea6c7-112">Sie öffnen das Security & Compliance Center unter <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="ea6c7-112">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="ea6c7-113">Wenn Sie direkt zur Seite **Mandanten-Zulassungs-und Sperrliste** wechseln möchten, verwenden Sie <https://protection.office.com/tenantAllowBlockList> .</span><span class="sxs-lookup"><span data-stu-id="ea6c7-113">To go directly to the **Tenant Allow/Block List** page, use <https://protection.office.com/tenantAllowBlockList>.</span></span>

- <span data-ttu-id="ea6c7-114">Die verfügbaren URL-Werte werden in der [URL-Syntax für den Abschnitt Mandanten-Zulassungs-und Sperrliste](#url-syntax-for-the-tenant-allowblock-list) weiter unten in diesem Thema beschrieben.</span><span class="sxs-lookup"><span data-stu-id="ea6c7-114">The available URL values are described in the [URL syntax for the Tenant Allow/Block List](#url-syntax-for-the-tenant-allowblock-list) section later in this topic.</span></span>

- <span data-ttu-id="ea6c7-115">Die Liste Mandanten Allow/Block erlaubt maximal 500 Einträge für URLs.</span><span class="sxs-lookup"><span data-stu-id="ea6c7-115">The Tenant Allow/Block List allows a maximum of 500 entries for URLs.</span></span>

- <span data-ttu-id="ea6c7-116">Ein Eintrag sollte innerhalb von 15 Minuten aktiv sein.</span><span class="sxs-lookup"><span data-stu-id="ea6c7-116">An entry should be active within 15 minutes.</span></span>

- <span data-ttu-id="ea6c7-117">Block Einträge haben Vorrang vor Zulassungs Einträgen.</span><span class="sxs-lookup"><span data-stu-id="ea6c7-117">Block entries take precedence over allow entries.</span></span>

- <span data-ttu-id="ea6c7-118">Standardmäßig laufen Einträge in der Liste Mandanten-Allow/Block nach 30 Tagen ab.</span><span class="sxs-lookup"><span data-stu-id="ea6c7-118">By default, entries in the Tenant Allow/Block List will expire after 30 days.</span></span> <span data-ttu-id="ea6c7-119">Sie können ein Datum angeben oder festlegen, dass es nie abläuft.</span><span class="sxs-lookup"><span data-stu-id="ea6c7-119">You can specify a date or set them to never expire.</span></span>

- <span data-ttu-id="ea6c7-120">Wie Sie eine Verbindung mit Exchange Online PowerShell herstellen, finden Sie unter [Herstellen einer Verbindung mit Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="ea6c7-120">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="ea6c7-121">Informationen zum Herstellen einer Verbindung mit dem eigenständigen Exchange Online Protection PowerShell finden Sie unter [Verbinden mit PowerShell in Exchange Online Protection](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="ea6c7-121">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="ea6c7-122">Bevor Sie die Verfahren in diesem Artikel ausführen können, müssen Ihnen im Security & Compliance Center Berechtigungen zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="ea6c7-122">You need to be assigned permissions in the Security & Compliance Center before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="ea6c7-123">Sie müssen Mitglied der Rollengruppen " **Organisationsverwaltung** " oder " **Sicherheits Administrator** " sein, um Werte aus der Liste "Allow/Block" für Mandanten hinzuzufügen und daraus zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="ea6c7-123">To add and remove values from the Tenant Allow/Block List, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="ea6c7-124">Für den schreibgeschützten Zugriff auf die Liste der Mandanten zulassen/blockieren müssen Sie ein Mitglied der Rollengruppen " **globaler Leser** " oder " **Sicherheits Leser** " sein.</span><span class="sxs-lookup"><span data-stu-id="ea6c7-124">For read-only access to the Tenant Allow/Block List, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="ea6c7-125">Weitere Informationen finden Sie unter [Berechtigungen im Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="ea6c7-125">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

  <span data-ttu-id="ea6c7-126">**Hinweise**:</span><span class="sxs-lookup"><span data-stu-id="ea6c7-126">**Notes**:</span></span>

  - <span data-ttu-id="ea6c7-127">Durch das Hinzufügen von Benutzern zur entsprechenden Azure Active Directory-Rolle im Microsoft 365 Admin Center erhalten Benutzer die erforderlichen Berechtigungen im Security & Compliance Center _und_ Berechtigungen für andere Features in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="ea6c7-127">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Security & Compliance Center _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="ea6c7-128">Weitere Informationen finden Sie unter [Informationen zu Administratorrollen](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).</span><span class="sxs-lookup"><span data-stu-id="ea6c7-128">For more information, see [About admin roles](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).</span></span>
  - <span data-ttu-id="ea6c7-129">Die Rollengruppe **Organisationsverwaltung mit Leserechten** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) ermöglicht auch einen schreibgeschützten Zugriff auf das Feature.</span><span class="sxs-lookup"><span data-stu-id="ea6c7-129">The **View-Only Organization Management** role group in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

## <a name="use-the-security--compliance-center-to-create-url-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="ea6c7-130">Verwenden Sie das Security & Compliance Center, um URL-Einträge in der Liste Mandanten-Allow/Block zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="ea6c7-130">Use the Security & Compliance Center to create URL entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="ea6c7-131">Ausführliche Informationen zur Syntax für URL-Einträge finden Sie weiter unten in diesem Thema in der [URL-Syntax für den Abschnitt Allow/Block List für Mandanten](#url-syntax-for-the-tenant-allowblock-list) .</span><span class="sxs-lookup"><span data-stu-id="ea6c7-131">For details about the syntax for URL entries, see the [URL syntax for the Tenant Allow/Block List](#url-syntax-for-the-tenant-allowblock-list) section later in this topic.</span></span>

1. <span data-ttu-id="ea6c7-132">Wechseln Sie im Security & Compliance Center zu **Bedrohungs Verwaltungs** \> **Richtlinie** \> **Mandanten-Zulassungs-/Sperrlisten**.</span><span class="sxs-lookup"><span data-stu-id="ea6c7-132">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="ea6c7-133">Überprüfen Sie auf der Seite **Mandantenliste zulassen/blockieren** , dass die Registerkarte **URLs** ausgewählt ist, und klicken Sie dann auf **Hinzufügen** .</span><span class="sxs-lookup"><span data-stu-id="ea6c7-133">On the **Tenant Allow/Block List** page, verify that the **URLs** tab is selected, and then click **Add**</span></span>

3. <span data-ttu-id="ea6c7-134">Konfigurieren Sie im Flyout **neue URLs hinzufügen** , das angezeigt wird, die folgenden Einstellungen:</span><span class="sxs-lookup"><span data-stu-id="ea6c7-134">In the **Add new URLs** flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="ea6c7-135">**URLs mit Platzhaltern hinzufügen**: Geben Sie eine URL pro Reihe bis maximal 20 ein.</span><span class="sxs-lookup"><span data-stu-id="ea6c7-135">**Add URLs with wildcards**: Enter one URL per line, up to a maximum of 20.</span></span>

   - <span data-ttu-id="ea6c7-136">**Block/Allow**: Wählen Sie aus, ob die angegebenen URLs **zugelassen** oder **blockiert** werden sollen.</span><span class="sxs-lookup"><span data-stu-id="ea6c7-136">**Block/Allow**: Select whether you want to **Allow** or **Block** the specified URLs.</span></span>

   - <span data-ttu-id="ea6c7-137">**Nie ablaufen**: führen Sie einen der folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="ea6c7-137">**Never expire**: Do one of the following steps:</span></span>

     - <span data-ttu-id="ea6c7-138">Stellen Sie sicher, dass die Einstellung deaktiviert ist (deaktivieren ![ ](../../media/scc-toggle-off.png) ), und verwenden Sie das Feld **expires on** , um das Ablaufdatum für die Einträge anzugeben.</span><span class="sxs-lookup"><span data-stu-id="ea6c7-138">Verify the setting is turned off (![Toggle off](../../media/scc-toggle-off.png)) and use the **Expires on** box to specify the expiration date for the entries.</span></span>

     <span data-ttu-id="ea6c7-139">oder</span><span class="sxs-lookup"><span data-stu-id="ea6c7-139">or</span></span>

     - <span data-ttu-id="ea6c7-140">Bewegen Sie die Umschaltfläche nach rechts, um die Einträge so zu konfigurieren, dass Sie nie ablaufen:</span><span class="sxs-lookup"><span data-stu-id="ea6c7-140">Move the toggle to the right to configure the entries to never expire:</span></span> ![Umschaltfläche ein](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png)<span data-ttu-id="ea6c7-142">.</span><span class="sxs-lookup"><span data-stu-id="ea6c7-142">.</span></span>

   - <span data-ttu-id="ea6c7-143">**Optional Hinweis**: Geben Sie einen beschreibenden Text für die Einträge ein.</span><span class="sxs-lookup"><span data-stu-id="ea6c7-143">**Optional note**: Enter descriptive text for the entries.</span></span>

4. <span data-ttu-id="ea6c7-144">Wenn Sie fertig sind, klicken Sie auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="ea6c7-144">When you're finished, click **Add**.</span></span>

## <a name="use-the-security--compliance-center-to-view-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="ea6c7-145">Verwenden Sie das Security & Compliance Center, um Einträge in der Liste Mandanten-Allow/Block anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="ea6c7-145">Use the Security & Compliance Center to view entries in the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="ea6c7-146">Wechseln Sie im Security & Compliance Center zu **Bedrohungs Verwaltungs** \> **Richtlinie** \> **Mandanten-Zulassungs-/Sperrlisten**.</span><span class="sxs-lookup"><span data-stu-id="ea6c7-146">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="ea6c7-147">Wählen Sie die Registerkarte **URLs** aus.</span><span class="sxs-lookup"><span data-stu-id="ea6c7-147">Select the **URLs** tab.</span></span>

<span data-ttu-id="ea6c7-148">Klicken Sie auf die folgenden Spaltenüberschriften, um Sie in aufsteigender oder absteigender Reihenfolge zu sortieren:</span><span class="sxs-lookup"><span data-stu-id="ea6c7-148">Click on the following column headings to sort in ascending or descending order:</span></span>

- <span data-ttu-id="ea6c7-149">**Wert**</span><span class="sxs-lookup"><span data-stu-id="ea6c7-149">**Value**</span></span>
- <span data-ttu-id="ea6c7-150">**Aktion**: **blockieren** oder **zulassen**.</span><span class="sxs-lookup"><span data-stu-id="ea6c7-150">**Action**: **Block** or **Allow**.</span></span>
- <span data-ttu-id="ea6c7-151">**Datum der letzten Aktualisierung**</span><span class="sxs-lookup"><span data-stu-id="ea6c7-151">**Last updated date**</span></span>
- <span data-ttu-id="ea6c7-152">**Ablaufdatum**</span><span class="sxs-lookup"><span data-stu-id="ea6c7-152">**Expiration date**</span></span>
- <span data-ttu-id="ea6c7-153">**Hinweis**</span><span class="sxs-lookup"><span data-stu-id="ea6c7-153">**Note**</span></span>

<span data-ttu-id="ea6c7-154">Klicken Sie auf **Gruppieren** , um die Einträge nach **Aktion** (**blockieren** oder **zulassen**) oder **ohne** zu gruppieren.</span><span class="sxs-lookup"><span data-stu-id="ea6c7-154">Click **Group** to group the entries by **Action** (**Block** or **Allow**) or **None**.</span></span>

<span data-ttu-id="ea6c7-155">Klicken Sie auf **Suchen**, geben Sie einen Wert ganz oder teilweise ein, und drücken Sie dann die EINGABETASTE, um einen bestimmten Wert zu suchen.</span><span class="sxs-lookup"><span data-stu-id="ea6c7-155">Click **Search**, enter all or part of a value, and then press ENTER to find a specific value.</span></span> <span data-ttu-id="ea6c7-156">Wenn Sie fertig sind, klicken Sie auf **Such** ![ Symbol Löschen ](../../media/b6512677-5e7b-42b0-a8a3-3be1d7fa23ee.gif) .</span><span class="sxs-lookup"><span data-stu-id="ea6c7-156">When you're finished, click **Clear search** ![Clear search icon](../../media/b6512677-5e7b-42b0-a8a3-3be1d7fa23ee.gif).</span></span>

<span data-ttu-id="ea6c7-157">Klicken Sie auf **Filter**.</span><span class="sxs-lookup"><span data-stu-id="ea6c7-157">Click **Filter**.</span></span> <span data-ttu-id="ea6c7-158">Konfigurieren Sie im angezeigten **Filter** Flyout die folgenden Einstellungen:</span><span class="sxs-lookup"><span data-stu-id="ea6c7-158">In the **Filter** flyout that appears, configure any of the following settings:</span></span>

- <span data-ttu-id="ea6c7-159">**Aktion**: Wählen Sie **zulassen**, **blockieren** oder beides aus.</span><span class="sxs-lookup"><span data-stu-id="ea6c7-159">**Action**: Select **Allow**, **Block** or both.</span></span>

- <span data-ttu-id="ea6c7-160">**Läuft nie** ab: Wählen Sie aus (deaktivieren ![ ](../../media/scc-toggle-off.png) ) oder ein (Umschalten ![ ](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png) ) aus.</span><span class="sxs-lookup"><span data-stu-id="ea6c7-160">**Never expire**: Select off (![Toggle off](../../media/scc-toggle-off.png)) or on (![Toggle on](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png)).</span></span>

- <span data-ttu-id="ea6c7-161">**Letzte Aktualisierung**: Wählen Sie ein Startdatum (von), ein Enddatum (**an**) oder beides **aus**.</span><span class="sxs-lookup"><span data-stu-id="ea6c7-161">**Last updated**: Select a start date (**From**), an end date (**To**) or both.</span></span>

- <span data-ttu-id="ea6c7-162">**Ablaufdatum**: Wählen Sie ein Startdatum (von), ein Enddatum (**an**) oder beides **aus**.</span><span class="sxs-lookup"><span data-stu-id="ea6c7-162">**Expiration date**: Select a start date (**From**), an end date (**To**) or both.</span></span>

<span data-ttu-id="ea6c7-163">Wenn Sie fertig sind, klicken Sie auf über **nehmen**.</span><span class="sxs-lookup"><span data-stu-id="ea6c7-163">When you're finished, click **Apply**.</span></span>

<span data-ttu-id="ea6c7-164">Wenn Sie vorhandene Filter löschen möchten, klicken Sie auf **Filter**, und klicken Sie im daraufhin angezeigten **Filter** Flyout auf Filter **Löschen**.</span><span class="sxs-lookup"><span data-stu-id="ea6c7-164">To clear existing filters, click **Filter**, and in the **Filter** flyout that appears, click **Clear filters**.</span></span>

## <a name="use-the-security--compliance-center-to-modify-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="ea6c7-165">Verwenden des Security & Compliance Center zum Ändern von Einträgen in der Liste "Mandanten zulassen/blockieren"</span><span class="sxs-lookup"><span data-stu-id="ea6c7-165">Use the Security & Compliance Center to modify entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="ea6c7-166">Sie können den URL-Wert selbst nicht ändern.</span><span class="sxs-lookup"><span data-stu-id="ea6c7-166">You can't modify the URL value itself.</span></span> <span data-ttu-id="ea6c7-167">Stattdessen müssen Sie den Eintrag löschen und neu erstellen.</span><span class="sxs-lookup"><span data-stu-id="ea6c7-167">Instead, you need to delete the entry and recreate it.</span></span>

1. <span data-ttu-id="ea6c7-168">Wechseln Sie im Security & Compliance Center zu **Bedrohungs Verwaltungs** \> **Richtlinie** \> **Mandanten-Zulassungs-/Sperrlisten**.</span><span class="sxs-lookup"><span data-stu-id="ea6c7-168">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="ea6c7-169">Wählen Sie die Registerkarte **URLs** aus.</span><span class="sxs-lookup"><span data-stu-id="ea6c7-169">Select the **URLs** tab.</span></span>

3. <span data-ttu-id="ea6c7-170">Wählen Sie den Eintrag aus, den Sie ändern möchten, und klicken Sie dann auf Bearbeitungssymbol **Bearbeiten** ![ ](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) .</span><span class="sxs-lookup"><span data-stu-id="ea6c7-170">Select the entry that you want to modify, and then click **Edit** ![Edit icon](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png).</span></span>

4. <span data-ttu-id="ea6c7-171">Konfigurieren Sie im Flyout, das angezeigt wird, die folgenden Einstellungen:</span><span class="sxs-lookup"><span data-stu-id="ea6c7-171">In the flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="ea6c7-172">**Blockieren/zulassen**: Wählen Sie **zulassen** oder **blockieren** aus.</span><span class="sxs-lookup"><span data-stu-id="ea6c7-172">**Block/Allow**: Select **Allow** or **Block**.</span></span>

   - <span data-ttu-id="ea6c7-173">**Nie ablaufen**: führen Sie einen der folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="ea6c7-173">**Never expire**: Do one of the following steps:</span></span>

     - <span data-ttu-id="ea6c7-174">Stellen Sie sicher, dass die Einstellung deaktiviert ist (deaktivieren ![ ](../../media/scc-toggle-off.png) ), und verwenden Sie das Feld **expires on** , um das Ablaufdatum für den Eintrag anzugeben.</span><span class="sxs-lookup"><span data-stu-id="ea6c7-174">Verify the setting is turned off (![Toggle off](../../media/scc-toggle-off.png)) and use the **Expires on** box to specify the expiration date for the entry.</span></span>

     <span data-ttu-id="ea6c7-175">oder</span><span class="sxs-lookup"><span data-stu-id="ea6c7-175">or</span></span>

     - <span data-ttu-id="ea6c7-176">Bewegen Sie die Umschaltfläche nach rechts, um den Eintrag so zu konfigurieren, dass er nie abläuft:</span><span class="sxs-lookup"><span data-stu-id="ea6c7-176">Move the toggle to the right to configure the entry to never expire:</span></span> ![Umschaltfläche ein](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png)<span data-ttu-id="ea6c7-178">.</span><span class="sxs-lookup"><span data-stu-id="ea6c7-178">.</span></span>

   - <span data-ttu-id="ea6c7-179">**Optional Hinweis**: Geben Sie einen beschreibenden Text für den Eintrag ein.</span><span class="sxs-lookup"><span data-stu-id="ea6c7-179">**Optional note**: Enter descriptive text for the entry.</span></span>

5. <span data-ttu-id="ea6c7-180">Klicken Sie nach Abschluss des Vorgangs auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="ea6c7-180">When you're finished, click **Save**.</span></span>

## <a name="use-the-security--compliance-center-to-remove-entries-from-the-tenant-allowblock-list"></a><span data-ttu-id="ea6c7-181">Verwenden des Security & Compliance Center zum Entfernen von Einträgen aus der Liste "Mandanten zulassen/blockieren"</span><span class="sxs-lookup"><span data-stu-id="ea6c7-181">Use the Security & Compliance Center to remove entries from the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="ea6c7-182">Wechseln Sie im Security & Compliance Center zu **Bedrohungs Verwaltungs** \> **Richtlinie** \> **Mandanten-Zulassungs-/Sperrlisten**.</span><span class="sxs-lookup"><span data-stu-id="ea6c7-182">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="ea6c7-183">Wählen Sie die Registerkarte **URLs** aus.</span><span class="sxs-lookup"><span data-stu-id="ea6c7-183">Select the **URLs** tab.</span></span>

3. <span data-ttu-id="ea6c7-184">Wählen Sie den Eintrag aus, den Sie entfernen möchten, und klicken Sie **dann auf Delete** ![ Delete Icon ](../../media/87565fbb-5147-4f22-9ed7-1c18ce664392.png) .</span><span class="sxs-lookup"><span data-stu-id="ea6c7-184">Select the entry that you want to remove, and then click **Delete** ![Delete icon](../../media/87565fbb-5147-4f22-9ed7-1c18ce664392.png).</span></span>

4. <span data-ttu-id="ea6c7-185">Klicken Sie im angezeigten Warndialogfeld auf **Löschen**.</span><span class="sxs-lookup"><span data-stu-id="ea6c7-185">In the warning dialog that appears, click **Delete**.</span></span>

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-the-tenant-allowblock-list"></a><span data-ttu-id="ea6c7-186">Verwenden Exchange Online PowerShell oder eigenständiger EoP PowerShell zum Konfigurieren der Liste "Mandanten zulassen/blockieren"</span><span class="sxs-lookup"><span data-stu-id="ea6c7-186">Use Exchange Online PowerShell or standalone EOP PowerShell to configure the Tenant Allow/Block List</span></span>

### <a name="use-powershell-to-add-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="ea6c7-187">Verwenden von PowerShell zum Hinzufügen von Einträgen in der Liste "Mandanten zulassen/blockieren"</span><span class="sxs-lookup"><span data-stu-id="ea6c7-187">Use PowerShell to add entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="ea6c7-188">Verwenden Sie die folgende Syntax, um Einträge in der Liste Mandanten Allow/Block hinzuzufügen:</span><span class="sxs-lookup"><span data-stu-id="ea6c7-188">To add entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
New-TenantAllowBlockListItems -ListType Url -Action <Allow | Block> -Entries <String[]> [-ExpirationDate <DateTime>] [-NoExpiration] [-Notes <String>]
```

<span data-ttu-id="ea6c7-189">In diesem Beispiel wird ein URL-Sperreintrag für contoso.com und alle Unterdomänen hinzugefügt (beispielsweise contoso.com, www.contoso.com und XYZ.ABC.contoso.com).</span><span class="sxs-lookup"><span data-stu-id="ea6c7-189">This example adds a URL block entry for contoso.com and all subdomains (for example, contoso.com, www.contoso.com, and xyz.abc.contoso.com).</span></span> <span data-ttu-id="ea6c7-190">Da die Parameter ExpirationDate oder NOEXPIRE nicht verwendet wurden, läuft der Eintrag nach 30 Tagen ab.</span><span class="sxs-lookup"><span data-stu-id="ea6c7-190">Because we didn't use the ExpirationDate or NoExpiration parameters, the entry expires after 30 days.</span></span>

```powershell
New-TenantAllowBlockListItem -ListType Url -Action Block -Entries ~contoso.com
```

<span data-ttu-id="ea6c7-191">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [New-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/new-tenantallowblocklistitems).</span><span class="sxs-lookup"><span data-stu-id="ea6c7-191">For detailed syntax and parameter information, see [New-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/new-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-view-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="ea6c7-192">Verwenden von PowerShell zum Anzeigen von Einträgen in der Liste "Mandanten zulassen/blockieren"</span><span class="sxs-lookup"><span data-stu-id="ea6c7-192">Use PowerShell to view entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="ea6c7-193">Verwenden Sie die folgende Syntax, um Einträge in der Liste Mandanten Allow/Block anzuzeigen:</span><span class="sxs-lookup"><span data-stu-id="ea6c7-193">To view entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType Url [-Entry <URLValue>] [-Action <Allow | Block>] [-ExpirationDate <DateTime>] [-NoExpiration]
```

<span data-ttu-id="ea6c7-194">In diesem Beispiel werden alle blockierten URLs zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="ea6c7-194">This example returns all blocked URLs.</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType Url -Action Block
```

<span data-ttu-id="ea6c7-195">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Get-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/get-tenantallowblocklistitems).</span><span class="sxs-lookup"><span data-stu-id="ea6c7-195">For detailed syntax and parameter information, see [Get-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/get-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-modify-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="ea6c7-196">Verwenden von PowerShell zum Ändern von Einträgen in der Liste "Mandanten zulassen/blockieren"</span><span class="sxs-lookup"><span data-stu-id="ea6c7-196">Use PowerShell to modify entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="ea6c7-197">Sie können den URL-Wert selbst nicht ändern.</span><span class="sxs-lookup"><span data-stu-id="ea6c7-197">You can't modify the URL value itself.</span></span> <span data-ttu-id="ea6c7-198">Stattdessen müssen Sie den Eintrag löschen und neu erstellen.</span><span class="sxs-lookup"><span data-stu-id="ea6c7-198">Instead, you need to delete the entry and recreate it.</span></span>

<span data-ttu-id="ea6c7-199">Verwenden Sie die folgende Syntax, um Einträge in der Liste Mandanten Allow/Block zu ändern:</span><span class="sxs-lookup"><span data-stu-id="ea6c7-199">To modify entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Set-TenantAllowBlockListItems -ListType Url -Ids <"Id1","Id2",..."IdN"> [-Action <Allow | Block>] [-ExpirationDate <DateTime>] [-NoExpiration] [-Notes <String>]
```

<span data-ttu-id="ea6c7-200">In diesem Beispiel wird das Ablaufdatum des angegebenen Eintrags geändert.</span><span class="sxs-lookup"><span data-stu-id="ea6c7-200">This example changes the expiration date of the specified entry.</span></span>

```powershell
Set-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSRAAAA" -ExpirationDate (Get-Date "5/30/2020 9:30 AM").ToUniversalTime()
```

<span data-ttu-id="ea6c7-201">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Sets-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/set-tenantallowblocklistitems).</span><span class="sxs-lookup"><span data-stu-id="ea6c7-201">For detailed syntax and parameter information, see [Set-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/set-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-remove-entries-from-the-tenant-allowblock-list"></a><span data-ttu-id="ea6c7-202">Verwenden von PowerShell zum Entfernen von Einträgen aus der Liste "Mandanten zulassen/blockieren"</span><span class="sxs-lookup"><span data-stu-id="ea6c7-202">Use PowerShell to remove entries from the Tenant Allow/Block List</span></span>

<span data-ttu-id="ea6c7-203">Verwenden Sie die folgende Syntax, um Einträge aus der Liste Mandanten Allow/Block zu entfernen:</span><span class="sxs-lookup"><span data-stu-id="ea6c7-203">To remove entries from the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Remove-TenantAllowBlockListItems -ListType Url -Ids <"Id1","Id2",..."IdN">
```

<span data-ttu-id="ea6c7-204">In diesem Beispiel wird der angegebene URL-Eintrag aus der Liste Mandanten-Allow/Block entfernt.</span><span class="sxs-lookup"><span data-stu-id="ea6c7-204">This example removes the specified URL entry from the Tenant Allow/Block List.</span></span>

```powershell
Remove-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSPAAAA0"
```

<span data-ttu-id="ea6c7-205">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Remove-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/remove-tenantallowblocklistitems).</span><span class="sxs-lookup"><span data-stu-id="ea6c7-205">For detailed syntax and parameter information, see [Remove-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/remove-tenantallowblocklistitems).</span></span>

## <a name="url-syntax-for-the-tenant-allowblock-list"></a><span data-ttu-id="ea6c7-206">URL-Syntax für die Liste "Mandanten zulassen/blockieren"</span><span class="sxs-lookup"><span data-stu-id="ea6c7-206">URL syntax for the Tenant Allow/Block List</span></span>

- <span data-ttu-id="ea6c7-207">IP4v-und IPv6-Adressen sind zulässig, TCP/UDP-Ports jedoch nicht.</span><span class="sxs-lookup"><span data-stu-id="ea6c7-207">IP4v and IPv6 addresses are allowed, but TCP/UDP ports are not.</span></span>

- <span data-ttu-id="ea6c7-208">Dateierweiterungen sind nicht zulässig (beispielsweise test.pdf).</span><span class="sxs-lookup"><span data-stu-id="ea6c7-208">Filename extensions are not allowed (for example, test.pdf).</span></span>

- <span data-ttu-id="ea6c7-209">Unicode wird nicht unterstützt, aber Punycode ist.</span><span class="sxs-lookup"><span data-stu-id="ea6c7-209">Unicode is not supported, but Punycode is.</span></span>

- <span data-ttu-id="ea6c7-210">Hostnames sind zulässig, wenn alle der folgenden Aussagen zutreffen:</span><span class="sxs-lookup"><span data-stu-id="ea6c7-210">Hostnames are allowed if all of the following statements are true:</span></span>

  - <span data-ttu-id="ea6c7-211">Der Hostname enthält einen Punkt.</span><span class="sxs-lookup"><span data-stu-id="ea6c7-211">The hostname contains a period.</span></span>
  - <span data-ttu-id="ea6c7-212">Es gibt mindestens ein Zeichen auf der linken Seite des Punkts.</span><span class="sxs-lookup"><span data-stu-id="ea6c7-212">There is at least one character to the left of the period.</span></span>
  - <span data-ttu-id="ea6c7-213">Rechts vom Punkt befinden sich mindestens zwei Zeichen.</span><span class="sxs-lookup"><span data-stu-id="ea6c7-213">There are at least two characters to the right of the period.</span></span>

  <span data-ttu-id="ea6c7-214">Beispielsweise `t.co` ist zulässig; `.com` oder ist `contoso.` nicht zulässig.</span><span class="sxs-lookup"><span data-stu-id="ea6c7-214">For example, `t.co` is allowed; `.com` or `contoso.` are not allowed.</span></span>

- <span data-ttu-id="ea6c7-215">Unterpfade sind nicht impliziert.</span><span class="sxs-lookup"><span data-stu-id="ea6c7-215">Subpaths are not implied.</span></span>

  <span data-ttu-id="ea6c7-216">Enthält beispielsweise `contoso.com` nicht `contoso.com/a` .</span><span class="sxs-lookup"><span data-stu-id="ea6c7-216">For example, `contoso.com` does not include `contoso.com/a`.</span></span>

- <span data-ttu-id="ea6c7-217">Platzhalterzeichen (\*) sind in den folgenden Szenarien zulässig:</span><span class="sxs-lookup"><span data-stu-id="ea6c7-217">Wildcards (\*) are allowed in the following scenarios:</span></span>

  - <span data-ttu-id="ea6c7-218">Auf einen linken Platzhalter muss ein Punkt folgen, um eine Unterdomäne anzugeben.</span><span class="sxs-lookup"><span data-stu-id="ea6c7-218">A left wildcard must be followed by a period to specify a subdomain.</span></span>

    <span data-ttu-id="ea6c7-219">Beispielsweise `*.contoso.com` ist zulässig; `*contoso.com` ist nicht zulässig.</span><span class="sxs-lookup"><span data-stu-id="ea6c7-219">For example, `*.contoso.com` is allowed; `*contoso.com` is not allowed.</span></span>

  - <span data-ttu-id="ea6c7-220">Ein rechter Platzhalter muss einem Schrägstrich (/) entsprechen, um einen Pfad anzugeben.</span><span class="sxs-lookup"><span data-stu-id="ea6c7-220">A right wildcard must follow a forward slash (/) to specify a path.</span></span>

    <span data-ttu-id="ea6c7-221">Beispielsweise `contoso.com/*` ist zulässig; `contoso.com*` oder ist `contoso.com/ab*` nicht zulässig.</span><span class="sxs-lookup"><span data-stu-id="ea6c7-221">For example, `contoso.com/*` is allowed; `contoso.com*` or `contoso.com/ab*` are not allowed.</span></span>

  - <span data-ttu-id="ea6c7-222">Alle untergeordneten Pfade sind nicht durch einen richtigen Platzhalter impliziert.</span><span class="sxs-lookup"><span data-stu-id="ea6c7-222">All subpaths are not implied by a right wildcard.</span></span>

    <span data-ttu-id="ea6c7-223">Enthält beispielsweise `contoso.com/*` nicht `contoso.com/a` .</span><span class="sxs-lookup"><span data-stu-id="ea6c7-223">For example, `contoso.com/*` does not include `contoso.com/a`.</span></span>

  - <span data-ttu-id="ea6c7-224">`*.com*` ist ungültig (keine auflösbare Domäne, und der Rechte Platzhalter folgt keinem Schrägstrich).</span><span class="sxs-lookup"><span data-stu-id="ea6c7-224">`*.com*` is invalid (not a resolvable domain and the right wildcard does not follow a forward slash).</span></span>

  - <span data-ttu-id="ea6c7-225">Platzhalter sind in IP-Adressen nicht zulässig.</span><span class="sxs-lookup"><span data-stu-id="ea6c7-225">Wildcards are not allowed in IP addresses.</span></span>

- <span data-ttu-id="ea6c7-226">Das Tildezeichen (~) steht in den folgenden Szenarien zur Verfügung:</span><span class="sxs-lookup"><span data-stu-id="ea6c7-226">The tilde (~) character is available in the following scenarios:</span></span>

  - <span data-ttu-id="ea6c7-227">Eine linke Tilde impliziert eine Domäne und alle Unterdomänen.</span><span class="sxs-lookup"><span data-stu-id="ea6c7-227">A left tilde implies a domain and all subdomains.</span></span>

    <span data-ttu-id="ea6c7-228">Beispielsweise `~contoso.com` enthält `contoso.com` und `*.contoso.com` .</span><span class="sxs-lookup"><span data-stu-id="ea6c7-228">For example `~contoso.com` includes `contoso.com` and `*.contoso.com`.</span></span>

- <span data-ttu-id="ea6c7-229">URL-Einträge, die Protokolle enthalten (beispielsweise,, `http://` `https://` oder `ftp://` ) schlagen fehl, da URL-Einträge auf alle Protokolle angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="ea6c7-229">URL entries that contain protocols (for example, `http://`, `https://`, or `ftp://`) will fail, because URL entries apply to all protocols.</span></span>

- <span data-ttu-id="ea6c7-230">Ein Benutzername oder ein Kennwort werden nicht unterstützt oder erforderlich.</span><span class="sxs-lookup"><span data-stu-id="ea6c7-230">A username or password aren't supported or required.</span></span>

- <span data-ttu-id="ea6c7-231">Anführungszeichen (' oder ') sind ungültige Zeichen.</span><span class="sxs-lookup"><span data-stu-id="ea6c7-231">Quotes (' or ") are invalid characters.</span></span>

- <span data-ttu-id="ea6c7-232">Eine URL sollte nach Möglichkeit alle Umleitungen enthalten.</span><span class="sxs-lookup"><span data-stu-id="ea6c7-232">A URL should include all redirects where possible.</span></span>

### <a name="url-entry-scenarios"></a><span data-ttu-id="ea6c7-233">URL-Eintrags Szenarien</span><span class="sxs-lookup"><span data-stu-id="ea6c7-233">URL entry scenarios</span></span>

<span data-ttu-id="ea6c7-234">In den folgenden Abschnitten werden gültige URL-Einträge und ihre Ergebnisse beschrieben.</span><span class="sxs-lookup"><span data-stu-id="ea6c7-234">Valid URL entries and their results are described in the following sections.</span></span>

#### <a name="scenario-no-wildcards"></a><span data-ttu-id="ea6c7-235">Szenario: keine Platzhalter</span><span class="sxs-lookup"><span data-stu-id="ea6c7-235">Scenario: No wildcards</span></span>

<span data-ttu-id="ea6c7-236">**Eintrag**: `contoso.com`</span><span class="sxs-lookup"><span data-stu-id="ea6c7-236">**Entry**: `contoso.com`</span></span>

- <span data-ttu-id="ea6c7-237">**Übereinstimmung zulassen**: contoso.com</span><span class="sxs-lookup"><span data-stu-id="ea6c7-237">**Allow match**: contoso.com</span></span>

- <span data-ttu-id="ea6c7-238">**Zulassen nicht abgeglichen**:</span><span class="sxs-lookup"><span data-stu-id="ea6c7-238">**Allow not matched**:</span></span>

  - <span data-ttu-id="ea6c7-239">abc-contoso.com</span><span class="sxs-lookup"><span data-stu-id="ea6c7-239">abc-contoso.com</span></span>
  - <span data-ttu-id="ea6c7-240">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="ea6c7-240">contoso.com/a</span></span>
  - <span data-ttu-id="ea6c7-241">payroll.contoso.com</span><span class="sxs-lookup"><span data-stu-id="ea6c7-241">payroll.contoso.com</span></span>
  - <span data-ttu-id="ea6c7-242">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="ea6c7-242">test.com/contoso.com</span></span>
  - <span data-ttu-id="ea6c7-243">test.com/q=contoso.com</span><span class="sxs-lookup"><span data-stu-id="ea6c7-243">test.com/q=contoso.com</span></span>
  - <span data-ttu-id="ea6c7-244">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="ea6c7-244">www.contoso.com</span></span>
  - <span data-ttu-id="ea6c7-245">www. contoso. com/q = a@contoso. com</span><span class="sxs-lookup"><span data-stu-id="ea6c7-245">www.contoso.com/q=a@contoso.com</span></span>

- <span data-ttu-id="ea6c7-246">**Block Übereinstimmung**:</span><span class="sxs-lookup"><span data-stu-id="ea6c7-246">**Block match**:</span></span>

  - <span data-ttu-id="ea6c7-247">contoso.com</span><span class="sxs-lookup"><span data-stu-id="ea6c7-247">contoso.com</span></span>
  - <span data-ttu-id="ea6c7-248">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="ea6c7-248">contoso.com/a</span></span>
  - <span data-ttu-id="ea6c7-249">payroll.contoso.com</span><span class="sxs-lookup"><span data-stu-id="ea6c7-249">payroll.contoso.com</span></span>
  - <span data-ttu-id="ea6c7-250">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="ea6c7-250">test.com/contoso.com</span></span>
  - <span data-ttu-id="ea6c7-251">test.com/q=contoso.com</span><span class="sxs-lookup"><span data-stu-id="ea6c7-251">test.com/q=contoso.com</span></span>
  - <span data-ttu-id="ea6c7-252">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="ea6c7-252">www.contoso.com</span></span>
  - <span data-ttu-id="ea6c7-253">www. contoso. com/q = a@contoso. com</span><span class="sxs-lookup"><span data-stu-id="ea6c7-253">www.contoso.com/q=a@contoso.com</span></span>

- <span data-ttu-id="ea6c7-254">**Block nicht abgeglichen**: ABC-contoso.com</span><span class="sxs-lookup"><span data-stu-id="ea6c7-254">**Block not matched**: abc-contoso.com</span></span>

#### <a name="scenario-left-wildcard-subdomain"></a><span data-ttu-id="ea6c7-255">Szenario: Linker Platzhalter (Unterdomäne)</span><span class="sxs-lookup"><span data-stu-id="ea6c7-255">Scenario: Left wildcard (subdomain)</span></span>

<span data-ttu-id="ea6c7-256">**Eintrag**: `*.contoso.com`</span><span class="sxs-lookup"><span data-stu-id="ea6c7-256">**Entry**: `*.contoso.com`</span></span>

- <span data-ttu-id="ea6c7-257">Übereinstimmung und **Block Übereinstimmung** **zulassen** :</span><span class="sxs-lookup"><span data-stu-id="ea6c7-257">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="ea6c7-258">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="ea6c7-258">www.contoso.com</span></span>
  - <span data-ttu-id="ea6c7-259">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="ea6c7-259">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="ea6c7-260">**Zulassen nicht abgeglichen** und **Block nicht abgeglichen**:</span><span class="sxs-lookup"><span data-stu-id="ea6c7-260">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="ea6c7-261">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="ea6c7-261">123contoso.com</span></span>
  - <span data-ttu-id="ea6c7-262">contoso.com</span><span class="sxs-lookup"><span data-stu-id="ea6c7-262">contoso.com</span></span>
  - <span data-ttu-id="ea6c7-263">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="ea6c7-263">test.com/contoso.com</span></span>
  - <span data-ttu-id="ea6c7-264">www.contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="ea6c7-264">www.contoso.com/abc</span></span>

#### <a name="scenario-right-wildcard-at-top-of-path"></a><span data-ttu-id="ea6c7-265">Szenario: rechter Platzhalter oben im Pfad</span><span class="sxs-lookup"><span data-stu-id="ea6c7-265">Scenario: Right wildcard at top of path</span></span>

<span data-ttu-id="ea6c7-266">**Eintrag**: `contoso.com/a/*`</span><span class="sxs-lookup"><span data-stu-id="ea6c7-266">**Entry**: `contoso.com/a/*`</span></span>

- <span data-ttu-id="ea6c7-267">Übereinstimmung und **Block Übereinstimmung** **zulassen** :</span><span class="sxs-lookup"><span data-stu-id="ea6c7-267">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="ea6c7-268">contoso.com/a/b</span><span class="sxs-lookup"><span data-stu-id="ea6c7-268">contoso.com/a/b</span></span>
  - <span data-ttu-id="ea6c7-269">contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="ea6c7-269">contoso.com/a/b/c</span></span>
  - <span data-ttu-id="ea6c7-270">contoso. com/a/? q = Joe@t. com</span><span class="sxs-lookup"><span data-stu-id="ea6c7-270">contoso.com/a/?q=joe@t.com</span></span>

- <span data-ttu-id="ea6c7-271">**Zulassen nicht abgeglichen** und **Block nicht abgeglichen**:</span><span class="sxs-lookup"><span data-stu-id="ea6c7-271">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="ea6c7-272">contoso.com</span><span class="sxs-lookup"><span data-stu-id="ea6c7-272">contoso.com</span></span>
  - <span data-ttu-id="ea6c7-273">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="ea6c7-273">contoso.com/a</span></span>
  - <span data-ttu-id="ea6c7-274">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="ea6c7-274">www.contoso.com</span></span>
  - <span data-ttu-id="ea6c7-275">www. contoso. com/q = a@contoso. com</span><span class="sxs-lookup"><span data-stu-id="ea6c7-275">www.contoso.com/q=a@contoso.com</span></span>

#### <a name="scenario-left-tilde"></a><span data-ttu-id="ea6c7-276">Szenario: linke Tilde</span><span class="sxs-lookup"><span data-stu-id="ea6c7-276">Scenario: Left tilde</span></span>

<span data-ttu-id="ea6c7-277">**Eintrag**: `~contoso.com`</span><span class="sxs-lookup"><span data-stu-id="ea6c7-277">**Entry**: `~contoso.com`</span></span>

- <span data-ttu-id="ea6c7-278">Übereinstimmung und **Block Übereinstimmung** **zulassen** :</span><span class="sxs-lookup"><span data-stu-id="ea6c7-278">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="ea6c7-279">contoso.com</span><span class="sxs-lookup"><span data-stu-id="ea6c7-279">contoso.com</span></span>
  - <span data-ttu-id="ea6c7-280">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="ea6c7-280">www.contoso.com</span></span>
  - <span data-ttu-id="ea6c7-281">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="ea6c7-281">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="ea6c7-282">**Zulassen nicht abgeglichen** und **Block nicht abgeglichen**:</span><span class="sxs-lookup"><span data-stu-id="ea6c7-282">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="ea6c7-283">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="ea6c7-283">123contoso.com</span></span>
  - <span data-ttu-id="ea6c7-284">contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="ea6c7-284">contoso.com/abc</span></span>
  - <span data-ttu-id="ea6c7-285">www.contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="ea6c7-285">www.contoso.com/abc</span></span>

#### <a name="scenario-right-wildcard-suffix"></a><span data-ttu-id="ea6c7-286">Szenario: Rechtes Platzhalter Suffix</span><span class="sxs-lookup"><span data-stu-id="ea6c7-286">Scenario: Right wildcard suffix</span></span>

<span data-ttu-id="ea6c7-287">**Eintrag**: `contoso.com/*`</span><span class="sxs-lookup"><span data-stu-id="ea6c7-287">**Entry**: `contoso.com/*`</span></span>

- <span data-ttu-id="ea6c7-288">Übereinstimmung und **Block Übereinstimmung** **zulassen** :</span><span class="sxs-lookup"><span data-stu-id="ea6c7-288">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="ea6c7-289">contoso. com/? q = whatever@fabrikam. com</span><span class="sxs-lookup"><span data-stu-id="ea6c7-289">contoso.com/?q=whatever@fabrikam.com</span></span>
  - <span data-ttu-id="ea6c7-290">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="ea6c7-290">contoso.com/a</span></span>
  - <span data-ttu-id="ea6c7-291">contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="ea6c7-291">contoso.com/a/b/c</span></span>
  - <span data-ttu-id="ea6c7-292">contoso.com/ab</span><span class="sxs-lookup"><span data-stu-id="ea6c7-292">contoso.com/ab</span></span>
  - <span data-ttu-id="ea6c7-293">contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="ea6c7-293">contoso.com/b</span></span>
  - <span data-ttu-id="ea6c7-294">contoso.com/b/a/c</span><span class="sxs-lookup"><span data-stu-id="ea6c7-294">contoso.com/b/a/c</span></span>
  - <span data-ttu-id="ea6c7-295">contoso.com/ba</span><span class="sxs-lookup"><span data-stu-id="ea6c7-295">contoso.com/ba</span></span>

- <span data-ttu-id="ea6c7-296">**Allow NOT MATCHED** and **Block NOT MATCHED**: contoso.com</span><span class="sxs-lookup"><span data-stu-id="ea6c7-296">**Allow not matched** and **Block not matched**: contoso.com</span></span>

#### <a name="scenario-left-wildcard-subdomain-and-right-wildcard-suffix"></a><span data-ttu-id="ea6c7-297">Szenario: linke Platzhalter-Unterdomäne und Rechte Platzhalter Suffix</span><span class="sxs-lookup"><span data-stu-id="ea6c7-297">Scenario: Left wildcard subdomain and right wildcard suffix</span></span>

<span data-ttu-id="ea6c7-298">**Eintrag**: `*.contoso.com/*`</span><span class="sxs-lookup"><span data-stu-id="ea6c7-298">**Entry**: `*.contoso.com/*`</span></span>

- <span data-ttu-id="ea6c7-299">Übereinstimmung und **Block Übereinstimmung** **zulassen** :</span><span class="sxs-lookup"><span data-stu-id="ea6c7-299">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="ea6c7-300">abc.contoso.com/ab</span><span class="sxs-lookup"><span data-stu-id="ea6c7-300">abc.contoso.com/ab</span></span>
  - <span data-ttu-id="ea6c7-301">abc.xyz.contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="ea6c7-301">abc.xyz.contoso.com/a/b/c</span></span>
  - <span data-ttu-id="ea6c7-302">www.contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="ea6c7-302">www.contoso.com/a</span></span>
  - <span data-ttu-id="ea6c7-303">www.contoso.com/b/a/c</span><span class="sxs-lookup"><span data-stu-id="ea6c7-303">www.contoso.com/b/a/c</span></span>
  - <span data-ttu-id="ea6c7-304">xyz.contoso.com/ba</span><span class="sxs-lookup"><span data-stu-id="ea6c7-304">xyz.contoso.com/ba</span></span>

- <span data-ttu-id="ea6c7-305">**Allow NOT MATCHED** and **Block NOT MATCHED**: contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="ea6c7-305">**Allow not matched** and **Block not matched**: contoso.com/b</span></span>

#### <a name="scenario-left-and-right-tilde"></a><span data-ttu-id="ea6c7-306">Szenario: linke und Rechte Tilde</span><span class="sxs-lookup"><span data-stu-id="ea6c7-306">Scenario: Left and right tilde</span></span>

<span data-ttu-id="ea6c7-307">**Eintrag**: `~contoso.com~`</span><span class="sxs-lookup"><span data-stu-id="ea6c7-307">**Entry**: `~contoso.com~`</span></span>

- <span data-ttu-id="ea6c7-308">Übereinstimmung und **Block Übereinstimmung** **zulassen** :</span><span class="sxs-lookup"><span data-stu-id="ea6c7-308">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="ea6c7-309">contoso.com</span><span class="sxs-lookup"><span data-stu-id="ea6c7-309">contoso.com</span></span>
  - <span data-ttu-id="ea6c7-310">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="ea6c7-310">contoso.com/a</span></span>
  - <span data-ttu-id="ea6c7-311">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="ea6c7-311">www.contoso.com</span></span>
  - <span data-ttu-id="ea6c7-312">www.contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="ea6c7-312">www.contoso.com/b</span></span>
  - <span data-ttu-id="ea6c7-313">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="ea6c7-313">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="ea6c7-314">**Zulassen nicht abgeglichen** und **Block nicht abgeglichen**:</span><span class="sxs-lookup"><span data-stu-id="ea6c7-314">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="ea6c7-315">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="ea6c7-315">123contoso.com</span></span>
  - <span data-ttu-id="ea6c7-316">contoso.org</span><span class="sxs-lookup"><span data-stu-id="ea6c7-316">contoso.org</span></span>

#### <a name="scenario-ip-address"></a><span data-ttu-id="ea6c7-317">Szenario: IP-Adresse</span><span class="sxs-lookup"><span data-stu-id="ea6c7-317">Scenario: IP address</span></span>

<span data-ttu-id="ea6c7-318">**Eintrag**: `1.2.3.4`</span><span class="sxs-lookup"><span data-stu-id="ea6c7-318">**Entry**: `1.2.3.4`</span></span>

- <span data-ttu-id="ea6c7-319">Übereinstimmung **zulassen** und **Block Übereinstimmung**: 1.2.3.4</span><span class="sxs-lookup"><span data-stu-id="ea6c7-319">**Allow match** and **Block match**: 1.2.3.4</span></span>

- <span data-ttu-id="ea6c7-320">**Zulassen nicht abgeglichen** und **Block nicht abgeglichen**:</span><span class="sxs-lookup"><span data-stu-id="ea6c7-320">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="ea6c7-321">1.2.3.4/a</span><span class="sxs-lookup"><span data-stu-id="ea6c7-321">1.2.3.4/a</span></span>
  - <span data-ttu-id="ea6c7-322">11.2.3.4/a</span><span class="sxs-lookup"><span data-stu-id="ea6c7-322">11.2.3.4/a</span></span>

#### <a name="ip-address-with-right-wildcard"></a><span data-ttu-id="ea6c7-323">IP-Adresse mit dem richtigen Platzhalter</span><span class="sxs-lookup"><span data-stu-id="ea6c7-323">IP address with right wildcard</span></span>

<span data-ttu-id="ea6c7-324">**Eintrag**: `1.2.3.4/*`</span><span class="sxs-lookup"><span data-stu-id="ea6c7-324">**Entry**: `1.2.3.4/*`</span></span>

- <span data-ttu-id="ea6c7-325">Übereinstimmung und **Block Übereinstimmung** **zulassen** :</span><span class="sxs-lookup"><span data-stu-id="ea6c7-325">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="ea6c7-326">1.2.3.4/b</span><span class="sxs-lookup"><span data-stu-id="ea6c7-326">1.2.3.4/b</span></span>
  - <span data-ttu-id="ea6c7-327">1.2.3.4/baaaa</span><span class="sxs-lookup"><span data-stu-id="ea6c7-327">1.2.3.4/baaaa</span></span>

### <a name="examples-of-invalid-entries"></a><span data-ttu-id="ea6c7-328">Beispiele für ungültige Einträge</span><span class="sxs-lookup"><span data-stu-id="ea6c7-328">Examples of invalid entries</span></span>

<span data-ttu-id="ea6c7-329">Die folgenden Einträge sind ungültig:</span><span class="sxs-lookup"><span data-stu-id="ea6c7-329">The following entries are invalid:</span></span>

- <span data-ttu-id="ea6c7-330">**Fehlende oder ungültige Domänenwerte**:</span><span class="sxs-lookup"><span data-stu-id="ea6c7-330">**Missing or invalid domain values**:</span></span>

  - <span data-ttu-id="ea6c7-331">contoso</span><span class="sxs-lookup"><span data-stu-id="ea6c7-331">contoso</span></span>
  - <span data-ttu-id="ea6c7-332">\*contoso.\*</span><span class="sxs-lookup"><span data-stu-id="ea6c7-332">\*.contoso.\*</span></span>
  - <span data-ttu-id="ea6c7-333">\*. com</span><span class="sxs-lookup"><span data-stu-id="ea6c7-333">\*.com</span></span>
  - <span data-ttu-id="ea6c7-334">\*. PDF</span><span class="sxs-lookup"><span data-stu-id="ea6c7-334">\*.pdf</span></span>

- <span data-ttu-id="ea6c7-335">**Platzhalter für Text oder ohne Leerzeichen**:</span><span class="sxs-lookup"><span data-stu-id="ea6c7-335">**Wildcard on text or without spacing characters**:</span></span>

  - <span data-ttu-id="ea6c7-336">\*contoso.com</span><span class="sxs-lookup"><span data-stu-id="ea6c7-336">\*contoso.com</span></span>
  - <span data-ttu-id="ea6c7-337">contoso.com\*</span><span class="sxs-lookup"><span data-stu-id="ea6c7-337">contoso.com\*</span></span>
  - <span data-ttu-id="ea6c7-338">\*1.2.3.4</span><span class="sxs-lookup"><span data-stu-id="ea6c7-338">\*1.2.3.4</span></span>
  - <span data-ttu-id="ea6c7-339">1.2.3.4\*</span><span class="sxs-lookup"><span data-stu-id="ea6c7-339">1.2.3.4\*</span></span>
  - <span data-ttu-id="ea6c7-340">contoso.com/a\*</span><span class="sxs-lookup"><span data-stu-id="ea6c7-340">contoso.com/a\*</span></span>
  - <span data-ttu-id="ea6c7-341">contoso.com/ab\*</span><span class="sxs-lookup"><span data-stu-id="ea6c7-341">contoso.com/ab\*</span></span>

- <span data-ttu-id="ea6c7-342">**IP-Adressen mit Ports**:</span><span class="sxs-lookup"><span data-stu-id="ea6c7-342">**IP addresses with ports**:</span></span>

  - <span data-ttu-id="ea6c7-343">contoso.com:443</span><span class="sxs-lookup"><span data-stu-id="ea6c7-343">contoso.com:443</span></span>
  - <span data-ttu-id="ea6c7-344">abc.contoso.com:25</span><span class="sxs-lookup"><span data-stu-id="ea6c7-344">abc.contoso.com:25</span></span>

- <span data-ttu-id="ea6c7-345">**Nicht beschreibende Platzhalter**:</span><span class="sxs-lookup"><span data-stu-id="ea6c7-345">**Non-descriptive wildcards**:</span></span>

  - \*
  - <span data-ttu-id="ea6c7-346">\*.\*</span><span class="sxs-lookup"><span data-stu-id="ea6c7-346">\*.\*</span></span>

- <span data-ttu-id="ea6c7-347">**Mittlere Platzhalter**:</span><span class="sxs-lookup"><span data-stu-id="ea6c7-347">**Middle wildcards**:</span></span>

  - <span data-ttu-id="ea6c7-348">Conto \* so.com</span><span class="sxs-lookup"><span data-stu-id="ea6c7-348">conto\*so.com</span></span>
  - <span data-ttu-id="ea6c7-349">Conto ~ so. com</span><span class="sxs-lookup"><span data-stu-id="ea6c7-349">conto~so.com</span></span>

- <span data-ttu-id="ea6c7-350">**Doppelte Platzhalter**</span><span class="sxs-lookup"><span data-stu-id="ea6c7-350">**Double wildcards**</span></span>

  - <span data-ttu-id="ea6c7-351">contoso.com/\*\*</span><span class="sxs-lookup"><span data-stu-id="ea6c7-351">contoso.com/\*\*</span></span>
  - <span data-ttu-id="ea6c7-352">contoso.com/\*/\*</span><span class="sxs-lookup"><span data-stu-id="ea6c7-352">contoso.com/\*/\*</span></span>
