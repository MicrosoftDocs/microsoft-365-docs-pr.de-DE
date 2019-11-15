---
title: Nahtloses einmaliges Anmelden in Azure AD für Ihre Microsoft 365-Testumgebung
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 08/21/2018
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom:
- TLGS
- Ent_TLGs
ms.assetid: ''
description: 'Zusammenfassung: Konfigurieren und Testen des nahtlosen einmaliges Anmeldens in Azure AD für Ihre Microsoft 365-Testumgebung.'
ms.openlocfilehash: c8417d7ff1c4a2b9a753968804d187300b6c6195
ms.sourcegitcommit: 2c2248b03f7753d64490f2f7e56ec644a235b65a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/15/2019
ms.locfileid: "38640596"
---
# <a name="azure-ad-seamless-single-sign-on-for-your-microsoft-365-test-environment"></a>Nahtloses einmaliges Anmelden in Azure AD für Ihre Microsoft 365-Testumgebung

Beim nahtlosen einmaligen Anmelden von Azure AD werden Benutzer automatisch angemeldet, wenn sie auf ihren Computern oder Geräten arbeiten, die mit ihrem Organisationsnetzwerk verbunden sind. Das nahtlose einmalige Anmelden in Azure AD bietet Benutzern einfachen Zugriff auf cloudbasierte Anwendungen, ohne dass dafür zusätzliche lokale Komponenten erforderlich sind.

Dieser Artikel beschreibt, wie Sie Ihre Microsoft 365-Testumgebung für das nahtlose einmalige Anmelden in Azure AD konfigurieren.

Die Einrichtung besteht aus zwei Phasen:

1.  Erstellen Sie die simulierte Microsoft 365-Testunternehmensumgebung mit Kennworthashsynchronisierung.
2.  Konfigurieren Sie Azure AD Connect auf APP1 für das nahtlose einmalige Anmelden in Azure AD.
    
