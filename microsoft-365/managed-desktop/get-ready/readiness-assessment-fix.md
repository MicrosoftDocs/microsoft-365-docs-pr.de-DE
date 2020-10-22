---
title: Beheben von Problemen, die mit dem Readiness Assessment Tool gefunden wurden
description: Detaillierte Aktionen, die für jedes von dem Tool gefundene Problem ausgeführt werden sollten
keywords: Microsoft Managed Desktop, Microsoft 365, Dienst, Dokumentation
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 2c9638dc7b8c6d095b87cf81114f3812c8362597
ms.sourcegitcommit: 3b1bd8aa1430bc9565743a446bbc27b199f30f73
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/22/2020
ms.locfileid: "48656139"
---
# <a name="fix-issues-found-by-the-readiness-assessment-tool"></a>Beheben von Problemen, die mit dem Readiness Assessment Tool gefunden wurden

Für jede Überprüfung meldet das Tool eines von drei möglichen Ergebnissen:


|Ergebnis  |Bedeutung  |
|---------|---------|
|Bereit     | Vor Abschluss der Registrierung ist keine Aktion erforderlich.        |
|Empfehlung    | Befolgen Sie die Schritte im Tool oder in diesem Artikel, um die besten Erfahrungen bei der Registrierung und für Benutzer zu finden. Sie *können* die Registrierung abschließen, aber Sie müssen diese Probleme beheben, bevor Sie das erste Gerät bereitstellen.        |
|Nicht bereit | *Die Registrierung schlägt fehl, wenn Sie diese Probleme nicht beheben.* Befolgen Sie die Schritte im Tool oder in diesem Artikel, um Sie zu beheben.        |

## <a name="microsoft-intune-settings"></a>Microsoft InTune-Einstellungen

### <a name="autopilot-deployment-profile"></a>Autopilot-Bereitstellungsprofil

Es sollten keine Autopilot-Profile vorhanden sein, die auf zugewiesene oder dynamische Gruppen abzielen, die von Microsoft Managed Desktop verwendet werden. Microsoft Managed Desktop verwendet Autopilot, um neue Geräte vorzusehen.

**Nicht bereit**

