---
title: Identität für die Contoso Corporation
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
ms.date: 09/13/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: Wie Contoso IDaaS (Identity as a Service) nutzt und eine cloudbasierte Authentifizierung für seine Mitarbeiter und eine Verbundauthentifizierung für Partner und Kunden bereitstellt.
ms.openlocfilehash: 7571aa455cac4da9e56d7d2001ae4421c3769c94
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/28/2018
ms.locfileid: "26868028"
---
# <a name="identity-for-the-contoso-corporation"></a>Identität für die Contoso Corporation

**Zusammenfassung:** Wie Contoso IDaaS (Identity as a Service) nutzt und eine cloudbasierte Authentifizierung für seine Mitarbeiter und eine Verbundauthentifizierung für Partner und Kunden bereitstellt.

Microsoft bietet mit Azure Active Directory (AD) eine IDaaS (Identity as a Service, Identität als Dienst) in seinen Cloudangeboten. Um Microsoft 365 Enterprise einzuführen, muss für die IDaaS-Lösung von Contoso dessen lokaler Identitätsanbieter genutzt und Verbundauthentifizierung mit den vorhandenen vertrauenswürdigen Drittanbieter-Identitätsanbietern einbezogen werden.

## <a name="contosos-windows-server-ad-forest"></a>Contosos Windows Server Active Directory-Gesamtstruktur

Contoso verwendet eine einzige Windows Server Active Directory-Gesamtstruktur für „contoso.com“ mit sieben Unterdomänen (eine für jede Region der Erde). Die Zentrale, Regionalstellen und Zweigstellen enthalten Domänencontroller für die lokale Authentifizierung und Autorisierung.

Abbildung 1 zeigt die Contoso-Gesamtstruktur mit regionalen Domänen für die unterschiedlichen Regionen, die Regionalstellen enthalten.

![](./media/contoso-identity/contoso-identity-fig1.png)
 
**Abbildung 1: Gesamtstruktur und Domänen von Contoso weltweit**

Contoso möchte die Konten und Gruppen in der „contoso.com“-Gesamtstruktur zur Authentifizierung und Autorisierung seiner cloudbasierten Apps und Arbeitslasten verwenden.

## <a name="contosos-federated-authentication-infrastructure"></a>Contosos Infrastruktur der Verbundauthentifizierung

Contoso lässt Folgendes zu:

- Kunden können ihre Microsoft-, Facebook- oder Google Mail-Konten verwenden, um sich bei ihren öffentlichen Websites anzumelden.
- Lieferanten und Partner können ihre LinkedIn-, Salesforce- oder Google Mail-Konten verwenden, um sich beim Partnerextranet anzumelden.

Abbildung 2 zeigt die Contoso-DMZ mit einer öffentlichen Website, einem Partnerextranet und einer Reihe von Active Directory Federation Services-Servern (AD FS). Die DMZ ist mit dem Internet verbunden, das Kunden, Partner und Internetdienste enthält.

![](./media/contoso-identity/contoso-identity-fig2.png)

**Abbildung 2: Contosos Unterstützung für die Verbundauthentifizierung für Kunden und Partner**
 
AD FS-Server in der DMZ authentifizieren Kundenanmeldeinformationen für Zugriff auf die öffentliche Website und Partneranmeldeinformationen für Zugriff auf das Partnerextranet.

