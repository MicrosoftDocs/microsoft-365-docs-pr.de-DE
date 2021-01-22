---
title: 'SCHRITT 3: Identität für Ihre Microsoft 365 Enterprise-Mandanten'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
- m365solution-tenantmanagement
ms.custom:
- Ent_Solutions
description: Stellen Sie das richtige Identitätsmodell für Ihre Microsoft 365-Mandanten zur Bereitstellung und erzwingen Sie starke Benutzer-Anmeldungen.
ms.openlocfilehash: 40ea67d9b30a385e36af45f57bd33906c10e495d
ms.sourcegitcommit: 99a7354e6a6b4d9d5202674ef57852d52a43fef6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/20/2021
ms.locfileid: "49908559"
---
# <a name="step-3-identity-for-your-microsoft-365-for-enterprise-tenants"></a>Schritt 3. Identität für Ihre Microsoft 365 Enterprise-Mandanten

Ihr Microsoft 365-Mandant enthält einen Azure Active Directory (Azure AD)-Mandanten zum Verwalten von Identitäten und der Authentifizierung für Anmeldungen. Die korrekte Konfiguration Ihrer Identitätsinfrastruktur ist für die Verwaltung des Microsoft 365-Benutzerzugriffs und der Berechtigungen für Ihre Organisation unerlässlich.

## <a name="cloud-only-vs-hybrid"></a>Nur Cloud im Vergleich zu Hybrid

Hier sind die beiden Arten von Identitätsmodellen und ihre beste Passform und ihre Vorteile.


| Modell | Beschreibung | Authentifizierung von Benutzeranmeldeinformationen durch Microsoft 365 | Ideal für | Größter Vorteil |
|:-------|:-----|:-----|:-----|:-----|
| Rein cloudbasiert | Das Benutzerkonto ist nur im Azure AD-Mandanten für Ihren Microsoft 365-Mandanten vorhanden. | Der Azure AD-Mandant für Ihren Microsoft 365-Mandanten führt die Authentifizierung mit dem Cloudidentitätskonto aus. | Organisationen, die keinen lokalen AD DS besitzen oder benötigen. | Einfach zu verwenden. Es sind keine zusätzlichen Verzeichnistools oder Server erforderlich. |
| Hybrid |  Das Benutzerkonto ist in Ihren lokalen Active Directory Domain Services (AD DS) vorhanden, und eine Kopie befindet sich auch im Azure AD-Mandanten für Ihren Microsoft 365-Mandanten. Azure AD Connect wird auf einem lokalen Server ausgeführt, um AD DS-Änderungen mit Ihrem Azure AD-Mandanten zu synchronisieren. Das Benutzerkonto in Azure AD enthält möglicherweise auch eine Hashversion des kennworts für das ad #A0 mit Hash. | Der Azure AD-Mandant für Ihren Microsoft 365-Mandanten übernimmt entweder den Authentifizierungsprozess oder leitet den Benutzer an einen anderen Identitätsanbieter um. | Organisationen, die AD DS oder einen anderen Identitätsanbieter verwenden. | Benutzer können dieselben Anmeldeinformationen verwenden, wenn sie auf lokale oder cloudbasierte Ressourcen zugreifen. |
||||||

Hier sind die grundlegenden Komponenten der reinen Cloudidentität.
 
![Grundlegende Komponenten der Nur-Cloud-Identität](../media/about-microsoft-365-identity/cloud-only-identity.png)

In dieser Abbildung melden sich lokale und Remotebenutzer mit Konten im Azure AD-Mandanten ihres Microsoft 365-Mandanten an.

Hier sind die grundlegenden Komponenten der Hybrididentität.

![Grundlegende Komponenten der Hybrididentität](../media/about-microsoft-365-identity/hybrid-identity.png)

In dieser Abbildung melden sich lokale und Remotebenutzer bei ihrem Microsoft 365-Mandanten mit Konten im Azure AD-Mandanten an, die aus ihrem lokalen AD DS kopiert wurden.

