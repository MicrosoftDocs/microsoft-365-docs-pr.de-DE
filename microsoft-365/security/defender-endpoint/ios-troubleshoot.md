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
ms.openlocfilehash: 2f9d56b7e72befb8acddf6d9f810a7ba5cec1083
ms.sourcegitcommit: 5377b00703b6f559092afe44fb61462e97968a60
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/27/2021
ms.locfileid: "52694365"
---
# <a name="troubleshoot-issues-and-find-answers-to-faqs-on-microsoft-defender-for-endpoint-on-ios"></a><span data-ttu-id="6d276-104">Behandeln von Problemen und Finden von Antworten auf häufig gestellte Fragen zu Microsoft Defender for Endpoint unter iOS</span><span class="sxs-lookup"><span data-stu-id="6d276-104">Troubleshoot issues and find answers to FAQs on Microsoft Defender for Endpoint on iOS</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="6d276-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="6d276-105">**Applies to:**</span></span>
- [<span data-ttu-id="6d276-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="6d276-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="6d276-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="6d276-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="6d276-108">Möchten Sie Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="6d276-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="6d276-109">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="6d276-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

<span data-ttu-id="6d276-110">Dieses Thema enthält Informationen zur Problembehandlung, mit deren Hilfe Sie Probleme beheben können, die bei der Verwendung von Microsoft Defender for Endpoint unter iOS auftreten können.</span><span class="sxs-lookup"><span data-stu-id="6d276-110">This topic provides troubleshooting information to help you address issues that may arise as you use Microsoft Defender for Endpoint on iOS.</span></span>



> [!NOTE]
> <span data-ttu-id="6d276-111">Defender for Endpoint unter iOS würde ein VPN verwenden, um das Web Protection-Feature zur Verfügung zu stellen.</span><span class="sxs-lookup"><span data-stu-id="6d276-111">Defender for Endpoint on iOS would use a VPN in order to provide the Web Protection feature.</span></span> <span data-ttu-id="6d276-112">Dies ist kein normales VPN und ein lokales VPN mit selbstschleifender Schleife, das keinen Datenverkehr außerhalb des Geräts verwendet.</span><span class="sxs-lookup"><span data-stu-id="6d276-112">This is not a regular VPN and is a local/self-looping VPN that does not take traffic outside the device.</span></span>

## <a name="apps-dont-work-when-vpn-is-turned-on"></a><span data-ttu-id="6d276-113">Apps funktionieren nicht, wenn VPN aktiviert ist</span><span class="sxs-lookup"><span data-stu-id="6d276-113">Apps don't work when VPN is turned on</span></span>
<span data-ttu-id="6d276-114">Es gibt einige Apps, die nicht mehr funktionieren, wenn ein aktives VPN erkannt wird.</span><span class="sxs-lookup"><span data-stu-id="6d276-114">There are some apps that stop functioning when an active VPN is detected.</span></span> <span data-ttu-id="6d276-115">Sie können das VPN während der Verwendung solcher Apps deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="6d276-115">You can disable the VPN during the time you are using such apps.</span></span> 

<span data-ttu-id="6d276-116">Standardmäßig enthält und aktiviert Defender for Endpoint unter iOS das Webschutzfeature.</span><span class="sxs-lookup"><span data-stu-id="6d276-116">By default, Defender for Endpoint on iOS includes and enables the web protection feature.</span></span> <span data-ttu-id="6d276-117">[Webschutz trägt](web-protection-overview.md) dazu bei, Geräte vor Webbedrohungen zu schützen und Benutzer vor Phishingangriffen zu schützen.</span><span class="sxs-lookup"><span data-stu-id="6d276-117">[Web protection](web-protection-overview.md) helps to secure devices against web threats and protect users from phishing attacks.</span></span> <span data-ttu-id="6d276-118">Defender for Endpoint unter iOS verwendet ein VPN, um diesen Schutz zu gewährleisten.</span><span class="sxs-lookup"><span data-stu-id="6d276-118">Defender for Endpoint on iOS uses a VPN in order to provide this protection.</span></span> <span data-ttu-id="6d276-119">Beachten Sie, dass es sich um ein lokales VPN handelt und im Gegensatz zu herkömmlichem VPN kein Netzwerkdatenverkehr außerhalb des Geräts gesendet wird.</span><span class="sxs-lookup"><span data-stu-id="6d276-119">Please note this is a local VPN and unlike traditional VPN, network traffic is not sent outside the device.</span></span>

<span data-ttu-id="6d276-120">Obwohl standardmäßig aktiviert, kann es einige Fälle sein, in denen Sie VPN deaktivieren müssen.</span><span class="sxs-lookup"><span data-stu-id="6d276-120">While enabled by default, there might be some cases that require you to disable VPN.</span></span> <span data-ttu-id="6d276-121">Beispielsweise möchten Sie einige Apps ausführen, die nicht funktionieren, wenn ein VPN konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="6d276-121">For example, you want to run some apps that do not work when a VPN is configured.</span></span> <span data-ttu-id="6d276-122">In solchen Fällen können Sie vpn von der App auf dem Gerät deaktivieren, indem Sie die folgenden Schritte ausführen:</span><span class="sxs-lookup"><span data-stu-id="6d276-122">In such cases, you can choose to disable VPN from the app on the device by following the steps below:</span></span>

1. <span data-ttu-id="6d276-123">Öffnen Sie auf Ihrem **iOS-Gerät die Einstellungen** App, klicken oder tippen Sie auf **Allgemein** und dann **auf VPN.**</span><span class="sxs-lookup"><span data-stu-id="6d276-123">On your iOS device, open the **Settings** app, click or tap **General** and then **VPN**.</span></span>
1. <span data-ttu-id="6d276-124">Klicken oder tippen Sie auf die Schaltfläche "i" für Microsoft Defender for Endpoint.</span><span class="sxs-lookup"><span data-stu-id="6d276-124">Click or tap the "i" button for Microsoft Defender for Endpoint.</span></span>
1. <span data-ttu-id="6d276-125">Umschalten Verbinden **Bei Bedarf, um** VPN zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="6d276-125">Toggle off **Connect On Demand** to disable VPN.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="6d276-126">![VPN config connect on demand](images/ios-vpn-config.png)</span><span class="sxs-lookup"><span data-stu-id="6d276-126">![VPN config connect on demand](images/ios-vpn-config.png)</span></span>

> [!NOTE]
> <span data-ttu-id="6d276-127">Web Protection ist nicht verfügbar, wenn VPN deaktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="6d276-127">Web Protection will not be available when VPN is disabled.</span></span> <span data-ttu-id="6d276-128">Öffnen Sie zum erneuten Aktivieren von Web Protection die Microsoft Defender for Endpoint-App auf dem Gerät, und klicken oder tippen **Sie auf VPN starten.**</span><span class="sxs-lookup"><span data-stu-id="6d276-128">To re-enable Web Protection, open the Microsoft Defender for Endpoint app on the device and click or tap **Start VPN**.</span></span>

## <a name="issues-with-multiple-vpn-profiles"></a><span data-ttu-id="6d276-129">Probleme mit mehreren VPN-Profilen</span><span class="sxs-lookup"><span data-stu-id="6d276-129">Issues with multiple VPN profiles</span></span>

<span data-ttu-id="6d276-130">Apple iOS unterstützt nicht mehrere **geräteweite** VPNs, um gleichzeitig aktiv zu sein.</span><span class="sxs-lookup"><span data-stu-id="6d276-130">Apple iOS does not support multiple **device-wide** VPNs to be active simultaneously.</span></span> <span data-ttu-id="6d276-131">Auf dem Gerät können zwar mehrere VPN-Profile vorhanden sein, aber nur ein VPN kann gleichzeitig aktiv sein.</span><span class="sxs-lookup"><span data-stu-id="6d276-131">While multiple VPN profiles can exist on the device, only one VPN can be active at a time.</span></span>

<span data-ttu-id="6d276-132">Microsoft Defender for Endpoint VPN kann mit anderen VPNs koexistent sein, die als pro *App* oder *"Persönlich" konfiguriert sind.*</span><span class="sxs-lookup"><span data-stu-id="6d276-132">Microsoft Defender for Endpoint VPN can co-exist with other VPNs that are configured as *per-app* or *"Personal"*.</span></span>

## <a name="battery-consumption"></a><span data-ttu-id="6d276-133">Akkuverbrauch</span><span class="sxs-lookup"><span data-stu-id="6d276-133">Battery consumption</span></span>

<span data-ttu-id="6d276-134">In der Einstellungen zeigt iOS nur den Akkuverbrauch von Apps an, die für den Benutzer für einen bestimmten Zeitraum sichtbar sind.</span><span class="sxs-lookup"><span data-stu-id="6d276-134">In the Settings app, iOS only shows battery usage of apps that are visible to the user for a specific duration of time.</span></span> <span data-ttu-id="6d276-135">Der Akkuverbrauch von Apps, die auf dem Bildschirm angezeigt werden, gilt nur für diese Zeitdauer und wird von iOS basierend auf einer Vielzahl von Faktoren wie CPU- und Netzwerknutzung berechnet.</span><span class="sxs-lookup"><span data-stu-id="6d276-135">The battery usage by apps shown on the screen are only for that time duration and is computed by iOS based on a multitude of factors including CPU and Network usage.</span></span> <span data-ttu-id="6d276-136">Microsoft Defender for Endpoint verwendet ein lokales /Loop-Back-VPN im Hintergrund, um den Webdatenverkehr auf schädliche Websites oder Verbindungen zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="6d276-136">Microsoft Defender for Endpoint uses a local/loop-back VPN in the background to check web traffic for any malicious websites or connections.</span></span> <span data-ttu-id="6d276-137">Netzwerkpakete von jeder App durchgehen diese Prüfung, was dazu führt, dass der Akkuverbrauch von Microsoft Defender for Endpoint ungenau berechnet wird.</span><span class="sxs-lookup"><span data-stu-id="6d276-137">Network packets from any app go through this check and that causes the battery usage of Microsoft Defender for Endpoint to be computed inaccurately.</span></span> <span data-ttu-id="6d276-138">Der tatsächliche Akkuverbrauch von Microsoft Defender for Endpoint ist viel geringer als der, der auf der Seite Battery Einstellungen auf dem Gerät angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="6d276-138">The actual battery consumption of Microsoft Defender for Endpoint is much less than what is shown on the Battery Settings page on the device.</span></span>

<span data-ttu-id="6d276-139">Im Durchschnitt beträgt der Akkuverbrauch pro Tag von Microsoft Defender for Endpoint, der im Hintergrund ausgeführt wird, ca. **8,81 %** des gesamten Akkuverbrauchs an diesem Tag.</span><span class="sxs-lookup"><span data-stu-id="6d276-139">On an average, per-day battery usage by Microsoft Defender for Endpoint running on the background is **approximately 8.81% of overall battery consumed in that day**.</span></span> <span data-ttu-id="6d276-140">Diese Metrik wird von Apple basierend auf der tatsächlichen Verwendung von Microsoft Defender for Endpoint auf Endbenutzergeräten gemeldet und kann aus den oben genannten Gründen auch anderen Apps mit Netzwerkaktivität berücksichtigt werden.</span><span class="sxs-lookup"><span data-stu-id="6d276-140">This metric is reported by Apple based on actual usage of Microsoft Defender for Endpoint on end-user devices and due to reasons mentioned above can also be accounted to other apps that have network activity.</span></span>

<span data-ttu-id="6d276-141">Außerdem handelt es sich bei dem verwendeten VPN um ein lokales VPN, und im Gegensatz zu einem herkömmlichen VPN wird der Netzwerkdatenverkehr nicht außerhalb des Geräts gesendet.</span><span class="sxs-lookup"><span data-stu-id="6d276-141">Also, the VPN used is a local VPN and unlike a traditional VPN, network traffic is not sent outside the device.</span></span>

## <a name="data-usage"></a><span data-ttu-id="6d276-142">Datenverwendung</span><span class="sxs-lookup"><span data-stu-id="6d276-142">Data usage</span></span>

<span data-ttu-id="6d276-143">Microsoft Defender for Endpoint verwendet ein lokales /loopback-VPN, um den Webdatenverkehr auf schädliche Websites oder Verbindungen zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="6d276-143">Microsoft Defender for Endpoint uses a local/loopback VPN to check web traffic for any malicious websites or connections.</span></span> <span data-ttu-id="6d276-144">Aus diesem Grund kann die Datenverwendung von Microsoft Defender for Endpoint falsch berücksichtigt werden.</span><span class="sxs-lookup"><span data-stu-id="6d276-144">Due to this reason, Microsoft Defender for Endpoint data usage can be inaccurately accounted for.</span></span> <span data-ttu-id="6d276-145">Die tatsächliche Datenverwendung durch Microsoft Defender for Endpoint ist nicht signifikant und kleiner als die Datenverwendungs-Einstellungen auf dem Gerät.</span><span class="sxs-lookup"><span data-stu-id="6d276-145">The actual data usage by Microsoft Defender for Endpoint is not significant and lesser than what is shown on the Data Usage Settings on the device.</span></span>

## <a name="report-unsafe-site"></a><span data-ttu-id="6d276-146">Unsichere Website melden</span><span class="sxs-lookup"><span data-stu-id="6d276-146">Report unsafe site</span></span>

<span data-ttu-id="6d276-147">Phishingwebsites geben sich als vertrauenswürdige Websites aus, um Ihre persönlichen oder finanziellen Informationen zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="6d276-147">Phishing websites impersonate trustworthy websites for the purpose of obtaining your personal or financial information.</span></span> <span data-ttu-id="6d276-148">Besuchen Sie [die Seite Feedback zum Netzwerkschutz](https://www.microsoft.com/wdsi/filesubmission/exploitguard/networkprotection) bereitstellen, um eine Website zu melden, bei der es sich um eine Phishingwebsite handelt.</span><span class="sxs-lookup"><span data-stu-id="6d276-148">Visit the [Provide feedback about network protection](https://www.microsoft.com/wdsi/filesubmission/exploitguard/networkprotection) page to report a website that could be a phishing site.</span></span>

## <a name="malicious-site-detected"></a><span data-ttu-id="6d276-149">Schädliche Website erkannt</span><span class="sxs-lookup"><span data-stu-id="6d276-149">Malicious site detected</span></span>

<span data-ttu-id="6d276-150">Microsoft Defender for Endpoint schützt Sie vor Phishing oder anderen webbasierten Angriffen.</span><span class="sxs-lookup"><span data-stu-id="6d276-150">Microsoft Defender for Endpoint protects you against phishing or other web-based attacks.</span></span> <span data-ttu-id="6d276-151">Wenn eine schädliche Website erkannt wird, wird die Verbindung blockiert und eine Warnung an das Security Center-Portal der Organisation gesendet.</span><span class="sxs-lookup"><span data-stu-id="6d276-151">If a malicious site is detected, the connection is blocked and an alert is sent to the organization's Security Center portal.</span></span> <span data-ttu-id="6d276-152">Die Warnung enthält den Domänennamen der Verbindung, die Remote-IP-Adresse und die Gerätedetails.</span><span class="sxs-lookup"><span data-stu-id="6d276-152">The alert includes the domain name of the connection, remote IP address and the device details.</span></span>

<span data-ttu-id="6d276-153">Darüber hinaus wird auf dem iOS-Gerät eine Benachrichtigung angezeigt.</span><span class="sxs-lookup"><span data-stu-id="6d276-153">In addition, a notification is shown on the iOS device.</span></span> <span data-ttu-id="6d276-154">Durch Tippen auf die Benachrichtigung wird der folgende Bildschirm geöffnet, damit der Benutzer die Details überprüfen kann.</span><span class="sxs-lookup"><span data-stu-id="6d276-154">Tapping on the notification opens the following screen for the user to review the details.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="6d276-155">![Abbildung der Website, die als unsichere Benachrichtigung gemeldet wurde](images/ios-phish-alert.png)</span><span class="sxs-lookup"><span data-stu-id="6d276-155">![Image of site reported as unsafe notification](images/ios-phish-alert.png)</span></span>

## <a name="data-and-privacy"></a><span data-ttu-id="6d276-156">Daten und Datenschutz</span><span class="sxs-lookup"><span data-stu-id="6d276-156">Data and Privacy</span></span>

<span data-ttu-id="6d276-157">Weitere Informationen zu erfassten Daten und zum Datenschutz finden Sie unter [Datenschutzinformationen – Microsoft Defender for Endpoint unter iOS](ios-privacy.md).</span><span class="sxs-lookup"><span data-stu-id="6d276-157">For details about data collected and privacy, see [Privacy Information - Microsoft Defender for Endpoint on iOS](ios-privacy.md).</span></span>

