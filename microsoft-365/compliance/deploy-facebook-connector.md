---
title: Bereitstellen eines Connectors zum Archivieren von Daten von Facebook Business-Seiten
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
description: Administratoren können einen systemeigenen Connector zum Importieren und Archivieren von Facebook Business-Seiten für Microsoft 365. Nachdem diese Daten in Microsoft 365 importiert wurden, können Sie Compliancefeatures wie gesetzliche Aufbewahrung, Inhaltssuche und Aufbewahrungsrichtlinien verwenden, um die Steuerung der Facebook-Daten Ihrer Organisation zu verwalten.
ms.openlocfilehash: b771c50eb5c2eb5f99269f1f399d27043ebee6bb
ms.sourcegitcommit: 6fc6aaa2b7610e148f41018abd229e3c55b2f3d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "49619951"
---
# <a name="deploy-a-connector-to-archive-facebook-business-pages-data"></a><span data-ttu-id="b2b3b-104">Bereitstellen eines Connectors zum Archivieren von Daten von Facebook Business-Seiten</span><span class="sxs-lookup"><span data-stu-id="b2b3b-104">Deploy a connector to archive Facebook Business pages data</span></span>

<span data-ttu-id="b2b3b-105">Dieser Artikel enthält den schrittweisen Prozess zum Bereitstellen eines Connectors, der den Office 365 Import-Dienst zum Importieren von Daten von Facebook Business-Seiten in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="b2b3b-105">This article contains the step-by-step process to deploy a connector that uses the Office 365 Import service to import data from Facebook Business pages to Microsoft 365.</span></span> <span data-ttu-id="b2b3b-106">Eine übersicht über diesen Prozess und eine Liste der erforderlichen Voraussetzungen für die Bereitstellung eines Facebook-Connectors finden Sie unter Einrichten eines Connectors zum Archivieren von [Facebook-Daten.](archive-facebook-data-with-sample-connector.md)</span><span class="sxs-lookup"><span data-stu-id="b2b3b-106">For a high-level overview of this process and a list of prerequisites required to deploy a Facebook connector, see [Set up a connector to archive Facebook data](archive-facebook-data-with-sample-connector.md).</span></span>

## <a name="step-1-create-an-app-in-azure-active-directory"></a><span data-ttu-id="b2b3b-107">Schritt 1: Erstellen einer App in Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="b2b3b-107">Step 1: Create an app in Azure Active Directory</span></span>

1. <span data-ttu-id="b2b3b-108">Wechseln Sie zu, und melden Sie <https://portal.azure.com> sich mit den Anmeldeinformationen eines globalen Administratorkontos an.</span><span class="sxs-lookup"><span data-stu-id="b2b3b-108">Go to <https://portal.azure.com> and sign in using the credentials of a global admin account.</span></span>

    ![Erstellen einer App in AAD](../media/FBCimage1.png)

2. <span data-ttu-id="b2b3b-110">Klicken Sie im linken Navigationsbereich auf **Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="b2b3b-110">In the left navigation pane, click **Azure Active Directory**.</span></span>

    ![Klicken Sie Azure Active Directory](../media/FBCimage2.png)

3. <span data-ttu-id="b2b3b-112">Klicken Sie im linken Navigationsbereich auf **App-Registrierungen (Vorschau)** und dann **auf Neue Registrierung**.</span><span class="sxs-lookup"><span data-stu-id="b2b3b-112">In the left navigation pane, click **App registrations (Preview)** and then click **New registration**.</span></span>

    ![Klicken Sie auf **App-Registrierungen (Vorschau)** und dann auf **Neue Registrierung**](../media/FBCimage3.png)

4. <span data-ttu-id="b2b3b-114">Registrieren Sie die Anwendung.</span><span class="sxs-lookup"><span data-stu-id="b2b3b-114">Register the application.</span></span> <span data-ttu-id="b2b3b-115">Wählen Sie unter Umleitungs-URI die Option Web in der Dropdownliste anwendungstyp aus, und geben Sie dann in das Feld <https://portal.azure.com> für den URI ein.</span><span class="sxs-lookup"><span data-stu-id="b2b3b-115">Under Redirect URI, select Web in the application type dropdown list and then type <https://portal.azure.com> in the box for the URI.</span></span>

   ![Registrieren der App](../media/FBCimage4.png)

