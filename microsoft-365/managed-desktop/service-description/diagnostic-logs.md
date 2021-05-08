---
title: Diagnoseprotokolle
description: Protokolle, die während der Problembehandlung von Geräten gesammelt werden und wie sie gespeichert werden
keywords: Microsoft Managed Desktop, Microsoft 365, Dienst, Dokumentation
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: ef7d19fef989610c10323c2a9820a5314d5e1641
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2021
ms.locfileid: "52272891"
---
# <a name="diagnostic-logs"></a><span data-ttu-id="f8e7f-104">Diagnoseprotokolle</span><span class="sxs-lookup"><span data-stu-id="f8e7f-104">Diagnostic logs</span></span>

<span data-ttu-id="f8e7f-105">Wenn wir ein Problem auf einem von Microsoft Managed Desktop verwalteten Gerät behandeln, unabhängig davon, ob sie gemeldet oder von unserem Dienst identifiziert wurden, müssen wir möglicherweise bestimmte Diagnoseprotokolle vom Gerät ohne Eingreifen des Benutzers erfassen.</span><span class="sxs-lookup"><span data-stu-id="f8e7f-105">When we troubleshoot an issue on a device managed by Microsoft Managed Desktop, whether one you've reported or one identified by our service, we might have to collect certain diagnostic logs from the device without intervention from the user.</span></span> <span data-ttu-id="f8e7f-106">Wir sammeln keine vom Benutzer generierten Inhalte oder Informationen aus Benutzerverzeichnissen.</span><span class="sxs-lookup"><span data-stu-id="f8e7f-106">We don't collect any user-generated content or information from user directories.</span></span> <span data-ttu-id="f8e7f-107">Wir erfassen nur Diagnose- und Protokolldaten, die den Gerätestatus und -status betrifft.</span><span class="sxs-lookup"><span data-stu-id="f8e7f-107">We only collect diagnostic and log data that concerns device health and status.</span></span>

<span data-ttu-id="f8e7f-108">Wir speichern alle gesammelten Protokolle für 28 Tage und löschen sie dann.</span><span class="sxs-lookup"><span data-stu-id="f8e7f-108">We store any collected logs for 28 days, and then delete them.</span></span> <span data-ttu-id="f8e7f-109">Wir verarbeiten alle Protokolle, die von einem Gerät gesammelt werden, nach unseren [Datenverarbeitungsstandards](privacy-personal-data.md).</span><span class="sxs-lookup"><span data-stu-id="f8e7f-109">We process any logs collected from a device following our [data handling standards](privacy-personal-data.md).</span></span>

## <a name="data-collected"></a><span data-ttu-id="f8e7f-110">Gesammelte Daten</span><span class="sxs-lookup"><span data-stu-id="f8e7f-110">Data collected</span></span>

<span data-ttu-id="f8e7f-111">Diese Liste enthält alle Ordner, Ereignisprotokolle, ausführbaren Dateien oder Registrierungsstandorte, von der Microsoft Managed Desktop Diagnoseprotokolle erfassen kann.</span><span class="sxs-lookup"><span data-stu-id="f8e7f-111">This list includes all the folders, event logs, executables, or registry locations that Microsoft Managed Desktop might collect diagnostic logs from.</span></span> <span data-ttu-id="f8e7f-112">Die tatsächlich gesammelten Daten sind eine Teilmenge dieser Liste und hängen vom identifizierten Problem ab.</span><span class="sxs-lookup"><span data-stu-id="f8e7f-112">The actual data collected will be a subset of this list and depends on the identified issue.</span></span>

### <a name="registry-keys"></a><span data-ttu-id="f8e7f-113">Registrierungsschlüssel</span><span class="sxs-lookup"><span data-stu-id="f8e7f-113">Registry keys</span></span>

