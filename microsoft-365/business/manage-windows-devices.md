---
title: Aktivieren der Verwaltung von in die Domäne eingebundenen Windows 10 Geräten durch Microsoft 365 for Business
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
- AdminTemplateSet
search.appverid:
- BCS160
- MET150
description: In nur wenigen Schritten erfahren Sie, wie Sie Microsoft 365 aktivieren, um lokale Active-Directory-verbundene Windows 10-Geräte zu schützen.
ms.openlocfilehash: 9cc7ca01cec667465e9114083fecdc56ef4e7ce7
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/12/2021
ms.locfileid: "53393377"
---
# <a name="enable-domain-joined-windows-10-devices-to-be-managed-by-microsoft-365-business-premium"></a><span data-ttu-id="11a39-103">Aktivieren der Verwaltung von in die Domäne eingebundenen Windows 10 Geräten durch Microsoft 365 Business Premium</span><span class="sxs-lookup"><span data-stu-id="11a39-103">Enable domain-joined Windows 10 devices to be managed by Microsoft 365 Business Premium</span></span>

<span data-ttu-id="11a39-104">Wenn Ihre Organisation Windows Server Active Directory lokal verwendet, können Sie Microsoft 365 Business Premium einrichten, um Ihre Windows 10 Geräte zu schützen und gleichzeitig den Zugriff auf lokale Ressourcen beizubehalten, die eine lokale Authentifizierung erfordern.</span><span class="sxs-lookup"><span data-stu-id="11a39-104">If your organization uses Windows Server Active Directory on-premises, you can set up Microsoft 365 Business Premium to protect your Windows 10 devices, while still maintaining access to on-premises resources that require local authentication.</span></span>
<span data-ttu-id="11a39-105">Um diesen Schutz einzurichten, können Sie **in Azure AD eingebundene Hybridgeräte** implementieren.</span><span class="sxs-lookup"><span data-stu-id="11a39-105">To set up this protection, you can implement **Hybrid Azure AD joined devices**.</span></span> <span data-ttu-id="11a39-106">Diese Geräte sind sowohl mit Ihrem lokalen Active Directory als auch mit Ihrem Azure Active Directory verbunden.</span><span class="sxs-lookup"><span data-stu-id="11a39-106">These devices are joined to both your on-premises Active Directory and your Azure Active Directory.</span></span>

## <a name="watch-configure-hybrid-azure-active-directory-join"></a><span data-ttu-id="11a39-107">Watch: Configure Hybrid Azure Active Directory join</span><span class="sxs-lookup"><span data-stu-id="11a39-107">Watch: Configure Hybrid Azure Active Directory join</span></span>

<span data-ttu-id="11a39-108">In diesem Video werden die Schritte zum Einrichten dieses Szenarios für das gängigste Szenario beschrieben. Dies wird auch in den folgenden Schritten beschrieben.</span><span class="sxs-lookup"><span data-stu-id="11a39-108">This video describes the steps for how to set this up for the most common scenario, which is also detailed in the steps that follow.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3C9hO]
  
## <a name="before-you-begin"></a><span data-ttu-id="11a39-109">Bevor Sie beginnen:</span><span class="sxs-lookup"><span data-stu-id="11a39-109">Before you begin</span></span>

- <span data-ttu-id="11a39-110">Synchronisieren von Benutzern mit Azure AD mit Azure AD Verbinden.</span><span class="sxs-lookup"><span data-stu-id="11a39-110">Synchronize users to Azure AD with Azure AD Connect.</span></span>
- <span data-ttu-id="11a39-111">Führen Sie die Synchronisierung der Azure AD-Verbinden Organisationseinheit (ORGANIZATIONAL Unit, OU) durch.</span><span class="sxs-lookup"><span data-stu-id="11a39-111">Complete Azure AD Connect Organizational Unit (OU) sync.</span></span>
- <span data-ttu-id="11a39-112">Stellen Sie sicher, dass alle domänenbenutzer, die Sie synchronisieren, über Lizenzen für Microsoft 365 Business Premium verfügen.</span><span class="sxs-lookup"><span data-stu-id="11a39-112">Make sure all the domain users you sync have licenses to Microsoft 365 Business Premium.</span></span>

