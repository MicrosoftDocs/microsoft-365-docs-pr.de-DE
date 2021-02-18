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
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 97921f0e-832f-40c7-b56d-414faede5191
ms.collection:
- M365-security-compliance
description: Erfahren Sie mehr über die Webverwaltungsschnittstelle in eigenständigem Exchange Online Protection (EOP).
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: ec9dcbccbee734ea7c475b1ac0a5f9a92a0b401b
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/18/2021
ms.locfileid: "50286957"
---
# <a name="exchange-admin-center-in-standalone-eop"></a><span data-ttu-id="8ca2c-103">Exchange Admin Center in EOP als eigenständige Lösung</span><span class="sxs-lookup"><span data-stu-id="8ca2c-103">Exchange admin center in standalone EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="8ca2c-104">**Gilt für**</span><span class="sxs-lookup"><span data-stu-id="8ca2c-104">**Applies to**</span></span>
-  [<span data-ttu-id="8ca2c-105">Exchange Online Protection als eigenständige Lösung</span><span class="sxs-lookup"><span data-stu-id="8ca2c-105">Exchange Online Protection standalone</span></span>](exchange-online-protection-overview.md)

<span data-ttu-id="8ca2c-106">Die Exchange Admin Center (EAC) ist eine webbasierte Verwaltungskonsole für eigenständige Exchange Online Protection (EOP).</span><span class="sxs-lookup"><span data-stu-id="8ca2c-106">The Exchange admin center (EAC) is a web-based management console for standalone Exchange Online Protection (EOP).</span></span>

