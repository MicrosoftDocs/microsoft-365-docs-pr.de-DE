---
title: Datenklassifizierung für Ihre Microsoft 365 Enterprise-Testumgebung
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 04/10/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-security-compliance
ms.custom: Ent_TLGs
ms.assetid: 1aa9639b-2862-49c4-bc33-1586dda636b8
description: Verwenden Sie dieses Test Labor Handbuch, um Office 365-Aufbewahrungs Bezeichnungen für Dokumente in Ihrer Microsoft 365 Enterprise-Testumgebung zu erstellen und zu verwenden.
ms.openlocfilehash: 66e06f9a89b102c131bc29af17c4564fabbab9b4
ms.sourcegitcommit: 66bb5af851947078872a4d31d3246e69f7dd42bb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/15/2019
ms.locfileid: "34072415"
---
# <a name="data-classification-for-your-microsoft-365-enterprise-test-environment"></a>Datenklassifizierung für Ihre Microsoft 365 Enterprise-Testumgebung

Mit den Anweisungen in diesem Artikel Konfigurieren Sie die Datenklassifizierung mithilfe von Office 365-Aufbewahrungs Bezeichnungen in Ihrer Microsoft 365 Enterprise-Testumgebung.

![Testumgebungsanleitungen für die Microsoft-Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> Klicken Sie [hier](https://aka.ms/m365etlgstack), um eine visuelle Darstellung aller Artikel im Stapel der Testumgebungsanleitungen in Microsoft 365 Enterprise zu erhalten.
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a>Phase 1: Erstellen Ihrer Microsoft 365 Enterprise-Testumgebung

Wenn Sie nur Office 365-Aufbewahrungs Bezeichnungen auf einfache Weise mit den Mindestanforderungen konfigurieren möchten, befolgen Sie die Anweisungen unter [Lightweight Base Configuration](lightweight-base-configuration-microsoft-365-enterprise.md).
  
Wenn Sie Office 365-Aufbewahrungs Bezeichnungen in einem simulierten Unternehmen konfigurieren möchten, befolgen Sie die Anweisungen unter [Passthrough-Authentifizierung](pass-through-auth-m365-ent-test-environment.md).
  
> [!NOTE]
> Das Testen von Office 365-Aufbewahrungs Bezeichnungen erfordert nicht die simulierte Unternehmens Testumgebung, die ein simuliertes Intranet enthält, das mit dem Internet und der Verzeichnissynchronisierung für eine Active Directory-Domänendienste (AD DS) verbunden ist. Sie wird hier als Option bereitgestellt, damit Sie die automatisierte Lizenzierung und die Gruppenmitgliedschaft testen und mit dieser in einer Umgebung experimentieren können, die eine typische Organisation darstellt. 

## <a name="phase-2-create-office-365-retention-labels"></a>Phase 2: Erstellen von Office 365-Aufbewahrungs Bezeichnungen

In dieser Phase erstellen Sie die Aufbewahrungs Bezeichnungen für die verschiedenen Aufbewahrungs Ebenen für SharePoint Online-Dokumentordner.

1. Melden Sie sich beim [Microsoft 365 Compliance-Portal](https://compliance.microsoft.com) mit Ihrem globalen Administratorkonto an.
    
2. Klicken Sie auf der Registerkarte **Start – Microsoft 365 Compliance ** im Browser auf **Klassifizierungen > Bezeichnungen**.
    
3. Klicken Sie auf **Aufbewahrungsbezeichnung > Erstellen einer Bezeichnung**.
    
4. Geben Sie im Bereich **Name für Bezeichnung****Intern Öffentlich** ein, und klicken Sie dann auf **Weiter**.

5. Klicken Sie im Bereich **Dateiplanbeschreibungen** auf **Weiter**.
    
6. Legen Sie im Bereich **Bezeichnungseigenschaften**, falls erforderlich, **Aufbewahrung** auf **Ein** fest, und klicken Sie dann auf **Weiter**.
    
7. Klicken Sie im Bereich **Einstellungen überprüfen** auf **Beschriftung erstellen**.
    
8. Wiederholen Sie die Schritte 3 bis 7 für die zusätzlichen Bezeichnungen mit diesen Namen:
    
  - Private
    
  - Vertraulich
    
  - Streng vertraulich
  
9. Klicken Sie im Bereich **Startseite > Bezeichnungen** auf **Bezeichnungen veröffentlichen**.
    
10. Klicken Sie im Bereich **Zu veröffentlichende Bezeichnungen wählen** auf **Zu veröffentlichende Bezeichnungen wählen**
    
11. Klicken Sie im Bereich **Choose labels** (Bezeichnungen auswählen) auf **Hinzufügen**, wählen Sie alle vier Bezeichnungen aus.
    
12. Klicken Sie auf **Fertig**.
    
13. Klicken Sie im Bereich **Zu veröffentlichende Bezeichnungen wählen** auf **Weiter**.
    
14. Klicken Sie im Bereich **Speicherorte auswählen** auf **Weiter**.
    
15. Geben Sie im Bereich **Richtlinie benennen** **Beispielorganisation** unter **Name** ein, und klicken Sie dann auf **Weiter**.
    
16. Klicken Sie im Bereich **Einstellungen überprüfen** auf **Bezeichnungen veröffentlichen**, und klicken Sie dann auf **Schließen**.
 
Beachten Sie, dass es einige Minuten dauern kann, bis die Aufbewahrungs Bezeichnungen veröffentlicht werden.

## <a name="phase-3-apply-office-365-retention-labels-to-documents"></a>Phase 3: Anwenden von Office 365-Aufbewahrungs Bezeichnungen auf Dokumente

In dieser Phase erkennen Sie das Standardverhalten der Aufbewahrungs Bezeichnung für Dateien im Ordner "Dokumente" einer SharePoint Online-Website und ändern die Aufbewahrungs Bezeichnung eines Dokuments manuell.

Erstellen Sie zunächst eine SharePoint Online-Teamwebsite auf vertraulicher Ebene:
  
1. Verwenden Sie einen Browser auf dem lokalen Computer, und melden Sie sich im [Office 365-Portal](https://portal.office.com) mit Ihrem globalen Administratorkonto an.
    
2. Klicken Sie in der Liste der Kacheln auf **SharePoint**.
    
3. Klicken Sie auf der neuen Registerkarte **SharePoint** in Ihrem Browser auf **Website erstellen**.
    
4. Klicken Sie auf der Seite **Website erstellen** auf **Teamwebsite**.
    
5. Geben Sie unter **Name der Team Website** **SensitiveFiles**.
    
6. Geben Sie unter **Beschreibung der Team Website** **den Text SharePoint-Website für vertrauliche Dateien**ein.
    
7.  Wählen Sie unter **Datenschutzeinstellungen** die Option **Privat - nur Mitglieder können auf diese Website zugreifen** aus, und klicken Sie dann auf **Weiter**.
    
8. Klicken Sie im Bereich **Wer soll hinzugefügt werden?** auf **Fertig stellen**.
    
Konfigurieren Sie als nächstes den Ordner "Dokumente" der SensitiveFiles-Teamwebsite für die vertrauliche Aufbewahrungs Bezeichnung.
  
1. Klicken Sie auf der Registerkarte **SensitiveFiles** des Browsers auf **Dokumente**.
    
2. Klicken Sie auf das Symbol für Einstellungen und anschließend auf **Bibliothekeinstellungen**.
    
3. Klicken Sie unter **Berechtigungen und Verwaltung** auf **Bezeichnung auf Elemente in dieser Bibliothek anwenden**.
    
4. Wählen Sie in der Dropdownliste unter **Einstellungen-Bezeichnung anwenden**die Option **vertraulich** aus, und klicken Sie dann auf **Speichern**.

Erstellen Sie als nächstes ein neues Dokument auf der SensitiveFiles-Website, und ändern Sie dessen Aufbewahrungs Bezeichnung.
    
1. Klicken Sie im Ordner Dokumente auf **Neues > Word-Dokument**.
    
2. Geben Sie im leeren Dokument Text ein. Warten Sie, bis der Text gespeichert wird.
    
3. Klicken Sie in der Menüleiste auf **freigegebene Dokumente**.
    
4. Klicken Sie auf das Word-Symbol neben dem Dateinamen **Document. docx** .
    
5. Beachten Sie im rechten Bereich im Abschnitt **Eigenschaften** unter **Aufbewahrungs Bezeichnung anwenden**, dass das Dokument die vertrauliche Bezeichnung automatisch angewendet hat **** .
    
6. Klicken Sie auf **alle bearbeiten**.
    
7. Wählen Sie im Bereich **Document. docx** unter **Bezeichnung anwenden**die Bezeichnung **streng vertraulich** aus, und klicken Sie dann auf **Speichern**.

Informationen und Links dazu, wie Sie Office 365- **** Aufbewahrungs Bezeichnungen in der Produktion bereitstellen, finden Sie unter [Konfigurieren der Klassifizierung für Ihre Umgebung](infoprotect-configure-classification.md) .

## <a name="next-step"></a>Nächster Schritt

Erkunden Sie zusätzliche Features und Funktionen zum [Schutz von Informationen](m365-enterprise-test-lab-guides.md#information-protection) in Ihrer Testumgebung.

## <a name="see-also"></a>Siehe auch

[Testumgebungsanleitungen für Microsoft 365 Enterprise](m365-enterprise-test-lab-guides.md)

[Bereitstellen von Microsoft 365 Enterprise](deploy-microsoft-365-enterprise.md)

[Dokumentation zu Microsoft 365 Enterprise](https://docs.microsoft.com/microsoft-365-enterprise/)

 