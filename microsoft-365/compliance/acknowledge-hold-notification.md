---
title: Bestätigen einer Aufbewahrungsbenachrichtigung
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
description: Erfahren Sie, wie Advanced eDiscovery verwenden, um Benachrichtigungen über das gesetzliche Haltestatus per E-Mail zu senden und zu verfolgen sowie den Status der Verpflichtung zu überwachen.
ms.openlocfilehash: 393d8884a4d4d39056267666fdce6a2754cb582b
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/05/2020
ms.locfileid: "44034885"
---
# <a name="acknowledge-a-hold-notification"></a><span data-ttu-id="e418c-103">Bestätigen einer Aufbewahrungsbenachrichtigung</span><span class="sxs-lookup"><span data-stu-id="e418c-103">Acknowledge a hold notification</span></span>

<span data-ttu-id="e418c-104">Wenn Sie auf eine behördliche Anforderung oder Untersuchung reagieren, müssen Sie die Verwahrer möglicherweise darüber informieren, dass sie verpflichtet sind, elektronisch gespeicherte Informationen (ESI) und alle Materialien zu speichern, die für eine aktive oder unmittelbar bevorstehende Rechtssache relevant sein können.</span><span class="sxs-lookup"><span data-stu-id="e418c-104">When responding to a regulatory request or investigation, you may be required to inform custodians of their obligation to preserve electronically stored information (ESI) and any material that may be relevant to an active or imminent legal matter.</span></span> <span data-ttu-id="e418c-105">Nachdem sie gesendet wurden, müssen die Rechtsteams wissen, dass jeder Custodian die angegebenen Anweisungen erhalten, gelesen, verstanden und zugestimmt hat.</span><span class="sxs-lookup"><span data-stu-id="e418c-105">Once sent, legal teams must know that each custodian has received, read, understood, and agreed to follow the given instructions.</span></span>

<span data-ttu-id="e418c-106">Um die Zeit, die Kosten und den Aufwand für die Nachhilfe bei Ihren Verwahrern zu reduzieren, können Sie Advanced eDiscovery Benachrichtigungen über das gesetzliche Halterecht per E-Mail senden und verfolgen.</span><span class="sxs-lookup"><span data-stu-id="e418c-106">To help reduce the time, cost, and effort of following up with your custodians,  Advanced eDiscovery allows you to send and follow up on legal hold notifications through email.</span></span> <span data-ttu-id="e418c-107">Zusätzlich zu E-Mail-Benachrichtigungen hat jeder Benachrichtigungsverwahrer Zugriff auf ein individualisiertes Complianceportal, sodass Custodians über Änderungen am Verpflichtungsstatus informiert werden können.</span><span class="sxs-lookup"><span data-stu-id="e418c-107">In addition to email notices, each custodian will have access to an individualized Compliance Portal, allowing custodians to be kept informed of changes to their obligation status.</span></span>

## <a name="email-notifications"></a><span data-ttu-id="e418c-108">E-Mail-Benachrichtigungen</span><span class="sxs-lookup"><span data-stu-id="e418c-108">Email notifications</span></span>

<span data-ttu-id="e418c-109">Nachdem eine Benachrichtigung über das gesetzliche Halterecht ausgegeben wurde, erhält jeder Custodian eine eindeutige und personalisierte E-Mail mit Ihrem definierten Rechtlichen Haltebemerkung und hinzugefügten Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="e418c-109">After a Legal Hold Notification has been issued, each custodian will receive a unique and personalized email containing your defined legal hold notice and added instructions.</span></span> 

> [!TIP]
> <span data-ttu-id="e418c-110">Erfahren Sie, wie Sie den integrierten  [Kommunikations-Editor](using-communications-editor.md) verwenden können, um Ihren Verwahrern zu ermöglichen, ihre Benachrichtigung zu bestätigen oder direkt über ihre E-Mail auf ihr Complianceportal zu zugreifen.</span><span class="sxs-lookup"><span data-stu-id="e418c-110">See how you can use the built-in  [Communication Editor](using-communications-editor.md) to allow your custodians to acknowledge their notice or access their Compliance Portal directly from their email.</span></span>

<span data-ttu-id="e418c-111">Basierend auf der Konfiguration Ihrer Benachrichtigung über das gesetzliche Halterecht erhalten Ihre Verwahrer möglicherweise die folgenden Benachrichtigungen:</span><span class="sxs-lookup"><span data-stu-id="e418c-111">Based on the configuration of your legal hold notification, your custodians may receive the following notices:</span></span> 

