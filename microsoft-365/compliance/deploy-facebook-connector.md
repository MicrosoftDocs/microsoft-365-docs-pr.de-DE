---
title: Bereitstellen eines Connectors zum Archivieren von Facebook-Daten in Office 365
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
description: Administratoren können einen systemeigenen Connector zum Importieren und Archivieren von Facebook-Geschäfts Seiten in Office 365 einrichten. Nachdem diese Daten in Office 365 importiert wurden, können Sie Compliance-Features wie Legal Hold, Inhaltssuche und Aufbewahrungsrichtlinien verwenden, um die Steuerung der Facebook-Daten Ihrer Organisation zu verwalten.
ms.openlocfilehash: 1f5b0f241616cc95e79e80d054a8782f97c5887b
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/20/2019
ms.locfileid: "37070965"
---
# <a name="deploy-a-connector-to-archive-facebook-data-in-office-365"></a><span data-ttu-id="dd0de-104">Bereitstellen eines Connectors zum Archivieren von Facebook-Daten in Office 365</span><span class="sxs-lookup"><span data-stu-id="dd0de-104">Deploy a connector to archive Facebook data in Office 365</span></span>

<span data-ttu-id="dd0de-105">Dieser Artikel enthält den schrittweisen Prozess zur Bereitstellungeines Connectors, der den Office 365 Import Dienst verwendet, um Daten von Facebook-Geschäfts Seiten in Office 365 zu importieren.</span><span class="sxs-lookup"><span data-stu-id="dd0de-105">This article contains the step-by-step process to deploy a connector that uses the Office 365 Import service to import data from Facebook Business pages to Office 365.</span></span> <span data-ttu-id="dd0de-106">Eine allgemeine Übersicht über diesen Prozess und eine Liste der erforderlichen Voraussetzungen für die Bereitstellungeines Facebook-Konnektors finden Sie unter [Verwenden eines Beispiel-Konnektors zum Archivieren von Facebook-Daten in Office 365 (Preview)](archive-facebook-data-with-sample-connector.md).</span><span class="sxs-lookup"><span data-stu-id="dd0de-106">For a high-level overview of this process and a list of prerequisites required to deploy a Facebook connector, see [Use a sample connector to archive Facebook data in Office 365 (Preview)](archive-facebook-data-with-sample-connector.md).</span></span> 

## <a name="step-1-download-the-package"></a><span data-ttu-id="dd0de-107">Schritt 1: Herunterladen des Pakets</span><span class="sxs-lookup"><span data-stu-id="dd0de-107">Step 1: Download the package</span></span>

<span data-ttu-id="dd0de-108">Laden Sie das vorgefertigte Paket aus dem Abschnitt Release im GitHub-Repository unter <https://github.com/Microsoft/m365-sample-connector-csharp-aspnet/releases>herunter.</span><span class="sxs-lookup"><span data-stu-id="dd0de-108">Download the prebuilt package from the Release section in the GitHub repository at <https://github.com/Microsoft/m365-sample-connector-csharp-aspnet/releases>.</span></span> <span data-ttu-id="dd0de-109">Laden Sie die ZIP-Datei mit dem Namen **SampleConnector. zip**unter der neuesten Version herunter.</span><span class="sxs-lookup"><span data-stu-id="dd0de-109">Under the latest release, download the zip file named **SampleConnector.zip**.</span></span> <span data-ttu-id="dd0de-110">Sie laden diese ZIP-Datei in Schritt 4 in Azure hoch.</span><span class="sxs-lookup"><span data-stu-id="dd0de-110">You upload this zip file to Azure in Step 4.</span></span>

## <a name="step-2-create-an-app-in-azure-active-directory"></a><span data-ttu-id="dd0de-111">Schritt 2: Erstellen einer APP in Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="dd0de-111">Step 2: Create an app in Azure Active Directory</span></span>

1. <span data-ttu-id="dd0de-112">Wechseln Sie <https://portal.azure.com> zu, und melden Sie sich mit den Anmeldeinformationen eines Office 365 globalen Administratorkontos an.</span><span class="sxs-lookup"><span data-stu-id="dd0de-112">Go to <https://portal.azure.com> and sign in using the credentials of an Office 365 global admin account.</span></span>

    ![Erstellen einer APP in Aad](media/FBCimage1.png)

2. <span data-ttu-id="dd0de-114">Klicken Sie im linken Navigationsbereich auf **Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="dd0de-114">In the left navigation pane, click **Azure Active Directory**.</span></span>

    ![](media/FBCimage2.png)

3. <span data-ttu-id="dd0de-115">Klicken Sie im linken Navigationsbereich auf **App-Registrierungen (Vorschau)** , und klicken Sie dann auf **neue Registrierung**.</span><span class="sxs-lookup"><span data-stu-id="dd0de-115">In the left navigation pane, click **App registrations (Preview)** and then click **New registration**.</span></span>

    ![](media/FBCimage3.png)

