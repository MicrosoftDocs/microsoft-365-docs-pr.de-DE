---
title: Entfernen von Lizenzen aus Ihrem Office 365 Business-Abonnement
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- commerce
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
- GEA150
ms.assetid: 9c64d127-e2dd-4ecc-81f5-2f87e5a74803
description: Erfahren Sie, wie Sie eine Lizenz aus Ihrem Office 365 Business-Abonnement entfernen, wenn die Lizenz bereits einer Person zugewiesen ist.
ms.openlocfilehash: d1af1b5696d359daf6578e090180b79587952106
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/24/2020
ms.locfileid: "42242326"
---
# <a name="remove-licenses-from-your-office-365-for-business-subscription"></a>Entfernen von Lizenzen aus Ihrem Office 365 Business-Abonnement

Sie können eine Lizenz nicht aus einem Abonnement entfernen, wenn Sie einem Benutzer zugewiesen ist. Wenn Sie eine Lizenz entfernen möchten, die derzeit einer Person zugewiesen ist, müssen Sie [-Lizenzen-von-users entfernen](../../admin/manage/remove-licenses-from-users.md), bevor Sie die Lizenz aus dem Abonnement entfernen können.

::: moniker range="o365-worldwide"

> [!NOTE]
> Wenn Sie das neue Microsoft 365 Admin Center nicht verwenden, können Sie es aktivieren, indem Sie den Umschalter **Das neue Admin Center** am oberen Rand der Startseite auswählen.

## <a name="remove-licenses"></a>Entfernen von Lizenzen

1. Navigieren Sie im Admin Center zur Seite **Abrechnung** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Produkte und Dienste</a>.

