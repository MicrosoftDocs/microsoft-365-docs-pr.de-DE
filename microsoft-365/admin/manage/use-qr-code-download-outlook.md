---
title: Verwenden eines QR-Codes zum Anmelden bei Outlook mobilen Apps
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
description: Erfahren Sie, wie Sie einen QR-Code zum Authentifizieren und Herunterladen von Outlook verwenden.
ms.openlocfilehash: 2c1853a6ea1dd1a5d2ad30b975d1dbd23b942040
ms.sourcegitcommit: 17f0aada83627d9defa0acf4db03a2d58e46842f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/24/2021
ms.locfileid: "52635998"
---
# <a name="use-a-qr-code-to-sign-in-to-the-outlook-mobile-apps"></a>Verwenden eines QR-Codes zum Anmelden bei Outlook mobilen Apps

> [!IMPORTANT]
> Dieses Feature ist nur für Organisationen verfügbar, die die gezielte Veröffentlichung im Microsoft 365 aktiviert haben. Weitere Informationen zur Funktionsweise der gezielten Veröffentlichung finden Sie unter [Set up the Standard or Targeted release options](release-options-in-office-365.md). Wir werden in den kommenden Wochen über die öffentliche Vorschau auf weitere Organisationen erweitern. Die öffentliche Vorschau bietet frühzeitigen Zugriff auf Microsoft 365 Features.

Als Microsoft 365 können Sie Ihren Benutzern die Anmeldung bei Outlook für Android oder iOS-App auf ihren mobilen Geräten ermöglichen, ohne ihren Benutzernamen und ihr Kennwort eingeben zu müssen. Durch Das Scannen eines QR-Codes können Benutzer sich sicher authentifizieren und sich bei Outlook anmelden.

In Outlook im Web oder in anderen Desktop-Outlook können Benutzern Benachrichtigungen angezeigt werden, die sie darüber informieren, dass sie Outlook auf ihrem mobilen Gerät verwenden können. Diese Benachrichtigungen können vom Administrator mithilfe von powershell Exchange verwaltet werden. Wenn Benutzer sich selbst eine SMS senden, um die App auf ihrem mobilen Gerät herunterzuladen, wird auf ihrem Computer ein QR-Code angezeigt. Sie können den QR-Code überprüfen, um sich Outlook Smartphone oder Tablet zu melden. Dieser QR-Code ist ein kurzlebiges Token, das nur einmal eingelöst werden kann.

> [!NOTE]
> In einigen Fällen müssen sich Ihre Benutzer erneut auf ihrem Computer authentifizieren, um den QR-Code zu generieren.

## <a name="use-exchange-powershell"></a>Verwenden Exchange PowerShell

Diese Funktion ist standardmäßig aktiviert. Führen Sie die folgenden Schritte aus, um dieses Feature zu deaktivieren.

1. [Verbinden zum Exchange PowerShell .](/powershell/exchange/connect-to-exchange-online-powershell?view=exchange-ps)
2. Mit PowerShell können Sie die Benachrichtigungen deaktivieren, die Ihre Benutzer über die Outlook informieren. Dadurch wird auch verhindert, dass der QR-Code-Anmeldefluss angezeigt wird.

```powershell
Set-OrganizationConfig -MobileAppEducationEnabled <Boolean>
```

## <a name="related-content"></a>Verwandte Inhalte

[Einrichten der Standard- oder Zielversionsoptionen](release-options-in-office-365.md) (Artikel)\
[Set-OrganizationConfig](/powershell/module/exchange/set-organizationconfig?view=exchange-ps) (Artikel)