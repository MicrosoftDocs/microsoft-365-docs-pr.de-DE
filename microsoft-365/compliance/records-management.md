---
title: Datensatzverwaltung
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
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Mit der Datensatzverwaltung in Microsoft 365 können Sie die spezifischen Aufbewahrungszeitpläne Ihrer Organisation in einen Aktenplan einbinden, um Aufbewahrung, Deklaration von Datensätzen und Disposition zur Unterstützung des gesamten Inhaltslebenszyklus zu verwalten.
ms.openlocfilehash: 261ae3286792dde540d9bf648c15e529863091ed
ms.sourcegitcommit: 252b1d1d8ae735b99bf46e27c08353afc330aef3
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/14/2020
ms.locfileid: "44231868"
---
# <a name="records-management-in-microsoft-365"></a><span data-ttu-id="a885d-103">Datensatzverwaltung in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="a885d-103">Records management in Microsoft 365</span></span>

><span data-ttu-id="a885d-104">*[Microsoft 365-Lizenzierungsleitfaden für Sicherheit und Compliance](https://aka.ms/ComplianceSD).*</span><span class="sxs-lookup"><span data-stu-id="a885d-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="a885d-105">Organisationen aller Art benötigen eine Datensatzverwaltungslösung, um gesetzliche, rechtliche sowie unternehmenskritische Datensätze in ihren Unternehmensdaten zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="a885d-105">Organizations of all types require a records-management solution to manage regulatory, legal, and business-critical records across their corporate data.</span></span> <span data-ttu-id="a885d-106">Die Datensatzverwaltung in Microsoft 365 unterstützt eine Organisation bei der Verwaltung ihrer gesetzlichen Verpflichtungen, bietet die Möglichkeit, die Einhaltung von Vorschriften nachzuweisen und erhöht die Effizienz bei der regelmäßigen Disposition von Elementen, die nicht mehr aufbewahrt werden müssen oder nicht mehr von Wert oder für Geschäftszwecke erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="a885d-106">Records management in Microsoft 365 helps an organization manage their legal obligations, provides the ability to demonstrate compliance with regulations, and increases efficiency with regular disposition of items that are no longer required to be retained, no longer of value, or no longer required for business purposes.</span></span>

<span data-ttu-id="a885d-107">Die Datensatzverwaltungslösung unterstützt die folgenden Elemente:</span><span class="sxs-lookup"><span data-stu-id="a885d-107">The records-management solution supports the following elements:</span></span>

- <span data-ttu-id="a885d-108">**Bezeichnen von Inhalt als Datensatz**</span><span class="sxs-lookup"><span data-stu-id="a885d-108">**Label content as a record**.</span></span> <span data-ttu-id="a885d-109">Erstellen und Veröffentlichen von Aufbewahrungsbezeichnungen, die Inhalte als [Datensätze](records.md) deklarieren, die von Endbenutzern oder [automatisch](labels.md#applying-a-retention-label-automatically-based-on-conditions) durch das identifizieren vertraulicher Informationen, Stichwörter oder Inhaltstypen angewendet werden können.</span><span class="sxs-lookup"><span data-stu-id="a885d-109">Create and publish retention labels that declare content as a [record](records.md) that can then be applied by end users or [auto-applied](labels.md#applying-a-retention-label-automatically-based-on-conditions) by identifying sensitive information, keywords, or content types.</span></span>

- <span data-ttu-id="a885d-110">**Migrieren und verwalten Sie Ihren Aufbewahrungsplan mit einem Dateiplan** und verwenden Sie den [Dateiplan-Manager](file-plan-manager.md), um Ihren bestehenden Aufbewahrungsplan einzubinden oder einen neuen mit Dateideskriptoren zu erstellen und Hierarchien zu expandieren.</span><span class="sxs-lookup"><span data-stu-id="a885d-110">**Migrate and manage your retention plan with file plan** and use [file plan manager](file-plan-manager.md) to bring in your existing retention plan, or build new with file descriptors and expanding hierarchies.</span></span>

- <span data-ttu-id="a885d-111">**Erstellung von Aufbewahrungs- und Löschrichtlinien innerhalb der Datensatzbezeichnung**.</span><span class="sxs-lookup"><span data-stu-id="a885d-111">**Establish retention and deletion policies within the record label**.</span></span> <span data-ttu-id="a885d-112">Definieren Sie Zeiträume für [Aufbewahrung](create-retention-policies.md#retaining-content-for-a-specific-period-of-time) und [Disposition](create-retention-policies.md#deleting-content-thats-older-than-a-specific-age), basierend auf zahlreichen Faktoren, z. B. dem Datum der letzten Änderung oder dem Erstellungsdatum.</span><span class="sxs-lookup"><span data-stu-id="a885d-112">Define [retention](create-retention-policies.md#retaining-content-for-a-specific-period-of-time) and [disposition](create-retention-policies.md#deleting-content-thats-older-than-a-specific-age) periods based on various factors including the date last modified or created.</span></span>

- <span data-ttu-id="a885d-113">**Lösen Sie ereignisbasierte Aufbewahrung** mit [ereignisbasierter Aufbewahrung](event-driven-retention.md) aus.</span><span class="sxs-lookup"><span data-stu-id="a885d-113">**Trigger event-based retention** with [event-based retention](event-driven-retention.md).</span></span>

- <span data-ttu-id="a885d-114">**Überprüfen und validieren Sie die Disposition** mit [Dispositionsüberprüfungen](disposition.md#disposition-reviews) und Nachweis der [Eintragslöschung](disposition.md#disposition-of-records).</span><span class="sxs-lookup"><span data-stu-id="a885d-114">**Review and validate disposition** with [disposition reviews](disposition.md#disposition-reviews) and proof of [records deletion](disposition.md#disposition-of-records).</span></span>

- <span data-ttu-id="a885d-115">**Exportieren Sie Informationen zu allen Elementen**, die mit der [Exportoption](disposition.md#filter-and-export-the-views) verworfen wurden.</span><span class="sxs-lookup"><span data-stu-id="a885d-115">**Export information about all disposed items** with the [export option](disposition.md#filter-and-export-the-views).</span></span>

- <span data-ttu-id="a885d-116">**Legen Sie spezifische Berechtigungen für Datensatzverwalterfunktionen in Ihrer Organisation fest**, um [über den richtigen Zugriff zu verfügen](../security/office-365-security/permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="a885d-116">**Set specific permissions** for records manager functions in your organization to [have the right access](../security/office-365-security/permissions-in-the-security-and-compliance-center.md).</span></span>

<span data-ttu-id="a885d-117">Mit der Datensatzverwalterlösung in Microsoft 365 können Sie die Aufbewahrungspläne Ihrer Organisation in den Dateiplan integrieren, um Aufbewahrung, Deklaration von Datensätzen und Disposition zur Unterstützung des gesamten Inhaltslebenszyklus zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="a885d-117">With the records-management solution in Microsoft 365, you can incorporate your organization’s retention schedules into the file plan to manage retention, records declaration, and disposition to support the full lifecycle of your content.</span></span>
