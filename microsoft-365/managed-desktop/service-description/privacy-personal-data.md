---
title: Datenschutz und personenbezogene Daten
description: Details zu den vom Dienst gesammelten, gespeicherten und verwendeten Daten
keywords: DSGVO, Aufbewahrung, Löschung, Speicherung, Aufbewahrung, Verarbeitung, Sicherheit, Überwachung
ms.service: m365-md
ms.sitesec: library
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.topic: article
ms.localizationpriority: normal
ms.openlocfilehash: 7005e09d5a3df158569e132d2954f3b9a0ebf371
ms.sourcegitcommit: 83a40facd66e14343ad3ab72591cab9c41ce6ac0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/13/2021
ms.locfileid: "49840481"
---
# <a name="privacy-and-personal-data"></a>Datenschutz und personenbezogene Daten

Benutzer können Daten auf Geräten empfangen, übertragen und speichern, die von Microsoft Managed Desktop verwaltet werden. Sie vertrauen darauf, dass der Datenschutz der Daten geschützt und nur in einer Weise verwendet wird, die ihren Erwartungen entspricht. In diesem Artikel wird erläutert, wie Microsoft Managed Desktop personenbezogene Daten sammelt, speichert, speichert, verarbeitet, sichert, teilt, überwacht und exportiert. Außerdem erfahren Sie, wie ein Administrator personenbezogene Daten anzeigen, korrigieren und löschen kann.

Microsoft Managed Desktop verwendet keine personenbezogenen Daten, die im Rahmen der Bereitstellung des Diensts für Profilerstellung, Werbung oder Marketing gesammelt werden.

## <a name="data-collection-of-microsoft-managed-desktop"></a>Datensammlung von Microsoft Managed Desktop

Wenn Benutzer Unternehmensgeräte bei Microsoft Managed Desktop registrieren, erfolgt die Datensammlung – auf technischer Ebene – mithilfe von Windows und Microsoft Intune. Diese Quellen sammeln personenbezogene Daten über Benutzergeräte, z. B. Gerätenamen für Microsoft Managed Desktop, um das zu verwaltende Gerät zu identifizieren und mit den Microsoft Managed Desktop-Erfahrungen zu erhalten.

