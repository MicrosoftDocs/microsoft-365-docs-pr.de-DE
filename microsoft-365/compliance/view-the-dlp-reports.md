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
ms.custom: seo-marvel-apr2020
description: Verwenden Sie die DLP-Berichte in Office 365, um die Anzahl der Übereinstimmungen, Außerkraftsetzungen oder falsch positiven Ergebnisse der DLP-Richtlinie zu sehen und festzustellen, ob sie im Laufe der Zeit nach oben oder unten zeigen.
ms.openlocfilehash: eb281f4d912a9e21716d7f9859564a02f9c23401
ms.sourcegitcommit: 355bd51ab6a79d5c36a4e4f57df74ae6873eba19
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/04/2021
ms.locfileid: "50423828"
---
# <a name="view-the-reports-for-data-loss-prevention"></a>Anzeigen der Berichtr zur Verhinderung von Datenverlust

Nachdem Sie Ihre Richtlinien zur Verhinderung von Datenverlust (Data Loss Prevention, DLP) erstellt haben, sollten Sie überprüfen, ob sie wie beabsichtigt funktionieren und Ihnen dabei helfen, konform zu bleiben. Mit den DLP-Berichten im Security &amp; Compliance Center können Sie schnell Dies anzeigen:
  
- **Übereinstimmungen mit der DLP-Richtlinie** Dieser Bericht zeigt die Anzahl der Übereinstimmungen von DLP-Richtlinien im Laufe der Zeit. Sie können den Bericht nach Datum, Speicherort, Richtlinie oder Aktion filtern. Sie können diesen Bericht für Folgendes verwenden: 
    
  - Sie können Ihre DLP-Richtlinien optimieren oder verfeinern, während Sie sie im Testmodus ausführen. Sie können die spezielle Regel, die mit dem Inhalt übereinstimmte, anzeigen.
    
  - Sie können sich auf bestimmte Zeiträume konzentrieren und so mehr über die Gründe für Spitzen und Trends erfahren.
    
  - Sie können die Geschäftsprozesse ermitteln, die gegen die DLP-Richtlinien Ihrer Organisation verstoßen.
    
  - Verstehen Sie alle geschäftlichen Auswirkungen der DLP-Richtlinien, indem Sie sehen, welche Aktionen auf Inhalte angewendet werden.
    
  - Sie können die Einhaltung einer bestimmten DLP-Richtlinie durch Anzeigen von Übereinstimmungen für diese Richtlinie überprüfen.
    
  - Sie können eine Liste der wichtigsten Benutzer und wiederholten Benutzer anzeigen, die zu Vorfällen in Ihrer Organisation beitragen.
    
  - Sie können eine Liste der wichtigsten Typen vertraulicher Informationen in Ihrer Organisation anzeigen.
    
- **DLP-Vorfälle** Dieser Bericht zeigt auch Übereinstimmungen mit Richtlinien im Laufe der Zeit an, z. B. den Bericht "Richtlinienüber übereinstimmungen". Der Bericht "Richtlinien übereinstimmungen" zeigt jedoch Übereinstimmungen auf Regelebene an. Wenn z. B. eine E-Mail drei verschiedenen Regeln entspricht, zeigt der Bericht Richtlinien übereinstimmungen drei unterschiedliche Zeilenelemente an. Im Gegensatz dazu zeigt der Bericht über Vorfälle Übereinstimmungen auf Elementebene an. Wenn z. B. eine E-Mail drei verschiedenen Regeln entsprechen sollte, zeigt der Bericht "Vorfälle" ein einzelnes Zeilenelement für diesen Inhalt an. 
    
  Da die Berichtsanzahl unterschiedlich aggregiert wird, ist der Bericht über Richtlinienabstimmungen besser zum Identifizieren von Übereinstimmungen mit bestimmten Regeln und zum Optimieren von DLP-Richtlinien. Der Bericht über Vorfälle ist besser zum Identifizieren bestimmter Inhaltsteile, die für Ihre DLP-Richtlinien problematisch sind.
    
- **Falsch positive Ergebnisse und Überschreibungen von DLP** Wenn Ihre DLP-Richtlinie Benutzern das Außerkraft setzen oder falsch positive Ergebnisse melden kann, zeigt dieser Bericht eine Anzahl solcher Instanzen im Laufe der Zeit an. Sie können den Bericht nach Datum, Speicherort oder Richtlinie filtern. Sie können diesen Bericht für Folgendes verwenden: 
    
  - Sie können Ihre DLP-Richtlinien optimieren oder verfeinern, indem Sie sehen, welche Richtlinien eine hohe Anzahl falsch positiver Ergebnisse verursachen.
    
  - Sie können die Begründungen anzeigen, die von Benutzern gesendet werden, wenn diese einen Richtlinientipp durch Außerkraftsetzen der Richtlinie lösen.
    
  - Sie können entdecken, wo DLP-Richtlinien mit gültigen Geschäftsprozessen in Konflikt stehen, wenn Sie eine hohe Anzahl von Außerkraftsetzungen durch Benutzer verzeichnen.
    
