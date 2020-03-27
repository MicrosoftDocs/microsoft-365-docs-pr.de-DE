---
title: Ruhestand von vorversions-eDiscovery-Tools
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
description: In-situ-eDiscovery und in-situ-Speicher (und die entsprechenden PowerShell-Cmdlets) in Exchange Online werden in der ersten Hälfte von 2020 zurückgezogen. Das Cmdlet Search-Mailbox und Office 365 Advanced eDiscovery v 1.0 werden auch innerhalb desselben Zeitraums zurückgezogen.
ms.openlocfilehash: 5ee588b2c05241628242e8660f10c23dba809bf8
ms.sourcegitcommit: 7646e2d742d1b2fad085a00200a2a10461dd4bac
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/26/2020
ms.locfileid: "42978165"
---
# <a name="retirement-of-legacy-ediscovery-tools"></a>Ruhestand von vorversions-eDiscovery-Tools

> [!IMPORTANT]
> Microsoft hat die öffentliche Gesundheitssituation bewertet, und wir verstehen, welche Auswirkungen dies auf unsere Kunden hat. Wir möchten starke Partner und verantwortungsvolle globale Bürger sein. Um eine der zahlreichen Belastungen zu lindern, die Ihnen gegenüber stehen, werden wir den geplanten Ruhestand für die unten aufgeführten Legacy-eDiscovery-Tools um drei Monate verzögern. **Die aktualisierten Pensions Termine werden nachfolgend wiedergegeben.**

