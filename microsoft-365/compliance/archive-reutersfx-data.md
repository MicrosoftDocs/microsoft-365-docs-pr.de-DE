---
title: Einrichten eines Connectors zum Archivieren von Reuters FX-Daten in Microsoft 365
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
description: Administratoren können einen Connector zum Importieren und Archivieren von Reuters FX-Daten von Globanet nach Microsoft 365 einrichten. Mit diesem Connector können Sie Daten aus Drittanbieter-Datenquellen in Microsoft 365 archivieren. Nach dem Archivieren dieser Daten können Sie Compliance-Features wie Legal Hold, Inhaltssuche und Aufbewahrungsrichtlinien zum Verwalten von drittanbieterdaten verwenden.
ms.openlocfilehash: ae2e36d2d51a22a8d2db1677634a7d66bde7c5c4
ms.sourcegitcommit: f07442d077eb4357fa5d99d051b035705eb30efa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/12/2020
ms.locfileid: "49002812"
---
# <a name="set-up-a-connector-to-archive-reuters-fx-data-preview"></a><span data-ttu-id="fb5c9-105">Einrichten eines Connectors zum Archivieren von Reuters FX Data (Vorschau)</span><span class="sxs-lookup"><span data-stu-id="fb5c9-105">Set up a connector to archive Reuters FX data (preview)</span></span>

