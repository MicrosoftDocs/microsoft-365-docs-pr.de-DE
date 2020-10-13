---
title: Schützen Ihrer globalen Administratorkonten in Microsoft 365
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
ms.openlocfilehash: 15c497e02b139ea6af4aabba9f3e9ab65a1205be
ms.sourcegitcommit: 9a764c2aed7338c37f6e92f5fb487f02b3c4dfa1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/13/2020
ms.locfileid: "48445407"
---
# <a name="protect-your-microsoft-365-global-administrator-accounts"></a>Schützen Ihrer globalen Administratorkonten in Microsoft 365

*Dieser Artikel gilt sowohl für Microsoft 365 Enterprise als auch für Office 365 Enterprise.*

Sicherheitsverletzungen eines Microsoft 365-Abonnements, einschließlich Informationen zum Sammeln und Phishing-Angriffen, werden in der Regel durch Kompromittierung der Anmeldeinformationen eines globalen Microsoft 365-Administratorkontos ausgeführt. Sicherheit in der Cloud ist eine Partnerschaft zwischen Ihnen und Microsoft:
  
- Microsoft-Cloud-Dienste basieren auf einem Fundament aus Vertrauen und Sicherheit. Microsoft stellt Ihnen Sicherheitssteuerelemente und Funktionen zur Verfügung, die Sie beim Schutz Ihrer Daten und Anwendungen unterstützen.
    
- Sie besitzen Ihre Daten und Identitäten sowie die Verantwortung für den Schutz, die Sicherheit Ihrer lokalen Ressourcen und die Sicherheit der von Ihnen kontrollierten Cloud-Komponenten.
    
Microsoft bietet Funktionen zum Schutz Ihrer Organisation, Sie sind jedoch nur wirksam, wenn Sie Sie verwenden. Wenn Sie diese nicht verwenden, sind Sie möglicherweise anfällig für Angriffe. Um Ihre globalen Administratorkonten zu schützen, steht Ihnen Microsoft für detaillierte Anweisungen zur Verfügung:
  
1. Erstellen Sie dedizierte globale Administratorkonten von Microsoft 365, und verwenden Sie Sie nur bei Bedarf.
    
2. Konfigurieren Sie die mehrstufige Authentifizierung für ihre dedizierten globalen Administratorkonten von Microsoft 365, und verwenden Sie die stärkste Form der sekundären Authentifizierung.
    
> [!Note]
> Obwohl sich dieser Artikel auf globale Administratorkonten konzentriert, sollten Sie berücksichtigen, ob zusätzliche Konten mit umfangreichen Berechtigungen für den Zugriff auf die Daten in Ihrem Abonnement wie eDiscovery-Administrator-oder Sicherheits-oder Compliance-Administratorkonten auf die gleiche Weise geschützt werden sollten. <br > Es kann ein globales Administratorkonto erstellt werden, ohne dass Lizenzen hinzugefügt werden.
  
## <a name="step-1-create-dedicated-microsoft-365-global-administrator-accounts-and-use-them-only-when-necessary"></a>Schritt 1: Erstellen Dedizierter globaler Administratorkonten von Microsoft 365, die nur bei Bedarf verwendet werden

Es gibt relativ wenige administrative Aufgaben wie das Zuweisen von Rollen zu Benutzerkonten, die globale Administratorrechte erfordern. Führen Sie daher die folgenden Schritte aus, anstatt alltägliche Benutzerkonten zu verwenden, denen die globale Administratorrolle zugewiesen wurde:
  
1. Bestimmen Sie die Gruppe von Benutzerkonten, denen die globale Administratorrolle zugewiesen wurde. Dies können Sie im Microsoft 365 Admin Center oder mit dem folgenden Azure Active (Azure AD) Directory PowerShell-Befehl für Graph ausführen:
  
  ```powershell
  Get-AzureADDirectoryRole | where { $_.DisplayName -eq "Company Administrator" } | Get-AzureADDirectoryRoleMember | Ft DisplayName
  ```

2. Melden Sie sich bei Ihrem Microsoft 365-Abonnement mit einem Benutzerkonto an, dem die globale Administratorrolle zugewiesen wurde.
    
