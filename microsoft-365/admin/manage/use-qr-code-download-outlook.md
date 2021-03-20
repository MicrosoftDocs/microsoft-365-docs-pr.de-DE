---
title: Verwenden eines QR-Codes zum Anmelden bei mobilen Outlook-Apps
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
description: Erfahren Sie, wie Sie einen QR-Code zum Authentifizieren und Herunterladen von Outlook mobile verwenden.
ms.openlocfilehash: bc8ab14d3c1c0621e84d0c95ad7448c6c50825d6
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50914966"
---
# <a name="use-a-qr-code-to-sign-in-to-the-outlook-mobile-apps"></a>Verwenden eines QR-Codes zum Anmelden bei mobilen Outlook-Apps

> [!IMPORTANT]
> Dieses Feature ist nur für Organisationen verfügbar, die die gezielte Veröffentlichung im Microsoft 365 Admin Center aktiviert haben. Weitere Informationen zur Funktionsweise der gezielten Veröffentlichung finden Sie unter [Set up the Standard or Targeted release options](release-options-in-office-365.md). Wir werden in den kommenden Wochen über die öffentliche Vorschau auf weitere Organisationen erweitern. Öffentliche Vorschau bietet frühzeitigen Zugriff auf Microsoft 365-Features.

Als Microsoft 365-Administrator können Sie Ihren Benutzern die Anmeldung bei Outlook für Android oder der iOS-App auf ihren mobilen Geräten ermöglichen, ohne ihren Benutzernamen und ihr Kennwort eingeben zu müssen. Durch Das Scannen eines QR-Codes können Benutzer sich sicher authentifizieren und sich bei Outlook mobile anmelden.

In Outlook im Web oder anderen Desktop-Outlook-Anwendungen werden Benutzern möglicherweise Benachrichtigungen angezeigt, die sie darüber informieren, dass sie Outlook auf ihrem mobilen Gerät verwenden können. Diese Benachrichtigungen können vom Administrator mithilfe von Exchange Powershell verwaltet werden. Wenn Benutzer sich selbst eine SMS senden möchten, um die App auf ihrem mobilen Gerät herunterzuladen, wird auf ihrem Computer ein QR-Code angezeigt. Sie können den QR-Code überprüfen, um sich auf ihrem Smartphone oder Tablet bei Outlook zu melden. Dieser QR-Code ist ein kurzlebiges Token, das nur einmal eingelöst werden kann.

> [!NOTE]
> In einigen Fällen müssen sich Ihre Benutzer erneut auf ihrem Computer authentifizieren, um den QR-Code zu generieren.

## <a name="use-exchange-powershell"></a>Verwenden von Exchange PowerShell

Diese Funktion ist standardmäßig aktiviert. Führen Sie die folgenden Schritte aus, um dieses Feature zu deaktivieren.

1. [Herstellen einer Verbindung mit Exchange PowerShell](/powershell/exchange/connect-to-exchange-online-powershell?view=exchange-ps).
2. Mit PowerShell können Sie die Benachrichtigungen deaktivieren, die Ihre Benutzer über die mobilen Outlook-Apps informieren. Dadurch wird auch verhindert, dass der Qr-Code-Anmeldefluss angezeigt wird.

```powershell
Set-OrganizationConfig -MobileAppEducationEnabled <Boolean>
```

Verwandte Themen

[Set-OrganizationConfig](/powershell/module/exchange/set-organizationconfig?view=exchange-ps)