---
title: Erste Schritte mit Microsoft 365 Business
f1.keywords:
- NOCSH
ms.author: efrene
author: efrene
manager: scotv
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
- TRN_SMB
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
- TRN_M365B
- OKR_SMB_Videos
- seo-marvel-mar
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
ms.assetid: 496e690b-b75d-4ff5-bf34-cc32905d0364
description: Erfahren Sie Microsoft 365 Unternehmens, wie Sie sie einrichten und wie Sie die Geräte und PCs Ihrer Benutzer vorbereiten, um sicherzustellen, dass sie von Microsoft 365 geschützt sind.
ms.openlocfilehash: ddf6f8d12587c6fb562a599a41c190ffef32c147
ms.sourcegitcommit: de5fce90de22ba588e75e1a1d2e87e03b9e25ec7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/10/2021
ms.locfileid: "52293705"
---
# <a name="get-started-with-microsoft-365-for-business"></a>Erste Schritte mit Microsoft 365 Business

## <a name="what-is-microsoft-365-for-business"></a>Was ist Microsoft 365 Business

Microsoft 365 business ist eine umfassende Reihe von Tools für Produktivität und Zusammenarbeit, z. B. Outlook, Word, Excel und andere Office-Produkte, die immer auf dem neuesten Stand sind. Sie können Ihre Arbeitsdateien auf all Ihren iOS-, Android- und Windows 10 mit sicherheit auf Unternehmensqualität schützen, die einfach zu verwalten ist.

Sehen Sie sich dieses Video an, um eine kurze Übersicht über Microsoft 365 Business zu erhalten.<br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE2mhaA] 
  
Microsoft 365 business ist für bis zu 300 Lizenzen gedacht. Wenn Sie weitere Lizenzen benötigen, lesen Sie die Dokumentation zu [Microsoft 365 Enterprise](../enterprise/index.yml), um weitere Informationen zu erhalten. 
  
## <a name="get-microsoft-365-for-business"></a>Get Microsoft 365 for Business

- Wenn Sie über einen Partner verfügen, erhalten sie Microsoft 365 Business: [Get Microsoft 365 for Business from Microsoft Partner Center](get-microsoft-365-business.md).
    
- Wenn Sie keinen Partner haben und Microsoft 365 erhalten möchten, können Sie ihn [hier kaufen.](https://www.microsoft.com/microsoft-365/business)
    
## <a name="set-up-microsoft-365-for-business"></a>Einrichten von Microsoft 365 für Unternehmen

 **Übersicht über Microsoft 365 business Suite einrichten**
  
Im folgenden Diagramm wird beschrieben, wie Administratoren Microsoft 365 Unternehmen einrichten. Außerdem werden die Schritte zum Vorbereiten Windows PCs für Microsoft 365 Business beschrieben. Sie können auch neue Geräte im Microsoft 365 Admin Center mit [Windows AutoPilot hinzufügen.](add-autopilot-devices-and-profile.md) Sie können AutoPilot verwenden, um neue Geräte so einrichten und vorkonfiguriert zu haben, dass sie für die produktive Verwendung bereit sind, sobald sich ein Benutzer mit seinen Anmeldeinformationen Microsoft 365 anmeldet.
  
![A diagram that shows the setup and management flow for admins, and also for a user](../media/249f81fc-7e79-44c7-8425-3a0b7b651c3b.png)

Sehen Sie sich dieses Video an, um eine Übersicht Microsoft 365 Unternehmenseinrichtung zu erhalten.<br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1FYSM] 

Wenn Sie dieses Video hilfreich fanden, sehen Sie sich bitte die [komplette Schulungsserie für kleine Unternehmen und jene, die neu bei Microsoft 365 sind](../business-video/index.yml), an.

  
### <a name="1-set-up-microsoft-365-for-business-admin"></a>1: Einrichten Microsoft 365 business (Admin)

