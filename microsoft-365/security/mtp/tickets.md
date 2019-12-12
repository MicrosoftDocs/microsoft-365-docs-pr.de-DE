---
title: Erstellen und Nachverfolgen von Tickets über ServiceNow
description: Das Microsoft 365-Sicherheitscenter wird erweitert, sodass Tickets in ServiceNow nativ erstellt und nachverfolgt werden können. Sicherheitsadministratoren können eine sichere Bewertungs Empfehlung direkt an ServiceNow senden und ein Ticket erstellen.
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
ms.openlocfilehash: e67ff2b28a6dec741b2ad7af5179dca226fb86ad
ms.sourcegitcommit: b65c80051e53d9be223f4769f4d42a39f5a07735
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2019
ms.locfileid: "39962572"
---
# <a name="manage-tickets-through-servicenow"></a><span data-ttu-id="d4c9c-105">Verwalten von Tickets über ServiceNow</span><span class="sxs-lookup"><span data-stu-id="d4c9c-105">Manage tickets through ServiceNow</span></span>

<span data-ttu-id="d4c9c-106">Das Microsoft 365-Sicherheitscenter wird erweitert, sodass Tickets in ServiceNow nativ erstellt und nachverfolgt werden können.</span><span class="sxs-lookup"><span data-stu-id="d4c9c-106">Microsoft 365 security center is being enhanced with the ability to natively create and track tickets in ServiceNow.</span></span> <span data-ttu-id="d4c9c-107">Sicherheitsadministratoren können eine [Microsoft Secure Score](microsoft-secure-score.md) -Verbesserungs Aktion direkt an ServiceNow senden und ein Ticket erstellen.</span><span class="sxs-lookup"><span data-stu-id="d4c9c-107">Security administrators can send a [Microsoft Secure Score](microsoft-secure-score.md) improvement action directly to ServiceNow and create a ticket.</span></span> <span data-ttu-id="d4c9c-108">Es können sowohl Incident Management als auch Change Management-Tickets erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="d4c9c-108">Both incident management and change management tickets can be created.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="d4c9c-109">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="d4c9c-109">Prerequisites</span></span>

<span data-ttu-id="d4c9c-110">Sie haben Zugriff auf das Microsoft 365 Security Center und eine ServiceNow-Instanz mit:</span><span class="sxs-lookup"><span data-stu-id="d4c9c-110">Have access to the Microsoft 365 security center and a ServiceNow instance with:</span></span>  

* <span data-ttu-id="d4c9c-111">Version von Kingston oder höher</span><span class="sxs-lookup"><span data-stu-id="d4c9c-111">Kingston or higher version</span></span>
* <span data-ttu-id="d4c9c-112">Administrator-Hi-Anmeldeinformationen</span><span class="sxs-lookup"><span data-stu-id="d4c9c-112">Have admin HI credentials</span></span>
* <span data-ttu-id="d4c9c-113">Verfügen über Administratorrechte für die Zielanbieter Instanz</span><span class="sxs-lookup"><span data-stu-id="d4c9c-113">Have admin privileges on your target vendor instance</span></span>

<span data-ttu-id="d4c9c-114">ServiceNow empfiehlt Benutzern, die Standardeinstellungen in ihrer ServiceNow-Instanz beizubehalten.</span><span class="sxs-lookup"><span data-stu-id="d4c9c-114">ServiceNow recommends that users keep default settings in your ServiceNow instance.</span></span> <span data-ttu-id="d4c9c-115">Anpassungen können beim Abschließen der Installationsprüfliste und der Integration mit dem Microsoft 365 Security Center zu Fehlern führen.</span><span class="sxs-lookup"><span data-stu-id="d4c9c-115">Having customizations could cause errors when completing the installation checklist and integration with the Microsoft 365 security center.</span></span>

## <a name="data-exchange"></a><span data-ttu-id="d4c9c-116">Datenaustausch</span><span class="sxs-lookup"><span data-stu-id="d4c9c-116">Data exchange</span></span>

<span data-ttu-id="d4c9c-117">Wenn Sie das Microsoft 365 Security Center mit ServiceNow verbinden, erhält Microsoft die folgenden zusätzlichen Daten:</span><span class="sxs-lookup"><span data-stu-id="d4c9c-117">When you connect the Microsoft 365 security center to ServiceNow, Microsoft receives the following additional data:</span></span>

