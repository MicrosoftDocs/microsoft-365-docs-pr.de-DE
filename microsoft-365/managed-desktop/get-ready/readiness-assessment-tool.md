---
title: Tools für die Bereitschaftsbewertung
description: Erläutert die beiden Tools, die ausgeführten Prüfungen und die Bedeutung der Ergebnisse.
keywords: Microsoft Managed Desktop, Microsoft 365, Dienst, Dokumentation
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
audience: Admin
ms.openlocfilehash: caf9274284548a179e088131930ae832c098b521
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/02/2021
ms.locfileid: "51579398"
---
# <a name="readiness-assessment-tools"></a>Tools für die Bereitschaftsbewertung

Für eine möglichst reibungslose Benutzererfahrung bei der Registrierung bei Microsoft Managed Desktop gibt es Einstellungen und andere Parameter, die Sie im Voraus festlegen müssen, sowie bestimmte Geräte- und Netzwerkanforderungen, die erfüllt werden müssen. Mit einem Tool, auf das über das Microsoft Managed Desktop Admin-Portal zugegriffen wird, werden verwaltungsbezogene Einstellungen überprüft. Ein weiteres Tool, das heruntergeladen werden kann, überprüft die individuellen Geräteanforderungen und Netzwerkeinstellungen. Sie können diese Tools verwenden, um diese Einstellungen zu überprüfen und detaillierte Schritte zum Beheben nicht richtiger Tools zu erhalten.

## <a name="downloadable-readiness-assessment-checker-for-devices-and-network"></a>Überprüfung der Herunterladbaren Bereitschaftsbewertung für Geräte und Netzwerke

Weitere Informationen zur Verwendung der Überprüfung der herunterladbaren Bereitschaftsbewertung finden Sie unter [Downloadable Readiness Assessment checker](readiness-assessment-downloadable.md).

## <a name="online-readiness-assessment-tool-for-management-settings"></a>Tool für die Onlinebereitschaftsbewertung für Verwaltungseinstellungen

