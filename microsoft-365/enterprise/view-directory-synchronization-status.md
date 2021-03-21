---
title: Anzeigen des Verzeichnissynchronisierungsstatus in Microsoft 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
ms.collection:
- Ent_O365
- M365-identity-device-management
search.appverid:
- MET150
- MOE150
- MED150
ms.assetid: 18be3b98-34ae-47be-9337-ab6c3fb372ac
description: In diesem Artikel erfahren Sie, wie Sie den Status Ihrer Verzeichnissynchronisierung in Office 365 überprüfen können.
ms.openlocfilehash: cbaae8bbd31f6124c2b0f4984b9a625ffbde538f
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50924660"
---
# <a name="view-directory-synchronization-status-in-microsoft-365"></a>Anzeigen des Verzeichnissynchronisierungsstatus in Microsoft 365

Wenn Sie Ihre lokalen Active Directory Domain Services (AD DS) in Azure Active Directory (Azure AD) integriert haben, indem Sie Ihre lokale Umgebung mit Microsoft 365 synchronisieren, können Sie auch den Status Ihrer Synchronisierung überprüfen.
  
## <a name="view-directory-synchronization-status"></a>Anzeigen des Status der Verzeichnissynchronisierung

- Melden Sie sich beim [Microsoft 365 Admin Center an,](https://admin.microsoft.com) und wählen Sie auf der Startseite **den DirSync-Status** aus.
- Alternativ können Sie zu **Benutzer** Aktive Benutzer wechseln, und wählen Sie auf der Seite Aktive Benutzer die Option \>  **Weitere**  \> **Verzeichnissynchronisierung aus.** Wählen Sie **im Bereich** Verzeichnissynchronisierung die Option Go **to DirSync management aus.**

## <a name="information-on-the-manage-directory-synchronization-page"></a>Informationen auf der Seite Verzeichnissynchronisierung verwalten

In der folgenden Tabelle sind die Features aufgeführt, über die Sie Informationen auf der Seite erhalten können.
  
Wenn ein Problem mit der Verzeichnissynchronisierung besteht, werden die Fehler auch auf dieser Seite aufgelistet. Weitere Informationen zu verschiedenen Fehlern, die auftreten können, finden Sie unter Identifizieren von Verzeichnissynchronisierungsfehlern [in Microsoft 365](identify-directory-synchronization-errors.md).
  
|Element|Zweck|
|:-----|:-----|
|**Überprüfte Domänen** | Anzahl der Domänen in Ihrem Microsoft 365-Mandanten, die Sie überprüft haben. |
|**Domänen nicht überprüft** | Domänen, die Sie hinzugefügt, aber nicht überprüft haben. |
|**Verzeichnissynchronisierung aktiviert** |"True" oder "False". Gibt an, ob Sie die Verzeichnissynchronisierung aktiviert haben. |
|**Neueste Verzeichnissynchronisierung** | Das letzte Mal, als die Verzeichnissynchronisierung gelaufen ist. Zeigt eine Warnung und einen Link zu einem Problembehandlungstool an, wenn die letzte Synchronisierung vor mehr als drei Tagen war. |
|**Kennwortsynchronisierung aktiviert** | "True" oder "False". Gibt an, ob Sie die Kennworthashsynchronisierung zwischen unserem lokalen und Ihrem Microsoft 365-Mandanten haben. |
|**Letzte Kennwortsynchronisierung** | Letzte Kennworthashsynchronisierung. Zeigt eine Warnung und einen Link zu einem Problembehandlungstool an, wenn die letzte Synchronisierung vor mehr als drei Tagen war. |
|**Verzeichnissynchronisierungsclientversion** | Enthält einen Downloadlink, wenn eine neue Version von Azure AD Connect veröffentlicht wurde. |
|**Verzeichnissynchronisierungsdienstkonto** | Zeigt den Namen Ihres Microsoft 365-Verzeichnissynchronisierungsdienstkontos an. |
|||

## <a name="monitor-synchronization-health"></a>Überwachen des Synchronisierungsstatus

In diesem Abschnitt installieren Sie einen Azure AD Connect Health-Agent auf den einzelnen lokalen AD DS-Domänencontrollern, um die Identitätsinfrastruktur und die von Azure AD Connect bereitgestellten Synchronisierungsdienste zu überwachen. Die Überwachungsinformationen werden in einem Azure AD Connect Health-Portal verfügbar gemacht, wo Sie Warnungen, Leistungsüberwachungsdaten, Nutzungsanalysen und andere Informationen anzeigen können.

Die wichtigste Entwurfsentscheidung hinsichtlich der Verwendung von Azure AD Connect Health basiert auf der Art und Weise, wie Sie Azure AD Connect verwenden:

- Wenn Sie die **verwaltete Authentifizierung** verwenden, beginnen Sie mit [Verwenden von Azure AD Connect Health mit Synchronisierung](/azure/active-directory/connect-health/active-directory-aadconnect-health-sync), um Informationen zur Funktionsweise und Konfiguration von Azure AD Connect Health zu erhalten.
- Wenn Sie nur die Namen der Konten und Gruppen mithilfe der **Verbundauthentifizierung** mit Active Directory-Verbunddiensten (AD FS) synchronisieren, beginnen Sie mit [Verwenden von Azure AD Connect Health mit AD FS](/azure/active-directory/connect-health/active-directory-aadconnect-health-adfs), um Informationen zur Funktionsweise und zur Konfiguration von Azure AD Connect Health zu erhalten.

Wenn Sie fertig sind, haben Sie:

- Der Azure AD Connect Health-Agent ist auf jedem Ihrer lokalen Identitätsanbieterserver installiert.
- Das Azure AD Connect Health-Portal zeigt den aktuellen Status Ihrer lokalen Infrastruktur und der Synchronisierungsaktivitäten mit dem Azure AD-Mandanten für Ihr Microsoft 365-Abonnement.