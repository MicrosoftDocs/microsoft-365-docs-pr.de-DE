---
title: Datenschutz und personenbezogene Daten
description: Details zu den vom Dienst gesammelten, gespeicherten und verwendeten Daten
keywords: DSGVO, Aufbewahrung, Löschung, Speicherung, Aufbewahrung, Verarbeitung, Sicherheit, Überwachung
ms.service: m365-md
ms.sitesec: library
author: jaimeo
manager: laurawi
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.topic: article
audience: Admin, ITPro
ms.localizationpriority: normal
ms.openlocfilehash: 3f1a251d98be5b3a9fefa5c1f6d5d5562516d5d5
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50908174"
---
# <a name="privacy-and-personal-data"></a>Datenschutz und personenbezogene Daten

Benutzer können Daten auf Geräten empfangen, übertragen und speichern, die von benutzern Microsoft Managed Desktop. Sie vertrauen darauf, dass der Datenschutz der Daten geschützt und nur auf eine Weise verwendet wird, die ihren Erwartungen entspricht. In diesem Artikel wird Microsoft Managed Desktop personenbezogene Daten gesammelt, gespeichert, gespeichert, verarbeitet, gesichert, freigaben, überwacht und exportiert. Außerdem erfahren Sie, wie ein Administrator personenbezogene Daten anzeigen, korrigieren und löschen kann.

Microsoft Managed Desktop verwendet keine personenbezogenen Daten, die im Rahmen der Bereitstellung des Diensts zu Profilerstellungs-, Werbe- oder Marketingzwecken erfasst werden.

## <a name="data-collection-of-microsoft-managed-desktop"></a>Datensammlung von Microsoft Managed Desktop

Wenn Benutzer Unternehmensgeräte für Microsoft Managed Desktop registrieren, wird die Datensammlung auf technischer Ebene mithilfe von Windows und Microsoft Intune. Diese Quellen sammeln personenbezogene Daten über Geräte von Benutzern, z. B. Gerätenamen für Microsoft Managed Desktop, um das zu verwaltende Gerät zu identifizieren und mit den Microsoft Managed Desktop zur Verfügung zu stellen.

