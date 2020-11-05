---
title: Azure and Dynamics 365-Benachrichtigungen bei Sicherheitsverletzungen im Rahmen der DSGVO
description: Hier erfahren Sie, wie Azure und Dynamics 365 Sie vor Verletzungen des Schutzes personenbezogener Daten schützen und wie Microsoft reagiert und Sie benachrichtigt, wenn eine Verletzung auftritt.
keywords: Azure, Microsoft 365, Dynamics 365, Microsoft 365-Dokumentation, DSGVO
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
ms.openlocfilehash: 0cdd3a2d8e158800cef534a1488df0f25e3d232f
ms.sourcegitcommit: d7975c391e03eeb96e29c1d02e77d2a1433ea67c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/05/2020
ms.locfileid: "48920259"
---
# <a name="azure-and-dynamics-365-breach-notification-under-the-gdpr"></a>Azure and Dynamics 365-Benachrichtigungen bei Sicherheitsverletzungen im Rahmen der DSGVO

Microsoft Azure nimmt seine Pflichten im Rahmen der Datenschutz-Grundverordnung (DSGVO) sehr ernst. Microsoft Azure ergreift umfassende Sicherheitsmaßnahmen, um vor Datenschutzverletzungen zu schützen. Diese umfassen sowohl physische und logische Sicherheitskontrollen als auch automatisierte Sicherheitsprozesse, umfassende Richtlinien zur Informationssicherheit und zum Datenschutz sowie Schulungen zur Sicherheit und zum Datenschutz für Mitarbeiter.

