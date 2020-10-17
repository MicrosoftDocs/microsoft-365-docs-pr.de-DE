---
title: Datenklassifizierung für Ihre Microsoft 365 für Enterprise-Testumgebung
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/10/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-security-compliance
ms.custom: Ent_TLGs
ms.assetid: 1aa9639b-2862-49c4-bc33-1586dda636b8
description: Verwenden Sie diese Test Umgebungs Anleitung, um Aufbewahrungs Bezeichnungen für Dokumente in Ihrer Microsoft 365 for Enterprise-Testumgebung zu erstellen und zu verwenden.
ms.openlocfilehash: 5cc77167db866d99f0beea5f554a777ecf355046
ms.sourcegitcommit: 53ff1fe6d6143b0bf011031eea9b85dc01ae4f74
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48487732"
---
# <a name="data-classification-for-your-microsoft-365-for-enterprise-test-environment"></a>Datenklassifizierung für Ihre Microsoft 365 für Enterprise-Testumgebung

*Diese Test Umgebungs Anleitung kann sowohl für Microsoft 365 für Unternehmen als auch für Office 365 Enterprise Testumgebungen verwendet werden.*

In diesem Artikel wird beschrieben, wie Sie die Datenklassifizierung mithilfe von Aufbewahrungs Bezeichnungen in Ihrer Microsoft 365 for Enterprise-Testumgebung konfigurieren.

