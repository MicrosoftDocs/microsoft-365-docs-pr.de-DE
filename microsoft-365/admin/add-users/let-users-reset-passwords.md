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
description: Erfahren Sie, wie Sie eine Richtlinie festlegen können, damit Benutzer ihre eigenen Kennwörter mithilfe des Self-Service-Kennwortzurücksetzungstools zurücksetzen können.
ms.openlocfilehash: 2c79d5611ab2db00f4de5f227b0ec2f411955558
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2021
ms.locfileid: "52571853"
---
# <a name="let-users-reset-their-own-passwords"></a>Benutzern das Zurücksetzen ihrer eigenen Kennwörter gestatten

Als Microsoft 365 Admin können Sie Es können Personen zulassen, dass sie das [Self-Service-Kennwort-Reset-Tool](https://go.microsoft.com/fwlink/p/?LinkId=522677) verwenden, sodass Sie keine Kennwörter für sie zurücksetzen müssen. Geringerer Arbeitsaufwand!
  
## <a name="before-you-begin"></a>Bevor Sie loslegen
  
- Sie erhalten Self-Service-Passwort-Reset für Cloud-Benutzer **kostenlos** mit jedem Microsoft 365 Business-, Bildungs- oder Non-Profit-Kosten-Plan. Es funktioniert nicht mit Microsoft 365 Test.

- Hierfür wird Azure verwendet. Sie erhalten dieses Feature in Azure automatisch **kostenlos**, wenn Sie diese Schritte ausführen. Die Aktivierung der Self-Service-Kennwortzurücksetzung kostet Sie nichts, falls Sie keine weiteren Azure-Features verwenden.

- **Wenn Sie ein lokal ansässiges Active Directory verwenden,** gelten die beiden oben genannten Punkte nicht. Sie können dies vielmehr einrichten, es ist jedoch **ein kostenpflichtiges Abonnement für Azure AD Premium** erforderlich.

Dieser Artikel richtet sich an Personen, die eine Kennwortablaufrichtlinie für ein Unternehmen, eine Schule/Uni oder eine gemeinnützige Organisation festlegen. Um diese Schritte auszuführen, müssen Sie sich mit Ihrem Microsoft 365-Administratorkonto anmelden. [Was ist ein Administratorkonto?](../../business-video/admin-center-overview.md)

Sie müssen ein [globaler Administrator oder Kennwortadministrator](about-admin-roles.md) sein, um diese Schritte ausführen zu können.

## <a name="watch-let-users-reset-their-own-passwords"></a>Sehen Sie: Lassen Sie Benutzer ihre eigenen Passwörter zurücksetzen

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3AY8S]

Wenn Sie dieses Video hilfreich fanden, sehen Sie sich bitte die [komplette Schulungsserie für kleine Unternehmen und diejenigen, für die Microsoft 365 neu ist](../../business-video/index.yml) an.

## <a name="steps-let-people-reset-their-own-passwords"></a>Schritte: Lassen Sie Menschen ihre eigenen Passwörter zurücksetzen

Mit diesen Schritten aktivieren Sie die Self-Service-Kennwortzurücksetzung für jeden Benutzer in Ihrem Unternehmen.

1. Wechseln Sie im <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Admin Center</a>zur Seite   >  **Einstellungen-Organisationseinstellungen.**

2. Wählen Sie oben auf der Seite **"Org-Einstellungen"** die Registerkarte **Sicherheit & Datenschutz** aus.
  
3. Wählen Sie **Self-Service Password Reset**.

4. Wählen Sie unter **Self-Service-Kennwortzurücksetzung** aus, und wählen Sie **Zum Azure-Portal wechseln aus, um das Zurücksetzen von Self-Service-Kennwörtern zu aktivieren.**

5. Wählen Sie im linken Navigationsbereich **Benutzer** aus, und dann im **| Alle Benutzer** Seite, wählen **Kennwort zurücksetzen**.
  
6. Wählen Sie auf der Seite **Eigenschaften** **alle** aus, um sie für alle Benutzer in Ihrem Unternehmen zu aktivieren, und wählen Sie dann **Speichern** aus.
  
7. Wenn sich Ihre Benutzer anmelden, werden sie aufgefordert, zusätzliche Kontaktinformationen einzugeben, die ihnen helfen, ihr Kennwort in Zukunft zurückzusetzen.

## <a name="related-content"></a>Verwandte Inhalte

[Festlegen der Kennwortablaufrichtlinie für Ihre Organisation](../manage/set-password-expiration-policy.md) (Artikel)

[Festlegen, dass das Kennwort eines einzelnen Benutzers nie abläuft](set-password-to-never-expire.md) (Artikel)

[Microsoft 365 Business Schulungsvideos](../../business-video/index.yml) (Linkseite)