<span data-ttu-id="fb5c9-106">Verwenden Sie einen Globanet-Connector im Microsoft 365 Compliance Center, um Daten aus der Reuters FX-Plattform in Benutzerpostfächer in Ihrer Microsoft 365-Organisation zu importieren und zu archivieren.</span><span class="sxs-lookup"><span data-stu-id="fb5c9-106">Use a Globanet connector in the Microsoft 365 compliance center to import and archive data from the Reuters FX platform to user mailboxes in your Microsoft 365 organization.</span></span> <span data-ttu-id="fb5c9-107">Globanet bietet Ihnen einen [Reuters FX](https://globanet.com/reuters-fx/) -Connector, der so konfiguriert ist, dass er Elemente aus der Drittanbieter-Datenquelle (regelmäßig) erfasst und diese Elemente dann nach Microsoft 365 importiert.</span><span class="sxs-lookup"><span data-stu-id="fb5c9-107">Globanet provides you with a [Reuters FX](https://globanet.com/reuters-fx/) connector that is configured to capture items from the third-party data source (on a regular basis) and then import those items to Microsoft 365.</span></span> <span data-ttu-id="fb5c9-108">Der Connector wandelt die Währungen und FX-Raten aus dem Reuters FX-Konto in ein e-Mail-Nachrichtenformat um und importiert diese Elemente dann in das Postfach des Benutzers in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="fb5c9-108">The connector converts the currencies and FX rates from the Reuters FX account to an email message format and then imports those items to the user's mailbox in Microsoft 365.</span></span>

<span data-ttu-id="fb5c9-109">Nachdem die Reuters FX-Daten in Benutzerpostfächern gespeichert wurden, können Sie Microsoft 365-Compliance-Features wie Beweissicherungsverfahren, eDiscovery, Aufbewahrungsrichtlinien und Aufbewahrungs Bezeichnungen sowie die Kompatibilität der Kommunikation anwenden.</span><span class="sxs-lookup"><span data-stu-id="fb5c9-109">After Reuters FX data is stored in user mailboxes, you can apply Microsoft 365 compliance features such as Litigation Hold, eDiscovery, retention policies and retention labels, and communication compliance.</span></span> <span data-ttu-id="fb5c9-110">Die Verwendung eines Reuters FX-Connectors zum Importieren und Archivieren von Daten in Microsoft 365 kann dazu beitragen, dass Ihre Organisation mit behördlichen und behördlichen Richtlinien konform bleibt.</span><span class="sxs-lookup"><span data-stu-id="fb5c9-110">Using a Reuters FX connector to import and archive data in Microsoft 365 can help your organization stay compliant with government and regulatory policies.</span></span>

## <a name="overview-of-archiving-reuters-fx-data"></a><span data-ttu-id="fb5c9-111">Übersicht über die Archivierung von Reuters FX-Daten</span><span class="sxs-lookup"><span data-stu-id="fb5c9-111">Overview of archiving Reuters FX data</span></span>

<span data-ttu-id="fb5c9-112">In der folgenden Übersicht wird der Vorgang der Verwendung eines Connectors zum Archivieren von Reuters FX-Daten in Microsoft 365 erläutert.</span><span class="sxs-lookup"><span data-stu-id="fb5c9-112">The following overview explains the process of using a connector to archive Reuters FX data in Microsoft 365.</span></span>

![Archivierungs Workflow für Reuters FX-Daten](../media/ReutersFXConnectorWorkflow.png)

1. <span data-ttu-id="fb5c9-114">Ihre Organisation arbeitet mit Reuters FX zusammen, um eine Reuters FX-Website einzurichten und zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="fb5c9-114">Your organization works with Reuters FX to set up and configure a Reuters FX site.</span></span>

2. <span data-ttu-id="fb5c9-115">Alle 24 Stunden werden Reuters FX-Elemente auf die Globanet Merge1-Website kopiert.</span><span class="sxs-lookup"><span data-stu-id="fb5c9-115">Once every 24 hours, Reuters FX items are copied to the Globanet Merge1 site.</span></span> <span data-ttu-id="fb5c9-116">Der Connector wandelt die Elemente auch in ein e-Mail-Nachrichtenformat um.</span><span class="sxs-lookup"><span data-stu-id="fb5c9-116">The connector also converts the items to an email message format.</span></span>

3. <span data-ttu-id="fb5c9-117">Der Reuters FX Connector, den Sie im Microsoft 365 Compliance Center erstellen, stellt jeden Tag eine Verbindung mit der Globanet Merge1-Website her und überträgt die Inhalte an einen sicheren Azure-Speicherort in der Microsoft-Cloud.</span><span class="sxs-lookup"><span data-stu-id="fb5c9-117">The Reuters FX connector that you create in the Microsoft 365 compliance center, connects to the Globanet Merge1 site every day and transfers the content to a secure Azure Storage location in the Microsoft cloud.</span></span>

4. <span data-ttu-id="fb5c9-118">Der Connector importiert die Elemente in die Postfächer bestimmter Benutzer, wobei der Wert der *Email* -Eigenschaft der automatischen Benutzerzuordnung wie in [Schritt 3](#step-3-map-users-and-complete-the-connector-setup)beschrieben wird.</span><span class="sxs-lookup"><span data-stu-id="fb5c9-118">The connector imports the items to the mailboxes of specific users using the value of the *Email* property of the automatic user mapping as described in [Step 3](#step-3-map-users-and-complete-the-connector-setup).</span></span> <span data-ttu-id="fb5c9-119">Ein Unterordner im Ordner "Posteingang" **Reuters FX** wird in den Benutzerpostfächern erstellt, und die Elemente werden in diesen Ordner importiert.</span><span class="sxs-lookup"><span data-stu-id="fb5c9-119">A subfolder in the Inbox folder named **Reuters FX** is created in the user mailboxes, and the items are imported to that folder.</span></span> <span data-ttu-id="fb5c9-120">Der Connector bestimmt anhand des Werts der *Email* -Eigenschaft, in welches Postfach Elemente importiert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="fb5c9-120">The connector determines which mailbox to import items to by using the value of the *Email* property.</span></span> <span data-ttu-id="fb5c9-121">Jedes Reuters FX-Element enthält diese Eigenschaft, die mit der e-Mail-Adresse jedes Teilnehmers des Elements aufgefüllt wird.</span><span class="sxs-lookup"><span data-stu-id="fb5c9-121">Every Reuters FX item contains this property, which is populated with the email address of every participant of the item.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="fb5c9-122">Bevor Sie beginnen</span><span class="sxs-lookup"><span data-stu-id="fb5c9-122">Before you begin</span></span>

- <span data-ttu-id="fb5c9-123">Erstellen Sie ein Globanet-Merge1-Konto für Microsoft-Connectors.</span><span class="sxs-lookup"><span data-stu-id="fb5c9-123">Create a Globanet Merge1 account for Microsoft connectors.</span></span> <span data-ttu-id="fb5c9-124">Um ein Konto zu erstellen, wenden Sie sich an den [Globanet-Kunden Support](https://globanet.com/contact-us).</span><span class="sxs-lookup"><span data-stu-id="fb5c9-124">To create an account, contact [Globanet Customer Support](https://globanet.com/contact-us).</span></span> <span data-ttu-id="fb5c9-125">Sie müssen sich bei diesem Konto anmelden, wenn Sie den Connector in Schritt 1 erstellen.</span><span class="sxs-lookup"><span data-stu-id="fb5c9-125">You need to sign into this account when you create the connector in Step 1.</span></span>

- <span data-ttu-id="fb5c9-126">Der Benutzer, der den Reuters FX-Connector in Schritt 1 erstellt (und diesen in Schritt 3 vervollständigt) muss der Rolle "Post Fach Import Export" in Exchange Online zugewiesen sein.</span><span class="sxs-lookup"><span data-stu-id="fb5c9-126">The user who creates the Reuters FX connector in Step 1 (and completes it in Step 3) must be assigned to the Mailbox Import Export role in Exchange Online.</span></span> <span data-ttu-id="fb5c9-127">Diese Rolle ist für das Hinzufügen von Connectors auf der Seite **Daten Konnektoren** im Microsoft 365 Compliance Center erforderlich.</span><span class="sxs-lookup"><span data-stu-id="fb5c9-127">This role is required to add connectors on the **Data connectors** page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="fb5c9-128">Diese Rolle ist in Exchange Online standardmäßig keiner Rollengruppe zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="fb5c9-128">By default, this role is not assigned to any role group in Exchange Online.</span></span> <span data-ttu-id="fb5c9-129">Sie können die Rolle "Post Fach Import exportieren" der Rollengruppe "Organisationsverwaltung" in Exchange Online hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="fb5c9-129">You can add the Mailbox Import Export role to the Organization Management role group in Exchange Online.</span></span> <span data-ttu-id="fb5c9-130">Sie können auch eine Rollengruppe erstellen, die Rolle "Post Fach Import Export" zuweisen und dann die entsprechenden Benutzer als Mitglieder hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="fb5c9-130">Or you can create a role group, assign the Mailbox Import Export role, and then add the appropriate users as members.</span></span> <span data-ttu-id="fb5c9-131">Weitere Informationen finden Sie im Abschnitt [Erstellen](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) von Rollengruppen oder [Ändern von Rollengruppen](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) im Artikel "Verwalten von Rollengruppen in Exchange Online".</span><span class="sxs-lookup"><span data-stu-id="fb5c9-131">For more information, see the [Create role groups](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) or [Modify role groups](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) sections in the article “Manage role groups in Exchange Online”.</span></span>

## <a name="step-1-set-up-the-reuters-fx-connector"></a><span data-ttu-id="fb5c9-132">Schritt 1: Einrichten des Reuters FX-Connectors</span><span class="sxs-lookup"><span data-stu-id="fb5c9-132">Step 1: Set up the Reuters FX connector</span></span>

<span data-ttu-id="fb5c9-133">Der erste Schritt besteht darin, auf die Seite " **Daten Konnektoren** " in Microsoft 365 zuzugreifen und einen Connector für Reuters FX-Daten zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="fb5c9-133">The first step is to access to the **Data Connectors** page in the Microsoft 365 and create a connector for Reuters FX data.</span></span>

1. <span data-ttu-id="fb5c9-134">Wechseln Sie zu, [https://compliance.microsoft.com](https://compliance.microsoft.com/) und klicken Sie dann auf **Data Connectors**  >  **Reuters FX**.</span><span class="sxs-lookup"><span data-stu-id="fb5c9-134">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com/) and then click **Data connectors** > **Reuters FX**.</span></span>

2. <span data-ttu-id="fb5c9-135">Klicken Sie auf der Seite **Reuters FX** -Produktbeschreibung auf **Connector hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="fb5c9-135">On the **Reuters FX** product description page, click **Add connector**.</span></span>

3. <span data-ttu-id="fb5c9-136">Klicken Sie auf der Seite **Nutzungsbedingungen** auf **annehmen**.</span><span class="sxs-lookup"><span data-stu-id="fb5c9-136">On the **Terms of service** page, click **Accept**.</span></span>

4. <span data-ttu-id="fb5c9-137">Geben Sie einen eindeutigen Namen ein, der den Connector identifiziert, und klicken Sie dann auf **weiter**.</span><span class="sxs-lookup"><span data-stu-id="fb5c9-137">Enter a unique name that identifies the connector, and then click **Next**.</span></span>

5. <span data-ttu-id="fb5c9-138">Melden Sie sich bei Ihrem Merge1-Konto an, um den Connector zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="fb5c9-138">Sign to your Merge1 account to configure the connector.</span></span>

## <a name="step-2-configure-the-reuters-fx-connector-on-the-globanet-merge1-site"></a><span data-ttu-id="fb5c9-139">Schritt 2: Konfigurieren des Reuters FX-Konnektors auf der Globanet Merge1-Website</span><span class="sxs-lookup"><span data-stu-id="fb5c9-139">Step 2: Configure the Reuters FX connector on the Globanet Merge1 site</span></span>

<span data-ttu-id="fb5c9-140">Der zweite Schritt besteht darin, den Reuters FX-Connector auf der Globanet Merge1-Website zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="fb5c9-140">The second step is to configure the Reuters FX connector on the Globanet Merge1 site.</span></span> <span data-ttu-id="fb5c9-141">Informationen zum Konfigurieren des Reuters FX-Connectors finden Sie unter [Merge1 Third-Party Connectors User Guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Reuters%20FX%20User%20Guide%20.pdf).</span><span class="sxs-lookup"><span data-stu-id="fb5c9-141">For information about configuring the Reuters FX connector, see [Merge1 Third-Party Connectors User Guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Reuters%20FX%20User%20Guide%20.pdf).</span></span>

<span data-ttu-id="fb5c9-142">Nachdem Sie auf **& Ende speichern** klicken, wird die Seite **Benutzerzuordnung** im Connector-Assistenten im Microsoft 365 Compliance Center angezeigt.</span><span class="sxs-lookup"><span data-stu-id="fb5c9-142">After you click **Save & Finish** , the **User mapping** page in the connector wizard in the Microsoft 365 compliance center is displayed.</span></span>

## <a name="step-3-map-users-and-complete-the-connector-setup"></a><span data-ttu-id="fb5c9-143">Schritt 3: Zuordnen von Benutzern und Abschließen des Connector-Setups</span><span class="sxs-lookup"><span data-stu-id="fb5c9-143">Step 3: Map users and complete the connector setup</span></span>

<span data-ttu-id="fb5c9-144">Führen Sie die folgenden Schritte aus, um Benutzer zuzuordnen und das Connector-Setup im Microsoft 365 Compliance Center abzuschließen:</span><span class="sxs-lookup"><span data-stu-id="fb5c9-144">To map users and complete the connector setup in the Microsoft 365 compliance center, follow the steps below:</span></span>

1. <span data-ttu-id="fb5c9-145">Aktivieren Sie auf der Seite **Reuters FX-Benutzer auf Microsoft 365-Benutzer** zuordnen die Option Automatische Benutzerzuordnung.</span><span class="sxs-lookup"><span data-stu-id="fb5c9-145">On the **Map Reuters FX users to Microsoft 365 users** page, enable automatic user mapping.</span></span>

   <span data-ttu-id="fb5c9-146">Reuters FX-Elemente enthalten eine Eigenschaft mit dem Namen " *e-Mail* ", die e-Mail-Adressen für Benutzer in Ihrer Organisation enthält.</span><span class="sxs-lookup"><span data-stu-id="fb5c9-146">Reuters FX items include a property called *Email* , which contains email addresses for users in your organization.</span></span> <span data-ttu-id="fb5c9-147">Wenn der Connector diese Adresse einem Microsoft 365-Benutzer zuordnen kann, werden die Elemente in das Postfach dieses Benutzers importiert.</span><span class="sxs-lookup"><span data-stu-id="fb5c9-147">If the connector can associate this address with a Microsoft 365 user, the items are imported to that user’s mailbox.</span></span>

2. <span data-ttu-id="fb5c9-148">Klicken Sie auf der Seite **Administrator Zustimmung** auf die Schaltfläche **Zustimmung erteilen** .</span><span class="sxs-lookup"><span data-stu-id="fb5c9-148">On the **Admin Consent** page, click the **Provide Consent** button.</span></span> <span data-ttu-id="fb5c9-149">Sie werden zur Microsoft-Website umgeleitet.</span><span class="sxs-lookup"><span data-stu-id="fb5c9-149">You will be redirected to the Microsoft site.</span></span> <span data-ttu-id="fb5c9-150">Klicken Sie auf **akzeptieren** , um die Zustimmung zu erteilen.</span><span class="sxs-lookup"><span data-stu-id="fb5c9-150">Click **Accept** to provide the consent.</span></span>

    <span data-ttu-id="fb5c9-151">Ihre Organisation muss einwilligen, dass der Office 365 Import Dienst auf Postfachdaten in Ihrer Organisation zugreifen kann.</span><span class="sxs-lookup"><span data-stu-id="fb5c9-151">Your organization must consent to allow the Office 365 Import service to access mailbox data in your organization.</span></span> <span data-ttu-id="fb5c9-152">Um die Zustimmung des Administrators bereitzustellen, müssen Sie mit den Anmeldeinformationen eines globalen Administrators von Microsoft 365 angemeldet sein und dann die Zustimmungs Anforderung annehmen.</span><span class="sxs-lookup"><span data-stu-id="fb5c9-152">To provide admin consent, you must be signed in with the credentials of a Microsoft 365 global admin, and then accept the consent request.</span></span> <span data-ttu-id="fb5c9-153">Wenn Sie nicht als globaler Administrator angemeldet sind, können Sie zu [dieser Seite](https://login.microsoftonline.com/common/oauth2/authorize?client_id=570d0bec-d001-4c4e-985e-3ab17fdc3073&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent) wechseln und sich mit globalen Administratoranmeldeinformationen anmelden, um die Anforderung zu akzeptieren.</span><span class="sxs-lookup"><span data-stu-id="fb5c9-153">If you aren't signed in as a global admin, you can go to [this page](https://login.microsoftonline.com/common/oauth2/authorize?client_id=570d0bec-d001-4c4e-985e-3ab17fdc3073&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent) and sign in using global admin credentials to accept the request.</span></span>

3. <span data-ttu-id="fb5c9-154">Klicken Sie auf **weiter** , überprüfen Sie Ihre Einstellungen, und wechseln Sie zur Seite **Daten Konnektoren** , um den Fortschritt des Importvorgangs für den neuen Connector anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="fb5c9-154">Click **Next** , review your settings, and go to the **Data connectors** page to see the progress of the import process for the new connector.</span></span>

## <a name="step-4-monitor-the-reuters-fx-connector"></a><span data-ttu-id="fb5c9-155">Schritt 4: Überwachen des Reuters FX-Connectors</span><span class="sxs-lookup"><span data-stu-id="fb5c9-155">Step 4: Monitor the Reuters FX connector</span></span>

<span data-ttu-id="fb5c9-156">Nachdem Sie den Reuters FX-Connector erstellt haben, können Sie den Connectorstatus im Microsoft 365 Compliance Center anzeigen.</span><span class="sxs-lookup"><span data-stu-id="fb5c9-156">After you create the Reuters FX connector, you can view the connector status in the Microsoft 365 compliance center.</span></span>

1. <span data-ttu-id="fb5c9-157">Wechseln Sie zu, <https://compliance.microsoft.com/> und klicken Sie im linken Navigationsbereich auf **Daten-Konnektoren** .</span><span class="sxs-lookup"><span data-stu-id="fb5c9-157">Go to <https://compliance.microsoft.com/> and click **Data connectors** in the left nav.</span></span>

2. <span data-ttu-id="fb5c9-158">Klicken Sie auf die Registerkarte **Connectors** , und wählen Sie dann den **Reuters FX** -Connector aus, um die Flyout-Seite anzuzeigen, die die Eigenschaften und Informationen zum Connector enthält.</span><span class="sxs-lookup"><span data-stu-id="fb5c9-158">Click the **Connectors** tab and then select the **Reuters FX** connector to display the flyout page, which contains the properties and information about the connector.</span></span>

3. <span data-ttu-id="fb5c9-159">Klicken Sie unter **Connectorstatus with Source** auf den Link **Download Protokoll** , um das Statusprotokoll für den Connector zu öffnen (oder zu speichern).</span><span class="sxs-lookup"><span data-stu-id="fb5c9-159">Under **Connector status with source** , click the **Download log** link to open (or save) the status log for the connector.</span></span> <span data-ttu-id="fb5c9-160">Dieses Protokoll enthält Daten, die in die Microsoft-Cloud importiert wurden.</span><span class="sxs-lookup"><span data-stu-id="fb5c9-160">This log contains data that has been imported to the Microsoft cloud.</span></span>

## <a name="known-issues"></a><span data-ttu-id="fb5c9-161">Bekannte Probleme</span><span class="sxs-lookup"><span data-stu-id="fb5c9-161">Known issues</span></span>

- <span data-ttu-id="fb5c9-162">Zurzeit wird das Importieren von Anlagen oder Elementen, die größer als 10 MB sind, nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="fb5c9-162">At this time, we don't support importing attachments or items that are larger than 10 MB.</span></span> <span data-ttu-id="fb5c9-163">Unterstützung für größere Elemente wird zu einem späteren Zeitpunkt zur Verfügung stehen.</span><span class="sxs-lookup"><span data-stu-id="fb5c9-163">Support for larger items will be available at a later date.</span></span>