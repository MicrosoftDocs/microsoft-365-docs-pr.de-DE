---
title: Kennwortzurücksetzung für Ihre Microsoft 365-Testumgebung
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 04/19/2019
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
description: 'Zusammenfassung: Konfigurieren und Testen der Kennwortzurücksetzung für Ihre Microsoft 365-Testumgebung.'
ms.openlocfilehash: f5fc8d68493464d6b4a6ffdcda64ed9a0d8c7cdd
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32289462"
---
# <a name="password-reset-for-your-microsoft-365-test-environment"></a>Kennwortzurücksetzung für Ihre Microsoft 365-Testumgebung

Die Azure AD Self-Service-Kennwortzurücksetzung (SSPR) erlaubt es Benutzern, ihre Kennwörter oder Konten zurücksetzen oder zu entsperren. 

Dieser Artikel beschreibt, wie Sie die Kennwortzurücksetzung in Ihrer Microsoft 365-Testumgebung in zwei Phasen konfigurieren und testen:

1.  Erstellen Sie die Microsoft 365 Enterprise-Testumgebung.
2.  Konfigurieren Sie und testen Sie die Kennwortzurücksetzung für das Konto von Benutzer 2.
    
![Testumgebungsanleitungen für die Microsoft-Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> Klicken Sie [hier](https://aka.ms/m365etlgstack), um eine visuelle Darstellung aller Artikel im Stapel der Testumgebungsanleitungen in Microsoft 365 Enterprise zu erhalten.

## <a name="phase-1-configure-password-hash-synchronization-and-password-writebback-for-your-microsoft-365-test-environment"></a>Phase 1: Konfigurieren von Kennworthashsynchronisierung und Kennwortrückschreibung für Ihre Microsoft 365-Testumgebung

Befolgen Sie zuerst die Anweisungen unter [Kennworthashsynchronisierung](password-hash-sync-m365-ent-test-environment.md). Hier ist die resultierende Konfiguration.
  
![Das simulierte Unternehmen mit Kennworthashsynchronisierung für die Testumgebung](media/pass-through-auth-m365-ent-test-environment/Phase1.png)
  
Diese Konfiguration besteht aus: 
  
- Testversionen oder kostenpflichtigen Abonnements von Office 365 E5 und EMS E5.
- Einem vereinfachtem Unternehmensintranet mit Internetzugriff, das aus virtuellen DC1-, APP1- und CLIENT1-Computern in einem Subnetz eines virtuellen Azure-Netzwerks besteht. 
- Azure AD Connect wird auf APP1 ausgeführt, um die AD DS-Domäne "TESTLAB" mit dem Azure AD-Mandanten Ihrer Office 365- und EMS E5-Abonnements zu synchronisieren.

Folgen Sie anschließend den Anweisungen unter [Phase 2 der Kennwortrückschreibung](password-writeback-m365-ent-test-environment.md#phase-2-enable-password-writeback-for-the-testlab-ad-ds-domain) der Testumgebungsanleitungen.

Sie müssen das Rückschreiben des Kennworts aktiviert haben, um das Kennwortzurücksetzen verwenden zu können.
  
## <a name="phase-2-configure-and-test-password-reset"></a>Phase 2: Konfigurieren und testen Sie die Kennwortzurücksetzung

In dieser Phase konfigurieren Sie die Kennwortzurücksetzung im Azure AD-Mandanten durch Gruppenmitgliedschaft und vergewissern sich anschließend, dass sie funktioniert.

Aktivieren Sie zunächst die Kennwortzurücksetzung für die Konten in einer bestimmten Azure AD-Gruppe.

1. Öffnen Sie [https://portal.azure.com](https://portal.azure.com) in einer privaten Browserinstanz, und melden Sie sich dann mit den Anmeldeinformationen des globalen Administratorkontos an.
2. Klicken Sie im Azure-Portal auf **Azure Active Directory > Gruppen > Neue Gruppe**.
3. Legen Sie **Gruppentyp** auf **Sicherheit**, **Gruppenname** auf **PWReset** und **Mitgliedschaftstyp** auf **Zugewiesen** fest. Klicken Sie auf **Erstellen**.
5. Klicken Sie auf die Gruppe **PWReset** in der Liste, und klicken Sie dann auf **Mitglieder**.
6. Klicken Sie auf **Mitglieder hinzufügen**, klicken Sie auf **Benutzer 2**, und klicken Sie dann auf **Auswählen**. Schließen Sie die Seiten **PWReset** und **Gruppe**.
7. Klicken Sie auf der Azure Active Directory-Seite auf **Kennwortzurücksetzung**.
8. Wählen Sie auf der Seite **Eigenschaften** unter der Option **Self-Service-Kennwortzurücksetzung aktiviert** die Option **Ausgewählt**.
9. Wählen Sie unter **Gruppe auswählen** den Eintrag **PWReset** aus, und klicken Sie dann auf **Speichern**.
10. Schließen Sie die private Browserinstanz.

Als Nächstes testen Sie die Kennwortzurücksetzung für das Konto von Benutzer 2.

1. Öffnen Sie eine neue private Browserinstanz, und navigieren Sie zu [https://aka.ms/ssprsetup](https://aka.ms/ssprsetup).
2. Melden Sie sich mit den Anmeldeinformationen des Kontos von Benutzer 2 an.
3. Legen Sie unter **Verlieren Sie nicht den Zugriff auf Ihr Konto** Ihre Mobiltelefonnummer als Telefonnummer für die Authentifizierung und Ihr Geschäfts- oder persönliches E-Mail-Konto als E-Mail-Adresse für die Authentifizierung fest.
4. Nachdem beide Angaben überprüft wurden, klicken Sie auf **Sieht gut aus**, und schließen Sie die private Browserinstanz.
5. Öffnen Sie eine neue private Browserinstanz, und wechseln Sie zu [https://aka.ms/sspr](https://aka.ms/sspr).
6. Melden Sie sich mit den Anmeldeinformationen des Kontos von Benutzer 2 an, geben Sie die Zeichen aus dem CAPTCHA ein, und klicken Sie dann auf **Weiter**.
8. Klicken Sie in **Überprüfungsschritt 1** auf **E-Mail an meine alternative E-Mail-Adresse senden**, und klicken Sie dann auf **E-Mail**. Wenn Sie die E-Mail erhalten, geben Sie den Überprüfungscode ein, und klicken Sie dann auf **Weiter**.
9. Geben Sie unter **Wiederherstellen des Kontos** ein neues Kennwort für das Konto von Benutzer 2 ein, und klicken Sie dann auf **Fertig stellen**. Notieren Sie sich das geänderte Kennwort für das Konto von Benutzer 2, und bewahren Sie es an einem sicheren Ort auf.
10. Gehen Sie in einer separaten Registerkarte derselben Browserinstanz zu [https://office.com](https://office.com), und melden Sie sich dann mit dem Kontonamen von Benutzer 2 und dem neuen Kennwort an. Die **Office-Startseite** sollte angezeigt werden.

Im Schritt [Vereinfachen der Kennwortzurücksetzung](identity-password-reset.md#identity-pw-reset) in der Identitätsphase finden Sie Informationen und Links zum Konfigurieren der Kennwortzurücksetzung in der Produktion.

## <a name="next-step"></a>Nächster Schritt

Sehen Sie sich weitere [Identitäts](m365-enterprise-test-lab-guides.md#identity)features und- funktionen in Ihrer Testumgebung an.

## <a name="see-also"></a>Siehe auch

[Testumgebungsanleitungen für Microsoft 365 Enterprise](m365-enterprise-test-lab-guides.md)

[Bereitstellen von Microsoft 365 Enterprise](deploy-microsoft-365-enterprise.md)

[Dokumentation zu Microsoft 365 Enterprise](https://docs.microsoft.com/microsoft-365-enterprise/)
