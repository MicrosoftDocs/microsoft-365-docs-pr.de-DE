---
title: Aktivieren von Domänenbeitritt von Windows 10-Geräten, die von Microsoft 365 for Business verwaltet werden
f1.keywords:
- CSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
- seo-marvel-mar
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
description: In diesem Artikel erfahren Sie, wie Sie Microsoft 365 in wenigen Schritten zum Schutz von lokalen Active Directory-verbundenen Windows 10-Geräten aktivieren.
ms.openlocfilehash: 6275c6c4be9cd9631ab095f8b0e1b39683022bb2
ms.sourcegitcommit: d988faa292c2661ffea43c7161aef92b2b4b99bc
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "46560841"
---
# <a name="enable-domain-joined-windows-10-devices-to-be-managed-by-microsoft-365-business-premium"></a><span data-ttu-id="12bac-103">Aktivieren von Domänenbeitritt von Windows 10-Geräten, die von Microsoft 365 Business Premium verwaltet werden</span><span class="sxs-lookup"><span data-stu-id="12bac-103">Enable domain-joined Windows 10 devices to be managed by Microsoft 365 Business Premium</span></span>

<span data-ttu-id="12bac-104">Wenn Ihre Organisation Windows Server Active Directory lokal verwendet, können Sie Microsoft 365 Business Premium zum Schutz Ihrer Windows 10-Geräte einrichten und gleichzeitig den Zugriff auf lokale Ressourcen aufrecht erhalten, die lokale Authentifizierung erfordern.</span><span class="sxs-lookup"><span data-stu-id="12bac-104">If your organization uses Windows Server Active Directory on-premises, you can set up Microsoft 365 Business Premium to protect your Windows 10 devices, while still maintaining access to on-premises resources that require local authentication.</span></span>
<span data-ttu-id="12bac-105">Um diesen Schutz einzurichten, können Sie **hybride Azure AD verbundene Geräte**implementieren.</span><span class="sxs-lookup"><span data-stu-id="12bac-105">To set up this protection, you can implement **Hybrid Azure AD joined devices**.</span></span> <span data-ttu-id="12bac-106">Diese Geräte sind sowohl mit Ihrem lokalen Active Directory als auch mit Ihrem Azure-Active Directory verbunden.</span><span class="sxs-lookup"><span data-stu-id="12bac-106">These devices are joined to both your on-premises Active Directory and your Azure Active Directory.</span></span>

<span data-ttu-id="12bac-107">In diesem Video werden die Schritte beschrieben, wie Sie dies für das am häufigsten verwendete Szenario einrichten, das auch in den folgenden Schritten detailliert erläutert wird.</span><span class="sxs-lookup"><span data-stu-id="12bac-107">This video describes the steps for how to set this up for the most common scenario, which is also detailed in the steps that follow.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3C9hO]
  

## <a name="before-you-get-started-make-sure-you-complete-these-steps"></a><span data-ttu-id="12bac-108">Bevor Sie beginnen, stellen Sie sicher, dass Sie die folgenden Schritte ausführen:</span><span class="sxs-lookup"><span data-stu-id="12bac-108">Before you get started, make sure you complete these steps:</span></span>
- <span data-ttu-id="12bac-109">Synchronisieren von Benutzern mit dem Azure AD mit Azure AD Connect.</span><span class="sxs-lookup"><span data-stu-id="12bac-109">Synchronize users to Azure AD with Azure AD Connect.</span></span>
- <span data-ttu-id="12bac-110">Schließen Sie die Synchronisierung Azure AD Connect Organizational Unit (OU) ab.</span><span class="sxs-lookup"><span data-stu-id="12bac-110">Complete Azure AD Connect Organizational Unit (OU) sync.</span></span>
- <span data-ttu-id="12bac-111">Stellen Sie sicher, dass alle von Ihnen synchronisierten Domänenbenutzer Lizenzen für Microsoft 365 Business Premium haben.</span><span class="sxs-lookup"><span data-stu-id="12bac-111">Make sure all the domain users you sync have licenses to Microsoft 365 Business Premium.</span></span>

<span data-ttu-id="12bac-112">Die Schritte finden Sie unter [Synchronisieren von Domänenbenutzern mit Microsoft](manage-domain-users.md) .</span><span class="sxs-lookup"><span data-stu-id="12bac-112">See [Synchronize domain users to Microsoft](manage-domain-users.md) for the steps.</span></span>

