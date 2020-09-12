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
description: Administratoren können sich mit der Verwaltung von Self-Service-Käufen von Benutzern in Ihrer Organisation vertraut machen.
ms.openlocfilehash: ca25bf0c3e3539196e81dcc289592028cc4dfa47
ms.sourcegitcommit: 27daadad9ca0f02a833ff3cff8a574551b9581da
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/12/2020
ms.locfileid: "47546674"
---
# <a name="manage-self-service-purchases-admin"></a>Self-Service-Einkäufe (Administrator) verwalten

::: moniker range="o365-21vianet"

> [!NOTE]
> Das Admin Center wird geändert. Wenn Ihre Erfahrung nicht den hier aufgeführten Details entspricht, lesen Sie [über das neue Microsoft 365 Admin Center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).

::: moniker-end

Als Administrator können Sie Self-Service-Käufe anzeigen, die von Personen in Ihrer Organisation getätigt wurden. Sie sehen den Produktnamen, den Käufer Namen, die erworbenen Abonnements, das Ablaufdatum, den Kaufpreis und die zugewiesenen Benutzer für jeden Self-Service-Einkauf. Wenn es für Ihre Organisation erforderlich ist, können Sie Self-Service-Einkauf auf Produktbasis über PowerShell deaktivieren. Sie haben die gleichen Datenverwaltungsdienste und Zugriffsrichtlinien für Produkte, die über Self-Service Purchase oder zentral erworben wurden.

Sie können auch steuern, ob Benutzer in Ihrer Organisation Self-Service-Käufe tätigen können. Weitere Informationen finden Sie unter [use AllowSelfServicePurchase for the MSCommerce PowerShell Module](allowselfservicepurchase-powershell.md).

## <a name="view-self-service-subscriptions"></a>Anzeigen von Self-Service-Abonnements

1. Wechseln Sie im Admin Center zur Seite **Fakturierung**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">ihrer Produkte</a> .
2. Wählen Sie auf der Registerkarte **Produkte** das Filtersymbol aus, und wählen Sie dann **Self-Service**aus.
3. Um weitere Details zu einem Abonnement anzuzeigen, wählen Sie eines aus der Liste aus.

## <a name="view-who-has-licenses-for-a-self-service-purchase-subscription"></a>Anzeigen, wer über Lizenzen für ein Self-Service-Abonnement für den Kauf verfügt

1. Wechseln Sie im Admin Center zur Seite **Abrechnungs**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Lizenzen</a> .
2. Wählen Sie das Filtersymbol aus, und wählen Sie dann **Self-Service**aus.
3. Wählen Sie ein Produkt aus, um den Personen zugewiesene Lizenzen anzuzeigen.
    > [!NOTE]
    > Wenn es mehrere Käufe für ein Produkt gibt, wird dieses Produkt nur einmal aufgeführt, und die Spalte **verfügbare Menge** zeigt die Summe aller Abonnements an, die für dieses Produkt erworben wurden.
4. Die **Benutzer** Liste wird nach den Namen von Personen gruppiert, die Self-Service-Käufe getätigt haben.
5. Um eine Liste der Benutzer mit Lizenzen für diese Abonnements zu exportieren, wählen Sie die Abonnements aus, die Sie exportieren möchten, und wählen Sie dann **Benutzer exportieren**aus.

## <a name="disable-or-enable-self-service-purchases"></a>Deaktivieren oder Aktivieren von Self-Service-Käufen

Sie können Self-Service-Käufe für Benutzer in Ihrer Organisation deaktivieren oder aktivieren. Das **MSCommerce** PowerShell-Modul enthält einen Parameterwert für die **Richtlinien** -Nr für **AllowSelfServicePurchase** , mit dem Sie steuern können, ob Benutzer in Ihrer Organisation Self-Service-Käufe tätigen können, und für welche Produkte.

Sie können das **MSCommerce** -PowerShell-Modul verwenden, um Folgendes zu tun:

- Anzeigen des Standardstatus des **AllowSelfServicePurchase** -Parameterwerts – unabhängig davon, ob er nach Produkt aktiviert oder deaktiviert ist
- Anzeigen einer Liste der anwendbaren Produkte und der Aktivierung oder Deaktivierung von Self-Service-Käufen
- Anzeigen oder Ändern der aktuellen Einstellung für ein bestimmtes Produkt, um es entweder zu aktivieren oder zu deaktivieren

Weitere Informationen finden Sie unter [use AllowSelfServicePurchase for the MSCommerce PowerShell Module](allowselfservicepurchase-powershell.md).

## <a name="centralize-licenses-under-a-single-subscription"></a>Zentralisieren von Lizenzen unter einem einzelnen Abonnement

Sie können vorhandene Lizenzen zuweisen oder zusätzliche Abonnements über vorhandene Vereinbarungen für Benutzer erwerben, die Self-Service-Käufen zugewiesen sind. Nachdem Sie diese zentral erworbenen Lizenzen zugewiesen haben, können Sie anfordern, dass die Käufer Ihre vorhandenen Abonnements kündigen.

