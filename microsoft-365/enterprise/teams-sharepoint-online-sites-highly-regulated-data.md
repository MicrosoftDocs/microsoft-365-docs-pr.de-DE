---
title: Microsoft Teams und SharePoint Online-Websites für streng geregelte Daten
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
ms.date: 04/03/2019
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
ms.custom: ''
description: Erstellen Sie eine sichere SharePoint Online-Teamwebsite oder ein Microsoft Teams-Team, um Ihre wertvollsten und vertraulichen digitalen Objekte zu speichern.
ms.openlocfilehash: d80be334f692f905ec70ae43f851d2b73801f4a0
ms.sourcegitcommit: dbcc32218489ab256b7eb343290fcccb9bc04e36
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/02/2019
ms.locfileid: "33553324"
---
# <a name="microsoft-teams-and-sharepoint-online-sites-for-highly-regulated-data"></a>Microsoft Teams und SharePoint Online-Websites für streng geregelte Daten

*Dieses Szenario gilt für die Versionen E3 und E5 von Microsoft 365 Enterprise.*

Microsoft 365 Enterprise umfasst eine vollständige Suite cloudbasierter Dienste, damit Sie streng geregelte Daten erstellen, speichern und schützen können. Dazu gehören folgende Daten:

- Daten, die regionalen Vorschriften unterliegen.
- Die wertvollsten Daten für Ihre Organisation, z. B. Geschäftsgeheimnisse, Informationen zu Finanzen oder Personalwesen und die Organisationsstrategie.

Für eine cloudbasierte Microsoft 365 Enterprise-Lösung, die diese Geschäftsanforderung erfüllt, müssen Sie:

- Digitale Objekte (Dokumente, Foliengruppen, Kalkulationstabellen usw.) in einer SharePoint Online-Teamwebsite oder auf der Registerkarte **Dateien** eines Microsoft Teams-Teams speichern.
- Die Website oder das Team sperren, um Folgendes zu verhindern:
   - Nur Zugriff auf eine bestimmte Gruppe von Benutzerkonten über Gruppenmitgliedschaft; dazu gehören Benutzer, die auf die SharePoint Online-Teamwebsite zugreifen können und mit welcher Berechtigungsstufe, und Benutzer, die diese verwalten können.
   - Dass Mitglieder der Website anderen Personen Zugriff gewähren.
   - Dass Nicht-Mitglieder der Website Zugriff auf die Website anfordern.
- Office 365-Aufbewahrungsbezeichnung für Ihre SharePoint Online-Websites oder -Teams als Standardmethode zum Definieren von Aufbewahrungsrichtlinien für die Dokumente der Website oder des Teams konfigurieren.
- Benutzer am Senden von Dateien außerhalb der Organisation hindern.
- Verschlüsseln Sie diehochgradig vertraulichen digitalen Objekte der Website oder des Teams.
- Fügen Sie den hochgradig vertraulichen digitalen Objekten Berechtigungen hinzu, sodass für das Öffnen der Ressourcen weiterhin gültige Anmeldeinformationen eines Benutzerkontos mit Berechtigung erforderlich sind, selbst wenn diese außerhalb der Website freigegeben werden.

In der folgenden Tabelle sind die Anforderungen dieser Lösung einem Feature von Microsoft 365 Enterprise zugeordnet.

|||
|:-------|:-----|
| **Anforderung** | **Microsoft 365 Enterprise-Feature** |
| Digitale Objekte speichern | SharePoint Online-Teamwebsites und Teams in Office 365 |
| Die Website sperren | Azure AD-Gruppen und SharePoint Online-Teamwebsiteberechtigungen |
| Digitale Objekte der Website kennzeichnen | Office 365-Aufbewahrungsbezeichnungen |
| Verhindern, dass Benutzer Dateien außerhalb der Organisation senden | Richtlinien zur Verhinderung von Datenverlust in Office 365 |
| Verschlüsseln aller digitalen Objekte der Website | Azure Information Protection-Unterbezeichnungen in Enterprise Mobility + Security (EMS) |
| Berechtigungen zu den digitalen Objekten der Website hinzufügen | Azure Information Protection-Unterbezeichnungen in EMS |
|||

