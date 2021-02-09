---
title: Tools zur Bewertung der Bereitschaft
description: Erläutert die beiden Tools, die ausgeführten Prüfungen und die Bedeutung der Ergebnisse.
keywords: Microsoft Managed Desktop, Microsoft 365, Dienst, Dokumentation
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 1a00f7d5fb37cc9eea3f9454d473703084960864
ms.sourcegitcommit: d739f48b991793c08522a3d5323beba27f0111b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/08/2021
ms.locfileid: "50142933"
---
# <a name="readiness-assessment-tools"></a>Tools zur Bewertung der Bereitschaft

Für eine möglichst reibungslose Benutzererfahrung bei der Registrierung bei Microsoft Managed Desktop gibt es Einstellungen und andere Parameter, die Sie im Voraus festlegen müssen, sowie bestimmte Geräte- und Netzwerkanforderungen, die erfüllt werden müssen. Ein Tool, auf das über das Microsoft Managed Desktop Admin Portal zugegriffen wird, überprüft verwaltungsbezogene Einstellungen. Ein anderes Tool, das heruntergeladen werden kann, überprüft die individuellen Geräteanforderungen und Netzwerkeinstellungen. Sie können diese Tools verwenden, um diese Einstellungen zu überprüfen und detaillierte Schritte zum Beheben nicht richtiger Informationen zu erhalten.

## <a name="downloadable-readiness-assessment-checker-for-devices-and-network"></a>Herunterladbare Überprüfung der Bereitschaftsbewertung für Geräte und Netzwerke

Weitere Informationen zur Verwendung des herunterladbaren Überprüfungsprüffelds für die Bereitschaftsbewertung finden Sie unter "Überprüfung der Herunterladbaren [Bereitschaftsbewertung".](readiness-assessment-downloadable.md)

## <a name="online-readiness-assessment-tool-for-management-settings"></a>Tool zur Bewertung der Onlinebereitschaft für Verwaltungseinstellungen

Das Onlinetool überprüft einstellungen in Microsoft Endpoint Manager (insbesondere Microsoft Intune), Azure Active Directory (Azure AD) und Microsoft 365, um sicherzustellen, dass sie mit Microsoft Managed Desktop funktionieren. Microsoft Managed Desktop bewahrt die daten, die diesen Überprüfungen zugeordnet sind, 12 Monate nach dem letzten Ausführen einer Überprüfung in Ihrer Azure AD-Organisation (Mandant) auf. Nach 12 Monaten behalten wir sie in nicht identifizierter Form bei. Sie können die gesammelten Daten löschen.

