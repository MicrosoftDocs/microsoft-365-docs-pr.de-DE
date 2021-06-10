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
ms.openlocfilehash: 3de39e8d10f949856862095ebd204fac1a4d694e
ms.sourcegitcommit: 3e971b31435d17ceeaa9871c01e88e25ead560fb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/09/2021
ms.locfileid: "52861683"
---
# <a name="privacy-and-personal-data"></a>Datenschutz und personenbezogene Daten

Benutzer können Daten auf Geräten empfangen, übertragen und speichern, die von Microsoft Managed Desktop verwaltet werden. Sie vertrauen darauf, dass die Privatsphäre der Daten geschützt und nur auf eine Weise verwendet wird, die ihren Erwartungen entspricht. In diesem Artikel wird erläutert, wie Microsoft Managed Desktop personenbezogene Daten sammelt, speichert, aufbewahrt, verarbeitet, sichert, teilt, überwacht und exportiert. Außerdem erfahren Sie, wie ein Administrator personenbezogene Daten anzeigen, korrigieren und löschen kann.

Microsoft Managed Desktop verwendet keine personenbezogenen Daten, die im Rahmen der Bereitstellung des Diensts für Profilerstellung, Werbung oder Marketingzwecke gesammelt werden.

## <a name="data-collection-of-microsoft-managed-desktop"></a>Datensammlung von Microsoft Managed Desktop

Wenn Benutzer Unternehmensgeräte bei Microsoft Managed Desktop registrieren, wird die Datenerfassung – auf der technischen Ebene – mithilfe von Windows und Microsoft Intune behandelt. Diese Quellen sammeln personenbezogene Daten über die Geräte von Benutzern, z. B. Gerätenamen für Microsoft Managed Desktop, um das zu verwaltende Gerät zu identifizieren und mit den Microsoft Managed Desktop-Oberflächen zu versehen.

