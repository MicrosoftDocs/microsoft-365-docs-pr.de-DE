---
title: Erstellen und Nachverfolgen von Tickets über ServiceNow
description: Das Microsoft 365-Sicherheitscenter wird erweitert, sodass Tickets in ServiceNow nativ erstellt und nachverfolgt werden können. Auf diese Weise können Sicherheitsadministratoren eine sichere Bewertungs Empfehlung direkt an ServiceNow senden und ein Ticket erstellen.
keywords: Sicherheit, Microsoft 365, M365, sicheres Ergebnis, Sicherheitscenter, ServiceNow, Tickets, Aufgaben
ms.prod: w10
ms.mktglfcycl: deploy
ms.localizationpriority: medium
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
ms.openlocfilehash: b0b8cda81bb6cec3958e7b2a758da191d803a0ed
ms.sourcegitcommit: acf29701bfba3e4843e49a79fde012f3c7a7024a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/01/2019
ms.locfileid: "37350330"
---
# <a name="manage-tickets-through-servicenow"></a><span data-ttu-id="8b580-105">Verwalten von Tickets über ServiceNow</span><span class="sxs-lookup"><span data-stu-id="8b580-105">Manage tickets through ServiceNow</span></span>

<span data-ttu-id="8b580-106">Das Microsoft 365-Sicherheitscenter wird erweitert, sodass Tickets in ServiceNow nativ erstellt und nachverfolgt werden können.</span><span class="sxs-lookup"><span data-stu-id="8b580-106">Microsoft 365 security center is being enhanced with the ability to natively create and track tickets in ServiceNow.</span></span> <span data-ttu-id="8b580-107">Auf diese Weise können Sicherheitsadministratoren eine [Microsoft Secure Score](microsoft-secure-score.md) -Verbesserungs Aktion direkt an ServiceNow senden und ein Ticket erstellen.</span><span class="sxs-lookup"><span data-stu-id="8b580-107">This allows security administrators to send a [Microsoft Secure Score](microsoft-secure-score.md) improvement action directly to ServiceNow and create a ticket.</span></span> <span data-ttu-id="8b580-108">Es können sowohl Incident Management als auch Change Management-Tickets erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="8b580-108">Both incident management and change management tickets can be created.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="8b580-109">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="8b580-109">Prerequisites</span></span>

<span data-ttu-id="8b580-110">Sie haben Zugriff auf das Microsoft 365 Security Center und eine ServiceNow-Instanz mit:</span><span class="sxs-lookup"><span data-stu-id="8b580-110">Have access to the Microsoft 365 security center and a ServiceNow instance with:</span></span>  

* <span data-ttu-id="8b580-111">Version von Kingston oder höher</span><span class="sxs-lookup"><span data-stu-id="8b580-111">Kingston or higher version</span></span>
* <span data-ttu-id="8b580-112">Administrator-Hi-Anmeldeinformationen</span><span class="sxs-lookup"><span data-stu-id="8b580-112">Have admin HI credentials</span></span>
* <span data-ttu-id="8b580-113">Verfügen über Administratorrechte für die Zielanbieter Instanz</span><span class="sxs-lookup"><span data-stu-id="8b580-113">Have admin privileges on your target vendor instance</span></span>

<span data-ttu-id="8b580-114">ServiceNow empfiehlt Benutzern, die Einstellungen (Standardeinstellung) in ihrer ServiceNow-Instanz aus dem Feld zu halten.</span><span class="sxs-lookup"><span data-stu-id="8b580-114">ServiceNow recommends users keep out of the box settings (default) in your ServiceNow instance.</span></span>  <span data-ttu-id="8b580-115">Das Ausführen von Anpassungen kann zu Fehlern beim Abschließen der Installationsprüfliste und der Integration mit dem Microsoft 365 Security Center führen.</span><span class="sxs-lookup"><span data-stu-id="8b580-115">Having customizations could cause errors in completing the installation checklist and integration with the Microsoft 365 security center.</span></span>

## <a name="data-exchange"></a><span data-ttu-id="8b580-116">Datenaustausch</span><span class="sxs-lookup"><span data-stu-id="8b580-116">Data exchange</span></span>

<span data-ttu-id="8b580-117">Wenn Sie das Microsoft 365 Security Center mit ServiceNow verbinden, erhält Microsoft die folgenden zusätzlichen Daten:</span><span class="sxs-lookup"><span data-stu-id="8b580-117">When you connect the Microsoft 365 security center to ServiceNow, Microsoft will be receiving the following additional data:</span></span>

