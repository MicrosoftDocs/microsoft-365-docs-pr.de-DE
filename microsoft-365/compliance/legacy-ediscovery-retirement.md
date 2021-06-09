---
title: Einstellung älterer eDiscovery-Tools
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection: M365-security-compliance
description: In-Place eDiscovery und In-Place Hold (und die entsprechenden PowerShell-Cmdlets) in Exchange Online werden in der ersten Hälfte des Jahres 2020 eingestellt. Das Cmdlet Search-Mailbox und Advanced eDiscovery Version 1.0 werden ebenfalls innerhalb desselben Zeitraums eingestellt.
ms.openlocfilehash: c5f1ddb4c817ebc316c2e2efdba9a4bc605eb5a2
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2021
ms.locfileid: "52842662"
---
# <a name="retirement-of-legacy-ediscovery-tools"></a>Einstellung älterer eDiscovery-Tools

> [!IMPORTANT]
> Microsoft hat die Situation im öffentlichen Gesundheitswesen ausgewertet, und wir wissen, welche Auswirkungen dies auf unsere Kunden hat. Wir möchten starke Partner und verantwortliche Globale Bürger sein. Um eine der vielen Belastungen zu verringern, mit denen Sie konfrontiert sind, werden wir die geplante Einstellung für die in diesem Artikel beschriebenen eDiscovery-Tools der Vorversion um drei Monate verzögern. **Die aktualisierten Einstellungstermine sind unten dargestellt.**