* <span data-ttu-id="d4c9c-118">Name der ServiceNow-Instanz</span><span class="sxs-lookup"><span data-stu-id="d4c9c-118">ServiceNow instance name</span></span>
* <span data-ttu-id="d4c9c-119">ServiceNow-Client-ID</span><span class="sxs-lookup"><span data-stu-id="d4c9c-119">ServiceNow client ID</span></span>
* <span data-ttu-id="d4c9c-120">Geheimer ServiceNow-Client</span><span class="sxs-lookup"><span data-stu-id="d4c9c-120">ServiceNow client secret</span></span>
* <span data-ttu-id="d4c9c-121">ServiceNow-Zugriffs #a0 Aktualisierungstoken</span><span class="sxs-lookup"><span data-stu-id="d4c9c-121">ServiceNow access & refresh tokens</span></span>

<span data-ttu-id="d4c9c-122">Wenn Sie ein ServiceNow-Ticket aus dem Microsoft 365 Security Center erstellen, werden die folgenden Daten an ServiceNow gesendet:</span><span class="sxs-lookup"><span data-stu-id="d4c9c-122">When you create a ServiceNow ticket from the Microsoft 365 security center, the following data is sent to ServiceNow:</span></span>

* <span data-ttu-id="d4c9c-123">Benutzer-ID, die die Ticketerstellung initiiert</span><span class="sxs-lookup"><span data-stu-id="d4c9c-123">User ID that initiates the ticket creation</span></span>
* <span data-ttu-id="d4c9c-124">Aufgabenname</span><span class="sxs-lookup"><span data-stu-id="d4c9c-124">Task name</span></span>
* <span data-ttu-id="d4c9c-125">Aufgabenbeschreibung</span><span class="sxs-lookup"><span data-stu-id="d4c9c-125">Task description</span></span>
* <span data-ttu-id="d4c9c-126">Priorität</span><span class="sxs-lookup"><span data-stu-id="d4c9c-126">Priority</span></span>
* <span data-ttu-id="d4c9c-127">Fälligkeitsdatum</span><span class="sxs-lookup"><span data-stu-id="d4c9c-127">Due date</span></span>
* <span data-ttu-id="d4c9c-128">Empfehlungsquelle (Benutzer Empfehlung oder Microsoft-Empfehlung)</span><span class="sxs-lookup"><span data-stu-id="d4c9c-128">Recommendation source (User recommendation or Microsoft recommendation)</span></span>
* <span data-ttu-id="d4c9c-129">Empfehlungskategorie (Geräte, Daten, apps, Identität, Infrastruktur)</span><span class="sxs-lookup"><span data-stu-id="d4c9c-129">Recommendation category (Devices, Data, Apps, Identity, Infrastructure)</span></span>

## <a name="connect-microsoft-365-security-center-to-servicenow"></a><span data-ttu-id="d4c9c-130">Verbinden von Microsoft 365 Security Center mit ServiceNow</span><span class="sxs-lookup"><span data-stu-id="d4c9c-130">Connect Microsoft 365 security center to ServiceNow</span></span>

<span data-ttu-id="d4c9c-131">Navigieren Sie zur Microsoft 365-Sicherheitscenter-Startseite, um die ServiceNow-Verbindungskarte anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="d4c9c-131">Navigate to the Microsoft 365 security center home page to see the ServiceNow connection card.</span></span>

![Verwenden Sie ServiceNow](../images/do-you-use-servicenow-250.png)

<span data-ttu-id="d4c9c-133">Wählen Sie "mit ServiceNow verbinden" aus, um die ServiceNow-Setup Seite zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="d4c9c-133">Select "Connect to ServiceNow" to go to the ServiceNow setup page.</span></span> <span data-ttu-id="d4c9c-134">Befolgen Sie die Anweisungen, um die Microsoft 365-Connector-APP zu autorisieren.</span><span class="sxs-lookup"><span data-stu-id="d4c9c-134">Follow the instructions to authorize the Microsoft 365 Connector app.</span></span>

> [!NOTE]
> <span data-ttu-id="d4c9c-135">Bevor Sie die Verbindung zwischen dem Microsoft 365 Security Center und ServiceNow autorisieren, müssen Sie sicherstellen, dass Sie den Benutzernamen und das Kennwort für die Integration verwenden, die Sie in den Installationsschritten erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="d4c9c-135">Before you authorize the connection between Microsoft 365 security center and ServiceNow, make sure you use the integration user login and password you created in the installation steps.</span></span> <span data-ttu-id="d4c9c-136">Verwenden Sie Ihre persönlichen Anmeldeinformationen nicht.</span><span class="sxs-lookup"><span data-stu-id="d4c9c-136">Do not use your personal credentials.</span></span>

