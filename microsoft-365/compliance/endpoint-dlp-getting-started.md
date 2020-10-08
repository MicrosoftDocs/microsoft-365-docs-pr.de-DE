---
title: Erste Schritte mit Microsoft 365 Endpunkt-DLP (Vorschau)
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 07/21/2020
audience: ITPro
ms.topic: conceptual
f1_keywords:
- ms.o365.cc.DLPLandingPage
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- m365solution-mip
- m365initiative-compliance
search.appverid:
- MET150
description: Richten Sie Microsoft 365 Endpunkt-DLP (Data Loss Prevention, Verhinderung von Datenverlust) ein, um Dateiaktivitäten zu überwachen und schützende Maßnahmen für diese Dateien auf Endpunkten anzuwenden.
ms.openlocfilehash: e0b9ba6afcad0c683aaa7386998a621f279aa9eb
ms.sourcegitcommit: 5e40c760c1af2a4cc6d85cb782b17f5c979677c5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/07/2020
ms.locfileid: "48379247"
---
# <a name="get-started-with-endpoint-data-loss-prevention-preview"></a><span data-ttu-id="4d4d9-103">Endpunkt-DLP (Vorschau) – Erste Schritte</span><span class="sxs-lookup"><span data-stu-id="4d4d9-103">Get started with Endpoint data loss prevention (preview)</span></span>

<span data-ttu-id="4d4d9-104">Microsoft Endpunkt-DLP (Data Loss Prevention, Verhinderung von Datenverlust) ist Bestandteil der Microsoft 365 DLP-Feature-Suite, mit der Sie vertrauliche Elemente in Microsoft 365-Diensten ermitteln und schützen können.</span><span class="sxs-lookup"><span data-stu-id="4d4d9-104">Microsoft Endpoint data loss prevention (Endpoint DLP) is part of the Microsoft 365 data loss prevention (DLP) suite of features you can use to discover and protect sensitive items across Microsoft 365 services.</span></span> <span data-ttu-id="4d4d9-105">Weitere Informationen zu den Microsoft-DLP-Angeboten finden Sie unter [Verhinderung von Datenverlust – Übersicht](data-loss-prevention-policies.md).</span><span class="sxs-lookup"><span data-stu-id="4d4d9-105">For more information about all of Microsoft’s DLP offerings, see [Overview of data loss prevention](data-loss-prevention-policies.md).</span></span> <span data-ttu-id="4d4d9-106">Weitere Informationen zu Endpunkt-DLP finden Sie unter [Informationen zu Endpunkt-DLP (Vorschau)](endpoint-dlp-learn-about.md)</span><span class="sxs-lookup"><span data-stu-id="4d4d9-106">To learn more about Endpoint DLP, see [Learn about Endpoint data loss prevention (preview)](endpoint-dlp-learn-about.md)</span></span>

<span data-ttu-id="4d4d9-107">Microsoft Endpunkt-DLP ermöglicht es Ihnen, Windows 10-Geräte zu überwachen und zu erkennen, wenn vertrauliche Elemente verwendet und freigegeben werden.</span><span class="sxs-lookup"><span data-stu-id="4d4d9-107">Microsoft Endpoint DLP allows you to monitor Windows 10 devices and detect when sensitive items are used and shared.</span></span> <span data-ttu-id="4d4d9-108">Auf diese Weise erhalten Sie die nötige Übersicht und Kontrolle, um sicherzustellen, dass sie ordnungsgemäß verwendet und geschützt werden, und um ihre Gefährdung durch riskantes Verhalten zu verhindern.</span><span class="sxs-lookup"><span data-stu-id="4d4d9-108">This gives you the visibility and control you need to ensure that they are used and protected properly, and to help prevent risky behavior that might compromise them.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="4d4d9-109">Vorabinformationen</span><span class="sxs-lookup"><span data-stu-id="4d4d9-109">Before you begin</span></span>

### <a name="skusubscriptions-licensing"></a><span data-ttu-id="4d4d9-110">SKU/Abonnement-Lizenzierung</span><span class="sxs-lookup"><span data-stu-id="4d4d9-110">SKU/subscriptions licensing</span></span>