4. <span data-ttu-id="dd0de-116">Registrieren Sie die Anwendung.</span><span class="sxs-lookup"><span data-stu-id="dd0de-116">Register the application.</span></span> <span data-ttu-id="dd0de-117">Wählen Sie unter Umleitungs-URI die Option Webin der Dropdownliste <https://portal.azure.com> Anwendungstyp aus, und geben Sie dann in das Feld für den URI ein.</span><span class="sxs-lookup"><span data-stu-id="dd0de-117">Under Redirect URI, select Web in the application type dropdown list and then type <https://portal.azure.com> in the box for the URI.</span></span>

   ![](media/FBCimage4.png)

5. <span data-ttu-id="dd0de-118">Kopieren Sie die Anwendungs-ID **(Client) ID** und **Verzeichnis (Mandanten)** , und speichern Sie Sie in einer Textdatei oder an einem anderen sicheren Ort.</span><span class="sxs-lookup"><span data-stu-id="dd0de-118">Copy the **Application (client) ID** and **Directory (tenant) ID** and save them to a text file or other safe location.</span></span> <span data-ttu-id="dd0de-119">Sie verwenden diese IDs in späteren Schritten.</span><span class="sxs-lookup"><span data-stu-id="dd0de-119">You use these IDs in later steps.</span></span>

   ![](media/FBCimage5.png)

6. <span data-ttu-id="dd0de-120">Wechseln Sie zu **Zertifikaten #a0 Geheimnisse für die neue APP.**</span><span class="sxs-lookup"><span data-stu-id="dd0de-120">Go to **Certificates & secrets for the new app.**</span></span>

   ![](media/FBCimage6.png)

7. <span data-ttu-id="dd0de-121">Klicken Sie auf **neuer geheimer Client Schlüssel**</span><span class="sxs-lookup"><span data-stu-id="dd0de-121">Click **New client secret**</span></span>

   ![](media/FBCimage7.png)

8. <span data-ttu-id="dd0de-122">Erstellen Sie einen neuen geheimen Schlüssel.</span><span class="sxs-lookup"><span data-stu-id="dd0de-122">Create a new secret.</span></span> <span data-ttu-id="dd0de-123">Geben Sie im Feld Beschreibung den geheimen Schlüssel ein, und wählen Sie dann einen Ablaufzeitraum aus.</span><span class="sxs-lookup"><span data-stu-id="dd0de-123">In the description box, type the secret and then choose an expiration period.</span></span> 

    ![](media/FBCimage8.png)

9. <span data-ttu-id="dd0de-124">Kopieren Sie den Wert des geheimen Schlüssels, und speichern Sie ihn in einer Textdatei oder an einem anderen Speicherort.</span><span class="sxs-lookup"><span data-stu-id="dd0de-124">Copy the value of the secret and save it to a text file or other storage location.</span></span> <span data-ttu-id="dd0de-125">Dies ist der geheime Aad-Anwendungsschlüssel, den Sie in späteren Schritten verwenden.</span><span class="sxs-lookup"><span data-stu-id="dd0de-125">This is the AAD application secret that you use in later steps.</span></span>

   ![](media/FBCimage9.png)

10. <span data-ttu-id="dd0de-126">Wechseln Sie zu **Manifest** , und kopieren Sie die identifierUris (die auch als Aad Application URI bezeichnet wird) wie im folgenden Screenshot hervorgehoben.</span><span class="sxs-lookup"><span data-stu-id="dd0de-126">Go to **Manifest** and copy the identifierUris (which is also called the AAD application Uri) as highlighted in the following screenshot.</span></span> <span data-ttu-id="dd0de-127">Kopieren Sie den Aad-Anwendungs-URI in eine Textdatei oder einen anderen Speicherort.</span><span class="sxs-lookup"><span data-stu-id="dd0de-127">Copy the AAD application Uri to a text file or other storage location.</span></span> <span data-ttu-id="dd0de-128">Sie verwenden Sie in Schritt 6.</span><span class="sxs-lookup"><span data-stu-id="dd0de-128">You use it in Step 6.</span></span>

   ![](media/FBCimage10.png)

## <a name="step-3-create-an-azure-storage-account"></a><span data-ttu-id="dd0de-129">Schritt 3: Erstellen eines Azure-speicherkontos</span><span class="sxs-lookup"><span data-stu-id="dd0de-129">Step 3: Create an Azure storage account</span></span>

1. <span data-ttu-id="dd0de-130">Wechseln Sie zur Azure-Startseite für Ihre Organisation.</span><span class="sxs-lookup"><span data-stu-id="dd0de-130">Go to the Azure home page for your organization.</span></span>

    ![](media/FBCimage11.png)

2. <span data-ttu-id="dd0de-131">Klicken Sie auf **Ressource erstellen** , und geben Sie **Speicherkonto** in das Suchfeld ein.</span><span class="sxs-lookup"><span data-stu-id="dd0de-131">Click **Create a resource** and they type **storage account** in the search box.</span></span>

    ![](media/FBCimage12.png)

3. <span data-ttu-id="dd0de-132">Klicken Sie auf **Speicher**, und klicken Sie dann auf **Speicherkonto**.</span><span class="sxs-lookup"><span data-stu-id="dd0de-132">Click **Storage**, and then click **Storage account**.</span></span>

    ![](media/FBCimage13.png)

