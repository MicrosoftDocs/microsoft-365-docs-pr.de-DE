---
title: Einrichten der Verzeichnissynchronisierung für Microsoft 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/30/2020
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
f1.keywords:
- CSH
ms.custom: Adm_O365
ms.collection:
- Ent_O365
- M365-identity-device-management
search.appverid:
- MET150
- MOE150
- MED15
- MBS150
- BCS160
ms.assetid: 1b3b5318-6977-42ed-b5c7-96fa74b08846
description: Erfahren Sie, wie Sie die Verzeichnissynchronisierung zwischen Microsoft 365 und Ihrem lokalen Active Directory einrichten.
ms.openlocfilehash: 14b44523c0a560a71ed8dc9182f677f2ebc0b865
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/14/2021
ms.locfileid: "52926526"
---
# <a name="set-up-directory-synchronization-for-microsoft-365"></a>Einrichten der Verzeichnissynchronisierung für Microsoft 365

*Dieser Artikel gilt sowohl für Microsoft 365 Enterprise als auch für Office 365 Enterprise.*

Microsoft 365 verwendet einen Azure Active Directory (Azure AD)-Mandanten zum Speichern und Verwalten von Identitäten für die Authentifizierung und Berechtigungen für den Zugriff auf cloudbasierte Ressourcen. 

Wenn Sie über eine lokale Active Directory Domain Services (AD DS)-Domäne oder -Gesamtstruktur verfügen, können Sie Ihre AD DS-Benutzerkonten, -Gruppen und -Kontakte mit dem Azure AD-Mandanten Ihres Microsoft 365-Abonnements synchronisieren. Dies ist eine Hybrididentität für Microsoft 365. Dies sind ihre Komponenten.

![Komponenten der Verzeichnissynchronisierung für Microsoft 365](../media/about-microsoft-365-identity/hybrid-identity.png)

Azure AD Connect wird auf einem lokalen Server ausgeführt und synchronisiert Ihre AD DS mit dem Azure AD-Mandanten. Zusammen mit der Verzeichnissynchronisierung können Sie auch die folgenden Authentifizierungsoptionen angeben:

- Kennworthashsynchronisierung (Password hash synchronization, PHS)

  Azure AD führt die Authentifizierung selbst durch.

- Passthrough-Authentifizierung (PTA)

  Azure AD lässt AD DS die Authentifizierung durchführen.

- Verbundauthentifizierung

  Azure AD verweist den Clientcomputer, der die Authentifizierung anfordert, auf einen anderen Identitätsanbieter.

Weitere Informationen finden Sie unter [Hybrididentitäten](plan-for-directory-synchronization.md).
  
## <a name="1-review-prerequisites-for-azure-ad-connect"></a>1. Voraussetzungen für Azure AD Connect überprüfen

Sie erhalten ein kostenloses Azure AD-Abonnement mit Ihrem Microsoft 365-Abonnement. Wenn Sie die Verzeichnissynchronisierung einrichten, installieren Sie Azure AD Connect auf einem Ihrer lokalen Server.
  
Für Microsoft 365 müssen Sie:
  
- Ihre lokale Domäne hinzufügen. Der Azure AD Connect-Assistent führt Sie schrittweise durch diesen Vorgang.
- Rufen Sie die Benutzernamen und Kennwörter für die Administratorkonten Ihres Microsoft 365 Mandanten und AD DS ab.

Für Ihren lokalen Server, auf dem Sie Azure AD Connect installieren, benötigen Sie Folgendes:
  
|**Server-Betriebssystem**|**Weitere Software**|
|:-----|:-----|
|Windows Server 2012 R2 oder neuer | – PowerShell wird standardmäßig installiert, keine Aktion erforderlich.  <br> – .NET 4.5.1 und höhere Versionen werden über Windows Update bereitgestellt. Vergewissern Sie sich in der Systemsteuerung, dass die neuesten Updates für Windows Server installiert sind. |
|Windows Server 2008 R2 mit Service Pack 1 (SP1)** oder Windows Server 2012 | – Die neueste Version von PowerShell finden Sie im Windows Management Framework 4.0. Suchen Sie im [Microsoft Download Center](https://go.microsoft.com/fwlink/p/?LinkId=717996) danach.  <br> – .NET 4.5.1 und höhere Versionen finden Sie im [Microsoft Download Center](https://go.microsoft.com/fwlink/p/?LinkId=717996). |
|Windows Server 2008 | – Die neueste unterstützte Version von PowerShell befindet sich im Windows Management Framework 3.0, das Sie aus dem [Microsoft Download Center](https://go.microsoft.com/fwlink/p/?LinkId=717996) herunterladen können.  <br> – .NET 4.5.1 und höhere Versionen finden Sie im [Microsoft Download Center](https://go.microsoft.com/fwlink/p/?LinkId=717996). |

Zusätzliche Informationen zur Hardware, Software, Anforderungen an Konten, Berechtigungen und SSL Zertifikate sowie zu Objekteinschränkungen für Azure AD Connect finden Sie unter [Voraussetzungen für Azure Active Directory Connect](/azure/active-directory/hybrid/how-to-connect-install-prerequisites).
  
Sie können auch den [Versionsveröffentlichungsverlauf](/azure/active-directory/hybrid/reference-connect-version-history) von Azure AD Connect verfolgen, um zu sehen, welche Features und Funktionen in jeder Version enthalten sind und welche Fehler behoben wurden.

## <a name="2-install-azure-ad-connect-and-configure-directory-synchronization"></a>2. Installieren von Azure AD Connect und Konfigurieren der Verzeichnissynchronisierung

Bevor Sie beginnen, sollten Sie sicherstellen, dass Sie über Folgendes verfügen:

- Benutzername und Kennwort eines Microsoft 365 globalen Administrators
- Den Benutzernamen und das Kennwort des AD-DS-Domänenadministrators.
- Welche Authentifizierungsmethode (PHS, PTA, Federated)
- Ob Sie [Azure AD Seamless Single Sign-On (SSO) verwenden möchten](/azure/active-directory/hybrid/how-to-connect-sso)

Führen Sie die folgenden Schritte aus:

1. Melden Sie sich beim [Microsoft 365 Admin Center](https://admin.microsoft.com) an, (https://admin.microsoft.com) und wählen Sie im linken Navigationsbereich **Benutzer** \> **Aktive Benutzer** aus.
2. Wählen Sie auf der Seite **"Aktive Benutzer"** die Option **"Weitere** (drei Punkte) \> **Verzeichnissynchronisierung"** aus.
  
3. Wählen Sie auf der **Azure Active Directory Vorbereitungsseite** das Download center aus, um den Link zum Azure AD Verbinden Tool für die ersten Schritte zu **erhalten.** 
4. Folgen Sie den Schritten in [Installationsübersicht: Azure AD Connect und Azure AD Connect Health](/azure/active-directory/hybrid/how-to-connect-install-roadmap).

## <a name="3-finish-setting-up-domains"></a>3. Abschließen der Einrichtung von Domänen

Führen Sie die Schritte unter [Erstellen von DNS-Einträgen für Microsoft 365 aus, wenn Sie Ihre DNS-Einträge verwalten,](/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider) um die Einrichtung Ihrer Domänen abzuschließen.

## <a name="next-step"></a>Nächster Schritt

[Zuweisen von Lizenzen für Benutzerkonten](assign-licenses-to-user-accounts.md)