Microsoft Managed Desktop sammelt keine Daten allein, um seinen Dienst zur Verfügung zu stellen (mit Ausnahme der Kontaktinformationen des [IT-Admins).](#it-admin-contact-information) Stattdessen werden von Microsoft Managed Desktop Daten wiederverwendet, die bereits von anderen Quellen wie Windows und Microsoft Intune erfasst wurden. Microsoft Managed Desktop verwendet Daten, die diese Dienste von registrierten Geräten erfassen:

- Windows-Diagnosedaten von Geräten, die von Microsoft Managed Desktop verwaltet werden, werden an die Microsoft -Diagnosedatenspeicher gesendet.
- Microsoft Managed Desktop verwendet [moderne Verwaltung für](https://docs.microsoft.com/learn/modules/introduction-to-modern-management-in-microsoft-365/) die Verwaltung der registrierten Geräte. Im Rahmen der modernen Verwaltung müssen die Geräte im Azure Active Directory des Mandanten registriert werden.
- Für die Verteilung der hochgradig optimierten und sicheren Konfiguration an registrierte Geräte verwendet Microsoft Managed Desktop Microsoft Intune.
- Microsoft Managed Desktop verwendet Sicherheitsintelligenzdaten von Microsoft Defender Advanced Thread Protection für kunden, die diesen Dienst verwenden.

## <a name="data-storage-and-sources-in-microsoft-managed-desktop"></a>Datenspeicherung und Quellen in Microsoft Managed Desktop

Nachdem Microsoft Managed Desktop die Daten erhalten hat, muss es den Dienst, die Speicherung und die Verarbeitung dieser Daten wie folgt bereitstellen:

### <a name="storing-data-storage-location-and-data-retention"></a>Speichern von Daten, Speicherort und Datenaufbewahrung

Microsoft Managed Desktop speichert seine Daten in einem oder mehreren der folgenden Microsoft-Speicherdienste:

- Azure SQL
- Azure Storage

Microsoft Managed Desktop speichert seine Daten in den USA. Personenbezogene Daten werden von Microsoft Managed Desktop maximal 30 Tage lang aufbewahrt.

### <a name="staff-location"></a>Standort des Mitarbeiters

Die MmD Operations- und MMD Security Operations Teams befinden sich in den USA und Indien.

## <a name="data-usage-of-microsoft-managed-desktop"></a>Datennutzung von Microsoft Managed Desktop

Microsoft Managed Desktop verwendet diese Daten:


| Datenquellen |Verwenden mit Microsoft Managed Desktop  |
|---------|---------|
|Azure Active Directory-Daten     | Wird in Berichten verwendet, die für Mandantenadministratoren erstellt wurden und im Microsoft Managed Desktop Admin Portal verfügbar sind.        |
|Intune-Daten     | Wird in Berichten verwendet, die für Mandantenadministratoren erstellt wurden und im Microsoft Managed Desktop Admin Portal verfügbar sind.        |
|Microsoft Defender für Endpunkt     |  Wird für die Behandlung von Sicherheitsbedrohungen verwendet, die auf registrierten Geräten vom Microsoft Managed Desktop Security Operations Center (SOC) erkannt werden.  |
|Windows-Diagnosedaten     |Wird verwendet, um den Updatestatus verwalteter Geräte zu bestimmen und um das IT-as-a-Service (ITaaS)-Angebot von Microsoft Managed Desktop zur Verfügung zu stellen und zu verbessern.         |
|Administratorkontaktdaten     | Wird von Microsoft Managed Desktop für die Kommunikation mit Mandantenadministratoren verwendet.        |


### <a name="entities-processed-by-microsoft-managed-desktop"></a>Von Microsoft Managed Desktop verarbeitete Entitäten

Microsoft Managed Desktop verarbeitet diese Entitäten, um den Dienst zur Verfügung zu stellen:

- Gerätedaten
- Sicherheitseinstellungen für Geräte
- Betriebssystem und Hardware des Geräts
- Aggregierte Informationen zum Gerätezustand
- Gerätediagnoseinformationen
- Mandantendaten
- Azure Active Directory-Ressourcen
- Richtlinien- und Konfigurationsdaten
- Microsoft Defender für Endpunktmetadaten
- Windows-Diagnosedaten
- Produkt- und Dienstnutzungsdaten

### <a name="microsoft-azure-active-directory"></a>Microsoft Azure Active Directory

Von Microsoft Managed Desktop verwendete Identitätsdaten werden von Azure Active Directory an einem geografischen Standort basierend auf der Adresse gespeichert, die von der Organisation beim Abonnieren eines Microsoft-Onlinediensts wie Office 365 oder Azure bereitgestellt wird. Unter [Microsoft Azure – Wo befinden sich meine Kundendaten?](http://azuredatacentermap.azurewebsites.net/) finden Sie eine Karte mit den Rechenzentren für Azure Active Directory.

Weitere Informationen zu den Regionen, die Azure für die Datenspeicherung verwendet, finden Sie unter [Azure Active Directory:](https://msit.powerbi.com/view?r=eyJrIjoiODdjOWViZDctMWRhZS00ODUzLWI4MmQtNWM5NjBkZTBkNjFlIiwidCI6IjcyZjk4OGJmLTg2ZjEtNDFhZi05MWFiLTJkN2NkMDExZGI0NyIsImMiOjV9)Wo befinden sich Ihre Daten.

### <a name="microsoft-intune"></a>Microsoft Intune

Intune-Daten können in einigen verschiedenen Regionen gespeichert werden, z. B. Europa Nord (Irland) und Europa -West (Niederlande). Ihr IT-Administrator erstellt ein Mandantenkonto und wählt das Land aus, in dem Daten gespeichert werden, wenn er sich anfänglich bei den Intune-Diensten registriert. Eine Liste der von Intune verwendeten Rechenzentrumsstandorte finden Sie unter [Microsoft Intune : Wo befinden sich meine Kundendaten?](http://intunedatacentermap.azurewebsites.net/) Weitere Informationen zur Datenspeicherung und -verwendung durch Intune finden Sie unter ["Datensammlung in Intune".](https://docs.microsoft.com/intune/privacy-data-collect)

### <a name="microsoft-defender-for-endpoint"></a>Microsoft Defender für Endpunkt

Microsoft Defender für Endpunktdaten können in einigen verschiedenen Regionen gespeichert werden. Aus diesem Grund arbeitet Defender for Endpoint in den Microsoft Azure-Rechenzentren in der Europäischen Union, im Vereinigten Königreich und in den Vereinigten Staaten, wie unter [Microsoft Defender for Endpoint](http://intunedatacentermap.azurewebsites.net/)– Datenspeicherorte angegeben. Weitere Informationen zur Datenspeicherung und Verwendung durch Defender for Endpoint finden Sie unter Welche Daten [sammelt Microsoft Defender for Endpoint?](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy#what-data-does-microsoft-defender-atp-collect)

### <a name="windows-10"></a>Windows 10

Wie in den Datenschutzbestimmungen von [Microsoft](https://privacy.microsoft.com/privacystatement)angegeben, können von Microsoft erfasste personenbezogene Daten in Ihrer Region, in den USA und in jedem anderen Land gespeichert und verarbeitet werden, in dem Microsoft oder seine Partner, Niederlassungen oder Dienstanbieter Einrichtungen betreiben. [...] In der Regel befindet sich der primäre Speicherort in der Region des Kunden oder in den USA, häufig mit einer Sicherung in einem Datencenter in einer anderen Region. Die Speicherorte werden ausgewählt, um effizient zu arbeiten, die Leistung zu verbessern und Redundanzen zu erstellen, um die Daten bei einem Ausfall oder einem anderen Problem zu schützen. Wir ergreifen Maßnahmen, um sicherzustellen, dass die im Rahmen dieser Datenschutzbestimmungen gesammelten Daten gemäß den Bestimmungen dieser Erklärung und den Anforderungen anwendbarer Gesetze verarbeitet werden, unabhängig davon, wo sich die Daten befinden."

Weitere Informationen zur Diagnosedatensammlung von Windows 10 finden Sie im Abschnitt "Wo wir personenbezogene Daten speichern und [verarbeiten"](https://privacy.microsoft.com/privacystatement#mainwherewestoreandprocessdatamodule) der Microsoft-Datenschutzbestimmungen.

## <a name="data-access-protection"></a>Schutz des Datenzugriffs

Der direkte Zugriff auf die internen Datenspeicher von Microsoft Managed Desktop ist auf verschiedene Weise eingeschränkt:

- Sie erfordert eine Genehmigung auf technischer Leadebene.
- Sie ist sowohl überwacht als auch zeitlich begrenzt.
- Es erfordert die Verwendung einer hochgradig gesicherten und eingeschränkten Arbeitsstation.
- Alle Daten werden verschlüsselt, während sie gespeichert werden.
- Es gibt keinen ständigen Zugriff.
- Für den Zugriff auf das interne Verwaltungsportal von Microsoft Managed Desktop ist eine hochgradig gesicherte und eingeschränkte Arbeitsstation erforderlich.

## <a name="processing-personal-data-in-a-compliant-manner"></a>Konforme Verarbeitung personenbezogener Daten
Microsoft Managed Desktop verarbeitet personenbezogene Daten mit ISO-zertifizierten Systemen. Weitere Informationen finden Sie unter [Compliance](../intro/compliance.md).

## <a name="profiling-and-marketing"></a>Profilerstellung und Marketing

Microsoft Managed Desktop verwendet keine personenbezogenen Daten, die im Rahmen der Bereitstellung des Diensts für Profilerstellung, Werbung oder Marketing gesammelt werden.

## <a name="data-subject-requests-for-the-gdpr-and-ccpa"></a>Anträge betroffener Personen im Rahmen der DSGVO und des CCPA

Die Allgemeine Datenschutzverordnung [(DSGVO)](https://ec.europa.eu/justice/data-protection/reform/index_en.htm) der Europäischen Union gewährt Personen (in der Verordnung als betroffene Personen bekannt) das Recht, die personenbezogenen Daten zu verwalten, die von einem Arbeitgeber oder einer anderen Art von Agentur oder Organisation (als Datenverantwortlicher oder nur Verantwortlicher bekannt) erfasst wurden. Personenbezogene Daten sind in der DSGVO ganz allgemein als Daten definiert, die sich auf eine identifizierte oder identifizierbare natürliche Person beziehen. Die DSGVO gewährt betroffenen Personen bestimmte Rechte an ihren personenbezogenen Daten, z. B. das Recht auf Erhalt einer Kopie dieser personenbezogenen Daten, das Recht auf Korrektur der Daten, das Recht auf Einschränkung der Bearbeitung dieser Daten und das Recht auf Empfang dieser Daten in einem elektronischen Format, sodass sie an einen anderen Verantwortlichen übermittelt werden können. Ein von einer betroffenen Person formal gestellter Antrag an den Verantwortlichen, bestimmte Maßnahmen im Zusammenhang mit den personenbezogenen Daten der betroffenen Person zu ergreifen, wird als Antrag einer betroffenen Person bezeichnet.

Entsprechend bietet der California Consumer Privacy Act (CCPA) den kalifornischen Verbrauchern Datenschutzrechte und -pflichten, einschließlich der Rechte, die den Rechten der DSGVO ähneln, z. B. das Recht auf Löschung, Zugriff und Empfang (Portabilität) ihrer personenbezogenen Informationen. Das CCPA bietet auch bestimmte Offenlegungen, Schutz gegen Willen bei der Wahl von Ausübungsrechten und "Opt-out/Opt-In"-Anforderungen für bestimmte Datenübertragungen, die als "Verkäufe" klassifiziert sind. Die Definition von "Verkäufe" umfasst die Freigabe von Daten für eine angemessene Gegenleistung. Weitere Informationen zum CCPA finden Sie im ["California Consumer Privacy Act](https://docs.microsoft.com/microsoft-365/compliance/offering-ccpa?view=o365-worldwide) und in den [häufig gestellten Fragen zum California Consumer Privacy Act](https://docs.microsoft.com/microsoft-365/compliance/ccpa-faq?view=o365-worldwide).

Im folgenden Abschnitt wird erläutert, wie Microsoft Managed Desktop Controllern dabei hilft, personenbezogene Daten oder personenbezogene Informationen, die von Microsoft Managed Desktop verwendet werden, zu suchen, darauf zu zugreifen und darauf zu handeln.

> [!NOTE]
> Wenn Sie nach allgemeinen Informationen zur DSGVO suchen, lesen Sie den Abschnitt zur DSGVO [im](https://servicetrust.microsoft.com/ViewPage/GDPRGetStarted) Service Trust Portal.

### <a name="it-admin-contact-information"></a>Kontaktinformationen für DEN IT-Administrator

Ein Mandantenadministrator kann seine eigenen personenbezogenen Daten (z. B. eigene Kontaktinformationen) direkt im Abschnitt "Administratorkontakt" des Microsoft Managed Desktop Portals anzeigen, korrigieren und löschen.

### <a name="user-related-personal-data"></a>Benutzerbezogene personenbezogene Daten

Abgesehen davon sammelt Microsoft Managed Desktop keine personenbezogenen Daten allein. Stattdessen werden personenbezogene Daten verwendet und verwendet, die andere Microsoft Enterprise Online Services gesammelt haben. IT-Administratoren, die auf ihre Benutzeranforderungen zum Anzeigen, Korrigieren und Löschen ihrer personenbezogenen Daten reagieren möchten, können die entsprechende Funktionalität der zugrunde liegenden Dienste nutzen, von der Microsoft Managed Desktop abhängt. Wenn Sie an der Anzeige oder Löschung von personenbezogenen Daten interessiert sind, die von diesen Diensten verwendet werden, lesen Sie zuerst die Azure-Datensubjektanforderungen für den [DSGVO-Artikel.](https://docs.microsoft.com/microsoft-365/compliance/gdpr-dsr-azure)

Verwenden Sie außerdem die folgenden Anleitungen, um DSRs für die Dienste zu verwenden, von der microsoft Managed Desktop für die Sammlung von personenbezogenen Daten abhängt:

- [Azure Active Directory](https://docs.microsoft.com/microsoft-365/compliance/gdpr-dsr-azure?view=o365-worldwide)
- [Microsoft Intune](https://docs.microsoft.com/microsoft-365/compliance/gdpr-dsr-intune?view=o365-worldwide)
- [Microsoft Defender für Endpunkt](https:/docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)
- [Windows 10](https://docs.microsoft.com/windows/privacy/windows-10-and-privacy-compliance)
