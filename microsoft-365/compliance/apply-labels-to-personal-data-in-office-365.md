---
title: Anwenden von Bezeichnungen auf personenbezogene Daten
f1.keywords:
- NOCSH
ms.author: bcarter
author: brendacarter
manager: laurawi
audience: ITPro
ms.topic: overview
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- GDPR
- M365-security-compliance
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
description: Erfahren Sie, wie Sie Office-Bezeichnungen im Rahmen Ihres DSGVO- (Datenschutz-Grundverordnung) Schutzplans verwenden können.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: a7bea2abeaec7a858b3cfc693603c46c0f2a416a
ms.sourcegitcommit: e8b9a4f18330bc09f665aa941f1286436057eb28
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/14/2020
ms.locfileid: "45126816"
---
# <a name="apply-labels-to-personal-data"></a>Anwenden von Bezeichnungen auf personenbezogene Daten

 Verwenden Sie dieses Thema, wenn Sie im Rahmen Ihres DSGVO-Schutzplans Klassifizierungsbezeichnungen verwenden. 

Wenn Sie Bezeichnungen zum Schutz persönlicher Daten in Microsoft 365 verwenden, empfiehlt Microsoft, mit [Aufbewahrungsbezeichnungen](retention.md#retention-labels) zu beginnen. Mit Aufbewahrungsbezeichnungen können Sie Folgendes:
- Verwenden Sie die Erweiterte Datenkontrolle, um Bezeichnungen automatisch auf vertrauliche Informationstypen oder andere Kriterien anzuwenden.
- Verwenden Sie Aufbewahrungsbezeichnungen mit der Verhinderung von Datenverlust, um einen Schutz anzuwenden. 
- Verwenden Sie Bezeichnungen mit eDiscovery und der Inhaltssuche. 

Cloud App Security unterstützt derzeit keine Aufbewahrungsbezeichnungen, aber Sie können Microsoft 365-Typen für vertrauliche Informationen mit Cloud App Security verwenden, um personenbezogene Daten zu überwachen, die in anderen SaaS-Apps gespeichert sind.

[Vertraulichkeitsbezeichnungen](sensitivity-labels.md) werden derzeit empfohlen, um Bezeichnungen auf lokale Dateien und Dateien in anderen Cloud-Diensten und bei anderen Anbietern anzuwenden. Sie werden ebenfalls empfohlen für Dateien in Microsoft 365, die für den Datenschutz eine Azure Informationen Protection-Verschlüsselung benötigen, wie z. B. Dateien mit Betriebsgeheimnissen.

Zu diesem Zeitpunkt wird die Verwendung der Azure Information Protection-Verschlüsselung nicht für Dateien in Microsoft 365 empfohlen, die der DSGVO unterliegen. Microsoft 365-Dienste können derzeit keine AIP-verschlüsselten Dateien lesen. Aus diesem Grund findet der Dienst keine vertraulichen Daten in diesen Dateien.

Aufbewahrungsbezeichnungen können in Exchange Online auf E-Mail-Nachrichten angewendet werden, und diese Bezeichnungen verwenden den Schutz vor Datenverlust von Microsoft 365. 

![Bezeichnungen in Microsoft 365 und Azure Information Protection](../media/Apply-labels-to-personal-data-in-Office-365-image1.png)


In der Abbildung sehen Sie Folgendes:

-   Verwenden von Aufbewahrungsbezeichnungen für personenbezogene Daten und streng geregelte Dateien sowie Dateien mit Betriebsgeheimnissen in SharePoint Online und OneDrive for Business.
-   Sie können Microsoft 365-Typen für vertrauliche Informationen in Microsoft 365 und mit Cloud App Security verwenden, um personenbezogene Daten zu überwachen, die in anderen SaaS-Apps gespeichert sind.
-   Verwenden von Vertraulichkeitsbezeichnungen für streng geregelte Dateien sowie Dateien mit Betriebsgeheimnissen, Exchange Online-E-Mails, Dateien in anderen SaaS-Diensten, Dateien in lokalen Rechenzentren und Dateien in anderen Cloudanbietern.


## <a name="use-retention-labels-and-sensitive-information-types-across-microsoft-365-for-information-protection"></a>Verwenden von Aufbewahrungsbezeichnungen und vertraulichen Informationstypen in Microsoft 365 zum Schutz von Informationen

Die folgende Abbildung zeigt, wie Aufbewahrungsbezeichnungen und vertrauliche Informationstypen in Bezeichnungsrichtlinien, DLP-Richtlinien und mit Cloud App Security-Richtlinien verwendet werden können.

![Office-Bezeichnungen und vertrauliche Informationstypen](../media/Apply-labels-to-personal-data-in-Office-365-image2.png)

Für Zwecke der Barrierefreiheit enthält die folgende Tabelle die gleichen Beispiele wie die Abbildung.

<table>
<thead>
<tr class="header">
<th align="left"><strong>Klassifikationselemente</strong></th>
<th align="left"><strong>Bezeichnungsrichtlinien – 2 Beispiele</strong></th>
<th align="left"><strong>DLP-Richtlinien – 2 Beispiele</strong></th>
<th align="left"><strong>Cloud App Security-Richtlinien für alle SaaS-Apps – 1 Beispiel</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left">Aufbewahrungsbezeichnungen Beispiele: „Privat“, „Öffentlich“, „Kundendaten“, „Personaldaten“, „Vertraulich“, „Streng vertraulich“</td>
<td align="left"><p>Auto apply this label . . .</p>
<p>Kundendaten</p>
<p>. . . to documents that match these sensitive information types . . .</p>
<p>&lt;Liste der Beispiele für vertrauliche Informationstypen&gt;</p></td>
<td align="left"><p>Apply this protection . . .</p>
<p>&lt;Schutz definieren&gt;</p>
<p>. . . to documents with this label . . .</p>
<p>Kundendaten</p></td>
<td align="left"><p>Alert when files with these attributes . . .</p>
<p>Wählen Sie ein oder mehrere Attribute aus: vordefiniertes PII-Attribut, Microsoft 365-Typ für vertrauliche Informationen, Vertraulichkeitsbezeichnung (AIP), benutzerdefinierter Ausdruck</p>
<p>. . . in einer beliebigen genehmigten SaaS-App außerhalb der Organisation freigegeben werden</p><p>Hinweis: Aufbewahrungsbezeichnungen werden derzeit in Cloud App Security nicht unterstützt.</td>
</tr>
<tr class="even">
<td align="left">Sensitive information types. Examples: Belgium National Number, Credit Card Number, Croatia Identity Cart Number, Finland National ID</td>
<td align="left"><p>Publish these labels for users to manually apply . . .</p>
<p>&lt;Bezeichnungen wählen&gt;</p>
<p>. . . to these locations . . .</p>
<p>&lt;alle Speicherorte oder bestimmte Speicherorte wählen&gt;</p></td>
<td align="left"><p>Apply this protection . . .</p>
<p>&lt;Schutz definieren&gt;</p>
<p>. . . to documents that match these sensitive information types&gt;</p></td>
<td align="left"></td>
</tr>
</tbody>
</table>

## <a name="prioritize-auto-apply-label-policies"></a>Priorisieren automatisch angewendeter Bezeichnungsrichtlinien

For personal data that is subject to GDPR, Microsoft recommends auto-applying labels by using the sensitive information types you curated for your environment. It is important that auto-apply label policies are well designed and tested to ensure the intended behavior occurs.

The order that auto-apply policies are created and whether users are also applying these labels affect the result. So, it's important to carefully plan the roll-out. Here's what you need to know.

### <a name="one-label-at-a-time"></a>Jeweils nur eine Bezeichnung

Sie können einem Dokument jeweils nur eine Bezeichnung zuweisen.

### <a name="older-auto-apply-policies-win"></a>Ältere automatisch anzuwendende Richtlinien gelten zuerst

If there are multiple rules that assign an auto-apply label and content meets the conditions of multiple rules, the label for the oldest rule is assigned. For this reason, it's important to plan the label policies carefully before configuring them. If an organization requires a change to the priority of the label policies, they'll need to delete and recreate them.

### <a name="manual-user-applied-labels-trump-auto-applied-labels"></a>Manuell von Benutzern angewendete Bezeichnungen sind wichtiger als automatisch angewendete Bezeichnungen

Manual user applied labels trump auto-applied labels. Auto-apply policies can't replace a label that is already applied by a user. Users can replace labels that are auto-applied.

### <a name="auto-assigned-labels-can-be-updated"></a>Automatisch zugewiesene Bezeichnungen können aktualisiert werden

Automatisch zugewiesene Bezeichnungen können entweder durch neuere Bezeichnungsrichtlinien oder durch Aktualisierungen vorhandener Richtlinien aktualisiert werden.

Achten Sie darauf, dass Ihr Plan für die Implementierung von Bezeichnungen Folgendes umfasst:

- Priorisieren der Reihenfolge, in der automatisch angewendete Richtlinien erstellt werden.

- Allowing enough time for labels to be automatically applied before rolling these out for users to manually apply. It can take up to seven days for the labels to be applied to all content that matches the conditions.

### <a name="example-priority-for-creating-the-auto-apply-policies"></a>Beispiel für Priorität für das Erstellen von automatisch angewendeten Richtlinien

<table>
<thead>
<tr class="header">
<th align="left"><strong>Bezeichnungen</strong></th>
<th align="left"><strong>Prioritätsreihenfolge beim Erstellen von automatisch angewendeten Richtlinien</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left">Personaldaten – Mitarbeiterdaten</td>
<td align="left">1</td>
</tr>
<tr class="even">
<td align="left">Kundendaten</td>
<td align="left">2</td>
</tr>
<tr class="odd">
<td align="left">Streng vertraulich</td>
<td align="left">3</td>
</tr>
<tr class="even">
<td align="left">Personaldaten – Gehaltsdaten</td>
<td align="left">4</td>
</tr>
<tr class="odd">
<td align="left">Vertraulich</td>
<td align="left">5</td>
</tr>
<tr class="even">
<td align="left">Öffentlich</td>
<td align="left">6</td>
</tr>
<tr class="odd">
<td align="left">Privat</td>
<td align="left">Keine automatisch angewendete Richtlinie</td>
</tr>
</tbody>
</table>

## <a name="create-labels-and-auto-apply-label-policies"></a>Erstellen von Bezeichnungen und automatisch angewendeten Bezeichnungsrichtlinien

Erstellen Sie Bezeichnungen und Richtlinien im Security Center oder Compliance Center.

<table>
<thead>
<tr class="header">
<th align="left"><strong>Schritt</strong></th>
<th align="left"><strong>Beschreibung</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>Gewähren von Berechtigungen für Mitglieder Ihres Complianceteams</p></td>
<td align="left"><p>Die Mitglieder Ihres Complianceteams, die Bezeichnungen erstellen sollen, benötigen Berechtigungen für das Security Center und/oder das Compliance Center. Gehen Sie im Security Center oder im Compliance Center zu „Berechtigungen“ und ändern Sie die Mitglieder der Gruppe „Complianceadministrator“.</p>
<p>Einzelheiten hierzu finden Sie unter <a href="https://docs.microsoft.com/microsoft-365/security/office-365-security/grant-access-to-the-security-and-compliance-center">Gewähren des Zugriffs auf das Security Center und/oder Compliance Center</a>.</p></td>
</tr>
<tr class="even">
<td align="left"><p>Erstellen Sie Aufbewahrungsbezeichnungen.</p></td>
<td align="left">Wechseln Sie im Security Center oder Compliance Center zu „Klassifizierungen“, wählen Sie „Aufbewahrungsbezeichnungen“, und erstellen Sie die Bezeichnungen für Ihre Umgebung.</td>
</tr>
<tr class="odd">
<td align="left"><p>Erstellen automatisch angewendeter Richtlinien für Bezeichnungen</p></td>
<td align="left">Wechseln Sie im Security Center oder Compliance Center zu „Klassifizierungen“, wählen Sie „Bezeichnungsrichtlinien“, und erstellen Sie die Richtlinien für das automatische Anwenden von Bezeichnungen. Achten Sie darauf, diese Richtlinien in der priorisierten Reihenfolge zu erstellen.</td>
</tr>
</tbody>
</table>

Die folgende Abbildung zeigt, wie Sie eine automatisch angewendete Bezeichnung für die Bezeichnung „Kundendaten“ erstellen können.

![Erstellen und Anwenden einer Bezeichnung für Kundendaten](../media/Apply-labels-to-personal-data-in-Office-365-image3.png)

In der Abbildung sehen Sie Folgendes:

- Die Bezeichnung „Kundendaten“ wird erstellt.

- Die gewünschten vertraulichen Informationstypen für die DSGVO werden aufgeführt: Nationale belgische Nummer, Kreditkartennummer, Kroatische ID-Kartennummer, nationale finnische ID-Nummer.

- Erstellen einer automatisch angewendeten Richtlinie, die die Bezeichnung „Kundendaten“ jeder Datei zuweist, die einen der vertraulichen Informationstypen enthält, die der Richtlinie hinzugefügt wurde.