2. Suchen Sie auf der Seite **Produkte und Dienste** das Abonnement, aus dem Sie Lizenzen entfernen möchten, und wählen Sie dann **Lizenzen hinzufügen/entfernen** aus.

    [Was geschieht, wenn der Link zum Hinzufügen/Entfernen von Lizenzen nicht angezeigt wird?](#what-if-i-dont-see-the-addremove-licenses-link)

3. Geben Sie im Feld **Lizenzen insgesamt** die Gesamtzahl der Lizenzen ein, die Sie für dieses Abonnement benötigen, und wählen Sie dann **Änderung absenden** aus. Wenn Sie beispielsweise über 110 Lizenzen verfügen und 5 davon entfernen möchten, geben Sie 105 ein.

::: moniker-end

::: moniker range="o365-germany"

1. Navigieren Sie im Admin Center zur Seite **Abrechnung** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847745" target="_blank">Abonnements</a>.

2. Wählen Sie auf der Seite **Abonnements** das Abonnement aus, aus dem Sie Lizenzen entfernen möchten, und wählen Sie dann **Lizenzen hinzufügen/entfernen** aus.

    [Was geschieht, wenn der Link zum Hinzufügen/Entfernen von Lizenzen nicht angezeigt wird?](#what-if-i-dont-see-the-addremove-licenses-link)

3. Geben Sie im Feld **Lizenzen insgesamt** die Gesamtzahl der Lizenzen ein, die Sie für dieses Abonnement benötigen. Wählen Sie dann **Absenden** aus. Wenn Sie beispielsweise über 110 Lizenzen verfügen und 5 davon entfernen möchten, geben Sie "105" ein.


::: moniker-end

::: moniker range="o365-21vianet"

1. Navigieren Sie im Admin Center zur Seite **Abrechnung** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850626" target="_blank">Abonnements</a>.

2. Wählen Sie auf der Seite **Abonnements** das Abonnement aus, aus dem Sie Lizenzen entfernen möchten, und wählen Sie dann **Lizenzen hinzufügen/entfernen** aus.

    [Was geschieht, wenn der Link zum Hinzufügen/Entfernen von Lizenzen nicht angezeigt wird?](#what-if-i-dont-see-the-addremove-licenses-link)

3. Geben Sie im Feld **Lizenzen insgesamt** die Gesamtzahl der Lizenzen ein, die Sie für dieses Abonnement benötigen. Wählen Sie dann **Absenden** aus. Wenn Sie beispielsweise über 110 Lizenzen verfügen und 5 davon entfernen möchten, geben Sie "105" ein.

::: moniker-end

## <a name="what-if-i-dont-see-the-addremove-licenses-link"></a>Was geschieht, wenn der Link zum Hinzufügen/Entfernen von Lizenzen nicht angezeigt wird?

In diesem Abschnitt werden die Gründe beschrieben, warum der Link **Lizenzen hinzufügen/entfernen** möglicherweise nicht verfügbar ist und was Sie dann unternehmen können.
  
### <a name="a-credit-check-is-pending"></a>Eine Kreditwürdigkeitsprüfung steht aus

Wenn eine Kreditwürdigkeitsprüfung aussteht, wird die Meldung "Kreditwürdigkeitsprüfung ausstehend" angezeigt, und Sie können erst nach Abschluss der Prüfung Lizenzen entfernen. Schauen Sie bei einer ausstehenden Kreditwürdigkeitsprüfung später wieder nach, ob sie abgeschlossen wurde. Kreditwürdigkeitsprüfungen dauern in der Regel bis zu zwei Werktage bis zum Abschluss.
  
Nach Abschluss der Kreditwürdigkeitsprüfung sollte der Link **Lizenzen hinzufügen/entfernen** im Abschnitt **Benutzer** angezeigt werden. Navigieren Sie in diesem Fall zu [Entfernen von Lizenzen aus Ihrem Office 365 Business-Abonnement](#remove-licenses-from-your-office-365-for-business-subscription).
  
### <a name="you-activated-the-subscription-using-a-product-key"></a>Sie haben das Abonnement mit einem Product Key aktiviert

Wenn Ihr Abonnement erworben und unter Angabe eines 25-stelligen Product Keys aktiviert wurde, wird der Text "Prepaid" angezeigt. Wurde Ihr Abonnement unter Angabe eines Product Keys im Voraus bezahlt, können Sie keine Lizenzen entfernen, weil diese bereits bezahlt wurden. Jedoch können Sie die zusätzlichen Lizenzen entfernen, wenn Sie das Abonnement verlängern.
  
### <a name="you-bought-your-subscription-through-a-partner"></a>Sie haben Ihr Abonnement über einen Partner erworben

Wenn Sie Ihr Abonnement über einen CSP oder Partner erworben haben, können Sie keine Lizenzen entfernen. Wenden Sie sich an Ihren CSP oder verwenden Sie den Link "Volume Licensing Service Center (VLSC)", um Hilfe zu erhalten.
  
## <a name="what-you-need-to-know-about-removing-licenses-from-users-in-office-365-for-business"></a>Wissenswertes zum Entfernen von Lizenzen für Benutzer in Office 365 Business

- Sie müssen entweder ein globaler Administrator oder Benutzerverwaltungsadministrator sein. Weitere Informationen finden Sie unter [Informationen zu Administratorrollen](../../admin/add-users/about-admin-roles.md).

- Mit den nachstehenden Schritten können Sie einem vorhandenen Benutzerkonto eine Lizenz hinzufügen. [Erfahren Sie, wie Sie gleichzeitig ein Benutzerkonto hinzufügen und eine Lizenz zuweisen](../../admin/add-users/add-users.md).

## <a name="articles-about-managing-licenses-for-your-subscription"></a>Artikel zum Verwalten der Lizenzen Ihres Abonnements

- [Grundlegendes zu Abonnements und Lizenzen](subscriptions-and-licenses.md)

- [Entfernen von Benutzerlizenzen](../../admin/manage/remove-licenses-from-users.md)

- [Zuweisen von Lizenzen für Benutzer](../../admin/manage/assign-licenses-to-users.md)

- [Erwerben von Lizenzen für Ihr Abonnement](buy-licenses.md)

- [Erwerb eines weiteren Abonnements](../buy-another-subscription.md)

- [Erwerben oder Bearbeiten eines Add-Ons](../buy-or-edit-an-add-on.md)

- [Verwalten von Yammer-Benutzerlizenzen](https://docs.microsoft.com/yammer/manage-yammer-users/manage-yammer-licenses-in-office-365)

## <a name="related-links"></a>Verwandte Links

[Kündigen Ihres Abonnements](../subscriptions/cancel-your-subscription.md)
