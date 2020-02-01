---
title: Anzeigen der Berichtr zur Verhinderung von Datenverlust
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 6/7/2018
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection:
- M365-security-compliance
localization_priority: Normal
search.appverid:
- MOE150
- MET150
description: Mit den DLP-Berichten in Office 365 können Sie schnell sehen, wie viele DLP-Richtlinien übereinstimmen, Außerkraftsetzungen oder falsch positive Ergebnisse aufweisen. Überprüfen, ob Sie im Laufe der Zeit nach oben oder unten tendieren Filtern des Berichts auf unterschiedliche Weise und weitere Details anzeigen, indem Sie einen Punkt in einer Kurve im Diagramm auswählen.
ms.openlocfilehash: 1605e2ebed9ada5903402ae5facdb40ce2f12c39
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2020
ms.locfileid: "41601232"
---
# <a name="view-the-reports-for-data-loss-prevention"></a>Anzeigen der Berichtr zur Verhinderung von Datenverlust

Nachdem Sie die DLP-Richtlinien (Data Loss Prevention, Verhinderung von Datenverlust) erstellt haben, sollten Sie überprüfen, ob Sie wie beabsichtigt arbeiten und Ihnen dabei helfen, die Kompatibilität zu verbringen. Mit den DLP-Berichten im Office 365 Security &amp; Compliance Center können Sie schnell Folgendes anzeigen:
  
- **Übereinstimmungen mit DLP-Richtlinien** Dieser Bericht zeigt die Anzahl der DLP-Richtlinien Übereinstimmungen im Laufe der Zeit an. Sie können den Bericht nach Datum, Ort, Richtlinie oder Aktion filtern. Sie können diesen Bericht für Folgendes verwenden: 
    
  - Optimieren oder optimieren Sie Ihre DLP-Richtlinien, während Sie Sie im Testmodus ausführen. Sie können die spezifische Regel anzeigen, die mit dem Inhalt übereinstimmt.
    
  - Sie können sich auf bestimmte Zeiträume konzentrieren und so mehr über die Gründe für Spitzen und Trends erfahren.
    
  - Sie können die Geschäftsprozesse ermitteln, die gegen die DLP-Richtlinien Ihrer Organisation verstoßen.
    
  - Grundlegendes zu den geschäftlichen Auswirkungen der DLP-Richtlinien, indem Sie sehen, welche Aktionen auf Inhalte angewendet werden.
    
  - Sie können die Einhaltung einer bestimmten DLP-Richtlinie durch Anzeigen von Übereinstimmungen für diese Richtlinie überprüfen.
    
  - Zeigen Sie eine Liste der wichtigsten Benutzer an, und wiederholen Sie Benutzer, die zu Vorfällen in Ihrer Organisation beitragen.
    
  - Zeigen Sie eine Liste der wichtigsten Typen vertraulicher Informationen in Ihrer Organisation an.
    
- **DLP-Vorfälle** In diesem Bericht werden auch Richtlinien Übereinstimmungen im Laufe der Zeit angezeigt, wie der Bericht "Richtlinien Übereinstimmungen". Der Bericht "Richtlinien Übereinstimmungen" zeigt jedoch Übereinstimmungen auf Regelebene an; Wenn beispielsweise eine e-Mail mit drei unterschiedlichen Regeln übereinstimmt, zeigt der Bericht "Richtlinien Übereinstimmungen" drei verschiedene Einzelposten an. Im Gegensatz dazu zeigt der Vorfall Bericht Übereinstimmungen auf Elementebene; Wenn beispielsweise eine e-Mail mit drei unterschiedlichen Regeln übereinstimmt, zeigt der Vorfall Bericht ein einzelnes Einzelposten Element für diesen Inhalt. 
    
  Da die Berichts Anzahl unterschiedlich aggregiert wird, ist der Bericht "Richtlinien Übereinstimmungen" besser für die Ermittlung von Übereinstimmungen mit bestimmten Regeln und für die Feinabstimmung von DLP-Richtlinien. Der Vorfall Bericht ist besser für die Identifizierung bestimmter Inhaltsteile, die für ihre DLP-Richtlinien problematisch sind.
    
- **DLP-falsch positive Ergebnisse und Außerkraftsetzungen** Wenn Ihre DLP-Richtlinie es Benutzern ermöglicht, Sie außer Kraft zu setzen oder ein falsch positives Ergebnis zu melden, zeigt dieser Bericht die Anzahl dieser Instanzen im Laufe der Zeit an. Sie können den Bericht nach Datum, Ort oder Richtlinie filtern. Sie können diesen Bericht für Folgendes verwenden: 
    
  - Optimieren oder optimieren Sie Ihre DLP-Richtlinien, indem Sie erkennen, welche Richtlinien eine hohe Anzahl falsch positiver Ergebnisse verursachen.
    
  - Zeigen Sie die von Benutzern übermittelten Begründungen an, wenn Sie einen richtlinientipp lösen, indem Sie die Richtlinie außer Kraft setzen.
    
  - Ermitteln, wo DLP-Richtlinien mit gültigen Geschäftsprozessen in Konflikt stehen, indem eine hohe Anzahl von Benutzerüberschreibungen entsteht.
    
