---
title: Benachrichtigung des Datenauftragsverarbeiterdiensts für Windows Enterprise gemäß DSGVO
description: Wie der Datenauftragsverarbeiterdienst für Windows Enterprise Schutz vor Datenschutzverletzungen für persönliche Daten bietet und wie Microsoft reagiert und Sie benachrichtigt, wenn eine Datenschutzverletzung auftritt.
keywords: Datenauftragsverarbeiterdienst für Windows Enterprise, Microsoft 365, Microsoft 365-Dokumentation, DSGVO
localization_priority: Priority
ROBOTS: NOINDEX, NOFOLLOW
ms.prod: microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.author: siosulli
author: DaniHalfin
manager: dansimp
audience: itpro
ms.collection:
- GDPR
- M365-security-compliance
ms.openlocfilehash: 5d0a5563de2443e5af0f3b7efda0947d4f669cee
ms.sourcegitcommit: e03bc2945e63f7f2638257e530056ae9283b45d9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/13/2020
ms.locfileid: "49070899"
---
# <a name="data-processor-service-for-windows-enterprise-breach-notification-under-the-gdpr"></a>Benachrichtigung des Datenauftragsverarbeiterdiensts für Windows Enterprise über eine Datenschutzverletzung gemäß DSGVO

>[!NOTE]
>This topic is intended for participants in the data processor service for Windows Enterprise preview program and requires acceptance of specific terms of use. To learn more about the program and agree to the terms of use, see [https://aka.ms/WindowsEnterprisePublicPreview](https://aka.ms/WindowsEnterprisePublicPreview).

Microsoft data processor service for Windows Enterprise takes its obligations under the General Data Protection Regulation (GDPR) seriously. Microsoft data processor service for Windows Enterprise takes extensive security measures to protect against data breaches. These include dedicated threat management teams that proactively anticipate, prevent, and mitigate malicious access.  Internal security measures such as port scanning, perimeter vulnerability scanning, and intrusion detection detect and prevent malicious access, as well as automated security processes, comprehensive information security and privacy policies, and security and privacy training for all personnel. 

Security is built into the Microsoft data processor service for Windows Enterprise from the ground up, starting with the [Security Development Lifecycle](https://www.microsoft.com/sdl/), a mandatory development process that incorporates privacy-by-design and privacy-by-default methodologies. The guiding principle of Microsoft's security strategy is to 'assume breach', which is an extension of the defense-in-depth strategy. By constantly challenging the security capabilities of the data processor service for Windows Enterprise, Microsoft can stay ahead of emerging threats. For more information on the data processor service for Windows Enterprise security, please review these [resources](https://www.microsoft.com/TrustCenter/Security/windows10-security) the data processor service for Windows Enterprise responds to a potential data breach according to the security incident response process. The data processor service for Windows Enterprise security incident response is implemented using a five-stage process: Detect, Assess, Diagnose, Stabilize, and Close. The Security Incident Response Team may alternate between the diagnose and stabilize stages as the investigation progresses. An overview of the security incident response process is below: 

|**Stage**|**Beschreibung**|
| ------- | ------------- |
| **_1 – Erkennung_* _ | Erste Anzeichen für einen potenziellen Vorfall. |
| _*_2 – Analyse_*_ | Ein abrufbereites Mitglied des Teams für die Reaktion auf Sicherheitsvorfälle analysiert die Auswirkungen und den Schweregrad des Ereignisses. Basierend auf den Nachweisen kann die Analyse zu einer Eskalation an das Sicherheitsteam führen. |
| _*_3 – Diagnose_*_ | Security response experts conduct the technical or forensic investigation, identify containment, mitigation, and workaround strategies. If the security team believes that customer data may have become exposed to an unlawful or unauthorized individual, execution of the Customer Incident Notification process begins in parallel. |
| _*_4 – Stabilisierung und Wiederherstellung_*_ | Das Team für die Reaktion auf Sicherheitsvorfälle erstellt einen Wiederherstellungsplan, um das Problem zu mindern. Schritte zur Eindämmung der Auswirkungen, wie die Isolierung der betroffenen Systeme, können sofort und parallel zur Diagnose ausgeführt werden. Zudem können längerfristige Maßnahmen zur Risikominderung geplant werden, die umgesetzt werden, sobald die unmittelbare Gefahr gebannt ist. |
| _*_5 – Abschluss und nachträgliche Analyse_*_ | Das Team für die Reaktion auf Sicherheitsvorfälle erstellt eine nachträgliche Analyse mit den Details des Vorfalls, anhand derer Richtlinien, Verfahren und Prozesse geprüft werden sollen, um ein erneutes Auftreten des Ereignisses zu verhindern. |

The detection processes used by Microsoft data processor service for Windows Enterprise are designed to discover events that risk the confidentiality, integrity, and availability of the data processor service for Windows Enterprise. Several events can trigger an investigation: 

 - Automated system alerts via internal monitoring and alerting frameworks. These alerts could come in the way of signature-based alarms such as anti-malware, intrusion detection or via algorithms designed to profile expected activity and alert upon anomalies.
 - Erstanbieterberichte von Microsoft-Diensten, die unter Microsoft Azure und Azure Government ausgeführt werden.
 - Security vulnerabilities are reported to the [Microsoft Security Response Center (MSRC)](https://technet.microsoft.com/security/dn440717) via [secure@microsoft.com] (mailto:secure@microsoft.com). MSRC works with partners and security researchers around the world to help prevent security incidents and to advance Microsoft product security.
 - Kundenberichte über das Kundenportal oder das Management Portal von Microsoft Azure und Azure Government, die der Azure-Infrastruktur zugeordnete verdächtige Aktivitäten beschreiben (im Gegensatz zu Aktivitäten, die in den Verantwortungsbereich des Kunden fallen).
 - Security [Red Team and Blue Team](https://azure.microsoft.com/blog/red-teaming-using-cutting-edge-threat-simulation-to-harden-the-microsoft-enterprise-cloud/) activity. This strategy uses a highly skilled Red Team of offensive Microsoft security experts to uncover and attack potential weaknesses in Azure. The security response Blue Team must detect and defend against the Red Team’s activity. Both Red and Blue Team actions are used to verify that Azure security response efforts are effectively managing security incidents. Security Red Team and Blue Team activities are operated under rules of engagement to help ensure the protection of customer data.
 - Eskalationen von Operatoren der Azure-Dienste. Microsoft-Mitarbeiter sind dahingehend geschult, potenzielle Sicherheitsprobleme zu identifizieren und zu eskalieren.

 ## <a name="data-processor-service-for-windows-enterprise-data-breach-response"></a>Reaktion des Datenauftragsverarbeiterdiensts für Windows Enterprise auf eine Datenschutzverletzung 

 Microsoft assigns the investigation appropriate priority and severity levels by determining the functional impact, recoverability, and information impact of the incident. Both the priority and severity may change over the course of the investigation, based on new findings and conclusions. Security events involving imminent or confirmed risk to customer data are treated as high severity and worked around the clock to resolution. Microsoft data processor service for Windows Enterprise categorizes the information impact of the incident into the following breach categories: 

| _ *Kategorie**             | **Definition**                                                                                                                   |
| ------------------------ | -------------------------------------------------------------------------------------------------------------------------------- |
| **_Keine_* _               | Es wurden keine Daten entfernt, geändert, gelöscht oder anderweitig kompromittiert. |
| _*_Datenschutzverletzung_*_     | Es wurde auf vertrauliche personenbezogene Daten von Steuerzahlern, Mitarbeitern, Begünstigten etc. zugegriffen oder diese wurden entfernt. |
| _*_Verletzung des Schutzes unternehmenseigener Daten_*_ | Es wurde auf nicht klassifizierte, unternehmenseigene Daten, z. B. geschützte kritische Infrastrukturdaten (Protected Critical Infrastructure Information, PCII), zugegriffen oder diese wurden entfernt. |
| _*_Integritätsverlust_*_     | Vertrauliche oder unternehmenseigene Daten wurden geändert oder gelöscht. |

The Security Response Team works with Microsoft data processor service for Windows Enterprise Security Engineers and SMEs to classify the event based on factual data from the evidence. A security event may be classified as: 

 - _*False Positive**: An event that meets detection criteria but is found to be part of a normal business practice and may need to be filtered. The service team will identify the root cause for false positives and will address them in a systematic way leveraging detection sources and fine-tuning them as needed. 
 - **Sicherheitsvorfall:** Ein Vorfall, bei dem ein unrechtmäßiger Zugriff auf Kundendaten oder Supportdaten, die auf Geräten oder in Einrichtungen von Microsoft gespeichert sind, bzw. ein nicht autorisierter Zugriff auf diese Geräte oder Einrichtungen erfolgt ist, der zu Verlust, Offenlegung oder Änderung von Kundendaten oder Supportdaten geführt hat. 
 - **Meldepflichtiger Sicherheitsvorfall (Customer-Reportable Security Incident, CRSI)**: Unrechtmäßiger oder nicht autorisierter Zugriff auf Systeme, Geräte oder Anlagen von Microsoft bzw. deren Verwendung, der bzw. die zu Offenlegung, Änderung oder Verlust von Kundendaten geführt hat. 
 - **Privacy Breach**: A subtype of Security Incident involving personal data. Handling procedures are no different than a security incident. 

 Damit ein CRSI erklärt werden kann, muss Microsoft bestimmen, dass ein nicht autorisierter Zugriff auf Kundendaten erfolgt ist oder sehr wahrscheinlich erfolgt ist und/oder dass eine rechtliche oder vertragliche Meldepflicht besteht. Es ist wünschenswert, aber nicht erforderlich, dass bestimmte Kundenauswirkungen, Ressourcenzugriff und Schritte zur Behebung bekannt sind. Ein Vorfall wird im Allgemeinen nach Abschluss der Diagnosestufe eines Sicherheitsvorfalls zu einem CRSI erklärt. Die Erklärung kann aber zu einem beliebigen Zeitpunkt erfolgen, sofern alle relevanten Informationen zur Verfügung stehen. Der Manager des Sicherheitsvorfalls muss zweifelsfrei nachweisen, dass ein meldepflichtiges Ereignis aufgetreten ist, um mit der Ausführung des Prozesses zur Benachrichtigung des Kunden über den Sicherheitsvorfall zu beginnen. 

Während der Untersuchung arbeitet das Sicherheitsteam eng mit globalen Rechtsberatern zusammen, um sicherzustellen, dass die Forensik entsprechend den gesetzlichen Verpflichtungen und Pflichten gegenüber dem Kunden ausgeführt wird. Es gibt zudem erhebliche Beschränkungen für das Anzeigen und Behandeln von System- und Kundendaten in verschiedenen Betriebsumgebungen. Sensible oder vertrauliche Daten sowie Kundendaten werden ohne explizite schriftliche Genehmigung des Vorfall-Managers, die im entsprechenden Vorfallsticket aufgezeichnet wird, nicht aus der Produktionsumgebung heraus übertragen. 

Microsoft überprüft, ob das Risiko für Kunden und Unternehmen erfolgreich gebannt wurde und ob Abhilfemaßnahmen implementiert wurden. Bei Bedarf werden Notfallverfahren zum Beheben unmittelbarer Sicherheitsrisiken im Zusammenhang mit dem Ereignis ausgeführt. 

Microsoft also completes an internal post-mortem for data breaches. As a part of this exercise, sufficiency of response and operating procedures are evaluated, and any updates that may be necessary to the Security Incident Response SOP or related processes are identified and implemented. Internal postmortems for data breaches are highly confidential records not available to customers. Postmortems may, however, be summarized and included in other customer event notifications. These reports are provided to external auditors for review as part of the data processor service for Windows Enterprise routine audit cycle. 

## <a name="customer-notice"></a>Kundenbenachrichtigung

Microsoft data processor service for Windows Enterprise notifies customers and regulatory authorities of data breaches as required. Microsoft relies on heavy internal compartmentalization in the operation of the data processor service for Windows Enterprise. Data flow logs are also robust. As a benefit of this design, most incidents can be scoped to specific customers. The goal is to provide impacted customers with an accurate, actionable, and timely notice when their data has been breached. 

After the declaration of a CRSI, the notification process takes place as expeditiously as possible while still considering the security risks of moving quickly. Generally, the process of drafting notifications occurs as the incident investigation is ongoing. Customer notices are delivered in no more than 72 hours from the time we declared a breach except for the following circumstances: 

 - Microsoft ist der Meinung, dass eine Benachrichtigung das Risiko für andere Kunden erhöht. Beispielsweise wenn durch die Benachrichtigung der Übeltäter gewarnt und der Schaden daraufhin nicht mehr behoben werden kann. 
 - Andere ungewöhnliche oder extreme Umstände, die von der Rechtsabteilung Corporate External and Legal Affairs (CELA) und dem leitenden Vorfall-Manager von Microsoft überprüft werden. 

 Der Microsoft-Datenauftragsverarbeiterdienst für Windows Enterprise bietet Kunden ausführliche Informationen, sodass sie interne Untersuchungen ausführen können und die Erfüllung von Verpflichtungen gegenüber Endbenutzern erleichtert wird, ohne den Benachrichtigungsprozess übermäßig zu verzögern. 

Die Benachrichtigung über eine Verletzung im Hinblick auf personenbezogene Daten wird dem Kunden auf einem von Microsoft gewählten Weg übermittelt, möglicherweise auch per E-Mail. Die Benachrichtigung über eine Datenschutzverletzung wird an die in Azure Defender hinterlegte Liste der Sicherheitskontakte übermittelt, die gemäß der [Implementierungsanleitung](https://docs.microsoft.com/azure/security-center/security-center-provide-security-contact-details) konfiguriert werden kann. Wenn in Azure Defender keine Kontaktdaten angegeben werden, wird die Benachrichtigung an einen oder mehrere Administratoren des Azure-Abonnements gesendet. Um sicherzustellen, dass die Benachrichtigung erfolgreich zugestellt ist, muss der Kunde sicherstellen, dass die administrativen Kontaktinformationen für jedes geltende Abonnement und im Online Services-Portal korrekt sind.

Das Team des Datenauftragsverarbeiterdiensts für Windows Enterprise kann auch entscheiden, zusätzliches Microsoft-Personal wie den Kundendienst und die Account Manager (AM) oder Technical Account Manager (TAM) des Kunden zu benachrichtigen. Diese Personen stehen häufig in enger Beziehung zum Kunden und können eine schnellere Problembehebung realisieren. 

Weitere Informationen darüber, wie Microsoft eine Verletzung des Schutzes personenbezogener Daten erkennt und darauf reagiert, finden Sie im Service Trust Portal unter [Benachrichtigung bei Datenschutzverletzungen im Rahmen der DSGVO](https://servicetrust.microsoft.com/ViewPage/GDPRBreach).
