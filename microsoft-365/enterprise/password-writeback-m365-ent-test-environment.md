---
title: Rückschreiben des Kennworts für Ihre Microsoft 365-Testumgebung
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/22/2019
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
description: 'Zusammenfassung: Konfigurieren des Rückschreibens des Kennworts für Ihre Microsoft 365-Testumgebung.'
ms.openlocfilehash: f1118c22ad1f65ea29bb14afacb7506a60d1fe1a
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50921480"
---
# <a name="password-writeback-for-your-microsoft-365-test-environment"></a>Rückschreiben des Kennworts für Ihre Microsoft 365-Testumgebung

*Diese Testumgebungsanleitung kann nur für Microsoft 365 für Unternehmenstestumgebungen verwendet werden.*

Benutzer können das Kennwortrückschreiben verwenden, um ihre Kennwörter über Azure Active Directory (Azure AD) zu aktualisieren, das dann in Ihre lokalen Active Directory Domain Services (AD DS) repliziert wird. Beim Kennwortrückschreiben müssen Benutzer ihre Kennwörter nicht über den lokalen AD DS aktualisieren, in dem ihre ursprünglichen Benutzerkonten gespeichert sind. Dies hilft Roaming- oder Remotebenutzern, die über keine Remotezugriffsverbindung zu ihrem lokalen Netzwerk verfügen.

In diesem Artikel wird beschrieben, wie Sie Ihre Microsoft 365-Testumgebung für das Kennwortrückschreiben konfigurieren.

