---
title: Mandantenverwaltung für Microsoft 365 Enterprise
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
- m365solution-tenantmanagement
- m365solution-overview
- tenant-management
ms.custom:
- Ent_Solutions
description: Eine Übersicht über die Planung, Bereitstellung und den laufenden Betrieb Ihrer Microsoft 365 Mandanten.
ms.openlocfilehash: 42bde00fbd4ddc1cf92236f099a22b2260dbb980
ms.sourcegitcommit: 070724118be25cd83418d2a56863da95582dae65
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/03/2021
ms.locfileid: "50405678"
---
# <a name="tenant-management-for-microsoft-365-for-enterprise"></a>Mandantenverwaltung für Microsoft 365 Enterprise

Das Erstellen eines Pfads zur digitalen Transformation Ihrer Organisation mit Cloud Computing erfordert eine feste Grundlage, auf der sich Ihre Mitarbeiter auf Produktivität, Zusammenarbeit, Leistung, Datenschutz, Compliance und Sicherheit verlassen können.

Die richtige Konfiguration Ihrer Microsoft 365-Mandanten bietet diese Grundlage, damit Sich Ihre Mitarbeiter darauf konzentrieren können, ihre Arbeit zu erledigen, und Ihre IT-Abteilung kann sich auf End-to-End-Lösungen konzentrieren, die zusätzlichen geschäftlichen Nutzen bieten. 

Diese Lösung führt Sie durch die Konfiguration dieser Foundation in den folgenden Schritten:

1. Ermitteln Ihrer Mandanten
2. Optimieren Ihres Netzwerks
3. Synchronisieren Ihrer Identitäten und Erzwingen sicherer Anmeldungen
4. Migrieren Ihrer Windows Geräte, Office Clients und lokalen Office Server und Daten
5. Bereitstellen der Geräte- und App-Verwaltung

Zunächst sollten wir uns jedoch einen Moment zeit nehmen, um zu verstehen, was ein Mandant ist und wie ein Mandant aussieht, der eine feste Grundlage bietet.

## <a name="a-microsoft-365-tenant-defined"></a>Ein Microsoft 365 definierter Mandant

Ein Microsoft 365 ist eine dedizierte Instanz der Dienste von Microsoft 365 und Ihrer Organisation, die an einem bestimmten Standardspeicherort gespeichert sind, z. B. Europa oder Nordamerika. Dieser Speicherort wird angegeben, wenn Sie den Mandanten für Ihre Organisation erstellen. Jeder Microsoft 365 Mandanten ist unterschiedlich, eindeutig und von allen anderen Mandanten Microsoft 365 getrennt. Sie erstellen einen Microsoft 365, wenn Sie ein oder mehrere Produkte von Microsoft erwerben, z. B. Microsoft 365 E3 oder E5, und eine Reihe von Lizenzen für jeden.

Ihr Microsoft 365-Mandant umfasst auch einen Azure Active Directory (Azure AD) Mandanten, bei dem es sich um eine dedizierte Instanz von Azure AD für Benutzerkonten, Gruppen und andere Objekte handelt. Jeder Azure AD-Mandant ist unterschiedlich, eindeutig und von allen anderen Azure AD-Mandanten getrennt. Während Ihre Organisation mehrere Azure AD-Mandanten haben kann, die Sie mit Azure-Abonnements einrichten können, können Microsoft 365-Mandanten nur einen einzelnen Azure AD-Mandanten verwenden, den Mandanten, der beim Erstellen des Mandanten erstellt wurde. 

Hier ein Beispiel:

![Ein Beispiel Microsoft 365 Mandanten mit seinem Azure AD-Mandanten](../media/tenant-management-overview/tenant-management-example-tenant.png)

*Mandantenverwaltung* ist die Planung, Bereitstellung und der laufende Betrieb Ihrer Microsoft 365 Mandanten. 

## <a name="attributes-of-a-well-designed-and-operating-tenant"></a>Attribute eines gut entworfenen und operativen Mandanten

Über den richtigen Namen und Standort für Ihren Mandanten hinaus gibt es zusätzliche Elemente zum Planen, Bereitstellen und Verwalten, um sicherzustellen, dass Ihre Benutzererfahrungen mit Cloudproduktivitäts-Apps wie Microsoft Teams und Exchange Online effektiv, sicher und performant &mdash; &mdash; sind.

Hier sind die Elemente:

- Sie verfügen über den richtigen Satz von Produkten (Abonnements) und Lizenzen.
  - Der Satz von Produkten entspricht Ihren Geschäfts-, IT- und Sicherheitsanforderungen.
  - Es gibt eine ausreichende Anzahl von Lizenzen für Ihre Mitarbeiter und erwartete Änderungen bei der Personalbearbeitung.
