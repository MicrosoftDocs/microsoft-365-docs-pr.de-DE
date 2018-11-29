---
title: Zugriff auf lokale Ressourcen von einem Azure AD gehörenden Gerät in Microsoft 365 Business
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.custom:
- Core_O365Admin_Migration
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
ms.assetid: b0f4d010-9fd1-44d0-9d20-fabad2cdbab5
description: Erfahren Sie, wie erhalten Sie Zugriff auf lokale Ressourcen, wie Line Of Business-apps, Dateifreigaben und Drucker von Azure Active Directory Windows 10 Gerät verbunden.
ms.openlocfilehash: 0a5d4b0828888fcb99676223000c446479f84ddc
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/28/2018
ms.locfileid: "26867586"
---
# <a name="access-on-premises-resources-from-an-azure-ad-joined-device-in-microsoft-365-business"></a>Zugriff auf lokale Ressourcen von einem Azure AD gehörenden Gerät in Microsoft 365 Business

Alle Windows 10-Geräte, die Azure Active Directory verbunden ist haben Zugriff auf alle cloudbasierte Ressourcen wie Ihre apps für Office 365 und kann von Microsoft 365 Business geschützt werden. Um den Zugriff auf lokale Ressourcen wie Zeile des Business (LOB) apps, Dateifreigaben und Drucker zu ermöglichen, müssen Sie Ihre lokale Active Directory mithilfe von [Azure Active Directory verbinden](https://docs.microsoft.com/en-us/azure/active-directory/connect/active-directory-aadconnect)mit Azure Active Directory synchronisieren. Finden Sie unter [Einführung in die Verwaltung von Geräten in Azure Active Directory](https://docs.microsoft.com/en-us/azure/active-directory/device-management-introduction) , um mehr zu erfahren. 
  
## <a name="run-azure-ad-connect"></a>Ausführen von Azure Active Directory verbinden

Gehen Sie folgendermaßen vor, um beigetreten Azure AD-Geräte für den Zugriff auf lokale Ressourcen auf Ihrer Organisation zu aktivieren.
  
1. Führen Sie zum Synchronisieren der Benutzer, Gruppen und Kontakte aus der lokalen Active Directory in Azure Active Directory-Assistenten für die-Synchronisierung, und Azure Active Directory verbinden als in [Einrichten von verzeichnissynchronisierung für Office 365](https://support.office.com/article/1b3b5318-6977-42ed-b5c7-96fa74b08846)beschrieben.
    
2. Nach Abschluss die verzeichnissynchronisierung, stellen Sie sicher, dass Ihre Organisation Windows 10 Geräte Azure AD verbunden sind. Dieser Schritt ist auf jedem Gerät Windows 10 einzeln ausgeführt. Einzelheiten finden Sie unter [Einrichten von Windows-Geräte für Microsoft 365 Geschäftsbenutzer](set-up-windows-devices.md) . 
    
3. Nachdem die Geräte 10 für Windows Azure AD verbunden sind, sollte jeder Benutzer ihre Geräte und melden Sie sich mit den Anmeldeinformationen ihres Microsoft 365 Business neu starten. Alle Geräte werden nun auf sowie auf lokale Ressourcen zugreifen.
    
Es sind keine zusätzliche Schritte erforderlich Zugriff auf lokale, dass Ressourcen für Azure AD Geräte verbunden. Dies ist die integrierte Funktionalität in Windows 10 verfügbar. 
  
Wenn Ihre Organisation nicht zum Bereitstellen von in Azure AD beigetreten Gerätekonfiguration oben beschriebenen bereit ist, sollten Sie einrichten [Hybrid Azure AD beigetreten Gerätekonfiguration](manage-windows-devices.md).
  
### <a name="considerations-when-joining-your-windows-devices-to-azure-ad"></a>Aspekte beim Beitritt Ihre Geräte Windows Azure AD

Wenn Sie die Teilnahme an einer Windows-Gerät, die zuvor in die Domäne eingebundener wurde Azure AD sind oder in einer Arbeitsgruppe, müssen Sie die folgenden Nachteile beachten:
  
- Wenn ein Gerät Azure AD beigetreten ist, erstellt es einen neuen Benutzer ohne verweisen auf ein vorhandenes Profil. Um dieses Problem zu beheben, müssen Profile manuell migriert werden müssen. Ein Benutzerprofil enthält Informationen wie Favoriten, lokale Dateien, Browsereinstellungen, Start im Menü Einstellungen usw.. Ein bewährte Ansatz besteht darin, ein Drittanbieter-Tool Zuordnen von vorhandenen Dateien und Einstellungen zu dem neuen Profil suchen
    
- Wenn das Gerät (Group Policy Objects, GPOs) verwendet wird, möglicherweise einige Gruppenrichtlinienobjekte eine vergleichbare [Konfiguration-Dienstanbieter](https://docs.microsoft.com/windows/configuration/provisioning-packages/how-it-pros-can-use-configuration-service-providers) (CSP) nicht in Intune. Führen Sie das [Tool MMAT](https://www.microsoft.com/download/details.aspx?id=45520) vergleichbare Kryptografiedienstanbieter für vorhandene Gruppenrichtlinienobjekte zu finden. 
    
- Benutzer werden nicht authentifiziert für Clientanwendungen, die von Active Directory-Authentifizierung abhängen. Für den Umgang mit dadurch auswerten mit einer Vorversion app und erwägen Sie eine Aktualisierung zu einer app, die moderne Auth möglichst verwendet.
    
- Active Directory Drucker Discovery funktioniert nicht. Um dieses Problem zu beheben, bieten Sie direkte Druckerpfade für alle Benutzer oder nutzen Sie [Hybrid Cloud drucken](https://docs.microsoft.com/windows-server/administration/hybrid-cloud-print/hybrid-cloud-print-deploy).
    

