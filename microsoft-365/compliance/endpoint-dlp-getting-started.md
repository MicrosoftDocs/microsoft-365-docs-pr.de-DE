---
title: Erste Schritte mit Microsoft 365 Endpunkt-DLP
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
ms.openlocfilehash: 6ba3b83d634f946f818890a732a83166f346162d
ms.sourcegitcommit: fcc1b40732f28f075d95faffc1655473e262dd95
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/14/2020
ms.locfileid: "49073094"
---
# <a name="get-started-with-endpoint-data-loss-prevention"></a><span data-ttu-id="743d0-103">Erste Schritte mit Endpunkt-DLP</span><span class="sxs-lookup"><span data-stu-id="743d0-103">Get started with Endpoint data loss prevention</span></span>

<span data-ttu-id="743d0-p101">Microsoft Endpunkt-DLP (Data Loss Prevention, Verhinderung von Datenverlust) ist Bestandteil der Microsoft 365 DLP-Suite, mit der Sie vertrauliche Elemente in Microsoft 365-Diensten ermitteln und schützen können. Weitere Informationen zu den Microsoft-DLP-Angeboten finden Sie unter [Verhinderung von Datenverlust – Übersicht](data-loss-prevention-policies.md). Einzelheiten über Endpunkt-DLP finden Sie unter [ Informationen zu Endpunkt-DLP](endpoint-dlp-learn-about.md).</span><span class="sxs-lookup"><span data-stu-id="743d0-p101">Microsoft Endpoint data loss prevention (Endpoint DLP) is part of the Microsoft 365 data loss prevention (DLP) suite of features you can use to discover and protect sensitive items across Microsoft 365 services. For more information about all of Microsoft’s DLP offerings, see [Overview of data loss prevention](data-loss-prevention-policies.md). To learn more about Endpoint DLP, see [Learn about Endpoint data loss prevention](endpoint-dlp-learn-about.md)</span></span>

<span data-ttu-id="743d0-p102">Microsoft Endpunkt-DLP ermöglicht es Ihnen, Windows 10-Geräte zu überwachen und zu erkennen, wenn vertrauliche Elemente verwendet und freigegeben werden. Auf diese Weise erhalten Sie die nötige Übersicht und Kontrolle, um sicherzustellen, dass sie ordnungsgemäß verwendet und geschützt werden, und um ihre Gefährdung durch riskantes Verhalten zu verhindern.</span><span class="sxs-lookup"><span data-stu-id="743d0-p102">Microsoft Endpoint DLP allows you to monitor Windows 10 devices and detect when sensitive items are used and shared. This gives you the visibility and control you need to ensure that they are used and protected properly, and to help prevent risky behavior that might compromise them.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="743d0-109">Vorbereitung</span><span class="sxs-lookup"><span data-stu-id="743d0-109">Before you begin</span></span>

### <a name="skusubscriptions-licensing"></a><span data-ttu-id="743d0-110">SKU/Abonnement-Lizenzierung</span><span class="sxs-lookup"><span data-stu-id="743d0-110">SKU/subscriptions licensing</span></span>

<span data-ttu-id="743d0-p103">Bevor Sie mit Endpunkt-DLP beginnen, sollten Sie Ihr [Microsoft 365-Abonnement](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1) und etwaige Add-Ons überprüfen. Für den Zugriff auf und die Verwendung von Endpunkt-DLP-Funktionen müssen Sie über eines der folgenden Abonnements oder Add-Ons verfügen.</span><span class="sxs-lookup"><span data-stu-id="743d0-p103">Before you get started with Endpoint DLP, you should confirm your [Microsoft 365 subscription](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1) and any add-ons. To access and use Endpoint DLP functionality, you must have one of these subscriptions or add-ons.</span></span>

- <span data-ttu-id="743d0-113">Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="743d0-113">Microsoft 365 E5</span></span>
- <span data-ttu-id="743d0-114">Microsoft 365 A5 (EDU)</span><span class="sxs-lookup"><span data-stu-id="743d0-114">Microsoft 365 A5 (EDU)</span></span>
- <span data-ttu-id="743d0-115">Microsoft 365 E5 Compliance</span><span class="sxs-lookup"><span data-stu-id="743d0-115">Microsoft 365 E5 compliance</span></span>
- <span data-ttu-id="743d0-116">Microsoft 365 A5 Compliance</span><span class="sxs-lookup"><span data-stu-id="743d0-116">Microsoft 365 A5 compliance</span></span>
- <span data-ttu-id="743d0-117">Microsoft 365 E5 Information Protection und Governance</span><span class="sxs-lookup"><span data-stu-id="743d0-117">Microsoft 365 E5 information protection and governance</span></span>
- <span data-ttu-id="743d0-118">Microsoft 365 A5 Information Protection und Governance</span><span class="sxs-lookup"><span data-stu-id="743d0-118">Microsoft 365 A5 information protection and governance</span></span>


