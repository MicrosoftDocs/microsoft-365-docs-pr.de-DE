---
title: Steuern der Informationen unterliegen der Datenschutzverordnung
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
ms.custom: ''
description: Verwenden Sie Microsoft 365-Aufbewahrungs Bezeichnungen und-Richtlinien zum Verwalten personenbezogener Daten in Ihrer Microsoft 365-Umgebung.
ms.openlocfilehash: a7a0d6e00d29d80dfd0cb72ba217177aa6029a2c
ms.sourcegitcommit: 0f71042edc7c3a7f10a7b92e1943abf51532cbf5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/29/2020
ms.locfileid: "46522301"
---
# <a name="govern-information-subject-to-data-privacy-regulation"></a>Steuern der Informationen unterliegen der Datenschutzverordnung

Die Steuerelemente zur Steuerung der Informationssteuerung können in Ihrer Umgebung eingesetzt werden, um die Anforderungen an die Einhaltung von Datenschutzrichtlinien zu erfüllen, einschließlich einer spezifischen Datenschutzverordnung (dsgvo), des HIPAA-HITECH (Datenschutzgesetz der USA), des California Consumer Protection Act (CCPA) und des Brazil Data Protection Act (LGPD). 

Diese Steuerelemente fallen in erster Linie in die folgenden Lösungsbereiche:

- Aufbewahrungsrichtlinien
- Aufbewahrungsbezeichnungen
- Datensatzverwaltung

## <a name="data-privacy-regulations-impacting-information-governance-controls"></a>Datenschutzbestimmungen, die sich auf die Steuerung der Informationssteuerung auswirken

Im folgenden finden Sie eine Beispielliste der Datenschutzbestimmungen, die sich möglicherweise auf die Steuerelemente für die Informationssteuerung beziehen:

- Dsgvo-Artikel (13) (2) (a)
- Dsgvo-Artikel (5) (1) (f)
- HIPAA-HITECH (45 CFR 164.312 (c) (2))
- HIPAA-HITECH (45 CFR 164.316 (b) (1) (i))
- HIPAA-HITECH (45 CFR 164.316 (b) (1) (II))
- LGPD-Artikel 46

Weitere Informationen zu diesen Richtlinien finden Sie unter [bewerten von Datenschutzrisiken und Identifizieren von vertraulichen Informations Artikeln](information-protection-deploy-assess.md).

Für die Informationssteuerung werden in der Regel die Datenschutzbestimmungen für Folgendes gefordert:

- Sie sollten ein technisches Schema für Aufbewahrung und Löschung für personenbezogene Daten verwenden, die in Microsoft 365 gespeichert sind.
- Wenn Sie personenbezogene Daten speichern möchten, informieren Sie den Betreff darüber, wie lange die Daten gespeichert werden, was heute auf Front-End-Websystemen üblich ist.
- Personenbezogene Daten sollten mit überprüfbaren Methoden vor versehentlicher Verarbeitung, Verlust oder Änderung geschützt werden.
- Alle Aktionen, die mit personenbezogenen Daten ausgeführt werden, sollten dokumentiert werden, und die Dokumentation sollte für einen bestimmten Zeitraum aufbewahrt werden.

Da die Datenschutzbestimmungen hinsichtlich der Datenaufbewahrung und-Löschung nicht sehr spezifisch sind, müssen andere Faktoren berücksichtigt werden, die die Richtlinien für die Informationssteuerung für persönliche Informationen diktieren, die in Ihrem Microsoft 365-Abonnement gespeichert sind. Hier ein paar Beispiele:

- Alterung von Consumer-Konten nach 5 Jahren Inaktivität und erfordert Löschung oder Anonymisierung von Kontodaten nach diesem Moment, erfordern Orchestrierung zwischen dem System speichern der Daten und Workflows im Zusammenhang mit Benachrichtigungen und andere Automatisierung.
- Konfigurieren von Regeln für die Beibehaltung von Richtlinien und Verfahren im Zusammenhang mit dsgvo für drei Jahre nach der abgelösten Einstellung, die mit dem aufbewahrungszeitplan der Organisation für Richtlinien und Verfahren übereinstimmt.
- Verwalten eines separaten Abonnements für die Kommunikation mit Verbrauchern über die Support Organisation. Alle e-Mail-Nachrichten wurden nach zwei Wochen aufbewahrt und gelöscht, um die Datenschutz Schulden im System zu reduzieren.

Eine wichtige Frage zu beantworten ist: 

- Wie lange müssen Daten, die personenbezogene Daten enthalten, aus gültigen geschäftlichen Gründen aufbewahrt werden, um zu verhindern, dass "Keep it Forever" praktiziert wird? Dies muss mit dem aufbewahrungsbedarf für Business Continuity ausgeglichen werden.