Diese Lösung erfordert, dass Sie Folgendes bereits bereitgestellt haben:

- Die Phase [Identität](identity-infrastructure.md) und die Schritte 1 und 2 der Phase [Informationsschutz](infoprotect-infrastructure.md) der Foundation-Infrastruktur. 
- Für streng geregelte Daten in SharePoint Online-Teamwebsites [SharePoint Online](sharepoint-online-onedrive-workload.md).
- Für streng geregelte Daten in Microsoft Teams-Teams [Microsoft Teams](teams-workload.md).

Die folgenden Phasen führen Sie schrittweise durch den Entwurf, die Konfiguration und das Fördern der Einführung für SharePoint Online-Websites und Teams für streng geregelte Daten.

Um zu erfahren, wie die Contoso Corporation, ein fiktives, aber repräsentatives multinationales Unternehmen, eine SharePoint Online-Website für seine Forschungsteams entwickelt hat, sehen Sie sich die folgende [Beispielkonfiguration](contoso-sharepoint-online-site-for-highly-confidential-assets.md) an.

>[!Note]
>Ein Team für streng geregelte Daten setzt voraus, dass Sie zuerst eine SharePoint Online-Teamwebsite für streng geregelte Daten erstellen. Anschließend erstellen Sie ein neues Team, das die Office 365-Gruppe der SharePoint Online-Teamwebsite verwendet. In Phase 2, Schritt 4, finden Sie weitere Informationen.
>

## <a name="identity-and-device-access-prerequisites"></a>Voraussetzungen für den Identitäts- und Gerätezugriff

Um den Zugriff auf das Team oder die SharePoint Online-Website zu schützen, stellen Sie sicher, dass Sie [Identitäts- und Gerätezugriffsrichtlinien](identity-access-policies.md) und die [empfohlenen SharePoint Online-Zugriffsrichtlinien](sharepoint-file-access-policies.md) konfiguriert haben.

## <a name="phase-1-design"></a>Phase 1: Entwurf

Um eine SharePoint Online-Website oder ein Team für streng geregelte Daten zu erstellen, müssen Sie zuerst den Zweck angeben. Die Abteilung für Forschung und Entwicklung einer Fertigungsorganisation benötigt z. B. eine SharePoint Online-Website, um aktuelle Entwurfsspezifikationen für vorhandene Produkte zu speichern, sowie einen Ort für Zusammenarbeit im Hinblick auf neue Produkte. Nur Mitglieder der Abteilung für Forschung und Entwicklung sowie ausgewählte Führungskräfte können auf die Website zugreifen.

Dieser Zweck unterstützt die Ermittlung wichtiger Konfigurationselemente, z. B.:

- Die Gruppe von SharePoint Online-Berechtigungssätzen und SharePoint-Gruppen
- Die Gruppe von Zugriffsgruppen, die Azure AD-Sicherheitsgruppen und deren Mitglieder, die zu SharePoint-Gruppen hinzugefügt werden sollen
- Office 365-Aufbewahrungsbezeichnung, die der Website zugewiesen werden soll, und die Gruppe von DLP-Richtlinien für die Bezeichnung
- Die Einstellungen für eine Azure Information Protection-Unterbezeichnung, die Benutzer auf hochgradig vertrauliche digitale Objekte anwenden, die in der Website gespeichert sind

Nach der Ermittlung werden diese Einstellungen zur Konfiguration der Website in Phase 2 verwendet. 

### <a name="step-1-an-isolated-sharepoint-online-site"></a>Schritt 1: Eine isolierte SharePoint Online-Website

Die gesperrte Version einer SharePoint Online-Teamwebsite wird als eine isolierte Website bezeichnet. Im Gegensatz zu den Standardeinstellungen privater Teamwebsites sind isolierte Websites so konfiguriert, dass Folgendes verhindert wird:

- Zugriff auf Personen, die nicht Mitglieder der angegebenen Gruppen sind.
- Das Anfordern von Zugriff.
- Die nicht autorisierte Erteilung von Zugriff durch aktuelle Mitglieder angegebener Gruppen.
- Verwaltung der Website durch Mitglieder der Zugriffsgruppe.

Die Sicherheit von SharePoint Online-Teamwebsites, die streng geregelte Objekte enthalten, ändert sich nicht, es sei denn, dies wird vom SharePoint-Administrator für die Website ausgeführt.

