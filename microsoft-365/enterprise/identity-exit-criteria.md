---
title: 'Phase 2: Beendigungskriterien für die Identitätsinfrastruktur'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/20/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom: ''
description: Stellen Sie sicher, dass Ihre Konfiguration die Kriterien von Microsoft 365 Enterprise für identitätsbasierte Dienste und Infrastrukturen erfüllt.
ms.openlocfilehash: 94343400482083b2e793ff218816f06cb982187e
ms.sourcegitcommit: 1d376287f6c1bf5174873e89ed4bf7bb15bc13f6
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/14/2019
ms.locfileid: "38627391"
---
# <a name="phase-2-identity-infrastructure-exit-criteria"></a>Phase 2: Beendigungskriterien für die Identitätsinfrastruktur

![Phase 2: Identität](./media/deploy-foundation-infrastructure/identity_icon-small.png)

Stellen Sie sicher, dass Ihre Identitätsinfrastruktur die folgenden erforderlichen Kriterien erfüllt, und dass Sie die optionalen Kriterien berücksichtigt haben.

Unter [Voraussetzungen](https://docs.microsoft.com/microsoft-365-enterprise/identity-access-policies#prerequisites) finden Sie weitere Empfehlungen zur Identitätsinfrastruktur.

<a name="crit-identity-global-admin"></a>
## <a name="required-your-global-administrator-accounts-are-protected"></a>Erforderlich: Ihre globalen Administratorkonten sind geschützt 

Sie haben [Ihre globalen Office 365-Administratorkonten geschützt](https://docs.microsoft.com/office365/enterprise/protect-your-global-administrator-accounts), um Versuche von Angreifern zur Kompromittierung von Anmeldeinformationen zu vereiteln, die zu Verstößen gegen Ihr Microsoft 365-Abonnement führen können.

Wenn Sie diese Anforderung überspringen, können Ihre globalen Administratorkonten anfällig für Angriffe und Kompromittierung sein. Dadurch kann ein Angreifer systemweiten Zugriff auf Ihre Daten erhalten, um diese zu stehlen, zu zerstören oder für Lösegeldforderungen zu missbrauchen.

Gegebenenfalls hilft Ihnen [Schritt 1](identity-create-protect-global-admins.md#identity-global-admin), diese Anforderung zu erfüllen.

### <a name="how-to-test"></a>Testen

Gehen Sie folgendermaßen vor, um sicherzustellen, dass Sie Ihre globalen Administratorkonten geschützt haben:

1. Führen Sie den folgenden Azure Active Directory PowerShell für Graph-Befehl an der PowerShell-Eingabeaufforderung aus. Es sollte nur die Liste der dedizierten globalen Administratorkonten angezeigt werden.
   ```powershell
   Get-AzureADDirectoryRole | where { $_.DisplayName -eq "Company Administrator" } | Get-AzureADDirectoryRoleMember | Ft DisplayName
   ```
2. Melden Sie sich bei Office 365 mit jedem der Konten aus Schritt 1 an. Bei jeder Anmeldung muss die mehrstufige Authentifizierung und die stärkste Form der sekundären Authentifizierung in Ihrer Organisation verlangt werden.

> [!Note]
> Anweisungen zum Installieren des Azure Active Directory PowerShell-Moduls und zum Anmelden bei Office 365 finden Sie unter [Verbinden mit Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell).

<a name="crit-identity-pim"></a>
## <a name="optional-you-have-set-up-privileged-identity-management-to-support-on-demand-assignment-of-the-global-administrator-role"></a>Optional: Sie haben Privileged Identity Management zur Unterstützung einer bedarfsgesteuerten Zuweisung der globalen Administratorrolle eingerichtet

Sie haben nach den Anweisungen in [Konfigurieren von Azure AD Privileged Identity Management (PIM)](https://docs.microsoft.com/azure/active-directory/active-directory-privileged-identity-management-configure) PIM in Ihrem Azure AD-Mandanten aktiviert und Ihre globalen Administratorkonten als berechtigte Administratoren konfiguriert.

Sie haben auch die Empfehlungen in [Schützen des privilegierten Zugriffs für hybride und Cloudbereitstellungen in Azure AD](https://docs.microsoft.com/azure/active-directory/admin-roles-best-practices) befolgt, um eine Roadmap zu entwickeln, die den privilegierten Zugriff vor Cyberangriffen schützt.

Wenn Sie diese Option überspringen, sind Ihre globalen Administratorkonten ständigen Onlineangriffen ausgesetzt und können bei einer Gefährdung zulassen, dass ein Angreifer Ihre vertraulichen Informationen stiehlt, zerstört oder gegen Lösegeldforderungen sperrt.

Gegebenenfalls kann [Schritt 1](identity-create-protect-global-admins.md#identity-pim) bei dieser Option hilfreich sein.

<a name="crit-identity-pam"></a>
## <a name="optional-you-have-configure-privileged-access-management-in-office-365"></a>Optional: Sie haben Privileged Access Management in Office 365 konfiguriert

Sie haben die Informationen im Thema [Konfigurieren von Privileged Access Management in Office 365](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-configuration) verwendet, um privilegierten Zugriff zu aktivieren und eine oder mehrere Richtlinien für privilegierten Zugriff in Ihrer Organisation zu erstellen. Sie haben diese Richtlinien konfiguriert, und Just-in-Time-Zugriff ist für Zugriff auf vertrauliche Daten oder Zugriff auf kritische Konfigurationseinstellungen aktiviert.

Gegebenenfalls hilft Ihnen [Schritt 1](identity-create-protect-global-admins.md#identity-pam), diese Anforderung zu erfüllen. 

<a name="crit-password-prot"></a>
## <a name="optional-azure-ad-password-protection-is-banning-the-use-of-weak-passwords"></a>Optional: Azure AD-Kennwortschutz verhindert die Verwendung von unsicheren Kennwörtern.

Sie haben das Sperren unsicherer Kennwörter [in der Cloud](https://docs.microsoft.com/azure/active-directory/authentication/concept-password-ban-bad) und für Ihre [lokalen Active Directory Domain Services (AD DS)](https://docs.microsoft.com/azure/active-directory/authentication/concept-password-ban-bad-on-premises) für global gesperrte Kennwörter und optional für benutzerdefinierte Ausdrücke aktiviert.

Gegebenenfalls hilft Ihnen [Schritt 2](identity-secure-your-passwords.md#identity-password-prot) bei dieser Option.

<a name="crit-identity-pw-reset"></a>
## <a name="optional-users-can-reset-their-own-passwords"></a>Optional: Benutzer können ihre eigenen Kennwörter zurücksetzen

Sie haben [Schnelle Bereitstellung der Self-Service-Kennwortzurücksetzung in Azure AD](https://docs.microsoft.com/azure/active-directory/active-directory-passwords-getting-started) verwendet, um die Kennwortzurücksetzung für die Benutzer zu konfigurieren.

Wenn Sie diese Bedingung nicht erfüllen, sind Benutzer von Benutzerkontoadministratoren abhängig, um ihre Kennwörter zurückzusetzen, was zusätzlichen IT-Verwaltungsaufwand bedeutet.

Gegebenenfalls hilft Ihnen [Schritt 2](identity-secure-your-passwords.md#identity-pw-reset) bei dieser Option.

<a name="crit-identity-sso"></a>
## <a name="optional-users-can-sign-in-using-azure-ad-seamless-single-sign-on"></a>Optional: Benutzer können Azure AD Seamless Single Sign-on für die Anmeldung verwenden

Sie haben [Azure AD Connect: Nahtloses einmaliges Anmelden](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-sso-quick-start) für Ihre Organisation aktiviert, um die Anmeldung von Benutzern bei cloudbasierten Anwendungen, z. B. Office 365, zu vereinfachen.

Wenn Sie diese Option überspringen, werden die Benutzer möglicherweise zur Eingabe von Anmeldeinformationen aufgefordert, wenn sie auf zusätzliche Anwendungen zugreifen, die Ihren Azure AD-Mandanten verwenden.

Gegebenenfalls hilft Ihnen [Schritt 2](identity-secure-your-passwords.md#identity-sso) bei dieser Option.

<a name="crit-identity-custom-sign-in"></a>
## <a name="optional-the-office-365-sign-in-screen-is-personalized-for-your-organization"></a>Optional: Der Office 365-Anmeldebildschirm ist für Ihre Organisation personalisiert

Sie haben entsprechend den Anweisungen unter [Hinzufügen eines Unternehmensbrandings zu den Anmelde- und Zugriffspanelseiten](https://aka.ms/aadpaddbranding) das Branding Ihrer Organisation auf der Anmeldeseite von Office 365 hinzugefügt.

Wenn Sie diese Option überspringen, sehen die Benutzer einen allgemeinen Office 365-Anmeldebildschirm und sind sich möglicherweise nicht sicher, dass sie sich auf der Website Ihrer Organisation anmelden.

Gegebenenfalls hilft Ihnen [Schritt 2](identity-secure-your-passwords.md#identity-custom-sign-in) bei dieser Option.


<a name="crit-identity-mfa"></a>
## <a name="optional-azure-multi-factor-authentication-is-enabled-for-your-users"></a>Optional: Die mehrstufige Azure-Authentifizierung ist für Ihre Benutzer aktiviert

Sie haben den [Plan für die mehrstufige Azure-Authentifizierung](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-getstarted) und [Richtlinien für bedingten Zugriff](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-getstarted#enable-multi-factor-authentication-with-conditional-access) verwendet, um die mehrstufige Azure-Authentifizierung (Multi-Factor Authentication, MFA) für ihre Benutzerkonten zu aktivieren.

Wenn Sie diese Option überspringen, sind die Benutzerkonten anfällig für eine Gefährdung der Anmeldeinformationen durch Cyberangriffe. Wenn das Kennwort eines Benutzerkontos manipuliert wurde, sind alle Ressourcen und Funktionen des Kontos, z. B. Administratorrollen, für den Angreifer verfügbar. Dadurch kann der Angreifer interne Dokumente und andere Daten kopieren, zerstören oder Lösegeld dafür verlangen.

Gegebenenfalls hilft Ihnen [Schritt 3](identity-secure-user-sign-ins.md#identity-mfa) bei dieser Option.

### <a name="how-to-test"></a>Testen

1.  Erstellen Sie ein Testbenutzerkonto, und weisen Sie ihm eine Lizenz zu. 
2.  Konfigurieren Sie die mehrstufige Azure-Authentifizierung für das Testbenutzerkonto mit der zusätzlichen Überprüfungsmethode, die Sie für tatsächliche Benutzerkonten verwenden, z. B. Senden einer SMS an Ihr Telefon. 
3.  Melden Sie sich mit dem Testbenutzerkonto beim Office 365-Portal an.
4.  Vergewissern Sie sich, dass Sie von MFA zur Eingabe der zusätzlichen Überprüfungsinformationen aufgefordert werden und die Authentifizierung erfolgreich ist. 
5.  Löschen Sie das Testbenutzerkonto.

<a name="crit-identity-ident-prot"></a>
## <a name="optional-azure-ad-identity-protection-is-enabled-to-protect-against-credential-compromise-microsoft-365-enterprise-e5-only"></a>Optional: Azure AD Identity Protection ist zum Schutz vor Gefährdung der Anmeldeinformationen aktiviert (nur Microsoft 365 Enterprise E5)

Sie haben Azure AD Identity Protection zu folgenden Zwecken aktiviert:

- Beseitigen potenzieller Anfälligkeiten für Identitätsverletzungen
- Erkennen möglicher Kompromittierungsversuche von Anmeldeinformationen
- Untersuchen und Beheben laufender verdächtiger Identitätsvorfälle

Wenn Sie diese Option überspringen, sind Sie nicht in der Lage, Kompromittierungsversuche von Anmeldeinformationen zu erkennen oder automatisch zu verhindern bzw. identitätsbezogene Sicherheitsvorfälle zu untersuchen. Dies macht Ihr Unternehmen potenziell anfällig für eine erfolgreiche Kompromittierung von Anmeldeinformationen und die resultierende Bedrohung für vertrauliche Daten Ihrer Organisation.

Gegebenenfalls hilft Ihnen [Schritt 3](identity-secure-user-sign-ins.md#identity-ident-prot) bei dieser Option.


### <a name="how-to-test"></a>Testen

1. Erstellen Sie ein Testbenutzerkonto mit einem anfänglichen Kennwort.
2. Führen Sie die Schritte in [Zulassen, dass Benutzer ihre eigenen Kennwörter in Office 365 zurücksetzen](https://docs.microsoft.com/office365/admin/add-users/let-users-reset-passwords) aus, um das Kennwort für das Testbenutzerkonto zurückzusetzen.
3. Melden Sie sich ab, und melden Sie sich dann mit dem zurückgesetzten Kennwort wieder am Testbenutzerkonto an.
4. Löschen Sie das Testbenutzerkonto.

<a name="crit-identity-sync"></a>
## <a name="required-for-hybrid-identity-users-and-groups-are-synchronized-with-azure-ad"></a>Erforderlich für Hybrididentiät: Benutzer und Gruppen werden mit Azure AD synchronisiert

Wenn Sie über lokale Active Directory Domain Services (AD DS) verfügen, haben Sie Azure AD Connect zum Synchronisieren von Benutzerkonten und Gruppen zwischen Ihren lokalen AD DS und Ihrem Azure AD-Mandanten verwendet.

Dank der Verzeichnissynchronisierung können sich Ihre Benutzer bei Office 365 und anderen Microsoft Cloud Services mit denselben Anmeldeinformationen anmelden, die sie zum Anmelden an ihren Computern und zum Zugriff auf lokale Ressourcen verwenden.

Gegebenenfalls hilft Ihnen [Schritt 4](identity-add-user-accounts.md#identity-sync), diese Anforderung zu erfüllen.

Wenn Sie diese Anforderung überspringen, haben Sie zwei Sätze von Benutzerkonten und Gruppen:

- Benutzerkonten und Gruppen, die in Ihren lokalen AD DS vorhanden sind
- Benutzerkonten und Gruppen, die in Ihrem Azure AD-Mandanten vorhanden sind

In diesem Zustand müssen die beiden Sätze von Benutzerkonten und Gruppen manuell von IT-Administratoren und Benutzern verwaltet werden. Dies führt zwangsläufig zu nicht synchronisierten Konten, deren Kennwörtern und Gruppen.

### <a name="how-to-test"></a>Testen
Um zu überprüfen, ob die Authentifizierung mit lokalen Anmeldeinformationen funktioniert, melden Sie sich mit Ihren lokalen Anmeldeinformationen beim Office 365 an.

Führen Sie folgende Schritte aus, um zu überprüfen, ob die Verzeichnissynchronisierung ordnungsgemäß funktioniert:

1.  Erstellen Sie eine neue Testgruppe in AD DS.
2.  Warten Sie, bis die Synchronisierungszeit abgelaufen ist.
3.  Überprüfen Sie Ihren Azure AD-Mandanten, um sicherzustellen, dass der Name der neuen Testgruppe angezeigt wird.

<a name="crit-identity-sync-health"></a>
## <a name="optional-directory-synchronization-is-monitored"></a>Optional: Verzeichnissynchronisierung wird überwacht

Sie haben [Azure AD Connect Health für die Synchronisierung](https://docs.microsoft.com/azure/active-directory/connect-health/active-directory-aadconnect-health-sync) (für die Synchronisierung von Kennwörtern) oder [Azure AD Connect Health mit AD FS](https://docs.microsoft.com/azure/active-directory/connect-health/active-directory-aadconnect-health-adfs) (für Verbundauthentifizierung) verwendet und Azure AD Connect Health bereitgestellt. Dazu gehört Folgendes:

- Installieren des Azure AD Connect Health-Agents auf jedem Ihrer lokalen Identitätsserver.
- Verwenden des Azure AD Connect Health-Portals zum Überwachen des Zustands der laufenden Synchronisierung.

Wenn Sie diese Option überspringen, können Sie den Zustand Ihrer cloudbasierten Identitätsinfrastruktur genauer beurteilen.

Gegebenenfalls hilft Ihnen [Schritt 4](identity-add-user-accounts.md#identity-sync-health) bei dieser Option.

### <a name="how-to-test"></a>Testen
Das Azure AD Connect Health-Portal zeigt den aktuellen und korrekten Zustand Ihrer lokalen Domänencontroller und der fortlaufenden Synchronisierung an.


<a name="crit-identity-pw-writeback"></a>
## <a name="optional-password-writeback-is-enabled-for-your-users"></a>Optional: Kennwortrückschreiben ist für Ihre Benutzer aktiviert

Sie haben die Anweisungen unter [Azure AD SSPR mit Kennwortrückschreiben](https://docs.microsoft.com/azure/active-directory/active-directory-passwords-getting-started) befolgt, um das Kennwortrückschreiben für den Azure AD-Mandanten Ihres Microsoft 365 Enterprise-Abonnements zu aktivieren.

Wenn Sie diese Option überspringen, müssen Benutzer, die nicht mit Ihrem lokalen Netzwerk verbunden sind, ihre AD DS-Kennwörter über einen IT-Administrator zurücksetzen oder entsperren.

Gegebenenfalls hilft Ihnen [Schritt 4](identity-add-user-accounts.md#identity-pw-writeback) bei dieser Option.

>[!Note]
>Das Kennwortrückschreiben ist erforderlich für die vollständige Nutzung von Azure AD Identity Protection-Features, z. B. um zu verlangen, dass Benutzer ihre lokalen Kennwörter ändern, wenn Azure AD ein hohes Risiko einer Kontogefährdung erkannt hat.
>

### <a name="how-to-test"></a>Testen

Sie testen das Kennwortrückschreiben durch Ändern Ihres Kennworts in Office 365. Sie sollten Ihr Konto und das neue Kennwort für den Zugriff auf lokale AD DS-Ressourcen verwenden können.

1. Erstellen Sie in Ihrem lokalen AD DS ein Testbenutzerkonto, lassen Sie Verzeichnissynchronisierung zu, und erteilen Sie dem Konto im Microsoft 365 Admin Center eine Microsoft 365 Enterprise-Lizenz.
2. Melden Sie sich von einem Remotecomputer, der Ihrer lokalen AD DS-Domäne angehört, mit den Anmeldeinformationen des Testbenutzerkontos beim Computer und beim Office-Portal an.
3. Wählen Sie **Einstellungen > Office 365-Einstellungen > Kennwort > Kennwort ändern**.
4. Geben Sie das aktuelle Kennwort ein, geben Sie ein neues Kennwort ein, und bestätigen Sie es dann.
5. Melden Sie sich beim Office-Portal und Remotecomputer ab, und melden Sie sich dann beim Computer mit dem Testbenutzerkonto und dem neuen Kennwort an. Dies beweist, dass Sie das Kennwort eines lokalen AD DS-Benutzerkontos unter Verwendung des Azure AD-Mandanten ändern konnten.

### <a name="how-to-test"></a>Testen

Melden Sie sich mit Ihrem Benutzerkontonamen und mittels mehrstufiger Azure-Authentifizierung beim Office 365-Portal an. Auf der Anmeldeseite sollten Ihre benutzerdefinierten Branding-Elemente angezeigt werden.


<a name="crit-identity-self-service-groups"></a>
## <a name="optional-self-service-group-management-is-enabled-for-specific-azure-ad-security-and-office-365-groups"></a>Optional: Self-Service-Gruppenverwaltung ist für bestimmte Azure AD-Sicherheitsgruppen und Office 365-Gruppen aktiviert

Sie haben bestimmt, welche Gruppen für Self-Service-Verwaltung geeignet sind, deren Besitzer bezüglich des Workflows und der Verantwortlichkeiten der Gruppenverwaltung instruiert und für diese Gruppen [die Self-Service-Verwaltung in Azure AD eingerichtet](https://docs.microsoft.com/azure/active-directory/active-directory-accessmanagement-self-service-group-management).

Wenn Sie diese Option überspringen, müssen alle Verwaltungsaufgaben für Azure AD-Gruppen von IT-Administratoren erledigt werden.

Gegebenenfalls hilft Ihnen [Schritt 5](identity-use-group-management.md#identity-self-service-groups) bei dieser Option.

### <a name="how-to-test"></a>Testen
1.  Erstellen Sie ein Testbenutzerkonto in Azure AD mit dem Azure-Portal.
2.  Melden Sie sich wie beim Testbenutzerkonto an, und erstellen Sie eine Azure AD-Testsicherheitsgruppe.
3.  Melden Sie sich ab, und melden Sie sich dann mit Ihrem IT-Administratorkonto an.
4.  Konfigurieren Sie die Testsicherheitsgruppe für Self-Service-Verwaltung für das Testbenutzerkonto.
5.  Melden Sie sich ab, und melden Sie sich dann mit Ihrem Testbenutzerkonto an.
6.  Verwenden Sie das Azure-Portal, um Mitglieder zu der Testsicherheitsgruppe hinzuzufügen.
7.  Löschen Sie die Testsicherheitsgruppe und das Testbenutzerkonto.

<a name="crit-identity-dyn-groups"></a>
## <a name="optional-dynamic-group-membership-settings-automatically-add-user-accounts-to-groups-based-on-user-account-attributes"></a>Optional: Dynamische Gruppenmitgliedschaftseinstellungen fügen Benutzerkonten automatisch basierend auf Benutzerkontoattributen zu Gruppen hinzu

Sie haben den Satz von dynamischen Azure AD-Gruppen bestimmt und nach den Anweisungen in [Erstellen attributbasierter Regeln für dynamische Gruppenmitgliedschaft in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-groups-dynamic-membership-azure-portal) die Gruppen und die Regeln erstellt, die den Satz von Benutzerkontoattributen und Werten für die Gruppenmitgliedschaft bestimmen.

Wenn Sie diese Option überspringen, muss die Gruppenmitgliedschaft manuell vorgenommen werden, wenn neue Konten hinzugefügt oder Benutzerkontoattribute im Lauf der Zeit geändert werden. Wenn beispielsweise eine Person aus der Vertriebsabteilung in die Buchhaltung wechselt, müssen Sie Folgendes tun:

- Aktualisieren Sie den Wert des Attributs „Abteilung“ für dieses Benutzerkonto.
- Entfernen Sie es manuell aus der Gruppe „Vertrieb“.
- Fügen Sie es manuell der Gruppe „Buchhaltung“ hinzu.

Wenn die Gruppen „Vertrieb“ und „Buchhaltung“ dynamisch wären, müssten Sie nur den Wert „Abteilung“ für das Benutzerkonto ändern.

Gegebenenfalls hilft Ihnen [Schritt 5](identity-use-group-management.md#identity-dyn-groups) bei dieser Option.

### <a name="how-to-test"></a>Testen

1. Erstellen Sie eine dynamische Testgruppe in Azure AD mit dem Azure-Portal, und konfigurieren Sie eine Regel für den Abteilungswert „test1“.
2. Erstellen Sie ein Testbenutzerkonto in Azure AD, und legen Sie die Eigenschaft „Abteilung“ auf „test1“ fest.
3. Untersuchen Sie die Eigenschaften des Benutzerkontos, um sicherzustellen, dass es ein Mitglied der dynamischen Testgruppe ist.
4. Ändern Sie den Wert der Eigenschaft „Abteilung“ für das Testbenutzerkonto in „test2“.
5. Untersuchen Sie die Eigenschaften des Benutzerkontos, um sicherzustellen, dass es kein Mitglied der dynamischen Testgruppe mehr ist.
6. Löschen Sie die dynamische Testgruppe und das Testbenutzerkonto.

<a name="crit-identity-group-license"></a>
## <a name="optional-group-based-licensing-to-automatically-assign-and-remove-licenses-to-user-accounts-based-on-group-membership"></a>Optional: Gruppenbasierte Lizenzierung für automatisches Zuweisen und Entfernen von Lizenzen zu Benutzerkonten basierend auf der Gruppenmitgliedschaft

Sie haben für die entsprechenden Azure AD-Sicherheitsgruppen [gruppenbasierte Lizenzierung aktiviert](https://docs.microsoft.com/azure/active-directory/active-directory-licensing-group-assignment-azure-portal), damit Ihre Microsoft 365 Enterprise-Lizenzen automatisch zugewiesen oder entfernt werden.

Wenn Sie diese Option überspringen, müssen Sie Folgendes manuell ausführen:

- Zuweisen von Lizenzen für neue Benutzer, die Zugriff haben sollen.
- Entfernen von Lizenzen von Benutzern, die nicht mehr in Ihrer Organisation sind oder keinen Zugriff haben.

Gegebenenfalls hilft Ihnen [Schritt 5](identity-use-group-management.md#identity-group-license) bei dieser Option.

### <a name="how-to-test"></a>Testen

1. Erstellen Sie eine Testsicherheitsgruppe in Azure AD mit dem Azure-Portal, und konfigurieren Sie die gruppenbasierte Lizenzierung, um Microsoft 365 Enterprise-Lizenzen zuzuweisen.
2. Erstellen Sie ein Testbenutzerkonto in Azure AD, und fügen Sie es der Testsicherheitsgruppe hinzu.
3. Untersuchen Sie die Eigenschaften des Benutzerkontos im Microsoft 365 Admin Center, um zu überprüfen, ob dem Konto die Microsoft 365 Enterprise-Lizenzen zugewiesen wurden.
4. Entfernen Sie das Testbenutzerkonto aus der Testsicherheitsgruppe.
5. Untersuchen Sie die Eigenschaften des Benutzerkontos, um zu überprüfen, ob ihm die Microsoft 365 Enterprise-Lizenzen nicht mehr zugewiesen sind.
6. Löschen Sie die Testsicherheitsgruppe und das Testbenutzerkonto.


<a name="crit-identity-access-reviews"></a>
## <a name="optional-access-reviews-configured-and-being-used-to-monitor-access"></a>Optional: Zugriffsüberprüfungen, die für die Überwachung des Zugriffs konfiguriert und verwendet werden

Sie haben diese Artikel zum Konfigurieren verschiedener Typen von Zugriffsüberprüfungen zum Überwachen der Gruppenmitgliedschaften, des Zugriffs auf Unternehmensanwendungen und der Rollenzuweisungen verwendet:

- [Gruppen und Apps](https://docs.microsoft.com/azure/active-directory/governance/create-access-review)
- [Azure AD-Rollen](https://docs.microsoft.com/azure/active-directory/privileged-identity-management/pim-how-to-start-security-review?toc=%2fazure%2factive-directory%2fgovernance%2ftoc.json)
- [Azure-Ressourcenrollen](https://docs.microsoft.com/azure/active-directory/privileged-identity-management/pim-resource-roles-start-access-review?toc=%2fazure%2factive-directory%2fgovernance%2ftoc.json)

Gegebenenfalls hilft Ihnen [Schritt 6](identity-configure-identity-governance.md#identity-access-reviews) bei dieser Option.


## <a name="results-and-next-steps"></a>Ergebnisse und nächste Schritte

Ihre Identitätsinfrastruktur in der Microsoft 365-Cloud verwendet starke Authentifizierung, geschützte Administratorkonten und vereinfachten Benutzerzugriff und vereinfachte Benutzerverwaltung.

|||
|:-------|:-----|
|![Phase 3: Windows 10 Enterprise](./media/deploy-foundation-infrastructure/win10enterprise_icon-small.png)| Wenn Sie den Phasen für die Ende-zu-Ende-Bereitstellung von Microsoft 365 Enterprise folgen, ist die nächste Phase [Windows 10 Enterprise](windows10-infrastructure.md). |

