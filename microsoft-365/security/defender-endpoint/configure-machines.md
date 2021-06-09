---
title: Sicherstellen, dass Ihre Geräte ordnungsgemäß konfiguriert sind
description: Konfigurieren Sie Geräte ordnungsgemäß, um die resilienz gegenüber Bedrohungen insgesamt zu erhöhen und Ihre Fähigkeit, Angriffe zu erkennen und darauf zu reagieren, zu verbessern.
keywords: Onboarding, Intune-Verwaltung, Microsoft Defender für Endpunkt, Microsoft Defender, Windows Defender, Verringerung der Angriffsfläche, ASR, Sicherheitsgrundwerte
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: lomayor
author: lomayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: dccc623bfa6c3f5e8fe4d88ccfafd66d3e53482a
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2021
ms.locfileid: "52840898"
---
# <a name="ensure-your-devices-are-configured-properly"></a><span data-ttu-id="eba02-104">Sicherstellen, dass Ihre Geräte ordnungsgemäß konfiguriert sind</span><span class="sxs-lookup"><span data-stu-id="eba02-104">Ensure your devices are configured properly</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="eba02-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="eba02-105">**Applies to:**</span></span>
- [<span data-ttu-id="eba02-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="eba02-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="eba02-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="eba02-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="eba02-108">Möchten Sie Defender für Endpunkt erleben?</span><span class="sxs-lookup"><span data-stu-id="eba02-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="eba02-109">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="eba02-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-onboardconfigure-abovefoldlink)

<span data-ttu-id="eba02-110">Mit ordnungsgemäß konfigurierten Geräten können Sie die resilienz insgesamt gegen Bedrohungen erhöhen und Ihre Fähigkeit verbessern, Angriffe zu erkennen und darauf zu reagieren.</span><span class="sxs-lookup"><span data-stu-id="eba02-110">With properly configured devices, you can boost overall resilience against threats and enhance your capability to detect and respond to attacks.</span></span> <span data-ttu-id="eba02-111">Mithilfe der Sicherheitskonfigurationsverwaltung können Sie sicherstellen, dass Ihre Geräte:</span><span class="sxs-lookup"><span data-stu-id="eba02-111">Security configuration management helps ensure that your devices:</span></span>

- <span data-ttu-id="eba02-112">Onboarding in Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="eba02-112">Onboard to Microsoft Defender for Endpoint</span></span>
- <span data-ttu-id="eba02-113">Erfüllen oder Überschreiten der Sicherheitsbaselinekonfiguration von Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="eba02-113">Meet or exceed the Defender for Endpoint security baseline configuration</span></span>
- <span data-ttu-id="eba02-114">Strategische Angriffsflächen-Gegenmaßnahmen</span><span class="sxs-lookup"><span data-stu-id="eba02-114">Have strategic attack surface mitigations in place</span></span>

<span data-ttu-id="eba02-115">Klicken Sie im Navigationsmenü auf **"Konfigurationsverwaltung",** um die Seite "Gerätekonfigurationsverwaltung" zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="eba02-115">Click **Configuration management** from the navigation menu to open the Device configuration management page.</span></span>

<span data-ttu-id="eba02-116">![Seite "Verwaltung der Sicherheitskonfiguration"](images/secconmgmt_main.png)</span><span class="sxs-lookup"><span data-stu-id="eba02-116">![Security configuration management page](images/secconmgmt_main.png)</span></span><br>
<span data-ttu-id="eba02-117">*Seite "Gerätekonfigurationsverwaltung"*</span><span class="sxs-lookup"><span data-stu-id="eba02-117">*Device configuration management page*</span></span>

<span data-ttu-id="eba02-118">Sie können den Konfigurationsstatus auf Organisationsebene nachverfolgen und schnell Maßnahmen ergreifen, um auf eine schlechte Onboarding-Abdeckung, Compliance-Probleme und schlecht optimierte Angriffsflächenminderungen über direkte, tiefe Links zu Geräteverwaltungsseiten in Microsoft Intune und Microsoft 365 Security Center zu reagieren.</span><span class="sxs-lookup"><span data-stu-id="eba02-118">You can track configuration status at an organizational level and quickly take action in response to poor onboarding coverage, compliance issues, and poorly optimized attack surface mitigations through direct, deep links to device management pages on Microsoft Intune and Microsoft 365 security center.</span></span>

