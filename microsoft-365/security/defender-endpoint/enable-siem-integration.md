---
title: Aktivieren der SIEM-Integration in Microsoft Defender für Endpunkt
description: Aktivieren Sie die SIEM-Integration, um Erkennungen in Ihrer SIEM-Lösung (Security Information and Event Management) zu empfangen.
keywords: Aktivieren von Siem-Connector, Siem, Connector, Sicherheitsinformationen und -ereignissen
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
ms.openlocfilehash: 87078bb7bfc6b38788fea2a6a4c3c9108be1d5b4
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2021
ms.locfileid: "52842962"
---
# <a name="enable-siem-integration-in-microsoft-defender-for-endpoint"></a><span data-ttu-id="80b0b-104">Aktivieren der SIEM-Integration in Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="80b0b-104">Enable SIEM integration in Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="80b0b-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="80b0b-105">**Applies to:**</span></span>
- [<span data-ttu-id="80b0b-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="80b0b-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)


><span data-ttu-id="80b0b-107">Möchten Sie Microsoft Defender für Endpunkt erleben?</span><span class="sxs-lookup"><span data-stu-id="80b0b-107">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="80b0b-108">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="80b0b-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-enablesiem-abovefoldlink) 

<span data-ttu-id="80b0b-109">Aktivieren Sie die SIEM-Integration (Security Information and Event Management), damit Sie Erkennungen aus Microsoft Defender Security Center abrufen können.</span><span class="sxs-lookup"><span data-stu-id="80b0b-109">Enable security information and event management (SIEM) integration so you can pull detections from Microsoft Defender Security Center.</span></span> <span data-ttu-id="80b0b-110">Abrufen von Erkennungen mithilfe Ihrer SIEM-Lösung oder durch direktes Herstellen einer Verbindung mit der REST-API für Erkennungen.</span><span class="sxs-lookup"><span data-stu-id="80b0b-110">Pull detections using your SIEM solution or by connecting directly to the detections REST API.</span></span>

>[!NOTE]
>- <span data-ttu-id="80b0b-111">[Microsoft Defender für Endpunkt-Warnung](alerts.md) besteht aus einer oder mehreren Erkennungen.</span><span class="sxs-lookup"><span data-stu-id="80b0b-111">[Microsoft Defender for Endpoint Alert](alerts.md) is composed from one or more detections.</span></span>
>- <span data-ttu-id="80b0b-112">[Die Microsoft Defender für Endpunkterkennung](api-portal-mapping.md) besteht aus dem verdächtigen Ereignis, das auf dem Gerät aufgetreten ist, und den zugehörigen Warnungsdetails.</span><span class="sxs-lookup"><span data-stu-id="80b0b-112">[Microsoft Defender for Endpoint Detection](api-portal-mapping.md) is composed from the suspicious event occurred on the Device and its related Alert details.</span></span>
>- <span data-ttu-id="80b0b-113">Die Microsoft Defender für Endpunkt-Warnungs-API ist die neueste API für die Benachrichtigungsnutzung und enthält eine detaillierte Liste der zugehörigen Nachweise für jede Warnung.</span><span class="sxs-lookup"><span data-stu-id="80b0b-113">The Microsoft Defender for Endpoint Alert API is the latest API for alert consumption and contain a detailed list of related evidence for each alert.</span></span> <span data-ttu-id="80b0b-114">Weitere Informationen finden Sie unter ["Warnungsmethoden und -eigenschaften"](alerts.md) und ["Warnungen auflisten".](get-alerts.md)</span><span class="sxs-lookup"><span data-stu-id="80b0b-114">For more information, see [Alert methods and properties](alerts.md) and [List alerts](get-alerts.md).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="80b0b-115">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="80b0b-115">Prerequisites</span></span>

- <span data-ttu-id="80b0b-116">Der Benutzer, der die Einstellung aktiviert, muss über Berechtigungen zum Erstellen einer App in Azure Active Directory (AAD) verfügen.</span><span class="sxs-lookup"><span data-stu-id="80b0b-116">The user who activates the setting must have permissions to create an app in Azure Active Directory (AAD).</span></span> <span data-ttu-id="80b0b-117">Dies ist eine Person mit den folgenden Rollen:</span><span class="sxs-lookup"><span data-stu-id="80b0b-117">This is someone with the following roles:</span></span> 

  - <span data-ttu-id="80b0b-118">Sicherheitsadministrator und globaler Administrator</span><span class="sxs-lookup"><span data-stu-id="80b0b-118">Security Administrator and either Global Administrator</span></span>
  - <span data-ttu-id="80b0b-119">Cloudanwendungsadministrator</span><span class="sxs-lookup"><span data-stu-id="80b0b-119">Cloud Application Administrator</span></span>
  - <span data-ttu-id="80b0b-120">Anwendungsadministrator</span><span class="sxs-lookup"><span data-stu-id="80b0b-120">Application Administrator</span></span>
  - <span data-ttu-id="80b0b-121">Besitzer des Dienstprinzipals</span><span class="sxs-lookup"><span data-stu-id="80b0b-121">Owner of the service principal</span></span>

