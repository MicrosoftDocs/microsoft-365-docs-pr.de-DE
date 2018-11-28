---
title: Bereitstellen von Windows 10 Enterprise für vorhandene Geräte als direktes Upgrade
description: Enthält Anleitungen zum Konfigurieren und Bereitstellen einer Windows 10 Enterprise Abbilds mithilfe von System Center Configuration Manager als ein direktes Upgrade.
keywords: Microsoft 365 Microsoft 365 Enterprise Microsoft 365 Dokumentation, Windows 10 Enterprise-Bereitstellung in-Place Upgrade vom Konfigurations-Manager, System Center Configuration Manager
author: greg-lindsay
localization_priority: Normal
audience: microsoft-business
ms.prod: microsoft-365-enterprise
ms.topic: article
ms.date: 08/30/2018
ms.author: greglin
ms.openlocfilehash: 35ec8b0d8452d1f448283c5e27c4028a07829253
ms.sourcegitcommit: df0ed4e9097acfee3cb128882102b3081144eb68
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/11/2018
ms.locfileid: "23938720"
---
# <a name="step-2-deploy-windows-10-enterprise-for-existing-devices-as-an-in-place-upgrade"></a><span data-ttu-id="db780-104">Schritt 2: Stellen Sie Windows 10 Enterprise für vorhandene Geräte als direktes Upgrade bereit</span><span class="sxs-lookup"><span data-stu-id="db780-104">Step 2: Deploy Windows 10 Enterprise for existing devices as an in-place upgrade</span></span>

<span data-ttu-id="db780-105">*Dieser Abschnitt gilt für die Versionen E3 und E5 von Microsoft 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="db780-105">*This article applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

![](./media/deploy-foundation-infrastructure/win10enterprise_icon-small.png)

<span data-ttu-id="db780-p101">Der einfachste Pfad zum Upgraden von PCs, die derzeit ausgeführten Windows 7 oder Windows 8.1 bis 10 für Windows wird über ein direktes Upgrade. Eine Aufgabensequenz System Center Configuration Manager (Konfigurations-Manager) können Sie um den Prozess zu automatisieren.</span><span class="sxs-lookup"><span data-stu-id="db780-p101">The simplest path to upgrade PCs currently running Windows 7 or Windows 8.1 to Windows 10 is through an in-place upgrade. You can use a System Center Configuration Manager (Configuration Manager) task sequence to completely automate the process.</span></span> 

<span data-ttu-id="db780-p102">Wenn Sie vorhandene Computer unter Windows 7 oder Windows 8.1 verfügen, empfehlen wir diesen Pfad Wenn Ihre Organisation Windows 10 bereitgestellt wird. Dies nutzt die Windows-Installationsprogramm (Setup.exe) zum Ausführen eines direkten Upgrades und automatisch, alle Daten, die Einstellungen, die Anwendungen behält, und die Treiber aus der vorhandenen Version des Betriebssystems. Dies erfordert den geringsten Aufwand für die IT, da es keine Notwendigkeit jeder komplexen Bereitstellung-Infrastruktur besteht.</span><span class="sxs-lookup"><span data-stu-id="db780-p102">If you have existing computers running Windows 7 or Windows 8.1, we recommend this path if your organization is deploying Windows 10. This leverages the Windows installation program (Setup.exe) to perform an in-place upgrade, which automatically preserves all data, settings, applications, and drivers from the existing operating system version. This requires the least IT effort, because there is no need for any complex deployment infrastructure.</span></span>

<span data-ttu-id="db780-111">Befolgen Sie diese Schritte zum Konfigurieren und Bereitstellen einer Windows 10 Enterprise Bild von Configuration Manager als ein direktes Upgrade aus.</span><span class="sxs-lookup"><span data-stu-id="db780-111">Follow these steps to configure and deploy a Windows 10 Enterprise image using Configuration Manager as an in-place upgrade.</span></span>

## <a name="part-1-verify-readiness-to-upgrade-windows"></a><span data-ttu-id="db780-112">Teil 1: Überprüfen Sie die Bereitschaft für das Aktualisieren von Windows</span><span class="sxs-lookup"><span data-stu-id="db780-112">Part 1: Verify readiness to upgrade Windows</span></span>

<span data-ttu-id="db780-p103">Zunächst, mit dem die Möglichkeit zum Upgrade Bereitschaft Windows Analytics bieten leistungsstarke Insights und Empfehlungen zu Computer, Anwendungen und Treiber in Ihrer Organisation, ohne zusätzliche Kosten und ohne zusätzliche infrastrukturanforderungen. Dieser neue Dienst führt Sie durch Verwenden eines Workflows basierend auf von Microsoft empfohlene Methoden für Upgrade und Feature Update Projekte. Auf dem neuesten Stand Bestandsdaten können Sie einen Lastenausgleich Kosten und Risiken in Ihrer Upgrade-Projekte.</span><span class="sxs-lookup"><span data-stu-id="db780-p103">First, use the Upgrade Readiness capability of Windows Analytics to provide powerful insights and recommendations about the computers, applications, and drivers in your organization, at no extra cost and without additional infrastructure requirements. This new service guides you through upgrade and feature update projects using a workflow based on Microsoft recommended practices. Up-to-date inventory data allows you to balance cost and risk in your upgrade projects.</span></span>