Microsoft Managed Desktop erfasst keine Daten allein, um seinen Dienst bereitzustellen (mit Ausnahme der Kontaktinformationen des [IT-Administrators.](#it-admin-contact-information) Stattdessen verwendet Microsoft Managed Desktop Wiederverwenden von Daten, die bereits von anderen Quellen wie Windows und Microsoft Intune gesammelt wurden. Microsoft Managed Desktop verwendet Daten, die diese Dienste von registrierten Geräten sammeln:

- Windows Diagnosedaten von Geräten, die von Microsoft Managed Desktop verwaltet werden, werden an die Windows Diagnosedatenspeicher von Microsoft gesendet.
- Microsoft Managed Desktop verwendet [die moderne Verwaltung](/learn/modules/introduction-to-modern-management-in-microsoft-365/) für die Verwaltung der registrierten Geräte. Im Rahmen der "modernen Verwaltung" müssen die Geräte im Azure Active Directory des Mandanten registriert werden.
- Für die Verteilung der hochgradig optimierten und sicheren Konfiguration an registrierte Geräte verwendet Microsoft Managed Desktop Microsoft Intune.
- Microsoft Managed Desktop verwendet Security Intelligence-Daten von Microsoft Defender Advanced Thread Protection für Kunden, die diesen Dienst verwenden.

## <a name="data-storage-and-sources-in-microsoft-managed-desktop"></a>Datenspeicherung und Datenquellen in Microsoft Managed Desktop

Nachdem Microsoft Managed Desktop die Daten erhalten hat, muss sie den Dienst, die Speicherung und die Verarbeitung dieser Daten wie folgt bereitstellen:

### <a name="storing-data-storage-location-and-data-retention"></a>Speichern von Daten, Speicherort und Datenaufbewahrung

Microsoft Managed Desktop speichert seine Daten in einem oder mehreren der folgenden Microsoft-Speicherdienste:

- Azure SQL
- Azure-Speicher
- Dynamics 365

Microsoft Managed Desktop speichert seine Daten in den USA. Personenbezogene Daten werden von Microsoft Managed Desktop maximal 30 Tage aufbewahrt, mit Ausnahme von Warnungsdaten für Microsoft Managed Desktop Geräte, die von Microsoft Defender für Endpunkt erfasst werden. Die tatsächlichen Warnungsdaten (einschließlich personenbezogener Daten) werden 180 Tage lang gespeichert. Benachrichtigungsdaten mit entfernten personenbezogenen Daten werden bis zu zwei Jahre lang gespeichert. In Übereinstimmung mit der Datenschutz-Grundverordnung (DSGVO) und dem California Consumer Privacy Act (CCPA) berücksichtigt Microsoft Managed Desktop die Rechte der betroffenen Person für alle personenbezogenen Daten, die in Benachrichtigungsdaten gespeichert sind.

### <a name="staff-location"></a>Mitarbeiterstandort

Die Teams für Microsoft Managed Desktop Operations and Security Operations befinden sich in den USA und Indien.

## <a name="data-usage-of-microsoft-managed-desktop"></a>Datennutzung von Microsoft Managed Desktop

Microsoft Managed Desktop verwendet diese Daten:


| Datenquellen |Verwenden mit Microsoft Managed Desktop  |
|---------|---------|
|Azure Active Directory Daten     | Wird in Berichten verwendet, die für Mandantenadministratoren erstellt wurden, die im Microsoft Managed Desktop Verwaltungsportal verfügbar sind.        |
|Intune-Daten     | Wird in Berichten verwendet, die für Mandantenadministratoren erstellt wurden, die im Microsoft Managed Desktop Verwaltungsportal verfügbar sind.        |
|Microsoft Defender für Endpunkt     |  Wird für die Behandlung von Sicherheitsbedrohungen verwendet, die von Microsoft Managed Desktop Security Operations Center (SOC) auf registrierten Geräten erkannt werden.  |
|diagnosedaten Windows     |Wird verwendet, um den Updatestatus von verwalteten Geräten zu ermitteln und das IT-as-a-Service (ITaaS)-Angebot Microsoft Managed Desktop bereitzustellen und zu verbessern.         |
|Administratorkontaktdaten     | Wird von Microsoft Managed Desktop für die Kommunikation mit Mandantenadministratoren verwendet.        |


### <a name="entities-processed-by-microsoft-managed-desktop"></a>Von Microsoft Managed Desktop verarbeitete Entitäten

Microsoft Managed Desktop verarbeitet diese Entitäten, um den Dienst bereitzustellen:

- Gerätedaten
- Sicherheitseinstellungen für Geräte
- Betriebssystem und Hardware des Geräts
- Aggregierte Informationen zur Geräteintegrität
- Gerätediagnoseinformationen
- Mandantendaten
- ressourcen Azure Active Directory
- Richtlinien- und Konfigurationsdaten
- Microsoft Defender für Endpunkt-Metadaten und Warnungsdaten
- diagnosedaten Windows
- Produkt- und Dienstnutzungsdaten

### <a name="microsoft-azure-active-directory"></a>Microsoft Azure Active Directory

Identitätsdaten, die von Microsoft Managed Desktop verwendet werden, werden von Azure Active Directory an einem geografischen Standort basierend auf der Adresse gespeichert, die von der Organisation beim Abonnieren eines Microsoft-Onlinediensts wie Office 365 oder Azure angegeben wird. Siehe [Microsoft Azure – Wo befinden sich meine Kundendaten?](http://azuredatacentermap.azurewebsites.net/) Eine Karte mit den Rechenzentren für Azure Active Directory.

Weitere Informationen zu den Regionen, die Azure für die Datenspeicherung verwendet, finden Sie unter [Azure Active Directory– Wo befinden sich Ihre Daten.](https://msit.powerbi.com/view?r=eyJrIjoiODdjOWViZDctMWRhZS00ODUzLWI4MmQtNWM5NjBkZTBkNjFlIiwidCI6IjcyZjk4OGJmLTg2ZjEtNDFhZi05MWFiLTJkN2NkMDExZGI0NyIsImMiOjV9)

### <a name="microsoft-intune"></a>Microsoft Intune

Intune-Daten können in einigen verschiedenen Regionen gespeichert werden, z. B. Europa Nord (Irland) und Europa West (Niederlande). Ihr IT-Administrator erstellt ein Mandantenkonto und wählt das Land aus, in dem Daten gespeichert werden, wenn sie sich zunächst für Intune-Dienste registrieren. Eine Liste der von Intune verwendeten Rechenzentren finden Sie unter [Microsoft Intune : Wo befinden sich meine Kundendaten?](http://intunedatacentermap.azurewebsites.net/) Weitere Informationen zur Datenspeicherung und -verwendung durch Intune finden Sie unter ["Datensammlung in Intune".](/intune/privacy-data-collect)

### <a name="microsoft-defender-for-endpoint"></a>Microsoft Defender für Endpunkt

Microsoft Defender für Endpunkt-Daten können in einigen verschiedenen Regionen gespeichert werden. Aus diesem Grund arbeitet Defender für Endpunkt in den Microsoft Azure Rechenzentren in der Europäischen Union, im Vereinigten Königreich und in den Vereinigten Staaten, wie in Microsoft Defender für Endpunkt angegeben [– Datenspeicherorte.](http://intunedatacentermap.azurewebsites.net/) Weitere Informationen zur Datenspeicherung und -verwendung durch Defender für Endpunkt finden Sie unter [Welche Daten erfasst Microsoft Defender für Endpunkt?](/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy#what-data-does-microsoft-defender-atp-collect)

### <a name="windows-10"></a>Windows 10

Wie in den [Microsoft-Datenschutzbestimmungen](https://privacy.microsoft.com/privacystatement)angegeben, "können personenbezogene Daten, die von Microsoft gesammelt werden, in Ihrer Region, in den Vereinigten Staaten und in jedem anderen Land, in dem Microsoft oder seine verbundenen Unternehmen, Niederlassungen oder Dienstanbieter Einrichtungen betreiben, gespeichert und verarbeitet werden. [...] In der Regel befindet sich der primäre Speicherort in der Region des Kunden oder in den Vereinigten Staaten, häufig mit einer Sicherung in einem Rechenzentrum in einer anderen Region. Die Speicherorte werden ausgewählt, um effizient zu arbeiten, die Leistung zu verbessern und Redundanzen zu erstellen, um die Daten zu schützen, wenn ein Ausfall oder ein anderes Problem auftritt. Wir unternehmen Maßnahmen, um sicherzustellen, dass die daten, die wir gemäß dieser Datenschutzerklärung sammeln, gemäß den Bestimmungen dieser Erklärung und den Anforderungen des geltenden Rechts verarbeitet werden, unabhängig davon, wo sich die Daten befinden."

Weitere Informationen zur Erfassung von Diagnosedaten von Windows 10 finden Sie im Abschnitt ["Wo wir personenbezogene Daten speichern und verarbeiten"](https://privacy.microsoft.com/privacystatement#mainwherewestoreandprocessdatamodule) der Microsoft-Datenschutzbestimmungen.

## <a name="data-access-protection"></a>Datenschutz

Der direkte Zugriff auf die internen Datenspeicher Microsoft Managed Desktop wird auf verschiedene Arten eingeschränkt:

- Es ist eine Genehmigung auf Engineering-Leadebene erforderlich.
- Es ist zeitgebunden und überwacht.
- Alle Daten werden verschlüsselt, während sie gespeichert werden.
- Der Zugriff auf das interne Verwaltungsportal Microsoft Managed Desktop erfordert eine hochgradig gesicherte und eingeschränkte Arbeitsstation.

## <a name="processing-personal-data-in-a-compliant-manner"></a>Konforme Verarbeitung personenbezogener Daten
Microsoft Managed Desktop verarbeitet personenbezogene Daten mit ISO-zertifizierten Systemen. Weitere Informationen finden Sie unter [Compliance.](../intro/compliance.md)

## <a name="profiling-and-marketing"></a>Profilerstellung und Marketing

Microsoft Managed Desktop verwendet keine personenbezogenen Daten, die im Rahmen der Bereitstellung des Diensts für Profilerstellung, Werbung oder Marketingzwecke gesammelt werden.

## <a name="data-subject-requests-for-the-gdpr-and-ccpa"></a>Anträge betroffener Personen im Rahmen der DSGVO und des CCPA

Die [Datenschutz-Grundverordnung (DSGVO)](https://ec.europa.eu/justice/data-protection/reform/index_en.htm) der Europäischen Union gewährt Personen (in der Verordnung als betroffene Personen bezeichnet) das Recht, die personenbezogenen Daten zu verwalten, die von einem Arbeitgeber oder einer anderen Art von Einrichtung oder Organisation (auch als Datenverantwortlicher oder verantwortlicher Datenverantwortlicher bezeichnet) erfasst wurden. Personenbezogene Daten sind in der DSGVO ganz allgemein als Daten definiert, die sich auf eine identifizierte oder identifizierbare natürliche Person beziehen. Die DSGVO gewährt betroffenen Personen bestimmte Rechte an ihren personenbezogenen Daten, z. B. das Recht auf Erhalt einer Kopie dieser personenbezogenen Daten, das Recht auf Korrektur der Daten, das Recht auf Einschränkung der Bearbeitung dieser Daten und das Recht auf Empfang dieser Daten in einem elektronischen Format, sodass sie an einen anderen Verantwortlichen übermittelt werden können. Ein von einer betroffenen Person formal gestellter Antrag an den Verantwortlichen, bestimmte Maßnahmen im Zusammenhang mit den personenbezogenen Daten der betroffenen Person zu ergreifen, wird als Antrag einer betroffenen Person bezeichnet.

Auf ähnliche Weise bietet das CCPA Den kalifornischen Verbrauchern Datenschutzrechte und -pflichten, einschließlich Rechten, die den Rechten betroffener Personen der DSGVO ähneln, z. B. das Recht auf Löschung, Zugriff und Empfang (Portabilität) ihrer persönlichen Informationen. Das CCPA sieht auch bestimmte Offenlegungen, Schutz vor Belästigung bei der Wahl von Ausübungsrechten und "Opt-Out/Opt-In"-Anforderungen für bestimmte Datenübertragungen vor, die als "Verkäufe" klassifiziert werden. Die Definition von "Verkäufe" umfasst die Freigabe von Daten für eine angemessene Gegenleistung. Weitere Informationen zum CCPA finden Sie im ["California Consumer Privacy Act](/compliance/regulatory/offering-ccpa?view=o365-worldwide) und in den [häufig gestellten Fragen zum California Consumer Privacy Act](/compliance/regulatory/ccpa-faq?view=o365-worldwide).

Im folgenden Abschnitt wird erläutert, wie Microsoft Managed Desktop Verantwortlichen dabei hilft, von Microsoft Managed Desktop verwendete personenbezogene Daten oder persönliche Informationen zu finden, auf sie zuzugreifen und sie zu bearbeiten.

> [!NOTE]
> Wenn Sie nach allgemeinen Informationen zur DSGVO suchen, lesen Sie den [ABSCHNITT DSGVO](https://servicetrust.microsoft.com/ViewPage/GDPRGetStarted) des Service Trust Portal.

### <a name="it-admin-contact-information"></a>Kontaktinformationen für IT-Administratoren

Ein Mandantenadministrator kann seine eigenen personenbezogenen Daten (z. B. eigene Kontaktinformationen) direkt im Abschnitt "Administratorkontakt" des Microsoft Managed Desktop-Portals anzeigen, korrigieren und löschen.

## <a name="microsoft-defender-for-endpoint-alert-data"></a>Microsoft Defender für Endpunkt – Warnungsdaten

Sicherheitsadministratoren können eine Extraktion oder Löschung von personenbezogenen Daten im Zusammenhang mit Microsoft Defender für Endpunkt-Warnungen auf einem Microsoft Managed Desktop verwalteten Gerät in ihrer Umgebung anfordern. Der Sicherheitsadministrator sollte sich beim Microsoft Managed Desktop [Admin Portal](https://aka.ms/memadmin) anmelden und eine Supportanfrage senden. Wählen Sie den **Supportanforderungstyp** von **Änderungsanforderung,** **Kategorie** der **Sicherheit** und **Unterkategorie** **anderer** aus, und geben Sie dann die relevanten Gerätenamen in der Beschreibung zusammen mit Ihrer Anforderung zum Extrahieren oder Löschen von Daten ein.

### <a name="user-related-personal-data"></a>Benutzerbezogene personenbezogene Daten

Abgesehen davon erfasst Microsoft Managed Desktop keine persönlichen Daten. Stattdessen werden personenbezogene Daten, die von anderen Microsoft Enterprise Onlinediensten erfasst wurden, verwendet und verwendet. IT-Administratoren, die auf Benutzeranforderungen zum Anzeigen, Korrigieren und Löschen ihrer personenbezogenen Daten reagieren möchten, können die jeweilige Funktionalität der zugrunde liegenden Dienste nutzen, von denen Microsoft Managed Desktop abhängig ist. Wenn Sie daran interessiert sind, von diesen Diensten verwendete personenbezogene Daten anzuzeigen oder zu löschen, lesen Sie zuerst die [Azure-Datensubjektanforderungen für den DSGVO-Artikel.](/compliance/regulatory/gdpr-dsr-Azure)

Verwenden Sie darüber hinaus die folgenden Anleitungen, um Anträge betroffener Personen für die Dienste auszuführen, Microsoft Managed Desktop für die Sammlung personenbezogener Daten abhängt:

- [Azure Active Directory](/compliance/regulatory/gdpr-dsr-Azure?view=o365-worldwide)
- [Microsoft Intune](/compliance/regulatory/gdpr-dsr-Intune?view=o365-worldwide)
- [Microsoft Defender für Endpunkt](/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)
- [Windows 10](/windows/privacy/windows-10-and-privacy-compliance)
