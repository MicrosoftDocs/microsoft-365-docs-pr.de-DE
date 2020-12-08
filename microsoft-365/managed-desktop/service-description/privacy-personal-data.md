---
title: Datenschutz und personenbezogene Daten
description: Details der vom Dienst gesammelten, gespeicherten und verwendeten Daten
keywords: Dsgvo, Aufbewahrung, Löschung, Speicherung, Aufbewahrung, Verarbeitung, Sicherheit, Überwachung
ms.service: m365-md
ms.sitesec: library
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.topic: article
ms.localizationpriority: normal
ms.openlocfilehash: 8412c10416a4a131129eebd20d1b4f01228afaf3
ms.sourcegitcommit: 280200281aec862517876319a3fe4ce170674047
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/07/2020
ms.locfileid: "49586685"
---
# <a name="privacy-and-personal-data"></a>Datenschutz und personenbezogene Daten

Benutzer können Daten auf Geräten empfangen, übertragen und speichern, die von Microsoft Managed Desktop verwaltet werden. Sie vertrauen darauf, dass die Datenschutzbestimmungen geschützt und nur auf eine Weise verwendet werden, die Ihren Erwartungen entspricht. In diesem Artikel wird erläutert, wie personenbezogene Daten von Microsoft Managed Desktop erfasst, gespeichert, aufbewahrt, verarbeitet, gesichert, freigegebenen, überwacht und exportiert werden. Außerdem erfahren Sie, wie ein Administrator personenbezogene Daten anzeigen, korrigieren und löschen kann.

Microsoft Managed Desktop verwendet keine personenbezogenen Daten, die im Rahmen der Bereitstellung des Diensts für Profilerstellung, Werbung oder Marketingzwecke erfasst werden.

## <a name="data-collection-of-microsoft-managed-desktop"></a>Datensammlung von Microsoft Managed Desktop

Wenn Benutzer unternehmensgeräte in Microsoft Managed Desktop registrieren, wird die Datensammlung – auf technischer Ebene – mithilfe von Windows und Microsoft InTune verarbeitet. Diese Quellen sammeln personenbezogene Daten über Geräte der Benutzer, wie Gerätenamen für Microsoft Managed Desktop, um das zu verwaltende Gerät identifizieren und mit den Microsoft Managed Desktop-Funktionen bereitstellen zu können.

