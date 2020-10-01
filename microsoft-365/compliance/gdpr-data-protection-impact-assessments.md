---
title: Datenschutz-Folgenabschätzung
description: Diese Dokumente stellen den Datenverantwortlichen Informationen bereit, die ihnen helfen, zu bestimmen, ob eine Datenschutz-Folgeabschätzung erforderlich ist, und wenn ja, welche Informationen sie enthalten soll.
keywords: Datenschutz-Folgenabschätzung, DPIA (Data Protection Impact Assessment), Dynamics 365, Microsoft Professional Services, Microsoft 365, Microsoft 365-Dokumentation, DSGVO
localization_priority: Priority
ms.prod: microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: itpro
ms.collection:
- GDPR
- M365-security-compliance
titleSuffix: Microsoft GDPR
ms.openlocfilehash: 612c2c310a337b38ab654c7465fad1d284c60903
ms.sourcegitcommit: 888b9355ef7b933c55ca6c18639c12426ff3fbde
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/29/2020
ms.locfileid: "48305075"
---
# <a name="data-protection-impact-assessment-for-the-gdpr"></a>Datenschutz-Folgenabschätzungen im Rahmen der DSGVO

Die Datenschutz-Grundverordnung (DSGVO) führt neue Regeln für Organisationen ein, die Waren und Dienstleistungen in der Europäischen Union (EU) anbieten oder Daten von in der EU ansässigen natürlichen Personen erfassen und analysieren, unabhängig von deren Wohnsitz und Unternehmenssitz. Weitere Details finden Sie in der [Zusammenfassung zum Thema DSGVO](gdpr.md). Dieses Dokument bietet Ihnen Informationen bezüglich Datenschutz-Folgenabschätzungen unter der DSGVO, während Sie Microsoft-Produkte und -Dienste verwenden.

## <a name="terminology"></a>Begrifflichkeiten

Hilfreiche Definitionen für DSGVO-Ausdrücke, die in diesem Dokument verwendet werden:

- *Datenverantwortlicher (Verantwortlicher)*: eine juristische Person, Behörde, Einrichtung oder andere Stelle, die allein oder gemeinsam mit anderen über die Zwecke und Mittel der Verarbeitung von personenbezogenen Daten entscheidet.  
- *Personenbezogene Daten * und *betroffene Person*: alle Informationen, die sich auf eine identifizierte oder identifizierbare natürliche Person (betroffene Person) beziehen; als identifizierbar wird eine natürliche Person angesehen, die direkt oder indirekt identifiziert werden kann.  
- *Auftragsverarbeiter*: eine natürliche oder juristische Person, Behörde, Einrichtung oder andere Stelle, die personenbezogene Daten im Auftrag des Verantwortlichen verarbeitet.  
- *Kundendaten*: Daten, die bei Ihrer tagtäglichen Geschäftsausführung erstellt und gespeichert werden.

## <a name="what-is-a-dpia"></a>Was ist Datenschutz-Folgenabschätzung?

Unter der DSGVO sind Datenverantwortliche dazu aufgerufen, eine Datenschutz-Folgenabschätzung (Data Protection Impact Assessment, DPIA) für Vorgänge vorzubereiten, die „wahrscheinlich zu einem hohen Risiko für die Rechte und Freiheiten natürlicher Personen führen“. Microsoft-Produkte und -Dienste an sich machen keine Datenschutzfolgenabschätzung erforderlich. Da Microsoft-Produkte und-Dienste jedoch hochgradig anpassbar sind, kann je nach den Details Ihrer Microsoft-Konfiguration eine DPIA erforderlich sein. Microsoft hat keine Kontrolle über und wenig oder gar keine Einsichten in solche Informationen. Sie als Datenverantwortlicher müssen die geeignete Verwendung der Daten ermitteln.

## <a name="dpia-in-action"></a>Angewendete DPIA

Der DPIA-Leitfaden gilt für Office 365, Azure, Dynamics 365 und Microsoft-Support sowie Professional Services. Der Leitfaden umfasst Folgendes:

**Wann ist eine DPIA erforderlich?**

Die nachstehend aufgeführten Risikofaktoren sollten bei den Überlegungen zur Durchführung einer DPIA berücksichtigt werden. Weitere potenzielle Faktoren und weitere Details finden Sie in Teil 1 der einzelnen Richtlinien.  

- Eine systematische und umfassende Auswertung von Daten auf der Grundlage einer automatisierten Verarbeitung.  
- Verarbeitung spezieller Kategorien von Daten (Daten, aus denen Informationen hervorgehen, anhand derer eine natürliche Person eindeutig identifiziert werden kann) bzw. personenbezogener Daten über strafrechtliche Verurteilungen und Straftaten.
- Systematische Überwachung eines öffentlich zugänglichen Bereichs.

