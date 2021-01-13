---
title: Verwalten Der zulässigen und blockierten Mandanten in der Liste der zulässigen/blockierten Mandanten
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
description: Administratoren können erfahren, wie Sie Dies in der Liste der zulässigen/blockierten Mandanten im Sicherheitsportal konfigurieren.
ms.openlocfilehash: c789b09224d00f5bb41ae29d6d2a6efa64d23a8d
ms.sourcegitcommit: 495b66b77d6dbe6d69e5b06b304089e4e476e568
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49799713"
---
# <a name="managing-allows-and-blocks-in-the-tenant-allowblock-list"></a><span data-ttu-id="a60ed-103">Verwalten von Zulässigen und Blöcken in der Liste der zulässigen/blockierten Mandanten</span><span class="sxs-lookup"><span data-stu-id="a60ed-103">Managing allows and blocks in the Tenant Allow/Block List</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


> [!NOTE]
> <span data-ttu-id="a60ed-104">Die in diesem Artikel beschriebenen Features befinden sich in der Vorschau, können geändert werden und sind nicht in allen Organisationen verfügbar.</span><span class="sxs-lookup"><span data-stu-id="a60ed-104">The features described in this article are in Preview, are subject to change, and are not available in all organizations.</span></span>

<span data-ttu-id="a60ed-105">In Microsoft 365-Organisationen mit Postfächern in Exchange Online oder eigenständigen Exchange Online Protection (EOP)-Organisationen ohne Exchange Online-Postfächer sind Sie möglicherweise mit der EOP-Filterungs-Ansicht nicht einverstanden.</span><span class="sxs-lookup"><span data-stu-id="a60ed-105">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, you might disagree with the EOP filtering verdict.</span></span> <span data-ttu-id="a60ed-106">Beispielsweise kann eine gute Nachricht als "schlecht" (ein falsch positives Ergebnis) oder eine ungültige Nachricht als "schlecht" (falsch negativ) markiert werden.</span><span class="sxs-lookup"><span data-stu-id="a60ed-106">For example, a good message might be marked as bad (a false positive), or a bad message might be allowed through (a false negative).</span></span>

<span data-ttu-id="a60ed-107">Mit der Liste der zulässigen/blockierten Mandanten im Security & Compliance Center können Sie die Microsoft 365-Filterungsverkn/-nkungen manuell außer Kraft setzen.</span><span class="sxs-lookup"><span data-stu-id="a60ed-107">The Tenant Allow/Block List in the Security & Compliance Center gives you a way to manually override the Microsoft 365 filtering verdicts.</span></span> <span data-ttu-id="a60ed-108">Die Liste der zulässigen/blockierten Mandanten wird während des Nachrichtenflusses und zum Zeitpunkt der Klicks des Benutzers verwendet.</span><span class="sxs-lookup"><span data-stu-id="a60ed-108">The Tenant Allow/Block List is used during mail flow and at the time of user clicks.</span></span> <span data-ttu-id="a60ed-109">Sie können URLs angeben, die in der Liste der zulässigen/blockierten Mandanten zulässig oder blockiert werden.</span><span class="sxs-lookup"><span data-stu-id="a60ed-109">You can specify URLs to allow or block in the Tenant Allow/Block List.</span></span>

<span data-ttu-id="a60ed-110">In diesem Thema wird beschrieben, wie Sie Einträge in der Liste der zulässigen/blockierten Mandanten im Security & Compliance Center oder in PowerShell konfigurieren (Exchange Online PowerShell für Microsoft 365-Organisationen mit Postfächern in Exchange Online; eigenständige EOP PowerShell für Organisationen ohne Exchange Online-Postfächer).</span><span class="sxs-lookup"><span data-stu-id="a60ed-110">This topic describes how to configure entries in the Tenant Allow/Block List in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="a60ed-111">Was sollten Sie wissen, bevor Sie beginnen?</span><span class="sxs-lookup"><span data-stu-id="a60ed-111">What do you need to know before you begin?</span></span>

- <span data-ttu-id="a60ed-112">Sie öffnen das Security & Compliance Center unter <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="a60ed-112">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="a60ed-113">Verwenden Sie dies, um direkt zur Seite **"Mandanten-Allow/Block List"** zu <https://protection.office.com/tenantAllowBlockList> wechseln.</span><span class="sxs-lookup"><span data-stu-id="a60ed-113">To go directly to the **Tenant Allow/Block List** page, use <https://protection.office.com/tenantAllowBlockList>.</span></span>

- <span data-ttu-id="a60ed-114">Die verfügbaren #A0 werden weiter unten in diesem Artikel in der #A1 für den Abschnitt "Mandanten [zulassen/blockieren"](#url-syntax-for-the-tenant-allowblock-list) beschrieben.</span><span class="sxs-lookup"><span data-stu-id="a60ed-114">The available URL values are described in the [URL syntax for the Tenant Allow/Block List](#url-syntax-for-the-tenant-allowblock-list) section later in this article.</span></span>

- <span data-ttu-id="a60ed-115">Die Liste der zulässigen/blockierten Mandanten lässt maximal 500 Einträge für URLs zu.</span><span class="sxs-lookup"><span data-stu-id="a60ed-115">The Tenant Allow/Block List allows a maximum of 500 entries for URLs.</span></span>

- <span data-ttu-id="a60ed-116">Ein Eintrag sollte innerhalb von 15 Minuten aktiv sein.</span><span class="sxs-lookup"><span data-stu-id="a60ed-116">An entry should be active within 15 minutes.</span></span>

- <span data-ttu-id="a60ed-117">Blockeinträge haben Vorrang vor Zulässigen Einträgen.</span><span class="sxs-lookup"><span data-stu-id="a60ed-117">Block entries take precedence over allow entries.</span></span>

- <span data-ttu-id="a60ed-118">Standardmäßig laufen Einträge in der Liste der zulässigen/blockierten Mandanten nach 30 Tagen ab.</span><span class="sxs-lookup"><span data-stu-id="a60ed-118">By default, entries in the Tenant Allow/Block List will expire after 30 days.</span></span> <span data-ttu-id="a60ed-119">Sie können ein Datum angeben oder festlegen, dass es nie abläuft.</span><span class="sxs-lookup"><span data-stu-id="a60ed-119">You can specify a date or set them to never expire.</span></span>

