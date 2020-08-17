---
title: Datensätzen mithilfe von Aufbewahrungsbezeichnungen deklarieren
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: Datensätze mithilfe von Aufbewahrungsbezeichnungen deklarieren.
ms.openlocfilehash: c8024cf08be2259ffa8b6747bebf4943e11e4d60
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46695252"
---
# <a name="declare-records-by-using-retention-labels"></a><span data-ttu-id="4e9cd-103">Datensätzen mithilfe von Aufbewahrungsbezeichnungen deklarieren</span><span class="sxs-lookup"><span data-stu-id="4e9cd-103">Declare records by using retention labels</span></span>

><span data-ttu-id="4e9cd-104">*[Microsoft 365-Lizenzierungsleitfaden für Sicherheit und Compliance](https://aka.ms/ComplianceSD).*</span><span class="sxs-lookup"><span data-stu-id="4e9cd-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="4e9cd-105">Verwenden Sie [Aufbewahrungsbezeichnungen](retention.md#retention-labels), um Inhalte als Datensätze zu kennzeichnen.</span><span class="sxs-lookup"><span data-stu-id="4e9cd-105">You use [retention labels](retention.md#retention-labels) to mark content as a record.</span></span> <span data-ttu-id="4e9cd-106">Sie können diese Bezeichnungen entweder veröffentlichen, damit Benutzer und Administratoren sie manuell auf Inhalte anwenden können, oder diese Bezeichnungen automatisch auf Inhalte anwenden, die Sie als Datensatz markieren möchten.</span><span class="sxs-lookup"><span data-stu-id="4e9cd-106">You can either publish those labels so that users and administrators can manually apply them to content, or auto-apply those labels to content that you want to mark as a record.</span></span>

## <a name="configuring-retention-labels-to-declare-records"></a><span data-ttu-id="4e9cd-107">Aufbewahrungsetiketten zum Deklarieren von Datensätzen konfigurieren</span><span class="sxs-lookup"><span data-stu-id="4e9cd-107">Configuring retention labels to declare records</span></span>

<span data-ttu-id="4e9cd-108">Wenn Sie eine [Aufbewahrungsbezeichnung](retention.md#retention-labels)erstellen, wählen Sie die Option aus, um den Inhalt als Datensatz zu markieren.</span><span class="sxs-lookup"><span data-stu-id="4e9cd-108">When you create a [retention label](retention.md#retention-labels), select the option to mark the content as a record.</span></span>

>[!NOTE] 
> <span data-ttu-id="4e9cd-109">Die Option zum Markieren des Inhalts als Datensatz ist nicht verfügbar, wenn Sie Aufbewahrungsbezeichnungen aus **Information Governance** im Microsoft 365 Compliance Center erstellen oder konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="4e9cd-109">The option to mark the content as a record is not available when you create or configure retention labels from **Information Governance** in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="4e9cd-110">Verwenden Sie stattdessen **Datensatzverwaltung**.</span><span class="sxs-lookup"><span data-stu-id="4e9cd-110">Instead, you must use **Records Management**.</span></span>

1. <span data-ttu-id="4e9cd-111">Gehen Sie im [Microsoft 365 Compliance Center](https://compliance.microsoft.com) zu **Datensatzverwaltung** \> **Ablageplan**.</span><span class="sxs-lookup"><span data-stu-id="4e9cd-111">In the [Microsoft 365 compliance center](https://compliance.microsoft.com), go to **Records Management** \> **File Plan**.</span></span> <span data-ttu-id="4e9cd-112">Wählen Sie von der Seite **Dateiplan** **Eine Bezeichnung erstellen**.</span><span class="sxs-lookup"><span data-stu-id="4e9cd-112">On the **File plan** page, select **Create a label**.</span></span>

2. <span data-ttu-id="4e9cd-113">Wählen Sie auf der Seite **Bezeichnungseinstellungen** im Assistenten die Option zum Klassifizieren von Inhalten als Datensatz aus.</span><span class="sxs-lookup"><span data-stu-id="4e9cd-113">On the **Label settings** page in the wizard, choose the option to classify content as a record.</span></span>
    
   ![Aktivieren Sie das Kontrollkästchen „Bezeichnung zum Klassifizieren von Inhalt als „Datensatz“ verwenden“](../media/recordversioning6.png)

3. <span data-ttu-id="4e9cd-115">Wenden Sie die Aufbewahrungsbezeichnung nach Bedarf auf SharePoint- oder OneDrive-Dokumente und Exchange-E-Mails an.</span><span class="sxs-lookup"><span data-stu-id="4e9cd-115">Apply the retention label to SharePoint or OneDrive documents and Exchange emails, as needed.</span></span> <span data-ttu-id="4e9cd-116">Für Anweisungen:</span><span class="sxs-lookup"><span data-stu-id="4e9cd-116">For instructions:</span></span>
    
    - [<span data-ttu-id="4e9cd-117">Erstellen von Aufbewahrungsbezeichnungen und Anwenden in Apps</span><span class="sxs-lookup"><span data-stu-id="4e9cd-117">Create retention labels and apply them in apps</span></span>](create-apply-retention-labels.md)
    
    - [<span data-ttu-id="4e9cd-118">Automatisches Anwenden einer Aufbewahrungsbezeichnung auf Inhalte</span><span class="sxs-lookup"><span data-stu-id="4e9cd-118">Apply a retention label to content automatically</span></span>](apply-retention-labels-automatically.md)

## <a name="applying-the-configured-retention-label-to-content"></a><span data-ttu-id="4e9cd-119">Anwenden der konfigurierten Aufbewahrungsbezeichnung auf Inhalte</span><span class="sxs-lookup"><span data-stu-id="4e9cd-119">Applying the configured retention label to content</span></span>

<span data-ttu-id="4e9cd-120">Wenn Aufbewahrungsbezeichnungen, die Inhalte als Datensatz markieren, Benutzern zur Verfügung gestellt werden, um sie in Apps anzuwenden:</span><span class="sxs-lookup"><span data-stu-id="4e9cd-120">When retention labels that mark content as a record are made available for users to apply them in apps:</span></span>

- <span data-ttu-id="4e9cd-121">Bei Exchange kann jeder Benutzer mit Schreibzugriff auf das Postfach diese Bezeichnung anwenden.</span><span class="sxs-lookup"><span data-stu-id="4e9cd-121">For Exchange, any user with write-access to the mailbox can apply these labels.</span></span> 
- <span data-ttu-id="4e9cd-122">Bei SharePoint und OneDrive kann jeder Benutzer in der Standardgruppe "Mitglieder" (Berechtigungsstufe "Beitrag") diese Bezeichnung anwenden.</span><span class="sxs-lookup"><span data-stu-id="4e9cd-122">For SharePoint and OneDrive, any user in the default Members group (the Contribute permission level) can apply these labels.</span></span>

<span data-ttu-id="4e9cd-123">Beispiel für ein Dokument, das mithilfe einer Aufbewahrungsbezeichnung als Datensatz markiert wurde:</span><span class="sxs-lookup"><span data-stu-id="4e9cd-123">Example of a document marked as record by using a retention label:</span></span>

![Detailbereich für ein als Datensatz markiertes Dokument](../media/recordversioning7.png)

## <a name="next-steps"></a><span data-ttu-id="4e9cd-125">Weitere Schritte</span><span class="sxs-lookup"><span data-stu-id="4e9cd-125">Next steps</span></span>

<span data-ttu-id="4e9cd-126">Wenn Sie Dokumente aktualisieren müssen, bei denen es sich um Datensätze handelt, lesen Sie [Versionsverwaltung zur Aktualisierung von Datensätzen verwenden, die in Microsoft Office SharePoint Online oder OneDrive gespeichert sind](record-versioning.md).</span><span class="sxs-lookup"><span data-stu-id="4e9cd-126">If you need to update documents that are records, see [Use record versioning to update records stored in SharePoint or OneDrive](record-versioning.md).</span></span>

<span data-ttu-id="4e9cd-127">Mehr zur Löschung von Datensätzen finden Sie unter [Löschung von Inhalten](disposition.md).</span><span class="sxs-lookup"><span data-stu-id="4e9cd-127">To learn about the disposition of records, see [Disposing of content](disposition.md).</span></span>
