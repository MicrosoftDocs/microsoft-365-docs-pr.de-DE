---
title: Benachrichtigung bei Sicherheitsverletzungen
description: Lernen Sie, wie Microsoft-Dienste Sie vor Verletzungen des Schutzes personenbezogener Daten schützen und wie Microsoft reagiert und Sie benachrichtigt, wenn eine Verletzung auftritt.
keywords: Microsoft 365, Microsoft 365 Education, Microsoft 365-Dokumentation, DSGVO
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
ms.custom:
- seo-marvel-mar2020
titleSuffix: Microsoft GDPR
ms.openlocfilehash: a671fc9234f76c63ff7336369c87e680a4432cc3
ms.sourcegitcommit: d7975c391e03eeb96e29c1d02e77d2a1433ea67c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/05/2020
ms.locfileid: "48920289"
---
# <a name="gdpr-breach-notification"></a>Benachrichtigung über DSGVO-Verstöße

The General Data Protection Regulation (GDPR) introduces new rules for organizations that offer goods and services to people in the European Union (EU), or that collect and analyze data for EU residents no matter where you or your enterprise are located. Additional details can be found in the [GDPR Summary topic](gdpr.md). This document leads you to information on the completion of Breach Notifications under the GDPR using Microsoft products and services.

## <a name="what-constitute-a-breach-of-personal-data-under-the-gdpr"></a>Was stellt eine Verletzung personenbezogener Daten im Rahmen der DSGVO dar?

Personal data means any information related to an individual that can be used to identify them directly or indirectly. A personal data breach is 'a breach of security leading to the accidental or unlawful destruction, loss, alteration, unauthorized disclosure of, or access to, personal data transmitted, stored, or otherwise processed'.

## <a name="terminology"></a>Begrifflichkeiten

Hilfreiche Definitionen für DSGVO-Ausdrücke, die in diesem Dokument verwendet werden:

- *Datenverantwortlicher (Verantwortlicher)* : eine juristische Person, Behörde, Einrichtung oder andere Stelle, die allein oder gemeinsam mit anderen über die Zwecke und Mittel der Verarbeitung von personenbezogenen Daten entscheidet.  
- *Personenbezogene Daten* und *betroffene Person* : alle Informationen, die sich auf eine identifizierte oder identifizierbare natürliche Person (betroffene Person) beziehen; als identifizierbar wird eine natürliche Person angesehen, die direkt oder indirekt identifiziert werden kann.  
- *Auftragsverarbeiter* : eine natürliche oder juristische Person, Behörde, Einrichtung oder andere Stelle, die personenbezogene Daten im Auftrag des Verantwortlichen verarbeitet.  
- *Kundendaten* : Daten, die während des regulären Geschäftsbetriebs erstellt und gespeichert werden.

## <a name="microsoft-and-breach-notification"></a>Microsoft und Benachrichtigungen bei Datenschutzverletzungen

Microsoft takes its obligations under the General Data Protection Regulation (GDPR) seriously. A security incident/data breach refers to events such as unlawful access to customer's data stored on Microsoft equipment or in Microsoft facilities, or unauthorized access to such that has the potential to result in the loss, disclosure, or alteration of customer data.

As a data processor, Microsoft ensures that service customers are able to meet the GDPR's breach notification requirements as data controllers. Our notification provides the information needed to make that assessment. Microsoft notifies customers of any personal data breach, except for those cases where personal data is confirmed to be unintelligible (for example, encrypted data where integrity of the keys is confirmed).

Data controllers are responsible for assessing risks to data privacy and determining whether a breach requires notification of a customer's DPA. Microsoft provides the information needed, along with your GDPR compliance policy, to make that assessment.

