---
title: Bereitstellen eines Connectors zum Archivieren von Facebook-Daten
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
ms.openlocfilehash: e1ab281b8a3b684f408f80f86246778a9ee6267d
ms.sourcegitcommit: 0ad0092d9c5cb2d69fc70c990a9b7cc03140611b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/19/2019
ms.locfileid: "40806258"
---
# <a name="deploy-a-connector-to-archive-facebook-data"></a><span data-ttu-id="7f727-104">Bereitstellen eines Connectors zum Archivieren von Facebook-Daten</span><span class="sxs-lookup"><span data-stu-id="7f727-104">Deploy a connector to archive Facebook data</span></span>

<span data-ttu-id="7f727-105">Dieser Artikel enthält den schrittweisen Prozess zur Bereitstellungeines Connectors, der den Office 365 Import Dienst verwendet, um Daten von Facebook-Geschäfts Seiten in Office 365 zu importieren.</span><span class="sxs-lookup"><span data-stu-id="7f727-105">This article contains the step-by-step process to deploy a connector that uses the Office 365 Import service to import data from Facebook Business pages to Office 365.</span></span> <span data-ttu-id="7f727-106">Eine allgemeine Übersicht über diesen Prozess und eine Liste der erforderlichen Voraussetzungen für die Bereitstellungeines Facebook-Konnektors finden Sie unter [Verwenden eines Beispiel-Konnektors zum Archivieren von Facebook-Daten in Office 365 (Preview)](archive-facebook-data-with-sample-connector.md).</span><span class="sxs-lookup"><span data-stu-id="7f727-106">For a high-level overview of this process and a list of prerequisites required to deploy a Facebook connector, see [Use a sample connector to archive Facebook data in Office 365 (Preview)](archive-facebook-data-with-sample-connector.md).</span></span> 

## <a name="step-1-download-the-package"></a><span data-ttu-id="7f727-107">Schritt 1: Herunterladen des Pakets</span><span class="sxs-lookup"><span data-stu-id="7f727-107">Step 1: Download the package</span></span>

<span data-ttu-id="7f727-108">Laden Sie das vorgefertigte Paket aus dem Abschnitt Release im GitHub-Repository unter <https://github.com/Microsoft/m365-sample-connector-csharp-aspnet/releases>herunter.</span><span class="sxs-lookup"><span data-stu-id="7f727-108">Download the prebuilt package from the Release section in the GitHub repository at <https://github.com/Microsoft/m365-sample-connector-csharp-aspnet/releases>.</span></span> <span data-ttu-id="7f727-109">Laden Sie die ZIP-Datei mit dem Namen **SampleConnector. zip**unter der neuesten Version herunter.</span><span class="sxs-lookup"><span data-stu-id="7f727-109">Under the latest release, download the zip file named **SampleConnector.zip**.</span></span> <span data-ttu-id="7f727-110">Sie laden diese ZIP-Datei in Schritt 4 in Azure hoch.</span><span class="sxs-lookup"><span data-stu-id="7f727-110">You upload this zip file to Azure in Step 4.</span></span>

## <a name="step-2-create-an-app-in-azure-active-directory"></a><span data-ttu-id="7f727-111">Schritt 2: Erstellen einer APP in Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="7f727-111">Step 2: Create an app in Azure Active Directory</span></span>

1. <span data-ttu-id="7f727-112">Wechseln Sie <https://portal.azure.com> zu, und melden Sie sich mit den Anmeldeinformationen eines Office 365 globalen Administratorkontos an.</span><span class="sxs-lookup"><span data-stu-id="7f727-112">Go to <https://portal.azure.com> and sign in using the credentials of an Office 365 global admin account.</span></span>

    ![Erstellen einer APP in Aad](media/FBCimage1.png)

2. <span data-ttu-id="7f727-114">Klicken Sie im linken Navigationsbereich auf **Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="7f727-114">In the left navigation pane, click **Azure Active Directory**.</span></span>

    ![Klicken Sie auf Azure Active Directory](media/FBCimage2.png)

3. <span data-ttu-id="7f727-116">Klicken Sie im linken Navigationsbereich auf **App-Registrierungen (Vorschau)** , und klicken Sie dann auf **neue Registrierung**.</span><span class="sxs-lookup"><span data-stu-id="7f727-116">In the left navigation pane, click **App registrations (Preview)** and then click **New registration**.</span></span>

    ![Klicken Sie auf \* \* App-Registrierungen (Vorschau) \* \* und dann auf \* \* neue Registrierung \* \*](media/FBCimage3.png)

4. <span data-ttu-id="7f727-118">Registrieren Sie die Anwendung.</span><span class="sxs-lookup"><span data-stu-id="7f727-118">Register the application.</span></span> <span data-ttu-id="7f727-119">Wählen Sie unter Umleitungs-URI die Option Webin der Dropdownliste <https://portal.azure.com> Anwendungstyp aus, und geben Sie dann in das Feld für den URI ein.</span><span class="sxs-lookup"><span data-stu-id="7f727-119">Under Redirect URI, select Web in the application type dropdown list and then type <https://portal.azure.com> in the box for the URI.</span></span>

   ![Registrieren der App](media/FBCimage4.png)