4. <span data-ttu-id="dd0de-133">Wählen Sie auf der Seite **Speicherkonto erstellen** im Feld Abonnement die Option **Pay-as-you-go** oder **﻿Kostenlose Testversion** je nach Typ des Azure-Abonnements aus.</span><span class="sxs-lookup"><span data-stu-id="dd0de-133">On the **Create storage account** page, in the Subscription box, select **Pay-As-You-Go** or **Free Trial** depending on which type of Azure subscription you have.</span></span> <span data-ttu-id="dd0de-134">Wählen Sie dann eine Ressourcengruppe aus, oder erstellen Sie eine.</span><span class="sxs-lookup"><span data-stu-id="dd0de-134">Then select or create a resource group.</span></span>

    ![](media/FBCimage14.png)

5. <span data-ttu-id="dd0de-135">Geben Sie einen Namen für das Speicherkonto ein.</span><span class="sxs-lookup"><span data-stu-id="dd0de-135">Type a name for the storage account.</span></span>

    ![](media/FBCimage15.png)

6. <span data-ttu-id="dd0de-136">Überprüfen Sie, und klicken Sie dann auf **Erstellen** , um das Speicherkonto zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="dd0de-136">Review and then click **Create** to create the storage account.</span></span>

    ![](media/FBCimage16.png)

7. <span data-ttu-id="dd0de-137">Klicken Sie nach einigen Momenten auf **Aktualisieren** , und klicken Sie dann auf **Ressource wechseln** , um zum Speicherkonto zu navigieren.</span><span class="sxs-lookup"><span data-stu-id="dd0de-137">After a few moments, click **Refresh** and then click **Go to resource** to navigate to the storage account.</span></span>

    ![](media/FBCimage17.png)

8. <span data-ttu-id="dd0de-138">Klicken Sie im linken Navigationsbereich auf **Zugriffstasten** .</span><span class="sxs-lookup"><span data-stu-id="dd0de-138">Click **Access keys** in the left navigation pane.</span></span>

    ![](media/FBCimage18.png)

9. <span data-ttu-id="dd0de-139">Kopieren Sie eine **Verbindungszeichenfolge** , und speichern Sie Sie in einer Textdatei oder an einem anderen Speicherort.</span><span class="sxs-lookup"><span data-stu-id="dd0de-139">Copy a **Connection string** and save it to a text file or other storage location.</span></span> <span data-ttu-id="dd0de-140">Verwenden Sie diese Option, wenn Sie eine Webanwendungs Ressource erstellen.</span><span class="sxs-lookup"><span data-stu-id="dd0de-140">You use this when creating a web app resource.</span></span>

    ![](media/FBCimage19.png)

## <a name="step-4-create-a-new-web-app-resource-in-azure"></a><span data-ttu-id="dd0de-141">Schritt 4: Erstellen einer neuen webapp-Ressource in Azure</span><span class="sxs-lookup"><span data-stu-id="dd0de-141">Step 4: Create a new web app resource in Azure</span></span>

1. <span data-ttu-id="dd0de-142">Klicken Sie auf der **Start** Seite im Azure-Portal auf **Ressource \> : alles \> -Webanwendung erstellen**.</span><span class="sxs-lookup"><span data-stu-id="dd0de-142">On the **Home** page in the Azure portal, click **Create a resource \> Everything \> Web app**.</span></span> <span data-ttu-id="dd0de-143">Klicken Sie auf der Seite **Webanwendung** auf **Erstellen**.</span><span class="sxs-lookup"><span data-stu-id="dd0de-143">On the **Web app** page, click **Create**.</span></span> 

   ![](media/FBCimage20.png)

2. <span data-ttu-id="dd0de-144">Geben Sie die Details ein (wie unten dargestellt), und erstellen Sie dann die Webanwendung.</span><span class="sxs-lookup"><span data-stu-id="dd0de-144">Fill in the details (as shown below) and then create the Web app.</span></span> <span data-ttu-id="dd0de-145">Beachten Sie, dass der Name, den Sie im Feld **App-Name** eingeben, zum Erstellen der Azure-App-Dienst-URL verwendet wird. Beispiel: FBconnector.azurewebsites.net.</span><span class="sxs-lookup"><span data-stu-id="dd0de-145">Note that the name that you enter in the **App name** box is used to create the Azure app service URL; for example, fbconnector.azurewebsites.net.</span></span>

   ![](media/FBCimage21.png)

