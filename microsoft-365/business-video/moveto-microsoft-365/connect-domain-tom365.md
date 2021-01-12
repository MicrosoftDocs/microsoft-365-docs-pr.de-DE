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
monikerRange: o365-worldwide
search.appverid:
- BCS160
- MET150
- MOE150
description: Erfahren Sie, wie Sie Ihre Domäne mit Microsoft 365 verbinden.
ms.openlocfilehash: c7827b93b56560579b31bd2abb5a852467565103
ms.sourcegitcommit: 9833f95ab6ab95aea20d68a277246dca2223f93d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/11/2021
ms.locfileid: "49794642"
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
1. Wählen Sie im linken Navigations navig, **Alle anzeigen**, **Einstellungen**, **Domänen**.
1. Wählen Sie dann Ihre Standarddomäne aus.
1. Select **Continue setup**, then, to connect your domain, choose  **Continue**.
1. Scrollen Sie nach unten, um die DNS-Einträge, die nach Google kopiert werden müssen, zu sehen.
1. Öffnen **Sie MX-Einträge,** und kopieren Sie den Eintrag unter "Verweist auf **Adresse"** oder "Wert".
1. Kehren Sie zu Google zurück, und öffnen Sie im Abschnitt **"Benutzerdefinierte** Ressourceneinträge" das Eintragstypdropdown, und wählen Sie **MX aus.**
1. Fügen Sie **in das Feld "Daten"** den kopierten Datensatz ein.
1. Wählen Sie dann **Hinzufügen** aus.
1. Wiederholen Sie den Vorgang für CNAME- und TXT-Einträge, und fügen Sie die Werte auf der Google #A0 hinzu.
1. Kehren Sie zum Microsoft 365 Admin Center zurück, und wählen Sie **"Weiter" aus.**

    Ihre Domäneneinrichtung ist abgeschlossen.