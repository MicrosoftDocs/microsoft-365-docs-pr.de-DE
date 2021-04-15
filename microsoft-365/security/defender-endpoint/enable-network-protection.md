---
title: Netzwerkschutz aktivieren
description: Aktivieren Sie den Netzwerkschutz mit Gruppenrichtlinien, PowerShell oder Mobile Device Management and Configuration Manager.
keywords: ANetwork-Schutz, Exploits, schädliche Website, IP, Domäne, Domänen, aktivieren, aktivieren
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: dansimp
ms.author: dansimp
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 5c7a2d943ec1813623065e70330b914a3911d1eb
ms.sourcegitcommit: 4acf613587128cae27e0fd470d1216b509775529
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/15/2021
ms.locfileid: "51768998"
---
# <a name="turn-on-network-protection"></a><span data-ttu-id="6fddb-104">Netzwerkschutz aktivieren</span><span class="sxs-lookup"><span data-stu-id="6fddb-104">Turn on network protection</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="6fddb-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="6fddb-105">**Applies to:**</span></span>
- [<span data-ttu-id="6fddb-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="6fddb-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="6fddb-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="6fddb-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!TIP]
> <span data-ttu-id="6fddb-108">Möchten Sie Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="6fddb-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="6fddb-109">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="6fddb-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

<span data-ttu-id="6fddb-110">[Der Netzwerkschutz](network-protection.md) verhindert, dass Mitarbeiter eine Anwendung verwenden, um auf gefährliche Domänen zu zugreifen, die Phishingbetrüger, Exploits und andere schädliche Inhalte im Internet hosten können.</span><span class="sxs-lookup"><span data-stu-id="6fddb-110">[Network protection](network-protection.md) helps to prevent employees from using any application to access dangerous domains that may host phishing scams, exploits, and other malicious content on the internet.</span></span> <span data-ttu-id="6fddb-111">Sie können [den Netzwerkschutz](evaluate-network-protection.md) in einer Testumgebung überwachen, um zu sehen, welche Apps blockiert werden, bevor Sie ihn aktivieren.</span><span class="sxs-lookup"><span data-stu-id="6fddb-111">You can [audit network protection](evaluate-network-protection.md) in a test environment to view which apps would be blocked before you enable it.</span></span>

