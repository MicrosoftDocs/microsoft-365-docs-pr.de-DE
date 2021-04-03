---
title: Aktivieren der Domänenverfingung von Windows 10-Geräten, die von Microsoft 365 Business verwaltet werden
f1.keywords:
- CSH
ms.author: efrene
author: efrene
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
description: Erfahren Sie, wie Sie Microsoft 365 aktivieren, um lokale Active-Directory-beigetretene Windows 10-Geräte in nur wenigen Schritten zu schützen.
ms.openlocfilehash: 8a45c6959bee368491c5c6424e3713300c443779
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/02/2021
ms.locfileid: "51580132"
---
# <a name="enable-domain-joined-windows-10-devices-to-be-managed-by-microsoft-365-business-premium"></a><span data-ttu-id="982f1-103">Aktivieren der In der Domäne beigetretenen Windows 10-Geräte, die von Microsoft 365 Business Premium verwaltet werden können</span><span class="sxs-lookup"><span data-stu-id="982f1-103">Enable domain-joined Windows 10 devices to be managed by Microsoft 365 Business Premium</span></span>

<span data-ttu-id="982f1-104">Wenn Ihre Organisation Windows Server Active Directory lokal verwendet, können Sie Microsoft 365 Business Premium zum Schutz Ihrer Windows 10-Geräte einrichten und gleichzeitig den Zugriff auf lokale Ressourcen beibehalten, die eine lokale Authentifizierung erfordern.</span><span class="sxs-lookup"><span data-stu-id="982f1-104">If your organization uses Windows Server Active Directory on-premises, you can set up Microsoft 365 Business Premium to protect your Windows 10 devices, while still maintaining access to on-premises resources that require local authentication.</span></span>
<span data-ttu-id="982f1-105">Zum Einrichten dieses Schutzes können Sie Azure **AD-Hybridgeräte implementieren.**</span><span class="sxs-lookup"><span data-stu-id="982f1-105">To set up this protection, you can implement **Hybrid Azure AD joined devices**.</span></span> <span data-ttu-id="982f1-106">Diese Geräte sind sowohl mit Ihrem lokalen Active Directory als auch mit Ihrem Azure Active Directory verbunden.</span><span class="sxs-lookup"><span data-stu-id="982f1-106">These devices are joined to both your on-premises Active Directory and your Azure Active Directory.</span></span>

<span data-ttu-id="982f1-107">In diesem Video werden die Schritte zum Einrichten dieses Szenarios für das gängigste Szenario beschrieben, das auch in den folgenden Schritten beschrieben wird.</span><span class="sxs-lookup"><span data-stu-id="982f1-107">This video describes the steps for how to set this up for the most common scenario, which is also detailed in the steps that follow.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3C9hO]
  

## <a name="before-you-get-started-make-sure-you-complete-these-steps"></a><span data-ttu-id="982f1-108">Bevor Sie beginnen, stellen Sie sicher, dass Sie die folgenden Schritte ausführen:</span><span class="sxs-lookup"><span data-stu-id="982f1-108">Before you get started, make sure you complete these steps:</span></span>
- <span data-ttu-id="982f1-109">Synchronisieren von Benutzern mit Azure AD mit Azure AD Connect.</span><span class="sxs-lookup"><span data-stu-id="982f1-109">Synchronize users to Azure AD with Azure AD Connect.</span></span>
- <span data-ttu-id="982f1-110">Schließen Sie die Azure AD Connect Organizational Unit (OU)-Synchronisierung ab.</span><span class="sxs-lookup"><span data-stu-id="982f1-110">Complete Azure AD Connect Organizational Unit (OU) sync.</span></span>
- <span data-ttu-id="982f1-111">Stellen Sie sicher, dass alle Domänenbenutzer, die Sie synchronisieren, über Lizenzen mit Microsoft 365 Business Premium verfügen.</span><span class="sxs-lookup"><span data-stu-id="982f1-111">Make sure all the domain users you sync have licenses to Microsoft 365 Business Premium.</span></span>

<span data-ttu-id="982f1-112">Die [Schritte finden Sie unter Synchronisieren von Domänenbenutzern](manage-domain-users.md) mit Microsoft.</span><span class="sxs-lookup"><span data-stu-id="982f1-112">See [Synchronize domain users to Microsoft](manage-domain-users.md) for the steps.</span></span>

## <a name="1-verify-mdm-authority-in-intune"></a><span data-ttu-id="982f1-113">1. Überprüfen der MDM-Autorität in Intune</span><span class="sxs-lookup"><span data-stu-id="982f1-113">1. Verify MDM Authority in Intune</span></span>

