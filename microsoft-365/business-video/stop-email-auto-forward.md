---
title: Automatische Weiterleitung von e-Mails beenden
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
description: Hier erfahren Sie, wie Sie e-Mails mit automatischer Weiterleitung beenden.
ms.openlocfilehash: 0683e133f6c261dc19cc098b13be298cd8086001
ms.sourcegitcommit: f231eece2927f0d01072fd092db1eab15525bbc2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/17/2020
ms.locfileid: "49702020"
---
# <a name="stop-email-auto-forward"></a>Beenden der automatischen e-Mail-Weiterleitung

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE2W6kS?autoplay=false]

Wenn ein Hacker Zugriff auf das Postfach eines Benutzers erhält, kann er die e-Mail des Benutzers automatisch an eine externe Adresse weiterleiten und proprietäre Informationen stehlen. Sie können dies beenden, indem Sie eine e-Mail-Fluss Regel erstellen.

## <a name="try-it"></a>Probieren Sie es aus!

1. Wählen Sie im Microsoft 365 Admin Center **Exchange**, **Nachrichtenfluss** aus, und wählen Sie auf der Registerkarte **Regeln** das Pluszeichen aus, und wählen Sie **neue Regel erstellen** aus.
1. Wählen Sie **Weitere Optionen** aus. Nennen Sie die neue Regel.
1. Öffnen Sie dann die Dropdownliste für **diese Regel anwenden, wenn** Sie **den Absender** auswählen und dann **Externe interne**.
1. Wählen Sie **innerhalb der Organisation** aus, und klicken Sie dann auf **OK**.
1. Wählen Sie **Bedingung hinzufügen** aus, öffnen Sie die Dropdownliste, wählen Sie **die Nachrichteneigenschaften** aus, und schließen Sie dann **den Nachrichtentyp ein**.
1. Öffnen Sie die Dropdownliste **Nachrichtentyp auswählen** , wählen Sie **automatisch weiterleiten** aus, und klicken Sie dann auf **OK**.
1. Öffnen Sie die Dropdownliste **gehen Sie wie folgt** vor, wählen Sie **Nachricht blockieren** aus, **und lehnen Sie die Nachricht ab, und fügen Sie eine Erläuterung hinzu**.
1. Geben Sie den Nachrichtentext für Ihre Erklärung ein, und wählen Sie dann **OK** aus.
1. Scrollen Sie nach unten, und wählen Sie **Speichern** aus.

    Ihre Regel wurde erstellt, und Hacker können keine Nachrichten mehr automatisch weiterleiten.