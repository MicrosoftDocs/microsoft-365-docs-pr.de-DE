---
title: Konfigurieren von S/MIME-Einstellungen in Exchange Online für Outlook im Internet
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: c7dee22c-9b5b-425c-91a9-d093204ff84e
ms.collection:
- M365-security-compliance
description: Eine kurze Beschreibung, was Exchange Online Administratoren tun müssen, um die S/MIME-Einstellungen in Outlook im Internet in Exchange Online anzuzeigen und zu konfigurieren.
ms.openlocfilehash: 408a8f7aed800175e7bae7af73d77f340359c17d
ms.sourcegitcommit: 70e920f76526f47fc849df615de4569e0ac2f4be
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/07/2019
ms.locfileid: "38032440"
---
# <a name="configure-smime-settings-in-exchange-online-for-outlook-on-the-web"></a>Konfigurieren von S/MIME-Einstellungen in Exchange Online für Outlook im Internet

Als Administrator für Exchange Online können Sie Outlook im Internet (früher als Outlook Web App bezeichnet) einrichten, um das Senden und empfangen von S/MIME-geschützten Nachrichten zu ermöglichen. Verwenden Sie die Cmdlets **Get-SmimeConfig** und **SmimeConfig** , um dieses Feature in Exchange Online PowerShell anzuzeigen und zu verwalten. Wie Sie eine Verbindung mit Exchange Online PowerShell herstellen, finden Sie unter [Herstellen einer Verbindung mit Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554).

Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Get-SmimeConfig](https://technet.microsoft.com/library/4b29fa89-0840-4fe9-8885-019fcef2e02b.aspx) und [Sets-SmimeConfig](https://technet.microsoft.com/library/de357ce0-8143-4c36-8032-026292fc63f0.aspx).

## <a name="considerations-for-chrome"></a>Überlegungen für Chrome

Um s/MIME in Outlook im Internet im Webbrowser von Google Chrome zu verwenden, müssen Sie (oder ein anderer Administrator) die Chrom Richtlinie mit dem Namen **ExtensionInstallForcelist** festlegen und konfigurieren, um die Microsoft S/MIME-Erweiterung in Chrome zu installieren. Der Richtlinienwert ist `maafgiompdekodanheihhgilkjchcakm;https://outlook.office.com/owa/SmimeCrxUpdate.ashx`. Beachten Sie, dass die Anwendung dieser Richtlinie Computer mit Domänenbeitritt erfordert, sodass die Verwendung von S/MIME in Chrome effektiv mit der Domäne verbundener Computer erforderlich ist.

Ausführliche Informationen zur **ExtensionInstallForcelist** -Richtlinie finden Sie unter [ExtensionInstallForcelist](https://dev.chromium.org/administrators/policy-list-3#ExtensionInstallForcelist).

Dieser Schritt ist eine Voraussetzung für die Verwendung von Chrome; das von Benutzern installierte S/MIME-Steuerelement wird nicht ersetzt. Benutzer werden aufgefordert, das s/MIME-Steuerelement in Outlook im Internet während der ersten Verwendung von s/MIME herunterzuladen und zu installieren. Oder können Benutzer proaktiv zu **S/MIME** in Ihren Outlook im Webeinstellungen wechseln, um den Download-Link für das Steuerelement abzurufen.

## <a name="for-more-information"></a>Weitere Informationen

[S/MIME für die Nachrichtensignierung und -verschlüsselung](s-mime-for-message-signing-and-encryption.md)
