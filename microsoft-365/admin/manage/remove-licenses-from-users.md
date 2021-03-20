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
description: Erfahren Sie, wie Sie lizenzen von Benutzerkonten wegzuweisen.
ms.date: 07/01/2020
ms.openlocfilehash: 858daaf0069ecba3e6ff65ce957462764b45c22c
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50915194"
---
# <a name="unassign-licenses-from-users"></a>Aufheben der Zuweisung von Benutzerlizenzen

::: moniker range="o365-21vianet"

> [!NOTE]
> Das Admin Center wird geändert. Wenn Ihre Erfahrung nicht den hier aufgeführten Details entspricht, lesen Sie [über das neue Microsoft 365 Admin Center](../microsoft-365-admin-center-preview.md?preserve-view=true&view=o365-21vianet).

::: moniker-end

::: moniker range="o365-worldwide"

Sie können lizenzen von Benutzern entweder auf der Seite **Aktive** Benutzer oder auf der Seite **Lizenzen zuweisen.** Die methode, die Sie verwenden, hängt davon ab, ob Sie Produktlizenzen von bestimmten Benutzern oder Benutzerlizenzen von einem bestimmten Produkt zuweisen möchten.

::: moniker-end

## <a name="before-you-begin"></a>Bevor Sie beginnen

- Sie müssen ein globaler, Lizenz-, Benutzeradministrator sein, um Lizenzen zuzuweisen. Weitere Informationen finden Sie unter [Informationen zu Administratorrollen von Microsoft 365](../add-users/about-admin-roles.md).
- Sie können [Lizenzen von Benutzerkonten mit Office 365 PowerShell entfernen](../../enterprise/remove-licenses-from-user-accounts-with-microsoft-365-powershell.md).
- Sie können auch [Benutzerkonten löschen,](../add-users/delete-a-user.md) denen eine Lizenz zugewiesen wurde, um ihre Lizenz anderen Benutzern zur Verfügung zu stellen. Wenn Sie ein Benutzerkonto löschen, steht deren Lizenz sofort zur Verfügung, um sie einer anderen Person zuzuordnen.

::: moniker range="o365-worldwide"

## <a name="use-the-licenses-page-to-unassign-licenses"></a>Verwenden der Seite Lizenzen zum Ensign von Lizenzen

Wenn Sie die Seite **Lizenzen** zum Zuweisen von Lizenzen verwenden, wird die Zuzuweisen von Lizenzen für ein bestimmtes Produkt für bis zu 20 Benutzer entfernt.

1. Navigieren Sie im Admin Center zur Seite **Abrechnung** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Lizenzen</a>.
2. Wählen Sie das Produkt aus, für das Sie Lizenzen zuweisen möchten.
3. Wählen Sie die Benutzer aus, für die Sie lizenzen nicht mehr zuweisen möchten.
4. Wählen **Sie Lizenzen nicht zuweisen aus.**
5. Wählen Sie **im Feld Lizenzen nicht zuweisen** die Option **Unassign aus.**

::: moniker-end

::: moniker range="o365-worldwide"

## <a name="use-the-active-users-page-to-unassign-licenses"></a>Verwenden der Seite Aktive Benutzer zum Zuweisen von Lizenzen

Wenn Sie die Seite **Aktive Benutzer** verwenden, um lizenzen zuzuweisen, wird die Zuzuweisen von Produktlizenzen von Benutzern entfernt.

### <a name="unassign-licenses-from-one-user"></a>Zuweisen von Lizenzen von einem Benutzer
  
1. Wechseln Sie im Admin Center zu der Seite **Benutzer** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Aktive Benutzer</a>.
2. Wählen Sie die Zeile des Benutzers aus, für den Sie die Lizenz zuweisen möchten.
3. Wählen Sie im rechten Bereich **Lizenzen und Apps** aus.
4. Erweitern Sie **den Abschnitt Lizenzen,** löschen Sie die Felder für die Lizenzen, die Sie zuweisen möchten, und wählen Sie **Dann Änderungen speichern aus.**

::: moniker-end

::: moniker range="o365-germany"

