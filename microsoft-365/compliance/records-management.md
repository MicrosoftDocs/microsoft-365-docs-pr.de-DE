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
ms.openlocfilehash: dcc3e5666bcd438a046d535cf9fce88910b85ad7
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2020
ms.locfileid: "41597652"
---
# <a name="records-management-in-microsoft-365"></a><span data-ttu-id="4afb9-103">Datensatzverwaltung in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="4afb9-103">Records management in Microsoft 365</span></span>

<span data-ttu-id="4afb9-104">Organisationen aller Art benötigen eine Datensatzverwaltungslösung, um gesetzliche, rechtliche sowie unternehmenskritische Datensätze in ihren Unternehmensdaten zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="4afb9-104">Organizations of all types require a records-management solution to manage regulatory, legal, and business-critical records across their corporate data.</span></span> <span data-ttu-id="4afb9-105">Die Datensatzverwaltung in Microsoft 365 unterstützt eine Organisation bei der Verwaltung ihrer gesetzlichen Verpflichtungen, bietet die Möglichkeit, die Einhaltung von Vorschriften nachzuweisen und erhöht die Effizienz bei der regelmäßigen Disposition von Elementen, die nicht mehr aufbewahrt werden müssen oder nicht mehr von Wert oder für Geschäftszwecke erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="4afb9-105">Records management in Microsoft 365 helps an organization manage their legal obligations, provides the ability to demonstrate compliance with regulations, and increases efficiency with regular disposition of items that are no longer required to be retained, no longer of value, or no longer required for business purposes.</span></span>

<span data-ttu-id="4afb9-106">Die Datensatzverwaltungslösung unterstützt die folgenden Elemente:</span><span class="sxs-lookup"><span data-stu-id="4afb9-106">The records-management solution supports the following elements:</span></span>

- <span data-ttu-id="4afb9-107">**Bezeichnen von Inhalt als Datensatz**</span><span class="sxs-lookup"><span data-stu-id="4afb9-107">**Label content as a record**.</span></span> <span data-ttu-id="4afb9-108">Veröffentlichen Sie [Datensatzbezeichnungen](records.md), die von Endbenutzern angewendet werden sollen, oder lassen Sie [Datensatzbezeichnungen automatisch auf Elemente anwenden](labels.md#applying-a-retention-label-automatically-based-on-conditions), die bestimmte sensible Informationen, Schlüsselwörter oder Inhaltstypen enthalten.</span><span class="sxs-lookup"><span data-stu-id="4afb9-108">Publish [record labels](records.md) to be applied by end users or [auto-apply](labels.md#applying-a-retention-label-automatically-based-on-conditions) record labels to items containing specific sensitive information, keywords, or content types.</span></span>

- <span data-ttu-id="4afb9-109">**Migrieren und verwalten Sie Ihren Aufbewahrungsplan mit einem Dateiplan** und verwenden Sie den [Dateiplan-Manager](file-plan-manager.md), um Ihren bestehenden Aufbewahrungsplan einzubinden oder einen neuen mit Dateideskriptoren zu erstellen und Hierarchien zu expandieren.</span><span class="sxs-lookup"><span data-stu-id="4afb9-109">**Migrate and manage your retention plan with file plan** and use [file plan manager](file-plan-manager.md) to bring in your existing retention plan, or build new with file descriptors and expanding hierarchies.</span></span>

- <span data-ttu-id="4afb9-110">**Erstellung von Aufbewahrungs- und Löschrichtlinien innerhalb der Datensatzbezeichnung**.</span><span class="sxs-lookup"><span data-stu-id="4afb9-110">**Establish retention and deletion policies within the record label**.</span></span> <span data-ttu-id="4afb9-111">Definieren Sie Zeiträume für [Aufbewahrung](retention-policies.md#retaining-content-for-a-specific-period-of-time) und [Disposition](retention-policies.md#deleting-content-thats-older-than-a-specific-age), basierend auf zahlreichen Faktoren, z. B. dem Datum der letzten Änderung oder dem Erstellungsdatum.</span><span class="sxs-lookup"><span data-stu-id="4afb9-111">Define [retention](retention-policies.md#retaining-content-for-a-specific-period-of-time) and [disposition](retention-policies.md#deleting-content-thats-older-than-a-specific-age) periods based on various factors including the date last modified or created.</span></span>

- <span data-ttu-id="4afb9-112">**Lösen Sie ereignisbasierte Aufbewahrung** mit [ereignisbasierter Aufbewahrung](event-driven-retention.md) aus.</span><span class="sxs-lookup"><span data-stu-id="4afb9-112">**Trigger event-based retention** with [event-based retention](event-driven-retention.md).</span></span>

- <span data-ttu-id="4afb9-113">**Überprüfen und validieren Sie die Disposition** mit [Dispositionsüberprüfungen](disposition-reviews.md).</span><span class="sxs-lookup"><span data-stu-id="4afb9-113">**Review and validate disposition** with [disposition review](disposition-reviews.md).</span></span>

- <span data-ttu-id="4afb9-114">**Überprüfen Sie die verworfenen Elemente mit Dispositionsüberprüfungen** und [exportieren Sie einen Dispositionsbericht](disposition-reviews.md#export-the-disposition-items) für weitere Validierungen und Berichte.</span><span class="sxs-lookup"><span data-stu-id="4afb9-114">**Review disposed items with disposition review** and [export a disposition report](disposition-reviews.md#export-the-disposition-items) for further validation and reporting.</span></span>

- <span data-ttu-id="4afb9-115">**Legen Sie spezifische Berechtigungen für Datensatzverwalterfunktionen in Ihrer Organisation fest**, um [über den richtigen Zugriff zu verfügen](../security/office-365-security/permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="4afb9-115">**Set specific permissions** for records manager functions in your organization to [have the right access](../security/office-365-security/permissions-in-the-security-and-compliance-center.md).</span></span>

<span data-ttu-id="4afb9-116">Mit der Datensatzverwalterlösung in Microsoft 365 können Sie die Aufbewahrungspläne Ihrer Organisation in den Dateiplan integrieren, um Aufbewahrung, Deklaration von Datensätzen und Disposition zur Unterstützung des gesamten Inhaltslebenszyklus zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="4afb9-116">With the records-management solution in Microsoft 365, you can incorporate your organization’s retention schedules into the file plan to manage retention, records declaration, and disposition in support of the full content lifecycle.</span></span>
