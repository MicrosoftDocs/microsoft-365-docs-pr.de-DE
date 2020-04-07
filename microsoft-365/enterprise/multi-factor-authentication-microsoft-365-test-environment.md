---
title: Mehrstufige Authentifizierung für Ihre Microsoft 365 Enterprise-Testumgebung
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
description: Konfigurieren Sie die mehrstufige Authentifizierung mit Textnachrichten, die an ein Smartphone in Ihrer Microsoft 365 Enterprise-Testumgebung gesendet werden.
ms.openlocfilehash: b17c6b3b39bebaff2737ea5e9bb198beef00844c
ms.sourcegitcommit: e525bcf073a61e1350484719a0c3ceb6ff0d8db1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/06/2020
ms.locfileid: "43153880"
---
# <a name="multi-factor-authentication-for-your-microsoft-365-enterprise-test-environment"></a>Mehrstufige Authentifizierung für Ihre Microsoft 365 Enterprise-Testumgebung

*Diese Testumgebungsanleitung kann für Microsoft 365 Enterprise- und Office 365 Enterprise-Testumgebungen verwendet werden.*

Für eine zusätzliche Sicherheitsstufe für die Anmeldung bei Microsoft 365 oder für einen Dienst oder eine Anwendung, die den Azure AD Mandanten für Ihr Abonnement verwendet, können Sie die Azure-mehrstufige Authentifizierung aktivieren, die mehr als nur einen Benutzernamen und ein Kennwort zum Überprüfen eines Kontos erfordert. 

Bei der mehrstufigen Authentifizierung müssen Benutzer einen Telefonanruf bestätigen, einen in einer Textnachricht gesendeten Bestätigungscode eingeben oder ein App-Kennwort auf dem Smartphone angeben, nachdem Sie die entsprechenden Kennwörter korrekt eingegeben haben. Eine Anmeldung ist nur möglich, nachdem diese zweite Authentifizierungsstufe passiert wurde. 
  
In diesem Artikel wird beschrieben, wie Sie die Textnachrichten basierte Authentifizierung für ein bestimmtes Benutzerkonto aktivieren und testen.
  
Es gibt zwei Phasen zum Einrichten der mehrstufigen Authentifizierung für ein Konto in Ihrer Microsoft 365 Enterprise-Testumgebung:
  
1. Erstellen Sie die Microsoft 365 Enterprise-Testumgebung.
    
2. Aktivieren und Testen von Multi-Factor Authentication für das Konto „Benutzer 2“

3. Aktivieren und testen Sie die mehrstufige Authentifizierung mit einer Richtlinie für bedingten Zugriff (optional).