[<span data-ttu-id="6fddb-112">Weitere Informationen zu Konfigurationsoptionen für die Netzwerkfilterung</span><span class="sxs-lookup"><span data-stu-id="6fddb-112">Learn more about network filtering configuration options</span></span>](/mem/intune/protect/endpoint-protection-windows-10#network-filtering)

## <a name="check-if-network-protection-is-enabled"></a><span data-ttu-id="6fddb-113">Überprüfen, ob der Netzwerkschutz aktiviert ist</span><span class="sxs-lookup"><span data-stu-id="6fddb-113">Check if network protection is enabled</span></span>

<span data-ttu-id="6fddb-114">Überprüfen Sie mithilfe des Registrierungs-Editors, ob der Netzwerkschutz auf einem lokalen Gerät aktiviert wurde.</span><span class="sxs-lookup"><span data-stu-id="6fddb-114">Check if network protection has been enabled on a local device by using Registry editor.</span></span>

1. <span data-ttu-id="6fddb-115">Wählen Sie die **Schaltfläche Start** in der Aufgabenleiste aus, und geben Sie **regedit ein,** um den Registrierungs-Editor zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="6fddb-115">Select the **Start** button in the task bar and type **regedit** to open Registry editor</span></span>

2. <span data-ttu-id="6fddb-116">Wählen **HKEY_LOCAL_MACHINE** im Seitenmenü aus</span><span class="sxs-lookup"><span data-stu-id="6fddb-116">Choose **HKEY_LOCAL_MACHINE** from the side menu</span></span>

3. <span data-ttu-id="6fddb-117">Navigieren Sie durch die geschachtelten Menüs zu  >  **SOFTWARERichtlinien**  >  **Microsoft**  >  **Windows Defender**  >  **Windows Defender Exploit Guard** Network  >  **Protection**</span><span class="sxs-lookup"><span data-stu-id="6fddb-117">Navigate through the nested menus to **SOFTWARE** > **Policies** > **Microsoft** > **Windows Defender** > **Windows Defender Exploit Guard** > **Network Protection**</span></span>

4. <span data-ttu-id="6fddb-118">Wählen **Sie EnableNetworkProtection** aus, um den aktuellen Status des Netzwerkschutzes auf dem Gerät zu sehen.</span><span class="sxs-lookup"><span data-stu-id="6fddb-118">Select **EnableNetworkProtection** to see the current state of network protection on the device</span></span>

    * <span data-ttu-id="6fddb-119">0 oder **Aus**</span><span class="sxs-lookup"><span data-stu-id="6fddb-119">0, or **Off**</span></span>
    * <span data-ttu-id="6fddb-120">1 oder **Ein**</span><span class="sxs-lookup"><span data-stu-id="6fddb-120">1, or **On**</span></span>
    * <span data-ttu-id="6fddb-121">2 oder **Überwachungsmodus**</span><span class="sxs-lookup"><span data-stu-id="6fddb-121">2, or **Audit** mode</span></span>
    
    ![networkprotection](https://user-images.githubusercontent.com/3296790/95341270-b738b280-08d3-11eb-84a0-16abb140c9fd.PNG)

## <a name="enable-network-protection"></a><span data-ttu-id="6fddb-123">Aktivieren des Netzwerkschutzes</span><span class="sxs-lookup"><span data-stu-id="6fddb-123">Enable network protection</span></span>

<span data-ttu-id="6fddb-124">Aktivieren sie den Netzwerkschutz mithilfe einer der folgenden Methoden:</span><span class="sxs-lookup"><span data-stu-id="6fddb-124">Enable network protection by using any of these methods:</span></span>

* [<span data-ttu-id="6fddb-125">PowerShell</span><span class="sxs-lookup"><span data-stu-id="6fddb-125">PowerShell</span></span>](#powershell)
* [<span data-ttu-id="6fddb-126">Mobile Geräteverwaltung (MDM)</span><span class="sxs-lookup"><span data-stu-id="6fddb-126">Mobile Device Management (MDM)</span></span>](#mobile-device-management-mdm)
* [<span data-ttu-id="6fddb-127">Microsoft Endpoint Manager / Intune</span><span class="sxs-lookup"><span data-stu-id="6fddb-127">Microsoft Endpoint Manager / Intune</span></span>](#microsoft-endpoint-manager-formerly-intune)
* [<span data-ttu-id="6fddb-128">Gruppenrichtlinie</span><span class="sxs-lookup"><span data-stu-id="6fddb-128">Group Policy</span></span>](#group-policy)

### <a name="powershell"></a><span data-ttu-id="6fddb-129">PowerShell</span><span class="sxs-lookup"><span data-stu-id="6fddb-129">PowerShell</span></span>

1. <span data-ttu-id="6fddb-130">Geben **Sie powershell** im Menü Start ein, klicken Sie mit der rechten **maustaste Windows PowerShell** und wählen Sie Als Administrator ausführen **aus.**</span><span class="sxs-lookup"><span data-stu-id="6fddb-130">Type **powershell** in the Start menu, right-click **Windows PowerShell** and select **Run as administrator**</span></span>
2. <span data-ttu-id="6fddb-131">Geben Sie das folgende Cmdlet ein:</span><span class="sxs-lookup"><span data-stu-id="6fddb-131">Enter the following cmdlet:</span></span>

    ```PowerShell
    Set-MpPreference -EnableNetworkProtection Enabled
    ```

3. <span data-ttu-id="6fddb-132">Optional: Aktivieren Sie das Feature im Überwachungsmodus mithilfe des folgenden Cmdlets:</span><span class="sxs-lookup"><span data-stu-id="6fddb-132">Optional: Enable the feature in audit mode using the following cmdlet:</span></span>

    ```PowerShell
    Set-MpPreference -EnableNetworkProtection AuditMode
    ```

    <span data-ttu-id="6fddb-133">Verwenden `Disabled` Sie anstelle oder deaktivieren Sie das `AuditMode` `Enabled` Feature.</span><span class="sxs-lookup"><span data-stu-id="6fddb-133">Use `Disabled` instead of `AuditMode` or `Enabled` to turn off the feature.</span></span>

### <a name="mobile-device-management-mdm"></a><span data-ttu-id="6fddb-134">Verwaltung mobiler Geräte (Mobile Device Management, MDM)</span><span class="sxs-lookup"><span data-stu-id="6fddb-134">Mobile device management (MDM)</span></span>

<span data-ttu-id="6fddb-135">Verwenden Sie [den ./Vendor/MSFT/Policy/Config/Defender/EnableNetworkProtection](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-enablenetworkprotection) Configuration Service Provider (CSP), um den Netzwerkschutz zu aktivieren oder zu deaktivieren oder den Überwachungsmodus zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="6fddb-135">Use the [./Vendor/MSFT/Policy/Config/Defender/EnableNetworkProtection](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-enablenetworkprotection) configuration service provider (CSP) to enable or disable network protection or enable audit mode.</span></span>

### <a name="microsoft-endpoint-manager-formerly-intune"></a><span data-ttu-id="6fddb-136">Microsoft Endpoint Manager (früher Intune)</span><span class="sxs-lookup"><span data-stu-id="6fddb-136">Microsoft Endpoint Manager (formerly Intune)</span></span>

1. <span data-ttu-id="6fddb-137">Melden Sie sich beim Microsoft Endpoint Manager Admin Center an (https://endpoint.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="6fddb-137">Sign into the Microsoft Endpoint Manager admin center (https://endpoint.microsoft.com)</span></span>

2. <span data-ttu-id="6fddb-138">Erstellen oder Bearbeiten eines [Konfigurationsprofils für den Endpunktschutz](/mem/intune/protect/endpoint-protection-configure)</span><span class="sxs-lookup"><span data-stu-id="6fddb-138">Create or edit an [endpoint protection configuration profile](/mem/intune/protect/endpoint-protection-configure)</span></span>

3. <span data-ttu-id="6fddb-139">Wechseln **Sie unter Konfigurationseinstellungen** im Profilfluss zu **Microsoft Defender Exploit Guard** Network  >  **filtering**  >  **Network Protection**  >  **Enable** or **Audit only**</span><span class="sxs-lookup"><span data-stu-id="6fddb-139">Under **Configuration Settings** in the profile flow, go to **Microsoft Defender Exploit Guard** > **Network filtering** > **Network protection** > **Enable** or **Audit only**</span></span>

### <a name="group-policy"></a><span data-ttu-id="6fddb-140">Gruppenrichtlinien</span><span class="sxs-lookup"><span data-stu-id="6fddb-140">Group Policy</span></span>

<span data-ttu-id="6fddb-141">Verwenden Sie das folgende Verfahren, um den Netzwerkschutz auf Computern mit Domänenverbindung oder auf einem eigenständigen Computer zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="6fddb-141">Use the following procedure to enable network protection on domain-joined computers or on a standalone computer.</span></span>

1. <span data-ttu-id="6fddb-142">Wechseln Sie auf einem eigenständigen Computer zu **Start,** und geben Sie dann Gruppenrichtlinie **bearbeiten ein.**</span><span class="sxs-lookup"><span data-stu-id="6fddb-142">On a standalone computer, go to **Start** and then type and select **Edit group policy**.</span></span>

    <span data-ttu-id="6fddb-143">*-Or-*</span><span class="sxs-lookup"><span data-stu-id="6fddb-143">*-Or-*</span></span>

    <span data-ttu-id="6fddb-144">Öffnen Sie auf einem In der [](https://technet.microsoft.com/library/cc731212.aspx)Domäne beigetretenen Gruppenrichtlinienverwaltungscomputer die Gruppenrichtlinienverwaltungskonsole, klicken Sie mit der rechten Maustaste auf das Gruppenrichtlinienobjekt, das Sie konfigurieren möchten, und wählen Sie **Bearbeiten aus.**</span><span class="sxs-lookup"><span data-stu-id="6fddb-144">On a domain-joined Group Policy management computer, open the [Group Policy Management Console](https://technet.microsoft.com/library/cc731212.aspx), right-click the Group Policy Object you want to configure and select **Edit**.</span></span>

2. <span data-ttu-id="6fddb-145">Wechseln Sie **im Gruppenrichtlinienverwaltungs-Editor** zu **Computerkonfiguration,** und wählen Sie **Administrative Vorlagen aus.**</span><span class="sxs-lookup"><span data-stu-id="6fddb-145">In the **Group Policy Management Editor**, go to **Computer configuration** and select **Administrative templates**.</span></span>

3. <span data-ttu-id="6fddb-146">Erweitern Sie die Struktur **auf Windows-Komponenten**  >  **Microsoft Defender Antivirus** Windows Defender Exploit  >  **Guard** Network  >  **Protection**.</span><span class="sxs-lookup"><span data-stu-id="6fddb-146">Expand the tree to **Windows components** > **Microsoft Defender Antivirus** > **Windows Defender Exploit Guard** > **Network protection**.</span></span>

> [!NOTE]
> <span data-ttu-id="6fddb-147">Bei älteren Versionen von Windows kann der Gruppenrichtlinienpfad "Windows Defender Antivirus" anstelle von "Microsoft Defender Antivirus" sagen.</span><span class="sxs-lookup"><span data-stu-id="6fddb-147">On older versions of Windows, the group policy path may say "Windows Defender Antivirus" instead of "Microsoft Defender Antivirus."</span></span>

4. <span data-ttu-id="6fddb-148">Doppelklicken Sie auf die Einstellung Benutzer **und Apps am** Zugriff auf gefährliche Websites hindern, und legen Sie die Option auf Aktiviert **.**</span><span class="sxs-lookup"><span data-stu-id="6fddb-148">Double-click the **Prevent users and apps from accessing dangerous websites** setting and set the option to **Enabled**.</span></span> <span data-ttu-id="6fddb-149">Im Abschnitt Optionen müssen Sie eine der folgenden Optionen angeben:</span><span class="sxs-lookup"><span data-stu-id="6fddb-149">In the options section, you must specify one of the following options:</span></span>
    * <span data-ttu-id="6fddb-150">**Blockieren** – Benutzer können nicht auf schädliche IP-Adressen und Domänen zugreifen</span><span class="sxs-lookup"><span data-stu-id="6fddb-150">**Block** - Users can't access malicious IP addresses and domains</span></span>
    * <span data-ttu-id="6fddb-151">**Disable (Standard)** – Das Netzwerkschutzfeature funktioniert nicht.</span><span class="sxs-lookup"><span data-stu-id="6fddb-151">**Disable (Default)** - The Network protection feature won't work.</span></span> <span data-ttu-id="6fddb-152">Benutzer werden nicht am Zugriff auf schädliche Domänen blockiert</span><span class="sxs-lookup"><span data-stu-id="6fddb-152">Users won't be blocked from accessing malicious domains</span></span>
    * <span data-ttu-id="6fddb-153">**Überwachungsmodus** : Wenn ein Benutzer eine schädliche IP-Adresse oder Domäne besucht, wird ein Ereignis im Windows-Ereignisprotokoll aufgezeichnet.</span><span class="sxs-lookup"><span data-stu-id="6fddb-153">**Audit Mode** - If a user visits a malicious IP address or domain, an event will be recorded in the Windows event log.</span></span> <span data-ttu-id="6fddb-154">Der Benutzer wird jedoch nicht am Besuch der Adresse blockiert.</span><span class="sxs-lookup"><span data-stu-id="6fddb-154">However, the user won't be blocked from visiting the address.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="6fddb-155">Um den Netzwerkschutz vollständig zu aktivieren, müssen Sie  die Option Gruppenrichtlinie auf **Aktiviert** festlegen und im Dropdownmenü Optionen auch Blockieren auswählen.</span><span class="sxs-lookup"><span data-stu-id="6fddb-155">To fully enable network protection, you must set the Group Policy option to **Enabled** and also select **Block** in the options drop-down menu.</span></span>

<span data-ttu-id="6fddb-156">Vergewissern Sie sich, dass der Netzwerkschutz auf einem lokalen Computer mithilfe des Registrierungs-Editors aktiviert ist:</span><span class="sxs-lookup"><span data-stu-id="6fddb-156">Confirm network protection is enabled on a local computer by using Registry editor:</span></span>

1. <span data-ttu-id="6fddb-157">Wählen **Sie Start** aus, und geben Sie **regedit ein,** um den **Registrierungs-Editor zu öffnen.**</span><span class="sxs-lookup"><span data-stu-id="6fddb-157">Select **Start** and type **regedit** to open **Registry Editor**.</span></span>

2. <span data-ttu-id="6fddb-158">Navigieren Sie zu **HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Defender\Policy Manager\EnableNetworkProtection**</span><span class="sxs-lookup"><span data-stu-id="6fddb-158">Navigate to **HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Defender\Policy Manager\EnableNetworkProtection**</span></span>

3. <span data-ttu-id="6fddb-159">Wählen **Sie EnableNetworkProtection aus,** und bestätigen Sie den Wert:</span><span class="sxs-lookup"><span data-stu-id="6fddb-159">Select **EnableNetworkProtection** and confirm the value:</span></span>
   * <span data-ttu-id="6fddb-160">0=Aus</span><span class="sxs-lookup"><span data-stu-id="6fddb-160">0=Off</span></span>
   * <span data-ttu-id="6fddb-161">1=Ein</span><span class="sxs-lookup"><span data-stu-id="6fddb-161">1=On</span></span>
   * <span data-ttu-id="6fddb-162">2=Überwachung</span><span class="sxs-lookup"><span data-stu-id="6fddb-162">2=Audit</span></span>

## <a name="see-also"></a><span data-ttu-id="6fddb-163">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6fddb-163">See also</span></span>

* [<span data-ttu-id="6fddb-164">Netzwerkschutz</span><span class="sxs-lookup"><span data-stu-id="6fddb-164">Network protection</span></span>](network-protection.md)
* [<span data-ttu-id="6fddb-165">Auswerten des Netzwerkschutzes</span><span class="sxs-lookup"><span data-stu-id="6fddb-165">Evaluate network protection</span></span>](evaluate-network-protection.md)
* [<span data-ttu-id="6fddb-166">Problembehandlung beim Netzwerkschutz</span><span class="sxs-lookup"><span data-stu-id="6fddb-166">Troubleshoot network protection</span></span>](troubleshoot-np.md)
