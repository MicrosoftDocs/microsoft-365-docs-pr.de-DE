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
ms.openlocfilehash: c777b9d840e0e9e467c1283fff94eca9a061ee73
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/22/2021
ms.locfileid: "49925554"
---
# <a name="let-users-reset-their-own-passwords"></a>Benutzern das Zurücksetzen ihrer eigenen Kennwörter gestatten

Als Microsoft 365-Administrator können Sie Personen die Verwendung des [Self-Service-Kennwortzurücksetzungstools](https://go.microsoft.com/fwlink/p/?LinkId=522677) gestatten, damit Sie keine Kennwörter für sie zurücksetzen müssen. Geringerer Arbeitsaufwand!
  
## <a name="before-you-begin"></a>Vorabinformationen
  
- Sie erhalten die Self-Service-Kennwortzurücksetzung für Cloudbenutzer kostenlos mit einem beliebigen kostenpflichtigen Microsoft 365 Business-, Education- oder gemeinnützigen Plan.  Es funktioniert nicht mit Microsoft 365-Testversionen.

- Hierfür wird Azure verwendet. Sie erhalten dieses Feature in Azure automatisch **kostenlos**, wenn Sie diese Schritte ausführen. Die Aktivierung der Self-Service-Kennwortzurücksetzung kostet Sie nichts, falls Sie keine weiteren Azure-Features verwenden.

- **Wenn Sie ein lokales Active Directory** verwenden, gelten die beiden oben genannten Punkte nicht. Stattdessen können Sie dies einrichten, aber **es erfordert ein kostenpflichtiges Abonnement von Azure AD Premium.**

Dieser Artikel richtet sich an Personen, die eine Kennwortablaufrichtlinie für ein Unternehmen, eine Schule/Uni oder eine gemeinnützige Organisation festlegen. Um diese Schritte auszuführen, müssen Sie sich mit Ihrem Microsoft 365-Administratorkonto anmelden. [Was ist ein Administratorkonto?](../admin-overview/admin-overview.md)

Sie müssen ein globaler [Administrator oder Kennwortadministrator](about-admin-roles.md) sein, um diese Schritte ausführen zu können.

## <a name="watch-let-users-reset-their-own-passwords"></a>Watch: Let users reset their own passwords

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3AY8S]

Wenn Sie dieses Video hilfreich fanden, sehen Sie sich bitte die [komplette Schulungsserie für kleine Unternehmen und diejenigen, für die Microsoft 365 neu ist](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816) an.

## <a name="steps-let-people-reset-their-own-passwords"></a>Schritte: Personen das Zurücksetzen ihrer eigenen Kennwörter gestatten

Mit diesen Schritten aktivieren Sie die Self-Service-Kennwortzurücksetzung für jeden Benutzer in Ihrem Unternehmen.
  
::: moniker range="o365-worldwide"

1. Wechseln Sie <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">im Admin Center</a>zur Einstellungsseite  > **"Organisationseinstellungen".**

::: moniker-end

::: moniker range="o365-germany"

1. Wechseln Sie <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">im Admin Center</a>zur Seite "Datenschutzeinstellungen".  \> **&amp;**

::: moniker-end

::: moniker range="o365-21vianet"

1. Wechseln Sie <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">im Admin Center</a>zur Seite "Datenschutzeinstellungen".  \>  \> **&amp;**

::: moniker-end

2. Wählen Sie oben auf der Seite **"Organisationseinstellungen"** die Registerkarte **"Sicherheit & Datenschutz"** aus.
  
3. Wählen Sie **Self-Service-Kennwortzurücksetzung aus.**

4. Wählen **Sie unter Self-Service-Kennwortzurücksetzung** die Option "Zum Azure-Portal wechseln" aus, um **die Self-Service-Kennwortzurücksetzung zu aktivieren.**

5. Wählen Sie im linken Navigationsbereich "Benutzer" und dann auf der Seite "Benutzer" **| Wählen Sie auf der** Seite "Alle Benutzer" die **Option "Kennwortzurücksetzung" aus.**
  
6. Wählen Sie **auf der Seite** "Eigenschaften" **"Alles"** aus, um es für alle Benutzer in Ihrem Unternehmen zu aktivieren, und wählen Sie dann **"Speichern" aus.**
  
7. Wenn sich Ihre Benutzer anmelden, werden sie aufgefordert, zusätzliche Kontaktinformationen einzugeben, mit denen sie ihr Kennwort in Zukunft zurücksetzen können.

## <a name="related-content"></a>Verwandte Inhalte

[Festlegen der Kennwortablaufrichtlinie für Ihre Organisation](../manage/set-password-expiration-policy.md)

[Festlegen, dass das Kennwort eines einzelnen Benutzers nie abläuft](set-password-to-never-expire.md)

[Microsoft 365 Business-Schulungsvideos](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816)
