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
description: In diesem Artikel finden Sie eine Erläuterung der Funktionsweise der Mandanten Isolierung zum Trennen von Mandantendaten in der Microsoft 365-Suche.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 3416afdeceaa7000b516ec89b4a2a1e59d8708d0
ms.sourcegitcommit: c029834c8a914b4e072de847fc4c3a3dde7790c5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/02/2020
ms.locfileid: "47332400"
---
# <a name="tenant-isolation-in-microsoft-365-search"></a>Mandantenisolation in der Microsoft 365-Suche

Bei der Suche in SharePoint Online wird ein Mandanten Trennungsmodell verwendet, das die Effizienz freigegebener Datenstrukturen mit dem Schutz vor Informationen abgleicht, die zwischen Mandanten auslaufen. Mit diesem Modell verhindern wir, dass die Suchfeatures von:

- Zurückgeben von Abfrageergebnissen, die Dokumente von anderen Mandanten enthalten
- Verfügbar machen ausreichenden Informationen in Abfrageergebnissen, die ein qualifizierter Benutzerinformationen zu anderen Mandanten ableiten könnte
- Anzeigen von Schema oder Einstellungen von einem anderen Mandanten
- Mischen von Analyse Verarbeitungsinformationen zwischen Mandanten oder Speicher Ergebnissen im falschen Mandanten
- Verwenden von Wörterbucheinträgen aus einem anderen Mandanten

Für jeden Typ von Mandantendaten verwenden wir mindestens eine Schutzschicht im Code, um das versehentliche Auslaufen von Informationen zu verhindern. Die kritischsten Daten haben die meisten Schutzschichten, um sicherzustellen, dass ein einzelner Fehler nicht zu tatsächlichen oder wahrgenommenen Datenverlusten führt.

## <a name="tenant-separation-for-the-search-index"></a>Mandantentrennung für den Suchindex

Der Suchindex wird auf dem Datenträger auf den Servern gespeichert, die die Indexkomponenten hosten, und die Mandanten teilen die Indexdateien. Die indizierten Dokumente eines Mandanten sind nur für Abfragen für diesen Mandanten sichtbar. Drei unabhängige Mechanismen verhindern Informationslecks:

- Mandanten-ID-Filterung
- Begriffs Präfix für Mandanten-ID
- ACL-Überprüfungen

Bei der Suche müssen alle drei Mechanismen fehlschlagen, um Dokumente an den falschen Mandanten zurückzugeben.

## <a name="tenant-id-filtering-and-tenant-id-term-prefixing"></a>Mandanten-ID-Filterung und Mandanten-ID-Ausdruckspräfix

Such Präfixe alle Begriffe, die im Volltextindex mit der Mandanten-ID indiziert sind. Wenn beispielsweise der Ausdruck "*foo*" für einen Mandanten mit der ID "*123*" indiziert wird, lautet der Eintrag im Volltextindex "123foo"*.*

Jede Abfrage wird konvertiert, um die Mandanten-ID mit einem Prozess namens Mandanten-ID-Filterung einzubeziehen. Beispielsweise wird die Abfrage "*foo*" in "<*GUID*> konvertiert. *foo* Und *Mandanten*-ID: <*GUID*> ", wobei <*GUID*> den Mandanten darstellt, der die Abfrage ausführt. Diese Abfrage Konvertierung erfolgt innerhalb jedes Index Knotens, und weder die Abfrage noch die Inhaltsverarbeitung können dies beeinflussen. Da die Mandanten-ID jeder Abfrage hinzugefügt wird, kann die Häufigkeit eines Ausdrucks in anderen Mandanten nicht durch die Suche nach der besten Übereinstimmungsbewertung in einem Mandanten hergeleitet werden.

Das Ausdruckspräfix für Mandanten-ID tritt nur im Volltextindex auf. Feldsuche, beispielsweise "*Title: foo*", wechseln Sie zu einem synthetischen Suchindex, wobei Ausdrücke nicht durch Mandanten-ID vorangestellt werden. Stattdessen wird dem Feldnamen ein Präfix für die Feld Suche vorangestellt. Beispielsweise wird die Abfrage "*Title: foo*" in "*Fields. Title: foo" und "Fields. Tenant-* ID: <*GUID*>" konvertiert. Da die Häufigkeit eines Ausdrucks die Rangfolge von Treffern im synthetischen Suchindex nicht beeinflusst, ist es nicht erforderlich, die mandantentrennung nach Begriffs Präfixen durchzuführen. Bei einer Feldsuche wie "*Title: foo*" hängt die Inhalts Trennung des Mandanten von der Mandanten-ID-Filterung durch die Abfrage Konvertierung ab.

## <a name="document-access-control-list-checks"></a>Überprüfungen von Dokumentzugriffs Steuerungs Listen

Search steuert den Zugriff auf Dokumente über ACLs, die im Suchindex gespeichert sind. Jedes Element wird mit einer Reihe von Ausdrücken in einem speziellen ACL-Feld indiziert. Das ACL-Feld enthält einen Ausdruck pro Gruppe oder Benutzer, der das Dokument anzeigen kann. Jede Abfrage wird mit einer Liste von ACE-Begriffen (Access Control Entry, Zugriffssteuerungseintrag) erweitert, eine für jede Gruppe, zu der der authentifizierte Benutzer gehört.

Beispiel: eine Abfrage wie "<*GUID*>. *foo und Mandanten-* ID: <*GUID*> "wird:" <*GUID*>. *foo und Mandanten-* ID: <*GUID* >  *und* (*docACL:* < *ace1* >  *oder docACL*: <*ace2* >  *oder docACL*: <*ace3* >  *...*) "

Da Benutzer-und Gruppen-IDs und damit ACEs eindeutig sind, bietet dies ein zusätzliches Sicherheitsniveau zwischen Mandanten für Dokumente, die nur für einige Benutzer sichtbar sind. Das gleiche gilt für den speziellen Ace "jeder außer externen Benutzern", der regulären Benutzern im Mandanten Zugriff gewährt. Da ACEs für "Everyone" jedoch für alle Mandanten gleich sind, hängt die mandantentrennung für öffentliche Dokumente von der Mandanten-ID-Filterung ab. Deny-ACEs werden ebenfalls unterstützt. Die Abfrageerweiterung fügt eine Klausel hinzu, die ein Dokument aus dem Ergebnis entfernt, wenn eine Übereinstimmung mit einem Deny-ACE vorliegt.

In Exchange Online Suche wird der Index für die Post Fach-ID für die Postfächer einzelner Benutzer anstelle der Mandanten-ID (Abonnement-ID) wie in SharePoint Online partitioniert. Der Partitionierungs Mechanismus ist identisch mit SharePoint Online, es gibt jedoch keine ACL-Filterung.
