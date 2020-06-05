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
ms.openlocfilehash: 857651081fb10856d28dd419333ebef655388407
ms.sourcegitcommit: e6e704cbd9a50fc7db1e6a0cf5d3f8c6cbb94363
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "44564941"
---
# <a name="enable-domain-joined-windows-10-devices-to-be-managed-by-microsoft-365-business-premium"></a><span data-ttu-id="06c0d-103">Aktivieren von Domänenbeitritt von Windows 10-Geräten, die von Microsoft 365 Business Premium verwaltet werden</span><span class="sxs-lookup"><span data-stu-id="06c0d-103">Enable domain-joined Windows 10 devices to be managed by Microsoft 365 Business Premium</span></span>

<span data-ttu-id="06c0d-104">Wenn Ihre Organisation Windows Server Active Directory lokal verwendet, können Sie Microsoft 365 Business Premium zum Schutz Ihrer Windows 10-Geräte einrichten und gleichzeitig den Zugriff auf lokale Ressourcen aufrecht erhalten, die lokale Authentifizierung erfordern.</span><span class="sxs-lookup"><span data-stu-id="06c0d-104">If your organization uses Windows Server Active Directory on-premises, you can set up Microsoft 365 Business Premium to protect your Windows 10 devices, while still maintaining access to on-premises resources that require local authentication.</span></span>
<span data-ttu-id="06c0d-105">Um diesen Schutz einzurichten, können Sie **hybride Azure AD verbundene Geräte**implementieren.</span><span class="sxs-lookup"><span data-stu-id="06c0d-105">To set up this protection, you can implement **Hybrid Azure AD joined devices**.</span></span> <span data-ttu-id="06c0d-106">Diese Geräte sind sowohl mit Ihrem lokalen Active Directory als auch mit Ihrem Azure-Active Directory verbunden.</span><span class="sxs-lookup"><span data-stu-id="06c0d-106">These devices are joined to both your on-premises Active Directory and your Azure Active Directory.</span></span>

<span data-ttu-id="06c0d-107">In diesem Video werden die Schritte beschrieben, wie Sie dies für das am häufigsten verwendete Szenario einrichten, das auch in den folgenden Schritten detailliert erläutert wird.</span><span class="sxs-lookup"><span data-stu-id="06c0d-107">This video describes the steps for how to set this up for the most common scenario, which is also detailed in the steps that follow.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3C9hO]
  

## <a name="before-you-get-started-make-sure-you-complete-these-steps"></a><span data-ttu-id="06c0d-108">Bevor Sie beginnen, stellen Sie sicher, dass Sie die folgenden Schritte ausführen:</span><span class="sxs-lookup"><span data-stu-id="06c0d-108">Before you get started, make sure you complete these steps:</span></span>
- <span data-ttu-id="06c0d-109">Synchronisieren von Benutzern mit dem Azure AD mit Azure AD Connect.</span><span class="sxs-lookup"><span data-stu-id="06c0d-109">Synchronize users to Azure AD with Azure AD Connect.</span></span>
- <span data-ttu-id="06c0d-110">Schließen Sie die Synchronisierung Azure AD Connect Organizational Unit (OU) ab.</span><span class="sxs-lookup"><span data-stu-id="06c0d-110">Complete Azure AD Connect Organizational Unit (OU) sync.</span></span>
- <span data-ttu-id="06c0d-111">Stellen Sie sicher, dass alle von Ihnen synchronisierten Domänenbenutzer Lizenzen für Microsoft 365 Business Premium haben.</span><span class="sxs-lookup"><span data-stu-id="06c0d-111">Make sure all the domain users you sync have licenses to Microsoft 365 Business Premium.</span></span>

<span data-ttu-id="06c0d-112">Die Schritte finden Sie unter [Synchronisieren von Domänenbenutzern mit Microsoft](manage-domain-users.md) .</span><span class="sxs-lookup"><span data-stu-id="06c0d-112">See [Synchronize domain users to Microsoft](manage-domain-users.md) for the steps.</span></span>

## <a name="1-verify-mdm-authority-in-intune"></a><span data-ttu-id="06c0d-113">1. Überprüfen der MDM-Autorität in InTune</span><span class="sxs-lookup"><span data-stu-id="06c0d-113">1. Verify MDM Authority in Intune</span></span>

<span data-ttu-id="06c0d-114">Wechseln Sie zu Portal.Azure.com, und klicken Sie oben auf der Seite auf die Suche nach InTune.</span><span class="sxs-lookup"><span data-stu-id="06c0d-114">Go to portal.azure.com and on the top of the page search for Intune.</span></span>
<span data-ttu-id="06c0d-115">Wählen Sie auf der Seite Microsoft InTune die Option **Geräteregistrierung** aus, und stellen Sie auf der Seite **Übersicht** sicher, dass die **MDM-Autorität** **InTune**ist.</span><span class="sxs-lookup"><span data-stu-id="06c0d-115">On the Microsoft Intune page, select **Device enrollment** and on the **Overview** page make sure **MDM authority** is **Intune**.</span></span>

- <span data-ttu-id="06c0d-116">Wenn **MDM Authority** **keine**ist, klicken Sie auf die **MDM-Autorität** , um Sie auf **InTune**festzulegen.</span><span class="sxs-lookup"><span data-stu-id="06c0d-116">If **MDM authority** is **None**, click the **MDM authority** to set it to **Intune**.</span></span>
- <span data-ttu-id="06c0d-117">Wenn **MDM Authority** **Microsoft Office 365**ist, wechseln Sie zu **Geräte**  >  **Registrieren von Geräten** , und verwenden Sie das Dialogfeld MDM- **Autorität hinzufügen** auf der rechten Seite zum Hinzufügen von **InTune-MDM** -Autorität (das Dialogfeld MDM- **Autorität hinzufügen** ist nur verfügbar, wenn die MDM- **Autorität** auf Microsoft Office 365 festgelegt ist).</span><span class="sxs-lookup"><span data-stu-id="06c0d-117">If **MDM authority** is **Microsoft Office 365**,go to **Devices** > **Enroll devices** and use the **Add MDM authority** dialog on the right to add **Intune MDM** authority (the **Add MDM Authority** dialog is only available if the **MDM Authority** is set to Microsoft Office 365).</span></span>

## <a name="2-verify-azure-ad-is-enabled-for-joining-computers"></a><span data-ttu-id="06c0d-118">2. überprüfen, ob Azure AD für das Hinzufügen von Computern aktiviert ist</span><span class="sxs-lookup"><span data-stu-id="06c0d-118">2. Verify Azure AD is enabled for joining computers</span></span>

- <span data-ttu-id="06c0d-119">Wechseln Sie zum Admin Center unter <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> , und wählen Sie **Azure Active Directory** (Wählen Sie alle anzeigen, wenn Azure Active Directory nicht sichtbar ist) in der Liste **Admin** Center aus.</span><span class="sxs-lookup"><span data-stu-id="06c0d-119">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>  and select **Azure Active Directory** (select Show all if Azure Active Directory is not visible) in the **Admin centers** list.</span></span> 
- <span data-ttu-id="06c0d-120">Wechseln Sie im **Azure Active Directory Admin Center**zu **Azure Active Directory** , wählen Sie **Geräte** und dann **Geräteeinstellungen**aus.</span><span class="sxs-lookup"><span data-stu-id="06c0d-120">In the **Azure Active Directory admin center**, go to **Azure Active Directory** , choose **Devices** and then **Device settings**.</span></span>
- <span data-ttu-id="06c0d-121">Sicherstellen **, dass Benutzer Geräte an Azure AD** aktiviert werden können</span><span class="sxs-lookup"><span data-stu-id="06c0d-121">Verify**Users may join devices to Azure AD** is enabled</span></span> 
    1. <span data-ttu-id="06c0d-122">Um alle Benutzer zu aktivieren, legen Sie **alle**fest.</span><span class="sxs-lookup"><span data-stu-id="06c0d-122">To enable all users, set to **All**.</span></span>
    2. <span data-ttu-id="06c0d-123">Um bestimmte Benutzer zu aktivieren, legen Sie auf **ausgewählt** fest, um eine bestimmte Gruppe von Benutzern zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="06c0d-123">To enable specific users, set to **Selected** to enable a specific group of users.</span></span>
        - <span data-ttu-id="06c0d-124">Fügen Sie die gewünschten Domänenbenutzer, die in Azure AD synchronisiert wurden, zu einer [Sicherheitsgruppe](../admin/create-groups/create-groups.md)hinzu.</span><span class="sxs-lookup"><span data-stu-id="06c0d-124">Add the desired domain users synced in Azure AD to a [security group](../admin/create-groups/create-groups.md).</span></span>
        - <span data-ttu-id="06c0d-125">Wählen **Sie Gruppen auswählen** aus, um den MDM-Benutzerbereich für diese Sicherheitsgruppe zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="06c0d-125">Choose **Select groups** to enable MDM user scope for that security group.</span></span>

## <a name="3-verify-azure-ad-is-enabled-for-mdm"></a><span data-ttu-id="06c0d-126">3. überprüfen Azure AD für MDM aktiviert ist</span><span class="sxs-lookup"><span data-stu-id="06c0d-126">3. Verify Azure AD is enabled for MDM</span></span>

- <span data-ttu-id="06c0d-127">Wechseln Sie zum Admin Center unter <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> , und wählen Sie " **Endpunkt Verwaltung**auswählen" aus (Wählen Sie **Alle anzeigen** aus, wenn **Endpunkt-Manager** nicht sichtbar ist)</span><span class="sxs-lookup"><span data-stu-id="06c0d-127">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>  and select select **Endpoint Managemen**t (select **Show all** if **Endpoint Manager** is not visible)</span></span>
- <span data-ttu-id="06c0d-128">Wechseln Sie im **Microsoft Endpoint Manager Admin Center**zu **Geräte**  >  **Windows**  >  **Windows-Registrierung**für die  >  **automatische Registrierung**.</span><span class="sxs-lookup"><span data-stu-id="06c0d-128">In the **Microsoft Endpoint Manager admin center**, go to **Devices** > **Windows** > **Windows Enrollment** > **Automatic Enrollment**.</span></span>
- <span data-ttu-id="06c0d-129">Überprüfen Sie, dass der MDM-Benutzerbereich aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="06c0d-129">Verify MDM user scope is enabled.</span></span>

    1. <span data-ttu-id="06c0d-130">Wenn Sie alle Computer registrieren möchten, **legen Sie alle** fest, damit alle Benutzer Computer, die zu Azure AD und zu neuen Computern gehören, automatisch registriert werden, wenn die Benutzer ein Arbeitskonto zu Windows hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="06c0d-130">To enroll all computers, set to **All** to automatically enroll all user computers that are joined to Azure AD and new computers  when the users add a work account to Windows.</span></span>
    2. <span data-ttu-id="06c0d-131">Auf **einige** festlegen, um die Computer einer bestimmten Gruppe von Benutzern zu registrieren.</span><span class="sxs-lookup"><span data-stu-id="06c0d-131">Set to **Some** to enroll the computers of a specific group of users.</span></span>
        -  <span data-ttu-id="06c0d-132">Fügen Sie die gewünschten Domänenbenutzer, die in Azure AD synchronisiert wurden, zu einer [Sicherheitsgruppe](../admin/create-groups/create-groups.md)hinzu.</span><span class="sxs-lookup"><span data-stu-id="06c0d-132">Add the desired domain users synced in Azure AD to a [security group](../admin/create-groups/create-groups.md).</span></span>
        -  <span data-ttu-id="06c0d-133">Wählen **Sie Gruppen auswählen** aus, um den MDM-Benutzerbereich für diese Sicherheitsgruppe zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="06c0d-133">Choose **Select groups** to enable MDM user scope for that security group.</span></span>

## <a name="4-set-up-service-connection-point-scp"></a><span data-ttu-id="06c0d-134">4. Einrichten des Dienstverbindungspunkts (SCP)</span><span class="sxs-lookup"><span data-stu-id="06c0d-134">4. Set up Service connection point (SCP)</span></span>

<span data-ttu-id="06c0d-135">Diese Schritte werden von [configure Hybrid Azure AD Join](https://docs.microsoft.com/azure/active-directory/devices/hybrid-azuread-join-managed-domains#configure-hybrid-azure-ad-join)vereinfacht.</span><span class="sxs-lookup"><span data-stu-id="06c0d-135">These steps are simplified from [configure hybrid azure AD join](https://docs.microsoft.com/azure/active-directory/devices/hybrid-azuread-join-managed-domains#configure-hybrid-azure-ad-join).</span></span> <span data-ttu-id="06c0d-136">Führen Sie die erforderlichen Schritte für die Verwendung Azure AD Connect und Ihrer Microsoft 365 Business Premium-Administrator-und Active Directory-Administratorkennwörter aus.</span><span class="sxs-lookup"><span data-stu-id="06c0d-136">To complete the steps you need to use Azure AD Connect and your Microsoft 365 Business Premium global admin and Active Directory admin passwords.</span></span>

1.  <span data-ttu-id="06c0d-137">Starten Sie Azure AD Connect, und wählen Sie dann **configure**aus.</span><span class="sxs-lookup"><span data-stu-id="06c0d-137">Start Azure AD Connect, and then select **Configure**.</span></span>
2.  <span data-ttu-id="06c0d-138">Wählen Sie auf der Seite **Weitere Aufgaben** die Option **Geräteoptionen konfigurieren**aus, und wählen Sie dann **weiter**aus.</span><span class="sxs-lookup"><span data-stu-id="06c0d-138">On the **Additional tasks**  page, select **Configure device options**, and then select **Next**.</span></span>
3.  <span data-ttu-id="06c0d-139">Wählen Sie auf der Seite **Übersicht** die Option **weiter**aus.</span><span class="sxs-lookup"><span data-stu-id="06c0d-139">On the **Overview** page, select **Next**.</span></span>
4.  <span data-ttu-id="06c0d-140">Geben Sie auf der Seite mit **Azure AD verbinden** die Anmeldeinformationen eines globalen Administrators für Microsoft 365 Business Premium ein.</span><span class="sxs-lookup"><span data-stu-id="06c0d-140">On the **Connect to Azure AD** page, enter the credentials of a global administrator for Microsoft 365 Business Premium.</span></span>
5.  <span data-ttu-id="06c0d-141">Wählen Sie auf der Seite **Geräteoptionen** die Option **Hybrid Azure AD beitreten konfigurieren**aus, und wählen Sie dann **weiter**aus.</span><span class="sxs-lookup"><span data-stu-id="06c0d-141">On the **Device options** page, select **Configure Hybrid Azure AD join**, and then select **Next**.</span></span>
6.  <span data-ttu-id="06c0d-142">Führen Sie auf der Seite **SCP** für jede Gesamtstruktur, in der Sie Azure AD eine Verbindung herstellen möchten, die folgenden Schritte aus, und wählen Sie dann **weiter**aus, um den SCP zu konfigurieren:</span><span class="sxs-lookup"><span data-stu-id="06c0d-142">On the **SCP** page, for each forest where you want Azure AD Connect to configure the SCP, complete the following steps, and then select **Next**:</span></span>
    - <span data-ttu-id="06c0d-143">Aktivieren Sie das Kontrollkästchen neben dem Namen der Gesamtstruktur.</span><span class="sxs-lookup"><span data-stu-id="06c0d-143">Check the box beside the forest name.</span></span> <span data-ttu-id="06c0d-144">Die Gesamtstruktur sollte der Name Ihrer AD-Domäne sein.</span><span class="sxs-lookup"><span data-stu-id="06c0d-144">The forest should be your AD domain name.</span></span>
    - <span data-ttu-id="06c0d-145">Öffnen Sie in der Spalte **Authentifizierungsdienst** das Dropdownfeld, und wählen Sie übereinstimmender Domänenname aus (es sollte nur eine einzige Option geben).</span><span class="sxs-lookup"><span data-stu-id="06c0d-145">Under the **Authentication Service** column, open the dropdown and select matching domain name (there should only be one only option).</span></span>
    - <span data-ttu-id="06c0d-146">Wählen Sie **Hinzufügen** aus, um die Anmeldeinformationen des Domänenadministrators einzugeben.</span><span class="sxs-lookup"><span data-stu-id="06c0d-146">Select **Add** to enter the domain administrator credentials.</span></span>  
7.  <span data-ttu-id="06c0d-147">Wählen Sie auf der Seite **Geräte Betriebssysteme** die Option Windows 10 oder höher nur für Domänen verbundene Geräte aus.</span><span class="sxs-lookup"><span data-stu-id="06c0d-147">On the **Device operating systems** page, select Windows 10 or later domain-joined devices only.</span></span>
8.  <span data-ttu-id="06c0d-148">Wählen Sie auf der Seite " **vorbereiten zur Konfiguration** " die Option **configure**aus.</span><span class="sxs-lookup"><span data-stu-id="06c0d-148">On the **Ready to configure** page, select **Configure**.</span></span>
9.  <span data-ttu-id="06c0d-149">Wählen Sie auf der Seite **Konfiguration abgeschlossen** die Option **Beenden**aus.</span><span class="sxs-lookup"><span data-stu-id="06c0d-149">On the **Configuration complete** page, select **Exit**.</span></span>


## <a name="5-create-a-gpo-for-intune-enrollment--admx-method"></a><span data-ttu-id="06c0d-150">5. Erstellen eines Gruppenrichtlinienobjekts für die Intune-Registrierung – ADMX-Methode</span><span class="sxs-lookup"><span data-stu-id="06c0d-150">5. Create a GPO for Intune Enrollment – ADMX method</span></span>

<span data-ttu-id="06c0d-151">Verwenden. ADMX-Vorlagendatei.</span><span class="sxs-lookup"><span data-stu-id="06c0d-151">Use .ADMX template file.</span></span>

1.  <span data-ttu-id="06c0d-152">Melden Sie sich bei Ad Server, der Such-und Open **Server Manager-**  >  **Tools**  >  **Gruppenrichtlinienverwaltung**an.</span><span class="sxs-lookup"><span data-stu-id="06c0d-152">Log on to AD server, search and open **Server Manager** > **Tools** > **Group Policy Management**.</span></span>
2.  <span data-ttu-id="06c0d-153">Wählen Sie Ihren Domänennamen unter **Domänen** aus, und klicken Sie mit der rechten Maustaste auf **Gruppenrichtlinienobjekte** , um **neu**auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="06c0d-153">Select your domain name under **Domains** and right-click **Group Policy Objects** to select **New**.</span></span>
3.  <span data-ttu-id="06c0d-154">Geben Sie dem neuen GPO einen Namen, beispielsweise "*Cloud_Enrollment*", und wählen Sie dann **OK**aus.</span><span class="sxs-lookup"><span data-stu-id="06c0d-154">Give the new GPO an name, for example “*Cloud_Enrollment*” and then select **OK**.</span></span>
4.  <span data-ttu-id="06c0d-155">Klicken Sie mit der rechten Maustaste auf das neue GPO unter **Gruppenrichtlinienobjekte** , und wählen Sie **Bearbeiten**aus.</span><span class="sxs-lookup"><span data-stu-id="06c0d-155">Right-click the new GPO under **Group Policy Objects** and select **Edit**.</span></span>
5.  <span data-ttu-id="06c0d-156">Wechseln Sie im **Gruppenrichtlinien-Verwaltungs-Editor**zu **Computer Konfigurations**  >  **Richtlinien**  >  **Administrative Vorlagen**  >  **Windows-Komponenten**  >  **MDM**.</span><span class="sxs-lookup"><span data-stu-id="06c0d-156">In the **Group Policy Management Editor**, go to **Computer Configuration** > **Policies** > **Administrative Templates** > **Windows Components** > **MDM**.</span></span>
6. <span data-ttu-id="06c0d-157">Klicken Sie mit der rechten Maustaste auf **Automatische MDM-Registrierung mithilfe der Standard Azure AD Anmeldeinformationen aktivieren** , und wählen Sie dann **aktiviert**  >  **OK**aus.</span><span class="sxs-lookup"><span data-stu-id="06c0d-157">Right-click **Enable automatic MDM enrollment using default Azure AD credentials** and then select **Enabled** > **OK**.</span></span> <span data-ttu-id="06c0d-158">Schließen Sie das Editor-Fenster.</span><span class="sxs-lookup"><span data-stu-id="06c0d-158">Close the editor window.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="06c0d-159">Wenn die **Automatische MDM-Registrierung mithilfe der Standard Azure AD Anmeldeinformationen nicht aktiviert**wird, finden Sie weitere Informationen unter [Abrufen der neuesten administrativen Vorlagen](#get-the-latest-administrative-templates).</span><span class="sxs-lookup"><span data-stu-id="06c0d-159">If you do not see the policy **Enable automatic MDM enrollment using default Azure AD credentials**, see [Get the latest Administrative Templates](#get-the-latest-administrative-templates).</span></span>

## <a name="6-deploy-the-group-policy"></a><span data-ttu-id="06c0d-160">6. Bereitstellen der Gruppenrichtlinie</span><span class="sxs-lookup"><span data-stu-id="06c0d-160">6. Deploy the Group Policy</span></span>

1.  <span data-ttu-id="06c0d-161">Wählen Sie im Server-Manager unter **Domänen** > Gruppenrichtlinienobjekte das GPO aus Schritt 3 aus, beispielsweise "Cloud_Enrollment".</span><span class="sxs-lookup"><span data-stu-id="06c0d-161">In the Server Manager, under **Domains** > Group Policy objects, select the GPO from Step 3 above, for example “Cloud_Enrollment”.</span></span>
2.  <span data-ttu-id="06c0d-162">Wählen Sie die Registerkarte **Bereich** für Ihr GPO aus.</span><span class="sxs-lookup"><span data-stu-id="06c0d-162">Select the **Scope** tab for your GPO.</span></span>
3.  <span data-ttu-id="06c0d-163">Klicken Sie auf der Registerkarte Bereich des GPO mit der rechten Maustaste auf den Link zur Domäne unter **Links**.</span><span class="sxs-lookup"><span data-stu-id="06c0d-163">In the GPO’s Scope tab, right-click the link to the domain under **Links**.</span></span>
4.  <span data-ttu-id="06c0d-164">Wählen Sie **erzwungen** aus, um das GPO bereitzustellen, und klicken Sie dann auf dem Bestätigungsbildschirm auf **OK** .</span><span class="sxs-lookup"><span data-stu-id="06c0d-164">Select **Enforced** to deploy the GPO and then **OK** in the confirmation screen.</span></span>

## <a name="get-the-latest-administrative-templates"></a><span data-ttu-id="06c0d-165">Abrufen der neuesten administrativen Vorlagen</span><span class="sxs-lookup"><span data-stu-id="06c0d-165">Get the latest Administrative Templates</span></span>

<span data-ttu-id="06c0d-166">Wenn die Richtlinie **Automatische MDM-Registrierung mithilfe der Standard Azure AD Anmeldeinformationen nicht aktiviert**wird, kann dies daran liegen, dass Sie den ADMX nicht für Windows 10, Version 1803, Version 1809 oder Version 1903 installiert haben.</span><span class="sxs-lookup"><span data-stu-id="06c0d-166">If you do not see the policy **Enable automatic MDM enrollment using default Azure AD credentials**, it may be because you don’t have the ADMX installed for Windows 10, version 1803, version 1809, or version 1903.</span></span> <span data-ttu-id="06c0d-167">Führen Sie die folgenden Schritte aus, um das Problem zu beheben (Hinweis: die neueste Version von MDM. ADMX ist abwärtskompatibel):</span><span class="sxs-lookup"><span data-stu-id="06c0d-167">To fix the issue, follow these steps (Note: the latest MDM.admx is backwards compatible):</span></span>

1.  <span data-ttu-id="06c0d-168">Download: [Administrative Vorlagen (ADMX) für Windows 10 May 2019 Update (1903)](https://www.microsoft.com/download/details.aspx?id=58495&WT.mc_id=rss_alldownloads_all).</span><span class="sxs-lookup"><span data-stu-id="06c0d-168">Download: [Administrative Templates (.admx) for Windows 10 May 2019 Update (1903)](https://www.microsoft.com/download/details.aspx?id=58495&WT.mc_id=rss_alldownloads_all).</span></span>
2.  <span data-ttu-id="06c0d-169">Installieren Sie das Paket auf dem primären Domänen Controller (PDC).</span><span class="sxs-lookup"><span data-stu-id="06c0d-169">Install the package on the Primary Domain Controller (PDC).</span></span>
3.  <span data-ttu-id="06c0d-170">Navigieren Sie je nach Version zum Ordner: **C:\Program Files (x86) \Microsoft Group Policy\Windows 10 May 2019 Update (1903) v3**.</span><span class="sxs-lookup"><span data-stu-id="06c0d-170">Navigate, depending on the version to the folder: **C:\Program Files (x86)\Microsoft Group Policy\Windows 10 May 2019 Update (1903) v3**.</span></span>
4.  <span data-ttu-id="06c0d-171">Benennen Sie den Ordner **Richtlinien Definitionen** im obigen Pfad in **PolicyDefinitions**um.</span><span class="sxs-lookup"><span data-stu-id="06c0d-171">Rename the **Policy Definitions** folder in the above path to **PolicyDefinitions**.</span></span>
5.  <span data-ttu-id="06c0d-172">Kopieren Sie **PolicyDefinitions** -Ordner in **C:\Windows\SYSVOL\domain\Policies**.</span><span class="sxs-lookup"><span data-stu-id="06c0d-172">Copy **PolicyDefinitions** folder to **C:\Windows\SYSVOL\domain\Policies**.</span></span> 
    -   <span data-ttu-id="06c0d-173">Wenn Sie einen zentralen Richtlinienspeicher für Ihre gesamte Domäne verwenden möchten, fügen Sie den Inhalt von PolicyDefinitions dort hinzu.</span><span class="sxs-lookup"><span data-stu-id="06c0d-173">If you plan to use a central policy store for your entire domain, add the contents of PolicyDefinitions there.</span></span>
6.  <span data-ttu-id="06c0d-174">Starten Sie den primären Domänen Controller neu, damit die Richtlinie zur Verfügung steht.</span><span class="sxs-lookup"><span data-stu-id="06c0d-174">Restart the Primary Domain Controller for the policy to be available.</span></span> <span data-ttu-id="06c0d-175">Dieses Verfahren kann auch für zukünftige Versionen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="06c0d-175">This procedure will work for any future version as well.</span></span>

<span data-ttu-id="06c0d-176">An dieser Position sollten Sie die **Automatische MDM-Registrierung mithilfe der standardmäßigen Azure AD** verfügbaren Anmeldeinformationen anzeigen können.</span><span class="sxs-lookup"><span data-stu-id="06c0d-176">At this point you should be able to see the policy **Enable automatic MDM enrollment using default Azure AD credentials** available.</span></span>