5. <span data-ttu-id="b2b3b-117">Kopieren Sie **die Anwendungs-ID (Client-)ID** und die **Verzeichnis-ID (Mandant),** und speichern Sie sie in einer Textdatei oder an einem anderen sicheren Speicherort.</span><span class="sxs-lookup"><span data-stu-id="b2b3b-117">Copy the **Application (client) ID** and **Directory (tenant) ID** and save them to a text file or other safe location.</span></span> <span data-ttu-id="b2b3b-118">Sie verwenden diese IDs in späteren Schritten.</span><span class="sxs-lookup"><span data-stu-id="b2b3b-118">You use these IDs in later steps.</span></span>

   ![Kopieren sie die Anwendungs-ID und die Verzeichnis-ID, und speichern Sie sie](../media/FBCimage5.png)

6. <span data-ttu-id="b2b3b-120">Wechseln Sie **zu Zertifikate & für die neue App.**</span><span class="sxs-lookup"><span data-stu-id="b2b3b-120">Go to **Certificates & secrets for the new app.**</span></span>

   ![Wechseln Sie zu Zertifikate & für die neue App](../media/FBCimage6.png)

7. <span data-ttu-id="b2b3b-122">Klicken Sie **auf Neuer Geheimer Clientgeheimnis**</span><span class="sxs-lookup"><span data-stu-id="b2b3b-122">Click **New client secret**</span></span>

   ![Klicken Sie auf Neuer Geheimer Clientgeheimnis](../media/FBCimage7.png)

8. <span data-ttu-id="b2b3b-124">Erstellen Sie einen neuen geheimen Schlüssel.</span><span class="sxs-lookup"><span data-stu-id="b2b3b-124">Create a new secret.</span></span> <span data-ttu-id="b2b3b-125">Geben Sie in das Feld Beschreibung den geheimen Schlüssel ein, und wählen Sie dann einen Ablaufzeitraum aus.</span><span class="sxs-lookup"><span data-stu-id="b2b3b-125">In the description box, type the secret and then choose an expiration period.</span></span>

    ![Geben Sie den geheimen Schlüssel ein, und wählen Sie dann einen Ablaufzeitraum aus.](../media/FBCimage8.png)

9. <span data-ttu-id="b2b3b-127">Kopieren Sie den Wert des geheimen Schlüssels, und speichern Sie ihn in einer Textdatei oder einem anderen Speicherort.</span><span class="sxs-lookup"><span data-stu-id="b2b3b-127">Copy the value of the secret and save it to a text file or other storage location.</span></span> <span data-ttu-id="b2b3b-128">Dies ist der geheime AAD-Anwendungsgeheimnis, den Sie in späteren Schritten verwenden.</span><span class="sxs-lookup"><span data-stu-id="b2b3b-128">This is the AAD application secret that you use in later steps.</span></span>

   ![Kopieren Sie den Wert des geheimen Schlüssels, und speichern Sie ihn.](../media/FBCimage9.png)

## <a name="step-2-deploy-the-connector-web-service-from-github-to-your-azure-account"></a><span data-ttu-id="b2b3b-130">Schritt 2: Bereitstellen des Connectorwebdiensts GitHub Ihrem Azure-Konto</span><span class="sxs-lookup"><span data-stu-id="b2b3b-130">Step 2: Deploy the connector web service from GitHub to your Azure account</span></span>