<span data-ttu-id="4d4d9-111">Bevor Sie mit Endpunkt-DLP beginnen, sollten Sie Ihr [Microsoft 365-Abonnement](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1) und etwaige Add-Ons überprüfen.</span><span class="sxs-lookup"><span data-stu-id="4d4d9-111">Before you get started with Endpoint DLP, you should confirm your [Microsoft 365 subscription](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1) and any add-ons.</span></span> <span data-ttu-id="4d4d9-112">Für den Zugriff auf und die Verwendung von Endpunkt-DLP-Funktionen müssen Sie über eines der folgenden Abonnements oder Add-Ons verfügen.</span><span class="sxs-lookup"><span data-stu-id="4d4d9-112">To access and use Endpoint DLP functionality, you must have one of these subscriptions or add-ons.</span></span>

- <span data-ttu-id="4d4d9-113">Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="4d4d9-113">Microsoft 365 E5</span></span>
- <span data-ttu-id="4d4d9-114">Microsoft 365 A5 (EDU)</span><span class="sxs-lookup"><span data-stu-id="4d4d9-114">Microsoft 365 A5 (EDU)</span></span>
- <span data-ttu-id="4d4d9-115">Microsoft 365 E5 Compliance</span><span class="sxs-lookup"><span data-stu-id="4d4d9-115">Microsoft 365 E5 compliance</span></span>
- <span data-ttu-id="4d4d9-116">Microsoft 365 A5 Compliance</span><span class="sxs-lookup"><span data-stu-id="4d4d9-116">Microsoft 365 A5 compliance</span></span>
- <span data-ttu-id="4d4d9-117">Microsoft 365 E5 Information Protection und Governance</span><span class="sxs-lookup"><span data-stu-id="4d4d9-117">Microsoft 365 E5 information protection and governance</span></span>
- <span data-ttu-id="4d4d9-118">Microsoft 365 A5 Information Protection und Governance</span><span class="sxs-lookup"><span data-stu-id="4d4d9-118">Microsoft 365 A5 information protection and governance</span></span>

### <a name="permissions"></a><span data-ttu-id="4d4d9-119">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="4d4d9-119">Permissions</span></span>

<span data-ttu-id="4d4d9-120">Zum Aktivieren der Geräteverwaltung muss das von Ihnen verwendete Konto eine der folgenden Rollen aufweisen:</span><span class="sxs-lookup"><span data-stu-id="4d4d9-120">To enable device management, the account you use must be a member of any one of these roles:</span></span>

- <span data-ttu-id="4d4d9-121">Globaler Administrator</span><span class="sxs-lookup"><span data-stu-id="4d4d9-121">Global admin</span></span>
- <span data-ttu-id="4d4d9-122">Sicherheitsadministrator</span><span class="sxs-lookup"><span data-stu-id="4d4d9-122">Security admin</span></span>
- <span data-ttu-id="4d4d9-123">Compliance-Administrator</span><span class="sxs-lookup"><span data-stu-id="4d4d9-123">Compliance admin</span></span>

<span data-ttu-id="4d4d9-124">Wenn Sie ein benutzerdefiniertes Konto verwenden möchten, um die Einstellungen für die Geräteverwaltung anzuzeigen, muss es eine der folgenden Rollen aufweisen:</span><span class="sxs-lookup"><span data-stu-id="4d4d9-124">If you want to use a custom account to view the device management settings, it must be in one of these roles:</span></span>

- <span data-ttu-id="4d4d9-125">Globaler Administrator</span><span class="sxs-lookup"><span data-stu-id="4d4d9-125">Global admin</span></span>
- <span data-ttu-id="4d4d9-126">Compliance-Administrator</span><span class="sxs-lookup"><span data-stu-id="4d4d9-126">Compliance admin</span></span>
- <span data-ttu-id="4d4d9-127">Compliancedaten-Administrator</span><span class="sxs-lookup"><span data-stu-id="4d4d9-127">Compliance data admin</span></span>
- <span data-ttu-id="4d4d9-128">Globale Leseberechtigung</span><span class="sxs-lookup"><span data-stu-id="4d4d9-128">Global reader</span></span>

<span data-ttu-id="4d4d9-129">Wenn Sie ein benutzerdefiniertes Konto für den Zugriff auf die Seite für das Onboarding/Offboarding verwenden möchten, muss es eine der folgenden Rollen aufweisen:</span><span class="sxs-lookup"><span data-stu-id="4d4d9-129">If you want to use a custom account to access the onboarding/offboarding page, it must be in one of these roles:</span></span>