## <a name="unassign-licenses-from-one-user"></a>Zuweisen von Lizenzen von einem Benutzer

1. Wechseln Sie im Admin Center zu der Seite **Benutzer** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Aktive Benutzer</a>.
2. Wählen Sie den Benutzer aus, für den Sie die Lizenz nicht mehr zuweisen möchten.
3. Wählen Sie auf der rechten Seite in der **Zeile Produktlizenzen** die Option **Bearbeiten aus.**
4. Wechseln Sie **im** Bereich Produktlizenzen  zur Aus-Position für die Lizenz, die Sie für den Benutzer nicht mehr zuweisen möchten. Wenn Sie beispielsweise die Office 365 Enterprise E3-Lizenz deaktivieren, werden diese Lizenz und alle Dienste unter dieser Lizenz für den Benutzer nicht zugewiesen.
5. Wählen Sie unten im Bereich **Produktlizenzen** nacheinander **Speichern** \> **Schließen** \> **Schließen** aus.

::: moniker-end

::: moniker range="o365-21vianet"

## <a name="unassign-licenses-from-one-user"></a>Zuweisen von Lizenzen von einem Benutzer

1. Wechseln Sie im Admin Center zu der Seite **Benutzer** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Aktive Benutzer</a>.
2. Wählen Sie den Benutzer aus, für den Sie die Lizenz nicht mehr zuweisen möchten.
3. Wählen Sie auf der rechten Seite in der **Zeile Produktlizenzen** die Option **Bearbeiten aus.**
4. Wechseln Sie **im** Bereich Produktlizenzen  zur Aus-Position für die Lizenz, die Sie für den Benutzer nicht mehr zuweisen möchten. Wenn Sie beispielsweise die Office 365 Enterprise E3-Lizenz deaktivieren, werden diese Lizenz und alle Dienste unter dieser Lizenz für den Benutzer nicht zugewiesen.
5. Wählen Sie unten im Bereich **Produktlizenzen** nacheinander **Speichern** \> **Schließen** \> **Schließen** aus.

::: moniker-end

::: moniker range="o365-worldwide"
###  <a name="unassign-licenses-from-multiple-users"></a>Zuweisen von Lizenzen von mehreren Benutzern

1. Wechseln Sie im Admin Center zu der Seite **Benutzer** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Aktive Benutzer</a>.
2. Wählen Sie die Kreise neben den Namen der Benutzer aus, für die Sie Lizenzen zuweisen möchten.
3. Wählen Sie am oberen Rand **Weitere Optionen** (...) und dann **Produktlizenzen verwalten** aus.
4. Wählen Sie im Bereich **Produktlizenzen verwalten** nacheinander **Vorhandenen Produktlizenzzuweisungen ersetzen** \> **Weiter** aus.
5. Aktivieren Sie unten im Bereich Vorhandene  Produkte **ersetzen** das Kontrollkästchen Alle Produktlizenzen aus dem ausgewählten Benutzer entfernen, und wählen Sie dann **Schließen** \> **ersetzen aus.**

::: moniker-end

::: moniker range="o365-germany"

##  <a name="unassign-licenses-from-multiple-users"></a>Zuweisen von Lizenzen von mehreren Benutzern

1. Wechseln Sie im Admin Center zu der Seite **Benutzer** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Aktive Benutzer</a>.
2. Wählen Sie die Felder neben den Namen der Benutzer aus, für die Sie alle Lizenzen zuweisen möchten.
3. Wählen Sie im Bereich **Massenaktionen** die Option **Produktlizenzen bearbeiten** aus.
4. Wählen Sie im Bereich **Vorhandene Produkte ersetzen** nacheinander **Vorhandene Produktlizenzverträge ersetzen** \> **Weiter** aus.
5. Aktivieren Sie unten im Bereich Vorhandene  Produkte **ersetzen** das Kontrollkästchen Alle Produktlizenzen  aus dem ausgewählten Benutzer entfernen, und wählen Sie dann Schließen schließen \>  \> **ersetzen aus.**

::: moniker-end

::: moniker range="o365-21vianet"

##  <a name="unassign-licenses-from-multiple-users"></a>Zuweisen von Lizenzen von mehreren Benutzern
  
