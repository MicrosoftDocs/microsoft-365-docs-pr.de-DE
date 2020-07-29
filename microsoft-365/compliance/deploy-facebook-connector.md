---
title: Bereitstellen eines Connectors zum Archivieren von Facebook-Geschäfts Seiten Daten
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
search.appverid:
- MET150
ms.collection: M365-security-compliance
ROBOTS: NOINDEX, NOFOLLOW
description: Administratoren können einen systemeigenen Connector einrichten, um Facebook-Geschäfts Seiten in Microsoft 365 zu importieren und zu archivieren. Nachdem diese Daten in Microsoft 365 importiert wurden, können Sie Compliance-Features wie Legal Hold, Inhaltssuche und Aufbewahrungsrichtlinien verwenden, um die Steuerung der Facebook-Daten Ihrer Organisation zu verwalten.
ms.openlocfilehash: 240ce3a90cf46a05ab5d6030b9318d42d23904d8
ms.sourcegitcommit: 50526f81ce3f57d58f0a7c0df4fe21685c5a0236
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/28/2020
ms.locfileid: "45434235"
---
# <a name="deploy-a-connector-to-archive-facebook-business-pages-data"></a><span data-ttu-id="1a5ef-104">Bereitstellen eines Connectors zum Archivieren von Facebook-Geschäfts Seiten Daten</span><span class="sxs-lookup"><span data-stu-id="1a5ef-104">Deploy a connector to archive Facebook Business pages data</span></span>

<span data-ttu-id="1a5ef-105">Dieser Artikel enthält den schrittweisen Prozess zur Bereitstellungeines Connectors, der den Office 365-Import Dienst verwendet, um Daten von Facebook-Geschäfts Seiten nach Microsoft 365 zu importieren.</span><span class="sxs-lookup"><span data-stu-id="1a5ef-105">This article contains the step-by-step process to deploy a connector that uses the Office 365 Import service to import data from Facebook Business pages to Microsoft 365.</span></span> <span data-ttu-id="1a5ef-106">Eine allgemeine Übersicht über diesen Prozess und eine Liste der Voraussetzungen, die für die Bereitstellungeines Facebook-Konnektors erforderlich sind, finden Sie unter [Einrichten eines Connectors zum Archivieren von Facebook-Daten](archive-facebook-data-with-sample-connector.md).</span><span class="sxs-lookup"><span data-stu-id="1a5ef-106">For a high-level overview of this process and a list of prerequisites required to deploy a Facebook connector, see [Set up a connector to archive Facebook data](archive-facebook-data-with-sample-connector.md).</span></span>

## <a name="step-1-create-an-app-in-azure-active-directory"></a><span data-ttu-id="1a5ef-107">Schritt 1: Erstellen einer APP in Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="1a5ef-107">Step 1: Create an app in Azure Active Directory</span></span>

1. <span data-ttu-id="1a5ef-108">Wechseln Sie zu, <https://portal.azure.com> und melden Sie sich mit den Anmeldeinformationen eines globalen Administratorkontos an.</span><span class="sxs-lookup"><span data-stu-id="1a5ef-108">Go to <https://portal.azure.com> and sign in using the credentials of a global admin account.</span></span>

    ![Erstellen einer APP in Aad](../media/FBCimage1.png)

2. <span data-ttu-id="1a5ef-110">Klicken Sie im linken Navigationsbereich auf **Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="1a5ef-110">In the left navigation pane, click **Azure Active Directory**.</span></span>

    ![Klicken Sie auf Azure Active Directory](../media/FBCimage2.png)

3. <span data-ttu-id="1a5ef-112">Klicken Sie im linken Navigationsbereich auf **App-Registrierungen (Vorschau)** , und klicken Sie dann auf **neue Registrierung**.</span><span class="sxs-lookup"><span data-stu-id="1a5ef-112">In the left navigation pane, click **App registrations (Preview)** and then click **New registration**.</span></span>

    ![Klicken Sie auf \* \* App-Registrierungen (Vorschau) \* \* und dann auf \* \* neue Registrierung \* \*](../media/FBCimage3.png)

4. <span data-ttu-id="1a5ef-114">Registrieren Sie die Anwendung.</span><span class="sxs-lookup"><span data-stu-id="1a5ef-114">Register the application.</span></span> <span data-ttu-id="1a5ef-115">Wählen Sie unter Umleitungs-URI die Option Webin der Dropdownliste Anwendungstyp aus, und geben Sie dann <https://portal.azure.com> in das Feld für den URI ein.</span><span class="sxs-lookup"><span data-stu-id="1a5ef-115">Under Redirect URI, select Web in the application type dropdown list and then type <https://portal.azure.com> in the box for the URI.</span></span>

   ![Registrieren der App](../media/FBCimage4.png)

