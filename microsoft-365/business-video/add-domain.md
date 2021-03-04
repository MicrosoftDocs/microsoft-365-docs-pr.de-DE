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
description: Erfahren Sie, wie Sie Ihrem Abonnement eine weitere Domäne hinzufügen.
ms.openlocfilehash: fef3dc06f270b79cc7f9e729b39727c9116b923d
ms.sourcegitcommit: 355bd51ab6a79d5c36a4e4f57df74ae6873eba19
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/04/2021
ms.locfileid: "50423083"
---
# <a name="add-another-domain"></a>Hinzufügen einer weiteren Domäne

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4dN8c?autoplay=false]

Ihr Unternehmen benötigt möglicherweise mehrere Domänennamen für verschiedene Zwecke. Sie können z. B. eine andere Schreibweise Ihres Firmennamens hinzufügen, da Kunden sie bereits verwenden und ihre Kommunikation Sie nicht erreicht hat.

## <a name="try-it"></a>Probieren Sie es aus!

1. Wählen Sie im Microsoft 365 Admin Center **Setup aus.**
1. Wählen **Sie unter Einrichten Ihrer benutzerdefinierten Domäne die** Option Ansicht **aus.**
1. Wählen **Sie Verwalten** und dann Domäne hinzufügen **aus.**
1. Geben Sie den neuen Domänennamen ein, den Sie hinzufügen möchten, und wählen Sie dann **Weiter aus.**
1. Melden Sie sich bei Ihrer Domänenregistrierungsstelle an, in diesem Fall GoDaddy, und wählen Sie dann **Weiter aus.**
1. Wenn Sie dazu aufgefordert werden, melden Sie sich bei Ihrer Registrierungsstelle an, und wählen Sie dann **Autorisieren aus.**
1. Wählen **Sie Hinzufügen der DNS-Einträge für mich** aus, und wählen Sie dann Weiter **aus.**
1. Wählen Sie die Dienste für Ihre neue Domäne aus, und aktivieren Sie die Kontrollkästchen für alle Dienste, die von einer anderen Domäne verarbeitet werden. Wenn Sie beispielsweise nur die neue Domäne für E-Mails verwenden möchten, wählen Sie **Exchange** aus, und aktivieren Sie die Kontrollkästchen für **Skype for Business** und Mobile Device Management für Office **365**.
1. Wählen **Sie Weiter**, **Autorisieren**, **Weiter** und dann Fertig **stellen aus.** Ihre neue Domäne wurde hinzugefügt.

Zum Empfangen von E-Mails in Ihrer neuen Domäne müssen Sie für jeden Benutzer einen neuen E-Mail-Alias hinzufügen:

1. Wählen **Sie Benutzer**, **Aktive** Benutzer und dann den Benutzer aus, dem der neue Alias zugewiesen wird.
1. Wählen **Sie Verwalten von E-Mail-Aliasen** aus, und fügen Sie dann einen Alias **hinzu.**
1. Geben Sie den Benutzernamen ein, und wählen Sie dann in der Dropdownliste die neue Domäne aus.
1. Wählen **Sie Änderungen speichern** aus, und schließen Sie das Fenster.
1. Wiederholen Sie diese Schritte für jeden Benutzer, der E-Mails in der neuen Domäne empfangen soll.