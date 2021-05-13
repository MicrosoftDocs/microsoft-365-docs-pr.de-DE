---
title: Upgrade von einem Office 365 E4-Abonnement
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
ms.reviewer: jkinma, jmueller
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- customer-email
- commerce_subscriptions
search.appverid: MET150
description: Erfahren Sie, wie Sie ein Upgrade von einem Office 365 E4-Abonnement durchführen.
ms.date: 08/14/2020
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: ee90038bb80120ed727cd2dee0c43a894053440f
ms.sourcegitcommit: 94e64afaf12f3d8813099d8ffa46baba65772763
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/12/2021
ms.locfileid: "52344626"
---
# <a name="upgrade-from-an-office-365-e4-subscription"></a>Upgrade von einem Office 365 E4-Abonnement

In diesem Artikel werden Sie durch den Prozess des Upgrades von einer Office 365 E4 auf ein neues Abonnement beschrieben. Informationen zu den verfügbaren Optionen beim Upgrade von Office 365 E4 finden Sie unter Wichtige Informationen für [Office 365 E4-Kunden](important-information-e4.md).

> [!IMPORTANT]
> Dieser Artikel gilt für Office 365 E4-Abonnements, die nur per Kreditkarte oder Rechnung direkt von Microsoft erworben wurden. Wenn Ihr Abonnement auf andere Weise erworben wurde, z. B. über einen Partner oder über das Volume Licensing Service Center, wenden Sie sich an Ihren Microsoft-Kontovertreter oder Partner, um Ihnen beim Upgrade von Plänen zu helfen.

## <a name="what-are-my-options-for-how-to-upgrade"></a>Was sind meine Optionen für das Upgrade?

Die einfachste Möglichkeit zum Aktualisieren Ihres Plans ist die Verwendung der Registerkarte **Upgrade** im Microsoft 365 Admin Center. Die Verwendung der Registerkarte **Upgrade** wird jedoch nicht in allen Situationen unterstützt. Wenn Ihr Szenario nicht unterstützt wird, können Sie pläne möglicherweise manuell aktualisieren.

## <a name="what-is-the-upgrade-tab"></a>Was ist die Registerkarte Upgrade?

Die **Registerkarte Upgrade** führt die folgenden Aufgaben für Sie aus:

- Er führt Sie durch das Verfahren zum Kauf eines neuen Plans.
- Er weist alle Benutzerlizenzen aus dem alten Plan dem neuen Plan zu.
- Er kündigt Ihren alten Plan.

## <a name="what-does-it-mean-to-upgrade-plans-manually"></a>Was bedeutet es, Pläne manuell zu aktualisieren?

Wenn Sie Pläne manuell aktualisieren, müssen Sie die folgenden separaten Verfahren ausführen, anstatt die Registerkarte **Upgrade zu** verwenden.

- Kaufen Sie ein neues Abonnement mit der richtigen Anzahl von Lizenzen.
- Überprüfen, ob das Abonnement einsatzbereit ist.
- Zuweisen von Lizenzen an Benutzer.
- Kündigen Des ursprünglichen Office 365 E4-Abonnements.

## <a name="find-out-if-you-can-use-the-upgrade-tab-to-upgrade-to-a-new-plan"></a>Erfahren Sie, ob Sie die Registerkarte Upgrade zum Upgrade auf einen neuen Plan verwenden können.

1. Navigieren Sie im Admin Center zur Seite **Abrechnung** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Ihre Produkte</a>.
2. Wählen Sie Office 365 E4-Abonnement aus.
3. Wählen Sie die **Registerkarte Upgrade** aus. Wenn andere Pläne aufgeführt sind, bedeutet dies, dass Sie Pläne automatisch aktualisieren können.
4. Wenn Sie nicht automatisch aktualisieren können, wird eine Meldung angezeigt, in der der Grund für das Nichtupgrade beschrieben wird.

