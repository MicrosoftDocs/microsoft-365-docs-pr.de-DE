---
title: Integrieren von ServiceNow-Tickets in das Microsoft 365 Security Center und Compliance Center
description: Informationen zum Erstellen und Nachverfolgen von Tickets in ServiceNow im Microsoft 365 Security Center und Compliance Center.
keywords: Sicherheit, Microsoft 365, M365, Compliance, Compliance Center, Sicherheitscenter, ServiceNow, Tickets, Aufgaben, Schnee, Verbindung
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
ms.openlocfilehash: ca13234a93ffcc226be45d337880692a3a39c28b
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2020
ms.locfileid: "48196119"
---
# <a name="integrate-servicenow-tickets-into-the-microsoft-365-security-center-and-compliance-center"></a><span data-ttu-id="42b10-104">Integrieren von ServiceNow-Tickets in das Microsoft 365 Security Center und Compliance Center</span><span class="sxs-lookup"><span data-stu-id="42b10-104">Integrate ServiceNow tickets into the Microsoft 365 security center and compliance center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


[!include[Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="42b10-105">ServiceNow ist eine beliebte Cloud Computing-Plattform, mit der Unternehmen digitale Workflows für Unternehmensvorgänge verwalten können.</span><span class="sxs-lookup"><span data-stu-id="42b10-105">ServiceNow is a popular cloud computing platform that helps companies manage digital workflows for enterprise operations.</span></span> <span data-ttu-id="42b10-106">Ihre now-Plattform umfasst IT-Workflows, Mitarbeiter Workflows und Kunden Workflows.</span><span class="sxs-lookup"><span data-stu-id="42b10-106">Their Now platform has IT workflows, employee workflows, and customer workflows.</span></span> [<span data-ttu-id="42b10-107">Erfahren Sie mehr über ServiceNow</span><span class="sxs-lookup"><span data-stu-id="42b10-107">Learn more about ServiceNow</span></span>](https://www.servicenow.com/)

<span data-ttu-id="42b10-108">Microsoft hat eine Partnerschaft mit ServiceNow getroffen, um IT-Administratoren die Verwaltung Ihrer Tickets und Aufgaben auf beiden Plattformen zu erleichtern.</span><span class="sxs-lookup"><span data-stu-id="42b10-108">Microsoft has partnered with ServiceNow to make it easier for IT admins to manage their tickets and tasks in both platforms.</span></span> <span data-ttu-id="42b10-109">Das [Microsoft 365 Security Center](overview-security-center.md) und das [Microsoft 365 Compliance Center](https://docs.microsoft.com/microsoft-365/compliance/microsoft-365-compliance-center) werden erweitert, sodass Tickets in ServiceNow nativ erstellt und nachverfolgt werden können.</span><span class="sxs-lookup"><span data-stu-id="42b10-109">[Microsoft 365 security center](overview-security-center.md) and the [Microsoft 365 compliance center](https://docs.microsoft.com/microsoft-365/compliance/microsoft-365-compliance-center) are being enhanced with the ability to natively create and track tickets in ServiceNow.</span></span>

- [<span data-ttu-id="42b10-110">**Verwalten von ServiceNow-Tickets im Sicherheitscenter**</span><span class="sxs-lookup"><span data-stu-id="42b10-110">**Manage ServiceNow tickets in the security center**</span></span>](tickets-security-center.md)
- <span data-ttu-id="42b10-111">**Verwalten von ServiceNow-Tickets im Compliance Center** (demnächst verfügbar)</span><span class="sxs-lookup"><span data-stu-id="42b10-111">**Manage ServiceNow tickets in the compliance center** (coming soon)</span></span>

## <a name="prerequisites"></a><span data-ttu-id="42b10-112">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="42b10-112">Prerequisites</span></span>

<span data-ttu-id="42b10-113">Zugriff auf das Microsoft 365 Security Center oder Compliance Center und eine ServiceNow-Instanz mit:</span><span class="sxs-lookup"><span data-stu-id="42b10-113">Have access to the Microsoft 365 security center or compliance center and a ServiceNow instance with:</span></span>  

* <span data-ttu-id="42b10-114">Version von Kingston oder höher</span><span class="sxs-lookup"><span data-stu-id="42b10-114">Kingston or higher version</span></span>
* <span data-ttu-id="42b10-115">Administrator-Hi-Anmeldeinformationen</span><span class="sxs-lookup"><span data-stu-id="42b10-115">Have admin HI credentials</span></span>
* <span data-ttu-id="42b10-116">Verfügen über Administratorrechte für die Zielanbieter Instanz</span><span class="sxs-lookup"><span data-stu-id="42b10-116">Have admin privileges on your target vendor instance</span></span>

<span data-ttu-id="42b10-117">ServiceNow empfiehlt Benutzern, die Standardeinstellungen in ihrer ServiceNow-Instanz beizubehalten.</span><span class="sxs-lookup"><span data-stu-id="42b10-117">ServiceNow recommends that users keep default settings in your ServiceNow instance.</span></span> <span data-ttu-id="42b10-118">Anpassungen können beim Abschließen der Installationsprüfliste und der Integration mit dem Microsoft 365 Security Center zu Fehlern führen.</span><span class="sxs-lookup"><span data-stu-id="42b10-118">Having customizations could cause errors when completing the installation checklist and integration with the Microsoft 365 security center.</span></span>

## <a name="data-exchange"></a><span data-ttu-id="42b10-119">Datenaustausch</span><span class="sxs-lookup"><span data-stu-id="42b10-119">Data exchange</span></span>

<span data-ttu-id="42b10-120">Wenn Sie das Microsoft 365 Security Center oder das Compliance Center mit ServiceNow verbinden, erhält Microsoft die folgenden zusätzlichen Daten:</span><span class="sxs-lookup"><span data-stu-id="42b10-120">When you connect the Microsoft 365 security center or compliance center to ServiceNow, Microsoft receives the following additional data:</span></span>

* <span data-ttu-id="42b10-121">Name der ServiceNow-Instanz</span><span class="sxs-lookup"><span data-stu-id="42b10-121">ServiceNow instance name</span></span>
* <span data-ttu-id="42b10-122">ServiceNow-Client-ID</span><span class="sxs-lookup"><span data-stu-id="42b10-122">ServiceNow client ID</span></span>
* <span data-ttu-id="42b10-123">Geheimer ServiceNow-Client</span><span class="sxs-lookup"><span data-stu-id="42b10-123">ServiceNow client secret</span></span>
* <span data-ttu-id="42b10-124">ServiceNow-Zugriffs & Aktualisierungstoken</span><span class="sxs-lookup"><span data-stu-id="42b10-124">ServiceNow access & refresh tokens</span></span>

<span data-ttu-id="42b10-125">Wenn Sie ein ServiceNow-Ticket im Microsoft 365 Security Center oder im Compliance Center erstellen, werden die folgenden Daten an ServiceNow gesendet:</span><span class="sxs-lookup"><span data-stu-id="42b10-125">When you create a ServiceNow ticket from the Microsoft 365 security center or compliance center, the following data is sent to ServiceNow:</span></span>

* <span data-ttu-id="42b10-126">Benutzer-ID, die die Ticketerstellung initiiert</span><span class="sxs-lookup"><span data-stu-id="42b10-126">User ID that initiates the ticket creation</span></span>
* <span data-ttu-id="42b10-127">Aufgabenname</span><span class="sxs-lookup"><span data-stu-id="42b10-127">Task name</span></span>
* <span data-ttu-id="42b10-128">Aufgabenbeschreibung</span><span class="sxs-lookup"><span data-stu-id="42b10-128">Task description</span></span>
* <span data-ttu-id="42b10-129">Priorität</span><span class="sxs-lookup"><span data-stu-id="42b10-129">Priority</span></span>
* <span data-ttu-id="42b10-130">Fälligkeitsdatum</span><span class="sxs-lookup"><span data-stu-id="42b10-130">Due date</span></span>
* <span data-ttu-id="42b10-131">Empfehlungsquelle (Benutzer Empfehlung oder Microsoft-Empfehlung)</span><span class="sxs-lookup"><span data-stu-id="42b10-131">Recommendation source (User recommendation or Microsoft recommendation)</span></span>
* <span data-ttu-id="42b10-132">Empfehlungskategorie (Geräte, Daten, apps, Identität, Infrastruktur)</span><span class="sxs-lookup"><span data-stu-id="42b10-132">Recommendation category (Devices, Data, Apps, Identity, Infrastructure)</span></span>

## <a name="connect-to-servicenow"></a><span data-ttu-id="42b10-133">Herstellen einer Verbindung mit ServiceNow</span><span class="sxs-lookup"><span data-stu-id="42b10-133">Connect to ServiceNow</span></span>

<span data-ttu-id="42b10-134">Informationen zum Herstellen einer Verbindung mit ServiceNow finden Sie unter [Erstellen und Nachverfolgen von ServiceNow-Tickets im Microsoft 365 Security Center](tickets-security-center.md) .</span><span class="sxs-lookup"><span data-stu-id="42b10-134">Go to [Create and track ServiceNow tickets in the Microsoft 365 security center](tickets-security-center.md) to learn how to connect to ServiceNow.</span></span> <span data-ttu-id="42b10-135">Eine Verbindung mit dem Microsoft 365 Compliance Center wird in Kürze verfügbar sein.</span><span class="sxs-lookup"><span data-stu-id="42b10-135">Connecting from the Microsoft 365 compliance center is coming soon.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="42b10-136">Problembehandlung</span><span class="sxs-lookup"><span data-stu-id="42b10-136">Troubleshooting</span></span>

### <a name="you-receive-an-error-in-the-first-step-of-the-installation-checklist-oauth-creation"></a><span data-ttu-id="42b10-137">Sie erhalten eine Fehlermeldung im ersten Schritt der Installationsprüfliste (OAuth-Erstellung)</span><span class="sxs-lookup"><span data-stu-id="42b10-137">You receive an error in the first step of the installation checklist (OAuth creation)</span></span>

<span data-ttu-id="42b10-138">**Fehlermeldung**: der Lesevorgang für "oauth_entity" aus dem Bereich "x_mioms_m365ticket" wurde aufgrund der bereichsübergreifenden Zugriffsrichtlinie der Tabelle abgelehnt.</span><span class="sxs-lookup"><span data-stu-id="42b10-138">**Error Message**: Read operation against 'oauth_entity' from scope 'x_mioms_m365ticket' has been refused because of the table's cross-scope access policy</span></span>

<span data-ttu-id="42b10-139">Die APP geht davon aus, dass ein Administrator in der ServiceNow-Instanz OAuth-Entitäten erstellen und lesen kann.</span><span class="sxs-lookup"><span data-stu-id="42b10-139">The app assumes any admin on the ServiceNow instance can create and read OAuth entities.</span></span> <span data-ttu-id="42b10-140">Dieser Fehler kann durch eine Anpassung in Ihrer Instanz von ServiceNow verursacht werden, die die Benutzer einschränken kann, die OAuth-Entitäten erstellen oder lesen können.</span><span class="sxs-lookup"><span data-stu-id="42b10-140">This error could be caused by a customization in your instance of ServiceNow that restricts who can create or read OAuth entities.</span></span>

<span data-ttu-id="42b10-141">**ServiceNow empfiehlt Benutzern, die Standardfunktionalität beizubehalten.**</span><span class="sxs-lookup"><span data-stu-id="42b10-141">**ServiceNow recommends that users keep default functionality.**</span></span>

<span data-ttu-id="42b10-142">Legen Sie die Tabellen Konfigurationen "Anwendungs Registrierungen" auf "Standard" fest:</span><span class="sxs-lookup"><span data-stu-id="42b10-142">Set the "application registries" table configurations to default:</span></span>

* <span data-ttu-id="42b10-143">Label = Anwendungs Registrierungen</span><span class="sxs-lookup"><span data-stu-id="42b10-143">Label = Application Registeries</span></span>
* <span data-ttu-id="42b10-144">Name = oauth_entity</span><span class="sxs-lookup"><span data-stu-id="42b10-144">Name = oauth_entity</span></span>
* <span data-ttu-id="42b10-145">Zugänglich von = alle Anwendungsbereiche</span><span class="sxs-lookup"><span data-stu-id="42b10-145">Accessible from = All application scopes</span></span>
* <span data-ttu-id="42b10-146">Can read = Kontrollkästchen aktiviert</span><span class="sxs-lookup"><span data-stu-id="42b10-146">Can read = check box selected</span></span>

### <a name="how-to-validate-the-oauth-entity-created-for-microsoft-365-security--compliance-connector"></a><span data-ttu-id="42b10-147">Überprüfen der OAuth-Entität, die für Microsoft 365 Security & Compliance Connector erstellt wurde</span><span class="sxs-lookup"><span data-stu-id="42b10-147">How to validate the OAuth entity created for Microsoft 365 Security & Compliance connector</span></span>

<span data-ttu-id="42b10-148">Wechseln Sie zur Tabelle Anwendungs Registrierungstabellen (**Menü > System OAuth > Anwendungsregistrierung**) in ServiceNow.</span><span class="sxs-lookup"><span data-stu-id="42b10-148">Go to application registries table (**Menu > System OAuth > Application Registry**) in ServiceNow.</span></span> <span data-ttu-id="42b10-149">Suchen Sie die von Ihnen erstellte OAuth-Entität mit dem Namen, den Sie Ihr zugewiesen haben.</span><span class="sxs-lookup"><span data-stu-id="42b10-149">Find the OAuth entity created by you, with the name that you assigned it.</span></span>

### <a name="signing-in-as-the-integration-user"></a><span data-ttu-id="42b10-150">Anmelden als Integrationsbenutzer</span><span class="sxs-lookup"><span data-stu-id="42b10-150">Signing in as the integration user</span></span>

<span data-ttu-id="42b10-151">Bevor Sie die Verbindung zwischen dem Microsoft 365 Security Center und ServiceNow autorisieren, müssen Sie sicherstellen, dass Sie die Benutzeranmeldung und das Kennwort für die Integration verwenden, die Sie in den Installationsschritten erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="42b10-151">Before you authorize the connection between Microsoft 365 security center and ServiceNow, make sure you use the integration user sign in and password you created in the installation steps.</span></span> <span data-ttu-id="42b10-152">Verwenden Sie Ihre persönlichen Anmeldeinformationen nicht.</span><span class="sxs-lookup"><span data-stu-id="42b10-152">Don't use your personal credentials.</span></span>

1. <span data-ttu-id="42b10-153">Wechseln Sie zur Autorisierungs Seite in ServiceNow.</span><span class="sxs-lookup"><span data-stu-id="42b10-153">Go the authorization page in ServiceNow.</span></span>
2. <span data-ttu-id="42b10-154">Wenn Sie mit Ihren persönlichen Anmeldeinformationen angemeldet sind, wählen Sie den Link **nicht** in der oberen rechten Ecke aus.</span><span class="sxs-lookup"><span data-stu-id="42b10-154">If you're signed in with your personal credentials, select the **Not You** link in the upper right-hand corner.</span></span>
3. <span data-ttu-id="42b10-155">Melden Sie sich bei ServiceNow als der Integrationsbenutzer an, den Sie zuvor in der Installationsprüfliste erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="42b10-155">Sign in to ServiceNow as the integration user you created previously from the installation checklist.</span></span>  
4. <span data-ttu-id="42b10-156">Wählen Sie auf der Seite ServiceNow die Option **zulassen** aus, die fragt, ob der Security + Compliance-Konnektor eine Verbindung mit Ihrem ServiceNow-Konto herstellen kann.</span><span class="sxs-lookup"><span data-stu-id="42b10-156">Select **Allow** in the ServiceNow page that asks whether the Security + Compliance Connector can connect to your ServiceNow account.</span></span>
5. <span data-ttu-id="42b10-157">Fahren Sie mit den Setupschritten fort.</span><span class="sxs-lookup"><span data-stu-id="42b10-157">Continue with the setup steps.</span></span>

### <a name="how-to-validate-the-integration-user-created-with-the-installation-checklist-for-microsoft-365-security--compliance-connector"></a><span data-ttu-id="42b10-158">Überprüfen des Integrations Benutzers, der mit der Installationsprüfliste für Microsoft 365 Security & Compliance Connector erstellt wurde</span><span class="sxs-lookup"><span data-stu-id="42b10-158">How to validate the Integration User created with the installation checklist for Microsoft 365 Security & Compliance connector</span></span>

<span data-ttu-id="42b10-159">Wechseln Sie zu Benutzertabelle **(Menü > Benutzerverwaltung > Benutzer**) in ServiceNow, und suchen Sie den von Ihnen erstellten Integrationsbenutzer mit dem Namen, den Sie ihm zugewiesen haben.</span><span class="sxs-lookup"><span data-stu-id="42b10-159">Go to Users Table **(Menu > User Administration > Users**) in ServiceNow and find the Integration user created by you, with the name that you assigned it.</span></span>

### <a name="your-company-has-single-sign-on-enabled-which-prevents-you-from-connecting-to-servicenow-through-the-microsoft-365-security-center"></a><span data-ttu-id="42b10-160">Ihr Unternehmen verfügt über ein einmaliges Anmelden, das verhindert, dass Sie sich über das Microsoft 365 Security Center mit ServiceNow verbinden.</span><span class="sxs-lookup"><span data-stu-id="42b10-160">Your company has single sign-on enabled which prevents you from connecting to ServiceNow through the Microsoft 365 security center</span></span>

<span data-ttu-id="42b10-161">Wenn Ihr Unternehmen einmaliges Anmelden aktiviert hat und Sie eine Fehlermeldung erhalten oder die Anmeldung nicht erfolgreich war, führen Sie eine der beiden Lösungen aus.</span><span class="sxs-lookup"><span data-stu-id="42b10-161">If your company has enabled single sign-on and you receive an error or sign in is unsuccessful, follow one of the two solutions.</span></span>

#### <a name="sign-in-to-servicenow-as-the-integration-user"></a><span data-ttu-id="42b10-162">Melden Sie sich bei ServiceNow als Integrationsbenutzer an.</span><span class="sxs-lookup"><span data-stu-id="42b10-162">Sign in to ServiceNow as the integration user</span></span>

1. <span data-ttu-id="42b10-163">Navigieren Sie zurück zur Autorisierungs Seite in ServiceNow.</span><span class="sxs-lookup"><span data-stu-id="42b10-163">Navigate back to the authorization page in ServiceNow.</span></span>
2. <span data-ttu-id="42b10-164">Klicken Sie in der rechten oberen Ecke auf den Link **Not You** .</span><span class="sxs-lookup"><span data-stu-id="42b10-164">Select the **Not You** link in the upper right-hand corner.</span></span>
3. <span data-ttu-id="42b10-165">Melden Sie sich bei ServiceNow als der Integrationsbenutzer an, den Sie zuvor in der Installationsprüfliste erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="42b10-165">Sign in to ServiceNow as the integration user you created previously from the installation checklist.</span></span>  
4. <span data-ttu-id="42b10-166">Wählen Sie auf der Seite ServiceNow die Option **zulassen** aus, die fragt, ob der Security + Compliance-Konnektor eine Verbindung mit Ihrem ServiceNow-Konto herstellen kann.</span><span class="sxs-lookup"><span data-stu-id="42b10-166">Select **Allow** in the ServiceNow page that asks whether the Security + Compliance Connector can connect to your ServiceNow account.</span></span>
5. <span data-ttu-id="42b10-167">Fahren Sie mit den Setupschritten fort.</span><span class="sxs-lookup"><span data-stu-id="42b10-167">Continue with the setup steps.</span></span>

#### <a name="create-a-security-admin-user"></a><span data-ttu-id="42b10-168">Erstellen eines Sicherheitsadministrator Benutzers</span><span class="sxs-lookup"><span data-stu-id="42b10-168">Create a security admin user</span></span>

1. <span data-ttu-id="42b10-169">Erstellen Sie einen Benutzer mit Sicherheitsadministrator rechten in Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="42b10-169">Create a user with security admin privileges in Azure Active Directory.</span></span> <span data-ttu-id="42b10-170">Der Benutzer benötigt denselben Namen und dieselbe e-Mail-Adresse wie der Integrationsbenutzer, den Sie aus der Installationsprüfliste erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="42b10-170">The user needs to have the same name and email address as the integration user you created from the Installation Checklist.</span></span> <span data-ttu-id="42b10-171">Sie können die Sicherheitsadministrator Rolle nach Abschluss der Anmeldung und der Verbindung entfernen.</span><span class="sxs-lookup"><span data-stu-id="42b10-171">You can remove the security admin role once sign-in and connection has been completed.</span></span>
2. <span data-ttu-id="42b10-172">Melden Sie sich beim Microsoft 365 Security Center als dieser Benutzer an, und befolgen Sie die Installationsschritte.</span><span class="sxs-lookup"><span data-stu-id="42b10-172">Sign in to the Microsoft 365 security center as this user and follow the setup steps.</span></span>

### <a name="ip-filtering"></a><span data-ttu-id="42b10-173">IP-Filterung</span><span class="sxs-lookup"><span data-stu-id="42b10-173">IP filtering</span></span>

<span data-ttu-id="42b10-174">Wenn Sie die IP-Filterung aktiviert haben, müssen Sie möglicherweise explizit IP-Adressen zulassen.</span><span class="sxs-lookup"><span data-stu-id="42b10-174">If you have enabled IP filtering, you may need to explicitly allow IP addresses.</span></span> <span data-ttu-id="42b10-175">Informationen zum Zulassen von IP-Bereichen in ServiceNow finden Sie unter [IP Address Access Control](https://docs.servicenow.com/bundle/orlando-platform-administration/page/administer/login/task/t_AccessControl.html) .</span><span class="sxs-lookup"><span data-stu-id="42b10-175">See [IP Address Access Control](https://docs.servicenow.com/bundle/orlando-platform-administration/page/administer/login/task/t_AccessControl.html) for information on how to allow IP ranges in ServiceNow.</span></span> <span data-ttu-id="42b10-176">Eine Liste der zulässigen IP-Adressen finden Sie unter [Azure IP Ranges and Service Tags-Public Cloud](https://www.microsoft.com/en-us/download/details.aspx?id=56519) .</span><span class="sxs-lookup"><span data-stu-id="42b10-176">See [Azure IP Ranges and Service Tags - Public Cloud](https://www.microsoft.com/en-us/download/details.aspx?id=56519) for a list of IP addresses to allow.</span></span>

### <a name="installation-is-complete-but-dont-see-tickets-and-cant-share"></a><span data-ttu-id="42b10-177">Die Installation ist abgeschlossen, es werden jedoch keine Tickets angezeigt und können nicht freigegeben werden</span><span class="sxs-lookup"><span data-stu-id="42b10-177">Installation is complete but don't see tickets and can't share</span></span>

<span data-ttu-id="42b10-178">Wenn die Installations-und Setupschritte abgeschlossen wurden, die ServiceNow-Karten jedoch nicht auf der Startseite angezeigt werden und nicht von Microsoft Secure Score an ServiceNow freigegeben werden können, überprüfen Sie den Status der Seite Bereitstellung unter https://security.microsoft.com/ticketProvisioning .</span><span class="sxs-lookup"><span data-stu-id="42b10-178">If the installation and setup steps have been completed, but you don't see the ServiceNow cards on the home page and can't share to ServiceNow from Microsoft Secure Score, check the status of the provisioning page at https://security.microsoft.com/ticketProvisioning.</span></span> <span data-ttu-id="42b10-179">Wählen Sie **autorisieren** und zur Startseite zurückkehren.</span><span class="sxs-lookup"><span data-stu-id="42b10-179">Select **Authorize** and return to the home page.</span></span> <span data-ttu-id="42b10-180">Die Karten sollten angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="42b10-180">The cards should appear.</span></span>

## <a name="resources"></a><span data-ttu-id="42b10-181">Ressourcen</span><span class="sxs-lookup"><span data-stu-id="42b10-181">Resources</span></span>

- [<span data-ttu-id="42b10-182">Verwalten von ServiceNow-Tickets im Sicherheitscenter</span><span class="sxs-lookup"><span data-stu-id="42b10-182">Manage ServiceNow tickets in the security center</span></span>](tickets-security-center.md)