- <span data-ttu-id="f8e7f-114">HKLM \\ SYSTEM \\ CurrentControlSet \\ Services</span><span class="sxs-lookup"><span data-stu-id="f8e7f-114">HKLM\\SYSTEM\\CurrentControlSet\\Services</span></span>
- <span data-ttu-id="f8e7f-115">HKLM \\ SOFTWARE \\ Microsoft \\ Surface</span><span class="sxs-lookup"><span data-stu-id="f8e7f-115">HKLM\\SOFTWARE\\Microsoft\\Surface</span></span>
- <span data-ttu-id="f8e7f-116">HKLM \\ SOFTWARE \\ Policies \\ Microsoft \\ Windows \\ WindowsUpdate</span><span class="sxs-lookup"><span data-stu-id="f8e7f-116">HKLM\\SOFTWARE\\Policies\\Microsoft\\Windows\\WindowsUpdate</span></span>
- <span data-ttu-id="f8e7f-117">HKLM \\ SYSTEM \\ CurrentControlSet \\ Control \\ MUI \\ UILanguages</span><span class="sxs-lookup"><span data-stu-id="f8e7f-117">HKLM\\SYSTEM\\CurrentControlSet\\Control\\MUI\\UILanguages</span></span>
- <span data-ttu-id="f8e7f-118">\\HKLM-Softwarerichtlinien \\ \\ Microsoft \\ WindowsStore</span><span class="sxs-lookup"><span data-stu-id="f8e7f-118">HKLM\\Software\\Policies\\Microsoft\\WindowsStore</span></span>
- <span data-ttu-id="f8e7f-119">HKLM \\ Software \\ Microsoft \\ Windows \\ CurrentVersion \\ WindowsStore \\ WindowsUpdate</span><span class="sxs-lookup"><span data-stu-id="f8e7f-119">HKLM\\Software\\Microsoft\\Windows\\CurrentVersion\\WindowsStore\\WindowsUpdate</span></span>
- <span data-ttu-id="f8e7f-120">HKLM \\ SOFTWARE \\ Microsoft \\ Windows NT \\ CurrentVersion</span><span class="sxs-lookup"><span data-stu-id="f8e7f-120">HKLM\\SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion</span></span>
- <span data-ttu-id="f8e7f-121">HKLM \\ SOFTWARE \\ Microsoft \\ Windows NT \\ CurrentVersion</span><span class="sxs-lookup"><span data-stu-id="f8e7f-121">HKLM\\SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion</span></span>
- <span data-ttu-id="f8e7f-122">HKLM \\ SOFTWARE \\ Microsoft \\ Windows \\ CurrentVersion \\ AppModel</span><span class="sxs-lookup"><span data-stu-id="f8e7f-122">HKLM\\SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\AppModel</span></span>
- <span data-ttu-id="f8e7f-123">HKLM \\ SYSTEM \\ CurrentControlSet \\ Control \\ FirmwareResources</span><span class="sxs-lookup"><span data-stu-id="f8e7f-123">HKLM\\SYSTEM\\CurrentControlSet\\Control\\FirmwareResources</span></span>
- <span data-ttu-id="f8e7f-124">HKLM \\ SOFTWARE \\ Microsoft \\ WindowsSelfhost</span><span class="sxs-lookup"><span data-stu-id="f8e7f-124">HKLM\\SOFTWARE\\Microsoft\\WindowsSelfhost</span></span>
- <span data-ttu-id="f8e7f-125">HKLM \\ SOFTWARE \\ Microsoft \\ WindowsUpdate</span><span class="sxs-lookup"><span data-stu-id="f8e7f-125">HKLM\\SOFTWARE\\Microsoft\\WindowsUpdate</span></span>
- <span data-ttu-id="f8e7f-126">HKLM \\ SOFTWARE \\ Microsoft \\ Windows \\ CurrentVersion \\ Appx</span><span class="sxs-lookup"><span data-stu-id="f8e7f-126">HKLM\\SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Appx</span></span>
- <span data-ttu-id="f8e7f-127">HKLM \\ SOFTWARE \\ Microsoft \\ Windows NT \\ CurrentVersion \\ Superfetch</span><span class="sxs-lookup"><span data-stu-id="f8e7f-127">HKLM\\SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\Superfetch</span></span>
- <span data-ttu-id="f8e7f-128">HKLM \\ SYSTEM \\ Setup</span><span class="sxs-lookup"><span data-stu-id="f8e7f-128">HKLM\\SYSTEM\\Setup</span></span>
- <span data-ttu-id="f8e7f-129">HKLM \\ Software \\ Microsoft \\ IntuneManagementExtension</span><span class="sxs-lookup"><span data-stu-id="f8e7f-129">HKLM\\Software\\Microsoft\\IntuneManagementExtension</span></span>
- <span data-ttu-id="f8e7f-130">HKLM \\ SOFTWARE \\ Microsoft \\ SystemCertificates \\ AuthRoot</span><span class="sxs-lookup"><span data-stu-id="f8e7f-130">HKLM\\SOFTWARE\\Microsoft\\SystemCertificates\\AuthRoot</span></span>
- <span data-ttu-id="f8e7f-131">HKLM \\ SOFTWARE \\ Microsoft \\ Windows Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="f8e7f-131">HKLM\\SOFTWARE\\Microsoft\\Windows Advanced Threat Protection</span></span>
- <span data-ttu-id="f8e7f-132">HKLM \\ SOFTWARE \\ Microsoft \\ Windows \\ CurrentVersion \\ Authentication \\ LogonUI</span><span class="sxs-lookup"><span data-stu-id="f8e7f-132">HKLM\\SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Authentication\\LogonUI</span></span>
- <span data-ttu-id="f8e7f-133">HKLM \\ SOFTWARE Microsoft Windows \\ \\ \\ CurrentVersion \\ -Interneteinstellungen</span><span class="sxs-lookup"><span data-stu-id="f8e7f-133">HKLM\\SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Internet Settings</span></span>
- <span data-ttu-id="f8e7f-134">HKLM \\ Software \\ Microsoft \\ Windows \\ CurrentVersion \\ Uninstall</span><span class="sxs-lookup"><span data-stu-id="f8e7f-134">HKLM\\Software\\Microsoft\\Windows\\CurrentVersion\\Uninstall</span></span>
- <span data-ttu-id="f8e7f-135">\\HKLM-Softwarerichtlinien \\</span><span class="sxs-lookup"><span data-stu-id="f8e7f-135">HKLM\\Software\\Policies</span></span>
- <span data-ttu-id="f8e7f-136">HKLM \\ SOFTWARE \\ Policies \\ Microsoft \\ Cryptography \\ Configuration \\ SSL</span><span class="sxs-lookup"><span data-stu-id="f8e7f-136">HKLM\\SOFTWARE\\Policies\\Microsoft\\Cryptography\\Configuration\\SSL</span></span>
- <span data-ttu-id="f8e7f-137">HKLM \\ SOFTWARE \\ Policies \\ Microsoft \\ Windows Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="f8e7f-137">HKLM\\SOFTWARE\\Policies\\Microsoft\\Windows Advanced Threat Protection</span></span>
- <span data-ttu-id="f8e7f-138">HKLM \\ SOFTWARE \\ WOW6432Node \\ Microsoft Windows \\ \\ CurrentVersion \\ Deinstallieren</span><span class="sxs-lookup"><span data-stu-id="f8e7f-138">HKLM\\SOFTWARE\\WOW6432Node\\Microsoft\\Windows\\CurrentVersion\\Uninstall</span></span>
- <span data-ttu-id="f8e7f-139">HKLM \\ SYSTEM \\ CurrentControlSet \\ Control \\ SecurityProviders \\ SCHANNEL</span><span class="sxs-lookup"><span data-stu-id="f8e7f-139">HKLM\\SYSTEM\\CurrentControlSet\\Control\\SecurityProviders\\SCHANNEL</span></span>