## <a name="synchronizing-your-on-premises-ad-ds"></a>Synchronisieren Ihrer lokalen AD DS

Je nach Ihren Geschäftsanforderungen und technischen Anforderungen ist das hybride Identitätsmodell und die Verzeichnissynchronisierung die häufigste Wahl für Unternehmenskunden, die Microsoft 365 übernehmen. Mit der Verzeichnissynchronisierung können Sie Identitäten in Ad DS verwalten, und alle Updates für Benutzerkonten, Gruppen und Kontakte werden mit dem Azure AD-Mandanten Ihres Microsoft 365-Mandanten synchronisiert.

>[!Note]
>Wenn AD DS-Benutzerkonten zum ersten Mal synchronisiert werden, wird ihnen nicht automatisch eine Microsoft 365-Lizenz zugewiesen, und sie können nicht auf Microsoft 365-Dienste wie E-Mails zugreifen. Sie müssen ihnen zuerst einen Verwendungsspeicherort zuweisen. Weisen Sie diesen Benutzerkonten dann entweder einzeln oder dynamisch über die Gruppenmitgliedschaft eine Lizenz zu.
>

Im Folgenden werden die beiden Authentifizierungstypen bei Verwendung des hybriden Identitätsmodells gezeigt.

| Authentifizierungstyp | Beschreibung |
|:-------|:-----|
| Verwaltete Authentifizierung | Azure AD verarbeitet den Authentifizierungsprozess mithilfe einer lokal gespeicherten Hashversion des Kennworts oder sendet die Anmeldeinformationen an einen lokalen Software-Agent, um vom lokalen AD DS authentifiziert zu werden. <br> <br>  Es gibt zwei Arten von verwalteter Authentifizierung: Kennworthashsynchronisierung (Password Hash Synchronization, PHS) und Pass-Through-Authentifizierung (PTA). Mit PHS führt Azure AD die Authentifizierung selbst aus. Mit PTA führt Azure AD die Authentifizierung durch AD DS aus. |
| Verbundauthentifizierung | Azure AD leitet den Clientcomputer, der die Authentifizierung anfordert, an einen anderen Identitätsanbieter um. |
|  |  |