- Für den Netzwerkbetrieb:
  - Sie haben die richtigen DNS-Domänennamen konfiguriert.
  - Für Unternehmensnetzwerke haben Sie den Netzwerkdatenverkehr zum Microsoft-Netzwerk für Mitarbeiter vor Ort optimiert.
  - Sie haben den Netzwerkdatenverkehr für Remotemitarbeiter optimiert, die einen VPN-Client verwenden.
- Sie haben Ihre Active Directory Domain Services (AD DS)-Konten, -Gruppen und andere Objekte synchronisiert.
  - Ihre Azure AD-Mandantenkonten werden Exchange Online Postfächern mit den richtigen DNS-Domänen für E-Mail-Adressen zugeordnet.
  - Ihren Benutzerkonten wurden die richtigen Lizenzen aus den richtigen gekauften Produkten zugewiesen (z. B. Microsoft 365 E3 oder E5).
- Sie haben eine starke Identitäts- und Zugriffsverwaltung konfiguriert.
  - Sie benötigen eine sichere Benutzer-Anmeldung mit kennwortloser oder mehrstufiger Authentifizierung (MFA).
  - Sie verfügen über Richtlinien für bedingten Zugriff, die Anmeldeanforderungen und Einschränkungen für höhere Sicherheitsstufen erzwingen.
- Lokale Office Server und deren Daten wurden zu Cloud-Apps migriert oder werden in einer Hybridkonfiguration verwendet.
- Sie verwenden die Geräteverwaltung mit Intune oder Basic Mobility and Security, die in die Microsoft 365.
  - Ihre Geräte im Besitz der Organisation werden registriert und verwaltet.
  - Die Apps für persönliche Geräte werden verwaltet.

Im Folgenden finden Sie ein Beispiel für Microsoft 365 Mandanten, in dem alle diese Elemente enthalten sind.

![Beispiel für Microsoft 365 Mandanten](../media/tenant-management-overview/tenant-management-tenant-config.png)

In dieser Abbildung enthält Microsoft 365 Mandanten:

- Produkte und Lizenzen für Microsoft 365 E3 und E5.
- Microsoft 365 Produktivitäts-Apps.
- Intune mit registrierten Geräten und Geräte- und Anwendungsrichtlinien.
- Ein Azure AD-Mandant mit synchronisierten Benutzerkonten (Gruppen und andere Verzeichnisobjekte werden nicht angezeigt), Domänen und Richtlinien für bedingten Zugriff.

## <a name="tenant-capabilities-for-microsoft-365-for-enterprise"></a>Mandantenfunktionen für Microsoft 365 Enterprise

In den folgenden Abschnitten und der Tabelle sind die wichtigsten Funktionen und Die Lizenzierung für die Schritte in dieser Lösung aufgeführt.

### <a name="tenant"></a>Mandant

| Funktion oder Feature | Beschreibung | Lizenzierung |
|:-------|:-----|:-------|
| Mehrere Mandanten | Jeder Microsoft 365 Mandanten ist unterschiedlich, eindeutig und von allen anderen Mandanten Microsoft 365 getrennt. Bei mehreren Mandanten gibt es Einschränkungen und zusätzliche Überlegungen beim Verwalten und Bereitstellen von Diensten für Ihre Benutzer. | Microsoft 365 E3 oder E5 | 
| Mandantenübergreifende Postfachmigration | Mandantenadministratoren können Postfächer zwischen Mandanten mit minimalen Infrastrukturabhängigkeiten in ihren lokalen Systemen verschieben. Dadurch wird die Notwendigkeit von Off-Board- und Onboardpostfächern entfernt. | Microsoft 365 E3 oder E5 | 
| Multi-Geo | Ihr Mandant kann ruhende Daten an den anderen geografischen Standorten des Rechenzentrums speichern, die Sie ausgewählt haben, um die Anforderungen an die Datenresidenz zu erfüllen. | Microsoft 365 E3 oder E5 | 
| Verschieben von Kerndaten in ein neues Geografisches Datencenter | Wenn Microsoft neue Rechenzentrums-Geos für zusätzliche Kapazitäts- und Rechenressourcen hinzufügt, können Sie eine geografische Datenvermittelung des Rechenzentrums für die In-Geo-Datenresidenz für Ihre Kernkundendaten anfordern. | Microsoft 365 E3 oder E5 | 
||||

### <a name="networking"></a>Netzwerk

| Funktion oder Feature | Beschreibung | Lizenzierung |
|:-------|:-----|:-------|
| Network Insights | Netzwerkleistungsmetriken, die von Ihrem mandanten Microsoft 365, um Ihnen beim Entwerfen von Netzwerkperimetern für Ihre Bürostandorte zu helfen. | Microsoft 365 E3 oder E5 | 
| Automatisieren von Endpunktupdates | Automatisieren Sie die Konfiguration und laufende Updates für Microsoft 365 Endpunkte in Ihren Client-PAC-Dateien und Netzwerkgeräten und -diensten. | Microsoft 365 E3 oder E5 | 
||||

