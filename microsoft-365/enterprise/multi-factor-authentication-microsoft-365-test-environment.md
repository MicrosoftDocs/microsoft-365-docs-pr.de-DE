---
title: Mehrstufige Authentifizierung in Microsoft 365 für die Enterprise-Testumgebung
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
ms.openlocfilehash: f41fe7ad933f85c4b44a1e90529a998651412191
ms.sourcegitcommit: 53ff1fe6d6143b0bf011031eea9b85dc01ae4f74
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48487140"
---
# <a name="multi-factor-authentication-for-your-microsoft-365-for-enterprise-test-environment"></a>Mehrstufige Authentifizierung für Ihre Microsoft 365 für Enterprise-Testumgebung

*Diese Test Umgebungs Anleitung kann sowohl für Microsoft 365 für Unternehmen als auch für Office 365 Enterprise Testumgebungen verwendet werden.*

Für eine zusätzliche Sicherheitsstufe für die Anmeldung bei Microsoft 365 oder für einen Dienst oder eine Anwendung, die den Azure AD Mandanten für Ihr Abonnement verwendet, können Sie die Azure-mehrstufige Authentifizierung aktivieren, die mehr als nur einen Benutzernamen und ein Kennwort zum Überprüfen eines Kontos erfordert.

Bei der mehrstufigen Authentifizierung müssen Benutzer einen Telefonanruf bestätigen, einen in einer Textnachricht gesendeten Überprüfungscode eingeben oder die Authentifizierung mit einer APP auf ihren Smartphones überprüfen, nachdem Sie Ihre Kennwörter korrekt eingegeben haben. Sie können sich erst anmelden, nachdem dieser zweite Authentifizierungs Faktor erfüllt wurde.
  
In diesem Artikel wird beschrieben, wie Sie die Textnachrichten basierte Authentifizierung für ein bestimmtes Benutzerkonto aktivieren und testen.
  