### <a name="commands"></a><span data-ttu-id="f8e7f-140">Befehle</span><span class="sxs-lookup"><span data-stu-id="f8e7f-140">Commands</span></span>

- <span data-ttu-id="f8e7f-141">%programfiles% \\ windows defendermpcmdrun.exe \\ -GetFiles</span><span class="sxs-lookup"><span data-stu-id="f8e7f-141">%programfiles%\\windows defender\\mpcmdrun.exe -GetFiles</span></span>
- <span data-ttu-id="f8e7f-142">%windir% \\ system32 \\certutil.exe -store</span><span class="sxs-lookup"><span data-stu-id="f8e7f-142">%windir%\\system32\\certutil.exe -store</span></span>
- <span data-ttu-id="f8e7f-143">%windir% \\ system32 \\certutil.exe -store -user my</span><span class="sxs-lookup"><span data-stu-id="f8e7f-143">%windir%\\system32\\certutil.exe -store -user my</span></span>
- <span data-ttu-id="f8e7f-144">%windir% \\ system32 \\Dsregcmd.exe /status</span><span class="sxs-lookup"><span data-stu-id="f8e7f-144">%windir%\\system32\\Dsregcmd.exe /status</span></span>
- <span data-ttu-id="f8e7f-145">%windir% \\ system32 \\ipconfig.exe /all</span><span class="sxs-lookup"><span data-stu-id="f8e7f-145">%windir%\\system32\\ipconfig.exe /all</span></span>
- <span data-ttu-id="f8e7f-146">%windir% \\ system32 \\ipconfig.exe /displaydns</span><span class="sxs-lookup"><span data-stu-id="f8e7f-146">%windir%\\system32\\ipconfig.exe /displaydns</span></span>
- <span data-ttu-id="f8e7f-147">%windir% \\ system32 \\mdmdiagnosticstool.exe</span><span class="sxs-lookup"><span data-stu-id="f8e7f-147">%windir%\\system32\\mdmdiagnosticstool.exe</span></span>
- <span data-ttu-id="f8e7f-148">%windir% \\ system32 \\msinfo32.exe /report %temp% \\ MDMDiagnostics \\ msinfo32.log</span><span class="sxs-lookup"><span data-stu-id="f8e7f-148">%windir%\\system32\\msinfo32.exe /report %temp%\\MDMDiagnostics\\msinfo32.log</span></span>
- <span data-ttu-id="f8e7f-149">%windir% \\ system32 \\netsh.exe advfirewall alleProfile anzeigen</span><span class="sxs-lookup"><span data-stu-id="f8e7f-149">%windir%\\system32\\netsh.exe advfirewall show allprofiles</span></span>
- <span data-ttu-id="f8e7f-150">%windir% \\ system32 \\netsh.exe advfirewall global anzeigen</span><span class="sxs-lookup"><span data-stu-id="f8e7f-150">%windir%\\system32\\netsh.exe advfirewall show global</span></span>
- <span data-ttu-id="f8e7f-151">%windir% \\ system32 \\netsh.exe lan show profiles</span><span class="sxs-lookup"><span data-stu-id="f8e7f-151">%windir%\\system32\\netsh.exe lan show profiles</span></span>
- <span data-ttu-id="f8e7f-152">%windir% \\ system32 \\netsh.exe winhttp show proxy</span><span class="sxs-lookup"><span data-stu-id="f8e7f-152">%windir%\\system32\\netsh.exe winhttp show proxy</span></span>
- <span data-ttu-id="f8e7f-153">%windir% \\ system32 \\netsh.exe wlan show profiles</span><span class="sxs-lookup"><span data-stu-id="f8e7f-153">%windir%\\system32\\netsh.exe wlan show profiles</span></span>
- <span data-ttu-id="f8e7f-154">%windir% \\ system32 \\netsh.exe wlan show wlanreport</span><span class="sxs-lookup"><span data-stu-id="f8e7f-154">%windir%\\system32\\netsh.exe wlan show wlanreport</span></span>
- <span data-ttu-id="f8e7f-155">%windir% \\ system32 \\ping.exe -n 50 localhost</span><span class="sxs-lookup"><span data-stu-id="f8e7f-155">%windir%\\system32\\ping.exe -n 50 localhost</span></span>
- <span data-ttu-id="f8e7f-156">%windir% \\ system32 \\powercfg.exe /batteryreport /output %temp% \\ MDMDiagnostics \\battery-report.html</span><span class="sxs-lookup"><span data-stu-id="f8e7f-156">%windir%\\system32\\powercfg.exe /batteryreport /output %temp%\\MDMDiagnostics\\battery-report.html</span></span>
- <span data-ttu-id="f8e7f-157">%windir% \\ system32 \\powercfg.exe /energy /output %temp% \\ MDMDiagnostics \\energy-report.html</span><span class="sxs-lookup"><span data-stu-id="f8e7f-157">%windir%\\system32\\powercfg.exe /energy /output %temp%\\MDMDiagnostics\\energy-report.html</span></span>
- <span data-ttu-id="f8e7f-158">bitsadmin /list /allusers /verbose</span><span class="sxs-lookup"><span data-stu-id="f8e7f-158">bitsadmin /list /allusers /verbose</span></span>
- <span data-ttu-id="f8e7f-159">fltMC.exe</span><span class="sxs-lookup"><span data-stu-id="f8e7f-159">fltMC.exe</span></span>
- <span data-ttu-id="f8e7f-160">bcdedit /enum all /v</span><span class="sxs-lookup"><span data-stu-id="f8e7f-160">bcdedit /enum all /v</span></span>
- <span data-ttu-id="f8e7f-161">manage-bde -protectors -get</span><span class="sxs-lookup"><span data-stu-id="f8e7f-161">manage-bde -protectors -get</span></span>
- <span data-ttu-id="f8e7f-162">Windows PowerShell Befehle:</span><span class="sxs-lookup"><span data-stu-id="f8e7f-162">Windows PowerShell commands:</span></span>
    - <span data-ttu-id="f8e7f-163">Get-appxpackage -allusers</span><span class="sxs-lookup"><span data-stu-id="f8e7f-163">Get-appxpackage -allusers</span></span>
    - <span data-ttu-id="f8e7f-164">Get-appxpackage -packagetype bundle</span><span class="sxs-lookup"><span data-stu-id="f8e7f-164">Get-appxpackage -packagetype bundle</span></span>
    - <span data-ttu-id="f8e7f-165">Get-Service wuauserv</span><span class="sxs-lookup"><span data-stu-id="f8e7f-165">Get-Service wuauserv</span></span>
    - <span data-ttu-id="f8e7f-166">Get-NetFirewallRule</span><span class="sxs-lookup"><span data-stu-id="f8e7f-166">Get-NetFirewallRule</span></span>
    - <span data-ttu-id="f8e7f-167">Get-WmiObject -Class win32 \_ product</span><span class="sxs-lookup"><span data-stu-id="f8e7f-167">Get-WmiObject -Class win32\_product</span></span>
    - <span data-ttu-id="f8e7f-168">Get-ComputerInfo</span><span class="sxs-lookup"><span data-stu-id="f8e7f-168">Get-ComputerInfo</span></span>
    - <span data-ttu-id="f8e7f-169">Get-Service</span><span class="sxs-lookup"><span data-stu-id="f8e7f-169">Get-Service</span></span>
    - <span data-ttu-id="f8e7f-170">Get-Process</span><span class="sxs-lookup"><span data-stu-id="f8e7f-170">Get-Process</span></span>
    - <span data-ttu-id="f8e7f-171">Get-WmiObject Win32 \_ PnPSignedDriver</span><span class="sxs-lookup"><span data-stu-id="f8e7f-171">Get-WmiObject Win32\_PnPSignedDriver</span></span>

