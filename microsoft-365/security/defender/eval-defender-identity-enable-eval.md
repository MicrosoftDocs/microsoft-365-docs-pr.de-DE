---
title: Aktivieren sie die Evaluierungsumgebung für Microsoft Defender for Identity, richten Sie die MDI-Instanz ein, installieren und konfigurieren Sie den MDI-Sensor, und lassen Sie den MDI-Sensor lokale Administratoren erkennen.
description: Richten Sie Microsoft Defender for Identity in Microsoft 365 Defender Testumgebung oder Pilotumgebung ein, indem Sie & Konfigurieren des Sensors installieren und lokale Administratoren auf anderen Computern ermitteln.
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
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
ms.openlocfilehash: f739c9897c9c43831cb4ed23cabaa1705c75d712
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/15/2021
ms.locfileid: "53458073"
---
# <a name="enable-the-evaluation-environment-for-microsoft-defender-for-identity"></a><span data-ttu-id="b3561-103">Aktivieren der Evaluierungsumgebung für Microsoft Defender for Identity</span><span class="sxs-lookup"><span data-stu-id="b3561-103">Enable the evaluation environment for Microsoft Defender for Identity</span></span>

<span data-ttu-id="b3561-104">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="b3561-104">**Applies to:**</span></span>
- <span data-ttu-id="b3561-105">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="b3561-105">Microsoft 365 Defender</span></span>

<span data-ttu-id="b3561-106">Dieser Artikel ist [Schritt 2 von 2](eval-defender-identity-overview.md) beim Einrichten der Evaluierungsumgebung für Microsoft Defender for Identity.</span><span class="sxs-lookup"><span data-stu-id="b3561-106">This article is [Step 2 of 2](eval-defender-identity-overview.md) in the process of setting up the evaluation environment for Microsoft Defender for Identity.</span></span> <span data-ttu-id="b3561-107">Weitere Informationen zu diesem Prozess finden Sie im [Übersichtsartikel.](eval-defender-identity-overview.md)</span><span class="sxs-lookup"><span data-stu-id="b3561-107">For more information about this process, see the [overview article](eval-defender-identity-overview.md).</span></span>

<span data-ttu-id="b3561-108">Führen Sie die folgenden Schritte aus, um Ihre Microsoft Defender for Identity-Umgebung einzurichten.</span><span class="sxs-lookup"><span data-stu-id="b3561-108">Use the following steps to set up your Microsoft Defender for Identity environment.</span></span> 

![Schritte zum Aktivieren von Microsoft Defender for Identity in der Microsoft Defender-Evaluierungsumgebung](../../media/defender/m365-defender-identity-eval-enable-steps.png)

