---
title: Erste Schritte mit Microsoft 365 Business
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
ms.assetid: 496e690b-b75d-4ff5-bf34-cc32905d0364
description: Informationen zum Einrichten von Microsoft 365 Business.
ms.openlocfilehash: 78f7360c80667b8d34fad9d849cfc2cf83a8577b
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32278107"
---
# <a name="get-started-with-microsoft-365-business"></a>Erste Schritte mit Microsoft 365 Business

## <a name="what-is-microsoft-365-business"></a>Was ist Microsoft 365 Business?

Microsoft 365 Business ist eine umfassende Sammlung von Tools für Produktivität und Zusammenarbeit im Unternehmen und besteht z. B. aus Outlook, Word, Excel und anderen Office-Produkten, die immer auf dem neuesten Stand sind. Sie können Ihre Arbeitsdateien auf allen Ihren iOS-, Android- und Windows 10-Geräten mit Sicherheit auf Unternehmensniveau schützen, die einfach zu verwalten ist.
  
Microsoft 365 Business ist für bis zu 300-Lizenzen gedacht, wenn Sie weitere Lizenzen benötigen, finden Sie weitere Informationen unter [microsoft 365 Enterprise](https://go.microsoft.com/fwlink/p/?linkid=860986) Documentation. 
  
## <a name="get-microsoft-365-business"></a>Abrufen von Microsoft 365 Business

- Wenn Sie über einen Partner verfügen, erhält dieser Microsoft 365 Business: [Abrufen von Microsoft 365 Business bei Microsoft über Microsoft Partner Center](get-microsoft-365-business.md).
    
- Wenn Sie keinen Partner haben und Microsoft 365 Business erhalten möchten, können Sie [es hier kaufen](https://www.microsoft.com/en-us/microsoft-365/business).
    
## <a name="set-up-microsoft-365-business"></a>Einrichten von Microsoft 365 Business

 **Übersicht über die Microsoft 365 Business Suite-Einrichtung**
  
Im folgenden Diagramm wird beschrieben, wie Administratoren Microsoft 365 Business einrichten. Darüber hinaus werden die Schritte zum Vorbereiten von Windows-PCs für Microsoft 365 Business beschrieben. Sie können mit dem [Windows AutoPilot](add-autopilot-devices-and-profile.md) auch neue Geräte im Microsoft 365 Business Admin Center hinzufügen. Mit dem AutoPilot können Sie neue Geräte einrichten und vorkonfigurieren, um sie auf den produktiven Einsatz vorzubereiten, sobald sich ein Benutzer mit seinen Microsoft 365 Business-Anmeldeinformationen anmeldet.
  
![A diagram that shows the setup and management flow for admins, and also for a user](media/249f81fc-7e79-44c7-8425-3a0b7b651c3b.png)
  
### <a name="1-set-up-microsoft-365-business-admin"></a>1: Einrichten von Microsoft 365 Business (admin)

Melden Sie sich mit Ihren globalen Administratoranmeldeinformationen beim [Microsoft 365 Business Admin Center](https://portal.office.com/adminportal/home) an, und führen Sie die nachstehenden Schritte zum Einrichten von Microsoft 365 Business aus. 
  
1. [Voraussetzungen zum Schutz von Daten auf Geräten mit Microsoft 365 Business](pre-requisites-for-data-protection.md)
    
    Lesen Sie zuerst die Voraussetzungen, um sicherzustellen, dass Ihre Geräte für Microsoft 365 Business bereit sind.
    
2. [Einrichten von Microsoft 365 Business mithilfe des Setup-Assistenten](set-up.md)
    
    Wenn Sie **dauerhaft von einem lokalen Active Directory in die Cloud wechseln**, können Sie Ihre Benutzer entweder manuell im Microsoft 365 Business Admin Center hinzufügen, indem Sie den Setup-Assistenten verwenden, oder Sie können eine einmalige Synchronisierung mit Azure AD Connect durchführen. Sie können auf zwei Arten vorgehen: 
    
  - Wenn Sie auch über einen Exchange 2010-, Exchange 2013-oder Exchange 2016-Server verfügen, können Sie [die minimale hybride verwenden, um Exchange-Postfächer schnell zu Office 365 zu migrieren](https://support.office.com/article/fdecceed-0702-4af3-85be-f2a0013937ef). Die Schritte bei der minimalen Hybridkonfiguration umfassen eine einmalige Synchronisierung von Benutzern mit Azure AD sowie die E-Mail-Migration aus der lokalen Bereitstellung in die Cloud. Nachdem die E-Mail-Migration abgeschlossen wurde, wird die Verzeichnissynchronisierung automatisch deaktiviert, wenn Sie diese Methode verwenden.
    
  - Verwenden Sie den Office 365-Verzeichnissynchronisierungs-Assistenten, um Ihre Benutzer mit der Cloud zu synchronisieren. Führen Sie die Schritte unter [Einrichten der Verzeichnissynchronisierung für Office 365](https://support.office.com/article/1b3b5318-6977-42ed-b5c7-96fa74b08846) aus, um diesen Vorgang abzuschließen. Nachdem Sie Ihre Benutzer mit der Cloud synchronisiert haben, müssen Sie die [Verzeichnissynchronisierung deaktivieren](https://support.office.com/article/ee5f861e-bd48-4267-83d1-a4ead4b4a00d).
    
    Außerdem müssen Sie jedem Benutzer, der auf diese Weise hinzugefügt wurde, eine Lizenz für Microsoft 365 Business erteilen. Sie können dies im Setup- [Assistenten](set-up.md)oder in den [benutzern in Office 365 für Unternehmen zuweisen](https://support.office.com/article/997596B5-4173-4627-B915-36ABAC6786DC).
    
### <a name="2-prepare-mobile-devices"></a>2: Vorbereiten mobiler Geräte

Führen Sie die Schritte unter[Einrichten von mobilen Geräten für microsoft 365 Business-Benutzer](set-up-mobile-devices.md) aus, um Office-Apps auf Geräten zu installieren und sicherzustellen, dass Sie von Microsoft 365 Business geschützt werden. 
  
### <a name="3-prepare-pcs"></a>3: Vorbereiten von PCs

Administratoren können Einstellungen für neue Geräte Windows 10-PCs mithilfe von [Windows Autopilot](add-autopilot-devices-and-profile.md)auswählen. Benutzer können Ihre vorhandenen oder neuen Windows 10-Geräte einrichten, indem Sie die Schritte in diesem Thema ausführen: Einrichten von [Windows-PCs für Microsoft 365 Business-Benutzer](set-up-windows-devices.md). Für vorhandene Geräte können Benutzer **optional**auch[Dateien in OneDrive for Business verschieben](move-files-to-onedrive.md). Sie können auch Drittanbietertools verwenden, um mit Windows Profile verknüpfte Dateien zu OneDrive zu verschieben.
  
Wenn Ihre Organisation Windows Server Active Directory lokal verwendet, können Sie Microsoft 365 Business einrichten, um Ihre Windows 10-Geräte zu schützen, ohne dabei den Zugriff auf lokale Ressourcen zu gewährleisten, die lokal authentifiziert werden müssen. Führen Sie die Schritte unter [enable Domain-joinEd Windows 10 Devices aus, die von Microsoft 365 Business verwaltet werden](manage-windows-devices.md) , um diese einzurichten. Dies ist die bevorzugte Methode, und die Geräte in diesem Zustand werden als **hybride Azure AD-verbundene Geräte**bezeichnet. 
  
Wenn Sie ein lokales Active Directory mit einigen lokalen Ressourcen (wie Dateifreigaben und Druckern) behalten, können Sie Ihren mit **Azure AD verbundenen Geräten** Zugriff auf diese Ressourcen gewähren, indem Sie die folgenden Schritte ausführen: [Zugriff auf lokale Ressourcen über eine Azure AD-verbundenes Gerät in Microsoft 365 Business](access-resources.md).
  
Nachdem Sie Windows 10-PCs eingerichtet haben, können Sie [Office automatisch](auto-install-or-uninstall-office.md) auf den Geräten installieren. 
  
## <a name="contact-support"></a>wenden Sie sich an den Support,

 **Wenn Sie den Support kontaktieren müssen:**
  
- Wenden Sie sich an Ihren Partner.
    
- Als Microsoft 365 Business admin haben Sie Zugriff auf unser Kundensupport-Team, ** [kontaktieren des Supports für Business-Produkte – Administratorhilfe](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)**
    
## <a name="related-topics"></a>Verwandte Themen
[Microsoft 365 Business-Dokumentation und -Ressourcen](https://go.microsoft.com/fwlink/p/?linkid=853701)
  
[Verwalten von Microsoft 365 Business](manage.md) [Migrieren zu Microsoft 365 Business](migrate-to-microsoft-365-business.md)
  

