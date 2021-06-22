---
title: Microsoft Defender für Endpunkt unter Android
ms.reviewer: ''
description: Beschreibt, wie Microsoft Defender für Endpunkt unter Android installiert und verwendet wird
keywords: Microsoft, Defender, Microsoft Defender für Endpunkt, Android, Installation, bereitstellen, Deinstallation, Intune
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: ceccd9e3c8a8137f672e7be519675034a84c7881
ms.sourcegitcommit: fa9efab24a84f71fec7d001f2ad8949125fa8eee
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/22/2021
ms.locfileid: "53055112"
---
# <a name="microsoft-defender-for-endpoint-on-android"></a><span data-ttu-id="76e5a-104">Microsoft Defender für Endpunkt unter Android</span><span class="sxs-lookup"><span data-stu-id="76e5a-104">Microsoft Defender for Endpoint on Android</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="76e5a-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="76e5a-105">**Applies to:**</span></span>
- [<span data-ttu-id="76e5a-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="76e5a-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="76e5a-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="76e5a-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="76e5a-108">Möchten Sie Microsoft Defender für Endpunkt erleben?</span><span class="sxs-lookup"><span data-stu-id="76e5a-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="76e5a-109">Registrieren Sie sich für eine kostenlose Testversion</span><span class="sxs-lookup"><span data-stu-id="76e5a-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="76e5a-110">In diesem Thema wird beschrieben, wie Sie Defender für Endpunkt unter Android installieren, konfigurieren, aktualisieren und verwenden.</span><span class="sxs-lookup"><span data-stu-id="76e5a-110">This topic describes how to install, configure, update, and use Defender for Endpoint on Android.</span></span>

> [!CAUTION]
> <span data-ttu-id="76e5a-111">Das Ausführen anderer Endpunktschutzprodukte von Drittanbietern zusammen mit Defender für Endpunkt unter Android führt wahrscheinlich zu Leistungsproblemen und unvorhersehbaren Systemfehlern.</span><span class="sxs-lookup"><span data-stu-id="76e5a-111">Running other third-party endpoint protection products alongside Defender for Endpoint on Android is likely to cause performance problems and unpredictable system errors.</span></span>


## <a name="how-to-install-microsoft-defender-for-endpoint-on-android"></a><span data-ttu-id="76e5a-112">So installieren Sie Microsoft Defender für Endpunkt unter Android</span><span class="sxs-lookup"><span data-stu-id="76e5a-112">How to install Microsoft Defender for Endpoint on Android</span></span>

### <a name="prerequisites"></a><span data-ttu-id="76e5a-113">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="76e5a-113">Prerequisites</span></span>

-   <span data-ttu-id="76e5a-114">**Für Endbenutzer**</span><span class="sxs-lookup"><span data-stu-id="76e5a-114">**For end users**</span></span>

    -   <span data-ttu-id="76e5a-115">Microsoft Defender für Endpunkt-Lizenz, die den Endbenutzern der App zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="76e5a-115">Microsoft Defender for Endpoint license assigned to the end user(s) of the app.</span></span> <span data-ttu-id="76e5a-116">Siehe [Microsoft Defender für Endpunkt-Lizenzierungsanforderungen](/microsoft-365/security/defender-endpoint/minimum-requirements#licensing-requirements)</span><span class="sxs-lookup"><span data-stu-id="76e5a-116">See [Microsoft Defender for Endpoint licensing requirements](/microsoft-365/security/defender-endpoint/minimum-requirements#licensing-requirements)</span></span>

    -   <span data-ttu-id="76e5a-117">Intune-Unternehmensportal App kann von [Google Play](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal) heruntergeladen werden und ist auf dem Android-Gerät verfügbar.</span><span class="sxs-lookup"><span data-stu-id="76e5a-117">Intune Company Portal app can be downloaded from [Google Play](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal) and is available on the Android device.</span></span>

        -   <span data-ttu-id="76e5a-118">Darüber hinaus können Geräte über die Intune-Unternehmensportal-App [registriert](/mem/intune/user-help/enroll-device-android-company-portal) werden, um Intune-Gerätekompatibilitätsrichtlinien zu erzwingen.</span><span class="sxs-lookup"><span data-stu-id="76e5a-118">Additionally, device(s) can be [enrolled](/mem/intune/user-help/enroll-device-android-company-portal) via the Intune Company Portal app to enforce Intune device compliance policies.</span></span> <span data-ttu-id="76e5a-119">Dies erfordert, dass dem Endbenutzer eine Microsoft Intune Lizenz zugewiesen wird.</span><span class="sxs-lookup"><span data-stu-id="76e5a-119">This requires the end user to be assigned a Microsoft Intune license.</span></span>

    -   <span data-ttu-id="76e5a-120">Weitere Informationen zum Zuweisen von Lizenzen finden Sie unter [Zuweisen von Lizenzen zu Benutzern.](/azure/active-directory/users-groups-roles/licensing-groups-assign)</span><span class="sxs-lookup"><span data-stu-id="76e5a-120">For more information on how to assign licenses, see [Assign licenses to users](/azure/active-directory/users-groups-roles/licensing-groups-assign).</span></span>
        

-   <span data-ttu-id="76e5a-121">**Für Administratoren**</span><span class="sxs-lookup"><span data-stu-id="76e5a-121">**For Administrators**</span></span>

    -   <span data-ttu-id="76e5a-122">Zugriff auf das Microsoft Defender Security Center-Portal.</span><span class="sxs-lookup"><span data-stu-id="76e5a-122">Access to the Microsoft Defender Security Center portal.</span></span>

        > [!NOTE]
        > <span data-ttu-id="76e5a-123">Microsoft Intune ist die einzige unterstützte Mdm-Lösung (Mobile Device Management) für die Bereitstellung von Microsoft Defender für Endpunkt unter Android.</span><span class="sxs-lookup"><span data-stu-id="76e5a-123">Microsoft Intune is the only supported Mobile Device Management (MDM) solution for deploying Microsoft Defender for Endpoint on Android.</span></span> <span data-ttu-id="76e5a-124">Derzeit werden nur registrierte Geräte unterstützt, um Defender für Endpunkt für Android-bezogene Gerätecompliancerichtlinien in Intune zu erzwingen.</span><span class="sxs-lookup"><span data-stu-id="76e5a-124">Currently only enrolled devices are supported for enforcing Defender for Endpoint on Android related device compliance policies in Intune.</span></span> 

    -   <span data-ttu-id="76e5a-125">Greifen Sie [auf Microsoft Endpoint Manager Admin Center](https://go.microsoft.com/fwlink/?linkid=2109431)zu, um die App für registrierte Benutzergruppen in Ihrer Organisation bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="76e5a-125">Access [Microsoft Endpoint Manager admin center](https://go.microsoft.com/fwlink/?linkid=2109431), to deploy the app to enrolled user groups in your organization.</span></span>
        
### <a name="network-requirements"></a><span data-ttu-id="76e5a-126">Netzwerkanforderungen</span><span class="sxs-lookup"><span data-stu-id="76e5a-126">Network Requirements</span></span>

- <span data-ttu-id="76e5a-127">Damit Microsoft Defender für Endpunkt unter Android funktioniert, wenn es mit einem Netzwerk verbunden ist, muss die Firewall/der Proxy konfiguriert werden, um [den Zugriff auf Microsoft Defender für Endpunktdienst-URLs zu ermöglichen.](configure-proxy-internet.md#enable-access-to-microsoft-defender-for-endpoint-service-urls-in-the-proxy-server)</span><span class="sxs-lookup"><span data-stu-id="76e5a-127">For Microsoft Defender for Endpoint on Android to function when connected to a network the firewall/proxy will need to be configured to [enable access to Microsoft Defender for Endpoint service URLs](configure-proxy-internet.md#enable-access-to-microsoft-defender-for-endpoint-service-urls-in-the-proxy-server).</span></span>

### <a name="system-requirements"></a><span data-ttu-id="76e5a-128">Systemanforderungen</span><span class="sxs-lookup"><span data-stu-id="76e5a-128">System Requirements</span></span>

-   <span data-ttu-id="76e5a-129">Mobiltelefone mit Android 6.0 und höher.</span><span class="sxs-lookup"><span data-stu-id="76e5a-129">Mobile phones running Android 6.0 and above.</span></span> <span data-ttu-id="76e5a-130">**Tablets und andere mobile Geräte unter Android werden derzeit nicht unterstützt.**</span><span class="sxs-lookup"><span data-stu-id="76e5a-130">**Tablets and other mobile devices running Android are not currently supported.**</span></span> 

-   <span data-ttu-id="76e5a-131">Intune-Unternehmensportal App wird von [Google Play](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal) heruntergeladen und installiert.</span><span class="sxs-lookup"><span data-stu-id="76e5a-131">Intune Company Portal app is downloaded from [Google Play](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal) and installed.</span></span> <span data-ttu-id="76e5a-132">Die Geräteregistrierung ist erforderlich, damit Intune-Gerätekompatibilitätsrichtlinien erzwungen werden.</span><span class="sxs-lookup"><span data-stu-id="76e5a-132">Device enrollment is required for Intune device compliance policies to be enforced.</span></span>

### <a name="installation-instructions"></a><span data-ttu-id="76e5a-133">Installationsanweisungen</span><span class="sxs-lookup"><span data-stu-id="76e5a-133">Installation instructions</span></span>

<span data-ttu-id="76e5a-134">Microsoft Defender für Endpunkt unter Android unterstützt die Installation auf beiden Modi registrierter Geräte – dem Legacy-Geräteadministrator und android-Enterprise Modi.</span><span class="sxs-lookup"><span data-stu-id="76e5a-134">Microsoft Defender for Endpoint on Android supports installation on both modes of enrolled devices - the legacy Device Administrator and Android Enterprise modes.</span></span>
<span data-ttu-id="76e5a-135">**Derzeit werden persönliche Geräte mit Arbeitsprofil und vollständig verwalteten Benutzergeräteregistrierungen im Besitz des Unternehmens in Android Enterprise unterstützt. Unterstützung für andere Android Enterprise Modi wird angekündigt, wenn sie bereit sind.**</span><span class="sxs-lookup"><span data-stu-id="76e5a-135">**Currently, Personally-owned devices with work profile and Corporate-owned fully managed user device enrollments are supported in Android Enterprise. Support for other Android Enterprise modes will be announced when ready.**</span></span>

<span data-ttu-id="76e5a-136">Die Bereitstellung von Microsoft Defender für Endpunkt unter Android erfolgt über Microsoft Intune (MDM).</span><span class="sxs-lookup"><span data-stu-id="76e5a-136">Deployment of Microsoft Defender for Endpoint on Android is via Microsoft Intune (MDM).</span></span>
<span data-ttu-id="76e5a-137">Weitere Informationen finden Sie unter [Bereitstellen von Microsoft Defender für Endpunkt unter Android mit Microsoft Intune.](android-intune.md)</span><span class="sxs-lookup"><span data-stu-id="76e5a-137">For more information, see [Deploy Microsoft Defender for Endpoint on Android with Microsoft Intune](android-intune.md).</span></span>


> [!NOTE]
> <span data-ttu-id="76e5a-138">**Microsoft Defender für Endpunkt unter Android ist jetzt in [Google Play](https://play.google.com/store/apps/details?id=com.microsoft.scmx) verfügbar.**</span><span class="sxs-lookup"><span data-stu-id="76e5a-138">**Microsoft Defender for Endpoint on Android is available on [Google Play](https://play.google.com/store/apps/details?id=com.microsoft.scmx) now.**</span></span> <br> <span data-ttu-id="76e5a-139">Sie können von Intune aus eine Verbindung mit Google Play herstellen, um die Microsoft Defender für Endpunkt-App über Geräteadministrator- und Android-Enterprise-Registrierungsmodi bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="76e5a-139">You can connect to Google Play from Intune to deploy Microsoft Defender for Endpoint app, across Device Administrator and Android Enterprise entrollment modes.</span></span> 

## <a name="how-to-configure-microsoft-defender-for-endpoint-on-android"></a><span data-ttu-id="76e5a-140">So konfigurieren Sie Microsoft Defender für Endpunkt unter Android</span><span class="sxs-lookup"><span data-stu-id="76e5a-140">How to Configure Microsoft Defender for Endpoint on Android</span></span>

<span data-ttu-id="76e5a-141">Anleitungen zum Konfigurieren von Microsoft Defender für Endpunkt unter Android-Features finden Sie unter [Konfigurieren von Microsoft Defender für Endpunkt unter Android-Features.](android-configure.md)</span><span class="sxs-lookup"><span data-stu-id="76e5a-141">Guidance on how to configure Microsoft Defender for Endpoint on Android features is available in [Configure Microsoft Defender for Endpoint on Android features](android-configure.md).</span></span>



## <a name="related-topics"></a><span data-ttu-id="76e5a-142">Ähnliche Themen</span><span class="sxs-lookup"><span data-stu-id="76e5a-142">Related topics</span></span>
- [<span data-ttu-id="76e5a-143">Bereitstellen von Microsoft Defender für Endpunkt unter Android mit Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="76e5a-143">Deploy Microsoft Defender for Endpoint on Android with Microsoft Intune</span></span>](android-intune.md)
- [<span data-ttu-id="76e5a-144">Konfigurieren von Funktionen von Microsoft Defender für Endpunkt unter Android</span><span class="sxs-lookup"><span data-stu-id="76e5a-144">Configure Microsoft Defender for Endpoint on Android features</span></span>](android-configure.md)

