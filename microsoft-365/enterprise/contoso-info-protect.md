---
title: Informationsschutz für die Contoso Corporation
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
ms.date: 10/02/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
ms.custom: ''
description: Erfahren Sie, wie Contoso die Features für den Informationsschutz in Microsoft 365 für Unternehmen verwendet, um Ihre digitalen Objekte in der Cloud zu sichern.
ms.openlocfilehash: a1aa08a20d284d3a003f4a406c37f2107ce19bd1
ms.sourcegitcommit: 66b8fc1d8ba4f17487cd2004ac19cf2fff472f3d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2020
ms.locfileid: "48754601"
---
# <a name="information-protection-for-the-contoso-corporation"></a>Informationsschutz für die Contoso Corporation

Contoso geht es ernst mit ihrer Informationssicherheit. Das Durchsickern oder zerstören von geistigem Eigentum, das Ihre Produktdesigns und proprietären Fertigungstechniken beschreibt, würde Sie Wettbewerbsnachteile bringen.

Vor dem Verschieben Ihrer vertraulichen digitalen Objekte in die Cloud hat Contoso sichergestellt, dass die lokalen Informations Klassifizierungs-und Schutzanforderungen von den cloudbasierten Diensten von Microsoft 365 for Enterprise unterstützt wurden.

## <a name="contoso-data-security-classification"></a>Contoso-Daten Sicherheitsklassifizierung

Contoso hat eine Analyse der Daten durchgeführt und die folgenden Klassifizierungsstufen ermittelt.

| Stufe 1: Baseline | Stufe 2: Vertraulich | Stufe 3: Hochgradig reguliert |
|:-------|:-----|:-----|
| Daten sind verschlüsselt und nur für authentifizierte Benutzer verfügbar.<BR> <BR> Für alle lokal und in der Cloud-basierten Speicherung und Arbeitsauslastungen gespeicherten Daten bereitgestellt. Die Daten werden verschlüsselt, während Sie sich im Dienst befinden, und während der Übertragung zwischen dem Dienst und den Clientgeräten. <BR><BR>Beispiele für die Daten der Stufe 1 sind normale Geschäftskommunikation (E-Mail) und Dateien für Mitarbeiter in der Verwaltung, im Vertrieb oder im Kundendienst. | Stufe 1 plus strenger Authentifizierung und Schutz vor Datenverlust.<BR> <BR> Eine starke Authentifizierung umfasst Azure Multi-Factor Authentication (MFA) mit SMS-Validierung. Durch Verhinderung von Datenverlust wird sichergestellt, dass vertrauliche oder wichtige Informationen nicht außerhalb der Microsoft-Cloud Reisen.<BR><BR>Beispiele für Daten der Stufe 2 sind Finanz- und rechtliche Informationen sowie Forschungs- und Entwicklungsdaten für neue Produkte. | Stufe 2 plus höchstmöglicher Verschlüsselung, Authentifizierung und Überwachung.<BR><BR>Die höchstmögliche, den regionalen Regelungen entsprechende Verschlüsselung für gespeicherte Daten oder Daten in der Cloud kombiniert mit MFA über Smartcards und präzise Überwachung und Benachrichtigung.<BR> <BR>Beispiele für Daten der Stufe 3 sind Kunden-und Partner personenbezogene Informationen, Produkt Technische Spezifikationen und proprietäre Fertigungstechniken.  |
||||

## <a name="contoso-information-policies"></a>Contoso-Informationsrichtlinien
In der folgenden Tabelle sind die Contoso-Informationsrichtlinien aufgeführt.


| Wert | Zugriff | Datenaufbewahrung
 | Schutz von Daten
 |
