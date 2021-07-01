---
title: Bereitstellen eines Connectors zum Archivieren von Twitter-Daten
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
description: Administratoren können einen systemeigenen Connector einrichten, um Twitter-Daten zu importieren und in Microsoft 365 zu archivieren. Nachdem diese Daten in Microsoft 365 importiert wurden, können Sie Compliance-Features wie gesetzliche Aufbewahrung, Inhaltssuche und Aufbewahrungsrichtlinien verwenden, um die Governance der Twitter-Daten Ihrer Organisation zu verwalten.
ms.openlocfilehash: 0a0ebb18cb39b7dd7416f2d03dcb5b4d21332c9b
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/30/2021
ms.locfileid: "53227055"
---
# <a name="deploy-a-connector-to-archive-twitter-data"></a><span data-ttu-id="de9ac-104">Bereitstellen eines Connectors zum Archivieren von Twitter-Daten</span><span class="sxs-lookup"><span data-stu-id="de9ac-104">Deploy a connector to archive Twitter data</span></span>

<span data-ttu-id="de9ac-105">Dieser Artikel enthält den schrittweisen Prozess zum Bereitstellen eines Connectors, der den Office 365 Importdienst verwendet, um Daten aus dem Twitter-Konto Ihrer Organisation in Microsoft 365 zu importieren.</span><span class="sxs-lookup"><span data-stu-id="de9ac-105">This article contains the step-by-step process to deploy a connector that uses the Office 365 Import service to import data from your organization's Twitter account to Microsoft 365.</span></span> <span data-ttu-id="de9ac-106">Eine allgemeine Übersicht über diesen Prozess und eine Liste der erforderlichen Komponenten für die Bereitstellung eines Twitter-Connectors finden Sie unter ["Einrichten eines Connectors zum Archivieren von Twitter-Daten". ](archive-twitter-data-with-sample-connector.md)</span><span class="sxs-lookup"><span data-stu-id="de9ac-106">For a high-level overview of this process and a list of prerequisites required to deploy a Twitter connector, see [Set up a connector to archive Twitter data ](archive-twitter-data-with-sample-connector.md).</span></span>

## <a name="step-1-create-an-app-in-azure-active-directory"></a><span data-ttu-id="de9ac-107">Schritt 1: Erstellen einer App in Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="de9ac-107">Step 1: Create an app in Azure Active Directory</span></span>

1. <span data-ttu-id="de9ac-108">Rufen Sie <https://portal.azure.com> die Anmeldeinformationen eines globalen Administratorkontos auf, und melden Sie sich an.</span><span class="sxs-lookup"><span data-stu-id="de9ac-108">Go to <https://portal.azure.com> and sign in using the credentials of a global admin account.</span></span>

   ![Anmelden bei Azure](../media/TCimage01.png)

2. <span data-ttu-id="de9ac-110">Klicken Sie im linken Navigationsbereich auf **Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="de9ac-110">In the left navigation pane, click **Azure Active Directory**.</span></span>

   ![Wechseln Sie zu Azure Active Directory](../media/TCimage02.png)

3. <span data-ttu-id="de9ac-112">Klicken Sie im linken Navigationsbereich auf **App-Registrierungen (Vorschau),** und klicken Sie dann auf **"Neue Registrierung".**</span><span class="sxs-lookup"><span data-stu-id="de9ac-112">In the left navigation pane, click **App registrations (Preview)** and then click **New registration**.</span></span>

   ![Erstellen einer neuen App-Registrierung](../media/TCimage03.png)

