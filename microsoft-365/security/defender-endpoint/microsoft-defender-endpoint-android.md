---
title: Microsoft Defender für Endpunkt unter Android
ms.reviewer: ''
description: Beschreibt die Installation und Verwendung von Microsoft Defender for Endpoint unter Android
keywords: microsoft, defender, Microsoft Defender for Endpoint, android, installation, deploy, deinstallation, intune
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
ms.openlocfilehash: 3f8a8c04f608096e5c226d6899fbbd983bd8d8c1
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/06/2021
ms.locfileid: "52246428"
---
# <a name="microsoft-defender-for-endpoint-on-android"></a><span data-ttu-id="f2766-104">Microsoft Defender für Endpunkt unter Android</span><span class="sxs-lookup"><span data-stu-id="f2766-104">Microsoft Defender for Endpoint on Android</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="f2766-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="f2766-105">**Applies to:**</span></span>
- [<span data-ttu-id="f2766-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="f2766-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="f2766-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f2766-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="f2766-108">Möchten Sie Microsoft Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="f2766-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="f2766-109">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="f2766-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="f2766-110">In diesem Thema wird beschrieben, wie Sie Defender for Endpoint unter Android installieren, konfigurieren, aktualisieren und verwenden.</span><span class="sxs-lookup"><span data-stu-id="f2766-110">This topic describes how to install, configure, update, and use Defender for Endpoint on Android.</span></span>

> [!CAUTION]
> <span data-ttu-id="f2766-111">Das Ausführen anderer Endpunktschutzprodukte von Drittanbietern zusammen mit Defender for Endpoint auf Android verursacht wahrscheinlich Leistungsprobleme und unvorhersehbare Systemfehler.</span><span class="sxs-lookup"><span data-stu-id="f2766-111">Running other third-party endpoint protection products alongside Defender for Endpoint on Android is likely to cause performance problems and unpredictable system errors.</span></span>


## <a name="how-to-install-microsoft-defender-for-endpoint-on-android"></a><span data-ttu-id="f2766-112">Installieren von Microsoft Defender for Endpoint unter Android</span><span class="sxs-lookup"><span data-stu-id="f2766-112">How to install Microsoft Defender for Endpoint on Android</span></span>

### <a name="prerequisites"></a><span data-ttu-id="f2766-113">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="f2766-113">Prerequisites</span></span>

-   <span data-ttu-id="f2766-114">**Für Endbenutzer**</span><span class="sxs-lookup"><span data-stu-id="f2766-114">**For end users**</span></span>

    -   <span data-ttu-id="f2766-115">Microsoft Defender for Endpoint-Lizenz, die den Endbenutzern der App zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="f2766-115">Microsoft Defender for Endpoint license assigned to the end user(s) of the app.</span></span> <span data-ttu-id="f2766-116">Siehe [Microsoft Defender for Endpoint-Lizenzierungsanforderungen](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/minimum-requirements#licensing-requirements)</span><span class="sxs-lookup"><span data-stu-id="f2766-116">See [Microsoft Defender for Endpoint licensing requirements](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/minimum-requirements#licensing-requirements)</span></span>

    -   <span data-ttu-id="f2766-117">Intune-Unternehmensportal App kann von [Google Play](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal) heruntergeladen werden und ist auf dem Android-Gerät verfügbar.</span><span class="sxs-lookup"><span data-stu-id="f2766-117">Intune Company Portal app can be downloaded from [Google Play](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal) and is available on the Android device.</span></span>

        -   <span data-ttu-id="f2766-118">Darüber hinaus können Geräte [](https://docs.microsoft.com/mem/intune/user-help/enroll-device-android-company-portal) über die app Intune-Unternehmensportal registriert werden, um Intune-Richtlinien zur Gerätekonformität zu erzwingen.</span><span class="sxs-lookup"><span data-stu-id="f2766-118">Additionally, device(s) can be [enrolled](https://docs.microsoft.com/mem/intune/user-help/enroll-device-android-company-portal) via the Intune Company Portal app to enforce Intune device compliance policies.</span></span> <span data-ttu-id="f2766-119">Dies erfordert, dass dem Endbenutzer eine Lizenz Microsoft Intune wird.</span><span class="sxs-lookup"><span data-stu-id="f2766-119">This requires the end user to be assigned a Microsoft Intune license.</span></span>

    -   <span data-ttu-id="f2766-120">Weitere Informationen zum Zuweisen von Lizenzen finden Sie unter [Zuweisen von Lizenzen zu Benutzern](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-groups-assign).</span><span class="sxs-lookup"><span data-stu-id="f2766-120">For more information on how to assign licenses, see [Assign licenses to users](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-groups-assign).</span></span>
        

-   <span data-ttu-id="f2766-121">**Für Administratoren**</span><span class="sxs-lookup"><span data-stu-id="f2766-121">**For Administrators**</span></span>

    -   <span data-ttu-id="f2766-122">Zugriff auf das Microsoft Defender Security Center Portal.</span><span class="sxs-lookup"><span data-stu-id="f2766-122">Access to the Microsoft Defender Security Center portal.</span></span>

        > [!NOTE]
        > <span data-ttu-id="f2766-123">Microsoft Intune ist die einzige unterstützte Mobile Device Management (MDM)-Lösung für die Bereitstellung von Microsoft Defender for Endpoint unter Android.</span><span class="sxs-lookup"><span data-stu-id="f2766-123">Microsoft Intune is the only supported Mobile Device Management (MDM) solution for deploying Microsoft Defender for Endpoint on Android.</span></span> <span data-ttu-id="f2766-124">Derzeit werden nur registrierte Geräte für die Erzwingung von Defender for Endpoint auf Android-bezogenen Geräte-Compliancerichtlinien in Intune unterstützt.</span><span class="sxs-lookup"><span data-stu-id="f2766-124">Currently only enrolled devices are supported for enforcing Defender for Endpoint on Android related device compliance policies in Intune.</span></span> 

    -   <span data-ttu-id="f2766-125">Access [Microsoft Endpoint Manager Admin Center](https://go.microsoft.com/fwlink/?linkid=2109431), um die App für registrierte Benutzergruppen in Ihrer Organisation zu bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="f2766-125">Access [Microsoft Endpoint Manager admin center](https://go.microsoft.com/fwlink/?linkid=2109431), to deploy the app to enrolled user groups in your organization.</span></span>
        
### <a name="network-requirements"></a><span data-ttu-id="f2766-126">Netzwerkanforderungen</span><span class="sxs-lookup"><span data-stu-id="f2766-126">Network Requirements</span></span>

- <span data-ttu-id="f2766-127">Damit Microsoft Defender for Endpoint unter Android funktioniert, wenn es mit einem Netzwerk verbunden ist, muss die Firewall/der Proxy so konfiguriert werden, dass der Zugriff auf URLs des [Microsoft Defender for Endpoint-Diensts ermöglicht wird.](configure-proxy-internet.md#enable-access-to-microsoft-defender-for-endpoint-service-urls-in-the-proxy-server)</span><span class="sxs-lookup"><span data-stu-id="f2766-127">For Microsoft Defender for Endpoint on Android to function when connected to a network the firewall/proxy will need to be configured to [enable access to Microsoft Defender for Endpoint service URLs](configure-proxy-internet.md#enable-access-to-microsoft-defender-for-endpoint-service-urls-in-the-proxy-server).</span></span>

### <a name="system-requirements"></a><span data-ttu-id="f2766-128">Systemanforderungen</span><span class="sxs-lookup"><span data-stu-id="f2766-128">System Requirements</span></span>

-   <span data-ttu-id="f2766-129">Android-Geräte mit Android 6.0 und höher.</span><span class="sxs-lookup"><span data-stu-id="f2766-129">Android devices running Android 6.0 and above.</span></span>
-   <span data-ttu-id="f2766-130">Intune-Unternehmensportal App wird von [Google Play heruntergeladen](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal) und installiert.</span><span class="sxs-lookup"><span data-stu-id="f2766-130">Intune Company Portal app is downloaded from [Google Play](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal) and installed.</span></span> <span data-ttu-id="f2766-131">Die Geräteregistrierung ist erforderlich, damit Intune-Gerätekonformitätsrichtlinien erzwungen werden.</span><span class="sxs-lookup"><span data-stu-id="f2766-131">Device enrollment is required for Intune device compliance policies to be enforced.</span></span>

### <a name="installation-instructions"></a><span data-ttu-id="f2766-132">Installationsanweisungen</span><span class="sxs-lookup"><span data-stu-id="f2766-132">Installation instructions</span></span>

<span data-ttu-id="f2766-133">Microsoft Defender for Endpoint unter Android unterstützt die Installation auf beiden Modi registrierter Geräte – dem älteren Geräteadministrator und dem Android-Enterprise Modi.</span><span class="sxs-lookup"><span data-stu-id="f2766-133">Microsoft Defender for Endpoint on Android supports installation on both modes of enrolled devices - the legacy Device Administrator and Android Enterprise modes.</span></span>
<span data-ttu-id="f2766-134">**Derzeit werden persönliche Geräte mit Geschäftsprofil und unternehmenseigenen, vollständig verwalteten Benutzergeräteregistrierungen in Android-Geräten Enterprise. Unterstützung für andere Android-Enterprise Modi wird angekündigt, sobald sie bereit sind.**</span><span class="sxs-lookup"><span data-stu-id="f2766-134">**Currently, Personally-owned devices with work profile and Corporate-owned fully managed user device enrollments are supported in Android Enterprise. Support for other Android Enterprise modes will be announced when ready.**</span></span>

<span data-ttu-id="f2766-135">Die Bereitstellung von Microsoft Defender for Endpoint unter Android erfolgt über Microsoft Intune (MDM).</span><span class="sxs-lookup"><span data-stu-id="f2766-135">Deployment of Microsoft Defender for Endpoint on Android is via Microsoft Intune (MDM).</span></span>
<span data-ttu-id="f2766-136">Weitere Informationen finden Sie unter [Deploy Microsoft Defender for Endpoint on Android with Microsoft Intune](android-intune.md).</span><span class="sxs-lookup"><span data-stu-id="f2766-136">For more information, see [Deploy Microsoft Defender for Endpoint on Android with Microsoft Intune](android-intune.md).</span></span>


> [!NOTE]
> <span data-ttu-id="f2766-137">**Microsoft Defender für Endpoint unter Android ist jetzt auf [Google Play](https://play.google.com/store/apps/details?id=com.microsoft.scmx) verfügbar.**</span><span class="sxs-lookup"><span data-stu-id="f2766-137">**Microsoft Defender for Endpoint on Android is available on [Google Play](https://play.google.com/store/apps/details?id=com.microsoft.scmx) now.**</span></span> <br> <span data-ttu-id="f2766-138">Sie können von Intune aus eine Verbindung mit Google Play herstellen, um Microsoft Defender for Endpoint-App über geräteadministrator- und android-Enterprise bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="f2766-138">You can connect to Google Play from Intune to deploy Microsoft Defender for Endpoint app, across Device Administrator and Android Enterprise entrollment modes.</span></span> 

## <a name="how-to-configure-microsoft-defender-for-endpoint-on-android"></a><span data-ttu-id="f2766-139">Konfigurieren von Microsoft Defender for Endpoint unter Android</span><span class="sxs-lookup"><span data-stu-id="f2766-139">How to Configure Microsoft Defender for Endpoint on Android</span></span>

<span data-ttu-id="f2766-140">Anleitungen zum Konfigurieren von Microsoft Defender for Endpoint auf Android-Features finden Sie unter [Configure Microsoft Defender for Endpoint on Android features](android-configure.md).</span><span class="sxs-lookup"><span data-stu-id="f2766-140">Guidance on how to configure Microsoft Defender for Endpoint on Android features is available in [Configure Microsoft Defender for Endpoint on Android features](android-configure.md).</span></span>



## <a name="related-topics"></a><span data-ttu-id="f2766-141">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="f2766-141">Related topics</span></span>
- [<span data-ttu-id="f2766-142">Bereitstellen von Microsoft Defender für Endpunkt unter Android mit Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="f2766-142">Deploy Microsoft Defender for Endpoint on Android with Microsoft Intune</span></span>](android-intune.md)
- [<span data-ttu-id="f2766-143">Konfigurieren von Funktionen von Microsoft Defender für Endpunkt unter Android</span><span class="sxs-lookup"><span data-stu-id="f2766-143">Configure Microsoft Defender for Endpoint on Android features</span></span>](android-configure.md)

