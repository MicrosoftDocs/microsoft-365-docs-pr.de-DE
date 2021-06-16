---
title: Schützen Ihrer Microsoft 365 globalen Administratorkonten
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/30/2020
audience: Admin
ms.topic: article
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
description: Dieser Artikel enthält Informationen zum Schutz des globalen Administratorzugriffs auf Ihr Microsoft 365 Abonnement.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 1c929651f3e70a1aeef16cdf48d853d675820833
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/14/2021
ms.locfileid: "52926547"
---
# <a name="protect-your-microsoft-365-global-administrator-accounts"></a>Schützen Ihrer Microsoft 365 globalen Administratorkonten

*Dieser Artikel gilt sowohl für Microsoft 365 Enterprise als auch für Office 365 Enterprise.*

Sicherheitsverletzungen eines Microsoft 365-Abonnements, einschließlich Informationssammel- und Phishingangriffe, werden in der Regel durch Kompromittierung der Anmeldeinformationen eines Microsoft 365 globalen Administratorkontos ausgeführt. Sicherheit in der Cloud ist eine Partnerschaft zwischen Ihnen und Microsoft:
  
- Microsoft Cloud Services basieren auf einer Grundlage von Vertrauen und Sicherheit. Microsoft bietet Ihnen Sicherheitskontrollen und -funktionen zum Schutz Ihrer Daten und Anwendungen.
    
- Sie besitzen Ihre Daten und Identitäten und die Verantwortung für deren Schutz, die Sicherheit Ihrer lokalen Ressourcen und die Sicherheit von Cloudkomponenten, die Sie steuern.
    
Microsoft bietet Funktionen zum Schutz Ihrer Organisation, sie sind jedoch nur wirksam, wenn Sie sie verwenden. Wenn Sie sie nicht verwenden, sind Sie möglicherweise anfällig für Angriffe. Um Ihre globalen Administratorkonten zu schützen, ist Microsoft hier, um Ihnen mit detaillierten Anweisungen zu helfen:
  
1. Erstellen Sie dedizierte Microsoft 365 globalen Administratorkonten, und verwenden Sie sie nur bei Bedarf.
    
2. Konfigurieren Sie die mehrstufige Authentifizierung für Ihre dedizierten Microsoft 365 globalen Administratorkonten, und verwenden Sie die stärkste Form der sekundären Authentifizierung.
    
> [!Note]
> Obwohl sich dieser Artikel auf globale Administratorkonten konzentriert, sollten Sie überlegen, ob zusätzliche Konten mit umfassenden Berechtigungen für den Zugriff auf die Daten in Ihrem Abonnement, z. B. eDiscovery-Administrator- oder Sicherheits- oder Complianceadministratorkonten, auf die gleiche Weise geschützt werden sollten. <br > Ein globales Administratorkonto kann erstellt werden, ohne Lizenzen hinzuzufügen.
  
## <a name="step-1-create-dedicated-microsoft-365-global-administrator-accounts-and-use-them-only-when-necessary"></a>Schritt 1. Erstellen sie dedizierte Microsoft 365 globalen Administratorkonten, und verwenden Sie sie nur bei Bedarf.

Es gibt relativ wenige administrative Aufgaben, z. B. das Zuweisen von Rollen zu Benutzerkonten, die globale Administratorrechte erfordern. Führen Sie daher die folgenden Schritte aus, anstatt normale Benutzerkonten zu verwenden, denen die globale Administratorrolle zugewiesen wurde:
  
1. Bestimmen Sie den Satz von Benutzerkonten, denen die globale Administratorrolle zugewiesen wurde. Sie können dies im Microsoft 365 Admin Center oder mit dem folgenden Azure Active (Azure AD)-Verzeichnis-PowerShell für Graph Befehl ausführen:
  
  ```powershell
  Get-AzureADDirectoryRole | where { $_.DisplayName -eq "Global Administrator" } | Get-AzureADDirectoryRoleMember | Ft DisplayName
  ```

2. Melden Sie sich bei Ihrem Microsoft 365-Abonnement mit einem Benutzerkonto an, dem die globale Administratorrolle zugewiesen wurde.
    