3. <span data-ttu-id="dd0de-146">Wechseln Sie zur neu erstellten Webanwendungs-Ressource, und klicken Sie im linken Navigationsbereich auf **Anwendungseinstellungen** .</span><span class="sxs-lookup"><span data-stu-id="dd0de-146">Go to the newly created web app resource, click **Application Settings** in the left navigation pane.</span></span> <span data-ttu-id="dd0de-147">Klicken Sie unter Anwendungseinstellungen auf neue Einstellung hinzufügen, und fügen Sie die folgenden drei Einstellungen hinzu: Verwenden Sie die Werte (die Sie in die Textdatei aus den vorherigen Schritten kopiert haben):</span><span class="sxs-lookup"><span data-stu-id="dd0de-147">Under Application settings, click Add new setting and add the following three settings: Use the values (that you copied to the text file from the previous steps):</span></span> 

    <span data-ttu-id="dd0de-148">– **APISecretKey** – Sie können einen beliebigen Wert als geheimen Schlüssel eingeben.</span><span class="sxs-lookup"><span data-stu-id="dd0de-148">– **APISecretKey** – You can type any value as the secret.</span></span> <span data-ttu-id="dd0de-149">Dieser wird für den Zugriff auf die Connector-Webanwendung in Schritt 7 verwendet.</span><span class="sxs-lookup"><span data-stu-id="dd0de-149">This is used to access the connector web app in Step 7.</span></span>

    <span data-ttu-id="dd0de-150">– \* \* StorageAccountConnectionString – der Verbindungszeichenfolgen-URI, den Sie nach dem Erstellen des Azure-speicherkontos in Schritt 3 kopiert haben.</span><span class="sxs-lookup"><span data-stu-id="dd0de-150">– \*\*StorageAccountConnectionString — The connection string Uri that you copied after creating the Azure storage account in Step 3.</span></span>

    <span data-ttu-id="dd0de-151">– **Mandanten** Kennung – die Mandanten-ID Ihrer Office 365 Organisation, die Sie nach dem Erstellen der Facebook-Connector-app in Azure Active Directory in Schritt 2 kopiert haben.</span><span class="sxs-lookup"><span data-stu-id="dd0de-151">– **tenantId** – The tenant ID of your Office 365 organization that you copied after creating the Facebook connector app in Azure Active Directory in Step 2.</span></span>

    ![](media/FBCimage22.png)

4. <span data-ttu-id="dd0de-152">Klicken Sie unter **Allgemeine Einstellungen** **auf neben** dem **immer ein**.</span><span class="sxs-lookup"><span data-stu-id="dd0de-152">Under **General settings**, click **On** next to the **Always On**.</span></span> <span data-ttu-id="dd0de-153">Klicken Sie oben auf der Seite auf **Speichern** , um Anwendungseinstellungen zu speichern.</span><span class="sxs-lookup"><span data-stu-id="dd0de-153">Click **Save** at the top of the page to save application settings.</span></span>

   ![](media/FBCimage23.png)

5. <span data-ttu-id="dd0de-154">Der letzte Schritt besteht darin, den Quellcode der Connector-app in Azure hochzuladen, den Sie in Schritt 1 heruntergeladen haben.</span><span class="sxs-lookup"><span data-stu-id="dd0de-154">The final step is to upload the connector app source code to Azure that you downloaded in Step 1.</span></span> <span data-ttu-id="dd0de-155">Wechseln Sie in einem Webbrowser zu https://<AzureAppResourceName>. SCM.azurewebsites.net/ZipDeployUi.</span><span class="sxs-lookup"><span data-stu-id="dd0de-155">In a web browser, go to https://<AzureAppResourceName>.scm.azurewebsites.net/ZipDeployUi.</span></span> <span data-ttu-id="dd0de-156">Wenn beispielsweise der Name Ihrer Azure-App-Ressource (die Sie in Schritt 2 in diesem Abschnitt genannt haben) **FBconnector**lautet, gehen Sie zu https://fbconnector.scm.azurewebsites.net/ZipDeployUi.</span><span class="sxs-lookup"><span data-stu-id="dd0de-156">For example, if the name of your Azure app resource (which you named in step 2 in this section) is **fbconnector**, then you would go to https://fbconnector.scm.azurewebsites.net/ZipDeployUi.</span></span> 

6. <span data-ttu-id="dd0de-157">Ziehen Sie das SampleConnector. zip-Menü (das Sie in Schritt 1 heruntergeladen haben) auf diese Seite.</span><span class="sxs-lookup"><span data-stu-id="dd0de-157">Drag and drop the SampleConnector.zip (that you downloaded in Step 1) to this page.</span></span> <span data-ttu-id="dd0de-158">Nachdem die Dateien hochgeladen wurden und die Bereitstellung erfolgreich war, sieht die Seite wie im folgenden Screenshot aus:</span><span class="sxs-lookup"><span data-stu-id="dd0de-158">After the files are uploaded and the deployment is successful, the page will look similar to the following screenshot:</span></span>

   ![](media/FBCimage24.png)

## <a name="step-5-register-the-facebook-app"></a><span data-ttu-id="dd0de-159">Schritt 5: Registrieren der Facebook-App</span><span class="sxs-lookup"><span data-stu-id="dd0de-159">Step 5: Register the Facebook app</span></span>

1. <span data-ttu-id="dd0de-160">Wechseln Sie <https://developers.facebook.com>zu, melden Sie sich mit den Anmeldeinformationen für das Konto für die Facebook-Geschäfts Seiten Ihrer Organisation an, und klicken Sie dann auf **neue APP hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="dd0de-160">Go to <https://developers.facebook.com>, log in using the credentials for the account for your organization’s Facebook Business pages, and then click **Add New App**.</span></span>

   ![](media/FBCimage25.png)

