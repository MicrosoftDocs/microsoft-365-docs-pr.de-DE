---
title: Konfigurieren von Microsoft Defender for Endpoint unter iOS-Features
description: Beschreibt die Bereitstellung von Microsoft Defender for Endpoint unter iOS-Features
keywords: microsoft, defender, Microsoft Defender for Endpoint, ios, configure, features, ios
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
ms.openlocfilehash: dab72da02927c3fff6025eb2d0fa9ed0fdf1d0d7
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/06/2021
ms.locfileid: "52245276"
---
# <a name="configure-microsoft-defender-for-endpoint-on-ios-features"></a><span data-ttu-id="bf196-104">Konfigurieren von Microsoft Defender for Endpoint unter iOS-Features</span><span class="sxs-lookup"><span data-stu-id="bf196-104">Configure Microsoft Defender for Endpoint on iOS features</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="bf196-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="bf196-105">**Applies to:**</span></span>
- [<span data-ttu-id="bf196-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="bf196-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="bf196-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="bf196-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="bf196-108">Möchten Sie Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="bf196-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="bf196-109">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="bf196-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

> [!NOTE]
> <span data-ttu-id="bf196-110">Defender for Endpoint unter iOS würde ein VPN verwenden, um das Web Protection-Feature zur Verfügung zu stellen.</span><span class="sxs-lookup"><span data-stu-id="bf196-110">Defender for Endpoint on iOS would use a VPN in order to provide the Web Protection feature.</span></span> <span data-ttu-id="bf196-111">Dies ist kein normales VPN und ein lokales VPN mit selbstschleifender Schleife, das keinen Datenverkehr außerhalb des Geräts verwendet.</span><span class="sxs-lookup"><span data-stu-id="bf196-111">This is not a regular VPN and is a local/self-looping VPN that does not take traffic outside the device.</span></span>

## <a name="conditional-access-with-defender-for-endpoint-on-ios"></a><span data-ttu-id="bf196-112">Bedingter Zugriff mit Defender for Endpoint unter iOS</span><span class="sxs-lookup"><span data-stu-id="bf196-112">Conditional Access with Defender for Endpoint on iOS</span></span>  
<span data-ttu-id="bf196-113">Microsoft Defender for Endpoint unter iOS ermöglicht zusammen mit Microsoft Intune und Azure Active Directory die Erzwingung von Gerätekonformität und Richtlinien für bedingten Zugriff basierend auf der Geräterisikopunktzahl.</span><span class="sxs-lookup"><span data-stu-id="bf196-113">Microsoft Defender for Endpoint on iOS along with Microsoft Intune and Azure Active Directory enables enforcing Device compliance and Conditional Access policies based on device risk score.</span></span> <span data-ttu-id="bf196-114">Defender for Endpoint ist eine Mobile Threat Defense (MTD)-Lösung, die Sie bereitstellen können, um diese Funktion über Intune zu nutzen.</span><span class="sxs-lookup"><span data-stu-id="bf196-114">Defender for Endpoint is a Mobile Threat Defense (MTD) solution that you can deploy to leverage this capability via Intune.</span></span>

<span data-ttu-id="bf196-115">Weitere Informationen zum Einrichten des bedingten Zugriffs mit Defender for Endpoint unter iOS finden Sie unter [Defender for Endpoint und Intune](https://docs.microsoft.com/mem/intune/protect/advanced-threat-protection).</span><span class="sxs-lookup"><span data-stu-id="bf196-115">For more information about how to set up Conditional Access with Defender for Endpoint on iOS, see [Defender for Endpoint and Intune](https://docs.microsoft.com/mem/intune/protect/advanced-threat-protection).</span></span>

> [!NOTE]
> <span data-ttu-id="bf196-116">**Die Jailbreakerkennung durch Microsoft Defender for Endpoint unter iOS befindet sich derzeit in der Vorschau**.</span><span class="sxs-lookup"><span data-stu-id="bf196-116">**Jailbreak detection by Microsoft Defender for Endpoint on iOS is currently in preview**.</span></span> <span data-ttu-id="bf196-117">Wenn ein Gerät von Microsoft Defender for Endpoint als jailbroken erkannt wird, wird eine Warnung mit hohem Risiko an das Security Center gemeldet, und wenn bedingter Zugriff basierend auf der Bewertung des Geräterisikos eingerichtet wird, wird das Gerät am Zugriff auf Unternehmensdaten blockiert.</span><span class="sxs-lookup"><span data-stu-id="bf196-117">If a device is detected to be jailbroken by Microsoft Defender for Endpoint, a **High**-risk alert will be reported to Security Center and if Conditional Access is setup based on device risk score, then the device will be blocked from accessing corporate data.</span></span>

## <a name="web-protection-and-vpn"></a><span data-ttu-id="bf196-118">Web Protection und VPN</span><span class="sxs-lookup"><span data-stu-id="bf196-118">Web Protection and VPN</span></span>

<span data-ttu-id="bf196-119">Standardmäßig enthält und aktiviert Defender for Endpoint unter iOS das Webschutzfeature.</span><span class="sxs-lookup"><span data-stu-id="bf196-119">By default, Defender for Endpoint on iOS includes and enables the web protection feature.</span></span> <span data-ttu-id="bf196-120">[Webschutz trägt](web-protection-overview.md) dazu bei, Geräte vor Webbedrohungen zu schützen und Benutzer vor Phishingangriffen zu schützen.</span><span class="sxs-lookup"><span data-stu-id="bf196-120">[Web protection](web-protection-overview.md) helps to secure devices against web threats and protect users from phishing attacks.</span></span> <span data-ttu-id="bf196-121">Defender for Endpoint unter iOS verwendet ein VPN, um diesen Schutz zu gewährleisten.</span><span class="sxs-lookup"><span data-stu-id="bf196-121">Defender for Endpoint on iOS uses a VPN in order to provide this protection.</span></span> <span data-ttu-id="bf196-122">Beachten Sie, dass es sich um ein lokales VPN handelt und im Gegensatz zu herkömmlichem VPN kein Netzwerkdatenverkehr außerhalb des Geräts gesendet wird.</span><span class="sxs-lookup"><span data-stu-id="bf196-122">Please note this is a local VPN and unlike traditional VPN, network traffic is not sent outside the device.</span></span>

<span data-ttu-id="bf196-123">Obwohl standardmäßig aktiviert, kann es einige Fälle sein, in denen Sie VPN deaktivieren müssen.</span><span class="sxs-lookup"><span data-stu-id="bf196-123">While enabled by default, there might be some cases that require you to disable VPN.</span></span> <span data-ttu-id="bf196-124">Beispielsweise möchten Sie einige Apps ausführen, die nicht funktionieren, wenn ein VPN konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="bf196-124">For example, you want to run some apps that do not work when a VPN is configured.</span></span> <span data-ttu-id="bf196-125">In solchen Fällen können Sie vpn von der App auf dem Gerät deaktivieren, indem Sie die folgenden Schritte ausführen:</span><span class="sxs-lookup"><span data-stu-id="bf196-125">In such cases, you can choose to disable VPN from the app on the device by following the steps below:</span></span>

1. <span data-ttu-id="bf196-126">Öffnen Sie auf Ihrem **iOS-Gerät die Einstellungen** App, klicken oder tippen Sie auf **Allgemein** und dann **auf VPN.**</span><span class="sxs-lookup"><span data-stu-id="bf196-126">On your iOS device, open the **Settings** app, click or tap **General** and then **VPN**.</span></span>
1. <span data-ttu-id="bf196-127">Klicken oder tippen Sie auf die Schaltfläche "i" für Microsoft Defender for Endpoint.</span><span class="sxs-lookup"><span data-stu-id="bf196-127">Click or tap the "i" button for Microsoft Defender for Endpoint.</span></span>
1. <span data-ttu-id="bf196-128">Umschalten Verbinden **Bei Bedarf, um** VPN zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="bf196-128">Toggle off **Connect On Demand** to disable VPN.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="bf196-129">![VPN config connect on demand](images/ios-vpn-config.png)</span><span class="sxs-lookup"><span data-stu-id="bf196-129">![VPN config connect on demand](images/ios-vpn-config.png)</span></span>

> [!NOTE]
> <span data-ttu-id="bf196-130">Web Protection ist nicht verfügbar, wenn VPN deaktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="bf196-130">Web Protection will not be available when VPN is disabled.</span></span> <span data-ttu-id="bf196-131">Öffnen Sie zum erneuten Aktivieren von Web Protection die Microsoft Defender for Endpoint-App auf dem Gerät, und klicken oder tippen **Sie auf VPN starten.**</span><span class="sxs-lookup"><span data-stu-id="bf196-131">To re-enable Web Protection, open the Microsoft Defender for Endpoint app on the device and click or tap **Start VPN**.</span></span>

## <a name="co-existence-of-multiple-vpn-profiles"></a><span data-ttu-id="bf196-132">Koexistenz mehrerer VPN-Profile</span><span class="sxs-lookup"><span data-stu-id="bf196-132">Co-existence of multiple VPN profiles</span></span>

<span data-ttu-id="bf196-133">Apple iOS unterstützt nicht mehrere geräteweite VPNs, um gleichzeitig aktiv zu sein.</span><span class="sxs-lookup"><span data-stu-id="bf196-133">Apple iOS does not support multiple device-wide VPNs to be active simultaneously.</span></span> <span data-ttu-id="bf196-134">Auf dem Gerät können zwar mehrere VPN-Profile vorhanden sein, aber nur ein VPN kann gleichzeitig aktiv sein.</span><span class="sxs-lookup"><span data-stu-id="bf196-134">While multiple VPN profiles can exist on the device, only one VPN can be active at a time.</span></span>


## <a name="configure-compliance-policy-against-jailbroken-devices"></a><span data-ttu-id="bf196-135">Konfigurieren der Compliancerichtlinie für jailbrokene Geräte</span><span class="sxs-lookup"><span data-stu-id="bf196-135">Configure compliance policy against jailbroken devices</span></span>

<span data-ttu-id="bf196-136">Um den Zugriff auf Unternehmensdaten auf ins Jailbroken gebrokenen iOS-Geräten zu schützen, wird empfohlen, die folgende Compliancerichtlinie für Intune zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="bf196-136">To protect corporate data from being accessed on jailbroken iOS devices, we recommend that you set up the following compliance policy on Intune.</span></span>

> [!NOTE]
> <span data-ttu-id="bf196-137">Zurzeit befindet sich die Jailbreakerkennung durch Microsoft Defender for Endpoint unter iOS in der Vorschau.</span><span class="sxs-lookup"><span data-stu-id="bf196-137">At this time jailbreak detection by Microsoft Defender for Endpoint on iOS is in preview.</span></span> <span data-ttu-id="bf196-138">Es wird empfohlen, dass Sie diese Richtlinie als zusätzliche Schutzebene gegen Jailbreakszenarien einrichten.</span><span class="sxs-lookup"><span data-stu-id="bf196-138">We recommend that you setup this policy as an additional layer of defense against jailbreak scenarios.</span></span>

<span data-ttu-id="bf196-139">Führen Sie die folgenden Schritte aus, um eine Compliancerichtlinie für jailbrokene Geräte zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="bf196-139">Follow the steps below to create a compliance policy against jailbroken devices.</span></span>

1. <span data-ttu-id="bf196-140">Wechseln [Microsoft Endpoint Manager Admin Center](https://go.microsoft.com/fwlink/?linkid=2109431)zu Richtlinien zur **Gerätekonformität**  ->    ->  **Erstellen von Richtlinien**.</span><span class="sxs-lookup"><span data-stu-id="bf196-140">In [Microsoft Endpoint Manager admin center](https://go.microsoft.com/fwlink/?linkid=2109431), go to **Devices** -> **Compliance policies** -> **Create Policy**.</span></span> <span data-ttu-id="bf196-141">Wählen Sie "iOS/iPadOS" als Plattform aus, und klicken Sie auf **Erstellen**.</span><span class="sxs-lookup"><span data-stu-id="bf196-141">Select "iOS/iPadOS" as platform and click **Create**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="bf196-142">![Erstellen einer Richtlinie](images/ios-jb-policy.png)</span><span class="sxs-lookup"><span data-stu-id="bf196-142">![Create Policy](images/ios-jb-policy.png)</span></span>

2. <span data-ttu-id="bf196-143">Geben Sie einen Namen der Richtlinie an, z. B. "Compliancerichtlinie für Jailbreak".</span><span class="sxs-lookup"><span data-stu-id="bf196-143">Specify a name of the policy, for example "Compliance Policy for Jailbreak".</span></span>
3. <span data-ttu-id="bf196-144">Klicken Sie auf der Seite Kompatibilitätseinstellungen auf , um den Abschnitt **Geräteintektion** zu erweitern, und klicken Sie auf **Block** for **Jailbroken devices** field.</span><span class="sxs-lookup"><span data-stu-id="bf196-144">In the compliance settings page, click to expand **Device Health** section and click **Block** for **Jailbroken devices** field.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="bf196-145">![Richtlinien Einstellungen](images/ios-jb-settings.png)</span><span class="sxs-lookup"><span data-stu-id="bf196-145">![Policy Settings](images/ios-jb-settings.png)</span></span>

4. <span data-ttu-id="bf196-146">Wählen Sie *im Abschnitt Aktion* für Nichtkompatibilität die Aktionen nach Ihren Anforderungen aus, und wählen Sie Weiter **aus.**</span><span class="sxs-lookup"><span data-stu-id="bf196-146">In the *Action for noncompliance* section, select the actions as per your requirements and select **Next**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="bf196-147">![Richtlinienaktionen](images/ios-jb-actions.png)</span><span class="sxs-lookup"><span data-stu-id="bf196-147">![Policy Actions](images/ios-jb-actions.png)</span></span>

5. <span data-ttu-id="bf196-148">Wählen Sie *im Abschnitt Zuordnungen* die Benutzergruppen aus, die Sie für diese Richtlinie verwenden möchten, und wählen Sie dann **Weiter aus.**</span><span class="sxs-lookup"><span data-stu-id="bf196-148">In the *Assignments* section, select the user groups that you want to include for this policy and then select **Next**.</span></span>
6. <span data-ttu-id="bf196-149">Überprüfen Sie **im Abschnitt Überprüfen+Erstellen,** ob alle eingegebenen Informationen korrekt sind, und wählen Sie dann **Erstellen aus.**</span><span class="sxs-lookup"><span data-stu-id="bf196-149">In the **Review+Create** section, verify that all the information entered is correct and then select **Create**.</span></span>

## <a name="configure-custom-indicators"></a><span data-ttu-id="bf196-150">Konfigurieren benutzerdefinierter Indikatoren</span><span class="sxs-lookup"><span data-stu-id="bf196-150">Configure custom indicators</span></span>

<span data-ttu-id="bf196-151">Mit Defender for Endpoint unter iOS können Administratoren auch benutzerdefinierte Indikatoren auf iOS-Geräten konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="bf196-151">Defender for Endpoint on iOS enables admins to configure custom indicators on iOS devices as well.</span></span> <span data-ttu-id="bf196-152">Weitere Informationen zum Konfigurieren benutzerdefinierter Indikatoren finden Sie unter [Manage indicators](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/manage-indicators).</span><span class="sxs-lookup"><span data-stu-id="bf196-152">For more information on how to configure custom indicators, see [Manage indicators](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/manage-indicators).</span></span>

> [!NOTE]
> <span data-ttu-id="bf196-153">Defender for Endpoint unter iOS unterstützt das Erstellen benutzerdefinierter Indikatoren nur für IP-Adressen und URLs/Domänen.</span><span class="sxs-lookup"><span data-stu-id="bf196-153">Defender for Endpoint on iOS supports creating custom indicators only for IP addresses and URLs/domains.</span></span>

## <a name="report-unsafe-site"></a><span data-ttu-id="bf196-154">Unsichere Website melden</span><span class="sxs-lookup"><span data-stu-id="bf196-154">Report unsafe site</span></span>

<span data-ttu-id="bf196-155">Phishingwebsites geben sich als vertrauenswürdige Websites aus, um Ihre persönlichen oder finanziellen Informationen zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="bf196-155">Phishing websites impersonate trustworthy websites for the purpose of obtaining your personal or financial information.</span></span> <span data-ttu-id="bf196-156">Besuchen Sie [die Seite Feedback zum Netzwerkschutz](https://www.microsoft.com/wdsi/filesubmission/exploitguard/networkprotection) bereitstellen, wenn Sie eine Website melden möchten, bei der es sich um eine Phishingwebsite handelt.</span><span class="sxs-lookup"><span data-stu-id="bf196-156">Visit the [Provide feedback about network protection](https://www.microsoft.com/wdsi/filesubmission/exploitguard/networkprotection) page if you want to report a website that could be a phishing site.</span></span>

## <a name="battery-consumption-issues-on-ios-when-microsoft-defender-for-endpoint-is-installed"></a><span data-ttu-id="bf196-157">Probleme mit dem Akkuverbrauch unter iOS bei der Installation von Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="bf196-157">Battery Consumption issues on iOS when Microsoft Defender for Endpoint is installed</span></span>

<span data-ttu-id="bf196-158">Der Akkuverbrauch einer App wird von Apple basierend auf einer Vielzahl von Faktoren wie CPU- und Netzwerknutzung berechnet.</span><span class="sxs-lookup"><span data-stu-id="bf196-158">The battery usage by an app is computed by Apple based on a multitude of factors including CPU and Network usage.</span></span> <span data-ttu-id="bf196-159">Microsoft Defender for Endpoint verwendet ein lokales /Loop-Back-VPN im Hintergrund, um den Webdatenverkehr auf schädliche Websites oder Verbindungen zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="bf196-159">Microsoft Defender for Endpoint uses a local/loop-back VPN in the background to check web traffic for any malicious websites or connections.</span></span> <span data-ttu-id="bf196-160">Netzwerkpakete von jeder App durchgehen diese Prüfung, was dazu führt, dass der Akkuverbrauch von Microsoft Defender for Endpoint ungenau berechnet wird.</span><span class="sxs-lookup"><span data-stu-id="bf196-160">Network packets from any app go through this check and that causes the battery usage of Microsoft Defender for Endpoint to be computed inaccurately.</span></span> <span data-ttu-id="bf196-161">Dies gibt dem Benutzer einen falschen Eindruck.</span><span class="sxs-lookup"><span data-stu-id="bf196-161">This gives a false impression to the user.</span></span> <span data-ttu-id="bf196-162">Der tatsächliche Akkuverbrauch von Microsoft Defender for Endpoint ist geringer als der, der auf der Seite Battery Einstellungen auf dem Gerät angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="bf196-162">The actual battery consumption of Microsoft Defender for Endpoint is lesser than what is shown on the Battery Settings page on the device.</span></span> <span data-ttu-id="bf196-163">Dies basiert auf durchgeführten Tests, die mit der Microsoft Defender for Endpoint-App durchgeführt wurden, um den Akkuverbrauch zu verstehen.</span><span class="sxs-lookup"><span data-stu-id="bf196-163">This is based on conducted tests done on the Microsoft Defender for Endpoint app to understand battery consumption.</span></span>

<span data-ttu-id="bf196-164">Auch das verwendete VPN ist ein lokales VPN und im Gegensatz zu herkömmlichen VPNs wird der Netzwerkdatenverkehr nicht außerhalb des Geräts gesendet.</span><span class="sxs-lookup"><span data-stu-id="bf196-164">Also the VPN used is a local VPN and unlike traditional VPNs, network traffic is not sent outside the device.</span></span>
