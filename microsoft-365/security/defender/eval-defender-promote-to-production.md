---
title: Bewerben Sie Ihre Microsoft 365 Defender Evaluierungsumgebung für die Produktion, Microsoft 365 Defender Evaluierung, testen Sie eine Evaluierung, behalten Sie eine Evaluierung, produktionsbezogene Evaluierung
description: Verwenden Sie diesen Artikel, um Ihre Ausweichen von MDI, MDO, MDE und MCAS in Ihre Liveumgebung in Microsoft 365 Defender oder M365D zu bewerben.
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: bcarter
author: brendacarter
f1.keywords:
- NOCSH
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-overview
- m365solution-evalutatemtp
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: b67f0f493c97b900fa08b10e3eb7a5967560dcfd
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/15/2021
ms.locfileid: "53458341"
---
# <a name="promote-your-microsoft-365-defender-evaluation-environment-to-production"></a><span data-ttu-id="a5409-103">Bewerben Ihrer Microsoft 365 Defender Evaluierungsumgebung für die Produktion</span><span class="sxs-lookup"><span data-stu-id="a5409-103">Promote your Microsoft 365 Defender evaluation environment to production</span></span>

<span data-ttu-id="a5409-104">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="a5409-104">**Applies to:**</span></span>
- <span data-ttu-id="a5409-105">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a5409-105">Microsoft 365 Defender</span></span>

<span data-ttu-id="a5409-106">Um Ihre Microsoft 365 Defender Evaluierungsumgebung für die Produktion zu bewerben, erwerben Sie zuerst die erforderliche Lizenz.</span><span class="sxs-lookup"><span data-stu-id="a5409-106">To promote your Microsoft 365 Defender evaluation environment to production, first purchase the necessary license.</span></span> <span data-ttu-id="a5409-107">Führen Sie die Schritte unter [Erstellen der eval-Umgebung](eval-create-eval-environment.md) aus, und erwerben Sie die Office 365 E5-Lizenz (anstatt die kostenlose Testversion starten zu wählen).</span><span class="sxs-lookup"><span data-stu-id="a5409-107">Follow the steps in [Create the eval environment](eval-create-eval-environment.md) and purchase the Office 365 E5 license (instead of selecting Start free trial).</span></span>

<span data-ttu-id="a5409-108">Schließen Sie als Nächstes alle zusätzlichen Konfigurationen ab, und erweitern Sie Ihre Pilotgruppen, bis diese die vollständige Produktion erreicht haben.</span><span class="sxs-lookup"><span data-stu-id="a5409-108">Next, complete any additional configuration and expand your pilot groups until these have reached full production.</span></span> 

## <a name="microsoft-defender-for-identity"></a><span data-ttu-id="a5409-109">Microsoft Defender for Identity</span><span class="sxs-lookup"><span data-stu-id="a5409-109">Microsoft Defender for Identity</span></span>
<span data-ttu-id="a5409-110">Defender for Identity erfordert keine zusätzliche Konfiguration.</span><span class="sxs-lookup"><span data-stu-id="a5409-110">Defender for Identity doesn't require any additional configuration.</span></span> <span data-ttu-id="a5409-111">Stellen Sie einfach sicher, dass Sie die erforderlichen Lizenzen erworben und den Sensor auf allen Active Directory-Domänencontrollern und Active Directory-Verbunddiensten (AD FS)-Servern installiert haben.</span><span class="sxs-lookup"><span data-stu-id="a5409-111">Just make sure you've purchased the necessary licenses and installed the sensor on all of your Active Directory domain controllers and Active Directory Federation Services (AD FS) servers.</span></span> 

## <a name="microsoft-defender-for-office-365"></a><span data-ttu-id="a5409-112">Microsoft Defender für Office 365</span><span class="sxs-lookup"><span data-stu-id="a5409-112">Microsoft Defender for Office 365</span></span>
<span data-ttu-id="a5409-113">Nachdem MDO erfolgreich ausgewertet oder pilotiert wurde, kann es in Ihre gesamte Produktionsumgebung übertragen werden.</span><span class="sxs-lookup"><span data-stu-id="a5409-113">After successfully evaluating or piloting MDO, it can be promoted to your entire production environment.</span></span>
1. <span data-ttu-id="a5409-114">Erwerben und bereitstellen Sie die erforderlichen Lizenzen, und weisen Sie sie Ihren Produktionsbenutzern zu.</span><span class="sxs-lookup"><span data-stu-id="a5409-114">Purchase and provision the necessary licenses and assign them to your production users.</span></span>
2. <span data-ttu-id="a5409-115">Führen Sie empfohlene Basisrichtlinienkonfigurationen (standard oder streng) für Ihre Produktions-E-Mail-Domäne oder bestimmte Benutzergruppen erneut aus.</span><span class="sxs-lookup"><span data-stu-id="a5409-115">Re-run recommended baseline policy configurations (either Standard or Strict) against your production email domain or specific groups of users.</span></span>
3. <span data-ttu-id="a5409-116">Optional können Sie benutzerdefinierte MDO-Richtlinien für Ihre Produktions-E-Mail-Domäne oder Benutzergruppen erstellen und konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="a5409-116">Optionally create and configure any custom MDO policies against your production email domain or groups of users.</span></span>  <span data-ttu-id="a5409-117">Denken Sie jedoch daran, dass alle zugewiesenen Basisrichtlinien immer Vorrang vor benutzerdefinierten Richtlinien haben.</span><span class="sxs-lookup"><span data-stu-id="a5409-117">However, remember that any assigned baseline policies will always take precedence over custom policies.</span></span>
4. <span data-ttu-id="a5409-118">Aktualisieren Sie den öffentlichen MX-Eintrag für Ihre Produktions-E-Mail-Domäne so, dass er direkt in EOP aufgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="a5409-118">Update the public MX record for your production email domain to resolve directly to EOP.</span></span>
5. <span data-ttu-id="a5409-119">Außerbetriebnahme aller SMTP-Gateways von Drittanbietern und Deaktivieren oder Löschen von EXO-Connectors, die diesem Relay zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="a5409-119">Decommission any third-party SMTP gateways and disable or delete any EXO connectors associated with this relay.</span></span>

