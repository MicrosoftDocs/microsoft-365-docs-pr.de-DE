---
title: Identität für die Contoso Corporation
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
ms.date: 10/01/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom: ''
description: Wie Contoso IDaaS (Identity as a Service) nutzt und eine cloudbasierte Authentifizierung für seine Mitarbeiter und eine Verbundauthentifizierung für Partner und Kunden bereitstellt.
ms.openlocfilehash: 10db0a35024595c4dba9a33ad83ae75bcad3870c
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/21/2020
ms.locfileid: "48637247"
---
# <a name="identity-for-the-contoso-corporation"></a>Identität für die Contoso Corporation

Microsoft stellt Identity as a Service (IDaaS) in seinen Cloud-angeboten über Azure Active Directory (Azure AD) bereit. Um Microsoft 365 für Unternehmen zu verabschieden, musste die Contoso-IDaaS-Lösung Ihren lokalen Identitätsanbieter verwenden und die Verbundauthentifizierung mit Ihren vorhandenen vertrauenswürdigen Drittanbieter-Identitätsanbietern einschließen.

## <a name="the-contoso-active-directory-domain-services-forest"></a>Die Contoso Active Directory-Domänendienste Gesamtstruktur

Contoso verwendet eine einzelne Active Directory-Domänendienste (AD DS) Gesamtstruktur für Contoso \. com mit sieben Unterdomänen, eine für jede Region der Welt. Die Zentrale, die Regionalstellen und die Zweigstellen enthalten Domänencontroller für die lokale Authentifizierung und Autorisierung.

Hier ist die Contoso-Gesamtstruktur mit regionalen Domänen für die verschiedenen Teile der Welt, die regionale Hubs enthalten.

![Gesamtstruktur und Domänen von Contoso weltweit](../media/contoso-identity/contoso-identity-fig1.png)
 
Contoso hat beschlossen, die Konten und Gruppen in der Contoso \. -com-Gesamtstruktur zur Authentifizierung und Autorisierung für seine Microsoft 365-Arbeitslasten und-Dienste zu verwenden.

## <a name="the-contoso-federated-authentication-infrastructure"></a>Die Contoso-Verbund Authentifizierungsinfrastruktur

Contoso lässt Folgendes zu:

- Kunden, Ihre Microsoft-, Facebook-oder Google Mail-Konten zu verwenden, um sich bei der öffentlichen Website des Unternehmens anzumelden.
- Kreditoren und Partner, die ihre LinkedIn-, Salesforce-oder Google Mail-Konten verwenden, um sich beim Partner-Extranet des Unternehmens anzumelden.

Hier ist die Contoso-DMZ mit einer öffentlichen Website, einem Partner-Extranet und einer Reihe von AD FS-Servern. Die DMZ ist mit dem Internet verbunden, das Kunden, Partner und Internetdienste enthält.

![Contoso-Unterstützung für die Verbundauthentifizierung für Kunden und Partner](../media/contoso-identity/contoso-identity-fig2.png)
 
AD FS-Server in der DMZ erleichtern die Authentifizierung von Kunden Anmeldeinformationen durch ihre Identitätsanbieter für den Zugriff auf die öffentliche Website und Partner Anmeldeinformationen für den Zugriff auf das Partner-Extranet.

Contoso hat beschlossen, diese Infrastruktur beizubehalten und für die Authentifizierung von Kunden und Partnern zu reservieren. Die Identitätsarchitekten bei Contoso befassen sich mit der Konvertierung dieser Infrastruktur in die Azure AD-Lösungen [B2B](https://docs.microsoft.com/azure/active-directory/b2b/hybrid-organizations) und [B2C](https://docs.microsoft.com/azure/active-directory-b2c/solution-articles).

## <a name="hybrid-identity-with-password-hash-synchronization-for-cloud-based-authentication"></a>Hybrididentität mit Kennwort-Hash-Synchronisierung für cloudbasierte Authentifizierung

Contoso wollte seine lokale AD DS Gesamtstruktur für die Authentifizierung von Microsoft 365 Cloud-Ressourcen verwenden. Sie hat sich für die Verwendung der Kennworthash Synchronisierung (PHS) entschieden.

PHS synchronisiert die lokale AD DS Gesamtstruktur mit dem Azure AD Mandanten Ihres Microsoft 365 for Enterprise-Abonnements und kopiert Benutzer-und Gruppenkonten sowie eine gehashte Version der Kennwörter für Benutzerkonten.

Um die Verzeichnissynchronisierung durchführen zu können, hat Contoso das Azure AD Connect-Tool auf einem Server in seinem Pariser Datencenter bereitgestellt.

Hier ist der Server, auf dem Azure AD Connect die Contoso AD DS-Gesamtstruktur für Änderungen abruft und diese Änderungen dann mit dem Azure AD Mandanten synchronisiert.

![Die Contoso-Verzeichnis Synchronisierungs Infrastruktur für PHS](../media/contoso-identity/contoso-identity-fig4.png)
 
## <a name="conditional-access-policies-for-identity-and-device-access"></a>Richtlinien für bedingten Zugriff für Identitäts- und Gerätezugriff

Contoso hat eine Gruppe von Azure AD- und Intune-[Richtlinien für bedingten Zugriff](identity-access-policies.md) für drei Schutzebenen erstellt:

- *Basis* Schutz gilt für alle Benutzerkonten.
- *Vertrauliche* Schutzmaßnahmen gelten für Führungskräfte und Führungskräfte.
- *Streng geregelte* Schutzmaßnahmen gelten für bestimmte Benutzer in den Abteilungen Finanzen, Recht und Forschung, die Zugriff auf streng geregelte Daten haben.

Im folgenden finden Sie eine Reihe von Contoso-Identitäts-und Geräte bedingten Zugriffsrichtlinien.

![Identitäts- und gerätebasierte Richtlinien für bedingten Zugriff](../media/contoso-identity/contoso-identity-fig5.png)
 
## <a name="next-step"></a>Nächster Schritt

[Erfahren Sie](contoso-win10.md) , wie Contoso seine Microsoft Endpoint Configuration Manager-Infrastruktur für die Bereitstellung und Verwaltung von Windows 10 Enterprise in seiner Organisation verwendet.

## <a name="see-also"></a>Siehe auch

[Identitäts-Roadmap für Microsoft 365](identity-roadmap-microsoft-365.md)

[Übersicht über Microsoft 365 Enterprise](microsoft-365-overview.md)

[Testumgebungsanleitungen](m365-enterprise-test-lab-guides.md)
