---
title: Microsoft Compliance Manager und die DSGVO
f1.keywords:
- NOCSH
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
description: Microsoft Compliance Manager ist ein kostenloses, Workflow-basiertes Tool zur Risikobewertung im Microsoft Service Trust-Portal. Mit Compliance Manager können Sie gesetzliche Compliance-Aktivitäten im Zusammenhang mit Microsoft Cloud-Diensten verfolgen, zuweisen und überprüfen.
ms.openlocfilehash: 69e6551620fb654cb09d46554e6e3c98b6a2fc60
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2020
ms.locfileid: "41595802"
---
# <a name="microsoft-compliance-manager-and-the-gdpr"></a><span data-ttu-id="4dcc0-104">Microsoft Compliance Manager und die DSGVO</span><span class="sxs-lookup"><span data-stu-id="4dcc0-104">Microsoft Compliance Manager and the GDPR</span></span>

<span data-ttu-id="4dcc0-105">Die von der Europäischen Union erlassene Allgemeine Datenschutzverordnung (DSGVO) kann sich auf Ihre Compliance-Strategie auswirken und spezifische Maßnahmen zur Verwaltung der im Compliance Manager verwendeten Benutzer- und Kundeninformationen vorschreiben.</span><span class="sxs-lookup"><span data-stu-id="4dcc0-105">The General Data Protection Regulation (GDPR) enacted by the European Union can impact your compliance strategy and mandate specific actions to manage user and customer information used in Compliance Manager.</span></span>

## <a name="user-privacy-settings"></a><span data-ttu-id="4dcc0-106">Datenschutzeinstellungen</span><span class="sxs-lookup"><span data-stu-id="4dcc0-106">User Privacy settings</span></span>

<span data-ttu-id="4dcc0-107">Bestimmte Vorschriften erfordern, dass eine Organisation in der Lage sein muss, Verlaufsdaten von Benutzern zu löschen.</span><span class="sxs-lookup"><span data-stu-id="4dcc0-107">Certain regulations require that an organization must be able to delete user history data.</span></span> <span data-ttu-id="4dcc0-108">Der Compliance-Manager bietet Funktionen für **Datenschutzeinstellungen**, mit denen Administratoren folgende Aufgaben ausführen können:</span><span class="sxs-lookup"><span data-stu-id="4dcc0-108">Compliance Manager provides **User Privacy Settings** functions that allow administrators to:</span></span>
  
