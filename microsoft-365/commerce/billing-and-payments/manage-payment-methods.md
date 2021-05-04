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
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- TopSMBIssues
- okr_SMB
- AdminSurgePortfolio
- commerce_billing
- PPM_jmueller
ms.reviewer: jamitche
search.appverid:
- MET150
description: Hier erfahren Sie, wie Sie Ihre Zahlungsmethoden im Microsoft 365 Admin Center verwalten können.
ms.date: 04/02/2021
ms.openlocfilehash: 4b35b7b8e874915e5f9c792686ff0e368292c802
ms.sourcegitcommit: 794f9767aaebe13ab1aead830b214ea674289d19
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/30/2021
ms.locfileid: "52107039"
---
# <a name="manage-payment-methods"></a>Verwalten von Zahlungsmethoden

Wenn Sie Business-Produkte oder -Dienste von Microsoft kaufen, können Sie eine vorhandene Zahlungsmethode verwenden oder eine neue hinzufügen. Die Bezahlung von gekauften Produkten kann über eine Kreditkarte, eine Debitkarte oder ein Bankkonto erfolgen.

Wenn Ihr Geschäftskonto über ein Abrechnungsprofil verfügt und Sie Besitzer oder Mitwirkender an dem Abrechnungsprofil sind, können Sie über das Abrechnungsprofil, das durch eine Kreditkarte oder Zahlung per Rechnung abgesichert ist, Einkäufe tätigen oder Rechnungen bezahlen. Wenn Sie Rechnungsadministrator sind, können Sie zum Bezahlen von Rechnungen nur ein Abrechnungsprofil verwenden. Weitere Informationen zu Abrechnungsprofilen und Rollen finden Sie unter [Verwalten von Abrechnungsprofilen](manage-billing-profiles.md).

Wenn Ihr Geschäftskonto nicht über ein Abrechnungsprofil verfügt, kann jeder globale oder Rechnungsadministrator jedes Bankkonto verwalten und verwenden, das dem Geschäftskonto hinzugefügt wurde. Sie können hingegen nur Kreditkarten verwalten oder verwenden, die Sie hinzufügen.

> [!NOTE]
> Die Option zum Bezahlen über ein Bankkonto ist in einigen Ländern oder Regionen nicht verfügbar.
>
> Sie müssen eine Zahlungsmethode verwenden, die im Land Ihres Mandanten ausgestellt wurde.

## <a name="before-you-begin"></a>Bevor Sie beginnen

Sie müssen ein globaler oder ein Rechnungsadministrator sein, um die in diesem Artikel beschriebenen Schritte durchführen zu können. Weitere Informationen finden Sie unter [Informationen zu Administratorrollen](../../admin/add-users/about-admin-roles.md).

## <a name="add-a-payment-method"></a>Eine Zahlungsmethode hinzufügen

