---
title: Schützen globaler Administratorkonten in Ihrer Microsoft 365 for Enterprise-Testumgebung
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
description: Gehen Sie wie folgt vor, um globale Administratorkonten in Ihrer Microsoft 365 for Enterprise-Testumgebung zu schützen.
ms.openlocfilehash: 1ae04e4761ed86e087e647464ad522466ed6abef
ms.sourcegitcommit: 53ff1fe6d6143b0bf011031eea9b85dc01ae4f74
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48487636"
---
# <a name="protect-global-administrator-accounts-in-your-microsoft-365-for-enterprise-test-environment"></a>Schützen globaler Administratorkonten in Ihrer Microsoft 365 for Enterprise-Testumgebung

*Diese Test Umgebungs Anleitung kann nur für Microsoft 365 für Enterprise-Testumgebungen verwendet werden.*

Sie können digitale Angriffe in Ihrer Organisation verhindern, indem Sie sicherstellen, dass Ihre Administratorkonten so sicher wie möglich sind. 

In diesem Artikel wird beschrieben, wie Sie mithilfe von Azure Active Directory (Azure AD) bedingten Zugriffsrichtlinien globale Administratorkonten schützen.

Das schützen globaler Administratorkonten in Ihrer Microsoft 365 for Enterprise-Testumgebung umfasst zwei Phasen:
- [Phase 1: Erstellen der Testumgebung für Microsoft 365 für Unternehmen](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [Phase 2: Konfigurieren von Richtlinien für bedingten Zugriff](#phase-2-configure-conditional-access-policies)

![Testumgebungsanleitungen für die Microsoft-Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> Eine visuelle Zuordnung zu allen Artikeln im Microsoft 365 for Enterprise Test Lab Guide Stack finden Sie unter [Microsoft 365 for Enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).

## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a>Phase 1: Erstellen der Testumgebung für Microsoft 365 für Unternehmen

Wenn Sie den Schutz des globalen Administratorkontos auf einfache Weise mit den Mindestanforderungen testen möchten, befolgen Sie die Anweisungen unter [Lightweight Base Configuration](lightweight-base-configuration-microsoft-365-enterprise.md).
  
Wenn Sie den Schutz des globalen Administratorkontos in einem simulierten Unternehmen testen möchten, befolgen Sie die Anweisungen unter [Pass-Through-Authentifizierung](pass-through-auth-m365-ent-test-environment.md).
  
> [!NOTE]
> Zum Testen des Schutzes globaler Administratorkonten ist keine simulierte Enterprise-Testumgebung erforderlich, die ein simuliertes, mit dem Internet verbundenes Intranet und eine Verzeichnissynchronisierung für ein Active Directory-Domänendienste (AD DS) enthält. Sie wird hier als Option bereitgestellt, damit Sie den Schutz globaler Administratorkonten testen und mit dieser in einer Umgebung experimentieren können, die eine typische Organisation repräsentiert. 
  
## <a name="phase-2-configure-conditional-access-policies"></a>Phase 2: Konfigurieren von Richtlinien für bedingten Zugriff

Erstellen Sie zunächst ein neues Benutzerkonto als dedizierter globaler Administrator.

1. Öffnen Sie auf einer separaten Registerkarte das [Microsoft 365 Admin Center](https://admin.microsoft.com/).
2. Wählen Sie **Benutzer**  >  **aktive Benutzer**aus, und wählen Sie dann **Benutzer hinzufügen**aus.
3. Geben Sie im Bereich **Benutzer hinzufügen** in den Feldern **Vorname**, **Anzeigename**und Benutzer **Name** **DedicatedAdmin** ein.
4. Wählen Sie **Kennwort**aus, wählen Sie **das Kennwort erstellen**aus, und geben Sie dann ein sicheres Kennwort ein. Notieren Sie sich das Kennwort für dieses neue Konto an einem sicheren Ort.
5. Wählen Sie **Weiter** aus.
6. Wählen Sie im Bereich **Produktlizenzen zuweisen** die Option **Microsoft 365 E5**aus, und wählen Sie dann **weiter**aus.
7. Wählen Sie im Bereich **Optionale Einstellungen** die Option **roles**  >  **Admin Center Access**  >  **Global admin**  >  **Next**aus.
8. Wählen Sie im Bereich **fast done** die Option **Hinzufügen fertig stellen**aus, und wählen Sie dann **Schließen**aus.

Erstellen Sie als nächstes eine neue Gruppe mit dem Namen GlobalAdmins, und fügen Sie Ihr das DedicatedAdmin-Konto hinzu.

1. Wählen Sie auf der Registerkarte **Microsoft 365 Admin Center** im linken Navigationsbereich die Option **Gruppen** aus, und wählen Sie dann **Gruppen**aus.
2. Wählen Sie **Gruppe hinzufügen** aus.
3. Wählen Sie im Bereich **Gruppentyp auswählen** die Option **Sicherheit**aus, und wählen Sie dann **weiter**aus.
4. Wählen Sie im Bereich **Grundlagen einrichten die** Option **Gruppe erstellen**aus, und wählen Sie dann **Schließen**aus.
5. Geben Sie im Bereich **überprüfen und Abschließen der Gruppe hinzufügen** **GlobalAdmins**ein, und wählen Sie dann **weiter**aus.
7. Wählen Sie in der Liste der Gruppen die Gruppe **GlobalAdmins** aus.
8. Wählen Sie im Bereich **GlobalAdmins** die Option **Mitglieder**aus, und wählen Sie dann **Alle anzeigen und Mitglieder verwalten**aus.
9. Wählen Sie im Bereich **GlobalAdmins** die Option **Mitglieder hinzufügen**aus, wählen Sie das **DedicatedAdmin** -Konto und ihr globales Administratorkonto aus, und wählen Sie dann **Save**  >  **Close**  >  **Close**speichern aus.

Erstellen Sie als nächstes Richtlinien für bedingten Zugriff, um mehrstufige Authentifizierung für globale Administratorkonten zu erfordern, und um die Authentifizierung zu verweigern, wenn das Anmelde Risiko Mittel oder hoch ist.

Für diese erste Richtlinie müssen alle globalen Administratorkonten MFA verwenden.

1. Wechseln Sie auf einer neuen Registerkarte Ihres Browsers zu [https://portal.azure.com](https://portal.azure.com) .
2. Klicken Sie auf **Azure Active Directory**  >  **Sicherheits**  >  **bedingten Zugriff**.
3. Wählen Sie im Bereich **bedingte Zugriffs-Richtlinien** die Option **Basisrichtlinie: MFA für Administratoren erfordern (Vorschau)** aus.
4. Wählen Sie im Bereich **Basisrichtlinie** die Option **Richtlinie sofort > speichern verwenden**aus.

Diese zweite Richtlinie blockiert den Zugriff auf die Authentifizierung des globalen Administratorkontos, wenn das Anmelde Risiko Mittel oder hoch ist.

1. Wählen Sie im Bereich **bedingte Zugriffs-Richtlinien** die Option **neue Richtlinie**aus.
2. Geben Sie im **neuen** Bereich **globale Administratoren** in **Name**ein.
3. Wählen Sie im Abschnitt **Zuweisungen** die Option **Benutzer und Gruppen**aus.
4. Wählen Sie im Bereich **Benutzer und Gruppen** auf der Registerkarte **einschließen** die Option Benutzer und **Gruppen**  >  **Benutzer**  >  **und Gruppen**auswählen aus.
5. Wählen Sie im Bereich **auswählen** die Gruppe **GlobalAdmins** aus, **und wählen Sie**dann  >  **Fertig**aus.
6. Wählen Sie im Abschnitt **Zuweisungen** die Option **Bedingungen**aus.
7. Wählen Sie im Bereich **Bedingungen** die **Option Anmelde Risiko**aus, wählen **Sie ja** für **configure**aus, wählen Sie **hoch** und **Mittel**aus, und wählen Sie dann **auswählen** und **Fertig**aus.
8. Wählen Sie im Bereich **Zugriffssteuerung** des **neuen** Bereichs die Option **Grant**aus.
9. Wählen Sie im Bereich **erteilen** die Option **Zugriff blockieren**aus, und wählen Sie dann **auswählen**aus.
10. Wählen Sie im Bereich **neu** die **Option** für **Richtlinie aktivieren**aus, und wählen Sie dann **Erstellen**aus.
11. Schließen Sie die Registerkarten **Azure-Portal** und **Microsoft 365 Admin Center** .

Um die erste Richtlinie zu testen, melden Sie sich ab, und melden Sie sich mit dem DedicatedAdmin-Konto an. Sie sollten aufgefordert werden, MFA zu konfigurieren. Dies zeigt, dass die erste Richtlinie angewendet wird.

## <a name="next-step"></a>Nächster Schritt

Sehen Sie sich weitere [Identitäts](m365-enterprise-test-lab-guides.md#identity)features und- funktionen in Ihrer Testumgebung an.

## <a name="see-also"></a>Siehe auch

[Identity-Roadmap](identity-roadmap-microsoft-365.md)

[Testumgebungsanleitungen für Microsoft 365 Enterprise](m365-enterprise-test-lab-guides.md)

[Übersicht über Microsoft 365 Enterprise](microsoft-365-overview.md)

[Dokumentation zu Microsoft 365 für Unternehmen](https://docs.microsoft.com/microsoft-365-enterprise/)