- <span data-ttu-id="80b0b-122">Während der anfänglichen Aktivierung wird ein Popupbildschirm für die Eingabe von Anmeldeinformationen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="80b0b-122">During the initial activation, a pop-up screen is displayed for credentials to be entered.</span></span> <span data-ttu-id="80b0b-123">Stellen Sie sicher, dass Sie Popups für diese Website zulassen.</span><span class="sxs-lookup"><span data-stu-id="80b0b-123">Make sure that you allow pop-ups for this site.</span></span>

## <a name="enabling-siem-integration"></a><span data-ttu-id="80b0b-124">Aktivieren der SIEM-Integration</span><span class="sxs-lookup"><span data-stu-id="80b0b-124">Enabling SIEM integration</span></span> 
1. <span data-ttu-id="80b0b-125">Wählen Sie im Navigationsbereich **Einstellungen**  >  **SIEM** aus.</span><span class="sxs-lookup"><span data-stu-id="80b0b-125">In the navigation pane, select **Settings** > **SIEM**.</span></span>

    ![Abbildung der SIEM-Integration aus Einstellungen Menü1](images/enable_siem.png)

    >[!TIP]
    ><span data-ttu-id="80b0b-127">Wenn beim Versuch, die SIEM-Connectoranwendung zu aktivieren, ein Fehler auftritt, überprüfen Sie die Popupblockereinstellungen Ihres Browsers.</span><span class="sxs-lookup"><span data-stu-id="80b0b-127">If you encounter an error when trying to enable the SIEM connector application, check the pop-up blocker settings of your browser.</span></span> <span data-ttu-id="80b0b-128">Möglicherweise blockiert es, dass das neue Fenster geöffnet wird, wenn Sie die Funktion aktivieren.</span><span class="sxs-lookup"><span data-stu-id="80b0b-128">It might be blocking the new window being opened when you enable the capability.</span></span> 

2. <span data-ttu-id="80b0b-129">Wählen Sie **"SIEM-Integration aktivieren"** aus.</span><span class="sxs-lookup"><span data-stu-id="80b0b-129">Select **Enable SIEM integration**.</span></span> <span data-ttu-id="80b0b-130">Dadurch wird der **Abschnitt "SIEM-Connector-Zugriffsdetails"** mit vordefinierten Werten aktiviert, und eine Anwendung wird unter Ihrem Azure Active Directory (Azure AD)-Mandanten erstellt.</span><span class="sxs-lookup"><span data-stu-id="80b0b-130">This activates the **SIEM connector access details** section with pre-populated values and an application is created under your Azure Active Directory (Azure AD) tenant.</span></span>

    > [!WARNING]
    ><span data-ttu-id="80b0b-131">Der geheime Clientschlüssel wird nur einmal angezeigt.</span><span class="sxs-lookup"><span data-stu-id="80b0b-131">The client secret is only displayed once.</span></span> <span data-ttu-id="80b0b-132">Stellen Sie sicher, dass Sie eine Kopie davon an einem sicheren Ort aufbewahren.</span><span class="sxs-lookup"><span data-stu-id="80b0b-132">Make sure you keep a copy of it in a safe place.</span></span><br>
     

    ![Abbildung der SIEM-Integration aus Einstellungen Menü2](images/siem_details.png)

3. <span data-ttu-id="80b0b-134">Wählen Sie den SIEM-Typ aus, den Sie in Ihrer Organisation verwenden.</span><span class="sxs-lookup"><span data-stu-id="80b0b-134">Choose the SIEM type you use in your organization.</span></span>

   > [!NOTE]
   > <span data-ttu-id="80b0b-135">Wenn Sie HP ArcSight auswählen, müssen Sie diese beiden Konfigurationsdateien speichern:</span><span class="sxs-lookup"><span data-stu-id="80b0b-135">If you select HP ArcSight, you'll need to save these two configuration files:</span></span><br>
   > - <span data-ttu-id="80b0b-136">WDATP-connector.jsonparser.properties</span><span class="sxs-lookup"><span data-stu-id="80b0b-136">WDATP-connector.jsonparser.properties</span></span>
   > - <span data-ttu-id="80b0b-137">WDATP-connector.properties</span><span class="sxs-lookup"><span data-stu-id="80b0b-137">WDATP-connector.properties</span></span> <br>

   <span data-ttu-id="80b0b-138">Wenn Sie über programmgesteuerten Zugriff eine direkte Verbindung mit der REST-API für Erkennungen herstellen möchten, wählen Sie **generische API** aus.</span><span class="sxs-lookup"><span data-stu-id="80b0b-138">If you want to connect directly to the detections REST API through programmatic access, choose **Generic API**.</span></span>

