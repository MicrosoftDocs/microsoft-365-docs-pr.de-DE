---
title: Verwalten von Self-Service-Käufen (Administratoren)
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
- commerce
search.appverid:
- MET150
description: Administratoren können sich mit der Verwaltung von Self-Service-Käufen von Benutzern in Ihrer Organisation vertraut machen.
ms.openlocfilehash: 5db942b42f398e8951da43add7013569af52c53f
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2020
ms.locfileid: "41594109"
---
# <a name="manage-self-service-purchases-admin"></a>Verwalten von Self-Service purchases (Administrator)

Als Administrator können Sie Self-Service-Käufe anzeigen, die von Personen in Ihrer Organisation getätigt wurden. Sie können das Produkt, den Käufer Namen, die erworbenen Abonnements, das Ablaufdatum, den Kaufpreis und die zugewiesenen Benutzer für jeden Self-Service-Einkauf sehen. Wenn es für Ihre Organisation erforderlich ist, können Sie Self-Service-Einkauf pro Produkt über PowerShell deaktivieren. Sie haben die gleichen Datenverwaltungsdienste und Zugriffsrichtlinien für Produkte, die über Self-Service Purchase oder zentral erworben wurden.

Sie können auch steuern, ob Benutzer in Ihrer Organisation Self-Service-Käufe tätigen können. Weitere Informationen finden Sie unter [use AllowSelfServicePurchase for the MSCommerce PowerShell Module](allowselfservicepurchase-powershell.md).

## <a name="view-self-service-subscriptions"></a>Anzeigen von Self-Service-Abonnements

1. Wechseln Sie im Admin Center zur Seite **Abrechnungs** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Produkte #a0 Dienste</a> .

2. Klicken Sie neben **Ergebnisse Verfeinern**in der Dropdownliste **Kontotyp** auf **Self-Service**.

3. Um weitere Details zu einem Abonnement anzuzeigen, wählen Sie eines aus der Liste aus.

## <a name="view-who-has-licenses-for-a-self-service-purchase-subscription"></a>Anzeigen, wer über Lizenzen für ein Self-Service-Abonnement für den Kauf verfügt

1. Wechseln Sie im Admin Center zur Seite **Abrechnungs** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Lizenzen</a> .

2. Klicken Sie auf das Filtersymbol, und wählen Sie dann **Self-Service**aus.

3. Wählen Sie ein Produkt aus, um den Personen zugewiesene Lizenzen anzuzeigen.

    > [!NOTE]
    > Wenn es mehrere Käufe für ein Produkt gibt, wird dieses Produkt nur einmal aufgeführt, und die Spalte **verfügbare Menge** zeigt die Summe aller Abonnements an, die für dieses Produkt erworben wurden.

4. Die **Benutzer** Liste wird nach den Namen von Personen gruppiert, die Self-Service-Käufe getätigt haben.

5. Um eine Liste der Benutzer mit Lizenzen für diese Abonnements zu exportieren, wählen Sie die Abonnements aus, die Sie exportieren möchten, und wählen Sie dann **Benutzer exportieren**aus.

## <a name="disable-or-enable-self-service-purchases"></a>Deaktivieren oder Aktivieren von Self-Service-Käufen

Sie können Self-Service-Käufe für Benutzer in Ihrer Organisation deaktivieren oder aktivieren. Das **MSCommerce** PowerShell-Modul enthält einen Parameterwert für die **Richtlinien** -Nr für **AllowSelfServicePurchase** , mit dem Sie steuern können, ob Benutzer in Ihrer Organisation Self-Service-Käufe tätigen können, und für welche Produkte.

Sie können das **MSCommerce** -PowerShell-Modul verwenden, um Folgendes zu tun:

- Anzeigen des Standardstatus des **AllowSelfServicePurchase** -Parameterwerts &mdash; , ob er nach Produkt aktiviert oder deaktiviert ist
- Anzeigen einer Liste der anwendbaren Produkte und der Aktivierung oder Deaktivierung von Self-Service-Käufen
- Anzeigen oder Ändern der aktuellen Einstellung für ein bestimmtes Produkt, um es entweder zu aktivieren oder zu deaktivieren

Weitere Informationen finden Sie unter [use AllowSelfServicePurchase for the MSCommerce PowerShell Module](allowselfservicepurchase-powershell.md).

## <a name="centralize-licenses-under-a-single-subscription"></a>Zentralisieren von Lizenzen unter einem einzelnen Abonnement

Sie können vorhandene Lizenzen zuweisen oder zusätzliche Abonnements über vorhandene Vereinbarungen für Benutzer erwerben, die Self-Service-Käufen zugewiesen sind. Nachdem Sie diese zentral erworbenen Lizenzen zugewiesen haben, können Sie anfordern, dass die Käufer Ihre vorhandenen Abonnements kündigen.

1. Melden Sie sich mit ihrem globalen Administrator-oder abrechnungsadministrator Konto beim <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Admin Center</a> an.

2. Wechseln Sie zur Seite **Abrechnungs** > -<a href="https://go.microsoft.com/fwlink/p/?linkid=868433" target="_blank">Einkaufsdienste</a> .

3. Suchen und wählen Sie das Produkt aus, das Sie kaufen möchten, und wählen Sie dann **kaufen**aus.

4. Führen Sie die restlichen Schritte aus, um den Kauf abzuschließen.

5. Befolgen Sie die Schritte unter [anzeigen, wer über Lizenzen für ein Self-Service-Abonnement verfügt](#view-who-has-licenses-for-a-self-service-purchase-subscription) , um eine Liste der in Schritt 6 zu referenzierenden Benutzer zu exportieren.

6. Zuweisen von Lizenzen zu allen Personen, die eine Lizenz im anderen Abonnement haben. Vollständige Schritte finden Sie unter [Zuweisen von Lizenzen zu Benutzern](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users).

7. Wenden Sie sich an die Person, die das Self-Service-Abonnement erworben hat, und bitten Sie Sie, diese zu stornieren.

## <a name="need-help-contact-us"></a>Benötigen Sie Hilfe? Kontaktieren Sie uns.

Häufige Fragen zum Self-Service-Einkauf finden Sie unter [Self-Service Purchases FAQ](self-service-purchase-faq.md).

Wenn Sie Fragen haben oder Hilfe bei Self-Service-Käufen benötigen, [wenden Sie sich an den Support](https://docs.microsoft.com/office365/admin/contact-support-for-business-products).