- <span data-ttu-id="e418c-112">**Benachrichtigung zur Ausstellung:** Der erste Hinweis, der an Ihren Custodian gesendet wurde.</span><span class="sxs-lookup"><span data-stu-id="e418c-112">**Issuance notice:** The first notice sent to your custodian.</span></span> <span data-ttu-id="e418c-113">Dieser Hinweis enthält Ihre Ausstellungsanweisungen und die Haltebenachrichtigung, die am Ende Ihrer Nachricht angefügt ist.</span><span class="sxs-lookup"><span data-stu-id="e418c-113">This notice will contain your issuance instructions and the hold notice appended to the end of your message.</span></span>

- <span data-ttu-id="e418c-114">**Erinnerungsbenachrichtigung:** Wenn diese Option aktiviert ist, wird eine Erinnerungsbenachrichtigung basierend auf der angegebenen Häufigkeit und dem angegebenen Intervall an Ihre Verwahrer gesendet.</span><span class="sxs-lookup"><span data-stu-id="e418c-114">**Reminder notice:** If enabled, a reminder notice will be sent to your custodians based on the specified frequency and interval.</span></span> <span data-ttu-id="e418c-115">Die Erinnerungen werden weiterhin gesendet, bis der Benachrichtigungsverwahrer seine Benachrichtigung bestätigt hat oder bis die Anzahl der Erinnerungen ausgeschöpft ist.</span><span class="sxs-lookup"><span data-stu-id="e418c-115">The reminders will continue to be sent either until the custodian has acknowledged their notice or until the number of reminders have been exhausted.</span></span>

- <span data-ttu-id="e418c-116">**Eskalationsbenachrichtigung:** Wenn diese Option aktiviert ist, wird eine Eskalationsbenachrichtigung an Ihren Verwalter und seinen Vorgesetzten gesendet, nachdem die Erinnerungsbenachrichtigungen aufgebraucht sind.</span><span class="sxs-lookup"><span data-stu-id="e418c-116">**Escalation notice:** If enabled, an escalation notice will be sent to your custodian and their manager after the reminder notices have been exhausted.</span></span> <span data-ttu-id="e418c-117">Das System sendet automatisch Eskalationsbenachrichtigungen, bis die angegebene Anzahl von Eskalationen abgeschlossen ist oder der Custodian seine Haltebenachrichtigung bestätigt.</span><span class="sxs-lookup"><span data-stu-id="e418c-117">The system will automatically send escalation notices until the specified number of escalations have been completed or until the custodian acknowledges their hold notification.</span></span>

- <span data-ttu-id="e418c-118">**Erneuter Veröffentlichungsbemerkung:** Wenn im Verlauf einer Untersuchung der Inhalt des Haltehinweises aktualisiert wird, wird der aktualisierte Hinweis automatisch an den Custodian gesendet.</span><span class="sxs-lookup"><span data-stu-id="e418c-118">**Reissue notice:** During the course of an investigation, if the contents of the hold notice are updated, then the updated notice will automatically be sent to the custodian.</span></span>

- <span data-ttu-id="e418c-119">**Veröffentlichungshinweise:** Wenn ein Verwahrer aus dem Fall freigelassen wird, wird der Veröffentlichungsbenachrichtigung gesendet.</span><span class="sxs-lookup"><span data-stu-id="e418c-119">**Release notice:** When a custodian is released from the case, they'll be sent the release notice.</span></span> 

## <a name="compliance-portal"></a><span data-ttu-id="e418c-120">Complianceportal</span><span class="sxs-lookup"><span data-stu-id="e418c-120">Compliance Portal</span></span>

<span data-ttu-id="e418c-121">Zusätzlich zu den E-Mail-Benachrichtigungen hat jeder Benachrichtigungsverwahrer Zugriff auf ein eindeutiges Complianceportal.</span><span class="sxs-lookup"><span data-stu-id="e418c-121">In addition to the email notifications, each custodian will have access to a unique Compliance Portal.</span></span> <span data-ttu-id="e418c-122">Über das Portal kann jeder Custodian seine aktiven Haltebenachrichtigungen anzeigen, darauf zugreifen und bestätigen.</span><span class="sxs-lookup"><span data-stu-id="e418c-122">Through the portal, each custodian can view, access, and acknowledge their active hold notifications.</span></span>

![Complianceportal für einen Custodian](../media/CustodianPortal.jpg)
