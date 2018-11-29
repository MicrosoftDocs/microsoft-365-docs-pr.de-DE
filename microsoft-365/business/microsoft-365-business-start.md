---
title: Erste Schritte mit Microsoft 365 Business
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
ms.collection: Adm_O365
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
ms.assetid: 496e690b-b75d-4ff5-bf34-cc32905d0364
description: Informationen Sie zum Einrichten von Microsoft 365 Business.
ms.openlocfilehash: 1c4adc64f62f7d4ae5038603804aa10e48d8a6e1
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/28/2018
ms.locfileid: "26868201"
---
# <a name="get-started-with-microsoft-365-business"></a>Erste Schritte mit Microsoft 365 Business

## <a name="what-is-microsoft-365-business"></a>Was ist Microsoft 365 Business?

Microsoft 365 Business ist eine umfassende Sammlung von Tools für Produktivität und Zusammenarbeit im Unternehmen und besteht z. B. aus Outlook, Word, Excel und anderen Office-Produkten, die immer auf dem neuesten Stand sind. Sie können Ihre Arbeitsdateien auf allen Ihren iOS-, Android- und Windows 10-Geräten mit Sicherheit auf Unternehmensniveau schützen, die einfach zu verwalten ist.
  
Microsoft 365 Business für bis zu 300 Lizenzen gedacht ist, wenn Sie weitere Lizenzen benötigen, finden Sie unter [Microsoft 365 Enterprise](https://go.microsoft.com/fwlink/p/?linkid=860986) -Dokumentation für Weitere Informationen. 
  
## <a name="get-microsoft-365-business"></a>Abrufen von Microsoft 365 Business

- Wenn Sie über einen Partner verfügen, erhält dieser Microsoft 365 Business: [Abrufen von Microsoft 365 Business bei Microsoft über Microsoft Partner Center](get-microsoft-365-business.md).
    
- Wenn Sie nicht die Partner haben und Microsoft 365 Business abrufen möchten, können Sie [hier kaufen](https://www.microsoft.com/en-us/microsoft-365/business).
    
## <a name="set-up-microsoft-365-business"></a>Einrichten von Microsoft 365 Business

 **Übersicht über Microsoft 365 Business Suite einrichten**
  
Das folgende Diagramm beschreibt, wie Administratoren Microsoft 365 Business einrichten. Außerdem werden die Schritte zum Vorbereiten der Windows-PCs für Microsoft 365 Business beschrieben. Sie können auch in der Microsoft 365 Business-Verwaltungskonsole mit der [Windows-AutoPilot](add-autopilot-devices-and-profile.md)neue Geräte hinzufügen. AutoPilot können Sie einrichten und vor dem Konfigurieren neuer Geräte gebracht, produktive einsatzbereit, sobald ein Benutzer sich mit den Anmeldeinformationen ihres Microsoft 365 Business anmeldet.
  
![A diagram that shows the setup and management flow for admins, and also for a user](media/249f81fc-7e79-44c7-8425-3a0b7b651c3b.png)
  
### <a name="1-set-up-microsoft-365-business-admin"></a>1: Einrichten von Microsoft 365 Business (Admin)

Melden Sie sich mit Ihren globalen Administratoranmeldeinformationen beim [Microsoft 365 Business Admin Center](https://portal.office.com/adminportal/home) an, und führen Sie die nachstehenden Schritte zum Einrichten von Microsoft 365 Business aus. 
  
1. [Voraussetzungen zum Schutz von Daten auf Geräten mit Microsoft 365 Business](pre-requisites-for-data-protection.md)
    
    Lesen Sie zuerst die Voraussetzungen, um sicherzustellen, dass Ihre Geräte für Microsoft 365 Business bereit sind.
    
2. [Einrichten von Microsoft 365 Business mithilfe des Setup-Assistenten](set-up.md)
    
    Wenn Sie **dauerhaft aus einer lokalen Active Directory in die Cloud verschieben**sind, können Sie können entweder die Benutzer manuell hinzufügen in der Verwaltungskonsole Microsoft 365 Business mithilfe des Setupassistenten, oder Sie eine einmalige Synchronisierung mit "Connect" Azure AD. Es gibt zwei Methoden, um diese Schritte durchführen: 
    
  - Wenn Sie auch eine Exchange 2010, Exchange 2013 oder 2016 Exchange Server verfügen, können Sie [Verwendung minimale hybride Exchange-Postfächern zu Office 365 schnell zu migrieren](https://support.office.com/article/fdecceed-0702-4af3-85be-f2a0013937ef). Die minimale Hybrid Schritte enthalten eine einmalige Synchronisierung von Azure AD-Benutzern sowie e-Mail-Migration aus lokalen in die Cloud. Nachdem die e-Mail-Migration abgeschlossen ist, ist die verzeichnissynchronisierung automatisch deaktiviert, bei Verwendung dieser Methode.
    
  - Verwenden Sie den Office 365-Verzeichnissynchronisierungs-Assistenten, um Ihre Benutzer mit der Cloud zu synchronisieren. Führen Sie die Schritte unter [Einrichten der Verzeichnissynchronisierung für Office 365](https://support.office.com/article/1b3b5318-6977-42ed-b5c7-96fa74b08846) aus, um diesen Vorgang abzuschließen. Nachdem Sie Ihre Benutzer mit der Cloud synchronisiert haben, müssen Sie die [Verzeichnissynchronisierung deaktivieren](https://support.office.com/article/ee5f861e-bd48-4267-83d1-a4ead4b4a00d).
    
    Außerdem müssen Sie für jeden Benutzer ein, die auf diese Weise eine Lizenz für Microsoft 365 Unternehmen hinzugefügt wurde. Dies ist in der [Setup-Assistenten](set-up.md)oder in das [Zuweisen von Lizenzen für Benutzer in Office 365 für Unternehmen](https://support.office.com/article/997596B5-4173-4627-B915-36ABAC6786DC)möglich.
    
### <a name="2-prepare-mobile-devices"></a>2: Vorbereiten von mobilen Geräten

Führen Sie die Schritte unter[Einrichten von mobilen Geräten für Microsoft 365 Geschäftsbenutzer](set-up-mobile-devices.md) zum Installieren von Office-apps auf Geräten und sicherstellen, dass sie von Microsoft 365 Business geschützt sind. 
  
### <a name="3-prepare-pcs"></a>3: Vorbereiten der PCs

Administratoren können Einstellungen für neue Geräte Windows 10 PCs vor dem Wählen Sie mithilfe von [Windows AutoPilot](add-autopilot-devices-and-profile.md). Benutzer können ihre vorhandenen oder neuen Windows 10 Geräte mithilfe der Schritte in diesem Thema einrichten: [Einrichten von Windows-PCs für Microsoft 365 Geschäftsbenutzer](set-up-windows-devices.md). Für vorhandene Geräte können Benutzer auch **optional**[Dateien zu OneDrive for Business zu verschieben](move-files-to-onedrive.md). Drittanbieter-Tools können sie um Dateien zu OneDrive Windows-Benutzerprofil zugeordnet zu verschieben.
  
Wenn Ihre Organisation Windows Server Active Directory lokalen verwendet wird, können Sie Microsoft 365 Business zum Schutz Ihrer Windows 10 Geräte bei gleichzeitiger Wahrung der Zugriff auf lokale Ressourcen, die erfordern lokale Authentifizierung festlegen. Führen Sie die Schritte zur Einrichtung dieser [Domäne eingebundener Windows 10 Geräte von Microsoft 365 Business verwaltet werden](manage-windows-devices.md) . Dies ist die bevorzugte Methode und Geräte in diesem Status heißen **Hybrid Azure AD Geräte verbunden**. 
  
Wenn Sie ein lokaler beibehalten Active Directory, die einige enthält lokale Ressourcen (beispielsweise Dateifreigaben und Drucker), Sie können Ihre **Azure AD gehörenden Geräten** Zugriff auf diese Ressourcen gewähren, anhand der folgenden Schritte: [Zugriff auf lokale Ressourcen aus einer Azure AD gehörenden Gerät in Microsoft 365 Business](access-resources.md).
  
Nachdem Sie die Windows-10-PCs eingerichtet haben, können Sie für die Geräte [automatisch installieren von Office](auto-install-or-uninstall-office.md) . 
  
## <a name="contact-support"></a>wenden Sie sich an den Support,

 **Wenn Sie den Support kontaktieren müssen:**
  
- Wenden Sie sich an Ihren Partner.
    
- Als ein Microsoft 365 Business Admin haben Sie Zugriff auf unserem Supportteam Customer ** [Kontakt Unterstützung für Business-Produkte – Admin Hilfe](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)**
    
## <a name="related-topics"></a>Verwandte Themen
[Microsoft 365 Business-Dokumentation und -Ressourcen](https://go.microsoft.com/fwlink/p/?linkid=853701)
  
[Verwalten von Microsoft 365 Business](manage.md) [Migrieren zu Microsoft 365 Business](migrate-to-microsoft-365-business.md)
  

