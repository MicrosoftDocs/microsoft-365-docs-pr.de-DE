---
title: Entwerfen eines Klassifikationsschemas für personenbezogene Daten
ms.author: bcarter
author: brendacarter
manager: laurawi
audience: ITPro
ms.topic: overview
ms.collection:
- Strat_O365_Enterprise
- Ent_O365
- GDPR
- M365-security-compliance
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
description: Ermitteln Sie, ob Ihre Organisation als Teil des DSGVO-Plans Bezeichnungen implementiert.
ms.openlocfilehash: 4470f766ad2f8fd2d914e0e45deac8604028ddb5
ms.sourcegitcommit: 7f26840a4330b0fd29807ec091c6915d283b3dd2
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2019
ms.locfileid: "39615645"
---
# <a name="architect-a-classification-schema-for-personal-data"></a>Entwerfen eines Klassifikationsschemas für personenbezogene Daten

Vorherige Artikel dieser Reihe konzentrieren sich auf die Verwendung vertraulicher Informationstypen zum Identifizieren personenbezogener Daten, die der DSGVO unterliegen. Vertrauliche Informationstypen sind eine Form der Klassifizierung. Dies ist möglicherweise die einzige Klassifizierung, die Sie benötigen. Viele Organisationen implementieren jedoch mithilfe von Bezeichnungen eine umfassendere Strategie für die Datenkontrolle. Anhand dieses Themas können Sie entscheiden, ob Sie auch im Rahmen Ihres DSGVO-Plans Bezeichnungen implementieren möchten. Wenn Sie sich dazu entscheiden, beinhaltet dieses Thema einige Anleitungen und Beispiele hierzu.

Hinweis: Die Definition eines Klassifikationsschemas für eine Organisation und die Konfiguration von Richtlinien, Bezeichnungen und Bedingungen erfordert sorgfältige Planung und Vorbereitung. Es ist wichtig zu erkennen, dass dies kein von der IT gesteuerter Prozess ist. Arbeiten Sie unbedingt mit Ihrer Rechts- und Complianceabteilung zusammen, um ein geeignetes Klassifikations- und Bezeichnungsschema für die Daten Ihrer Organisation zu entwickeln.

## <a name="decide-if-youre-using-labels-in-addition-to-sensitive-data-types"></a>Entscheiden, ob Bezeichnungen neben vertraulichen Informationstypen verwendet werden sollen

Sie können einen der beiden Ansätze für die Klassifikation personenbezogener Informationen in Office 365 verwenden. Jeder Ansatz kann für Schutz für die DSGVO verwendet werden. Wenn Sie nur vertrauliche Informationstypen für die Klassifikation verwenden möchten, können Sie den Rest dieses Themas überspringen.

Wählen Sie eine der folgenden Optionen.

### <a name="option-1-use-only-office-365-sensitive-information-types"></a>Option 1: Ausschließliches Verwenden vertraulicher Informationstypen in Office 365

- Vertrauliche Informationstypen sind gut zum Identifizieren und Schutz personenbezogener Daten geeignet, die der DSGVO und anderen Vorschriften unterliegen.

- Diese sind einfacher zu verwenden, wenn Ihre Organisation nicht bereits einen umfassenden Plan für die Datenkontrolle mithilfe von Bezeichnungen hat bzw. plant.

- Sie können mit DLP-Regeln verwendet werden (genauso wie Aufbewahrungsbezeichnungen).

- Typen vertraulicher Informationen können auch mit Cloud App Security verwendet werden, sodass Sie vertrauliche Informationen in anderen SaaS-Apps erkennen können.

### <a name="option-2-use-sensitive-information-types--retention-labels"></a>Option 2: Verwenden von vertraulichen Informationstypen und Aufbewahrungsbezeichnungen

- Sie benötigen vertrauliche Informationstypen, um Bezeichnungen automatisch auf personenbezogene Daten anzuwenden, die der DSGVO unterliegen, diese sind somit eine Voraussetzung.

