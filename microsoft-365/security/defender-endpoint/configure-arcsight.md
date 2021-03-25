---
title: Konfigurieren von Micro Focus ArcSight zum Ziehen von Microsoft Defender for Endpoint-Erkennungen
description: Konfigurieren von Micro Focus ArcSight zum Empfangen und Ziehen von Erkennungen vom Microsoft Defender Security Center
keywords: Konfigurieren von Micro Focus ArcSight, Sicherheitsinformations- und Ereignisverwaltungstools, arcsight
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: a52f810647c387c5a5726b9d31998c34add4092e
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/24/2021
ms.locfileid: "51166185"
---
# <a name="configure-micro-focus-arcsight-to-pull-defender-for-endpoint-detections"></a><span data-ttu-id="941c6-104">Konfigurieren von Micro Focus ArcSight zum Ziehen von Defender for Endpoint-Erkennungen</span><span class="sxs-lookup"><span data-stu-id="941c6-104">Configure Micro Focus ArcSight to pull Defender for Endpoint detections</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="941c6-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="941c6-105">**Applies to:**</span></span>
- [<span data-ttu-id="941c6-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="941c6-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="941c6-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="941c6-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


><span data-ttu-id="941c6-108">Möchten Sie Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="941c6-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="941c6-109">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="941c6-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-configurearcsight-abovefoldlink) 

<span data-ttu-id="941c6-110">Sie müssen einige Dateien und Tools für die Verwendung von Micro Focus ArcSight installieren und konfigurieren, damit Defender for Endpoint-Erkennungen verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="941c6-110">You'll need to install and configure some files and tools to use Micro Focus ArcSight so that it can pull Defender for Endpoint detections.</span></span>

>[!Note]
>- <span data-ttu-id="941c6-111">[Defender for Endpoint Alert](alerts.md) besteht aus einer oder mehreren Erkennungen</span><span class="sxs-lookup"><span data-stu-id="941c6-111">[Defender for Endpoint Alert](alerts.md) is composed from one or more detections</span></span>
>- <span data-ttu-id="941c6-112">[Defender for Endpoint Detection besteht](api-portal-mapping.md) aus dem verdächtigen Ereignis, das auf dem Gerät aufgetreten ist, und den zugehörigen Warnungsdetails.</span><span class="sxs-lookup"><span data-stu-id="941c6-112">[Defender for Endpoint Detection](api-portal-mapping.md) is composed from the suspicious event occurred on the Device and its related Alert details.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="941c6-113">Vorbereitung</span><span class="sxs-lookup"><span data-stu-id="941c6-113">Before you begin</span></span>

<span data-ttu-id="941c6-114">Für die Konfiguration des Micro Focus ArcSight Connector-Tools sind mehrere Konfigurationsdateien erforderlich, um Erkennungen aus Ihrer Azure Active Directory (AAD)-Anwendung zu ziehen und zu analysieren.</span><span class="sxs-lookup"><span data-stu-id="941c6-114">Configuring the Micro Focus ArcSight Connector tool requires several configuration files for it to pull and parse detections from your Azure Active Directory (AAD) application.</span></span>

<span data-ttu-id="941c6-115">In diesem Abschnitt erhalten Sie die erforderlichen Informationen zum ordnungsgemäßen Festlegen und Verwenden der erforderlichen Konfigurationsdateien.</span><span class="sxs-lookup"><span data-stu-id="941c6-115">This section guides you in getting the necessary information to set and use the required configuration files correctly.</span></span>

- <span data-ttu-id="941c6-116">Stellen Sie sicher, dass Sie das SIEM-Integrationsfeature im Menü **Einstellungen aktiviert** haben.</span><span class="sxs-lookup"><span data-stu-id="941c6-116">Make sure you have enabled the SIEM integration feature from the **Settings** menu.</span></span> <span data-ttu-id="941c6-117">Weitere Informationen finden Sie unter [Aktivieren der SIEM-Integration in Defender for Endpoint](enable-siem-integration.md).</span><span class="sxs-lookup"><span data-stu-id="941c6-117">For more information, see [Enable SIEM integration in Defender for Endpoint](enable-siem-integration.md).</span></span>

- <span data-ttu-id="941c6-118">Die Datei, die Sie beim Aktivieren des SIEM-Integrationsfeatures gespeichert haben, ist bereit.</span><span class="sxs-lookup"><span data-stu-id="941c6-118">Have the file you saved from enabling the SIEM integration feature ready.</span></span> <span data-ttu-id="941c6-119">Sie müssen die folgenden Werte erhalten:</span><span class="sxs-lookup"><span data-stu-id="941c6-119">You'll need to get the following values:</span></span>
  - <span data-ttu-id="941c6-120">OAuth 2.0 Tokenaktualisierungs-URL</span><span class="sxs-lookup"><span data-stu-id="941c6-120">OAuth 2.0 Token refresh URL</span></span>
  - <span data-ttu-id="941c6-121">OAuth 2.0-Client-ID</span><span class="sxs-lookup"><span data-stu-id="941c6-121">OAuth 2.0 Client ID</span></span>
  - <span data-ttu-id="941c6-122">OAuth 2.0 Geheimer Clientgeheimnis</span><span class="sxs-lookup"><span data-stu-id="941c6-122">OAuth 2.0 Client secret</span></span>