<span data-ttu-id="eba02-119">Dadurch profitieren Sie von Folgendem:</span><span class="sxs-lookup"><span data-stu-id="eba02-119">In doing so, you benefit from:</span></span>
- <span data-ttu-id="eba02-120">Umfassende Sichtbarkeit der Ereignisse auf Ihren Geräten</span><span class="sxs-lookup"><span data-stu-id="eba02-120">Comprehensive visibility of the events on your devices</span></span>
- <span data-ttu-id="eba02-121">Robuste Bedrohungserkennung und leistungsstarke Gerätelerntechnologien für die Verarbeitung von Rohereignissen und die Identifizierung der Aktivität von Sicherheitsverletzungen und Bedrohungsindikatoren</span><span class="sxs-lookup"><span data-stu-id="eba02-121">Robust threat intelligence and powerful device learning technologies for processing raw events and identifying the breach activity and threat indicators</span></span>
- <span data-ttu-id="eba02-122">Ein vollständiger Stapel von Sicherheitsfeatures, die so konfiguriert sind, dass die Installation schädlicher Implente, das Missbrauch von Systemdateien und -prozessen, die Datenexfiltration und andere Bedrohungsaktivitäten effizient beendet werden.</span><span class="sxs-lookup"><span data-stu-id="eba02-122">A full stack of security features configured to efficiently stop the installation of malicious implants, hijacking of system files and process, data exfiltration, and other threat activities</span></span>
- <span data-ttu-id="eba02-123">Optimierte Angriffsflächenminderungen, die die strategische Abwehr von Bedrohungsaktivitäten maximieren und gleichzeitig die Auswirkungen auf die Produktivität minimieren</span><span class="sxs-lookup"><span data-stu-id="eba02-123">Optimized attack surface mitigations, maximizing strategic defenses against threat activity while minimizing impact to productivity</span></span>

## <a name="enroll-devices-to-intune-management"></a><span data-ttu-id="eba02-124">Registrieren von Geräten bei der Intune-Verwaltung</span><span class="sxs-lookup"><span data-stu-id="eba02-124">Enroll devices to Intune management</span></span>

<span data-ttu-id="eba02-125">Die Gerätekonfigurationsverwaltung arbeitet eng mit der Intune-Geräteverwaltung zusammen, um den Bestand der Geräte in Ihrer Organisation und die grundlegende Sicherheitskonfiguration einzurichten.</span><span class="sxs-lookup"><span data-stu-id="eba02-125">Device configuration management works closely with Intune device management to establish the inventory of the devices in your organization and the baseline security configuration.</span></span> <span data-ttu-id="eba02-126">Sie können Konfigurationsprobleme auf von Intune verwalteten Windows 10-Geräten nachverfolgen und verwalten.</span><span class="sxs-lookup"><span data-stu-id="eba02-126">You will be able to track and manage configuration issues on Intune-managed Windows 10 devices.</span></span>

<span data-ttu-id="eba02-127">Bevor Sie sicherstellen können, dass Ihre Geräte ordnungsgemäß konfiguriert sind, registrieren Sie sie bei der Intune-Verwaltung.</span><span class="sxs-lookup"><span data-stu-id="eba02-127">Before you can ensure your devices are configured properly, enroll them to Intune management.</span></span> <span data-ttu-id="eba02-128">Die Intune-Registrierung ist robust und verfügt über mehrere Registrierungsoptionen für Windows 10 Geräte.</span><span class="sxs-lookup"><span data-stu-id="eba02-128">Intune enrollment is robust and has several enrollment options for Windows 10 devices.</span></span> <span data-ttu-id="eba02-129">Weitere Informationen zu Intune-Registrierungsoptionen finden Sie unter "Einrichten der [Registrierung für Windows Geräte".](/intune/windows-enroll)</span><span class="sxs-lookup"><span data-stu-id="eba02-129">For more information about Intune enrollment options, read about [setting up enrollment for Windows devices](/intune/windows-enroll).</span></span>

>[!NOTE]
><span data-ttu-id="eba02-130">Um Windows Geräte bei Intune zu registrieren, müssen Administratoren bereits Lizenzen zugewiesen worden sein.</span><span class="sxs-lookup"><span data-stu-id="eba02-130">To enroll Windows devices to Intune, administrators must have already been assigned licenses.</span></span> <span data-ttu-id="eba02-131">[Informationen zum Zuweisen von Lizenzen für die Geräteregistrierung.](/intune/licenses-assign)</span><span class="sxs-lookup"><span data-stu-id="eba02-131">[Read about assigning licenses for device enrollment](/intune/licenses-assign).</span></span>

