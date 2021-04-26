---
title: Benutzern das Zurücksetzen ihrer eigenen Kennwörter gestatten
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- MSStore_Link
- TRN_M365B
- OKR_SMB_Videos
- AdminSurgePortfolio
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 5bc3f460-13cc-48c0-abd6-b80bae72d04a
description: Erfahren Sie, wie Sie Ihre Kennwörter mithilfe des Self-Service-Kennwortzurücksetzungstools zurücksetzen können.
ms.openlocfilehash: 0842430eda8c96647dd12d0da6d0c9e0481346dc
ms.sourcegitcommit: 72795ec56a7c4db863dcaaff5e9f7c41c653fda8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/26/2021
ms.locfileid: "52023761"
---
# <a name="let-users-reset-their-own-passwords"></a>Benutzern das Zurücksetzen ihrer eigenen Kennwörter gestatten

Als Microsoft 365-Administrator können Sie es Personen gestatten, das [Self-Service-Kennwortzurücksetzungstool](https://go.microsoft.com/fwlink/p/?LinkId=522677) zu verwenden, damit Sie keine Kennwörter für sie zurücksetzen müssen. Geringerer Arbeitsaufwand!
  
## <a name="before-you-begin"></a>Bevor Sie beginnen
  
- Sie erhalten die Self-Service-Kennwortzurücksetzung für Cloudbenutzer kostenlos mit einem beliebigen kostenpflichtigen Microsoft 365-Geschäfts-, Bildungs- oder gemeinnützigen Plan.  Es funktioniert nicht mit Microsoft 365-Testversion.

- Hierfür wird Azure verwendet. Sie erhalten dieses Feature in Azure automatisch **kostenlos**, wenn Sie diese Schritte ausführen. Die Aktivierung der Self-Service-Kennwortzurücksetzung kostet Sie nichts, falls Sie keine weiteren Azure-Features verwenden.

- **Wenn Sie ein lokales Active Directory verwenden,** gelten die beiden oben genannten Punkte nicht. Stattdessen können Sie dies einrichten, **aber es erfordert ein kostenpflichtiges Abonnement für Azure AD Premium.**

Dieser Artikel richtet sich an Personen, die eine Kennwortablaufrichtlinie für ein Unternehmen, eine Schule/Uni oder eine gemeinnützige Organisation festlegen. Um diese Schritte auszuführen, müssen Sie sich mit Ihrem Microsoft 365-Administratorkonto anmelden. [Was ist ein Administratorkonto?](https://docs.microsoft.com/microsoft-365/business-video/admin-center-overview)

Sie müssen ein globaler [Administrator oder Kennwortadministrator sein,](about-admin-roles.md) um diese Schritte ausführen zu können.

## <a name="watch-let-users-reset-their-own-passwords"></a>Watch: Benutzer können ihre eigenen Kennwörter zurücksetzen

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3AY8S]

Wenn Sie dieses Video hilfreich fanden, sehen Sie sich bitte die [komplette Schulungsserie für kleine Unternehmen und diejenigen, für die Microsoft 365 neu ist](../../business-video/index.yml) an.

## <a name="steps-let-people-reset-their-own-passwords"></a>Schritte: Personen können ihre eigenen Kennwörter zurücksetzen

Mit diesen Schritten aktivieren Sie die Self-Service-Kennwortzurücksetzung für jeden Benutzer in Ihrem Unternehmen.
  
::: moniker range="o365-worldwide"

1. Wechseln Sie <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">im Admin Center</a>zur **Einstellungsseite** > **"Organisationseinstellungen".**

::: moniker-end

::: moniker range="o365-germany"

1. Wechseln Sie <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">im Admin Center</a>zur Seite **Einstellungen** \> **Sicherheit &amp; Datenschutz.**

::: moniker-end

::: moniker range="o365-21vianet"

1. Wechseln Sie <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">im Admin Center</a>zur Seite **Einstellungen** \> **Einstellungen** \> **Sicherheit &amp; Datenschutz.**

::: moniker-end

2. Wählen Sie oben auf der Seite **Organisationseinstellungen** die Registerkarte **Sicherheit & Datenschutz** aus.
  
3. Wählen **Sie Self-Service Password Reset aus.**

4. Wählen **Sie unter Self-Service password reset** die Option Wechseln zum Azure-Portal aus, um die **Self-Service-Kennwortzurücksetzung zu aktivieren.**

5. Wählen Sie im linken Navigationsbereich **Benutzer** aus, und wählen Sie dann auf der Seite **Benutzer | Wählen Sie auf** der Seite Alle Benutzer die Option **Kennwortzurücksetzung aus.**
  
6. Wählen Sie **auf** der Seite Eigenschaften **alle** aus, um es für alle Benutzer in Ihrem Unternehmen zu aktivieren, und wählen Sie dann **Speichern aus.**
  
7. Wenn sich Ihre Benutzer anmelden, werden sie aufgefordert, zusätzliche Kontaktinformationen einzugeben, mit denen sie ihr Kennwort in Zukunft zurücksetzen können.

## <a name="related-content"></a>Verwandte Inhalte

[Festlegen der Kennwortablaufrichtlinie für Ihre Organisation](../manage/set-password-expiration-policy.md)

[Festlegen, dass das Kennwort eines einzelnen Benutzers nie abläuft](set-password-to-never-expire.md)

[Microsoft 365 Business-Schulungsvideos](../../business-video/index.yml)