![Testumgebungsanleitungen für die Microsoft-Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> Klicken Sie [hier](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf), um eine visuelle Darstellung aller Artikel im Stapel der Testumgebungsanleitungen in Microsoft 365 Enterprise zu erhalten.
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a>Phase 1: Erstellen Ihrer Microsoft 365 Enterprise-Testumgebung

Wenn Sie die mehrstufige Authentifizierung nur auf einfache Weise mit den Mindestanforderungen testen möchten, befolgen Sie die Anweisungen unter [Lightweight Base Configuration](lightweight-base-configuration-microsoft-365-enterprise.md).
  
Wenn Sie die mehrstufige Authentifizierung in einem simulierten Unternehmen testen möchten, befolgen Sie die Anweisungen unter [Pass-Through-Authentifizierung](pass-through-auth-m365-ent-test-environment.md).
  
> [!NOTE]
> Zum Testen der mehrstufigen Authentifizierung ist keine simulierte Enterprise-Testumgebung erforderlich, die ein simuliertes, mit dem Internet verbundenes Intranet und eine Verzeichnissynchronisierung für eine Active Directory-Domänendienste (AD DS) Gesamtstruktur umfasst. Dies wird hier als Option bereitgestellt, damit Sie Multi-Factor Authentication testen und damit in einer Umgebung experimentieren können, die eine typische Organisation darstellt. 
  
## <a name="phase-2-enable-and-test-multi-factor-authentication-for-the-user-2-account"></a>Phase 2: Aktivieren und Testen von Multi-Factor Authentication für das Konto „Benutzer 2“

Aktivieren Sie Multi-Factor Authentication für das Konto „Benutzer 2“ mit den folgenden Schritten:
  
1. Öffnen Sie eine separate private Instanz Ihres Browsers, wechseln Sie zum Microsoft 365 Admin Center ([https://portal.microsoft.com](https://portal.microsoft.com)), und melden Sie sich dann mit ihrem globalen Administratorkonto an.
    
2. Klicken Sie im linken Navigationsbereich auf **Benutzer > Aktive Benutzer**.
    
3. Klicken Sie im Bereich aktive Benutzer auf **mehr**stufige Authentifizierung.
    
4. Wählen Sie in der Liste das Konto **Benutzer 2** aus.
    
5. Klicken Sie im Abschnitt **Benutzer 2** unter **QuickSteps** auf **Aktivieren**.
    
6. Klicken Sie im Dialogfeld **Informationen zum Aktivieren von mehrstufiger Aktualisierung** auf **Multi-Factor Authentication aktivieren**.
    
7. Klicken Sie im Dialogfeld **Updates erfolgreich** auf **Schließen**.
    
8. Klicken Sie auf der Registerkarte **Microsoft 365 Admin Center** in der oberen rechten Ecke auf das Symbol für das Benutzerkonto, und klicken Sie dann auf **Abmelden**.
    
9. Schließen Sie Ihre Browserinstanz.
   
Schließen Sie die Konfiguration des Kontos „Benutzer 2“ für die Verwendung einer Textnachricht zur Prüfung ab, und testen Sie es mit den folgenden Schritten:
  
1. Öffnen Sie eine neue private Instanz Ihres Browsers.
    
2. Wechseln Sie zum Office 365 Portal ([https://portal.office.com](https://portal.office.com)), und melden Sie sich mit dem Kontonamen und Kennwort des Benutzers 2 an.
    
3. Nachdem Sie sich angemeldet haben, werden Sie aufgefordert, das Konto einzurichten, um weitere Informationen zu erhalten. Klicken Sie auf **Weiter**.
    
4. Führen Sie auf der Seite **Zusätzliche Sicherheitsüberprüfung** die folgenden Schritte aus: 
    
   - Wählen Sie Ihr Land oder Ihre Region aus.
    
   - Geben Sie die Telefonnummer des Smartphones ein, das Textnachrichten erhalten soll.
    
   - Klicken Sie in **Methode**auf **Senden Sie mir einen Code per Textnachricht**.
    
5. Klicken Sie auf **Weiter**.
    
6. Geben Sie den Verifizierungscode aus der Textnachricht ein, die an Ihr Smartphone gesendet wurde, und klicken Sie dann auf **Überprüfen**.
    
7. Zeichnen Sie das auf der Seite **Schritt 3: Keep your existing applications** angezeigte App-Kennwort für das Konto „Benutzer 2“ an einem sicheren Ort auf, und klicken Sie dann auf **Fertig**.
    
8. Wenn dies das erste Mal ist, dass Sie sich mit dem Konto „Benutzer 2“ angemeldet haben, werden Sie aufgefordert, das Kennwort zu ändern. Geben Sie das ursprüngliche Kennwort und dann zwei Mal ein neues Kennwort ein, und klicken Sie dann auf **Kennwort ändern und anmelden**. Zeichnen Sie das neue Kennwort an einem sicheren Ort auf.
    
    Das Office-Portal für Benutzer 2 sollte auf der Registerkarte **Microsoft Office Startseite** Ihres Browsers angezeigt werden.

## <a name="phase-3-enable-and-test-multi-factor-authentication-with-a-conditional-access-policy"></a>Phase 3: Aktivieren und Testen der mehrstufigen Authentifizierung mit einer Richtlinie für bedingten Zugriff

*Diese Phase kann nur für eine Microsoft 365 Enterprise-Testumgebung verwendet werden.*

In dieser Phase aktivieren Sie die mehrstufige Authentifizierung für das Konto "Benutzer 3" mithilfe einer Gruppenrichtlinie und einer Richtlinie für den bedingten Zugriff.

Erstellen Sie als nächstes eine neue Gruppe mit dem Namen MFAUsers, und fügen Sie das Benutzerkonto 3 hinzu.

1. Klicken Sie auf der Registerkarte **Microsoft 365 Admin Center** im linken Navigationsbereich auf **Gruppen** , und klicken Sie dann auf **Gruppen**.
2. Klicken Sie auf **Gruppe hinzufügen**.
3. Wählen Sie im Bereich **Gruppentyp auswählen** die Option **Sicherheit**aus, und klicken Sie dann auf **weiter**.
4. Klicken Sie im Bereich **Grundlagen einrichten** auf **Gruppe erstellen**, und klicken Sie dann auf **Schließen**.
5. Geben Sie im Bereich **überprüfen und Abschließen der Gruppe hinzufügen** **MFAUsers**ein, und klicken Sie dann auf **weiter**.
6. Klicken Sie in der Liste der Gruppen auf die Gruppe **MFAUsers** .
7. Klicken Sie im Bereich **MFAUsers** auf **Mitglieder**, und klicken Sie dann auf **Alle anzeigen und Mitglieder verwalten**.
8. Klicken Sie im Bereich **MFAUsers** auf **Mitglieder hinzufügen**, wählen Sie das Konto **Benutzer 3** aus, und klicken Sie dann auf **speichern > schließen > schließen**.

Erstellen Sie als nächstes eine Richtlinie für den bedingten Zugriff, um die mehrstufige Authentifizierung für Mitglieder der MFAUsers-Gruppe zu erfordern.

1. Wechseln Sie auf einer neuen Registerkarte Ihres Browsers zu [https://portal.azure.com](https://portal.azure.com).
2. Klicken Sie auf **Azure Active Directory > Sicherheits > bedingten Zugriff**.
3. Klicken Sie im Bereich **bedingter Zugriff – Richtlinien** auf **neue Richtlinie**.
4. Geben Sie im **neuen** Bereich **MFA für Benutzerkonten** unter **Name**ein.
5. Klicken Sie im Abschnitt **Zuweisungen** auf **Benutzer und Gruppen**.
6. Klicken Sie im Bereich **Benutzer und Gruppen** auf der Registerkarte **einschließen** auf Benutzer und Gruppen **> Benutzer und Gruppen auswählen > auswählen**.
7. Klicken Sie im Bereich **auswählen** auf die Gruppe **MFAUsers** , und klicken Sie dann auf **> fertig wählen**.
8. Klicken Sie im Abschnitt **Zugriffssteuerung** des **neuen** Bereichs auf **erteilen**.
9. Klicken Sie im Bereich **Grant** auf **mehrstufige Authentifizierung erfordern**, und klicken Sie dann auf **auswählen**.
10. Klicken Sie im Bereich **neu** **auf** für **Richtlinie aktivieren**, und klicken Sie dann auf **Erstellen**.
11. Schließen Sie die Registerkarten **Azure-Portal** und **Microsoft 365 Admin Center** .

Um diese Richtlinie zu testen, melden Sie sich ab, und melden Sie sich mit dem Benutzerkonto 3 an. Sie sollten aufgefordert werden, MFA zu konfigurieren. Dies zeigt, dass die MFAUsers-Richtlinie angewendet wird.

Informationen und Links zum Bereitstellen der mehrstufigen Authentifizierung in der Produktionsumgebung finden Sie im Schritt zum [Einrichten der mehr](identity-secure-user-sign-ins.md#identity-mfa) stufigen Authentifizierung in der Identitäts Phase.
    
## <a name="next-step"></a>Nächster Schritt

Sehen Sie sich weitere [Identitäts](m365-enterprise-test-lab-guides.md#identity)features und- funktionen in Ihrer Testumgebung an.

## <a name="see-also"></a>Siehe auch

[Phase 2: Identität](identity-infrastructure.md)

[Testumgebungsanleitungen für Microsoft 365 Enterprise](m365-enterprise-test-lab-guides.md)

[Microsoft 365 Enterprise-Bereitstellungshandbuch](deploy-microsoft-365-enterprise.md)

[Dokumentation zu Microsoft 365 Enterprise](https://docs.microsoft.com/microsoft-365-enterprise/)
