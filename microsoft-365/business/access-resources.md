---
title: Zugreifen auf lokale Ressourcen von einem In Azure AD beigetretenen Gerät in Microsoft 365 Business
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.collection: M365-subscription-management
localization_priority: Normal
ms.custom:
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
ms.assetid: b0f4d010-9fd1-44d0-9d20-fabad2cdbab5
description: Erfahren Sie, wie Sie von einem mit Azure Active Directory beigetretenen Windows 10-Gerät Zugriff auf lokale Ressourcen wie Line-of-Business-Apps, Dateifreigaben und Drucker erhalten.
ms.openlocfilehash: fc02fd30f41f25f52e653e750a6bdfd1bd7f800e
ms.sourcegitcommit: a62ac3c01ba700a51b78a647e2301f27ac437c5a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/12/2021
ms.locfileid: "50233838"
---
# <a name="access-on-premises-resources-from-an-azure-ad-joined-device-in-microsoft-365-business-premium"></a>Zugreifen auf lokale Ressourcen von einem In Azure AD beigetretenen Gerät in Microsoft 365 Business Premium

Dieser Artikel bezieht sich auf Microsoft 365 Business Premium.

Jedes Windows 10-Gerät, dem Azure Active Directory beigetreten ist, hat Zugriff auf alle cloudbasierten Ressourcen, z. B. Ihre Microsoft 365-Apps, und kann durch Microsoft 365 Business Premium geschützt werden. Sie können auch den Zugriff auf lokale Ressourcen wie Branchen-Apps, Dateifreigaben und Drucker zulassen. Um den Zugriff zu ermöglichen, verwenden [Sie Azure AD Connect,](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect) um Ihr lokales Active Directory mit Azure Active Directory zu synchronisieren. 

Weitere Informationen finden Sie unter [Einführung in die Geräteverwaltung in Azure Active Directory.](https://docs.microsoft.com/azure/active-directory/device-management-introduction)
Die Schritte werden auch in den folgenden Abschnitten zusammengefasst.
 
## <a name="run-azure-ad-connect"></a>Ausführen von Azure AD Connect

Führen Sie die folgenden Schritte aus, um den azure AD-beigetretenen Geräten Ihrer Organisation den Zugriff auf lokale Ressourcen zu ermöglichen.
  
1. Um Ihre Benutzer, Gruppen und Kontakte aus dem lokalen Active Directory mit Azure Active Directory zu synchronisieren, führen Sie den Assistenten für die Verzeichnissynchronisierung und Azure AD Connect aus, wie unter Einrichten der Verzeichnissynchronisierung für [Office 365 beschrieben.](https://docs.microsoft.com/microsoft-365/enterprise/set-up-directory-synchronization)
    
2. Stellen Sie nach Abschluss der Verzeichnissynchronisierung sicher, dass die Windows 10-Geräte Ihrer Organisation in Azure AD verbunden sind. Dieser Schritt wird auf jedem Windows 10-Gerät einzeln ausgeführt. Weitere [Informationen finden Sie unter "Einrichten von Windows-Geräten für Microsoft 365 Business Premium-Benutzer".](set-up-windows-devices.md) 
    
3. Sobald die Windows 10-Geräte Azure AD beigetreten sind, muss jeder Benutzer seine Geräte neu starten und sich mit seinen Microsoft 365 Business Premium-Anmeldeinformationen anmelden. Alle Geräte haben jetzt auch Zugriff auf lokale Ressourcen.
    
Es sind keine zusätzlichen Schritte erforderlich, um Zugriff auf lokale Ressourcen für azure AD-beigetretene Geräte zu erhalten. Diese Funktionalität ist in Windows 10 integrierte. 

Wenn Sie planen, sich beim anderen AADJ-Gerät als der Kennwortmethode wie PIN/Biometrie über die Anmeldeinformationen des WHFB anzumelden und dann auf lokale Ressourcen (Freigaben, Drucker) zu zugreifen. usw.), folgen Sie bitte https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-hybrid-aadj-sso-base
  
Wenn Ihre Organisation nicht bereit für die Bereitstellung in der oben beschriebenen Azure AD-Gerätekonfiguration ist, erwägen Sie die Einrichtung der Azure [AD-Geräte-Hybridkonfiguration.](manage-windows-devices.md)
  
### <a name="considerations-when-you-join-windows-devices-to-azure-ad"></a>Überlegungen beim Beitritt von Windows-Geräten zu Azure AD

Wenn das Windows-Gerät, dem Sie Azure AD beigetreten sind, zuvor einer Domäne oder einer Arbeitsgruppe beigetreten ist, sollten Sie die folgenden Einschränkungen beachten:
  
- Wenn ein Gerät mit Azure AD beitritt, wird ein neuer Benutzer erstellt, ohne auf ein vorhandenes Profil zu verweisen. Profile müssen manuell migriert werden. Ein Benutzerprofil enthält Informationen wie Favoriten, lokale Dateien, Browsereinstellungen und Startmenüeinstellungen. Ein optimaler Ansatz besteht in der Suche nach einem Drittanbietertool, um vorhandene Dateien und Einstellungen dem neuen Profil zu zuordnungen.

- Wenn das Gerät Gruppenrichtlinienobjekte (Group Policy Objects, GPO) verwendet, verfügen einige Gruppenrichtlinienobjekte möglicherweise nicht über einen vergleichbaren [Konfigurationsdienstanbieter (Configuration Service Provider,](https://docs.microsoft.com/windows/configuration/provisioning-packages/how-it-pros-can-use-configuration-service-providers) CSP) in Intune. Führen Sie das [Tool MMAT aus,](https://www.microsoft.com/download/details.aspx?id=45520) um nach vergleichbaren CSPs für vorhandene Gruppenrichtlinienobjekte zu suchen.

- Benutzer können sich möglicherweise nicht bei Anwendungen authentifizieren, die von der Active Directory-Authentifizierung abhängig sind. Bewerten Sie die Legacy-App, und erwägen Sie nach Möglichkeit das Aktualisieren auf eine App, die moderne Authentifizierung verwendet.

- Die Active Directory-Druckerermittlung funktioniert nicht. Sie können direkte Druckerpfade für alle Benutzer bereitstellen oder [universelles Drucken verwenden.](https://aka.ms/UPDocs)