2. <span data-ttu-id="dd0de-161">Erstellen Sie eine neue APP-ID.</span><span class="sxs-lookup"><span data-stu-id="dd0de-161">Create a new app ID.</span></span>

   ![](media/FBCimage26.png)

3. <span data-ttu-id="dd0de-162">Klicken Sie im linken Navigationsbereich auf **Produkte hinzufügen** , und klicken Sie dann auf der **Facebook-Anmelde** Kachel auf **Einrichten** .</span><span class="sxs-lookup"><span data-stu-id="dd0de-162">In the left navigation pane, click **Add Products** and then click **Set Up** in the **Facebook Login** tile.</span></span>

   ![](media/FBCimage27.png)

4. <span data-ttu-id="dd0de-163">Klicken Sie auf der Seite Facebook-Anmeldung einbinden auf **Website**.</span><span class="sxs-lookup"><span data-stu-id="dd0de-163">On the Integrate Facebook Login page, click **Web**.</span></span>

   ![](media/FBCimage28.png)

5. <span data-ttu-id="dd0de-164">Hinzufügen der Azure-App-Dienst-URL zum Beispiel https://fbconnector.azurewebsites.net.</span><span class="sxs-lookup"><span data-stu-id="dd0de-164">Add the Azure app service URL; for example https://fbconnector.azurewebsites.net.</span></span>

   ![](media/FBCimage29.png)

6. <span data-ttu-id="dd0de-165">Schließen Sie den Abschnitt Quick Start im Facebook-Anmelde Setup ab.</span><span class="sxs-lookup"><span data-stu-id="dd0de-165">Complete the QuickStart section of the Facebook Login setup.</span></span>

   ![](media/FBCimage30.png)

7. <span data-ttu-id="dd0de-166">Klicken Sie im linken Navigationsbereich unter **Facebook-Anmeldung**auf **Einstellungen**, und fügen Sie den OAuth-Umleitungs-URI im Feld **gültige OAuth-Umleitungs-URIs** hinzu.</span><span class="sxs-lookup"><span data-stu-id="dd0de-166">In the left navigation pane under **Facebook Login**, click **Settings**, and add the OAuth redirect URI in the **Valid OAuth Redirect URIs** box.</span></span> <span data-ttu-id="dd0de-167">Verwenden Sie das Format \*\* \<connectorserviceuri>/views/facebookoauth\*\*, wobei der Wert für connectorserviceuri die Azure-App-Dienst-URL für Ihre Organisation ist. Beispiel: https://fbconnector.azurewebsites.net.</span><span class="sxs-lookup"><span data-stu-id="dd0de-167">Use the format **\<connectorserviceuri>/Views/FacebookOAuth**, where the value for connectorserviceuri is the Azure app service URL for your organization; for example, https://fbconnector.azurewebsites.net.</span></span>

   ![](media/FBCimage31.png)

8. <span data-ttu-id="dd0de-168">Klicken Sie im linken Navigationsbereich auf **Produkte hinzufügen** , und klicken Sie dann auf **webhooks.**</span><span class="sxs-lookup"><span data-stu-id="dd0de-168">In the left navigation pane, click **Add Products** and then click **Webhooks.**</span></span> <span data-ttu-id="dd0de-169">Klicken Sie im Pulldown-Menü **Seite** auf **Seite**.</span><span class="sxs-lookup"><span data-stu-id="dd0de-169">In the **Page** pull-down menu, click **Page**.</span></span> 

   ![](media/FBCimage32.png)

9. <span data-ttu-id="dd0de-170">Fügen Sie die webhooks-Rückruf-URL hinzu, und fügen Sie ein Verify-Token hinzu.</span><span class="sxs-lookup"><span data-stu-id="dd0de-170">Add Webhooks Callback URL and add a verify token.</span></span> <span data-ttu-id="dd0de-171">Das Format der Rückruf-URL, verwenden Sie das Format \*\* <connectorserviceuri>/API/FbPageWebhook\*\*, wobei der Wert für connectorserviceuri die Azure-App-Dienst-URL für Ihre Organisation ist. zum Beispiel https://fbconnector.azurewebsites.net.</span><span class="sxs-lookup"><span data-stu-id="dd0de-171">The format of the callback URL, use the format **<connectorserviceuri>/api/FbPageWebhook**, where the value for connectorserviceuri is the Azure app service URL for your organization; for example https://fbconnector.azurewebsites.net.</span></span> 

    <span data-ttu-id="dd0de-172">Das Verify-Token sollte einem starken Kennwort ähneln.</span><span class="sxs-lookup"><span data-stu-id="dd0de-172">The verify token should similar to a strong password.</span></span> <span data-ttu-id="dd0de-173">Kopieren Sie das Verify-Token in eine Textdatei oder einen anderen Speicherort.</span><span class="sxs-lookup"><span data-stu-id="dd0de-173">Copy the verify token to a text file or other storage location.</span></span>

     ![](media/FBCimage33.png)