### <a name="event-logs"></a><span data-ttu-id="f8e7f-172">Ereignisprotokolle</span><span class="sxs-lookup"><span data-stu-id="f8e7f-172">Event logs</span></span>

- <span data-ttu-id="f8e7f-173">Anwendung</span><span class="sxs-lookup"><span data-stu-id="f8e7f-173">Application</span></span>
- <span data-ttu-id="f8e7f-174">Microsoft-Windows-AppLocker/EXE und DLL</span><span class="sxs-lookup"><span data-stu-id="f8e7f-174">Microsoft-Windows-AppLocker/EXE and DLL</span></span>
- <span data-ttu-id="f8e7f-175">Microsoft-Windows-AppLocker/MSI und Script</span><span class="sxs-lookup"><span data-stu-id="f8e7f-175">Microsoft-Windows-AppLocker/MSI and Script</span></span>
- <span data-ttu-id="f8e7f-176">Microsoft-Windows-AppLocker/Packaged app-Deployment</span><span class="sxs-lookup"><span data-stu-id="f8e7f-176">Microsoft-Windows-AppLocker/Packaged app-Deployment</span></span>
- <span data-ttu-id="f8e7f-177">Microsoft-Windows-AppLocker/Packaged app-Execution</span><span class="sxs-lookup"><span data-stu-id="f8e7f-177">Microsoft-Windows-AppLocker/Packaged app-Execution</span></span>
- <span data-ttu-id="f8e7f-178">Microsoft-Windows-Bitlocker/Bitlocker-Verwaltung</span><span class="sxs-lookup"><span data-stu-id="f8e7f-178">Microsoft-Windows-Bitlocker/Bitlocker Management</span></span>
- <span data-ttu-id="f8e7f-179">Microsoft-Windows-SENSE/Operational</span><span class="sxs-lookup"><span data-stu-id="f8e7f-179">Microsoft-Windows-SENSE/Operational</span></span>
- <span data-ttu-id="f8e7f-180">Microsoft-Windows-SenseIR/Operational</span><span class="sxs-lookup"><span data-stu-id="f8e7f-180">Microsoft-Windows-SenseIR/Operational</span></span>
- <span data-ttu-id="f8e7f-181">Setup</span><span class="sxs-lookup"><span data-stu-id="f8e7f-181">Setup</span></span>
- <span data-ttu-id="f8e7f-182">System</span><span class="sxs-lookup"><span data-stu-id="f8e7f-182">System</span></span>

