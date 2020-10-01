---
title: Anzeigen des Status der Verzeichnissynchronisierung in Microsoft 365
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
ms.openlocfilehash: 7577ed358a262d5b0ef2932bc73cf61941bec31b
ms.sourcegitcommit: 04c4252457d9b976d31f53e0ba404e8f5b80d527
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/01/2020
ms.locfileid: "48326949"
---
# <a name="view-directory-synchronization-status-in-microsoft-365"></a>Anzeigen des Status der Verzeichnissynchronisierung in Microsoft 365

Wenn Sie Ihre lokale Active Directory-Domänendienste (AD DS) mit Azure Active Directory (Azure AD) durch Synchronisieren Ihrer lokalen Umgebung mit Microsoft 365 integriert haben, können Sie auch den Status der Synchronisierung überprüfen.
  
## <a name="view-directory-synchronization-status"></a>Anzeigen des Status der Verzeichnissynchronisierung

- Melden Sie sich beim [Microsoft 365 Admin Center](https://admin.microsoft.com) an, und wählen Sie auf der Startseite **Dirsync-Status** aus.
- Alternativ können Sie zu " **Benutzer** \> **aktive**Benutzer" wechseln und auf der Seite " **aktive Benutzer** " **Weitere** \> **Verzeichnis Synchronisierungen**auswählen. Wählen Sie im Bereich **Verzeichnissynchronisierung** die Option **zu Dirsync-Verwaltung wechseln**aus.

## <a name="information-on-the-manage-directory-synchronization-page"></a>Informationen auf der Seite "Verzeichnissynchronisierung verwalten"

In der folgenden Tabelle sind die Features aufgeführt, auf denen Sie auf der Seite Informationen abrufen können.
  
Wenn ein Problem mit der Verzeichnissynchronisierung vorliegt, werden die Fehler auch auf dieser Seite aufgeführt. Weitere Informationen zu unterschiedlichen Fehlern, die auftreten können, finden Sie unter [Identifizieren von Verzeichnis Synchronisierungsfehlern in Microsoft 365](identify-directory-synchronization-errors.md).
  
|Element|Zweck|
|:-----|:-----|
|**Domänen überprüft** | Die Anzahl der Domänen in Ihrem Microsoft 365-Mandanten, die Sie selbst überprüft haben. |
|**Domänen nicht überprüft** | Domänen, die Sie hinzugefügt, aber nicht überprüft haben. |
|**Verzeichnissynchronisierung aktiviert** |True oder false. Gibt an, ob die Verzeichnissynchronisierung aktiviert ist. |
|**Neueste Verzeichnissynchronisierung** | Zeitpunkt der letzten Verzeichnissynchronisierung wurde ausgeführt. Zeigt eine Warnung und einen Link zu einem Tool zur Problembehandlung an, wenn die letzte Synchronisierung vor mehr als drei Tagen stattfand. |
|**Kennwortsynchronisierung aktiviert** | True oder false. Gibt an, ob eine Kennworthash Synchronisierung zwischen unserem lokalen und Ihrem Microsoft 365-Mandanten vorliegt. |
|**Letzte Kennwortsynchronisierung** | Das letzte Mal, als Password Hash Sync ausgeführt wurde. Zeigt eine Warnung und einen Link zu einem Tool zur Problembehandlung an, wenn die letzte Synchronisierung vor mehr als drei Tagen stattfand. |
|**Version des Verzeichnis Synchronisierungs Clients** | Enthält einen Download Link, wenn eine neue Version von Azure AD Connect veröffentlicht wurde. |
|**Verzeichnissynchronisierungsdienst Konto** | Zeigt den Namen Ihres Microsoft 365-Verzeichnissynchronisierungsdienst Kontos an. |
|||

## <a name="monitor-synchronization-health"></a>Überwachen des Synchronisierungsstatus

In diesem Abschnitt installieren Sie einen Azure AD Connect Health-Agent auf den einzelnen lokalen AD DS-Domänencontrollern, um die Identitätsinfrastruktur und die von Azure AD Connect bereitgestellten Synchronisierungsdienste zu überwachen. Die Überwachungsinformationen werden in einem Azure AD Connect Health-Portal verfügbar gemacht, wo Sie Warnungen, Leistungsüberwachungsdaten, Nutzungsanalysen und andere Informationen anzeigen können.

Die wichtigste Entwurfsentscheidung hinsichtlich der Verwendung von Azure AD Connect Health basiert auf der Art und Weise, wie Sie Azure AD Connect verwenden:

- Wenn Sie die **verwaltete Authentifizierung** verwenden, beginnen Sie mit [Verwenden von Azure AD Connect Health mit Synchronisierung](https://docs.microsoft.com/azure/active-directory/connect-health/active-directory-aadconnect-health-sync), um Informationen zur Funktionsweise und Konfiguration von Azure AD Connect Health zu erhalten.
- Wenn Sie nur die Namen der Konten und Gruppen mithilfe der **Verbundauthentifizierung** mit Active Directory-Verbunddiensten (AD FS) synchronisieren, beginnen Sie mit [Verwenden von Azure AD Connect Health mit AD FS](https://docs.microsoft.com/azure/active-directory/connect-health/active-directory-aadconnect-health-adfs), um Informationen zur Funktionsweise und zur Konfiguration von Azure AD Connect Health zu erhalten.

Wenn Sie fertig sind, haben Sie folgende Möglichkeiten:

- Der Azure AD Connect Health-Agent ist auf jedem Ihrer lokalen Identitätsanbieterserver installiert.
- Das Azure AD Connect Health-Portal zeigt den aktuellen Status Ihrer lokalen Infrastruktur und der Synchronisierungsaktivitäten mit dem Azure AD-Mandanten für Ihr Microsoft 365-Abonnement.

