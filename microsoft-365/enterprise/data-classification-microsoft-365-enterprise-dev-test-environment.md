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
ms.openlocfilehash: 171fcb74b09a1f2e5c80f23e010640dce55660bc
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46686406"
---
# <a name="data-classification-for-your-microsoft-365-for-enterprise-test-environment"></a>Datenklassifizierung für Ihre Microsoft 365 für Enterprise-Testumgebung

*Diese Test Umgebungs Anleitung kann sowohl für Microsoft 365 für Unternehmen als auch für Office 365 Enterprise Testumgebungen verwendet werden.*

Mit den Anweisungen in diesem Artikel Konfigurieren Sie die Datenklassifizierung mithilfe von Aufbewahrungs Bezeichnungen in Ihrer Microsoft 365 for Enterprise-Testumgebung.

![Testumgebungsanleitungen für die Microsoft-Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> Klicken Sie [hier](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf), um eine visuelle Darstellung aller Artikel im Stapel der Testumgebungsanleitungen in Microsoft 365 Enterprise zu erhalten.
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a>Phase 1: Erstellen der Testumgebung für Microsoft 365 für Unternehmen

Wenn Sie Aufbewahrungs Bezeichnungen nur auf einfache Weise mit den Mindestanforderungen konfigurieren möchten, befolgen Sie die Anweisungen unter [Lightweight Base Configuration](lightweight-base-configuration-microsoft-365-enterprise.md).
  
Wenn Sie Aufbewahrungs Bezeichnungen in einem simulierten Unternehmen konfigurieren möchten, befolgen Sie die Anweisungen unter [Pass-Through-Authentifizierung](pass-through-auth-m365-ent-test-environment.md).
  
> [!NOTE]
> Das Testen von Aufbewahrungs Bezeichnungen erfordert keine simulierte Enterprise-Testumgebung, die ein simuliertes Intranet enthält, das mit dem Internet verbunden ist, und die Verzeichnissynchronisierung für eine Active Directory-Domänendienste (AD DS) Gesamtstruktur. Sie wird hier als Option bereitgestellt, damit Sie die automatisierte Lizenzierung und Gruppenmitgliedschaft testen und in einer Umgebung experimentieren können, die eine typische Organisation darstellt. 

## <a name="phase-2-create-retention-labels"></a>Phase 2: Erstellen von Aufbewahrungs Bezeichnungen

In dieser Phase erstellen Sie die Aufbewahrungs Bezeichnungen für die unterschiedlichen Aufbewahrungs Ebenen für SharePoint Online Dokumentordner.

1. Melden Sie sich beim [Microsoft 365-Sicherheitscenter](https://security.microsoft.com/homepage) mit ihrem globalen Administratorkonto an.
    
2. Klicken Sie auf der Registerkarte " **Start-Microsoft 365 Security** " Ihres Browsers auf **Klassifizierung > Aufbewahrungs Bezeichnungen**.
    
3. Klicken Sie auf **Bezeichnung erstellen**.
    
4. Geben Sie im Bereich **Name Ihrer** Bezeichnung den Namen **internal Public** in **Name Your Label**ein, und klicken Sie dann auf **weiter**.

5. Klicken Sie im Bereich **Datei Plan Deskriptoren** auf **weiter**.
    
6. Legen Sie im Bereich **Bezeichnungs Einstellungen** bei Bedarf **Retention** die Beibehaltung **auf ein**fest, und klicken Sie dann auf **weiter**.
    
7. Klicken Sie im Bereich **Einstellungen überprüfen** auf **Bezeichnung erstellen**.
    
8. Wiederholen Sie die Schritte 3 bis 7 für die zusätzlichen Bezeichnungen mit diesen Namen:
    
  - Private
    
  - Vertraulich
    
  - Streng vertraulich
  
9. Klicken Sie im Bereich **Aufbewahrungs Bezeichnungen** auf **Bezeichnungen veröffentlichen**.
    
10. Klicken Sie im Bereich **zu veröffentlichende Bezeichnungen auswählen** auf **Bezeichnungen zur Veröffentlichung auswählen**.
    
11. Klicken Sie im Bereich **Beschriftungen auswählen** auf **Hinzufügen** , und wählen Sie alle vier Bezeichnungen aus.
    
12. Klicken Sie auf **Hinzufügen** und dann auf **Fertig**.
    
13. Klicken Sie im Bereich **Zu veröffentlichende Bezeichnungen wählen** auf **Weiter**.
    
14. Klicken Sie im Bereich **Speicherorte auswählen** auf **Weiter**.
    
15. Geben Sie im Bereich **Richtlinie benennen** **Beispielorganisation** unter **Name** ein, und klicken Sie dann auf **Weiter**.
    
16. Klicken Sie im Bereich **Einstellungen überprüfen** auf **Bezeichnungen veröffentlichen**.
 
Beachten Sie, dass es einige Minuten dauern kann, bis die Aufbewahrungs Bezeichnungen veröffentlicht werden.

## <a name="phase-3-apply-retention-labels-to-documents"></a>Phase 3: Anwenden von Aufbewahrungs Bezeichnungen auf Dokumente

In dieser Phase ermitteln Sie das Standardverhalten für die Aufbewahrungs Bezeichnung für Dateien im Ordner "Dokumente" einer SharePoint Online Website und ändern die Aufbewahrungs Bezeichnung eines Dokuments manuell.

Erstellen Sie zunächst eine SharePoint Online Teamwebsite auf sensibler Ebene:
  
1. Melden Sie sich mit einer privaten Instanz Ihres Browsers beim [Microsoft 365 Admin Center](https://admin.microsoft.com) mit ihrem globalen Administratorkonto an.
    
2. Klicken Sie in der Liste der Kacheln auf **SharePoint**.
    
3. Klicken Sie auf der neuen **SharePoint** -Registerkarte in Ihrem Browser auf **Website erstellen**.
    
4. Klicken Sie auf der Seite **Website erstellen** auf **Teamwebsite**.
    
5. Geben Sie unter **Name der Team Website den Namen** **SensitiveFiles**ein.
    
6. Geben Sie unter **Beschreibung der Team Website** **den Text SharePoint-Website für vertrauliche Dateien**ein.
    
7.  Wählen Sie unter **Datenschutzeinstellungen** die Option **Privat - nur Mitglieder können auf diese Website zugreifen** aus, und klicken Sie dann auf **Weiter**.
    
8. Klicken Sie im Bereich **Wen möchten Sie hinzufügen?** auf **Fertig stellen**.
    
Konfigurieren Sie als nächstes den Ordner "Dokumente" der SensitiveFiles-Teamwebsite für die Bezeichnung für die vertrauliche Aufbewahrung.
  
1. Klicken Sie auf der Registerkarte **SensitiveFiles** in Ihrem Browser auf **Dokumente**.
    
2. Klicken Sie auf das Symbol für Einstellungen und anschließend auf **Bibliothekeinstellungen**.
    
3. Klicken Sie unter **Berechtigungen und Verwaltung**auf **Bezeichnung auf Elemente in dieser Liste oder Bibliothek anwenden**. Wenn diese Option nicht angezeigt wird, werden Ihre Aufbewahrungs Bezeichnungen noch nicht veröffentlicht. Versuchen Sie diesen Schritt zu einem späteren Zeitpunkt.
    
4. Wählen Sie unter **Einstellungen – Bezeichnung anwenden**die Option **vertraulich** im Dropdownfeld aus, und klicken Sie dann auf **Speichern**.

Erstellen Sie als nächstes ein neues Dokument auf der SensitiveFiles-Website, und ändern Sie dessen Aufbewahrungs Bezeichnung.
    
1. Klicken Sie im Ordner Dokumente auf **Neues > Word-Dokument**.
    
2. Geben Sie Text in das leere Dokument ein. Warten Sie, bis der Text gespeichert wird.
    
3. Klicken Sie in der Menüleiste auf **freigegebene Dokumente**.
    
4. Klicken Sie auf die vertikalen Auslassungspunkte neben dem Namen der **Document.docx** Datei, und klicken Sie dann auf **Details**.
    
5. Beachten Sie im rechten Bereich im Abschnitt **Eigenschaften** unter **Aufbewahrungs Bezeichnung anwenden**, dass für das Dokument die Bezeichnung für die **vertrauliche** Aufbewahrung automatisch angewendet wurde.
    
6. Klicken Sie auf **Alle bearbeiten**.
    
7. Wählen Sie im Bereich **Document.docx** unter **Aufbewahrungs Bezeichnung anwenden**die Bezeichnung **streng vertraulich** aus, und klicken Sie dann auf **Speichern**.

## <a name="next-step"></a>Nächster Schritt

Untersuchen Sie zusätzliche Features und Funktionen für den [Informationsschutz](m365-enterprise-test-lab-guides.md#information-protection) in Ihrer Testumgebung.

## <a name="see-also"></a>Siehe auch

[Testumgebungsanleitungen für Microsoft 365 Enterprise](m365-enterprise-test-lab-guides.md)

[Übersicht über Microsoft 365 Enterprise](microsoft-365-overview.md)

[Dokumentation zu Microsoft 365 für Unternehmen](https://docs.microsoft.com/microsoft-365-enterprise/)

 
