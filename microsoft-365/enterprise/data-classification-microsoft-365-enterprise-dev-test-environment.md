---
title: Klassifizierung von Daten für Ihr Unternehmen der Microsoft 365 test Environment.
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/16/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: Ent_O365
ms.custom: Ent_TLGs
ms.assetid: 1aa9639b-2862-49c4-bc33-1586dda636b8
description: Verwenden Sie diese Test Lab Guide erstellen und Verwenden von Office 365 Etiketten auf Dokumente in Ihrer testumgebung Microsoft 365 Enterprise.
ms.openlocfilehash: 33ac1fa8e26c0037882e6c240cc04ec19e6a6a7b
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/16/2019
ms.locfileid: "26868173"
---
# <a name="data-classification-for-your-microsoft-365-enterprise-test-environment"></a>Klassifizierung von Daten für Ihr Unternehmen der Microsoft 365 test Environment.

Mit den Anweisungen in diesem Artikel konfigurieren Sie mithilfe von Office 365 Aufbewahrung Bezeichnungen in Ihrer unternehmensumgebung Microsoft 365 Test Datenklassifikation.

![Testumgebungsanleitungen für die Microsoft-Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> Klicken Sie [hier](https://aka.ms/m365etlgstack), um eine visuelle Darstellung aller Artikel im Stapel der Testumgebungsanleitungen in Microsoft 365 Enterprise zu erhalten.
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a>Phase 1: Erstellen Sie Ihre Umgebung für Microsoft 365 Enterprise

Wenn Sie Office 365 Beschriftungen auf einfache Weise mit den Mindestanforderungen konfigurieren möchten, befolgen Sie die Anweisungen in der [Lightweight Basiskonfiguration](lightweight-base-configuration-microsoft-365-enterprise.md).
  
Wenn Sie Office 365 Bezeichnungen in einer simulierten Enterprise konfigurieren möchten, befolgen Sie die Anweisungen in [Pass-Through-Authentifizierung](pass-through-auth-m365-ent-test-environment.md).
  
> [!NOTE]
> Testen Office 365 Etiketten erfordert keinen der simulierten Enterprise-testumgebung, einschließlich einer simulierten Intranet mit dem Internet verbunden und Directory-Synchronisierung für eine Windows Server Active Directory-Gesamtstruktur. Erfolgt hier als eine Option, damit Sie automatisierte Lizenzierung und Gruppenmitgliedschaft testen können, und probieren Sie es in einer Umgebung, die eine typische Organisation darstellt. 

## <a name="phase-2-create-office-365-labels"></a>Phase 2: Erstellen von Office 365-Bezeichnungen

In dieser Phase erstellen Sie die Beschriftungen für die verschiedenen Berechtigungsstufen Aufbewahrung für SharePoint Online Dokumente Ordner.
  
1. Falls erforderlich, verwenden Sie eine private Instanz des Internetbrowsers, und melden Sie sich das Office-Portal mit Ihrer globalen Administratorkonto an. Hilfe finden Sie unter [Where zur Anmeldung bei Office 365](https://support.office.com/Article/Where-to-sign-in-to-Office-365-e9eb7d51-5430-4929-91ab-6157c5a050b4).
    
2. Klicken Sie auf der Registerkarte **Microsoft Office Home** auf die Kachel **Admin**.
    
3. Klicken Sie auf der neuen Registerkarte **Office Admin Center** im Browser auf **Admin Center > Security &amp; Compliance**.
    
4. Von der neuen **Home - Sicherheit &amp; Compliance** Registerkarte des Browsers, klicken Sie auf **Klassifikationen > Etiketten**. Aus der **Home > Etiketten** Bereich, klicken Sie auf der Registerkarte **Archivierung** .
    
5. Klicken Sie auf **eine Beschriftung erstellen**.
    
6. Geben Sie im Bereich **Name für Bezeichnung** **Intern Öffentlich** ein, und klicken Sie dann auf **Weiter**.
    
7. Klicken Sie im Bereich **Bezeichnungseinstellungen** auf **Weiter**.
    
8. Klicken Sie im Bereich **Einstellungen überprüfen** auf **Bezeichnung erstellen**, und klicken Sie dann auf **Schließen**.
    
9. Wiederholen Sie die Schritte 5 bis 8 für diese zusätzlichen Bezeichnungen:
    
  - Private
    
  - Vertraulich
    
  - Streng vertraulich
    
10. Klicken Sie im Bereich **Startseite > Bezeichnungen** auf **Bezeichnungen veröffentlichen**.
    
11. Klicken Sie im Bereich **Zu veröffentlichende Bezeichnungen wählen** auf **Zu veröffentlichende Bezeichnungen wählen**
    
12. Klicken Sie im Bereich **Choose labels** (Bezeichnungen auswählen) auf **Hinzufügen**, wählen Sie alle vier Bezeichnungen aus.
    
13. Klicken Sie auf **Fertig**.
    
14. Klicken Sie im Bereich **Zu veröffentlichende Bezeichnungen wählen** auf **Weiter**.
    
15. Klicken Sie im Bereich **Speicherorte auswählen** auf **Weiter**.
    
16. Geben Sie im Bereich **Richtlinie benennen** **Beispielorganisation** unter **Name** ein, und klicken Sie dann auf **Weiter**.
    
17. Klicken Sie im Bereich **Einstellungen überprüfen** auf **Bezeichnungen veröffentlichen**, und klicken Sie dann auf **Schließen**.

Beachten Sie, dass es ein paar Minuten für die Beschriftungen zu veröffentlichenden dauern kann.

## <a name="phase-3-apply-office-365-retention-labels-to-documents"></a>Phase 3: Office 365 Aufbewahrung Etiketten auf Dokumente anwenden

In dieser Phase ermitteln das Standardverhalten für die Beschriftung für Dateien im Ordner "Dokumente" einer SharePoint Online-Website und Manuelles Ändern der Beschriftung eines Dokuments.

Erstellen Sie zunächst eine Sensitive-Ebene SharePoint Online-Teamwebsite:
  
1. Melden Sie sich mit einem Browser auf dem lokalen Computer an, in das Office-Portal mit Ihrem Konto globaler Administrator. Hilfe finden Sie unter [Where zur Anmeldung bei Office 365](https://support.office.com/Article/Where-to-sign-in-to-Office-365-e9eb7d51-5430-4929-91ab-6157c5a050b4).
    
2. Klicken Sie in der Liste von Kacheln auf **SharePoint**.
    
3. Klicken Sie auf der neuen Registerkarte **SharePoint** in Ihrem Browser auf **Website erstellen**.
    
4. Klicken Sie auf der Seite **Website erstellen** auf **Teamwebsite**.
    
5. Geben Sie in das Feld **Teamname Website** **SensitiveFiles**.
    
6. Geben Sie im Feld **websitebeschreibung Team** **SharePoint-Website für vertrauliche Dateien**.
    
7.  Wählen Sie unter **Datenschutzeinstellungen** die Option **Privat - nur Mitglieder können auf diese Website zugreifen** aus, und klicken Sie dann auf **Weiter**.
    
8. Klicken Sie im Bereich **Wer soll hinzugefügt werden?** auf **Fertig stellen**.
    
Konfigurieren Sie anschließend den Dokumentenordner der Teamwebsite SensitiveFiles für die Bezeichnung vertrauliche.
  
1. Klicken Sie auf der Registerkarte **SensitiveFiles** Ihres Browsers auf **Dokumente**.
    
2. Klicken Sie auf das Symbol „Einstellungen“, und klicken Sie dann auf **Bibliothekseinstellungen**.
    
3. Klicken Sie unter **Berechtigungen und Verwaltung** auf **Bezeichnung auf Elemente in dieser Bibliothek anwenden**.
    
4. **Bezeichnung Einstellungen anwenden**wählen Sie im Dropdown- **vertrauliche** aus, und klicken Sie dann auf **Speichern**.

Im nächsten Schritt erstellen Sie ein neues Dokument auf der Website SensitiveFiles, und ändern Sie dessen Beschriftung.
    
1. Klicken Sie im Dokumentenordner auf **Neu > Word-Dokument**.
    
2. Geben Sie Text in das leere Dokument. Warten Sie auf den Text gespeichert werden soll.
    
3. Klicken Sie in der Menüleiste auf **Freigegebene Dokumente**.
    
4. Klicken Sie auf das Word-Symbol neben dem Dateinamen **Document.docx** .
    
5. Beachten Sie im rechten Bereich, in den Abschnitt **Eigenschaften** unter **Übernehmen Aufbewahrung Label**, dass das Dokument die Bezeichnung des **vertrauliche** automatisch angewendet wurde.
    
6. Klicken Sie auf **alle zu bearbeiten**.
    
7. Wählen Sie im Bereich **Document.docx** unter **Übernehmen Beschriftung**die **Streng vertraulich** Beschriftung, und klicken Sie dann auf **Speichern**.

Finden Sie im Schritt [Configure Klassifizierung für Ihre Umgebung](infoprotect-configure-classification.md) in der Phase **Information Protection** Informationen und Links zu Office 365 Aufbewahrung Bezeichnungen in der Produktion.

## <a name="next-step"></a>Nächster Schritt

Hier finden Sie zusätzliche [Informationen Protection](m365-enterprise-test-lab-guides.md#information-protection) Features und Funktionen in Ihrer testumgebung.

## <a name="see-also"></a>Siehe auch

[Testumgebungsanleitungen für Microsoft 365 Enterprise](m365-enterprise-test-lab-guides.md)

[Bereitstellen von Microsoft 365 Enterprise](deploy-microsoft-365-enterprise.md)

[Dokumentation zu Microsoft 365 Enterprise](https://docs.microsoft.com/microsoft-365-enterprise/)

 