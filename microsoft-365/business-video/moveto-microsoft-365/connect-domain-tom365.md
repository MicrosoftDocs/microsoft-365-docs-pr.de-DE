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
description: Erfahren Sie, wie Sie Ihre Domäne mit Microsoft 365.
ms.openlocfilehash: 1bec66a43026321ddf1979c73902a533bee3a07b
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/22/2021
ms.locfileid: "49925110"
---
# <a name="connect-your-domain-to-microsoft-365-for-business"></a>Verbinden Ihrer Domäne für Microsoft 365 Unternehmen

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4LFpy?autoplay=false]

Nachdem Sie ihre Microsoft 365 eingerichtet und Ihre E-Mail-Daten aus Google Workspace verschoben haben, können Sie Ihre Domäne mit Microsoft 365. 

Zuerst müssen Sie vorhandene DNS-Einträge aus Google löschen, dann können wir neue DNS-Einträge aus Microsoft 365.

## <a name="try-it"></a>Probieren Sie es aus!

1. Melden Sie sich bei Ihrer Google Workspace Admin Console [unter admin.google.com](https://admin.google.com).
1. Wählen **Sie Domänen**, Domänen **verwalten**, **Details anzeigen,** Domäne **verwalten** und **dann DNS** im linken Navigations navi aus.
1. Scrollen Sie nach unten zu **Synthetische Datensätze,** öffnen **Sie Google Workspace,** wählen **Sie Löschen** und dann **erneut** löschen aus.
1. Scrollen Sie nach unten zu **Benutzerdefinierte** Ressourceneinträge, und löschen Sie alle vorhandenen DNS-Einträge, einschließlich aller vorhandenen, die Sie möglicherweise zuvor für die Microsoft 365.
1. Wechseln Sie zum [Microsoft 365 Admin Center](https://admin.microsoft.com).
1. Wählen Sie im linken Navigations navi, **Show all**, **Einstellungen**, **Domains aus.**
1. Wählen Sie dann Ihre Standarddomäne aus.
1. Wählen **Sie Setup fortsetzen** aus, und wählen Sie dann Weiter aus, um eine Verbindung zu Ihrer Domäne **herzustellen.**
1. Scrollen Sie nach unten, um die DNS-Einträge zu sehen, die nach Google kopiert werden müssen.
1. Öffnen **Sie MX Records**, und kopieren Sie unter Points to address or **value** den Datensatz.
1. Kehren Sie zu Google  zurück, und öffnen Sie im Abschnitt Benutzerdefinierte Ressourceneinträge das Dropdownmenü datensatztyp, und wählen Sie **MX aus.**
1. Fügen Sie **im Feld Daten** den kopierten Datensatz ein.
1. Wählen Sie dann **Hinzufügen** aus.
1. Wiederholen Sie den Vorgang für CNAME- und #A0 und fügen Sie die Werte auf der Google #A1 hinzu.
1. Kehren Sie zum Microsoft 365 Admin Center zurück, und wählen Sie **Weiter aus.**

    Die Domäneneinrichtung ist abgeschlossen.