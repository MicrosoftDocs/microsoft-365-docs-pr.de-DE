---
title: Verwalten von Self-Service-Käufen (Administratoren)
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- commerce
ms.custom: AdminSurgePortfolio
search.appverid:
- MET150
description: Administratoren können erfahren, wie Sie Self-Service-Käufe von Benutzern in ihrer Organisation verwalten.
ms.openlocfilehash: 3e04f58c10b14aca8b356c064106b7107f144d91
ms.sourcegitcommit: 0d709e9ab0d8d56c5fc11a921298f82e40e122c5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/05/2021
ms.locfileid: "50114693"
---
# <a name="manage-self-service-purchases-admin"></a>Self-Service-Einkäufe (Administrator) verwalten

::: moniker range="o365-21vianet"

> [!NOTE]
> Das Admin Center wird geändert. Wenn Ihre Erfahrung nicht den hier aufgeführten Details entspricht, lesen Sie [über das neue Microsoft 365 Admin Center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true).

::: moniker-end

Als Administrator können Sie Self-Service-Käufe von Personen in Ihrer Organisation sehen. Für jeden Self-Service-Kauf werden der Produktname, der Käufername, die erworbenen Abonnements, das Ablaufdatum, der Verkaufspreis und die zugewiesenen Benutzer angezeigt. Wenn dies für Ihre Organisation erforderlich ist, können Sie den Self-Service-Kauf pro Produkt über PowerShell deaktivieren. Sie verfügen über die gleichen Datenverwaltungs- und Zugriffsrichtlinien gegenüber Produkten, die über den Self-Service-Kauf oder zentral erworben wurden.

Sie können auch steuern, ob Benutzer in Ihrer Organisation Self-Service-Käufe tätigen können. Weitere Informationen finden Sie unter [Verwenden von AllowSelfServicePurchase für das MSSelf PowerShell-Modul.](allowselfservicepurchase-powershell.md)

## <a name="view-self-service-subscriptions"></a>Anzeigen von Self-Service-Abonnements

1. Navigieren Sie im Admin Center zur Seite **Abrechnung** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Ihre Produkte</a>.
2. Wählen Sie **auf der** Registerkarte "Produkte" das Filtersymbol und dann **"Self-Service" aus.**
3. Wenn Sie weitere Details zu einem Abonnement anzeigen möchten, wählen Sie eine aus der Liste aus.

## <a name="view-who-has-licenses-for-a-self-service-purchase-subscription"></a>Anzeigen, wer Über Lizenzen für ein Self-Service-Kaufabonnement verfügt

1. Wechseln Sie im Admin Center zur Seite "Abrechnungslizenzen".  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank"></a>
2. Wählen Sie das Filtersymbol und dann **"Self-Service" aus.**
3. Wählen Sie ein Produkt aus, um Den Personen zugewiesene Lizenzen zu sehen.
    > [!NOTE]
    > Wenn mehrere Einkäufe für ein Produkt vorhanden sind, wird  dieses Produkt nur einmal aufgeführt, und in der Spalte "Verfügbare Menge" wird die Summe aller Abonnements angezeigt, die für dieses Produkt gekauft wurden.
4. Die **Liste** "Benutzer" ist nach den Namen der Personen, die Self-Service-Käufe getätigt haben, gruppieren.
5. Um eine Liste der Benutzer mit Lizenzen für diese Abonnements zu exportieren, wählen Sie die Abonnements aus, die Sie exportieren möchten, und wählen Sie dann **"Benutzer exportieren" aus.**

## <a name="disable-or-enable-self-service-purchases"></a>Deaktivieren oder Aktivieren von Self-Service-Käufen

Sie können Self-Service-Käufe für Benutzer in Ihrer Organisation deaktivieren oder aktivieren. Das **MSSelf** -PowerShell-Modul enthält einen **PolicyID-Parameterwert** für **AllowSelfServicePurchase,** mit dem Sie steuern können, ob Benutzer in Ihrer Organisation Self-Service-Käufe tätigen können und für welche Produkte.

Sie können das **MS Commerce -PowerShell-Modul** verwenden, um:

- Anzeigen des Standardstatus des Parameters **"AllowSelfServicePurchase"** – unabhängig davon, ob er nach Produkt aktiviert oder deaktiviert ist
- Anzeigen einer Liste der zutreffenden Produkte und ob der Self-Service-Kauf aktiviert oder deaktiviert ist
- Anzeigen oder Ändern der aktuellen Einstellung für ein bestimmtes Produkt zum Aktivieren oder Deaktivieren

Weitere Informationen finden Sie unter [Verwenden von AllowSelfServicePurchase für das MSSelf PowerShell-Modul.](allowselfservicepurchase-powershell.md)

## <a name="centralize-licenses-under-a-single-subscription"></a>Zentralisieren von Lizenzen unter einem einzelnen Abonnement

Sie können vorhandene Lizenzen zuweisen oder zusätzliche Abonnements über bestehende Vereinbarungen für Benutzer erwerben, die Self-Service-Käufen zugewiesen sind. Nachdem Sie diese zentral erworbenen Lizenzen zugewiesen haben, können Sie anfordern, dass Käufer ihre vorhandenen Abonnements kündigen.

