---
title: Zugreifen auf lokale Ressourcen von einem Azure AD verbundenen Gerät in Microsoft 365 Business
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.collection: M365-subscription-management
localization_priority: Normal
ms.custom: OKR_SMB_M365
search.appverid:
- BCS160
- MET150
ms.assetid: b0f4d010-9fd1-44d0-9d20-fabad2cdbab5
description: Hier erfahren Sie, wie Sie Zugriff auf lokale Ressourcen wie Branchen-apps, Dateifreigaben und Drucker aus einem Azure-Active Directory, dem Windows 10-Gerät beigetreten ist.
ms.openlocfilehash: 26ba0ffb64ddce32369002120657456e47ac0c7f
ms.sourcegitcommit: 6003d6da0a85c97357eb3dba3918eb145f381fe1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/27/2019
ms.locfileid: "37287353"
---
# <a name="access-on-premises-resources-from-an-azure-ad-joined-device-in-microsoft-365-business"></a>Zugreifen auf lokale Ressourcen von einem Azure AD verbundenen Gerät in Microsoft 365 Business

Jedes Windows 10-Gerät, das als Azure Active Directory beigetreten ist, hat Zugriff auf alle Cloud-basierten Ressourcen wie Ihre Office 365-apps und kann von Microsoft 365 Business geschützt werden. Um auch Zugriff auf lokale Ressourcen wie Branchen-apps, Dateifreigaben und Drucker zu gewähren, müssen Sie Ihre lokale Active Directory mit Azure Active Directory mithilfe von [Azure AD Connect](https://docs.microsoft.com/en-us/azure/active-directory/connect/active-directory-aadconnect)synchronisieren. 

Weitere Informationen finden Sie unter [Einführung in die Geräteverwaltung in Azure Active Directory](https://docs.microsoft.com/en-us/azure/active-directory/device-management-introduction) .
Die Schritte sind auch in den folgenden Abschnitten zusammengefasst.

## <a name="run-azure-ad-connect"></a>Ausführen Azure AD Connect

Führen Sie die folgenden Schritte aus, um die Azure AD verbundenen Geräte Ihrer Organisation für den Zugriff auf lokale Ressourcen zu aktivieren.
  
1. Führen Sie den Assistenten für die Verzeichnissynchronisierung aus, und Azure AD Connect wie unter [Einrichten der Verzeichnissynchronisierung für Office 365](https://support.office.com/article/1b3b5318-6977-42ed-b5c7-96fa74b08846)beschrieben, um Ihre Benutzer, Gruppen und Kontakte von der lokalen Active Directory in Azure Active Directory zu synchronisieren.
    
2. Stellen Sie nach Abschluss der Verzeichnissynchronisierung sicher, dass die Windows 10-Geräte Ihrer Organisation Azure AD verbunden sind. Dieser Schritt wird auf jedem Windows 10-Gerät einzeln ausgeführt. Weitere Informationen finden Sie unter [Einrichten von Windows-Geräten für Microsoft 365 Business-Benutzer](set-up-windows-devices.md) . 
    
3. Sobald die Windows 10-Geräte Azure AD beigetreten sind, sollten alle Benutzer ihre Geräte neu starten und sich mit Ihren Microsoft 365-Geschäfts Anmeldeinformationen anmelden. Alle Geräte können nun auch auf lokale Ressourcen zugreifen.
    
Es sind keine weiteren Schritte erforderlich, um Zugriff auf lokale Ressourcen für Azure AD verbundene Geräte zu erhalten. Hierbei handelt es sich um integrierte Funktionen, die in Windows 10 verfügbar sind. 
  
Wenn Ihre Organisation nicht bereit ist, in der oben beschriebenen Azure AD beigefügten Gerätekonfiguration bereitzustellen, sollten Sie die [Konfiguration einer hybriden Azure AD](manage-windows-devices.md)die Verbindung mit dem Gerät konfigurieren.
  
### <a name="considerations-when-joining-your-windows-devices-to-azure-ad"></a>Überlegungen zum Verbinden Ihrer Windows-Geräte mit Azure AD

Wenn Sie Azure AD einem Windows-Gerät beitreten, das zuvor einer Domäne oder einer Arbeitsgruppe beigetreten ist, müssen Sie die folgenden Einschränkungen in Frage stellen:
  
- Wenn ein Gerät Azure AD Beitritt, wird ein neuer Benutzer erstellt, ohne auf ein vorhandenes Profil zu verweisen. Um dies zu beheben, müssen Profile manuell migriert werden. Ein Benutzerprofil enthält Informationen wie Favoriten, lokale Dateien, Browsereinstellungen, Start Menü Einstellungen usw. Ein optimaler Ansatz besteht darin, ein Drittanbietertool zu finden, um vorhandene Dateien und Einstellungen dem neuen Profil zuzuordnen.

- Wenn das Gerät Gruppenrichtlinienobjekte (Group Policy Objects, GPO) verwendet, verfügen einige GPOs möglicherweise nicht über einen vergleichbaren [Configuration Service Provider](https://docs.microsoft.com/windows/configuration/provisioning-packages/how-it-pros-can-use-configuration-service-providers) (CSP) in InTune. Führen Sie das [FMAT-Tool](https://www.microsoft.com/download/details.aspx?id=45520) aus, um vergleichbare Kryptografiedienstanbieter für vorhandene GPOs zu finden.

- Benutzer können sich bei Anwendungen, die von der Active Directory Authentifizierung abhängen, nicht authentifizieren. Um dies zu bewältigen, verwenden Sie eine Legacy-APP, und aktualisieren Sie eine APP, die nach Möglichkeit moderne Authentifizierung verwendet.

- Die Active Directory Druckererkennung funktioniert nicht. Um dies zu beheben, stellen Sie direkte Druckerpfade für alle Benutzer bereit oder nutzen Sie den [Hybriden Cloud-Druck](https://docs.microsoft.com/windows-server/administration/hybrid-cloud-print/hybrid-cloud-print-deploy).
