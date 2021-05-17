---
title: Arbeiten mit Verwahrern in Advanced eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
ms.custom:
- seo-marvel-apr2020
description: Erfahren Sie, wie Sie das Verwaltungstool für Custodian in Advanced eDiscovery verwenden, um Daten für einen Rechtsstreit zu verwalten.
ms.openlocfilehash: 22297edbf73f561ad46e5fae521abeb371fdc88d
ms.sourcegitcommit: 6501e01a9ab131205a3eef910e6cea7f65b3f010
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/30/2020
ms.locfileid: "46528131"
---
# <a name="work-with-custodians-and-non-custodial-data-sources-in-advanced-ediscovery"></a><span data-ttu-id="7a51e-103">Arbeiten mit Verwahrern und nicht verwahrten Datenquellen in Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="7a51e-103">Work with custodians and non-custodial data sources in Advanced eDiscovery</span></span>

<span data-ttu-id="7a51e-104">Wenn eine Organisation auf eine rechtliche Untersuchung reagiert, basiert der Workflow zum Identifizieren, Beibehalten und Sammeln potenziell relevanter Inhalte auf den Personen in der Organisation, die die Mittler relevanter Daten sind.</span><span class="sxs-lookup"><span data-stu-id="7a51e-104">When an organization responds to a legal investigation, the workflow around identifying, preserving, and collecting potentially relevant content is based on the people in the organization who are the custodians of relevant data.</span></span> <span data-ttu-id="7a51e-105">In eDiscovery werden diese Personen als Datenverwahrer *(oder* nur Verwahrer) bezeichnet und als "Personen mit administrativer Kontrolle über ein Dokument oder eine elektronische Datei" definiert.</span><span class="sxs-lookup"><span data-stu-id="7a51e-105">In eDiscovery, these individuals are called *data custodians* (or just *custodians*) and are defined as "persons having administrative control of a document or electronic file".</span></span> <span data-ttu-id="7a51e-106">So könnte beispielsweise der Verwalter einer E-Mail-Nachricht der Besitzer des Postfachs sein, das die relevante Nachricht enthält.</span><span class="sxs-lookup"><span data-stu-id="7a51e-106">For example, the custodian of an email message could be the owner of the mailbox that contains the relevant message.</span></span>

<span data-ttu-id="7a51e-107">Darüber hinaus können sich Inhalte in Postfächern und Websites befinden, die keinem Verwahrer zugeordnet sind, aber für den Fall relevant sind.</span><span class="sxs-lookup"><span data-stu-id="7a51e-107">Additionally, there may be content located in mailboxes and sites that aren't associated with a custodian but that's relevant to the case.</span></span> <span data-ttu-id="7a51e-108">Inhaltsspeicherorte, an denen Fallverwahrer keine administrative Kontrolle haben, aber möglicherweise Besitzer relevanter Daten sind, werden als nicht verwahrte *Datenquellen bezeichnet.*</span><span class="sxs-lookup"><span data-stu-id="7a51e-108">Content locations where case custodians don't have administrative control but may be owners of relevant data, are known as *non-custodial data sources*.</span></span>

<span data-ttu-id="7a51e-109">In einem Advanced eDiscovery können Rechtsteams Personen in ihrer Organisation als Verwahrer hinzufügen und Verwahrerdatenquellen wie Exchange-Postfächer, OneDrive-Konten sowie SharePoint- und Teams-Websites identifizieren und beibehalten.</span><span class="sxs-lookup"><span data-stu-id="7a51e-109">In an Advanced eDiscovery case, legal teams can add individuals in their organization as custodians, and  identify and preserve custodial data sources such as Exchange mailboxes, OneDrive accounts, and SharePoint and Teams sites.</span></span> <span data-ttu-id="7a51e-110">Sie können auch nicht verwahrte Datenquellen identifizieren und beibehalten.</span><span class="sxs-lookup"><span data-stu-id="7a51e-110">They can also identify and preserve non-custodial data sources.</span></span> <span data-ttu-id="7a51e-111">Mithilfe des integrierten Verwaltungstools für Custodian und Datenquellen in Advanced eDiscovery können Organisationen elektronisch gespeicherte Informationen vor versehentlicher (oder beabsichtigter) Löschung sichern.</span><span class="sxs-lookup"><span data-stu-id="7a51e-111">By using the built-in custodian and data source management tool in Advanced eDiscovery, organizations can secure electronically stored information from inadvertent (or intentional) deletion.</span></span> <span data-ttu-id="7a51e-112">Auf diese Weise können Sie den zeitaufwändigen und fehleranfälligen Prozess der manuellen Durchführung der Prozesse für die gesetzliche Auflage vermeiden.</span><span class="sxs-lookup"><span data-stu-id="7a51e-112">This lets you eliminate the time-consuming and error-prone process of manually having to perform the legal hold processes.</span></span>

<span data-ttu-id="7a51e-113">Weitere Informationen zum Arbeiten mit Verwahrern finden Sie in den folgenden Artikeln:</span><span class="sxs-lookup"><span data-stu-id="7a51e-113">For more information about working with custodians, see the following articles:</span></span>

- [<span data-ttu-id="7a51e-114">Hinzufügen von Verwaltungsberechtigten zu einem Fall</span><span class="sxs-lookup"><span data-stu-id="7a51e-114">Add custodians to a case</span></span>](add-custodians-to-case.md)

- [<span data-ttu-id="7a51e-115">Massenhinzufügung von Verwaltungsberechtigten zu einem Fall</span><span class="sxs-lookup"><span data-stu-id="7a51e-115">Bulk-add custodians to a case</span></span>](bulk-add-custodians.md)

- [<span data-ttu-id="7a51e-116">Verwalten von Verwahrern in einem Fall</span><span class="sxs-lookup"><span data-stu-id="7a51e-116">Manage custodians in a case</span></span>](manage-new-custodians.md)

- [<span data-ttu-id="7a51e-117">Anzeigen der Aktivitäten von Verwaltungsberechtigten</span><span class="sxs-lookup"><span data-stu-id="7a51e-117">View custodian activity</span></span>](view-custodian-activity.md)

- [<span data-ttu-id="7a51e-118">Hinzufügen von nicht-verwahrten Datenquellen zu einem Fall</span><span class="sxs-lookup"><span data-stu-id="7a51e-118">Add non-custodial data sources to a case</span></span>](non-custodial-data-sources.md)