1. Wechseln Sie im Admin Center zur Seite **Abrechnungs** \> - <a href="https://go.microsoft.com/fwlink/p/?linkid=868433" target="_blank">Einkaufsdienste</a> .
2. Suchen und wählen Sie das Produkt aus, das Sie kaufen möchten, und wählen Sie dann **kaufen**aus.
3. Führen Sie die restlichen Schritte aus, um den Kauf abzuschließen.
4. Befolgen Sie die Schritte unter [anzeigen, wer über Lizenzen für ein Self-Service-Abonnement verfügt](#view-who-has-licenses-for-a-self-service-purchase-subscription) , um im nächsten Schritt eine Liste der Benutzer zu exportieren, auf die verwiesen wird.
5. Zuweisen von Lizenzen zu allen Personen, die eine Lizenz im anderen Abonnement haben. Vollständige Schritte finden Sie unter [Zuweisen von Lizenzen zu Benutzern](../../admin/manage/assign-licenses-to-users.md).
6. Wenden Sie sich an die Person, die das Self-Service-Abonnement erworben hat, und bitten Sie Sie, [diese zu stornieren](manage-self-service-purchases-users.md#cancel-a-subscription).

## <a name="take-over-a-self-service-purchase-subscription"></a>Übernehmen eines Self-Service-Kauf Abonnements

Sie können ein Self-Service-Kauf Abonnement durchführen, das von einem Benutzer in Ihrer Organisation erstellt wurde. Wenn Sie ein Self-Service-Kauf Abonnement übernehmen, haben Sie zwei Möglichkeiten:

1. Sie können die Benutzer in ein anderes Abonnement migrieren und das ursprüngliche Abonnement kündigen.
2. Kündigen des Self-Service-Kauf Abonnements und Entfernen von Lizenzen von zugewiesenen Benutzern.

### <a name="move-users-to-a-different-subscription"></a>Verschieben von Benutzern zu einem anderen Abonnement

Wenn Sie Benutzer in ein anderes Abonnement migrieren, wird das alte Abonnement automatisch abgebrochen. Der Benutzer, der das Self-Service-Abonnement ursprünglich erworben hat, erhält eine e-Mail, die besagt, dass das Abonnement storniert wurde.

> [!NOTE]
> Sie benötigen eine verfügbare Lizenz für jeden Benutzer, den Sie in das Abonnement verschieben, zu dem Sie Benutzer verschieben.

1. Wechseln Sie im Admin Center zur Seite **Fakturierung**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">ihrer Produkte</a> .
2. Wählen Sie auf der Registerkarte **Produkte** das Filtersymbol aus, und wählen Sie dann **Self-Service**aus.
3. Wählen Sie das Abonnement aus, das Sie übernehmen möchten.
4. Wählen Sie auf der Seite Abonnementdetails im Abschnitt **Abonnements und Einstellungen** die Option **Steuerelement dieses Abonnements übernehmen**aus.
5. Wählen Sie im rechten Bereich **Benutzer migrieren**aus.
6. Wählen Sie das Produkt aus, zu dem Sie die Benutzer migrieren möchten, und wählen Sie dann **Benutzer migrieren**aus.
7. Wählen Sie im Feld **Benutzer werden zu** die Option **Benutzer verlagern**aus. Der Verschiebevorgang kann mehrere Minuten dauern. Schließen Sie den Browser nicht, während der Prozess ausgeführt wird.
8. Wenn der Verschiebevorgang abgeschlossen ist, schließen Sie den Bereich zum Verlegen **abgeschlossen**.
9. Auf der Seite Abonnementdetails wird der **Abonnementstatus** für das erworbene Self-Service-Abonnement als **gelöscht**angezeigt.

### <a name="cancel-a-self-service-purchase-subscription"></a>Kündigen eines Self-Service-Kauf Abonnements

Wenn Sie sich entscheiden, ein Self-Service-Abonnement zu kündigen, verlieren Benutzer mit Lizenzen keinen Zugriff auf das Produkt. Der Benutzer, der das Self-Service-Abonnement ursprünglich erworben hat, erhält eine e-Mail, die besagt, dass das Abonnement storniert wurde.

1. Wechseln Sie im Admin Center zur Seite **Fakturierung**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">ihrer Produkte</a> .
2. Wählen Sie auf der Registerkarte **Produkte** das Filtersymbol aus, und wählen Sie dann **Self-Service**aus.
3. Wählen Sie das Abonnement aus, das Sie abbrechen möchten.
4. Wählen Sie auf der Seite Abonnementdetails im Abschnitt **Abonnements und Einstellungen** die Option **Steuerelement dieses Abonnements übernehmen**aus.
5. Wählen Sie im rechten Bereich **Abonnement kündigen**aus.
6. Wählen Sie in der Dropdownliste einen Grund für Ihre Absage aus, und wählen Sie dann **Abonnement kündigen**aus.
7. Wählen Sie im Feld möchten **Sie wirklich kündigen?** die Option **Abonnement kündigen**aus.
8. Schließen Sie den rechten Bereich.
9. Auf der Seite Abonnementdetails wird der **Abonnementstatus** als **gelöscht**angezeigt.

## <a name="need-help-contact-us"></a>Benötigen Sie Hilfe? Kontaktieren Sie uns.

Häufige Fragen zum Self-Service-Einkauf finden Sie unter [Self-Service Purchases FAQ](self-service-purchase-faq.md).

Wenn Sie Fragen haben oder Hilfe bei Self-Service-Käufen benötigen, [wenden Sie sich an den Support](../../admin/contact-support-for-business-products.md).