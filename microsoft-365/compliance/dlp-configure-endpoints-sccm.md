---
title: Integrierte Windows 10-Geräte mithilfe von Configuration Manager
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
description: Verwenden Sie den Konfigurations-Manager, um das Konfigurationspaket auf Geräten bereitzustellen, damit Sie für den Dienst an Bord sind.
ms.openlocfilehash: ea1b0cba10dc3e7120192e0c0ee87e2e354f1cc2
ms.sourcegitcommit: 6647055154002c7d3b8f7ce25ad53c9636bc8066
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/27/2020
ms.locfileid: "48769478"
---
# <a name="onboard-windows-10-devices-using-configuration-manager"></a><span data-ttu-id="e7d3a-103">Integrierte Windows 10-Geräte mithilfe von Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="e7d3a-103">Onboard Windows 10 devices using Configuration Manager</span></span>

<span data-ttu-id="e7d3a-104">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="e7d3a-104">**Applies to:**</span></span>

- [<span data-ttu-id="e7d3a-105">Microsoft 365 Endpunkt-Datenverlust Verhinderung (DLP)</span><span class="sxs-lookup"><span data-stu-id="e7d3a-105">Microsoft 365 Endpoint data loss prevention (DLP)</span></span>](/microsoft-365/compliance/endpoint-dlp-learn-about)
- <span data-ttu-id="e7d3a-106">System Center 2012 R2 Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="e7d3a-106">System Center 2012 R2 Configuration Manager</span></span>

### <a name="onboard-devices-using-system-center-configuration-manager"></a><span data-ttu-id="e7d3a-107">Integrierte Geräte mithilfe von System Center Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="e7d3a-107">Onboard devices using System Center Configuration Manager</span></span>

