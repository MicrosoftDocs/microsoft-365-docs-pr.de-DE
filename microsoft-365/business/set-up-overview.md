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
description: Übersicht über die Schritte zum Einrichten von Microsoft 365 Business.
ms.openlocfilehash: 50f172c235aa06aa78fec60fc119ac7f568df308
ms.sourcegitcommit: bd52f7b662887f552f90c46f69d6a2a42fb66914
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2019
ms.locfileid: "37575586"
---
# <a name="overview-of-setup"></a>Übersicht über die Einrichtung

Die meisten der Schritte zum einrichten können im Setup-Assistenten ausgeführt werden, aber die anderen Optionen werden ebenfalls aufgeführt.


## <a name="step-1-add-your-domain-and-users"></a>Schritt 1: Hinzufügen Ihrer Domäne und Benutzer

   - **[Hinzufügen Ihrer Domäne](set-up.md#add-your-domain-to-personalize-sign-in)** (wenn Sie Ihre Domäne während der [Registrierung](sign-up.md)erworben haben, ist dieser Schritt bereits abgeschlossen.)

    - **Benutzer hinzufügen**. Sie können auf eine der folgenden drei Arten vorgehen:
        - Im [Assistenten](set-up.md#add-users-in-the-wizard).
        - Verwenden Sie die Verzeichnissynchronisierung, um [Benutzer mithilfe Azure AD Connect hinzuzufügen](https://docs.microsoft.com/office365/enterprise/set-up-directory-synchronization) , wenn Sie über ein lokales Active Directory verfügen.
        - Sie können Benutzer auch später im Admin Center [Hinzufügen](add-users-m365b.md) .
## <a name="step-2-set-up-security-policies-and-configure-devices"></a>Schritt 2: Einrichten von Sicherheitsrichtlinien und Konfigurieren von Geräten 

  - Verwenden Sie den [Setup-Assistenten](set-up.md#protect-data-and-devices) , um Geräte-und Sicherheitsrichtlinien zu konfigurieren. 
  - Sie können auch später im [Admin Center](view-policies-and-devices.md) und im [InTune-Portal](https://docs.microsoft.com/intune/tutorial-walkthrough-intune-portal)weitere hinzufügen oder bearbeiten.
  - Zusätzlich zu den Sicherheitseinstellungen im Setup-Assistenten können Sie die Sicherheit durch Hinzufügen der folgenden Einstellungen verbessern:

      - **E-Mail-Schutz vor Schadsoftware**
      - **Sichere Links für Advanced Threat Protection (ATP)**
      - **Sichere Anlagen in ATP**
      - **ATP-Anti-Phishing**
      - **Exchange Online-Archivierung**
      - **Verhinderung von Datenverlust**
      - **Azure Information Protection (plan1**)

          Für erste Schritte siehe [Einrichten von erweiterten Sicherheitsrichtlinien](set-up-advanced-security.md).

        Eine Übersicht über die besten Sicherheitsmethoden finden Sie auch unter [Top 10 Ways to Secure your Microsoft 365 Business](https://docs.microsoft.com/office365/admin/security-and-compliance/secure-your-business-data) .

## <a name="step-3-set-up-and-manage-windows-10-devices"></a>Schritt 3: Einrichten und Verwalten von Windows 10-Geräten

   Wenn Sie ein Windows 10-Gerät mit Azure AD verknüpfen, werden die Richtlinien, die Sie in [Schritt 2](#step-2-set-up-security-policies-and-configure-devices) eingerichtet haben, darauf angewendet.

   - Windows 10 pro ist eine [Voraussetzung](pre-requisites-for-data-protection.md) für Microsoft 365 Business, aber wenn Sie Windows 7 pro, Windows 8 pro oder Windows 8.1 pro haben, berechtigen Sie Ihr Abonnement zu einem [Upgrade auf Windows 10 pro](https://docs.microsoft.com/microsoft-365/business/upgrade-to-windows-pro-creators-update).
    - Verwenden Sie den [Setup-Assistenten](set-up.md#protect-data-and-devices) , um Richtlinien für Windows 10-Geräte zu konfigurieren.

## <a name="stes-4-install-office-365-business"></a>Stes 4: Installieren von Office 365 Business
- Sie können Office auf den Windows-Geräten automatisch mithilfe des [Setup-Assistenten](set-up.md#deploy-office-365-client-apps)installieren.
- [Installieren Sie Office](auto-install-or-uninstall-office.md) automatisch aus dem Admin Center.
- Benutzer können [Office-Apps](https://docs.microsoft.com/office365/admin/setup/install-applications) für Windows und Geräte installieren.
     
## <a name="advanced"></a>Fortgeschritten
- **Verwenden von Autopilot zum Einrichten neuer Geräte**
            
     Sie können [Windows Autopilot](add-autopilot-devices-and-profile.md) verwenden, um **neue** Windows 10-Geräte für einen Benutzer automatisch vorkonfigurieren, aber es ist möglicherweise einfacher, einen [Partner](https://www.microsoft.com/solution-providers/search) zu erhalten, der dies für Sie tun kann. Sie können auch zu [Microsoft Store](https://go.microsoft.com/fwlink/?linkid=874598) wechseln und einen Cloud Technology Expert bitten, neue Geräte einzurichten, die Sie für Sie kaufen.

- **Zugriff auf lokale Ressourcen**

     - Wenn Ihre Organisation Windows Server Active Directory lokal verwendet, können Sie Microsoft 365 Business zum Schutz Ihrer Windows 10-Geräte einrichten und gleichzeitig den Zugriff auf lokale Ressourcen aufrecht erhalten, die lokale Authentifizierung erfordern. Führen Sie die Schritte unter [enable Domain-Joined Windows 10 Devices to manage by Microsoft 365 Business](manage-windows-devices.md) aus, um diesen einzurichten. Dies ist die bevorzugte Methode, und Geräte in diesem Zustand werden als Hybrid Azure AD verbundene Geräte bezeichnet.

    - Wenn Ihr Unternehmen über ein lokales Active Directory verfügt, das einige lokale Ressourcen enthält (beispielsweise Dateifreigaben und Drucker), können Sie Ihren Azure AD-verbundenen Geräten Zugriff auf diese Ressourcen gewähren, indem Sie die folgenden Schritte ausführen: [zugreifen auf lokale Ressourcen von einem Azure AD verbundenes Gerät in Microsoft 365 Business](access-resources.md).

  