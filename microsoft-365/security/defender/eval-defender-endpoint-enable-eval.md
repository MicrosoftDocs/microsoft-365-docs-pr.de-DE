---
title: Aktivieren der Microsoft Defender für Endpunkt-Auswertung, Aktivieren der Auswertung für MDE
description: Aktivieren Sie Ihre Microsoft 365 Defender Testumgebung oder Pilotumgebung, einschließlich der Überprüfung des Lizenzstatus und des Onboardings von enpoints
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.date: 07/09/2021
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-overview
- m365solution-evalutatemtp
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: 48186dbfcde897022ac74dfad604c739a45ab68f
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/15/2021
ms.locfileid: "53458097"
---
# <a name="enable-microsoft-defender-for-endpoint-evaluation-environment"></a><span data-ttu-id="6e59b-103">Aktivieren der Evaluierungsumgebung von Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="6e59b-103">Enable Microsoft Defender for Endpoint evaluation environment</span></span>


<span data-ttu-id="6e59b-104">Dieser Artikel führt Sie durch die Schritte zum Einrichten der Evaluierungsumgebung für Microsoft Defender für Endpunkt unter Verwendung von Produktionsgeräten.</span><span class="sxs-lookup"><span data-stu-id="6e59b-104">This article will guide you through the steps on setting up the evaluation environment for Microsoft Defender for Endpoint using production devices.</span></span> 


>[!TIP]
><span data-ttu-id="6e59b-105">Microsoft Defender für Endpunkt enthält auch ein Produktbewertungslabor, in dem Sie vorkonfigurierte Geräte hinzufügen und Simulationen ausführen können, um die Funktionen der Plattform zu bewerten.</span><span class="sxs-lookup"><span data-stu-id="6e59b-105">Microsoft Defender for Endpoint also comes with an in-product evaluation lab where you can add pre-configured devices and run simulations to evaluate the capabilities of the platform.</span></span> <span data-ttu-id="6e59b-106">Die Übung bietet eine vereinfachte Einrichtungsoberfläche, die ihnen dabei helfen kann, den Nutzen von Microsoft Defender für Enpdoint schnell zu demonstrieren, einschließlich Anleitungen für viele Features wie erweiterte Suche und Bedrohungsanalyse.</span><span class="sxs-lookup"><span data-stu-id="6e59b-106">The lab comes with a simplified set-up experience that can help quickly demonstrate the value of Microsoft Defender for Enpdoint including guidance for many features like advanced hunting and threat analytics.</span></span> <span data-ttu-id="6e59b-107">Weitere Informationen finden Sie unter ["Auswerten von Funktionen".](/defender-endpoint/evaluation-lab.md)</span><span class="sxs-lookup"><span data-stu-id="6e59b-107">For more information, see [Evaluate capabilities](/defender-endpoint/evaluation-lab.md).</span></span> <br> <span data-ttu-id="6e59b-108">Der Hauptunterschied zwischen den Anleitungen in diesem Artikel und dem Evaluierungslabor besteht in der Evaluierungsumgebung, in der Produktionsgeräte verwendet werden, während das Evaluierungslabor Nicht-Produktionsgeräte verwendet.</span><span class="sxs-lookup"><span data-stu-id="6e59b-108">The main difference between the guidance provided in this article and the evaluation lab is the evaluation environment uses production devices whereas the evaluation lab uses non-production devices.</span></span> 

<span data-ttu-id="6e59b-109">Führen Sie die folgenden Schritte aus, um die Auswertung für Microsoft Defender für Endpunkt zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="6e59b-109">Use the following steps to enable the evaluation for Microsoft Defender for Endpoint.</span></span>

![Schritte zum Aktivieren von Microsoft Defender für Endpunkt in der Microsoft Defender-Evaluierungsumgebung](../../media/defender/m365-defender-endpoint-eval-enable-steps.png)

