---
title: Automatisieren der Lizenzierung und Gruppe Mitgliedschaft für Ihre Umgebung für Microsoft 365 Enterprise
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 08/21/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: Ent_O365
ms.custom:
- TLG
- Ent_TLGs
description: Konfigurieren von Arbeitsgruppen-Lizenzierung und dynamische Gruppenmitgliedschaft in Ihrer testumgebung Microsoft 365 Enterprise.
ms.openlocfilehash: 46d2f0ca063b387d1a4a51b4ea97bd5d60c03fe5
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/28/2018
ms.locfileid: "26867947"
---
# <a name="automate-licensing-and-group-membership-for-your-microsoft-365-enterprise-test-environment"></a>Automatisieren der Lizenzierung und Gruppe Mitgliedschaft für Ihre Umgebung für Microsoft 365 Enterprise

Arbeitsgruppen-Lizenzierung automatisch weist oder Lizenzen für ein Benutzerkonto basierend auf der Gruppenmitgliedschaft entfernt. Dynamische Gruppenmitgliedschaft hinzugefügt oder entfernt Mitglieder einer Gruppe basierend auf Benutzerkontoeigenschaften wie Abteilung oder jedes Land. Dieser Artikel führt Sie schrittweise durch eine Demonstration von sowohl in Ihrer testumgebung Microsoft 365 Enterprise.

Es gibt zwei Phasen Auto-Lizenzierung und dynamische Gruppenmitgliedschaft in Ihrer Microsoft 365 Enterprise-testumgebung einrichten:

1. Erstellen der testumgebung Microsoft 365 Enterprise.
2. Konfigurieren und Testen von dynamischen Gruppenmitgliedschaft und automatische Lizenzierung.

