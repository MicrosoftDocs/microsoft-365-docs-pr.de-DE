---
title: Erstellen und Nachverfolgen von Tickets über ServiceNow
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
ms.openlocfilehash: 6070878d6cf0efd8a85d05ff6ef89ee49baf4144
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/05/2020
ms.locfileid: "44034188"
---
# <a name="manage-tickets-through-servicenow"></a><span data-ttu-id="864a2-104">Verwalten von Tickets über ServiceNow</span><span class="sxs-lookup"><span data-stu-id="864a2-104">Manage tickets through ServiceNow</span></span>

<span data-ttu-id="864a2-105">ServiceNow ist eine beliebte Cloud Computing-Plattform, mit der Unternehmen digitale Workflows für Unternehmensvorgänge verwalten können.</span><span class="sxs-lookup"><span data-stu-id="864a2-105">ServiceNow is a popular cloud computing platform that helps companies manage digital workflows for enterprise operations.</span></span> <span data-ttu-id="864a2-106">Ihre now-Plattform umfasst IT-Workflows, Mitarbeiter Workflows und Kunden Workflows.</span><span class="sxs-lookup"><span data-stu-id="864a2-106">Their Now platform has IT workflows, employee workflows, and customer workflows.</span></span> <span data-ttu-id="864a2-107">Microsoft hat eine Partnerschaft mit ServiceNow getroffen, um IT-Administratoren die Verwaltung Ihrer Tickets und Aufgaben auf beiden Plattformen zu erleichtern.</span><span class="sxs-lookup"><span data-stu-id="864a2-107">Microsoft has partnered with ServiceNow to make it easier for IT admins to manage their tickets and tasks in both platforms.</span></span> [<span data-ttu-id="864a2-108">Erfahren Sie mehr über ServiceNow</span><span class="sxs-lookup"><span data-stu-id="864a2-108">Learn more about ServiceNow</span></span>](https://www.servicenow.com/)

<span data-ttu-id="864a2-109">Das Microsoft 365-Sicherheitscenter wurde jetzt erweitert, sodass Tickets in ServiceNow nativ erstellt und nachverfolgt werden können.</span><span class="sxs-lookup"><span data-stu-id="864a2-109">Microsoft 365 security center is now enhanced with the ability to natively create and track tickets in ServiceNow.</span></span> <span data-ttu-id="864a2-110">Sicherheitsadministratoren können eine [Microsoft Secure Score](microsoft-secure-score.md) -Verbesserungs Aktion direkt an ServiceNow senden und ein Ticket erstellen.</span><span class="sxs-lookup"><span data-stu-id="864a2-110">Security administrators can send a [Microsoft Secure Score](microsoft-secure-score.md) improvement action directly to ServiceNow and create a ticket.</span></span> <span data-ttu-id="864a2-111">Es können sowohl Incident Management als auch Change Management-Tickets erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="864a2-111">Both incident management and change management tickets can be created.</span></span> <span data-ttu-id="864a2-112">Anschließend können Sie auf der Microsoft Security Center-Startseite und in ServiceNow nachverfolgt werden.</span><span class="sxs-lookup"><span data-stu-id="864a2-112">They can then be tracked in the Microsoft security center home page, and ServiceNow.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="864a2-113">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="864a2-113">Prerequisites</span></span>

<span data-ttu-id="864a2-114">Sie haben Zugriff auf das Microsoft 365 Security Center und eine ServiceNow-Instanz mit:</span><span class="sxs-lookup"><span data-stu-id="864a2-114">Have access to the Microsoft 365 security center and a ServiceNow instance with:</span></span>  

* <span data-ttu-id="864a2-115">Version von Kingston oder höher</span><span class="sxs-lookup"><span data-stu-id="864a2-115">Kingston or higher version</span></span>
* <span data-ttu-id="864a2-116">Administrator-Hi-Anmeldeinformationen</span><span class="sxs-lookup"><span data-stu-id="864a2-116">Have admin HI credentials</span></span>
* <span data-ttu-id="864a2-117">Verfügen über Administratorrechte für die Zielanbieter Instanz</span><span class="sxs-lookup"><span data-stu-id="864a2-117">Have admin privileges on your target vendor instance</span></span>

<span data-ttu-id="864a2-118">ServiceNow empfiehlt Benutzern, die Standardeinstellungen in ihrer ServiceNow-Instanz beizubehalten.</span><span class="sxs-lookup"><span data-stu-id="864a2-118">ServiceNow recommends that users keep default settings in your ServiceNow instance.</span></span> <span data-ttu-id="864a2-119">Anpassungen können beim Abschließen der Installationsprüfliste und der Integration mit dem Microsoft 365 Security Center zu Fehlern führen.</span><span class="sxs-lookup"><span data-stu-id="864a2-119">Having customizations could cause errors when completing the installation checklist and integration with the Microsoft 365 security center.</span></span>

## <a name="data-exchange"></a><span data-ttu-id="864a2-120">Datenaustausch</span><span class="sxs-lookup"><span data-stu-id="864a2-120">Data exchange</span></span>

<span data-ttu-id="864a2-121">Wenn Sie das Microsoft 365 Security Center mit ServiceNow verbinden, erhält Microsoft die folgenden zusätzlichen Daten:</span><span class="sxs-lookup"><span data-stu-id="864a2-121">When you connect the Microsoft 365 security center to ServiceNow, Microsoft receives the following additional data:</span></span>

* <span data-ttu-id="864a2-122">Name der ServiceNow-Instanz</span><span class="sxs-lookup"><span data-stu-id="864a2-122">ServiceNow instance name</span></span>
* <span data-ttu-id="864a2-123">ServiceNow-Client-ID</span><span class="sxs-lookup"><span data-stu-id="864a2-123">ServiceNow client ID</span></span>
* <span data-ttu-id="864a2-124">Geheimer ServiceNow-Client</span><span class="sxs-lookup"><span data-stu-id="864a2-124">ServiceNow client secret</span></span>
* <span data-ttu-id="864a2-125">ServiceNow-Zugriffs & Aktualisierungstoken</span><span class="sxs-lookup"><span data-stu-id="864a2-125">ServiceNow access & refresh tokens</span></span>

<span data-ttu-id="864a2-126">Wenn Sie ein ServiceNow-Ticket aus dem Microsoft 365 Security Center erstellen, werden die folgenden Daten an ServiceNow gesendet:</span><span class="sxs-lookup"><span data-stu-id="864a2-126">When you create a ServiceNow ticket from the Microsoft 365 security center, the following data is sent to ServiceNow:</span></span>

* <span data-ttu-id="864a2-127">Benutzer-ID, die die Ticketerstellung initiiert</span><span class="sxs-lookup"><span data-stu-id="864a2-127">User ID that initiates the ticket creation</span></span>
* <span data-ttu-id="864a2-128">Aufgabenname</span><span class="sxs-lookup"><span data-stu-id="864a2-128">Task name</span></span>
* <span data-ttu-id="864a2-129">Aufgabenbeschreibung</span><span class="sxs-lookup"><span data-stu-id="864a2-129">Task description</span></span>
* <span data-ttu-id="864a2-130">Priorität</span><span class="sxs-lookup"><span data-stu-id="864a2-130">Priority</span></span>
* <span data-ttu-id="864a2-131">Fälligkeitsdatum</span><span class="sxs-lookup"><span data-stu-id="864a2-131">Due date</span></span>
* <span data-ttu-id="864a2-132">Empfehlungsquelle (Benutzer Empfehlung oder Microsoft-Empfehlung)</span><span class="sxs-lookup"><span data-stu-id="864a2-132">Recommendation source (User recommendation or Microsoft recommendation)</span></span>
* <span data-ttu-id="864a2-133">Empfehlungskategorie (Geräte, Daten, apps, Identität, Infrastruktur)</span><span class="sxs-lookup"><span data-stu-id="864a2-133">Recommendation category (Devices, Data, Apps, Identity, Infrastructure)</span></span>

## <a name="connect-microsoft-365-security-center-to-servicenow"></a><span data-ttu-id="864a2-134">Verbinden von Microsoft 365 Security Center mit ServiceNow</span><span class="sxs-lookup"><span data-stu-id="864a2-134">Connect Microsoft 365 security center to ServiceNow</span></span>

<span data-ttu-id="864a2-135">Navigieren Sie zur Microsoft 365-Sicherheitscenter-Startseite, um die ServiceNow-Verbindungskarte anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="864a2-135">Navigate to the Microsoft 365 security center home page to see the ServiceNow connection card.</span></span>

![Verwenden Sie ServiceNow](../../media/do-you-use-servicenow-250.png)

<span data-ttu-id="864a2-137">Wählen Sie "mit ServiceNow verbinden" aus, um die ServiceNow-Setup Seite zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="864a2-137">Select "Connect to ServiceNow" to go to the ServiceNow setup page.</span></span> <span data-ttu-id="864a2-138">Befolgen Sie die Anweisungen, um die Microsoft 365-Connector-APP zu autorisieren.</span><span class="sxs-lookup"><span data-stu-id="864a2-138">Follow the instructions to authorize the Microsoft 365 Connector app.</span></span>

> [!NOTE]
> <span data-ttu-id="864a2-139">Bevor Sie die Verbindung zwischen dem Microsoft 365 Security Center und ServiceNow autorisieren, müssen Sie sicherstellen, dass Sie den Benutzernamen und das Kennwort für die Integration verwenden, die Sie in den Installationsschritten erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="864a2-139">Before you authorize the connection between Microsoft 365 security center and ServiceNow, make sure you use the integration user login and password you created in the installation steps.</span></span> <span data-ttu-id="864a2-140">Verwenden Sie Ihre persönlichen Anmeldeinformationen nicht.</span><span class="sxs-lookup"><span data-stu-id="864a2-140">Do not use your personal credentials.</span></span>

<span data-ttu-id="864a2-141">Nachdem Sie die Anweisungen befolgt und die Verbindung autorisiert haben, zeigen Sie den Verbindungsstatus sowohl auf der Microsoft 365 Security Center-Verbindungsseite als auch in der APP-Erfahrung von Microsoft 365 Ticketing Connector für den ServiceNow an.</span><span class="sxs-lookup"><span data-stu-id="864a2-141">After you have followed the directions and authorizing the connection, view the connection status on both the Microsoft 365 security center connection page and in the ServiceNow Microsoft 365 Ticketing Connector App experience.</span></span> <span data-ttu-id="864a2-142">Jetzt können Sie mit dem Erstellen von Aufgaben beginnen.</span><span class="sxs-lookup"><span data-stu-id="864a2-142">Now you are all set to start creating tasks!</span></span>

## <a name="create-a-task-and-share-it-to-servicenow"></a><span data-ttu-id="864a2-143">Erstellen einer Aufgabe und freigeben für ServiceNow</span><span class="sxs-lookup"><span data-stu-id="864a2-143">Create a task and share it to ServiceNow</span></span>

<span data-ttu-id="864a2-144">Nachdem die Integration eingerichtet wurde, erstellen Sie ServiceNow-Aufgaben basierend auf bestimmten Microsoft Secure Score-Verbesserungs Aktionen.</span><span class="sxs-lookup"><span data-stu-id="864a2-144">Once the integration is set up, create ServiceNow tasks based on specific Microsoft Secure Score improvement actions.</span></span> <span data-ttu-id="864a2-145">Wechseln Sie zu einer Verbesserungs Aktion in Secure Score im Microsoft 365 Security Center-Portal, und wählen Sie das Symbol "freigeben" aus.</span><span class="sxs-lookup"><span data-stu-id="864a2-145">Go to any improvement action in Secure Score in the Microsoft 365 security center portal, and select the "share" icon.</span></span> <span data-ttu-id="864a2-146">Eine der Dropdownoptionen ist ServiceNow.</span><span class="sxs-lookup"><span data-stu-id="864a2-146">One of the dropdown options is ServiceNow.</span></span>

![ServiceNow-Freigabe in sicherer Punktzahl](../../media/servicenow-share.png)

<span data-ttu-id="864a2-148">Es wird eine Aufgabe generiert, in der Sie die Priorität festlegen und den Namen, die Beschreibung oder das Fälligkeitsdatum bearbeiten können.</span><span class="sxs-lookup"><span data-stu-id="864a2-148">A task is generated where you can set the priority and edit the name, description, or due date.</span></span> <span data-ttu-id="864a2-149">Wenn alle erforderlichen Felder ausgefüllt sind, senden Sie die Aufgabe an ServiceNow.</span><span class="sxs-lookup"><span data-stu-id="864a2-149">Once all the required fields are filled in, send the task to ServiceNow.</span></span>

<span data-ttu-id="864a2-150">Die Aufgabe ist in ServiceNow als Microsoft 365 Sicherheits-und Konfigurations Änderungsanforderung sichtbar.</span><span class="sxs-lookup"><span data-stu-id="864a2-150">The task is visible in ServiceNow as a Microsoft 365 Security and Configuration Change Request.</span></span>

## <a name="track-tickets"></a><span data-ttu-id="864a2-151">Nachverfolgen von Tickets</span><span class="sxs-lookup"><span data-stu-id="864a2-151">Track tickets</span></span>

<span data-ttu-id="864a2-152">Nachdem ServiceNow Change Management-und Incident Management-Tickets erstellt wurden, werden diese auf Karten auf der Startseite von Microsoft 365 Security Center angezeigt.</span><span class="sxs-lookup"><span data-stu-id="864a2-152">Once ServiceNow change management and incident management tickets have been created, they are displayed on cards in the Microsoft 365 security center home page.</span></span> <span data-ttu-id="864a2-153">Auf diesen Karten können Sie ein Ticket erstellen, alle Tickets anzeigen oder die ServiceNow-Konfiguration verwalten.</span><span class="sxs-lookup"><span data-stu-id="864a2-153">From these cards, you can create a ticket, view all tickets, or manage the ServiceNow configuration.</span></span>

![ServiceNow Change Management-Tickets](../../media/change-management-375.png)  ![ServiceNow Incident Management Tickets](../../media/incident-management-375.png)

<span data-ttu-id="864a2-156">Um die ServiceNow-Integration in das Microsoft 365 Security Center erneut zu überwachen oder zu verwalten, wählen Sie auf beiden Karten die Option **Manage ServiceNow Configuration** aus.</span><span class="sxs-lookup"><span data-stu-id="864a2-156">To re-provision or manage your ServiceNow integration in the Microsoft 365 security center, select **Manage ServiceNow configuration** on either of the cards.</span></span> <span data-ttu-id="864a2-157">Entfernen Sie von dort die aktuelle ServiceNow-Verbindung, und passen Sie die Ticket Statusnamen an.</span><span class="sxs-lookup"><span data-stu-id="864a2-157">From there, remove the current ServiceNow connection and customize ticket state names.</span></span>

<span data-ttu-id="864a2-158">Wenn ServiceNow-Tickets im Microsoft 365 Security Center angezeigt werden, werden Ihre Aufgaben an einer Stelle gespeichert, an der Sie neben den anderen Sicherheits Dashboard-Elementen nachverfolgt und bearbeitet werden können.</span><span class="sxs-lookup"><span data-stu-id="864a2-158">With ServiceNow tickets visible in the Microsoft 365 security center, your tasks live in a place where they can be tracked and acted upon alongside your other security dashboard items.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="864a2-159">Problembehandlung</span><span class="sxs-lookup"><span data-stu-id="864a2-159">Troubleshooting</span></span>

### <a name="you-receive-an-error-in-the-first-step-of-the-installation-checklist-oauth-creation"></a><span data-ttu-id="864a2-160">Sie erhalten eine Fehlermeldung im ersten Schritt der Installationsprüfliste (OAuth-Erstellung)</span><span class="sxs-lookup"><span data-stu-id="864a2-160">You receive an error in the first step of the installation checklist (OAuth creation)</span></span>

<span data-ttu-id="864a2-161">**Fehlermeldung**: der Lesevorgang für "oauth_entity" aus dem Bereich "x_mioms_m365ticket" wurde aufgrund der bereichsübergreifenden Zugriffsrichtlinie der Tabelle verweigert.</span><span class="sxs-lookup"><span data-stu-id="864a2-161">**Error Message**: Read operation against 'oauth_entity' from scope 'x_mioms_m365ticket' has been refused due to the table's cross-scope access policy</span></span>

<span data-ttu-id="864a2-162">Die APP geht davon aus, dass ein Administrator in der ServiceNow-Instanz OAuth-Entitäten erstellen und lesen kann.</span><span class="sxs-lookup"><span data-stu-id="864a2-162">The app assumes any admin on the ServiceNow instance can create and read OAuth entities.</span></span> <span data-ttu-id="864a2-163">Dieser Fehler kann aufgrund einer Anpassung Ihrer Instanz von ServiceNow verursacht werden, wodurch die Benutzer eingeschränkt werden, die OAuth-Entitäten erstellen/lesen können.</span><span class="sxs-lookup"><span data-stu-id="864a2-163">This error could be caused due to a customization on your instance of ServiceNow, which restricts who can create/read OAuth entities.</span></span>

<span data-ttu-id="864a2-164">**ServiceNow empfiehlt Benutzern, die Standardfunktionalität beizubehalten.**</span><span class="sxs-lookup"><span data-stu-id="864a2-164">**ServiceNow recommends that users keep default functionality.**</span></span>

<span data-ttu-id="864a2-165">Legen Sie die Tabellen Konfigurationen "Anwendungs Registrierungen" auf "Standard" fest:</span><span class="sxs-lookup"><span data-stu-id="864a2-165">Set the "application registries" table configurations to default:</span></span>

* <span data-ttu-id="864a2-166">Label = Anwendungs Registrierungen</span><span class="sxs-lookup"><span data-stu-id="864a2-166">Label = Application Registeries</span></span>
* <span data-ttu-id="864a2-167">Name = oauth_entity</span><span class="sxs-lookup"><span data-stu-id="864a2-167">Name = oauth_entity</span></span>
* <span data-ttu-id="864a2-168">Zugänglich von = alle Anwendungsbereiche</span><span class="sxs-lookup"><span data-stu-id="864a2-168">Accessible from = All application scopes</span></span>
* <span data-ttu-id="864a2-169">Can read = Kontrollkästchen aktiviert</span><span class="sxs-lookup"><span data-stu-id="864a2-169">Can read = check box selected</span></span>

### <a name="how-to-validate-the-oauth-entity-created-for-microsoft-365-security--compliance-connector"></a><span data-ttu-id="864a2-170">Überprüfen der OAuth-Entität, die für Microsoft 365 Security & Compliance Connector erstellt wurde</span><span class="sxs-lookup"><span data-stu-id="864a2-170">How to validate the OAuth entity created for Microsoft 365 Security & Compliance connector</span></span>

<span data-ttu-id="864a2-171">Wechseln Sie zur Tabelle Anwendungs Registrierungstabellen (**Menü > System OAuth > Anwendungsregistrierung**) in ServiceNow, und suchen Sie nach der von Ihnen erstellten OAuth-Entität mit dem Namen, den Sie Ihr zugewiesen haben.</span><span class="sxs-lookup"><span data-stu-id="864a2-171">Go to application registries table (**Menu > System OAuth > Application Registry**) in ServiceNow and find the OAuth entity created by you, with the name that you assigned it.</span></span>

### <a name="logging-in-as-the-integration-user"></a><span data-ttu-id="864a2-172">Anmelden als Integrationsbenutzer</span><span class="sxs-lookup"><span data-stu-id="864a2-172">Logging in as the integration user</span></span>

<span data-ttu-id="864a2-173">Bevor Sie die Verbindung zwischen dem Microsoft 365 Security Center und ServiceNow autorisieren, müssen Sie sicherstellen, dass Sie den Benutzernamen und das Kennwort für die Integration verwenden, die Sie in den Installationsschritten erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="864a2-173">Before you authorize the connection between Microsoft 365 security center and ServiceNow, make sure you use the integration user login and password you created in the installation steps.</span></span> <span data-ttu-id="864a2-174">Verwenden Sie Ihre persönlichen Anmeldeinformationen nicht.</span><span class="sxs-lookup"><span data-stu-id="864a2-174">Do not use your personal credentials.</span></span>

1. <span data-ttu-id="864a2-175">Wechseln Sie zur Autorisierungs Seite in ServiceNow.</span><span class="sxs-lookup"><span data-stu-id="864a2-175">Go the authorization page in ServiceNow.</span></span>
2. <span data-ttu-id="864a2-176">Wenn Sie mit Ihren persönlichen Anmeldeinformationen angemeldet sind, wählen Sie den Link **nicht** in der rechten oberen Ecke aus.</span><span class="sxs-lookup"><span data-stu-id="864a2-176">If you are signed in with your personal credentials, select the **Not You** link in the upper right-hand corner.</span></span>
3. <span data-ttu-id="864a2-177">Melden Sie sich bei ServiceNow als der Integrationsbenutzer an, den Sie zuvor in der Installationsprüfliste erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="864a2-177">Log in to ServiceNow as the integration user you created previously from the installation checklist.</span></span>  
4. <span data-ttu-id="864a2-178">Wählen Sie auf der Seite ServiceNow die Option **zulassen** aus, die fragt, ob der Security + Compliance-Konnektor eine Verbindung mit Ihrem ServiceNow-Konto herstellen kann.</span><span class="sxs-lookup"><span data-stu-id="864a2-178">Select **Allow** in the ServiceNow page that asks whether the Security + Compliance Connector can connect to your ServiceNow account.</span></span>
5. <span data-ttu-id="864a2-179">Fahren Sie mit den Setupschritten fort.</span><span class="sxs-lookup"><span data-stu-id="864a2-179">Proceed with the setup steps.</span></span>

### <a name="how-to-validate-the-integration-user-created-with-the-installation-checklist-for-microsoft-365-security--compliance-connector"></a><span data-ttu-id="864a2-180">Überprüfen des Integrations Benutzers, der mit der Installationsprüfliste für Microsoft 365 Security & Compliance Connector erstellt wurde</span><span class="sxs-lookup"><span data-stu-id="864a2-180">How to validate the Integration User created with the installation checklist for Microsoft 365 Security & Compliance connector</span></span>

<span data-ttu-id="864a2-181">Wechseln Sie zu Benutzertabelle **(Menü > Benutzerverwaltung > Benutzer**) in ServiceNow, und suchen Sie den von Ihnen erstellten Integrationsbenutzer mit dem Namen, den Sie ihm zugewiesen haben.</span><span class="sxs-lookup"><span data-stu-id="864a2-181">Go to Users Table **(Menu > User Administration > Users**) in ServiceNow and find the Integration user created by you, with the name that you assigned it.</span></span>

### <a name="your-company-has-single-sign-on-enabled-which-prevents-you-from-connecting-to-servicenow-through-the-microsoft-365-security-center"></a><span data-ttu-id="864a2-182">Ihr Unternehmen verfügt über ein einmaliges Anmelden, das verhindert, dass Sie sich über das Microsoft 365 Security Center mit ServiceNow verbinden.</span><span class="sxs-lookup"><span data-stu-id="864a2-182">Your company has single sign-on enabled which prevents you from connecting to ServiceNow through the Microsoft 365 security center</span></span>

<span data-ttu-id="864a2-183">Wenn Ihr Unternehmen einmaliges Anmelden aktiviert hat und Sie eine Fehlermeldung erhalten oder die Anmeldung nicht erfolgreich war, führen Sie eine der beiden Lösungen aus.</span><span class="sxs-lookup"><span data-stu-id="864a2-183">If your company has enabled single sign-on and you receive an error or login is unsuccessful, follow one of the two solutions.</span></span>

#### <a name="log-into-servicenow-as-the-integration-user"></a><span data-ttu-id="864a2-184">Melden Sie sich als Integrationsbenutzer bei ServiceNow an.</span><span class="sxs-lookup"><span data-stu-id="864a2-184">Log into ServiceNow as the integration user</span></span>

1. <span data-ttu-id="864a2-185">Navigieren Sie zurück zur Autorisierungs Seite in ServiceNow.</span><span class="sxs-lookup"><span data-stu-id="864a2-185">Navigate back to the authorization page in ServiceNow.</span></span>
2. <span data-ttu-id="864a2-186">Klicken Sie in der rechten oberen Ecke auf den Link **Not You** .</span><span class="sxs-lookup"><span data-stu-id="864a2-186">Select the **Not You** link in the upper right-hand corner.</span></span>
3. <span data-ttu-id="864a2-187">Melden Sie sich bei ServiceNow als der Integrationsbenutzer an, den Sie zuvor in der Installationsprüfliste erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="864a2-187">Log in to ServiceNow as the integration user you created previously from the installation checklist.</span></span>  
4. <span data-ttu-id="864a2-188">Wählen Sie auf der Seite ServiceNow die Option **zulassen** aus, die fragt, ob der Security + Compliance-Konnektor eine Verbindung mit Ihrem ServiceNow-Konto herstellen kann.</span><span class="sxs-lookup"><span data-stu-id="864a2-188">Select **Allow** in the ServiceNow page that asks whether the Security + Compliance Connector can connect to your ServiceNow account.</span></span>
5. <span data-ttu-id="864a2-189">Fahren Sie mit den Setupschritten fort.</span><span class="sxs-lookup"><span data-stu-id="864a2-189">Proceed with the setup steps.</span></span>

#### <a name="create-a-security-admin-user"></a><span data-ttu-id="864a2-190">Erstellen eines Sicherheitsadministrator Benutzers</span><span class="sxs-lookup"><span data-stu-id="864a2-190">Create a security admin user</span></span>

1. <span data-ttu-id="864a2-191">Erstellen Sie einen Benutzer mit Sicherheitsadministrator rechten in Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="864a2-191">Create a user with security admin privileges in Azure Active Directory.</span></span> <span data-ttu-id="864a2-192">Der Benutzer benötigt denselben Namen und dieselbe e-Mail-Adresse wie der Integrationsbenutzer, den Sie aus der Installationsprüfliste erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="864a2-192">The user needs to have the same name and email address as the integration user you created from the Installation Checklist.</span></span> <span data-ttu-id="864a2-193">Sie können die Sicherheitsadministrator Rolle nach Abschluss der Anmeldung und der Verbindung entfernen.</span><span class="sxs-lookup"><span data-stu-id="864a2-193">You can remove the security admin role once login and connection has been completed.</span></span>
2. <span data-ttu-id="864a2-194">Melden Sie sich beim Microsoft 365 Security Center als dieser Benutzer an, und befolgen Sie die Installationsschritte.</span><span class="sxs-lookup"><span data-stu-id="864a2-194">Log in to the Microsoft 365 security center as this user and follow the setup steps.</span></span>

### <a name="ip-filtering"></a><span data-ttu-id="864a2-195">IP-Filterung</span><span class="sxs-lookup"><span data-stu-id="864a2-195">IP filtering</span></span>

<span data-ttu-id="864a2-196">Wenn Sie die IP-Filterung aktiviert haben, müssen Sie möglicherweise explizit IP-Adressen zulassen.</span><span class="sxs-lookup"><span data-stu-id="864a2-196">If you have enabled IP filtering, you may need to explicitly allow IP addresses.</span></span> <span data-ttu-id="864a2-197">Informationen zum Zulassen von IP-Bereichen in ServiceNow finden Sie unter [IP Address Access Control](https://docs.servicenow.com/bundle/orlando-platform-administration/page/administer/login/task/t_AccessControl.html) .</span><span class="sxs-lookup"><span data-stu-id="864a2-197">See [IP Address Access Control](https://docs.servicenow.com/bundle/orlando-platform-administration/page/administer/login/task/t_AccessControl.html) for information on how to allow IP ranges in ServiceNow.</span></span> <span data-ttu-id="864a2-198">Eine Liste der zulässigen IP-Adressen finden Sie unter [Azure IP Ranges and Service Tags-Public Cloud](https://www.microsoft.com/en-us/download/details.aspx?id=56519) .</span><span class="sxs-lookup"><span data-stu-id="864a2-198">See [Azure IP Ranges and Service Tags - Public Cloud](https://www.microsoft.com/en-us/download/details.aspx?id=56519) for a list of IP addresses to allow.</span></span>

### <a name="installation-is-complete-but-dont-see-tickets-and-cant-share"></a><span data-ttu-id="864a2-199">Die Installation ist abgeschlossen, es werden jedoch keine Tickets angezeigt und können nicht freigegeben werden</span><span class="sxs-lookup"><span data-stu-id="864a2-199">Installation is complete but don't see tickets and can't share</span></span>

<span data-ttu-id="864a2-200">Wenn die Installations-und Setupschritte abgeschlossen wurden, die ServiceNow-Karten jedoch nicht auf der Startseite angezeigt werden und nicht von Microsoft Secure Score an ServiceNow freigegeben werden können, überprüfen Sie den Status der https://security.microsoft.com/ticketProvisioningSeite Bereitstellung unter.</span><span class="sxs-lookup"><span data-stu-id="864a2-200">If the installation and setup steps have been completed, but you don't see the ServiceNow cards on the home page and can't share to ServiceNow from Microsoft Secure Score, check the status of the provisioning page at https://security.microsoft.com/ticketProvisioning.</span></span> <span data-ttu-id="864a2-201">Wählen Sie **autorisieren** und zur Startseite zurückkehren.</span><span class="sxs-lookup"><span data-stu-id="864a2-201">Select **Authorize** and return to the home page.</span></span> <span data-ttu-id="864a2-202">Die Karten sollten angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="864a2-202">The cards should appear.</span></span>

