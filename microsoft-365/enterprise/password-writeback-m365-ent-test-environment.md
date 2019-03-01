---
title: Rückschreiben des Kennworts für Ihre Microsoft 365-Testumgebung
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/20/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom:
- TLGS
- Ent_TLGs
ms.assetid: ''
description: 'Zusammenfassung: Konfigurieren des Rückschreibens des Kennworts für Ihre Microsoft 365-Testumgebung.'
ms.openlocfilehash: 51ac9caf1cbc2edd979d9529301388a30981ee44
ms.sourcegitcommit: e749e2db2a15bb52b1a2857dbccdf55c31cff3d7
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/28/2019
ms.locfileid: "30340105"
---
# <a name="password-writeback-for-your-microsoft-365-test-environment"></a>Rückschreiben des Kennworts für Ihre Microsoft 365-Testumgebung

Mit dem Rückschreiben des Kennworts können Benutzer ihre Kennwörter über Azure Active Directory (Azure AD) aktualisieren, das dann in Ihre lokalen Active Directory Domain Services (AD DS) repliziert wird. Dank dem Kennwortrückschreiben müssen Benutzer ihre Kennwörter nicht über das lokale Windows Server AD aktualisieren, wo ihre ursprünglichen Benutzerkonten gespeichert sind. Dies ist für Roaming- oder Remote-Benutzer nützlich, die keine Remote-Zugriffsverbindung zum lokalen Netzwerk haben.

Dieser Artikel beschreibt, wie Sie Ihre Microsoft 365-Testumgebung für das Kennwortrückschreiben konfigurieren.

Die Einrichtung besteht aus zwei Phasen:

1.  Erstellen Sie die simulierte Microsoft 365-Testunternehmensumgebung mit Kennworthashsynchronisierung.
2.  Aktivieren Sie das Kennwortrückschreiben für die Windows Server AD-Domäne „TESTLAB“.
    
