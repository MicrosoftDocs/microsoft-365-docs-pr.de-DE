---
title: Anträge betroffener Personen für Azure DevOps im Rahmen der DSGVO und des CCPA
keywords: Visual Studio Team Services, VSTS, Azure DevOps-Dokumentation, Datenschutz, DSGVO, CCPA
localization_priority: Priority
audience: itpro
ms.prod: devops
ms.topic: article
ms.date: 06/11/2018
author: robmazz
f1.keywords:
- NOCSH
ms.author: robmazz
manager: laurawi
ms.collection:
- GDPR
- M365-security-compliance
ms.workload:
- multiple
titleSuffix: Microsoft GDPR
ms.openlocfilehash: a43c2e874092de70535c0150f10870b8a071aafc
ms.sourcegitcommit: e741930c41abcde61add22d4b773dbf171ed72ac
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/07/2020
ms.locfileid: "42557975"
---
# <a name="azure-devops-services-data-subject-requests-for-the-gdpr-and-ccpa"></a>Anträge betroffener Personen für Azure DevOps Services im Rahmen der DSGVO und des CCPA

Die [Datenschutz-Grundverordnung (DSGVO)](https://ec.europa.eu/justice/data-protection/reform/index_en.htm) der Europäischen Union gewährt Personen, die in den Bestimmungen als *betroffene Personen* bezeichnet werden, Berechtigungen zum Verwalten der personenbezogenen Daten, die von einem *Datenverantwortlichen* erfasst werden. Ein Datenverantwortlicher oder nur *Verantwortlicher* ist ein Arbeitgeber oder eine andere Art von Behörde oder Organisation. Personenbezogene Daten sind im Rahmen der DSGVO sehr weitgefasst als Daten definiert, die sich auf eine identifizierte oder identifizierbare natürliche Person beziehen. Die DSGVO erteilt betroffenen Personen bestimmte Rechte für ihre personenbezogenen Daten. Dazu gehören das Kopieren der personenbezogenen Daten, das Anfordern von Korrekturen, das Einschränken der Verarbeitung, das Löschen oder das Erhalten in einem elektronischen Format, damit sie zu einem anderen Datenverantwortlichen bewegt werden können. Eine formale Anforderung von einer betroffenen Person an einen Datenverantwortlichen im Hinblick auf eine bestimmte Aktion für deren persönliche Daten wird als *Antrag einer betroffenen Person* bezeichnet.

In ähnlicher Weise bietet der California Consumer Privacy Act (CCPA) den kalifornischen Verbrauchern Datenschutzrechte und -pflichten, einschließlich von Rechten, die den Rechten von betroffenen Personen der DSGV entsprechen, wie z. B. das Recht auf Löschung, Zugriff und Empfang (Portabilität) der persönlichen Informationen.  Das CCPA ermöglicht außerdem bestimmte Offenlegungen, Schutz vor Diskriminierung bei der Wahl von Ausübungsrechten und Deaktivierungs-/Aktivierungsanforderungen für bestimmte Datentransfers, die als "Verkäufe" eingestuft werden. Die Definition von "Verkäufe" umfasst die Freigabe von Daten für eine angemessene Gegenleistung. Weitere Informationen zum CCPA finden Sie im ["California Consumer Privacy Act](offering-ccpa.md) und in den [häufig gestellten Fragen zum California Consumer Privacy Act](ccpa-faq.md).

Allgemeine Informationen zur DSGVO finden Sie im [DSGVO-Bereich des Service Trust-Portals](https://servicetrust.microsoft.com/ViewPage/GDPRGetStarted).

Dieser Leitfaden erläutert, wie Microsoft-Tools zum Exportieren oder Löschen von personenbezogenen Daten verwendet werden, die während einer authentifizierten (angemeldeten) Sitzung von Azure DevOps Services (vorher bekannt als Visual Studio Team Services) erfasst wurden.

## <a name="additional-privacy-information"></a>Zusätzliche Datenschutzinformationen

Die Artikel [Microsoft-Datenschutzbestimmungen](https://privacy.microsoft.com/privacystatement), [Online-Dienstbestimmungen (OST)](https://www.microsoft.com/licensing/product-licensing/products.aspx) und [DSGVO-Verpflichtungen von Microsoft](/legal/gdpr) beschreiben unsere Datenverarbeitungsmethoden.

## <a name="personal-data-we-collect"></a>Von uns erfasste personenbezogene Daten

Microsoft erfasst Daten von Benutzern zur Ausführung und Verbesserung der Azure DevOps Services. Die Azure DevOps Services erfassen zwei Kategorien von Daten – Kundendaten und vom System generierte Protokolle. Kundendaten umfassen vom Benutzer identifizierbare transaktionale und interaktionale Daten, die Azure DevOps Services zur Ausführung des Dienstes benötigt. Vom System generierte Protokolle enthalten Dienstverwendungsdaten, die für jeden Produktbereich und jede Produktfunktion aggregiert werden.

## <a name="delete-azure-devops-data"></a>Löschen Azure DevOps-Daten

Der erste Schritt zum Löschen von zugehörigen Azure DevOps Services-Kundendaten und zum Anonymisieren von personenbezogenen Daten, die sich in vom System generierten Protokollen befinden, ist das Schließen des Azure Active Directory (AAD)-Identitätskontos oder Microsoft Account (MSA). Azure DevOps Services ist ein Aufzeichnungssystem mit strengen Integritäts-, Nachverfolgbarkeits- und Überwachungsregeln. Diese bestehenden Verpflichtungen wirken sich auf die Lösch- und Aufbewahrungspflichten der DSGVO aus. Wenn Sie das Identitätskonto schließen, werden Artefakte und Aufzeichnungen, die mit der individuellen Identität im Azure DevOps Services-Konto verknüpft sind, nicht bearbeitet, entfernt oder geändert. Wir haben sichergestellt, dass alle verknüpften personenbezogenen Daten und vom System generierten Protokolle der Organisation aus unserem System entfernt werden, wenn eine komplette Azure DevOps-Organisation gelöscht wird (nach dem erforderlichen 30-tägigen Zeitraum für vorläufige Löschung der Azure DevOps-Organisation).

## <a name="export-azure-devops-data"></a>Exportieren Azure DevOps-Daten

Verantwortliche können Kundendaten und vom System generierte Protokolle der Betroffenen mit einer von zwei Methoden exportieren, je nach Identitätsanbieter (MSA oder AAD) zum Anmelden beim Azure DevOps Service.

- Benutzer, die sich über ein Konto registriert haben, das auf einem Azure-Mandanten basiert (z.B. ein AAD- oder MSA-Konto unter einem Azure-Abonnement), können die Anleitung unter [Azure-Anfragen von Betroffenen für die DSGVO](gdpr-dsr-azure.md) befolgen.

- Benutzer, die sich mit einer MSA-Identität authentifizieren, können diese [Datenschutzanfrage-Website](https://www.microsoft.com/concern/privacyrequest-msa) verwenden, um Aktivitätsdaten zu ihrer MSA-Identität für mehrere Microsoft-Dienste anzuzeigen. In diesem Szenario ist der Benutzer ein Verantwortlicher für die personenbezogenen Daten.

## <a name="export-or-delete-issues"></a>Exportieren oder Löschen von Problemen

Für AAD-Identitäten: Wenn beim Exportieren oder Löschen von Daten aus dem Azure-Portal Probleme auftreten, rufen Sie das Azure-Portalblatt **Hilfe + Support** auf, und übermitteln Sie unter **Abonnementverwaltung** > **Andere Sicherheits- und Complianceanforderung** > **Datenschutzblatt und DSGVO-Anforderungen** ein neues Ticket.

Für MSA-Identitäten: Wenn Probleme beim Exportieren von Daten von der Datenschutzanfrage-Website auftreten, melden Sie sich auf der [Datenschutzanfrage-Website](https://www.microsoft.com/concern/privacyrequest-msa) an, und senden Sie eine Anfrage zur Unterstützung durch das Microsoft-Datenschutzteam über das Anfrage-Webformular.

## <a name="learn-more"></a>Weitere Informationen

Microsoft ist bestrebt, sicherzustellen, dass Ihre Azure DevOps Services-Daten ohne Ausnahme sicher und privat bleiben. Lesen Sie das Whitepaper [Übersicht über Azure DevOps Services-Datenschutz](/vsts/articles/team-services-security-whitepaper?view=vsts), um weitere Informationen dazu zu erhalten, wie wir Ihre Azure DevOps Services-Daten schützen.

## <a name="see-also"></a>Siehe auch

- [DSGVO-Verpflichtungen von Microsoft für Kunden unserer allgemein verfügbaren Unternehmenssoftwareprodukte](https://docs.microsoft.com/legal/gdpr)
- [Microsoft Trust Center](https://www.microsoft.com/trust-center/privacy/gdpr-overview)
- [Service Trust Portal (STP)](https://servicetrust.microsoft.com/ViewPage/GDPRGetStarted)
- [Microsoft-Datenschutzdashboard](https://account.microsoft.com/privacy)
- [Microsoft Privacy Response Center](https://aka.ms/userprivacysite)
- [Azure-Anfragen von Betroffenen für die DSGVO](gdpr-dsr-azure.md)
