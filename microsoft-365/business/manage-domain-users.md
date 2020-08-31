---
title: Synchronisieren von Domänenbenutzern mit Microsoft 365
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: sirkkuw
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
description: Synchronisieren Sie Domänen gesteuerte Benutzer mit Microsoft 365 for Business.
ms.openlocfilehash: 9495d893eb6870ef7c417a78f921296bfc0e6705
ms.sourcegitcommit: 555d756c69ac9031d1fb928f2e1f9750beede066
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/29/2020
ms.locfileid: "47306447"
---
# <a name="synchronize-domain-users-to-microsoft-365"></a>Synchronisieren von Domänenbenutzern mit Microsoft 365

## <a name="1-prepare-for-directory-synchronization"></a>1. Vorbereiten der Verzeichnissynchronisierung 

Bevor Sie Ihre Benutzer und Computer aus der lokalen Active Directory Domäne synchronisieren, überprüfen Sie die [Verzeichnissynchronisierung auf Microsoft 365](https://docs.microsoft.com/microsoft-365/enterprise/prepare-for-directory-synchronization). Insbesondere:

   - Stellen Sie sicher, dass in Ihrem Verzeichnis keine Duplikate für die folgenden Attribute vorhanden sind: **Mail**, **proxyAddresses**und **userPrincipalName**. Diese Werte müssen eindeutig sein, und alle Duplikate müssen entfernt werden.
   
   - Es wird empfohlen, das UPN-Attribut ( **userPrincipalName** ) für jedes lokale Benutzerkonto so zu konfigurieren, dass es mit der primären e-Mail-Adresse übereinstimmt, die dem lizenzierten Microsoft 365-Benutzer entspricht. Beispiel: *Mary.Shelley@contoso.com* statt *Mary@contoso. local*
   
   - Wenn die Active Directory Domäne in einem nicht routingfähigen Suffix wie *. local* oder *. LAN*endet, müssen Sie anstelle eines über das Internet routingfähigen Suffixes wie *. com* oder *. org*das UPN-Suffix der lokalen Benutzerkonten anpassen, wie unter [Vorbereiten einer nicht routingfähigen Domäne für die Verzeichnissynchronisierung](https://docs.microsoft.com/microsoft-365/enterprise/prepare-a-non-routable-domain-for-directory-synchronization)beschrieben. 

Mit dem unten **ausgeführten IdFix** in Schritt 4 (4) wird außerdem sichergestellt, dass Ihre lokale Active Directory für dir Sync bereit ist.

## <a name="2-install-and-configure-azure-ad-connect"></a>2. installieren und Konfigurieren von Azure AD Connect

Wenn Sie Ihre Benutzer, Gruppen und Kontakte vom lokalen Active Directory in Azure Active Directory synchronisieren möchten, installieren Sie Azure Active Directory Connect, und richten Sie die Verzeichnissynchronisierung ein. 

 1. Wählen Sie im Admin Center <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> unter **Setup** im linken Navigationsbereich aus.

 2. Wählen Sie unter **Anmeldung und Sicherheit**die Option **Ansicht**  unter **Synchronisierungs Benutzer aus dem Verzeichnis Ihrer Organisation aus**.

 3. Wählen Sie auf der Seite **Benutzer aus der org-Verzeichnissynchronisierung synchronisieren** die Option **Erste Schritte**aus.

 4. Im ersten Schritt führen Sie das IdFix-Tool aus, um die Verzeichnissynchronisierung vorzubereiten.

 5. Befolgen Sie die Schritte des Assistenten zum Herunterladen Azure AD Connect, und verwenden Sie diese, um Ihre domänengesteuerten Benutzer mit Microsoft 365 zu synchronisieren.


Weitere Informationen finden Sie unter [Einrichten der Verzeichnissynchronisierung für Microsoft 365](https://docs.microsoft.com/microsoft-365/enterprise/set-up-directory-synchronization) .

Wenn Sie Ihre Optionen für Azure AD Connect konfigurieren, wird empfohlen, dass Sie die **Kennwortsynchronisierung**, das **nahtlose einmalige Anmelden**und das **Kenn Wort Rückschreibe** Feature aktivieren, das auch in Microsoft 365 for Business unterstützt wird.

> [!NOTE]
> Es gibt einige zusätzliche Schritte für das Kenn Wort Rückschreiben über das Kontrollkästchen in Azure AD Connect hinaus. Weitere Informationen finden Sie unter [Vorgehensweise: Konfigurieren des Kenn Wort](https://docs.microsoft.com/azure/active-directory/authentication/howto-sspr-writeback)Rückschreibens. 

Wenn Sie auch Domänen verbundene Windows 10-Geräte verwalten möchten, finden Sie weitere Informationen unter [enable Domain-Joined Windows 10 Devices to manage by Microsoft 365 Business Premium](manage-windows-devices.md) , um eine hybride Azure AD Join einzurichten. 