---
title: Schützen globaler Administratorkonten in Ihrer Microsoft 365 Enterprise-Testumgebung
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 04/16/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-identity-device-management
ms.custom:
- TLG
- Ent_TLGs
description: Verwenden Sie diese Schritte, um globale Administratorkonten in Ihrer Microsoft 365 Enterprise-Testumgebung zu schützen.
ms.openlocfilehash: 457ac33aa2242dc4b25cd662bf233bb1599a6fec
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/20/2019
ms.locfileid: "37071554"
---
# <a name="protect-global-administrator-accounts-in-your-microsoft-365-enterprise-test-environment"></a>Schützen globaler Administratorkonten in Ihrer Microsoft 365 Enterprise-Testumgebung

Sie können digitale Angriffe in Ihrer Organisation verhindern, indem Sie sicherstellen, dass Ihre Administratorkonten so sicher wie möglich sind. In diesem Artikel wird beschrieben, wie Sie mithilfe von Azure Active Directory (Azure AD) bedingten Zugriffsrichtlinien globale Administratorkonten schützen.

Es gibt zwei Phasen zum Schutz globaler Administratorkonten in Ihrer Microsoft 365 Enterprise-Testumgebung:

1.  Erstellen Sie die Microsoft 365 Enterprise-Testumgebung.
2.  Schützen Sie Ihr dediziertes globales Administratorkonto.