1. Wechseln Sie im Admin  Center zur Seite "Abrechnungskaufdienste". \> <a href="https://go.microsoft.com/fwlink/p/?linkid=868433" target="_blank"></a>
2. Suchen Sie das Produkt, das Sie kaufen möchten, und wählen Sie dann **"Kaufen" aus.**
3. Führen Sie die verbleibenden Schritte aus, um den Kauf abschließen zu können.
4. Führen Sie die Schritte in "Anzeigen" aus, die Lizenzen für ein erworbenes [Self-Service-Abonnement](#view-who-has-licenses-for-a-self-service-purchase-subscription) besitzen, um eine Liste der Benutzer zu exportieren, auf die im nächsten Schritt verwiesen werden soll.
5. Weisen Sie allen Benutzern, die über eine Lizenz im anderen Abonnement verfügen, Lizenzen zu. Vollständige Schritte finden Sie unter [Zuweisen von Lizenzen zu Benutzern.](../../admin/manage/assign-licenses-to-users.md)
6. Wenden Sie sich an die Person, die das Self-Service-Kaufabonnement erworben hat, und bitten Sie sie, [es zu kündigen.](manage-self-service-purchases-users.md#cancel-a-subscription)

## <a name="take-over-a-self-service-purchase-subscription"></a>Übernehmen eines Self-Service-Kaufabonnements

Sie können ein Self-Service-Kaufabonnement übernehmen, das von einem Benutzer in Ihrer Organisation vorgenommen wurde. Wenn Sie ein Self-Service-Kaufabonnement übernehmen, haben Sie zwei Möglichkeiten:

1. Verschieben Sie die Benutzer in ein anderes Abonnement, und kündigen Sie das ursprüngliche Abonnement.
2. Kündigen Sie das Self-Service-Kaufabonnement, und entfernen Sie Lizenzen von zugewiesenen Benutzern.

### <a name="move-users-to-a-different-subscription"></a>Verschieben von Benutzern zu einem anderen Abonnement

Wenn Sie Benutzer in ein anderes Abonnement verschieben, wird das alte Abonnement automatisch gekündigt. Der Benutzer, der das Self-Service-Kaufabonnement ursprünglich erworben hat, erhält eine E-Mail mit der Nachricht, dass das Abonnement gekündigt wurde.

> [!NOTE]
> Sie müssen über eine verfügbare Lizenz für jeden Benutzer verfügen, auf den Sie in dem Abonnement umstiegen, zu dem Sie Benutzer verschieben.

1. Navigieren Sie im Admin Center zur Seite **Abrechnung** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Ihre Produkte</a>.
2. Wählen Sie **auf der** Registerkarte "Produkte" das Filtersymbol und dann **"Self-Service" aus.**
3. Wählen Sie das Abonnement aus, das Sie übernehmen möchten.
4. Wählen Sie auf der Seite mit den Abonnementdetails im Abschnitt **"Abonnements** und Einstellungen" die Option **"Übernehmen der Kontrolle über dieses Abonnement" aus.**
5. Wählen Sie im rechten Bereich **"Benutzer verschieben" aus.**
6. Wählen Sie das Produkt aus, in das Sie die Benutzer verschieben möchten, und wählen Sie dann **"Benutzer verschieben" aus.**
7. Wählen Sie im **Feld "Benutzer verschieben in"** die Option **"Benutzer verschieben" aus.** Der Verschiebevorgang kann mehrere Minuten dauern. Schließen Sie den Browser nicht, während der Prozess ausgeführt wird.
8. Schließen Sie nach Abschluss des Verschiebevorgangs den Bereich **"Verschieben abgeschlossen".**
9. Auf der Seite mit den Abonnementdetails wird **der Abonnementstatus** für das erworbene Self-Service-Abonnement als **gelöscht angezeigt.**

### <a name="cancel-a-self-service-purchase-subscription"></a>Kündigen eines Self-Service-Kaufabonnements

Wenn Sie ein Self-Service-Kaufabonnement kündigen, verlieren Benutzer mit Lizenzen den Zugriff auf das Produkt. Der Benutzer, der das Self-Service-Kaufabonnement ursprünglich erworben hat, erhält eine E-Mail mit der Nachricht, dass das Abonnement gekündigt wurde.

1. Navigieren Sie im Admin Center zur Seite **Abrechnung** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Ihre Produkte</a>.
2. Wählen Sie **auf der** Registerkarte "Produkte" das Filtersymbol und dann **"Self-Service" aus.**
3. Wählen Sie das Abonnement aus, das Sie kündigen möchten.
4. Wählen Sie auf der Seite mit den Abonnementdetails im Abschnitt **"Abonnements** und Einstellungen" die Option **"Übernehmen der Kontrolle über dieses Abonnement" aus.**
5. Wählen Sie im rechten Bereich "Abonnement **kündigen" aus.**
6. Wählen Sie in der Dropdownliste einen Grund für ihre Kündigung aus, und wählen Sie dann Abonnement **kündigen aus.**
7. Wählen Sie **im Feld "Möchten Sie das Abonnement wirklich kündigen?"** die Option **"Abonnement kündigen" aus.**
8. Schließen Sie den rechten Bereich.
9. Auf der Seite mit den Abonnementdetails wird **der Abonnementstatus** als gelöscht **angezeigt.**

## <a name="need-help-contact-us"></a>Benötigen Sie Hilfe? Wenden Sie sich an uns.

Häufig gestellte Fragen zu Self-Service-Käufen finden Sie unter Häufig gestellte Fragen zu [Self-Service-Käufen.](self-service-purchase-faq.md)

Wenn Sie Fragen haben oder Hilfe bei Self-Service-Käufen benötigen, wenden [Sie sich an den Support.](../../admin/contact-support-for-business-products.md)