---
title: Arbeiten mit Kommunikationen in Advanced eDiscovery
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
description: Mit Advanced eDiscovery können Sie den Workflow für rechtliche Aufbewahrungs Benachrichtigungen einfach verwalten, um Benachrichtigungsverwalter in rechtlichen Ermittlungen zu benachrichtigen.
ms.openlocfilehash: 28b719a83cbc1608ad5468e401a8b7946cb8da5f
ms.sourcegitcommit: bd51f626f0c7788c2a3cf89deee25264659aebd5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/17/2020
ms.locfileid: "43551240"
---
# <a name="work-with-communications-in-advanced-ediscovery"></a><span data-ttu-id="ace2c-103">Arbeiten mit Kommunikationen in Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="ace2c-103">Work with communications in Advanced eDiscovery</span></span>

<span data-ttu-id="ace2c-104">Advanced eDiscovery ermöglicht juristischen Abteilungen, Ihre Prozesse bei der Verfolgung und Verteilung von Benachrichtigungen über rechtliche Aufbewahrungsfristen zu vereinfachen.</span><span class="sxs-lookup"><span data-stu-id="ace2c-104">Advanced eDiscovery allows legal departments to simplify their processes around tracking and distributing legal hold notifications.</span></span> <span data-ttu-id="ace2c-105">Das Tool "Depotbank-Kommunikation" ermöglicht es juristischen Abteilungen, den gesamten rechtlichen Aufbewahrungs Prozess, von erst Benachrichtigungen über Erinnerungen bis hin zu Eskalationen, an einem einzigen Ort zu verwalten und zu automatisieren.</span><span class="sxs-lookup"><span data-stu-id="ace2c-105">The custodian communications tool enables legal departments to manage and automate the entire legal hold process, from initial notifications, to reminders, and to escalations, all in one location.</span></span>

## <a name="what-is-a-legal-hold-notification"></a><span data-ttu-id="ace2c-106">Was ist eine rechtliche Aufbewahrungs Benachrichtigung?</span><span class="sxs-lookup"><span data-stu-id="ace2c-106">What is a legal hold notification?</span></span>

<span data-ttu-id="ace2c-107">Eine rechtliche Aufbewahrungspflicht (auch als *Beweissicherungsverfahren*bezeichnet) ist eine Benachrichtigung, die von der Rechtsabteilung einer Organisation an Mitarbeiter, Kontingente Mitarbeiter oder Verwalter von Daten gesendet wird, die möglicherweise für eine rechtliche Untersuchung relevant sind.</span><span class="sxs-lookup"><span data-stu-id="ace2c-107">A legal hold (also known as a *litigation hold*) notice is a notification sent from an organization’s legal department to employees, contingent staff, or custodians of data that may be relevant to a legal investigation.</span></span> <span data-ttu-id="ace2c-108">Diese Benachrichtigungen weisen Verwalter an, elektronisch gespeicherte Informationen sowie alle Inhalte beizubehalten, die für eine aktive oder bevorstehende Rechtsfrage relevant sein können.</span><span class="sxs-lookup"><span data-stu-id="ace2c-108">These notifications instruct custodians to preserve electronically stored information as well as any content that may be relevant to an active or impending legal matter.</span></span> <span data-ttu-id="ace2c-109">Juristische Teams müssen wissen, dass jede Depotbank die angegebenen Anweisungen erhalten, gelesen, verstanden und vereinbart hat.</span><span class="sxs-lookup"><span data-stu-id="ace2c-109">Legal teams must know that each custodian has received, read, understood, and has agreed to comply with the given instructions.</span></span>

## <a name="the-legal-hold-notification-process"></a><span data-ttu-id="ace2c-110">Benachrichtigungsprozess für Legal Hold</span><span class="sxs-lookup"><span data-stu-id="ace2c-110">The legal hold notification process</span></span>

<span data-ttu-id="ace2c-111">Eine Organisation hat die Pflicht, relevante Informationen beizubehalten, wenn Sie von einer bevorstehenden Rechtsstreitigkeiten oder behördlichen Untersuchung erfahren.</span><span class="sxs-lookup"><span data-stu-id="ace2c-111">An organization has a duty to preserve relevant information when it learns about an impending litigation or regulatory investigation.</span></span> <span data-ttu-id="ace2c-112">Um die Aufbewahrungsanforderungen einer Untersuchung einzuhalten, sollte die Organisation potenzielle Verwalter unverzüglich über ihre Pflicht zur Wahrung relevanter Informationen informieren.</span><span class="sxs-lookup"><span data-stu-id="ace2c-112">To comply with the preservation requirements of an investigation, the organization should immediately inform potential custodians about their duty to preserve relevant information.</span></span>

<span data-ttu-id="ace2c-113">Mit Advanced eDiscovery können Legal Teams ihren rechtlichen Aufbewahrungs Benachrichtigungs Workflow erstellen und anpassen.</span><span class="sxs-lookup"><span data-stu-id="ace2c-113">With Advanced eDiscovery, legal teams can create and customize their legal hold notification workflow.</span></span> <span data-ttu-id="ace2c-114">Das Tool "Depotbank-Kommunikation" ermöglicht es juristischen Teams, die folgenden Hinweise und Workflows zu konfigurieren:</span><span class="sxs-lookup"><span data-stu-id="ace2c-114">The custodian communications tool lets legal teams to configure the following notices and workflows:</span></span>

