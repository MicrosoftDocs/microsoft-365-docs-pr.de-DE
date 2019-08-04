---
title: Anträge betroffener Personen im Rahmen der DSGVO
description: ''
keywords: Microsoft 365, Microsoft 365 Education, Microsoft 365-Dokumentation, DSGVO
localization_priority: Priority
ms.prod: Microsoft-365-enterprise
ms.topic: article
ms.author: robmazz
author: robmazz
manager: laurawi
audience: itpro
ms.collection: GDPR
ms.openlocfilehash: dc4352ac14f42a227f1572b0c7f1442aa4dec838
ms.sourcegitcommit: c201f5cc13d501e5207ebad166e42f90260af0c4
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/19/2019
ms.locfileid: "35078905"
---
# <a name="data-subject-requests-and-the-gdpr"></a>Anfragen von betroffenen Personen und die DSGVO

Die Datenschutz-Grundverordnung (DSGVO) führt neue Regeln für Unternehmen, Regierungsbehörden, gemeinnützige Organisationen sowie andere Organisationen ein, die Waren und Dienstleistungen in der Europäischen Union (EU) anbieten oder Daten von in der EU ansässigen natürlichen Personen erfassen und analysieren. Die DSGVO gilt unabhängig von Ihrem Wohnsitz und dem Sitz Ihres Unternehmens. Weitere Details finden Sie in der [Zusammenfassung zum Thema DSGVO](gdpr.md). <br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWs1SI] 

Dieses Dokument führt Sie zu Informationen zur Bearbeitung von Anfragen von betroffenen Personen (Datensubjekten) im Rahmen der DSGVO unter Verwendung von Microsoft-Produkten und -Diensten.

- [Office 365](gdpr-dsr-Office365.md)
- [Azure](gdpr-dsr-Azure.md)
- [Intune](gdpr-dsr-Intune.md)
- [Dynamics 365](gdpr-dsr-Dynamics365.md)
- [Visual Studio-Produktfamilie](gdpr-dsr-visual-studio-family.md)
- [Azure DevOps Services](gdpr-dsr-vsts.md)
- [Microsoft-Support und Professional Services](gdpr-dsr-prof-services.md)

## <a name="terminology"></a>Begrifflichkeiten

Hilfreiche Definitionen für DSGVO-Ausdrücke, die in diesem Dokument verwendet werden:

- *Datenverantwortlicher (Verantwortlicher)*: eine juristische Person, eine öffentliche Stelle, eine Behörde oder eine andere Stelle, die allein oder zusammen mit anderen den Zweck und die Mittel für die Verarbeitung personenbezogener Daten bestimmt.  
- *Personenbezogene Daten * und *betroffene Person (oder Datensubjekt) *: alle Informationen, die sich auf eine bestimmte oder identifizierbare natürliche Person beziehen (betroffene Person); eine identifizierbare natürliche Person ist eine Person, die direkt oder indirekt identifiziert werden kann.  
- *Verarbeiter*: eine natürliche oder juristische Person, eine öffentliche Behörde, eine Agentur oder eine andere Stelle, die personenbezogene Daten im Auftrag des Verantwortlichen verarbeitet.  
- *Kundendaten*: Daten, die bei den tagtäglichen Geschäftsausführung erstellt und gespeichert werden.

## <a name="what-is-a-dsr"></a>Was sind Anfragen von betroffenen Personen?

Die Allgemeine Datenschutz-Grundverordnung (DSGVO) räumt natürlichen Personen (in der Verordnung als betroffene Personen bezeichnet) das Recht ein, vom Arbeitgeber oder einer anderen Einrichtung oder Organisation ( Datenverantwortlicher oder Verantwortlicher) erhobene personenbezogene Daten zu verwalten. Die DSGVO gewährt betroffenen Personen bestimmte Rechte an ihren personenbezogenen Daten. Es sind dies das Recht auf Erhalt einer Kopie dieser Daten, das Recht auf Korrektur der Daten, das Recht auf Beschränkung der Bearbeitung dieser Daten und das Recht auf Empfang dieser Daten in einem elektronischen Format, sodass sie an einen anderen Verantwortlichen übermittelt werden können.

Als Verantwortlicher sind Sie verpflichtet, jede Datensubjektanfrage sofort zu überprüfen und darauf zu reagieren, und zwar entweder, indem Sie die angeforderte Maßnahme ergreifen oder indem Sie erläutern, warum der Anfrage der betroffenen Person seitens des Verantwortlichen nicht nachgekommen werden kann. Ein Verantwortlicher sollte sich mit seinen eigenen Rechts- oder Complianceberatern hinsichtlich der geeigneten Disposition bezüglich einer bestimmten Datensubjektanfrage beraten.

Es sind möglicherweise mehrere Prozesse involviert, um eine Datensubjektanfrage entsprechend der DSGVO-Complianceregeln Ihrer Organisation zu erfüllen.
  
