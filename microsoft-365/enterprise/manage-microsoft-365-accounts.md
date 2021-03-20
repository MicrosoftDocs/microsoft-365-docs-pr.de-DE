---
title: Verwalten von Microsoft 365-Benutzerkonten
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: overview
ms.prod: office-online-server
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-mar2020
ms.collection:
- Ent_O365
- M365-subscription-management
search.appverid:
- MET150
- MOE150
- MED150
- BCS160
ms.assetid: 98ca5b3f-f720-4d8e-91be-fe656548a25a
description: Erfahren Sie, wie Sie Microsoft 365-Benutzerkonten verwalten.
ms.openlocfilehash: c0387bf50228e0eeb763b4807b15c8d57e02eeac
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50909562"
---
# <a name="manage-microsoft-365-user-accounts"></a>Verwalten von Microsoft 365-Benutzerkonten

Je nach Konfiguration können Sie Microsoft 365-Benutzerkonten auf verschiedene Weise verwalten. Sie können Benutzerkonten im [Microsoft 365 Admin Center](../admin/add-users/index.yml), [PowerShell](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md), in Active Directory Domain Services (AD DS) oder im Azure Active Directory (Azure AD) Admin Portal verwalten. 

Sobald Sie Microsoft 365 erwerben, können das Microsoft 365 Admin Center und PowerShell zum Verwalten von Konten verwendet werden. Bei der Verwaltung von Cloudidentitäten verfügt jede Person in Ihrer Organisation über einen separaten Benutzernamen und ein kennwort. Wenn Sie sich in Ihre lokale Infrastruktur integrieren und Benutzerkonten mit Microsoft 365 synchronisieren möchten, können Sie Azure AD Connect verwenden, um die Synchronisierung von Identitäten und Kennwörtern für die Funktion für einmaliges Anmelden (Single Sign-On, SSO) bereitzustellen.
  
## <a name="plan-for-where-and-how-you-will-manage-your-user-accounts"></a>Planen, wo und wie Sie Ihre Benutzerkonten verwalten

Wo und wie Sie Ihre Benutzerkonten verwalten können, hängt vom Identitätsmodell ab, das Sie für Microsoft 365 verwenden möchten. Die beiden Gesamtmodelle sind nur cloudbasierte und hybride Modelle.
  
### <a name="cloud-only"></a>Rein cloudbasiert

Sie erstellen und verwalten Benutzer im Microsoft 365 Admin Center. Sie können auch PowerShell oder das Azure AD Admin Center verwenden. 
    
### <a name="hybrid"></a>Hybrid

Benutzerkonten werden von AD DS mit Microsoft 365 synchronisiert, daher müssen Sie lokale AD DS-Tools zum Verwalten von Benutzerkonten verwenden. 
    
## <a name="managing-accounts"></a>Verwalten von Konten

Berücksichtigen Sie bei der Entscheidung, auf welche Weise Ihre Organisation Konten erstellt und verwaltet, die folgenden Anforderungen:
  
- Die Verzeichnissynchronisierungssoftware muss auf Servern in Ihrer lokalen Umgebung installiert werden, um die Identitäten zwischen Microsoft 365 und Ihrem AD DS zu verbinden.
    
- Jede Verzeichnissynchronisierungsoption, einschließlich der SSO-Optionen, erfordert, dass Ihre AD DS-Attribute den Standards entsprechen. Die Spezifischen der attribute, die in Ihrem Verzeichnis verwendet werden und welche Bereinigung (falls vorhanden) erforderlich ist, werden unter [Prepare for directory synchronization to Microsoft 365 beschrieben.](prepare-for-directory-synchronization.md) 
    
- Planen Sie, wie Sie Microsoft 365-Konten erstellen.
    
In der folgenden Tabelle sind die verschiedenen Kontoverwaltungstools aufgeführt.
    
