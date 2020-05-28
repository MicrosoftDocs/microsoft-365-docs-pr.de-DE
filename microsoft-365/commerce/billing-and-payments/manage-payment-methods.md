---
title: Verwalten von Zahlungsmethoden
f1.keywords:
- CSH
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
ms.custom:
- TopSMBIssues
- okr_SMB
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
description: Erfahren Sie, wie Sie Ihre Zahlungsmethoden im Microsoft 365 Admin Center verwalten.
ms.openlocfilehash: 0320f71180a5c2c127217ebf01854943409e6386
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/27/2020
ms.locfileid: "44403678"
---
# <a name="manage-payment-methods"></a>Verwalten von Zahlungsmethoden

::: moniker range="o365-21vianet"
> [!NOTE]
> Das Admin Center wird geändert. Wenn Ihre Erfahrung nicht den hier aufgeführten Details entspricht, lesen Sie [über das neue Microsoft 365 Admin Center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).
::: moniker-end

Wenn Sie Geschäftsprodukte oder-Dienste von Microsoft kaufen, können Sie eine vorhandene Zahlungsmethode verwenden oder einen neuen hinzufügen. Sie können eine Kredit-oder Debitkarte oder ein Bankkonto verwenden, um die von Ihnen erworbenen Dinge zu bezahlen.

Wenn Ihr Geschäftskonto über ein Abrechnungsprofil verfügt und Sie ein Abrechnungsprofil Besitzer oder ein Abrechnungsprofil Mitwirkender sind, können Sie das Abrechnungsprofil verwenden, das von einer Kreditkarte oder einer Rechnungszahlung unterstützt wird, um Einkäufe zu tätigen oder Rechnungen zu bezahlen. Wenn Sie Rechnungs Rechnungs-Manager sind, können Sie nur ein Abrechnungsprofil verwenden, um Rechnungen zu bezahlen. Weitere Informationen zu Abrechnungs Profilen und Rollen finden Sie unter [Verwalten von Abrechnungs Profilen](manage-billing-profiles.md).

Wenn Ihr Geschäftskonto nicht über ein Abrechnungsprofil verfügt, kann ein globaler oder abrechnungsadministrator alle Bankkonten verwalten und verwenden, die dem Geschäftskonto hinzugefügt werden. Sie können jedoch nur Kreditkarten verwalten oder verwenden, die Sie hinzufügen.

> [!NOTE]
> Die Option zur Zahlung mit einem Bankkonto steht in einigen Ländern oder Regionen nicht zur Verfügung.
>
> Sie müssen eine Zahlungsmethode verwenden, die aus demselben Land wie Ihr Mandant ausgestellt wurde.

## <a name="add-a-payment-method"></a>Zahlungsmethode hinzufügen

