---
title: Netzwerkschutz aktivieren
description: Aktivieren Sie den Netzwerkschutz mit gruppenrichtlinien, PowerShell oder Mobile Device Management and Configuration Manager.
keywords: ANetwork-Schutz, Exploits, schädliche Website, IP, Domäne, Domänen, aktivieren, aktivieren
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
ms.topic: conceptual
author: dansimp
ms.author: dansimp
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: bde97638a39eef4561b898b2cf49e51bed6e77a5
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/14/2021
ms.locfileid: "52926655"
---
# <a name="turn-on-network-protection"></a><span data-ttu-id="c38bf-104">Netzwerkschutz aktivieren</span><span class="sxs-lookup"><span data-stu-id="c38bf-104">Turn on network protection</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="c38bf-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="c38bf-105">**Applies to:**</span></span>
- [<span data-ttu-id="c38bf-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="c38bf-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="c38bf-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c38bf-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!TIP]
> <span data-ttu-id="c38bf-108">Möchten Sie Defender für Endpunkt erleben?</span><span class="sxs-lookup"><span data-stu-id="c38bf-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="c38bf-109">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="c38bf-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

<span data-ttu-id="c38bf-110">[Der Netzwerkschutz](network-protection.md) verhindert, dass Mitarbeiter beliebige Anwendungen verwenden, um auf gefährliche Domänen zuzugreifen, die Phishing-Angriffe, Exploits und andere schädliche Inhalte im Internet hosten können.</span><span class="sxs-lookup"><span data-stu-id="c38bf-110">[Network protection](network-protection.md) helps to prevent employees from using any application to access dangerous domains that may host phishing scams, exploits, and other malicious content on the internet.</span></span> <span data-ttu-id="c38bf-111">Sie können [den Netzwerkschutz](evaluate-network-protection.md) in einer Testumgebung überwachen, um anzuzeigen, welche Apps blockiert werden, bevor Sie sie aktivieren.</span><span class="sxs-lookup"><span data-stu-id="c38bf-111">You can [audit network protection](evaluate-network-protection.md) in a test environment to view which apps would be blocked before you enable it.</span></span>

[<span data-ttu-id="c38bf-112">Weitere Informationen zu Konfigurationsoptionen für die Netzwerkfilterung</span><span class="sxs-lookup"><span data-stu-id="c38bf-112">Learn more about network filtering configuration options</span></span>](/mem/intune/protect/endpoint-protection-windows-10#network-filtering)

## <a name="check-if-network-protection-is-enabled"></a><span data-ttu-id="c38bf-113">Überprüfen, ob der Netzwerkschutz aktiviert ist</span><span class="sxs-lookup"><span data-stu-id="c38bf-113">Check if network protection is enabled</span></span>

<span data-ttu-id="c38bf-114">Überprüfen Sie mithilfe des Registrierungs-Editors, ob der Netzwerkschutz auf einem lokalen Gerät aktiviert wurde.</span><span class="sxs-lookup"><span data-stu-id="c38bf-114">Check if network protection has been enabled on a local device by using Registry editor.</span></span>

1. <span data-ttu-id="c38bf-115">Wählen Sie die **Schaltfläche "Start"** in der Taskleiste aus, und geben Sie **"regedit" ein,** um den Registrierungs-Editor zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="c38bf-115">Select the **Start** button in the task bar and type **regedit** to open Registry editor</span></span>

2. <span data-ttu-id="c38bf-116">HKEY_LOCAL_MACHINE  aus dem Seitenmenü auswählen</span><span class="sxs-lookup"><span data-stu-id="c38bf-116">Choose **HKEY_LOCAL_MACHINE** from the side menu</span></span>

3. <span data-ttu-id="c38bf-117">Navigieren Sie durch die geschachtelten Menüs zu **SOFTWARE**  >  **Microsoft**  >  **Windows Defender**  >  **Windows Defender Exploit Guard** Network  >  **Protection**</span><span class="sxs-lookup"><span data-stu-id="c38bf-117">Navigate through the nested menus to **SOFTWARE** > **Microsoft** > **Windows Defender** > **Windows Defender Exploit Guard** > **Network Protection**</span></span>

4. <span data-ttu-id="c38bf-118">Wählen Sie **"EnableNetworkProtection" aus,** um den aktuellen Status des Netzwerkschutzes auf dem Gerät anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="c38bf-118">Select **EnableNetworkProtection** to see the current state of network protection on the device</span></span>

    * <span data-ttu-id="c38bf-119">0 oder **aus**</span><span class="sxs-lookup"><span data-stu-id="c38bf-119">0, or **Off**</span></span>
    * <span data-ttu-id="c38bf-120">1 oder **ein**</span><span class="sxs-lookup"><span data-stu-id="c38bf-120">1, or **On**</span></span>
    * <span data-ttu-id="c38bf-121">2 oder **Überwachungsmodus**</span><span class="sxs-lookup"><span data-stu-id="c38bf-121">2, or **Audit** mode</span></span>
    
    ![networkprotection](https://user-images.githubusercontent.com/3296790/95341270-b738b280-08d3-11eb-84a0-16abb140c9fd.PNG)

## <a name="enable-network-protection"></a><span data-ttu-id="c38bf-123">Netzwerkschutz aktivieren</span><span class="sxs-lookup"><span data-stu-id="c38bf-123">Enable network protection</span></span>

<span data-ttu-id="c38bf-124">Aktivieren Sie den Netzwerkschutz mithilfe einer der folgenden Methoden:</span><span class="sxs-lookup"><span data-stu-id="c38bf-124">Enable network protection by using any of these methods:</span></span>

* [<span data-ttu-id="c38bf-125">PowerShell</span><span class="sxs-lookup"><span data-stu-id="c38bf-125">PowerShell</span></span>](#powershell)
* [<span data-ttu-id="c38bf-126">Verwaltung mobiler Geräte (Mobile Device Management, MDM)</span><span class="sxs-lookup"><span data-stu-id="c38bf-126">Mobile Device Management (MDM)</span></span>](#mobile-device-management-mdm)
* [<span data-ttu-id="c38bf-127">Microsoft Endpoint Manager/Intune</span><span class="sxs-lookup"><span data-stu-id="c38bf-127">Microsoft Endpoint Manager / Intune</span></span>](#microsoft-endpoint-manager-formerly-intune)
* [<span data-ttu-id="c38bf-128">Gruppenrichtlinie</span><span class="sxs-lookup"><span data-stu-id="c38bf-128">Group Policy</span></span>](#group-policy)

### <a name="powershell"></a><span data-ttu-id="c38bf-129">PowerShell</span><span class="sxs-lookup"><span data-stu-id="c38bf-129">PowerShell</span></span>

1. <span data-ttu-id="c38bf-130">Geben Sie **PowerShell** im Startmenü ein, klicken Sie mit der rechten Maustaste auf **Windows PowerShell,** und wählen Sie **"Als Administrator ausführen"** aus.</span><span class="sxs-lookup"><span data-stu-id="c38bf-130">Type **powershell** in the Start menu, right-click **Windows PowerShell** and select **Run as administrator**</span></span>
2. <span data-ttu-id="c38bf-131">Geben Sie das folgende Cmdlet ein:</span><span class="sxs-lookup"><span data-stu-id="c38bf-131">Enter the following cmdlet:</span></span>

    ```PowerShell
    Set-MpPreference -EnableNetworkProtection Enabled
    ```

3. <span data-ttu-id="c38bf-132">Optional: Aktivieren Sie das Feature im Überwachungsmodus mit dem folgenden Cmdlet:</span><span class="sxs-lookup"><span data-stu-id="c38bf-132">Optional: Enable the feature in audit mode using the following cmdlet:</span></span>

    ```PowerShell
    Set-MpPreference -EnableNetworkProtection AuditMode
    ```

    <span data-ttu-id="c38bf-133">Verwenden Sie das Feature anstelle oder deaktivieren Sie `Disabled` `AuditMode` `Enabled` es.</span><span class="sxs-lookup"><span data-stu-id="c38bf-133">Use `Disabled` instead of `AuditMode` or `Enabled` to turn off the feature.</span></span>

### <a name="mobile-device-management-mdm"></a><span data-ttu-id="c38bf-134">Mobile Geräteverwaltung (MDM)</span><span class="sxs-lookup"><span data-stu-id="c38bf-134">Mobile device management (MDM)</span></span>

<span data-ttu-id="c38bf-135">Verwenden Sie [den Konfigurationsdienstanbieter ./Vendor/MSFT/Policy/Config/Defender/EnableNetworkProtection](/windows/client-management/mdm/policy-csp-defender) (CSP), um den Netzwerkschutz zu aktivieren oder zu deaktivieren oder den Überwachungsmodus zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="c38bf-135">Use the [./Vendor/MSFT/Policy/Config/Defender/EnableNetworkProtection](/windows/client-management/mdm/policy-csp-defender) configuration service provider (CSP) to enable or disable network protection or enable audit mode.</span></span>

### <a name="microsoft-endpoint-manager-formerly-intune"></a><span data-ttu-id="c38bf-136">Microsoft Endpoint Manager (früher Intune)</span><span class="sxs-lookup"><span data-stu-id="c38bf-136">Microsoft Endpoint Manager (formerly Intune)</span></span>

1. <span data-ttu-id="c38bf-137">Melden Sie sich beim Microsoft Endpoint Manager Admin Center an (https://endpoint.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="c38bf-137">Sign into the Microsoft Endpoint Manager admin center (https://endpoint.microsoft.com)</span></span>

2. <span data-ttu-id="c38bf-138">Erstellen oder Bearbeiten eines [Endpunktschutz-Konfigurationsprofils](/mem/intune/protect/endpoint-protection-configure)</span><span class="sxs-lookup"><span data-stu-id="c38bf-138">Create or edit an [endpoint protection configuration profile](/mem/intune/protect/endpoint-protection-configure)</span></span>

3. <span data-ttu-id="c38bf-139">Wechseln Sie unter **"Konfiguration Einstellungen** im Profilfluss" zu **Microsoft Defender Exploit Guard**  >  **Netzwerkfilterungsnetzwerkschutz**  >    >   aktivieren oder **nur überwachen**</span><span class="sxs-lookup"><span data-stu-id="c38bf-139">Under **Configuration Settings** in the profile flow, go to **Microsoft Defender Exploit Guard** > **Network filtering** > **Network protection** > **Enable** or **Audit only**</span></span>

### <a name="group-policy"></a><span data-ttu-id="c38bf-140">Gruppenrichtlinien</span><span class="sxs-lookup"><span data-stu-id="c38bf-140">Group Policy</span></span>

<span data-ttu-id="c38bf-141">Verwenden Sie das folgende Verfahren, um den Netzwerkschutz auf Computern zu aktivieren, die einer Domäne beigetreten sind, oder auf einem eigenständigen Computer.</span><span class="sxs-lookup"><span data-stu-id="c38bf-141">Use the following procedure to enable network protection on domain-joined computers or on a standalone computer.</span></span>

1. <span data-ttu-id="c38bf-142">Wechseln Sie auf einem eigenständigen Computer zu **"Start",** geben Sie die Gruppenrichtlinie ein, und wählen Sie sie **aus.**</span><span class="sxs-lookup"><span data-stu-id="c38bf-142">On a standalone computer, go to **Start** and then type and select **Edit group policy**.</span></span>

    <span data-ttu-id="c38bf-143">*-Or-*</span><span class="sxs-lookup"><span data-stu-id="c38bf-143">*-Or-*</span></span>

    <span data-ttu-id="c38bf-144">Öffnen Sie auf einem in die Domäne eingebundenen Computer für die Gruppenrichtlinienverwaltung die [Gruppenrichtlinien-Verwaltungskonsole,](https://technet.microsoft.com/library/cc731212.aspx)klicken Sie mit der rechten Maustaste auf das Gruppenrichtlinienobjekt, das Sie konfigurieren möchten, und wählen Sie **Bearbeiten** aus.</span><span class="sxs-lookup"><span data-stu-id="c38bf-144">On a domain-joined Group Policy management computer, open the [Group Policy Management Console](https://technet.microsoft.com/library/cc731212.aspx), right-click the Group Policy Object you want to configure and select **Edit**.</span></span>

2. <span data-ttu-id="c38bf-145">Wechseln Sie im **Gruppenrichtlinien-Verwaltungs-Editor** zu **Computerkonfiguration**, und wählen Sie **Administrative Vorlagen** aus.</span><span class="sxs-lookup"><span data-stu-id="c38bf-145">In the **Group Policy Management Editor**, go to **Computer configuration** and select **Administrative templates**.</span></span>

3. <span data-ttu-id="c38bf-146">Erweitern Sie die Struktur bis **Windows Komponenten**  >  **Microsoft Defender Antivirus**  >  **Windows Defender Exploit**  >  **Guard-Netzwerkschutz.**</span><span class="sxs-lookup"><span data-stu-id="c38bf-146">Expand the tree to **Windows components** > **Microsoft Defender Antivirus** > **Windows Defender Exploit Guard** > **Network protection**.</span></span>

> [!NOTE]
> <span data-ttu-id="c38bf-147">In älteren Versionen von Windows kann der Gruppenrichtlinienpfad "Windows Defender Antivirus" anstelle von "Microsoft Defender Antivirus" sagen.</span><span class="sxs-lookup"><span data-stu-id="c38bf-147">On older versions of Windows, the group policy path may say "Windows Defender Antivirus" instead of "Microsoft Defender Antivirus."</span></span>

4. <span data-ttu-id="c38bf-148">Doppelklicken Sie auf die Einstellung **"Benutzer und Apps am Zugriff auf gefährliche Websites** hindern", und legen Sie die Option auf **"Aktiviert"** fest.</span><span class="sxs-lookup"><span data-stu-id="c38bf-148">Double-click the **Prevent users and apps from accessing dangerous websites** setting and set the option to **Enabled**.</span></span> <span data-ttu-id="c38bf-149">Im Abschnitt "Optionen" müssen Sie eine der folgenden Optionen angeben:</span><span class="sxs-lookup"><span data-stu-id="c38bf-149">In the options section, you must specify one of the following options:</span></span>
    * <span data-ttu-id="c38bf-150">**Blockieren** – Benutzer können nicht auf schädliche IP-Adressen und Domänen zugreifen</span><span class="sxs-lookup"><span data-stu-id="c38bf-150">**Block** - Users can't access malicious IP addresses and domains</span></span>
    * <span data-ttu-id="c38bf-151">**Deaktivieren (Standard):** Das Netzwerkschutzfeature funktioniert nicht.</span><span class="sxs-lookup"><span data-stu-id="c38bf-151">**Disable (Default)** - The Network protection feature won't work.</span></span> <span data-ttu-id="c38bf-152">Benutzer werden nicht am Zugriff auf schädliche Domänen gehindert</span><span class="sxs-lookup"><span data-stu-id="c38bf-152">Users won't be blocked from accessing malicious domains</span></span>
    * <span data-ttu-id="c38bf-153">**Überwachungsmodus:** Wenn ein Benutzer eine schädliche IP-Adresse oder Domäne besucht, wird ein Ereignis im Windows-Ereignisprotokoll aufgezeichnet.</span><span class="sxs-lookup"><span data-stu-id="c38bf-153">**Audit Mode** - If a user visits a malicious IP address or domain, an event will be recorded in the Windows event log.</span></span> <span data-ttu-id="c38bf-154">Der Benutzer wird jedoch nicht daran gehindert, die Adresse zu besuchen.</span><span class="sxs-lookup"><span data-stu-id="c38bf-154">However, the user won't be blocked from visiting the address.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c38bf-155">Um den Netzwerkschutz vollständig zu aktivieren, müssen Sie die Gruppenrichtlinienoption auf **"Aktiviert"** festlegen und im Dropdownmenü "Optionen" die Option **"Blockieren"** auswählen.</span><span class="sxs-lookup"><span data-stu-id="c38bf-155">To fully enable network protection, you must set the Group Policy option to **Enabled** and also select **Block** in the options drop-down menu.</span></span>

<span data-ttu-id="c38bf-156">Stellen Sie sicher, dass der Netzwerkschutz auf einem lokalen Computer mithilfe des Registrierungs-Editors aktiviert ist:</span><span class="sxs-lookup"><span data-stu-id="c38bf-156">Confirm network protection is enabled on a local computer by using Registry editor:</span></span>

1. <span data-ttu-id="c38bf-157">Wählen Sie **"Start"** aus, und geben Sie **"regedit" ein,** um den **Registrierungs-Editor** zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="c38bf-157">Select **Start** and type **regedit** to open **Registry Editor**.</span></span>

2. <span data-ttu-id="c38bf-158">Navigieren Sie zu **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows Defender\Windows Defender Exploit Guard\Network Protection\EnableNetworkProtection**</span><span class="sxs-lookup"><span data-stu-id="c38bf-158">Navigate to **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows Defender\Windows Defender Exploit Guard\Network Protection\EnableNetworkProtection**</span></span>

3. <span data-ttu-id="c38bf-159">Wählen Sie **"EnableNetworkProtection" aus,** und bestätigen Sie den Wert:</span><span class="sxs-lookup"><span data-stu-id="c38bf-159">Select **EnableNetworkProtection** and confirm the value:</span></span>
   * <span data-ttu-id="c38bf-160">0=Aus</span><span class="sxs-lookup"><span data-stu-id="c38bf-160">0=Off</span></span>
   * <span data-ttu-id="c38bf-161">1=Ein</span><span class="sxs-lookup"><span data-stu-id="c38bf-161">1=On</span></span>
   * <span data-ttu-id="c38bf-162">2=Überwachung</span><span class="sxs-lookup"><span data-stu-id="c38bf-162">2=Audit</span></span>

## <a name="see-also"></a><span data-ttu-id="c38bf-163">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c38bf-163">See also</span></span>

* [<span data-ttu-id="c38bf-164">Netzwerkschutz</span><span class="sxs-lookup"><span data-stu-id="c38bf-164">Network protection</span></span>](network-protection.md)
* [<span data-ttu-id="c38bf-165">Auswerten des Netzwerkschutzes</span><span class="sxs-lookup"><span data-stu-id="c38bf-165">Evaluate network protection</span></span>](evaluate-network-protection.md)
* [<span data-ttu-id="c38bf-166">Problembehandlung beim Netzwerkschutz</span><span class="sxs-lookup"><span data-stu-id="c38bf-166">Troubleshoot network protection</span></span>](troubleshoot-np.md)