<span data-ttu-id="d4c9c-137">Nachdem Sie die Anweisungen befolgt und die Verbindung autorisiert haben, zeigen Sie den Verbindungsstatus sowohl auf der Microsoft 365 Security Center-Verbindungsseite als auch in der APP-Erfahrung von Microsoft 365 Ticketing Connector für den ServiceNow an.</span><span class="sxs-lookup"><span data-stu-id="d4c9c-137">After you have followed the directions and authorizing the connection, view the connection status on both the Microsoft 365 security center connection page and in the ServiceNow Microsoft 365 Ticketing Connector App experience.</span></span> <span data-ttu-id="d4c9c-138">Jetzt können Sie mit dem Erstellen von Aufgaben beginnen.</span><span class="sxs-lookup"><span data-stu-id="d4c9c-138">Now you are all set to start creating tasks!</span></span>

## <a name="create-a-task-and-share-it-to-servicenow"></a><span data-ttu-id="d4c9c-139">Erstellen einer Aufgabe und freigeben für ServiceNow</span><span class="sxs-lookup"><span data-stu-id="d4c9c-139">Create a task and share it to ServiceNow</span></span>

<span data-ttu-id="d4c9c-140">Nachdem die Integration eingerichtet wurde, erstellen Sie ServiceNow-Aufgaben basierend auf bestimmten Microsoft Secure Score-Verbesserungs Aktionen.</span><span class="sxs-lookup"><span data-stu-id="d4c9c-140">Once the integration is set up, create ServiceNow tasks based on specific Microsoft Secure Score improvement actions.</span></span> <span data-ttu-id="d4c9c-141">Wechseln Sie zu einer Verbesserungs Aktion in Secure Score im Microsoft 365 Security Center-Portal, und wählen Sie das Symbol "freigeben" aus.</span><span class="sxs-lookup"><span data-stu-id="d4c9c-141">Go to any improvement action in Secure Score in the Microsoft 365 security center portal, and select the “share” icon.</span></span> <span data-ttu-id="d4c9c-142">Eine der Dropdownoptionen ist ServiceNow.</span><span class="sxs-lookup"><span data-stu-id="d4c9c-142">One of the dropdown options is ServiceNow.</span></span>

![ServiceNow-Freigabe in sicherer Punktzahl](../images/servicenow-share.png)

<span data-ttu-id="d4c9c-144">Es wird eine Aufgabe generiert, in der Sie die Priorität festlegen und den Namen, die Beschreibung oder das Fälligkeitsdatum bearbeiten können.</span><span class="sxs-lookup"><span data-stu-id="d4c9c-144">A task is generated where you can set the priority and edit the name, description, or due date.</span></span> <span data-ttu-id="d4c9c-145">Wenn alle erforderlichen Felder ausgefüllt sind, senden Sie die Aufgabe an ServiceNow.</span><span class="sxs-lookup"><span data-stu-id="d4c9c-145">Once all the required fields are filled in, send the task to ServiceNow.</span></span>

<span data-ttu-id="d4c9c-146">Die Aufgabe ist in ServiceNow als Microsoft 365 Sicherheits-und Konfigurations Änderungsanforderung sichtbar.</span><span class="sxs-lookup"><span data-stu-id="d4c9c-146">The task is visible in ServiceNow as a Microsoft 365 Security and Configuration Change Request.</span></span>

## <a name="track-tickets"></a><span data-ttu-id="d4c9c-147">Nachverfolgen von Tickets</span><span class="sxs-lookup"><span data-stu-id="d4c9c-147">Track tickets</span></span>

<span data-ttu-id="d4c9c-148">Nachdem ServiceNow Change Management-und Incident Management-Tickets erstellt wurden, werden diese auf Karten auf der Startseite von Microsoft 365 Security Center angezeigt.</span><span class="sxs-lookup"><span data-stu-id="d4c9c-148">Once ServiceNow change management and incident management tickets have been created, they are displayed on cards in the Microsoft 365 security center home page.</span></span> <span data-ttu-id="d4c9c-149">Auf diesen Karten können Sie ein Ticket erstellen, alle Tickets anzeigen oder die ServiceNow-Konfiguration verwalten.</span><span class="sxs-lookup"><span data-stu-id="d4c9c-149">From these cards, you can create a ticket, view all tickets, or manage the ServiceNow configuration.</span></span>