## <a name="1-verify-mdm-authority-in-intune"></a><span data-ttu-id="12bac-113">1. Überprüfen der MDM-Autorität in InTune</span><span class="sxs-lookup"><span data-stu-id="12bac-113">1. Verify MDM Authority in Intune</span></span>

<span data-ttu-id="12bac-114">Wechseln Sie zu [Endpunkt-Manager](https://endpoint.microsoft.com/#blade/Microsoft_Intune_Enrollment/EnrollmentMenu/overview) , und wählen Sie auf der Seite Microsoft InTune die Option **Geräteregistrierung**aus, und stellen Sie dann auf der Seite **Übersicht** sicher, dass die **MDM-Autorität** **InTune**ist.</span><span class="sxs-lookup"><span data-stu-id="12bac-114">Go to [Endpoint Manager](https://endpoint.microsoft.com/#blade/Microsoft_Intune_Enrollment/EnrollmentMenu/overview) and on the Microsoft Intune page, select **Device enrollment**, then on the **Overview** page, make sure **MDM authority** is **Intune**.</span></span>

- <span data-ttu-id="12bac-115">Wenn **MDM Authority** **keine**ist, klicken Sie auf die **MDM-Autorität** , um Sie auf **InTune**festzulegen.</span><span class="sxs-lookup"><span data-stu-id="12bac-115">If **MDM authority** is **None**, click the **MDM authority** to set it to **Intune**.</span></span>
- <span data-ttu-id="12bac-116">Wenn **MDM Authority** **Microsoft Office 365**ist, wechseln Sie zu **Geräte**  >  **Registrieren von Geräten** , und verwenden Sie das Dialogfeld MDM- **Autorität hinzufügen** auf der rechten Seite zum Hinzufügen von **InTune-MDM** -Autorität (das Dialogfeld MDM- **Autorität hinzufügen** ist nur verfügbar, wenn die MDM- **Autorität** auf Microsoft Office 365 festgelegt ist).</span><span class="sxs-lookup"><span data-stu-id="12bac-116">If **MDM authority** is **Microsoft Office 365**,go to **Devices** > **Enroll devices** and use the **Add MDM authority** dialog on the right to add **Intune MDM** authority (the **Add MDM Authority** dialog is only available if the **MDM Authority** is set to Microsoft Office 365).</span></span>

## <a name="2-verify-azure-ad-is-enabled-for-joining-computers"></a><span data-ttu-id="12bac-117">2. überprüfen, ob Azure AD für das Hinzufügen von Computern aktiviert ist</span><span class="sxs-lookup"><span data-stu-id="12bac-117">2. Verify Azure AD is enabled for joining computers</span></span>

- <span data-ttu-id="12bac-118">Wechseln Sie zum Admin Center unter <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> , und wählen Sie **Azure Active Directory** (Wählen Sie alle anzeigen, wenn Azure Active Directory nicht sichtbar ist) in der Liste **Admin** Center aus.</span><span class="sxs-lookup"><span data-stu-id="12bac-118">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>  and select **Azure Active Directory** (select Show all if Azure Active Directory is not visible) in the **Admin centers** list.</span></span> 
- <span data-ttu-id="12bac-119">Wechseln Sie im **Azure Active Directory Admin Center**zu **Azure Active Directory** , wählen Sie **Geräte** und dann **Geräteeinstellungen**aus.</span><span class="sxs-lookup"><span data-stu-id="12bac-119">In the **Azure Active Directory admin center**, go to **Azure Active Directory** , choose **Devices** and then **Device settings**.</span></span>
- <span data-ttu-id="12bac-120">Sicherstellen **, dass Benutzer Geräte an Azure AD** aktiviert werden können</span><span class="sxs-lookup"><span data-stu-id="12bac-120">Verify**Users may join devices to Azure AD** is enabled</span></span> 
    1. <span data-ttu-id="12bac-121">Um alle Benutzer zu aktivieren, legen Sie **alle**fest.</span><span class="sxs-lookup"><span data-stu-id="12bac-121">To enable all users, set to **All**.</span></span>
    2. <span data-ttu-id="12bac-122">Um bestimmte Benutzer zu aktivieren, legen Sie auf **ausgewählt** fest, um eine bestimmte Gruppe von Benutzern zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="12bac-122">To enable specific users, set to **Selected** to enable a specific group of users.</span></span>
        - <span data-ttu-id="12bac-123">Fügen Sie die gewünschten Domänenbenutzer, die in Azure AD synchronisiert wurden, zu einer [Sicherheitsgruppe](../admin/create-groups/create-groups.md)hinzu.</span><span class="sxs-lookup"><span data-stu-id="12bac-123">Add the desired domain users synced in Azure AD to a [security group](../admin/create-groups/create-groups.md).</span></span>
        - <span data-ttu-id="12bac-124">Wählen **Sie Gruppen auswählen** aus, um den MDM-Benutzerbereich für diese Sicherheitsgruppe zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="12bac-124">Choose **Select groups** to enable MDM user scope for that security group.</span></span>

## <a name="3-verify-azure-ad-is-enabled-for-mdm"></a><span data-ttu-id="12bac-125">3. überprüfen Azure AD für MDM aktiviert ist</span><span class="sxs-lookup"><span data-stu-id="12bac-125">3. Verify Azure AD is enabled for MDM</span></span>

- <span data-ttu-id="12bac-126">Wechseln Sie zum Admin Center unter <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> , und wählen Sie " **Endpunkt Verwaltung**auswählen" aus (Wählen Sie **Alle anzeigen** aus, wenn **Endpunkt-Manager** nicht sichtbar ist)</span><span class="sxs-lookup"><span data-stu-id="12bac-126">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>  and select select **Endpoint Managemen**t (select **Show all** if **Endpoint Manager** is not visible)</span></span>
- <span data-ttu-id="12bac-127">Wechseln Sie im **Microsoft Endpoint Manager Admin Center**zu **Geräte**  >  **Windows**  >  **Windows-Registrierung**für die  >  **automatische Registrierung**.</span><span class="sxs-lookup"><span data-stu-id="12bac-127">In the **Microsoft Endpoint Manager admin center**, go to **Devices** > **Windows** > **Windows Enrollment** > **Automatic Enrollment**.</span></span>
- <span data-ttu-id="12bac-128">Überprüfen Sie, dass der MDM-Benutzerbereich aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="12bac-128">Verify MDM user scope is enabled.</span></span>

    1. <span data-ttu-id="12bac-129">Wenn Sie alle Computer registrieren möchten, **legen Sie alle** fest, damit alle Benutzer Computer, die zu Azure AD und zu neuen Computern gehören, automatisch registriert werden, wenn die Benutzer ein Arbeitskonto zu Windows hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="12bac-129">To enroll all computers, set to **All** to automatically enroll all user computers that are joined to Azure AD and new computers  when the users add a work account to Windows.</span></span>
    2. <span data-ttu-id="12bac-130">Auf **einige** festlegen, um die Computer einer bestimmten Gruppe von Benutzern zu registrieren.</span><span class="sxs-lookup"><span data-stu-id="12bac-130">Set to **Some** to enroll the computers of a specific group of users.</span></span>
        -  <span data-ttu-id="12bac-131">Fügen Sie die gewünschten Domänenbenutzer, die in Azure AD synchronisiert wurden, zu einer [Sicherheitsgruppe](../admin/create-groups/create-groups.md)hinzu.</span><span class="sxs-lookup"><span data-stu-id="12bac-131">Add the desired domain users synced in Azure AD to a [security group](../admin/create-groups/create-groups.md).</span></span>
        -  <span data-ttu-id="12bac-132">Wählen **Sie Gruppen auswählen** aus, um den MDM-Benutzerbereich für diese Sicherheitsgruppe zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="12bac-132">Choose **Select groups** to enable MDM user scope for that security group.</span></span>

## <a name="4-create-the-required-resources"></a><span data-ttu-id="12bac-133">4. Erstellen der erforderlichen Ressourcen</span><span class="sxs-lookup"><span data-stu-id="12bac-133">4. Create the required resources</span></span> 

<span data-ttu-id="12bac-134">Das Ausführen der erforderlichen Aufgaben zum [Konfigurieren von Hybrid Azure AD Verknüpfung](https://docs.microsoft.com/azure/active-directory/devices/hybrid-azuread-join-managed-domains#configure-hybrid-azure-ad-join) wurde durch die Verwendung des Cmdlets [Initialize-SecMgmtHybirdDeviceEnrollment](https://github.com/microsoft/secmgmt-open-powershell/blob/master/docs/help/Initialize-SecMgmtHybirdDeviceEnrollment.md) im PowerShell-Modul [SecMgmt](https://www.powershellgallery.com/packages/SecMgmt) vereinfacht.</span><span class="sxs-lookup"><span data-stu-id="12bac-134">Performing the required tasks to [configure hybrid Azure AD join](https://docs.microsoft.com/azure/active-directory/devices/hybrid-azuread-join-managed-domains#configure-hybrid-azure-ad-join) has been simplified through the use of the [Initialize-SecMgmtHybirdDeviceEnrollment](https://github.com/microsoft/secmgmt-open-powershell/blob/master/docs/help/Initialize-SecMgmtHybirdDeviceEnrollment.md) cmdlet found in the [SecMgmt](https://www.powershellgallery.com/packages/SecMgmt) PowerShell module.</span></span> <span data-ttu-id="12bac-135">Wenn Sie dieses Cmdlet aufrufen, wird der erforderliche Dienst Verbindungspfad und die Gruppenrichtlinie erstellt und konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="12bac-135">When you invoke this cmdlet it will create and configure the required service connection point and group policy.</span></span>

<span data-ttu-id="12bac-136">Sie können dieses Modul installieren, indem Sie aus einer Instanz von PowerShell Folgendes aufrufen:</span><span class="sxs-lookup"><span data-stu-id="12bac-136">You can install this module by invoking the following from an instance of PowerShell:</span></span>

```powershell
Install-Module SecMgmt
```

> [!IMPORTANT]
> <span data-ttu-id="12bac-137">Es wird empfohlen, dieses Modul auf dem Windows-Server mit Azure AD Connect zu installieren.</span><span class="sxs-lookup"><span data-stu-id="12bac-137">It is recommended that you install this module on the Windows Server running Azure AD Connect.</span></span>

<span data-ttu-id="12bac-138">Zum Erstellen des erforderlichen Dienst Verbindungs Pfads und der Gruppenrichtlinie rufen Sie das Cmdlet [Initialize-SecMgmtHybirdDeviceEnrollment](https://github.com/microsoft/secmgmt-open-powershell/blob/master/docs/help/Initialize-SecMgmtHybirdDeviceEnrollment.md) auf.</span><span class="sxs-lookup"><span data-stu-id="12bac-138">To create the required service connection point and group policy, you will invoke the  [Initialize-SecMgmtHybirdDeviceEnrollment](https://github.com/microsoft/secmgmt-open-powershell/blob/master/docs/help/Initialize-SecMgmtHybirdDeviceEnrollment.md) cmdlet.</span></span> <span data-ttu-id="12bac-139">Sie benötigen Ihre globalen Administratoranmeldeinformationen für Microsoft 365 Business Premium, wenn Sie diese Aufgabe ausführen.</span><span class="sxs-lookup"><span data-stu-id="12bac-139">You will need your Microsoft 365 Business Premium global admin credentials when performing this task.</span></span> <span data-ttu-id="12bac-140">Wenn Sie bereit sind, die Ressourcen zu erstellen, rufen Sie Folgendes auf:</span><span class="sxs-lookup"><span data-stu-id="12bac-140">When you are ready to create the resources, invoke the following:</span></span>

```powershell
PS C:\> Connect-SecMgmtAccount
PS C:\> Initialize-SecMgmtHybirdDeviceEnrollment -GroupPolicyDisplayName 'Device Management'
```

<span data-ttu-id="12bac-141">Mit dem ersten Befehl wird eine Verbindung mit der Microsoft-Cloud hergestellt, und wenn Sie dazu aufgefordert werden, geben Sie Ihre globalen Administratoranmeldeinformationen für Microsoft 365 Business Premium an.</span><span class="sxs-lookup"><span data-stu-id="12bac-141">The first command will establish a connection with the Microsoft cloud, and when you are prompted, specify your Microsoft 365 Business Premium global admin credentials.</span></span>

## <a name="5-link-the-group-policy"></a><span data-ttu-id="12bac-142">5. Verknüpfen der Gruppenrichtlinie</span><span class="sxs-lookup"><span data-stu-id="12bac-142">5. Link the Group Policy</span></span>

1. <span data-ttu-id="12bac-143">Klicken Sie in der Gruppenrichtlinien-Verwaltungskonsole (Group Policy Management Console, GPMC) mit der rechten Maustaste auf den Speicherort, an dem Sie die Richtlinie verknüpfen möchten, und wählen Sie im Kontextmenü die Option *vorhandenes GPO verknüpfen* aus.</span><span class="sxs-lookup"><span data-stu-id="12bac-143">In the Group Policy Management Console (GPMC), right-click on the location where you want to link the policy and select *Link an existing GPO...* from the context menu.</span></span>
2. <span data-ttu-id="12bac-144">Wählen Sie die im obigen Schritt erstellte Richtlinie aus, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="12bac-144">Select the policy created in the above step, then click **OK**.</span></span>

## <a name="get-the-latest-administrative-templates"></a><span data-ttu-id="12bac-145">Abrufen der neuesten administrativen Vorlagen</span><span class="sxs-lookup"><span data-stu-id="12bac-145">Get the latest Administrative Templates</span></span>

<span data-ttu-id="12bac-146">Wenn die Richtlinie **Automatische MDM-Registrierung mithilfe der Standard Azure AD Anmeldeinformationen nicht aktiviert**wird, kann dies daran liegen, dass Sie den ADMX nicht für Windows 10, Version 1803, Version 1809 oder Version 1903 installiert haben.</span><span class="sxs-lookup"><span data-stu-id="12bac-146">If you do not see the policy **Enable automatic MDM enrollment using default Azure AD credentials**, it may be because you don’t have the ADMX installed for Windows 10, version 1803, version 1809, or version 1903.</span></span> <span data-ttu-id="12bac-147">Führen Sie die folgenden Schritte aus, um das Problem zu beheben (Hinweis: die neueste Version von MDM. ADMX ist abwärtskompatibel):</span><span class="sxs-lookup"><span data-stu-id="12bac-147">To fix the issue, follow these steps (Note: the latest MDM.admx is backwards compatible):</span></span>

1.  <span data-ttu-id="12bac-148">Download: [Administrative Vorlagen (ADMX) für Windows 10 May 2019 Update (1903)](https://www.microsoft.com/download/details.aspx?id=58495&WT.mc_id=rss_alldownloads_all).</span><span class="sxs-lookup"><span data-stu-id="12bac-148">Download: [Administrative Templates (.admx) for Windows 10 May 2019 Update (1903)](https://www.microsoft.com/download/details.aspx?id=58495&WT.mc_id=rss_alldownloads_all).</span></span>
2.  <span data-ttu-id="12bac-149">Installieren Sie das Paket auf dem primären Domänen Controller (PDC).</span><span class="sxs-lookup"><span data-stu-id="12bac-149">Install the package on the Primary Domain Controller (PDC).</span></span>
3.  <span data-ttu-id="12bac-150">Navigieren Sie je nach Version zum Ordner: **C:\Program Files (x86) \Microsoft Group Policy\Windows 10 May 2019 Update (1903) v3**.</span><span class="sxs-lookup"><span data-stu-id="12bac-150">Navigate, depending on the version to the folder: **C:\Program Files (x86)\Microsoft Group Policy\Windows 10 May 2019 Update (1903) v3**.</span></span>
4.  <span data-ttu-id="12bac-151">Benennen Sie den Ordner **Richtlinien Definitionen** im obigen Pfad in **PolicyDefinitions**um.</span><span class="sxs-lookup"><span data-stu-id="12bac-151">Rename the **Policy Definitions** folder in the above path to **PolicyDefinitions**.</span></span>
5.  <span data-ttu-id="12bac-152">Kopieren Sie **PolicyDefinitions** -Ordner in **C:\Windows\SYSVOL\domain\Policies**.</span><span class="sxs-lookup"><span data-stu-id="12bac-152">Copy **PolicyDefinitions** folder to **C:\Windows\SYSVOL\domain\Policies**.</span></span> 
    -   <span data-ttu-id="12bac-153">Wenn Sie einen zentralen Richtlinienspeicher für Ihre gesamte Domäne verwenden möchten, fügen Sie den Inhalt von PolicyDefinitions dort hinzu.</span><span class="sxs-lookup"><span data-stu-id="12bac-153">If you plan to use a central policy store for your entire domain, add the contents of PolicyDefinitions there.</span></span>
6.  <span data-ttu-id="12bac-154">Starten Sie den primären Domänen Controller neu, damit die Richtlinie zur Verfügung steht.</span><span class="sxs-lookup"><span data-stu-id="12bac-154">Restart the Primary Domain Controller for the policy to be available.</span></span> <span data-ttu-id="12bac-155">Dieses Verfahren kann auch für zukünftige Versionen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="12bac-155">This procedure will work for any future version as well.</span></span>

<span data-ttu-id="12bac-156">An dieser Position sollten Sie die **Automatische MDM-Registrierung mithilfe der standardmäßigen Azure AD** verfügbaren Anmeldeinformationen anzeigen können.</span><span class="sxs-lookup"><span data-stu-id="12bac-156">At this point you should be able to see the policy **Enable automatic MDM enrollment using default Azure AD credentials** available.</span></span>
