---
title: Schützen globaler Administratorkonten in Ihrer Microsoft 365 Enterprise-Testumgebung
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 04/16/2019
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-identity-device-management
ms.custom:
- TLG
- Ent_TLGs
description: Führen Sie die folgenden Schritte aus, um globale Administratorkonten in Ihrer Microsoft 365 Enterprise-Testumgebung zu schützen.
ms.openlocfilehash: cded424188447f96e5614f31d3e207bb541d438e
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32290858"
---
# <a name="protect-global-administrator-accounts-in-your-microsoft-365-enterprise-test-environment"></a>Schützen globaler Administratorkonten in Ihrer Microsoft 365 Enterprise-Testumgebung

Sie können digitale Angriffe auf Ihre Organisation verhindern, indem Sie sicherstellen, dass Ihre Administratorkonten so sicher wie möglich sind. In diesem Artikel wird beschrieben, wie Sie Office 365 Cloud App Security und Azure AD Conditional Access-Richtlinien zum Schutz globaler Administratorkonten verwenden.

Es gibt zwei Phasen zum Schutz globaler Administratorkonten in Ihrer Microsoft 365 Enterprise-Testumgebung:

1.  Erstellen Sie die Microsoft 365 Enterprise-Testumgebung.
2.  Schützen Sie Ihr dediziertes globales Administratorkonto.

