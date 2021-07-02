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
description: Erfahren Sie, wie Sie Lizenzanforderungen von Benutzern für Ihr Microsoft 365 for Business-Abonnement überprüfen und genehmigen oder verweigern.
ms.date: 06/07/2021
ms.openlocfilehash: 23258d21ebb413c56323aa4dab25cee60baf2be0
ms.sourcegitcommit: a4c93a4c7d7db08fe3b032b58d5c7dbbb9476e90
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/02/2021
ms.locfileid: "53256807"
---
# <a name="manage-license-requests"></a>Verwalten von Lizenzanforderungen

> [!NOTE]
> Die Informationen in diesem Artikel gelten nur für Selbstbedienungsprodukte. Weitere Informationen finden Sie unter [Häufig gestellte Fragen zum Self-Service-Kauf.](../subscriptions/self-service-purchase-faq.yml)

Wenn Sie Self-Service-Käufe in Ihrer Organisation deaktivieren, können Sie Lizenzanforderungen verwenden, um den Lizenzanforderungsprozess für Ihre Benutzer zu verwalten. Wenn ein Benutzer versucht, einen Self-Service-Kauf für ein Produkt zu tätigen, das Sie blockiert haben, kann er eine Lizenzanforderung an Sie, den Administrator, senden. Wenn sie eine Anforderung stellen, können sie die Namen anderer Benutzer hinzufügen, die ebenfalls Lizenzen für das Produkt benötigen.

> [!NOTE]
> Wenn Sie verhindern, dass Benutzer Self-Service-Käufe tätigen, sendet Microsoft ihnen keine Marketing-E-Mails. Wenn sie eine Testversion eines Produkts verwenden, werden keine Aufforderungen zum Kauf angezeigt. Weitere Informationen finden Sie unter [Verwalten von Self-Service-Käufen (Administrator).](../subscriptions/manage-self-service-purchases-admins.md)

Um Lizenzanforderungen anzuzeigen und zu verwalten, verwendet der Administrator die Registerkarte **"Anforderungen"** auf der **Seite "Lizenzierung".** Die Liste enthält den Namen des Produkts, das angefordert wird, den Namen der Person, die eine Lizenz anfordert, das angeforderte Datum und den Status der Anforderung. Administratoren können die Liste filtern, um Anforderungen anzuzeigen, die ausstehend oder abgeschlossen sind. Anforderungen werden 30 Tage lang aufbewahrt.

## <a name="before-you-begin"></a>Vorabinformationen

Sie müssen ein globaler Administrator sein, um die Aufgaben in diesem Artikel ausführen zu können. Weitere Informationen finden Sie unter [Informationen zu Administratorrollen](../../admin/add-users/about-admin-roles.md).

## <a name="use-your-own-request-process"></a>Verwenden Ihres eigenen Anforderungsprozesses

Wenn Ihre Organisation über einen eigenen Anforderungsprozess verfügt, können Sie ihn stattdessen verwenden. Sie erstellen eine Meldung, die Benutzern angezeigt wird, wenn sie eine Lizenz anfordern.

> [!IMPORTANT]
> Wenn Sie Ihren eigenen Anforderungsprozess verwenden, werden auf der Registerkarte **"Anforderungen"** keine Anforderungen angezeigt. Vorhandene Anforderungen vor dem Hinzufügen ihrer Nachricht werden weiterhin angezeigt, bis Sie sie genehmigt oder abgelehnt haben.

1. Wechseln Sie im Admin Center zur Seite  >  "Abrechnungslizenzen", und wählen Sie dann die Registerkarte **"Anforderungen"** aus.<a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank"></a>
2. Wählen Sie **stattdessen "Vorhandenen Anforderungsprozess verwenden"** aus.
3. Geben Sie im rechten Bereich im **Meldungsfeld** die Nachricht ein, die Benutzern angezeigt werden soll, wenn sie eine Lizenz anfordern. Wenn Sie auch einen Link zu Ihrer Organisationsrichtlinie oder einer anderen Dokumentation hinzufügen möchten, geben Sie die URL in das Textfeld Link **zur Dokumentation (optional)** ein.
4. Klicken Sie auf **Speichern**.

Wenn Sie zur Liste **"Anforderungen"** zurückkehren, wird die Meldung angezeigt, **dass Sie Ihren eigenen Lizenzanforderungsprozess verwenden.** Um Änderungen an der Nachricht vorzunehmen, die an Benutzer gesendet wird, wählen Sie **stattdessen Ihren vorhandenen Anforderungsprozess verwenden** aus.

## <a name="stop-using-your-own-request-process"></a>Beenden der Verwendung Ihres eigenen Anforderungsprozesses

1. Wechseln Sie im Admin Center zur Seite  >  "Abrechnungslizenzen", und wählen Sie dann die Registerkarte **"Anforderungen"** aus.<a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank"></a>
2. Wählen Sie **stattdessen "Vorhandenen Anforderungsprozess verwenden"** aus.
3. Deaktivieren Sie im rechten Bereich das Kontrollkästchen **"Anforderungsprozess meiner Organisation verwenden".**
4. Klicken Sie auf **Speichern**.

## <a name="approve-or-deny-a-license-request"></a>Genehmigen oder Ablehnen einer Lizenzanforderung

1. Wechseln Sie im Admin Center zur Seite  >  "Abrechnungslizenzen", und wählen Sie dann die Registerkarte **"Anforderungen"** aus.<a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank"></a>
2. Wählen Sie die Zeile aus, die die Anforderung enthält, die Sie überprüfen möchten. Im rechten Bereich werden Details darüber angezeigt, welche Benutzer Lizenzen für das Produkt wünschen.
3. Um die gesamte Anforderung zu verweigern, wählen Sie **"Nicht genehmigen"** aus, und wählen Sie im Dialogfeld **"Nicht genehmigen"** aus.
4. Um einige Benutzer für die Anforderung zu verweigern, aber andere zu genehmigen, wählen Sie das X anhand des Namens der Benutzer aus, die Sie entfernen möchten. Ihre Namen werden unter **"Diesen Benutzern nicht zuweisen"** verschoben.
5. Wenn Sie über mehrere Produkte verfügen, wählen Sie unter **"Produkt auswählen"** das Produkt aus, für das Sie Lizenzen zuweisen möchten.
6. Um Benutzern den Zugriff auf bestimmte Apps und Dienste zu verweigern, erweitern **Sie "Apps und Dienste aktivieren oder deaktivieren"** und deaktivieren Sie dann die Kontrollkästchen für diejenigen, die Sie ausschließen möchten.
7. Geben Sie unten im Bereich eine optionale Nachricht in das Textfeld ein.
8. Wenn Sie fertig sind, wählen Sie **Genehmigen** aus. Im rechten Bereich werden die Details der Anforderung angezeigt.
9. Schließen Sie den rechten Bereich.
    Benutzer erhalten eine E-Mail, die besagt, dass ihre Anforderung genehmigt oder abgelehnt wurde.

## <a name="related-content"></a>Verwandte Inhalte

[Zuweisen von Lizenzen zu Benutzern ](../../admin/manage/assign-licenses-to-users.md) (Artikel)\
[Verschieben von Benutzern in ein anderes Abonnement](../subscriptions/move-users-different-subscription.md) (Artikel)\
[Abonnementlizenzen kaufen oder entfernen](buy-licenses.md) (Artikel)