4. <span data-ttu-id="80b0b-139">Kopieren Sie die einzelnen Werte, oder wählen **Sie "Details speichern" aus, um** eine Datei herunterzuladen, die alle Werte enthält.</span><span class="sxs-lookup"><span data-stu-id="80b0b-139">Copy the individual values or select **Save details to file** to download a file that contains all the values.</span></span>

5. <span data-ttu-id="80b0b-140">Wählen Sie **"Token generieren"** aus, um ein Zugriffs- und Aktualisierungstoken abzurufen.</span><span class="sxs-lookup"><span data-stu-id="80b0b-140">Select **Generate tokens** to get an access and refresh token.</span></span>
  
   > [!NOTE]
   > <span data-ttu-id="80b0b-141">Sie müssen alle 90 Tage ein neues Aktualisierungstoken generieren.</span><span class="sxs-lookup"><span data-stu-id="80b0b-141">You'll need to generate a new Refresh token every 90 days.</span></span> 

6. <span data-ttu-id="80b0b-142">Befolgen Sie die Anweisungen zum [Erstellen einer Azure AD-App-Registrierung für Microsoft Defender für Endpunkt,](/microsoft-365/security/defender-endpoint/exposed-apis-create-app-webapp) und weisen Sie ihr die richtigen Berechtigungen zum Lesen von Warnungen zu.</span><span class="sxs-lookup"><span data-stu-id="80b0b-142">Follow the instructions for [creating an Azure AD app registration for Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint/exposed-apis-create-app-webapp) and assign the correct permissions to it to read alerts.</span></span>

<span data-ttu-id="80b0b-143">Sie können jetzt mit der Konfiguration Ihrer SIEM-Lösung fortfahren oder eine Verbindung mit der REST-API für Erkennungen über programmgesteuerten Zugriff herstellen.</span><span class="sxs-lookup"><span data-stu-id="80b0b-143">You can now proceed with configuring your SIEM solution or connecting to the detections REST API through programmatic access.</span></span> <span data-ttu-id="80b0b-144">Sie müssen die Token verwenden, wenn Sie Ihre SIEM-Lösung konfigurieren, damit sie Erkennungen von Microsoft Defender Security Center empfangen kann.</span><span class="sxs-lookup"><span data-stu-id="80b0b-144">You'll need to use the tokens when configuring your SIEM solution to allow it to receive detections from Microsoft Defender Security Center.</span></span>

## <a name="integrate-microsoft-defender-for-endpoint-with-ibm-qradar"></a><span data-ttu-id="80b0b-145">Integrieren von Microsoft Defender für Endpunkt in IBM QRadar</span><span class="sxs-lookup"><span data-stu-id="80b0b-145">Integrate Microsoft Defender for Endpoint with IBM QRadar</span></span> 
<span data-ttu-id="80b0b-146">Sie können IBM QRadar konfigurieren, um Erkennungen von Microsoft Defender für Endpunkt zu sammeln.</span><span class="sxs-lookup"><span data-stu-id="80b0b-146">You can configure IBM QRadar to collect detections from Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="80b0b-147">Weitere Informationen finden Sie im [IBM Knowledge Center.](https://www.ibm.com/support/knowledgecenter/SS42VS_DSM/c_dsm_guide_MS_Win_Defender_ATP_overview.html?cp=SS42VS_7.3.1)</span><span class="sxs-lookup"><span data-stu-id="80b0b-147">For more information, see [IBM Knowledge Center](https://www.ibm.com/support/knowledgecenter/SS42VS_DSM/c_dsm_guide_MS_Win_Defender_ATP_overview.html?cp=SS42VS_7.3.1).</span></span>

## <a name="see-also"></a><span data-ttu-id="80b0b-148">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="80b0b-148">See also</span></span>
- [<span data-ttu-id="80b0b-149">Konfigurieren von HP ArcSight zum Abrufen von Microsoft Defender für Endpunkterkennungen</span><span class="sxs-lookup"><span data-stu-id="80b0b-149">Configure HP ArcSight to pull Microsoft Defender for Endpoint detections</span></span>](configure-arcsight.md)
- [<span data-ttu-id="80b0b-150">Microsoft Defender für Endpunkterkennungsfelder</span><span class="sxs-lookup"><span data-stu-id="80b0b-150">Microsoft Defender for Endpoint Detection fields</span></span>](api-portal-mapping.md)
- [<span data-ttu-id="80b0b-151">Abrufen von Microsoft Defender für Endpunkterkennungen mithilfe der REST-API</span><span class="sxs-lookup"><span data-stu-id="80b0b-151">Pull Microsoft Defender for Endpoint detections using REST API</span></span>](pull-alerts-using-rest-api.md)
- [<span data-ttu-id="80b0b-152">Behandeln von Problemen mit der Integration von SIEM-Tools</span><span class="sxs-lookup"><span data-stu-id="80b0b-152">Troubleshoot SIEM tool integration issues</span></span>](troubleshoot-siem.md)
