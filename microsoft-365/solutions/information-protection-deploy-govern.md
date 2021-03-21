---
title: Regeln von Informationen, die den Datenschutzbestimmungen unterliegen
ms.author: bcarter
author: brendacarter
f1.keywords:
- NOCSH
manager: laurawi
ms.date: 06/09/2020
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
- m365solution-infoprotection
- m365solution-scenario
ms.custom: ''
description: Verwenden Sie Microsoft 365-Aufbewahrungsbezeichnungen und -richtlinien, um personenbezogene Daten in Ihrer Microsoft 365-Umgebung zu verwalten.
ms.openlocfilehash: 62c2386ac8f9c5b31650df8be2c2a411d8b75959
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50928436"
---
# <a name="govern-information-subject-to-data-privacy-regulation"></a>Regeln von Informationen, die den Datenschutzbestimmungen unterliegen

Steuerungssteuerelemente für die Information Governance können in Ihrer Umgebung eingesetzt werden, um anforderungen an die Einhaltung von Datenschutzbestimmungen zu erfüllen, einschließlich einer Zahl, die speziell für die DSGVO (General Data Protection Regulation, DSGVO), HIPAA-HITECH (Us States Health Care Privacy Act), California Consumer Protection Act (CCPA) und den Brazil Data Protection Act (LGPD) gilt. 

Diese Steuerelemente fallen in erster Linie in die folgenden Lösungsbereiche:

- Aufbewahrungsrichtlinien
- Aufbewahrungsbezeichnungen
- Datensatzverwaltung

## <a name="data-privacy-regulations-impacting-information-governance-controls"></a>Datenschutzbestimmungen, die sich auf Die Steuerung von Informationen auswirken

Im Folgenden finden Sie eine Beispielliste der Datenschutzbestimmungen, die sich auf Die Steuerung von Informationen beziehen können:

- Artikel zur DSGVO (13)(2)(a)
- Artikel zur DSGVO (5)(1)(f)
- HIPAA-HITECH (45 CFR 164.312(c)(2))
- HIPAA-HITECH (45 CFR 164.316(b)(1)(i))
- HIPAA-HITECH (45 CFR 164.316(b)(1)(ii))
- LGPD Artikel 46

Weitere Informationen zu diesen Bestimmungen finden Sie im Artikel "Bewerten von Datenschutzrisiken und Identifizieren [vertraulicher Informationen".](information-protection-deploy-assess.md)

Für die Steuerung von Informationen müssen Datenschutzbestimmungen in der Regel Folgendes umfassen:

- Sie sollten ein technisches Schema für die Aufbewahrung und Löschung von personenbezogenen Daten verwenden, die in Microsoft 365 gespeichert sind.
- Wenn Sie personenbezogene Daten speichern möchten, informieren Sie den Betreff darüber, wie lange die Daten gespeichert werden, was in Front-End-Websystemen zur Standardpraxis gehört.
- Personenbezogene Daten sollten mit überprüfbaren Methoden vor versehentlicher Verarbeitung, Verlust oder Änderung geschützt werden.
- Alle Aktionen, die gegen personenbezogene Daten ausgeführt werden, sollten dokumentiert werden, und diese Dokumentation sollte für einen bestimmten Zeitraum aufbewahrt werden.

Da die Datenschutzbestimmungen nicht sehr spezifisch sind, wenn es um die Aufbewahrung und Löschung von Daten geht, müssen andere Faktoren berücksichtigt werden, die Richtlinien für die Informationsverwaltung für personenbezogene Informationen bestimmen können, die in Ihrem Microsoft 365-Abonnement gespeichert sind. Hier ein paar Beispiele:

- Das Altern von Verbraucherkonten nach 5 Jahren Inaktivität erfordert das Löschen oder Anonymisieren von Kontodaten nach diesem Zeitpunkt, was eine Orchestrierung zwischen dem System erfordert, in dem die Daten und Workflows im Zusammenhang mit Benachrichtigungen und anderer Automatisierung gespeichert werden.
- Konfigurieren von Regeln für die Beibehaltung von Richtlinien und Verfahren im Zusammenhang mit der DSGVO für drei Jahre, nachdem sie ersetzt wurden, was dem Aufbewahrungszeitplan der Organisation für Richtlinien und Verfahren entspricht.
- Verwalten eines separaten Abonnements für die Kommunikation mit Verbrauchern über die Supportorganisation. Alle E-Mail-Kommunikationen wurden nach zwei Wochen aufbewahrt und gelöscht, um den Aufbau von Datenschutzschulden im System zu reduzieren.

