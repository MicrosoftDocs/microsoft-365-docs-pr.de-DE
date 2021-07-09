---
title: Erste Schritte mit Microsoft 365 for Business
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
description: Erfahren Sie mehr über Microsoft 365 für Unternehmen, wie Sie es einrichten und wie Sie die Geräte und PCs Ihrer Benutzer vorbereiten, um sicherzustellen, dass sie durch Microsoft 365 für Unternehmen geschützt sind.
ms.openlocfilehash: 2ab0079da7a8f30d481cdb3d3dc6d165b4a19e99
ms.sourcegitcommit: 0d1b065c94125b495e9886200f7918de3bda40b3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/08/2021
ms.locfileid: "53339288"
---
# <a name="get-started-with-microsoft-365-for-business"></a>Erste Schritte mit Microsoft 365 for Business

## <a name="what-is-microsoft-365-for-business"></a>Was ist Microsoft 365 für Unternehmen?

Microsoft 365 für Unternehmen ist eine umfassende Sammlung von Tools für die Produktivität und Zusammenarbeit im Unternehmen, z. B. Outlook, Word, Excel und andere Office Produkte, die immer auf dem neuesten Stand sind. Sie können Ihre Arbeitsdateien auf allen Ihren iOS-, Android- und Windows 10-Geräten mit einfacher Verwaltung von Sicherheit auf Unternehmensniveau schützen.

## <a name="watch-what-is-microsoft-365-business-premium"></a>Schauen Sie sich an: Was ist Microsoft 365 Business Premium

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE2mhaA] 
  
Microsoft 365 business ist für bis zu 300 Lizenzen vorgesehen. Wenn Sie weitere Lizenzen benötigen, lesen Sie die Dokumentation zu [Microsoft 365 Enterprise](../enterprise/index.yml), um weitere Informationen zu erhalten. 
  
## <a name="get-microsoft-365-for-business"></a>Abrufen von Microsoft 365 für Unternehmen

- Wenn Sie einen Partner haben, erhält er Microsoft 365 für Unternehmen: [Holen Sie sich Microsoft 365 for Business aus dem Microsoft Partner Center.](get-microsoft-365-business.md)
    
- Wenn Sie keinen Partner haben und Microsoft 365 für Unternehmen erhalten möchten, können Sie [ihn hier kaufen.](https://www.microsoft.com/microsoft-365/business)
    
## <a name="set-up-microsoft-365-for-business"></a>Einrichten von Microsoft 365 für Unternehmen

 **Übersicht über die Einrichtung von Microsoft 365 for Business Suite**
  
Das folgende Diagramm beschreibt, wie Administratoren Microsoft 365 für Unternehmen einrichten. Außerdem werden die Schritte zum Vorbereiten Windows PCs für Microsoft 365 for Business beschrieben. Sie können auch neue Geräte im Microsoft 365 Admin Center mit [Windows AutoPilot](add-autopilot-devices-and-profile.md)hinzufügen. Sie können AutoPilot verwenden, um neue Geräte einzurichten und vorkonfigurieren, damit sie produktiv verwendet werden können, sobald sich ein Benutzer mit seiner Microsoft 365 für Geschäftsanmeldeinformationen anmeldet.
  
![A diagram that shows the setup and management flow for admins, and also for a user](../media/249f81fc-7e79-44c7-8425-3a0b7b651c3b.png)

## <a name="watch-set-up-microsoft-365-business"></a>Überwachung: Einrichten von Microsoft 365 Business

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1FYSM] 

Wenn Sie dieses Video hilfreich fanden, schauen Sie sich bitte die [komplette Schulungsserie für kleine Unternehmen und jene, die neu bei Microsoft 365 sind](../business-video/index.yml), an.

  
### <a name="1-set-up-microsoft-365-for-business-admin"></a>1: Einrichten von Microsoft 365 für Unternehmen (Administrator)

