---
title: Arbeiten mit kommunikation in Advanced eDiscovery
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
description: Advanced eDiscovery erleichtert die Verwaltung des Benachrichtigungsworkflows für gesetzliche Benachrichtigungen rund um die Benachrichtigung von Verwahrern in juristischen Untersuchungen.
ms.openlocfilehash: 28b719a83cbc1608ad5468e401a8b7946cb8da5f
ms.sourcegitcommit: bd51f626f0c7788c2a3cf89deee25264659aebd5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/17/2020
ms.locfileid: "43551240"
---
# <a name="work-with-communications-in-advanced-ediscovery"></a><span data-ttu-id="f2502-103">Arbeiten mit kommunikation in Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="f2502-103">Work with communications in Advanced eDiscovery</span></span>

<span data-ttu-id="f2502-104">Advanced eDiscovery ermöglicht es Rechtsabteilungen, ihre Prozesse im Rahmen der Nachverfolgung und Verteilung von Benachrichtigungen über gesetzliche Benachrichtigungen zu vereinfachen.</span><span class="sxs-lookup"><span data-stu-id="f2502-104">Advanced eDiscovery allows legal departments to simplify their processes around tracking and distributing legal hold notifications.</span></span> <span data-ttu-id="f2502-105">Das Kommunikationstool des Wahrerdienstes ermöglicht es rechtsabteilungen, den gesamten Prozess der rechtlichen Benachrichtigungen zu verwalten und zu automatisieren, von anfänglichen Benachrichtigungen über Erinnerungen bis zu Eskalationen, und dies alles an einem einzigen Ort.</span><span class="sxs-lookup"><span data-stu-id="f2502-105">The custodian communications tool enables legal departments to manage and automate the entire legal hold process, from initial notifications, to reminders, and to escalations, all in one location.</span></span>

## <a name="what-is-a-legal-hold-notification"></a><span data-ttu-id="f2502-106">Was ist eine Gesetzliche Haltebenachrichtigung?</span><span class="sxs-lookup"><span data-stu-id="f2502-106">What is a legal hold notification?</span></span>

<span data-ttu-id="f2502-107">Ein Rechtlicher Haltebereich (auch bekannt als Rechtsstreitigkeiten ) ist eine Benachrichtigung, die von der Rechtsabteilung einer Organisation an Mitarbeiter, Kontingentmitarbeiter oder Verwahrer von Daten gesendet wird, die für eine rechtliche Untersuchung relevant sein können.</span><span class="sxs-lookup"><span data-stu-id="f2502-107">A legal hold (also known as a *litigation hold*) notice is a notification sent from an organization’s legal department to employees, contingent staff, or custodians of data that may be relevant to a legal investigation.</span></span> <span data-ttu-id="f2502-108">In diesen Benachrichtigungen werden Beauftragte angewiesen, elektronisch gespeicherte Informationen sowie Inhalte zu speichern, die für eine aktive oder bevorstehende Rechtssache relevant sein können.</span><span class="sxs-lookup"><span data-stu-id="f2502-108">These notifications instruct custodians to preserve electronically stored information as well as any content that may be relevant to an active or impending legal matter.</span></span> <span data-ttu-id="f2502-109">Die Rechtsteams müssen wissen, dass jeder Custodian die angegebenen Anweisungen erhalten, gelesen, verstanden und zugestimmt hat.</span><span class="sxs-lookup"><span data-stu-id="f2502-109">Legal teams must know that each custodian has received, read, understood, and has agreed to comply with the given instructions.</span></span>

## <a name="the-legal-hold-notification-process"></a><span data-ttu-id="f2502-110">Benachrichtigungsverfahren für gesetzliches Halteverfahren</span><span class="sxs-lookup"><span data-stu-id="f2502-110">The legal hold notification process</span></span>

<span data-ttu-id="f2502-111">Eine Organisation ist verpflichtet, relevante Informationen zu erhalten, wenn sie von einer bevorstehenden Rechtsstreitigkeiten oder behördlichen Untersuchung erfahren.</span><span class="sxs-lookup"><span data-stu-id="f2502-111">An organization has a duty to preserve relevant information when it learns about an impending litigation or regulatory investigation.</span></span> <span data-ttu-id="f2502-112">Um die Erhaltungsanforderungen einer Untersuchung zu erfüllen, sollte die Organisation potenzielle Verwahrer sofort über ihre Pflicht zur Aufbewahrung relevanter Informationen informieren.</span><span class="sxs-lookup"><span data-stu-id="f2502-112">To comply with the preservation requirements of an investigation, the organization should immediately inform potential custodians about their duty to preserve relevant information.</span></span>

<span data-ttu-id="f2502-113">Mit Advanced eDiscovery können Rechtsteams ihren Benachrichtigungsworkflow für gesetzliches Haltebereich erstellen und anpassen.</span><span class="sxs-lookup"><span data-stu-id="f2502-113">With Advanced eDiscovery, legal teams can create and customize their legal hold notification workflow.</span></span> <span data-ttu-id="f2502-114">Mit dem Kommunikationstool für Custodian können Rechtsteams die folgenden Hinweise und Workflows konfigurieren:</span><span class="sxs-lookup"><span data-stu-id="f2502-114">The custodian communications tool lets legal teams to configure the following notices and workflows:</span></span>

