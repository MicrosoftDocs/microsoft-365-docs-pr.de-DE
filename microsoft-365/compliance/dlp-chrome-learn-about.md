---
title: Erfahren Sie mehr über die Microsoft Compliance-Erweiterung
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: conceptual
f1_keywords:
- ms.o365.cc.DLPLandingPage
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- m365solution-mip
- m365initiative-compliance
search.appverid:
- MET150
description: Die Microsoft Compliance-Erweiterung erweitert die Überwachung von Dateiaktivitäten und Schutzaktionen auf den Google Chrome-Browser
ms.openlocfilehash: cf7a3cd2e26f2e7d7a116e4a609f98aeea78be19
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2021
ms.locfileid: "52843806"
---
# <a name="learn-about-the-microsoft-compliance-extension"></a><span data-ttu-id="f7ae0-103">Erfahren Sie mehr über die Microsoft Compliance-Erweiterung</span><span class="sxs-lookup"><span data-stu-id="f7ae0-103">Learn about the Microsoft Compliance Extension</span></span>

<span data-ttu-id="f7ae0-104">[Verhinderung von Datenverlust am Endpunkt (Endpunkt-DLP)](endpoint-dlp-learn-about.md) erweitert die Aktivitätsüberwachung und die Schutzfunktionen von [Microsoft 365-Verhinderung von Datenverlust](dlp-learn-about-dlp.md) auf sensible Elemente auf Windows 10-Geräten.</span><span class="sxs-lookup"><span data-stu-id="f7ae0-104">[Endpoint data loss prevention (endpoint DLP)](endpoint-dlp-learn-about.md) extends the activity monitoring and protection capabilities of [Microsoft 365 data loss prevention (DLP)](dlp-learn-about-dlp.md) to sensitive items that are on Windows 10 devices.</span></span> <span data-ttu-id="f7ae0-105">Sobald Geräte in den Microsoft 365 Compliance-Lösungen eingebunden wurden, werden die Informationen zu den Aktionen, die Benutzer mit und an vertraulichen Elementen ausführen, im [Aktivitäten-Explorer](data-classification-activity-explorer.md) angezeigt, und Sie können Schutzmaßnahmen für diese Elemente über [DLP-Richtlinien](create-test-tune-dlp-policy.md) erzwingen.</span><span class="sxs-lookup"><span data-stu-id="f7ae0-105">Once devices are onboarded into the Microsoft 365 compliance solutions, the information about what users are doing with sensitive items is made visible in [activity explorer](data-classification-activity-explorer.md) and you can enforce protective actions on those items via [DLP policies](create-test-tune-dlp-policy.md).</span></span>

<span data-ttu-id="f7ae0-106">Sobald die Microsoft Compliance-Erweiterung auf einem Windows 10-Gerät installiert ist, werden Organisationen überwachen können, ob ein Benutzer versucht ein vertrauliches Element auf einen Clouddienst mittels Google Chrome hochzuladen, und sie werden Schutzaktionen mittels des DLP erzwingen können.</span><span class="sxs-lookup"><span data-stu-id="f7ae0-106">Once the Microsoft Compliance Extension is installed on a Windows 10 device, organizations can monitor when a user attempts to access or upload a sensitive item to a cloud service using Google Chrome and enforce protective actions via DLP.</span></span>  

## <a name="activities-you-can-monitor-and-take-action-on"></a><span data-ttu-id="f7ae0-107">Aktivitäten, die Sie überwachen und für die Sie Maßnahmen festlegen können</span><span class="sxs-lookup"><span data-stu-id="f7ae0-107">Activities you can monitor and take action on</span></span>

<span data-ttu-id="f7ae0-108">Mit der Microsoft Compliance-Erweiterung können Sie die folgenden Aktivitätstypen überwachen und verwalten, die von Benutzern mit und an vertraulichen Elementen auf Windows 10-Geräten ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="f7ae0-108">The Microsoft Compliance Extension enables you to audit and manage the following types of activities users take on sensitive items on devices running Windows 10.</span></span>

