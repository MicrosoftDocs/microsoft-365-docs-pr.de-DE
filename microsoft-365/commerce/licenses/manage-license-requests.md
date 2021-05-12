---
title: Verwalten von Lizenzanforderungen
f1.keywords:
- CSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
ms.reviewer: micurn, nicholak
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- MACBillingLicensesRequests
- AdminSurgePortfolio
- commerce_licensing
search.appverid: MET150
description: Erfahren Sie, wie Sie Lizenzanforderungen von Benutzern für Ihr Microsoft 365 Business-Abonnement überprüfen und genehmigen oder verweigern.
ms.date: 08/07/2020
ms.openlocfilehash: 06ee210b39c19c1f2c8a2041c463568e55001b6e
ms.sourcegitcommit: 967f64dfa1a05f31179c8316b96bfb7758a5d990
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/12/2021
ms.locfileid: "52331550"
---
# <a name="manage-license-requests"></a>Verwalten von Lizenzanforderungen

> [!NOTE]
> Die Informationen in diesem Artikel gelten nur für gekaufte Self-Service-Produkte. Weitere Informationen finden Sie unter [Self-Service Purchase FAQ](../subscriptions/self-service-purchase-faq.md).

Wenn Sie Self-Service-Käufe in Ihrer Organisation deaktivieren, können Sie Lizenzanforderungen verwenden, um den Lizenzanforderungsprozess für Ihre Benutzer zu verwalten. Wenn ein Benutzer versucht, einen Self-Service-Kauf für ein blockiertes Produkt zu tätigen, kann er eine Lizenzanforderung an Sie, den Administrator, senden. Wenn sie eine Anforderung stellen, können sie die Namen anderer Benutzer hinzufügen, die ebenfalls Lizenzen für das Produkt benötigen.

> [!NOTE]
> Wenn Sie Benutzer am Tätigen von Self-Service-Käufen blockieren, sendet Microsoft ihnen keine Marketing-E-Mails. Wenn sie außerdem eine Testversion eines Produkts verwenden, werden keine Aufforderungen zum Kauf angezeigt. Weitere Informationen finden Sie unter [Manage self-service purchases (Admin)](../subscriptions/manage-self-service-purchases-admins.md).

Zum Anzeigen und Verwalten von Lizenzanforderungen verwendet der Administrator die Registerkarte **Anforderungen** auf der **Seite Lizenzierung.** Die Liste enthält den Namen des angeforderten Produkts, den Namen der Person, die eine Lizenz anfordert, das angeforderte Datum und den Status der Anforderung. Administratoren können die Liste so filtern, dass ausstehende oder abgeschlossene Anforderungen angezeigt werden. Anforderungen werden für 30 Tage gehalten.

## <a name="before-you-begin"></a>Bevor Sie beginnen

Sie müssen ein globaler Administrator sein, um die Aufgaben in diesem Artikel ausführen zu können. Weitere Informationen finden Sie unter [Informationen zu Administratorrollen](../../admin/add-users/about-admin-roles.md).

## <a name="use-your-own-request-process"></a>Verwenden Eines eigenen Anforderungsprozesses

Wenn Ihre Organisation über einen eigenen Anforderungsprozess verfügt, können Sie ihn stattdessen verwenden. Sie erstellen eine Meldung, die Benutzern angezeigt wird, wenn sie eine Lizenz anfordern.

> [!IMPORTANT]
> Wenn Sie Ihren eigenen Anforderungsprozess verwenden, werden auf der Registerkarte Anforderungen **keine Anforderungen** angezeigt. Vorhandene Anforderungen vor dem Hinzufügen der Nachricht werden weiterhin angezeigt, bis Sie sie genehmigen oder ablehnen.

1. Wechseln Sie im Admin Center zur Seite Abrechnungslizenzen,  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank"></a> und wählen Sie dann die Registerkarte **Anforderungen** aus.
2. Wählen **Sie Stattdessen den vorhandenen Anforderungsprozess verwenden aus.**
3. Geben Sie im rechten Bereich im **Feld** Nachricht die Nachricht ein, die Benutzern angezeigt werden soll, wenn sie eine Lizenz anfordern. Wenn Sie auch einen Link zu Ihrer Organisationsrichtlinie oder anderen Dokumentation hinzufügen möchten, geben Sie die URL in das Textfeld **Link zur Dokumentation (optional)** ein.
4. Wählen Sie **Speichern** aus.

Wenn Sie zur Liste Anforderungen **zurückkehren,** wird die Meldung Angezeigt, dass Sie Ihren eigenen **Lizenzanforderungsprozess verwenden.** Wenn Sie Änderungen an der Nachricht vornehmen möchten, die an Benutzer gesendet wird, wählen Sie **Stattdessen Den vorhandenen Anforderungsprozess verwenden aus.**

## <a name="stop-using-your-own-request-process"></a>Beenden der Verwendung Ihres eigenen Anforderungsprozesses

1. Wechseln Sie im Admin Center zur Seite Abrechnungslizenzen,  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank"></a> und wählen Sie dann die Registerkarte **Anforderungen** aus.
2. Wählen **Sie Stattdessen den vorhandenen Anforderungsprozess verwenden aus.**
3. Aktivieren Sie im rechten  Bereich das Kontrollkästchen Anforderungsprozess meiner Organisation verwenden.
4. Wählen Sie **Speichern** aus.

## <a name="approve-or-deny-a-license-request"></a>Genehmigen oder Verweigern einer Lizenzanforderung

1. Wechseln Sie im Admin Center zur Seite Abrechnungslizenzen,  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank"></a> und wählen Sie dann die Registerkarte **Anforderungen** aus.
2. Wählen Sie die Zeile aus, die die Anforderung enthält, die Sie überprüfen möchten. Im rechten Bereich werden Details dazu angezeigt, welche Benutzer Lizenzen für das Produkt wünschen.
3. Um die gesamte Anforderung zu verweigern, wählen **Sie Nicht** genehmigen aus, und wählen Sie im Dialogfeld Nicht **genehmigen aus.**
4. Um einige Benutzer für die Anforderung zu verweigern, andere jedoch zu genehmigen, wählen Sie das X nach dem Namen der Benutzer aus, die Sie entfernen möchten. Ihre Namen werden unter Diesen Benutzern **nicht zuweisen verschoben.**
5. Wenn Sie mehrere Produkte haben, wählen Sie unter **Produkt auswählen** das Produkt aus, für das Sie Lizenzen zuweisen möchten.
6. Um Benutzern den Zugriff auf bestimmte Apps und Dienste zu verweigern, erweitern Sie **Apps** und Dienste aktivieren oder deaktivieren, und deaktivieren Sie dann die Kontrollkästchen für die, die Sie ausschließen möchten.
7. Geben Sie unten im Bereich eine optionale Nachricht in das Textfeld ein.
8. Wenn Sie fertig sind, wählen Sie **Genehmigen aus.** Im rechten Bereich werden die Details der Anforderung angezeigt.
9. Schließen Sie den rechten Bereich.
    Benutzer erhalten eine E-Mail mit der Nachricht, dass ihre Anforderung genehmigt oder abgelehnt wurde.

## <a name="related-content"></a>Verwandte Inhalte

[Zuweisen von Lizenzen zu Benutzern ](../../admin/manage/assign-licenses-to-users.md) (Artikel)\
[Verschieben von Benutzern in ein anderes Abonnement](../subscriptions/move-users-different-subscription.md) (Artikel)\
[Kaufen oder Entfernen von Abonnementlizenzen](buy-licenses.md) (Artikel)