|:-------|:-----|:-----|:-----|
| Geringer Geschäftswert (Stufe 1: Baseline) | Zugriff auf alle zulassen.  | 6 Monate | Verschlüsselung verwenden. |
| Mittlerer Geschäftswert (Stufe 2: Vertraulich) | Zugriff auf contoso-Mitarbeiter, Subunternehmer und Partner zulassen. <BR><BR> MFA, Transport Layer Security (TLS) und mobile Anwendungsverwaltung (Mobile Application Management, MAM) verwenden. | 2 Jahre  | Hashwerte für Datenintegrität verwenden.  |
| Hoher Geschäftswert (Stufe 3: Hochgradig reguliert) | Zugriff für Manager und Führungskräfte in Technik und Fertigung zulassen. <BR> <BR> Rechteverwaltungssystem (Rights Management System, RMS) nur mit verwalteten Netzwerkgeräten.  | 7 Jahre  | Digitale Signaturen für Nachweisbarkeit (Unleugbarkeit) verwenden.  |
|||||

## <a name="the-contoso-path-to-information-protection-with-microsoft-365-for-enterprise"></a>Der Contoso-Pfad zum Informationsschutz mit Microsoft 365 für Unternehmen

Contoso hat die folgenden Schritte ausgeführt, um Microsoft 365 for Enterprise auf Ihre Anforderungen an den Informationsschutz vorzubereiten:

1. Identifizieren der zu schützenden Informationen

   Contoso hat eine umfassende Überprüfung der vorhandenen digitalen Objekte vorgenommen, die sich auf lokalen SharePoint-Websites und Dateifreigaben befinden, und klassifiziert jede Ressource.

2. Bestimmen von Zugriffs-, Aufbewahrungs- und Datensicherungsrichtlinien für Datenstufen

   Basierend auf den Datenstufen ermittelte Contoso detaillierte Richtlinienanforderungen, die zum Schützen vorhandener digitaler Datenbestände während des Verschiebens in die Cloud verwendet wurden.

3. Erstellen von Sensitivitäts Bezeichnungen und deren Einstellungen für die verschiedenen Informationsebenen

   Contoso hat Vertraulichkeitsbezeichnungen (hochgradig reguliert) für seine Datenstufen erstellt, die Verschlüsselung, Berechtigungen und Wasserzeichen umfasst.

4.  Migrieren von Daten aus lokalen SharePoint-Websites und Dateifreigaben in Ihre neuen SharePoint-Websites

    Die Dateien, die zu den neuen SharePoint-Websites migriert wurden, übernahmen die standardmäßigen Aufbewahrungsbezeichnungen, die der Website zugewiesen waren.

5.  Schulung der Mitarbeiter für die Verwendung von Sensitivitäts Bezeichnungen für neue Dokumente, die Interaktion mit Contoso IT beim Erstellen neuer SharePoint-Websites und das digitale Speichern digitaler Objekte auf SharePoint-Websites

    Ändern von schlechten Arbeitsinformationen – Speicher Gewohnheiten werden häufig als der schwierigste Teil des Informationsschutz Übergangs für die Cloud betrachtet. IT und Verwaltung von Contoso erforderlich, damit Mitarbeiter ihre digitalen Objekte in der Cloud immer bezeichnen und speichern können, ohne lokale Dateifreigaben zu verwenden und Drittanbieter-cloudspeicher oder USB-Laufwerke nicht zu nutzen.

## <a name="conditional-access-policies-for-information-protection"></a>Bedingte Zugriffsrichtlinien für Informationsschutz

Im Rahmen der Einführung von Exchange Online und SharePoint hat Contoso die folgenden Richtlinien für den bedingten Zugriff konfiguriert und auf die entsprechenden Gruppen angewendet:

- [Richtlinien für den verwalteten und nicht verwalteten Zugriff auf Geräteanwendungen](../security/office-365-security/identity-access-policies.md)
- [Exchange Online-Zugriffsrichtlinien](../security/office-365-security/secure-email-recommended-policies.md)
- [SharePoint-Zugriffsrichtlinien](../security/office-365-security/sharepoint-file-access-policies.md)

