---
title: Upgrade von einem Office 365 E4-Abonnement
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
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
- commerce
ms.custom: customer-email
search.appverid:
- MET150
description: Erfahren Sie, wie Sie ein Upgrade von einem Office 365 E4-Abonnement durchführen.
ms.date: 08/14/2020
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 3ab3ac1c85dc3726585f9c414449ff4847626fc8
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46690697"
---
# <a name="upgrade-from-an-office-365-e4-subscription"></a>Upgrade von einem Office 365 E4-Abonnement

In diesem Artikel werden Sie schrittweise durch den Vorgang des Upgrades von einem Office 365 E4 auf ein neues Abonnement geführt. Informationen zu den Optionen, die beim Upgrade von Office 365 E4 zur Verfügung stehen, finden Sie unter [wichtige Informationen für Office 365 E4-Kunden](important-information-e4.md).

> [!IMPORTANT]
> Dieser Artikel bezieht sich auf Office 365 E4-Abonnements, die direkt bei Microsoft per Kreditkarte oder Rechnung gekauft wurden. Wenn Ihr Abonnement auf andere Weise erworben wurde, beispielsweise über einen Partner oder über das Volume Licensing Service Center, wenden Sie sich an Ihren Microsoft-Konto Vertreter oder Partner, um das Upgrade der Pläne zu unterstützen.

## <a name="what-are-my-options-for-how-to-upgrade"></a>Welche Optionen habe ich für ein Upgrade?

Die einfachste Möglichkeit zum Upgrade Ihres Plans ist die Verwendung der Registerkarte " **Upgrade** " im Microsoft 365 Admin Center. Die Verwendung der Registerkarte **Upgrade** wird jedoch nicht in allen Situationen unterstützt. Wenn Ihr Szenario nicht unterstützt wird, können Sie Pläne möglicherweise manuell aktualisieren.

## <a name="what-is-the-upgrade-tab"></a>Was ist die Registerkarte "Upgrade"?

Die Registerkarte **Upgrade** führt für Sie die folgenden Aufgaben aus:

- Er führt Sie durch das Verfahren zum Kauf eines neuen Plans.
- Er weist alle Benutzerlizenzen aus dem alten Plan dem neuen Plan zu.
- Er kündigt Ihren alten Plan.

## <a name="what-does-it-mean-to-upgrade-plans-manually"></a>Was bedeutet es, Pläne manuell zu aktualisieren?

Das manuelle Aktualisieren von Plänen bedeutet, dass Sie die folgenden separaten Verfahren anstelle der Registerkarte " **Upgrade** " ausführen.

- Erwerben Sie ein neues Abonnement mit der richtigen Anzahl von Lizenzen.
- Überprüfen, ob das Abonnement einsatzbereit ist.
- Zuweisen von Lizenzen zu Benutzern.
- Kündigen Sie das ursprüngliche Office 365 E4-Abonnement.

## <a name="find-out-if-you-can-use-the-upgrade-tab-to-upgrade-to-a-new-plan"></a>Finden Sie heraus, ob Sie auf der Registerkarte "Upgrade" ein Upgrade auf einen neuen Plan durchführen können.

1. Wechseln Sie im Admin Center zur Seite **Fakturierung**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">ihrer Produkte</a> .
2. Wählen Sie Ihr Abonnement für Office 365 E4 aus.
3. Wählen Sie die Registerkarte **Upgrade** aus. Wenn andere Pläne aufgeführt werden, bedeutet dies, dass Sie Pläne automatisch aktualisieren können.
4. Wenn Sie kein automatisches Upgrade durchführen können, wird eine Meldung angezeigt, in der der Grund für das Upgrade beschrieben wird.