### <a name="permissions"></a><span data-ttu-id="743d0-119">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="743d0-119">Permissions</span></span>

<span data-ttu-id="743d0-120">Zum Aktivieren der Geräteverwaltung muss das von Ihnen verwendete Konto eine der folgenden Rollen aufweisen:</span><span class="sxs-lookup"><span data-stu-id="743d0-120">To enable device management, the account you use must be a member of any one of these roles:</span></span>

- <span data-ttu-id="743d0-121">Globaler Administrator</span><span class="sxs-lookup"><span data-stu-id="743d0-121">Global admin</span></span>
- <span data-ttu-id="743d0-122">Sicherheitsadministrator</span><span class="sxs-lookup"><span data-stu-id="743d0-122">Security admin</span></span>
- <span data-ttu-id="743d0-123">Compliance-Administrator</span><span class="sxs-lookup"><span data-stu-id="743d0-123">Compliance admin</span></span>

<span data-ttu-id="743d0-124">Wenn Sie ein benutzerdefiniertes Konto verwenden möchten, um die Einstellungen für die Geräteverwaltung anzuzeigen, muss es eine der folgenden Rollen aufweisen:</span><span class="sxs-lookup"><span data-stu-id="743d0-124">If you want to use a custom account to view the device management settings, it must be in one of these roles:</span></span>

- <span data-ttu-id="743d0-125">Globaler Administrator</span><span class="sxs-lookup"><span data-stu-id="743d0-125">Global admin</span></span>
- <span data-ttu-id="743d0-126">Compliance-Administrator</span><span class="sxs-lookup"><span data-stu-id="743d0-126">Compliance admin</span></span>
- <span data-ttu-id="743d0-127">Compliancedaten-Administrator</span><span class="sxs-lookup"><span data-stu-id="743d0-127">Compliance data admin</span></span>
- <span data-ttu-id="743d0-128">Globale Leseberechtigung</span><span class="sxs-lookup"><span data-stu-id="743d0-128">Global reader</span></span>

<span data-ttu-id="743d0-129">Wenn Sie ein benutzerdefiniertes Konto für den Zugriff auf die Seite für das Onboarding/Offboarding verwenden möchten, muss es eine der folgenden Rollen aufweisen:</span><span class="sxs-lookup"><span data-stu-id="743d0-129">If you want to use a custom account to access the onboarding/offboarding page, it must be in one of these roles:</span></span>

- <span data-ttu-id="743d0-130">Globaler Administrator</span><span class="sxs-lookup"><span data-stu-id="743d0-130">Global admin</span></span>
- <span data-ttu-id="743d0-131">Compliance-Administrator</span><span class="sxs-lookup"><span data-stu-id="743d0-131">Compliance admin</span></span>

<span data-ttu-id="743d0-132">Wenn Sie ein benutzerdefiniertes Konto zum Aktivieren/Deaktivieren der Geräteüberwachung verwenden möchten, muss es eine der folgenden Rollen aufweisen:</span><span class="sxs-lookup"><span data-stu-id="743d0-132">If you want to use a custom account to turn on/off device monitoring, it must be in one of these roles:</span></span>

- <span data-ttu-id="743d0-133">Globaler Administrator</span><span class="sxs-lookup"><span data-stu-id="743d0-133">Global admin</span></span>
- <span data-ttu-id="743d0-134">Compliance-Administrator</span><span class="sxs-lookup"><span data-stu-id="743d0-134">Compliance admin</span></span>

<span data-ttu-id="743d0-p104">Endpunkt-DLP-Daten können im [Aktivitäten-Explorer](data-classification-activity-explorer.md) angezeigt werden. Es gibt vier Rollen, die Berechtigungen für den Aktivitäten-Explorer gewähren; das Konto, das Sie für den Zugriff auf die Daten verwenden, muss eine dieser Rollen aufweisen.</span><span class="sxs-lookup"><span data-stu-id="743d0-p104">Data from Endpoint DLP can be viewed in [Activity explorer](data-classification-activity-explorer.md). There are four roles that grant permission to activity explorer, the account you use for accessing the data must be a member of any one of them.</span></span>