![ServiceNow Change Management-Tickets](../images/change-management-375.png)  ![ServiceNow Incident Management Tickets](../images/incident-management-375.png)

<span data-ttu-id="d4c9c-152">Um die ServiceNow-Integration in das Microsoft 365 Security Center erneut zu überwachen oder zu verwalten, wählen Sie auf beiden Karten die Option **Manage ServiceNow Configuration** aus.</span><span class="sxs-lookup"><span data-stu-id="d4c9c-152">To re-provision or manage your ServiceNow integration in the Microsoft 365 security center, select **Manage ServiceNow configuration** on either of the cards.</span></span> <span data-ttu-id="d4c9c-153">Entfernen Sie von dort die aktuelle ServiceNow-Verbindung, und passen Sie die Ticket Statusnamen an.</span><span class="sxs-lookup"><span data-stu-id="d4c9c-153">From there, remove the current ServiceNow connection and customize ticket state names.</span></span>

<span data-ttu-id="d4c9c-154">Wenn ServiceNow-Tickets im Microsoft 365 Security Center angezeigt werden, werden Ihre Aufgaben an einer Stelle gespeichert, an der Sie neben den anderen Sicherheits Dashboard-Elementen nachverfolgt und bearbeitet werden können.</span><span class="sxs-lookup"><span data-stu-id="d4c9c-154">With ServiceNow tickets visible in the Microsoft 365 security center, your tasks live in a place where they can be tracked and acted upon alongside your other security dashboard items.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="d4c9c-155">Problembehandlung</span><span class="sxs-lookup"><span data-stu-id="d4c9c-155">Troubleshooting</span></span>

### <a name="you-receive-an-error-in-the-first-step-of-the-installation-checklist-oauth-creation"></a><span data-ttu-id="d4c9c-156">Sie erhalten eine Fehlermeldung im ersten Schritt der Installationsprüfliste (OAuth-Erstellung)</span><span class="sxs-lookup"><span data-stu-id="d4c9c-156">You receive an error in the first step of the installation checklist (OAuth creation)</span></span>

<span data-ttu-id="d4c9c-157">**Fehlermeldung**: der Lesevorgang für "oauth_entity" aus dem Bereich "x_mioms_m365ticket" wurde aufgrund der bereichsübergreifenden Zugriffsrichtlinie der Tabelle verweigert.</span><span class="sxs-lookup"><span data-stu-id="d4c9c-157">**Error Message**: Read operation against 'oauth_entity' from scope 'x_mioms_m365ticket' has been refused due to the table's cross-scope access policy</span></span>

<span data-ttu-id="d4c9c-158">Die APP geht davon aus, dass ein Administrator in der ServiceNow-Instanz OAuth-Entitäten erstellen und lesen kann.</span><span class="sxs-lookup"><span data-stu-id="d4c9c-158">The app assumes any admin on the ServiceNow instance can create and read OAuth entities.</span></span> <span data-ttu-id="d4c9c-159">Dieser Fehler kann aufgrund einer Anpassung Ihrer Instanz von ServiceNow verursacht werden, wodurch die Benutzer eingeschränkt werden, die OAuth-Entitäten erstellen/lesen können.</span><span class="sxs-lookup"><span data-stu-id="d4c9c-159">This error could be caused due to a customization on your instance of ServiceNow, which restricts who can create/read OAuth entities.</span></span>

<span data-ttu-id="d4c9c-160">**ServiceNow empfiehlt Benutzern, die Standardfunktionalität beizubehalten.**</span><span class="sxs-lookup"><span data-stu-id="d4c9c-160">**ServiceNow recommends that users keep default functionality.**</span></span>

<span data-ttu-id="d4c9c-161">Legen Sie die Tabellen Konfigurationen "Anwendungs Registrierungen" auf "Standard" fest:</span><span class="sxs-lookup"><span data-stu-id="d4c9c-161">Set the “application registries” table configurations to default:</span></span>