* <span data-ttu-id="8b580-118">Name der ServiceNow-Instanz</span><span class="sxs-lookup"><span data-stu-id="8b580-118">ServiceNow instance name</span></span>
* <span data-ttu-id="8b580-119">ServiceNow-Client-ID</span><span class="sxs-lookup"><span data-stu-id="8b580-119">ServiceNow client ID</span></span>
* <span data-ttu-id="8b580-120">Geheimer ServiceNow-Client</span><span class="sxs-lookup"><span data-stu-id="8b580-120">ServiceNow client secret</span></span>
* <span data-ttu-id="8b580-121">ServiceNow-Zugriffs #a0 Aktualisierungstoken</span><span class="sxs-lookup"><span data-stu-id="8b580-121">ServiceNow access & refresh tokens</span></span>

<span data-ttu-id="8b580-122">Wenn Sie ein ServiceNow-Ticket aus dem Microsoft 365 Security Center erstellen, werden die folgenden Daten an ServiceNow gesendet:</span><span class="sxs-lookup"><span data-stu-id="8b580-122">When you create a ServiceNow ticket from the Microsoft 365 security center the following data is sent to ServiceNow:</span></span>

* <span data-ttu-id="8b580-123">Benutzer-ID, die die Ticketerstellung initiiert</span><span class="sxs-lookup"><span data-stu-id="8b580-123">User ID that initiates the ticket creation</span></span>
* <span data-ttu-id="8b580-124">Aufgabenname</span><span class="sxs-lookup"><span data-stu-id="8b580-124">Task name</span></span>
* <span data-ttu-id="8b580-125">Aufgabenbeschreibung</span><span class="sxs-lookup"><span data-stu-id="8b580-125">Task description</span></span>
* <span data-ttu-id="8b580-126">Priorität</span><span class="sxs-lookup"><span data-stu-id="8b580-126">Priority</span></span>
* <span data-ttu-id="8b580-127">Fälligkeitsdatum</span><span class="sxs-lookup"><span data-stu-id="8b580-127">Due date</span></span>
* <span data-ttu-id="8b580-128">Empfehlungsquelle (Benutzer Empfehlung oder Microsoft-Empfehlung)</span><span class="sxs-lookup"><span data-stu-id="8b580-128">Recommendation source (User recommendation or Microsoft recommendation)</span></span>
* <span data-ttu-id="8b580-129">Empfehlungskategorie (Geräte, Daten, apps, Identität, Infrastruktur)</span><span class="sxs-lookup"><span data-stu-id="8b580-129">Recommendation category (Devices, Data, Apps, Identity, Infrastructure)</span></span>

## <a name="connect-microsoft-365-security-center-to-servicenow"></a><span data-ttu-id="8b580-130">Verbinden von Microsoft 365 Security Center mit ServiceNow</span><span class="sxs-lookup"><span data-stu-id="8b580-130">Connect Microsoft 365 security center to ServiceNow</span></span>

<span data-ttu-id="8b580-131">Navigieren Sie zur Microsoft 365 Security Center-Startseite, auf der Sie eine Karte sehen, in der Sie gefragt werden, ob Sie ServiceNow verwenden.</span><span class="sxs-lookup"><span data-stu-id="8b580-131">Navigate to the Microsoft 365 security center home page, where you will see a card asking if you use ServiceNow.</span></span>

![Verwenden Sie ServiceNow](../images/do-you-use-servicenow-250.png)

<span data-ttu-id="8b580-133">Von dort aus werden Sie an die ServiceNow-Setup Seite gesendet, auf der Sie die Anweisungen zum Autorisieren der Microsoft 365 Connector-App befolgen.</span><span class="sxs-lookup"><span data-stu-id="8b580-133">From there you will be sent to the ServiceNow set up page where you'll follow the instructions to authorize the Microsoft 365 Connector app.</span></span>

<span data-ttu-id="8b580-134">Stellen Sie beim Autorisieren der Verbindung zwischen dem Microsoft 365 Security Center und ServiceNow sicher, dass Sie den Benutzernamen und das Kennwort für die Integration verwenden, die Sie in den Installationsschritten und nicht in Ihren persönlichen Anmeldeinformationen erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="8b580-134">When authorizing the connection between Microsoft 365 security center and ServiceNow, make sure you use the integration user login and password you created in the installation steps and not your personal credentials.</span></span>

