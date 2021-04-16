---
title: Domäne hinzufügen
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- adminvideo
monikerRange: o365-worldwide
search.appverid:
- BCS160
- MET150
- MOE150
description: Erfahren Sie, wie Sie Ihrem Abonnement eine weitere Domäne hinzufügen können.
ms.openlocfilehash: 8899cb9667ffa080746ca9173b61897f9c5db399
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/02/2021
ms.locfileid: "51579001"
---
# <a name="add-another-domain"></a>Hinzufügen einer weiteren Domäne

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4dN8c?autoplay=false]

In Ihrem Unternehmen könnten mehrere Domänennamen für unterschiedliche Zwecke benötigt werden. Beispielsweise könnte es sein, dass Sie eine andere Schreibweise für Ihren Firmennamen hinzufügen möchten, weil Kunden diese bereits verwenden und ihre Mitteilungen bei Ihnen nicht angekommen sind.

## <a name="try-it"></a>Probieren Sie es aus!

1. Wählen Sie im Microsoft 365 Admin Center **Einrichten** aus.
1. Wählen Sie unter **Benutzerdefinierte Domäne einrichten** die Option **Anzeigen** aus.
1. Wählen Sie **Verwalten** und dann **Domäne hinzufügen** aus.
1. Geben Sie den Namen der Domäne ein, die Sie hinzufügen möchten, und klicken Sie auf **Weiter**.
1. Melden Sie sich bei Ihrer Domänenregistrierungsstelle an, in diesem Fall GoDaddy, und klicken Sie dann auf **Weiter**.
1. Melden Sie sich bei der Registrierungsstelle an, sofern Sie dazu aufgefordert werden, und wählen Sie dann **Autorisieren** aus.
1. Wählen Sie **DNS-Einträge für mich hinzufügen** und dann **Weiter** aus.
1. Wählen Sie die Dienste für Ihre neue Domäne aus, und deaktivieren Sie die Kontrollkästchen für alle Dienste, die von einer anderen Domäne verarbeitet werden. Wenn Sie beispielsweise die neue Domäne nur für E-Mails verwenden möchten, wählen Sie **Exchange** aus, und deaktivieren Sie die Kontrollkästchen für **Skype for Business** und **Verwaltung mobiler Geräte für Office 365**.
1. Wählen Sie **Weiter**, **Autorisieren**, **Weiter** und dann **Fertigstellen** aus. Ihre neue Domäne wurde hinzugefügt.

Um E-Mails in Ihrer neuen Domäne zu empfangen, müssen Sie für jeden Benutzer einen neuen E-Mail-Alias hinzufügen:

1. Wählen Sie **Benutzer**, **Aktive Benutzer** und dann den Benutzer aus, dem der neue Alias zugewiesen werden soll.
1. Wählen Sie **Verwalten von E-Mail-Aliasen** und dann **Alias hinzufügen** aus.
1. Geben Sie den Benutzernamen ein, und wählen Sie dann in der Dropdownliste die neue Domäne aus.
1. Klicken Si auf **Änderungen speichern**, und schließen Sie dann das Fenster.
1. Wiederholen Sie diese Schritte für jeden Benutzer, der E-Mails in der neuen Domäne empfangen soll.