10. <span data-ttu-id="dd0de-174">Testen und Abonnieren des Endpunkts für Feeds.</span><span class="sxs-lookup"><span data-stu-id="dd0de-174">Test and subscribe to the endpoint for feed.</span></span>

    ![](media/FBCimage34.png)

11. <span data-ttu-id="dd0de-175">Fügen Sie eine Datenschutz-URL, ein App-Symbol und eine geschäftliche Verwendung hinzu.</span><span class="sxs-lookup"><span data-stu-id="dd0de-175">Add a privacy URL, app icon, and business use.</span></span> <span data-ttu-id="dd0de-176">Kopieren Sie außerdem die APP-ID und den App-Schlüssel in eine Textdatei oder einen anderen Speicherort.</span><span class="sxs-lookup"><span data-stu-id="dd0de-176">Also, copy the app ID and app secret to a text file or other storage location.</span></span>

    ![](media/FBCimage35.png)

12. <span data-ttu-id="dd0de-177">Machen Sie die APP öffentlich.</span><span class="sxs-lookup"><span data-stu-id="dd0de-177">Make the app public.</span></span>

    ![](media/FBCimage36.png)

13. <span data-ttu-id="dd0de-178">Fügen Sie der Administrator-oder Tester-Rolle einen Benutzer hinzu.</span><span class="sxs-lookup"><span data-stu-id="dd0de-178">Add user to the admin or tester role.</span></span>

    ![](media/FBCimage37.png)

14. <span data-ttu-id="dd0de-179">Fügen Sie die **Seite öffentliche Inhalts Zugriffs** Berechtigung hinzu.</span><span class="sxs-lookup"><span data-stu-id="dd0de-179">Add the **Page Public Content Access** permission.</span></span>

    ![](media/FBCimage38.png)

15. <span data-ttu-id="dd0de-180">Berechtigung zum Hinzufügen von Seiten verwalten.</span><span class="sxs-lookup"><span data-stu-id="dd0de-180">Add Manage Pages permission.</span></span>

    ![](media/FBCimage39.png)

16. <span data-ttu-id="dd0de-181">Holen Sie sich die Anwendung von Facebook überprüft.</span><span class="sxs-lookup"><span data-stu-id="dd0de-181">Get the application reviewed by Facebook.</span></span>

    ![](media/FBCimage40.png)

## <a name="step-6-configure-the-connector-web-app"></a><span data-ttu-id="dd0de-182">Schritt 6: Konfigurieren der Connector-Webanwendung</span><span class="sxs-lookup"><span data-stu-id="dd0de-182">Step 6: Configure the connector web app</span></span>

1. <span data-ttu-id="dd0de-183">Wechseln Sie zu\<https://AzureAppResourceName>. azurewebsites.net (wobei AzureAppResourceName der Name Ihrer Azure-App-Ressource ist, die Sie in Schritt 4 benannt haben) Wenn beispielsweise der Name **FBconnector**lautet https://fbconnector.azurewebsites.net, wechseln Sie zu.</span><span class="sxs-lookup"><span data-stu-id="dd0de-183">Go to https://\<AzureAppResourceName>.azurewebsites.net (where AzureAppResourceName is the name of your Azure app resource that you named in Step 4) For example, if the name is **fbconnector**, go to https://fbconnector.azurewebsites.net.</span></span> <span data-ttu-id="dd0de-184">Die Startseite der APP sieht wie im folgenden Screenshot aus:</span><span class="sxs-lookup"><span data-stu-id="dd0de-184">The home page of the app will look like the following screenshot:</span></span>


   ![](media/FBCimage41.png)

2. <span data-ttu-id="dd0de-185">Klicken Sie auf **Konfigurieren** , um eine Anmeldeseite anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="dd0de-185">Click **Configure** to display a sign in page.</span></span>
 
   ![](media/FBCimage42.png)

3. <span data-ttu-id="dd0de-186">Geben Sie in das Feld Mandanten-ID die Mandanten-ID ein, die Sie in Schritt 2 erhalten haben, oder fügen Sie Sie ein.</span><span class="sxs-lookup"><span data-stu-id="dd0de-186">In the Tenant Id box, type or paste your tenant Id (that you obtained in Step 2).</span></span> <span data-ttu-id="dd0de-187">Geben Sie in das Feld Kennwort den APISecretKey (den Sie in Schritt 2 erhalten haben) ein, oder fügen Sie ihn ein, und klicken Sie dann auf **Konfigurationseinstellungen festlegen** , um die Seite **Konfigurations Details** anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="dd0de-187">In the password box, type or paste the APISecretKey (that you obtained in Step 2), and then click **Set Configuration Settings** to display the **Configuration Details** page.</span></span>

    ![](media/FBCimage43.png)


