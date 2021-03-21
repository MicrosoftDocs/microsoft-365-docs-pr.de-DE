---
title: Überwachen und Reagieren auf Datenschutzvorfälle in Ihrer Organisation
ms.author: bcarter
author: brendacarter
f1.keywords:
- NOCSH
manager: laurawi
ms.date: 01/04/2021
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
description: Verwenden Sie Überwachungs- und Warnungsrichtlinien und Anfragen von personensubjektierten Personen, um Vorfälle mit personenbezogenen Daten zu überwachen und darauf zu reagieren.
ms.openlocfilehash: 4070cd772d243bcfba33bfb164fd05e1f0911b3b
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50928424"
---
# <a name="monitor-and-respond-to-data-privacy-incidents-in-your-organization"></a>Überwachen und Reagieren auf Datenschutzvorfälle in Ihrer Organisation

Microsoft 365-Features stehen Ihnen bei der Überwachung, Untersuchung und Reaktion auf Datenschutzvorfälle in Ihrer Organisation bei der Operationalisierung verwandter Funktionen zur Verfügung. Prozesse, Verfahren und andere Dokumentationen für jede dieser Verfahren können auch wichtig sein, um die Einhaltung von Vorschriften zu demonstrieren.

Zu diesen zählen: 

- Überwachungs- und Warnungsrichtlinien
- Anfragen von Datensubjekten (einschließlich Inhaltssuche und eDiscovery)
- Zusätzliche Untersuchungstools und Berichte

## <a name="data-privacy-regulations-impacting-the-use-of-monitoring-and-response-tools"></a>Datenschutzbestimmungen, die sich auf die Verwendung von Überwachungs- und Reaktionstools auswirken

Im Folgenden finden Sie eine Beispielliste der Datenschutzbestimmungen, die sich auf Die Steuerung von Informationen beziehen können:

- LGPD Artikel 46
- LGPD Artikel 48
- Artikel zur DSGVO (5)(1)(f)
- Artikel zur DSGVO (15)(1)(e)
- HIPAA-HITECH (45 C.F.R. 164.308(a)(1)(ii)(D))
- HIPAA-HITECH (45 C.F.R. 164.308(a)(6)(ii)
- HIPAA-HITECH (45 C.F.R. 164.312(b))
- CCPA (1798.105(c))

Weitere Informationen finden Sie unter [Bewerten von Datenschutzrisiken und Identifizieren vertraulicher Informationen.](information-protection-deploy-assess.md)

Die Datenschutzbestimmungen fordern im Allgemeinen Folgendes zur Überwachung und Reaktion auf:

- Überwachung, Warnung und Berichterstellung für Aktivitäten im Zusammenhang mit der Speicherung, Freigabe und Verarbeitung personenbezogener Daten
- Die Möglichkeit, auf eine Anfrage einer Person zu antworten und in einigen Fällen Ermittlungen und andere administrative Maßnahmen zur Erfüllung dieser Anforderungen durchzuführen.

Ihre Organisation möchte möglicherweise auch Überwachungs- und Reaktionsaktivitäten für andere Zwecke durchführen, z. B. für andere Complianceanforderungen oder aus geschäftlichen Gründen. Die Einrichtung Ihres Überwachungs- und Reaktionsschemas für den Datenschutz sollte im Rahmen der allgemeinen Überwachungs- und Reaktionsplanung, -implementierung und -verwaltung durchgeführt werden.

Damit Sie mit einem Überwachungs- und Reaktionsschema in Microsoft 365 für Datenschutzbestimmungen beginnen können, werden in diesem Artikel nützliche Funktionen in Microsoft 365 zur Beantwortung von Fragen wie: 

- Welche Art von Täglichen Überwachungs-, Untersuchungs- und Berichtstechniken stehen für die verschiedenen Datentypen und Quellen zur Verfügung?
- Welche Mechanismen sind erforderlich, um Anträge von Datensubjekten (Data Subject Requests, DSRs) und Abhilfemaßnahmen wie Anonymisierung, Redaction und Löschung zu behandeln?

## <a name="auditing-and-alert-policies-in-the-security-and-compliance-center"></a>Überwachungs- und Warnungsrichtlinien im Security and Compliance Center

In diesen Artikeln finden Sie Informationen zum Einrichten von Überwachungs-, Erweiterten Überwachungs- und Warnungsrichtlinien:

- [Vereinheitlichte Überwachung](../compliance/search-the-audit-log-in-security-and-compliance.md)
- [Postfachüberwachung](../compliance/enable-mailbox-auditing.md)
- [Erweiterte Überwachung](../compliance/advanced-audit.md)
- [Warnungsrichtlinien](../compliance/alert-policies.md)

## <a name="data-subject-requests-for-the-gdpr-and-ccpa"></a>Anträge von Datensubjekten für die DSGVO und das CCPA

Informationen zum Reagieren auf einen Antrag auf Antrag von Personen in Microsoft 365 finden Sie unter Anfragen von Personen nach der DSGVO und [ccpa.](/compliance/regulatory/gdpr-dsr-Office365)

## <a name="manage-deleted-users-in-microsoft-stream"></a>Verwalten gelöschter Benutzer in Microsoft Stream

Wenn ein Benutzer in Microsoft Stream aus Azure Active Directory (Azure AD) gelöscht wird, bleibt seine E-Mail-Adresse dem Video zugeordnet, wenn sein Name vor diesem Zeitpunkt einem bereitgestellten Stream-Video zugeordnet wurde. Weitere [Informationen finden Sie unter Verwalten gelöschter Benutzer aus Microsoft Stream.](/stream/managing-deleted-users)

## <a name="insider-risk-management-as-an-investigative-tool"></a>Insider-Risikomanagement als Untersuchungstool

[Das Insider-Risikomanagement in Microsoft 365](../compliance/insider-risk-management.md) ist ein Feature des Microsoft Compliance Admin Centers, mit dem Sie interne Risiken minimieren können, indem Sie riskante Aktivitäten in Ihrer Organisation erkennen, untersuchen und Maßnahmen ergreifen können.