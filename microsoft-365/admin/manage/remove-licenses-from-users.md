---
title: Aufheben der Zuweisung von Benutzerlizenzen
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_TOC
- commerce
ms.custom:
- AdminSurgePortfolio
- manage_licenses
search.appverid:
- MET150
description: Erfahren Sie, wie Sie die Lizenzzuweisung von Benutzerkonten aufheern.
ms.date: 07/01/2020
ms.openlocfilehash: 6fb07883fdfd4f4a837890e3e8c4c04b2411772b
ms.sourcegitcommit: 0d709e9ab0d8d56c5fc11a921298f82e40e122c5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/05/2021
ms.locfileid: "50114477"
---
# <a name="unassign-licenses-from-users"></a>Aufheben der Zuweisung von Benutzerlizenzen

::: moniker range="o365-21vianet"

> [!NOTE]
> Das Admin Center wird geändert. Wenn Ihre Erfahrung nicht den hier aufgeführten Details entspricht, lesen Sie [über das neue Microsoft 365 Admin Center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true).

::: moniker-end

::: moniker range="o365-worldwide"

Sie können die Lizenzzuweisung von Benutzern auf der Seite **"Aktive** Benutzer" oder auf der Seite **"Lizenzen"** aufheern. Die methode, die Sie verwenden, hängt davon ab, ob Sie die Zuzuweisen von Produktlizenzen von bestimmten Benutzern oder Benutzerlizenzen von einem bestimmten Produkt aufheern möchten.

::: moniker-end

## <a name="before-you-begin"></a>Vorabinformationen