<span data-ttu-id="8ca2c-107">Suchen Sie die Exchange Online-Version dieses Themas?</span><span class="sxs-lookup"><span data-stu-id="8ca2c-107">Looking for the Exchange Online version of this topic?</span></span> <span data-ttu-id="8ca2c-108">Weitere Informationen finden Sie unter [Exchange admin center in Exchange Online](https://docs.microsoft.com/exchange/exchange-admin-center).</span><span class="sxs-lookup"><span data-stu-id="8ca2c-108">See [Exchange admin center in Exchange Online](https://docs.microsoft.com/exchange/exchange-admin-center).</span></span>

## <a name="open-the-eac-in-eop"></a><span data-ttu-id="8ca2c-109">Öffnen der EAC in EOP</span><span class="sxs-lookup"><span data-stu-id="8ca2c-109">Open the EAC in EOP</span></span>

<span data-ttu-id="8ca2c-110">Kunden von eigenständigem EOP können mithilfe der folgenden Methoden auf die EAC zugreifen:</span><span class="sxs-lookup"><span data-stu-id="8ca2c-110">Standalone EOP customers can access the EAC by using the following methods:</span></span>

- <span data-ttu-id="8ca2c-111">**Aus dem Microsoft 365 Admin Center:**</span><span class="sxs-lookup"><span data-stu-id="8ca2c-111">**From the Microsoft 365 admin center**:</span></span>

  1. <span data-ttu-id="8ca2c-112">Wechseln Sie zu <https://admin.microsoft.com> , und klicken Sie auf **"Alle anzeigen".**</span><span class="sxs-lookup"><span data-stu-id="8ca2c-112">Go to <https://admin.microsoft.com> and click **Show all**.</span></span>

     ![Klicken Sie im Microsoft 365 Admin Center auf "Alle anzeigen"](../../media/m365-center-show-all.png)

  2. <span data-ttu-id="8ca2c-114">Klicken Sie im angezeigten Abschnitt **"Admin Center"** auf **"Alle Admin Center".**</span><span class="sxs-lookup"><span data-stu-id="8ca2c-114">In the **Admin centers** section that appears, click **All admin centers**.</span></span>

     ![Klicken Sie im Microsoft 365 Admin Center auf "Alle Admin Center".](../../media/m365-center-select-all-admin-centers.png)

  3. <span data-ttu-id="8ca2c-116">Klicken Sie **auf der angezeigten** Seite "Alle Admin Center" auf **Exchange Online Protection**.</span><span class="sxs-lookup"><span data-stu-id="8ca2c-116">On the **All admin centers** page that appears, click **Exchange Online Protection**.</span></span>

- <span data-ttu-id="8ca2c-117">Wechseln Sie direkt zu `https://admin.protection.outlook.com/ecp/` .</span><span class="sxs-lookup"><span data-stu-id="8ca2c-117">Go directly to `https://admin.protection.outlook.com/ecp/`.</span></span>

## <a name="common-user-interface-elements-in-the-eac-in-eop"></a><span data-ttu-id="8ca2c-118">Allgemeine Benutzeroberflächenelemente in der EAC in EOP</span><span class="sxs-lookup"><span data-stu-id="8ca2c-118">Common user interface elements in the EAC in EOP</span></span>

<span data-ttu-id="8ca2c-119">In diesem Abschnitt werden die Elemente der Benutzeroberfläche der Exchange-Verwaltungskonsole beschrieben.</span><span class="sxs-lookup"><span data-stu-id="8ca2c-119">This section describes the user interface elements that are found in the EAC.</span></span>

![Das Exchange Admin Center in Exchange Online Protection](../../media/EOP-AdminCenter.png)

### <a name="feature-pane"></a><span data-ttu-id="8ca2c-121">Featurebereich</span><span class="sxs-lookup"><span data-stu-id="8ca2c-121">Feature Pane</span></span>

<span data-ttu-id="8ca2c-p102">Dies ist die erste Navigationsebene für die meisten Aufgaben, die Sie in der Exchange-Verwaltungskonsole ausführen. Der Featurebereich ist nach Funktionsbereichen organisiert.</span><span class="sxs-lookup"><span data-stu-id="8ca2c-p102">This is the first level of navigation for most of the tasks you'll perform in the EAC. The feature pane is organized by feature areas.</span></span>

- <span data-ttu-id="8ca2c-124">**Empfänger:** Hier werden Gruppen und externe Kontakte angezeigt.</span><span class="sxs-lookup"><span data-stu-id="8ca2c-124">**Recipients**: This is where you'll view groups and external contacts.</span></span>

- <span data-ttu-id="8ca2c-125">**Berechtigungen:** Hier verwalten Sie Administratorrollen.</span><span class="sxs-lookup"><span data-stu-id="8ca2c-125">**Permissions**: This where you'll manage admin roles.</span></span>

- <span data-ttu-id="8ca2c-126">**Verwaltung der** Richtlinienkonformität: Hier finden Sie den Administrator-Rollengruppenbericht und den Administrator-Überwachungsprotokollbericht.</span><span class="sxs-lookup"><span data-stu-id="8ca2c-126">**Compliance Management**: This is where you'll find the administrator role group report and the admin audit log report.</span></span>

- <span data-ttu-id="8ca2c-127">**Schutz:** Hier können Sie An malware-Richtlinien, die Standardrichtlinie für Verbindungsfilter und DKIM verwalten.</span><span class="sxs-lookup"><span data-stu-id="8ca2c-127">**Protection**: This is where you can manage anti-malware policies, the default connection filter policy, and DKIM.</span></span>

  > [!NOTE]
  > <span data-ttu-id="8ca2c-128">Im Security & Compliance Center sollten Sie Ansoftwarerichtlinien und die Standardrichtlinie für Verbindungsfilter verwalten.</span><span class="sxs-lookup"><span data-stu-id="8ca2c-128">You should manage anti-malware policies and the default connection filter policy in the Security & Compliance Center.</span></span> <span data-ttu-id="8ca2c-129">Weitere Informationen finden Sie unter [Configure anti-malware policies in EOP](configure-anti-malware-policies.md) and [Configure connection filtering in EOP](configure-the-connection-filter-policy.md).</span><span class="sxs-lookup"><span data-stu-id="8ca2c-129">For more information, see [Configure anti-malware policies in EOP](configure-anti-malware-policies.md) and [Configure connection filtering in EOP](configure-the-connection-filter-policy.md).</span></span>

- <span data-ttu-id="8ca2c-130">**Nachrichtenfluss:** Hier verwalten Sie Nachrichtenflussregeln (auch als Transportregeln bezeichnet), akzeptierte Domänen und Connectors sowie die Nachrichtenablaufverfolgung.</span><span class="sxs-lookup"><span data-stu-id="8ca2c-130">**Mail Flow**: This is where you'll manage mail flow rules (also known as transport rules), accepted domains, and connectors, as well as where you can go to run message trace.</span></span>

- <span data-ttu-id="8ca2c-131">**Hybrid:** Hier können Sie den Assistenten für [die Hybridkonfiguration](https://docs.microsoft.com/Exchange/hybrid-configuration-wizard)ausführen und das [Exchange Online -PowerShell-Modul installieren.](https://docs.microsoft.com/powershell/exchange/mfa-connect-to-exchange-online-powershell)</span><span class="sxs-lookup"><span data-stu-id="8ca2c-131">**Hybrid**: This is where you can run the [Hybrid Configuration Wizard](https://docs.microsoft.com/Exchange/hybrid-configuration-wizard), and where you can install the [Exchange Online PowerShell module](https://docs.microsoft.com/powershell/exchange/mfa-connect-to-exchange-online-powershell).</span></span>

### <a name="tabs"></a><span data-ttu-id="8ca2c-132">Registerkarten</span><span class="sxs-lookup"><span data-stu-id="8ca2c-132">Tabs</span></span>

<span data-ttu-id="8ca2c-133">Die Registerkarten sind Ihre zweite Ebene der Navigation.</span><span class="sxs-lookup"><span data-stu-id="8ca2c-133">The tabs are your second level of navigation.</span></span> <span data-ttu-id="8ca2c-134">Alle Featurebereiche enthalten verschiedene Registerkarten, die jeweils ein Feature repräsentieren.</span><span class="sxs-lookup"><span data-stu-id="8ca2c-134">Each of the feature areas contains various tabs, each representing a feature.</span></span>

### <a name="toolbar"></a><span data-ttu-id="8ca2c-135">Symbolleiste</span><span class="sxs-lookup"><span data-stu-id="8ca2c-135">Toolbar</span></span>

<span data-ttu-id="8ca2c-p105">Für die meisten Registerkarten wird eine Symbolleiste angezeigt, nachdem Sie auf sie geklickt haben. Die Symbolleiste enthält Symbole, die jeweils eine bestimmte Aktion auslösen. Die folgende Tabelle beschreibt die Symbole und deren Aktionen.</span><span class="sxs-lookup"><span data-stu-id="8ca2c-p105">When you click most tabs, you'll see a toolbar. The toolbar has icons that perform a specific action. The following table describes the icons and their actions.</span></span>

****

|<span data-ttu-id="8ca2c-139">Symbol</span><span class="sxs-lookup"><span data-stu-id="8ca2c-139">Icon</span></span>|<span data-ttu-id="8ca2c-140">Name</span><span class="sxs-lookup"><span data-stu-id="8ca2c-140">Name</span></span>|<span data-ttu-id="8ca2c-141">Aktion</span><span class="sxs-lookup"><span data-stu-id="8ca2c-141">Action</span></span>|
|---|---|---|
|![Hinzufügen (Symbol)](../../media/ITPro-EAC-AddIcon.gif)|<span data-ttu-id="8ca2c-143">Hinzufügen, Neu</span><span class="sxs-lookup"><span data-stu-id="8ca2c-143">Add, New</span></span>|<span data-ttu-id="8ca2c-p106">Über dieses Symbol können Sie ein neues Objekt erstellen. Bei einigen dieser Symbole gibt es einen dazugehörigen nach unten zeigenden Pfeil, auf den Sie klicken können, um weitere Objekte anzuzeigen, die Sie erstellen können.</span><span class="sxs-lookup"><span data-stu-id="8ca2c-p106">Use this icon to create a new object. Some of these icons have an associated down arrow you can click to show additional objects you can create.</span></span>|
|![Bearbeitungssymbol](../../media/ITPro-EAC-EditIcon.gif)|<span data-ttu-id="8ca2c-147">Bearbeiten</span><span class="sxs-lookup"><span data-stu-id="8ca2c-147">Edit</span></span>|<span data-ttu-id="8ca2c-148">Über dieses Symbol können Sie ein Objekt bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="8ca2c-148">Use this icon to edit an object.</span></span>|
|![Löschen (Symbol)](../../media/ITPro-EAC-DeleteIcon.gif)|<span data-ttu-id="8ca2c-150">Delete</span><span class="sxs-lookup"><span data-stu-id="8ca2c-150">Delete</span></span>|<span data-ttu-id="8ca2c-p107">Über dieses Symbol können Sie ein Objekt löschen. Bei einigen Löschsymbolen gibt es einen nach unten zeigenden Pfeil, auf den Sie zum Einblenden weiterer Optionen klicken können.</span><span class="sxs-lookup"><span data-stu-id="8ca2c-p107">Use this icon to delete an object. Some delete icons have a down arrow you can click to show additional options.</span></span>|
|![Suchen (Symbol)](../../media/ITPro-EAC-.gif)|<span data-ttu-id="8ca2c-154">Suche</span><span class="sxs-lookup"><span data-stu-id="8ca2c-154">Search</span></span>|<span data-ttu-id="8ca2c-155">Über dieses Symbol können Sie ein Suchfeld öffnen, in das Sie den Suchbegriff für ein zu suchendes Objekt eingeben können.</span><span class="sxs-lookup"><span data-stu-id="8ca2c-155">Use this icon to open a search box in which you can type the search phrase for an object you want to find.</span></span>|
|![Aktualisieren (Symbol)](../../media/ITPro-EAC-RefreshIcon.gif)|<span data-ttu-id="8ca2c-157">Aktualisieren</span><span class="sxs-lookup"><span data-stu-id="8ca2c-157">Refresh</span></span>|<span data-ttu-id="8ca2c-158">Über dieses Symbol können Sie die Listenansicht aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="8ca2c-158">Use this icon to refresh the list view.</span></span>|
|![Weitere Optionen (Symbol)](../../media/ITPro-EAC-MoreOptionsIcon.gif)|<span data-ttu-id="8ca2c-160">Weitere Optionen</span><span class="sxs-lookup"><span data-stu-id="8ca2c-160">More options</span></span>|<span data-ttu-id="8ca2c-p108">Über dieses Symbol können Sie mehrere Aktionen anzeigen, die Sie auf die Objekte dieser Registerkarte anwenden können. Wenn Sie z. B. unter **Empfänger \> Benutzer** auf dieses Symbol klicken, wird die Option **Erweiterte Suche** angezeigt.  </span><span class="sxs-lookup"><span data-stu-id="8ca2c-p108">Use this icon to view more actions you can perform for that tab's objects. For example, in **Recipients \> Users** clicking this icon shows the option to perform an **Advanced Search**.</span></span>|
|![NACH-OBEN-TASTE (Symbol)](../../media/ITPro-EAC-UpArrowIcon.gif)![NACH-UNTEN-TASTE (Symbol)](../../media/ITPro-EAC-DownArrowIcon.gif)|<span data-ttu-id="8ca2c-165">Pfeil nach oben und Pfeil nach unten</span><span class="sxs-lookup"><span data-stu-id="8ca2c-165">Up arrow and down arrow</span></span>|<span data-ttu-id="8ca2c-166">Mithilfe dieser Symbole können Sie die Priorität eines Objekts nach oben oder unten verschieben.</span><span class="sxs-lookup"><span data-stu-id="8ca2c-166">Use these icons to move an object's priority up or down.</span></span>|
|![Entfernen (Symbol)](../../media/ITPro-EAC-RemoveIcon.gif)|<span data-ttu-id="8ca2c-168">Entfernen</span><span class="sxs-lookup"><span data-stu-id="8ca2c-168">Remove</span></span>|<span data-ttu-id="8ca2c-169">Über dieses Symbol können Sie Objekte aus einer Liste entfernen.</span><span class="sxs-lookup"><span data-stu-id="8ca2c-169">Use this icon to remove objects from a list.</span></span>|
|

### <a name="list-view"></a><span data-ttu-id="8ca2c-170">Listenansicht</span><span class="sxs-lookup"><span data-stu-id="8ca2c-170">List View</span></span>

<span data-ttu-id="8ca2c-p109">Wenn Sie auf eine Registerkarte klicken, sehen Sie in den meisten Fällen eine Listenansicht. In der Listenansicht der Exchange-Verwaltungskonsole können ungefähr 10.000 Objekte angezeigt werden. Darüber hinaus können Sie die Ergebnisse seitenweise anzeigen.</span><span class="sxs-lookup"><span data-stu-id="8ca2c-p109">When you select a tab, in most cases you'll see a list view. The viewable limit with the EAC list view is approximately 10,000 objects. In addition, paging is included so that you can page to results.</span></span>

### <a name="details-pane"></a><span data-ttu-id="8ca2c-174">Bereich "Details"</span><span class="sxs-lookup"><span data-stu-id="8ca2c-174">Details Pane</span></span>

<span data-ttu-id="8ca2c-p110">Wenn Sie in der Listenansicht ein Objekt auswählen, werden Informationen zu diesem Objekt im Detailbereich angezeigt. In einigen Fällen enthält der Detailbereich Verwaltungsaufgaben.</span><span class="sxs-lookup"><span data-stu-id="8ca2c-p110">When you select an object from the list view, information about that object is displayed in the details pane. In some cases the details pane includes management tasks.</span></span>

### <a name="me-tile-and-help"></a><span data-ttu-id="8ca2c-177">Ich-Kachel und Hilfe</span><span class="sxs-lookup"><span data-stu-id="8ca2c-177">Me tile and Help</span></span>

<span data-ttu-id="8ca2c-178">Über die **Ich**-Kachel können Sie sich bei der Exchange-Verwaltungskonsole abmelden und als ein anderer Benutzer anmelden.</span><span class="sxs-lookup"><span data-stu-id="8ca2c-178">The **Me** tile allows you to sign out the EAC and sign in as a different user.</span></span> <span data-ttu-id="8ca2c-179">Im Dropdownmenü ![ "Hilfehilfesymbol" ](../../media/ITPro-EAC-HelpIcon.gif) können Sie die folgenden Aktionen ausführen:</span><span class="sxs-lookup"><span data-stu-id="8ca2c-179">From the **Help**![Help Icon](../../media/ITPro-EAC-HelpIcon.gif) drop-down menu, you can do the following actions:</span></span>

- <span data-ttu-id="8ca2c-180">**Hilfe**: Klicken Sie ![ auf das ](../../media/ITPro-EAC-HelpIcon.gif) Hilfesymbol, um die Onlinehilfeinhalte anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="8ca2c-180">**Help**: Click ![Help Icon](../../media/ITPro-EAC-HelpIcon.gif) to view the online help content.</span></span>
- <span data-ttu-id="8ca2c-181">**Feedback:** Geben Sie Feedback.</span><span class="sxs-lookup"><span data-stu-id="8ca2c-181">**Feedback**: Leave feedback.</span></span>
- <span data-ttu-id="8ca2c-182">**Community:** Stellen Sie eine Frage, um Antworten in den Communityforen zu finden.</span><span class="sxs-lookup"><span data-stu-id="8ca2c-182">**Community**: Post a question for find answers in the community forums.</span></span>
- <span data-ttu-id="8ca2c-183">**Hilfeblase deaktivieren:** Die Hilfeblase zeigt kontextbezogene Hilfe für Felder an, wenn Sie ein Objekt erstellen oder bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="8ca2c-183">**Disable Help bubble**: The Help bubble displays contextual help for fields when you create or edit an object.</span></span> <span data-ttu-id="8ca2c-184">Sie können die Hilfesprechblase deaktivieren oder aktivieren, wenn sie deaktiviert wurde.</span><span class="sxs-lookup"><span data-stu-id="8ca2c-184">You can turn off the Help bubble or turn it on if it has been disabled.</span></span>
- <span data-ttu-id="8ca2c-185">**Befehlsprotokollierung** anzeigen: Ein neues Fenster wird geöffnet, in dem die entsprechenden PowerShell-Befehle basierend auf den in der EAC konfigurierten Einstellungen angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="8ca2c-185">**Show Command Logging**: A new window opens that shows the equivalent PowerShell commands based on what you configured in EAC.</span></span>

## <a name="supported-browsers"></a><span data-ttu-id="8ca2c-186">Unterstützte Browser</span><span class="sxs-lookup"><span data-stu-id="8ca2c-186">Supported Browsers</span></span>

<span data-ttu-id="8ca2c-187">Für eine optimale Nutzung des EAC sollten Sie immer die neuesten Browser, Office-Clients und Apps verwenden.</span><span class="sxs-lookup"><span data-stu-id="8ca2c-187">For the best experience using the EAC, we recommend that you always use the latest browsers, Office clients, and apps.</span></span> <span data-ttu-id="8ca2c-188">Zudem wird empfohlen, dass Sie Softwareupdates installieren, sobald sie verfügbar werden.</span><span class="sxs-lookup"><span data-stu-id="8ca2c-188">We also recommend that you install software updates when they become available.</span></span> <span data-ttu-id="8ca2c-189">Weitere Informationen zu den unterstützten Browsern und Systemanforderungen für den Dienst finden Sie unter [Systemanforderungen für Office.](https://products.office.com/office-system-requirements)</span><span class="sxs-lookup"><span data-stu-id="8ca2c-189">For more information about the supported browsers and system requirements for the service, see [System requirements for Office](https://products.office.com/office-system-requirements).</span></span>

## <a name="supported-languages"></a><span data-ttu-id="8ca2c-190">Unterstützte Sprachen</span><span class="sxs-lookup"><span data-stu-id="8ca2c-190">Supported languages</span></span>

<span data-ttu-id="8ca2c-191">Die folgenden Sprachen werden für die EAC im eigenständigen EOP unterstützt und verfügbar.</span><span class="sxs-lookup"><span data-stu-id="8ca2c-191">The following languages are supported and available for the EAC in standalone EOP.</span></span>

- <span data-ttu-id="8ca2c-192">Amharisch</span><span class="sxs-lookup"><span data-stu-id="8ca2c-192">Amharic</span></span>
- <span data-ttu-id="8ca2c-193">Arabisch</span><span class="sxs-lookup"><span data-stu-id="8ca2c-193">Arabic</span></span>
- <span data-ttu-id="8ca2c-194">Baskisch (Baskisch)</span><span class="sxs-lookup"><span data-stu-id="8ca2c-194">Basque (Basque)</span></span>
- <span data-ttu-id="8ca2c-195">Bengali (Indien)</span><span class="sxs-lookup"><span data-stu-id="8ca2c-195">Bengali (India)</span></span>
- <span data-ttu-id="8ca2c-196">Bulgarisch</span><span class="sxs-lookup"><span data-stu-id="8ca2c-196">Bulgarian</span></span>
- <span data-ttu-id="8ca2c-197">Katalanisch</span><span class="sxs-lookup"><span data-stu-id="8ca2c-197">Catalan</span></span>
- <span data-ttu-id="8ca2c-198">Chinesisch (vereinfacht)</span><span class="sxs-lookup"><span data-stu-id="8ca2c-198">Chinese (Simplified)</span></span>
- <span data-ttu-id="8ca2c-199">Chinesisch (traditionell)</span><span class="sxs-lookup"><span data-stu-id="8ca2c-199">Chinese (Traditional)</span></span>
- <span data-ttu-id="8ca2c-200">Kroatisch</span><span class="sxs-lookup"><span data-stu-id="8ca2c-200">Croatian</span></span>
- <span data-ttu-id="8ca2c-201">Tschechisch</span><span class="sxs-lookup"><span data-stu-id="8ca2c-201">Czech</span></span>
- <span data-ttu-id="8ca2c-202">Dänisch</span><span class="sxs-lookup"><span data-stu-id="8ca2c-202">Danish</span></span>
- <span data-ttu-id="8ca2c-203">Niederländisch</span><span class="sxs-lookup"><span data-stu-id="8ca2c-203">Dutch</span></span>
- <span data-ttu-id="8ca2c-204">Englisch</span><span class="sxs-lookup"><span data-stu-id="8ca2c-204">English</span></span>
- <span data-ttu-id="8ca2c-205">Estnisch</span><span class="sxs-lookup"><span data-stu-id="8ca2c-205">Estonian</span></span>
- <span data-ttu-id="8ca2c-206">Filipino (Philippinen)</span><span class="sxs-lookup"><span data-stu-id="8ca2c-206">Filipino (Philippines)</span></span>
- <span data-ttu-id="8ca2c-207">Finnisch</span><span class="sxs-lookup"><span data-stu-id="8ca2c-207">Finnish</span></span>
- <span data-ttu-id="8ca2c-208">Französisch</span><span class="sxs-lookup"><span data-stu-id="8ca2c-208">French</span></span>
- <span data-ttu-id="8ca2c-209">Galizisch</span><span class="sxs-lookup"><span data-stu-id="8ca2c-209">Galician</span></span>
- <span data-ttu-id="8ca2c-210">Deutsch</span><span class="sxs-lookup"><span data-stu-id="8ca2c-210">German</span></span>
- <span data-ttu-id="8ca2c-211">Griechisch</span><span class="sxs-lookup"><span data-stu-id="8ca2c-211">Greek</span></span>
- <span data-ttu-id="8ca2c-212">Gujarati</span><span class="sxs-lookup"><span data-stu-id="8ca2c-212">Gujarati</span></span>
- <span data-ttu-id="8ca2c-213">Hebräisch</span><span class="sxs-lookup"><span data-stu-id="8ca2c-213">Hebrew</span></span>
- <span data-ttu-id="8ca2c-214">Hindi</span><span class="sxs-lookup"><span data-stu-id="8ca2c-214">Hindi</span></span>
- <span data-ttu-id="8ca2c-215">Ungarisch</span><span class="sxs-lookup"><span data-stu-id="8ca2c-215">Hungarian</span></span>
- <span data-ttu-id="8ca2c-216">Isländisch</span><span class="sxs-lookup"><span data-stu-id="8ca2c-216">Icelandic</span></span>
- <span data-ttu-id="8ca2c-217">Indonesisch</span><span class="sxs-lookup"><span data-stu-id="8ca2c-217">Indonesian</span></span>
- <span data-ttu-id="8ca2c-218">Italienisch</span><span class="sxs-lookup"><span data-stu-id="8ca2c-218">Italian</span></span>
- <span data-ttu-id="8ca2c-219">Japanisch</span><span class="sxs-lookup"><span data-stu-id="8ca2c-219">Japanese</span></span>
- <span data-ttu-id="8ca2c-220">Kannada</span><span class="sxs-lookup"><span data-stu-id="8ca2c-220">Kannada</span></span>
- <span data-ttu-id="8ca2c-221">Kasachisch</span><span class="sxs-lookup"><span data-stu-id="8ca2c-221">Kazakh</span></span>
- <span data-ttu-id="8ca2c-222">Kisuaheli</span><span class="sxs-lookup"><span data-stu-id="8ca2c-222">Kiswahili</span></span>
- <span data-ttu-id="8ca2c-223">Koreanisch</span><span class="sxs-lookup"><span data-stu-id="8ca2c-223">Korean</span></span>
- <span data-ttu-id="8ca2c-224">Lettisch</span><span class="sxs-lookup"><span data-stu-id="8ca2c-224">Latvian</span></span>
- <span data-ttu-id="8ca2c-225">Litauisch</span><span class="sxs-lookup"><span data-stu-id="8ca2c-225">Lithuanian</span></span>
- <span data-ttu-id="8ca2c-226">Malaiisch (Brunei Darussalam)</span><span class="sxs-lookup"><span data-stu-id="8ca2c-226">Malay (Brunei Darussalam)</span></span>
- <span data-ttu-id="8ca2c-227">Malaiisch (Malaysia)</span><span class="sxs-lookup"><span data-stu-id="8ca2c-227">Malay (Malaysia)</span></span>
- <span data-ttu-id="8ca2c-228">Malayalam</span><span class="sxs-lookup"><span data-stu-id="8ca2c-228">Malayalam</span></span>
- <span data-ttu-id="8ca2c-229">Marathi</span><span class="sxs-lookup"><span data-stu-id="8ca2c-229">Marathi</span></span>
- <span data-ttu-id="8ca2c-230">Norwegisch (Bokmål)</span><span class="sxs-lookup"><span data-stu-id="8ca2c-230">Norwegian (Bokmål)</span></span>
- <span data-ttu-id="8ca2c-231">Norwegisch (Nynorsk)</span><span class="sxs-lookup"><span data-stu-id="8ca2c-231">Norwegian (Nynorsk)</span></span>
- <span data-ttu-id="8ca2c-232">Odia</span><span class="sxs-lookup"><span data-stu-id="8ca2c-232">Oriya</span></span>
- <span data-ttu-id="8ca2c-233">Persisch</span><span class="sxs-lookup"><span data-stu-id="8ca2c-233">Persian</span></span>
- <span data-ttu-id="8ca2c-234">Polnisch</span><span class="sxs-lookup"><span data-stu-id="8ca2c-234">Polish</span></span>
- <span data-ttu-id="8ca2c-235">Portugiesisch (Brasilien)</span><span class="sxs-lookup"><span data-stu-id="8ca2c-235">Portuguese (Brazil)</span></span>
- <span data-ttu-id="8ca2c-236">Portugiesisch (Portugal)</span><span class="sxs-lookup"><span data-stu-id="8ca2c-236">Portuguese (Portugal)</span></span>
- <span data-ttu-id="8ca2c-237">Rumänisch</span><span class="sxs-lookup"><span data-stu-id="8ca2c-237">Romanian</span></span>
- <span data-ttu-id="8ca2c-238">Russisch</span><span class="sxs-lookup"><span data-stu-id="8ca2c-238">Russian</span></span>
- <span data-ttu-id="8ca2c-239">Serbisch (Kyrillisch, Serbien)</span><span class="sxs-lookup"><span data-stu-id="8ca2c-239">Serbian (Cyrillic, Serbia)</span></span>
- <span data-ttu-id="8ca2c-240">Serbisch (Lateinisch)</span><span class="sxs-lookup"><span data-stu-id="8ca2c-240">Serbian (Latin)</span></span>
- <span data-ttu-id="8ca2c-241">Slowakisch</span><span class="sxs-lookup"><span data-stu-id="8ca2c-241">Slovak</span></span>
- <span data-ttu-id="8ca2c-242">Slowenisch</span><span class="sxs-lookup"><span data-stu-id="8ca2c-242">Slovenian</span></span>
- <span data-ttu-id="8ca2c-243">Spanisch</span><span class="sxs-lookup"><span data-stu-id="8ca2c-243">Spanish</span></span>
- <span data-ttu-id="8ca2c-244">Schwedisch</span><span class="sxs-lookup"><span data-stu-id="8ca2c-244">Swedish</span></span>
- <span data-ttu-id="8ca2c-245">Tamil</span><span class="sxs-lookup"><span data-stu-id="8ca2c-245">Tamil</span></span>
- <span data-ttu-id="8ca2c-246">Telugu</span><span class="sxs-lookup"><span data-stu-id="8ca2c-246">Telugu</span></span>
- <span data-ttu-id="8ca2c-247">Thailändisch</span><span class="sxs-lookup"><span data-stu-id="8ca2c-247">Thai</span></span>
- <span data-ttu-id="8ca2c-248">Türkisch</span><span class="sxs-lookup"><span data-stu-id="8ca2c-248">Turkish</span></span>
- <span data-ttu-id="8ca2c-249">Ukrainisch</span><span class="sxs-lookup"><span data-stu-id="8ca2c-249">Ukrainian</span></span>
- <span data-ttu-id="8ca2c-250">Urdu</span><span class="sxs-lookup"><span data-stu-id="8ca2c-250">Urdu</span></span>
- <span data-ttu-id="8ca2c-251">Vietnamesisch</span><span class="sxs-lookup"><span data-stu-id="8ca2c-251">Vietnamese</span></span>
- <span data-ttu-id="8ca2c-252">Walisisch</span><span class="sxs-lookup"><span data-stu-id="8ca2c-252">Welsh</span></span>
