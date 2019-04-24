---
title: Zugreifen auf lokale Ressourcen über ein Azure AD-verbundenes Gerät in Microsoft 365 Business
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
ms.collection: M365-subscription-management
localization_priority: Normal
ms.custom:
- Core_O365Admin_Migration
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
ms.assetid: b0f4d010-9fd1-44d0-9d20-fabad2cdbab5
description: Hier erfahren Sie, wie Sie Zugriff auf lokale Ressourcen wie Branchen-apps, Dateifreigaben und Drucker aus einem Azure Active Directory, das Windows 10-Gerät hat, erhalten.
ms.openlocfilehash: 212685bc229f519152e69b09d0a745bfac7a38cd
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32276879"
---
# <a name="access-on-premises-resources-from-an-azure-ad-joined-device-in-microsoft-365-business"></a>Zugreifen auf lokale Ressourcen über ein Azure AD-verbundenes Gerät in Microsoft 365 Business

Jedes Windows 10-Gerät, das mit Azure Active Directory verbunden ist, hat Zugriff auf alle cloudbasierten Ressourcen wie Ihre Office 365-apps und kann von Microsoft 365 Business geschützt werden. Sie müssen Ihr lokales Active Directory mit Azure Active Directory mithilfe von [Azure AD Connect](https://docs.microsoft.com/en-us/azure/active-directory/connect/active-directory-aadconnect)synchronisieren, um auch den Zugriff auf lokale Ressourcen wie Branchen-apps, Dateifreigaben und Drucker zuzulassen. Weitere Informationen finden Sie unter [Einführung in die Geräteverwaltung in Azure Active Directory](https://docs.microsoft.com/en-us/azure/active-directory/device-management-introduction) . 
  
## <a name="run-azure-ad-connect"></a>Ausführen von Azure AD Connect

Führen Sie die folgenden Schritte aus, um den Zugriff ihrer Organisation für Azure AD-Geräte auf lokale Ressourcen zu ermöglichen.
  
1. Führen Sie den Assistenten für die Verzeichnissynchronisierung und Azure AD Connect wie unter [Einrichten der Verzeichnissynchronisierung für Office 365](https://support.office.com/article/1b3b5318-6977-42ed-b5c7-96fa74b08846)beschrieben aus, um Ihre Benutzer, Gruppen und Kontakte aus dem lokalen Active Directory in Azure Active Directory zu synchronisieren.
    
2. Stellen Sie nach Abschluss der Verzeichnissynchronisierung sicher, dass die Windows 10-Geräte Ihrer Organisation Azure AD beigetreten sind. Dieser Schritt wird auf jedem Windows 10-Gerät einzeln ausgeführt. Weitere Informationen finden Sie unter [Einrichten von Windows-Geräten für Microsoft 365 Business-Benutzer](set-up-windows-devices.md) . 
    
3. Sobald die Windows 10-Geräte mit Azure AD verbunden sind, sollten alle Benutzer ihre Geräte neu starten und sich mit Ihren Microsoft 365 Business-Anmeldeinformationen anmelden. Alle Geräte haben nun auch Zugriff auf lokale Ressourcen.
    
Es sind keine zusätzlichen Schritte erforderlich, um Zugriff auf lokale Ressourcen für mit Azure AD verbundene Geräte zu erhalten. Dies ist eine integrierte Funktionalität, die in Windows 10 verfügbar ist. 
  
Wenn Ihre Organisation nicht bereit ist, in der oben beschriebenen Azure AD-Gerätekonfiguration bereitzustellen, erwägen Sie die Einrichtung einer [hybridEn Azure AD-Gerätekonfiguration](manage-windows-devices.md).
  
### <a name="considerations-when-joining-your-windows-devices-to-azure-ad"></a>Überlegungen beim Hinzufügen Ihrer Windows-Geräte zu Azure AD

Wenn Sie Azure AD beitreten zu einem Windows-Gerät, das zuvor Domänenmitglied oder in einer Arbeitsgruppe war, müssen Sie die folgenden Einschränkungen berücksichtigen:
  
- Bei der Verknüpfung eines Device Azure AD wird ein neuer Benutzer erstellt, ohne auf ein vorhandenes Profil zu verweisen. Um dies zu beheben, müssen Profile manuell migriert werden. Ein Benutzerprofil enthält Informationen wie Favoriten, lokale Dateien, Browsereinstellungen, Startmenü-Einstellungen usw. Eine optimale Vorgehensweise besteht darin, ein Drittanbietertool zu finden, um vorhandene Dateien und Einstellungen dem neuen Profil zuzuordnen.
    
- Wenn das Gerät Gruppenrichtlinienobjekte (GPO) verwendet, verfügen einige GPOs möglicherweise nicht über einen vergleichbaren [Konfigurationsdienstanbieter](https://docs.microsoft.com/windows/configuration/provisioning-packages/how-it-pros-can-use-configuration-service-providers) (CSP) in InTune. Führen Sie das [FMAT-Tool](https://www.microsoft.com/download/details.aspx?id=45520) aus, um vergleichbare Kryptografiedienstanbieter für vorhandene GPOs zu finden. 
    
- Benutzer können sich nicht bei Anwendungen authentifizieren, die von der Active Directory-Authentifizierung abhängig sind. Um dieses Problem zu umgehen, verwenden Sie eine Legacy-APP und erwägen Sie, nach Möglichkeit eine APP zu aktualisieren, die moderne auth verwendet.
    
- Die Active Directory-Druckersuche funktioniert nicht. Um dies zu beheben, stellen Sie direkte Druckerpfade für alle Benutzer bereit, oder nutzen Sie den [hybridEn Cloud-Druck](https://docs.microsoft.com/windows-server/administration/hybrid-cloud-print/hybrid-cloud-print-deploy).
    

