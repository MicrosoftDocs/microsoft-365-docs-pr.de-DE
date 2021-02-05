---
title: Verwalten von Zahlungsmethoden
f1.keywords:
- CSH
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
- Adm_TOC
- commerce
ms.custom:
- TopSMBIssues
- okr_SMB
- AdminSurgePortfolio
search.appverid:
- MET150
description: Erfahren Sie, wie Sie Ihre Zahlungsmethoden im Microsoft 365 Admin Center verwalten.
ms.date: ''
ms.openlocfilehash: 6cba5e33ba99212cb6e67a90d1535120ccac3c38
ms.sourcegitcommit: 0d709e9ab0d8d56c5fc11a921298f82e40e122c5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/05/2021
ms.locfileid: "50114849"
---
# <a name="manage-payment-methods"></a>Verwalten von Zahlungsmethoden

::: moniker range="o365-21vianet"
> [!NOTE]
> Das Admin Center wird geändert. Wenn Ihre Erfahrung nicht den hier aufgeführten Details entspricht, lesen Sie [über das neue Microsoft 365 Admin Center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true).
::: moniker-end

Wenn Sie Geschäftsprodukte oder -dienste von Microsoft kaufen, können Sie eine vorhandene Zahlungsmethode verwenden oder eine neue Zahlungsmethode hinzufügen. Sie können eine Kredit- oder Debitkarte oder ein Bankkonto verwenden, um die gekauften Dinge zu bezahlen.

Wenn Ihr Geschäftskonto über ein Abrechnungsprofil verfügt und Sie ein Abrechnungsprofilbesitzer oder Mitwirkender des Abrechnungsprofils sind, können Sie das Abrechnungsprofil verwenden, das durch eine Kreditkarte oder Rechnungszahlung gesichert ist, um Einkäufe zu tätigen oder Rechnungen zu bezahlen. Wenn Sie ein Rechnungsmanager sind, können Sie nur ein Abrechnungsprofil zum Bezahlen von Rechnungen verwenden. Weitere Informationen zu Abrechnungsprofilen und -rollen finden Sie unter ["Verwalten von Abrechnungsprofilen".](manage-billing-profiles.md)

Wenn Ihr Geschäftskonto kein Abrechnungsprofil hat, kann jeder globale Administrator oder Abrechnungsadministrator ein beliebiges Bankkonto verwalten und verwenden, das dem Geschäftskonto hinzugefügt wurde. Sie können jedoch nur Kreditkarten verwalten oder verwenden, die Sie hinzufügen.

> [!NOTE]
> Die Option zum Bezahlen mit einem Bankkonto ist in einigen Ländern oder Regionen nicht verfügbar.
>
> Sie müssen eine Zahlungsmethode verwenden, die aus demselben Land wie Ihr Mandant ausgestellt wurde.

## <a name="before-you-begin"></a>Vorabinformationen

Sie müssen ein globaler Administrator oder Abrechnungsadministrator sein, um die Aufgaben in diesem Artikel ausführen zu können. Weitere Informationen finden Sie unter [Informationen zu Administratorrollen](../../admin/add-users/about-admin-roles.md).

## <a name="add-a-payment-method"></a>Zahlungsmethode hinzufügen