- **Ermittlung**. Der Vorgang, mit dem ermittelt wird, welche Daten zum Erfüllen einer Datensubjektanfrage erforderlich sind.
- **Zugriff**. Abrufen der ermittelten Daten und deren potenzielle Übermittlung an das Datensubjekt.
- **Berichtigung**. Implementieren von Änderungen oder andere angeforderte Änderungen der personenbezogenen Daten.
- **Einschränkung**. Ändern des Zugriffs oder der Verarbeitung von personenbezogenen Daten durch Einschränken des Zugriffs oder Entfernen von Daten aus der Microsoft-Cloud.
- **Export**. Bereitstellen personenbezogener Daten in einem "strukturierten, häufig verwendeten, maschinell lesbaren Format" an die betroffene Person gemäß dem "Recht auf Datenübertragbarkeit" gemäß DSGVO.
- **Löschen**. Permanentes Entfernen personenbezogener Daten aus der Microsoft-Cloud.

## <a name="specific-dsr-considerations"></a>Spezifische Überlegungen zu Datensubjektanfragen

### <a name="insights-generated-by-microsoft-products-or-services"></a>Von Microsoft-Produkten oder -Diensten generierte Einblicke

[Einblicke](https://docs.microsoft.com/microsoft-365/compliance/gdpr-dsr-office365#part-2-responding-to-dsrs-with-respect-to-insights-generated-by-office-365) können durch Dienste (myAnalytics usw.) generiert werden. Office 365 umfasst Onlinedienste, die Benutzern und Organisationen, die diese Dienste nutzen, Einblicke gewähren. Die von diesen Diensten generierten Daten erzeugen möglicherweise personenbezogene Daten, die für eine Datensubjektanfrage relevant sind. Folgen Sie dem Link in der nachstehenden Liste, um Details zu dienstspezifischen Datensubjektanfrage-Prozessen anzuzeigen.  

### <a name="dsrs-for-system-generated-logs"></a>Datensubjektanfragen bezüglich vom System generierten Protokollen

Protokolle und verwandte Daten, die von Microsoft generiert werden, enthalten möglicherweise Daten, die gemäß der DSGVO-Definition "personenbezogene Daten" sind. Daten in vom System generierten Protokollen einzuschränken oder zu korrigieren, wird nicht unterstützt. Daten in vom System generierten Protokollen geben auf Fakten basierende Aktionen innerhalb der Microsoft-Cloud sowie Diagnosedaten wieder. Änderungen würden die historische Erfassung von Aktionen kompromittieren und das Betrugs- und Sicherheitsrisiko erhöhen. Microsoft bietet die Möglichkeit, auf vom System generierte Protokolle zuzugreifen, sie zu exportieren und zu löschen, wenn dies zur Erfüllung einer Datensubjektanfrage erforderlich ist. Beispiele für solche Daten sind unter anderem:  

- Daten zu Produkt- und Dienstnutzung, z. B. Aktivitätsprotokolle
- Suchanfragen und Abfragedaten von Benutzern
- Daten, die durch Produkte und Dienste infolge der Systemfunktionalität und Interaktion von Benutzern oder anderen Systemen erzeugt werden.  

### <a name="yammer-and-kaizala"></a>Yammer und Kaizala

Beim Löschen eines Benutzerkontos werden die vom System generierten Protokolle für Yammer und Kaizala nicht entfernt. Siehe die folgenden Links, um Daten aus diesen Anwendungen zu entfernen:

- [Verwalten von DSGVO-Datensubjektanfragen in Yammer Enterprise](https://docs.microsoft.com/yammer/manage-security-and-compliance/gdpr-requests-in-yammer-enterprise)
- [Exportieren oder Löschen von Organisationsdaten eines Benutzers in Kaizala](https://docs.microsoft.com/office365/kaizala/export-or-delete-a-user-s-data)

### <a name="national-clouds"></a>Nationale Clouds

In einigen nationalen Clouds muss ein globaler IT-Administrator vom System generierte Protokolle löschen.

### <a name="microsoft-services"></a>Microsoft Services

Wenn Ihre Organisation oder Ihre Benutzer sich mit Microsoft in Verbindung setzen, um Support für Microsoft-Produkte und -Dienste zu erhalten, können einige der übermittelten Daten personenbezogene Daten enthalten. Weitere Informationen finden Sie unter [Microsoft-Support und Professional Services für Anfragen von betroffenen Personen im Rahmen der DSGVO](gdpr-dsr-prof-services.md).

### <a name="microsoft-controller-products"></a>Produkte, deren Datenverantwortlicher Microsoft ist

Unter bestimmten Umständen greifen die Benutzer Ihrer Organisation auf Microsoft-Produkte oder -Dienste zu, für die Microsoft der Datenverantwortliche ist. In diesen Fällen müssen Ihre Benutzer die eigenen Datensubjektanfragen direkt an Microsoft stellen, und Microsoft erfüllt die Anforderungen direkt an den Benutzer.

### <a name="third-party-products"></a>Produkte von Drittanbietern

Datensubjektanfragen für Produkte und Dienste von Drittanbietern, auf die über die Microsoft-Kontoauthentifizierung zugegriffen wird, sollten direkt an den entsprechenden Drittanbieter gerichtet werden.

## <a name="learn-more"></a>Weitere Informationen

- [Microsoft Trust Center](https://www.microsoft.com/TrustCenter/Privacy/gdpr/default.aspx)