1. <span data-ttu-id="f2502-115">**Benachrichtigung zur Ausstellung:** Ein Rechtlicher Haltebemerkung wird durch eine Benachrichtigung der Rechtsabteilung an Verwahrer ausgegeben (oder initiiert), die über relevante Informationen zu dem Fall verfügen.</span><span class="sxs-lookup"><span data-stu-id="f2502-115">**Issuance notice:** A legal hold notice is issued (or initiated) by a notification from the legal department to custodians who may have relevant information about the case matter.</span></span> <span data-ttu-id="f2502-116">Diese Benachrichtigung weist die Verwalter an, alle Informationen, die für die Ermittlung benötigt werden könnten, aufzubewahren.</span><span class="sxs-lookup"><span data-stu-id="f2502-116">This notice instructs the custodians to preserve any information that may be needed for discovery.</span></span>

2. <span data-ttu-id="f2502-117">**Benachrichtigung zur erneuten Ausstellung:** Während eines Falls müssen Verwahrer möglicherweise zusätzliche Inhalte (oder weniger Inhalte) beibehalten, als zuvor angefordert wurden.</span><span class="sxs-lookup"><span data-stu-id="f2502-117">**Re-Issuance notice:** During a case, custodians may be required to preserve additional content (or less content) than was previously requested.</span></span> <span data-ttu-id="f2502-118">In diesem Szenario können Sie den vorhandenen Haltehinweise aktualisieren und erneut an Verwahrer ausheften.</span><span class="sxs-lookup"><span data-stu-id="f2502-118">For this scenario, you can update the existing hold notice and re-issue it to custodians.</span></span>

3. <span data-ttu-id="f2502-119">**Veröffentlichungshinweise:** Sobald eine Sache gelöst wurde und der Custodian keiner Aufbewahrungsanforderung mehr unterliegt, kann der Custodian aus dem Fall entlassen werden.</span><span class="sxs-lookup"><span data-stu-id="f2502-119">**Release notice:** Once a matter is resolved and the custodian is no longer subject to a preservation requirement, the custodian can be released from the case.</span></span> <span data-ttu-id="f2502-120">Darüber hinaus können Sie den Verwahrer darüber informieren, dass er keine Inhalte mehr beibehalten muss, und Anweisungen zum Fortsetzen der normalen Arbeitsaktivität in Bezug auf ihre Daten bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="f2502-120">Additionally, you can notify the custodian that they are no longer required to preserve content, and provide instructions about how to resume their normal work activity with regard to their data.</span></span>

4. <span data-ttu-id="f2502-121">**Erinnerungen und Eskalationen:** In einigen Fällen reicht die Benachrichtigung nicht aus, um gesetzliche Ermittlungsanforderungen zu erfüllen.</span><span class="sxs-lookup"><span data-stu-id="f2502-121">**Reminders and escalations:** In some instances, just issuing a notice isn't enough to satisfy legal discovery requirements.</span></span> <span data-ttu-id="f2502-122">Mit jeder Benachrichtigung können Rechtsabteilungen eine Reihe von Erinnerungs- und Eskalations-Workflows planen, damit nicht reagierende Verwalter automatisch nachverfolgt werden.</span><span class="sxs-lookup"><span data-stu-id="f2502-122">With each notification, legal teams can schedule a set of reminder and escalation workflows to automatically follow up with unresponsive custodians.</span></span>

   - <span data-ttu-id="f2502-123">**Erinnerungen:** Nachdem eine gesetzliche Haltebenachrichtigung an eine Gruppe von Verwahrern ausgestellt oder erneut ausgestellt wurde, kann eine Organisation Erinnerungen einrichten, um nicht reagierende Verwahrer zu warnen.</span><span class="sxs-lookup"><span data-stu-id="f2502-123">**Reminders:** After a legal hold notice has been issued or re-issued to a set of custodians, an organization can set up reminders to alert unresponsive custodians.</span></span>

   - <span data-ttu-id="f2502-124">**Eskalationen:** Wenn ein Verwalter auch nach einer Reihe von Erinnerungen über einen bestimmten Zeitraum nicht reagiert, kann das Rechtsteam in einigen Fällen einen Eskalationsworkflow einrichten, um nicht reagierende Verwalter und deren Vorgesetzte zu benachrichtigen.</span><span class="sxs-lookup"><span data-stu-id="f2502-124">**Escalations:** In some cases, if a custodian remains unresponsive even after a set of reminders over a period of time, the legal team can set up an escalation workflow to notify unresponsive custodians and their manager.</span></span>

<span data-ttu-id="f2502-125">Weitere Informationen zum Verwalten des Custodian-Kommunikationsprozesses finden Sie unter:</span><span class="sxs-lookup"><span data-stu-id="f2502-125">For more information about managing the custodian communication process, see the following:</span></span> 

- [<span data-ttu-id="f2502-126">Erstellen eines Rechtlichen Haltehinweises</span><span class="sxs-lookup"><span data-stu-id="f2502-126">Create a legal hold notice</span></span>](create-hold-notification.md)

- [<span data-ttu-id="f2502-127">Verwenden des Kommunikations-Editors</span><span class="sxs-lookup"><span data-stu-id="f2502-127">Use the communications editor</span></span>](using-communications-editor.md)

- [<span data-ttu-id="f2502-128">Verwalten von Aufbewahrungsbenachrichtigungen</span><span class="sxs-lookup"><span data-stu-id="f2502-128">Manage hold notifications</span></span>](manage-hold-notification.md)

- [<span data-ttu-id="f2502-129">Bestätigen einer Aufbewahrungsbenachrichtigung</span><span class="sxs-lookup"><span data-stu-id="f2502-129">Acknowledge a hold notification</span></span>](acknowledge-hold-notification.md)