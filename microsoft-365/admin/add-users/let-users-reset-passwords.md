---
title: Zulassen, dass Benutzer ihre eigenen Kennwörter in Office 365 zurücksetzen
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
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
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 5bc3f460-13cc-48c0-abd6-b80bae72d04a
description: Erfahren Sie, wie Sie Ihre Kennwörter mithilfe des Self-Service-Kenn Wort Zurücksetzungs Tools zurücksetzen können.
ms.openlocfilehash: 666d3843f7917cf9bd5718c0ce29f87f93d6effe
ms.sourcegitcommit: 4a34b48584071e0c43c920bb35025e34cb4f5d15
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/09/2020
ms.locfileid: "43211895"
---
# <a name="let-users-reset-their-own-passwords"></a>Benutzern das Zurücksetzen ihrer eigenen Kennwörter gestatten

Werden Sie öfter von Personen bedrängt, die Sie bitten, ihre Kennwörter zurückzusetzen? Als Microsoft 365-Administrator können Sie Benutzern das [Tool zum Zurücksetzen von Self-Service-Kennwörtern](https://go.microsoft.com/fwlink/p/?LinkId=522677) zur Verfügung stellen, damit Sie keine Kennwörter für diese zurücksetzen müssen. Geringerer Arbeitsaufwand! 
  
Hier sind ein paar Dinge, die Sie wissen müssen:
  
- In jedem kostenpflichtigen Office 365 Business-, Education- oder Non-Profit-Plan ist die Self-Service-Kennwortzurücksetzung für Cloudbenutzer **kostenlos**. In der Office 365-Testversion funktioniert sie jedoch nicht. 
    
- Hierfür wird Azure verwendet. Sie erhalten dieses Feature in Azure automatisch **kostenlos**, wenn Sie diese Schritte ausführen. Die Aktivierung der Self-Service-Kennwortzurücksetzung kostet Sie nichts, falls Sie keine weiteren Azure-Features verwenden. 
    
- **Wenn Sie eine lokale Active Directory verwenden**, gelten die beiden folgenden Punkte nicht. Stattdessen können Sie dies einrichten, **es ist jedoch ein kostenpflichtiges Abonnement für Azure AD Premium erforderlich**. 

Sehen Sie sich ein kurzes Video an, in dem Benutzer ihre eigenen Kennwörter zurücksetzen lassen. <br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3AY8S] 

Wenn Sie dieses Video hilfreich fanden, sehen Sie sich bitte die [komplette Schulungsserie für kleine Unternehmen und jene, die neu bei Microsoft 365 sind](https://support.office.com/article/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816), an.

## <a name="let-people-reset-their-own-passwords"></a>Zulassen, dass Benutzer ihre eigenen Kennwörter zurücksetzen 

Mit diesen Schritten aktivieren Sie die Self-Service-Kennwortzurücksetzung für jeden Benutzer in Ihrem Unternehmen.
  
::: moniker range="o365-worldwide"
1.  Wechseln Sie im Admin Center zur Seite **Einstellungen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2072756" target="_blank">Sicherheit & Privatsphäre</a> .

::: moniker-end

::: moniker range="o365-germany"

1. Wechseln Sie im <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">Admin Center</a>zur Seite **Einstellungen** \> - **Sicherheits &amp; Datenschutz** .

::: moniker-end

::: moniker range="o365-21vianet"

1. Wechseln Sie im <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">Admin Center</a>zur Seite **Einstellungen** \> - **Sicherheits &amp; Datenschutz** .

::: moniker-end

   
2. Wählen Sie unter zulassen, dass **Ihre Personen Ihre eigenen Kennwörter zurücksetzen**die Verknüpfung für das **Azure AD Admin Center**aus. Azure wird kostenlos zur Verfügung gestellt!
  
3. Wählen Sie im linken Navigationsbereich die Option **Benutzer** aus, und wählen Sie dann **Kennwortzurücksetzung**aus.
  
4. Wählen Sie auf der Seite Eigenschaften die Option **alle** aus, um Sie für alle Benutzer in Ihrem Unternehmen zu aktivieren, und wählen Sie dann **Speichern**aus.
  
5. Wenn sich Ihre Benutzer bei Office 365 anmelden, werden sie zur Eingabe zusätzlicher Kontaktinformationen aufgefordert, mit denen sie ihr Kennwort künftig zurücksetzen können.

## <a name="related-articles"></a>Verwandte Artikel

[Festlegen der Kennwortablaufrichtlinie für Ihre Organisation](../manage/set-password-expiration-policy.md)
  
[Festlegen, dass das Kennwort eines einzelnen Benutzers nie abläuft](set-password-to-never-expire.md)

[Microsoft 365 Business-Schulungsvideos](https://support.office.com/article/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816)
