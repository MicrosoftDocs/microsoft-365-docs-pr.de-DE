---
title: Onboarding von Windows 10-Geräten mithilfe von Configuration Manager
f1.keywords: NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MET150
description: Verwenden Sie Configuration Manager, um das Konfigurationspaket auf Geräten so zu bereitstellen, dass sie in den Dienst integrierte werden.
ms.openlocfilehash: ac05581ce33e94859dbd67848197878595d5ed0f
ms.sourcegitcommit: 55791ddab9ae484f76b30f0470eec8a4cf7b46d1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/20/2021
ms.locfileid: "51893296"
---
# <a name="onboard-windows-10-devices-using-configuration-manager"></a><span data-ttu-id="126f2-103">Onboarding von Windows 10-Geräten mithilfe von Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="126f2-103">Onboard Windows 10 devices using Configuration Manager</span></span>

<span data-ttu-id="126f2-104">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="126f2-104">**Applies to:**</span></span>

- [<span data-ttu-id="126f2-105">Microsoft 365 Verhinderung von Endpunktdatenverlusten (Endpoint Data Loss Prevention, DLP)</span><span class="sxs-lookup"><span data-stu-id="126f2-105">Microsoft 365 Endpoint data loss prevention (DLP)</span></span>](./endpoint-dlp-learn-about.md)
- <span data-ttu-id="126f2-106">System Center 2012 R2 Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="126f2-106">System Center 2012 R2 Configuration Manager</span></span>

### <a name="onboard-devices-using-system-center-configuration-manager"></a><span data-ttu-id="126f2-107">Onboarding von Geräten mithilfe System Center Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="126f2-107">Onboard devices using System Center Configuration Manager</span></span>