Alle DLP-Berichte können Daten aus dem letzten Zeitraum von vier Monaten anzeigen. Die neuesten Daten können bis zu 24 Stunden in Anspruch nehmen, um in den Berichten angezeigt zu werden.
  
Diese Berichte finden Sie &amp; im **Dashboard**Security Compliance Center \> **Reports** \> .
  
![Bericht über DLP-Richtlinien Übereinstimmungen](media/117d20c9-d379-403f-ad68-1f5cd6c4e5cf.png)
  
## <a name="view-the-justification-submitted-by-a-user-for-an-override"></a>Anzeigen der von einem Benutzer übermittelten Begründung für eine Außerkraftsetzung

Wenn Ihre DLP-Richtlinie es Benutzern ermöglicht, Sie außer Kraft zu setzen, können Sie den Bericht "falsch positiv" und "außer Kraft setzen" verwenden, um den von Benutzern im richtlinientipp übermittelten Text anzuzeigen.
  
![Feld "Begründung" in Details des DLP-Berichts "falsch positiv" und "überschreiben"](media/e11e3126-026d-4e77-a16d-74a0686d1fa3.png)
  
## <a name="take-action-on-insights-and-recommendations"></a>Durchführen von Maßnahmen zu Einblicken und Empfehlungen

Berichte können Einblicke und Empfehlungen anzeigen, in denen Sie auf das rote Warnsymbol klicken können, um Details zu potenziellen Problemen anzuzeigen und mögliche Abhilfemaßnahmen zu ergreifen.
  
![Klicken auf ein Insights-Symbol, um Details und auszuführende Aktionen anzuzeigen](media/51782036-7299-4960-8175-75c2b1637159.png)
  
## <a name="permissions-for-dlp-reports"></a>Berechtigungen für DLP-Berichte

Um DLP-Berichte im Security #a0 Compliance Center anzuzeigen, müssen Sie folgendem zugewiesen sein:

- Rolle " **Sicherheits Leser** " im Exchange Admin Center. Diese Rolle wird standardmäßig der Rollengruppe Organisationsverwaltung und Sicherheits Leser in der Exchange-Verwaltungskonsole zugewiesen.

- **Verwaltungsrolle "DLP-Konformität anzeigen** " im Security #a0 Compliance Center. Diese Rolle wird standardmäßig den Rollengruppen Compliance-Administrator, Organisationsverwaltung, Sicherheitsadministrator und Sicherheits Leser im Security #a0 Compliance Center zugewiesen.

- Rolle " **View-Only Recipients** " im Exchange Admin Center. Diese Rolle wird standardmäßig der Verwaltungsrollengruppe "Compliance Management", "Organisationsverwaltung" und "nur anzeigen" im Exchange Admin Center zugewiesen.

## <a name="find-the-cmdlets-for-the-dlp-reports"></a>Suchen der Cmdlets für die DLP-Berichte

Zur Verwendung der meisten Cmdlets für das Security &amp; Compliance Center müssen Sie folgende Aktionen ausführen:
  
1. [Eine Verbindung zum Office 365 Security &amp; Compliance Center mithilfe von Remote-PowerShell herstellen](https://go.microsoft.com/fwlink/?LinkID=799771&amp;clcid=0x409)
    
2. Verwenden eines dieser [Office 365 Security &amp; Compliance Center-Cmdlets](https://go.microsoft.com/fwlink/?LinkID=799772&amp;clcid=0x409)
    
DLP-Berichte müssen jedoch Daten aus allen Office 365-Komponenten (einschließlich Exchange Online) abrufen. Aus diesem Grund sind die Cmdlets für die DLP-Berichte in Exchange Online PowerShell verfügbar – nicht in der &amp; Security Compliance Center-PowerShell. Zur Verwendung der Cmdlets für die DLP-Berichte müssen Sie daher folgende Aktionen ausführen:
  
1. [Stellen Sie eine Verbindung mit Exchange Online mithilfe der Remote-PowerShell her](https://go.microsoft.com/fwlink/?LinkID=799773&amp;clcid=0x409)
    
2. Verwenden Sie eines dieser Cmdlets für die DLP-Berichte:
    
      - [Get-DlpDetectionsReport](https://go.microsoft.com/fwlink/?LinkID=799774&amp;clcid=0x409)
    
      - [Get-DlpDetailReport](https://go.microsoft.com/fwlink/?LinkID=799775&amp;clcid=0x409)
    

