---
title: Verwalten von Self-Service-Käufen (Admins)
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
ms.reviewer: mijeffer, pablom
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- okr_smb
- commerce_ssp
search.appverid:
- MET150
description: Administratoren können erfahren, wie Sie Self-Service-Käufe von Benutzern in ihrer Organisation verwalten.
ms.date: 03/26/2021
ms.openlocfilehash: a4ac4b79a9a73f80fc22e6f14696e25925df9faf
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2021
ms.locfileid: "52536094"
---
# <a name="manage-self-service-purchases-admin"></a>Self-Service-Einkäufe (Administrator) verwalten

Als Administrator können Sie Self-Service-Käufe von Personen in Ihrer Organisation sehen. Der Produktname, der Käufername, die erworbenen Abonnements, das Ablaufdatum, der Einkaufspreis und die zugewiesenen Benutzer werden für jeden Self-Service-Kauf angezeigt. Falls von Ihrer Organisation erforderlich, können Sie den Self-Service-Kauf pro Produktbasis über PowerShell deaktivieren. Sie verfügen über dieselben Datenverwaltungs- und Zugriffsrichtlinien über Produkte, die über den Self-Service-Kauf oder zentral erworben wurden.

Sie können auch steuern, ob Benutzer in Ihrer Organisation Self-Service-Käufe tätigen können. Weitere Informationen finden Sie unter [Use AllowSelfServicePurchase for the MS Commerce PowerShell module](allowselfservicepurchase-powershell.md).

## <a name="view-self-service-subscriptions"></a>Anzeigen von Self-Service-Abonnements

::: moniker range="o365-worldwide"

1. Navigieren Sie im Admin Center zur Seite **Abrechnung** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Ihre Produkte</a>.

::: moniker-end

::: moniker range="o365-germany"

1. Navigieren Sie im Admin Center zur Seite **Abrechnung** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847745" target="_blank">Ihre Produkte</a>.

::: moniker-end

::: moniker range="o365-21vianet"

1. Navigieren Sie im Admin Center zur Seite **Abrechnung** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850626" target="_blank">Ihre Produkte</a>.
::: moniker-end

2. Wählen Sie **auf der** Registerkarte Produkte das Filtersymbol aus, und wählen Sie **dann Self-Service aus.**
3. Wenn Sie weitere Details zu einem Abonnement anzeigen möchten, wählen Sie eines aus der Liste aus.

## <a name="view-who-has-licenses-for-a-self-service-purchase-subscription"></a>Anzeigen von Lizenzen für ein Self-Service-Kaufabonnement