<span data-ttu-id="f7ae0-109">Aktivität</span><span class="sxs-lookup"><span data-stu-id="f7ae0-109">activity</span></span> |<span data-ttu-id="f7ae0-110">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f7ae0-110">description</span></span>  | <span data-ttu-id="f7ae0-111">Unterstützte Richtlinienaktionen</span><span class="sxs-lookup"><span data-stu-id="f7ae0-111">supported policy actions</span></span>|
|---------|---------|---------|
|<span data-ttu-id="f7ae0-112">Datei in die Cloud kopiert</span><span class="sxs-lookup"><span data-stu-id="f7ae0-112">file copied to cloud</span></span>  | <span data-ttu-id="f7ae0-113">Erkennt, wenn ein Benutzer versucht, ein vertrauliches Element in eine eingeschränkte Dienstdomäne hochzuladen oder über den Chrome-Browser</span><span class="sxs-lookup"><span data-stu-id="f7ae0-113">Detects when a user attempts to upload a sensitive item to a restricted service domain through the Chrome browser</span></span> |<span data-ttu-id="f7ae0-114">überwachen, blockieren</span><span class="sxs-lookup"><span data-stu-id="f7ae0-114">audit, block</span></span>|
|<span data-ttu-id="f7ae0-115">Datei gedruckt</span><span class="sxs-lookup"><span data-stu-id="f7ae0-115">file printed</span></span>  |<span data-ttu-id="f7ae0-116">Erkennt, wenn ein Benutzer versucht ein vertrauliches Element zu drucken, das im Chrome-Browser zu einem lokalen Netzwerkdrucker geöffnet ist</span><span class="sxs-lookup"><span data-stu-id="f7ae0-116">Detects when a user attempts to print a sensitive item that is open in the Chrome browser to a local or network printer</span></span> |<span data-ttu-id="f7ae0-117">überwachen, blockieren mit Außerkraftsetzung, blockieren</span><span class="sxs-lookup"><span data-stu-id="f7ae0-117">audit, block with override, block</span></span>|
|<span data-ttu-id="f7ae0-118">Datei in die Zwischenablage kopiert</span><span class="sxs-lookup"><span data-stu-id="f7ae0-118">file copied to clipboard</span></span> |<span data-ttu-id="f7ae0-119">Erkennt, wenn ein Benutzer versucht, Informationen aus einem vertraulichen Element zu kopieren, das in einem Chrome-Browser angezeigt wird, und in eine andere App, einen Prozess, oder ein Element einzufügen.</span><span class="sxs-lookup"><span data-stu-id="f7ae0-119">Detects when a user attempts to copy information from a sensitive item that is being viewed in the Chrome browser and then paste it into another app, process, or item.</span></span> |<span data-ttu-id="f7ae0-120">überwachen, blockieren mit Außerkraftsetzung, blockieren</span><span class="sxs-lookup"><span data-stu-id="f7ae0-120">audit, block with override, block</span></span>|
|<span data-ttu-id="f7ae0-121">Datei auf Wechselmedium kopiert</span><span class="sxs-lookup"><span data-stu-id="f7ae0-121">file copied to removable storage</span></span>    | <span data-ttu-id="f7ae0-122">Erkennt, wen ein Benutzer versucht ein vertrauliches Element oder Informationen von einem vertraulichen Element, das im Chrome-Browser geöffnet ist, auf ein Wechselmedium oder USB-Gerät zu kopieren</span><span class="sxs-lookup"><span data-stu-id="f7ae0-122">Detects when a user attempts to copy a sensitive item or information from a sensitive item that is open in the Chrome browser to removable media or USB device</span></span> |<span data-ttu-id="f7ae0-123">überwachen, blockieren mit Außerkraftsetzung, blockieren</span><span class="sxs-lookup"><span data-stu-id="f7ae0-123">audit, block with override, block</span></span>|
|<span data-ttu-id="f7ae0-124">Datei auf die Netzwerkfreigabe kopiert</span><span class="sxs-lookup"><span data-stu-id="f7ae0-124">file copied to network share</span></span>  |<span data-ttu-id="f7ae0-125">Erkennt, wen ein Benutzer versucht ein vertrauliches Element oder Informationen von einem vertraulichen Element, das im Chrome-Browser geöffnet ist, auf eine Netzwerkfreigabe oder ein zugeordnetes Netzwerklaufwerk zu kopieren.</span><span class="sxs-lookup"><span data-stu-id="f7ae0-125">Detects when a user attempts to copy a sensitive item or information from a sensitive item that is open in the Chrome browser  to a network share or mapped network drive.</span></span>|<span data-ttu-id="f7ae0-126">überwachen, blockieren mit Außerkraftsetzung, blockieren</span><span class="sxs-lookup"><span data-stu-id="f7ae0-126">audit, block with override, block</span></span> |