1. Wechseln Sie im Admin Center zu der Seite **Benutzer** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Aktive Benutzer</a>.
2. Wählen Sie die Felder neben den Namen der Benutzer aus, für die Sie alle Lizenzen zuweisen möchten.
3. Wählen Sie im Bereich **Massenaktionen** die Option **Produktlizenzen bearbeiten** aus.
4. Wählen Sie im Bereich **Vorhandene Produkte ersetzen** nacheinander **Vorhandene Produktlizenzverträge ersetzen** \> **Weiter** aus.
5. Aktivieren Sie unten im Bereich Vorhandene  Produkte **ersetzen** das Kontrollkästchen Alle Produktlizenzen  aus dem ausgewählten Benutzer entfernen, und wählen Sie dann Schließen schließen \>  \> **ersetzen aus.**

::: moniker-end

## <a name="what-happens-to-a-users-data-when-you-remove-their-license"></a>Was geschieht mit den Daten eines Benutzers, wenn Sie die Lizenz entfernen?

- Wenn eine Lizenz von einem Benutzer entfernt wird, werden daten, die diesem Konto zugeordnet sind, 30 Tage lang gespeichert. Nach der 30-tägigen Nachfrist werden die Daten gelöscht und können nicht wiederhergestellt werden.
- In OneDrive for Business gespeicherte Dateien werden nur gelöscht, wenn der Benutzer aus dem Microsoft 365 Admin Center gelöscht oder über die Active #A0 entfernt wird. Weitere Informationen finden Sie unter [OneDrive retention and deletion](/onedrive/retention-and-deletion).
- Wenn die Lizenz entfernt wird, kann das Postfach des Benutzers nicht mehr mit einem eDiscovery-Tool wie inhaltssuche oder advanced eDiscovery durchsucht werden. Weitere Informationen finden Sie unter "Suchen getrennter oder nicht lizenzierter Postfächer" [in Der Inhaltssuche in Microsoft 365](../../compliance/content-search.md#searching-disconnected-or-de-licensed-mailboxes).
- Wenn Sie über ein Enterprise-Abonnement wie Office 365 Enterprise E3 verfügen, können Sie mit Exchange Online die Postfachdaten eines gelöschten Benutzerkontos mithilfe inaktiver [Postfächer beibehalten.](../../compliance/inactive-mailboxes-in-office-365.md) Weitere Informationen finden Sie unter [Create and manage inactive mailboxes in Exchange Online](../../compliance/create-and-manage-inactive-mailboxes.md).
- Informationen zum Blockieren des Zugriffs eines Benutzers auf Microsoft 365-Daten nach dem Entfernen der Lizenz und zum anschließenden Zugriff auf die Daten finden Sie unter Entfernen eines ehemaligen [Mitarbeiters.](../add-users/remove-former-employee.md)
- Wenn Sie die Lizenz eines Benutzers entfernen und weiterhin Office-Apps installiert sind, werden [unlizenzierte Produkt-](https://support.microsoft.com/office/0d23d3c0-c19c-4b2f-9845-5344fedc4380) und Aktivierungsfehler in Office angezeigt, wenn sie Office-Apps verwenden.

## <a name="next-steps"></a>Nächste Schritte

Wenn Sie die nicht verwendeten Lizenzen nicht anderen Benutzern [](../../commerce/licenses/buy-licenses.md) erneut zuweisen [möchten,](../../managed-desktop/get-started/assign-licenses.md)sollten Sie die Lizenzen aus Ihrem Abonnement entfernen, damit Sie nicht für mehr Lizenzen bezahlen, als Sie benötigen.

## <a name="related-content"></a>Verwandte Inhalte

[Entfernen von Lizenzen aus Ihrem Abonnement](../../commerce/licenses/buy-licenses.md) (Artikel)\
[Zuweisen von Lizenzen zu Benutzern ](assign-licenses-to-users.md) (Artikel)\
[Verstehen von Abonnements und Lizenzen in Microsoft 365 Business](../../commerce/licenses/subscriptions-and-licenses.md) (Artikel)