4. <span data-ttu-id="dd0de-188">Geben Sie unter **Konfigurations Details**die folgenden Konfigurationseinstellungen ein:</span><span class="sxs-lookup"><span data-stu-id="dd0de-188">Under **Configuration Details**, enter the following configuration settings</span></span> 

   <span data-ttu-id="dd0de-189">– **Facebook-Anwendungs-ID** – die APP-ID für die Facebook-Anwendung, die Sie in Schritt 5 erhalten haben.</span><span class="sxs-lookup"><span data-stu-id="dd0de-189">– **Facebook application ID** – The app ID for the Facebook application that you obtained in Step 5.</span></span>
   <span data-ttu-id="dd0de-190">– **Facebook-Anwendungs Geheimnis** – der APP-Schlüssel für die Facebook-Anwendung, die Sie in Schritt 5 erhalten haben.</span><span class="sxs-lookup"><span data-stu-id="dd0de-190">– **Facebook application secret** – The app secret for the Facebook application that you obtained in Step 5.</span></span>
   <span data-ttu-id="dd0de-191">– **Facebook webhooks Überprüfen des Tokens** – das Überprüfen-Token, das Sie in Schritt 5 erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="dd0de-191">– **Facebook webhooks verify token** – The verify token that you created in Step 5.</span></span>
   <span data-ttu-id="dd0de-192">– **Aad-Anwendungs-ID** – die Anwendungs-ID für die Azure Active Directory-APP, die Sie in Schritt 2 erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="dd0de-192">– **AAD application ID** – The application ID for the Azure Active Directory app that you created in Step 2.</span></span>
   <span data-ttu-id="dd0de-193">– **Aad-Anwendungs Geheimnis** – der Wert für den geheimen Schlüssel "APISecretKey", den Sie in Schritt 4 erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="dd0de-193">– **AAD application secret** – The value for the APISecretKey secret that you created in Step 4.</span></span>
   <span data-ttu-id="dd0de-194">– **Aad Application URI** – der in Schritt 2 abgerufene Aad-Anwendungs-URI; Beispiel: https://microsoft.onmicrosoft.com/2688yu6n-12q3-23we-e3ee-121111123213.</span><span class="sxs-lookup"><span data-stu-id="dd0de-194">– **AAD application Uri** – The AAD application Uri obtained in Step 2; for example, https://microsoft.onmicrosoft.com/2688yu6n-12q3-23we-e3ee-121111123213.</span></span>
   <span data-ttu-id="dd0de-195">– **App Insights Instrumentation Key** – lassen Sie dieses Feld leer.</span><span class="sxs-lookup"><span data-stu-id="dd0de-195">– **App insights instrumentation key** – Leave this box blank.</span></span>

5. <span data-ttu-id="dd0de-196">Klicken Sie auf **Speichern** , um die Verbindungseinstellungen zu speichern.</span><span class="sxs-lookup"><span data-stu-id="dd0de-196">Click **Save** to save the connector settings.</span></span>

## <a name="step-7-set-up-a-custom-connector-in-the-security--compliance-center"></a><span data-ttu-id="dd0de-197">Schritt 7: Einrichten eines benutzerdefinierten Connectors im Security #a0 Compliance Center</span><span class="sxs-lookup"><span data-stu-id="dd0de-197">Step 7: Set up a custom connector in the Security & Compliance Center</span></span>

1. <span data-ttu-id="dd0de-198">Wechseln Sie <https://protection.office.com> zu, und klicken Sie dann auf **Data Governance \> Import \> Archivieren von drittanbieterdaten**.</span><span class="sxs-lookup"><span data-stu-id="dd0de-198">Go to <https://protection.office.com> and then click **Data governance \> Import \> Archive third-party data**.</span></span>

   ![](media/FBCimage44.png)

2.  <span data-ttu-id="dd0de-199">Klicken Sie auf **Connector hinzufügen** , und klicken Sie dann auf **Facebook-Seiten**.</span><span class="sxs-lookup"><span data-stu-id="dd0de-199">Click **Add a connector** and then click **Facebook pages**.</span></span>

    ![](media/FBCimage46.png)

3.  <span data-ttu-id="dd0de-200">Geben Sie auf der Seite " **Connector-app hinzufügen** " die folgenden Informationen ein, und klicken Sie dann auf **Connector überprüfen**.</span><span class="sxs-lookup"><span data-stu-id="dd0de-200">On the **Add Connector App** page, enter the following information and then click **Validate connector**.</span></span>

    <span data-ttu-id="dd0de-201">– Geben Sie im ersten Feld einen Namen für den Connector ein, beispielsweise **Facebook**.</span><span class="sxs-lookup"><span data-stu-id="dd0de-201">– In the first box, type a name for the connector, such as **Facebook**.</span></span>
    <span data-ttu-id="dd0de-202">– Geben Sie im zweiten Feld den Wert des APISecretKey ein, den Sie in Schritt 4 hinzugefügt haben, oder fügen Sie ihn ein.</span><span class="sxs-lookup"><span data-stu-id="dd0de-202">– In the second box, type or paste the value of the APISecretKey that you added in Step 4.</span></span>
    <span data-ttu-id="dd0de-203">– Geben Sie im dritten Feld die Azure-App-Dienst-URL ein, oder fügen Sie Sie ein. zum Beispiel **https://fbconnector.azurewebsites.net**.</span><span class="sxs-lookup"><span data-stu-id="dd0de-203">– In the third box, type or paste the Azure app service URL; for example **https://fbconnector.azurewebsites.net**.</span></span>
 
    <span data-ttu-id="dd0de-204">Nachdem der Connector erfolgreich überprüft wurde, klicken Sie auf **weiter**.</span><span class="sxs-lookup"><span data-stu-id="dd0de-204">After the connector is successfully validated, click **Next**.</span></span>
    
    ![](media/FBCimage47.png)

