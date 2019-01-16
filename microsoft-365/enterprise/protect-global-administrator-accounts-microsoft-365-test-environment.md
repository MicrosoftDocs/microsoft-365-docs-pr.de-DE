---
title: Schützen von Konten in Ihrer unternehmensumgebung Microsoft 365 Test globaler administrator
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
description: Verwenden Sie diese Schritte, um globale Administratorkonten in Ihrer unternehmensumgebung Microsoft 365 Test zu schützen.
ms.openlocfilehash: 4d444e217c5a232811701f6519c2eb3ebe86df70
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/16/2019
ms.locfileid: "26867582"
---
# <a name="protect-global-administrator-accounts-in-your-microsoft-365-enterprise-test-environment"></a>Schützen von Konten in Ihrer unternehmensumgebung Microsoft 365 Test globaler administrator

Sie können digitale Angriffe auf Ihre Organisation verhindern, indem Sie sicherstellen, dass Ihre Administratorkonten so sicher wie möglich sind. In diesem Artikel wird beschrieben, wie mit Office 365-Cloud-App-Sicherheit und Azure AD bedingte Zugriffsrichtlinien globale Administratorkonten schützen.

Es gibt zwei Phasen zum Schützen von Konten in Ihrer unternehmensumgebung Microsoft 365 Test globaler Administrator:

1.  Erstellen der testumgebung Microsoft 365 Enterprise.
2.  Schützen Sie Ihre dedizierten globale Administratorkonto ein.