![Testumgebungsanleitungen für die Microsoft-Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> Klicken Sie [hier](media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf), um eine visuelle Darstellung aller Artikel im Stapel der Testumgebungsanleitungen in Microsoft 365 Enterprise zu erhalten.
  
## <a name="phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment"></a>Phase 1: Konfigurieren Sie Kennworthashsynchronisierung für Ihre Microsoft 365-Testumgebung

Befolgen Sie die Anweisungen unter [Kennworthashsynchronisierung für Microsoft 365](password-hash-sync-m365-ent-test-environment.md). Hier ist die resultierende Konfiguration.
  
![Das simulierte Unternehmen mit Kennworthashsynchronisierung für die Testumgebung](media/pass-through-auth-m365-ent-test-environment/Phase1.png)
  
Diese Konfiguration besteht aus: 
  
- Testversionen oder kostenpflichtigen Abonnements von Office 365 E5 und EMS E5.
- Einem vereinfachtem Unternehmensintranet mit Internetzugriff, das aus virtuellen DC1-, APP1- und CLIENT1-Computern in einem Subnetz eines virtuellen Azure-Netzwerks besteht. 
- Azure AD Connect wird auf APP1 ausgeführt, um die Active Directory Domain Services (AD DS)-Domäne TESTLAB mit dem Azure AD-Mandanten Ihrer Office 365- und EMS E5-Abonnements in regelmäßigen Abständen zu synchronisieren.

## <a name="phase-2-configure-azure-ad-connect-on-app1-for-azure-ad-seamless-sso"></a>Phase 2: Konfigurieren Sie Azure AD Connect auf APP1 für das nahtlose einmalige Anmelden in Azure AD.

In dieser Phase konfigurieren Sie Azure AD Connect auf APP1 für das nahtlose einmalige Anmelden in Azure AD und vergewissern sich dann, dass es funktioniert.

### <a name="configure-azure-ad-connect-on-app1"></a>Konfigurieren von Azure AD Connect auf APP1

1. Melden Sie sich über das [Azure-Portal](https://portal.azure.com) mit Ihrem globalen Administratorkonto an, und stellen Sie dann mit dem Konto „TESTLAB\User1“ eine Verbindung zu APP1 her.

2. Führen Sie Azure AD Connect über den Desktop von APP1 aus.

3. Klicken Sie auf der Seite **Willkommen** auf **Konfigurieren**.

4. Klicken Sie auf der Seite **Weitere Aufgaben** auf **Benutzeranmeldung ändern**, und klicken Sie dann auf **Weiter**.

5. Geben Sie auf der Seite **Mit Azure AD verbinden** die Anmeldeinformationen für das globale Administratorkonto ein, und klicken Sie dann auf **Weiter**.

6. Wählen Sie auf der Seite **Benutzeranmeldung** die Option **Einmaliges Anmelden aktivieren**, und klicken Sie dann auf **Weiter**.

7. Klicken Sie auf der Seite **Einmaliges Anmelden aktivieren** auf **Anmeldeinformationen eingeben**.

8. Geben Sie im Dialogfeld **Windows-Sicherheit** den Benutzer **Benutzer1** und das Kennwort für das Konto „Benutzer1“ ein, und klicken Sie dann auf **OK**. Klicken Sie auf **Weiter**.

9. Klicken Sie auf der Seite **Bereit zur Konfiguration** auf **Konfigurieren**.

10. Klicken Sie auf der Seite **Konfiguration abgeschlossen** auf **Beenden**.

11. Klicken Sie im Azure-Portal im linken Bereich auf **Azure Active Directory > Azure AD Connect**. Überprüfen Sie, ob die Funktion **Einmaliges Anmelden** als **Aktiviert** angezeigt wird.

Als Nächstes testen Sie, ob Sie sich mit dem Benutzernamen <strong>user1@testlab.</strong>\<Ihre öffentliche Domäne> des Kontos „Benutzer1“ beim Ihrem Office 365-Abonnement anmelden können.

1. Klicken Sie in Internet Explorer auf APP1 auf das Symbol „Einstellungen“, und klicken Sie dann auf **Internetoptionen**.
 
2. Klicken Sie unter **Internetoptionen** auf die Registerkarte **Sicherheit**.

3. Klicken Sie auf **Lokales Intranet** und dann auf **Sites**.

4. Klicken Sie unter **Lokales Intranet** auf **Erweitert**.

5. Geben Sie unter **Diese Website zur Zone hinzufügen** die Adresse **https<span>://</span>autologon.microsoftazuread-sso.com** ein, und klicken Sie auf **Hinzufügen > Schließen > OK > OK**.

6. Melden Sie sich von Office 365 ab, und melden Sie sich dann erneut an. Geben Sie dieses Mal ein anderes Konto an.

7. Wenn Sie aufgefordert werden, sich anzumelden, geben Sie <strong>user1@testlab.</strong>\<Ihren öffentlichen Domänennamen> an, und klicken Sie dann auf **Weiter**. Sie sollten sich erfolgreich als "User1" anmelden können, ohne zur Eingabe eines Kennworts aufgefordert zu werden. Dies beweist, dass das nahtlose einmalige Anmelden mit Azure AD funktioniert.

Beachten Sie, dass "User1" zwar über Administratorberechtigungen für die AD DS-Domäne TESTLAB verfügt, er aber kein globaler Administrator für Azure AD und Office 365 ist. Daher wird das Symbol **Admin** nicht als Option angezeigt.

Nachfolgend sehen Sie die daraus resultierende Konfiguration:

![Das simulierte Unternehmen mit einer Testumgebung mit Pass-Trought-Authentifizierung](media/pass-through-auth-m365-ent-test-environment/Phase1.png)

 
Diese Konfiguration besteht aus: 

- Testversionen oder kostenpflichtigen Abonnements von Office 365 E5 und EMS E5 mit der registrieren DNS-Domäne testlab.\<Ihr Domänenname>.
- Einem vereinfachtem Unternehmensintranet mit Internetzugriff, das aus virtuellen DC1-, APP1- und CLIENT1-Computern in einem Subnetz eines virtuellen Azure-Netzwerks besteht. 
- Azure AD Connect wird auf APP1 ausgeführt, um die Liste von Konten und Gruppen des Azure AD-Mandanten Ihrer Office 365- und EMS E5-Abonnements mit der AD DS-Domäne "TESTLAB" zu synchronisieren. 
- Das nahtlose einmalige Anmelden in Azure AD wird aktiviert, damit sich Computer im simulierten Intranet bei Microsoft 365-Cloudressourcen anmelden können, ohne ein Kennwort für ein Benutzerkonto anzugeben.

Im Schritt [Vereinfachen der Benutzeranmeldung](identity-secure-your-passwords.md#identity-sso) in der Identitätsphase finden Sie Informationen und Links zum Konfigurieren der nahtlosen einmaligen Anmeldung in Azure AD in der Produktion.

## <a name="next-step"></a>Nächster Schritt

Sehen Sie sich weitere [Identitäts](m365-enterprise-test-lab-guides.md#identity)features und- funktionen in Ihrer Testumgebung an.

## <a name="see-also"></a>Siehe auch

[Testumgebungsanleitungen für Microsoft 365 Enterprise](m365-enterprise-test-lab-guides.md)

[Bereitstellen von Microsoft 365 Enterprise](deploy-microsoft-365-enterprise.md)

[Dokumentation zu Microsoft 365 Enterprise](https://docs.microsoft.com/microsoft-365-enterprise/)