Sicherheit ist in Microsoft Azure von Grund auf integriert, beginnend mit dem [Security Development Lifecycle](https://www.microsoft.com/sdl/), einem obligatorischen Entwicklungsprozess, der benutzerdefinierte und standardmäßige Datenschutz-Methodologien umfasst. Das Leitprinzip der Sicherheitsstrategie von Microsoft besteht darin, vom Vorhandensein einer Datenschutzverletzung auszugehen, und stellt somit eine Erweiterung der Strategie für tiefgreifende, vorbeugende Sicherheit dar. Indem die Sicherheitsfunktionen von Azure ständig getestet werden, kann Microsoft neuen Bedrohungen immer einen Schritt voraus bleiben. Weitere Informationen zur Sicherheit bei Azure finden Sie in diesen [Ressourcen](https://www.microsoft.com/trustcenter/security/azure-security).

Microsoft verfügt über einen globalen, rund um die Uhr aktiven Service für die Reaktion auf Vorfälle, der daran arbeitet, die Auswirkungen von Angriffen gegen Microsoft Azure zu mindern. Microsoft nutzt in seinen Rechenzentren strenge Abläufe und Prozesse zur Verhinderung von nicht autorisiertem Zugriff, darunter 24-Stunden-Videoüberwachung, geschultes Sicherheitspersonal, Smartcards und biometrische Kontrollen. Dies wird durch mehrere Sicherheits- und Compliance-Audits bestätigt (z. B. [ISO/IEC 27018](offering-iso-27018.md)).

## <a name="detection-of-potential-breaches"></a>Erkennung potenzieller Sicherheitsverletzungen

Due to the nature of modern cloud computing, not all data breaches occurring in a customer cloud environment involve Microsoft Azure services. Microsoft employs a shared responsibility model for Azure services to define security and operational accountabilities. Shared responsibility is important when discussing security of a cloud service, because both the cloud services provider and the customer are accountable for portions of cloud security.

Microsoft does not monitor for or respond to security incidents within the customer's realm of responsibility. A customer-only security compromise would not be processed as an Azure security incident and would require the customer tenant to manage the response effort. Customer incident response may involve collaboration with Microsoft Azure [customer support](https://azure.microsoft.com/support/options/), given appropriate service contracts. Microsoft Azure bietet ebenfalls verschiedene Dienste an (z.B., [Azure Defender](https://azure.microsoft.com/services/security-center/)), die Kunden dazu nutzen können, Reaktionen auf Sicherheitsvorfälle zu entwickeln und zu verwalten.

Azure reagiert auf ein potenzielles Datenleck entsprechend dem Prozess für die Reaktion auf Sicherheitsvorfälle, der Teil des Vorfallmanagementplans von Microsoft Azure ist. Die Reaktion auf Sicherheitsvorfälle seitens Azure erfolgt in fünf Stufen: Erkennung, Analyse, Diagnose, Stabilisierung und Abschluss. Das Team für die Reaktion auf Sicherheitsvorfälle kann im Verlauf der Untersuchung zwischen den Stufen der Diagnose und der Stabilisierung wechseln. Nachfolgend finden Sie eine Übersicht über die Vorgehensweise bei Sicherheitsvorfällen:

|**Stage**|**Beschreibung**|
| ------- | ------------- |
| **_1 – Erkennung_* _ | Erste Anzeichen für einen potenziellen Vorfall. |
| _*_2 – Analyse_*_ | Ein abrufbereites Mitglied des Teams für die Reaktion auf Sicherheitsvorfälle analysiert die Auswirkungen und den Schweregrad des Ereignisses. Basierend auf den Nachweisen kann die Analyse zu einer Eskalation an das Sicherheitsteam führen. |
| _*_3 – Diagnose_*_ | Security response experts conduct the technical or forensic investigation, identify containment, mitigation, and workaround strategies. If the security team believes that customer data may have become exposed to an unlawful or unauthorized individual, execution of the Customer Incident Notification process begins in parallel. |
| _*_4 – Stabilisierung und Wiederherstellung_*_ | Das Team für die Reaktion auf Sicherheitsvorfälle erstellt einen Wiederherstellungsplan, um das Problem zu mindern. Schritte zur Eindämmung der Auswirkungen, wie die Isolierung der betroffenen Systeme, können sofort und parallel zur Diagnose ausgeführt werden. Zudem können längerfristige Maßnahmen zur Risikominderung geplant werden, die umgesetzt werden, sobald die unmittelbare Gefahr gebannt ist. |
| _*_5 – Abschluss und nachträgliche Analyse_*_ | Das Team für die Reaktion auf Sicherheitsvorfälle erstellt eine nachträgliche Analyse, die den Vorfall detailliert untersucht, mit dem Ziel, die vorhandenen Richtlinien und Prozesse zu überarbeiten, um ein erneutes Auftreten des Ereignisses zu verhindern. |

Das Whitepaper [Microsoft Azure Security Response in the Cloud](https://gallery.technet.microsoft.com/Azure-Security-Response-in-dd18c678) enthält weitere Informationen dazu, wie Microsoft Sicherheitsvorfälle in Azure untersucht, verwaltet und darauf reagiert.

Die Erkennungsprozesse von Microsoft Azure sind darauf ausgelegt, Ereignisse zu erkennen, welche die Vertraulichkeit, Integrität und Verfügbarkeit von Azure-Diensten gefährden. Verschiedene Ereignisse können eine Untersuchung auslösen:

- Automated system alerts via internal monitoring and alerting frameworks. These alerts could come in the way of signature-based alarms such as anti-malware, intrusion detection or via algorithms designed to profile expected activity and alert upon anomalies.
- Erstanbieterberichte von Microsoft-Diensten, die unter Microsoft Azure und Azure Government ausgeführt werden.
- Security vulnerabilities are reported to the [Microsoft Security Response Center (MSRC)](https://technet.microsoft.com/security/dn440717) via [secure@microsoft.com](mailto:secure@microsoft.com). MSRC works with partners and security researchers around the world to help prevent security incidents and to advance Microsoft product security.
- Kundenberichte über das [Kundenportal](https://www.windowsazure.com/support/contact/) oder das Management Portal von Microsoft Azure und Azure Government, die der Azure-Infrastruktur zugeordnete verdächtige Aktivitäten beschreiben (im Gegensatz zu Aktivitäten, die in den Verantwortungsbereich des Kunden fallen).
- Security [Red Team and Blue Team](https://azure.microsoft.com/blog/red-teaming-using-cutting-edge-threat-simulation-to-harden-the-microsoft-enterprise-cloud/) activity. This strategy uses a highly skilled Red Team of offensive Microsoft security experts to uncover and attack potential weaknesses in Azure. The security response Blue Team must detect and defend against the Red Team's activity. Both Red and Blue Team actions are used to verify that Azure security response efforts are effectively managing security incidents. Security Red Team and Blue Team activities are operated under rules of engagement to help ensure the protection of customer data.
- Eskalationen von Operatoren der Azure-Dienste. Microsoft-Mitarbeiter sind dahingehend geschult, potenzielle Sicherheitsprobleme zu identifizieren und zu eskalieren.

## <a name="azures-data-breach-response"></a>Reaktion auf Datenschutzverletzungen in Azure

Microsoft assigns the investigation appropriate priority and severity levels by determining the functional impact, recoverability, and information impact of the incident. Both the priority and severity may change over the course of the investigation, based on new findings and conclusions. Security events involving imminent or confirmed risk to customer data are treated as high severity and worked around the clock to resolution. 

Microsoft Azure kategorisiert die Auswirkungen des Vorfalls auf die Informationen in die folgenden Kategorien von Sicherheitsverletzungen:

| _ *Kategorie**             | **Definition**                                                                                                                   |
| ------------------------ | -------------------------------------------------------------------------------------------------------------------------------- |
| **_Keine_* _               | Es wurden keine Daten extrahiert, geändert, gelöscht oder anderweitig kompromittiert.                                                      |
| _*_Datenschutzverletzung_*_     | Es wurde auf vertrauliche personenbezogene Daten von Steuerzahlern, Mitarbeitern, Begünstigten etc. zugegriffen oder diese wurden extrahiert.                                |
| _*_Verletzung des Schutzes unternehmenseigener Daten_*_ | Es wurde auf nicht klassifizierte, unternehmenseigene Daten, z. B. geschützte kritische Infrastrukturdaten (Protected Critical Infrastructure Information, PCII), zugegriffen oder diese wurden extrahiert. |
| _*_Integritätsverlust_*_     | Vertrauliche oder unternehmenseigene Daten wurden geändert oder gelöscht.                                                                     |

Das Sicherheitsteam arbeitet mit Sicherheitstechnikern und -experten (Subject Matter Experts, SMEs) von Microsoft Azure zusammen, um das Ereignis basierend auf Fakten aus den gewonnenen Erkenntnissen zu klassifizieren. Ein Sicherheitsereignis kann wie folgt klassifiziert werden:

- _*False Positive**: An event that meets detection criteria but is found to be part of a normal business practice and may need to be filtered. The service team identifies the root cause for false positives and will address them in a systematic way using detection sources and fine-tuning them as needed.
- **Sicherheitsvorfall:** Ein Vorfall, bei dem ein unrechtmäßiger Zugriff auf Kundendaten oder Supportdaten, die auf Geräten oder in Einrichtungen von Microsoft gespeichert sind, bzw. ein nicht autorisierter Zugriff auf diese Geräte oder Einrichtungen erfolgt ist, der zu Verlust, Offenlegung oder Änderung von Kundendaten oder Supportdaten geführt hat.
- **Meldepflichtiger Sicherheitsvorfall/Datenschutzvorfall (Customer-Reportable Security Incident, CRSI):** Unrechtmäßiger oder nicht autorisierter Zugriff auf Systeme, Geräte oder Einrichtungen von Microsoft bzw. eine unrechtmäßige oder nicht autorisierte Verwendung dieser Systeme, Geräte oder Einrichtungen, der bzw. die zu Offenlegung, Änderung oder Verlust von Kundendaten geführt hat.
- **Privacy Breach** : A subtype of Security Incident involving personal data. Handling procedures are no different than a security incident.

For a CRSPI to be declared, Microsoft must determine that unauthorized access to customer data has or has likely occurred and/or that there is a legal or contractual commitment that notification must occur. It is desired, but not required, that specific customer impact, resource access, and repair steps be known. An incident is generally declared a CRSPI after the conclusion of the Diagnose stage of a security incident. However, the declaration may happen at any point that all pertinent information is available. The security incident manager must establish evidence beyond reasonable doubt that a reportable event has occurred to begin execution of the Customer Incident Notification Process.

Während der Untersuchung arbeitet das Sicherheitsteam eng mit globalen Rechtsberatern zusammen, um sicherzustellen, dass die Forensik entsprechend den gesetzlichen Verpflichtungen und Pflichten gegenüber dem Kunden ausgeführt wird. Es gibt zudem erhebliche Beschränkungen für das Anzeigen und Behandeln von System- und Kundendaten in verschiedenen Betriebsumgebungen. Sensible oder vertrauliche Daten sowie Kundendaten werden ohne explizite schriftliche Genehmigung des Vorfall-Managers, die im entsprechenden Vorfallsticket aufgezeichnet wird, nicht aus der Produktionsumgebung heraus übertragen.

Microsoft überprüft, ob das Risiko für Kunden und Unternehmen erfolgreich gebannt wurde und ob Abhilfemaßnahmen implementiert wurden. Bei Bedarf werden Notfallverfahren zum Beheben unmittelbarer Sicherheitsrisiken im Zusammenhang mit dem Ereignis ausgeführt.

Microsoft also completes an internal post-mortem for data breaches. As a part of this exercise, sufficiency of response and operating procedures are evaluated, and any updates that may be necessary to the Security Incident Response SOP or related processes are identified and implemented. Internal postmortems for data breaches are highly confidential records not available to customers. Postmortems may, however, be summarized and included in other customer event notifications. These reports are provided to external auditors for review as part of Azure's routine audit cycle.

## <a name="customer-notification"></a>Kundenbenachrichtigung

Microsoft Azure benachrichtigt Kunden und Aufsichtsbehörden vorgabengerecht über Datenschutzverletzungen. Microsoft baut auf eine starke interne Trennung des Betriebs von Azure. Datenflussprotokolle sind ebenfalls robust. Ein Vorteil dieses Designs ist, dass die meisten Vorfälle bestimmten Kunden zugeordnet werden können. Das Ziel ist, den betroffenen Kunden präzise, umsetzbare und zeitgerechte Informationen bereitzustellen, wenn der Schutz ihrer Daten verletzt wurde.

After the declaration of a CRSPI, the notification process takes place as expeditiously as possible while still considering the security risks of moving quickly. Generally, the process of drafting notifications occurs as the incident investigation is ongoing. Customer notices are delivered in no more than 72 hours from the time we declared a breach *except* in the following circumstances:

- Microsoft believes that the act of performing a notification increases the risk to other customers. For example, the act of notifying may tip off an adversary causing an inability to remediate.
- Andere ungewöhnliche oder extreme Umstände, die von der Rechtsabteilung Corporate External and Legal Affairs (CELA) und dem leitenden Vorfall-Manager von Microsoft überprüft werden.
- The 72-hour timeline may leave some incident details available. These are provided to customers and regulatory authorities as the investigation proceeds.

Microsoft Azure stellt Kunden detaillierte Informationen bereit, sodass sie interne Untersuchungen ausführen können ihre Verpflichtungen gegenüber Endbenutzern erfüllen können, ohne den Benachrichtigungsprozess übermäßig zu verzögern.

Die Benachrichtigung über eine Verletzung im Hinblick auf personenbezogene Daten wird dem Kunden auf einem von Microsoft gewählten Weg übermittelt, möglicherweise auch per E-Mail. Die Benachrichtigung über eine Datenschutzverletzung wird an die in Azure Defender hinterlegte Liste der Sicherheitskontakte übermittelt, die gemäß der [Implementierungsanleitung](https://docs.microsoft.com/azure/security-center/security-center-provide-security-contact-details) konfiguriert werden kann. Wenn in Azure Defender keine Kontaktdaten angegeben werden, wird die Benachrichtigung an einen oder mehrere Administratoren des Azure-Abonnements gesendet. Um sicherzustellen, dass die Benachrichtigung erfolgreich zugestellt ist, muss der Kunde sicherstellen, dass die administrativen Kontaktinformationen für jedes geltende Abonnement und im Online Services-Portal korrekt sind.

Das Microsoft Azure- oder Azure Government-Team kann auch entscheiden, zusätzliches Microsoft-Personal wie den Kundendienst und die Account Manager (AM) oder Technical Account Manager (TAM) des Kunden zu benachrichtigen. Diese Personen stehen häufig in enger Beziehung zum Kunden und können eine schnellere Problembehebung realisieren.

## <a name="microsoft-dynamics-365-built-in-security-features"></a>Microsoft Dynamics 365 – Integrierte Sicherheitsfeatures

Microsoft Dynamics 365 nutzt die Cloud-Service-Infrastruktur und integrierten Sicherheitsfeatures, um Daten mithilfe von Sicherheitsmaßnahmen und -mechanismen zu schützen. Darüber hinaus bietet Dynamics 365 effizienten Datenzugriff und Zusammenarbeit plus Datenintegrität und Datenschutz in den folgenden Bereichen: [Sichere Identität, Datenschutz, rollenbasierte Sicherheit und Bedrohungsmanagement](https://www.microsoft.com/trustcenter/security/dynamics365-security).

Das Microsoft Dynamics 365-Angebot befolgt dieselben technischen und organisatorischen Maßnahmen, die ein oder mehrere Microsoft Azure-Dienstteams zur Sicherung gegen Datenverletzungsprozesse ergreifen. Daher sind alle Informationen, die im Benachrichtigungsdokument "Microsoft Azure-Datenverletzung" dokumentiert sind, analog zu Microsoft Dynamics 365.

## <a name="learn-more"></a>Mehr erfahren

[Microsoft Trust Center](https://www.microsoft.com/trust-center/privacy/gdpr-overview)