Es gibt mehrere Gründe, warum Sie Pläne nicht automatisch aktualisieren können. Die meisten der Probleme sind vorübergehender Natur, wie Probleme mit dem Dienststatus, die Sie beheben können. Weitere Informationen finden Sie unter [Why can't I upgrade plans?](upgrade-to-different-plan.md#why-cant-i-upgrade-plans) Wenn Sie Hilfe bei Ihrem Upgrade benötigen, wenden Sie [sich an den Support.](../../business-video/get-help-support.md)

## <a name="will-a-credit-check-be-required"></a>Ist eine Kreditwürdigkeitsprüfung erforderlich?

Wenn Sie ihren neuen Plan per Rechnung bezahlen oder Ihr Kauf über bestimmten Kosten liegt, ist möglicherweise eine Kreditwürdigkeitsprüfung erforderlich. Wenn eine Kreditwürdigkeitsprüfung erforderlich ist, kann das Upgrade bis zu zwei Werktage dauern. Administratoren haben keinen Zugriff auf das Microsoft 365 Admin Center, bis die Kreditwürdigkeitsprüfung abgeschlossen ist. Benutzer haben jedoch weiterhin vollzugriff auf den E4-Plan, bis das Upgrade abgeschlossen ist.

## <a name="upgrade-your-plan-by-using-the-upgrade-tab"></a>Aktualisieren Ihres Plans mithilfe der Registerkarte Upgrade

### <a name="before-you-begin"></a>Vorabinformationen

Hier einige wichtige Informationen, die Sie kennen sollten, bevor Sie die ersten Schritte unternehmen.

- **Planen von administrativen Ausfallzeiten.** Administratoren können das Microsoft 365 Admin Center nicht verwenden, während der Plan aktualisiert wird. Je nach Anzahl der Benutzer kann das Upgrade minuten- bis stundenlang dauern. Es wird empfohlen, das Upgrade zu planen, wenn Sie keine Updates mithilfe des Microsoft 365 müssen.

    Während des Upgrades des Plans kommt es zu keinen Dienstunterbrechungen für Benutzer – während des Upgradeprozesses haben sie weiterhin Vollzugriff auf das E4-Abonnement. Nach Abschluss des Upgrades haben Benutzer Zugriff auf den neuen Plan.
- **Benutzer, Lizenzen, Abrechnung und benutzerdefinierte Domänen.** Informationen zur Handhabung von Benutzern und Lizenzen während des Upgrades, zu den Auswirkungen von Upgradeplänen auf Ihre Abrechnung und zur Handhabung benutzerdefinierter Domänen finden Sie unter Was bedeutet das Upgrade eines Plans für meinen Dienst und die [Abrechnung?](upgrade-to-different-plan.md#what-does-upgrading-a-plan-do-to-my-service-and-billing)
- **Ändern Sie die Anzahl der Benutzerlizenzen.** Lizenzen können im Rahmen von Upgradeplänen nicht entfernt werden. Sie können jedoch die [Anzahl der Lizenzen](../licenses/buy-licenses.md) vor oder nach dem Upgrade von Plänen reduzieren.

### <a name="start-the-upgrade-by-using-the-upgrade-tab"></a>Starten des Upgrades mithilfe der Registerkarte Upgrade

1. Navigieren Sie im Admin Center zur Seite **Abrechnung** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Ihre Produkte</a>.
2. Wählen Sie Office 365 E4-Abonnement aus.
3. Wählen Sie auf der Seite Abonnementdetails die Registerkarte **Upgrade** aus.
4. Suchen Sie das Abonnement, das Sie kaufen möchten, und wählen Sie dann **Upgrade aus.**
5. Überprüfen Sie **auf** der Seite Einkaufswagen, ob alles korrekt ist. Wählen Sie aus, ob monatlich oder jährlich bezahlt werden soll, und überprüfen Sie die Anzahl der Lizenzen unter **Menge**.
    > [!NOTE]
    > Alle Add-On-Abonnements, die Ihrem Office 365 E4-Abonnement zugeordnet sind, z. B. Office 365 Zusätzliche Datei Storage werden ebenfalls aufgeführt. Wenn Sie jedoch über Add-On-Abonnements verfügen, die in dem Abonnement enthalten sind, auf das Sie ein Upgrade durchführen, entfernen wir sie.
6. Nachdem Sie Ihre Bestellung überprüft haben, wählen Sie **Zum Auschecken wechseln aus.**
7. Überprüfen Sie auf der **Seite** Auschecken die Informationen **Verkauft an**, In **Rechnungen** und **Elemente in dieser Reihenfolge**. Wählen **Sie Neben** einem dieser Elemente ändern aus, um die Informationen zu bearbeiten.
    > [!NOTE]
    > Die Option, Rechnung als Zahlungsmethode zu verwenden, ist nur für Bestellungen verfügbar, die über einem bestimmten Kostenbetrag liegen. Wenn Sie die Zahlungsoption für Rechnungen auswählen, kann der Upgradevorgang um bis zu zwei Werktage verzögert werden, wenn eine Kreditwürdigkeitsprüfung erforderlich ist.
8. Wenn Sie fertig sind, wählen Sie **Bestellung platzieren aus.**

> [!NOTE]
> Das Upgrade von Plänen dauert in der Regel weniger als zehn Minuten, wenn keine Fehler oder Probleme auftreten. Sie können den Status Ihres Upgrades überprüfen, indem Sie sich entweder Ihr altes oder neues Abonnement anzeigen.

## <a name="upgrade-your-plan-manually"></a>Manuelles Upgrade Des Plans

Führen Sie zum manuellen Upgrade von Benutzern auf ein anderes Abonnement die folgenden Schritte in der angezeigten Reihenfolge aus.

- [Schritt 1: Kaufen eines neuen Abonnements](#step-1-buy-a-new-subscription)
- [Schritt 2: Überprüfen, ob Ihr Abonnement über die richtige Anzahl von Lizenzen verfügt](#step-2-verify-that-your-subscription-has-the-right-number-of-licenses)
- [Schritt 3: Erneutes Zuweisen von Lizenzen an Benutzer](#step-3-reassign-licenses-to-users)
- [Schritt 4: Kündigen des Office 365 E4-Abonnements](#step-4-cancel-the-office-365-e4-subscription)

### <a name="step-1-buy-a-new-subscription"></a>Schritt 1: Kaufen eines neuen Abonnements

Wenn Sie noch kein neues Abonnement haben, können Sie ein Microsoft 365 [business-Abonnement erwerben.](../try-or-buy-microsoft-365.md)

Wenn Sie bereits über ein Abonnement verfügen, fahren Sie mit dem nächsten Schritt fort.

### <a name="step-2-verify-that-your-subscription-has-the-right-number-of-licenses"></a>Schritt 2: Überprüfen, ob Ihr Abonnement über die richtige Anzahl von Lizenzen verfügt

Bevor Sie mit dem nächsten Schritt fort gehen, müssen Sie sicherstellen, dass alle Dienste in Ihrem neuen Abonnement eingerichtet wurden. Wenn das Abonnement beim ersten Überprüfen nicht bereit ist, versuchen Sie es später erneut.

> [!NOTE]
> Wenn Sie das neue Abonnement per Rechnung bezahlen möchten, ist möglicherweise eine Kreditwürdigkeitsprüfung erforderlich. Es kann bis zu zwei Werktage dauern, bis das Abonnement verfügbar ist.

1. Navigieren Sie im Admin Center zur Seite **Abrechnung** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Ihre Produkte</a>.
2. Wählen Sie **in der Dropdownliste** Abonnementstatus die Option **Aktiv aus.**
3. Stellen Sie sicher, dass Ihr neues Abonnement angezeigt wird und dass die Anzahl der Lizenzen mit der Anzahl der Lizenzen für E4 Office 365 ist.
4. Wenn Sie weitere Lizenzen kaufen müssen, führen Sie die Schritte unter [Kaufen oder Entfernen von Abonnementlizenzen aus.](../licenses/buy-licenses.md)

### <a name="step-3-reassign-licenses-to-users"></a>Schritt 3: Erneutes Zuweisen von Lizenzen an Benutzer

Sie können das Microsoft 365 Admin Center verwenden, um Lizenzen für bis zu 20 Benutzer gleichzeitig neu zuzuweisen. Weitere Informationen finden Sie unter [Verschieben von Benutzern in ein anderes Abonnement](move-users-different-subscription.md).

> [!TIP]
> Wenn Sie über viele Benutzer verfügen, können Sie Office 365 PowerShell verwenden, um [Benutzerlizenzen in Massen zuzuordnen.](../../enterprise/assign-licenses-to-user-accounts-with-microsoft-365-powershell.md)

### <a name="step-4-cancel-the-office-365-e4-subscription"></a>Schritt 4: Kündigen des Office 365 E4-Abonnements

Nachdem alle Ihre Benutzer ihrem neuen Abonnement zugewiesen wurden, kündigen Sie das [Office 365 E4-Abonnement.](cancel-your-subscription.md)

## <a name="related-content"></a>Verwandte Inhalte

[Upgrade auf einen anderen Plan](upgrade-to-different-plan.md) (Artikel)\
[Kaufen oder Entfernen von Abonnementlizenzen](../licenses/buy-licenses.md) (Artikel)\
[Zuweisen von Lizenzen zu Benutzern](../../admin/manage/assign-licenses-to-users.md) (Artikel)
