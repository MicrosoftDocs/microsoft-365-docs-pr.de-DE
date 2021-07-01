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
ms.openlocfilehash: 0ee214cf7ff5d5998a7fa35688574a23f8b082f0
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/30/2021
ms.locfileid: "53229599"
---
# <a name="overview"></a>Übersicht

Microsoft Managed Desktop ist ein IT-as-a-Service (ITaaS)-Dienst für Unternehmenscloudkunden, mit dem die Windows Geräte der Mitarbeiter bereitgestellt und aktualisiert werden. Es bietet auch IT-Dienstverwaltung und -vorgänge, überwacht die Sicherheits- und Vorfallreaktion sowie den Benutzersupport. Diese Dokumentation enthält zusätzliche Details zur Datenplattform und zur Datenschutzcompliance für Microsoft Managed Desktop.

## <a name="microsoft-managed-desktop-data-sources-and-purpose"></a>Microsoft Managed Desktop Datenquellen und Zweck

Microsoft Managed Desktop stellt seinen Dienst für Unternehmenskunden bereit und verwaltet die registrierten Geräte von Kunden ordnungsgemäß mithilfe von Daten aus verschiedenen Quellen. Diese Quellen, einschließlich Azure Active Directory, Microsoft Intune, Microsoft Windows 10 und Microsoft Defender für Endpunkt, bieten eine umfassende Übersicht über die Geräte, die von Microsoft Managed Desktop verwaltet werden. Der Dienst verwendet auch diese Microsoft-Dienste, um Microsoft Managed Desktop die Bereitstellung von ITaaS-Funktionen zu ermöglichen:

- [Microsoft Windows 10 Enterprise](/windows/windows-10/) – für die Verwaltung der Geräteeinrichtung, die Verwaltung von Verbindungen mit anderen Diensten und die betriebliche Unterstützung für IT-Spezialisten.
- [Windows Update for Business](/windows/deployment/update/waas-manage-updates-wufb) : verwendet Windows 10 Enterprise Diagnosedaten, um zusätzliche Informationen zu Windows 10 Update bereitzustellen. 
- [Microsoft Endpoint Manager](/mem/endpoint-manager-overview) – für die Geräteverwaltung und um Ihre Daten zu schützen.
  - [Microsoft Azure Active Directory](/azure/active-directory/) – für die Authentifizierung und Identifizierung aller Benutzerkonten. 
  - [Microsoft Intune](/mem/intune/) – für die Verteilung von Gerätekonfigurationen, Geräteverwaltung und Anwendungsverwaltung.
  - [Endpoint Analytics](/mem/analytics/overview) – für analysebasierte Einblicke zur Geräte- und App-Nutzung.
  - [Windows Autopilot](/microsoft-365/windows/windows-autopilot) – für die Bereitstellung und Bereitstellung von Geräten.
  - [Microsoft Defender für Endpunkt](/microsoft-365/security/defender-endpoint/) – bietet Sicherheitsdienste wie Gerätesicherheitsüberwachung und Security Intelligence-Daten.