![Testumgebungsanleitungen für die Microsoft-Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> Klicken Sie [hier](https://aka.ms/m365etlgstack), um eine visuelle Darstellung aller Artikel im Stapel der Testumgebungsanleitungen in Microsoft 365 Enterprise zu erhalten.
  
## <a name="phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment"></a>Phase 1: Konfigurieren Sie Kennworthashsynchronisierung für Ihre Microsoft 365-Testumgebung

Befolgen Sie die Anweisungen unter [Kennworthashsynchronisierung für Microsoft 365](password-hash-sync-m365-ent-test-environment.md). Hier ist die resultierende Konfiguration.
  
![Das simulierte Unternehmen mit Kennworthashsynchronisierung für die Testumgebung](media/pass-through-auth-m365-ent-test-environment/Phase1.png)
  
Diese Konfiguration besteht aus:  
  
- Testversionen oder dauerhaften Abonnements von Office 365 E5 und EMS E5.
- Einem vereinfachtem Unternehmensintranet mit Internetzugriff, das aus virtuellen DC1-, APP1- und CLIENT1-Computern in einem Subnetz eines virtuellen Azure-Netzwerks besteht. 
- Azure AD Connect wird auf APP1 ausgeführt, um die Active Directory-Domäne TESTLAB von Windows Server mit dem Azure AD-Mandanten Ihrer Office 365- und EMS E5-Abonnements zu synchronisieren.

## <a name="phase-2-enable-password-writeback-for-the-testlab-windows-server-ad-domain"></a>Phase 2: Aktivieren Sie das Kennwortrückschreiben für die Windows Server AD-Domäne „TESTLAB“.

Konfigurieren Sie zuerst das Konto „User1“ mit der globalen Administratorrolle.

1. Melden Sie sich aus dem [Office-Portal](https://office.com) mit Ihrem globalen Administratorkonto an.

2. Klicken Sie auf die Kachel **Admin** Kachel. Klicken Sie auf der neuen Registerkarte **Microsoft 365 Admin Center** des Browsers auf **Aktive Benutzer**.
 
3. Klicken Sie auf der Seite **Aktive Benutzer** auf das Konto **Benutzer 1**.

4. Klicken Sie im Bereich **User1** auf **Bearbeiten** neben **Rollen**.

5. Klicken Sie im Bereich **Benutzerrollen bearbeiten** für User1 auf **Globaler Administrator**. Klicken Sie auf **Speichern** und dann auf **Schließen**.

Als Nächstes konfigurieren Sie das Konto „User1“ mit den Sicherheitseinstellungen, mit denen es Kennwörter im Auftrag von anderen Benutzern in der Windows Satz AD-Domäne „TESTLAB“ ändern kann.

1. Melden Sie sich über das [Azure-Portal](https://portal.azure.com) mit Ihrem globalen Administratorkonto an, und stellen Sie dann mit dem Konto „TESTLAB\User1“ eine Verbindung zu APP1 her.

2.  Klicken Sie auf dem Desktop von APP1 auf **Start**, geben Sie **active** ein, und klicken Sie dann auf **Active Directory-Benutzer und -Computer**.

3. Klicken Sie in der Menüleiste auf **Ansicht**. Wenn **Erweiterte Funktionen** nicht aktiviert ist, klicken Sie darauf, um diese Option zu aktivieren.

4. Klicken Sie im Strukturbereich mit der rechten Maustaste auf Ihre Domäne, klicken Sie auf **Eigenschaften**, und klicken Sie dann auf die Registerkarte **Sicherheit**.

5. Klicken Sie auf **Erweitert**.

6. Klicken Sie auf der Registerkarte **Berechtigungen** auf **Hinzufügen**.

7. Klicken Sie auf **Prinzipal auswählen**, geben Sie **User1** ein, und klicken Sie dann auf **OK**.

8. Wählen Sie unter **Gilt für** die Option **Untergeordnete Benutzerobjekte** aus.

9. Wählen Sie unter **Berechtigungen** Folgendes aus:

    - Kennwort ändern
    - Kennwort zurücksetzen

10. Wählen Sie unter **Eigenschaften** Folgendes aus:
    - Write lockoutTime
    - Write pwdLastSet

11. Klicken Sie dreimal auf **OK**, um die Änderungen zu speichern.

12. Schließen Sie **Active Directory-Benutzer und -Computer**.

Konfigurieren Sie als Nächstes Azure AD Connect auf APP1 für das Rückschreiben des Kennworts.

1. Verbinden Sie APP1 bei Bedarf mit dem Konto „TESTLAB\User1“.

2. Doppelklicken Sie auf dem Desktop von APP1 auf **Azure AD Connect**.

3. Klicken Sie auf der Seite **Willkommen** auf **Konfigurieren**.

4. Wählen Sie auf der Seite **Weitere Aufgaben** die Option **Synchronisierungsoptionen anpassen** aus, und klicken Sie dann auf **Weiter**.

5. Geben Sie auf der Seite **Mit Azure AD verbinden** die Anmeldeinformationen für das globale Administratorkonto ein, und klicken Sie dann auf **Weiter**.

6. Klicken sie auf den Seiten **Verzeichnisse verbinden** und **Domänen-/OE-Filterung** auf **Weiter**.

7. Wählen Sie auf der Seite **Optionale Funktionen** die Option **Kennwortrückschreiben** aus, und klicken Sie auf **Weiter**. 

8. Klicken Sie auf der Seite **Bereit zum Konfigurieren** auf **Konfigurieren** und warten Sie, bis der Vorgang abgeschlossen ist.

9. Wenn die Option zum Abschließen der Konfiguration angezeigt wird, klicken Sie auf **Beenden**.

Sie können jetzt das Kennwortrückschreiben für Benutzer auf Computern testen, die nicht mit dem virtuellen Netzwerk Ihres simulierten Intranets verbunden sind.

Nachfolgend sehen Sie die daraus resultierende Konfiguration:

![Das simulierte Unternehmen mit einer Testumgebung mit Pass-Trought-Authentifizierung](media/pass-through-auth-m365-ent-test-environment/Phase1.png)

Diese Konfiguration besteht aus: 

- Testversionen oder dauerhaften Abonnements von Office 365 E5 und EMS E5 mit der registrieren DNS-Domäne „TESTLAB.\<Ihr Domänenname>.
- Einem vereinfachtem Unternehmensintranet mit Internetzugriff, das aus virtuellen DC1-, APP1- und CLIENT1-Computern in einem Subnetz eines virtuellen Azure-Netzwerks besteht. 
- Azure AD Connect wird auf APP1 ausgeführt, um die Liste von Konten und Gruppen des Azure AD-Mandanten Ihrer Office 365- und EMS E5-Abonnements mit der Windows Server AD-Domäne TESTLAB zu synchronisieren. 
- Kennwortrückschreiben ist aktiviert, damit Benutzer ihre Kennwörter über Azure Active Directory ändern können, ohne mit dem vereinfachten Intranet verbunden sein zu müssen.

Im Schritt [Vereinfachen der Kennwortzurücksetzung](identity-password-reset.md#identity-pw-writeback) in der Identitätsphase finden Sie Informationen und Links zum Konfigurieren des Kennwortrückschreibens in der Produktion.

## <a name="next-step"></a>Nächster Schritt

Sehen Sie sich weitere [Identitäts](m365-enterprise-test-lab-guides.md#identity)features und- funktionen in Ihrer Testumgebung an.

## <a name="see-also"></a>Siehe auch

[Testumgebungsanleitungen für Microsoft 365 Enterprise](m365-enterprise-test-lab-guides.md)

[Bereitstellen von Microsoft 365 Enterprise](deploy-microsoft-365-enterprise.md)

[Dokumentation zu Microsoft 365 Enterprise](https://docs.microsoft.com/microsoft-365-enterprise/)