- Mit Aufbewahrungsbezeichnungen können Sie personenbezogene Daten, die der DSGVO unterliegen, in einen umfassenderen Plan für die Datenkontrolle für Ihre Organisation implementieren.

## <a name="develop-a-label-schema-that-includes-personal-data"></a>Entwickeln eines Bezeichnungsschemas, das personenbezogene Daten enthält

Bevor Sie die technischen Funktionen zum Anwenden von Bezeichnungen und des Schutzes verwenden können, müssen Sie ein Klassifikationsschema für Ihre Organisation definieren. Ihre Organisation verfügt möglicherweise bereits über ein Klassifikationsschema, was Ihnen das Hinzufügen personenbezogener Daten erleichtert. Dieses Thema enthält ein Beispiel für ein Klassifikationsschema. Sie können dieses Beispiel bei Bedarf als Ausgangspunkt verwenden.

### <a name="getting-started"></a>Erste Schritte

Entscheiden Sie zunächst über die Anzahl und die Namen von Bezeichnungen, die Sie implementieren möchten. Machen Sie sich zu diesem Zeitpunkt keine Gedanken darüber, welche Technologie verwendet und wie Bezeichnungen angewendet werden sollen. Wenden Sie dieses Schema universell innerhalb der gesamten Organisation an, darunter Daten, die lokal und in anderen Clouddiensten gespeichert sind.

### <a name="recommendations"></a>Empfehlungen 

Berücksichtigen Sie beim Entwerfen und Implementieren von Richtlinien, Bezeichnungen und Bedingungen die folgenden Empfehlungen:

- Verwenden Sie ein vorhandenes Klassifikationsschema (sofern vorhanden) &ndash; Viele Organisationen verwenden bereits eine Datenklassifizierung in irgendeiner Form. Werten Sie sorgfältig das vorhandene Bezeichnungsschema aus, und verwenden Sie es nach Möglichkeit unverändert. Vertraute Bezeichnungen, die für den Endbenutzer erkennbar sind, sorgen für größere Akzeptanz.

- Beginnen Sie mit Standardrichtlinien und -bezeichnungen &ndash; Alle Lösungen enthalten eine Reihe vordefinierter Richtlinien und Bezeichnungen. Werten Sie diese sorgfältig anhand der rechtlichen und geschäftlichen Anforderungen der Organisation aus, und ziehen Sie es in Erwägung, diese zu verwenden, anstatt neue zu erstellen.

- Beginnen Sie klein &ndash; Es gibt nahezu keine Beschränkung, was die Anzahl der Bezeichnungen angeht, die erstellt werden können. Viele Bezeichnungen und Unterbezeichnungen wirken sich jedoch negativ auf die Akzeptanz aus. Zu viele Auswahlmöglichkeiten bedeuten häufig überhaupt keine Auswahl.

- Verwenden Sie Szenarien und Anwendungsfälle &ndash; Identifizieren Sie allgemeine Anwendungsfälle innerhalb der Organisation, und verwenden Sie Szenarien, die von der DSGVO abgeleitet sind, um zu prüfen, ob die vorgesehene Bezeichnungs- und Klassifikationskonfiguration in der Praxis funktionieren.

- Stellen Sie jede Anforderung für eine neue Bezeichnung in Frage &ndash; Ist für jedes Szenario oder jeden Anwendungsfall wirklich eine neue Bezeichnung erforderlich, oder kann hierfür eine bereits vorhandene Bezeichnung verwendet werden? Eine minimale Anzahl von Bezeichnungen verbessert die Akzeptanz.

- Verwenden Sie Unterbezeichnungen für wichtige Abteilungen &ndash; Für einige Abteilungen sind spezielle Bezeichnungen erforderlich. Definieren Sie diese Bezeichnungen als Unterbezeichnungen für vorhandene Bezeichnungen, und ziehen Sie es in Erwägung, bereichsbezogene Richtlinien zu verwenden, die einer Benutzergruppe zugewiesen sind, anstelle von globalen Richtlinien.