<span data-ttu-id="8b580-135">Nachdem Sie den Anweisungen folgen und die Verbindung autorisiert haben, können Sie den Verbindungsstatus sowohl auf der Microsoft 365 Security Center-Verbindungsseite als auch in der APP-Erfahrung von ServiceNow Microsoft 365 Ticketing Connector anzeigen.</span><span class="sxs-lookup"><span data-stu-id="8b580-135">After following the directions and authorizing the connection, you can view the connection status on both the Microsoft 365 security center connection page and in the ServiceNow Microsoft 365 Ticketing Connector App experience.</span></span> <span data-ttu-id="8b580-136">Jetzt können Sie mit dem Erstellen von Aufgaben beginnen.</span><span class="sxs-lookup"><span data-stu-id="8b580-136">Now you are all set to start creating tasks!</span></span>

## <a name="create-a-task-and-share-it-to-servicenow"></a><span data-ttu-id="8b580-137">Erstellen einer Aufgabe und freigeben für ServiceNow</span><span class="sxs-lookup"><span data-stu-id="8b580-137">Create a task and share it to ServiceNow</span></span>

<span data-ttu-id="8b580-138">Nachdem die Integration eingerichtet wurde, können Sie ServiceNow-Aufgaben basierend auf bestimmten Microsoft Secure Score-Verbesserungs Aktionen erstellen.</span><span class="sxs-lookup"><span data-stu-id="8b580-138">Once the integration is set up, you can create ServiceNow tasks based on specific Microsoft Secure Score improvement actions.</span></span> <span data-ttu-id="8b580-139">Wechseln Sie zu einer Verbesserungs Aktion in Secure Score im Microsoft 365 Security Center-Portal, und wählen Sie das Symbol "freigeben" aus.</span><span class="sxs-lookup"><span data-stu-id="8b580-139">Go to any improvement action in Secure Score in the Microsoft 365 security center portal, and select the “share” icon.</span></span> <span data-ttu-id="8b580-140">Eine der Dropdownoptionen ist ServiceNow.</span><span class="sxs-lookup"><span data-stu-id="8b580-140">One of the dropdown options is ServiceNow.</span></span>

![ServiceNow-Freigabe in sicherer Punktzahl](../images/servicenow-share.png)

<span data-ttu-id="8b580-142">Anschließend wird eine Aufgabe generiert, in der Sie die Priorität festlegen und den Namen, die Beschreibung oder das Fälligkeitsdatum bearbeiten können.</span><span class="sxs-lookup"><span data-stu-id="8b580-142">A task will then be generated where you can set the priority and edit the name, description, or due date.</span></span> <span data-ttu-id="8b580-143">Sobald alle erforderlichen Felder ausgefüllt sind, können Sie die Aufgabe an ServiceNow senden.</span><span class="sxs-lookup"><span data-stu-id="8b580-143">Once all the required fields are filled in, you can send the task to ServiceNow.</span></span>

<span data-ttu-id="8b580-144">Die Aufgabe wird in ServiceNow als Microsoft 365 Sicherheits-und Konfigurations Änderungsanforderung angezeigt.</span><span class="sxs-lookup"><span data-stu-id="8b580-144">The task will be visible in ServiceNow as a Microsoft 365 Security and Configuration Change Request.</span></span>

## <a name="track-tickets"></a><span data-ttu-id="8b580-145">Nachverfolgen von Tickets</span><span class="sxs-lookup"><span data-stu-id="8b580-145">Track tickets</span></span>

<span data-ttu-id="8b580-146">Nachdem ServiceNow Change Management und Incident Management Tickets erstellt wurden, werden diese auf Karten auf der Startseite von Microsoft 365 Security Center angezeigt.</span><span class="sxs-lookup"><span data-stu-id="8b580-146">Once ServiceNow change management and incident management tickets have been created, they will be displayed on cards in the Microsoft 365 security center home page.</span></span> <span data-ttu-id="8b580-147">Auf diesen Karten können Sie ein Ticket erstellen, alle Tickets anzeigen oder die ServiceNow-Konfiguration verwalten.</span><span class="sxs-lookup"><span data-stu-id="8b580-147">From these cards, you can create a ticket, view all tickets, or manage the ServiceNow configuration.</span></span>

![ServiceNow Change Management-Tickets](../images/change-management-375.png)  ![ServiceNow Incident Management Tickets](../images/incident-management-375.png)