Das Einrichten der mehrstufigen Authentifizierung für ein Konto in Ihrer Microsoft 365 for Enterprise-Testumgebung umfasst zwei Phasen und eine dritte optionale Phase:
- [Phase 1: Erstellen der Testumgebung für Microsoft 365 für Unternehmen](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [Phase 2: Aktivieren und Testen von Multi-Factor Authentication für das Konto „Benutzer 2“](#phase-2-enable-and-test-multi-factor-authentication-for-the-user-2-account)
- [Phase 3: Aktivieren und Testen der mehrstufigen Authentifizierung mit einer Richtlinie für bedingten Zugriff](#phase-3-enable-and-test-multi-factor-authentication-with-a-conditional-access-policy)

![Testumgebungsanleitungen für die Microsoft-Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> Eine visuelle Zuordnung zu allen Artikeln im Microsoft 365 for Enterprise Test Lab Guide Stack finden Sie unter [Microsoft 365 for Enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a>Phase 1: Erstellen der Testumgebung für Microsoft 365 für Unternehmen

Wenn Sie die mehrstufige Authentifizierung nur auf einfache Weise mit den Mindestanforderungen testen möchten, befolgen Sie die Anweisungen unter [Lightweight Base Configuration](lightweight-base-configuration-microsoft-365-enterprise.md).
  
Wenn Sie die mehrstufige Authentifizierung in einem simulierten Unternehmen testen möchten, befolgen Sie die Anweisungen unter [Pass-Through-Authentifizierung](pass-through-auth-m365-ent-test-environment.md).
  
> [!NOTE]
> Zum Testen der mehrstufigen Authentifizierung ist keine simulierte Enterprise-Testumgebung erforderlich, die ein simuliertes, mit dem Internet verbundenes Intranet und eine Verzeichnissynchronisierung für eine Active Directory-Domänendienste (AD DS) Gesamtstruktur umfasst. Dies wird hier als Option bereitgestellt, damit Sie Multi-Factor Authentication testen und damit in einer Umgebung experimentieren können, die eine typische Organisation darstellt.
  
## <a name="phase-2-enable-and-test-multi-factor-authentication-for-the-user-2-account"></a>Phase 2: Aktivieren und Testen von Multi-Factor Authentication für das Konto „Benutzer 2“

Aktivieren Sie Multi-Factor Authentication für das Konto „Benutzer 2“ mit den folgenden Schritten:
  
1. Öffnen Sie eine separate private Instanz Ihres Browsers, wechseln Sie zum Microsoft 365 Admin Center ( [https://portal.microsoft.com](https://portal.microsoft.com) ), und melden Sie sich dann mit ihrem globalen Administratorkonto an.
    
2. Wählen Sie im linken Navigationsbereich **Benutzer**  >  **aktive Benutzer**aus.
    
3. Wählen Sie im Bereich aktive Benutzer die Option **mehrstufige Authentifizierung**aus.
    
4. Wählen Sie in der Liste das Konto **Benutzer 2** aus.
    
5. Wählen Sie im Abschnitt **Benutzer 2** unter **schnell Schritte**die Option **aktivieren**aus.
    
6. Wählen Sie im Dialogfeld **Informationen zum Aktivieren der mehr** stufigen Authentifizierung die Option mehrstufige **Authentifizierung aktivieren**aus.
    
7. Wählen Sie im Dialogfeld **Updates erfolgreich** die Option **Schließen**aus.
    
8. Wählen Sie auf der Registerkarte **Microsoft 365 Admin Center** das Benutzerkonto Symbol in der oberen rechten Ecke aus, und wählen Sie dann **Abmelden aus**.
    
9. Schließen Sie Ihre Browserinstanz.
   
Schließen Sie die Konfiguration des Kontos „Benutzer 2“ für die Verwendung einer Textnachricht zur Prüfung ab, und testen Sie es mit den folgenden Schritten:
  
1. Öffnen Sie eine neue private Instanz Ihres Browsers.
    
2. Wechseln Sie zum [Microsoft 365 Admin Center](https://admin.microsoft.com) , und melden Sie sich mit dem Kontonamen und Kennwort des Benutzers 2 an.
    
3. Nachdem Sie sich angemeldet haben, werden Sie aufgefordert, das Konto einzurichten, um weitere Informationen zu erhalten. Wählen Sie **Weiter** aus.
    
4. Führen Sie auf der Seite **Zusätzliche Sicherheitsüberprüfung** die folgenden Schritte aus: 
    
   - Wählen Sie Ihr Land oder Ihre Region aus.
    
   - Geben Sie die Telefonnummer des Smartphones ein, das Textnachrichten empfangen soll.
    
   - Wählen **Method**Sie unter Methode **die Option mir einen Code per Textnachricht senden**aus.
    
5. Wählen Sie **Weiter** aus.
    
6. Geben Sie den Überprüfungscode aus der auf dem Smartphone empfangenen Textnachricht ein, und wählen Sie dann **überprüfen**aus.
    
7. Wählen Sie auf der Seite **Schritt 3: vorhandene Anwendungen beibehalten** die Option **Fertig**aus.
    
8. Wenn dies das erste Mal ist, dass Sie sich mit dem Konto „Benutzer 2“ angemeldet haben, werden Sie aufgefordert, das Kennwort zu ändern. Geben Sie das ursprüngliche Kennwort und ein neues Kennwort zweimal ein, und wählen Sie dann **Kennwort aktualisieren aus, und melden Sie sich an**. Zeichnen Sie das neue Kennwort an einem sicheren Ort auf.
    
    Das Office-Portal für Benutzer 2 sollte auf der Registerkarte **Microsoft Office Startseite** Ihres Browsers angezeigt werden.

## <a name="phase-3-enable-and-test-multi-factor-authentication-with-a-conditional-access-policy"></a>Phase 3: Aktivieren und Testen der mehrstufigen Authentifizierung mit einer Richtlinie für bedingten Zugriff

*Diese Phase kann nur für eine Microsoft 365 für Enterprise-Testumgebung verwendet werden.*

In dieser Phase aktivieren Sie die mehrstufige Authentifizierung für das Konto "Benutzer 3" mithilfe einer Gruppenrichtlinie und einer Richtlinie für den bedingten Zugriff.

Erstellen Sie als nächstes eine neue Gruppe mit dem Namen MFAUsers, und fügen Sie das Benutzerkonto 3 hinzu.

1. Wählen Sie auf der Registerkarte **Microsoft 365 Admin Center** im linken Navigationsbereich die Option **Gruppen** aus, und wählen Sie dann **Gruppen**aus.
2. Wählen Sie **Gruppe hinzufügen** aus.
3. Wählen Sie im Bereich **Gruppentyp auswählen** die Option **Sicherheit**aus, und wählen Sie dann **weiter**aus.
4. Wählen Sie im Bereich **Grundlagen einrichten die** Option **Gruppe erstellen**aus, und wählen Sie dann **Schließen**aus.
5. Geben Sie im Bereich **überprüfen und Abschließen der Gruppe hinzufügen** **MFAUsers**ein, und wählen Sie dann **weiter**aus.
6. Wählen Sie in der Liste der Gruppen die Gruppe **MFAUsers** aus.
7. Wählen Sie im Bereich **MFAUsers** die Option **Mitglieder**aus, und wählen Sie dann **Alle anzeigen und Mitglieder verwalten**aus.
8. Wählen Sie im Bereich **MFAUsers** die Option **Mitglieder hinzufügen**aus, wählen Sie das Konto **Benutzer 3** aus, und wählen Sie dann **Save**  >  **Close**  >  **Close**speichern aus.

Erstellen Sie als nächstes eine Richtlinie für den bedingten Zugriff, um die mehrstufige Authentifizierung für Mitglieder der MFAUsers-Gruppe zu erfordern.

1. Wechseln Sie auf einer neuen Registerkarte Ihres Browsers zu [https://portal.azure.com](https://portal.azure.com) .
2. Wählen Sie **Azure Active Directory**  >  **Sicherheits**  >  **bedingten Zugriff**aus.
3. Wählen Sie im Bereich **bedingte Zugriffs-Richtlinien** die Option **neue Richtlinie**aus.
4. Geben Sie im **neuen** Bereich **MFA für Benutzerkonten** in das Feld **Name** ein.
5. Wählen Sie im Abschnitt **Zuweisungen** die Option **Benutzer und Gruppen**aus.
6. Wählen Sie im Bereich **Benutzer und Gruppen** auf der Registerkarte **einschließen** die Option Benutzer und **Gruppen**  >  **Benutzer**  >  **und Gruppen**auswählen aus.
7. Wählen Sie im Bereich **auswählen** die Gruppe **MFAUsers** aus, **und wählen Sie**dann  >  **Fertig**aus.
8. Wählen Sie im Bereich **Zugriffssteuerung** des **neuen** Bereichs die Option **Grant**aus.
9. Wählen Sie im Bereich **Grant** die Option **mehrstufige Authentifizierung erforderlich**aus, und wählen Sie dann **auswählen**aus.
10. Wählen Sie im Bereich **neu** die **Option** für **Richtlinie aktivieren**aus, und wählen Sie dann **Erstellen**aus.
11. Schließen Sie die Registerkarten **Azure-Portal** und **Microsoft 365 Admin Center** .

Um diese Richtlinie zu testen, melden Sie sich ab, und melden Sie sich mit dem Benutzerkonto 3 an. Sie sollten aufgefordert werden, MFA zu konfigurieren. Dies zeigt, dass die MFAUsers-Richtlinie angewendet wird.

## <a name="next-step"></a>Nächster Schritt

Sehen Sie sich weitere [Identitäts](m365-enterprise-test-lab-guides.md#identity)features und- funktionen in Ihrer Testumgebung an.

## <a name="see-also"></a>Siehe auch

[Identity-Roadmap](identity-roadmap-microsoft-365.md)

[Testumgebungsanleitungen für Microsoft 365 Enterprise](m365-enterprise-test-lab-guides.md)

[Übersicht über Microsoft 365 Enterprise](microsoft-365-overview.md)

[Dokumentation zu Microsoft 365 für Unternehmen](https://docs.microsoft.com/microsoft-365-enterprise/)
