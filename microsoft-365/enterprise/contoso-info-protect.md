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
description: Verstehen, wie Contoso die Informationsschutzfeatures in Microsoft 365 für Unternehmen verwendet, um seine digitalen Objekte in der Cloud zu sichern.
ms.openlocfilehash: bb797fa4f71b699069f8542b8bc7a353a9ee1698
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/03/2021
ms.locfileid: "53288671"
---
# <a name="information-protection-for-the-contoso-corporation"></a>Informationsschutz für die Contoso Corporation

Contoso ist mit seiner Informationssicherheit sehr ernst. Die Vernichtung oder Vernichtung von geistigem Eigentum, die ihre Produktdesigns und proprietären Herstellungstechniken beschreibt, würde sie in einen Wettbewerbsvorteil benachteiligen.

Bevor Contoso seine vertraulichen digitalen Objekte in die Cloud verlagern musste, vergewisserte sich Contoso, dass die lokalen Anforderungen an die Informationsklassifizierung und den Schutz durch die cloudbasierten Dienste von Microsoft 365 für Unternehmen unterstützt wurden.

## <a name="contoso-data-security-classification"></a>Contoso-Datensicherheitsklassifizierung

Contoso führte eine Analyse seiner Daten durch und ermittelte die folgenden Klassifizierungsebenen.

| Stufe 1: Baseline | Stufe 2: Vertraulich | Stufe 3: Hochgradig reguliert |
|:-------|:-----|:-----|
| Daten sind verschlüsselt und nur für authentifizierte Benutzer verfügbar.<BR> <BR> Wird für alle Daten bereitgestellt, die lokal und in cloudbasiertem Speicher und Workloads gespeichert sind. Daten werden verschlüsselt, während sie sich im Dienst und im Übergang zwischen dem Dienst und Clientgeräten befinden. <BR><BR>Beispiele für die Daten der Stufe 1 sind normale Geschäftskommunikation (E-Mail) und Dateien für Mitarbeiter in der Verwaltung, im Vertrieb oder im Kundendienst. | Stufe 1 plus strenger Authentifizierung und Schutz vor Datenverlust.<BR> <BR> Die starke Authentifizierung umfasst die mehrstufige Azure AD-Authentifizierung (Multi-Factor Authentication, MFA) mit SMS-Überprüfung. Die Verhinderung von Datenverlust stellt sicher, dass vertrauliche oder kritische Informationen nicht außerhalb der Microsoft-Cloud übertragen werden.<BR><BR>Beispiele für Daten der Stufe 2 sind Finanz- und rechtliche Informationen sowie Forschungs- und Entwicklungsdaten für neue Produkte. | Stufe 2 plus höchstmöglicher Verschlüsselung, Authentifizierung und Überwachung.<BR><BR>Die höchstmögliche, den regionalen Regelungen entsprechende Verschlüsselung für gespeicherte Daten oder Daten in der Cloud kombiniert mit MFA über Smartcards und präzise Überwachung und Benachrichtigung.<BR> <BR>Beispiele für Daten der Stufe 3 sind persönliche Kunden- und Partnerinformationen, Produktentwicklungsspezifikationen und proprietäre Fertigungstechniken.  |
||||

## <a name="contoso-information-policies"></a>Contoso-Informationsrichtlinien
In der folgenden Tabelle sind die Contoso-Informationsrichtlinien aufgeführt.


| Wert | Zugriff | Datenaufbewahrung
 | Schutz von Daten
 |
|:-------|:-----|:-----|:-----|
| Geringer Geschäftswert (Stufe 1: Baseline) | Zugriff auf alle zulassen.  | 6 Monate | Verschlüsselung verwenden. |
| Mittlerer Geschäftswert (Stufe 2: Vertraulich) | Zugriff auf Contoso-Mitarbeiter, Subunternehmer und Partner zulassen. <BR><BR> MFA, Transport Layer Security (TLS) und mobile Anwendungsverwaltung (Mobile Application Management, MAM) verwenden. | 2 Jahre  | Hashwerte für Datenintegrität verwenden.  |
| Hoher Geschäftswert (Stufe 3: Hochgradig reguliert) | Zugriff für Manager und Führungskräfte in Technik und Fertigung zulassen. <BR> <BR> Rechteverwaltungssystem (Rights Management System, RMS) nur mit verwalteten Netzwerkgeräten.  | 7 Jahre  | Digitale Signaturen für Nachweisbarkeit (Unleugbarkeit) verwenden.  |
|||||

## <a name="the-contoso-path-to-information-protection-with-microsoft-365-for-enterprise"></a>Der Contoso-Pfad zum Informationsschutz mit Microsoft 365 enterprise

Contoso hat die folgenden Schritte ausgeführt, um Microsoft 365 für Unternehmen auf seine Anforderungen an den Informationsschutz vorzubereiten:

1. Identifizieren, welche Informationen geschützt werden sollen

   Contoso hat seine vorhandenen digitalen Ressourcen, die sich lokal SharePoint Websites und Dateifreigaben befinden, umfassend überprüft und jede Ressource klassifiziert.

2. Bestimmen von Zugriffs-, Aufbewahrungs- und Datensicherungsrichtlinien für Datenstufen

   Basierend auf den Datenstufen ermittelte Contoso detaillierte Richtlinienanforderungen, die zum Schützen vorhandener digitaler Datenbestände während des Verschiebens in die Cloud verwendet wurden.

3. Erstellen von Vertraulichkeitsbezeichnungen und deren Einstellungen für die verschiedenen Informationsebenen

   Contoso hat Vertraulichkeitsbezeichnungen (hochgradig reguliert) für seine Datenstufen erstellt, die Verschlüsselung, Berechtigungen und Wasserzeichen umfasst.