Weitere [Informationen finden Sie unter](https://docs.microsoft.com/azure/active-directory/hybrid/choose-ad-authn) Auswahl der richtigen Authentifizierungsmethode.

## <a name="enforcing-strong-sign-ins"></a>Erzwingen starker Anmeldungen

Um die Sicherheit von Benutzer anmeldungen zu erhöhen, verwenden Sie die Features und Funktionen in der folgenden Tabelle.

| Funktion | Beschreibung | Weitere Informationen | Lizenzierungsanforderungen |
|:-------|:-----|:-----|:-----|:-----|
| Windows Hello for Business | Ersetzt Kennwörter durch eine sichere zweistufige Authentifizierung beim Signieren auf einem Windows-Gerät. Beide Faktoren zählen zu neuen Arten von Benutzeranmeldeinformationen, die mit einem Gerät verknüpft sind und biometrische Daten oder eine PIN erfordern. | [Windows Hello for Business – Übersicht](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-overview) | Microsoft 365 E3 oder E5 |
| Azure AD-Kennwortschutz | Erkennt und blockiert bekannte schwache Kennwörter und deren Varianten und kann auch zusätzliche schwache Begriffe blockieren, die für Ihre Organisation spezifisch sind. | [Konfigurieren des Azure AD-Kennwortschutzes](https://docs.microsoft.com/azure/active-directory/authentication/concept-password-ban-bad) | Microsoft 365 E3 oder E5 |
| Verwenden der mehrstufigen Authentifizierung (Multi-Factor Authentication, MFA) | MFA setzt voraus, dass bei Benutzera0-Anmeldungen eine zusätzliche Überprüfung über das Benutzerkontokennwort hinaus erforderlich ist, z. B. eine Überprüfung mit einer Smartphone-App oder eine an ein Smartphone gesendete Textnachricht. In [diesem Video finden](https://support.microsoft.com/office/set-up-multi-factor-authentication-in-microsoft-365-business-a32541df-079c-420d-9395-9d59354f7225) Sie Anweisungen dazu, wie Benutzer MFA einrichten. | [MFA für Microsoft 365 Enterprise](../enterprise/microsoft-365-secure-sign-in.md#mfa) | Microsoft 365 E3 oder E5 |
| Konfigurationen für den Identitäts- und Gerätezugriff | Einstellungen und Richtlinien, die aus empfohlenen erforderlichen Features und deren Einstellungen in Kombination mit Richtlinien für bedingten Zugriff, Intune und Azure AD Identity Protection bestehen, die bestimmen, ob eine bestimmte Zugriffsanforderung gewährt werden soll und unter welchen Bedingungen.  | [Konfigurationen für den Identitäts- und Gerätezugriff](../security/office-365-security/microsoft-365-policies-configurations.md) | Microsoft 365 E3 oder E5 |
| Azure AD Identity Protection | Schutz vor Der Angriff auf Anmeldeinformationen, bei dem ein Angreifer den Kontonamen und das Kennwort eines Benutzers bestimmt, um Zugriff auf die Clouddienste und -daten einer Organisation zu erhalten. | [Azure AD Identity Protection](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection) | Microsoft 365 E5 oder Microsoft 365 E3 mit dem Identity & Threat Protection-Add-On |
|  |  |  |



## <a name="results-of-step-3"></a>Ergebnisse von Schritt 3

Für die Identität Ihres Microsoft 365-Mandanten haben Sie ermittelt:

- Welches Identitätsmodell verwendet werden soll.
- Wie Sie starken Benutzer- und Gerätezugriff erzwingen.

Hier ist ein Beispiel für einen Mandanten mit hervorgehobenen neuen Hybrididentitätselementen.

![Beispiel für eine Hybrididentität für einen Mandanten](../media/tenant-management-overview/tenant-management-tenant-build-step3.png)

In dieser Abbildung hat der Mandant:

- Eine AD DS-Gesamtstruktur, die mit dem Azure AD-Mandanten mithilfe eines DirSync-Servers und Azure AD Connect synchronisiert wird.
- Eine Kopie der AD DS-Benutzerkonten und anderer Objekte aus der AD DS-Gesamtstruktur.
- Eine Reihe von Richtlinien für den bedingten Zugriff, um sichere Benutzer bei Anmeldungen und Zugriff basierend auf dem Benutzerkonto zu erzwingen. 

## <a name="ongoing-maintenance-for-identity"></a>Fortlaufende Wartung der Identität

Es kann sein, dass Sie regelmäßig:

- Hinzufügen oder Ändern von Benutzerkonten und Gruppen. Für eine cloudbasierte Identität verwalten Sie Ihre cloudbasierten Benutzer und Gruppen mit Azure AD-Tools wie dem Microsoft 365 Admin Center oder PowerShell. Für hybride Identitäten verwalten Sie Ihre lokalen Benutzer und Gruppen mit AD DS-Tools.
- Fügen Sie Ihre Identitäts- und Gerätezugriffskonfiguration hinzu, oder ändern Sie sie, um Anmeldesicherheitsanforderungen zu erzwingen.

## <a name="next-step"></a>Nächster Schritt

[![Schritt 4. Migrieren Ihrer lokalen Office-Server und -Daten](../media/tenant-management-overview/tenant-management-step-grid-migration.png)](tenant-management-migration.md)

Fahren Sie mit [der Migration](tenant-management-migration.md) fort, um Ihre lokalen Office Server und deren Daten zu Microsoft 365 zu migrieren.