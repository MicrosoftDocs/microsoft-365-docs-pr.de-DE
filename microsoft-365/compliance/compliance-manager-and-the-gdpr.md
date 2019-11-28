---
title: Microsoft Compliance Manager und die dsgvo
ms.author: robmazz
author: robmazz
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Der Microsoft Compliance-Manager ist ein kostenloses Workflow basiertes Risiko Bewertungstool im Microsoft-Dienst Vertrauensstellungs Portal. Mit dem Compliance-Manager können Sie behördliche Compliance-Aktivitäten im Zusammenhang mit Microsoft Cloud Services nachverfolgen, zuweisen und überprüfen.
ms.openlocfilehash: 0d2edb2f7362fa8e8bea6ae82c417f61072bccff
ms.sourcegitcommit: e386037c9cc335c86896dc153344850735afbccd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/27/2019
ms.locfileid: "39633614"
---
# <a name="microsoft-compliance-manager-and-the-gdpr"></a><span data-ttu-id="a2cfb-104">Microsoft Compliance Manager und die dsgvo</span><span class="sxs-lookup"><span data-stu-id="a2cfb-104">Microsoft Compliance Manager and the GDPR</span></span>

<span data-ttu-id="a2cfb-105">Die allgemeine Datenschutzverordnung (dsgvo), die von der Europäischen Union erlassen wird, kann sich auf Ihre Compliance-Strategie auswirken und spezifische Aktionen zum Verwalten von Benutzer-und Kundeninformationen im Compliance-Manager durchführen.</span><span class="sxs-lookup"><span data-stu-id="a2cfb-105">The General Data Protection Regulation (GDPR) enacted by the European Union can impact your compliance strategy and mandate specific actions to manage user and customer information used in Compliance Manager.</span></span>

## <a name="user-privacy-settings"></a><span data-ttu-id="a2cfb-106">Datenschutzeinstellungen</span><span class="sxs-lookup"><span data-stu-id="a2cfb-106">User Privacy settings</span></span>

<span data-ttu-id="a2cfb-107">Für bestimmte Richtlinien ist es erforderlich, dass eine Organisation Benutzer Verlaufsdaten löschen kann.</span><span class="sxs-lookup"><span data-stu-id="a2cfb-107">Certain regulations require that an organization must be able to delete user history data.</span></span> <span data-ttu-id="a2cfb-108">Compliance-Manager bietet Funktionen für **Benutzerdaten Schutzeinstellungen** , die Administratoren Folgendes ermöglichen:</span><span class="sxs-lookup"><span data-stu-id="a2cfb-108">Compliance Manager provides **User Privacy Settings** functions that allow administrators to:</span></span>
  
