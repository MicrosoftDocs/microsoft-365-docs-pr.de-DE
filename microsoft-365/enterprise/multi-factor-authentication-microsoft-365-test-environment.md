---
title: Mehrstufige Authentifizierung der Microsoft 365 for Enterprise-Testumgebung
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/12/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-identity-device-management
ms.custom:
- TLG
- Ent_TLGs
- seo-marvel-apr2020
description: Konfigurieren Sie die mehrstufige Authentifizierung mithilfe von Textnachrichten, die an ein Smartphone in Ihrer Microsoft 365 for Enterprise-Testumgebung gesendet werden.
ms.openlocfilehash: aeb8940a9499909b8c568d1230f9aa45aee07b3d
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50923756"
---
# <a name="multi-factor-authentication-for-your-microsoft-365-for-enterprise-test-environment"></a>Mehrstufige Authentifizierung für Ihre Microsoft 365 for Enterprise-Testumgebung

*Diese Testumgebungsanleitung kann sowohl für Microsoft 365 Enterprise- als auch für Office 365 Enterprise-Testumgebungen verwendet werden.*

Für ein zusätzliches Maß an Sicherheit für die Anmeldung bei Microsoft 365 oder für alle Dienste oder Anwendungen, die den Azure AD-Mandanten für Ihr Abonnement verwenden, können Sie die mehrstufige Azure AD-Authentifizierung aktivieren, die mehr als nur einen Benutzernamen und ein Kennwort zum Überprüfen eines Kontos erfordert.

Bei der mehrstufigen Authentifizierung müssen Benutzer einen Anruf bestätigen, einen In einer Textnachricht gesendeten Überprüfungscode eingeben oder die Authentifizierung mit einer App auf ihren Smartphones überprüfen, nachdem sie ihre Kennwörter richtig eingegeben haben. Sie können sich nur anmelden, wenn dieser zweite Authentifizierungsfaktor erfüllt ist.
  
In diesem Artikel wird beschrieben, wie Sie die nachrichtenbasierte Textauthentifizierung für ein bestimmtes Benutzerkonto aktivieren und testen.
  
