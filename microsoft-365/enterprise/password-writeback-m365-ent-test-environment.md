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
ms.openlocfilehash: b999d50b0e98b11638199327bd7ffe7269b261ce
ms.sourcegitcommit: 53ff1fe6d6143b0bf011031eea9b85dc01ae4f74
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48487128"
---
# <a name="password-writeback-for-your-microsoft-365-test-environment"></a>Rückschreiben des Kennworts für Ihre Microsoft 365-Testumgebung

*Diese Test Umgebungs Anleitung kann nur für Microsoft 365 für Enterprise-Testumgebungen verwendet werden.*

Benutzer können Kenn Wort Rückschreiben verwenden, um Ihre Kennwörter über Azure Active Directory (Azure AD) zu aktualisieren, die dann auf Ihre lokalen Active Directory-Domänendienste (AD DS) repliziert wird. Bei Kenn Wort Rückschreiben müssen Benutzer ihre Kennwörter nicht über das lokale AD DS aktualisieren, in dem die ursprünglichen Benutzerkonten gespeichert sind. Dies hilft Roaming-oder Remotebenutzern, die keine RAS-Verbindung mit Ihrem lokalen Netzwerk haben.

In diesem Artikel wird beschrieben, wie Sie Ihre Microsoft 365-Testumgebung für das Kenn Wort Rückschreiben konfigurieren.

