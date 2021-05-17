---
title: Verwalten sicherer Links
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
ms.custom:
- AdminSurgePortfolio
- adminvideo
monikerRange: o365-worldwide
search.appverid:
- BCS160
- MET150
- MOE150
description: Erfahren Sie, wie Sie sichere Links verwalten, um Ihr Unternehmen vor schädlichen Websites zu schützen.
ms.openlocfilehash: ce0c1ba6e4099b6eaf4ec974938170020b8a5892
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/02/2021
ms.locfileid: "51580630"
---
# <a name="manage-safe-links"></a>Verwalten sicherer Links

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWvdwy?autoplay=false]

Microsoft Defender für Office 365 , früher als Microsoft 365 ATP oder Advanced Threat Protection bezeichnet, schützt Ihr Unternehmen vor schädlichen Websites, wenn Benutzer auf Links in Office klicken.

## <a name="try-it"></a>Probieren Sie es aus!

1. Wechseln Sie zum [Admin Center,](https://admin.microsoft.com)und wählen Sie **Setup aus.**
1. Scrollen Sie nach unten, **um den Schutz vor erweiterten Bedrohungen zu erhöhen.** Wählen **Sie Ansicht,** **Verwalten** und dann **ATP Sichere Links aus.**
1. Wählen **Sie unter Richtlinien, die für die gesamte Organisation gelten,** die **Standardrichtlinie** aus, und wählen Sie dann das **Symbol Bearbeiten** aus.
1. Geben Sie eine URL ein, die Sie blockieren möchten.
1. Wählen **Sie Sichere Links in Office apps, Office für iOS und Android verwenden** aus. wählen **Sie Nicht nachverfolgen aus, wenn Benutzer auf sichere Links klicken.** und wählen Sie Benutzer nicht durch sichere Links **zur ursprünglichen URL klicken lassen aus.** Diese sind möglicherweise bereits ausgewählt, wenn Sie die Standardrichtlinie einrichten. Klicken Sie auf **Speichern**.
1. Wählen **Sie unter Richtlinien, die für bestimmte Empfänger** gelten, Die Regel Empfohlene sichere **Links** aus, und wählen Sie dann das Symbol **Bearbeiten** aus.
1. Wählen **Sie Einstellungen** aus, scrollen Sie nach unten, geben Sie die URL ein, die nicht überprüft werden soll, und wählen Sie dann das Symbol **Hinzufügen** aus.
1. Wählen **Sie auf** angewendet aus, und wählen Sie dann Ihren Domänennamen aus. Wählen Sie alle zusätzlichen Domänen aus, auf die die Regel angewendet werden soll. Wählen **Sie Hinzufügen**, **OK** und dann **Speichern aus.**

Sichere ATP-Links sind jetzt konfiguriert. Lassen Sie bis zu 30 Minuten zu, bis Ihre Änderungen wirksam werden.

Wenn ein Benutzer eine E-Mail mit Links empfängt, werden die Links überprüft. Wenn die Links als sicher eingestuft werden, können sie angeklickt werden. Wenn sich der Link jedoch in der Blockierten Liste befindet, wird benutzern eine Meldung angezeigt, dass sie blockiert wurde.