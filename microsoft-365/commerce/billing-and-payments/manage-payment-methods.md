---
title: Zahlungsmethoden verwalten
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
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
description: Erfahren Sie, wie Sie Ihre Zahlungsmethoden im Microsoft 365 Admin Center verwalten.
ms.openlocfilehash: 997b957bb28d32402e17eb855bc891ed07e5f27f
ms.sourcegitcommit: fce0d5cad32ea60a08ff001b228223284710e2ed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/21/2020
ms.locfileid: "42894841"
---
# <a name="manage-payment-methods"></a>Zahlungsmethoden verwalten

Wenn Sie Geschäftsprodukte oder-Dienste von Microsoft kaufen, können Sie eine vorhandene Zahlungsmethode verwenden oder einen neuen hinzufügen. Sie können eine Kredit-oder Debitkarte oder ein Bankkonto verwenden, um die von Ihnen erworbenen Dinge zu bezahlen. Sie können jedoch nur Zahlungsmethoden verwalten, die Sie hinzufügen.

> [!NOTE]
> Die Option zur Zahlung mit einem Bankkonto steht in einigen Ländern oder Regionen nicht zur Verfügung.
>
> Sie müssen eine Zahlungsmethode verwenden, die aus demselben Land wie Ihr Mandant ausgestellt wurde.

## <a name="add-a-payment-method"></a>Hinzufügen einer Zahlungsmethode