## <a name="microsoft-defender-for-endpoint"></a><span data-ttu-id="a5409-120">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="a5409-120">Microsoft Defender for Endpoint</span></span>
<span data-ttu-id="a5409-121">Um die Evaluierungsumgebung von Microsoft Defender für Endpunkt von einem Pilotprojekt zur Produktion zu fördern, integrieren Sie einfach mehr Endpunkte mithilfe der [unterstützten Tools und Methoden](/defender-endpoint/onboard-configure)in den Dienst.</span><span class="sxs-lookup"><span data-stu-id="a5409-121">To promote Microsoft Defender for Endpoint evaluation environment from a pilot to production, simply onboard more endpoints to the service using any of the [supported tools and methods](/defender-endpoint/onboard-configure).</span></span>

<span data-ttu-id="a5409-122">Verwenden Sie die folgenden allgemeinen Richtlinien, um weitere Geräte in Microsoft Defender für Endpunkt zu integrieren.</span><span class="sxs-lookup"><span data-stu-id="a5409-122">Use the following general guidelines to onboard more devices to Microsoft Defender for Endpoint.</span></span> 

1. <span data-ttu-id="a5409-123">Stellen Sie sicher, dass das Gerät die [Mindestanforderungen](/defender-endpoint/minimum-requirements)erfüllt.</span><span class="sxs-lookup"><span data-stu-id="a5409-123">Verify that the device fulfills the [minimum requirements](/defender-endpoint/minimum-requirements).</span></span>
2. <span data-ttu-id="a5409-124">Führen Sie je nach Gerät die Konfigurationsschritte aus, die im Onboarding-Abschnitt des Defender für Endpunkt-Portals angegeben sind.</span><span class="sxs-lookup"><span data-stu-id="a5409-124">Depending on the device, follow the configuration steps provided in the onboarding section of the Defender for Endpoint portal.</span></span>
3. <span data-ttu-id="a5409-125">Verwenden Sie das entsprechende Verwaltungstool und die entsprechende Bereitstellungsmethode für Ihre Geräte.</span><span class="sxs-lookup"><span data-stu-id="a5409-125">Use the appropriate management tool and deployment method for your devices.</span></span>
4.  <span data-ttu-id="a5409-126">Führen Sie einen Erkennungstest aus, um sicherzustellen, dass die Geräte ordnungsgemäß integriert sind, und melden Sie sich an den Dienst.</span><span class="sxs-lookup"><span data-stu-id="a5409-126">Run a detection test to verify that the devices are properly onboarded and reporting to the service.</span></span>

## <a name="microsoft-cloud-app-security"></a><span data-ttu-id="a5409-127">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="a5409-127">Microsoft Cloud App Security</span></span>
<span data-ttu-id="a5409-128">Microsoft Cloud App Security erfordert keine zusätzliche Konfiguration.</span><span class="sxs-lookup"><span data-stu-id="a5409-128">Microsoft Cloud App Security doesn't require any additional configuration.</span></span> <span data-ttu-id="a5409-129">Stellen Sie einfach sicher, dass Sie die erforderlichen Lizenzen erworben haben.</span><span class="sxs-lookup"><span data-stu-id="a5409-129">Just make sure you've purchased the necessary licenses.</span></span> <span data-ttu-id="a5409-130">Wenn Sie die Bereitstellung auf bestimmte Benutzergruppen beschränkt haben, erweitern Sie den Umfang dieser Gruppen, bis Sie die Produktionsskala erreichen.</span><span class="sxs-lookup"><span data-stu-id="a5409-130">If you've scoped the deployment to certain user groups, increase the scope of these groups until you reach production scale.</span></span> 

