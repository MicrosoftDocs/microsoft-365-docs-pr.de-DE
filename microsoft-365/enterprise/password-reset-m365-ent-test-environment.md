---
title: Kennwortzurücksetzung für Ihre Microsoft 365-Testumgebung
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/13/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom:
- TLGS
- Ent_TLGs
ms.assetid: ''
description: 'Zusammenfassung: Konfigurieren und Testen der Kennwortzurücksetzung für Ihre Microsoft 365-Testumgebung.'
ms.openlocfilehash: efcaaf9ed1873c0908bb0e64644b8e10de280a01
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50921492"
---
# <a name="password-reset-for-your-microsoft-365-test-environment"></a>Kennwortzurücksetzung für Ihre Microsoft 365-Testumgebung

*Diese Testumgebungsanleitung kann nur für Microsoft 365 für Unternehmenstestumgebungen verwendet werden.*

Die Self-Service-Kennwortzurücksetzung (SSPR) des Azure Active Directory (Azure AD) erlaubt es Benutzern, ihre Kennwörter oder Konten zurücksetzen oder zu entsperren.

In diesem Artikel wird beschrieben, wie Sie Kennwortzurücksetzungen in Ihrer Microsoft 365 konfigurieren und testen.

Das Einrichten von SSPR umfasst drei Phasen:
- [Phase 1: Konfigurieren Sie Kennworthashsynchronisierung für Ihre Microsoft 365-Testumgebung](#phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment)
- [Phase 2: Aktivieren Sie das Kennwortrückschreiben](#phase-2-enable-password-writeback)
- [Phase 3: Konfigurieren und testen Sie die Kennwortzurücksetzung](#phase-3-configure-and-test-password-reset)
    
![Testumgebungsanleitungen für die Microsoft-Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> Eine visuelle Karte zu allen Artikeln im Stapel Microsoft 365 test lab guide für unternehmen finden Sie unter [Microsoft 365 for enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).

## <a name="phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment"></a>Phase 1: Konfigurieren Sie Kennworthashsynchronisierung für Ihre Microsoft 365-Testumgebung

Befolgen Sie zunächst die Anweisungen unter [Kennworthashsynchronisierung](password-hash-sync-m365-ent-test-environment.md). 

Die resultierende Konfiguration sieht wie die folgenden aus:
  
![Das simulierte Unternehmen mit Kennworthashsynchronisierung für die Testumgebung](../media/pass-through-auth-m365-ent-test-environment/Phase1.png)
  
Diese Konfiguration besteht aus: 
  
- Eine Testversion oder ein kostenpflichtiges Abonnement für Microsoft 365 E5.
- Ein vereinfachtes Unternehmensintranet, das mit dem Internet verbunden ist und aus den virtuellen Computern DC1, APP1 und CLIENT1 in einem Subnetz eines virtuellen Azure-Netzwerks besteht.
- Azure AD Connect wird auf APP1 ausgeführt, um die Active Directory Domain Services (AD DS)-Domäne TESTLAB mit dem Azure AD-Mandanten Ihrer Microsoft 365-Abonnements zu synchronisieren.

## <a name="phase-2-enable-password-writeback"></a>Phase 2: Aktivieren Sie das Kennwortrückschreiben

Folgen Sie den Anweisungen unter [Phase 2 der Kennwortrückschreibung der Testumgebungsanleitungen](password-writeback-m365-ent-test-environment.md#phase-2-enable-password-writeback-for-the-testlab-ad-ds-domain).

Sie müssen das Rückschreiben des Kennworts aktiviert haben, um das Kennwortzurücksetzen verwenden zu können.
  
## <a name="phase-3-configure-and-test-password-reset"></a>Phase 3: Konfigurieren und testen Sie die Kennwortzurücksetzung

Konfigurieren Sie in dieser Phase die Kennwortzurücksetzung im Azure AD-Mandanten über die Gruppenmitgliedschaft, und überprüfen Sie dann, ob sie funktioniert.

Aktivieren Sie zunächst die Kennwortzurücksetzung für die Konten in einer bestimmten Azure AD-Gruppe.

1. Öffnen Sie [https://portal.azure.com](https://portal.azure.com) in einer privaten Browserinstanz, und melden Sie sich dann mit den Anmeldeinformationen des globalen Administratorkontos an.
2. Wählen Sie im Azure-Portal **Azure Active Directory**  >  **Gruppen**  >  **Neue Gruppe aus.**
3. Legen Sie **Gruppentyp** auf **Sicherheit**, **Gruppenname** auf **PWReset** und **Mitgliedschaftstyp** auf **Zugewiesen** fest.
4. Wählen **Sie Mitglieder** aus, suchen und wählen Sie Benutzer **3** aus, wählen **Sie Auswählen** aus, und wählen Sie dann **Erstellen aus.**
5. Schließen Sie den Bereich **Gruppen**.
6. Wählen Sie Azure Active Directory linken Navigation  die Option Kennwortzurücksetzung aus.
7. Wählen Sie im Bereich **Kennwort zurücksetzen, Eigenschaften** unter **Self-Service-Kennwortzurücksetzung aktiviert** die Option **Ausgewählt** aus.
8. Wählen **Sie Gruppe auswählen** aus, wählen Sie die Gruppe **PWReset** aus, und wählen Sie **dann Speichern**  >  **aus.**
9. Schließen Sie die private Browserinstanz.

Testen Sie als Nächstes die Kennwortzurücksetzung für das Benutzer 3-Konto.

1. Öffnen Sie eine neue private Browserinstanz, und navigieren Sie zu [https://aka.ms/ssprsetup](https://aka.ms/ssprsetup).
1. Melden Sie sich mit den Anmeldeinformationen des Kontos von Benutzer 3 an.
1. Wählen **Sie unter Weitere Informationen erforderlich** die Option Weiter **aus.** 
1. Legen Sie unter **Verlieren Sie nicht den Zugriff auf Ihr Konto** Ihre Mobiltelefonnummer als Telefonnummer für die Authentifizierung und Ihr Geschäfts- oder persönliches E-Mail-Konto als E-Mail-Adresse für die Authentifizierung fest.
1. Nachdem beide überprüft wurden, wählen **Sie Gut aussehen** aus, und schließen Sie dann die private Instanz des Browsers.
1. Wechseln Sie in einer neuen privaten Browserinstanz zu [https://aka.ms/sspr](https://aka.ms/sspr) .
1. Geben Sie den Kontonamen Benutzer 3 ein, geben Sie die Zeichen aus dem CAPTCHA ein, und wählen Sie dann **Weiter aus.**
1. Wählen **Sie für überprüfungsschritt 1** die Option **E-Mail meine alternative** E-Mail senden aus, und wählen Sie dann **E-Mail aus.** Wenn Sie die E-Mail erhalten, geben Sie den Überprüfungscode ein, und wählen Sie dann **Weiter aus.**
1. Geben **Sie unter Zurück in Ihr Konto** ein neues Kennwort für das Konto "Benutzer 3" ein, und wählen Sie dann Fertig stellen **aus.** Notieren Sie sich das geänderte Kennwort des Kontos von Benutzer 3, und bewahren Sie es an einem sicheren Ort auf.
1. Gehen Sie in einer separaten Registerkarte derselben Browserinstanz zu [https://portal.office.com](https://portal.office.com), und melden Sie sich dann mit dem Kontonamen von Benutzer 3 und dem neuen Kennwort an. Die **Microsoft Office-Startseite** sollte angezeigt werden.

## <a name="next-step"></a>Nächster Schritt

Sehen Sie sich weitere [Identitäts](m365-enterprise-test-lab-guides.md#identity)features und- funktionen in Ihrer Testumgebung an.

## <a name="see-also"></a>Siehe auch

[Testumgebungsanleitungen für Microsoft 365 Enterprise](m365-enterprise-test-lab-guides.md)

[Übersicht über Microsoft 365 Enterprise](microsoft-365-overview.md)

[Dokumentation zu Microsoft 365 Enterprise](/microsoft-365-enterprise/)