![Testumgebungsanleitungen für die Microsoft-Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> Klicken Sie [hier](https://aka.ms/m365etlgstack), um eine visuelle Darstellung aller Artikel im Stapel der Testumgebungsanleitungen in Microsoft 365 Enterprise zu erhalten.

> [!NOTE]
> In der Microsoft 365 Enterprise-Testumgebung werden E5-Versionen von Office 365 und Enterprise Management + Security (EMS) verwendet. Die Office 365 Cloud App-Sicherheitsfunktion ist nur in der E5-Version von Office 365 verfügbar. 

## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a>Phase 1: Erstellen Ihrer Microsoft 365 Enterprise-Testumgebung

Wenn Sie nur den Schutz globaler Administratorkonten auf einfache Weise mit den Mindestanforderungen testen möchten, befolgen Sie die Anweisungen unter [Lightweight Base Configuration](lightweight-base-configuration-microsoft-365-enterprise.md).
  
Wenn Sie den Schutz globaler Administratorkonten in einem simulierten Unternehmen testen möchten, befolgen Sie die Anweisungen unter [Passthrough-Authentifizierung](pass-through-auth-m365-ent-test-environment.md).

  
> [!NOTE]
> Das Testen des globalen Administratorkonto Schutzes erfordert nicht die simulierte Enterprise-Testumgebung, die ein simuliertes Intranet enthält, das mit dem Internet und der Verzeichnissynchronisierung für eine Active Directory-Domänendienste (AD DS) verbunden ist. Sie wird hier als Option bereitgestellt, damit Sie den Schutz globaler Administratorkonten testen und mit dieser in einer Umgebung experimentieren können, die eine typische Organisation darstellt. 
  
## <a name="phase-2-configure-cloud-app-security-and-conditional-access-policies"></a>Phase 2: Konfigurieren von Sicherheits-und bedingten Zugriffsrichtlinien für Cloud-apps

Erstellen Sie zunächst eine Office 365 Cloud App-Sicherheitsrichtlinie, um die globale Administratorkonto Aktivität zu überwachen und Warnungen an die e-Mail-Adresse Ihres globalen Administratorkontos zu senden. 

1. Melden Sie sich beim [Office 365 Security _AMP_ Compliance-Portal](https://protection.office.com/) mit ihrem globalen Administratorkonto an.
2. Klicken Sie im linken Navigationsbereich auf **Warnungen > Erweiterte Warnungen verwalten**.
3. Klicken Sie auf der Seite **Erweiterte Warnungen verwalten** auf **Office 365 Cloud App Security aktivieren**, und klicken Sie dann auf **Zu Office 365 Cloud App Security wechseln**.
4. Klicken Sie auf der neuen **Dashboard**-Registerkarte auf **Steuern > Richtlinien**.
5. Klicken Sie auf der Seite **Richtlinie** auf **Richtlinie erstellen**, und klicken Sie dann auf **Aktivitätsrichtlinie**.
6. Geben Sie im Feld **Richtlinienname** den Namen **Administrative Aktivität** ein.
7. Klicken Sie unter **Schweregrad der Richtlinie** auf **Hoch**.
8. Klicken Sie unter **Kategorie** auf **Privilegierte Konten**.
9. Klicken Sie in **Filter für die Richtlinie erstellen** unter **Aktivitäten entspricht allen folgenden Kriterien** auf **Administrative Aktivität**.
10. Klicken Sie unter **Benachrichtigungen** auf **Benachrichtigung als E-Mail senden**. Geben Sie unter **An** die E-Mail-Adresse Ihres globalen Administratorkontos ein.
11. Klicken Sie unten auf der Seite auf **Erstellen**.
12. Schließt die Registerkarte **Dashboard** .
    
Als Nächstes erstellen Sie ein neues Benutzerkonto als dedizierter globaler Administrator.

1. Öffnen Sie auf einer separaten Registerkarte das [Microsoft 365 Admin Center](https://admin.microsoft.com/).
2. Klicken Sie unter **aktive Benutzer**auf **Benutzer hinzufügen**.
3. Geben Sie auf der Seite **neuer Benutzer** **DedicatedAdmin** unter **Vorname**, **Anzeigename**und **Benutzer**Name ein.
4. Klicken Sie auf **Kennwort**, aktivieren Sie **das Kennwort erstellen**, und geben Sie dann ein sicheres Kennwort ein. NoTieren Sie sich das Kennwort für dieses neue Konto an einem sicheren Ort.
5. Deaktivieren **Sie dieses Benutzerkennwort bei der ersten Anmeldung ändern**.
6. Klicken Sie auf **Rollen**, und klicken Sie dann auf **globaler Administrator**.
7. Klicken Sie auf **Produktlizenzen**und dann auf **Enterprise Mobility + Security e5** und **Office 365 Enterprise E5** .
8. Klicken Sie auf **Hinzufügen**.
9. Deaktivieren Sie auf der **Seite hinzugefügte Benutzer**das **Kennwort in e-Mail senden**, und klicken Sie dann auf **Schließen**.

Erstellen Sie als nächstes eine neue Gruppe mit dem Namen GlobalAdmins, und fügen Sie Ihr das DedicatedAdmin-Konto hinzu.

1. Klicken Sie auf der Registerkarte **Microsoft 365 Admin Center** in der linken Navigationsleiste auf das Symbol Gruppen, und klicken Sie dann auf **Gruppen**.
2. Klicken Sie auf **Gruppe hinzufügen**.
3. Geben Sie auf der Seite **neue Gruppe** **GlobalAdmins**.
4. Klicken Sie auf **Besitzer auswählen** , klicken Sie auf ihr globales Administratorkonto, und klicken Sie dann auf **> schließen**.
5. Klicken Sie in der Liste der Gruppen auf die Gruppe **GlobalAdmins** .
6. Klicken Sie auf der Seite **GlobalAdmins** auf **für Mitglied bearbeiten**, und klicken Sie dann auf **Mitglieder hinzufügen**.
7. Klicken Sie in der Liste auf das **DedicatedAdmin** -Konto, und klicken Sie dann auf **Speichern _GT_ schließen _GT_ schließen > Admin Center**.

Erstellen Sie als nächstes Richtlinien für bedingten Zugriff, um die mehrstufige Authentifizierung für globale Administratorkonten zu erfordern, und um die Authentifizierung zu verweigern, wenn das Anmelde Risiko Mittel oder hoch ist.

Diese erste Richtlinie erfordert, dass alle globalen Administratorkonten MFA verwenden.

1. Wechseln Sie auf einer neuen Registerkarte Ihres Browsers zu [https://portal.azure.com](https://portal.azure.com).
2. Klicken Sie auf **Azure Active Directory _GT_ Conditional Access**.
3. Klicken Sie auf dem Blatt **bedingte Zugriffsrichtlinien** auf **Basisrichtlinie: MFA für Administratoren (Vorschau) erforderlich**.
4. In den **Basisrichtlinien...** auf **Richtlinie sofort _GT_ speichern**.

Diese zweite Richtlinie blockiert den Zugriff auf die globale Administratorkonto Authentifizierung, wenn das Anmelde Risiko Mittel oder hoch ist.

1. Klicken Sie auf dem Blatt **bedingte Zugriffsrichtlinien** auf **neue Richtlinie**.
2. Geben Sie auf dem **neuen** Blatt **globale Administratoren** in **Name**ein.
3. Klicken Sie **** im Abschnitt Zuweisungen auf **Benutzer und Gruppen**.
4. Klicken Sie auf der Registerkarte " **einbeziehen** " des Blades " **Benutzer und Gruppen** " auf Benutzer und Gruppen **_GT_ Benutzer und Gruppen > auswählen**.
5. Klicken Sie auf dem Blade **auswählen** auf die **GlobalAdmins > wählen Sie > fertig**aus.
6. Klicken Sie **** im Abschnitt Zuweisungen auf **Bedingungen**.
7. Klicken Sie auf dem Blatt **Bedingungen** auf **Anmelde Risiko**, klicken Sie **auf Ja** , um zu **Konfigurieren**, klicken Sie auf **hoch** und **Mittel**, und klicken Sie dann auf **auswählen** und **Fertig**.
8. Klicken Sie im Abschnitt **Zugriffssteuerung** des **neuen** Blatts auf **erteilen**.
9. Klicken Sie auf der **Grant** -Blade auf **Zugriff blockieren**, und klicken Sie dann auf **auswählen**.
10. Klicken Sie auf dem **neuen** Blade **** auf für **Richtlinie aktivieren**, und klicken Sie dann auf **Erstellen**.
11. Beenden Sie die Registerkarten **Azure Portal** und **Microsoft 365 Admin Center** .

Um die erste Richtlinie zu testen, melden Sie sich ab und melden Sie sich mit dem DedicatedAdmin-Konto an. Sie sollten aufgefordert werden, MFA für das Benutzerkonto zu konfigurieren. Dies zeigt, dass die erste Richtlinie angewendet wird.

Weitere Informationen und Links zum Schutz ihrer globalen Administratorkonten in der Produktion finden Sie unter [Schützen von globalen Administratorkonten](identity-designate-protect-admin-accounts.md#identity-global-admin) .

## <a name="next-step"></a>Nächster Schritt

Sehen Sie sich weitere [Identitäts](m365-enterprise-test-lab-guides.md#identity)features und- funktionen in Ihrer Testumgebung an.

## <a name="see-also"></a>Siehe auch

[Phase 2: Identität](identity-infrastructure.md)

[Testumgebungsanleitungen für Microsoft 365 Enterprise](m365-enterprise-test-lab-guides.md)

[Microsoft 365 Enterprise-Bereitstellung](deploy-microsoft-365-enterprise.md)

[Dokumentation zu Microsoft 365 Enterprise](https://docs.microsoft.com/microsoft-365-enterprise/)