Microsoft Managed Desktop sammelt keine Daten allein, um seinen Dienst zur Verfügung zu stellen (mit Ausnahme von Kontaktinformationen des [IT-Admins](#it-admin-contact-information). Stattdessen werden Microsoft Managed Desktop wiederverwendet, die andere Quellen, z. B. Windows und Microsoft Intune, bereits gesammelt haben. Microsoft Managed Desktop verwendet Daten, die diese Dienste von registrierten Geräten sammeln:

- Windows Diagnosedaten von Geräten, die von Microsoft Managed Desktop verwaltet werden, werden an die Windows Von Microsoft gesendet.
- Microsoft Managed Desktop verwendet [moderne Verwaltung für](/learn/modules/introduction-to-modern-management-in-microsoft-365/) die Verwaltung der registrierten Geräte. Im Rahmen der modernen Verwaltung müssen die Geräte in der Mandantenverwaltung Azure Active Directory.
- Für die Verteilung der hochoptimierten und sicheren Konfiguration auf registrierte Geräte verwendet Microsoft Managed Desktop Microsoft Intune.
- Microsoft Managed Desktop verwendet Sicherheitsintelligenzdaten aus Microsoft Defender Advanced Thread Protection für kunden, die diesen Dienst verwenden.

## <a name="data-storage-and-sources-in-microsoft-managed-desktop"></a>Datenspeicherung und Quellen in Microsoft Managed Desktop

Nachdem Microsoft Managed Desktop die Daten erhält, muss sie den Dienst, die Speicherung und Verarbeitung dieser Daten wie folgt bereitstellen:

### <a name="storing-data-storage-location-and-data-retention"></a>Speichern von Daten, Speicherort und Datenaufbewahrung

Microsoft Managed Desktop speichert seine Daten in einem oder mehreren der folgenden Microsoft-Speicherdienste:

- Azure SQL
- Azure-Speicher
- Dynamics 365

Microsoft Managed Desktop speichert seine Daten in den USA. Personenbezogene Daten werden von Microsoft Managed Desktop maximal 30 Tage aufbewahrt, mit Ausnahme von Benachrichtigungsdaten für Microsoft Managed Desktop von Microsoft Defender for Endpoint erfassten Geräten. Die tatsächlichen Benachrichtigungsdaten (die personenbezogene Daten enthalten können) werden 180 Tage lang gespeichert. Benachrichtigungsdaten mit entfernten personenbezogenen Daten werden bis zu zwei Jahre lang gespeichert. In Übereinstimmung mit der Datenschutz-Grundverordnung (DSGVO) und dem California Consumer Privacy Act (CCPA) berücksichtigt Microsoft Managed Desktop die Rechte der datensubjektierten Person für alle personenbezogenen Daten, die in Benachrichtigungsdaten gespeichert sind.

### <a name="staff-location"></a>Standort des Personals

Die Microsoft Managed Desktop Operations and Security Operations Teams befinden sich in den USA und Indien.

## <a name="data-usage-of-microsoft-managed-desktop"></a>Datenverwendung von Microsoft Managed Desktop

Microsoft Managed Desktop verwendet diese Daten:


| Datenquellen |Verwenden mit Microsoft Managed Desktop  |
|---------|---------|
|Azure Active Directory Daten     | Wird in Berichten verwendet, die für Mandantenadministratoren erstellt wurden und im Microsoft Managed Desktop verfügbar sind.        |
|Intune-Daten     | Wird in Berichten verwendet, die für Mandantenadministratoren erstellt wurden und im Microsoft Managed Desktop verfügbar sind.        |
|Microsoft Defender für Endpunkt     |  Wird für die Behandlung von Sicherheitsbedrohungen verwendet, die auf registrierten Geräten von Microsoft Managed Desktop Security Operations Center (SOC) erkannt wurden.  |
|Windows Diagnosedaten     |Wird verwendet, um den Updatestatus verwalteter Geräte zu ermitteln und um das IT-as-a-Service(ITaaS)-Angebot von Microsoft Managed Desktop zur Verfügung zu stellen und zu verbessern.         |
|Administratorkontaktdaten     | Wird von Microsoft Managed Desktop verwendet, um mit Mandantenadministratoren zu kommunizieren.        |


### <a name="entities-processed-by-microsoft-managed-desktop"></a>Entitäten, die von Microsoft Managed Desktop

Microsoft Managed Desktop verarbeitet diese Entitäten, um den Dienst zur Verfügung zu stellen:

- Gerätedaten
- Sicherheitseinstellungen für Geräte
- Gerätebetriebssystem und Hardware
- Aggregierte Informationen zum Gerätezustand
- Gerätediagnoseinformationen
- Mandantendaten
- Azure Active Directory Ressourcen
- Richtlinien- und Konfigurationsdaten
- Metadaten und Benachrichtigungsdaten von Microsoft Defender for Endpoint
- Windows Diagnosedaten
- Produkt- und Dienstnutzungsdaten

### <a name="microsoft-azure-active-directory"></a>Microsoft Azure Active Directory

Von Microsoft Managed Desktop verwendete Identitätsdaten werden von Azure Active Directory basierend auf der von der Organisation angegebenen Adresse beim Abonnieren eines Microsoft Onlinediensts wie Office 365 oder Azure an einem geografischen Ort gespeichert. Unter [Microsoft Azure – Wo sind meine Kundendaten?](http://azuredatacentermap.azurewebsites.net/) finden Sie eine Karte mit den Rechenzentren für Azure Active Directory.

Weitere Informationen zu den Regionen, die Azure für die Datenspeicherung verwendet, finden Sie [unter Azure Active Directory-Where is your data located](https://msit.powerbi.com/view?r=eyJrIjoiODdjOWViZDctMWRhZS00ODUzLWI4MmQtNWM5NjBkZTBkNjFlIiwidCI6IjcyZjk4OGJmLTg2ZjEtNDFhZi05MWFiLTJkN2NkMDExZGI0NyIsImMiOjV9).

### <a name="microsoft-intune"></a>Microsoft Intune

Intune-Daten können in einigen verschiedenen Regionen gespeichert werden, z. B. Europa Nord (Irland) und Europe West (Niederlande). Ihr IT-Administrator erstellt ein Mandantenkonto und wählt das Land aus, in dem Daten gespeichert werden, wenn er sich anfänglich bei Intune-Diensten registriert. Eine Liste der von Intune verwendeten Rechenzentren finden Sie [unter Microsoft Intune– Wo sind meine Kundendaten?](http://intunedatacentermap.azurewebsites.net/). Weitere Informationen zur Datenspeicherung und -verwendung durch Intune finden Sie unter [Datensammlung in Intune](/intune/privacy-data-collect).

### <a name="microsoft-defender-for-endpoint"></a>Microsoft Defender für Endpunkt

Microsoft Defender for Endpoint-Daten können in einigen verschiedenen Regionen gespeichert werden. Aus diesem Grund arbeitet Defender for Endpoint in den Microsoft Azure-Rechenzentren in der Europäischen Union, im Vereinigten Königreich und in den Vereinigten Staaten, wie unter [Microsoft Defender for Endpoint – Data storage locations angegeben.](http://intunedatacentermap.azurewebsites.net/) Weitere Informationen zur Datenspeicherung und Verwendung durch Defender for Endpoint finden Sie unter Welche Daten [sammelt Microsoft Defender for Endpoint?](/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy#what-data-does-microsoft-defender-atp-collect)

### <a name="windows-10"></a>Windows 10

Wie in der [Microsoft-Datenschutzbestimmungen](https://privacy.microsoft.com/privacystatement)angegeben, können "von Microsoft erfasste personenbezogene Daten in Ihrer Region, in den USA und in jedem anderen Land gespeichert und verarbeitet werden, in dem Microsoft oder seine Verbundenen, Tochtergesellschaften oder Dienstanbieter Einrichtungen betreiben. [...] In der Regel befindet sich der primäre Speicherort in der Region des Kunden oder in den Vereinigten Staaten, häufig mit einer Sicherung zu einem Rechenzentrum in einer anderen Region. Die Speicherorte werden ausgewählt, um effizient zu arbeiten, die Leistung zu verbessern und Redundanzen zu erstellen, um die Daten bei einem Ausfall oder einem anderen Problem zu schützen. Wir ergreifen Maßnahmen, um sicherzustellen, dass die im Rahmen dieser Datenschutzerklärung gesammelten Daten gemäß den Bestimmungen dieser Erklärung und den Anforderungen des anwendbaren Rechts verarbeitet werden, unabhängig davon, wo sich die Daten befinden."

Weitere Informationen zur Diagnosedatensammlung von Windows 10 finden Sie im Abschnitt "Wo wir personenbezogene Daten speichern und [verarbeiten"](https://privacy.microsoft.com/privacystatement#mainwherewestoreandprocessdatamodule) der Microsoft-Datenschutzbestimmungen.

## <a name="data-access-protection"></a>Datenschutz

Der direkte Zugriff Microsoft Managed Desktop internen Datenspeichern ist auf verschiedene Weise eingeschränkt:

- Es ist eine technische Genehmigung auf Leadebene erforderlich.
- Es ist sowohl überwacht als auch zeitlich begrenzt.
- Es erfordert die Verwendung einer hoch gesicherten und eingeschränkten Arbeitsstation.
- Alle Daten werden verschlüsselt, während sie gespeichert werden.
- Es gibt keinen ständigen Zugriff.
- Der Zugriff Microsoft Managed Desktop internen Verwaltungsportals erfordert eine hochgradig gesicherte und eingeschränkte Arbeitsstation.

## <a name="processing-personal-data-in-a-compliant-manner"></a>Konforme Verarbeitung personenbezogener Daten
Microsoft Managed Desktop verarbeitet personenbezogene Daten mit ISO-zertifizierten Systemen. Weitere Informationen finden Sie unter [Compliance](../intro/compliance.md).

## <a name="profiling-and-marketing"></a>Profilerstellung und Marketing

Microsoft Managed Desktop verwendet keine personenbezogenen Daten, die im Rahmen der Bereitstellung des Diensts zu Profilerstellungs-, Werbe- oder Marketingzwecken erfasst werden.

## <a name="data-subject-requests-for-the-gdpr-and-ccpa"></a>Anträge betroffener Personen im Rahmen der DSGVO und des CCPA

Die Allgemeine Datenschutz-Verordnung [(DSGVO)](https://ec.europa.eu/justice/data-protection/reform/index_en.htm) der Europäischen Union gewährt Personen (in der Verordnung als betroffene Personen bekannt) das Recht, die personenbezogenen Daten zu verwalten, die von einem Arbeitgeber oder einer anderen Art von Agentur oder Organisation (als Datenverantwortlicher oder verantwortlicher Verantwortlicher bekannt) erfasst wurden. Personenbezogene Daten sind in der DSGVO ganz allgemein als Daten definiert, die sich auf eine identifizierte oder identifizierbare natürliche Person beziehen. Die DSGVO gewährt betroffenen Personen bestimmte Rechte an ihren personenbezogenen Daten, z. B. das Recht auf Erhalt einer Kopie dieser personenbezogenen Daten, das Recht auf Korrektur der Daten, das Recht auf Einschränkung der Bearbeitung dieser Daten und das Recht auf Empfang dieser Daten in einem elektronischen Format, sodass sie an einen anderen Verantwortlichen übermittelt werden können. Ein von einer betroffenen Person formal gestellter Antrag an den Verantwortlichen, bestimmte Maßnahmen im Zusammenhang mit den personenbezogenen Daten der betroffenen Person zu ergreifen, wird als Antrag einer betroffenen Person bezeichnet.

Auf ähnliche Weise bietet das CCPA Datenschutzrechte und -verpflichtungen für verbraucher in Kalifornien, einschließlich Rechte, die den Datenschutzrechten der DSGVO ähneln, z. B. das Recht auf Löschung, Zugriff und Empfang (Portabilität) ihrer personenbezogenen Informationen. Das CCPA sieht außerdem bestimmte Offenlegungen, Schutz vor Diskriminierung bei der Wahl von Ausübungsrechten und "Opt-out/Opt-In"-Anforderungen für bestimmte Datenübertragungen vor, die als "Verkäufe" klassifiziert sind. Die Definition von "Verkäufe" umfasst die Freigabe von Daten für eine angemessene Gegenleistung. Weitere Informationen zum CCPA finden Sie im ["California Consumer Privacy Act](/compliance/regulatory/offering-ccpa?view=o365-worldwide) und in den [häufig gestellten Fragen zum California Consumer Privacy Act](/compliance/regulatory/ccpa-faq?view=o365-worldwide).

Im folgenden Abschnitt wird erläutert, Microsoft Managed Desktop verantwortlichen Personen dabei hilft, personenbezogene Daten oder personenbezogene Informationen zu finden, auf diese zu zugreifen und darauf zu Microsoft Managed Desktop.

> [!NOTE]
> Wenn Sie nach allgemeinen Informationen zur DSGVO suchen, lesen Sie den Abschnitt [DSGVO](https://servicetrust.microsoft.com/ViewPage/GDPRGetStarted) im Service Trust Portal.

### <a name="it-admin-contact-information"></a>Kontaktinformationen für IT-Administratoren

Ein Mandantenadministrator kann seine eigenen personenbezogenen Daten (z. B. eigene Kontaktinformationen) direkt im Abschnitt Administratorkontakt des Microsoft Managed Desktop löschen.

## <a name="microsoft-defender-for-endpoint-alert-data"></a>Microsoft Defender for Endpoint-Warnungsdaten

Sicherheitsadministratoren können eine Extraktion oder Löschung von personenbezogenen Daten im Zusammenhang mit Microsoft Defender for Endpoint-Warnungen auf einem Microsoft Managed Desktop verwalteten Gerät in ihrer Umgebung anfordern. Der Sicherheitsadministrator sollte sich beim Administratorportal Microsoft Managed Desktop [anmelden](https://aka.ms/memadmin) und eine Supportanfrage senden. Wählen **Sie support request type** of Change **request**, **Category** of **Security** und **Subcategory** of **Other** aus, und geben Sie dann die entsprechenden Gerätenamen in der Beschreibung zusammen mit Ihrer Anforderung zum Extrahieren oder Löschen von Daten an.

### <a name="user-related-personal-data"></a>Benutzerbezogene personenbezogene Daten

Abgesehen davon sammelt Microsoft Managed Desktop personenbezogene Daten nicht allein. Stattdessen werden personenbezogene Daten verwendet, die von anderen Microsoft Enterprise online Services gesammelt wurden. IT-Administratoren, die auf ihre Benutzeranforderungen zum Anzeigen, Korrigieren und Löschen ihrer personenbezogenen Daten reagieren möchten, können die entsprechenden Funktionen der zugrunde liegenden Dienste nutzen, von Microsoft Managed Desktop abhängig sind. Wenn Sie an der Anzeige oder Löschung von personenbezogenen Daten interessiert sind, die von diesen Diensten verwendet werden, lesen Sie zunächst den Artikel Azure-Anfragen für betroffene Personen für den Artikel [DSGVO.](/compliance/regulatory/gdpr-dsr-Azure)

Verwenden Sie außerdem die folgenden Anleitungen, um DSRs für die Dienste zu Microsoft Managed Desktop, die von der Sammlung personenbezogener Daten abhängig sind:

- [Azure Active Directory](/compliance/regulatory/gdpr-dsr-Azure?view=o365-worldwide)
- [Microsoft Intune](/compliance/regulatory/gdpr-dsr-Intune?view=o365-worldwide)
- [Microsoft Defender for Endpoint](/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)
- [Windows 10](/windows/privacy/windows-10-and-privacy-compliance)