### <a name="identity"></a>Identität

| Funktion oder Feature | Beschreibung | Lizenzierung |
|:-------|:-----|:-------|
| Synchronisieren der lokalen Active Directory Domain Services (AD DS) mit Ihrem Azure AD-Mandanten    | Nutzen Sie Ihren lokalen Identitätsanbieter für Benutzerkonten, Gruppen und andere Objekte. | Microsoft 365 E3 oder E5 |
| Mehrstufige Authentifizierung (MFA, Multi-Factor Authentication) mit Sicherheitsstandards erzwingen   | Schützen Sie sich vor kompromittierten Identitäten und Geräten, indem Sie eine zweite Authentifizierungsmethode für die Anmeldung vorsehen. Sicherheitsstandards schreiben MFA für alle Benutzerkonten vor.   | Microsoft 365 E3 oder E5 |
| Mehrstufige Authentifizierung (MFA, Multi-Factor Authentication) mit bedingtem Zugriff erzwingen| Fordern Sie MFA basierend auf den Attributen der Anmeldung mit Richtlinien für bedingten Zugriff an.    | Microsoft 365 E3 oder E5 | 
| Mehrstufige Authentifizierung (MFA, Multi-Factor Authentication) mit risikoabhängig bedingtem Zugriff erzwingen   | Erfordert MFA basierend auf dem Risiko der Benutzeranmeldung mit Microsoft Defender for Identity. | Microsoft 365 E5 oder E3 mit Azure AD Premium P2-Lizenzen | 
| Zurücksetzen von Kennwörtern durch den Benutzer (Self-Service Password Reset, SSPR)    | Ermöglichen Sie Ihren Benutzern das Zurücksetzen oder Entsperren ihrer Kennwörter oder Konten.  | Microsoft 365 E3 oder E5 |
||||

### <a name="migration"></a>Migration

| Funktion oder Feature | Beschreibung | Lizenzierung |
|:-------|:-----|:-------|
| Migration zu Windows 10 | Migrieren Sie Ihre Geräte, auf Windows 7 oder Windows 8.1 ausgeführt Windows 10 Enterprise. | Windows 10 Enterprise, die in Microsoft 365 E3 oder E5 enthalten sind | 
| Migrieren zu Microsoft 365 Apps for Enterprise | Migrieren Sie Office Client-Apps wie Word und PowerPoint zu den versionen, die aus der Cloud installiert sind, die mit neuen Features aktualisiert werden. | Microsoft 365 E3 oder E5 | 
| Migrieren sie lokale Server und Daten zu Microsoft 365 | Migrieren Sie Exchange Postfächer, SharePoint Websites und Skype for Business Online zu Microsoft 365 Cloud services. | Microsoft 365 E3 oder E5 | 
||||

### <a name="device-and-app-management"></a>Verwaltung von Geräten und Apps

| Funktion oder Feature | Beschreibung | Lizenzierung |
|:-------|:-----|:-------|
| Microsoft Intune | Ein cloudbasierter Dienst, der mobile Geräteverwaltung (Mobile Device Management, MDM) und Verwaltung mobiler Anwendungen (Mobile Application Management, MAM) bietet, um zu steuern, wie die Anwendung Ihrer Organisation und die Geräte verwendet werden, einschließlich Mobiltelefone, Tablets und Laptops. | Microsoft 365 E3 oder E5 | 
| Grundlegende Mobilität und Sicherheit | Sichern und verwalten Sie die mobilen Geräte Ihrer Benutzer wie iPhones, iPads, Androids und Windows mit diesem integrierten Dienst.  | Microsoft 365 E3 oder E5 | 
||||

## <a name="next-steps"></a>Nächste Schritte

Führen Sie diese Schritte aus, um Ihre Mandanten Microsoft 365 zu verwalten.

1. [Ermitteln Ihrer Mandanten](tenant-management-tenants.md)
2. [Optimieren Ihres Netzwerks](tenant-management-networking.md)
3. [Synchronisieren Ihrer Identitäten und Erzwingen sicherer Anmeldungen](tenant-management-identity.md)
4. [Migrieren Ihrer lokalen Office und Daten](tenant-management-migration.md)
5. [Bereitstellen der Geräte- und App-Verwaltung](tenant-management-device-management.md)

[![Die Schritte zum Bereitstellen und Verwalten eines Microsoft 365 Mandanten](../media/tenant-management-overview/tenant-management-step-grid.png)](tenant-management-tenants.md)

In jedem Schritt werden Bereitstellungsoptionen beschrieben, die Ergebnisse und laufende Wartungsaufgaben zusammengefasst.

Informationen dazu, wie eine fiktive, aber repräsentative multinationale Organisation die Elemente ihres mandanten Microsoft 365 bereitgestellt hat, finden Sie in der [Contoso-Fallstudie](../enterprise/contoso-case-study.md).
