---
title: Einrichten der mehrstufigen Authentifizierung für Office 365-Benutzer
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: sirkkuw
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
- GEA150
ms.assetid: 8f0454b2-f51a-4d9c-bcde-2c48e41621c6
description: Informationen zur Verwendung der Sicherheitsstandardeinstellungen zum Einrichten der mehrstufigen Authentifizierung für Office 365-Benutzer.
monikerRange: o365-worldwide
ms.openlocfilehash: bc906299e42929dd4dd09b94502a6d463a5971b4
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/24/2020
ms.locfileid: "42254204"
---
# <a name="set-up-multi-factor-authentication"></a>Einrichten der mehrstufigen Authentifizierung
  
Bei jedem neuen Office 365 Business- oder Microsoft 365 Business-Abonnement sind die Sicherheitseinstellungen automatisch aktiviert. Dies bedeutet, dass jeder Benutzer die mehrstufige Authentifizierung (MFA) einrichten und die Authenticator-App auf seinem mobilen Gerät installieren muss. Weitere Informationen finden Sie unter [Einrichten der Prüfung in zwei Schritten für Office 365](https://support.office.com/article/ace1d096-61e5-449b-a875-58eb3d74de14).  

Für die folgenden neun Administratorrollen ist bei jeder Anmeldung eine zusätzliche Authentifizierung erforderlich:
- Globaler Administrator
- SharePoint-Administrator
- Exchange-Administrator
- Administrator für bedingten Zugriff
- Sicherheitsadministrator
- Helpdesk- oder Kennwortadministrator
- Abrechnungsadministrator
- Benutzeradministrator
- Authentifizierungsadministrator

Alle anderen Benutzer werden bei Bedarf zu einer weiteren Authentifizierung aufgefordert. Weitere Informationen hierzu finden Sie unter [Was sind Standardsicherheitseinstellungen?](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)

> [!NOTE]
> Sie müssen ein globaler Office 365-Administrator sein, um die mehrstufige Authentifizierung einzurichten oder zu ändern. <br><br>
> Wenn Sie das neue Microsoft 365 Admin Center nicht verwenden, können Sie es aktivieren, indem Sie den Umschalter **Das neue Admin Center** am oberen Rand der Startseite auswählen.

Wenn Sie zuvor die mehrstufige Authentifizierung mit Basisrichtlinien eingerichtet haben, müssen Sie [diese deaktivieren und die Standardsicherheitseinstellungen aktivieren](#move-from-baseline-policies-to-security-defaults). Wenn Sie hingegen über Microsoft 365 Business verfügen oder Ihr Abonnement [Azure Active Directory Premium 1 oder Azure Active Directory Premium 2](https://azure.microsoft.com/pricing/details/active-directory/) enthält, können Sie auch Richtlinien für den [bedingten Zugriff](https://docs.microsoft.com/azure/active-directory/conditional-access/overview) einrichten. Um Richtlinien für den bedingten Zugriff verwenden zu können, müssen Sie sicherstellen, dass die Option für die [moderne Authentifizierung](#enable-multi-factor-authentication-for-your-organization) aktiviert ist.

## <a name="manage-security-defaults"></a>Verwalten von Sicherheitsstandards

1. Melden Sie sich beim [Admin Center](https://go.microsoft.com/fwlink/p/?linkid=834822) mit Ihren globalen Administratoranmeldeinformationen an.
2. Wechseln Sie zu [Azure Active Directory-Eigenschaften](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).

3. Wählen Sie am unteren Rand der Seite **Sicherheitsstandards verwalten** aus.
4. Wählen Sie **Ja** aus, um Sicherheitsstandards zu aktivieren, und **Nein**, um Sicherheitsstandards zu deaktivieren.

## <a name="move-from-baseline-policies-to-security-defaults"></a>Von Basisrichtlinien zu Sicherheitsstandards wechseln

1. Wählen Sie im [Admin Center](https://go.microsoft.com/fwlink/p/?linkid=834822) die Option **Setup** aus.

2. Wählen Sie neben **Anmeldung und Sicherheit** unter **Anmeldung sicherer machen** die Option **Anzeigen** aus.

3. Wählen Sie unter **Anmeldung sicherer machen** die Option **Verwalten** aus. 

4. Wählen Sie auf der Seite **Bedingter Zugriff auf das Azure-Portal – Richtlinien** jede Basisrichtlinie aus, die **aktiviert** ist, und **deaktivieren** Sie sie.
5. Wechseln Sie zur Seite [Azure Active Directory-Eigenschaften](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).
6. Wählen Sie am unteren Rand der Seite **Sicherheitsstandards verwalten** aus, und legen Sie im Bereich **Sicherheitsstandards aktivieren** für die Option **Sicherheitsstandards aktivieren** **Ja** fest. 

## <a name="enable-modern-authentication-for-your-organization"></a>Aktivieren der modernen Authentifizierung für Ihre Organisation

Alle Office 2016-Clientanwendungen unterstützen MFA durch die Nutzung der Active Directory-Authentifizierungsbibliothek (Active Directory Authentication Library, ADAL). Dies bedeutet, dass App-Kennwörter für Office 2016-Clients nicht erforderlich sind. Sie müssen jedoch sicherstellen, dass Ihr Office 365-Abonnement für ADAL oder die moderne Authentifizierung aktiviert ist.

1. Wenn Sie die moderne Authentifizierung aktivieren möchten, wählen Sie im [Admin Center](https://go.microsoft.com/fwlink/p/?linkid=834822) die Option **Einstellungen** \> **Einstellungen**, und dann auf der Registerkarte **Dienste** die Option **Moderne Authentifizierung** aus der Liste aus.

2. Aktivieren Sie das Kontrollkästchen **Moderne Authentifizierung aktivieren** im Bereich **Moderne Authentifizierung**. 

    ![Bereich "Moderne Authentifizierung" mit aktiviertem Kontrollkästchen "Moderne Authentifizierung aktivieren".](../media/enablemodernauth.png)
    
## <a name="enable-multi-factor-authentication-for-your-organization"></a>Aktivieren der mehrstufigen Authentifizierung für Ihre Organisation
    
1. Wählen Sie im [Admin Center](https://go.microsoft.com/fwlink/p/?linkid=834822)die Option **Users** und **Active Users**aus.

2. Klicken Sie im Abschnitt **aktive Benutzer** auf mehrstufige **Authentifizierung**.

3. Wählen Sie auf der Seite mehrstufige **Authentifizierung** die Option **Benutzer** aus, wenn Sie dies für einen Benutzer aktivieren, oder Sie können eine **Massenaktualisierung**führen.

4. Klicken Sie unter **Quick Steps**auf **aktivieren** .

5. Klicken Sie im Popupfenster auf CLickc, um die mehrstufige **Authentifizierung zu aktivieren**.

Nachdem Sie die mehrstufige Authentifizierung für Ihre Organisation eingerichtet haben, müssen die Benutzer auf ihren Geräten die Prüfung in zwei Schritten einrichten. Weitere Informationen finden Sie unter [Einrichten der Prüfung in zwei Schritten für Office 365](https://support.office.com/article/ace1d096-61e5-449b-a875-58eb3d74de14).
    
> [!TIP]
> Wenn Sie Ihren Benutzern erklären möchten, wie die Authenticator-App eingerichtet wird, lesen Sie [Verwenden von Microsoft Authenticator mit Office 365](https://support.office.com/article/use-microsoft-authenticator-with-office-365-1412611f-ad8d-43ab-807c-7965e5155411?ui=en-US&rs=en-US&ad=US#ID0EAADAAA=_Step_1).


> [!IMPORTANT]
> Seit August 2017 ist die moderne Authentifizierung (MA) auf allen neuen Office 365-Mandanten, die Skype for Business Online und Exchange Online umfassen, standardmäßig aktiviert. Um Ihren MA-Status für Skype for Business Online zu überprüfen, können Sie Skype for Business Online-PowerShell mit Anmeldeinformationen eines globalen Administrators verwenden. Führen Sie "Get-CsOAuthConfiguration" aus, um die Ausgabe von "-ClientADALAuthOverride" zu überprüfen. Wenn "-ClientADALAuthOverride" den Wert "Allowed" aufweist, ist die moderne Authentifizierung aktiviert.
Informationen zum Überprüfen Ihres MA-Status für Exchange Online finden Sie unter [Aktivieren der modernen Authentifizierung in Exchange Online](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online).

## <a name="related-articles"></a>Verwandte Artikel

[Top 10 Methoden zum Sichern von Office 365 und Microsoft 365 Business-Pläne](secure-your-business-data.md)

[Aktivieren der modernen Authentifizierung für Office 2013 auf Windows-Geräten](enable-modern-authentication.md)