Initial notification includes a description of the nature of the breach, approximate user impact, and mitigation steps (if applicable). If our investigation is not complete at the time of initial notification, we will indicate next steps and timelines for subsequent communication. For more information about how Microsoft detects and responds to a breach of personal data, see [Data Breach Notification Under the GDPR](https://servicetrust.microsoft.com/ViewPage/GDPRBreach) in the Service Trust Portal.

Details zur Benachrichtigung über Datenschutzverletzungen für bestimmte Microsoft-Produkte und -Dienste finden Sie nachstehend.
  
1. **[Office 365](gdpr-breach-Office365.md)**  
    Microsoft invests extensively in systems, processes, and personnel to reduce the likelihood of personal data breach and to quickly detect and mitigate consequence of breach if it does occur. Additional details can be read at [Office 365 Investments in Data Security](https://docs.microsoft.com/microsoft-365/compliance/gdpr-breach-office365#office-365-investments-in-data-security).

    A customer may become aware of a breach and wish to contact Microsoft. In this case, notify Microsoft Support, which will then interface with engineering teams for more information.

2. **[Azure und Dynamics 365](gdpr-breach-azure-dynamics.md)**  
    Microsoft verfügt über einen rund um die Uhr verfügbaren weltweiten Notfalldienst, der dafür verantwortlich ist, die Auswirkungen von Angriffen auf Microsoft Azure und Dynamics 365 abzufangen.

    - *Erkennung von Sicherheitsverletzungen* : Weil Microsoft und der Kunde beide Sicherheitsverpflichtungen haben, setzen Azure-Dienste eine Modell der geteilten Verantwortung ein, um die Sicherheits- und Aufgabenrechenschaftspflichten zu definieren. In den Bereichen, für die der Kunde verantwortlich ist, überwacht Microsoft Sicherheitsvorfälle nicht und reagiert auch auf diese nicht. Die Reaktion auf Sicherheitsvorfälle des Kunden kann, unter Voraussetzung geeigneter Dienstleistungsverträge, eine Zusammenarbeit mit Azure [Kundendienst](https://azure.microsoft.com/support/options/) beinhalten. Microsoft Azure bietet ebenfalls verschiedene Dienste an (z.B. [Azure Defender](https://azure.microsoft.com/services/security-center/)), die Kunden dazu nutzen können, Reaktionen auf Sicherheitsvorfälle zu entwickeln und zu verwalten.

        For a list of events that trigger a breach investigation in Microsoft Azure, see [Detection of Potential Breaches](https://docs.microsoft.com/microsoft-365/compliance/gdpr-breach-azure-dynamics#detection-of-potential-breaches). [Azure and Breach Notification under the GDPR](gdpr-breach-azure-dynamics.md) further details how Microsoft investigates, manages, and responds to security incidents within Azure.

    - *Data Breach Response* : Microsoft determines appropriate priority and severity levels of a breach by investigating the functional impact, recoverability, and information impact of the incident. Priority and severity may change over the course of the investigation, based on new findings and conclusions. Microsoft's security response team works closely with global legal advisors to help ensure that forensics are performed in accordance with legal obligations and commitments to customers. These processes are detailed in [Azure's Data Breach Response](https://docs.microsoft.com/microsoft-365/compliance/gdpr-breach-azure-dynamics#azures-data-breach-response).

    - *Customer Notification* : Microsoft Azure notifies customers and regulatory authorities of data breaches as required. Customer notices are delivered in no more than 72 hours from the time we declared a breach except for the following circumstances:

        - Microsoft ist der Meinung, dass eine Benachrichtigung das Risiko für andere Kunden erhöht.
        - The 72-hour timeline may leave some incident details available. These details will be provided to you as the investigation proceeds.

        Weitere Details finden Sie unter [Kundenbenachrichtigung](https://docs.microsoft.com/microsoft-365/compliance/gdpr-breach-azure-dynamics#customer-notification).

3. **[Microsoft-Support und Professional Services](gdpr-breach-Microsoft-Support-Professional-Services.md)**  
    The nature of professional services means that some data protection incidents may fall within the customer's realm of responsibility. When Microsoft Professional Services identifies a data protection incident, it follows documented industry standard response plan as outlined in [Scope & Limits of Data Protection Incident Response Process](https://docs.microsoft.com/microsoft-365/compliance/gdpr-breach-microsoft-support-professional-services#scope--limits-of-data-protection-incident-response-process).

## <a name="breach-notification-admin-tools"></a>Administratortools zur Benachrichtigung bei Sicherheitsverletzungen

- **Legen Sie den Datenschutzkontakt Ihrer Organisation fest** : Mandantenadministratoren können das [Azure Active Directory-Verwaltungsportal](https://go.microsoft.com/fwlink/p/?linkid=2052736) verwenden, um den Datenschutzkontakt Ihrer Organisation für den Fall zu definieren, dass Microsoft mit diesen Personen kommunizieren muss.

## <a name="learn-more"></a>Weitere Informationen

- [Microsoft Trust Center](https://www.microsoft.com/trust-center/privacy/gdpr-overview)
