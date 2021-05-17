---
title: Hinzufügen Ihrer Google Workspace-Domäne
f1.keywords:
- NOCSH
ms.author: twerner
author: twernermsft
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
description: Erfahren Sie, wie Sie Ihre Domäne von Google Workspace in Microsoft 365 verschieben.
ms.openlocfilehash: 814e714527467bb6e7008ea141989f3117ddcdd8
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/02/2021
ms.locfileid: "51578771"
---
# <a name="add-your-google-workspace-domain-to-microsoft-365"></a>Hinzufügen Ihrer Google Workspace-Domäne zu Microsoft 365

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4LWKT?autoplay=false]

Fügen Sie Ihre Google Workspace-Domäne Microsoft 365 Business hinzu, damit Sie Ihre geschäftliche E-Mail-Adresse weiterhin verwenden können.

## <a name="try-it"></a>Probieren Sie es aus!

1. Wechseln Sie zum [Microsoft 365 Admin Center](https://admin.microsoft.com).
1. Wählen Sie im Microsoft 365 Admin Center im linken Navigations navi die Option **Alle** anzeigen, **Einstellungen** und dann **Domänen aus.**
1. Wählen **Sie Domäne hinzufügen** aus, geben Sie Ihren Domänennamen ein, und wählen Sie dann Diese Domäne verwenden **aus.** 
1. Wählen Sie, **Fügen Sie den Domänen DNS-Einträge einen TXT-Eintrag hinzu,** wählen Sie **Weiter** aus, und kopieren Sie den TXT-Wert. 
1. Wechseln Sie zurück zur [Google Admin Console,](https://admin.google.com)wählen Sie **Domänen** **,** Domänen verwalten , **Details anzeigen**, **Domäne** verwalten, **DNS**, und scrollen Sie dann nach unten zu **Benutzerdefinierte Ressourceneinträge**. 
1. Öffnen Sie die Dropdownliste Datensatztyp, wählen Sie **TXT** aus, fügen Sie den kopierten TXT-Wert ein, und wählen Sie **dann Hinzufügen aus.** 

    Das Update dauert in der Regel innerhalb weniger Minuten, kann jedoch bis zu 48 Stunden dauern. 
1. Kehren Sie zum Microsoft 365 Admin Center zurück, wählen **Sie Überprüfen** und dann **Schließen aus.** 
1. Wenn Sie Ihre Domäne als primäre E-Mail für Ihre Benutzer festlegen möchten, wählen Sie im linken Navigations navi die Option **Benutzer**  >  **Aktive Benutzer aus.** 
1. Wählen Sie einen Benutzer aus, wählen Sie **Benutzername und** E-Mail verwalten, **Bearbeiten** aus, wählen Sie Ihre Domäne aus der Dropdownliste aus, und wählen Sie dann **Fertig** und Änderungen **speichern aus.** 
1. Wiederholen Sie diesen Vorgang für jeden Benutzer. 

    Wenn Sie fertig sind, können Sie Office Apps installieren und Ihre E-Mail- und Kalenderelemente zu Microsoft 365. 