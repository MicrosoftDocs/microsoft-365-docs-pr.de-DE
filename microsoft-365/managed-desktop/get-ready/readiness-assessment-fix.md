---
title: Lösen von Problemen, die durch das Tool zur Bereitschaftsbewertung gefunden wurden
description: Detaillierte Maßnahmen für jedes vom Tool gefundene Problem
keywords: Microsoft Managed Desktop, Microsoft 365, Dienst, Dokumentation
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
audience: Admin
ms.openlocfilehash: 0296e8151162ad4f2855fdd29ff2fc0ed4b4d6b2
ms.sourcegitcommit: cfd7644570831ceb7f57c61401df6a0001ef0a6a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/29/2021
ms.locfileid: "53177573"
---
# <a name="fix-issues-found-by-the-readiness-assessment-tool"></a>Lösen von Problemen, die durch das Tool zur Bereitschaftsbewertung gefunden wurden

Für jede Überprüfung meldet das Tool eines von vier möglichen Ergebnissen:


|Ergebnis  |Bedeutung  |
|---------|---------|
|Bereit     | Vor Abschluss der Registrierung ist keine Aktion erforderlich.        |
|Empfehlung    | Führen Sie die Schritte im Tool oder in diesem Artikel aus, um die beste Erfahrung mit der Registrierung und für Benutzer zu erzielen. Sie *können* die Registrierung abschließen, aber Sie müssen diese Probleme beheben, bevor Sie Ihr erstes Gerät bereitstellen.        |
|Nicht bereit | *Die Registrierung schlägt fehl, wenn Sie diese Probleme nicht beheben.* Führen Sie die Schritte im Tool oder in diesem Artikel aus, um sie zu beheben.        |
|Fehler (ungefährer Wortlaut) | Die Azure Active Directory (AD)-Rolle, die Sie verwenden, verfügt nicht über ausreichende Berechtigungen, um diese Überprüfung auszuführen. |

> [!NOTE]
> Die von diesem Tool gemeldeten Ergebnisse geben den Status Ihrer Einstellungen nur zu dem bestimmten Zeitpunkt wieder, zu dem Sie es ausgeführt haben. Wenn Sie später Änderungen an Richtlinien in Microsoft Intune, Azure Active Directory oder Microsoft 365 vornehmen, können Elemente, die "Bereit" waren, "Nicht bereit" werden. Um Probleme mit Microsoft Managed Desktop Vorgängen zu vermeiden, überprüfen Sie die in diesem Artikel beschriebenen spezifischen Einstellungen, bevor Sie Richtlinien ändern.

## <a name="microsoft-intune-settings"></a>Microsoft Intune Einstellungen

