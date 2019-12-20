---
title: Schützen globaler Administratorkonten in Ihrer Microsoft 365 Enterprise-Testumgebung
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
description: Verwenden Sie diese Schritte, um globale Administratorkonten in Ihrer Microsoft 365 Enterprise-Testumgebung zu schützen.
ms.openlocfilehash: 32e5983532c89c6ada106ed32d8ef3eabd5dc569
ms.sourcegitcommit: 0ad0092d9c5cb2d69fc70c990a9b7cc03140611b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/19/2019
ms.locfileid: "40801390"
---
# <a name="protect-global-administrator-accounts-in-your-microsoft-365-enterprise-test-environment"></a>Schützen globaler Administratorkonten in Ihrer Microsoft 365 Enterprise-Testumgebung

*Diese Testumgebungsanleitung kann nur für Microsoft 365 Enterprise-Testumgebungen verwendet werden.*

Sie können digitale Angriffe in Ihrer Organisation verhindern, indem Sie sicherstellen, dass Ihre Administratorkonten so sicher wie möglich sind. In diesem Artikel wird beschrieben, wie Sie mithilfe von Azure Active Directory (Azure AD) bedingten Zugriffsrichtlinien globale Administratorkonten schützen.

Es gibt zwei Phasen zum Schutz globaler Administratorkonten in Ihrer Microsoft 365 Enterprise-Testumgebung:

1.  Erstellen Sie die Microsoft 365 Enterprise-Testumgebung.
2.  Schützen Sie Ihr dediziertes globales Administratorkonto.

