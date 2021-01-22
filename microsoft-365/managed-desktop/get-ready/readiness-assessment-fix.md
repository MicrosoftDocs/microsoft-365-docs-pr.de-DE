---
title: Lösen von Problemen, die durch das Tool zur Bereitschaftsbewertung gefunden wurden
description: Detaillierte Aktionen, die für jedes vom Tool gefundene Problem zu ergreifen sind
keywords: Microsoft Managed Desktop, Microsoft 365, Dienst, Dokumentation
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: f1af39a9b2a09908ecf5f5ff15b9fd6d764459d6
ms.sourcegitcommit: 7ecd10b302b3b3dfa4ba3be3a6986dd3c189fbff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/21/2021
ms.locfileid: "49921858"
---
# <a name="fix-issues-found-by-the-readiness-assessment-tool"></a>Lösen von Problemen, die durch das Tool zur Bereitschaftsbewertung gefunden wurden

Für jede Überprüfung gibt das Tool eines von vier möglichen Ergebnissen an:


|Ergebnis  |Bedeutung  |
|---------|---------|
|Bereit     | Es ist keine Aktion erforderlich, bevor die Registrierung abgeschlossen wird.        |
|Empfehlung    | Führen Sie die Schritte im Tool oder in diesem Artikel aus, um die beste Erfahrung mit der Registrierung und den Benutzern zu bieten. Sie *können* die Registrierung abschließen, aber Sie müssen diese Probleme beheben, bevor Sie Ihr erstes Gerät bereitstellen.        |
|Nicht bereit | *Die Registrierung wird fehlschlagen, wenn Sie diese Probleme nicht beheben.* Führen Sie die Schritte im Tool oder in diesem Artikel aus, um sie zu beheben.        |
|Error | Die Azure Active Director (AD)-Rolle, die Sie verwenden, verfügt nicht über ausreichende Berechtigungen, um diese Überprüfung ausführen zu können. |

> [!NOTE]
> Die von diesem Tool gemeldeten Ergebnisse spiegeln den Status Ihrer Einstellungen nur zu dem bestimmten Zeitpunkt wider, zu dem Sie sie verwendet haben. Wenn Sie später Änderungen an Richtlinien in Microsoft Intune, Azure Active Directory oder Microsoft 365 vornehmen, können Elemente, die "Bereit" waren, "Nicht bereit" werden. Überprüfen Sie die in diesem Artikel beschriebenen Einstellungen, bevor Sie Richtlinien ändern, um Probleme mit Microsoft Managed Desktop-Vorgängen zu vermeiden.

## <a name="microsoft-intune-settings"></a>Microsoft Intune-Einstellungen

