---
title: Lösen von Problemen, die durch das Tool zur Bereitschaftsbewertung gefunden wurden
description: Detaillierte Aktionen für jedes gefundene Problem
keywords: Microsoft Managed Desktop, Microsoft 365, Dienst, Dokumentation
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 75c2967037ae83abca2aaa3cd02d1f6b2ae14caa
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50925916"
---
# <a name="fix-issues-found-by-the-readiness-assessment-tool"></a>Lösen von Problemen, die durch das Tool zur Bereitschaftsbewertung gefunden wurden

Für jede Prüfung berichtet das Tool eines von vier möglichen Ergebnissen:


|Ergebnis  |Bedeutung  |
|---------|---------|
|Bereit     | Vor Abschluss der Registrierung ist keine Aktion erforderlich.        |
|Empfehlung    | Führen Sie die Schritte im Tool oder in diesem Artikel aus, um eine optimale Erfahrung mit der Registrierung und für Benutzer zu erhalten. Sie *können* die Registrierung abschließen, aber Sie müssen diese Probleme beheben, bevor Sie Ihr erstes Gerät bereitstellen.        |
|Nicht bereit | *Wenn Sie diese Probleme nicht beheben, wird bei der Registrierung ein Fehler auftreten.* Führen Sie die Schritte im Tool oder in diesem Artikel aus, um sie zu beheben.        |
|Fehler | Die von Ihnen verwendeten Azure Active Directory (AD)-Rolle verfügt nicht über ausreichende Berechtigungen, um diese Überprüfung ausführen zu können. |

> [!NOTE]
> Die von diesem Tool gemeldeten Ergebnisse spiegeln den Status Ihrer Einstellungen nur zu dem bestimmten Zeitpunkt wider, zu dem Sie sie erstellt haben. Wenn Sie später Änderungen an Richtlinien in Microsoft Intune, Azure Active Directory oder Microsoft 365 vornehmen, können Elemente, die "Bereit" waren, "Nicht bereit" werden. Um Probleme mit Microsoft Managed Desktop-Vorgängen zu vermeiden, überprüfen Sie die in diesem Artikel beschriebenen spezifischen Einstellungen, bevor Sie Richtlinien ändern.

## <a name="microsoft-intune-settings"></a>Microsoft Intune-Einstellungen