Im folgenden finden Sie eine Reihe von Contoso-Richtlinien für den Informationsschutz.

![Bedinge Zugriffsrichtlinien für Geräte, Exchange Online und SharePoint](../media/contoso-info-protect/contoso-info-protect-fig1.png)

>[!Note]
>Contoso konfigurierte darüber hinaus zusätzliche bedingte Zugriffsrichtlinien für Identität und Anmeldung. Siehe [Identität für die Contoso Corporation](contoso-identity.md#conditional-access-policies-for-identity-and-device-access).
>

Diese Richtlinien stellen Folgendes sicher:

- Apps, die zulässig sind und die Aktionen, die Sie mit den Daten der Organisation durchführen können, werden durch APP-Schutzrichtlinien definiert.
- PCs und mobile Geräte müssen diesen Richtlinien entsprechen.
- Exchange Online verwendet Office 365 Nachrichtenverschlüsselung (OM) für Exchange Online.
- SharePoint verwendet App-erzwungene Einschränkungen.
- SharePoint verwendet Zugriffssteuerungsrichtlinien für den reinen Browserzugriff und zum Blockieren des Zugriffs über nicht verwaltete Geräte.

## <a name="mapping-microsoft-365-for-enterprise-features-to-contoso-data-levels"></a>Zuordnen von Microsoft 365 für Enterprise-Features zu Contoso-Datenebenen

In der folgenden Tabelle werden die Contoso-Datenebenen den Features für den Informationsschutz in Microsoft 365 für Unternehmen zugeordnet.

| Stufe | Microsoft 365 Cloud Services | Windows 10 und Microsoft 365 Apps for Enterprise | Sicherheit und Compliance |
|:-------|:-----|:-----|:-----|
| Stufe 1: Baseline  | Bedingte Zugriffsrichtlinien für SharePoint und Exchange Online <BR> Berechtigungen für SharePoint-Websites | Vertraulichkeitsbezeichnungen <BR> BitLocker <BR> Windows Information Protection | Bedingte Zugriffsrichtlinien für Geräte und MAM-Richtlinien (Mobile Application Management) |
| Stufe 2: Vertraulich | Stufe 1 plus: <BR> <BR> Vertraulichkeitsbezeichnungen <BR> Microsoft 365-Aufbewahrungsbezeichnungen auf SharePoint-Websites <BR> Verhinderung von Datenverlust für SharePoint und Exchange Online <BR> Isolierte SharePoint-Websites  | Stufe 1 plus: <BR> <BR> Vertraulichkeitsbezeichnungen auf digitalen Assets  | Stufe 1 |
| Stufe 3: Hochgradig reguliert | Stufe 2 plus: <BR><BR> Bringen Sie Ihre eigene Schlüssel Verschlüsselung (BYOK) und Schutz für Handelsgeheimnis-Informationen <BR> Azure Key Vault für Branchenanwendungen, die mit Microsoft 365-Diensten interagieren | Stufe 2 | Stufe 1 |
|||||

Hier ist die resultierende Konfiguration des Contoso-Informationsschutzes.

![Resultierende Informationsschutzkonfiguration von Contoso](../media/contoso-info-protect/contoso-info-protect-fig2.png)

## <a name="next-step"></a>Nächster Schritt

Erfahren Sie, wie Contoso die [Sicherheitsfunktionen in Microsoft 365 für Unternehmen](contoso-security-summary.md) für Identitäts-und Zugriffsverwaltung, Bedrohungsschutz, Informationsschutz und Sicherheitsverwaltung verwendet.

## <a name="see-also"></a>Siehe auch

[Sicherheitsroadmap](https://docs.microsoft.com/microsoft-365/security/office-365-security/security-roadmap)

[Übersicht über Microsoft 365 Enterprise](microsoft-365-overview.md)

[Testumgebungsanleitungen](m365-enterprise-test-lab-guides.md)