## <a name="deployment-process"></a><span data-ttu-id="f7ae0-127">Bereitstellungsprozess</span><span class="sxs-lookup"><span data-stu-id="f7ae0-127">Deployment process</span></span>
1. [<span data-ttu-id="f7ae0-128">Endpunkt-DLP – Erste Schritte</span><span class="sxs-lookup"><span data-stu-id="f7ae0-128">Get started with endpoint data loss prevention</span></span>](endpoint-dlp-getting-started.md)
2. [<span data-ttu-id="f7ae0-129">Onboarding-Tools und -Methoden für Windows 10-Computer</span><span class="sxs-lookup"><span data-stu-id="f7ae0-129">Onboarding tools and methods for Windows 10 devices</span></span>](dlp-configure-endpoints.md)
3. [<span data-ttu-id="f7ae0-130">Erweiterung auf Ihre Windows 10-Geräte installieren</span><span class="sxs-lookup"><span data-stu-id="f7ae0-130">Install the extension on your Windows 10 devices</span></span>](dlp-chrome-get-started.md)
4. <span data-ttu-id="f7ae0-131">[DLP-Richtlinien erstellen oder bearbeiten](create-test-tune-dlp-policy.md), die „In Cloud hochladen“-Dienste einschränken, oder greifen Sie mittels unzulässiger Browseraktionen zu und wenden Sie sie auf Ihren Microsoft 10-Geräten an</span><span class="sxs-lookup"><span data-stu-id="f7ae0-131">[Create or edit DLP policies](create-test-tune-dlp-policy.md) that restrict upload to cloud service, or access by unallowed browsers actions and apply them to your Windows 10 devices</span></span>

## <a name="next-steps"></a><span data-ttu-id="f7ae0-132">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="f7ae0-132">Next steps</span></span>

<span data-ttu-id="f7ae0-133">Lesen Sie [Erste Schritte mit der Microsoft Compliance-Erweiterung](dlp-chrome-get-started.md), um vollständige Bereitstellungsverfahren und -Szenarien zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="f7ae0-133">See [Get started with the Microsoft Compliance Extension](dlp-chrome-get-started.md) for complete deployment procedures and scenarios.</span></span>

## <a name="see-also"></a><span data-ttu-id="f7ae0-134">Mehr dazu</span><span class="sxs-lookup"><span data-stu-id="f7ae0-134">See also</span></span>

- [<span data-ttu-id="f7ae0-135">Erste Schritte mit der Microsoft Compliance-Erweiterung</span><span class="sxs-lookup"><span data-stu-id="f7ae0-135">Get started with Microsoft Compliance Extension</span></span>](dlp-chrome-get-started.md)
- [<span data-ttu-id="f7ae0-136">Informationen zu Microsoft 365 Endpunkt-DLP (Data Loss Prevention, Verhinderung von Datenverlust)</span><span class="sxs-lookup"><span data-stu-id="f7ae0-136">Learn about Microsoft 365 Endpoint data loss prevention</span></span>](endpoint-dlp-learn-about.md)
- [<span data-ttu-id="f7ae0-137">Erste Schritte mit Microsoft Endpunkt-DLP</span><span class="sxs-lookup"><span data-stu-id="f7ae0-137">Getting started with Microsoft Endpoint data loss prevention</span></span>](endpoint-dlp-getting-started.md)
- [<span data-ttu-id="f7ae0-138">Nutzung von Microsoft Endpunkt-DLP </span><span class="sxs-lookup"><span data-stu-id="f7ae0-138">Using Microsoft Endpoint data loss prevention</span></span>](endpoint-dlp-using.md)
- [<span data-ttu-id="f7ae0-139">Informationen zur Verhinderung von Datenverlust</span><span class="sxs-lookup"><span data-stu-id="f7ae0-139">Learn about data loss prevention</span></span>](dlp-learn-about-dlp.md)
- [<span data-ttu-id="f7ae0-140">Erstellen, Testen und Optimieren einer DLP-Richtlinie</span><span class="sxs-lookup"><span data-stu-id="f7ae0-140">Create, test, and tune a DLP policy</span></span>](create-test-tune-dlp-policy.md)
- [<span data-ttu-id="f7ae0-141">Erste Schritte mit dem Aktivitäten-Explorer</span><span class="sxs-lookup"><span data-stu-id="f7ae0-141">Get started with Activity explorer</span></span>](data-classification-activity-explorer.md)
- [<span data-ttu-id="f7ae0-142">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="f7ae0-142">Microsoft Defender for Endpoint</span></span>](/windows/security/threat-protection/)
- [<span data-ttu-id="f7ae0-143">Insider-Risikomanagement</span><span class="sxs-lookup"><span data-stu-id="f7ae0-143">Insider Risk management</span></span>](insider-risk-management.md)
