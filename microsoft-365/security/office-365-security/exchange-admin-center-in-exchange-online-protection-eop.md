---
title: Exchange Admin Center in Exchange Online Protection
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 97921f0e-832f-40c7-b56d-414faede5191
ms.collection:
- M365-security-compliance
description: Die Exchange-Verwaltungskonsole (EAC) ist die webbasierte Verwaltungskonsole für Microsoft Exchange Online Protection (EOP).
ms.openlocfilehash: f38d36249387fce2ba3b4cac9e187c1cbcadd707
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42083272"
---
# <a name="exchange-admin-center-in-exchange-online-protection"></a><span data-ttu-id="479ce-103">Exchange Admin Center in Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="479ce-103">Exchange admin center in Exchange Online Protection</span></span>

<span data-ttu-id="479ce-104">Die Exchange-Verwaltungskonsole (EAC) ist die webbasierte Verwaltungskonsole für Microsoft Exchange Online Protection (EOP).</span><span class="sxs-lookup"><span data-stu-id="479ce-104">The Exchange admin center (EAC) is the web-based management console for Microsoft Exchange Online Protection (EOP).</span></span>

<span data-ttu-id="479ce-105">Suchen Sie die Exchange Server-Version dieses Themas?</span><span class="sxs-lookup"><span data-stu-id="479ce-105">Looking for the Exchange Server version of this topic?</span></span> <span data-ttu-id="479ce-106">Weitere Informationen finden Sie unter [Exchange Admin Center in Exchange Server](https://docs.microsoft.com/exchange/architecture/client-access/exchange-admin-center).</span><span class="sxs-lookup"><span data-stu-id="479ce-106">See [Exchange admin center in Exchange Server](https://docs.microsoft.com/exchange/architecture/client-access/exchange-admin-center).</span></span>

<span data-ttu-id="479ce-107">Suchen Sie die Exchange Online-Version dieses Themas?</span><span class="sxs-lookup"><span data-stu-id="479ce-107">Looking for the Exchange Online version of this topic?</span></span> <span data-ttu-id="479ce-108">Weitere Informationen finden Sie unter [Exchange admin center in Exchange Online](https://docs.microsoft.com/exchange/exchange-admin-center).</span><span class="sxs-lookup"><span data-stu-id="479ce-108">See [Exchange admin center in Exchange Online](https://docs.microsoft.com/exchange/exchange-admin-center).</span></span>

## <a name="accessing-the-eac"></a><span data-ttu-id="479ce-109">Zugreifen auf die Exchange-Verwaltungskonsole</span><span class="sxs-lookup"><span data-stu-id="479ce-109">Accessing the EAC</span></span>

<span data-ttu-id="479ce-110">In den meisten Fällen greifen EoP-Kunden über das Microsoft 365 Admin Center auf die Exchange-Verwaltungskonsole zu.</span><span class="sxs-lookup"><span data-stu-id="479ce-110">In most cases, EOP customers will access the EAC through the Microsoft 365 admin center.</span></span> <span data-ttu-id="479ce-111">Einen Link zu EOP finden Sie im Dropdownmenü der **Admin**-Kachel, die sich neben der **Ich**-Kachel befindet.</span><span class="sxs-lookup"><span data-stu-id="479ce-111">You can find a link to EOP in the drop-down menu in the **Admin** tile, which is next to the **Me** tile.</span></span> <span data-ttu-id="479ce-112">Klicken Sie auf die **Admin**-Kachel, und wählen Sie im Dropdownmenü **Exchange Online Protection**, um die Exchange-Verwaltungskonsole aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="479ce-112">Click the **Admin** tile and select **Exchange Online Protection** from the drop down menu to be taken to the EAC.</span></span>

<span data-ttu-id="479ce-p104">Sie können auch über den folgenden URL direkt auf das EAC-Zeichen auf der Seite zugreifen: `https://admin.protection.outlook.com/ecp/<companydomain>`. Beispiel: `https://admin.protection.outlook.com/ecp/contoso.onmicrosoft.com`. Nachdem Sie Ihre Benutzeranmeldeinformationen eingegeben haben, gelangen Sie direkt zur Exchange-Verwaltungskonsole.</span><span class="sxs-lookup"><span data-stu-id="479ce-p104">You can also access the EAC sign in page directly via the following URL: `https://admin.protection.outlook.com/ecp/<companydomain>`. For example, `https://admin.protection.outlook.com/ecp/contoso.onmicrosoft.com`. After specifying your user credentials you will be taken directly into the EAC.</span></span>

## <a name="common-user-interface-elements-in-the-eac"></a><span data-ttu-id="479ce-116">Allgemeine Elemente der Benutzeroberfläche in der Exchange-Verwaltungskonsole</span><span class="sxs-lookup"><span data-stu-id="479ce-116">Common user interface elements in the EAC</span></span>

<span data-ttu-id="479ce-117">In diesem Abschnitt werden die Elemente der Benutzeroberfläche der Exchange-Verwaltungskonsole beschrieben.</span><span class="sxs-lookup"><span data-stu-id="479ce-117">This section describes the user interface elements that are found in the EAC.</span></span>

![EoP-Admincenter](../../media/EOP-AdminCenter.png)

### <a name="feature-pane"></a><span data-ttu-id="479ce-119">Featurebereich</span><span class="sxs-lookup"><span data-stu-id="479ce-119">Feature Pane</span></span>

<span data-ttu-id="479ce-p105">Dies ist die erste Navigationsebene für die meisten Aufgaben, die Sie in der Exchange-Verwaltungskonsole ausführen. Der Featurebereich ist nach Funktionsbereichen organisiert.</span><span class="sxs-lookup"><span data-stu-id="479ce-p105">This is the first level of navigation for most of the tasks you'll perform in the EAC. The feature pane is organized by feature areas.</span></span>

1. <span data-ttu-id="479ce-122">**Recipients**: Dies ist der Ort, an dem Sie interne Benutzer und externe Kontakte anzeigen können.</span><span class="sxs-lookup"><span data-stu-id="479ce-122">**Recipients**: This is where you'll view internal users and external contacts.</span></span>

2. <span data-ttu-id="479ce-123">**Berechtigungen**: Hier können Sie Administratorrollen verwalten.</span><span class="sxs-lookup"><span data-stu-id="479ce-123">**Permissions**: This where you'll manage administrator roles.</span></span>

3. <span data-ttu-id="479ce-124">**Compliance-Verwaltung**: Hier finden Sie Überwachungsprotokolle und Berichte wie den Administrator-Rollengruppen Bericht.</span><span class="sxs-lookup"><span data-stu-id="479ce-124">**Compliance Management**: This is where you'll find audit logs and reports, such as the administrator role group report.</span></span>

4. <span data-ttu-id="479ce-125">**Schutz**: Hier können Sie Antischadsoftware-und Antispamschutz für Ihre Organisation sowie Nachrichten in Quarantäne verwalten.</span><span class="sxs-lookup"><span data-stu-id="479ce-125">**Protection**: This is where you'll manage anti-malware and anti-spam protection for your organization, as well as manage messages in quarantine.</span></span>

5. <span data-ttu-id="479ce-126">**Nachrichtenfluss**: Hier können Sie Regeln, akzeptierte Domänen und Connectors verwalten sowie die Nachrichtenablaufverfolgung durchführen.</span><span class="sxs-lookup"><span data-stu-id="479ce-126">**Mail Flow**: This is where you'll manage rules, accepted domains, and connectors, as well as where you'll go to perform message trace.</span></span>

### <a name="tabs"></a><span data-ttu-id="479ce-127">Registerkarten</span><span class="sxs-lookup"><span data-stu-id="479ce-127">Tabs</span></span>

<span data-ttu-id="479ce-128">Die Registerkarten sind Ihre zweite Ebene der Navigation.</span><span class="sxs-lookup"><span data-stu-id="479ce-128">The tabs are your second level of navigation.</span></span> <span data-ttu-id="479ce-129">Alle Featurebereiche enthalten verschiedene Registerkarten, die jeweils ein Feature repräsentieren.</span><span class="sxs-lookup"><span data-stu-id="479ce-129">Each of the feature areas contains various tabs, each representing a feature.</span></span>

### <a name="toolbar"></a><span data-ttu-id="479ce-130">Symbolleiste</span><span class="sxs-lookup"><span data-stu-id="479ce-130">Toolbar</span></span>

<span data-ttu-id="479ce-p107">Für die meisten Registerkarten wird eine Symbolleiste angezeigt, nachdem Sie auf sie geklickt haben. Die Symbolleiste enthält Symbole, die jeweils eine bestimmte Aktion auslösen. Die folgende Tabelle beschreibt die Symbole und deren Aktionen.</span><span class="sxs-lookup"><span data-stu-id="479ce-p107">When you click most tabs, you'll see a toolbar. The toolbar has icons that perform a specific action. The following table describes the icons and their actions.</span></span>

|<span data-ttu-id="479ce-134">**Symbol**</span><span class="sxs-lookup"><span data-stu-id="479ce-134">**Icon**</span></span>|<span data-ttu-id="479ce-135">**Name**</span><span class="sxs-lookup"><span data-stu-id="479ce-135">**Name**</span></span>|<span data-ttu-id="479ce-136">**Action**</span><span class="sxs-lookup"><span data-stu-id="479ce-136">**Action**</span></span>|
|:-----|:-----|:-----|
|![Hinzufügen (Symbol)](../../media/ITPro-EAC-AddIcon.gif)|<span data-ttu-id="479ce-138">Hinzufügen, Neu</span><span class="sxs-lookup"><span data-stu-id="479ce-138">Add, New</span></span>|<span data-ttu-id="479ce-p108">Über dieses Symbol können Sie ein neues Objekt erstellen. Bei einigen dieser Symbole gibt es einen dazugehörigen nach unten zeigenden Pfeil, auf den Sie klicken können, um weitere Objekte anzuzeigen, die Sie erstellen können.</span><span class="sxs-lookup"><span data-stu-id="479ce-p108">Use this icon to create a new object. Some of these icons have an associated down arrow you can click to show additional objects you can create.</span></span>|
|![Bearbeitungssymbol](../../media/ITPro-EAC-EditIcon.gif)|<span data-ttu-id="479ce-142">Bearbeiten</span><span class="sxs-lookup"><span data-stu-id="479ce-142">Edit</span></span>|<span data-ttu-id="479ce-143">Über dieses Symbol können Sie ein Objekt bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="479ce-143">Use this icon to edit an object.</span></span>|
|![Löschen (Symbol)](../../media/ITPro-EAC-DeleteIcon.gif)|<span data-ttu-id="479ce-145">Delete</span><span class="sxs-lookup"><span data-stu-id="479ce-145">Delete</span></span>|<span data-ttu-id="479ce-p109">Über dieses Symbol können Sie ein Objekt löschen. Bei einigen Löschsymbolen gibt es einen nach unten zeigenden Pfeil, auf den Sie zum Einblenden weiterer Optionen klicken können.</span><span class="sxs-lookup"><span data-stu-id="479ce-p109">Use this icon to delete an object. Some delete icons have a down arrow you can click to show additional options.</span></span>|
|![Suchen (Symbol)](../../media/ITPro-EAC-.gif)|<span data-ttu-id="479ce-149">Suche</span><span class="sxs-lookup"><span data-stu-id="479ce-149">Search</span></span>|<span data-ttu-id="479ce-150">Über dieses Symbol können Sie ein Suchfeld öffnen, in das Sie den Suchbegriff für ein zu suchendes Objekt eingeben können.</span><span class="sxs-lookup"><span data-stu-id="479ce-150">Use this icon to open a search box in which you can type the search phrase for an object you want to find.</span></span>|
|![Aktualisieren (Symbol)](../../media/ITPro-EAC-RefreshIcon.gif)|<span data-ttu-id="479ce-152">Aktualisieren</span><span class="sxs-lookup"><span data-stu-id="479ce-152">Refresh</span></span>|<span data-ttu-id="479ce-153">Über dieses Symbol können Sie die Listenansicht aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="479ce-153">Use this icon to refresh the list view.</span></span>|
|![Weitere Optionen (Symbol)](../../media/ITPro-EAC-MoreOptionsIcon.gif)|<span data-ttu-id="479ce-155">Weitere Optionen</span><span class="sxs-lookup"><span data-stu-id="479ce-155">More options</span></span>|<span data-ttu-id="479ce-p110">Über dieses Symbol können Sie mehrere Aktionen anzeigen, die Sie auf die Objekte dieser Registerkarte anwenden können. Wenn Sie z. B. unter **Empfänger \> Benutzer** auf dieses Symbol klicken, wird die Option **Erweiterte Suche** angezeigt.  </span><span class="sxs-lookup"><span data-stu-id="479ce-p110">Use this icon to view more actions you can perform for that tab's objects. For example, in **Recipients \> Users** clicking this icon shows the option to perform an **Advanced Search**.</span></span>|
|![NACH-OBEN-TASTE (Symbol)](../../media/ITPro-EAC-UpArrowIcon.gif)![NACH-UNTEN-TASTE (Symbol)](../../media/ITPro-EAC-DownArrowIcon.gif)|<span data-ttu-id="479ce-160">Pfeil nach oben und Pfeil nach unten</span><span class="sxs-lookup"><span data-stu-id="479ce-160">Up arrow and down arrow</span></span>|<span data-ttu-id="479ce-161">Mithilfe dieser Symbole können Sie die Priorität eines Objekts nach oben oder unten verschieben.</span><span class="sxs-lookup"><span data-stu-id="479ce-161">Use these icons to move an object's priority up or down.</span></span>|
|![Entfernen (Symbol)](../../media/ITPro-EAC-RemoveIcon.gif)|<span data-ttu-id="479ce-163">Entfernen</span><span class="sxs-lookup"><span data-stu-id="479ce-163">Remove</span></span>|<span data-ttu-id="479ce-164">Über dieses Symbol können Sie Objekte aus einer Liste entfernen.</span><span class="sxs-lookup"><span data-stu-id="479ce-164">Use this icon to remove objects from a list.</span></span>|

### <a name="list-view"></a><span data-ttu-id="479ce-165">Listenansicht</span><span class="sxs-lookup"><span data-stu-id="479ce-165">List View</span></span>

<span data-ttu-id="479ce-p111">Wenn Sie auf eine Registerkarte klicken, sehen Sie in den meisten Fällen eine Listenansicht. In der Listenansicht der Exchange-Verwaltungskonsole können ungefähr 10.000 Objekte angezeigt werden. Darüber hinaus können Sie die Ergebnisse seitenweise anzeigen.</span><span class="sxs-lookup"><span data-stu-id="479ce-p111">When you select a tab, in most cases you'll see a list view. The viewable limit with the EAC list view is approximately 10,000 objects. In addition, paging is included so that you can page to results.</span></span>

### <a name="details-pane"></a><span data-ttu-id="479ce-169">Bereich "Details"</span><span class="sxs-lookup"><span data-stu-id="479ce-169">Details Pane</span></span>

<span data-ttu-id="479ce-p112">Wenn Sie in der Listenansicht ein Objekt auswählen, werden Informationen zu diesem Objekt im Detailbereich angezeigt. In einigen Fällen enthält der Detailbereich Verwaltungsaufgaben.</span><span class="sxs-lookup"><span data-stu-id="479ce-p112">When you select an object from the list view, information about that object is displayed in the details pane. In some cases the details pane includes management tasks.</span></span>

### <a name="me-tile-and-help"></a><span data-ttu-id="479ce-172">Ich-Kachel und Hilfe</span><span class="sxs-lookup"><span data-stu-id="479ce-172">Me tile and Help</span></span>

<span data-ttu-id="479ce-p113">Über die **Ich**-Kachel können Sie sich bei der Exchange-Verwaltungskonsole abmelden und als ein anderer Benutzer anmelden. Über das Dropdownmenü der **Hilfe**![Hilfe (Symbol)](../../media/ITPro-EAC-HelpIcon.gif) können Sie folgende Aktionen ausführen:</span><span class="sxs-lookup"><span data-stu-id="479ce-p113">The **Me** tile allows you to sign out the EAC and sign in as a different user. From the **Help**![Help Icon](../../media/ITPro-EAC-HelpIcon.gif) drop-down menu, you can perform the following actions:</span></span>

1. <span data-ttu-id="479ce-175">**Hilfe**: Klicken ![Sie auf](../../media/ITPro-EAC-HelpIcon.gif) Hilfesymbol, um den Inhalt der Online Hilfe anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="479ce-175">**Help**: Click ![Help Icon](../../media/ITPro-EAC-HelpIcon.gif) to view the online help content.</span></span>

2. <span data-ttu-id="479ce-176">**Hilfe Blase deaktivieren**: in der Hilfe-Sprechblase wird Kontexthilfe für Felder angezeigt, wenn Sie ein Objekt erstellen oder bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="479ce-176">**Disable Help bubble**: The Help bubble displays contextual help for fields when you create or edit an object.</span></span> <span data-ttu-id="479ce-177">Sie können die Hilfe Blase deaktivieren oder aktivieren, wenn Sie deaktiviert wurde.</span><span class="sxs-lookup"><span data-stu-id="479ce-177">You can turn off the Help bubble or turn it on if it has been disabled.</span></span>

3. <span data-ttu-id="479ce-178">**Copyright**: Klicken Sie auf diesen Link, um den Copyright-Hinweis für Exchange Online Protection zu lesen.</span><span class="sxs-lookup"><span data-stu-id="479ce-178">**Copyright**: Click this link to read the copyright notice for Exchange Online Protection.</span></span>

4. <span data-ttu-id="479ce-179">**Privacy**: Klicken Sie hier, um die Datenschutzrichtlinie für Exchange Online Schutz zu lesen.</span><span class="sxs-lookup"><span data-stu-id="479ce-179">**Privacy**: Click to read the privacy policy for Exchange Online Protection.</span></span>

## <a name="supported-browsers"></a><span data-ttu-id="479ce-180">Unterstützte Browser</span><span class="sxs-lookup"><span data-stu-id="479ce-180">Supported Browsers</span></span>

<span data-ttu-id="479ce-181">Für eine optimale Nutzung des EAC sollten Sie immer die neuesten Browser, Office-Clients und Apps verwenden.</span><span class="sxs-lookup"><span data-stu-id="479ce-181">For the best experience using the EAC, we recommend that you always use the latest browsers, Office clients, and apps.</span></span> <span data-ttu-id="479ce-182">Zudem wird empfohlen, dass Sie Softwareupdates installieren, sobald sie verfügbar werden.</span><span class="sxs-lookup"><span data-stu-id="479ce-182">We also recommend that you install software updates when they become available.</span></span> <span data-ttu-id="479ce-183">Weitere Informationen zu den unterstützten Browsern und Systemanforderungen für den Dienst finden Sie unter [System Requirements for Office](https://products.office.com/office-system-requirements).</span><span class="sxs-lookup"><span data-stu-id="479ce-183">For more information about the supported browsers and system requirements for the service, see [System requirements for Office](https://products.office.com/office-system-requirements).</span></span>

## <a name="supported-languages-in-eop"></a><span data-ttu-id="479ce-184">Unterstützte Sprachen in EOP</span><span class="sxs-lookup"><span data-stu-id="479ce-184">Supported languages in EOP</span></span>

<span data-ttu-id="479ce-185">Die folgenden Sprachen werden für Exchange Online Protection unterstützt und zur Verfügung gestellt.</span><span class="sxs-lookup"><span data-stu-id="479ce-185">The following languages are supported and available for Exchange Online Protection.</span></span>

- <span data-ttu-id="479ce-186">Amharisch</span><span class="sxs-lookup"><span data-stu-id="479ce-186">Amharic</span></span>

- <span data-ttu-id="479ce-187">Arabisch</span><span class="sxs-lookup"><span data-stu-id="479ce-187">Arabic</span></span>

- <span data-ttu-id="479ce-188">Baskisch (Baskisch)</span><span class="sxs-lookup"><span data-stu-id="479ce-188">Basque (Basque)</span></span>

- <span data-ttu-id="479ce-189">Bengali (Indien)</span><span class="sxs-lookup"><span data-stu-id="479ce-189">Bengali (India)</span></span>

- <span data-ttu-id="479ce-190">Bulgarisch</span><span class="sxs-lookup"><span data-stu-id="479ce-190">Bulgarian</span></span>

- <span data-ttu-id="479ce-191">Katalanisch</span><span class="sxs-lookup"><span data-stu-id="479ce-191">Catalan</span></span>

- <span data-ttu-id="479ce-192">Chinesisch (vereinfacht)</span><span class="sxs-lookup"><span data-stu-id="479ce-192">Chinese (Simplified)</span></span>

- <span data-ttu-id="479ce-193">Chinesisch (traditionell)</span><span class="sxs-lookup"><span data-stu-id="479ce-193">Chinese (Traditional)</span></span>

- <span data-ttu-id="479ce-194">Kroatisch</span><span class="sxs-lookup"><span data-stu-id="479ce-194">Croatian</span></span>

- <span data-ttu-id="479ce-195">Tschechisch</span><span class="sxs-lookup"><span data-stu-id="479ce-195">Czech</span></span>

- <span data-ttu-id="479ce-196">Dänisch</span><span class="sxs-lookup"><span data-stu-id="479ce-196">Danish</span></span>

- <span data-ttu-id="479ce-197">Niederländisch</span><span class="sxs-lookup"><span data-stu-id="479ce-197">Dutch</span></span>

- <span data-ttu-id="479ce-198">Niederländisch</span><span class="sxs-lookup"><span data-stu-id="479ce-198">Dutch</span></span>

- <span data-ttu-id="479ce-199">Englisch</span><span class="sxs-lookup"><span data-stu-id="479ce-199">English</span></span>

- <span data-ttu-id="479ce-200">Estnisch</span><span class="sxs-lookup"><span data-stu-id="479ce-200">Estonian</span></span>

- <span data-ttu-id="479ce-201">Filipino (Philippinen)</span><span class="sxs-lookup"><span data-stu-id="479ce-201">Filipino (Philippines)</span></span>

- <span data-ttu-id="479ce-202">Finnisch</span><span class="sxs-lookup"><span data-stu-id="479ce-202">Finnish</span></span>

- <span data-ttu-id="479ce-203">Französisch</span><span class="sxs-lookup"><span data-stu-id="479ce-203">French</span></span>

- <span data-ttu-id="479ce-204">Galizisch</span><span class="sxs-lookup"><span data-stu-id="479ce-204">Galician</span></span>

- <span data-ttu-id="479ce-205">Deutsch</span><span class="sxs-lookup"><span data-stu-id="479ce-205">German</span></span>

- <span data-ttu-id="479ce-206">Griechisch</span><span class="sxs-lookup"><span data-stu-id="479ce-206">Greek</span></span>

- <span data-ttu-id="479ce-207">Gujarati</span><span class="sxs-lookup"><span data-stu-id="479ce-207">Gujarati</span></span>

- <span data-ttu-id="479ce-208">Hebräisch</span><span class="sxs-lookup"><span data-stu-id="479ce-208">Hebrew</span></span>

- <span data-ttu-id="479ce-209">Hindi</span><span class="sxs-lookup"><span data-stu-id="479ce-209">Hindi</span></span>

- <span data-ttu-id="479ce-210">Ungarisch</span><span class="sxs-lookup"><span data-stu-id="479ce-210">Hungarian</span></span>

- <span data-ttu-id="479ce-211">Isländisch</span><span class="sxs-lookup"><span data-stu-id="479ce-211">Icelandic</span></span>

- <span data-ttu-id="479ce-212">Indonesisch</span><span class="sxs-lookup"><span data-stu-id="479ce-212">Indonesian</span></span>

- <span data-ttu-id="479ce-213">Italienisch</span><span class="sxs-lookup"><span data-stu-id="479ce-213">Italian</span></span>

- <span data-ttu-id="479ce-214">Japanisch</span><span class="sxs-lookup"><span data-stu-id="479ce-214">Japanese</span></span>

- <span data-ttu-id="479ce-215">Kannada</span><span class="sxs-lookup"><span data-stu-id="479ce-215">Kannada</span></span>

- <span data-ttu-id="479ce-216">Kasachisch</span><span class="sxs-lookup"><span data-stu-id="479ce-216">Kazakh</span></span>

- <span data-ttu-id="479ce-217">Kisuaheli</span><span class="sxs-lookup"><span data-stu-id="479ce-217">Kiswahili</span></span>

- <span data-ttu-id="479ce-218">Koreanisch</span><span class="sxs-lookup"><span data-stu-id="479ce-218">Korean</span></span>

- <span data-ttu-id="479ce-219">Lettisch</span><span class="sxs-lookup"><span data-stu-id="479ce-219">Latvian</span></span>

- <span data-ttu-id="479ce-220">Litauisch</span><span class="sxs-lookup"><span data-stu-id="479ce-220">Lithuanian</span></span>

- <span data-ttu-id="479ce-221">Malaiisch (Brunei Darussalam)</span><span class="sxs-lookup"><span data-stu-id="479ce-221">Malay (Brunei Darussalam)</span></span>

- <span data-ttu-id="479ce-222">Malaiisch (Malaysia)</span><span class="sxs-lookup"><span data-stu-id="479ce-222">Malay (Malaysia)</span></span>

- <span data-ttu-id="479ce-223">Malayalam</span><span class="sxs-lookup"><span data-stu-id="479ce-223">Malayalam</span></span>

- <span data-ttu-id="479ce-224">Marathi</span><span class="sxs-lookup"><span data-stu-id="479ce-224">Marathi</span></span>

- <span data-ttu-id="479ce-225">Norwegisch (Bokmål)</span><span class="sxs-lookup"><span data-stu-id="479ce-225">Norwegian (Bokmål)</span></span>

- <span data-ttu-id="479ce-226">Norwegisch (Nynorsk)</span><span class="sxs-lookup"><span data-stu-id="479ce-226">Norwegian (Nynorsk)</span></span>

- <span data-ttu-id="479ce-227">Odia</span><span class="sxs-lookup"><span data-stu-id="479ce-227">Oriya</span></span>

- <span data-ttu-id="479ce-228">Persisch</span><span class="sxs-lookup"><span data-stu-id="479ce-228">Persian</span></span>

- <span data-ttu-id="479ce-229">Polnisch</span><span class="sxs-lookup"><span data-stu-id="479ce-229">Polish</span></span>

- <span data-ttu-id="479ce-230">Portugiesisch (Brasilien)</span><span class="sxs-lookup"><span data-stu-id="479ce-230">Portuguese (Brazil)</span></span>

- <span data-ttu-id="479ce-231">Portugiesisch (Portugal)</span><span class="sxs-lookup"><span data-stu-id="479ce-231">Portuguese (Portugal)</span></span>

- <span data-ttu-id="479ce-232">Rumänisch</span><span class="sxs-lookup"><span data-stu-id="479ce-232">Romanian</span></span>

- <span data-ttu-id="479ce-233">Russisch</span><span class="sxs-lookup"><span data-stu-id="479ce-233">Russian</span></span>

- <span data-ttu-id="479ce-234">Serbisch (Kyrillisch, Serbien)</span><span class="sxs-lookup"><span data-stu-id="479ce-234">Serbian (Cyrillic, Serbia)</span></span>

- <span data-ttu-id="479ce-235">Serbisch (Lateinisch)</span><span class="sxs-lookup"><span data-stu-id="479ce-235">Serbian (Latin)</span></span>

- <span data-ttu-id="479ce-236">Slowakisch</span><span class="sxs-lookup"><span data-stu-id="479ce-236">Slovak</span></span>

- <span data-ttu-id="479ce-237">Slowenisch</span><span class="sxs-lookup"><span data-stu-id="479ce-237">Slovenian</span></span>

- <span data-ttu-id="479ce-238">Spanisch</span><span class="sxs-lookup"><span data-stu-id="479ce-238">Spanish</span></span>

- <span data-ttu-id="479ce-239">Schwedisch</span><span class="sxs-lookup"><span data-stu-id="479ce-239">Swedish</span></span>

- <span data-ttu-id="479ce-240">Tamil</span><span class="sxs-lookup"><span data-stu-id="479ce-240">Tamil</span></span>

- <span data-ttu-id="479ce-241">Telugu</span><span class="sxs-lookup"><span data-stu-id="479ce-241">Telugu</span></span>

- <span data-ttu-id="479ce-242">Thailändisch</span><span class="sxs-lookup"><span data-stu-id="479ce-242">Thai</span></span>

- <span data-ttu-id="479ce-243">Türkisch</span><span class="sxs-lookup"><span data-stu-id="479ce-243">Turkish</span></span>

- <span data-ttu-id="479ce-244">Ukrainisch</span><span class="sxs-lookup"><span data-stu-id="479ce-244">Ukrainian</span></span>

- <span data-ttu-id="479ce-245">Urdu</span><span class="sxs-lookup"><span data-stu-id="479ce-245">Urdu</span></span>

- <span data-ttu-id="479ce-246">Vietnamesisch</span><span class="sxs-lookup"><span data-stu-id="479ce-246">Vietnamese</span></span>

- <span data-ttu-id="479ce-247">Walisisch</span><span class="sxs-lookup"><span data-stu-id="479ce-247">Welsh</span></span>


