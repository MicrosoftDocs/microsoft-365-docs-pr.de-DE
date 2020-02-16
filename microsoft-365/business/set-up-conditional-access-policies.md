---
title: Einrichten von Richtlinien für bedingten Zugriff für Microsoft 365-Kampagnen
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- Adm_O365
- MiniMaven
- MSB365
- OKR_SMB_M365
search.appverid:
- BCS160
- MET150
- MOE150
description: Hier erfahren Sie, wie Sie Richtlinien für bedingten Zugriff für Microsoft 365-Kampagnen einrichten.
ms.openlocfilehash: 1ef90bd77da43ded624d85cef9c7a33beec74345
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42064606"
---
# <a name="set-up-conditional-access-policies"></a>Einrichten von Richtlinien für bedingten Zugriff

[Bedingte Zugriffs](https://docs.microsoft.com/azure/active-directory/conditional-access/overview) Richtlinien fügen erhebliche zusätzliche Sicherheit hinzu. Microsoft stellt eine Reihe von Baseline-bedingten Zugriffsrichtlinien bereit, die für alle Kunden empfohlen werden. Baseline-Richtlinien sind eine Reihe von vordefinierten Richtlinien, die Organisationen vor zahlreichen häufigen Angriffen schützen sollen. Diese häufigen Angriffe können Kenn Wort Spray, Wiedergabe und Phishing umfassen.

Für diese Richtlinien müssen Administratoren und Benutzer eine zweite Authentifizierungsform (die als mehrstufige Authentifizierung bezeichnet wird, oder MFA) eingeben, wenn bestimmte Bedingungen erfüllt sind. Wenn sich ein Benutzer beispielsweise von einem anderen Land aus anmeldet, wird die Anmeldung möglicherweise als riskant betrachtet, und der Benutzer muss eine zusätzliche Authentifizierungsform bereitstellen. 

Derzeit umfassen Baseline-Richtlinien Folgendes:
- Für **Administratoren** &ndash; erfordert die mehrstufige Authentifizierung für die privilegierten Administratorrollen, einschließlich des globalen Administrators.
- Der **Endbenutzer Schutz** &ndash; erfordert mehrstufige Authentifizierung für Benutzer nur, wenn eine Anmeldung riskant ist. 
- **Legacy Authentifizierung** &ndash; blockieren ältere Client-apps und einige neue Apps verwenden keine neueren, sichereren Authentifizierungsprotokolle. Diese älteren Apps können Richtlinien für bedingten Zugriff umgehen und nicht autorisierten Zugriff auf Ihre Umgebung erlangen. Diese Richtlinie blockiert den Zugriff von Clients, die keinen bedingten Zugriff unterstützen. 
- Für die **Verwaltung von MFA for Service Management** &ndash; ist eine mehrstufige Authentifizierung für den Zugriff auf Verwaltungstools erforderlich, einschließlich des Azure-Portals (in dem Sie Basisrichtlinien konfigurieren). 

Microsoft empfiehlt, alle diese Basisrichtlinien zu aktivieren. Nachdem diese Richtlinien aktiviert wurden, werden Administratoren und Benutzer aufgefordert, sich für die Azure multii-Factor Authentication zu registrieren.

Weitere Informationen zu diesen Richtlinien finden Sie unter [Was sind Basisrichtlinien](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-baseline-protection)?


## <a name="set-up-baseline-policies"></a>Einrichten von Baseline-Richtlinien

1. Wechseln Sie [zu Azure-Portal](https://portal.azure.com), und navigieren Sie dann zu **Azure Active Directory** \> **bedingten Zugriff**.
    
    Die Basisrichtlinien werden auf der Seite aufgelistet. <br/> <br/>
    ![Seite, auf der Basisrichtlinien für bedingten Zugriff aufgelistet werden.](../media/baslinepolicies.png)
1. Lesen Sie die folgenden spezifischen Anweisungen für jede Richtlinie:

  - [MFA für Administratoren erforderlich](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-baseline-protect-administrators)
- [MFA für Benutzer erforderlich](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-baseline-protect-end-users)  
 - [Legacy Authentifizierung blockieren](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-baseline-protect-legacy-auth)
  - [MFA für Service Management erforderlich](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-baseline-protect-azure)

Sie können viele zusätzliche Richtlinien einrichten, beispielsweise das Anfordern von genehmigten Client-apps. Weitere Informationen finden Sie in der [Dokumentation zum bedingten Zugriff](https://docs.microsoft.com/azure/active-directory/conditional-access/).
