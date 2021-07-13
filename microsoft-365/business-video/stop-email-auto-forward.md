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
- AdminTemplateSet
monikerRange: o365-worldwide
search.appverid:
- BCS160
- MET150
- MOE150
description: Erfahren Sie, wie Sie die automatische Weiterleitung von E-Mails beenden, indem Sie eine Nachrichtenflussregel erstellen, um den Diebstahl proprietärer Informationen zu vermeiden.
ms.openlocfilehash: 23b1afa7a851c0b00fb9fca574ca0bb32057ea42
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/12/2021
ms.locfileid: "53394797"
---
# <a name="stop-email-auto-forward"></a>Automatische Weiterleitung von E-Mails beenden

## <a name="watch-stop-auto-forwarding-emails"></a>Überwachung: Beenden der automatischen Weiterleitung von E-Mails

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE2W6kS?autoplay=false]

Wenn ein Hacker Zugriff auf das Postfach eines Benutzers erhält, kann er die E-Mails des Benutzers automatisch an eine externe Adresse weiterleiten und proprietäre Informationen stehlen. Sie können dies beenden, indem Sie eine Nachrichtenflussregel erstellen.

## <a name="try-it"></a>Probieren Sie es aus!

1. Wählen Sie im Microsoft 365 Admin Center **Exchange**, **Nachrichtenfluss** und auf der Registerkarte **"Regeln"** das Pluszeichen aus, und wählen Sie **"Neue Regel erstellen"** aus.
1. Wählen Sie **weitere Optionen aus.** Benennen Sie die neue Regel.
1. Öffnen Sie dann die Dropdownliste, um **diese Regel anzuwenden, wenn**, wählen Sie den **Absender** aus und ist dann **extern intern**.
1. Wählen Sie **"Innerhalb der Organisation"** und dann **"OK"** aus.
1. Wählen Sie **Bedingung hinzufügen,** öffnen Sie die Dropdownliste, wählen Sie **Die Nachrichteneigenschaften** aus, und schließen Sie dann **den Nachrichtentyp ein.**
1. Öffnen Sie die Dropdownliste **"Nachrichtentyp auswählen",** wählen Sie **"Automatisch weiterleiten"** und dann **"OK"** aus.
1. Öffnen Sie die Dropdownliste **"Do the following",** wählen Sie **"Nachricht blockieren"** aus, weisen Sie die Nachricht dann **zurück, und fügen Sie eine Erklärung ein.**
1. Geben Sie den Nachrichtentext für Ihre Erklärung ein, und wählen Sie dann **OK** aus.
1. Scrollen Sie nach unten, und wählen Sie **Speichern** aus.

    Ihre Regel wurde erstellt, und Hacker können Nachrichten nicht mehr automatisch weiterleiten.

## <a name="related-content"></a>Verwandte Inhalte

[Hinzufügen eines weiteren E-Mail-Alias für einen Benutzer](../admin/email/add-another-email-alias-for-a-user.md) (Artikel)\
[Konfigurieren der E-Mail-Weiterleitung in Microsoft 365](../admin/email/configure-email-forwarding.md) (Artikel)\
[Suchen und Beheben von Problemen bei der E-Mail-Zustellung als Office 365 für Den Unternehmensadministrator](/exchange/troubleshoot/email-delivery/email-delivery-issues) (Artikel)