- [Microsoft Managed Desktop](https://endpoint.microsoft.com/#home) – Vom Kunden bereitgestellte oder vom Dienst während der Ausführung des Diensts generierte Daten.
- [Microsoft 365 Apps für Unternehmen](https://www.microsoft.com/en-us/microsoft-365/enterprise/compare-office-365-plans?rtc=1) – für die Verwaltung von Microsoft 365 Apps.

## <a name="microsoft-managed-desktop-data-process-and-storage"></a>Microsoft Managed Desktop Datenprozess und -speicherung

Microsoft Managed Desktop nutzt Daten aus mehreren Microsoft-Produkten und -Diensten, um seine Dienste für Unternehmenskunden bereitzustellen. Um das Ziel des Schutzes und der Wartung registrierter Geräte zu erreichen, verarbeiten und kopieren wir Daten aus diesen Diensten in Microsoft Managed Desktop. Wenn wir Daten verarbeiten, folgen wir den dokumentierten Anweisungen, die Sie bereitstellen, wie in den Onlinedienstbedingungen und den Microsoft-Datenschutzbestimmungen beschrieben. Wenn wir Daten verarbeiten, folgen wir den dokumentierten Anweisungen, die Sie bereitstellen, wie in den [Nutzungsbedingungen](https://www.microsoft.com/licensing/product-licensing/products) für Onlinedienste und den [Microsoft-Datenschutzbestimmungen](https://privacy.microsoft.com/privacystatement)beschrieben. zu den Auftragsverarbeiteraufgaben Microsoft Managed Desktop gehören die Gewährleistung der angemessenen Vertraulichkeit, Sicherheit und Resilienz. Microsoft Managed Desktop setzt zusätzliche Datenschutz- und Sicherheitsmaßnahmen ein, um den ordnungsgemäßen Umgang mit personenbezogenen Daten sicherzustellen. 


## <a name="microsoft-managed-desktop-data-storage-and-staff-location"></a>Microsoft Managed Desktop Datenspeicherung und Mitarbeiterstandort

Microsoft Managed Desktop speichert seine Daten in den Azure-Rechenzentren in den USA. Personenbezogene Daten, die von Microsoft Managed Desktop und anderen Diensten abgerufen werden, sind erforderlich, um den Dienst betriebsbereit zu halten. Wenn ein Gerät aus Microsoft Managed Desktop entfernt wird, speichern wir personenbezogene Daten maximal 30 Tage, mit Ausnahme von Warnungsdaten, die von Microsoft Defender für Endpunkt gesammelt werden und für 180 Tage zu Sicherheitszwecken gespeichert werden. Weitere Informationen zur Datenaufbewahrung finden Sie unter [Datenaufbewahrung, Löschung und Vernichtung in Microsoft 365](/compliance/assurance/assurance-data-retention-deletion-and-destruction-overview).

Microsoft Managed Desktop Engineering Operations and Security Operations teams are located in the United States and India. 

## <a name="microsoft-windows-10-diagnostic-data"></a>Diagnosedaten von Microsoft Windows 10

Microsoft Managed Desktop verwendet [Windows 10 Erweiterte Diagnosedaten,](/windows/privacy/windows-diagnostic-data) um Windows sicher, auf dem neuesten Stand zu halten, Probleme zu beheben und Produktverbesserungen vorzunehmen. Die erweiterte Diagnosedateneinstellung enthält ausführlichere Informationen zu den geräten, die in Microsoft Managed Desktop registriert sind, sowie deren Einstellungen, Funktionen und Geräteintegrität. Wenn erweiterte Diagnosedaten ausgewählt werden, werden Daten, einschließlich der erforderlichen Diagnosedaten, gesammelt. Unter [Änderungen an Windows Diagnosedatensammlung](/windows/privacy/changes-to-windows-diagnostic-data-collection) finden Sie weitere Informationen über die einstellung Windows 10 Diagnosedaten und die Datensammlung.

Die Diagnosedatenterminologie wird sich in zukünftigen Versionen von Windows ändern. Microsoft Managed Desktop ist verpflichtet, nur die Daten zu verarbeiten, die der Dienst benötigt. Dies bedeutet zwar, dass die Diagnosestufe in **"Optional"** geändert wird, Microsoft Managed Desktop implementiert jedoch die eingeschränkten Diagnoserichtlinien, um die für den Dienst erforderliche Diagnosedatensammlung zu optimieren. Weitere Informationen finden Sie unter [Änderungen an Windows Diagnosedatensammlung.](/windows/privacy/changes-to-windows-diagnostic-data-collection)

Microsoft Managed Desktop verarbeitet und speichert nur Daten auf Systemebene aus Windows 10 optionalen Diagnosedaten, die von registrierten Geräten stammen, z. B. Informationen zur Zuverlässigkeit und Leistung von Anwendungen und Geräten. Microsoft Managed Desktop verarbeitet und speichert keine personenbezogenen Daten von Kunden wie Chat- und Browserverlauf, Sprach-, Text- oder Sprachdaten. 

Weitere Informationen zur Erfassung von Diagnosedaten von Microsoft Windows 10 finden Sie im Abschnitt ["Wo wir personenbezogene Daten speichern und verarbeiten"](https://privacy.microsoft.com/privacystatement#mainwherewestoreandprocessdatamodule) der Microsoft-Datenschutzbestimmungen.

## <a name="microsoft-windows-update-for-business"></a>Microsoft Windows Update for Business
Microsoft Windows Update for Business verwendet Daten aus Windows Diagnose, um den Updatestatus und Fehler zu analysieren. Microsoft Managed Desktop nutzt diese Daten und verwendet sie, um Probleme zu beheben und zu beheben, um sicherzustellen, dass alle registrierten Geräte basierend auf einem vordefinierten Update-Rhythmus auf dem neuesten Stand sind.

## <a name="microsoft-azure-active-directory"></a>Microsoft Azure Active Directory
Das Identifizieren von Daten, die von Microsoft Managed Desktop verwendet werden, wird von Azure Active Directory (Azure AD) an einem geografischen Standort basierend auf dem Standort gespeichert, der von der Organisation beim Abonnieren von Microsoft-Onlinediensten bereitgestellt wird, z. B. Microsoft Apps für Unternehmen und Azure. Das Identifizieren von Daten, die von Microsoft Managed Desktop verwendet werden, wird von Azure AD an einem geografischen Standort basierend auf dem von der Organisation bereitgestellten Standort gespeichert, wenn Microsoft-Onlinedienste wie Microsoft Apps für Unternehmen und Azure abonniert werden. Weitere Informationen dazu, wo sich Ihre Azure AD-Daten befinden, finden Sie unter [Azure Active Directory – Wo befinden sich Ihre Daten?](https://msit.powerbi.com/view?r=eyJrIjoiODdjOWViZDctMWRhZS00ODUzLWI4MmQtNWM5NjBkZTBkNjFlIiwidCI6IjcyZjk4OGJmLTg2ZjEtNDFhZi05MWFiLTJkN2NkMDExZGI0NyIsImMiOjV9)

## <a name="microsoft-intune"></a>Microsoft Intune
Microsoft Intune erfasst, verarbeitet und gibt Daten an Microsoft Managed Desktop weiter, um Geschäftsvorgänge und Dienste zu unterstützen. Weitere Informationen zu den in Intune gesammelten Daten finden Sie unter ["Datensammlung in Intune".](/mem/intune/protect/privacy-data-collect) 

Weitere Informationen zu Microsoft Intune Datenspeicherorten finden Sie unter [Where your Microsoft 365 customer data is stored](/microsoft-365/enterprise/o365-data-locations). Intune respektiert die vom Administrator getroffene Auswahl des Speicherorts für Kundendaten.

## <a name="microsoft-defender-for-endpoint"></a>Microsoft Defender für Endpunkt
Microsoft Defender für Endpunkt sammelt und speichert Informationen für Geräte, die in Microsoft Managed Desktop zu Verwaltungs-, Nachverfolgungs- und Berichterstellungszwecken registriert sind. Zu den erfassten Informationen gehören Dateidaten (z. B. Dateinamen, Größe und Hashes), Prozessdaten (ausgeführte Prozesse, Hashes), Registrierungsdaten, Netzwerkverbindungsdaten und Gerätedetails (z. B. Geräte-IDs, Gerätenamen und die Betriebssystemversion). Weitere Informationen zu Den Datensammlungs- und Speicherorten von Microsoft Defender für Endpunkt finden Sie unter Microsoft [Defender für Endpunkt.](/microsoft-365/security/defender-endpoint/data-storage-privacy#what-data-does-microsoft-defender-atp-collect) 

## <a name="microsoft-365-apps-for-enterprise"></a>Microsoft 365 Apps for Enterprise 
Microsoft 365 Apps for Enterprise sammelt und teilt Daten mit Microsoft Managed Desktop, um sicherzustellen, dass diese Apps auf der Grundlage vordefinierter, von Microsoft Managed Desktop verwalteter Updatekanäle mit der neuesten Version auf dem neuesten Stand sind. Weitere Informationen zu den Datensammlungs- und Speicherorten von Microsoft 365 Apps finden Sie unter [Microsoft Defender für Endpunkt.](/microsoft-365/security/defender-endpoint/data-storage-privacy#what-data-does-microsoft-defender-atp-collect)

## <a name="major-data-change-notification"></a>Benachrichtigung über wichtige Datenänderungen
Microsoft Managed Desktop folgt einem Änderungskontrollprozess, wie in unserem Dienstkommunikationsframework beschrieben. Wir benachrichtigen Kunden über das Microsoft 365 Nachrichtencenter und Microsoft Managed Desktop Verwaltungsportal sowohl über Sicherheitsvorfälle als auch über wichtige Änderungen am Dienst. Änderungen an den gesammelten Datentypen und dem Speicherort werden als wesentliche Änderungen betrachtet. Wir werden eine Benachrichtigung über diese Änderung mindestens 30 Tage lang bereitstellen, wie es für Microsoft 365 Produkte und Dienste üblich ist. Weitere Informationen finden Sie unter [Dienständerungen und Kommunikation.](/microsoft-365/managed-desktop/service-description/servicechanges)

## <a name="compliance"></a>Compliance
Microsoft Managed Desktop wurde externen Prüfungen unterzogen und hat eine umfassende Reihe von Compliance-Angeboten erhalten. Weitere Informationen finden Sie unter Microsoft Managed Desktop [Compliance.](/microsoft-365/managed-desktop/intro/compliance) Überwachungsberichte stehen im Microsoft [Service Trust Portal](https://aka.ms/stp)zum Download zur Verfügung, das als zentrales Repository für Microsoft Enterprise Onlinedienste dient. (Microsoft Managed Desktop wird in diesen Dokumenten unter der Kategorie "Überwachung und Verwaltung" aufgeführt.) 

## <a name="legal"></a>Rechtliche Hinweise
**Microsoft-Datenschutzhinweis für Endbenutzer von Produkten,** die von Organisationskunden bereitgestellt werden – In den [Microsoft-Datenschutzbestimmungen werden](https://privacy.microsoft.com/privacystatement) Endbenutzer darüber benachrichtigt, dass ihre Organisation, wenn sie sich mit einem Geschäftskonto bei Microsoft-Produkten anmelden, ihr Konto kontrollieren und verwalten kann (einschließlich der Kontrolle datenschutzbezogener Einstellungen) und auf ihre Daten zugreifen und diese verarbeiten kann, und b) Microsoft die Daten sammeln und verarbeiten kann, um den Dienst für die Organisation und die Endbenutzer bereitzustellen.