Sie verfügen über ein Autopilot-Profil, das allen Geräten zugewiesen ist. Schritte finden Sie unter [Registrieren von Windows-Geräten in InTune mithilfe von Windows Autopilot](https://docs.microsoft.com/mem/autopilot/enrollment-autopilot). Nachdem Sie die Microsoft Managed Desktop-Registrierung eingerichtet haben, müssen Sie Ihre Autopilot-Richtlinie so konfigurieren, dass die **modernen Arbeitsplatz Geräte-alle** Azure Ad Gruppe ausgeschlossen werden

**Empfehlung**

Stellen Sie sicher, dass Ihre Autopilot-Profile auf eine zugewiesene oder dynamische Azure Ad Gruppe Zielen, die keine von Microsoft verwalteten Desktop-Geräte enthält, die bei der Registrierung erstellt werden. Schritte finden Sie unter [Registrieren von Windows-Geräten in InTune mithilfe von Windows Autopilot](https://docs.microsoft.com/mem/autopilot/enrollment-autopilot). Nachdem Sie die Microsoft Managed Desktop-Registrierung eingerichtet haben, müssen Sie Ihre Autopilot-Richtlinie so konfigurieren, dass die **modernen Arbeitsplatz Geräte-alle** Azure Ad Gruppe ausgeschlossen werden


### <a name="certificate-connectors"></a>Zertifikat-Konnektoren

Wenn Sie über die von den Geräten, die Sie in Microsoft Managed Desktop registrieren möchten, verwendeten Zertifikat-Konnektoren haben, können die Connectors keine Fehler aufweisen. Nur einer der folgenden Hinweise wird auf Ihre Situation zutreffen, daher sollten Sie Sie sorgfältig überprüfen.

**Empfehlung**

Es sind keine Zertifikat-Konnektoren vorhanden. Es ist möglich, dass Sie keine Konnektoren benötigen, aber Sie sollten überprüfen, ob Sie möglicherweise einige für die Netzwerkkonnektivität mit Microsoft Managed Desktop-Geräten benötigen. Weitere Informationen finden Sie unter [Prepare Certificates and Network Profiles for Microsoft Managed Desktop](certs-wifi-lan.md).

**Empfehlung**

Mindestens ein Zertifikat-Konnektor hat einen Fehler. Wenn Sie diesen Connector für die Verbindung mit Microsoft Managed Desktop-Geräten benötigen, müssen Sie den Fehler beheben. Weitere Informationen finden Sie unter [Prepare Certificates and Network Profiles for Microsoft Managed Desktop](certs-wifi-lan.md).


**Empfehlung**

Sie verfügen über mindestens einen Zertifikat-Konnektor, und es werden keine Fehler gemeldet. Möglicherweise müssen Sie jedoch ein Profil erstellen, um den Connector für Microsoft Managed Desktop-Geräte wiederzuverwenden. Weitere Informationen finden Sie unter [Prepare Certificates and Network Profiles for Microsoft Managed Desktop](certs-wifi-lan.md).


### <a name="conditional-access-policies"></a>Richtlinien für bedingten Zugriff

Richtlinien für bedingten Zugriff in ihrer Azure AD Organisation dürfen keine Microsoft Manage Desktop-Benutzer abzielen.

**Nicht bereit**

Sie haben mindestens eine Richtlinie für den bedingten Zugriff, die auf alle Benutzer abzielt. Setzen Sie die Richtlinie auf eine bestimmte Azure Ad Gruppe zurück, die nicht die Azure Ad Gruppe von Microsoft Managed Desktop-Dienstkonten enthält, die bei der Registrierung erstellt werden. Schritte finden Sie unter [bedingter Zugriff: Benutzer und Gruppen](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-users-groups).

**Empfehlung**

Stellen Sie sicher, dass alle Richtlinien für den bedingten Zugriff die Azure Ad Gruppe für **moderne Arbeitsplatz Dienstkonten** ausschließen. Schritte finden Sie unter [Anpassen des bedingten Zugriffs](https://docs.microsoft.com/microsoft-365/managed-desktop/get-started/conditional-access). Die **Dienstkonten für moderne Arbeitsplatz Dienste** Azure Ad Gruppe ist eine dynamische Gruppe, die wir bei der Registrierung für den Dienst erstellen. Sie müssen zurückkehren, um diese Gruppe nach der Registrierung auszuschließen. Weitere Informationen zu diesen Dienstkonten finden Sie unter [Standard Operating Procedures](../service-description/operations-and-monitoring.md#standard-operating-procedures).


### <a name="device-compliance-policies"></a>Geräte Konformitätsrichtlinien

InTune-Geräte Konformitätsrichtlinien in ihrer Azure AD Organisation dürfen keine Microsoft Managed Desktop-Benutzer adressieren.

**Nicht bereit**

Sie haben mindestens eine Konformitätsrichtlinie, die auf alle Benutzer abzielt. Setzen Sie die Richtlinie auf eine bestimmte Azure Ad Gruppe, die keine Benutzer von Microsoft Managed Desktop enthält. Eine schrittweise Anleitung finden Sie unter [Create a Compliance Policy in Microsoft InTune](https://docs.microsoft.com/mem/intune/protect/create-compliance-policy).

**Empfehlung**

Stellen Sie sicher, dass alle Konformitätsrichtlinien, die Sie verwenden, keine von Microsoft verwalteten Desktop Benutzer enthalten. Eine schrittweise Anleitung finden Sie unter [Create a Compliance Policy in Microsoft InTune](https://docs.microsoft.com/mem/intune/protect/create-compliance-policy).



### <a name="device-configuration-policies"></a>Geräte Konfigurationsrichtlinien

InTune-Geräte Konfigurationsrichtlinien in ihrer Azure AD Organisation dürfen keine Microsoft Manage-Desktop Geräte oder-Benutzer als Ziel haben.

**Nicht bereit**

Sie verfügen über mindestens eine Konfigurationsrichtlinie, die auf alle Benutzer, alle Geräte oder beides abzielt. Setzen Sie die Richtlinie auf eine bestimmte Azure Ad Gruppe, die keine verwalteten Desktop Geräte von Microsoft enthält, zurück. Eine schrittweise Anleitung finden Sie unter [Create a Compliance Policy in Microsoft InTune](https://docs.microsoft.com/mem/intune/configuration/custom-settings-configure).

**Empfehlung**

Stellen Sie sicher, dass alle Konformitätsrichtlinien, die Sie verwenden, keine von Microsoft verwalteten Desktop Geräte oder Benutzer enthalten. Eine schrittweise Anleitung finden Sie unter [Create a Compliance Policy in Microsoft InTune](https://docs.microsoft.com/mem/intune/configuration/custom-settings-configure).



### <a name="device-type-restrictions"></a>Einschränkungen für Gerätetypen

Microsoft Managed Desktop-Geräte müssen sich in InTune registrieren können.

**Nicht bereit**

Befolgen Sie die Schritte unter [Festlegen von Registrierungs Einschränkungen](https://docs.microsoft.com/mem/intune/enrollment/enrollment-restrictions-set) , um die Einstellung in **zulassen**zu ändern.


### <a name="enrollment-status-page"></a>Seite "Registrierungs Status"

Derzeit ist die Registrierungs Status Seite (ESP) aktiviert. Wenn Sie an der öffentlichen Vorschau dieses Features teilnehmen, können Sie dieses Element ignorieren. Weitere Informationen finden Sie unter [First-Run-Erfahrung mit Autopilot und der Registrierungs Status Seite](../get-started/esp-first-run.md).

**Nicht bereit**

Sie haben das ESP-Standardprofil festgelegt, um den **Fortschritt der APP-und Profilkonfiguration anzuzeigen**. Deaktivieren Sie diese Einstellung, indem Sie die Schritte unter [Einrichten der Registrierungs Status Seite](https://docs.microsoft.com/mem/intune/enrollment/windows-enrollment-status)ausführen.

**Empfehlung**

Stellen Sie sicher, dass alle Profile mit der Einstellung " **App-und Profil Konfigurationsstatus anzeigen** " keiner Azure Ad Gruppe zugeordnet sind, die Microsoft Managed Desktop-Geräte enthält. Weitere Informationen finden Sie unter [Einrichten der Registrierungs Status Seite](https://docs.microsoft.com/mem/intune/enrollment/windows-enrollment-status).

### <a name="intune-enrollment"></a>InTune-Registrierung

Windows 10-Geräte in ihrer Azure AD Organisation müssen automatisch in InTune registriert sein.

**Nicht bereit**

Benutzer in ihrer Azure AD Organisation werden nicht automatisch in Microsoft InTune registriert. Ändern Sie den MDM-Benutzerbereich in **einen** oder **alle**. Wenn Sie auswählen. Einige * *, kehren Sie nach der Registrierung zurück, und wählen Sie die Gruppe **moderner Arbeitsplatz-alle** Azure AD für **Gruppen**aus.


### <a name="microsoft-store-for-business"></a>Microsoft Store für Unternehmen

Microsoft Store for Business wird verwendet, damit Sie das Unternehmens Portal herunterladen können, um einige apps wie Microsoft Project und Microsoft Visio bereitzustellen.

**Nicht bereit**

Microsoft Store for Business ist entweder nicht aktiviert oder nicht mit InTune synchronisiert. Weitere Informationen finden Sie unter [Verwalten von Volumen erworbenen Apps aus dem Microsoft Store for Business mit Microsoft InTune](https://docs.microsoft.com/mem/intune/apps/windows-store-for-business) und [Installieren des InTune-Unternehmensportals auf auf Geräten](../get-started/company-portal.md).

### <a name="multi-factor-authentication"></a>Mehrstufige Authentifizierung

Die mehrstufige Authentifizierung darf nicht versehentlich auf von Microsoft verwaltete Desktop Dienstkonten angewendet werden.


**Nicht bereit**

Sie haben einige Richtlinien für die mehrstufige Authentifizierung (MFA) als "erforderlich" für Richtlinien für bedingten Zugriff festgelegt, die allen Benutzern zugewiesen sind. Ändern Sie die Richtlinie so, dass eine Zuweisung verwendet wird, die auf eine bestimmte Azure Ad Gruppe zielt, die keine von Microsoft verwalteten Desktop Geräte enthält. Weitere Informationen finden Sie unter [bedingter Zugriffsrichtlinien](#conditional-access-policies) und [bedingter Zugriff: MFA für alle Benutzer erforderlich](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa).

**Empfehlung**

Stellen Sie sicher, dass alle bedingten Zugriffsrichtlinien, die MFA erfordern, den **modernen Arbeitsplatz-alle** Azure Ad Gruppe ausschließen. Weitere Informationen finden Sie unter [bedingter Zugriffsrichtlinien](#conditional-access-policies) und [bedingter Zugriff: MFA für alle Benutzer erforderlich](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa). Die Gruppe " **moderner Arbeitsplatz-alle** Azure AD" ist eine dynamische Gruppe, die wir erstellen, wenn Sie sich für Microsoft Managed Desktop registrieren, damit Sie nach der Registrierung zurückkehren müssen, um diese Gruppe auszuschließen.



### <a name="powershell-scripts"></a>PowerShell-Skripts

Windows PowerShell Skripts können nicht auf eine Weise zugewiesen werden, die auf Microsoft Managed Desktop-Geräte abzielt.  

**Empfehlung**

Stellen Sie sicher, dass Windows PowerShell Skripts in ihrer Azure AD Organisation nicht auf Microsoft Manage-Desktop Geräte oder-Benutzer abzielen. Weitere Informationen finden Sie unter [Verwenden von PowerShell-Skripts auf Windows 10-Geräten in InTune](https://docs.microsoft.com/mem/intune/apps/intune-management-extension).

### <a name="region"></a>Region

Ihre Region muss von Microsoft Managed Desktop unterstützt werden.

**Nicht bereit**

Ihre Azure AD Organisations Region wird derzeit nicht von Microsoft Managed Desktop unterstützt. Weitere Informationen finden Sie unter [unterstützte Regionen und Sprachen in Microsoft Managed Desktop](../service-description/regions-languages.md).

**Empfehlung**

Mindestens ein Land, in dem sich Ihre Azure AD Organisation befindet, wird von Microsoft Managed Desktop nicht unterstützt. Weitere Informationen finden Sie unter [unterstützte Regionen und Sprachen in Microsoft Managed Desktop](../service-description/regions-languages.md).


### <a name="security-baselines"></a>Sicherheitsbasislinien

Sicherheitsbasislinien sollten nicht auf Microsoft Managed Desktop-Geräte abzielen.

**Nicht bereit**

Sie verfügen über ein Sicherheitsbasis Profil, das auf alle Benutzer, alle Geräte oder beides abzielt. Ändern Sie die Richtlinie so, dass eine Zuweisung verwendet wird, die auf eine bestimmte Azure Ad Gruppe zielt, die keine von Microsoft verwalteten Desktop Geräte enthält. Eine schrittweise Anleitung finden Sie unter [use Security Baselines to configure Windows 10 Devices in InTune](https://docs.microsoft.com/mem/intune/protect/security-baselines).

**Empfehlung**

Stellen Sie sicher, dass alle Sicherheitsbasis Richtlinien, auf denen Sie Microsoft Managed Desktop-Geräte ausschließen. Eine schrittweise Anleitung finden Sie unter [use Security Baselines to configure Windows 10 Devices in InTune](https://docs.microsoft.com/mem/intune/protect/security-baselines). Die **moderne Arbeitsplatz Geräte-alle** Azure Ad Gruppe ist eine dynamische Gruppe, die wir erstellen, wenn Sie sich für Microsoft Managed Desktop registrieren, damit Sie nach der Registrierung zurückkehren müssen, um diese Gruppe auszuschließen.


### <a name="windows-apps"></a>Windows-apps

Überprüfen Sie die apps, die Ihre Microsoft Managed Desktop-Benutzer haben sollen.

**Empfehlung**

Sie sollten eine Inventarisierung der apps vorbereiten, die ihre von Microsoft verwalteten Desktop-Benutzer haben sollen. Stellen Sie sicher, dass diese apps von InTune bereitgestellt werden können. Weitere Informationen finden Sie unter [apps in Microsoft Managed Desktop](apps.md).

Sie können Ihren Microsoft-Konto Vertreter für eine Abfrage im Microsoft Endpoint Configuration Manager bitten, um die apps zu identifizieren, die für die Migration zu InTune bereit sind oder Anpassungen benötigen.


### <a name="windows-hello-for-business"></a>Windows Hello for Business

Microsoft Managed Desktop erfordert die Aktivierung von Windows Hello for Business.

**Nicht bereit**

Windows Hello for Business ist deaktiviert. Aktivieren Sie es, indem Sie die Schritte unter [Erstellen einer Windows Hello for Business-Richtlinie](https://docs.microsoft.com/mem/intune/protect/windows-hello#create-a-windows-hello-for-business-policy) ausführen.

**Empfehlung**

Windows Hello for Business ist nicht eingerichtet. Aktivieren Sie es, indem Sie die Schritte unter [Erstellen einer Windows Hello for Business-Richtlinie](https://docs.microsoft.com/mem/intune/protect/windows-hello#create-a-windows-hello-for-business-policy)ausführen.


### <a name="windows-10-update-rings"></a>Windows 10-Update klingelt

Die Richtlinie "Windows 10 Update Ring" in InTune darf nicht auf Microsoft-verwaltete Desktop Geräte abzielen.

**Nicht bereit**

Sie haben eine Richtlinie "Update Ring", die auf alle Geräte, alle Benutzer oder beides abzielt. Ändern Sie die Richtlinie so, dass eine Zuweisung verwendet wird, die auf eine bestimmte Azure Ad Gruppe zielt, die keine von Microsoft verwalteten Desktop Geräte enthält. Eine schrittweise Anleitung finden Sie unter [Manage Windows 10 Softwareupdates in InTune](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure).

**Empfehlung**

Stellen Sie sicher, dass alle Update Ring-Richtlinien den **modernen Arbeitsplatz-alle** Azure Ad Gruppe ausschließen. Eine schrittweise Anleitung finden Sie unter [Manage Windows 10 Softwareupdates in InTune](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure). Die **moderne Arbeitsplatz Geräte-alle** Azure Ad Gruppe ist eine dynamische Gruppe, die wir erstellen, wenn Sie sich für Microsoft Managed Desktop registrieren, damit Sie nach der Registrierung zurückkehren müssen, um diese Gruppe auszuschließen.


## <a name="azure-active-directory-settings"></a>Azure Active Directory-Einstellungen


### <a name="ad-hoc-subscriptions"></a>Ad-hoc-Abonnements

Gibt an, wie eine Einstellung überprüft wird, die (wenn Sie auf "false" festgelegt ist) möglicherweise verhindert, dass das Roaming von Unternehmensstatus ordnungsgemäß funktioniert.

**Empfehlung**

Stellen Sie sicher, dass **AllowAdHocSubscriptions** auf **true**festgelegt ist. Andernfalls funktioniert das Roaming im Enterprise-Status möglicherweise nicht. Weitere Informationen finden Sie unter [Sets-MsolCompanySettings](https://docs.microsoft.com/powershell/module/msonline/set-msolcompanysettings?view=azureadps-1.0).


### <a name="enterprise-state-roaming"></a>Enterprise State Roaming

Das Enterprise-Status-Roaming sollte aktiviert sein.

**Empfehlung**

Stellen Sie sicher, dass das Enterprise-Status-Roaming für **alle** oder für **ausgewählte** Gruppen aktiviert ist. Weitere Informationen finden Sie unter [enable Enterprise State Roaming in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/devices/enterprise-state-roaming-enable).

### <a name="licenses"></a>Lizenzen

Für die Verwendung von Microsoft Managed Desktop sind eine Reihe von Lizenzen erforderlich.

**Nicht einsatzfähig**

Sie verfügen nicht über alle Lizenzen, die Sie für die Verwendung von Microsoft Managed Desktop benötigen. Weitere Informationen finden Sie unter [Microsoft Managed Desktop Technologies](../intro/technologies.md) und [mehr zu Lizenzen](prerequisites.md#more-about-licenses).


### <a name="security-account-names"></a>Namen von Sicherheitskonten

Bestimmte Namen von Sicherheitskonten können Konflikte mit denen verursachen, die von Microsoft Managed Desktop erstellt wurden.

**Nicht bereit**

Sie haben mindestens einen Kontonamen, der mit den von Microsoft Managed Desktop erstellten Konflikten in Konflikt steht. Arbeiten Sie mit Ihrem Microsoft-Konto Vertreter zusammen, um diese Kontonamen auszuschließen.


### <a name="security-administrator-roles"></a>Sicherheitsadministrator Rollen

Benutzer mit bestimmten Sicherheitsrollen müssen diese in Microsoft Defender für Endpoint zugewiesen haben.

**Empfehlung**

Wenn Sie eine dieser Rollen in ihrer Azure AD Organisation zugewiesen haben, stellen Sie sicher, dass diese Rollen auch in Microsoft Defender für Endpoint zugewiesen sind. Andernfalls können Administratoren mit diesen Rollen nicht auf das Verwaltungsportal zugreifen.

- Sicherheitsleseberechtigter
- Sicherheitsoperator
- Globaler Leser

Weitere Informationen finden Sie unter [Erstellen und Verwalten von Rollen für die rollenbasierte Zugriffssteuerung](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/user-roles).


### <a name="security-default"></a>Sicherheitsstandard

Sicherheitsstandards in Azure Active Directory verhindern, dass von Microsoft Managed Desktop Ihre Geräte verwaltet werden.

**Nicht bereit**

Sie haben Sicherheitsstandards aktiviert. Deaktivieren Sie Sicherheitseinstellungen, und richten Sie Richtlinien für bedingten Zugriff ein. Weitere Informationen finden Sie unter [Common Conditional Access Policies](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-policy-common).

### <a name="self-service-password-reset"></a>Zurücksetzen von Self-Service-Kennwörtern

Self-Service Password Reset (SSPR) muss aktiviert sein.

**Nicht bereit**

SSPR muss für alle Benutzer aktiviert sein. Wenn dies nicht der Fall ist, können die Microsoft Managed Desktop-Dienstkonten nicht funktionieren. Weitere Informationen finden Sie unter [Lernprogramm: Aktivieren von Benutzern zum Entsperren Ihres Kontos oder Zurücksetzen von Kennwörtern mithilfe von Azure Active Directory Self-Service Password Reset](https://docs.microsoft.com/azure/active-directory/authentication/tutorial-enable-sspr).

**Empfehlung**

Stellen Sie sicher, dass die SSPR **Selected** -Einstellung Microsoft Managed Desktop Devices enthält.

### <a name="standard-user-role"></a>Standard Benutzerrolle

Microsoft Managed Desktop-Benutzer sollten Standardbenutzer ohne lokale Administratorrechte sein. Ihnen wird beim Starten Ihres von Microsoft verwalteten Desktop Geräts eine Standardbenutzerrolle zugewiesen.

**Empfehlung**

Microsoft Managed Desktop-Benutzer sollten vor dem registrieren keine lokalen Administratorrechte haben.

## <a name="microsoft-365-apps-for-enterprise"></a>Microsoft 365 Apps for Enterprise

### <a name="onedrive-for-business"></a>OneDrive for Business

Die Einstellung **Synchronisierung nur auf PCs zulassen, die mit bestimmten Domänen verbunden sind,** wird mit dem Microsoft Managed Desktop in Konflikt stehen.

**Empfehlung**

Sie verwenden die Einstellung **Synchronisierung nur für PCs zulassen, die mit bestimmten Domänen verbunden** sind. Diese Einstellung funktioniert nicht mit Microsoft Managed Desktop. Deaktivieren Sie diese Einstellung, und richten Sie OneDrive für Unternehmen für die Verwendung einer Richtlinie für bedingten Zugriff ein. Weitere Informationen finden Sie unter [Planen einer Bereitstellung für bedingten Zugriff](https://docs.microsoft.com/azure/active-directory/conditional-access/plan-conditional-access) .