### <a name="files"></a><span data-ttu-id="f8e7f-183">Dateien</span><span class="sxs-lookup"><span data-stu-id="f8e7f-183">Files</span></span>

- <span data-ttu-id="f8e7f-184">%ProgramData% \\ Microsoft \\ DiagnosticLogCSP \\ Collectors \\ \* .etl</span><span class="sxs-lookup"><span data-stu-id="f8e7f-184">%ProgramData%\\Microsoft\\DiagnosticLogCSP\\Collectors\\\*.etl</span></span>
- <span data-ttu-id="f8e7f-185">%ProgramData% \\ Microsoft \\ IntuneManagementExtension \\ Logs \\ \* .\*</span><span class="sxs-lookup"><span data-stu-id="f8e7f-185">%ProgramData%\\Microsoft\\IntuneManagementExtension\\Logs\\\*.\*</span></span>
- <span data-ttu-id="f8e7f-186">%ProgramData% \\ Microsoft Windows Defender Support \\ \\ \\MpSupportFiles.cab</span><span class="sxs-lookup"><span data-stu-id="f8e7f-186">%ProgramData%\\Microsoft\\Windows Defender\\Support\\MpSupportFiles.cab</span></span>
- <span data-ttu-id="f8e7f-187">%ProgramData% \\ Microsoft \\ Windows \\ WlanReportwlan-report-latest.htm\\ l</span><span class="sxs-lookup"><span data-stu-id="f8e7f-187">%ProgramData%\\Microsoft\\Windows\\WlanReport\\wlan-report-latest.html</span></span>
- <span data-ttu-id="f8e7f-188">%ProgramData% \\ Microsoft \\ Windows \\ WLANReport -SourceFileName wlan-report-latest.html</span><span class="sxs-lookup"><span data-stu-id="f8e7f-188">%ProgramData%\\Microsoft\\Windows\\WlanReport -SourceFileName wlan-report-latest.html</span></span>
- <span data-ttu-id="f8e7f-189">%windir% \\ ccm \\ logs \* .log</span><span class="sxs-lookup"><span data-stu-id="f8e7f-189">%windir%\\ccm\\logs\*.log</span></span>
- <span data-ttu-id="f8e7f-190">%windir% \\ ccmsetup \\ logs \* .log</span><span class="sxs-lookup"><span data-stu-id="f8e7f-190">%windir%\\ccmsetup\\logs\*.log</span></span>
- <span data-ttu-id="f8e7f-191">%windir% \\ logs \\ CBS \\ cbs.log</span><span class="sxs-lookup"><span data-stu-id="f8e7f-191">%windir%\\logs\\CBS\\cbs.log</span></span>
- <span data-ttu-id="f8e7f-192">%windir% \\ logs \\ measuredboot \* .\*</span><span class="sxs-lookup"><span data-stu-id="f8e7f-192">%windir%\\logs\\measuredboot\*.\*</span></span>
- <span data-ttu-id="f8e7f-193">%windir% \\ Logs \\ WindowsUpdate \* .etl</span><span class="sxs-lookup"><span data-stu-id="f8e7f-193">%windir%\\Logs\\WindowsUpdate\*.etl</span></span>
- <span data-ttu-id="f8e7f-194">%windir% \\ inf \\ \* .log</span><span class="sxs-lookup"><span data-stu-id="f8e7f-194">%windir%\\inf\\\*.log</span></span>
- <span data-ttu-id="f8e7f-195">\\%windir%-Wartungssitzungen \\ \\ActionList.xml</span><span class="sxs-lookup"><span data-stu-id="f8e7f-195">%windir%\\servicing\\sessions\\ActionList.xml</span></span>
- <span data-ttu-id="f8e7f-196">\\%windir%-Wartungssitzungen \\ \\Sessions.xml</span><span class="sxs-lookup"><span data-stu-id="f8e7f-196">%windir%\\servicing\\sessions\\Sessions.xml</span></span>
- <span data-ttu-id="f8e7f-197">%windir% \\ SoftwareDistribution \\ DataStore \\ Logs \\ edb.log</span><span class="sxs-lookup"><span data-stu-id="f8e7f-197">%windir%\\SoftwareDistribution\\DataStore\\Logs\\edb.log</span></span>
- <span data-ttu-id="f8e7f-198">%windir% \\ SoftwareDistribution \\ DataStore \\ DataStore.edb</span><span class="sxs-lookup"><span data-stu-id="f8e7f-198">%windir%\\SoftwareDistribution\\DataStore\\DataStore.edb</span></span>
- <span data-ttu-id="f8e7f-199">%windir% \\ logs \\ dism \\ dism.log</span><span class="sxs-lookup"><span data-stu-id="f8e7f-199">%windir%\\logs\\dism\\dism.log</span></span>
- <span data-ttu-id="f8e7f-200">%SystemRoot% \\ System32 \\ Winevt \\ Logs</span><span class="sxs-lookup"><span data-stu-id="f8e7f-200">%SystemRoot%\\System32\\Winevt\\Logs</span></span>\\
- <span data-ttu-id="f8e7f-201">%appdata% \\ Microsoft \\ Teams \\ media-stack \\ \* .blog</span><span class="sxs-lookup"><span data-stu-id="f8e7f-201">%appdata%\\Microsoft\\Teams\\media-stack\\\*.blog</span></span>
- <span data-ttu-id="f8e7f-202">%appdata% \\ Microsoft \\ Teams \\ skylib \\ \* .blog</span><span class="sxs-lookup"><span data-stu-id="f8e7f-202">%appdata%\\Microsoft\\Teams\\skylib\\\*.blog</span></span>
- <span data-ttu-id="f8e7f-203">%appdata% \\ Microsoft \\ Teams \\ media-stack \\ \* .etl</span><span class="sxs-lookup"><span data-stu-id="f8e7f-203">%appdata%\\Microsoft\\Teams\\media-stack\\\*.etl</span></span>
- <span data-ttu-id="f8e7f-204">%appdata% \\ Microsoft \\ Teams \\logs.txt</span><span class="sxs-lookup"><span data-stu-id="f8e7f-204">%appdata%\\Microsoft\\Teams\\logs.txt</span></span>
- <span data-ttu-id="f8e7f-205">%windir% \\ Windows \\ System32 \\ winevt \\ \* .\*</span><span class="sxs-lookup"><span data-stu-id="f8e7f-205">%windir%\\Windows\\System32\\winevt\\\*.\*</span></span>