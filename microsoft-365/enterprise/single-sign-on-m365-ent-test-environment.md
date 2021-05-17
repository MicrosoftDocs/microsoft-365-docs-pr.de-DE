---
title: Nahtloses einmaliges Anmelden in Azure AD für Ihre Microsoft 365-Testumgebung
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/21/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom:
- TLGS
- Ent_TLGs
ms.assetid: ''
description: 'Zusammenfassung: Konfigurieren und Testen des nahtlosen einmaliges Anmeldens in Azure AD für Ihre Microsoft 365-Testumgebung.'
ms.openlocfilehash: 7fcbc82cfb35c598358c8160dd06427c2a9c59a2
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50904864"
---
# <a name="azure-ad-seamless-single-sign-on-for-your-microsoft-365-test-environment"></a>Nahtloses einmaliges Anmelden in Azure AD für Ihre Microsoft 365-Testumgebung

*Diese Testumgebungsanleitung kann sowohl für Microsoft 365 als auch für Office 365 Enterprise verwendet werden.*

Azure AD Seamless Single Sign-On (Seamless SSO) meldet sich automatisch bei Benutzern an, wenn sie sich auf ihren PCs oder Geräten befinden, die mit ihrem Organisationsnetzwerk verbunden sind. Azure AD Seamless SSO bietet Benutzern einfachen Zugriff auf cloudbasierte Anwendungen, ohne dass zusätzliche lokale Komponenten benötigt werden.

In diesem Artikel wird beschrieben, wie Sie Microsoft 365 Testumgebung für Azure AD Seamless SSO konfigurieren.