Unter [Entwerfen einer isolierten SharePoint Online-Teamwebsite](https://docs.microsoft.com/office365/enterprise/design-an-isolated-sharepoint-online-team-site) finden Sie weitere Informationen zum Bestimmen der Gruppe von Berechtigungsstufen, SharePoint-Gruppen, Zugriffsgruppen und Gruppenmitgliedern.

### <a name="step-2-office-365-retention-labels-and-dlp-policies"></a>Schritt 2: Office 365-Aufbewahrungsbezeichnungen und DLP-Richtlinien

Wenn Office 365-Aufbewahrungsbezeichnungen auf eine SharePoint Online-Teamwebsite angewendet werden, bieten diese eine Standardmethode zum Klassifizieren aller digitalen Objekte, die auf der Website gespeichert sind.
 
Für SharePoint Online-Websites für streng geregelte Daten müssen Sie ermitteln, welche Office 365-Aufbewahrungsbezeichnung verwendet werden soll.

Die Entwurfsaspekte für Office 365-Bezeichnungen finden Sie unter [Office 365-Klassifizierung und -Bezeichnungen](https://docs.microsoft.com/office365/securitycompliance/secure-sharepoint-online-sites-and-files#office-365-retention-labels).

Um vertrauliche Informationen zu schützen und ihre versehentliche oder absichtliche Veröffentlichung zu verhindern, verwenden Sie die DLP-Richtlinien. Weitere Informationen finden Sie in dieser [Übersicht](https://docs.microsoft.com/office365/securitycompliance/data-loss-prevention-policies).

Für SharePoint Online-Websites für streng geregelte Daten müssen Sie eine DLP-Richtlinie für die Office 365-Aufbewahrungsbezeichnung konfigurieren, die der Website zugewiesen ist, um zu verhindern, dass Benutzer digitale Objekte für externe Benutzer freigeben. 

### <a name="step-3-your-azure-information-protection-sub-label"></a>Schritt 3: Azure Information Protection-Unterbezeichnung

Um Verschlüsselung und eine Reihe von Berechtigungen für Ihre hochgradig vertraulichen digitalen Objekte bereitzustellen, müssen die Benutzer eine Azure Information Protection-Bezeichnung mithilfe des Azure Information Protection-Clients anwenden. Um Azure Information Protection-Bezeichnungen für SharePoint Online-Websites für streng geregelte Daten zu verwenden, müssen Sie eine Azure Information Protection-Unterbezeichnung in einer begrenzten Richtlinie konfigurieren. 

Eine Unterbezeichnung ist unter einer vorhandenen Bezeichnung vorhanden. Sie können beispielsweise die Unterbezeichnung „Forschung und Entwicklung“ unter der Bezeichnung „Streng vertraulich“ erstellen. Eine begrenzte Richtlinie ist eine Richtlinie, die nur für eine Untergruppe von Benutzern gilt. Für SharePoint Online-Websites mit streng geregelten Daten ist der Bereich die Gruppe von Benutzern, die Mitglieder der Zugriffsgruppen für die Website sind.

Die Einstellungen der angewendeten Unterbezeichnung werden mit dem Objekt verschoben. Nur authentifizierte Benutzerkonten mit entsprechenden Berechtigungen können es öffnen, selbst wenn es heruntergeladen und außerhalb der Website freigegeben wird.

### <a name="design-results"></a>Entwurfsergebnisse

Sie haben Folgendes bestimmt:

- Die Gruppe von SharePoint-Gruppen und Berechtigungsstufen.
- Die Gruppe von Zugriffsgruppen und deren Mitglieder für jede Berechtigungsstufe
- Die entsprechende Office 365 Aufbewahrungsbezeichnung und die DLP-Richtlinie, die dieser Bezeichnung zugeordnet ist
- Die Einstellungen der Azure Information Protection-Unterbezeichnung, die Verschlüsselung und Berechtigungen umfassen

## <a name="phase-2-configure"></a>Phase 2: Konfigurieren

In dieser Phase implementieren Sie die in Phase 1 ermittelten Einstellungen, um eine SharePoint Online-Website für streng geregelte Daten zu erstellen.

### <a name="step-1-create-and-configure-an-isolated-sharepoint-online-team-site"></a>Schritt 1: Erstellen und Konfigurieren einer isolierten SharePoint Online-Teamwebsite

Verwenden Sie die Anweisungen unter [Bereitstellen einer isolierten SharePoint Online-Teamwebsite](https://docs.microsoft.com/office365/enterprise/deploy-an-isolated-sharepoint-online-team-site), um Folgendes zu tun:

- Erstellen Sie die Zugriffsgruppen für jeder auf der Website verwendete SharePoint-Berechtigungsstufe, und füllen Sie diese.
- Erstellen und Konfigurieren Sie die isolierte Teamwebsite.

### <a name="step-2-configure-the-site-for-an-office-365-retention-label-dlp-policy"></a>Schritt 2: Konfigurieren der Website für eine DLP-Richtlinie für eine Office 365-Aufbewahrungsbezeichnung

Verwenden Sie die Anweisungen unter [Schützen von SharePoint Online-Dateien mit Office 365-Bezeichnungen und Verhindern von Datenverlust](https://docs.microsoft.com/office365/enterprise/protect-sharepoint-online-files-with-office-365-labels-and-dlp), um Folgendes zu tun:

- Identifizieren oder erstellen Sie die Office 365-Aufbewahrungsbezeichnung, und wenden Sie diese auf Ihre isolierte SharePoint Online-Website an.
- Erstellen und Konfigurieren Sie die DLP-Richtlinie, die verhindert, dass Benutzer ein digitales Objekt auf Ihrer SharePoint Online-Website außerhalb der Organisation freigeben.

### <a name="step-3-create-an-azure-information-protection-sub-label-for-the-site"></a>Schritt 3: Erstellen einer Azure Information Protection-Unterbezeichnung für die Website

Verwenden Sie die Anweisungen unter [Schützen von SharePoint Online-Dateien mit Azure Information Protection ](https://docs.microsoft.com/office365/enterprise/protect-sharepoint-online-files-with-azure-information-protection), um Folgendes zu tun: 

- Erstellen und Konfigurieren einer Azure Information Protection-Unterbezeichnung in einer begrenzten Richtlinie.
- Bereitstellen des Azure Information Protection-Clients für Benutzercomputer.

### <a name="step-4-optional-create-a-team-for-the-highly-regulated-data"></a>Schritt 4 (optional): Erstellen eines Teams streng geregelte Daten

Wenn Sie ein Team für streng geregelte Daten möchten, erstellen Sie zuerst eine SharePoint Online-Website für streng geregelte Daten. Wenn Sie die ursprüngliche private SharePoint Online-Teamwebsite erstellt haben, geben Sie einen Office 365-Gruppennamen an.

Nachdem die SharePoint Online-Website für streng geregelte Daten vollständig konfiguriert ist, verwenden Sie die folgenden Schritte, um diese in ein Team für streng geregelte Daten zu konvertieren:

1. Melden Sie sich bei Office 365 an.
2. Klicken Sie auf der Registerkarte der **Microsoft Office-Startseite** auf **Teams**.
3. Klicken Sie auf der Registerkarte **Microsoft Teams** im Bereich **Team beitreten oder erstellen** auf **Team erstellen**.
4. Klicken Sie im Bereich **Team erstellen** auf **Erstellen eines Teams aus einer vorhandenen Office 365-Gruppe**.
5. Wählen Sie in der Liste der Office 365-Gruppen den Namen der Office 365-Gruppe aus, der der SharePoint Online-Website für streng geregelte Daten entspricht, und klicken Sie dann auf **Team auswählen**.

Auf der Registerkarte **Dateien** des neuen Teams werden die Inhalte des Ordners **Allgemein** im Bereich **Dokumente** der entsprechenden SharePoint Online-Website aufgeführt. Um die restlichen Ressourcen der SharePoint Online-Website für das Team anzuzeigen, klicken Sie auf das Auslassungszeichen (...), und klicken Sie dann auf **In SharePoint öffnen**.

### <a name="configuration-results"></a>Konfigurationsergebnisse

Sie haben Folgendes konfiguriert:

- Eine isolierte SharePoint Online-Website
- Eine Office 365-Aufbewahrungsbezeichnung, die der isolierten SharePoint Online-Website zugewiesen ist
- Eine DLP-Richtlinie für die Office 365-Aufbewahrungsbezeichnung
- Eine Azure Information Protection-Unterbezeichnung einer begrenzten Richtlinie, die Benutzer auf die hochgradig vertraulich digitalen Objekte anwenden können, die in der Website gespeichert sind, durch die das Objekt verschlüsselt und Berechtigungen erzwungen werden
- Bei Bedarf ein Team für stark geregelte Daten auf Grundlage der SharePoint Online-Website

## <a name="phase-3-drive-user-adoption"></a>Phase 3: Fördern der Benutzerakzeptanz

Eine SharePoint Online-Website oder ein Team für streng geregelte Daten kann Daten nur dann schützen, wenn sie bzw. es kontinuierlich zum Speichern und für den Zugriff vertraulicher digitaler Objekte verwendet werden. Dies ist die schwierigste Phase, da sie darauf beruht, dass Benutzer ihre Arbeitsweise ändern. 

Beispielsweise müssen Führungskräfte, die vertrauliche Dateien bisher auf USB-Laufwerken oder auf persönlichen cloudbasierten Speicherlösungen gespeichert hatten, diese nun ausschließlich in einer SharePoint Online-Website oder einem -Team für streng geregelte Daten speichern.

### <a name="step-1-train-your-users"></a>Schritt 1: Schulen der Benutzer

Schulen Sie nach Abschluss der Konfiguration die Gruppe von Benutzern, die Mitglied der Websitezugriffsgruppen sind:

- Vermitteln Sie Ihnen, wie wichtig es ist, die neue Website oder das neue Team zu verwenden, um wertvolle Ressourcen zu schützen, und was die Auswirkungen eines Lecks von streng geregelten Daten sind, z. B. rechtliche Konsequenzen, Bußgelder oder Verlust des Wettbewerbsvorteils.
- Erläutern Sie, wie auf die Website und deren Ressourcen zugegriffen wird.
- Erklären Sie, wie neue Dateien auf der Website erstellt und neue, lokal gespeicherte Dateien hochgeladen werden.
- Veranschaulichen Sie, wie durch die DLP-Richtlinie verhindert wird, dass Dateien extern freigegeben werden.
- Erläutern Sie die Verwendung des Azure Information Protection-Clients, um streng vertrauliche digitale Objekte mit der konfigurierten Unterbezeichnung zu kennzeichnen.
- Veranschaulichen Sie, wie die Azure Information Protection-Bezeichnung ein Objekt schützt, auch wenn es bei der Website oder bei dem Team zu einem Datenleck gekommen ist.

Diese Schulung sollte praktische Übungen umfassen, damit die Benutzer diese Vorgänge und deren Ergebnisse ausprobieren können.

### <a name="step-2-conduct-periodic-reviews-of-usage-and-files"></a>Schritt 2: Durchführen regelmäßiger Verwendungs- und Dateiprüfungen

In den Wochen nach der Schulung können der SharePoint-Administrator für die SharePoint Online-Website oder das Team Folgendes tun:

- Die Verwendung für die Website oder das Team analysieren und dies mit den Erwartungen vergleichen.
- Sicherstellen, dass streng vertrauliche Dateien korrekt mit der Azure Information Protection-Unterbezeichnung gekennzeichnet wurden.

Ihre Benutzer bei Bedarf erneut schulen.

### <a name="user-adoption-results"></a>Ergebnisse der Benutzerakzeptanz

Vertrauliche digitale Objekte werden ausschließlich auf SharePoint Online-Websites oder Teams für stark geregelte Daten gespeichert, und auf die hochgradig vertraulichen Objekte wurde die Azure Information Protection-Unterbezeichnung angewendet.

## <a name="see-also"></a>Siehe auch

[Bereitstellungshandbuch](deploy-microsoft-365-enterprise.md)

[Testumgebungsanleitungen](m365-enterprise-test-lab-guides.md)

[Sichern von SharePoint Online-Websites in einer Entwicklungs-/Testumgebung](https://docs.microsoft.com/office365/enterprise/secure-sharepoint-online-sites-in-a-dev-test-environment)