Durch das Hinzufügen einer Zahlungsmethode werden dieser keine Abonnements zugeordnet. Informationen dazu, wie Sie ein einzelnes Abonnement einer Zahlungsmethode zuordnen können, finden Sie unter [Ändern der Zahlungsmethode für ein einzelnes Abonnement](#change-a-payment-method-for-a-single-subscription). Wenn Sie für alle Abonnements, für die eine andere Zahlungsmethode verwendet wird, die neue verwenden möchten, lesen Sie [Ersetzen einer Zahlungsmethode](#replace-a-payment-method).

1. Navigieren Sie im Admin Center zur Seite **Abrechnung** > **Rechnungen und Zahlungen** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2018806" target="_blank">Zahlungsmethoden</a>.
2. Wählen Sie **Zahlungsmethode hinzufügen** aus.
3. Wählen Sie auf der Seite **Zahlungsmethoden** im Dropdownmenü eine Zahlungsmethode aus.
4. Geben Sie die Informationen für die neue Kreditkarte oder das Bankkonto ein, und wählen Sie **Hinzufügen** aus.

## <a name="update-payment-method-details"></a>Aktualisieren von Zahlungsmethodendetails

Sie können den Namen auf der Kreditkarte oder der Debitkarte, die Rechnungsadresse oder das Ablaufdatum für eine bestehende Zahlungsmethode ändern. Sie können jedoch nicht die Karten- oder Kontonummer ändern. Wenn sich die Kontonummer geändert hat, [ersetzen Sie diese durch eine andere Zahlungsmethode](#replace-a-payment-method), und [löschen Sie dann die alte](#delete-a-payment-method).

1. Navigieren Sie im Admin Center zur Seite **Abrechnung** > **Rechnungen und Zahlungen** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2018806" target="_blank">Zahlungsmethoden</a>.
2. Wählen Sie die Zeile der Zahlungsmethode aus, die aktualisiert werden soll. Wählen Sie im rechten Bereich die Option **Bearbeiten** aus.
3. Aktualisieren Sie Ihre Angaben zur Zahlungsmethode, einschließlich des Namens auf der Kredit- oder Debitkarte, der Rechnungsadresse oder des Ablaufdatums, und wählen Sie dann **Speichern** aus.

## <a name="replace-a-payment-method"></a>Eine Zahlungsmethode ersetzen

Wenn Sie eine Zahlungsmethode ersetzen, ersetzen Sie sie für alle Abonnements und Abrechnungsprofile, für die dieselbe Zahlungsmethode verwendet wird. Durch das Ersetzen einer Zahlungsmethode wird die vorhandene Zahlungsmethode nicht gelöscht. Sie steht weiterhin zur Auswahl und kann für andere Abonnements und Abrechnungsprofile verwendet werden.

Informationen zum Ändern der Zahlungsmethode für ein einzelnes Abonnement finden Sie unter [Ändern der Zahlungsmethode für ein einzelnes Abonnement](#change-a-payment-method-for-a-single-subscription).

1. Navigieren Sie im Admin Center zur Seite **Abrechnung** > **Rechnungen und Zahlungen** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2018806" target="_blank">Zahlungsmethoden</a>.
2. Wählen Sie die Zeile der Zahlungsmethode aus, die ersetzt werden soll. Im rechten Bereich werden alle Abrechnungsprofile und einzelne Abonnements mit der ausgewählten Zahlungsmethode aufgelistet.
3. Wählen Sie im rechten Bereich **Zahlungsmethode für alle Elemente ersetzen** aus.
4. Wenn Sie eine vorhandene Zahlungsmethode verwenden möchten, wählen Sie in der Dropdownliste eine aus und wählen Sie dann **Ersetzen**.
    > [!NOTE]
    > Wenn Sie Abonnements haben, die mit einem Abrechnungsprofil verknüpft sind, können Sie diese nur mit einer Kredit- oder Debitkarte bezahlen. Wenn Sie auf der Seite **Zahlungsmethoden** Bankkonten aufgelistet haben, können diese in der Dropdownliste nicht ausgewählt werden.
5. Wenn Sie eine neue Zahlungsmethode hinzufügen möchten, wählen Sie **Zahlungsmethode hinzufügen** aus.
6. Geben Sie im Bereich **Zahlungsmethode hinzufügen** die Kontoinformationen ein und wählen Sie dann **Speichern** aus. Sie müssen eine Zahlungsmethode aus dem gleichen Land wie Ihr Mandant verwenden.
7. Die neue Zahlungsmethode ist bereits in der Dropdownliste ausgewählt. Wählen Sie **Ersetzen**.

## <a name="change-a-payment-method-for-a-single-subscription"></a>Ändern der Zahlungsmethode für ein einzelnes Abonnement

Sie können die Zahlungsmethode ändern, die zur Bezahlung für ein einzelnes Abonnement verwendet wird.

1. Navigieren Sie im Admin Center zur Seite **Abrechnung** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Ihre Produkte</a>.
2. Suchen Sie auf der Registerkarte **Produkte** das Abonnement, für das Sie mit der alternativen Zahlungsmethode bezahlen möchten.
3. Wählen Sie **Weitere Aktionen** (drei Punkte) und dann **Zahlungsmethode ersetzen** aus.
4. Wählen Sie im Bereich **Zahlungsmethode ersetzen** in der Dropdownliste eine alternative Zahlungsmethode aus, oder fügen Sie eine Zahlungsmethode hinzu.
5. Wenn Sie eine Zahlungsmethode hinzufügen, geben Sie die Kreditkarte oder die Kontodetails ein, und wählen Sie dann **Speichern** aus.
6. Überprüfen Sie, ob die ausgewählte Zahlungsmethode korrekt ist, und klicken Sie dann auf **Ersetzen**.

## <a name="delete-a-payment-method"></a>Eine Zahlungsmethode löschen

Sie können nur eine Zahlungsmethode löschen, die nicht an ein Abonnement oder Abrechnungsprofil geknüpft ist. Dies gilt für alle Abonnements und unabhängig von deren Status.

### <a name="delete-a-payment-method-with-no-subscriptions-or-billing-profiles-attached"></a>Löschen einer Zahlungsmethode ohne verknüpfte Abonnements oder Abrechnungsprofile

Wenn eine Zahlungsmethode keinem Abonnement oder Abrechnungsprofil zugeordnet ist, können Sie diese sofort löschen.

1. Navigieren Sie im Admin Center zur Seite **Abrechnung** > **Rechnungen und Zahlungen** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2018806" target="_blank">Zahlungsmethoden</a>.
2. Suchen Sie die zu löschende Zahlungsmethode, klicken Sie auf die drei Punkte und dann auf **Löschen**.
3. Klicken Sie unten im rechten Bereich auf **Löschen**.

### <a name="delete-a-payment-method-with-subscriptions-or-billing-profiles-attached"></a>Löschen einer Zahlungsmethode mit verknüpften Abonnements oder Abrechnungsprofilen

Wenn einer Zahlungsmethode Abonnements oder Abrechnungsprofile zugeordnet sind, ersetzen Sie sie zunächst durch eine bestehende Zahlungsmethode, oder fügen Sie eine neue hinzu, und löschen Sie dann die alte Zahlungsmethode.

1. Navigieren Sie im Admin Center zur Seite **Abrechnung** > **Rechnungen und Zahlungen** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2018806" target="_blank">Zahlungsmethoden</a>.
2. Wählen Sie die Zeile der Zahlungsmethode aus, die gelöscht werden soll. Im rechten Bereich sind Abonnements aufgeführt, für die diese Zahlungsmethode verwendet wird.
3. Klicken Sie im rechten Bereich auf **Löschen**.
4. Wenn Sie eine vorhandene Zahlungsmethode verwenden möchten, wählen Sie diese in der Dropdownliste aus, klicken Sie dann auf **Weiter** und anschließend auf **Löschen**.
    > [!NOTE]
    > Wenn mit einem Abrechnungsprofil Abonnements verknüpft sind, können Sie diese nur mit einer Kreditkarte bezahlen. Wenn auf der Seite **Zahlungsmethoden** Bankkonten aufgeführt sind, können diese in der Dropdownliste nicht ausgewählt werden.
5. Wenn Sie eine neue Zahlungsmethode hinzufügen möchten, klicken Sie auf **Zahlungsmethode hinzufügen**.
6. Wählen Sie die Zahlungsmethode aus, die Sie hinzufügen möchten, geben Sie die Kontoinformationen ein, und klicken Sie dann auf **Speichern**.
7. Die neue Zahlungsmethode ist bereits in der Dropdownliste ausgewählt. Klicken Sie auf **Weiter**.
8. Klicken Sie auf **Löschen**.

## <a name="troubleshoot-payment-methods"></a>Behandlung von Problemen mit Zahlungsmethoden

| Problem | Schritte zur Problembehandlung |
|:----------|:-----|
|**Ich erhalte eine Fehlermeldung, die Folgendes besagt: "In Ihrem Browser werden Cookies derzeit blockiert."** |Konfigurieren Sie Ihren Browser so, dass er Cookies von Drittanbietern zulässt, und versuchen Sie es dann erneut. |
|**Meine Debit- oder Kreditkarte wurde abgelehnt.** |Wenn Sie mit Debit- oder Kreditkarte bezahlen und Ihre Karte wird abgelehnt, erhalten Sie eine E-Mail, in der Sie darüber informiert werden, dass Microsoft die Zahlung nicht verarbeitet konnte. Prüfen Sie zunächst sorgfältig, ob Sie die Kartendetails &mdash; Nummer, Ablaufdatum, Name des Karteninhabers und Adresse einschließlich Ort, Bundesland und PLZ &mdash; genau so angegeben haben, wie sie auf der Karte und auf der Abrechnung aufgeführt sind. Sie können Ihre Karteninformationen aktualisieren und die Zahlung sofort senden, indem Sie auf den Link **Saldo ausgleichen** im Abschnitt **Abrechnung** der Seite mit den Abonnementdetails klicken. Weitere Informationen finden Sie unter [Was passiert, wenn noch eine Saldoforderung besteht?](pay-for-your-subscription.md#what-if-i-have-an-outstanding-balance)  <br/><br/>  Wenn die Kreditkarte dann immer noch abgelehnt wird, wenden Sie sich an Ihre Bank. Es ist möglich, dass Ihre Kreditkarte nicht aktiv ist. Wenn Sie die Karte mit einem aktualisierten Ablaufdatum vor Kurzem per Post erhalten haben, müssen Sie sicherstellen, dass sie aktiviert ist. Ihre Bank kann Ihnen ebenfalls mitteilen, ob Ihre Kreditkarte für Online-, internationale oder wiederkehrende Transaktionen zugelassen ist oder nicht. |
|**Ich möchte eine Karten- oder Kontonummer aktualisieren.** |Die Kreditkarten- oder Kontonummer einer vorhandenen Zahlungsmethode kann nicht geändert werden. Wenn sich Ihre Karten- oder Kontonummer geändert hat, [ersetzen Sie diese durch eine andere Zahlungsmethode](#replace-a-payment-method), wodurch alle aktiven Abonnements von der alten zur neuen Zahlungsmethode wechseln, und [löschen Sie dann die alte Zahlungsmethode](#delete-a-payment-method-with-no-subscriptions-or-billing-profiles-attached). |
|**In meinem Konto gibt es nur eine Kreditkarte oder nur ein Bankkonto, und ich möchte sie/es entfernen.** |Wenn Sie nur über eine Zahlungsmethode verfügen, müssen Sie diese [durch eine neue Zahlungsmethode ersetzen](#replace-a-payment-method), bevor Sie sie löschen können. |
|**Ich kann meine Karte bzw. mein Bankkonto nicht hinzufügen.**  |Sie müssen eine Zahlungsmethode verwenden, die im Land Ihres Mandanten ausgestellt wurde. Wenn es bei der Eingabe Ihrer Karten- bzw. Bankkontoinformationen Probleme gibt, können Sie [den Support kontaktieren](../../admin/contact-support-for-business-products.md). |

## <a name="related-content"></a>Verwandte Inhalte

[Bezahlen Ihres Business-Abonnements](pay-for-your-subscription.md) (Artikel)\
[Verwalten von Abrechnungsprofilen](manage-billing-profiles.md) (Artikel)\
[Ändern der Abrechnungshäufigkeit](change-payment-frequency.md) (Artikel)