Das Einrichten der mehrstufigen Authentifizierung für ein Konto in Ihrer Microsoft 365 for Enterprise-Testumgebung umfasst zwei Phasen und eine dritte optionale Phase:
- [Phase 1: Erstellen Ihrer Microsoft 365 for Enterprise-Testumgebung](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [Phase 2: Aktivieren und Testen von Multi-Factor Authentication für das Konto „Benutzer 2“](#phase-2-enable-and-test-multi-factor-authentication-for-the-user-2-account)
- [Phase 3: Aktivieren und Testen der mehrstufigen Authentifizierung mit einer Richtlinie für bedingten Zugriff](#phase-3-enable-and-test-multi-factor-authentication-with-a-conditional-access-policy)

![Testumgebungsanleitungen für die Microsoft-Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> Eine visuelle Karte zu allen Artikeln im Microsoft 365 for Enterprise Test Lab Guide-Stapel finden Sie unter [Microsoft 365 for Enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a>Phase 1: Erstellen Ihrer Microsoft 365 for Enterprise-Testumgebung

Wenn Sie die mehrstufige Authentifizierung nur auf einfache Weise mit den Mindestanforderungen testen möchten, befolgen Sie die Anweisungen unter [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).
  
Wenn Sie die mehrstufige Authentifizierung in einem simulierten Unternehmen testen möchten, befolgen Sie die Anweisungen unter [Pass-Through-Authentifizierung](pass-through-auth-m365-ent-test-environment.md).
  
> [!NOTE]
> Das Testen der mehrstufigen Authentifizierung erfordert keine simulierte Unternehmenstestumgebung, die ein simuliertes Intranet umfasst, das mit dem Internet verbunden ist, und die Verzeichnissynchronisierung für eine Active Directory Domain Services (AD DS)-Gesamtstruktur. Dies wird hier als Option bereitgestellt, damit Sie Multi-Factor Authentication testen und damit in einer Umgebung experimentieren können, die eine typische Organisation darstellt.
  
## <a name="phase-2-enable-and-test-multi-factor-authentication-for-the-user-2-account"></a>Phase 2: Aktivieren und Testen von Multi-Factor Authentication für das Konto „Benutzer 2“

Aktivieren Sie Multi-Factor Authentication für das Konto „Benutzer 2“ mit den folgenden Schritten:
  
1. Öffnen Sie eine separate, private Instanz Ihres Browsers, wechseln Sie zum Microsoft 365 Admin Center ( ), und melden Sie sich dann mit Ihrem [https://portal.microsoft.com](https://portal.microsoft.com) globalen Administratorkonto an.
    
2. Wählen Sie in der linken Navigation **Benutzer**  >  **Aktive Benutzer aus.**
    
3. Wählen Sie im Bereich Aktive Benutzer die **Option Mehrstufige Authentifizierung aus.**
    
4. Wählen Sie in der Liste das **Konto "Benutzer 2"** aus.
    
5. Wählen Sie **im Abschnitt Benutzer 2** unter **Schnellschritte** die Option **Aktivieren aus.**
    
6. Wählen Sie **im Dialogfeld Mehrstufige Authentifizierung** aktivieren die Option **Mehrstufige Authentifizierung aktivieren aus.**
    
7. Wählen Sie **im Dialogfeld Updates erfolgreich** die Option Schließen **aus.**
    
8. Wählen Sie auf der **Registerkarte Microsoft 365 Admin Center** oben rechts das Benutzerkontosymbol aus, und wählen Sie dann **Abmelden aus.**
    
9. Schließen Sie Ihre Browserinstanz.
   
Schließen Sie die Konfiguration des Kontos „Benutzer 2“ für die Verwendung einer Textnachricht zur Prüfung ab, und testen Sie es mit den folgenden Schritten:
  
1. Öffnen Sie eine neue, private Instanz Ihres Browsers.
    
2. Wechseln Sie zum [Microsoft 365 Admin Center,](https://admin.microsoft.com) und melden Sie sich mit dem Benutzer 2-Kontonamen und -kennwort an.
    
3. Nach der Anmeldung werden Sie aufgefordert, das Konto für weitere Informationen zu einrichten. Wählen Sie **Weiter** aus.
    
4. Führen Sie auf der Seite **Zusätzliche Sicherheitsüberprüfung** die folgenden Schritte aus: 
    
   - Wählen Sie Ihr Land oder Ihre Region aus.
    
   - Geben Sie die Telefonnummer des Smartphones ein, das Textnachrichten erhält.
    
   - Wählen **Sie unter Methode** die Option Code per **Textnachricht senden aus.**
    
5. Wählen Sie **Weiter** aus.
    
6. Geben Sie den Überprüfungscode aus der auf Ihrem Smartphone empfangenen Textnachricht ein, und wählen Sie **dann Überprüfen aus.**
    
7. Wählen Sie **auf der Seite Schritt 3: Vorhandene** Anwendungen behalten die Option Fertig **aus.**
    
8. Wenn dies das erste Mal ist, dass Sie sich mit dem Konto „Benutzer 2“ angemeldet haben, werden Sie aufgefordert, das Kennwort zu ändern. Geben Sie zweimal das ursprüngliche Kennwort und ein neues Kennwort ein, und wählen Sie **dann Kennwort aktualisieren aus, und melden Sie sich an.** Zeichnen Sie das neue Kennwort an einem sicheren Ort auf.
    
    Das Office-Portal für Benutzer 2 sollte auf der Registerkarte **Microsoft Office Ihrem** Browser angezeigt werden.

## <a name="phase-3-enable-and-test-multi-factor-authentication-with-a-conditional-access-policy"></a>Phase 3: Aktivieren und Testen der mehrstufigen Authentifizierung mit einer Richtlinie für bedingten Zugriff

*Diese Phase kann nur für eine Microsoft 365 for Enterprise-Testumgebung verwendet werden.*

In dieser Phase aktivieren Sie die mehrstufige Authentifizierung für das Benutzer 3-Konto mithilfe einer Gruppe und einer Richtlinie für bedingten Zugriff.

Erstellen Sie als Nächstes eine neue Gruppe mit dem Namen MFAUsers, und fügen Sie ihr das Konto "Benutzer 3" hinzu.

1. Wählen Sie auf der **Registerkarte Microsoft 365 Admin Center** im linken Navigationsbereich Gruppen aus, und wählen Sie dann Gruppen **aus.** 
2. Wählen Sie **Gruppe hinzufügen** aus.
3. Wählen Sie **im Bereich Gruppentyp auswählen** die Option **Sicherheit** aus, und wählen Sie dann **Weiter aus.**
4. Wählen Sie **im Bereich** Einrichten der Grundlagen die Option Gruppe erstellen aus, und wählen Sie dann Schließen **aus.** 
5. Geben Sie im Bereich Überprüfen und Fertig stellen **des Hinzufügens** von Gruppen **MFAUsers** ein, und wählen Sie dann **Weiter aus.**
6. Wählen Sie in der Liste der Gruppen die **Gruppe MFAUsers** aus.
7. Wählen Sie **im Bereich MFAUsers** die Option **Mitglieder** aus, und wählen Sie dann Alle anzeigen und Mitglieder **verwalten aus.**
8. Wählen Sie **im Bereich MFAUsers** die Option Mitglieder **hinzufügen** aus, wählen Sie das Konto **Benutzer 3** aus, und wählen Sie **dann Schließen**  >  **schließen**  >  **speichern aus.**

Erstellen Sie als Nächstes eine Richtlinie für bedingten Zugriff, um die mehrstufige Authentifizierung für Mitglieder der Gruppe "MFAUsers" zu erfordern.

1. Wechseln Sie auf einer neuen Registerkarte Ihres Browsers zu [https://portal.azure.com](https://portal.azure.com) .
2. Wählen **Sie Azure Active Directory**  >  **Security** Conditional Access  >  **aus.**
3. Wählen Sie **im Bereich Bedingter Zugriff – Richtlinien** die Option Neue Richtlinie **aus.**
4. Geben Sie **im Bereich** Neu **MFA für Benutzerkonten** in das Feld **Name** ein.
5. Wählen Sie **im Abschnitt Zuweisungen** die Option **Benutzer und Gruppen aus.**
6. Wählen Sie **auf der** Registerkarte Include im Bereich **Benutzer und** Gruppen die Option Benutzer und **Gruppen** Auswählen Benutzer  >  **und Gruppen** Auswählen  >  **aus.**
7. Wählen Sie **im Bereich** Auswählen die **Gruppe MFAUsers** aus, und wählen Sie **dann Fertig**  >  **auswählen aus.**
8. Wählen Sie **im Abschnitt Zugriffssteuerelemente** im **Bereich Neu** die Option **Gewähren aus.**
9. Wählen Sie **im Bereich** Gewähren die Option **Mehrstufige Authentifizierung** erforderlich aus, und wählen Sie dann **Auswählen aus.**
10. Wählen Sie **im Bereich Neu** die Option **Ein** für Richtlinie **aktivieren** aus, und wählen Sie dann **Erstellen aus.**
11. Schließen Sie **die Registerkarten Azure-Portal** und **Microsoft 365 Admin Center.**

Um diese Richtlinie zu testen, melden Sie sich ab und melden Sie sich mit dem Benutzer 3-Konto an. Sie sollten aufgefordert werden, MFA zu konfigurieren. Dies zeigt, dass die MFAUsers-Richtlinie angewendet wird.

## <a name="next-step"></a>Nächster Schritt

Sehen Sie sich weitere [Identitäts](m365-enterprise-test-lab-guides.md#identity)features und- funktionen in Ihrer Testumgebung an.

## <a name="see-also"></a>Siehe auch

[Identitätsplan](identity-roadmap-microsoft-365.md)

[Testumgebungsanleitungen für Microsoft 365 Enterprise](m365-enterprise-test-lab-guides.md)

[Übersicht über Microsoft 365 Enterprise](microsoft-365-overview.md)

[Dokumentation zu Microsoft 365 Enterprise](/microsoft-365-enterprise/)