<span data-ttu-id="982f1-114">Wechseln Sie zu [Endpoint Manager,](https://endpoint.microsoft.com/#blade/Microsoft_Intune_Enrollment/EnrollmentMenu/overview) und wählen Sie auf  der Seite Microsoft Intune die Option Geräteregistrierung **aus,** und stellen Sie dann auf der Seite Übersicht sicher, dass **die MDM-Autorität** **Intune ist.**</span><span class="sxs-lookup"><span data-stu-id="982f1-114">Go to [Endpoint Manager](https://endpoint.microsoft.com/#blade/Microsoft_Intune_Enrollment/EnrollmentMenu/overview) and on the Microsoft Intune page, select **Device enrollment**, then on the **Overview** page, make sure **MDM authority** is **Intune**.</span></span>

- <span data-ttu-id="982f1-115">Wenn **die MDM-Autorität** **Keine ist,** klicken Sie auf die **MDM-Autorität,** um sie auf **Intune zu setzen.**</span><span class="sxs-lookup"><span data-stu-id="982f1-115">If **MDM authority** is **None**, click the **MDM authority** to set it to **Intune**.</span></span>
- <span data-ttu-id="982f1-116">Wenn **die MDM-Autorität** Microsoft Office **365** ist, wechseln Sie zu Geräte registrieren Geräte registrieren, und verwenden Sie das Dialogfeld MdM-Autorität hinzufügen auf der rechten Seite, um intune MDM-Autorität hinzuzufügen (das Dialogfeld MDM-Autorität hinzufügen ist nur verfügbar, wenn die MDM-Autorität auf Microsoft Office  >   365 festgelegt ist).    </span><span class="sxs-lookup"><span data-stu-id="982f1-116">If **MDM authority** is **Microsoft Office 365**,go to **Devices** > **Enroll devices** and use the **Add MDM authority** dialog on the right to add **Intune MDM** authority (the **Add MDM Authority** dialog is only available if the **MDM Authority** is set to Microsoft Office 365).</span></span>

## <a name="2-verify-azure-ad-is-enabled-for-joining-computers"></a><span data-ttu-id="982f1-117">2. Überprüfen, ob Azure AD für den Beitritt zu Computern aktiviert ist</span><span class="sxs-lookup"><span data-stu-id="982f1-117">2. Verify Azure AD is enabled for joining computers</span></span>

- <span data-ttu-id="982f1-118">Wechseln Sie zum Admin Center unter, und wählen Sie Azure Active Directory (wählen Sie Alle anzeigen aus, wenn Azure Active Directory nicht sichtbar ist) in der Liste <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> **Admin Center** aus. </span><span class="sxs-lookup"><span data-stu-id="982f1-118">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>  and select **Azure Active Directory** (select Show all if Azure Active Directory is not visible) in the **Admin centers** list.</span></span> 
- <span data-ttu-id="982f1-119">Wechseln Sie **im Azure Active Directory Admin Center** zu Azure Active **Directory,** wählen Sie **Geräte** und dann **Geräteeinstellungen aus.**</span><span class="sxs-lookup"><span data-stu-id="982f1-119">In the **Azure Active Directory admin center**, go to **Azure Active Directory** , choose **Devices** and then **Device settings**.</span></span>
- <span data-ttu-id="982f1-120">Überprüfen,**ob Benutzer Geräte zu Azure AD beitreten können aktiviert** ist</span><span class="sxs-lookup"><span data-stu-id="982f1-120">Verify **Users may join devices to Azure AD** is enabled</span></span> 
    1. <span data-ttu-id="982f1-121">Um alle Benutzer zu aktivieren, legen Sie auf **Alle .**</span><span class="sxs-lookup"><span data-stu-id="982f1-121">To enable all users, set to **All**.</span></span>
    2. <span data-ttu-id="982f1-122">Um bestimmte Benutzer zu aktivieren, legen Sie auf **Ausgewählt festgelegt,** um eine bestimmte Gruppe von Benutzern zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="982f1-122">To enable specific users, set to **Selected** to enable a specific group of users.</span></span>
        - <span data-ttu-id="982f1-123">Fügen Sie die gewünschten Domänenbenutzer, die in Azure AD synchronisiert wurden, einer [Sicherheitsgruppe hinzu.](../admin/create-groups/create-groups.md)</span><span class="sxs-lookup"><span data-stu-id="982f1-123">Add the desired domain users synced in Azure AD to a [security group](../admin/create-groups/create-groups.md).</span></span>
        - <span data-ttu-id="982f1-124">Wählen **Sie Gruppen auswählen** aus, um den MDM-Benutzerbereich für diese Sicherheitsgruppe zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="982f1-124">Choose **Select groups** to enable MDM user scope for that security group.</span></span>

## <a name="3-verify-azure-ad-is-enabled-for-mdm"></a><span data-ttu-id="982f1-125">3. Überprüfen, ob Azure AD für MDM aktiviert ist</span><span class="sxs-lookup"><span data-stu-id="982f1-125">3. Verify Azure AD is enabled for MDM</span></span>

- <span data-ttu-id="982f1-126">Wechseln Sie zum Admin Center unter, und wählen Sie <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> **Endpoint Managemen** t aus (wählen Sie **Alle** anzeigen aus, wenn **Endpoint Manager** nicht sichtbar ist)</span><span class="sxs-lookup"><span data-stu-id="982f1-126">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>  and select select **Endpoint Managemen** t (select **Show all** if **Endpoint Manager** is not visible)</span></span>
- <span data-ttu-id="982f1-127">Wechseln Sie **im Microsoft Endpoint Manager Admin Center** zu **Geräte**  >  **Windows Windows**  >  **Registrierung**  >  **automatische Registrierung**.</span><span class="sxs-lookup"><span data-stu-id="982f1-127">In the **Microsoft Endpoint Manager admin center**, go to **Devices** > **Windows** > **Windows Enrollment** > **Automatic Enrollment**.</span></span>
- <span data-ttu-id="982f1-128">Überprüfen Sie, ob der MDM-Benutzerbereich aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="982f1-128">Verify MDM user scope is enabled.</span></span>

    1. <span data-ttu-id="982f1-129">Wenn Sie alle Computer  registrieren möchten, legen Sie all fest, um alle Benutzercomputer, die Azure AD beigetreten sind, und neue Computer automatisch zu registrieren, wenn die Benutzer Windows ein Arbeitskonto hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="982f1-129">To enroll all computers, set to **All** to automatically enroll all user computers that are joined to Azure AD and new computers  when the users add a work account to Windows.</span></span>
    2. <span data-ttu-id="982f1-130">Wird auf **Einige festgelegt,** um die Computer einer bestimmten Gruppe von Benutzern zu registrieren.</span><span class="sxs-lookup"><span data-stu-id="982f1-130">Set to **Some** to enroll the computers of a specific group of users.</span></span>
        -  <span data-ttu-id="982f1-131">Fügen Sie die gewünschten Domänenbenutzer, die in Azure AD synchronisiert wurden, einer [Sicherheitsgruppe hinzu.](../admin/create-groups/create-groups.md)</span><span class="sxs-lookup"><span data-stu-id="982f1-131">Add the desired domain users synced in Azure AD to a [security group](../admin/create-groups/create-groups.md).</span></span>
        -  <span data-ttu-id="982f1-132">Wählen **Sie Gruppen auswählen** aus, um den MDM-Benutzerbereich für diese Sicherheitsgruppe zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="982f1-132">Choose **Select groups** to enable MDM user scope for that security group.</span></span>

## <a name="4-create-the-required-resources"></a><span data-ttu-id="982f1-133">4. Erstellen der erforderlichen Ressourcen</span><span class="sxs-lookup"><span data-stu-id="982f1-133">4. Create the required resources</span></span> 

<span data-ttu-id="982f1-134">Die Ausführung der [](/azure/active-directory/devices/hybrid-azuread-join-managed-domains#configure-hybrid-azure-ad-join) erforderlichen Aufgaben zum Konfigurieren der Azure AD-Hybrid-Verknüpfung wurde durch die Verwendung des [Cmdlets Initialize-SecMgmtHybirdDeviceEnrollment](https://github.com/microsoft/secmgmt-open-powershell/blob/master/docs/help/Initialize-SecMgmtHybirdDeviceEnrollment.md) im [SecMgmt](https://www.powershellgallery.com/packages/SecMgmt) PowerShell-Modul vereinfacht.</span><span class="sxs-lookup"><span data-stu-id="982f1-134">Performing the required tasks to [configure hybrid Azure AD join](/azure/active-directory/devices/hybrid-azuread-join-managed-domains#configure-hybrid-azure-ad-join) has been simplified through the use of the [Initialize-SecMgmtHybirdDeviceEnrollment](https://github.com/microsoft/secmgmt-open-powershell/blob/master/docs/help/Initialize-SecMgmtHybirdDeviceEnrollment.md) cmdlet found in the [SecMgmt](https://www.powershellgallery.com/packages/SecMgmt) PowerShell module.</span></span> <span data-ttu-id="982f1-135">Wenn Sie dieses Cmdlet aufrufen, wird der erforderliche Dienstverbindungspunkt und die Gruppenrichtlinie erstellt und konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="982f1-135">When you invoke this cmdlet it will create and configure the required service connection point and group policy.</span></span>

<span data-ttu-id="982f1-136">Sie können dieses Modul installieren, indem Sie folgendes aus einer Instanz von PowerShell aufrufen:</span><span class="sxs-lookup"><span data-stu-id="982f1-136">You can install this module by invoking the following from an instance of PowerShell:</span></span>

```powershell
Install-Module SecMgmt
```

> [!IMPORTANT]
> <span data-ttu-id="982f1-137">Es wird empfohlen, dieses Modul auf dem Windows Server mit Azure AD Connect zu installieren.</span><span class="sxs-lookup"><span data-stu-id="982f1-137">It is recommended that you install this module on the Windows Server running Azure AD Connect.</span></span>

<span data-ttu-id="982f1-138">Zum Erstellen der erforderlichen Dienstverbindungspunkt- und Gruppenrichtlinie rufen Sie das  [Cmdlet Initialize-SecMgmtHybirdDeviceEnrollment](https://github.com/microsoft/secmgmt-open-powershell/blob/master/docs/help/Initialize-SecMgmtHybirdDeviceEnrollment.md) auf.</span><span class="sxs-lookup"><span data-stu-id="982f1-138">To create the required service connection point and group policy, you will invoke the  [Initialize-SecMgmtHybirdDeviceEnrollment](https://github.com/microsoft/secmgmt-open-powershell/blob/master/docs/help/Initialize-SecMgmtHybirdDeviceEnrollment.md) cmdlet.</span></span> <span data-ttu-id="982f1-139">Sie benötigen ihre globalen Microsoft 365 Business Premium-Administratoranmeldeinformationen, wenn Sie diese Aufgabe ausführen.</span><span class="sxs-lookup"><span data-stu-id="982f1-139">You will need your Microsoft 365 Business Premium global admin credentials when performing this task.</span></span> <span data-ttu-id="982f1-140">Wenn Sie bereit sind, die Ressourcen zu erstellen, rufen Sie Folgendes auf:</span><span class="sxs-lookup"><span data-stu-id="982f1-140">When you are ready to create the resources, invoke the following:</span></span>

```powershell
PS C:\> Connect-SecMgmtAccount
PS C:\> Initialize-SecMgmtHybirdDeviceEnrollment -GroupPolicyDisplayName 'Device Management'
```

<span data-ttu-id="982f1-141">Mit dem ersten Befehl wird eine Verbindung mit der Microsoft Cloud erstellt, und wenn Sie dazu aufgefordert werden, geben Sie Ihre globalen Microsoft 365 Business Premium-Administratoranmeldeinformationen an.</span><span class="sxs-lookup"><span data-stu-id="982f1-141">The first command will establish a connection with the Microsoft cloud, and when you are prompted, specify your Microsoft 365 Business Premium global admin credentials.</span></span>

## <a name="5-link-the-group-policy"></a><span data-ttu-id="982f1-142">5. Verknüpfen der Gruppenrichtlinie</span><span class="sxs-lookup"><span data-stu-id="982f1-142">5. Link the Group Policy</span></span>

1. <span data-ttu-id="982f1-143">Klicken Sie in der Gruppenrichtlinienverwaltungskonsole (GPMC) mit der rechten Maustaste auf den Speicherort, an dem Sie die Richtlinie verknüpfen möchten, und wählen Sie im Kontextmenü *Link ein* vorhandenes Gruppenrichtlinienobjekt... aus.</span><span class="sxs-lookup"><span data-stu-id="982f1-143">In the Group Policy Management Console (GPMC), right-click on the location where you want to link the policy and select *Link an existing GPO...* from the context menu.</span></span>
2. <span data-ttu-id="982f1-144">Wählen Sie die im obigen Schritt erstellte Richtlinie aus, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="982f1-144">Select the policy created in the above step, then click **OK**.</span></span>

## <a name="get-the-latest-administrative-templates"></a><span data-ttu-id="982f1-145">Die neuesten administrativen Vorlagen erhalten</span><span class="sxs-lookup"><span data-stu-id="982f1-145">Get the latest Administrative Templates</span></span>

<span data-ttu-id="982f1-146">Wenn die Richtlinie Automatische **MDM-Registrierung** mit standardmäßigen Azure AD-Anmeldeinformationen aktivieren nicht angezeigt wird, liegt dies möglicherweise daran, dass ADMX nicht für Windows 10, Version 1803 oder höher, installiert ist.</span><span class="sxs-lookup"><span data-stu-id="982f1-146">If you do not see the policy **Enable automatic MDM enrollment using default Azure AD credentials**, it may be because you don’t have the ADMX installed for Windows 10, version 1803, or later.</span></span> <span data-ttu-id="982f1-147">Führen Sie die folgenden Schritte aus, um das Problem zu beheben (Hinweis: Die neueste MDM.admx ist abwärtskompatibel):</span><span class="sxs-lookup"><span data-stu-id="982f1-147">To fix the issue, follow these steps (Note: the latest MDM.admx is backwards compatible):</span></span>

1.  <span data-ttu-id="982f1-148">Download: [Administrative Vorlagen (ADMX) für Windows 10 October 2020 Update (20H2)](https://www.microsoft.com/download/102157).</span><span class="sxs-lookup"><span data-stu-id="982f1-148">Download: [Administrative Templates (.admx) for Windows 10 October 2020 Update (20H2)](https://www.microsoft.com/download/102157).</span></span>
2.  <span data-ttu-id="982f1-149">Installieren Sie das Paket auf einem Domänencontroller.</span><span class="sxs-lookup"><span data-stu-id="982f1-149">Install the package on a Domain Controller.</span></span>
3.  <span data-ttu-id="982f1-150">Navigieren Sie in Abhängigkeit von der Version administrative Vorlagen zum Ordner: **C:\Program Files (x86)\Microsoft Group Policy\Windows 10 October 2020 Update (20H2)**.</span><span class="sxs-lookup"><span data-stu-id="982f1-150">Navigate, depending on the Administrative Templates version to the folder: **C:\Program Files (x86)\Microsoft Group Policy\Windows 10 October 2020 Update (20H2)**.</span></span>
4.  <span data-ttu-id="982f1-151">Benennen Sie **den Ordner Richtliniendefinitionen** im obigen Pfad in **PolicyDefinitions um.**</span><span class="sxs-lookup"><span data-stu-id="982f1-151">Rename the **Policy Definitions** folder in the above path to **PolicyDefinitions**.</span></span>
5.  <span data-ttu-id="982f1-152">Kopieren Sie **den Ordner PolicyDefinitions** in Ihre SYSVOL-Freigabe, die sich standardmäßig unter **C:\Windows\SYSVOL\domain\Policies befindet.**</span><span class="sxs-lookup"><span data-stu-id="982f1-152">Copy the **PolicyDefinitions** folder to your SYSVOL share, by default located at **C:\Windows\SYSVOL\domain\Policies**.</span></span> 
    -   <span data-ttu-id="982f1-153">Wenn Sie planen, einen zentralen Richtlinienspeicher für Ihre gesamte Domäne zu verwenden, fügen Sie dort den Inhalt von PolicyDefinitions hinzu.</span><span class="sxs-lookup"><span data-stu-id="982f1-153">If you plan to use a central policy store for your entire domain, add the contents of PolicyDefinitions there.</span></span>
6.  <span data-ttu-id="982f1-154">Für den Fall, dass Mehrere Domänencontroller vorhanden sind, warten Sie, bis SYSVOL repliziert wird, bis die Richtlinien verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="982f1-154">In case you have several Domain Controllers, wait for SYSVOL to replicate for the policies to be available.</span></span> <span data-ttu-id="982f1-155">Dieses Verfahren funktioniert auch für jede zukünftige Version der administrativen Vorlagen.</span><span class="sxs-lookup"><span data-stu-id="982f1-155">This procedure will work for any future version of the Administrative Templates as well.</span></span>

<span data-ttu-id="982f1-156">An diesem Punkt sollte die Richtlinie Automatische MDM-Registrierung aktivieren mit standardmäßig verfügbaren **Azure AD-Anmeldeinformationen angezeigt** werden.</span><span class="sxs-lookup"><span data-stu-id="982f1-156">At this point you should be able to see the policy **Enable automatic MDM enrollment using default Azure AD credentials** available.</span></span>