1. <span data-ttu-id="ace2c-115">**Veröffentlichungshinweis:** Eine rechtliche Aufbewahrungsfrist wird durch eine Mitteilung der Rechtsabteilung an Verwalter ausgestellt (oder eingeleitet), die möglicherweise relevante Informationen zum Fall haben.</span><span class="sxs-lookup"><span data-stu-id="ace2c-115">**Issuance notice:** A legal hold notice is issued (or initiated) by a notification from the legal department to custodians who may have relevant information about the case matter.</span></span> <span data-ttu-id="ace2c-116">In diesem Hinweis werden die Verwalter angehalten, alle Informationen beizubehalten, die für die Ermittlung möglicherweise erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="ace2c-116">This notice instructs the custodians to preserve any information that may be needed for discovery.</span></span>

2. <span data-ttu-id="ace2c-117">**Hinweis zur erneuten Veröffentlichung:** In einem Fall müssen Verwalter möglicherweise zusätzliche Inhalte (oder weniger Inhalte) aufbewahren, als zuvor angefordert wurden.</span><span class="sxs-lookup"><span data-stu-id="ace2c-117">**Re-Issuance notice:** During a case, custodians may be required to preserve additional content (or less content) than was previously requested.</span></span> <span data-ttu-id="ace2c-118">In diesem Szenario können Sie den vorhandenen Aufbewahrungs Hinweis aktualisieren und ihn erneut an Verwalter ausgeben.</span><span class="sxs-lookup"><span data-stu-id="ace2c-118">For this scenario, you can update the existing hold notice and re-issue it to custodians.</span></span>

3. <span data-ttu-id="ace2c-119">**Veröffentlichungshinweis:** Sobald ein Problem gelöst ist und die Depotbank nicht mehr einer Aufbewahrungspflicht unterliegt, kann die Depotbank aus dem Fall entlassen werden.</span><span class="sxs-lookup"><span data-stu-id="ace2c-119">**Release notice:** Once a matter is resolved and the custodian is no longer subject to a preservation requirement, the custodian can be released from the case.</span></span> <span data-ttu-id="ace2c-120">Darüber hinaus können Sie die Depotbank darüber informieren, dass Sie nicht mehr für die Aufbewahrung von Inhalten benötigt werden, und Anweisungen zum Fortsetzen ihrer normalen Arbeitsaktivität im Hinblick auf Ihre Daten geben.</span><span class="sxs-lookup"><span data-stu-id="ace2c-120">Additionally, you can notify the custodian that they are no longer required to preserve content, and provide instructions about how to resume their normal work activity with regard to their data.</span></span>

4. <span data-ttu-id="ace2c-121">**Erinnerungen und Eskalationen:** In einigen Fällen genügt ein Hinweis nur, um die Anforderungen an die rechtliche Ermittlung zu erfüllen.</span><span class="sxs-lookup"><span data-stu-id="ace2c-121">**Reminders and escalations:** In some instances, just issuing a notice isn't enough to satisfy legal discovery requirements.</span></span> <span data-ttu-id="ace2c-122">Mit jeder Benachrichtigung können Legal Teams einen Mahn-und Eskalations Workflow planen, um nicht reagierende depotverwalter automatisch zu verfolgen.</span><span class="sxs-lookup"><span data-stu-id="ace2c-122">With each notification, legal teams can schedule a set of reminder and escalation workflows to automatically follow up with unresponsive custodians.</span></span>

   - <span data-ttu-id="ace2c-123">**Erinnerungen:** Nachdem ein rechtlicher Aufbewahrungs Bescheid für eine Reihe von Depotstellen ausgestellt oder erneut ausgestellt wurde, kann eine Organisation Erinnerungen einrichten, um nicht reagierende Verwalter zu warnen.</span><span class="sxs-lookup"><span data-stu-id="ace2c-123">**Reminders:** After a legal hold notice has been issued or re-issued to a set of custodians, an organization can set up reminders to alert unresponsive custodians.</span></span>

   - <span data-ttu-id="ace2c-124">**Eskalationen:** In einigen Fällen kann das juristische Team einen Eskalations Workflow einrichten, um nicht reagierende Verwalter und deren Vorgesetzten zu benachrichtigen, wenn eine Depotbank auch nach einer Reihe von Erinnerungen über einen bestimmten Zeitraum nicht mehr reagiert.</span><span class="sxs-lookup"><span data-stu-id="ace2c-124">**Escalations:** In some cases, if a custodian remains unresponsive even after a set of reminders over a period of time, the legal team can set up an escalation workflow to notify unresponsive custodians and their manager.</span></span>

<span data-ttu-id="ace2c-125">Weitere Informationen zum Verwalten des Depotbank-Kommunikationsprozesses finden Sie in den folgenden Themen:</span><span class="sxs-lookup"><span data-stu-id="ace2c-125">For more information about managing the custodian communication process, see the following:</span></span> 

- [<span data-ttu-id="ace2c-126">Erstellen eines rechtlichen Aufbewahrungs Vermerks</span><span class="sxs-lookup"><span data-stu-id="ace2c-126">Create a legal hold notice</span></span>](create-hold-notification.md)

- [<span data-ttu-id="ace2c-127">Verwenden des Kommunikations-Editors</span><span class="sxs-lookup"><span data-stu-id="ace2c-127">Use the communications editor</span></span>](using-communications-editor.md)

- [<span data-ttu-id="ace2c-128">Verwalten von Aufbewahrungsbenachrichtigungen</span><span class="sxs-lookup"><span data-stu-id="ace2c-128">Manage hold notifications</span></span>](manage-hold-notification.md)

- [<span data-ttu-id="ace2c-129">Bestätigen einer Aufbewahrungsbenachrichtigung</span><span class="sxs-lookup"><span data-stu-id="ace2c-129">Acknowledge a hold notification</span></span>](acknowledge-hold-notification.md)