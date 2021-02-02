---
title: Verwenden eines QR-Codes zum Anmelden bei den mobilen Outlook-Apps
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
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
description: Erfahren Sie, wie Sie einen QR-Code verwenden, um Outlook Mobile zu authentifizieren und herunterzuladen.
ms.openlocfilehash: 2d62a49b93fa7bd5f2d747525de7244e8014e6a7
ms.sourcegitcommit: b8e9b2ecdc4927b67088c5fffb1585424c66fb10
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2021
ms.locfileid: "50050774"
---
# <a name="use-a-qr-code-to-sign-in-to-the-outlook-mobile-apps"></a>Verwenden eines QR-Codes zum Anmelden bei den mobilen Outlook-Apps

> [!IMPORTANT]
> Dieses Microsoft 365-Feature befindet sich in der öffentlichen Vorschau. Die öffentliche Vorschau bietet frühzeitigen Zugriff auf Microsoft 365-Features.

Als Microsoft 365-Administrator können Sie Ihren Benutzern ermöglichen, sich bei Outlook für Android oder einer iOS-App auf ihren mobilen Geräten ohne Eingabe ihres Benutzernamens und Kennworts anmelden zu müssen. Durch das Scannen eines QR-Codes können Benutzer sich sicher authentifizieren und sich bei Outlook Mobile anmelden.

In Outlook im Web oder anderen Desktop-Outlook-Anwendungen werden Benutzern möglicherweise Benachrichtigungen angezeigt, die sie darüber informieren, dass sie Outlook auf ihrem mobilen Gerät verwenden können. Diese Benachrichtigungen können vom Administrator mithilfe von Exchange Powershell verwaltet werden. Wenn sich Benutzer entscheiden, sich selbst eine SMS zu senden, um die App auf ihr mobiles Gerät herunterzuladen, wird auf ihrem Computer ein QR-Code angezeigt. Sie können den QR-Code überprüfen, um sich auf ihrem Smartphone oder Tablet bei Outlook zu anmelden. Dieser QR-Code ist ein kurzlebiges Token, das nur einmal eingelöst werden kann.

> [!NOTE]
> In einigen Fällen müssen sich Die Benutzer auf ihrem Computer erneut authentifizieren, um den QR-Code zu generieren.

## <a name="use-exchange-powershell"></a>Verwenden von Exchange PowerShell

Diese Erfahrung ist standardmäßig aktiviert. Führen Sie die folgenden Schritte aus, um dieses Feature zu deaktivieren.

1. [Herstellen einer Verbindung mit Exchange PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell?view=exchange-ps).
2. Mithilfe von PowerShell können Sie die Benachrichtigungen deaktivieren, die Ihre Benutzer über die mobilen Outlook-Apps informieren. Dadurch wird auch verhindert, dass der Anmeldefluss des QR-Codes angezeigt wird.

```powershell
Set-Organization -MobileAppEducationEnabled <Boolean>
```

Verwandte Themen

[Set-OrganizationConfig](https://docs.microsoft.com/powershell/module/exchange/set-organizationconfig?view=exchange-ps)