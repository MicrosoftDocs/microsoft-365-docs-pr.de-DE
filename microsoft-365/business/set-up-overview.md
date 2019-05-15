---
title: Übersicht über die Einrichtung
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
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
search.appverid:
- BCS160
- MET150
ms.assetid: 6e7a2dfd-8ec4-4eb7-8390-3ee103e5fece
description: Übersicht über die Schritte zum Einrichten von Microsoft 365 Business.
ms.openlocfilehash: efa4d352b00ebba0cb9754c93e773d1ddaef19df
ms.sourcegitcommit: 720881c1a9c5f708e1b4adf7e5ea4ff8da48ea99
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/14/2019
ms.locfileid: "33970452"
---
# <a name="overview-of-setup"></a><span data-ttu-id="22abf-103">Übersicht über die Einrichtung</span><span class="sxs-lookup"><span data-stu-id="22abf-103">Overview of setup</span></span>

<span data-ttu-id="22abf-104">Die meisten der einrichten-Schritte können im Setup-Assistenten ausgeführt werden, die anderen Optionen werden ebenfalls aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="22abf-104">Most of the set up steps can be done in the setup wizard, but the other options are also listed.</span></span>


## <a name="step-1-add-your-domain-and-users"></a><span data-ttu-id="22abf-105">Schritt 1: Hinzufügen der Domäne und der Benutzer</span><span class="sxs-lookup"><span data-stu-id="22abf-105">Step 1: Add your domain and users</span></span>

   - <span data-ttu-id="22abf-106">**[Hinzufügen Ihrer Domäne](set-up.md#add-your-domain-to-personalize-sign-in)** (wenn Sie Ihre Domäne während der [Registrierung](sign-up.md)erworben haben, ist dieser Schritt bereits erfolgt.)</span><span class="sxs-lookup"><span data-stu-id="22abf-106">**[Add your domain](set-up.md#add-your-domain-to-personalize-sign-in)** (if you bought your domain during [sign up](sign-up.md), this step is already done.)</span></span>

    - <span data-ttu-id="22abf-107">**Benutzer hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="22abf-107">**Add users**.</span></span> <span data-ttu-id="22abf-108">Sie haben die folgenden Möglichkeiten:</span><span class="sxs-lookup"><span data-stu-id="22abf-108">You can do this in any of the three ways:</span></span>
        - <span data-ttu-id="22abf-109">Im [Assistenten](set-up.md#add-users-in-the-wizard).</span><span class="sxs-lookup"><span data-stu-id="22abf-109">In the [wizard](set-up.md#add-users-in-the-wizard).</span></span>
        - <span data-ttu-id="22abf-110">Verwenden Sie die Verzeichnissynchronisierung, um [Benutzer mithilfe von Azure AD Connect hinzuzufügen](https://docs.microsoft.com/office365/enterprise/set-up-directory-synchronization) , wenn Sie über ein lokales Active Directory verfügen.</span><span class="sxs-lookup"><span data-stu-id="22abf-110">Use directory synchronization to [add users by using Azure AD Connect](https://docs.microsoft.com/office365/enterprise/set-up-directory-synchronization) if you have an on-premises Active directory.</span></span>
        - <span data-ttu-id="22abf-111">Sie können auch später im Admin Center [Benutzer hinzufügen](add-users-m365b.md) .</span><span class="sxs-lookup"><span data-stu-id="22abf-111">You can also [add users later](add-users-m365b.md) in the admin center.</span></span>
## <a name="step-2-set-up-security-policies-and-configure-devices"></a><span data-ttu-id="22abf-112">Schritt 2: Einrichten von Sicherheitsrichtlinien und Konfigurieren von Geräten</span><span class="sxs-lookup"><span data-stu-id="22abf-112">Step 2: Set up security policies and configure devices</span></span> 

  - <span data-ttu-id="22abf-113">Verwenden Sie den [Setup-Assistenten](set-up.md#set-up-security-policies-and-device-configurations) , um Geräte-und Sicherheitsrichtlinien zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="22abf-113">Use the [Setup wizard](set-up.md#set-up-security-policies-and-device-configurations) to configure device and security policies.</span></span> 
  - <span data-ttu-id="22abf-114">Sie können Sie auch später im [Admin Center](view-policies-and-devices.md) und im [InTune-Portal](https://docs.microsoft.com/intune/tutorial-walkthrough-intune-portal)hinzufügen oder bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="22abf-114">You can also add more or edit them later in the [admin center](view-policies-and-devices.md) and in the [Intune portal](https://docs.microsoft.com/intune/tutorial-walkthrough-intune-portal).</span></span>
  - <span data-ttu-id="22abf-115">Zusätzlich zu den Sicherheitseinstellungen im Setup-Assistenten können Sie die Sicherheit verbessern, indem Sie die folgenden Einstellungen hinzufügen:</span><span class="sxs-lookup"><span data-stu-id="22abf-115">In addition to the security settings in the setup wizard, you can increase your security by adding the following settings:</span></span>

      - <span data-ttu-id="22abf-116">**Schutz von e-Mail-Schadsoftware**</span><span class="sxs-lookup"><span data-stu-id="22abf-116">**Email malware protection**</span></span>
      - <span data-ttu-id="22abf-117">**Advanced Threat Protection (ATP) sichere Links**</span><span class="sxs-lookup"><span data-stu-id="22abf-117">**Advanced Threat Protection (ATP) Safe links**</span></span>
      - <span data-ttu-id="22abf-118">**Sichere Anlagen in ATP**</span><span class="sxs-lookup"><span data-stu-id="22abf-118">**ATP Safe Attachments**</span></span>
      - <span data-ttu-id="22abf-119">**ATP-Phishing**</span><span class="sxs-lookup"><span data-stu-id="22abf-119">**ATP anti-phishing**</span></span>
      - <span data-ttu-id="22abf-120">**Exchange Online-Archivierung**</span><span class="sxs-lookup"><span data-stu-id="22abf-120">**Exchange Online Archiving**</span></span>
      - <span data-ttu-id="22abf-121">**Verhinderung von Datenverlust**</span><span class="sxs-lookup"><span data-stu-id="22abf-121">**Data Loss Prevention (DLP)**</span></span>
      - <span data-ttu-id="22abf-122">**Azure Information Protection (plan1**)</span><span class="sxs-lookup"><span data-stu-id="22abf-122">**Azure Information Protection (Plan1**)</span></span>

          <span data-ttu-id="22abf-123">Weitere Informationen finden Sie unter [Einrichten von erweiterten Sicherheitsrichtlinien](set-up-advanced-security.md).</span><span class="sxs-lookup"><span data-stu-id="22abf-123">To get started see, [set up advanced security policies](set-up-advanced-security.md).</span></span>

        <span data-ttu-id="22abf-124">Weitere Informationen finden Sie unter [Top 10 Ways to Secure your Microsoft 365 Business](https://docs.microsoft.com/office365/admin/security-and-compliance/secure-your-business-data) for a Roadmap of Best Security Practices.</span><span class="sxs-lookup"><span data-stu-id="22abf-124">See also [top 10 ways to secure your Microsoft 365 Business](https://docs.microsoft.com/office365/admin/security-and-compliance/secure-your-business-data) for a roadmap of best security practices.</span></span>

## <a name="step-3-set-up-and-manage-windows-10-devices"></a><span data-ttu-id="22abf-125">Schritt 3: Einrichten und Verwalten von Windows 10-Geräten</span><span class="sxs-lookup"><span data-stu-id="22abf-125">Step 3: Set up and manage Windows 10 devices</span></span>

   <span data-ttu-id="22abf-126">Wenn Sie einem Windows 10-Gerät zu Azure AD beitreten, werden die in [Schritt 2](#step-2-set-up-security-policies-and-configure-devices) eingerichteten Richtlinien darauf angewendet.</span><span class="sxs-lookup"><span data-stu-id="22abf-126">When you join a Windows 10 device to Azure AD, the policies you set up in [Step 2](#step-2-set-up-security-policies-and-configure-devices) get applied to it.</span></span>

   - <span data-ttu-id="22abf-127">Windows 10 pro ist eine [Voraussetzung](pre-requisites-for-data-protection.md) für Microsoft 365 Business, aber wenn Sie Windows 7 pro, Windows 8 pro oder Windows 8,1 pro haben, berechtigt Sie Ihr Abonnement zu einem [Upgrade auf Windows 10 pro](https://docs.microsoft.com/microsoft-365/business/upgrade-to-windows-pro-creators-update).</span><span class="sxs-lookup"><span data-stu-id="22abf-127">Windows 10 Pro is a [pre-requisite](pre-requisites-for-data-protection.md) for Microsoft 365 Business, but if you have Windows 7 Pro, Windows 8 Pro, or Windows 8.1 Pro, your subscription entitles you to an [upgrade to  Windows 10 Pro](https://docs.microsoft.com/microsoft-365/business/upgrade-to-windows-pro-creators-update).</span></span>
    - <span data-ttu-id="22abf-128">Verwenden Sie den [Setup-Assistenten](set-up.md#set-up-security-policies-and-device-configurations) , um Richtlinien für Windows 10-Geräte zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="22abf-128">Use the [setup wizard](set-up.md#set-up-security-policies-and-device-configurations) to configure policies for Windows 10 devices.</span></span>

## <a name="stes-4-install-office-365-business"></a><span data-ttu-id="22abf-129">Stes 4: Installieren von Office 365 Business</span><span class="sxs-lookup"><span data-stu-id="22abf-129">Stes 4: Install Office 365 Business</span></span>
- <span data-ttu-id="22abf-130">Sie können Office auf den Windows-Geräten mithilfe des Setup- [Assistenten](set-up.md#deploy-office-365-client-apps)automatisch installieren.</span><span class="sxs-lookup"><span data-stu-id="22abf-130">You can automatically install Office in the Windows devices by using the [setup wizard](set-up.md#deploy-office-365-client-apps).</span></span>
- <span data-ttu-id="22abf-131">[Installieren Sie Office](auto-install-or-uninstall-office.md) automatisch über das Admin Center.</span><span class="sxs-lookup"><span data-stu-id="22abf-131">Automatically [install Office](auto-install-or-uninstall-office.md) from the admin center.</span></span>
- <span data-ttu-id="22abf-132">Benutzer können [Office-Apps](https://docs.microsoft.com/office365/admin/setup/install-applications) für Windows und Geräte installieren.</span><span class="sxs-lookup"><span data-stu-id="22abf-132">Let users [install Office apps](https://docs.microsoft.com/office365/admin/setup/install-applications) for Windows and devices.</span></span>
     
## <a name="advanced"></a><span data-ttu-id="22abf-133">Fortgeschritten</span><span class="sxs-lookup"><span data-stu-id="22abf-133">Advanced</span></span>
- <span data-ttu-id="22abf-134">**Verwenden von Autopilot zum Einrichten neuer Geräte**</span><span class="sxs-lookup"><span data-stu-id="22abf-134">**Use Autopilot to set up new devices**</span></span>
            
     <span data-ttu-id="22abf-135">Sie können [Windows Autopilot](add-autopilot-devices-and-profile.md) verwenden, um **neue** Windows 10-Geräte für einen Benutzer automatisch vorkonfigurieren, aber es ist möglicherweise einfacher, einen [Partner](https://www.microsoft.com/solution-providers/search) zu erhalten, der dies für Sie tun kann.</span><span class="sxs-lookup"><span data-stu-id="22abf-135">You can use [Windows Autopilot](add-autopilot-devices-and-profile.md) to automatically pre-configure **new** Windows 10 devices for a user, but it might be easier to get a [partner](https://www.microsoft.com/solution-providers/search) who can do this for you.</span></span> <span data-ttu-id="22abf-136">Sie können auch zu [Microsoft Store](https://go.microsoft.com/fwlink/?linkid=874598) wechseln und einen Experten für die Cloud-Technologie bitten, neue Geräte einzurichten, die Sie für Sie erwerben.</span><span class="sxs-lookup"><span data-stu-id="22abf-136">You can also go to [Microsoft Store](https://go.microsoft.com/fwlink/?linkid=874598) and ask a cloud technology expert set up new devices you purchase for you.</span></span>

- <span data-ttu-id="22abf-137">**Zugriff auf lokale Ressourcen**</span><span class="sxs-lookup"><span data-stu-id="22abf-137">**Access on-premises resources**</span></span>

     - <span data-ttu-id="22abf-138">Wenn Ihre Organisation Windows Server Active Directory lokal verwendet, können Sie Microsoft 365 Business einrichten, um Ihre Windows 10-Geräte zu schützen, ohne dabei den Zugriff auf lokale Ressourcen zu gewährleisten, die lokal authentifiziert werden müssen.</span><span class="sxs-lookup"><span data-stu-id="22abf-138">If your organization uses Windows Server Active Directory on-premises, you can set up Microsoft 365 Business to protect your Windows 10 devices, while still maintaining access to on-premises resources that require local authentication.</span></span> <span data-ttu-id="22abf-139">Führen Sie die Schritte unter [enable Domain-Joined Windows 10 Devices aus, die von Microsoft 365 Business verwaltet werden](manage-windows-devices.md) , um diese einzurichten.</span><span class="sxs-lookup"><span data-stu-id="22abf-139">Follow the steps in [Enable domain-joined Windows 10 devices to be managed by Microsoft 365 Business](manage-windows-devices.md) to set this up.</span></span> <span data-ttu-id="22abf-140">Dies ist die bevorzugte Methode, und die Geräte in diesem Zustand werden als hybride Azure AD-verbundene Geräte bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="22abf-140">This is the preferred method and devices in this state are called Hybrid Azure AD joined devices.</span></span>

    - <span data-ttu-id="22abf-141">Wenn Ihr Unternehmen über ein lokales Active Directory verfügt, das einige lokale Ressourcen (wie Dateifreigaben und Drucker) enthält, können Sie Ihren Azure AD-verbundenen Geräten Zugriff auf diese Ressourcen gewähren, indem Sie die folgenden Schritte ausführen: [Zugriff auf lokale Ressourcen über eine Azure AD-verbundenes Gerät in Microsoft 365 Business](access-resources.md).</span><span class="sxs-lookup"><span data-stu-id="22abf-141">If your business has a local Active Directory that contains some on-premises resources (such as file shares and printers) , you can give your Azure AD-joined devices access to these resources by following the steps here: [Access on-premises resources from an Azure AD-joined device in Microsoft 365 Business](access-resources.md).</span></span>

  