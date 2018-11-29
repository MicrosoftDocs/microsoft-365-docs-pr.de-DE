---
title: Mehrstufige Authentifizierung für Microsoft 365 Unternehmen test Environment.
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 08/21/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: Ent_O365
ms.custom:
- TLG
- Ent_TLGs
description: Konfigurieren Sie mehrstufige Authentifizierung über Textnachrichten gesendet, um ein Smartphone in Ihrer Microsoft 365 Enterprise-testumgebung.
ms.openlocfilehash: aae493e79a197635b2e14fa7f238a3189ed695ae
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/28/2018
ms.locfileid: "26867561"
---
# <a name="multi-factor-authentication-for-your-microsoft-365-enterprise-test-environment"></a>Mehrstufige Authentifizierung für Microsoft 365 Unternehmen test Environment.

Für eine zusätzliche Sicherheitsebene für die Anmeldung Office 365 oder eine beliebige Dienst oder einer Anwendung, die für Ihre Organisation den Azure AD-Mandanten verwendet, können Sie Azure mehrstufige Authentifizierung, die erforderlich sind mehr als nur einen Benutzernamen und das Kennwort ein, vergewissern Sie sich ein Konto. Mehrstufige Authentifizierung müssen Benutzer ein Telefonanrufs zu bestätigen, geben Sie einen Überprüfungscode in einer Textnachricht gesendet oder geben Sie ein app-Kennwort in ihrer Smartphones nach Eingabe der Kennwörter, ordnungsgemäß. Sie können erst nach diesem zweiten Authentifizierung Faktor erfüllt wurden anmelden. 
  
In diesem Artikel wird beschrieben, wie aktivieren und Testen Sie die Text-basierten Authentifizierung für ein bestimmtes Konto.
  
Es gibt zwei Phasen mehrstufige Authentifizierung für ein Konto in Ihrer Microsoft 365 Enterprise-testumgebung einrichten:
  
1. Erstellen der testumgebung Microsoft 365 Enterprise.
    
2. Aktivieren und Testen von Multi-Factor Authentication für das Konto „Benutzer 2“