<span data-ttu-id="11a39-113">Die Schritte finden Sie unter [Synchronisieren von Domänenbenutzern mit Microsoft.](manage-domain-users.md)</span><span class="sxs-lookup"><span data-stu-id="11a39-113">See [Synchronize domain users to Microsoft](manage-domain-users.md) for the steps.</span></span>

## <a name="1-verify-mdm-authority-in-intune"></a><span data-ttu-id="11a39-114">1. Überprüfen der MDM-Autorität in Intune</span><span class="sxs-lookup"><span data-stu-id="11a39-114">1. Verify MDM Authority in Intune</span></span>

<span data-ttu-id="11a39-115">Wechseln Sie zu [Endpoint Manager,](https://endpoint.microsoft.com/#blade/Microsoft_Intune_Enrollment/EnrollmentMenu/overview) und wählen Sie auf der seite Microsoft Intune die **Geräteregistrierung** aus, und stellen Sie dann auf der Seite **"Übersicht"** sicher, dass die **MDM-Autorität** **Intune** ist.</span><span class="sxs-lookup"><span data-stu-id="11a39-115">Go to [Endpoint Manager](https://endpoint.microsoft.com/#blade/Microsoft_Intune_Enrollment/EnrollmentMenu/overview) and on the Microsoft Intune page, select **Device enrollment**, then on the **Overview** page, make sure **MDM authority** is **Intune**.</span></span>

- <span data-ttu-id="11a39-116">Wenn **die MDM-Autorität** **keine** ist, klicken Sie auf die **MDM-Autorität,** um sie auf **Intune** festzulegen.</span><span class="sxs-lookup"><span data-stu-id="11a39-116">If **MDM authority** is **None**, click the **MDM authority** to set it to **Intune**.</span></span>
- <span data-ttu-id="11a39-117">Wenn **die MDM-Autorität** **Microsoft Office 365** ist, wechseln Sie **zu**  >  **Geräte registrieren,** und verwenden Sie das Dialogfeld **"MDM-Autorität hinzufügen"** auf der rechten Seite, um eine **Intune MDM-Autorität** hinzuzufügen (das Dialogfeld **"MDM-Autorität hinzufügen"** ist nur verfügbar, wenn die **MDM-Autorität** auf Microsoft Office 365 festgelegt ist).</span><span class="sxs-lookup"><span data-stu-id="11a39-117">If **MDM authority** is **Microsoft Office 365**,go to **Devices** > **Enroll devices** and use the **Add MDM authority** dialog on the right to add **Intune MDM** authority (the **Add MDM Authority** dialog is only available if the **MDM Authority** is set to Microsoft Office 365).</span></span>

## <a name="2-verify-azure-ad-is-enabled-for-joining-computers"></a><span data-ttu-id="11a39-118">2. Überprüfen, ob Azure AD für die Teilnahme an Computern aktiviert ist</span><span class="sxs-lookup"><span data-stu-id="11a39-118">2. Verify Azure AD is enabled for joining computers</span></span>

- <span data-ttu-id="11a39-119">Wechseln Sie zum Admin Center, <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> und wählen Sie **Azure Active Directory** (wählen Sie "Alle anzeigen" aus, wenn Azure Active Directory nicht sichtbar ist) in der Admin **Center-Liste.**</span><span class="sxs-lookup"><span data-stu-id="11a39-119">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>  and select **Azure Active Directory** (select Show all if Azure Active Directory is not visible) in the **Admin centers** list.</span></span> 
- <span data-ttu-id="11a39-120">Wechseln **Sie** im Azure Active Directory Admin Center zu **Azure Active Directory,** wählen Sie **"Geräte"** und dann **"Geräteeinstellungen"** aus.</span><span class="sxs-lookup"><span data-stu-id="11a39-120">In the **Azure Active Directory admin center**, go to **Azure Active Directory** , choose **Devices** and then **Device settings**.</span></span>
- <span data-ttu-id="11a39-121">Überprüfen, ob **Benutzer Geräte mit Azure AD verknüpfen können**</span><span class="sxs-lookup"><span data-stu-id="11a39-121">Verify **Users may join devices to Azure AD** is enabled</span></span> 
    1. <span data-ttu-id="11a39-122">To enable all users, set to **All**.</span><span class="sxs-lookup"><span data-stu-id="11a39-122">To enable all users, set to **All**.</span></span>
    2. <span data-ttu-id="11a39-123">Um bestimmte Benutzer zu aktivieren, legen **Sie "Ausgewählt"** fest, um eine bestimmte Gruppe von Benutzern zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="11a39-123">To enable specific users, set to **Selected** to enable a specific group of users.</span></span>
        - <span data-ttu-id="11a39-124">Fügen Sie die gewünschten Domänenbenutzer, die in Azure AD synchronisiert wurden, einer [Sicherheitsgruppe](../admin/create-groups/create-groups.md)hinzu.</span><span class="sxs-lookup"><span data-stu-id="11a39-124">Add the desired domain users synced in Azure AD to a [security group](../admin/create-groups/create-groups.md).</span></span>
        - <span data-ttu-id="11a39-125">Wählen Sie **"Gruppen auswählen"** aus, um den MDM-Benutzerbereich für diese Sicherheitsgruppe zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="11a39-125">Choose **Select groups** to enable MDM user scope for that security group.</span></span>

## <a name="3-verify-azure-ad-is-enabled-for-mdm"></a><span data-ttu-id="11a39-126">3. Überprüfen, ob Azure AD für MDM aktiviert ist</span><span class="sxs-lookup"><span data-stu-id="11a39-126">3. Verify Azure AD is enabled for MDM</span></span>

- <span data-ttu-id="11a39-127">Wechseln Sie zum Admin Center, <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> und wählen Sie **"Endpoint Managemen** t" aus (wählen Sie **"Alle anzeigen"** aus, wenn **Endpoint Manager** nicht sichtbar ist)</span><span class="sxs-lookup"><span data-stu-id="11a39-127">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>  and select select **Endpoint Managemen** t (select **Show all** if **Endpoint Manager** is not visible)</span></span>
- <span data-ttu-id="11a39-128">Wechseln Sie im **Microsoft Endpoint Manager Admin Center** zu **"Geräte**  >  **Windows** automatische Registrierung Windows  >    >  **Registrierung".**</span><span class="sxs-lookup"><span data-stu-id="11a39-128">In the **Microsoft Endpoint Manager admin center**, go to **Devices** > **Windows** > **Windows Enrollment** > **Automatic Enrollment**.</span></span>
- <span data-ttu-id="11a39-129">Überprüfen Sie, ob der MDM-Benutzerbereich aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="11a39-129">Verify MDM user scope is enabled.</span></span>

    1. <span data-ttu-id="11a39-130">Um alle Computer zu registrieren, legen Sie **"Alle"** fest, um automatisch alle Benutzercomputer zu registrieren, die mit Azure AD verbunden sind, und neue Computer, wenn die Benutzer ein Geschäftskonto zu Windows hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="11a39-130">To enroll all computers, set to **All** to automatically enroll all user computers that are joined to Azure AD and new computers  when the users add a work account to Windows.</span></span>
    2. <span data-ttu-id="11a39-131">Legen Sie diesen Wert auf **"Einige"** fest, um die Computer einer bestimmten Benutzergruppe zu registrieren.</span><span class="sxs-lookup"><span data-stu-id="11a39-131">Set to **Some** to enroll the computers of a specific group of users.</span></span>
        -  <span data-ttu-id="11a39-132">Fügen Sie die gewünschten Domänenbenutzer, die in Azure AD synchronisiert wurden, einer [Sicherheitsgruppe](../admin/create-groups/create-groups.md)hinzu.</span><span class="sxs-lookup"><span data-stu-id="11a39-132">Add the desired domain users synced in Azure AD to a [security group](../admin/create-groups/create-groups.md).</span></span>
        -  <span data-ttu-id="11a39-133">Wählen Sie **"Gruppen auswählen"** aus, um den MDM-Benutzerbereich für diese Sicherheitsgruppe zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="11a39-133">Choose **Select groups** to enable MDM user scope for that security group.</span></span>

## <a name="4-create-the-required-resources"></a><span data-ttu-id="11a39-134">4. Erstellen der erforderlichen Ressourcen</span><span class="sxs-lookup"><span data-stu-id="11a39-134">4. Create the required resources</span></span> 

<span data-ttu-id="11a39-135">Das Ausführen der erforderlichen Aufgaben zum Konfigurieren der [Azure AD-Hybridverknüpfung](/azure/active-directory/devices/hybrid-azuread-join-managed-domains#configure-hybrid-azure-ad-join) wurde durch die Verwendung des Cmdlets [Initialize-SecMgmtHy hybridDeviceEnrollment](https://github.com/microsoft/secmgmt-open-powershell/blob/master/docs/help/Initialize-SecMgmtHybirdDeviceEnrollment.md) im [SecMgmt](https://www.powershellgallery.com/packages/SecMgmt) PowerShell-Modul vereinfacht.</span><span class="sxs-lookup"><span data-stu-id="11a39-135">Performing the required tasks to [configure hybrid Azure AD join](/azure/active-directory/devices/hybrid-azuread-join-managed-domains#configure-hybrid-azure-ad-join) has been simplified through the use of the [Initialize-SecMgmtHybirdDeviceEnrollment](https://github.com/microsoft/secmgmt-open-powershell/blob/master/docs/help/Initialize-SecMgmtHybirdDeviceEnrollment.md) cmdlet found in the [SecMgmt](https://www.powershellgallery.com/packages/SecMgmt) PowerShell module.</span></span> <span data-ttu-id="11a39-136">Wenn Sie dieses Cmdlet aufrufen, wird der erforderliche Dienstverbindungspunkt und die erforderliche Gruppenrichtlinie erstellt und konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="11a39-136">When you invoke this cmdlet it will create and configure the required service connection point and group policy.</span></span>

<span data-ttu-id="11a39-137">Sie können dieses Modul installieren, indem Sie Folgendes aus einer Instanz von PowerShell aufrufen:</span><span class="sxs-lookup"><span data-stu-id="11a39-137">You can install this module by invoking the following from an instance of PowerShell:</span></span>

```powershell
Install-Module SecMgmt
```

> [!IMPORTANT]
> <span data-ttu-id="11a39-138">Es wird empfohlen, dieses Modul auf dem Windows Server zu installieren, auf dem Azure AD Verbinden ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="11a39-138">It is recommended that you install this module on the Windows Server running Azure AD Connect.</span></span>

<span data-ttu-id="11a39-139">Zum Erstellen des erforderlichen Dienstverbindungspunkts und der Gruppenrichtlinie rufen Sie das Cmdlet  ["Initialize-SecMgmtHy flyDeviceEnrollment"](https://github.com/microsoft/secmgmt-open-powershell/blob/master/docs/help/Initialize-SecMgmtHybirdDeviceEnrollment.md) auf.</span><span class="sxs-lookup"><span data-stu-id="11a39-139">To create the required service connection point and group policy, you will invoke the  [Initialize-SecMgmtHybirdDeviceEnrollment](https://github.com/microsoft/secmgmt-open-powershell/blob/master/docs/help/Initialize-SecMgmtHybirdDeviceEnrollment.md) cmdlet.</span></span> <span data-ttu-id="11a39-140">Sie benötigen ihre Microsoft 365 Business Premium globalen Administratoranmeldeinformationen, wenn Sie diese Aufgabe ausführen.</span><span class="sxs-lookup"><span data-stu-id="11a39-140">You will need your Microsoft 365 Business Premium global admin credentials when performing this task.</span></span> <span data-ttu-id="11a39-141">Wenn Sie bereit sind, die Ressourcen zu erstellen, rufen Sie Folgendes auf:</span><span class="sxs-lookup"><span data-stu-id="11a39-141">When you are ready to create the resources, invoke the following:</span></span>

```powershell
PS C:\> Connect-SecMgmtAccount
PS C:\> Initialize-SecMgmtHybirdDeviceEnrollment -GroupPolicyDisplayName 'Device Management'
```

<span data-ttu-id="11a39-142">Mit dem ersten Befehl wird eine Verbindung mit der Microsoft-Cloud hergestellt. Wenn Sie dazu aufgefordert werden, geben Sie Ihre Microsoft 365 Business Premium globalen Administratoranmeldeinformationen an.</span><span class="sxs-lookup"><span data-stu-id="11a39-142">The first command will establish a connection with the Microsoft cloud, and when you are prompted, specify your Microsoft 365 Business Premium global admin credentials.</span></span>

## <a name="5-link-the-group-policy"></a><span data-ttu-id="11a39-143">5. Verknüpfen der Gruppenrichtlinie</span><span class="sxs-lookup"><span data-stu-id="11a39-143">5. Link the Group Policy</span></span>

1. <span data-ttu-id="11a39-144">Klicken Sie in der Gruppenrichtlinien-Verwaltungskonsole (Group Policy Management Console, GPMC) mit der rechten Maustaste auf den Speicherort, an dem Sie die Richtlinie verknüpfen möchten, und wählen Sie im Kontextmenü die Option *"Vorhandenes Gruppenrichtlinienobjekt verknüpfen"* aus.</span><span class="sxs-lookup"><span data-stu-id="11a39-144">In the Group Policy Management Console (GPMC), right-click on the location where you want to link the policy and select *Link an existing GPO...* from the context menu.</span></span>
2. <span data-ttu-id="11a39-145">Wählen Sie die im obigen Schritt erstellte Richtlinie aus, und klicken Sie dann auf **"OK".**</span><span class="sxs-lookup"><span data-stu-id="11a39-145">Select the policy created in the above step, then click **OK**.</span></span>

## <a name="get-the-latest-administrative-templates"></a><span data-ttu-id="11a39-146">Abrufen der neuesten administrativen Vorlagen</span><span class="sxs-lookup"><span data-stu-id="11a39-146">Get the latest Administrative Templates</span></span>

<span data-ttu-id="11a39-147">Wenn die Richtlinie **"Automatische MDM-Registrierung mit azure AD-Standardanmeldeinformationen aktivieren"** nicht angezeigt wird, liegt dies möglicherweise daran, dass die ADMX für Windows 10, Version 1803 oder höher, nicht installiert ist.</span><span class="sxs-lookup"><span data-stu-id="11a39-147">If you do not see the policy **Enable automatic MDM enrollment using default Azure AD credentials**, it may be because you don’t have the ADMX installed for Windows 10, version 1803, or later.</span></span> <span data-ttu-id="11a39-148">Führen Sie die folgenden Schritte aus, um das Problem zu beheben (Hinweis: die neueste MDM.admx ist abwärtskompatibel):</span><span class="sxs-lookup"><span data-stu-id="11a39-148">To fix the issue, follow these steps (Note: the latest MDM.admx is backwards compatible):</span></span>

1. <span data-ttu-id="11a39-149">Download: [Administrative Vorlagen (ADMX) für Windows 10 Update vom Oktober 2020 (20H2)](https://www.microsoft.com/download/102157).</span><span class="sxs-lookup"><span data-stu-id="11a39-149">Download: [Administrative Templates (.admx) for Windows 10 October 2020 Update (20H2)](https://www.microsoft.com/download/102157).</span></span>
2. <span data-ttu-id="11a39-150">Installieren Sie das Paket auf einem Domänencontroller.</span><span class="sxs-lookup"><span data-stu-id="11a39-150">Install the package on a Domain Controller.</span></span>
3. <span data-ttu-id="11a39-151">Navigieren Sie je nach Version der administrativen Vorlagen zum Ordner: **C:\Programme (x86)\Microsoft-Gruppenrichtlinie\Windows 10 Update vom Oktober 2020 (20H2)**.</span><span class="sxs-lookup"><span data-stu-id="11a39-151">Navigate, depending on the Administrative Templates version to the folder: **C:\Program Files (x86)\Microsoft Group Policy\Windows 10 October 2020 Update (20H2)**.</span></span>
4. <span data-ttu-id="11a39-152">Benennen Sie den Ordner **"Richtliniendefinitionen"** im obigen Pfad in **"PolicyDefinitions"** um.</span><span class="sxs-lookup"><span data-stu-id="11a39-152">Rename the **Policy Definitions** folder in the above path to **PolicyDefinitions**.</span></span>
5. <span data-ttu-id="11a39-153">Kopieren Sie den **Ordner "PolicyDefinitions"** in die SYSVOL-Freigabe, die sich standardmäßig unter **"C:\Windows\SYSVOL\domain\Policies"** befindet.</span><span class="sxs-lookup"><span data-stu-id="11a39-153">Copy the **PolicyDefinitions** folder to your SYSVOL share, by default located at **C:\Windows\SYSVOL\domain\Policies**.</span></span>
   - <span data-ttu-id="11a39-154">Wenn Sie beabsichtigen, einen zentralen Richtlinienspeicher für Ihre gesamte Domäne zu verwenden, fügen Sie dort den Inhalt von PolicyDefinitions hinzu.</span><span class="sxs-lookup"><span data-stu-id="11a39-154">If you plan to use a central policy store for your entire domain, add the contents of PolicyDefinitions there.</span></span>
6. <span data-ttu-id="11a39-155">Falls Mehrere Domänencontroller vorhanden sind, warten Sie, bis SYSVOL repliziert wurde, damit die Richtlinien verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="11a39-155">In case you have several Domain Controllers, wait for SYSVOL to replicate for the policies to be available.</span></span> <span data-ttu-id="11a39-156">Dieses Verfahren funktioniert auch für jede zukünftige Version der administrativen Vorlagen.</span><span class="sxs-lookup"><span data-stu-id="11a39-156">This procedure will work for any future version of the Administrative Templates as well.</span></span>

<span data-ttu-id="11a39-157">An diesem Punkt sollten Sie in der Lage sein, die Richtlinie zum Aktivieren der **automatischen MDM-Registrierung mit den standardmäßig verfügbaren Azure AD-Anmeldeinformationen** anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="11a39-157">At this point you should be able to see the policy **Enable automatic MDM enrollment using default Azure AD credentials** available.</span></span>

## <a name="related-content"></a><span data-ttu-id="11a39-158">Verwandte Inhalte</span><span class="sxs-lookup"><span data-stu-id="11a39-158">Related content</span></span>

<span data-ttu-id="11a39-159">[Synchronisieren von Domänenbenutzern mit Microsoft 365](manage-domain-users.md) (Artikel)</span><span class="sxs-lookup"><span data-stu-id="11a39-159">[Synchronize domain users to Microsoft 365](manage-domain-users.md) (article)</span></span>\
<span data-ttu-id="11a39-160">[Erstellen einer Gruppe im Admin Center](../admin/create-groups/create-groups.md) (Artikel)</span><span class="sxs-lookup"><span data-stu-id="11a39-160">[Create a group in the admin center](../admin/create-groups/create-groups.md) (article)</span></span>\
<span data-ttu-id="11a39-161">[Lernprogramm: Konfigurieren der Hybrid-Azure Active Directory-Verknüpfung für verwaltete Domänen](/azure/active-directory/devices/hybrid-azuread-join-managed-domains.md) (Artikel)</span><span class="sxs-lookup"><span data-stu-id="11a39-161">[Tutorial: Configure hybrid Azure Active Directory join for managed domains](/azure/active-directory/devices/hybrid-azuread-join-managed-domains.md) (article)</span></span>