Das Einrichten von nahtlosen Azure AD-SSO umfasst zwei Phasen:
- [Phase 1: Konfigurieren Sie Kennworthashsynchronisierung für Ihre Microsoft 365-Testumgebung](#phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment)
- [Phase 2: Konfigurieren Sie Azure AD Connect auf APP1 für das nahtlose einmalige Anmelden in Azure AD.](#phase-2-configure-azure-ad-connect-on-app1-for-azure-ad-seamless-sso)
   
![Testumgebungsanleitungen für die Microsoft-Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> Eine visuelle Karte zu allen Artikeln im Stapel Microsoft 365 test lab guide für unternehmen finden Sie unter [Microsoft 365 for enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).
  
## <a name="phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment"></a>Phase 1: Konfigurieren Sie Kennworthashsynchronisierung für Ihre Microsoft 365-Testumgebung

Befolgen Sie die Anweisungen unter [Kennworthashsynchronisierung für Microsoft 365.](password-hash-sync-m365-ent-test-environment.md) 

Die resultierende Konfiguration sieht wie die folgenden aus:
  
![Das simulierte Unternehmen mit Kennworthashsynchronisierung für die Testumgebung](../media/pass-through-auth-m365-ent-test-environment/Phase1.png)
  
Diese Konfiguration besteht aus: 
  
- Eine Testversion oder ein kostenpflichtiges Abonnement für Microsoft 365 E5.
- Ein vereinfachtes Unternehmensintranet, das mit dem Internet verbunden ist und aus den virtuellen Computern DC1, APP1 und CLIENT1 in einem Subnetz eines virtuellen Azure-Netzwerks besteht.
- Azure AD Verbinden wird auf APP1 ausgeführt, um die Active Directory Domain Services (AD DS)-Domäne testlab regelmäßig mit dem Azure AD-Mandanten Ihres Microsoft 365 synchronisieren.

## <a name="phase-2-configure-azure-ad-connect-on-app1-for-azure-ad-seamless-sso"></a>Phase 2: Konfigurieren Sie Azure AD Connect auf APP1 für das nahtlose einmalige Anmelden in Azure AD.

Konfigurieren Sie in dieser Phase Azure AD Verbinden app1 für Azure AD Seamless SSO, und überprüfen Sie dann, ob es funktioniert.

### <a name="configure-azure-ad-connect-on-app1"></a>Konfigurieren von Azure AD Connect auf APP1

1. Melden Sie sich über das [Azure-Portal](https://portal.azure.com) mit Ihrem globalen Administratorkonto an, und stellen Sie dann mit dem Konto „TESTLAB\User1“ eine Verbindung zu APP1 her.

2. Führen Sie auf dem APP1-Desktop Azure AD Verbinden.

3. Wählen Sie **auf der Seite Willkommen** die Option Konfigurieren **aus.**

4. Wählen Sie **auf der** Seite Zusätzliche Aufgaben die Option **Benutzeranmelden ändern** aus, und wählen Sie dann Weiter **aus.**

5. Geben Sie **Verbinden Azure AD** ein, und wählen Sie dann **Weiter** aus.

6. Wählen Sie **auf der Seite Benutzeranmelden** die Option **Einmaliges Anmelden aktivieren** aus, und wählen Sie dann Weiter **aus.**

7. Wählen Sie **auf der Seite Einmaliges Anmelden** aktivieren die Option **Anmeldeinformationen eingeben aus.**

8. Geben Sie **Windows-Sicherheit** **benutzer1** und das Kennwort des Benutzerkontos ein, wählen Sie **OK** aus, und wählen Sie dann **Weiter aus.**

9. Wählen Sie **auf der Seite Bereit** zum Konfigurieren die Option Konfigurieren **aus.**

10. Wählen Sie **auf der Seite Konfiguration abgeschlossen** die Option Beenden **aus.**

11. Wählen Sie im Azure-Portal im linken Bereich die **option Azure Active Directory** Azure  >  **AD Verbinden**. Stellen Sie **sicher,** dass das Feature Für einmaliges Anmelden nahtlos als **Aktiviert angezeigt wird.**

Testen Sie als Nächstes die Möglichkeit, sich bei Ihrem Abonnement mit dem <strong>user1@testlab.</strong>\<*your public domain*> Benutzername des User1-Kontos.

1. Wählen Sie in Internet Explorer auf APP1 das Einstellungssymbol aus, und wählen Sie **dann Internetoptionen aus.**
 
2. Wählen **Sie unter Internetoptionen** die Registerkarte **Sicherheit** aus.

3. Wählen **Sie Lokales Intranet** aus, und wählen Sie dann Websites **aus.**

4. Wählen **Sie im lokalen Intranet** erweitert **aus.**

5. Geben Sie unter Diese **Website zur Zone hinzufügen** https **<span>://</span>autologon.microsoftazuread-sso.com** ein, wählen Sie **Schließen**  >    >  **schließen**  >  **OK hinzufügen OK aus.**

6. Melden Sie sich ab, und melden Sie sich dann erneut an. Geben Sie dieses Mal ein anderes Konto an.

7. Wenn Sie zur Anmeldung aufgefordert werden, geben Sie <strong>user1@testlab.</strong>\<*your public domain*> name, und wählen Sie dann **Weiter aus.** Sie sollten sich erfolgreich als "User1" anmelden können, ohne zur Eingabe eines Kennworts aufgefordert zu werden. Dies beweist, dass das nahtlose einmalige Anmelden mit Azure AD funktioniert.

Beachten Sie, dass "User1" zwar über Administratorberechtigungen für die AD DS-Domäne TESTLAB verfügt, er aber kein globaler Administrator für Azure AD ist. Daher wird das Symbol **Admin** nicht als Option angezeigt.

Nachfolgend sehen Sie die daraus resultierende Konfiguration:

![Das simulierte Unternehmen mit einer Testumgebung mit Pass-Trought-Authentifizierung](../media/pass-through-auth-m365-ent-test-environment/Phase1.png)

Diese Konfiguration besteht aus: 

- Eine Microsoft 365 E5 oder kostenpflichtige Abonnements mit dem TESTlab der DNS-Domäne.\<*your domain name*> registriert.
- Ein vereinfachtes Unternehmensintranet, das mit dem Internet verbunden ist und aus den virtuellen Computern DC1, APP1 und CLIENT1 in einem Subnetz eines virtuellen Azure-Netzwerks besteht.
- Azure AD Connect wird auf APP1 ausgeführt, um die Liste von Konten und Gruppen des Azure AD-Mandanten Ihrer Microsoft 365-Abonnements mit der AD DS-Domäne „TESTLAB“ zu synchronisieren.
- Azure AD Seamless SSO ist aktiviert, damit sich Computer im simulierten Intranet bei Microsoft 365 anmelden können, ohne ein Benutzerkontokennwort anzugeben.

## <a name="next-step"></a>Nächster Schritt

Sehen Sie sich weitere [Identitäts](m365-enterprise-test-lab-guides.md#identity)features und- funktionen in Ihrer Testumgebung an.

## <a name="see-also"></a>Siehe auch

[Testumgebungsanleitungen für Microsoft 365 Enterprise](m365-enterprise-test-lab-guides.md)

[Übersicht über Microsoft 365 Enterprise](microsoft-365-overview.md)

[Dokumentation zu Microsoft 365 Enterprise](/microsoft-365-enterprise/)