Durch das Hinzufügen einer Zahlungsmethode werden keine Abonnements zugeordnet. Informationen zum Zuweisen eines einzelnen Abonnements zur Zahlungsmethode finden Sie unter [Ändern einer Zahlungsmethode für ein einzelnes Abonnement](#change-a-payment-method-for-a-single-subscription). Informationen zum Ersetzen aller Abonnements, die eine andere Zahlungsmethode mit der neuen Zahlung verwenden, finden Sie unter [Replace a Payment Method](#replace-a-payment-method).

::: moniker range="o365-worldwide"
1. Wechseln Sie im Admin Center zur Seite **Billing** > **Bills & Payments** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2018806" target="_blank">Payment Methods</a> .
::: moniker-end

::: moniker range="o365-germany"
1. Wechseln Sie im Admin Center zur Seite **Billing** > **Bills & Payments** > **Payment Methods** .
::: moniker-end

::: moniker range="o365-21vianet"
1. Wechseln Sie im Admin Center zur Seite **Billing** > **Bills & Payments** > **Payment Methods** .
::: moniker-end

2. Wählen Sie **Zahlungsmethode hinzufügen** aus.

3. Wählen Sie auf der Seite **Zahlungsmethoden** im Dropdownmenü eine Zahlungsmethode aus.

4. Geben Sie die Informationen für das neue Kreditkarten-oder Bank Konto ein, und wählen Sie dann **Hinzufügen**aus.

## <a name="update-payment-method-details"></a>Zahlungsmethodendetails aktualisieren

Sie können den Namen auf der Kredit-oder Debitkarte, der Rechnungsadresse oder dem Ablaufdatum für eine vorhandene Zahlungsmethode ändern. Sie können die Karten-oder Kontonummer jedoch nicht ändern. Wenn sich die Kontonummer geändert hat, [Ersetzen Sie Sie durch eine andere Zahlungsmethode](#replace-a-payment-method), und [Löschen Sie die alte](#delete-a-payment-method).

::: moniker range="o365-worldwide"
1. Wechseln Sie im Admin Center zur Seite **Billing** > **Bills & Payments** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2018806" target="_blank">Payment Methods</a> .
::: moniker-end

::: moniker range="o365-germany"
1. Wechseln Sie im Admin Center zur Seite **Billing** > **Bills & Payments** > **Payment Methods** .
::: moniker-end

::: moniker range="o365-21vianet"
1. Wechseln Sie im Admin Center zur Seite **Billing** > **Bills & Payments** > **Payment Methods** .
::: moniker-end

2. Wählen Sie die Zeile der Zahlungsmethode aus, die aktualisiert werden soll. Wählen Sie im rechten Bereich die Option **Bearbeiten** aus.

3. Aktualisieren Sie Ihre Angaben zur Zahlungsmethode, einschließlich des Namens auf der Kredit- oder Debitkarte, der Rechnungsadresse oder des Ablaufdatums, und wählen Sie dann **Speichern** aus.

## <a name="replace-a-payment-method"></a>Ersetzen einer Zahlungsmethode

Wenn Sie eine Zahlungsmethode ersetzen, ersetzen Sie Sie für alle Abonnements und Abrechnungsprofile, die dieselbe Zahlungsmethode verwenden. Wenn Sie eine Zahlungsmethode ersetzen, wird die vorhandene Zahlungsmethode nicht gelöscht. Es steht Ihnen weiterhin zur Auswahl und Verwendung für andere Abonnements und Abrechnungsprofile zur Verfügung.

Informationen zum Ändern der Zahlungsmethode für ein einzelnes Abonnement finden Sie unter [Ändern einer Zahlungsmethode für ein einzelnes Abonnement](#change-a-payment-method-for-a-single-subscription).

::: moniker range="o365-worldwide"
1. Wechseln Sie im Admin Center zur Seite **Billing** > **Bills & Payments** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2018806" target="_blank">Payment Methods</a> .
::: moniker-end

::: moniker range="o365-germany"
1. Wechseln Sie im Admin Center zur Seite **Billing** > **Bills & Payments** > **Payment Methods** .
::: moniker-end

::: moniker range="o365-21vianet"
1. Wechseln Sie im Admin Center zur Seite **Billing** > **Bills & Payments** > **Payment Methods** .
::: moniker-end

2. Wählen Sie die Zeile der Zahlungsmethode aus, die ersetzt werden soll. Im rechten Bereich werden alle Abrechnungsprofile und einzelne Abonnements mit der ausgewählten Zahlungsmethode aufgelistet.

3. Wählen Sie im rechten Bereich **Zahlungsmethode für alle Elemente ersetzen** aus.

4. Wenn Sie eine vorhandene Zahlungsmethode verwenden möchten, wählen Sie in der Dropdownliste eine aus und wählen Sie dann **Ersetzen**.
    > [!NOTE]
    > Wenn Sie Abonnements haben, die mit einem Abrechnungsprofil verknüpft sind, können Sie diese nur mit einer Kredit- oder Debitkarte bezahlen. Wenn Sie auf der Seite **Zahlungsmethoden** Bankkonten aufgelistet haben, können diese in der Dropdownliste nicht ausgewählt werden.

5. Wenn Sie eine neue Zahlungsmethode hinzufügen möchten, wählen Sie **Zahlungsmethode hinzufügen** aus.

6. Geben Sie im Bereich **Zahlungsmethode hinzufügen** die Kontoinformationen ein und wählen Sie dann **Speichern** aus. Sie müssen eine Zahlungsmethode aus dem gleichen Land wie Ihr Mandant verwenden.

7. Die neue Zahlungsmethode ist bereits in der Dropdownliste ausgewählt. Wählen Sie **Ersetzen**.

## <a name="change-a-payment-method-for-a-single-subscription"></a>Ändern einer Zahlungsmethode für ein einzelnes Abonnement

Sie können die Zahlungsmethode ändern, die für das bezahlen eines einzelnen Abonnements verwendet wird.

::: moniker range="o365-worldwide"
1. Navigieren Sie im Admin Center zur Seite **Abrechnung** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Ihre Produkte</a>.
::: moniker-end

::: moniker range="o365-germany"
1. Navigieren Sie im Admin Center zur Seite **Abrechnung** > **Ihre Produkte**.
::: moniker-end

::: moniker range="o365-21vianet"
1. Navigieren Sie im Admin Center zur Seite **Abrechnung** > **Ihre Produkte**.
::: moniker-end

2. Wählen Sie auf der Registerkarte **Abonnements** das Abonnement aus, für das Sie mit der alternativen Zahlungsmethode bezahlen möchten.

3. Wählen Sie unter **Abrechnung**neben der Zahlungsmethode die Option **Bearbeiten**aus.

4. Wählen Sie neben der vorhandenen Zahlungsmethode die Option **Change**aus.

5. Wählen Sie in der Dropdownliste eine alternative Zahlungsmethode aus, oder wählen Sie aus, um eine Zahlungsmethode hinzuzufügen.

6. Wenn Sie eine Zahlungsmethode hinzufügen, geben Sie die Karten-oder Kontodetails ein, und wählen Sie dann **Speichern**aus.

7. Stellen Sie sicher, dass die ausgewählte Zahlungsmethode richtig ist, und wählen Sie dann **Speichern**aus.

## <a name="delete-a-payment-method"></a>Löschen einer Zahlungsmethode

Sie können nur eine Zahlungsmethode löschen, die nicht an ein Abonnement oder ein Abrechnungsprofil angefügt ist. Dies gilt für alle Abonnements unabhängig von Ihrem Status.

### <a name="delete-a-payment-method-with-no-subscriptions-or-billing-profiles-attached"></a>Löschen einer Zahlungsmethode ohne zugeordnete Abonnements oder Abrechnungsprofile

Wenn eine Zahlungsmethode keinem Abonnement oder Abrechnungsprofil zugeordnet ist, können Sie Sie sofort löschen.

::: moniker range="o365-worldwide"
1. Wechseln Sie im Admin Center zur Seite **Billing** > **Bills & Payments** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2018806" target="_blank">Payment Methods</a> .
::: moniker-end

::: moniker range="o365-germany"
1. Wechseln Sie im Admin Center zur Seite **Billing** > **Bills & Payments** > **Payment Methods** .
::: moniker-end

::: moniker range="o365-21vianet"
1. Wechseln Sie im Admin Center zur Seite **Billing** > **Bills & Payments** > **Payment Methods** .
::: moniker-end

2. Suchen Sie die zu löschende Zahlungsmethode, wählen Sie die drei Punkte aus, und wählen Sie dann **Löschen**aus.

3. Wählen Sie unten im rechten Bereich **Löschen**aus.

### <a name="delete-a-payment-method-with-subscriptions-or-billing-profiles-attached"></a>Löschen einer Zahlungsmethode mit angefügten Abonnements oder Abrechnungs Profilen

Wenn eine Zahlungsmethode an alle Abonnements oder Abrechnungsprofile angehängt ist, ersetzen Sie Sie zunächst durch eine vorhandene Zahlungsmethode, oder fügen Sie eine neue Zahlung hinzu, und löschen Sie dann die alte Zahlungsmethode.

::: moniker range="o365-worldwide"
1. Wechseln Sie im Admin Center zur Seite **Billing** > **Bills & Payments** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2018806" target="_blank">Payment Methods</a> .
::: moniker-end

::: moniker range="o365-germany"
1. Wechseln Sie im Admin Center zur Seite **Billing** > **Bills & Payments** > **Payment Methods** .
::: moniker-end

::: moniker range="o365-21vianet"
1. Wechseln Sie im Admin Center zur Seite **Billing** > **Bills & Payments** > **Payment Methods** .
::: moniker-end

2. Wählen Sie die Zeile für die zu löschende Zahlungsmethode aus. Im rechten Bereich werden vorhandene Abonnements aufgelistet, die diese Zahlungsmethode verwenden.

3. Wählen Sie im rechten Bereich **Löschen**aus.

4. Um eine vorhandene Zahlungsmethode zu verwenden, wählen Sie eine aus der Dropdownliste aus, wählen Sie dann **weiter**aus, und wählen Sie dann **Löschen**aus.
    > [!NOTE]
    > Wenn Sie einem Abrechnungsprofil Abonnements zugeordnet haben, können Sie diese nur mit einer Kreditkarte bezahlen. Wenn auf der Seite **Zahlungsmethoden** Bankkonten aufgeführt sind, stehen Sie in der Dropdownliste nicht zur Auswahl.

5. Wenn Sie eine neue Zahlungsmethode hinzufügen möchten, wählen Sie **Zahlungsmethode hinzufügen** aus.

6. Wählen Sie den Typ der Zahlungsmethode aus, den Sie hinzufügen möchten, geben Sie die Kontoinformationen ein, und wählen Sie dann **Speichern**aus.

7. Die neue Zahlungsmethode ist bereits in der Dropdownliste ausgewählt. Wählen Sie **Weiter** aus.

8. Wählen Sie **Löschen** aus.

## <a name="troubleshoot-payment-methods"></a>Behandlung von Problemen mit Zahlungsmethoden

|**Problem**|**Schritte zur Problembehandlung**|
|:----------|:-----|
|**Ich erhalte eine Fehlermeldung mit dem Hinweis "der Browser ist derzeit auf Cookies blockieren" festgelegt.** |Konfigurieren Sie Ihren Browser so, dass er Cookies von Drittanbietern zulässt, und versuchen Sie es dann erneut. |
|**Meine Kreditkarte oder Debitkarte wurde abgelehnt.** |Wenn Sie per Kreditkarte oder Debitkarte bezahlen und Ihre Karte abgelehnt wird, erhalten Sie eine e-Mail, die besagt, dass Microsoft die Zahlung nicht verarbeiten konnte. Stellen Sie sicher, dass die Karten &mdash; Nummer, das Ablaufdatum, der Name auf der Karte und die Adresse, einschließlich Stadt, Bundesland und Postleitzahl &mdash; genau so angezeigt werden, wie auf der Karte und ihrer Erklärung. Sie können Ihre Karteninformationen aktualisieren und die Zahlung sofort über den Link **Ausgleichs Saldo** im Abschnitt **Abrechnung** auf der Seite Abonnementdetails übermitteln. Weitere Informationen finden Sie unter [Was passiert, wenn meine Kreditkarte abgelehnt wurde und meine Zahlung überfällig ist?](pay-for-your-subscription.md#what-if-my-credit-card-was-declined-and-my-payment-is-past-due)  <br/><br/>  Wenn die Kreditkarte dann immer noch abgelehnt wird, wenden Sie sich an Ihre Bank. Es ist möglich, dass Ihre Karte nicht aktiv ist. Wenn Sie die Karte kürzlich in der e-Mail mit einem aktualisierten Ablaufdatum erhalten haben, stellen Sie sicher, dass Sie aktiviert ist. Ihre Bank kann Ihnen auch mitteilen, ob Ihre Karte nicht für Online-, internationale oder wiederkehrende Transaktionen genehmigt wurde. |
|**Ich möchte eine Karten-oder Bank Kontonummer aktualisieren.** |Sie können die Karten-oder Kontonummer für eine vorhandene Zahlungsmethode nicht ändern. Wenn sich Ihre Karte oder Kontonummer geändert hat, [Ersetzen Sie Sie durch eine andere Zahlungsmethode](#replace-a-payment-method), die alle aktiven Abonnements von der Zahlungsmethode in die neue verlagert und dann [die alte Zahlungsmethode löscht](#delete-a-payment-method-with-no-subscriptions-or-billing-profiles-attached). |
|**Ich habe nur eine Karte oder ein Bankkonto in meinem Konto und möchte es entfernen.** |Wenn Sie nur über eine Zahlungsmethode verfügen, müssen Sie Sie [durch eine neue Zahlungsmethode ersetzen](#replace-a-payment-method) , bevor Sie Sie löschen können. |
|**Meine Karte oder Ihr Bankkonto kann nicht hinzugefügt werden.**  |Sie müssen eine Zahlungsmethode verwenden, die aus demselben Land wie Ihr Mandant ausgestellt wurde. Wenn Sie Probleme bei der Eingabe Ihrer Kreditkarten-oder Bankkontoinformationen haben, können Sie [sich an den Support wenden](../../admin/contact-support-for-business-products.md). |

## <a name="related-articles"></a>Verwandte Artikel

[Bezahlen Ihres Geschäfts Abonnements](pay-for-your-subscription.md)

[Verwalten von Abrechnungsprofilen](manage-billing-profiles.md)

[Ändern der Zahlungshäufigkeit](change-payment-frequency.md)