Durch das Hinzufügen einer Zahlungsmethode werden keine Abonnements zugeordnet. Informationen zum Zuweisen eines einzelnen Abonnements zur Zahlungsmethode finden Sie unter [Ändern einer Zahlungsmethode für ein einzelnes Abonnement](#change-a-payment-method-for-a-single-subscription). Informationen zum Ersetzen aller Abonnements, die eine andere Zahlungsmethode mit der neuen Zahlung verwenden, finden Sie unter [Replace a Payment Method](#replace-a-payment-method).

1. Wechseln Sie im Admin Center zur Seite **Billing** > **Bills & Payments** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2018806" target="_blank">Payment Methods</a> .
2. Wählen Sie **Zahlungsmethode hinzufügen** aus.
3. Wählen Sie auf der Seite **Zahlungsmethoden** im Dropdownmenü eine Zahlungsmethode aus.
4. Geben Sie die Informationen für das neue Kreditkarten-oder Bank Konto ein, und wählen Sie dann **Hinzufügen**aus.

## <a name="update-payment-method-details"></a>Details zur Zahlungsmethode aktualisieren

Sie können den Namen auf der Kredit-oder Debitkarte, der Rechnungsadresse oder dem Ablaufdatum für eine vorhandene Zahlungsmethode ändern. Sie können die Karten-oder Kontonummer jedoch nicht ändern. Wenn sich die Kontonummer geändert hat, [Ersetzen Sie Sie durch eine andere Zahlungsmethode](#replace-a-payment-method), und [Löschen Sie die alte](#delete-a-payment-method).

1. Wechseln Sie im Admin Center zur Seite **Billing** > **Bills & Payments** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2018806" target="_blank">Payment Methods</a> .
2. Wählen Sie die Zeile der zu aktualisierende Zahlungsmethode aus. Wählen Sie im rechten Bereich **Bearbeiten**aus.
3. Aktualisieren Sie Ihre Zahlungsmethoden Informationen (Name auf der Kredit-oder Debitkarte, Rechnungsadresse oder Ablaufdatum), und wählen Sie dann **Speichern**aus.

## <a name="replace-a-payment-method"></a>Ersetzen einer Zahlungsmethode

Wenn Sie eine Zahlungsmethode ersetzen, ersetzen Sie Sie für alle Abonnements und Abrechnungsprofile, die dieselbe Zahlungsmethode verwenden. Wenn Sie eine Zahlungsmethode ersetzen, wird die vorhandene Zahlungsmethode nicht gelöscht. Es steht Ihnen weiterhin zur Auswahl und Verwendung für andere Abonnements und Abrechnungsprofile zur Verfügung.

Informationen zum Ändern der Zahlungsmethode für ein einzelnes Abonnement finden Sie unter [Ändern einer Zahlungsmethode für ein einzelnes Abonnement](#change-a-payment-method-for-a-single-subscription).

1. Wechseln Sie im Admin Center zur Seite **Billing** > **Bills & Payments** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2018806" target="_blank">Payment Methods</a> .
2. Wählen Sie die Zeile der Zahlungsmethode aus, die ersetzt werden soll. Im rechten Bereich werden alle Abrechnungsprofile und einzelnen Abonnements aufgelistet, die die ausgewählte Zahlungsmethode verwenden.
3. Wählen Sie im rechten Bereich **Zahlungsmethode ersetzen für alle Elemente**aus.
4. Um eine vorhandene Zahlungsmethode zu verwenden, wählen Sie eine aus der Dropdownliste aus, und wählen Sie dann **ersetzen**aus.
    > [!NOTE]
    > Wenn Sie einem Abrechnungsprofil Abonnements zugeordnet haben, können Sie nur eine Kredit-oder Debitkarte verwenden, um Sie zu bezahlen. Wenn auf der Seite **Zahlungsmethoden** Bankkonten aufgeführt sind, stehen Sie in der Dropdownliste nicht zur Auswahl zur Verfügung.
5. Um eine neue Zahlungsmethode hinzuzufügen, wählen Sie **Zahlungsmethode hinzufügen**aus.
6. Geben Sie im Bereich **Zahlungsmethode hinzufügen** die Kontoinformationen ein, und wählen Sie dann **Speichern**aus. Sie müssen eine Zahlungsmethode aus demselben Land wie Ihr Mandant verwenden.
7. Die neue Zahlungsmethode ist in der Dropdownliste bereits ausgewählt. Wählen Sie **ersetzen**aus.

## <a name="change-a-payment-method-for-a-single-subscription"></a>Ändern einer Zahlungsmethode für ein einzelnes Abonnement

Sie können die Zahlungsmethode ändern, die für das bezahlen eines einzelnen Abonnements verwendet wird.

1. Wechseln Sie im Admin Center zur Seite **Abrechnungs** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Produkte & Dienste</a> .
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

1. Wechseln Sie im Admin Center zur Seite **Billing** > **Bills & Payments** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2018806" target="_blank">Payment Methods</a> .
2. Suchen Sie die zu löschende Zahlungsmethode, wählen Sie die drei Punkte aus, und wählen Sie dann **Löschen**aus.
3. Wählen Sie unten im rechten Bereich **Löschen**aus.

### <a name="delete-a-payment-method-with-subscriptions-or-billing-profiles-attached"></a>Löschen einer Zahlungsmethode mit angefügten Abonnements oder Abrechnungs Profilen

Wenn eine Zahlungsmethode an alle Abonnements oder Abrechnungsprofile angehängt ist, ersetzen Sie Sie zunächst durch eine vorhandene Zahlungsmethode, oder fügen Sie eine neue Zahlung hinzu, und löschen Sie dann die alte Zahlungsmethode.

1. Wechseln Sie im Admin Center zur Seite **Billing** > **Bills & Payments** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2018806" target="_blank">Payment Methods</a> .
2. Wählen Sie die Zeile für die zu löschende Zahlungsmethode aus. Im rechten Bereich werden vorhandene Abonnements aufgelistet, die diese Zahlungsmethode verwenden.
3. Wählen Sie im rechten Bereich **Löschen**aus.
4. Um eine vorhandene Zahlungsmethode zu verwenden, wählen Sie eine aus der Dropdownliste aus, wählen Sie dann **weiter**aus, und wählen Sie dann **Löschen**aus.
    > [!NOTE]
    > Wenn Sie einem Abrechnungsprofil Abonnements zugeordnet haben, können Sie diese nur mit einer Kreditkarte bezahlen. Wenn auf der Seite **Zahlungsmethoden** Bankkonten aufgeführt sind, stehen Sie in der Dropdownliste nicht zur Auswahl.
5. Um eine neue Zahlungsmethode hinzuzufügen, wählen Sie **Zahlungsmethode hinzufügen**aus.
6. Wählen Sie den Typ der Zahlungsmethode aus, den Sie hinzufügen möchten, geben Sie die Kontoinformationen ein, und wählen Sie dann **Speichern**aus.
7. Die neue Zahlungsmethode ist in der Dropdownliste bereits ausgewählt. Wählen Sie **Weiter** aus.
8. Wählen Sie **Löschen** aus.

## <a name="troubleshoot-payment-methods"></a>Problembehandlung bei Zahlungsmethoden

|**Problem**|**Schritte zur Problembehandlung**|
|:----------|:-----|
|**Ich erhalte eine Fehlermeldung mit dem Hinweis "der Browser ist derzeit auf Cookies blockieren" festgelegt.** |Konfigurieren Sie Ihren Browser so, dass er Cookies von Drittanbietern zulässt, und versuchen Sie es dann erneut. |
|**Meine Kreditkarte oder Debitkarte wurde abgelehnt.** |Wenn Sie per Kreditkarte oder Debitkarte bezahlen und Ihre Karte abgelehnt wird, erhalten Sie eine e-Mail, die besagt, dass Microsoft die Zahlung nicht verarbeiten konnte. Stellen Sie sicher, dass die Karten &mdash; Nummer, das Ablaufdatum, der Name auf der Karte und die Adresse, einschließlich Stadt, Bundesland und Postleitzahl, genau so angezeigt werden, wie Sie auf der Karte und ihrer Erklärung dargestellt werden. Sie können Ihre Karteninformationen aktualisieren und die Zahlung sofort über den Link **Ausgleichs Saldo** im Abschnitt **Abrechnung** auf der Seite Abonnementdetails übermitteln. Weitere Informationen finden Sie unter [Was passiert, wenn meine Kreditkarte abgelehnt wurde und meine Zahlung überfällig ist?](pay-for-your-subscription.md#what-if-my-credit-card-was-declined-and-my-payment-is-past-due)  <br/><br/>  Wenn die Kreditkarte dann immer noch abgelehnt wird, wenden Sie sich an Ihre Bank. Es ist möglich, dass Ihre Karte nicht aktiv ist. Wenn Sie die Karte kürzlich in der e-Mail mit einem aktualisierten Ablaufdatum erhalten haben, stellen Sie sicher, dass Sie aktiviert ist. Ihre Bank kann Ihnen auch mitteilen, ob Ihre Karte nicht für Online-, internationale oder wiederkehrende Transaktionen genehmigt wurde. |
|**Ich möchte eine Karten-oder Bank Kontonummer aktualisieren.** |Sie können die Karten-oder Kontonummer für eine vorhandene Zahlungsmethode nicht ändern. Wenn sich Ihre Karte oder Kontonummer geändert hat, [Ersetzen Sie Sie durch eine andere Zahlungsmethode](#replace-a-payment-method), die alle aktiven Abonnements von der Zahlungsmethode in die neue verlagert und dann [die alte Zahlungsmethode löscht](#delete-a-payment-method-with-no-subscriptions-or-billing-profiles-attached). |
|**Ich habe nur eine Karte oder ein Bankkonto in meinem Konto und möchte es entfernen.** |Wenn Sie nur über eine Zahlungsmethode verfügen, müssen Sie Sie [durch eine neue Zahlungsmethode ersetzen](#replace-a-payment-method) , bevor Sie Sie löschen können. |
|**Meine Karte oder Ihr Bankkonto kann nicht hinzugefügt werden.**  |Sie müssen eine Zahlungsmethode verwenden, die aus demselben Land wie Ihr Mandant ausgestellt wurde. Wenn Sie Probleme bei der Eingabe Ihrer Kreditkarten-oder Bankkontoinformationen haben, können Sie [sich an den Support wenden](../../admin/contact-support-for-business-products.md). |

## <a name="related-articles"></a>Verwandte Artikel

[Bezahlen Ihres Geschäfts Abonnements](pay-for-your-subscription.md)

[Verwalten von Abrechnungsprofilen](manage-billing-profiles.md)

[Ändern der Zahlungshäufigkeit](change-payment-frequency.md)