* <span data-ttu-id="d4c9c-162">Label = Anwendungs Registrierungen</span><span class="sxs-lookup"><span data-stu-id="d4c9c-162">Label = Application Registeries</span></span>
* <span data-ttu-id="d4c9c-163">Name = oauth_entity</span><span class="sxs-lookup"><span data-stu-id="d4c9c-163">Name = oauth_entity</span></span>
* <span data-ttu-id="d4c9c-164">Zugänglich von = alle Anwendungsbereiche</span><span class="sxs-lookup"><span data-stu-id="d4c9c-164">Accessible from = All application scopes</span></span>
* <span data-ttu-id="d4c9c-165">Can read = Kontrollkästchen aktiviert</span><span class="sxs-lookup"><span data-stu-id="d4c9c-165">Can read = check box selected</span></span>

### <a name="how-to-validate-the-oauth-entity-created-for-microsoft-365-security--compliance-connector"></a><span data-ttu-id="d4c9c-166">Überprüfen der OAuth-Entität, die für Microsoft 365 Security #a0 Compliance Connector erstellt wurde</span><span class="sxs-lookup"><span data-stu-id="d4c9c-166">How to validate the OAuth entity created for Microsoft 365 Security & Compliance connector</span></span>

<span data-ttu-id="d4c9c-167">Wechseln Sie zur Tabelle Anwendungs Registrierungstabellen (Menü #a0 System OAuth #a1 Anwendungsregistrierung) in ServiceNow, und suchen Sie nach der von Ihnen erstellten OAuth-Entität (Name, den Sie Ihr zugewiesen haben).</span><span class="sxs-lookup"><span data-stu-id="d4c9c-167">Go to application registries table (Menu > System OAuth > Application Registry) in ServiceNow and find the OAuth entity created by you (name that you assigned it).</span></span>

### <a name="how-to-validate-the-integration-user-created-with-the-installation-checklist-for-microsoft-365-security--compliance-connector"></a><span data-ttu-id="d4c9c-168">Überprüfen des Integrations Benutzers, der mit der Installationsprüfliste für Microsoft 365 Security #a0 Compliance Connector erstellt wurde</span><span class="sxs-lookup"><span data-stu-id="d4c9c-168">How to validate the Integration User created with the installation checklist for Microsoft 365 Security & Compliance connector</span></span>

<span data-ttu-id="d4c9c-169">Wechseln Sie zu Benutzertabelle (Menü #a0 Benutzerverwaltung #a1 Benutzer) in ServiceNow, und suchen Sie nach dem von Ihnen erstellten Integrationsbenutzer (Name, den Sie ihm zugewiesen haben).</span><span class="sxs-lookup"><span data-stu-id="d4c9c-169">Go to Users Table (Menu > User Administration > Users) in ServiceNow and find the Integration user created by you (name that you assigned it).</span></span>

<span data-ttu-id="d4c9c-170">Bevor Sie die Verbindung zwischen dem Microsoft 365 Security Center und ServiceNow autorisieren, müssen Sie sicherstellen, dass Sie den Benutzernamen und das Kennwort für die Integration verwenden, die Sie in den Installationsschritten erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="d4c9c-170">Before you authorize the connection between Microsoft 365 security center and ServiceNow, make sure you use the integration user login and password you created in the installation steps.</span></span> <span data-ttu-id="d4c9c-171">Verwenden Sie Ihre persönlichen Anmeldeinformationen nicht.</span><span class="sxs-lookup"><span data-stu-id="d4c9c-171">Do not use your personal credentials.</span></span>

### <a name="installation-is-complete-but-dont-see-tickets-and-cant-share"></a><span data-ttu-id="d4c9c-172">Die Installation ist abgeschlossen, es werden jedoch keine Tickets angezeigt und können nicht freigegeben werden</span><span class="sxs-lookup"><span data-stu-id="d4c9c-172">Installation is complete but don't see tickets and can't share</span></span>

<span data-ttu-id="d4c9c-173">Wenn die Installations-und Setupschritte abgeschlossen wurden, die ServiceNow-Karten jedoch nicht auf der Startseite angezeigt werden und nicht von Microsoft Secure Score an ServiceNow freigegeben werden können, überprüfen Sie den Status der https://security.microsoft.com/ticketProvisioningSeite Bereitstellung unter.</span><span class="sxs-lookup"><span data-stu-id="d4c9c-173">If the installation and setup steps have been completed, but you don't see the ServiceNow cards on the home page and can't share to ServiceNow from Microsoft Secure Score, check the status of the provisioning page at https://security.microsoft.com/ticketProvisioning.</span></span> <span data-ttu-id="d4c9c-174">Wählen Sie **Speichern** und zur Startseite zurückkehren aus.</span><span class="sxs-lookup"><span data-stu-id="d4c9c-174">Select **Save** and return to the home page.</span></span> <span data-ttu-id="d4c9c-175">Die Karten sollten angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="d4c9c-175">The cards should appear.</span></span>

### <a name="your-company-has-single-sign-on-enabled-which-prevents-you-from-connecting-to-servicenow-through-the-microsoft-365-security-center"></a><span data-ttu-id="d4c9c-176">Ihr Unternehmen verfügt über ein einmaliges Anmelden, das verhindert, dass Sie sich über das Microsoft 365 Security Center mit ServiceNow verbinden.</span><span class="sxs-lookup"><span data-stu-id="d4c9c-176">Your company has single sign-on enabled which prevents you from connecting to ServiceNow through the Microsoft 365 security center</span></span>

<span data-ttu-id="d4c9c-177">Wenn Ihr Unternehmen einmaliges Anmelden aktiviert hat und Sie eine Fehlermeldung erhalten oder die Anmeldung nicht erfolgreich war, führen Sie eine der beiden Lösungen aus.</span><span class="sxs-lookup"><span data-stu-id="d4c9c-177">If your company has enabled single sign-on and you receive an error or login is unsuccessful, follow one of the two solutions.</span></span>

#### <a name="logging-into-servicenow-as-the-integration-user"></a><span data-ttu-id="d4c9c-178">Anmelden bei ServiceNow als Integrationsbenutzer</span><span class="sxs-lookup"><span data-stu-id="d4c9c-178">Logging into ServiceNow as the integration user</span></span>

1. <span data-ttu-id="d4c9c-179">Navigieren Sie zurück zur Autorisierungs Seite in ServiceNow.</span><span class="sxs-lookup"><span data-stu-id="d4c9c-179">Navigate back to the authorization page in ServiceNow.</span></span>
2. <span data-ttu-id="d4c9c-180">Klicken Sie in der rechten oberen Ecke auf den Link **Not You** .</span><span class="sxs-lookup"><span data-stu-id="d4c9c-180">Select the **Not You** link in the upper right-hand corner.</span></span>
3. <span data-ttu-id="d4c9c-181">Melden Sie sich bei ServiceNow als der Integrationsbenutzer an, den Sie zuvor in der Installationsprüfliste erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="d4c9c-181">Log in to ServiceNow as the integration user you created previously from the installation checklist.</span></span>  
4. <span data-ttu-id="d4c9c-182">Wählen Sie auf der Seite ServiceNow die Option **zulassen** aus, die fragt, ob der Security + Compliance-Konnektor eine Verbindung mit Ihrem ServiceNow-Konto herstellen kann.</span><span class="sxs-lookup"><span data-stu-id="d4c9c-182">Select **Allow** in the ServiceNow page that asks whether the Security + Compliance Connector can connect to your ServiceNow account.</span></span>
5. <span data-ttu-id="d4c9c-183">Fahren Sie mit den Setupschritten fort.</span><span class="sxs-lookup"><span data-stu-id="d4c9c-183">Proceed with the setup steps.</span></span>

#### <a name="create-a-security-admin-user"></a><span data-ttu-id="d4c9c-184">Erstellen eines Sicherheitsadministrator Benutzers</span><span class="sxs-lookup"><span data-stu-id="d4c9c-184">Create a security admin user</span></span>

1. <span data-ttu-id="d4c9c-185">Erstellen Sie einen Benutzer mit Sicherheitsadministrator rechten in Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="d4c9c-185">Create a user with security admin privileges in Azure Active Directory.</span></span> <span data-ttu-id="d4c9c-186">Der Benutzer benötigt denselben Namen und dieselbe e-Mail-Adresse wie der Integrationsbenutzer, den Sie aus der Installationsprüfliste erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="d4c9c-186">The user needs to have the same name and email address as the integration user you created from the Installation Checklist.</span></span> <span data-ttu-id="d4c9c-187">Sie können die Sicherheitsadministrator Rolle nach Abschluss der Anmeldung und der Verbindung entfernen.</span><span class="sxs-lookup"><span data-stu-id="d4c9c-187">You can remove the security admin role once login and connection has been completed.</span></span>
2. <span data-ttu-id="d4c9c-188">Melden Sie sich beim Microsoft 365 Security Center als dieser Benutzer an, und befolgen Sie die Installationsschritte.</span><span class="sxs-lookup"><span data-stu-id="d4c9c-188">Log in to the Microsoft 365 security center as this user and follow the setup steps.</span></span>
