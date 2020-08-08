---
title: Verwalten von Lizenzanforderungen
f1.keywords:
- CSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- commerce
ms.custom: MACBillingLicensesRequests
search.appverid:
- MET150
description: Hier erfahren Sie, wie Sie Lizenzanforderungen von Benutzern für Ihr Microsoft 365 for Business-Abonnement überprüfen und genehmigen oder verweigern.
ms.date: 08/07/2020
ms.openlocfilehash: cbcdc5550d404278832cc702560ac55f6ace8a44
ms.sourcegitcommit: 9550298946f8accb90cd59be7b46b71d4bf4f8cc
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/08/2020
ms.locfileid: "46597654"
---
# <a name="manage-license-requests"></a>Verwalten von Lizenzanforderungen

> [!NOTE]
> Die Informationen in diesem Artikel gelten nur für Self-Service-erworbene Produkte. Weitere Informationen finden Sie unter [Self-Service purchase FAQ](../subscriptions/self-service-purchase-faq.md).

Wenn Sie Self-Service purchases in Ihrer Organisation deaktivieren, können Sie Lizenzanforderungen verwenden, um den Lizenz Anforderungsprozess für Ihre Benutzer zu verwalten. Wenn ein Benutzer versucht, einen Self-Service-Kauf für ein Produkt zu tätigen, das Sie blockiert haben, kann er eine Anforderung für eine Lizenz an Sie, den Administrator, übermitteln. Wenn Sie eine Anforderung stellen, können Sie die Namen anderer Benutzer hinzufügen, die auch Lizenzen für das Produkt benötigen.

> [!NOTE]
> Wenn Sie Benutzer daran hindern, Self-Service-Käufe zu tätigen, sendet Microsoft Ihnen keine Marketing-e-Mails. Auch wenn Sie eine Testversion eines Produkts verwenden, werden keine Eingabeaufforderungen zum Kauf angezeigt. Weitere Informationen finden Sie unter [Verwalten von Self-Service purchases (Administrator)](../subscriptions/manage-self-service-purchases-admins.md).

Zum Anzeigen und Verwalten von Lizenzanforderungen verwendet der Administrator die Registerkarte **Anforderungen** auf der Seite **Lizenzierung** . Die Liste zeigt den Namen des angeforderten Produkts, den Namen der Person, die eine Lizenz anfordert, das angeforderte Datum und den Status der Anforderung an. Administratoren können die Liste filtern, um Anforderungen anzuzeigen, die ausstehend oder abgeschlossen sind. Anforderungen werden 30 Tage lang aufbewahrt.

## <a name="before-you-begin"></a>Bevor Sie beginnen

Sie müssen ein globaler Administrator sein, um die Aufgaben in diesem Artikel ausführen zu können. Weitere Informationen finden Sie unter [Informationen zu Administratorrollen](../../admin/add-users/about-admin-roles.md).

## <a name="use-your-own-request-process"></a>Verwenden eines eigenen Anforderungsprozesses

Wenn Ihre Organisation über einen eigenen Anforderungsprozess verfügt, können Sie Sie stattdessen verwenden. Sie erstellen eine Nachricht, die Benutzern angezeigt wird, wenn Sie eine Lizenz anfordern.

> [!IMPORTANT]
> Wenn Sie einen eigenen Anforderungsprozess verwenden, werden auf der Registerkarte **Anforderungen** keine Anforderungen angezeigt. vorhandene Anforderungen vor dem Hinzufügen Ihrer Nachricht werden weiterhin angezeigt, bis Sie Sie genehmigen oder ablehnen.

1. Wechseln Sie im Admin Center zur Seite **Abrechnungs**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Lizenzen</a> , und wählen Sie dann die Registerkarte **Anforderungen** aus.
2. Wählen Sie **stattdessen vorhandenen Anforderungsprozess verwenden**aus.
3. Geben Sie im rechten Bereich im Feld **Nachricht** die Nachricht ein, die Benutzern angezeigt werden soll, wenn Sie eine Lizenz anfordern. Wenn Sie auch einen Link zu ihrer Organisationsrichtlinie oder andere Dokumentation hinzufügen möchten, geben Sie die URL in das Textfeld **Link to Documentation (optional)** ein.
4. Wählen Sie **Speichern** aus.

Wenn Sie zur Liste **Anforderungen** zurückkehren, wird die Nachricht angezeigt, in der **Sie Ihren eigenen Lizenz Anforderungsprozess verwenden**. Um Änderungen an der Nachricht vorzunehmen, die an Benutzer gesendet wird, wählen Sie **stattdessen den vorhandenen Anforderungsprozess verwenden**aus.

## <a name="stop-using-your-own-request-process"></a>Beenden der Verwendung eines eigenen Anforderungsprozesses

1. Wechseln Sie im Admin Center zur Seite **Abrechnungs**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Lizenzen</a> , und wählen Sie dann die Registerkarte **Anforderungen** aus.
2. Wählen Sie **stattdessen vorhandenen Anforderungsprozess verwenden**aus.
3. Deaktivieren Sie im rechten Bereich das Kontrollkästchen **Anforderungsprozess für meine Organisation verwenden** .
4. Wählen Sie **Speichern** aus.

## <a name="approve-or-deny-a-license-request"></a>Genehmigen oder Verweigern einer Lizenzanforderung

1. Wechseln Sie im Admin Center zur Seite **Abrechnungs**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Lizenzen</a> , und wählen Sie dann die Registerkarte **Anforderungen** aus.
2. Wählen Sie die Zeile aus, die die Anforderung enthält, die Sie überprüfen möchten. Im rechten Bereich werden Details angezeigt, über die Benutzerlizenzen für das Produkt wünschen.
3. Um die gesamte Anforderung abzulehnen, wählen Sie **nicht genehmigen**aus, und wählen Sie im Dialogfeld die Option **nicht genehmigen**aus.
4. Um einige Benutzer für die Anforderung zu verweigern, aber andere zu genehmigen, wählen Sie das X nach dem Namen der Benutzer aus, die Sie entfernen möchten. Ihre Namen werden unter " **diesen Benutzern nicht zuweisen**" verschoben.
5. Wenn Sie mehr als ein Produkt haben, wählen Sie unter **Produkt auswählen**diejenige aus, die Sie zum Zuweisen von Lizenzen verwenden möchten.
6. Um Benutzern den Zugriff auf bestimmte apps und Dienste zu verweigern, erweitern Sie **apps und Dienste aktivieren oder deaktivieren**, und deaktivieren Sie dann die Kontrollkästchen für diejenigen, die Sie ausschließen möchten.
7. Geben Sie unten im Bereich eine optionale Nachricht in das Textfeld ein.
8. Wenn Sie fertig sind, wählen Sie **genehmigen**aus. Im rechten Bereich werden die Details der Anforderung angezeigt.
9. Schließen Sie den rechten Bereich.
    Benutzer erhalten eine e-Mail, die besagt, dass Ihre Anforderung genehmigt oder verweigert wurde.

## <a name="related-content"></a>Verwandte Inhalte

[Zuweisen von Lizenzen zu Benutzern](../../admin/manage/assign-licenses-to-users.md) (Artikel) \
[Migrieren von Benutzern zu einem anderen Abonnement](../subscriptions/move-users-different-subscription.md) (Artikel) \
[Kaufen oder Entfernen von Abonnementlizenzen](buy-licenses.md) (Artikel)