Alle DLP-Berichte können Daten aus dem letzten Zeitraum von vier Monaten anzeigen. Es kann bis zu 24 Stunden dauern, bis die aktuellsten Daten in den Berichten angezeigt werden.
  
Diese Berichte finden Sie im Security &amp; Compliance Center \> **Reports** \> **Dashboard**.
  
![Bericht über Übereinstimmungen mit DLP-Richtlinien](../media/117d20c9-d379-403f-ad68-1f5cd6c4e5cf.png)
  
## <a name="view-the-justification-submitted-by-a-user-for-an-override"></a>Anzeigen der von einem Benutzer für eine Außerkraftsetzung übermittelten Begründung

Wenn Ihre DLP-Richtlinie Benutzern die Außerkraftsetzung ermöglicht, können Sie den Bericht "Falsch positiv" und "Außerkraftsetzung" verwenden, um den von Benutzern übermittelten Text in der Richtlinieninfo zu sehen.
  
![Feld "Begründung" im Detail des Berichts "Falsch positiv" und "Außerkraftsetzung" der DLP](../media/e11e3126-026d-4e77-a16d-74a0686d1fa3.png)
  
## <a name="take-action-on-insights-and-recommendations"></a>Ergreifen von Maßnahmen zu Erkenntnissen und Empfehlungen

Berichte können Einblicke und Empfehlungen anzeigen, in denen Sie auf das rote Warnsymbol klicken können, um Details zu potenziellen Problemen anzuzeigen und mögliche Abhilfemaßnahmen zu ergreifen.
  
![Klicken auf ein Einblickesymbol, um Details und Aktionen anzuzeigen](../media/51782036-7299-4960-8175-75c2b1637159.png)
  
## <a name="permissions-for-dlp-reports"></a>Berechtigungen für DLP-Berichte

Zum Anzeigen von DLP-Berichten im Security & Compliance Center müssen Ihnen die:

- **Rolle "Security Reader"** im Exchange Admin Center. Diese Rolle wird standardmäßig den Rollengruppen Organisationsverwaltung und Sicherheitsleseprogramm im Exchange Admin Center zugewiesen.

- **View-Only DLP Compliance Management role** in the Security & Compliance Center. Diese Rolle wird standardmäßig den Rollengruppen Complianceadministrator, Organisationsverwaltung, Sicherheitsadministrator und Sicherheitsleseprogramm im Security & Compliance Center zugewiesen.

- **Rolle "Nur Anzeigen von Empfängern"** im Exchange Admin Center. Standardmäßig ist diese Rolle den Rollengruppen Complianceverwaltung, Organisationsverwaltung und View-Only Organisationsverwaltung im Exchange Admin Center zugewiesen.

## <a name="find-the-cmdlets-for-the-dlp-reports"></a>Suchen der Cmdlets für die DLP-Berichte

Zur Verwendung der meisten Cmdlets für das Security &amp; Compliance Center müssen Sie folgende Aktionen ausführen:
  
1. [Herstellen einer Verbindung mit dem Security &amp; Compliance Center mithilfe der Remote-PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell&amp;clcid=0x409)
    
2. Verwenden eines dieser [Security &amp; Compliance Center-Cmdlets](https://go.microsoft.com/fwlink/?LinkID=799772&amp;clcid=0x409)
    
DLP-Berichte müssen jedoch Daten aus allen Office 365-Komponenten (einschließlich Exchange Online) abrufen. Aus diesem Grund sind die Cmdlets für die DLP-Berichte in Exchange Online Powershell verfügbar, nicht in Security &amp; Compliance Center Powershell. Zur Verwendung der Cmdlets für die DLP-Berichte müssen Sie daher folgende Aktionen ausführen:
  
1. [Stellen Sie eine Verbindung mit Exchange Online mithilfe der Remote-PowerShell her](https://go.microsoft.com/fwlink/?LinkID=799773&amp;clcid=0x409)
    
2. Verwenden Sie eines dieser Cmdlets für die DLP-Berichte:
    
      - [Get-DlpDetectionsReport](https://go.microsoft.com/fwlink/?LinkID=799774&amp;clcid=0x409)
    
      - [Get-DlpDetailReport](https://go.microsoft.com/fwlink/?LinkID=799775&amp;clcid=0x409)
    