3. Erstellen Sie bis zu vier dedizierte globale Administratorbenutzerkonten. **Verwenden Sie sichere Kennwörter, die mindestens 12 Zeichen lang sind.** Weitere Informationen finden Sie unter [Erstellen eines sicheren Kennworts.](https://support.microsoft.com/help/4026406/microsoft-account-create-a-strong-password) Store die Kennwörter für die neuen Konten an einem sicheren Ort an. 
    
4. Weisen Sie die rolle des globalen Administrators jedem der neuen dedizierten globalen Administratorbenutzerkonten zu.
    
5. Melden Sie sich von Microsoft 365 ab.
    
6. Melden Sie sich mit einem der neuen dedizierten globalen Administratorbenutzerkonten an.
    
7. Für jedes vorhandene Benutzerkonto, dem die globale Administratorrolle aus Schritt 1 zugewiesen wurde:
    
  - Entfernen Sie die globale Administratorrolle.
    
  - Weisen Sie dem Konto Administratorrollen zu, die der Aufgabenfunktion und Zuständigkeit dieses Benutzers entsprechen. Weitere Informationen zu verschiedenen Administratorrollen in Microsoft 365 finden Sie unter [Informationen zu Administratorrollen.](/office365/admin/add-users/about-admin-roles)
    
8. Melden Sie sich von Microsoft 365 ab.
    
Die Ergebnisse sollten folgendermaßen sein:
  
- Die einzigen Benutzerkonten in Ihrem Abonnement, die über die Berechtigungen eines globalen Administrators verfügen, befinden sich im neuen Satz der dedizierten Konten für globale Administratoren. Überprüfen Sie dies mit dem folgenden PowerShell-Befehl:
    
  ```powershell
  Get-AzureADDirectoryRole | where { $_.DisplayName -eq "Company Administrator" } | Get-AzureADDirectoryRoleMember | Ft DisplayName
  ```

- Alle anderen normalen Benutzerkonten für die Verwaltung Ihres Abonnements verfügen über Administratorrollen, die ihren beruflichen Zuständigkeiten zugewiesen sind.
    
Ab diesem Zeitpunkt melden Sie sich mit den dedizierten globalen Administratorkonten nur für Aufgaben an, die globale Administratorrechte erfordern. Alle anderen Microsoft 365 Verwaltung müssen durch Zuweisen anderer Administratorrollen zu Benutzerkonten erfolgen.
  
> [!NOTE]
> Dies erfordert zusätzliche Schritte, um sich als normales Benutzerkonto abmelden und sich mit einem dedizierten globalen Administratorkonto anmelden zu können. Dies muss jedoch nur gelegentlich für globale Administratorvorgänge erfolgen. Bedenken Sie, dass die Wiederherstellung Ihres Microsoft 365-Abonnements nach einer Verletzung des globalen Administratorkontos viel mehr Schritte erfordert.
  
## <a name="step-2-configure-multi-factor-authentication-for-your-dedicated-microsoft-365-global-administrator-accounts"></a>Schritt 2. Konfigurieren der mehrstufigen Authentifizierung für Ihre dedizierten Microsoft 365 globalen Administratorkonten

Die mehrstufige Authentifizierung (Multi-Factor Authentication, MFA) erfordert zusätzliche Informationen, die über den Kontonamen und das Kennwort hinausgehen. Microsoft 365 unterstützt diese zusätzlichen Überprüfungsmethoden:
  
- Der Microsoft Authenticator-App

- Ein Telefonanruf
    
- Ein zufällig generierter Überprüfungscode, der über eine Textnachricht gesendet wird
    
- Eine Smartcard (virtuell oder physisch)
    
- Ein biometrisches Gerät
    
>[!Note]
>Für Organisationen, die den Standards des National Institute of Standards and Technology (NIST) entsprechen müssen, ist die Verwendung eines Telefonanrufs oder smsbasierter zusätzlicher Überprüfungsmethoden eingeschränkt. Klicken Sie [hier,](https://pages.nist.gov/800-63-FAQ/#q-b01) um die Details zu erhalten.
>

Wenn Sie ein kleines Unternehmen sind, das nur in der Cloud gespeicherte Benutzerkonten verwendet (das reine Cloudidentitätsmodell), richten Sie MFA ein, um [MFA](/office365/admin/security-and-compliance/set-up-multi-factor-authentication) mithilfe eines Telefonanrufs oder eines Sms-Überprüfungscodes zu konfigurieren, der für jedes dedizierte globale Administratorkonto an ein Smartphone gesendet wird.
    
Wenn Sie eine größere Organisation sind, die ein Microsoft 365 Hybrididentitätsmodell verwendet, haben Sie mehr Überprüfungsoptionen. Wenn Sie die Sicherheitsinfrastruktur bereits für eine stärkere sekundäre Authentifizierungsmethode eingerichtet haben, [richten Sie MFA ein,](../admin/security-and-compliance/set-up-multi-factor-authentication.md) und konfigurieren Sie jedes dedizierte globale Administratorkonto für die entsprechende Überprüfungsmethode.
  
Wenn die Sicherheitsinfrastruktur für die gewünschte stärkere Überprüfungsmethode nicht vorhanden ist und für Microsoft 365 MFA funktioniert, wird dringend empfohlen, dedizierte globale Administratorkonten mit MFA mithilfe der Microsoft Authenticator-App, eines Telefonanrufs oder eines Sms-Überprüfungscodes, der an ein Smartphone für Ihre globalen Administratorkonten gesendet wird, als vorläufige Sicherheitsmaßnahme zu konfigurieren. Verlassen Sie Ihre dedizierten globalen Administratorkonten nicht ohne den zusätzlichen Schutz durch MFA.
  
Weitere Informationen finden Sie unter [MFA für Microsoft 365](../admin/security-and-compliance/multi-factor-authentication-microsoft-365.md).
  
Informationen zum Herstellen einer Verbindung mit Microsoft 365 Diensten mit MFA und PowerShell finden Sie in den folgenden Artikeln:

- [PowerShell für Microsoft 365 für Benutzerkonten, Gruppen und Lizenzen](connect-to-microsoft-365-powershell.md)
- [Microsoft Teams](/microsoftteams/teams-powershell-install)
- [Exchange Online](/powershell/exchange/mfa-connect-to-exchange-online-powershell#connect-to-exchange-online-powershell-using-mfa)
- [SharePoint Online](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online#to-connect-with-multifactor-authentication-mfa)
- [Skype for Business Online](manage-skype-for-business-online-with-microsoft-365-powershell.md#connect-using-an-admin-account-with-multi-factor-authentication)

## <a name="additional-protections-for-enterprise-organizations"></a>Zusätzliche Schutzmaßnahmen für Unternehmen

Verwenden Sie diese zusätzlichen Methoden, um sicherzustellen, dass Ihr globales Administratorkonto und die Konfiguration, die Sie mit ihm ausführen, so sicher wie möglich sind.
  
### <a name="privileged-access-workstation"></a>Arbeitsstation mit privilegiertem Zugriff

Um sicherzustellen, dass die Ausführung von Aufgaben mit hoher Berechtigung so sicher wie möglich ist, verwenden Sie eine Workstation mit privilegiertem Zugriff (PRIVILEGED Access Workstation, PAW). Ein PAW ist ein dedizierter Computer, der nur für vertrauliche Konfigurationsaufgaben verwendet wird, z. B. Microsoft 365 Konfiguration, die ein globales Administratorkonto erfordert. Da dieser Computer nicht täglich für internetbrowsen oder E-Mails verwendet wird, ist er besser vor Internetangriffen und Bedrohungen geschützt.
  
Anweisungen zum Einrichten eines PAW finden Sie unter [https://aka.ms/cyberpaw](/security/compass/privileged-access-devices) .

Weitere Informationen zum Aktivieren von Azure PIM für Ihren Azure AD-Mandanten und für Administratorkonten finden Sie unter [Schritte zum Konfigurieren von PIM](/azure/active-directory/active-directory-privileged-identity-management-configure).

Weitere Informationen zum Entwickeln einer Roadmap, um den privilegierten Zugriff vor Cyberangriffen schützt, finden Sie unter [Schützen des privilegierten Zugriffs für hybride Cloudbereitstellungen in Azure AD](/azure/active-directory/admin-roles-best-practices).

### <a name="azure-ad-privileged-identity-management"></a>Azure AD Privileged Identity Management

Anstatt Ihren globalen Administratorkonten die globale Administratorrolle dauerhaft zuzuweisen, können Sie Azure AD Privileged Identity Management (PIM) verwenden, um die Just-in-Time-Zuweisung der globalen Administratorrolle bei Bedarf bei Bedarf zu aktivieren.
  
Ihre globalen Administratorkonten wechseln von permanenten Administratoren zu berechtigten Administratoren. Die rolle des globalen Administrators ist inaktiv, bis jemand sie benötigt. Anschließend führen Sie einen Aktivierungsprozess aus, um die globale Administratorrolle für einen vordefinierten Zeitraum dem globalen Administratorkonto hinzuzufügen. Wenn die Zeit abläuft, entfernt PIM die globale Administratorrolle aus dem globalen Administratorkonto.
  
Durch die Verwendung von PIM und diesem Prozess wird die Zeit, in der Ihre globalen Administratorkonten anfällig für Angriffe und die Verwendung durch böswillige Benutzer sind, erheblich reduziert.

PIM ist im Lieferumfang von Azure Active Directory Premium P2 verfügbar, das im Lieferumfang von Microsoft 365 E5 enthalten ist. Alternativ hierzu können Sie einzelne Azure Active Directory Premium P2-Lizenzen für Ihre Administratorkonten erwerben.
  
Weitere Informationen finden Sie unter [Azure AD Privileged Identity Management.](/azure/active-directory/active-directory-privileged-identity-management-configure)
  

### <a name="privileged-access-management"></a>Privileged Access Management

Privileged Access Management wird durch Konfigurieren von Richtlinien aktiviert, die Just-in-Time-Zugriff für aufgabenbasierte Aktivitäten in Ihrem Mandanten angeben. Dadurch kann Ihre Organisation vor Sicherheitsverletzungen geschützt werden, bei denen vorhandene Privileged Access Management-Konten mit ständigem Zugriff auf vertrauliche Daten oder Zugriff auf kritische Konfigurationseinstellungen verwenden. Sie könnten beispielsweise eine Privileged Access Management-Richtlinie konfigurieren, die für den Zugriff und das Ändern von Postfacheinstellungen in der Organisation eine explizite Genehmigung in Ihrem Mandanten benötigt.

In diesem Schritt aktivieren Sie Privileged Access Management in Ihrem Mandanten und konfigurieren Richtlinien für privilegierten Zugriff, die zusätzliche Sicherheit für aufgabenbasierten Zugriff auf Daten und Konfigurationseinstellungen für Ihre Organisation bereitstellen. Es gibt drei grundlegende Schritte, um mit dem privilegierten Zugriff in Ihrer Organisation zu beginnen:

- Erstellen einer Gruppe einer genehmigenden Person
- Aktivieren des privilegierten Zugriffs
- Erstellen von Genehmigungsrichtlinien

Die Verwaltung des privilegierten Zugriffs ermöglicht Es Ihrer Organisation, mit null ständigen Berechtigungen zu arbeiten und eine Schutzebene gegen Sicherheitsrisiken bereitzustellen, die aufgrund eines solchen ständigen administrativen Zugriffs entstehen. Privilegierter Zugriff erfordert Genehmigungen für die Ausführung von Aufgaben, für die eine zugehörige Genehmigungsrichtlinie definiert ist. Benutzer, die Aufgaben ausführen müssen, die in der Genehmigungsrichtlinie enthalten sind, müssen die Zugriffsgenehmigung anfordern und erhalten diese.

Informationen zum Aktivieren der Verwaltung des privilegierten Zugriffs finden Sie unter Konfigurieren der [Verwaltung des privilegierten Zugriffs.](/office365/securitycompliance/privileged-access-management-configuration)

Weitere Informationen finden Sie unter [Privileged Access Management](/office365/securitycompliance/privileged-access-management-overview).

### <a name="security-information-and-event-management-siem-software-for-microsoft-365-logging"></a>SIEM-Software (Security Information and Event Management) für Microsoft 365 Protokollierung

Siem-Software, die auf einem Server ausgeführt wird, führt eine Echtzeitanalyse von Sicherheitswarnungen und -ereignissen durch, die von Anwendungen und Netzwerkhardware erstellt wurden. Damit Ihr SIEM-Server Microsoft 365 Sicherheitswarnungen und -ereignisse in die Analyse- und Berichtsfunktionen aufnehmen kann, integrieren Sie Azure AD in Ihr SEIM. Siehe [Einführung in Azure Log Integration](/azure/security/security-azure-log-integration-overview).

## <a name="next-step"></a>Nächster Schritt

Wenn Sie die Identität für Ihr Microsoft 365-Abonnement einrichten, lesen Sie Folgendes:

- [Reine Cloudidentitäten,](cloud-only-identities.md) wenn Sie reine Cloudidentität verwenden
- [Vorbereiten der Verzeichnissynchronisierung](prepare-for-directory-synchronization.md) bei Verwendung der Hybrididentität

  
## <a name="see-also"></a>Siehe auch

[Microsoft 365-Sicherheits-Roadmap](/office365/securitycompliance/security-roadmap)