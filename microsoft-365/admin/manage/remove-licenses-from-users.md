---
title: Aufheben der Zuweisung von Benutzerlizenzen
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
ms.reviewer: sinakassaw, nicholak
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- okr_smb
- manage_licenses
- commerce_licensing
- AdminTemplateSet
search.appverid: MET150
description: Die Methode zum Aufheben der Zuweisung von Produktlizenzen hängt davon ab, ob Sie die Zuweisung von Lizenzen von bestimmten Benutzern oder von einem bestimmten Produkt aufheben.
ms.date: 06/07/2021
ms.openlocfilehash: 8a67d7e690ff07631f696a97d6ed59925bc871df
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/12/2021
ms.locfileid: "53392491"
---
# <a name="unassign-licenses-from-users"></a>Aufheben der Zuweisung von Benutzerlizenzen

Sie können die Zuweisung von Lizenzen von Benutzern entweder auf der Seite **"Aktive Benutzer"** oder auf der Seite **"Lizenzen"** aufheben. Die verwendete Methode hängt davon ab, ob Sie die Zuweisung von Produktlizenzen von bestimmten Benutzern aufheben oder die Zuweisung von Benutzerlizenzen für ein bestimmtes Produkt aufheben möchten.

> [!NOTE]
> Als Administrator können Sie keine Lizenzen für ein Self-Service-Kaufabonnement zuweisen oder aufheben, die von einem Benutzer in Ihrer Organisation erworben wurden. Sie können ein [Self-Service-Kaufabonnement übernehmen](../../commerce/subscriptions/manage-self-service-purchases-admins.md#take-over-a-self-service-purchase-subscription)und dann Lizenzen zuweisen oder die Zuweisung von Lizenzen kündigen.

## <a name="before-you-begin"></a>Bevor Sie beginnen:

- Sie müssen ein globaler, Lizenz- und Benutzeradministrator sein, um die Zuweisung von Lizenzen aufzuheben. Weitere Informationen finden Sie unter [Informationen zu Administratorrollen von Microsoft 365](../add-users/about-admin-roles.md).
- Sie können [Lizenzen von Benutzerkonten mit Office 365 PowerShell entfernen](../../enterprise/remove-licenses-from-user-accounts-with-microsoft-365-powershell.md).
- Sie können auch [Benutzerkonten löschen,](../add-users/delete-a-user.md) denen eine Lizenz zugewiesen wurde, um ihre Lizenz anderen Benutzern zur Verfügung zu stellen. Wenn Sie ein Benutzerkonto löschen, ist die Lizenz sofort verfügbar, um es einer anderen Person zuzuweisen.

## <a name="use-the-licenses-page-to-unassign-licenses"></a>Verwenden der Seite "Lizenzen" zum Aufheben der Zuweisung von Lizenzen

Wenn Sie die Seite **"Lizenzen"** verwenden, um die Zuweisung von Lizenzen aufzuheben, heben Sie die Zuweisung von Lizenzen für ein bestimmtes Produkt für bis zu 20 Benutzer auf.

::: moniker range="o365-worldwide"

1. Navigieren Sie im Admin Center zur Seite **Abrechnung** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Lizenzen</a>.

::: moniker-end

::: moniker range="o365-germany"

 1. Navigieren Sie im Admin Center zur Seite **Abrechnung** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=848038" target="_blank">Lizenzen</a>.

::: moniker-end

::: moniker range="o365-21vianet"

 1. Navigieren Sie im Admin Center zur Seite **Abrechnung** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850625" target="_blank">Lizenzen</a>.

::: moniker-end

2. Wählen Sie das Produkt aus, für das Sie die Zuweisung von Lizenzen aufheben möchten.
3. Wählen Sie die Benutzer aus, für die Sie die Zuweisung von Lizenzen aufheben möchten.
4. Wählen Sie **"Lizenzen aufheben" aus.**
5. Wählen Sie im Feld **"Lizenzen aufheben"** die Option **"Zuweisung aufheben"** aus.

## <a name="use-the-active-users-page-to-unassign-licenses"></a>Verwenden der Seite "Aktive Benutzer" zum Aufheben der Zuweisung von Lizenzen

Wenn Sie die Seite **"Aktive Benutzer"** verwenden, um die Zuweisung von Lizenzen aufzuheben, heben Sie die Zuweisung von Produktlizenzen von Benutzern auf.

### <a name="unassign-licenses-from-one-user"></a>Aufheben der Zuweisung von Lizenzen von einem Benutzer

::: moniker range="o365-worldwide"

1. Wechseln Sie im Admin Center zu der Seite **Benutzer** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Aktive Benutzer</a>.

::: moniker-end

::: moniker range="o365-germany"

 1. Wechseln Sie im Admin Center zu der Seite **Benutzer** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Aktive Benutzer</a>.

::: moniker-end

::: moniker range="o365-21vianet"

 1. Wechseln Sie im Admin Center zu der Seite **Benutzer** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Aktive Benutzer</a>.

::: moniker-end

2. Wählen Sie die Zeile des Benutzers aus, für den Sie die Zuweisung einer Lizenz aufheben möchten.
3. Wählen Sie im rechten Fensterbereich **Lizenzen und Apps** aus.
4. Erweitern Sie den Abschnitt **"Lizenzen",** deaktivieren Sie die Felder für die Lizenzen, die Sie die Zuweisung aufheben möchten, und wählen Sie dann **"Änderungen speichern"** aus.

### <a name="unassign-licenses-from-multiple-users"></a>Aufheben der Zuweisung von Lizenzen von mehreren Benutzern

::: moniker range="o365-worldwide"

1. Wechseln Sie im Admin Center zu der Seite **Benutzer** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Aktive Benutzer</a>.

::: moniker-end

::: moniker range="o365-germany"

 1. Wechseln Sie im Admin Center zu der Seite **Benutzer** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Aktive Benutzer</a>.

::: moniker-end

::: moniker range="o365-21vianet"

 1. Wechseln Sie im Admin Center zu der Seite **Benutzer** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Aktive Benutzer</a>.

::: moniker-end

2. Wählen Sie die Kreise neben den Namen der Benutzer aus, für die Sie die Zuweisung von Lizenzen aufheben möchten.
3. Wählen Sie oben **Produktlizenzen verwalten** aus.
4. Wählen Sie im Bereich **"Produktlizenzen verwalten"** die Option **"Alle**  >  **Änderungen speichern aufheben"** aus.
5. Wählen Sie unten im Bereich **"Fertig"** aus.  

## <a name="what-happens-to-a-users-data-when-you-remove-their-license"></a>Was geschieht mit den Daten eines Benutzers, wenn Sie seine Lizenz entfernen?

- Wenn eine Lizenz von einem Benutzer entfernt wird, werden Exchange Onlinedaten, die diesem Konto zugeordnet sind, 30 Tage lang aufbewahrt. Nach Ablauf der 30-tägigen Nachfrist werden die Daten gelöscht und können nicht wiederhergestellt werden.
- In OneDrive for Business gespeicherte Dateien werden nicht gelöscht, es sei denn, der Benutzer wird aus dem Microsoft 365 Admin Center gelöscht oder über die Active Directory-Synchronisierung entfernt. Weitere Informationen finden Sie unter [OneDrive Aufbewahrung und Löschung.](/onedrive/retention-and-deletion)
- Wenn die Lizenz entfernt wird, kann das Postfach des Benutzers nicht mehr mithilfe eines eDiscovery-Tools wie inhaltssuche oder Advanced eDiscovery durchsucht werden. Weitere Informationen finden Sie unter "Durchsuchen getrennter oder nicht lizenzierter Postfächer" in der [Inhaltssuche in Microsoft 365.](../../compliance/content-search.md)
- Wenn Sie über ein Enterprise Abonnement verfügen, z. B. Office 365 Enterprise E3, können Sie mit Exchange Online die Postfachdaten eines gelöschten Benutzerkontos mithilfe [inaktiver Postfächer](../../compliance/inactive-mailboxes-in-office-365.md)beibehalten. Weitere Informationen finden Sie unter [Erstellen und Verwalten inaktiver Postfächer in Exchange Online.](../../compliance/create-and-manage-inactive-mailboxes.md)
- Informationen dazu, wie Sie den Zugriff eines Benutzers auf Microsoft 365 Daten blockieren, nachdem die Lizenz entfernt wurde, und wie Sie danach Zugriff auf die Daten erhalten, finden Sie unter [Entfernen eines ehemaligen Mitarbeiters.](../add-users/remove-former-employee.md)
- Wenn Sie die Lizenz eines Benutzers entfernen und er weiterhin Office Apps installiert hat, werden in Office fehler [beim](https://support.microsoft.com/office/0d23d3c0-c19c-4b2f-9845-5344fedc4380) Verwenden Office Apps angezeigt.

## <a name="next-steps"></a>Nächste Schritte

Wenn Sie [die nicht verwendeten Lizenzen](../../managed-desktop/get-started/assign-licenses.md)nicht anderen Benutzern zuweisen möchten, sollten Sie [die Lizenzen aus Ihrem Abonnement entfernen,](../../commerce/licenses/buy-licenses.md) damit Sie nicht mehr Lizenzen bezahlen, als Sie benötigen.

## <a name="related-content"></a>Verwandte Inhalte

[Entfernen von Lizenzen aus Ihrem Abonnement](../../commerce/licenses/buy-licenses.md) (Artikel)\
[Zuweisen von Lizenzen zu Benutzern ](assign-licenses-to-users.md) (Artikel)\
[Grundlegendes zu Abonnements und Lizenzen in Microsoft 365 for Business](../../commerce/licenses/subscriptions-and-licenses.md) (Artikel)
