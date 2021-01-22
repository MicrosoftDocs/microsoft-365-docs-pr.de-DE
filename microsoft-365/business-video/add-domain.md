---
title: Domäne hinzufügen
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- adminvideo
- okr_smb
monikerRange: o365-worldwide
search.appverid:
- BCS160
- MET150
- MOE150
description: Erfahren Sie, wie Sie Ihrem Abonnement eine weitere Domäne hinzufügen.
ms.openlocfilehash: a5df440f3b7e28c2bdbc69f9383a8399ef193ed0
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/22/2021
ms.locfileid: "49927610"
---
# <a name="add-another-domain"></a>Hinzufügen einer weiteren Domäne

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4dN8c?autoplay=false]

Ihr Unternehmen benötigt möglicherweise mehrere Domänennamen für verschiedene Zwecke. Sie können beispielsweise eine andere Schreibweise Ihres Firmennamens hinzufügen, da Kunden ihn bereits verwenden und ihre Kommunikation Sie nicht erreichen konnte.

## <a name="try-it"></a>Probieren Sie es aus!

1. Wählen Sie im Microsoft 365 Admin Center **Setup aus.**
1. Wählen **Sie unter "Benutzerdefinierte Domäne einrichten einrichten"** die Option **"Ansicht" aus.**
1. Wählen **Sie "Verwalten"** und dann **"Domäne hinzufügen" aus.**
1. Geben Sie den neuen Domänennamen ein, den Sie hinzufügen möchten, und wählen Sie dann **"Weiter" aus.**
1. Melden Sie sich bei Ihrer Domänenregistrierungsstelle an, in diesem Fall GoDaddy, und wählen Sie dann **"Weiter" aus.**
1. Wenn Sie dazu aufgefordert werden, melden Sie sich bei Ihrer Registrierungsstelle an, und wählen Sie dann **"Autorisieren"** aus.
1. Choose **Add the DNS records for me**, and then select **Next**.
1. Wählen Sie die Dienste für Ihre neue Domäne aus, und aktivieren Sie die Kontrollkästchen für alle Dienste, die von einer anderen Domäne verarbeitet werden. Wenn Sie beispielsweise nur die neue Domäne für E-Mail verwenden möchten, wählen Sie **Exchange** aus, und aktivieren Sie die Kontrollkästchen für **Skype for Business** und die Verwaltung mobiler Geräte für Office **365.**
1. Wählen **Sie "Weiter",** **"Autorisieren", "Weiter"** und dann **"Fertig stellen" aus.**  Ihre neue Domäne wurde hinzugefügt.

Um E-Mails in Ihrer neuen Domäne zu empfangen, müssen Sie einen neuen E-Mail-Alias für jeden Benutzer hinzufügen:

1. Wählen **Sie "Benutzer"** und **"Aktive** Benutzer" aus, und wählen Sie dann den Benutzer aus, dem der neue Alias zugewiesen wird.
1. Wählen **Sie "Verwalten von E-Mail-Aliasen"** aus, und fügen **Sie dann einen Alias hinzu.**
1. Geben Sie den Benutzernamen ein, und wählen Sie dann die neue Domäne aus der Dropdownliste aus.
1. Wählen **Sie "Änderungen speichern"** aus, und schließen Sie dann das Fenster.
1. Wiederholen Sie diese Schritte für jeden Benutzer, der E-Mails in der neuen Domäne empfangen soll.