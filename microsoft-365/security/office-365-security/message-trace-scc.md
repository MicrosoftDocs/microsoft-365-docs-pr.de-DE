---
title: Nachrichtenablaufverfolgung im Microsoft 365 Defender-Portal
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
localization_priority: Normal
ms.assetid: 3e64f99d-ac33-4aba-91c5-9cb4ca476803
ms.custom:
- seo-marvel-apr2020
description: Administratoren können den Link zur Nachrichtenablaufverfolgung im Microsoft 365 Defender-Portal verwenden, um herauszufinden, was mit Nachrichten passiert ist.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: f7b6f7b12086e46c6ad93b60e8c510ea533815a1
ms.sourcegitcommit: ebb1c3b4d94058a58344317beb9475c8a2eae9a7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/24/2021
ms.locfileid: "53108127"
---
# <a name="message-trace-in-the-microsoft-365-defender-portal"></a>Nachrichtenablaufverfolgung im Microsoft 365 Defender-Portal

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gilt für**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender für Office 365 Plan 1 und Plan 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Die Nachrichtenablaufverfolgung im Microsoft 365 Defender Portal folgt E-Mail-Nachrichten, während sie ihre Exchange Online Organisation durchlaufen. Sie können ermitteln, ob eine Nachricht empfangen, abgelehnt, zurückgestellt oder vom Dienst übermittelt wurde. Außerdem werden die Aktionen der Nachricht gezeigt, bevor diese ihren finalen Status erreicht hat.

Sie können die Informationen aus der Nachrichtenablaufverfolgung verwenden, um Benutzerfragen zu den Nachrichten effizient zu beantworten, Probleme mit dem Nachrichtenfluss zu beheben und Richtlinienänderungen zu überprüfen.

> [!NOTE]
> Die Nachrichtenablaufverfolgung im Microsoft 365 Defender-Portal ist nur eine Übergabe an die Nachrichtenablaufverfolgung im Exchange Admin Center. Weitere Informationen finden Sie unter [Nachrichtenablaufverfolgung im modernen Exchange Admin Center.](/exchange/monitoring/trace-an-email-message/message-trace-modern-eac)

## <a name="what-do-you-need-to-know-before-you-begin"></a>Was sollten Sie wissen, bevor Sie beginnen?

- Sie müssen Mitglied der **Rollengruppen "Organisationsverwaltung",** **"Complianceverwaltung"** oder **"Helpdesk"** in **Exchange Online** sein, um die Nachrichtenablaufverfolgung zu verwenden. Weitere Informationen finden Sie unter [Berechtigungen in Exchange Online](/exchange/permissions-exo/permissions-exo).

  **Hinweis:** Die Mitgliedschaft in der entsprechenden Azure Active Directory-Rolle im Microsoft 365 Admin Center gewährt Benutzern die erforderlichen Berechtigungen _und_ Berechtigungen für andere Features in Microsoft 365. Weitere Informationen finden Sie unter [Informationen zu Administratorrollen](../../admin/add-users/about-admin-roles.md).

- Die maximale Anzahl von Nachrichten, die in den Ergebnissen einer Nachrichtenablaufverfolgung angezeigt werden, hängt vom ausgewählten Berichtstyp ab (Details finden Sie im Abschnitt ["Berichtstyp auswählen").](/exchange/monitoring/trace-an-email-message/message-trace-modern-eac#choose-report-type) Das Cmdlet ["Get-HistoricalSearch"](/powershell/module/exchange/get-historicalsearch) in Exchange Online PowerShell oder der eigenständigen EOP-PowerShell gibt alle Nachrichten in den Ergebnissen zurück.

## <a name="open-message-trace"></a>Öffnen der Nachrichtenablaufverfolgung

Wechseln Sie im Microsoft 365 Defender Portal ( <https://security.microsoft.com> ) zu **E-Mail & Zusammenarbeit** Exchange \> **Nachrichtenablaufverfolgung.** Oder verwenden Sie , um direkt zur Nachrichtenablaufverfolgungsseite zu <https://admin.exchange.microsoft.com/#/messagetrace> wechseln.

An diesem Punkt wird die Nachrichtenablaufverfolgung im EAC geöffnet. Weitere Informationen finden Sie unter [Nachrichtenablaufverfolgung im modernen Exchange Admin Center.](/exchange/monitoring/trace-an-email-message/message-trace-modern-eac)