3. Erstellen Sie bis zu maximal vier dedizierte Benutzerkonten für globale Administratoren. **Verwenden Sie sichere Kennwörter, die mindestens 12 Zeichen lang sind.** Weitere Informationen finden Sie unter [Erstellen eines sicheren Kennworts](https://support.microsoft.com/help/4026406/microsoft-account-create-a-strong-password) . Speichern Sie die Kennwörter für die neuen Konten an einem sicheren Ort. 
    
4. Weisen Sie jedem der neuen dedizierten globalen Administratorbenutzerkonten die globale Administratorrolle zu.
    
5. Melden Sie sich bei Microsoft 365 an.
    
6. Melden Sie sich mit einem der neuen dedizierten globalen Administrator-Benutzerkonten an.
    
7. Für jedes vorhandene Benutzerkonto, dem die globale Administratorrolle aus Schritt 1 zugewiesen wurde:
    
  - Entfernen Sie die globale Administratorrolle.
    
  - Weisen Sie dem Konto Administratorrollen zu, die für die Funktion und Verantwortung dieses Benutzers geeignet sind. Weitere Informationen zu verschiedenen Administratorrollen in Microsoft 365 finden Sie unter [Informationen zu Administratorrollen](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles).
    
8. Melden Sie sich bei Microsoft 365 an.
    
Die Ergebnisse sollten lauten:
  
- Die einzigen Benutzerkonten in Ihrem Abonnement, die über die Berechtigungen eines globalen Administrators verfügen, befinden sich im neuen Satz der dedizierten Konten für globale Administratoren. Überprüfen Sie dies mit dem folgenden PowerShell-Befehl:
    
  ```powershell
  Get-AzureADDirectoryRole | where { $_.DisplayName -eq "Company Administrator" } | Get-AzureADDirectoryRoleMember | Ft DisplayName
  ```

- Alle anderen normalen Benutzerkonten für die Verwaltung Ihres Abonnements verfügen über Administratorrollen, die ihren beruflichen Zuständigkeiten zugewiesen sind.
    
Ab diesem Moment melden Sie sich mit den dedizierten globalen Administratorkonten nur für Aufgaben an, die globale Administratorrechte erfordern. Alle anderen Microsoft 365-Verwaltungsaufgaben müssen durch Zuweisen weiterer Verwaltungsrollen zu Benutzerkonten erfolgen.
  
> [!NOTE]
> Dafür sind zusätzliche Schritte erforderlich, um sich als alltägliches Benutzerkonto abzumelden und sich mit einem dedizierten globalen Administratorkonto anzumelden. Dies muss jedoch nur gelegentlich für globale Administrator Vorgänge erfolgen. Beachten Sie, dass die erneute Bereitstellung Ihres Microsoft 365-Abonnements nach einem Verstoß durch ein globales Administratorkonto viel mehr Schritte erfordert.
  
## <a name="step-2-configure-multi-factor-authentication-for-your-dedicated-microsoft-365-global-administrator-accounts"></a>Schritt 2: Konfigurieren der mehrstufigen Authentifizierung für ihre dedizierten globalen Administratorkonten von Microsoft 365

Mehrstufige Authentifizierung (MFA) erfordert zusätzliche Informationen über den Kontonamen und das Kennwort hinaus. Microsoft 365 unterstützt diese zusätzlichen Überprüfungsmethoden:
  
- Der Microsoft Authenticator-App

- Ein Telefonanruf
    
- Ein zufällig generierter Überprüfungscode, der über eine Textnachricht gesendet wird
    
- Eine Smartcard (virtuell oder physisch)
    
- Ein biometrisches Gerät
    
>[!Note]
>Für Organisationen, die die Standards des National Institute of Standards and Technology (NIST) einhalten müssen, ist die Verwendung eines Telefonanrufs oder von Textnachrichten basierten zusätzlichen Überprüfungsmethoden eingeschränkt. Klicken Sie [hier](https://pages.nist.gov/800-63-FAQ/#q-b01) , um Details anzuzeigen.
>

Wenn Sie ein kleines Unternehmen sind, das Benutzerkonten verwendet, die nur in der Cloud (dem reinen Cloud-Identitätsmodell) gespeichert sind, [richten Sie MFA](https://docs.microsoft.com/office365/admin/security-and-compliance/set-up-multi-factor-authentication) zum Konfigurieren von MFA mithilfe eines Telefonanrufs oder eines Textnachrichten Überprüfungscodes ein, der für jedes dedizierte globale Administratorkonto an ein Smartphone gesendet wird.
    
Wenn Sie eine größere Organisation sind, die ein Microsoft 365-Hybrid Identitätsmodell verwendet, haben Sie weitere Überprüfungsoptionen. Wenn die Sicherheitsinfrastruktur bereits für eine stärkere sekundäre Authentifizierungsmethode eingerichtet ist, [richten Sie MFA](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/set-up-multi-factor-authentication) ein, und konfigurieren Sie jedes dedizierte globale Administratorkonto für die entsprechende Überprüfungsmethode.
  
Wenn die Sicherheitsinfrastruktur für die gewünschte stärkere Überprüfungsmethode für Microsoft 365 MFA nicht vorhanden und funktionsfähig ist, wird dringend empfohlen, dass Sie dedizierte globale Administratorkonten mit MFA mithilfe der Microsoft Authenticator-APP, eines Telefonanrufs oder eines Textnachrichten Überprüfungscodes konfigurieren, der an ein Smartphone für Ihre globalen Administratorkonten als Interims Sicherheitsmaßnahme gesendet wird. Lassen Sie Ihre dedizierten globalen Administratorkonten nicht ohne den zusätzlichen Schutz, der von MFA bereitgestellt wird.
  
Weitere Informationen finden Sie unter [MFA für Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/multi-factor-authentication-microsoft-365).
  
Informationen zum Herstellen einer Verbindung mit Microsoft 365-Diensten mit MFA und PowerShell finden Sie in den folgenden Artikeln:

- [PowerShell für Microsoft 365 für Benutzerkonten, Gruppen und Lizenzen](connect-to-microsoft-365-powershell.md)
- [Microsoft Teams](https://docs.microsoft.com/microsoftteams/teams-powershell-install)
- [Exchange Online](https://docs.microsoft.com/powershell/exchange/mfa-connect-to-exchange-online-powershell#connect-to-exchange-online-powershell-using-mfa)
- [SharePoint Online](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online#to-connect-with-multifactor-authentication-mfa)
- [Skype for Business Online](manage-skype-for-business-online-with-microsoft-365-powershell.md#connect-using-an-admin-account-with-multi-factor-authentication)

## <a name="additional-protections-for-enterprise-organizations"></a>Zusätzliche Schutzmaßnahmen für Unternehmensorganisationen

Verwenden Sie diese zusätzlichen Methoden, um sicherzustellen, dass ihr globales Administratorkonto und die Konfiguration, die Sie verwenden, so sicher wie möglich sind.
  
### <a name="privileged-access-workstation"></a>Workstation mit privilegiertem Zugriff

Um sicherzustellen, dass die Ausführung von äußerst privilegierten Aufgaben so sicher wie möglich ist, verwenden Sie eine privilegierte Zugriffs Arbeitsstation (PAW). Bei einer PAW handelt es sich um einen dedizierten Computer, der nur für vertrauliche Konfigurationsaufgaben verwendet wird, beispielsweise für die Konfiguration von Microsoft 365, für die ein globales Administratorkonto erforderlich ist. Da dieser Computer nicht täglich für das Internet-browsen oder e-Mail verwendet wird, ist er besser vor Internetangriffen und-Bedrohungen geschützt.
  
Anweisungen zum Einrichten einer Pfote finden Sie unter [https://aka.ms/cyberpaw](https://aka.ms/cyberpaw) .

Weitere Informationen zum Aktivieren von Azure PIM für Ihren Azure AD-Mandanten und für Administratorkonten finden Sie unter [Schritte zum Konfigurieren von PIM](https://docs.microsoft.com/azure/active-directory/active-directory-privileged-identity-management-configure).

Weitere Informationen zum Entwickeln einer Roadmap, um den privilegierten Zugriff vor Cyberangriffen schützt, finden Sie unter [Schützen des privilegierten Zugriffs für hybride Cloudbereitstellungen in Azure AD](https://docs.microsoft.com/azure/active-directory/admin-roles-best-practices).

### <a name="azure-ad-privileged-identity-management"></a>Azure AD Privileged Identity Management

Anstatt ihren globalen Administratorkonten dauerhaft die globale Administratorrolle zuweisen zu müssen, können Sie Azure AD privilegierte Identitätsverwaltung (PIM) verwenden, um bei Bedarf eine Just-in-Time-Zuweisung der globalen Administratorrolle zu aktivieren.
  
Ihre globalen Administratorkonten gehen von permanenten Administratoren zu berechtigten Administratoren. Die globale Administratorrolle ist inaktiv, bis Sie von jemand benötigt wird. Anschließend führen Sie einen Aktivierungsprozess aus, um dem globalen Administratorkonto die globale Administratorrolle für eine vorgegebene Zeitspanne hinzuzufügen. Wenn die Zeit abgelaufen ist, entfernt PIM die globale Administratorrolle aus dem globalen Administratorkonto.
  
Durch die Verwendung von PIM und diesen Prozess wird die Zeit erheblich verkürzt, die ihre globalen Administratorkonten anfällig für Angriffe und die Verwendung durch böswillige Benutzer sind.

PIM ist im Lieferumfang von Azure Active Directory Premium P2 verfügbar, das im Lieferumfang von Microsoft 365 E5 enthalten ist. Alternativ hierzu können Sie einzelne Azure Active Directory Premium P2-Lizenzen für Ihre Administratorkonten erwerben.
  
Weitere Informationen finden Sie unter [Azure AD privilegierte Identitätsverwaltung](https://docs.microsoft.com/azure/active-directory/active-directory-privileged-identity-management-configure).
  

### <a name="privileged-access-management"></a>Privileged Access Management

Privileged Access Management wird durch Konfigurieren von Richtlinien aktiviert, die Just-in-Time-Zugriff für aufgabenbasierte Aktivitäten in Ihrem Mandanten angeben. Dadurch kann Ihre Organisation vor Sicherheitsverletzungen geschützt werden, bei denen vorhandene Privileged Access Management-Konten mit ständigem Zugriff auf vertrauliche Daten oder Zugriff auf kritische Konfigurationseinstellungen verwenden. Sie könnten beispielsweise eine Privileged Access Management-Richtlinie konfigurieren, die für den Zugriff und das Ändern von Postfacheinstellungen in der Organisation eine explizite Genehmigung in Ihrem Mandanten benötigt.

In diesem Schritt aktivieren Sie Privileged Access Management in Ihrem Mandanten und konfigurieren Richtlinien für privilegierten Zugriff, die zusätzliche Sicherheit für aufgabenbasierten Zugriff auf Daten und Konfigurationseinstellungen für Ihre Organisation bereitstellen. Es gibt drei grundlegende Schritte, um mit dem privilegierten Zugriff in Ihrer Organisation zu beginnen:

- Erstellen einer Gruppe einer genehmigenden Person
- Aktivieren des privilegierten Zugriffs
- Erstellen von Genehmigungsrichtlinien

Durch die Verwaltung privilegierter Zugriffsrechte kann Ihre Organisation mit NULL stehenden rechten arbeiten und eine Verteidigungsstufe gegen Sicherheitsanfälligkeiten schaffen, die aufgrund eines solchen ständigen administrativen Zugriffs entstehen. Für privilegierten Zugriff sind Genehmigungen für die Ausführung von Aufgaben erforderlich, für die eine zugeordnete Genehmigungsrichtlinie definiert ist. Benutzer, die Aufgaben ausführen müssen, die in der Genehmigungsrichtlinie enthalten sind, müssen die Genehmigung für den Zugriff anfordern und erteilt werden.

Informationen zum Aktivieren der Verwaltung privilegierten Zugriffs finden Sie unter [configure privileged Access Management](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-configuration).

Weitere Informationen finden Sie unter [privileged Access Management](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-overview).

### <a name="security-information-and-event-management-siem-software-for-microsoft-365-logging"></a>Security Information and Event Management (SIEM)-Software für Microsoft 365-Protokollierung

Siem-Software, die auf einem Server ausgeführt wird, führt Echtzeitanalysen von Sicherheitswarnungen und Ereignissen durch, die von Anwendungen und Netzwerkhardware erstellt wurden. Damit Ihr Siem-Server Microsoft 365-Sicherheitswarnungen und-Ereignisse in seine Analyse-und Berichtsfunktionen einbeziehen kann, integrieren Sie Azure AD in Sie Seim. Weitere Informationen finden Sie unter [Introduction to Azure Log Integration](https://docs.microsoft.com/azure/security/security-azure-log-integration-overview).

## <a name="next-step"></a>Nächster Schritt

Informationen zum Einrichten der Identität für Ihr Microsoft 365-Abonnement finden Sie unter:

- [Nur Cloud-Identitäten](cloud-only-identities.md) , wenn Sie nur die Cloud verwenden
- [Vorbereiten der Verzeichnissynchronisierung](prepare-for-directory-synchronization.md) bei Verwendung der Hybrid Identität

  
## <a name="see-also"></a>Weitere Informationen:

[Microsoft 365-Sicherheits Wegweiser](https://docs.microsoft.com/office365/securitycompliance/security-roadmap)
