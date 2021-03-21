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
description: Erfahren Sie, wie Sitzungstimeouts verwendet werden, um Sicherheit und einfacher Zugriff in Microsoft 365-Client-Apps zu gewährleisten.
ms.openlocfilehash: b85ed8a45727e8a8eed2537fa2233125cd05ece7
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50924916"
---
# <a name="session-timeouts-for-microsoft-365"></a>Sitzungstimeouts für Microsoft 365

Die Sitzungsdauer ist ein wichtiger Bestandteil der Authentifizierung für Microsoft 365 und eine wichtige Komponente für den Sicherheitsausgleich und die Anzahl der Benutzer, die zur Eingabe ihrer Anmeldeinformationen aufgefordert werden.

## <a name="session-times-for-microsoft-365-services"></a>Sitzungszeiten für Microsoft 365-Dienste

Wenn Benutzer sich in einer der Microsoft 365-Web-Apps oder mobilen Apps authentifizieren, wird eine Sitzung eingerichtet. Für die Dauer der Sitzung müssen sich Die Benutzer nicht erneut authentifizieren. Sitzungen können ablaufen, wenn Benutzer inaktiv sind, wenn sie den Browser oder die Registerkarte schließen oder wenn ihr Authentifizierungstoken aus anderen Gründen abläuft, z. B. wenn das Kennwort zurückgesetzt wurde. Die Microsoft 365-Dienste verfügen über unterschiedliche Sitzungstimeouts, die der typischen Verwendung der einzelnen Dienste entsprechen.

In der folgenden Tabelle sind die Sitzungsdauern für Microsoft 365-Dienste aufgeführt:

| Microsoft 365-Dienst | Sitzungstimeout |
|:-----|:-----|
|Microsoft 365 Admin Center  <br/> |Sie werden aufgefordert, alle 8 Stunden Anmeldeinformationen für das Admin Center zur Verfügung zu stellen.  <br/> |
|SharePoint Online  <br/> |5 Tage Inaktivität, solange die Benutzer mich angemeldet **lassen auswählen.** Wenn der Benutzer nach 24 oder mehr Stunden nach der vorherigen Anmeldung erneut auf SharePoint Online zutritt, wird der Timeoutwert auf 5 Tage zurückgesetzt.  <br/> |
|Outlook Web App  <br/> |6 Stunden.  <br/> Sie können diesen Wert mithilfe des  _Parameters ActivityBasedAuthenticationTimeoutInterval_ im [Cmdlet Set-OrganizationConfig](/powershell/module/exchange/set-organizationconfig) ändern.  <br/> |
|Azure Active Directory  <br/> (Wird von Office- und Microsoft 365-Anwendungen in Windows-Clients mit aktivierter moderner Authentifizierung verwendet)  <br/> | Die moderne Authentifizierung verwendet Zugriffstoken und Aktualisierungstoken, um Benutzern mithilfe von Azure Active Directory Zugriff auf Microsoft 365-Ressourcen zu gewähren. Ein Zugriffstoken ist ein JSON-Webtoken, das nach einer erfolgreichen Authentifizierung bereitgestellt wird und eine Stunde lang gültig ist. Ein Aktualisierungstoken mit einer längeren Lebensdauer wird ebenfalls bereitgestellt. Wenn Zugriffstoken ablaufen, verwenden Office-Clients ein gültiges Aktualisierungstoken, um ein neues Zugriffstoken abzurufen. Dieser Austausch ist erfolgreich, wenn die anfängliche Authentifizierung des Benutzers noch gültig ist.  <br/>  Aktualisierungstoken sind 90 Tage gültig und können bei fortlaufender Verwendung bis zum Widerruf gültig sein.  <br/>  Aktualisierungstoken können durch mehrere Ereignisse ungültig werden, z. B.:  <br/>  Das Kennwort des Benutzers hat sich seit dem Erstellen des Aktualisierungstokens geändert.  <br/>  Ein Administrator kann Richtlinien für bedingten Zugriff anwenden, die den Zugriff auf die Ressource einschränken, auf die der Benutzer zugreifen will.  <br/> |
|Mobile SharePoint- und OneDrive-Apps für Android, iOS und Windows 10  <br/> |Die Standardlebensdauer für das Zugriffstoken beträgt 1 Stunde. Die inaktive Standardzeit des Aktualisierungstokens beträgt 90 Tage.  <br/> [Weitere Informationen zu Token und zum Konfigurieren von Tokenlebensdauern](/azure/active-directory/active-directory-configurable-token-lifetimes) <br/> Zum Widerrufen des Aktualisierungstokens können Sie das Microsoft 365-Kennwort des Benutzers zurücksetzen.  <br/> |
|Yammer mit Microsoft 365 Sign-In  <br/> |Lebensdauer des Browsers. Wenn Benutzer den Browser schließen und Yammer in einem neuen Browser zugreifen, Yammer sie bei Microsoft 365 erneut authentifiziert. Wenn Benutzer Browser von Drittanbietern verwenden, die Cookies zwischenspeichern, müssen sie sich möglicherweise nicht erneut authentifizieren, wenn sie den Browser erneut öffnen.  <br/> > [!NOTE]> Dies gilt nur für Netzwerke, die Microsoft 365-Sign-In für Yammer.           |