Unabhängig von den rechtlichen und geschäftlichen Gründen, um personenbezogene Informationen zu speichern oder zu löschen, bietet Microsoft eine Reihe von Funktionen zur Implementierung Ihres Daten steuerungsschemas in Microsoft 365.

## <a name="managing-information-governance-in-microsoft-365"></a>Managing Information Governance in Microsoft 365

Informationen zu Beginn finden Sie unter [Manage Information Governance](../compliance/manage-information-governance.md) and [Data Retention, Deletion and Destruction in Microsoft 365](https://docs.microsoft.com/office365/Enterprise/office-365-data-retention-deletion-and-destruction-overview).

### <a name="develop-data-retention-schedules-for-containers-email-and-content"></a>Entwickeln von Zeitplänen für die Datenaufbewahrung für Container, e-Mail und Inhalte

Denken Sie dabei an Folgendes:

- Das Festlegen eines Daten Aufbewahrungs Zeitplans für definierte Informationstypen sollte als Voraussetzung für die Implementierung eines Aufbewahrungs-oder Lösch Schemas betrachtet werden.

- Angesichts der Anzahl von Informationstypen, die von den meisten Organisationen als wichtig erachtet werden, und der entsprechenden umfangreichen Aufbewahrungszeiträume für Datensätze, die mit diesen übereinstimmen, ist die Implementierung einer Daten Aufbewahrungs-und Datensatzverwaltungsstrategie geplant. 

- Der Schlüssel zum Einrichten einer effektiven Strategie für die Datensteuerung dieses Typs besteht darin, sich auf die Geschäftsfunktionen und Informationstypen mit der höchsten Priorität zu konzentrieren, die eine formellere Verwaltung erfordern. Beispiele sind gesetzliche Verträge, Abschlüsse und Dokumentationen zur behördlichen Konformität. Versuchen Sie, einen separaten aufbewahrungszeitplan für jeden einzelnen Informationstyp zu vermeiden. Versuchen Sie, allgemeine Kategorien so weit wie möglich zu nutzen, beispielsweise mit Aufbewahrungszeit Plänen von 7 Jahren für allgemeine Geschäftsinhalte.

- Wenn die personenbezogenen Informationstypen in Ihrer Umgebung besser bekannt sind, legen Sie Aufbewahrungs-und Lösch Zeitpläne für diese Art von Inhalten fest, und passen Sie Ihre Informationsarchitektur an, um die Steuerung dieser Art von Informationen zu vereinfachen. Isolieren Sie beispielsweise persönliche Informationen in separaten Websites, Bibliotheken oder Ordnern mit gesteuertem Zugriff.

### <a name="retention-policies"></a>Aufbewahrungsrichtlinien

Erstellen und Bereitstellen von [Aufbewahrungsrichtlinien](../compliance/retention-policies.md) für Inhalte in Websites, die automatisch angewendet werden.

Für den Datenschutz für Websites, die personenbezogene Daten enthalten oder erwartet werden, geben Sie Aufbewahrungs-oder Löschregeln zur Behebung von Organisationsstandards an.

### <a name="retention-labels"></a>Aufbewahrungsbezeichnungen

Erstellen und Bereitstellen von [Aufbewahrungs Bezeichnungen](../compliance/labels.md) für Inhalt und e-Mail.

Für den Datenschutz von Websites, Bibliotheken, Ordnern und e-Mails, die personenbezogene Daten enthalten oder erwartet werden, geben Sie automatische Aufbewahrungs-oder Löschregeln zur Behebung von Organisationsstandards an.

### <a name="records-management"></a>Datensatzverwaltung

Erstellen und Bereitstellen von Aufbewahrungs Bezeichnungen für die Datensatzverwaltung basierend auf einem Zeitplan für die Datensatzaufbewahrung und einem Dateiplan.

Für den Datenschutz werden Datensubjekt Anforderungen (DSRs), die von der Rechtsabteilung empfangen werden, als Datensatz deklariert und auf unbestimmte Zeit gespeichert, um die Aufbewahrungspflichten für gesetzliche Aktivitäten einzuhalten.

Weitere Informationen finden Sie in den folgenden Ressourcen: 

- [Datensatzverwaltung](../compliance/records-management.md)
- [Dateiplan-Manager](../compliance/file-plan-manager.md)
- [Ereignisbasierte Aufbewahrung für die Datensatzverwaltung](../compliance/automate-event-driven-retention.md)
- [Disposition von Inhalten](../compliance/disposition-reviews.md)