Contoso hat sich entschlossen, seine Infrastruktur beizubehalten und diese für die Kunden- und Partnerauthentifizierung zu verwenden. Die Identitätsingenieure bei Contoso befassen sich mit der Konvertierung dieser Infrastruktur in die Azure AD-Lösungen [B2B](https://docs.microsoft.com/azure/active-directory/b2b/hybrid-organizations) und [B2C](https://docs.microsoft.com/azure/active-directory-b2c/solution-articles).

## <a name="hybrid-identity-with-pass-through-authentication-for-cloud-based-authentication"></a>Hybrididentität mit Durchsatzauthentifizierung für cloudbasierte Authentifizierung

Contoso wollte seine lokale Windows Server Active Directory-Gesamtstruktur für die Authentifizierung bei Microsoft 365 nutzen. Deshalb wurde eine Durchsatzauthentifizierung mit Kennworthashsynchronisierung eingeführt.

### <a name="pta-authentication"></a>Durchsatzauthentifizierung

Für die Authentifizierung von Benutzeranmeldeinformationen verwendet Contoso die Durchsatzauthentifizierung. Wenn ein Contoso-Benutzer auf cloudbasierte Ressourcen zugreift, werden die gesendeten Anmeldeinformationen von Azure AD an einen Server im Rechenzentrum der Contoso-Zentrale übergeben, auf dem ein Authentifizierungs-Agent ausgeführt wird. Die Benutzeranmeldeinformationen werden im Auftrag von Azure AD von einem dieser Authentifizierungsserver überprüft.

In Abbildung 3 ist eine Reihe von Servern in der Contoso-Zentrale dargestellt, auf denen der Authentifizierungs-Agent ausgeführt wird und die Authentifizierungsanforderungen verarbeiten, die ihnen von Azure AD übergeben wurden. 

![](./media/contoso-identity/contoso-identity-fig3.png)
 
**Abbildung 3: Infrastruktur der Durchsatzauthentifizierung bei Contoso**

Contoso hat sich für die Durchsatzauthentifizierung entschieden, um alle Sicherheitsanforderungen zu erfüllen. Dabei werden alle Authentifizierungsversuche auf unmittelbare Änderungen an Benutzerkontostatus, Kennwortrichtlinien und Anmeldestunden überprüft, die an der lokalen Windows Server AD-Gesamtstruktur erfolgen.

### <a name="phs"></a>Kennworthashsynchronisierung (PHS)

Bei der Kennworthashsynchronisierung wird die lokale Windows Server AD-Gesamtstruktur mit dem Azure AD-Mandanten ihres Microsoft 365 Enterprise-Abonnements synchronisiert, wobei Benutzer- und Gruppenkonten sowie eine Hashversion von Benutzerkontokennwörtern kopiert werden. Contoso hat sich für die Kennwortsynchronisierung entschieden, um eine alternative Authentifizierungsmethode direkt mit dem Azure AD-Mandanten bereitzustellen, falls die Durchsatzauthentifizierung nicht verfügbar ist.

Um die laufende Verzeichnissynchronisierung durchzuführen, hat Contoso das Azure AD Connect-Tool auf einem Server im Rechenzentrum in Paris bereitgestellt. Abbildung 4 zeigt die Server mit Azure AD Connect, die die Windows Server Active Directory-Gesamtstruktur von Contoso auf Änderungen abfragt und diese Änderungen dann mit dem Azure AD-Mandanten synchronisiert.

![](./media/contoso-identity/contoso-identity-fig4.png)
 
**Abbildung 4: Infrastruktur für die PHS-Verzeichnissynchronisierung von Contoso**

## <a name="conditional-access-policies-for-identity"></a>Richtlinien für bedingten Zugriff für Identität

Contoso hat eine Reihe von [Richtlinien für bedingten Zugriff](identity-access-policies.md) in Azure AD erstellt, um sicherzustellen, dass eine mehrstufige Authentifizierung und Kennwortänderungen erzwungen werden, wenn Azure AD feststellt, dass ein Anmelderisiko für eine Authentifizierungsanfrage besteht.

Abbildung 5 zeigt die resultierenden Richtlinien für bedingten Zugriff für Identität.

![](./media/contoso-identity/contoso-identity-fig5.png)
 
**Abbildung 5: Identitätsbasierte Richtlinien für bedingen Zugriff**

## <a name="next-step"></a>Nächster Schritt

[Erfahren Sie](contoso-win10.md), wie Contoso seine System Center Configuration Manager-Infrastruktur verwendet, um Windows 10 Enterprise über die Organisation hinweg bereitzustellen und auf dem neuesten Stand zu halten.

## <a name="see-also"></a>Siehe auch

[Microsoft 365 Enterprise](identity-infrastructure.md)

[Bereitstellungshandbuch](deploy-microsoft-365-enterprise.md)

[Testumgebungsanleitungen](m365-enterprise-test-lab-guides.md)
