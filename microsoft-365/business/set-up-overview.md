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
# <a name="overview-of-setup"></a>Übersicht über die Einrichtung

Die meisten der einrichten-Schritte können im Setup-Assistenten ausgeführt werden, die anderen Optionen werden ebenfalls aufgeführt.


## <a name="step-1-add-your-domain-and-users"></a>Schritt 1: Hinzufügen der Domäne und der Benutzer

   - **[Hinzufügen Ihrer Domäne](set-up.md#add-your-domain-to-personalize-sign-in)** (wenn Sie Ihre Domäne während der [Registrierung](sign-up.md)erworben haben, ist dieser Schritt bereits erfolgt.)

    - **Benutzer hinzufügen**. Sie haben die folgenden Möglichkeiten:
        - Im [Assistenten](set-up.md#add-users-in-the-wizard).
        - Verwenden Sie die Verzeichnissynchronisierung, um [Benutzer mithilfe von Azure AD Connect hinzuzufügen](https://docs.microsoft.com/office365/enterprise/set-up-directory-synchronization) , wenn Sie über ein lokales Active Directory verfügen.
        - Sie können auch später im Admin Center [Benutzer hinzufügen](add-users-m365b.md) .
## <a name="step-2-set-up-security-policies-and-configure-devices"></a>Schritt 2: Einrichten von Sicherheitsrichtlinien und Konfigurieren von Geräten 

  - Verwenden Sie den [Setup-Assistenten](set-up.md#set-up-security-policies-and-device-configurations) , um Geräte-und Sicherheitsrichtlinien zu konfigurieren. 
  - Sie können Sie auch später im [Admin Center](view-policies-and-devices.md) und im [InTune-Portal](https://docs.microsoft.com/intune/tutorial-walkthrough-intune-portal)hinzufügen oder bearbeiten.
  - Zusätzlich zu den Sicherheitseinstellungen im Setup-Assistenten können Sie die Sicherheit verbessern, indem Sie die folgenden Einstellungen hinzufügen:

      - **Schutz von e-Mail-Schadsoftware**
      - **Advanced Threat Protection (ATP) sichere Links**
      - **Sichere Anlagen in ATP**
      - **ATP-Phishing**
      - **Exchange Online-Archivierung**
      - **Verhinderung von Datenverlust**
      - **Azure Information Protection (plan1**)

          Weitere Informationen finden Sie unter [Einrichten von erweiterten Sicherheitsrichtlinien](set-up-advanced-security.md).

        Weitere Informationen finden Sie unter [Top 10 Ways to Secure your Microsoft 365 Business](https://docs.microsoft.com/office365/admin/security-and-compliance/secure-your-business-data) for a Roadmap of Best Security Practices.

## <a name="step-3-set-up-and-manage-windows-10-devices"></a>Schritt 3: Einrichten und Verwalten von Windows 10-Geräten

   Wenn Sie einem Windows 10-Gerät zu Azure AD beitreten, werden die in [Schritt 2](#step-2-set-up-security-policies-and-configure-devices) eingerichteten Richtlinien darauf angewendet.

   - Windows 10 pro ist eine [Voraussetzung](pre-requisites-for-data-protection.md) für Microsoft 365 Business, aber wenn Sie Windows 7 pro, Windows 8 pro oder Windows 8,1 pro haben, berechtigt Sie Ihr Abonnement zu einem [Upgrade auf Windows 10 pro](https://docs.microsoft.com/microsoft-365/business/upgrade-to-windows-pro-creators-update).
    - Verwenden Sie den [Setup-Assistenten](set-up.md#set-up-security-policies-and-device-configurations) , um Richtlinien für Windows 10-Geräte zu konfigurieren.

## <a name="stes-4-install-office-365-business"></a>Stes 4: Installieren von Office 365 Business
- Sie können Office auf den Windows-Geräten mithilfe des Setup- [Assistenten](set-up.md#deploy-office-365-client-apps)automatisch installieren.
- [Installieren Sie Office](auto-install-or-uninstall-office.md) automatisch über das Admin Center.
- Benutzer können [Office-Apps](https://docs.microsoft.com/office365/admin/setup/install-applications) für Windows und Geräte installieren.
     
## <a name="advanced"></a>Fortgeschritten
- **Verwenden von Autopilot zum Einrichten neuer Geräte**
            
     Sie können [Windows Autopilot](add-autopilot-devices-and-profile.md) verwenden, um **neue** Windows 10-Geräte für einen Benutzer automatisch vorkonfigurieren, aber es ist möglicherweise einfacher, einen [Partner](https://www.microsoft.com/solution-providers/search) zu erhalten, der dies für Sie tun kann. Sie können auch zu [Microsoft Store](https://go.microsoft.com/fwlink/?linkid=874598) wechseln und einen Experten für die Cloud-Technologie bitten, neue Geräte einzurichten, die Sie für Sie erwerben.

- **Zugriff auf lokale Ressourcen**

     - Wenn Ihre Organisation Windows Server Active Directory lokal verwendet, können Sie Microsoft 365 Business einrichten, um Ihre Windows 10-Geräte zu schützen, ohne dabei den Zugriff auf lokale Ressourcen zu gewährleisten, die lokal authentifiziert werden müssen. Führen Sie die Schritte unter [enable Domain-Joined Windows 10 Devices aus, die von Microsoft 365 Business verwaltet werden](manage-windows-devices.md) , um diese einzurichten. Dies ist die bevorzugte Methode, und die Geräte in diesem Zustand werden als hybride Azure AD-verbundene Geräte bezeichnet.

    - Wenn Ihr Unternehmen über ein lokales Active Directory verfügt, das einige lokale Ressourcen (wie Dateifreigaben und Drucker) enthält, können Sie Ihren Azure AD-verbundenen Geräten Zugriff auf diese Ressourcen gewähren, indem Sie die folgenden Schritte ausführen: [Zugriff auf lokale Ressourcen über eine Azure AD-verbundenes Gerät in Microsoft 365 Business](access-resources.md).

  