---
title: Konfigurieren von Microsoft Defender für Endpunkt unter iOS-Features
description: Beschreibt, wie Microsoft Defender für Endpunkt unter iOS-Features bereitgestellt wird
keywords: Microsoft, Defender, Microsoft Defender für Endpunkt, ios, konfigurieren, Features, ios
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
ms.openlocfilehash: 749e03cb9d14476245baea82c21d322d4d726aad
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/30/2021
ms.locfileid: "53230007"
---
# <a name="configure-microsoft-defender-for-endpoint-on-ios-features"></a><span data-ttu-id="23a53-104">Konfigurieren von Microsoft Defender für Endpunkt unter iOS-Features</span><span class="sxs-lookup"><span data-stu-id="23a53-104">Configure Microsoft Defender for Endpoint on iOS features</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="23a53-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="23a53-105">**Applies to:**</span></span>
- [<span data-ttu-id="23a53-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="23a53-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="23a53-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="23a53-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="23a53-108">Möchten Sie Defender für Endpunkt erfahren?</span><span class="sxs-lookup"><span data-stu-id="23a53-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="23a53-109">Registrieren Sie sich für eine kostenlose Testversion</span><span class="sxs-lookup"><span data-stu-id="23a53-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

> [!NOTE]
> <span data-ttu-id="23a53-110">Defender für Endpunkt unter iOS würde ein VPN verwenden, um das Webschutzfeature bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="23a53-110">Defender for Endpoint on iOS would use a VPN in order to provide the Web Protection feature.</span></span> <span data-ttu-id="23a53-111">Dies ist kein reguläres VPN und ein lokales/selbstschleifendes VPN, das keinen Datenverkehr außerhalb des Geräts aufnimmt.</span><span class="sxs-lookup"><span data-stu-id="23a53-111">This is not a regular VPN and is a local/self-looping VPN that does not take traffic outside the device.</span></span>

## <a name="conditional-access-with-defender-for-endpoint-on-ios"></a><span data-ttu-id="23a53-112">Bedingter Zugriff mit Defender für Endpunkt unter iOS</span><span class="sxs-lookup"><span data-stu-id="23a53-112">Conditional Access with Defender for Endpoint on iOS</span></span>  
<span data-ttu-id="23a53-113">Microsoft Defender für Endpunkt unter iOS zusammen mit Microsoft Intune und Azure Active Directory ermöglicht das Erzwingen von Gerätecompliance und Richtlinien für bedingten Zugriff basierend auf der Geräterisikobewertung.</span><span class="sxs-lookup"><span data-stu-id="23a53-113">Microsoft Defender for Endpoint on iOS along with Microsoft Intune and Azure Active Directory enables enforcing Device compliance and Conditional Access policies based on device risk score.</span></span> <span data-ttu-id="23a53-114">Defender für Endpunkt ist eine MTD-Lösung (Mobile Threat Defense), die Sie bereitstellen können, um diese Funktion über Intune zu nutzen.</span><span class="sxs-lookup"><span data-stu-id="23a53-114">Defender for Endpoint is a Mobile Threat Defense (MTD) solution that you can deploy to leverage this capability via Intune.</span></span>

<span data-ttu-id="23a53-115">Weitere Informationen zum Einrichten des bedingten Zugriffs mit Defender für Endpunkt unter iOS finden Sie unter [Defender für Endpunkt und Intune.](/mem/intune/protect/advanced-threat-protection)</span><span class="sxs-lookup"><span data-stu-id="23a53-115">For more information about how to set up Conditional Access with Defender for Endpoint on iOS, see [Defender for Endpoint and Intune](/mem/intune/protect/advanced-threat-protection).</span></span>

### <a name="jailbreak-detection-by-microsoft-defender-for-endpoint"></a><span data-ttu-id="23a53-116">Jailbreak-Erkennung durch Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="23a53-116">Jailbreak detection by Microsoft Defender for Endpoint</span></span>
<span data-ttu-id="23a53-117">Microsoft Defender für Endpunkt verfügt über die Möglichkeit, nicht verwaltete und verwaltete Geräte zu erkennen, die ohne Jailbreak sind.</span><span class="sxs-lookup"><span data-stu-id="23a53-117">Microsoft Defender for Endpoint has the capability of detecting unmanaged and managed devices that are jailbroken.</span></span> <span data-ttu-id="23a53-118">Wenn festgestellt wird, dass ein Gerät im Jailbreak ist, wird eine Warnung mit **hohem** Risiko an das Security Center gemeldet. Wenn der bedingte Zugriff basierend auf der Geräterisikobewertung eingerichtet wird, wird der Zugriff auf Unternehmensdaten für das Gerät blockiert.</span><span class="sxs-lookup"><span data-stu-id="23a53-118">If a device is detected to be jailbroken, a **High**-risk alert will be reported to Security Center and if Conditional Access is setup based on device risk score, then the device will be blocked from accessing corporate data.</span></span>

## <a name="web-protection-and-vpn"></a><span data-ttu-id="23a53-119">Webschutz und VPN</span><span class="sxs-lookup"><span data-stu-id="23a53-119">Web Protection and VPN</span></span>

<span data-ttu-id="23a53-120">Standardmäßig enthält Defender für Endpunkt unter iOS das Webschutzfeature und aktiviert es.</span><span class="sxs-lookup"><span data-stu-id="23a53-120">By default, Defender for Endpoint on iOS includes and enables the web protection feature.</span></span> <span data-ttu-id="23a53-121">[Webschutz](web-protection-overview.md) hilft dabei, Geräte vor Webbedrohungen zu schützen und Benutzer vor Phishingangriffen zu schützen.</span><span class="sxs-lookup"><span data-stu-id="23a53-121">[Web protection](web-protection-overview.md) helps to secure devices against web threats and protect users from phishing attacks.</span></span> <span data-ttu-id="23a53-122">Defender für Endpunkt unter iOS verwendet ein VPN, um diesen Schutz bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="23a53-122">Defender for Endpoint on iOS uses a VPN in order to provide this protection.</span></span> <span data-ttu-id="23a53-123">Bitte beachten Sie, dass es sich um ein lokales VPN handelt und im Gegensatz zu herkömmlichem VPN kein Netzwerkdatenverkehr außerhalb des Geräts gesendet wird.</span><span class="sxs-lookup"><span data-stu-id="23a53-123">Please note this is a local VPN and unlike traditional VPN, network traffic is not sent outside the device.</span></span>

<span data-ttu-id="23a53-124">Obwohl sie standardmäßig aktiviert ist, kann es einige Fälle geben, in denen Sie VPN deaktivieren müssen.</span><span class="sxs-lookup"><span data-stu-id="23a53-124">While enabled by default, there might be some cases that require you to disable VPN.</span></span> <span data-ttu-id="23a53-125">Sie möchten beispielsweise einige Apps ausführen, die nicht funktionieren, wenn ein VPN konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="23a53-125">For example, you want to run some apps that do not work when a VPN is configured.</span></span> <span data-ttu-id="23a53-126">In solchen Fällen können Sie vpn von der App auf dem Gerät deaktivieren, indem Sie die folgenden Schritte ausführen:</span><span class="sxs-lookup"><span data-stu-id="23a53-126">In such cases, you can choose to disable VPN from the app on the device by following the steps below:</span></span>

1. <span data-ttu-id="23a53-127">Öffnen Sie auf Ihrem iOS-Gerät die **Einstellungen** App, klicken oder tippen Sie auf **"Allgemein"** und dann auf **"VPN".**</span><span class="sxs-lookup"><span data-stu-id="23a53-127">On your iOS device, open the **Settings** app, click or tap **General** and then **VPN**.</span></span>
1. <span data-ttu-id="23a53-128">Klicken oder tippen Sie auf die Schaltfläche "i" für Microsoft Defender für Endpunkt.</span><span class="sxs-lookup"><span data-stu-id="23a53-128">Click or tap the "i" button for Microsoft Defender for Endpoint.</span></span>
1. <span data-ttu-id="23a53-129">Schalten Sie **Verbinden bei Bedarf** aus, um VPN zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="23a53-129">Toggle off **Connect On Demand** to disable VPN.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="23a53-130">![VPN config connect on demand](images/ios-vpn-config.png)</span><span class="sxs-lookup"><span data-stu-id="23a53-130">![VPN config connect on demand](images/ios-vpn-config.png)</span></span>

> [!NOTE]
> <span data-ttu-id="23a53-131">Webschutz ist nicht verfügbar, wenn VPN deaktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="23a53-131">Web Protection will not be available when VPN is disabled.</span></span> <span data-ttu-id="23a53-132">Um Web Protection erneut zu aktivieren, öffnen Sie die Microsoft Defender für Endpunkt-App auf dem Gerät, und klicken oder tippen Sie auf **"VPN starten".**</span><span class="sxs-lookup"><span data-stu-id="23a53-132">To re-enable Web Protection, open the Microsoft Defender for Endpoint app on the device and click or tap **Start VPN**.</span></span>

## <a name="co-existence-of-multiple-vpn-profiles"></a><span data-ttu-id="23a53-133">Koexistenz mehrerer VPN-Profile</span><span class="sxs-lookup"><span data-stu-id="23a53-133">Co-existence of multiple VPN profiles</span></span>

<span data-ttu-id="23a53-134">Apple iOS unterstützt nicht, dass mehrere geräteweite VPNs gleichzeitig aktiv sind.</span><span class="sxs-lookup"><span data-stu-id="23a53-134">Apple iOS does not support multiple device-wide VPNs to be active simultaneously.</span></span> <span data-ttu-id="23a53-135">Während mehrere VPN-Profile auf dem Gerät vorhanden sein können, kann jeweils nur ein VPN aktiv sein.</span><span class="sxs-lookup"><span data-stu-id="23a53-135">While multiple VPN profiles can exist on the device, only one VPN can be active at a time.</span></span>

## <a name="configure-microsoft-defender-for-endpoint-risk-signal-in-app-protection-policy-mam"></a><span data-ttu-id="23a53-136">Konfigurieren des Microsoft Defender für Endpunkt-Risikosignals in der App-Schutzrichtlinie (MAM)</span><span class="sxs-lookup"><span data-stu-id="23a53-136">Configure Microsoft Defender for Endpoint risk signal in app protection policy (MAM)</span></span>

<span data-ttu-id="23a53-137">Microsoft Defender für Endpunkt kann so konfiguriert werden, dass Bedrohungssignale gesendet werden, die in App-Schutzrichtlinien (APP, auch als MAM bezeichnet) unter iOS/iPadOS verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="23a53-137">Microsoft Defender for Endpoint can be configured to send threat signals to be used in App Protection Policies (APP, also known as MAM) on iOS/iPadOS.</span></span> <span data-ttu-id="23a53-138">Mit dieser Funktion können Sie Microsoft Defender für Endpunkt verwenden, um den Zugriff auf Unternehmensdaten auch von nicht registrierungierten Geräten aus zu schützen.</span><span class="sxs-lookup"><span data-stu-id="23a53-138">With this capability, you can use Microsoft Defender for Endpoint to protect access to corporate data from unenrolled devices as well.</span></span>

<span data-ttu-id="23a53-139">Schritte zum Einrichten von App-Schutzrichtlinien mit Microsoft Defender für Endpunkt sind wie folgt:</span><span class="sxs-lookup"><span data-stu-id="23a53-139">Steps to setup app protection policies with Microsoft Defender for Endpoint are as below:</span></span>

1. <span data-ttu-id="23a53-140">Richten Sie die Verbindung von Ihrem Microsoft Endpoint Manager-Mandanten zu Microsoft Defender für Endpunkt ein.</span><span class="sxs-lookup"><span data-stu-id="23a53-140">Set up the connection from your Microsoft Endpoint Manager tenant to Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="23a53-141">Wechseln Sie [im Microsoft Endpoint Manager Admin Center](https://go.microsoft.com/fwlink/?linkid=2109431)zu **Mandantenverwaltungsconnectors**  >  **und -token**  >  **Microsoft Defender für Endpunkt** (plattformübergreifend) oder **Endpunktsicherheit**  >  **Microsoft Defender für Endpunkt** (unter Setup), und aktivieren Sie die Umschaltflächen unter **App-Schutzrichtlinie Einstellungen für iOS.**</span><span class="sxs-lookup"><span data-stu-id="23a53-141">In [Microsoft Endpoint manager admin center](https://go.microsoft.com/fwlink/?linkid=2109431), go to **Tenant Administration** > **Connectors and tokens** > **Microsoft Defender for Endpoint** (under Cross platform) or **Endpoint Security** > **Microsoft Defender for Endpoint** (under Setup) and turn on the toggles under **App Protection Policy Settings for iOS**.</span></span>
1. <span data-ttu-id="23a53-142">Wählen Sie "Speichern" aus.</span><span class="sxs-lookup"><span data-stu-id="23a53-142">Select Save.</span></span> <span data-ttu-id="23a53-143">Es sollte angezeigt werden, dass der **Verbindungsstatus** jetzt auf **"Aktiviert"** festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="23a53-143">You should see **Connection status** is now set to **Enabled**.</span></span>
1. <span data-ttu-id="23a53-144">Erstellen einer App-Schutzrichtlinie: Navigieren Sie nach Abschluss des Setups des Microsoft Defender für Endpunkt-Connectors zu **den**  >  **App-Schutzrichtlinien** (unter "Richtlinie"), um eine neue Richtlinie zu erstellen oder eine vorhandene zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="23a53-144">Create app protection policy: After your Microsoft Defender for Endpoint connector setup is complete, navigate to **Apps** > **App protection policies** (under Policy) to create a new policy or update an existing one.</span></span>
1. <span data-ttu-id="23a53-145">Wählen Sie die Plattform, **Apps, Datenschutz, Zugriffsanforderungseinstellungen aus,** die Ihre Organisation für Ihre Richtlinie benötigt.</span><span class="sxs-lookup"><span data-stu-id="23a53-145">Select the platform, **Apps, Data protection, Access requirements** settings that your organization requires for your policy.</span></span>
1. <span data-ttu-id="23a53-146">Unter Bedingungen des Geräts für **bedingten Start** finden Sie die Einstellung  >   **"Maximale Gerätegefährdungsstufe"**.</span><span class="sxs-lookup"><span data-stu-id="23a53-146">Under **Conditional launch** > **Device conditions**, you will find the setting **Max allowed device threat level**.</span></span> <span data-ttu-id="23a53-147">Dies muss entweder auf "Niedrig", "Mittel", "Hoch" oder "Gesichert" konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="23a53-147">This will need to be configured to either Low, Medium, High, or Secured.</span></span> <span data-ttu-id="23a53-148">Die verfügbaren Aktionen sind **"Zugriff blockieren"** oder **"Daten zurücksetzen".**</span><span class="sxs-lookup"><span data-stu-id="23a53-148">The actions available to you will be **Block access** or **Wipe data**.</span></span> <span data-ttu-id="23a53-149">Möglicherweise wird ein Informationsdialogfeld angezeigt, um sicherzustellen, dass Ihr Connector eingerichtet ist, bevor diese Einstellung wirksam wird.</span><span class="sxs-lookup"><span data-stu-id="23a53-149">You may see an informational dialog to make sure you have your connector set up prior to this setting take effect.</span></span> <span data-ttu-id="23a53-150">Wenn Ihr Connector bereits eingerichtet ist, können Sie dieses Dialogfeld ignorieren.</span><span class="sxs-lookup"><span data-stu-id="23a53-150">If your connector is already set up, you may ignore this dialog.</span></span>
1. <span data-ttu-id="23a53-151">Schließen Sie die Aufgaben ab, und speichern Sie Ihre Richtlinie.</span><span class="sxs-lookup"><span data-stu-id="23a53-151">Finish with Assignments and save your policy.</span></span>

<span data-ttu-id="23a53-152">Weitere Informationen zur MAM- oder App-Schutzrichtlinie finden Sie unter [iOS-App-Schutzrichtlinieneinstellungen.](/mem/intune/apps/app-protection-policy-settings-ios)</span><span class="sxs-lookup"><span data-stu-id="23a53-152">For more details on MAM or app protection policy, see [iOS app protection policy settings](/mem/intune/apps/app-protection-policy-settings-ios).</span></span>

### <a name="deploying-microsoft-defender-for-endpoint-for-mam-or-on-unenrolled-devices"></a><span data-ttu-id="23a53-153">Bereitstellen von Microsoft Defender für Endpunkt für MAM oder auf nicht angemeldeten Geräten</span><span class="sxs-lookup"><span data-stu-id="23a53-153">Deploying Microsoft Defender for Endpoint for MAM or on unenrolled devices</span></span>

<span data-ttu-id="23a53-154">Microsoft Defender für Endpunkt unter iOS aktiviert das App Protection Policy-Szenario und ist im Apple App Store verfügbar.</span><span class="sxs-lookup"><span data-stu-id="23a53-154">Microsoft Defender for Endpoint on iOS enables the App Protection Policy scenario and is available in the Apple app store.</span></span>

<span data-ttu-id="23a53-155">Endbenutzer sollten die neueste Version der App direkt aus dem Apple App Store installieren.</span><span class="sxs-lookup"><span data-stu-id="23a53-155">End-users should install the latest version of the app directly from the Apple app store.</span></span>

## <a name="configure-compliance-policy-against-jailbroken-devices"></a><span data-ttu-id="23a53-156">Konfigurieren der Compliancerichtlinie für Geräte mit Jailbreak</span><span class="sxs-lookup"><span data-stu-id="23a53-156">Configure compliance policy against jailbroken devices</span></span>

<span data-ttu-id="23a53-157">Um den Zugriff auf Unternehmensdaten auf iOS-Geräten mit Jailbreak zu schützen, empfehlen wir, dass Sie die folgende Compliancerichtlinie in Intune einrichten.</span><span class="sxs-lookup"><span data-stu-id="23a53-157">To protect corporate data from being accessed on jailbroken iOS devices, we recommend that you set up the following compliance policy on Intune.</span></span>

> [!NOTE]
> <span data-ttu-id="23a53-158">Die Jailbreak-Erkennung ist eine Funktion, die von Microsoft Defender für Endpunkt unter iOS bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="23a53-158">Jailbreak detection is a capability provided by Microsoft Defender for Endpoint on iOS.</span></span> <span data-ttu-id="23a53-159">Es wird jedoch empfohlen, diese Richtlinie als zusätzliche Schutzebene gegen Jailbreak-Szenarien einzurichten.</span><span class="sxs-lookup"><span data-stu-id="23a53-159">However, we recommend that you setup this policy as an additional layer of defense against jailbreak scenarios.</span></span>

<span data-ttu-id="23a53-160">Führen Sie die folgenden Schritte aus, um eine Compliancerichtlinie für Geräte mit Jailbreak zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="23a53-160">Follow the steps below to create a compliance policy against jailbroken devices.</span></span>

1. <span data-ttu-id="23a53-161">Wechseln [Sie in Microsoft Endpoint Manager Admin Center](https://go.microsoft.com/fwlink/?linkid=2109431)zu **"Gerätecompliancerichtlinien**  ->    ->  **erstellen".**</span><span class="sxs-lookup"><span data-stu-id="23a53-161">In [Microsoft Endpoint Manager admin center](https://go.microsoft.com/fwlink/?linkid=2109431), go to **Devices** -> **Compliance policies** -> **Create Policy**.</span></span> <span data-ttu-id="23a53-162">Wählen Sie "iOS/iPadOS" als Plattform aus, und klicken Sie auf **"Erstellen".**</span><span class="sxs-lookup"><span data-stu-id="23a53-162">Select "iOS/iPadOS" as platform and click **Create**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="23a53-163">![Richtlinie erstellen](images/ios-jb-policy.png)</span><span class="sxs-lookup"><span data-stu-id="23a53-163">![Create Policy](images/ios-jb-policy.png)</span></span>

2. <span data-ttu-id="23a53-164">Geben Sie einen Namen der Richtlinie an, z. B. "Compliancerichtlinie für Jailbreak".</span><span class="sxs-lookup"><span data-stu-id="23a53-164">Specify a name of the policy, for example "Compliance Policy for Jailbreak".</span></span>
3. <span data-ttu-id="23a53-165">Klicken Sie auf der Seite "Complianceeinstellungen" auf den Abschnitt **"Geräteintegrität",** und klicken Sie auf das Feld **"Für** **Jailbroken** blockieren".</span><span class="sxs-lookup"><span data-stu-id="23a53-165">In the compliance settings page, click to expand **Device Health** section and click **Block** for **Jailbroken devices** field.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="23a53-166">![Richtlinien-Einstellungen](images/ios-jb-settings.png)</span><span class="sxs-lookup"><span data-stu-id="23a53-166">![Policy Settings](images/ios-jb-settings.png)</span></span>

4. <span data-ttu-id="23a53-167">Wählen Sie im Abschnitt **"Aktion für Nichtkonformität"** die Aktionen gemäß Ihren Anforderungen aus, und wählen Sie **"Weiter"** aus.</span><span class="sxs-lookup"><span data-stu-id="23a53-167">In the **Action for noncompliance** section, select the actions as per your requirements and select **Next**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="23a53-168">![Richtlinienaktionen](images/ios-jb-actions.png)</span><span class="sxs-lookup"><span data-stu-id="23a53-168">![Policy Actions](images/ios-jb-actions.png)</span></span>

5. <span data-ttu-id="23a53-169">Wählen Sie im Abschnitt **"Aufgaben"** die Benutzergruppen aus, die Sie für diese Richtlinie einschließen möchten, und wählen Sie dann **"Weiter"** aus.</span><span class="sxs-lookup"><span data-stu-id="23a53-169">In the **Assignments** section, select the user groups that you want to include for this policy and then select **Next**.</span></span>
6. <span data-ttu-id="23a53-170">Überprüfen Sie im Abschnitt **"Überprüfen und Erstellen",** ob alle eingegebenen Informationen korrekt sind, und wählen Sie dann **"Erstellen"** aus.</span><span class="sxs-lookup"><span data-stu-id="23a53-170">In the **Review+Create** section, verify that all the information entered is correct and then select **Create**.</span></span>

## <a name="configure-custom-indicators"></a><span data-ttu-id="23a53-171">Konfigurieren von benutzerdefinierten Indikatoren</span><span class="sxs-lookup"><span data-stu-id="23a53-171">Configure custom indicators</span></span>

<span data-ttu-id="23a53-172">Mit Defender für Endpunkt unter iOS können Administratoren auch benutzerdefinierte Indikatoren auf iOS-Geräten konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="23a53-172">Defender for Endpoint on iOS enables admins to configure custom indicators on iOS devices as well.</span></span> <span data-ttu-id="23a53-173">Weitere Informationen zum Konfigurieren von benutzerdefinierten Indikatoren finden Sie unter [Verwalten von Indikatoren.](/microsoft-365/security/defender-endpoint/manage-indicators)</span><span class="sxs-lookup"><span data-stu-id="23a53-173">For more information on how to configure custom indicators, see [Manage indicators](/microsoft-365/security/defender-endpoint/manage-indicators).</span></span>

> [!NOTE]
> <span data-ttu-id="23a53-174">Defender für Endpunkt unter iOS unterstützt das Erstellen benutzerdefinierter Indikatoren nur für IP-Adressen und URLs/Domänen.</span><span class="sxs-lookup"><span data-stu-id="23a53-174">Defender for Endpoint on iOS supports creating custom indicators only for IP addresses and URLs/domains.</span></span>

## <a name="report-unsafe-site"></a><span data-ttu-id="23a53-175">Unsichere Website melden</span><span class="sxs-lookup"><span data-stu-id="23a53-175">Report unsafe site</span></span>

<span data-ttu-id="23a53-176">Phishing-Websites imitieren vertrauenswürdige Websites, um Ihre persönlichen oder finanziellen Informationen zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="23a53-176">Phishing websites impersonate trustworthy websites for the purpose of obtaining your personal or financial information.</span></span> <span data-ttu-id="23a53-177">Besuchen Sie die Seite ["Feedback zum Netzwerkschutz",](https://www.microsoft.com/wdsi/filesubmission/exploitguard/networkprotection) wenn Sie eine Website melden möchten, bei der es sich um eine Phishing-Website handeln könnte.</span><span class="sxs-lookup"><span data-stu-id="23a53-177">Visit the [Provide feedback about network protection](https://www.microsoft.com/wdsi/filesubmission/exploitguard/networkprotection) page if you want to report a website that could be a phishing site.</span></span>