Das [Onlinetool](https://aka.ms/mmdart) überprüft die Einstellungen in Microsoft Endpoint Manager (insbesondere Microsoft Intune), Azure Active Directory (Azure AD) und Microsoft 365, um sicherzustellen, dass sie mit Microsoft Managed Desktop funktionieren. Microsoft Managed Desktop behält die diesen Prüfungen zugeordneten Daten 12 Monate lang bei, nachdem Sie das letzte Mal eine Überprüfung in Ihrer Azure AD-Organisation (Mandant) durchgeführt haben. Nach 12 Monaten behalten wir sie in nicht identifizierter Form bei. Sie können die von uns gesammelten Daten löschen.

Jeder Benutzer mit mindestens der Rolle "Globaler Leser" oder "Intune-Administrator" kann dieses Tool ausführen, aber zwei der Prüfungen[(](readiness-assessment-fix.md#conditional-access-policies) Richtlinien für bedingten Zugriff und [mehrstufige](readiness-assessment-fix.md#multifactor-authentication) Authentifizierung erfordern zusätzliche Berechtigungen.
 
Das Bewertungstool überprüft die folgenden Elemente:

## <a name="microsoft-intune-settings"></a>Microsoft Intune-Einstellungen

|Scheck  |Beschreibung  |
|---------|---------|
|Autopilot-Bereitstellungsprofil     | Überprüft, ob die Zuweisung des Autopilot-Bereitstellungsprofils nicht  für alle Geräte gilt (Das Profil sollte keinem Microsoft Managed Desktop-Gerät zugewiesen werden.)       |
|Zertifikatconnectors     | Überprüft den Status von Zertifikatconnectors, um sicherzustellen, dass sie aktiv sind.   |
|Bedingter Zugriff     | Überprüft, ob Richtlinien für bedingten Zugriff nicht allen  Benutzern zugewiesen sind (Richtlinien für bedingten Zugriff sollten nicht Microsoft Managed Desktop-Dienstkonten zugewiesen werden.)    |
|Richtlinien zur Gerätekonformität     | Überprüft, ob Intune-Compliancerichtlinien nicht allen Benutzern  zugewiesen sind (Die Richtlinien sollten keinem Microsoft Managed Desktop-Gerät zugewiesen werden.)    |
|Gerätekonfigurationsprofile     | Bestätigt, dass Konfigurationsprofile nicht allen Benutzern oder allen  Geräten zugewiesen sind (Konfigurationsprofile sollten keinem Microsoft Managed Desktop-Gerät zugewiesen werden.)     |
|Gerätetypeinschränkungen     | Überprüft, ob Windows 10-Geräte in Ihrer Organisation in Intune registriert werden dürfen        |
|Seite "Registrierungsstatus"     | Bestätigt, dass die Registrierungsstatusseite nicht aktiviert ist      |
|Intune-Registrierung     | Überprüft, ob Windows 10-Geräte in Ihrer Azure AD-Organisation automatisch in Intune registriert werden         |
|Microsoft Store für Unternehmen     | Bestätigt, dass microsoft Store für Unternehmen aktiviert und mit Intune synchronisiert ist        |
|Mehrstufige Authentifizierung | Überprüft, ob die mehrstufige Authentifizierung nicht auf Microsoft Managed Desktop-Dienstkonten angewendet wird.
|PowerShell-Skripts     | Überprüft, Windows PowerShell Skripts *nicht* auf Microsoft Managed Desktop-Geräte zugewiesen sind.    |
|Region     | Überprüft, ob Ihre Region von Microsoft Managed Desktop unterstützt wird        |
|Sicherheitsgrundwerte     | Überprüft, ob das Sicherheitsgrundprofil nicht für alle Benutzer oder  alle Geräte gilt (Sicherheitsgrundlinienrichtlinien sollten nicht auf Microsoft Managed Desktop-Geräte ausgerichtet sein.)       |
|Windows-Apps     | Überprüfen, welche Apps Sie Microsoft Managed Desktop-Geräten zuweisen möchten      |
|Windows Hello for Business     | Überprüft, ob Windows Hello for Business aktiviert ist        |
|Windows 10-Updatering     | Überprüft, ob die Richtlinie "Windows 10-Updatering" von Intune nicht für  alle Benutzer oder alle Geräte gilt (Die Richtlinie sollte nicht auf Microsoft Managed Desktop-Geräte zielen.)     |


## <a name="azure-active-directory-settings"></a>Azure Active Directory-Einstellungen

|Scheck  |Beschreibung  |
|---------|---------|
|"Ad-hoc"-Abonnements für Enterprise State Roaming     | Hier erfahren Sie, wie Sie eine Einstellung überprüfen, die (bei Festlegung auf "false") möglicherweise verhindert, dass das Enterprise State Roaming ordnungsgemäß funktioniert.  |
|Enterprise State Roaming     | Hier erfahren Sie, wie Sie überprüfen, ob das Enterprise State Roaming aktiviert ist.       |
|Lizenzen     | Überprüft, ob Sie die erforderlichen Lizenzen erhalten [haben](prerequisites.md#more-about-licenses)         |
|Mehrstufige Authentifizierung     | Überprüft, ob die mehrstufige Authentifizierung nicht auf alle Benutzer angewendet wird (Die mehrstufige Authentifizierung darf nicht versehentlich auf Microsoft Managed Desktop-Dienstkonten angewendet werden.)|
|Namen von Sicherheitskontos   | Überprüft, ob keine Benutzernamen mit denen in Konflikt stehen, die Microsoft Managed Desktop für die eigene Verwendung reserviert.        |
|Sicherheitsadministratorrollen     | Bestätigt, dass Benutzern mit Sicherheitslese-, Sicherheitsoperator- oder globalen Leserrollen diese Rollen in Microsoft Defender for Endpoint zugewiesen wurden         |
|Sicherheitsstandards | Überprüft, ob für Ihre Azure AD-Organisation Sicherheitseinstellungen in Azure Active Directory aktiviert sind. |
|Zurücksetzen von Kennwörtern durch den Benutzer     | Bestätigt, dass die Self-Service-Kennwortzurücksetzung aktiviert ist        |
|Standardbenutzerrolle     | Überprüft, ob Benutzer Standardbenutzer sind und nicht über lokale Administratorrechte verfügen         |


## <a name="microsoft-365-apps-for-enterprise-settings"></a>Microsoft 365 Apps for Enterprise-Einstellungen

|Scheck  |Beschreibung  |
|---------|---------|
|OneDrive for Business     | Überprüft, ob OneDrive for Business nicht unterstützte Einstellungen verwendet.        |


Für jede Prüfung berichtet das Tool eines von vier möglichen Ergebnissen:


|Ergebnis  |Bedeutung  |
|---------|---------|
|Bereit     | Es ist keine Aktion erforderlich, bevor Sie die Registrierung abschließen.        |
|Empfehlung    | Führen Sie die Schritte im Tool aus, um eine optimale Erfahrung mit der Registrierung und für Benutzer zu erhalten. Sie *können* die Registrierung abschließen, aber Sie müssen diese Probleme beheben, bevor Sie Ihr erstes Gerät bereitstellen.        |
|Nicht bereit | *Wenn Sie diese Probleme* nicht beheben, wird bei der Registrierung ein Fehler auftreten. Führen Sie die Schritte im Tool aus, um sie zu beheben.        |
|Error | Die Azure Active Director (AD)-Rolle, die Sie verwenden, verfügt nicht über ausreichende Berechtigungen, um diese Prüfung ausführen zu können. |

## <a name="after-enrollment"></a>Nach der Registrierung

Nachdem Sie die Registrierung bei Microsoft Managed Desktop abgeschlossen haben, denken Sie daran, zurück zu gehen und bestimmte Intune- und Azure AD-Einstellungen anzupassen. Weitere Informationen finden Sie unter [Anpassen von Einstellungen nach der Registrierung](../get-started/conditional-access.md).

## <a name="steps-to-get-ready"></a>Schritte für die ersten Schritte

1. Überprüfung der [Voraussetzungen für Microsoft Managed Desktop](prerequisites.md).
2. Verwendung des [Tools zur Bereitschaftsbewertung](readiness-assessment-tool.md). (Dieser Artikel)
3. [Voraussetzungen für Gastkonten](guest-accounts.md)
4. [Netzwerkkonfiguration für Microsoft Managed Desktop](network.md)
5. [Vorbereiten von Zertifikaten und Netzwerkprofilen für Microsoft Managed Desktop](certs-wifi-lan.md)
6. [Vorbereiten des lokalen Ressourcenzugriffs für Microsoft Managed Desktop](authentication.md)
7. [Apps im Microsoft Managed Desktop](apps.md)
8. [Vorbereiten zugeordneter Laufwerke für Microsoft Managed Desktop](mapped-drives.md)
9. [Vorbereiten der Druckressourcen für Microsoft Managed Desktop](printing.md)