Sie können im Microsoft Endpoint Manager [Admin Center](https://endpoint.microsoft.com)auf Intune-Einstellungen zugreifen.

### <a name="autopilot-deployment-profile"></a>Autopilot-Bereitstellungsprofil

Sie sollten keine vorhandenen Autopilot-Profile haben, die auf zugewiesene oder dynamische Gruppen mit Microsoft Managed Desktop Geräten abzielen. Microsoft Managed Desktop verwendet Autopilot, um neue Geräte bereitzustellen.

**Nicht bereit**

Sie verfügen über ein Autopilot-Profil, das allen Geräten zugewiesen ist. Schritte finden Sie unter [Registrieren Windows Geräte in Intune mithilfe von Windows Autopilot.](/mem/autopilot/enrollment-autopilot) Legen Sie nach Microsoft Managed Desktop Registrierung Ihre Autopilot-Richtlinie fest, um die Gruppe **"Moderne Workplace-Geräte – Alle** Azure AD"-Gruppen auszuschließen.

**Empfehlung**

Stellen Sie sicher, dass Ihre Autopilot-Profile auf eine zugewiesene oder dynamische Azure AD-Gruppe abzielen, die keine Microsoft Managed Desktop Geräte enthält. Schritte finden Sie unter [Registrieren Windows Geräte in Intune mithilfe von Windows Autopilot.](/mem/autopilot/enrollment-autopilot) Legen Sie nach Microsoft Managed Desktop Registrierung Ihre Autopilot-Profile so fest, dass die Gruppe **"Moderne Workplace-Geräte – Alle** Azure AD"-Gruppen ausgeschlossen wird.


### <a name="certificate-connectors"></a>Zertifikatconnectors

Wenn Sie über Zertifikatconnectors verfügen, die von den Geräten verwendet werden, die Sie für Microsoft Managed Desktop registrieren möchten, sollten die Connectors keine Fehler aufweisen. Nur einer der folgenden Empfehlungen gilt für Ihre Situation. Überprüfen Sie diese daher sorgfältig.

**Empfehlung**

Es sind keine Zertifikatconnectors vorhanden. Es ist möglich, dass Sie keine Connectors benötigen, aber Sie sollten prüfen, ob Sie möglicherweise einige für die Netzwerkkonnektivität auf Ihren Microsoft Managed Desktop Geräten benötigen. Weitere Informationen finden Sie unter [Vorbereiten von Zertifikaten und Netzwerkprofilen für Microsoft Managed Desktop.](certs-wifi-lan.md)

**Empfehlung**

Mindestens ein Zertifikatconnector weist einen Fehler auf. Wenn Sie diesen Connector zum Bereitstellen von Zertifikaten für Microsoft Managed Desktop Geräte benötigen, müssen Sie den Fehler beheben. Weitere Informationen finden Sie unter [Vorbereiten von Zertifikaten und Netzwerkprofilen für Microsoft Managed Desktop.](certs-wifi-lan.md)


**Empfehlung**

Sie verfügen über mindestens einen Zertifikatconnector, und es werden keine Fehler gemeldet. In Vorbereitung auf die Bereitstellung müssen Sie jedoch möglicherweise ein Profil erstellen, um den Connector für Microsoft Managed Desktop Geräte wiederzuverwenden. Weitere Informationen finden Sie unter [Vorbereiten von Zertifikaten und Netzwerkprofilen für Microsoft Managed Desktop.](certs-wifi-lan.md)

### <a name="company-portal"></a>Unternehmensportal

Microsoft Managed Desktop erfordert, dass IT-Administratoren Intune-Unternehmensportal für ihre Benutzer mit Microsoft Managed Desktop Geräten installieren. 

**Nicht bereit**

Sie haben keine Unternehmensportal für Ihre Benutzer installiert. Erwerben Sie Unternehmensportal und erzwingen Sie eine Synchronisierung zwischen Intune und Microsoft Store für Unternehmen. Weitere Informationen finden Sie unter [Installieren Intune-Unternehmensportal auf Geräten.](../get-started/company-portal.md)


### <a name="conditional-access-policies"></a>Richtlinien für bedingten Zugriff

Richtlinien für bedingten Zugriff dürfen Microsoft Managed Desktop nicht daran hindern, Ihre Azure AD-Organisation (Mandant) in Intune und Azure AD zu verwalten.

**Nicht bereit**

Sie verfügen über mindestens eine Richtlinie für bedingten Zugriff, die auf alle Benutzer ausgerichtet ist. Während der Registrierung schließen wir Microsoft Managed Desktop Dienstkonten von relevanten Richtlinien für bedingten Zugriff aus und wenden neue Richtlinien für bedingten Zugriff an, um den Zugriff auf diese Konten einzuschränken. Nach der Registrierung können Sie die Microsoft Managed Desktop Richtlinie für bedingten Zugriff in Microsoft Endpoint Manager überprüfen. Weitere Informationen zu diesen Dienstkonten finden Sie unter [Standardvorgehensweisen.](../service-description/operations-and-monitoring.md#standard-operating-procedures)

**Empfehlung**

Sie verfügen über Richtlinien für bedingten Zugriff, die verhindern können, dass Microsoft Managed Desktop den Microsoft Managed Desktop Dienst verwalten. Während der Registrierung schließen wir Microsoft Managed Desktop Dienstkonten von relevanten Richtlinien für bedingten Zugriff aus und wenden neue Richtlinien für bedingten Zugriff an, um den Zugriff auf diese Konten einzuschränken. Weitere Informationen zu diesen Dienstkonten finden Sie unter [Standardvorgehensweisen.](../service-description/operations-and-monitoring.md#standard-operating-procedures)

**Error**

Die Intune-Administratorrolle verfügt nicht über ausreichende Berechtigungen für diese Überprüfung. Sie benötigen auch eine der folgenden Azure AD-Rollen, um diese Überprüfung auszuführen:

- Sicherheitsleseberechtigter
- Sicherheitsadministrator
- Administrator für bedingten Zugriff
- Globaler Leser
- Geräteadministrator


### <a name="device-compliance-policies"></a>Gerätekompatibilitätsrichtlinien

Intune Device Compliance-Richtlinien in Ihrer Azure AD-Organisation können sich auf Microsoft Managed Desktop Geräte auswirken.

**Nicht bereit**

Sie verfügen über mindestens eine Compliancerichtlinie, die auf alle Benutzer ausgerichtet ist. Microsoft Managed Desktop enthält Compliancerichtlinien, die auf Ihre Microsoft Managed Desktop-Geräte ausgerichtet sind.  Ändern Sie die Richtlinie so, dass sie auf eine bestimmte Azure AD-Gruppe ausgerichtet ist, die keine Microsoft Managed Desktop Benutzer oder Geräte enthält. Schritte finden Sie unter [Erstellen einer Compliancerichtlinie in Microsoft Intune.](/mem/intune/protect/create-compliance-policy)

**Empfehlung**

Stellen Sie sicher, dass alle Compliancerichtlinien, die Sie haben, nicht für Microsoft Managed Desktop Benutzer bestimmt sind. Schritte finden Sie unter [Erstellen einer Compliancerichtlinie in Microsoft Intune.](/mem/intune/protect/create-compliance-policy)



### <a name="device-configuration-profiles"></a>Gerätekonfigurationsprofile

Intune-Gerätekonfigurationsprofile in Ihrer Azure AD-Organisation dürfen nicht auf Microsoft Manage Desktop-Geräte oder -Benutzer ausgerichtet sein.

**Nicht bereit**

Sie verfügen über mindestens ein Konfigurationsprofil, das auf alle Benutzer, alle Geräte oder beides ausgerichtet ist. Setzen Sie das Profil auf eine bestimmte Azure AD-Gruppe zurück, die keine Microsoft Managed Desktop Geräte enthält. Schritte finden Sie unter [Erstellen eines Profils mit benutzerdefinierten Einstellungen in Microsoft Intune.](/mem/intune/configuration/custom-settings-configure)

**Empfehlung**

Stellen Sie sicher, dass alle Konfigurationsrichtlinien, die Sie haben, keine Microsoft Managed Desktop Geräte oder Benutzer enthalten. Schritte finden Sie unter [Erstellen eines Profils mit benutzerdefinierten Einstellungen in Microsoft Intune.](/mem/intune/configuration/custom-settings-configure)



### <a name="device-type-restrictions"></a>Einschränkungen für Gerätetypen

Microsoft Managed Desktop Geräte müssen in Intune registriert werden dürfen.

**Nicht bereit**

Sie haben derzeit mindestens eine Registrierungseinschränkungsrichtlinie konfiguriert, um zu verhindern, dass Windows Geräte in Intune registriert werden. Führen Sie die Schritte unter [Festlegen von Registrierungseinschränkungen](/mem/intune/enrollment/enrollment-restrictions-set) für jede Registrierungseinschränkungsrichtlinie aus, die auf Microsoft Managed Desktop Benutzer ausgerichtet ist, und ändern Sie die Einstellung **Windows (MDM)** in **"Zulassen".** Sie können jedoch alle **persönlichen** **Windows (MDM)-Geräte** auf **"Blockieren"** festlegen. 


### <a name="enrollment-status-page"></a>Registrierungsstatusseite

Sie haben derzeit die Registrierungsstatusseite (ESP) aktiviert. Wenn Sie beabsichtigen, an der Microsoft Managed Desktop öffentlichen Vorschau dieses Features teilzunehmen, können Sie dieses Element ignorieren. Weitere Informationen finden Sie unter ["Erste Ausführung" mit Autopilot und auf der Seite "Registrierungsstatus".](../get-started/esp-first-run.md)

**Nicht bereit**

You have the ESP default profile set to **Show app and profile configuration progress**. Deaktivieren Sie diese Einstellung, oder stellen Sie sicher, dass Zuweisungen zu einer Azure AD-Gruppe keine Microsoft Managed Desktop Geräte enthalten, indem Sie die Schritte unter ["Einrichten der Registrierungsstatusseite"](/mem/intune/enrollment/windows-enrollment-status)ausführen.

**Empfehlung**

Stellen Sie sicher, dass alle Profile mit der Statuseinstellung **"App anzeigen" und "Profilkonfiguration"** keiner Azure AD-Gruppe zugewiesen sind, die Microsoft Managed Desktop Geräte enthält. Weitere Informationen finden Sie unter [Einrichten der Registrierungsstatusseite.](/mem/intune/enrollment/windows-enrollment-status)

### <a name="microsoft-store-for-business"></a>Microsoft Store für Unternehmen

Wir verwenden Microsoft Store für Unternehmen und stellen die Unternehmensportal-App auf Microsoft Managed Desktop bereit, damit Benutzer optional einige Apps installieren können, z. B. Microsoft Project und Microsoft Visio (sofern zulässig).

**Nicht bereit**

Microsoft Store für Unternehmen ist entweder nicht aktiviert oder wird nicht mit Intune synchronisiert. Weitere Informationen finden Sie unter Verwalten von [Volumen-Apps aus dem Microsoft Store für Unternehmen mit Microsoft Intune](/mem/intune/apps/windows-store-for-business) und Installieren von Intune-Unternehmensportal auf [Geräten.](../get-started/company-portal.md)

### <a name="multifactor-authentication"></a>Mehrstufige Authentifizierung

Die mehrstufige Authentifizierung darf Microsoft Managed Desktop nicht daran hindern, Ihre Azure AD-Organisation (Mandant) in Intune und Azure AD zu verwalten.


**Nicht bereit**

Sie haben einige mehrstufige Authentifizierungsrichtlinien als **erforderlich** für Richtlinien für bedingten Zugriff festgelegt, die allen Benutzern zugewiesen sind. Während der Registrierung schließen wir Microsoft Managed Desktop Dienstkonten von relevanten Richtlinien für bedingten Zugriff aus und wenden neue Richtlinien für bedingten Zugriff an, um den Zugriff auf diese Konten einzuschränken. Weitere Informationen zu diesen Dienstkonten finden Sie unter [Standardvorgehensweisen.](../service-description/operations-and-monitoring.md#standard-operating-procedures)

**Empfehlung**

Für Richtlinien für bedingten Zugriff ist eine mehrstufige Authentifizierung erforderlich, die verhindern könnte, dass Microsoft Managed Desktop den Microsoft Managed Desktop Dienst verwalten. Während der Registrierung schließen wir Microsoft Managed Desktop Dienstkonten von relevanten Richtlinien für bedingten Zugriff aus und wenden neue Richtlinien für bedingten Zugriff an, um den Zugriff auf diese Konten einzuschränken. Weitere Informationen zu diesen Dienstkonten finden Sie unter [Standardvorgehensweisen.](../service-description/operations-and-monitoring.md#standard-operating-procedures)

**Error**

Die Intune-Administratorrolle verfügt nicht über ausreichende Berechtigungen für diese Überprüfung. Sie benötigen auch eine der folgenden Azure AD-Rollen, um diese Überprüfung auszuführen:

- Sicherheitsleseberechtigter
- Sicherheitsadministrator
- Administrator für bedingten Zugriff
- Globaler Leser
- Geräteadministrator


### <a name="powershell-scripts"></a>PowerShell-Skripts

Windows PowerShell Skripts können nicht auf eine Weise zugewiesen werden, die auf Microsoft Managed Desktop Geräte ausgerichtet wäre.  

**Empfehlung**

Stellen Sie sicher, dass Windows PowerShell Skripts in Ihrer Azure AD-Organisation nicht auf Microsoft Manage Desktop-Geräte oder -Benutzer ausgerichtet sind. Weisen Sie kein PowerShell-Skript für alle Benutzer, alle Geräte oder beides zu. Ändern Sie die Richtlinie so, dass eine Zuordnung verwendet wird, die auf eine bestimmte Azure AD-Gruppe ausgerichtet ist, die keine Microsoft Managed Desktop Geräte oder Benutzer enthält. Weitere Informationen finden Sie unter [Verwenden von PowerShell-Skripts auf Windows 10 Geräten in Intune.](/mem/intune/apps/intune-management-extension)

### <a name="region"></a>Region

Ihre Region muss von Microsoft Managed Desktop unterstützt werden.

**Nicht bereit**

Ihre Azure AD-Organisationsregion wird derzeit nicht von Microsoft Managed Desktop unterstützt. Weitere Informationen finden Sie unter [Microsoft Managed Desktop unterstützten Regionen und Sprachen.](../service-description/regions-languages.md)

**Empfehlung**

Mindestens eines der Länder, in denen sich Ihre Azure AD-Organisation befindet, wird von Microsoft Managed Desktop nicht unterstützt. Weitere Informationen finden Sie unter [Microsoft Managed Desktop unterstützten Regionen und Sprachen.](../service-description/regions-languages.md)


### <a name="security-baselines"></a>Sicherheitsgrundwerte

Richtlinien für Sicherheitsgrundwerte sollten nicht auf Microsoft Managed Desktop Geräte ausgerichtet sein.

**Nicht bereit**

Sie verfügen über ein Sicherheitsbaselineprofil, das auf alle Benutzer, alle Geräte oder beides ausgerichtet ist. Ändern Sie die Richtlinie so, dass eine Zuordnung verwendet wird, die auf eine bestimmte Azure AD-Gruppe ausgerichtet ist, die keine Microsoft Managed Desktop Geräte enthält. Schritte finden Sie unter [Verwenden von Sicherheitsgrundwerten zum Konfigurieren Windows 10 Geräte in Intune.](/mem/intune/protect/security-baselines) Während der Registrierung wenden wir eine neue Sicherheitsgrundlinie auf alle Microsoft Managed Desktop Geräte an. Nach der Registrierung können Sie die Richtlinie für Microsoft Managed Desktop Sicherheitsgrundwerte im Bereich der **Konfigurationsrichtlinien** von Microsoft Endpoint Manager überprüfen.

**Empfehlung**

Stellen Sie sicher, dass alle Sicherheitsgrundwerterichtlinien, die Sie Microsoft Managed Desktop Geräten ausgeschlossen haben. Schritte finden Sie unter [Verwenden von Sicherheitsgrundwerten zum Konfigurieren Windows 10 Geräte in Intune.](/mem/intune/protect/security-baselines) Während der Registrierung wenden wir eine neue Sicherheitsgrundlinie auf alle Microsoft Managed Desktop Geräte an. Die **Gruppe "Moderne Workplace-Geräte – Alle** Azure AD-Gruppen" ist eine dynamische Gruppe, die wir erstellen, wenn Sie sich bei Microsoft Managed Desktop registrieren. Sie müssen daher zurückkehren, um diese Gruppe nach der Registrierung auszuschließen. 


### <a name="windows-apps"></a>Windows-Apps

Überprüfen Sie Apps, die Ihre Microsoft Managed Desktop Benutzer haben sollen.

**Empfehlung**

Sie sollten eine Bestandsaufnahme der Apps vorbereiten, über die Ihre Microsoft Managed Desktop Benutzer verfügen sollen. Da diese Apps von Intune bereitgestellt werden müssen, sollten Sie die Wiederverwendung vorhandener Intune-Apps auswerten. Erwägen Sie die Verwendung von Unternehmensportal (siehe [Installieren von Intune-Unternehmensportal auf Geräten](../get-started/company-portal.md) und der Registrierungsstatusseite (ESP), um Apps an Ihre Benutzer zu verteilen. Weitere Informationen finden Sie unter ["Apps in Microsoft Managed Desktop"](apps.md) und ["Erste Ausführung" mit Autopilot und der Seite "Registrierungsstatus".](../get-started/esp-first-run.md)

Sie können Ihren Microsoft-Kontomitarbeiter um eine Abfrage in Microsoft Endpoint Configuration Manager bitten, um die Apps zu identifizieren, die zur Migration zu Intune bereit sind oder anpassungsfähig sind.


### <a name="windows-hello-for-business"></a>Windows Hello for Business

Microsoft Managed Desktop erfordert, dass Windows Hello for Business aktiviert ist.

**Nicht bereit**

Windows Hello für Unternehmen ist deaktiviert. Aktivieren Sie dies, indem Sie die Schritte unter ["Erstellen einer Windows Hello for Business-Richtlinie"](/mem/intune/protect/windows-hello#create-a-windows-hello-for-business-policy) ausführen.

**Empfehlung**

Windows Hello für Unternehmen ist nicht eingerichtet. Aktivieren Sie dies, indem Sie die Schritte unter [Erstellen einer Windows Hello for Business-Richtlinie](/mem/intune/protect/windows-hello#create-a-windows-hello-for-business-policy)ausführen.


### <a name="windows-10-update-rings"></a>Windows 10 Updateringe

Ihre Richtlinie "Windows 10 Updatering" in Intune darf nicht auf Microsoft Managed Desktop Geräte ausgerichtet sein.

**Nicht bereit**

Sie verfügen über eine "Updatering"-Richtlinie, die auf alle Geräte, alle Benutzer oder beides ausgerichtet ist. Ändern Sie die Richtlinie so, dass eine Zuordnung verwendet wird, die auf eine bestimmte Azure AD-Gruppe ausgerichtet ist, die keine Microsoft Managed Desktop Geräte enthält. Schritte finden Sie unter [Verwalten Windows 10 Softwareupdates in Intune.](/mem/intune/protect/windows-update-for-business-configure)

**Empfehlung**

Stellen Sie sicher, dass alle Updateringrichtlinien, die Sie aus der Gruppe **"Modern Workplace Devices - Alle** Azure AD" ausgeschlossen haben. Wenn Sie diesen Richtlinien Azure AD-Benutzergruppen zugewiesen haben, stellen Sie sicher, dass alle Updateringrichtlinien, die Sie ebenfalls aus der **Gruppe "Moderner Arbeitsplatz – Alle** Azure AD" ausgeschlossen haben, der Sie Ihre Microsoft Managed Desktop Benutzer hinzufügen (oder einer entsprechenden Gruppe). Schritte finden Sie unter [Verwalten Windows 10 Softwareupdates in Intune.](/mem/intune/protect/windows-update-for-business-configure) Sowohl die **Modern Workplace Devices -All** and **Modern Workplace -All** Azure AD groups are groups that we create when you enroll in Microsoft Managed Desktop, so you'll have to come back to exclude this group after enrollment.


## <a name="azure-active-directory-settings"></a>Azure Active Directory Einstellungen

Sie können im [Azure-Portal](https://portal.azure.com)auf Azure Active Directory Einstellungen zugreifen.

### <a name="intune-enrollment"></a>Intune-Registrierung

Windows 10 Geräte in Ihrer Azure AD-Organisation müssen automatisch in Intune registriert werden können.

**Empfehlung**

Stellen Sie sicher, dass der **MDM-Benutzerbereich** auf **"Some"** oder **"All"** und nicht **"None"** festgelegt ist. Wenn Sie **"Einige"** auswählen, kehren Sie nach der Registrierung zurück und wählen Sie die Gruppe **"Modern Workplace -All** Azure AD" für **Gruppen** oder eine entsprechende Gruppe für alle Ihre Microsoft Managed Desktop Benutzer aus.  Weitere Informationen finden [Sie unter Einrichten der Registrierung für Windows Geräte mithilfe von Microsoft Intune.](/mem/intune/enrollment/windows-enroll#enable-windows-10-automatic-enrollment)


### <a name="ad-hoc-subscriptions"></a>Ad-hoc-Abonnements

Gibt an, wie Sie eine Einstellung überprüfen, die (bei Festlegung auf "false") möglicherweise verhindert, dass Enterprise Statusroaming ordnungsgemäß funktioniert.

**Empfehlung**

Stellen Sie sicher, dass **AllowAdHocSubscriptions** auf **True** festgelegt ist. Andernfalls funktioniert Enterprise Statusroaming möglicherweise nicht. Weitere Informationen finden Sie unter ["Set-MsolCompanySettings".](/powershell/module/msonline/set-msolcompanysettings?view=azureadps-1.0)


### <a name="enterprise-state-roaming"></a>Enterprise State Roaming

Enterprise Statusroaming sollte aktiviert sein.

**Empfehlung**

Stellen Sie sicher, dass Enterprise Statusroaming für **alle** oder für **ausgewählte** Gruppen aktiviert ist. Weitere Informationen finden Sie unter [Aktivieren Enterprise Statusroaming in Azure Active Directory.](/azure/active-directory/devices/enterprise-state-roaming-enable)

### <a name="licenses"></a>Lizenzen

Für die Verwendung von Microsoft Managed Desktop sind eine Reihe von Lizenzen erforderlich.

**Nicht bereit**

Sie verfügen nicht über alle Lizenzen, die Sie benötigen, um Microsoft Managed Desktop zu verwenden. Weitere Informationen finden Sie unter [Microsoft Managed Desktop Technologien](../intro/technologies.md) und mehr [zu Lizenzen.](prerequisites.md#more-about-licenses)


### <a name="microsoft-managed-desktop-service-accounts"></a>Microsoft Managed Desktop-Dienstkonten

Bestimmte Kontonamen können mit Kontonamen in Konflikt geraten, die von Microsoft Managed Desktop zum Verwalten des Microsoft Managed Desktop Diensts erstellt wurden.

**Nicht bereit**

Sie haben mindestens einen Kontonamen, der mit den von Microsoft Managed Desktop erstellten Kontonamen in Konflikt stehen kann. Arbeiten Sie mit Ihrem Microsoft-Kontomitarbeiter, um diese Kontonamen auszuschließen. Wir listen die Kontonamen nicht öffentlich auf, um das Sicherheitsrisiko zu minimieren. 


### <a name="security-administrator-roles"></a>Sicherheitsadministratorrollen

Benutzer mit bestimmten Sicherheitsrollen müssen diese Rollen in Microsoft Defender für Endpunkt zugewiesen haben.

**Empfehlung**

Wenn Sie Benutzern eine dieser Rollen in Ihrer Azure AD-Organisation zugewiesen haben, stellen Sie sicher, dass ihnen auch diese Rollen in Microsoft Defender für Endpunkt zugewiesen sind. Andernfalls können Administratoren mit diesen Rollen nicht auf das Verwaltungsportal zugreifen.

- Sicherheitsoperator
- Globaler Leser

Weitere Informationen finden Sie unter [Erstellen und Verwalten von Rollen für die rollenbasierte Zugriffssteuerung.](/windows/security/threat-protection/microsoft-defender-atp/user-roles)


### <a name="security-default"></a>Standardsicherheit

Die Sicherheitsstandards in Azure Active Directory verhindern, dass Microsoft Managed Desktop Ihre Geräte verwalten.

**Nicht bereit**

Die Sicherheitsstandards sind aktiviert. Deaktivieren Sie die Sicherheitsstandards, und richten Sie Richtlinien für bedingten Zugriff ein. Weitere Informationen finden Sie unter [Allgemeine Richtlinien für bedingten Zugriff.](/azure/active-directory/conditional-access/concept-conditional-access-policy-common)

### <a name="self-service-password-reset"></a>Self-Service-Kennwortzurücksetzung

Self-Service Password Reset (SSPR) kann für alle Microsoft Managed Desktop Benutzer mit Ausnahme Microsoft Managed Desktop Dienstkonten aktiviert werden. Weitere Informationen finden Sie im [Lernprogramm: Ermöglichen Sie Benutzern, ihr Konto zu entsperren oder Kennwörter mit Azure Active Directory Self-Service-Kennwortzurücksetzung zurückzusetzen.](/azure/active-directory/authentication/tutorial-enable-sspr)

**Empfehlung**

Stellen Sie sicher, dass die Einstellung "SSPR **Selected"** Microsoft Managed Desktop Benutzer enthält, aber Microsoft Managed Desktop Dienstkonten ausschließt. Microsoft Managed Desktop Dienstkonten können nicht wie erwartet funktionieren, wenn SSPR aktiviert ist.  


### <a name="standard-user-role"></a>Standardbenutzerrolle

Abgesehen von den Benutzern, denen Azure AD-Rollen als globaler Administrator und Geräteadministrator zugewiesen sind, sind Microsoft Managed Desktop Benutzer Standardbenutzer ohne lokale Administratorrechte. Allen anderen Benutzern wird eine Standardbenutzerrolle zugewiesen, wenn sie ihr Microsoft Managed Desktop Gerät starten.

**Empfehlung**

Microsoft Managed Desktop Benutzer verfügen nach der Registrierung nicht über lokale Administratorrechte auf ihren Microsoft Managed Desktop Geräten.

## <a name="microsoft-365-apps-for-enterprise"></a>Microsoft 365 Apps for Enterprise

### <a name="onedrive"></a>OneDrive

Die Einstellung **"Synchronisierung nur auf PCs zulassen", die mit bestimmten Domänen verknüpft sind,** führt zu Einem Konflikt mit Microsoft Managed Desktop. Sie können im OneDrive [Admin Center](https://admin.onedrive.com)auf OneDrive Einstellungen zugreifen.

**Empfehlung**

Sie verwenden die Einstellung **"Synchronisierung nur auf PCs zulassen", die mit bestimmten Domänen verbunden** sind. Diese Einstellung funktioniert nicht mit Microsoft Managed Desktop. Deaktivieren Sie diese Einstellung, und richten Sie stattdessen OneDrive für die Verwendung einer Richtlinie für bedingten Zugriff ein. Hilfe finden Sie unter Planen einer Bereitstellung für [bedingten Zugriff.](/azure/active-directory/conditional-access/plan-conditional-access)