- <span data-ttu-id="4d4d9-130">Globaler Administrator</span><span class="sxs-lookup"><span data-stu-id="4d4d9-130">Global admin</span></span>
- <span data-ttu-id="4d4d9-131">Compliance-Administrator</span><span class="sxs-lookup"><span data-stu-id="4d4d9-131">Compliance admin</span></span>

<span data-ttu-id="4d4d9-132">Wenn Sie ein benutzerdefiniertes Konto zum Aktivieren/Deaktivieren der Geräteüberwachung verwenden möchten, muss es eine der folgenden Rollen aufweisen:</span><span class="sxs-lookup"><span data-stu-id="4d4d9-132">If you want to use a custom account to turn on/off device monitoring, it must be in one of these roles:</span></span>

- <span data-ttu-id="4d4d9-133">Globaler Administrator</span><span class="sxs-lookup"><span data-stu-id="4d4d9-133">Global admin</span></span>
- <span data-ttu-id="4d4d9-134">Compliance-Administrator</span><span class="sxs-lookup"><span data-stu-id="4d4d9-134">Compliance admin</span></span>

<span data-ttu-id="4d4d9-135">Endpunkt-DLP-Daten können im [Aktivitäten-Explorer](data-classification-activity-explorer.md) angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="4d4d9-135">Data from Endpoint DLP can be viewed in [Activity explorer](data-classification-activity-explorer.md).</span></span> <span data-ttu-id="4d4d9-136">Es gibt vier Rollen, die Berechtigungen für den Aktivitäten-Explorer gewähren; das Konto, das Sie für den Zugriff auf die Daten verwenden, muss eine der folgenden Rollen aufweisen:</span><span class="sxs-lookup"><span data-stu-id="4d4d9-136">There are four roles that grant permission to activity explorer, the account you use for accessing the data must be a member of any one of them.</span></span>

- <span data-ttu-id="4d4d9-137">Globaler Administrator</span><span class="sxs-lookup"><span data-stu-id="4d4d9-137">Global admin</span></span>
- <span data-ttu-id="4d4d9-138">Compliance-Administrator</span><span class="sxs-lookup"><span data-stu-id="4d4d9-138">Compliance admin</span></span>
- <span data-ttu-id="4d4d9-139">Sicherheitsadministrator</span><span class="sxs-lookup"><span data-stu-id="4d4d9-139">Security admin</span></span>
- <span data-ttu-id="4d4d9-140">Compliancedaten-Administrator</span><span class="sxs-lookup"><span data-stu-id="4d4d9-140">Compliance data admin</span></span>

### <a name="prepare-your-endpoints"></a><span data-ttu-id="4d4d9-141">Vorbereiten der Endpunkte</span><span class="sxs-lookup"><span data-stu-id="4d4d9-141">Prepare your endpoints</span></span>

<span data-ttu-id="4d4d9-142">Vergewissern Sie sich, dass die Windows 10-Geräte, auf die Sie Endpunkt-DLP anwenden möchten, die nachstehenden Anforderungen erfüllen.</span><span class="sxs-lookup"><span data-stu-id="4d4d9-142">Make sure that the Windows 10 devices that you plan on deploying Endpoint DLP to meet these requirements.</span></span>

