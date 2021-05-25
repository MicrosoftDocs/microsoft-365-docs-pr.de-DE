---
title: Behandeln von Problemen und Finden von Antworten auf HÄUFIG GESTELLTE Fragen im Zusammenhang mit Microsoft Defender for Endpoint unter iOS
description: Problembehandlung und Häufig gestellte Fragen – Microsoft Defender for Endpoint unter iOS
keywords: microsoft, defender, Microsoft Defender for Endpoint, ios, troubleshoot, faq, how to
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
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 13c0a575fd2614f58eb6a2163cda04118c2a391d
ms.sourcegitcommit: 17f0aada83627d9defa0acf4db03a2d58e46842f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/24/2021
ms.locfileid: "52636278"
---
# <a name="troubleshoot-issues-and-find-answers-to-faqs-on-microsoft-defender-for-endpoint-on-ios"></a><span data-ttu-id="eadb4-104">Behandeln von Problemen und Finden von Antworten auf häufig gestellte Fragen zu Microsoft Defender for Endpoint unter iOS</span><span class="sxs-lookup"><span data-stu-id="eadb4-104">Troubleshoot issues and find answers to FAQs on Microsoft Defender for Endpoint on iOS</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="eadb4-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="eadb4-105">**Applies to:**</span></span>
- [<span data-ttu-id="eadb4-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="eadb4-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="eadb4-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="eadb4-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="eadb4-108">Möchten Sie Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="eadb4-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="eadb4-109">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="eadb4-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

<span data-ttu-id="eadb4-110">Dieses Thema enthält Informationen zur Problembehandlung, mit deren Hilfe Sie Probleme beheben können, die bei der Verwendung von Microsoft Defender for Endpoint unter iOS auftreten können.</span><span class="sxs-lookup"><span data-stu-id="eadb4-110">This topic provides troubleshooting information to help you address issues that may arise as you use Microsoft Defender for Endpoint on iOS.</span></span>



> [!NOTE]
> <span data-ttu-id="eadb4-111">Defender for Endpoint unter iOS würde ein VPN verwenden, um das Web Protection-Feature zur Verfügung zu stellen.</span><span class="sxs-lookup"><span data-stu-id="eadb4-111">Defender for Endpoint on iOS would use a VPN in order to provide the Web Protection feature.</span></span> <span data-ttu-id="eadb4-112">Dies ist kein normales VPN und ein lokales VPN mit selbstschleifender Schleife, das keinen Datenverkehr außerhalb des Geräts verwendet.</span><span class="sxs-lookup"><span data-stu-id="eadb4-112">This is not a regular VPN and is a local/self-looping VPN that does not take traffic outside the device.</span></span>

## <a name="apps-dont-work-when-vpn-is-turned-on"></a><span data-ttu-id="eadb4-113">Apps funktionieren nicht, wenn VPN aktiviert ist</span><span class="sxs-lookup"><span data-stu-id="eadb4-113">Apps don't work when VPN is turned on</span></span>
<span data-ttu-id="eadb4-114">Es gibt einige Apps, die nicht mehr funktionieren, wenn ein aktives VPN erkannt wird.</span><span class="sxs-lookup"><span data-stu-id="eadb4-114">There are some apps that stop functioning when an active VPN is detected.</span></span> <span data-ttu-id="eadb4-115">Sie können das VPN während der Verwendung solcher Apps deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="eadb4-115">You can disable the VPN during the time you are using such apps.</span></span> 

<span data-ttu-id="eadb4-116">Standardmäßig enthält und aktiviert Defender for Endpoint unter iOS das Webschutzfeature.</span><span class="sxs-lookup"><span data-stu-id="eadb4-116">By default, Defender for Endpoint on iOS includes and enables the web protection feature.</span></span> <span data-ttu-id="eadb4-117">[Webschutz trägt](web-protection-overview.md) dazu bei, Geräte vor Webbedrohungen zu schützen und Benutzer vor Phishingangriffen zu schützen.</span><span class="sxs-lookup"><span data-stu-id="eadb4-117">[Web protection](web-protection-overview.md) helps to secure devices against web threats and protect users from phishing attacks.</span></span> <span data-ttu-id="eadb4-118">Defender for Endpoint unter iOS verwendet ein VPN, um diesen Schutz zu gewährleisten.</span><span class="sxs-lookup"><span data-stu-id="eadb4-118">Defender for Endpoint on iOS uses a VPN in order to provide this protection.</span></span> <span data-ttu-id="eadb4-119">Beachten Sie, dass es sich um ein lokales VPN handelt und im Gegensatz zu herkömmlichem VPN kein Netzwerkdatenverkehr außerhalb des Geräts gesendet wird.</span><span class="sxs-lookup"><span data-stu-id="eadb4-119">Please note this is a local VPN and unlike traditional VPN, network traffic is not sent outside the device.</span></span>

<span data-ttu-id="eadb4-120">Obwohl standardmäßig aktiviert, kann es einige Fälle sein, in denen Sie VPN deaktivieren müssen.</span><span class="sxs-lookup"><span data-stu-id="eadb4-120">While enabled by default, there might be some cases that require you to disable VPN.</span></span> <span data-ttu-id="eadb4-121">Beispielsweise möchten Sie einige Apps ausführen, die nicht funktionieren, wenn ein VPN konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="eadb4-121">For example, you want to run some apps that do not work when a VPN is configured.</span></span> <span data-ttu-id="eadb4-122">In solchen Fällen können Sie vpn von der App auf dem Gerät deaktivieren, indem Sie die folgenden Schritte ausführen:</span><span class="sxs-lookup"><span data-stu-id="eadb4-122">In such cases, you can choose to disable VPN from the app on the device by following the steps below:</span></span>

1. <span data-ttu-id="eadb4-123">Öffnen Sie auf Ihrem **iOS-Gerät die Einstellungen** App, klicken oder tippen Sie auf **Allgemein** und dann **auf VPN.**</span><span class="sxs-lookup"><span data-stu-id="eadb4-123">On your iOS device, open the **Settings** app, click or tap **General** and then **VPN**.</span></span>
1. <span data-ttu-id="eadb4-124">Klicken oder tippen Sie auf die Schaltfläche "i" für Microsoft Defender for Endpoint.</span><span class="sxs-lookup"><span data-stu-id="eadb4-124">Click or tap the "i" button for Microsoft Defender for Endpoint.</span></span>
1. <span data-ttu-id="eadb4-125">Umschalten Verbinden **Bei Bedarf, um** VPN zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="eadb4-125">Toggle off **Connect On Demand** to disable VPN.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="eadb4-126">![VPN config connect on demand](images/ios-vpn-config.png)</span><span class="sxs-lookup"><span data-stu-id="eadb4-126">![VPN config connect on demand](images/ios-vpn-config.png)</span></span>

> [!NOTE]
> <span data-ttu-id="eadb4-127">Web Protection ist nicht verfügbar, wenn VPN deaktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="eadb4-127">Web Protection will not be available when VPN is disabled.</span></span> <span data-ttu-id="eadb4-128">Öffnen Sie zum erneuten Aktivieren von Web Protection die Microsoft Defender for Endpoint-App auf dem Gerät, und klicken oder tippen **Sie auf VPN starten.**</span><span class="sxs-lookup"><span data-stu-id="eadb4-128">To re-enable Web Protection, open the Microsoft Defender for Endpoint app on the device and click or tap **Start VPN**.</span></span>

## <a name="issues-with-multiple-vpn-profiles"></a><span data-ttu-id="eadb4-129">Probleme mit mehreren VPN-Profilen</span><span class="sxs-lookup"><span data-stu-id="eadb4-129">Issues with multiple VPN profiles</span></span>

<span data-ttu-id="eadb4-130">Apple iOS unterstützt nicht mehrere geräteweite VPNs, um gleichzeitig aktiv zu sein.</span><span class="sxs-lookup"><span data-stu-id="eadb4-130">Apple iOS does not support multiple device-wide VPNs to be active simultaneously.</span></span> <span data-ttu-id="eadb4-131">Auf dem Gerät können zwar mehrere VPN-Profile vorhanden sein, aber nur ein VPN kann gleichzeitig aktiv sein.</span><span class="sxs-lookup"><span data-stu-id="eadb4-131">While multiple VPN profiles can exist on the device, only one VPN can be active at a time.</span></span>


## <a name="battery-consumption"></a><span data-ttu-id="eadb4-132">Akkuverbrauch</span><span class="sxs-lookup"><span data-stu-id="eadb4-132">Battery consumption</span></span>

<span data-ttu-id="eadb4-133">Der Akkuverbrauch einer App wird von Apple basierend auf einer Vielzahl von Faktoren wie CPU- und Netzwerknutzung berechnet.</span><span class="sxs-lookup"><span data-stu-id="eadb4-133">The battery usage by an app is computed by Apple based on a multitude of factors including CPU and Network usage.</span></span> <span data-ttu-id="eadb4-134">Microsoft Defender for Endpoint verwendet ein lokales /Loop-Back-VPN im Hintergrund, um den Webdatenverkehr auf schädliche Websites oder Verbindungen zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="eadb4-134">Microsoft Defender for Endpoint uses a local/loop-back VPN in the background to check web traffic for any malicious websites or connections.</span></span> <span data-ttu-id="eadb4-135">Netzwerkpakete von jeder App durchgehen diese Prüfung, was dazu führt, dass der Akkuverbrauch von Microsoft Defender for Endpoint ungenau berechnet wird.</span><span class="sxs-lookup"><span data-stu-id="eadb4-135">Network packets from any app go through this check and that causes the battery usage of Microsoft Defender for Endpoint to be computed inaccurately.</span></span> <span data-ttu-id="eadb4-136">Dies gibt dem Benutzer einen falschen Eindruck.</span><span class="sxs-lookup"><span data-stu-id="eadb4-136">This gives a false impression to the user.</span></span> <span data-ttu-id="eadb4-137">Der tatsächliche Akkuverbrauch von Microsoft Defender for Endpoint ist geringer als der, der auf der Seite Battery Einstellungen auf dem Gerät angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="eadb4-137">The actual battery consumption of Microsoft Defender for Endpoint is lesser than what is shown on the Battery Settings page on the device.</span></span> <span data-ttu-id="eadb4-138">Dies basiert auf durchgeführten Tests, die mit der Microsoft Defender for Endpoint-App durchgeführt wurden, um den Akkuverbrauch zu verstehen.</span><span class="sxs-lookup"><span data-stu-id="eadb4-138">This is based on conducted tests done on the Microsoft Defender for Endpoint app to understand battery consumption.</span></span>

<span data-ttu-id="eadb4-139">Auch das verwendete VPN ist ein lokales VPN und im Gegensatz zu einem herkömmlichen VPN wird der Netzwerkdatenverkehr nicht außerhalb des Geräts gesendet.</span><span class="sxs-lookup"><span data-stu-id="eadb4-139">Also the VPN used is a local VPN and unlike a traditional VPN, network traffic is not sent outside the device.</span></span>

## <a name="data-usage"></a><span data-ttu-id="eadb4-140">Datenverwendung</span><span class="sxs-lookup"><span data-stu-id="eadb4-140">Data usage</span></span>

<span data-ttu-id="eadb4-141">Microsoft Defender for Endpoint verwendet ein lokales /loopback-VPN, um den Webdatenverkehr auf schädliche Websites oder Verbindungen zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="eadb4-141">Microsoft Defender for Endpoint uses a local/loopback VPN to check web traffic for any malicious websites or connections.</span></span> <span data-ttu-id="eadb4-142">Aus diesem Grund macht Apple die Datenverwendung für Microsoft Defender for Endpoint ungenau.</span><span class="sxs-lookup"><span data-stu-id="eadb4-142">Due to this reason Apple accounts data usage to Microsoft Defender for Endpoint inaccurately.</span></span> <span data-ttu-id="eadb4-143">Die tatsächliche Datenverwendung durch Microsoft Defender for Endpoint ist nicht signifikant und viel geringer als die Datenverwendungs-Einstellungen auf dem Gerät.</span><span class="sxs-lookup"><span data-stu-id="eadb4-143">The actual data usage by Microsoft Defender for Endpoint is not significant and much less than what is shown on the Data Usage Settings on the device.</span></span>

## <a name="report-unsafe-site"></a><span data-ttu-id="eadb4-144">Unsichere Website melden</span><span class="sxs-lookup"><span data-stu-id="eadb4-144">Report unsafe site</span></span>

<span data-ttu-id="eadb4-145">Phishingwebsites geben sich als vertrauenswürdige Websites aus, um Ihre persönlichen oder finanziellen Informationen zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="eadb4-145">Phishing websites impersonate trustworthy websites for the purpose of obtaining your personal or financial information.</span></span> <span data-ttu-id="eadb4-146">Besuchen Sie [die Seite Feedback zum Netzwerkschutz](https://www.microsoft.com/wdsi/filesubmission/exploitguard/networkprotection) bereitstellen, um eine Website zu melden, bei der es sich um eine Phishingwebsite handelt.</span><span class="sxs-lookup"><span data-stu-id="eadb4-146">Visit the [Provide feedback about network protection](https://www.microsoft.com/wdsi/filesubmission/exploitguard/networkprotection) page to report a website that could be a phishing site.</span></span>

## <a name="malicious-site-detected"></a><span data-ttu-id="eadb4-147">Schädliche Website erkannt</span><span class="sxs-lookup"><span data-stu-id="eadb4-147">Malicious site detected</span></span>

<span data-ttu-id="eadb4-148">Microsoft Defender for Endpoint schützt Sie vor Phishing oder anderen webbasierten Angriffen.</span><span class="sxs-lookup"><span data-stu-id="eadb4-148">Microsoft Defender for Endpoint protects you against phishing or other web-based attacks.</span></span> <span data-ttu-id="eadb4-149">Wenn eine schädliche Website erkannt wird, wird die Verbindung blockiert und eine Warnung an das Security Center-Portal der Organisation gesendet.</span><span class="sxs-lookup"><span data-stu-id="eadb4-149">If a malicious site is detected, the connection is blocked and an alert is sent to the organization's Security Center portal.</span></span> <span data-ttu-id="eadb4-150">Die Warnung enthält den Domänennamen der Verbindung, die Remote-IP-Adresse und die Gerätedetails.</span><span class="sxs-lookup"><span data-stu-id="eadb4-150">The alert includes the domain name of the connection, remote IP address and the device details.</span></span>

<span data-ttu-id="eadb4-151">Darüber hinaus wird auf dem iOS-Gerät eine Benachrichtigung angezeigt.</span><span class="sxs-lookup"><span data-stu-id="eadb4-151">In addition, a notification is shown on the iOS device.</span></span> <span data-ttu-id="eadb4-152">Durch Tippen auf die Benachrichtigung wird der folgende Bildschirm geöffnet, damit der Benutzer die Details überprüfen kann.</span><span class="sxs-lookup"><span data-stu-id="eadb4-152">Tapping on the notification opens the following screen for the user to review the details.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="eadb4-153">![Abbildung der Website, die als unsichere Benachrichtigung gemeldet wurde](images/ios-phish-alert.png)</span><span class="sxs-lookup"><span data-stu-id="eadb4-153">![Image of site reported as unsafe notification](images/ios-phish-alert.png)</span></span>

## <a name="data-and-privacy"></a><span data-ttu-id="eadb4-154">Daten und Datenschutz</span><span class="sxs-lookup"><span data-stu-id="eadb4-154">Data and Privacy</span></span>

<span data-ttu-id="eadb4-155">Weitere Informationen zu erfassten Daten und zum Datenschutz finden Sie unter [Datenschutzinformationen – Microsoft Defender for Endpoint unter iOS](ios-privacy.md).</span><span class="sxs-lookup"><span data-stu-id="eadb4-155">For details about data collected and privacy, see [Privacy Information - Microsoft Defender for Endpoint on iOS](ios-privacy.md).</span></span>

