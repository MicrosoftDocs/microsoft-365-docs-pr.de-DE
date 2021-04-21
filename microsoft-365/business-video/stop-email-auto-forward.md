---
title: Automatische Weiterleitung von E-Mails beenden
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
description: Erfahren Sie, wie Sie die automatische Weiterleitung von E-Mails beenden.
ms.openlocfilehash: f8bd599c7c8bca8d4789188acbcd3574b7473dcb
ms.sourcegitcommit: 13ce4b31303a1a21ca53700a54bcf8d91ad2f8c1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/20/2021
ms.locfileid: "51903682"
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

## <a name="related-content"></a>Verwandte Inhalte

Hinzufügen eines weiteren [E-Mail-Alias](https://docs.microsoft.com/microsoft-365/admin/email/add-another-email-alias-for-a-user) für einen Benutzer (Artikel) Konfigurieren der E-Mail-Weiterleitung [in Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/email/configure-email-forwarding) (Artikel) Suchen und Beheben von Problemen mit der E-Mail-Zustellung als [Office 365 Business Admin](https://docs.microsoft.com/exchange/troubleshoot/email-delivery/email-delivery-issues) (Artikel)