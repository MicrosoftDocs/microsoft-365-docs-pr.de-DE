---
title: Verwalten von Richtlinien für automatischen Anspruch
f1.keywords:
- CSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
ms.review: yinggiy, pablom
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- commerce_licensing
description: Erfahren Sie, wie Sie Richtlinien für automatische Ansprüche erstellen und verwalten, die Benutzern für bestimmte Apps automatisch Lizenzen zuweisen.
search.appverid: MET150
ms.date: 04/06/2021
ms.openlocfilehash: b104700905b3753466036411368951f12a7012d8
ms.sourcegitcommit: 967f64dfa1a05f31179c8316b96bfb7758a5d990
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/12/2021
ms.locfileid: "52331646"
---
# <a name="manage-auto-claim-policies"></a>Verwalten von Richtlinien für automatischen Anspruch

Mit einer Richtlinie für automatische Ansprüche können Benutzer bei der ersten Anmeldung bei einer App automatisch eine Lizenz für ein Produkt beanspruchen. Als Administrator weisen Sie Benutzern in der Regel Lizenzen entweder manuell oder mithilfe der gruppenbasierten Lizenzierung zu. Mithilfe von Richtlinien für automatische Ansprüche verwalten Sie die Produkte, für die Benutzer automatisch Lizenzen beanspruchen können. Sie können auch steuern, von welchen Produkten diese Lizenzen stammen.

Nachdem Sie eine Richtlinie für automatische Ansprüche erstellt haben, können Sie die folgenden Aufgaben ausführen, um die Richtlinie zu verwalten:

- [Aktivieren oder Deaktivieren der Richtlinie](#turn-a-policy-on-or-off)
- [Bearbeiten des Anzeigenamens der Richtlinie](#edit-the-policy-friendly-name)
- [Hinzufügen oder Entfernen von Sicherungsprodukten](#add-or-remove-backup-products)
- [Verwalten der zuweisenden Apps und Dienste](#change-the-assigning-apps-and-services)
- [Ändern der Zuweisungsreihenfolge](#change-the-assigning-order-for-backup-products)
- [Anzeigen eines Richtlinienberichts](#view-an-auto-claim-policy-report)

> [!IMPORTANT]
> Richtlinien für automatische Ansprüche sind derzeit nur für Microsoft Teams verfügbar. In Zukunft stehen weitere Produkte zur Verfügung.

## <a name="before-you-begin"></a>Bevor Sie beginnen

Sie müssen ein globaler, Benutzer- oder Lizenzadministrator sein, um Richtlinien für automatische Ansprüche zu erstellen und zu verwalten. Weitere Informationen finden Sie unter [Informationen zu Administratorrollen von Microsoft 365](../../admin/add-users/about-admin-roles.md).

## <a name="turn-the-auto-claim-policy-feature-on-or-off"></a>Aktivieren oder Deaktivieren des Richtlinienfeatures für automatische Ansprüche

Standardmäßig ist das Feature für automatische Anspruchsrichtlinien deaktiviert. Bevor Sie das Feature verwenden können, müssen Sie es zuerst aktivieren. Nachdem Sie das Feature aktivieren, können Sie eine Richtlinie für den automatischen Anspruch erstellen.

### <a name="turn-on-auto-claim-policies"></a>Aktivieren von Richtlinien für automatische Ansprüche

1. Wechseln Sie im Admin Center zur **Seite** Abrechnungslizenzen, und wählen Sie dann die Registerkarte \>  Richtlinie für automatische <a href="https://go.microsoft.com/fwlink/p/?linkid=2134398" target="_blank">Ansprüche</a> aus.
2. Wählen Sie in der Mitte der Seite die Schaltfläche Einstellung **aktivieren** aus.

### <a name="turn-off-auto-claim-policies"></a>Automatische Anspruchsrichtlinien deaktivieren

Nur ein globaler Administrator kann eine Richtlinieneinstellung für automatische Ansprüche deaktivieren.

1. Wechseln Sie im Admin Center zu **Einstellungen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2053743" target="_blank">Organisationseinstellungen</a>.
2. Wählen Sie am unteren Rand der Tabelle die Option **Benutzereigene Apps und Dienste aus.**
3. Löschen Sie im rechten Bereich das Kontrollkästchen Benutzer bei der ersten Anmeldung automatisch Lizenzen beanspruchen **lassen.**

Wenn Sie bereits über eine aktive Richtlinie verfügen, aber keine weiteren Benutzer Lizenzen beanspruchen möchten, deaktivieren Sie [die Richtlinie](#turn-a-policy-on-or-off). Wenn Sie eine Richtlinie für automatische Ansprüche deaktivieren, können ab diesem Zeitpunkt keine weiteren Benutzer eine Lizenz beanspruchen. Benutzer, die bereits eine Lizenz beansprucht haben, verlieren ihre Lizenz nicht.

## <a name="create-an-auto-claim-policy"></a>Erstellen einer Richtlinie für automatische Ansprüche

Auf der Registerkarte Richtlinie <a href="https://go.microsoft.com/fwlink/p/?linkid=2134398" target="_blank">für automatische</a> Ansprüche werden die von Ihnen erstellten Richtlinien aufgeführt. Auf dieser Registerkarte sehen Sie: den Namen der Richtlinie, die der Richtlinie zugeordnete App, das Produkt, das der Richtlinie zugewiesen ist, die Anzahl der verfügbaren Lizenzen und der Status der Richtlinie.

Wenn Sie eine Richtlinie für automatische Ansprüche erstellen, können Sie ihr ein Sicherungsprodukt hinzufügen. Wenn das primäre Produkt keine Lizenzen hat, wird das Sicherungsprodukt zum Zuweisen von Lizenzen zu Benutzern verwendet. Sie können bis zu vier Sicherungsprodukte hinzufügen und [die Reihenfolge ändern, in](#change-the-assigning-order-for-backup-products)der sie verwendet werden. Weitere Informationen finden Sie unter Hinzufügen oder Entfernen [von Sicherungsprodukten](#add-or-remove-backup-products).

> [!NOTE]
> Derzeit können Sie nur eine Richtlinie für automatische Ansprüche erstellen. Die Anzahl der Richtlinien, die Sie erstellen können, wird steigen, wenn mehr Produkte dieses Feature verwenden können.

1. Wechseln Sie im Admin Center zur **Seite** Abrechnungslizenzen, und wählen Sie dann die Registerkarte \>  Richtlinie für automatische <a href="https://go.microsoft.com/fwlink/p/?linkid=2134398" target="_blank">Ansprüche</a> aus.
2. Wählen **Sie Richtlinie hinzufügen aus.**
3. Geben Sie auf der Seite Diese Richtlinie für **automatischen** Anspruch benennen einen Namen für die Richtlinie ein, und wählen Sie **dann Weiter aus.**
4. Wählen Sie **auf der Seite** App und Produkt für automatische Ansprüche festlegen eine App und das Abonnement aus, aus dem Lizenzen zugewiesen werden.
5. Wenn Sie ein Sicherungsprodukt hinzufügen möchten, wählen Sie **Dieser** Richtlinie ein Sicherungsprodukt hinzufügen aus, und wählen Sie dann das Produkt aus der Liste aus.
6. Wählen Sie **Weiter** aus.
7. Löschen oder aktivieren Sie **auf** der Seite Apps auswählen die Felder für die Apps, die ausgeschlossen oder in die Lizenz mit einschließen werden, und wählen Sie dann **Weiter aus.**
8. Wenn Sie ein oder mehrere Sicherungsprodukte hinzugefügt haben, wiederholen Sie Schritt 7 für jedes Produkt. Wechseln Sie andernfalls zu Schritt 9.
9. Überprüfen Sie **auf der Seite** Überprüfen und Fertig stellen die neuen Richtlinieninformationen, nehmen Sie alle erforderlichen Änderungen vor, und wählen Sie dann Richtlinie erstellen **aus.**
10. Wählen Sie **Schließen** aus.

## <a name="turn-a-policy-on-or-off"></a>Aktivieren oder Deaktivieren einer Richtlinie

Wenn Sie eine Richtlinie deaktivieren, können keine weiteren Benutzer Lizenzen gemäß dieser Richtlinie beanspruchen. Die Änderung hat keine Auswirkungen auf Benutzer, die bereits Lizenzen im Rahmen dieser Richtlinie beansprucht haben.

1. Wechseln Sie im Admin Center zur **Seite** Abrechnungslizenzen, und wählen Sie dann die Registerkarte \>  Richtlinie für automatische <a href="https://go.microsoft.com/fwlink/p/?linkid=2134398" target="_blank">Ansprüche</a> aus.
2. Wählen Sie die Richtlinie aus, die Sie bearbeiten möchten.
3. Aktivieren oder deaktivieren Sie im Detailbereich unter Aktivieren oder **Deaktivieren** dieser Richtlinie das Kontrollkästchen.
4. Wählen **Sie Speichern** aus, um den Detailbereich zu schließen.

## <a name="edit-the-policy-friendly-name"></a>Bearbeiten des Anzeigenamens der Richtlinie

1. Wechseln Sie im Admin Center zur **Seite** Abrechnungslizenzen, und wählen Sie dann die Registerkarte \>  Richtlinie für automatische <a href="https://go.microsoft.com/fwlink/p/?linkid=2134398" target="_blank">Ansprüche</a> aus.
2. Wählen Sie die Richtlinie aus, die Sie bearbeiten möchten.
3. Wählen Sie im Detailbereich im Abschnitt **Richtlinienname** die Option **Bearbeiten aus.**
4. Geben Sie einen neuen Richtliniennamen ein, und wählen Sie dann **Speichern aus.**
5. Wählen **Sie Speichern** aus, um den Detailbereich zu schließen.

## <a name="add-or-remove-backup-products"></a>Hinzufügen oder Entfernen von Sicherungsprodukten

Wenn Sie eine Richtlinie erstellen, fügen Sie ihr ein Produkt hinzu. Lizenzen werden dann Benutzern aus diesem Pool von Lizenzen automatisch zugewiesen. Sie können Produkte für eine Richtlinie für automatische Ansprüche jederzeit hinzufügen oder entfernen. Wenn Der Richtlinie bereits ein Produkt zugeordnet ist, werden alle hinzugefügten Produkte als Sicherungsprodukte betrachtet. Wenn die verfügbare Anzahl von Lizenzen aus dem ersten Produkt verbraucht wird, verwendet die Richtlinie das nächste Sicherungsprodukt in der Liste, um Lizenzen zuzuordnen. Sie [können die Liste der Produkte neu anordnen,](#change-the-assigning-apps-and-services) wie Sie möchten.

Wenn Sie ein Sicherungsprodukt entfernen, wird es nicht mehr zum Zuweisen von Lizenzen verwendet. Benutzer mit einer vorhandenen Lizenz verfügen weiterhin über diese Lizenz, aber keine neuen Benutzer können Lizenzen für dieses Produkt erhalten.

> [!NOTE]
> Eine Richtlinie für automatische Ansprüche muss mindestens ein Produkt enthalten. Sie können nicht alle Produkte aus einer Richtlinie entfernen. Wenn Sie keine Lizenzen aus einer bestimmten Richtlinie für automatische Ansprüche mehr zuweisen möchten, deaktivieren Sie [die Richtlinie](#view-an-auto-claim-policy-report).

### <a name="add-a-backup-product"></a>Hinzufügen eines Sicherungsprodukts

1. Wechseln Sie im Admin Center zur **Seite** Abrechnungslizenzen, und wählen Sie dann die Registerkarte \>  Richtlinie für automatische <a href="https://go.microsoft.com/fwlink/p/?linkid=2134398" target="_blank">Ansprüche</a> aus.
2. Wählen Sie die Richtlinie aus, die Sie bearbeiten möchten.
3. Wählen Sie im Detailbereich unten die Option Dieser Richtlinie ein **Sicherungsprodukt hinzufügen aus.**
    > [!NOTE]
    > Wenn dieser Link nicht zu sehen ist, liegt dies daran, dass Ihrem Konto nur ein Produkt zugeordnet ist.
4. Wählen Sie **im Bereich** Produkt hinzufügen in der Dropdownliste ein Produkt aus, das der Richtlinie hinzugefügt werden soll, und wählen Sie dann **Hinzufügen aus.**
5. Wählen **Sie Speichern** aus, um den Detailbereich zu schließen.

### <a name="remove-a-backup-product"></a>Entfernen eines Sicherungsprodukts

1. Wechseln Sie im Admin Center zur **Seite** Abrechnungslizenzen, und wählen Sie dann die Registerkarte \>  Richtlinie für automatische <a href="https://go.microsoft.com/fwlink/p/?linkid=2134398" target="_blank">Ansprüche</a> aus.
2. Wählen Sie die Richtlinie aus, die Sie bearbeiten möchten.
3. Wählen Sie im Detailbereich unten die Option Produkt **entfernen aus.**
4. Wählen Sie im Bereich Produkt **aus dem Richtlinienbereich entfernen** das Feld für die Richtlinie aus, die Sie entfernen möchten, und wählen Sie dann Speichern **aus.**
5. Schließen Sie den Detailbereich.

## <a name="change-the-assigning-apps-and-services"></a>Ändern der zuweisenden Apps und Dienste

Jedem Produkt ist eine Sammlung von Apps und Diensten zugeordnet.
Für jedes Produkt in Ihrer Richtlinie für automatische Ansprüche können Sie angeben, welche Apps und Dienste enthalten sein sollten, wenn einem Benutzer automatisch eine Lizenz für dieses Produkt zugewiesen wird.

1. Wechseln Sie im Admin Center zur **Seite** Abrechnungslizenzen, und wählen Sie dann die Registerkarte \>  Richtlinie für automatische <a href="https://go.microsoft.com/fwlink/p/?linkid=2134398" target="_blank">Ansprüche</a> aus.
2. Wählen Sie die Richtlinie aus, die Sie bearbeiten möchten.
3. Wählen Sie im Detailbereich unter **Apps und Dienste** bearbeiten **aus.**
4. Wählen Sie im Bereich Apps  **und** Dienste in der Dropdownliste Produkt ein einzelnes Produkt aus, oder wählen Sie Alle Produkte **aus.**
5. Aktivieren oder löschen Sie die Kontrollkästchen für Apps und Dienste, auf die Benutzer Zugriff haben möchten oder nicht.
6. Wenn Sie fertig sind, wählen **Sie Speichern** aus, und schließen Sie dann den Detailbereich.

## <a name="change-the-assigning-order-for-backup-products"></a>Ändern der Zuweisungsreihenfolge für Sicherungsprodukte

Wenn Der Richtlinie Sicherungsprodukte zugewiesen sind, können Sie die Reihenfolge ändern, in der sie zum Zuweisen von Lizenzen verwendet werden, wenn sich Benutzer bei der App anmelden.

1. Wechseln Sie im Admin Center zur **Seite** Abrechnungslizenzen, und wählen Sie dann die Registerkarte \>  Richtlinie für automatische <a href="https://go.microsoft.com/fwlink/p/?linkid=2134398" target="_blank">Ansprüche</a> aus.
2. Wählen Sie die Richtlinie aus, die Sie bearbeiten möchten.
3. Wählen Sie im Detailbereich im Abschnitt Produktlizenzen das Feld neben dem Produkt aus, das Sie verschieben möchten, und wählen Sie dann **Nach** oben oder **Nach unten verschieben aus.** 
4. Wiederholen Sie Schritt 3 für jedes Produkt, das Sie neu anordnen möchten.
5. Wenn Sie die Neubestellung der Produkte abgeschlossen haben, wählen Sie **Speichern** aus, um den Detailbereich zu schließen.

## <a name="view-an-auto-claim-policy-report"></a>Anzeigen eines Richtlinienberichts für automatische Ansprüche

1. Wechseln Sie im Admin Center zur **Seite** Abrechnungslizenzen, und wählen Sie dann die Registerkarte \>  Richtlinie für automatische <a href="https://go.microsoft.com/fwlink/p/?linkid=2134398" target="_blank">Ansprüche</a> aus.
2. Wählen **Sie Bericht anzeigen aus.** Auf **der Seite Richtlinienbericht für automatische** Ansprüche werden alle Lizenzen aufgeführt, die in den letzten 90 Tagen von jeder Richtlinie zugewiesen wurden. Standardmäßig werden auf der Seite die letzten 90 Tage angezeigt.
3. Um den angezeigten Zeitraum zu ändern, wählen Sie die Dropdownliste Vergangene **30** Tage aus. Sie können Berichte für die letzten 1, 7, 30 und 90 Tage anzeigen.

## <a name="next-steps"></a>Nächste Schritte

Sie können regelmäßig zur  Registerkarte Richtlinie für automatische Ansprüche zurückkehren, um eine Liste der Benutzer zu sehen, die lizenzen unter den von Ihnen erstellten Richtlinien beansprucht haben.

## <a name="related-content"></a>Verwandte Inhalte

[Zuweisen von Lizenzen zu Benutzern ](../../admin/manage/assign-licenses-to-users.md) (Artikel)\
[Kaufen oder Entfernen von Abonnementlizenzen](buy-licenses.md) (Artikel)\
[Verstehen von Abonnements und Lizenzen](subscriptions-and-licenses.md) (Artikel)