>[!TIP] 
><span data-ttu-id="eba02-132">Um die Geräteverwaltung über Intune zu optimieren, [verbinden Sie Intune mit Defender für Endpunkt.](/intune/advanced-threat-protection#enable-windows-defender-atp-in-intune)</span><span class="sxs-lookup"><span data-stu-id="eba02-132">To optimize device management through Intune, [connect Intune to Defender for Endpoint](/intune/advanced-threat-protection#enable-windows-defender-atp-in-intune).</span></span>

## <a name="obtain-required-permissions"></a><span data-ttu-id="eba02-133">Abrufen der erforderlichen Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="eba02-133">Obtain required permissions</span></span>
<span data-ttu-id="eba02-134">Standardmäßig können nur Benutzer, denen die Rolle "Globaler Administrator" oder "Intune-Dienstadministrator" in Azure AD zugewiesen wurde, die gerätekonfigurationsprofile verwalten und zuweisen, die für das Onboarding von Geräten und die Bereitstellung der Sicherheitsgrundwerte erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="eba02-134">By default, only users who have been assigned the Global Administrator or the Intune Service Administrator role on Azure AD can manage and assign the device configuration profiles needed for onboarding devices and deploying the security baseline.</span></span>

<span data-ttu-id="eba02-135">Wenn Ihnen andere Rollen zugewiesen wurden, stellen Sie sicher, dass Sie über die erforderlichen Berechtigungen verfügen:</span><span class="sxs-lookup"><span data-stu-id="eba02-135">If you have been assigned other roles, ensure you have the necessary permissions:</span></span>

- <span data-ttu-id="eba02-136">Vollständige Berechtigungen für Gerätekonfigurationen</span><span class="sxs-lookup"><span data-stu-id="eba02-136">Full permissions to device configurations</span></span>
- <span data-ttu-id="eba02-137">Vollständige Berechtigungen für Sicherheitsgrundwerte</span><span class="sxs-lookup"><span data-stu-id="eba02-137">Full permissions to security baselines</span></span>
- <span data-ttu-id="eba02-138">Leseberechtigungen für Gerätekompatibilitätsrichtlinien</span><span class="sxs-lookup"><span data-stu-id="eba02-138">Read permissions to device compliance policies</span></span>
- <span data-ttu-id="eba02-139">Leseberechtigungen für die Organisation</span><span class="sxs-lookup"><span data-stu-id="eba02-139">Read permissions to the organization</span></span>

<span data-ttu-id="eba02-140">![Erforderliche Berechtigungen für Intune](images/secconmgmt_intune_permissions.png)</span><span class="sxs-lookup"><span data-stu-id="eba02-140">![Required permissions on intune](images/secconmgmt_intune_permissions.png)</span></span><br>
<span data-ttu-id="eba02-141">*Gerätekonfigurationsberechtigungen in Intune*</span><span class="sxs-lookup"><span data-stu-id="eba02-141">*Device configuration permissions on Intune*</span></span>

>[!TIP] 
><span data-ttu-id="eba02-142">Weitere Informationen zum Zuweisen von Berechtigungen für Intune [finden Sie unter Erstellen benutzerdefinierter Rollen.](/intune/create-custom-role#to-create-a-custom-role)</span><span class="sxs-lookup"><span data-stu-id="eba02-142">To learn more about assigning permissions on Intune, [read about creating custom roles](/intune/create-custom-role#to-create-a-custom-role).</span></span>

## <a name="in-this-section"></a><span data-ttu-id="eba02-143">Inhalt dieses Abschnitts</span><span class="sxs-lookup"><span data-stu-id="eba02-143">In this section</span></span>
<span data-ttu-id="eba02-144">Thema</span><span class="sxs-lookup"><span data-stu-id="eba02-144">Topic</span></span> | <span data-ttu-id="eba02-145">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="eba02-145">Description</span></span>
:---|:---
[<span data-ttu-id="eba02-146">Geräte in Defender für Endpunkt integrieren</span><span class="sxs-lookup"><span data-stu-id="eba02-146">Get devices onboarded to Defender for Endpoint</span></span>](configure-machines-onboarding.md)| <span data-ttu-id="eba02-147">Nachverfolgen des Onboardingstatus von von Intune verwalteten Geräten und Onboarding weiterer Geräte über Intune.</span><span class="sxs-lookup"><span data-stu-id="eba02-147">Track onboarding status of Intune-managed devices and onboard more devices through Intune.</span></span> 
[<span data-ttu-id="eba02-148">Erhöhen der Compliance für die Defender für Endpunkt-Sicherheitsgrundwerte</span><span class="sxs-lookup"><span data-stu-id="eba02-148">Increase compliance to the Defender for Endpoint security baseline</span></span>](configure-machines-security-baseline.md) | <span data-ttu-id="eba02-149">Nachverfolgen der Geplanten Compliance und Nichtkonformität.</span><span class="sxs-lookup"><span data-stu-id="eba02-149">Track baseline compliance and noncompliance.</span></span> <span data-ttu-id="eba02-150">Stellen Sie die Sicherheitsgrundwerte auf mehr von Intune verwalteten Geräten bereit.</span><span class="sxs-lookup"><span data-stu-id="eba02-150">Deploy the security baseline to more Intune-managed devices.</span></span>
[<span data-ttu-id="eba02-151">Optimieren der Bereitstellung und Erkennung von ASR-Regeln</span><span class="sxs-lookup"><span data-stu-id="eba02-151">Optimize ASR rule deployment and detections</span></span>](configure-machines-asr.md) | <span data-ttu-id="eba02-152">Überprüfen Sie die Regelbereitstellung und optimieren Sie die Erkennungen mithilfe von Auswirkungsanalysetools im Microsoft 365 Security Center.</span><span class="sxs-lookup"><span data-stu-id="eba02-152">Review rule deployment and tweak detections using impact analysis tools in Microsoft 365 security center.</span></span>

><span data-ttu-id="eba02-153">Möchten Sie Defender für Endpunkt erleben?</span><span class="sxs-lookup"><span data-stu-id="eba02-153">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="eba02-154">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="eba02-154">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-onboardconfigure-belowfoldlink)
