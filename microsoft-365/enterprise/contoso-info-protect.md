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
ms.openlocfilehash: 1966fdec3de246ca54fd99ab018485b9ee817281
ms.sourcegitcommit: cd17328baa58448214487e3e68c37590ab9fd08d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/09/2020
ms.locfileid: "48399241"
---
# <a name="information-protection-for-the-contoso-corporation"></a>Informationsschutz für die Contoso Corporation

Contoso ist die Sicherheit und der Schutz seiner Informationen äußerst wichtig. So würde zum Beispiel der unbefugte Zugriff auf das geistige Eigentum des Unternehmens, das heißt die Beschreibung von Produktdesigns und eigene Herstellungstechniken, oder dessen Zerstörung zu einem enormen Wettbewerbsnachteil führen.

Bevor Sie Ihre vertraulichen und wertvollsten digitalen Objekte in die Cloud verschieben, haben Sie sichergestellt, dass Ihre lokalen Informations Klassifizierungs-und Schutzanforderungen in den cloudbasierten Diensten von Microsoft 365 for Enterprise unterstützt und implementiert wurden.

## <a name="contosos-data-security-classification"></a>Contosos Datensicherheitsklassifizierung

Contoso führte eine Analyse der Daten durch und ermittelte die folgenden Stufen.

| Stufe 1: Baseline | Stufe 2: Vertraulich | Stufe 3: Hochgradig reguliert |
|:-------|:-----|:-----|
| Daten sind verschlüsselt und nur für authentifizierte Benutzer verfügbar. <BR> <BR> Für alle lokal und in der Cloud-basierten Speicherung und Arbeitsauslastungen gespeicherten Daten bereitgestellt. Die Daten werden verschlüsselt, während Sie sich im Dienst befinden, und während der Übertragung zwischen dem Dienst und den Clientgeräten. <BR><BR> Beispiele für die Daten der Stufe 1 sind normale Geschäftskommunikation (E-Mail) und Dateien für Mitarbeiter in der Verwaltung, im Vertrieb oder im Kundendienst. | Stufe 1 plus strenger Authentifizierung und Schutz vor Datenverlust. <BR> <BR> Eine starke Authentifizierung umfasst Azure Multi-Factor Authentication (MFA) mit SMS-Validierung. Durch eine Verhinderung von Datenverlust wird sichergestellt, dass vertrauliche oder kritische Informationen die Microsoft-Cloud nicht verlassen. <BR><BR> Beispiele für Daten der Stufe 2 sind Finanz- und rechtliche Informationen sowie Forschungs- und Entwicklungsdaten für neue Produkte. | Stufe 2 plus höchstmöglicher Verschlüsselung, Authentifizierung und Überwachung. <BR> <BR>  Die höchstmögliche, den regionalen Regelungen entsprechende Verschlüsselung für gespeicherte Daten oder Daten in der Cloud kombiniert mit MFA über Smartcards und präzise Überwachung und Benachrichtigung. <BR> <BR> Beispiele für Daten der Stufe 3 sind personenbezogene Kunden- und Partnerdaten sowie technische Produktspezifikationen und proprietäre Fertigungsverfahren.  |
||||

## <a name="contosos-information-policies"></a>Contosos Datenrichtlinien
In der folgenden Tabelle sind die Informationsrichtlinien von Contoso aufgeführt.


| Wert | Zugriff | Datenaufbewahrung
 | Schutz von Daten
 |
