---
title: Verwalten von sicheren Links
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
monikerRange: o365-worldwide
search.appverid:
- BCS160
- MET150
- MOE150
description: Hier erfahren Sie, wie Sie sichere Links zum Schutz Ihres Unternehmens vor bösartigen Websites verwalten.
ms.openlocfilehash: eabb2c1f71b1183867ffcb005ba4f7e44ed6e4b7
ms.sourcegitcommit: f231eece2927f0d01072fd092db1eab15525bbc2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/17/2020
ms.locfileid: "49702067"
---
# <a name="manage-safe-links"></a>Verwalten von sicheren Links

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWvdwy?autoplay=false]

Microsoft Defender für Office 365, früher als Microsoft 365 ATP oder Advanced Threat Protection bezeichnet, trägt zum Schutz Ihres Unternehmens vor bösartigen Websites bei, wenn Personen auf Links in Office-Apps klicken.

## <a name="try-it"></a>Probieren Sie es aus!

1. Wechseln Sie zum [Admin Center](https://admin.microsoft.com), und wählen Sie **Setup** aus.
1. Scrollen Sie nach unten, um den **Schutz vor erweiterten Bedrohungen zu erweitern**. Wählen Sie **anzeigen**, **Verwalten** und dann **ATP-sichere Links** aus.
1. Wählen Sie unter **Richtlinien, die für die gesamte Organisation gelten**, die **Standard** Richtlinie aus, und wählen Sie dann das Symbol **Bearbeiten** aus.
1. Geben Sie eine URL ein, die Sie blockieren möchten.
1. Wählen Sie **sichere Links in Office-Apps, Office für IOS und Android verwenden**; Wählen Sie **nicht nachverfolgen aus, wenn Benutzer auf sichere Links klicken**; und wählen Sie **nicht zulassen, dass Benutzer über sichere Links auf die ursprüngliche URL klicken**. Diese sind möglicherweise bereits ausgewählt, wenn Sie die Standardrichtlinie einrichten. Klicken Sie auf **Speichern**.
1. Wählen Sie unter **Richtlinien für bestimmte Empfänger** die Option **empfohlene Regel für sichere Links** aus, und wählen Sie dann das Symbol **Bearbeiten** aus.
1. Wählen Sie **Einstellungen**, Scrollen Sie nach unten, geben Sie die URL ein, die Sie nicht überprüfen möchten, und wählen Sie dann das Symbol **Hinzufügen** aus.
1. Wählen Sie **angewendet auf** aus, und wählen Sie dann Ihren Domänennamen aus. Wählen Sie alle weiteren Domänen aus, auf die die Regel angewendet werden soll. Wählen Sie **Hinzufügen**, **OK** und dann **Speichern** aus.

ATP-sichere Links sind jetzt konfiguriert. Erlauben Sie bis zu 30 Minuten, bis Ihre Änderungen wirksam werden.

Wenn ein Benutzer eine e-Mail mit Links erhält, werden die Links gescannt. Wenn die Links als sicher eingestuft werden, sind Sie klickbar. Wenn sich der Link jedoch in der Liste blockierter Listen befindet, wird Benutzern eine Meldung angezeigt, dass er blockiert wurde.