Jeder Benutzer mit mindestens der Rolle "Globaler Leser" oder "Intune-Administrator" kann dieses Tool ausführen, aber zwei der Prüfungen[(](readiness-assessment-fix.md#conditional-access-policies) Richtlinien für bedingten Zugriff und mehrstufige Authentifizierung [erfordern](readiness-assessment-fix.md#multifactor-authentication) zusätzliche Berechtigungen.
 
Das Bewertungstool überprüft diese Elemente:

## <a name="microsoft-intune-settings"></a>Microsoft Intune-Einstellungen

|Scheck  |Beschreibung  |
|---------|---------|
|Autopilot-Bereitstellungsprofil     | Überprüft, ob die Zuweisung des Autopilot-Bereitstellungsprofils nicht  für alle Geräte gilt (das Profil sollte keinem Microsoft Managed Desktop zugewiesen werden.)       |
|Zertifikatconnectors     | Überprüft den Status von Zertifikatconnectors, um sicherzustellen, dass sie aktiv sind.   |
|Bedingter Zugriff     | Überprüft, ob Richtlinien für bedingten Zugriff nicht allen  Benutzern zugewiesen sind (Richtlinien für bedingten Zugriff sollten nicht Microsoft Managed Desktop-Dienstkonten zugewiesen werden.)    |
|Gerätekonformitätsrichtlinien     | Überprüft, ob Intune-Compliance-Richtlinien nicht allen  Benutzern zugewiesen sind (die Richtlinien sollten keinem Microsoft Managed Desktop-Gerät zugewiesen werden.)    |
|Gerätekonfigurationsprofile     | Überprüft, ob Konfigurationsprofile nicht allen Benutzern oder allen  Geräten zugewiesen sind (Konfigurationsprofile sollten keinem Microsoft Managed Desktop zugewiesen werden.)     |
|Gerätetypeinschränkungen     | Überprüft, ob Windows 10-Geräte in Ihrer Organisation in Intune registriert werden dürfen.        |
|Seite "Registrierungsstatus"     | Überprüft, ob die Seite "Registrierungsstatus" nicht aktiviert ist      |
|Registrierung in Intune     | Überprüft, ob Windows 10-Geräte in Ihrer Azure AD-Organisation automatisch in Intune registriert sind         |
|Microsoft Store für Unternehmen     | Überprüft, ob der Microsoft Store für Unternehmen aktiviert und mit Intune synchronisiert wurde        |
|Mehrstufige Authentifizierung | Überprüft, ob die mehrstufige Authentifizierung nicht auf Microsoft Managed Desktop -Dienstkonten angewendet wird.
|PowerShell-Skripts     | Überprüft, ob Windows PowerShell Skripts *nicht* auf eine Weise zugewiesen werden, die auf Microsoft Managed Desktop-Geräte zu zielen wäre.    |
|Region     | Überprüft, ob Ihre Region von Microsoft Managed Desktop unterstützt wird        |
|Sicherheitsgrundwerte     | Überprüft, ob das Sicherheitsbaselineprofil nicht für alle Benutzer  oder alle Geräte gilt (Sicherheitsgrundlinienrichtlinien sollten nicht auf Microsoft Managed Desktop-Geräte ausgerichtet sein.)       |
|Windows-Apps     | Überprüfen, welche Apps Sie Microsoft Managed Desktop-Geräten zuweisen möchten      |
|Windows Hello for Business     | Überprüft, ob Windows Hello for Business aktiviert ist        |
|Windows 10-Updatering     | Überprüft, ob die Richtlinie "Windows 10-Updatering" von Intune nicht für  alle Benutzer oder alle Geräte gilt (die Richtlinie sollte nicht für Microsoft Managed Desktop-Geräte verwendet werden.)     |


## <a name="azure-active-directory-settings"></a>Azure Active Directory-Einstellungen

|Scheck  |Beschreibung  |
|---------|---------|
|"Ad hoc"-Abonnements für Enterprise State Roaming     | Empfiehlt, eine Einstellung zu überprüfen, die (bei Festlegung auf "false") möglicherweise verhindert, dass Enterprise State Roaming ordnungsgemäß funktioniert.  |
|Enterprise State Roaming     | Empfiehlt, zu überprüfen, ob Enterprise State Roaming aktiviert ist.       |
|Lizenzen     | Überprüft, ob Sie die erforderlichen Lizenzen [erhalten haben](prerequisites.md#more-about-licenses)         |
|Mehrstufige Authentifizierung     | Überprüft, ob die mehrstufige Authentifizierung nicht auf alle Benutzer angewendet wird (die mehrstufige Authentifizierung darf nicht versehentlich auf Microsoft Managed Desktop-Dienstkonten angewendet werden.)|
|Namen von Sicherheitskontos   | Überprüft, ob keine Benutzernamen mit denen in Konflikt stehen, die Microsoft Managed Desktop für die eigene Verwendung reserviert.        |
|Sicherheitsadministratorrollen     | Überprüft, ob Benutzern mit Rollen "Sicherheitsleseprogramm", "Sicherheitsoperator" oder "Globaler Leser" diese Rollen in Microsoft Defender for Endpoint zugewiesen wurden.         |
|Sicherheitsstandards | Überprüft, ob in Ihrer Azure AD-Organisation Sicherheitseinstellungen in Azure Active Directory aktiviert sind. |
|Zurücksetzen von Kennwörtern durch den Benutzer     | Überprüft, ob die Self-Service-Kennwortzurücksetzung aktiviert ist        |
|Standardbenutzerrolle     | Überprüft, ob Benutzer Standardbenutzer sind und nicht über lokale Administratorrechte verfügen         |


## <a name="microsoft-365-apps-for-enterprise-settings"></a>Einstellungen für Microsoft 365 Apps for Enterprise

|Scheck  |Beschreibung  |
|---------|---------|
|OneDrive for Business     | Überprüft, ob OneDrive for Business nicht unterstützte Einstellungen verwendet.        |


Für jede Prüfung wird das Tool eines von vier möglichen Ergebnissen melden:


|Ergebnis  |Bedeutung  |
|---------|---------|
|Bereit     | Es ist keine Aktion erforderlich, bevor Sie die Registrierung abschließen.        |
|Empfehlung    | Führen Sie die Schritte im Tool aus, um die beste Erfahrung mit der Registrierung und für Benutzer zu bieten. Sie *können* die Registrierung abschließen, aber Sie müssen diese Probleme beheben, bevor Sie Ihr erstes Gerät bereitstellen.        |
|Nicht bereit | *Die Registrierung wird fehlschlagen,* wenn Sie diese Probleme nicht beheben. Führen Sie die Schritte im Tool aus, um sie zu beheben.        |
|Fehler | Die Azure Active Director (AD)-Rolle, die Sie verwenden, verfügt nicht über ausreichende Berechtigungen, um diese Überprüfung ausführen zu können. |

## <a name="after-enrollment"></a>Nach der Registrierung

Nachdem Sie die Registrierung bei Microsoft Managed Desktop abgeschlossen haben, denken Sie daran, zurück zu gehen und bestimmte Intune- und Azure AD-Einstellungen anzupassen. Weitere Informationen finden Sie unter ["Einstellungen nach der Registrierung anpassen".](../get-started/conditional-access.md)
