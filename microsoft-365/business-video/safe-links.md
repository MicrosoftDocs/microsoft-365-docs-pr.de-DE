---
title: Verwalten sicherer Links
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
description: Erfahren Sie, wie Sie sichere Links verwalten, um Ihr Unternehmen vor schädlichen Websites zu schützen.
ms.openlocfilehash: 1f5b3f61871e8d231029156631031dbb0ef4f2f5
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/22/2021
ms.locfileid: "49928018"
---
# <a name="manage-safe-links"></a>Verwalten sicherer Links

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWvdwy?autoplay=false]

Microsoft Defender für Office 365 , früher als Microsoft 365 ATP oder Advanced Threat Protection bezeichnet, schützt Ihr Unternehmen vor schädlichen Websites, wenn Benutzer auf Links in Office-Apps klicken.

## <a name="try-it"></a>Probieren Sie es aus!

1. Wechseln Sie zum [Admin Center,](https://admin.microsoft.com)und wählen Sie **Setup aus.**
1. Scrollen Sie nach unten, **um den Schutz vor erweiterten Bedrohungen zu erhöhen.** Wählen **Sie "Ansicht",** **"Verwalten"** und dann **"ATP-sichere Links" aus.**
1. Wählen **Sie unter Richtlinien, die für die gesamte** Organisation gelten, die Standardrichtlinie und dann das Bearbeitungssymbol aus.  
1. Geben Sie eine URL ein, die Sie blockieren möchten.
1. Wählen **Sie "Sichere Links in Office-Apps, Office für iOS und Android verwenden" aus.** select **Do not track when users click safe links**; und wählen **Sie "Benutzer nicht durch sichere Links zur ursprünglichen URL klicken lassen" aus.** Diese sind möglicherweise bereits ausgewählt, wenn Sie die Standardrichtlinie einrichten. Klicken Sie auf **Speichern**.
1. Wählen **Sie unter "Richtlinien, die für bestimmte Empfänger gelten"** **die** Regel "Empfohlene sichere Links" aus, und wählen Sie dann das Symbol **"Bearbeiten"** aus.
1. Wählen **Sie Einstellungen** aus, scrollen Sie nach unten, geben Sie die URL ein, die nicht überprüft werden soll, und wählen Sie dann das Symbol "Hinzufügen" aus. 
1. Wählen **Sie "Angewendet auf"** und dann Ihren Domänennamen aus. Wählen Sie alle zusätzlichen Domänen aus, auf die die Regel angewendet werden soll. Wählen **Sie "Hinzufügen",** **"OK"** und dann **"Speichern" aus.**

AtP Safe Links are now configured. Es kann bis zu 30 Minuten dauern, bis Ihre Änderungen wirksam werden.

Wenn ein Benutzer eine E-Mail mit Links empfängt, werden die Links überprüft. Wenn die Links als sicher eingestuft werden, können sie angeklickt werden. Wenn sich der Link jedoch in der Sperrliste befindet, wird Benutzern eine Meldung angezeigt, dass sie blockiert wurde.