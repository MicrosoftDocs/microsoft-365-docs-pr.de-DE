---
title: Behandeln von Problemen mit der Integration von SIEM-Tools in Microsoft Defender ATP
description: Behandeln von Problemen, die bei der Verwendung von SIEM-Tools mit Microsoft Defender ATP auftreten können.
keywords: Problembehandlung, Siem, geheimer Client, Geheimer Schlüssel
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
ms.topic: troubleshooting
ms.technology: mde
ms.openlocfilehash: 7a6bb0c455ed0406c941e9269b8b04b5cfe738be
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51064839"
---
# <a name="troubleshoot-siem-tool-integration-issues"></a><span data-ttu-id="03f1b-104">Problembehandlung bei der Integration von SIEM-Tools</span><span class="sxs-lookup"><span data-stu-id="03f1b-104">Troubleshoot SIEM tool integration issues</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="03f1b-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="03f1b-105">**Applies to:**</span></span>
- [<span data-ttu-id="03f1b-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="03f1b-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [<span data-ttu-id="03f1b-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="03f1b-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


> <span data-ttu-id="03f1b-108">Möchten Sie Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="03f1b-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="03f1b-109">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="03f1b-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-pullalerts-abovefoldlink) 

<span data-ttu-id="03f1b-110">Möglicherweise müssen Sie Beim Ziehen von Erkennungen in Ihren SIEM-Tools Probleme beheben.</span><span class="sxs-lookup"><span data-stu-id="03f1b-110">You might need to troubleshoot issues while pulling detections in your SIEM tools.</span></span>

<span data-ttu-id="03f1b-111">Auf dieser Seite finden Sie detaillierte Schritte zur Problembehandlung.</span><span class="sxs-lookup"><span data-stu-id="03f1b-111">This page provides detailed steps to troubleshoot issues you might encounter.</span></span>


## <a name="learn-how-to-get-a-new-client-secret"></a><span data-ttu-id="03f1b-112">Erfahren Sie, wie Sie einen neuen Geheimen Clientgeheimnis erhalten</span><span class="sxs-lookup"><span data-stu-id="03f1b-112">Learn how to get a new client secret</span></span>
<span data-ttu-id="03f1b-113">Wenn Ihr Geheimer Clientgeheimnis abläuft oder Sie die beim Aktivieren der SIEM-Toolanwendung bereitgestellte Kopie falsch platziert haben, müssen Sie einen neuen Schlüssel erhalten.</span><span class="sxs-lookup"><span data-stu-id="03f1b-113">If your client secret expires or if you've misplaced the copy provided when you were enabling the SIEM tool application,  you'll need to get a new secret.</span></span>

1. <span data-ttu-id="03f1b-114">Melden Sie sich beim [Azure-Verwaltungsportal an.](https://portal.azure.com)</span><span class="sxs-lookup"><span data-stu-id="03f1b-114">Login to the [Azure management portal](https://portal.azure.com).</span></span>

2. <span data-ttu-id="03f1b-115">Wählen Sie **Azure Active Directory** aus.</span><span class="sxs-lookup"><span data-stu-id="03f1b-115">Select **Azure Active Directory**.</span></span>

3. <span data-ttu-id="03f1b-116">Wählen Sie Ihren Mandanten aus.</span><span class="sxs-lookup"><span data-stu-id="03f1b-116">Select your tenant.</span></span>

4. <span data-ttu-id="03f1b-117">Klicken Sie **auf App-Registrierungen**.</span><span class="sxs-lookup"><span data-stu-id="03f1b-117">Click **App registrations**.</span></span> <span data-ttu-id="03f1b-118">Wählen Sie dann in der Liste Anwendungen die Anwendung aus.</span><span class="sxs-lookup"><span data-stu-id="03f1b-118">Then in the applications list, select the application.</span></span>

5. <span data-ttu-id="03f1b-119">Wählen **Sie Den** Abschnitt Schlüssel aus, geben Sie eine Schlüsselbeschreibung an, und geben Sie die Gültigkeitsdauer des Schlüssels an.</span><span class="sxs-lookup"><span data-stu-id="03f1b-119">Select **Keys** section, then provide a key description and specify the key validity duration.</span></span>

6. <span data-ttu-id="03f1b-120">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="03f1b-120">Click **Save**.</span></span> <span data-ttu-id="03f1b-121">Der Schlüsselwert wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="03f1b-121">The key value is displayed.</span></span>

7. <span data-ttu-id="03f1b-122">Kopieren Sie den Wert, und speichern Sie ihn an einem sicheren Ort.</span><span class="sxs-lookup"><span data-stu-id="03f1b-122">Copy the value and save it in a safe place.</span></span>


## <a name="error-when-getting-a-refresh-access-token"></a><span data-ttu-id="03f1b-123">Fehler beim Abrufen eines Aktualisierungszugriffstokens</span><span class="sxs-lookup"><span data-stu-id="03f1b-123">Error when getting a refresh access token</span></span>
<span data-ttu-id="03f1b-124">Wenn beim Versuch, ein Aktualisierungstoken zu erhalten, beim Verwenden der Threat Intelligence-API oder der SIEM-Tools ein Fehler auftritt, müssen Sie die Antwort-URL für die relevante Anwendung in Azure Active Directory hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="03f1b-124">If you encounter an error when trying to get a refresh token when using the threat intelligence API or SIEM tools, you'll need to add reply URL for relevant application in Azure Active Directory.</span></span>

1. <span data-ttu-id="03f1b-125">Melden Sie sich beim [Azure-Verwaltungsportal an.](https://ms.portal.azure.com)</span><span class="sxs-lookup"><span data-stu-id="03f1b-125">Login to the [Azure management portal](https://ms.portal.azure.com).</span></span>

2. <span data-ttu-id="03f1b-126">Wählen Sie **Azure Active Directory** aus.</span><span class="sxs-lookup"><span data-stu-id="03f1b-126">Select **Azure Active Directory**.</span></span>

3. <span data-ttu-id="03f1b-127">Wählen Sie Ihren Mandanten aus.</span><span class="sxs-lookup"><span data-stu-id="03f1b-127">Select your tenant.</span></span>

4. <span data-ttu-id="03f1b-128">Klicken Sie **auf App-Registrierungen**.</span><span class="sxs-lookup"><span data-stu-id="03f1b-128">Click **App Registrations**.</span></span> <span data-ttu-id="03f1b-129">Wählen Sie dann in der Liste Anwendungen die Anwendung aus.</span><span class="sxs-lookup"><span data-stu-id="03f1b-129">Then in the applications list, select the application.</span></span>

5. <span data-ttu-id="03f1b-130">Fügen Sie die folgende URL hinzu:</span><span class="sxs-lookup"><span data-stu-id="03f1b-130">Add the following URL:</span></span>
   - <span data-ttu-id="03f1b-131">Für die Europäische Union: `https://winatpmanagement-eu.securitycenter.windows.com/UserAuthenticationCallback`</span><span class="sxs-lookup"><span data-stu-id="03f1b-131">For the European Union: `https://winatpmanagement-eu.securitycenter.windows.com/UserAuthenticationCallback`</span></span>
   - <span data-ttu-id="03f1b-132">Für Großbritannien: `https://winatpmanagement-uk.securitycenter.windows.com/UserAuthenticationCallback`</span><span class="sxs-lookup"><span data-stu-id="03f1b-132">For the United Kingdom: `https://winatpmanagement-uk.securitycenter.windows.com/UserAuthenticationCallback`</span></span>
   - <span data-ttu-id="03f1b-133">Für die Vereinigten Staaten:  `https://winatpmanagement-us.securitycenter.windows.com/UserAuthenticationCallback` .</span><span class="sxs-lookup"><span data-stu-id="03f1b-133">For the United States:  `https://winatpmanagement-us.securitycenter.windows.com/UserAuthenticationCallback`.</span></span>
 
6. <span data-ttu-id="03f1b-134">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="03f1b-134">Click **Save**.</span></span>

## <a name="error-while-enabling-the-siem-connector-application"></a><span data-ttu-id="03f1b-135">Fehler beim Aktivieren der SIEM-Connectoranwendung</span><span class="sxs-lookup"><span data-stu-id="03f1b-135">Error while enabling the SIEM connector application</span></span>
<span data-ttu-id="03f1b-136">Wenn beim Versuch, die SIEM-Connectoranwendung zu aktivieren, ein Fehler auftritt, überprüfen Sie die Popupblockereinstellungen Ihres Browsers.</span><span class="sxs-lookup"><span data-stu-id="03f1b-136">If you encounter an error when trying to enable the SIEM connector application, check the pop-up blocker settings of your browser.</span></span> <span data-ttu-id="03f1b-137">Möglicherweise wird das neue Fenster blockiert, das geöffnet wird, wenn Sie die Funktion aktivieren.</span><span class="sxs-lookup"><span data-stu-id="03f1b-137">It might be blocking the new window being opened when you enable the capability.</span></span>




><span data-ttu-id="03f1b-138">Möchten Sie Microsoft Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="03f1b-138">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="03f1b-139">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="03f1b-139">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-troubleshootsiem-belowfoldlink) 

## <a name="related-topics"></a><span data-ttu-id="03f1b-140">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="03f1b-140">Related topics</span></span>
- [<span data-ttu-id="03f1b-141">Aktivieren der SIEM-Integration in Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="03f1b-141">Enable SIEM integration in Microsoft Defender for Endpoint</span></span>](enable-siem-integration.md)
- [<span data-ttu-id="03f1b-142">Konfigurieren von ArcSight zum Ziehen von Microsoft Defender for Endpoint-Erkennungen</span><span class="sxs-lookup"><span data-stu-id="03f1b-142">Configure ArcSight to pull Microsoft Defender for Endpoint detections</span></span>](configure-arcsight.md)
- [<span data-ttu-id="03f1b-143">Ziehen von Erkennungen an Ihre SIEM-Tools</span><span class="sxs-lookup"><span data-stu-id="03f1b-143">Pull detections to your SIEM tools</span></span>](configure-siem.md)
- [<span data-ttu-id="03f1b-144">Microsoft Defender for Endpoint Detection-Felder</span><span class="sxs-lookup"><span data-stu-id="03f1b-144">Microsoft Defender for Endpoint Detection fields</span></span>](api-portal-mapping.md)
- [<span data-ttu-id="03f1b-145">Abrufen von Microsoft Defender for Endpoint-Erkennungen mithilfe der REST-API</span><span class="sxs-lookup"><span data-stu-id="03f1b-145">Pull Microsoft Defender for Endpoint detections using REST API</span></span>](pull-alerts-using-rest-api.md)
