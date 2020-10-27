---
title: Sitzungstimeouts für Microsoft 365
ms.author: tracyp
author: MSFTTracyP
manager: scotv
ms.date: 6/29/2018
audience: Admin
ms.topic: reference
ms.service: o365-administration
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
search.appverid:
- MET150
- MOE150
- MED150
- MBS150
- BCS160
ms.assetid: 37a5c116-5b07-4f70-8333-5b86fd2c3c40
ms.collection:
- M365-security-compliance
description: Erfahren Sie, wie Sitzungstimeouts verwendet werden, um die Sicherheit und den einfachen Zugriff in Microsoft 365-Client-apps auszugleichen.
ms.openlocfilehash: 2c0a7c2633715ac23942a22858b41e83a091c46a
ms.sourcegitcommit: 6647055154002c7d3b8f7ce25ad53c9636bc8066
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/27/2020
ms.locfileid: "48769292"
---
# <a name="session-timeouts-for-microsoft-365"></a>Sitzungstimeouts für Microsoft 365

Die Sitzungslebensdauer ist ein wichtiger Bestandteil der Authentifizierung für Microsoft 365 und eine wichtige Komponente für die Sicherheit und die Häufigkeit, mit der Benutzer zur Eingabe Ihrer Anmeldeinformationen aufgefordert werden.

## <a name="session-times-for-microsoft-365-services"></a>Sitzungszeiten für Microsoft 365-Dienste

Wenn sich Benutzer in einer der Microsoft 365-Webanwendungen oder Mobile Apps authentifizieren, wird eine Sitzung eingerichtet. Für die Dauer der Sitzung müssen sich die Benutzer nicht erneut authentifizieren. Sitzungen können ablaufen, wenn Benutzer inaktiv sind, wenn Sie den Browser oder die Registerkarte schließen oder wenn Ihr Authentifizierungstoken aus anderen Gründen abläuft, beispielsweise wenn Ihr Kennwort zurückgesetzt wurde. Die Microsoft 365-Dienste haben unterschiedliche Sitzungstimeouts, die mit der typischen Verwendung jedes Diensts übereinstimmen.

In der folgenden Tabelle sind die Sitzungslebensdauer für Microsoft 365-Dienste aufgeführt:

| Microsoft 365-Dienst | Sitzungstimeout |
|:-----|:-----|
|Microsoft 365 Admin Center  <br/> |Sie werden aufgefordert, die Anmeldeinformationen für das Admin Center alle 8 Stunden anzugeben.  <br/> |
|SharePoint Online  <br/> |5 Tage Inaktivität, solange die Benutzer sich für die Auswahl von **Keep Me angemeldet haben** . Wenn der Benutzer erneut auf SharePoint Online zugreift, nachdem 24 oder mehr Stunden von der vorherigen Anmeldung übergeben wurden, wird der Timeoutwert auf 5 Tage zurückgesetzt.  <br/> |
|Outlook Web App  <br/> |6 Stunden.  <br/> Sie können diesen Wert mithilfe des  _ActivityBasedAuthenticationTimeoutInterval_ -Parameters im Cmdlet " [OrganizationConfig](https://go.microsoft.com/fwlink/p/?LinkId=615378) " ändern.  <br/> |
|Azure Active Directory  <br/> (Wird von Office-und Microsoft 365-Anwendungen in Windows-Clients mit aktivierter moderner Authentifizierung verwendet)  <br/> | Bei der modernen Authentifizierung werden Zugriffstoken und Aktualisierungstoken verwendet, um Benutzer Zugriff auf Microsoft 365-Ressourcen mithilfe von Azure Active Directory zu gewähren. Ein Zugriffstoken ist ein JSON-webtoken, das nach erfolgreicher Authentifizierung bereitgestellt wird und 1 Stunde gültig ist. Ein Aktualisierungstoken mit einer längeren Lebensdauer wird ebenfalls bereitgestellt. Wenn Zugriffstoken ablaufen, verwenden Office-Clients ein gültiges Aktualisierungstoken, um ein neues Zugriffstoken zu erhalten. Dieser Exchange-Nachfolger ist erfolgreich, wenn die anfängliche Authentifizierung des Benutzers weiterhin gültig ist.  <br/>  Aktualisierungstoken sind 90 Tage gültig und können mit der dauerhaften Verwendung bis zum Widerruf gültig sein.  <br/>  Aktualisierungstoken können von mehreren Ereignissen für ungültig erklärt werden, beispielsweise:  <br/>  Das Kennwort des Benutzers wurde geändert, seit das Aktualisierungstoken ausgestellt wurde.  <br/>  Ein Administrator kann Richtlinien für bedingten Zugriff anwenden, die den Zugriff auf die Ressource einschränken, auf die der Benutzer zuzugreifen versucht.  <br/> |
|SharePoint-und OneDrive-Mobile Apps für Android, IOS und Windows 10  <br/> |Die Standardlebensdauer für das Zugriffstoken beträgt 1 Stunde. Die standardmäßige Max inaktive Zeit des Aktualisierungs Tokens beträgt 90 Tage.  <br/> [Weitere Informationen zu Token und zum Konfigurieren der Token-Gültigkeitsdauer](https://docs.microsoft.com/azure/active-directory/active-directory-configurable-token-lifetimes) <br/> Um das Aktualisierungstoken aufzuheben, können Sie das Microsoft 365-Kennwort des Benutzers zurücksetzen.  <br/> |
|Jammern mit Microsoft 365 Sign-In  <br/> |Gültigkeitsdauer des Browsers. Wenn Benutzer den Browser schließen und in einem neuen Browser auf jammern zugreifen, werden Sie von jammern erneut mit Microsoft 365 authentifiziert. Wenn Benutzer Drittanbieter Browser verwenden, die Cookies Zwischenspeichern, müssen Sie sich möglicherweise nicht erneut authentifizieren, wenn Sie den Browser erneut öffnen.  <br/> > [!NOTE]> Dies gilt nur für Netzwerke, die Microsoft 365 Sign-In für jammern verwenden.           |

