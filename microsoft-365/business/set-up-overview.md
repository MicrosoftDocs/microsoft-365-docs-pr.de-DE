---
title: Übersicht über die Einrichtung
f1.keywords:
- NOCSH
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
- seo-marvel-mar
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
ms.assetid: 6e7a2dfd-8ec4-4eb7-8390-3ee103e5fece
description: Erfahren Sie mehr über die Einrichtungsschritte für Microsoft 365 Business Premium, vom Abonnieren über das Hinzufügen einer Domäne und Benutzer bis zum Einrichten von Sicherheitsrichtlinien und vielem mehr.
ms.openlocfilehash: 9d92aefb3b5666bb7c2fd2e13c9a00f074f107a7
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50912488"
---
# <a name="overview-of-setup"></a>Übersicht über die Einrichtung

Sehen Sie sich ein kurzes Video zum Microsoft 365 Business Premium-Setup an.<br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4jZwg] 

Wenn Sie dieses Video hilfreich fanden, sehen Sie sich bitte die [komplette Schulungsserie für kleine Unternehmen und diejenigen, für die Microsoft 365 neu ist](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816) an.

Die meisten Setupschritte können im geführten Setup durchgeführt werden, aber die anderen Optionen werden auch aufgelistet.

## <a name="step-1-add-your-domain-and-users"></a>Schritt 1: Hinzufügen Ihrer Domäne und Ihrer Benutzer

   - **[Fügen Sie Ihre Domäne](set-up.md#add-your-domain-to-personalize-sign-in)** hinzu (wenn Sie Ihre Domäne während der Anmeldung erworben [haben,](sign-up.md)ist dieser Schritt bereits erledigt.)

   - **Hinzufügen von Benutzern**. Sie können Benutzer auf drei Arten hinzufügen:
        - Im [geführten Setup](set-up.md#add-users-in-the-wizard).
        - Verwenden Sie die [Verzeichnissynchronisierung, um Benutzer mithilfe von Azure AD Connect](../enterprise/set-up-directory-synchronization.md) hinzuzufügen, wenn Sie über ein lokales Active Directory verfügen.
        - Sie können benutzer [auch später im](../admin/add-users/add-users.md) Admin Center hinzufügen.
## <a name="step-2-set-up-security-policies-and-configure-devices"></a>Schritt 2: Einrichten von Sicherheitsrichtlinien und Konfigurieren von Geräten 

  - Verwenden Sie das [geführte Setup](set-up.md#protect-your-organization) zum Konfigurieren von Geräterichtlinien. 
  - Sie können sie auch später im [Admin Center](view-policies-and-devices.md) und im Intune-Portal hinzufügen oder [bearbeiten.](/intune/tutorial-walkthrough-intune-portal)
  - Der Setup-Assistent erstellt außerdem grundlegende Einstellungen zum Schutz vor Bedrohungen und zur Verhinderung von Datenverlust.
  
  Zusätzlich zu den Sicherheitseinstellungen im Setup-Assistenten können Sie Ihre Sicherheit erhöhen, indem Sie die folgenden Einstellungen hinzufügen:

- **Schutz vor Schadsoftware per E-Mail**
- **Antiphishing in Defender for Office 365**
- **Exchange Online-Archivierung**
- **Azure Information Protection (Plan1**)

Informationen zu den ersten Schritte finden Sie [unter Erhöhen des Bedrohungsschutzes](increase-threat-protection.md) und [Einrichten von Compliancefeatures.](set-up-compliance.md)

Weitere Informationen zu bewährten Sicherheitsmethoden finden Sie unter Top [10 ways to secure your Microsoft 365 Business Premium.](/office365/admin/security-and-compliance/secure-your-business-data)

## <a name="step-3-set-up-and-manage-windows-10-devices"></a>Schritt 3: Einrichten und Verwalten von Windows 10-Geräten

Nachdem Sie das geführte Setup abgeschlossen haben, sollten Sie alle Windows 10-Computer in Ihrer Organisation schützen.
  
- Windows 10 Pro [](pre-requisites-for-data-protection.md) ist eine Voraussetzung für Microsoft 365 Business Premium, aber wenn Sie über Windows 7 Pro, Windows 8 Pro oder Windows 8.1 Pro verfügen, berechtigt Ihr Abonnement Sie zu einem Upgrade auf [Windows 10 Pro.](./upgrade-to-windows-pro-creators-update.md)
- Führen Sie die Schritte unter [Sichere Windows 10-PCs aus,](secure-win-10-pcs.md) um Richtlinien für Windows 10-Geräte zu erstellen.

Wenn Sie ein Windows 10-Gerät mit Azure AD verbinden, werden die richtlinien, die Sie für Windows 10-Computer festgelegt haben, auf das Gerät angewendet. Weitere Informationen finden Sie unter [Einrichten von Windows-Geräten für Microsoft 365-Benutzer](set-up-windows-devices.md).

## <a name="step-4-install-microsoft-365-apps-for-business"></a>Schritt 4: Installieren von Microsoft 365 Apps for Business
- Sie können Office mithilfe des Setup-Assistenten automatisch auf den [Windows-Geräten installieren.](set-up.md#deploy-office-365-client-apps)
- Benutzer können [Office-Apps](/office365/admin/setup/install-applications) für Windows und Geräte installieren.
     
## <a name="advanced"></a>Fortgeschritten
- **Einrichten neuer Geräte mithilfe von Autopilot**
            
     Sie können [Windows Autopilot](add-autopilot-devices-and-profile.md) verwenden, um neue **Windows** 10-Geräte automatisch für einen [](https://www.microsoft.com/solution-providers/search) Benutzer vorzukonfiguriert, aber es ist möglicherweise einfacher, einen Partner zu erhalten, der dies für Sie tun kann. Sie können auch zum [Microsoft Store wechseln](https://go.microsoft.com/fwlink/?linkid=874598)und einen Cloudtechnologieexperten bitten, neue Geräte zu einrichten, die Sie kaufen.

- **Zugriff auf lokale Ressourcen**

     - Wenn Ihre Organisation Windows Server Active Directory lokal verwendet, können Sie Microsoft 365 Business Premium zum Schutz Ihrer Windows 10-Geräte einrichten und gleichzeitig den Zugriff auf lokale Ressourcen beibehalten, die eine lokale Authentifizierung erfordern. Führen Sie die Schritte unter [Aktivieren von Windows 10-Geräten,](manage-windows-devices.md) die mit der Domäne verbunden sind, so aus, dass sie von Microsoft 365 Business Premium verwaltet werden, um diese Einrichtung zu ermöglichen. Dies ist die bevorzugte Methode, und Geräte in diesem Zustand werden als Azure AD-Hybridgeräte bezeichnet.

    - Wenn Ihr Unternehmen über ein lokales Active Directory verfügt, das einige lokale Ressourcen (z. B. Dateifreigaben und Drucker) enthält, können Sie Ihren Azure AD-beigetretenen Geräten Zugriff auf diese Ressourcen geben, indem Sie die folgenden Schritte ausführen: Zugreifen auf lokale Ressourcen von einem Azure AD-beigetretenen Gerät [in Microsoft 365 Business Premium](access-resources.md).

## <a name="see-also"></a>Siehe auch

[Microsoft 365 für Unternehmen-Schulungsvideos](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816)