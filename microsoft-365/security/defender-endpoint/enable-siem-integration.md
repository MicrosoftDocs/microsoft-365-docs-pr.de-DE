---
title: Aktivieren der SIEM-Integration in Microsoft Defender for Endpoint
description: Aktivieren Sie die SIEM-Integration, um Erkennungen in Ihrer Sicherheitsinformations- und Ereignisverwaltungslösung (SIEM) zu empfangen.
keywords: Siemconnector, Siem, Connector, Sicherheitsinformationen und Ereignisse aktivieren
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
ms.openlocfilehash: 337eb28b7e4b4a7c57b63ff45fb1cea81db43604
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51068207"
---
# <a name="enable-siem-integration-in-microsoft-defender-for-endpoint"></a><span data-ttu-id="961d7-104">Aktivieren der SIEM-Integration in Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="961d7-104">Enable SIEM integration in Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="961d7-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="961d7-105">**Applies to:**</span></span>
- [<span data-ttu-id="961d7-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="961d7-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)


><span data-ttu-id="961d7-107">Möchten Sie Microsoft Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="961d7-107">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="961d7-108">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="961d7-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-enablesiem-abovefoldlink) 

<span data-ttu-id="961d7-109">Aktivieren Sie die Integration von Sicherheitsinformationen und Ereignisverwaltung (SIEM), damit Sie Erkennungen aus dem Microsoft Defender Security Center ziehen können.</span><span class="sxs-lookup"><span data-stu-id="961d7-109">Enable security information and event management (SIEM) integration so you can pull detections from Microsoft Defender Security Center.</span></span> <span data-ttu-id="961d7-110">Abrufen von Erkennungen mithilfe Ihrer SIEM-Lösung oder durch direkte Verbindung mit der ERKENNUNGS-REST-API.</span><span class="sxs-lookup"><span data-stu-id="961d7-110">Pull detections using your SIEM solution or by connecting directly to the detections REST API.</span></span>

>[!NOTE]
>- <span data-ttu-id="961d7-111">[Microsoft Defender for Endpoint Alert](alerts.md) besteht aus einer oder mehreren Erkennungen.</span><span class="sxs-lookup"><span data-stu-id="961d7-111">[Microsoft Defender for Endpoint Alert](alerts.md) is composed from one or more detections.</span></span>
>- <span data-ttu-id="961d7-112">[Microsoft Defender for Endpoint Detection](api-portal-mapping.md) besteht aus dem verdächtigen Ereignis, das auf dem Gerät aufgetreten ist, und den zugehörigen Warnungsdetails.</span><span class="sxs-lookup"><span data-stu-id="961d7-112">[Microsoft Defender for Endpoint Detection](api-portal-mapping.md) is composed from the suspicious event occurred on the Device and its related Alert details.</span></span>
>- <span data-ttu-id="961d7-113">Die Microsoft Defender for Endpoint Alert-API ist die neueste API für den Warnungsverbrauch und enthält eine detaillierte Liste der zugehörigen Nachweise für jede Warnung.</span><span class="sxs-lookup"><span data-stu-id="961d7-113">The Microsoft Defender for Endpoint Alert API is the latest API for alert consumption and contain a detailed list of related evidence for each alert.</span></span> <span data-ttu-id="961d7-114">Weitere Informationen finden Sie unter [Warnungsmethoden und -eigenschaften und](alerts.md) [Warnungen auflisten.](get-alerts.md)</span><span class="sxs-lookup"><span data-stu-id="961d7-114">For more information, see [Alert methods and properties](alerts.md) and [List alerts](get-alerts.md).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="961d7-115">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="961d7-115">Prerequisites</span></span>

- <span data-ttu-id="961d7-116">Der Benutzer, der die Einstellung aktiviert, muss über Berechtigungen zum Erstellen einer App in Azure Active Directory (AAD) verfügen.</span><span class="sxs-lookup"><span data-stu-id="961d7-116">The user who activates the setting must have permissions to create an app in Azure Active Directory (AAD).</span></span> <span data-ttu-id="961d7-117">Dies ist eine Person mit den folgenden Rollen:</span><span class="sxs-lookup"><span data-stu-id="961d7-117">This is someone with the following roles:</span></span> 

  - <span data-ttu-id="961d7-118">Sicherheitsadministrator und entweder globaler Administrator</span><span class="sxs-lookup"><span data-stu-id="961d7-118">Security Administrator and either Global Administrator</span></span>
  - <span data-ttu-id="961d7-119">Cloudanwendungsadministrator</span><span class="sxs-lookup"><span data-stu-id="961d7-119">Cloud Application Administrator</span></span>
  - <span data-ttu-id="961d7-120">Anwendungsadministrator</span><span class="sxs-lookup"><span data-stu-id="961d7-120">Application Administrator</span></span>
  - <span data-ttu-id="961d7-121">Besitzer des Dienstprinzipal</span><span class="sxs-lookup"><span data-stu-id="961d7-121">Owner of the service principal</span></span>