Sie können auf die Intune-Einstellungen im Microsoft Endpoint Manager [Admin Center zugreifen.](https://endpoint.microsoft.com)

### <a name="autopilot-deployment-profile"></a>Autopilot-Bereitstellungsprofil

Es sollten keine vorhandenen Autopilotprofile vorhanden sein, die auf zugewiesene oder dynamische Gruppen mit Microsoft Managed Desktop-Geräten zielen. Microsoft Managed Desktop verwendet Autopilot zum Bereitstellen neuer Geräte.

**Nicht bereit**

Sie verfügen über ein Autopilot-Profil, das allen Geräten zugewiesen ist. Weitere Schritte finden Sie [unter Registrieren von Windows-Geräten in Intune mithilfe von Windows Autopilot](/mem/autopilot/enrollment-autopilot). Legen Sie nach der Registrierung von Microsoft Managed Desktop die Autopilot-Richtlinie so ein, dass die Gruppe Moderne Arbeitsplatzgeräte **–Alle** Azure AD ausgeschlossen wird.

**Empfehlung**

Stellen Sie sicher, dass Ihre Autopilotprofile auf eine zugewiesene oder dynamische Azure AD-Gruppe zielen, die keine Microsoft Managed Desktop-Geräte enthält. Weitere Schritte finden Sie [unter Registrieren von Windows-Geräten in Intune mithilfe von Windows Autopilot](/mem/autopilot/enrollment-autopilot). Legen Sie nach der Registrierung von Microsoft Managed Desktop ihre Autopilot-Profile so ein, dass die Gruppe Moderne Arbeitsplatzgeräte **–Alle** Azure AD ausgeschlossen wird.


### <a name="certificate-connectors"></a>Zertifikatconnectors

Wenn Sie über Zertifikatconnectors verfügen, die von den Geräten verwendet werden, die Sie bei Microsoft Managed Desktop registrieren möchten, sollten die Connectors keine Fehler enthalten. Nur eine der folgenden Ratgeber gilt für Ihre Situation, überprüfen Sie sie daher sorgfältig.

**Empfehlung**

Es sind keine Zertifikatconnectors vorhanden. Es ist möglich, dass Sie keine Connectors benötigen, aber Sie sollten bewerten, ob Sie möglicherweise einige für die Netzwerkkonnektivität auf Ihren Microsoft Managed Desktop-Geräten benötigen. Weitere Informationen finden Sie unter [Prepare certificates and network profiles for Microsoft Managed Desktop](certs-wifi-lan.md).

**Empfehlung**

Mindestens ein Zertifikatconnector hat einen Fehler. Wenn Sie diesen Connector zum Bereitstellen von Zertifikaten für Microsoft Managed Desktop-Geräte benötigen, müssen Sie den Fehler beheben. Weitere Informationen finden Sie unter [Prepare certificates and network profiles for Microsoft Managed Desktop](certs-wifi-lan.md).


**Empfehlung**

Sie verfügen über mindestens einen Zertifikatconnector, und es werden keine Fehler gemeldet. In Vorbereitung auf die Bereitstellung müssen Sie jedoch möglicherweise ein Profil erstellen, um den Connector für Microsoft Managed Desktop-Geräte wiederzuverwenden. Weitere Informationen finden Sie unter [Prepare certificates and network profiles for Microsoft Managed Desktop](certs-wifi-lan.md).


### <a name="conditional-access-policies"></a>Richtlinien für bedingten Zugriff

Richtlinien für bedingten Zugriff dürfen Microsoft Managed Desktop nicht daran hindern, Ihre Azure AD-Organisation (Mandant) in Intune und Azure AD zu verwalten.

**Nicht bereit**

Sie verfügen über mindestens eine Richtlinie für bedingten Zugriff, die auf alle Benutzer zielt. Während der Registrierung schließen wir Microsoft Managed Desktop-Dienstkonten aus relevanten Richtlinien für bedingten Zugriff aus und wenden neue Richtlinien für bedingten Zugriff an, um den Zugriff auf diese Konten einzuschränken. Nach der Registrierung können Sie die Microsoft Managed Desktop-Richtlinie für bedingten Zugriff in Microsoft Endpoint Manager überprüfen. Weitere Informationen zu diesen Dienstkonten finden Sie unter [Standard operating procedures](../service-description/operations-and-monitoring.md#standard-operating-procedures).

**Empfehlung**

Sie verfügen über Richtlinien für bedingten Zugriff, die verhindern können, dass Microsoft Managed Desktop den Microsoft Managed Desktop-Dienst verwaltet. Während der Registrierung schließen wir Microsoft Managed Desktop-Dienstkonten aus relevanten Richtlinien für bedingten Zugriff aus und wenden neue Richtlinien für bedingten Zugriff an, um den Zugriff auf diese Konten einzuschränken. Weitere Informationen zu diesen Dienstkonten finden Sie unter [Standard operating procedures](../service-description/operations-and-monitoring.md#standard-operating-procedures).

**Error**

Die Intune-Administratorrolle verfügt nicht über ausreichende Berechtigungen für diese Prüfung. Sie benötigen außerdem eine der folgenden Azure AD-Rollen, um diese Prüfung ausführen zu können:

- Sicherheitsleseberechtigter
- Sicherheitsadministrator
- Administrator für bedingten Zugriff
- Globaler Leser
- Geräteadministrator


### <a name="device-compliance-policies"></a>Richtlinien zur Gerätekonformität

Intune-Richtlinien zur Gerätekonformität in Ihrer Azure AD-Organisation können sich auf Microsoft Managed Desktop-Geräte auswirken.

**Nicht bereit**

Sie verfügen über mindestens eine Compliancerichtlinie, die auf alle Benutzer zielt. Microsoft Managed Desktop enthält Compliancerichtlinien für Ihre Microsoft Managed Desktop-Geräte.  Ändern Sie die Richtlinie auf eine bestimmte Azure AD-Gruppe, die keine Microsoft Managed Desktop-Benutzer oder -Geräte enthält. Weitere Schritte finden Sie unter [Create a compliance policy in Microsoft Intune](/mem/intune/protect/create-compliance-policy).

**Empfehlung**

Stellen Sie sicher, dass Compliancerichtlinien, die Sie haben, nicht für Microsoft Managed Desktop-Benutzer bestimmt sind. Weitere Schritte finden Sie unter [Create a compliance policy in Microsoft Intune](/mem/intune/protect/create-compliance-policy).



### <a name="device-configuration-profiles"></a>Gerätekonfigurationsprofile

Intune-Gerätekonfigurationsprofile in Ihrer Azure AD-Organisation dürfen keine Microsoft Manage Desktop-Geräte oder -Benutzer verwenden.

**Nicht bereit**

Sie verfügen über mindestens ein Konfigurationsprofil, das auf alle Benutzer, alle Geräte oder beides zielt. Setzen Sie das Profil auf eine bestimmte Azure AD-Gruppe zurück, die keine Microsoft Managed Desktop-Geräte enthält. Weitere Schritte finden Sie unter [Erstellen eines Profils mit benutzerdefinierten Einstellungen in Microsoft Intune](/mem/intune/configuration/custom-settings-configure).

**Empfehlung**

Stellen Sie sicher, dass alle Konfigurationsrichtlinien, die Sie haben, keine Microsoft Managed Desktop-Geräte oder -Benutzer enthalten. Weitere Schritte finden Sie unter [Erstellen eines Profils mit benutzerdefinierten Einstellungen in Microsoft Intune](/mem/intune/configuration/custom-settings-configure).



### <a name="device-type-restrictions"></a>Gerätetypeinschränkungen

Microsoft Managed Desktop-Geräte müssen in Intune registrieren dürfen.

**Nicht bereit**

Derzeit ist mindestens eine Registrierungseinschränkungsrichtlinie konfiguriert, um die Registrierung von Windows-Geräten in Intune zu verhindern. Führen Sie die Schritte unter [Festlegen](/mem/intune/enrollment/enrollment-restrictions-set) von Registrierungseinschränkungen für jede Registrierungseinschränkungsrichtlinie für Microsoft Managed Desktop-Benutzer aus, und ändern Sie die **Einstellung Windows (MDM)** auf **Zulassen**. Sie können jedoch alle  persönlichen **Windows (MDM)-Geräte** auf **Blockieren festlegen.** 


### <a name="enrollment-status-page"></a>Seite "Registrierungsstatus"

Derzeit ist die Registrierungsstatusseite (Enrollment Status Page, ESP) aktiviert. Wenn Sie an der öffentlichen Microsoft Managed Desktop-Vorschau dieses Features teilnehmen möchten, können Sie dieses Element ignorieren. Weitere Informationen finden Sie unter [First-run experience with Autopilot und the Enrollment Status Page](../get-started/esp-first-run.md).

**Nicht bereit**

Sie haben das STANDARDprofil für ESP auf App- und **Profilkonfigurationsfortschritt anzeigen festgelegt.** Deaktivieren Sie diese Einstellung, oder stellen Sie sicher, dass Zuordnungen zu einer Azure AD-Gruppe keine Microsoft Managed Desktop-Geräte enthalten, indem Sie die Schritte unter Einrichten der [Registrierungsstatusseite ausführen.](/mem/intune/enrollment/windows-enrollment-status)

**Empfehlung**

Stellen Sie sicher, dass  Profile mit der Einstellung App- und Profilkonfigurationsfortschritt anzeigen keine Azure AD-Gruppe zugewiesen sind, die Microsoft Managed Desktop-Geräte enthält. Weitere Informationen finden Sie unter [Einrichten der Registrierungsstatusseite](/mem/intune/enrollment/windows-enrollment-status).

### <a name="microsoft-store-for-business"></a>Microsoft Store für Unternehmen

Wir verwenden den Microsoft Store für Unternehmen und stellen die Unternehmensportal-App auf Microsoft Managed Desktop zur Verfügung, damit Benutzer optional einige Apps installieren können, z. B. Microsoft Project und Microsoft Visio (sofern zulässig).

**Nicht bereit**

Microsoft Store für Unternehmen ist entweder nicht aktiviert oder nicht mit Intune synchronisiert. Weitere Informationen finden Sie unter Verwalten von volumenkauften Apps aus dem [Microsoft Store für Unternehmen](/mem/intune/apps/windows-store-for-business) mit Microsoft Intune und Installieren des [Intune-Unternehmensportals auf Geräten.](../get-started/company-portal.md)

### <a name="multifactor-authentication"></a>Mehrstufige Authentifizierung

Die mehrstufige Authentifizierung darf nicht verhindern, dass Microsoft Managed Desktop Ihre Azure AD-Organisation (Mandant) in Intune und Azure AD verwaltet.


**Nicht bereit**

Sie haben einige mehrstufige Authentifizierungsrichtlinien als erforderlich für **Richtlinien** für bedingten Zugriff festgelegt, die allen Benutzern zugewiesen sind. Während der Registrierung schließen wir Microsoft Managed Desktop-Dienstkonten aus relevanten Richtlinien für bedingten Zugriff aus und wenden neue Richtlinien für bedingten Zugriff an, um den Zugriff auf diese Konten einzuschränken. Weitere Informationen zu diesen Dienstkonten finden Sie unter [Standard operating procedures](../service-description/operations-and-monitoring.md#standard-operating-procedures).

**Empfehlung**

Für Richtlinien für bedingten Zugriff ist eine mehrstufige Authentifizierung erforderlich, die verhindern könnte, dass Microsoft Managed Desktop den Microsoft Managed Desktop-Dienst verwaltet. Während der Registrierung schließen wir Microsoft Managed Desktop-Dienstkonten aus relevanten Richtlinien für bedingten Zugriff aus und wenden neue Richtlinien für bedingten Zugriff an, um den Zugriff auf diese Konten einzuschränken. Weitere Informationen zu diesen Dienstkonten finden Sie unter [Standard operating procedures](../service-description/operations-and-monitoring.md#standard-operating-procedures).

**Error**

Die Intune-Administratorrolle verfügt nicht über ausreichende Berechtigungen für diese Prüfung. Sie benötigen außerdem eine der folgenden Azure AD-Rollen, um diese Prüfung ausführen zu können:

- Sicherheitsleseberechtigter
- Sicherheitsadministrator
- Administrator für bedingten Zugriff
- Globaler Leser
- Geräteadministrator


### <a name="powershell-scripts"></a>PowerShell-Skripts

Windows PowerShell Skripts können nicht auf eine Weise zugewiesen werden, die auf Microsoft Managed Desktop-Geräte zielen würde.  

**Empfehlung**

Stellen Sie sicher, Windows PowerShell Skripts in Ihrer Azure AD-Organisation nicht für Microsoft Manage Desktop-Geräte oder -Benutzer bestimmt sind. Weisen Sie kein PowerShell-Skript für alle Benutzer, alle Geräte oder beides zu. Ändern Sie die Richtlinie so, dass sie eine Zuordnung für eine bestimmte Azure AD-Gruppe verwendet, die keine Microsoft Managed Desktop-Geräte oder -Benutzer enthält. Weitere Informationen finden Sie unter [Use PowerShell scripts on Windows 10 devices in Intune](/mem/intune/apps/intune-management-extension).

### <a name="region"></a>Region

Ihre Region muss von Microsoft Managed Desktop unterstützt werden.

**Nicht bereit**

Ihre Azure AD-Organisationsregion wird derzeit nicht von Microsoft Managed Desktop unterstützt. Weitere Informationen finden Sie unter [Microsoft Managed Desktop supported regions and languages](../service-description/regions-languages.md).

**Empfehlung**

Mindestens eines der Länder, in denen sich Ihre Azure AD-Organisation befindet, wird von Microsoft Managed Desktop nicht unterstützt. Weitere Informationen finden Sie unter [Microsoft Managed Desktop supported regions and languages](../service-description/regions-languages.md).


### <a name="security-baselines"></a>Sicherheitsgrundwerte

Sicherheitsgrundlinienrichtlinien sollten nicht auf Microsoft Managed Desktop-Geräte ausgerichtet sein.

**Nicht bereit**

Sie verfügen über ein Sicherheitsgrundprofil, das auf alle Benutzer, alle Geräte oder beides ausgerichtet ist. Ändern Sie die Richtlinie so, dass sie eine Zuordnung für eine bestimmte Azure AD-Gruppe verwendet, die keine Microsoft Managed Desktop-Geräte enthält. Weitere Schritte finden Sie unter [Verwenden von Sicherheitsgrundwerten zum Konfigurieren von Windows 10-Geräten in Intune](/mem/intune/protect/security-baselines). Während der Registrierung wenden wir eine neue Sicherheitsgrundlinie auf alle Microsoft Managed Desktop-Geräte an. Nach der Registrierung können Sie die Microsoft Managed Desktop-Sicherheitsgrundlinie im **Bereich Konfigurationsrichtlinien** von Microsoft Endpoint Manager überprüfen.

**Empfehlung**

Stellen Sie sicher, dass alle Sicherheitsgrundrichtlinien, die Sie von Microsoft Managed Desktop-Geräten ausgeschlossen haben. Weitere Schritte finden Sie unter [Verwenden von Sicherheitsgrundwerten zum Konfigurieren von Windows 10-Geräten in Intune](/mem/intune/protect/security-baselines). Während der Registrierung wenden wir eine neue Sicherheitsgrundlinie auf alle Microsoft Managed Desktop-Geräte an. Die **Gruppe Moderne Arbeitsplatzgeräte – Alle** Azure AD ist eine dynamische Gruppe, die wir erstellen, wenn Sie sich bei Microsoft Managed Desktop registrieren, sodass Sie nach der Registrierung wiederkommen müssen, um diese Gruppe auszuschließen. 


### <a name="windows-apps"></a>Windows-Apps

Überprüfen Sie apps you want your Microsoft Managed Desktop users to have.

**Empfehlung**

Sie sollten eine Bestandsaufnahme der Apps vorbereiten, über die Ihre Microsoft Managed Desktop-Benutzer verfügen sollen. Da diese Apps von Intune bereitgestellt werden müssen, sollten Sie die Erneutvernendung vorhandener Intune-Apps auswerten. Erwägen Sie die Verwendung des Unternehmensportals (siehe [Install Intune Company Portal on devices](../get-started/company-portal.md) and Enrollment Status Page (ESP), um Apps an Ihre Benutzer zu verteilen. Weitere Informationen finden Sie unter [Apps in Microsoft Managed Desktop](apps.md) und [First-run experience with Autopilot und der Registrierungsstatusseite](../get-started/esp-first-run.md).

Sie können Ihren Microsoft-Kontomitarbeiter um eine Abfrage in Microsoft Endpoint Configuration Manager bitten, die Apps zu identifizieren, die für die Migration zu Intune bereit sind oder anpassungen müssen.


### <a name="windows-hello-for-business"></a>Windows Hello for Business

Microsoft Managed Desktop erfordert, dass Windows Hello for Business aktiviert ist.

**Nicht bereit**

Windows Hello for Business ist deaktiviert. Aktivieren Sie dies, indem Sie die Schritte unter [Erstellen einer Windows Hello for Business-Richtlinie ausführen.](/mem/intune/protect/windows-hello#create-a-windows-hello-for-business-policy)

**Empfehlung**

Windows Hello for Business ist nicht eingerichtet. Aktivieren Sie dies, indem Sie die Schritte unter [Erstellen einer Windows Hello for Business-Richtlinie ausführen.](/mem/intune/protect/windows-hello#create-a-windows-hello-for-business-policy)


### <a name="windows-10-update-rings"></a>Windows 10-Updateringe

Ihre Richtlinie "Windows 10 Update ring" in Intune darf keine Microsoft Managed Desktop-Geräte verwenden.

**Nicht bereit**

Sie verfügen über eine "Updatering"-Richtlinie, die auf alle Geräte, alle Benutzer oder beides zielt. Ändern Sie die Richtlinie so, dass sie eine Zuordnung für eine bestimmte Azure AD-Gruppe verwendet, die keine Microsoft Managed Desktop-Geräte enthält. Weitere Schritte finden Sie [unter Manage Windows 10 software updates in Intune](/mem/intune/protect/windows-update-for-business-configure).

**Empfehlung**

Stellen Sie sicher, dass alle Updateringrichtlinien, die Sie die **Gruppe Moderne Arbeitsplatzgeräte –Alle** Azure AD ausgeschlossen haben. Wenn Sie diesen Richtlinien Azure AD-Benutzergruppen zugewiesen haben, stellen Sie sicher, dass alle Updateringrichtlinien, zu denen Sie auch die Gruppe **Modern Workplace -All** Azure AD ausgeschlossen haben, der Sie Ihre Microsoft Managed Desktop-Benutzer hinzufügen (oder eine entsprechende Gruppe). Weitere Schritte finden Sie [unter Manage Windows 10 software updates in Intune](/mem/intune/protect/windows-update-for-business-configure). Sowohl **die Modernen Arbeitsplatzgeräte - All** als auch **Modern Workplace** - Alle Azure AD-Gruppen sind Gruppen, die wir erstellen, wenn Sie sich bei Microsoft Managed Desktop registrieren, sodass Sie nach der Registrierung wiederkommen müssen, um diese Gruppe auszuschließen.


## <a name="azure-active-directory-settings"></a>Azure Active Directory-Einstellungen

Sie können auf Azure Active Directory-Einstellungen im [Azure-Portal zugreifen.](https://portal.azure.com)

### <a name="intune-enrollment"></a>Intune-Registrierung

Windows 10-Geräte in Ihrer Azure AD-Organisation müssen in der Lage sein, sich automatisch bei Intune zu registrieren.

**Empfehlung**

Stellen Sie **sicher, dass der MDM-Benutzerbereich** auf **Some** oder **All** und nicht None **festgelegt ist.** Wenn Sie **Einige** auswählen, kommen Sie nach der Registrierung zurück, und wählen Sie die Gruppe **Modern Workplace -All** Azure AD für **Gruppen** oder eine entsprechende Gruppe für alle Microsoft Managed Desktop-Benutzer aus.  Weitere [Informationen finden Sie unter Einrichten der Registrierung für Windows-Geräte mithilfe von Microsoft Intune](/mem/intune/enrollment/windows-enroll#enable-windows-10-automatic-enrollment).


### <a name="ad-hoc-subscriptions"></a>Ad-hoc-Abonnements

Hier erfahren Sie, wie Sie eine Einstellung überprüfen, die (bei Festlegung auf "false") möglicherweise verhindert, dass das Enterprise State Roaming ordnungsgemäß funktioniert.

**Empfehlung**

Stellen Sie **sicher, dass AllowAdHocSubscriptions** auf **True festgelegt ist.** Andernfalls funktioniert das Enterprise State Roaming möglicherweise nicht. Weitere Informationen finden Sie unter [Set-MsolCompanySettings](/powershell/module/msonline/set-msolcompanysettings?view=azureadps-1.0).


### <a name="enterprise-state-roaming"></a>Enterprise State Roaming

Enterprise State Roaming sollte aktiviert sein.

**Empfehlung**

Stellen Sie sicher, dass das Enterprise State Roaming für **Alle oder** ausgewählte **Gruppen aktiviert** ist. Weitere Informationen finden Sie unter [Enable Enterprise State Roaming in Azure Active Directory](/azure/active-directory/devices/enterprise-state-roaming-enable).

### <a name="licenses"></a>Lizenzen

Für die Verwendung von Microsoft Managed Desktop sind eine Reihe von Lizenzen erforderlich.

**Nicht bereit**

Sie verfügen nicht über alle Lizenzen, die Sie für die Verwendung von Microsoft Managed Desktop benötigen. Weitere Informationen finden Sie unter [Microsoft Managed Desktop-Technologien](../intro/technologies.md) und [Weitere Informationen zu Lizenzen.](prerequisites.md#more-about-licenses)


### <a name="microsoft-managed-desktop-service-accounts"></a>Microsoft Managed Desktop-Dienstkonten

Bestimmte Kontonamen können mit von Microsoft Managed Desktop erstellten Kontonamen in Konflikt stehen, um den Microsoft Managed Desktop-Dienst zu verwalten.

**Nicht bereit**

Sie verfügen über mindestens einen Kontonamen, der mit von Microsoft Managed Desktop erstellten Kontonamen in Konflikt steht. Arbeiten Sie mit Ihrem Microsoft-Kontomitarbeiter zusammen, um diese Kontonamen auszuschließen. Wir listen die Kontonamen nicht öffentlich auf, um das Sicherheitsrisiko zu minimieren. 


### <a name="security-administrator-roles"></a>Sicherheitsadministratorrollen

Benutzern mit bestimmten Sicherheitsrollen müssen diese Rollen in Microsoft Defender for Endpoint zugewiesen sein.

**Empfehlung**

Wenn Benutzern eine dieser Rollen in Ihrer Azure AD-Organisation zugewiesen ist, stellen Sie sicher, dass ihnen auch diese Rollen in Microsoft Defender for Endpoint zugewiesen sind. Andernfalls können Administratoren mit diesen Rollen nicht auf das Administratorportal zugreifen.

- Sicherheitsoperator
- Globaler Leser

Weitere Informationen finden Sie unter [Erstellen und Verwalten von Rollen für die rollenbasierte Zugriffssteuerung](/windows/security/threat-protection/microsoft-defender-atp/user-roles).


### <a name="security-default"></a>Standardsicherheit

Sicherheitseinstellungen in Azure Active Directory verhindern, dass Microsoft Managed Desktop Ihre Geräte verwaltet.

**Nicht bereit**

Die Sicherheitseinstellungen sind aktiviert. Deaktivieren Sie Sicherheitseinstellungen, und richten Sie Richtlinien für bedingten Zugriff ein. Weitere Informationen finden Sie unter [Common Conditional Access policies](/azure/active-directory/conditional-access/concept-conditional-access-policy-common).

### <a name="self-service-password-reset"></a>Self-service Password Reset

Self-Service Password Reset (SSPR) kann für alle Microsoft Managed Desktop-Benutzer mit Ausnahme von Microsoft Managed Desktop-Dienstkonten aktiviert werden. Weitere Informationen finden Sie unter Tutorial: Aktivieren sie, dass Benutzer ihr Konto entsperren oder Kennwörter mithilfe der [Azure Active Directory-Self-Service-Kennwortzurücksetzung zurücksetzen.](/azure/active-directory/authentication/tutorial-enable-sspr)

**Empfehlung**

Stellen Sie sicher, dass die Einstellung SSPR **Selected** Microsoft Managed Desktop-Benutzer enthält, aber Microsoft Managed Desktop-Dienstkonten ausschließt. Microsoft Managed Desktop-Dienstkonten können nicht wie erwartet funktionieren, wenn SSPR aktiviert ist.  


### <a name="standard-user-role"></a>Standardbenutzerrolle

Anders als die Benutzer, denen Azure AD-Rollen als globaler Administrator und Geräteadministrator zugewiesen sind, sind Microsoft Managed Desktop-Benutzer Standardbenutzer ohne lokale Administratorrechte. Allen anderen Benutzern wird eine Standardbenutzerrolle zugewiesen, wenn sie ihr Microsoft Managed Desktop-Gerät starten.

**Empfehlung**

Microsoft Managed Desktop-Benutzer verfügen nach der Registrierung nicht über lokale Administratorrechte auf ihren Microsoft Managed Desktop-Geräten.

## <a name="microsoft-365-apps-for-enterprise"></a>Microsoft 365 Apps for Enterprise

### <a name="onedrive"></a>OneDrive

Die **Einstellung Synchronisierung nur auf PCs zulassen,** die bestimmten Domänen beigetreten sind, ist mit Microsoft Managed Desktop in Konflikt. Sie können auf #A0 im OneDrive [Admin Center zugreifen.](https://admin.onedrive.com)

**Empfehlung**

Sie verwenden die Einstellung Synchronisierung nur auf PCs zulassen, **die bestimmten Domänen beigetreten** sind. Diese Einstellung funktioniert nicht mit Microsoft Managed Desktop. Deaktivieren Sie diese Einstellung, und richten Sie stattdessen OneDrive für die Verwendung einer Richtlinie für bedingten Zugriff ein. Hilfe [finden Sie unter Plan a Conditional Access deployment.](/azure/active-directory/conditional-access/plan-conditional-access)