5. <span data-ttu-id="7f727-121">Kopieren Sie die Anwendungs-ID **(Client) ID** und **Verzeichnis (Mandanten)** , und speichern Sie Sie in einer Textdatei oder an einem anderen sicheren Ort.</span><span class="sxs-lookup"><span data-stu-id="7f727-121">Copy the **Application (client) ID** and **Directory (tenant) ID** and save them to a text file or other safe location.</span></span> <span data-ttu-id="7f727-122">Sie verwenden diese IDs in späteren Schritten.</span><span class="sxs-lookup"><span data-stu-id="7f727-122">You use these IDs in later steps.</span></span>

   ![Kopieren Sie die Anwendungs-ID und die Verzeichnis-ID, und speichern Sie Sie.](media/FBCimage5.png)

6. <span data-ttu-id="7f727-124">Wechseln Sie zu **Zertifikaten #a0 Geheimnisse für die neue APP.**</span><span class="sxs-lookup"><span data-stu-id="7f727-124">Go to **Certificates & secrets for the new app.**</span></span>

   ![Wechseln Sie zu Zertifikaten #a0 Geheimnisse für die neue APP.](media/FBCimage6.png)

7. <span data-ttu-id="7f727-126">Klicken Sie auf **neuer geheimer Client Schlüssel**</span><span class="sxs-lookup"><span data-stu-id="7f727-126">Click **New client secret**</span></span>

   ![Klicken Sie auf neuer geheimer Client Schlüssel](media/FBCimage7.png)

8. <span data-ttu-id="7f727-128">Erstellen Sie einen neuen geheimen Schlüssel.</span><span class="sxs-lookup"><span data-stu-id="7f727-128">Create a new secret.</span></span> <span data-ttu-id="7f727-129">Geben Sie im Feld Beschreibung den geheimen Schlüssel ein, und wählen Sie dann einen Ablaufzeitraum aus.</span><span class="sxs-lookup"><span data-stu-id="7f727-129">In the description box, type the secret and then choose an expiration period.</span></span> 

    ![Geben Sie den geheimen Schlüssel ein, und wählen Sie dann einen Ablaufzeitraum](media/FBCimage8.png)

9. <span data-ttu-id="7f727-131">Kopieren Sie den Wert des geheimen Schlüssels, und speichern Sie ihn in einer Textdatei oder an einem anderen Speicherort.</span><span class="sxs-lookup"><span data-stu-id="7f727-131">Copy the value of the secret and save it to a text file or other storage location.</span></span> <span data-ttu-id="7f727-132">Dies ist der geheime Aad-Anwendungsschlüssel, den Sie in späteren Schritten verwenden.</span><span class="sxs-lookup"><span data-stu-id="7f727-132">This is the AAD application secret that you use in later steps.</span></span>

   ![Kopieren Sie den Wert des geheimen Schlüssels, und speichern Sie ihn.](media/FBCimage9.png)

10. <span data-ttu-id="7f727-134">Wechseln Sie zu **Manifest** , und kopieren Sie die identifierUris (die auch als Aad Application URI bezeichnet wird) wie im folgenden Screenshot hervorgehoben.</span><span class="sxs-lookup"><span data-stu-id="7f727-134">Go to **Manifest** and copy the identifierUris (which is also called the AAD application Uri) as highlighted in the following screenshot.</span></span> <span data-ttu-id="7f727-135">Kopieren Sie den Aad-Anwendungs-URI in eine Textdatei oder einen anderen Speicherort.</span><span class="sxs-lookup"><span data-stu-id="7f727-135">Copy the AAD application Uri to a text file or other storage location.</span></span> <span data-ttu-id="7f727-136">Sie verwenden Sie in Schritt 6.</span><span class="sxs-lookup"><span data-stu-id="7f727-136">You use it in Step 6.</span></span>

   ![Wechseln Sie zu Manifest, und kopieren Sie den Aad-Anwendungs-URI.](media/FBCimage10.png)

## <a name="step-3-create-an-azure-storage-account"></a><span data-ttu-id="7f727-138">Schritt 3: Erstellen eines Azure-speicherkontos</span><span class="sxs-lookup"><span data-stu-id="7f727-138">Step 3: Create an Azure storage account</span></span>

1. <span data-ttu-id="7f727-139">Wechseln Sie zur Azure-Startseite für Ihre Organisation.</span><span class="sxs-lookup"><span data-stu-id="7f727-139">Go to the Azure home page for your organization.</span></span>

    ![Wechseln zur Azure-Startseite](media/FBCimage11.png)

2. <span data-ttu-id="7f727-141">Klicken Sie auf **Ressource erstellen** , und geben Sie dann **Speicherkonto** in das Suchfeld ein.</span><span class="sxs-lookup"><span data-stu-id="7f727-141">Click **Create a resource** and then type **storage account** in the search box.</span></span>

    ![Klicken Sie auf Ressource erstellen, und geben Sie Speicherkonto ein.](media/FBCimage12.png)

3. <span data-ttu-id="7f727-143">Klicken Sie auf **Speicher**, und klicken Sie dann auf **Speicherkonto**.</span><span class="sxs-lookup"><span data-stu-id="7f727-143">Click **Storage**, and then click **Storage account**.</span></span>

    ![Klicken Sie auf Speicher, und klicken Sie dann auf Speicherkonto](media/FBCimage13.png)

4. <span data-ttu-id="7f727-145">Wählen Sie auf der Seite **Speicherkonto erstellen** im Feld Abonnement die Option **Pay-as-you-go** oder **﻿Kostenlose Testversion** je nach Typ des Azure-Abonnements aus.</span><span class="sxs-lookup"><span data-stu-id="7f727-145">On the **Create storage account** page, in the Subscription box, select **Pay-As-You-Go** or **Free Trial** depending on which type of Azure subscription you have.</span></span> <span data-ttu-id="7f727-146">Wählen Sie dann eine Ressourcengruppe aus, oder erstellen Sie eine.</span><span class="sxs-lookup"><span data-stu-id="7f727-146">Then select or create a resource group.</span></span>

    ![Wählen Sie Pay-as-you-go oder ﻿kostenlose Testversion aus.](media/FBCimage14.png)

5. <span data-ttu-id="7f727-148">Geben Sie einen Namen für das Speicherkonto ein.</span><span class="sxs-lookup"><span data-stu-id="7f727-148">Type a name for the storage account.</span></span>

    ![Geben Sie einen Namen für das Speicherkonto ein.](media/FBCimage15.png)

6. <span data-ttu-id="7f727-150">Überprüfen Sie, und klicken Sie dann auf **Erstellen** , um das Speicherkonto zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="7f727-150">Review and then click **Create** to create the storage account.</span></span>

    ![Erstellen des speicherkontos](media/FBCimage16.png)

7. <span data-ttu-id="7f727-152">Klicken Sie nach einigen Momenten auf **Aktualisieren** , und klicken Sie dann auf **Ressource wechseln** , um zum Speicherkonto zu navigieren.</span><span class="sxs-lookup"><span data-stu-id="7f727-152">After a few moments, click **Refresh** and then click **Go to resource** to navigate to the storage account.</span></span>

    ![Navigieren Sie zum Speicherkonto.](media/FBCimage17.png)

8. <span data-ttu-id="7f727-154">Klicken Sie im linken Navigationsbereich auf **Zugriffstasten** .</span><span class="sxs-lookup"><span data-stu-id="7f727-154">Click **Access keys** in the left navigation pane.</span></span>

    ![Klicken Sie auf Zugriffstasten](media/FBCimage18.png)

9. <span data-ttu-id="7f727-156">Kopieren Sie eine **Verbindungszeichenfolge** , und speichern Sie Sie in einer Textdatei oder an einem anderen Speicherort.</span><span class="sxs-lookup"><span data-stu-id="7f727-156">Copy a **Connection string** and save it to a text file or other storage location.</span></span> <span data-ttu-id="7f727-157">Verwenden Sie diese Option, wenn Sie eine Webanwendungs Ressource erstellen.</span><span class="sxs-lookup"><span data-stu-id="7f727-157">You use this when creating a web app resource.</span></span>

    ![Kopieren einer Verbindungszeichenfolge und speichern](media/FBCimage19.png)

## <a name="step-4-create-a-new-web-app-resource-in-azure"></a><span data-ttu-id="7f727-159">Schritt 4: Erstellen einer neuen webapp-Ressource in Azure</span><span class="sxs-lookup"><span data-stu-id="7f727-159">Step 4: Create a new web app resource in Azure</span></span>

1. <span data-ttu-id="7f727-160">Klicken Sie auf der **Start** Seite im Azure-Portal auf **Ressource \> : alles \> -Webanwendung erstellen**.</span><span class="sxs-lookup"><span data-stu-id="7f727-160">On the **Home** page in the Azure portal, click **Create a resource \> Everything \> Web app**.</span></span> <span data-ttu-id="7f727-161">Klicken Sie auf der Seite **Webanwendung** auf **Erstellen**.</span><span class="sxs-lookup"><span data-stu-id="7f727-161">On the **Web app** page, click **Create**.</span></span> 

   ![Erstellen einer neuen webapp-Ressource](media/FBCimage20.png)

2. <span data-ttu-id="7f727-163">Geben Sie die Details ein (wie unten dargestellt), und erstellen Sie dann die Webanwendung.</span><span class="sxs-lookup"><span data-stu-id="7f727-163">Fill in the details (as shown below) and then create the Web app.</span></span> <span data-ttu-id="7f727-164">Beachten Sie, dass der Name, den Sie im Feld **App-Name** eingeben, zum Erstellen der Azure-App-Dienst-URL verwendet wird. Beispiel: FBconnector.azurewebsites.net.</span><span class="sxs-lookup"><span data-stu-id="7f727-164">Note that the name that you enter in the **App name** box is used to create the Azure app service URL; for example, fbconnector.azurewebsites.net.</span></span>

   ![Geben Sie die Details ein, und erstellen Sie dann die Webanwendung.](media/FBCimage21.png)

3. <span data-ttu-id="7f727-166">Wechseln Sie zur neu erstellten Webanwendungs-Ressource, und klicken Sie im linken Navigationsbereich auf **Anwendungseinstellungen** .</span><span class="sxs-lookup"><span data-stu-id="7f727-166">Go to the newly created web app resource, click **Application Settings** in the left navigation pane.</span></span> <span data-ttu-id="7f727-167">Klicken Sie unter Anwendungseinstellungen auf neue Einstellung hinzufügen, und fügen Sie die folgenden drei Einstellungen hinzu: Verwenden Sie die Werte (die Sie in die Textdatei aus den vorherigen Schritten kopiert haben):</span><span class="sxs-lookup"><span data-stu-id="7f727-167">Under Application settings, click Add new setting and add the following three settings: Use the values (that you copied to the text file from the previous steps):</span></span> 

    - <span data-ttu-id="7f727-168">**APISecretKey** – Sie können einen beliebigen Wert als geheimen Schlüssel eingeben.</span><span class="sxs-lookup"><span data-stu-id="7f727-168">**APISecretKey** – You can type any value as the secret.</span></span> <span data-ttu-id="7f727-169">Dieser wird für den Zugriff auf die Connector-Webanwendung in Schritt 7 verwendet.</span><span class="sxs-lookup"><span data-stu-id="7f727-169">This is used to access the connector web app in Step 7.</span></span>

    - <span data-ttu-id="7f727-170">**StorageAccountConnectionString** – der Verbindungszeichenfolgen-URI, den Sie nach dem Erstellen des Azure-speicherkontos in Schritt 3 kopiert haben.</span><span class="sxs-lookup"><span data-stu-id="7f727-170">**StorageAccountConnectionString** — The connection string Uri that you copied after creating the Azure storage account in Step 3.</span></span>

    - <span data-ttu-id="7f727-171">**Mandanten** Kennung – die Mandanten-ID Ihrer Office 365 Organisation, die Sie nach dem Erstellen der Facebook-Connector-app in Azure Active Directory in Schritt 2 kopiert haben.</span><span class="sxs-lookup"><span data-stu-id="7f727-171">**tenantId** – The tenant ID of your Office 365 organization that you copied after creating the Facebook connector app in Azure Active Directory in Step 2.</span></span>

    ![Geben Sie die Anwendungseinstellungen ein.](media/FBCimage22.png)

4. <span data-ttu-id="7f727-173">Klicken Sie unter **Allgemeine Einstellungen** **auf neben** dem **immer ein**.</span><span class="sxs-lookup"><span data-stu-id="7f727-173">Under **General settings**, click **On** next to the **Always On**.</span></span> <span data-ttu-id="7f727-174">Klicken Sie oben auf der Seite auf **Speichern** , um die Anwendungseinstellungen zu speichern.</span><span class="sxs-lookup"><span data-stu-id="7f727-174">Click **Save** at the top of the page to save the application settings.</span></span>

   ![Speichern der Anwendungseinstellungen](media/FBCimage23.png)

5. <span data-ttu-id="7f727-176">Der letzte Schritt besteht darin, den Quellcode der Connector-app in Azure hochzuladen, den Sie in Schritt 1 heruntergeladen haben.</span><span class="sxs-lookup"><span data-stu-id="7f727-176">The final step is to upload the connector app source code to Azure that you downloaded in Step 1.</span></span> <span data-ttu-id="7f727-177">Wechseln Sie in einem Webbrowser zu https://<AzureAppResourceName>. SCM.azurewebsites.net/ZipDeployUi.</span><span class="sxs-lookup"><span data-stu-id="7f727-177">In a web browser, go to https://<AzureAppResourceName>.scm.azurewebsites.net/ZipDeployUi.</span></span> <span data-ttu-id="7f727-178">Wenn beispielsweise der Name Ihrer Azure-App-Ressource (die Sie in Schritt 2 in diesem Abschnitt genannt haben) **FBconnector**lautet, gehen Sie zu https://fbconnector.scm.azurewebsites.net/ZipDeployUi.</span><span class="sxs-lookup"><span data-stu-id="7f727-178">For example, if the name of your Azure app resource (which you named in step 2 in this section) is **fbconnector**, then you would go to https://fbconnector.scm.azurewebsites.net/ZipDeployUi.</span></span> 

6. <span data-ttu-id="7f727-179">Ziehen Sie das SampleConnector. zip-Menü (das Sie in Schritt 1 heruntergeladen haben) auf diese Seite.</span><span class="sxs-lookup"><span data-stu-id="7f727-179">Drag and drop the SampleConnector.zip (that you downloaded in Step 1) to this page.</span></span> <span data-ttu-id="7f727-180">Nachdem die Dateien hochgeladen wurden und die Bereitstellung erfolgreich war, sieht die Seite wie im folgenden Screenshot aus:</span><span class="sxs-lookup"><span data-stu-id="7f727-180">After the files are uploaded and the deployment is successful, the page will look similar to the following screenshot:</span></span>

   ![Drag & Drop der SampleConnector. zip auf diese Seite](media/FBCimage24.png)

## <a name="step-5-register-the-facebook-app"></a><span data-ttu-id="7f727-182">Schritt 5: Registrieren der Facebook-App</span><span class="sxs-lookup"><span data-stu-id="7f727-182">Step 5: Register the Facebook app</span></span>

1. <span data-ttu-id="7f727-183">Wechseln Sie <https://developers.facebook.com>zu, melden Sie sich mit den Anmeldeinformationen für das Konto für die Facebook-Geschäfts Seiten Ihrer Organisation an, und klicken Sie dann auf **neue APP hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="7f727-183">Go to <https://developers.facebook.com>, log in using the credentials for the account for your organization’s Facebook Business pages, and then click **Add New App**.</span></span>

   ![Hinzufügen einer neuen App für Facebook-Geschäftsseite](media/FBCimage25.png)

2. <span data-ttu-id="7f727-185">Erstellen Sie eine neue APP-ID.</span><span class="sxs-lookup"><span data-stu-id="7f727-185">Create a new app ID.</span></span>

   ![Erstellen einer neuen APP-ID](media/FBCimage26.png)

3. <span data-ttu-id="7f727-187">Klicken Sie im linken Navigationsbereich auf **Produkte hinzufügen** , und klicken Sie dann auf der **Facebook-Anmelde** Kachel auf **Einrichten** .</span><span class="sxs-lookup"><span data-stu-id="7f727-187">In the left navigation pane, click **Add Products** and then click **Set Up** in the **Facebook Login** tile.</span></span>

   ![Klicken Sie auf Produkte hinzufügen.](media/FBCimage27.png)

4. <span data-ttu-id="7f727-189">Klicken Sie auf der Seite Facebook-Anmeldung einbinden auf **Website**.</span><span class="sxs-lookup"><span data-stu-id="7f727-189">On the Integrate Facebook Login page, click **Web**.</span></span>

   ![Klicken Sie auf der Seite Facebook-Anmeldung integrieren auf Website.](media/FBCimage28.png)

5. <span data-ttu-id="7f727-191">Hinzufügen der Azure-App-Dienst-URL zum Beispiel `https://fbconnector.azurewebsites.net`.</span><span class="sxs-lookup"><span data-stu-id="7f727-191">Add the Azure app service URL; for example `https://fbconnector.azurewebsites.net`.</span></span>

   ![Hinzufügen der Azure-App-Dienst-URL](media/FBCimage29.png)

6. <span data-ttu-id="7f727-193">Schließen Sie den Abschnitt Quick Start im Facebook-Anmelde Setup ab.</span><span class="sxs-lookup"><span data-stu-id="7f727-193">Complete the QuickStart section of the Facebook Login setup.</span></span>

   ![Abschließen des Schnellstart-Abschnitts](media/FBCimage30.png)

7. <span data-ttu-id="7f727-195">Klicken Sie im linken Navigationsbereich unter **Facebook-Anmeldung**auf **Einstellungen**, und fügen Sie den OAuth-Umleitungs-URI im Feld **gültige OAuth-Umleitungs-URIs** hinzu.</span><span class="sxs-lookup"><span data-stu-id="7f727-195">In the left navigation pane under **Facebook Login**, click **Settings**, and add the OAuth redirect URI in the **Valid OAuth Redirect URIs** box.</span></span> <span data-ttu-id="7f727-196">Verwenden Sie das Format \*\* \<connectorserviceuri>/views/facebookoauth\*\*, wobei der Wert für connectorserviceuri die Azure-App-Dienst-URL für Ihre Organisation ist. Beispiel: `https://fbconnector.azurewebsites.net`.</span><span class="sxs-lookup"><span data-stu-id="7f727-196">Use the format **\<connectorserviceuri>/Views/FacebookOAuth**, where the value for connectorserviceuri is the Azure app service URL for your organization; for example, `https://fbconnector.azurewebsites.net`.</span></span>

   ![Fügen Sie den OAuth-Umleitungs-URI zum Feld gültige OAuth-Umleitungs-URIs hinzu](media/FBCimage31.png)

8. <span data-ttu-id="7f727-198">Klicken Sie im linken Navigationsbereich auf **Produkte hinzufügen** , und klicken Sie dann auf **webhooks.**</span><span class="sxs-lookup"><span data-stu-id="7f727-198">In the left navigation pane, click **Add Products** and then click **Webhooks.**</span></span> <span data-ttu-id="7f727-199">Klicken Sie im Pulldown-Menü **Seite** auf **Seite**.</span><span class="sxs-lookup"><span data-stu-id="7f727-199">In the **Page** pull-down menu, click **Page**.</span></span> 

   ![Klicken Sie auf Produkte hinzufügen, und klicken Sie dann auf \* \* webhooks.](media/FBCimage32.png)

9. <span data-ttu-id="7f727-201">Fügen Sie die webhooks-Rückruf-URL hinzu, und fügen Sie ein Verify-Token hinzu.</span><span class="sxs-lookup"><span data-stu-id="7f727-201">Add Webhooks Callback URL and add a verify token.</span></span> <span data-ttu-id="7f727-202">Das Format der Rückruf-URL, verwenden Sie das Format \*\* <connectorserviceuri>/API/FbPageWebhook\*\*, wobei der Wert für connectorserviceuri die Azure-App-Dienst-URL für Ihre Organisation ist. zum Beispiel `https://fbconnector.azurewebsites.net`.</span><span class="sxs-lookup"><span data-stu-id="7f727-202">The format of the callback URL, use the format **<connectorserviceuri>/api/FbPageWebhook**, where the value for connectorserviceuri is the Azure app service URL for your organization; for example `https://fbconnector.azurewebsites.net`.</span></span> 

    <span data-ttu-id="7f727-203">Das Verify-Token sollte einem starken Kennwort ähneln.</span><span class="sxs-lookup"><span data-stu-id="7f727-203">The verify token should similar to a strong password.</span></span> <span data-ttu-id="7f727-204">Kopieren Sie das Verify-Token in eine Textdatei oder einen anderen Speicherort.</span><span class="sxs-lookup"><span data-stu-id="7f727-204">Copy the verify token to a text file or other storage location.</span></span>

        ![Add the verify token](media/FBCimage33.png)

10. <span data-ttu-id="7f727-205">Testen und Abonnieren des Endpunkts für Feeds.</span><span class="sxs-lookup"><span data-stu-id="7f727-205">Test and subscribe to the endpoint for feed.</span></span>

    ![Testen und Abonnieren des Endpunkts](media/FBCimage34.png)

11. <span data-ttu-id="7f727-207">Fügen Sie eine Datenschutz-URL, ein App-Symbol und eine geschäftliche Verwendung hinzu.</span><span class="sxs-lookup"><span data-stu-id="7f727-207">Add a privacy URL, app icon, and business use.</span></span> <span data-ttu-id="7f727-208">Kopieren Sie außerdem die APP-ID und den App-Schlüssel in eine Textdatei oder einen anderen Speicherort.</span><span class="sxs-lookup"><span data-stu-id="7f727-208">Also, copy the app ID and app secret to a text file or other storage location.</span></span>

    ![Hinzufügen einer Datenschutz-URL, eines App-Symbols und einer geschäftlichen Verwendung](media/FBCimage35.png)

12. <span data-ttu-id="7f727-210">Machen Sie die APP öffentlich.</span><span class="sxs-lookup"><span data-stu-id="7f727-210">Make the app public.</span></span>

    ![Veröffentlichen der APP](media/FBCimage36.png)

13. <span data-ttu-id="7f727-212">Fügen Sie der Administrator-oder Tester-Rolle einen Benutzer hinzu.</span><span class="sxs-lookup"><span data-stu-id="7f727-212">Add user to the admin or tester role.</span></span>

    ![Hinzufügen eines Benutzers zur Administrator-oder Tester-Rolle](media/FBCimage37.png)

14. <span data-ttu-id="7f727-214">Fügen Sie die **Seite öffentliche Inhalts Zugriffs** Berechtigung hinzu.</span><span class="sxs-lookup"><span data-stu-id="7f727-214">Add the **Page Public Content Access** permission.</span></span>

    ![DD die Seite öffentliche Inhalts Zugriffsberechtigung](media/FBCimage38.png)

15. <span data-ttu-id="7f727-216">Berechtigung zum Hinzufügen von Seiten verwalten.</span><span class="sxs-lookup"><span data-stu-id="7f727-216">Add Manage Pages permission.</span></span>

    ![Berechtigung zum Hinzufügen von Seiten verwalten](media/FBCimage39.png)

16. <span data-ttu-id="7f727-218">Holen Sie sich die Anwendung von Facebook überprüft.</span><span class="sxs-lookup"><span data-stu-id="7f727-218">Get the application reviewed by Facebook.</span></span>

    ![Abrufen der von Facebook überprüften Anwendung](media/FBCimage40.png)

## <a name="step-6-configure-the-connector-web-app"></a><span data-ttu-id="7f727-220">Schritt 6: Konfigurieren der Connector-Webanwendung</span><span class="sxs-lookup"><span data-stu-id="7f727-220">Step 6: Configure the connector web app</span></span>

1. <span data-ttu-id="7f727-221">Wechseln Sie zu\<https://AzureAppResourceName>. azurewebsites.net (wobei AzureAppResourceName der Name Ihrer Azure-App-Ressource ist, die Sie in Schritt 4 benannt haben) Wenn beispielsweise der Name **FBconnector**lautet `https://fbconnector.azurewebsites.net`, wechseln Sie zu.</span><span class="sxs-lookup"><span data-stu-id="7f727-221">Go to https://\<AzureAppResourceName>.azurewebsites.net (where AzureAppResourceName is the name of your Azure app resource that you named in Step 4) For example, if the name is **fbconnector**, go to `https://fbconnector.azurewebsites.net`.</span></span> <span data-ttu-id="7f727-222">Die Startseite der APP sieht wie im folgenden Screenshot aus:</span><span class="sxs-lookup"><span data-stu-id="7f727-222">The home page of the app will look like the following screenshot:</span></span>

   ![Wechseln Sie zur Connector-Webanwendung](media/FBCimage41.png)

2. <span data-ttu-id="7f727-224">Klicken Sie auf **Konfigurieren** , um eine Anmeldeseite anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="7f727-224">Click **Configure** to display a sign in page.</span></span>
 
   ![Klicken Sie auf konfigurieren, um eine Anmeldeseite anzuzeigen.](media/FBCimage42.png)

3. <span data-ttu-id="7f727-226">Geben Sie in das Feld Mandanten-ID die Mandanten-ID ein, die Sie in Schritt 2 erhalten haben, oder fügen Sie Sie ein.</span><span class="sxs-lookup"><span data-stu-id="7f727-226">In the Tenant Id box, type or paste your tenant Id (that you obtained in Step 2).</span></span> <span data-ttu-id="7f727-227">Geben Sie in das Feld Kennwort den APISecretKey (den Sie in Schritt 2 erhalten haben) ein, oder fügen Sie ihn ein, und klicken Sie dann auf **Konfigurationseinstellungen festlegen** , um die Seite **Konfigurations Details** anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="7f727-227">In the password box, type or paste the APISecretKey (that you obtained in Step 2), and then click **Set Configuration Settings** to display the **Configuration Details** page.</span></span>

    ![Melden Sie sich mit Ihrer Mandanten-ID und Ihrem Kennwort an, und wechseln Sie zur Seite Konfigurationsdetails.](media/FBCimage43.png)

4. <span data-ttu-id="7f727-229">Geben Sie unter **Konfigurations Details**die folgenden Konfigurationseinstellungen ein:</span><span class="sxs-lookup"><span data-stu-id="7f727-229">Under **Configuration Details**, enter the following configuration settings</span></span> 

   - <span data-ttu-id="7f727-230">**Facebook-Anwendungs-ID** – die APP-ID für die Facebook-Anwendung, die Sie in Schritt 5 erhalten haben.</span><span class="sxs-lookup"><span data-stu-id="7f727-230">**Facebook application ID** – The app ID for the Facebook application that you obtained in Step 5.</span></span>
   - <span data-ttu-id="7f727-231">**Facebook-Anwendungs Geheimnis** – der APP-Schlüssel für die Facebook-Anwendung, die Sie in Schritt 5 erhalten haben.</span><span class="sxs-lookup"><span data-stu-id="7f727-231">**Facebook application secret** – The app secret for the Facebook application that you obtained in Step 5.</span></span>
   - <span data-ttu-id="7f727-232">**Facebook webhooks Überprüfen des Tokens** – das Überprüfen-Token, das Sie in Schritt 5 erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="7f727-232">**Facebook webhooks verify token** – The verify token that you created in Step 5.</span></span>
   - <span data-ttu-id="7f727-233">**Aad-Anwendungs-ID** – die Anwendungs-ID für die Azure Active Directory-APP, die Sie in Schritt 2 erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="7f727-233">**AAD application ID** – The application ID for the Azure Active Directory app that you created in Step 2.</span></span>
   - <span data-ttu-id="7f727-234">**Aad-Anwendungs Geheimnis** – der Wert für den geheimen Schlüssel "APISecretKey", den Sie in Schritt 4 erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="7f727-234">**AAD application secret** – The value for the APISecretKey secret that you created in Step 4.</span></span>
   - <span data-ttu-id="7f727-235">**Aad-Anwendungs-URI** – der in Schritt 2 abgerufene Aad-Anwendungs-URI; Beispiel: `https://microsoft.onmicrosoft.com/2688yu6n-12q3-23we-e3ee-121111123213`.</span><span class="sxs-lookup"><span data-stu-id="7f727-235">**AAD application Uri** – The AAD application Uri obtained in Step 2; for example, `https://microsoft.onmicrosoft.com/2688yu6n-12q3-23we-e3ee-121111123213`.</span></span>
   - <span data-ttu-id="7f727-236">**App Insights Instrumentation Key** – lassen Sie dieses Feld leer.</span><span class="sxs-lookup"><span data-stu-id="7f727-236">**App insights instrumentation key** – Leave this box blank.</span></span>

5. <span data-ttu-id="7f727-237">Klicken Sie auf **Speichern** , um die Verbindungseinstellungen zu speichern.</span><span class="sxs-lookup"><span data-stu-id="7f727-237">Click **Save** to save the connector settings.</span></span>

## <a name="step-7-set-up-a-custom-connector-in-the-security--compliance-center"></a><span data-ttu-id="7f727-238">Schritt 7: Einrichten eines benutzerdefinierten Connectors im Security #a0 Compliance Center</span><span class="sxs-lookup"><span data-stu-id="7f727-238">Step 7: Set up a custom connector in the Security & Compliance Center</span></span>

1. <span data-ttu-id="7f727-239">Wechseln Sie <https://protection.office.com> zu, und klicken Sie dann auf **Information Governance \> Import \> Archivieren von drittanbieterdaten**.</span><span class="sxs-lookup"><span data-stu-id="7f727-239">Go to <https://protection.office.com> and then click **Information governance \> Import \> Archive third-party data**.</span></span>

   ![Wechseln Sie zum Security and Compliance Center, und klicken Sie auf Information Governance #a0 Import #a1 Archivieren von drittanbieterdaten](media/FBCimage44.png)

2.  <span data-ttu-id="7f727-241">Klicken Sie auf **Connector hinzufügen** , und klicken Sie dann auf **Facebook-Seiten**.</span><span class="sxs-lookup"><span data-stu-id="7f727-241">Click **Add a connector** and then click **Facebook pages**.</span></span>

    ![Hinzufügen eines Facebook-Connectors konfigurieren des Connectors](media/FBCimage46.png)

3.  <span data-ttu-id="7f727-243">Geben Sie auf der Seite " **Connector-app hinzufügen** " die folgenden Informationen ein, und klicken Sie dann auf **Connector überprüfen**.</span><span class="sxs-lookup"><span data-stu-id="7f727-243">On the **Add Connector App** page, enter the following information and then click **Validate connector**.</span></span>

    - <span data-ttu-id="7f727-244">Geben Sie im ersten Feld einen Namen für den Connector ein, beispielsweise **Facebook**.</span><span class="sxs-lookup"><span data-stu-id="7f727-244">In the first box, type a name for the connector, such as **Facebook**.</span></span>
    - <span data-ttu-id="7f727-245">Geben Sie im zweiten Feld den Wert des APISecretKey ein, den Sie in Schritt 4 hinzugefügt haben, oder fügen Sie ihn ein.</span><span class="sxs-lookup"><span data-stu-id="7f727-245">In the second box, type or paste the value of the APISecretKey that you added in Step 4.</span></span>
    - <span data-ttu-id="7f727-246">Geben Sie im dritten Feld die Azure-App-Dienst-URL ein, oder fügen Sie Sie ein. zum Beispiel `https://fbconnector.azurewebsites.net`.</span><span class="sxs-lookup"><span data-stu-id="7f727-246">In the third box, type or paste the Azure app service URL; for example `https://fbconnector.azurewebsites.net`.</span></span>
 
    <span data-ttu-id="7f727-247">Nachdem der Connector erfolgreich überprüft wurde, klicken Sie auf **weiter**.</span><span class="sxs-lookup"><span data-stu-id="7f727-247">After the connector is successfully validated, click **Next**.</span></span>
    
    ![Klicken Sie auf Weiter, nachdem der Connector erfolgreich überprüft wurde](media/FBCimage47.png)

4.  <span data-ttu-id="7f727-249">Klicken Sie auf **Anmeldung mit der Connector-App**.</span><span class="sxs-lookup"><span data-stu-id="7f727-249">Click **Login with Connector App**.</span></span>

    ![Klicken Sie auf Anmeldung mit der Connector-App](media/FBCimage45.png)

5. <span data-ttu-id="7f727-251">Geben Sie den APISecretKey erneut ein, oder fügen Sie ihn ein, und klicken Sie dann auf **Login to Connector Service**.</span><span class="sxs-lookup"><span data-stu-id="7f727-251">Type or paste the APISecretKey again and then click  **Login to Connector Service**.</span></span>

   ![Geben oder fügen Sie den APISecretKey ein, und klicken Sie dann auf die Schaltfläche anmelden.](media/FBCimage48.png)

6. <span data-ttu-id="7f727-253">Klicken Sie auf **Anmelden bei Facebook**.</span><span class="sxs-lookup"><span data-stu-id="7f727-253">Click **Login with Facebook**.</span></span>

   ![Klicken Sie auf \* \* Login bei Facebook](media/FBCimage49.png)

7. <span data-ttu-id="7f727-255">Melden Sie sich auf der Seite **Anmelden bei Facebook** mit den Anmeldeinformationen für das Konto für die Facebook-Geschäfts Seiten Ihrer Organisation an.</span><span class="sxs-lookup"><span data-stu-id="7f727-255">On the **Log in to Facebook** page, log in using the credentials for the account for your organization’s Facebook Business pages.</span></span> <span data-ttu-id="7f727-256">Stellen Sie sicher, dass das Facebook-Konto, an dem Sie sich angemeldet haben, der Administratorrolle für die Facebook-Geschäfts Seiten Ihrer Organisation zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="7f727-256">Make sure the Facebook account that you logged in to is assigned the admin role for your organization’s Facebook Business pages</span></span>

   ![Melden Sie sich bei Facebook an](media/FBCimage50.png)

8. <span data-ttu-id="7f727-258">Klicken Sie auf **Seiten auswählen** , um die Geschäfts Seiten Ihrer Organisation auszuwählen, die Sie in Office 365 archivieren möchten.</span><span class="sxs-lookup"><span data-stu-id="7f727-258">Click **Select Pages** to choose your organization’s business pages that you want to archive in Office 365.</span></span>

   ![Klicken Sie auf Seiten auswählen, um die Geschäfts Seiten Ihrer Organisation anzuzeigen.](media/FBCimage51.png)

9. <span data-ttu-id="7f727-260">Eine Liste der Geschäfts Seiten, die von dem Facebook-Konto verwaltet werden, in dem Sie sich angemeldet haben, wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="7f727-260">A list of the Business pages managed by the Facebook account that you logged in to is displayed.</span></span> <span data-ttu-id="7f727-261">Wählen Sie die zu archivierende Seite aus, und klicken Sie dann auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="7f727-261">Select the page to archive and then click **Save**.</span></span>

    ![Wählen Sie die Geschäftsseite der Organisation aus, die Sie archivieren möchten.](media/FBCimage52.png)

10. <span data-ttu-id="7f727-263">Klicken Sie auf **Fertig stellen** , um das Setup der Connector-Dienst-APP zu beenden.</span><span class="sxs-lookup"><span data-stu-id="7f727-263">Click **Finish** to exit the setup of the connector service app.</span></span>

    ![Klicken Sie auf Fertig stellen, um die Connector Service-APP zu beenden.](media/FBCimage53.png)

11. <span data-ttu-id="7f727-265">Auf der Seite **Filter festlegen** können Sie einen Filter anwenden, um Elemente zu importieren (und archivieren), die ein bestimmtes Alter aufweisen.</span><span class="sxs-lookup"><span data-stu-id="7f727-265">On the **Set Filters** page, you can apply a filter to import (and archive) items that are a certain age.</span></span> <span data-ttu-id="7f727-266">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="7f727-266">Click **Next**.</span></span>

    ![Anwenden eines Filters zum Importieren von Elementen, die ein bestimmtes Alter aufweisen](media/FBCimage54.png)

12. <span data-ttu-id="7f727-268">Wählen Sie auf der Seite **Speicherkonto festlegen** das Office 365 Postfach aus, in das die Elemente der Facebook-Geschäfts Seiten importiert werden, die Sie zuvor ausgewählt haben.</span><span class="sxs-lookup"><span data-stu-id="7f727-268">On the **Set Storage Account** page, select the Office 365 mailbox that the items from the Facebook Business pages that you previously selected will be imported to.</span></span>

    ![Angeben einer Office 365 Post Fach Archiv Elemente, die von Facebook importiert wurden](media/FBCimage55.png)

13. <span data-ttu-id="7f727-270">Überprüfen Sie Ihre Einstellungen, und klicken Sie dann auf **Fertig stellen** , um das Connector-Setup im Security #a0 Compliance Center abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="7f727-270">Review your settings and then click **Finish** to complete the connector setup in the Security & Compliance Center.</span></span>

    ![Überprüfen der Verbindungseinstellungen](media/FBCimage56.png)

14. <span data-ttu-id="7f727-272">Wechseln Sie zur Seite **Archivieren von drittanbieterdaten** , um den Fortschritt des Importvorgangs anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="7f727-272">Go to the **Archive third-party data** page to see the progress of the import process.</span></span>

    ![Wechseln Sie zur Seite Archivieren von drittanbieterdaten, um den Importprozess nachzuverfolgen.](media/FBCimage58.png)
