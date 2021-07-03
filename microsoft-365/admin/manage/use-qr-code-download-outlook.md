---
title: Verwenden sie einen QR-Code, um sich bei den Outlook mobilen Apps anzumelden.
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
description: Erfahren Sie, wie Sie mithilfe eines QR-Codes Outlook Mobilgerät authentifizieren und herunterladen können.
ms.openlocfilehash: a403fbbed90229300e707653062c552104c47d97
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/03/2021
ms.locfileid: "53286705"
---
# <a name="use-a-qr-code-to-sign-in-to-the-outlook-mobile-apps"></a>Verwenden sie einen QR-Code, um sich bei den Outlook mobilen Apps anzumelden.

> [!IMPORTANT]
> Dieses Feature ist nur für Organisationen verfügbar, die targeted Release im Microsoft 365 Admin Center aktiviert haben. Informationen zur Aktivierung der gezielten Version und weitere Informationen zur Funktionsweise finden Sie unter ["Einrichten der Standard- oder Targeted Release-Optionen".](release-options-in-office-365.md) Wir werden in den kommenden Wochen über die öffentliche Vorschau auf weitere Organisationen erweitern. Die öffentliche Vorschau bietet frühzeitigen Zugriff auf Microsoft 365 Features.

Als Microsoft 365-Administrator können Sie Ihren Benutzern die Anmeldung bei Outlook für Android oder die iOS-App auf ihren mobilen Geräten ermöglichen, ohne ihren Benutzernamen und ihr Kennwort eingeben zu müssen. Durch Scannen eines QR-Codes können Sich Benutzer sicher authentifizieren und sich bei Outlook Mobilgerät anmelden.

In Outlook im Web oder anderen Desktop-Outlook-Anwendungen werden Benutzern möglicherweise Benachrichtigungen angezeigt, die sie darüber informieren, dass sie Outlook auf ihrem mobilen Gerät verwenden können. Diese Benachrichtigungen können vom Administrator mit Exchange PowerShell verwaltet werden. Wenn Benutzer sich selbst eine SMS senden, um die App auf ihrem mobilen Gerät herunterzuladen, wird ein QR-Code auf ihrem Computer angezeigt. Sie können den QR-Code scannen, um sich auf ihrem Smartphone oder Tablet bei Outlook anzumelden. Dieser QR-Code ist ein kurzlebiges Token, das nur einmal eingelöst werden kann.

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