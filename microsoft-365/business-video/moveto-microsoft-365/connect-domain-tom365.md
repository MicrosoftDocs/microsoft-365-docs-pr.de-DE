---
title: Verbinden Ihrer Domäne zu Microsoft 365
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
- okr_smb
monikerRange: o365-worldwide
search.appverid:
- BCS160
- MET150
- MOE150
description: Erfahren Sie, wie Sie Ihre Domäne mit Microsoft 365 verbinden.
ms.openlocfilehash: 1bec66a43026321ddf1979c73902a533bee3a07b
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/22/2021
ms.locfileid: "49925110"
---
# <a name="connect-your-domain-to-microsoft-365-for-business"></a>Verbinden Ihrer Domäne mit Microsoft 365 Business

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4LFpy?autoplay=false]

Nachdem Sie Microsoft 365 eingerichtet und Ihre E-Mail-Daten aus Google Workspace verschoben haben, können Sie Ihre Domäne mit Microsoft 365 verbinden. 

Zuerst müssen Sie vorhandene DNS-Einträge aus Google löschen, dann können wir neue DNS-Einträge aus Microsoft 365 hinzufügen.

## <a name="try-it"></a>Probieren Sie es aus!

1. Melden Sie sich bei Ihrer Google Workspace-Verwaltungskonsole [unter admin.google.com](https://admin.google.com).
1. Select **Domains**, **Manage domains**, View **details**, **Manage domain**, then **DNS** in the left nav.
1. Scrollen Sie nach unten zu **synthetischen Datensätzen,** öffnen **Sie Google Workspace,** wählen **Sie "Löschen"** und **dann** erneut "Löschen" aus.
1. Scrollen Sie nach unten zu **benutzerdefinierten** Ressourceneinträgen, und löschen Sie alle vorhandenen DNS-Einträge, die angezeigt werden, einschließlich aller, die Sie möglicherweise zuvor für Microsoft 365 erstellt haben.
1. Wechseln Sie zum [Microsoft 365 Admin Center.](https://admin.microsoft.com)
1. In the left nav, choose, **Show all**, **Settings**, **Domains**.
1. Wählen Sie dann Ihre Standarddomäne aus.
1. Select **Continue setup**, then, to connect your domain, choose  **Continue**.
1. Scrollen Sie nach unten, um die DNS-Einträge, die nach Google kopiert werden müssen, zu sehen.
1. Öffnen **Sie MX-Einträge,** und kopieren Sie den Eintrag unter "Verweist auf **Adresse"** oder "Wert".
1. Kehren Sie zu Google zurück, und öffnen Sie im Abschnitt **"Benutzerdefinierte Ressourceneinträge"** das Eintragstypdropdown, und wählen Sie **MX aus.**
1. Fügen Sie **in das Feld "Daten"** den kopierten Datensatz ein.
1. Wählen Sie dann **Hinzufügen** aus.
1. Wiederholen Sie den Vorgang für CNAME- und TXT-Einträge, und fügen Sie die Werte auf der Google #A0 hinzu.
1. Kehren Sie zum Microsoft 365 Admin Center zurück, und wählen Sie **"Weiter" aus.**

    Ihre Domäneneinrichtung ist abgeschlossen.