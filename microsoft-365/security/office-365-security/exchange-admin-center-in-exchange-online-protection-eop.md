---
title: Exchange Admin Center in EOP als eigenständige Lösung
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
description: Erfahren Sie mehr über die Webverwaltungsoberfläche in eigenständigen Exchange Online Schutz (EoP).
ms.openlocfilehash: 777597489e54c642220cb42f0c686b675101897f
ms.sourcegitcommit: 73b2426001dc5a3f4b857366ef51e877db549098
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/09/2020
ms.locfileid: "44616998"
---
# <a name="exchange-admin-center-in-standalone-eop"></a><span data-ttu-id="7297e-103">Exchange Admin Center in EOP als eigenständige Lösung</span><span class="sxs-lookup"><span data-stu-id="7297e-103">Exchange admin center in standalone EOP</span></span>

<span data-ttu-id="7297e-104">Das Exchange Admin Center (EAC) ist eine webbasierte Verwaltungskonsole für eigenständige Exchange Online Schutz (EoP).</span><span class="sxs-lookup"><span data-stu-id="7297e-104">The Exchange admin center (EAC) is a web-based management console for standalone Exchange Online Protection (EOP).</span></span>

<span data-ttu-id="7297e-105">Suchen Sie die Exchange Online-Version dieses Themas?</span><span class="sxs-lookup"><span data-stu-id="7297e-105">Looking for the Exchange Online version of this topic?</span></span> <span data-ttu-id="7297e-106">Weitere Informationen finden Sie unter [Exchange admin center in Exchange Online](https://docs.microsoft.com/exchange/exchange-admin-center).</span><span class="sxs-lookup"><span data-stu-id="7297e-106">See [Exchange admin center in Exchange Online](https://docs.microsoft.com/exchange/exchange-admin-center).</span></span>

## <a name="open-the-eac-in-eop"></a><span data-ttu-id="7297e-107">Öffnen der Exchange-Verwaltungskonsole in EoP</span><span class="sxs-lookup"><span data-stu-id="7297e-107">Open the EAC in EOP</span></span>

<span data-ttu-id="7297e-108">Eigenständige EoP-Kunden können mithilfe der folgenden Methoden auf die Exchange-Verwaltungskonsole zugreifen:</span><span class="sxs-lookup"><span data-stu-id="7297e-108">Standalone EOP customers can access the EAC by using the following methods:</span></span>

- <span data-ttu-id="7297e-109">**Aus dem Microsoft 365 Admin Center**:</span><span class="sxs-lookup"><span data-stu-id="7297e-109">**From the Microsoft 365 admin center**:</span></span>

  1. <span data-ttu-id="7297e-110">Wechseln Sie zu, <https://admin.microsoft.com> und klicken Sie auf **Alle anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="7297e-110">Go to <https://admin.microsoft.com> and click **Show all**.</span></span>

     ![Klicken Sie im Microsoft 365 Admin Center auf alle anzeigen.](../../media/m365-center-show-all.png)

  2. <span data-ttu-id="7297e-112">Klicken Sie im angezeigten Abschnitt **Admin Centers** auf **alle Admin Center**.</span><span class="sxs-lookup"><span data-stu-id="7297e-112">In the **Admin centers** section that appears, click **All admin centers**.</span></span>

     ![Klicken Sie auf alle Admin Center im Microsoft 365 Admin Center](../../media/m365-center-select-all-admin-centers.png)

  3. <span data-ttu-id="7297e-114">Klicken Sie auf der Seite **alle Admin Center** , die angezeigt wird, auf **Exchange Online Schutz**.</span><span class="sxs-lookup"><span data-stu-id="7297e-114">On the **All admin centers** page that appears, click **Exchange Online Protection**.</span></span>

- <span data-ttu-id="7297e-115">Wechseln Sie direkt zu `https://admin.protection.outlook.com/ecp/` .</span><span class="sxs-lookup"><span data-stu-id="7297e-115">Go directly to `https://admin.protection.outlook.com/ecp/`.</span></span>

## <a name="common-user-interface-elements-in-the-eac-in-eop"></a><span data-ttu-id="7297e-116">Allgemeine Elemente der Benutzeroberfläche in der Exchange-Verwaltungskonsole in EoP</span><span class="sxs-lookup"><span data-stu-id="7297e-116">Common user interface elements in the EAC in EOP</span></span>

<span data-ttu-id="7297e-117">In diesem Abschnitt werden die Elemente der Benutzeroberfläche der Exchange-Verwaltungskonsole beschrieben.</span><span class="sxs-lookup"><span data-stu-id="7297e-117">This section describes the user interface elements that are found in the EAC.</span></span>

![EoP-Admincenter](../../media/EOP-AdminCenter.png)

### <a name="feature-pane"></a><span data-ttu-id="7297e-119">Featurebereich</span><span class="sxs-lookup"><span data-stu-id="7297e-119">Feature Pane</span></span>

<span data-ttu-id="7297e-p102">Dies ist die erste Navigationsebene für die meisten Aufgaben, die Sie in der Exchange-Verwaltungskonsole ausführen. Der Featurebereich ist nach Funktionsbereichen organisiert.</span><span class="sxs-lookup"><span data-stu-id="7297e-p102">This is the first level of navigation for most of the tasks you'll perform in the EAC. The feature pane is organized by feature areas.</span></span>

- <span data-ttu-id="7297e-122">**Recipients**: Hier werden Gruppen und externe Kontakte angezeigt.</span><span class="sxs-lookup"><span data-stu-id="7297e-122">**Recipients**: This is where you'll view groups and external contacts.</span></span>

- <span data-ttu-id="7297e-123">**Berechtigungen**: Hier können Sie Administratorrollen verwalten.</span><span class="sxs-lookup"><span data-stu-id="7297e-123">**Permissions**: This where you'll manage admin roles.</span></span>

- <span data-ttu-id="7297e-124">**Compliance-Verwaltung**: Hier finden Sie den Administrator-Rollengruppen Bericht und den Bericht admin-Überwachungsprotokoll.</span><span class="sxs-lookup"><span data-stu-id="7297e-124">**Compliance Management**: This is where you'll find the administrator role group report and the admin audit log report.</span></span>

- <span data-ttu-id="7297e-125">**Schutz**: Hier können Sie Antischadsoftware-Richtlinien, die standardmäßige Verbindungsfilter Richtlinie und DKIM verwalten.</span><span class="sxs-lookup"><span data-stu-id="7297e-125">**Protection**: This is where you can manage anti-malware policies, the default connection filter policy, and DKIM.</span></span>

  > [!NOTE]
  > <span data-ttu-id="7297e-126">Sie sollten Antischadsoftware-Richtlinien und die standardmäßige Verbindungsfilter Richtlinie im Security & Compliance Center verwalten.</span><span class="sxs-lookup"><span data-stu-id="7297e-126">You should manage anti-malware policies and the default connection filter policy in the Security & Compliance Center.</span></span> <span data-ttu-id="7297e-127">Weitere Informationen finden Sie unter [configure Anti-Malware Policies in EoP](configure-anti-malware-policies.md) und [Konfigurieren der Verbindungsfilterung in EoP](configure-the-connection-filter-policy.md).</span><span class="sxs-lookup"><span data-stu-id="7297e-127">For more information, see [Configure anti-malware policies in EOP](configure-anti-malware-policies.md) and [Configure connection filtering in EOP](configure-the-connection-filter-policy.md).</span></span>

- <span data-ttu-id="7297e-128">**Nachrichtenfluss**: Hier können Sie Nachrichtenfluss Regeln (auch bekannt als Transportregeln), akzeptierte Domänen und Connectors verwalten sowie den Weg zur Ausführung der Nachrichtenablaufverfolgung.</span><span class="sxs-lookup"><span data-stu-id="7297e-128">**Mail Flow**: This is where you'll manage mail flow rules (also known as transport rules), accepted domains, and connectors, as well as where you can go to run message trace.</span></span>

- <span data-ttu-id="7297e-129">**Hybrid**: Dies ist der Ort, an dem Sie den [Assistenten für die Hybrid Konfiguration](https://docs.microsoft.com/Exchange/hybrid-configuration-wizard)ausführen können und auf dem Sie das [Exchange Online-PowerShell-Modul](https://docs.microsoft.com/powershell/exchange/mfa-connect-to-exchange-online-powershell)installieren können.</span><span class="sxs-lookup"><span data-stu-id="7297e-129">**Hybrid**: This is where you can run the [Hybrid Configuration Wizard](https://docs.microsoft.com/Exchange/hybrid-configuration-wizard), and where you can install the [Exchange Online PowerShell module](https://docs.microsoft.com/powershell/exchange/mfa-connect-to-exchange-online-powershell).</span></span>

### <a name="tabs"></a><span data-ttu-id="7297e-130">Registerkarten</span><span class="sxs-lookup"><span data-stu-id="7297e-130">Tabs</span></span>

<span data-ttu-id="7297e-131">Die Registerkarten sind Ihre zweite Ebene der Navigation.</span><span class="sxs-lookup"><span data-stu-id="7297e-131">The tabs are your second level of navigation.</span></span> <span data-ttu-id="7297e-132">Alle Featurebereiche enthalten verschiedene Registerkarten, die jeweils ein Feature repräsentieren.</span><span class="sxs-lookup"><span data-stu-id="7297e-132">Each of the feature areas contains various tabs, each representing a feature.</span></span>

### <a name="toolbar"></a><span data-ttu-id="7297e-133">Symbolleiste</span><span class="sxs-lookup"><span data-stu-id="7297e-133">Toolbar</span></span>

<span data-ttu-id="7297e-p105">Für die meisten Registerkarten wird eine Symbolleiste angezeigt, nachdem Sie auf sie geklickt haben. Die Symbolleiste enthält Symbole, die jeweils eine bestimmte Aktion auslösen. Die folgende Tabelle beschreibt die Symbole und deren Aktionen.</span><span class="sxs-lookup"><span data-stu-id="7297e-p105">When you click most tabs, you'll see a toolbar. The toolbar has icons that perform a specific action. The following table describes the icons and their actions.</span></span>

||||
|---|---|---|
|<span data-ttu-id="7297e-137">**Symbol**</span><span class="sxs-lookup"><span data-stu-id="7297e-137">**Icon**</span></span>|<span data-ttu-id="7297e-138">**Name**</span><span class="sxs-lookup"><span data-stu-id="7297e-138">**Name**</span></span>|<span data-ttu-id="7297e-139">**Action**</span><span class="sxs-lookup"><span data-stu-id="7297e-139">**Action**</span></span>|
|![Hinzufügen (Symbol)](../../media/ITPro-EAC-AddIcon.gif)|<span data-ttu-id="7297e-141">Hinzufügen, Neu</span><span class="sxs-lookup"><span data-stu-id="7297e-141">Add, New</span></span>|<span data-ttu-id="7297e-p106">Über dieses Symbol können Sie ein neues Objekt erstellen. Bei einigen dieser Symbole gibt es einen dazugehörigen nach unten zeigenden Pfeil, auf den Sie klicken können, um weitere Objekte anzuzeigen, die Sie erstellen können.</span><span class="sxs-lookup"><span data-stu-id="7297e-p106">Use this icon to create a new object. Some of these icons have an associated down arrow you can click to show additional objects you can create.</span></span>|
|![Bearbeitungssymbol](../../media/ITPro-EAC-EditIcon.gif)|<span data-ttu-id="7297e-145">Bearbeiten</span><span class="sxs-lookup"><span data-stu-id="7297e-145">Edit</span></span>|<span data-ttu-id="7297e-146">Über dieses Symbol können Sie ein Objekt bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="7297e-146">Use this icon to edit an object.</span></span>|
|![Löschen (Symbol)](../../media/ITPro-EAC-DeleteIcon.gif)|<span data-ttu-id="7297e-148">Delete</span><span class="sxs-lookup"><span data-stu-id="7297e-148">Delete</span></span>|<span data-ttu-id="7297e-p107">Über dieses Symbol können Sie ein Objekt löschen. Bei einigen Löschsymbolen gibt es einen nach unten zeigenden Pfeil, auf den Sie zum Einblenden weiterer Optionen klicken können.</span><span class="sxs-lookup"><span data-stu-id="7297e-p107">Use this icon to delete an object. Some delete icons have a down arrow you can click to show additional options.</span></span>|
|![Suchen (Symbol)](../../media/ITPro-EAC-.gif)|<span data-ttu-id="7297e-152">Suche</span><span class="sxs-lookup"><span data-stu-id="7297e-152">Search</span></span>|<span data-ttu-id="7297e-153">Über dieses Symbol können Sie ein Suchfeld öffnen, in das Sie den Suchbegriff für ein zu suchendes Objekt eingeben können.</span><span class="sxs-lookup"><span data-stu-id="7297e-153">Use this icon to open a search box in which you can type the search phrase for an object you want to find.</span></span>|
|![Aktualisieren (Symbol)](../../media/ITPro-EAC-RefreshIcon.gif)|<span data-ttu-id="7297e-155">Aktualisieren</span><span class="sxs-lookup"><span data-stu-id="7297e-155">Refresh</span></span>|<span data-ttu-id="7297e-156">Über dieses Symbol können Sie die Listenansicht aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="7297e-156">Use this icon to refresh the list view.</span></span>|
|![Weitere Optionen (Symbol)](../../media/ITPro-EAC-MoreOptionsIcon.gif)|<span data-ttu-id="7297e-158">Weitere Optionen</span><span class="sxs-lookup"><span data-stu-id="7297e-158">More options</span></span>|<span data-ttu-id="7297e-p108">Über dieses Symbol können Sie mehrere Aktionen anzeigen, die Sie auf die Objekte dieser Registerkarte anwenden können. Wenn Sie z. B. unter **Empfänger \> Benutzer** auf dieses Symbol klicken, wird die Option **Erweiterte Suche** angezeigt.  </span><span class="sxs-lookup"><span data-stu-id="7297e-p108">Use this icon to view more actions you can perform for that tab's objects. For example, in **Recipients \> Users** clicking this icon shows the option to perform an **Advanced Search**.</span></span>|
|![NACH-OBEN-TASTE (Symbol)](../../media/ITPro-EAC-UpArrowIcon.gif)![NACH-UNTEN-TASTE (Symbol)](../../media/ITPro-EAC-DownArrowIcon.gif)|<span data-ttu-id="7297e-163">Pfeil nach oben und Pfeil nach unten</span><span class="sxs-lookup"><span data-stu-id="7297e-163">Up arrow and down arrow</span></span>|<span data-ttu-id="7297e-164">Mithilfe dieser Symbole können Sie die Priorität eines Objekts nach oben oder unten verschieben.</span><span class="sxs-lookup"><span data-stu-id="7297e-164">Use these icons to move an object's priority up or down.</span></span>|
|![Entfernen (Symbol)](../../media/ITPro-EAC-RemoveIcon.gif)|<span data-ttu-id="7297e-166">Entfernen</span><span class="sxs-lookup"><span data-stu-id="7297e-166">Remove</span></span>|<span data-ttu-id="7297e-167">Über dieses Symbol können Sie Objekte aus einer Liste entfernen.</span><span class="sxs-lookup"><span data-stu-id="7297e-167">Use this icon to remove objects from a list.</span></span>|
|

### <a name="list-view"></a><span data-ttu-id="7297e-168">Listenansicht</span><span class="sxs-lookup"><span data-stu-id="7297e-168">List View</span></span>

<span data-ttu-id="7297e-p109">Wenn Sie auf eine Registerkarte klicken, sehen Sie in den meisten Fällen eine Listenansicht. In der Listenansicht der Exchange-Verwaltungskonsole können ungefähr 10.000 Objekte angezeigt werden. Darüber hinaus können Sie die Ergebnisse seitenweise anzeigen.</span><span class="sxs-lookup"><span data-stu-id="7297e-p109">When you select a tab, in most cases you'll see a list view. The viewable limit with the EAC list view is approximately 10,000 objects. In addition, paging is included so that you can page to results.</span></span>

### <a name="details-pane"></a><span data-ttu-id="7297e-172">Bereich "Details"</span><span class="sxs-lookup"><span data-stu-id="7297e-172">Details Pane</span></span>

<span data-ttu-id="7297e-p110">Wenn Sie in der Listenansicht ein Objekt auswählen, werden Informationen zu diesem Objekt im Detailbereich angezeigt. In einigen Fällen enthält der Detailbereich Verwaltungsaufgaben.</span><span class="sxs-lookup"><span data-stu-id="7297e-p110">When you select an object from the list view, information about that object is displayed in the details pane. In some cases the details pane includes management tasks.</span></span>

### <a name="me-tile-and-help"></a><span data-ttu-id="7297e-175">Ich-Kachel und Hilfe</span><span class="sxs-lookup"><span data-stu-id="7297e-175">Me tile and Help</span></span>

<span data-ttu-id="7297e-p111">Über die **Ich**-Kachel können Sie sich bei der Exchange-Verwaltungskonsole abmelden und als ein anderer Benutzer anmelden. Über das Dropdownmenü der **Hilfe**![Hilfe (Symbol)](../../media/ITPro-EAC-HelpIcon.gif) können Sie folgende Aktionen ausführen:</span><span class="sxs-lookup"><span data-stu-id="7297e-p111">The **Me** tile allows you to sign out the EAC and sign in as a different user. From the **Help**![Help Icon](../../media/ITPro-EAC-HelpIcon.gif) drop-down menu, you can perform the following actions:</span></span>

- <span data-ttu-id="7297e-178">**Hilfe**: Klicken Sie auf ![ Hilfesymbol ](../../media/ITPro-EAC-HelpIcon.gif) , um den Inhalt der Online Hilfe anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="7297e-178">**Help**: Click ![Help Icon](../../media/ITPro-EAC-HelpIcon.gif) to view the online help content.</span></span>

- <span data-ttu-id="7297e-179">**Feedback**: hinterlassen Sie Feedback.</span><span class="sxs-lookup"><span data-stu-id="7297e-179">**Feedback**: Leave feedback.</span></span>

- <span data-ttu-id="7297e-180">**Community**: Stellen Sie eine Frage für Find Answers in den Community-Foren bereit.</span><span class="sxs-lookup"><span data-stu-id="7297e-180">**Community**: Post a question for find answers in the community forums.</span></span>

- <span data-ttu-id="7297e-181">**Hilfe Blase deaktivieren**: in der Hilfe-Sprechblase wird Kontexthilfe für Felder angezeigt, wenn Sie ein Objekt erstellen oder bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="7297e-181">**Disable Help bubble**: The Help bubble displays contextual help for fields when you create or edit an object.</span></span> <span data-ttu-id="7297e-182">Sie können die Hilfe Blase deaktivieren oder aktivieren, wenn Sie deaktiviert wurde.</span><span class="sxs-lookup"><span data-stu-id="7297e-182">You can turn off the Help bubble or turn it on if it has been disabled.</span></span>

- <span data-ttu-id="7297e-183">**Befehlsprotokollierung anzeigen**: Es wird ein neues Fenster geöffnet, in dem die entsprechenden PowerShell-Befehle basierend auf den in der Exchange-Verwaltungskonsole konfigurierten angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="7297e-183">**Show Command Logging**: A new window opens that shows the equivalent PowerShell commands based on what you configured in EAC.</span></span>

## <a name="supported-browsers"></a><span data-ttu-id="7297e-184">Unterstützte Browser</span><span class="sxs-lookup"><span data-stu-id="7297e-184">Supported Browsers</span></span>

<span data-ttu-id="7297e-185">Für eine optimale Nutzung des EAC sollten Sie immer die neuesten Browser, Office-Clients und Apps verwenden.</span><span class="sxs-lookup"><span data-stu-id="7297e-185">For the best experience using the EAC, we recommend that you always use the latest browsers, Office clients, and apps.</span></span> <span data-ttu-id="7297e-186">Zudem wird empfohlen, dass Sie Softwareupdates installieren, sobald sie verfügbar werden.</span><span class="sxs-lookup"><span data-stu-id="7297e-186">We also recommend that you install software updates when they become available.</span></span> <span data-ttu-id="7297e-187">Weitere Informationen zu den unterstützten Browsern und Systemanforderungen für den Dienst finden Sie unter [System Requirements for Office](https://products.office.com/office-system-requirements).</span><span class="sxs-lookup"><span data-stu-id="7297e-187">For more information about the supported browsers and system requirements for the service, see [System requirements for Office](https://products.office.com/office-system-requirements).</span></span>

## <a name="supported-languages"></a><span data-ttu-id="7297e-188">Unterstützte Sprachen</span><span class="sxs-lookup"><span data-stu-id="7297e-188">Supported languages</span></span>

<span data-ttu-id="7297e-189">Die folgenden Sprachen werden für die Exchange-Verwaltungskonsole in eigenständigen EoP unterstützt und zur Verfügung gestellt.</span><span class="sxs-lookup"><span data-stu-id="7297e-189">The following languages are supported and available for the EAC in standalone EOP.</span></span>

- <span data-ttu-id="7297e-190">Amharisch</span><span class="sxs-lookup"><span data-stu-id="7297e-190">Amharic</span></span>

- <span data-ttu-id="7297e-191">Arabisch</span><span class="sxs-lookup"><span data-stu-id="7297e-191">Arabic</span></span>

- <span data-ttu-id="7297e-192">Baskisch (Baskisch)</span><span class="sxs-lookup"><span data-stu-id="7297e-192">Basque (Basque)</span></span>

- <span data-ttu-id="7297e-193">Bengali (Indien)</span><span class="sxs-lookup"><span data-stu-id="7297e-193">Bengali (India)</span></span>

- <span data-ttu-id="7297e-194">Bulgarisch</span><span class="sxs-lookup"><span data-stu-id="7297e-194">Bulgarian</span></span>

- <span data-ttu-id="7297e-195">Katalanisch</span><span class="sxs-lookup"><span data-stu-id="7297e-195">Catalan</span></span>

- <span data-ttu-id="7297e-196">Chinesisch (vereinfacht)</span><span class="sxs-lookup"><span data-stu-id="7297e-196">Chinese (Simplified)</span></span>

- <span data-ttu-id="7297e-197">Chinesisch (traditionell)</span><span class="sxs-lookup"><span data-stu-id="7297e-197">Chinese (Traditional)</span></span>

- <span data-ttu-id="7297e-198">Kroatisch</span><span class="sxs-lookup"><span data-stu-id="7297e-198">Croatian</span></span>

- <span data-ttu-id="7297e-199">Tschechisch</span><span class="sxs-lookup"><span data-stu-id="7297e-199">Czech</span></span>

- <span data-ttu-id="7297e-200">Dänisch</span><span class="sxs-lookup"><span data-stu-id="7297e-200">Danish</span></span>

- <span data-ttu-id="7297e-201">Niederländisch</span><span class="sxs-lookup"><span data-stu-id="7297e-201">Dutch</span></span>

- <span data-ttu-id="7297e-202">Niederländisch</span><span class="sxs-lookup"><span data-stu-id="7297e-202">Dutch</span></span>

- <span data-ttu-id="7297e-203">Englisch</span><span class="sxs-lookup"><span data-stu-id="7297e-203">English</span></span>

- <span data-ttu-id="7297e-204">Estnisch</span><span class="sxs-lookup"><span data-stu-id="7297e-204">Estonian</span></span>

- <span data-ttu-id="7297e-205">Filipino (Philippinen)</span><span class="sxs-lookup"><span data-stu-id="7297e-205">Filipino (Philippines)</span></span>

- <span data-ttu-id="7297e-206">Finnisch</span><span class="sxs-lookup"><span data-stu-id="7297e-206">Finnish</span></span>

- <span data-ttu-id="7297e-207">Französisch</span><span class="sxs-lookup"><span data-stu-id="7297e-207">French</span></span>

- <span data-ttu-id="7297e-208">Galizisch</span><span class="sxs-lookup"><span data-stu-id="7297e-208">Galician</span></span>

- <span data-ttu-id="7297e-209">Deutsch</span><span class="sxs-lookup"><span data-stu-id="7297e-209">German</span></span>

- <span data-ttu-id="7297e-210">Griechisch</span><span class="sxs-lookup"><span data-stu-id="7297e-210">Greek</span></span>

- <span data-ttu-id="7297e-211">Gujarati</span><span class="sxs-lookup"><span data-stu-id="7297e-211">Gujarati</span></span>

- <span data-ttu-id="7297e-212">Hebräisch</span><span class="sxs-lookup"><span data-stu-id="7297e-212">Hebrew</span></span>

- <span data-ttu-id="7297e-213">Hindi</span><span class="sxs-lookup"><span data-stu-id="7297e-213">Hindi</span></span>

- <span data-ttu-id="7297e-214">Ungarisch</span><span class="sxs-lookup"><span data-stu-id="7297e-214">Hungarian</span></span>

- <span data-ttu-id="7297e-215">Isländisch</span><span class="sxs-lookup"><span data-stu-id="7297e-215">Icelandic</span></span>

- <span data-ttu-id="7297e-216">Indonesisch</span><span class="sxs-lookup"><span data-stu-id="7297e-216">Indonesian</span></span>

- <span data-ttu-id="7297e-217">Italienisch</span><span class="sxs-lookup"><span data-stu-id="7297e-217">Italian</span></span>

- <span data-ttu-id="7297e-218">Japanisch</span><span class="sxs-lookup"><span data-stu-id="7297e-218">Japanese</span></span>

- <span data-ttu-id="7297e-219">Kannada</span><span class="sxs-lookup"><span data-stu-id="7297e-219">Kannada</span></span>

- <span data-ttu-id="7297e-220">Kasachisch</span><span class="sxs-lookup"><span data-stu-id="7297e-220">Kazakh</span></span>

- <span data-ttu-id="7297e-221">Kisuaheli</span><span class="sxs-lookup"><span data-stu-id="7297e-221">Kiswahili</span></span>

- <span data-ttu-id="7297e-222">Koreanisch</span><span class="sxs-lookup"><span data-stu-id="7297e-222">Korean</span></span>

- <span data-ttu-id="7297e-223">Lettisch</span><span class="sxs-lookup"><span data-stu-id="7297e-223">Latvian</span></span>

- <span data-ttu-id="7297e-224">Litauisch</span><span class="sxs-lookup"><span data-stu-id="7297e-224">Lithuanian</span></span>

- <span data-ttu-id="7297e-225">Malaiisch (Brunei Darussalam)</span><span class="sxs-lookup"><span data-stu-id="7297e-225">Malay (Brunei Darussalam)</span></span>

- <span data-ttu-id="7297e-226">Malaiisch (Malaysia)</span><span class="sxs-lookup"><span data-stu-id="7297e-226">Malay (Malaysia)</span></span>

- <span data-ttu-id="7297e-227">Malayalam</span><span class="sxs-lookup"><span data-stu-id="7297e-227">Malayalam</span></span>

- <span data-ttu-id="7297e-228">Marathi</span><span class="sxs-lookup"><span data-stu-id="7297e-228">Marathi</span></span>

- <span data-ttu-id="7297e-229">Norwegisch (Bokmål)</span><span class="sxs-lookup"><span data-stu-id="7297e-229">Norwegian (Bokmål)</span></span>

- <span data-ttu-id="7297e-230">Norwegisch (Nynorsk)</span><span class="sxs-lookup"><span data-stu-id="7297e-230">Norwegian (Nynorsk)</span></span>

- <span data-ttu-id="7297e-231">Odia</span><span class="sxs-lookup"><span data-stu-id="7297e-231">Oriya</span></span>

- <span data-ttu-id="7297e-232">Persisch</span><span class="sxs-lookup"><span data-stu-id="7297e-232">Persian</span></span>

- <span data-ttu-id="7297e-233">Polnisch</span><span class="sxs-lookup"><span data-stu-id="7297e-233">Polish</span></span>

- <span data-ttu-id="7297e-234">Portugiesisch (Brasilien)</span><span class="sxs-lookup"><span data-stu-id="7297e-234">Portuguese (Brazil)</span></span>

- <span data-ttu-id="7297e-235">Portugiesisch (Portugal)</span><span class="sxs-lookup"><span data-stu-id="7297e-235">Portuguese (Portugal)</span></span>

- <span data-ttu-id="7297e-236">Rumänisch</span><span class="sxs-lookup"><span data-stu-id="7297e-236">Romanian</span></span>

- <span data-ttu-id="7297e-237">Russisch</span><span class="sxs-lookup"><span data-stu-id="7297e-237">Russian</span></span>

- <span data-ttu-id="7297e-238">Serbisch (Kyrillisch, Serbien)</span><span class="sxs-lookup"><span data-stu-id="7297e-238">Serbian (Cyrillic, Serbia)</span></span>

- <span data-ttu-id="7297e-239">Serbisch (Lateinisch)</span><span class="sxs-lookup"><span data-stu-id="7297e-239">Serbian (Latin)</span></span>

- <span data-ttu-id="7297e-240">Slowakisch</span><span class="sxs-lookup"><span data-stu-id="7297e-240">Slovak</span></span>

- <span data-ttu-id="7297e-241">Slowenisch</span><span class="sxs-lookup"><span data-stu-id="7297e-241">Slovenian</span></span>

- <span data-ttu-id="7297e-242">Spanisch</span><span class="sxs-lookup"><span data-stu-id="7297e-242">Spanish</span></span>

- <span data-ttu-id="7297e-243">Schwedisch</span><span class="sxs-lookup"><span data-stu-id="7297e-243">Swedish</span></span>

- <span data-ttu-id="7297e-244">Tamil</span><span class="sxs-lookup"><span data-stu-id="7297e-244">Tamil</span></span>

- <span data-ttu-id="7297e-245">Telugu</span><span class="sxs-lookup"><span data-stu-id="7297e-245">Telugu</span></span>

- <span data-ttu-id="7297e-246">Thailändisch</span><span class="sxs-lookup"><span data-stu-id="7297e-246">Thai</span></span>

- <span data-ttu-id="7297e-247">Türkisch</span><span class="sxs-lookup"><span data-stu-id="7297e-247">Turkish</span></span>

- <span data-ttu-id="7297e-248">Ukrainisch</span><span class="sxs-lookup"><span data-stu-id="7297e-248">Ukrainian</span></span>

- <span data-ttu-id="7297e-249">Urdu</span><span class="sxs-lookup"><span data-stu-id="7297e-249">Urdu</span></span>

- <span data-ttu-id="7297e-250">Vietnamesisch</span><span class="sxs-lookup"><span data-stu-id="7297e-250">Vietnamese</span></span>

- <span data-ttu-id="7297e-251">Walisisch</span><span class="sxs-lookup"><span data-stu-id="7297e-251">Welsh</span></span>