![Testumgebungsanleitungen für die Microsoft-Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> Klicken Sie [hier](https://aka.ms/m365etlgstack), um eine visuelle Darstellung aller Artikel im Stapel der Testumgebungsanleitungen in Microsoft 365 Enterprise zu erhalten.

## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a>Phase 1: Erstellen der Microsoft 365 Enterprise-Testumgebung

Wenn Sie lediglich den Schutz des globalen Administratorkontos auf einfache Weise mit den Mindestanforderungen testen möchten, befolgen Sie die Anweisungen unter [Lightweight Base Configuration](lightweight-base-configuration-microsoft-365-enterprise.md).
  
Wenn Sie den Schutz des globalen Administratorkontos in einem simulierten Unternehmen testen möchten, befolgen Sie die Anweisungen unter [Pass-Through-Authentifizierung](pass-through-auth-m365-ent-test-environment.md).

  
> [!NOTE]
> Zum Testen des Schutzes globaler Administratorkonten ist keine simulierte Enterprise-Testumgebung erforderlich, die ein simuliertes, mit dem Internet verbundenes Intranet und eine Verzeichnissynchronisierung für ein Active Directory-Domänendienste (AD DS) enthält. Sie wird hier als Option bereitgestellt, damit Sie den Schutz globaler Administratorkonten testen und mit dieser in einer Umgebung experimentieren können, die eine typische Organisation repräsentiert. 
  
## <a name="phase-2-configure-conditional-access-policies"></a>Phase 2: Konfigurieren von Richtlinien für bedingten Zugriff

Erstellen Sie zunächst ein neues Benutzerkonto als dedizierter globaler Administrator.

1. Öffnen Sie auf einer separaten Registerkarte das [Microsoft 365 Admin Center](https://admin.microsoft.com/).
2. Klicken Sie unter **aktive Benutzer**auf **Benutzer hinzufügen**.
3. Geben Sie auf der Seite **neuer Benutzer** **DedicatedAdmin** in **Vorname**, **Anzeigename**und **Benutzer**Name ein.
4. Klicken Sie auf **Kennwort**, klicken Sie auf **das Kennwort erstellen**, und geben Sie dann ein sicheres Kennwort ein. Notieren Sie sich das Kennwort für dieses neue Konto an einem sicheren Ort.
5. Deaktivieren **Sie, dass dieser Benutzer sein Kennwort bei der ersten Anmeldung ändert**.
6. Klicken Sie auf **Rollen**, und klicken Sie dann auf **globaler Administrator**.
7. Klicken Sie auf **Produktlizenzen**, und schalten Sie dann die Lizenzen **Enterprise Mobility + Security E5** und **Office 365 Enterprise E5** ein.
8. Klicken Sie auf **Hinzufügen**.
9. Deaktivieren Sie auf der **Seite Benutzer wurde hinzugefügt die Seite** **Kennwort in e-Mail senden**, und klicken Sie dann auf **Schließen**.

Erstellen Sie als nächstes eine neue Gruppe mit dem Namen GlobalAdmins, und fügen Sie Ihr das DedicatedAdmin-Konto hinzu.

1. Klicken Sie auf der Registerkarte **Microsoft 365 Admin Center** auf das Symbol Gruppen in der linken Navigationsleiste, und klicken Sie dann auf **Gruppen**.
2. Klicken Sie auf **Gruppe hinzufügen**.
3. Geben Sie auf der Seite **neue Gruppe** **GlobalAdmins**.
4. Klicken Sie auf **Besitzer auswählen** klicken Sie auf ihr globales Administratorkonto, und klicken Sie dann auf **#a0 schließen hinzufügen**.
5. Klicken Sie in der Liste der Gruppen auf die Gruppe **GlobalAdmins** .
6. Klicken Sie auf der Seite **GlobalAdmins** auf **für Mitglied bearbeiten**, und klicken Sie dann auf **Mitglieder hinzufügen**.
7. Klicken Sie in der Liste auf das Konto **DedicatedAdmin** , und klicken Sie dann auf **speichern #a0 schließen #a1 #a2 Admin Center schließen**.

Erstellen Sie als nächstes Richtlinien für bedingten Zugriff, um mehrstufige Authentifizierung für globale Administratorkonten zu erfordern, und um die Authentifizierung zu verweigern, wenn das Anmelde Risiko Mittel oder hoch ist.

Für diese erste Richtlinie müssen alle globalen Administratorkonten MFA verwenden.

1. Wechseln Sie auf einer neuen Registerkarte Ihres Browsers zu [https://portal.azure.com](https://portal.azure.com).
2. Klicken Sie auf **Azure Active Directory #a0 bedingten Zugriff**.
3. Klicken Sie auf dem Blatt **bedingter Zugriff – Richtlinien** auf **Baseline-Richtlinie: MFA für Administratoren erforderlich (Vorschau)**.
4. Auf den **Basisrichtlinien...** auf **Richtlinie sofort verwenden #a0 speichern**.

Diese zweite Richtlinie blockiert den Zugriff auf die Authentifizierung des globalen Administratorkontos, wenn das Anmelde Risiko Mittel oder hoch ist.

1. Klicken Sie auf dem Blatt **bedingter Zugriff – Richtlinien** auf **neue Richtlinie**.
2. Geben Sie auf dem **neuen** Blade **globale Administratoren** in **Name**ein.
3. Klicken Sie im Abschnitt **Zuweisungen** auf **Benutzer und Gruppen**.
4. Klicken Sie auf der Registerkarte **einschließen** des Blades **Benutzer und Gruppen** auf **Benutzer und Gruppen #a0 Benutzer und Gruppen auswählen #a1 auswählen**.
5. Klicken Sie auf dem Blatt **auswählen** auf **GlobalAdmins #a0 wählen Sie #a1 fertig**aus.
6. Klicken Sie im Abschnitt **Zuweisungen** auf **Bedingungen**.
7. Klicken Sie auf dem Blatt **Bedingungen** auf **Anmelde Risiko**, klicken Sie **auf Ja** für **configure**, klicken Sie auf **hoch** und **Mittel**, und klicken Sie dann auf **auswählen** und **Fertig**.
8. Klicken Sie im Abschnitt **Zugriffssteuerung** des **neuen** Blades auf **erteilen**.
9. Klicken Sie auf dem Blatt **Grant** auf **Zugriff blockieren**, und klicken Sie dann auf **auswählen**.
10. Klicken Sie auf dem **neuen** Blade **auf für die** **Option Richtlinie aktivieren**, und klicken Sie dann auf **Erstellen**.
11. Schließen Sie die Registerkarten **Azure-Portal** und **Microsoft 365 Admin Center** .

Um die erste Richtlinie zu testen, melden Sie sich ab, und melden Sie sich mit dem DedicatedAdmin-Konto an. Sie sollten aufgefordert werden, MFA für das Benutzerkonto zu konfigurieren. Dies zeigt, dass die erste Richtlinie angewendet wird.

Informationen und Links zum Schutz ihrer globalen Administratorkonten in der Produktion finden Sie unter [Protect Global Administrator Accounts](identity-create-protect-global-admins.md#identity-global-admin) Step in the Identity Phase.

## <a name="next-step"></a>Nächster Schritt

Sehen Sie sich weitere [Identitäts](m365-enterprise-test-lab-guides.md#identity)features und- funktionen in Ihrer Testumgebung an.

## <a name="see-also"></a>Siehe auch

[Phase 2: Identität](identity-infrastructure.md)

[Testumgebungsanleitungen für Microsoft 365 Enterprise](m365-enterprise-test-lab-guides.md)

[Microsoft 365 Enterprise-Bereitstellungshandbuch](deploy-microsoft-365-enterprise.md)

[Dokumentation zu Microsoft 365 Enterprise](https://docs.microsoft.com/microsoft-365-enterprise/)