1. <span data-ttu-id="e7d3a-108">Öffnen Sie die ZIP-Datei des Configuration Manager-Konfigurationspakets ( *DeviceComplianceOnboardingPackage.zip* ), die Sie aus dem Dienst-Onboarding-Assistenten heruntergeladen haben.</span><span class="sxs-lookup"><span data-stu-id="e7d3a-108">Open the Configuration Manager configuration package .zip file ( *DeviceComplianceOnboardingPackage.zip* ) that you downloaded from the service onboarding wizard.</span></span> <span data-ttu-id="e7d3a-109">Sie können das Paket auch aus dem [Microsoft Compliance Center](https://compliance.microsoft.com/)abrufen.</span><span class="sxs-lookup"><span data-stu-id="e7d3a-109">You can also get the package from [Microsoft Compliance center](https://compliance.microsoft.com/).</span></span>

2. <span data-ttu-id="e7d3a-110">Wählen Sie im Navigationsbereich die Option **Einstellungen** für das  >  **Onboarding von Geräten** aus  >  **Onboarding** .</span><span class="sxs-lookup"><span data-stu-id="e7d3a-110">In the navigation pane, select **Settings** > **Device Onboarding** > **Onboarding** .</span></span>

3. <span data-ttu-id="e7d3a-111">Wählen Sie im Feld **Bereitstellungsmethode** den **Microsoft Endpoint Configuration Manager 2012/2012 R2/1511/1602** aus.</span><span class="sxs-lookup"><span data-stu-id="e7d3a-111">In the **Deployment method** field, select **Microsoft Endpoint Configuration Manager 2012/2012 R2/1511/1602** .</span></span>
 
4. <span data-ttu-id="e7d3a-112">Wählen Sie **Paket herunterladen** aus, und speichern Sie die ZIP-Datei.</span><span class="sxs-lookup"><span data-stu-id="e7d3a-112">Select **Download package** , and save the .zip file.</span></span>

5. <span data-ttu-id="e7d3a-113">Extrahieren Sie den Inhalt der ZIP-Datei an einen freigegebenen, schreibgeschützten Speicherort, auf den die Netzwerkadministratoren zugreifen können, die das Paket bereitstellen werden.</span><span class="sxs-lookup"><span data-stu-id="e7d3a-113">Extract the contents of the .zip file to a shared, read-only location that can be accessed by the network administrators who will deploy the package.</span></span> <span data-ttu-id="e7d3a-114">Sie sollten über eine Datei mit dem Namen " *DeviceComplianceOnboardingScript. cmd* " verfügen.</span><span class="sxs-lookup"><span data-stu-id="e7d3a-114">You should have a file named *DeviceComplianceOnboardingScript.cmd* .</span></span>

6. <span data-ttu-id="e7d3a-115">Stellen Sie das Paket bereit, indem Sie die Schritte im Artikel [Pakete und Programme in System Center 2012 R2 Configuration Manager](https://docs.microsoft.com/previous-versions/system-center/system-center-2012-R2/gg699369\(v=technet.10\)) ausführen.</span><span class="sxs-lookup"><span data-stu-id="e7d3a-115">Deploy the package by following the steps in the [Packages and Programs in System Center 2012 R2 Configuration Manager](https://docs.microsoft.com/previous-versions/system-center/system-center-2012-R2/gg699369\(v=technet.10\)) article.</span></span>

7. <span data-ttu-id="e7d3a-116">Wählen Sie eine vordefinierte gerätesammlung aus, in der das Paket bereitgestellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="e7d3a-116">Choose a predefined device collection to deploy the package to.</span></span>

> [!NOTE]
> <span data-ttu-id="e7d3a-117">Die Microsoft 365-Endpunkt Datenverlust-Verhinderung unterstützt Onboarding während der [out-of-Box-Erfahrungs Phase (OOBE)](https://answers.microsoft.com/en-us/windows/wiki/windows_10/how-to-complete-the-windows-10-out-of-box/47e3f943-f000-45e3-8c5c-9d85a1a0cf87) nicht.</span><span class="sxs-lookup"><span data-stu-id="e7d3a-117">Microsoft 365 Endpoint data loss prevention doesn't support onboarding during the [Out-Of-Box Experience (OOBE)](https://answers.microsoft.com/en-us/windows/wiki/windows_10/how-to-complete-the-windows-10-out-of-box/47e3f943-f000-45e3-8c5c-9d85a1a0cf87) phase.</span></span> <span data-ttu-id="e7d3a-118">Stellen Sie sicher, dass die Benutzer die OOBE nach Ausführung der Windows-Installation oder Aktualisierung vollständig ausführen.</span><span class="sxs-lookup"><span data-stu-id="e7d3a-118">Make sure users complete OOBE after running Windows installation or upgrading.</span></span>

>[!TIP]
> <span data-ttu-id="e7d3a-119">Nach dem Onboarding des Geräts können Sie einen Erkennungstest ausführen, um zu überprüfen, ob ein Gerät ordnungsgemäß mit dem Dienst an Bord ist.</span><span class="sxs-lookup"><span data-stu-id="e7d3a-119">After onboarding the device, you can choose to run a detection test to verify that an device is properly onboarded to the service.</span></span> <span data-ttu-id="e7d3a-120">Weitere Informationen finden Sie unter [Ausführen eines Erkennungstests auf einem neu integrierten Microsoft Defender-ATP-Gerät](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/run-detection-test).</span><span class="sxs-lookup"><span data-stu-id="e7d3a-120">For more information, see [Run a detection test on a newly onboarded Microsoft Defender ATP device](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/run-detection-test).</span></span>
>
> <span data-ttu-id="e7d3a-121">Beachten Sie, dass es möglich ist, eine Erkennungsregel für eine Configuration Manager-Anwendung zu erstellen, um kontinuierlich zu überprüfen, ob ein Gerät onboarded war.</span><span class="sxs-lookup"><span data-stu-id="e7d3a-121">Note that it is possible to create a detection rule on a Configuration Manager application to continuously check if a device has been onboarded.</span></span> <span data-ttu-id="e7d3a-122">Eine Anwendung ist ein anderer Objekttyp als ein Paket und Programm.</span><span class="sxs-lookup"><span data-stu-id="e7d3a-122">An application is a different type of object than a package and program.</span></span>
> <span data-ttu-id="e7d3a-123">Wenn ein Gerät noch nicht an Bord ist (aufgrund einer ausstehenden OOBE-Fertigstellung oder aus einem anderen Grund), versucht Configuration Manager, das Gerät an Bord zu führen, bis die Regel die Statusänderung erkennt.</span><span class="sxs-lookup"><span data-stu-id="e7d3a-123">If a device is not yet onboarded (due to pending OOBE completion or any other reason), Configuration Manager will retry to onboard the device until the rule detects the status change.</span></span>
> 
> <span data-ttu-id="e7d3a-124">Dieses Verhalten kann durch Erstellen einer Erkennungsregel überprüft werden, wenn der Registrierungswert "OnboardingState" (vom Typ REG_DWORD) = 1 ist.</span><span class="sxs-lookup"><span data-stu-id="e7d3a-124">This behavior can be accomplished by creating a detection rule checking if the "OnboardingState" registry value (of type REG_DWORD) = 1.</span></span>
> <span data-ttu-id="e7d3a-125">Dieser Registrierungswert befindet sich unter "HKLM\Software\Microsoft\Windows Advanced Threat Protection\Status".</span><span class="sxs-lookup"><span data-stu-id="e7d3a-125">This registry value is located under "HKLM\SOFTWARE\Microsoft\Windows Advanced Threat Protection\Status".</span></span>
<span data-ttu-id="e7d3a-126">Weitere Informationen finden Sie unter [configure detection methods in System Center 2012 R2 Configuration Manager](https://docs.microsoft.com/previous-versions/system-center/system-center-2012-R2/gg682159\(v=technet.10\)#step-4-configure-detection-methods-to-indicate-the-presence-of-the-deployment-type).</span><span class="sxs-lookup"><span data-stu-id="e7d3a-126">For more information, see [Configure Detection Methods in System Center 2012 R2 Configuration Manager](https://docs.microsoft.com/previous-versions/system-center/system-center-2012-R2/gg682159\(v=technet.10\)#step-4-configure-detection-methods-to-indicate-the-presence-of-the-deployment-type).</span></span>

### <a name="configure-sample-collection-settings"></a><span data-ttu-id="e7d3a-127">Konfigurieren von Einstellungen für die Beispielsammlung</span><span class="sxs-lookup"><span data-stu-id="e7d3a-127">Configure sample collection settings</span></span>

<span data-ttu-id="e7d3a-128">Sie können für jedes Gerät einen Konfigurationswert festlegen, um anzugeben, ob Proben vom Gerät erfasst werden können, wenn eine Anforderung über das Microsoft Defender Security Center gestellt wird, um eine Datei zur tiefen Analyse zu übermitteln.</span><span class="sxs-lookup"><span data-stu-id="e7d3a-128">For each device, you can set a configuration value to state whether samples can be collected from the device when a request is made through Microsoft Defender Security Center to submit a file for deep analysis.</span></span>

>[!NOTE]
><span data-ttu-id="e7d3a-129">Diese Konfigurationseinstellungen werden normalerweise über den Konfigurations-Manager ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="e7d3a-129">These configuration settings are typically done through Configuration Manager.</span></span> 

<span data-ttu-id="e7d3a-130">Sie können eine Konformitätsregel für das Konfigurationselement in Configuration Manager festlegen, um die Beispiel Freigabe Einstellung auf einem Gerät zu ändern.</span><span class="sxs-lookup"><span data-stu-id="e7d3a-130">You can set a compliance rule for configuration item in Configuration Manager to change the sample share setting on a device.</span></span>

<span data-ttu-id="e7d3a-131">Bei dieser Regel muss es sich um ein Konfigurationselement für die richtlinienkonforme Konformitätsregel handeln, das den Wert eines Registrierungsschlüssels auf Zielgeräten festlegt, um sicherzustellen, dass es sich *um eine Reklamation* handelt.</span><span class="sxs-lookup"><span data-stu-id="e7d3a-131">This rule should be a *remediating* compliance rule configuration item that sets the value of a registry key on targeted devices to make sure they’re complaint.</span></span>

<span data-ttu-id="e7d3a-132">Die Konfiguration wird über den folgenden Registrierungsschlüsseleintrag festgelegt:</span><span class="sxs-lookup"><span data-stu-id="e7d3a-132">The configuration is set through the following registry key entry:</span></span>

```
Path: “HKLM\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection”
Name: "AllowSampleCollection"
Value: 0 or 1
```
<span data-ttu-id="e7d3a-133">Dabei gilt:</span><span class="sxs-lookup"><span data-stu-id="e7d3a-133">Where:</span></span><br>
<span data-ttu-id="e7d3a-134">Key-Typ ist ein D-Wort.</span><span class="sxs-lookup"><span data-stu-id="e7d3a-134">Key type is a D-WORD.</span></span> <br>
<span data-ttu-id="e7d3a-135">Die folgenden Werte sind möglich:</span><span class="sxs-lookup"><span data-stu-id="e7d3a-135">Possible values are:</span></span>
- <span data-ttu-id="e7d3a-136">0 – die Beispiel Freigabe für dieses Gerät wird nicht zugelassen.</span><span class="sxs-lookup"><span data-stu-id="e7d3a-136">0 - doesn't allow sample sharing  from this device</span></span>
- <span data-ttu-id="e7d3a-137">1-ermöglicht die Freigabe aller Dateitypen von diesem Gerät</span><span class="sxs-lookup"><span data-stu-id="e7d3a-137">1 - allows sharing of all file types from this device</span></span>

<span data-ttu-id="e7d3a-138">Der Standardwert für den Fall, dass der Registrierungsschlüssel nicht vorhanden ist, ist 1.</span><span class="sxs-lookup"><span data-stu-id="e7d3a-138">The default value in case the registry key doesn’t exist is 1.</span></span>

<span data-ttu-id="e7d3a-139">Weitere Informationen zur Compliance von System Center Configuration Manager finden Sie unter [Introduction to Compliance Settings in System Center 2012 R2 Configuration Manager](https://docs.microsoft.com/previous-versions/system-center/system-center-2012-R2/gg682139\(v=technet.10\)).</span><span class="sxs-lookup"><span data-stu-id="e7d3a-139">For more information about System Center Configuration Manager Compliance, see [Introduction to compliance settings in System Center 2012 R2 Configuration Manager](https://docs.microsoft.com/previous-versions/system-center/system-center-2012-R2/gg682139\(v=technet.10\)).</span></span>


## <a name="other-recommended-configuration-settings"></a><span data-ttu-id="e7d3a-140">Weitere empfohlene Konfigurationseinstellungen</span><span class="sxs-lookup"><span data-stu-id="e7d3a-140">Other recommended configuration settings</span></span>
<span data-ttu-id="e7d3a-141">Nachdem Sie die Onboarding-Geräte für den Dienst verwendet haben, ist es wichtig, dass Sie die enthaltenen Funktionen zum Schutz vor Bedrohungen nutzen, indem Sie Sie mit den folgenden empfohlenen Konfigurationseinstellungen aktivieren.</span><span class="sxs-lookup"><span data-stu-id="e7d3a-141">After onboarding devices to the service, it's important to take advantage of the included threat protection capabilities by enabling them with the following recommended configuration settings.</span></span>

### <a name="device-collection-configuration"></a><span data-ttu-id="e7d3a-142">Konfiguration der gerätesammlung</span><span class="sxs-lookup"><span data-stu-id="e7d3a-142">Device collection configuration</span></span>
<span data-ttu-id="e7d3a-143">Wenn Sie den Endpunkt Konfigurations-Manager (Version 2002 oder höher) verwenden, können Sie die Bereitstellung erweitern, um Server oder untergeordnete Clients einzubeziehen.</span><span class="sxs-lookup"><span data-stu-id="e7d3a-143">If you're using Endpoint Configuration Manager, version 2002 or later, you can choose to broaden the deployment to include servers or down-level clients.</span></span>


### <a name="next-generation-protection-configuration"></a><span data-ttu-id="e7d3a-144">Schutzkonfiguration der nächsten Generation</span><span class="sxs-lookup"><span data-stu-id="e7d3a-144">Next generation protection configuration</span></span>

<span data-ttu-id="e7d3a-145">Die folgenden Konfigurationseinstellungen werden empfohlen:</span><span class="sxs-lookup"><span data-stu-id="e7d3a-145">The following configuration settings are recommended:</span></span>

<span data-ttu-id="e7d3a-146">**Überprüfung**</span><span class="sxs-lookup"><span data-stu-id="e7d3a-146">**Scan**</span></span>

- <span data-ttu-id="e7d3a-147">Scannen von Wechselmediengeräten wie USB-Laufwerken: Ja</span><span class="sxs-lookup"><span data-stu-id="e7d3a-147">Scan removable storage devices such as USB drives: Yes</span></span>

<span data-ttu-id="e7d3a-148">**Echtzeitschutz**</span><span class="sxs-lookup"><span data-stu-id="e7d3a-148">**Real-time Protection**</span></span>

- <span data-ttu-id="e7d3a-149">Aktivieren der Verhaltensüberwachung: Ja</span><span class="sxs-lookup"><span data-stu-id="e7d3a-149">Enable Behavioral Monitoring: Yes</span></span>
- <span data-ttu-id="e7d3a-150">Aktivieren des Schutzes vor potenziell unerwünschten Anwendungen beim Herunterladen und vor der Installation: Ja</span><span class="sxs-lookup"><span data-stu-id="e7d3a-150">Enable protection against Potentially Unwanted Applications at download and prior to installation: Yes</span></span>

<span data-ttu-id="e7d3a-151">**Cloud Protection-Dienst**</span><span class="sxs-lookup"><span data-stu-id="e7d3a-151">**Cloud Protection Service**</span></span>

- <span data-ttu-id="e7d3a-152">Typ der Cloud Protection-Dienst Mitgliedschaft: erweiterte Mitgliedschaft</span><span class="sxs-lookup"><span data-stu-id="e7d3a-152">Cloud Protection Service membership type: Advanced membership</span></span>

<span data-ttu-id="e7d3a-153">**Angriffsflächen Reduzierung** Konfigurieren Sie alle verfügbaren Regeln für die Überwachung.</span><span class="sxs-lookup"><span data-stu-id="e7d3a-153">**Attack surface reduction** Configure all available rules to Audit.</span></span>

>[!NOTE]
> <span data-ttu-id="e7d3a-154">Das Blockieren dieser Aktivitäten kann legitime Geschäftsprozesse unterbrechen.</span><span class="sxs-lookup"><span data-stu-id="e7d3a-154">Blocking these activities may interrupt legitimate business processes.</span></span> <span data-ttu-id="e7d3a-155">Der beste Ansatz besteht darin, alles für die Überwachung festzulegen, zu ermitteln, welche sicher aktiviert werden sollen, und diese Einstellungen dann auf Endpunkten zu aktivieren, die keine falsch positiven Erkennungen aufweisen.</span><span class="sxs-lookup"><span data-stu-id="e7d3a-155">The best approach is setting everything to audit, identifying which ones are safe to turn on, and then enabling those settings on endpoints which do not have false positive detections.</span></span>

<span data-ttu-id="e7d3a-156">**Netzwerkschutz**</span><span class="sxs-lookup"><span data-stu-id="e7d3a-156">**Network protection**</span></span>

<span data-ttu-id="e7d3a-157">Vor dem Aktivieren von Netzwerkschutz im Überwachungs-oder Blockierungs Modus müssen Sie sicherstellen, dass Sie das Platt Form Update für Antischadsoftware installiert haben, das auf der [Support Seite](https://support.microsoft.com/en-us/help/4560203/windows-defender-anti-malware-platform-binaries-are-missing)abgerufen werden kann.</span><span class="sxs-lookup"><span data-stu-id="e7d3a-157">Prior to enabling network protection in audit or block mode, ensure that you've installed the antimalware platform update, which can be obtained from the [support page](https://support.microsoft.com/en-us/help/4560203/windows-defender-anti-malware-platform-binaries-are-missing).</span></span>


<span data-ttu-id="e7d3a-158">**Zugriff auf kontrollierte Ordner**</span><span class="sxs-lookup"><span data-stu-id="e7d3a-158">**Controlled folder access**</span></span>

<span data-ttu-id="e7d3a-159">Aktivieren Sie das Feature für mindestens 30 Tage im Überwachungsmodus.</span><span class="sxs-lookup"><span data-stu-id="e7d3a-159">Enable the feature in audit mode for at least 30 days.</span></span> <span data-ttu-id="e7d3a-160">Überprüfen Sie nach diesem Zeitraum Erkennungen, und erstellen Sie eine Liste der Anwendungen, die in geschützte Verzeichnisse schreiben dürfen.</span><span class="sxs-lookup"><span data-stu-id="e7d3a-160">After this period, review detections and create a list of applications that are allowed to write to protected directories.</span></span>

<span data-ttu-id="e7d3a-161">Weitere Informationen finden Sie unter [evaluieren des Zugriffs auf kontrollierte Ordner](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/evaluate-controlled-folder-access).</span><span class="sxs-lookup"><span data-stu-id="e7d3a-161">For more information, see [Evaluate controlled folder access](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/evaluate-controlled-folder-access).</span></span>


## <a name="offboard-devices-using-configuration-manager"></a><span data-ttu-id="e7d3a-162">Extern-Geräte mithilfe von Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="e7d3a-162">Offboard devices using Configuration Manager</span></span>

<span data-ttu-id="e7d3a-163">Aus Sicherheitsgründen läuft das Paket, das für extern-Geräte verwendet wird, 30 Tage nach dem heruntergeladenen Datum ab.</span><span class="sxs-lookup"><span data-stu-id="e7d3a-163">For security reasons, the package used to Offboard devices will expire 30 days after the date it was downloaded.</span></span> <span data-ttu-id="e7d3a-164">Abgelaufene offboarding-Pakete, die an ein Gerät gesendet werden, werden zurückgewiesen.</span><span class="sxs-lookup"><span data-stu-id="e7d3a-164">Expired offboarding packages sent to a device will be rejected.</span></span> <span data-ttu-id="e7d3a-165">Wenn Sie ein offboarding-Paket herunterladen, werden Sie über das Ablaufdatum der Pakete benachrichtigt, und es wird auch in den Paketnamen eingeschlossen.</span><span class="sxs-lookup"><span data-stu-id="e7d3a-165">When downloading an offboarding package, you will be notified of the packages expiry date and it will also be included in the package name.</span></span>

> [!NOTE]
> <span data-ttu-id="e7d3a-166">Onboarding-und offboarding-Richtlinien dürfen nicht gleichzeitig auf demselben Gerät bereitgestellt werden, da dies andernfalls zu unvorhersehbaren Konflikten führen kann.</span><span class="sxs-lookup"><span data-stu-id="e7d3a-166">Onboarding and offboarding policies must not be deployed on the same device at the same time, otherwise this will cause unpredictable collisions.</span></span>

### <a name="offboard-devices-using-microsoft-endpoint-configuration-manager-current-branch"></a><span data-ttu-id="e7d3a-167">Extern-Geräte mit dem aktuellen Zweig "Microsoft Endpoint Configuration Manager"</span><span class="sxs-lookup"><span data-stu-id="e7d3a-167">Offboard devices using Microsoft Endpoint Configuration Manager current branch</span></span>

<span data-ttu-id="e7d3a-168">Wenn Sie den aktuellen Zweig Microsoft Endpoint Configuration Manager verwenden, lesen Sie [Erstellen einer offboarding-Konfigurationsdatei](https://docs.microsoft.com/configmgr/protect/deploy-use/windows-defender-advanced-threat-protection#create-an-offboarding-configuration-file).</span><span class="sxs-lookup"><span data-stu-id="e7d3a-168">If you use Microsoft Endpoint Configuration Manager current branch, see [Create an offboarding configuration file](https://docs.microsoft.com/configmgr/protect/deploy-use/windows-defender-advanced-threat-protection#create-an-offboarding-configuration-file).</span></span>

### <a name="offboard-devices-using-system-center-2012-r2-configuration-manager"></a><span data-ttu-id="e7d3a-169">Extern-Geräte mit System Center 2012 R2-Konfigurations-Manager</span><span class="sxs-lookup"><span data-stu-id="e7d3a-169">Offboard devices using System Center 2012 R2 Configuration Manager</span></span>

1. <span data-ttu-id="e7d3a-170">Rufen Sie das offboarding-Paket im [Microsoft Compliance Center](https://compliance.microsoft.com/)ab:</span><span class="sxs-lookup"><span data-stu-id="e7d3a-170">Get the offboarding package from [Microsoft Compliance center](https://compliance.microsoft.com/):</span></span>

2. <span data-ttu-id="e7d3a-171">Wählen Sie im Navigationsbereich **Einstellungen**  >   **Gerät Onboarding** >  **Offboarding** .</span><span class="sxs-lookup"><span data-stu-id="e7d3a-171">In the navigation pane, select **Settings** >  **Device onboarding**> **Offboarding** .</span></span>

3. <span data-ttu-id="e7d3a-172">Wählen Sie als Betriebssystem Windows 10 aus.</span><span class="sxs-lookup"><span data-stu-id="e7d3a-172">Select Windows 10 as the operating system.</span></span>

4. <span data-ttu-id="e7d3a-173">Wählen Sie im Feld **Bereitstellungsmethode** den **Microsoft Endpoint Configuration Manager 2012/2012 R2/1511/1602** aus.</span><span class="sxs-lookup"><span data-stu-id="e7d3a-173">In the **Deployment method** field, select **Microsoft Endpoint Configuration Manager 2012/2012 R2/1511/1602** .</span></span>
    
5. <span data-ttu-id="e7d3a-174">Wählen Sie **Paket herunterladen** aus, und speichern Sie die ZIP-Datei.</span><span class="sxs-lookup"><span data-stu-id="e7d3a-174">Select **Download package** , and save the .zip file.</span></span>

6. <span data-ttu-id="e7d3a-175">Extrahieren Sie den Inhalt der ZIP-Datei an einen freigegebenen, schreibgeschützten Speicherort, auf den die Netzwerkadministratoren zugreifen können, die das Paket bereitstellen werden.</span><span class="sxs-lookup"><span data-stu-id="e7d3a-175">Extract the contents of the .zip file to a shared, read-only location that can be accessed by the network administrators who will deploy the package.</span></span> <span data-ttu-id="e7d3a-176">Sie sollten über eine Datei mit dem Namen *DeviceComplianceOffboardingScript_valid_until_YYYY-mm-dd. cmd* verfügen.</span><span class="sxs-lookup"><span data-stu-id="e7d3a-176">You should have a file named *DeviceComplianceOffboardingScript_valid_until_YYYY-MM-DD.cmd* .</span></span>

7. <span data-ttu-id="e7d3a-177">Stellen Sie das Paket bereit, indem Sie die Schritte im Artikel [Pakete und Programme in System Center 2012 R2 Configuration Manager](https://docs.microsoft.com/previous-versions/system-center/system-center-2012-R2/gg699369\(v=technet.10\)) ausführen.</span><span class="sxs-lookup"><span data-stu-id="e7d3a-177">Deploy the package by following the steps in the [Packages and Programs in System Center 2012 R2 Configuration Manager](https://docs.microsoft.com/previous-versions/system-center/system-center-2012-R2/gg699369\(v=technet.10\)) article.</span></span>

8. <span data-ttu-id="e7d3a-178">Wählen Sie eine vordefinierte gerätesammlung aus, in der das Paket bereitgestellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="e7d3a-178">Choose a predefined device collection to deploy the package to.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e7d3a-179">Offboarding bewirkt, dass das Gerät das Senden von Sensordaten an das Portal beendet, aber die Daten des Geräts, einschließlich des Verweises auf bereits gemachte Warnungen, werden bis zu 6 Monate aufbewahrt.</span><span class="sxs-lookup"><span data-stu-id="e7d3a-179">Offboarding causes the device to stop sending sensor data to the portal but data from the device, including reference to any alerts it has had will be retained for up to 6 months.</span></span>


## <a name="monitor-device-configuration"></a><span data-ttu-id="e7d3a-180">Überwachen der Gerätekonfiguration</span><span class="sxs-lookup"><span data-stu-id="e7d3a-180">Monitor device configuration</span></span>

<span data-ttu-id="e7d3a-181">Wenn Sie den Microsoft Endpoint Configuration Manager Current Branch verwenden, verwenden Sie das integrierte Microsoft Defender ATP-Dashboard in der Configuration Manager-Konsole.</span><span class="sxs-lookup"><span data-stu-id="e7d3a-181">If you're using Microsoft Endpoint Configuration Manager current branch, use the built-in Microsoft Defender ATP dashboard in the Configuration Manager console.</span></span> <span data-ttu-id="e7d3a-182">Weitere Informationen finden Sie unter [Advanced Threat Protection-Monitor von Microsoft Defender](https://docs.microsoft.com/configmgr/protect/deploy-use/windows-defender-advanced-threat-protection#monitor).</span><span class="sxs-lookup"><span data-stu-id="e7d3a-182">For more information, see [Microsoft Defender Advanced Threat Protection - Monitor](https://docs.microsoft.com/configmgr/protect/deploy-use/windows-defender-advanced-threat-protection#monitor).</span></span>

<span data-ttu-id="e7d3a-183">Wenn Sie den System Center 2012 R2-Konfigurations-Manager verwenden, besteht die Überwachung aus zwei Teilen:</span><span class="sxs-lookup"><span data-stu-id="e7d3a-183">If you're using System Center 2012 R2 Configuration Manager, monitoring consists of two parts:</span></span>

1. <span data-ttu-id="e7d3a-184">Bestätigen, dass das Konfigurationspaket ordnungsgemäß bereitgestellt wurde und auf den Geräten in Ihrem Netzwerk ausgeführt (oder erfolgreich ausgeführt wurde).</span><span class="sxs-lookup"><span data-stu-id="e7d3a-184">Confirming the configuration package has been correctly deployed and is running (or has successfully run) on the devices in your network.</span></span>

2. <span data-ttu-id="e7d3a-185">Überprüfen, ob die Geräte mit dem Microsoft 365 Endpoint Data Loss Prevention-Dienst kompatibel sind (Dadurch wird sichergestellt, dass das Gerät den Onboarding-Prozess abschließen kann und weiterhin Daten an den Dienst melden kann).</span><span class="sxs-lookup"><span data-stu-id="e7d3a-185">Checking that the devices are compliant with the Microsoft 365 Endpoint data loss prevention service (this ensures the device can complete the onboarding process and can continue to report data to the service).</span></span>

### <a name="confirm-the-configuration-package-has-been-correctly-deployed"></a><span data-ttu-id="e7d3a-186">Bestätigen, dass das Konfigurationspaket ordnungsgemäß bereitgestellt wurde</span><span class="sxs-lookup"><span data-stu-id="e7d3a-186">Confirm the configuration package has been correctly deployed</span></span>

1. <span data-ttu-id="e7d3a-187">Klicken Sie in der Configuration Manager-Konsole unten im Navigationsbereich auf **Überwachung** .</span><span class="sxs-lookup"><span data-stu-id="e7d3a-187">In the Configuration Manager console, click **Monitoring** at the bottom of the navigation pane.</span></span>

2. <span data-ttu-id="e7d3a-188">Wählen Sie **Übersicht** und dann **Bereitstellungen** aus.</span><span class="sxs-lookup"><span data-stu-id="e7d3a-188">Select **Overview** and then **Deployments** .</span></span>

3. <span data-ttu-id="e7d3a-189">Wählen Sie auf der Bereitstellung mit dem Paketnamen aus.</span><span class="sxs-lookup"><span data-stu-id="e7d3a-189">Select on the deployment with the package name.</span></span>

4. <span data-ttu-id="e7d3a-190">Überprüfen Sie die Statusindikatoren unter **abschlussstatistik** und **Inhaltsstatus** .</span><span class="sxs-lookup"><span data-stu-id="e7d3a-190">Review the status indicators under **Completion Statistics** and **Content Status** .</span></span>

    <span data-ttu-id="e7d3a-191">Bei fehlgeschlagenen Bereitstellungen (Geräte mit **Fehlern** , **Anforderungen nicht erfüllt** oder **Status Fehler** ) müssen Sie möglicherweise eine Problembehandlung für die Geräte durchzuführen.</span><span class="sxs-lookup"><span data-stu-id="e7d3a-191">If there are failed deployments (devices with **Error** , **Requirements Not Met** , or **Failed statuses** ), you may need to  troubleshoot the devices.</span></span> <span data-ttu-id="e7d3a-192">Weitere Informationen finden Sie unter [Problembehandlung bei Onboarding-Problemen bei Microsoft Defender Advanced Threat Protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding).</span><span class="sxs-lookup"><span data-stu-id="e7d3a-192">For more information, see, [Troubleshoot Microsoft Defender Advanced Threat Protection onboarding issues](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding).</span></span>

    ![Konfigurations-Manager zeigt eine erfolgreiche Bereitstellung ohne Fehler](../media/sccm-deployment.png)

### <a name="check-that-the-devices-are-compliant-with-the-microsoft-365-endpoint-data-loss-prevention-service"></a><span data-ttu-id="e7d3a-194">Überprüfen, ob die Geräte mit dem Microsoft 365 Endpoint Data Loss Prevention-Dienst kompatibel sind</span><span class="sxs-lookup"><span data-stu-id="e7d3a-194">Check that the devices are compliant with the Microsoft 365 Endpoint data loss prevention service</span></span>

<span data-ttu-id="e7d3a-195">Sie können eine Konformitätsregel für das Konfigurationselement in System Center 2012 R2 Configuration Manager festlegen, um Ihre Bereitstellung zu überwachen.</span><span class="sxs-lookup"><span data-stu-id="e7d3a-195">You can set a compliance rule for configuration item in System Center 2012 R2 Configuration Manager to monitor your deployment.</span></span>

> [!NOTE]
> <span data-ttu-id="e7d3a-196">Diese Prozedur und der Registrierungseintrag gelten sowohl für die Endpunkt-DLP-Installation als auch für Advanced Threat Protection.</span><span class="sxs-lookup"><span data-stu-id="e7d3a-196">This procedure and registry entry applies to Endpoint DLP as well as Advanced Threat Protection.</span></span>

<span data-ttu-id="e7d3a-197">Diese Regel sollte ein Konfigurationselement für *die Konformitäts* Regel sein, das den Wert eines Registrierungsschlüssels auf Zielgeräten überwacht.</span><span class="sxs-lookup"><span data-stu-id="e7d3a-197">This rule should be a *non-remediating* compliance rule configuration item that monitors the value of a registry key on targeted devices.</span></span>

<span data-ttu-id="e7d3a-198">Überwachen Sie den folgenden Registrierungsschlüsseleintrag:</span><span class="sxs-lookup"><span data-stu-id="e7d3a-198">Monitor the following registry key entry:</span></span>
```
Path: “HKLM\SOFTWARE\Microsoft\Windows Advanced Threat Protection\Status”
Name: “OnboardingState”
Value: “1”
```
<span data-ttu-id="e7d3a-199">Weitere Informationen finden Sie unter [Introduction to Compliance Settings in System Center 2012 R2 Configuration Manager](https://docs.microsoft.com/previous-versions/system-center/system-center-2012-R2/gg682139\(v=technet.10\)).</span><span class="sxs-lookup"><span data-stu-id="e7d3a-199">For more information, see [Introduction to compliance settings in System Center 2012 R2 Configuration Manager](https://docs.microsoft.com/previous-versions/system-center/system-center-2012-R2/gg682139\(v=technet.10\)).</span></span>

## <a name="related-topics"></a><span data-ttu-id="e7d3a-200">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="e7d3a-200">Related topics</span></span>
- [<span data-ttu-id="e7d3a-201">Integrierte Windows 10-Geräte mithilfe von Gruppenrichtlinien</span><span class="sxs-lookup"><span data-stu-id="e7d3a-201">Onboard Windows 10 devices using Group Policy</span></span>](dlp-configure-endpoints-gp.md)
- [<span data-ttu-id="e7d3a-202">Integrierte Windows 10-Geräte mit Tools zur Verwaltung mobiler Geräte</span><span class="sxs-lookup"><span data-stu-id="e7d3a-202">Onboard Windows 10 devices using Mobile Device Management tools</span></span>](dlp-configure-endpoints-mdm.md)
- [<span data-ttu-id="e7d3a-203">Onboard-Windows 10-Geräte mithilfe eines lokalen Skripts</span><span class="sxs-lookup"><span data-stu-id="e7d3a-203">Onboard Windows 10 devices using a local script</span></span>](dlp-configure-endpoints-script.md)
- [<span data-ttu-id="e7d3a-204">Onboard-VDI-Geräte (Non-persistent Virtual Desktop Infrastructure)</span><span class="sxs-lookup"><span data-stu-id="e7d3a-204">Onboard non-persistent virtual desktop infrastructure (VDI) devices</span></span>](dlp-configure-endpoints-vdi.md)
- [<span data-ttu-id="e7d3a-205">Ausführen eines Erkennungstests auf einem neu integrierten Microsoft Defender-ATP-Gerät</span><span class="sxs-lookup"><span data-stu-id="e7d3a-205">Run a detection test on a newly onboarded Microsoft Defender ATP device</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/run-detection-test)
- [<span data-ttu-id="e7d3a-206">Problembehandlung bei Onboarding-Problemen bei Microsoft Defender Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="e7d3a-206">Troubleshoot Microsoft Defender Advanced Threat Protection onboarding issues</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding)