|:-------|:-----|:-----|:-----|
| Geringer Geschäftswert (Stufe 1: Baseline) | Zugriff auf alles zulassen  | 6 Monate | Verschlüsselung verwenden. |
| Mittlerer Geschäftswert (Stufe 2: Vertraulich) | Zugriff für Mitarbeiter, Subunternehmer und Partner von Contoso zulassen <BR> <BR> MFA, Transport Layer Security (TLS) und mobile Anwendungsverwaltung (Mobile Application Management, MAM) verwenden. | 2 Jahre  | Hashwerte für Datenintegrität verwenden.  |
| Hoher Geschäftswert (Stufe 3: Hochgradig reguliert) | Zugriff für Manager und Führungskräfte in Technik und Fertigung zulassen. <BR> <BR> Rechteverwaltungssystem (Rights Management System, RMS) nur mit verwalteten Netzwerkgeräten.  | 7 Jahre  | Digitale Signaturen für Nachweisbarkeit (Unleugbarkeit) verwenden.  |
|||||

## <a name="contosos-path-to-information-protection-with-microsoft-365-for-enterprise"></a>Contosos Pfad zum Informationsschutz mit Microsoft 365 für Unternehmen

Contoso hat die folgenden Schritte ausgeführt, um Microsoft 365 für Unternehmen auf Ihre Anforderungen an den Informationsschutz vorzubereiten:

1. Ermitteln, welche Informationen geschützt werden müssen

   Contoso führte eine umfassende Prüfung der vorhandenen digitalen Datenbestände durch, die sich auf lokalen SharePoint-Websites und auf Dateifreigaben befinden, und klassifizierte sie einzeln.

2. Festlegen des Zugriffs, der Aufbewahrung und der Informationsschutzrichtlinien für Datenstufen

   Basierend auf den Datenstufen ermittelte Contoso detaillierte Richtlinienanforderungen, die zum Schützen vorhandener digitaler Datenbestände während des Verschiebens in die Cloud verwendet wurden.

3. Erstellen von Vertraulichkeitsbezeichnungen und Einstellungen für die verschiedenen Informationsstufen

   Contoso hat Vertraulichkeitsbezeichnungen (hochgradig reguliert) für seine Datenstufen erstellt, die Verschlüsselung, Berechtigungen und Wasserzeichen umfasst.

4.  Verschieben der Daten von den lokalen SharePoint-Websites und Dateifreigaben in die neuen SharePoint-Websites

    Die Dateien, die zu den neuen SharePoint-Websites migriert wurden, übernahmen die standardmäßigen Aufbewahrungsbezeichnungen, die der Website zugewiesen waren.

5.  Schulen der Mitarbeiter im Hinblick auf die Verwendung von Aufbewahrungsbezeichnungen für neue Dokumente, die Interaktion mit den Contoso-IT-Mitarbeitern beim Erstellen neuer SharePoint-Websites und das stetige Speichern von digitalen Assets auf SharePoint-Websites

    Folgendes galt als der schwierigste Teil des Informationsschutzübergangs in die Cloud: Die IT-Mitarbeiter von Contoso und das Management mussten die schlechten Angewohnheiten der Mitarbeiter, wenn es um Informationsspeicherung geht, ändern und sie anhalten, digitale Assets immer mit Bezeichnungen zu versehen und zu speichern, keine lokalen Dateifreigaben und nie Cloudspeicherdienste von Drittanbietern oder USB-Laufwerke zu verwenden.

## <a name="conditional-access-policies-for-information-protection"></a>Bedingte Zugriffsrichtlinien für Informationsschutz

Contoso konfigurierte zusammen mit seiner Infrastruktur für die Verwaltung von Identitäten und mobilen Geräten sowie als Teil des Exchange Online- und SharePoint-Rollouts die folgenden Sätze von bedingten Zugriffsrichtlinien und wendete sie auf die entsprechenden Gruppen an:

- [Richtlinien für den verwalteten und nicht verwalteten Zugriff auf Geräteanwendungen](../security/office-365-security/identity-access-policies.md)
- [Exchange Online-Zugriffsrichtlinien](../security/office-365-security/secure-email-recommended-policies.md)
- [SharePoint-Zugriffsrichtlinien](../security/office-365-security/sharepoint-file-access-policies.md)

