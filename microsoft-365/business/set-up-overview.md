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
search.appverid:
- BCS160
- MET150
ms.assetid: 6e7a2dfd-8ec4-4eb7-8390-3ee103e5fece
description: Übersicht über die Schritte zum Einrichten von Microsoft 365 Business.
ms.openlocfilehash: ae7ed0aab36a6e759e0f0c1fbc3d3183273a284e
ms.sourcegitcommit: 66bb5af851947078872a4d31d3246e69f7dd42bb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/15/2019
ms.locfileid: "34074405"
---
# <a name="overview-of-setup"></a><span data-ttu-id="c26ac-103">Übersicht über das Setup</span><span class="sxs-lookup"><span data-stu-id="c26ac-103">Overview of setup</span></span>

<span data-ttu-id="c26ac-104">Die meisten der Schritte zum einrichten können im Setup-Assistenten ausgeführt werden, aber die anderen Optionen werden ebenfalls aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="c26ac-104">Most of the set up steps can be done in the setup wizard, but the other options are also listed.</span></span>


## <a name="step-1-add-your-domain-and-users"></a><span data-ttu-id="c26ac-105">Schritt 1: Hinzufügen Ihrer Domäne und Benutzer</span><span class="sxs-lookup"><span data-stu-id="c26ac-105">Step 1: Add your domain and users</span></span>

   - <span data-ttu-id="c26ac-106">**[Hinzufügen Ihrer Domäne](set-up.md#add-your-domain-to-personalize-sign-in)** (wenn Sie Ihre Domäne während der [Registrierung](sign-up.md)erworben haben, ist dieser Schritt bereits abgeschlossen.)</span><span class="sxs-lookup"><span data-stu-id="c26ac-106">**[Add your domain](set-up.md#add-your-domain-to-personalize-sign-in)** (if you bought your domain during [sign up](sign-up.md), this step is already done.)</span></span>

    - <span data-ttu-id="c26ac-107">**Benutzer hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="c26ac-107">**Add users**.</span></span> <span data-ttu-id="c26ac-108">Sie können auf eine der folgenden drei Arten vorgehen:</span><span class="sxs-lookup"><span data-stu-id="c26ac-108">You can do this in any of the three ways:</span></span>
        - <span data-ttu-id="c26ac-109">Im [Assistenten](set-up.md#add-users-in-the-wizard).</span><span class="sxs-lookup"><span data-stu-id="c26ac-109">In the [wizard](set-up.md#add-users-in-the-wizard).</span></span>
        - <span data-ttu-id="c26ac-110">Verwenden Sie die Verzeichnissynchronisierung, um [Benutzer mithilfe Azure AD Connect hinzuzufügen](https://docs.microsoft.com/office365/enterprise/set-up-directory-synchronization) , wenn Sie über ein lokales Active Directory verfügen.</span><span class="sxs-lookup"><span data-stu-id="c26ac-110">Use directory synchronization to [add users by using Azure AD Connect](https://docs.microsoft.com/office365/enterprise/set-up-directory-synchronization) if you have an on-premises Active directory.</span></span>
        - <span data-ttu-id="c26ac-111">Sie können Benutzer auch später im Admin Center [Hinzufügen](add-users-m365b.md) .</span><span class="sxs-lookup"><span data-stu-id="c26ac-111">You can also [add users later](add-users-m365b.md) in the admin center.</span></span>
## <a name="step-2-set-up-security-policies-and-configure-devices"></a><span data-ttu-id="c26ac-112">Schritt 2: Einrichten von Sicherheitsrichtlinien und Konfigurieren von Geräten</span><span class="sxs-lookup"><span data-stu-id="c26ac-112">Step 2: Set up security policies and configure devices</span></span> 

  - <span data-ttu-id="c26ac-113">Verwenden Sie den [Setup-Assistenten](set-up.md#set-up-security-policies-and-device-configurations) , um Geräte-und Sicherheitsrichtlinien zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="c26ac-113">Use the [Setup wizard](set-up.md#set-up-security-policies-and-device-configurations) to configure device and security policies.</span></span> 
  - <span data-ttu-id="c26ac-114">Sie können auch später im [Admin Center](view-policies-and-devices.md) und im [InTune-Portal](https://docs.microsoft.com/intune/tutorial-walkthrough-intune-portal)weitere hinzufügen oder bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="c26ac-114">You can also add more or edit them later in the [admin center](view-policies-and-devices.md) and in the [Intune portal](https://docs.microsoft.com/intune/tutorial-walkthrough-intune-portal).</span></span>
  - <span data-ttu-id="c26ac-115">Zusätzlich zu den Sicherheitseinstellungen im Setup-Assistenten können Sie die Sicherheit durch Hinzufügen der folgenden Einstellungen verbessern:</span><span class="sxs-lookup"><span data-stu-id="c26ac-115">In addition to the security settings in the setup wizard, you can increase your security by adding the following settings:</span></span>

      - <span data-ttu-id="c26ac-116">**E-Mail-Schutz vor Schadsoftware**</span><span class="sxs-lookup"><span data-stu-id="c26ac-116">**Email malware protection**</span></span>
      - <span data-ttu-id="c26ac-117">**Sichere Links für Advanced Threat Protection (ATP)**</span><span class="sxs-lookup"><span data-stu-id="c26ac-117">**Advanced Threat Protection (ATP) Safe links**</span></span>
      - <span data-ttu-id="c26ac-118">**Sichere Anlagen in ATP**</span><span class="sxs-lookup"><span data-stu-id="c26ac-118">**ATP Safe Attachments**</span></span>
      - <span data-ttu-id="c26ac-119">**ATP-Anti-Phishing**</span><span class="sxs-lookup"><span data-stu-id="c26ac-119">**ATP anti-phishing**</span></span>
      - <span data-ttu-id="c26ac-120">**Exchange Online-Archivierung**</span><span class="sxs-lookup"><span data-stu-id="c26ac-120">**Exchange Online Archiving**</span></span>
      - <span data-ttu-id="c26ac-121">**Verhinderung von Datenverlust**</span><span class="sxs-lookup"><span data-stu-id="c26ac-121">**Data Loss Prevention (DLP)**</span></span>
      - <span data-ttu-id="c26ac-122">**Azure Information Protection (plan1**)</span><span class="sxs-lookup"><span data-stu-id="c26ac-122">**Azure Information Protection (Plan1**)</span></span>

          <span data-ttu-id="c26ac-123">Für erste Schritte siehe [Einrichten von erweiterten Sicherheitsrichtlinien](set-up-advanced-security.md).</span><span class="sxs-lookup"><span data-stu-id="c26ac-123">To get started see, [set up advanced security policies](set-up-advanced-security.md).</span></span>

        <span data-ttu-id="c26ac-124">Eine Übersicht über die besten Sicherheitsmethoden finden Sie auch unter [Top 10 Ways to Secure your Microsoft 365 Business](https://docs.microsoft.com/office365/admin/security-and-compliance/secure-your-business-data) .</span><span class="sxs-lookup"><span data-stu-id="c26ac-124">See also [top 10 ways to secure your Microsoft 365 Business](https://docs.microsoft.com/office365/admin/security-and-compliance/secure-your-business-data) for a roadmap of best security practices.</span></span>

## <a name="step-3-set-up-and-manage-windows-10-devices"></a><span data-ttu-id="c26ac-125">Schritt 3: Einrichten und Verwalten von Windows 10-Geräten</span><span class="sxs-lookup"><span data-stu-id="c26ac-125">Step 3: Set up and manage Windows 10 devices</span></span>

   <span data-ttu-id="c26ac-126">Wenn Sie ein Windows 10-Gerät mit Azure AD verknüpfen, werden die Richtlinien, die Sie in [Schritt 2](#step-2-set-up-security-policies-and-configure-devices) eingerichtet haben, darauf angewendet.</span><span class="sxs-lookup"><span data-stu-id="c26ac-126">When you join a Windows 10 device to Azure AD, the policies you set up in [Step 2](#step-2-set-up-security-policies-and-configure-devices) get applied to it.</span></span>

   - <span data-ttu-id="c26ac-127">Windows 10 pro ist eine [Voraussetzung](pre-requisites-for-data-protection.md) für Microsoft 365 Business, aber wenn Sie Windows 7 pro, Windows 8 pro oder Windows 8.1 pro haben, berechtigen Sie Ihr Abonnement zu einem [Upgrade auf Windows 10 pro](https://docs.microsoft.com/microsoft-365/business/upgrade-to-windows-pro-creators-update).</span><span class="sxs-lookup"><span data-stu-id="c26ac-127">Windows 10 Pro is a [pre-requisite](pre-requisites-for-data-protection.md) for Microsoft 365 Business, but if you have Windows 7 Pro, Windows 8 Pro, or Windows 8.1 Pro, your subscription entitles you to an [upgrade to  Windows 10 Pro](https://docs.microsoft.com/microsoft-365/business/upgrade-to-windows-pro-creators-update).</span></span>
    - <span data-ttu-id="c26ac-128">Verwenden Sie den [Setup-Assistenten](set-up.md#set-up-security-policies-and-device-configurations) , um Richtlinien für Windows 10-Geräte zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="c26ac-128">Use the [setup wizard](set-up.md#set-up-security-policies-and-device-configurations) to configure policies for Windows 10 devices.</span></span>

## <a name="stes-4-install-office-365-business"></a><span data-ttu-id="c26ac-129">Stes 4: Installieren von Office 365 Business</span><span class="sxs-lookup"><span data-stu-id="c26ac-129">Stes 4: Install Office 365 Business</span></span>
- <span data-ttu-id="c26ac-130">Sie können Office auf den Windows-Geräten automatisch mithilfe des [Setup-Assistenten](set-up.md#deploy-office-365-client-apps)installieren.</span><span class="sxs-lookup"><span data-stu-id="c26ac-130">You can automatically install Office in the Windows devices by using the [setup wizard](set-up.md#deploy-office-365-client-apps).</span></span>
- <span data-ttu-id="c26ac-131">[Installieren Sie Office](auto-install-or-uninstall-office.md) automatisch aus dem Admin Center.</span><span class="sxs-lookup"><span data-stu-id="c26ac-131">Automatically [install Office](auto-install-or-uninstall-office.md) from the admin center.</span></span>
- <span data-ttu-id="c26ac-132">Benutzer können [Office-Apps](https://docs.microsoft.com/office365/admin/setup/install-applications) für Windows und Geräte installieren.</span><span class="sxs-lookup"><span data-stu-id="c26ac-132">Let users [install Office apps](https://docs.microsoft.com/office365/admin/setup/install-applications) for Windows and devices.</span></span>
     
## <a name="advanced"></a><span data-ttu-id="c26ac-133">Fortgeschritten</span><span class="sxs-lookup"><span data-stu-id="c26ac-133">Advanced</span></span>
- <span data-ttu-id="c26ac-134">**Verwenden von Autopilot zum Einrichten neuer Geräte**</span><span class="sxs-lookup"><span data-stu-id="c26ac-134">**Use Autopilot to set up new devices**</span></span>
            
     <span data-ttu-id="c26ac-135">Sie können [Windows Autopilot](add-autopilot-devices-and-profile.md) verwenden, um **neue** Windows 10-Geräte für einen Benutzer automatisch vorkonfigurieren, aber es ist möglicherweise einfacher, einen [Partner](https://www.microsoft.com/solution-providers/search) zu erhalten, der dies für Sie tun kann.</span><span class="sxs-lookup"><span data-stu-id="c26ac-135">You can use [Windows Autopilot](add-autopilot-devices-and-profile.md) to automatically pre-configure **new** Windows 10 devices for a user, but it might be easier to get a [partner](https://www.microsoft.com/solution-providers/search) who can do this for you.</span></span> <span data-ttu-id="c26ac-136">Sie können auch zu [Microsoft Store](https://go.microsoft.com/fwlink/?linkid=874598) wechseln und einen Cloud Technology Expert bitten, neue Geräte einzurichten, die Sie für Sie kaufen.</span><span class="sxs-lookup"><span data-stu-id="c26ac-136">You can also go to [Microsoft Store](https://go.microsoft.com/fwlink/?linkid=874598) and ask a cloud technology expert set up new devices you purchase for you.</span></span>

- <span data-ttu-id="c26ac-137">**Zugreifen auf lokale Ressourcen**</span><span class="sxs-lookup"><span data-stu-id="c26ac-137">**Access on-premises resources**</span></span>

     - <span data-ttu-id="c26ac-138">Wenn Ihre Organisation Windows Server Active Directory lokal verwendet, können Sie Microsoft 365 Business zum Schutz Ihrer Windows 10-Geräte einrichten und gleichzeitig den Zugriff auf lokale Ressourcen aufrecht erhalten, die lokale Authentifizierung erfordern.</span><span class="sxs-lookup"><span data-stu-id="c26ac-138">If your organization uses Windows Server Active Directory on-premises, you can set up Microsoft 365 Business to protect your Windows 10 devices, while still maintaining access to on-premises resources that require local authentication.</span></span> <span data-ttu-id="c26ac-139">Führen Sie die Schritte unter [enable Domain-Joined Windows 10 Devices to manage by Microsoft 365 Business](manage-windows-devices.md) aus, um diesen einzurichten.</span><span class="sxs-lookup"><span data-stu-id="c26ac-139">Follow the steps in [Enable domain-joined Windows 10 devices to be managed by Microsoft 365 Business](manage-windows-devices.md) to set this up.</span></span> <span data-ttu-id="c26ac-140">Dies ist die bevorzugte Methode, und Geräte in diesem Zustand werden als Hybrid Azure AD verbundene Geräte bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="c26ac-140">This is the preferred method and devices in this state are called Hybrid Azure AD joined devices.</span></span>

    - <span data-ttu-id="c26ac-141">Wenn Ihr Unternehmen über ein lokales Active Directory verfügt, das einige lokale Ressourcen enthält (beispielsweise Dateifreigaben und Drucker), können Sie Ihren Azure AD-verbundenen Geräten Zugriff auf diese Ressourcen gewähren, indem Sie die folgenden Schritte ausführen: [zugreifen auf lokale Ressourcen von einem Azure AD verbundenes Gerät in Microsoft 365 Business](access-resources.md).</span><span class="sxs-lookup"><span data-stu-id="c26ac-141">If your business has a local Active Directory that contains some on-premises resources (such as file shares and printers) , you can give your Azure AD-joined devices access to these resources by following the steps here: [Access on-premises resources from an Azure AD-joined device in Microsoft 365 Business](access-resources.md).</span></span>

  