Das Konfigurieren der Testumgebung für das Kenn Wort Rückschreiben umfasst zwei Phasen:
- [Phase 1: Konfigurieren Sie Kennworthashsynchronisierung für Ihre Microsoft 365-Testumgebung](#phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment)
- [Phase 2: Aktivieren des Kennwortrückschreibens für die AD DS-Domäne "TESTLAB"](#phase-2-enable-password-writeback-for-the-testlab-ad-ds-domain)
  
![Testumgebungsanleitungen für die Microsoft-Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> Eine visuelle Zuordnung zu allen Artikeln im Microsoft 365 for Enterprise Test Lab Guide Stack finden Sie unter [Microsoft 365 for Enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).

## <a name="phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment"></a>Phase 1: Konfigurieren Sie Kennworthashsynchronisierung für Ihre Microsoft 365-Testumgebung

Befolgen Sie zuerst die Anweisungen unter [Kennworthash Synchronisierung](password-hash-sync-m365-ent-test-environment.md). Die resultierende Konfiguration sieht wie folgt aus:
  
![Das simulierte Unternehmen mit Kennworthashsynchronisierung für die Testumgebung](../media/pass-through-auth-m365-ent-test-environment/Phase1.png)
  
Diese Konfiguration besteht aus: 
  
- Eine Testversion oder ein kostenpflichtiges Abonnement für Microsoft 365 E5.
- Ein vereinfachtes Organisationsintranet, das mit dem Internet verbunden ist, das aus den virtuellen Computern DC1, App1 und CLIENT1 in einem Subnetz eines virtuellen Azure-Netzwerks besteht.
- Azure AD Connect wird auf APP1 ausgeführt, um die AD DS-Domäne „TESTLAB“ mit dem Azure AD-Mandanten Ihrer Microsoft 365-Abonnements zu synchronisieren.

## <a name="phase-2-enable-password-writeback-for-the-testlab-ad-ds-domain"></a>Phase 2: Aktivieren des Kennwortrückschreibens für die AD DS-Domäne "TESTLAB"

Konfigurieren Sie zuerst das Konto „User1“ mit der globalen Administratorrolle.

1. Melden Sie sich aus dem [Microsoft 365 Admin Center](https://portal.microsoft.com) mit Ihrem globalen Administratorkonto an.

2. Wählen Sie **aktive Benutzer**aus.
 
3. Wählen Sie auf der Seite **aktive Benutzer** das Konto **User1** aus,

4. Wählen Sie im Bereich **User1** neben **Rollen**die Option **Bearbeiten** aus.

5. Wählen Sie im Bereich **Benutzerrollen bearbeiten** für User1 die Option **globaler Administrator**aus, wählen Sie **Speichern**aus, und klicken Sie dann auf **Schließen**.

Als Nächstes konfigurieren Sie das Konto "User1" mit den Sicherheitseinstellungen, mit denen es Kennwörter im Auftrag von anderen Benutzern in der AD DS-Domäne "TESTLAB" ändern kann.

1. Melden Sie sich über das [Azure-Portal](https://portal.azure.com) mit Ihrem globalen Administratorkonto an, und stellen Sie dann mit dem Konto „TESTLAB\User1“ eine Verbindung zu APP1 her.

2. Wählen Sie auf dem Desktop von App1 **Start**aus, geben Sie **aktiv**ein, und wählen Sie dann **Active Directory Benutzer und Computer**aus.

3. Wählen Sie in der Menüleiste **Ansicht**aus. Wenn **Erweiterte Funktionen** nicht aktiviert ist, wählen Sie Sie aus, um Sie zu aktivieren.

4. Wählen Sie im Strukturbereich Ihre Domäne aus, halten Sie sie gedrückt (oder klicken Sie mit der rechten Maustaste darauf), wählen Sie **Eigenschaften**aus, und klicken Sie dann auf die Registerkarte **Sicherheit** .

5. Wählen Sie **Erweitert** aus.

6. Wählen Sie auf der Registerkarte **Berechtigungen** die Option **Hinzufügen**aus.

7. Wählen Sie **Wählen Sie einen Prinzipal aus**, geben Sie **User1**ein, und klicken Sie dann auf **OK**.

8. Wählen Sie unter **Gilt für** die Option **Untergeordnete Benutzerobjekte** aus.

9. Wählen Sie unter **Berechtigungen** Folgendes aus:

    - **Kennwort ändern**
    - **Kennwort zurücksetzen**

10. Wählen Sie unter **Eigenschaften** Folgendes aus:
    - **Write lockoutTime**
    - **Write pwdLastSet**

11. Wählen Sie drei Mal **OK** aus, um die Änderungen zu speichern.

12. Schließen Sie **Active Directory-Benutzer und -Computer**.

Konfigurieren Sie als Nächstes Azure AD Connect auf APP1 für das Rückschreiben des Kennworts.

1. Verbinden Sie APP1 bei Bedarf mit dem Konto „TESTLAB\User1“.

2. Doppelklicken Sie auf dem Desktop von APP1 auf **Azure AD Connect**.

3. Wählen Sie auf der **Willkommensseite** **configure**aus.

4. Wählen Sie auf der Seite **Weitere Aufgaben** die Option **Synchronisierungsoptionen anpassen**aus, und wählen Sie dann **weiter**aus.

5. Geben Sie auf der Seite mit **Azure AD verbinden** die Anmeldeinformationen des globalen Administratorkontos ein, und wählen Sie dann **weiter**aus.

6. Wählen Sie auf der Seite Verzeichnisse und **Domänen/ou-Filterung** **verbinden** die Option **weiter**aus.

7. Wählen Sie auf der Seite **optionale Features** die Option **Kenn Wort**Rückschreiben aus, und wählen Sie dann **weiter**aus.

8. Wählen Sie auf der Seite **bereit zur Konfiguration** **konfigurieren aus,** und warten Sie, bis der Vorgang abgeschlossen ist.

9. Wenn das Ende der Konfiguration angezeigt wird, wählen Sie **Beenden**aus.

Sie können jetzt das Kenn Wort Rückschreiben für Benutzer auf Computern testen, die nicht mit dem virtuellen Netzwerk Ihres simulierten Intranets verbunden sind.

Die resultierende Konfiguration sieht wie folgt aus:

![Das simulierte Unternehmen mit einer Testumgebung mit Pass-Trought-Authentifizierung](../media/pass-through-auth-m365-ent-test-environment/Phase1.png)

Diese Konfiguration besteht aus: 

- Eine Microsoft 365 E5-Testversion oder kostenpflichtige Abonnements mit der DNS-Domäne TESTLAB.\<*your domain name*> registriert.
- Ein vereinfachtes Organisationsintranet, das mit dem Internet verbunden ist, das aus den virtuellen Computern DC1, App1 und CLIENT1 in einem Subnetz eines virtuellen Azure-Netzwerks besteht.
- Azure AD Connect wird auf APP1 ausgeführt, um die Liste von Konten und Gruppen des Azure AD-Mandanten Ihrer Microsoft 365-Abonnements mit der AD DS-Domäne „TESTLAB“ zu synchronisieren.
- Kennwortrückschreiben ist aktiviert, damit Benutzer ihre Kennwörter über Azure Active Directory ändern können, ohne mit dem vereinfachten Intranet verbunden sein zu müssen.

## <a name="next-step"></a>Nächster Schritt

Sehen Sie sich weitere [Identitäts](m365-enterprise-test-lab-guides.md#identity)features und- funktionen in Ihrer Testumgebung an.

## <a name="see-also"></a>Siehe auch

[Testumgebungsanleitungen für Microsoft 365 Enterprise](m365-enterprise-test-lab-guides.md)

[Übersicht über Microsoft 365 Enterprise](microsoft-365-overview.md)

[Dokumentation zu Microsoft 365 für Unternehmen](https://docs.microsoft.com/microsoft-365-enterprise/)


