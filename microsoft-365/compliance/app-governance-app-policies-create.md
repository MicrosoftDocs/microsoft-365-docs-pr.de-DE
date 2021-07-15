---
title: Erstellen von App-Richtlinien
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection: m365-security-compliance
localization_priority: Priority
search.appverid:
- MOE150
- MET150
description: Erstellen von App-Richtlinien.
ms.openlocfilehash: 66d8dda7c9cd768d6971e2b58dca4c9c5437e5bb
ms.sourcegitcommit: 2fd60871975d61e60d4827b36cd689021fd2a4c8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/15/2021
ms.locfileid: "53438060"
---
# <a name="create-app-policies"></a>Erstellen von App-Richtlinien

>*[Microsoft 365-Lizenzierungsleitfaden für Sicherheit und Compliance](https://aka.ms/ComplianceSD).*

Neben einer Reihe integrierter Funktionen zur Erkennung von anomalem App-Verhalten und zur Generierung von Warnungen sind App-Richtlinien in Microsoft-App-Governance eine Möglichkeit für Sie:

- Geben Sie Bedingungen an, unter denen Sie von der App-Governance über das App-Verhalten informiert werden, um eine automatische oder manuelle Wartung vorzunehmen.
- Implementieren Sie die App-Compliancerichtlinien für Ihre Organisation.

Sie können App-Richtlinien aus bereitgestellten Vorlagen erstellen, die angepasst werden können, oder Sie können eine eigene benutzerdefinierte App-Richtlinie erstellen.

Um eine neue App-Richtlinie zu erstellen, wechseln Sie zur Seite **Microsoft 365 Compliance Center > App-Governance > Übersichtsseite > Richtlinien**:

- Um eine neue App-Richtlinie mit Vorlagen für die App-Nutzung zu erstellen, wählen Sie **Richtlinie erstellen** unter **App-Nutzungsrichtlinie erstellen** aus.
- Um eine neue App-Richtlinie mit Vorlagen für die App-Berechtigungen zu erstellen, wählen Sie **Richtlinie erstellen** unter **Berechtigungsrichtlinie erstellen** aus.
- Um eine neue App-Richtlinie für die App-Zertifizierung oder eine benutzerdefinierte Richtlinie zu erstellen, wählen Sie **Neue erstellen** aus.

## <a name="app-policy-templates"></a>App-Richtlinienvorlagen

Um eine neue App-Richtlinie basierend auf einer App-Richtlinienvorlage zu erstellen, wählen Sie auf der Seite **App-Richtlinienvorlage auswählen** eine App-Vorlagenkategorie, anschließend den Namen der Vorlage und dann **Weiter** aus.

App-Governance verfügt über drei Kategorien von App-Richtlinienvorlagen.

### <a name="app-users-and-data-access"></a>App-Benutzer- und -Datenzugriff

App-Governance stellt diese Vorlagen bereit, um Warnungen für die App-Nutzung zu generieren.

| Vorlagenname | Beschreibung |
|:-------|:-----|
| Neue App mit einer großen Anzahl von Datenzugriffen | Hebt alle kürzlich registrierten Apps mit einer großen Anzahl von Datenzugriffen hervor, um sicherzustellen, dass es sich dabei um erwartete Datenmuster handelt. <br><br> Standardmäßig kennzeichnet diese Richtlinie alle Apps, die in den letzten 7 Tagen registriert wurden und in diesem Zeitraum auf über mehr als 1 GB Daten zugreifen konnten. Diese Richtlinie kann mit weiteren Bedingungen und Aktionen angepasst werden. |
|||

### <a name="app-permissions"></a>App-Berechtigungen

App-Governance stellt diese Vorlagen bereit, um Warnungen für App-Berechtigungen zu generieren.

| Vorlagenname | Beschreibung |
|:-------|:-----|
| Überprivilegierte Apps | Hebt alle Apps hervor, denen mehr Berechtigungen erteilt wurden, als verwendet werden, um zu ermitteln, wo Berechtigungen reduziert werden können. <br><br> Standardmäßig kennzeichnet diese Richtlinie alle Apps, die als „Überprivilegiert“ gekennzeichnet sind, wenn sie 90 Tage lang nicht verwendet werden. Dieser Zeitraumfilter kann mit weiteren Bedingungen und Aktionen angepasst werden. |
| Neue App mit hoher Berechtigung | Hebt alle neuen Apps mit hoher Berechtigung hervor, um Apps mit potenziell großem Fußabdruck zu erkennen, die möglicherweise weitere Untersuchungen erfordern. <br><br> Standardmäßig werden durch diese Richtlinie alle Apps gekennzeichnet, die in den letzten 7 Tagen registriert wurden und über weitreichende Berechtigungen verfügen. |
|||

### <a name="app-certification"></a>App-Zertifizierung

App-Governance stellt diese Vorlagen bereit, um Warnungen für App-Zertifizierungen zu generieren.

| Vorlagenname | Beschreibung |
|:-------|:-----|
| Neue, nicht zertifizierte App | Hebt neue Apps hervor, die nicht den App-Zertifizierungsprozess durchlaufen haben, um sicherzustellen, dass sie im Mandanten erwartet werden. <br><br> Standardmäßig werden durch diese Richtlinie alle Apps gekennzeichnet, die in den letzten sieben Tagen registriert wurden und nicht zertifiziert sind. |
|||

## <a name="custom-app-policies"></a>Benutzerdefinierte App-Richtlinien

Verwenden Sie eine benutzerdefinierte App-Richtlinie für Aktionen, die nicht bereits von einer der integrierten Vorlagen ausgeführt werden.

Um eine neue benutzerdefinierte App-Richtlinie zu erstellen, wählen Sie zuerst auf der Seite **Richtlinien** die Option **Neue erstellen** aus. Wählen Sie auf der Seite **App-Richtlinienvorlage auswählen** die Kategorie **Benutzerdefiniert**, die Vorlage **Benutzerdefinierte Richtlinie** und dann **Weiter** aus.

Konfigurieren Sie auf der Seite **Name und Beschreibung** Folgendes:

- Richtlinienname

- Richtlinienbeschreibung

- Wählen Sie den Richtlinienschweregrad aus, der den Schweregrad der von dieser Richtlinie generierten Warnungen festlegt.

  - High
  - Medium
  - Niedrig

Wählen Sie auf der Seite **Richtlinieneinstellungen und -bedingungen auswählen** für **Auswählen, für welche Apps diese Richtlinie gilt** Folgendes aus:

- Alle Apps
- Bestimmte Apps auswählen

  In einem Bereich können Sie eine oder mehrere Apps auswählen.
  Wählen Sie **Hinzufügen** aus.

Wählen Sie **Weiter** aus.

Wählen Sie auf der Seite **Richtlinieneinstellungen und -bedingungen auswählen** die Option **Neue Bedingungen für Richtlinie festlegen** und dann **Weiter** aus.

Im Bereich **Regel erstellen** können Sie Bedingungen für eine neue Regel auswählen. Wählen Sie **Bedingung hinzufügen** aus. Wählen Sie dann Bedingungen aus der Liste aus, und geben Sie den Wert der Bedingung an. Sie können mehrere Bedingungen hinzufügen.

Im Folgenden finden Sie die verfügbaren Bedingungen für eine benutzerdefinierte App-Richtlinie.

|Bedingung | Akzeptierte Bedingungswerte | Weitere Informationen |
|:-------|:-----|:-------|
| App-Registrierungsalter | Innerhalb der letzten x Tage |  |
| App-Zertifizierung | Grundlegende Compliance, MCAS-Compliance oder N/V | [Microsoft 365-Zertifizierung](https://docs.microsoft.com/microsoft-365-app-certification/docs/enterprise-app-certification-guide) |
| Herausgeberüberprüfung | Ja oder Nein | [Herausgeberüberprüfung](https://docs.microsoft.com/azure/active-directory/develop/publisher-verification-overview) |
| Anwendungsberechtigung | Wählen Sie mindestens eine API-Berechtigung aus der Liste aus. | [Microsoft Graph-Berechtigungsreferenz](https://docs.microsoft.com/graph/permissions-reference) |
| Delegierte Berechtigung | Wählen Sie mindestens eine API-Berechtigung aus der Liste aus. | [Microsoft Graph-Berechtigungsreferenz](https://docs.microsoft.com/graph/permissions-reference) |
| Hohe Berechtigung | Ja oder Nein | Dies ist eine interne Bezeichnung, die auf der gleichen Logik basiert, die von MCAS verwendet wird. |
| Überprivilegierte App | Ja oder Nein | Apps, denen mehr Berechtigungen gewährt wurden, als von ihnen verwendet werden. |
| Zugriff auf App-Daten | Mehr als x GB Datenzugriff pro Stunde |  |
| Trend des Zugriffs auf App-Daten | x % Erhöhung der Datennutzung in den letzten 7 Tagen |  |
| App-API-Zugriff | Mehr als x API-Aufrufe pro Stunde |  |
| Trend des App-API-Zugriffs | x % Erhöhung der API-Aufrufe in den letzten 7 Tagen     |  |
| Benutzer, die zugestimmt haben | (Größer als oder kleiner als) x Benutzer, die zugestimmt haben |  |
| Prioritärer Benutzer hat zugestimmt | Ja oder Nein | Benutzer mit einem [Prioritätskonto](https://docs.microsoft.com/microsoft-365/admin/setup/priority-accounts). |
| App zugestimmt von | Benutzer aus Liste auswählen |  |
| Rolle des zustimmenden Benutzers | Wählen Sie einen oder mehrere aus: Teams-Administrator, Verzeichnisleseberechtigter, Sicherheitsleseberechtigter, Complianceadministrator, Sicherheitsadministrator, Helpdeskadministrator, SharePoint-Administrator, Exchange-Administrator, Globaler Leseberechtigter, Globaler Administrator, Compliancedatenadministrator, Benutzeradministrator, Dienstsupportadministrator | Mehrfachauswahl zulässig. <br><br> Jede Azure AD-Rolle mit zugewiesenem Mitglied sollte in dieser Liste verfügbar gemacht werden. |
| Zugriff auf Workload | OneDrive und/oder SharePoint und/oder Exchange | Mehrfachauswahl zulässig. |
| Fehlerrate | Die Fehlerrate ist in den letzten 7 Tagen größer als x %, wobei x ein vom Administrator definierter Wert ist. |  |
||||

<!--
NOTE TO WRITER: Replace X in the above table with correct values.
-->

Alle angegebenen Bedingungen müssen erfüllt sein, damit diese App-Richtlinie angewendet wird.

Wenn Sie alle gewünschten Bedingungen angegeben haben, wählen Sie **Speichern** und dann **Weiter** aus.

Wählen Sie auf der Seite **Richtlinienaktionen definieren** die Option **App deaktivieren** aus, wenn die App-Governance die App deaktivieren soll, sobald eine Warnung basierend auf dieser Richtlinie generiert wird, und wählen Sie dann **Weiter** aus.

Wählen Sie auf der Seite **Richtlinienstatus definieren** eine der folgenden Optionen aus:

- **Überwachungsmodus**: Richtlinien werden ausgewertet, aber konfigurierte Aktionen werden nicht ausgeführt. Richtlinien für den Überwachungsmodus werden in der Liste der Richtlinien mit dem Status **Überwachung** angezeigt.
- **Aktiv**: Richtlinien werden ausgewertet, und die konfigurierten Aktionen werden ausgeführt.
- **Inaktiv**: Richtlinien werden nicht ausgewertet, und die konfigurierten Aktionen werden nicht ausgeführt.

<!--
## Configure a user-based policy

## Create an app metadata-based policy

Publish metadata-based policies

## Configure access permissions
-->

## <a name="test-and-monitor-your-new-app-policy"></a>Testen und Überwachen Ihrer neuen App-Richtlinie

Nachdem Ihre App-Richtlinie erstellt wurde, sollten Sie sie auf der Seite **Richtlinien** überwachen, um sicherzustellen, dass während des Tests eine erwartete Anzahl aktiver Warnungen und gesamter Warnungen registriert werden. 

![Übersichtsseite der MAPG-Richtlinien im Microsoft 365 Compliance Center mit einer hervorgehobenen Richtlinie](..\media\manage-app-protection-governance\mapg-cc-policies-policy.png)

Wenn die Anzahl der Warnungen unerwartet niedrig ist, bearbeiten Sie die Einstellungen der App-Richtlinie, um sicherzustellen, dass Sie sie ordnungsgemäß konfiguriert haben, bevor Sie ihren Status festlegen.

Im Folgenden finden Sie ein Beispiel für einen Prozess zum Erstellen, Testen und anschließenden Aktivieren der Richtlinie:

1. Erstellen Sie die neue Richtlinie mit Schweregrad, Apps, Bedingungen und Aktionen, legen Sie Ausgangswerte fest, und setzen Sie den Status auf **Überwachungsmodus**.
2. Überprüfen Sie auf erwartetes Verhalten, z. B. generierte Warnungen.
3. Wenn das Verhalten nicht den Erwartungen entspricht, bearbeiten Sie die Richtlinien-Apps, Bedingungen und Aktionseinstellungen nach Bedarf, und kehren Sie zu Schritt 2 zurück.
4. Wenn das Verhalten den Erwartungen entspricht, bearbeiten Sie die Richtlinie, und ändern Sie ihren Status in **Aktiv**.

![Der Workflow zum Erstellen von App-Richtlinien](../media/manage-app-protection-governance/mapg-create-new-policy-process.png)

## <a name="next-step"></a>Nächster Schritt

[Verwalten Sie Ihre App-Richtlinien.](app-governance-app-policies-manage.md)