- <span data-ttu-id="961d7-122">Während der ersten Aktivierung wird ein Popupbildschirm angezeigt, auf dem Anmeldeinformationen eingegeben werden können.</span><span class="sxs-lookup"><span data-stu-id="961d7-122">During the initial activation, a pop-up screen is displayed for credentials to be entered.</span></span> <span data-ttu-id="961d7-123">Stellen Sie sicher, dass Sie Popups für diese Website zulassen.</span><span class="sxs-lookup"><span data-stu-id="961d7-123">Make sure that you allow pop-ups for this site.</span></span>

## <a name="enabling-siem-integration"></a><span data-ttu-id="961d7-124">Aktivieren der SIEM-Integration</span><span class="sxs-lookup"><span data-stu-id="961d7-124">Enabling SIEM integration</span></span> 
1. <span data-ttu-id="961d7-125">Wählen Sie im Navigationsbereich **Einstellungen**  >  **SIEM aus.**</span><span class="sxs-lookup"><span data-stu-id="961d7-125">In the navigation pane, select **Settings** > **SIEM**.</span></span>

    ![Abbildung der SIEM-Integration aus dem Menü Einstellungen1](images/enable_siem.png)

    >[!TIP]
    ><span data-ttu-id="961d7-127">Wenn beim Versuch, die SIEM-Connectoranwendung zu aktivieren, ein Fehler auftritt, überprüfen Sie die Popupblockereinstellungen Ihres Browsers.</span><span class="sxs-lookup"><span data-stu-id="961d7-127">If you encounter an error when trying to enable the SIEM connector application, check the pop-up blocker settings of your browser.</span></span> <span data-ttu-id="961d7-128">Möglicherweise wird das neue Fenster blockiert, das geöffnet wird, wenn Sie die Funktion aktivieren.</span><span class="sxs-lookup"><span data-stu-id="961d7-128">It might be blocking the new window being opened when you enable the capability.</span></span> 

2. <span data-ttu-id="961d7-129">Wählen **Sie SIEM-Integration aktivieren aus.**</span><span class="sxs-lookup"><span data-stu-id="961d7-129">Select **Enable SIEM integration**.</span></span> <span data-ttu-id="961d7-130">Dadurch wird der **Abschnitt MITM-Connectorzugriffsdetails** mit vordefinierten Werten aktiviert, und eine Anwendung wird unter Ihrem Azure Active Directory (Azure AD)-Mandanten erstellt.</span><span class="sxs-lookup"><span data-stu-id="961d7-130">This activates the **SIEM connector access details** section with pre-populated values and an application is created under your Azure Active Directory (Azure AD) tenant.</span></span>

    > [!WARNING]
    ><span data-ttu-id="961d7-131">Der geheime Clientgeheimnis wird nur einmal angezeigt.</span><span class="sxs-lookup"><span data-stu-id="961d7-131">The client secret is only displayed once.</span></span> <span data-ttu-id="961d7-132">Stellen Sie sicher, dass Sie eine Kopie davon an einem sicheren Ort behalten.</span><span class="sxs-lookup"><span data-stu-id="961d7-132">Make sure you keep a copy of it in a safe place.</span></span><br>
     

    ![Abbildung der SIEM-Integration aus dem Menü Einstellungen2](images/siem_details.png)

3. <span data-ttu-id="961d7-134">Wählen Sie den SIEM-Typ aus, den Sie in Ihrer Organisation verwenden.</span><span class="sxs-lookup"><span data-stu-id="961d7-134">Choose the SIEM type you use in your organization.</span></span>

   > [!NOTE]
   > <span data-ttu-id="961d7-135">Wenn Sie HP ArcSight auswählen, müssen Sie diese beiden Konfigurationsdateien speichern:</span><span class="sxs-lookup"><span data-stu-id="961d7-135">If you select HP ArcSight, you'll need to save these two configuration files:</span></span><br>
   > - <span data-ttu-id="961d7-136">WDATP-connector.jsonparser.properties</span><span class="sxs-lookup"><span data-stu-id="961d7-136">WDATP-connector.jsonparser.properties</span></span>
   > - <span data-ttu-id="961d7-137">WDATP-connector.properties</span><span class="sxs-lookup"><span data-stu-id="961d7-137">WDATP-connector.properties</span></span> <br>

   <span data-ttu-id="961d7-138">Wenn Sie über programmgesteuerten Zugriff eine direkte Verbindung mit der ERKENNUNGS-REST-API herstellen möchten, wählen Sie **Generische API aus.**</span><span class="sxs-lookup"><span data-stu-id="961d7-138">If you want to connect directly to the detections REST API through programmatic access, choose **Generic API**.</span></span>