- <span data-ttu-id="941c6-123">Die folgenden Konfigurationsdateien sind bereit:</span><span class="sxs-lookup"><span data-stu-id="941c6-123">Have the following configuration files ready:</span></span>
  - <span data-ttu-id="941c6-124">WDATP-connector.properties</span><span class="sxs-lookup"><span data-stu-id="941c6-124">WDATP-connector.properties</span></span>
  - <span data-ttu-id="941c6-125">WDATP-connector.jsonparser.properties</span><span class="sxs-lookup"><span data-stu-id="941c6-125">WDATP-connector.jsonparser.properties</span></span>

    <span data-ttu-id="941c6-126">Sie hätten eine ZIP-Datei gespeichert, die diese beiden Dateien enthält, wenn Sie Micro Focus ArcSight als SIEM-Typ ausgewählt haben, den Sie in Ihrer Organisation verwenden.</span><span class="sxs-lookup"><span data-stu-id="941c6-126">You would have saved a .zip file which contains these two files when you chose Micro Focus ArcSight as the SIEM type you use in your organization.</span></span>

- <span data-ttu-id="941c6-127">Stellen Sie sicher, dass Sie die folgenden Token generieren und bereit sind:</span><span class="sxs-lookup"><span data-stu-id="941c6-127">Make sure you generate the following tokens and have them ready:</span></span>
  - <span data-ttu-id="941c6-128">Zugriffstoken</span><span class="sxs-lookup"><span data-stu-id="941c6-128">Access token</span></span>
  - <span data-ttu-id="941c6-129">Aktualisierungstoken</span><span class="sxs-lookup"><span data-stu-id="941c6-129">Refresh token</span></span>

  <span data-ttu-id="941c6-130">Sie können diese Token im Abschnitt **SIEM-Integrationseinrichtung** des Portals generieren.</span><span class="sxs-lookup"><span data-stu-id="941c6-130">You can generate these tokens from the **SIEM integration** setup section of the portal.</span></span>

## <a name="install-and-configure-micro-focus-arcsight-flexconnector"></a><span data-ttu-id="941c6-131">Installieren und Konfigurieren von Micro Focus ArcSight FlexConnector</span><span class="sxs-lookup"><span data-stu-id="941c6-131">Install and configure Micro Focus ArcSight FlexConnector</span></span>