![Testumgebungsanleitungen für die Microsoft-Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> Klicken Sie [hier](media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf), um eine visuelle Darstellung aller Artikel im Stapel der Testumgebungsanleitungen in Microsoft 365 Enterprise zu erhalten.

## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a>Phase 1: Erstellen Ihrer Microsoft 365 Enterprise-Testumgebung

Wenn Sie lediglich den Schutz des globalen Administratorkontos auf einfache Weise mit den Mindestanforderungen testen möchten, befolgen Sie die Anweisungen unter [Lightweight Base Configuration](lightweight-base-configuration-microsoft-365-enterprise.md).
  
Wenn Sie den Schutz des globalen Administratorkontos in einem simulierten Unternehmen testen möchten, befolgen Sie die Anweisungen unter [Pass-Through-Authentifizierung](pass-through-auth-m365-ent-test-environment.md).
  
> [!NOTE]
> Zum Testen des Schutzes globaler Administratorkonten ist keine simulierte Enterprise-Testumgebung erforderlich, die ein simuliertes, mit dem Internet verbundenes Intranet und eine Verzeichnissynchronisierung für ein Active Directory-Domänendienste (AD DS) enthält. Sie wird hier als Option bereitgestellt, damit Sie den Schutz globaler Administratorkonten testen und mit dieser in einer Umgebung experimentieren können, die eine typische Organisation repräsentiert. 
  
## <a name="phase-2-configure-conditional-access-policies"></a>Phase 2: Konfigurieren von Richtlinien für bedingten Zugriff

Erstellen Sie zunächst ein neues Benutzerkonto als dedizierter globaler Administrator.

1. Öffnen Sie auf einer separaten Registerkarte das [Microsoft 365 Admin Center](https://admin.microsoft.com/).
2. Klicken Sie auf **Benutzer #a0 aktive Benutzer**, und klicken Sie dann auf **Benutzer hinzufügen**.
3. Geben Sie im Bereich **Benutzer hinzufügen** **DedicatedAdmin** in **Vorname**, **Anzeigename**und **Benutzer**Name ein.
4. Klicken Sie auf **Kennwort**, klicken Sie auf **das Kennwort erstellen**, und geben Sie dann ein sicheres Kennwort ein. Notieren Sie sich das Kennwort für dieses neue Konto an einem sicheren Ort.
5. Klicken Sie auf **Weiter**.
6. Wählen Sie im Bereich **Produktlizenzen zuweisen** die Option **Microsoft 365 E5** oder **Office 365 E5**aus, und klicken Sie dann auf **weiter**.
7. Klicken Sie im Bereich **Optionale Einstellungen** auf **Rollen**, und wählen Sie dann **Admin Center-Zugriff** und **globaler Administrator**aus. Klicken Sie auf **weiter**.
8. Klicken Sie im Bereich **Sie sind fast fertig** auf **Hinzufügen fertig stellen**, und klicken Sie dann auf **Schließen**.

Erstellen Sie als nächstes eine neue Gruppe mit dem Namen GlobalAdmins, und fügen Sie Ihr das DedicatedAdmin-Konto hinzu.

1. Klicken Sie auf der Registerkarte **Microsoft 365 Admin Center** im linken Navigationsbereich auf **Gruppen** , und klicken Sie dann auf **Gruppen**.
2. Klicken Sie auf **Gruppe hinzufügen**.
3. Wählen Sie im Bereich **Gruppentyp auswählen** die Option **Sicherheit**aus, und klicken Sie dann auf **weiter**.
4. Klicken Sie im Bereich **Grundlagen einrichten** auf **Gruppe erstellen**, und klicken Sie dann auf **Schließen**.
5. Geben Sie im Bereich **überprüfen und Abschließen der Gruppe hinzufügen** **GlobalAdmins**ein, und klicken Sie dann auf **weiter**.
7. Klicken Sie in der Liste der Gruppen auf die Gruppe **GlobalAdmins** .
8. Klicken Sie im Bereich **GlobalAdmins** auf **Mitglieder**, und klicken Sie dann auf **Alle anzeigen und Mitglieder verwalten**.
9. Klicken Sie im Bereich **GlobalAdmins** auf **Mitglieder hinzufügen**, wählen Sie das **DedicatedAdmin** -Konto und ihr globales Administratorkonto aus, und klicken Sie dann auf **speichern #a0 schließen #a1 schließen**.

Erstellen Sie als nächstes Richtlinien für bedingten Zugriff, um mehrstufige Authentifizierung für globale Administratorkonten zu erfordern, und um die Authentifizierung zu verweigern, wenn das Anmelde Risiko Mittel oder hoch ist.

Für diese erste Richtlinie müssen alle globalen Administratorkonten MFA verwenden.

1. Wechseln Sie auf einer neuen Registerkarte Ihres Browsers zu [https://portal.azure.com](https://portal.azure.com).
2. Klicken Sie auf **Azure Active Directory #a0 Sicherheits #a1 bedingten Zugriff**.
3. Klicken Sie im Bereich **bedingter Zugriff – Richtlinien** auf **Baseline-Richtlinie: MFA für Administratoren erfordern (Vorschau)**.
4. Klicken Sie im Bereich **Basisrichtlinie** auf **Richtlinie sofort #a0 speichern verwenden**.

Diese zweite Richtlinie blockiert den Zugriff auf die Authentifizierung des globalen Administratorkontos, wenn das Anmelde Risiko Mittel oder hoch ist.

1. Klicken Sie im Bereich **bedingter Zugriff – Richtlinien** auf **neue Richtlinie**.
2. Geben Sie im **neuen** Bereich **globale Administratoren** in **Name**ein.
3. Klicken Sie im Abschnitt **Zuweisungen** auf **Benutzer und Gruppen**.
4. Klicken Sie im Bereich **Benutzer und Gruppen** auf der Registerkarte **einschließen** auf Benutzer und Gruppen **#a0 Benutzer und Gruppen auswählen #a1 auswählen**.
5. Klicken Sie im Bereich **auswählen** auf die Gruppe **GlobalAdmins** , und klicken Sie dann auf **#a0 fertig wählen**.
6. Klicken Sie im Abschnitt **Zuweisungen** auf **Bedingungen**.
7. Klicken Sie im Bereich **Bedingungen** auf **Anmelde Risiko**, klicken Sie auf **Ja** für **configure**, klicken Sie auf **hoch** und **Mittel**, und klicken Sie dann auf **auswählen** und **Fertig**.
8. Klicken Sie im Abschnitt **Zugriffssteuerung** des **neuen** Bereichs auf **erteilen**.
9. Klicken Sie im Bereich **erteilen** auf **Zugriff blockieren**, und klicken Sie dann auf **auswählen**.
10. Klicken Sie im Bereich **neu** **auf** für **Richtlinie aktivieren**, und klicken Sie dann auf **Erstellen**.
11. Schließen Sie die Registerkarten **Azure-Portal** und **Microsoft 365 Admin Center** .

Um die erste Richtlinie zu testen, melden Sie sich ab, und melden Sie sich mit dem DedicatedAdmin-Konto an. Sie sollten aufgefordert werden, MFA zu konfigurieren. Dies zeigt, dass die erste Richtlinie angewendet wird.

Informationen und Links zum Schutz ihrer globalen Administratorkonten in der Produktion finden Sie unter [Protect Global Administrator Accounts](identity-create-protect-global-admins.md#identity-global-admin) Step in the Identity Phase.

## <a name="next-step"></a>Nächster Schritt

Sehen Sie sich weitere [Identitäts](m365-enterprise-test-lab-guides.md#identity)features und- funktionen in Ihrer Testumgebung an.

## <a name="see-also"></a>Siehe auch

[Phase 2: Identität](identity-infrastructure.md)

[Testumgebungsanleitungen für Microsoft 365 Enterprise](m365-enterprise-test-lab-guides.md)

[Microsoft 365 Enterprise-Bereitstellungshandbuch](deploy-microsoft-365-enterprise.md)

[Dokumentation zu Microsoft 365 Enterprise](https://docs.microsoft.com/microsoft-365-enterprise/)
