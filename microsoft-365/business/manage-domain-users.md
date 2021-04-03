---
title: Synchronisieren von Domänenbenutzern mit Microsoft 365
f1.keywords:
- NOCSH
ms.author: efrene
author: efrene
manager: scotv
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection: M365-subscription-management
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
- seo-marvel-mar
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
description: Synchronisieren sie domänengesteuerte Benutzer mit Microsoft 365 Business.
ms.openlocfilehash: b477b8a1f35a790d6c49937c973c141ad9f90ad4
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/02/2021
ms.locfileid: "51578405"
---
# <a name="synchronize-domain-users-to-microsoft-365"></a>Synchronisieren von Domänenbenutzern mit Microsoft 365

## <a name="1-prepare-for-directory-synchronization"></a>1. Vorbereiten der Verzeichnissynchronisierung 

Bevor Sie Ihre Benutzer und Computer aus der lokalen Active Directory-Domäne synchronisieren, lesen Sie Vorbereiten der Verzeichnissynchronisierung [mit Microsoft 365](../enterprise/prepare-for-directory-synchronization.md). Insbesondere:

   - Stellen Sie sicher, dass in Ihrem Verzeichnis keine Duplikate für die folgenden Attribute vorhanden sind: **mail**, **proxyAddresses** und **userPrincipalName**. Diese Werte müssen eindeutig sein, und alle Duplikate müssen entfernt werden.
   
   - Es wird empfohlen, das **UserPrincipalName** (UPN)-Attribut für jedes lokale Benutzerkonto so zu konfigurieren, dass es der primären E-Mail-Adresse entspricht, die dem lizenzierten Microsoft 365-Benutzer entspricht. Beispiel: *mary.shelley@contoso.com* anstatt *mary@contoso.local*
   
   - Wenn die Active Directory-Domäne in einem nicht routablen Suffix wie *.local* oder *.lan* endet, anstatt eines internetroutablen Suffixes wie *.com* oder *.org,* passen Sie zuerst das UPN-Suffix der lokalen Benutzerkonten an, wie unter [Prepare a non-routable domain for directory synchronization](../enterprise/prepare-a-non-routable-domain-for-directory-synchronization.md)beschrieben. 

Das **Ausführen von IdFix** in Schritt 4 (4) unten sorgt außerdem dafür, dass Ihr lokales Active Directory für die Verzeichnissynchronisierung bereit ist.

## <a name="2-install-and-configure-azure-ad-connect"></a>2. Installieren und Konfigurieren von Azure AD Connect

Um Ihre Benutzer, Gruppen und Kontakte aus dem lokalen Active Directory in Azure Active Directory zu synchronisieren, installieren Sie Azure Active Directory Connect, und richten Sie die Verzeichnissynchronisierung ein. 

 1. Wählen Sie [im Admin Center](https://go.microsoft.com/fwlink/p/?linkid=2024339) **setup** im linken Navigations navi aus.

 2. Wählen **Sie unter Anmeldung und Sicherheit** die Option **Anzeigen** aus dem Verzeichnis Ihrer Organisation unter Benutzer **synchronisieren aus.**

 3. Wählen Sie **auf der Verzeichnisseite Ihrer** Organisation Benutzer synchronisieren die Option Erste Schritte **aus.**

 4. Führen Sie im ersten Schritt das IdFix-Tool aus, um die Verzeichnissynchronisierung vorzubereiten.

 5. Führen Sie die Schritte des Assistenten aus, um Azure AD Connect herunterzuladen und sie zum Synchronisieren ihrer domänengesteuerten Benutzer mit Microsoft 365 zu verwenden.


Weitere Informationen finden Sie unter Einrichten der Verzeichnissynchronisierung für [Microsoft 365.](../enterprise/set-up-directory-synchronization.md)

Wenn Sie Ihre Optionen für Azure AD Connect konfigurieren, wird empfohlen, die  **Kennwortsynchronisierung,** das nahtlose einmalige Anmelden und das Kennwortrückschreiben zu aktivieren, das auch in Microsoft 365 Business unterstützt wird.

> [!NOTE]
> Es gibt einige zusätzliche Schritte für das Kennwortrückschreiben über das Kontrollkästchen in Azure AD Connect hinaus. Weitere Informationen finden Sie unter [How-to: configure password writeback](/azure/active-directory/authentication/howto-sspr-writeback). 

Wenn Sie auch Mit der Domäne beigetretene Windows 10-Geräte verwalten möchten, finden Sie weitere Informationen unter Aktivieren der Domänenverwaltung von Windows 10-Geräten, die von [Microsoft 365 Business Premium](manage-windows-devices.md) verwaltet werden, um einen Azure AD-Hybrid-Beitritt zu einrichten.