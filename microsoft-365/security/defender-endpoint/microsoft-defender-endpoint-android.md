---
title: Microsoft Defender ATP für Android
ms.reviewer: ''
description: Beschreibt die Installation und Verwendung von Microsoft Defender ATP für Android
keywords: microsoft, defender, atp, android, installation, deploy, deinstallation, intune
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
ms.openlocfilehash: 6518b86861fd5d03533bb787d4ee005d7ace1a0c
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51068831"
---
# <a name="microsoft-defender-for-endpoint-for-android"></a><span data-ttu-id="16928-104">Microsoft Defender für Endpoint für Android</span><span class="sxs-lookup"><span data-stu-id="16928-104">Microsoft Defender for Endpoint for Android</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="16928-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="16928-105">**Applies to:**</span></span>
- [<span data-ttu-id="16928-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="16928-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [<span data-ttu-id="16928-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="16928-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="16928-108">Möchten Sie Microsoft Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="16928-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="16928-109">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="16928-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="16928-110">In diesem Thema wird beschrieben, wie Sie Defender for Endpoint für Android installieren, konfigurieren, aktualisieren und verwenden.</span><span class="sxs-lookup"><span data-stu-id="16928-110">This topic describes how to install, configure, update, and use Defender for Endpoint for Android.</span></span>

> [!CAUTION]
> <span data-ttu-id="16928-111">Das Ausführen anderer Endpunktschutzprodukte von Drittanbietern zusammen mit Defender for Endpoint für Android verursacht wahrscheinlich Leistungsprobleme und unvorhersehbare Systemfehler.</span><span class="sxs-lookup"><span data-stu-id="16928-111">Running other third-party endpoint protection products alongside Defender for Endpoint for Android is likely to cause performance problems and unpredictable system errors.</span></span>


## <a name="how-to-install-microsoft-defender-for-endpoint-for-android"></a><span data-ttu-id="16928-112">Installieren von Microsoft Defender for Endpoint für Android</span><span class="sxs-lookup"><span data-stu-id="16928-112">How to install Microsoft Defender for Endpoint for Android</span></span>

### <a name="prerequisites"></a><span data-ttu-id="16928-113">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="16928-113">Prerequisites</span></span>

-   <span data-ttu-id="16928-114">**Für Endbenutzer**</span><span class="sxs-lookup"><span data-stu-id="16928-114">**For end users**</span></span>

    -   <span data-ttu-id="16928-115">Microsoft Defender for Endpoint-Lizenz, die den Endbenutzern der App zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="16928-115">Microsoft Defender for Endpoint license assigned to the end user(s) of the app.</span></span> <span data-ttu-id="16928-116">Siehe [Microsoft Defender for Endpoint-Lizenzierungsanforderungen](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/minimum-requirements#licensing-requirements)</span><span class="sxs-lookup"><span data-stu-id="16928-116">See [Microsoft Defender for Endpoint licensing requirements](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/minimum-requirements#licensing-requirements)</span></span>

    -   <span data-ttu-id="16928-117">Die Intune-Unternehmensportal-App kann von [Google Play](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal) heruntergeladen werden und ist auf dem Android-Gerät verfügbar.</span><span class="sxs-lookup"><span data-stu-id="16928-117">Intune Company Portal app can be downloaded from [Google Play](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal) and is available on the Android device.</span></span>

        -   <span data-ttu-id="16928-118">Darüber hinaus können Geräte [](https://docs.microsoft.com/mem/intune/user-help/enroll-device-android-company-portal) über die Intune-Unternehmensportal-App registriert werden, um Intune-Gerätekonformitätsrichtlinien zu erzwingen.</span><span class="sxs-lookup"><span data-stu-id="16928-118">Additionally, device(s) can be [enrolled](https://docs.microsoft.com/mem/intune/user-help/enroll-device-android-company-portal) via the Intune Company Portal app to enforce Intune device compliance policies.</span></span> <span data-ttu-id="16928-119">Dies erfordert, dass dem Endbenutzer eine Microsoft Intune-Lizenz zugewiesen wird.</span><span class="sxs-lookup"><span data-stu-id="16928-119">This requires the end user to be assigned a Microsoft Intune license.</span></span>

    -   <span data-ttu-id="16928-120">Weitere Informationen zum Zuweisen von Lizenzen finden Sie unter [Zuweisen von Lizenzen zu Benutzern](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-groups-assign).</span><span class="sxs-lookup"><span data-stu-id="16928-120">For more information on how to assign licenses, see [Assign licenses to users](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-groups-assign).</span></span>
        

-   <span data-ttu-id="16928-121">**Für Administratoren**</span><span class="sxs-lookup"><span data-stu-id="16928-121">**For Administrators**</span></span>

    -   <span data-ttu-id="16928-122">Zugriff auf das Microsoft Defender Security Center-Portal.</span><span class="sxs-lookup"><span data-stu-id="16928-122">Access to the Microsoft Defender Security Center portal.</span></span>

        > [!NOTE]
        > <span data-ttu-id="16928-123">Microsoft Intune ist die einzige unterstützte Mobile Device Management (MDM)-Lösung für die Bereitstellung von Microsoft Defender for Endpoint für Android.</span><span class="sxs-lookup"><span data-stu-id="16928-123">Microsoft Intune is the only supported Mobile Device Management (MDM) solution for deploying Microsoft Defender for Endpoint for Android.</span></span> <span data-ttu-id="16928-124">Derzeit werden nur registrierte Geräte unterstützt, um Defender for Endpoint für Android-bezogene Gerätekonformitätsrichtlinien in Intune zu erzwingen.</span><span class="sxs-lookup"><span data-stu-id="16928-124">Currently only enrolled devices are supported for enforcing Defender for Endpoint for Android related device compliance policies in Intune.</span></span> 

    -   <span data-ttu-id="16928-125">Greifen [Sie auf Microsoft Endpoint Manager Admin Center zu,](https://go.microsoft.com/fwlink/?linkid=2109431)um die App für registrierte Benutzergruppen in Ihrer Organisation zu bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="16928-125">Access [Microsoft Endpoint Manager admin center](https://go.microsoft.com/fwlink/?linkid=2109431), to deploy the app to enrolled user groups in your organization.</span></span>

### <a name="system-requirements"></a><span data-ttu-id="16928-126">Systemanforderungen</span><span class="sxs-lookup"><span data-stu-id="16928-126">System Requirements</span></span>

-   <span data-ttu-id="16928-127">Android-Geräte mit Android 6.0 und höher.</span><span class="sxs-lookup"><span data-stu-id="16928-127">Android devices running Android 6.0 and above.</span></span>
-   <span data-ttu-id="16928-128">Die Intune-Unternehmensportal-App wird von [Google Play heruntergeladen und](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal) installiert.</span><span class="sxs-lookup"><span data-stu-id="16928-128">Intune Company Portal app is downloaded from [Google Play](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal) and installed.</span></span> <span data-ttu-id="16928-129">Die Geräteregistrierung ist erforderlich, damit Intune-Gerätekonformitätsrichtlinien erzwungen werden.</span><span class="sxs-lookup"><span data-stu-id="16928-129">Device enrollment is required for Intune device compliance policies to be enforced.</span></span>

### <a name="installation-instructions"></a><span data-ttu-id="16928-130">Installationsanweisungen</span><span class="sxs-lookup"><span data-stu-id="16928-130">Installation instructions</span></span>

<span data-ttu-id="16928-131">Microsoft Defender für Endpoint für Android unterstützt die Installation auf beiden Modi von registrierten Geräten – dem älteren Geräteadministrator und dem Android Enterprise-Modus.</span><span class="sxs-lookup"><span data-stu-id="16928-131">Microsoft Defender for Endpoint for Android supports installation on both modes of enrolled devices - the legacy Device Administrator and Android Enterprise modes.</span></span>
<span data-ttu-id="16928-132">**Derzeit werden persönliche Geräte mit Geschäftsprofil und unternehmenseigenen, vollständig verwalteten Benutzergeräten in Android Enterprise unterstützt. Unterstützung für andere Android Enterprise-Modi wird angekündigt, sobald sie bereit sind.**</span><span class="sxs-lookup"><span data-stu-id="16928-132">**Currently, Personally-owned devices with work profile and Corporate-owned fully managed user device enrolments are supported in Android Enterprise. Support for other Android Enterprise modes will be announced when ready.**</span></span>

<span data-ttu-id="16928-133">Die Bereitstellung von Microsoft Defender for Endpoint für Android erfolgt über Microsoft Intune (MDM).</span><span class="sxs-lookup"><span data-stu-id="16928-133">Deployment of Microsoft Defender for Endpoint for Android is via Microsoft Intune (MDM).</span></span>
<span data-ttu-id="16928-134">Weitere Informationen finden Sie unter [Deploy Microsoft Defender for Endpoint for Android with Microsoft Intune](android-intune.md).</span><span class="sxs-lookup"><span data-stu-id="16928-134">For more information, see [Deploy Microsoft Defender for Endpoint for Android with Microsoft Intune](android-intune.md).</span></span>


> [!NOTE]
> <span data-ttu-id="16928-135">**Microsoft Defender für Endpoint für Android ist jetzt auf [Google Play](https://play.google.com/store/apps/details?id=com.microsoft.scmx) verfügbar.**</span><span class="sxs-lookup"><span data-stu-id="16928-135">**Microsoft Defender for Endpoint for Android is available on [Google Play](https://play.google.com/store/apps/details?id=com.microsoft.scmx) now.**</span></span> <br> <span data-ttu-id="16928-136">Sie können von Intune aus eine Verbindung mit Google Play herstellen, um Microsoft Defender for Endpoint-App über geräteadministrator- und Android Enterprise-Entrollmentmodi bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="16928-136">You can connect to Google Play from Intune to deploy Microsoft Defender for Endpoint app, across Device Administrator and Android Enterprise entrollment modes.</span></span> 

## <a name="how-to-configure-microsoft-defender-for-endpoint-for-android"></a><span data-ttu-id="16928-137">Konfigurieren von Microsoft Defender for Endpoint für Android</span><span class="sxs-lookup"><span data-stu-id="16928-137">How to Configure Microsoft Defender for Endpoint for Android</span></span>

<span data-ttu-id="16928-138">Anleitungen zum Konfigurieren von Microsoft Defender for Endpoint für Android-Features finden Sie unter [Configure Microsoft Defender for Endpoint for Android features](android-configure.md).</span><span class="sxs-lookup"><span data-stu-id="16928-138">Guidance on how to configure Microsoft Defender for Endpoint for Android features is available in [Configure Microsoft Defender for Endpoint for Android features](android-configure.md).</span></span>



## <a name="related-topics"></a><span data-ttu-id="16928-139">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="16928-139">Related topics</span></span>
- [<span data-ttu-id="16928-140">Bereitstellen von Microsoft Defender for Endpoint für mit Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="16928-140">Deploy Microsoft Defender for Endpoint for with Microsoft Intune</span></span>](android-intune.md)
- [<span data-ttu-id="16928-141">Konfigurieren von Microsoft Defender for Endpoint für Android-Features</span><span class="sxs-lookup"><span data-stu-id="16928-141">Configure Microsoft Defender for Endpoint for Android features</span></span>](android-configure.md)

