---
title: Einrichten von Richtlinien für bedingten Zugriff für Microsoft 365-Kampagnen
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
ms.custom: OKR_SMB_M365
search.appverid:
- BCS160
- MET150
- MOE150
description: Hier erfahren Sie, wie Sie Richtlinien für bedingten Zugriff für Microsoft 365-Kampagnen einrichten.
ms.openlocfilehash: dbb5231032d2faef0a7ecb2734226b34290c70bf
ms.sourcegitcommit: 6003d6da0a85c97357eb3dba3918eb145f381fe1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/27/2019
ms.locfileid: "37288613"
---
# <a name="set-up-conditional-access-policies"></a>Einrichten von Richtlinien für bedingten Zugriff

[Bedingte Zugriffs](https://docs.microsoft.com/azure/active-directory/conditional-access/overview) Richtlinien fügen substancial zusätzliche Sicherheit hinzu. Microsoft stellt eine Reihe von Baseline-bedingten Zugriffsrichtlinien bereit, die für alle Kunden empfohlen werden. Baseline-Richtlinien sind eine Reihe von vordefinierten Richtlinien, die Organisationen vor zahlreichen häufigen Angriffen schützen sollen. Diese häufigen Angriffe können Kenn Wort Spray, Wiedergabe und Phishing umfassen.

Für diese Richtlinien müssen Administratoren und Benutzer eine zweite Authentifizierungsform (die als mehrstufige Authentifizierung bezeichnet wird, oder MFA) eingeben, wenn bestimmte Bedingungen erfüllt sind. Wenn sich ein Benutzer beispielsweise von einem anderen Land aus anmeldet, wird die Anmeldung möglicherweise als riskant betrachtet, und der Benutzer muss eine zusätzliche Authentifizierungsform bereitstellen. 

Derzeit umfassen Baseline-Richtlinien Folgendes:
- **MFA für Administratoren erforderlich** – erfordert mehrstufige Authentifizierung für die privilegierten Administratorrollen, einschließlich des globalen Administrators.
- **Endbenutzer Schutz** – erfordert mehrstufige Authentifizierung für Benutzer nur, wenn eine Anmeldung riskant ist. 
- **Legacy Authentifizierung blockieren** – ältere Client-apps und einige neue Apps verwenden keine neueren, sichereren Authentifizierungsprotokolle. Diese älteren Apps können Richtlinien für bedingten Zugriff umgehen und nicht autorisierten Zugriff auf Ihre Umgebung erlangen. Diese Richtlinie blockiert den Zugriff von Clients, die keinen bedingten Zugriff unterstützen. 
- **MFA für die Dienstverwaltung erforderlich** – erfordert mehrstufige Authentifizierung für den Zugriff auf Verwaltungstools, einschließlich Azure-Portal (in dem Sie Basisrichtlinien konfigurieren). 

Microsoft empfiehlt, alle diese Basisrichtlinien zu aktivieren. Nachdem diese Richtlinien aktiviert wurden, werden Administratoren und Benutzer aufgefordert, sich für die Azure multii-Factor Authentication zu registrieren.

Weitere Informationen zu diesen Richtlinien finden Sie unter [Was sind Basisrichtlinien](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-baseline-protection)?


## <a name="set-up-baseline-policies"></a>Einrichten von Baseline-Richtlinien

1. Wechseln Sie [zu Azure-Portal](https://portal.azure.com), und navigieren Sie dann zu **Azure Active Directory** \> **bedingten Zugriff**.
    
    Die Basisrichtlinien werden auf der Seite aufgelistet. <br/> <br/>
    ![Seite, auf der Basisrichtlinien für bedingten Zugriff aufgelistet werden.](media/baslinepolicies.png)
1. Lesen Sie die folgenden spezifischen Anweisungen für jede Richtlinie:

  - [MFA für Administratoren erforderlich](https://docs.microsoft.com/en-us/azure/active-directory/conditional-access/howto-baseline-protect-administrators)
- [MFA für Benutzer erforderlich](https://docs.microsoft.com/en-us/azure/active-directory/conditional-access/howto-baseline-protect-end-users)  
 - [Legacy Authentifizierung blockieren](https://docs.microsoft.com/en-us/azure/active-directory/conditional-access/howto-baseline-protect-legacy-auth)
  - [MFA für Service Management erforderlich](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-baseline-protect-azure)

Sie können viele zusätzliche Richtlinien einrichten, beispielsweise das Anfordern von genehmigten Client-apps. Weitere Informationen finden Sie in der [Dokumentation zum bedingten Zugriff](https://docs.microsoft.com/azure/active-directory/conditional-access/) .