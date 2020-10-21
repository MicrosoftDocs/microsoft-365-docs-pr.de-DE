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
description: Erfahren Sie, wie Sie die Zuweisung von Lizenzen von Benutzerkonten aufheben.
ms.date: 07/01/2020
ms.openlocfilehash: 455348e7dba20913e54e5a4059755f9391644e03
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/21/2020
ms.locfileid: "48645095"
---
# <a name="unassign-licenses-from-users"></a>Aufheben der Zuweisung von Benutzerlizenzen

::: moniker range="o365-21vianet"

> [!NOTE]
> Das Admin Center wird geändert. Wenn Ihre Erfahrung nicht den hier aufgeführten Details entspricht, lesen Sie [über das neue Microsoft 365 Admin Center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).

::: moniker-end

::: moniker range="o365-worldwide"

Sie können die Zuweisung von Lizenzen von Benutzern auf der Seite " **aktive Benutzer** " oder auf der Seite " **Lizenzen** " aufheben. Die verwendete Methode hängt davon ab, ob Sie Produktlizenzen von bestimmten Benutzern aufheben oder die Zuweisung von Benutzerlizenzen von einem bestimmten Produkt aufheben möchten.

::: moniker-end

## <a name="before-you-begin"></a>Bevor Sie beginnen:

- Zum Aufheben der Zuweisung von Lizenzen müssen Sie ein globaler, Lizenz-, Benutzer-Admin sein. Weitere Informationen finden Sie unter [Informationen zu Administratorrollen von Microsoft 365](../add-users/about-admin-roles.md).
- Sie können [Lizenzen von Benutzerkonten mit Office 365 PowerShell entfernen](https://docs.microsoft.com/microsoft-365/enterprise/remove-licenses-from-user-accounts-with-microsoft-365-powershell).
- Sie können auch [Benutzerkonten löschen](../add-users/delete-a-user.md) , denen eine Lizenz zugewiesen wurde, um Ihre Lizenz anderen Benutzern zur Verfügung zu stellen. Wenn Sie ein Benutzerkonto löschen, ist Ihre Lizenz sofort verfügbar, um Sie einer anderen Person zuzuweisen.

::: moniker range="o365-worldwide"

## <a name="use-the-licenses-page-to-unassign-licenses"></a>Verwenden der Seite "Lizenzen" zum Aufheben der Zuweisung von Lizenzen

Wenn Sie die Zuweisung von Lizenzen mithilfe der Seite **Lizenzen** aufheben, werden Lizenzen für ein bestimmtes Produkt für bis zu 20 Benutzer aufheben.

1. Navigieren Sie im Admin Center zur Seite **Abrechnung** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Lizenzen</a>.
2. Wählen Sie das Produkt aus, für das Sie die Zuweisung von Lizenzen aufheben möchten.
3. Wählen Sie die Benutzer aus, für die Sie die Zuweisung von Lizenzen aufheben möchten.
4. Wählen Sie Lizenzen für Aufheben der **Zuweisung**aus.
5. **Wählen Sie**im Feld **Zuweisungs Lizenzen** aufheben aus.

::: moniker-end

::: moniker range="o365-worldwide"

## <a name="use-the-active-users-page-to-unassign-licenses"></a>Verwenden der Seite "aktive Benutzer" zum Aufheben der Zuweisung von Lizenzen

Wenn Sie die Zuweisung von Lizenzen mithilfe der Seite **aktive Benutzer** aufheben, heben Sie die Zuweisung von Produktlizenzen von Benutzern auf.

### <a name="unassign-licenses-from-one-user"></a>Aufheben der Zuweisung von Lizenzen von einem Benutzer
  
1. Wechseln Sie im Admin Center zu der Seite **Benutzer** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Aktive Benutzer</a>.
2. Wählen Sie die Zeile des Benutzers aus, für den Sie die Zuweisung einer Lizenz aufheben möchten.
3. Wählen Sie im rechten Bereich **Lizenzen und Apps** aus.
4. Erweitern Sie den Abschnitt **Lizenzen** , deaktivieren Sie die Felder für die Lizenzen, die Sie aufheben möchten, und wählen Sie dann **Änderungen speichern**aus.

::: moniker-end

::: moniker range="o365-germany"

## <a name="unassign-licenses-from-one-user"></a>Aufheben der Zuweisung von Lizenzen von einem Benutzer

1. Wechseln Sie im Admin Center zu der Seite **Benutzer** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Aktive Benutzer</a>.
2. Wählen Sie den Benutzer aus, für den Sie die Zuweisung der Lizenz aufheben möchten.
3. Wählen Sie auf der rechten Seite in der Zeile **Produktlizenzen** die Option **Bearbeiten**aus.
4. Wechseln Sie im Bereich **Produktlizenzen** die Umschaltfläche in die Position aus für die Lizenz, die Sie dem Benutzer **aufheben** möchten. Wenn Sie beispielsweise die Office 365 Enterprise E3-Lizenz deaktivieren, wird die Zuweisung dieser Lizenz und aller Dienste unter dieser Lizenz für diesen Benutzer deaktiviert.
5. Wählen Sie unten im Bereich **Produktlizenzen** nacheinander **Speichern** \> **Schließen** \> **Schließen** aus.

::: moniker-end

::: moniker range="o365-21vianet"

## <a name="unassign-licenses-from-one-user"></a>Aufheben der Zuweisung von Lizenzen von einem Benutzer

1. Wechseln Sie im Admin Center zu der Seite **Benutzer** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Aktive Benutzer</a>.
2. Wählen Sie den Benutzer aus, für den Sie die Zuweisung der Lizenz aufheben möchten.
3. Wählen Sie auf der rechten Seite in der Zeile **Produktlizenzen** die Option **Bearbeiten**aus.
4. Wechseln Sie im Bereich **Produktlizenzen** die Umschaltfläche in die Position aus für die Lizenz, die Sie dem Benutzer **aufheben** möchten. Wenn Sie beispielsweise die Office 365 Enterprise E3-Lizenz deaktivieren, wird die Zuweisung dieser Lizenz und aller Dienste unter dieser Lizenz für diesen Benutzer deaktiviert.
5. Wählen Sie unten im Bereich **Produktlizenzen** nacheinander **Speichern** \> **Schließen** \> **Schließen** aus.

::: moniker-end

::: moniker range="o365-worldwide"
###  <a name="unassign-licenses-from-multiple-users"></a>Aufheben der Zuweisung von Lizenzen von mehreren Benutzern

1. Wechseln Sie im Admin Center zu der Seite **Benutzer** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Aktive Benutzer</a>.
2. Wählen Sie die Kreise neben den Namen der Benutzer aus, für die Sie die Zuweisung von Lizenzen aufheben möchten.
3. Wählen Sie am oberen Rand **Weitere Optionen** (...) und dann **Produktlizenzen verwalten** aus.
4. Wählen Sie im Bereich **Produktlizenzen verwalten** nacheinander **Vorhandenen Produktlizenzzuweisungen ersetzen** \> **Weiter** aus.
5. Aktivieren Sie am unteren Rand des Bereichs **vorhandene Produkte ersetzen** das Kontrollkästchen **alle Produktlizenzen aus dem ausgewählten Benutzer entfernen** , und wählen Sie dann **Replace** \> **Schließen**ersetzen aus.

::: moniker-end

::: moniker range="o365-germany"

##  <a name="unassign-licenses-from-multiple-users"></a>Aufheben der Zuweisung von Lizenzen von mehreren Benutzern

1. Wechseln Sie im Admin Center zu der Seite **Benutzer** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Aktive Benutzer</a>.
2. Aktivieren Sie die Kontrollkästchen neben den Namen der Benutzer, für die Sie die Zuweisung aller Lizenzen aufheben möchten.
3. Wählen Sie im Bereich **Massenaktionen** die Option **Produktlizenzen bearbeiten** aus.
4. Wählen Sie im Bereich **Vorhandene Produkte ersetzen** nacheinander **Vorhandene Produktlizenzverträge ersetzen** \> **Weiter** aus.
5. Aktivieren Sie am unteren Rand des Bereichs **vorhandene Produkte ersetzen** das Kontrollkästchen **alle Produktlizenzen aus dem ausgewählten Benutzer entfernen** , und wählen Sie dann **Replace** \> **Close** \> **Close**ersetzen aus.

::: moniker-end

::: moniker range="o365-21vianet"

##  <a name="unassign-licenses-from-multiple-users"></a>Aufheben der Zuweisung von Lizenzen von mehreren Benutzern
  
1. Wechseln Sie im Admin Center zu der Seite **Benutzer** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Aktive Benutzer</a>.
2. Aktivieren Sie die Kontrollkästchen neben den Namen der Benutzer, für die Sie die Zuweisung aller Lizenzen aufheben möchten.
3. Wählen Sie im Bereich **Massenaktionen** die Option **Produktlizenzen bearbeiten** aus.
4. Wählen Sie im Bereich **Vorhandene Produkte ersetzen** nacheinander **Vorhandene Produktlizenzverträge ersetzen** \> **Weiter** aus.
5. Aktivieren Sie am unteren Rand des Bereichs **vorhandene Produkte ersetzen** das Kontrollkästchen **alle Produktlizenzen aus dem ausgewählten Benutzer entfernen** , und wählen Sie dann **Replace** \> **Close** \> **Close**ersetzen aus.

::: moniker-end

## <a name="what-happens-to-a-users-data-when-you-remove-their-license"></a>Was geschieht mit den Daten eines Benutzers, wenn er seine Lizenz entfernt?

- Wenn eine Lizenz von einem Benutzer entfernt wird, werden Daten, die diesem Konto zugeordnet sind, 30 Tage lang aufbewahrt. Nach Ablauf der 30-tägigen Kulanzzeit werden die Daten gelöscht und können nicht wiederhergestellt werden.
- In OneDrive für Unternehmen gespeicherte Dateien werden nicht gelöscht, es sei denn, der Benutzer wird aus dem Microsoft 365 Admin Center gelöscht oder durch Active Directory Synchronisierung entfernt. Weitere Informationen finden Sie unter [OneDrive Retention and Deletion](https://docs.microsoft.com/onedrive/retention-and-deletion).
- Wenn die Lizenz entfernt wird, kann das Postfach des Benutzers nicht mehr mithilfe eines eDiscovery-Tools wie der Inhaltssuche oder Advanced eDiscovery durchsucht werden. Weitere Informationen finden Sie unter "Durchsuchen von getrennten oder delizenzierten Postfächern" in der [Inhaltssuche in Microsoft 365](https://docs.microsoft.com/microsoft-365/compliance/content-search#searching-disconnected-or-de-licensed-mailboxes).
- Wenn Sie über ein Enterprise-Abonnement wie Office 365 Enterprise E3 verfügen, können Sie mit Exchange Online die Postfachdaten eines gelöschten Benutzerkontos mithilfe [inaktiver Postfächer](https://docs.microsoft.com/microsoft-365/compliance/inactive-mailboxes-in-office-365)beibehalten. Weitere Informationen finden Sie unter [Erstellen und Verwalten inaktiver Postfächer in Exchange Online](https://docs.microsoft.com/microsoft-365/compliance/create-and-manage-inactive-mailboxes).
- Informationen darüber, wie Sie den Zugriff eines Benutzers auf Microsoft 365-Daten nach dem Entfernen Ihrer Lizenz und wie Sie später auf die Daten zugreifen können, finden Sie unter [Entfernen eines ehemaligen Mitarbeiters](../add-users/remove-former-employee.md).
- Wenn Sie die Lizenz eines Benutzers entfernen und weiterhin Office-Apps installiert sind, werden bei der Verwendung von Office-Apps nicht [lizenzierte Produkt-und Aktivierungsfehler in Office](https://support.microsoft.com/office/0d23d3c0-c19c-4b2f-9845-5344fedc4380) angezeigt.

## <a name="next-steps"></a>Nächste Schritte

Wenn Sie nicht [die nicht verwendeten Lizenzen anderen Benutzern zuweisen](../../managed-desktop/get-started/assign-licenses.md)möchten, sollten Sie [die Lizenzen aus Ihrem Abonnement entfernen](../../commerce/licenses/buy-licenses.md) , damit Sie nicht mehr Lizenzen als erforderlich bezahlen.

## <a name="related-content"></a>Verwandte Inhalte

[Entfernen von Lizenzen aus Ihrem Abonnement](../../commerce/licenses/remove-licenses-from-subscription.md) (Artikel) \
[Zuweisen von Lizenzen zu Benutzern](assign-licenses-to-users.md) (Artikel) \
Grund [Legendes zu Abonnements und Lizenzen in Microsoft 365 for Business](../../commerce/licenses/subscriptions-and-licenses.md) (Artikel)