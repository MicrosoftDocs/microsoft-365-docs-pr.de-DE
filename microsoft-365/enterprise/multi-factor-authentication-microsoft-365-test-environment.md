---
title: Mehrstufige Authentifizierung für Ihre Microsoft 365 Enterprise-Testumgebung
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 08/21/2018
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-identity-device-management
ms.custom:
- TLG
- Ent_TLGs
description: Konfigurieren Sie die mehrstufige Authentifizierung mit Textnachrichten, die an ein Smartphone in Ihrer Microsoft 365 Enterprise-Testumgebung gesendet werden.
ms.openlocfilehash: 319f8058aa4504c52cacf5f0d97982d115c41c8a
ms.sourcegitcommit: 66bb5af851947078872a4d31d3246e69f7dd42bb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/15/2019
ms.locfileid: "34074215"
---
# <a name="multi-factor-authentication-for-your-microsoft-365-enterprise-test-environment"></a>Mehrstufige Authentifizierung für Ihre Microsoft 365 Enterprise-Testumgebung

Für eine zusätzliche Sicherheitsstufe für die Anmeldung bei Office 365 oder einem Dienst oder einer Anwendung, die den Azure AD-Mandanten für Ihre Organisation verwenden, können Sie die Azure-mehrstufige Authentifizierung aktivieren, die mehr als nur einen Benutzernamen und ein Kennwort zum Überprüfen benötigt. Konto. Bei der mehrstufigen Authentifizierung müssen Benutzer einen Telefonanruf bestätigen, einen in einer Textnachricht gesendeten Bestätigungscode eingeben oder ein App-Kennwort auf dem Smartphone angeben, nachdem Sie die entsprechenden Kennwörter korrekt eingegeben haben. Eine Anmeldung ist nur möglich, nachdem diese zweite Authentifizierungsstufe passiert wurde. 
  
In diesem Artikel wird beschrieben, wie Sie die Textnachrichten basierte Authentifizierung für ein bestimmtes Konto aktivieren und testen.
  
Es gibt zwei Phasen zum Einrichten der mehrstufigen Authentifizierung für ein Konto in Ihrer Microsoft 365 Enterprise-Testumgebung:
  
1. Erstellen Sie die Microsoft 365 Enterprise-Testumgebung.
    
2. Aktivieren und Testen von Multi-Factor Authentication für das Konto „Benutzer 2“

![Testumgebungsanleitungen für die Microsoft-Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> Klicken Sie [hier](https://aka.ms/m365etlgstack), um eine visuelle Darstellung aller Artikel im Stapel der Testumgebungsanleitungen in Microsoft 365 Enterprise zu erhalten.
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a>Phase 1: Erstellen der Microsoft 365 Enterprise-Testumgebung

Wenn Sie die mehrstufige Authentifizierung nur auf einfache Weise mit den Mindestanforderungen testen möchten, befolgen Sie die Anweisungen unter [Lightweight Base Configuration](lightweight-base-configuration-microsoft-365-enterprise.md).
  
Wenn Sie die mehrstufige Authentifizierung in einem simulierten Unternehmen testen möchten, befolgen Sie die Anweisungen unter [Pass-Through-Authentifizierung](pass-through-auth-m365-ent-test-environment.md).
  
> [!NOTE]
> Zum Testen der mehrstufigen Authentifizierung ist die simulierte Enterprise-Testumgebung nicht erforderlich, die ein simuliertes, mit dem Internet verbundenes Intranet und eine Verzeichnissynchronisierung für eine Active Directory-Domänendienste (AD DS)-Gesamtstruktur umfasst. Dies wird hier als Option bereitgestellt, damit Sie Multi-Factor Authentication testen und damit in einer Umgebung experimentieren können, die eine typische Organisation darstellt. 
  
## <a name="phase-2-enable-and-test-multi-factor-authentication-for-the-user-2-account"></a>Phase 2: Aktivieren und Testen von Multi-Factor Authentication für das Konto „Benutzer 2“

Aktivieren Sie Multi-Factor Authentication für das Konto „Benutzer 2“ mit den folgenden Schritten:
  
1. Öffnen Sie eine separate private Instanz Ihres Browsers, wechseln Sie zum Microsoft 365 Admin Center ([https://portal.microsoft.com](https://portal.microsoft.com)), und melden Sie sich dann mit ihrem globalen Administratorkonto an.
    
2. Klicken Sie im linken Navigationsbereich auf **Benutzer > Aktive Benutzer**.
    
3. Klicken Sie im Bereich aktive Benutzer auf **mehr #a0 Setup**für die mehrstufige Authentifizierung.
    
4. Wählen Sie in der Liste das Konto **Benutzer 2** aus.
    
5. Klicken Sie im Abschnitt **Benutzer 2** unter **QuickSteps** auf **Aktivieren**.
    
6. Klicken Sie im Dialogfeld **Informationen zum Aktivieren von mehrstufiger Aktualisierung** auf **Multi-Factor Authentication aktivieren**.
    
7. Klicken Sie im Dialogfeld **Updates erfolgreich** auf **Schließen**.
    
8. Klicken Sie auf der Registerkarte **Microsoft 365 Admin Center** in der oberen rechten Ecke auf das Symbol für das Benutzer **** Konto, und klicken Sie dann auf Abmelden.
    
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


Informationen und Links zum Bereitstellen der mehrstufigen Authentifizierung in der Produktionsumgebung finden Sie im Schritt zum [Einrichten der mehr](identity-multi-factor-authentication.md#identity-mfa) stufigen Authentifizierung in der Identitäts Phase.
    
## <a name="next-step"></a>Nächster Schritt

Sehen Sie sich weitere [Identitäts](m365-enterprise-test-lab-guides.md#identity)features und- funktionen in Ihrer Testumgebung an.

## <a name="see-also"></a>Siehe auch

[Phase 2: Identität](identity-infrastructure.md)

[Testumgebungsanleitungen für Microsoft 365 Enterprise](m365-enterprise-test-lab-guides.md)

[Microsoft 365 Enterprise-Bereitstellungshandbuch](deploy-microsoft-365-enterprise.md)

[Dokumentation zu Microsoft 365 Enterprise](https://docs.microsoft.com/microsoft-365-enterprise/)
