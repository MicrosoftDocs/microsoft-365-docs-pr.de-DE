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
description: Administratoren können einen systemeigenen Connector zum Importieren und Archivieren von Twitter-Daten in Office 365 einrichten. Nachdem diese Daten in Office 365 importiert wurden, können Sie Compliance-Features wie Legal Hold, Inhaltssuche und Aufbewahrungsrichtlinien verwenden, um die Steuerung der Twitter-Daten Ihrer Organisation zu verwalten.
ms.openlocfilehash: ee15086c6389fa2d2e7d07412ab533301cd8a842
ms.sourcegitcommit: ce0651075aa7e3e1b189437f1990207dd10374b0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/21/2020
ms.locfileid: "41247468"
---
# <a name="deploy-a-connector-to-archive-twitter-data"></a><span data-ttu-id="a7994-104">Bereitstellen eines Connectors zum Archivieren von Twitter-Daten</span><span class="sxs-lookup"><span data-stu-id="a7994-104">Deploy a connector to archive Twitter data</span></span>

<span data-ttu-id="a7994-105">Dieser Artikel enthält den schrittweisen Prozess zur Bereitstellungeines Connectors, der den Office 365 Import Dienst verwendet, um Daten aus dem Twitter-Konto Ihrer Organisation in Office 365 zu importieren.</span><span class="sxs-lookup"><span data-stu-id="a7994-105">This article contains the step-by-step process to deploy a connector that uses the Office 365 Import service to import data from your organization's Twitter account to Office 365.</span></span> <span data-ttu-id="a7994-106">Eine allgemeine Übersicht über diesen Prozess und eine Liste der erforderlichen Voraussetzungen für die Bereitstellungeines Twitter-Konnektors finden Sie unter [Verwenden eines Connectors zum Archivieren von Twitter-Daten in Office 365 (Preview)](archive-twitter-data-with-sample-connector.md).</span><span class="sxs-lookup"><span data-stu-id="a7994-106">For a high-level overview of this process and a list of prerequisites required to deploy a Twitter connector, see [Use a connector to archive Twitter data in Office 365 (Preview)](archive-twitter-data-with-sample-connector.md).</span></span> 

## <a name="step-1-download-the-package"></a><span data-ttu-id="a7994-107">Schritt 1: Herunterladen des Pakets</span><span class="sxs-lookup"><span data-stu-id="a7994-107">Step 1: Download the package</span></span>