- <span data-ttu-id="743d0-137">Globaler Administrator</span><span class="sxs-lookup"><span data-stu-id="743d0-137">Global admin</span></span>
- <span data-ttu-id="743d0-138">Compliance-Administrator</span><span class="sxs-lookup"><span data-stu-id="743d0-138">Compliance admin</span></span>
- <span data-ttu-id="743d0-139">Sicherheitsadministrator</span><span class="sxs-lookup"><span data-stu-id="743d0-139">Security admin</span></span>
- <span data-ttu-id="743d0-140">Compliancedaten-Administrator</span><span class="sxs-lookup"><span data-stu-id="743d0-140">Compliance data admin</span></span>

### <a name="prepare-your-endpoints"></a><span data-ttu-id="743d0-141">Vorbereiten der Endpunkte</span><span class="sxs-lookup"><span data-stu-id="743d0-141">Prepare your endpoints</span></span>

<span data-ttu-id="743d0-142">Vergewissern Sie sich, dass die Windows 10-Geräte, auf die Sie Endpunkt-DLP anwenden möchten, die nachstehenden Anforderungen erfüllen.</span><span class="sxs-lookup"><span data-stu-id="743d0-142">Make sure that the Windows 10 devices that you plan on deploying Endpoint DLP to meet these requirements.</span></span>

1. <span data-ttu-id="743d0-143">Es muss Windows 10 x64 Build 1809 oder höher ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="743d0-143">Must be running Windows 10 x64 build 1809 or later.</span></span>

2. <span data-ttu-id="743d0-p105">Antimalware Client, Version 4.18.2009.7 oder höher. Überprüfen Sie die aktuelle Version, indem Sie die Windows-Sicherheits-App öffnen, das Einstellungen-Symbol und dann "Info" auswählen. Führen Sie eine Aktualisierung auf die neueste Antimalware-Clientversion durch, indem Sie Windows Update KB4052623 installieren. Hinweis: Keine der Windows-Sicherheitskomponenten muss aktiv sein, Sie können Endpunkt-DLP unabhängig vom Windows-Sicherheitsstatus ausführen.</span><span class="sxs-lookup"><span data-stu-id="743d0-p105">Antimalware Client Version is 4.18.2009.7 or newer. Check your current version by opening Windows Security app, select the Settings icon, and then select About. The version number is listed under Antimalware Client Version. Update to the latest Antimalware Client Version by installing Windows Update KB4052623. Note: None of Windows Security components need to be active, you can run Endpoint DLP independent of Windows Security status.</span></span>

3. <span data-ttu-id="743d0-p106">Die nachstehenden Windows-Updates sind installiert. Hinweis: Diese Updates sind keine Voraussetzung für die Einbindung eines Geräts in Endpunkt-DLP, enthalten jedoch Fixes für wichtige Probleme und müssen daher vor der Verwendung des Produkts installiert werden.</span><span class="sxs-lookup"><span data-stu-id="743d0-p106">The following Windows Updates are installed. Note: These updates are not a pre-requisite to onboard a device to Endpoint DLP, but contain fixes for important issues thus must be installed before using the product.</span></span>

    - <span data-ttu-id="743d0-151">Für Windows 10 1809 – KB4559003, KB4577069, KB4580390</span><span class="sxs-lookup"><span data-stu-id="743d0-151">For Windows 10 1809 - KB4559003, KB4577069, KB4580390</span></span>
    - <span data-ttu-id="743d0-152">Für Windows 10 1903 oder 1909 – KB4559004, KB4577062, KB4580386</span><span class="sxs-lookup"><span data-stu-id="743d0-152">For Windows 10 1903 or 1909 - KB4559004, KB4577062, KB4580386</span></span>
    - <span data-ttu-id="743d0-153">Für Windows 10 2004 – KB4568831, KB4577063</span><span class="sxs-lookup"><span data-stu-id="743d0-153">For Windows 10 2004 - KB4568831, KB4577063</span></span>
    - <span data-ttu-id="743d0-154">Für Geräte mit Office 2016 (und keine andere Office-Version) – KB4577063</span><span class="sxs-lookup"><span data-stu-id="743d0-154">For devices running Office 2016 (and not any other Office version) - KB4577063</span></span> 

