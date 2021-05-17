---
title: Mandantenisolation in der Microsoft 365-Suche
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
f1.keywords:
- NOCSH
description: In diesem Artikel finden Sie eine Erläuterung der Funktionsweise der Mandantenisolation zum Trennen von Mandantendaten in Microsoft 365 Suche.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 3416afdeceaa7000b516ec89b4a2a1e59d8708d0
ms.sourcegitcommit: c029834c8a914b4e072de847fc4c3a3dde7790c5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/02/2020
ms.locfileid: "47332400"
---
# <a name="tenant-isolation-in-microsoft-365-search"></a>Mandantenisolation in der Microsoft 365-Suche

SharePoint Die Onlinesuche verwendet ein Mandantentrennungsmodell, das die Effizienz freigegebener Datenstrukturen mit dem Schutz vor Informationslecks zwischen Mandanten abgleicht. Mit diesem Modell verhindern wir, dass die Suchfeatures:

- Zurückgeben von Abfrageergebnissen, die Dokumente von anderen Mandanten enthalten
- Exposing sufficient information in query results that a skilled user could inferen information about other tenants
- Anzeigen des Schemas oder der Einstellungen eines anderen Mandanten
- Mischen von Analyseverarbeitungsinformationen zwischen Mandanten oder Speicherergebnissen im falschen Mandanten
- Verwenden von Wörterbucheinträgen eines anderen Mandanten

Für jeden Typ von Mandantendaten verwenden wir eine oder mehrere Schutzebenen im Code, um versehentliches Auslaufen von Informationen zu verhindern. Die kritischsten Daten haben die meisten Schutzebenen, um sicherzustellen, dass ein einzelner Fehler nicht zu tatsächlichen oder wahrgenommenen Informationslecks führt.

## <a name="tenant-separation-for-the-search-index"></a>Mandantentrennung für den Suchindex

Der Suchindex wird auf dem Datenträger auf den Servern gespeichert, auf denen die Indexkomponenten hosten, und die Mandanten teilen sich die Indexdateien. Die indizierten Dokumente eines Mandanten sind nur für Abfragen für den Mandanten sichtbar. Drei unabhängige Mechanismen verhindern Informationslecks:

- Mandanten-ID-Filterung
- Präfix des Mandanten-ID-Ausdrucks
- ACL-Prüfungen

Alle drei Mechanismen müssten fehlschlagen, damit die Suche Dokumente an den falschen Mandanten zurücksenkte.

## <a name="tenant-id-filtering-and-tenant-id-term-prefixing"></a>Mandanten-ID-Filterung und Mandanten-ID-Ausdruckspräfixierung

Die Suche enthält Präfixe für jeden Ausdruck, der im Volltextindex mit der Mandanten-ID indiziert ist. Wenn beispielsweise der Begriff *"foo"* für einen Mandanten mit der ID *" 123*" indiziert wird, ist der Eintrag im Volltextindex "*123foo ".*

Jede Abfrage wird mithilfe eines Prozesses namens Mandanten-ID-Filterung in die Mandanten-ID konvertiert. Beispielsweise wird die Abfrage "*foo*" in "<*guid>.* *foo* AND *tenantID*:<*guid*>", wobei <*guid>* den Mandanten darstellt, der die Abfrage ausgeführt hat. Diese Abfragekonvertierung erfolgt innerhalb jedes Indexknotens, und weder die Abfrage noch die Inhaltsverarbeitung können sie beeinflussen. Da jeder Abfrage die Mandanten-ID hinzugefügt wird, kann die Häufigkeit eines Ausdrucks in anderen Mandanten nicht abgeleitet werden, indem die beste Übereinstimmungsrangfolge in einem Mandanten betrachtet wird.

Mandanten-ID-Ausdruckspräfixierung tritt nur im Volltextindex auf. Feldsuchen, z. B. "*title:foo*", wechseln zu einem synthetischen Suchindex, in dem Begriffen nicht mandanten-ID vorangestellt wird. Feldsuchen wird stattdessen mit dem Feldnamen vorangestellt. Beispielsweise wird die Abfrage "*title:foo*" in "*fields.title:foo AND fields.tenantID*:<*guid>."* konvertiert. Da die Häufigkeit eines Ausdrucks die Rangfolge der Treffer im synthetischen Suchindex nicht beeinflusst, ist keine Mandantentrennung durch Ausdruckspräfixierung nötig. Bei einer feldierten Suche wie "*title:foo*" hängt die Mandanteninhaltstrennung von der Mandanten-ID-Filterung durch Abfragekonvertierung ab.

## <a name="document-access-control-list-checks"></a>Listenüberprüfungen der Dokumentzugriffssteuerung

Die Suche steuert den Zugriff auf Dokumente über ACLs, die im Suchindex gespeichert sind. Jedes Element wird mit einem Satz von Begriffen in einem speziellen ACL-Feld indiziert. Das Feld ACL enthält einen Ausdruck pro Gruppe oder Benutzer, der das Dokument anzeigen kann. Jede Abfrage wird durch eine Liste von Zugriffssteuerungseintragsbegriffen (Access Control Entry, ACE) erweitert, einer für jede Gruppe, zu der der authentifizierte Benutzer gehört.

Beispiel: Eine Abfrage wie "<*guid>.* *foo AND tenantID*:<*guid*>" wird: "<*guid>.* *foo AND tenantID*:<*guid* >  *AND* (*docACL:* < *ace1* >  *OR docACL*:<*ace2* >  *OR docACL*:<*ace3* >  *...*)"

Da Benutzer- und Gruppenbezeichner und damit ACEs eindeutig sind, bietet dies ein zusätzliches Maß an Sicherheit zwischen Mandanten für Dokumente, die nur für einige Benutzer sichtbar sind. Dies gilt auch für den speziellen ACE "Jeder außer externen Benutzern", der regulären Benutzern im Mandanten Zugriff gewährt. Da ACEs für "Everyone" jedoch für alle Mandanten gleich sind, hängt die Mandantentrennung für öffentliche Dokumente von der Mandanten-ID-Filterung ab. Deny ACEs werden ebenfalls unterstützt. Die Abfragevergrößerung fügt eine Klausel hinzu, die ein Dokument aus dem Ergebnis entfernt, wenn eine Übereinstimmung mit einem abgelehnten ACE vor liegt.

Bei Exchange Online wird der Index nach Postfach-ID für die Postfächer einzelner Benutzer und nicht nach Mandanten-ID (Abonnement-ID) partitioniert, wie in SharePoint Online. Der Partitionierungsmechanismus ist mit SharePoint Online identisch, es gibt jedoch keine ACL-Filterung.