Microsoft Managed Desktop erfasst keine Daten selbst, um seinen Dienst bereitzustellen (mit Ausnahme der [Kontaktinformationen für IT-Administratoren](#it-admin-contact-information)). Stattdessen verwendet Microsoft Managed Desktop Daten, die andere Quellen wie Windows und Microsoft InTune bereits gesammelt haben. Microsoft Managed Desktop verwendet Daten, die diese Dienste von registrierten Geräten sammeln:

- Windows-Diagnosedaten von Geräten, die von Microsoft Managed Desktop verwaltet werden, werden an die Windows-Diagnosedaten Speicher von Microsoft gesendet.
- Microsoft Managed Desktop verwendet ein [modernes Management](https://docs.microsoft.com/learn/modules/introduction-to-modern-management-in-microsoft-365/) für die Verwaltung der registrierten Geräte. Im Rahmen dieser Vorgehensweise müssen die Geräte in der Azure-Active Directory des Mandanten registriert sein.
- Für die Verteilung der hoch optimierten und sicheren Konfiguration auf die registrierten Geräte verwendet Microsoft InTune Microsoft-Desktop.
- Microsoft Managed Desktop verwendet Security Intelligence-Daten aus dem erweiterten Thread Schutz von Microsoft Defender für Kunden, die diesen Dienst verwenden.

## <a name="data-storage-and-sources-in-microsoft-managed-desktop"></a>Datenspeicherung und Quellen in Microsoft Managed Desktop

Nachdem Microsoft Managed Desktop die Daten abgerufen hat, muss der Dienst, die Speicherung und die Verarbeitung dieser Daten wie folgt bereitgestellt werden:

### <a name="storing-data-storage-location-and-data-retention"></a>Speichern von Daten, Speicherort und Datenaufbewahrung

Microsoft Managed Desktop speichert die Daten in einem oder mehreren der folgenden Microsoft-Speicherdienste:

- Azure SQL
- Azure-Speicher

Microsoft Managed Desktop speichert die Daten in den Vereinigten Staaten. Personenbezogene Daten werden für maximal 30 Tage von Microsoft Managed Desktop aufbewahrt.

### <a name="staff-location"></a>Mitarbeiter Standort

Die Teams MMD Operations und MMD Security Operations befinden sich in den USA und in Indien.

## <a name="data-usage-of-microsoft-managed-desktop"></a>Datennutzung von Microsoft Managed Desktop

Microsoft Managed Desktop verwendet diese Daten:


| Datenquellen |Verwendung mit Microsoft Managed Desktop  |
|---------|---------|
|Azure-Active Directory Daten     | Wird in Berichten verwendet, die für mandantenadministratoren erstellt wurden, die im Verwaltungsportal von Microsoft Managed Desktop verfügbar sind.        |
|InTune-Daten     | Wird in Berichten verwendet, die für mandantenadministratoren erstellt wurden, die im Verwaltungsportal von Microsoft Managed Desktop verfügbar sind.        |
|Microsoft Defender für Endpoint     |  Dient zum Beheben von Sicherheitsbedrohungen, die auf registrierten Geräten vom Microsoft Managed Desktop Security Operations Center (SoC) erkannt wurden.  |
|Windows-Diagnosedaten     |Dient zum Ermitteln des Updatestatus verwalteter Geräte sowie zum Bereitstellen und verbessern des IT-as-a-Service-Angebots (ITaaS) von Microsoft Managed Desktop.         |
|Kontaktdaten des Administrators     | Wird von Microsoft Managed Desktop zur Kommunikation mit mandantenadministratoren verwendet.        |


### <a name="entities-processed-by-microsoft-managed-desktop"></a>Von Microsoft Managed Desktop verarbeitete Entitäten

Microsoft Managed Desktop verarbeitet diese Entitäten, um den Dienst bereitzustellen:

- Gerätedaten
- Sicherheitseinstellungen für Geräte
- Betriebssystem und Hardware des Geräts
- Aggregierte Informationen zur Geräte Integrität
- Gerätediagnose Informationen
- Mandantendaten
- Azure Active Directory-Ressourcen
- Richtlinien-und Konfigurationsdaten
- Microsoft Defender für Endpoint-Metadaten
- Windows-Diagnosedaten
- Produkt-und Dienst Nutzungsdaten

### <a name="microsoft-azure-active-directory"></a>Microsoft Azure Active Directory

Von Microsoft Managed Desktop verwendete Identitätsdaten werden von Azure Active Directory an einem geografischen Standort basierend auf der von der Organisation bereitgestellten Adresse gespeichert, wenn ein Microsoft Online-Dienst wie Office 365 oder Azure abonniert wird. Weitere Informationen finden Sie unter [Microsoft Azure – wo sind meine Kundendaten?](http://azuredatacentermap.azurewebsites.net/) für eine Karte mit den Rechenzentren für Azure Active Directory.

Weitere Informationen zu den Regionen, die Azure für die Datenspeicherung verwendet, finden Sie unter [Azure Active Directory – wo befinden sich Ihre Daten](https://msit.powerbi.com/view?r=eyJrIjoiODdjOWViZDctMWRhZS00ODUzLWI4MmQtNWM5NjBkZTBkNjFlIiwidCI6IjcyZjk4OGJmLTg2ZjEtNDFhZi05MWFiLTJkN2NkMDExZGI0NyIsImMiOjV9).

### <a name="microsoft-intune"></a>Microsoft Intune

InTune-Daten können in einigen verschiedenen Regionen gespeichert werden, beispielsweise in Europa Nord (Irland) und Europa West (Niederlande). Ihr IT-Administrator erstellt ein Mandantenkonto und wählt das Land aus, in dem Daten gespeichert werden, wenn Sie sich zunächst für InTune-Dienste registrieren. Eine Liste der von InTune verwendeten Rechenzentrums Standorte finden Sie unter [Microsoft InTune – wo sind meine Kundendaten?](http://intunedatacentermap.azurewebsites.net/). Weitere Informationen zur Datenspeicherung und-Verwendung durch InTune finden Sie unter [Datensammlung in InTune](https://docs.microsoft.com/intune/privacy-data-collect).

### <a name="microsoft-defender-for-endpoint"></a>Microsoft Defender für Endpoint

Microsoft Defender für Endpoint-Daten kann in einigen verschiedenen Regionen gespeichert werden. Aus diesem Grund arbeitet Defender for Endpoint in den Microsoft Azure-Rechenzentren in der Europäischen Union, im Vereinigten Königreich und in den USA, wie unter [Microsoft Defender for Endpoint – Datenspeicherorte](http://intunedatacentermap.azurewebsites.net/)angegeben. Weitere Informationen zur Datenspeicherung und zur Verwendung durch Defender für Endpoint finden Sie unter [welche Daten werden von Microsoft Defender für Endpoint erfasst?](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy#what-data-does-microsoft-defender-atp-collect)

### <a name="windows-10"></a>Windows 10

Wie in der [Microsoft-Datenschutzerklärung](https://privacy.microsoft.com/privacystatement)beschrieben, können von Microsoft gesammelte personenbezogene Daten in Ihrer Region, in den USA und in einem anderen Land, in dem Microsoft oder seine verbundenen Unternehmen, Niederlassungen oder Dienstanbieter Einrichtungen betreiben, gespeichert und verarbeitet werden. [...] Normalerweise befindet sich der primäre Speicherort in der Region des Kunden oder in den Vereinigten Staaten, häufig mit einer Sicherung in einem Rechenzentrum in einer anderen Region. Die Speicherorte werden ausgewählt, um effizient zu arbeiten, die Leistung zu verbessern und Redundanzen zu schaffen, um die Daten zu schützen, wenn ein Ausfall oder ein anderes Problem vorliegt. Wir Unternehmen Schritte, um sicherzustellen, dass die Daten, die wir im Rahmen dieser Datenschutzerklärung erfassen, gemäß den Bestimmungendieser Erklärung und den Anforderungen des anwendbaren Rechts verarbeitet werden, wenn sich die Daten befinden. "

Weitere Informationen zur Diagnose Datenerfassung von Windows 10 finden Sie im Abschnitt ["wo wir Daten speichern und verarbeiten"](https://privacy.microsoft.com/privacystatement#mainwherewestoreandprocessdatamodule) der Microsoft-Datenschutzerklärung.

## <a name="data-access-protection"></a>Datenzugriffsschutz

Der direkte Zugriff auf interne Datenspeicher von Microsoft Managed Desktop wird auf verschiedene Weise eingeschränkt:

- Sie erfordert eine Genehmigung des technischen Lead-Levels.
- Es wird sowohl überwacht als auch zeitlich limitiert.
- Sie erfordert die Verwendung einer streng gesicherten und eingeschränkten Arbeitsstation.
- Alle Daten werden während der Speicherung verschlüsselt.
- Es gibt keinen ständigen Zugriff.
- Der Zugriff auf das interne Verwaltungsportal von Microsoft Managed Desktop erfordert eine stark gesicherte und eingeschränkte Arbeitsstation.

## <a name="processing-personal-data-in-a-compliant-manner"></a>Verarbeiten von personenbezogenen Daten in einer konformen Weise
Microsoft Managed Desktop verarbeitet personenbezogene Daten mit ISO-zertifizierten Systemen. Weitere Informationen finden Sie unter [Compliance](../intro/compliance.md).

## <a name="profiling-and-marketing"></a>Profilerstellung und Marketing

Microsoft Managed Desktop verwendet keine personenbezogenen Daten, die im Rahmen der Bereitstellung des Diensts für Profilerstellung, Werbung oder Marketingzwecke erfasst werden.

## <a name="data-subject-requests-for-the-gdpr-and-ccpa"></a>Anträge betroffener Personen im Rahmen der DSGVO und des CCPA

Die [Allgemeine Datenschutzverordnung (dsgvo)](https://ec.europa.eu/justice/data-protection/reform/index_en.htm) der Europäischen Union erteilt Personen Rechte (die in der Verordnung als Datensubjekte bekannt sind) zur Verwaltung der personenbezogenen Daten, die von einem Arbeitgeber oder einer anderen Art von Agentur oder Organisation (als Daten Verantwortlicher oder nur Controller bezeichnet) erfasst wurden. Personenbezogene Daten sind in der DSGVO ganz allgemein als Daten definiert, die sich auf eine identifizierte oder identifizierbare natürliche Person beziehen. Die DSGVO gewährt betroffenen Personen bestimmte Rechte an ihren personenbezogenen Daten, z. B. das Recht auf Erhalt einer Kopie dieser personenbezogenen Daten, das Recht auf Korrektur der Daten, das Recht auf Einschränkung der Bearbeitung dieser Daten und das Recht auf Empfang dieser Daten in einem elektronischen Format, sodass sie an einen anderen Verantwortlichen übermittelt werden können. Ein von einer betroffenen Person formal gestellter Antrag an den Verantwortlichen, bestimmte Maßnahmen im Zusammenhang mit den personenbezogenen Daten der betroffenen Person zu ergreifen, wird als Antrag einer betroffenen Person bezeichnet.

Ebenso bietet das California Consumer Privacy Act (CCPA) Datenschutz Rechte und-Pflichten für kalifornische Verbraucher, einschließlich der Rechte, die den Datensubjekt rechten von dsgvo ähneln, wie das Recht zum Löschen, Zugriff und empfangen (Portabilität) Ihrer persönlichen Informationen. Das CCPA bietet auch bestimmte Angaben, Schutz vor Diskriminierung bei der Wahl von Übungs rechten und "Opt-out/Opt-in"-Anforderungen für bestimmte Datentransfers, die als "Vertrieb" klassifiziert werden. Die Definition von "Verkäufe" umfasst die Freigabe von Daten für eine angemessene Gegenleistung. Weitere Informationen zum CCPA finden Sie im ["California Consumer Privacy Act](https://docs.microsoft.com/microsoft-365/compliance/offering-ccpa?view=o365-worldwide) und in den [häufig gestellten Fragen zum California Consumer Privacy Act](https://docs.microsoft.com/microsoft-365/compliance/ccpa-faq?view=o365-worldwide).

Im folgenden Abschnitt wird erläutert, wie Controller bei der Suche, dem Zugriff und dem Handeln von personenbezogenen Daten oder persönlichen Informationen, die von Microsoft Managed Desktop verwendet werden, von Microsoft Managed Desktop unterstützt werden.

> [!NOTE]
> Wenn Sie allgemeine Informationen zum dsgvo suchen, lesen Sie den [Abschnitt dsgvo](https://servicetrust.microsoft.com/ViewPage/GDPRGetStarted) des Dienst Vertrauensstellungs Portals.

### <a name="it-admin-contact-information"></a>Kontaktinformationen für IT-Administratoren

Ein mandantenadministrator kann seine persönlichen Daten (beispielsweise eigene Kontaktinformationen) direkt im Abschnitt "admin Contact" des Microsoft Managed Desktop-Portals anzeigen, korrigieren und löschen.

### <a name="user-related-personal-data"></a>Benutzerbezogene personenbezogene Daten

Abgesehen davon erfasst Microsoft Managed Desktop keine eigenen persönlichen Daten. Stattdessen stützt Sie sich auf personenbezogene Daten, die andere Microsoft Enterprise Online-Dienste gesammelt haben, und verwendet diese. IT-Administratoren, die auf Ihre Benutzeranforderungen reagieren möchten, um Ihre personenbezogenen Daten anzuzeigen, zu korrigieren und zu löschen, können die jeweilige Funktionalität der zugrunde liegenden Dienste verwenden, von denen Microsoft Managed Desktop abhängt. Wenn Sie personenbezogene Daten, die von diesen Diensten verwendet werden, anzeigen oder löschen möchten, lesen Sie zuerst die [Azure-Datensubjekt Anforderungen für den dsgvo](https://docs.microsoft.com/microsoft-365/compliance/gdpr-dsr-azure) -Artikel.

Verwenden Sie außerdem die folgenden Anleitungen zur Ausübung von DSRs für die Dienste, auf denen Microsoft Managed Desktop für die Erfassung personenbezogener Daten verwendet wird:

- [Azure Active Directory](https://docs.microsoft.com/microsoft-365/compliance/gdpr-dsr-azure?view=o365-worldwide)
- [Microsoft Intune](https://docs.microsoft.com/microsoft-365/compliance/gdpr-dsr-intune?view=o365-worldwide)
- [Microsoft Defender für Endpoint](https:/docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)
- [Windows 10](https://docs.microsoft.com/windows/privacy/windows-10-and-privacy-compliance)