<span data-ttu-id="941c6-132">In den folgenden Schritten wird davon ausgegangen, dass Sie alle erforderlichen Schritte unter [Before you begin abgeschlossen haben.](#before-you-begin)</span><span class="sxs-lookup"><span data-stu-id="941c6-132">The following steps assume that you have completed all the required steps in [Before you begin](#before-you-begin).</span></span>

1. <span data-ttu-id="941c6-133">Installieren Sie das neueste 32-Bit-Windows FlexConnector-Installationsprogramm.</span><span class="sxs-lookup"><span data-stu-id="941c6-133">Install the latest 32-bit Windows FlexConnector installer.</span></span> <span data-ttu-id="941c6-134">Dies finden Sie im HPE Software Center.</span><span class="sxs-lookup"><span data-stu-id="941c6-134">You can find this in the HPE Software center.</span></span> <span data-ttu-id="941c6-135">Das Tool wird in der Regel am folgenden Standardspeicherort installiert: `C:\Program Files\ArcSightFlexConnectors\current\bin` .</span><span class="sxs-lookup"><span data-stu-id="941c6-135">The tool is typically installed in the following default location: `C:\Program Files\ArcSightFlexConnectors\current\bin`.</span></span></br></br><span data-ttu-id="941c6-136">Sie können auswählen, wo das Tool gespeichert werden soll, z. B. C: \\ *folder_location*\current\bin, wobei folder_location Installationsspeicherort darstellt. </span><span class="sxs-lookup"><span data-stu-id="941c6-136">You can choose where to save the tool, for example C:\\*folder_location*\current\bin where *folder_location* represents the installation location.</span></span>

2. <span data-ttu-id="941c6-137">Führen Sie den Installationsassistenten durch die folgenden Aufgaben aus:</span><span class="sxs-lookup"><span data-stu-id="941c6-137">Follow the installation wizard through the following tasks:</span></span>
   - <span data-ttu-id="941c6-138">Einführung</span><span class="sxs-lookup"><span data-stu-id="941c6-138">Introduction</span></span>
   - <span data-ttu-id="941c6-139">Wählen Sie Ordner installieren aus</span><span class="sxs-lookup"><span data-stu-id="941c6-139">Choose Install Folder</span></span>
   - <span data-ttu-id="941c6-140">Wählen Sie Installationssatz aus.</span><span class="sxs-lookup"><span data-stu-id="941c6-140">Choose Install Set</span></span>
   - <span data-ttu-id="941c6-141">Auswählen des Verknüpfungsordners</span><span class="sxs-lookup"><span data-stu-id="941c6-141">Choose Shortcut Folder</span></span>
   - <span data-ttu-id="941c6-142">Zusammenfassung vor der Installation</span><span class="sxs-lookup"><span data-stu-id="941c6-142">Pre-Installation Summary</span></span>
   - <span data-ttu-id="941c6-143">Installieren...</span><span class="sxs-lookup"><span data-stu-id="941c6-143">Installing...</span></span>

   <span data-ttu-id="941c6-144">Sie können die Standardwerte für jede dieser Aufgaben behalten oder die Auswahl an Ihre Anforderungen anpassen.</span><span class="sxs-lookup"><span data-stu-id="941c6-144">You can keep the default values for each of these tasks or modify the selection to suit your requirements.</span></span>

3. <span data-ttu-id="941c6-145">Öffnen Sie den Datei-Explorer, und suchen Sie die beiden Konfigurationsdateien, die Sie beim Aktivieren des SIEM-Integrationsfeatures gespeichert haben.</span><span class="sxs-lookup"><span data-stu-id="941c6-145">Open File Explorer and locate the two configuration files you saved when you enabled the SIEM integration feature.</span></span> <span data-ttu-id="941c6-146">Legen Sie die beiden Dateien am Installationsspeicherort von FlexConnector ab, z. B.:</span><span class="sxs-lookup"><span data-stu-id="941c6-146">Put the two files in the FlexConnector installation location, for example:</span></span>

   - <span data-ttu-id="941c6-147">WDATP-connector.jsonparser.properties: C: \\ *folder_location*\current\user\agent\flexagent</span><span class="sxs-lookup"><span data-stu-id="941c6-147">WDATP-connector.jsonparser.properties: C:\\*folder_location*\current\user\agent\flexagent</span></span>\

   - <span data-ttu-id="941c6-148">WDATP-connector.properties: C: \\ *folder_location*\current\user\agent\flexagent</span><span class="sxs-lookup"><span data-stu-id="941c6-148">WDATP-connector.properties: C:\\*folder_location*\current\user\agent\flexagent</span></span>\

   > [!NOTE]
   > 
   > <span data-ttu-id="941c6-149">Sie müssen die Konfigurationsdateien an  diesem Speicherort speichern, folder_location dem Speicherort darstellt, an dem Sie das Tool installiert haben.</span><span class="sxs-lookup"><span data-stu-id="941c6-149">You must put the configuration files in this location, where *folder_location* represents the location where you installed the tool.</span></span>

4. <span data-ttu-id="941c6-150">Nachdem die Installation des Hauptconnector abgeschlossen ist, wird das Fenster Connector-Setup geöffnet.</span><span class="sxs-lookup"><span data-stu-id="941c6-150">After the installation of the core connector completes, the Connector Setup window opens.</span></span> <span data-ttu-id="941c6-151">Wählen Sie im Fenster Connectoreinrichtung die Option **Connector hinzufügen aus.**</span><span class="sxs-lookup"><span data-stu-id="941c6-151">In the Connector Setup window, select **Add a Connector**.</span></span>

5. <span data-ttu-id="941c6-152">Wählen Sie Typ: **ArcSight FlexConnector REST aus,** und klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="941c6-152">Select Type: **ArcSight FlexConnector REST** and click **Next**.</span></span>

6. <span data-ttu-id="941c6-153">Geben Sie die folgenden Informationen im Formular parameterdetails ein.</span><span class="sxs-lookup"><span data-stu-id="941c6-153">Type the following information in the parameter details form.</span></span> <span data-ttu-id="941c6-154">Alle anderen Werte im Formular sind optional und können leer gelassen werden.</span><span class="sxs-lookup"><span data-stu-id="941c6-154">All other values in the form are optional and can be left blank.</span></span>

   <table>
    <tbody style="vertical-align:top;">
    <tr>
    <th><span data-ttu-id="941c6-155">Feld</span><span class="sxs-lookup"><span data-stu-id="941c6-155">Field</span></span></th>
    <th><span data-ttu-id="941c6-156">Wert</span><span class="sxs-lookup"><span data-stu-id="941c6-156">Value</span></span></th>
    </tr>
    <tr>
    <td><span data-ttu-id="941c6-157">Konfigurationsdatei</span><span class="sxs-lookup"><span data-stu-id="941c6-157">Configuration File</span></span></td>
    <td><span data-ttu-id="941c6-158">Geben Sie den Namen der Clienteigenschaftsdatei ein.</span><span class="sxs-lookup"><span data-stu-id="941c6-158">Type in the name of the client property file.</span></span> <span data-ttu-id="941c6-159">Der Name muss mit der Datei übereinstimmen, die in der heruntergeladenen ZIP-Datei enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="941c6-159">The name must match the file provided in the .zip that you downloaded.</span></span>
<span data-ttu-id="941c6-160">Wenn die Konfigurationsdatei im Verzeichnis flexagent beispielsweise den Namen &quot; &quot;WDATP-Connector.js&quot; onparser.properties hat, müssen Sie &quot; &quot; WDATP-Connector &quot; als Namen der Clienteigenschaftsdatei eingeben.</span><span class="sxs-lookup"><span data-stu-id="941c6-160">For example, if the configuration file in &quot;flexagent&quot; directory is named &quot;WDATP-Connector.jsonparser.properties&quot;, you must type &quot;WDATP-Connector&quot; as the name of the client property file.</span></span></td>
    </tr>
    <td><span data-ttu-id="941c6-161">Ereignis-URL</span><span class="sxs-lookup"><span data-stu-id="941c6-161">Events URL</span></span></td>
    <td><span data-ttu-id="941c6-162">Wählen Sie je nach Standort Ihres Rechenzentrums entweder die EU- oder die US-URL aus:</span><span class="sxs-lookup"><span data-stu-id="941c6-162">Depending on the location of your datacenter, select either the EU or the US URL:</span></span> </br></br> <span data-ttu-id="941c6-163"><b>Für EU</b>: https:// <i></i> wdatp-alertexporter-eu.windows.com/api/alerts/?sinceTimeUtc=$START_AT_TIME</span><span class="sxs-lookup"><span data-stu-id="941c6-163"><b>For EU</b>:  https://<i></i>wdatp-alertexporter-eu.windows.com/api/alerts/?sinceTimeUtc=$START_AT_TIME</span></span> <br>
   </br><span data-ttu-id="941c6-164"><b>For US:</b> https:// <i></i> wdatp-alertexporter-us.windows.com/api/alerts/?sinceTimeUtc=$START_AT_TIME</span><span class="sxs-lookup"><span data-stu-id="941c6-164"><b>For US:</b> https://<i></i>wdatp-alertexporter-us.windows.com/api/alerts/?sinceTimeUtc=$START_AT_TIME</span></span> <br> <br> <span data-ttu-id="941c6-165"><b>For UK</b>: https:// <i></i> wdatp-alertexporter-uk.windows.com/api/alerts/?sinceTimeUtc=$START_AT_TIME</span><span class="sxs-lookup"><span data-stu-id="941c6-165"><b>For UK</b>:  https://<i></i>wdatp-alertexporter-uk.windows.com/api/alerts/?sinceTimeUtc=$START_AT_TIME</span></span></td>
    <tr>
    <td><span data-ttu-id="941c6-166">Authentifizierungstyp</span><span class="sxs-lookup"><span data-stu-id="941c6-166">Authentication Type</span></span></td>
    <td><span data-ttu-id="941c6-167">OAuth 2</span><span class="sxs-lookup"><span data-stu-id="941c6-167">OAuth 2</span></span></td>
    </tr>
    <td><span data-ttu-id="941c6-168">OAuth 2-Clienteigenschaftendatei</span><span class="sxs-lookup"><span data-stu-id="941c6-168">OAuth 2 Client Properties file</span></span></td>
    <td><span data-ttu-id="941c6-169">Navigieren Sie zum Speicherort der <em>Datei wdatp-connector.properties.</em></span><span class="sxs-lookup"><span data-stu-id="941c6-169">Browse to the location of the <em>wdatp-connector.properties</em> file.</span></span> <span data-ttu-id="941c6-170">Der Name muss mit der Datei übereinstimmen, die in der heruntergeladenen ZIP-Datei enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="941c6-170">The name must match the file provided in the .zip that you downloaded.</span></span></td>
    <tr>
    <td><span data-ttu-id="941c6-171">Aktualisierungstoken</span><span class="sxs-lookup"><span data-stu-id="941c6-171">Refresh Token</span></span></td>
    <td><span data-ttu-id="941c6-172">Sie können ein Aktualisierungstoken auf zwei Arten abrufen: durch Generieren eines Aktualisierungstokens auf der <b>Seite mit den SIEM-Einstellungen</b> oder mithilfe des Restutil-Tools.</span><span class="sxs-lookup"><span data-stu-id="941c6-172">You can obtain a refresh token in two ways: by generating a refresh token from the <b>SIEM settings</b> page or using the restutil tool.</span></span> <br><br> <span data-ttu-id="941c6-173">Weitere Informationen zum Generieren eines <b>Aktualisierungstokens</b> aus dem Setup der Einstellungen finden Sie unter Aktivieren der <a href="enable-siem-integration.md" data-raw-source="[Enable SIEM integration in Defender for Endpoint](enable-siem-integration.md)">SIEM-Integration in Defender for Endpoint</a>.</span><span class="sxs-lookup"><span data-stu-id="941c6-173">For more information on generating a refresh token from the <b>Preferences setup</b> , see <a href="enable-siem-integration.md" data-raw-source="[Enable SIEM integration in Defender for Endpoint](enable-siem-integration.md)">Enable SIEM integration in Defender for Endpoint</a>.</span></span> </br> </br><span data-ttu-id="941c6-174"><b>Mit dem restutil-Tool können Sie Ihr Aktualisierungstoken erhalten:</b> </span><span class="sxs-lookup"><span data-stu-id="941c6-174"><b>Get your refresh token using the restutil tool:</b> </span></span></br> <span data-ttu-id="941c6-175">a.</span><span class="sxs-lookup"><span data-stu-id="941c6-175">a.</span></span> <span data-ttu-id="941c6-176">Öffnen Sie eine Eingabeaufforderung.</span><span class="sxs-lookup"><span data-stu-id="941c6-176">Open a command prompt.</span></span> <span data-ttu-id="941c6-177">Navigieren Sie zu C:\<em>folder_location</em>\current\bin, folder_location den Speicherort darstellt, an dem Sie das Tool installiert haben. <em></em></span><span class="sxs-lookup"><span data-stu-id="941c6-177">Navigate to C:\<em>folder_location</em>\current\bin where <em>folder_location</em> represents the location where you installed the tool.</span></span> </br></br> <span data-ttu-id="941c6-178">b.</span><span class="sxs-lookup"><span data-stu-id="941c6-178">b.</span></span> <span data-ttu-id="941c6-179">Typ: <code>arcsight restutil token -config</code> aus dem Bin-Verzeichnis. Beispiel: <b>arcsight restutil boxtoken -proxy proxy.location.hp.com:8080</b> ein Webbrowserfenster wird geöffnet.</span><span class="sxs-lookup"><span data-stu-id="941c6-179">Type: <code>arcsight restutil token -config</code> from the bin directory.For example: <b>arcsight restutil boxtoken -proxy proxy.location.hp.com:8080</b> A Web browser window will open.</span></span> </br> </br><span data-ttu-id="941c6-180">c.</span><span class="sxs-lookup"><span data-stu-id="941c6-180">c.</span></span> <span data-ttu-id="941c6-181">Geben Sie Ihre Anmeldeinformationen ein, und klicken Sie dann auf das Kennwortfeld, damit die Seite umgeleitet wird.</span><span class="sxs-lookup"><span data-stu-id="941c6-181">Type in your credentials then click on the password field to let the page redirect.</span></span> <span data-ttu-id="941c6-182">Geben Sie in der Anmeldeaufforderung Ihre Anmeldeinformationen ein.</span><span class="sxs-lookup"><span data-stu-id="941c6-182">In the login prompt, enter your credentials.</span></span> </br> </br><span data-ttu-id="941c6-183">d.</span><span class="sxs-lookup"><span data-stu-id="941c6-183">d.</span></span> <span data-ttu-id="941c6-184">In der Eingabeaufforderung wird ein Aktualisierungstoken angezeigt.</span><span class="sxs-lookup"><span data-stu-id="941c6-184">A refresh token is shown in the command prompt.</span></span> </br></br> <span data-ttu-id="941c6-185">e.</span><span class="sxs-lookup"><span data-stu-id="941c6-185">e.</span></span> <span data-ttu-id="941c6-186">Kopieren Sie sie, und fügen Sie sie in das <b>Feld Aktualisierungstoken</b> ein.</span><span class="sxs-lookup"><span data-stu-id="941c6-186">Copy and paste it into the <b>Refresh Token</b> field.</span></span>
    </td>
    </tr>
    </tr>
    </table><br/>
    
7. <span data-ttu-id="941c6-187">Ein Browserfenster wird vom Connector geöffnet.</span><span class="sxs-lookup"><span data-stu-id="941c6-187">A browser window is opened by the connector.</span></span> <span data-ttu-id="941c6-188">Melden Sie sich mit Ihren Anmeldeinformationen an.</span><span class="sxs-lookup"><span data-stu-id="941c6-188">Login with your application credentials.</span></span> <span data-ttu-id="941c6-189">Nach der Anmeldung werden Sie aufgefordert, Ihrem OAuth2-Client die Berechtigung zu erteilen.</span><span class="sxs-lookup"><span data-stu-id="941c6-189">After you log in, you'll be asked to give permission to your OAuth2 Client.</span></span> <span data-ttu-id="941c6-190">Sie müssen Ihrem OAuth 2-Client die Berechtigung erteilen, damit die Connectorkonfiguration authentifiziert werden kann.</span><span class="sxs-lookup"><span data-stu-id="941c6-190">You must give permission to your OAuth 2 Client so that the connector configuration can authenticate.</span></span>

   <span data-ttu-id="941c6-191">Wenn es <code>redirect_uri</code> sich bei der um eine https-URL handelt, werden Sie zu einer URL auf dem lokalen Host umgeleitet.</span><span class="sxs-lookup"><span data-stu-id="941c6-191">If the <code>redirect_uri</code> is a https URL, you'll be redirected to a URL on the local host.</span></span> <span data-ttu-id="941c6-192">Es wird eine Seite angezeigt, die anfordert, dem Zertifikat zu vertrauen, das vom Connector bereitgestellt wird, der auf dem lokalen Host ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="941c6-192">You'll see a page that requests for you to trust the certificate supplied by the connector running on the local host.</span></span> <span data-ttu-id="941c6-193">Sie müssen diesem Zertifikat vertrauen, wenn redirect_uri https ist.</span><span class="sxs-lookup"><span data-stu-id="941c6-193">You'll need to trust this certificate if the redirect_uri is a https.</span></span>
   
   <span data-ttu-id="941c6-194">Wenn Sie jedoch eine http-URL für die redirect_uri, müssen Sie keine Zustimmung zum Vertrauen des Zertifikats erteilen.</span><span class="sxs-lookup"><span data-stu-id="941c6-194">If however you specify a http URL for the redirect_uri, you do not need to provide consent in trusting the certificate.</span></span>

8. <span data-ttu-id="941c6-195">Fahren Sie mit der Connectoreinrichtung fort, indem Sie zum Fenster Micro Focus ArcSight Connector Setup zurückkehren.</span><span class="sxs-lookup"><span data-stu-id="941c6-195">Continue with the connector setup by returning to the Micro Focus ArcSight Connector Setup window.</span></span>

9. <span data-ttu-id="941c6-196">Wählen Sie **den ArcSight Manager (verschlüsselt)** als Ziel aus, und klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="941c6-196">Select the **ArcSight Manager (encrypted)** as the destination and click **Next**.</span></span>

10. <span data-ttu-id="941c6-197">Geben Sie die Ziel-IP/Hostname in **Manager Hostname** und Ihre Anmeldeinformationen im Parameterformular ein.</span><span class="sxs-lookup"><span data-stu-id="941c6-197">Type in the destination IP/hostname in **Manager Hostname** and your credentials in the parameters form.</span></span> <span data-ttu-id="941c6-198">Alle anderen Werte im Formular sollten mit den Standardwerten beibehalten werden.</span><span class="sxs-lookup"><span data-stu-id="941c6-198">All other values in the form should be retained with the default values.</span></span> <span data-ttu-id="941c6-199">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="941c6-199">Click **Next**.</span></span>

11. <span data-ttu-id="941c6-200">Geben Sie im Connectordetailseformular einen Namen für den Connector ein.</span><span class="sxs-lookup"><span data-stu-id="941c6-200">Type in a name for the connector in the connector details form.</span></span> <span data-ttu-id="941c6-201">Alle anderen Werte im Formular sind optional und können leer gelassen werden.</span><span class="sxs-lookup"><span data-stu-id="941c6-201">All other values in the form are optional and can be left blank.</span></span> <span data-ttu-id="941c6-202">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="941c6-202">Click **Next**.</span></span>

12. <span data-ttu-id="941c6-203">Das Importzertifikatfenster des ESM-Managers wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="941c6-203">The ESM Manager import certificate window is shown.</span></span> <span data-ttu-id="941c6-204">Wählen **Sie Zertifikat vom Ziel in Connector importieren aus,** und klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="941c6-204">Select **Import the certificate to connector from destination** and click **Next**.</span></span> <span data-ttu-id="941c6-205">Das **Fenster Connector-Zusammenfassung** hinzufügen wird angezeigt, und das Zertifikat wird importiert.</span><span class="sxs-lookup"><span data-stu-id="941c6-205">The **Add connector Summary** window is displayed and the certificate is imported.</span></span>

13. <span data-ttu-id="941c6-206">Stellen Sie sicher, dass die Details im **Fenster** Connector-Zusammenfassung hinzufügen korrekt sind, und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="941c6-206">Verify that the details in the **Add connector Summary** window is correct, then click **Next**.</span></span>

14. <span data-ttu-id="941c6-207">Wählen **Sie Als Dienst installieren aus,** und klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="941c6-207">Select **Install as a service** and click **Next**.</span></span>

15. <span data-ttu-id="941c6-208">Geben Sie einen Namen in das **Feld Dienst interner Name** ein.</span><span class="sxs-lookup"><span data-stu-id="941c6-208">Type a name in the **Service Internal Name** field.</span></span> <span data-ttu-id="941c6-209">Alle anderen Werte im Formular können mit den Standardwerten beibehalten oder leer gelassen werden.</span><span class="sxs-lookup"><span data-stu-id="941c6-209">All other values in the form can be retained with the default values or left blank .</span></span> <span data-ttu-id="941c6-210">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="941c6-210">Click **Next**.</span></span>

16. <span data-ttu-id="941c6-211">Geben Sie die Dienstparameter ein, und klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="941c6-211">Type in the service parameters and click **Next**.</span></span> <span data-ttu-id="941c6-212">Ein Fenster mit der **Installationsdienstzusammenfassung** wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="941c6-212">A window with the **Install Service Summary** is shown.</span></span> <span data-ttu-id="941c6-213">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="941c6-213">Click **Next**.</span></span>

17. <span data-ttu-id="941c6-214">Beenden Sie die Installation, indem Sie **Exit und** **Next auswählen.**</span><span class="sxs-lookup"><span data-stu-id="941c6-214">Finish the installation by selecting **Exit** and **Next**.</span></span>

## <a name="install-and-configure-the-micro-focus-arcsight-console"></a><span data-ttu-id="941c6-215">Installieren und Konfigurieren der Micro Focus ArcSight-Konsole</span><span class="sxs-lookup"><span data-stu-id="941c6-215">Install and configure the Micro Focus ArcSight console</span></span>

1. <span data-ttu-id="941c6-216">Führen Sie den Installationsassistenten durch die folgenden Aufgaben aus:</span><span class="sxs-lookup"><span data-stu-id="941c6-216">Follow the installation wizard through the following tasks:</span></span>
   - <span data-ttu-id="941c6-217">Einführung</span><span class="sxs-lookup"><span data-stu-id="941c6-217">Introduction</span></span>
   - <span data-ttu-id="941c6-218">Lizenzvertrag</span><span class="sxs-lookup"><span data-stu-id="941c6-218">License Agreement</span></span>
   - <span data-ttu-id="941c6-219">Sonderbenachrichtigung</span><span class="sxs-lookup"><span data-stu-id="941c6-219">Special Notice</span></span>
   - <span data-ttu-id="941c6-220">Auswählen des ArcSight-Installationsverzeichnisses</span><span class="sxs-lookup"><span data-stu-id="941c6-220">Choose ArcSight installation directory</span></span>
   - <span data-ttu-id="941c6-221">Auswählen des Verknüpfungsordners</span><span class="sxs-lookup"><span data-stu-id="941c6-221">Choose Shortcut Folder</span></span>
   - <span data-ttu-id="941c6-222">Zusammenfassung vor der Installation</span><span class="sxs-lookup"><span data-stu-id="941c6-222">Pre-Installation Summary</span></span>

2. <span data-ttu-id="941c6-223">Klicken Sie auf **Installieren**.</span><span class="sxs-lookup"><span data-stu-id="941c6-223">Click **Install**.</span></span> <span data-ttu-id="941c6-224">Nach Abschluss der Installation wird der Assistent für die Konfiguration der ArcSight-Konsole geöffnet.</span><span class="sxs-lookup"><span data-stu-id="941c6-224">After the installation completes, the ArcSight Console Configuration Wizard opens.</span></span>

3. <span data-ttu-id="941c6-225">Geben Sie localhost im **Managerhostnamen** und 8443 im **Managerport ein,** und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="941c6-225">Type localhost in **Manager Host Name** and 8443 in **Manager Port** then click **Next**.</span></span>

4. <span data-ttu-id="941c6-226">Wählen **Sie Direkte Verbindung verwenden** aus, und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="941c6-226">Select **Use direct connection**, then click **Next**.</span></span>

5. <span data-ttu-id="941c6-227">Wählen **Sie Kennwortbasierte Authentifizierung** aus, und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="941c6-227">Select **Password Based Authentication**, then click **Next**.</span></span>

6. <span data-ttu-id="941c6-228">Wählen **Sie This is a single user installation aus. (Empfohlen)**, und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="941c6-228">Select **This is a single user installation. (Recommended)**, then click **Next**.</span></span>

7. <span data-ttu-id="941c6-229">Klicken Sie **auf Fertig,** um das Installationsprogramm zu beenden.</span><span class="sxs-lookup"><span data-stu-id="941c6-229">Click **Done** to quit the installer.</span></span>

8. <span data-ttu-id="941c6-230">Melden Sie sich bei der Micro Focus ArcSight-Konsole an.</span><span class="sxs-lookup"><span data-stu-id="941c6-230">Login to the Micro Focus ArcSight console.</span></span>

9. <span data-ttu-id="941c6-231">Navigieren Sie zu **Active channel set** New  >  **Condition**  >    >  **Device Device Product**.</span><span class="sxs-lookup"><span data-stu-id="941c6-231">Navigate to **Active channel set** > **New Condition** > **Device** > **Device Product**.</span></span>

10. <span data-ttu-id="941c6-232">Set **Device Product = Microsoft Defender ATP**.</span><span class="sxs-lookup"><span data-stu-id="941c6-232">Set **Device Product = Microsoft Defender ATP**.</span></span> <span data-ttu-id="941c6-233">Wenn Sie überprüft haben, dass Ereignisse an das Tool fließen, beenden Sie den Prozess erneut, und wechseln Sie zu Windows Services, und starten Sie den ArcSight FlexConnector REST.</span><span class="sxs-lookup"><span data-stu-id="941c6-233">When you've verified that events are flowing to the tool, stop the process again and go to Windows Services and start the ArcSight FlexConnector REST.</span></span>

<span data-ttu-id="941c6-234">Sie können jetzt Abfragen in der Micro Focus ArcSight-Konsole ausführen.</span><span class="sxs-lookup"><span data-stu-id="941c6-234">You can now run queries in the Micro Focus ArcSight console.</span></span>

<span data-ttu-id="941c6-235">Defender for Endpoint-Erkennungen werden als diskrete Ereignisse mit "Microsoft" als Anbieter und "Windows Defender ATP" als Gerätename angezeigt.</span><span class="sxs-lookup"><span data-stu-id="941c6-235">Defender for Endpoint detections will appear as discrete events, with "Microsoft” as the vendor and “Windows Defender ATP” as the device name.</span></span>


## <a name="troubleshooting-micro-focus-arcsight-connection"></a><span data-ttu-id="941c6-236">Problembehandlung bei der Micro Focus ArcSight-Verbindung</span><span class="sxs-lookup"><span data-stu-id="941c6-236">Troubleshooting Micro Focus ArcSight connection</span></span>

<span data-ttu-id="941c6-237">**Problem:** Fehler beim Aktualisieren des Tokens.</span><span class="sxs-lookup"><span data-stu-id="941c6-237">**Problem:** Failed to refresh the token.</span></span> <span data-ttu-id="941c6-238">Sie finden das Protokoll in C: \\ *folder_location*\current\logs, wobei folder_location den Speicherort darstellt, an dem Sie das Tool installiert haben. </span><span class="sxs-lookup"><span data-stu-id="941c6-238">You can find the log located in C:\\*folder_location*\current\logs where *folder_location* represents the location where you installed the tool.</span></span> <span data-ttu-id="941c6-239">Öffnen _Sie agent.log,_ und suchen Sie nach `ERROR/FATAL/WARN` .</span><span class="sxs-lookup"><span data-stu-id="941c6-239">Open _agent.log_ and look for `ERROR/FATAL/WARN`.</span></span>

<span data-ttu-id="941c6-240">**Symptom:** Die folgende Fehlermeldung wird angezeigt:</span><span class="sxs-lookup"><span data-stu-id="941c6-240">**Symptom:** You get the following error message:</span></span>

`Failed to refresh the token. Set reauthenticate to true: com.arcsight.common.al.e: Failed to refresh access token: status=HTTP/1.1 400 Bad Request FATAL EXCEPTION: Could not refresh the access token`

<span data-ttu-id="941c6-241">**Lösung:**</span><span class="sxs-lookup"><span data-stu-id="941c6-241">**Solution:**</span></span>

1. <span data-ttu-id="941c6-242">Beenden Sie den Vorgang, indem Sie im Connectorfenster auf STRG + C klicken.</span><span class="sxs-lookup"><span data-stu-id="941c6-242">Stop the process by clicking Ctrl + C on the Connector window.</span></span> <span data-ttu-id="941c6-243">Klicken **Sie auf Y,** wenn Sie "Batchauftrag Y/N beenden?" gefragt werden.</span><span class="sxs-lookup"><span data-stu-id="941c6-243">Click **Y** when asked "Terminate batch job Y/N?".</span></span>

2. <span data-ttu-id="941c6-244">Navigieren Sie zu dem Ordner, in dem Sie die Datei WDATP-connector.properties gespeichert haben, und bearbeiten Sie sie, um den folgenden Wert hinzuzufügen: `reauthenticate=true` .</span><span class="sxs-lookup"><span data-stu-id="941c6-244">Navigate to the folder where you stored the WDATP-connector.properties file and edit it to add the following value: `reauthenticate=true`.</span></span>

3. <span data-ttu-id="941c6-245">Starten Sie den Connector neu, indem Sie den folgenden Befehl ausführen: `arcsight.bat connectors` .</span><span class="sxs-lookup"><span data-stu-id="941c6-245">Restart the connector by running the following command: `arcsight.bat connectors`.</span></span>

   <span data-ttu-id="941c6-246">Ein Browserfenster wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="941c6-246">A browser window appears.</span></span> <span data-ttu-id="941c6-247">Lassen Sie die Ausführung zu, es sollte ausgeblendet werden, und der Connector sollte nun ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="941c6-247">Allow it to run, it should disappear, and the connector should now be running.</span></span>

> [!NOTE]
> <span data-ttu-id="941c6-248">Stellen Sie sicher, dass der Connector ausgeführt wird, indem Sie den Prozess erneut beenden.</span><span class="sxs-lookup"><span data-stu-id="941c6-248">Verify that the connector is running by stopping the process again.</span></span> <span data-ttu-id="941c6-249">Starten Sie dann den Connector erneut, und es sollte kein Browserfenster angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="941c6-249">Then start the connector again, and no browser window should appear.</span></span>

## <a name="related-topics"></a><span data-ttu-id="941c6-250">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="941c6-250">Related topics</span></span>
- [<span data-ttu-id="941c6-251">Aktivieren der SIEM-Integration in Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="941c6-251">Enable SIEM integration in Defender for Endpoint</span></span>](enable-siem-integration.md)
- [<span data-ttu-id="941c6-252">Ziehen von Erkennungen an Ihre SIEM-Tools</span><span class="sxs-lookup"><span data-stu-id="941c6-252">Pull detections to your SIEM tools</span></span>](/windows/security/threat-protection/microsoft-defender-atp/configure-siem)
- [<span data-ttu-id="941c6-253">Pull Defender for Endpoint-Erkennungen mithilfe der REST-API</span><span class="sxs-lookup"><span data-stu-id="941c6-253">Pull Defender for Endpoint detections using REST API</span></span>](pull-alerts-using-rest-api.md)
- [<span data-ttu-id="941c6-254">Problembehandlung bei der Integration von SIEM-Tools</span><span class="sxs-lookup"><span data-stu-id="941c6-254">Troubleshoot SIEM tool integration issues</span></span>](troubleshoot-siem.md)