Eine wichtige Frage, die Sie beantworten müssen, ist: 

- Wie lange müssen Informationen, die personenbezogene Daten enthalten, aus gültigen geschäftlichen Gründen aufbewahrt werden, um zu verhindern, dass sie für immer beibehalten werden? Dies muss mit den Aufbewahrungsanforderungen für die Geschäftskontinuität abgewogen werden.

Unabhängig von den rechtlichen und geschäftlichen Gründen für die Aufbewahrung personenbezogener Informationen oder deren Löschung bietet Microsoft eine Reihe von Funktionen zum Implementieren Ihres Data Governance-Schemas in Microsoft 365.

## <a name="managing-information-governance-in-microsoft-365"></a>Verwalten der Informationsverwaltung in Microsoft 365

Informationen zu Beginn finden Sie unter [Manage information governance](../compliance/manage-information-governance.md) and Data [Retention, Deletion and Destruction in Microsoft 365](/office365/Enterprise/office-365-data-retention-deletion-and-destruction-overview).

### <a name="develop-data-retention-schedules-for-containers-email-and-content"></a>Entwickeln von Datenaufbewahrungszeitplänen für Container, E-Mails und Inhalte

Denken Sie dabei an Folgendes:

- Die Festlegung eines Zeitplans für die Datenspeicherung für definierte Informationstypen sollte als Voraussetzung für die Implementierung eines Aufbewahrungs- oder Löschungsschemas betrachtet werden.

- Angesichts der Anzahl der Informationstypen, die die meisten Organisationen für wichtig halten, und der zugehörigen großen Aufbewahrungszeitpläne für Datensätze, die mit ihnen zusammenhingen, erfordert die Implementierung einer Strategie für die Datenspeicherung und Datensatzverwaltung eine Planung. 

- Der Schlüssel zum Einrichten einer effektiven Daten-Governance-Strategie dieses Typs besteht in der Fokussierung auf die wichtigsten Geschäftsfunktionen und Informationstypen, die eine formellere Verwaltung erfordern. Beispiele hierfür sind Gesetzliche Verträge, Abschlüsse und Dokumentation zur Einhaltung gesetzlicher Vorschriften. Versuchen Sie, einen separaten Aufbewahrungszeitplan für jeden einzelnen Informationstyp zu vermeiden. Versuchen Sie, allgemeine Kategorien so weit wie möglich zu verwenden, z. B. mit Aufbewahrungszeitplänen von 7 Jahren für allgemeine Geschäftsinhalte.

- Sobald die typen personenbezogenen Informationen in Ihrer Umgebung besser bekannt sind, richten Sie Aufbewahrungs- und Löschungszeitpläne für diese Art von Inhalten ein, und passen Sie Ihre Informationsarchitektur an, um die Steuerung dieser Art von Informationen zu vereinfachen. Isolieren Sie beispielsweise personenbezogene Informationen in separaten Websites, Bibliotheken oder Ordnern mit kontrolliertem Zugriff.

### <a name="retention-policies-and-retention-labels"></a>Aufbewahrungsrichtlinien und Aufbewahrungsbezeichnungen

Verwenden [Sie Aufbewahrungsrichtlinien und Aufbewahrungsbezeichnungen,](../compliance/retention.md) um Inhalte in Microsoft 365 zu speichern oder zu löschen, die personenbezogene Daten enthalten oder voraussichtlich enthalten.

### <a name="records-management"></a>Datensatzverwaltung

Verwenden Sie Aufbewahrungsbezeichnungen, die Inhalte als Datensatz deklarieren, um eine [Datensatzverwaltungslösung](../compliance/records-management.md) für Daten in Microsoft 365 zu implementieren.

Für den Datenschutz werden Anträge von Personen, die von der Rechtsabteilung empfangen werden, als Datensatz deklariert und können für unbegrenzte Zeit gespeichert oder mit Nachweisen beseitigt werden, um die Aufbewahrungsspezifikationen für gesetzliche Aktivitäten einzuhalten.