4. <span data-ttu-id="de9ac-114">Registrieren Sie die Anwendung.</span><span class="sxs-lookup"><span data-stu-id="de9ac-114">Register the application.</span></span> <span data-ttu-id="de9ac-115">Wählen Sie unter **Umleitungs-URI (optional)** in der Dropdownliste für den Anwendungstyp **"Web"** aus, und geben Sie dann `https://portal.azure.com` das Feld für den URI ein.</span><span class="sxs-lookup"><span data-stu-id="de9ac-115">Under **Redirect URI (optional)**, select **Web** in the application type dropdown list and then type `https://portal.azure.com` in the box for the URI.</span></span>

   ![Typ https://portal.azure.com für den Umleitungs-URI](../media/TCimage04.png)

5. <span data-ttu-id="de9ac-117">Kopieren Sie die **Anwendungs-ID (Client)-ID** und **die Verzeichnis-ID (Mandanten-ID),** und speichern Sie sie in einer Textdatei oder an einem anderen sicheren Speicherort.</span><span class="sxs-lookup"><span data-stu-id="de9ac-117">Copy the **Application (client) ID** and **Directory (tenant) ID** and save them to a text file or other safe location.</span></span> <span data-ttu-id="de9ac-118">Sie verwenden diese IDs in späteren Schritten.</span><span class="sxs-lookup"><span data-stu-id="de9ac-118">You use these IDs in later steps.</span></span>

    ![Kopieren und Speichern der Anwendungs- und Verzeichnis-ID](../media/TCimage05.png)

6. <span data-ttu-id="de9ac-120">Wechseln Sie zu **Zertifikate & geheimen Schlüssel für die neue App,** und klicken Sie unter **"Geheime Clientschlüssel"** auf **"Neuer geheimer Clientschlüssel".**</span><span class="sxs-lookup"><span data-stu-id="de9ac-120">Go to **Certificates & secrets for the new app** and under **Client secrets** click **New client secret**.</span></span>

   ![Erstellen eines neuen geheimen Clientschlüssels](../media/TCimage06.png)

7. <span data-ttu-id="de9ac-122">Erstellen Sie einen neuen geheimen Schlüssel.</span><span class="sxs-lookup"><span data-stu-id="de9ac-122">Create a new secret.</span></span> <span data-ttu-id="de9ac-123">Geben Sie im Beschreibungsfeld den geheimen Schlüssel ein, und wählen Sie dann einen Ablaufzeitraum aus.</span><span class="sxs-lookup"><span data-stu-id="de9ac-123">In the description box, type the secret and then choose an expiration period.</span></span>

   ![Geben Sie den geheimen Schlüssel ein, und wählen Sie den Ablaufzeitraum aus.](../media/TCimage08.png)

8. <span data-ttu-id="de9ac-125">Kopieren Sie den Wert des geheimen Schlüssels, und speichern Sie ihn in einer Textdatei oder an einem anderen Speicherort.</span><span class="sxs-lookup"><span data-stu-id="de9ac-125">Copy the value of the secret and save it to a text file or other storage location.</span></span> <span data-ttu-id="de9ac-126">Dies ist der geheime AAD-Anwendungsschlüssel, den Sie in späteren Schritten verwenden.</span><span class="sxs-lookup"><span data-stu-id="de9ac-126">This is the AAD application secret that you use in later steps.</span></span>

   ![Kopieren und Speichern des geheimen Schlüssels](../media/TCimage09.png)


## <a name="step-2-deploy-the-connector-web-service-from-github-to-your-azure-account"></a><span data-ttu-id="de9ac-128">Schritt 2: Bereitstellen des Connectorwebdiensts von GitHub auf Ihrem Azure-Konto</span><span class="sxs-lookup"><span data-stu-id="de9ac-128">Step 2: Deploy the connector web service from GitHub to your Azure account</span></span>

1. <span data-ttu-id="de9ac-129">Wechseln Sie zu [dieser GitHub Website,](https://github.com/microsoft/m365-sample-twitter-connector-csharp-aspnet) und klicken Sie auf **"Bereitstellen in Azure".**</span><span class="sxs-lookup"><span data-stu-id="de9ac-129">Go to [this GitHub site](https://github.com/microsoft/m365-sample-twitter-connector-csharp-aspnet) and click **Deploy to Azure**.</span></span>

    ![Wechseln Sie zur Azure-Startseite](../media/FBCimage11.png)

2. <span data-ttu-id="de9ac-131">Nachdem Sie auf **"Bereitstellen in Azure"** geklickt haben, werden Sie mit einer benutzerdefinierten Vorlagenseite zu einem Azure-Portal umgeleitet.</span><span class="sxs-lookup"><span data-stu-id="de9ac-131">After you click **Deploy to Azure**, you will be redirected to an Azure portal with a custom template page.</span></span> <span data-ttu-id="de9ac-132">Geben Sie die **Grundlagen** und **Einstellungen** Details ein, und klicken Sie dann auf **"Kaufen".**</span><span class="sxs-lookup"><span data-stu-id="de9ac-132">Fill in the **Basics** and **Settings** details and then click **Purchase**.</span></span>

   ![Klicken Sie auf "Ressource erstellen" und geben Sie "Speicherkonto" ein.](../media/FBCimage12.png)

    - <span data-ttu-id="de9ac-134">**Abonnement:** Wählen Sie Ihr Azure-Abonnement aus, in dem Sie den Twitter Connector-Webdienst bereitstellen möchten.</span><span class="sxs-lookup"><span data-stu-id="de9ac-134">**Subscription:** Select your Azure subscription that you want to deploy the Twitter connector web service to.</span></span>

    - <span data-ttu-id="de9ac-135">**Ressourcengruppe:** Wählen Oder erstellen Sie eine neue Ressourcengruppe.</span><span class="sxs-lookup"><span data-stu-id="de9ac-135">**Resource group:** Choose or create a new resource group.</span></span> <span data-ttu-id="de9ac-136">Eine Ressourcengruppe ist ein Container, der verwandte Ressourcen für eine Azure-Lösung enthält.</span><span class="sxs-lookup"><span data-stu-id="de9ac-136">A resource group is a container that holds related resources for an Azure solution.</span></span>

    - <span data-ttu-id="de9ac-137">**Speicherort:** Wählen Sie einen Speicherort aus.</span><span class="sxs-lookup"><span data-stu-id="de9ac-137">**Location:** Choose a location.</span></span>

    - <span data-ttu-id="de9ac-138">**Name der Web-App:** Geben Sie einen eindeutigen Namen für die Connector-Web-App an.</span><span class="sxs-lookup"><span data-stu-id="de9ac-138">**Web App Name:** Provide a unique name for the connector web app.</span></span> <span data-ttu-id="de9ac-139">Der Name muss zwischen 3 und 18 Zeichen lang sein.</span><span class="sxs-lookup"><span data-stu-id="de9ac-139">Th name must be between 3 and 18 characters in length.</span></span> <span data-ttu-id="de9ac-140">Dieser Name wird zum Erstellen der Azure-App-Dienst-URL verwendet. Wenn Sie beispielsweise den Web-App-Namen von **twitterconnector** angeben, wird die URL des Azure-App-Diensts **twitterconnector.azurewebsites.net.**</span><span class="sxs-lookup"><span data-stu-id="de9ac-140">This name is used to create the Azure app service URL; for example, if you provide the Web app name of **twitterconnector** then the Azure app service URL  will be **twitterconnector.azurewebsites.net**.</span></span>

    - <span data-ttu-id="de9ac-141">**tenantId:** Die Mandanten-ID Ihrer Microsoft 365 Organisation, die Sie nach dem Erstellen der Facebook-Connector-App in Azure Active Directory in Schritt 1 kopiert haben.</span><span class="sxs-lookup"><span data-stu-id="de9ac-141">**tenantId:** The tenant ID of your Microsoft 365 organization that you copied after creating the Facebook connector app in Azure       Active Directory in Step 1.</span></span>

   - <span data-ttu-id="de9ac-142">**APISecretKey:** Sie können einen beliebigen Wert als geheimen Schlüssel eingeben.</span><span class="sxs-lookup"><span data-stu-id="de9ac-142">**APISecretKey:** You can type any value as the secret.</span></span> <span data-ttu-id="de9ac-143">Dies wird verwendet, um auf die Connector-Web-App in Schritt 5 zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="de9ac-143">This is used to access the connector web app in Step 5.</span></span>

3. <span data-ttu-id="de9ac-144">Nachdem die Bereitstellung erfolgreich war, sieht die Seite ähnlich wie im folgenden Screenshot aus:</span><span class="sxs-lookup"><span data-stu-id="de9ac-144">After the deployment is successful, the page will look similar to the following screenshot:</span></span>

    ![Klicken Sie auf Storage und dann auf Storage Konto.](../media/FBCimage13.png)

## <a name="step-3-create-the-twitter-app"></a><span data-ttu-id="de9ac-146">Schritt 3: Erstellen der Twitter-App</span><span class="sxs-lookup"><span data-stu-id="de9ac-146">Step 3: Create the Twitter app</span></span>

1. <span data-ttu-id="de9ac-147">Wechseln Sie zu https://developer.twitter.com , melden Sie sich mit den Anmeldeinformationen für das Entwicklerkonto für Ihre Organisation an, und klicken Sie dann auf **"Apps".**</span><span class="sxs-lookup"><span data-stu-id="de9ac-147">Go to https://developer.twitter.com, log in using the credentials for the developer account for your organization, and then click **Apps**.</span></span>

   ![Wechseln sie zu https://developer.twitter.com und melden Sie sich an](../media/TCimage25-5.png)
2. <span data-ttu-id="de9ac-149">Klicken Sie auf **"App erstellen".**</span><span class="sxs-lookup"><span data-stu-id="de9ac-149">Click **Create an app**.</span></span>

   ![Wechseln Sie zur Seite "Apps", um eine App zu erstellen.](../media/TCimage26.png)

3. <span data-ttu-id="de9ac-151">Fügen Sie unter **App-Details** Informationen zur Anwendung hinzu.</span><span class="sxs-lookup"><span data-stu-id="de9ac-151">Under **App details**, add information about the application.</span></span>

   ![Eingeben von Informationen zur App](../media/TCimage27.png)

4. <span data-ttu-id="de9ac-153">Wählen Sie im Twitter-Entwicklerdashboard die App aus, die Sie soeben erstellt haben, und klicken Sie dann auf **"Details".**</span><span class="sxs-lookup"><span data-stu-id="de9ac-153">On the Twitter developer dashboard, select the app that you just created and then click **Details**.</span></span>

   ![Kopieren und Speichern der App-ID](../media/TCimage28.png)

5. <span data-ttu-id="de9ac-155">Kopieren Sie auf der Registerkarte **"Schlüssel und Token"** unter **"Consumer-API-Schlüssel"** sowohl den API-Schlüssel als auch den geheimen API-Schlüssel, und speichern Sie sie in einer Textdatei oder an einem anderen Speicherort.</span><span class="sxs-lookup"><span data-stu-id="de9ac-155">On the **Keys and tokens** tab, under **Consumer API keys** copy both the API Key and the API secret key and save them to a text file or other storage location.</span></span> <span data-ttu-id="de9ac-156">Klicken Sie dann auf **"Erstellen",** um ein Zugriffstoken und einen geheimen Zugriffstokenschlüssel zu generieren und diese in eine Textdatei oder einen anderen Speicherort zu kopieren.</span><span class="sxs-lookup"><span data-stu-id="de9ac-156">Then click **Create** to generate an access token and access token secret and copy these to a text file or other storage location.</span></span>

   ![Kopieren und Speichern in den geheimen API-Schlüssel](../media/TCimage29.png)

   <span data-ttu-id="de9ac-158">Klicken Sie dann auf **"Erstellen",** um ein Zugriffstoken und einen geheimen Zugriffstokenschlüssel zu generieren, und kopieren Sie diese in eine Textdatei oder einen anderen Speicherort.</span><span class="sxs-lookup"><span data-stu-id="de9ac-158">Then click **Create** to generate an access token and an access token secret, and copy these to a text file or other storage location.</span></span>

6. <span data-ttu-id="de9ac-159">Klicken Sie auf die Registerkarte **"Berechtigungen",** und konfigurieren Sie die Berechtigungen wie im folgenden Screenshot dargestellt:</span><span class="sxs-lookup"><span data-stu-id="de9ac-159">Click the **Permissions** tab and configure the permissions as shown in the following screenshot:</span></span>

   ![Konfigurieren von Berechtigungen](../media/TCimage30.png)

7. <span data-ttu-id="de9ac-161">Klicken Sie nach dem Speichern der Berechtigungseinstellungen auf die Registerkarte **"App-Details"** und dann auf **"Bearbeiten > Details bearbeiten".**</span><span class="sxs-lookup"><span data-stu-id="de9ac-161">After you save the permission settings, click the **App details** tab, and then click **Edit > Edit details**.</span></span>

   ![Bearbeiten der App-Details](../media/TCimage31.png)

8. <span data-ttu-id="de9ac-163">Führen Sie die folgenden Aufgaben aus:</span><span class="sxs-lookup"><span data-stu-id="de9ac-163">Do the following tasks:</span></span>

   - <span data-ttu-id="de9ac-164">Aktivieren Sie das Kontrollkästchen, damit sich die Connector-App bei Twitter anmelden kann.</span><span class="sxs-lookup"><span data-stu-id="de9ac-164">Select the checkbox to allow the connector app to sign in to Twitter.</span></span>

   - <span data-ttu-id="de9ac-165">Fügen Sie den OAuth-Umleitungs-URI mit dem folgenden Format hinzu: **\<connectorserviceuri> /Views/TwitterOAuth**, wobei der Wert von *connectorserviceuri* die AZURE-App-Dienst-URL für Ihre Organisation ist, z. https://twitterconnector.azurewebsites.net/Views/TwitterOAuth B. .</span><span class="sxs-lookup"><span data-stu-id="de9ac-165">Add the OAuth redirect Uri using the following format: **\<connectorserviceuri>/Views/TwitterOAuth**, where the value of *connectorserviceuri* is the Azure app service URL for your organization; for example, https://twitterconnector.azurewebsites.net/Views/TwitterOAuth.</span></span>

    ![Zulassen, dass sich die Connector-App bei Twitter anmeldet und OAuth-Umleitungs-URI hinzufüge](../media/TCimage32.png)

<span data-ttu-id="de9ac-167">Die Twitter-Entwickler-App kann jetzt verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="de9ac-167">The Twitter developer app is now ready to use.</span></span>

## <a name="step-4-configure-the-connector-web-app"></a><span data-ttu-id="de9ac-168">Schritt 4: Konfigurieren der Connector-Web-App</span><span class="sxs-lookup"><span data-stu-id="de9ac-168">Step 4: Configure the connector web app</span></span>

1. <span data-ttu-id="de9ac-169">Wechseln Sie zu https:// \<AzureAppResourceName> .azurewebsites.net (wobei **AzureAppResourceName** der Name Ihrer Azure-App-Ressource ist, die Sie in Schritt 4 benannt haben).</span><span class="sxs-lookup"><span data-stu-id="de9ac-169">Go to https://\<AzureAppResourceName>.azurewebsites.net (where **AzureAppResourceName** is the name of your Azure app resource that you named in Step 4).</span></span> <span data-ttu-id="de9ac-170">Wenn der Name z. B. **twitterconnector** ist, wechseln Sie zu https://twitterconnector.azurewebsites.net .</span><span class="sxs-lookup"><span data-stu-id="de9ac-170">For example, if the name is **twitterconnector**, go to https://twitterconnector.azurewebsites.net.</span></span> <span data-ttu-id="de9ac-171">Die Startseite der App sieht wie im folgenden Screenshot aus:</span><span class="sxs-lookup"><span data-stu-id="de9ac-171">The home page of the app looks like the following screenshot:</span></span>

   ![Zur Ressourcenseite der Azure-App wechseln](../media/FBCimage41.png)

2. <span data-ttu-id="de9ac-173">Klicken Sie auf **"Konfigurieren",** um eine Anmeldeseite anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="de9ac-173">Click **Configure** to display a sign in page.</span></span>

   ![Klicken Sie auf "Konfigurieren" zum Anzeigen der Anmeldeseite.](../media/FBCimage42.png)

3. <span data-ttu-id="de9ac-175">Geben Sie im Feld "Mandanten-ID" Ihre Mandanten-ID (die Sie in Schritt 2 abgerufen haben) ein, oder fügen Sie sie ein.</span><span class="sxs-lookup"><span data-stu-id="de9ac-175">In the Tenant Id box, type or paste your tenant Id (that you obtained in Step 2).</span></span> <span data-ttu-id="de9ac-176">Geben Sie im Kennwortfeld den APISecretKey (den Sie in Schritt 2 erhalten haben) ein, oder fügen Sie ihn ein, und klicken Sie dann auf **"Konfiguration festlegen" Einstellungen,** um die Seite mit den Konfigurationsdetails anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="de9ac-176">In the password box, type or paste the APISecretKey (that you obtained in Step 2), and then click **Set Configuration Settings** to display the configuration details page.</span></span>

   ![Melden Sie sich mit der Mandanten-ID und dem geheimen API-Schlüssel an](../media/TCimage35.png)

4. <span data-ttu-id="de9ac-178">Geben Sie die folgenden Konfigurationseinstellungen ein:</span><span class="sxs-lookup"><span data-stu-id="de9ac-178">Enter the following configuration settings</span></span>

   - <span data-ttu-id="de9ac-179">**Twitter-API-Schlüssel:** Der API-Schlüssel für die Twitter-Anwendung, die Sie in Schritt 3 erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="de9ac-179">**Twitter Api Key:** The API key for the Twitter application that you created in Step 3.</span></span>

   - <span data-ttu-id="de9ac-180">**Geheimer Twitter-Api-Schlüssel:** Der geheime API-Schlüssel für die Twitter-Anwendung, die Sie in Schritt 3 erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="de9ac-180">**Twitter Api Secret Key:** The API secret key for the Twitter application that you created in Step 3.</span></span>

   - <span data-ttu-id="de9ac-181">**Twitter-Zugriffstoken:** Das Zugriffstoken, das Sie in Schritt 3 erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="de9ac-181">**Twitter Access Token:** The access token that you created in Step 3.</span></span>

   - <span data-ttu-id="de9ac-182">**Geheimer Twitter-Zugriffstokenschlüssel:** Der geheime Zugriffstokenschlüssel, den Sie in Schritt 3 erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="de9ac-182">**Twitter Access Token Secret:** The access token secret that you created in Step 3.</span></span>

   - <span data-ttu-id="de9ac-183">**AAD-Anwendungs-ID:** Die Anwendungs-ID für die Azure Active Directory App, die Sie in Schritt 1 erstellt haben</span><span class="sxs-lookup"><span data-stu-id="de9ac-183">**AAD Application ID:** The application ID for the Azure Active Directory app that you created in Step 1</span></span>

   - <span data-ttu-id="de9ac-184">**Geheimer AAD-Anwendungsschlüssel:** Der Wert für den geheimen APISecretKey-Schlüssel, den Sie in Schritt 1 erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="de9ac-184">**AAD Application Secret:** The value for the APISecretKey secret that you created in Step 1.</span></span>

5. <span data-ttu-id="de9ac-185">Klicken Sie auf **"Speichern",** um die Connectoreinstellungen zu speichern.</span><span class="sxs-lookup"><span data-stu-id="de9ac-185">Click **Save** to save the connector settings.</span></span>

## <a name="step-5-set-up-a-twitter-connector-in-the-microsoft-365-compliance-center"></a><span data-ttu-id="de9ac-186">Schritt 5: Einrichten eines Twitter-Connectors im Microsoft 365 Compliance Center</span><span class="sxs-lookup"><span data-stu-id="de9ac-186">Step 5: Set up a Twitter connector in the Microsoft 365 compliance center</span></span>

1. <span data-ttu-id="de9ac-187">Wechseln Sie zu [https://compliance.microsoft.com](https://compliance.microsoft.com) und klicken Sie dann im linken Navigationsbereich auf **Datenconnectors.**</span><span class="sxs-lookup"><span data-stu-id="de9ac-187">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com) and then click **Data connectors** in the left nav.</span></span>

2. <span data-ttu-id="de9ac-188">Klicken Sie auf der Seite **"Datenconnectors"** unter **Twitter** auf **"Anzeigen".**</span><span class="sxs-lookup"><span data-stu-id="de9ac-188">On the **Data connectors** page under **Twitter**, click **View**.</span></span>

3. <span data-ttu-id="de9ac-189">Klicken Sie auf der **Twitter-Seite** auf **Connector hinzufügen.**</span><span class="sxs-lookup"><span data-stu-id="de9ac-189">On the **Twitter** page, click **Add connector**.</span></span>

4. <span data-ttu-id="de9ac-190">Klicken Sie auf der Seite **"Nutzungsbedingungen"** auf **"Annehmen".**</span><span class="sxs-lookup"><span data-stu-id="de9ac-190">On the **Terms of service** page, click **Accept**.</span></span>

5. <span data-ttu-id="de9ac-191">Geben Sie auf der Seite **"Anmeldeinformationen für Ihre Connector-App hinzufügen"** die folgenden Informationen ein, und klicken Sie dann auf **"Verbindung überprüfen".**</span><span class="sxs-lookup"><span data-stu-id="de9ac-191">On the **Add credentials for your connector app** page, enter the following information and then click **Validate connection**.</span></span>

   ![Eingeben von Connector-App-Anmeldeinformationen](../media/TCimage38.png)

    - <span data-ttu-id="de9ac-193">Geben Sie im **Feld "Name"** einen Namen für den Connector ein, **z. B. die Twitter-Hilfebehandlung.**</span><span class="sxs-lookup"><span data-stu-id="de9ac-193">In the **Name** box, type a name for the connector, such as **Twitter help handle**.</span></span>

    - <span data-ttu-id="de9ac-194">Geben Sie im **Feld "Connector-URL"** die URL des Azure-App-Diensts ein, oder fügen Sie sie ein. Beispiel: `https://twitterconnector.azurewebsites.net` .</span><span class="sxs-lookup"><span data-stu-id="de9ac-194">In the **Connector URL** box, type or paste the Azure app service URL; for example `https://twitterconnector.azurewebsites.net`.</span></span>

    - <span data-ttu-id="de9ac-195">Geben Sie im **Feld "Kennwort"** den Wert des APISecretKey ein, den Sie in Schritt 2 erstellt haben, oder fügen Sie ihn ein.</span><span class="sxs-lookup"><span data-stu-id="de9ac-195">In the **Password** box, type or paste the value of the APISecretKey that you created in Step 2.</span></span>

    - <span data-ttu-id="de9ac-196">Geben Sie im **Feld "Azure-App-ID"** den Wert der Azure-Anwendungs-App-ID (auch *client-ID* genannt) ein, die Sie in Schritt 1 abgerufen haben, oder fügen Sie ihn ein.</span><span class="sxs-lookup"><span data-stu-id="de9ac-196">In the **Azure App ID** box, type or paste the value of the Azure Application App Id (also called the *client ID*) that you obtained in Step 1.</span></span>

6. <span data-ttu-id="de9ac-197">Nachdem die Verbindung erfolgreich überprüft wurde, klicken Sie auf **"Weiter".**</span><span class="sxs-lookup"><span data-stu-id="de9ac-197">After the connection is successfully validated, click **Next**.</span></span>

7. <span data-ttu-id="de9ac-198">Geben Sie auf der **Seite "Autorisieren Microsoft 365 zum Importieren** von Daten" den APISecretKey erneut ein, oder fügen Sie ihn ein, und klicken Sie dann auf **"Web-App anmelden".**</span><span class="sxs-lookup"><span data-stu-id="de9ac-198">On the **Authorize Microsoft 365 to import data** page, type or paste the APISecretKey again and then click  **Login web app**.</span></span>

8. <span data-ttu-id="de9ac-199">Klicken Sie auf **"Mit Twitter anmelden".**</span><span class="sxs-lookup"><span data-stu-id="de9ac-199">Click **Login with Twitter**.</span></span>

9. <span data-ttu-id="de9ac-200">Melden Sie sich auf der Twitter-Anmeldeseite mit den Anmeldeinformationen für das Twitter-Konto Ihrer Organisation an.</span><span class="sxs-lookup"><span data-stu-id="de9ac-200">On the Twitter sign in page, sign in using the credentials for your organization's Twitter account.</span></span>

   ![Anmelden bei Twitter-Konto](../media/TCimage42.png)

   <span data-ttu-id="de9ac-202">Nach der Anmeldung wird auf der Twitter-Seite die folgende Meldung angezeigt: "Twitter Connector Job Successfully set up".</span><span class="sxs-lookup"><span data-stu-id="de9ac-202">After you sign in, the Twitter page will display the following message, "Twitter Connector Job Successfully set up."</span></span>

10. <span data-ttu-id="de9ac-203">Klicken Sie auf **"Weiter",** um die Einrichtung des Twitter-Connectors abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="de9ac-203">Click **Continue** to complete setting up the Twitter connector.</span></span>

11. <span data-ttu-id="de9ac-204">Auf der Seite **"Filter festlegen"** können Sie einen Filter anwenden, um zunächst Elemente mit einem bestimmten Alter zu importieren.</span><span class="sxs-lookup"><span data-stu-id="de9ac-204">On the **Set filters** page, you can apply a filter to initially import items that are a certain age.</span></span> <span data-ttu-id="de9ac-205">Wählen Sie ein Alter aus, und klicken Sie dann auf **"Weiter".**</span><span class="sxs-lookup"><span data-stu-id="de9ac-205">Select an age, and then click **Next**.</span></span>

12. <span data-ttu-id="de9ac-206">Geben Sie auf der Seite **"Speicherort auswählen"** die E-Mail-Adresse Microsoft 365 Postfach ein, in das die Twitter-Elemente importiert werden, und klicken Sie dann auf **"Weiter".**</span><span class="sxs-lookup"><span data-stu-id="de9ac-206">On the **Choose storage location** page, type the email address of Microsoft 365 mailbox that the Twitter items will be imported to, and then click **Next**.</span></span>

13. <span data-ttu-id="de9ac-207">Klicken Sie auf **"Weiter",** um die Connectoreinstellungen zu überprüfen, und klicken Sie dann auf **"Fertig stellen",** um die Connectoreinrichtung abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="de9ac-207">Click **Next** to review the connector settings and then click **Finish** to complete the connector setup.</span></span>

14. <span data-ttu-id="de9ac-208">Wechseln Sie im Compliance Center zur Seite **"Datenconnectors",** und klicken Sie auf die Registerkarte **"Connectors",** um den Fortschritt des Importvorgangs anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="de9ac-208">In the compliance center, go to the **Data connectors** page, and click the **Connectors** tab to see the progress of the import process.</span></span>
