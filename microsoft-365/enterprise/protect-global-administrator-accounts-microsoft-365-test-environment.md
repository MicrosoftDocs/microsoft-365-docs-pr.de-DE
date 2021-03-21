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
description: Verwenden Sie diese Schritte, um globale Administratorkonten in Ihrer Microsoft 365 for Enterprise-Testumgebung zu schützen.
ms.openlocfilehash: 3eab538b59e460857e2fa195aaacf51051f94d6b
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50918882"
---
# <a name="protect-global-administrator-accounts-in-your-microsoft-365-for-enterprise-test-environment"></a>Schützen globaler Administratorkonten in Ihrer Microsoft 365 for Enterprise-Testumgebung

*Diese Testumgebungsanleitung kann nur für Microsoft 365 für Unternehmenstestumgebungen verwendet werden.*

Sie können digitale Angriffe auf Ihre Organisation verhindern, indem Sie sicherstellen, dass Ihre Administratorkonten so sicher wie möglich sind. 

In diesem Artikel wird beschrieben, wie Sie Richtlinien für bedingten Zugriff in Azure Active Directory (Azure AD) verwenden, um globale Administratorkonten zu schützen.

Der Schutz globaler Administratorkonten in Ihrer Microsoft 365 for Enterprise-Testumgebung umfasst zwei Phasen:
- [Phase 1: Erstellen Ihrer Microsoft 365 for Enterprise-Testumgebung](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [Phase 2: Konfigurieren von Richtlinien für bedingten Zugriff](#phase-2-configure-conditional-access-policies)

![Testumgebungsanleitungen für die Microsoft-Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> Eine visuelle Karte zu allen Artikeln im Microsoft 365 for Enterprise Test Lab Guide-Stapel finden Sie unter [Microsoft 365 for Enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).

## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a>Phase 1: Erstellen Ihrer Microsoft 365 for Enterprise-Testumgebung

Wenn Sie den globalen Administratorkontoschutz auf einfache Weise mit den Mindestanforderungen testen möchten, befolgen Sie die Anweisungen unter [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).
  
Wenn Sie den globalen Administratorkontoschutz in einem simulierten Unternehmen testen möchten, befolgen Sie die Anweisungen unter [Pass-Through-Authentifizierung](pass-through-auth-m365-ent-test-environment.md).
  
> [!NOTE]
> Für das Testen des globalen Administratorkontoschutzes ist keine simulierte Unternehmenstestumgebung erforderlich, die ein simuliertes Intranet, das mit dem Internet verbunden ist, und die Verzeichnissynchronisierung für active Directory Domain Services (AD DS) umfasst. Es wird hier als Option bereitgestellt, damit Sie den Schutz globaler Administratorkonten testen und damit in einer Umgebung experimentieren können, die eine typische Organisation darstellt. 
  
## <a name="phase-2-configure-conditional-access-policies"></a>Phase 2: Konfigurieren von Richtlinien für bedingten Zugriff

Erstellen Sie zunächst ein neues Benutzerkonto als dedizierter globaler Administrator.

1. Öffnen Sie auf einer separaten Registerkarte das [Microsoft 365 Admin Center](https://admin.microsoft.com/).
2. Wählen **Sie Benutzer** Aktive  >  **Benutzer** aus, und wählen Sie dann Benutzer hinzufügen **aus.**
3. Geben Sie **im Bereich** Benutzer hinzufügen **dedicatedAdmin** in die Felder **Vorname,** **Anzeigename** und **Benutzername** ein.
4. Wählen **Sie Kennwort** aus, wählen Sie Lassen Sie mich das Kennwort **erstellen,** und geben Sie dann ein starkes Kennwort ein. Noten Sie das Kennwort für dieses neue Konto an einem sicheren Ort auf.
5. Wählen Sie **Weiter** aus.
6. Wählen Sie **im Bereich Produktlizenzen** zuweisen die Option **Microsoft 365 E5** aus, und wählen Sie dann **Weiter aus.**
7. Wählen Sie **im Bereich Optionale Einstellungen** die Option **Rollen** Admin  >  **Center access** Global  >  **admin**  >  **Next aus.**
8. Wählen Sie **im Bereich You're almost done** die Option Hinzufügen fertig stellen aus, und wählen Sie dann Schließen  **aus.**

Erstellen Sie als Nächstes eine neue Gruppe namens GlobalAdmins, und fügen Sie ihr das DedicatedAdmin-Konto hinzu.

1. Wählen Sie auf der **Registerkarte Microsoft 365 Admin Center** im linken Navigationsbereich Gruppen aus, und wählen Sie dann Gruppen **aus.** 
2. Wählen Sie **Gruppe hinzufügen** aus.
3. Wählen Sie **im Bereich Gruppentyp auswählen** die Option **Sicherheit** aus, und wählen Sie dann **Weiter aus.**
4. Wählen Sie **im Bereich** Einrichten der Grundlagen die Option Gruppe erstellen aus, und wählen Sie dann Schließen **aus.** 
5. Geben Sie im Bereich Überprüfen und Fertig stellen **des Hinzufügens** von Gruppen **die Option GlobalAdmins** ein, und wählen Sie dann **Weiter aus.**
7. Wählen Sie in der Liste der Gruppen die **Gruppe GlobalAdmins** aus.
8. Wählen Sie **im Bereich GlobalAdmins** **Mitglieder** aus, und wählen Sie dann Alle anzeigen und Mitglieder **verwalten aus.**
9. Wählen Sie **im Bereich GlobalAdmins** Mitglieder hinzufügen **aus,** wählen Sie das **Konto DedicatedAdmin** und Ihr globales Administratorkonto aus, und wählen Sie dann **Schließen** schließen  >    >  **speichern aus.**

Erstellen Sie als Nächstes Richtlinien für bedingten Zugriff, um die mehrstufige Authentifizierung für globale Administratorkonten zu erfordern und die Authentifizierung zu verweigern, wenn das Anmelderisiko mittel oder hoch ist.

Diese erste Richtlinie erfordert, dass alle globalen Administratorkonten MFA verwenden.

1. Wechseln Sie auf einer neuen Registerkarte Ihres Browsers zu [https://portal.azure.com](https://portal.azure.com) .
2. Klicken **Sie auf Bedingter Azure Active**  >  **Directory-Sicherheitszugriff.**  >  
3. Wählen Sie **im Bereich Bedingter** Zugriff – Richtlinien die **Option Baseline policy: Require MFA for admins (preview)** aus.
4. Wählen Sie **im Bereich Baseline policy** die Option Richtlinie sofort > Speichern **aus.**

Diese zweite Richtlinie blockiert den Zugriff auf die globale Administratorkontoauthentifizierung, wenn das Anmelderisiko mittel oder hoch ist.

1. Wählen Sie **im Bereich Bedingter Zugriff – Richtlinien** die Option Neue Richtlinie **aus.**
2. Geben Sie **im Bereich Neu** den Namen globale **Administratoren** **ein.**
3. Wählen Sie **im Abschnitt Zuweisungen** die Option **Benutzer und Gruppen aus.**
4. Wählen Sie **auf der** Registerkarte Include im Bereich **Benutzer und** Gruppen die Option Benutzer und **Gruppen** Auswählen Benutzer  >  **und Gruppen** Auswählen  >  **aus.**
5. Wählen Sie **im Bereich** Auswählen die **Gruppe GlobalAdmins** aus, und wählen Sie **dann Fertig**  >  **auswählen aus.**
6. Wählen Sie **im Abschnitt Zuordnungen** die Option **Bedingungen aus.**
7. Wählen Sie **im** Bereich Bedingungen die Option **Anmelderisiko** aus, wählen Sie **Ja** für **Konfigurieren** aus, wählen Sie **Hoch** und **Mittel** aus, und wählen Sie **dann Auswählen** und **Fertig aus.**
8. Wählen Sie **im Abschnitt Zugriffssteuerelemente** im **Bereich Neu** die Option **Gewähren aus.**
9. Wählen Sie **im Bereich** Gewähren die Option **Zugriff blockieren** aus, und wählen Sie dann **Auswählen aus.**
10. Wählen Sie **im Bereich Neu** die Option **Ein** für Richtlinie **aktivieren** aus, und wählen Sie dann **Erstellen aus.**
11. Schließen Sie **die Registerkarten Azure-Portal** und **Microsoft 365 Admin Center.**

Um die erste Richtlinie zu testen, melden Sie sich ab und melden Sie sich mit dem DedicatedAdmin-Konto an. Sie sollten aufgefordert werden, MFA zu konfigurieren. Dies zeigt, dass die erste Richtlinie angewendet wird.

## <a name="next-step"></a>Nächster Schritt

Sehen Sie sich weitere [Identitäts](m365-enterprise-test-lab-guides.md#identity)features und- funktionen in Ihrer Testumgebung an.

## <a name="see-also"></a>Siehe auch

[Identitätsplan](identity-roadmap-microsoft-365.md)

[Testumgebungsanleitungen für Microsoft 365 Enterprise](m365-enterprise-test-lab-guides.md)

[Übersicht über Microsoft 365 Enterprise](microsoft-365-overview.md)

[Dokumentation zu Microsoft 365 Enterprise](/microsoft-365-enterprise/)