5. <span data-ttu-id="1a5ef-117">Kopieren Sie die Anwendungs-ID **(Client) ID** und **Verzeichnis (Mandanten)** , und speichern Sie Sie in einer Textdatei oder an einem anderen sicheren Ort.</span><span class="sxs-lookup"><span data-stu-id="1a5ef-117">Copy the **Application (client) ID** and **Directory (tenant) ID** and save them to a text file or other safe location.</span></span> <span data-ttu-id="1a5ef-118">Sie verwenden diese IDs in späteren Schritten.</span><span class="sxs-lookup"><span data-stu-id="1a5ef-118">You use these IDs in later steps.</span></span>

   ![Kopieren Sie die Anwendungs-ID und die Verzeichnis-ID, und speichern Sie Sie.](../media/FBCimage5.png)

6. <span data-ttu-id="1a5ef-120">Wechseln Sie zu **Zertifikaten & Geheimnisse für die neue APP.**</span><span class="sxs-lookup"><span data-stu-id="1a5ef-120">Go to **Certificates & secrets for the new app.**</span></span>

   ![Wechseln Sie zu Zertifikaten & Geheimnisse für die neue APP.](../media/FBCimage6.png)

7. <span data-ttu-id="1a5ef-122">Klicken Sie auf **neuer geheimer Client Schlüssel**</span><span class="sxs-lookup"><span data-stu-id="1a5ef-122">Click **New client secret**</span></span>

   ![Klicken Sie auf neuer geheimer Client Schlüssel](../media/FBCimage7.png)

8. <span data-ttu-id="1a5ef-124">Erstellen Sie einen neuen geheimen Schlüssel.</span><span class="sxs-lookup"><span data-stu-id="1a5ef-124">Create a new secret.</span></span> <span data-ttu-id="1a5ef-125">Geben Sie im Feld Beschreibung den geheimen Schlüssel ein, und wählen Sie dann einen Ablaufzeitraum aus.</span><span class="sxs-lookup"><span data-stu-id="1a5ef-125">In the description box, type the secret and then choose an expiration period.</span></span>

    ![Geben Sie den geheimen Schlüssel ein, und wählen Sie dann einen Ablaufzeitraum](../media/FBCimage8.png)

9. <span data-ttu-id="1a5ef-127">Kopieren Sie den Wert des geheimen Schlüssels, und speichern Sie ihn in einer Textdatei oder an einem anderen Speicherort.</span><span class="sxs-lookup"><span data-stu-id="1a5ef-127">Copy the value of the secret and save it to a text file or other storage location.</span></span> <span data-ttu-id="1a5ef-128">Dies ist der geheime Aad-Anwendungsschlüssel, den Sie in späteren Schritten verwenden.</span><span class="sxs-lookup"><span data-stu-id="1a5ef-128">This is the AAD application secret that you use in later steps.</span></span>

   ![Kopieren Sie den Wert des geheimen Schlüssels, und speichern Sie ihn.](../media/FBCimage9.png)

## <a name="step-2-deploy-the-connector-web-service-from-github-to-your-azure-account"></a><span data-ttu-id="1a5ef-130">Schritt 2: Bereitstellen des Connector-Webdiensts von GitHub in Ihrem Azure-Konto</span><span class="sxs-lookup"><span data-stu-id="1a5ef-130">Step 2: Deploy the connector web service from GitHub to your Azure account</span></span>