4. <span data-ttu-id="961d7-139">Kopieren Sie die einzelnen Werte, oder wählen Sie **Details in Datei speichern aus,** um eine Datei herunterzuladen, die alle Werte enthält.</span><span class="sxs-lookup"><span data-stu-id="961d7-139">Copy the individual values or select **Save details to file** to download a file that contains all the values.</span></span>

5. <span data-ttu-id="961d7-140">Wählen **Sie Token generieren aus,** um ein Zugriffs- und Aktualisierungstoken abzurufen.</span><span class="sxs-lookup"><span data-stu-id="961d7-140">Select **Generate tokens** to get an access and refresh token.</span></span>
  
   > [!NOTE]
   > <span data-ttu-id="961d7-141">Sie müssen alle 90 Tage ein neues Aktualisierungstoken generieren.</span><span class="sxs-lookup"><span data-stu-id="961d7-141">You'll need to generate a new Refresh token every 90 days.</span></span> 

6. <span data-ttu-id="961d7-142">Befolgen Sie die Anweisungen [zum Erstellen einer Azure AD-App-Registrierung für Microsoft Defender for Endpoint,](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/exposed-apis-create-app-webapp) und weisen Sie ihr die richtigen Berechtigungen zum Lesen von Warnungen zu.</span><span class="sxs-lookup"><span data-stu-id="961d7-142">Follow the instructions for [creating an Azure AD app registration for Microsoft Defender for Endpoint](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/exposed-apis-create-app-webapp) and assign the correct permissions to it to read alerts.</span></span>

<span data-ttu-id="961d7-143">Sie können nun mit der Konfiguration Ihrer SIEM-Lösung fortfahren oder über programmgesteuerten Zugriff eine Verbindung mit der REST-API für Erkennungen herstellen.</span><span class="sxs-lookup"><span data-stu-id="961d7-143">You can now proceed with configuring your SIEM solution or connecting to the detections REST API through programmatic access.</span></span> <span data-ttu-id="961d7-144">Sie müssen die Token verwenden, wenn Sie Ihre SIEM-Lösung so konfigurieren, dass sie Erkennungen vom Microsoft Defender Security Center empfangen kann.</span><span class="sxs-lookup"><span data-stu-id="961d7-144">You'll need to use the tokens when configuring your SIEM solution to allow it to receive detections from Microsoft Defender Security Center.</span></span>

## <a name="integrate-microsoft-defender-for-endpoint-with-ibm-qradar"></a><span data-ttu-id="961d7-145">Integrieren von Microsoft Defender for Endpoint in IBM QRadar</span><span class="sxs-lookup"><span data-stu-id="961d7-145">Integrate Microsoft Defender for Endpoint with IBM QRadar</span></span> 
<span data-ttu-id="961d7-146">Sie können IBM QRadar so konfigurieren, dass Erkennungen von Microsoft Defender for Endpoint erfasst werden.</span><span class="sxs-lookup"><span data-stu-id="961d7-146">You can configure IBM QRadar to collect detections from Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="961d7-147">Weitere Informationen finden Sie unter [IBM Knowledge Center](https://www.ibm.com/support/knowledgecenter/SS42VS_DSM/c_dsm_guide_MS_Win_Defender_ATP_overview.html?cp=SS42VS_7.3.1).</span><span class="sxs-lookup"><span data-stu-id="961d7-147">For more information, see [IBM Knowledge Center](https://www.ibm.com/support/knowledgecenter/SS42VS_DSM/c_dsm_guide_MS_Win_Defender_ATP_overview.html?cp=SS42VS_7.3.1).</span></span>

## <a name="see-also"></a><span data-ttu-id="961d7-148">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="961d7-148">See also</span></span>
- [<span data-ttu-id="961d7-149">Konfigurieren von HP ArcSight zum Ziehen von Microsoft Defender for Endpoint-Erkennungen</span><span class="sxs-lookup"><span data-stu-id="961d7-149">Configure HP ArcSight to pull Microsoft Defender for Endpoint detections</span></span>](configure-arcsight.md)
- [<span data-ttu-id="961d7-150">Microsoft Defender for Endpoint Detection-Felder</span><span class="sxs-lookup"><span data-stu-id="961d7-150">Microsoft Defender for Endpoint Detection fields</span></span>](api-portal-mapping.md)
- [<span data-ttu-id="961d7-151">Abrufen von Microsoft Defender for Endpoint-Erkennungen mithilfe der REST-API</span><span class="sxs-lookup"><span data-stu-id="961d7-151">Pull Microsoft Defender for Endpoint detections using REST API</span></span>](pull-alerts-using-rest-api.md)
- [<span data-ttu-id="961d7-152">Problembehandlung bei der Integration von SIEM-Tools</span><span class="sxs-lookup"><span data-stu-id="961d7-152">Troubleshoot SIEM tool integration issues</span></span>](troubleshoot-siem.md)