- <span data-ttu-id="a60ed-120">Wie Sie eine Verbindung mit Exchange Online PowerShell herstellen, finden Sie unter [Herstellen einer Verbindung mit Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="a60ed-120">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="a60ed-121">Informationen zum Herstellen einer Verbindung mit dem eigenständigen Exchange Online Protection PowerShell finden Sie unter [Verbinden mit PowerShell in Exchange Online Protection](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="a60ed-121">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="a60ed-122">Bevor Sie die Verfahren in diesem Artikel ausführen können, müssen Ihnen im Security & Compliance Center Berechtigungen zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="a60ed-122">You need to be assigned permissions in the Security & Compliance Center before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="a60ed-123">Zum Hinzufügen und Entfernen von Werten aus der Liste zulässiger/blockierter Mandanten müssen Sie Mitglied der Rollengruppe "Organisationsverwaltung" oder **"Sicherheitsadministrator"** sein. </span><span class="sxs-lookup"><span data-stu-id="a60ed-123">To add and remove values from the Tenant Allow/Block List, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="a60ed-124">Für den schreibgeschützten Zugriff auf die Liste zulässiger/blockierter  Mandanten müssen Sie Mitglied der Rollengruppe "Globaler Leser" oder **"Sicherheitsleser"** sein.</span><span class="sxs-lookup"><span data-stu-id="a60ed-124">For read-only access to the Tenant Allow/Block List, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="a60ed-125">Weitere Informationen finden Sie unter [Berechtigungen im Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="a60ed-125">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

  <span data-ttu-id="a60ed-126">**Hinweise**:</span><span class="sxs-lookup"><span data-stu-id="a60ed-126">**Notes**:</span></span>

  - <span data-ttu-id="a60ed-127">Durch das Hinzufügen von Benutzern zur entsprechenden Azure Active Directory-Rolle im Microsoft 365 Admin Center erhalten Benutzer die erforderlichen Berechtigungen im Security & Compliance Center _und_ Berechtigungen für andere Features in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="a60ed-127">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Security & Compliance Center _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="a60ed-128">Weitere Informationen finden Sie unter [Informationen zu Administratorrollen](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).</span><span class="sxs-lookup"><span data-stu-id="a60ed-128">For more information, see [About admin roles](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).</span></span>
  - <span data-ttu-id="a60ed-129">Die Rollengruppe **Organisationsverwaltung mit Leserechten** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) ermöglicht auch einen schreibgeschützten Zugriff auf das Feature.</span><span class="sxs-lookup"><span data-stu-id="a60ed-129">The **View-Only Organization Management** role group in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

## <a name="use-the-security--compliance-center-to-create-url-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="a60ed-130">Verwenden des Security & Compliance Center zum Erstellen von URL-Einträgen in der Liste der zulässigen/blockierten Mandanten</span><span class="sxs-lookup"><span data-stu-id="a60ed-130">Use the Security & Compliance Center to create URL entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="a60ed-131">Weitere Informationen zur Syntax für #A0 finden Sie in der #A1 für den Abschnitt ["Mandanten-Zulassen/Sperrliste"](#url-syntax-for-the-tenant-allowblock-list) weiter unten in diesem Artikel.</span><span class="sxs-lookup"><span data-stu-id="a60ed-131">For details about the syntax for URL entries, see the [URL syntax for the Tenant Allow/Block List](#url-syntax-for-the-tenant-allowblock-list) section later in this article.</span></span>

1. <span data-ttu-id="a60ed-132">Wechseln Sie im Security & Compliance  Center zu "Richtlinienrichtlinien-Mandanten-Allow/Block \>  \> **Lists".**</span><span class="sxs-lookup"><span data-stu-id="a60ed-132">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="a60ed-133">Überprüfen Sie **auf der** Seite "Mandanten-Zulassen/Sperrliste", ob die Registerkarte **"URLs"** ausgewählt ist, und klicken Sie dann auf "Hinzufügen". </span><span class="sxs-lookup"><span data-stu-id="a60ed-133">On the **Tenant Allow/Block List** page, verify that the **URLs** tab is selected, and then click **Add**</span></span>

3. <span data-ttu-id="a60ed-134">Konfigurieren Sie **im angezeigten** Flyout "Neue URLs hinzufügen" die folgenden Einstellungen:</span><span class="sxs-lookup"><span data-stu-id="a60ed-134">In the **Add new URLs** flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="a60ed-135">**Fügen Sie URLs mit Platzhaltern hinzu:** Geben Sie eine URL pro Zeile ein, bis zu maximal 20.</span><span class="sxs-lookup"><span data-stu-id="a60ed-135">**Add URLs with wildcards**: Enter one URL per line, up to a maximum of 20.</span></span>

   - <span data-ttu-id="a60ed-136">**Blockieren/Zulassen:** Wählen Sie  aus, ob Sie die **angegebenen** URLs zulassen oder blockieren möchten.</span><span class="sxs-lookup"><span data-stu-id="a60ed-136">**Block/Allow**: Select whether you want to **Allow** or **Block** the specified URLs.</span></span>

   - <span data-ttu-id="a60ed-137">**Läuft nie** ab: Gehen Sie wie folgt vor:</span><span class="sxs-lookup"><span data-stu-id="a60ed-137">**Never expire**: Do one of the following steps:</span></span>

     - <span data-ttu-id="a60ed-138">Stellen Sie sicher, dass die Einstellung deaktiviert ist (Umschalten aus), und verwenden Sie das Feld "Abläuft bei", um das Ablaufdatum ![ ](../../media/scc-toggle-off.png) für die Einträge anzugeben. </span><span class="sxs-lookup"><span data-stu-id="a60ed-138">Verify the setting is turned off (![Toggle off](../../media/scc-toggle-off.png)) and use the **Expires on** box to specify the expiration date for the entries.</span></span>

     <span data-ttu-id="a60ed-139">oder</span><span class="sxs-lookup"><span data-stu-id="a60ed-139">or</span></span>

     - <span data-ttu-id="a60ed-140">Verschieben Sie den Umschalter nach rechts, um die Einträge so zu konfigurieren, dass sie nie ablaufen:</span><span class="sxs-lookup"><span data-stu-id="a60ed-140">Move the toggle to the right to configure the entries to never expire:</span></span> ![Umschaltfläche ein](../../media/scc-toggle-on.png)<span data-ttu-id="a60ed-142">.</span><span class="sxs-lookup"><span data-stu-id="a60ed-142">.</span></span>

   - <span data-ttu-id="a60ed-143">**Optionaler Hinweis:** Geben Sie beschreibenden Text für die Einträge ein.</span><span class="sxs-lookup"><span data-stu-id="a60ed-143">**Optional note**: Enter descriptive text for the entries.</span></span>

4. <span data-ttu-id="a60ed-144">Klicken Sie nach Abschluss des Abschlusses auf **"Hinzufügen".**</span><span class="sxs-lookup"><span data-stu-id="a60ed-144">When you're finished, click **Add**.</span></span>

## <a name="use-the-security--compliance-center-to-view-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="a60ed-145">Verwenden des Security & Compliance Center zum Anzeigen von Einträgen in der Liste der zulässigen/blockierten Mandanten</span><span class="sxs-lookup"><span data-stu-id="a60ed-145">Use the Security & Compliance Center to view entries in the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="a60ed-146">Wechseln Sie im Security & Compliance  Center zu "Richtlinienrichtlinien-Mandanten-Allow/Block \>  \> **Lists".**</span><span class="sxs-lookup"><span data-stu-id="a60ed-146">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="a60ed-147">Wählen Sie die **Registerkarte "URLs"** aus.</span><span class="sxs-lookup"><span data-stu-id="a60ed-147">Select the **URLs** tab.</span></span>

<span data-ttu-id="a60ed-148">Klicken Sie auf die folgenden Spaltenüberschriften, um in aufsteigender oder absteigender Reihenfolge zu sortieren:</span><span class="sxs-lookup"><span data-stu-id="a60ed-148">Click on the following column headings to sort in ascending or descending order:</span></span>

- <span data-ttu-id="a60ed-149">**Wert**</span><span class="sxs-lookup"><span data-stu-id="a60ed-149">**Value**</span></span>
- <span data-ttu-id="a60ed-150">**Aktion:** **Blockieren oder** **Zulassen**.</span><span class="sxs-lookup"><span data-stu-id="a60ed-150">**Action**: **Block** or **Allow**.</span></span>
- <span data-ttu-id="a60ed-151">**Datum der letzten Aktualisierung**</span><span class="sxs-lookup"><span data-stu-id="a60ed-151">**Last updated date**</span></span>
- <span data-ttu-id="a60ed-152">**Ablaufdatum**</span><span class="sxs-lookup"><span data-stu-id="a60ed-152">**Expiration date**</span></span>
- <span data-ttu-id="a60ed-153">**Hinweis**</span><span class="sxs-lookup"><span data-stu-id="a60ed-153">**Note**</span></span>

<span data-ttu-id="a60ed-154">Klicken **Sie auf "Gruppieren",** um die Einträge nach **Aktion** (**Blockieren** oder **Zulassen)** oder Keine **zu gruppieren.**</span><span class="sxs-lookup"><span data-stu-id="a60ed-154">Click **Group** to group the entries by **Action** (**Block** or **Allow**) or **None**.</span></span>

<span data-ttu-id="a60ed-155">Klicken **Sie auf "Suchen",** geben Sie einen Wert ganz oder teilweise ein, und drücken Sie dann die EINGABETASTE, um einen bestimmten Wert zu finden.</span><span class="sxs-lookup"><span data-stu-id="a60ed-155">Click **Search**, enter all or part of a value, and then press ENTER to find a specific value.</span></span> <span data-ttu-id="a60ed-156">Klicken Sie nach Abschluss des Abschlusses auf "Suche **löschen",** ![ um das Suchsymbol zu ](../../media/b6512677-5e7b-42b0-a8a3-3be1d7fa23ee.gif) löschen.</span><span class="sxs-lookup"><span data-stu-id="a60ed-156">When you're finished, click **Clear search** ![Clear search icon](../../media/b6512677-5e7b-42b0-a8a3-3be1d7fa23ee.gif).</span></span>

<span data-ttu-id="a60ed-157">Klicken Sie **auf Filter**.</span><span class="sxs-lookup"><span data-stu-id="a60ed-157">Click **Filter**.</span></span> <span data-ttu-id="a60ed-158">Konfigurieren Sie **im angezeigten** Filterf flyout eine der folgenden Einstellungen:</span><span class="sxs-lookup"><span data-stu-id="a60ed-158">In the **Filter** flyout that appears, configure any of the following settings:</span></span>

- <span data-ttu-id="a60ed-159">**Aktion:** Wählen Sie **"Zulassen",** **"Blockieren"** oder beides aus.</span><span class="sxs-lookup"><span data-stu-id="a60ed-159">**Action**: Select **Allow**, **Block** or both.</span></span>

- <span data-ttu-id="a60ed-160">**Nie ablaufen:** Auswählen aus: ![ Umschalten ](../../media/scc-toggle-off.png) aus oder ein: ![ Umschalten ein ](../../media/scc-toggle-on.png) .</span><span class="sxs-lookup"><span data-stu-id="a60ed-160">**Never expire**: Select off: ![Toggle off](../../media/scc-toggle-off.png) or on: ![Toggle on](../../media/scc-toggle-on.png).</span></span>

- <span data-ttu-id="a60ed-161">**Last updated**: Select a start date (**From**), an end date (**To**) or both.</span><span class="sxs-lookup"><span data-stu-id="a60ed-161">**Last updated**: Select a start date (**From**), an end date (**To**) or both.</span></span>

- <span data-ttu-id="a60ed-162">**Ablaufdatum:** Wählen Sie ein Startdatum (**Von**), ein Enddatum (**bis**) oder beides aus.</span><span class="sxs-lookup"><span data-stu-id="a60ed-162">**Expiration date**: Select a start date (**From**), an end date (**To**) or both.</span></span>

<span data-ttu-id="a60ed-163">Klicken Sie nach Abschluss des Abschlusses auf **"Übernehmen".**</span><span class="sxs-lookup"><span data-stu-id="a60ed-163">When you're finished, click **Apply**.</span></span>

<span data-ttu-id="a60ed-164">Klicken Sie auf **"Filter",** und klicken Sie im angezeigten **Flyout "Filter"** auf "Filter löschen", um vorhandene **Filter zu löschen.**</span><span class="sxs-lookup"><span data-stu-id="a60ed-164">To clear existing filters, click **Filter**, and in the **Filter** flyout that appears, click **Clear filters**.</span></span>

## <a name="use-the-security--compliance-center-to-modify-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="a60ed-165">Verwenden des Security & Compliance Center zum Ändern von Einträgen in der Liste der zulässigen/blockierten Mandanten</span><span class="sxs-lookup"><span data-stu-id="a60ed-165">Use the Security & Compliance Center to modify entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="a60ed-166">Sie können den URL-Wert selbst nicht ändern.</span><span class="sxs-lookup"><span data-stu-id="a60ed-166">You can't modify the URL value itself.</span></span> <span data-ttu-id="a60ed-167">Stattdessen müssen Sie den Eintrag löschen und neu erstellen.</span><span class="sxs-lookup"><span data-stu-id="a60ed-167">Instead, you need to delete the entry and recreate it.</span></span>

1. <span data-ttu-id="a60ed-168">Wechseln Sie im Security & Compliance  Center zu "Richtlinienrichtlinien-Mandanten-Allow/Block \>  \> **Lists".**</span><span class="sxs-lookup"><span data-stu-id="a60ed-168">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="a60ed-169">Wählen Sie die **Registerkarte "URLs"** aus.</span><span class="sxs-lookup"><span data-stu-id="a60ed-169">Select the **URLs** tab.</span></span>

3. <span data-ttu-id="a60ed-170">Wählen Sie den Eintrag aus, den Sie ändern möchten, und klicken Sie dann auf **das** ![ Symbol "Bearbeiten". ](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png)</span><span class="sxs-lookup"><span data-stu-id="a60ed-170">Select the entry that you want to modify, and then click **Edit** ![Edit icon](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png).</span></span>

4. <span data-ttu-id="a60ed-171">Konfigurieren Sie im angezeigten Flyout die folgenden Einstellungen:</span><span class="sxs-lookup"><span data-stu-id="a60ed-171">In the flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="a60ed-172">**Block/Allow**: Select **Allow** or **Block**.</span><span class="sxs-lookup"><span data-stu-id="a60ed-172">**Block/Allow**: Select **Allow** or **Block**.</span></span>

   - <span data-ttu-id="a60ed-173">**Läuft nie** ab: Gehen Sie wie folgt vor:</span><span class="sxs-lookup"><span data-stu-id="a60ed-173">**Never expire**: Do one of the following steps:</span></span>

     - <span data-ttu-id="a60ed-174">Stellen Sie sicher, dass die Einstellung deaktiviert ist (Umschalten aus), und verwenden Sie das Feld "Abläuft bei", um das ![ ](../../media/scc-toggle-off.png) Ablaufdatum für den Eintrag anzugeben. </span><span class="sxs-lookup"><span data-stu-id="a60ed-174">Verify the setting is turned off (![Toggle off](../../media/scc-toggle-off.png)) and use the **Expires on** box to specify the expiration date for the entry.</span></span>

     <span data-ttu-id="a60ed-175">oder</span><span class="sxs-lookup"><span data-stu-id="a60ed-175">or</span></span>

     - <span data-ttu-id="a60ed-176">Verschieben Sie den Umschalter nach rechts, um den Eintrag so zu konfigurieren, dass er nie abläuft:</span><span class="sxs-lookup"><span data-stu-id="a60ed-176">Move the toggle to the right to configure the entry to never expire:</span></span> ![Umschaltfläche ein](../../media/scc-toggle-on.png)<span data-ttu-id="a60ed-178">.</span><span class="sxs-lookup"><span data-stu-id="a60ed-178">.</span></span>

   - <span data-ttu-id="a60ed-179">**Optionaler Hinweis:** Geben Sie einen beschreibenden Text für den Eintrag ein.</span><span class="sxs-lookup"><span data-stu-id="a60ed-179">**Optional note**: Enter descriptive text for the entry.</span></span>

5. <span data-ttu-id="a60ed-180">Klicken Sie nach Abschluss des Vorgangs auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="a60ed-180">When you're finished, click **Save**.</span></span>

## <a name="use-the-security--compliance-center-to-remove-entries-from-the-tenant-allowblock-list"></a><span data-ttu-id="a60ed-181">Verwenden des Security & Compliance Center zum Entfernen von Einträgen aus der Liste der zulässigen/blockierten Mandanten</span><span class="sxs-lookup"><span data-stu-id="a60ed-181">Use the Security & Compliance Center to remove entries from the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="a60ed-182">Wechseln Sie im Security & Compliance  Center zu "Richtlinienrichtlinien-Mandanten-Allow/Block \>  \> **Lists".**</span><span class="sxs-lookup"><span data-stu-id="a60ed-182">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="a60ed-183">Wählen Sie die **Registerkarte "URLs"** aus.</span><span class="sxs-lookup"><span data-stu-id="a60ed-183">Select the **URLs** tab.</span></span>

3. <span data-ttu-id="a60ed-184">Wählen Sie den Eintrag aus, den Sie entfernen möchten, und klicken Sie dann auf **das** Symbol ![ "Löschen". ](../../media/87565fbb-5147-4f22-9ed7-1c18ce664392.png)</span><span class="sxs-lookup"><span data-stu-id="a60ed-184">Select the entry that you want to remove, and then click **Delete** ![Delete icon](../../media/87565fbb-5147-4f22-9ed7-1c18ce664392.png).</span></span>

4. <span data-ttu-id="a60ed-185">Klicken Sie im angezeigten Warnungsdialogfeld auf **"Löschen".**</span><span class="sxs-lookup"><span data-stu-id="a60ed-185">In the warning dialog that appears, click **Delete**.</span></span>

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-the-tenant-allowblock-list"></a><span data-ttu-id="a60ed-186">Verwenden von Exchange Online PowerShell oder der eigenständigen EOP PowerShell zum Konfigurieren der Liste zulässiger/blockierter Mandanten</span><span class="sxs-lookup"><span data-stu-id="a60ed-186">Use Exchange Online PowerShell or standalone EOP PowerShell to configure the Tenant Allow/Block List</span></span>

### <a name="use-powershell-to-add-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="a60ed-187">Verwenden von PowerShell zum Hinzufügen von Einträgen in der Liste der zulässigen/blockierten Mandanten</span><span class="sxs-lookup"><span data-stu-id="a60ed-187">Use PowerShell to add entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="a60ed-188">Verwenden Sie die folgende Syntax, um Einträge in der Liste der zulässigen/blockierten Mandanten hinzuzufügen:</span><span class="sxs-lookup"><span data-stu-id="a60ed-188">To add entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
New-TenantAllowBlockListItems -ListType Url -Action <Allow | Block> -Entries <String[]> [-ExpirationDate <DateTime>] [-NoExpiration] [-Notes <String>]
```

<span data-ttu-id="a60ed-189">In diesem Beispiel wird für contoso.com und alle Unterdomänen (z. B. contoso.com, www.contoso.com und xyz.abc.contoso.com) ein Urlblockeintrag hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="a60ed-189">This example adds a URL block entry for contoso.com and all subdomains (for example, contoso.com, www.contoso.com, and xyz.abc.contoso.com).</span></span> <span data-ttu-id="a60ed-190">Da wir die Parameter "ExpirationDate" oder "NoExpiration" nicht verwendet haben, läuft der Eintrag nach 30 Tagen ab.</span><span class="sxs-lookup"><span data-stu-id="a60ed-190">Because we didn't use the ExpirationDate or NoExpiration parameters, the entry expires after 30 days.</span></span>

```powershell
New-TenantAllowBlockListItem -ListType Url -Action Block -Entries ~contoso.com
```

<span data-ttu-id="a60ed-191">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [New-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/new-tenantallowblocklistitems).</span><span class="sxs-lookup"><span data-stu-id="a60ed-191">For detailed syntax and parameter information, see [New-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/new-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-view-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="a60ed-192">Verwenden von PowerShell zum Anzeigen von Einträgen in der Liste der zulässigen/blockierten Mandanten</span><span class="sxs-lookup"><span data-stu-id="a60ed-192">Use PowerShell to view entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="a60ed-193">Verwenden Sie die folgende Syntax, um Einträge in der Liste der zulässigen/blockierten Mandanten anzeigen zu können:</span><span class="sxs-lookup"><span data-stu-id="a60ed-193">To view entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType Url [-Entry <URLValue>] [-Action <Allow | Block>] [-ExpirationDate <DateTime>] [-NoExpiration]
```

<span data-ttu-id="a60ed-194">In diesem Beispiel werden alle blockierten URLs zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="a60ed-194">This example returns all blocked URLs.</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType Url -Action Block
```

<span data-ttu-id="a60ed-195">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Get-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/get-tenantallowblocklistitems).</span><span class="sxs-lookup"><span data-stu-id="a60ed-195">For detailed syntax and parameter information, see [Get-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/get-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-modify-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="a60ed-196">Verwenden von PowerShell zum Ändern von Einträgen in der Liste der zulässigen/blockierten Mandanten</span><span class="sxs-lookup"><span data-stu-id="a60ed-196">Use PowerShell to modify entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="a60ed-197">Sie können den URL-Wert selbst nicht ändern.</span><span class="sxs-lookup"><span data-stu-id="a60ed-197">You can't modify the URL value itself.</span></span> <span data-ttu-id="a60ed-198">Stattdessen müssen Sie den Eintrag löschen und neu erstellen.</span><span class="sxs-lookup"><span data-stu-id="a60ed-198">Instead, you need to delete the entry and recreate it.</span></span>

<span data-ttu-id="a60ed-199">Verwenden Sie die folgende Syntax, um Einträge in der Liste der zulässigen/blockierten Mandanten zu ändern:</span><span class="sxs-lookup"><span data-stu-id="a60ed-199">To modify entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Set-TenantAllowBlockListItems -ListType Url -Ids <"Id1","Id2",..."IdN"> [-Action <Allow | Block>] [-ExpirationDate <DateTime>] [-NoExpiration] [-Notes <String>]
```

<span data-ttu-id="a60ed-200">In diesem Beispiel wird das Ablaufdatum des angegebenen Eintrags geändert.</span><span class="sxs-lookup"><span data-stu-id="a60ed-200">This example changes the expiration date of the specified entry.</span></span>

```powershell
Set-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSRAAAA" -ExpirationDate (Get-Date "5/30/2020 9:30 AM").ToUniversalTime()
```

<span data-ttu-id="a60ed-201">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Set-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/set-tenantallowblocklistitems).</span><span class="sxs-lookup"><span data-stu-id="a60ed-201">For detailed syntax and parameter information, see [Set-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/set-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-remove-entries-from-the-tenant-allowblock-list"></a><span data-ttu-id="a60ed-202">Verwenden von PowerShell zum Entfernen von Einträgen aus der Liste der zulässigen/blockierten Mandanten</span><span class="sxs-lookup"><span data-stu-id="a60ed-202">Use PowerShell to remove entries from the Tenant Allow/Block List</span></span>

<span data-ttu-id="a60ed-203">Verwenden Sie die folgende Syntax, um Einträge aus der Liste der zulässigen/blockierten Mandanten zu entfernen:</span><span class="sxs-lookup"><span data-stu-id="a60ed-203">To remove entries from the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Remove-TenantAllowBlockListItems -ListType Url -Ids <"Id1","Id2",..."IdN">
```

<span data-ttu-id="a60ed-204">In diesem Beispiel wird der angegebene URL-Eintrag aus der Liste der zulässigen/blockierten Mandanten entfernt.</span><span class="sxs-lookup"><span data-stu-id="a60ed-204">This example removes the specified URL entry from the Tenant Allow/Block List.</span></span>

```powershell
Remove-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSPAAAA0"
```

<span data-ttu-id="a60ed-205">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Remove-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/remove-tenantallowblocklistitems).</span><span class="sxs-lookup"><span data-stu-id="a60ed-205">For detailed syntax and parameter information, see [Remove-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/remove-tenantallowblocklistitems).</span></span>

## <a name="url-syntax-for-the-tenant-allowblock-list"></a><span data-ttu-id="a60ed-206">#A0 für die Liste der zulässigen/blockierten Mandanten</span><span class="sxs-lookup"><span data-stu-id="a60ed-206">URL syntax for the Tenant Allow/Block List</span></span>

- <span data-ttu-id="a60ed-207">IP4v- und IPv6-Adressen sind zulässig, TCP/UDP-Ports jedoch nicht.</span><span class="sxs-lookup"><span data-stu-id="a60ed-207">IP4v and IPv6 addresses are allowed, but TCP/UDP ports are not.</span></span>

- <span data-ttu-id="a60ed-208">Dateinamenerweiterungen sind nicht zulässig (z. B. test.pdf).</span><span class="sxs-lookup"><span data-stu-id="a60ed-208">Filename extensions are not allowed (for example, test.pdf).</span></span>

- <span data-ttu-id="a60ed-209">Unicode wird nicht unterstützt, Punycode jedoch.</span><span class="sxs-lookup"><span data-stu-id="a60ed-209">Unicode is not supported, but Punycode is.</span></span>

- <span data-ttu-id="a60ed-210">Hostnamen sind zulässig, wenn alle folgenden Anweisungen wahr sind:</span><span class="sxs-lookup"><span data-stu-id="a60ed-210">Hostnames are allowed if all of the following statements are true:</span></span>

  - <span data-ttu-id="a60ed-211">Der Hostname enthält einen Zeitraum.</span><span class="sxs-lookup"><span data-stu-id="a60ed-211">The hostname contains a period.</span></span>
  - <span data-ttu-id="a60ed-212">Links vom Zeitraum befindet sich mindestens ein Zeichen.</span><span class="sxs-lookup"><span data-stu-id="a60ed-212">There is at least one character to the left of the period.</span></span>
  - <span data-ttu-id="a60ed-213">Rechts neben dem Zeitraum befinden sich mindestens zwei Zeichen.</span><span class="sxs-lookup"><span data-stu-id="a60ed-213">There are at least two characters to the right of the period.</span></span>

  <span data-ttu-id="a60ed-214">Beispielsweise ist `t.co` dies zulässig oder `.com` nicht `contoso.` zulässig.</span><span class="sxs-lookup"><span data-stu-id="a60ed-214">For example, `t.co` is allowed; `.com` or `contoso.` are not allowed.</span></span>

- <span data-ttu-id="a60ed-215">Unterpfade werden nicht impliziert.</span><span class="sxs-lookup"><span data-stu-id="a60ed-215">Subpaths are not implied.</span></span>

  <span data-ttu-id="a60ed-216">Enthält z. `contoso.com` B. nicht `contoso.com/a` .</span><span class="sxs-lookup"><span data-stu-id="a60ed-216">For example, `contoso.com` does not include `contoso.com/a`.</span></span>

- <span data-ttu-id="a60ed-217">Platzhalter (\*) sind in den folgenden Szenarien zulässig:</span><span class="sxs-lookup"><span data-stu-id="a60ed-217">Wildcards (\*) are allowed in the following scenarios:</span></span>

  - <span data-ttu-id="a60ed-218">Auf einen linken Platzhalter muss ein Zeitraum folgen, um eine Unterdomäne anzugeben.</span><span class="sxs-lookup"><span data-stu-id="a60ed-218">A left wildcard must be followed by a period to specify a subdomain.</span></span>

    <span data-ttu-id="a60ed-219">Ist z. `*.contoso.com` B. zulässig; `*contoso.com` ist nicht zulässig.</span><span class="sxs-lookup"><span data-stu-id="a60ed-219">For example, `*.contoso.com` is allowed; `*contoso.com` is not allowed.</span></span>

  - <span data-ttu-id="a60ed-220">Ein rechter Platzhalter muss einem Schrägstrich (/) folgen, um einen Pfad anzugeben.</span><span class="sxs-lookup"><span data-stu-id="a60ed-220">A right wildcard must follow a forward slash (/) to specify a path.</span></span>

    <span data-ttu-id="a60ed-221">Beispielsweise ist `contoso.com/*` dies zulässig oder `contoso.com*` nicht `contoso.com/ab*` zulässig.</span><span class="sxs-lookup"><span data-stu-id="a60ed-221">For example, `contoso.com/*` is allowed; `contoso.com*` or `contoso.com/ab*` are not allowed.</span></span>

  - <span data-ttu-id="a60ed-222">Alle Unterpfade werden nicht durch einen rechten Platzhalter impliziert.</span><span class="sxs-lookup"><span data-stu-id="a60ed-222">All subpaths are not implied by a right wildcard.</span></span>

    <span data-ttu-id="a60ed-223">Enthält z. `contoso.com/*` B. nicht `contoso.com/a` .</span><span class="sxs-lookup"><span data-stu-id="a60ed-223">For example, `contoso.com/*` does not include `contoso.com/a`.</span></span>

  - <span data-ttu-id="a60ed-224">`*.com*` ungültig ist (keine auflösbare Domäne, und der rechte Platzhalter folgt keinem Schrägstrich).</span><span class="sxs-lookup"><span data-stu-id="a60ed-224">`*.com*` is invalid (not a resolvable domain and the right wildcard does not follow a forward slash).</span></span>

  - <span data-ttu-id="a60ed-225">Platzhalter sind in IP-Adressen nicht zulässig.</span><span class="sxs-lookup"><span data-stu-id="a60ed-225">Wildcards are not allowed in IP addresses.</span></span>

- <span data-ttu-id="a60ed-226">Das Tildezeichen (~) ist in den folgenden Szenarien verfügbar:</span><span class="sxs-lookup"><span data-stu-id="a60ed-226">The tilde (~) character is available in the following scenarios:</span></span>

  - <span data-ttu-id="a60ed-227">Eine linke Tilde impliziert eine Domäne und alle Unterdomänen.</span><span class="sxs-lookup"><span data-stu-id="a60ed-227">A left tilde implies a domain and all subdomains.</span></span>

    <span data-ttu-id="a60ed-228">Beispielsweise enthält `~contoso.com` `contoso.com` und `*.contoso.com` .</span><span class="sxs-lookup"><span data-stu-id="a60ed-228">For example `~contoso.com` includes `contoso.com` and `*.contoso.com`.</span></span>

- <span data-ttu-id="a60ed-229">BEI URL-Einträgen, die Protokolle (z. B. , oder ) enthalten, kann ein Fehler angezeigt werden, da die Urleinträge `http://` `https://` für alle Protokolle `ftp://` gelten.</span><span class="sxs-lookup"><span data-stu-id="a60ed-229">URL entries that contain protocols (for example, `http://`, `https://`, or `ftp://`) will fail, because URL entries apply to all protocols.</span></span>

- <span data-ttu-id="a60ed-230">Ein Benutzername oder Kennwort wird nicht unterstützt oder ist nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="a60ed-230">A username or password aren't supported or required.</span></span>

- <span data-ttu-id="a60ed-231">Anführungszeichen (' oder ") sind ungültige Zeichen.</span><span class="sxs-lookup"><span data-stu-id="a60ed-231">Quotes (' or ") are invalid characters.</span></span>

- <span data-ttu-id="a60ed-232">Eine URL sollte nach Möglichkeit alle Umleitungen enthalten.</span><span class="sxs-lookup"><span data-stu-id="a60ed-232">A URL should include all redirects where possible.</span></span>

### <a name="url-entry-scenarios"></a><span data-ttu-id="a60ed-233">Szenarien für die EINGABE VON URLs</span><span class="sxs-lookup"><span data-stu-id="a60ed-233">URL entry scenarios</span></span>

<span data-ttu-id="a60ed-234">Gültige URL-Einträge und deren Ergebnisse werden in den folgenden Abschnitten beschrieben.</span><span class="sxs-lookup"><span data-stu-id="a60ed-234">Valid URL entries and their results are described in the following sections.</span></span>

#### <a name="scenario-no-wildcards"></a><span data-ttu-id="a60ed-235">Szenario: Keine Platzhalter</span><span class="sxs-lookup"><span data-stu-id="a60ed-235">Scenario: No wildcards</span></span>

<span data-ttu-id="a60ed-236">**Eintrag:**`contoso.com`</span><span class="sxs-lookup"><span data-stu-id="a60ed-236">**Entry**: `contoso.com`</span></span>

- <span data-ttu-id="a60ed-237">**Übereinstimmung zulassen:** contoso.com</span><span class="sxs-lookup"><span data-stu-id="a60ed-237">**Allow match**: contoso.com</span></span>

- <span data-ttu-id="a60ed-238">**Nicht übereinstimmend zulassen:**</span><span class="sxs-lookup"><span data-stu-id="a60ed-238">**Allow not matched**:</span></span>

  - <span data-ttu-id="a60ed-239">abc-contoso.com</span><span class="sxs-lookup"><span data-stu-id="a60ed-239">abc-contoso.com</span></span>
  - <span data-ttu-id="a60ed-240">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="a60ed-240">contoso.com/a</span></span>
  - <span data-ttu-id="a60ed-241">payroll.contoso.com</span><span class="sxs-lookup"><span data-stu-id="a60ed-241">payroll.contoso.com</span></span>
  - <span data-ttu-id="a60ed-242">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="a60ed-242">test.com/contoso.com</span></span>
  - <span data-ttu-id="a60ed-243">test.com/q=contoso.com</span><span class="sxs-lookup"><span data-stu-id="a60ed-243">test.com/q=contoso.com</span></span>
  - <span data-ttu-id="a60ed-244">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="a60ed-244">www.contoso.com</span></span>
  - <span data-ttu-id="a60ed-245">www.contoso.com/q=a@contoso.com</span><span class="sxs-lookup"><span data-stu-id="a60ed-245">www.contoso.com/q=a@contoso.com</span></span>

- <span data-ttu-id="a60ed-246">**Übereinstimmung blockieren:**</span><span class="sxs-lookup"><span data-stu-id="a60ed-246">**Block match**:</span></span>

  - <span data-ttu-id="a60ed-247">contoso.com</span><span class="sxs-lookup"><span data-stu-id="a60ed-247">contoso.com</span></span>
  - <span data-ttu-id="a60ed-248">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="a60ed-248">contoso.com/a</span></span>
  - <span data-ttu-id="a60ed-249">payroll.contoso.com</span><span class="sxs-lookup"><span data-stu-id="a60ed-249">payroll.contoso.com</span></span>
  - <span data-ttu-id="a60ed-250">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="a60ed-250">test.com/contoso.com</span></span>
  - <span data-ttu-id="a60ed-251">test.com/q=contoso.com</span><span class="sxs-lookup"><span data-stu-id="a60ed-251">test.com/q=contoso.com</span></span>
  - <span data-ttu-id="a60ed-252">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="a60ed-252">www.contoso.com</span></span>
  - <span data-ttu-id="a60ed-253">www.contoso.com/q=a@contoso.com</span><span class="sxs-lookup"><span data-stu-id="a60ed-253">www.contoso.com/q=a@contoso.com</span></span>

- <span data-ttu-id="a60ed-254">**Block nicht übereinstimmend:** abc-contoso.com</span><span class="sxs-lookup"><span data-stu-id="a60ed-254">**Block not matched**: abc-contoso.com</span></span>

#### <a name="scenario-left-wildcard-subdomain"></a><span data-ttu-id="a60ed-255">Szenario: Linker Platzhalter (Unterdomäne)</span><span class="sxs-lookup"><span data-stu-id="a60ed-255">Scenario: Left wildcard (subdomain)</span></span>

<span data-ttu-id="a60ed-256">**Eintrag:**`*.contoso.com`</span><span class="sxs-lookup"><span data-stu-id="a60ed-256">**Entry**: `*.contoso.com`</span></span>

- <span data-ttu-id="a60ed-257">**Übereinstimmung zulassen** und **Übereinstimmung blockieren:**</span><span class="sxs-lookup"><span data-stu-id="a60ed-257">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="a60ed-258">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="a60ed-258">www.contoso.com</span></span>
  - <span data-ttu-id="a60ed-259">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="a60ed-259">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="a60ed-260">**Nicht übereinstimmend zulassen und** **Block nicht übereinstimmen:**</span><span class="sxs-lookup"><span data-stu-id="a60ed-260">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="a60ed-261">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="a60ed-261">123contoso.com</span></span>
  - <span data-ttu-id="a60ed-262">contoso.com</span><span class="sxs-lookup"><span data-stu-id="a60ed-262">contoso.com</span></span>
  - <span data-ttu-id="a60ed-263">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="a60ed-263">test.com/contoso.com</span></span>
  - <span data-ttu-id="a60ed-264">www.contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="a60ed-264">www.contoso.com/abc</span></span>

#### <a name="scenario-right-wildcard-at-top-of-path"></a><span data-ttu-id="a60ed-265">Szenario: Rechter Platzhalter oben im Pfad</span><span class="sxs-lookup"><span data-stu-id="a60ed-265">Scenario: Right wildcard at top of path</span></span>

<span data-ttu-id="a60ed-266">**Eintrag:**`contoso.com/a/*`</span><span class="sxs-lookup"><span data-stu-id="a60ed-266">**Entry**: `contoso.com/a/*`</span></span>

- <span data-ttu-id="a60ed-267">**Übereinstimmung zulassen** und **Übereinstimmung blockieren:**</span><span class="sxs-lookup"><span data-stu-id="a60ed-267">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="a60ed-268">contoso.com/a/b</span><span class="sxs-lookup"><span data-stu-id="a60ed-268">contoso.com/a/b</span></span>
  - <span data-ttu-id="a60ed-269">contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="a60ed-269">contoso.com/a/b/c</span></span>
  - <span data-ttu-id="a60ed-270">contoso.com/a/?q=joe@t.com</span><span class="sxs-lookup"><span data-stu-id="a60ed-270">contoso.com/a/?q=joe@t.com</span></span>

- <span data-ttu-id="a60ed-271">**Nicht übereinstimmend zulassen und** **Block nicht übereinstimmen:**</span><span class="sxs-lookup"><span data-stu-id="a60ed-271">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="a60ed-272">contoso.com</span><span class="sxs-lookup"><span data-stu-id="a60ed-272">contoso.com</span></span>
  - <span data-ttu-id="a60ed-273">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="a60ed-273">contoso.com/a</span></span>
  - <span data-ttu-id="a60ed-274">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="a60ed-274">www.contoso.com</span></span>
  - <span data-ttu-id="a60ed-275">www.contoso.com/q=a@contoso.com</span><span class="sxs-lookup"><span data-stu-id="a60ed-275">www.contoso.com/q=a@contoso.com</span></span>

#### <a name="scenario-left-tilde"></a><span data-ttu-id="a60ed-276">Szenario: Left tilde</span><span class="sxs-lookup"><span data-stu-id="a60ed-276">Scenario: Left tilde</span></span>

<span data-ttu-id="a60ed-277">**Eintrag:**`~contoso.com`</span><span class="sxs-lookup"><span data-stu-id="a60ed-277">**Entry**: `~contoso.com`</span></span>

- <span data-ttu-id="a60ed-278">**Übereinstimmung zulassen** und **Übereinstimmung blockieren:**</span><span class="sxs-lookup"><span data-stu-id="a60ed-278">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="a60ed-279">contoso.com</span><span class="sxs-lookup"><span data-stu-id="a60ed-279">contoso.com</span></span>
  - <span data-ttu-id="a60ed-280">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="a60ed-280">www.contoso.com</span></span>
  - <span data-ttu-id="a60ed-281">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="a60ed-281">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="a60ed-282">**Nicht übereinstimmend zulassen und** **Block nicht übereinstimmen:**</span><span class="sxs-lookup"><span data-stu-id="a60ed-282">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="a60ed-283">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="a60ed-283">123contoso.com</span></span>
  - <span data-ttu-id="a60ed-284">contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="a60ed-284">contoso.com/abc</span></span>
  - <span data-ttu-id="a60ed-285">www.contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="a60ed-285">www.contoso.com/abc</span></span>

#### <a name="scenario-right-wildcard-suffix"></a><span data-ttu-id="a60ed-286">Szenario: Rechtes Platzhaltersuffix</span><span class="sxs-lookup"><span data-stu-id="a60ed-286">Scenario: Right wildcard suffix</span></span>

<span data-ttu-id="a60ed-287">**Eintrag:**`contoso.com/*`</span><span class="sxs-lookup"><span data-stu-id="a60ed-287">**Entry**: `contoso.com/*`</span></span>

- <span data-ttu-id="a60ed-288">**Übereinstimmung zulassen** und **Übereinstimmung blockieren:**</span><span class="sxs-lookup"><span data-stu-id="a60ed-288">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="a60ed-289">contoso.com/?q=whatever@fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="a60ed-289">contoso.com/?q=whatever@fabrikam.com</span></span>
  - <span data-ttu-id="a60ed-290">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="a60ed-290">contoso.com/a</span></span>
  - <span data-ttu-id="a60ed-291">contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="a60ed-291">contoso.com/a/b/c</span></span>
  - <span data-ttu-id="a60ed-292">contoso.com/ab</span><span class="sxs-lookup"><span data-stu-id="a60ed-292">contoso.com/ab</span></span>
  - <span data-ttu-id="a60ed-293">contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="a60ed-293">contoso.com/b</span></span>
  - <span data-ttu-id="a60ed-294">contoso.com/b/a/c</span><span class="sxs-lookup"><span data-stu-id="a60ed-294">contoso.com/b/a/c</span></span>
  - <span data-ttu-id="a60ed-295">contoso.com/ba</span><span class="sxs-lookup"><span data-stu-id="a60ed-295">contoso.com/ba</span></span>

- <span data-ttu-id="a60ed-296">**Nicht übereinstimmend zulassen und** **Block nicht übereinstimmen:** contoso.com</span><span class="sxs-lookup"><span data-stu-id="a60ed-296">**Allow not matched** and **Block not matched**: contoso.com</span></span>

#### <a name="scenario-left-wildcard-subdomain-and-right-wildcard-suffix"></a><span data-ttu-id="a60ed-297">Szenario: Linke Platzhalterunterdomäne und rechtes Platzhaltersuffix</span><span class="sxs-lookup"><span data-stu-id="a60ed-297">Scenario: Left wildcard subdomain and right wildcard suffix</span></span>

<span data-ttu-id="a60ed-298">**Eintrag:**`*.contoso.com/*`</span><span class="sxs-lookup"><span data-stu-id="a60ed-298">**Entry**: `*.contoso.com/*`</span></span>

- <span data-ttu-id="a60ed-299">**Übereinstimmung zulassen** und **Übereinstimmung blockieren:**</span><span class="sxs-lookup"><span data-stu-id="a60ed-299">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="a60ed-300">abc.contoso.com/ab</span><span class="sxs-lookup"><span data-stu-id="a60ed-300">abc.contoso.com/ab</span></span>
  - <span data-ttu-id="a60ed-301">abc.xyz.contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="a60ed-301">abc.xyz.contoso.com/a/b/c</span></span>
  - <span data-ttu-id="a60ed-302">www.contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="a60ed-302">www.contoso.com/a</span></span>
  - <span data-ttu-id="a60ed-303">www.contoso.com/b/a/c</span><span class="sxs-lookup"><span data-stu-id="a60ed-303">www.contoso.com/b/a/c</span></span>
  - <span data-ttu-id="a60ed-304">xyz.contoso.com/ba</span><span class="sxs-lookup"><span data-stu-id="a60ed-304">xyz.contoso.com/ba</span></span>

- <span data-ttu-id="a60ed-305">**Nicht übereinstimmend zulassen und** **Block nicht übereinstimmen:** contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="a60ed-305">**Allow not matched** and **Block not matched**: contoso.com/b</span></span>

#### <a name="scenario-left-and-right-tilde"></a><span data-ttu-id="a60ed-306">Szenario: Linke und rechte Tilde</span><span class="sxs-lookup"><span data-stu-id="a60ed-306">Scenario: Left and right tilde</span></span>

<span data-ttu-id="a60ed-307">**Eintrag:**`~contoso.com~`</span><span class="sxs-lookup"><span data-stu-id="a60ed-307">**Entry**: `~contoso.com~`</span></span>

- <span data-ttu-id="a60ed-308">**Übereinstimmung zulassen** und **Übereinstimmung blockieren:**</span><span class="sxs-lookup"><span data-stu-id="a60ed-308">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="a60ed-309">contoso.com</span><span class="sxs-lookup"><span data-stu-id="a60ed-309">contoso.com</span></span>
  - <span data-ttu-id="a60ed-310">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="a60ed-310">contoso.com/a</span></span>
  - <span data-ttu-id="a60ed-311">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="a60ed-311">www.contoso.com</span></span>
  - <span data-ttu-id="a60ed-312">www.contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="a60ed-312">www.contoso.com/b</span></span>
  - <span data-ttu-id="a60ed-313">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="a60ed-313">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="a60ed-314">**Nicht übereinstimmend zulassen und** **Block nicht übereinstimmen:**</span><span class="sxs-lookup"><span data-stu-id="a60ed-314">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="a60ed-315">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="a60ed-315">123contoso.com</span></span>
  - <span data-ttu-id="a60ed-316">contoso.org</span><span class="sxs-lookup"><span data-stu-id="a60ed-316">contoso.org</span></span>

#### <a name="scenario-ip-address"></a><span data-ttu-id="a60ed-317">Szenario: IP-Adresse</span><span class="sxs-lookup"><span data-stu-id="a60ed-317">Scenario: IP address</span></span>

<span data-ttu-id="a60ed-318">**Eintrag:**`1.2.3.4`</span><span class="sxs-lookup"><span data-stu-id="a60ed-318">**Entry**: `1.2.3.4`</span></span>

- <span data-ttu-id="a60ed-319">**Übereinstimmung zulassen** und **Blockierung:** 1.2.3.4</span><span class="sxs-lookup"><span data-stu-id="a60ed-319">**Allow match** and **Block match**: 1.2.3.4</span></span>

- <span data-ttu-id="a60ed-320">**Nicht übereinstimmend zulassen und** **Block nicht übereinstimmen:**</span><span class="sxs-lookup"><span data-stu-id="a60ed-320">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="a60ed-321">1.2.3.4/a</span><span class="sxs-lookup"><span data-stu-id="a60ed-321">1.2.3.4/a</span></span>
  - <span data-ttu-id="a60ed-322">11.2.3.4/a</span><span class="sxs-lookup"><span data-stu-id="a60ed-322">11.2.3.4/a</span></span>

#### <a name="ip-address-with-right-wildcard"></a><span data-ttu-id="a60ed-323">IP-Adresse mit rechtem Platzhalter</span><span class="sxs-lookup"><span data-stu-id="a60ed-323">IP address with right wildcard</span></span>

<span data-ttu-id="a60ed-324">**Eintrag:**`1.2.3.4/*`</span><span class="sxs-lookup"><span data-stu-id="a60ed-324">**Entry**: `1.2.3.4/*`</span></span>

- <span data-ttu-id="a60ed-325">**Übereinstimmung zulassen** und **Übereinstimmung blockieren:**</span><span class="sxs-lookup"><span data-stu-id="a60ed-325">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="a60ed-326">1.2.3.4/b</span><span class="sxs-lookup"><span data-stu-id="a60ed-326">1.2.3.4/b</span></span>
  - <span data-ttu-id="a60ed-327">1.2.3.4/baaaa</span><span class="sxs-lookup"><span data-stu-id="a60ed-327">1.2.3.4/baaaa</span></span>

### <a name="examples-of-invalid-entries"></a><span data-ttu-id="a60ed-328">Beispiele für ungültige Einträge</span><span class="sxs-lookup"><span data-stu-id="a60ed-328">Examples of invalid entries</span></span>

<span data-ttu-id="a60ed-329">Die folgenden Einträge sind ungültig:</span><span class="sxs-lookup"><span data-stu-id="a60ed-329">The following entries are invalid:</span></span>

- <span data-ttu-id="a60ed-330">**Fehlende oder ungültige Domänenwerte:**</span><span class="sxs-lookup"><span data-stu-id="a60ed-330">**Missing or invalid domain values**:</span></span>

  - <span data-ttu-id="a60ed-331">contoso</span><span class="sxs-lookup"><span data-stu-id="a60ed-331">contoso</span></span>
  - <span data-ttu-id="a60ed-332">\*.contoso.\*</span><span class="sxs-lookup"><span data-stu-id="a60ed-332">\*.contoso.\*</span></span>
  - <span data-ttu-id="a60ed-333">\*.com</span><span class="sxs-lookup"><span data-stu-id="a60ed-333">\*.com</span></span>
  - <span data-ttu-id="a60ed-334">\*.pdf</span><span class="sxs-lookup"><span data-stu-id="a60ed-334">\*.pdf</span></span>

- <span data-ttu-id="a60ed-335">**Platzhalter für Text oder ohne Leerzeichen:**</span><span class="sxs-lookup"><span data-stu-id="a60ed-335">**Wildcard on text or without spacing characters**:</span></span>

  - <span data-ttu-id="a60ed-336">\*contoso.com</span><span class="sxs-lookup"><span data-stu-id="a60ed-336">\*contoso.com</span></span>
  - <span data-ttu-id="a60ed-337">contoso.com\*</span><span class="sxs-lookup"><span data-stu-id="a60ed-337">contoso.com\*</span></span>
  - <span data-ttu-id="a60ed-338">\*1.2.3.4</span><span class="sxs-lookup"><span data-stu-id="a60ed-338">\*1.2.3.4</span></span>
  - <span data-ttu-id="a60ed-339">1.2.3.4\*</span><span class="sxs-lookup"><span data-stu-id="a60ed-339">1.2.3.4\*</span></span>
  - <span data-ttu-id="a60ed-340">contoso.com/a\*</span><span class="sxs-lookup"><span data-stu-id="a60ed-340">contoso.com/a\*</span></span>
  - <span data-ttu-id="a60ed-341">contoso.com/ab\*</span><span class="sxs-lookup"><span data-stu-id="a60ed-341">contoso.com/ab\*</span></span>

- <span data-ttu-id="a60ed-342">**IP-Adressen mit Ports:**</span><span class="sxs-lookup"><span data-stu-id="a60ed-342">**IP addresses with ports**:</span></span>

  - <span data-ttu-id="a60ed-343">contoso.com:443</span><span class="sxs-lookup"><span data-stu-id="a60ed-343">contoso.com:443</span></span>
  - <span data-ttu-id="a60ed-344">abc.contoso.com:25</span><span class="sxs-lookup"><span data-stu-id="a60ed-344">abc.contoso.com:25</span></span>

- <span data-ttu-id="a60ed-345">**Nicht beschreibende Platzhalter:**</span><span class="sxs-lookup"><span data-stu-id="a60ed-345">**Non-descriptive wildcards**:</span></span>

  - \*
  - <span data-ttu-id="a60ed-346">\*.\*</span><span class="sxs-lookup"><span data-stu-id="a60ed-346">\*.\*</span></span>

- <span data-ttu-id="a60ed-347">**Mittlere Platzhalter:**</span><span class="sxs-lookup"><span data-stu-id="a60ed-347">**Middle wildcards**:</span></span>

  - <span data-ttu-id="a60ed-348">conto \* so.com</span><span class="sxs-lookup"><span data-stu-id="a60ed-348">conto\*so.com</span></span>
  - <span data-ttu-id="a60ed-349">conto~so.com</span><span class="sxs-lookup"><span data-stu-id="a60ed-349">conto~so.com</span></span>

- <span data-ttu-id="a60ed-350">**Doppelte Platzhalter**</span><span class="sxs-lookup"><span data-stu-id="a60ed-350">**Double wildcards**</span></span>

  - <span data-ttu-id="a60ed-351">contoso.com/\*\*</span><span class="sxs-lookup"><span data-stu-id="a60ed-351">contoso.com/\*\*</span></span>
  - <span data-ttu-id="a60ed-352">contoso.com/\*/\*</span><span class="sxs-lookup"><span data-stu-id="a60ed-352">contoso.com/\*/\*</span></span>