1. <span data-ttu-id="4d4d9-143">Auf den Geräten muss Windows 10 Build 1809 oder höher ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="4d4d9-143">Must be running Windows 10 build 1809 or up.</span></span>
2. <span data-ttu-id="4d4d9-144">Alle Geräte müssen in [Azure Active Directory (AAD)](https://docs.microsoft.com/azure/active-directory/devices/concept-azure-ad-join), oder in Azure AD Hybrid eingebunden sein.</span><span class="sxs-lookup"><span data-stu-id="4d4d9-144">All devices must be [Azure Active Directory (AAD) joined](https://docs.microsoft.com/azure/active-directory/devices/concept-azure-ad-join), or Hybrid Azure AD joined.</span></span>
3. <span data-ttu-id="4d4d9-145">Installieren Sie den Microsoft Edge-Browser auf dem Endpunktgerät, um Richtlinienaktionen für die Aktivität „Hochladen in die Cloud“ durchzusetzen.</span><span class="sxs-lookup"><span data-stu-id="4d4d9-145">Install Microsoft Chromium Edge browser on the endpoint device to enforce policy actions for the upload to cloud activity.</span></span> <span data-ttu-id="4d4d9-146">Weitere Informationen finden Sie unter [Herunterladen des auf Chromium basierenden neuen Microsoft Edge](https://support.microsoft.com/help/4501095/download-the-new-microsoft-edge-based-on-chromium).</span><span class="sxs-lookup"><span data-stu-id="4d4d9-146">See, [Download the new Microsoft Edge based on Chromium](https://support.microsoft.com/help/4501095/download-the-new-microsoft-edge-based-on-chromium).</span></span>

## <a name="onboarding-devices-into-device-management"></a><span data-ttu-id="4d4d9-147">Onboarding von Geräten für die Geräteverwaltung</span><span class="sxs-lookup"><span data-stu-id="4d4d9-147">Onboarding devices into device management</span></span>

 <span data-ttu-id="4d4d9-148">Sie müssen die Geräteüberwachung aktivieren und die Endpunkte einbinden, bevor vertrauliche Elemente auf einem Gerät überwacht und geschützt werden können.</span><span class="sxs-lookup"><span data-stu-id="4d4d9-148">You must enable device monitoring and onboard your endpoints before you can monitor and protect sensitive items on a device.</span></span> <span data-ttu-id="4d4d9-149">Beide Aktionen werden im Microsoft 365 Compliance-Portal durchgeführt.</span><span class="sxs-lookup"><span data-stu-id="4d4d9-149">Both of these actions are done in the Microsoft 365 Compliance portal.</span></span>

<span data-ttu-id="4d4d9-150">Wenn Sie das Onboarding von noch nicht eingebundenen Geräten vornehmen möchten, laden Sie das entsprechende Skript herunter, und installieren Sie es auf diesen Geräten.</span><span class="sxs-lookup"><span data-stu-id="4d4d9-150">When you want to onboard devices that haven't been onboarded yet, you'll download the appropriate script and deploy it to those devices.</span></span> <span data-ttu-id="4d4d9-151">Wenden Sie das [Verfahren zum Onboarding von Geräten](endpoint-dlp-getting-started.md#onboarding-devices) an.</span><span class="sxs-lookup"><span data-stu-id="4d4d9-151">Follow the [Onboarding devices procedure](endpoint-dlp-getting-started.md#onboarding-devices).</span></span>

<span data-ttu-id="4d4d9-152">Wenn bereits Geräte in [Microsoft Defender für Endpunkt](https://docs.microsoft.com/windows/security/threat-protection/) eingebunden sind, werden sie in der Liste der verwalteten Geräte angezeigt.</span><span class="sxs-lookup"><span data-stu-id="4d4d9-152">If you already have devices onboarded into [Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection/), they will already appear in the managed devices list.</span></span> <span data-ttu-id="4d4d9-153">Folgen Sie der Vorgehensweise unter [Bei Geräten, die in Microsoft Defender für Endpunkt eingebunden sind](endpoint-dlp-getting-started.md#with-devices-onboarded-into-microsoft-defender-for- endpoint).</span><span class="sxs-lookup"><span data-stu-id="4d4d9-153">Follow the [With devices onboarded into Microsoft Defender for Endpoint procedure](endpoint-dlp-getting-started.md#with-devices-onboarded-into-microsoft-defender-for- endpoint).</span></span>

### <a name="onboarding-devices"></a><span data-ttu-id="4d4d9-154">Onboarding von Geräten</span><span class="sxs-lookup"><span data-stu-id="4d4d9-154">Onboarding devices</span></span>

<span data-ttu-id="4d4d9-155">In diesem Bereitstellungsszenario werden Sie das Onboarding von noch nicht eingebundenen Geräten vornehmen, und Sie werden dafür sorgen, dass vertrauliche Elemente auf Windows 10-Geräten im Hinblick auf versehentliche Freigabe überwacht und geschützt sind.</span><span class="sxs-lookup"><span data-stu-id="4d4d9-155">In this deployment scenario, you'll onboard devices that have not been onboarded yet, and you just want to monitor and protect sensitive items from unintentional sharing on Windows 10 devices.</span></span>

1. <span data-ttu-id="4d4d9-156">Öffnen Sie das [Microsoft Compliance Center](https://compliance.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="4d4d9-156">Open the [Microsoft compliance center](https://compliance.microsoft.com).</span></span>
2. <span data-ttu-id="4d4d9-157">Öffnen Sie die Seite "Einstellungen", und wählen Sie **Geräte-Onboarding** aus.</span><span class="sxs-lookup"><span data-stu-id="4d4d9-157">Open the Compliance Center settings page and choose **Onboard devices**.</span></span> 

   ![Aktivieren der Geräteverwaltung](../media/endpoint-dlp-learn-about-1-enable-device-management.png)

   > [!NOTE]
   > <span data-ttu-id="4d4d9-159">In der Regel dauert es zwar nur ungefähr eine Minute, bis das Geräte-Onboarding aktiviert ist, warten Sie aber mindestens 30 Minuten, bevor Sie sich an den Microsoft-Support wenden.</span><span class="sxs-lookup"><span data-stu-id="4d4d9-159">While it usually takes about 60 seconds for device onboarding to be enabled, please allow up to 30 minutes before engaging with Microsoft support.</span></span>

3. <span data-ttu-id="4d4d9-160">Wählen Sie **Geräteverwaltung** aus, um die Liste der **Geräte** zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="4d4d9-160">Choose **Device management** to open the **Devices** list.</span></span> <span data-ttu-id="4d4d9-161">Die Liste ist leer, solange keine Geräte eingebunden sind.</span><span class="sxs-lookup"><span data-stu-id="4d4d9-161">The list will be empty until you onboard devices.</span></span>
4. <span data-ttu-id="4d4d9-162">Wählen Sie **Onboarding** aus, um mit dem Onboarding-Prozess zu beginnen.</span><span class="sxs-lookup"><span data-stu-id="4d4d9-162">Choose **Onboarding** to begin the onboarding process.</span></span>
5. <span data-ttu-id="4d4d9-163">Wählen Sie die Art der Bereitstellung auf diesen zusätzlichen Geräten aus der Liste der **Bereitstellungsmethoden** und anschließend **Paket herunterladen** aus.</span><span class="sxs-lookup"><span data-stu-id="4d4d9-163">Choose the way you want to deploy to these additional devices from the **Deployment method** list and then **download package**.</span></span>

   ![Bereitstellungsmethode](../media/endpoint-dlp-getting-started-3-deployment-method.png)
6. <span data-ttu-id="4d4d9-165">Führen Sie die unter [Onboarding-Tools und -Methoden für Windows 10-Computer](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints) beschriebenen entsprechenden Verfahren aus.</span><span class="sxs-lookup"><span data-stu-id="4d4d9-165">Follow the appropriate procedures in [Onboarding tools and methods for Windows 10 machines](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints).</span></span> <span data-ttu-id="4d4d9-166">Über diesen Link gelangen Sie zu einer Zielseite, auf der Microsoft Defender für Endpunkt-Prozeduren beschrieben werden, die dem in Schritt 5 ausgewählten Bereitstellungspaket entsprechen:</span><span class="sxs-lookup"><span data-stu-id="4d4d9-166">This link take you to a landing page where you can access Microsoft Defender for Endpoint procedures that match the deployment package you selected in step 5:</span></span>
    - <span data-ttu-id="4d4d9-167">Onboarding von Windows 10-Computern mithilfe von Gruppenrichtlinien</span><span class="sxs-lookup"><span data-stu-id="4d4d9-167">Onboard Windows 10 machines using Group Policy</span></span>
    - <span data-ttu-id="4d4d9-168">Onboarding von Windows-Computern mithilfe von Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="4d4d9-168">Onboard Windows machines using Microsoft Endpoint Configuration Manager</span></span>
    - <span data-ttu-id="4d4d9-169">Onboarding von Windows 10-Computern mit Tools für die Verwaltung von Mobilgeräten</span><span class="sxs-lookup"><span data-stu-id="4d4d9-169">Onboard Windows 10 machines using Mobile Device Management tools</span></span>
    - <span data-ttu-id="4d4d9-170">Onboarding von Windows 10-Computern mithilfe eines lokalen Skripts</span><span class="sxs-lookup"><span data-stu-id="4d4d9-170">Onboard Windows 10 machines using a local script</span></span>
    - <span data-ttu-id="4d4d9-171">Onboarding von nicht-persistenten Computern einer VD-Infrastruktur (Virtual Desktop)</span><span class="sxs-lookup"><span data-stu-id="4d4d9-171">Onboard non-persistent virtual desktop infrastructure (VDI) machines.</span></span>

<span data-ttu-id="4d4d9-172">Nach Abschluss des Endpunkt-Onboardings sollten diese in der Liste der Geräte aufgeführt sein, und das Übertragen von Aktivitätsüberwachungsprotokollen an den Aktivitäten-Explorer sollte beginnen.</span><span class="sxs-lookup"><span data-stu-id="4d4d9-172">Once done and endpoint is onboarded, it should be visible in the devices list and also start reporting audit activity logs to Activity explorer.</span></span>

> [!NOTE]
> <span data-ttu-id="4d4d9-173">Diese Funktion erfordert eine Lizenz.</span><span class="sxs-lookup"><span data-stu-id="4d4d9-173">This experience is under license enforcement.</span></span> <span data-ttu-id="4d4d9-174">Ohne die erforderliche Lizenz werden keine Daten angezeigt und es ist kein Zugriff auf sie möglich.</span><span class="sxs-lookup"><span data-stu-id="4d4d9-174">Without the required license, data will not be visible or accessible.</span></span>

### <a name="with-devices-onboarded-into-microsoft-defender-for-endpoint"></a><span data-ttu-id="4d4d9-175">Bei Geräten, die in Microsoft Defender für Endpunkt eingebunden sind</span><span class="sxs-lookup"><span data-stu-id="4d4d9-175">With devices onboarded into Microsoft Defender for Endpoint</span></span>

<span data-ttu-id="4d4d9-176">In diesem Szenario ist Microsoft Defender für Endpunkt bereits installiert, und Endpunkte senden Protokolle.</span><span class="sxs-lookup"><span data-stu-id="4d4d9-176">In this scenario, Microsoft Defender for Endpoint is already deployed and there are endpoints reporting in.</span></span> <span data-ttu-id="4d4d9-177">Alle diese Endpunkte werden in der Liste der verwalteten Geräte angezeigt.</span><span class="sxs-lookup"><span data-stu-id="4d4d9-177">All these endpoints will appear in the managed devices list.</span></span> <span data-ttu-id="4d4d9-178">Über das [Geräte-Onboarding](endpoint-dlp-getting-started.md#onboarding-devices) können Sie weiterhin neue Geräte in Endpunkt-DLP einbinden, um die Abdeckung zu erweitern.</span><span class="sxs-lookup"><span data-stu-id="4d4d9-178">You can continue to onboard new devices into Endpoint DLP to expand coverage by using the [Onboarding devices procedure](endpoint-dlp-getting-started.md#onboarding-devices).</span></span>

1. <span data-ttu-id="4d4d9-179">Öffnen Sie das [Microsoft Compliance Center](https://compliance.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="4d4d9-179">Open the [Microsoft compliance center](https://compliance.microsoft.com).</span></span>
2. <span data-ttu-id="4d4d9-180">Öffnen Sie die Seite "Einstellungen", und wählen Sie **Geräteüberwachung aktivieren** aus.</span><span class="sxs-lookup"><span data-stu-id="4d4d9-180">Open the Compliance Center settings page and choose **Enable device monitoring**.</span></span>
3. <span data-ttu-id="4d4d9-181">Wählen Sie **Geräteverwaltung** aus, um die Liste der **Geräte** zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="4d4d9-181">Choose **Device management** to open the **Devices** list.</span></span> <span data-ttu-id="4d4d9-182">Es sollte die Liste der Geräte angezeigt werden, die bereits Berichte für Microsoft Defender für Endpunkt erstellen.</span><span class="sxs-lookup"><span data-stu-id="4d4d9-182">You should see the list of devices that are already reporting in to Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="4d4d9-183">![Geräteverwaltung](../media/endpoint-dlp-getting-started-2-device-management.png)</span><span class="sxs-lookup"><span data-stu-id="4d4d9-183">![device management](../media/endpoint-dlp-getting-started-2-device-management.png)</span></span>
4. <span data-ttu-id="4d4d9-184">Wenn Sie zusätzliche Geräte einbinden möchten, wählen Sie **Onboarding** aus.</span><span class="sxs-lookup"><span data-stu-id="4d4d9-184">Choose **Onboarding** if you need to onboard additional devices.</span></span>
5. <span data-ttu-id="4d4d9-185">Wählen Sie die Art der Bereitstellung auf diesen zusätzlichen Geräten aus der Liste der **Bereitstellungsmethoden** und anschließend **Paket herunterladen** aus.</span><span class="sxs-lookup"><span data-stu-id="4d4d9-185">Choose the way you want to deploy to these additional devices from the **Deployment method** list and then **Download package**.</span></span>
6. <span data-ttu-id="4d4d9-186">Führen Sie die unter [Onboarding-Tools und -Methoden für Windows 10-Computer](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints) beschriebenen entsprechenden Verfahren aus.</span><span class="sxs-lookup"><span data-stu-id="4d4d9-186">Follow the appropriate procedures in [Onboarding tools and methods for Windows 10 machines](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints).</span></span> <span data-ttu-id="4d4d9-187">Über diesen Link gelangen Sie zu einer Zielseite, auf der Microsoft Defender für Endpunkt-Prozeduren beschrieben werden, die dem in Schritt 5 ausgewählten Bereitstellungspaket entsprechen:</span><span class="sxs-lookup"><span data-stu-id="4d4d9-187">This link take you to a landing page where you can access Microsoft Defender for Endpoint procedures that match the deployment package you selected in step 5:</span></span>
    - <span data-ttu-id="4d4d9-188">Onboarding von Windows 10-Computern mithilfe von Gruppenrichtlinien</span><span class="sxs-lookup"><span data-stu-id="4d4d9-188">Onboard Windows 10 machines using Group Policy</span></span>
    - <span data-ttu-id="4d4d9-189">Onboarding von Windows-Computern mithilfe von Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="4d4d9-189">Onboard Windows machines using Microsoft Endpoint Configuration Manager</span></span>
    - <span data-ttu-id="4d4d9-190">Onboarding von Windows 10-Computern mit Tools für die Verwaltung von Mobilgeräten</span><span class="sxs-lookup"><span data-stu-id="4d4d9-190">Onboard Windows 10 machines using Mobile Device Management tools</span></span>
    - <span data-ttu-id="4d4d9-191">Onboarding von Windows 10-Computern mithilfe eines lokalen Skripts</span><span class="sxs-lookup"><span data-stu-id="4d4d9-191">Onboard Windows 10 machines using a local script</span></span>
    - <span data-ttu-id="4d4d9-192">Onboarding von nicht-persistenten Computern einer VD-Infrastruktur (Virtual Desktop)</span><span class="sxs-lookup"><span data-stu-id="4d4d9-192">Onboard non-persistent virtual desktop infrastructure (VDI) machines.</span></span>

<span data-ttu-id="4d4d9-193">Nach Abschluss des Endpunkt-Onboardings sollten diese in der Tabelle der **Geräte** aufgeführt sein, und das Übertragen von Überwachungsprotokollen an den **Aktivitäten-Explorer** sollte beginnen.</span><span class="sxs-lookup"><span data-stu-id="4d4d9-193">Once done and endpoint is onboarded, it should be visible under the **Devices** table and also start reporting audit logs to the **Activity Explorer**.</span></span>

> [!NOTE]
><span data-ttu-id="4d4d9-194">Diese Funktion erfordert eine Lizenz.</span><span class="sxs-lookup"><span data-stu-id="4d4d9-194">This experience is under license enforcement.</span></span> <span data-ttu-id="4d4d9-195">Ohne die erforderliche Lizenz werden keine Daten angezeigt und es ist kein Zugriff auf sie möglich.</span><span class="sxs-lookup"><span data-stu-id="4d4d9-195">Without the required license, data will not be visible or accessible.</span></span>

### <a name="viewing-endpoint-dlp-data-in-activity-explorer"></a><span data-ttu-id="4d4d9-196">Anzeigen von Endpunkt-DLP-Daten im Aktivitäten-Explorer</span><span class="sxs-lookup"><span data-stu-id="4d4d9-196">Viewing Endpoint DLP data in activity explorer</span></span>

1. <span data-ttu-id="4d4d9-197">Öffnen Sie im Microsoft 365 Compliance Center die Seite [Datenklassifizierung](https://compliance.microsoft.com/dataclassification?viewid=overview) für Ihre Domäne, und wählen Sie den Aktivitäten-Explorer aus.</span><span class="sxs-lookup"><span data-stu-id="4d4d9-197">Open the [Data classification page](https://compliance.microsoft.com/dataclassification?viewid=overview) for your domain in the Microsoft 365 Compliance center and choose Activity explorer.</span></span>
2. <span data-ttu-id="4d4d9-198">Unter [Erste Schritte mit dem Aktivitäten-Explorer](data-classification-activity-explorer.md) erfahren Sie Näheres dazu, wie Sie auf alle Daten zu Ihren Endpunktgeräten zugreifen und diese filtern können.</span><span class="sxs-lookup"><span data-stu-id="4d4d9-198">Refer to the procedures in [Get started with Activity explorer](data-classification-activity-explorer.md) to access and filter all the data for your Endpoint devices.</span></span>

![Aktivitäten-Explorer-Filter für Endpunktgeräte](../media/endpoint-dlp-4-getting-started-activity-explorer.png)

## <a name="next-steps"></a><span data-ttu-id="4d4d9-200">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="4d4d9-200">Next steps</span></span>
<span data-ttu-id="4d4d9-201">Jetzt, da Geräte eingebunden sind und entsprechende Aktivitätsdaten im Aktivitäten-Explorer angezeigt werden, können Sie mit dem nächsten Schritt fortfahren, bei dem Sie DLP-Richtlinien zum Schutz Ihrer vertraulichen Elemente erstellen werden.</span><span class="sxs-lookup"><span data-stu-id="4d4d9-201">Now that you have onboarded devices and can view the activity data in Activity explorer, you are ready to move on to your next step where you create DLP policies that protect your sensitive items.</span></span>

- [<span data-ttu-id="4d4d9-202">Nutzung von Endpunkt-DLP (Vorschau)</span><span class="sxs-lookup"><span data-stu-id="4d4d9-202">Using Endpoint data loss prevention (preview)</span></span>](endpoint-dlp-using.md)

## <a name="see-also"></a><span data-ttu-id="4d4d9-203">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4d4d9-203">See also</span></span>

- [<span data-ttu-id="4d4d9-204">Informationen zu Endpunkt-DLP (Vorschau)</span><span class="sxs-lookup"><span data-stu-id="4d4d9-204">Learn about Endpoint data loss prevention (preview)</span></span>](endpoint-dlp-learn-about.md)
- [<span data-ttu-id="4d4d9-205">Nutzung von Endpunkt-DLP (Vorschau)</span><span class="sxs-lookup"><span data-stu-id="4d4d9-205">Using Endpoint data loss prevention (preview)</span></span>](endpoint-dlp-using.md)
- [<span data-ttu-id="4d4d9-206">Verhinderung von Datenverlust – Übersicht</span><span class="sxs-lookup"><span data-stu-id="4d4d9-206">Overview of data loss prevention</span></span>](data-loss-prevention-policies.md)
- [<span data-ttu-id="4d4d9-207">Erstellen, Testen und Optimieren einer DLP-Richtlinie</span><span class="sxs-lookup"><span data-stu-id="4d4d9-207">Create, test, and tune a DLP policy</span></span>](create-test-tune-dlp-policy.md)
- [<span data-ttu-id="4d4d9-208">Erste Schritte mit dem Aktivitäten-Explorer</span><span class="sxs-lookup"><span data-stu-id="4d4d9-208">Get started with Activity explorer</span></span>](data-classification-activity-explorer.md)
- [<span data-ttu-id="4d4d9-209">Microsoft Defender Advanced Threat Protection (Microsoft Defender ATP)</span><span class="sxs-lookup"><span data-stu-id="4d4d9-209">Microsoft Defender Advanced Threat Protection (Microsoft Defender ATP)</span></span>](https://docs.microsoft.com/windows/security/threat-protection/)
- [<span data-ttu-id="4d4d9-210">Onboarding-Tools und -Methoden für Windows 10-Computer</span><span class="sxs-lookup"><span data-stu-id="4d4d9-210">Onboarding tools and methods for Windows 10 machines</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints)
- [<span data-ttu-id="4d4d9-211">Microsoft 365-Abonnement</span><span class="sxs-lookup"><span data-stu-id="4d4d9-211">Microsoft 365 subscription</span></span>](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1)
- [<span data-ttu-id="4d4d9-212">Azure Active Directory (AAD) Einbindung</span><span class="sxs-lookup"><span data-stu-id="4d4d9-212">Azure Active Directory (AAD) joined</span></span>](https://docs.microsoft.com/azure/active-directory/devices/concept-azure-ad-join)
- [<span data-ttu-id="4d4d9-213">Herunterladen des auf Chromium basierenden neuen Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="4d4d9-213">Download the new Microsoft Edge based on Chromium</span></span>](https://support.microsoft.com/help/4501095/download-the-new-microsoft-edge-based-on-chromium)
