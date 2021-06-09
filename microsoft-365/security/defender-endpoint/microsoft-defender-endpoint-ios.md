---
title: Microsoft Defender für Endpunkt für iOS
ms.reviewer: ''
description: Beschreibt, wie Microsoft Defender für Endpunkt unter iOS installiert und verwendet wird
keywords: Microsoft, Defender, Microsoft Defender für Endpunkt, IOS, Übersicht, Installation, bereitstellen, Deinstallation, Intune
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
ms.openlocfilehash: b4c2d586cd23a346db1bcebf891689ff648b639b
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2021
ms.locfileid: "52844706"
---
# <a name="microsoft-defender-for-endpoint-on-ios"></a><span data-ttu-id="51413-104">Microsoft Defender für Endpunkt für iOS</span><span class="sxs-lookup"><span data-stu-id="51413-104">Microsoft Defender for Endpoint on iOS</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="51413-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="51413-105">**Applies to:**</span></span>
- [<span data-ttu-id="51413-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="51413-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="51413-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="51413-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="51413-108">Möchten Sie Microsoft Defender für Endpunkt erleben?</span><span class="sxs-lookup"><span data-stu-id="51413-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="51413-109">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="51413-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="51413-110">**Microsoft Defender für Endpunkt unter iOS** bietet Schutz vor Phishing und unsicheren Netzwerkverbindungen von Websites, E-Mails und Apps.</span><span class="sxs-lookup"><span data-stu-id="51413-110">**Microsoft Defender for Endpoint on iOS** will offer protection against phishing and unsafe network connections from websites, emails, and apps.</span></span> <span data-ttu-id="51413-111">Alle Warnungen werden über einen einzelnen Fensterausschnitt im Microsoft Defender Security Center verfügbar sein.</span><span class="sxs-lookup"><span data-stu-id="51413-111">All alerts will be available through a single pane of glass in the Microsoft Defender Security Center.</span></span> <span data-ttu-id="51413-112">Das Portal bietet Sicherheitsteams eine zentrale Übersicht über Bedrohungen auf iOS-Geräten und anderen Plattformen.</span><span class="sxs-lookup"><span data-stu-id="51413-112">The portal gives security teams a centralized view of threats on iOS devices along with other platforms.</span></span>

> [!CAUTION]
> <span data-ttu-id="51413-113">Das Ausführen anderer Endpunktschutzprodukte von Drittanbietern zusammen mit Defender für Endpunkt unter iOS führt wahrscheinlich zu Leistungsproblemen und unvorhersehbaren Systemfehlern.</span><span class="sxs-lookup"><span data-stu-id="51413-113">Running other third-party endpoint protection products alongside Defender for Endpoint on iOS is likely to cause performance problems and unpredictable system errors.</span></span>

## <a name="pre-requisites"></a><span data-ttu-id="51413-114">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="51413-114">Pre-requisites</span></span>

<span data-ttu-id="51413-115">**Für Endbenutzer**</span><span class="sxs-lookup"><span data-stu-id="51413-115">**For End Users**</span></span>

- <span data-ttu-id="51413-116">Microsoft Defender für Endpunkt-Lizenz, die den Endbenutzern der App zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="51413-116">Microsoft Defender for Endpoint license assigned to the end user(s) of the app.</span></span> <span data-ttu-id="51413-117">Siehe [Microsoft Defender für Endpunkt-Lizenzierungsanforderungen.](/microsoft-365/security/defender-endpoint/minimum-requirements#licensing-requirements)</span><span class="sxs-lookup"><span data-stu-id="51413-117">See [Microsoft Defender for Endpoint licensing requirements](/microsoft-365/security/defender-endpoint/minimum-requirements#licensing-requirements).</span></span>

- <span data-ttu-id="51413-118">Geräte werden über die Intune-Unternehmensportal-App [registriert,](/mem/intune/user-help/enroll-your-device-in-intune-ios) um Intune-Gerätekompatibilitätsrichtlinien zu erzwingen.</span><span class="sxs-lookup"><span data-stu-id="51413-118">Device(s) are [enrolled](/mem/intune/user-help/enroll-your-device-in-intune-ios) via the Intune Company Portal app to enforce Intune device compliance policies.</span></span> <span data-ttu-id="51413-119">Dies erfordert, dass dem Endbenutzer eine Microsoft Intune Lizenz zugewiesen wird.</span><span class="sxs-lookup"><span data-stu-id="51413-119">This requires the end user to be assigned a Microsoft Intune license.</span></span>
    - <span data-ttu-id="51413-120">Intune-Unternehmensportal App kann aus der [Apple App Store](https://apps.apple.com/us/app/intune-company-portal/id719171358)heruntergeladen werden.</span><span class="sxs-lookup"><span data-stu-id="51413-120">Intune Company Portal app can be downloaded from the [Apple App Store](https://apps.apple.com/us/app/intune-company-portal/id719171358).</span></span>
    - <span data-ttu-id="51413-121">Beachten Sie, dass Apple das Umleiten von Benutzern zum Herunterladen anderer Apps aus dem App Store nicht zulässt. Daher muss dieser Schritt vom Benutzer vor dem Onboarding in die Microsoft Defender für Endpunkt-App ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="51413-121">Note that Apple does not allow redirecting users to download other apps from the app store and hence this step needs to be done by the user before onboarding to Microsoft Defender for Endpoint app.</span></span>

- <span data-ttu-id="51413-122">Weitere Informationen zum Zuweisen von Lizenzen finden Sie unter [Zuweisen von Lizenzen zu Benutzern.](/azure/active-directory/users-groups-roles/licensing-groups-assign)</span><span class="sxs-lookup"><span data-stu-id="51413-122">For more information on how to assign licenses, see [Assign licenses to users](/azure/active-directory/users-groups-roles/licensing-groups-assign).</span></span>

<span data-ttu-id="51413-123">**Für Administratoren**</span><span class="sxs-lookup"><span data-stu-id="51413-123">**For Administrators**</span></span>

- <span data-ttu-id="51413-124">Zugriff auf das Microsoft Defender Security Center-Portal.</span><span class="sxs-lookup"><span data-stu-id="51413-124">Access to the Microsoft Defender Security Center portal.</span></span>

    > [!NOTE]
    > <span data-ttu-id="51413-125">Microsoft Intune ist die einzige unterstützte Unified Endpoint Management (UEM)-Lösung zum Bereitstellen von Microsoft Defender für Endpunkt und Erzwingen von Defender für Endpunkt-bezogenen Gerätekompatibilitätsrichtlinien in Intune.</span><span class="sxs-lookup"><span data-stu-id="51413-125">Microsoft Intune is the only supported Unified Endpoint Management (UEM) solution for deploying Microsoft Defender for Endpoint and enforcing Defender for Endpoint related device compliance policies in Intune.</span></span>

- <span data-ttu-id="51413-126">Zugriff auf [Microsoft Endpoint Manager Admin Center,](https://go.microsoft.com/fwlink/?linkid=2109431)um die App für registrierte Benutzergruppen in Ihrer Organisation bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="51413-126">Access to [Microsoft Endpoint Manager admin center](https://go.microsoft.com/fwlink/?linkid=2109431), to deploy the app to enrolled user groups in your organization.</span></span>

<span data-ttu-id="51413-127">**Systemanforderungen**</span><span class="sxs-lookup"><span data-stu-id="51413-127">**System Requirements**</span></span>

- <span data-ttu-id="51413-128">iOS-Geräte mit iOS 11.0 und höher.</span><span class="sxs-lookup"><span data-stu-id="51413-128">iOS devices running iOS 11.0 and above.</span></span> <span data-ttu-id="51413-129">iPad Geräte werden ab Version 1.1.15010101 offiziell unterstützt.</span><span class="sxs-lookup"><span data-stu-id="51413-129">iPad devices are officially supported from version 1.1.15010101 onward.</span></span>

- <span data-ttu-id="51413-130">Das Gerät ist bei der [Intune-Unternehmensportal-App](https://apps.apple.com/us/app/intune-company-portal/id719171358)registriert.</span><span class="sxs-lookup"><span data-stu-id="51413-130">Device is enrolled with the [Intune Company Portal app](https://apps.apple.com/us/app/intune-company-portal/id719171358).</span></span>

## <a name="installation-instructions"></a><span data-ttu-id="51413-131">Installationsanweisungen</span><span class="sxs-lookup"><span data-stu-id="51413-131">Installation instructions</span></span>

<span data-ttu-id="51413-132">Die Bereitstellung von Microsoft Defender für Endpunkt unter iOS erfolgt über Microsoft Intune (MDM), und sowohl überwachte als auch nicht überwachte Geräte werden unterstützt.</span><span class="sxs-lookup"><span data-stu-id="51413-132">Deployment of Microsoft Defender for Endpoint on iOS is via Microsoft Intune (MDM) and both supervised and unsupervised devices are supported.</span></span> <span data-ttu-id="51413-133">Endbenutzer können die App auch direkt aus dem [Apple App Store](https://aka.ms/mdatpiosappstore)installieren.</span><span class="sxs-lookup"><span data-stu-id="51413-133">End-users can also directly install the app from the [Apple app store](https://aka.ms/mdatpiosappstore).</span></span>
<span data-ttu-id="51413-134">Weitere Informationen finden Sie unter [Bereitstellen von Microsoft Defender für Endpunkt unter iOS.](ios-install.md)</span><span class="sxs-lookup"><span data-stu-id="51413-134">For more information, see [Deploy Microsoft Defender for Endpoint on iOS](ios-install.md).</span></span>

## <a name="resources"></a><span data-ttu-id="51413-135">Ressourcen</span><span class="sxs-lookup"><span data-stu-id="51413-135">Resources</span></span>

- <span data-ttu-id="51413-136">Informieren Sie sich über bevorstehende Versionen, indem Sie die [Neuigkeiten in Microsoft Defender für Endpunkt unter iOS](ios-whatsnew.md) oder in unserem [Blog](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/bg-p/MicrosoftDefenderATPBlog/label-name/iOS)besuchen.</span><span class="sxs-lookup"><span data-stu-id="51413-136">Stay informed about upcoming releases by visiting [What's new in Microsoft Defender for Endpoint on iOS](ios-whatsnew.md) or our [blog](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/bg-p/MicrosoftDefenderATPBlog/label-name/iOS).</span></span>

- <span data-ttu-id="51413-137">Bereitstellen von Feedback über das In-App-Feedbacksystem oder über [das SecOps-Portal](https://securitycenter.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="51413-137">Provide feedback through in-app feedback system or through [SecOps portal](https://securitycenter.microsoft.com)</span></span>

## <a name="next-steps"></a><span data-ttu-id="51413-138">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="51413-138">Next steps</span></span>

- [<span data-ttu-id="51413-139">Bereitstellen von Microsoft Defender für Endpunkt unter iOS</span><span class="sxs-lookup"><span data-stu-id="51413-139">Deploy Microsoft Defender for Endpoint on iOS</span></span>](ios-install.md)
- [<span data-ttu-id="51413-140">Konfigurieren von Microsoft Defender für Endpunkt unter iOS-Features</span><span class="sxs-lookup"><span data-stu-id="51413-140">Configure Microsoft Defender for Endpoint on iOS features</span></span>](ios-configure-features.md)
