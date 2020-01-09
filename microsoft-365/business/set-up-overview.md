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
ms.openlocfilehash: cab999493bf86ed0adf32521eaf6b3943f107f79
ms.sourcegitcommit: cf7b0fd80ecfb7a216111a801269c5322794795e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/09/2020
ms.locfileid: "40995248"
---
# <a name="overview-of-setup"></a>Übersicht über die Einrichtung

Sehen Sie sich ein kurzes Video über Microsoft 365 Business Setup an.<br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4jZwg] 

Wenn Sie dieses Video hilfreich fanden, schauen Sie sich bitte die [komplette Schulungsserie für kleine Unternehmen und jene, die neu bei Microsoft 365 sind](https://support.office.com/article/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816), an.

Die meisten Setupschritte können im Setup-Assistenten ausgeführt werden, aber auch die anderen Optionen werden aufgelistet.

## <a name="step-1-add-your-domain-and-users"></a>Schritt 1: Hinzufügen Ihrer Domäne und Benutzer

   - **[Hinzufügen Ihrer Domäne](set-up.md#add-your-domain-to-personalize-sign-in)** (wenn Sie Ihre Domäne während der [Registrierung](sign-up.md)erworben haben, ist dieser Schritt bereits abgeschlossen.)

    - **Benutzer hinzufügen**. Sie können auf drei Arten Benutzer hinzufügen:
        - Im [Assistenten](set-up.md#add-users-in-the-wizard).
        - Verwenden Sie die Verzeichnissynchronisierung, um [Benutzer mithilfe Azure AD Connect hinzuzufügen](https://docs.microsoft.com/office365/enterprise/set-up-directory-synchronization) , wenn Sie über ein lokales Active Directory verfügen.
        - Sie können Benutzer auch später im Admin Center [Hinzufügen](add-users-m365b.md) .
## <a name="step-2-set-up-security-policies-and-configure-devices"></a>Schritt 2: Einrichten von Sicherheitsrichtlinien und Konfigurieren von Geräten 

  - Verwenden Sie den [Setup-Assistenten](set-up.md#protect-your-organization) , um Geräterichtlinien zu konfigurieren. 
  - Sie können auch später im [Admin Center](view-policies-and-devices.md) und im [InTune-Portal](https://docs.microsoft.com/intune/tutorial-walkthrough-intune-portal)weitere hinzufügen oder bearbeiten.
  - Außerdem werden mit dem Setup-Assistenten grundlegende Bedrohungen und Verhinderung von Datenverlust Einstellungen eingerichtet.
  
  Zusätzlich zu den Sicherheitseinstellungen im Setup-Assistenten können Sie die Sicherheit durch Hinzufügen der folgenden Einstellungen verbessern:

- **E-Mail-Schutz vor Schadsoftware**
- **ATP-Anti-Phishing**
- **Exchange Online-Archivierung**
- **Azure Information Protection (plan1**)

Informationen zu den ersten Schritten finden Sie unter [Erweitern des Bedrohungsschutzes](increase-threat-protection.md) und [Einrichten von Kompatibilitätsfeatures](set-up-compliance.md).

Eine Übersicht über die besten Sicherheitsmethoden finden Sie auch unter [Top 10 Ways to Secure your Microsoft 365 Business](https://docs.microsoft.com/office365/admin/security-and-compliance/secure-your-business-data) .

## <a name="step-3-set-up-and-manage-windows-10-devices"></a>Schritt 3: Einrichten und Verwalten von Windows 10-Geräten

Nachdem Sie den Assistenten für die Einrichtung ausgeführt haben, sollten Sie alle Windwos 10-Computer in Ihrer Organisation proctect.
  
- Windows 10 pro ist eine [Voraussetzung](pre-requisites-for-data-protection.md) für Microsoft 365 Business, aber wenn Sie Windows 7 pro, Windows 8 pro oder Windows 8.1 pro haben, berechtigen Sie Ihr Abonnement zu einem [Upgrade auf Windows 10 pro](https://docs.microsoft.com/microsoft-365/business/upgrade-to-windows-pro-creators-update).
- Führen Sie die Schritte unter [Secure Windows 10 PCs](secure-win-10-pcs.md) aus, um Richtlinien für Windows 10-Geräte einzurichten.

Wenn Sie ein Windows 10-Gerät mit Azure AD verknüpfen, werden die Richtlinien, die Sie für Windows 10-Computer festgelegt haben, auf diese angewendet. Weitere Informationen finden Sie unter [Einrichten von Windows-Geräten für Microsoft 365 Business-Benutzer](set-up-windows-devices.md).

## <a name="step-4-install-office-365-business"></a>Schritt 4: Installieren von Office 365 Business
- Sie können Office auf den Windows-Geräten automatisch mithilfe des [Setup-Assistenten](set-up.md#deploy-office-365-client-apps)installieren.
- Benutzer können [Office-Apps](https://docs.microsoft.com/office365/admin/setup/install-applications) für Windows und Geräte installieren.
     
## <a name="advanced"></a>Fortgeschritten
- **Verwenden von Autopilot zum Einrichten neuer Geräte**
            
     Sie können [Windows Autopilot](add-autopilot-devices-and-profile.md) verwenden, um **neue** Windows 10-Geräte für einen Benutzer automatisch vorkonfigurieren, aber es ist möglicherweise einfacher, einen [Partner](https://www.microsoft.com/solution-providers/search) zu erhalten, der dies für Sie tun kann. Sie können auch zu [Microsoft Store](https://go.microsoft.com/fwlink/?linkid=874598)wechseln und einen Experten für die Cloud-Technologie bitten, neue Geräte einzurichten, die Sie kaufen.

- **Zugriff auf lokale Ressourcen**

     - Wenn Ihre Organisation Windows Server Active Directory lokal verwendet, können Sie Microsoft 365 Business zum Schutz Ihrer Windows 10-Geräte einrichten und gleichzeitig den Zugriff auf lokale Ressourcen aufrecht erhalten, die lokale Authentifizierung erfordern. Führen Sie die Schritte unter [enable Domain-Joined Windows 10 Devices to manage by Microsoft 365 Business](manage-windows-devices.md) aus, um diesen einzurichten. Dies ist die bevorzugte Methode, und Geräte in diesem Zustand werden als Hybrid Azure AD verbundene Geräte bezeichnet.

    - Wenn Ihr Unternehmen über ein lokales Active Directory verfügt, das einige lokale Ressourcen enthält (beispielsweise Dateifreigaben und Drucker), können Sie Ihren Azure AD-verbundenen Geräten Zugriff auf diese Ressourcen gewähren, indem Sie die folgenden Schritte ausführen: [zugreifen auf lokale Ressourcen von einem Azure AD verbundenen Gerät in Microsoft 365 Business](access-resources.md).

## <a name="see-also"></a>Siehe auch

[Microsoft 365 Business-Schulungsvideos](https://support.office.com/article/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816)