<span data-ttu-id="8b580-150">Um die ServiceNow-Integration in das Microsoft 365 Security Center erneut zu überwachen oder zu verwalten, wählen Sie auf beiden Karten die Option **Manage ServiceNow Configuration** aus.</span><span class="sxs-lookup"><span data-stu-id="8b580-150">To re-provision or manage your ServiceNow integration in the Microsoft 365 security center, select **Manage ServiceNow configuration** on either of the cards.</span></span> <span data-ttu-id="8b580-151">Von dort aus können Sie die aktuelle ServiceNow-Verbindung entfernen und Ticket Statusnamen anpassen.</span><span class="sxs-lookup"><span data-stu-id="8b580-151">From there you can  remove the current ServiceNow connection and customize ticket state names.</span></span>

<span data-ttu-id="8b580-152">Wenn ServiceNow-Tickets im Microsoft 365 Security Center angezeigt werden, werden Ihre Aufgaben an einer Stelle gespeichert, an der Sie neben den anderen Sicherheits Dashboard-Elementen nachverfolgt und bearbeitet werden können.</span><span class="sxs-lookup"><span data-stu-id="8b580-152">With ServiceNow tickets visible in the Microsoft 365 security center, your tasks will live in a place where they can be tracked and acted upon alongside your other security dashboard items.</span></span>

## <a name="frequently-asked-questions"></a><span data-ttu-id="8b580-153">Häufig gestellte Fragen</span><span class="sxs-lookup"><span data-stu-id="8b580-153">Frequently asked questions</span></span>

### <a name="i-am-receiving-an-error-in-the-first-step-of-the-installation-checklist-oauth-creation"></a><span data-ttu-id="8b580-154">Ich erhalte einen Fehler im ersten Schritt der Installationsprüfliste (OAuth-Erstellung)</span><span class="sxs-lookup"><span data-stu-id="8b580-154">I am receiving an error in the first step of the installation checklist (OAuth creation)</span></span>

<span data-ttu-id="8b580-155">**Fehlermeldung**: der Lesevorgang für "oauth_entity" aus dem Bereich "x_mioms_m365ticket" wurde aufgrund der bereichsübergreifenden Zugriffsrichtlinie der Tabelle verweigert.</span><span class="sxs-lookup"><span data-stu-id="8b580-155">**Error Message**: Read operation against 'oauth_entity' from scope 'x_mioms_m365ticket' has been refused due to the table's cross-scope access policy</span></span>

<span data-ttu-id="8b580-156">Unsere App geht davon aus, dass Administratoren in der ServiceNow-Instanz OAuth-Entitäten erstellen und lesen können.</span><span class="sxs-lookup"><span data-stu-id="8b580-156">Our app assumes any admin on the ServiceNow instance can create and read OAuth entities.</span></span> <span data-ttu-id="8b580-157">Dieser Fehler kann aufgrund einer Anpassung Ihrer Instanz von ServiceNow verursacht werden, wodurch die Benutzer eingeschränkt werden, die OAuth-Entitäten erstellen/lesen können.</span><span class="sxs-lookup"><span data-stu-id="8b580-157">This error could be caused due to a customization on your instance of ServiceNow, which restricts who can create/read OAuth entities.</span></span> <span data-ttu-id="8b580-158">ServiceNow empfiehlt Benutzern, die Funktionalität außerhalb der Box zu halten (Standardeinstellung).</span><span class="sxs-lookup"><span data-stu-id="8b580-158">ServiceNow recommends users keep out of the box functionality (default).</span></span>

<span data-ttu-id="8b580-159">Legen Sie die Tabellen Konfigurationen "Anwendungs Registrierungen" auf "Standard" fest:</span><span class="sxs-lookup"><span data-stu-id="8b580-159">Set the “application registries” table configurations to default:</span></span>

* <span data-ttu-id="8b580-160">Label = Anwendungs Registrierungen</span><span class="sxs-lookup"><span data-stu-id="8b580-160">Label = Application Registeries</span></span>
* <span data-ttu-id="8b580-161">Name = oauth_entity</span><span class="sxs-lookup"><span data-stu-id="8b580-161">Name = oauth_entity</span></span>
* <span data-ttu-id="8b580-162">Zugänglich von = alle Anwendungsbereiche</span><span class="sxs-lookup"><span data-stu-id="8b580-162">Accessible from = All application scopes</span></span>
* <span data-ttu-id="8b580-163">Can read = Kontrollkästchen aktiviert</span><span class="sxs-lookup"><span data-stu-id="8b580-163">Can read = check box selected</span></span>