- [<span data-ttu-id="6e59b-111">Schritt 1. Überprüfen des Lizenzstatus</span><span class="sxs-lookup"><span data-stu-id="6e59b-111">Step 1. Check license state</span></span>](#step-1-check-license-state)
- [<span data-ttu-id="6e59b-112">Schritt 2. Integrieren von Endpunkten</span><span class="sxs-lookup"><span data-stu-id="6e59b-112">Step 2. Onboard endpoints</span></span>](#step-2-onboard-endpoints-using-any-of-the-supported-management-tools)


## <a name="step-1-check-license-state"></a><span data-ttu-id="6e59b-113">Schritt 1.</span><span class="sxs-lookup"><span data-stu-id="6e59b-113">Step 1.</span></span> <span data-ttu-id="6e59b-114">Überprüfen des Lizenzstatus</span><span class="sxs-lookup"><span data-stu-id="6e59b-114">Check license state</span></span>

<span data-ttu-id="6e59b-115">Zunächst müssen Sie den Lizenzstatus überprüfen, um sicherzustellen, dass er ordnungsgemäß bereitgestellt wurde.</span><span class="sxs-lookup"><span data-stu-id="6e59b-115">You'll first need to check the license state to verify that it was properly provisioned.</span></span> <span data-ttu-id="6e59b-116">Sie können dies über das Admin Center oder über das **Microsoft Azure-Portal** tun.</span><span class="sxs-lookup"><span data-stu-id="6e59b-116">You can do this through the admin center or through the **Microsoft Azure portal**.</span></span>


1. <span data-ttu-id="6e59b-117">Um Ihre Lizenzen anzuzeigen, wechseln Sie zum **Microsoft Azure-Portal,** und navigieren Sie zum [Lizenzabschnitt Microsoft Azure Portal.](https://portal.azure.com/#blade/Microsoft_AAD_IAM/LicensesMenuBlade/Products)</span><span class="sxs-lookup"><span data-stu-id="6e59b-117">To view your licenses, go to the **Microsoft Azure portal** and navigate to the [Microsoft Azure portal license section](https://portal.azure.com/#blade/Microsoft_AAD_IAM/LicensesMenuBlade/Products).</span></span>

   ![Abbildung der Azure-Lizenzierungsseite](../../media/defender/atp-licensing-azure-portal.png)

1. <span data-ttu-id="6e59b-119">Navigieren Sie alternativ im Admin Center zu **Abrechnungsabonnements.**  >  </span><span class="sxs-lookup"><span data-stu-id="6e59b-119">Alternately, in the admin center, navigate to **Billing** > **Subscriptions**.</span></span>

    <span data-ttu-id="6e59b-120">Auf dem Bildschirm werden alle bereitgestellten Lizenzen und deren aktueller **Status angezeigt.**</span><span class="sxs-lookup"><span data-stu-id="6e59b-120">On the screen, you'll see all the provisioned licenses and their current **Status**.</span></span>

    ![Abbildung der Abrechnungslizenzen](../../media/defender/atp-billing-subscriptions.png)

## <a name="step-2-onboard-endpoints-using-any-of-the-supported-management-tools"></a><span data-ttu-id="6e59b-122">Schritt 2.</span><span class="sxs-lookup"><span data-stu-id="6e59b-122">Step 2.</span></span> <span data-ttu-id="6e59b-123">Integrieren von Endpunkten mithilfe der unterstützten Verwaltungstools</span><span class="sxs-lookup"><span data-stu-id="6e59b-123">Onboard endpoints using any of the supported management tools</span></span>

<span data-ttu-id="6e59b-124">Nachdem Sie überprüft haben, ob der Lizenzstatus ordnungsgemäß bereitgestellt wurde, können Sie mit dem Onboarding von Geräten in den Dienst beginnen.</span><span class="sxs-lookup"><span data-stu-id="6e59b-124">After verifying that the license state has been provisioned properly, you can start onboarding devices to the service.</span></span> 

<span data-ttu-id="6e59b-125">Für die Bewertung von Microsoft Defender für Endpunkt empfehlen wir, ein paar Windows 10 Geräte auszuwählen, auf denen die Bewertung durchgeführt werden soll.</span><span class="sxs-lookup"><span data-stu-id="6e59b-125">For the purpose of evaluating Microsoft Defender for Endpoint, we recommend choosing a couple of Windows 10 devices to conduct the evaluation on.</span></span> 

<span data-ttu-id="6e59b-126">Das Thema ["Planbereitstellung"](../defender-endpoint/deployment-strategy.md) beschreibt die allgemeinen Schritte, die Sie zum Bereitstellen von Defender für Endpunkt ausführen müssen.</span><span class="sxs-lookup"><span data-stu-id="6e59b-126">The [Plan deployment](../defender-endpoint/deployment-strategy.md) topic outlines the general steps you need to take to deploy Defender for Endpoint.</span></span>  

<span data-ttu-id="6e59b-127">Sehen Sie sich dieses Video an, um einen schnellen Überblick über den Onboardingprozess zu erhalten und mehr über die verfügbaren Tools und Methoden zu erfahren.</span><span class="sxs-lookup"><span data-stu-id="6e59b-127">Watch this video for a quick overview of the onboarding process and learn about the available tools and methods.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4bGqr]

### <a name="onboarding-tool-options"></a><span data-ttu-id="6e59b-128">Onboarding-Tooloptionen</span><span class="sxs-lookup"><span data-stu-id="6e59b-128">Onboarding tool options</span></span>

<span data-ttu-id="6e59b-129">In der folgenden Tabelle sind die verfügbaren Tools aufgeführt, die auf dem Endpunkt basieren, den Sie integrieren müssen.</span><span class="sxs-lookup"><span data-stu-id="6e59b-129">The following table lists the available tools based on the endpoint that you need to onboard.</span></span>

<span data-ttu-id="6e59b-130">Endpunkt</span><span class="sxs-lookup"><span data-stu-id="6e59b-130">Endpoint</span></span> | <span data-ttu-id="6e59b-131">Tooloptionen</span><span class="sxs-lookup"><span data-stu-id="6e59b-131">Tool options</span></span>
:---|:---
<span data-ttu-id="6e59b-132">**Windows**</span><span class="sxs-lookup"><span data-stu-id="6e59b-132">**Windows**</span></span> | <span data-ttu-id="6e59b-133">[Lokales Skript (bis zu 10 Geräte),](../defender-endpoint/configure-endpoints-script.md) [Gruppenrichtlinie,](../defender-endpoint/configure-endpoints-gp.md) [Microsoft Endpoint Manager/Mobile Device Manager,](../defender-endpoint/configure-endpoints-mdm.md) [Microsoft Endpoint Configuration Manager,](../defender-endpoint/configure-endpoints-sccm.md) [VDI-Skripts,](../defender-endpoint/configure-endpoints-vdi.md) [Integration in Azure Defender](../defender-endpoint/configure-server-endpoints.md#integration-with-azure-defender)</span><span class="sxs-lookup"><span data-stu-id="6e59b-133">[Local script (up to 10 devices)](../defender-endpoint/configure-endpoints-script.md),  [Group Policy](../defender-endpoint/configure-endpoints-gp.md),  [Microsoft Endpoint Manager/ Mobile Device Manager](../defender-endpoint/configure-endpoints-mdm.md),  [Microsoft Endpoint Configuration Manager](../defender-endpoint/configure-endpoints-sccm.md),  [VDI scripts](../defender-endpoint/configure-endpoints-vdi.md),  [Integration with Azure Defender](../defender-endpoint/configure-server-endpoints.md#integration-with-azure-defender)</span></span>
<span data-ttu-id="6e59b-134">**macOS**</span><span class="sxs-lookup"><span data-stu-id="6e59b-134">**macOS**</span></span> | <span data-ttu-id="6e59b-135">[Lokale Skripts,](../defender-endpoint/mac-install-manually.md) [Microsoft Endpoint Manager,](../defender-endpoint/mac-install-with-intune.md) [JAMF-Pro,](../defender-endpoint/mac-install-with-jamf.md) [Verwaltung mobiler Geräte](../defender-endpoint/mac-install-with-other-mdm.md)</span><span class="sxs-lookup"><span data-stu-id="6e59b-135">[Local scripts](../defender-endpoint/mac-install-manually.md),  [Microsoft Endpoint Manager](../defender-endpoint/mac-install-with-intune.md),  [JAMF Pro](../defender-endpoint/mac-install-with-jamf.md),  [Mobile Device Management](../defender-endpoint/mac-install-with-other-mdm.md)</span></span>
<span data-ttu-id="6e59b-136">**Linux Server**</span><span class="sxs-lookup"><span data-stu-id="6e59b-136">**Linux Server**</span></span> | <span data-ttu-id="6e59b-137">[Lokales Skript,](../defender-endpoint/linux-install-manually.md)  [Überzeichen,](../defender-endpoint/linux-install-with-puppet.md)  [Ansible](../defender-endpoint/linux-install-with-ansible.md)</span><span class="sxs-lookup"><span data-stu-id="6e59b-137">[Local script](../defender-endpoint/linux-install-manually.md),  [Puppet](../defender-endpoint/linux-install-with-puppet.md),  [Ansible](../defender-endpoint/linux-install-with-ansible.md)</span></span>
<span data-ttu-id="6e59b-138">**iOS**</span><span class="sxs-lookup"><span data-stu-id="6e59b-138">**iOS**</span></span> | [<span data-ttu-id="6e59b-139">App-basiert</span><span class="sxs-lookup"><span data-stu-id="6e59b-139">App-based</span></span>](../defender-endpoint/ios-install.md)
<span data-ttu-id="6e59b-140">**Android**</span><span class="sxs-lookup"><span data-stu-id="6e59b-140">**Android**</span></span> | [<span data-ttu-id="6e59b-141">Microsoft Endpoint Manager</span><span class="sxs-lookup"><span data-stu-id="6e59b-141">Microsoft Endpoint Manager</span></span>](../defender-endpoint/android-intune.md)



## <a name="next-step"></a><span data-ttu-id="6e59b-142">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="6e59b-142">Next step</span></span>
[<span data-ttu-id="6e59b-143">Einrichten des Pilotprojekts für Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="6e59b-143">Setup the pilot for Microsoft Defender for Endpoint</span></span>](eval-defender-endpoint-pilot.md)
 
<span data-ttu-id="6e59b-144">Kehren Sie zur Übersicht für ["Auswerten von Microsoft Defender für Endpunkt"](eval-defender-endpoint-overview.md) zurück.</span><span class="sxs-lookup"><span data-stu-id="6e59b-144">Return to the overview for [Evaluate Microsoft Defender for Endpoint](eval-defender-endpoint-overview.md)</span></span>

<span data-ttu-id="6e59b-145">Kehren Sie zur Übersicht für [Evaluierungs- und Pilot-Microsoft 365 Defender](eval-overview.md)</span><span class="sxs-lookup"><span data-stu-id="6e59b-145">Return to the overview for [Evaluate and pilot Microsoft 365 Defender](eval-overview.md)</span></span>