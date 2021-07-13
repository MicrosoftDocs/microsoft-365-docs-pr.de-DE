---
title: Verwenden eines QR-Codes zum Anmelden bei den Outlook mobilen Apps
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
- AdminTemplateSet
description: Erfahren Sie, wie Sie mithilfe eines QR-Codes Outlook Mobilgerät authentifizieren und herunterladen können.
ms.openlocfilehash: c13fbeabd320c64925165ba16797d5a3471961ad
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/12/2021
ms.locfileid: "53391339"
---
# <a name="use-a-qr-code-to-sign-in-to-the-outlook-mobile-apps"></a>Verwenden eines QR-Codes zum Anmelden bei den Outlook mobilen Apps

> [!IMPORTANT]
> Dieses Feature ist nur für Organisationen verfügbar, die targeted Release im Microsoft 365 Admin Center aktiviert haben. Informationen zur Aktivierung der gezielten Version und weitere Informationen zur Funktionsweise finden Sie unter ["Einrichten der Standard- oder Targeted Release-Optionen".](release-options-in-office-365.md) Wir werden in den kommenden Wochen über die öffentliche Vorschau auf weitere Organisationen erweitern. Die öffentliche Vorschau bietet frühzeitigen Zugriff auf Microsoft 365 Features.

Als Microsoft 365-Administrator können Sie Ihren Benutzern die Anmeldung bei Outlook für Android oder die iOS-App auf ihren mobilen Geräten ermöglichen, ohne ihren Benutzernamen und ihr Kennwort eingeben zu müssen. Durch Scannen eines QR-Codes können sich Benutzer sicher authentifizieren und sich bei Outlook Mobilen anmelden.

In Outlook im Web oder anderen Desktop-Outlook-Anwendungen werden Benutzern möglicherweise Benachrichtigungen angezeigt, die sie darüber informieren, dass sie Outlook auf ihrem mobilen Gerät verwenden können. Diese Benachrichtigungen können vom Administrator mit Exchange PowerShell verwaltet werden. Wenn Benutzer sich selbst eine SMS senden, um die App auf ihrem mobilen Gerät herunterzuladen, wird ein QR-Code auf ihrem Computer angezeigt. Sie können den QR-Code scannen, um sich bei Outlook auf ihrem Smartphone oder Tablet anzumelden. Dieser QR-Code ist ein kurzlebiges Token, das nur einmal eingelöst werden kann.

> [!NOTE]
> In einigen Fällen müssen sich Die Benutzer auf ihrem Computer erneut authentifizieren, um den QR-Code zu generieren.

## <a name="use-exchange-powershell"></a>Verwenden von Exchange PowerShell

Diese Funktion ist standardmäßig aktiviert. Führen Sie die folgenden Schritte aus, um dieses Feature zu deaktivieren.

1. [Verbinden zu Exchange PowerShell.](/powershell/exchange/connect-to-exchange-online-powershell)
2. Mithilfe von PowerShell können Sie die Benachrichtigungen deaktivieren, die Ihre Benutzer über die Outlook mobilen Apps informieren. Dadurch wird auch verhindert, dass der QR-Code-Anmeldefluss angezeigt wird.

```powershell
Set-OrganizationConfig -MobileAppEducationEnabled <Boolean>
```

## <a name="related-content"></a>Verwandte Inhalte

[Einrichten der Standard- oder Targeted Release-Optionen](release-options-in-office-365.md) (Artikel)\
[Set-OrganizationConfig](/powershell/module/exchange/set-organizationconfig) (Artikel)