4. Verschieben von Daten von lokalen SharePoint Websites und Dateifreigaben zu ihren neuen SharePoint Websites

    Die Dateien, die zu den neuen SharePoint-Websites migriert wurden, übernahmen die standardmäßigen Aufbewahrungsbezeichnungen, die der Website zugewiesen waren.

5. Schulen Von Mitarbeitern, wie Vertraulichkeitsbezeichnungen für neue Dokumente verwendet werden, wie sie mit contoso IT interagieren, wenn sie neue SharePoint Websites erstellen, und digitale Objekte immer auf SharePoint Websites speichern

    Das Ändern schlechter Arbeitsdatenspeicherungsgewohnheiten wird häufig als der schwierigste Teil des Informationsschutzübergangs für die Cloud betrachtet. Die IT-Abteilung und das Management von Contoso mussten dazu führen, dass Mitarbeiter ihre digitalen Ressourcen immer in der Cloud bezeichnen und speichern, keine lokalen Dateifreigaben verwenden und keine Cloudspeicherdienste von Drittanbietern oder USB-Laufwerke verwenden.

## <a name="conditional-access-policies-for-information-protection"></a>Bedingte Zugriffsrichtlinien für Informationsschutz

Im Rahmen des Rollouts von Exchange Online und SharePoint konfigurierte Contoso den folgenden Satz von Richtlinien für bedingten Zugriff und wendete sie auf die entsprechenden Gruppen an:

- [Richtlinien für den verwalteten und nicht verwalteten Zugriff auf Geräteanwendungen](../security/office-365-security/identity-access-policies.md)
- [Exchange Online-Zugriffsrichtlinien](../security/office-365-security/secure-email-recommended-policies.md)
- [SharePoint-Zugriffsrichtlinien](../security/office-365-security/sharepoint-file-access-policies.md)

Hier sehen Sie eine Reihe von Contoso-Richtlinien für den Informationsschutz.

![Bedinge Zugriffsrichtlinien für Geräte, Exchange Online und SharePoint](../media/contoso-info-protect/contoso-info-protect-fig1.png)

>[!Note]
>Contoso konfigurierte darüber hinaus zusätzliche bedingte Zugriffsrichtlinien für Identität und Anmeldung. Siehe [Identität für die Contoso Corporation](contoso-identity.md#conditional-access-policies-for-identity-and-device-access).
>

Diese Richtlinien stellen Folgendes sicher:

- Apps, die zulässig sind, und die Aktionen, die sie mit den Daten der Organisation ausführen können, werden durch App-Schutzrichtlinien definiert.
- PCs und mobile Geräte müssen diesen Richtlinien entsprechen.
- Exchange Online verwendet Office 365 Nachrichtenverschlüsselung (Message Encryption, OME) für Exchange Online.
- SharePoint verwendet von der App erzwungene Einschränkungen.
- SharePoint verwendet Zugriffssteuerungsrichtlinien für den reinen Browserzugriff und zum Blockieren des Zugriffs über nicht verwaltete Geräte.

## <a name="mapping-microsoft-365-for-enterprise-features-to-contoso-data-levels"></a>Zuordnen von Microsoft 365 für Unternehmensfeatures zu Contoso-Datenebenen

In der folgenden Tabelle werden Contoso-Datenebenen den Informationsschutzfeatures in Microsoft 365 enterprise zugeordnet.

| Ebene | Microsoft 365 Clouddienste | Windows 10 und Microsoft 365 Apps for Enterprise | Sicherheit und Compliance |
|:-------|:-----|:-----|:-----|
| Stufe 1: Baseline  | Bedingte Zugriffsrichtlinien für SharePoint und Exchange Online <BR> Berechtigungen für SharePoint-Websites | Vertraulichkeitsbezeichnungen <BR> BitLocker <BR> Windows Information Protection | Bedingte Zugriffsrichtlinien für Geräte und MAM-Richtlinien (Mobile Application Management) |
| Stufe 2: Vertraulich | Stufe 1 plus: <BR> <BR> Vertraulichkeitsbezeichnungen <BR> Microsoft 365-Aufbewahrungsbezeichnungen auf SharePoint-Websites <BR> Verhinderung von Datenverlust für SharePoint und Exchange Online <BR> Isolierte SharePoint-Websites  | Stufe 1 plus: <BR> <BR> Vertraulichkeitsbezeichnungen auf digitalen Assets  | Stufe 1 |
| Stufe 3: Hochgradig reguliert | Stufe 2 plus: <BR><BR> Bring your own key (BYOK) encryption and protection for trade secret information <BR> Azure Key Vault für Branchenanwendungen, die mit Microsoft 365 Diensten interagieren | Stufe 2 | Stufe 1 |
|||||

Hier sehen Sie die resultierende Contoso-Informationsschutzkonfiguration.

![Resultierende Informationsschutzkonfiguration von Contoso](../media/contoso-info-protect/contoso-info-protect-fig2.png)

## <a name="next-step"></a>Nächster Schritt

Erfahren Sie, wie Contoso die [Sicherheitsfeatures für Microsoft 365 Unternehmen für](contoso-security-summary.md) Identitäts- und Zugriffsverwaltung, Bedrohungsschutz, Informationsschutz und Sicherheitsverwaltung verwendet.

## <a name="see-also"></a>Weitere Informationen:

[Sicherheitsroadmap](../security/office-365-security/security-roadmap.md)

[Übersicht über Microsoft 365 Enterprise](microsoft-365-overview.md)

[Testumgebungsanleitungen](m365-enterprise-test-lab-guides.md)