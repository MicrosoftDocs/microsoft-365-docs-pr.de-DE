---
title: Microsoft Defender für Endpunkt auf Nicht-Windows-Plattformen
description: Erfahren Sie mehr über die Microsoft Defender für Endpunkt-Funktionen für Nicht-Windows-Plattformen
keywords: Nicht-Fenster, Mac, Macos, Linux, Android
search.product: eADQiWindows 10XVcnh
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
- M365-security-compliance
- m365solution-evalutatemtp
ms.topic: article
ms.technology: mde
ms.openlocfilehash: dc5710a73685c67eff17c0f281bd14e48707e60f
ms.sourcegitcommit: 1c11035dd4432e34603022740baef0c8f7ff4425
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/16/2021
ms.locfileid: "52964788"
---
# <a name="microsoft-defender-for-endpoint-for-non-windows-platforms"></a><span data-ttu-id="69f8e-104">Microsoft Defender für Endpunkt auf Nicht-Windows-Plattformen</span><span class="sxs-lookup"><span data-stu-id="69f8e-104">Microsoft Defender for Endpoint for non-Windows platforms</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="69f8e-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="69f8e-105">**Applies to:**</span></span>
- [<span data-ttu-id="69f8e-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="69f8e-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="69f8e-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="69f8e-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


> <span data-ttu-id="69f8e-108">Möchten Sie Microsoft Defender für Endpunkt erleben?</span><span class="sxs-lookup"><span data-stu-id="69f8e-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="69f8e-109">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="69f8e-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="69f8e-110">Microsoft ist auf dem Weg, seine branchenführenden Endpunktsicherheitsfunktionen über Windows und Windows Server hinaus auf macOS, Linux, Android und bald iOS zu erweitern.</span><span class="sxs-lookup"><span data-stu-id="69f8e-110">Microsoft has been on a journey to extend its industry leading endpoint security capabilities beyond Windows and Windows Server to macOS, Linux, Android, and soon iOS.</span></span>

<span data-ttu-id="69f8e-111">Organisationen sind mit Bedrohungen auf einer Vielzahl von Plattformen und Geräten konfrontiert.</span><span class="sxs-lookup"><span data-stu-id="69f8e-111">Organizations face threats across a variety of platforms and devices.</span></span> <span data-ttu-id="69f8e-112">Unsere Teams haben sich verpflichtet, Sicherheitslösungen nicht nur *für* Microsoft, sondern auch *von* Microsoft zu entwickeln, damit unsere Kunden ihre heterogenen Umgebungen schützen und schützen können.</span><span class="sxs-lookup"><span data-stu-id="69f8e-112">Our teams have committed to building security solutions not just *for* Microsoft, but also *from* Microsoft to enable our customers to protect and secure their heterogenous environments.</span></span> <span data-ttu-id="69f8e-113">Wir hören auf Kundenfeedback und arbeiten eng mit unseren Kunden zusammen, um Lösungen zu erstellen, die ihren Anforderungen entsprechen.</span><span class="sxs-lookup"><span data-stu-id="69f8e-113">We're listening to customer feedback and partnering closely with our customers to build solutions that meet their needs.</span></span>

<span data-ttu-id="69f8e-114">Mit Microsoft Defender für Endpunkt profitieren Kunden von einer einheitlichen Ansicht aller Bedrohungen und Warnungen in der Microsoft Defender Security Center, über Windows- und Nicht-Windows-Plattformen hinweg, sodass sie ein vollständiges Bild davon erhalten können, was in ihrer Umgebung geschieht, sodass sie Bedrohungen schneller bewerten und darauf reagieren können.</span><span class="sxs-lookup"><span data-stu-id="69f8e-114">With Microsoft Defender for Endpoint, customers benefit from a unified view of all threats and alerts in the Microsoft Defender Security Center, across Windows and non-Windows platforms, enabling them to get a full picture of what's happening in their environment, which empowers them to more quickly assess and respond to threats.</span></span>

## <a name="microsoft-defender-for-endpoint-on-macos"></a><span data-ttu-id="69f8e-115">Microsoft Defender für Endpunkt unter Mac OS</span><span class="sxs-lookup"><span data-stu-id="69f8e-115">Microsoft Defender for Endpoint on macOS</span></span> 

<span data-ttu-id="69f8e-116">Microsoft Defender für Endpunkt unter macOS bietet Antivirus- und EDR(EDR)-Funktionen für die drei neuesten veröffentlichten Versionen von macOS.</span><span class="sxs-lookup"><span data-stu-id="69f8e-116">Microsoft Defender for Endpoint on macOS offers antivirus and endpoint detection and response (EDR) capabilities for the three latest released versions of macOS.</span></span> <span data-ttu-id="69f8e-117">Kunden können die Lösung über Microsoft Endpoint Manager und Jamf bereitstellen und verwalten.</span><span class="sxs-lookup"><span data-stu-id="69f8e-117">Customers can deploy and manage the solution through Microsoft Endpoint Manager and Jamf.</span></span> <span data-ttu-id="69f8e-118">Genau wie bei Microsoft Office-Anwendungen unter macOS wird Microsoft Auto Update zum Verwalten von Microsoft Defender für Endpunkt auf Mac-Updates verwendet.</span><span class="sxs-lookup"><span data-stu-id="69f8e-118">Just like with Microsoft Office applications on macOS, Microsoft Auto Update is used to manage Microsoft Defender for Endpoint on Mac updates.</span></span> <span data-ttu-id="69f8e-119">Informationen zu den wichtigsten Features und Vorteilen finden Sie in unseren [Ankündigungen.](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/bg-p/MicrosoftDefenderATPBlog/label-name/macOS)</span><span class="sxs-lookup"><span data-stu-id="69f8e-119">For information about the key features and benefits, read our [announcements](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/bg-p/MicrosoftDefenderATPBlog/label-name/macOS).</span></span>

<span data-ttu-id="69f8e-120">Weitere Informationen zu den ersten Schritten finden Sie in der [Dokumentation](microsoft-defender-endpoint-mac.md)zu Defender für Endpunkt unter macOS.</span><span class="sxs-lookup"><span data-stu-id="69f8e-120">For more details on how to get started, visit the Defender for Endpoint on macOS [documentation](microsoft-defender-endpoint-mac.md).</span></span>

>[!NOTE]
><span data-ttu-id="69f8e-121">Die folgenden Funktionen werden derzeit auf macOS-Endpunkten nicht unterstützt:</span><span class="sxs-lookup"><span data-stu-id="69f8e-121">The following capabilities are not currently supported on macOS endpoints:</span></span>
>- <span data-ttu-id="69f8e-122">Verhinderung von Datenverlust</span><span class="sxs-lookup"><span data-stu-id="69f8e-122">Data loss prevention</span></span>
>- <span data-ttu-id="69f8e-123">Live-Antwort</span><span class="sxs-lookup"><span data-stu-id="69f8e-123">Live response</span></span>
>- <span data-ttu-id="69f8e-124">SIEM</span><span class="sxs-lookup"><span data-stu-id="69f8e-124">SIEM</span></span>


## <a name="microsoft-defender-for-endpoint-on-linux"></a><span data-ttu-id="69f8e-125">Microsoft Defender für Endpunkt unter Linux</span><span class="sxs-lookup"><span data-stu-id="69f8e-125">Microsoft Defender for Endpoint on Linux</span></span>

<span data-ttu-id="69f8e-126">Microsoft Defender für Endpunkt unter Linux bietet präventive (AV)-Funktionen für Linux-Server.</span><span class="sxs-lookup"><span data-stu-id="69f8e-126">Microsoft Defender for Endpoint on Linux offers preventative (AV) capabilities for Linux servers.</span></span> <span data-ttu-id="69f8e-127">Dies umfasst eine vollständige Befehlszeilenerfahrung zum Konfigurieren und Verwalten des Agents, zum Initiieren von Scans und zum Verwalten von Bedrohungen.</span><span class="sxs-lookup"><span data-stu-id="69f8e-127">This includes a full command line experience to configure and manage the agent, initiate scans, and manage threats.</span></span> <span data-ttu-id="69f8e-128">Wir unterstützen aktuelle Versionen der sechs gängigsten Linux Server-Distributionen: RHEL 7.2+, CentOS Linux 7.2+, Ubuntu 16 LTS oder höher LTS, SLES 12+, Git 9+ und Oracle Linux 7.2.</span><span class="sxs-lookup"><span data-stu-id="69f8e-128">We support recent versions of the six most common Linux Server distributions: RHEL 7.2+, CentOS Linux 7.2+, Ubuntu 16 LTS, or higher LTS, SLES 12+, Debian 9+, and Oracle Linux 7.2.</span></span> <span data-ttu-id="69f8e-129">Microsoft Defender für Endpunkt unter Linux kann mithilfe von "Aufrechte", "Ansible" oder mit ihrem vorhandenen Linux-Konfigurationsverwaltungstool bereitgestellt und konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="69f8e-129">Microsoft Defender for Endpoint on Linux can be deployed and configured using Puppet, Ansible, or using your existing Linux configuration management tool.</span></span> <span data-ttu-id="69f8e-130">Informationen zu den wichtigsten Features und Vorteilen finden Sie in unseren [Ankündigungen.](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/bg-p/MicrosoftDefenderATPBlog/label-name/Linux)</span><span class="sxs-lookup"><span data-stu-id="69f8e-130">For information about the key features and benefits, read our [announcements](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/bg-p/MicrosoftDefenderATPBlog/label-name/Linux).</span></span>

<span data-ttu-id="69f8e-131">Weitere Informationen zu den ersten Schritten finden Sie in der [Dokumentation](microsoft-defender-endpoint-linux.md)zu Microsoft Defender für Endpunkt unter Linux.</span><span class="sxs-lookup"><span data-stu-id="69f8e-131">For more details on how to get started, visit the Microsoft Defender for Endpoint on Linux [documentation](microsoft-defender-endpoint-linux.md).</span></span>

>[!NOTE]
><span data-ttu-id="69f8e-132">Die folgenden Funktionen werden derzeit auf Linux-Endpunkten nicht unterstützt:</span><span class="sxs-lookup"><span data-stu-id="69f8e-132">The following capabilities are not currently supported on Linux endpoints:</span></span>
>- <span data-ttu-id="69f8e-133">Verhinderung von Datenverlust</span><span class="sxs-lookup"><span data-stu-id="69f8e-133">Data loss prevention</span></span>
>- <span data-ttu-id="69f8e-134">Live-Antwort</span><span class="sxs-lookup"><span data-stu-id="69f8e-134">Live response</span></span>
>- <span data-ttu-id="69f8e-135">SIEM</span><span class="sxs-lookup"><span data-stu-id="69f8e-135">SIEM</span></span>



## <a name="microsoft-defender-for-endpoint-on-android"></a><span data-ttu-id="69f8e-136">Microsoft Defender für Endpunkt unter Android</span><span class="sxs-lookup"><span data-stu-id="69f8e-136">Microsoft Defender for Endpoint on Android</span></span>

<span data-ttu-id="69f8e-137">Microsoft Defender für Endpunkt unter Android ist unsere Mobile Threat Defense-Lösung für Geräte mit Android 6.0 und höher.</span><span class="sxs-lookup"><span data-stu-id="69f8e-137">Microsoft Defender for Endpoint on Android is our mobile threat defense solution for devices running Android 6.0 and higher.</span></span> <span data-ttu-id="69f8e-138">Sowohl der Android-Enterprise (Arbeitsprofil) als auch der Geräteadministratormodus werden unterstützt.</span><span class="sxs-lookup"><span data-stu-id="69f8e-138">Both Android Enterprise (Work Profile) and Device Administrator modes are supported.</span></span> <span data-ttu-id="69f8e-139">Unter Android bieten wir Webschutz, einschließlich Antiphishing, Blockieren unsicherer Verbindungen und Festlegen von benutzerdefinierten Indikatoren.</span><span class="sxs-lookup"><span data-stu-id="69f8e-139">On Android, we offer web protection, which includes anti-phishing, blocking of unsafe connections, and setting of custom indicators.</span></span> <span data-ttu-id="69f8e-140">Die Lösung sucht nach Schadsoftware und potenziell unerwünschten Anwendungen (PUA) und bietet zusätzliche Funktionen zur Verhinderung von Sicherheitsverletzungen durch Die Integration in Microsoft Endpoint Manager und bedingten Zugriff.</span><span class="sxs-lookup"><span data-stu-id="69f8e-140">The solution scans for malware and potentially unwanted applications (PUA) and offers additional breach prevention capabilities through integration with Microsoft Endpoint Manager and Conditional Access.</span></span> <span data-ttu-id="69f8e-141">Informationen zu den wichtigsten Features und Vorteilen finden Sie in unseren [Ankündigungen.](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/bg-p/MicrosoftDefenderATPBlog/label-name/Android)</span><span class="sxs-lookup"><span data-stu-id="69f8e-141">For information about the key features and benefits, read our [announcements](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/bg-p/MicrosoftDefenderATPBlog/label-name/Android).</span></span>

<span data-ttu-id="69f8e-142">Weitere Informationen zu den ersten Schritten finden Sie in der [Dokumentation](microsoft-defender-endpoint-android.md)zu Microsoft Defender für Endpunkt unter Android.</span><span class="sxs-lookup"><span data-stu-id="69f8e-142">For more details on how to get started, visit the Microsoft Defender for Endpoint on Android [documentation](microsoft-defender-endpoint-android.md).</span></span>

## <a name="microsoft-defender-for-endpoint-on-ios"></a><span data-ttu-id="69f8e-143">Microsoft Defender für Endpunkt für iOS</span><span class="sxs-lookup"><span data-stu-id="69f8e-143">Microsoft Defender for Endpoint on iOS</span></span>

<span data-ttu-id="69f8e-144">Microsoft Defender für Endpunkt unter iOS ist unsere Mobile Threat Defense-Lösung für Geräte mit iOS 11.0 und höher.</span><span class="sxs-lookup"><span data-stu-id="69f8e-144">Microsoft Defender for Endpoint on iOS is our mobile threat defense solution for devices running iOS 11.0 and higher.</span></span> <span data-ttu-id="69f8e-145">Überwachte und nicht überwachte Geräte werden unterstützt.</span><span class="sxs-lookup"><span data-stu-id="69f8e-145">Both Supervised and Unsupervised devices are supported.</span></span> <span data-ttu-id="69f8e-146">Unter iOS bieten wir Webschutz, der Antiphishing, das Blockieren unsicherer Verbindungen und das Festlegen benutzerdefinierter Indikatoren umfasst.</span><span class="sxs-lookup"><span data-stu-id="69f8e-146">On iOS, we offer web protection which includes anti-phishing, blocking unsafe connections, and setting custom indicators.</span></span> <span data-ttu-id="69f8e-147">Weitere Informationen zu den wichtigsten Features und Vorteilen finden Sie in unseren [Ankündigungen.](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/bg-p/MicrosoftDefenderATPBlog/label-name/iOS)</span><span class="sxs-lookup"><span data-stu-id="69f8e-147">For more information about the key features and benefits, read our [announcements](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/bg-p/MicrosoftDefenderATPBlog/label-name/iOS).</span></span> 

<span data-ttu-id="69f8e-148">Weitere Informationen zu den ersten Schritten finden Sie in der [Dokumentation](microsoft-defender-endpoint-ios.md)zu Microsoft Defender für Endpunkt unter iOS.</span><span class="sxs-lookup"><span data-stu-id="69f8e-148">For more details on how to get started, visit the Microsoft Defender for Endpoint on iOS [documentation](microsoft-defender-endpoint-ios.md).</span></span>

## <a name="licensing-requirements"></a><span data-ttu-id="69f8e-149">Lizenzierungsanforderungen</span><span class="sxs-lookup"><span data-stu-id="69f8e-149">Licensing requirements</span></span> 

<span data-ttu-id="69f8e-150">Berechtigte lizenzierte Benutzer können Microsoft Defender für Endpunkt auf bis zu fünf gleichzeitigen Geräten verwenden.</span><span class="sxs-lookup"><span data-stu-id="69f8e-150">Eligible Licensed Users may use Microsoft Defender for Endpoint on up to five concurrent devices.</span></span> <span data-ttu-id="69f8e-151">Microsoft Defender für Endpunkt steht auch zum Kauf über einen Cloud-Lösungsanbieter (CSP) zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="69f8e-151">Microsoft Defender for Endpoint is also available for purchase from a Cloud Solution Provider (CSP).</span></span>

<span data-ttu-id="69f8e-152">Kunden können Microsoft Defender für Endpunkt unter macOS über eine eigenständige Microsoft Defender für Endpunkt-Lizenz als Teil von Microsoft 365 A5/E5 oder Microsoft 365 Security erwerben.</span><span class="sxs-lookup"><span data-stu-id="69f8e-152">Customers can obtain Microsoft Defender for Endpoint on macOS through a standalone Microsoft Defender for Endpoint license, as part of Microsoft 365 A5/E5, or Microsoft 365 Security.</span></span>

<span data-ttu-id="69f8e-153">Kürzlich angekündigte Funktionen von Microsoft Defender für Endpunkt unter Android und iOS sind in den oben genannten Angeboten als Teil der fünf qualifizierten Geräte für berechtigte lizenzierte Benutzer enthalten.</span><span class="sxs-lookup"><span data-stu-id="69f8e-153">Recently announced capabilities of Microsoft Defender for Endpoint on Android and iOS are included in the above mentioned offers as part of the five qualified devices for eligible licensed users.</span></span>

<span data-ttu-id="69f8e-154">Defender für Endpunkt unter Linux ist über die Defender für Endpoint Server-SKU verfügbar, die sowohl für kommerzielle Kunden als auch für Kunden im Bildungsbereich verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="69f8e-154">Defender for Endpoint on Linux is available through the Defender for Endpoint Server SKU that is available for both commercial and education customers.</span></span>

<span data-ttu-id="69f8e-155">Bitte wenden Sie sich an Ihr Kontoteam oder CSP, um Preise und zusätzliche Berechtigungsanforderungen zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="69f8e-155">Please contact your account team or CSP for pricing and additional eligibility requirements.</span></span>