|Tool|Notizen|
|:-----|:-----|
|Microsoft 365 Admin Center  <br/> |[Hinzufügen von Benutzern einzeln oder in Massen](../admin/add-users/add-users.md) <br/>  Stellt eine einfache Webschnittstelle zum Hinzufügen und Ändern von Benutzerkonten bereit.  <br/>  Kann nicht verwendet werden, um Benutzer zu ändern, wenn die Verzeichnissynchronisierung aktiviert ist (Speicherort und Lizenzzuweisung können festgelegt werden).  <br/>  Kann nicht mit SSO-Optionen verwendet werden.  <br/> |
|Windows PowerShell  <br/> |[Verwalten von Microsoft 365 mit Windows PowerShell](./manage-microsoft-365-with-microsoft-365-powershell.md) <br/>  Ermöglicht das Hinzufügen von Benutzern in Massenbenutzern mithilfe eines Windows PowerShell Skripts.  <br/>  Kann zum Zuweisen von Speicherorten und Lizenzen zu Konten verwendet werden, unabhängig davon, wie die Konten erstellt werden.  <br/> |
|Massenimport  <br/> |[Gleichzeitiges Hinzufügen von mehreren Benutzern](add-several-users-at-the-same-time.md) <br/>  Ermöglicht das Importieren einer CSV-Datei zum Hinzufügen einer Gruppe von Benutzern zu Microsoft 365.  <br/>  Kann nicht mit SSO-Optionen verwendet werden.  <br/> |
|Azure AD  <br/> |Sie erhalten eine kostenlose Version von Azure AD mit Ihrem Microsoft 365-Abonnement. Sie können Funktionen wie die Self-Service-Kennwortzurücksetzung für Cloudbenutzer und die Anpassung der Anmelde- und Zugriffssteuerungsseiten mithilfe der kostenlosen Edition ausführen. Um erweiterte Funktionen zu erhalten, können Sie ein Upgrade auf die Basisversion, Azure AD Premium P1 oder Azure AD Premium P2 durchführen. Eine [Liste der unterstützten](/azure/active-directory/fundamentals/active-directory-whatis) Features finden Sie unter Azure AD-Editionen.  <br/> |
|Verzeichnissynchronisierung  <br/> |[Integrieren Ihrer lokalen Identitäten in Azure AD](/azure/active-directory/hybrid/whatis-hybrid-identity) <br/>  Verwenden Sie für die Verzeichnissynchronisierung mit oder ohne Kennwortsynchronisierung [Azure AD Connect mit Expresseinstellungen.](/azure/active-directory/hybrid/how-to-connect-install-express)  <br/>  Verwenden Sie für mehrere Gesamtstrukturen und [SSO-Optionen](/azure/active-directory/hybrid/how-to-connect-install-custom)die benutzerdefinierte Installation von Azure AD Connect .  <br/>  Stellt die Infrastruktur zur Verfügung, die zum Aktivieren von SSO erforderlich ist.  <br/>  Erforderlich für viele Hybridszenarien, z. B. mehrstufige Migration und Hybrid-Exchange  <br/>  Synchronisiert Sicherheits- und E-Mail-aktivierte Gruppen aus Ihrem AD DS.  <br/> |
|||
   
- Unabhängig davon, wie Sie die Benutzerkonten zu Microsoft 365 hinzufügen möchten, müssen Sie mehrere Kontofeatures verwalten, z. B. zuweisen von Lizenzen, Angeben des Speicherorts und so weiter. Diese Features können langfristig über das Microsoft 365 Admin Center verwaltet werden, oder Sie können auch Benutzerkonten [mit PowerShell erstellen.](./create-user-accounts-with-microsoft-365-powershell.md)
    
    Wenn Sie alle Benutzer über das Admin Center hinzufügen und verwalten möchten, geben Sie den Speicherort an und weisen lizenzen gleichzeitig mit dem Erstellen des Microsoft 365-Kontos zu. Aus diesem Grund ist nicht viel Planung erforderlich.
    
    > [!IMPORTANT]
    > Das Erstellen von Konten in Microsoft 365 ohne Zuweisen einer Lizenz (z. B. sharePoint Online) bedeutet, dass der Kontobesitzer das Microsoft 365 Center anzeigen kann, aber nicht auf die Dienste im Abonnement Ihres Unternehmens zugreifen kann. Nachdem Sie einen Standort und die Lizenz zugewiesen haben, wird das Konto auf den von Ihnen zugewiesenen Dienst oder Dienste repliziert. Der Benutzer kann sich bei ihrem Konto anmelden und die ihm zugewiesenen Dienste nutzen. 
  
## <a name="see-also"></a>Siehe auch

[Microsoft 365 Admin Center](../admin/add-users/index.yml)

[PowerShell](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)