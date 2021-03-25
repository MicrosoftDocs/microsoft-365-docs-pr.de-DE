---
title: Sicherstellen, dass Ihre Geräte ordnungsgemäß konfiguriert sind
description: Konfigurieren Sie Geräte ordnungsgemäß, um die Ausfallsicherheit gegen Bedrohungen insgesamt zu erhöhen und Ihre Fähigkeit zum Erkennen und Reagieren auf Angriffe zu verbessern.
keywords: Onboard, Intune-Verwaltung, MDATP, WDATP, Microsoft Defender, Windows Defender, erweiterter Bedrohungsschutz, Reduzierung der Angriffsfläche, ASR, Sicherheitsgrundlinie
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
ms.openlocfilehash: e7b00ceafc2761f42c316f434a27acf7c551e7cf
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/24/2021
ms.locfileid: "51163363"
---
# <a name="ensure-your-devices-are-configured-properly"></a><span data-ttu-id="3b30e-104">Sicherstellen, dass Ihre Geräte ordnungsgemäß konfiguriert sind</span><span class="sxs-lookup"><span data-stu-id="3b30e-104">Ensure your devices are configured properly</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="3b30e-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="3b30e-105">**Applies to:**</span></span>
- [<span data-ttu-id="3b30e-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="3b30e-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="3b30e-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="3b30e-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="3b30e-108">Möchten Sie Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="3b30e-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="3b30e-109">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="3b30e-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-onboardconfigure-abovefoldlink)

<span data-ttu-id="3b30e-110">Mit ordnungsgemäß konfigurierten Geräten können Sie die Ausfallsicherheit gegen Bedrohungen insgesamt erhöhen und Ihre Fähigkeit zum Erkennen und Reagieren auf Angriffe verbessern.</span><span class="sxs-lookup"><span data-stu-id="3b30e-110">With properly configured devices, you can boost overall resilience against threats and enhance your capability to detect and respond to attacks.</span></span> <span data-ttu-id="3b30e-111">Die Verwaltung der Sicherheitskonfiguration trägt dazu bei, dass Ihre Geräte:</span><span class="sxs-lookup"><span data-stu-id="3b30e-111">Security configuration management helps ensure that your devices:</span></span>

- <span data-ttu-id="3b30e-112">Onboarding bei Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="3b30e-112">Onboard to Microsoft Defender for Endpoint</span></span>
- <span data-ttu-id="3b30e-113">Erfüllen oder Überschreiten der Basiskonfiguration der Defender for Endpoint-Sicherheitsbasis</span><span class="sxs-lookup"><span data-stu-id="3b30e-113">Meet or exceed the Defender for Endpoint security baseline configuration</span></span>
- <span data-ttu-id="3b30e-114">Strategische Gegenmaßnahmen zur Angriffsfläche</span><span class="sxs-lookup"><span data-stu-id="3b30e-114">Have strategic attack surface mitigations in place</span></span>

<span data-ttu-id="3b30e-115">Klicken **Sie im Navigationsmenü** auf Konfigurationsverwaltung, um die Seite Gerätekonfigurationsverwaltung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="3b30e-115">Click **Configuration management** from the navigation menu to open the Device configuration management page.</span></span>

<span data-ttu-id="3b30e-116">![Sicherheitskonfigurationsverwaltungsseite](images/secconmgmt_main.png)</span><span class="sxs-lookup"><span data-stu-id="3b30e-116">![Security configuration management page](images/secconmgmt_main.png)</span></span><br>
<span data-ttu-id="3b30e-117">*Seite "Gerätekonfigurationsverwaltung"*</span><span class="sxs-lookup"><span data-stu-id="3b30e-117">*Device configuration management page*</span></span>

<span data-ttu-id="3b30e-118">Sie können den Konfigurationsstatus auf Organisatorischer Ebene nachverfolgen und schnell Maßnahmen ergreifen, um auf eine schlechte Onboardingabdeckung, Kompatibilitätsprobleme und schlecht optimierte Gegenmaßnahmen zur Angriffsfläche durch direkte, tiefe Links zu Geräteverwaltungsseiten in Microsoft Intune und Microsoft 365 Security Center zu reagieren.</span><span class="sxs-lookup"><span data-stu-id="3b30e-118">You can track configuration status at an organizational level and quickly take action in response to poor onboarding coverage, compliance issues, and poorly optimized attack surface mitigations through direct, deep links to device management pages on Microsoft Intune and Microsoft 365 security center.</span></span>

