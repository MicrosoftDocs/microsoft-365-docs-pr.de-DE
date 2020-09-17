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
ms.openlocfilehash: 841c5197addff704016e344ba7ae44355c872f72
ms.sourcegitcommit: 9f5b136b96b3af4db4cc6f5b1f35130ae60d6b12
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2020
ms.locfileid: "47817101"
---
# <a name="declare-records-by-using-retention-labels"></a><span data-ttu-id="1932f-103">Datensätzen mithilfe von Aufbewahrungsbezeichnungen deklarieren</span><span class="sxs-lookup"><span data-stu-id="1932f-103">Declare records by using retention labels</span></span>

><span data-ttu-id="1932f-104">*[Microsoft 365-Lizenzierungsleitfaden für Sicherheit und Compliance](https://aka.ms/ComplianceSD).*</span><span class="sxs-lookup"><span data-stu-id="1932f-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="1932f-105">Um Dokumente und E-Mails als Datensatz zu deklarieren, verwenden Sie [Aufbewahrungsbezeichnungen](retention.md#retention-labels), die Elemente als Datensatz markieren.</span><span class="sxs-lookup"><span data-stu-id="1932f-105">To declare documents and emails as a record, you use [retention labels](retention.md#retention-labels) that mark items as a record.</span></span> <span data-ttu-id="1932f-106">Sie können diese Bezeichnungen entweder veröffentlichen, damit Benutzer und Administratoren sie manuell auf Inhalte anwenden können, oder diese Bezeichnungen automatisch auf Inhalte anwenden, die Sie als Datensatz markieren möchten.</span><span class="sxs-lookup"><span data-stu-id="1932f-106">You can either publish those labels so that users and administrators can manually apply them to content, or auto-apply those labels to content that you want to mark as a record.</span></span>

## <a name="configuring-retention-labels-to-declare-records"></a><span data-ttu-id="1932f-107">Aufbewahrungsetiketten zum Deklarieren von Datensätzen konfigurieren</span><span class="sxs-lookup"><span data-stu-id="1932f-107">Configuring retention labels to declare records</span></span>

<span data-ttu-id="1932f-108">Wenn Sie eine Aufbewahrungsbezeichnung erstellen oder konfigurieren, wählen Sie die Option aus, um Elemente als Datensatz zu markieren.</span><span class="sxs-lookup"><span data-stu-id="1932f-108">When you create or configure a retention label, select the option to mark items as a record.</span></span>

>[!NOTE] 
> <span data-ttu-id="1932f-109">Die Option zum Markieren des Inhalts als Datensatz ist nicht verfügbar, wenn Sie Aufbewahrungsbezeichnungen aus **Information Governance** im Microsoft 365 Compliance Center erstellen oder konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="1932f-109">The option to mark the content as a record is not available when you create or configure retention labels from **Information Governance** in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="1932f-110">Verwenden Sie stattdessen **Datensatzverwaltung**.</span><span class="sxs-lookup"><span data-stu-id="1932f-110">Instead, you must use **Records Management**.</span></span>

<span data-ttu-id="1932f-111">So erstellen Sie eine neue Aufbewahrungsbezeichnung, die den Inhalt als Datensatz kennzeichnet:</span><span class="sxs-lookup"><span data-stu-id="1932f-111">To create a new retention label that marks the content as a record:</span></span>

1. <span data-ttu-id="1932f-112">Gehen Sie im [Microsoft 365 Compliance Center](https://compliance.microsoft.com) zu **Datensatzverwaltung** \> **Ablageplan**.</span><span class="sxs-lookup"><span data-stu-id="1932f-112">In the [Microsoft 365 compliance center](https://compliance.microsoft.com), go to **Records Management** \> **File Plan**.</span></span> <span data-ttu-id="1932f-113">Wählen Sie von der Seite **Dateiplan** **Eine Bezeichnung erstellen**.</span><span class="sxs-lookup"><span data-stu-id="1932f-113">On the **File plan** page, select **Create a label**.</span></span>

2. <span data-ttu-id="1932f-114">Wählen Sie im Assistenten auf der Seite **Aufbewahrungseinstellungen definieren** die Option, Elemente als Datensätze festzulegen:</span><span class="sxs-lookup"><span data-stu-id="1932f-114">On the **Define retention settings** page in the wizard, choose the option to mark items as records:</span></span>
    
   ![Wählen Sie die Aufbewahrungseinstellung aus, um Elemente als Datensatz zu markieren](../media/recordversioning6.png)

3. <span data-ttu-id="1932f-116">Wenden Sie die Aufbewahrungsbezeichnung nach Bedarf auf SharePoint- oder OneDrive-Dokumente und Exchange-E-Mails an.</span><span class="sxs-lookup"><span data-stu-id="1932f-116">Apply the retention label to SharePoint or OneDrive documents and Exchange emails, as needed.</span></span> <span data-ttu-id="1932f-117">Für Anweisungen:</span><span class="sxs-lookup"><span data-stu-id="1932f-117">For instructions:</span></span>
    
    - [<span data-ttu-id="1932f-118">Erstellen von Aufbewahrungsbezeichnungen und Anwenden in Apps</span><span class="sxs-lookup"><span data-stu-id="1932f-118">Create retention labels and apply them in apps</span></span>](create-apply-retention-labels.md)
    
    - [<span data-ttu-id="1932f-119">Automatisches Anwenden einer Aufbewahrungsbezeichnung auf Inhalte</span><span class="sxs-lookup"><span data-stu-id="1932f-119">Apply a retention label to content automatically</span></span>](apply-retention-labels-automatically.md)

## <a name="applying-the-configured-retention-label-to-content"></a><span data-ttu-id="1932f-120">Anwenden der konfigurierten Aufbewahrungsbezeichnung auf Inhalte</span><span class="sxs-lookup"><span data-stu-id="1932f-120">Applying the configured retention label to content</span></span>

<span data-ttu-id="1932f-121">Wenn Aufbewahrungsbezeichnungen, die Inhalte als Datensatz markieren, Benutzern zur Verfügung gestellt werden, um sie in Apps anzuwenden:</span><span class="sxs-lookup"><span data-stu-id="1932f-121">When retention labels that mark content as a record are made available for users to apply them in apps:</span></span>

- <span data-ttu-id="1932f-122">Bei Exchange kann jeder Benutzer mit Schreibzugriff auf das Postfach diese Bezeichnung anwenden.</span><span class="sxs-lookup"><span data-stu-id="1932f-122">For Exchange, any user with write-access to the mailbox can apply these labels.</span></span> 
- <span data-ttu-id="1932f-123">Bei SharePoint und OneDrive kann jeder Benutzer in der Standardgruppe "Mitglieder" (Berechtigungsstufe "Beitrag") diese Bezeichnung anwenden.</span><span class="sxs-lookup"><span data-stu-id="1932f-123">For SharePoint and OneDrive, any user in the default Members group (the Contribute permission level) can apply these labels.</span></span>

<span data-ttu-id="1932f-124">Beispiel für ein Dokument, das mithilfe einer Aufbewahrungsbezeichnung als Datensatz markiert wurde:</span><span class="sxs-lookup"><span data-stu-id="1932f-124">Example of a document marked as record by using a retention label:</span></span>

![Detailbereich für ein als Datensatz markiertes Dokument](../media/recordversioning7.png)

## <a name="next-steps"></a><span data-ttu-id="1932f-126">Weitere Schritte</span><span class="sxs-lookup"><span data-stu-id="1932f-126">Next steps</span></span>

<span data-ttu-id="1932f-127">Eine Liste von Szenarios, die von der Datensatzverwaltung unterstützt werden, finden Sie unter [Häufige Szenarios für die Datensatzverwaltung](get-started-with-records-management.md#common-scenarios-for-records-management).</span><span class="sxs-lookup"><span data-stu-id="1932f-127">For a list of scenarios supported by records management, see [Common scenarios for records management](get-started-with-records-management.md#common-scenarios-for-records-management).</span></span>
