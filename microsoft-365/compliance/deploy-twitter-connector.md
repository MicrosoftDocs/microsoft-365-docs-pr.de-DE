---
title: Bereitstellen eines Connectors zum Archivieren von Twitter-Daten
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
ROBOTS: NOINDEX, NOFOLLOW
description: Administratoren können einen systemeigenen Connector zum Importieren und Archivieren von Twitter-Daten nach Microsoft 365 einrichten. Nachdem diese Daten in Microsoft 365 importiert wurden, können Sie Compliance-Features wie Legal Hold, Inhaltssuche und Aufbewahrungsrichtlinien verwenden, um die Steuerung der Twitter-Daten Ihrer Organisation zu verwalten.
ms.openlocfilehash: 9bf0be8684eb18fbc022f4eefa798c5c9265b3d7
ms.sourcegitcommit: e872676ec98036a50d3a0cb5071109ea5f5a7ae5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "41515696"
---
# <a name="deploy-a-connector-to-archive-twitter-data"></a><span data-ttu-id="9ccd2-104">Bereitstellen eines Connectors zum Archivieren von Twitter-Daten</span><span class="sxs-lookup"><span data-stu-id="9ccd2-104">Deploy a connector to archive Twitter data</span></span>

<span data-ttu-id="9ccd2-105">Dieser Artikel enthält den schrittweisen Prozess zur Bereitstellungeines Connectors, der den Office 365 Import Dienst verwendet, um Daten aus dem Twitter-Konto Ihrer Organisation nach Microsoft 365 zu importieren.</span><span class="sxs-lookup"><span data-stu-id="9ccd2-105">This article contains the step-by-step process to deploy a connector that uses the Office 365 Import service to import data from your organization's Twitter account to Microsoft 365.</span></span> <span data-ttu-id="9ccd2-106">Eine allgemeine Übersicht über diesen Prozess und eine Liste der Voraussetzungen, die für die Bereitstellungeines Twitter-Connectors erforderlich sind, finden Sie unter [Einrichten eines Connectors zum Archivieren von Twitter-Daten ](archive-twitter-data-with-sample-connector.md).</span><span class="sxs-lookup"><span data-stu-id="9ccd2-106">For a high-level overview of this process and a list of prerequisites required to deploy a Twitter connector, see [Set up a connector to archive Twitter data ](archive-twitter-data-with-sample-connector.md).</span></span> 

## <a name="step-1-create-an-app-in-azure-active-directory"></a><span data-ttu-id="9ccd2-107">Schritt 1: Erstellen einer APP in Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="9ccd2-107">Step 1: Create an app in Azure Active Directory</span></span>

1. <span data-ttu-id="9ccd2-108">Wechseln Sie <https://portal.azure.com> zu, und melden Sie sich mit den Anmeldeinformationen eines Office 365 globalen Administratorkontos an.</span><span class="sxs-lookup"><span data-stu-id="9ccd2-108">Go to <https://portal.azure.com> and sign in using the credentials of an Office 365 global admin account.</span></span>

   ![Bei Azure anmelden](media/TCimage01.png)

2. <span data-ttu-id="9ccd2-110">Klicken Sie im linken Navigationsbereich auf **Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="9ccd2-110">In the left navigation pane, click **Azure Active Directory**.</span></span>

   ![Wechseln Sie zu Azure Active Directory](media/TCimage02.png)

3. <span data-ttu-id="9ccd2-112">Klicken Sie im linken Navigationsbereich auf **App-Registrierungen (Vorschau)** , und klicken Sie dann auf **neue Registrierung**.</span><span class="sxs-lookup"><span data-stu-id="9ccd2-112">In the left navigation pane, click **App registrations (Preview)** and then click **New registration**.</span></span>

   ![Erstellen einer neuen App-Registrierung](media/TCimage03.png)

