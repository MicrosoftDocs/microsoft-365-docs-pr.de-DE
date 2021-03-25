---
title: Übersicht über Microsoft Defender ATP für iOS
ms.reviewer: ''
description: Beschreibt die Installation und Verwendung von Microsoft Defender ATP für iOS
keywords: microsoft, defender, atp, ios, overview, installation, deploy, deinstallation, intune
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
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 72c3cfd51e472bbbda61f0084e131c4298633193
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/24/2021
ms.locfileid: "51186989"
---
# <a name="microsoft-defender-for-endpoint-for-ios"></a><span data-ttu-id="e2665-104">Microsoft Defender für Endpunkt für iOS</span><span class="sxs-lookup"><span data-stu-id="e2665-104">Microsoft Defender for Endpoint for iOS</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="e2665-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="e2665-105">**Applies to:**</span></span>
- [<span data-ttu-id="e2665-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="e2665-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="e2665-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e2665-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="e2665-108">Möchten Sie Microsoft Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="e2665-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="e2665-109">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="e2665-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="e2665-110">**Microsoft Defender for Endpoint für iOS** bietet Schutz vor Phishing und unsicheren Netzwerkverbindungen von Websites, E-Mails und Apps.</span><span class="sxs-lookup"><span data-stu-id="e2665-110">**Microsoft Defender for Endpoint for iOS** will offer protection against phishing and unsafe network connections from websites, emails, and apps.</span></span> <span data-ttu-id="e2665-111">Alle Warnungen sind über einen einzelnen Fensterausschnitt im Microsoft Defender Security Center verfügbar.</span><span class="sxs-lookup"><span data-stu-id="e2665-111">All alerts will be available through a single pane of glass in the Microsoft Defender Security Center.</span></span> <span data-ttu-id="e2665-112">Das Portal bietet Sicherheitsteams eine zentrale Ansicht von Bedrohungen auf iOS-Geräten und anderen Plattformen.</span><span class="sxs-lookup"><span data-stu-id="e2665-112">The portal gives security teams a centralized view of threats on iOS devices along with other platforms.</span></span>

> [!CAUTION]
> <span data-ttu-id="e2665-113">Das Ausführen anderer Endpunktschutzprodukte von Drittanbietern zusammen mit Defender for Endpoint für iOS verursacht wahrscheinlich Leistungsprobleme und unvorhersehbare Systemfehler.</span><span class="sxs-lookup"><span data-stu-id="e2665-113">Running other third-party endpoint protection products alongside Defender for Endpoint for iOS is likely to cause performance problems and unpredictable system errors.</span></span>

## <a name="pre-requisites"></a><span data-ttu-id="e2665-114">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="e2665-114">Pre-requisites</span></span>

<span data-ttu-id="e2665-115">**Für Endbenutzer**</span><span class="sxs-lookup"><span data-stu-id="e2665-115">**For End Users**</span></span>

- <span data-ttu-id="e2665-116">Microsoft Defender for Endpoint-Lizenz, die den Endbenutzern der App zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="e2665-116">Microsoft Defender for Endpoint license assigned to the end user(s) of the app.</span></span> <span data-ttu-id="e2665-117">Weitere Informationen [finden Sie unter Microsoft Defender for Endpoint licensing requirements](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/minimum-requirements#licensing-requirements).</span><span class="sxs-lookup"><span data-stu-id="e2665-117">See [Microsoft Defender for Endpoint licensing requirements](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/minimum-requirements#licensing-requirements).</span></span>

- <span data-ttu-id="e2665-118">Geräte werden über [](https://docs.microsoft.com/mem/intune/user-help/enroll-your-device-in-intune-ios) die Intune-Unternehmensportal-App registriert, um Intune-Gerätekonformitätsrichtlinien zu erzwingen.</span><span class="sxs-lookup"><span data-stu-id="e2665-118">Device(s) are [enrolled](https://docs.microsoft.com/mem/intune/user-help/enroll-your-device-in-intune-ios) via the Intune Company Portal app to enforce Intune device compliance policies.</span></span> <span data-ttu-id="e2665-119">Dies erfordert, dass dem Endbenutzer eine Microsoft Intune-Lizenz zugewiesen wird.</span><span class="sxs-lookup"><span data-stu-id="e2665-119">This requires the end user to be assigned a Microsoft Intune license.</span></span>
    - <span data-ttu-id="e2665-120">Die Intune-Unternehmensportal-App kann aus dem [Apple App Store heruntergeladen werden.](https://apps.apple.com/us/app/intune-company-portal/id719171358)</span><span class="sxs-lookup"><span data-stu-id="e2665-120">Intune Company Portal app can be downloaded from the [Apple App Store](https://apps.apple.com/us/app/intune-company-portal/id719171358).</span></span>
    - <span data-ttu-id="e2665-121">Beachten Sie, dass Apple es Benutzern nicht erlaubt, andere Apps aus dem App Store herunterzuladen. Daher muss dieser Schritt vom Benutzer vor dem Onboarding in die Microsoft Defender for Endpoint-App durchgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="e2665-121">Note that Apple does not allow redirecting users to download other apps from the app store and hence this step needs to be done by the user before onboarding to Microsoft Defender for Endpoint app.</span></span>

- <span data-ttu-id="e2665-122">Weitere Informationen zum Zuweisen von Lizenzen finden Sie unter [Zuweisen von Lizenzen zu Benutzern](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-groups-assign).</span><span class="sxs-lookup"><span data-stu-id="e2665-122">For more information on how to assign licenses, see [Assign licenses to users](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-groups-assign).</span></span>

<span data-ttu-id="e2665-123">**Für Administratoren**</span><span class="sxs-lookup"><span data-stu-id="e2665-123">**For Administrators**</span></span>

- <span data-ttu-id="e2665-124">Zugriff auf das Microsoft Defender Security Center-Portal.</span><span class="sxs-lookup"><span data-stu-id="e2665-124">Access to the Microsoft Defender Security Center portal.</span></span>

    > [!NOTE]
    > <span data-ttu-id="e2665-125">Microsoft Intune ist die einzige unterstützte Mobile Device Management (MDM)-Lösung für die Bereitstellung von Microsoft Defender for Endpoint für iOS.</span><span class="sxs-lookup"><span data-stu-id="e2665-125">Microsoft Intune is the only supported Mobile Device Management (MDM) solution for deploying Microsoft Defender for Endpoint for iOS.</span></span> <span data-ttu-id="e2665-126">Derzeit werden nur registrierte Geräte zum Erzwingen von Defender for Endpoint für iOS-bezogene Geräte-Compliance-Richtlinien in Intune unterstützt.</span><span class="sxs-lookup"><span data-stu-id="e2665-126">Currently only enrolled devices are supported for enforcing Defender for Endpoint for iOS related device compliance policies in Intune.</span></span>

- <span data-ttu-id="e2665-127">Zugriff auf [Microsoft Endpoint Manager Admin Center,](https://go.microsoft.com/fwlink/?linkid=2109431)um die App für registrierte Benutzergruppen in Ihrer Organisation zu bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="e2665-127">Access to [Microsoft Endpoint Manager admin center](https://go.microsoft.com/fwlink/?linkid=2109431), to deploy the app to enrolled user groups in your organization.</span></span>

<span data-ttu-id="e2665-128">**Systemanforderungen**</span><span class="sxs-lookup"><span data-stu-id="e2665-128">**System Requirements**</span></span>

- <span data-ttu-id="e2665-129">iOS-Geräte mit iOS 11.0 und höher.</span><span class="sxs-lookup"><span data-stu-id="e2665-129">iOS devices running iOS 11.0 and above.</span></span> <span data-ttu-id="e2665-130">iPad-Geräte werden ab Version 1.1.15010101 offiziell unterstützt.</span><span class="sxs-lookup"><span data-stu-id="e2665-130">iPad devices are officially supported from version 1.1.15010101 onward.</span></span>

- <span data-ttu-id="e2665-131">Das Gerät wird bei der [Intune Company Portal-App registriert.](https://apps.apple.com/us/app/intune-company-portal/id719171358)</span><span class="sxs-lookup"><span data-stu-id="e2665-131">Device is enrolled with the [Intune Company Portal app](https://apps.apple.com/us/app/intune-company-portal/id719171358).</span></span>

> [!NOTE]
> <span data-ttu-id="e2665-132">**Microsoft Defender ATP (Microsoft Defender for Endpoint) für iOS ist jetzt im [Apple App Store verfügbar.](https://aka.ms/mdatpiosappstore)**</span><span class="sxs-lookup"><span data-stu-id="e2665-132">**Microsoft Defender ATP (Microsoft Defender for Endpoint) for iOS is now available on [Apple App Store](https://aka.ms/mdatpiosappstore).**</span></span>

## <a name="installation-instructions"></a><span data-ttu-id="e2665-133">Installationsanweisungen</span><span class="sxs-lookup"><span data-stu-id="e2665-133">Installation instructions</span></span>

<span data-ttu-id="e2665-134">Die Bereitstellung von Microsoft Defender for Endpoint für iOS erfolgt über Microsoft Intune (MDM), und überwachte und nicht überwachte Geräte werden unterstützt.</span><span class="sxs-lookup"><span data-stu-id="e2665-134">Deployment of Microsoft Defender for Endpoint for iOS is via Microsoft Intune (MDM) and both supervised and unsupervised devices are supported.</span></span>
<span data-ttu-id="e2665-135">Weitere Informationen finden Sie unter [Deploy Microsoft Defender for Endpoint for iOS](ios-install.md).</span><span class="sxs-lookup"><span data-stu-id="e2665-135">For more information, see [Deploy Microsoft Defender for Endpoint for iOS](ios-install.md).</span></span>

## <a name="resources"></a><span data-ttu-id="e2665-136">Ressourcen</span><span class="sxs-lookup"><span data-stu-id="e2665-136">Resources</span></span>

- <span data-ttu-id="e2665-137">Informieren Sie sich über bevorstehende Versionen, indem Sie unseren [Blog besuchen.](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/bg-p/MicrosoftDefenderATPBlog/label-name/iOS)</span><span class="sxs-lookup"><span data-stu-id="e2665-137">Stay informed about upcoming releases by visiting our [blog](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/bg-p/MicrosoftDefenderATPBlog/label-name/iOS).</span></span>

- <span data-ttu-id="e2665-138">Bereitstellen von Feedback über das In-App-Feedbacksystem oder über [das SecOps-Portal](https://securitycenter.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="e2665-138">Provide feedback through in-app feedback system or through [SecOps portal](https://securitycenter.microsoft.com)</span></span>

## <a name="next-steps"></a><span data-ttu-id="e2665-139">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="e2665-139">Next steps</span></span>

- [<span data-ttu-id="e2665-140">Bereitstellen von Microsoft Defender for Endpoint für iOS</span><span class="sxs-lookup"><span data-stu-id="e2665-140">Deploy Microsoft Defender for Endpoint for iOS</span></span>](ios-install.md)
- [<span data-ttu-id="e2665-141">Konfigurieren von Microsoft Defender for Endpoint für iOS-Features</span><span class="sxs-lookup"><span data-stu-id="e2665-141">Configure Microsoft Defender for Endpoint for iOS features</span></span>](ios-configure-features.md)
