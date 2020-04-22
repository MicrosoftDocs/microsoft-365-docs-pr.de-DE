---
title: Einrichten der mehrstufigen Authentifizierung für Benutzer
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
description: In diesem Artikel erfahren Sie, wie Sie Sicherheitsstandards zum Einrichten der mehrstufigen Authentifizierung für Benutzer verwenden.
monikerRange: o365-worldwide
ms.openlocfilehash: 1000689794b8b5471efa898e731fd75a0e5a8cce
ms.sourcegitcommit: 7c0470fd7a98911d142bac060c228947c46a6be7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/22/2020
ms.locfileid: "43665632"
---
# <a name="set-up-multi-factor-authentication"></a>Einrichten der mehrstufigen Authentifizierung
  
> [!IMPORTANT]
> Wenn Sie Ihr Abonnement oder eine Testversion nach dem 21. Oktober 2019 gekauft haben und Sie unerwarteterweise zur Eingabe einer mehrstufigen Authentifizierung (Multi-Factor Authentication, MFA) aufgefordert werden, wurden [Sicherheitsstandards](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults) automatisch für Ihr Abonnement aktiviert.

Für jedes neue Microsoft 365-Abonnement werden automatisch [Sicherheitsstandards](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults) aktiviert. Dies bedeutet, dass jeder Benutzer die Multi-Factor Authentication (MFA) einrichten und die Microsoft Authenticator-App auf seinem mobilen Gerät installieren muss. Weitere Informationen finden Sie unter [Einrichten von MFA für ein Microsoft 365-Konto](https://support.office.com/article/ace1d096-61e5-449b-a875-58eb3d74de14).

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

Alle anderen Benutzer werden bei Bedarf zu einer weiteren Authentifizierung aufgefordert.

> [!NOTE]
> Sie müssen ein globaler Administrator sein, um MFA einzurichten oder zu ändern. <br><br>
> Wenn Sie das neue Microsoft 365 Admin Center nicht verwenden, können Sie es aktivieren, indem Sie den Umschalter **Das neue Admin Center** am oberen Rand der Startseite auswählen.

Wenn Sie zuvor MFA mit Basisrichtlinien eingerichtet haben, [müssen Sie diese deaktivieren, um Sicherheitsstandards zu aktivieren](#move-from-baseline-policies-to-security-defaults). Wenn Sie jedoch über Microsoft 365 Business verfügen oder Ihr Abonnement [Azure Active Directory Premium P1 oder Azure Active Directory Premium P2](https://azure.microsoft.com/pricing/details/active-directory/)enthält, können Sie auch Richtlinien für [bedingten Zugriff](https://docs.microsoft.com/azure/active-directory/conditional-access/overview) einrichten. Um Richtlinien für bedingten Zugriff zu verwenden, müssen Sie sicherstellen, dass die Sicherheitseinstellungen deaktiviert sind und die [moderne Authentifizierung](#enable-modern-authentication-for-your-organization) aktiviert ist.

> [!TIP]
> Um Ihren Benutzern zu erklären, wie Sie die Microsoft Authenticator-App einrichten, lesen Sie [Verwenden von Microsoft Authenticator mit Office 365](https://support.office.com/article/use-microsoft-authenticator-with-office-365-1412611f-ad8d-43ab-807c-7965e5155411).

## <a name="manage-security-defaults"></a>Verwalten von Sicherheitsstandards

1. Melden Sie sich beim [Admin Center](https://go.microsoft.com/fwlink/p/?linkid=834822) mit globalen Administratoranmeldeinformationen an.
2. Wechseln Sie zur [Seite Azure Active Directory-Eigenschaften](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).
3. Wählen Sie am unteren Rand der Seite **Sicherheitsstandards verwalten** aus.
4. Wählen Sie **Ja** aus, um Sicherheitsstandards zu aktivieren, und **Nein** , um Sicherheitsstandards zu deaktivieren, und wählen Sie dann **Speichern**aus.

## <a name="move-from-baseline-policies-to-security-defaults"></a>Von Basisrichtlinien zu Sicherheitsstandards wechseln

1. Wechseln Sie zur [Seite bedingte Zugriffs-Richtlinien](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade/Policies).
2. Wählen Sie die einzelnen Basisrichtlinien **aus, und legen** Sie die **Option Richtlinie aktivieren** auf **aus**fest.
3. Wechseln Sie zur [Seite Azure Active Directory-Eigenschaften](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).
4. Klicken Sie unten auf der Seite auf **Sicherheitsstandards verwalten**, und wählen Sie im Bereich **Sicherheitsstandard Einstellungen aktivieren** die Option **Sicherheits Standardwerte aktivieren** auf **Ja**, und klicken Sie dann auf **Speichern**. 

## <a name="enable-modern-authentication-for-your-organization"></a>Aktivieren der modernen Authentifizierung für Ihre Organisation

Alle Office 2016-Clientanwendungen unterstützen MFA durch die Nutzung der Active Directory-Authentifizierungsbibliothek (Active Directory Authentication Library, ADAL). Dies bedeutet, dass App-Kennwörter für Office 2016-Clients nicht erforderlich sind. Sie müssen jedoch sicherstellen, dass Ihr Microsoft 365-Abonnement für Adal oder moderne Authentifizierung aktiviert ist.

1. Wenn Sie die moderne Authentifizierung aktivieren möchten, wählen Sie im [Admin Center](https://go.microsoft.com/fwlink/p/?linkid=834822) die Option **Einstellungen** \> **Einstellungen**, und dann auf der Registerkarte **Dienste** die Option **Moderne Authentifizierung** aus der Liste aus.

2. Aktivieren Sie das Kontrollkästchen **moderne Authentifizierung aktivieren (empfohlen)** im Bereich **moderne Authentifizierung** , und wählen Sie dann **Save Changes**aus. 

    ![Bereich "Moderne Authentifizierung" mit aktiviertem Kontrollkästchen "Moderne Authentifizierung aktivieren".](../../media/enablemodernauth.png)
    
> [!IMPORTANT]
> Ab August 2017 werden alle neuen Microsoft 365-Abonnements, die Skype for Business Online und Exchange Online einschließen, standardmäßig mit moderner Authentifizierung aktiviert. Um Ihren MA-Status für Skype for Business Online zu überprüfen, können Sie Skype for Business Online-PowerShell mit Anmeldeinformationen eines globalen Administrators verwenden. Führen Sie "Get-CsOAuthConfiguration" aus, um die Ausgabe von "-ClientADALAuthOverride" zu überprüfen. Wenn "-ClientADALAuthOverride" den Wert "Allowed" aufweist, ist die moderne Authentifizierung aktiviert.
Informationen zum Überprüfen Ihres MA-Status für Exchange Online finden Sie unter [Aktivieren der modernen Authentifizierung in Exchange Online](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online).

## <a name="related-articles"></a>Verwandte Artikel

[Die 10 wichtigsten Möglichkeiten zum Sichern von Microsoft 365 for Business-Plänen](secure-your-business-data.md)

[Aktivieren der modernen Authentifizierung für Office 2013 auf Windows-Geräten](enable-modern-authentication.md)
