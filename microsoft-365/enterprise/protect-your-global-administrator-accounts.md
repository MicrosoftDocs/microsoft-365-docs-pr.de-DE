---
title: Schützen Ihrer globalen Microsoft 365-Administratorkonten
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/30/2020
audience: Admin
ms.topic: get-started-article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- m365initiative-coredeploy
search.appverid:
- MET150
- MOE150
- MED150
- MBS150
- BCS160
f1.keywords:
- NOCSH
ms.assetid: 6b4ded77-ac8d-42ed-8606-c014fd947560
description: Dieser Artikel enthält Informationen zum Schutz des globalen Administratorzugriffs auf Ihr Microsoft 365-Abonnement.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 4ade5fd8070a656f976caa75c16ab92cadb7b64a
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50929048"
---
# <a name="protect-your-microsoft-365-global-administrator-accounts"></a>Schützen Ihrer globalen Microsoft 365-Administratorkonten

*Dieser Artikel gilt sowohl für Microsoft 365 Enterprise als auch für Office 365 Enterprise.*

Sicherheitsverletzungen eines Microsoft 365-Abonnements, einschließlich der Informationsernte und Phishingangriffe, werden in der Regel durch Kompromittieren der Anmeldeinformationen eines globalen Microsoft 365-Administratorkontos durchgeführt. Sicherheit in der Cloud ist eine Partnerschaft zwischen Ihnen und Microsoft:
  
- Microsoft Cloud Services sind auf einer Grundlage von Vertrauen und Sicherheit aufgebaut. Microsoft bietet Ihnen Sicherheitssteuerelemente und -funktionen, mit deren Hilfe Sie Ihre Daten und Anwendungen schützen können.
    
- Sie besitzen Ihre Daten und Identitäten und die Verantwortung für ihren Schutz, die Sicherheit Ihrer lokalen Ressourcen und die Sicherheit der von Ihnen kontrollierten Cloudkomponenten.
    
Microsoft bietet Funktionen zum Schutz Ihrer Organisation, die jedoch nur dann wirksam sind, wenn Sie sie verwenden. Wenn Sie sie nicht verwenden, sind Sie möglicherweise anfällig für Angriffe. Um Ihre globalen Administratorkonten zu schützen, ist Microsoft hier, um Ihnen mit detaillierten Anweisungen zu helfen:
  
1. Erstellen Sie dedizierte globale Microsoft 365-Administratorkonten, und verwenden Sie sie nur bei Bedarf.
    
2. Konfigurieren Sie die mehrstufige Authentifizierung für Ihre dedizierten globalen Microsoft 365-Administratorkonten, und verwenden Sie die stärkste Form der sekundären Authentifizierung.
    
> [!Note]
> Obwohl sich dieser Artikel auf globale Administratorkonten konzentriert, sollten Sie berücksichtigen, ob zusätzliche Konten mit umfassenden Berechtigungen für den Zugriff auf die Daten in Ihrem Abonnement, z. B. eDiscovery-Administrator- oder Sicherheits- oder Complianceadministratorkonten, auf die gleiche Weise geschützt werden sollten. <br > Ein globales Administratorkonto kann ohne Hinzufügen von Lizenzen erstellt werden.
  
## <a name="step-1-create-dedicated-microsoft-365-global-administrator-accounts-and-use-them-only-when-necessary"></a>Schritt 1: Erstellen dedizierter globaler Microsoft 365-Administratorkonten und deren Verwendung nur bei Bedarf

Es gibt relativ wenige administrative Aufgaben, z. B. das Zuweisen von Rollen zu Benutzerkonten, die globale Administratorrechte erfordern. Gehen Sie daher wie die folgenden Schritte vor, anstatt alltägliche Benutzerkonten zu verwenden, denen die globale Administratorrolle zugewiesen wurde:
  
1. Bestimmen Sie den Satz von Benutzerkonten, denen die globale Administratorrolle zugewiesen wurde. Sie können dies im Microsoft 365 Admin Center oder mit dem folgenden Azure Active (Azure AD)-Verzeichnis-PowerShell für Graph-Befehl tun:
  
  ```powershell
  Get-AzureADDirectoryRole | where { $_.DisplayName -eq "Global Administrator" } | Get-AzureADDirectoryRoleMember | Ft DisplayName
  ```

2. Melden Sie sich bei Ihrem Microsoft 365-Abonnement mit einem Benutzerkonto an, dem die globale Administratorrolle zugewiesen wurde.
    