Sie können im Microsoft Endpoint Manager Admin Center auf die Einstellungen von Intune [zugreifen.](https://endpoint.microsoft.com)

### <a name="autopilot-deployment-profile"></a>Autopilot-Bereitstellungsprofil

Sie sollten keine vorhandenen Autopilotprofile haben, die auf zugewiesene oder dynamische Gruppen mit Microsoft Managed Desktop-Geräten zielen. Microsoft Managed Desktop verwendet Autopilot zum Bereitstellen neuer Geräte.

**Nicht bereit**

Sie verfügen über ein Autopilot-Profil, das allen Geräten zugewiesen ist. Die Schritte finden Sie unter [Registrieren von Windows-Geräten in Intune mithilfe von Windows Autopilot.](https://docs.microsoft.com/mem/autopilot/enrollment-autopilot) Legen Sie nach der Registrierung von Microsoft Managed Desktop Ihre Autopilot-Richtlinie so vor, dass die **Gruppe "Moderne Arbeitsplatzgeräte – Alle** Azure AD" ausgeschlossen wird.

**Empfehlung**

Stellen Sie sicher, dass Ihre Autopilotprofile für eine zugewiesene oder dynamische Azure AD-Gruppe bestimmt sind, die keine Microsoft Managed Desktop-Geräte enthält. Die Schritte finden Sie unter [Registrieren von Windows-Geräten in Intune mithilfe von Windows Autopilot.](https://docs.microsoft.com/mem/autopilot/enrollment-autopilot) Legen Sie nach der Registrierung von Microsoft Managed Desktop Ihre Autopilotprofile so vor, dass sie die **Gruppe "Moderne Arbeitsplatzgeräte – Alle** Azure AD" ausschließen.


### <a name="certificate-connectors"></a>Zertifikatconnectors

Wenn Sie über Zertifikatconnectors verfügen, die von den Geräten verwendet werden, die Sie bei Microsoft Managed Desktop registrieren möchten, sollten für die Connectors keine Fehler auftreten. Es gilt nur einer der folgenden Ratgeber für Ihre Situation. Überprüfen Sie sie daher sorgfältig.

**Empfehlung**

Es sind keine Zertifikatconnectors vorhanden. Es ist möglich, dass Sie keine Connectors benötigen, aber Sie sollten prüfen, ob Sie möglicherweise einige für die Netzwerkkonnektivität auf Ihren Microsoft Managed Desktop-Geräten benötigen. Weitere Informationen finden Sie unter [Vorbereiten von Zertifikaten und Netzwerkprofilen für Microsoft Managed Desktop](certs-wifi-lan.md).

**Empfehlung**

Mindestens ein Zertifikatconnector hat einen Fehler. Wenn Sie diesen Connector zum Bereitstellen von Zertifikaten für Microsoft Managed Desktop-Geräte benötigen, müssen Sie den Fehler beheben. Weitere Informationen finden Sie unter [Vorbereiten von Zertifikaten und Netzwerkprofilen für Microsoft Managed Desktop](certs-wifi-lan.md).


**Empfehlung**

Sie verfügen über mindestens einen Zertifikatconnector, und es werden keine Fehler gemeldet. Zur Vorbereitung der Bereitstellung müssen Sie jedoch möglicherweise ein Profil erstellen, um den Connector für Microsoft Managed Desktop-Geräte wiederzuverwenden. Weitere Informationen finden Sie unter [Vorbereiten von Zertifikaten und Netzwerkprofilen für Microsoft Managed Desktop](certs-wifi-lan.md).


### <a name="conditional-access-policies"></a>Richtlinien für bedingten Zugriff

Richtlinien für bedingten Zugriff in Ihrer Azure AD-Organisation dürfen keine Microsoft Manage Desktop -Dienstkonten als Ziel haben.

**Nicht bereit**

Sie verfügen über mindestens eine Richtlinie für bedingten Zugriff für alle Benutzer. Ändern Sie die Richtlinie für eine bestimmte Azure AD-Gruppe, die nicht die Azure AD-Gruppe von Microsoft Managed Desktop-Dienstkonten enthält, die bei der Registrierung erstellt werden. Die Schritte finden Sie unter [Bedingter Zugriff: Benutzer und Gruppen.](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-users-groups)

**Empfehlung**

Stellen Sie sicher, dass alle Richtlinien für bedingten Zugriff, die Sie erstellt haben, die **Azure AD-Gruppe "Modern Workplace Service Accounts"** ausschließen. Weitere Schritte finden Sie unter [Anpassen des bedingten Zugriffs.](https://docs.microsoft.com/microsoft-365/managed-desktop/get-started/conditional-access) Die **Azure AD-Gruppe "Modern Workplace Service Accounts"** ist eine dynamische Gruppe, die wir bei der Registrierung für den Dienst erstellen. Sie müssen nach der Registrierung wiederkommen, um diese Gruppe auszuschließen. Weitere Informationen zu diesen Dienstkonten finden Sie unter [Standard operating procedures](../service-description/operations-and-monitoring.md#standard-operating-procedures).

**Fehler**

Die Rolle "Intune-Administrator" verfügt nicht über ausreichende Berechtigungen für diese Überprüfung. Außerdem benötigen Sie eine der folgenden Azure AD-Rollen, um diese Prüfung ausführen zu können:

- Sicherheitsleseberechtigter
- Sicherheitsadministrator
- Administrator für bedingten Zugriff
- Globaler Leser
- Geräteadministrator


### <a name="device-compliance-policies"></a>Gerätekonformitätsrichtlinien

Richtlinien zur Gerätekonformität in Intune in Ihrer Azure AD-Organisation können Auswirkungen auf Microsoft Managed Desktop-Geräte haben.

**Nicht bereit**

Sie verfügen über mindestens eine Compliancerichtlinie, die auf alle Benutzer abzielt. Microsoft Managed Desktop enthält Compliancerichtlinien für Ihre Microsoft Managed Desktop-Geräte.  Ändern Sie die Richtlinie für eine bestimmte Azure AD-Gruppe, die keine Microsoft Managed Desktop-Benutzer oder -Geräte enthält. Die Schritte finden Sie unter [Erstellen einer Compliancerichtlinie in Microsoft Intune.](https://docs.microsoft.com/mem/intune/protect/create-compliance-policy)

**Empfehlung**

Stellen Sie sicher, dass alle Compliancerichtlinien, die Sie haben, nicht für Microsoft Managed Desktop-Benutzer bestimmt sind. Die Schritte finden Sie unter [Erstellen einer Compliancerichtlinie in Microsoft Intune.](https://docs.microsoft.com/mem/intune/protect/create-compliance-policy)



### <a name="device-configuration-profiles"></a>Gerätekonfigurationsprofile

Intune-Gerätekonfigurationsprofile in Ihrer Azure AD-Organisation dürfen nicht für Microsoft Manage Desktop-Geräte oder -Benutzer verwendet werden.

**Nicht bereit**

Sie verfügen über mindestens ein Konfigurationsprofil für alle Benutzer, alle Geräte oder beides. Setzen Sie das Profil auf eine bestimmte Azure AD-Gruppe zurück, die keine Microsoft Managed Desktop-Geräte enthält. Schritte finden Sie unter [Erstellen eines Profils mit benutzerdefinierten Einstellungen in Microsoft Intune.](https://docs.microsoft.com/mem/intune/configuration/custom-settings-configure)

**Empfehlung**

Stellen Sie sicher, dass alle Konfigurationsrichtlinien, die Sie haben, keine Microsoft Managed Desktop-Geräte oder -Benutzer enthalten. Weitere Informationen finden Sie unter [Erstellen eines Profils mit benutzerdefinierten Einstellungen in Microsoft Intune.](https://docs.microsoft.com/mem/intune/configuration/custom-settings-configure)



### <a name="device-type-restrictions"></a>Gerätetypeinschränkungen

Microsoft Managed Desktop-Geräte müssen sich bei Intune registrieren dürfen.

**Nicht bereit**

Sie haben derzeit mindestens eine Richtlinie zur Registrierungseinschränkung konfiguriert, um die Registrierung von Windows-Geräten in Intune zu verhindern. Führen Sie [](https://docs.microsoft.com/mem/intune/enrollment/enrollment-restrictions-set) die Schritte in "Registrierungseinschränkungen festlegen" für jede Registrierungseinschränkungsrichtlinie für Microsoft Managed Desktop-Benutzer aus, und ändern Sie die Einstellung für **Windows (MDM)** in **"Zulassen".** Sie können jedoch alle persönlichen **Windows (MDM)-Geräte** auf **"Blockieren" festlegen.**  


### <a name="enrollment-status-page"></a>Seite "Registrierungsstatus"

Derzeit ist die Seite "Registrierungsstatus" (Enrollment Status Page, ESP) aktiviert. Wenn Sie an der öffentlichen Vorschau dieses Features von Microsoft Managed Desktop teilnehmen möchten, können Sie dieses Element ignorieren. Weitere Informationen finden Sie unter ["Erste Ausführung" mit Autopilot und der Seite "Registrierungsstatus".](../get-started/esp-first-run.md)

**Nicht bereit**

Sie haben das Standardprofil ESP auf **"App- und Profilkonfigurationsfortschritt anzeigen" festgelegt.** Deaktivieren Sie diese Einstellung, oder stellen Sie sicher, dass Zuordnungen zu einer Azure AD-Gruppe keine Microsoft Managed Desktop-Geräte enthalten, indem Sie die Schritte unter "Einrichten [der Registrierungsstatusseite" ausführen.](https://docs.microsoft.com/mem/intune/enrollment/windows-enrollment-status)

**Empfehlung**

Stellen Sie sicher, dass  Alle Profile mit der Statuseinstellung "App- und Profilkonfiguration anzeigen" keinem Azure AD-Gruppen zugewiesen sind, die Microsoft Managed Desktop-Geräte enthalten. Weitere Informationen finden Sie auf [der Seite "Registrierungsstatus einrichten".](https://docs.microsoft.com/mem/intune/enrollment/windows-enrollment-status)

### <a name="microsoft-store-for-business"></a>Microsoft Store für Unternehmen

Wir verwenden den Microsoft Store für Unternehmen und stellen die Unternehmensportal-App auf Microsoft Managed Desktop zur Verfügung, damit Benutzer optional einige Apps installieren können, z. B. Microsoft Project und Microsoft Visio (sofern zulässig).

**Nicht bereit**

Der Microsoft Store für Unternehmen ist entweder nicht aktiviert oder nicht mit Intune synchronisiert. Weitere Informationen finden Sie unter Verwalten von Volumen gekaufter Apps aus dem [Microsoft Store für Unternehmen](https://docs.microsoft.com/mem/intune/apps/windows-store-for-business) mit Microsoft Intune und Installieren des [Intune-Unternehmensportals auf Geräten.](../get-started/company-portal.md)

### <a name="multifactor-authentication"></a>Mehrstufige Authentifizierung

Die mehrstufige Authentifizierung darf nicht auf Microsoft Managed Desktop -Dienstkonten angewendet werden.


**Nicht bereit**

Sie haben einige mehrstufige Authentifizierungsrichtlinien festgelegt, die für **Richtlinien** für bedingten Zugriff erforderlich sind, die allen Benutzern zugewiesen sind. Ändern Sie die Richtlinie so, dass eine Zuweisung für eine bestimmte Azure AD-Gruppe verwendet wird, die keine Microsoft Managed Desktop -Dienstkonten enthält. Weitere Informationen finden Sie unter [Richtlinien für bedingten Zugriff](#conditional-access-policies) und [bedingter Zugriff: MFA für alle Benutzer erforderlich.](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa)

**Empfehlung**

Stellen Sie sicher, dass alle Richtlinien für bedingten Zugriff, die eine mehrstufige Authentifizierung erfordern, die **Gruppe "Moderner Arbeitsplatz – Alle** Azure AD" ausschließen. Weitere Informationen finden Sie unter [Richtlinien für bedingten Zugriff](#conditional-access-policies) und [bedingter Zugriff: MFA für alle Benutzer erforderlich.](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa) The **Modern Workplace -All** Azure AD group is a dynamic group that we create when you enroll in Microsoft Managed Desktop, so you'll have to come back to exclude this group after enrollment.

**Fehler**

Die Rolle "Intune-Administrator" verfügt nicht über ausreichende Berechtigungen für diese Überprüfung. Außerdem benötigen Sie eine der folgenden Azure AD-Rollen, um diese Prüfung ausführen zu können:

- Sicherheitsleseberechtigter
- Sicherheitsadministrator
- Administrator für bedingten Zugriff
- Globaler Leser
- Geräteadministrator


### <a name="powershell-scripts"></a>PowerShell-Skripts

Windows PowerShell Skripts können nicht auf eine Weise zugewiesen werden, die auf Microsoft Managed Desktop-Geräte zielen würde.  

**Empfehlung**

Stellen Sie sicher, Windows PowerShell Skripts in Ihrer Azure AD-Organisation nicht für Microsoft Manage Desktop-Geräte oder -Benutzer bestimmt sind. Weisen Sie kein PowerShell-Skript für alle Benutzer, alle Geräte oder beides zu. Ändern Sie die Richtlinie so, dass eine Zuweisung für eine bestimmte Azure AD-Gruppe verwendet wird, die keine Microsoft Managed Desktop-Geräte oder -Benutzer enthält. Weitere Informationen finden Sie unter [Verwenden von PowerShell-Skripts auf Windows 10-Geräten in Intune.](https://docs.microsoft.com/mem/intune/apps/intune-management-extension)

### <a name="region"></a>Region

Ihre Region muss von Microsoft Managed Desktop unterstützt werden.

**Nicht bereit**

Ihre Azure AD-Organisationsregion wird derzeit nicht von Microsoft Managed Desktop unterstützt. Weitere Informationen finden Sie unter [Von Microsoft Managed Desktop unterstützte Regionen und Sprachen.](../service-description/regions-languages.md)

**Empfehlung**

Mindestens eines der Länder, in denen sich Ihre Azure AD-Organisation befindet, wird von Microsoft Managed Desktop nicht unterstützt. Weitere Informationen finden Sie unter [von Microsoft Managed Desktop unterstützte Regionen und Sprachen.](../service-description/regions-languages.md)


### <a name="security-baselines"></a>Sicherheitsgrundwerte

Sicherheitsgrundlinienrichtlinien sollten nicht auf Microsoft Managed Desktop-Geräte ausgerichtet sein.

**Nicht bereit**

Sie verfügen über ein Sicherheitsgrundprofil, das auf alle Benutzer, alle Geräte oder beides ausgerichtet ist. Ändern Sie die Richtlinie so, dass eine Zuweisung für eine bestimmte Azure AD-Gruppe verwendet wird, die keine Microsoft Managed Desktop-Geräte enthält. Die Schritte finden Sie unter [Verwenden von Sicherheitsgrundwerten zum Konfigurieren von Windows 10-Geräten in Intune.](https://docs.microsoft.com/mem/intune/protect/security-baselines)

**Empfehlung**

Stellen Sie sicher, dass alle Sicherheitsgrundlinienrichtlinien, die Sie von Microsoft Managed Desktop ausgeschlossen haben, ausgeschlossen sind. Die Schritte finden Sie unter [Verwenden von Sicherheitsgrundwerten zum Konfigurieren von Windows 10-Geräten in Intune.](https://docs.microsoft.com/mem/intune/protect/security-baselines) The **Modern Workplace Devices -All** Azure AD group is a dynamic group that we create when you enroll in Microsoft Managed Desktop, so you'll have to come back to exclude this group after enrollment.


### <a name="windows-apps"></a>Windows-Apps

Überprüfen Sie die Apps, die Ihre Microsoft Managed Desktop-Benutzer haben möchten.

**Empfehlung**

Sie sollten eine Bestandsaufnahme der Apps vorbereiten, die Ihre Microsoft Managed Desktop-Benutzer haben sollen. Da diese Apps von Intune bereitgestellt werden müssen, sollten Sie die Reusing vorhandener Intune-Apps auswerten. Erwägen Sie die Verwendung des Unternehmensportals (siehe ["Installieren des Intune-Unternehmensportals auf Geräten und](https://docs.microsoft.com/microsoft-365/managed-desktop/get-started/company-portal) der Seite "Registrierungsstatus" (Enrollment Status Page, ESP), um Apps an Ihre Benutzer zu verteilen. Weitere Informationen finden Sie unter ["Apps in Microsoft Managed Desktop"](apps.md) und "Erste Ausführung" mit Autopilot und [auf der Seite "Registrierungsstatus".](https://docs.microsoft.com/microsoft-365/managed-desktop/get-started/esp-first-run)

Sie können Ihren Vertreter Ihres Microsoft-Kontos um eine Abfrage in Microsoft Endpoint Configuration Manager bitten, die Apps zu identifizieren, die zu Intune migriert werden können oder anpassungen erforderlich sind.


### <a name="windows-hello-for-business"></a>Windows Hello for Business

Microsoft Managed Desktop erfordert, dass Windows Hello for Business aktiviert ist.

**Nicht bereit**

Windows Hello for Business ist deaktiviert. Aktivieren Sie dies, indem Sie die Schritte unter ["Erstellen einer Windows Hello for Business-Richtlinie" ausführen.](https://docs.microsoft.com/mem/intune/protect/windows-hello#create-a-windows-hello-for-business-policy)

**Empfehlung**

Windows Hello for Business ist nicht eingerichtet. Aktivieren Sie dies, indem Sie die Schritte unter ["Erstellen einer Windows Hello for Business-Richtlinie" ausführen.](https://docs.microsoft.com/mem/intune/protect/windows-hello#create-a-windows-hello-for-business-policy)


### <a name="windows-10-update-rings"></a>Windows 10-Updateringe

Ihre Richtlinie "Windows 10-Updatering" in Intune darf nicht für Microsoft Managed Desktop-Geräte verwendet werden.

**Nicht bereit**

Sie verfügen über eine "Updatering"-Richtlinie, die auf alle Geräte, alle Benutzer oder beides zielt. Ändern Sie die Richtlinie so, dass eine Zuweisung für eine bestimmte Azure AD-Gruppe verwendet wird, die keine Microsoft Managed Desktop-Geräte enthält. Die Schritte finden Sie unter [Verwalten von Windows 10-Softwareupdates in Intune.](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure)

**Empfehlung**

Stellen Sie sicher, dass alle Updateringrichtlinien, die Sie eingerichtet haben, die **Gruppe "Moderne Arbeitsplatzgeräte – Alle** Azure AD"-Gruppen ausschließen. Wenn Sie diesen Richtlinien Azure AD-Benutzergruppen zugewiesen haben, stellen Sie sicher, dass alle Updateringrichtlinien, die Sie ebenfalls ausgeschlossen haben, die Moderne **Workplace -Alle** Azure AD-Gruppe, der Sie Ihre Microsoft Managed Desktop-Benutzer hinzufügen (oder einer entsprechenden Gruppe) hinzugefügt haben. Die Schritte finden Sie unter [Verwalten von Windows 10-Softwareupdates in Intune.](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure) Sowohl die modernen Arbeitsplatzgeräte **–Alle** als auch alle modernen Workplace **-Alle** Azure AD-Gruppen sind Gruppen, die wir erstellen, wenn Sie sich bei Microsoft Managed Desktop registrieren. Daher müssen Sie nach der Registrierung zurückkommen, um diese Gruppe auszuschließen.


## <a name="azure-active-directory-settings"></a>Azure Active Directory-Einstellungen

Sie können auf Azure Active Directory-Einstellungen im [Azure-Portal zugreifen.](https://portal.azure.com)

### <a name="intune-enrollment"></a>Registrierung in Intune

Windows 10-Geräte in Ihrer Azure AD-Organisation müssen in der Lage sein, sich automatisch bei Intune zu registrieren.

**Empfehlung**

Stellen Sie sicher, dass der **Bereich "MDM-Benutzer"** auf **"Some"** oder **"All"** und nicht auf **"None" festgelegt ist.** Wenn Sie **"Einige"** auswählen, kommen Sie nach der Registrierung  zurück und wählen Sie die Moderne Workplace **-Alle** Azure AD-Gruppe für Gruppen oder eine entsprechende Gruppe für alle Benutzer von Microsoft Managed Desktop aus.  Siehe ["Einrichten der Registrierung für Windows-Geräte mithilfe von Microsoft Intune".](https://docs.microsoft.com/mem/intune/enrollment/windows-enroll#enable-windows-10-automatic-enrollment)


### <a name="ad-hoc-subscriptions"></a>Ad-hoc-Abonnements

Empfiehlt, eine Einstellung zu überprüfen, die (bei Festlegung auf "false") möglicherweise verhindert, dass Enterprise State Roaming ordnungsgemäß funktioniert.

**Empfehlung**

Stellen Sie **sicher, dass AllowAdHocSubscriptions** auf **"True" festgelegt ist.** Andernfalls funktioniert Enterprise State Roaming möglicherweise nicht. Weitere Informationen finden Sie unter [Set-MsolCompanySettings](https://docs.microsoft.com/powershell/module/msonline/set-msolcompanysettings?view=azureadps-1.0).


### <a name="enterprise-state-roaming"></a>Enterprise State Roaming

Enterprise State Roaming sollte aktiviert sein.

**Empfehlung**

Stellen Sie sicher, dass Enterprise State Roaming für **alle oder** für ausgewählte **Gruppen aktiviert** ist. Weitere Informationen finden Sie unter [Aktivieren von Enterprise State Roaming in Azure Active Directory.](https://docs.microsoft.com/azure/active-directory/devices/enterprise-state-roaming-enable)

### <a name="licenses"></a>Lizenzen

Für die Verwendung von Microsoft Managed Desktop sind eine Reihe von Lizenzen erforderlich.

**Nicht bereit**

Sie verfügen nicht über alle Lizenzen, die Sie für die Verwendung von Microsoft Managed Desktop benötigen. Weitere Informationen finden Sie unter [Microsoft Managed Desktop-Technologien](../intro/technologies.md) und [weitere Informationen zu Lizenzen.](prerequisites.md#more-about-licenses)


### <a name="security-account-names"></a>Namen von Sicherheitskontos

Bestimmte Sicherheitskontonamen können mit von Microsoft Managed Desktop erstellten Namen in Konflikt stehen.

**Nicht bereit**

Sie verfügen über mindestens einen Kontonamen, der mit den von Microsoft Managed Desktop erstellten Namen in Konflikt steht. Arbeiten Sie mit Ihrem Microsoft-Kontomitarbeiter zusammen, um diese Kontonamen auszuschließen.


### <a name="security-administrator-roles"></a>Sicherheitsadministratorrollen

Benutzern mit bestimmten Sicherheitsrollen müssen diese Rollen in Microsoft Defender for Endpoint zugewiesen sein.

**Empfehlung**

Wenn Sie Benutzern eine dieser Rollen in Ihrer Azure AD-Organisation zugewiesen haben, stellen Sie sicher, dass ihnen auch diese Rollen in Microsoft Defender for Endpoint zugewiesen sind. Andernfalls können Administratoren mit diesen Rollen nicht auf das Verwaltungsportal zugreifen.

- Sicherheitsoperator
- Globaler Leser

Weitere Informationen finden Sie unter ["Erstellen und Verwalten von Rollen für die rollenbasierte Zugriffssteuerung".](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/user-roles)


### <a name="security-default"></a>Standardsicherheit

Sicherheitseinstellungen in Azure Active Directory verhindern, dass Microsoft Managed Desktop Ihre Geräte verwaltet.

**Nicht bereit**

Die Sicherheitseinstellungen sind aktiviert. Deaktivieren Sie die Sicherheitseinstellungen, und richten Sie Richtlinien für bedingten Zugriff ein. Weitere Informationen finden Sie unter ["Allgemeine Richtlinien für bedingten Zugriff".](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-policy-common)

### <a name="self-service-password-reset"></a>Self-Service-Kennwortzurücksetzung

Die Self-Service-Kennwortzurücksetzung (Self-Service Password Reset, SSPR) kann für alle Benutzer von Microsoft Managed Desktop aktiviert werden, mit Ausnahme von Microsoft Managed Desktop-Dienstkonten. Weitere Informationen finden Sie im [Lernprogramm:](https://docs.microsoft.com/azure/active-directory/authentication/tutorial-enable-sspr)Ermöglichen Sie Benutzern das Entsperren ihres Kontos oder das Zurücksetzen von Kennwörtern mithilfe der Self-Service-Kennwortzurücksetzung in Azure Active Directory.

**Empfehlung**

Stellen Sie sicher, dass die Einstellung "SSPR **Selected"** Microsoft Managed Desktop-Benutzer enthält, aber Microsoft Managed Desktop-Dienstkonten ausschließt. Microsoft Managed Desktop -Dienstkonten können nicht wie erwartet funktionieren, wenn SSPR aktiviert ist.  


### <a name="standard-user-role"></a>Standardbenutzerrolle

Mit anderen Benutzern als den Benutzern, denen Azure AD-Rollen des globalen Administrators und Geräteadministrators zugewiesen sind, sind Microsoft Managed Desktop-Benutzer Standardbenutzer ohne lokale Administratorrechte. Allen anderen Benutzern wird eine Standardbenutzerrolle zugewiesen, wenn sie ihr Microsoft Managed Desktop-Gerät starten.

**Empfehlung**

Microsoft Managed Desktop-Benutzer verfügen nach der Registrierung nicht über lokale Administratorrechte auf ihren Microsoft Managed Desktop-Geräten.

## <a name="microsoft-365-apps-for-enterprise"></a>Microsoft 365 Apps for Enterprise

### <a name="onedrive"></a>OneDrive

Die **Einstellung "Synchronisierung nur auf PCs** zulassen, die einer bestimmten Domäneneinstellung beigetreten sind" ist mit Microsoft Managed Desktop in Konflikt. Sie können im OneDrive Admin Center auf [#A0 zugreifen.](https://admin.onedrive.com)

**Empfehlung**

Sie verwenden die Einstellung "Synchronisierung zulassen" nur auf **PCs, die mit bestimmten Domänen verbunden** sind. Diese Einstellung funktioniert nicht mit Microsoft Managed Desktop. Deaktivieren Sie diese Einstellung, und richten Sie stattdessen OneDrive für die Verwendung einer Richtlinie für bedingten Zugriff ein. Hilfe [finden Sie unter "Planen einer Bereitstellung für bedingten](https://docs.microsoft.com/azure/active-directory/conditional-access/plan-conditional-access) Zugriff".