![Testumgebungsanleitungen für die Microsoft-Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> Klicken Sie [hier](https://aka.ms/m365etlgstack), um eine visuelle Darstellung aller Artikel im Stapel der Testumgebungsanleitungen in Microsoft 365 Enterprise zu erhalten.
  

## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a>Phase 1: Erstellen Sie Ihre Umgebung für Microsoft 365 Enterprise

Wenn Sie auf einfache Weise mit den Mindestanforderungen globaler Administrator Kontoschutz testen möchten, befolgen Sie die Anweisungen in der [Lightweight Basiskonfiguration](lightweight-base-configuration-microsoft-365-enterprise.md).
  
Wenn Sie in einer simulierten Enterprise globaler Administrator Kontoschutz testen möchten, befolgen Sie die Anweisungen in [Pass-Through-Authentifizierung](pass-through-auth-m365-ent-test-environment.md).
  
> [!NOTE]
> Testen globale Administratorkonto ein Protection erfordert nicht den simulierten Enterprise Test Environment, einem simulierten Intranet umfasst Folgendes mit dem Internet verbunden und Directory-Synchronisierung für eine Windows Server Active Directory-Gesamtstruktur. Erfolgt hier als eine Option, damit können Sie globaler Administrator Kontoschutz testen und probieren Sie es in einer Umgebung, die eine typische Organisation darstellt. 
  
## <a name="phase-2-configure-cloud-app-security-and-conditional-access-policies"></a>Phase 2: Konfigurieren von Cloud-App Sicherheits- und bedingte Zugriffsrichtlinien

Erstellen Sie zunächst eine Richtlinie Office 365-Cloud-App-Sicherheit, um globaler Administrator Kontoaktivitäten überwachen und Senden von Benachrichtigungen an die e-Mail-Adresse des globalen Administratorkontos. 

1. Melden Sie sich bei der Office-Portal unter [http://portal.office.com](http://portal.office.com) mit Ihrer globalen Administratorkonto an.
2. Klicken Sie auf die Kachel " **Admin** ". Klicken Sie auf die Registerkarte **Office Admin Center** auf **Zentriert Admin > Sicherheit und Compliance**.
3. Klicken Sie im linken Navigationsbereich auf **Warnungen > Erweiterte Warnungen verwalten**.
4. Klicken Sie auf der Seite **Erweiterte Warnungen verwalten** auf **Office 365 Cloud App Security aktivieren**, und klicken Sie dann auf **Zu Office 365 Cloud App Security wechseln**.
5. Klicken Sie auf der neuen **Dashboard**-Registerkarte auf **Steuern > Richtlinien**.
6. Klicken Sie auf der Seite **Richtlinie** auf **Richtlinie erstellen**, und klicken Sie dann auf **Aktivitätsrichtlinie**.
7. Geben Sie im Feld **Richtlinienname** den Namen **Administrative Aktivität** ein.
8. Klicken Sie unter **Schweregrad der Richtlinie** auf **Hoch**.
9. Klicken Sie unter **Kategorie** auf **Privilegierte Konten**.
10. Klicken Sie in **Filter für die Richtlinie erstellen** unter **Aktivitäten entspricht allen folgenden Kriterien** auf **Administrative Aktivität**.
11. Klicken Sie unter **Benachrichtigungen** auf **Benachrichtigung als E-Mail senden**. Geben Sie unter **An** die E-Mail-Adresse Ihres globalen Administratorkontos ein.
12. Klicken Sie unten auf der Seite auf **Erstellen**.
13. Schließen Sie die Registerkarte **Dashboard** .
    
Im nächsten Schritt erstellen Sie ein neues Benutzerkonto als dedizierten globaler Administrator.

1. Klicken Sie auf der Registerkarte **Office Admin Center** unter **aktive Benutzer**auf **Benutzer hinzufügen**.
2. Geben Sie auf der Seite **Neuer Benutzer** **DedicatedAdmin** in **Vorname**, **Anzeigename**und **Username**.
3. Klicken Sie auf **Kennwort**, klicken Sie auf **mich das Kennwort zu erstellen**, und geben Sie ein sicheres Kennwort. Tragen Sie das Kennwort für das neue Konto an einem sicheren Ort.
4. Deaktivieren **Sie dieser Benutzer ändern ihres Kennworts beim erstmaligen Anmelden ist**.
5. Klicken Sie auf **Rollen**, und klicken Sie dann auf **globaler Administrator**.
6. Klicken Sie auf **Produktlizenzen**, und schalten Sie die **Enterprise-Mobilität + Sicherheit E5** und **Office 365 Enterprise E5 Lizenzen** .
7. Klicken Sie auf **Hinzufügen**.
8. Klicken Sie auf die **Benutzer Seite hinzugefügt wurde**deaktivieren Sie **das Kennwort in e-Mail senden**, und klicken Sie dann auf **Schließen**.

Im nächsten Schritt erstellen Sie eine neue Gruppe mit dem Namen GlobalAdmins, und fügen Sie das Konto DedicatedAdmin hinzu.

1. Klicken Sie auf das Gruppensymbol im linken Navigationsbereich auf der Registerkarte **Office-Verwaltungskonsole** , und klicken Sie dann auf **Gruppen**.
2. Klicken Sie auf **Gruppe hinzufügen**.
3. Geben Sie auf der Seite **Neue Gruppe** **GlobalAdmins**.
4. Klicken Sie auf **Select Besitzer** auf das globale Administratorkonto ein, und klicken Sie dann auf **Hinzufügen > Schließen**.
5. Klicken Sie in der Liste der Gruppen auf die Gruppe **GlobalAdmins** .
6. Klicken Sie auf der Seite **GlobalAdmins** auf **Element bearbeiten**, und klicken Sie dann auf **Mitglieder hinzufügen**.
7. In der Liste, klicken Sie auf das Konto **DedicatedAdmin** , und klicken Sie dann auf **Speichern > Schließen > Schließen > Administrationscenter**.

Erstellen Sie als Nächstes bedingte Zugriffsrichtlinien für globale Administratorkonten mehrstufige Authentifizierung erforderlich ist und Authentifizierung verweigern, wenn das Risiko-Anmeldung Mittel oder hoch ist.

Diese erste Richtlinie erfordert, dass alle globalen Administratorkonten mehrstufiger Authentifizierung das verwenden.

1. Wechseln Sie in einer neuen Registerkarte Ihres Browsers zu [https://portal.azure.com](https://portal.azure.com).
2. Klicken Sie auf **Azure Active Directory > bedingten Zugriff**.
3. Klicken Sie auf das Blade **bedingte – Richtlinien Zugriff** auf **Baseline-Richtlinie: erfordern mehrstufiger Authentifizierung das für Administratoren (Preview)**.
4. Klicken Sie auf das Blade **... Baseline-Richtlinien** auf **Verwenden Sie die Richtlinie sofort > Speichern**.

In diesem zweiten Richtlinie blockiert den Zugriff auf globaler Administrator Kontoauthentifizierung bei das Anmeldung Risiko Mittel oder hoch ist.

1. Klicken Sie auf das Blade **bedingte – Richtlinien Zugriff** auf **neue Richtlinie**.
2. Geben Sie auf der Blade **New** **globale Administratoren** im **Feld Name**ein.
3. Klicken Sie im Abschnitt **Zuordnungen** auf **Benutzer und Gruppen**.
4. Klicken Sie auf der Registerkarte **einschließen** von der Blade- **Benutzer und Gruppen** auf **Benutzer und Gruppen auswählen > Benutzer und Gruppen > Wählen Sie**.
5. Klicken Sie auf das Blade **Wählen Sie** auf der **GlobalAdmins > Wählen Sie > Fertig**.
6. Klicken Sie im Abschnitt **Zuordnungen** auf **Bedingungen**.
7. Klicken Sie in der Blade **Bedingungen** auf **Anmelden Risiko**, klicken Sie auf **Ja** , für die **Konfiguration**, klicken Sie auf **Hoch** und **Mittel**und klicken Sie dann auf **auswählen** und **Fertig**.
8. Klicken Sie im Abschnitt **Zugreifen auf Steuerelemente** von der **neu** Blade auf **erteilen**.
9. Klicken Sie in der **Grant** -Blade auf **Blockieren Sie den Zugriff**, und klicken Sie dann auf **auswählen**.
10. Klicken Sie auf das Blade **neu** **auf** für die **Richtlinie zu aktivieren**, und klicken Sie dann auf **Erstellen**.
11. Schließen Sie die Registerkarten **Azure-Portal** und **Office-Verwaltungskonsole** .

Um die erste Richtlinie zu testen, melden Sie sich ab, und melden Sie sich mit dem Konto DedicatedAdmin. Sie werden aufgefordert, auf das Benutzerkonto mehrstufiger Authentifizierung das konfigurieren. Dies veranschaulicht, dass die erste Richtlinie angewendet wird.

Finden Sie unter der [globalen Administratorkonten Protect](identity-designate-protect-admin-accounts.md) Schritt in der Phase Identität Informationen und Links zu Ihrer globalen Administratorkonten in der Produktion zu schützen.

## <a name="next-step"></a>Nächster Schritt

Sehen Sie sich weitere [Identitäts](m365-enterprise-test-lab-guides.md#identity)features und- funktionen in Ihrer Testumgebung an.

## <a name="see-also"></a>Siehe auch

[Phase 2: Identität](identity-infrastructure.md)

[Testumgebungsanleitungen für Microsoft 365 Enterprise](m365-enterprise-test-lab-guides.md)

[Bereitstellung von Microsoft 365 Enterprise](deploy-microsoft-365-enterprise.md)

[Dokumentation zu Microsoft 365 Enterprise](https://docs.microsoft.com/microsoft-365-enterprise/)