Das Klassifizieren von Daten in Ihrer Testumgebung umfasst drei Phasen:
- [Phase 1: Erstellen der Testumgebung für Microsoft 365 für Unternehmen](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [Phase 2: Erstellen von Aufbewahrungs Bezeichnungen](#phase-2-create-retention-labels)
- [Phase 3: Anwenden von Aufbewahrungs Bezeichnungen auf Dokumente](#phase-3-apply-retention-labels-to-documents)

![Testumgebungsanleitungen für die Microsoft-Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> Eine visuelle Zuordnung zu allen Artikeln im Microsoft 365 for Enterprise Test Lab Guide Stack finden Sie unter [Microsoft 365 for Enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a>Phase 1: Erstellen der Testumgebung für Microsoft 365 für Unternehmen

Wenn Sie Aufbewahrungs Bezeichnungen nur auf einfache Weise mit den Mindestanforderungen konfigurieren möchten, befolgen Sie die Anweisungen unter [Lightweight Base Configuration](lightweight-base-configuration-microsoft-365-enterprise.md).
  
Wenn Sie Aufbewahrungs Bezeichnungen in einem simulierten Unternehmen konfigurieren möchten, befolgen Sie die Anweisungen unter [Pass-Through-Authentifizierung](pass-through-auth-m365-ent-test-environment.md).
  
> [!NOTE]
> Das Testen von Aufbewahrungs Bezeichnungen erfordert nicht die simulierte Enterprise-Testumgebung, die ein simuliertes, mit dem Internet verbundenes Intranet und eine Verzeichnissynchronisierung für eine Active Directory-Domänendienste (AD DS) Gesamtstruktur umfasst. Er wird hier als Option bereitgestellt, damit Sie die automatisierte Lizenzierung und Gruppenmitgliedschaft testen und in einer Umgebung experimentieren können, die eine typische Organisation darstellt.

## <a name="phase-2-create-retention-labels"></a>Phase 2: Erstellen von Aufbewahrungs Bezeichnungen

Erstellen Sie in dieser Phase die Aufbewahrungs Bezeichnungen für die unterschiedlichen Aufbewahrungs Ebenen für SharePoint Online Dokumentordner:

1. Melden Sie sich beim [Microsoft 365-Sicherheitscenter](https://security.microsoft.com/homepage) mit ihrem globalen Administratorkonto an.
1. Wählen Sie auf der Registerkarte **Home-Microsoft 365 Security** in Ihrem Browser **Klassifizierungs**  >  **Aufbewahrungs Bezeichnungen**aus.
1. Wählen Sie **Bezeichnung erstellen** aus.
1. Geben Sie im Bereich **Name Ihres Bezeichnungs** Felds **internal Public** in **Name Your Label**ein, und wählen Sie dann **weiter**aus.
1. Wählen Sie im Bereich **Datei Plan Deskriptoren** die Option **weiter**aus.
1. Legen Sie im Bereich **Bezeichnungs Einstellungen** bei Bedarf die Option **Aufbewahrung** auf **ein**fest, und wählen Sie dann **weiter**aus.
1. Wählen Sie im Bereich **Einstellungen überprüfen** **die Option Bezeichnung erstellen**aus.
1. Wiederholen Sie die Schritte 3 bis 7 für die zusätzlichen Bezeichnungen mit diesen Namen:
  - Private
  - Vertraulich
  - Streng vertraulich
1. Wählen Sie im Bereich **Aufbewahrungs Bezeichnungen** die Option **Bezeichnungen veröffentlichen**aus.
1. Wählen Sie im Bereich **zu veröffentlichende Bezeichnungen** auswählen die Option **zu veröffentlichende Bezeichnungen**auswählen aus.
1. Wählen Sie im Bereich **Beschriftungen** auswählen die Option **Hinzufügen** aus, und wählen Sie alle vier Bezeichnungen aus.
1. Wählen Sie **Hinzufügen**aus, und klicken Sie dann auf **Fertig**.
1. Wählen Sie im Bereich **zu veröffentlichende Bezeichnungen auswählen** die Option **weiter**aus.
1. Wählen Sie im Bereich **Speicherorte** auswählen die Option **weiter**aus.
1. Geben Sie im Bereich **Name Ihrer Richtlinie** unter **Name**die **Beispielorganisation** ein, und wählen Sie dann **weiter**aus.
1. Wählen Sie im Bereich **Einstellungen überprüfen** die Option **Bezeichnungen veröffentlichen**aus.
 
Es kann einige Minuten dauern, bis die Aufbewahrungs Bezeichnungen veröffentlicht werden.

## <a name="phase-3-apply-retention-labels-to-documents"></a>Phase 3: Anwenden von Aufbewahrungs Bezeichnungen auf Dokumente

In dieser Phase ermitteln Sie das Standardverhalten für die Aufbewahrungs Bezeichnung für Dateien im Ordner "Dokumente" einer SharePoint Online Website und ändern die Aufbewahrungs Bezeichnung eines Dokuments manuell.

Erstellen Sie zunächst eine SharePoint Online Teamwebsite auf sensibler Ebene:
  
1. Melden Sie sich mit einer privaten Instanz Ihres Browsers beim [Microsoft 365 Admin Center](https://admin.microsoft.com) mit ihrem globalen Administratorkonto an.
1. Wählen Sie in der Kachel Liste die Option **SharePoint**aus.
1. Wählen Sie auf der neuen **SharePoint** -Registerkarte in Ihrem Browser **Website erstellen**aus.
1. Wählen Sie auf der Seite **Website erstellen** die Option **Teamwebsite** aus.
1. Geben Sie im Feld **Name der Team Website den Namen** **SensitiveFiles**ein.
1. Geben Sie im Feld **Beschreibung der Team Website** die Option **SharePoint-Website für vertrauliche Dateien**ein.
1. Wählen Sie unter **Datenschutzeinstellungen** **die Option Privat nur Mitglieder können auf diese Website zugreifen**aus, und wählen Sie dann **weiter**aus.
1. Wählen Sie im Bereich **Wen möchten Sie hinzufügen?** die Option **Fertig stellen**aus.
    
Konfigurieren Sie als nächstes den Ordner "Dokumente" der SensitiveFiles-Teamwebsite für die Bezeichnung für die vertrauliche Aufbewahrung.
  
1. Wählen Sie auf der Registerkarte **SensitiveFiles** Ihres Browsers die Option **Dokumente**aus.
1. Wählen Sie das Symbol **Einstellungen** aus, und wählen Sie dann **Bibliothekseinstellungen**aus.
1. Wählen Sie unter **Berechtigungen und Verwaltung** **die Option Bezeichnung auf Elemente in dieser Liste oder Bibliothek anwenden**aus. Wenn diese Option nicht angezeigt wird, werden Ihre Aufbewahrungs Bezeichnungen noch nicht veröffentlicht. Versuchen Sie diesen Schritt zu einem späteren Zeitpunkt.
1. Wählen Sie unter **Einstellungen – Bezeichnung anwenden**die Option **vertraulich** im Dropdownfeld aus, und wählen Sie dann **Speichern**aus.

Erstellen Sie als nächstes ein neues Dokument auf der SensitiveFiles-Website, und ändern Sie dessen Aufbewahrungs Bezeichnung.
    
1. Wählen Sie im Ordner Dokumente die Option **Neues**  >  **Word-Dokument**aus.
1. Geben Sie einen Text in das leere Dokument ein. Warten Sie, bis der Text gespeichert wird.
1. Wählen Sie in der Menüleiste **freigegebene Dokumente**aus.
1. Wählen Sie neben dem Namen der **Document.docx** Datei die vertikalen Auslassungspunkte aus, und wählen Sie dann **Details**aus.
1. Beachten Sie im rechten Bereich im Abschnitt **Eigenschaften** unter **Aufbewahrungs Bezeichnung anwenden**, dass für das Dokument die Aufbewahrungs Bezeichnung für **vertrauliche** Dokumente automatisch angewendet wurde.
1. Klicken Sie auf **Alle bearbeiten**.
1. Wählen Sie im Bereich **Document.docx** unter **Aufbewahrungs Bezeichnung anwenden**die Bezeichnung **streng vertraulich** aus, und wählen Sie dann **Speichern**aus.

## <a name="next-step"></a>Nächster Schritt

Untersuchen Sie zusätzliche Features und Funktionen für den [Informationsschutz](m365-enterprise-test-lab-guides.md#information-protection) in Ihrer Testumgebung.

## <a name="see-also"></a>Siehe auch

[Testumgebungsanleitungen für Microsoft 365 Enterprise](m365-enterprise-test-lab-guides.md)

[Übersicht über Microsoft 365 Enterprise](microsoft-365-overview.md)

[Dokumentation zu Microsoft 365 für Unternehmen](https://docs.microsoft.com/microsoft-365-enterprise/)