4. <span data-ttu-id="9ccd2-114">Registrieren Sie die Anwendung.</span><span class="sxs-lookup"><span data-stu-id="9ccd2-114">Register the application.</span></span> <span data-ttu-id="9ccd2-115">Wählen Sie unter **Umleitungs-URI (optional)** in der Dropdownliste Anwendungstyp die `https://portal.azure.com` Option **Webseite** aus, und geben Sie dann in das Feld für den URI ein.</span><span class="sxs-lookup"><span data-stu-id="9ccd2-115">Under **Redirect URI (optional)**, select **Web** in the application type dropdown list and then type `https://portal.azure.com` in the box for the URI.</span></span>

   ![<span data-ttu-id="9ccd2-116">Typ https://portal.azure.com für den Umleitungs-URI</span><span class="sxs-lookup"><span data-stu-id="9ccd2-116">Type https://portal.azure.com for the redirect URI</span></span> ](media/TCimage04.png)

5. <span data-ttu-id="9ccd2-117">Kopieren Sie die Anwendungs-ID **(Client) ID** und **Verzeichnis (Mandanten)** , und speichern Sie Sie in einer Textdatei oder an einem anderen sicheren Ort.</span><span class="sxs-lookup"><span data-stu-id="9ccd2-117">Copy the **Application (client) ID** and **Directory (tenant) ID** and save them to a text file or other safe location.</span></span> <span data-ttu-id="9ccd2-118">Sie verwenden diese IDs in späteren Schritten.</span><span class="sxs-lookup"><span data-stu-id="9ccd2-118">You use these IDs in later steps.</span></span>

    ![Kopieren und Speichern der Anwendungs-ID und der Verzeichnis-ID](media/TCimage05.png)

6. <span data-ttu-id="9ccd2-120">Wechseln Sie zu **Zertifikaten #a0 Geheimnisse für die neue APP** und unter **Client Secrets** auf **neuen geheimen Client Schlüssel**.</span><span class="sxs-lookup"><span data-stu-id="9ccd2-120">Go to **Certificates & secrets for the new app** and under **Client secrets** click **New client secret**.</span></span>

   ![Erstellen eines neuen geheimen Client Schlüssels](media/TCimage06.png)

7. <span data-ttu-id="9ccd2-122">Erstellen Sie einen neuen geheimen Schlüssel.</span><span class="sxs-lookup"><span data-stu-id="9ccd2-122">Create a new secret.</span></span> <span data-ttu-id="9ccd2-123">Geben Sie im Feld Beschreibung den geheimen Schlüssel ein, und wählen Sie dann einen Ablaufzeitraum aus.</span><span class="sxs-lookup"><span data-stu-id="9ccd2-123">In the description box, type the secret and then choose an expiration period.</span></span> 

   ![Geben Sie den geheimen Schlüssel ein und wählen Sie Ablaufzeitraum](media/TCimage08.png)

8. <span data-ttu-id="9ccd2-125">Kopieren Sie den Wert des geheimen Schlüssels, und speichern Sie ihn in einer Textdatei oder an einem anderen Speicherort.</span><span class="sxs-lookup"><span data-stu-id="9ccd2-125">Copy the value of the secret and save it to a text file or other storage location.</span></span> <span data-ttu-id="9ccd2-126">Dies ist der geheime Aad-Anwendungsschlüssel, den Sie in späteren Schritten verwenden.</span><span class="sxs-lookup"><span data-stu-id="9ccd2-126">This is the AAD application secret that you use in later steps.</span></span>

   ![Kopieren und Speichern des geheimen Schlüssels](media/TCimage09.png)


## <a name="step-2-deploy-the-connector-web-service-from-github-to-your-azure-account"></a><span data-ttu-id="9ccd2-128">Schritt 2: Bereitstellen des Connector-Webdiensts von GitHub in Ihrem Azure-Konto</span><span class="sxs-lookup"><span data-stu-id="9ccd2-128">Step 2: Deploy the connector web service from GitHub to your Azure account</span></span>

1. <span data-ttu-id="9ccd2-129">Wechseln Sie zu [dieser GitHub-Website](https://github.com/microsoft/m365-sample-twitter-connector-csharp-aspnet) , und klicken Sie auf **in Azure bereitstellen**.</span><span class="sxs-lookup"><span data-stu-id="9ccd2-129">Go to [this GitHub site](https://github.com/microsoft/m365-sample-twitter-connector-csharp-aspnet) and click **Deploy to Azure**.</span></span>

    ![Wechseln zur Azure-Startseite](media/FBCimage11.png)

2. <span data-ttu-id="9ccd2-131">Nachdem Sie auf **in Azure bereitstellen**klicken, werden Sie zu einem Azure-Portal mit einer benutzerdefinierten Vorlagenseite umgeleitet.</span><span class="sxs-lookup"><span data-stu-id="9ccd2-131">After you click **Deploy to Azure**, you will be redirected to an Azure portal with a custom template page.</span></span> <span data-ttu-id="9ccd2-132">Füllen Sie die Details **Grundlagen** und **Einstellungen** aus, und klicken Sie dann auf **kaufen**.</span><span class="sxs-lookup"><span data-stu-id="9ccd2-132">Fill in the **Basics** and **Settings** details and then click **Purchase**.</span></span>

   ![Klicken Sie auf Ressource erstellen, und geben Sie Speicherkonto ein.](media/FBCimage12.png)

    - <span data-ttu-id="9ccd2-134">**Abonnement:** Wählen Sie Ihr Azure-Abonnement aus, für das Sie den Twitter Connector-Webdienst bereitstellen möchten.</span><span class="sxs-lookup"><span data-stu-id="9ccd2-134">**Subscription:** Select your Azure subscription that you want to deploy the Twitter connector web service to.</span></span>
    
    - <span data-ttu-id="9ccd2-135">**Ressourcengruppe:** Wählen oder erstellen Sie eine neue Ressourcengruppe.</span><span class="sxs-lookup"><span data-stu-id="9ccd2-135">**Resource group:** Choose or create a new resource group.</span></span> <span data-ttu-id="9ccd2-136">Eine Ressourcengruppe ist ein Container, der verwandte Ressourcen für eine Azure-Lösung bereit hält.</span><span class="sxs-lookup"><span data-stu-id="9ccd2-136">A resource group is a container that holds related resources for an Azure solution.</span></span>

    - <span data-ttu-id="9ccd2-137">**Speicherort:** Wählen Sie einen Speicherort aus.</span><span class="sxs-lookup"><span data-stu-id="9ccd2-137">**Location:** Choose a location.</span></span>

    - <span data-ttu-id="9ccd2-138">**Name der Webanwendung:** Geben Sie einen eindeutigen Namen für die Connector-Webanwendung an.</span><span class="sxs-lookup"><span data-stu-id="9ccd2-138">**Web App Name:** Provide a unique name for the connector web app.</span></span> <span data-ttu-id="9ccd2-139">Th Name muss zwischen 3 und 18 Zeichen lang sein.</span><span class="sxs-lookup"><span data-stu-id="9ccd2-139">Th name must be between 3 and 18 characters in length.</span></span> <span data-ttu-id="9ccd2-140">Dieser Name wird zum Erstellen der Azure-App-Dienst-URL verwendet. Wenn Sie beispielsweise den Namen der Webanwendung von **twitterconnector** angeben, wird die Azure-App-Dienst-URL **twitterconnector.azurewebsites.net**.</span><span class="sxs-lookup"><span data-stu-id="9ccd2-140">This name is used to create the Azure app service URL; for example, if you provide the Web app name of **twitterconnector** then the Azure app service URL  will be **twitterconnector.azurewebsites.net**.</span></span>
    
    - <span data-ttu-id="9ccd2-141">**Mandanten** -Nr: Die Mandanten-ID Ihrer Microsoft 365-Organisation, die Sie nach dem Erstellen der Facebook-Connector-app in Azure Active Directory in Schritt 1 kopiert haben.</span><span class="sxs-lookup"><span data-stu-id="9ccd2-141">**tenantId:** The tenant ID of your Microsoft 365 organization that you copied after creating the Facebook connector app in Azure       Active Directory in Step 1.</span></span>
    
   - <span data-ttu-id="9ccd2-142">**APISecretKey:** Sie können einen beliebigen Wert als geheimen Schlüssel eingeben.</span><span class="sxs-lookup"><span data-stu-id="9ccd2-142">**APISecretKey:** You can type any value as the secret.</span></span> <span data-ttu-id="9ccd2-143">Dies wird verwendet, um in Schritt 5 auf die Connector-Webanwendung zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="9ccd2-143">This is used to access the connector web app in Step 5.</span></span>

3. <span data-ttu-id="9ccd2-144">Nachdem die Bereitstellung erfolgreich war, sieht die Seite ähnlich wie der folgende Screenshot aus:</span><span class="sxs-lookup"><span data-stu-id="9ccd2-144">After the deployment is successful, the page will look similar to the following screenshot:</span></span>

    ![Klicken Sie auf Speicher, und klicken Sie dann auf Speicherkonto](media/FBCimage13.png)

## <a name="step-3-create-the-twitter-app"></a><span data-ttu-id="9ccd2-146">Schritt 3: Erstellen der Twitter-APP</span><span class="sxs-lookup"><span data-stu-id="9ccd2-146">Step 3: Create the Twitter app</span></span>

1. <span data-ttu-id="9ccd2-147">Wechseln Sie https://developer.twitter.comzu, melden Sie sich mit den Anmeldeinformationen für das Entwicklerkonto für Ihre Organisation an, und klicken Sie dann auf **apps**.</span><span class="sxs-lookup"><span data-stu-id="9ccd2-147">Go to https://developer.twitter.com, log in using the credentials for the developer account for your organization, and then click **Apps**.</span></span>

   ![Wechseln Sie https://developer.twitter.com zu und melden Sie sich an.](media/TCimage25-5.png)
2. <span data-ttu-id="9ccd2-149">Klicken Sie auf **app erstellen**.</span><span class="sxs-lookup"><span data-stu-id="9ccd2-149">Click **Create an app**.</span></span>
   
   ![Zur Seite "Apps" wechseln, um eine APP zu erstellen](media/TCimage26.png)

3. <span data-ttu-id="9ccd2-151">Fügen Sie unter **App-Details**Informationen zur Anwendung hinzu.</span><span class="sxs-lookup"><span data-stu-id="9ccd2-151">Under **App details**, add information about the application.</span></span>

   ![Eingeben von Informationen zur APP](media/TCimage27.png)

4. <span data-ttu-id="9ccd2-153">Wählen Sie im Twitter Developer Dashboard die soeben erstellte App aus, und kopieren Sie die angezeigte APP-ID, und speichern Sie Sie in einer Textdatei oder an einem anderen Speicherort.</span><span class="sxs-lookup"><span data-stu-id="9ccd2-153">On the Twitter developer dashboard, select the app that you just created and copy the App ID that's displayed  and save it to a text file or other storage location.</span></span> <span data-ttu-id="9ccd2-154">Klicken Sie dann auf **Details**.</span><span class="sxs-lookup"><span data-stu-id="9ccd2-154">Then click **Details**.</span></span>
   
   ![Kopieren und Speichern der APP-ID](media/TCimage28.png)

5. <span data-ttu-id="9ccd2-156">Kopieren Sie auf der Registerkarte **Schlüssel und Token** unter **Consumer-API-Schlüssel** den geheimen Schlüssel der API, und speichern Sie ihn in einer Textdatei oder an einem anderen Speicherort.</span><span class="sxs-lookup"><span data-stu-id="9ccd2-156">On the **Keys and tokens** tab, under **Consumer API keys** copy the API secret key and save it to a text file or other storage location.</span></span> <span data-ttu-id="9ccd2-157">Klicken Sie dann auf **Erstellen** , um ein Zugriffstoken und einen Zugriffstoken Schlüssel zu generieren, und kopieren Sie diese in eine Textdatei oder einen anderen Speicherort.</span><span class="sxs-lookup"><span data-stu-id="9ccd2-157">Then click **Create** to generate an access token and an access token secret, and copy these to a text file or other storage location.</span></span>
   
   ![Geheimer Schlüssel "Kopieren und speichern in API"](media/TCimage29.png)

   <span data-ttu-id="9ccd2-159">Klicken Sie dann auf **Erstellen** , um ein Zugriffstoken und einen Zugriffstoken Schlüssel zu generieren, und kopieren Sie diese in eine Textdatei oder einen anderen Speicherort.</span><span class="sxs-lookup"><span data-stu-id="9ccd2-159">Then click **Create** to generate an access token and an access token secret, and copy these to a text file or other storage location.</span></span>

6. <span data-ttu-id="9ccd2-160">Klicken Sie auf die Registerkarte **Berechtigungen** , und konfigurieren Sie die Berechtigungen wie im folgenden Screenshot dargestellt:</span><span class="sxs-lookup"><span data-stu-id="9ccd2-160">Click the **Permissions** tab and configure the permissions as shown in the following screenshot:</span></span>

   ![Konfigurieren von Berechtigungen](media/TCimage30.png)

7. <span data-ttu-id="9ccd2-162">Nachdem Sie die Berechtigungseinstellungen gespeichert haben, klicken Sie auf die Registerkarte **App-Details** , und klicken Sie dann auf **Bearbeiten #a0 bearbeiten von Details**.</span><span class="sxs-lookup"><span data-stu-id="9ccd2-162">After you save the permission settings, click the **App details** tab, and then click **Edit > Edit details**.</span></span>

   ![Bearbeiten der App-Details](media/TCimage31.png)

8. <span data-ttu-id="9ccd2-164">Führen Sie die folgenden Aufgaben aus:</span><span class="sxs-lookup"><span data-stu-id="9ccd2-164">Do the following tasks:</span></span>

   - <span data-ttu-id="9ccd2-165">Aktivieren Sie das Kontrollkästchen, damit sich die Connector-App bei Twitter anmelden kann.</span><span class="sxs-lookup"><span data-stu-id="9ccd2-165">Select the checkbox to allow the connector app to sign in to Twitter.</span></span>
   
   - <span data-ttu-id="9ccd2-166">Fügen Sie den OAuth-Umleitungs-URI mit dem folgenden Format hinzu: \*\* \<connectorserviceuri>/views/twitteroauth\*\*, wobei der Wert von *connectorserviceuri* die Azure-App-Dienst-URL für Ihre Organisation ist. Beispiel: https://twitterconnector.azurewebsites.net/Views/TwitterOAuth.</span><span class="sxs-lookup"><span data-stu-id="9ccd2-166">Add the OAuth redirect Uri using the following format: **\<connectorserviceuri>/Views/TwitterOAuth**, where the value of *connectorserviceuri* is the Azure app service URL for your organization; for example, https://twitterconnector.azurewebsites.net/Views/TwitterOAuth.</span></span>

    ![Connector-App erlauben, sich bei Twitter anzumelden und OAuth-Umleitungs-URI hinzuzufügen](media/TCimage32.png)

<span data-ttu-id="9ccd2-168">Die Twitter-Entwickler-App ist jetzt einsatzfähig.</span><span class="sxs-lookup"><span data-stu-id="9ccd2-168">The Twitter developer app is now ready to use.</span></span>

## <a name="step-4-configure-the-connector-web-app"></a><span data-ttu-id="9ccd2-169">Schritt 4: Konfigurieren der Connector-Webanwendung</span><span class="sxs-lookup"><span data-stu-id="9ccd2-169">Step 4: Configure the connector web app</span></span> 

1. <span data-ttu-id="9ccd2-170">Wechseln Sie zu\<https://AzureAppResourceName>. azurewebsites.net (wobei **AzureAppResourceName** der Name Ihrer Azure-App-Ressource ist, die Sie in Schritt 4 benannt haben).</span><span class="sxs-lookup"><span data-stu-id="9ccd2-170">Go to https://\<AzureAppResourceName>.azurewebsites.net (where **AzureAppResourceName** is the name of your Azure app resource that you named in Step 4).</span></span> <span data-ttu-id="9ccd2-171">Wenn der Name beispielsweise **twitterconnector**lautet, wechseln Sie zu https://twitterconnector.azurewebsites.net.</span><span class="sxs-lookup"><span data-stu-id="9ccd2-171">For example, if the name is **twitterconnector**, go to https://twitterconnector.azurewebsites.net.</span></span> <span data-ttu-id="9ccd2-172">Die Startseite der APP sieht wie im folgenden Screenshot aus:</span><span class="sxs-lookup"><span data-stu-id="9ccd2-172">The home page of the app looks like the following screenshot:</span></span>

   ![Seite zur Azure-App-Ressource wechseln](media/FBCimage41.png)

2. <span data-ttu-id="9ccd2-174">Klicken Sie auf **Konfigurieren** , um eine Anmeldeseite anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="9ccd2-174">Click **Configure** to display a sign in page.</span></span>

   ![Klicken Sie auf konfigurieren, um die Anmeldeseite anzuzeigen.](media/FBCimage42.png)

3. <span data-ttu-id="9ccd2-176">Geben Sie in das Feld Mandanten-ID die Mandanten-ID ein, die Sie in Schritt 2 erhalten haben, oder fügen Sie Sie ein.</span><span class="sxs-lookup"><span data-stu-id="9ccd2-176">In the Tenant Id box, type or paste your tenant Id (that you obtained in Step 2).</span></span> <span data-ttu-id="9ccd2-177">Geben Sie in das Feld Kennwort den APISecretKey (den Sie in Schritt 2 erhalten haben) ein, oder fügen Sie ihn ein, und klicken Sie dann auf **Konfigurationseinstellungen festlegen** , um die Seite Konfigurationsdetails anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="9ccd2-177">In the password box, type or paste the APISecretKey (that you obtained in Step 2), and then click **Set Configuration Settings** to display the configuration details page.</span></span>

   ![Anmelden mithilfe der Mandanten-ID und des geheimen Schlüssels der API](media/TCimage35.png)

4. <span data-ttu-id="9ccd2-179">Geben Sie die folgenden Konfigurationseinstellungen ein:</span><span class="sxs-lookup"><span data-stu-id="9ccd2-179">Enter the following configuration settings</span></span> 

   - <span data-ttu-id="9ccd2-180">**Twitter-API-Schlüssel:** Die APP-ID für die Twitter-Anwendung, die Sie in Schritt 3 erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="9ccd2-180">**Twitter Api Key:** The app ID for the Twitter application that you created in Step 3.</span></span>
   
   - <span data-ttu-id="9ccd2-181">**Geheimer Twitter-API-Schlüssel:** Der geheime API-Schlüssel für die Twitter-Anwendung, die Sie in Schritt 3 erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="9ccd2-181">**Twitter Api Secret Key:** The API secret key for the Twitter application that you created in Step 3.</span></span>
   
   - <span data-ttu-id="9ccd2-182">**Twitter-Zugriffs Token:** Das Zugriffstoken, das Sie in Schritt 3 erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="9ccd2-182">**Twitter Access Token:** The access token that you created in Step 3.</span></span>
   
   - <span data-ttu-id="9ccd2-183">**Geheimer Twitter-Zugriffs Token:** Der geheime Zugriffstoken, den Sie in Schritt 3 erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="9ccd2-183">**Twitter Access Token Secret:** The access token secret that you created in Step 3.</span></span>
   
   - <span data-ttu-id="9ccd2-184">**Aad-Anwendungs-ID:** Die Anwendungs-ID für die Azure Active Directory-APP, die Sie in Schritt 1 erstellt haben</span><span class="sxs-lookup"><span data-stu-id="9ccd2-184">**AAD Application ID:** The application ID for the Azure Active Directory app that you created in Step 1</span></span>
   
   - <span data-ttu-id="9ccd2-185">**Aad-Anwendungsschlüssel:** Der Wert für den geheimen APISecretKey, den Sie in Schritt 1 erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="9ccd2-185">**AAD Application Secret:** The value for the APISecretKey secret that you created in Step 1.</span></span>

5. <span data-ttu-id="9ccd2-186">Klicken Sie auf **Speichern** , um die Verbindungseinstellungen zu speichern.</span><span class="sxs-lookup"><span data-stu-id="9ccd2-186">Click **Save** to save the connector settings.</span></span>

## <a name="step-5-set-up-a-twitter-connector-in-the-microsoft-365-compliance-center"></a><span data-ttu-id="9ccd2-187">Schritt 5: Einrichten eines Twitter-Konnektors im Microsoft 365 Compliance Center</span><span class="sxs-lookup"><span data-stu-id="9ccd2-187">Step 5: Set up a Twitter connector in the Microsoft 365 compliance center</span></span>

1. <span data-ttu-id="9ccd2-188">Wechseln Sie [https://compliance.microsoft.com](https://compliance.microsoft.com) zu, und klicken Sie dann im linken Navigationsbereich auf **Datenverbindungen** .</span><span class="sxs-lookup"><span data-stu-id="9ccd2-188">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com) and then click **Data connectors** in the left nav.</span></span>

2. <span data-ttu-id="9ccd2-189">Klicken Sie auf der Seite **Daten Konnektoren (Vorschau)** unter **Twitter**auf **Ansicht**.</span><span class="sxs-lookup"><span data-stu-id="9ccd2-189">On the **Data connectors (preview)** page under **Twitter**, click **View**.</span></span>

3. <span data-ttu-id="9ccd2-190">Klicken Sie auf der Seite **Twitter** auf **Connector hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="9ccd2-190">On the **Twitter** page, click **Add connector**.</span></span>

4. <span data-ttu-id="9ccd2-191">Klicken Sie auf der Seite **Nutzungsbedingungen** auf **annehmen**.</span><span class="sxs-lookup"><span data-stu-id="9ccd2-191">On the **Terms of service** page, click **Accept**.</span></span>

5. <span data-ttu-id="9ccd2-192">Geben Sie auf der Seite **Anmeldeinformationen für ihre Connector-app hinzufügen** die folgenden Informationen ein, und klicken Sie dann auf **Verbindung überprüfen**.</span><span class="sxs-lookup"><span data-stu-id="9ccd2-192">On the **Add credentials for your connector app** page, enter the following information and then click **Validate connection**.</span></span>

   ![Eingeben von Connector-App-Anmeldeinformationen](media/TCimage38.png)

    - <span data-ttu-id="9ccd2-194">Geben Sie im Feld **Name** einen Namen für den Connector ein, beispielsweise **Twitter help handle**.</span><span class="sxs-lookup"><span data-stu-id="9ccd2-194">In the **Name** box, type a name for the connector, such as **Twitter help handle**.</span></span>
    
    - <span data-ttu-id="9ccd2-195">Geben Sie im Feld **Connector-URL** die Azure-App-Dienst-URL ein, oder fügen Sie Sie ein. zum Beispiel `https://twitterconnector.azurewebsites.net`.</span><span class="sxs-lookup"><span data-stu-id="9ccd2-195">In the **Connector URL** box, type or paste the Azure app service URL; for example `https://twitterconnector.azurewebsites.net`.</span></span>
    
    - <span data-ttu-id="9ccd2-196">Geben Sie in das Feld **Kennwort** den Wert des APISecretKey ein, den Sie in Schritt 2 erstellt haben, oder fügen Sie ihn ein.</span><span class="sxs-lookup"><span data-stu-id="9ccd2-196">In the **Password** box, type or paste the value of the APISecretKey that you created in Step 2.</span></span>
    
    - <span data-ttu-id="9ccd2-197">Geben Sie in das Feld **Azure-APP-ID** den Wert der Azure Application-APP-ID (auch als *Client-ID*bezeichnet) ein, oder fügen Sie ihn ein, den Sie in Schritt 1 erhalten haben.</span><span class="sxs-lookup"><span data-stu-id="9ccd2-197">In the **Azure App ID** box, type or paste the value of the Azure Application App Id (also called the *client ID*) that you obtained in Step 1.</span></span>

6. <span data-ttu-id="9ccd2-198">Nachdem die Verbindung erfolgreich überprüft wurde, klicken Sie auf **weiter**.</span><span class="sxs-lookup"><span data-stu-id="9ccd2-198">After the connection is successfully validated, click **Next**.</span></span>

7. <span data-ttu-id="9ccd2-199">Geben Sie auf der Seite **Microsoft 365 zum Importieren von Daten autorisieren** den APISecretKey erneut ein, oder fügen Sie ihn ein, und klicken Sie dann auf **Login-webapp**.</span><span class="sxs-lookup"><span data-stu-id="9ccd2-199">On the **Authorize Microsoft 365 to import data** page, type or paste the APISecretKey again and then click  **Login web app**.</span></span>

8. <span data-ttu-id="9ccd2-200">Klicken Sie auf **Login mit Twitter**.</span><span class="sxs-lookup"><span data-stu-id="9ccd2-200">Click **Login with Twitter**.</span></span>

9. <span data-ttu-id="9ccd2-201">Melden Sie sich auf der Twitter-Anmeldeseite mit den Anmeldeinformationen für das Twitter-Konto Ihrer Organisation an.</span><span class="sxs-lookup"><span data-stu-id="9ccd2-201">On the Twitter sign in page, sign in using the credentials for your organization’s Twitter account.</span></span>

   ![Bei Twitter-Konto anmelden](media/TCimage42.png)

   <span data-ttu-id="9ccd2-203">Nachdem Sie sich angemeldet haben, wird auf der Twitter-Seite die folgende Meldung angezeigt: "Twitter Connector-Auftrag erfolgreich eingerichtet."</span><span class="sxs-lookup"><span data-stu-id="9ccd2-203">After you sign in, the Twitter page will display the following message, "Twitter Connector Job Successfully set up."</span></span>

10. <span data-ttu-id="9ccd2-204">Klicken Sie auf **weiter** , um die Einrichtung des Twitter-Konnektors abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="9ccd2-204">Click **Continue** to complete setting up the Twitter connector.</span></span>

11. <span data-ttu-id="9ccd2-205">Auf der Seite **Filter festlegen** können Sie einen Filter anwenden, um Elemente anfänglich zu importieren, die ein bestimmtes Alter aufweisen.</span><span class="sxs-lookup"><span data-stu-id="9ccd2-205">On the **Set filters** page, you can apply a filter to initially import items that are a certain age.</span></span> <span data-ttu-id="9ccd2-206">Wählen Sie ein Alter aus, und klicken Sie dann auf **weiter**.</span><span class="sxs-lookup"><span data-stu-id="9ccd2-206">Select an age, and then click **Next**.</span></span>

12. <span data-ttu-id="9ccd2-207">Geben Sie auf der Seite Speicherort **auswählen** die e-Mail-Adresse des Microsoft 365-Postfachs ein, in das die Twitter-Elemente importiert werden sollen, und klicken Sie dann auf **weiter**.</span><span class="sxs-lookup"><span data-stu-id="9ccd2-207">On the **Choose storage location** page, type the email address of Microsoft 365 mailbox that the Twitter items will be imported to, and then click **Next**.</span></span>

13. <span data-ttu-id="9ccd2-208">Klicken Sie im die **Zustimmung des Administrators bereit**stellen auf **Zustimmung erteilen** , und führen Sie dann die Schritte aus.</span><span class="sxs-lookup"><span data-stu-id="9ccd2-208">On the **Provide admin consent**, click **Provide consent** and then follow the steps.</span></span> <span data-ttu-id="9ccd2-209">Sie müssen ein globaler Administrator sein, um die Zustimmung des Office 365-Import Diensts für den Zugriff auf Daten in Ihrer Organisation zu geben.</span><span class="sxs-lookup"><span data-stu-id="9ccd2-209">You must be a global admin to provide consent for the Office 365 Import service to access data in your organization.</span></span>

14. <span data-ttu-id="9ccd2-210">Klicken Sie auf **weiter** , um die Connectoreinstellungen zu überprüfen, und klicken Sie dann auf **Fertig stellen** , um das Connector-Setup abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="9ccd2-210">Click **Next** to review the connector settings and then click **Finish** to complete the connector setup.</span></span>

15. <span data-ttu-id="9ccd2-211">Wechseln Sie im Compliance Center zur Seite **Daten Konnektoren** , und klicken Sie auf die Registerkarte **Connectors** , um den Status des Importvorgangs anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="9ccd2-211">In the compliance center, go to the **Data connectors** page, and click the **Connectors** tab to see the progress of the import process.</span></span>
