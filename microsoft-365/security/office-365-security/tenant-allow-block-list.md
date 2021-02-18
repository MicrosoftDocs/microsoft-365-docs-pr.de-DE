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
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: Administratoren können erfahren, wie Sie Dies in der Liste der zulässigen/blockierten Mandanten im Sicherheitsportal konfigurieren.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 250b6223ffe663e0cd950069a3c3c7827b4aa57b
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/18/2021
ms.locfileid: "50290165"
---
# <a name="manage-the-tenant-allowblock-list"></a><span data-ttu-id="b7e65-103">Verwalten der Zulassungs-/Sperrliste des Mandanten</span><span class="sxs-lookup"><span data-stu-id="b7e65-103">Manage the Tenant Allow/Block List</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="b7e65-104">**Gilt für**</span><span class="sxs-lookup"><span data-stu-id="b7e65-104">**Applies to**</span></span>
- [<span data-ttu-id="b7e65-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="b7e65-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="b7e65-106">Microsoft Defender für Office 365 Plan 1 und Plan 2</span><span class="sxs-lookup"><span data-stu-id="b7e65-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="b7e65-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="b7e65-107">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

> [!NOTE]
>
> <span data-ttu-id="b7e65-108">Die in diesem Artikel beschriebenen Features befinden sich in der Vorschau, können geändert werden und sind nicht in allen Organisationen verfügbar.</span><span class="sxs-lookup"><span data-stu-id="b7e65-108">The features described in this article are in Preview, are subject to change, and are not available in all organizations.</span></span>
>
> <span data-ttu-id="b7e65-109">Sie können zu **diesem** Zeitpunkt keine zulässigen Elemente in der Liste zugelassener/blockierter Mandanten konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="b7e65-109">You can't **configure** allowed items in the Tenant Allow/Block List at this time.</span></span>

<span data-ttu-id="b7e65-110">In Microsoft 365-Organisationen mit Postfächern in Exchange Online oder eigenständigen Exchange Online Protection (EOP)-Organisationen ohne Exchange Online-Postfächer sind Sie möglicherweise mit der EOP-Filterungs-Ansicht nicht einverstanden.</span><span class="sxs-lookup"><span data-stu-id="b7e65-110">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, you might disagree with the EOP filtering verdict.</span></span> <span data-ttu-id="b7e65-111">Beispielsweise kann eine gute Nachricht als "schlecht" (ein falsch positives Ergebnis) oder eine ungültige Nachricht als "schlecht" (falsch negativ) markiert werden.</span><span class="sxs-lookup"><span data-stu-id="b7e65-111">For example, a good message might be marked as bad (a false positive), or a bad message might be allowed through (a false negative).</span></span>

<span data-ttu-id="b7e65-112">Die Liste der zulässigen/blockierten Mandanten im Security & Compliance Center bietet Ihnen die Möglichkeit, die Microsoft 365-Filterungsverdingungen manuell außer Kraft zu setzen.</span><span class="sxs-lookup"><span data-stu-id="b7e65-112">The Tenant Allow/Block List in the Security & Compliance Center gives you a way to manually override the Microsoft 365 filtering verdicts.</span></span> <span data-ttu-id="b7e65-113">Die Liste der zulässigen/blockierten Mandanten wird während des Nachrichtenflusses und zum Zeitpunkt der Klicks des Benutzers verwendet.</span><span class="sxs-lookup"><span data-stu-id="b7e65-113">The Tenant Allow/Block List is used during mail flow and at the time of user clicks.</span></span> <span data-ttu-id="b7e65-114">Sie können URLs oder Dateien angeben, die immer blockiert werden.</span><span class="sxs-lookup"><span data-stu-id="b7e65-114">You can specify URLs or files to always block.</span></span>

<span data-ttu-id="b7e65-115">In diesem Artikel wird beschrieben, wie Sie Einträge in der Liste zulässiger/blockierter Mandanten im Security & Compliance Center oder in PowerShell (Exchange Online PowerShell für Microsoft 365-Organisationen mit Postfächern in Exchange Online; eigenständige EOP PowerShell für Organisationen ohne Exchange & ) konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="b7e65-115">This article describes how to configure entries in the Tenant Allow/Block List in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="b7e65-116">Was sollten Sie wissen, bevor Sie beginnen?</span><span class="sxs-lookup"><span data-stu-id="b7e65-116">What do you need to know before you begin?</span></span>

- <span data-ttu-id="b7e65-117">Sie öffnen das Security & Compliance Center unter <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="b7e65-117">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="b7e65-118">Verwenden Sie dies, um direkt zur Seite **"Mandanten-Allow/Block List"** zu <https://protection.office.com/tenantAllowBlockList> wechseln.</span><span class="sxs-lookup"><span data-stu-id="b7e65-118">To go directly to the **Tenant Allow/Block List** page, use <https://protection.office.com/tenantAllowBlockList>.</span></span>

- <span data-ttu-id="b7e65-119">Sie geben Dateien mithilfe des #A0 der Datei an.</span><span class="sxs-lookup"><span data-stu-id="b7e65-119">You specify files by using the SHA256 hash value of the file.</span></span> <span data-ttu-id="b7e65-120">Führen Sie den folgenden Befehl an einer Eingabeaufforderung aus, um den #A0 einer Datei in Windows zu finden:</span><span class="sxs-lookup"><span data-stu-id="b7e65-120">To find the SHA256 hash value of a file in Windows, run the following command in a Command Prompt:</span></span>

  ```dos
  certutil.exe -hashfile "<Path>\<Filename>" SHA256
  ```

  <span data-ttu-id="b7e65-121">Ein Beispielwert ist `768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3a` .</span><span class="sxs-lookup"><span data-stu-id="b7e65-121">An example value is `768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3a`.</span></span> <span data-ttu-id="b7e65-122">Perceptual Hash (pHash)-Werte werden nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="b7e65-122">Perceptual hash (pHash) values are not supported.</span></span>

- <span data-ttu-id="b7e65-123">Die verfügbaren #A0 werden weiter unten in diesem Artikel in der #A1 für den Abschnitt "Mandanten [zulassen/blockieren"](#url-syntax-for-the-tenant-allowblock-list) beschrieben.</span><span class="sxs-lookup"><span data-stu-id="b7e65-123">The available URL values are described in the [URL syntax for the Tenant Allow/Block List](#url-syntax-for-the-tenant-allowblock-list) section later in this article.</span></span>

- <span data-ttu-id="b7e65-124">Die Liste der zulässigen/blockierten Mandanten lässt maximal 500 Einträge für URLs und 500 Einträge für Dateihashes zu.</span><span class="sxs-lookup"><span data-stu-id="b7e65-124">The Tenant Allow/Block List allows a maximum of 500 entries for URLs, and 500 entries for file hashes.</span></span>

- <span data-ttu-id="b7e65-125">Ein Eintrag sollte innerhalb von 15 Minuten aktiv sein.</span><span class="sxs-lookup"><span data-stu-id="b7e65-125">An entry should be active within 15 minutes.</span></span>

- <span data-ttu-id="b7e65-126">Standardmäßig laufen Einträge in der Liste der zulässigen/blockierten Mandanten nach 30 Tagen ab.</span><span class="sxs-lookup"><span data-stu-id="b7e65-126">By default, entries in the Tenant Allow/Block List will expire after 30 days.</span></span> <span data-ttu-id="b7e65-127">Sie können ein Datum angeben oder festlegen, dass es nie abläuft.</span><span class="sxs-lookup"><span data-stu-id="b7e65-127">You can specify a date or set them to never expire.</span></span>

- <span data-ttu-id="b7e65-128">Wie Sie eine Verbindung mit Exchange Online PowerShell herstellen, finden Sie unter [Herstellen einer Verbindung mit Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="b7e65-128">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="b7e65-129">Informationen zum Herstellen einer Verbindung mit dem eigenständigen Exchange Online Protection PowerShell finden Sie unter [Verbinden mit PowerShell in Exchange Online Protection](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="b7e65-129">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="b7e65-130">Bevor Sie die Verfahren in diesem Artikel ausführen können, müssen Ihnen im Security & Compliance Center Berechtigungen zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="b7e65-130">You need to be assigned permissions in the Security & Compliance Center before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="b7e65-131">Zum Hinzufügen und Entfernen von Werten aus der Liste zulässiger/blockierter Mandanten müssen Sie Mitglied der Rollengruppe "Organisationsverwaltung" oder **"Sicherheitsadministrator"** sein. </span><span class="sxs-lookup"><span data-stu-id="b7e65-131">To add and remove values from the Tenant Allow/Block List, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="b7e65-132">Für den schreibgeschützten Zugriff auf die Liste der zulässigen/blockierten Mandanten müssen Sie Mitglied der Rollengruppe "Globaler Leser" oder **"Sicherheitsleseprogramm"** sein. </span><span class="sxs-lookup"><span data-stu-id="b7e65-132">For read-only access to the Tenant Allow/Block List, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="b7e65-133">Weitere Informationen finden Sie unter [Berechtigungen im Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="b7e65-133">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

  <span data-ttu-id="b7e65-134">**Hinweise**:</span><span class="sxs-lookup"><span data-stu-id="b7e65-134">**Notes**:</span></span>

  - <span data-ttu-id="b7e65-135">Durch das Hinzufügen von Benutzern zur entsprechenden Azure Active Directory-Rolle im Microsoft 365 Admin Center erhalten Benutzer die erforderlichen Berechtigungen im Security & Compliance Center _und_ Berechtigungen für andere Features in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="b7e65-135">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Security & Compliance Center _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="b7e65-136">Weitere Informationen finden Sie unter [Informationen zu Administratorrollen](../../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="b7e65-136">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  - <span data-ttu-id="b7e65-137">Die Rollengruppe **Organisationsverwaltung mit Leserechten** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) ermöglicht auch einen schreibgeschützten Zugriff auf das Feature.</span><span class="sxs-lookup"><span data-stu-id="b7e65-137">The **View-Only Organization Management** role group in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

## <a name="use-the-security--compliance-center-to-create-url-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="b7e65-138">Verwenden des Security & Compliance Center zum Erstellen von URL-Einträgen in der Liste der zulässigen/blockierten Mandanten</span><span class="sxs-lookup"><span data-stu-id="b7e65-138">Use the Security & Compliance Center to create URL entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="b7e65-139">Weitere Informationen zur Syntax für #A0 finden Sie in der #A1 für den Abschnitt ["Mandanten-Zulassen/Blockieren-Liste"](#url-syntax-for-the-tenant-allowblock-list) weiter unten in diesem Artikel.</span><span class="sxs-lookup"><span data-stu-id="b7e65-139">For details about the syntax for URL entries, see the [URL syntax for the Tenant Allow/Block List](#url-syntax-for-the-tenant-allowblock-list) section later in this article.</span></span>

1. <span data-ttu-id="b7e65-140">Wechseln Sie im Security & Compliance  Center zu "Richtlinienrichtlinien-Mandanten-Allow/Block \>  \> **Lists".**</span><span class="sxs-lookup"><span data-stu-id="b7e65-140">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="b7e65-141">Überprüfen Sie auf der Seite "Mandanten-Allow/Block **List",** ob die Registerkarte **"URLs"** ausgewählt ist, und klicken Sie dann auf **"Blockieren".**</span><span class="sxs-lookup"><span data-stu-id="b7e65-141">On the **Tenant Allow/Block List** page, verify that the **URLs** tab is selected, and then click **Block**</span></span>

3. <span data-ttu-id="b7e65-142">Konfigurieren Sie im angezeigten Flyout **"URLs** blockieren" die folgenden Einstellungen:</span><span class="sxs-lookup"><span data-stu-id="b7e65-142">In the **Block URLs** flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="b7e65-143">**Zu blockierende URLs hinzufügen:** Geben Sie eine URL pro Zeile ein, bis zu maximal 20.</span><span class="sxs-lookup"><span data-stu-id="b7e65-143">**Add URLs to block**: Enter one URL per line, up to a maximum of 20.</span></span>

   - <span data-ttu-id="b7e65-144">**Läuft nie** ab: Gehen Sie wie folgt vor:</span><span class="sxs-lookup"><span data-stu-id="b7e65-144">**Never expire**: Do one of the following steps:</span></span>

     - <span data-ttu-id="b7e65-145">Stellen Sie sicher, dass die Einstellung deaktiviert ist (Umschalten aus), und verwenden Sie das Feld "Abläuft bei", um das Ablaufdatum ![ ](../../media/scc-toggle-off.png) für die Einträge anzugeben. </span><span class="sxs-lookup"><span data-stu-id="b7e65-145">Verify the setting is turned off (![Toggle off](../../media/scc-toggle-off.png)) and use the **Expires on** box to specify the expiration date for the entries.</span></span>

     <span data-ttu-id="b7e65-146">oder</span><span class="sxs-lookup"><span data-stu-id="b7e65-146">or</span></span>

     - <span data-ttu-id="b7e65-147">Verschieben Sie den Umschalter nach rechts, um die Einträge so zu konfigurieren, dass sie nie ablaufen:</span><span class="sxs-lookup"><span data-stu-id="b7e65-147">Move the toggle to the right to configure the entries to never expire:</span></span> ![Umschaltfläche ein](../../media/scc-toggle-on.png)<span data-ttu-id="b7e65-149">.</span><span class="sxs-lookup"><span data-stu-id="b7e65-149">.</span></span>

   - <span data-ttu-id="b7e65-150">**Optionaler Hinweis:** Geben Sie beschreibenden Text für die Einträge ein.</span><span class="sxs-lookup"><span data-stu-id="b7e65-150">**Optional note**: Enter descriptive text for the entries.</span></span>

4. <span data-ttu-id="b7e65-151">Klicken Sie nach Abschluss des Vorgangs auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="b7e65-151">When you're finished, click **Add**.</span></span>

## <a name="use-the-security--compliance-center-to-create-file-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="b7e65-152">Verwenden des Security & Compliance Center zum Erstellen von Dateieinträgen in der Liste der zulässigen/blockierten Mandanten</span><span class="sxs-lookup"><span data-stu-id="b7e65-152">Use the Security & Compliance Center to create file entries in the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="b7e65-153">Wechseln Sie im Security & Compliance  Center zu "Richtlinienrichtlinien-Mandanten-Allow/Block \>  \> **Lists".**</span><span class="sxs-lookup"><span data-stu-id="b7e65-153">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="b7e65-154">Wählen Sie **auf der Seite "Mandanten zulassen/blockieren"** die Registerkarte **"Dateien"** aus, und klicken Sie dann auf **"Blockieren".**</span><span class="sxs-lookup"><span data-stu-id="b7e65-154">On the **Tenant Allow/Block List** page, select **Files** tab, and then click **Block**.</span></span>

3. <span data-ttu-id="b7e65-155">Konfigurieren Sie **in den angezeigten Dateien zum Blockieren** des angezeigten Flyouts die folgenden Einstellungen:</span><span class="sxs-lookup"><span data-stu-id="b7e65-155">In the **Add files to block** flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="b7e65-156">**Hinzufügen von Dateihashes:** Geben Sie einen #A0 pro Zeile ein, bis zu maximal 20.</span><span class="sxs-lookup"><span data-stu-id="b7e65-156">**Add file hashes**: Enter one SHA256 hash value per line, up to a maximum of 20.</span></span>

   - <span data-ttu-id="b7e65-157">**Läuft nie** ab: Gehen Sie wie folgt vor:</span><span class="sxs-lookup"><span data-stu-id="b7e65-157">**Never expire**: Do one of the following steps:</span></span>

     - <span data-ttu-id="b7e65-158">Stellen Sie sicher, dass die Einstellung deaktiviert ist (Umschalten aus), und verwenden Sie das Feld "Abläuft bei", um das Ablaufdatum ![ ](../../media/scc-toggle-off.png) für die Einträge anzugeben. </span><span class="sxs-lookup"><span data-stu-id="b7e65-158">Verify the setting is turned off (![Toggle off](../../media/scc-toggle-off.png)) and use the **Expires on** box to specify the expiration date for the entries.</span></span>

     <span data-ttu-id="b7e65-159">oder</span><span class="sxs-lookup"><span data-stu-id="b7e65-159">or</span></span>

     - <span data-ttu-id="b7e65-160">Verschieben Sie den Umschalter nach rechts, um die Einträge so zu konfigurieren, dass sie nie ablaufen:</span><span class="sxs-lookup"><span data-stu-id="b7e65-160">Move the toggle to the right to configure the entries to never expire:</span></span> ![Umschaltfläche ein](../../media/scc-toggle-on.png)<span data-ttu-id="b7e65-162">.</span><span class="sxs-lookup"><span data-stu-id="b7e65-162">.</span></span>

   - <span data-ttu-id="b7e65-163">**Optionaler Hinweis:** Geben Sie beschreibenden Text für die Einträge ein.</span><span class="sxs-lookup"><span data-stu-id="b7e65-163">**Optional note**: Enter descriptive text for the entries.</span></span>

4. <span data-ttu-id="b7e65-164">Klicken Sie nach Abschluss des Vorgangs auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="b7e65-164">When you're finished, click **Add**.</span></span>

## <a name="use-the-security--compliance-center-to-view-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="b7e65-165">Verwenden des Security & Compliance Center zum Anzeigen von Einträgen in der Liste der zulässigen/blockierten Mandanten</span><span class="sxs-lookup"><span data-stu-id="b7e65-165">Use the Security & Compliance Center to view entries in the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="b7e65-166">Wechseln Sie im Security & Compliance  Center zu "Richtlinienrichtlinien-Mandanten-Allow/Block \>  \> **Lists".**</span><span class="sxs-lookup"><span data-stu-id="b7e65-166">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="b7e65-167">Wählen Sie die **Registerkarte "URLs"** oder **"Dateien"** aus.</span><span class="sxs-lookup"><span data-stu-id="b7e65-167">Select the **URLs** tab or the **Files** tab.</span></span>

<span data-ttu-id="b7e65-168">Klicken Sie auf die folgenden Spaltenüberschriften, um in aufsteigender oder absteigender Reihenfolge zu sortieren:</span><span class="sxs-lookup"><span data-stu-id="b7e65-168">Click on the following column headings to sort in ascending or descending order:</span></span>

- <span data-ttu-id="b7e65-169">**Wert:** Die URL oder der Dateihash.</span><span class="sxs-lookup"><span data-stu-id="b7e65-169">**Value**: The URL or the file hash.</span></span>
- <span data-ttu-id="b7e65-170">**Datum der letzten Aktualisierung**</span><span class="sxs-lookup"><span data-stu-id="b7e65-170">**Last updated date**</span></span>
- <span data-ttu-id="b7e65-171">**Ablaufdatum**</span><span class="sxs-lookup"><span data-stu-id="b7e65-171">**Expiration date**</span></span>
- <span data-ttu-id="b7e65-172">**Hinweis**</span><span class="sxs-lookup"><span data-stu-id="b7e65-172">**Note**</span></span>

<span data-ttu-id="b7e65-173">Klicken **Sie auf "Suchen",** geben Sie einen Wert ganz oder teilweise ein, und drücken Sie dann die EINGABETASTE, um einen bestimmten Wert zu finden.</span><span class="sxs-lookup"><span data-stu-id="b7e65-173">Click **Search**, enter all or part of a value, and then press ENTER to find a specific value.</span></span> <span data-ttu-id="b7e65-174">Klicken Sie nach Abschluss des Abschlusses auf "Suche **löschen",** ![ um das Suchsymbol zu ](../../media/b6512677-5e7b-42b0-a8a3-3be1d7fa23ee.gif) löschen.</span><span class="sxs-lookup"><span data-stu-id="b7e65-174">When you're finished, click **Clear search** ![Clear search icon](../../media/b6512677-5e7b-42b0-a8a3-3be1d7fa23ee.gif).</span></span>

<span data-ttu-id="b7e65-175">Klicken Sie **auf Filter**.</span><span class="sxs-lookup"><span data-stu-id="b7e65-175">Click **Filter**.</span></span> <span data-ttu-id="b7e65-176">Konfigurieren Sie **im angezeigten** Filterf flyout eine der folgenden Einstellungen:</span><span class="sxs-lookup"><span data-stu-id="b7e65-176">In the **Filter** flyout that appears, configure any of the following settings:</span></span>

- <span data-ttu-id="b7e65-177">**Nie ablaufen:** Auswählen aus: ![ Umschalten ](../../media/scc-toggle-off.png) aus oder ein: ![ Umschalten ein ](../../media/scc-toggle-on.png) .</span><span class="sxs-lookup"><span data-stu-id="b7e65-177">**Never expire**: Select off: ![Toggle off](../../media/scc-toggle-off.png) or on: ![Toggle on](../../media/scc-toggle-on.png).</span></span>

- <span data-ttu-id="b7e65-178">**Last updated**: Select a start date (**From**), an end date (**To**) or both.</span><span class="sxs-lookup"><span data-stu-id="b7e65-178">**Last updated**: Select a start date (**From**), an end date (**To**) or both.</span></span>

- <span data-ttu-id="b7e65-179">**Ablaufdatum:** Wählen Sie ein Startdatum (**Von**), ein Enddatum (**Bis**) oder beides aus.</span><span class="sxs-lookup"><span data-stu-id="b7e65-179">**Expiration date**: Select a start date (**From**), an end date (**To**) or both.</span></span>

<span data-ttu-id="b7e65-180">Klicken Sie nach Abschluss des Abschlusses auf **"Übernehmen".**</span><span class="sxs-lookup"><span data-stu-id="b7e65-180">When you're finished, click **Apply**.</span></span>

<span data-ttu-id="b7e65-181">Klicken Sie auf **"Filter",** und klicken Sie im angezeigten **Flyout "Filter"** auf "Filter löschen", um vorhandene **Filter zu löschen.**</span><span class="sxs-lookup"><span data-stu-id="b7e65-181">To clear existing filters, click **Filter**, and in the **Filter** flyout that appears, click **Clear filters**.</span></span>

## <a name="use-the-security--compliance-center-to-modify-block-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="b7e65-182">Verwenden des Security & Compliance Center zum Ändern von Sperreinträgen in der Liste der zulässigen/blockierten Mandanten</span><span class="sxs-lookup"><span data-stu-id="b7e65-182">Use the Security & Compliance Center to modify block entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="b7e65-183">Sie können die vorhandenen blockierten URL- oder Dateiwerte in einem Eintrag nicht ändern.</span><span class="sxs-lookup"><span data-stu-id="b7e65-183">You can't modify the existing blocked URL or file values within an entry.</span></span> <span data-ttu-id="b7e65-184">Um diese Werte zu ändern, müssen Sie den Eintrag löschen und neu erstellen.</span><span class="sxs-lookup"><span data-stu-id="b7e65-184">To modify these values, you need to delete and recreate the entry.</span></span>

1. <span data-ttu-id="b7e65-185">Wechseln Sie im Security & Compliance  Center zu "Richtlinienrichtlinien-Mandanten-Allow/Block \>  \> **Lists".**</span><span class="sxs-lookup"><span data-stu-id="b7e65-185">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="b7e65-186">Wählen Sie die **Registerkarte "URLs"** oder **"Dateien"** aus.</span><span class="sxs-lookup"><span data-stu-id="b7e65-186">Select the **URLs** tab or the **Files** tab.</span></span>

3. <span data-ttu-id="b7e65-187">Wählen Sie den Blockeintrag aus, den Sie ändern möchten, und klicken Sie dann auf **das** ![ Bearbeitungssymbol ](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) .</span><span class="sxs-lookup"><span data-stu-id="b7e65-187">Select the block entry that you want to modify, and then click **Edit** ![Edit icon](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png).</span></span>

4. <span data-ttu-id="b7e65-188">Konfigurieren Sie im angezeigten Flyout die folgenden Einstellungen:</span><span class="sxs-lookup"><span data-stu-id="b7e65-188">In the flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="b7e65-189">**Läuft nie** ab: Gehen Sie wie folgt vor:</span><span class="sxs-lookup"><span data-stu-id="b7e65-189">**Never expire**: Do one of the following steps:</span></span>

     - <span data-ttu-id="b7e65-190">Stellen Sie sicher, dass die Einstellung deaktiviert ist (Umschalten aus), und verwenden Sie das Feld "Abläuft bei", um das ![ ](../../media/scc-toggle-off.png) Ablaufdatum für den Eintrag anzugeben. </span><span class="sxs-lookup"><span data-stu-id="b7e65-190">Verify the setting is turned off (![Toggle off](../../media/scc-toggle-off.png)) and use the **Expires on** box to specify the expiration date for the entry.</span></span>

     <span data-ttu-id="b7e65-191">oder</span><span class="sxs-lookup"><span data-stu-id="b7e65-191">or</span></span>

     - <span data-ttu-id="b7e65-192">Verschieben Sie den Umschalter nach rechts, um den Eintrag so zu konfigurieren, dass er nie abläuft:</span><span class="sxs-lookup"><span data-stu-id="b7e65-192">Move the toggle to the right to configure the entry to never expire:</span></span> ![Umschaltfläche ein](../../media/scc-toggle-on.png)<span data-ttu-id="b7e65-194">.</span><span class="sxs-lookup"><span data-stu-id="b7e65-194">.</span></span>

   - <span data-ttu-id="b7e65-195">**Optionaler Hinweis:** Geben Sie einen beschreibenden Text für den Eintrag ein.</span><span class="sxs-lookup"><span data-stu-id="b7e65-195">**Optional note**: Enter descriptive text for the entry.</span></span>

5. <span data-ttu-id="b7e65-196">Klicken Sie nach Abschluss des Vorgangs auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="b7e65-196">When you're finished, click **Save**.</span></span>

## <a name="use-the-security--compliance-center-to-remove-block-entries-from-the-tenant-allowblock-list"></a><span data-ttu-id="b7e65-197">Verwenden des Security & Compliance Center zum Entfernen von Blockeinträgen aus der Liste der zulässigen/blockierten Mandanten</span><span class="sxs-lookup"><span data-stu-id="b7e65-197">Use the Security & Compliance Center to remove block entries from the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="b7e65-198">Wechseln Sie im Security & Compliance  Center zu "Richtlinienrichtlinien-Mandanten-Allow/Block \>  \> **Lists".**</span><span class="sxs-lookup"><span data-stu-id="b7e65-198">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="b7e65-199">Wählen Sie die **Registerkarte "URLs"** oder **"Dateien"** aus.</span><span class="sxs-lookup"><span data-stu-id="b7e65-199">Select the **URLs** tab or the **Files** tab.</span></span>

3. <span data-ttu-id="b7e65-200">Wählen Sie den Blockeintrag aus, den Sie entfernen möchten, und klicken Sie dann auf **das** Symbol ![ "Löschen". ](../../media/87565fbb-5147-4f22-9ed7-1c18ce664392.png)</span><span class="sxs-lookup"><span data-stu-id="b7e65-200">Select the block entry that you want to remove, and then click **Delete** ![Delete icon](../../media/87565fbb-5147-4f22-9ed7-1c18ce664392.png).</span></span>

4. <span data-ttu-id="b7e65-201">Klicken Sie im angezeigten Warnungsdialogfeld auf **"Löschen".**</span><span class="sxs-lookup"><span data-stu-id="b7e65-201">In the warning dialog that appears, click **Delete**.</span></span>

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-the-tenant-allowblock-list"></a><span data-ttu-id="b7e65-202">Verwenden von Exchange Online PowerShell oder der eigenständigen EOP PowerShell zum Konfigurieren der Liste zulässiger/blockierter Mandanten</span><span class="sxs-lookup"><span data-stu-id="b7e65-202">Use Exchange Online PowerShell or standalone EOP PowerShell to configure the Tenant Allow/Block List</span></span>

### <a name="use-powershell-to-add-block-entries-to-the-tenant-allowblock-list"></a><span data-ttu-id="b7e65-203">Verwenden von PowerShell zum Hinzufügen von Blockeinträgen zur Liste der zulässigen/blockierten Mandanten</span><span class="sxs-lookup"><span data-stu-id="b7e65-203">Use PowerShell to add block entries to the Tenant Allow/Block List</span></span>

<span data-ttu-id="b7e65-204">Verwenden Sie die folgende Syntax, um blockeinträge in der Liste der zulässigen/blockierten Mandanten hinzuzufügen:</span><span class="sxs-lookup"><span data-stu-id="b7e65-204">To add block entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
New-TenantAllowBlockListItems -ListType <Url | FileHash> -Block -Entries <String[]> [-ExpirationDate <DateTime>] [-NoExpiration] [-Notes <String>]
```

<span data-ttu-id="b7e65-205">In diesem Beispiel wird ein Block-URL-Eintrag für contoso.com und alle Unterdomänen hinzugefügt (z. B. contoso.com, www.contoso.com und xyz.abc.contoso.com).</span><span class="sxs-lookup"><span data-stu-id="b7e65-205">This example adds a block URL entry for contoso.com and all subdomains (for example, contoso.com, www.contoso.com, and xyz.abc.contoso.com).</span></span> <span data-ttu-id="b7e65-206">Da wir die Parameter "ExpirationDate" oder "NoExpiration" nicht verwendet haben, läuft der Eintrag nach 30 Tagen ab.</span><span class="sxs-lookup"><span data-stu-id="b7e65-206">Because we didn't use the ExpirationDate or NoExpiration parameters, the entry expires after 30 days.</span></span>

```powershell
New-TenantAllowBlockListItem -ListType Url -Block -Entries ~contoso.com
```

<span data-ttu-id="b7e65-207">In diesem Beispiel wird für die angegebenen Dateien, die nie ablaufen, ein Blockdateieintrag hinzufügt.</span><span class="sxs-lookup"><span data-stu-id="b7e65-207">This example adds a block file entry for the specified files that never expires.</span></span>

```powershell
New-TenantAllowBlockListItem -ListType FileHash -Block -Entries "768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3","2c0a35409ff0873cfa28b70b8224e9aca2362241c1f0ed6f622fef8d4722fd9a" -NoExpiration
```

<span data-ttu-id="b7e65-208">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [New-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/new-tenantallowblocklistitems).</span><span class="sxs-lookup"><span data-stu-id="b7e65-208">For detailed syntax and parameter information, see [New-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/new-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-view-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="b7e65-209">Verwenden von PowerShell zum Anzeigen von Einträgen in der Liste der zulässigen/blockierten Mandanten</span><span class="sxs-lookup"><span data-stu-id="b7e65-209">Use PowerShell to view entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="b7e65-210">Verwenden Sie die folgende Syntax, um Einträge in der Liste der zulässigen/blockierten Mandanten anzeigen zu können:</span><span class="sxs-lookup"><span data-stu-id="b7e65-210">To view entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType <Url | FileHash> [-Entry <URLValue | FileHashValue>] [-Block] [-ExpirationDate <DateTime>] [-NoExpiration]
```

<span data-ttu-id="b7e65-211">In diesem Beispiel werden alle blockierten URLs zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="b7e65-211">This example returns all blocked URLs.</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType Url -Block
```

<span data-ttu-id="b7e65-212">In diesem Beispiel werden Informationen für den angegebenen Dateihashwert zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="b7e65-212">This example returns information for the specified file hash value.</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType FileHash -Entry "9f86d081884c7d659a2feaa0c55ad015a3bf4f1b2b0b822cd15d6c15b0f00a08"
```

<span data-ttu-id="b7e65-213">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Get-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/get-tenantallowblocklistitems).</span><span class="sxs-lookup"><span data-stu-id="b7e65-213">For detailed syntax and parameter information, see [Get-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/get-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-modify-block-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="b7e65-214">Verwenden von PowerShell zum Ändern von Blockeinträgen in der Liste der zulässigen/blockierten Mandanten</span><span class="sxs-lookup"><span data-stu-id="b7e65-214">Use PowerShell to modify block entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="b7e65-215">Sie können die vorhandenen URL- oder Dateiwerte in einem Blockeintrag nicht ändern.</span><span class="sxs-lookup"><span data-stu-id="b7e65-215">You can't modify the existing URL or file values within a block entry.</span></span> <span data-ttu-id="b7e65-216">Um diese Werte zu ändern, müssen Sie den Eintrag löschen und neu erstellen.</span><span class="sxs-lookup"><span data-stu-id="b7e65-216">To modify these values, you need to delete and recreate the entry.</span></span>

<span data-ttu-id="b7e65-217">Verwenden Sie die folgende Syntax, um Blockeinträge in der Liste der zulässigen/blockierten Mandanten zu ändern:</span><span class="sxs-lookup"><span data-stu-id="b7e65-217">To modify block entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Set-TenantAllowBlockListItems -ListType <Url | FileHash> -Ids <"Id1","Id2",..."IdN"> [-Block] [-ExpirationDate <DateTime>] [-NoExpiration] [-Notes <String>]
```

<span data-ttu-id="b7e65-218">In diesem Beispiel wird das Ablaufdatum des angegebenen Blockeintrags geändert.</span><span class="sxs-lookup"><span data-stu-id="b7e65-218">This example changes the expiration date of the specified block entry.</span></span>

```powershell
Set-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSRAAAA" -ExpirationDate (Get-Date "5/30/2020 9:30 AM").ToUniversalTime()
```

<span data-ttu-id="b7e65-219">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Set-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/set-tenantallowblocklistitems).</span><span class="sxs-lookup"><span data-stu-id="b7e65-219">For detailed syntax and parameter information, see [Set-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/set-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-remove-block-entries-from-the-tenant-allowblock-list"></a><span data-ttu-id="b7e65-220">Verwenden von PowerShell zum Entfernen von Blockeinträgen aus der Liste der zulässigen/blockierten Mandanten</span><span class="sxs-lookup"><span data-stu-id="b7e65-220">Use PowerShell to remove block entries from the Tenant Allow/Block List</span></span>

<span data-ttu-id="b7e65-221">Verwenden Sie die folgende Syntax, um Blockeinträge aus der Liste der zulässigen/blockierten Mandanten zu entfernen:</span><span class="sxs-lookup"><span data-stu-id="b7e65-221">To remove block entries from the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Remove-TenantAllowBlockListItems -ListType <Url | FileHash> -Ids <"Id1","Id2",..."IdN">
```

<span data-ttu-id="b7e65-222">In diesem Beispiel wird der angegebene Block-URL-Eintrag aus der Liste der zulässigen/blockierten Mandanten entfernt.</span><span class="sxs-lookup"><span data-stu-id="b7e65-222">This example removes the specified block URL entry from the Tenant Allow/Block List.</span></span>

```powershell
Remove-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSPAAAA0"
```

<span data-ttu-id="b7e65-223">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Remove-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/remove-tenantallowblocklistitems).</span><span class="sxs-lookup"><span data-stu-id="b7e65-223">For detailed syntax and parameter information, see [Remove-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/remove-tenantallowblocklistitems).</span></span>

## <a name="url-syntax-for-the-tenant-allowblock-list"></a><span data-ttu-id="b7e65-224">#A0 für die Liste der zulässigen/blockierten Mandanten</span><span class="sxs-lookup"><span data-stu-id="b7e65-224">URL syntax for the Tenant Allow/Block List</span></span>

- <span data-ttu-id="b7e65-225">IP4v- und IPv6-Adressen sind zulässig, TCP/UDP-Ports jedoch nicht.</span><span class="sxs-lookup"><span data-stu-id="b7e65-225">IP4v and IPv6 addresses are allowed, but TCP/UDP ports are not.</span></span>

- <span data-ttu-id="b7e65-226">Dateinamenerweiterungen sind nicht zulässig (z. B. test.pdf).</span><span class="sxs-lookup"><span data-stu-id="b7e65-226">Filename extensions are not allowed (for example, test.pdf).</span></span>

- <span data-ttu-id="b7e65-227">Unicode wird nicht unterstützt, Punycode jedoch.</span><span class="sxs-lookup"><span data-stu-id="b7e65-227">Unicode is not supported, but Punycode is.</span></span>

- <span data-ttu-id="b7e65-228">Hostnamen sind zulässig, wenn alle folgenden Anweisungen wahr sind:</span><span class="sxs-lookup"><span data-stu-id="b7e65-228">Hostnames are allowed if all of the following statements are true:</span></span>
  - <span data-ttu-id="b7e65-229">Der Hostname enthält einen Zeitraum.</span><span class="sxs-lookup"><span data-stu-id="b7e65-229">The hostname contains a period.</span></span>
  - <span data-ttu-id="b7e65-230">Links vom Zeitraum befindet sich mindestens ein Zeichen.</span><span class="sxs-lookup"><span data-stu-id="b7e65-230">There is at least one character to the left of the period.</span></span>
  - <span data-ttu-id="b7e65-231">Rechts neben dem Zeitraum befinden sich mindestens zwei Zeichen.</span><span class="sxs-lookup"><span data-stu-id="b7e65-231">There are at least two characters to the right of the period.</span></span>

  <span data-ttu-id="b7e65-232">Beispielsweise ist `t.co` dies zulässig oder `.com` nicht `contoso.` zulässig.</span><span class="sxs-lookup"><span data-stu-id="b7e65-232">For example, `t.co` is allowed; `.com` or `contoso.` are not allowed.</span></span>

- <span data-ttu-id="b7e65-233">Unterpfade werden nicht impliziert.</span><span class="sxs-lookup"><span data-stu-id="b7e65-233">Subpaths are not implied.</span></span>

  <span data-ttu-id="b7e65-234">Enthält z. `contoso.com` B. nicht `contoso.com/a` .</span><span class="sxs-lookup"><span data-stu-id="b7e65-234">For example, `contoso.com` does not include `contoso.com/a`.</span></span>

- <span data-ttu-id="b7e65-235">Platzhalter (\*) sind in den folgenden Szenarien zulässig:</span><span class="sxs-lookup"><span data-stu-id="b7e65-235">Wildcards (\*) are allowed in the following scenarios:</span></span>

  - <span data-ttu-id="b7e65-236">Auf einen linken Platzhalter muss ein Zeitraum folgen, um eine Unterdomäne anzugeben.</span><span class="sxs-lookup"><span data-stu-id="b7e65-236">A left wildcard must be followed by a period to specify a subdomain.</span></span>

    <span data-ttu-id="b7e65-237">Ist z. `*.contoso.com` B. zulässig; `*contoso.com` ist nicht zulässig.</span><span class="sxs-lookup"><span data-stu-id="b7e65-237">For example, `*.contoso.com` is allowed; `*contoso.com` is not allowed.</span></span>

  - <span data-ttu-id="b7e65-238">Ein rechter Platzhalter muss einem Schrägstrich (/) folgen, um einen Pfad anzugeben.</span><span class="sxs-lookup"><span data-stu-id="b7e65-238">A right wildcard must follow a forward slash (/) to specify a path.</span></span>

    <span data-ttu-id="b7e65-239">Beispielsweise ist `contoso.com/*` dies zulässig oder `contoso.com*` nicht `contoso.com/ab*` zulässig.</span><span class="sxs-lookup"><span data-stu-id="b7e65-239">For example, `contoso.com/*` is allowed; `contoso.com*` or `contoso.com/ab*` are not allowed.</span></span>

  - <span data-ttu-id="b7e65-240">Alle Unterpfade werden nicht durch einen rechten Platzhalter impliziert.</span><span class="sxs-lookup"><span data-stu-id="b7e65-240">All subpaths are not implied by a right wildcard.</span></span>

    <span data-ttu-id="b7e65-241">Enthält `contoso.com/*` z. B. nicht `contoso.com/a` .</span><span class="sxs-lookup"><span data-stu-id="b7e65-241">For example, `contoso.com/*` does not include `contoso.com/a`.</span></span>

  - <span data-ttu-id="b7e65-242">`*.com*` ungültig ist (keine auflösbare Domäne, und der rechte Platzhalter folgt keinem Schrägstrich).</span><span class="sxs-lookup"><span data-stu-id="b7e65-242">`*.com*` is invalid (not a resolvable domain and the right wildcard does not follow a forward slash).</span></span>

  - <span data-ttu-id="b7e65-243">Platzhalter sind in IP-Adressen nicht zulässig.</span><span class="sxs-lookup"><span data-stu-id="b7e65-243">Wildcards are not allowed in IP addresses.</span></span>

- <span data-ttu-id="b7e65-244">Das Tildezeichen (~) ist in den folgenden Szenarien verfügbar:</span><span class="sxs-lookup"><span data-stu-id="b7e65-244">The tilde (~) character is available in the following scenarios:</span></span>

  - <span data-ttu-id="b7e65-245">Eine linke Tilde impliziert eine Domäne und alle Unterdomänen.</span><span class="sxs-lookup"><span data-stu-id="b7e65-245">A left tilde implies a domain and all subdomains.</span></span>

    <span data-ttu-id="b7e65-246">Beispielsweise enthält `~contoso.com` `contoso.com` und `*.contoso.com` .</span><span class="sxs-lookup"><span data-stu-id="b7e65-246">For example `~contoso.com` includes `contoso.com` and `*.contoso.com`.</span></span>

- <span data-ttu-id="b7e65-247">BEI URL-Einträgen, die Protokolle (z. B. , oder ) enthalten, kann ein Fehler angezeigt werden, da die Urleinträge `http://` `https://` für alle Protokolle `ftp://` gelten.</span><span class="sxs-lookup"><span data-stu-id="b7e65-247">URL entries that contain protocols (for example, `http://`, `https://`, or `ftp://`) will fail, because URL entries apply to all protocols.</span></span>

- <span data-ttu-id="b7e65-248">Ein Benutzername oder Kennwort wird nicht unterstützt oder ist nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="b7e65-248">A username or password aren't supported or required.</span></span>

- <span data-ttu-id="b7e65-249">Anführungszeichen (' oder ") sind ungültige Zeichen.</span><span class="sxs-lookup"><span data-stu-id="b7e65-249">Quotes (' or ") are invalid characters.</span></span>

- <span data-ttu-id="b7e65-250">Eine URL sollte nach Möglichkeit alle Umleitungen enthalten.</span><span class="sxs-lookup"><span data-stu-id="b7e65-250">A URL should include all redirects where possible.</span></span>

### <a name="url-entry-scenarios"></a><span data-ttu-id="b7e65-251">Szenarien für die EINGABE VON URLs</span><span class="sxs-lookup"><span data-stu-id="b7e65-251">URL entry scenarios</span></span>

<span data-ttu-id="b7e65-252">Gültige URL-Einträge und deren Ergebnisse werden in den folgenden Abschnitten beschrieben.</span><span class="sxs-lookup"><span data-stu-id="b7e65-252">Valid URL entries and their results are described in the following sections.</span></span>

#### <a name="scenario-no-wildcards"></a><span data-ttu-id="b7e65-253">Szenario: Keine Platzhalter</span><span class="sxs-lookup"><span data-stu-id="b7e65-253">Scenario: No wildcards</span></span>

<span data-ttu-id="b7e65-254">**Eintrag:**`contoso.com`</span><span class="sxs-lookup"><span data-stu-id="b7e65-254">**Entry**: `contoso.com`</span></span>

- <span data-ttu-id="b7e65-255">**Übereinstimmung zulassen:** contoso.com</span><span class="sxs-lookup"><span data-stu-id="b7e65-255">**Allow match**: contoso.com</span></span>

- <span data-ttu-id="b7e65-256">**Nicht übereinstimmend zulassen:**</span><span class="sxs-lookup"><span data-stu-id="b7e65-256">**Allow not matched**:</span></span>

  - <span data-ttu-id="b7e65-257">abc-contoso.com</span><span class="sxs-lookup"><span data-stu-id="b7e65-257">abc-contoso.com</span></span>
  - <span data-ttu-id="b7e65-258">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="b7e65-258">contoso.com/a</span></span>
  - <span data-ttu-id="b7e65-259">payroll.contoso.com</span><span class="sxs-lookup"><span data-stu-id="b7e65-259">payroll.contoso.com</span></span>
  - <span data-ttu-id="b7e65-260">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="b7e65-260">test.com/contoso.com</span></span>
  - <span data-ttu-id="b7e65-261">test.com/q=contoso.com</span><span class="sxs-lookup"><span data-stu-id="b7e65-261">test.com/q=contoso.com</span></span>
  - <span data-ttu-id="b7e65-262">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="b7e65-262">www.contoso.com</span></span>
  - <span data-ttu-id="b7e65-263">www.contoso.com/q=a@contoso.com</span><span class="sxs-lookup"><span data-stu-id="b7e65-263">www.contoso.com/q=a@contoso.com</span></span>

- <span data-ttu-id="b7e65-264">**Übereinstimmung blockieren:**</span><span class="sxs-lookup"><span data-stu-id="b7e65-264">**Block match**:</span></span>

  - <span data-ttu-id="b7e65-265">contoso.com</span><span class="sxs-lookup"><span data-stu-id="b7e65-265">contoso.com</span></span>
  - <span data-ttu-id="b7e65-266">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="b7e65-266">contoso.com/a</span></span>
  - <span data-ttu-id="b7e65-267">payroll.contoso.com</span><span class="sxs-lookup"><span data-stu-id="b7e65-267">payroll.contoso.com</span></span>
  - <span data-ttu-id="b7e65-268">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="b7e65-268">test.com/contoso.com</span></span>
  - <span data-ttu-id="b7e65-269">test.com/q=contoso.com</span><span class="sxs-lookup"><span data-stu-id="b7e65-269">test.com/q=contoso.com</span></span>
  - <span data-ttu-id="b7e65-270">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="b7e65-270">www.contoso.com</span></span>
  - <span data-ttu-id="b7e65-271">www.contoso.com/q=a@contoso.com</span><span class="sxs-lookup"><span data-stu-id="b7e65-271">www.contoso.com/q=a@contoso.com</span></span>

- <span data-ttu-id="b7e65-272">**Block nicht übereinstimmend:** abc-contoso.com</span><span class="sxs-lookup"><span data-stu-id="b7e65-272">**Block not matched**: abc-contoso.com</span></span>

#### <a name="scenario-left-wildcard-subdomain"></a><span data-ttu-id="b7e65-273">Szenario: Linker Platzhalter (Unterdomäne)</span><span class="sxs-lookup"><span data-stu-id="b7e65-273">Scenario: Left wildcard (subdomain)</span></span>

<span data-ttu-id="b7e65-274">**Eintrag:**`*.contoso.com`</span><span class="sxs-lookup"><span data-stu-id="b7e65-274">**Entry**: `*.contoso.com`</span></span>

- <span data-ttu-id="b7e65-275">**Übereinstimmung zulassen** und **Übereinstimmung blockieren:**</span><span class="sxs-lookup"><span data-stu-id="b7e65-275">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="b7e65-276">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="b7e65-276">www.contoso.com</span></span>
  - <span data-ttu-id="b7e65-277">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="b7e65-277">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="b7e65-278">**Nicht übereinstimmend zulassen und** **Block nicht übereinstimmen:**</span><span class="sxs-lookup"><span data-stu-id="b7e65-278">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="b7e65-279">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="b7e65-279">123contoso.com</span></span>
  - <span data-ttu-id="b7e65-280">contoso.com</span><span class="sxs-lookup"><span data-stu-id="b7e65-280">contoso.com</span></span>
  - <span data-ttu-id="b7e65-281">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="b7e65-281">test.com/contoso.com</span></span>
  - <span data-ttu-id="b7e65-282">www.contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="b7e65-282">www.contoso.com/abc</span></span>

#### <a name="scenario-right-wildcard-at-top-of-path"></a><span data-ttu-id="b7e65-283">Szenario: Rechter Platzhalter oben im Pfad</span><span class="sxs-lookup"><span data-stu-id="b7e65-283">Scenario: Right wildcard at top of path</span></span>

<span data-ttu-id="b7e65-284">**Eintrag:**`contoso.com/a/*`</span><span class="sxs-lookup"><span data-stu-id="b7e65-284">**Entry**: `contoso.com/a/*`</span></span>

- <span data-ttu-id="b7e65-285">**Übereinstimmung zulassen** und **Übereinstimmung blockieren:**</span><span class="sxs-lookup"><span data-stu-id="b7e65-285">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="b7e65-286">contoso.com/a/b</span><span class="sxs-lookup"><span data-stu-id="b7e65-286">contoso.com/a/b</span></span>
  - <span data-ttu-id="b7e65-287">contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="b7e65-287">contoso.com/a/b/c</span></span>
  - <span data-ttu-id="b7e65-288">contoso.com/a/?q=joe@t.com</span><span class="sxs-lookup"><span data-stu-id="b7e65-288">contoso.com/a/?q=joe@t.com</span></span>

- <span data-ttu-id="b7e65-289">**Nicht übereinstimmend zulassen und** **Block nicht übereinstimmen:**</span><span class="sxs-lookup"><span data-stu-id="b7e65-289">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="b7e65-290">contoso.com</span><span class="sxs-lookup"><span data-stu-id="b7e65-290">contoso.com</span></span>
  - <span data-ttu-id="b7e65-291">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="b7e65-291">contoso.com/a</span></span>
  - <span data-ttu-id="b7e65-292">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="b7e65-292">www.contoso.com</span></span>
  - <span data-ttu-id="b7e65-293">www.contoso.com/q=a@contoso.com</span><span class="sxs-lookup"><span data-stu-id="b7e65-293">www.contoso.com/q=a@contoso.com</span></span>

#### <a name="scenario-left-tilde"></a><span data-ttu-id="b7e65-294">Szenario: Left tilde</span><span class="sxs-lookup"><span data-stu-id="b7e65-294">Scenario: Left tilde</span></span>

<span data-ttu-id="b7e65-295">**Eintrag:**`~contoso.com`</span><span class="sxs-lookup"><span data-stu-id="b7e65-295">**Entry**: `~contoso.com`</span></span>

- <span data-ttu-id="b7e65-296">**Übereinstimmung zulassen** und **Übereinstimmung blockieren:**</span><span class="sxs-lookup"><span data-stu-id="b7e65-296">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="b7e65-297">contoso.com</span><span class="sxs-lookup"><span data-stu-id="b7e65-297">contoso.com</span></span>
  - <span data-ttu-id="b7e65-298">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="b7e65-298">www.contoso.com</span></span>
  - <span data-ttu-id="b7e65-299">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="b7e65-299">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="b7e65-300">**Nicht übereinstimmend zulassen und** **Block nicht übereinstimmen:**</span><span class="sxs-lookup"><span data-stu-id="b7e65-300">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="b7e65-301">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="b7e65-301">123contoso.com</span></span>
  - <span data-ttu-id="b7e65-302">contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="b7e65-302">contoso.com/abc</span></span>
  - <span data-ttu-id="b7e65-303">www.contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="b7e65-303">www.contoso.com/abc</span></span>

#### <a name="scenario-right-wildcard-suffix"></a><span data-ttu-id="b7e65-304">Szenario: Rechtes Platzhaltersuffix</span><span class="sxs-lookup"><span data-stu-id="b7e65-304">Scenario: Right wildcard suffix</span></span>

<span data-ttu-id="b7e65-305">**Eintrag:**`contoso.com/*`</span><span class="sxs-lookup"><span data-stu-id="b7e65-305">**Entry**: `contoso.com/*`</span></span>

- <span data-ttu-id="b7e65-306">**Übereinstimmung zulassen** und **Übereinstimmung blockieren:**</span><span class="sxs-lookup"><span data-stu-id="b7e65-306">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="b7e65-307">contoso.com/?q=whatever@fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="b7e65-307">contoso.com/?q=whatever@fabrikam.com</span></span>
  - <span data-ttu-id="b7e65-308">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="b7e65-308">contoso.com/a</span></span>
  - <span data-ttu-id="b7e65-309">contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="b7e65-309">contoso.com/a/b/c</span></span>
  - <span data-ttu-id="b7e65-310">contoso.com/ab</span><span class="sxs-lookup"><span data-stu-id="b7e65-310">contoso.com/ab</span></span>
  - <span data-ttu-id="b7e65-311">contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="b7e65-311">contoso.com/b</span></span>
  - <span data-ttu-id="b7e65-312">contoso.com/b/a/c</span><span class="sxs-lookup"><span data-stu-id="b7e65-312">contoso.com/b/a/c</span></span>
  - <span data-ttu-id="b7e65-313">contoso.com/ba</span><span class="sxs-lookup"><span data-stu-id="b7e65-313">contoso.com/ba</span></span>

- <span data-ttu-id="b7e65-314">**Nicht übereinstimmend zulassen und** **Block nicht übereinstimmen:** contoso.com</span><span class="sxs-lookup"><span data-stu-id="b7e65-314">**Allow not matched** and **Block not matched**: contoso.com</span></span>

#### <a name="scenario-left-wildcard-subdomain-and-right-wildcard-suffix"></a><span data-ttu-id="b7e65-315">Szenario: Linke Platzhalterunterdomäne und rechtes Platzhaltersuffix</span><span class="sxs-lookup"><span data-stu-id="b7e65-315">Scenario: Left wildcard subdomain and right wildcard suffix</span></span>

<span data-ttu-id="b7e65-316">**Eintrag:**`*.contoso.com/*`</span><span class="sxs-lookup"><span data-stu-id="b7e65-316">**Entry**: `*.contoso.com/*`</span></span>

- <span data-ttu-id="b7e65-317">**Übereinstimmung zulassen** und **Übereinstimmung blockieren:**</span><span class="sxs-lookup"><span data-stu-id="b7e65-317">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="b7e65-318">abc.contoso.com/ab</span><span class="sxs-lookup"><span data-stu-id="b7e65-318">abc.contoso.com/ab</span></span>
  - <span data-ttu-id="b7e65-319">abc.xyz.contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="b7e65-319">abc.xyz.contoso.com/a/b/c</span></span>
  - <span data-ttu-id="b7e65-320">www.contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="b7e65-320">www.contoso.com/a</span></span>
  - <span data-ttu-id="b7e65-321">www.contoso.com/b/a/c</span><span class="sxs-lookup"><span data-stu-id="b7e65-321">www.contoso.com/b/a/c</span></span>
  - <span data-ttu-id="b7e65-322">xyz.contoso.com/ba</span><span class="sxs-lookup"><span data-stu-id="b7e65-322">xyz.contoso.com/ba</span></span>

- <span data-ttu-id="b7e65-323">**Nicht übereinstimmend zulassen und** **Block nicht übereinstimmen:** contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="b7e65-323">**Allow not matched** and **Block not matched**: contoso.com/b</span></span>

#### <a name="scenario-left-and-right-tilde"></a><span data-ttu-id="b7e65-324">Szenario: Linke und rechte Tilde</span><span class="sxs-lookup"><span data-stu-id="b7e65-324">Scenario: Left and right tilde</span></span>

<span data-ttu-id="b7e65-325">**Eintrag:**`~contoso.com~`</span><span class="sxs-lookup"><span data-stu-id="b7e65-325">**Entry**: `~contoso.com~`</span></span>

- <span data-ttu-id="b7e65-326">**Übereinstimmung zulassen** und **Übereinstimmung blockieren:**</span><span class="sxs-lookup"><span data-stu-id="b7e65-326">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="b7e65-327">contoso.com</span><span class="sxs-lookup"><span data-stu-id="b7e65-327">contoso.com</span></span>
  - <span data-ttu-id="b7e65-328">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="b7e65-328">contoso.com/a</span></span>
  - <span data-ttu-id="b7e65-329">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="b7e65-329">www.contoso.com</span></span>
  - <span data-ttu-id="b7e65-330">www.contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="b7e65-330">www.contoso.com/b</span></span>
  - <span data-ttu-id="b7e65-331">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="b7e65-331">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="b7e65-332">**Nicht übereinstimmend zulassen und** **Block nicht übereinstimmen:**</span><span class="sxs-lookup"><span data-stu-id="b7e65-332">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="b7e65-333">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="b7e65-333">123contoso.com</span></span>
  - <span data-ttu-id="b7e65-334">contoso.org</span><span class="sxs-lookup"><span data-stu-id="b7e65-334">contoso.org</span></span>

#### <a name="scenario-ip-address"></a><span data-ttu-id="b7e65-335">Szenario: IP-Adresse</span><span class="sxs-lookup"><span data-stu-id="b7e65-335">Scenario: IP address</span></span>

<span data-ttu-id="b7e65-336">**Eintrag:**`1.2.3.4`</span><span class="sxs-lookup"><span data-stu-id="b7e65-336">**Entry**: `1.2.3.4`</span></span>

- <span data-ttu-id="b7e65-337">**Übereinstimmung zulassen** und **Blockierung:** 1.2.3.4</span><span class="sxs-lookup"><span data-stu-id="b7e65-337">**Allow match** and **Block match**: 1.2.3.4</span></span>

- <span data-ttu-id="b7e65-338">**Nicht übereinstimmend zulassen und** **Block nicht übereinstimmen:**</span><span class="sxs-lookup"><span data-stu-id="b7e65-338">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="b7e65-339">1.2.3.4/a</span><span class="sxs-lookup"><span data-stu-id="b7e65-339">1.2.3.4/a</span></span>
  - <span data-ttu-id="b7e65-340">11.2.3.4/a</span><span class="sxs-lookup"><span data-stu-id="b7e65-340">11.2.3.4/a</span></span>

#### <a name="ip-address-with-right-wildcard"></a><span data-ttu-id="b7e65-341">IP-Adresse mit rechtem Platzhalter</span><span class="sxs-lookup"><span data-stu-id="b7e65-341">IP address with right wildcard</span></span>

<span data-ttu-id="b7e65-342">**Eintrag:**`1.2.3.4/*`</span><span class="sxs-lookup"><span data-stu-id="b7e65-342">**Entry**: `1.2.3.4/*`</span></span>

- <span data-ttu-id="b7e65-343">**Übereinstimmung zulassen** und **Übereinstimmung blockieren:**</span><span class="sxs-lookup"><span data-stu-id="b7e65-343">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="b7e65-344">1.2.3.4/b</span><span class="sxs-lookup"><span data-stu-id="b7e65-344">1.2.3.4/b</span></span>
  - <span data-ttu-id="b7e65-345">1.2.3.4/baaaa</span><span class="sxs-lookup"><span data-stu-id="b7e65-345">1.2.3.4/baaaa</span></span>

### <a name="examples-of-invalid-entries"></a><span data-ttu-id="b7e65-346">Beispiele für ungültige Einträge</span><span class="sxs-lookup"><span data-stu-id="b7e65-346">Examples of invalid entries</span></span>

<span data-ttu-id="b7e65-347">Die folgenden Einträge sind ungültig:</span><span class="sxs-lookup"><span data-stu-id="b7e65-347">The following entries are invalid:</span></span>

- <span data-ttu-id="b7e65-348">**Fehlende oder ungültige Domänenwerte:**</span><span class="sxs-lookup"><span data-stu-id="b7e65-348">**Missing or invalid domain values**:</span></span>

  - <span data-ttu-id="b7e65-349">contoso</span><span class="sxs-lookup"><span data-stu-id="b7e65-349">contoso</span></span>
  - <span data-ttu-id="b7e65-350">\*.contoso.\*</span><span class="sxs-lookup"><span data-stu-id="b7e65-350">\*.contoso.\*</span></span>
  - <span data-ttu-id="b7e65-351">\*.com</span><span class="sxs-lookup"><span data-stu-id="b7e65-351">\*.com</span></span>
  - <span data-ttu-id="b7e65-352">\*.pdf</span><span class="sxs-lookup"><span data-stu-id="b7e65-352">\*.pdf</span></span>

- <span data-ttu-id="b7e65-353">**Platzhalter für Text oder ohne Leerzeichen:**</span><span class="sxs-lookup"><span data-stu-id="b7e65-353">**Wildcard on text or without spacing characters**:</span></span>

  - <span data-ttu-id="b7e65-354">\*contoso.com</span><span class="sxs-lookup"><span data-stu-id="b7e65-354">\*contoso.com</span></span>
  - <span data-ttu-id="b7e65-355">contoso.com\*</span><span class="sxs-lookup"><span data-stu-id="b7e65-355">contoso.com\*</span></span>
  - <span data-ttu-id="b7e65-356">\*1.2.3.4</span><span class="sxs-lookup"><span data-stu-id="b7e65-356">\*1.2.3.4</span></span>
  - <span data-ttu-id="b7e65-357">1.2.3.4\*</span><span class="sxs-lookup"><span data-stu-id="b7e65-357">1.2.3.4\*</span></span>
  - <span data-ttu-id="b7e65-358">contoso.com/a\*</span><span class="sxs-lookup"><span data-stu-id="b7e65-358">contoso.com/a\*</span></span>
  - <span data-ttu-id="b7e65-359">contoso.com/ab\*</span><span class="sxs-lookup"><span data-stu-id="b7e65-359">contoso.com/ab\*</span></span>

- <span data-ttu-id="b7e65-360">**IP-Adressen mit Ports:**</span><span class="sxs-lookup"><span data-stu-id="b7e65-360">**IP addresses with ports**:</span></span>

  - <span data-ttu-id="b7e65-361">contoso.com:443</span><span class="sxs-lookup"><span data-stu-id="b7e65-361">contoso.com:443</span></span>
  - <span data-ttu-id="b7e65-362">abc.contoso.com:25</span><span class="sxs-lookup"><span data-stu-id="b7e65-362">abc.contoso.com:25</span></span>

- <span data-ttu-id="b7e65-363">**Nicht beschreibende Platzhalter:**</span><span class="sxs-lookup"><span data-stu-id="b7e65-363">**Non-descriptive wildcards**:</span></span>

  - \*
  - <span data-ttu-id="b7e65-364">\*.\*</span><span class="sxs-lookup"><span data-stu-id="b7e65-364">\*.\*</span></span>

- <span data-ttu-id="b7e65-365">**Mittlere Platzhalter:**</span><span class="sxs-lookup"><span data-stu-id="b7e65-365">**Middle wildcards**:</span></span>

  - <span data-ttu-id="b7e65-366">conto \* so.com</span><span class="sxs-lookup"><span data-stu-id="b7e65-366">conto\*so.com</span></span>
  - <span data-ttu-id="b7e65-367">conto~so.com</span><span class="sxs-lookup"><span data-stu-id="b7e65-367">conto~so.com</span></span>

- <span data-ttu-id="b7e65-368">**Doppelte Platzhalter**</span><span class="sxs-lookup"><span data-stu-id="b7e65-368">**Double wildcards**</span></span>

  - <span data-ttu-id="b7e65-369">contoso.com/\*\*</span><span class="sxs-lookup"><span data-stu-id="b7e65-369">contoso.com/\*\*</span></span>
  - <span data-ttu-id="b7e65-370">contoso.com/\*/\*</span><span class="sxs-lookup"><span data-stu-id="b7e65-370">contoso.com/\*/\*</span></span>