4.  <span data-ttu-id="dd0de-205">Klicken Sie auf **Anmeldung mit der Connector-App**.</span><span class="sxs-lookup"><span data-stu-id="dd0de-205">Click **Login with Connector App**.</span></span>

    ![](media/FBCimage45.png)

5. <span data-ttu-id="dd0de-206">Geben Sie den APISecretKey erneut ein, oder fügen Sie ihn ein, und klicken Sie dann auf **Login to Connector Service**.</span><span class="sxs-lookup"><span data-stu-id="dd0de-206">Type or paste the APISecretKey again and then click  **Login to Connector Service**.</span></span>

   ![](media/FBCimage48.png)


6. <span data-ttu-id="dd0de-207">Klicken Sie auf **Anmelden bei Facebook.**</span><span class="sxs-lookup"><span data-stu-id="dd0de-207">Click **Login with Facebook.**</span></span>

   ![](media/FBCimage49.png)

7. <span data-ttu-id="dd0de-208">Melden Sie sich auf der Seite **Anmelden bei Facebook** mit den Anmeldeinformationen für das Konto für die Facebook-Geschäfts Seiten Ihrer Organisation an.</span><span class="sxs-lookup"><span data-stu-id="dd0de-208">On the **Log in to Facebook** page, log in using the credentials for the account for your organization’s Facebook Business pages.</span></span> <span data-ttu-id="dd0de-209">Stellen Sie sicher, dass das Facebook-Konto, an dem Sie sich angemeldet haben, der Administratorrolle für die Facebook-Geschäfts Seiten Ihrer Organisation zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="dd0de-209">Make sure the Facebook account that you logged in to is assigned the admin role for your organization’s Facebook Business pages</span></span>

   ![](media/FBCimage50.png)

8. <span data-ttu-id="dd0de-210">Klicken Sie auf **Seiten auswählen** , um die Geschäfts Seiten Ihrer Organisation auszuwählen, die Sie in Office 365 archivieren möchten.</span><span class="sxs-lookup"><span data-stu-id="dd0de-210">Click **Select Pages** to choose your organization’s business pages that you want to archive in Office 365.</span></span>

   ![](media/FBCimage51.png)

9. <span data-ttu-id="dd0de-211">Eine Liste der Geschäfts Seiten, die von dem Facebook-Konto verwaltet werden, in dem Sie sich angemeldet haben, wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="dd0de-211">A list of the Business pages managed by the Facebook account that you logged in to is displayed.</span></span> <span data-ttu-id="dd0de-212">Wählen Sie die zu archivierende Seite aus, und klicken Sie dann auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="dd0de-212">Select the page to archive and then click **Save**.</span></span>

    ![](media/FBCimage52.png)

10. <span data-ttu-id="dd0de-213">Klicken Sie auf **vorbereiten** , um das Setup der Connector-Dienst-APP zu beenden.</span><span class="sxs-lookup"><span data-stu-id="dd0de-213">Click **prepare** to exit the setup of the connector service app.</span></span>

    ![](media/FBCimage53.png)

11. <span data-ttu-id="dd0de-214">Auf der Seite **Filter festlegen** können Sie einen Filter anwenden, um Elemente zu importieren (und archivieren), die ein bestimmtes Alter aufweisen.</span><span class="sxs-lookup"><span data-stu-id="dd0de-214">On the **Set Filters** page, you can apply a filter to import (and archive) items that are a certain age.</span></span> <span data-ttu-id="dd0de-215">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="dd0de-215">Click **Next**.</span></span>

    ![](media/FBCimage54.png)

12. <span data-ttu-id="dd0de-216">Wählen Sie auf der Seite **Speicherkonto festlegen** das Office 365 Postfach aus, in das die Elemente der Facebook-Geschäfts Seiten importiert werden, die Sie zuvor ausgewählt haben.</span><span class="sxs-lookup"><span data-stu-id="dd0de-216">On the **Set Storage Account** page, select the Office 365 mailbox that the items from the Facebook Business pages that you previously selected will be imported to.</span></span>

    ![](media/FBCimage55.png)

13. <span data-ttu-id="dd0de-217">Überprüfen Sie Ihre Einstellungen, und klicken Sie dann auf **Fertig stellen** , um das Connector-Setup im Security #a0 Compliance Center abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="dd0de-217">Review your settings and then click **Finish** to complete the connector setup in the Security & Compliance Center.</span></span>

    ![](media/FBCimage56.png)

14. <span data-ttu-id="dd0de-218">Wechseln Sie zur Seite **Archivieren von drittanbieterdaten** , um den Fortschritt des Importvorgangs anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="dd0de-218">Go to the **Archive third-party data** page to see the progress of the import process.</span></span>

    ![](media/FBCimage58.png)