Es gibt mehrere Gründe, warum Sie Pläne nicht automatisch aktualisieren können. Die meisten der Probleme sind vorübergehender Natur, wie Probleme mit dem Dienststatus, die Sie beheben können. Weitere Informationen finden Sie unter [Warum kann ich keine Pläne aktualisieren?](upgrade-to-different-plan.md#why-cant-i-upgrade-plans) Wenn Sie Hilfe zu Ihrem Upgrade benötigen, [wenden Sie sich an den Support](../../admin/contact-support-for-business-products.md).

## <a name="will-a-credit-check-be-required"></a>Ist eine Bonitätsprüfung erforderlich?

Wenn Sie Ihren neuen Plan per Rechnung bezahlen oder Ihr Einkauf über einem bestimmten Preis liegt, ist möglicherweise eine Bonitätsprüfung erforderlich. Wenn eine Bonitätsprüfung erforderlich ist, kann das Upgrade bis zu zwei Werktage dauern. Administratoren haben keinen Zugriff auf das Microsoft 365 Admin Center, bis die Bonitätsprüfung abgeschlossen ist. Benutzer haben jedoch weiterhin Vollzugriff auf den E4-Plan, bis das Upgrade abgeschlossen ist.

## <a name="upgrade-your-plan-by-using-the-upgrade-tab"></a>Aktualisieren des Plans mithilfe der Registerkarte "Upgrade"

### <a name="before-you-begin"></a>Bevor Sie beginnen

Hier einige wichtige Informationen, die Sie kennen sollten, bevor Sie die ersten Schritte unternehmen.

- **Planen von Verwaltungs Ausfällen** Administratoren können das Microsoft 365 Admin Center nicht verwenden, während der Plan aktualisiert wird. Je nach der Anzahl der Benutzer, die Sie haben, kann das Upgrade von Minuten auf Stunden dauern. Es wird empfohlen, das Upgrade zu planen, wenn Sie keine Updates mit dem Microsoft 365 Admin Center vornehmen müssen.

    Bei einem Upgrade des Plans treten für Benutzer keine Unterbrechung des Diensts auf – Sie haben während des Upgrades weiterhin vollständigen Zugriff auf das E4-Abonnement. Wenn das Upgrade abgeschlossen ist, haben Benutzer Zugriff auf den neuen Plan.
- **Benutzer, Lizenzen, Abrechnung und benutzerdefinierte Domänen.** Informationen dazu, wie Benutzer und Lizenzen während des Upgrades verarbeitet werden, wie sich das upgradepläne auf Ihre Abrechnung auswirkt und wie benutzerdefinierte Domänen behandelt werden, finden Sie unter [Was bewirkt das Upgrade eines Plans an meinen Dienst und die Abrechnung?](upgrade-to-different-plan.md#what-does-upgrading-a-plan-do-to-my-service-and-billing)
- **Ändern Sie die Anzahl der Benutzerlizenzen.** Sie können keine Lizenzen im Rahmen der Aktualisierung von Plänen entfernen. Sie können jedoch [die Anzahl der Lizenzen](../licenses/buy-licenses.md) vor oder nach dem Upgrade von Plänen reduzieren.

### <a name="start-the-upgrade-by-using-the-upgrade-tab"></a>Starten des Upgrades mithilfe der Registerkarte "Upgrade"

1. Wechseln Sie im Admin Center zur Seite **Fakturierung**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">ihrer Produkte</a> .
2. Wählen Sie Ihr Abonnement für Office 365 E4 aus.
3. Wählen Sie auf der Seite Abonnementdetails die Registerkarte **Upgrade** aus.
4. Suchen Sie das Abonnement, das Sie kaufen möchten, und wählen Sie dann **Upgrade**aus.
5. Überprüfen Sie auf der Seite **Warenkorb** , ob alles korrekt ist. Wählen Sie aus, ob Sie monatlich oder jährlich zahlen möchten, und überprüfen Sie die Anzahl der Lizenzen unter **Quantity**.
    > [!NOTE]
    > Alle Add-on-Abonnements, die Ihrem Office 365 E4-Abonnement zugeordnet sind, wie beispielsweise Office 365 zusätzlichen Dateispeicher werden ebenfalls aufgeführt. Wenn Sie jedoch über Add-on-Abonnements verfügen, die in dem Abonnement enthalten sind, auf das Sie ein Upgrade durchführen, werden wir Sie entfernen.
6. Nachdem Sie Ihre Bestellung überprüft haben, wählen Sie **Gehe zu Kasse**aus.
7. Überprüfen Sie auf der Seite zum **Auschecken** die **in dieser Reihenfolge** **verkaufte**, in **Rechnung**gestellten und die Elemente. Wählen Sie neben einem dieser Elemente **ändern** aus, um die Informationen zu bearbeiten.
    > [!NOTE]
    > Die Option zum Verwenden der Rechnung als Zahlungsmethode steht nur für Bestellungen zur Verfügung, die über einem bestimmten Kostenbetrag liegen. Durch Auswahl der Option "Rechnungszahlung" kann der Upgradeprozess um bis zu zwei Werktage verzögert werden, wenn eine Bonitätsprüfung erforderlich ist.
8. Wenn Sie fertig sind, wählen Sie **Bestellung aufgeben**aus.

> [!NOTE]
> Das Aktualisieren von Plänen dauert in der Regel weniger als zehn Minuten, wenn keine Fehler oder Probleme vorliegen. Sie können den Status Ihres Upgrades überprüfen, indem Sie entweder Ihr altes oder neues Abonnement betrachten.

## <a name="upgrade-your-plan-manually"></a>Manuelles Upgrade Ihres Plans

Führen Sie die folgenden Schritte in der angegebenen Reihenfolge aus, um Benutzer manuell auf ein anderes Abonnement zu aktualisieren.

- [Schritt 1: erwerben eines neuen Abonnements](#step-1-buy-a-new-subscription)
- [Schritt 2: überprüfen, ob Ihr Abonnement über die richtige Anzahl von Lizenzen verfügt](#step-2-verify-that-your-subscription-has-the-right-number-of-licenses)
- [Schritt 3: Zuweisen von Lizenzen zu Benutzern](#step-3-reassign-licenses-to-users)
- [Schritt 4: Abbrechen des Abonnements für Office 365 E4](#step-4-cancel-the-office-365-e4-subscription)

### <a name="step-1-buy-a-new-subscription"></a>Schritt 1: erwerben eines neuen Abonnements

Wenn Sie noch kein neues Abonnement haben, können Sie [ein weiteres Microsoft 365 for Business-Abonnement erwerben](../buy-another-subscription.md).

Wenn Sie bereits über ein Abonnement verfügen, fahren Sie mit dem nächsten Schritt fort.

### <a name="step-2-verify-that-your-subscription-has-the-right-number-of-licenses"></a>Schritt 2: überprüfen, ob Ihr Abonnement über die richtige Anzahl von Lizenzen verfügt

Bevor Sie mit dem nächsten Schritt fortfahren, müssen Sie unbedingt sicherstellen, dass alle Dienste in Ihrem neuen Abonnement eingerichtet wurden. Wenn das Abonnement bei der ersten Überprüfung nicht zur Verfügung steht, versuchen Sie es später erneut.

> [!NOTE]
> Wenn Sie das neue Abonnement per Rechnung bezahlen möchten, ist möglicherweise eine Bonitätsprüfung erforderlich. Es kann bis zu zwei Werktage dauern, bis das Abonnement verfügbar ist.

1. Wechseln Sie im Admin Center zur Seite **Fakturierung**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">ihrer Produkte</a> .
2. Wählen Sie in der Dropdownliste **Abonnementstatus** die Option **aktiv**aus.
3. Stellen Sie sicher, dass Ihr neues Abonnement angezeigt wird und dass die Anzahl der Lizenzen mit dem identisch ist, was Sie für Office 365 E4 hatten.
4. Wenn Sie weitere Lizenzen kaufen müssen, führen Sie die Schritte unter [kaufen oder Entfernen von Abonnementlizenzen](../licenses/buy-licenses.md)aus.

### <a name="step-3-reassign-licenses-to-users"></a>Schritt 3: Zuweisen von Lizenzen zu Benutzern

Sie können das Microsoft 365 Admin Center verwenden, um Lizenzen für bis zu 20 Benutzer gleichzeitig neu zuzuweisen. Weitere Informationen finden Sie unter [Migrieren von Benutzern zu einem anderen Abonnement](move-users-different-subscription.md).

> [!TIP]
> Wenn Sie viele Benutzer haben, können Sie [Office 365 PowerShell verwenden, um Benutzerlizenzen massenweise zuzuweisen](https://docs.microsoft.com/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell).

### <a name="step-4-cancel-the-office-365-e4-subscription"></a>Schritt 4: Abbrechen des Abonnements für Office 365 E4

Nachdem alle Ihre Benutzer Ihrem neuen Abonnement neu zugewiesen wurden, kündigen Sie [das Abonnement für Office 365 E4](cancel-your-subscription.md)an.

## <a name="related-content"></a>Verwandte Inhalte

[Upgrade auf einen anderen Plan](upgrade-to-different-plan.md) (Artikel) \
[Kaufen oder Entfernen von Abonnementlizenzen](../licenses/buy-licenses.md) (Artikel) \
[Zuweisen von Lizenzen zu Benutzern](../../admin/manage/assign-licenses-to-users.md) (Artikel)
