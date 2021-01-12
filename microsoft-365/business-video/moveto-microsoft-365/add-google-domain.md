---
title: Hinzufügen Ihrer Google Workspace-Domäne
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
description: Erfahren Sie, wie Sie Ihre Domäne von Google Workspace zu Microsoft 365 Business verschieben.
ms.openlocfilehash: 1abc05867147d2b52e26804918e8247053b5e1d5
ms.sourcegitcommit: 9833f95ab6ab95aea20d68a277246dca2223f93d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/11/2021
ms.locfileid: "49794675"
---
# <a name="add-your-google-workspace-domain-to-microsoft-365"></a>Hinzufügen Ihrer Google Workspace-Domäne zu Microsoft 365

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4LWKT?autoplay=false]

Fügen Sie Ihre Google Workspace-Domäne zu Microsoft 365 Business hinzu, damit Sie Ihre geschäftliche E-Mail-Adresse weiterhin verwenden können.

## <a name="try-it"></a>Probieren Sie es aus!

1. Wechseln Sie zum [Microsoft 365 Admin Center.](https://admin.microsoft.com)
1. Wählen Sie im Microsoft 365 Admin Center im linken Navigationsbereich **"Alle** anzeigen", **"Einstellungen"** und dann **"Domänen" aus.**
1. Wählen **Sie "Domäne hinzufügen"** aus, geben Sie Ihren Domänennamen ein, und wählen **Sie dann "Diese Domäne verwenden" aus.** 
1. Choose, **Add a TXT record to the domains DNS records,** select **Continue**, and copy the TXT value. 
1. Go back to the [Google Admin Console](https://admin.google.com), choose **Domains**, **Manage domains**, View **Details**, **Manage domain**, **DNS**, and then scroll down to Custom **resource records**. 
1. Öffnen Sie die Dropdownliste für den Eintragstyp, wählen **Sie TXT** aus, fügen Sie den kopierten TXT-Wert ein, und wählen Sie dann **"Hinzufügen" aus.** 

    Das Update dauert in der Regel innerhalb weniger Minuten, kann aber bis zu 48 Stunden dauern. 
1. Kehren Sie zum Microsoft 365 Admin Center zurück, wählen **Sie "Überprüfen"** und dann **"Schließen" aus.** 
1. Wenn Sie Ihre Domäne als primäre E-Mail-Adresse für Ihre Benutzer festlegen möchten, wählen Sie im linken Navigationsbereich **"Aktive**  >  **Benutzer" aus.** 
1. Choose a user, select **Manage username and email**, **Edit**, select your domain from the dropdown, then select **Done** and **Save changes**. 
1. Wiederholen Sie diesen Vorgang für jeden Benutzer. 

    Wenn Sie fertig sind, können Sie die Office-Apps installieren und Ihre E-Mail- und Kalenderelemente zu Microsoft 365 migrieren. 