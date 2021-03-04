---
title: Automatische Weiterleitung von E-Mails beenden
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
description: Erfahren Sie, wie Sie die automatische Weiterleitung von E-Mails beenden.
ms.openlocfilehash: ca4383a3f9d64a123955ebe005d0fad5819d3a5d
ms.sourcegitcommit: 355bd51ab6a79d5c36a4e4f57df74ae6873eba19
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/04/2021
ms.locfileid: "50421799"
---
# <a name="stop-email-auto-forward"></a>Automatische Weiterleitung von E-Mails beenden

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE2W6kS?autoplay=false]

Wenn ein Hacker Zugriff auf das Postfach eines Benutzers erhält, kann er die E-Mails des Benutzers automatisch an eine externe Adresse weiterleiten und proprietäre Informationen stehlen. Sie können dies beenden, indem Sie eine Nachrichtenflussregel erstellen.

## <a name="try-it"></a>Probieren Sie es aus!

1. Wählen Sie im Microsoft 365 Admin Center Die  Option **Exchange,** Nachrichtenfluss und auf der Registerkarte Regeln das Pluszeichen aus, und wählen Sie **neue Regel erstellen aus.**
1. Wählen **Sie Weitere Optionen aus.** Nennen Sie Ihre neue Regel.
1. Öffnen Sie dann die Dropdownliste, um **diese Regel anzuwenden, wenn**, wählen Sie den **Absender** aus, und ist dann **extern intern**.
1. Wählen **Sie Innerhalb der Organisation** aus, und klicken Sie dann auf **OK**.
1. Wählen **Sie Bedingung hinzufügen** aus, öffnen Sie die Dropdownliste, wählen Sie **Nachrichteneigenschaften** aus, und schließen Sie **dann den Nachrichtentyp ein.**
1. Öffnen Sie **die Dropdownliste Nachrichtentyp** auswählen, wählen **Sie Automatisch weiterleiten** und dann OK **aus.**
1. Öffnen Sie **die Dropdownliste** Do the following, select **Block the message,** then **reject the message and include an explanation**.
1. Geben Sie den Nachrichtentext für Ihre Erläuterung ein, und wählen Sie dann **OK aus.**
1. Scrollen Sie nach unten, und wählen Sie **Speichern aus.**

    Ihre Regel wurde erstellt, und Hacker können Nachrichten nicht mehr automatisch weiterleiten.