Das Konfigurieren der Testumgebung für das Kennwortrückschreiben umfasst zwei Phasen:
- [Phase 1: Konfigurieren Sie Kennworthashsynchronisierung für Ihre Microsoft 365-Testumgebung](#phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment)
- [Phase 2: Aktivieren des Kennwortrückschreibens für die AD DS-Domäne "TESTLAB"](#phase-2-enable-password-writeback-for-the-testlab-ad-ds-domain)
  
![Testumgebungsanleitungen für die Microsoft-Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> Eine visuelle Karte zu allen Artikeln im Microsoft 365 for Enterprise Test Lab Guide-Stapel finden Sie unter [Microsoft 365 for Enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).

## <a name="phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment"></a>Phase 1: Konfigurieren Sie Kennworthashsynchronisierung für Ihre Microsoft 365-Testumgebung

Befolgen Sie zunächst die Anweisungen unter [Kennworthashsynchronisierung](password-hash-sync-m365-ent-test-environment.md). Die resultierende Konfiguration sieht wie die folgenden aus:
  
![Das simulierte Unternehmen mit Kennworthashsynchronisierung für die Testumgebung](../media/pass-through-auth-m365-ent-test-environment/Phase1.png)
  
Diese Konfiguration besteht aus: 
  
- Eine Testversion oder ein kostenpflichtiges Abonnement für Microsoft 365 E5.
- Ein vereinfachtes Unternehmensintranet, das mit dem Internet verbunden ist und aus den virtuellen Computern DC1, APP1 und CLIENT1 in einem Subnetz eines virtuellen Azure-Netzwerks besteht.
- Azure AD Connect wird auf APP1 ausgeführt, um die AD DS-Domäne „TESTLAB“ mit dem Azure AD-Mandanten Ihrer Microsoft 365-Abonnements zu synchronisieren.

## <a name="phase-2-enable-password-writeback-for-the-testlab-ad-ds-domain"></a>Phase 2: Aktivieren des Kennwortrückschreibens für die AD DS-Domäne "TESTLAB"

Konfigurieren Sie zuerst das Konto „User1“ mit der globalen Administratorrolle.

1. Melden Sie sich aus dem [Microsoft 365 Admin Center](https://portal.microsoft.com) mit Ihrem globalen Administratorkonto an.

2. Wählen **Sie Aktive Benutzer aus.**
 
3. Wählen Sie **auf der** Seite Aktive Benutzer das **Konto "User1"** aus.

4. Wählen Sie **im Bereich Benutzer1** **neben** Rollen bearbeiten **aus.**

5. Wählen Sie **im Bereich Benutzerrollen** bearbeiten für Benutzer1 die Option **Globaler Administrator** aus, wählen Sie **Speichern** und dann **Schließen aus.**

Als Nächstes konfigurieren Sie das Konto "User1" mit den Sicherheitseinstellungen, mit denen es Kennwörter im Auftrag von anderen Benutzern in der AD DS-Domäne "TESTLAB" ändern kann.

1. Melden Sie sich über das [Azure-Portal](https://portal.azure.com) mit Ihrem globalen Administratorkonto an, und stellen Sie dann mit dem Konto „TESTLAB\User1“ eine Verbindung zu APP1 her.

2. Wählen Sie auf dem Desktop von APP1 **Start**, geben Sie **aktiv** ein, und wählen Sie dann **Active Directory-Benutzer und -Computer aus.**

3. Wählen Sie auf der Menüleiste Ansicht **aus.** Wenn **Erweiterte Features** nicht aktiviert sind, wählen Sie sie aus, um sie zu aktivieren.

4. Wählen Sie im Strukturbereich Ihre Domäne aus, und halten Sie sie (oder klicken Sie mit der rechten Maustaste), wählen Sie **Eigenschaften** aus, und wählen Sie dann **die** Registerkarte Sicherheit aus.

5. Wählen Sie **Erweitert** aus.

6. Wählen Sie **auf der** Registerkarte Berechtigungen die Option **Hinzufügen aus.**

7. Wählen **Sie Prinzipal auswählen** aus, geben Sie **Benutzer1 ein,** und wählen Sie dann **OK aus.**

8. Wählen Sie unter **Gilt für** die Option **Untergeordnete Benutzerobjekte** aus.

9. Wählen Sie unter **Berechtigungen** Folgendes aus:

    - **Kennwort ändern**
    - **Kennwort zurücksetzen**

10. Wählen Sie unter **Eigenschaften** Folgendes aus:
    - **Write lockoutTime**
    - **Write pwdLastSet**

11. Wählen **Sie dreimal OK** aus, um die Änderungen zu speichern.

12. Schließen Sie **Active Directory-Benutzer und -Computer**.

Konfigurieren Sie als Nächstes Azure AD Connect auf APP1 für das Rückschreiben des Kennworts.

1. Verbinden Sie APP1 bei Bedarf mit dem Konto „TESTLAB\User1“.

2. Doppelklicken Sie auf dem Desktop von APP1 auf **Azure AD Connect**.

3. Wählen Sie **auf der Seite Willkommen** die Option Konfigurieren **aus.**

4. Wählen Sie **auf der** Seite Zusätzliche Aufgaben die Option **Synchronisierungsoptionen anpassen** aus, und wählen Sie dann Weiter **aus.**

5. Geben Sie **auf der Seite Verbindung mit Azure AD** herstellen Ihre Anmeldeinformationen für ihr globales Administratorkonto ein, und wählen Sie dann Weiter **aus.**

6. Wählen Sie auf den Seiten Connect **directories** und **Domain/OU filtering** die Option **Weiter aus.**

7. Wählen Sie **auf der** Seite Optionale Features die Option **Kennwortrückschreiben** aus, und wählen Sie dann **Weiter aus.**

8. Wählen Sie **auf der Seite** Bereit zum Konfigurieren die Option **Konfigurieren** aus, und warten Sie, bis der Prozess abgeschlossen ist.

9. Wenn die Konfiguration abgeschlossen ist, wählen Sie **Beenden aus.**

Sie können nun das Kennwortrückschreiben für Benutzer auf Computern testen, die nicht mit dem virtuellen Netzwerk Ihres simulierten Intranets verbunden sind.

Die resultierende Konfiguration sieht wie die folgenden aus:

![Das simulierte Unternehmen mit einer Testumgebung mit Pass-Trought-Authentifizierung](../media/pass-through-auth-m365-ent-test-environment/Phase1.png)

Diese Konfiguration besteht aus: 

- Eine Microsoft 365 E5-Testversion oder kostenpflichtige Abonnements mit der DNS-Domäne TESTLAB.\<*your domain name*> registriert.
- Ein vereinfachtes Unternehmensintranet, das mit dem Internet verbunden ist und aus den virtuellen Computern DC1, APP1 und CLIENT1 in einem Subnetz eines virtuellen Azure-Netzwerks besteht.
- Azure AD Connect wird auf APP1 ausgeführt, um die Liste von Konten und Gruppen des Azure AD-Mandanten Ihrer Microsoft 365-Abonnements mit der AD DS-Domäne „TESTLAB“ zu synchronisieren.
- Kennwortrückschreiben ist aktiviert, damit Benutzer ihre Kennwörter über Azure Active Directory ändern können, ohne mit dem vereinfachten Intranet verbunden sein zu müssen.

## <a name="next-step"></a>Nächster Schritt

Sehen Sie sich weitere [Identitäts](m365-enterprise-test-lab-guides.md#identity)features und- funktionen in Ihrer Testumgebung an.

## <a name="see-also"></a>Siehe auch

[Testumgebungsanleitungen für Microsoft 365 Enterprise](m365-enterprise-test-lab-guides.md)

[Übersicht über Microsoft 365 Enterprise](microsoft-365-overview.md)

[Dokumentation zu Microsoft 365 Enterprise](/microsoft-365-enterprise/)