![Testumgebungsanleitungen für die Microsoft-Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> Klicken Sie [hier](https://aka.ms/m365etlgstack), um eine visuelle Darstellung aller Artikel im Stapel der Testumgebungsanleitungen in Microsoft 365 Enterprise zu erhalten.
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a>Phase 1: Erstellen Sie Ihre Umgebung für Microsoft 365 Enterprise

Wenn Sie auf einfache Weise mit den Mindestanforderungen mehrstufige Authentifizierung testen möchten, befolgen Sie die Anweisungen in der [Lightweight Basiskonfiguration](lightweight-base-configuration-microsoft-365-enterprise.md).
  
Wenn Sie in einer simulierten Enterprise mehrstufige Authentifizierung testen möchten, befolgen Sie die Anweisungen in [Pass-Through-Authentifizierung](pass-through-auth-m365-ent-test-environment.md).
  
> [!NOTE]
> Testen der mehrstufigen Authentifizierung erfordert keinen der simulierten Enterprise-testumgebung, einschließlich einer simulierten Intranet mit dem Internet verbunden und Directory-Synchronisierung für eine Windows Server Active Directory-Gesamtstruktur. Erfolgt hier als eine Option, damit können Sie mehrstufige Authentifizierung testen und probieren Sie es in einer Umgebung, die eine typische Organisation darstellt. 
  
## <a name="phase-2-enable-and-test-multi-factor-authentication-for-the-user-2-account"></a>Phase 2: Aktivieren und Testen von Multi-Factor Authentication für das Konto „Benutzer 2“

Aktivieren Sie Multi-Factor Authentication für das Konto „Benutzer 2“ mit den folgenden Schritten:
  
1. Öffnen Sie eine separate, private Instanz des Browsers, fahren Sie mit Office 365-Portal ([https://portal.office.com](https://portal.office.com)), und melden Sie sich mit Ihrem globale Administratorkonto ein.
    
2. Klicken Sie auf der Hauptportalseite auf **Admin**.
    
3. Klicken Sie im linken Navigationsbereich auf **Benutzer > Aktive Benutzer**.
    
4. Klicken Sie im Bereich aktive Benutzer klicken Sie auf **mehr > Multi-Factor Authentication Setup**.
    
5. Wählen Sie in der Liste der **Benutzer 2** -Konto aus.
    
6. Klicken Sie im Abschnitt **Benutzer 2** unter **QuickSteps** auf **Aktivieren**.
    
7. Klicken Sie im Dialogfeld **Informationen zum Aktivieren von mehrstufiger Aktualisierung** auf **Multi-Factor Authentication aktivieren**.
    
8. Klicken Sie auf **Schließen**, klicken Sie im Dialogfeld **erfolgreich aktualisiert** .
    
9. Klicken Sie auf der Registerkarte **Microsoft Office-Starts** auf das Benutzerkontosymbol in der oberen rechten Ecke, und klicken Sie dann auf **Abmelden**.
    
10. Schließen Sie Ihre Browserinstanz.
   
Schließen Sie die Konfiguration des Kontos „Benutzer 2“ für die Verwendung einer Textnachricht zur Prüfung ab, und testen Sie es mit den folgenden Schritten:
  
1. Öffnen Sie eine neue Instanz des Browsers private.
    
2. Wechseln Sie zu Office 365-Portal ([https://portal.office.com](https://portal.office.com)) und melden Sie sich mit dem Konto Benutzer 2 (Benutzer2 @\<Organisationsname >. onmicrosoft.com) und das Kennwort ein.
    
3. Nach der Anmeldung werden Sie aufgefordert, richten Sie das Konto für Weitere Informationen ein. Klicken Sie auf **Weiter**.
    
4. Führen Sie auf der Seite **Zusätzliche Sicherheitsüberprüfung** die folgenden Schritte aus: 
    
   - Wählen Sie Ihr Land oder Ihre Region aus.
    
   - Geben Sie die Telefonnummer des Smartphones ein, das Textnachrichten erhalten soll.
    
   - Klicken Sie in- **Methode**auf **mich senden einen Code über Textnachricht**.
    
5. Klicken Sie auf **Weiter**.
    
6. Geben Sie den Verifizierungscode aus der Textnachricht ein, die an Ihr Smartphone gesendet wurde, und klicken Sie dann auf **Überprüfen**.
    
7. Zeichnen Sie das auf der Seite **Schritt 3: Keep your existing applications** angezeigte App-Kennwort für das Konto „Benutzer 2“ an einem sicheren Ort auf, und klicken Sie dann auf **Fertig**.
    
8. Wenn dies das erste Mal ist, dass Sie sich mit dem Konto „Benutzer 2“ angemeldet haben, werden Sie aufgefordert, das Kennwort zu ändern. Geben Sie das ursprüngliche Kennwort und dann zwei Mal ein neues Kennwort ein, und klicken Sie dann auf **Kennwort ändern und anmelden**. Zeichnen Sie das neue Kennwort an einem sicheren Ort auf.
    
    Office 365-Portal sollte für Benutzer 2 auf der Registerkarte **Microsoft Office Home** des Browsers angezeigt werden.


Finden Sie im Schritt [Richten Sie mehrstufige Authentifizierung](identity-multi-factor-authentication.md) in der Phase Identität Informationen und Links zu Multi-Factor Authentication in der Produktion bereitstellen.
    
## <a name="next-step"></a>Nächster Schritt

Sehen Sie sich weitere [Identitäts](m365-enterprise-test-lab-guides.md#identity)features und- funktionen in Ihrer Testumgebung an.

## <a name="see-also"></a>Siehe auch

[Phase 2: Identität](identity-infrastructure.md)

[Testumgebungsanleitungen für Microsoft 365 Enterprise](m365-enterprise-test-lab-guides.md)

[Bereitstellung von Microsoft 365 Enterprise](deploy-microsoft-365-enterprise.md)

[Dokumentation zu Microsoft 365 Enterprise](https://docs.microsoft.com/microsoft-365-enterprise/)
