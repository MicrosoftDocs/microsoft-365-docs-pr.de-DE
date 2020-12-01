---
title: Bereitschafts Bewertungstool
description: Erläutert die Prüfungen, die vom Tool ausgeführt werden, und die Bedeutung der Ergebnisse.
keywords: Microsoft Managed Desktop, Microsoft 365, Dienst, Dokumentation
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: e2d1c68c3fe963c957e4c3e18fce441b92c96bf1
ms.sourcegitcommit: d3ca8021f7da00a474ac14aac5f1358204a848f2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/01/2020
ms.locfileid: "49519821"
---
# <a name="readiness-assessment-tool"></a>Bereitschafts Bewertungstool

Für eine möglichst reibungslose Benutzerfreundlichkeit bei der Registrierung in Microsoft Managed Desktop gibt es eine Reihe von Einstellungen und anderen Parametern, die Sie vor der Zeit festlegen müssen. Sie können dieses Tool verwenden, um diese Einstellungen zu überprüfen und detaillierte Schritte zur Behebung der nicht richtigen Informationen zu erhalten.

Das Tool überprüft die Einstellungen in Microsoft Endpoint Manager (insbesondere Microsoft InTune), Azure Active Directory (Azure AD) und Microsoft 365, um sicherzustellen, dass Sie mit dem verwalteten Desktop von Microsoft arbeiten können. Microsoft Managed Desktop behält die Daten, die diesen Prüfungen zugeordnet sind, 12 Monate nach dem letzten Ausführen einer Überprüfung in ihrer Azure AD Organisation (Mandant). Nach 12 Monaten behalten wir es in der nicht identifizierten Form bei.  Sie können auswählen, dass die erfassten Daten gelöscht werden sollen.

