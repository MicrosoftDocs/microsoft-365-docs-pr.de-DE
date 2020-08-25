---
title: Erstellen und Nachverfolgen von ServiceNow-Tickets im Microsoft 365 Security Center
description: Informationen zum Erstellen und Nachverfolgen von Tickets in ServiceNow im Microsoft 365 Security Center.
keywords: Sicherheit, Microsoft 365, M365, sicheres Ergebnis, Sicherheitscenter, ServiceNow, Tickets, Aufgaben
ms.prod: w10
ms.mktglfcycl: deploy
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.author: ellevin
author: levinec
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: article
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
ms.openlocfilehash: bd5bf8533d38337c063acdf0dda073e4961e416a
ms.sourcegitcommit: 787b198765565d54ee73972f664bdbd5023d666b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/24/2020
ms.locfileid: "46867245"
---
# <a name="create-and-track-servicenow-tickets-in-the-microsoft-365-security-center"></a><span data-ttu-id="1cf8e-104">Erstellen und Nachverfolgen von ServiceNow-Tickets im Microsoft 365 Security Center</span><span class="sxs-lookup"><span data-stu-id="1cf8e-104">Create and track ServiceNow tickets in the Microsoft 365 security center</span></span>

<span data-ttu-id="1cf8e-105">Das [Microsoft 365-Sicherheitscenter](overview-security-center.md) wurde erweitert, sodass Tickets in ServiceNow nativ erstellt und nachverfolgt werden können.</span><span class="sxs-lookup"><span data-stu-id="1cf8e-105">The [Microsoft 365 security center](overview-security-center.md) has been enhanced with the ability to natively create and track tickets in ServiceNow.</span></span> [<span data-ttu-id="1cf8e-106">Erfahren Sie mehr über ServiceNow</span><span class="sxs-lookup"><span data-stu-id="1cf8e-106">Learn more about ServiceNow</span></span>](https://www.servicenow.com/)

<span data-ttu-id="1cf8e-107">Im Sicherheitscenter können Sicherheitsadministratoren eine [Microsoft Secure Score](microsoft-secure-score.md) -Verbesserungs Aktion direkt an ServiceNow senden und ein Ticket erstellen.</span><span class="sxs-lookup"><span data-stu-id="1cf8e-107">In the security center, security administrators can send a [Microsoft Secure Score](microsoft-secure-score.md) improvement action directly to ServiceNow and create a ticket.</span></span> <span data-ttu-id="1cf8e-108">Es können sowohl Incident Management als auch Change Management-Tickets erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="1cf8e-108">Both incident management and change management tickets can be created.</span></span> <span data-ttu-id="1cf8e-109">Verfolgen Sie Tickets auf der Startseite des Sicherheitscenters und ServiceNow.</span><span class="sxs-lookup"><span data-stu-id="1cf8e-109">Track tickets in the security center home page and ServiceNow.</span></span>

- [<span data-ttu-id="1cf8e-110">**Informationen zu Voraussetzungen, Datenaustausch und Problembehandlung**</span><span class="sxs-lookup"><span data-stu-id="1cf8e-110">**Learn about prerequisites, data exchange, and troubleshooting**</span></span>](tickets.md)
- <span data-ttu-id="1cf8e-111">**Verwalten von ServiceNow-Tickets im Compliance Center** (demnächst verfügbar)</span><span class="sxs-lookup"><span data-stu-id="1cf8e-111">**Manage ServiceNow tickets in the compliance center** (coming soon)</span></span>

## <a name="connect-microsoft-365-security-center-to-servicenow"></a><span data-ttu-id="1cf8e-112">Verbinden von Microsoft 365 Security Center mit ServiceNow</span><span class="sxs-lookup"><span data-stu-id="1cf8e-112">Connect Microsoft 365 security center to ServiceNow</span></span>

<span data-ttu-id="1cf8e-113">Navigieren Sie zur Microsoft 365-Sicherheitscenter-Startseite, um die ServiceNow-Verbindungskarte anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="1cf8e-113">Navigate to the Microsoft 365 security center home page to see the ServiceNow connection card.</span></span>

![Verwenden Sie ServiceNow](../../media/do-you-use-servicenow-250.png)

<span data-ttu-id="1cf8e-115">Wählen Sie "mit ServiceNow verbinden" aus, um die ServiceNow-Setup Seite zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="1cf8e-115">Select "Connect to ServiceNow" to go to the ServiceNow setup page.</span></span> <span data-ttu-id="1cf8e-116">Befolgen Sie die Anweisungen, um die Microsoft 365-Connector-APP zu autorisieren.</span><span class="sxs-lookup"><span data-stu-id="1cf8e-116">Follow the instructions to authorize the Microsoft 365 Connector app.</span></span>

> [!NOTE]
> <span data-ttu-id="1cf8e-117">Bevor Sie die Verbindung zwischen dem Microsoft 365 Security Center und ServiceNow autorisieren, müssen Sie sicherstellen, dass Sie den Benutzernamen und das Kennwort für die Integration verwenden, die Sie in den Installationsschritten erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="1cf8e-117">Before you authorize the connection between Microsoft 365 security center and ServiceNow, make sure you use the integration user login and password you created in the installation steps.</span></span> <span data-ttu-id="1cf8e-118">Verwenden Sie Ihre persönlichen Anmeldeinformationen nicht.</span><span class="sxs-lookup"><span data-stu-id="1cf8e-118">Do not use your personal credentials.</span></span>

<span data-ttu-id="1cf8e-119">Nachdem Sie die Anweisungen befolgt und die Verbindung autorisiert haben, zeigen Sie den Verbindungsstatus auf der Seite Microsoft 365 Security Center Connection und in der ServiceNow Microsoft 365 Ticketing Connector App Experience an.</span><span class="sxs-lookup"><span data-stu-id="1cf8e-119">After you've followed the directions and authorized the connection, view the connection status in the Microsoft 365 security center connection page and in the ServiceNow Microsoft 365 Ticketing Connector App experience.</span></span> <span data-ttu-id="1cf8e-120">Jetzt können Sie mit dem Erstellen von Aufgaben beginnen.</span><span class="sxs-lookup"><span data-stu-id="1cf8e-120">Now you're all set to start creating tasks!</span></span>

### <a name="troubleshooting"></a><span data-ttu-id="1cf8e-121">Problembehandlung</span><span class="sxs-lookup"><span data-stu-id="1cf8e-121">Troubleshooting</span></span>

<span data-ttu-id="1cf8e-122">Erfahren Sie häufig auftretende Fehler im Verbindungsprozess und wie Sie sie entschärfen können, im [Abschnitt Problembehandlung](tickets.md#troubleshooting).</span><span class="sxs-lookup"><span data-stu-id="1cf8e-122">Learn common errors you may come across in the connection process, and how to mitigate them, in the [troubleshooting section](tickets.md#troubleshooting).</span></span>

## <a name="create-a-task-and-share-it-to-servicenow"></a><span data-ttu-id="1cf8e-123">Erstellen einer Aufgabe und freigeben für ServiceNow</span><span class="sxs-lookup"><span data-stu-id="1cf8e-123">Create a task and share it to ServiceNow</span></span>

<span data-ttu-id="1cf8e-124">Nachdem die Integration eingerichtet wurde, erstellen Sie ServiceNow-Aufgaben basierend auf bestimmten [Microsoft Secure Score](microsoft-secure-score.md) -Verbesserungs Aktionen.</span><span class="sxs-lookup"><span data-stu-id="1cf8e-124">Once the integration is set up, create ServiceNow tasks based on specific [Microsoft Secure Score](microsoft-secure-score.md) improvement actions.</span></span> <span data-ttu-id="1cf8e-125">Wechseln Sie zur Aktion sichere Ergebnisverbesserung im Microsoft 365 Security Center, und wählen Sie dann **Freigeben**aus.</span><span class="sxs-lookup"><span data-stu-id="1cf8e-125">Go to any Secure Score improvement action in the Microsoft 365 security center, and select **Share**.</span></span> <span data-ttu-id="1cf8e-126">Eine der Dropdownoptionen ist ServiceNow.</span><span class="sxs-lookup"><span data-stu-id="1cf8e-126">One of the dropdown options is ServiceNow.</span></span>

<span data-ttu-id="1cf8e-127">Es wird eine Aufgabe generiert, in der Sie die Priorität festlegen und den Namen, die Beschreibung oder das Fälligkeitsdatum bearbeiten können.</span><span class="sxs-lookup"><span data-stu-id="1cf8e-127">A task is generated where you can set the priority and edit the name, description, or due date.</span></span> <span data-ttu-id="1cf8e-128">Wenn alle erforderlichen Felder ausgefüllt sind, senden Sie die Aufgabe an ServiceNow.</span><span class="sxs-lookup"><span data-stu-id="1cf8e-128">Once all the required fields are filled in, send the task to ServiceNow.</span></span>

<span data-ttu-id="1cf8e-129">Die Aufgabe ist in ServiceNow als Microsoft 365 Sicherheits-und Konfigurations Änderungsanforderung sichtbar.</span><span class="sxs-lookup"><span data-stu-id="1cf8e-129">The task is visible in ServiceNow as a Microsoft 365 Security and Configuration Change Request.</span></span>

## <a name="track-tickets"></a><span data-ttu-id="1cf8e-130">Nachverfolgen von Tickets</span><span class="sxs-lookup"><span data-stu-id="1cf8e-130">Track tickets</span></span>

<span data-ttu-id="1cf8e-131">Nachdem ServiceNow Change Management-und Incident Management-Tickets erstellt wurden, werden diese auf Karten auf der Startseite von Microsoft 365 Security Center angezeigt.</span><span class="sxs-lookup"><span data-stu-id="1cf8e-131">Once ServiceNow change management and incident management tickets have been created, they're displayed on cards in the Microsoft 365 security center home page.</span></span> <span data-ttu-id="1cf8e-132">Auf diesen Karten können Sie ein Ticket erstellen, alle Tickets anzeigen oder die ServiceNow-Konfiguration verwalten.</span><span class="sxs-lookup"><span data-stu-id="1cf8e-132">From these cards, you can create a ticket, view all tickets, or manage the ServiceNow configuration.</span></span>

![ServiceNow Change Management-Tickets](../../media/change-management-375.png)  ![ServiceNow Incident Management Tickets](../../media/incident-management-375.png)

<span data-ttu-id="1cf8e-135">Um die ServiceNow-Integration in das Microsoft 365 Security Center erneut zu überwachen oder zu verwalten, wählen Sie auf beiden Karten die Option **Manage ServiceNow Configuration** aus.</span><span class="sxs-lookup"><span data-stu-id="1cf8e-135">To reprovision or manage your ServiceNow integration in the Microsoft 365 security center, select **Manage ServiceNow configuration** on either of the cards.</span></span> <span data-ttu-id="1cf8e-136">Entfernen Sie von dort die aktuelle ServiceNow-Verbindung, und passen Sie die Ticket Statusnamen an.</span><span class="sxs-lookup"><span data-stu-id="1cf8e-136">From there, remove the current ServiceNow connection and customize ticket state names.</span></span>

<span data-ttu-id="1cf8e-137">Wenn ServiceNow-Tickets im Microsoft 365 Security Center angezeigt werden, werden Ihre Aufgaben an einer Stelle gespeichert, an der Sie neben den anderen Sicherheits Dashboard-Elementen nachverfolgt und bearbeitet werden können.</span><span class="sxs-lookup"><span data-stu-id="1cf8e-137">With ServiceNow tickets visible in the Microsoft 365 security center, your tasks live in a place where they can be tracked and acted upon alongside your other security dashboard items.</span></span>

## <a name="resources"></a><span data-ttu-id="1cf8e-138">Ressourcen</span><span class="sxs-lookup"><span data-stu-id="1cf8e-138">Resources</span></span>

- [<span data-ttu-id="1cf8e-139">Informationen zu Voraussetzungen, Datenaustausch und Problembehandlung</span><span class="sxs-lookup"><span data-stu-id="1cf8e-139">Learn about prerequisites, data exchange, and troubleshooting</span></span>](tickets.md)
- [<span data-ttu-id="1cf8e-140">Microsoft-Sicherheitsbewertung</span><span class="sxs-lookup"><span data-stu-id="1cf8e-140">Microsoft Secure Score</span></span>](microsoft-secure-score.md)