3. Erstellen Sie bis zu vier dedizierte globale Administratorbenutzerkonten. **Verwenden Sie sichere Kennwörter mit einer Länge von mindestens 12 Zeichen.** Weitere [Informationen finden Sie unter Erstellen](https://support.microsoft.com/help/4026406/microsoft-account-create-a-strong-password) eines starken Kennworts. Speichern Sie die Kennwörter für die neuen Konten an einem sicheren Ort. 
    
4. Weisen Sie die globale Administratorrolle jedem der neuen dedizierten globalen Administratorbenutzerkonten zu.
    
5. Melden Sie sich bei Microsoft 365 ab.
    
6. Melden Sie sich mit einem der neuen dedizierten globalen Administratorbenutzerkonten an.
    
7. Für jedes vorhandene Benutzerkonto, dem die globale Administratorrolle aus Schritt 1 zugewiesen wurde:
    
  - Entfernen Sie die globale Administratorrolle.
    
  - Weisen Sie dem Konto Administratorrollen zu, die für die Auftragsfunktion und -verantwortung dieses Benutzers geeignet sind. Weitere Informationen zu verschiedenen Administratorrollen in Microsoft 365 finden Sie unter [Informationen zu Administratorrollen](/office365/admin/add-users/about-admin-roles).
    
8. Melden Sie sich bei Microsoft 365 ab.
    
Die Ergebnisse sollten:
  
- Die einzigen Benutzerkonten in Ihrem Abonnement, die über die Berechtigungen eines globalen Administrators verfügen, befinden sich im neuen Satz der dedizierten Konten für globale Administratoren. Überprüfen Sie dies mit dem folgenden PowerShell-Befehl:
    
  ```powershell
  Get-AzureADDirectoryRole | where { $_.DisplayName -eq "Company Administrator" } | Get-AzureADDirectoryRoleMember | Ft DisplayName
  ```

- Alle anderen normalen Benutzerkonten für die Verwaltung Ihres Abonnements verfügen über Administratorrollen, die ihren beruflichen Zuständigkeiten zugewiesen sind.
    
Ab diesem Moment melden Sie sich mit den dedizierten globalen Administratorkonten nur für Aufgaben an, für die globale Administratorrechte erforderlich sind. Alle anderen Microsoft 365-Verwaltungen müssen durch Zuweisen anderer Verwaltungsrollen zu Benutzerkonten durchgeführt werden.
  
> [!NOTE]
> Dies erfordert zusätzliche Schritte, um sich als Ihr tägliches Benutzerkonto abmelden und sich mit einem dedizierten globalen Administratorkonto anmelden zu können. Dies muss jedoch nur gelegentlich für globale Administratorvorgänge durchgeführt werden. Bedenken Sie, dass die Wiederherstellung Ihres Microsoft 365-Abonnements nach einer Verletzung eines globalen Administratorkontos sehr viel mehr Schritte erfordert.
  
## <a name="step-2-configure-multi-factor-authentication-for-your-dedicated-microsoft-365-global-administrator-accounts"></a>Schritt 2: Konfigurieren der mehrstufigen Authentifizierung für Ihre dedizierten globalen Microsoft 365-Administratorkonten

Die mehrstufige Authentifizierung (Multi-Factor Authentication, MFA) erfordert zusätzliche Informationen über den Kontonamen und das Kennwort hinaus. Microsoft 365 unterstützt die folgenden zusätzlichen Überprüfungsmethoden:
  
- Der Microsoft Authenticator-App

- Ein Telefonanruf
    
- Ein zufällig generierter Überprüfungscode, der über eine Textnachricht gesendet wird
    
- Eine Smartcard (virtuell oder physisch)
    
- Ein biometrisches Gerät
    
>[!Note]
>Für Organisationen, die die Standards des National Institute of Standards and Technology (NIST) einhalten müssen, ist die Verwendung eines Telefonanrufs oder einer smsbasierten zusätzlichen Überprüfungsmethode eingeschränkt. Klicken [Sie hier,](https://pages.nist.gov/800-63-FAQ/#q-b01) um die Details zu erhalten.
>

Wenn Sie ein kleines Unternehmen sind, das benutzerkonten verwendet, die nur in der Cloud gespeichert sind (das nur in der Cloud enthaltene Identitätsmodell), richten Sie MFA ein, um [MFA](/office365/admin/security-and-compliance/set-up-multi-factor-authentication) mithilfe eines Telefonanrufs oder eines Textnachrichtenüberprüfungscodes zu konfigurieren, der für jedes dedizierte globale Administratorkonto an ein Smartphone gesendet wird.
    
Wenn Sie eine größere Organisation sind, die ein Microsoft 365-Hybrididentitätsmodell verwendet, haben Sie mehr Überprüfungsoptionen. Wenn Sie bereits über die Sicherheitsinfrastruktur für eine stärkere sekundäre Authentifizierungsmethode verfügen, richten Sie [MFA ein,](../admin/security-and-compliance/set-up-multi-factor-authentication.md) und konfigurieren Sie jedes dedizierte globale Administratorkonto für die entsprechende Überprüfungsmethode.
  
Wenn die Sicherheitsinfrastruktur für die gewünschte strengere Überprüfungsmethode nicht für Microsoft 365 MFA verfügbar ist und funktioniert, wird dringend empfohlen, dedizierte globale Administratorkonten mit MFA mithilfe der Microsoft Authenticator-App, eines Telefonanrufs oder eines Textnachrichtüberprüfungscodes zu konfigurieren, der für Ihre globalen Administratorkonten an ein Smartphone gesendet wird. Verlassen Sie ihre dedizierten globalen Administratorkonten nicht ohne den zusätzlichen Schutz, der von MFA bereitgestellt wird.
  
Weitere Informationen finden Sie unter [MFA für Microsoft 365](../admin/security-and-compliance/multi-factor-authentication-microsoft-365.md).
  
Informationen zum Herstellen einer Verbindung mit Microsoft 365-Diensten mit MFA und PowerShell finden Sie in den folgenden Artikeln:

- [PowerShell für Microsoft 365 für Benutzerkonten, Gruppen und Lizenzen](connect-to-microsoft-365-powershell.md)
- [Microsoft Teams](/microsoftteams/teams-powershell-install)
- [Exchange Online](/powershell/exchange/mfa-connect-to-exchange-online-powershell#connect-to-exchange-online-powershell-using-mfa)
- [SharePoint Online](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online#to-connect-with-multifactor-authentication-mfa)
- [Skype for Business Online](manage-skype-for-business-online-with-microsoft-365-powershell.md#connect-using-an-admin-account-with-multi-factor-authentication)

## <a name="additional-protections-for-enterprise-organizations"></a>Zusätzliche Schutzmaßnahmen für Unternehmensorganisationen

Verwenden Sie diese zusätzlichen Methoden, um sicherzustellen, dass Ihr globales Administratorkonto und die konfiguration, die Sie verwenden, so sicher wie möglich sind.
  
### <a name="privileged-access-workstation"></a>Arbeitsstation mit privilegiertem Zugriff

Um sicherzustellen, dass die Ausführung von Aufgaben mit besonders privilegierten Berechtigungen so sicher wie möglich ist, verwenden Sie eine Workstation mit privilegiertem Zugriff (Privileged Access Workstation, PAW). Eine PAW ist ein dedizierter Computer, der nur für vertrauliche Konfigurationsaufgaben verwendet wird, z. B. microsoft 365-Konfiguration, für die ein globales Administratorkonto erforderlich ist. Da dieser Computer nicht täglich für Internetbrowsen oder E-Mails verwendet wird, ist er besser vor Internetangriffen und Bedrohungen geschützt.
  
Anweisungen zum Einrichten einer PAW finden Sie unter [https://aka.ms/cyberpaw](/security/compass/privileged-access-devices) .

Weitere Informationen zum Aktivieren von Azure PIM für Ihren Azure AD-Mandanten und für Administratorkonten finden Sie unter [Schritte zum Konfigurieren von PIM](/azure/active-directory/active-directory-privileged-identity-management-configure).

Weitere Informationen zum Entwickeln einer Roadmap, um den privilegierten Zugriff vor Cyberangriffen schützt, finden Sie unter [Schützen des privilegierten Zugriffs für hybride Cloudbereitstellungen in Azure AD](/azure/active-directory/admin-roles-best-practices).

### <a name="azure-ad-privileged-identity-management"></a>Azure AD Privileged Identity Management

Anstatt Ihren globalen Administratorkonten dauerhaft die rolle des globalen Administrators zu zuweisen, können Sie Azure AD Privileged Identity Management (PIM) verwenden, um bei Bedarf die Just-in-Time-Zuweisung der globalen Administratorrolle zu aktivieren.
  
Ihre globalen Administratorkonten gehen von permanenten Administratoren zu berechtigten Administratoren. Die rolle des globalen Administrators ist inaktiv, bis jemand sie benötigt. Anschließend führen Sie einen Aktivierungsprozess aus, um dem globalen Administratorkonto für einen vordefinierten Zeitraum die globale Administratorrolle hinzuzufügen. Wenn die Zeit abläuft, entfernt PIM die rolle des globalen Administrators aus dem globalen Administratorkonto.
  
Durch die Verwendung von PIM und diesem Prozess wird die Zeit, für die Ihre globalen Administratorkonten anfällig für Angriffe und die Verwendung durch böswillige Benutzer sind, erheblich reduziert.

PIM ist im Lieferumfang von Azure Active Directory Premium P2 verfügbar, das im Lieferumfang von Microsoft 365 E5 enthalten ist. Alternativ hierzu können Sie einzelne Azure Active Directory Premium P2-Lizenzen für Ihre Administratorkonten erwerben.
  
Weitere Informationen finden Sie unter [Azure AD Privileged Identity Management](/azure/active-directory/active-directory-privileged-identity-management-configure).
  

### <a name="privileged-access-management"></a>Privileged Access Management

Privileged Access Management wird durch Konfigurieren von Richtlinien aktiviert, die Just-in-Time-Zugriff für aufgabenbasierte Aktivitäten in Ihrem Mandanten angeben. Dadurch kann Ihre Organisation vor Sicherheitsverletzungen geschützt werden, bei denen vorhandene Privileged Access Management-Konten mit ständigem Zugriff auf vertrauliche Daten oder Zugriff auf kritische Konfigurationseinstellungen verwenden. Sie könnten beispielsweise eine Privileged Access Management-Richtlinie konfigurieren, die für den Zugriff und das Ändern von Postfacheinstellungen in der Organisation eine explizite Genehmigung in Ihrem Mandanten benötigt.

In diesem Schritt aktivieren Sie Privileged Access Management in Ihrem Mandanten und konfigurieren Richtlinien für privilegierten Zugriff, die zusätzliche Sicherheit für aufgabenbasierten Zugriff auf Daten und Konfigurationseinstellungen für Ihre Organisation bereitstellen. Es gibt drei grundlegende Schritte, um mit dem privilegierten Zugriff in Ihrer Organisation zu beginnen:

- Erstellen einer Gruppe einer genehmigenden Person
- Aktivieren des privilegierten Zugriffs
- Erstellen von Genehmigungsrichtlinien

Die Verwaltung privilegierter Zugriffe ermöglicht Es Ihrer Organisation, mit null stehenden Rechten zu arbeiten und eine Schutzebene gegen Sicherheitsrisiken zu bieten, die aufgrund eines solchen ständigen Administrativen Zugriffs entstehen. Für den privilegierten Zugriff sind Genehmigungen für die Ausführung von Vorgängen erforderlich, für die eine zugehörige Genehmigungsrichtlinie definiert ist. Benutzer, die Aufgaben ausführen müssen, die in der Genehmigungsrichtlinie enthalten sind, müssen die Zugriffsgenehmigung anfordern und erhalten diese.

Informationen zum Aktivieren der Verwaltung des privilegierten Zugriffs finden Sie unter [Configure privileged access management](/office365/securitycompliance/privileged-access-management-configuration).

Weitere Informationen finden Sie unter [Privileged access management](/office365/securitycompliance/privileged-access-management-overview).

### <a name="security-information-and-event-management-siem-software-for-microsoft-365-logging"></a>Sicherheitsinformations- und Ereignisverwaltungssoftware (SIEM) für die Microsoft 365-Protokollierung

Die auf einem Server ausgeführte SIEM-Software führt eine Echtzeitanalyse von Sicherheitswarnungen und Ereignissen durch, die von Anwendungen und Netzwerkhardware erstellt wurden. Damit Ihr SIEM-Server Microsoft 365-Sicherheitswarnungen und -ereignisse in seine Analyse- und Berichtsfunktionen integrieren kann, integrieren Sie Azure AD in Sie SEIM. Weitere [Informationen finden Sie unter Introduction to Azure Log Integration](/azure/security/security-azure-log-integration-overview).

## <a name="next-step"></a>Nächster Schritt

Informationen zum Einrichten der Identität für Ihr Microsoft 365-Abonnement finden Sie unter:

- [Nur cloudbasierte Identitäten,](cloud-only-identities.md) wenn Sie nur cloudbasierte Identität verwenden
- [Vorbereiten der Verzeichnissynchronisierung](prepare-for-directory-synchronization.md) bei Verwendung der Hybrididentität

  
## <a name="see-also"></a>Siehe auch

[Microsoft 365 Security Roadmap](/office365/securitycompliance/security-roadmap)