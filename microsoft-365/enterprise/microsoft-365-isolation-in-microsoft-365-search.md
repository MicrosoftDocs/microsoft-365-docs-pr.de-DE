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
description: In diesem Artikel finden Sie eine Erläuterung der Funktionsweise der Mandantenisolation, um Mandantendaten in Microsoft 365 Suche zu trennen.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 3416afdeceaa7000b516ec89b4a2a1e59d8708d0
ms.sourcegitcommit: 27addd4dac07926528b788215d2dcd0e46301eb1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/16/2021
ms.locfileid: "53464084"
---
# <a name="tenant-isolation-in-microsoft-365-search"></a>Mandantenisolation in der Microsoft 365-Suche

SharePoint Die Onlinesuche verwendet ein Mandantentrennungsmodell, das die Effizienz gemeinsam genutzter Datenstrukturen mit dem Schutz vor Informationslecks zwischen Mandanten ausgleicht. Mit diesem Modell verhindern wir, dass die Suchfeatures:

- Zurückgeben von Abfrageergebnissen, die Dokumente von anderen Mandanten enthalten
- Verfügbarmachen ausreichender Informationen in Abfrageergebnissen, die ein erfahrener Benutzer informationen zu anderen Mandanten ableiten könnte
- Anzeigen von Schemas oder Einstellungen von einem anderen Mandanten
- Mischen von Analyseverarbeitungsinformationen zwischen Mandanten oder Speichern führt zu einem falschen Mandanten
- Verwenden von Wörterbucheinträgen von einem anderen Mandanten

Für jeden Typ von Mandantendaten verwenden wir eine oder mehrere Schutzebenen im Code, um versehentliches Verlust von Informationen zu verhindern. Die kritischsten Daten verfügen über die meisten Schutzebenen, um sicherzustellen, dass ein einzelner Fehler nicht zu tatsächlichen oder wahrgenommenen Informationslecks führt.

## <a name="tenant-separation-for-the-search-index"></a>Mandantentrennung für den Suchindex

Der Suchindex wird auf dem Datenträger auf den Servern gespeichert, auf dem die Indexkomponenten gehostet werden, und die Mandanten teilen sich die Indexdateien. Die indizierten Dokumente eines Mandanten sind nur für Abfragen für diesen Mandanten sichtbar. Drei unabhängige Mechanismen verhindern Informationslecks:

- Mandanten-ID-Filterung
- Präfix für Mandanten-ID
- ACL-Prüfungen

Alle drei Mechanismen müssten fehlschlagen, damit Search Dokumente an den falschen Mandanten zurückgibt.

## <a name="tenant-id-filtering-and-tenant-id-term-prefixing"></a>Mandanten-ID-Filterung und Mandanten-ID-Präfixe

Suche präfixet jeden Begriff, der im Volltextindex mit der Mandanten-ID indiziert ist. Wenn beispielsweise der Begriff *"foo"* für einen Mandanten mit der ID "*123*" indiziert wird, lautet der Eintrag im Volltextindex "*123foo".*

Jede Abfrage wird konvertiert, um die Mandanten-ID mithilfe eines Prozesses namens Mandanten-ID-Filterung einzuschließen. Beispielsweise wird die Abfrage *"foo"* in "<*guid*> konvertiert. *foo* AND *tenantID*:<*guid*>", wobei <*GUID*> den Mandanten darstellt, der die Abfrage ausführt. Diese Abfragekonvertierung erfolgt innerhalb jedes Indexknotens, und weder Abfrage noch Inhaltsverarbeitung können sie beeinflussen. Da die Mandanten-ID jeder Abfrage hinzugefügt wird, kann die Häufigkeit eines Ausdrucks in anderen Mandanten nicht abgeleitet werden, indem die beste Übereinstimmungsrangfolge in einem Mandanten betrachtet wird.

Das Präfix des Mandanten-ID-Ausdrucks findet nur im Volltextindex statt. Feldsuchen, z. B.*"title:foo",* wechseln zu einem synthetischen Suchindex, bei dem Ausdrücke nicht mit dem Präfix "Mandanten-ID" versehen sind. Stattdessen wird bei Feldsuchen der Feldname vorangestellt. Beispielsweise wird die Abfrage "*title:foo*" in "*fields.title:foo AND fields.tenantID*:<*guid*>" konvertiert. Da die Häufigkeit eines Ausdrucks die Rangfolge von Treffern im synthetischen Suchindex nicht beeinflusst, ist keine Mandantentrennung durch Begriffspräfixe erforderlich. Bei einer Feldsuche wie *"title:foo"* hängt die Trennung von Mandanteninhalten von der Mandanten-ID-Filterung nach Abfragekonvertierung ab.

## <a name="document-access-control-list-checks"></a>Listenüberprüfungen der Dokumentzugriffssteuerung

Die Suche steuert den Zugriff auf Dokumente über ACLs, die im Suchindex gespeichert sind. Jedes Element wird mit einer Reihe von Begriffen in einem speziellen ACL-Feld indiziert. Das ACL-Feld enthält einen Ausdruck pro Gruppe oder Benutzer, der das Dokument anzeigen kann. Jede Abfrage wird mit einer Liste von Zugriffssteuerungseintragsbegriffen (Access Control Entry, ACE) erweitert, einer für jede Gruppe, zu der der authentifizierte Benutzer gehört.

Beispielsweise eine Abfrage wie "<*guid*>. *foo AND tenantID*:<*guid*>" wird: "<*guid*>. *foo AND tenantID*:<*guid* >  *AND* (*docACL:* < *ace1* >  *OR docACL*:<*ace2* >  *OR docACL*:<*ace3* >  *...*)"

Da Benutzer- und Gruppenbezeichner und damit ACEs eindeutig sind, bietet dies ein zusätzliches Maß an Sicherheit zwischen Mandanten für Dokumente, die nur für einige Benutzer sichtbar sind. Das gleiche gilt für den speziellen Ace "Jeder außer externen Benutzern", der regulären Benutzern im Mandanten Zugriff gewährt. Da ACEs für "Jeder" jedoch für alle Mandanten identisch sind, hängt die Mandantentrennung für öffentliche Dokumente von der Mandanten-ID-Filterung ab. Verweigerungs-ACEs werden ebenfalls unterstützt. Die Abfrageerweiterung fügt eine Klausel hinzu, die ein Dokument aus dem Ergebnis entfernt, wenn eine Übereinstimmung mit einem Ablehnungs-ACE vorliegt.

Bei Exchange Online Suche wird der Index wie in SharePoint Online nach Postfach-ID für die Postfächer einzelner Benutzer und nicht nach Mandanten-ID (Abonnement-ID) partitioniert. Der Partitionierungsmechanismus ist identisch mit SharePoint Online, es gibt jedoch keine ACL-Filterung.