Durch das Hinzufügen einer Zahlungsmethode werden ihr keine Abonnements zugeordnet. Informationen zum Zuweisen eines einzelnen Abonnements zur Zahlungsmethode finden Sie unter [Ändern einer Zahlungsmethode für ein einzelnes Abonnement.](#change-a-payment-method-for-a-single-subscription) Informationen zum Ersetzen aller Abonnements, die eine andere Zahlungsmethode verwenden, finden Sie unter ["Ersetzen einer Zahlungsmethode".](#replace-a-payment-method)

1. Navigieren Sie im Admin Center zur Seite **Abrechnung** > **Rechnungen und Zahlungen** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2018806" target="_blank">Zahlungsmethoden</a>.
2. Wählen Sie **Zahlungsmethode hinzufügen** aus.
3. Wählen Sie auf der Seite **Zahlungsmethoden** im Dropdownmenü eine Zahlungsmethode aus.
4. Geben Sie die Informationen für die neue Karte oder das Bankkonto ein, und wählen Sie dann **"Hinzufügen" aus.**

## <a name="update-payment-method-details"></a>Zahlungsmethodendetails aktualisieren

Sie können den Namen auf der Kredit- oder Debitkarte, der Rechnungsadresse oder dem Ablaufdatum für eine vorhandene Zahlungsmethode ändern. Sie können die Karte oder Kontonummer jedoch nicht ändern. Wenn sich die Kontonummer geändert hat, ersetzen Sie sie [durch](#replace-a-payment-method)eine andere Zahlungsmethode, und löschen Sie dann [die alte.](#delete-a-payment-method)

1. Navigieren Sie im Admin Center zur Seite **Abrechnung** > **Rechnungen und Zahlungen** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2018806" target="_blank">Zahlungsmethoden</a>.
2. Wählen Sie die Zeile der Zahlungsmethode aus, die aktualisiert werden soll. Wählen Sie im rechten Bereich die Option **Bearbeiten** aus.
3. Aktualisieren Sie Ihre Angaben zur Zahlungsmethode, einschließlich des Namens auf der Kredit- oder Debitkarte, der Rechnungsadresse oder des Ablaufdatums, und wählen Sie dann **Speichern** aus.

## <a name="replace-a-payment-method"></a>Zahlungsmethode ersetzen

Wenn Sie eine Zahlungsmethode ersetzen, ersetzen Sie sie für alle Abonnements und Abrechnungsprofile, die dieselbe Zahlungsmethode verwenden. Durch das Ersetzen einer Zahlungsmethode wird die vorhandene Zahlungsmethode nicht gelöscht. Es steht Ihnen weiterhin zur Auswahl und Verwendung für andere Abonnements und Abrechnungsprofile zur Verfügung.

Informationen zum Ändern der Zahlungsmethode für ein einzelnes Abonnement finden Sie unter [Ändern einer Zahlungsmethode für ein einzelnes Abonnement.](#change-a-payment-method-for-a-single-subscription)

1. Navigieren Sie im Admin Center zur Seite **Abrechnung** > **Rechnungen und Zahlungen** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2018806" target="_blank">Zahlungsmethoden</a>.
2. Wählen Sie die Zeile der Zahlungsmethode aus, die ersetzt werden soll. Im rechten Bereich werden alle Abrechnungsprofile und einzelne Abonnements mit der ausgewählten Zahlungsmethode aufgelistet.
3. Wählen Sie im rechten Bereich **Zahlungsmethode für alle Elemente ersetzen** aus.
4. Wenn Sie eine vorhandene Zahlungsmethode verwenden möchten, wählen Sie in der Dropdownliste eine aus und wählen Sie dann **Ersetzen**.
    > [!NOTE]
    > Wenn Sie Abonnements haben, die mit einem Abrechnungsprofil verknüpft sind, können Sie diese nur mit einer Kredit- oder Debitkarte bezahlen. Wenn Sie auf der Seite **Zahlungsmethoden** Bankkonten aufgelistet haben, können diese in der Dropdownliste nicht ausgewählt werden.
5. Wenn Sie eine neue Zahlungsmethode hinzufügen möchten, wählen Sie **Zahlungsmethode hinzufügen** aus.
6. Geben Sie im Bereich **Zahlungsmethode hinzufügen** die Kontoinformationen ein und wählen Sie dann **Speichern** aus. Sie müssen eine Zahlungsmethode aus dem gleichen Land wie Ihr Mandant verwenden.
7. Die neue Zahlungsmethode ist bereits in der Dropdownliste ausgewählt. Wählen Sie **Ersetzen**.

## <a name="change-a-payment-method-for-a-single-subscription"></a>Ändern einer Zahlungsmethode für ein einzelnes Abonnement

Sie können die Zahlungsmethode ändern, die zum Bezahlen eines einzelnen Abonnements verwendet wird.

1. Navigieren Sie im Admin Center zur Seite **Abrechnung** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Ihre Produkte</a>.
2. Suchen Sie **auf** der Registerkarte "Produkte" das Abonnement, für das Sie mit der alternativen Zahlungsmethode bezahlen möchten.
3. Wählen **Sie "Weitere Aktionen"** (drei Punkte) und dann **"Zahlungsmethode ersetzen" aus.**
4. Wählen Sie **im Bereich** Zahlungsmethode ersetzen in der Dropdownliste eine alternative Zahlungsmethode aus, oder fügen Sie eine Zahlungsmethode hinzu.
5. Wenn Sie eine Zahlungsmethode hinzufügen, geben Sie die Karten- oder Kontodetails ein, und wählen Sie "Speichern" **aus.**
6. Stellen Sie sicher, dass die ausgewählte Zahlungsmethode korrekt ist, und wählen Sie **"Ersetzen" aus.**

## <a name="delete-a-payment-method"></a>Zahlungsmethode löschen

Sie können nur eine Zahlungsmethode löschen, die keinem Abonnement oder Abrechnungsprofil zugeordnet ist. Dies gilt für alle Abonnements, unabhängig von ihrem Status.

### <a name="delete-a-payment-method-with-no-subscriptions-or-billing-profiles-attached"></a>Löschen einer Zahlungsmethode ohne zugeordnete Abonnements oder Abrechnungsprofile

Wenn eine Zahlungsmethode keinem Abonnement oder Abrechnungsprofil zugeordnet ist, können Sie sie sofort löschen.

1. Navigieren Sie im Admin Center zur Seite **Abrechnung** > **Rechnungen und Zahlungen** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2018806" target="_blank">Zahlungsmethoden</a>.
2. Suchen Sie die Zahlungsmethode, die Sie löschen möchten, wählen Sie die drei Punkte aus, und wählen Sie dann **"Löschen" aus.**
3. Wählen Sie unten im rechten Bereich **"Löschen" aus.**

### <a name="delete-a-payment-method-with-subscriptions-or-billing-profiles-attached"></a>Löschen einer Zahlungsmethode mit angefügten Abonnements oder Abrechnungsprofilen

Wenn eine Zahlungsmethode an Abonnements oder Abrechnungsprofile angefügt ist, ersetzen Sie sie zuerst durch eine vorhandene Zahlungsmethode, oder fügen Sie eine neue hinzu, und löschen Sie dann die alte Zahlungsmethode.

1. Navigieren Sie im Admin Center zur Seite **Abrechnung** > **Rechnungen und Zahlungen** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2018806" target="_blank">Zahlungsmethoden</a>.
2. Wählen Sie die Zeile für die zu löschende Zahlungsmethode aus. Im rechten Bereich sind vorhandene Abonnements aufgeführt, die diese Zahlungsmethode verwenden.
3. Wählen Sie im rechten Bereich **"Löschen" aus.**
4. Wenn Sie eine vorhandene Zahlungsmethode verwenden möchten, wählen Sie eine aus der Dropdownliste aus, wählen Sie **"Weiter"** und dann **"Löschen" aus.**
    > [!NOTE]
    > Wenn Einem Abrechnungsprofil Abonnements zugeordnet sind, können Sie diese nur mit einer Kreditkarte bezahlen. Wenn Auf der Seite  Zahlungsmethoden Bankkonten aufgeführt sind, stehen diese nicht zur Auswahl in der Dropdownliste zur Verfügung.
5. Wenn Sie eine neue Zahlungsmethode hinzufügen möchten, wählen Sie **Zahlungsmethode hinzufügen** aus.
6. Wählen Sie den Typ der Zahlungsmethode aus, die Sie hinzufügen möchten, geben Sie die Kontoinformationen ein, und wählen Sie dann "Speichern" **aus.**
7. Die neue Zahlungsmethode ist bereits in der Dropdownliste ausgewählt. Wählen Sie **Weiter** aus.
8. Wählen Sie **Löschen** aus.

## <a name="troubleshoot-payment-methods"></a>Behandlung von Problemen mit Zahlungsmethoden

| Problem | Schritte zur Problembehandlung |
|:----------|:-----|
|**Es wird eine Fehlermeldung angezeigt, die lautet: "Der Browser ist derzeit so eingestellt, dass Cookies blockiert werden."** |Konfigurieren Sie Ihren Browser so, dass er Cookies von Drittanbietern zulässt, und versuchen Sie es dann erneut. |
|**Meine Kredit- oder Debitkarte wurde abgelehnt.** |Wenn Sie per Kredit- oder Debitkarte bezahlen und Ihre Karte abgelehnt wird, erhalten Sie eine E-Mail, dass Microsoft die Zahlung nicht verarbeiten konnte. Überprüfen Sie, ob die Kartendetailsekartennummer, das Ablaufdatum, der Name auf der Karte und die Adresse, einschließlich Ort, Bundesland und Postleitzahl, genau so angezeigt werden, wie auf der Karte und In-Mail-Anweisung. &mdash; &mdash; Sie können Ihre Karteninformationen aktualisieren und die  Zahlung sofort  übermitteln, indem Sie den Link "Saldo ausgleichen" im Abschnitt "Abrechnung" der Seite mit den Abonnementdetails verwenden. Weitere Informationen finden Sie unter [What if I have an outstanding balance?](pay-for-your-subscription.md#what-if-i-have-an-outstanding-balance)  <br/><br/>  Wenn die Kreditkarte dann immer noch abgelehnt wird, wenden Sie sich an Ihre Bank. Es ist möglich, dass Ihre Karte nicht aktiv ist. Wenn Sie die Karte kürzlich in der E-Mail mit einem aktualisierten Ablaufdatum erhalten haben, stellen Sie sicher, dass sie aktiviert ist. Ihre Bank kann Ihnen auch mitteilen, ob Ihre Karte nicht für Online-, internationale oder wiederkehrende Transaktionen genehmigt wurde. |
|**Ich möchte eine Karte oder Bankkontonummer aktualisieren.** |Sie können die Karte oder Kontonummer einer vorhandenen Zahlungsmethode nicht ändern. Wenn Sich Ihre Karte oder Kontonummer geändert [hat,](#replace-a-payment-method)ersetzen Sie sie durch eine andere Zahlungsmethode, die alle aktiven Abonnements von der Zahlungsmethode in die neue verschiebt, und löschen Sie dann die alte [Zahlungsmethode.](#delete-a-payment-method-with-no-subscriptions-or-billing-profiles-attached) |
|**Ich habe nur eine Karte oder ein Bankkonto auf meinem Konto und möchte sie entfernen.** |Wenn Sie nur über eine Zahlungsmethode verfügen, müssen Sie sie durch eine neue [Zahlungsmethode](#replace-a-payment-method) ersetzen, bevor Sie sie löschen können. |
|**Ich kann meine Karte oder mein Bankkonto nicht hinzufügen.**  |Sie müssen eine Zahlungsmethode verwenden, die aus demselben Land wie Ihr Mandant ausgestellt wurde. Wenn Sie Probleme beim Eingeben Ihrer Karten- oder Bankkontoinformationen haben, können Sie sich [an den Support wenden.](../../admin/contact-support-for-business-products.md) |

## <a name="related-content"></a>Verwandte Inhalte

[Bezahlen Für Ihr Geschäftsabonnement](pay-for-your-subscription.md) (Artikel)\
[Verwalten von Abrechnungsprofilen](manage-billing-profiles.md) (Artikel)\
[Ändern der Abrechnungshäufigkeit](change-payment-frequency.md) (Artikel)