Melden Sie sich mit Ihren globalen Administratoranmeldeinformationen bei [Microsoft 365 Admin Center](https://admin.microsoft.com/adminportal/home) an, und führen Sie die folgenden Schritte aus, um Microsoft 365 für Unternehmen einzurichten. 
  
1. [Voraussetzungen für den Schutz von Daten auf Geräten mit Microsoft 365 for Business](pre-requisites-for-data-protection.md)
    
    Lesen Sie zuerst die Voraussetzungen, um sicherzustellen, dass Ihre Geräte für Microsoft 365 business bereit sind.
    
2. [Verwenden des Setup-Assistenten zum Einrichten von Microsoft 365 für Unternehmen](set-up.md)
    
    Wenn Sie **dauerhaft von einem lokalen Active Directory in die Cloud wechseln,** können Sie zum Microsoft 365 Admin Center wechseln und den Setup-Assistenten verwenden, um Ihre Benutzer manuell hinzuzufügen, oder Sie können eine einmalige Synchronisierung mit Azure AD Verbinden durchführen. Sie können auf zwei Arten vorgehen: 
    
    - Wenn Sie auch über einen Server Exchange 2010, Exchange 2013 oder Exchange 2016 verfügen, können Sie [minimale Hybridbereitstellung verwenden, um Exchange Postfächer schnell zu Microsoft 365 zu migrieren.](/Exchange/mailbox-migration/use-minimal-hybrid-to-quickly-migrate) Die minimalen Hybridschritte umfassen eine einmalige Synchronisierung von Benutzern mit Azure AD und die E-Mail-Migration von der lokalen Umgebung in die Cloud. Nach Abschluss der E-Mail-Migration wird die Verzeichnissynchronisierung automatisch deaktiviert, wenn Sie diese Methode verwenden.
    
    - Verwenden Sie den Verzeichnissynchronisierungs-Assistenten, um Ihre Benutzer mit der Cloud zu synchronisieren. Führen Sie die Schritte unter Einrichten der [Verzeichnissynchronisierung für Microsoft 365](../enterprise/set-up-directory-synchronization.md) aus, um diesen Vorgang abzuschließen. Nachdem Sie Ihre Benutzer mit der Cloud synchronisiert haben, müssen Sie die [Verzeichnissynchronisierung für Microsoft 365 deaktivieren.](../enterprise/turn-off-directory-synchronization.md)
    
    Außerdem müssen Sie jedem Benutzer, der auf diese Weise hinzugefügt wurde, eine Lizenz für Microsoft 365 für Unternehmen erteilen. Sie können dies im [Setup-Assistenten](set-up.md) tun, oder Sie können [Benutzern Lizenzen zuweisen.](../admin/manage/assign-licenses-to-users.md)
    
### <a name="2-prepare-mobile-devices"></a>2: Vorbereiten mobiler Geräte

Führen Sie die Schritte unter ["Einrichten mobiler Geräte für Microsoft 365 für Geschäftsbenutzer"](set-up-mobile-devices.md) aus, um Office Apps auf Geräten zu installieren und sicherzustellen, dass sie durch Microsoft 365 für Unternehmen geschützt sind. 
  
### <a name="3-prepare-pcs"></a>3: Vorbereiten von PCs

Administratoren können Einstellungen für neue Windows 10 PCs mithilfe von [Windows AutoPilot](add-autopilot-devices-and-profile.md)vorab auswählen. Benutzer können ihre vorhandenen oder neuen Windows 10 Geräte einrichten, indem sie die Schritte in diesem Thema ausführen: [Einrichten Windows PCs für Microsoft 365 für Geschäftsbenutzer.](set-up-windows-devices.md) Bei vorhandenen Geräten können Benutzer **Dateien optional** in [OneDrive for Business verschieben.](move-files-to-onedrive.md) Sie können auch Drittanbietertools verwenden, um Dateien, die Windows Profil zugeordnet sind, in OneDrive zu verschieben.
  
Wenn Ihre Organisation Windows Server Active Directory lokal verwendet, können Sie Microsoft 365 für Unternehmen einrichten, um Ihre Windows 10 Geräte zu schützen und gleichzeitig den Zugriff auf lokale Ressourcen beizubehalten, die eine lokale Authentifizierung erfordern. Führen Sie die Schritte unter Aktivieren der [domänenverbundenen Windows 10 Geräte aus, die von Microsoft 365 für Unternehmen verwaltet werden,](manage-windows-devices.md) um dies einzurichten. Diese Methode wird bevorzugt, und Geräte in diesem Zustand werden als **in Azure AD eingebundene Hybridgeräte** bezeichnet. 
  
Wenn Sie ein lokales Active Directory beibehalten, das einige lokale Ressourcen (z. B. Dateifreigaben und Drucker) enthält, können Sie Ihren **In Azure AD-verbundenen Geräten** Zugriff auf diese Ressourcen gewähren, indem Sie die hier beschriebenen Schritte ausführen: Zugreifen auf lokale Ressourcen von einem Mit Azure AD [verbundenen Gerät in Microsoft 365 for Business.](access-resources.md)
  
  
## <a name="contact-support"></a>Support kontaktieren

 **Wenn Sie den Support kontaktieren müssen:**
  
- Wenden Sie sich an Ihren Partner.
    
- Als Microsoft 365 für Geschäftsadministratoren haben Sie Zugriff auf unser Kundensupportteam: **[Wenden Sie sich an den Support für Geschäftsprodukte – Administratorhilfe](../business-video/get-help-support.md)**
    
## <a name="related-content"></a>Verwandte Inhalte

[Microsoft 365 für Geschäftsdokumentation und Ressourcen](./index.yml) (Linkseite)\
[Verwalten Microsoft 365 für Unternehmen](manage.md) (Artikel)\
[Migrieren zu Microsoft 365 for Business](migrate-to-microsoft-365-business.md) (Artikel)\
[Microsoft 365 für Business-Schulungsvideos](../business-video/index.yml) (Linkseite)