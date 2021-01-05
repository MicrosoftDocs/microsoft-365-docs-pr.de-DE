---
title: Überwachen und reagieren auf Datenschutz Vorfälle in Ihrer Organisation
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
description: Verwenden Sie Überwachungs-und Warnungsrichtlinien sowie Anforderungen von Datensubjekten zur Überwachung und Reaktion auf personenbezogene Daten Vorfälle.
ms.openlocfilehash: 3ae0f2a6528f6188500c7cee7732c6447013eaa6
ms.sourcegitcommit: ae646779d84e993cf80b1207e76b856a21be5790
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/04/2021
ms.locfileid: "49749587"
---
# <a name="monitor-and-respond-to-data-privacy-incidents-in-your-organization"></a>Überwachen und reagieren auf Datenschutz Vorfälle in Ihrer Organisation

Microsoft 365-Funktionen stehen Ihnen zur Überwachung, Untersuchung und Reaktion auf Datenschutz Vorfälle in Ihrer Organisation zur Verfügung, wenn Sie verwandte Funktionen einbringen. Es kann auch wichtig sein, Prozesse, Verfahren und andere Dokumentationen für diese zu untersuchen, um die Einhaltung von Regulierungsstellen zu demonstrieren.

Zu diesen zählen: 

- Überwachungs-und Warnungsrichtlinien
- Anforderungen von Datensubjekten (einschließlich Inhaltssuche und eDiscovery)
- Zusätzliche Ermittlungs Tools und Berichte

## <a name="data-privacy-regulations-impacting-the-use-of-monitoring-and-response-tools"></a>Datenschutzbestimmungen, die sich auf die Verwendung von Überwachungs-und Antwort Tools auswirken

Im folgenden finden Sie eine Beispielliste der Datenschutzbestimmungen, die sich möglicherweise auf die Steuerelemente für die Informationssteuerung beziehen:

- LGPD-Artikel 46
- LGPD-Artikel 48
- Dsgvo-Artikel (5) (1) (f)
- Dsgvo-Artikel (15) (1) (e)
- HIPAA-HITECH (45 C.F.R. 164.308 (a) (1) (II) (D))
- HIPAA-HITECH (45 C.F.R. 164.308(a)(6)(ii)
- HIPAA-HITECH (45 C.F.R. 164.312 (b))
- CCPA (1798.105 (c))

Weitere Informationen finden Sie unter [bewerten von Datenschutzrisiken und identifizieren vertraulicher Informationen](information-protection-deploy-assess.md).

In den Datenschutzbestimmungen wird generell folgendes zur Überwachung und Reaktion gefordert:

- Überwachung, Benachrichtigung und Berichterstellung für Aktivitäten im Zusammenhang mit der Speicherung, Freigabe und Verarbeitung personenbezogener Daten
- Die Möglichkeit, auf eine Datensubjekt Anforderung (DSR) zu reagieren und in einigen Fällen Ermittlungs-und andere administrative Maßnahmen durchzuführen, um diese Anforderungen einzuhalten.

Ihre Organisation möchte möglicherweise auch Überwachungs-und Antwort Aktivitäten für andere Zwecke wie andere Compliance-Anforderungen oder aus geschäftlichen Gründen durchführen. Das Einrichten Ihres Überwachungs-und Reaktionsschemas für den Datenschutz sollte im Rahmen der allgemeinen Überwachung und der Reaktionsplanung, Implementierung und Verwaltung erfolgen.

Um Ihnen den Einstieg in ein Überwachungs-und Reaktionsschema in Microsoft 365 für Datenschutzbestimmungen zu erleichtern, werden in diesem Artikel nützliche Funktionen in Microsoft 365 aufgelistet, um Fragen zu beantworten, beispielsweise: 

- Welche Art von alltäglichen Überwachungs-, Ermittlungs-und Bericht Erstellungstechniken stehen für die verschiedenen Datentypen und Quellen zur Verfügung?
- Welche Mechanismen erforderlich sind, um Anforderungen an die Datensubjekte (DSRs) und etwaige Korrekturmaßnahmen wie Anonymisierung, Korrektur und Löschung zu behandeln.

## <a name="auditing-and-alert-policies-in-the-security-and-compliance-center"></a>Überwachungs-und Warnungsrichtlinien im Security and Compliance Center

Weitere Informationen finden Sie in den folgenden Artikeln zum Einrichten von Überwachung, erweiterter Überwachung und Warnungsrichtlinien:

- [Vereinheitlichte Überwachung](../compliance/search-the-audit-log-in-security-and-compliance.md)
- [Postfachüberwachung](../compliance/enable-mailbox-auditing.md)
- [Erweiterte Überwachung](../compliance/advanced-audit.md)
- [Warnungsrichtlinien](../compliance/alert-policies.md)

## <a name="data-subject-requests-for-the-gdpr-and-ccpa"></a>Anforderungen von Datensubjekten für die dsgvo und CCPA

Informationen zum Antworten auf einen DSR in Microsoft 365 finden Sie unter [Datensubjekt Anforderungen für die dsgvo und CCPA](../compliance/gdpr-dsr-office365.md) .

## <a name="manage-deleted-users-in-microsoft-stream"></a>Verwalten von gelöschten Benutzern in Microsoft Stream

Wenn ein Benutzer für Microsoft Stream aus Azure Active Directory (Azure AD) gelöscht wird, wenn sein Name einem gebuchten Stream-Video vor diesem Zeitpunkt zugeordnet wurde, bleibt seine e-Mail-Adresse dem Video zugeordnet. Entfernen Sie die Informationen unter [Verwalten gelöschter Benutzer aus Microsoft Stream](https://docs.microsoft.com/stream/managing-deleted-users) .

## <a name="insider-risk-management-as-an-investigative-tool"></a>Insider Risikomanagement als Ermittlungs Tool

Das [Insider Risikomanagement in Microsoft 365](../compliance/insider-risk-management.md) ist ein Feature des Microsoft Compliance Admin Center, mit dem Sie das interne Risikomini mieren können, indem Sie riskante Aktivitäten in Ihrer Organisation erkennen, untersuchen und Maßnahmen ergreifen können.