- [<span data-ttu-id="4dcc0-109">Suchen eines Benutzers</span><span class="sxs-lookup"><span data-stu-id="4dcc0-109">Search for a user</span></span>](#search-for-a-user)
- [<span data-ttu-id="4dcc0-110">Exportieren eines Berichts mit Kontoverlaufsdaten</span><span class="sxs-lookup"><span data-stu-id="4dcc0-110">Export a report of account data history</span></span>](#export-a-report-of-account-data-history)
- [<span data-ttu-id="4dcc0-111">Löschen der Verlaufsdaten von Benutzern</span><span class="sxs-lookup"><span data-stu-id="4dcc0-111">Delete user data history</span></span>](#delete-user-data-history)
  
## <a name="search-for-a-user"></a><span data-ttu-id="4dcc0-112">Suchen eines Benutzers</span><span class="sxs-lookup"><span data-stu-id="4dcc0-112">Search for a user</span></span>

<span data-ttu-id="4dcc0-113">So suchen Sie nach einem Benutzerkonto</span><span class="sxs-lookup"><span data-stu-id="4dcc0-113">To search for a user account:</span></span>
  
1. <span data-ttu-id="4dcc0-p103">Geben Sie den E-Mail-Alias des Benutzers ein (die Informationen links vom @-Symbol) und wählen Sie den Domänennamen aus der Liste der Domänensuffixe auf der rechten Seite aus. Bei Organisationen mit mehreren registrierten Domänen überprüfen Sie das Domänensuffix, um sicherzustellen, dass es korrekt ist.</span><span class="sxs-lookup"><span data-stu-id="4dcc0-p103">Enter the user email alias (the information to the left of the @ symbol) and choose the domain name from the  domain suffix list on the right. For organizations with multiple registered domains, double check the domain name suffix to ensure that it is correct.</span></span>

2. <span data-ttu-id="4dcc0-116">Wenn Sie den Benutzernamen richtig eingegeben haben, wählen Sie **Suche**.</span><span class="sxs-lookup"><span data-stu-id="4dcc0-116">When you have the username correctly entered, select **Search**.</span></span>

3. <span data-ttu-id="4dcc0-117">Bei Benutzerkonten, die nicht zurückgegeben werden, wird auf der Seite angezeigt: **Benutzer nicht gefunden**.</span><span class="sxs-lookup"><span data-stu-id="4dcc0-117">For user accounts not returned, the page displays **User not found**.</span></span> <span data-ttu-id="4dcc0-118">Überprüfen Sie die E-Mail-Adressinformationen des Benutzers, und nehmen Sie bei Bedarf Korrekturen vor.</span><span class="sxs-lookup"><span data-stu-id="4dcc0-118">Check the user's email address information and make corrections as necessary.</span></span> <span data-ttu-id="4dcc0-119">Um es erneut zu versuchen, wählen Sie **Suche** aus.</span><span class="sxs-lookup"><span data-stu-id="4dcc0-119">To retry, select **Search**.</span></span>

4. <span data-ttu-id="4dcc0-120">Bei zurückgegebenen Benutzerkonten ändert sich der Text der Schaltfläche von **Suche** in **Löschen**.</span><span class="sxs-lookup"><span data-stu-id="4dcc0-120">For user accounts returned, the text of the button changes from **Search** to **Clear**.</span></span> <span data-ttu-id="4dcc0-121">Dies weist darauf hin, dass das zurückgegebene Benutzerkonto der Betriebssystemkontext für die zusätzlichen Funktionen ist und dass diese Funktionen für dieses Benutzerkonto gelten.</span><span class="sxs-lookup"><span data-stu-id="4dcc0-121">This indicates that the returned user account is the operating context for the additional functions and that these functions apply to this user account.</span></span>

5. <span data-ttu-id="4dcc0-122">Um Suchergebnisse zu löschen und nach einem anderen Benutzer zu suchen, wählen Sie **Löschen**.</span><span class="sxs-lookup"><span data-stu-id="4dcc0-122">To clear search results and search for a different user, select **Clear**.</span></span>

## <a name="export-a-report-of-account-data-history"></a><span data-ttu-id="4dcc0-123">Exportieren eines Berichts mit Kontoverlaufsdaten</span><span class="sxs-lookup"><span data-stu-id="4dcc0-123">Export a report of account data history</span></span>

<span data-ttu-id="4dcc0-p106">Für jedes identifizierte Benutzerkonto können Sie einen Bericht der mit dem Konto verknüpften Abhängigkeiten generieren. Diese Informationen ermöglichen es Ihnen, geöffnete Aktionselemente erneut zuzuweisen oder den Zugriff auf zuvor hochgeladene Nachweise sicherzustellen.</span><span class="sxs-lookup"><span data-stu-id="4dcc0-p106">For each user account identified, you can generate a report of dependencies linked to the account. This information allows you to reassign open Action Items or ensure access to previously uploaded evidence.</span></span>
  
 <span data-ttu-id="4dcc0-126">So generieren und exportieren Sie einen Bericht:</span><span class="sxs-lookup"><span data-stu-id="4dcc0-126">To generate and export a report:</span></span>
  
1. <span data-ttu-id="4dcc0-127">Klicken Sie auf **Exportieren**, um einen Bericht über die Compliance Manager-Steuerelement-Aktionselemente zu generieren und herunterzuladen, die derzeit dem zurückgegebenen Benutzerkonto zugewiesen sind, sowie die Liste der von diesem Benutzer hochgeladenen Dokumente.</span><span class="sxs-lookup"><span data-stu-id="4dcc0-127">Select **Export** to generate and download a report of the Compliance Manager control Action Items currently assigned to the returned user account, and the list of documents uploaded by that user.</span></span> <span data-ttu-id="4dcc0-128">Wenn keine zugewiesenen Aktionen oder hochgeladenen Dokumente enthalten sind, wird in einer Fehlermeldung „Keine Daten für diesen Benutzer“ angezeigt.</span><span class="sxs-lookup"><span data-stu-id="4dcc0-128">If there are no assigned actions or uploaded documents, an error message states "No data for this user".</span></span>

2. <span data-ttu-id="4dcc0-129">Der Bericht wird im Hintergrund des aktiven Browserfensters heruntergeladen, wenn kein Popupfenster für Downloads angezeigt wird, das Sie im Downloadverlauf Ihres Browsers überprüfen sollten.</span><span class="sxs-lookup"><span data-stu-id="4dcc0-129">The report downloads in the background of the active browser window — if you don't see a download popup that you want to check your browser download history.</span></span>

3. <span data-ttu-id="4dcc0-130">Öffnen Sie das Dokument, um die Berichtsdaten zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="4dcc0-130">Open the document to review the report data.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="4dcc0-p108">Die Berichtsdaten sind keine Verlaufsliste, in der Zustandsänderungen des Zuordnungsverlaufs für Aktionselement beibehalten und angezeigt werden. Der generierte Bericht ist eine Momentaufnahme des Steuerelements "Aktionen", das zum Zeitpunkt der Ausführung des Berichts zugewiesen wurde (Datums- und Zeitstempel, der in den Bericht geschrieben wurde). Beispielsweise führt jede nachfolgende Neusignierung von Aktionselementen zu unterschiedlichen Momentaufnahmeberichtsdaten, wenn der Bericht für denselben Benutzer erneut generiert wird.</span><span class="sxs-lookup"><span data-stu-id="4dcc0-p108">The report data is not a historical list that retains and displays state changes to Action Item assignment history. The generated report is a snapshot of the control Action Items assigned at the time that the report is run (date and time stamp written into the report). For example, any subsequent reassignment of Action Items result in different snapshot report data if the report is generated again for the same user.</span></span>
  
## <a name="delete-user-data-history"></a><span data-ttu-id="4dcc0-134">Löschen der Verlaufsdaten von Benutzern</span><span class="sxs-lookup"><span data-stu-id="4dcc0-134">Delete user data history</span></span>

<span data-ttu-id="4dcc0-135">Setzt alle dem zurückgegebenen Benutzer zugewiesenen Steuerungsaktionselemente auf "nicht zugewiesen" fest.</span><span class="sxs-lookup"><span data-stu-id="4dcc0-135">Sets all control Action Items assigned to the returned user to 'unassigned'.</span></span> <span data-ttu-id="4dcc0-136">Legt den Wert für **hochgeladen von** für jegliche Dokumente, die vom zurückgegebenen Benutzer hochgeladen wurden, auf "Benutzer entfernt" fest.</span><span class="sxs-lookup"><span data-stu-id="4dcc0-136">Sets the **uploaded by** value for any documents uploaded by the returned user to 'user removed'.</span></span>
  
<span data-ttu-id="4dcc0-137">So löschen Sie das Aktionselement für das Benutzerkonto und den Uploadverlauf des Dokuments:</span><span class="sxs-lookup"><span data-stu-id="4dcc0-137">To delete the user account Action Item and document upload history:</span></span>
  
1. <span data-ttu-id="4dcc0-138">Klicken Sie auf **Löschen**.</span><span class="sxs-lookup"><span data-stu-id="4dcc0-138">Select **Delete**.</span></span>

    <span data-ttu-id="4dcc0-139">Es wird ein Bestätigungsdialogfeld angezeigt: „*Dadurch werden alle Steuerelementzuweisungen des Aktionselements und der Verlauf des Dokumentuploads für den ausgewählten Benutzer entfernt. Diese Aktion ist dauerhaft. Möchten Sie wirklich fortfahren?*“</span><span class="sxs-lookup"><span data-stu-id="4dcc0-139">A confirmation dialog is displayed: "*This removes all control Action Item assignments and the document upload history for the selected user. This action is permanent. Are you sure you want to continue?*"</span></span>

2. <span data-ttu-id="4dcc0-140">Um fortzufahren, wählen Sie **OK** aus, andernfalls **Abbrechen**.</span><span class="sxs-lookup"><span data-stu-id="4dcc0-140">To continue select **OK**, otherwise select **Cancel**.</span></span>