Melden Sie sich [bei Microsoft 365 Admin Center](https://portal.office.com/adminportal/home) mit Ihren globalen Administratoranmeldeinformationen an, und führen Sie die folgenden Schritte zum Einrichten von Microsoft 365 Business aus. 
  
1. [Voraussetzungen für den Schutz von Daten auf Geräten mit Microsoft 365 Business](pre-requisites-for-data-protection.md)
    
    Lesen Sie zuerst die voraussetzungen, um sicherzustellen, dass Ihre Geräte für die Microsoft 365 bereit sind.
    
2. [Einrichten von Microsoft 365 business mithilfe des Setup-Assistenten](set-up.md)
    
    Wenn Sie dauerhaft von einem lokalen **Active Directory** in die Cloud wechseln, können Sie zum Microsoft 365 Admin Center wechseln und den Setup-Assistenten verwenden, um Ihre Benutzer manuell hinzuzufügen, oder Sie können eine einmalige Synchronisierung mit Azure AD Verbinden. Sie können auf zwei Arten vorgehen: 
    
    - Wenn Sie auch über einen server Exchange 2010, Exchange 2013 oder Exchange 2016 verfügen, können Sie minimal hybrid verwenden, um [Exchange](/Exchange/mailbox-migration/use-minimal-hybrid-to-quickly-migrate)Postfächer schnell zu Microsoft 365 . Die minimalen Hybridschritte umfassen eine einmalige Synchronisierung von Benutzern mit Azure AD und die E-Mail-Migration von der lokalen in die Cloud. Nach Abschluss der E-Mail-Migration wird die Verzeichnissynchronisierung automatisch deaktiviert, wenn Sie diese Methode verwenden.
    
    - Verwenden Sie den Verzeichnissynchronisierungs-Assistenten, um Ihre Benutzer mit der Cloud zu synchronisieren. Führen Sie die Schritte unter [Einrichten der Verzeichnissynchronisierung für Microsoft 365,](../enterprise/set-up-directory-synchronization.md) um diesen Prozess zu ausführen. Nachdem Sie Ihre Benutzer mit der Cloud synchronisiert haben, müssen Sie die Verzeichnissynchronisierung für [Microsoft 365.](../enterprise/turn-off-directory-synchronization.md)
    
    Außerdem müssen Sie jedem Benutzer, der auf diese Weise hinzugefügt wurde, eine Lizenz für Microsoft 365 geben. Sie können dies im [Setup-Assistenten tun,](set-up.md) oder Sie können [Benutzern Lizenzen zuweisen.](../admin/manage/assign-licenses-to-users.md)
    
### <a name="2-prepare-mobile-devices"></a>2: Vorbereiten mobiler Geräte

Führen Sie die Schritte unter Einrichten mobiler Geräte für [Microsoft 365 für Geschäftsbenutzer](set-up-mobile-devices.md) aus, um Office-Apps auf Geräten zu installieren und sicherzustellen, dass sie durch Microsoft 365 Business geschützt sind. 
  
### <a name="3-prepare-pcs"></a>3: Vorbereiten von PCs

Administratoren können Einstellungen für neue Windows 10 mithilfe von [autoPilot Windows auswählen.](add-autopilot-devices-and-profile.md) Benutzer können ihre vorhandenen oder neuen Windows 10 einrichten, indem sie die Schritte in diesem Thema ausführen: Einrichten Windows PCs für Microsoft 365 [Für Geschäftsbenutzer](set-up-windows-devices.md). Bei vorhandenen Geräten können Benutzer **Dateien optional** [in OneDrive for Business.](move-files-to-onedrive.md) Sie können auch Tools von Drittanbietern verwenden, um Dateien zu verschieben, die Windows profil zugeordnet sind, OneDrive.
  
Wenn Ihre Organisation Windows Server Active Directory lokal verwendet, können Sie Microsoft 365 for Business einrichten, um Ihre Windows 10-Geräte zu schützen und gleichzeitig den Zugriff auf lokale Ressourcen zu erhalten, die eine lokale Authentifizierung erfordern. Führen Sie die Schritte unter Aktivieren der Windows 10, die von Microsoft 365 [business](manage-windows-devices.md) verwaltet werden, um diese Einrichtung zu ermöglichen. Diese Methode wird bevorzugt, und Geräte in diesem Zustand werden **als Azure AD-Hybridgeräte bezeichnet.** 
  
Wenn Sie ein lokales Active Directory beibehalten, das einige lokale Ressourcen (z. B. Dateifreigaben und Drucker) enthält, können Sie Ihren **Azure AD-beigetretenen** Geräten Zugriff auf diese Ressourcen geben, indem Sie die folgenden Schritte ausführen: Zugreifen auf lokale Ressourcen von einem [Azure AD-beigetretenen](access-resources.md)Gerät in Microsoft 365 business .
  
  
## <a name="contact-support"></a>wenden Sie sich an den Support,

 **Wenn Sie den Support kontaktieren müssen:**
  
- Wenden Sie sich an Ihren Partner.
    
- Als Microsoft 365 für Geschäftsadministratoren haben Sie Zugriff auf unser Kundensupportteam: **[Kontakt support for business products - Admin Help](../business-video/get-help-support.md)**
    
## <a name="related-content"></a>Verwandte Inhalte

[Microsoft 365 für Geschäftsdokumentationen und -ressourcen](./index.yml)
  
[Manage Microsoft 365 for Business](manage.md)[Migrate to Microsoft 365 business](migrate-to-microsoft-365-business.md)

[Microsoft 365 für Unternehmen-Schulungsvideos](../business-video/index.yml)