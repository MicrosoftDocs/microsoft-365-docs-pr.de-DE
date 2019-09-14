---
title: Identität für die Contoso Corporation
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
ms.date: 09/06/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom: ''
description: Wie Contoso IDaaS (Identity as a Service) nutzt und eine cloudbasierte Authentifizierung für seine Mitarbeiter und eine Verbundauthentifizierung für Partner und Kunden bereitstellt.
ms.openlocfilehash: f40be4ad7d93781ff2ac980228ae5271a8e844c4
ms.sourcegitcommit: 91ff1d4339f0f043c2b43997d87d84677c79e279
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/14/2019
ms.locfileid: "36982126"
---
# <a name="identity-for-the-contoso-corporation"></a>Identität für die Contoso Corporation

**Zusammenfassung:** Wie Contoso IDaaS (Identity as a Service) nutzt und eine cloudbasierte Authentifizierung für seine Mitarbeiter und eine Verbundauthentifizierung für Partner und Kunden bereitstellt.

Microsoft bietet eine IDaaS (Identity as a Service, Identität als Dienst) in seinen Cloudangeboten mit Azure Active Directory (Azure AD). Um Microsoft 365 Enterprise einzuführen, musste für die IDaaS-Lösung von Contoso dessen lokaler Identitätsanbieter genutzt und weiterhin Verbundauthentifizierung mit den vorhandenen vertrauenswürdigen Drittanbieter-Identitätsanbietern einbezogen werden.

## <a name="contosos-active-directory-domain-services-forest"></a>Active Directory Domain Services-Gesamtstruktur von Contoso

Contoso verwendet eine einzelne Active Directory Domain Services(AD DS)-Gesamtstruktur für „contoso.com“ mit sieben Unterdomänen, eine für jede Region der Welt. Die Zentrale, die Regionalstellen und die Zweigstellen enthalten Domänencontroller für die lokale Authentifizierung und Autorisierung.

Abbildung 1 zeigt die Contoso-Gesamtstruktur mit regionalen Domänen für die unterschiedlichen Regionen, die Regionalstellen enthalten.

![](./media/contoso-identity/contoso-identity-fig1.png)
 
**Abbildung 1: Gesamtstruktur und Domänen von Contoso weltweit**

Contoso wollte die Konten und Gruppen in der „contoso.com“-Gesamtstruktur zur Authentifizierung und Autorisierung seiner Microsoft 365-Arbeitslasten und -Dienste verwenden.

## <a name="contosos-federated-authentication-infrastructure"></a>Contosos Infrastruktur der Verbundauthentifizierung

Contoso lässt Folgendes zu:

- Kunden können ihre Microsoft-, Facebook- oder Google Mail-Konten verwenden, um sich bei ihren öffentlichen Websites anzumelden.
- Lieferanten und Partner können ihre LinkedIn-, Salesforce- oder Google Mail-Konten verwenden, um sich beim Partnerextranet anzumelden.

Abbildung 2 zeigt die Contoso-DMZ mit einer öffentlichen Website, einem Partnerextranet und einer Reihe von Active Directory Federation Services-Servern (AD FS). Die DMZ ist mit dem Internet verbunden, das Kunden, Partner und Internetdienste enthält.

![](./media/contoso-identity/contoso-identity-fig2.png)

**Abbildung 2: Contosos Unterstützung für die Verbundauthentifizierung für Kunden und Partner**
 
AD FS-Server in der DMZ erleichtern das Authentifizieren von Kundenanmeldeinformationen durch den Identitätsanbieter für Zugriff auf die öffentliche Website und Partneranmeldeinformationen für Zugriff auf das Partnerextranet.

Contoso hat sich entschlossen, seine Infrastruktur beizubehalten und diese für die Kunden- und Partnerauthentifizierung zu verwenden. Die Identitätsarchitekten bei Contoso befassen sich mit der Konvertierung dieser Infrastruktur in die Azure AD-Lösungen [B2B](https://docs.microsoft.com/azure/active-directory/b2b/hybrid-organizations) und [B2C](https://docs.microsoft.com/azure/active-directory-b2c/solution-articles).

## <a name="hybrid-identity-with-password-hash-synchronization-for-cloud-based-authentication"></a>Hybrididentität mit Kennwort-Hash-Synchronisierung für cloudbasierte Authentifizierung

Contoso wollte seine lokale AD DS-Gesamtstruktur für die Authentifizierung bei Microsoft 365-Cloudressourcen nutzen. Es entschied sich für Kennwort-Hash-Synchronisierung.

Bei der Kennwort-Hash-Synchronisierung wird die lokale AD DS-Gesamtstruktur mit dem Azure AD-Mandanten des Microsoft 365 Enterprise-Abonnements synchronisiert, wobei Benutzer- und Gruppenkonten und eine Hash-Version von Benutzerkontokennwörtern kopiert werden. 

Um die laufende Verzeichnissynchronisierung durchzuführen, hat Contoso das Azure AD Connect-Tool auf einem Server im Rechenzentrum in Paris bereitgestellt. Abbildung 3 zeigt den Server mit Azure AD Connect, das die AD DS-Gesamtstruktur von Contoso auf Änderungen abruft und diese Änderungen dann mit dem Azure AD-Mandanten synchronisiert.

![](./media/contoso-identity/contoso-identity-fig4.png)
 
**Abbildung 3: Infrastruktur für die PHS-Verzeichnissynchronisierung von Contoso**


## <a name="conditional-access-policies-for-identity-and-device-access"></a>Richtlinien für bedingten Zugriff für Identitäts- und Gerätezugriff

Contoso hat eine Gruppe von Azure AD- und Intune-[Richtlinien für bedingten Zugriff](identity-access-policies.md) für drei Schutzebenen erstellt:

- **Baseline**-Schutz gilt für alle Benutzerkonten
- **Vertraulicher** Schutz gilt für die Geschäftsleitung und Führungskräfte
- **Hochgradig regulierter** Schutz gilt für bestimmte Benutzer der Finanz-, Rechts- und Forschungsabteilung, die Zugriff auf hochgradig regulierte Daten haben.

Abbildung 4 zeigt die resultierenden identitäts- und gerätebasierten Richtlinien für bedingten Zugriff.

![](./media/contoso-identity/contoso-identity-fig5.png)
 
**Abbildung 4: Identitäts- und gerätebasierte Richtlinien für bedingten Zugriff**

## <a name="next-step"></a>Nächster Schritt

[Erfahren Sie](contoso-win10.md), wie Contoso seine System Center Configuration Manager-Infrastruktur verwendet, um Windows 10 Enterprise über die Organisation hinweg bereitzustellen und auf dem neuesten Stand zu halten.

## <a name="see-also"></a>Siehe auch

[Microsoft 365 Enterprise](identity-infrastructure.md)

[Bereitstellungshandbuch](deploy-microsoft-365-enterprise.md)

[Testumgebungsanleitungen](m365-enterprise-test-lab-guides.md)