- [<span data-ttu-id="a2cfb-109">Suchen eines Benutzers</span><span class="sxs-lookup"><span data-stu-id="a2cfb-109">Search for a user</span></span>](#search-for-a-user)
- [<span data-ttu-id="a2cfb-110">Exportieren eines Berichts mit Kontoverlaufsdaten</span><span class="sxs-lookup"><span data-stu-id="a2cfb-110">Export a report of account data history</span></span>](#export-a-report-of-account-data-history)
- [<span data-ttu-id="a2cfb-111">Löschen der Verlaufsdaten von Benutzern</span><span class="sxs-lookup"><span data-stu-id="a2cfb-111">Delete user data history</span></span>](#delete-user-data-history)
  
## <a name="search-for-a-user"></a><span data-ttu-id="a2cfb-112">Suchen eines Benutzers</span><span class="sxs-lookup"><span data-stu-id="a2cfb-112">Search for a user</span></span>

<span data-ttu-id="a2cfb-113">So suchen Sie nach einem Benutzerkonto</span><span class="sxs-lookup"><span data-stu-id="a2cfb-113">To search for a user account:</span></span>
  
1. <span data-ttu-id="a2cfb-114">Geben Sie den Benutzer-e-Mail-Alias (die Informationen links neben dem @-Symbol) ein, und wählen Sie den Domänennamen aus der Liste Domänensuffix auf der rechten Seite aus.</span><span class="sxs-lookup"><span data-stu-id="a2cfb-114">Enter the user email alias (the information to the left of the @ symbol) and choose the domain name from the  domain suffix list on the right.</span></span> <span data-ttu-id="a2cfb-115">Für Organisationen mit mehreren registrierten Domänen überprüfen Sie das Domänennamensuffix doppelt, um sicherzustellen, dass es richtig ist.</span><span class="sxs-lookup"><span data-stu-id="a2cfb-115">For organizations with multiple registered domains, double check the domain name suffix to ensure that it is correct.</span></span>

2. <span data-ttu-id="a2cfb-116">Wenn Sie den Benutzernamen richtig eingegeben haben, wählen Sie **Suchen**aus.</span><span class="sxs-lookup"><span data-stu-id="a2cfb-116">When you have the username correctly entered, select **Search**.</span></span>

3. <span data-ttu-id="a2cfb-117">Für Benutzerkonten, die nicht zurückgegeben werden, wird die Seite **Benutzer nicht gefunden**angezeigt.</span><span class="sxs-lookup"><span data-stu-id="a2cfb-117">For user accounts not returned, the page displays **User not found**.</span></span> <span data-ttu-id="a2cfb-118">Überprüfen Sie die e-Mail-Adressinformationen des Benutzers, und nehmen Sie bei Bedarf Korrekturen vor.</span><span class="sxs-lookup"><span data-stu-id="a2cfb-118">Check the user's email address information and make corrections as necessary.</span></span> <span data-ttu-id="a2cfb-119">Zum Wiederholen wählen Sie **Suchen**aus.</span><span class="sxs-lookup"><span data-stu-id="a2cfb-119">To retry, select **Search**.</span></span>

4. <span data-ttu-id="a2cfb-120">Für Benutzerkonten, die zurückgegeben werden, ändert sich der Text der Schaltfläche von **Suche** zu **Löschen**.</span><span class="sxs-lookup"><span data-stu-id="a2cfb-120">For user accounts returned, the text of the button changes from **Search** to **Clear**.</span></span> <span data-ttu-id="a2cfb-121">Dies deutet darauf hin, dass das zurückgegebene Benutzerkonto der Betriebs Kontext für die zusätzlichen Funktionen ist und dass diese Funktionen für dieses Benutzerkonto gelten.</span><span class="sxs-lookup"><span data-stu-id="a2cfb-121">This indicates that the returned user account is the operating context for the additional functions and that these functions apply to this user account.</span></span>

5. <span data-ttu-id="a2cfb-122">Um Suchergebnisse zu löschen und nach einem anderen Benutzer zu suchen, wählen Sie **Löschen**aus.</span><span class="sxs-lookup"><span data-stu-id="a2cfb-122">To clear search results and search for a different user, select **Clear**.</span></span>

## <a name="export-a-report-of-account-data-history"></a><span data-ttu-id="a2cfb-123">Exportieren eines Berichts mit Kontoverlaufsdaten</span><span class="sxs-lookup"><span data-stu-id="a2cfb-123">Export a report of account data history</span></span>

<span data-ttu-id="a2cfb-124">Sie können für jedes identifizierte Benutzerkonto einen Bericht über Abhängigkeiten generieren, die mit dem Konto verknüpft sind.</span><span class="sxs-lookup"><span data-stu-id="a2cfb-124">For each user account identified, you can generate a report of dependencies linked to the account.</span></span> <span data-ttu-id="a2cfb-125">Mit diesen Informationen können Sie offene Aktionselemente neu zuweisen oder den Zugriff auf zuvor hochgeladene Beweise sicherstellen.</span><span class="sxs-lookup"><span data-stu-id="a2cfb-125">This information allows you to reassign open Action Items or ensure access to previously uploaded evidence.</span></span>
  
 <span data-ttu-id="a2cfb-126">So generieren und exportieren Sie einen Bericht:</span><span class="sxs-lookup"><span data-stu-id="a2cfb-126">To generate and export a report:</span></span>
  
1. <span data-ttu-id="a2cfb-127">Wählen Sie **exportieren** aus, um einen Bericht der Compliance-Manager-Steuerelement Aktionselemente zu generieren und herunterzuladen, die dem zurückgegebenen Benutzerkonto derzeit zugewiesen sind, und die Liste der Dokumente, die von diesem Benutzer hochgeladen wurden.</span><span class="sxs-lookup"><span data-stu-id="a2cfb-127">Select **Export** to generate and download a report of the Compliance Manager control Action Items currently assigned to the returned user account, and the list of documents uploaded by that user.</span></span> <span data-ttu-id="a2cfb-128">Wenn keine Aktionen oder hochgeladenen Dokumente zugeordnet sind, wird in einer Fehlermeldung "keine Daten für diesen Benutzer" angezeigt.</span><span class="sxs-lookup"><span data-stu-id="a2cfb-128">If there are no assigned actions or uploaded documents, an error message states "No data for this user".</span></span>

2. <span data-ttu-id="a2cfb-129">Der Bericht lädt im Hintergrund des aktiven Browserfensters herunter – wenn kein Popup zum Herunterladen angezeigt wird, in dem Sie den Downloadverlauf Ihres Browsers überprüfen möchten.</span><span class="sxs-lookup"><span data-stu-id="a2cfb-129">The report downloads in the background of the active browser window — if you don't see a download popup that you want to check your browser download history.</span></span>

3. <span data-ttu-id="a2cfb-130">Öffnen Sie das Dokument, um die Daten des Berichts zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="a2cfb-130">Open the document to review the report data.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a2cfb-131">Bei den Berichtsdaten handelt es sich nicht um eine Verlaufsliste, in der Statusänderungen an Aktionselement-Zuordnungs Verlauf gespeichert und angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="a2cfb-131">The report data is not a historical list that retains and displays state changes to Action Item assignment history.</span></span> <span data-ttu-id="a2cfb-132">Der generierte Bericht ist eine Momentaufnahme der Steuerungs Aktionselemente, die zum Zeitpunkt der Ausführung des Berichts zugewiesen wurden (Datum und Zeitstempel in den Bericht).</span><span class="sxs-lookup"><span data-stu-id="a2cfb-132">The generated report is a snapshot of the control Action Items assigned at the time that the report is run (date and time stamp written into the report).</span></span> <span data-ttu-id="a2cfb-133">Beispielsweise ergeben alle nachfolgenden Neuzuweisungen von Aktionselementen unterschiedliche Snapshot-Berichtsdaten, wenn der Bericht für denselben Benutzer erneut generiert wird.</span><span class="sxs-lookup"><span data-stu-id="a2cfb-133">For example, any subsequent reassignment of Action Items result in different snapshot report data if the report is generated again for the same user.</span></span>
  
## <a name="delete-user-data-history"></a><span data-ttu-id="a2cfb-134">Löschen der Verlaufsdaten von Benutzern</span><span class="sxs-lookup"><span data-stu-id="a2cfb-134">Delete user data history</span></span>

<span data-ttu-id="a2cfb-135">Legt alle dem zurückgegebenen Benutzer zugewiesenen Steuerungs Aktionselemente auf "nicht zugewiesen" fest.</span><span class="sxs-lookup"><span data-stu-id="a2cfb-135">Sets all control Action Items assigned to the returned user to 'unassigned'.</span></span> <span data-ttu-id="a2cfb-136">Legt den Wert für **hochgeladene** nach Werte für alle Dokumente fest, die vom zurückgegebenen Benutzer auf "Benutzer entfernt" hochgeladen wurden.</span><span class="sxs-lookup"><span data-stu-id="a2cfb-136">Sets the **uploaded by** value for any documents uploaded by the returned user to 'user removed'.</span></span>
  
<span data-ttu-id="a2cfb-137">So löschen Sie das Benutzerkonto-Aktionselement und den Dokumentupload-Verlauf:</span><span class="sxs-lookup"><span data-stu-id="a2cfb-137">To delete the user account Action Item and document upload history:</span></span>
  
1. <span data-ttu-id="a2cfb-138">Wählen Sie **Löschen**aus.</span><span class="sxs-lookup"><span data-stu-id="a2cfb-138">Select **Delete**.</span></span>

    <span data-ttu-id="a2cfb-139">Es wird ein Bestätigungsdialogfeld angezeigt: "*Hierdurch werden alle Aktionselement Zuweisungen des Steuerelements und der Verlauf des dokumentuploads für den ausgewählten Benutzer entfernt. Diese Aktion ist dauerhaft. Möchten Sie wirklich fortfahren?*"</span><span class="sxs-lookup"><span data-stu-id="a2cfb-139">A confirmation dialog is displayed: "*This removes all control Action Item assignments and the document upload history for the selected user. This action is permanent. Are you sure you want to continue?*"</span></span>

2. <span data-ttu-id="a2cfb-140">Um fortzufahren, wählen Sie **OK**, andernfalls **Abbrechen**aus.</span><span class="sxs-lookup"><span data-stu-id="a2cfb-140">To continue select **OK**, otherwise select **Cancel**.</span></span>
