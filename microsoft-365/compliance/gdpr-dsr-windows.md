---
title: Anträge betroffener Personen zum Datenauftragsverarbeiterdienst für Windows im Rahmen der DSGVO und des CCPA
description: Erlernen Sie die Verwendung von Microsoft-Produkten, -Diensten und -Verwaltungstools, um nach personenbezogenen Daten zu suchen und auf DSRs zu reagieren.
keywords: Microsoft 365, Microsoft 365 Education, Microsoft 365-Dokumentation, DSGVO
localization_priority: Priority
ROBOTS: NOINDEX, NOFOLLOW
ms.prod: Microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.author: daniha
author: DaniHalfin
manager: dansimp
audience: itpro
ms.collection:
- GDPR
- M365-security-compliance
ms.openlocfilehash: 525b8b0783886a7449be72c89a2aa624afda9929
ms.sourcegitcommit: 3ddcf08e8deec087df1fe524147313f1cb12a26d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/02/2020
ms.locfileid: "45023597"
---
# <a name="data-processor-service-for-windows-data-subject-requests-for-the-gdpr-and-ccpa"></a>Anträge betroffener Personen zum Datenauftragsverarbeiterdienst für Windows im Rahmen der DSGVO und des CCPA 

>[!NOTE]
>Dieser Artikel richtet sich an Teilnehmer am Vorschauprogramm „Datenauftragsverarbeiterdienst für Windows“ und setzt die Zustimmung zu bestimmten Nutzungsbedingungen voraus. Wenn Sie mehr über das Programm erfahren und den Nutzungsbedingungen zustimmen möchten, wechseln Sie zu [https://aka.ms/dpswpublicpreview](https://aka.ms/dpswpublicpreview).

## <a name="introduction-to-data-subject-requests-dsrs"></a>Einführung in Anträge betroffener Personen 
Die Datenschutz-Grundverordnung (DSGVO) der EU räumt natürlichen Personen (in der Verordnung als _betroffene Personen_ bezeichnet) das Recht ein, vom Arbeitgeber oder einer anderen Einrichtung oder Organisation (_Datenverantwortlicher_ oder _Verantwortlicher_) erhobene personenbezogene Daten zu verwalten. Personenbezogene Daten sind in der DSGVO ganz allgemein als Daten definiert, die sich auf eine identifizierte oder identifizierbare natürliche Person beziehen. Die DSGVO gewährt betroffenen Personen bestimmte Rechte an ihren personenbezogenen Daten, z. B. das Recht auf Erhalt einer Kopie dieser personenbezogenen Daten, das Recht auf Korrektur der Daten, das Recht auf Einschränkung der Bearbeitung dieser Daten und das Recht auf Empfang dieser Daten in einem elektronischen Format, sodass sie an einen anderen Verantwortlichen übermittelt werden können. Ein von einer betroffenen Person formal gestellter Antrag an den Verantwortlichen, bestimmte Maßnahmen im Zusammenhang mit den personenbezogenen Daten der betroffenen Person zu ergreifen, wird als _Antrag einer betroffenen Person_ bezeichnet. 

In ähnlicher Weise bietet der California Consumer Privacy Act (CCPA) den kalifornischen Verbrauchern Datenschutzrechte und -pflichten, einschließlich von Rechten, die den Rechten von betroffenen Personen der DSGV entsprechen, wie z. B. das Recht auf Löschung, Zugriff und Empfang (Portabilität) der persönlichen Informationen. Das CCPA ermöglicht außerdem bestimmte Offenlegungen, Schutz vor Diskriminierung bei der Wahl von Ausübungsrechten und Deaktivierungs-/Aktivierungsanforderungen für bestimmte Datentransfers, die als "Verkäufe" eingestuft werden. Die Definition von "Verkäufe" umfasst die Freigabe von Daten für eine angemessene Gegenleistung. Weitere Informationen zum CCPA finden Sie im ["California Consumer Privacy Act](https://docs.microsoft.com/microsoft-365/compliance/offering-ccpa) und in den [häufig gestellten Fragen zum California Consumer Privacy Act](https://docs.microsoft.com/microsoft-365/compliance/ccpa-faq).

In diesem Leitfaden wird erläutert, wie Microsoft-Produkte, -Dienste und -Verwaltungstools verwendet werden können, um unseren als Datenverantwortliche handelnden Kunden dabei zu helfen, personenbezogene Daten zu finden und auf Anträge betroffener Personen zu reagieren. Dies umfasst das Suchen und Abrufen der personenbezogenen Daten, die in der Microsoft-Cloud gespeichert sind, sowie das weitere Verarbeiten dieser Daten. Im Folgenden finden Sie eine kurze Übersicht der in diesem Leitfaden beschriebenen Prozesse: 

1. **Zugriff** – rufen Sie personenbezogene Daten ab, die sich in der Microsoft-Cloud befinden, und erstellen Sie eine Kopie, die der betroffenen Person zur Verfügung gestellt werden kann, sofern dies beantragt wurde. 
2. **Löschung** – entfernen Sie personenbezogene Daten, die sich in der Microsoft-Cloud befinden, dauerhaft. 
3. **Export** – stellen Sie der betroffenen Person eine elektronische Kopie (in einem maschinenlesbaren Format) ihrer personenbezogenen Daten zur Verfügung. Personenbezogene Informationen gemäß CCPA sind alle Informationen, die eine identifizierte oder identifizierbare Person betreffen.

Personenbezogene Informationen gemäß CCPA sind alle Informationen, die eine identifizierte oder identifizierbare Person betreffen. Es wird nicht zwischen privaten, öffentlichen oder beruflichen Rollen einer Person unterschieden. Der definierte Begriff "persönliche Informationen" entspricht in etwa dem Begriff "persönliche Daten" unter der DSGVO. Allerdings umfasst das CCPA auch Familien- und Haushaltsdaten. Weitere Informationen zum CCPA finden Sie im ["California Consumer Privacy Act](https://docs.microsoft.com/microsoft-365/compliance/offering-ccpa) und in den [häufig gestellten Fragen zum California Consumer Privacy Act](https://docs.microsoft.com/microsoft-365/compliance/ccpa-faq).

In jedem Abschnitt dieses Leitfadens werden die Prozesse beschrieben, die ein als Datenverantwortlicher handelndes Unternehmen nutzen kann, um auf einen Antrag einer betroffenen Person bezüglich ihrer personenbezogenen Daten in der Microsoft-Cloud zu reagieren. 

## <a name="terminology"></a>Terminologie 
Nachfolgend finden Sie Definitionen von Begriffen, die für diesen Leitfaden relevant sind. 

* _Datenverantwortlicher_ – eine natürliche oder juristische Person, öffentliche Behörde, Agentur oder andere Stelle, die allein oder gemeinsam mit anderen die Zwecke und Mittel der Verarbeitung personenbezogener Daten bestimmt. Sofern die Zwecke und Mittel der Verarbeitung durch das Recht der Union oder der Mitgliedstaaten bestimmt werden, können der Datenverantwortliche bzw. die spezifischen Kriterien für dessen Benennung durch das Recht der Union oder des Mitgliedstaats angegeben werden. 

* _Personenbezogene Daten und betroffene Person_ – alle Informationen, die sich auf eine identifizierte oder identifizierbare natürliche Person („betroffene Person“) beziehen; als identifizierbar wird eine natürliche Person angesehen, die direkt oder indirekt, insbesondere mittels Zuordnung zu einer Kennung wie einem Namen, zu einer Kennnummer, zu Standortdaten, zu einer Online-Kennung oder zu einem oder mehreren besonderen Merkmalen identifiziert werden kann, die Ausdruck der physischen, physiologischen, genetischen, psychischen, wirtschaftlichen, kulturellen oder sozialen Identität dieser natürlichen Person sind. 

* _Auftragsverarbeiter_ – eine natürliche oder juristische Person, öffentliche Behörde, Agentur oder andere Stelle, die personenbezogene Daten im Auftrag des Datenverantwortlichen verarbeitet. 

* _Kundendaten_: Alle Daten, einschließlich aller Text-, Sound-, Video- oder Bilddateien, die Microsoft vom Kunden oder im Auftrag des Kunden durch Nutzung von Enterprise-Diensten bereitgestellt werden. 

* _Windows-Diagnosedaten_: Wichtige technische Daten von Windows-Geräten über das Gerät sowie die Leistung von Windows und verwandter Software. Sie werden verwendet, um Windows auf dem neuesten Stand, sicher, zuverlässig und leistungsfähig zu halten sowie Windows durch die aggregierte Analyse der Nutzung von Windows zu verbessern. Einige Beispiele für Windows-Diagnosedaten sind der Typ der verwendeten Hardware, die installierten Anwendungen mit ihrer jeweiligen Nutzung sowie Informationen zur Zuverlässigkeit von Gerätetreibern. Einige Windows-Komponenten und Apps bauen eine direkte Verbindung mit Microsoft-Diensten auf, aber bei den ausgetauschten Daten handelt es sich nicht um Windows-Diagnosedaten. So handelt es sich beispielsweise beim Erfassen des Standorts eines Benutzers für den lokalen Wetterbericht oder Nachrichten nicht um Windows-Diagnosedaten. 

## <a name="how-to-use-this-guide"></a>Verwenden dieses Leitfadens 

Bei Verwendung von Geräten, die beim Datenauftragsverarbeiterdienst für Windows registriert sind, generiert Windows einige Informationen, die als Windows-Diagnosedaten bezeichnet werden, um den Dienst bereitzustellen.

## <a name="windows-diagnostic-data"></a>Windows-Diagnosedaten 

Microsoft bietet Ihnen die Möglichkeit, auf Windows-Diagnosedaten, die mit der Nutzung des Datenauftragsverarbeiterdiensts für Windows durch den Benutzer in Verbindung stehen, zuzugreifen, diese zu löschen und zu exportieren.

>[!IMPORTANT]
>Die Möglichkeit zur Berichtigung von Windows-Diagnosedaten wird nicht unterstützt. Windows-Diagnosedaten stellen tatsächliche Aktionen dar, die innerhalb von Windows durchgeführt wurden, und Änderungen an diesen Daten würden die historische Erfassung von Aktionen kompromittieren und das Sicherheitsrisiko erhöhen sowie die Zuverlässigkeit beschädigen. Alle in diesem Dokument behandelten Daten werden als Windows-Diagnosedaten betrachtet. 

## <a name="executing-dsrs-against-windows-diagnostic-data"></a>Ausführen von DSRs an Windows-Diagnosedaten 

Microsoft bietet die Möglichkeit, auf bestimmte Windows-Diagnosedaten über das Azure-Portal und auch direkt über bereits vorhandene Anwendungsprogrammierschnittstellen (APIs) zuzugreifen, diese zu löschen und zu exportieren.

### <a name="step-1-access"></a>Schritt 1: Zugriff 

Der Mandantenadministrator ist die einzige Person in Ihrer Organisation, die auf Windows-Diagnosedaten zugreifen kann, die sich auf die Verwendung eines beim Datenauftragsverarbeiterdienst für Windows registrierten Geräts durch einen bestimmten Benutzer beziehen. Die für einen Zugriffsantrag abgerufenen Daten werden mittels Export in einem maschinell lesbaren Format sowie in Dateien bereitgestellt, durch die der Benutzer erkennen kann, welchen Geräten und Diensten die Daten zugeordnet sind. Die abgerufenen Daten enthalten keine Daten, die die Sicherheit oder Stabilität des Windows-Geräts beeinträchtigen könnten. 

Microsoft stellt eine Portal-Erfahrung bereit, über die der Mandantenadministrator des Unternehmenskunden Zugriffsanträge betroffener Personen verwalten kann. [Azure-DSR, Teil 2, Schritt 3: Export](https://docs.microsoft.com/microsoft-365/compliance/gdpr-dsr-azure#step-3-export), beschreibt, wie ein DSR-Zugriffsantrag mittels Export über das Azure-Portal durchzuführen ist.

### <a name="step-2-delete"></a>Schritt 2: Löschung 

Microsoft bietet eine Möglichkeit zum Ausführen benutzerbasierter DSR-Löschungsanträge, basierend auf dem Azure Active Directory-Objekt eines bestimmten Benutzers.

Für benutzerbasierte Löschungsanträge stellt Microsoft eine Portalerfahrung bereit, über die der Mandantenadministrator des Unternehmenskunden Löschungsanträge betroffener Personen verwalten kann. [Azure-DSR, Teil 1, Schritt 5: Löschung](https://docs.microsoft.com/microsoft-365/compliance/gdpr-dsr-azure#step-5-delete), beschreibt, wie ein DSR-Löschungsantrag über das Azure-Portal durchzuführen ist. 

Microsoft bietet die Möglichkeit, Benutzer direkt über eine bereits vorhandene Anwendungsprogrammierschnittstelle (API) zu löschen, wodurch wiederum Kundendaten gelöscht werden. Details werden in der [Referenzdokumentation der API](https://docs.microsoft.com/graph/api/directory-deleteditems-delete?view=graph-rest-beta) beschrieben. 

>[!IMPORTANT]  
>Durch das Löschen von gesammelten Daten wird die weitere Sammlung nicht beendet. Um die Datensammlung zu beenden, befolgen Sie das in der [jeweiligen Referenzdokumentation des entsprechenden Diensts](https://docs.microsoft.com/windows/privacy/configure-windows-diagnostic-data-in-your-organization#enterprise-management) beschriebene Verfahren.
 
 Darüber hinaus erfordern benutzerbasierte Löschungsanträge, dass das Benutzerkonto selbst gelöscht wird. 

### <a name="step-3-export"></a>Schritt 3: Export 

Der Mandantenadministrator ist die einzige Person in Ihrer Organisation, die auf Windows-Diagnosedaten zugreifen kann, die sich auf die Verwendung eines beim Datenauftragsverarbeiterdienst für Windows registrierten Geräts durch einen bestimmten Benutzer beziehen. Die für einen Exportantrag abgerufenen Daten werden in einem maschinell lesbaren Format bereitgestellt und in Dateien bereitgestellt, durch die der Benutzer erkennen kann, welchen Geräten und Diensten die Daten zugeordnet sind. Die abgerufenen Daten enthalten keine Daten, die die Sicherheit oder Stabilität des Windows-Geräts beeinträchtigen könnten. [Azure-DSR, Teil 2, Schritt 3: Export](https://docs.microsoft.com/microsoft-365/compliance/gdpr-dsr-azure#step-3-export), beschreibt, wie ein DSR-Exportantrag über das Azure-Portal durchzuführen ist. 

Microsoft bietet die Möglichkeit, Kundendaten direkt über eine bereits vorhandene Anwendungsprogrammierschnittstelle (API) zu exportieren. Details werden in der [Referenzdokumentation der API](https://docs.microsoft.com/graph/api/user-exportpersonaldata?view=graph-rest-1.0) beschrieben.

## <a name="notify-about-exporting-or-deleting-issues"></a>Benachrichtigung über Probleme beim Exportieren oder Löschen 

Wenn beim Exportieren oder Löschen von Daten aus dem Azure-Portal Probleme auftreten, rufen Sie das Azure-Portalblatt **Hilfe + Support** auf, und übermitteln Sie unter **Abonnementverwaltung > Andere Sicherheits- und Complianceanforderung > Datenschutzblatt und DSGVO-Anforderungen** ein neues Ticket. 