Hier sehen Sie den von Contoso erstellten Satz von Informationsschutzrichtlinien.

![Bedinge Zugriffsrichtlinien für Geräte, Exchange Online und SharePoint](../media/contoso-info-protect/contoso-info-protect-fig1.png)

>[!Note]
>Contoso konfigurierte darüber hinaus zusätzliche bedingte Zugriffsrichtlinien für Identität und Anmeldung. Siehe [Identität für die Contoso Corporation](contoso-identity.md#conditional-access-policies-for-identity-and-device-access).
>

Diese Richtlinien stellen Folgendes sicher:

- Apps sind zulässig und die Aktionen, die diese Apps mit den Unternehmensdaten ausführen können, werden durch die App-Schutzrichtlinien definiert.
- PCs und mobile Geräte müssen diesen Richtlinien entsprechen.
- Exchange Online verwendet Office 365 Nachrichtenverschlüsselung (OM) für Exchange Online.
- SharePoint verwendet die durch die App erzwungenen Einschränkungen.
- SharePoint verwendet Zugriffssteuerungsrichtlinien für den reinen Browserzugriff und zum Blockieren des Zugriffs über nicht verwaltete Geräte.

## <a name="mapping-microsoft-365-for-enterprise-features-to-contosos-data-levels"></a>Zuordnen von Microsoft 365 für Enterprise-Features zu Contosos Datenebenen

In der folgenden Tabelle werden die Datenebenen von Contoso den Informationen Schutzfeatures in Microsoft 365 für Unternehmen zugeordnet.

| Stufe | Microsoft 365 Cloud Services | Windows 10 und Microsoft 365 Apps for Enterprise | Sicherheit und Compliance |
|:-------|:-----|:-----|:-----|
| Stufe 1: Baseline  | Bedingte Zugriffsrichtlinien für SharePoint und Exchange Online <BR> Berechtigungen für SharePoint-Websites | Vertraulichkeitsbezeichnungen <BR> BitLocker <BR> Windows Information Protection | Bedingte Zugriffsrichtlinien für Geräte und MAM-Richtlinien (Mobile Application Management) |
| Stufe 2: Vertraulich | Stufe 1 plus: <BR> <BR> Vertraulichkeitsbezeichnungen <BR> Microsoft 365-Aufbewahrungsbezeichnungen auf SharePoint-Websites <BR> Verhinderung von Datenverlust für SharePoint und Exchange Online <BR> Isolierte SharePoint-Websites  | Stufe 1 plus: <BR> <BR> Vertraulichkeitsbezeichnungen auf digitalen Assets  | Stufe 1 |
| Stufe 3: Hochgradig reguliert | Stufe 2 plus: <BR><BR> BYOK-Verschlüsselung („Bring Your Own Key“, Bereitstellen eines eigenen Schlüssels) und Schutz von Geschäftsgeheimnissen <BR> Azure Key Vault für Branchenlösungen, die mit Diensten von Microsoft 365 interagieren | Stufe 2 | Stufe 1 |
|||||

Hier sehen Sie die resultierende Informationsschutzkonfiguration von Contoso.

![Resultierende Informationsschutzkonfiguration von Contoso](../media/contoso-info-protect/contoso-info-protect-fig2.png)

## <a name="next-step"></a>Nächster Schritt

[Erfahren Sie](contoso-security-summary.md) , wie Contoso die Sicherheitsfunktionen in Microsoft 365 für Unternehmen für Identitäts-und Zugriffsverwaltung, Bedrohungsschutz, Informationsschutz und Sicherheitsverwaltung verwendet hat.

## <a name="see-also"></a>Siehe auch

[Sicherheitsroadmap](https://docs.microsoft.com/microsoft-365/security/office-365-security/security-roadmap)

[Übersicht über Microsoft 365 Enterprise](microsoft-365-overview.md)

[Testumgebungsanleitungen](m365-enterprise-test-lab-guides.md)