<span data-ttu-id="3b30e-119">Dabei profitieren Sie von:</span><span class="sxs-lookup"><span data-stu-id="3b30e-119">In doing so, you benefit from:</span></span>
- <span data-ttu-id="3b30e-120">Umfassende Sichtbarkeit der Ereignisse auf Ihren Geräten</span><span class="sxs-lookup"><span data-stu-id="3b30e-120">Comprehensive visibility of the events on your devices</span></span>
- <span data-ttu-id="3b30e-121">Robuste Bedrohungsintelligenz und leistungsstarke Gerätelerntechnologien für die Verarbeitung von Unformatereignissen und das Identifizieren der Verletzungsaktivität und Bedrohungsindikatoren</span><span class="sxs-lookup"><span data-stu-id="3b30e-121">Robust threat intelligence and powerful device learning technologies for processing raw events and identifying the breach activity and threat indicators</span></span>
- <span data-ttu-id="3b30e-122">Ein vollständiger Stapel von Sicherheitsfeatures, die so konfiguriert sind, dass die Installation von schädlichen Implanten, die Entführung von Systemdateien und -verfahren, die Daten-Exfiltration und andere Bedrohungsaktivitäten effizient beendet werden.</span><span class="sxs-lookup"><span data-stu-id="3b30e-122">A full stack of security features configured to efficiently stop the installation of malicious implants, hijacking of system files and process, data exfiltration, and other threat activities</span></span>
- <span data-ttu-id="3b30e-123">Optimierte Gegenmaßnahmen gegen Angriffsflächen, Maximierung der strategischen Verteidigung gegen Bedrohungsaktivitäten bei gleichzeitiger Minimierung der Produktivitätsauswirkungen</span><span class="sxs-lookup"><span data-stu-id="3b30e-123">Optimized attack surface mitigations, maximizing strategic defenses against threat activity while minimizing impact to productivity</span></span>

## <a name="enroll-devices-to-intune-management"></a><span data-ttu-id="3b30e-124">Registrieren von Geräten für die Intune-Verwaltung</span><span class="sxs-lookup"><span data-stu-id="3b30e-124">Enroll devices to Intune management</span></span>

<span data-ttu-id="3b30e-125">Die Gerätekonfigurationsverwaltung arbeitet eng mit der Intune-Geräteverwaltung zusammen, um das Inventar der Geräte in Ihrer Organisation und die grundlegende Sicherheitskonfiguration zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="3b30e-125">Device configuration management works closely with Intune device management to establish the inventory of the devices in your organization and the baseline security configuration.</span></span> <span data-ttu-id="3b30e-126">Sie können Konfigurationsprobleme auf von Intune verwalteten Windows 10-Geräten nachverfolgen und verwalten.</span><span class="sxs-lookup"><span data-stu-id="3b30e-126">You will be able to track and manage configuration issues on Intune-managed Windows 10 devices.</span></span>