<span data-ttu-id="a7994-108">Laden Sie das vorgefertigte Paket aus dem Abschnitt Release im GitHub-Repository unter [https://github.com/microsoft/m365-sample-twitter-connector-csharp-aspnet/releases](https://github.com/microsoft/m365-sample-twitter-connector-csharp-aspnet/releases)herunter.</span><span class="sxs-lookup"><span data-stu-id="a7994-108">Download the prebuilt package from the Release section in the GitHub repository at [https://github.com/microsoft/m365-sample-twitter-connector-csharp-aspnet/releases](https://github.com/microsoft/m365-sample-twitter-connector-csharp-aspnet/releases).</span></span> <span data-ttu-id="a7994-109">Laden Sie die ZIP-Datei mit dem Namen **SampleConnector. zip**unter der neuesten Version herunter.</span><span class="sxs-lookup"><span data-stu-id="a7994-109">Under the latest release, download the zip file named **SampleConnector.zip**.</span></span> <span data-ttu-id="a7994-110">Sie laden diese ZIP-Datei in Schritt 4 in Azure hoch.</span><span class="sxs-lookup"><span data-stu-id="a7994-110">You upload this zip file to Azure in Step 4.</span></span>

## <a name="step-2-create-an-app-in-azure-active-directory"></a><span data-ttu-id="a7994-111">Schritt 2: Erstellen einer APP in Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="a7994-111">Step 2: Create an app in Azure Active Directory</span></span>

1. <span data-ttu-id="a7994-112">Wechseln Sie <https://portal.azure.com> zu, und melden Sie sich mit den Anmeldeinformationen eines Office 365 globalen Administratorkontos an.</span><span class="sxs-lookup"><span data-stu-id="a7994-112">Go to <https://portal.azure.com> and sign in using the credentials of an Office 365 global admin account.</span></span>

   ![Bei Azure anmelden](media/TCimage01.png)

2. <span data-ttu-id="a7994-114">Klicken Sie im linken Navigationsbereich auf **Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="a7994-114">In the left navigation pane, click **Azure Active Directory**.</span></span>

   ![Wechseln Sie zu Azure Active Directory](media/TCimage02.png)

3. <span data-ttu-id="a7994-116">Klicken Sie im linken Navigationsbereich auf **App-Registrierungen (Vorschau)** , und klicken Sie dann auf **neue Registrierung**.</span><span class="sxs-lookup"><span data-stu-id="a7994-116">In the left navigation pane, click **App registrations (Preview)** and then click **New registration**.</span></span>

   ![Erstellen einer neuen App-Registrierung](media/TCimage03.png)

4. <span data-ttu-id="a7994-118">Registrieren Sie die Anwendung.</span><span class="sxs-lookup"><span data-stu-id="a7994-118">Register the application.</span></span> <span data-ttu-id="a7994-119">Wählen Sie unter **Umleitungs-URI (optional)** in der Dropdownliste Anwendungstyp die `https://portal.azure.com` Option **Webseite** aus, und geben Sie dann in das Feld für den URI ein.</span><span class="sxs-lookup"><span data-stu-id="a7994-119">Under **Redirect URI (optional)**, select **Web** in the application type dropdown list and then type `https://portal.azure.com` in the box for the URI.</span></span>

   ![<span data-ttu-id="a7994-120">Typ https://portal.azure.com für den Umleitungs-URI</span><span class="sxs-lookup"><span data-stu-id="a7994-120">Type https://portal.azure.com for the redirect URI</span></span> ](media/TCimage04.png)

5. <span data-ttu-id="a7994-121">Kopieren Sie die Anwendungs-ID **(Client) ID** und **Verzeichnis (Mandanten)** , und speichern Sie Sie in einer Textdatei oder an einem anderen sicheren Ort.</span><span class="sxs-lookup"><span data-stu-id="a7994-121">Copy the **Application (client) ID** and **Directory (tenant) ID** and save them to a text file or other safe location.</span></span> <span data-ttu-id="a7994-122">Sie verwenden diese IDs in späteren Schritten.</span><span class="sxs-lookup"><span data-stu-id="a7994-122">You use these IDs in later steps.</span></span>

    ![Kopieren und Speichern der Anwendungs-ID und der Verzeichnis-ID](media/TCimage05.png)

6. <span data-ttu-id="a7994-124">Wechseln Sie zu **Zertifikaten #a0 Geheimnisse für die neue APP** und unter **Client Secrets** auf **neuen geheimen Client Schlüssel**.</span><span class="sxs-lookup"><span data-stu-id="a7994-124">Go to **Certificates & secrets for the new app** and under **Client secrets** click **New client secret**.</span></span>

   ![Erstellen eines neuen geheimen Client Schlüssels](media/TCimage06.png)

7. <span data-ttu-id="a7994-126">Erstellen Sie einen neuen geheimen Schlüssel.</span><span class="sxs-lookup"><span data-stu-id="a7994-126">Create a new secret.</span></span> <span data-ttu-id="a7994-127">Geben Sie im Feld Beschreibung den geheimen Schlüssel ein, und wählen Sie dann einen Ablaufzeitraum aus.</span><span class="sxs-lookup"><span data-stu-id="a7994-127">In the description box, type the secret and then choose an expiration period.</span></span> 

   ![Geben Sie den geheimen Schlüssel ein und wählen Sie Ablaufzeitraum](media/TCimage08.png)

8. <span data-ttu-id="a7994-129">Kopieren Sie den Wert des geheimen Schlüssels, und speichern Sie ihn in einer Textdatei oder an einem anderen Speicherort.</span><span class="sxs-lookup"><span data-stu-id="a7994-129">Copy the value of the secret and save it to a text file or other storage location.</span></span> <span data-ttu-id="a7994-130">Dies ist der geheime Aad-Anwendungsschlüssel, den Sie in späteren Schritten verwenden.</span><span class="sxs-lookup"><span data-stu-id="a7994-130">This is the AAD application secret that you use in later steps.</span></span>

   ![Kopieren und Speichern des geheimen Schlüssels](media/TCimage09.png)

9. <span data-ttu-id="a7994-132">Wechseln Sie zu **Manifest** , und kopieren Sie die identifierUris (die auch als Aad Application URI bezeichnet wird) wie im folgenden Screenshot hervorgehoben.</span><span class="sxs-lookup"><span data-stu-id="a7994-132">Go to **Manifest** and copy the identifierUris (which is also called the AAD application Uri) as highlighted in the following screenshot.</span></span> <span data-ttu-id="a7994-133">Kopieren Sie den Aad-Anwendungs-URI in eine Textdatei oder einen anderen Speicherort.</span><span class="sxs-lookup"><span data-stu-id="a7994-133">Copy the AAD application Uri to a text file or other storage location.</span></span> <span data-ttu-id="a7994-134">Sie verwenden Sie in Schritt 6.</span><span class="sxs-lookup"><span data-stu-id="a7994-134">You use it in Step 6.</span></span>

    ![Kopieren und Speichern des Aad-Anwendungs-URI](media/TCimage10.png)

## <a name="step-3-create-an-azure-storage-account"></a><span data-ttu-id="a7994-136">Schritt 3: Erstellen eines Azure-speicherkontos</span><span class="sxs-lookup"><span data-stu-id="a7994-136">Step 3: Create an Azure storage account</span></span>

1.  <span data-ttu-id="a7994-137">Wechseln Sie zur Azure-Startseite für Ihre Organisation.</span><span class="sxs-lookup"><span data-stu-id="a7994-137">Go to the Azure home page for your organization.</span></span>

    ![GI-to-Azure-Startseite](media/TCimage11.png)

2. <span data-ttu-id="a7994-139">Klicken Sie auf **Ressource erstellen** , und geben Sie **Speicherkonto** in das Suchfeld ein.</span><span class="sxs-lookup"><span data-stu-id="a7994-139">Click **Create a resource** and they type **storage account** in the search box.</span></span>

   ![Erstellen einer Speicherkonto Ressource](media/TCimage12.png)

3. <span data-ttu-id="a7994-141">Klicken Sie auf **Speicher**, und klicken Sie dann auf **Speicherkonto**.</span><span class="sxs-lookup"><span data-stu-id="a7994-141">Click **Storage**, and then click **Storage account**.</span></span>

   ![Klicken Sie auf Speicher, und klicken Sie dann auf Speicherkonto](media/TCimage13.png)

4. <span data-ttu-id="a7994-143">Wählen Sie auf der Seite **Speicherkonto erstellen** im Feld Abonnement die Option **Pay-as-you-go** oder **﻿Kostenlose Testversion** je nach Typ des Azure-Abonnements aus.</span><span class="sxs-lookup"><span data-stu-id="a7994-143">On the **Create storage account** page, in the Subscription box, select **Pay-As-You-Go** or **Free Trial** depending on which type of Azure subscription you have.</span></span> 

   ![Auswählen eines Speicherkonto Typs](media/TCimage14.png)

5. <span data-ttu-id="a7994-145">Wählen oder erstellen Sie eine Ressourcengruppe.</span><span class="sxs-lookup"><span data-stu-id="a7994-145">Select or create a resource group.</span></span>

   ![Auswählen oder Erstellen einer Ressourcengruppe](media/TCimage15.png)

6. <span data-ttu-id="a7994-147">Geben Sie einen Namen für das Speicherkonto ein.</span><span class="sxs-lookup"><span data-stu-id="a7994-147">Type a name for the storage account.</span></span>

   ![Benennen des speicherkontos](media/TCimage16.png)

7. <span data-ttu-id="a7994-149">Überprüfen Sie, und klicken Sie dann auf **Erstellen** , um das Speicherkonto zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="a7994-149">Review and then click **Create** to create the storage account.</span></span>

   ![Überprüfen der Einstellungen und Erstellen des speicherkontos](media/TCimage17.png)

8. <span data-ttu-id="a7994-151">Klicken Sie nach einigen Momenten auf **Aktualisieren** , und klicken Sie dann auf **Ressource wechseln** , um zum Speicherkonto zu navigieren.</span><span class="sxs-lookup"><span data-stu-id="a7994-151">After a few moments, click **Refresh** and then click **Go to resource** to navigate to the storage account.</span></span>

   ![Wechseln Sie zu dem soeben erstellten Speicherkonto.](media/TCimage18.png)

9. <span data-ttu-id="a7994-153">Klicken Sie im linken Navigationsbereich auf **Zugriffstasten** .</span><span class="sxs-lookup"><span data-stu-id="a7994-153">Click **Access keys** in the left navigation pane.</span></span>

   ![Klicken Sie auf Zugriffstasten](media/TCimage19.png)

10. <span data-ttu-id="a7994-155">Kopieren Sie eine **Verbindungszeichenfolge** , und speichern Sie Sie in einer Textdatei oder an einem anderen Speicherort.</span><span class="sxs-lookup"><span data-stu-id="a7994-155">Copy a **Connection string** and save it to a text file or other storage location.</span></span> <span data-ttu-id="a7994-156">Verwenden Sie diese Option, wenn Sie in Schritt 4 eine Webanwendungs Ressource erstellen.</span><span class="sxs-lookup"><span data-stu-id="a7994-156">You use this when creating a web app resource in Step 4.</span></span>

    ![Kopieren einer Verbindungszeichenfolge](media/TCimage20.png)

## <a name="step-4-create-a-new-web-app-resource-in-azure"></a><span data-ttu-id="a7994-158">Schritt 4: Erstellen einer neuen webapp-Ressource in Azure</span><span class="sxs-lookup"><span data-stu-id="a7994-158">Step 4: Create a new web app resource in Azure</span></span>

1. <span data-ttu-id="a7994-159">Klicken Sie auf der **Start** Seite im Azure-Portal auf **Ressource \> : alles \> -Webanwendung erstellen**.</span><span class="sxs-lookup"><span data-stu-id="a7994-159">On the **Home** page in the Azure portal, click **Create a resource \> Everything \> Web app**.</span></span> <span data-ttu-id="a7994-160">Klicken Sie auf der Seite **Webanwendung** auf **Erstellen**.</span><span class="sxs-lookup"><span data-stu-id="a7994-160">On the **Web app** page, click **Create**.</span></span>

   ![Erstellen von webapp-Ressourcen in Azure](media/TCimage21.png)

2. <span data-ttu-id="a7994-162">Geben Sie die Details ein (wie unten dargestellt), und erstellen Sie dann die Webanwendung.</span><span class="sxs-lookup"><span data-stu-id="a7994-162">Fill in the details (as shown below) and then create the Web app.</span></span> <span data-ttu-id="a7994-163">Der Name, den Sie im Feld **App-Name** eingeben, wird verwendet, um die Azure-App-Dienst-URL zu erstellen. Beispiel: twitterconnector.azurewebsites.net.</span><span class="sxs-lookup"><span data-stu-id="a7994-163">The name that you enter in the **App name** box is used to create the Azure app service URL; for example, twitterconnector.azurewebsites.net.</span></span>

   ![<span data-ttu-id="a7994-164">Typname für die webapp-Ressource; Beispiel twitterconnector.azurewebsites.net</span><span class="sxs-lookup"><span data-stu-id="a7994-164">Type name for the web app resource; for example twitterconnector.azurewebsites.net</span></span> ](media/TCimage22.png)

3. <span data-ttu-id="a7994-165">Wechseln Sie zur neu erstellten Ressource für Webanwendungen, und klicken Sie im linken Navigationsbereich auf **Anwendungseinstellungen** .</span><span class="sxs-lookup"><span data-stu-id="a7994-165">Go to the newly created web app resource and click **Application Settings** in the left navigation pane.</span></span> <span data-ttu-id="a7994-166">Klicken Sie unter **Anwendungseinstellungen**auf **neue Einstellung hinzufügen** , und fügen Sie die folgenden drei Einstellungen hinzu.</span><span class="sxs-lookup"><span data-stu-id="a7994-166">Under **Application settings**, click **Add new setting** and add the following three settings.</span></span> <span data-ttu-id="a7994-167">Verwenden Sie die Werte (die Sie in die Textdatei aus den vorherigen Schritten kopiert haben):</span><span class="sxs-lookup"><span data-stu-id="a7994-167">Use the values (that you copied to the text file from the previous steps):</span></span> 

    - <span data-ttu-id="a7994-168">**APISecretKey** – Sie können einen beliebigen Wert als geheimen Schlüssel eingeben.</span><span class="sxs-lookup"><span data-stu-id="a7994-168">**APISecretKey** – You can type any value as the secret.</span></span> <span data-ttu-id="a7994-169">Dieser wird für den Zugriff auf die Connector-Webanwendung in Schritt 7 verwendet.</span><span class="sxs-lookup"><span data-stu-id="a7994-169">This is used to access the connector web app in Step 7.</span></span>

    - <span data-ttu-id="a7994-170">**StorageAccountConnectionString** – der Verbindungszeichenfolgen-URI, den Sie nach dem Erstellen des Azure-speicherkontos in Schritt 3 kopiert haben.</span><span class="sxs-lookup"><span data-stu-id="a7994-170">**StorageAccountConnectionString** – The connection string Uri that you copied after creating the Azure storage account in Step 3.</span></span>

    - <span data-ttu-id="a7994-171">**Mandanten** Kennung – die Mandanten-ID Ihrer Office 365 Organisation, die Sie nach dem Erstellen der Twitter Connector-app in Azure Active Directory in Schritt 2 kopiert haben.</span><span class="sxs-lookup"><span data-stu-id="a7994-171">**tenantId** – The tenant ID of your Office 365 organization that you copied after creating the Twitter connector app in Azure Active Directory in Step 2.</span></span>

    ![Hinzufügen von App-Einstellungen](media/TCimage23.png)

4. <span data-ttu-id="a7994-173">Klicken Sie unter **Allgemeine Einstellungen** **auf neben** dem **immer ein**.</span><span class="sxs-lookup"><span data-stu-id="a7994-173">Under **General settings**, click **On** next to the **Always On**.</span></span> <span data-ttu-id="a7994-174">Klicken Sie oben auf der Seite auf **Speichern** , um die Anwendungseinstellungen zu speichern.</span><span class="sxs-lookup"><span data-stu-id="a7994-174">Click **Save** at the top of the page to save the application settings.</span></span>

   ![Aktivieren der webapp-Ressource und speichern](media/TCimage24.png)

5. <span data-ttu-id="a7994-176">Der letzte Schritt besteht darin, den Quellcode der Connector-app in Azure hochzuladen, den Sie in Schritt 1 heruntergeladen haben.</span><span class="sxs-lookup"><span data-stu-id="a7994-176">The final step is to upload the connector app source code to Azure that you downloaded in Step 1.</span></span> <span data-ttu-id="a7994-177">Wechseln Sie in einem Webbrowser zu https://<AzureAppResourceName>. SCM.azurewebsites.net/ZipDeployUi.</span><span class="sxs-lookup"><span data-stu-id="a7994-177">In a web browser, go to https://<AzureAppResourceName>.scm.azurewebsites.net/ZipDeployUi.</span></span> <span data-ttu-id="a7994-178">Wenn beispielsweise der Name Ihrer Azure-App-Ressource (die Sie in Schritt 2 in diesem Abschnitt genannt haben) **twitterconnector**lautet, gehen Sie zu https://twitterconnector.scm.azurewebsites.net/ZipDeployUi.</span><span class="sxs-lookup"><span data-stu-id="a7994-178">For example, if the name of your Azure app resource (which you named in step 2 in this section) is **twitterconnector**, then you would go to https://twitterconnector.scm.azurewebsites.net/ZipDeployUi.</span></span>

6. <span data-ttu-id="a7994-179">Ziehen Sie das SampleConnector. zip-Menü (das Sie in Schritt 1 heruntergeladen haben) auf diese Seite.</span><span class="sxs-lookup"><span data-stu-id="a7994-179">Drag and drop the SampleConnector.zip (that you downloaded in Step 1) to this page.</span></span> <span data-ttu-id="a7994-180">Nachdem die Dateien hochgeladen wurden und die Bereitstellung erfolgreich war, sieht die Seite wie im folgenden Screenshot aus:</span><span class="sxs-lookup"><span data-stu-id="a7994-180">After the files are uploaded and the deployment is successful, the page will look similar to the following screenshot:</span></span>

   ![Drag & Drop der Datei SampleConnector. zip auf diese Seite](media/TCimage25.png)

## <a name="step-5-create-the-twitter-app"></a><span data-ttu-id="a7994-182">Schritt 5: Erstellen der Twitter-APP</span><span class="sxs-lookup"><span data-stu-id="a7994-182">Step 5: Create the Twitter app</span></span>

1. <span data-ttu-id="a7994-183">Wechseln Sie https://developer.twitter.comzu, melden Sie sich mit den Anmeldeinformationen für das Entwicklerkonto für Ihre Organisation an, und klicken Sie dann auf **apps**.</span><span class="sxs-lookup"><span data-stu-id="a7994-183">Go to https://developer.twitter.com, log in using the credentials for the developer account for your organization, and then click **Apps**.</span></span>

   ![Wechseln Sie https://developer.twitter.com zu und melden Sie sich an.](media/TCimage25-5.png)
2. <span data-ttu-id="a7994-185">Klicken Sie auf **app erstellen**.</span><span class="sxs-lookup"><span data-stu-id="a7994-185">Click **Create an app**.</span></span>
   
   ![Zur Seite "Apps" wechseln, um eine APP zu erstellen](media/TCimage26.png)

3. <span data-ttu-id="a7994-187">Fügen Sie unter **App-Details**Informationen zur Anwendung hinzu.</span><span class="sxs-lookup"><span data-stu-id="a7994-187">Under **App details**, add information about the application.</span></span>

   ![Eingeben von Informationen zur APP](media/TCimage27.png)

4. <span data-ttu-id="a7994-189">Wählen Sie im Twitter Developer Dashboard die soeben erstellte App aus, und kopieren Sie die angezeigte APP-ID, und speichern Sie Sie in einer Textdatei oder an einem anderen Speicherort.</span><span class="sxs-lookup"><span data-stu-id="a7994-189">On the Twitter developer dashboard, select the app that you just created and copy the App ID that's displayed  and save it to a text file or other storage location.</span></span> <span data-ttu-id="a7994-190">Klicken Sie dann auf **Details**.</span><span class="sxs-lookup"><span data-stu-id="a7994-190">Then click **Details**.</span></span>
   
   ![Kopieren und Speichern der APP-ID](media/TCimage28.png)

5. <span data-ttu-id="a7994-192">Kopieren Sie auf der Registerkarte **Schlüssel und Token** unter **Consumer-API-Schlüssel** den geheimen Schlüssel der API, und speichern Sie ihn in einer Textdatei oder an einem anderen Speicherort.</span><span class="sxs-lookup"><span data-stu-id="a7994-192">On the **Keys and tokens** tab, under **Consumer API keys** copy the API secret key and save it to a text file or other storage location.</span></span> <span data-ttu-id="a7994-193">Klicken Sie dann auf **Erstellen** , um ein Zugriffstoken und einen Zugriffstoken Schlüssel zu generieren, und kopieren Sie diese in eine Textdatei oder einen anderen Speicherort.</span><span class="sxs-lookup"><span data-stu-id="a7994-193">Then click **Create** to generate an access token and an access token secret, and copy these to a text file or other storage location.</span></span>
   
   ![Geheimer Schlüssel "Kopieren und speichern in API"](media/TCimage29.png)

   <span data-ttu-id="a7994-195">Klicken Sie dann auf **Erstellen** , um ein Zugriffstoken und einen Zugriffstoken Schlüssel zu generieren, und kopieren Sie diese in eine Textdatei oder einen anderen Speicherort.</span><span class="sxs-lookup"><span data-stu-id="a7994-195">Then click **Create** to generate an access token and an access token secret, and copy these to a text file or other storage location.</span></span>

6. <span data-ttu-id="a7994-196">Klicken Sie auf die Registerkarte **Berechtigungen** , und konfigurieren Sie die Berechtigungen wie im folgenden Screenshot dargestellt:</span><span class="sxs-lookup"><span data-stu-id="a7994-196">Click the **Permissions** tab and configure the permissions as shown in the following screenshot:</span></span>

   ![Konfigurieren von Berechtigungen](media/TCimage30.png)

7. <span data-ttu-id="a7994-198">Nachdem Sie die Berechtigungseinstellungen gespeichert haben, klicken Sie auf die Registerkarte **App-Details** , und klicken Sie dann auf **Bearbeiten #a0 bearbeiten von Details**.</span><span class="sxs-lookup"><span data-stu-id="a7994-198">After you save the permission settings, click the **App details** tab, and then click **Edit > Edit details**.</span></span>

   ![Bearbeiten der App-Details](media/TCimage31.png)

8. <span data-ttu-id="a7994-200">Führen Sie die folgenden Aufgaben aus:</span><span class="sxs-lookup"><span data-stu-id="a7994-200">Do the following tasks:</span></span>

   - <span data-ttu-id="a7994-201">Aktivieren Sie das Kontrollkästchen, damit sich die Connector-App bei Twitter anmelden kann.</span><span class="sxs-lookup"><span data-stu-id="a7994-201">Select the checkbox to allow the connector app to sign in to Twitter.</span></span>
   
   - <span data-ttu-id="a7994-202">Fügen Sie den OAuth-Umleitungs-URI mit dem folgenden Format hinzu: \*\* \<connectorserviceuri>/views/twitteroauth\*\*, wobei der Wert von *connectorserviceuri* die Azure-App-Dienst-URL für Ihre Organisation ist. Beispiel: https://twitterconnector.azurewebsites.net/Views/TwitterOAuth.</span><span class="sxs-lookup"><span data-stu-id="a7994-202">Add the OAuth redirect Uri using the following format: **\<connectorserviceuri>/Views/TwitterOAuth**, where the value of *connectorserviceuri* is the Azure app service URL for your organization; for example, https://twitterconnector.azurewebsites.net/Views/TwitterOAuth.</span></span>

    ![Connector-App erlauben, sich bei Twitter anzumelden und OAuth-Umleitungs-URI hinzuzufügen](media/TCimage32.png)

<span data-ttu-id="a7994-204">Die Twitter-Entwickler-App ist jetzt einsatzfähig.</span><span class="sxs-lookup"><span data-stu-id="a7994-204">The Twitter developer app is now ready to use.</span></span>

## <a name="step-6-configure-the-connector-web-app"></a><span data-ttu-id="a7994-205">Schritt 6: Konfigurieren der Connector-Webanwendung</span><span class="sxs-lookup"><span data-stu-id="a7994-205">Step 6: Configure the connector web app</span></span> 

1. <span data-ttu-id="a7994-206">Wechseln Sie zu\<https://AzureAppResourceName>. azurewebsites.net (wobei **AzureAppResourceName** der Name Ihrer Azure-App-Ressource ist, die Sie in Schritt 4 benannt haben).</span><span class="sxs-lookup"><span data-stu-id="a7994-206">Go to https://\<AzureAppResourceName>.azurewebsites.net (where **AzureAppResourceName** is the name of your Azure app resource that you named in Step 4).</span></span> <span data-ttu-id="a7994-207">Wenn der Name beispielsweise **twitterconnector**lautet, wechseln Sie zu https://twitterconnector.azurewebsites.net.</span><span class="sxs-lookup"><span data-stu-id="a7994-207">For example, if the name is **twitterconnector**, go to https://twitterconnector.azurewebsites.net.</span></span> <span data-ttu-id="a7994-208">Die Startseite der APP sieht wie im folgenden Screenshot aus:</span><span class="sxs-lookup"><span data-stu-id="a7994-208">The home page of the app looks like the following screenshot:</span></span>

   ![Seite zur Azure-App-Ressource wechseln](media/FBCimage41.png)

2. <span data-ttu-id="a7994-210">Klicken Sie auf **Konfigurieren** , um eine Anmeldeseite anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="a7994-210">Click **Configure** to display a sign in page.</span></span>

   ![Klicken Sie auf konfigurieren, um die Anmeldeseite anzuzeigen.](media/FBCimage42.png)

3. <span data-ttu-id="a7994-212">Geben Sie in das Feld Mandanten-ID die Mandanten-ID ein, die Sie in Schritt 2 erhalten haben, oder fügen Sie Sie ein.</span><span class="sxs-lookup"><span data-stu-id="a7994-212">In the Tenant Id box, type or paste your tenant Id (that you obtained in Step 2).</span></span> <span data-ttu-id="a7994-213">Geben Sie in das Feld Kennwort den APISecretKey (den Sie in Schritt 2 erhalten haben) ein, oder fügen Sie ihn ein, und klicken Sie dann auf **Konfigurationseinstellungen festlegen** , um die Seite **Konfigurations Details** anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="a7994-213">In the password box, type or paste the APISecretKey (that you obtained in Step 2), and then click **Set Configuration Settings** to display the **Configuration Details** page.</span></span>

   ![Anmelden mithilfe der Mandanten-ID und des geheimen Schlüssels der API](media/TCimage35.png)

4. <span data-ttu-id="a7994-215">Geben Sie unter **Konfigurations Details**die folgenden Konfigurationseinstellungen ein:</span><span class="sxs-lookup"><span data-stu-id="a7994-215">Under **Configuration Details**, enter the following configuration settings</span></span> 

   - <span data-ttu-id="a7994-216">**Twitter-API-Schlüssel** – die APP-ID für die Twitter-Anwendung, die Sie in Schritt 5 erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="a7994-216">**Twitter Api Key** – The app ID for the Twitter application that you created in Step 5.</span></span>
   - <span data-ttu-id="a7994-217">**Twitter-API-geheimer Schlüssel** – der geheime API-Schlüssel für die Twitter-Anwendung, die Sie in Schritt 5 erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="a7994-217">**Twitter Api Secret Key** – The API secret key for the Twitter application that you created in Step 5.</span></span>
   - <span data-ttu-id="a7994-218">**Twitter-Zugriffstoken** – das Zugriffstoken, das Sie in Schritt 5 erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="a7994-218">**Twitter Access Token** – The access token that you created in Step 5.</span></span>
   - <span data-ttu-id="a7994-219">**Twitter-Zugriffstoken Secret** – der geheime Zugriffstoken-Schlüssel, den Sie in Schritt 5 erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="a7994-219">**Twitter Access Token Secret** – The access token secret that you created in Step 5.</span></span>
   - <span data-ttu-id="a7994-220">**Aad-Anwendungs-ID** – die Anwendungs-ID für die Azure Active Directory-APP, die Sie in Schritt 2 erstellt haben</span><span class="sxs-lookup"><span data-stu-id="a7994-220">**AAD Application ID** – The application ID for the Azure Active Directory app that you created in Step 2</span></span>
   - <span data-ttu-id="a7994-221">**Aad-Anwendungs Geheimnis** – der Wert für den geheimen Schlüssel "APISecretKey", den Sie in Schritt 4 erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="a7994-221">**AAD Application Secret** – The value for the APISecretKey secret that you created in Step 4.</span></span>
   - <span data-ttu-id="a7994-222">**Aad-Anwendungs-URI** – der in Schritt 2 abgerufene Aad-Anwendungs-URI; Beispiel: `https://microsoft.onmicrosoft.com/2688yu6n-12q3-23we-e3ee-121111123213`.</span><span class="sxs-lookup"><span data-stu-id="a7994-222">**AAD Application Uri** – The AAD application Uri obtained in Step 2; for example, `https://microsoft.onmicrosoft.com/2688yu6n-12q3-23we-e3ee-121111123213`.</span></span>
   - <span data-ttu-id="a7994-223">**App Insights Instrumentation Key** – lassen Sie dieses Feld leer.</span><span class="sxs-lookup"><span data-stu-id="a7994-223">**App Insights Instrumentation Key** – Leave this box blank.</span></span>

5. <span data-ttu-id="a7994-224">Klicken Sie auf **Speichern** , um die Verbindungseinstellungen zu speichern.</span><span class="sxs-lookup"><span data-stu-id="a7994-224">Click **Save** to save the connector settings.</span></span>

## <a name="step-7-set-up-a-custom-connector-in-the-security-and-compliance-center"></a><span data-ttu-id="a7994-225">Schritt 7: Einrichten eines benutzerdefinierten Connectors im Security and Compliance Center</span><span class="sxs-lookup"><span data-stu-id="a7994-225">Step 7: Set up a custom connector in the security and compliance center</span></span>

1.  <span data-ttu-id="a7994-226">Wechseln Sie <https://protection.office.com> zu, und klicken Sie dann auf **Information Governance \> Import \> Archivieren von drittanbieterdaten**.</span><span class="sxs-lookup"><span data-stu-id="a7994-226">Go to <https://protection.office.com> and then click **Information governance \> Import \> Archive third-party data**.</span></span>

    ![Wechseln zur Seite "Archivieren von drittanbieterdaten" im Security and Compliance Center](media/TCimage36.png)

2. <span data-ttu-id="a7994-228">Klicken Sie auf **Connector hinzufügen** , und klicken Sie dann auf **Twitter**.</span><span class="sxs-lookup"><span data-stu-id="a7994-228">Click **Add a connector** and then click **Twitter**.</span></span>

   ![Klicken Sie auf Connector hinzufügen, um einen Twitter-Konnektor hinzuzufügen](media/TCimage37.png)

3. <span data-ttu-id="a7994-230">Geben Sie auf der Seite " **Connector-app hinzufügen** " die folgenden Informationen ein, und klicken Sie dann auf **Connector überprüfen**.</span><span class="sxs-lookup"><span data-stu-id="a7994-230">On the **Add Connector App** page, enter the following information and then click **Validate connector**.</span></span>

    - <span data-ttu-id="a7994-231">Geben Sie im ersten Feld einen Namen für den Connector ein, beispielsweise **Twitter**.</span><span class="sxs-lookup"><span data-stu-id="a7994-231">In the first box, type a name for the connector, such as **Twitter**.</span></span>
    - <span data-ttu-id="a7994-232">Geben Sie im zweiten Feld den Wert des APISecretKey ein, den Sie in Schritt 4 hinzugefügt haben, oder fügen Sie ihn ein.</span><span class="sxs-lookup"><span data-stu-id="a7994-232">In the second box, type or paste the value of the APISecretKey that you added in Step 4.</span></span>
    - <span data-ttu-id="a7994-233">Geben Sie im dritten Feld die Azure-App-Dienst-URL ein, oder fügen Sie Sie ein. Beispiel: **https://twitterconnector.azurewebsites.net**.</span><span class="sxs-lookup"><span data-stu-id="a7994-233">In the third box, type or paste the Azure app service URL; for example, **https://twitterconnector.azurewebsites.net**.</span></span>

   <span data-ttu-id="a7994-234">Nachdem der Connector erfolgreich überprüft wurde, klicken Sie auf **weiter**.</span><span class="sxs-lookup"><span data-stu-id="a7994-234">After the connector is successfully validated, click **Next**.</span></span>

   ![Eingeben von Connector-App-Einstellungen](media/TCimage38.png)

4. <span data-ttu-id="a7994-236">Klicken Sie auf **Anmeldung mit der Connector-App**.</span><span class="sxs-lookup"><span data-stu-id="a7994-236">Click **Login with Connector App**.</span></span>

   ![Melden Sie sich bei der Connector-APP an](media/TCimage39.png)

5. <span data-ttu-id="a7994-238">Geben Sie den APISecretKey erneut ein, oder fügen Sie ihn ein, und klicken Sie dann auf **Login to Connector Service**.</span><span class="sxs-lookup"><span data-stu-id="a7994-238">Type or paste the APISecretKey again and then click  **Login to Connector Service**.</span></span>

   ![Typ-API-geheimer Schlüssel für die Anmeldung bei Connector Service](media/TCimage40.png)

6. <span data-ttu-id="a7994-240">Klicken Sie auf **weiter mit Twitter**.</span><span class="sxs-lookup"><span data-stu-id="a7994-240">Click **Continue with Twitter**.</span></span>

7. <span data-ttu-id="a7994-241">Melden Sie sich auf der Twitter-Anmeldeseite mit den Anmeldeinformationen für das Konto für das Twitter-Konto Ihrer Organisation an.</span><span class="sxs-lookup"><span data-stu-id="a7994-241">On the Twitter sign in page, sign in using the credentials for the account for your organization’s Twitter account.</span></span>

   ![Bei Twitter-Konto anmelden](media/TCimage42.png)

   <span data-ttu-id="a7994-243">Nachdem Sie sich angemeldet haben, wird auf der Twitter-Seite die folgende Meldung angezeigt: "Twitter Connector-Auftrag erfolgreich eingerichtet."</span><span class="sxs-lookup"><span data-stu-id="a7994-243">After you sign in, the Twitter page will display the following message, "Twitter Connector Job Successfully set up."</span></span>

8. <span data-ttu-id="a7994-244">Klicken Sie auf **Fertig stellen** , um die Einrichtung des Twitter-Konnektors abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="a7994-244">Click **Finish** to complete setting up the Twitter connector.</span></span>

9. <span data-ttu-id="a7994-245">Auf der Seite **Filter festlegen** können Sie einen Filter anwenden, um Elemente zu importieren (und archivieren), die ein bestimmtes Alter aufweisen.</span><span class="sxs-lookup"><span data-stu-id="a7994-245">On the **Set Filters** page, you can apply a filter to import (and archive) items that are a certain age.</span></span> <span data-ttu-id="a7994-246">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="a7994-246">Click **Next**.</span></span>

   ![Konfigurieren des Filters zum Importieren von Elementen eines bestimmten Alters](media/TCimage44.png)

10. <span data-ttu-id="a7994-248">Geben Sie auf der Seite **Speicherkonto festlegen** die e-Mail-Adresse eines Office 365 Postfachs ein, in das die Twitter-Elemente importiert werden.</span><span class="sxs-lookup"><span data-stu-id="a7994-248">On the **Set Storage Account** page, type the email address of an Office 365 mailbox that the Twitter items will be imported to.</span></span>

    ![Geben Sie ein Office 365 Postfach an, in das Twitter-Elemente importiert werden sollen.](media/TCimage45.png)

11. <span data-ttu-id="a7994-250">Überprüfen Sie Ihre Einstellungen, und klicken Sie dann auf **Fertig stellen** , um das Connector-Setup im Security #a0 Compliance Center abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="a7994-250">Review your settings and then click **Finish** to complete the connector setup in the Security & Compliance Center.</span></span>

    ![Überprüfen Sie die Einstellungen, und klicken Sie dann auf Fertig stellen](media/TCimage46.png)

    ![Bildschirmanzeige für den Abschluss des Connector-Setups](media/TCimage47.png)

12. <span data-ttu-id="a7994-253">Wechseln Sie zur Seite **Archivieren von drittanbieterdaten** , um den Fortschritt des Importvorgangs anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="a7994-253">Go to the **Archive third-party data** page to see the progress of the import process.</span></span>

    ![Neuer Connector im Security and Compliance Center angezeigt](media/TCimage48.png)