Im Laufe der Jahre hat Microsoft eDiscovery-Tools bereitgestellt, mit denen Sie e-Mail-Inhalte aus Exchange Online durchsuchen, in einer Vorschau anzeigen und exportieren können. Diese Tools bieten jedoch nicht mehr die Möglichkeit, nach nicht-Exchange-Inhalten in anderen Office 365 Diensten wie SharePoint Online und Office 365 Gruppen zu suchen. Um dies zu beheben, bietet Microsoft weitere eDiscovery-Tools, die Sie bei der Suche nach einer Vielzahl von Office 365 Inhalten unterstützen. Und wir arbeiten hart daran, die aktuellsten und leistungsfähigsten eDiscovery-Funktionen im [Microsoft 365 Compliance Center](https://compliance.microsoft.com)zu integrieren. Auf diese Weise können Organisationen auf rechtliche, interne und andere Dokumentanforderungen für Inhalte in vielen Office 365 Diensten, einschließlich Exchange Online, reagieren.

Aufgrund dieser neuen und verbesserten eDiscovery-Funktionalität im Microsoft 365 Compliance Center werden die folgenden eDiscovery-bezogenen Features und Funktionen im Zusammenhang mit der Suche nach e-Mail-Inhalten in Exchange Online und Office 365 in den Ruhestand gehen:

- In [-Place-eDiscovery](https://docs.microsoft.com/exchange/security-and-compliance/in-place-ediscovery/in-place-ediscovery) und [in-Place-](https://docs.microsoft.com/exchange/security-and-compliance/create-or-remove-in-place-holds) Speicher in der Exchange-Verwaltungskonsole.

- Die Exchange Online PowerShell-Cmdlets, die Compliance-eDiscovery und in-Place-Speicher unterstützen (diese Cmdlets werden gemeinsam als **-MailboxSearch-* Cmdlets bezeichnet). Dies umfasst die folgenden Cmdlets:

  - [New-MailboxSearch](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/new-mailboxsearch)

  - [Start-MailboxSearch](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/start-mailboxsearch)

  - [Stop-MailboxSearch](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/stop-mailboxsearch)

  - [Gruppe-MailboxSearch](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/set-mailboxsearch)

   > [!NOTE]
   > Die Cmdlets [Get-MailboxSearch](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/get-mailboxsearch) und [Remove-MailboxSearch](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/remove-mailboxsearch) sind verfügbar, nachdem die anderen Cmdlets * * * *-MailboxSearch * * * zurückgezogen wurden, damit Sie Sie beim Übergang zu anderen eDiscovery-und Hold-Tools unterstützen können. Nach einem bestimmten Datum (zitiert unten) wird der Microsoft-Support diese beiden Cmdlets jedoch nicht mehr unterstützen.

- Das Cmdlet [Search-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/search-mailbox?view=exchange-ps) in Exchange Online PowerShell.

- Die folgenden Vorgänge in der Exchange Webdienste-API:

   - [GetSearchableMailboxes](https://docs.microsoft.com/exchange/client-developer/web-service-reference/getsearchablemailboxes-operation)

   - [SearchMailboxes](https://docs.microsoft.com/exchange/client-developer/web-service-reference/searchmailboxes-operation)
   
   - [SetHoldOnMailboxes](https://docs.microsoft.com/exchange/client-developer/web-service-reference/setholdonmailboxes-operation)

   - [GetHoldOnMailboxes](https://docs.microsoft.com/exchange/client-developer/web-service-reference/getholdonmailboxes-operation)
   


- [Office 365 Advanced eDiscovery v 1.0](office-365-advanced-ediscovery.md), bei dem es sich um die erste Version von Advanced eDiscovery handelt, auf die über einen eDiscovery-Fall im Office 365 Security & Compliance Center zugegriffen wird.

> [!NOTE]
> Die zurückgezogene eDiscovery-Funktionalität gilt nur für Cloud-basierte Versionen von Microsoft 365 und Office 365. eDiscovery-Funktionen in lokalen Versionen von Exchange und SharePoint werden bis auf weiteres weiterhin unterstützt.

Die folgenden Abschnitte in diesem Artikel enthalten Anleitungen zu jedem Feature, das in den Ruhestand geht. Diese Informationen umfassen Zeitpläne und Alternative Tools, die Sie anstelle des Tools zum Zurücksetzen verwenden können.

## <a name="in-place-ediscovery-and-in-place-holds-in-the-exchange-admin-center"></a>Compliance-eDiscovery und in-Place-Speicher im Exchange Admin Center 

Gemäß der ursprünglichen Ankündigung am 1. Juli 2017 wird die in-situ-eDiscovery-&-Funktion in der Exchange-Verwaltungskonsole (EAC) zurückgezogen. Auf der Seite in-situ-eDiscovery-& in der Exchange-Verwaltungskonsole können Sie Inhalte aus Exchange Online durchsuchen, speichern und exportieren. Mit Compliance-eDiscovery können Sie auch Suchergebnisse in ein Discovery-Postfach kopieren, sodass Sie oder andere eDiscovery-Manager Inhalte überprüfen und für rechtliche, regulatorische und öffentliche Anforderungen zur Verfügung stellen können.

Da alle diese Funktionen (mit Ausnahme des Kopierens von Suchergebnissen in ein Discovery-Postfach) jetzt in der Inhaltssuche, eDiscovery und erweiterten eDiscovery-Tools im [Microsoft 365 Compliance Center](https://docs.microsoft.com/microsoft-365/compliance/microsoft-365-compliance-center) verfügbar sind (mit einer verbesserten Funktionalität, Zuverlässigkeit und Unterstützung für eine breite Palette von Microsoft 365-Diensten), sollten Sie diese Tools so schnell wie möglich verwenden. Um Sie beim Übergang zu diesen anderen eDiscovery-Tools zu unterstützen, werden in der folgenden Tabelle die Tools aufgelistet, die Sie anstelle von in-situ-eDiscovery und in-situ-Speicher verwenden können.

### <a name="scope-of-affected-organizations"></a>Umfang der betroffenen Organisationen

- Office 365-und Microsoft 365-Unternehmensorganisationen

- Office 365-und Microsoft 365-Bildungseinrichtungen

- Office 365-und Microsoft 365-Regierungsorganisationen; Dies umfasst gcc, gcc hoch und DoD.

- Office 365 Deutschland

### <a name="timeline-for-retirement"></a>Zeitachse für den Ruhestand

- 1. Juli 2020: Sie können keine neuen suchen und Aufbewahrungen erstellen, aber Sie können vorhandene Suchvorgänge auf eigenes Risiko ausführen, bearbeiten und löschen. Der Microsoft-Support kann keine Compliance-eDiscovery-& mehr in der Exchange-Verwaltungskonsole bereitstellen.

- 1. Oktober 2020: die in-situ-eDiscovery-&, in der die Exchange-Verwaltungskonsole Funktionen enthält, wird in den schreibgeschützten Modus versetzt. Dies bedeutet, dass Sie nur vorhandene suchen und Haltestatus entfernen können.

### <a name="alternative-tools"></a>Alternative Tools

In der folgenden Tabelle werden andere Tools beschrieben, die Sie zum Ersetzen der vorhandenen Funktionen verwenden können, die in den Ruhestand gehen.

<table>
<thead>
<tr class="header">
<th><strong>Funktionalität</strong></th>
<th><strong>Alternatives Tool</strong></th>
<th><strong>Comments</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Suchen, exportieren und speichern aus rechtlichen Gründen</td>
<td>Zentrale eDiscovery-Fälle im Microsoft 365 Compliance Center </td>
<td><p>Durch die Verwendung der Funktionen von zentralen eDiscovery-Fällen wird die funktionale Parität für Compliance-eDiscovery und in-Place-Speicher bereitgestellt. Dazu gehört Folgendes:</p>
<ul>
<li>
<p>Such Skalen an Millionen von Speicherorten</p>
</li>
<li>
<p>Höhere Zuverlässigkeit beim Suchen, exportieren und Platzieren von Inhalten in der Warteschleife</p>
</li>
<li>
<p>Suchen nach Inhalten in für Exchange Online, SharePoint Online, OneDrive für Unternehmen, Skype for Business, Microsoft Teams, Jammern von Gruppen, Office 365 Gruppen und anderen in Office 365 Anwendungen gespeicherten Inhalten</p></li></ul>
<p>Weitere Informationen finden Sie unter <a href="https://docs.microsoft.com/microsoft-365/compliance/manage-legal-investigations">Manage legal Investigations in Office 365</a>.</td>
</tr>
<tr class="even">
<td>Aufbewahrung für Aufbewahrungszwecke</td>
<td>Aufbewahrungsrichtlinien im Microsoft 365 Compliance Center</td>
<td><p>Sie können Aufbewahrungsrichtlinien verwenden, um Inhalte beizubehalten und, falls gewünscht, nach Ablauf des Aufbewahrungszeitraums zu löschen. Zu den weiteren Funktionen gehören:</p>
<ul>
<li>
<p>Anwenden von Richtlinien auf Ihre gesamte Organisation </p>
</li><li>
<p>Anwenden von Richtlinien auf bestimmte inhaltsspeicherorte wie Exchange Online, SharePoint Online, OneDrive für Unternehmen, Skype for Business, Microsoft Teams und Office 365 Gruppen</p></li>
<li>
<p>Anwenden von Richtlinien auf bestimmte Benutzer</p></li></ul>
<p>Weitere Informationen finden Sie unter <a href="https://docs.microsoft.com/microsoft-365/compliance/retention-policies">Übersicht über Aufbewahrungsrichtlinien</a>.</td>
</tr>
<tr class="odd">
<td>Kopieren von e-Mail-Suchergebnissen in ein Ermittlungspostfach zur Überarbeitung</td><td>Überprüfungs Sätze in Advanced eDiscovery v 2.0</td>
<td><p>Die Überprüfung von Inhalten in Microsoft 365 war noch nie so einfach. Überprüfungs Sätze weisen viele große Funktionen auf, um den Zeitaufwand und die erforderlichen Daten für die Überprüfung zu reduzieren, einschließlich:</p>
<ul>
<li><p>Ausführen schneller Suchabfragen und Filtern von Inhalten in einem Überprüfungs Satzes</p></li>
<li><p>Analysieren des Inhalts eines Überprüfungs Satzes; Dazu gehören e-Mail-Threading, Erkennung in mehrfacher Nähe, Design Analyse und Vorhersage Codierung.</p></li>
<li><p>Markieren von Dokumenten in einem Prüfdateisatz</p></li>
<li><p>Tagging von Vorschlägen zur Identifizierung von Rechtsanwalt-Client-Privileg-Inhalten</p></li></ul>
<p>Weitere Informationen finden Sie unter <a href="https://docs.microsoft.com/microsoft-365/compliance/overview-ediscovery-20">Übersicht über die Advanced eDiscovery-Lösung in Microsoft 365</a>.</p>
<p>
<p>Alternativ können Sie die Suchergebnisse in PST-Dateien exportieren und dann den Microsoft 365-Import Dienst verwenden, um das PST in ein Discovery-Postfach zu importieren. Eine Schritt-für-Schritt-Anleitung finden Sie unter <a href="https://docs.microsoft.com/microsoft-365/compliance/use-network-upload-to-import-pst-files">Verwenden des Netzwerk Uploads zum Importieren von PST-Dateien in Office 365</a>.
</tr>
<tr class=even>
  <td>Kopieren von Nachrichten von einem Postfach in ein anderes Postfach</td>
  <td><a href="https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-permissions-for-recipients">Zuweisen von Berechtigungen zu einem Postfach</a></td>
  <td>Wenn Sie einer Person Zugriff auf die e-Mail-Adresse eines anderen Benutzers gewähren möchten (beispielsweise wenn ein Mitarbeiter Ihre Organisation verlässt und einer anderen Person Zugriff auf die e-Mail-Adresse des ehemaligen Mitarbeiters geben muss), wird empfohlen, dass Sie dieser Person Berechtigungen für den Zugriff auf die früheren Mitarbeiter erteilen. Postfach. Anstatt also Postfachelemente in ein anderes Benutzerpostfach oder ein freigegebenes Postfach zu kopieren, weisen Sie einfach einen Benutzerberechtigungen für den Zugriff auf das Quellpostfach zu.</td>
  
  </tr>
<tr class="odd">
<td>Wiederherstellen von Elementen aus dem Ordner "Wiederherstellbare Elemente"</td>
  <td><a href="https://docs.microsoft.com/powershell/module/exchange/mailboxes/Restore-RecoverableItems">Restore-RecoverableItems</td>
  <td>Sie können endgültig gelöschte Elemente (auch als <i>vorläufig gelöschte</i> Elemente bezeichnet) in Postfächern wiederherstellen, solange der Aufbewahrungszeitraum für gelöschte Elemente für ein Element nicht abgelaufen ist. Weitere Informationen finden Sie unter <a href="https://docs.microsoft.com/Exchange/security-and-compliance/recoverable-items-folder/recoverable-items-folder">Ordner "refundable Items" in Exchange Online</a>.</td>
</tr>
</tbody>
</table>

### <a name="faqs-about-in-place-ediscovery-and-in-place-holds"></a>FAQs zu Compliance-eDiscovery und in-Place-Archiven

**Ich verwende die Funktion zum Kopieren von Suchergebnissen von in-Place-eDiscovery & in der Exchange-Verwaltungskonsole, um Suchergebnisse in ein Ermittlungspostfach zur Überprüfung durch Anwälte zu kopieren. Welche Optionen habe ich jetzt?**

Es gibt zwei Möglichkeiten, diese Funktionalität heute zu replizieren. Die erste besteht in der Verwendung [von Überprüfungs Sätzen in Advanced eDiscovery v 2.0](https://docs.microsoft.com/microsoft-365/compliance/view-documents-in-review-set). Überprüfungs Sätze weisen viele der gleichen Funktionen auf, die Sie in einem herkömmlichen Überprüfungstool wie fast search of Documents, Tagging, e-Mail-Threading, in der Nähe von doppelten Gruppierungen, Themen Analysen und Vorhersage Codierung sehen. Wenn Sie weiterhin Discovery-Postfächer für die Überprüfung verwenden möchten, besteht die zweite Option darin, Suchergebnisse in PST-Dateien zu exportieren und dann die PST-Dateien mithilfe der [PST-Importfunktion](use-network-upload-to-import-pst-files.md) im Microsoft Compliance Center in ein Discovery-Postfach zu importieren.

**Wie kann ich Steuern, welche inhaltsspeicherorte (wie Postfächer oder Websites), die ein eDiscovery-Manager verwenden können, mithilfe der neuen Tools suchen können?**

Das Microsoft 365 Compliance Center verwendet auch [Kompatibilitäts Grenzen](set-up-compliance-boundaries.md) , um zu steuern, welche inhaltsspeicherorte ein eDiscovery-Manager durchsuchen kann. Compliance-Grenzen sind in Regierungseinheiten nützlich, die innerhalb von Vermittlungs Grenzen oder multinationalen Unternehmen bleiben müssen, die für die Einhaltung geografischer Internats stellen erforderlich sind.

**Wie kann ich meine aktuellen Suchvorgänge und Haltestatus in das Microsoft 365 Compliance Center verlagern?**

Es ist möglich, in-Place-eDiscovery-suchen und-Aufbewahrungen mithilfe von PowerShell aus der Exchange-Verwaltungskonsole zu migrieren. Anweisungen finden Sie unter [Migrat searchs and Holds from the EAC to the Microsoft 365 Compliance Center](https://go.microsoft.com/fwlink/?linkid=2114224).

## <a name="-mailboxsearch-cmdlets"></a>\*-MailboxSearch-Cmdlets

Gemäß dem ursprünglichen Hinweis, der am 1. Juli 2017 in der Exchange-Verwaltungskonsole angekündigt wurde, werden die in-situ-eDiscovery-&-Funktionalität und die entsprechenden ** \*-MailboxSearch-** Cmdlets zurückgezogen. Mit diesen Cmdlets können Benutzer Postfachinhalte für rechtliche, regulatorische und öffentliche Anforderungen durchsuchen, speichern und exportieren.

Da diese Funktionen nun im [<span class="underline">Microsoft 365 Compliance Center</span>](https://docs.microsoft.com/microsoft-365/compliance/microsoft-365-compliance-center) und Office 365 Security & Compliance Center PowerShell mit verbesserter Leistung und Skalierbarkeit verfügbar sind, sollten Sie diese verbesserten Cmdlets verwenden. Zu diesen Cmdlets gehören [<span class="underline"> \*-ComplianceCase</span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-ediscovery/get-compliancecase), [<span class="underline"> \*-ComplianceSearch</span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/get-compliancesearch), [<span class="underline"> \*-CaseHoldPolicy</span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-ediscovery/get-caseholdpolicy), [<span class="underline"> \*-CaseHoldRule</span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-ediscovery/get-caseholdrule)und [<span class="underline"> \*-ComplianceSearchAction</span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/get-compliancesearchaction).

### <a name="scope-of-affected-organizations"></a>Umfang der betroffenen Organisationen

- Office 365-und Microsoft 365-Unternehmensorganisationen

- Office 365-und Microsoft 365-Bildungseinrichtungen

- Office 365-und Microsoft 365-Regierungsorganisationen; Dies umfasst gcc, gcc hoch und DoD.

- Office 365 Deutschland

### <a name="timeline"></a>Zeitachse

- 1. Juli 2020: Sie können **New-MailboxSearch** nicht zum Erstellen neuer Compliance-eDiscovery-suchen und in-Place-Speicher verwenden, aber Sie können Cmdlets zum Ausführen, bearbeiten und Löschen vorhandener Suchvorgänge und-Aufbewahrungen auf eigenes Risiko verwenden. Der Microsoft-Support bietet keine Unterstützung mehr für diese Art von Suche und Aufbewahrung.

- 1. Oktober 2020: wie bereits erwähnt, wird die in-situ-eDiscovery-&, in der die Exchange-Verwaltungskonsole Funktionen enthält, in den schreibgeschützten Modus versetzt. Das bedeutet auch, dass Sie die Cmdlets **New-MailboxSearch**, **Start-MailboxSearch**oder **setMailboxSearch** nicht verwenden können. Sie können nur vorhandene suchen und Aufbewahrungen abrufen und entfernen.

### <a name="alternative-tools"></a>Alternative Tools

In der folgenden Tabelle werden andere Tools beschrieben, die Sie zum Ersetzen der vorhandenen Funktionen verwenden können, die in den Ruhestand gehen.

<table>
<thead>
<tr class="header">
<th><strong>Funktionalität</strong></th>
<th><strong>Alternative Tools</strong></th>
<th><strong>Comments</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Suchen und exportieren</td>
<td><p><a href="https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/get-compliancesearch"><span class="underline">*-ComplianceSearch</span></a></p>
<p><a href="https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/get-compliancesearchaction"><span class="underline">*-ComplianceSearchAction</span></a></p>
<p><a href="https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-ediscovery/get-compliancecase"><span class="underline">*-ComplianceCase</span></a></p>
<p> </p></td>
<td><p>Die ComplianceSearch-und ComplianceSearchAction-Cmdlets arbeiten zusammen, um Sie beim Durchsuchen und Exportieren von Inhalten zu unterstützen. Sie können eine neue Suche erstellen und die geschätzte Suche anzeigen, indem Sie die Cmdlets <strong>New-</strong>, <strong>Get-</strong>und <strong>Start-ComplianceSearch</strong> verwenden. Anschließend können Sie das Cmdlet <strong>New-ComplianceSearchAction</strong> verwenden, um die Suchergebnisse zu exportieren. Sie müssen weiterhin das zentrale eDiscovery-Tool im Microsoft 365 Compliance Center verwenden, um diese Suchergebnisse auf Ihren lokalen Computer herunterzuladen.</p>
<p>
<p><strong>Hinweis:</strong> Wenn Sie diese Cmdlets zum Erstellen von Suchvorgängen verwenden, die nicht einem zentralen eDiscovery-Fall zugeordnet sind, befinden sich diese Suchvorgänge auf der Seite " <strong>Inhaltssuche</strong> " im Microsoft 365 Compliance Center.</p></td>
</tr>
<tr class="even">
<td>Speichern von Inhalten in einem Postfach</td>
<td><p><a href="https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-ediscovery/get-caseholdpolicy"><span class="underline">*-CaseHoldPolicy</span></a></p>
<p><a href="https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-ediscovery/get-caseholdrule"><span class="underline">*-CaseHoldRule</span></a></p>
<p><a href="https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-ediscovery/get-compliancecase"><span class="underline">*-ComplianceCase</span></a></p>
<p> </p></td>
<td><p>Haltestatus im Microsoft 365 Compliance Center müssen einem ComplianceCase zugeordnet sein. Erstellen Sie zuerst den Fall Compliance, und erstellen Sie dann eine CaseHoldPolicy und eine CaseHoldRule.</p>
<p><strong>Hinweis:</strong> Durch das Erstellen einer CaseHoldPolicy ohne Erstellungs-CaseHoldRule wird der Haltestatus so lange funktionsfähig gerendert, bis das CaseHoldRule erstellt und dem CaseHoldPolicy zugeordnet ist. Weitere Informationen finden Sie in der Cmdlet-Dokumentation.</p></td>
</tr>
<tr class="odd">
<td>Kopieren von Suchergebnissen in ein Ermittlungspostfach</td>
<td>Keine</td>
<td>Es gibt keinen direkten Ersatz für diese Funktionalität, da er keinen Zugriff auf alle Microsoft 365-Dienste bereitstellt. Unter den folgenden häufig gestellten Fragen finden Sie alternative Lösungen.</td>
</tr>
  <tr class=even>
  <td>Kopieren von Nachrichten von einem Postfach in ein anderes Postfach</td>
  <td><a href="https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-permissions-for-recipients">Zuweisen von Berechtigungen zu einem Postfach</a></td>
  <td>Wenn Sie einer Person Zugriff auf die e-Mail-Adresse eines anderen Benutzers gewähren möchten (beispielsweise wenn ein Mitarbeiter Ihre Organisation verlässt und einer anderen Person Zugriff auf die e-Mail-Adresse des ehemaligen Mitarbeiters geben muss), wird empfohlen, dass Sie dieser Person Berechtigungen für den Zugriff auf die früheren Mitarbeiter erteilen. Postfach. Anstatt also Postfachelemente in ein anderes Benutzerpostfach oder ein freigegebenes Postfach zu kopieren, weisen Sie einfach einen Benutzerberechtigungen für den Zugriff auf das Quellpostfach zu.</td>
  
  </tr>

</tbody>
</table>

### <a name="faqs-about--mailboxsearch-cmdlets"></a>FAQs zu ***-MailboxSearch-** Cmdlets

**Wir verwenden die Kopie-Suche zum Exportieren von e-Mail-Nachrichten oder Chatnachrichten für Zwecke anderer eDiscovery und rechtlicher Untersuchungen. Welche weiteren Optionen haben wir, nachdem diese Cmdlets ausgemustert wurden?**

Die [<span class="underline">Microsoft Graph-APIs</span>](https://developer.microsoft.com/en-us/graph) bieten eine Reihe von Methoden zum Extrahieren von Daten zur Analyse und anderen Zwecken, die weitaus widerstandsfähiger und skalierbarer als die Verwendung der ** \*-MailboxSearch-** Cmdlets sind.

**Wie kann ich meine suchen und Haltestatus an das Microsoft 365 Compliance Center migrieren?**

Es ist möglich, in-Place-eDiscovery-suchen und-Aufbewahrungen über das Exchange Admin Center mithilfe eines PowerShell-Skripts zu migrieren. Weitere Informationen finden Sie unter [Migrieren von Vorversionen für eDiscovery-suchen und-Aufbewahrungen zum Microsoft 365 Compliance Center](migrate-legacy-eDiscovery-searches-and-holds.md).

**Kann ich nach dem zurückziehen der Cmdlets Suchvorgänge dennoch entfernen oder Abrufen?**

Ja, obwohl wir die Möglichkeit zum Erstellen und Ändern von Suchvorgängen entfernen, können Sie immer noch **Get-MailboxSearch** und **Remove-MailboxSearch** verwenden, bis es auf weiteres geht. Die Verwendung dieser Cmdlets erfolgt jedoch auf eigenes Risiko, nachdem die Renten Termine und der Microsoft-Support keine Unterstützung mehr leisten können.

## <a name="search-mailbox-cmdlet"></a>Cmdlet "Search-Mailbox"

Das Cmdlet **Search-Mailbox** in Exchange Online PowerShell wird wie ursprünglich in einer Warnung in der Cmdlet-Ausgabe beginnend mit 2018 angekündigt zurückgezogen. Das Cmdlet **Search-Mailbox** wurde ursprünglich verwendet, um das Postfach eines Benutzers zu durchsuchen und schädlichen Inhalt zu löschen. Es wird empfohlen, dass Sie zunächst die Cmdlets **New-ComplianceSearch** und **New-ComplianceSearchAction** in Office 365 Security & Compliance Center PowerShell verwenden, um Inhalte zu suchen und zu löschen. Für eine integrierte Sicherheitserfahrung bieten die [<span class="underline">Microsoft 365-Sicherheitsfeatures</span>](https://docs.microsoft.com/microsoft-365/security/) zuverlässigen Schutz vor Bedrohungen für e-Mails und viele andere Microsoft-Dienste.

### <a name="scope-of-affected-organizations"></a>Umfang der betroffenen Organisationen

- Office 365-und Microsoft 365-Unternehmensorganisationen

- Office 365-und Microsoft 365-Bildungseinrichtungen

- Office 365-und Microsoft 365-Regierungsorganisationen; Dies umfasst gcc, gcc hoch und DoD.

- Office 365 Deutschland

### <a name="timeline"></a>Zeitachse

-  1. Juli 2020: das Cmdlet **Search-Mailbox** ist nicht mehr verfügbar, und der Microsoft-Support bietet keine Unterstützung mehr.

### <a name="alternative-tools"></a>Alternative Tools

In der folgenden Tabelle werden andere Tools beschrieben, die Sie zum Ersetzen der vorhandenen Funktionen verwenden können, die in den Ruhestand gehen.

<table>
<thead>
<tr class="header">
<th><strong>Funktionalität</strong></th>
<th><strong>Alternative Tools</strong></th>
<th><strong>Comments</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Durchsuchen eines Postfachs</td>
<td><p><a href="https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/get-compliancesearch?view=exchange-ps"><span class="underline">*-ComplianceSearch</span></a></p>
<p><a href="https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/get-compliancesearchaction?view=exchange-ps"><span class="underline">*-ComplianceSearchAction</span></a></p>
<p></a></p></td>
<td><p>Die ComplianceSearch-und ComplianceSearchAction-Cmdlets arbeiten zusammen, um Sie beim Durchsuchen und Exportieren von Inhalten zu unterstützen. Sie können eine neue Suche erstellen und die geschätzte Suche anzeigen, indem Sie die Cmdlets <strong>New-</strong>, <strong>Get-</strong>und <strong>Start-ComplianceSearch</strong> verwenden. Anschließend können Sie den Befehl <strong>New-ComplianceSearchAction-Export</strong> verwenden, um die Suchergebnisse zu exportieren. Sie müssen weiterhin das zentrale eDiscovery-Tool im Microsoft 365 Compliance Center verwenden, um diese Suchergebnisse auf Ihren lokalen Computer herunterzuladen.</p></p>
</td>
</tr>
<tr class="even">
<td>Nachrichten aus einem Postfach löschen</td>
<td><p><a href="https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/get-compliancesearch?view=exchange-ps"><span class="underline">*-ComplianceSearch</span></a></p>
<p><a href="https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/get-compliancesearchaction?view=exchange-ps"><span class="underline">*-ComplianceSearchAction</span></a></p>
<p></p></td>
<td><p>Die ComplianceSearch-und ComplianceSearchAction-Cmdlets arbeiten zusammen, um Sie beim Durchsuchen und Löschen von Inhalten zu unterstützen. Sie können eine Suche mit <strong>New-ComplianceSearch</strong> -und <strong>New-ComplianceSearch</strong> -Cmdlets erstellen und ausführen, und dann können Sie den Inhalt mithilfe des Befehls <strong>New-ComplianceSearchAction-Purge-purgetype</strong> löschen. Weitere Informationen finden Sie unter <a href="https://docs.microsoft.com/microsoft-365/compliance/search-for-and-delete-messages-in-your-organization"><span class="underline">Suchen nach und Löschen von Nachrichten</span></a>.</p>
</td>
</tr>
<tr class="odd">
<td>Löschen von Massen-e-Mails aus einem Postfach</td>
<td><p><a href="https://docs.microsoft.com/microsoft-365/compliance/set-up-an-archive-and-deletion-policy-for-mailboxes?view=o365-worldwide"><span class="underline">Einrichten einer Richtlinie zum Archivieren und Löschen für Postfächer</span></a></p>
<p></p></td>
<td><p>Administratoren können eine Archivierungs-und Löschrichtlinie erstellen, die Elemente automatisch in das Archivpostfach eines Benutzers verschiebt und Elemente automatisch aus dem Postfach löscht.</p>
</td>
</tr>
<tr class="even">
<td>Kopieren von Suchergebnissen in ein Ermittlungspostfach</td>
<td> </td>
<td>Es gibt keinen direkten Ersatz für diese Funktionalität, da er keinen Zugriff auf alle Microsoft 365-Dienste bereitstellt. In den FAQs im Abschnitt <strong>*-MailboxSearch-Cmdlets</strong> finden Sie alternative Lösungen. </td>
</tr>
</tbody>
</table>

## <a name="exchange-web-services-api-operations"></a>Exchange Webdienste-API-Vorgänge

Diese Vorgänge in der Exchange Webdienste-API werden von der Funktion in-Place-eDiscovery-& in der Exchange-Verwaltungskonsole und den entsprechenden ** \*-MailboxSearch-** Cmdlets in Exchange Online PowerShell verwendet. Sie werden auch im Rahmen des Ausscheidens der anderen vorversions-eDiscovery-Tools in den Ruhestand gehen.

### <a name="scope-of-affected-organizations"></a>Umfang der betroffenen Organisationen

- Office 365-und Microsoft 365-Unternehmensorganisationen

- Office 365-und Microsoft 365-Bildungseinrichtungen

- Office 365-und Microsoft 365-Regierungsorganisationen; Dies umfasst gcc, gcc hoch und DoD.

- Office 365 Deutschland

### <a name="timeline"></a>Zeitachse

- 1. Juli 2020: die GetSearchableMailboxes-, SearchMailboxes-, SetHoldOnMailboxes-und GetHoldOnMailboxes-Vorgänge sind nicht mehr verfügbar, und der Microsoft-Support bietet keine Unterstützung mehr.

## <a name="advanced-ediscovery-v10"></a>Erweiterte eDiscovery v 1.0

Advanced eDiscovery v 1.0, bei dem es sich um die Version von Advanced eDiscovery handelt, die in einem eDiscovery-Fall verfügbar ist, indem **Sie auf zu Advanced eDiscovery wechseln** , wird zurückgezogen. Die Funktionalität wurde durch die neue [Erweiterte eDiscovery-Lösung](https://aka.ms/edisco) im Microsoft 365 Compliance Center ersetzt.

Die neue erweiterte eDiscovery-Lösung in Microsoft 365 (auch bekannt als *Advanced eDiscovery v 2.0*genannt) bietet alle Funktionen der ursprünglichen Lösung, enthält jetzt jedoch einen Verwalter basierten Ansatz zum Identifizieren von Inhalten in anderen Microsoft 365-Diensten, zum Sammeln dieser Inhalte und zum Hinzufügen eines Überprüfungs Satzes, in dem Bearbeiter schnelle Suchabfragen, Tagging und Analysefunktionen nutzen können, um die relevanten Dokumente zu ermitteln. Advanced eDiscovery enthält jetzt eine verbesserte Verarbeitung und Native Viewer für Microsoft-und nicht-Microsoft-Dateitypen, eine vollständige Liste der Dateitypen ist [hier](https://docs.microsoft.com/microsoft-365/compliance/supported-filetypes-ediscovery20) und unterstützte Metadatenfelder befinden sich [hier](https://docs.microsoft.com/microsoft-365/compliance/document-metadata-fields-in-advanced-ediscovery). Darüber hinaus bietet die neue erweiterte eDiscovery-Lösung eine leistungsstarke Depot Verwaltungsfunktion, mit der Sie in einem erweiterten eDiscovery-Fall auf Inhalte in verschiedenen Diensten eintragen, Benutzer über die Aufbewahrungspflicht Benachrichtigen und Depotbank-Antworten nachverfolgen können.

Zu diesem Zeitpunkt wird empfohlen, dass Sie mit dem Übergang Ihres eDiscovery-Workflows zur neuen erweiterten eDiscovery-Funktionalität beginnen. Obwohl Sie weiterhin in den vorhandenen Fällen auf Advanced eDiscovery v 1.0 zugreifen können, bietet der Microsoft-Support nach dem 1. Oktober 2020 keine Unterstützung. Weitere Informationen finden Sie in der folgenden Zeitachse.

### <a name="scope-of-affected-organizations"></a>Umfang der betroffenen Organisationen
    
- Office 365-und Microsoft 365-Unternehmensorganisationen

- Office 365-und Microsoft 365-Bildungseinrichtungen

- Office 365 Deutschland

### <a name="timeline"></a>Zeitachse

- 1. Juli 2020: Es ist nicht möglich, neue erweiterte eDiscovery v 1.0-Fälle zu erstellen.

- 1. Oktober 2020: Sie können keine neuen Daten hinzufügen (Suchergebnisse für erweiterte eDiscovery) auf alle Fälle vorbereiten. Sie können die Datenverarbeitung in vorhandenen Fällen auf eigenes Risiko fortsetzen. Der Microsoft-Support kann keine Unterstützung mehr leisten. 

### <a name="alternative-tools"></a>Alternative Tools

Die [Erweiterte eDiscovery-Lösung](https://docs.microsoft.com/microsoft-365/compliance/overview-ediscovery-20) im Microsoft 365 Compliance Center.
