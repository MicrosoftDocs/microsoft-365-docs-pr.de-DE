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
description: In-Place eDiscovery und In-Place Hold (und die entsprechenden PowerShell-Cmdlets) in Exchange Online werden in der ersten Hälfte des Jahres 2020 eingestellt. Das Search-Mailbox cmdlet und Advanced eDiscovery v1.0 werden ebenfalls innerhalb desselben Zeitraums eingestellt.
ms.openlocfilehash: 48a20b9e73c5379325afb715a86c4945385fd0b9
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50903605"
---
# <a name="retirement-of-legacy-ediscovery-tools"></a>Einstellung älterer eDiscovery-Tools

> [!IMPORTANT]
> Microsoft hat die Situation der öffentlichen Gesundheit ausgewertet, und wir wissen, wie sich dies auf unsere Kunden auswirken kann. Wir möchten starke Partner und verantwortliche globale Bürger sein. Um eine der vielen Lasten zu verringern, mit denen Sie konfrontiert sind, verzögern wir die geplante Rente für die älteren eDiscovery-Tools, die in diesem Artikel beschrieben werden, um drei Monate. **Die aktualisierten Ruhezeitdaten werden unten angezeigt.**

Im Laufe der Jahre hat Microsoft eDiscovery-Tools bereitgestellt, mit deren Unterstützung Sie E-Mail-Inhalte aus Exchange Online durchsuchen, in der Vorschau anzeigen und exportieren können. Diese Tools bieten jedoch keine effektive Möglichkeit mehr, in anderen Microsoft 365-Diensten wie SharePoint Online und Microsoft 365-Gruppen nach Nicht-Exchange-Inhalten zu suchen. Um dies zu adressieren, bietet Microsoft weitere eDiscovery-Tools, mit deren Hilfe Sie nach einer Vielzahl von Microsoft 365-Inhalten suchen können. Und wir haben hart daran gearbeitet, die aktuelle und leistungsstärkste eDiscovery-Funktionalität im [Microsoft 365 Compliance Center zu integrieren.](https://compliance.microsoft.com) Auf diese Weise können Organisationen auf rechtliche, interne und andere Dokumentanforderungen für Inhalte in vielen Microsoft 365-Diensten, einschließlich Exchange Online, reagieren.

Als Ergebnis dieser neuen und verbesserten eDiscovery-Funktionalität im Microsoft 365 Compliance Center werden die folgenden eDiscovery-bezogenen Features und Funktionen im Zusammenhang mit der Suche nach E-Mail-Inhalten in Exchange Online und Microsoft 365 zurück gestellt:

- [In-Place eDiscovery](/exchange/security-and-compliance/in-place-ediscovery/in-place-ediscovery) und [In-Place Holds](/exchange/security-and-compliance/create-or-remove-in-place-holds) im Exchange Admin Center.

- Die Exchange Online PowerShell-Cmdlets, die In-Place eDiscovery und In-Place Holds unterstützen (diese Cmdlets werden gemeinsam als **-MailboxSearch-Cmdlets* identifiziert). Dies umfasst die folgenden Cmdlets:

  - [New-MailboxSearch](/powershell/module/exchange/new-mailboxsearch)

  - [Start-MailboxSearch](/powershell/module/exchange/start-mailboxsearch)

  - [Stop-MailboxSearch](/powershell/module/exchange/stop-mailboxsearch)

  - [Set-MailboxSearch](/powershell/module/exchange/set-mailboxsearch)

   > [!NOTE]
   > Die [Cmdlets Get-MailboxSearch](/powershell/module/exchange/get-mailboxsearch) und [Remove-MailboxSearch](/powershell/module/exchange/remove-mailboxsearch) sind verfügbar, nachdem die anderen ****-MailboxSearch***-Cmdlets eingestellt wurden, sodass Sie sie verwenden können, um beim Übergang zu anderen eDiscovery- und Haltetools zu helfen. Nach einem bestimmten Datum (siehe unten) unterstützt der Microsoft Support diese beiden Cmdlets jedoch nicht mehr.

- Das [Cmdlet Search-Mailbox](/powershell/module/exchange/search-mailbox) in Exchange Online PowerShell.

- Die folgenden Vorgänge in der Exchange Web Services-API:

   - [GetSearchableMailboxes](/exchange/client-developer/web-service-reference/getsearchablemailboxes-operation)

   - [SearchMailboxes](/exchange/client-developer/web-service-reference/searchmailboxes-operation)
   
   - [SetHoldOnMailboxes](/exchange/client-developer/web-service-reference/setholdonmailboxes-operation)

   - [GetHoldOnMailboxes](/exchange/client-developer/web-service-reference/getholdonmailboxes-operation)

- [Office 365 Advanced eDiscovery v1.0](./overview-ediscovery-20.md), die erste Version von Advanced eDiscovery, auf die über einen Core eDiscovery-Fall im Office 365 Security & Compliance Center zugegriffen wird. Die Rente von Advanced eDiscovery v1.0 wirkt sich nicht auf die Möglichkeit aus, Core eDiscovery-Fälle zu erstellen und zu verwalten.

> [!NOTE]
> Die eingestellte eDiscovery-Funktionalität gilt nur für cloudbasierte Versionen von Microsoft 365 und Office 365. eDiscovery-Funktionen in lokalen Versionen von Exchange und SharePoint werden bis auf weiteres weiterhin unterstützt.

Die folgenden Abschnitte in diesem Artikel enthalten Anleitungen zu den einzelnen Features, die eingestellt werden. Diese Informationen enthalten Zeitachsen und alternative Tools, die Sie anstelle des eingestellten Tools verwenden können.

## <a name="in-place-ediscovery-and-in-place-holds-in-the-exchange-admin-center"></a>In-Place eDiscovery und In-Place im Exchange Admin Center 

Wie der ursprünglichen Ankündigung vom 1. Juli 2017 entspricht, wird die In-Place eDiscovery & Hold-Funktion im Exchange Admin Center (EAC) eingestellt. Die In-Place eDiscovery & in der EAC ermöglicht es Ihnen, Inhalte aus Exchange Online zu suchen, zu halten und zu exportieren. In-Place eDiscovery können Sie auch Suchergebnisse in ein Discoverypostfach kopieren, damit Sie oder andere eDiscovery-Manager Inhalte überprüfen und für rechtliche, behördliche und öffentliche Anforderungen zur Verfügung stellen können.

Da alle diese Funktionen (mit Ausnahme des Kopierens von Suchergebnissen in ein Discoverypostfach) jetzt in der Inhaltssuche, eDiscovery- und Advanced eDiscovery-Tools im [Microsoft 365 Compliance Center](./microsoft-365-compliance-center.md) verfügbar sind (mit verbesserter Funktionalität, Zuverlässigkeit und Unterstützung für eine vielzahl von Microsoft 365-Diensten), wird empfohlen, diese Tools so bald wie möglich zu verwenden. Um Ihnen beim Übergang zu diesen anderen eDiscovery-Tools zu helfen, werden in der folgenden Tabelle die Tools aufgeführt, die Sie anstelle von eDiscovery und In-Place verwenden In-Place können.

### <a name="scope-of-affected-organizations"></a>Umfang betroffener Organisationen

- Office 365- und Microsoft 365 Enterprise-Organisationen

- Office 365- und Microsoft 365 Education-Organisationen

- Office 365- und Microsoft 365 Government-Organisationen; Dazu gehören GCC, GCC High und DoD

- Office 365 Deutschland

### <a name="timeline-for-retirement"></a>Zeitachse für die Rente

- 1. Juli 2020: Sie können keine neuen Such- und Haltekriterien erstellen, aber Sie können vorhandene Suchen auf eigenes Risiko ausführen, bearbeiten und löschen. Der Microsoft Support In-Place eDiscovery & in der EAC nicht mehr verfügbar.

- 1. Oktober 2020: Die In-Place eDiscovery & Holds-Funktionalität in der EAC wird in einen schreibgeschützten Modus versetzt. Dies bedeutet, dass Sie nur vorhandene Such- und Haltekriterien entfernen können.

### <a name="alternative-tools"></a>Alternative Tools

In der folgenden Tabelle werden andere Tools beschrieben, die Sie zum Ersetzen der vorhandenen Funktionalität verwenden können, die eingestellt wird.

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
<td>Suchen, Exportieren und Halten zu rechtlichen Zwecken</td>
<td>Zentrale eDiscovery-Fälle im Microsoft 365 Compliance Center </td>
<td><p>Die Verwendung der Funktionen von eDiscovery-Kernfällen bietet die funktionale Parität für In-Place eDiscovery und In-Place Holds. Dazu gehört Folgendes:</p>
<ul>
<li>
<p>Suchskalen auf Millionen von Speicherorten</p>
</li>
<li>
<p>Höhere Zuverlässigkeit beim Suchen, Exportieren und Platzieren von Inhalten</p>
</li>
<li>
<p>Suchen nach Inhalten für Exchange Online, SharePoint Online, OneDrive for Business, Skype for Business, Microsoft Teams, Yammer-Gruppen, Microsoft 365-Gruppen und andere in Office 365-Anwendungen gespeicherte Inhalte</p></li></ul>
</td>
</tr>
<tr class="even">
<td>Aufbewahrung für Aufbewahrungszwecke</td>
<td>Aufbewahrungsrichtlinien im Microsoft 365 Compliance Center</td>
<td><p>Mithilfe von Aufbewahrungsrichtlinien können Sie Inhalte beibehalten und nach Ablauf des Aufbewahrungszeitraums bei Bedarf löschen. Weitere Funktionen sind:</p>
<ul>
<li>
<p>Anwenden von Richtlinien auf Ihre gesamte Organisation </p>
</li><li>
<p>Anwenden von Richtlinien auf bestimmte Inhaltsstandorte wie Exchange Online, SharePoint Online, OneDrive for Business, Skype for Business, Microsoft Teams und Office 365-Gruppen</p></li>
<li>
<p>Anwenden von Richtlinien auf bestimmte Benutzer</p></li></ul>
<p>Weitere Informationen finden Sie <a href="/microsoft-365/compliance/retention-policies">unter Informationen zu Aufbewahrungsrichtlinien und Aufbewahrungsbezeichnungen.</a></td>
</tr>
<tr class="odd">
<td>Kopieren von E-Mail-Suchergebnissen zur Überprüfung in ein Discoverypostfach</td><td>Überprüfen von Sätzen in Advanced eDiscovery v2.0</td>
<td><p>Das Überprüfen von Inhalten in Microsoft 365 war noch nie einfacher. Überprüfungssätze verfügen über viele großartige Funktionen, um den Zeit- und Datenaufwand für die Überprüfung zu reduzieren, einschließlich:</p>
<ul>
<li><p>Ausführen schneller Suchabfragen und Filtern von Inhalten in einem Überprüfungssatz</p></li>
<li><p>Analysieren von Inhalten in einem Überprüfungssatz; Dies umfasst E-Mail-Threading, Fast-Dupliziert-Erkennung, Designs-Analyse und Vorhersagecodierung</p></li>
<li><p>Markieren von Dokumenten in einem Prüfdateisatz</p></li>
<li><p>Markieren von Vorschlägen zur Identifizierung von Inhalten von Anwalts-Clientrechten</p></li></ul>
<p>Weitere Informationen finden Sie unter <a href="/microsoft-365/compliance/overview-ediscovery-20">Übersicht über die Advanced eDiscovery-Lösung in Microsoft 365</a>.</p>
<p>
<p>Alternativ können Sie Suchergebnisse in PST-Dateien exportieren und dann den Microsoft 365-Importdienst verwenden, um die PSTs in ein Discoverypostfach zu importieren. Eine schrittweise Anleitung finden Sie unter Verwenden des Netzwerkuploads zum <a href="/microsoft-365/compliance/use-network-upload-to-import-pst-files">Importieren von PST-Dateien in Office 365</a>.
</tr>
<tr class=even>
  <td>Kopieren von Nachrichten aus einem Postfach in ein anderes Postfach</td>
  <td><a href="/exchange/recipients-in-exchange-online/manage-permissions-for-recipients">Zuweisen von Berechtigungen zu einem Postfach</a></td>
  <td>Um einer Person Zugriff auf die E-Mails eines anderen Benutzers zu gewähren (z. B. wenn ein Mitarbeiter Ihre Organisation verlässt und Sie einer anderen Person Zugriff auf die E-Mail des ehemaligen Mitarbeiters gewähren müssen), wird empfohlen, dieser Person Berechtigungen für den Zugriff auf das Postfach des ehemaligen Mitarbeiters zu erteilen. Anstatt also Postfachelemente in ein anderes Benutzerpostfach oder ein freigegebenes Postfach zu kopieren, weisen Sie einfach einem Benutzer Berechtigungen für den Zugriff auf das Quellpostfach zu.</td>
  
  </tr>
<tr class="odd">
<td>Wiederherstellen von Elementen aus dem Ordner "Wiederherstellbare Elemente"</td>
  <td><a href="https://docs.microsoft.com/powershell/module/exchange/Restore-RecoverableItems">Restore-RecoverableItems</td>
  <td>Sie können dauerhaft gelöschte Elemente (auch als <i>"soft-deleted</i> items" bezeichnet) in Postfächern wiederherstellen, solange der Aufbewahrungszeitraum für gelöschte Elemente für ein Element nicht abgelaufen ist. Weitere Informationen finden Sie unter <a href="/Exchange/security-and-compliance/recoverable-items-folder/recoverable-items-folder">Ordner "Wiederherstellbare Elemente" in Exchange Online</a>.</td>
</tr>
</tbody>
</table>

### <a name="faqs-about-in-place-ediscovery-and-in-place-holds"></a>Häufig gestellte Fragen In-Place eDiscovery und In-Place Holds

**Ich verwende die Funktion zum Kopieren von Suchergebnissen von In-Place eDiscovery & In der EAC, um Suchergebnisse zur Überprüfung durch Anwälte in ein Discoverypostfach zu kopieren. Welche Optionen habe ich jetzt?**

Es gibt zwei Möglichkeiten, diese Funktionalität heute zu replizieren. Der erste ist die Verwendung [von Überprüfungssätzen in Advanced eDiscovery v2.0](./view-documents-in-review-set.md). Überprüfungssätze verfügen über viele der gleichen Funktionen, die Sie in einem herkömmlichen Überprüfungstool sehen, z. B. schnelle Suche nach Dokumenten, Tagging, E-Mail-Threading, beinahe doppelte Gruppierung, Designsanalyse und Vorhersagecodierung. Wenn Sie weiterhin Discoverypostfächer zur Überprüfung verwenden möchten, besteht die zweite Option im Exportieren von Suchergebnissen in [](use-network-upload-to-import-pst-files.md) PST-Dateien und anschließendes Importieren der PST-Dateien in ein Discoverypostfach mithilfe des PST-Importfeatures im Microsoft Compliance Center.

**Wie kann ich steuern, welche Inhaltsspeicherorte (z. B. Postfächer oder Websites) ein eDiscovery-Manager mit den neuen Tools durchsuchen kann?**

Das Microsoft 365 Compliance [](set-up-compliance-boundaries.md) Center verwendet auch Compliancegrenzen, um zu steuern, welche Inhaltsstandorte ein eDiscovery-Manager durchsuchen kann. Compliancegrenzen sind nützlich für Behörden, die innerhalb von Agenturgrenzen bleiben müssen, oder in multinationalen Unternehmen, die zur Einhaltung geografischer Boarder erforderlich sind.

**Wie kann ich meine aktuellen Such- und Halte halte in das Microsoft 365 Compliance Center verschieben?**

Es ist möglich, In-Place eDiscovery-Suche und -Halte von der EAC mithilfe von PowerShell zu migrieren. Anweisungen finden Sie unter [Migrate searches and holds from the EAC to the Microsoft 365 Compliance Center](./migrate-legacy-ediscovery-searches-and-holds.md).

## <a name="-mailboxsearch-cmdlets"></a>\*-MailboxSearch-Cmdlets

Wie im ursprünglichen Hinweis vom 1. Juli 2017 im Exchange Admin Center angekündigt, werden die In-Place eDiscovery & Hold-Funktion und die entsprechenden **\* -MailboxSearch-Cmdlets** eingestellt. Diese Cmdlets bieten Benutzern die Möglichkeit, Postfachinhalte für rechtliche, behördliche und öffentliche Anforderungen zu durchsuchen, zu archivieren und zu exportieren.

Da diese Funktionen jetzt im [<span class="underline">Microsoft 365 Compliance Center</span>](./microsoft-365-compliance-center.md) und office 365 Security & Compliance Center PowerShell mit verbesserter Leistung und Skalierbarkeit verfügbar sind, sollten Sie diese verbesserten Cmdlets verwenden. Zu diesen Cmdlets gehören [<span class="underline"> \* -ComplianceCase</span>](/powershell/module/exchange/get-compliancecase), [<span class="underline"> \* -ComplianceSearch</span>](/powershell/module/exchange/get-compliancesearch), [<span class="underline"> \* -CaseHoldPolicy</span>](/powershell/module/exchange/get-caseholdpolicy), [<span class="underline"> \* -CaseHoldRule</span>](/powershell/module/exchange/get-caseholdrule)und [<span class="underline"> \* -ComplianceSearchAction</span>](/powershell/module/exchange/get-compliancesearchaction).

### <a name="scope-of-affected-organizations"></a>Umfang betroffener Organisationen

- Office 365- und Microsoft 365 Enterprise-Organisationen

- Office 365- und Microsoft 365 Education-Organisationen

- Office 365- und Microsoft 365 Government-Organisationen; Dazu gehören GCC, GCC High und DoD

- Office 365 Deutschland

### <a name="timeline"></a>Zeitachse

- 1. Juli 2020: Sie können **New-MailboxSearch** nicht verwenden, um neue In-Place eDiscovery-Suchen und In-Place-Haltefächer zu erstellen. Sie können jedoch weiterhin Cmdlets verwenden, um vorhandene Suchen und Haltefächer auf eigenes Risiko ausführen, bearbeiten und löschen zu können. Der Microsoft-Support bietet keine Unterstützung mehr für diese Such- und Haltetypen.

- 1. Oktober 2020: Wie bereits erwähnt, wird die In-Place eDiscovery & Holds-Funktionalität in der EAC in einen schreibgeschützten Modus versetzt. Das bedeutet auch, dass Sie die **Cmdlets New-MailboxSearch,** **Start-MailboxSearch** oder **Set-MailboxSearch nicht** verwenden können. Sie können nur vorhandene Such- und Haltekriterien erhalten und entfernen.

### <a name="alternative-tools"></a>Alternative Tools

In der folgenden Tabelle werden andere Tools beschrieben, die Sie zum Ersetzen der vorhandenen Funktionalität verwenden können, die eingestellt wird.

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
<td><p><a href="https://docs.microsoft.com/powershell/module/exchange/get-compliancesearch"><span class="underline">*-ComplianceSearch</span></a></p>
<p><a href="https://docs.microsoft.com/powershell/module/exchange/get-compliancesearchaction"><span class="underline">*-ComplianceSearchAction</span></a></p>
<p><a href="https://docs.microsoft.com/powershell/module/exchange/get-compliancecase"><span class="underline">*-ComplianceCase</span></a></p>
<p> </p></td>
<td><p>Die Cmdlets ComplianceSearch und ComplianceSearchAction arbeiten zusammen, um Ihnen beim Suchen und Exportieren von Inhalten zu helfen. Sie können eine neue Suche erstellen und die Suchschätzung mithilfe der <strong>Cmdlets New-</strong>, <strong>Get-</strong>und <strong>Start-ComplianceSearch</strong> anzeigen. Anschließend können Sie das <strong>Cmdlet New-ComplianceSearchAction</strong> verwenden, um die Suchergebnisse zu exportieren. Sie müssen weiterhin das zentrale eDiscovery-Tool im Microsoft 365 Compliance Center verwenden, um diese Suchergebnisse auf Ihren lokalen Computer herunterzuladen.</p>
<p>
<p><strong>Hinweis:</strong> Wenn Sie diese Cmdlets zum Erstellen von Suchen verwenden, die keinem zentralen eDiscovery-Fall <strong></strong> zugeordnet sind, befinden sich diese Suchen auf der Seite Inhaltssuche im Microsoft 365 Compliance Center.</p></td>
</tr>
<tr class="even">
<td>Halten von Inhalten in einem Postfach</td>
<td><p><a href="https://docs.microsoft.com/powershell/module/exchange/get-caseholdpolicy"><span class="underline">*-CaseHoldPolicy</span></a></p>
<p><a href="https://docs.microsoft.com/powershell/module/exchange/get-caseholdrule"><span class="underline">*-CaseHoldRule</span></a></p>
<p><a href="https://docs.microsoft.com/powershell/module/exchange/get-compliancecase"><span class="underline">*-ComplianceCase</span></a></p>
<p> </p></td>
<td><p>Halte halte im Microsoft 365 Compliance Center müssen einem ComplianceCase zugeordnet sein. Erstellen Sie zuerst den Compliancefall, und erstellen Sie dann caseHoldPolicy und CaseHoldRule.</p>
<p><strong>Hinweis:</strong> Durch das Erstellen eines CaseHoldPolicy-Falls ohne erstellen von CaseHoldRule ist der Haltegriff nicht mehr funktionsfähig, bis caseHoldRule erstellt und caseHoldPolicy zugeordnet ist. Weitere Informationen finden Sie in der Cmdletdokumentation.</p></td>
</tr>
<tr class="odd">
<td>Kopieren von Suchergebnissen in ein Discoverypostfach</td>
<td>Keine</td>
<td>Es gibt keinen direkten Ersatz für diese Funktionalität, da sie nicht zugriff auf alle Microsoft 365-Dienste bietet. Weitere Informationen zu alternativen Lösungen finden Sie in den folgenden häufig gestellten Fragen.</td>
</tr>
  <tr class=even>
  <td>Kopieren von Nachrichten aus einem Postfach in ein anderes Postfach</td>
  <td><a href="/exchange/recipients-in-exchange-online/manage-permissions-for-recipients">Zuweisen von Berechtigungen zu einem Postfach</a></td>
  <td>Um einer Person Zugriff auf die E-Mails eines anderen Benutzers zu gewähren (z. B. wenn ein Mitarbeiter Ihre Organisation verlässt und Sie einer anderen Person Zugriff auf die E-Mail des ehemaligen Mitarbeiters gewähren müssen), wird empfohlen, dieser Person Berechtigungen für den Zugriff auf das Postfach des ehemaligen Mitarbeiters zu erteilen. Anstatt also Postfachelemente in ein anderes Benutzerpostfach oder ein freigegebenes Postfach zu kopieren, weisen Sie einfach einem Benutzer Berechtigungen für den Zugriff auf das Quellpostfach zu.</td>
  
  </tr>

</tbody>
</table>

### <a name="faqs-about--mailboxsearch-cmdlets"></a>FAQs zu ***-MailboxSearch-Cmdlets**

**Wir verwenden die Kopiersuche, um E-Mail-Nachrichten oder Sofortnachrichten für andere eDiscovery- und rechtliche Untersuchungen zu exportieren. Welche anderen Optionen haben wir, nachdem diese Cmdlets eingestellt wurden?**

Die [<span class="underline">Microsoft Graph-APIs</span>](https://developer.microsoft.com/en-us/graph) bieten eine Reihe von Methoden zum Extrahieren von Daten für Analysen und andere Zwecke, die viel stabiler und skalierbarer sind als die Verwendung der **\* -MailboxSearch-Cmdlets.**

**Wie kann ich meine Such- und Haltefunktion zum Microsoft 365 Compliance Center migrieren?**

Mithilfe eines PowerShell-Skripts In-Place eDiscovery-Suche und -Haltebereich aus dem Exchange Admin Center migriert werden. Weitere Informationen finden Sie unter [Migrate legacy eDiscovery searches and holds to the Microsoft 365 Compliance Center](migrate-legacy-eDiscovery-searches-and-holds.md).

**Kann ich nach dem Ausmustern der Cmdlets weiterhin Suchen entfernen oder abrufen?**

Ja, obwohl wir die Möglichkeit zum Erstellen und Ändern von Suchen entfernen, können Sie **get-MailboxSearch** und **Remove-MailboxSearch** bis auf weiteres verwenden. Die Verwendung dieser Cmdlets wird jedoch nach dem Fälligkeitsdatum auf eigenes Risiko gehen, und der Microsoft Support kann keine Unterstützung mehr leisten.

## <a name="search-mailbox-cmdlet"></a>Search-Mailbox Cmdlet

Das **Cmdlet Search-Mailbox** in Exchange Online PowerShell wird wie ursprünglich in einer Warnung in der Ausgabe des Cmdlets ab 2018 angekündigt eingestellt. Das **Cmdlet Search-Mailbox** wurde ursprünglich verwendet, um das Postfach eines Benutzers zu durchsuchen und schädliche Inhalte zu löschen. Es wird empfohlen, die **Cmdlets New-ComplianceSearch** und **New-ComplianceSearchAction** in Office 365 Security & Compliance Center PowerShell zum Suchen und Löschen von Inhalten zu verwenden. Für eine integrierte Sicherheitserfahrung bieten die [<span class="underline">Microsoft 365-Sicherheitsfeatures</span>](../security/index.yml) einen robusten Bedrohungsschutz für E-Mails und viele andere Microsoft-Dienste.

### <a name="scope-of-affected-organizations"></a>Umfang betroffener Organisationen

- Office 365- und Microsoft 365 Enterprise-Organisationen

- Office 365- und Microsoft 365 Education-Organisationen

- Office 365- und Microsoft 365 Government-Organisationen; Dazu gehören GCC, GCC High und DoD

- Office 365 Deutschland

### <a name="timeline"></a>Zeitachse

-  1. Juli 2020: Das **Cmdlet Search-Mailbox** ist nicht mehr verfügbar, und der Microsoft Support bietet keine Unterstützung mehr.

### <a name="alternative-tools"></a>Alternative Tools

In der folgenden Tabelle werden andere Tools beschrieben, die Sie zum Ersetzen der vorhandenen Funktionalität verwenden können, die eingestellt wird.

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
<td><p><a href="https://docs.microsoft.com/powershell/module/exchange/get-compliancesearch"><span class="underline">*-ComplianceSearch</span></a></p>
<p><a href="https://docs.microsoft.com/powershell/module/exchange/get-compliancesearchaction"><span class="underline">*-ComplianceSearchAction</span></a></p>
<p></a></p></td>
<td><p>Die Cmdlets ComplianceSearch und ComplianceSearchAction arbeiten zusammen, um Ihnen beim Suchen und Exportieren von Inhalten zu helfen. Sie können eine neue Suche erstellen und die Suchschätzung mithilfe der <strong>Cmdlets New-</strong>, <strong>Get-</strong>und <strong>Start-ComplianceSearch</strong> anzeigen. Anschließend können Sie den <strong>Befehl New-ComplianceSearchAction -Export verwenden,</strong> um die Suchergebnisse zu exportieren. Sie müssen weiterhin das zentrale eDiscovery-Tool im Microsoft 365 Compliance Center verwenden, um diese Suchergebnisse auf Ihren lokalen Computer herunterzuladen.</p></p>
</td>
</tr>
<tr class="even">
<td>Löschen von Massen-E-Mails aus einem Postfach</td>
<td><p><a href="https://docs.microsoft.com/microsoft-365/compliance/set-up-an-archive-and-deletion-policy-for-mailboxes?view=o365-worldwide"><span class="underline">Einrichten einer Richtlinie zum Archivieren und Löschen für Postfächer</span></a></p>
<p></p></td>
<td><p>Administratoren können eine Archivierungs- und Löschrichtlinie erstellen, die Elemente automatisch in das Archivpostfach eines Benutzers verschiebt und Elemente automatisch aus dem Postfach löscht.</p>
</td>
</tr>
<tr class="even">
<td>Kopieren von Suchergebnissen in ein Discoverypostfach</td>
<td> </td>
<td>Es gibt keinen direkten Ersatz für diese Funktionalität, da sie nicht zugriff auf alle Microsoft 365-Dienste bietet. Alternative Lösungen finden Sie in den FAQs im Abschnitt <strong>*-MailboxSearch-Cmdlets.</strong> </td>
</tr>
<tr class=odd>
  <td>Kopieren von Nachrichten aus einem Postfach in ein anderes Postfach</td>
  <td><a href="/exchange/recipients-in-exchange-online/manage-permissions-for-recipients">Zuweisen von Berechtigungen zu einem Postfach</a></td>
  <td>Um einer Person Zugriff auf die E-Mails eines anderen Benutzers zu gewähren (z. B. wenn ein Mitarbeiter Ihre Organisation verlässt und Sie einer anderen Person Zugriff auf die E-Mail des ehemaligen Mitarbeiters gewähren müssen), wird empfohlen, dieser Person Berechtigungen für den Zugriff auf das Postfach des ehemaligen Mitarbeiters zu erteilen. Anstatt also Postfachelemente in ein anderes Benutzerpostfach oder ein freigegebenes Postfach zu kopieren, weisen Sie einfach einem Benutzer Berechtigungen für den Zugriff auf das Quellpostfach zu.</td>
</tr>
<tr class=even>
  <td>Löschen von Nachrichten aus einem Postfach</td>
<td><p><a href="https://docs.microsoft.com/powershell/module/exchange/get-compliancesearch"><span class="underline">*-ComplianceSearch</span></a></p>
<p><a href="https://docs.microsoft.com/powershell/module/exchange/get-compliancesearchaction"><span class="underline">*-ComplianceSearchAction</span></a></p>
<p></p></td>
<td><p>Die Cmdlets ComplianceSearch und ComplianceSearchAction arbeiten zusammen, um Ihnen beim Suchen und Löschen von Inhalten zu helfen. Sie können eine Suche mit <strong>Cmdlets New-ComplianceSearch</strong> und <strong>New-ComplianceSearch</strong> erstellen und ausführen und dann den Inhalt mithilfe des <strong>Befehls New-ComplianceSearchAction -Purge -PurgeType</strong> löschen. Weitere Informationen finden Sie unter <a href="https://docs.microsoft.com/microsoft-365/compliance/search-for-and-delete-messages-in-your-organization"><span class="underline">Suchen nach und Löschen von Nachrichten</span></a>.</p>
</td>
</tr>
<tr class="odd"> 
<td>Löschen von Nachrichten aus einem Postfach</td>
<td><a href="/exchange/recipients-in-exchange-online/manage-permissions-for-recipients">Zuweisen von Berechtigungen zu einem Postfach</a></td>
<td>Um Nachrichten aus einem Postfach zu löschen, weisen Sie einem Administrator Berechtigungen für den Zugriff auf das Postfach des Mitarbeiters zu. Nachrichten können bei Bedarf gelöscht und wiederverwendet werden, indem sie die integrierten Such- und Anzeigefunktionen in Outlook nutzen.</td>
</tr>
</tbody>
</table>

## <a name="exchange-web-services-api-operations"></a>Exchange Web Services-API-Vorgänge

Diese Vorgänge in der Exchange Web Services-API werden von der In-Place eDiscovery & Holds-Funktion im Exchange Admin Center und den entsprechenden **\* Cmdlets -MailboxSearch** in Exchange Online PowerShell verwendet. Sie werden auch im Rahmen des Zurücktretens der anderen älteren eDiscovery-Tools eingestellt.

### <a name="scope-of-affected-organizations"></a>Umfang betroffener Organisationen

- Office 365- und Microsoft 365 Enterprise-Organisationen

- Office 365- und Microsoft 365 Education-Organisationen

- Office 365- und Microsoft 365 Government-Organisationen; Dazu gehören GCC, GCC High und DoD

- Office 365 Deutschland

### <a name="timeline"></a>Zeitachse

- 1. Juli 2020: Die Vorgänge GetSearchableMailboxes, SearchMailboxes, SetHoldOnMailboxes und GetHoldOnMailboxes sind nicht mehr verfügbar, und der Microsoft Support bietet keine Unterstützung mehr.

## <a name="advanced-ediscovery-v10"></a>Advanced eDiscovery v1.0

Advanced eDiscovery v1.0, die Version von Advanced eDiscovery, die in einem zentralen eDiscovery-Fall verfügbar ist, indem Sie auf **Switch to Advanced eDiscovery** klicken, wird eingestellt. Seine Funktionalität wurde durch die neue [Advanced eDiscovery-Lösung](./ediscovery.md) im Microsoft 365 Compliance Center ersetzt.

So ermitteln Sie, ob Ihre Organisation Advanced eDiscovery v1.0 verwendet:

1. Wechseln Sie zum [Office 365 Security & Compliance Center](https://protection.office.com).

2. Klicken Sie im linken Navigationsbereich des Security & Compliance Center auf **eDiscovery > eDiscovery,** und öffnen Sie einen Core eDiscovery-Fall.

3. Wenn die Schaltfläche **Switch to Advanced eDiscovery** angezeigt wird, wechseln Sie durch Klicken auf die Schaltfläche zur 1.0-Version von Advanced eDiscovery, die eingestellt wird. Die Möglichkeit, Fälle in Core eDiscovery zu erstellen und zu verwalten, wird nicht beeinträchtigt. Es wird nur die Möglichkeit zum Hinzufügen und Analysieren von Falldaten in Advanced eDiscovery v1.0 (durch Klicken auf **Switch to Advanced eDiscovery**) eingestellt.

Die neue Advanced eDiscovery-Lösung in Microsoft 365 (auch bekannt als *Advanced eDiscovery v2.0*) bietet alle Funktionen der ursprünglichen Lösung, umfasst nun jedoch einen custodian-basierten Ansatz zum Identifizieren von Inhalten in anderen Microsoft 365-Diensten, zum Sammeln dieser Inhalte und zum Hinzufügen zu einem Überprüfungssatz, in dem Prüfer schnelle Suchabfragen, Markierungen und Analysefeatures nutzen können, um relevante Dokumente zu entfernen. Advanced eDiscovery umfasst nun eine verbesserte Verarbeitung und systemeigene Viewer für Microsoft- und [](./supported-filetypes-ediscovery20.md) Nicht-Microsoft-Dateitypen, eine vollständige Liste der Dateitypen ist hier und unterstützte Metadatenfelder sind [hier .](./document-metadata-fields-in-advanced-ediscovery.md) Darüber hinaus bietet die neue Advanced eDiscovery-Lösung ein leistungsfähiges Verwaltungsfeature für Verwahrer, mit dem Sie Haltefeatures auf Inhalte in verschiedenen Diensten anwenden, Benutzer über die Haltedienste benachrichtigen und Verwahrerantworten nachverfolgen können, und dies alles in einem Advanced eDiscovery-Fall.

So greifen Sie auf Advanced eDiscovery v2.0 zu

1. Wechseln Sie zum [Microsoft 365 Compliance Center](https://compliance.microsoft.com).

2. Klicken Sie im linken Navigationsbereich des Microsoft 365 Compliance Centers auf **Ale anzeigen**, und klicken Sie dann auf **eDiscovery > Advanced**.

Zu diesem Zeitpunkt wird empfohlen, den eDiscovery-Workflow auf die neue Erweiterte eDiscovery-Funktionalität um zu ändern. Bei Bedarf können Sie Ihre Advanced eDiscovery 1.0-Fälle archivieren, indem Sie den Inhalt exportieren und offline speichern. Obwohl Sie in vorhandenen Fällen noch bis zum 31. Dezember 2020 auf Advanced eDiscovery v1.0 zugreifen können, bietet der Microsoft Support nach dem 1. Oktober 2020 keinen Support mehr. Weitere Informationen finden Sie auf der folgenden Zeitachse.

### <a name="scope-of-affected-organizations"></a>Umfang betroffener Organisationen

- Office 365- und Microsoft 365 Enterprise-Organisationen

- Office 365- und Microsoft 365 Education-Organisationen

- Office 365- und Microsoft 365 Government-Organisationen; Dazu gehören GCC, GCC High und DoD

- Office 365 Deutschland

### <a name="timeline"></a>Zeitachse

- 1. Juli 2020: Sie können keine neuen Erweiterten eDiscovery v1.0-Fälle erstellen.

- 1. Oktober 2020: Sie können in keinem Fall neue Daten hinzufügen (Suchergebnisse für Advanced eDiscovery vorbereiten). Sie können weiterhin auf eigenes Risiko mit Daten in vorhandenen Fällen arbeiten. Der Microsoft Support bietet keine Unterstützung mehr. 

- 31. Dezember 2020: Sie können nicht auf Advanced eDiscovery v1.0-Fälle zugreifen.

### <a name="alternative-tools"></a>Alternative Tools

Die [Advanced eDiscovery-Lösung](./overview-ediscovery-20.md) im Microsoft 365 Compliance Center.