Die DSGVO stellt Folgendes klar: „Die Verarbeitung personenbezogener Daten sollte nicht als umfangreich gelten, wenn die Verarbeitung personenbezogene Daten von Patienten oder von Mandanten betrifft und durch einen einzelnen Arzt, sonstigen Angehörigen eines Gesundheitsberufes oder Rechtsanwalt erfolgt. In diesen Fällen sollte eine Datenschutz-Folgenabschätzung nicht zwingend vorgeschrieben sein.“

**Was ist für die Durchführung einer Datenschutzfolgenabschätzung erforderlich?**

Eine DPIA sollte spezifische Informationen zur beabsichtigten Verarbeitung bereitstellen. Darauf wird in Teil 2 des Leitfadens genauer eingegangen. Dazu gehören:

- Eine Bewertung der Notwendigkeit und Verhältnismäßigkeit der Datenverarbeitung in Bezug auf den Zweck der DPIA.  
- Bewertung der Risiken für die Rechte und Grundfreiheiten natürlicher Personen.
- Vorgesehene Maßnahmen zum Umgang mit den Risiken, Sicherheitsvorkehrungen, Sicherheitsmaßnahmen und Mechanismen zur Sicherstellung des Schutzes personenbezogener Daten und zur Veranschaulichung der Einhaltung des DSGVO.
- Zwecke der Verarbeitung  
- Kategorien verarbeiteter personenbezogener Daten  
- Datenaufbewahrung  
- Speicherort und Übermittlung personenbezogener Daten  
- Teilen von Daten mit Dritten  
- Teilen von Daten mit unabhängigen Dritten  
- Rechte betroffener Personen

## <a name="additional-considerations"></a>Weitere Überlegungen

Nachstehend finden Sie spezifische Details, die für Ihre Microsoft-Implementierung relevant sein können.

- [Office 365](gdpr-dpia-office365.md): Dieses Dokument gilt für Office 365-Anwendungen und -Dienste, einschließlich, aber nicht beschränkt auf Exchange Online, SharePoint Online, Yammer, Skype for Business und Power BI. Weitere Details finden Sie in den Tabellen [1](https://docs.microsoft.com/microsoft-365/compliance/gdpr-dpia-office365#part-1--determining-whether-a-dpia-is-needed) und [2](https://docs.microsoft.com/microsoft-365/compliance/gdpr-dpia-office365#part-2--contents-of-a-dpia).  
- [Azure](gdpr-dpia-azure.md): Kunden sind dazu angehalten, mit Ihren Datenschutzbeauftragten und Rechtsberatern zu arbeiten, um die Notwendigkeit und Inhalte aller DPIAs zu ermitteln, die mit der Verwendung von Microsoft Azure verbunden sind.  
- [Dynamics 365](gdpr-dpia-dynamics.md): Der Inhalt einer DPIA kann variieren, je nachdem, welche Dynamics 365-Tools Sie verwenden. Spezifische Details finden Sie in [Teil 2 – Inhalte einer DPIA](https://docs.microsoft.com/microsoft-365/compliance/gdpr-dpia-dynamics#part-2--contents-of-a-dpia).
- [Microsoft-Support und Professional Services](gdpr-dpia-prof-services.md): Professional Services führt keine bestimmte routinemäßige oder automatisierte Datenverarbeitung aus und ist nicht für die Verarbeitung spezieller Kategorien bzw. die Ausführung bestimmter Aufgaben vorgesehen, die das Überwachen von öffentlich zugänglichen Daten erleichtern oder erfordern. Details hierzu finden Sie in [Teil 1 – Bestimmen, ob eine DPIA erforderlich ist](https://docs.microsoft.com/microsoft-365/compliance/gdpr-dpia-prof-services#part-1--determining-whether-a-dpia-is-needed). Die Verantwortlichen müssen die oben genannten DPIA-Elemente sowie alle anderen relevanten Faktoren im Kontext der spezifischen Implementierungen und Verwendungen von Professional Services durch den Verantwortlichen berücksichtigen. Informationen zu Professional Services finden Sie in [Teil 2 – Inhalte einer DPIA](https://docs.microsoft.com/microsoft-365/compliance/gdpr-dpia-prof-services#part-2--contents-of-a-dpia).

## <a name="learn-more"></a>Weitere Informationen

- [Microsoft Trust Center](https://www.microsoft.com/trust-center/privacy/gdpr-overview)
