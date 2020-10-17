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
ms.openlocfilehash: f98f82de50feb2a9f92d1ecc4775c5307b314a72
ms.sourcegitcommit: 53ff1fe6d6143b0bf011031eea9b85dc01ae4f74
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48487600"
---
# <a name="azure-ad-seamless-single-sign-on-for-your-microsoft-365-test-environment"></a>Nahtloses einmaliges Anmelden in Azure AD für Ihre Microsoft 365-Testumgebung

*Diese Test Umgebungs Anleitung kann sowohl für Microsoft 365 für Unternehmen als auch für Office 365 Enterprise Testumgebungen verwendet werden.*

Azure AD nahtlose Einzel Sign-On (Seamless SSO) automatisch Benutzer, wenn Sie sich auf ihren PCs oder Geräten befinden, die mit Ihrem Organisationsnetzwerk verbunden sind. Azure AD nahtloses SSO bietet Benutzern einfachen Zugriff auf Cloud-basierte Anwendungen, ohne dass zusätzliche lokale Komponenten erforderlich sind.

In diesem Artikel wird beschrieben, wie Sie Ihre Microsoft 365-Testumgebung für Azure AD nahtloses SSO konfigurieren.

Das Einrichten Azure AD nahtlosen SSO umfasst zwei Phasen:
- [Phase 1: Konfigurieren Sie Kennworthashsynchronisierung für Ihre Microsoft 365-Testumgebung](#phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment)
- [Phase 2: Konfigurieren Sie Azure AD Connect auf APP1 für das nahtlose einmalige Anmelden in Azure AD.](#phase-2-configure-azure-ad-connect-on-app1-for-azure-ad-seamless-sso)
   
![Testumgebungsanleitungen für die Microsoft-Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> Eine visuelle Zuordnung zu allen Artikeln im Microsoft 365 for Enterprise Test Lab Guide Stack finden Sie unter [Microsoft 365 for Enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).
  
## <a name="phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment"></a>Phase 1: Konfigurieren Sie Kennworthashsynchronisierung für Ihre Microsoft 365-Testumgebung

Befolgen Sie die Anweisungen unter [Kennworthash Synchronisierung für Microsoft 365](password-hash-sync-m365-ent-test-environment.md). 

Die resultierende Konfiguration sieht wie folgt aus:
  
![Das simulierte Unternehmen mit Kennworthashsynchronisierung für die Testumgebung](../media/pass-through-auth-m365-ent-test-environment/Phase1.png)
  
Diese Konfiguration besteht aus: 
  
- Eine Testversion oder ein kostenpflichtiges Abonnement für Microsoft 365 E5.
- Ein vereinfachtes Organisationsintranet, das mit dem Internet verbunden ist, das aus den virtuellen Computern DC1, App1 und CLIENT1 in einem Subnetz eines virtuellen Azure-Netzwerks besteht.
- Azure AD Connect wird auf App1 ausgeführt, um die TESTLAB Active Directory-Domänendienste (AD DS) Domäne regelmäßig mit dem Azure AD Mandanten Ihres Microsoft 365-Abonnements zu synchronisieren.

## <a name="phase-2-configure-azure-ad-connect-on-app1-for-azure-ad-seamless-sso"></a>Phase 2: Konfigurieren Sie Azure AD Connect auf APP1 für das nahtlose einmalige Anmelden in Azure AD.

Konfigurieren Sie in dieser Phase Azure AD Connect on App1 für Azure AD nahtloses SSO, und überprüfen Sie dann, ob es funktioniert.

### <a name="configure-azure-ad-connect-on-app1"></a>Konfigurieren von Azure AD Connect auf APP1

1. Melden Sie sich über das [Azure-Portal](https://portal.azure.com) mit Ihrem globalen Administratorkonto an, und stellen Sie dann mit dem Konto „TESTLAB\User1“ eine Verbindung zu APP1 her.

2. Führen Sie auf dem App1-Desktop Azure AD Connect aus.

3. Wählen Sie auf der **Willkommensseite** **configure**aus.

4. Wählen Sie auf der Seite **Weitere Aufgaben** die Option **Benutzeranmeldung ändern**aus, und wählen Sie dann **weiter**aus.

5. Geben Sie auf der Seite mit **Azure AD verbinden** die Anmeldeinformationen des globalen Administratorkontos ein, und wählen Sie dann **weiter**aus.

6. Wählen Sie auf der Seite **Benutzeranmeldung** die Option **einmaliges Anmelden aktivieren**aus, und wählen Sie dann **weiter**aus.

7. Wählen Sie auf der Seite **einmaliges Anmelden aktivieren** die Option **Anmeldeinformationen eingeben**aus.

8. Geben Sie im Dialogfeld **Windows** -Sicherheit **User1** und das Kennwort des user1-Kontos ein, klicken Sie auf **OK**, und wählen Sie dann **weiter**aus.

9. Wählen Sie auf der Seite " **vorbereiten zur Konfiguration** " die Option **configure**aus.

10. Wählen Sie auf der Seite **Konfiguration abgeschlossen** die Option **Beenden**aus.

11. Wählen Sie im Azure-Portal im linken Bereich **Azure Active Directory**  >  **Azure AD Connect**aus. Stellen Sie sicher, dass das **nahtlose Feature für einmaliges Anmelden** als **aktiviert**angezeigt wird.

Testen Sie als nächstes die Möglichkeit, sich mit dem user1@testlab bei Ihrem Abonnement anzumelden <strong>.</strong>\<*your public domain*> Benutzername des User1-Kontos.

1. Wählen Sie unter Internet Explorer auf App1 das Symbol Einstellungen aus, und wählen Sie dann **Internet Optionen**aus.
 
2. Wählen Sie unter **Internet Optionen**die Registerkarte **Sicherheit** aus.

3. Wählen Sie **Lokales Intranet**aus, und wählen Sie dann **Sites**aus.

4. Wählen Sie im **lokalen Intranet**die Option **erweitert**aus.

5. Geben Sie unter **diese Website zur Zone hinzufügen die**Option **https<span>://</span>Autologon.microsoftazuread-SSO.com**ein, und **Wählen Sie**  >  **Schließen**  >  **OK**  >  **OK**aus.

6. Melden Sie sich ab, und melden Sie sich dann erneut an. Geben Sie dieses Mal ein anderes Konto an.

7. Wenn Sie zur Anmeldung aufgefordert werden, geben Sie <strong>User1@testlab an.</strong>\<*your public domain*> Name, und wählen Sie dann **weiter**aus. Sie sollten sich erfolgreich als "User1" anmelden können, ohne zur Eingabe eines Kennworts aufgefordert zu werden. Dies beweist, dass das nahtlose einmalige Anmelden mit Azure AD funktioniert.

Beachten Sie, dass "User1" zwar über Administratorberechtigungen für die AD DS-Domäne TESTLAB verfügt, er aber kein globaler Administrator für Azure AD ist. Daher wird das Symbol **Admin** nicht als Option angezeigt.

Nachfolgend sehen Sie die daraus resultierende Konfiguration:

![Das simulierte Unternehmen mit einer Testumgebung mit Pass-Trought-Authentifizierung](../media/pass-through-auth-m365-ent-test-environment/Phase1.png)

Diese Konfiguration besteht aus: 

- Eine Microsoft 365 E5-Testversion oder kostenpflichtige Abonnements mit der DNS-Domäne testlab.\<*your domain name*> registriert.
- Ein vereinfachtes Organisationsintranet, das mit dem Internet verbunden ist, das aus den virtuellen Computern DC1, App1 und CLIENT1 in einem Subnetz eines virtuellen Azure-Netzwerks besteht.
- Azure AD Connect wird auf APP1 ausgeführt, um die Liste von Konten und Gruppen des Azure AD-Mandanten Ihrer Microsoft 365-Abonnements mit der AD DS-Domäne „TESTLAB“ zu synchronisieren.
- Azure AD nahtloses SSO ist aktiviert, sodass Computer im simulierten Intranet sich bei den Cloud-Ressourcen von Microsoft 365 anmelden können, ohne ein Benutzerkontokennwort anzugeben.

## <a name="next-step"></a>Nächster Schritt

Sehen Sie sich weitere [Identitäts](m365-enterprise-test-lab-guides.md#identity)features und- funktionen in Ihrer Testumgebung an.

## <a name="see-also"></a>Siehe auch

[Testumgebungsanleitungen für Microsoft 365 Enterprise](m365-enterprise-test-lab-guides.md)

[Übersicht über Microsoft 365 Enterprise](microsoft-365-overview.md)

[Dokumentation zu Microsoft 365 für Unternehmen](https://docs.microsoft.com/microsoft-365-enterprise/)
