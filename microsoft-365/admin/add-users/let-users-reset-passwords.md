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
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 5bc3f460-13cc-48c0-abd6-b80bae72d04a
description: Erfahren Sie, wie Sie Ihre Kennwörter mithilfe des Self-Service-Kenn Wort Zurücksetzungs Tools zurücksetzen können.
ms.openlocfilehash: bbde517858186d844412aca21f231620ed76496a
ms.sourcegitcommit: 38d828ae8d4350ae774a939c8decf30cb36c3bea
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2020
ms.locfileid: "49551920"
---
# <a name="let-users-reset-their-own-passwords"></a>Benutzern das Zurücksetzen ihrer eigenen Kennwörter gestatten

Als Microsoft 365-Administrator können Sie Benutzern das [Tool zum Zurücksetzen von Self-Service-Kennwörtern](https://go.microsoft.com/fwlink/p/?LinkId=522677) zur Verfügung stellen, damit Sie keine Kennwörter für diese zurücksetzen müssen. Geringerer Arbeitsaufwand!
  
## <a name="before-you-begin"></a>Bevor Sie beginnen:
  
- Sie erhalten Self-Service Password Reset für Cloud- **Benutzer mit** einem beliebigen Microsoft 365 Business-, Education-oder gemeinnützigen kostenpflichtigen Plan. Sie funktioniert nicht mit der Microsoft 365-Testversion.

- Hierfür wird Azure verwendet. Sie erhalten dieses Feature in Azure automatisch **kostenlos**, wenn Sie diese Schritte ausführen. Die Aktivierung der Self-Service-Kennwortzurücksetzung kostet Sie nichts, falls Sie keine weiteren Azure-Features verwenden.

- **Wenn Sie eine lokale Active Directory verwenden**, gelten die beiden folgenden Punkte nicht. Stattdessen können Sie dies einrichten, **es ist jedoch ein kostenpflichtiges Abonnement für Azure AD Premium erforderlich**.

Dieser Artikel richtet sich an Personen, die eine Kennwortablaufrichtlinie für ein Unternehmen, eine Schule/Uni oder eine gemeinnützige Organisation festlegen. Um diese Schritte auszuführen, müssen Sie sich mit Ihrem Microsoft 365-Administratorkonto anmelden. [Was ist ein Administratorkonto?](../admin-overview/admin-overview.md)

Sie müssen ein [globaler Administrator oder Kenn Wort Administrator](about-admin-roles.md) sein, um diese Schritte ausführen zu können.

## <a name="watch-let-users-reset-their-own-passwords"></a>Watch: Benutzer können Ihre eigenen Kennwörter zurücksetzen

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3AY8S]

Wenn Sie dieses Video hilfreich fanden, sehen Sie sich bitte die [komplette Schulungsserie für kleine Unternehmen und jene, die neu bei Microsoft 365 sind](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816), an.

## <a name="steps-let-people-reset-their-own-passwords"></a>Schritte: zulassen, dass Benutzer ihre eigenen Kennwörter zurücksetzen

Mit diesen Schritten aktivieren Sie die Self-Service-Kennwortzurücksetzung für jeden Benutzer in Ihrem Unternehmen.
  
::: moniker range="o365-worldwide"

1. Wechseln Sie im <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Admin Center</a>zur Seite **Einstellungen** für > **Organisations** Einstellungen.

::: moniker-end

::: moniker range="o365-germany"

1. Wechseln Sie im <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">Admin Center</a>zur Seite **Einstellungen** - \> **Sicherheits &amp; Datenschutz** .

::: moniker-end

::: moniker range="o365-21vianet"

1. Wechseln Sie im <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">Admin Center</a>zur Seite mit den **Einstellungen** für die \> **Settings** \> **Sicherheit der &amp; Datenschutz** Optionen.

::: moniker-end

2. Wählen Sie oben auf der Seite " **org-Einstellungen** " die Registerkarte **Sicherheit & Datenschutz** aus.
  
3. Wählen Sie **Self-Service Password Reset** aus.

4. Wählen Sie unter **Self-Service Password Reset** **die Option zum Azure-Portal wechseln aus, um Self-Service Password Reset zu aktivieren**.

5. Wählen Sie im linken Navigationsbereich **Benutzer** aus, und klicken Sie dann auf der Seite **Benutzer | Seite "alle Benutzer" die** Option **Kennwort zurücksetzen**.
  
6. Wählen Sie auf der Seite **Eigenschaften** die Option **alle** aus, um Sie für alle Benutzer in Ihrem Unternehmen zu aktivieren, und wählen Sie dann **Speichern** aus.
  
7. Wenn sich Ihre Benutzer anmelden, werden Sie aufgefordert, zusätzliche Kontaktinformationen einzugeben, mit denen Sie Ihr Kennwort in Zukunft zurücksetzen können.

## <a name="related-content"></a>Verwandte Inhalte

[Festlegen der Kennwortablaufrichtlinie für Ihre Organisation](../manage/set-password-expiration-policy.md)

[Festlegen, dass das Kennwort eines einzelnen Benutzers nie abläuft](set-password-to-never-expire.md)

[Microsoft 365 Business-Schulungsvideos](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816)