<span data-ttu-id="3b30e-127">Bevor Sie sicherstellen können, dass Ihre Geräte ordnungsgemäß konfiguriert sind, registrieren Sie sie bei der Intune-Verwaltung.</span><span class="sxs-lookup"><span data-stu-id="3b30e-127">Before you can ensure your devices are configured properly, enroll them to Intune management.</span></span> <span data-ttu-id="3b30e-128">Die Intune-Registrierung ist robust und verfügt über mehrere Registrierungsoptionen für Windows 10-Geräte.</span><span class="sxs-lookup"><span data-stu-id="3b30e-128">Intune enrollment is robust and has several enrollment options for Windows 10 devices.</span></span> <span data-ttu-id="3b30e-129">Weitere Informationen zu Intune-Registrierungsoptionen finden Sie unter Einrichten [der Registrierung für Windows-Geräte.](https://docs.microsoft.com/intune/windows-enroll)</span><span class="sxs-lookup"><span data-stu-id="3b30e-129">For more information about Intune enrollment options, read about [setting up enrollment for Windows devices](https://docs.microsoft.com/intune/windows-enroll).</span></span>

>[!NOTE]
><span data-ttu-id="3b30e-130">Zum Registrieren von Windows-Geräten bei Intune müssen Administratoren bereits Lizenzen zugewiesen worden sein.</span><span class="sxs-lookup"><span data-stu-id="3b30e-130">To enroll Windows devices to Intune, administrators must have already been assigned licenses.</span></span> <span data-ttu-id="3b30e-131">[Informationen zum Zuweisen von Lizenzen für die Geräteregistrierung](https://docs.microsoft.com/intune/licenses-assign).</span><span class="sxs-lookup"><span data-stu-id="3b30e-131">[Read about assigning licenses for device enrollment](https://docs.microsoft.com/intune/licenses-assign).</span></span>

>[!TIP] 
><span data-ttu-id="3b30e-132">Um die Geräteverwaltung über Intune zu optimieren, [verbinden Sie Intune mit Defender for Endpoint](https://docs.microsoft.com/intune/advanced-threat-protection#enable-windows-defender-atp-in-intune).</span><span class="sxs-lookup"><span data-stu-id="3b30e-132">To optimize device management through Intune, [connect Intune to Defender for Endpoint](https://docs.microsoft.com/intune/advanced-threat-protection#enable-windows-defender-atp-in-intune).</span></span>

## <a name="obtain-required-permissions"></a><span data-ttu-id="3b30e-133">Abrufen der erforderlichen Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="3b30e-133">Obtain required permissions</span></span>
<span data-ttu-id="3b30e-134">Standardmäßig können nur Benutzer, denen die Rolle "Globaler Administrator" oder "Intune Service Administrator" in Azure AD zugewiesen wurde, die gerätekonfigurationsprofile verwalten und zuweisen, die für das Onboarding von Geräten und die Bereitstellung der Sicherheitsbasis erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="3b30e-134">By default, only users who have been assigned the Global Administrator or the Intune Service Administrator role on Azure AD can manage and assign the device configuration profiles needed for onboarding devices and deploying the security baseline.</span></span>

<span data-ttu-id="3b30e-135">Wenn Ihnen andere Rollen zugewiesen wurden, stellen Sie sicher, dass Sie über die erforderlichen Berechtigungen verfügen:</span><span class="sxs-lookup"><span data-stu-id="3b30e-135">If you have been assigned other roles, ensure you have the necessary permissions:</span></span>

- <span data-ttu-id="3b30e-136">Vollständige Berechtigungen für Gerätekonfigurationen</span><span class="sxs-lookup"><span data-stu-id="3b30e-136">Full permissions to device configurations</span></span>
- <span data-ttu-id="3b30e-137">Vollständige Berechtigungen für Sicherheitsgrundwerte</span><span class="sxs-lookup"><span data-stu-id="3b30e-137">Full permissions to security baselines</span></span>
- <span data-ttu-id="3b30e-138">Lesen von Berechtigungen für Gerätekonformitätsrichtlinien</span><span class="sxs-lookup"><span data-stu-id="3b30e-138">Read permissions to device compliance policies</span></span>
- <span data-ttu-id="3b30e-139">Lesen von Berechtigungen für die Organisation</span><span class="sxs-lookup"><span data-stu-id="3b30e-139">Read permissions to the organization</span></span>

<span data-ttu-id="3b30e-140">![Erforderliche Berechtigungen für Intune](images/secconmgmt_intune_permissions.png)</span><span class="sxs-lookup"><span data-stu-id="3b30e-140">![Required permissions on intune](images/secconmgmt_intune_permissions.png)</span></span><br>
<span data-ttu-id="3b30e-141">*Gerätekonfigurationsberechtigungen für Intune*</span><span class="sxs-lookup"><span data-stu-id="3b30e-141">*Device configuration permissions on Intune*</span></span>

>[!TIP] 
><span data-ttu-id="3b30e-142">Weitere Informationen zum Zuweisen von Berechtigungen für Intune finden Sie [unter Erstellen benutzerdefinierter Rollen](https://docs.microsoft.com/intune/create-custom-role#to-create-a-custom-role).</span><span class="sxs-lookup"><span data-stu-id="3b30e-142">To learn more about assigning permissions on Intune, [read about creating custom roles](https://docs.microsoft.com/intune/create-custom-role#to-create-a-custom-role).</span></span>

## <a name="in-this-section"></a><span data-ttu-id="3b30e-143">Inhalt dieses Abschnitts</span><span class="sxs-lookup"><span data-stu-id="3b30e-143">In this section</span></span>
<span data-ttu-id="3b30e-144">Thema</span><span class="sxs-lookup"><span data-stu-id="3b30e-144">Topic</span></span> | <span data-ttu-id="3b30e-145">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3b30e-145">Description</span></span>
:---|:---
[<span data-ttu-id="3b30e-146">In Defender for Endpoint integrierte Geräte</span><span class="sxs-lookup"><span data-stu-id="3b30e-146">Get devices onboarded to Defender for Endpoint</span></span>](configure-machines-onboarding.md)| <span data-ttu-id="3b30e-147">Verfolgen Sie den Onboardingstatus von von Intune verwalteten Geräten, und integrieren Sie weitere Geräte über Intune.</span><span class="sxs-lookup"><span data-stu-id="3b30e-147">Track onboarding status of Intune-managed devices and onboard more devices through Intune.</span></span> 
[<span data-ttu-id="3b30e-148">Erhöhen der Einhaltung der Sicherheitsgrundlinie für Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="3b30e-148">Increase compliance to the Defender for Endpoint security baseline</span></span>](configure-machines-security-baseline.md) | <span data-ttu-id="3b30e-149">Verfolgen Sie die Geplante Compliance und Nichtcompliance.</span><span class="sxs-lookup"><span data-stu-id="3b30e-149">Track baseline compliance and noncompliance.</span></span> <span data-ttu-id="3b30e-150">Stellen Sie die Sicherheitsgrundlinie auf mehr von Intune verwalteten Geräten zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="3b30e-150">Deploy the security baseline to more Intune-managed devices.</span></span>
[<span data-ttu-id="3b30e-151">Optimieren der Bereitstellung und Erkennung von ASR-Regeln</span><span class="sxs-lookup"><span data-stu-id="3b30e-151">Optimize ASR rule deployment and detections</span></span>](configure-machines-asr.md) | <span data-ttu-id="3b30e-152">Überprüfen sie die Erkennung von Regelbereitstellungen und Optimierungen mithilfe von Impact Analysis Tools im Microsoft 365 Security Center.</span><span class="sxs-lookup"><span data-stu-id="3b30e-152">Review rule deployment and tweak detections using impact analysis tools in Microsoft 365 security center.</span></span>

><span data-ttu-id="3b30e-153">Möchten Sie Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="3b30e-153">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="3b30e-154">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="3b30e-154">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-onboardconfigure-belowfoldlink)