![Testumgebungsanleitungen für die Microsoft-Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> Klicken Sie [hier](https://aka.ms/m365etlgstack), um eine visuelle Darstellung aller Artikel im Stapel der Testumgebungsanleitungen in Microsoft 365 Enterprise zu erhalten.
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a>Phase 1: Erstellen Sie Ihre Umgebung für Microsoft 365 Enterprise

Wenn Sie automatisierte Lizenzierung und Gruppenmitgliedschaft auf einfache Weise mit den Mindestanforderungen testen möchten, befolgen Sie die Anweisungen in der [Lightweight Basiskonfiguration](lightweight-base-configuration-microsoft-365-enterprise.md).
  
Wenn Sie automatisierte Lizenzierung und Gruppenmitgliedschaft in einer simulierten Enterprise testen möchten, befolgen Sie die Anweisungen in [Pass-Through-Authentifizierung](pass-through-auth-m365-ent-test-environment.md).
  
> [!NOTE]
> Testen der automatisiert Lizenzierung und Gruppenmitgliedschaft erfordert keinen der simulierten Enterprise-testumgebung, einschließlich einer simulierten Intranet mit dem Internet verbunden und Directory-Synchronisierung für eine Windows Server Active Directory-Gesamtstruktur. Erfolgt hier als eine Option, damit Sie automatisierte Lizenzierung und Gruppenmitgliedschaft testen können, und probieren Sie es in einer Umgebung, die eine typische Organisation darstellt. 
  
## <a name="phase-2-configure-and-test-dynamic-group-membership-and-automatic-licensing"></a>Phase 2: Konfigurieren und Testen von dynamischen Gruppenmitgliedschaft und automatische Lizenzierung

Zuerst erstellen eine neue Gruppe "Sales" und eine dynamische Gruppenmitgliedschaft Regel hinzufügen, sodass Benutzerkonten mit der Abteilung, legen Sie auf dem Umsatz automatisch der Gruppe "Sales" hinzugefügt werden.

1. Verwenden eine private Instanz des Internetbrowsers, melden Sie sich bei Office 365-Portal unter [https://portal.office.com](https://portal.office.com) mit das globale Administratorkonto des Office 365 E5 Test-Abonnement.
2. Wechseln Sie auf einer separaten Registerkarte Ihres Browsers zu der Azure-Portal unter [https://portal.azure.com](https://portal.azure.com).
3. Klicken Sie im Azure-Portal auf **Azure Active Directory > Benutzer und Gruppen > Alle Gruppen**.
4. Klicken Sie auf das Blade **alle Gruppen** auf **neue Gruppe**.
5. Wählen Sie im **Gruppentyp** **Office 365**.
6. Geben Sie im Feld **Gruppenname** **Sales**.
7. Wählen Sie unter **Typ der Mitgliedschaft** **dynamische Benutzer** aus.
8. Klicken Sie auf **Dynamische Abfrage hinzufügen**.
9. Wählen Sie unter **Benutzer hinzufügen**die Option **Abteilung** aus.
10. Wählen Sie im nächsten Feld **Gleich** aus.
11. Geben Sie in das nächste Feld **Sales**.
12. Klicken Sie auf **Abfrage hinzufügen**, und klicken Sie dann auf **Erstellen**.
13. Schließen Sie die **Gruppe** und **alle Gruppen Gruppen** Blade.

Im nächsten Schritt konfigurieren Sie die Gruppe "Sales", sodass Elemente automatisch, Office 365 E5 und Enterprise-Mobilität + Sicherheit E5 Lizenzen zugewiesen sind.

1. Klicken Sie in der **Übersicht über die** Blade für Azure Active Directory, auf **Lizenzen > alle Produkte**.
2. Wählen Sie in der Liste **Enterprise Mobility + Security E5** und **Office 365 Enterprise E5** aus, und klicken Sie dann auf **Zuweisen**.
3. Klicken Sie in der Blade **Lizenz zuweisen** auf **Benutzer und Gruppen**.
4. Wählen Sie in der Liste der Gruppen die Gruppe " **Sales** " aus.
5. Klicken Sie auf **Auswählen** und dann auf **Zuweisen**.
6. Schließen Sie die Registerkarte für das Azure Portal in Ihrem Browser.

Im nächsten Schritt testen Sie dynamische Gruppenmitgliedschaft und automatische Lizenzierung für das Konto des Benutzers 4. 

1. Klicken Sie auf der Registerkarte **Startseite von Microsoft Office** in Ihrem Browser auf **Admin**.
2. Klicken Sie auf der Registerkarte **Office Admin Center** auf **aktive Benutzer**.
3. Klicken Sie auf der Seite **aktive Benutzer** auf das Konto des **Benutzers 4** .
4. Klicken Sie im Bereich **Benutzer 4** für **Lizenzen**auf **Bearbeiten** .
5. Klicken Sie im Bereich **Lizenzen** Aktivieren der **Enterprise-Mobilität + Sicherheit E5** und **Office 365 Enterprise E5** Lizenzen deaktiviert, und klicken Sie dann auf **Speichern > Schließen**.
6. In den Eigenschaften des Kontos Benutzer 4 Stellen Sie sicher, dass keine Lizenzen zugewiesen wurden, und es keine Gruppenmitgliedschaften werden.
7. Klicken Sie auf **Bearbeiten** , um die **Kontaktinformationen**.
8. Klicken Sie auf **Kontaktinformationen**, klicken Sie im Bereich **Kontaktinformationen bearbeiten** .
9. Geben Sie in das Feld **Abteilung** **Sales**, und klicken Sie dann auf **Speichern > Schließen**.
10. Warten Sie einige Minuten, und klicken Sie dann in regelmäßigen Abständen auf das Aktualisierungssymbol in der rechten oberen Ecke des Bereichs Konto Benutzer 4. 

Zeitpunkt sollten Sie sehen die:

- **Gruppenmitgliedschaften** -Eigenschaft mit der Gruppe " **Sales** " aktualisiert.
- **Lizenzen** -Eigenschaft mit der **Mobilität in Unternehmen + Sicherheit E5** und **Office 365 Enterprise E5** Lizenzen aktualisiert.

Finden Sie diese Schritte in der Phase Identität Informationen und Links zu dynamischen Gruppenmitgliedschaft und automatische Lizenzierung in der Produktion bereitstellen:

- [Einrichten der automatischen Lizenzierung](identity-group-based-licensing.md)
- [Einrichten der dynamischen Gruppenmitgliedschaft](identity-automatic-group-membership.md)

## <a name="next-step"></a>Nächster Schritt

Sehen Sie sich weitere [Identitäts](m365-enterprise-test-lab-guides.md#identity)features und- funktionen in Ihrer Testumgebung an.

## <a name="see-also"></a>Siehe auch

[Phase 2: Identität](identity-infrastructure.md)

[Testumgebungsanleitungen für Microsoft 365 Enterprise](m365-enterprise-test-lab-guides.md)

[Bereitstellung von Microsoft 365 Enterprise](deploy-microsoft-365-enterprise.md)

[Dokumentation zu Microsoft 365 Enterprise](https://docs.microsoft.com/microsoft-365-enterprise/)