Jeder Benutzer mit mindestens der InTune-Administrator Rolle kann dieses Tool ausführen, aber zwei der Prüfungen ([Richtlinien für bedingten Zugriff](readiness-assessment-fix.md#conditional-access-policies) und mehrstufige [Authentifizierung](readiness-assessment-fix.md#multi-factor-authentication) erfordern zusätzliche Berechtigungen).
 
Das Assessment-Tool überprüft diese Elemente:

## <a name="microsoft-intune-settings"></a>Microsoft InTune-Einstellungen

|Prüfen  |Beschreibung  |
|---------|---------|
|Autopilot-Bereitstellungsprofil     | Überprüft, ob die Zuweisung des Autopilot-Bereitstellungs Profils für alle Geräte nicht gilt (das Profil *sollte keinem Microsoft* Managed Desktop-Gerät zugewiesen werden.)       |
|Zertifikat-Konnektoren     | Überprüft den Status von Zertifikat-Konnektoren, um sicherzustellen, dass Sie aktiv sind   |
|Bedingter Zugriff     | Überprüft, ob Richtlinien für bedingten Zugriff nicht allen Benutzern zugewiesen sind (Richtlinien für den bedingten Zugriff sollten *nicht* Microsoft Managed Desktop-Dienstkonten zugewiesen werden).    |
|Geräte Konformitätsrichtlinien     | Überprüft, ob InTune-Konformitätsrichtlinien nicht allen Benutzern zugewiesen sind (die Richt *Linien sollten keinem* Microsoft Managed Desktop Devices zugewiesen werden.)    |
|Geräte Konfigurationsprofile     | Überprüft, ob Konfigurationsprofile nicht allen Benutzern oder allen Geräten zugewiesen sind (Konfigurations *Profile sollten keinem* Microsoft Managed Desktop-Gerät zugewiesen werden.)     |
|Einschränkungen für Gerätetypen     | Überprüft, ob Windows 10-Geräte in Ihrer Organisation in InTune registriert werden dürfen.        |
|Seite "Registrierungs Status"     | Bestätigt, dass die Seite Registrierungs Status nicht aktiviert ist      |
|InTune-Registrierung     | Überprüft, ob Windows 10-Geräte in ihrer Azure AD Organisation automatisch in InTune registriert sind.         |
|Microsoft Store für Unternehmen     | Bestätigt, dass Microsoft Store for Business mit InTune aktiviert und synchronisiert ist.        |
|Mehrstufige Authentifizierung | Überprüft, ob die mehrstufige Authentifizierung nicht auf von Microsoft verwaltete Desktop Dienstkonten angewendet wird.
|PowerShell-Skripts     | Überprüft, ob Windows PowerShell Skripts *nicht* auf eine Weise zugewiesen werden, die auf Microsoft Managed Desktop-Geräte ausgerichtet ist.    |
|Region     | Überprüft, ob Ihre Region von Microsoft Managed Desktop unterstützt wird.        |
|Sicherheitsbasislinien     | Überprüft, ob das Sicherheitsbasis Profil nicht auf alle Benutzer oder alle Geräte ausgerichtet ist (Sicherheitsbasislinien sollten *nicht* auf Microsoft-verwaltete Desktop Geräte abzielen.)       |
|Windows-apps     | Überprüfen der apps, die Sie Microsoft Managed Desktop-Geräten zuweisen möchten      |
|Windows Hello for Business     | Überprüft, ob Windows Hello for Business aktiviert ist.        |
|Windows 10-Update Ring     | Überprüft, ob die Richtlinie "Windows 10 Update Ring" von InTune nicht auf alle Benutzer oder alle Geräte ausgerichtet ist (die Richtlinie sollte *nicht* auf Microsoft verwaltete Desktop Geräte abzielen.)     |


## <a name="azure-active-directory-settings"></a>Azure Active Directory-Einstellungen

|Prüfen  |Beschreibung  |
|---------|---------|
|Ad-hoc-Abonnements für das Enterprise-Status-Roaming     | Gibt an, wie eine Einstellung überprüft wird, die (wenn Sie auf "false" festgelegt ist) möglicherweise verhindert, dass das Roaming von Unternehmensstatus ordnungsgemäß funktioniert.  |
|Enterprise State Roaming     | Gibt an, wie Sie überprüfen, ob das Enterprise-Status-Roaming aktiviert ist.       |
|Lizenzen     | Überprüft, ob Sie die erforderlichen [Lizenzen](prerequisites.md#more-about-licenses) erhalten haben.         |
|Mehrstufige Authentifizierung     | Überprüft, ob die mehrstufige Authentifizierung nicht auf alle Benutzer angewendet wird (mehrstufige Authentifizierung darf nicht versehentlich auf von Microsoft verwaltete Desktop Dienstkonten angewendet werden.)|
|Namen von Sicherheitskonten   | Überprüft, ob keine Benutzernamen mit denen in Konflikt stehen, die von Microsoft verwaltete Desktop zur eigenen Verwendung reserviert werden.        |
|Sicherheitsadministrator Rollen     | Bestätigt, dass Benutzern mit dem Sicherheits Leser, dem Sicherheits Operator oder den globalen Leser Rollen diese Rollen in Microsoft Defender für Endpoint zugewiesen wurden.         |
|Sicherheitsstandards | Überprüft, ob in ihrer Azure AD Organisation Sicherheitsstandards in Azure aktiviert sind Active Directory |
|Zurücksetzen von Kennwörtern durch den Benutzer     | Bestätigt, dass Self-Service Password Reset aktiviert ist        |
|Standard Benutzerrolle     | Überprüft, ob Benutzer Standardbenutzer sind und nicht über lokale Administratorrechte verfügen.         |


## <a name="microsoft-365-apps-for-enterprise-settings"></a>Microsoft 365-Apps für Enterprise-Einstellungen

|Prüfen  |Beschreibung  |
|---------|---------|
|OneDrive for Business     | Überprüft, ob OneDrive für Unternehmen nicht unterstützte Einstellungen verwendet.        |


Für jede Überprüfung meldet das Tool eine von vier möglichen Ergebnissen:


|Ergebnis  |Bedeutung  |
|---------|---------|
|Bereit     | Es ist keine Aktion erforderlich, bevor Sie die Registrierung abschließen.        |
|Empfehlung    | Führen Sie die Schritte im Tool aus, um die besten Erfahrungen mit der Registrierung und für Benutzer zu erzielen. Sie *können* die Registrierung abschließen, aber Sie müssen diese Probleme beheben, bevor Sie das erste Gerät bereitstellen.        |
|Nicht bereit | Die *Registrierung schlägt fehl* , wenn Sie diese Probleme nicht beheben. Befolgen Sie die Schritte im Tool, um Sie zu beheben.        |
|Error | Die von Ihnen verwendete Azure Active Director (AD)-Rolle verfügt nicht über ausreichende Berechtigungen zum Ausführen dieser Überprüfung. |
