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
ms.openlocfilehash: cbe2fb39221bd9907a3d690503a392edb019d61b
ms.sourcegitcommit: 6749455c52b0f98a92f6fffbc2bb86caf3538bd8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/29/2021
ms.locfileid: "53194853"
---
# <a name="microsoft-defender-for-endpoint-on-ios"></a><span data-ttu-id="5e715-104">Microsoft Defender für Endpunkt für iOS</span><span class="sxs-lookup"><span data-stu-id="5e715-104">Microsoft Defender for Endpoint on iOS</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="5e715-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="5e715-105">**Applies to:**</span></span>
- [<span data-ttu-id="5e715-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="5e715-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="5e715-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="5e715-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="5e715-108">Möchten Sie Microsoft Defender für Endpunkt erleben?</span><span class="sxs-lookup"><span data-stu-id="5e715-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="5e715-109">Registrieren Sie sich für eine kostenlose Testversion</span><span class="sxs-lookup"><span data-stu-id="5e715-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="5e715-110">**Microsoft Defender für Endpunkt unter iOS** bietet Schutz vor Phishing und unsicheren Netzwerkverbindungen von Websites, E-Mails und Apps.</span><span class="sxs-lookup"><span data-stu-id="5e715-110">**Microsoft Defender for Endpoint on iOS** offers protection against phishing and unsafe network connections from websites, emails, and apps.</span></span> <span data-ttu-id="5e715-111">Alle Warnungen sind über einen einzelnen Ausschnitt im Microsoft Defender Security Center verfügbar.</span><span class="sxs-lookup"><span data-stu-id="5e715-111">All alerts will be available through a single pane of glass in the Microsoft Defender Security Center.</span></span> <span data-ttu-id="5e715-112">Das Portal bietet Sicherheitsteams eine zentrale Übersicht über Bedrohungen auf iOS-Geräten und anderen Plattformen.</span><span class="sxs-lookup"><span data-stu-id="5e715-112">The portal gives security teams a centralized view of threats on iOS devices along with other platforms.</span></span>

> [!CAUTION]
> <span data-ttu-id="5e715-113">Das Ausführen anderer Endpunktschutzprodukte von Drittanbietern zusammen mit Defender für Endpunkt unter iOS führt wahrscheinlich zu Leistungsproblemen und unvorhersehbaren Systemfehlern.</span><span class="sxs-lookup"><span data-stu-id="5e715-113">Running other third-party endpoint protection products alongside Defender for Endpoint on iOS is likely to cause performance problems and unpredictable system errors.</span></span>

## <a name="pre-requisites"></a><span data-ttu-id="5e715-114">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="5e715-114">Pre-requisites</span></span>

<span data-ttu-id="5e715-115">**Für Endbenutzer**</span><span class="sxs-lookup"><span data-stu-id="5e715-115">**For End Users**</span></span>

- <span data-ttu-id="5e715-116">Microsoft Defender für Endpunkt-Lizenz, die den Endbenutzern der App zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="5e715-116">Microsoft Defender for Endpoint license assigned to the end user(s) of the app.</span></span> <span data-ttu-id="5e715-117">Siehe [Microsoft Defender für Endpunkt-Lizenzierungsanforderungen.](/microsoft-365/security/defender-endpoint/minimum-requirements#licensing-requirements)</span><span class="sxs-lookup"><span data-stu-id="5e715-117">See [Microsoft Defender for Endpoint licensing requirements](/microsoft-365/security/defender-endpoint/minimum-requirements#licensing-requirements).</span></span>

- <span data-ttu-id="5e715-118">**Für registrierte Geräte:** Geräte werden über die Intune-Unternehmensportal-App [registriert,](/mem/intune/user-help/enroll-your-device-in-intune-ios) um Intune-Gerätecompliancerichtlinien zu erzwingen.</span><span class="sxs-lookup"><span data-stu-id="5e715-118">**For enrolled devices**: Device(s) are [enrolled](/mem/intune/user-help/enroll-your-device-in-intune-ios) via the Intune Company Portal app to enforce Intune device compliance policies.</span></span> <span data-ttu-id="5e715-119">Dies erfordert, dass dem Endbenutzer eine Microsoft Intune-Lizenz zugewiesen wird.</span><span class="sxs-lookup"><span data-stu-id="5e715-119">This requires the end user to be assigned a Microsoft Intune license.</span></span>
    - <span data-ttu-id="5e715-120">Intune-Unternehmensportal App kann aus der [Apple App Store](https://apps.apple.com/us/app/intune-company-portal/id719171358)heruntergeladen werden.</span><span class="sxs-lookup"><span data-stu-id="5e715-120">Intune Company Portal app can be downloaded from the [Apple App Store](https://apps.apple.com/us/app/intune-company-portal/id719171358).</span></span>
    - <span data-ttu-id="5e715-121">Beachten Sie, dass Apple das Umleiten von Benutzern zum Herunterladen anderer Apps aus dem App Store nicht zulässt. Daher muss dieser Schritt vom Benutzer vor dem Onboarding in die Microsoft Defender für Endpunkt-App ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="5e715-121">Note that Apple does not allow redirecting users to download other apps from the app store and hence this step needs to be done by the user before onboarding to Microsoft Defender for Endpoint app.</span></span>

- <span data-ttu-id="5e715-122">**Für nicht registrierte Geräte:** Geräte werden bei Azure Active Directory registriert.</span><span class="sxs-lookup"><span data-stu-id="5e715-122">**For unenrolled devices**: Device(s) are registered with Azure Active Directory.</span></span> <span data-ttu-id="5e715-123">Dazu muss der Endbenutzer über [Microsoft Authenticator App](https://apps.apple.com/app/microsoft-authenticator/id983156458)angemeldet sein.</span><span class="sxs-lookup"><span data-stu-id="5e715-123">This requires end user to be signed in through [Microsoft Authenticator app](https://apps.apple.com/app/microsoft-authenticator/id983156458).</span></span>

- <span data-ttu-id="5e715-124">Weitere Informationen zum Zuweisen von Lizenzen finden Sie unter [Zuweisen von Lizenzen zu Benutzern.](/azure/active-directory/users-groups-roles/licensing-groups-assign)</span><span class="sxs-lookup"><span data-stu-id="5e715-124">For more information on how to assign licenses, see [Assign licenses to users](/azure/active-directory/users-groups-roles/licensing-groups-assign).</span></span>

<span data-ttu-id="5e715-125">**Für Administratoren**</span><span class="sxs-lookup"><span data-stu-id="5e715-125">**For Administrators**</span></span>

- <span data-ttu-id="5e715-126">Zugriff auf das Microsoft Defender Security Center-Portal.</span><span class="sxs-lookup"><span data-stu-id="5e715-126">Access to the Microsoft Defender Security Center portal.</span></span>

- <span data-ttu-id="5e715-127">Zugriff auf [Microsoft Endpoint Manager Admin Center,](https://go.microsoft.com/fwlink/?linkid=2109431)um die App für registrierte Benutzergruppen in Ihrer Organisation bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="5e715-127">Access to [Microsoft Endpoint Manager admin center](https://go.microsoft.com/fwlink/?linkid=2109431), to deploy the app to enrolled user groups in your organization.</span></span>

    > [!NOTE]
    > <span data-ttu-id="5e715-128">Microsoft Intune ist die einzige unterstützte Unified Endpoint Management (UEM)-Lösung für die Bereitstellung von Microsoft Defender für Endpunkt und das Erzwingen von Defender für Endpunkt-bezogenen Gerätekompatibilitätsrichtlinien in Intune.</span><span class="sxs-lookup"><span data-stu-id="5e715-128">Microsoft Intune is the only supported Unified Endpoint Management (UEM) solution for deploying Microsoft Defender for Endpoint and enforcing Defender for Endpoint related device compliance policies in Intune.</span></span>

<span data-ttu-id="5e715-129">**Systemanforderungen**</span><span class="sxs-lookup"><span data-stu-id="5e715-129">**System Requirements**</span></span>

- <span data-ttu-id="5e715-130">iOS-Gerät mit iOS 11.0 und höher.</span><span class="sxs-lookup"><span data-stu-id="5e715-130">iOS device running iOS 11.0 and above.</span></span> <span data-ttu-id="5e715-131">iPad Geräte werden ab Version 1.1.15010101 offiziell unterstützt.</span><span class="sxs-lookup"><span data-stu-id="5e715-131">iPad devices are officially supported from version 1.1.15010101 onward.</span></span>

- <span data-ttu-id="5e715-132">Das Gerät ist entweder bei der [Intune-Unternehmensportal-App](https://apps.apple.com/us/app/intune-company-portal/id719171358) registriert oder über Microsoft Authenticator bei [Azure Active Directory](https://apps.apple.com/app/microsoft-authenticator/id983156458)registriert.</span><span class="sxs-lookup"><span data-stu-id="5e715-132">Device is either enrolled with the [Intune Company Portal app](https://apps.apple.com/us/app/intune-company-portal/id719171358) or registered with Azure Active Directory through [Microsoft Authenticator](https://apps.apple.com/app/microsoft-authenticator/id983156458).</span></span>

## <a name="installation-instructions"></a><span data-ttu-id="5e715-133">Installationsanweisungen</span><span class="sxs-lookup"><span data-stu-id="5e715-133">Installation instructions</span></span>

<span data-ttu-id="5e715-134">Die Bereitstellung von Microsoft Defender für Endpunkt unter iOS kann über Microsoft Endpoint Manager (MEM) erfolgen, und sowohl überwachte als auch nicht überwachte Geräte werden unterstützt.</span><span class="sxs-lookup"><span data-stu-id="5e715-134">Deployment of Microsoft Defender for Endpoint on iOS can be done via Microsoft Endpoint Manager (MEM) and both supervised and unsupervised devices are supported.</span></span> <span data-ttu-id="5e715-135">Endbenutzer können die App auch direkt aus dem [Apple App Store](https://aka.ms/mdatpiosappstore)installieren.</span><span class="sxs-lookup"><span data-stu-id="5e715-135">End-users can also directly install the app from the [Apple app store](https://aka.ms/mdatpiosappstore).</span></span>
<span data-ttu-id="5e715-136">Weitere Informationen finden Sie unter [Bereitstellen von Microsoft Defender für Endpunkt unter iOS.](ios-install.md)</span><span class="sxs-lookup"><span data-stu-id="5e715-136">For more information, see [Deploy Microsoft Defender for Endpoint on iOS](ios-install.md).</span></span>

## <a name="resources"></a><span data-ttu-id="5e715-137">Ressourcen</span><span class="sxs-lookup"><span data-stu-id="5e715-137">Resources</span></span>

- <span data-ttu-id="5e715-138">Informieren Sie sich über bevorstehende Versionen, indem Sie die [Neuigkeiten in Microsoft Defender für Endpunkt unter iOS](ios-whatsnew.md) oder in unserem [Blog](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/bg-p/MicrosoftDefenderATPBlog/label-name/iOS)besuchen.</span><span class="sxs-lookup"><span data-stu-id="5e715-138">Stay informed about upcoming releases by visiting [What's new in Microsoft Defender for Endpoint on iOS](ios-whatsnew.md) or our [blog](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/bg-p/MicrosoftDefenderATPBlog/label-name/iOS).</span></span>

- <span data-ttu-id="5e715-139">Bereitstellen von Feedback über das In-App-Feedbacksystem oder über [das SecOps-Portal](https://securitycenter.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="5e715-139">Provide feedback through in-app feedback system or through [SecOps portal](https://securitycenter.microsoft.com)</span></span>

## <a name="next-steps"></a><span data-ttu-id="5e715-140">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="5e715-140">Next steps</span></span>

- [<span data-ttu-id="5e715-141">Bereitstellen von Microsoft Defender für Endpunkt unter iOS</span><span class="sxs-lookup"><span data-stu-id="5e715-141">Deploy Microsoft Defender for Endpoint on iOS</span></span>](ios-install.md)
- [<span data-ttu-id="5e715-142">Konfigurieren von Microsoft Defender für Endpunkt unter iOS-Features</span><span class="sxs-lookup"><span data-stu-id="5e715-142">Configure Microsoft Defender for Endpoint on iOS features</span></span>](ios-configure-features.md)