1. <span data-ttu-id="b2b3b-131">Wechseln Sie [zu GitHub Website,](https://github.com/microsoft/m365-sample-connector-csharp-aspnet) und klicken Sie **auf Bereitstellen in Azure**.</span><span class="sxs-lookup"><span data-stu-id="b2b3b-131">Go to [this GitHub site](https://github.com/microsoft/m365-sample-connector-csharp-aspnet) and click **Deploy to Azure**.</span></span>

    ![Klicken Sie auf Bereitstellen in Azure](../media/FBCGithubApp.png)

2. <span data-ttu-id="b2b3b-133">Nachdem Sie auf **Bereitstellen in Azure** geklickt haben, werden Sie zu einem Azure-Portal mit einer benutzerdefinierten Vorlagenseite umgeleitet.</span><span class="sxs-lookup"><span data-stu-id="b2b3b-133">After you click **Deploy to Azure**, you will be redirected to an Azure portal with a custom template page.</span></span> <span data-ttu-id="b2b3b-134">Füllen Sie die **Grundlagen und** **Einstellungen** aus, und klicken Sie dann auf **Kaufen**.</span><span class="sxs-lookup"><span data-stu-id="b2b3b-134">Fill in the **Basics** and **Settings** details and then click **Purchase**.</span></span>

   - <span data-ttu-id="b2b3b-135">**Abonnement:** Wählen Sie Ihr Azure-Abonnement aus, für das Sie den Connectorwebdienst für Facebook Business-Seiten bereitstellen möchten.</span><span class="sxs-lookup"><span data-stu-id="b2b3b-135">**Subscription:** Select your Azure subscription that you want to deploy the Facebook Business pages connector web service to.</span></span>

   - <span data-ttu-id="b2b3b-136">**Ressourcengruppe:** Wählen oder erstellen Sie eine neue Ressourcengruppe.</span><span class="sxs-lookup"><span data-stu-id="b2b3b-136">**Resource group:** Choose or create a new resource group.</span></span> <span data-ttu-id="b2b3b-137">Eine Ressourcengruppe ist ein Container, der verwandte Ressourcen für eine Azure-Lösung enthält.</span><span class="sxs-lookup"><span data-stu-id="b2b3b-137">A resource group is a container that holds related resources for an Azure solution.</span></span>

   - <span data-ttu-id="b2b3b-138">**Speicherort:** Wählen Sie einen Speicherort aus.</span><span class="sxs-lookup"><span data-stu-id="b2b3b-138">**Location:** Choose a location.</span></span>

   - <span data-ttu-id="b2b3b-139">**Web-App-Name:** Geben Sie einen eindeutigen Namen für die Connector-Web-App an.</span><span class="sxs-lookup"><span data-stu-id="b2b3b-139">**Web App Name:** Provide a unique name for the connector web app.</span></span> <span data-ttu-id="b2b3b-140">Der Name Th muss zwischen 3 und 18 Zeichen lang sein.</span><span class="sxs-lookup"><span data-stu-id="b2b3b-140">Th name must be between 3 and 18 characters in length.</span></span> <span data-ttu-id="b2b3b-141">Dieser Name wird zum Erstellen der Azure-App-Dienst-URL verwendet. Wenn Sie z. B. den Web-App-Namen **fbconnector** angeben, wird die Azure-App-Dienst-URL **fbconnector.azurewebsites.net.**</span><span class="sxs-lookup"><span data-stu-id="b2b3b-141">This name is used to create the Azure app service URL; for example, if you provide the Web app name of **fbconnector** then the Azure app service URL  will be **fbconnector.azurewebsites.net**.</span></span>

   - <span data-ttu-id="b2b3b-142">**tenantId:** Die Mandanten-ID Ihrer Microsoft 365, die Sie nach dem Erstellen der Facebook-Connector-App in Azure Active Directory Schritt 1 kopiert haben.</span><span class="sxs-lookup"><span data-stu-id="b2b3b-142">**tenantId:** The tenant ID of your Microsoft 365 organization that you copied after creating the Facebook connector app in Azure Active Directory in Step 1.</span></span>

   - <span data-ttu-id="b2b3b-143">**APISecretKey:** Sie können einen beliebigen Wert als geheimen Wert eingeben.</span><span class="sxs-lookup"><span data-stu-id="b2b3b-143">**APISecretKey:** You can type any value as the secret.</span></span> <span data-ttu-id="b2b3b-144">Dies wird für den Zugriff auf die Connectorweb-App in Schritt 5 verwendet.</span><span class="sxs-lookup"><span data-stu-id="b2b3b-144">This is used to access the connector web app in Step 5.</span></span>

     ![Klicken Sie auf Ressourcen- und Typspeicherkonto erstellen](../media/FBCimage12.png)

3. <span data-ttu-id="b2b3b-146">Nachdem die Bereitstellung erfolgreich war, sieht die Seite ähnlich dem folgenden Screenshot aus:</span><span class="sxs-lookup"><span data-stu-id="b2b3b-146">After the deployment is successful, the page will look similar to the following screenshot:</span></span>

   ![Klicken Storage und dann auf Storage Konto](../media/FBCimage13.png)

## <a name="step-3-register-the-facebook-app"></a><span data-ttu-id="b2b3b-148">Schritt 3: Registrieren der Facebook-App</span><span class="sxs-lookup"><span data-stu-id="b2b3b-148">Step 3: Register the Facebook app</span></span>

1. <span data-ttu-id="b2b3b-149">Wechseln Sie zu , melden Sie sich mit den Anmeldeinformationen für das Konto für die Facebook Business-Seiten Ihrer Organisation an, und klicken Sie dann <https://developers.facebook.com> **auf Neue App hinzufügen.**</span><span class="sxs-lookup"><span data-stu-id="b2b3b-149">Go to <https://developers.facebook.com>, log in using the credentials for the account for your organization's Facebook Business pages, and then click **Add New App**.</span></span>

   ![Hinzufügen einer neuen App für Facebook-Geschäftsseite](../media/FBCimage25.png)

2. <span data-ttu-id="b2b3b-151">Erstellen Sie eine neue App-ID.</span><span class="sxs-lookup"><span data-stu-id="b2b3b-151">Create a new app ID.</span></span>

   ![Erstellen einer neuen App-ID](../media/FBCimage26.png)

3. <span data-ttu-id="b2b3b-153">Klicken Sie im linken Navigationsbereich auf **Produkte hinzufügen,** und klicken Sie dann **in** der Kachel **Facebook-Anmeldung** auf Einrichten.</span><span class="sxs-lookup"><span data-stu-id="b2b3b-153">In the left navigation pane, click **Add Products** and then click **Set Up** in the **Facebook Login** tile.</span></span>

   ![Klicken Sie auf Produkte hinzufügen](../media/FBCimage27.png)

4. <span data-ttu-id="b2b3b-155">Klicken Sie auf der Seite Facebook-Anmeldung integrieren auf **Web**.</span><span class="sxs-lookup"><span data-stu-id="b2b3b-155">On the Integrate Facebook Login page, click **Web**.</span></span>

   ![Klicken Sie auf der Seite "Facebook-Anmeldung integrieren" auf Web.](../media/FBCimage28.png)

5. <span data-ttu-id="b2b3b-157">Fügen Sie die Azure-App-Dienst-URL hinzu. beispiel: `https://fbconnector.azurewebsites.net` .</span><span class="sxs-lookup"><span data-stu-id="b2b3b-157">Add the Azure app service URL; for example `https://fbconnector.azurewebsites.net`.</span></span>

   ![Hinzufügen der Azure-App-Dienst-URL](../media/FBCimage29.png)

6. <span data-ttu-id="b2b3b-159">Schließen Sie den Abschnitt Schnellstart des Setups für die Facebook-Anmeldung ab.</span><span class="sxs-lookup"><span data-stu-id="b2b3b-159">Complete the QuickStart section of the Facebook Login setup.</span></span>

   ![Abschließen des Abschnitts QuickStart](../media/FBCimage30.png)

7. <span data-ttu-id="b2b3b-161">Klicken Sie im linken Navigationsbereich unter **Facebook-Anmeldung** **auf Einstellungen**, und fügen Sie den OAuth-Umleitungs-URI im Feld Gültige **OAuth-Umleitungs-URIs** hinzu.</span><span class="sxs-lookup"><span data-stu-id="b2b3b-161">In the left navigation pane under **Facebook Login**, click **Settings**, and add the OAuth redirect URI in the **Valid OAuth Redirect URIs** box.</span></span> <span data-ttu-id="b2b3b-162">Verwenden Sie das **\<connectorserviceuri> Format /Views/FacebookOAuth**, wobei der Wert für connectorserviceuri die Azure-App-Dienst-URL für Ihre Organisation ist, z. B. `https://fbconnector.azurewebsites.net` .</span><span class="sxs-lookup"><span data-stu-id="b2b3b-162">Use the format **\<connectorserviceuri>/Views/FacebookOAuth**, where the value for connectorserviceuri is the Azure app service URL for your organization; for example, `https://fbconnector.azurewebsites.net`.</span></span>

   ![Hinzufügen des OAuth-Umleitungs-URI zum Feld Gültige OAuth-Umleitungs-URIs](../media/FBCimage31.png)

8. <span data-ttu-id="b2b3b-164">Klicken Sie im linken Navigationsbereich auf **Produkte hinzufügen,** und klicken Sie dann auf **Webhooks.**</span><span class="sxs-lookup"><span data-stu-id="b2b3b-164">In the left navigation pane, click **Add Products** and then click **Webhooks.**</span></span> <span data-ttu-id="b2b3b-165">Klicken Sie **im** Pull-Down-Menü Seite auf **Seite**.</span><span class="sxs-lookup"><span data-stu-id="b2b3b-165">In the **Page** pull-down menu, click **Page**.</span></span>

   ![Klicken Sie auf Produkte hinzufügen, und klicken Sie dann auf \*\*Webhooks](../media/FBCimage32.png)

9. <span data-ttu-id="b2b3b-167">Fügen Sie die Webhooks-Rückruf-URL hinzu, und fügen Sie ein Überprüfungstoken hinzu.</span><span class="sxs-lookup"><span data-stu-id="b2b3b-167">Add Webhooks Callback URL and add a verify token.</span></span> <span data-ttu-id="b2b3b-168">Verwenden Sie im Format der Rückruf-URL das Format **<connectorserviceuri> /api/FbPageWebhook**, wobei der Wert für connectorserviceuri die Azure-App-Dienst-URL für Ihre Organisation ist, z. B. `https://fbconnector.azurewebsites.net` .</span><span class="sxs-lookup"><span data-stu-id="b2b3b-168">The format of the callback URL, use the format **<connectorserviceuri>/api/FbPageWebhook**, where the value for connectorserviceuri is the Azure app service URL for your organization; for example `https://fbconnector.azurewebsites.net`.</span></span>

   <span data-ttu-id="b2b3b-169">Das Überprüfungstoken sollte einem starken Kennwort ähnlich sein.</span><span class="sxs-lookup"><span data-stu-id="b2b3b-169">The verify token should similar to a strong password.</span></span> <span data-ttu-id="b2b3b-170">Kopieren Sie das Überprüfungstoken in eine Textdatei oder einen anderen Speicherort.</span><span class="sxs-lookup"><span data-stu-id="b2b3b-170">Copy the verify token to a text file or other storage location.</span></span>

   ![Hinzufügen des Überprüfungstokens](../media/FBCimage33.png)

10. <span data-ttu-id="b2b3b-172">Testen und abonnieren Sie den Endpunkt für feed.</span><span class="sxs-lookup"><span data-stu-id="b2b3b-172">Test and subscribe to the endpoint for feed.</span></span>

    ![Testen und Abonnieren des Endpunkts](../media/FBCimage34.png)

11. <span data-ttu-id="b2b3b-174">Fügen Sie eine Datenschutz-URL, ein App-Symbol und eine Unternehmensnutzung hinzu.</span><span class="sxs-lookup"><span data-stu-id="b2b3b-174">Add a privacy URL, app icon, and business use.</span></span> <span data-ttu-id="b2b3b-175">Kopieren Sie außerdem die App-ID und den geheimen App-Schlüssel in eine Textdatei oder einen anderen Speicherort.</span><span class="sxs-lookup"><span data-stu-id="b2b3b-175">Also, copy the app ID and app secret to a text file or other storage location.</span></span>

    ![Hinzufügen einer Datenschutz-URL, eines App-Symbols und einer Unternehmensnutzung](../media/FBCimage35.png)

12. <span data-ttu-id="b2b3b-177">Machen Sie die App öffentlich.</span><span class="sxs-lookup"><span data-stu-id="b2b3b-177">Make the app public.</span></span>

    ![Öffentliches Machen der App](../media/FBCimage36.png)

13. <span data-ttu-id="b2b3b-179">Hinzufügen eines Benutzers zur Rolle "Administrator" oder "Tester".</span><span class="sxs-lookup"><span data-stu-id="b2b3b-179">Add user to the admin or tester role.</span></span>

    ![Hinzufügen eines Benutzers zur Rolle "Administrator" oder "Tester"](../media/FBCimage37.png)

14. <span data-ttu-id="b2b3b-181">Fügen Sie die **Berechtigung Page Public Content Access** hinzu.</span><span class="sxs-lookup"><span data-stu-id="b2b3b-181">Add the **Page Public Content Access** permission.</span></span>

    ![dd die Berechtigung "Page Public Content Access"](../media/FBCimage38.png)

15. <span data-ttu-id="b2b3b-183">Hinzufügen der Berechtigung Seiten verwalten.</span><span class="sxs-lookup"><span data-stu-id="b2b3b-183">Add Manage Pages permission.</span></span>

    ![Hinzufügen der Berechtigung Seiten verwalten](../media/FBCimage39.png)

16. <span data-ttu-id="b2b3b-185">Die Anwendung wird von Facebook überprüft.</span><span class="sxs-lookup"><span data-stu-id="b2b3b-185">Get the application reviewed by Facebook.</span></span>

    ![Von Facebook überprüfte Anwendung erhalten](../media/FBCimage40.png)

## <a name="step-4-configure-the-connector-web-app"></a><span data-ttu-id="b2b3b-187">Schritt 4: Konfigurieren der Connectorweb-App</span><span class="sxs-lookup"><span data-stu-id="b2b3b-187">Step 4: Configure the connector web app</span></span>

1. <span data-ttu-id="b2b3b-188">Wechseln Sie `https://<AzureAppResourceName>.azurewebsites.net` zu (wobei AzureAppResourceName der Name Ihrer Azure-App-Ressource ist, die Sie in Schritt 4 benannt haben).</span><span class="sxs-lookup"><span data-stu-id="b2b3b-188">Go to `https://<AzureAppResourceName>.azurewebsites.net` (where AzureAppResourceName is the name of your Azure app resource that you named in Step 4).</span></span> <span data-ttu-id="b2b3b-189">Wenn der Name beispielsweise **fbconnector ist,** wechseln Sie zu `https://fbconnector.azurewebsites.net` .</span><span class="sxs-lookup"><span data-stu-id="b2b3b-189">For example, if the name is **fbconnector**, go to `https://fbconnector.azurewebsites.net`.</span></span> <span data-ttu-id="b2b3b-190">Die Startseite der App sieht wie der folgende Screenshot aus:</span><span class="sxs-lookup"><span data-stu-id="b2b3b-190">The home page of the app will look like the following screenshot:</span></span>

   ![Gehe zu Connector-Web-App](../media/FBCimage41.png)

2. <span data-ttu-id="b2b3b-192">Klicken **Sie auf Konfigurieren,** um eine Anmeldeseite anzeigen zu können.</span><span class="sxs-lookup"><span data-stu-id="b2b3b-192">Click **Configure** to display a sign in page.</span></span>

   ![Klicken Sie auf Konfigurieren, um eine Anmeldeseite anzeigen zu können.](../media/FBCimage42.png)

3. <span data-ttu-id="b2b3b-194">Geben Sie im Feld Mandanten-ID Ihre Mandanten-ID ein oder fügen Sie sie ein (die Sie in Schritt 2 erhalten haben).</span><span class="sxs-lookup"><span data-stu-id="b2b3b-194">In the Tenant Id box, type or paste your tenant Id (that you obtained in Step 2).</span></span> <span data-ttu-id="b2b3b-195">Geben Sie im Feld Kennwort den APISecretKey (den Sie in Schritt 2 erhalten haben) ein, oder fügen Sie ihn ein, und klicken Sie dann auf Konfigurationseinstellungen **festlegen Einstellungen,** um die Seite konfigurationsdetails anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="b2b3b-195">In the password box, type or paste the APISecretKey (that you obtained in Step 2), and then click **Set Configuration Settings** to display the configuration details page.</span></span>

    ![Melden Sie sich mit Ihrer Mandanten-ID und Ihrem Kennwort an, und wechseln Sie zur Seite konfigurationsdetails.](../media/FBCimage43.png)

4. <span data-ttu-id="b2b3b-197">Geben Sie die folgenden Konfigurationseinstellungen ein</span><span class="sxs-lookup"><span data-stu-id="b2b3b-197">Enter the following configuration settings</span></span>

   - <span data-ttu-id="b2b3b-198">**Facebook-Anwendungs-ID:** Die App-ID für die Facebook-Anwendung, die Sie in Schritt 3 erhalten haben.</span><span class="sxs-lookup"><span data-stu-id="b2b3b-198">**Facebook application ID:** The app ID for the Facebook application that you obtained in Step 3.</span></span>

   - <span data-ttu-id="b2b3b-199">**Geheimer Facebook-Anwendungsgeheimnis:** Der geheime App-Schlüssel für die Facebook-Anwendung, die Sie in Schritt 3 erhalten haben.</span><span class="sxs-lookup"><span data-stu-id="b2b3b-199">**Facebook application secret:** The app secret for the Facebook application that you obtained in Step 3.</span></span>

   - <span data-ttu-id="b2b3b-200">**Facebook-Webhooks überprüfen Token:** Das in Schritt 3 erstellte Überprüfungstoken.</span><span class="sxs-lookup"><span data-stu-id="b2b3b-200">**Facebook webhooks verify token:** The verify token that you created in Step 3.</span></span>

   - <span data-ttu-id="b2b3b-201">**AAD-Anwendungs-ID:** Die Anwendungs-ID für Azure Active Directory App, die Sie in Schritt 1 erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="b2b3b-201">**AAD application ID:** The application ID for the Azure Active Directory app that you created in Step 1.</span></span>

   - <span data-ttu-id="b2b3b-202">**Geheimer AAD-Anwendungsgeheimnis:** Der Wert für den geheimen APISecretKey-Schlüssel, den Sie in Schritt 1 erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="b2b3b-202">**AAD application secret:** The value for the APISecretKey secret that you created in Step 1.</span></span>

5. <span data-ttu-id="b2b3b-203">Klicken Sie **auf Speichern,** um die Connectoreinstellungen zu speichern.</span><span class="sxs-lookup"><span data-stu-id="b2b3b-203">Click **Save** to save the connector settings.</span></span>

## <a name="step-5-set-up-a-facebook-connector-in-the-microsoft-365-compliance-center"></a><span data-ttu-id="b2b3b-204">Schritt 5: Einrichten eines Facebook-Connectors im Microsoft 365 Compliance Center</span><span class="sxs-lookup"><span data-stu-id="b2b3b-204">Step 5: Set up a Facebook connector in the Microsoft 365 compliance center</span></span>

1. <span data-ttu-id="b2b3b-205">Wechseln Sie [https://compliance.microsoft.com](https://compliance.microsoft.com) zu,  und klicken Sie dann im linken Navigations navi auf Datenconnectors.</span><span class="sxs-lookup"><span data-stu-id="b2b3b-205">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com) and then click **Data connectors** in the left nav.</span></span>

2. <span data-ttu-id="b2b3b-206">Klicken Sie **auf der Seite** Datenconnectors unter Facebook **Business-Seiten** auf **Anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="b2b3b-206">On the **Data connectors** page under **Facebook Business pages**, click **View**.</span></span>

3. <span data-ttu-id="b2b3b-207">Klicken Sie **auf der Seite Facebook-Geschäftsseiten** auf **Connector hinzufügen.**</span><span class="sxs-lookup"><span data-stu-id="b2b3b-207">On the **Facebook business pages** page, click **Add connector**.</span></span>

4. <span data-ttu-id="b2b3b-208">Klicken Sie **auf der Seite Nutzungsbedingungen** auf **Akzeptieren**.</span><span class="sxs-lookup"><span data-stu-id="b2b3b-208">On the **Terms of service** page, click **Accept**.</span></span>

5. <span data-ttu-id="b2b3b-209">Geben Sie **auf der Seite Anmeldeinformationen für Ihre Connector-App** hinzufügen die folgenden Informationen ein, und klicken Sie dann **auf Verbindung überprüfen.**</span><span class="sxs-lookup"><span data-stu-id="b2b3b-209">On the **Add credentials for your connector app** page, enter the following information and then click **Validate connection**.</span></span>

   ![Eingeben von Connector-App-Anmeldeinformationen](../media/TCimage38.png)

   - <span data-ttu-id="b2b3b-211">Geben Sie **im Feld Name** einen Namen für den Connector ein, z. B. facebook news **page**.</span><span class="sxs-lookup"><span data-stu-id="b2b3b-211">In the **Name** box, type a name for the connector, such as **Facebook news page**.</span></span>

   - <span data-ttu-id="b2b3b-212">Geben Sie **im Feld Verbindungs-URL** die Azure-App-Dienst-URL ein oder fügen Sie sie ein. beispiel: `https://fbconnector.azurewebsites.net` .</span><span class="sxs-lookup"><span data-stu-id="b2b3b-212">In the **Connection URL** box, type or paste the Azure app service URL; for example `https://fbconnector.azurewebsites.net`.</span></span>

   - <span data-ttu-id="b2b3b-213">Geben Sie **im Feld Kennwort** den Wert des APISecretKey ein, den Sie in Schritt 2 hinzugefügt haben, oder fügen Sie ihn ein.</span><span class="sxs-lookup"><span data-stu-id="b2b3b-213">In the **Password** box, type or paste the value of the APISecretKey that you added in Step 2.</span></span>

   - <span data-ttu-id="b2b3b-214">Geben Sie **im Feld Azure App ID** den Wert der Anwendungs-ID (Client-ID) ein, die auch als AAD-Anwendungs-ID bezeichnet wird, die Sie in Schritt 1 erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="b2b3b-214">In the **Azure App ID** box, type or paste the value of the Application (client) ID also called as AAD Application ID that you created in Step 1.</span></span>

6. <span data-ttu-id="b2b3b-215">Nachdem die Verbindung erfolgreich überprüft wurde, klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="b2b3b-215">After the connection is successfully validated, click **Next**.</span></span>

7. <span data-ttu-id="b2b3b-216">Geben Sie **auf Microsoft 365 Seite** Zum Importieren von Daten autorisieren den APISecretKey erneut ein, oder fügen Sie ihn ein, und klicken Sie dann auf **Anmeldeweb-App**.</span><span class="sxs-lookup"><span data-stu-id="b2b3b-216">On the **Authorize Microsoft 365 to import data** page, type or paste the APISecretKey again and then click **Login web app**.</span></span>

8. <span data-ttu-id="b2b3b-217">Klicken Sie auf der Seite **Facebook-Connector-App** konfigurieren auf Anmelden bei **Facebook,** und melden Sie sich mit den Anmeldeinformationen für das Konto für die Facebook Business-Seiten Ihrer Organisation an.</span><span class="sxs-lookup"><span data-stu-id="b2b3b-217">On the **Configure Facebook connector app** page, click **Login with Facebook** and log in using the credentials for the account for your organization's Facebook Business pages.</span></span> <span data-ttu-id="b2b3b-218">Stellen Sie sicher, dass dem Facebook-Konto, bei dem Sie sich angemeldet haben, die Administratorrolle für die Facebook Business-Seiten Ihrer Organisation zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="b2b3b-218">Make sure the Facebook account that you logged in to is assigned the admin role for your organization's Facebook Business pages.</span></span>

   ![Melden Sie sich mit Facebook an](../media/FBCimage50.png)

9. <span data-ttu-id="b2b3b-220">Eine Liste der Geschäftsseiten, die von dem Facebook-Konto verwaltet werden, bei dem Sie sich angemeldet haben, wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="b2b3b-220">A list of the business pages managed by the Facebook account that you logged in to is displayed.</span></span> <span data-ttu-id="b2b3b-221">Wählen Sie die zu archivierende Seite aus, und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="b2b3b-221">Select the page to archive and then click **Next**.</span></span>

   ![Wählen Sie die Organisationsgeschäftsseite aus, die Sie archivieren möchten.](../media/FBCimage52.png)

10. <span data-ttu-id="b2b3b-223">Klicken **Sie auf Weiter,** um das Setup der Connectordienst-App zu beenden.</span><span class="sxs-lookup"><span data-stu-id="b2b3b-223">Click **Continue** to exit the setup of the connector service app.</span></span>

11. <span data-ttu-id="b2b3b-224">Auf der **Seite Filter festlegen** können Sie einen Filter anwenden, um elemente zu importieren, die ein bestimmtes Alter haben.</span><span class="sxs-lookup"><span data-stu-id="b2b3b-224">On the **Set filters** page, you can apply a filter to initially import items that are a certain age.</span></span> <span data-ttu-id="b2b3b-225">Wählen Sie ein Alter aus, und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="b2b3b-225">Select an age, and then click **Next**.</span></span>

12. <span data-ttu-id="b2b3b-226">Geben Sie **auf der** Seite Speicherort auswählen die E-Mail-Adresse des Microsoft 365 ein, in das die Facebook-Elemente importiert werden sollen, und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="b2b3b-226">On the **Choose storage location** page, type the email address of Microsoft 365 mailbox that the Facebook items will be imported to, and then click **Next**.</span></span>

13. <span data-ttu-id="b2b3b-227">Klicken **Sie auf Weiter,** um die Connectoreinstellungen zu überprüfen, und klicken Sie dann auf **Fertig** stellen, um die Connectoreinrichtung abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="b2b3b-227">Click **Next** to review the connector settings and then click **Finish** to complete the connector setup.</span></span>

14. <span data-ttu-id="b2b3b-228">Wechseln Sie im Compliance  Center zur Seite Datenconnectors, und klicken Sie auf die Registerkarte **Connectors,** um den Fortschritt des Importvorgangs zu sehen.</span><span class="sxs-lookup"><span data-stu-id="b2b3b-228">In the compliance center, go to the **Data connectors** page, and click the **Connectors** tab to see the progress of the import process.</span></span>