- Sie müssen ein globaler, Lizenz- und Benutzeradministrator sein, um die Lizenzzuweisung aufzuweisen. Weitere Informationen finden Sie unter [Informationen zu Administratorrollen von Microsoft 365](../add-users/about-admin-roles.md).
- Sie können [Lizenzen von Benutzerkonten mit Office 365 PowerShell entfernen](https://docs.microsoft.com/microsoft-365/enterprise/remove-licenses-from-user-accounts-with-microsoft-365-powershell).
- Sie können auch [Benutzerkonten löschen,](../add-users/delete-a-user.md) denen eine Lizenz zugewiesen wurde, um ihre Lizenz anderen Benutzern zur Verfügung zu stellen. Wenn Sie ein Benutzerkonto löschen, steht seine Lizenz sofort zur Verfügung, um sie einer anderen Person zuzuordnen.

::: moniker range="o365-worldwide"

## <a name="use-the-licenses-page-to-unassign-licenses"></a>Verwenden der Seite "Lizenzen", um die Lizenzzuweisung aufzuweisen

Wenn Sie die **Lizenzseite** verwenden, um die Lizenzzuweisung aufzuweisen, wird die Lizenzzuweisung für ein bestimmtes Produkt für bis zu 20 Benutzer entfernt.

1. Navigieren Sie im Admin Center zur Seite **Abrechnung** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Lizenzen</a>.
2. Wählen Sie das Produkt aus, für das Sie lizenzen zuweisen möchten.
3. Wählen Sie die Benutzer aus, für die Sie die Lizenzen zuweisen möchten.
4. Wählen **Sie "Lizenzen nicht zuweisen" aus.**
5. Wählen Sie **im Feld "Lizenzen zuweisen"** die Option **"Zuweisen" aus.**

::: moniker-end

::: moniker range="o365-worldwide"

## <a name="use-the-active-users-page-to-unassign-licenses"></a>Verwenden der Seite "Aktive Benutzer" zum Unentsigning von Lizenzen

Wenn Sie die Seite **"Aktive Benutzer"** verwenden, um die Lizenzzuweisung aufzuweisen, wird die Zuzuweisen von Produktlizenzen von Benutzern entfernt.

### <a name="unassign-licenses-from-one-user"></a>Zuweisen von Lizenzen von einem Benutzer
  
1. Wechseln Sie im Admin Center zu der Seite **Benutzer** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Aktive Benutzer</a>.
2. Wählen Sie die Zeile des Benutzers aus, für den Sie die Lizenz zuweisen möchten.
3. Wählen Sie im rechten Bereich **Lizenzen und Apps** aus.
4. Erweitern Sie **den Abschnitt "Lizenzen",** löschen Sie die Kontrollkästchen für die Lizenzen, die Sie zuweisen möchten, und wählen Sie dann **"Änderungen speichern" aus.**

::: moniker-end

::: moniker range="o365-germany"

## <a name="unassign-licenses-from-one-user"></a>Zuweisen von Lizenzen von einem Benutzer

1. Wechseln Sie im Admin Center zu der Seite **Benutzer** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Aktive Benutzer</a>.
2. Wählen Sie den Benutzer aus, für den Sie die Lizenz zuweisen möchten.
3. Wählen Sie auf der rechten Seite in der **Zeile "Produktlizenzen"** die Option **"Bearbeiten" aus.**
4. Schalten Sie **im** Bereich "Produktlizenzen" die Umschaltposition für die Lizenz, die Sie für den Benutzer nicht mehr zuweisen möchten, auf die Aus-Position.  Wenn Sie beispielsweise die Office 365 Enterprise E3-Lizenz deaktivieren, werden diese Lizenz und alle Dienste unter dieser Lizenz für den Benutzer entfernt.
5. Wählen Sie unten im Bereich **Produktlizenzen** nacheinander **Speichern** \> **Schließen** \> **Schließen** aus.

::: moniker-end

::: moniker range="o365-21vianet"

## <a name="unassign-licenses-from-one-user"></a>Zuweisen von Lizenzen von einem Benutzer

1. Wechseln Sie im Admin Center zu der Seite **Benutzer** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Aktive Benutzer</a>.
2. Wählen Sie den Benutzer aus, für den Sie die Lizenz zuweisen möchten.
3. Wählen Sie auf der rechten Seite in der **Zeile "Produktlizenzen"** die Option **"Bearbeiten" aus.**
4. Schalten Sie **im** Bereich "Produktlizenzen" die Umschaltposition für die Lizenz, die Sie für den Benutzer nicht mehr zuweisen möchten, auf die Aus-Position.  Wenn Sie beispielsweise die Office 365 Enterprise E3-Lizenz deaktivieren, werden diese Lizenz und alle Dienste unter dieser Lizenz für den Benutzer entfernt.
5. Wählen Sie unten im Bereich **Produktlizenzen** nacheinander **Speichern** \> **Schließen** \> **Schließen** aus.

::: moniker-end

::: moniker range="o365-worldwide"
###  <a name="unassign-licenses-from-multiple-users"></a>Unassign licenses from multiple users

1. Wechseln Sie im Admin Center zu der Seite **Benutzer** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Aktive Benutzer</a>.
2. Wählen Sie die Kreise neben den Namen der Benutzer aus, für die Sie lizenzen zuweisen möchten.
3. Wählen Sie am oberen Rand **Weitere Optionen** (...) und dann **Produktlizenzen verwalten** aus.
4. Wählen Sie im Bereich **Produktlizenzen verwalten** nacheinander **Vorhandenen Produktlizenzzuweisungen ersetzen** \> **Weiter** aus.
5. Aktivieren Sie unten im Bereich "Vorhandene  Produkte ersetzen" das Kontrollkästchen "Alle  Produktlizenzen aus den ausgewählten Benutzern entfernen" und dann "Schließen  \> **ersetzen".**

::: moniker-end

::: moniker range="o365-germany"

##  <a name="unassign-licenses-from-multiple-users"></a>Unassign licenses from multiple users

1. Wechseln Sie im Admin Center zu der Seite **Benutzer** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Aktive Benutzer</a>.
2. Aktivieren Sie die Kontrollkästchen neben den Namen der Benutzer, für die Sie die Lizenzzuweisung für alle Benutzer aufheern möchten.
3. Wählen Sie im Bereich **Massenaktionen** die Option **Produktlizenzen bearbeiten** aus.
4. Wählen Sie im Bereich **Vorhandene Produkte ersetzen** nacheinander **Vorhandene Produktlizenzverträge ersetzen** \> **Weiter** aus.
5. Aktivieren Sie unten im Bereich "Vorhandene  Produkte ersetzen" das Kontrollkästchen "Alle  Produktlizenzen aus den ausgewählten Benutzern entfernen" und dann "Schließen  \>  \> **ersetzen".**

::: moniker-end

::: moniker range="o365-21vianet"

##  <a name="unassign-licenses-from-multiple-users"></a>Unassign licenses from multiple users
  
1. Wechseln Sie im Admin Center zu der Seite **Benutzer** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Aktive Benutzer</a>.
2. Aktivieren Sie die Kontrollkästchen neben den Namen der Benutzer, für die Sie die Lizenzzuweisung für alle Benutzer aufheern möchten.
3. Wählen Sie im Bereich **Massenaktionen** die Option **Produktlizenzen bearbeiten** aus.
4. Wählen Sie im Bereich **Vorhandene Produkte ersetzen** nacheinander **Vorhandene Produktlizenzverträge ersetzen** \> **Weiter** aus.
5. Aktivieren Sie unten im Bereich "Vorhandene  Produkte ersetzen" das Kontrollkästchen "Alle  Produktlizenzen aus den ausgewählten Benutzern entfernen" und dann "Schließen  \>  \> **ersetzen".**

::: moniker-end

## <a name="what-happens-to-a-users-data-when-you-remove-their-license"></a>Was geschieht mit den Daten eines Benutzers, wenn Sie seine Lizenz entfernen?

- Wenn eine Lizenz von einem Benutzer entfernt wird, werden daten, die diesem Konto zugeordnet sind, 30 Tage lang gespeichert. Nach der 30-tägigen Nachfrist werden die Daten gelöscht und können nicht wiederhergestellt werden.
- In OneDrive for Business gespeicherte Dateien werden nur gelöscht, wenn der Benutzer aus dem Microsoft 365 Admin Center oder über die Active #A0 entfernt wird. Weitere Informationen finden Sie unter Aufbewahrung [und Löschung in OneDrive.](https://docs.microsoft.com/onedrive/retention-and-deletion)
- Wenn die Lizenz entfernt wird, kann das Postfach des Benutzers nicht mehr mit einem eDiscovery-Tool wie der Inhaltssuche oder Advanced eDiscovery durchsucht werden. Weitere Informationen finden Sie unter "Durchsuchen getrennter oder nicht lizenzierter Postfächer" in [der Inhaltssuche in Microsoft 365.](https://docs.microsoft.com/microsoft-365/compliance/content-search#searching-disconnected-or-de-licensed-mailboxes)
- Wenn Sie über ein Enterprise-Abonnement wie Office 365 Enterprise E3 verfügen, können Sie mit Exchange Online die Postfachdaten eines gelöschten Benutzerkontos mithilfe inaktiver [Postfächer beibehalten.](https://docs.microsoft.com/microsoft-365/compliance/inactive-mailboxes-in-office-365) Weitere Informationen finden Sie unter [Erstellen und Verwalten inaktiver Postfächer in Exchange Online.](https://docs.microsoft.com/microsoft-365/compliance/create-and-manage-inactive-mailboxes)
- Informationen dazu, wie Sie den Zugriff eines Benutzers auf Microsoft 365-Daten blockieren, nachdem seine Lizenz entfernt wurde, und wie Sie danach Zugriff auf die Daten erhalten, finden Sie unter Entfernen eines ehemaligen [Mitarbeiters.](../add-users/remove-former-employee.md)
- Wenn Sie die Lizenz eines Benutzers entfernen und weiterhin Office-Apps installiert sind, werden benutzern nicht [lizenzierte](https://support.microsoft.com/office/0d23d3c0-c19c-4b2f-9845-5344fedc4380) Produkte und Aktivierungsfehler in Office angezeigt, wenn sie office-Apps verwenden.

## <a name="next-steps"></a>Nächste Schritte

Wenn Sie die nicht verwendeten Lizenzen nicht anderen Benutzern [](../../commerce/licenses/buy-licenses.md) zuweisen [möchten,](../../managed-desktop/get-started/assign-licenses.md)sollten Sie die Lizenzen aus Ihrem Abonnement entfernen, damit Sie nicht für mehr Lizenzen bezahlen, als Sie benötigen.

## <a name="related-content"></a>Verwandte Inhalte

[Entfernen von Lizenzen aus Ihrem Abonnement](../../commerce/licenses/remove-licenses-from-subscription.md) (Artikel)\
[Zuweisen von Lizenzen zu Benutzern ](assign-licenses-to-users.md) (Artikel)\
[Informationen zu Abonnements und Lizenzen in Microsoft 365 Business](../../commerce/licenses/subscriptions-and-licenses.md) (Artikel)