- Ziehen Sie die Verwendung von bereichsbezogenen Richtlinien in Erwägung &ndash; Richtlinien, die auf eine Teilmenge von Benutzern abzielen, verhindern zu viele Bezeichnungen. Mit einer bereichsbezogenen Richtlinie können Sie rollen- oder abteilungsspezifische (Unter-)Bezeichnungen nur Mitarbeitern zuweisen, die für diese Abteilung arbeiten.

- Verwenden Sie aussagekräftige Namen &ndash; Es wird empfohlen, Jargon, Standards oder Akronyme nicht als Bezeichnungsnamen zu verwenden. Verwenden Sie Namen, die hohe Akzeptanz bei Endbenutzern finden. Verwenden Sie statt Bezeichnungen wie PII, PCI, HIPAA, LBI, MBI und HBI Namen wie „Privat“, „Öffentlich“, „Allgemein“, „Vertraulich“ und „Streng vertraulich“.

### <a name="example-classification-schema"></a>Beispiel für ein Klassifikationsschema

<table>
<thead>
<tr class="header">
<th align="left"><strong>Bezeichnungsname</strong></th>
<th align="left"><strong>Beschreibung</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left">Privat</td>
<td align="left">Nicht geschäftliche Daten, nur für private Verwendung.</td>
</tr>
<tr class="even">
<td align="left">Öffentlich</td>
<td align="left">Geschäftsdaten, die speziell für die öffentliche Nutzung vorbereitet und genehmigt sind.</td>
</tr>
<tr class="odd">
<td align="left">Kundendaten</td>
<td align="left">Geschäftsdaten, die personenbezogene Informationen enthalten. Beispiele sind Kreditkartennummern, Bankkontonummern und Sozialversicherungsnummern.</td>
</tr>
<tr class="even">
<td align="left">Personaldaten</td>
<td align="left">Personaldaten über Contoso-Mitarbeiter, z. B. Mitarbeiternummer und Gehalt.</td>
</tr>
<tr class="odd">
<td align="left">Vertraulich</td>
<td align="left">Vertrauliche Geschäftsdaten, die dem Unternehmen schaden können, wenn sie an nicht autorisierte Personen weitergegeben werden. Beispiele hierfür sind Verträge, Sicherheitsberichte, Prognosen und Vertriebsdaten.</td>
</tr>
<tr class="even">
<td align="left">Streng vertraulich</td>
<td align="left">Streng vertrauliche Geschäftsdaten, die dem Unternehmen schaden, wenn sie an nicht autorisierte Personen weitergegeben werden. Beispiele hierfür sind Mitarbeiter- und Kundeninformationen, Kennwörter, Quellcode und vorangekündigte Finanzberichte.</td>
</tr>
</tbody>
</table>

## <a name="define-a-taxonomy-and-search-criteria-for-each-label"></a>Definieren von Taxonomie und Suchkriterien für jede Bezeichnung

Nachdem Sie ein Klassifikationsschema für Ihre Organisation entwickelt haben, besteht der nächste Schritt darin, die Taxonomie und Suchkriterien für die Suche nach diesen Daten zu entwickeln. Für personenbezogene Daten haben Sie diese Arbeit durch das Identifizieren von vertraulichen Informationstypen sowie durch Anpassen oder Erstellen neuer vertraulicher Informationstypen für Ihre Umgebung bereits abgeschlossen.

Die folgende Tabelle enthält Beispiele für Schema, Taxonomie und Suchkriterien für eine Organisation. Die Bezeichnungen sind nach Vertraulichkeitsstufe von am wenigsten vertraulich bis streng vertraulich sortiert, um sicherzustellen, dass Daten, die mehreren Bezeichnungsbedingungen entsprechen, der entsprechenden Bezeichnung zugewiesen sind.

Hinweis: Das Konfigurationsbeispiel dient nur der Veranschaulichung und stellt keine Bereitstellungsanleitung oder Referenz dar.

Die wichtige Schlussfolgerung besteht darin, sicherzustellen, dass die Arbeit, die Sie in die Klassifizierung personenbezogener Daten für die Einhaltung der DSGVO stecken, zu den Zielen für Ihre gesamte Organisation passt.