<span data-ttu-id="db780-116">Erfahren mehr, erste Schritte, verwenden und aktualisieren Bereitschaft Problembehandlung finden Sie unter [Verwalten von Windows-Upgrades mit Bereitschaft aktualisieren](https://docs.microsoft.com/windows/deployment/upgrade/manage-windows-upgrades-with-upgrade-readiness) .</span><span class="sxs-lookup"><span data-stu-id="db780-116">See [Manage Windows upgrades with Upgrade Readiness](https://docs.microsoft.com/windows/deployment/upgrade/manage-windows-upgrades-with-upgrade-readiness) to learn more, get started, use, and troubleshoot Upgrade Readiness.</span></span>

<span data-ttu-id="db780-p104">Im nächsten Schritt führen Sie im Handbuch für System Center Configuration Manager (aktuelle Zweig) zum Aktualisieren von Windows 7 oder höher auf Windows 10 verwenden, um ein. Wie bei jeder Bereitstellung mit hohem Risiko wird empfohlen, Sichern von Benutzerdaten, bevor Sie fortfahren. OneDrive-Cloud-Speicher ist für lizenzierte Benutzer von Microsoft 365 verwenden und kann verwendet werden, um ihre Dateien sicher zu speichern. Weitere Informationen finden Sie unter [OneDrive quick start Guide](https://aka.ms/ODfBquickstartguide). Um auf diese Seite zuzugreifen, müssen Sie als Administrator oder als globaler Administrator in einem Office 365 oder Microsoft 365-Mandanten anmelden.</span><span class="sxs-lookup"><span data-stu-id="db780-p104">Next, follow the guide to use System Center Configuration Manager (Current Branch) to upgrade Windows 7 or later operating system to Windows 10. As with any high-risk deployment, we recommend backing up user data before proceeding. OneDrive cloud storage is ready to use for licensed Microsoft 365 users and can be used to securely store their files. For more info, see [OneDrive quick start guide](https://aka.ms/ODfBquickstartguide). To access this page, you must sign in as a tenant admin or global admin in an Office 365 or Microsoft 365 tenant.</span></span>

<span data-ttu-id="db780-122">Eine Liste der Konfigurations-Manager sowie den entsprechenden Windows 10-Client-Versionen, die unterstützt werden, finden Sie unter [Unterstützung für Windows 10 für System Center Configuration Manager](https://aka.ms/supportforwin10sccm).</span><span class="sxs-lookup"><span data-stu-id="db780-122">For a list of Configuration Manager versions and the corresponding Windows 10 client versions that are supported, see [Support for Windows 10 for System Center Configuration Manager](https://aka.ms/supportforwin10sccm).</span></span>

<span data-ttu-id="db780-123">**So überprüfen Sie die Bereitschaft für das Aktualisieren von Windows**</span><span class="sxs-lookup"><span data-stu-id="db780-123">**To verify readiness to upgrade Windows**</span></span>

<span data-ttu-id="db780-124">Lesen Sie diesen Anforderungen vor dem Starten der Windows-10-bereitstellungs:</span><span class="sxs-lookup"><span data-stu-id="db780-124">Review these requirements before starting your Windows 10 deployment:</span></span>

- <span data-ttu-id="db780-p105">**Aktualisieren Sie für die Windows-Editionen** - Gerät müssen Editionen von Windows 7 oder Windows 8.1, die für ein Upgrade auf Windows 10 Enterprise kommen ausgeführt werden. Eine Liste der unterstützten Editionen finden Sie unter [Windows 10 Pfade zu aktualisieren](https://aka.ms/win10upgradepaths).</span><span class="sxs-lookup"><span data-stu-id="db780-p105">**Windows editions eligible for upgrade** - Your devices must be running editions of Windows 7 or Windows 8.1 that are eligible for upgrade to Windows 10 Enterprise. For a list of supported editions, see [Windows 10 upgrade paths](https://aka.ms/win10upgradepaths).</span></span> 
- <span data-ttu-id="db780-p106">**Unterstützte Geräte** - die meisten Computer, die mit Windows 8.1 kompatibel sind, werden mit Windows 10 kompatibel sein. Sie müssen möglicherweise aktualisierte Treiber für Ihre Geräte ordnungsgemäß-Funktion in Windows 10 installieren. Weitere Informationen finden Sie unter [Windows 10 Spezifikationen](https://aka.ms/windows10specifications) .</span><span class="sxs-lookup"><span data-stu-id="db780-p106">**Supported devices** - Most computers that are compatible with Windows 8.1 will be compatible with Windows 10. You may need to install updated drivers in Windows 10 for your devices to properly function. See [Windows 10 specifications](https://aka.ms/windows10specifications) for more info.</span></span>
- <span data-ttu-id="db780-130">**Vorbereiten der Bereitstellung** - stellen Sie sicher, dass die folgenden vor die Bereitstellung konfigurieren:</span><span class="sxs-lookup"><span data-stu-id="db780-130">**Deployment preparation** - Make sure you have the following before you start configuring the deployment:</span></span>
    - <span data-ttu-id="db780-p107">Windows-10-Installationsmedien - den Installationsmedien müssen auf einem separaten Laufwerk, mit der bereits bereitgestellt ISO befinden. Sie können die ISO aus [Downloads für MSDN-Abonnenten](https://aka.ms/msdn-subscriber-downloads) oder aus dem [Volume Licensing Service Center](https://aka.ms/mvlsc)abrufen.</span><span class="sxs-lookup"><span data-stu-id="db780-p107">Windows 10 installation media - The installation media must be located on a separate drive, with the ISO already mounted. You can obtain the ISO from [MSDN Subscriber Downloads](https://aka.ms/msdn-subscriber-downloads) or from the [Volume Licensing Service Center](https://aka.ms/mvlsc).</span></span>
    - <span data-ttu-id="db780-p108">Sicherungen von Benutzerdaten - zwar Benutzerdaten in das Upgrade migriert werden bewährte Methode zum Konfigurieren einer Sicherung Szenarios ist. Exportieren Sie beispielsweise alle Benutzerdaten in einer OneDrive-Konto, BitLocker To Go-verschlüsselten USB-Laufwerk oder Netzwerk-Dateiserver. Weitere Informationen finden Sie unter [Sichern oder Übertragen von Daten in Windows](https://aka.ms/backuptransferdatawindows).</span><span class="sxs-lookup"><span data-stu-id="db780-p108">Backups of user data - Although user data will be migrated in the upgrade, best practice is to configure a backup scenario. For example, export all user data to a OneDrive account, BitLocker To Go-encrypted USB flash drive, or network file server. For more information, see [Back up or transfer data in Windows](https://aka.ms/backuptransferdatawindows).</span></span>
- <span data-ttu-id="db780-p109">**Vorbereitung der Umgebung** - verwenden Sie eine vorhandene Serverstruktur des Konfigurations-Manager-zur Vorbereitung der Bereitstellung eines Betriebssystems. Zusätzlich zu den Basisinstallation sollte in der Configuration Manager-Umgebung die folgenden Konfigurationen vorgenommen werden:</span><span class="sxs-lookup"><span data-stu-id="db780-p109">**Environment preparation** - You will use an existing Configuration Manager server structure to prepare for operating system deployment. In addition to the base setup, the following configurations should be made in the Configuration Manager environment:</span></span>
    1. <span data-ttu-id="db780-138">[Active Directory-Schema erweitern](https://aka.ms/extendadschema) und [Erstellen Sie einen System Management Container](https://aka.ms/createsysmancontainer).</span><span class="sxs-lookup"><span data-stu-id="db780-138">[Extend the Active Directory Schema](https://aka.ms/extendadschema) and [create a System Management container](https://aka.ms/createsysmancontainer).</span></span>
    2. <span data-ttu-id="db780-p110">Active Directory-Gesamtstruktur aktivieren Discovery und Active Directory-System-Erkennung. Weitere Informationen finden Sie unter [Configure-Discovery-Methoden für System Center Configuration Manager](https://aka.ms/configurediscoverymethods).</span><span class="sxs-lookup"><span data-stu-id="db780-p110">Enable Active Directory Forest Discovery and Active Directory System Discovery. For more info, see [Configure discovery methods for System Center Configuration Manager](https://aka.ms/configurediscoverymethods).</span></span>
    3. <span data-ttu-id="db780-p111">IP-Bereich Beschränkungen und Grenzgruppe für Inhalte und Website-Zuordnung zu erstellen. Weitere Informationen finden Sie unter [Define Website Beschränkungen und Grenzgruppen für System Center Configuration Manager](https://aka.ms/definesiteboundaries).</span><span class="sxs-lookup"><span data-stu-id="db780-p111">Create IP range boundaries and boundary group for content and site assignment. For more info, see [Define site boundaries and boundary groups for System Center Configuration Manager](https://aka.ms/definesiteboundaries).</span></span>
    4. <span data-ttu-id="db780-p112">Fügen Sie hinzu und konfigurieren Sie den Konfigurations-Manager reporting Services-Punkt-Rolle. Weitere Informationen finden Sie unter [Konfigurieren von Reporting im Konfigurations-Manager](https://aka.ms/configurereporting).</span><span class="sxs-lookup"><span data-stu-id="db780-p112">Add and configure the Configuration Manager reporting services point role. For more info, see [Configuring Reporting in Configuration Manager](https://aka.ms/configurereporting).</span></span>
    5. <span data-ttu-id="db780-145">Erstellen Sie eine Ordner Dateisystemstruktur für Pakete.</span><span class="sxs-lookup"><span data-stu-id="db780-145">Create a file system folder structure for packages.</span></span>
    6. <span data-ttu-id="db780-146">Erstellen Sie eine Ordnerstruktur des Konfigurations-Manager-Konsole für Pakete.</span><span class="sxs-lookup"><span data-stu-id="db780-146">Create a Configuration Manager console folder structure for packages.</span></span>
    7. <span data-ttu-id="db780-147">Installieren von System Center Configuration Manager (aktuelle Zweig) Updates und zusätzlichen Windows 10 erforderliche Komponenten.</span><span class="sxs-lookup"><span data-stu-id="db780-147">Install System Center Configuration Manager (Current Branch) updates and any additional Windows 10 prerequisites.</span></span>

## <a name="part-2-add-a-windows-10-os-image-using-configuration-manager"></a><span data-ttu-id="db780-148">Teil 2: Hinzufügen ein Windows 10-Betriebssystemabbilds von Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="db780-148">Part 2: Add a Windows 10 OS image using Configuration Manager</span></span>
<span data-ttu-id="db780-p113">Jetzt müssen Sie ein Betriebssystem Aktualisierungspaket erstellen, die das vollständige Windows-10-Installationsmedium enthält. Konfigurations-Manager verwenden Sie in den folgenden Schritten erstellen ein Upgrade-Paket für Windows 10 Enterprise X64.</span><span class="sxs-lookup"><span data-stu-id="db780-p113">Now you'll need to create an operating system upgrade package that contains the full Windows 10 installation media. In the following steps, you’ll use Configuration Manager to create an upgrade package for Windows 10 Enterprise x64.</span></span>

<span data-ttu-id="db780-151">**So fügen Sie ein Windows 10-Betriebssystemabbild von Configuration Manager hinzu**</span><span class="sxs-lookup"><span data-stu-id="db780-151">**To add a Windows 10 OS image using Configuration Manager**</span></span>

1. <span data-ttu-id="db780-152">Die Konfigurations-Manager-Konsole im Arbeitsbereich **Software Library** rechten Maustaste auf den Knoten **Betriebssystem aktualisieren Pakete** , und wählen Sie dann **Betriebssystem Aktualisierungspaket hinzufügen**aus.</span><span class="sxs-lookup"><span data-stu-id="db780-152">Using the Configuration Manager console, in the **Software Library** workspace, right-click the **Operating System Upgrade Packages** node, and then select **Add Operating System Upgrade Package**.</span></span>
2. <span data-ttu-id="db780-153">Klicken Sie auf der Seite **Datenquelle** Geben Sie UNC-Pfad zu Windows 10 Enterprise X64 Mediums an, und wählen Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="db780-153">On the **Data Source** page, specify the UNC path to the Windows 10 Enterprise x64 media, and then select **Next**.</span></span>
3. <span data-ttu-id="db780-154">Klicken Sie auf der Seite **Allgemein** Geben Sie **Windows 10 Enterprise X64 aktualisieren**, und wählen Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="db780-154">On the **General** page, specify **Windows 10 Enterprise x64 Upgrade**, and then select **Next**.</span></span> 
4. <span data-ttu-id="db780-155">Klicken Sie auf der Seite **Zusammenfassung** wählen Sie **Weiter**aus, und wählen Sie dann auf **Schließen**.</span><span class="sxs-lookup"><span data-stu-id="db780-155">On the **Summary** page, select **Next**, and then select **Close**.</span></span> 
5. <span data-ttu-id="db780-156">Mit der rechten Maustaste in des erstellten **Windows 10 Enterprise X64 Update** -Pakets, und wählen Sie dann auf **Content verteilen**.</span><span class="sxs-lookup"><span data-stu-id="db780-156">Right-click the created **Windows 10 Enterprise x64 Update** package, and then select **Distribute Content**.</span></span> 
6. <span data-ttu-id="db780-157">Wählen Sie Ihre Verteilungspunkt aus.</span><span class="sxs-lookup"><span data-stu-id="db780-157">Choose your distribution point.</span></span>

## <a name="part-3-configure-deployment-settings"></a><span data-ttu-id="db780-158">Teil 3: Konfigurieren der Einstellungen für die Bereitstellung</span><span class="sxs-lookup"><span data-stu-id="db780-158">Part 3: Configure deployment settings</span></span>
<span data-ttu-id="db780-p114">In diesem Schritt fügen Sie ein Upgrade Aufgabensequenz konfigurieren, die Einstellungen für das Upgrade von Windows 10 enthält. Sie identifizieren Sie die Geräte zu aktualisieren, und klicken Sie dann die Abfolge der Vorgänge für diese Geräte bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="db780-p114">In this step, you'll configure an upgrade task sequence that contains the settings for the Windows 10 upgrade. You'll then identify the devices to upgrade, and then deploy the task sequence to those devices.</span></span>

### <a name="create-a-task-sequence"></a><span data-ttu-id="db780-161">Erstellen einer Aufgabensequenz</span><span class="sxs-lookup"><span data-stu-id="db780-161">Create a task sequence</span></span>
<span data-ttu-id="db780-162">So erstellen Sie ein Upgrade Aufgabensequenz, führen Sie die folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="db780-162">To create an upgrade task sequence, perform the following steps:</span></span>
  
1. <span data-ttu-id="db780-163">Erweitern Sie in der Configuration Manager-Konsole, klicken Sie im Arbeitsbereich **Software Library** **Betriebssysteme**.</span><span class="sxs-lookup"><span data-stu-id="db780-163">In the Configuration Manager console, in the **Software Library** workspace, expand **Operating Systems**.</span></span> 
2. <span data-ttu-id="db780-164">Maustaste auf den Knoten **Task Sequences** , und wählen Sie dann auf **Task Sequence erstellen**.</span><span class="sxs-lookup"><span data-stu-id="db780-164">Right-click the **Task Sequences** node, and then select **Create Task Sequence**.</span></span>
3. <span data-ttu-id="db780-165">Wählen Sie auf der Seite **Erstellen einer neuen Aufgabensequenz** **ein Betriebssystem aus Aktualisierungspaket aktualisieren**, und wählen Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="db780-165">On the **Create a new task sequence** page, select **Upgrade an operating system from upgrade package**, and then select **Next**.</span></span>
4. <span data-ttu-id="db780-166">Klicken Sie auf der Seite **Task Sequence Informationen** Geben Sie **Windows 10 Enterprise X64 aktualisieren**, und wählen Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="db780-166">On the **Task Sequence Information** page, specify **Windows 10 Enterprise x64 Upgrade**, and then select **Next**.</span></span>
5. <span data-ttu-id="db780-167">Klicken Sie auf der Seite **Aktualisieren des Windows-Betriebssystems** wählen Sie **Durchsuchen** und wählen Sie das **Upgrade Betriebssystem Windows 10 Enterprise X64 upgrade-Pakets**, wählen Sie **OK**aus, und wählen Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="db780-167">On the **Upgrade the Windows operating system** page, select **Browse** and choose the **Windows 10 Enterprise x64 Upgrade operating system upgrade package**, select **OK**, and then select **Next**.</span></span>
6. <span data-ttu-id="db780-168">Folgen Sie den restlichen Seiten des Assistenten, und wählen Sie dann auf **Schließen**.</span><span class="sxs-lookup"><span data-stu-id="db780-168">Continue through the remaining wizard pages, and then select **Close**.</span></span>

### <a name="create-a-device-collection"></a><span data-ttu-id="db780-169">Erstellen Sie eine Gerät-Auflistung</span><span class="sxs-lookup"><span data-stu-id="db780-169">Create a device collection</span></span>
<span data-ttu-id="db780-170">Nachdem Sie die Upgrade-Task Sequence erstellt haben, müssen Sie eine Auflistung erstellen, die Geräte enthält, die Sie upgraden.</span><span class="sxs-lookup"><span data-stu-id="db780-170">After you create the upgrade task sequence, you'll need to create a collection that contains the devices you will upgrade.</span></span>

> [!NOTE]
> <span data-ttu-id="db780-p115">Verwenden Sie die folgenden Einstellungen zum Testen der Bereitstellung auf einem einzigen Gerät. Regeln für die verschiedenen Mitgliedschaft können Sie Gruppen von Geräten zählen, wenn Sie bereit sind. Weitere Informationen finden Sie unter [Sammlungen in System Center Configuration Manager zu erstellen](https://aka.ms/sccm-create-collections).</span><span class="sxs-lookup"><span data-stu-id="db780-p115">Use the following settings to test the deployment on a single device. You can use different membership rules to include groups of devices when you are ready. For more info, see [How to create collections in System Center Configuration Manager](https://aka.ms/sccm-create-collections).</span></span>

1. <span data-ttu-id="db780-174">In der Configuration Manager-Konsole, klicken Sie im Arbeitsbereich **Ressourcen und Compliance** mit der rechten Maustaste **Gerät Sammlungen**, und wählen Sie dann auf **Geräte-Sammlung erstellen**.</span><span class="sxs-lookup"><span data-stu-id="db780-174">In the Configuration Manager console, in the **Assets and Compliance** workspace, right-click **Device Collections**, and then select **Create Device Collection**.</span></span> 
2. <span data-ttu-id="db780-175">Im Gerät-Sammlung erstellen-Assistenten auf der Seite **Allgemein** Geben Sie die folgenden Einstellungen, und wählen Sie dann auf **Weiter**:</span><span class="sxs-lookup"><span data-stu-id="db780-175">In the Create Device Collection wizard, on the **General** page, enter the following settings and then select **Next**:</span></span>
    - <span data-ttu-id="db780-176">Name: Windows 10 Enterprise X64 Upgrade</span><span class="sxs-lookup"><span data-stu-id="db780-176">Name: Windows 10 Enterprise x64 Upgrade</span></span>
    - <span data-ttu-id="db780-177">Einschränkende Auflistung: Alle Systeme</span><span class="sxs-lookup"><span data-stu-id="db780-177">Limiting Collection: All Systems</span></span>
3. <span data-ttu-id="db780-178">Wählen Sie auf der Seite **Regeln für die Mitgliedschaft** **Regel hinzufügen** > **direkte Regel** zum Starten des Assistenten für die Erstellung direkter Mitgliedschaft.</span><span class="sxs-lookup"><span data-stu-id="db780-178">On the **Membership Rules** page, select **Add Rule** > **Direct rule** to launch the Create Direct Membership Rule Wizard.</span></span>
4. <span data-ttu-id="db780-179">Wählen Sie auf der Seite **Willkommen** des Assistenten für die Erstellung direkter Mitgliedschaft **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="db780-179">On the **Welcome** page of the Create Direct Membership Rule Wizard, select **Next**.</span></span>
5. <span data-ttu-id="db780-180">Geben Sie auf der Seite **Ressourcen suchen** Sie die folgenden Einstellungen, und ersetzen den Platzhaltertext **Wert** Text mit dem Namen des Geräts, die Sie aktualisieren:</span><span class="sxs-lookup"><span data-stu-id="db780-180">On the **Search for Resources** page, enter the following settings, replacing the placeholder **Value** text with the name of the device you are upgrading:</span></span> 
    - <span data-ttu-id="db780-181">Resource-Klasse: Systemressource</span><span class="sxs-lookup"><span data-stu-id="db780-181">Resource Class: System Resource</span></span>
    - <span data-ttu-id="db780-182">Attribut Name: Name</span><span class="sxs-lookup"><span data-stu-id="db780-182">Attribute Name: Name</span></span>
    - <span data-ttu-id="db780-183">Wert: *PC0003*</span><span class="sxs-lookup"><span data-stu-id="db780-183">Value: *PC0003*</span></span>
6. <span data-ttu-id="db780-184">Klicken Sie auf der Seite **Ressourcen auswählen** wählen Sie das Gerät, und wählen Sie **Weiter**aus.</span><span class="sxs-lookup"><span data-stu-id="db780-184">On the **Select Resources** page, select your device, and select **Next**.</span></span>
7. <span data-ttu-id="db780-185">Führen Sie den Assistenten für direkte Mitgliedschaftsregel erstellen und den Assistenten zum Erstellen eines Geräts-Auflistung.</span><span class="sxs-lookup"><span data-stu-id="db780-185">Complete the Create Direct Membership Rule wizard and the Create Device Collection Wizard.</span></span>  
8. <span data-ttu-id="db780-p116">Überprüfen der Aktualisierung Windows 10 Enterprise X64-Auflistung. Führen Sie nicht fortgesetzt werden, bis Sie die Computer sehen Sie in der Auflistung hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="db780-p116">Review the Windows 10 Enterprise x64 Upgrade collection. Do not continue until you see the machines you added in the collection.</span></span>

### <a name="create-an-operating-system-deployment"></a><span data-ttu-id="db780-188">Erstellen einer bereitstellungs eines Betriebssystems</span><span class="sxs-lookup"><span data-stu-id="db780-188">Create an operating system deployment</span></span>
<span data-ttu-id="db780-189">Befolgen Sie diese Schritte, um eine Bereitstellung für die Abfolge der Vorgänge zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="db780-189">Follow these steps to create a deployment for the task sequence.</span></span>

1. <span data-ttu-id="db780-190">In der Configuration Manager-Konsole, klicken Sie im Arbeitsbereich **Softwarebibliothek** mit der rechten Maustaste die Abfolge der Vorgänge, die Sie in einem vorherigen Schritt erstellt haben, und wählen Sie dann auf **Bereitstellen**.</span><span class="sxs-lookup"><span data-stu-id="db780-190">In the Configuration Manager console, in the **Software Library** workspace, right-click the task sequence you created in a previous step, and then select **Deploy**.</span></span>
2. <span data-ttu-id="db780-191">Wählen Sie auf der Seite **Allgemein** die Sammlung **Windows 10 Enterprise X64 aktualisieren** , und wählen Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="db780-191">On the **General** page, select the **Windows 10 Enterprise x64 Upgrade** collection, and then select **Next**.</span></span>
3. <span data-ttu-id="db780-192">Wählen Sie auf der Seite **Inhalt** **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="db780-192">On the **Content** page, select **Next**.</span></span>
4. <span data-ttu-id="db780-193">Klicken Sie auf der Seite **Einstellungen für die Bereitstellung** wählen Sie die folgenden Einstellungen, und wählen Sie dann auf **Weiter**:</span><span class="sxs-lookup"><span data-stu-id="db780-193">On the **Deployment Settings** page, select the following settings, and then select **Next**:</span></span>

    > [!NOTE]
    > <span data-ttu-id="db780-p117">Für diese testbereitstellung wird den Zweck **verfügbar**, festlegen auf die zum Starten der bereitstellungs Benutzereingriff erforderlich sind. Möglicherweise möchten Sie automatisieren die Bereitstellung mithilfe des erforderlichen zwecks, der umfasst die Konfiguration zusätzlicher Optionen wie bei Ausführung die Bereitstellung planen, in einer produktionsumgebung.</span><span class="sxs-lookup"><span data-stu-id="db780-p117">For this test deployment, you'll set the purpose to **Available**, which requires user intervention to start the deployment. In a production environment, you may wish to automate the deployment using the Required purpose, which involves configuring additional options such as scheduling when the deployment is run.</span></span> 

    - <span data-ttu-id="db780-196">Aktion: Installieren</span><span class="sxs-lookup"><span data-stu-id="db780-196">Action: Install</span></span>
    - <span data-ttu-id="db780-197">Zweck: verfügbar</span><span class="sxs-lookup"><span data-stu-id="db780-197">Purpose: Available</span></span>

5. <span data-ttu-id="db780-198">Klicken Sie auf der Seite **Planung** übernehmen Sie die Standardeinstellungen, und wählen Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="db780-198">On the **Scheduling** page, accept the default settings, and then select **Next**.</span></span>
6. <span data-ttu-id="db780-199">Übernehmen Sie auf der Seite **Benutzer** die Standardeinstellungen, und wählen Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="db780-199">On the **User Experience** page, accept the default settings, and then select **Next**.</span></span>
7. <span data-ttu-id="db780-200">Klicken Sie auf der Seite **Warnungen** übernehmen Sie die Standardeinstellungen, und wählen Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="db780-200">On the **Alerts** page, accept the default settings, and then select **Next**.</span></span>
8. <span data-ttu-id="db780-201">Klicken Sie auf der Seite **Zusammenfassung** wählen Sie **Weiter**aus, und wählen Sie dann auf **Schließen**.</span><span class="sxs-lookup"><span data-stu-id="db780-201">On the **Summary** page, select **Next**, and then select **Close**.</span></span>

## <a name="part-5-start-the-windows-10-upgrade-task-sequence"></a><span data-ttu-id="db780-202">Teil 5: Starten der Windows-10 Upgrade Aufgabensequenz</span><span class="sxs-lookup"><span data-stu-id="db780-202">Part 5: Start the Windows 10 upgrade task sequence</span></span>
<span data-ttu-id="db780-203">Befolgen Sie diese Schritte, um die Aktualisierung von Windows 10 Aufgabensequenz auf dem Gerät zu starten, den Sie aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="db780-203">Follow these steps to start the Windows 10 Upgrade task sequence on the device that you are upgrading.</span></span>
 
1. <span data-ttu-id="db780-204">Melden Sie sich an der Windows-Computer und starten Sie **Software Center**zu.</span><span class="sxs-lookup"><span data-stu-id="db780-204">Log on to the Windows computer and start **Software Center**.</span></span>
2. <span data-ttu-id="db780-205">Wählen Sie die Abfolge der Vorgänge, die Sie in einem vorherigen Schritt erstellt haben, und wählen Sie dann auf **Installieren**.</span><span class="sxs-lookup"><span data-stu-id="db780-205">Select the task sequence that you created in a previous step, and then select **Install**.</span></span>
3. <span data-ttu-id="db780-206">Klicken Sie nach Beginn die Aufgabensequenz, er automatisch initiiert den Upgradeprozess in-Place durch Aufrufen das Windows-Setupprogramm (Setup.exe) mit den erforderlichen Befehlszeilenparametern ausführen und eine automatisierte Aktualisierung, alle Daten, die Einstellungen, die apps behält, und Treiber.</span><span class="sxs-lookup"><span data-stu-id="db780-206">When the task sequence begins, it automatically initiates the in-place upgrade process by invoking the Windows setup program (Setup.exe) with the necessary command-line parameters to perform an automated upgrade, which preserves all data, settings, apps, and drivers.</span></span>
4. <span data-ttu-id="db780-207">Nach dem erfolgreichen der Aufgabensequenz Abschluss wird der Computer vollständig auf Windows 10 aktualisiert werden.</span><span class="sxs-lookup"><span data-stu-id="db780-207">After the task sequence completes successfully, the computer will be fully upgraded to Windows 10.</span></span>

<span data-ttu-id="db780-p118">Wenn bei der Verwendung von Windows 10 in einer Unternehmensumgebung Probleme auftreten, konsultieren Sie die [wichtigsten Microsoft-Support-Lösungen für am häufigsten auftretenden Probleme](https://docs.microsoft.com/windows/client-management/windows-10-support-solutions). Diese Ressourcen umfassen KB-Artikel, Updates und Bibliotheksartikel.</span><span class="sxs-lookup"><span data-stu-id="db780-p118">If you experience issues when using Windows 10 in an enterprise environment, you can consult [top Microsoft Support solutions for the most common issues](https://docs.microsoft.com/windows/client-management/windows-10-support-solutions). These resources include KB articles, updates, and library articles.</span></span>

<span data-ttu-id="db780-p119">Während der Installation von Updates in Ihrer Organisation mit der aktualisieren Compliance-Funktion eines Windows Analytics einen ganzheitlichen OS Update Compliance, Update Bereitstellungsfortschritts und Fehler bei der Problembehandlung für Windows 10 Geräte bieten. Dieser neue Dienst verwendet Installationsstatus, Windows Update-Konfiguration und andere Informationen einschließlich Diagnosedaten um solche Einblicke ohne zusätzliche Kosten und ohne zusätzliche infrastrukturanforderungen. Ob sie mit Windows Update für Geschäftskunden und anderen Verwaltungstools verwendet wird, können Sie sicher sein, die Ihre Geräte ordnungsgemäß aktualisiert werden.</span><span class="sxs-lookup"><span data-stu-id="db780-p119">During the rollout of updates across your organization, use the Update Compliance capability of Windows Analytics to provide a holistic view of OS update compliance, update deployment progress, and failure troubleshooting for Windows 10 devices. This new service uses diagnostic data including installation progress, Windows Update configuration and other information to provide such insights, at no extra cost and without additional infrastructure requirements. Whether it's used with Windows Update for Business or other management tools, you can be assured that your devices are properly updated.</span></span>

<span data-ttu-id="db780-213">Finden Sie unter [Monitor-Updates für Windows und Windows Defender Antivirus mit Update Compliance](https://docs.microsoft.com/windows/deployment/update/update-compliance-monitor) erfahren mehr, erste Schritte und Kompatibilität verwenden.</span><span class="sxs-lookup"><span data-stu-id="db780-213">See [Monitor Windows Updates and Windows Defender Antivirus with Update Compliance](https://docs.microsoft.com/windows/deployment/update/update-compliance-monitor) to learn more, get started, and use Update Compliance.</span></span>

<span data-ttu-id="db780-214">Als Zwischenprüfung können Sie die [Beendigungskriterien](windows10-exit-criteria.md#crit-windows10-step2) für diesen Schritt betrachten.</span><span class="sxs-lookup"><span data-stu-id="db780-214">As an interim checkpoint, you can see the [exit criteria](windows10-exit-criteria.md#crit-windows10-step2) corresponding to this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="db780-215">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="db780-215">Next step</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step3.png)| [<span data-ttu-id="db780-216">Bereitstellen von Windows 10 Enterprise für neue Geräte mittels Windows Autopilot</span><span class="sxs-lookup"><span data-stu-id="db780-216">Deploy Windows 10 Enterprise for new devices with Windows Autopilot</span></span>](windows10-deploy-autopilot.md) |



<!--

| Phases | Description |
|:--- |:--- |
| [Phase 1: Consideration phase](#phase-1-consideration-phase) | TBD |
| [Phase 2: Testing phase](#phase-2-testing-phase) | TBD |
| [Phase 3: Deployment phase](#phase-3-deployment-phase) | TBD |

## Phase 1: Consideration phase
Before upgrading an OS in an enterprise environment, take the following technical aspects into account:
* [Infrastructure](#step-1-infrastructure)
* [Apps](#step-2-apps)
* [Governance and business processes](#step-3-governance-and-business-processes)

This guide is meant only to provide Microsoft's best recommendations around these assumptions by providing links to existing documentation.

### Step 1: Infrastructure
Consider your organization's collection of hardware, software, policies, networks, and other related technologies as part of the deployment process.

For in-place upgrade with Configuration Manager, these are the infrastructure you need to take into account:

#### Group Policy
Windows 10 introduces many new features and removes and changes many others in Windows 7 and 8.1, including new Group Policy settings which you need to test and implement as part of a Windows 10 migration. Use the examples from the following resources to assess current group policies for Windows, including Group Policy Objects in the Active Directory structure:
* [Manage Windows 10 with administrative templates](https://go.microsoft.com/fwlink/?linkid=860226) - Get step-by-step info on how to manage Windows 10 with administrative templates
* [Group Policy settings that apply to Windows 10](https://docs.microsoft.com/windows/client-management/group-policies-for-enterprise-and-education-editions) - Find out which Group Policy settings apply only to Windows 10 Enterprise

> [!NOTE]
> If you are considering moving to modern management by using MDM instead of Group Policy to manage device configurations, you can start by using the [MDM Migration Analysis Tool (MMAT)](https://github.com/WindowsDeviceManagement/MMAT) to determine what Group Policies are set on the device and report the corresponding settings, if available.

#### Data management
Although in-place upgrades shouldn’t affect user data and apps, a best practice is to configure a backup scenario and back up user data. For example, export all user data to a OneDrive for Business account, BitLocker To Go-encrypted USB flash drive, or network file server. For more details, see:
* [How to back up or transfer your data on a Windows-based computer](https://go.microsoft.com/fwlink/?linkid=860230) - Get step-by-step info on how to manually back up your personal files and settings.
* [Redirect known folders to OneDrive for Business](https://go.microsoft.com/fwlink/?linkid=846620) - Learn how to set a policy at the domain level to make sure users all sync to the same folder when they install the OneDrive sync client and how you can set additional policies to redirect the Documents folder to that sync location.

#### System Center Configuration Manager
This guide assumes you are following Microsoft recommendations and have one of the following versions of System Center Configuration Manager 2012 onward:
* System Center 2012 Configuration Manager with SP2
* System Center 2012, 2012 R2 Configuration Manager with SP1, Current Branch, 1706
    * [Run an in-place upgrade to the latest Configuration Manager](https://go.microsoft.com/fwlink/?linkid=839406)
    * [Updates for Configuration Manager](https://go.microsoft.com/fwlink/?linkid=620343)
* Core Configuration Manager configuration:
    * CONFIGURATION MANAGER accounts
    * Active Directory permissions
    * Source folder structure
    * Active Directory schema
* Configure the following [necessary Configuration Manager components for Windows 10 deployment](https://go.microsoft.com/fwlink/?linkid=860245):
    * **State migration point** - Stores user state migration data during computer replace scenarios
    * **Distribution point** - Stores all packages in Configuration Manager
    * **Software update point** - Updates an OS as part of the deployment process
    * **Reporting services point** - Monitors the OS deployment process
    * **Boot images** - Are Windows Preinstallation Environment (PE) images used by Configuration Manager to start deployments
    * **OS images** - Denotes the production deployment image (mounted OS)
    * **OS installers** - Creates reference images using Microsoft Deployment Toolkit (MDT) Light Touch
    * **Drivers** - Denotes a repository of managed device drivers
    * **Task Sequence** - Is delivered automatically to the client as a policy

#### Network bandwidth
This guide assumes you have enough network bandwidth to support the deployment of Windows 10 Enterprise and Office 365 ProPlus as a unit. As a bundle, network bandwidth is a significant factor.

#### Client machines and in-place upgrade scenario
* Disk encryption - Third-party disk encryption isn't supported in an in-place upgrade scenario.
* User profiles - Only the standard user profile type is supported.
* Legacy BIOS to Unified Extensible Firmware Interface (UEFI) booting - Changing from legacy BIOS to UEFI booting isn't supported.
* Dual-boot - This scenario is not covered in the guide. If you have the FastTrack Benefit, it only covers devices running a single OS.
* Virtual desktop infrastructure (VDI) environments - This scenario is not covered in the guide. If you have the FastTrack Benefit, it doesn't cover configuration or deployment on VDI environments.
* x64 and x86 - Changing from a 32-bit OS to a 64-bit isn't supported. For more info, see [Windows 10 deployment scenario > In-place upgrade](https://docs.microsoft.com/windows/deployment/windows-10-deployment-scenarios#in-place-upgrade).

### Step 2: Apps

#### Security
Security clients (like antivirus, anti-malware, and anti-spam) are typically found on all PCs within an organization. Because these programs hook into the deeper levels of the OS, you may need to perform a compatibility assessment before starting any Windows 10 migrations. You may need to upgrade, reconfigure, or even replace Some software. Not performing this assessment can lead to:
* Native app compatibility checks failing and preventing an in-place upgrade from starting.
* Broken functionality in the security software.
* Instability after upgrading to Windows 10 (like crashing and reduced performance)

**Antivirus**

Assess current antivirus software. Windows 10 comes with Windows Defender Antivirus to protect devices from malware, viruses, and security threats. We recommend Windows Defender Antivirus. To enable Windows Defender Antivirus, see [Windows Defender Antivirus](windows10-enable-security-features.md#windows-defender-antivirus) and [Protect devices with Windows Defender Antivirus](https://go.microsoft.com/fwlink/?linkid=860254).

To learn about antivirus solutions from other providers, see [Consumer antivirus software providers for Windows](https://go.microsoft.com/fwlink/?linkid=67345).

#### App readiness
Each Windows 10 release provides improved app compatibility. However, some apps may not be compatible. Depending on the app, you may need to only do a simple upgrade or configuration update before upgrading to Windows 10. In other circumstances, you may need to remove an app entirely.

Be sure to assess business critical apps and understand the impact of upgrading to the next OS. Prioritize the workloads that impact the least number of people during deployment. 

See the following Upgrade Readiness resources to help with app inventory, driver compatibility issues, and usage information:
* [Manage Windows Upgrades with Upgrade Readiness](https://go.microsoft.com/fwlink/?linkid=860255) - Learn about the tools to help you plan and manage the upgrade process end to end, which allow you to adopt new Windows releases more quickly.
* [Configure Windows diagnostic data](https://go.microsoft.com/fwlink/?linkid=859970) - Find out about the importance of Windows diagnostic data and how Microsoft protects that data.

> [!NOTE]
> Upgrade Readiness may not be able to assess compatibility for custom and line-of-business (LOB) apps in an organization.

#### Language packs
In-place upgrades have have limitations when it comes to language packs. The language stays consistent throughout the upgrade. Verify the language version and make sure it stays consistent. For example, Windows 7 with English as the default won’t change when upgraded to Windows 10. For more info, see:
* [Default language pack on your OS](https://go.microsoft.com/fwlink/?linkid=860282)
* [Finding language packs on each Windows 10 deployment](https://go.microsoft.com/fwlink/?linkid=860283)

For a Microsoft 365 powered device, you'll also need to download Office 365 ProPlus language packs that applies to the client. These come in 32-bit (x86) or 64-bit (x64). A specific language must be installed as the default. You can install other languages later. For more info, see:
* [Choose between 64-bit or 32-bit version of Office](https://go.microsoft.com/fwlink/?linkid=862361) - Helps you decide which version of Office is right for you.
* [Language accessory pack for Office](https://go.microsoft.com/fwlink/?linkid=860280) - Follow the steps to install the language accessory pack for Office.
* [Add an additional language pack](https://go.microsoft.com/fwlink/?linkid=860281) - Get step-by-step info on adding a language or setting language preferences in Office.

### Step 3: Governance and business processes

#### Windows as a service
Windows 10 introduced the concept of Windows as a service. This greatly changes the frequency and style of updates to Windows. Instead of new versions being released every 3-5 years, a more incremental model is used where two smaller updates (Feature Updates) are released yearly. For more info, see:
* [Windows as a service on the Windows IT Pro Center](https://www.microsoft.com/itpro/windows-10/windows-as-a-service)
* [Overview of Windows as a service](https://go.microsoft.com/fwlink/?linkid=860288)
* [Update Windows 10 in the enterprise](https://go.microsoft.com/fwlink/?linkid=860285)

#### Pilot users and deployment rings
Be sure to have a pilot group of users selected from different parts of the business. If you have Microsoft 365 powered devices, Windows 10 and Office 365 ProPlus users should be in these deployment rings. This affects future Windows updates as well (including features and quality). You need to create and edit device collections by deployment rings to help minimize the effect on network bandwidth and simplify future updates. 

For the group of pilot users, create a device collection on Configuration Manager. The list of devices should correspond to the list of the first users upgraded to Windows 10. 

**Windows 10 deployment rings**

There are three servicing channels for OS deployment rings:
* Windows Insider Program - Provides organizations with the opportunity to test and provide feedback on features that are shipped in the next feature update.
* Semi-Annual Channel - Provides new functionality with twice-per-year feature update releases. Organizations can choose when to deploy updates from the Semi-Annual Channel.
* Long-Term Servicing Channel (LTSC) - Used for specialized devices and receives new feature releases about every three years.

For more info, see:
* [Windows Insider Program, Semi-Annual Channel, and Long-Term Servicing Channel](https://go.microsoft.com/fwlink/?linkid=860293)
* [Build deployment rings for Windows 10 updates](https://go.microsoft.com/fwlink/?linkid=860294)
* [Manage software updates using Intune in Azure Portal](https://docs.microsoft.com/intune/windows-update-for-business-configure)

**Office 365 ProPlus**

For Microsoft 365 powered devices, you must also be able to support the six-month update channel for both IT and business users. One way to do so is to have three groups:
* Current Channel
* Deferred Channel
* First-release for Deferred Channel

Each group has different configuration files, as users from the Current Channel are used as a pilot to test earlier updates. For more info, see:
* [Update process for Office 365 ProPlus](https://go.microsoft.com/fwlink/?linkid=860299)
* [Manage updates to Office 365 ProPlus](https://go.microsoft.com/fwlink/?linkid=860300)
* [Configure update settings for Office 365 ProPlus](https://go.microsoft.com/fwlink/?linkid=860301)
* [Update channels for Office 365 ProPlus](https://go.microsoft.com/fwlink/?linkid=860302)
* [Version and build numbers of update channel releases](https://go.microsoft.com/fwlink/?linkid=860304)

For more info, see [Phase 4: Office 365 ProPlus infrastructure for Microsoft 365 Enterprise](office365proplus-infrastructure.md).

## Phase 2: Testing phase
Once you've completed the scenarios and requirements in [Step 1: Consideration phase](#step-1-consideration-phase), you can move to this stage.
* [Networking](#step-1-networking)
* [Identity](#step-2-identity)
* [Client readiness](#step-3-client-readiness)
* [System Center Configuration Manager](#step-4-system-center-configuration-manager)
* [Diagnostic data](#step-5-diagnostic-data)

### Step 1: Networking
Ports to the client need to be opened for Office 365 ProPlus (for a Microsoft 365 powered device) and Configuration Manager. For more details about setting up your Microsoft 365 Enterprise networking infrastructure, see [Phase 1: Networking](networking-infrastructure.md).

When setting up your networking infrastructure as part your in-place upgrade, make sure you complete these steps:
1. Read the best practices for [network planning and improving migration performance for Office 365](http://go.microsoft.com/fwlink/?LinkId=733655).
2. [Plan for network devices that connect to Office 365 services](http://go.microsoft.com/fwlink/?LinkId=733652).
3. [Review network impact of directory synchronization](http://go.microsoft.com/fwlink/?LinkId=733652).
4. Calculate the number of clients to use per IP address and understand [Network Address Translation (NAT) support with Office 365](http://go.microsoft.com/fwlink/?LinkId=733653) and how it impacts the number of users and client devices you can serve with a single IP address.
5. If your organization restricts computers on your network from connecting to the Internet, you'll need to understand the [endpoints (fully qualified domain names (FQDNs), ports, URLs, IPv4, and IPv6 address ranges)](http://go.microsoft.com/fwlink/?LinkID=280129) that you should include in your outbound allow lists to ensure your computers can successfully use Office 365 services.
6. [Create domain name system records for Office 365 at any Domain Name System hosting provider](http://go.microsoft.com/fwlink/?LinkId=733656).
7. [Reduce mail exchange (MX) DNS record time to live (TTL) value](http://go.microsoft.com/fwlink/?LinkId=733656).

### Step 2: Identity
Intelligent security for Microsoft 365 Enterprise, in which the right users have access to the right resources with an appropriate level of access, begins with identity management. For more details about setting up your Microsoft 365 Enterprise identity infrastructure, see [Phase 2: Identity](identity-infrastructure.md).

When setting up your identity infrastructure as part of your in-place upgrade, make sure you complete these tasks:
1. [Add a domain and users to Office 365](http://go.microsoft.com/fwlink/?LinkID=526338).
2. [Install and run the Office 365 IdFix tool](http://go.microsoft.com/fwlink/?LinkId=733662), which scans your on-premises Active Directory environment and identifies problems that might impact directory synchronization and slow your migration to Office 365.
3. Configure Active Directory for directory synchronization with Office 365 and [integrate on-premises directories with Azure AD](http://go.microsoft.com/fwlink/?LinkId=733661).
4. [Prepare to provision users through directory synchronization to Office 365](http://go.microsoft.com/fwlink/?LinkId=733659).
5. Know the [prerequisites for Azure AD Connect](http://go.microsoft.com/fwlink/?LinkId=733663), then install and run the Azure AD Connect tool to synchronize your on-premises Active Directory to the Azure AD service used by Office 365.
6. Determine custom installation of Azure AD Connect (full version of SQL Server for directory synchronization, if required).
7. [Integrate your on-premises identities with Azure AD](http://go.microsoft.com/fwlink/?LinkID=733485).
8. [Sync a list of required attributes with AD Connect](https://go.microsoft.com/fwlink/?linkid=860363) to get all the features in Office 365 and Windows 10.
9. Activate Windows 10 Enterprise licenses, which are checked based on Azure AD credentials.

    This provides a systematic way to assign licenses to end users and groups in your organization. For more info, see [Windows 10 Subscription Activation](https://go.microsoft.com/fwlink/?linkid=860365) and [Deploy Windows 10 licenses](https://go.microsoft.com/fwlink/?linkid=860367).

### Step 3: Client readiness

#### System requirements for Office 365
Confirm that Windows 10 works with Office 365. Be sure you're using the latest OS version and browsers with Office 365 and have updated them with the latest service packs. For more info on Office requirements, see [System requirements for Office](http://go.microsoft.com/fwlink/?LinkID=394412).

### Step 4: System Center Configuration Manager
See [System Center Configuration Manager](#system-center-configuration-manager).

### Step 5: Diagnostic data
Microsoft uses diagnostic data to help keep Windows devices secure by identifying malware trends and other threats and to help us improve the quality of Windows and Microsoft services. You must ensure that the diagnostics service is enabled at a minimum level of Basic on all endpoints in your organization. **By default, this service is enabled and set to the Enhanced level.** However, it’s good practice to check and ensure that they are receiving sensor data. Setting levels through policies overrides device-level settings. 

**Windows 10 operating system diagnostic data levels**

You can configure your operating system diagnostic data settings using the management tools you’re already using, such as Group Policy, MDM, or Windows Provisioning. You can also manually change your settings using Registry Editor. Setting your diagnostic data levels through a management policy overrides any device level settings.

Use the appropriate value in the table below when you configure the management policy.

| Level | Data gathered | Value |
|:--- |:--- |:--- |
| Security | Security data only. | 0 |
| Basic | Security data, and basic system and quality data. | 1 |
| Enhanced | Security data, basic system and quality data, and enhanced insights and advanced reliability data. | 2 |
| Full | Security data, basic system and quality data, enhanced insights and advanced reliability data, and full diagnostics data. | 3 |

You can enable diagnostics data through these methods:
* Microsoft Intune - If you plan to use Intune to manage your devices, you can create a configuration policy to enable diagnostic data by configuring the <a href="https://docs.microsoft.com/windows/client-management/mdm/policy-csp-system#system-allowtelemetry" target="blank">SystemAllowTelemetry</a> system policy. For more info on setting up configuration policies, see [Manage settings and features on your devices with Microsoft Intune policies](https://aka.ms/intuneconfigpolicies).
* Registry Editor - You can use the Registry Editor to manually enable diagnostic data on each device in your organization, or write a script to edit the registry. If a management policy already exists, such as Group Policy or MDM, it will override this registry setting.
* Group Policy - If you do not plan to enroll devices in Intune, you can use a Group Policy object to set your organization’s diagnostic data level.
* Command prompt - You can set Windows 10 diagnostics data and service to automatically start with the command prompt. This method is best if you are testing the service on only a few devices. Enabling the service to start automatically with this command will not configure the diagnostic data level. If you have not configured a diagnostic data level using management tools, the service will operate with the default Enhanced level.

See [Configure Windows diagnostic data in your organization](https://docs.microsoft.com/windows/configuration/configure-windows-diagnostic-data-in-your-organization) to learn more about Windows diagnostic data and how you can enable it based on the method that you choose.

## Phase 3: Deployment phase
When ready, complete these:
* [In-place upgrade to Windows 10 Enterprise](#31-in-place-upgrade-to-windows-10-enterprise)
* [Windows Defender Antivirus](#32-windows-defender-antivirus)

### Step 1: In-place upgrade to Windows 10 Enterprise
1. Integrate System Center Configuration Manager with Microsoft Deployment Tool.

    Be sure to use the Microsoft Deployment Toolkit (MDT) in conjunction with Configuration Manager when deploying an updated version of Windows 10. MDT brings Zero Touch Installation and Light Touch Installation enhancements to help with deployments at no cost to the customer. For more info, see:
    * [Download the latest MDT](https://go.microsoft.com/fwlink/?linkid=860465)
    * [Deploy Windows 10 with the Microsoft Deployment Toolkit](https://go.microsoft.com/fwlink/?linkid=860466)

2. Prepare for zero touch installation.

    As part of zero touch installation, you are responsible for preparing the following:
    * Configuration Manager service accounts
    * Active Directory permissions
    * Source folder structure

    Then, [integrate Configuration Manager with MDT](https://go.microsoft.com/fwlink/?linkid=860035).

3. Create a custom Windows Preinstallation Environment boot image.

    Windows Preinstallation Environment (PE) is a pre-installation environment required for OS deployments. It’s used to prepare a client machine for Windows installation, to copy disk images from a network file server, and to initiate Windows Setup. It’s used for Windows 10 Enterprise editions. For more info, see:
    * [Overview of Windows PE](https://go.microsoft.com/fwlink/?linkid=860468)
    * [Windows PE features, hardware requirements, and limitations](https://go.microsoft.com/fwlink/?linkid=860469)
    * [Create a custom Windows PE boot image with Configuration Manager](https://go.microsoft.com/fwlink/?linkid=860470)

4. Add a Windows 10 OS upgrade image.

    You need to create a Windows 10 reference image with MDT (as needed). Reference images are the foundation of what each of the client machine’s OS looks like. The image should be in a separate folder located with the already-mounted ISO file. The task sequence looks for and then runs “setup.exe”. 

    Follow the steps to create and add a Windows 10 OS upgrade image on Configuration Manager:
    * [Create a Windows 10 reference image](https://go.microsoft.com/fwlink/?linkid=860500)
    * [Add a Windows 10 OS image using Configuration Manager](https://go.microsoft.com/fwlink/?linkid=860501)

5. Create an app to deploy with Windows 10.

    For a Microsoft 365 powered device, you can deploy Office 365 ProPlus with Windows 10 Enterprise using Configuration Manager. You can also add other apps as needed.

    To deploy Office 365 ProPlus, follow the steps in [Phase 4: Office 365 ProPlus infrastructure for Microsoft 365 Enterprise](office365proplus-infrastructure.md). During this phase, make sure you complete these steps:
    
    1. Download the Office 2016 Deployment Tool (ODT) in conjunction with Configuration Manager to help with Office 365 ProPlus deployments. 
    2. Edit the configuration XML file to fit specific deployment needs (like version, language, and product element). 
    
    You can then create apps with Configuration Manager. For more info, see:
    * [Configuration options for ODT](https://go.microsoft.com/fwlink/?linkid=860504)
    * [Create apps in Configuration Manager](https://go.microsoft.com/fwlink/?linkid=761079)
    * [Deploy Office 365 ProPlus with Configuration Manager](https://go.microsoft.com/fwlink/?linkid=860506)

6. Add drivers to a Windows 10 deployment using Windows PE.

    Network drivers need to be created for both Windows PE and Windows 10 to connect deployment shares and storage drivers with local storage on a client computer. Use Configuration Manager to create these drivers required for deployment. For more info, see [Add drivers to a Windows 10 deployment with Windows PE using Configuration Manager](https://go.microsoft.com/fwlink/?linkid=860036).

7. Create a task sequence.

    A task sequence (a collection of commands) is required for MDT Lite Touch Installation (LTI). You need to create and then edit the task sequence for optimal deployment experience. One of the configurations enable support for Unified Extensible Firmware Interface (UEFI). The UEFI environment is a minimal boot OS where devices are booted and the Windows 10 OS runs. For more info, see:
    * [Overview of Windows Boot Manager](https://go.microsoft.com/fwlink/?linkid=860696)
    * [Create the task sequence in Configuration Manager](https://go.microsoft.com/fwlink/?linkid=860697)

8. Finalize the OS configuration for Windows 10 deployment.

    **To finalize the OS configuration**

    1. Enable MDT monitoring
    2. Create and share the Logs folder
    3. Configure the rules
    4. Distribute content to the distribution point (a server running Configuration Manager)
    5. Create a deployment for the task sequence

   For more info, see [Finalize OS configuration with Configuration Manager](https://go.microsoft.com/fwlink/?linkid=860697).

9. Deploy the Windows 10 Enterprise image to a UEFI machine.

    For more info, see [Deploy Windows 10 using Configuration Manager](https://go.microsoft.com/fwlink/?linkid=860697).

10. Monitor the Windows 10 deployment.

    Use Configuration Manager and MDT to monitor your deployment. Deployment Workbench enables access to the computer remotely using the Diagnostics and Recovery Toolset (DaRT) (optional). Deployments can be monitored in Configuration Manager. For more info, see [Monitor the Windows 10 deployment with Configuration Manager](https://go.microsoft.com/fwlink/?linkid=860705).

### Step 2: Windows Defender Antivirus
See [Enable Windows 10 Enterprise security features > Windows Defender Antivirus](windows10-enable-security-features.md#windows-defender-antivirus)

-->