- [<span data-ttu-id="b3561-110">Schritt 1. Einrichten der Defender for Identity-Instanz</span><span class="sxs-lookup"><span data-stu-id="b3561-110">Step 1. Set up the Defender for Identity Instance</span></span>](#step-1-set-up-the-defender-for-identity-instance)
- [<span data-ttu-id="b3561-111">Schritt 2. Installieren und Konfigurieren des Sensors</span><span class="sxs-lookup"><span data-stu-id="b3561-111">Step 2. Install and configure the sensor</span></span>](#step-2-install-and-configure-the-sensor)
- [<span data-ttu-id="b3561-112">Schritt 3. Konfigurieren von Ereignisprotokoll- und Proxyeinstellungen auf Computern mit dem Sensor</span><span class="sxs-lookup"><span data-stu-id="b3561-112">Step 3. Configure event log and proxy settings on machines with the sensor</span></span>](#step-3-configure-event-log-and-proxy-settings-on-machines-with-the-sensor)
- [<span data-ttu-id="b3561-113">Schritt 4. Zulassen, dass Defender for Identity lokale Administratoren auf anderen Computern identifiziert</span><span class="sxs-lookup"><span data-stu-id="b3561-113">Step 4. Allow Defender for Identity to identify local admins on other computers</span></span>](#step-4-allow-defender-for-identity-to-identify-local-admins-on-other-computers)

## <a name="step-1-set-up-the-defender-for-identity-instance"></a><span data-ttu-id="b3561-114">Schritt 1.</span><span class="sxs-lookup"><span data-stu-id="b3561-114">Step 1.</span></span> <span data-ttu-id="b3561-115">Einrichten der Defender for Identity-Instanz</span><span class="sxs-lookup"><span data-stu-id="b3561-115">Set up the Defender for Identity Instance</span></span>

<span data-ttu-id="b3561-116">Melden Sie sich beim Defender for Identity-Portal an, um Ihre Instanz zu erstellen, und verbinden Sie diese Instanz mit Ihrer Active Directory-Umgebung.</span><span class="sxs-lookup"><span data-stu-id="b3561-116">Sign in to the Defender for Identity portal to create your instance and then connect this instance to your Active Directory environment.</span></span> 

|  |<span data-ttu-id="b3561-117">Schritt</span><span class="sxs-lookup"><span data-stu-id="b3561-117">Step</span></span>     |<span data-ttu-id="b3561-118">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="b3561-118">More information</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="b3561-119">1</span><span class="sxs-lookup"><span data-stu-id="b3561-119">1</span></span>     | <span data-ttu-id="b3561-120">Erstellen der Defender for Identity-Instanz</span><span class="sxs-lookup"><span data-stu-id="b3561-120">Create the Defender for Identity instance</span></span>        | [<span data-ttu-id="b3561-121">Schnellstart: Erstellen Ihrer Microsoft Defender for Identity-Instanz</span><span class="sxs-lookup"><span data-stu-id="b3561-121">Quickstart: Create your Microsoft Defender for Identity instance</span></span>](/defender-for-identity/install-step1)        |
|<span data-ttu-id="b3561-122">2</span><span class="sxs-lookup"><span data-stu-id="b3561-122">2</span></span>     | <span data-ttu-id="b3561-123">Verbinden der Defender for Identity-Instanz zu Ihrer Active Directory-Gesamtstruktur</span><span class="sxs-lookup"><span data-stu-id="b3561-123">Connect the Defender for Identity instance to your Active Directory forest</span></span>   | [<span data-ttu-id="b3561-124">Schnellstart: Verbinden zu Ihrer Active Directory-Gesamtstruktur</span><span class="sxs-lookup"><span data-stu-id="b3561-124">Quickstart: Connect to your Active Directory Forest</span></span>](/defender-for-identity/install-step2)  |
| | |

## <a name="step-2-install-and-configure-the-sensor"></a><span data-ttu-id="b3561-125">Schritt 2.</span><span class="sxs-lookup"><span data-stu-id="b3561-125">Step 2.</span></span> <span data-ttu-id="b3561-126">Installieren und Konfigurieren des Sensors</span><span class="sxs-lookup"><span data-stu-id="b3561-126">Install and configure the sensor</span></span>

<span data-ttu-id="b3561-127">Laden Sie als Nächstes den Defender for Identity-Sensor auf den Domänencontrollern und AD FS-Servern in Ihrer lokalen Umgebung herunter, installieren und konfigurieren Sie diesen.</span><span class="sxs-lookup"><span data-stu-id="b3561-127">Next, download, install, and configure the Defender for Identity sensor on the domain controllers and AD FS servers in your on-premises environment.</span></span>

|  |<span data-ttu-id="b3561-128">Schritt</span><span class="sxs-lookup"><span data-stu-id="b3561-128">Step</span></span>     |<span data-ttu-id="b3561-129">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="b3561-129">More information</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="b3561-130">1</span><span class="sxs-lookup"><span data-stu-id="b3561-130">1</span></span>     | <span data-ttu-id="b3561-131">Ermitteln Sie, wie viele Microsoft Defender for Identity-Sensoren Sie benötigen.</span><span class="sxs-lookup"><span data-stu-id="b3561-131">Determine how many Microsoft Defender for Identity sensors you need.</span></span>        | [<span data-ttu-id="b3561-132">Planen der Kapazität für Microsoft Defender for Identity</span><span class="sxs-lookup"><span data-stu-id="b3561-132">Plan capacity for Microsoft Defender for Identity</span></span>](/defender-for-identity/capacity-planning)   |
|<span data-ttu-id="b3561-133">2</span><span class="sxs-lookup"><span data-stu-id="b3561-133">2</span></span>     | <span data-ttu-id="b3561-134">Herunterladen des Sensoreinrichtungspakets</span><span class="sxs-lookup"><span data-stu-id="b3561-134">Download the sensor setup package</span></span>  |  [<span data-ttu-id="b3561-135">Schnellstart: Herunterladen des Setuppakets für den Microsoft Defender for Identity-Sensor</span><span class="sxs-lookup"><span data-stu-id="b3561-135">Quickstart: Download the Microsoft Defender for Identity sensor setup package</span></span>](/defender-for-identity/install-step3)   |
|<span data-ttu-id="b3561-136">3</span><span class="sxs-lookup"><span data-stu-id="b3561-136">3</span></span>     | <span data-ttu-id="b3561-137">Installieren des Defender for Identity-Sensors</span><span class="sxs-lookup"><span data-stu-id="b3561-137">Install the Defender for Identity sensor</span></span>    |  [<span data-ttu-id="b3561-138">Schnellstart: Installieren des Microsoft Defender for Identity-Sensors</span><span class="sxs-lookup"><span data-stu-id="b3561-138">Quickstart: Install the Microsoft Defender for Identity sensor</span></span>](/defender-for-identity/install-step4)       |
|<span data-ttu-id="b3561-139">4 </span><span class="sxs-lookup"><span data-stu-id="b3561-139">4</span></span>     | <span data-ttu-id="b3561-140">Konfigurieren des Sensors</span><span class="sxs-lookup"><span data-stu-id="b3561-140">Configure the sensor</span></span>       |  [<span data-ttu-id="b3561-141">Konfigurieren von Microsoft Defender for Identity-Sensoreinstellungen </span><span class="sxs-lookup"><span data-stu-id="b3561-141">Configure Microsoft Defender for Identity sensor settings </span></span>](/defender-for-identity/install-step5)   |
|   |         |         |

## <a name="step-3-configure-event-log-and-proxy-settings-on-machines-with-the-sensor"></a><span data-ttu-id="b3561-142">Schritt 3:</span><span class="sxs-lookup"><span data-stu-id="b3561-142">Step 3.</span></span> <span data-ttu-id="b3561-143">Konfigurieren von Ereignisprotokoll- und Proxyeinstellungen auf Computern mit dem Sensor</span><span class="sxs-lookup"><span data-stu-id="b3561-143">Configure event log and proxy settings on machines with the sensor</span></span>

<span data-ttu-id="b3561-144">Konfigurieren Sie auf den Computern, auf denen Sie den Sensor installiert haben, Windows Ereignisprotokollsammlung und Internetproxyeinstellungen, um erkennungsfunktionen zu aktivieren und zu verbessern.</span><span class="sxs-lookup"><span data-stu-id="b3561-144">On the machines that you installed the sensor on, configure Windows event log collection and Internet proxy settings to enable and enhance detection capabilities.</span></span>

|  |<span data-ttu-id="b3561-145">Schritt</span><span class="sxs-lookup"><span data-stu-id="b3561-145">Step</span></span>     |<span data-ttu-id="b3561-146">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="b3561-146">More information</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="b3561-147">1</span><span class="sxs-lookup"><span data-stu-id="b3561-147">1</span></span>     | <span data-ttu-id="b3561-148">Konfigurieren Windows Ereignisprotokollsammlung</span><span class="sxs-lookup"><span data-stu-id="b3561-148">Configure Windows event log collection</span></span>         | [<span data-ttu-id="b3561-149">Konfigurieren Windows-Ereignissammlung</span><span class="sxs-lookup"><span data-stu-id="b3561-149">Configure Windows Event collection</span></span>](/defender-for-identity/configure-windows-event-collection)        |
|<span data-ttu-id="b3561-150">2</span><span class="sxs-lookup"><span data-stu-id="b3561-150">2</span></span>     | <span data-ttu-id="b3561-151">Konfigurieren von Internetproxyeinstellungen</span><span class="sxs-lookup"><span data-stu-id="b3561-151">Configure Internet proxy settings</span></span>        | [<span data-ttu-id="b3561-152">Konfigurieren von Endpunktproxy- und Internetkonnektivitätseinstellungen für Ihren Microsoft Defender for Identity Sensor</span><span class="sxs-lookup"><span data-stu-id="b3561-152">Configure endpoint proxy and Internet connectivity settings for your Microsoft Defender for Identity Sensor</span></span>](/defender-for-identity/configure-proxy)        |
|   |         |         |

## <a name="step-4-allow-defender-for-identity-to-identify-local-admins-on-other-computers"></a><span data-ttu-id="b3561-153">Schritt 4.</span><span class="sxs-lookup"><span data-stu-id="b3561-153">Step 4.</span></span> <span data-ttu-id="b3561-154">Zulassen, dass Defender for Identity lokale Administratoren auf anderen Computern identifiziert</span><span class="sxs-lookup"><span data-stu-id="b3561-154">Allow Defender for Identity to identify local admins on other computers</span></span>

<span data-ttu-id="b3561-155">Die Lateral Movement Path-Erkennung von Microsoft Defender for Identity basiert auf Abfragen, die lokale Administratoren auf bestimmten Computern identifizieren.</span><span class="sxs-lookup"><span data-stu-id="b3561-155">Microsoft Defender for Identity lateral movement path detection relies on queries that identify local admins on specific machines.</span></span> <span data-ttu-id="b3561-156">Diese Abfragen werden mit dem SAM-R-Protokoll unter Verwendung des Defender for Identity Service-Kontos ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="b3561-156">These queries are performed with the SAM-R protocol, using the Defender for Identity Service account.</span></span> 

<span data-ttu-id="b3561-157">Um sicherzustellen Windows Clients und Server Ihrem Defender for Identity-Konto die Ausführung von SAM-R gestatten, muss eine Änderung an der Gruppenrichtlinie vorgenommen werden, um das Defender for Identity-Dienstkonto zusätzlich zu den konfigurierten Konten hinzuzufügen, die in der Netzwerkzugriffsrichtlinie aufgeführt sind.</span><span class="sxs-lookup"><span data-stu-id="b3561-157">To ensure Windows clients and servers allow your Defender for Identity account to perform SAM-R, a modification to Group Policy must be made to add the Defender for Identity service account in addition to the configured accounts listed in the Network access policy.</span></span> <span data-ttu-id="b3561-158">Stellen Sie sicher, dass Gruppenrichtlinien auf alle Computer **außer Domänencontrollern** angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="b3561-158">Make sure to apply group policies to all computers **except domain controllers**.</span></span>

<span data-ttu-id="b3561-159">Anweisungen hierzu finden Sie unter [Konfigurieren von Microsoft Defender for Identity für Remoteaufrufe an SAM.](/defender-for-identity/install-step8-samr)</span><span class="sxs-lookup"><span data-stu-id="b3561-159">For instructions on how to do this, see [Configure Microsoft Defender for Identity to make remote calls to SAM](/defender-for-identity/install-step8-samr).</span></span> 

## <a name="next-steps"></a><span data-ttu-id="b3561-160">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="b3561-160">Next steps</span></span>

<span data-ttu-id="b3561-161">Schritt 3 von 3: Testen von [Microsoft Defender for Identity](eval-defender-identity-pilot.md)</span><span class="sxs-lookup"><span data-stu-id="b3561-161">Step 3 of 3: [Pilot Microsoft Defender for Identity](eval-defender-identity-pilot.md)</span></span>

<span data-ttu-id="b3561-162">Kehren Sie zur Übersicht für ["Auswerten von Microsoft Defender for Identity"](eval-defender-identity-overview.md) zurück.</span><span class="sxs-lookup"><span data-stu-id="b3561-162">Return to the overview for [Evaluate Microsoft Defender for Identity](eval-defender-identity-overview.md)</span></span>

<span data-ttu-id="b3561-163">Kehren Sie zur Übersicht für [Evaluierungs- und Pilot-Microsoft 365 Defender](eval-overview.md)</span><span class="sxs-lookup"><span data-stu-id="b3561-163">Return to the overview for [Evaluate and pilot Microsoft 365 Defender](eval-overview.md)</span></span>