### <a name="example-schema-taxonomy-and-search-criteria"></a>Beispiele für Schema, Taxonomie und Suchkriterien

<table>
<thead>
<tr class="header">
<th align="left"><strong>Bezeichnung</strong></th>
<th align="left"><strong>Taxonomie</strong></th>
<th align="left"><strong>Methode</strong></th>
<th align="left"><strong>Suchsyntax</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left">Privat</td>
<td align="left">Manuell vom Endbenutzer als „Privat“ gekennzeichnete Dokumente.</td>
<td align="left">Manuell</td>
<td align="left">Manuell vom Endbenutzer als „Privat“ gekennzeichnete Dokumente.</td>
</tr>
<tr class="even">
<td align="left">Öffentlich</td>
<td align="left">Dokumente, die den Ausdruck „Approved for Public Release  ##/###“ (Genehmigt für öffentliche Freigabe ##/###) enthalten, wobei # eine beliebige Ziffer darstellt. Dabei wird Groß- und Kleinschreibung nicht beachtet.</td>
<td align="left"><p>KQL</p>
<p>RegEx</p></td>
<td align="left"><p>KQL — Approved for Public Release*</p>
<p>RegEx – (?i)(\bApproved for Public Release \d{2}\/\d{4}\b)</p></td>
</tr>
<tr class="odd">
<td align="left">Kundendaten</td>
<td align="left">Typen vertraulicher Informationen für Daten von EU-Bürgern.</td>
<td align="left">Typen vertraulicher Informationen</td>
<td align="left"></td>
</tr>
<tr class="even">
<td align="left">Personaldaten – Mitarbeiterdaten</td>
<td align="left">Dokumente, die die Mitarbeiter-ID, ohne Berücksichtigung der Kleinschreibung, im Format CONTOSO-9##### enthalten, wobei # eine beliebige Ziffer darstellt.</td>
<td align="left"><p>KQL</p>
<p>RegEx</p></td>
<td align="left"><p>KQL — CONTOSO-9*</p>
<p>RegEx – (\bCONTOSO-9\d{5}\b)</p></td>
</tr>
<tr class="odd">
<td align="left">Personaldaten – Gehaltsdaten</td>
<td align="left">Dokumente, die das Schlüsselwort (ohne Berücksichtigung der Groß-und Kleinschreibung) Contoso UND entweder das Schlüsselwort „Salary“ (Gehalt) (ohne Berücksichtigung der Groß-und Kleinschreibung) ODER „Compensation“ (Entgelt) enthalten</td>
<td align="left"><p>KQL</p>
<p>RegEx</p></td>
<td align="left"><p>KQL — Contoso AND (Salary OR Compensation)</p>
<p>RegEx – (\bCONTOSO-9\d{5}\b)</p></td>
</tr>
<tr class="even">
<td align="left">Vertraulich</td>
<td align="left">Dokumente, die den Ausdruck „Contoso Confidential“ (Contoso Vertraulich) (ohne Berücksichtigung der Groß-und Kleinschreibung) enthalten.</td>
<td align="left"><p>KQL</p>
<p>RegEx</p></td>
<td align="left"><p>KQL — Contoso Confidential</p>
<p>RegEx — (?i)(\bContoso Confidential\b)</p></td>
</tr>
<tr class="odd">
<td align="left">Streng vertraulich</td>
<td align="left">Dokumente, die entweder den Ausdruck „Contoso Secret“ (Contoso Geheimnis) oder „Secret-C####“ (Geheimnis-C####) (ohne Berücksichtigung der Groß-/Kleinschreibung) enthalten, wobei # eine beliebige Ziffer darstellt.</td>
<td align="left"><p>KQL</p>
<p>RegEx</p></td>
<td align="left"><p>KQL — Contoso Secret OR Secret-C*</p>
<p>RegEx – (?i)(\bContoso Secret\b)|(\bSecret-C\d{4}\b)</p></td>
</tr>
</tbody>
</table>