> [!NOTE]
> Als Administrator können Sie keine Lizenzen für ein Self-Service-Kaufabonnement zuweisen oder aufheben, die von einem Benutzer in Ihrer Organisation erworben wurden. Sie können ein [Self-Service-Kaufabonnement übernehmen](#take-over-a-self-service-purchase-subscription)und dann Lizenzen zuweisen oder die Zuweisung von Lizenzen kündigen.

::: moniker range="o365-worldwide"

1. Navigieren Sie im Admin Center zur Seite **Abrechnung** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Lizenzen</a>.

::: moniker-end

::: moniker range="o365-germany"

 1. Navigieren Sie im Admin Center zur Seite **Abrechnung** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=848038" target="_blank">Lizenzen</a>.

::: moniker-end

::: moniker range="o365-21vianet"

 1. Navigieren Sie im Admin Center zur Seite **Abrechnung** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850625" target="_blank">Lizenzen</a>.

::: moniker-end

2. Wählen Sie das Filtersymbol aus, und wählen Sie **dann Self-Service aus.**
3. Wählen Sie ein Produkt aus, um Den Personen zugewiesene Lizenzen zu sehen.
    > [!NOTE]
    > Wenn mehrere Einkäufe für ein Produkt vorhanden sind, wird  dieses Produkt nur einmal aufgeführt, und die Spalte Verfügbare Menge zeigt die Gesamtzahl aller Abonnements an, die für dieses Produkt gekauft wurden.
4. Die **Liste Benutzer** wird nach den Namen der Personen, die Self-Service-Käufe getätigt haben, gruppieren.
5. Wenn Sie eine Liste der Benutzer mit Lizenzen für diese Abonnements exportieren möchten, wählen Sie die Abonnements aus, die Sie exportieren möchten, und wählen Sie **dann Benutzer exportieren aus.**

## <a name="disable-or-enable-self-service-purchases"></a>Deaktivieren oder Aktivieren von Self-Service-Käufen

Sie können Self-Service-Käufe für Benutzer in Ihrer Organisation deaktivieren oder aktivieren. Das **MS Commerce** PowerShell-Modul enthält einen **PolicyID-Parameterwert** für **AllowSelfServicePurchase,** mit dem Sie steuern können, ob Benutzer in Ihrer Organisation Self-Service-Käufe tätigen können und für welche Produkte.

Sie können das **MS Commerce PowerShell-Modul** verwenden, um:

- Anzeigen des Standardstatus des **Parameterwerts AllowSelfServicePurchase** – unabhängig davon, ob er nach Produkt aktiviert oder deaktiviert ist
- Anzeigen einer Liste der zutreffenden Produkte und ob der Self-Service-Kauf aktiviert oder deaktiviert ist
- Anzeigen oder Ändern der aktuellen Einstellung für ein bestimmtes Produkt, um sie entweder zu aktivieren oder zu deaktivieren

Weitere Informationen finden Sie unter [Use AllowSelfServicePurchase for the MS Commerce PowerShell module](allowselfservicepurchase-powershell.md).

## <a name="centralize-licenses-under-a-single-subscription"></a>Zentralisieren von Lizenzen unter einem einzigen Abonnement

Sie können vorhandene Lizenzen zuweisen oder zusätzliche Abonnements über vorhandene Vereinbarungen für Benutzer erwerben, die Self-Service-Käufen zugewiesen sind. Nachdem Sie diese zentral erworbenen Lizenzen zugewiesen haben, können Sie anfordern, dass Käufer ihre vorhandenen Abonnements kündigen.

::: moniker range="o365-worldwide"

1. Wechseln Sie im Admin  Center zur Seite > <a href="https://go.microsoft.com/fwlink/p/?linkid=868433" target="_blank">Abrechnungskaufdienste.</a>

::: moniker-end

::: moniker range="o365-germany"

1. Wechseln Sie <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">im Admin Center</a>zur Seite  > **Abrechnungskaufdienste.**

::: moniker-end

::: moniker range="o365-21vianet"

1. Wechseln Sie <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">im Admin Center</a>zur Seite  > **Abrechnungskaufdienste.**

::: moniker-end

2. Suchen Sie das Produkt, das Sie kaufen möchten, und wählen Sie dann **Kaufen aus.**
3. Führen Sie die verbleibenden Schritte aus, um Ihren Kauf zu abschließen.
4. Führen Sie die Schritte in [View who has licenses for a self-service purchased subscription](#view-who-has-licenses-for-a-self-service-purchase-subscription) aus, um eine Liste von Benutzern zu exportieren, auf die im nächsten Schritt verwiesen werden soll.
5. Weisen Sie allen Benutzern, die über eine Lizenz im anderen Abonnement verfügen, Lizenzen zu. Vollständige Schritte finden Sie unter [Zuweisen von Lizenzen zu Benutzern](../../admin/manage/assign-licenses-to-users.md).
6. Wenden Sie sich an die Person, die das Self-Service-Kaufabonnement erworben hat, und bitten Sie sie, es [zu kündigen.](manage-self-service-purchases-users.md#cancel-a-subscription)

## <a name="take-over-a-self-service-purchase-subscription"></a>Übernehmen eines Self-Service-Kaufabonnements

Sie können ein Self-Service-Kaufabonnement übernehmen, das von einem Benutzer in Ihrer Organisation vorgenommen wurde. Wenn Sie ein Self-Service-Kaufabonnement übernehmen, haben Sie zwei Optionen:

1. Verschieben Sie die Benutzer in ein anderes Abonnement, und kündigen Sie das ursprüngliche Abonnement.
2. Kündigen Sie das Self-Service-Kaufabonnement, und entfernen Sie Lizenzen von zugewiesenen Benutzern.

### <a name="move-users-to-a-different-subscription"></a>Verschieben von Benutzern zu einem anderen Abonnement

Wenn Sie Benutzer in ein anderes Abonnement verschieben, wird das alte Abonnement automatisch gekündigt. Der Benutzer, der das Self-Service-Kaufabonnement ursprünglich erworben hat, erhält eine E-Mail mit der Nachricht, dass das Abonnement gekündigt wurde.

> [!NOTE]
> Sie müssen über eine verfügbare Lizenz für jeden Benutzer verfügen, in den Sie das Abonnement verschieben, zu dem Sie Benutzer verschieben.

::: moniker range="o365-worldwide"

1. Navigieren Sie im Admin Center zur Seite **Abrechnung** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Ihre Produkte</a>.

::: moniker-end

::: moniker range="o365-germany"

1. Wechseln Sie <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">im Admin Center</a>zur Seite **Abrechnung** > **Ihre Produkte.**

::: moniker-end

::: moniker range="o365-21vianet"

1. Wechseln Sie <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">im Admin Center</a>zur Seite **Abrechnung** > **Ihre Produkte.**

::: moniker-end

2. Wählen Sie **auf der** Registerkarte Produkte das Filtersymbol aus, und wählen Sie **dann Self-Service aus.**
3. Wählen Sie das Abonnement aus, das Sie übernehmen möchten.
4. Wählen Sie auf der Seite Abonnementdetails im Abschnitt **Abonnements und** Einstellungen die Option Kontrolle über dieses Abonnement **übernehmen aus.**
5. Wählen Sie im rechten Bereich Benutzer **verschieben aus.**
6. Wählen Sie das Produkt aus, in das Sie die Benutzer verschieben möchten, und wählen Sie **dann Benutzer verschieben aus.**
7. Wählen Sie **im Feld Benutzer in** verschieben die Option Benutzer verschieben **aus.** Der Verschiebevorgang kann einige Minuten dauern. Schließen Sie den Browser nicht, während der Prozess ausgeführt wird.
8. Schließen Sie nach Abschluss des Verschiebens den **Bereich Abgeschlossen verschieben.**
9. Auf der Seite Abonnementdetails wird **der Abonnementstatus** für das gekaufte Self-Service-Abonnement als **Gelöscht angezeigt.**

### <a name="cancel-a-self-service-purchase-subscription"></a>Kündigen eines Self-Service-Kaufabonnements

Wenn Sie ein Self-Service-Kaufabonnement kündigen, verlieren Benutzer mit Lizenzen den Zugriff auf das Produkt. Der Benutzer, der das Self-Service-Kaufabonnement ursprünglich erworben hat, erhält eine E-Mail mit der Nachricht, dass das Abonnement gekündigt wurde.

::: moniker range="o365-worldwide"

1. Navigieren Sie im Admin Center zur Seite **Abrechnung** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Ihre Produkte</a>.

::: moniker-end

::: moniker range="o365-germany"

1. Wechseln Sie <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">im Admin Center</a>zur Seite **Abrechnung** > **Ihre Produkte.**

::: moniker-end

::: moniker range="o365-21vianet"

1. Wechseln Sie <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">im Admin Center</a>zur Seite **Abrechnung** > **Ihre Produkte.**

::: moniker-end

2. Wählen Sie **auf der** Registerkarte Produkte das Filtersymbol aus, und wählen Sie **dann Self-Service aus.**
3. Wählen Sie das Abonnement aus, das Sie stornieren möchten.
4. Wählen Sie auf der Seite Abonnementdetails im Abschnitt **Abonnements und** Einstellungen die Option Kontrolle über dieses Abonnement **übernehmen aus.**
5. Wählen Sie im rechten Bereich Abonnement **abbrechen aus.**
6. Wählen Sie in der Dropdownliste einen Grund für Ihre Kündigung aus, und wählen Sie Dann **Abonnement abbrechen aus.**
7. Wählen Sie im Feld Sind **Sie sicher, dass Sie kündigen möchten?** die Option **Abonnement abbrechen aus.**
8. Schließen Sie den rechten Bereich.
9. Auf der Seite Abonnementdetails wird der **Abonnementstatus** als **Gelöscht angezeigt.**

## <a name="need-help-contact-us"></a>Benötigen Sie Hilfe? Kontaktieren Sie uns.

Allgemeine Fragen zu Self-Service-Käufen finden Sie unter Häufig gestellte Fragen zu [Self-Service-Käufen.](self-service-purchase-faq.yml)

Wenn Sie Fragen haben oder Hilfe bei Self-Service-Käufen benötigen, wenden [Sie sich an den Support.](../../business-video/get-help-support.md)
