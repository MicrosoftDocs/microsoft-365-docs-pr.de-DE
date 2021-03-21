---
title: Microsoft 365-Integration in lokale Umgebungen
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
ms.collection:
- Ent_O365
search.appverid:
- MET150
- LYN150
- SPS150
- MOE150
- MED150
ms.assetid: 263faf8d-aa21-428b-aed3-2021837a4b65
description: In diesem Artikel erfahren Sie, wie Sie Microsoft 365 in Ihre vorhandenen Verzeichnisdienste und lokalen Umgebungen integrieren.
ms.openlocfilehash: c0453b7685254ccbbb301a17749fe48549fae78d
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50923966"
---
# <a name="microsoft-365-integration-with-on-premises-environments"></a>Microsoft 365-Integration in lokale Umgebungen

*Dieser Artikel gilt sowohl für Microsoft 365 Enterprise als auch für Office 365 Enterprise.*

Sie können Microsoft 365 in Ihre vorhandenen lokalen Active Directory Domain Services (AD DS) und in lokale Installationen von Exchange Server, Skype for Business Server 2015 oder SharePoint Server integrieren.
  
 - Wenn Sie AD DS integrieren, können Sie Benutzerkonten für beide Umgebungen synchronisieren und verwalten. Sie können auch die Kennworthashsynchronisierung (Password Hash Synchronization, PHS) oder einmaliges Anmelden (Single Sign-On, SSO) hinzufügen, damit sich Benutzer mit ihren lokalen Anmeldeinformationen bei beiden Umgebungen anmelden können.
 - Bei der Integration in lokale Serverprodukte erstellen Sie eine Hybridumgebung. Eine Hybridumgebung kann beim Migrieren von Benutzern oder Informationen zu Microsoft 365 hilfreich sein, oder Sie können weiterhin einige Benutzer oder einige Informationen lokal und einige in der Cloud haben. Weitere Informationen zu Hybridumgebungen finden Sie unter [Hybrid Cloud](../solutions/cloud-architecture-models.md#hybrid).

Sie können auch die Azure Active Directory (Azure AD)-Berater für benutzerdefinierte Setupanleitungen im Microsoft 365 Admin Center verwenden (Sie müssen bei Microsoft 365 angemeldet sein):

- [Azure AD-Einrichtungshandbuch](https://aka.ms/aadpguidance)
- [Synchronisieren von Benutzern aus dem Verzeichnis Ihrer Organisation](https://aka.ms/aadconnectpwsync)
- [Bereitstellungsratgeber für Active Directory Federation Services (AD FS)](https://aka.ms/adfsguidance)
   
## <a name="before-you-begin"></a>Bevor Sie beginnen

Bevor Sie Microsoft 365 und eine lokale Umgebung integrieren, müssen Sie auch die Netzwerkplanung und [Leistungsoptimierung tun.](network-planning-and-performance.md) Außerdem ist es wichtig, dass Sie die verfügbaren [Identitätsmodelle](about-microsoft-365-identity.md) verstehen. 

Eine Liste der Tools zum Verwalten von [Microsoft 365-Benutzerkonten](manage-microsoft-365-accounts.md) finden Sie unter Verwalten von Microsoft 365-Konten. 
  
## <a name="integrate-microsoft-365-with-ad-ds"></a>Integrieren von Microsoft 365 in AD DS

Wenn Sie über vorhandene Benutzerkonten in AD DS verfügen, möchten Sie nicht alle diese Konten in Microsoft 365 neu erstellen und riskieren Unterschiede oder Fehler zwischen den Umgebungen. Mit der Verzeichnissynchronisierung können Sie diese Konten zwischen Ihren lokalen und Onlineumgebungen spiegeln. Bei der Verzeichnissynchronisierung müssen sich die Benutzer nicht neue Informationen zu jeder Umgebung merken, und Sie brauchen die Konten nicht zweimal zu erstellen oder zu aktualisieren. Sie müssen Ihr [lokales](prepare-for-directory-synchronization.md) Verzeichnis für die Verzeichnissynchronisierung vorbereiten.
  
![Mit Verzeichnissynchronisierung sorgen Sie dafür, dass die Informationen für lokale und Online-Benutzerkonten synchronisiert bleiben.](../media/microsoft-365-integration/directory-synchronization.png)
  
Wenn Sich Benutzer mit ihren lokalen Anmeldeinformationen bei Microsoft 365 anmelden können sollen, können Sie auch SSO konfigurieren. Mit SSO ist Microsoft 365 so konfiguriert, dass er der lokalen Umgebung für die Benutzerauthentifizierung vertraut.
  
![Bei der einmaligen Anmeldung steht dasselbe Konto in der lokalen und der Onlineumgebung zur Verfügung.](../media/microsoft-365-integration/single-sign-on.png)

### <a name="directory-synchronization-with-or-without-password-hash-synchronization-or-pass-through-authentication-pta"></a>Verzeichnissynchronisierung mit oder ohne Kennworthashsynchronisierung oder Pass-Through-Authentifizierung (PTA)

Ein Benutzer meldet sich mit seinem Benutzerkonto (domäne\benutzername) bei seiner lokalen Umgebung an. Wenn sie zu Microsoft 365 wechseln, müssen sie sich erneut mit ihrem Arbeits- oder Schulkonto (user@domain.com) anmelden. Der Benutzername ist in beiden Umgebungen identisch. Wenn Sie PHS oder PTA hinzufügen, hat der Benutzer dasselbe Kennwort für beide Umgebungen, muss diese Anmeldeinformationen jedoch bei der Anmeldung bei Microsoft 365 erneut angeben. Die Verzeichnissynchronisierung mit PHS ist die am häufigsten verwendete Verzeichnissynchronisierung.

Verwenden Sie Azure AD Connect, um die Verzeichnissynchronisierung einrichten. Anweisungen finden Sie unter [Einrichten der Verzeichnissynchronisierung für Microsoft 365](set-up-directory-synchronization.md) und [Azure AD Connect mit Expresseinstellungen.](/azure/active-directory/hybrid/how-to-connect-install-express)

Erfahren Sie mehr [über die Vorbereitung der Verzeichnissynchronisierung mit Microsoft 365](prepare-for-directory-synchronization.md).

### <a name="directory-synchronization-with-sso"></a>Verzeichnissynchronisierung mit SSO

Ein Benutzer meldet sich mit seinem Benutzerkonto bei seiner lokalen Umgebung an. Wenn sie zu Microsoft 365 wechseln, werden sie entweder automatisch angemeldet, oder sie melden sich mit denselben Anmeldeinformationen an, die sie für ihre lokale Umgebung verwenden (Domäne\Benutzername).

Zum Einrichten von SSO verwenden Sie ebenfalls Azure Active Directory Connect. Anweisungen finden Sie unter [Benutzerdefinierte Installation von Azure AD Connect](/azure/active-directory/hybrid/how-to-connect-install-custom).

Weitere Informationen finden Sie unter [Einmaliges Anmelden](/azure/active-directory/manage-apps/what-is-single-sign-on).

## <a name="azure-ad-connect"></a>Azure AD Connect

Azure AD Connect ersetzt ältere Versionen von Identitätsintegrationstools wie DirSync und Azure AD Sync. Wenn Sie von Azure Active Directory Sync auf Azure AD Connect aktualisieren möchten, lesen Sie [die Upgradeanweisungen](/azure/active-directory/hybrid/how-to-dirsync-upgrade-get-started). 

## <a name="see-also"></a>Siehe auch

[Übersicht zu Microsoft 365 Enterprise](microsoft-365-overview.md)