1. <span data-ttu-id="126f2-108">Öffnen Sie die Konfigurationspaketdatei .zip Configuration Manager (*DeviceComplianceOnboardingPackage.zip*), die Sie aus dem Dienst-Onboarding-Assistenten heruntergeladen haben.</span><span class="sxs-lookup"><span data-stu-id="126f2-108">Open the Configuration Manager configuration package .zip file (*DeviceComplianceOnboardingPackage.zip*) that you downloaded from the service onboarding wizard.</span></span> <span data-ttu-id="126f2-109">Sie können das Paket auch über das [Microsoft Compliance Center erhalten.](https://compliance.microsoft.com/)</span><span class="sxs-lookup"><span data-stu-id="126f2-109">You can also get the package from [Microsoft Compliance center](https://compliance.microsoft.com/).</span></span>

2. <span data-ttu-id="126f2-110">Wählen Sie im Navigationsbereich **Einstellungen**  >  **Onboarding**  >  **des Geräts aus.**</span><span class="sxs-lookup"><span data-stu-id="126f2-110">In the navigation pane, select **Settings** > **Device Onboarding** > **Onboarding**.</span></span>

3. <span data-ttu-id="126f2-111">Wählen Sie **im** Feld **Bereitstellungsmethode Microsoft Endpoint Configuration Manager 2012/2012 R2/1511/1602 aus.**</span><span class="sxs-lookup"><span data-stu-id="126f2-111">In the **Deployment method** field, select **Microsoft Endpoint Configuration Manager 2012/2012 R2/1511/1602**.</span></span>
 
4. <span data-ttu-id="126f2-112">Wählen **Sie Paket herunterladen** aus, und speichern Sie .zip Datei.</span><span class="sxs-lookup"><span data-stu-id="126f2-112">Select **Download package**, and save the .zip file.</span></span>

5. <span data-ttu-id="126f2-113">Extrahieren Sie den Inhalt der .zip an einen freigegebenen, schreibgeschützten Speicherort, auf den die Netzwerkadministratoren zugreifen können, die das Paket bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="126f2-113">Extract the contents of the .zip file to a shared, read-only location that can be accessed by the network administrators who will deploy the package.</span></span> <span data-ttu-id="126f2-114">Sie sollten über eine Datei mit dem Namen *DeviceComplianceOnboardingScript.cmd verfügen.*</span><span class="sxs-lookup"><span data-stu-id="126f2-114">You should have a file named *DeviceComplianceOnboardingScript.cmd*.</span></span>

6. <span data-ttu-id="126f2-115">Stellen Sie das Paket zur Verfügung, indem Sie die Schritte im Artikel Pakete und Programme [in System Center 2012 R2 Configuration Manager](/previous-versions/system-center/system-center-2012-R2/gg699369(v=technet.10)) ausführen.</span><span class="sxs-lookup"><span data-stu-id="126f2-115">Deploy the package by following the steps in the [Packages and Programs in System Center 2012 R2 Configuration Manager](/previous-versions/system-center/system-center-2012-R2/gg699369(v=technet.10)) article.</span></span>

7. <span data-ttu-id="126f2-116">Wählen Sie eine vordefinierte Gerätesammlung aus, auf der das Paket bereitgestellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="126f2-116">Choose a predefined device collection to deploy the package to.</span></span>

> [!NOTE]
> <span data-ttu-id="126f2-117">Microsoft 365 Die Verhinderung von Endpunktdatenverlusten unterstützt das Onboarding während der [Out-Of-Box Experience (OOBE)-Phase](https://answers.microsoft.com/en-us/windows/wiki/windows_10/how-to-complete-the-windows-10-out-of-box/47e3f943-f000-45e3-8c5c-9d85a1a0cf87) nicht.</span><span class="sxs-lookup"><span data-stu-id="126f2-117">Microsoft 365 Endpoint data loss prevention doesn't support onboarding during the [Out-Of-Box Experience (OOBE)](https://answers.microsoft.com/en-us/windows/wiki/windows_10/how-to-complete-the-windows-10-out-of-box/47e3f943-f000-45e3-8c5c-9d85a1a0cf87) phase.</span></span> <span data-ttu-id="126f2-118">Stellen Sie sicher, dass Benutzer OOBE abschließen, nachdem sie Windows oder Upgrade ausgeführt haben.</span><span class="sxs-lookup"><span data-stu-id="126f2-118">Make sure users complete OOBE after running Windows installation or upgrading.</span></span>

>[!TIP]
> <span data-ttu-id="126f2-119">Nach dem Onboarding des Geräts können Sie einen Erkennungstest ausführen, um sicherzustellen, dass ein Gerät ordnungsgemäß in den Dienst integrierte ist.</span><span class="sxs-lookup"><span data-stu-id="126f2-119">After onboarding the device, you can choose to run a detection test to verify that an device is properly onboarded to the service.</span></span> <span data-ttu-id="126f2-120">Weitere Informationen finden Sie unter Ausführen eines Erkennungstests auf einem neu integrierten [Microsoft Defender for Endpoint-Gerät.](/windows/security/threat-protection/microsoft-defender-atp/run-detection-test)</span><span class="sxs-lookup"><span data-stu-id="126f2-120">For more information, see [Run a detection test on a newly onboarded Microsoft Defender for Endpoint device](/windows/security/threat-protection/microsoft-defender-atp/run-detection-test).</span></span>
>
> <span data-ttu-id="126f2-121">Beachten Sie, dass es möglich ist, eine Erkennungsregel für eine Configuration Manager-Anwendung zu erstellen, um kontinuierlich zu überprüfen, ob ein Gerät onboardiert wurde.</span><span class="sxs-lookup"><span data-stu-id="126f2-121">Note that it is possible to create a detection rule on a Configuration Manager application to continuously check if a device has been onboarded.</span></span> <span data-ttu-id="126f2-122">Eine Anwendung ist ein anderer Objekttyp als ein Paket und Programm.</span><span class="sxs-lookup"><span data-stu-id="126f2-122">An application is a different type of object than a package and program.</span></span>
> <span data-ttu-id="126f2-123">Wenn ein Gerät noch nicht onboarded ist (aufgrund ausstehender OOBE-Fertigstellung oder aus einem anderen Grund), wird der Configuration Manager versuchen, das Gerät so lange zu integrieren, bis die Regel die Statusänderung erkennt.</span><span class="sxs-lookup"><span data-stu-id="126f2-123">If a device is not yet onboarded (due to pending OOBE completion or any other reason), Configuration Manager will retry to onboard the device until the rule detects the status change.</span></span>
> 
> <span data-ttu-id="126f2-124">Dieses Verhalten kann erreicht werden, indem eine Erkennungsregel erstellt wird, die überprüft, ob der Registrierungswert "OnboardingState" (vom Typ REG_DWORD) = 1 ist.</span><span class="sxs-lookup"><span data-stu-id="126f2-124">This behavior can be accomplished by creating a detection rule checking if the "OnboardingState" registry value (of type REG_DWORD) = 1.</span></span>
> <span data-ttu-id="126f2-125">Dieser Registrierungswert befindet sich unter "HKLM\SOFTWARE\Microsoft\Windows Advanced Threat Protection\Status".</span><span class="sxs-lookup"><span data-stu-id="126f2-125">This registry value is located under "HKLM\SOFTWARE\Microsoft\Windows Advanced Threat Protection\Status".</span></span>
<span data-ttu-id="126f2-126">Weitere Informationen finden Sie unter [Configure Detection Methods in System Center 2012 R2 Configuration Manager](/previous-versions/system-center/system-center-2012-R2/gg682159(v=technet.10)#step-4-configure-detection-methods-to-indicate-the-presence-of-the-deployment-type).</span><span class="sxs-lookup"><span data-stu-id="126f2-126">For more information, see [Configure Detection Methods in System Center 2012 R2 Configuration Manager](/previous-versions/system-center/system-center-2012-R2/gg682159(v=technet.10)#step-4-configure-detection-methods-to-indicate-the-presence-of-the-deployment-type).</span></span>

### <a name="configure-sample-collection-settings"></a><span data-ttu-id="126f2-127">Konfigurieren von Beispielsammlungseinstellungen</span><span class="sxs-lookup"><span data-stu-id="126f2-127">Configure sample collection settings</span></span>

<span data-ttu-id="126f2-128">Für jedes Gerät können Sie einen Konfigurationswert festlegen, um zu bestimmen, ob Beispiele vom Gerät erfasst werden können, wenn über Microsoft Defender Security Center eine Datei zur tiefen Analyse übermittelt wird.</span><span class="sxs-lookup"><span data-stu-id="126f2-128">For each device, you can set a configuration value to state whether samples can be collected from the device when a request is made through Microsoft Defender Security Center to submit a file for deep analysis.</span></span>

>[!NOTE]
><span data-ttu-id="126f2-129">Diese Konfigurationseinstellungen werden in der Regel über Configuration Manager durchgeführt.</span><span class="sxs-lookup"><span data-stu-id="126f2-129">These configuration settings are typically done through Configuration Manager.</span></span> 

<span data-ttu-id="126f2-130">Sie können eine Complianceregel für das Konfigurationselement in Configuration Manager festlegen, um die Beispielfreigabeeinstellung auf einem Gerät zu ändern.</span><span class="sxs-lookup"><span data-stu-id="126f2-130">You can set a compliance rule for configuration item in Configuration Manager to change the sample share setting on a device.</span></span>

<span data-ttu-id="126f2-131">Diese Regel sollte  ein Konfigurationselement zur Behebung der Complianceregel sein, das den Wert eines Registrierungsschlüssels auf zielgerichteten Geräten fest legt, um sicherzustellen, dass sie sich beschweren.</span><span class="sxs-lookup"><span data-stu-id="126f2-131">This rule should be a *remediating* compliance rule configuration item that sets the value of a registry key on targeted devices to make sure they’re complaint.</span></span>

<span data-ttu-id="126f2-132">Die Konfiguration wird über den folgenden Registrierungsschlüsseleintrag festgelegt:</span><span class="sxs-lookup"><span data-stu-id="126f2-132">The configuration is set through the following registry key entry:</span></span>

```
Path: “HKLM\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection”
Name: "AllowSampleCollection"
Value: 0 or 1
```
<span data-ttu-id="126f2-133">Dabei gilt:</span><span class="sxs-lookup"><span data-stu-id="126f2-133">Where:</span></span><br>
<span data-ttu-id="126f2-134">Der Schlüsseltyp ist D-WORD.</span><span class="sxs-lookup"><span data-stu-id="126f2-134">Key type is a D-WORD.</span></span> <br>
<span data-ttu-id="126f2-135">Die folgenden Werte sind möglich:</span><span class="sxs-lookup"><span data-stu-id="126f2-135">Possible values are:</span></span>
- <span data-ttu-id="126f2-136">0 – lässt keine Beispielfreigabe von diesem Gerät zu</span><span class="sxs-lookup"><span data-stu-id="126f2-136">0 - doesn't allow sample sharing  from this device</span></span>
- <span data-ttu-id="126f2-137">1 – Ermöglicht die Freigabe aller Dateitypen von diesem Gerät</span><span class="sxs-lookup"><span data-stu-id="126f2-137">1 - allows sharing of all file types from this device</span></span>

<span data-ttu-id="126f2-138">Der Standardwert für den Fall, dass der Registrierungsschlüssel nicht vorhanden ist, ist 1.</span><span class="sxs-lookup"><span data-stu-id="126f2-138">The default value in case the registry key doesn’t exist is 1.</span></span>

<span data-ttu-id="126f2-139">Weitere Informationen zur System Center Configuration Manager finden Sie unter [Einführung in Complianceeinstellungen in System Center 2012 R2 Configuration Manager](/previous-versions/system-center/system-center-2012-R2/gg682139(v=technet.10)).</span><span class="sxs-lookup"><span data-stu-id="126f2-139">For more information about System Center Configuration Manager Compliance, see [Introduction to compliance settings in System Center 2012 R2 Configuration Manager](/previous-versions/system-center/system-center-2012-R2/gg682139(v=technet.10)).</span></span>


## <a name="other-recommended-configuration-settings"></a><span data-ttu-id="126f2-140">Weitere empfohlene Konfigurationseinstellungen</span><span class="sxs-lookup"><span data-stu-id="126f2-140">Other recommended configuration settings</span></span>
<span data-ttu-id="126f2-141">Nach dem Onboarding von Geräten in den Dienst ist es wichtig, die enthaltenen Funktionen zum Schutz vor Bedrohungen zu nutzen, indem Sie sie mit den folgenden empfohlenen Konfigurationseinstellungen aktivieren.</span><span class="sxs-lookup"><span data-stu-id="126f2-141">After onboarding devices to the service, it's important to take advantage of the included threat protection capabilities by enabling them with the following recommended configuration settings.</span></span>

### <a name="device-collection-configuration"></a><span data-ttu-id="126f2-142">Gerätesammlungskonfiguration</span><span class="sxs-lookup"><span data-stu-id="126f2-142">Device collection configuration</span></span>
<span data-ttu-id="126f2-143">Wenn Sie Endpoint Configuration Manager, Version 2002 oder höher, verwenden, können Sie die Bereitstellung auf Server oder Clients auf ebener Ebene erweitern.</span><span class="sxs-lookup"><span data-stu-id="126f2-143">If you're using Endpoint Configuration Manager, version 2002 or later, you can choose to broaden the deployment to include servers or down-level clients.</span></span>


### <a name="next-generation-protection-configuration"></a><span data-ttu-id="126f2-144">Schutzkonfiguration der nächsten Generation</span><span class="sxs-lookup"><span data-stu-id="126f2-144">Next generation protection configuration</span></span>

<span data-ttu-id="126f2-145">Die folgenden Konfigurationseinstellungen werden empfohlen:</span><span class="sxs-lookup"><span data-stu-id="126f2-145">The following configuration settings are recommended:</span></span>

<span data-ttu-id="126f2-146">**Überprüfung**</span><span class="sxs-lookup"><span data-stu-id="126f2-146">**Scan**</span></span>

- <span data-ttu-id="126f2-147">Überprüfen von Wechselmediengeräten wie USB-Laufwerken: Ja</span><span class="sxs-lookup"><span data-stu-id="126f2-147">Scan removable storage devices such as USB drives: Yes</span></span>

<span data-ttu-id="126f2-148">**Echtzeitschutz**</span><span class="sxs-lookup"><span data-stu-id="126f2-148">**Real-time Protection**</span></span>

- <span data-ttu-id="126f2-149">Aktivieren der Verhaltensüberwachung: Ja</span><span class="sxs-lookup"><span data-stu-id="126f2-149">Enable Behavioral Monitoring: Yes</span></span>
- <span data-ttu-id="126f2-150">Aktivieren des Schutzes vor potenziell unerwünschten Anwendungen beim Herunterladen und vor der Installation: Ja</span><span class="sxs-lookup"><span data-stu-id="126f2-150">Enable protection against Potentially Unwanted Applications at download and prior to installation: Yes</span></span>

<span data-ttu-id="126f2-151">**Cloud Protection Service**</span><span class="sxs-lookup"><span data-stu-id="126f2-151">**Cloud Protection Service**</span></span>

- <span data-ttu-id="126f2-152">Cloud Protection Service-Mitgliedschaftstyp: Erweiterte Mitgliedschaft</span><span class="sxs-lookup"><span data-stu-id="126f2-152">Cloud Protection Service membership type: Advanced membership</span></span>

<span data-ttu-id="126f2-153">**Reduzierung der Angriffsfläche** Konfigurieren Sie alle verfügbaren Regeln für Überwachung.</span><span class="sxs-lookup"><span data-stu-id="126f2-153">**Attack surface reduction** Configure all available rules to Audit.</span></span>

>[!NOTE]
> <span data-ttu-id="126f2-154">Das Blockieren dieser Aktivitäten kann legitime Geschäftsprozesse unterbrechen.</span><span class="sxs-lookup"><span data-stu-id="126f2-154">Blocking these activities may interrupt legitimate business processes.</span></span> <span data-ttu-id="126f2-155">Der beste Ansatz besteht in der Festlegung der Überwachung, der Identifizierung derjenigen, die sicher aktiviert werden können, und dem Aktivieren dieser Einstellungen auf Endpunkten, die keine falsch positiven Erkennungen haben.</span><span class="sxs-lookup"><span data-stu-id="126f2-155">The best approach is setting everything to audit, identifying which ones are safe to turn on, and then enabling those settings on endpoints which do not have false positive detections.</span></span>

<span data-ttu-id="126f2-156">**Netzwerkschutz**</span><span class="sxs-lookup"><span data-stu-id="126f2-156">**Network protection**</span></span>

<span data-ttu-id="126f2-157">Stellen Sie vor dem Aktivieren des Netzwerkschutzes im Überwachungs- oder Blockmodus sicher, dass Sie das Update der Antischalwareplattform installiert haben, das sie auf der [Supportseite erhalten können.](https://support.microsoft.com/en-us/help/4560203/windows-defender-anti-malware-platform-binaries-are-missing)</span><span class="sxs-lookup"><span data-stu-id="126f2-157">Prior to enabling network protection in audit or block mode, ensure that you've installed the antimalware platform update, which can be obtained from the [support page](https://support.microsoft.com/en-us/help/4560203/windows-defender-anti-malware-platform-binaries-are-missing).</span></span>


<span data-ttu-id="126f2-158">**Kontrollierter Ordnerzugriff**</span><span class="sxs-lookup"><span data-stu-id="126f2-158">**Controlled folder access**</span></span>

<span data-ttu-id="126f2-159">Aktivieren Sie das Feature im Überwachungsmodus für mindestens 30 Tage.</span><span class="sxs-lookup"><span data-stu-id="126f2-159">Enable the feature in audit mode for at least 30 days.</span></span> <span data-ttu-id="126f2-160">Überprüfen Sie nach diesem Zeitraum die Erkennungen, und erstellen Sie eine Liste der Anwendungen, die in geschützte Verzeichnisse schreiben dürfen.</span><span class="sxs-lookup"><span data-stu-id="126f2-160">After this period, review detections and create a list of applications that are allowed to write to protected directories.</span></span>

<span data-ttu-id="126f2-161">Weitere Informationen finden Sie unter [Evaluate controlled folder access](/windows/security/threat-protection/microsoft-defender-atp/evaluate-controlled-folder-access).</span><span class="sxs-lookup"><span data-stu-id="126f2-161">For more information, see [Evaluate controlled folder access](/windows/security/threat-protection/microsoft-defender-atp/evaluate-controlled-folder-access).</span></span>


## <a name="offboard-devices-using-configuration-manager"></a><span data-ttu-id="126f2-162">Offboardgeräte mit Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="126f2-162">Offboard devices using Configuration Manager</span></span>

<span data-ttu-id="126f2-163">Aus Sicherheitsgründen läuft das für Offboard-Geräte verwendete Paket 30 Tage nach dem Downloaddatum ab.</span><span class="sxs-lookup"><span data-stu-id="126f2-163">For security reasons, the package used to Offboard devices will expire 30 days after the date it was downloaded.</span></span> <span data-ttu-id="126f2-164">Abgelaufene offboarding-Pakete, die an ein Gerät gesendet werden, werden abgelehnt.</span><span class="sxs-lookup"><span data-stu-id="126f2-164">Expired offboarding packages sent to a device will be rejected.</span></span> <span data-ttu-id="126f2-165">Beim Herunterladen eines offboarding-Pakets werden Sie über das Ablaufdatum der Pakete benachrichtigt und es wird auch im Paketnamen enthalten sein.</span><span class="sxs-lookup"><span data-stu-id="126f2-165">When downloading an offboarding package, you will be notified of the packages expiry date and it will also be included in the package name.</span></span>

> [!NOTE]
> <span data-ttu-id="126f2-166">Onboarding- und Offboardingrichtlinien dürfen nicht gleichzeitig auf demselben Gerät bereitgestellt werden, da andernfalls unvorhersehbare Kollisionen verursacht werden.</span><span class="sxs-lookup"><span data-stu-id="126f2-166">Onboarding and offboarding policies must not be deployed on the same device at the same time, otherwise this will cause unpredictable collisions.</span></span>

### <a name="offboard-devices-using-microsoft-endpoint-configuration-manager-current-branch"></a><span data-ttu-id="126f2-167">Offboardgeräte mit Microsoft Endpoint Configuration Manager aktuellen Verzweigung</span><span class="sxs-lookup"><span data-stu-id="126f2-167">Offboard devices using Microsoft Endpoint Configuration Manager current branch</span></span>

<span data-ttu-id="126f2-168">Wenn Sie Microsoft Endpoint Configuration Manager aktuellen Zweigstelle verwenden, lesen [Sie Erstellen einer Offboardingkonfigurationsdatei](/configmgr/protect/deploy-use/windows-defender-advanced-threat-protection#create-an-offboarding-configuration-file).</span><span class="sxs-lookup"><span data-stu-id="126f2-168">If you use Microsoft Endpoint Configuration Manager current branch, see [Create an offboarding configuration file](/configmgr/protect/deploy-use/windows-defender-advanced-threat-protection#create-an-offboarding-configuration-file).</span></span>

### <a name="offboard-devices-using-system-center-2012-r2-configuration-manager"></a><span data-ttu-id="126f2-169">Offboardgeräte mit System Center 2012 R2 Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="126f2-169">Offboard devices using System Center 2012 R2 Configuration Manager</span></span>

1. <span data-ttu-id="126f2-170">Holen Sie sich das offboarding-Paket aus [dem Microsoft Compliance Center:](https://compliance.microsoft.com/)</span><span class="sxs-lookup"><span data-stu-id="126f2-170">Get the offboarding package from [Microsoft Compliance center](https://compliance.microsoft.com/):</span></span>

2. <span data-ttu-id="126f2-171">Wählen Sie im Navigationsbereich die **option Einstellungen**  >   **Device onboarding** >  **Offboarding aus.**</span><span class="sxs-lookup"><span data-stu-id="126f2-171">In the navigation pane, select **Settings** >  **Device onboarding**> **Offboarding**.</span></span>

3. <span data-ttu-id="126f2-172">Wählen Windows 10 als Betriebssystem aus.</span><span class="sxs-lookup"><span data-stu-id="126f2-172">Select Windows 10 as the operating system.</span></span>

4. <span data-ttu-id="126f2-173">Wählen Sie **im** Feld **Bereitstellungsmethode Microsoft Endpoint Configuration Manager 2012/2012 R2/1511/1602 aus.**</span><span class="sxs-lookup"><span data-stu-id="126f2-173">In the **Deployment method** field, select **Microsoft Endpoint Configuration Manager 2012/2012 R2/1511/1602**.</span></span>
    
5. <span data-ttu-id="126f2-174">Wählen **Sie Paket herunterladen** aus, und speichern Sie .zip Datei.</span><span class="sxs-lookup"><span data-stu-id="126f2-174">Select **Download package**, and save the .zip file.</span></span>

6. <span data-ttu-id="126f2-175">Extrahieren Sie den Inhalt der .zip an einen freigegebenen, schreibgeschützten Speicherort, auf den die Netzwerkadministratoren zugreifen können, die das Paket bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="126f2-175">Extract the contents of the .zip file to a shared, read-only location that can be accessed by the network administrators who will deploy the package.</span></span> <span data-ttu-id="126f2-176">Sie sollten über eine Datei namens *DeviceComplianceOffboardingScript_valid_until_YYYY-MM-DD.cmd verfügen.*</span><span class="sxs-lookup"><span data-stu-id="126f2-176">You should have a file named *DeviceComplianceOffboardingScript_valid_until_YYYY-MM-DD.cmd*.</span></span>

7. <span data-ttu-id="126f2-177">Stellen Sie das Paket zur Verfügung, indem Sie die Schritte im Artikel Pakete und Programme [in System Center 2012 R2 Configuration Manager](/previous-versions/system-center/system-center-2012-R2/gg699369(v=technet.10)) ausführen.</span><span class="sxs-lookup"><span data-stu-id="126f2-177">Deploy the package by following the steps in the [Packages and Programs in System Center 2012 R2 Configuration Manager](/previous-versions/system-center/system-center-2012-R2/gg699369(v=technet.10)) article.</span></span>

8. <span data-ttu-id="126f2-178">Wählen Sie eine vordefinierte Gerätesammlung aus, auf der das Paket bereitgestellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="126f2-178">Choose a predefined device collection to deploy the package to.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="126f2-179">Offboarding bewirkt, dass das Gerät das Senden von Sensordaten an das Portal beendet, aber Daten vom Gerät, einschließlich Verweis auf alle Warnungen, die es erhalten hat, werden für bis zu 6 Monate aufbewahrt.</span><span class="sxs-lookup"><span data-stu-id="126f2-179">Offboarding causes the device to stop sending sensor data to the portal but data from the device, including reference to any alerts it has had will be retained for up to 6 months.</span></span>


## <a name="monitor-device-configuration"></a><span data-ttu-id="126f2-180">Überwachen der Gerätekonfiguration</span><span class="sxs-lookup"><span data-stu-id="126f2-180">Monitor device configuration</span></span>

<span data-ttu-id="126f2-181">Wenn Sie die aktuelle Microsoft Endpoint Configuration Manager verwenden, verwenden Sie das integrierte Microsoft Defender for Endpoint-Dashboard in der Configuration Manager-Konsole.</span><span class="sxs-lookup"><span data-stu-id="126f2-181">If you're using Microsoft Endpoint Configuration Manager current branch, use the built-in Microsoft Defender for Endpoint dashboard in the Configuration Manager console.</span></span> <span data-ttu-id="126f2-182">Weitere Informationen finden Sie unter [Microsoft Defender Advanced Threat Protection - Monitor](/configmgr/protect/deploy-use/windows-defender-advanced-threat-protection#monitor).</span><span class="sxs-lookup"><span data-stu-id="126f2-182">For more information, see [Microsoft Defender Advanced Threat Protection - Monitor](/configmgr/protect/deploy-use/windows-defender-advanced-threat-protection#monitor).</span></span>

<span data-ttu-id="126f2-183">Wenn Sie den System Center 2012 R2 Configuration Manager verwenden, besteht die Überwachung aus zwei Teilen:</span><span class="sxs-lookup"><span data-stu-id="126f2-183">If you're using System Center 2012 R2 Configuration Manager, monitoring consists of two parts:</span></span>

1. <span data-ttu-id="126f2-184">Bestätigen, dass das Konfigurationspaket ordnungsgemäß bereitgestellt wurde und auf den Geräten in Ihrem Netzwerk ausgeführt wird (oder erfolgreich ausgeführt wurde).</span><span class="sxs-lookup"><span data-stu-id="126f2-184">Confirming the configuration package has been correctly deployed and is running (or has successfully run) on the devices in your network.</span></span>

2. <span data-ttu-id="126f2-185">Überprüfen, ob die Geräte mit dem Microsoft 365 Endpoint Data Loss Prevention Service kompatibel sind (dadurch wird sichergestellt, dass das Gerät den Onboardingprozess abschließen und weiterhin Daten an den Dienst melden kann).</span><span class="sxs-lookup"><span data-stu-id="126f2-185">Checking that the devices are compliant with the Microsoft 365 Endpoint data loss prevention service (this ensures the device can complete the onboarding process and can continue to report data to the service).</span></span>

### <a name="confirm-the-configuration-package-has-been-correctly-deployed"></a><span data-ttu-id="126f2-186">Bestätigen, dass das Konfigurationspaket ordnungsgemäß bereitgestellt wurde</span><span class="sxs-lookup"><span data-stu-id="126f2-186">Confirm the configuration package has been correctly deployed</span></span>

1. <span data-ttu-id="126f2-187">Klicken Sie in der Configuration Manager-Konsole unten **im** Navigationsbereich auf Überwachung.</span><span class="sxs-lookup"><span data-stu-id="126f2-187">In the Configuration Manager console, click **Monitoring** at the bottom of the navigation pane.</span></span>

2. <span data-ttu-id="126f2-188">Wählen **Sie Übersicht** und dann **Bereitstellungen aus.**</span><span class="sxs-lookup"><span data-stu-id="126f2-188">Select **Overview** and then **Deployments**.</span></span>

3. <span data-ttu-id="126f2-189">Wählen Sie die Bereitstellung mit dem Paketnamen aus.</span><span class="sxs-lookup"><span data-stu-id="126f2-189">Select on the deployment with the package name.</span></span>

4. <span data-ttu-id="126f2-190">Überprüfen Sie die Statusindikatoren unter **Abschlussstatistik** und **Inhaltsstatus**.</span><span class="sxs-lookup"><span data-stu-id="126f2-190">Review the status indicators under **Completion Statistics** and **Content Status**.</span></span>

    <span data-ttu-id="126f2-191">Bei fehlgeschlagenen Bereitstellungen (Geräte mit **Fehler,** **Nicht** erfüllten Anforderungen oder fehlgeschlagenen **Status)** müssen Sie möglicherweise Probleme mit den Geräten beheben.</span><span class="sxs-lookup"><span data-stu-id="126f2-191">If there are failed deployments (devices with **Error**, **Requirements Not Met**, or **Failed statuses**), you may need to  troubleshoot the devices.</span></span> <span data-ttu-id="126f2-192">Weitere Informationen finden Sie unter [Troubleshoot Microsoft Defender Advanced Threat Protection onboarding issues](/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding).</span><span class="sxs-lookup"><span data-stu-id="126f2-192">For more information, see, [Troubleshoot Microsoft Defender Advanced Threat Protection onboarding issues](/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding).</span></span>

    ![Configuration Manager zeigt eine erfolgreiche Bereitstellung ohne Fehler an](../media/sccm-deployment.png)

### <a name="check-that-the-devices-are-compliant-with-the-microsoft-365-endpoint-data-loss-prevention-service"></a><span data-ttu-id="126f2-194">Überprüfen Sie, ob die Geräte mit dem Microsoft 365 Endpoint Data Loss Prevention Service kompatibel sind.</span><span class="sxs-lookup"><span data-stu-id="126f2-194">Check that the devices are compliant with the Microsoft 365 Endpoint data loss prevention service</span></span>

<span data-ttu-id="126f2-195">Sie können eine Kompatibilitätsregel für konfigurationselement in System Center 2012 R2 Configuration Manager festlegen, um Ihre Bereitstellung zu überwachen.</span><span class="sxs-lookup"><span data-stu-id="126f2-195">You can set a compliance rule for configuration item in System Center 2012 R2 Configuration Manager to monitor your deployment.</span></span>

> [!NOTE]
> <span data-ttu-id="126f2-196">Dieses Verfahren und der Registrierungseintrag gelten für Endpoint DLP sowie Advanced Threat Protection.</span><span class="sxs-lookup"><span data-stu-id="126f2-196">This procedure and registry entry applies to Endpoint DLP as well as Advanced Threat Protection.</span></span>

<span data-ttu-id="126f2-197">Bei dieser Regel sollte es sich um ein Konfigurationselement *zur Nichtbehendung* der Complianceregel, das den Wert eines Registrierungsschlüssels auf zielgerichteten Geräten überwacht.</span><span class="sxs-lookup"><span data-stu-id="126f2-197">This rule should be a *non-remediating* compliance rule configuration item that monitors the value of a registry key on targeted devices.</span></span>

<span data-ttu-id="126f2-198">Überwachen Sie den folgenden Registrierungsschlüsseleintrag:</span><span class="sxs-lookup"><span data-stu-id="126f2-198">Monitor the following registry key entry:</span></span>
```
Path: “HKLM\SOFTWARE\Microsoft\Windows Advanced Threat Protection\Status”
Name: “OnboardingState”
Value: “1”
```
<span data-ttu-id="126f2-199">Weitere Informationen finden Sie unter [Einführung in Complianceeinstellungen in System Center 2012 R2 Configuration Manager](/previous-versions/system-center/system-center-2012-R2/gg682139(v=technet.10)).</span><span class="sxs-lookup"><span data-stu-id="126f2-199">For more information, see [Introduction to compliance settings in System Center 2012 R2 Configuration Manager](/previous-versions/system-center/system-center-2012-R2/gg682139(v=technet.10)).</span></span>

## <a name="related-topics"></a><span data-ttu-id="126f2-200">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="126f2-200">Related topics</span></span>
- [<span data-ttu-id="126f2-201">Onboarding Windows 10 Geräte mithilfe von Gruppenrichtlinien</span><span class="sxs-lookup"><span data-stu-id="126f2-201">Onboard Windows 10 devices using Group Policy</span></span>](dlp-configure-endpoints-gp.md)
- [<span data-ttu-id="126f2-202">Onboarding von Windows 10-Geräten mithilfe von Tools für die Verwaltung von Mobilgeräten</span><span class="sxs-lookup"><span data-stu-id="126f2-202">Onboard Windows 10 devices using Mobile Device Management tools</span></span>](dlp-configure-endpoints-mdm.md)
- [<span data-ttu-id="126f2-203">Onboarding von Windows 10-Geräten mithilfe eines lokalen Skripts</span><span class="sxs-lookup"><span data-stu-id="126f2-203">Onboard Windows 10 devices using a local script</span></span>](dlp-configure-endpoints-script.md)
- [<span data-ttu-id="126f2-204">Onboarding von nicht-persistenten Geräten einer VD-Infrastruktur (Virtual Desktop)</span><span class="sxs-lookup"><span data-stu-id="126f2-204">Onboard non-persistent virtual desktop infrastructure (VDI) devices</span></span>](dlp-configure-endpoints-vdi.md)
- [<span data-ttu-id="126f2-205">Ausführen eines Erkennungstests auf einem neu integrierten Microsoft Defender for Endpoint-Gerät</span><span class="sxs-lookup"><span data-stu-id="126f2-205">Run a detection test on a newly onboarded Microsoft Defender for Endpoint device</span></span>](/windows/security/threat-protection/microsoft-defender-atp/run-detection-test)
- [<span data-ttu-id="126f2-206">Problembehandlung bei Microsoft Defender Advanced Threat Protection Onboardingproblemen</span><span class="sxs-lookup"><span data-stu-id="126f2-206">Troubleshoot Microsoft Defender Advanced Threat Protection onboarding issues</span></span>](/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding)