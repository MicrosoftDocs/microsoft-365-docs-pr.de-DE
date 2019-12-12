---
title: Übersicht über die Einrichtung
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
f1_keywords:
- O365E_M365SetupBanner
- BCS365_M365SetupBanner
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MSB365
- OKR_SMB_M365
search.appverid:
- BCS160
- MET150
ms.assetid: 6e7a2dfd-8ec4-4eb7-8390-3ee103e5fece
description: Übersicht über die Installationsschritte für Microsoft 365 Business.
ms.openlocfilehash: f531830bffbe1cb6ce4e39ee2ba12da5738a2684
ms.sourcegitcommit: 8c244b38c43dd00c4ef0102f8bed02ab36639a6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2019
ms.locfileid: "39967621"
---
# <a name="overview-of-setup"></a><span data-ttu-id="dc2ad-103">Übersicht über die Einrichtung</span><span class="sxs-lookup"><span data-stu-id="dc2ad-103">Overview of setup</span></span>

<span data-ttu-id="dc2ad-104">Die meisten Setupschritte können im Setup-Assistenten ausgeführt werden, aber auch die anderen Optionen werden aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="dc2ad-104">Most of the setup steps can be done in the setup wizard, but the other options are also listed.</span></span>

## <a name="step-1-add-your-domain-and-users"></a><span data-ttu-id="dc2ad-105">Schritt 1: Hinzufügen Ihrer Domäne und Benutzer</span><span class="sxs-lookup"><span data-stu-id="dc2ad-105">Step 1: Add your domain and users</span></span>

   - <span data-ttu-id="dc2ad-106">**[Hinzufügen Ihrer Domäne](set-up.md#add-your-domain-to-personalize-sign-in)** (wenn Sie Ihre Domäne während der [Registrierung](sign-up.md)erworben haben, ist dieser Schritt bereits abgeschlossen.)</span><span class="sxs-lookup"><span data-stu-id="dc2ad-106">**[Add your domain](set-up.md#add-your-domain-to-personalize-sign-in)** (if you bought your domain during [sign up](sign-up.md), this step is already done.)</span></span>

    - <span data-ttu-id="dc2ad-107">**Benutzer hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="dc2ad-107">**Add users**.</span></span> <span data-ttu-id="dc2ad-108">Sie können auf drei Arten Benutzer hinzufügen:</span><span class="sxs-lookup"><span data-stu-id="dc2ad-108">You can add users in any of the three ways:</span></span>
        - <span data-ttu-id="dc2ad-109">Im [Assistenten](set-up.md#add-users-in-the-wizard).</span><span class="sxs-lookup"><span data-stu-id="dc2ad-109">In the [wizard](set-up.md#add-users-in-the-wizard).</span></span>
        - <span data-ttu-id="dc2ad-110">Verwenden Sie die Verzeichnissynchronisierung, um [Benutzer mithilfe Azure AD Connect hinzuzufügen](https://docs.microsoft.com/office365/enterprise/set-up-directory-synchronization) , wenn Sie über ein lokales Active Directory verfügen.</span><span class="sxs-lookup"><span data-stu-id="dc2ad-110">Use directory synchronization to [add users by using Azure AD Connect](https://docs.microsoft.com/office365/enterprise/set-up-directory-synchronization) if you have an on-premises Active directory.</span></span>
        - <span data-ttu-id="dc2ad-111">Sie können Benutzer auch später im Admin Center [Hinzufügen](add-users-m365b.md) .</span><span class="sxs-lookup"><span data-stu-id="dc2ad-111">You can also [add users later](add-users-m365b.md) in the admin center.</span></span>
## <a name="step-2-set-up-security-policies-and-configure-devices"></a><span data-ttu-id="dc2ad-112">Schritt 2: Einrichten von Sicherheitsrichtlinien und Konfigurieren von Geräten</span><span class="sxs-lookup"><span data-stu-id="dc2ad-112">Step 2: Set up security policies and configure devices</span></span> 

  - <span data-ttu-id="dc2ad-113">Verwenden Sie den [Setup-Assistenten](set-up.md#protect-your-organization) , um Geräterichtlinien zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="dc2ad-113">Use the [Setup wizard](set-up.md#protect-your-organization) to configure device policies.</span></span> 
  - <span data-ttu-id="dc2ad-114">Sie können auch später im [Admin Center](view-policies-and-devices.md) und im [InTune-Portal](https://docs.microsoft.com/intune/tutorial-walkthrough-intune-portal)weitere hinzufügen oder bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="dc2ad-114">You can also add more or edit them later in the [admin center](view-policies-and-devices.md) and in the [Intune portal](https://docs.microsoft.com/intune/tutorial-walkthrough-intune-portal).</span></span>
  - <span data-ttu-id="dc2ad-115">Außerdem werden mit dem Setup-Assistenten grundlegende Bedrohungen und Verhinderung von Datenverlust Einstellungen eingerichtet.</span><span class="sxs-lookup"><span data-stu-id="dc2ad-115">The setup wizard will also set up basic threat protection and data loss prevention settings.</span></span>
  
  <span data-ttu-id="dc2ad-116">Zusätzlich zu den Sicherheitseinstellungen im Setup-Assistenten können Sie die Sicherheit durch Hinzufügen der folgenden Einstellungen verbessern:</span><span class="sxs-lookup"><span data-stu-id="dc2ad-116">In addition to the security settings in the setup wizard, you can increase your security by adding the following settings:</span></span>


- <span data-ttu-id="dc2ad-117">**E-Mail-Schutz vor Schadsoftware**</span><span class="sxs-lookup"><span data-stu-id="dc2ad-117">**Email malware protection**</span></span>
- <span data-ttu-id="dc2ad-118">**ATP-Anti-Phishing**</span><span class="sxs-lookup"><span data-stu-id="dc2ad-118">**ATP anti-phishing**</span></span>
- <span data-ttu-id="dc2ad-119">**Exchange Online-Archivierung**</span><span class="sxs-lookup"><span data-stu-id="dc2ad-119">**Exchange Online Archiving**</span></span>
- <span data-ttu-id="dc2ad-120">**Azure Information Protection (plan1**)</span><span class="sxs-lookup"><span data-stu-id="dc2ad-120">**Azure Information Protection (Plan1**)</span></span>


<span data-ttu-id="dc2ad-121">Für erste Schritte siehe [Einrichten von erweiterten Sicherheitsrichtlinien](set-up-advanced-security.md).</span><span class="sxs-lookup"><span data-stu-id="dc2ad-121">To get started see, [set up advanced security policies](set-up-advanced-security.md).</span></span>

<span data-ttu-id="dc2ad-122">Eine Übersicht über die besten Sicherheitsmethoden finden Sie auch unter [Top 10 Ways to Secure your Microsoft 365 Business](https://docs.microsoft.com/office365/admin/security-and-compliance/secure-your-business-data) .</span><span class="sxs-lookup"><span data-stu-id="dc2ad-122">See also [top 10 ways to secure your Microsoft 365 Business](https://docs.microsoft.com/office365/admin/security-and-compliance/secure-your-business-data) for a roadmap of best security practices.</span></span>

## <a name="step-3-set-up-and-manage-windows-10-devices"></a><span data-ttu-id="dc2ad-123">Schritt 3: Einrichten und Verwalten von Windows 10-Geräten</span><span class="sxs-lookup"><span data-stu-id="dc2ad-123">Step 3: Set up and manage Windows 10 devices</span></span>

<span data-ttu-id="dc2ad-124">Nachdem Sie den Assistenten für die Einrichtung ausgeführt haben, sollten Sie alle Windwos 10-Computer in Ihrer Organisation proctect.</span><span class="sxs-lookup"><span data-stu-id="dc2ad-124">After you run the set up wizard, you will want to proctect all the Windwos 10 computers in your organization.</span></span>
  
- <span data-ttu-id="dc2ad-125">Windows 10 pro ist eine [Voraussetzung](pre-requisites-for-data-protection.md) für Microsoft 365 Business, aber wenn Sie Windows 7 pro, Windows 8 pro oder Windows 8.1 pro haben, berechtigen Sie Ihr Abonnement zu einem [Upgrade auf Windows 10 pro](https://docs.microsoft.com/microsoft-365/business/upgrade-to-windows-pro-creators-update).</span><span class="sxs-lookup"><span data-stu-id="dc2ad-125">Windows 10 Pro is a [prerequisite](pre-requisites-for-data-protection.md) for Microsoft 365 Business, but if you have Windows 7 Pro, Windows 8 Pro, or Windows 8.1 Pro, your subscription entitles you to an [upgrade to  Windows 10 Pro](https://docs.microsoft.com/microsoft-365/business/upgrade-to-windows-pro-creators-update).</span></span>
- <span data-ttu-id="dc2ad-126">Führen Sie die Schritte unter [Secure Windows 10 PCs](secure-win-10-pcs.md) aus, um Richtlinien für Windows 10-Geräte einzurichten.</span><span class="sxs-lookup"><span data-stu-id="dc2ad-126">Follow the steps in [secure Windows 10 PCs](secure-win-10-pcs.md) to set up policies for Windows 10 devices.</span></span>

<span data-ttu-id="dc2ad-127">Wenn Sie ein Windows 10-Gerät mit Azure AD verknüpfen, werden die Richtlinien, die Sie für Windows 10-Computer festgelegt haben, auf diese angewendet.</span><span class="sxs-lookup"><span data-stu-id="dc2ad-127">When you join a Windows 10 device to Azure AD, the policies you set for Windows 10 computers get applied to it.</span></span> <span data-ttu-id="dc2ad-128">Weitere Informationen finden Sie unter [Einrichten von Windows-Geräten für Microsoft 365 Business-Benutzer](set-up-windows-devices.md).</span><span class="sxs-lookup"><span data-stu-id="dc2ad-128">For more information, see [Set up Windows devices for Microsoft 365 Business users](set-up-windows-devices.md).</span></span>

## <a name="step-4-install-office-365-business"></a><span data-ttu-id="dc2ad-129">Schritt 4: Installieren von Office 365 Business</span><span class="sxs-lookup"><span data-stu-id="dc2ad-129">Step 4: Install Office 365 Business</span></span>
- <span data-ttu-id="dc2ad-130">Sie können Office auf den Windows-Geräten automatisch mithilfe des [Setup-Assistenten](set-up.md#deploy-office-365-client-apps)installieren.</span><span class="sxs-lookup"><span data-stu-id="dc2ad-130">You can automatically install Office in the Windows devices by using the [setup wizard](set-up.md#deploy-office-365-client-apps).</span></span>
- <span data-ttu-id="dc2ad-131">Benutzer können [Office-Apps](https://docs.microsoft.com/office365/admin/setup/install-applications) für Windows und Geräte installieren.</span><span class="sxs-lookup"><span data-stu-id="dc2ad-131">Let users [install Office apps](https://docs.microsoft.com/office365/admin/setup/install-applications) for Windows and devices.</span></span>
     
## <a name="advanced"></a><span data-ttu-id="dc2ad-132">Fortgeschritten</span><span class="sxs-lookup"><span data-stu-id="dc2ad-132">Advanced</span></span>
- <span data-ttu-id="dc2ad-133">**Verwenden von Autopilot zum Einrichten neuer Geräte**</span><span class="sxs-lookup"><span data-stu-id="dc2ad-133">**Use Autopilot to set up new devices**</span></span>
            
     <span data-ttu-id="dc2ad-134">Sie können [Windows Autopilot](add-autopilot-devices-and-profile.md) verwenden, um **neue** Windows 10-Geräte für einen Benutzer automatisch vorkonfigurieren, aber es ist möglicherweise einfacher, einen [Partner](https://www.microsoft.com/solution-providers/search) zu erhalten, der dies für Sie tun kann.</span><span class="sxs-lookup"><span data-stu-id="dc2ad-134">You can use [Windows Autopilot](add-autopilot-devices-and-profile.md) to automatically pre-configure **new** Windows 10 devices for a user, but it might be easier to get a [partner](https://www.microsoft.com/solution-providers/search) who can do this for you.</span></span> <span data-ttu-id="dc2ad-135">Sie können auch zu [Microsoft Store](https://go.microsoft.com/fwlink/?linkid=874598)wechseln und einen Experten für die Cloud-Technologie bitten, neue Geräte einzurichten, die Sie kaufen.</span><span class="sxs-lookup"><span data-stu-id="dc2ad-135">You can also go to [Microsoft Store](https://go.microsoft.com/fwlink/?linkid=874598), and ask a cloud technology expert to set up new devices that you purchase.</span></span>

- <span data-ttu-id="dc2ad-136">**Zugriff auf lokale Ressourcen**</span><span class="sxs-lookup"><span data-stu-id="dc2ad-136">**Access on-premises resources**</span></span>

     - <span data-ttu-id="dc2ad-137">Wenn Ihre Organisation Windows Server Active Directory lokal verwendet, können Sie Microsoft 365 Business zum Schutz Ihrer Windows 10-Geräte einrichten und gleichzeitig den Zugriff auf lokale Ressourcen aufrecht erhalten, die lokale Authentifizierung erfordern.</span><span class="sxs-lookup"><span data-stu-id="dc2ad-137">If your organization uses Windows Server Active Directory on-premises, you can set up Microsoft 365 Business to protect your Windows 10 devices, while still maintaining access to on-premises resources that require local authentication.</span></span> <span data-ttu-id="dc2ad-138">Führen Sie die Schritte unter [enable Domain-Joined Windows 10 Devices to manage by Microsoft 365 Business](manage-windows-devices.md) aus, um diesen einzurichten.</span><span class="sxs-lookup"><span data-stu-id="dc2ad-138">Follow the steps in [Enable domain-joined Windows 10 devices to be managed by Microsoft 365 Business](manage-windows-devices.md) to set this up.</span></span> <span data-ttu-id="dc2ad-139">Dies ist die bevorzugte Methode, und Geräte in diesem Zustand werden als Hybrid Azure AD verbundene Geräte bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="dc2ad-139">This is the preferred method, and devices in this state are called Hybrid Azure AD joined devices.</span></span>

    - <span data-ttu-id="dc2ad-140">Wenn Ihr Unternehmen über ein lokales Active Directory verfügt, das einige lokale Ressourcen enthält (beispielsweise Dateifreigaben und Drucker), können Sie Ihren Azure AD-verbundenen Geräten Zugriff auf diese Ressourcen gewähren, indem Sie die folgenden Schritte ausführen: [zugreifen auf lokale Ressourcen von einem Azure AD verbundenen Gerät in Microsoft 365 Business](access-resources.md).</span><span class="sxs-lookup"><span data-stu-id="dc2ad-140">If your business has a local Active Directory that contains some on-premises resources (such as file shares and printers), you can give your Azure AD-joined devices access to these resources by following the steps here: [Access on-premises resources from an Azure AD-joined device in Microsoft 365 Business](access-resources.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="dc2ad-141">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="dc2ad-141">See also</span></span>

[<span data-ttu-id="dc2ad-142">Microsoft 365 Business Training Videos</span><span class="sxs-lookup"><span data-stu-id="dc2ad-142">Microsoft 365 Business training videos</span></span>](https://support.office.com/article/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816)