<span data-ttu-id="8b580-164">**ServiceNow empfiehlt Benutzern, die Funktionalität außerhalb der Box zu halten (Standardeinstellung).**</span><span class="sxs-lookup"><span data-stu-id="8b580-164">**ServiceNow recommends users keep out of the box functionality (default).**</span></span>

### <a name="how-do-i-validate-the-oauth-entity-created-for-microsoft-365-security--compliance-connector"></a><span data-ttu-id="8b580-165">Wie kann ich die OAuth-Entität überprüfen, die für Microsoft 365 Security #a0 Compliance Connector erstellt wurde?</span><span class="sxs-lookup"><span data-stu-id="8b580-165">How do I validate the OAuth entity created for Microsoft 365 Security & Compliance connector?</span></span>

<span data-ttu-id="8b580-166">Wechseln Sie zur Tabelle Anwendungs Registrierungstabellen (Menü #a0 System OAuth #a1 Anwendungsregistrierung) in ServiceNow, und suchen Sie nach der von Ihnen erstellten OAuth-Entität (Name, den Sie Ihr zugewiesen haben).</span><span class="sxs-lookup"><span data-stu-id="8b580-166">Go to application registries table (Menu > System OAuth > Application Registry) in ServiceNow and find the OAuth entity created by you (name that you assigned it).</span></span>

### <a name="how-do-i-validate-the-integration-user-created-in-step-two-of-installation-checklist-for-microsoft-365-security--compliance-connector"></a><span data-ttu-id="8b580-167">Wie kann ich den Integrationsbenutzer überprüfen, der in Schritt 2 der Installationsprüfliste für Microsoft 365 Security #a0 Compliance Connector erstellt wurde?</span><span class="sxs-lookup"><span data-stu-id="8b580-167">How do I validate the Integration User created in step two of installation checklist for Microsoft 365 Security & Compliance connector?</span></span>

<span data-ttu-id="8b580-168">Wechseln Sie zu Benutzertabelle (Menü #a0 Benutzerverwaltung #a1 Benutzer) in ServiceNow, und suchen Sie nach dem von Ihnen erstellten Integrationsbenutzer (Name, den Sie ihm zugewiesen haben).</span><span class="sxs-lookup"><span data-stu-id="8b580-168">Go to Users Table (Menu > User Administration > Users) in ServiceNow and find the Integration user created by you (name that you assigned it).</span></span>

<span data-ttu-id="8b580-169">Stellen Sie beim Autorisieren der Verbindung zwischen dem Microsoft 365 Security Center und ServiceNow sicher, dass Sie den Benutzernamen und das Kennwort für die Integration verwenden, die Sie in den Installationsschritten und nicht in Ihren persönlichen Anmeldeinformationen erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="8b580-169">When authorizing the connection between Microsoft 365 security center and ServiceNow, make sure you use the integration user login and password you created in the installation steps and not your personal credentials.</span></span>

### <a name="i-have-completed-the-installation-and-set-up-steps-but-i-am-unable-to-see-the-servicenow-cards-on-the-home-page-and-cannot-see-the-share-icon-in-microsoft-secure-score"></a><span data-ttu-id="8b580-170">Ich habe die Installation abgeschlossen und Schritte eingerichtet, aber ich kann die ServiceNow-Karten nicht auf der Startseite anzeigen und das Symbol "freigeben" in Microsoft Secure Score nicht sehen.</span><span class="sxs-lookup"><span data-stu-id="8b580-170">I have completed the installation and set up steps, but I am unable to see the ServiceNow cards on the home page and cannot see the Share icon in Microsoft Secure Score</span></span>

<span data-ttu-id="8b580-171">Überprüfen Sie den Status der Seite "Übersicht", indem https://security.microsoft.com/ticketProvisioningSie zu wechseln.</span><span class="sxs-lookup"><span data-stu-id="8b580-171">Check the status of the provisioning page by going to https://security.microsoft.com/ticketProvisioning.</span></span> <span data-ttu-id="8b580-172">Wählen Sie **Speichern** und zur Startseite zurückkehren aus.</span><span class="sxs-lookup"><span data-stu-id="8b580-172">Select **Save** and return to the home page.</span></span> <span data-ttu-id="8b580-173">Die Karten sollten angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="8b580-173">The cards should appear.</span></span>
