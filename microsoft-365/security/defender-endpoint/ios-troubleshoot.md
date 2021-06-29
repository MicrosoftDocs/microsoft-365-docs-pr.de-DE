---
title: Behandeln von Problemen und Suchen nach Antworten auf häufig gestellte Fragen im Zusammenhang mit Microsoft Defender für Endpunkt unter iOS
description: Problembehandlung und häufig gestellte Fragen – Microsoft Defender für Endpunkt unter iOS
keywords: Microsoft, Defender, Microsoft Defender für Endpunkt, ios, Problembehandlung, häufig gestellte Fragen, Vorgehensweise
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
ms.openlocfilehash: b82b6993ce9ed5a3f0f3e6e13e8a260a185c9730
ms.sourcegitcommit: 6749455c52b0f98a92f6fffbc2bb86caf3538bd8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/29/2021
ms.locfileid: "53194973"
---
# <a name="troubleshoot-issues-and-find-answers-to-faqs-on-microsoft-defender-for-endpoint-on-ios"></a><span data-ttu-id="c8882-104">Behandeln von Problemen und Suchen nach Antworten auf häufig gestellte Fragen zu Microsoft Defender für Endpunkt unter iOS</span><span class="sxs-lookup"><span data-stu-id="c8882-104">Troubleshoot issues and find answers to FAQs on Microsoft Defender for Endpoint on iOS</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="c8882-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="c8882-105">**Applies to:**</span></span>
- [<span data-ttu-id="c8882-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="c8882-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="c8882-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c8882-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="c8882-108">Möchten Sie Defender für Endpunkt erfahren?</span><span class="sxs-lookup"><span data-stu-id="c8882-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="c8882-109">Registrieren Sie sich für eine kostenlose Testversion</span><span class="sxs-lookup"><span data-stu-id="c8882-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

<span data-ttu-id="c8882-110">Dieses Thema enthält Informationen zur Problembehandlung, mit denen Sie Probleme beheben können, die bei der Verwendung von Microsoft Defender für Endpunkt unter iOS auftreten können.</span><span class="sxs-lookup"><span data-stu-id="c8882-110">This topic provides troubleshooting information to help you address issues that may arise as you use Microsoft Defender for Endpoint on iOS.</span></span>



> [!NOTE]
> <span data-ttu-id="c8882-111">Defender für Endpunkt unter iOS würde ein VPN verwenden, um das Webschutzfeature bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="c8882-111">Defender for Endpoint on iOS would use a VPN in order to provide the Web Protection feature.</span></span> <span data-ttu-id="c8882-112">Dies ist kein reguläres VPN und ein lokales/selbstschleifendes VPN, das keinen Datenverkehr außerhalb des Geräts aufnimmt.</span><span class="sxs-lookup"><span data-stu-id="c8882-112">This is not a regular VPN and is a local/self-looping VPN that does not take traffic outside the device.</span></span>

## <a name="apps-dont-work-when-vpn-is-turned-on"></a><span data-ttu-id="c8882-113">Apps funktionieren nicht, wenn VPN aktiviert ist</span><span class="sxs-lookup"><span data-stu-id="c8882-113">Apps don't work when VPN is turned on</span></span>
<span data-ttu-id="c8882-114">Es gibt einige Apps, die nicht mehr funktionieren, wenn ein aktives VPN erkannt wird.</span><span class="sxs-lookup"><span data-stu-id="c8882-114">There are some apps that stop functioning when an active VPN is detected.</span></span> <span data-ttu-id="c8882-115">Sie können das VPN während der Verwendung solcher Apps deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="c8882-115">You can disable the VPN during the time you are using such apps.</span></span> 

<span data-ttu-id="c8882-116">Standardmäßig enthält Defender für Endpunkt unter iOS das Webschutzfeature und aktiviert es.</span><span class="sxs-lookup"><span data-stu-id="c8882-116">By default, Defender for Endpoint on iOS includes and enables the web protection feature.</span></span> <span data-ttu-id="c8882-117">[Webschutz](web-protection-overview.md) hilft dabei, Geräte vor Webbedrohungen zu schützen und Benutzer vor Phishingangriffen zu schützen.</span><span class="sxs-lookup"><span data-stu-id="c8882-117">[Web protection](web-protection-overview.md) helps to secure devices against web threats and protect users from phishing attacks.</span></span> <span data-ttu-id="c8882-118">Defender für Endpunkt unter iOS verwendet ein VPN, um diesen Schutz bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="c8882-118">Defender for Endpoint on iOS uses a VPN in order to provide this protection.</span></span> <span data-ttu-id="c8882-119">Bitte beachten Sie, dass es sich um ein lokales VPN handelt und im Gegensatz zu herkömmlichem VPN kein Netzwerkdatenverkehr außerhalb des Geräts gesendet wird.</span><span class="sxs-lookup"><span data-stu-id="c8882-119">Please note this is a local VPN and unlike traditional VPN, network traffic is not sent outside the device.</span></span>

<span data-ttu-id="c8882-120">Obwohl sie standardmäßig aktiviert ist, kann es einige Fälle geben, in denen Sie VPN deaktivieren müssen.</span><span class="sxs-lookup"><span data-stu-id="c8882-120">While enabled by default, there might be some cases that require you to disable VPN.</span></span> <span data-ttu-id="c8882-121">Sie möchten beispielsweise einige Apps ausführen, die nicht funktionieren, wenn ein VPN konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="c8882-121">For example, you want to run some apps that do not work when a VPN is configured.</span></span> <span data-ttu-id="c8882-122">In solchen Fällen können Sie vpn von der App auf dem Gerät deaktivieren, indem Sie die folgenden Schritte ausführen:</span><span class="sxs-lookup"><span data-stu-id="c8882-122">In such cases, you can choose to disable VPN from the app on the device by following the steps below:</span></span>

1. <span data-ttu-id="c8882-123">Öffnen Sie auf Ihrem iOS-Gerät die **Einstellungen** App, klicken oder tippen Sie auf **"Allgemein"** und dann auf **"VPN".**</span><span class="sxs-lookup"><span data-stu-id="c8882-123">On your iOS device, open the **Settings** app, click or tap **General** and then **VPN**.</span></span>
1. <span data-ttu-id="c8882-124">Klicken oder tippen Sie auf die Schaltfläche "i" für Microsoft Defender für Endpunkt.</span><span class="sxs-lookup"><span data-stu-id="c8882-124">Click or tap the "i" button for Microsoft Defender for Endpoint.</span></span>
1. <span data-ttu-id="c8882-125">Schalten Sie **Verbinden bei Bedarf** aus, um VPN zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="c8882-125">Toggle off **Connect On Demand** to disable VPN.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="c8882-126">![VPN config connect on demand](images/ios-vpn-config.png)</span><span class="sxs-lookup"><span data-stu-id="c8882-126">![VPN config connect on demand](images/ios-vpn-config.png)</span></span>

> [!NOTE]
> <span data-ttu-id="c8882-127">Webschutz ist nicht verfügbar, wenn VPN deaktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="c8882-127">Web Protection will not be available when VPN is disabled.</span></span> <span data-ttu-id="c8882-128">Um Web Protection erneut zu aktivieren, öffnen Sie die Microsoft Defender für Endpunkt-App auf dem Gerät, und klicken oder tippen Sie auf **"VPN starten".**</span><span class="sxs-lookup"><span data-stu-id="c8882-128">To re-enable Web Protection, open the Microsoft Defender for Endpoint app on the device and click or tap **Start VPN**.</span></span>

## <a name="co-existence-with-multiple-vpn-profiles"></a><span data-ttu-id="c8882-129">Koexistenz mit mehreren VPN-Profilen</span><span class="sxs-lookup"><span data-stu-id="c8882-129">Co-existence with multiple VPN profiles</span></span>

<span data-ttu-id="c8882-130">Apple iOS unterstützt nicht, dass mehrere **geräteweite** VPNs gleichzeitig aktiv sind.</span><span class="sxs-lookup"><span data-stu-id="c8882-130">Apple iOS does not support multiple **device-wide** VPNs to be active simultaneously.</span></span> <span data-ttu-id="c8882-131">Während mehrere VPN-Profile auf dem Gerät vorhanden sein können, kann jeweils nur ein VPN aktiv sein.</span><span class="sxs-lookup"><span data-stu-id="c8882-131">While multiple VPN profiles can exist on the device, only one VPN can be active at a time.</span></span>

<span data-ttu-id="c8882-132">Microsoft Defender für Endpunkt-VPN kann gemeinsam mit anderen VPNs vorhanden sein, die als *pro App* oder *"Persönlich"* konfiguriert sind.</span><span class="sxs-lookup"><span data-stu-id="c8882-132">Microsoft Defender for Endpoint VPN can co-exist with other VPNs that are configured as *per-app* or *"Personal"*.</span></span>

## <a name="battery-consumption"></a><span data-ttu-id="c8882-133">Akkuverbrauch</span><span class="sxs-lookup"><span data-stu-id="c8882-133">Battery consumption</span></span>

<span data-ttu-id="c8882-134">In der Einstellungen App zeigt iOS nur die Akkunutzung von Apps an, die für einen bestimmten Zeitraum für den Benutzer sichtbar sind.</span><span class="sxs-lookup"><span data-stu-id="c8882-134">In the Settings app, iOS only shows battery usage of apps that are visible to the user for a specific duration of time.</span></span> <span data-ttu-id="c8882-135">Der Akkuverbrauch von Apps, die auf dem Bildschirm angezeigt werden, gilt nur für diese Zeit und wird von iOS basierend auf einer Vielzahl von Faktoren wie CPU- und Netzwerkauslastung berechnet.</span><span class="sxs-lookup"><span data-stu-id="c8882-135">The battery usage by apps shown on the screen are only for that time duration and is computed by iOS based on a multitude of factors including CPU and Network usage.</span></span> <span data-ttu-id="c8882-136">Microsoft Defender für Endpunkt verwendet ein lokales/Loop-Back-VPN im Hintergrund, um den Webdatenverkehr auf schädliche Websites oder Verbindungen zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="c8882-136">Microsoft Defender for Endpoint uses a local/loop-back VPN in the background to check web traffic for any malicious websites or connections.</span></span> <span data-ttu-id="c8882-137">Netzwerkpakete aus einer beliebigen App durchlaufen diese Überprüfung und führen dazu, dass die Akkunutzung von Microsoft Defender für Endpunkt ungenau berechnet wird.</span><span class="sxs-lookup"><span data-stu-id="c8882-137">Network packets from any app go through this check and that causes the battery usage of Microsoft Defender for Endpoint to be computed inaccurately.</span></span> <span data-ttu-id="c8882-138">Der tatsächliche Akkuverbrauch von Microsoft Defender für Endpunkt ist viel geringer als der, der auf der Seite "Akku Einstellungen" auf dem Gerät angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="c8882-138">The actual battery consumption of Microsoft Defender for Endpoint is much less than what is shown on the Battery Settings page on the device.</span></span>

<span data-ttu-id="c8882-139">Der durchschnittliche Akkuverbrauch von Microsoft Defender für Endpunkt im Hintergrund pro Tag beträgt **ca. 8,81 % des gesamten Akkuverbrauchs an diesem Tag.**</span><span class="sxs-lookup"><span data-stu-id="c8882-139">On an average, per-day battery usage by Microsoft Defender for Endpoint running on the background is **approximately 8.81% of overall battery consumed in that day**.</span></span> <span data-ttu-id="c8882-140">Diese Metrik wird von Apple basierend auf der tatsächlichen Nutzung von Microsoft Defender für Endpunkt auf Endbenutzergeräten gemeldet und kann aus den oben genannten Gründen auch auf andere Apps mit Netzwerkaktivität berücksichtigt werden.</span><span class="sxs-lookup"><span data-stu-id="c8882-140">This metric is reported by Apple based on actual usage of Microsoft Defender for Endpoint on end-user devices and due to reasons mentioned above can also be accounted to other apps that have network activity.</span></span>

<span data-ttu-id="c8882-141">Außerdem handelt es sich bei dem verwendeten VPN um ein lokales VPN, und im Gegensatz zu einem herkömmlichen VPN wird kein Netzwerkdatenverkehr außerhalb des Geräts gesendet.</span><span class="sxs-lookup"><span data-stu-id="c8882-141">Also, the VPN used is a local VPN and unlike a traditional VPN, network traffic is not sent outside the device.</span></span>

## <a name="data-usage"></a><span data-ttu-id="c8882-142">Datennutzung</span><span class="sxs-lookup"><span data-stu-id="c8882-142">Data usage</span></span>

<span data-ttu-id="c8882-143">Microsoft Defender für Endpunkt verwendet ein lokales/Loopback-VPN, um den Webdatenverkehr auf schädliche Websites oder Verbindungen zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="c8882-143">Microsoft Defender for Endpoint uses a local/loopback VPN to check web traffic for any malicious websites or connections.</span></span> <span data-ttu-id="c8882-144">Aus diesem Grund kann die Nutzung von Microsoft Defender für Endpunkt-Daten ungenau berücksichtigt werden.</span><span class="sxs-lookup"><span data-stu-id="c8882-144">Due to this reason, Microsoft Defender for Endpoint data usage can be inaccurately accounted for.</span></span> <span data-ttu-id="c8882-145">Wir haben auch festgestellt, dass, wenn sich das Gerät nur im Mobilfunknetz befindet, die vom Dienstanbieter gemeldete Datennutzung sehr nahe am tatsächlichen Verbrauch liegt, während Apple in der Einstellungen-App etwa 1,5x bis 2x der tatsächlich verbrauchten Daten anzeigt.</span><span class="sxs-lookup"><span data-stu-id="c8882-145">We have also observed that if the device is on cellular network only, the data usage reported by service provider is very close to the actual consumption whereas in the Settings app, Apple shows about 1.5x to 2x of actual data consumed.</span></span>

<span data-ttu-id="c8882-146">Wir haben ähnliche Beobachtungen auch mit anderen VPN-Diensten und haben dies an Apple gemeldet.</span><span class="sxs-lookup"><span data-stu-id="c8882-146">We have similar observations with other VPN services as well and have reported this to Apple.</span></span>

<span data-ttu-id="c8882-147">Darüber hinaus ist es wichtig, dass Microsoft Defender für Endpunkt mit unseren Back-End-Diensten auf dem neuesten Stand ist, um einen besseren Schutz zu bieten.</span><span class="sxs-lookup"><span data-stu-id="c8882-147">In addition, it is critical for Microsoft Defender for Endpoint to be up to date with our backend services to provide better protection.</span></span> <span data-ttu-id="c8882-148">Wir arbeiten jedoch daran, die Datennutzung durch Microsoft Defender für Endpunkt zu optimieren.</span><span class="sxs-lookup"><span data-stu-id="c8882-148">However, we are working on optimizing the data usage by Microsoft Defender for Endpoint.</span></span>

## <a name="report-unsafe-site"></a><span data-ttu-id="c8882-149">Unsichere Website melden</span><span class="sxs-lookup"><span data-stu-id="c8882-149">Report unsafe site</span></span>

<span data-ttu-id="c8882-150">Phishing-Websites imitieren vertrauenswürdige Websites, um Ihre persönlichen oder finanziellen Informationen zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="c8882-150">Phishing websites impersonate trustworthy websites for the purpose of obtaining your personal or financial information.</span></span> <span data-ttu-id="c8882-151">Besuchen Sie die Seite ["Feedback zum Netzwerkschutz",](https://www.microsoft.com/wdsi/filesubmission/exploitguard/networkprotection) um eine Website zu melden, bei der es sich um eine Phishing-Website handeln könnte.</span><span class="sxs-lookup"><span data-stu-id="c8882-151">Visit the [Provide feedback about network protection](https://www.microsoft.com/wdsi/filesubmission/exploitguard/networkprotection) page to report a website that could be a phishing site.</span></span>

## <a name="malicious-site-detected"></a><span data-ttu-id="c8882-152">Schadsoftware-Website erkannt</span><span class="sxs-lookup"><span data-stu-id="c8882-152">Malicious site detected</span></span>

<span data-ttu-id="c8882-153">Microsoft Defender für Endpunkt schützt Sie vor Phishing oder anderen webbasierten Angriffen.</span><span class="sxs-lookup"><span data-stu-id="c8882-153">Microsoft Defender for Endpoint protects you against phishing or other web-based attacks.</span></span> <span data-ttu-id="c8882-154">Wenn eine schädliche Website erkannt wird, wird die Verbindung blockiert, und eine Warnung wird an das Security Center-Portal der Organisation gesendet.</span><span class="sxs-lookup"><span data-stu-id="c8882-154">If a malicious site is detected, the connection is blocked and an alert is sent to the organization's Security Center portal.</span></span> <span data-ttu-id="c8882-155">Die Warnung enthält den Domänennamen der Verbindung, die Remote-IP-Adresse und die Gerätedetails.</span><span class="sxs-lookup"><span data-stu-id="c8882-155">The alert includes the domain name of the connection, remote IP address and the device details.</span></span>

<span data-ttu-id="c8882-156">Darüber hinaus wird eine Benachrichtigung auf dem iOS-Gerät angezeigt.</span><span class="sxs-lookup"><span data-stu-id="c8882-156">In addition, a notification is shown on the iOS device.</span></span> <span data-ttu-id="c8882-157">Durch Tippen auf die Benachrichtigung wird der folgende Bildschirm geöffnet, auf dem der Benutzer die Details überprüfen kann.</span><span class="sxs-lookup"><span data-stu-id="c8882-157">Tapping on the notification opens the following screen for the user to review the details.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="c8882-158">![Abbildung der Website, die als unsichere Benachrichtigung gemeldet wird](images/ios-phish-alert.png)</span><span class="sxs-lookup"><span data-stu-id="c8882-158">![Image of site reported as unsafe notification](images/ios-phish-alert.png)</span></span>

## <a name="data-and-privacy"></a><span data-ttu-id="c8882-159">Daten und Datenschutz</span><span class="sxs-lookup"><span data-stu-id="c8882-159">Data and Privacy</span></span>

<span data-ttu-id="c8882-160">Ausführliche Informationen zu gesammelten Daten und zum Datenschutz finden Sie unter [Datenschutzinformationen – Microsoft Defender für Endpunkt unter iOS.](ios-privacy.md)</span><span class="sxs-lookup"><span data-stu-id="c8882-160">For details about data collected and privacy, see [Privacy Information - Microsoft Defender for Endpoint on iOS](ios-privacy.md).</span></span>