1. <span data-ttu-id="1a5ef-131">Wechseln Sie zu [dieser GitHub-Website](https://github.com/microsoft/m365-sample-connector-csharp-aspnet) , und klicken Sie auf **in Azure bereitstellen**.</span><span class="sxs-lookup"><span data-stu-id="1a5ef-131">Go to [this GitHub site](https://github.com/microsoft/m365-sample-connector-csharp-aspnet) and click **Deploy to Azure**.</span></span>

    ![Klicken Sie auf in Azure bereitstellen](../media/FBCGithubApp.png)

2. <span data-ttu-id="1a5ef-133">Nachdem Sie auf **in Azure bereitstellen**klicken, werden Sie zu einem Azure-Portal mit einer benutzerdefinierten Vorlagenseite umgeleitet.</span><span class="sxs-lookup"><span data-stu-id="1a5ef-133">After you click **Deploy to Azure**, you will be redirected to an Azure portal with a custom template page.</span></span> <span data-ttu-id="1a5ef-134">Füllen Sie die Details **Grundlagen** und **Einstellungen** aus, und klicken Sie dann auf **kaufen**.</span><span class="sxs-lookup"><span data-stu-id="1a5ef-134">Fill in the **Basics** and **Settings** details and then click **Purchase**.</span></span>

   - <span data-ttu-id="1a5ef-135">**Abonnement:** Wählen Sie Ihr Azure-Abonnement aus, für das Sie den Facebook Business Pages-Connector-Webdienst bereitstellen möchten.</span><span class="sxs-lookup"><span data-stu-id="1a5ef-135">**Subscription:** Select your Azure subscription that you want to deploy the Facebook Business pages connector web service to.</span></span>

   - <span data-ttu-id="1a5ef-136">**Ressourcengruppe:** Wählen oder erstellen Sie eine neue Ressourcengruppe.</span><span class="sxs-lookup"><span data-stu-id="1a5ef-136">**Resource group:** Choose or create a new resource group.</span></span> <span data-ttu-id="1a5ef-137">Eine Ressourcengruppe ist ein Container, der verwandte Ressourcen für eine Azure-Lösung bereit hält.</span><span class="sxs-lookup"><span data-stu-id="1a5ef-137">A resource group is a container that holds related resources for an Azure solution.</span></span>

   - <span data-ttu-id="1a5ef-138">**Speicherort:** Wählen Sie einen Speicherort aus.</span><span class="sxs-lookup"><span data-stu-id="1a5ef-138">**Location:** Choose a location.</span></span>

   - <span data-ttu-id="1a5ef-139">**Name der Webanwendung:** Geben Sie einen eindeutigen Namen für die Connector-Webanwendung an.</span><span class="sxs-lookup"><span data-stu-id="1a5ef-139">**Web App Name:** Provide a unique name for the connector web app.</span></span> <span data-ttu-id="1a5ef-140">Th Name muss zwischen 3 und 18 Zeichen lang sein.</span><span class="sxs-lookup"><span data-stu-id="1a5ef-140">Th name must be between 3 and 18 characters in length.</span></span> <span data-ttu-id="1a5ef-141">Dieser Name wird zum Erstellen der Azure-App-Dienst-URL verwendet. Wenn Sie beispielsweise den Namen der Webanwendung von **FBconnector** angeben, wird die Azure-App-Dienst-URL **FBconnector.azurewebsites.net**.</span><span class="sxs-lookup"><span data-stu-id="1a5ef-141">This name is used to create the Azure app service URL; for example, if you provide the Web app name of **fbconnector** then the Azure app service URL  will be **fbconnector.azurewebsites.net**.</span></span>

   - <span data-ttu-id="1a5ef-142">**Mandanten** -Nr: Die Mandanten-ID Ihrer Microsoft 365-Organisation, die Sie nach dem Erstellen der Facebook-Connector-app in Azure Active Directory in Schritt 1 kopiert haben.</span><span class="sxs-lookup"><span data-stu-id="1a5ef-142">**tenantId:** The tenant ID of your Microsoft 365 organization that you copied after creating the Facebook connector app in Azure Active Directory in Step 1.</span></span>

   - <span data-ttu-id="1a5ef-143">**APISecretKey:** Sie können einen beliebigen Wert als geheimen Schlüssel eingeben.</span><span class="sxs-lookup"><span data-stu-id="1a5ef-143">**APISecretKey:** You can type any value as the secret.</span></span> <span data-ttu-id="1a5ef-144">Dies wird verwendet, um in Schritt 5 auf die Connector-Webanwendung zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="1a5ef-144">This is used to access the connector web app in Step 5.</span></span>

     ![Klicken Sie auf Ressource erstellen, und geben Sie Speicherkonto ein.](../media/FBCimage12.png)

3. <span data-ttu-id="1a5ef-146">Nachdem die Bereitstellung erfolgreich war, sieht die Seite ähnlich wie der folgende Screenshot aus:</span><span class="sxs-lookup"><span data-stu-id="1a5ef-146">After the deployment is successful, the page will look similar to the following screenshot:</span></span>

   ![Klicken Sie auf Speicher, und klicken Sie dann auf Speicherkonto](../media/FBCimage13.png)

## <a name="step-3-register-the-facebook-app"></a><span data-ttu-id="1a5ef-148">Schritt 3: Registrieren der Facebook-App</span><span class="sxs-lookup"><span data-stu-id="1a5ef-148">Step 3: Register the Facebook app</span></span>

1. <span data-ttu-id="1a5ef-149">Wechseln <https://developers.facebook.com> Sie zu, melden Sie sich mit den Anmeldeinformationen für das Konto für die Facebook-Geschäfts Seiten Ihrer Organisation an, und klicken Sie dann auf **neue APP hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="1a5ef-149">Go to <https://developers.facebook.com>, log in using the credentials for the account for your organization's Facebook Business pages, and then click **Add New App**.</span></span>

   ![Hinzufügen einer neuen App für Facebook-Geschäftsseite](../media/FBCimage25.png)

2. <span data-ttu-id="1a5ef-151">Erstellen Sie eine neue APP-ID.</span><span class="sxs-lookup"><span data-stu-id="1a5ef-151">Create a new app ID.</span></span>

   ![Erstellen einer neuen APP-ID](../media/FBCimage26.png)

3. <span data-ttu-id="1a5ef-153">Klicken Sie im linken Navigationsbereich auf **Produkte hinzufügen** , und klicken Sie dann auf der **Facebook-Anmelde** Kachel auf **Einrichten** .</span><span class="sxs-lookup"><span data-stu-id="1a5ef-153">In the left navigation pane, click **Add Products** and then click **Set Up** in the **Facebook Login** tile.</span></span>

   ![Klicken Sie auf Produkte hinzufügen.](../media/FBCimage27.png)

4. <span data-ttu-id="1a5ef-155">Klicken Sie auf der Seite Facebook-Anmeldung einbinden auf **Website**.</span><span class="sxs-lookup"><span data-stu-id="1a5ef-155">On the Integrate Facebook Login page, click **Web**.</span></span>

   ![Klicken Sie auf der Seite Facebook-Anmeldung integrieren auf Website.](../media/FBCimage28.png)

5. <span data-ttu-id="1a5ef-157">Hinzufügen der Azure-App-Dienst-URL zum Beispiel `https://fbconnector.azurewebsites.net` .</span><span class="sxs-lookup"><span data-stu-id="1a5ef-157">Add the Azure app service URL; for example `https://fbconnector.azurewebsites.net`.</span></span>

   ![Hinzufügen der Azure-App-Dienst-URL](../media/FBCimage29.png)

6. <span data-ttu-id="1a5ef-159">Schließen Sie den Abschnitt Quick Start im Facebook-Anmelde Setup ab.</span><span class="sxs-lookup"><span data-stu-id="1a5ef-159">Complete the QuickStart section of the Facebook Login setup.</span></span>

   ![Abschließen des Schnellstart-Abschnitts](../media/FBCimage30.png)

7. <span data-ttu-id="1a5ef-161">Klicken Sie im linken Navigationsbereich unter **Facebook-Anmeldung**auf **Einstellungen**, und fügen Sie den OAuth-Umleitungs-URI im Feld **gültige OAuth-Umleitungs-URIs** hinzu.</span><span class="sxs-lookup"><span data-stu-id="1a5ef-161">In the left navigation pane under **Facebook Login**, click **Settings**, and add the OAuth redirect URI in the **Valid OAuth Redirect URIs** box.</span></span> <span data-ttu-id="1a5ef-162">Verwenden Sie das Format \*\* \<connectorserviceuri> /views/FacebookOAuth\*\*, wobei der Wert für connectorserviceuri die Azure-App-Dienst-URL für Ihre Organisation ist, beispielsweise `https://fbconnector.azurewebsites.net` .</span><span class="sxs-lookup"><span data-stu-id="1a5ef-162">Use the format **\<connectorserviceuri>/Views/FacebookOAuth**, where the value for connectorserviceuri is the Azure app service URL for your organization; for example, `https://fbconnector.azurewebsites.net`.</span></span>

   ![Fügen Sie den OAuth-Umleitungs-URI zum Feld gültige OAuth-Umleitungs-URIs hinzu](../media/FBCimage31.png)

8. <span data-ttu-id="1a5ef-164">Klicken Sie im linken Navigationsbereich auf **Produkte hinzufügen** , und klicken Sie dann auf **webhooks.**</span><span class="sxs-lookup"><span data-stu-id="1a5ef-164">In the left navigation pane, click **Add Products** and then click **Webhooks.**</span></span> <span data-ttu-id="1a5ef-165">Klicken Sie im Pulldown-Menü **Seite** auf **Seite**.</span><span class="sxs-lookup"><span data-stu-id="1a5ef-165">In the **Page** pull-down menu, click **Page**.</span></span>

   ![Klicken Sie auf Produkte hinzufügen, und klicken Sie dann auf \* \* webhooks.](../media/FBCimage32.png)

9. <span data-ttu-id="1a5ef-167">Fügen Sie die webhooks-Rückruf-URL hinzu, und fügen Sie ein Verify-Token hinzu.</span><span class="sxs-lookup"><span data-stu-id="1a5ef-167">Add Webhooks Callback URL and add a verify token.</span></span> <span data-ttu-id="1a5ef-168">Das Format der Rückruf-URL, verwenden Sie das Format \*\* <connectorserviceuri> /API/FbPageWebhook\*\*, wobei der Wert für connectorserviceuri die Azure-App-Dienst-URL für Ihre Organisation ist, zum Beispiel `https://fbconnector.azurewebsites.net` .</span><span class="sxs-lookup"><span data-stu-id="1a5ef-168">The format of the callback URL, use the format **<connectorserviceuri>/api/FbPageWebhook**, where the value for connectorserviceuri is the Azure app service URL for your organization; for example `https://fbconnector.azurewebsites.net`.</span></span>

   <span data-ttu-id="1a5ef-169">Das Verify-Token sollte einem starken Kennwort ähneln.</span><span class="sxs-lookup"><span data-stu-id="1a5ef-169">The verify token should similar to a strong password.</span></span> <span data-ttu-id="1a5ef-170">Kopieren Sie das Verify-Token in eine Textdatei oder einen anderen Speicherort.</span><span class="sxs-lookup"><span data-stu-id="1a5ef-170">Copy the verify token to a text file or other storage location.</span></span>

   ![Hinzufügen des Überprüfungs Tokens](../media/FBCimage33.png)

10. <span data-ttu-id="1a5ef-172">Testen und Abonnieren des Endpunkts für Feeds.</span><span class="sxs-lookup"><span data-stu-id="1a5ef-172">Test and subscribe to the endpoint for feed.</span></span>

    ![Testen und Abonnieren des Endpunkts](../media/FBCimage34.png)

11. <span data-ttu-id="1a5ef-174">Fügen Sie eine Datenschutz-URL, ein App-Symbol und eine geschäftliche Verwendung hinzu.</span><span class="sxs-lookup"><span data-stu-id="1a5ef-174">Add a privacy URL, app icon, and business use.</span></span> <span data-ttu-id="1a5ef-175">Kopieren Sie außerdem die APP-ID und den App-Schlüssel in eine Textdatei oder einen anderen Speicherort.</span><span class="sxs-lookup"><span data-stu-id="1a5ef-175">Also, copy the app ID and app secret to a text file or other storage location.</span></span>

    ![Hinzufügen einer Datenschutz-URL, eines App-Symbols und einer geschäftlichen Verwendung](../media/FBCimage35.png)

12. <span data-ttu-id="1a5ef-177">Machen Sie die APP öffentlich.</span><span class="sxs-lookup"><span data-stu-id="1a5ef-177">Make the app public.</span></span>

    ![Veröffentlichen der APP](../media/FBCimage36.png)

13. <span data-ttu-id="1a5ef-179">Fügen Sie der Administrator-oder Tester-Rolle einen Benutzer hinzu.</span><span class="sxs-lookup"><span data-stu-id="1a5ef-179">Add user to the admin or tester role.</span></span>

    ![Hinzufügen eines Benutzers zur Administrator-oder Tester-Rolle](../media/FBCimage37.png)

14. <span data-ttu-id="1a5ef-181">Fügen Sie die **Seite öffentliche Inhalts Zugriffs** Berechtigung hinzu.</span><span class="sxs-lookup"><span data-stu-id="1a5ef-181">Add the **Page Public Content Access** permission.</span></span>

    ![DD die Seite öffentliche Inhalts Zugriffsberechtigung](../media/FBCimage38.png)

15. <span data-ttu-id="1a5ef-183">Berechtigung zum Hinzufügen von Seiten verwalten.</span><span class="sxs-lookup"><span data-stu-id="1a5ef-183">Add Manage Pages permission.</span></span>

    ![Berechtigung zum Hinzufügen von Seiten verwalten](../media/FBCimage39.png)

16. <span data-ttu-id="1a5ef-185">Holen Sie sich die Anwendung von Facebook überprüft.</span><span class="sxs-lookup"><span data-stu-id="1a5ef-185">Get the application reviewed by Facebook.</span></span>

    ![Abrufen der von Facebook überprüften Anwendung](../media/FBCimage40.png)

## <a name="step-4-configure-the-connector-web-app"></a><span data-ttu-id="1a5ef-187">Schritt 4: Konfigurieren der Connector-Webanwendung</span><span class="sxs-lookup"><span data-stu-id="1a5ef-187">Step 4: Configure the connector web app</span></span>

1. <span data-ttu-id="1a5ef-188">Wechseln `https://<AzureAppResourceName>.azurewebsites.net` Sie zu (wobei AzureAppResourceName der Name Ihrer Azure-App-Ressource ist, die Sie in Schritt 4 benannt haben).</span><span class="sxs-lookup"><span data-stu-id="1a5ef-188">Go to `https://<AzureAppResourceName>.azurewebsites.net` (where AzureAppResourceName is the name of your Azure app resource that you named in Step 4).</span></span> <span data-ttu-id="1a5ef-189">Wenn der Name beispielsweise **FBconnector**lautet, wechseln Sie zu `https://fbconnector.azurewebsites.net` .</span><span class="sxs-lookup"><span data-stu-id="1a5ef-189">For example, if the name is **fbconnector**, go to `https://fbconnector.azurewebsites.net`.</span></span> <span data-ttu-id="1a5ef-190">Die Startseite der APP sieht wie im folgenden Screenshot aus:</span><span class="sxs-lookup"><span data-stu-id="1a5ef-190">The home page of the app will look like the following screenshot:</span></span>

   ![Wechseln Sie zur Connector-Webanwendung](../media/FBCimage41.png)

2. <span data-ttu-id="1a5ef-192">Klicken Sie auf **Konfigurieren** , um eine Anmeldeseite anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="1a5ef-192">Click **Configure** to display a sign in page.</span></span>

   ![Klicken Sie auf konfigurieren, um eine Anmeldeseite anzuzeigen.](../media/FBCimage42.png)

3. <span data-ttu-id="1a5ef-194">Geben Sie in das Feld Mandanten-ID die Mandanten-ID ein, die Sie in Schritt 2 erhalten haben, oder fügen Sie Sie ein.</span><span class="sxs-lookup"><span data-stu-id="1a5ef-194">In the Tenant Id box, type or paste your tenant Id (that you obtained in Step 2).</span></span> <span data-ttu-id="1a5ef-195">Geben Sie in das Feld Kennwort den APISecretKey (den Sie in Schritt 2 erhalten haben) ein, oder fügen Sie ihn ein, und klicken Sie dann auf **Konfigurationseinstellungen festlegen** , um die Seite Konfigurationsdetails anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="1a5ef-195">In the password box, type or paste the APISecretKey (that you obtained in Step 2), and then click **Set Configuration Settings** to display the configuration details page.</span></span>

    ![Melden Sie sich mit Ihrer Mandanten-ID und Ihrem Kennwort an, und wechseln Sie zur Seite Konfigurationsdetails.](../media/FBCimage43.png)

4. <span data-ttu-id="1a5ef-197">Geben Sie die folgenden Konfigurationseinstellungen ein:</span><span class="sxs-lookup"><span data-stu-id="1a5ef-197">Enter the following configuration settings</span></span>

   - <span data-ttu-id="1a5ef-198">**Facebook-Anwendungs-ID:** Die APP-ID für die Facebook-Anwendung, die Sie in Schritt 3 erhalten haben.</span><span class="sxs-lookup"><span data-stu-id="1a5ef-198">**Facebook application ID:** The app ID for the Facebook application that you obtained in Step 3.</span></span>

   - <span data-ttu-id="1a5ef-199">**Geheime Facebook-Anwendung:** Der APP-Schlüssel für die Facebook-Anwendung, die Sie in Schritt 3 erhalten haben.</span><span class="sxs-lookup"><span data-stu-id="1a5ef-199">**Facebook application secret:** The app secret for the Facebook application that you obtained in Step 3.</span></span>

   - <span data-ttu-id="1a5ef-200">**Facebook webhooks überprüfen Token:** Das Überprüfen-Token, das Sie in Schritt 3 erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="1a5ef-200">**Facebook webhooks verify token:** The verify token that you created in Step 3.</span></span>

   - <span data-ttu-id="1a5ef-201">**Aad-Anwendungs-ID:** Die Anwendungs-ID für die Azure Active Directory-APP, die Sie in Schritt 1 erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="1a5ef-201">**AAD application ID:** The application ID for the Azure Active Directory app that you created in Step 1.</span></span>

   - <span data-ttu-id="1a5ef-202">**Aad-Anwendungsschlüssel:** Der Wert für den geheimen APISecretKey, den Sie in Schritt 1 erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="1a5ef-202">**AAD application secret:** The value for the APISecretKey secret that you created in Step 1.</span></span>

5. <span data-ttu-id="1a5ef-203">Klicken Sie auf **Speichern** , um die Verbindungseinstellungen zu speichern.</span><span class="sxs-lookup"><span data-stu-id="1a5ef-203">Click **Save** to save the connector settings.</span></span>

## <a name="step-5-set-up-a-facebook-connector-in-the-microsoft-365-compliance-center"></a><span data-ttu-id="1a5ef-204">Schritt 5: Einrichten eines Facebook-Connectors im Microsoft 365 Compliance Center</span><span class="sxs-lookup"><span data-stu-id="1a5ef-204">Step 5: Set up a Facebook connector in the Microsoft 365 compliance center</span></span>

1. <span data-ttu-id="1a5ef-205">Wechseln Sie zu, [https://compliance.microsoft.com](https://compliance.microsoft.com) und klicken Sie dann im linken Navigationsbereich auf **Datenverbindungen** .</span><span class="sxs-lookup"><span data-stu-id="1a5ef-205">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com) and then click **Data connectors** in the left nav.</span></span>

2. <span data-ttu-id="1a5ef-206">Klicken Sie auf der Seite **Daten Konnektoren (Vorschau)** unter **Facebook Business Pages**auf **Ansicht**.</span><span class="sxs-lookup"><span data-stu-id="1a5ef-206">On the **Data connectors (preview)** page under **Facebook Business pages**, click **View**.</span></span>

3. <span data-ttu-id="1a5ef-207">Klicken Sie auf der Seite **Facebook-Geschäfts Seiten** auf **Connector hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="1a5ef-207">On the **Facebook business pages** page, click **Add connector**.</span></span>

4. <span data-ttu-id="1a5ef-208">Klicken Sie auf der Seite **Nutzungsbedingungen** auf **annehmen**.</span><span class="sxs-lookup"><span data-stu-id="1a5ef-208">On the **Terms of service** page, click **Accept**.</span></span>

5. <span data-ttu-id="1a5ef-209">Geben Sie auf der Seite **Anmeldeinformationen für ihre Connector-app hinzufügen** die folgenden Informationen ein, und klicken Sie dann auf **Verbindung überprüfen**.</span><span class="sxs-lookup"><span data-stu-id="1a5ef-209">On the **Add credentials for your connector app** page, enter the following information and then click **Validate connection**.</span></span>

   ![Eingeben von Connector-App-Anmeldeinformationen](../media/TCimage38.png)

   - <span data-ttu-id="1a5ef-211">Geben Sie im Feld **Name** einen Namen für den Connector ein, beispielsweise **Facebook-Nachrichtenseite**.</span><span class="sxs-lookup"><span data-stu-id="1a5ef-211">In the **Name** box, type a name for the connector, such as **Facebook news page**.</span></span>

   - <span data-ttu-id="1a5ef-212">Geben Sie im Feld **Verbindungs-URL** die Azure-App-Dienst-URL ein, oder fügen Sie Sie ein. zum Beispiel `https://fbconnector.azurewebsites.net` .</span><span class="sxs-lookup"><span data-stu-id="1a5ef-212">In the **Connection URL** box, type or paste the Azure app service URL; for example `https://fbconnector.azurewebsites.net`.</span></span>

   - <span data-ttu-id="1a5ef-213">Geben Sie in das Feld **Kennwort** den Wert des APISecretKey ein, den Sie in Schritt 2 hinzugefügt haben, oder fügen Sie ihn ein.</span><span class="sxs-lookup"><span data-stu-id="1a5ef-213">In the **Password** box, type or paste the value of the APISecretKey that you added in Step 2.</span></span>

   - <span data-ttu-id="1a5ef-214">Geben Sie in das Feld **Azure-APP-ID** den Wert der Anwendungs-ID Application (Client) ein, die auch als Aad-Anwendungs-ID bezeichnet wird, die Sie in Schritt 1 erstellt haben, oder fügen Sie ihn ein.</span><span class="sxs-lookup"><span data-stu-id="1a5ef-214">In the **Azure App ID** box, type or paste the value of the Application (client) ID also called as AAD Application ID that you created in Step 1.</span></span>

6. <span data-ttu-id="1a5ef-215">Nachdem die Verbindung erfolgreich überprüft wurde, klicken Sie auf **weiter**.</span><span class="sxs-lookup"><span data-stu-id="1a5ef-215">After the connection is successfully validated, click **Next**.</span></span>

7. <span data-ttu-id="1a5ef-216">Geben Sie auf der Seite **Microsoft 365 zum Importieren von Daten autorisieren** den APISecretKey erneut ein, oder fügen Sie ihn ein, und klicken Sie dann auf **Login-webapp**.</span><span class="sxs-lookup"><span data-stu-id="1a5ef-216">On the **Authorize Microsoft 365 to import data** page, type or paste the APISecretKey again and then click **Login web app**.</span></span>

8. <span data-ttu-id="1a5ef-217">Klicken Sie auf der Seite **Facebook Connector-App konfigurieren** auf **Anmeldung bei Facebook** , und melden Sie sich mit den Anmeldeinformationen für das Konto für die Facebook-Geschäfts Seiten Ihrer Organisation an.</span><span class="sxs-lookup"><span data-stu-id="1a5ef-217">On the **Configure Facebook connector app** page, click **Login with Facebook** and log in using the credentials for the account for your organization's Facebook Business pages.</span></span> <span data-ttu-id="1a5ef-218">Stellen Sie sicher, dass das Facebook-Konto, an dem Sie sich angemeldet haben, der Administratorrolle für die Facebook-Geschäfts Seiten Ihrer Organisation zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="1a5ef-218">Make sure the Facebook account that you logged in to is assigned the admin role for your organization's Facebook Business pages.</span></span>

   ![Melden Sie sich bei Facebook an.](../media/FBCimage50.png)

9. <span data-ttu-id="1a5ef-220">Eine Liste der Geschäfts Seiten, die von dem Facebook-Konto verwaltet werden, in dem Sie sich angemeldet haben, wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="1a5ef-220">A list of the business pages managed by the Facebook account that you logged in to is displayed.</span></span> <span data-ttu-id="1a5ef-221">Wählen Sie die zu archivierende Seite aus, und klicken Sie dann auf **weiter**.</span><span class="sxs-lookup"><span data-stu-id="1a5ef-221">Select the page to archive and then click **Next**.</span></span>

   ![Wählen Sie die Geschäftsseite der Organisation aus, die Sie archivieren möchten.](../media/FBCimage52.png)

10. <span data-ttu-id="1a5ef-223">Klicken Sie auf **weiter** , um das Setup der Connector-Dienst-APP zu beenden.</span><span class="sxs-lookup"><span data-stu-id="1a5ef-223">Click **Continue** to exit the setup of the connector service app.</span></span>

11. <span data-ttu-id="1a5ef-224">Auf der Seite **Filter festlegen** können Sie einen Filter anwenden, um Elemente anfänglich zu importieren, die ein bestimmtes Alter aufweisen.</span><span class="sxs-lookup"><span data-stu-id="1a5ef-224">On the **Set filters** page, you can apply a filter to initially import items that are a certain age.</span></span> <span data-ttu-id="1a5ef-225">Wählen Sie ein Alter aus, und klicken Sie dann auf **weiter**.</span><span class="sxs-lookup"><span data-stu-id="1a5ef-225">Select an age, and then click **Next**.</span></span>

12. <span data-ttu-id="1a5ef-226">Geben Sie auf der Seite Speicherort **auswählen** die e-Mail-Adresse des Microsoft 365-Postfachs ein, in das die Facebook-Elemente importiert werden sollen, und klicken Sie dann auf **weiter**.</span><span class="sxs-lookup"><span data-stu-id="1a5ef-226">On the **Choose storage location** page, type the email address of Microsoft 365 mailbox that the Facebook items will be imported to, and then click **Next**.</span></span>

13. <span data-ttu-id="1a5ef-227">Klicken Sie im die **Zustimmung des Administrators bereit**stellen auf **Zustimmung erteilen** , und führen Sie dann die Schritte aus.</span><span class="sxs-lookup"><span data-stu-id="1a5ef-227">On the **Provide admin consent**, click **Provide consent** and then follow the steps.</span></span> <span data-ttu-id="1a5ef-228">Sie müssen ein globaler Administrator sein, um die Zustimmung des Office 365-Import Diensts für den Zugriff auf Daten in Ihrer Organisation zu geben.</span><span class="sxs-lookup"><span data-stu-id="1a5ef-228">You must be a global admin to provide consent for the Office 365 Import service to access data in your organization.</span></span>

14. <span data-ttu-id="1a5ef-229">Klicken Sie auf **weiter** , um die Connectoreinstellungen zu überprüfen, und klicken Sie dann auf **Fertig stellen** , um das Connector-Setup abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="1a5ef-229">Click **Next** to review the connector settings and then click **Finish** to complete the connector setup.</span></span>

15. <span data-ttu-id="1a5ef-230">Wechseln Sie im Compliance Center zur Seite **Daten Konnektoren** , und klicken Sie auf die Registerkarte **Connectors** , um den Status des Importvorgangs anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="1a5ef-230">In the compliance center, go to the **Data connectors** page, and click the **Connectors** tab to see the progress of the import process.</span></span>