4. <span data-ttu-id="743d0-155">Alle Geräte müssen in [Azure Active Directory (Azure AD)](https://docs.microsoft.com/azure/active-directory/devices/concept-azure-ad-join) oder Azure AD Hybrid eingebunden sein.</span><span class="sxs-lookup"><span data-stu-id="743d0-155">All devices must be [Azure Active Directory (Azure AD) joined](https://docs.microsoft.com/azure/active-directory/devices/concept-azure-ad-join), or Hybrid Azure AD joined.</span></span>

5. <span data-ttu-id="743d0-p107">Installieren Sie den Microsoft Chromium Edge-Browser auf dem Endpunktgerät, um Richtlinienaktionen für das Hochladen in die Cloud durchzusetzen. Weitere Informationen finden Sie unter [Herunterladen des auf Chromium basierenden neuen Microsoft Edge](https://support.microsoft.com/help/4501095/download-the-new-microsoft-edge-based-on-chromium).</span><span class="sxs-lookup"><span data-stu-id="743d0-p107">Install Microsoft Chromium Edge browser on the endpoint device to enforce policy actions for the upload to cloud activity. See, [Download the new Microsoft Edge based on Chromium](https://support.microsoft.com/help/4501095/download-the-new-microsoft-edge-based-on-chromium).</span></span>

6. <span data-ttu-id="743d0-p108">Im monatlichen Enterprise-Kanal der Microsoft 365 Apps Versionen 2004–2008 gibt es ein bekanntes Problem mit Endpunkt-DLP im Hinblick auf die Klassifizierung von Office-Inhalten. Führen Sie eine Aktualisierung auf Version 2009 oder höher durch. Mehr zu den aktuellen Versionen erfahren Sie unter [Updateverlauf für Microsoft 365 Apps (nach Datum)](https://docs.microsoft.com/officeupdates/update-history-microsoft365-apps-by-date). Weitere Informationen zu diesem Problem finden Sie unter [Anmerkungen zu aktuellen Kanalversionen von 2020](https://docs.microsoft.com/officeupdates/current-channel#version-2010-october-27).</span><span class="sxs-lookup"><span data-stu-id="743d0-p108">If you are on Monthly Enterprise Channel of Microsoft 365 Apps versions 2004-2008, there is a known issue with Endpoint DLP classifying Office content and you need to update to version 2009 or later. See [Update history for Microsoft 365 Apps (listed by date)](https://docs.microsoft.com/officeupdates/update-history-microsoft365-apps-by-date) for current versions. To learn more about this issue, see the Office Suite section of [Release notes for Current Channel releases in 2020](https://docs.microsoft.com/officeupdates/current-channel#version-2010-october-27).</span></span>

## <a name="onboarding-devices-into-device-management"></a><span data-ttu-id="743d0-161">Onboarding von Geräten für die Geräteverwaltung</span><span class="sxs-lookup"><span data-stu-id="743d0-161">Onboarding devices into device management</span></span>

<span data-ttu-id="743d0-p109">Sie müssen die Geräteüberwachung aktivieren und die Endpunkte einbinden, bevor vertrauliche Elemente auf einem Gerät überwacht und geschützt werden können. Beide Aktionen werden im Microsoft 365 Compliance-Portal durchgeführt.</span><span class="sxs-lookup"><span data-stu-id="743d0-p109">You must enable device monitoring and onboard your endpoints before you can monitor and protect sensitive items on a device. Both of these actions are done in the Microsoft 365 Compliance portal.</span></span>

<span data-ttu-id="743d0-p110">Wenn Sie das Onboarding von noch nicht eingebundenen Geräten vornehmen möchten, laden Sie das entsprechende Skript herunter, und installieren Sie es auf diesen Geräten. Wenden Sie das [Verfahren zum Onboarding von Geräten](endpoint-dlp-getting-started.md#onboarding-devices) an.</span><span class="sxs-lookup"><span data-stu-id="743d0-p110">When you want to onboard devices that haven't been onboarded yet, you'll download the appropriate script and deploy it to those devices. Follow the [Onboarding devices procedure](endpoint-dlp-getting-started.md#onboarding-devices).</span></span>

<span data-ttu-id="743d0-p111">Wenn bereits Geräte in [Microsoft Defender für Endpunkt](https://docs.microsoft.com/windows/security/threat-protection/) eingebunden sind, werden sie in der Liste der verwalteten Geräte angezeigt. Wenden Sie das [Verfahren für Geräte, die in Microsoft Defender für Endpunkt eingebunden sind](endpoint-dlp-getting-started.md#with-devices-onboarded-into-microsoft-defender-for- endpoint), an.</span><span class="sxs-lookup"><span data-stu-id="743d0-p111">If you already have devices onboarded into [Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection/), they will already appear in the managed devices list. Follow the [With devices onboarded into Microsoft Defender for Endpoint procedure](endpoint-dlp-getting-started.md#with-devices-onboarded-into-microsoft-defender-for- endpoint).</span></span>

### <a name="onboarding-devices"></a><span data-ttu-id="743d0-168">Onboarding von Geräten</span><span class="sxs-lookup"><span data-stu-id="743d0-168">Onboarding devices</span></span>

<span data-ttu-id="743d0-169">In diesem Bereitstellungsszenario werden Sie das Onboarding von noch nicht eingebundenen Geräten vornehmen, und Sie werden dafür sorgen, dass vertrauliche Elemente auf Windows 10-Geräten im Hinblick auf versehentliche Freigabe überwacht und geschützt sind.</span><span class="sxs-lookup"><span data-stu-id="743d0-169">In this deployment scenario, you'll onboard devices that have not been onboarded yet, and you just want to monitor and protect sensitive items from unintentional sharing on Windows 10 devices.</span></span>

1. <span data-ttu-id="743d0-170">Öffnen Sie das [Microsoft Compliance Center](https://compliance.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="743d0-170">Open the [Microsoft compliance center](https://compliance.microsoft.com).</span></span>

2. <span data-ttu-id="743d0-171">Öffnen Sie die Seite "Einstellungen", und wählen Sie **Geräte-Onboarding** aus.</span><span class="sxs-lookup"><span data-stu-id="743d0-171">Open the Compliance Center settings page and choose **Onboard devices**.</span></span> 

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="743d0-172">![Aktivieren der Geräteverwaltung](../media/endpoint-dlp-learn-about-1-enable-device-management.png)</span><span class="sxs-lookup"><span data-stu-id="743d0-172">![enable device management](../media/endpoint-dlp-learn-about-1-enable-device-management.png)</span></span>

   > [!NOTE]
   > <span data-ttu-id="743d0-173">In der Regel dauert es zwar nur ungefähr eine Minute, bis das Geräte-Onboarding aktiviert ist, warten Sie aber mindestens 30 Minuten, bevor Sie sich an den Microsoft-Support wenden.</span><span class="sxs-lookup"><span data-stu-id="743d0-173">While it usually takes about 60 seconds for device onboarding to be enabled, please allow up to 30 minutes before engaging with Microsoft support.</span></span>

3. <span data-ttu-id="743d0-p112">Wählen Sie **Geräteverwaltung** aus, um die Liste der **Geräte** zu öffnen. Die Liste ist leer, solange keine Geräte eingebunden sind.</span><span class="sxs-lookup"><span data-stu-id="743d0-p112">Choose **Device management** to open the **Devices** list. The list will be empty until you onboard devices.</span></span>

4. <span data-ttu-id="743d0-176">Wählen Sie **Onboarding** aus, um mit dem Onboarding-Prozess zu beginnen.</span><span class="sxs-lookup"><span data-stu-id="743d0-176">Choose **Onboarding** to begin the onboarding process.</span></span>

5. <span data-ttu-id="743d0-177">Wählen Sie die Art der Bereitstellung auf diesen zusätzlichen Geräten aus der Liste der **Bereitstellungsmethoden** und anschließend **Paket herunterladen** aus.</span><span class="sxs-lookup"><span data-stu-id="743d0-177">Choose the way you want to deploy to these additional devices from the **Deployment method** list and then **download package**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="743d0-178">![Bereitstellungsmethode](../media/endpoint-dlp-getting-started-3-deployment-method.png)</span><span class="sxs-lookup"><span data-stu-id="743d0-178">![deployment method](../media/endpoint-dlp-getting-started-3-deployment-method.png)</span></span>
   
6. <span data-ttu-id="743d0-p113">Wenden Sie die unter [Onboarding-Tools und -Methoden für Windows 10-Computer](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints) beschriebenen entsprechenden Verfahren an. Über diesen Link gelangen Sie zu einer Zielseite, auf der Microsoft Defender für Endpunkt-Verfahren beschrieben werden, die dem in Schritt 5 ausgewählten Bereitstellungspaket entsprechen:</span><span class="sxs-lookup"><span data-stu-id="743d0-p113">Follow the appropriate procedures in [Onboarding tools and methods for Windows 10 machines](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints). This link take you to a landing page where you can access Microsoft Defender for Endpoint procedures that match the deployment package you selected in step 5:</span></span>

    - <span data-ttu-id="743d0-181">Onboarding von Windows 10-Computern mithilfe von Gruppenrichtlinien</span><span class="sxs-lookup"><span data-stu-id="743d0-181">Onboard Windows 10 machines using Group Policy</span></span>
    - <span data-ttu-id="743d0-182">Onboarding von Windows-Computern mithilfe von Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="743d0-182">Onboard Windows machines using Microsoft Endpoint Configuration Manager</span></span>
    - <span data-ttu-id="743d0-183">Onboarding von Windows 10-Computern mit Tools für die Verwaltung von Mobilgeräten</span><span class="sxs-lookup"><span data-stu-id="743d0-183">Onboard Windows 10 machines using Mobile Device Management tools</span></span>
    - <span data-ttu-id="743d0-184">Onboarding von Windows 10-Computern mithilfe eines lokalen Skripts</span><span class="sxs-lookup"><span data-stu-id="743d0-184">Onboard Windows 10 machines using a local script</span></span>
    - <span data-ttu-id="743d0-185">Onboarding von nicht-persistenten Computern einer VD-Infrastruktur (Virtual Desktop)</span><span class="sxs-lookup"><span data-stu-id="743d0-185">Onboard non-persistent virtual desktop infrastructure (VDI) machines.</span></span>

<span data-ttu-id="743d0-186">Nach Abschluss des Endpunkt-Onboardings sollten diese in der Liste der Geräte aufgeführt sein, und das Übertragen von Aktivitätsüberwachungsprotokollen an den Aktivitäten-Explorer sollte beginnen.</span><span class="sxs-lookup"><span data-stu-id="743d0-186">Once done and endpoint is onboarded, it should be visible in the devices list and also start reporting audit activity logs to Activity explorer.</span></span>

> [!NOTE]
> <span data-ttu-id="743d0-p114">Diese Funktion erfordert eine Lizenz. Ohne die erforderliche Lizenz werden keine Daten angezeigt und es ist kein Zugriff auf sie möglich.</span><span class="sxs-lookup"><span data-stu-id="743d0-p114">This experience is under license enforcement. Without the required license, data will not be visible or accessible.</span></span>

### <a name="with-devices-onboarded-into-microsoft-defender-for-endpoint"></a><span data-ttu-id="743d0-189">Bei Geräten, die in Microsoft Defender für Endpunkt eingebunden sind</span><span class="sxs-lookup"><span data-stu-id="743d0-189">With devices onboarded into Microsoft Defender for Endpoint</span></span>

<span data-ttu-id="743d0-p115">In diesem Szenario ist Microsoft Defender für Endpunkt bereits installiert, und Endpunkte senden Protokolle. Alle diese Endpunkte werden in der Liste der verwalteten Geräte angezeigt. Über das [Geräte-Onboarding](endpoint-dlp-getting-started.md#onboarding-devices) können Sie weiterhin neue Geräte in Endpunkt-DLP einbinden, um die Abdeckung zu erweitern.</span><span class="sxs-lookup"><span data-stu-id="743d0-p115">In this scenario, Microsoft Defender for Endpoint is already deployed and there are endpoints reporting in. All these endpoints will appear in the managed devices list. You can continue to onboard new devices into Endpoint DLP to expand coverage by using the [Onboarding devices procedure](endpoint-dlp-getting-started.md#onboarding-devices).</span></span>

1. <span data-ttu-id="743d0-193">Öffnen Sie das [Microsoft Compliance Center](https://compliance.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="743d0-193">Open the [Microsoft compliance center](https://compliance.microsoft.com).</span></span>

2. <span data-ttu-id="743d0-194">Öffnen Sie die Seite "Einstellungen", und wählen Sie **Geräteüberwachung aktivieren** aus.</span><span class="sxs-lookup"><span data-stu-id="743d0-194">Open the Compliance Center settings page and choose **Enable device monitoring**.</span></span>

3. <span data-ttu-id="743d0-p116">Wählen Sie **Geräteverwaltung** aus, um die Liste der **Geräte** zu öffnen. Es sollte die Liste der Geräte angezeigt werden, die bereits Berichte für Microsoft Defender für Endpunkt erstellen.</span><span class="sxs-lookup"><span data-stu-id="743d0-p116">Choose **Device management** to open the **Devices** list. You should see the list of devices that are already reporting in to Microsoft Defender for Endpoint.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="743d0-197">![Geräteverwaltung](../media/endpoint-dlp-getting-started-2-device-management.png)</span><span class="sxs-lookup"><span data-stu-id="743d0-197">![device management](../media/endpoint-dlp-getting-started-2-device-management.png)</span></span>
   
4. <span data-ttu-id="743d0-198">Wenn Sie zusätzliche Geräte einbinden möchten, wählen Sie **Onboarding** aus.</span><span class="sxs-lookup"><span data-stu-id="743d0-198">Choose **Onboarding** if you need to onboard additional devices.</span></span>

5. <span data-ttu-id="743d0-199">Wählen Sie die Art der Bereitstellung auf diesen zusätzlichen Geräten aus der Liste der **Bereitstellungsmethoden** und anschließend **Paket herunterladen** aus.</span><span class="sxs-lookup"><span data-stu-id="743d0-199">Choose the way you want to deploy to these additional devices from the **Deployment method** list and then **Download package**.</span></span>

6. <span data-ttu-id="743d0-p117">Wenden Sie die unter [Onboarding-Tools und -Methoden für Windows 10-Computer](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints) beschriebenen entsprechenden Verfahren an. Über diesen Link gelangen Sie zu einer Zielseite, auf der Microsoft Defender für Endpunkt-Verfahren beschrieben werden, die dem in Schritt 5 ausgewählten Bereitstellungspaket entsprechen:</span><span class="sxs-lookup"><span data-stu-id="743d0-p117">Follow the appropriate procedures in [Onboarding tools and methods for Windows 10 machines](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints). This link take you to a landing page where you can access Microsoft Defender for Endpoint procedures that match the deployment package you selected in step 5:</span></span>

    - <span data-ttu-id="743d0-202">Onboarding von Windows 10-Computern mithilfe von Gruppenrichtlinien</span><span class="sxs-lookup"><span data-stu-id="743d0-202">Onboard Windows 10 machines using Group Policy</span></span>
    - <span data-ttu-id="743d0-203">Onboarding von Windows-Computern mithilfe von Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="743d0-203">Onboard Windows machines using Microsoft Endpoint Configuration Manager</span></span>
    - <span data-ttu-id="743d0-204">Onboarding von Windows 10-Computern mit Tools für die Verwaltung von Mobilgeräten</span><span class="sxs-lookup"><span data-stu-id="743d0-204">Onboard Windows 10 machines using Mobile Device Management tools</span></span>
    - <span data-ttu-id="743d0-205">Onboarding von Windows 10-Computern mithilfe eines lokalen Skripts</span><span class="sxs-lookup"><span data-stu-id="743d0-205">Onboard Windows 10 machines using a local script</span></span>
    - <span data-ttu-id="743d0-206">Onboarding von nicht-persistenten Computern einer VD-Infrastruktur (Virtual Desktop)</span><span class="sxs-lookup"><span data-stu-id="743d0-206">Onboard non-persistent virtual desktop infrastructure (VDI) machines.</span></span>

<span data-ttu-id="743d0-207">Nach Abschluss des Endpunkt-Onboardings sollten diese in der Tabelle der **Geräte** aufgeführt sein, und das Übertragen von Überwachungsprotokollen an den **Aktivitäten-Explorer** sollte beginnen.</span><span class="sxs-lookup"><span data-stu-id="743d0-207">Once done and endpoint is onboarded, it should be visible under the **Devices** table and also start reporting audit logs to the **Activity Explorer**.</span></span>

> [!NOTE]
><span data-ttu-id="743d0-p118">Diese Funktion erfordert eine Lizenz. Ohne die erforderliche Lizenz werden keine Daten angezeigt und es ist kein Zugriff auf sie möglich.</span><span class="sxs-lookup"><span data-stu-id="743d0-p118">This experience is under license enforcement. Without the required license, data will not be visible or accessible.</span></span>

### <a name="viewing-endpoint-dlp-alerts-in-dlp-alerts-management-dashboard"></a><span data-ttu-id="743d0-210">Anzeigen von Endpunkt-DLP-Warnungen im Verwaltungsdashboard für DLP-Warnungen</span><span class="sxs-lookup"><span data-stu-id="743d0-210">Viewing Endpoint DLP alerts in DLP Alerts Management dashboard</span></span>

1. <span data-ttu-id="743d0-211">Öffnen Sie im Microsoft 365 Compliance Center die Seite "Verhinderung von Datenverlust" (DLP), und wählen Sie "Warnungen" aus.</span><span class="sxs-lookup"><span data-stu-id="743d0-211">Open the Data loss prevention page in the Microsoft 365 Compliance center and choose Alerts.</span></span>

2. <span data-ttu-id="743d0-212">Wenden Sie in [Konfigurieren und Anzeigen von Warnungen für DLP-Richtlinien](dlp-configure-view-alerts-policies.md) beschriebenen Verfahrensweisen an, um Warnungen für Ihre Endpunkt-DLP-Richtlinien anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="743d0-212">Refer to the procedures in [How to configure and view alerts for your DLP policies](dlp-configure-view-alerts-policies.md) to view alerts for your Endpoint DLP policies.</span></span>


### <a name="viewing-endpoint-dlp-data-in-activity-explorer"></a><span data-ttu-id="743d0-213">Anzeigen von Endpunkt-DLP-Daten im Aktivitäten-Explorer</span><span class="sxs-lookup"><span data-stu-id="743d0-213">Viewing Endpoint DLP data in activity explorer</span></span>

1. <span data-ttu-id="743d0-214">Öffnen Sie im Microsoft 365 Compliance Center die Seite [Datenklassifizierung](https://compliance.microsoft.com/dataclassification?viewid=overview) für Ihre Domäne, und wählen Sie den Aktivitäten-Explorer aus.</span><span class="sxs-lookup"><span data-stu-id="743d0-214">Open the [Data classification page](https://compliance.microsoft.com/dataclassification?viewid=overview) for your domain in the Microsoft 365 Compliance center and choose Activity explorer.</span></span>

2. <span data-ttu-id="743d0-215">Unter [Erste Schritte mit dem Aktivitäten-Explorer](data-classification-activity-explorer.md) erfahren Sie Näheres dazu, wie Sie auf alle Daten zu Ihren Endpunktgeräten zugreifen und diese filtern können.</span><span class="sxs-lookup"><span data-stu-id="743d0-215">Refer to the procedures in [Get started with Activity explorer](data-classification-activity-explorer.md) to access and filter all the data for your Endpoint devices.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="743d0-216">![Aktivitäten-Explorer-Filter für Endpunktgeräte](../media/endpoint-dlp-4-getting-started-activity-explorer.png)</span><span class="sxs-lookup"><span data-stu-id="743d0-216">![activity explorer filter for endpoint devices](../media/endpoint-dlp-4-getting-started-activity-explorer.png)</span></span>

## <a name="next-steps"></a><span data-ttu-id="743d0-217">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="743d0-217">Next steps</span></span>
<span data-ttu-id="743d0-218">Jetzt, da Geräte eingebunden sind und entsprechende Aktivitätsdaten im Aktivitäten-Explorer angezeigt werden, können Sie mit dem nächsten Schritt fortfahren, bei dem Sie DLP-Richtlinien zum Schutz Ihrer vertraulichen Elemente erstellen werden.</span><span class="sxs-lookup"><span data-stu-id="743d0-218">Now that you have onboarded devices and can view the activity data in Activity explorer, you are ready to move on to your next step where you create DLP policies that protect your sensitive items.</span></span>

- [<span data-ttu-id="743d0-219">Nutzung von Endpunkt-DLP (Vorschau)</span><span class="sxs-lookup"><span data-stu-id="743d0-219">Using Endpoint data loss prevention (preview)</span></span>](endpoint-dlp-using.md)

## <a name="see-also"></a><span data-ttu-id="743d0-220">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="743d0-220">See also</span></span>

- [<span data-ttu-id="743d0-221">Informationen zu Endpunkt-DLP (Vorschau)</span><span class="sxs-lookup"><span data-stu-id="743d0-221">Learn about Endpoint data loss prevention (preview)</span></span>](endpoint-dlp-learn-about.md)
- [<span data-ttu-id="743d0-222">Nutzung von Endpunkt-DLP (Vorschau)</span><span class="sxs-lookup"><span data-stu-id="743d0-222">Using Endpoint data loss prevention (preview)</span></span>](endpoint-dlp-using.md)
- [<span data-ttu-id="743d0-223">Verhinderung von Datenverlust – Übersicht</span><span class="sxs-lookup"><span data-stu-id="743d0-223">Overview of data loss prevention</span></span>](data-loss-prevention-policies.md)
- [<span data-ttu-id="743d0-224">Erstellen, Testen und Optimieren einer DLP-Richtlinie</span><span class="sxs-lookup"><span data-stu-id="743d0-224">Create, test, and tune a DLP policy</span></span>](create-test-tune-dlp-policy.md)
- [<span data-ttu-id="743d0-225">Erste Schritte mit dem Aktivitäten-Explorer</span><span class="sxs-lookup"><span data-stu-id="743d0-225">Get started with Activity explorer</span></span>](data-classification-activity-explorer.md)
- [<span data-ttu-id="743d0-226">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="743d0-226">Microsoft Defender for Endpoint</span></span>](https://docs.microsoft.com/windows/security/threat-protection/)
- [<span data-ttu-id="743d0-227">Onboarding-Tools und -Methoden für Windows 10-Computer</span><span class="sxs-lookup"><span data-stu-id="743d0-227">Onboarding tools and methods for Windows 10 machines</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints)
- [<span data-ttu-id="743d0-228">Microsoft 365-Abonnement</span><span class="sxs-lookup"><span data-stu-id="743d0-228">Microsoft 365 subscription</span></span>](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1)
- [<span data-ttu-id="743d0-229">Azure AD-verbundene Geräte</span><span class="sxs-lookup"><span data-stu-id="743d0-229">Azure AD joined devices</span></span>](https://docs.microsoft.com/azure/active-directory/devices/concept-azure-ad-join)
- [<span data-ttu-id="743d0-230">Herunterladen des auf Chromium basierenden neuen Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="743d0-230">Download the new Microsoft Edge based on Chromium</span></span>](https://support.microsoft.com/help/4501095/download-the-new-microsoft-edge-based-on-chromium)