Im Laufe der Jahre hat Microsoft eDiscovery-Tools bereitgestellt, mit denen Sie E-Mail-Inhalte aus Exchange Online suchen, in der Vorschau anzeigen und exportieren können. Diese Tools bieten jedoch keine effektive Möglichkeit mehr, in anderen Microsoft 365 Diensten, z. B. SharePoint Online- und Microsoft 365-Gruppen, nach nicht Exchange Inhalten zu suchen. Um dies zu beheben, bietet Microsoft weitere eDiscovery-Tools, die Ihnen bei der Suche nach einer Vielzahl von Microsoft 365 Inhalten helfen. Und wir haben hart daran gearbeitet, die aktuellsten und leistungsstärksten eDiscovery-Funktionen in das [Microsoft 365 Compliance Center](https://compliance.microsoft.com)zu integrieren. Auf diese Weise können Organisationen auf rechtliche, interne und andere Dokumentanforderungen für Inhalte in vielen Microsoft 365 Diensten, einschließlich Exchange Online, reagieren.

Aufgrund dieser neuen und verbesserten eDiscovery-Funktionalität im Microsoft 365 Compliance Center werden die folgenden eDiscovery-bezogenen Features und Funktionen im Zusammenhang mit der Suche nach E-Mail-Inhalten in Exchange Online und Microsoft 365 entfernt:

- [In-Situ-eDiscovery](/exchange/security-and-compliance/in-place-ediscovery/in-place-ediscovery) und [In-Situ-Speicher](/exchange/security-and-compliance/create-or-remove-in-place-holds) im Exchange Admin Center.

- Die Exchange Online PowerShell-Cmdlets, die In-Place eDiscovery- und In-Place-Haltebereiche unterstützen (diese Cmdlets werden gemeinsam als **-MailboxSearch-Cmdlets* identifiziert). Dazu gehören die folgenden Cmdlets:

  - [New-MailboxSearch](/powershell/module/exchange/new-mailboxsearch)

  - [Start-MailboxSearch](/powershell/module/exchange/start-mailboxsearch)

  - [Stop-MailboxSearch](/powershell/module/exchange/stop-mailboxsearch)

  - [Set-MailboxSearch](/powershell/module/exchange/set-mailboxsearch)

   > [!NOTE]
   > The [Get-MailboxSearch](/powershell/module/exchange/get-mailboxsearch) and [Remove-MailboxSearch](/powershell/module/exchange/remove-mailboxsearch) cmdlets will be available after the other "-MailboxSearch" cmdlets are retired so that you can use them to help in your transition to other eDiscovery and hold tools. Nach einem bestimmten Datum (siehe unten) unterstützt der Microsoft-Support diese beiden Cmdlets jedoch nicht mehr.

- Das Cmdlet ["Search-Mailbox"](/powershell/module/exchange/search-mailbox) in Exchange Online PowerShell.

- Die folgenden Vorgänge in der Exchange-Webdienst-API:

   - [GetSearchableMailboxes](/exchange/client-developer/web-service-reference/getsearchablemailboxes-operation)

   - [SearchMailboxes](/exchange/client-developer/web-service-reference/searchmailboxes-operation)
   
   - [SetHoldOnMailboxes](/exchange/client-developer/web-service-reference/setholdonmailboxes-operation)

   - [GetHoldOnMailboxes](/exchange/client-developer/web-service-reference/getholdonmailboxes-operation)

- [Office 365 Advanced eDiscovery v1.0](./overview-ediscovery-20.md), die erste Version von Advanced eDiscovery, auf die über einen Core eDiscovery-Fall im Office 365 Security & Compliance Center zugegriffen wird. Die Einstellung von Advanced eDiscovery v1.0 wirkt sich nicht auf Ihre Fähigkeit aus, Core eDiscovery-Fälle zu erstellen und zu verwalten.

> [!NOTE]
> Die eDiscovery-Funktion, die eingestellt wird, gilt nur für cloudbasierte Versionen von Microsoft 365 und Office 365. eDiscovery-Funktionen in lokalen Versionen von Exchange und SharePoint werden bis auf weiteres weiterhin unterstützt.

Die folgenden Abschnitte in diesem Artikel enthalten Anleitungen zu den einzelnen Funktionen, die eingestellt werden. Diese Informationen enthalten Zeitachsen und alternative Tools, die Sie anstelle des veralteten Tools verwenden können.

## <a name="in-place-ediscovery-and-in-place-holds-in-the-exchange-admin-center"></a>In-Place eDiscovery und In-Place Haltebereiche im Exchange Admin Center 

Gemäß der ursprünglichen Ankündigung vom 1. Juli 2017 wird die In-Place eDiscovery & Hold-Funktion im Exchange Admin Center (EAC) eingestellt. Auf der Seite "In-Place eDiscovery & Holds" im EAC können Sie Inhalte aus Exchange Online suchen, aufbewahren und exportieren. In-Place eDiscovery können Sie auch Suchergebnisse in ein Discoverypostfach kopieren, damit Sie oder andere eDiscovery-Manager Inhalte überprüfen und für rechtliche, behördliche und öffentliche Anforderungen verfügbar machen können.

Da alle diese Funktionen (mit Ausnahme des Kopierens von Suchergebnissen in ein Discoverypostfach) jetzt in der Inhaltssuche, eDiscovery und Advanced eDiscovery Tools im [Microsoft 365 Compliance Center](./microsoft-365-compliance-center.md) (mit verbesserter Funktionalität, Zuverlässigkeit und Unterstützung für eine Vielzahl von Microsoft 365 Diensten) verfügbar sind, empfehlen wir, diese Tools so schnell wie möglich zu verwenden. Um Sie beim Übergang zu diesen anderen eDiscovery-Tools zu unterstützen, sind in der folgenden Tabelle die Tools aufgeführt, die Sie anstelle von In-Place eDiscovery und In-Place Hold verwenden können.

### <a name="scope-of-affected-organizations"></a>Umfang der betroffenen Organisationen

- Office 365 und Microsoft 365 Enterprise Organisationen

- Office 365 und Microsoft 365 Education Organisationen

- Office 365 und Microsoft 365 Behörden; dazu gehören GCC, GCC Hoch und DoD.

- Office 365 Deutschland

### <a name="timeline-for-retirement"></a>Zeitachse für die Ausmusterung

- 1. Juli 2020: Sie können keine neuen Suchvorgänge und Haltebereiche erstellen, aber Sie können vorhandene Suchvorgänge weiterhin auf eigenes Risiko ausführen, bearbeiten und löschen. Der Microsoft-Support In-Place eDiscovery-&-Haltebereiche im EAC nicht mehr.

- 1. Oktober 2020: Die Funktion "In-Place eDiscovery & Holds" im EAC wird in den schreibgeschützten Modus versetzt. Dies bedeutet, dass Sie nur vorhandene Suchen und Haltebereiche entfernen können.

### <a name="alternative-tools"></a>Alternative Tools

In der folgenden Tabelle werden andere Tools beschrieben, die Sie verwenden können, um die vorhandene Funktion zu ersetzen, die eingestellt wird.

<table>
<thead>
<tr class="header">
<th>Funktionalität</th>
<th>Alternatives Tool</th>
<th>Kommentare</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Suchen, Exportieren und Aufbewahren zu rechtlichen Zwecken</td>
<td>Core eDiscovery-Fälle im Microsoft 365 Compliance Center </td>
<td><p>Die Verwendung der Funktionen von eDiscovery-Kernfällen stellt die funktionale Parität In-Place eDiscovery- und In-Place-Haltebereiche bereit. Dazu gehört Folgendes:</p>
<ul>
<li>
<p>Suchskalierungen auf Millionen von Standorten</p>
</li>
<li>
<p>Höhere Zuverlässigkeit beim Suchen, Exportieren und Platzieren von Inhalten im Haltebereich</p>
</li>
<li>
<p>Suchen nach Inhalten für Exchange Online, SharePoint Online, OneDrive for Business, Skype for Business, Microsoft Teams, Yammer Gruppen, Microsoft 365 Gruppen und andere Inhalte, die in Office 365 Anwendungen gespeichert sind</p></li></ul>
</td>
</tr>
<tr class="even">
<td>Zu Aufbewahrungszwecken aufbewahren</td>
<td>Aufbewahrungsrichtlinien im Microsoft 365 Compliance Center</td>
<td><p>Sie können Aufbewahrungsrichtlinien verwenden, um Inhalte aufzubewahren und, falls gewünscht, nach Ablauf des Aufbewahrungszeitraums zu löschen. Weitere Funktionen sind:</p>
<ul>
<li>
<p>Anwenden von Richtlinien auf Ihre gesamte Organisation </p>
</li><li>
<p>Anwenden von Richtlinien auf bestimmte Inhaltsspeicherorte wie Exchange Online, SharePoint Online, OneDrive for Business, Skype for Business, Microsoft Teams und Office 365 Gruppen</p></li>
<li>
<p>Anwenden von Richtlinien auf bestimmte Benutzer</p></li></ul>
<p>Weitere Informationen finden Sie unter <a href="/microsoft-365/compliance/retention-policies">Informationen zu Aufbewahrungsrichtlinien und Aufbewahrungsbezeichnungen.</a></td>
</tr>
<tr class="odd">
<td>Kopieren von E-Mail-Suchergebnissen in ein Ermittlungspostfach zur Überprüfung</td><td>Prüfdateisätze in Advanced eDiscovery v2.0</td>
<td><p>Das Überprüfen von Inhalten in Microsoft 365 war noch nie einfacher. Prüfdateisätze verfügen über viele großartige Funktionen, um den Zeit- und Datenaufwand für die Überprüfung zu reduzieren, einschließlich:</p>
<ul>
<li><p>Durchführen schneller Suchabfragen und Filtern von Inhalten in einem Prüfdateisatz</p></li>
<li><p>Analysieren von Inhalten in einem Prüfdateisatz; dazu gehören E-Mail-Threading, Erkennung nahezu doppelter Elemente, Designanalyse und Vorhersagecodierung.</p></li>
<li><p>Markieren von Dokumenten in einem Prüfdateisatz</p></li>
<li><p>Taggingvorschläge zur Identifizierung von Anwaltsgeheimnissen</p></li></ul>
<p>Weitere Informationen finden Sie unter <a href="/microsoft-365/compliance/overview-ediscovery-20">Übersicht über die Advanced eDiscovery-Lösung in Microsoft 365</a>.</p>
<p>
<p>Alternativ können Sie Suchergebnisse in PST-Dateien exportieren und dann Microsoft 365 Importdienst verwenden, um die PSTs in ein Ermittlungspostfach zu importieren. Eine schrittweise Anleitung finden Sie unter <a href="/microsoft-365/compliance/use-network-upload-to-import-pst-files">Verwenden des Netzwerkuploads zum Importieren von PST-Dateien in Office 365.</a>
</tr>
<tr class=even>
  <td>Kopieren von Nachrichten aus einem Postfach in ein anderes Postfach</td>
  <td><a href="/exchange/recipients-in-exchange-online/manage-permissions-for-recipients">Zuweisen von Berechtigungen zu einem Postfach</a></td>
  <td>Um einer Person Zugriff auf die E-Mails eines anderen Benutzers zu gewähren (z. B. wenn ein Mitarbeiter Ihre Organisation verlässt und Sie einer anderen Person Zugriff auf die E-Mails des ehemaligen Mitarbeiters gewähren müssen), empfehlen wir, dass Sie dieser Person Berechtigungen zuweisen, um auf das Postfach des ehemaligen Mitarbeiters zuzugreifen. Anstatt Postfachelemente in ein anderes Benutzerpostfach oder ein freigegebenes Postfach zu kopieren, weisen Sie einfach eine Benutzerberechtigung für den Zugriff auf das Quellpostfach zu.</td>
  
  </tr>
<tr class="odd">
<td>Wiederherstellen von Elementen aus dem Ordner "Wiederherstellbare Elemente"</td>
  <td><a href="/powershell/module/exchange/Restore-RecoverableItems">Restore-RecoverableItems</td>
  <td>Sie können dauerhaft gelöschte Elemente (auch als <i>vorläufig gelöschte</i> Elemente bezeichnet) in Postfächern wiederherstellen, solange der Aufbewahrungszeitraum für gelöschte Elemente für ein Element nicht abgelaufen ist. Weitere Informationen finden Sie im <a href="/Exchange/security-and-compliance/recoverable-items-folder/recoverable-items-folder">Ordner "Wiederherstellbare Elemente" in Exchange Online.</a></td>
</tr>
</tbody>
</table>

### <a name="faqs-about-in-place-ediscovery-and-in-place-holds"></a>Häufig gestellte Fragen zu In-Place eDiscovery und In-Place-Haltebereichen

**Ich verwende die Funktion zum Kopieren von Suchergebnissen von In-Place eDiscovery & Haltebereiche im EAC, um Suchergebnisse zur Überprüfung durch Anwälte in ein Suchpostfach zu kopieren. Welche Optionen habe ich jetzt?**

Es gibt heute zwei Möglichkeiten, diese Funktionalität zu replizieren. Die erste besteht [darin, Prüfdateisätze in Advanced eDiscovery Version 2.0](./view-documents-in-review-set.md)zu verwenden. Prüfdateisätze verfügen über viele der gleichen Funktionen, die Sie in einem herkömmlichen Überprüfungstool sehen, z. B. schnelle Suche nach Dokumenten, Tagging, E-Mail-Threading, nahezu doppelte Gruppierung, Designanalyse und Vorhersagecodierung. Wenn Sie weiterhin Ermittlungspostfächer zur Überprüfung verwenden möchten, besteht die zweite Option darin, Suchergebnisse in PST-Dateien zu exportieren und dann die PST-Dateien mithilfe der [PST-Importfunktion](use-network-upload-to-import-pst-files.md) im Microsoft Compliance Center in ein Ermittlungspostfach zu importieren.

**Wie kann ich steuern, welche Inhaltsspeicherorte (z. B. Postfächer oder Websites), die ein eDiscovery-Manager mithilfe der neuen Tools durchsuchen kann?**

Das Microsoft 365 Compliance Center verwendet auch [Compliance-Grenzen,](set-up-compliance-boundaries.md) um zu steuern, welche Inhaltsspeicherorte ein eDiscovery-Manager durchsuchen kann. Compliance-Begrenzungen eignen sich für Behörden, die innerhalb der Agenturgrenzen bleiben müssen, oder multinationale Unternehmen, die geografisch kontrolliere berücksichtigen müssen.

**Wie kann ich meine aktuellen Suchvorgänge und Haltebereiche in das Microsoft 365 Compliance Center verschieben?**

Es ist möglich, In-Place eDiscovery-Suchvorgänge und -haltebereiche aus dem EAC mithilfe von PowerShell zu migrieren. Anweisungen finden Sie unter [Migrieren von Suchvorgängen und Haltebereichen vom EAC zum Microsoft 365 Compliance Center.](./migrate-legacy-ediscovery-searches-and-holds.md)

## <a name="-mailboxsearch-cmdlets"></a>\*-MailboxSearch-Cmdlets

Gemäß der ursprünglichen Benachrichtigung vom 1. Juli 2017 im Exchange Admin Center werden die In-Place eDiscovery & Hold-Funktion und die entsprechenden **\* -MailboxSearch-Cmdlets** eingestellt. Diese Cmdlets bieten Benutzern die Möglichkeit, Postfachinhalte für rechtliche, behördliche und öffentliche Anforderungen zu durchsuchen, aufzubewahren und zu exportieren.

Da diese Funktionen jetzt im [<span class="underline">Microsoft 365 Compliance Center</span>](./microsoft-365-compliance-center.md) und Office 365 Security & Compliance Center PowerShell mit verbesserter Leistung und Skalierbarkeit verfügbar sind, sollten Sie diese verbesserten Cmdlets verwenden. Zu diesen Cmdlets gehören [<span class="underline"> \* "-ComplianceCase",</span>](/powershell/module/exchange/get-compliancecase) [<span class="underline"> \* "-ComplianceSearch",</span>](/powershell/module/exchange/get-compliancesearch) [<span class="underline"> \* "-CaseHoldPolicy",</span>](/powershell/module/exchange/get-caseholdpolicy) [<span class="underline"> \* "-CaseHoldRule"</span>](/powershell/module/exchange/get-caseholdrule)und [<span class="underline"> \* "-ComplianceSearchAction".</span>](/powershell/module/exchange/get-compliancesearchaction)

### <a name="scope-of-affected-organizations"></a>Umfang der betroffenen Organisationen

- Office 365 und Microsoft 365 Enterprise Organisationen

- Office 365 und Microsoft 365 Education Organisationen

- Office 365 und Microsoft 365 Behörden; dazu gehören GCC, GCC Hoch und DoD.

- Office 365 Deutschland

### <a name="timeline"></a>Zeitachse

- 1. Juli 2020: Sie können **New-MailboxSearch** nicht verwenden, um neue In-Place eDiscovery-Suchvorgänge und In-Place Haltebereiche zu erstellen. Sie können jedoch weiterhin Cmdlets verwenden, um vorhandene Suchen und Haltebereiche auf eigenes Risiko auszuführen, zu bearbeiten und zu löschen. Der Microsoft-Support bietet keine Unterstützung mehr für diese Such- und Haltebereiche.

- 1. Oktober 2020: Wie bereits erwähnt, wird die Funktion "In-Place eDiscovery & Holds" im EAC in einen schreibgeschützten Modus versetzt. Das bedeutet auch, dass Sie die Cmdlets **New-MailboxSearch,** **Start-MailboxSearch** oder **Set-MailboxSearch** nicht verwenden können. Sie können nur vorhandene Suchen und Haltebereiche abrufen und entfernen.

### <a name="alternative-tools"></a>Alternative Tools

In der folgenden Tabelle werden andere Tools beschrieben, die Sie verwenden können, um die vorhandene Funktion zu ersetzen, die eingestellt wird.

<table>
<thead>
<tr class="header">
<th>Funktionalität</th>
<th>Alternative Tools</th>
<th>Kommentare</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Suchen und Exportieren</td>
<td><p><a href="/powershell/module/exchange/get-compliancesearch"><span class="underline">*-ComplianceSearch</span></a></p>
<p><a href="/powershell/module/exchange/get-compliancesearchaction"><span class="underline">*-ComplianceSearchAction</span></a></p>
<p><a href="/powershell/module/exchange/get-compliancecase"><span class="underline">*-ComplianceCase</span></a></p>
<p> </p></td>
<td><p>Die Cmdlets "ComplianceSearch" und "ComplianceSearchAction" helfen Ihnen beim Suchen und Exportieren von Inhalten. Sie können eine neue Suche erstellen und die Suchvorkalkulation anzeigen, indem Sie die Cmdlets <strong>New-</strong>, <strong>Get-</strong>und <strong>Start-ComplianceSearch</strong> verwenden. Anschließend können Sie das Cmdlet <strong>"New-ComplianceSearchAction"</strong> verwenden, um die Suchergebnisse zu exportieren. Sie müssen weiterhin das eDiscovery-Kerntool im Microsoft 365 Compliance Center verwenden, um diese Suchergebnisse auf Ihren lokalen Computer herunterzuladen.</p>
<p>
<p><strong>Hinweis:</strong> Wenn Sie diese Cmdlets verwenden, um Suchen zu erstellen, die keinem eDiscovery-Kernfall zugeordnet sind, befinden sich diese Suchen auf der Seite <strong>"Inhaltssuche"</strong> im Microsoft 365 Compliance Center.</p></td>
</tr>
<tr class="even">
<td>Speichern von Inhalten in einem Postfach</td>
<td><p><a href="/powershell/module/exchange/get-caseholdpolicy"><span class="underline">*-CaseHoldPolicy</span></a></p>
<p><a href="/powershell/module/exchange/get-caseholdrule"><span class="underline">*-CaseHoldRule</span></a></p>
<p><a href="/powershell/module/exchange/get-compliancecase"><span class="underline">*-ComplianceCase</span></a></p>
<p> </p></td>
<td><p>Haltebereiche im Microsoft 365 Compliance Center müssen einem ComplianceCase zugeordnet sein. Erstellen Sie zuerst den Compliancefall und dann eine CaseHoldPolicy und eine CaseHoldRule.</p>
<p><strong>Hinweis:</strong> Das Erstellen einer CaseHoldPolicy ohne das Erstellen von CaseHoldRule rendert den Haltebereich, bis CaseHoldRule erstellt und der CaseHoldPolicy zugeordnet wird. Weitere Informationen finden Sie in der Cmdlet-Dokumentation.</p></td>
</tr>
<tr class="odd">
<td>Kopieren von Suchergebnissen in ein Ermittlungspostfach</td>
<td>Keine</td>
<td>Es gibt keinen direkten Ersatz für diese Funktion, da sie nicht zugriff auf alle Microsoft 365-Dienste bietet. Alternative Lösungen finden Sie in den folgenden häufig gestellten Fragen.</td>
</tr>
  <tr class=even>
  <td>Kopieren von Nachrichten aus einem Postfach in ein anderes Postfach</td>
  <td><a href="/exchange/recipients-in-exchange-online/manage-permissions-for-recipients">Zuweisen von Berechtigungen zu einem Postfach</a></td>
  <td>Um einer Person Zugriff auf die E-Mails eines anderen Benutzers zu gewähren (z. B. wenn ein Mitarbeiter Ihre Organisation verlässt und Sie einer anderen Person Zugriff auf die E-Mails des ehemaligen Mitarbeiters gewähren müssen), empfehlen wir, dass Sie dieser Person Berechtigungen zuweisen, um auf das Postfach des ehemaligen Mitarbeiters zuzugreifen. Anstatt Postfachelemente in ein anderes Benutzerpostfach oder ein freigegebenes Postfach zu kopieren, weisen Sie einfach eine Benutzerberechtigung für den Zugriff auf das Quellpostfach zu.</td>
  
  </tr>

</tbody>
</table>

### <a name="faqs-about--mailboxsearch-cmdlets"></a>Häufig gestellte Fragen zu ***-MailboxSearch-Cmdlets**

**Wir verwenden die Kopiersuche, um E-Mail-Nachrichten oder Chatnachrichten für andere eDiscovery- und rechtliche Untersuchungen zu exportieren. Welche weiteren Optionen haben wir, nachdem diese Cmdlets eingestellt wurden?**

Die [<span class="underline">Microsoft Graph-APIs</span>](https://developer.microsoft.com/en-us/graph) bieten eine Reihe von Methoden zum Extrahieren von Daten für Analysen und andere Zwecke, die wesentlich stabiler und skalierbarer sind als die Verwendung der **\* -MailboxSearch-Cmdlets.**

**Wie kann ich meine Suchvorgänge und Haltebereiche zum Microsoft 365 Compliance Center migrieren?**

Es ist möglich, In-Place eDiscovery-Suchvorgänge und -haltebereiche aus dem Exchange Admin Center mithilfe eines PowerShell-Skripts zu migrieren. Weitere Informationen finden Sie unter [Migrieren von eDiscovery-Legacysuchen und -haltebereichen zum Microsoft 365 Compliance Center.](migrate-legacy-eDiscovery-searches-and-holds.md)

**Kann ich nach dem Zurückziehen der Cmdlets weiterhin Suchvorgänge entfernen oder abrufen?**

Ja, obwohl wir die Möglichkeit zum Erstellen und Ändern von Suchvorgängen entfernen, können Sie **get-MailboxSearch** und **Remove-MailboxSearch** bis auf weiteres verwenden. Die Verwendung dieser Cmdlets erfolgt jedoch auf eigenes Risiko nach dem Einstellungsdatum, und der Microsoft-Support kann keine Unterstützung mehr bereitstellen.

## <a name="search-mailbox-cmdlet"></a>cmdlet Search-Mailbox

Das Cmdlet **"Search-Mailbox"** in Exchange Online PowerShell wird wie ursprünglich in einer Warnung in der Cmdlet-Ausgabe ab 2018 angekündigt eingestellt. Das Cmdlet **"Search-Mailbox"** wurde ursprünglich verwendet, um das Postfach eines Benutzers zu durchsuchen und schädliche Inhalte zu löschen. Es wird empfohlen, die Cmdlets **New-ComplianceSearch** und **New-ComplianceSearchAction** in Office 365 Security & Compliance Center PowerShell zu verwenden, um nach Inhalten zu suchen und diese zu löschen. Für eine integrierte Sicherheitsumgebung bieten die [<span class="underline">Microsoft 365 Sicherheitsfeatures</span>](../security/index.yml) einen robusten Bedrohungsschutz für E-Mails und viele andere Microsoft-Dienste.

### <a name="scope-of-affected-organizations"></a>Umfang der betroffenen Organisationen

- Office 365 und Microsoft 365 Enterprise Organisationen

- Office 365 und Microsoft 365 Education Organisationen

- Office 365 und Microsoft 365 Behörden; dazu gehören GCC, GCC Hoch und DoD.

- Office 365 Deutschland

### <a name="timeline"></a>Zeitachse

-  1. Juli 2020: Das Cmdlet **"Search-Mailbox"** ist nicht mehr verfügbar, und der Microsoft-Support bietet keine Unterstützung mehr.

### <a name="alternative-tools"></a>Alternative Tools

In der folgenden Tabelle werden andere Tools beschrieben, die Sie verwenden können, um die vorhandene Funktion zu ersetzen, die eingestellt wird.

<table>
<thead>
<tr class="header">
<th>Funktionalität</th>
<th>Alternative Tools</th>
<th>Kommentare</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Durchsuchen eines Postfachs</td>
<td><p><a href="/powershell/module/exchange/get-compliancesearch"><span class="underline">*-ComplianceSearch</span></a></p>
<p><a href="/powershell/module/exchange/get-compliancesearchaction"><span class="underline">*-ComplianceSearchAction</span></a></p>
<p></a></p></td>
<td><p>Die Cmdlets "ComplianceSearch" und "ComplianceSearchAction" helfen Ihnen beim Suchen und Exportieren von Inhalten. Sie können eine neue Suche erstellen und die Suchvorkalkulation anzeigen, indem Sie die Cmdlets <strong>New-</strong>, <strong>Get-</strong>und <strong>Start-ComplianceSearch</strong> verwenden. Anschließend können Sie den Befehl <strong>"New-ComplianceSearchAction -Export"</strong> verwenden, um die Suchergebnisse zu exportieren. Sie müssen weiterhin das eDiscovery-Kerntool im Microsoft 365 Compliance Center verwenden, um diese Suchergebnisse auf Ihren lokalen Computer herunterzuladen.</p></p>
</td>
</tr>
<tr class="even">
<td>Massenlöschen von E-Mails aus einem Postfach</td>
<td><p><a href="/microsoft-365/compliance/set-up-an-archive-and-deletion-policy-for-mailboxes?view=o365-worldwide"><span class="underline">Einrichten einer Richtlinie zum Archivieren und Löschen für Postfächer</span></a></p>
<p></p></td>
<td><p>Administratoren können eine Archivierungs- und Löschrichtlinie erstellen, die Elemente automatisch in das Archivpostfach eines Benutzers verschiebt und Elemente automatisch aus dem Postfach löscht.</p>
</td>
</tr>
<tr class="even">
<td>Kopieren von Suchergebnissen in ein Ermittlungspostfach</td>
<td> </td>
<td>Es gibt keinen direkten Ersatz für diese Funktion, da sie nicht zugriff auf alle Microsoft 365-Dienste bietet. Alternative Lösungen finden Sie in den häufig gestellten Fragen im Abschnitt <strong>"*-MailboxSearch"-Cmdlets.</strong> </td>
</tr>
<tr class=odd>
  <td>Kopieren von Nachrichten aus einem Postfach in ein anderes Postfach</td>
  <td><a href="/exchange/recipients-in-exchange-online/manage-permissions-for-recipients">Zuweisen von Berechtigungen zu einem Postfach</a></td>
  <td>Um einer Person Zugriff auf die E-Mails eines anderen Benutzers zu gewähren (z. B. wenn ein Mitarbeiter Ihre Organisation verlässt und Sie einer anderen Person Zugriff auf die E-Mails des ehemaligen Mitarbeiters gewähren müssen), empfehlen wir, dass Sie dieser Person Berechtigungen zuweisen, um auf das Postfach des ehemaligen Mitarbeiters zuzugreifen. Anstatt Postfachelemente in ein anderes Benutzerpostfach oder ein freigegebenes Postfach zu kopieren, weisen Sie einfach eine Benutzerberechtigung für den Zugriff auf das Quellpostfach zu.</td>
</tr>
<tr class=even>
  <td>Löschen von Nachrichten aus einem Postfach</td>
<td><p><a href="/powershell/module/exchange/get-compliancesearch"><span class="underline">*-ComplianceSearch</span></a></p>
<p><a href="/powershell/module/exchange/get-compliancesearchaction"><span class="underline">*-ComplianceSearchAction</span></a></p>
<p></p></td>
<td><p>Die Cmdlets "ComplianceSearch" und "ComplianceSearchAction" helfen Ihnen bei der Suche und Bereinigung von Inhalten. Sie können eine Suche mit <strong>New-ComplianceSearch-</strong> und <strong>New-ComplianceSearch-Cmdlets</strong> erstellen und ausführen und dann den Inhalt mit dem Befehl <strong>"New-ComplianceSearchAction -Purge -PurgeType"</strong> löschen. Weitere Informationen finden Sie unter <a href="/microsoft-365/compliance/search-for-and-delete-messages-in-your-organization"><span class="underline">Suchen nach und Löschen von Nachrichten.</span></a></p>
</td>
</tr>
<tr class="odd"> 
<td>Löschen von Nachrichten aus einem Postfach</td>
<td><a href="/exchange/recipients-in-exchange-online/manage-permissions-for-recipients">Zuweisen von Berechtigungen zu einem Postfach</a></td>
<td>Um Nachrichten aus einem Postfach zu löschen, weisen Sie einem Administrator Berechtigungen für den Zugriff auf das Postfach des Mitarbeiters zu. Nachrichten können bei Bedarf gelöscht und wiederverwendet werden, indem die integrierten Such- und Anzeigefunktionen in Outlook genutzt werden.</td>
</tr>
</tbody>
</table>

## <a name="exchange-web-services-api-operations"></a>Exchange Webdienst-API-Vorgänge

Diese Vorgänge in der Exchange Webdienst-API werden von der Funktion "In-Place eDiscovery & Haltebereiche" im Exchange Admin Center und den entsprechenden Cmdlets **\* "-MailboxSearch"** in Exchange Online PowerShell verwendet. Sie werden auch im Rahmen der Einstellung der anderen eDiscovery-Tools der Vorversion eingestellt.

### <a name="scope-of-affected-organizations"></a>Umfang der betroffenen Organisationen

- Office 365 und Microsoft 365 Enterprise Organisationen

- Office 365 und Microsoft 365 Education Organisationen

- Office 365 und Microsoft 365 Behörden; dazu gehören GCC, GCC High und DoD

- Office 365 Deutschland

### <a name="timeline"></a>Zeitachse

- 1. Juli 2020: Die Vorgänge "GetSearchableMailboxes", "SearchMailboxes", "SetHoldOnMailboxes" und "GetHoldOnMailboxes" sind nicht mehr verfügbar, und der Microsoft-Support bietet keine Unterstützung mehr.

## <a name="advanced-ediscovery-v10"></a>Advanced eDiscovery v1.0

Advanced eDiscovery Version 1.0, bei der es sich um die Version von Advanced eDiscovery handelt, die in einem eDiscovery-Kernfall durch Klicken auf **"Zu Advanced eDiscovery wechseln"** verfügbar ist, wird eingestellt. Die Funktionalität wurde durch die neue [Advanced eDiscovery Lösung](./ediscovery.md) im Microsoft 365 Compliance Center ersetzt.

So ermitteln Sie, ob Ihre Organisation Advanced eDiscovery v1.0 verwendet:

1. Wechseln Sie zum [Office 365 Security & Compliance Center.](https://protection.office.com)

2. Klicken Sie im linken Navigationsbereich des Security & Compliance Centers auf **eDiscovery > eDiscovery,** und öffnen Sie einen Core eDiscovery-Fall.

3. Wenn die Schaltfläche **"Zu Advanced eDiscovery wechseln"** angezeigt wird, gelangen Sie durch Klicken darauf zur Version 1.0 von Advanced eDiscovery, die zurückgezogen wird. Die Möglichkeit zum Erstellen und Verwalten von Fällen in Core eDiscovery wird nicht beeinträchtigt. Es wird nur die Möglichkeit zum Hinzufügen und Analysieren von Falldaten in Advanced eDiscovery Version 1.0 (durch Klicken auf **"Zu Advanced eDiscovery wechseln")** eingestellt.

Die neue Advanced eDiscovery-Lösung in Microsoft 365 (auch bekannt als *Advanced eDiscovery v2.0)* bietet alle Funktionen der ursprünglichen Lösung, umfasst aber jetzt einen verwahrerbasierten Ansatz zum Identifizieren von Inhalten in anderen Microsoft 365 Diensten, zum Sammeln dieser Inhalte und zum hinzufügen zu einem Prüfdateisatz, in dem Prüfer schnelle Suchabfragen, Tagging und Analysefeatures nutzen können, um relevante Dokumente auszusortieren. Advanced eDiscovery jetzt eine verbesserte Verarbeitung und systemeigene Viewer für Microsoft- und Nicht-Microsoft-Dateitypen enthält, finden [Sie](./supported-filetypes-ediscovery20.md) hier eine vollständige Liste der Dateitypen und unterstützte Metadatenfelder sind [hier.](./document-metadata-fields-in-advanced-ediscovery.md) Darüber hinaus bietet die neue Advanced eDiscovery-Lösung ein leistungsstarkes Verwaltungsfeature für Verwahrer, mit dem Sie Haltebereiche auf Inhalte in verschiedenen Diensten anwenden, Benutzer über die Haltebereiche benachrichtigen und Antworten von Verwahrern nachverfolgen können, alles innerhalb eines Advanced eDiscovery Falls.

So greifen Sie auf Advanced eDiscovery v2.0 zu

1. Wechseln Sie zum [Microsoft 365 Compliance Center](https://compliance.microsoft.com).

2. Klicken Sie im linken Navigationsbereich des Microsoft 365 Compliance Centers auf **Ale anzeigen**, und klicken Sie dann auf **eDiscovery > Advanced**.

Zu diesem Zeitpunkt empfehlen wir Ihnen, mit dem Übergang Ihres eDiscovery-Workflows zu der neuen Advanced eDiscovery-Funktionalität zu beginnen. Falls erforderlich, können Sie Ihre Advanced eDiscovery 1.0-Fälle archivieren, indem Sie den Inhalt exportieren und offline speichern. Obwohl Sie in vorhandenen Fällen bis zum 31. Dezember 2020 weiterhin auf Advanced eDiscovery Version 1.0 zugreifen können, bietet der Microsoft-Support nach dem 1. Oktober 2020 keinen Support mehr. Weitere Informationen finden Sie auf der folgenden Zeitachse.

### <a name="scope-of-affected-organizations"></a>Umfang der betroffenen Organisationen

- Office 365 und Microsoft 365 Enterprise Organisationen

- Office 365 und Microsoft 365 Education Organisationen

- Office 365 und Microsoft 365 Behörden; dazu gehören GCC, GCC High und DoD

- Office 365 Deutschland

### <a name="timeline"></a>Zeitachse

- 1. Juli 2020: Sie können keine neuen Advanced eDiscovery v1.0-Fälle erstellen.

- 1. Oktober 2020: Sie können keine neuen Daten hinzufügen (Suchergebnisse für Advanced eDiscovery vorbereiten). Sie können weiterhin mit Daten in vorhandenen Fällen auf eigenes Risiko arbeiten. Der Microsoft-Support bietet keine Unterstützung mehr. 

- 31. Dezember 2020: Sie können nicht auf Advanced eDiscovery v1.0-Fälle zugreifen.

### <a name="alternative-tools"></a>Alternative Tools

Die [Advanced eDiscovery Lösung](./overview-ediscovery-20.md) im Microsoft 365 Compliance Center.