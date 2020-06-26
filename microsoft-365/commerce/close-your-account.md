---
title: Schließen Ihres Kontos
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- commerce
ms.custom:
- AdminSurgePortfolio
- fwlink 2133922 to Delete subscription heading
search.appverid:
- MET150
description: Erfahren Sie, wie Sie Ihr Konto bei Microsoft schließen.
ms.openlocfilehash: a92b9f2053d9acf4e8233bee7a42047f51288943
ms.sourcegitcommit: ab10c042e5e9c6a7b2afef930ab0d247a6aa275d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/26/2020
ms.locfileid: "44898921"
---
# <a name="close-your-account"></a>Schließen Ihres Kontos

::: moniker range="o365-21vianet"

> [!NOTE]
> Das Admin Center wird geändert. Wenn Ihre Erfahrung nicht den hier aufgeführten Details entspricht, lesen Sie [über das neue Microsoft 365 Admin Center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).

::: moniker-end

Wenn Sie Ihr Microsoft-Konto schließen, werden alle Informationen zu Ihrem Konto gelöscht. Diese Informationen umfassen Abonnements, Lizenzen, Zahlungsmethoden, Benutzer und Benutzerdaten. Bevor Sie diesen Prozess starten, müssen Sie sicherstellen, dass alle Daten gesichert werden, die Sie beibehalten möchten.

## <a name="step-1-delete-users"></a>Schritt 1: Löschen von Benutzern

Löschen Sie alle Benutzer mit Ausnahme eines globalen Administrators, der die Schritte zum Schließen des Kontos abgeschlossen hat. Bevor Sie das Verzeichnis am Ende dieses Prozesses löschen können, müssen Sie alle anderen Benutzer löschen.

Wenn Benutzer lokal synchronisiert werden, deaktivieren Sie zunächst die Synchronisierung, und löschen Sie dann die Benutzer im Cloud-Verzeichnis mithilfe des Azure-Portals oder der Azure PowerShell-Cmdlets.

Informationen zum Löschen von Benutzern finden Sie unter <a href="https://docs.microsoft.com/office365/admin/add-users/delete-a-user?view=o365-worldwide#user-management-admin-delete-one-or-more-users-from-office-365">Benutzer Verwaltungs Administrator: Löschen eines oder mehrerer Benutzer</a>.

Sie können auch das Cmdlet <a href="https://go.microsoft.com/fwlink/?linkid=842230">Remove-MsolUser</a> PowerShell verwenden, um Benutzer in Massen zu löschen.

Wenn Ihre Organisation Active Directory verwendet, die mit Azure AD synchronisiert werden, löschen Sie stattdessen das Benutzerkonto aus Active Directory. Anweisungen finden Sie unter <a href="https://docs.microsoft.com/azure/active-directory/users-groups-roles/users-bulk-delete">Massenlöschung von Benutzern in Azure Active Directory</a>.

## <a name="step-2-cancel-all-active-subscriptions"></a>Schritt 2: Abbrechen aller aktiven Abonnements

1. Wechseln Sie im Admin Center zur Seite **Fakturierung**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">ihrer Produkte</a> .

2. Wenn sich die Liste Abonnements in der **Tabellen** Ansicht befindet, wählen Sie auf der rechten Seite **Karten**aus.

3. Suchen Sie ein aktives Abonnement, und wählen Sie im Abschnitt **Einstellungen & Aktionen** die Option **Abonnement kündigen**aus.

4. Befolgten Sie die Anweisungen, um den Vorgang abzuschließen.

5. Wiederholen Sie die Schritte 1 bis 4, um alle aktiven Abonnements abzubrechen.

## <a name="step-3-delete-all-disabled-subscriptions"></a>Schritt 3: Löschen aller deaktivierten Abonnements

1. Wechseln Sie im Admin Center zur Seite **Fakturierung**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">ihrer Produkte</a> .

2. Wenn sich die Liste Abonnements in der **Tabellen** Ansicht befindet, wählen Sie auf der rechten Seite **Karten**aus.

3. Wählen Sie neben **Abonnementstatus**die Option **deaktiviert**aus.

4. Suchen Sie nach einem deaktivierten Abonnement, und wählen Sie im Abschnitt **Einstellungen & Aktionen** die Option **Löschen**aus.

5. Aktivieren Sie im Dialogfeld **Abonnement löschen** das Kontrollkästchen **Ich verstehe den Einfluss** , und wählen Sie dann **Abonnement löschen**aus.

6. Wiederholen Sie für jedes deaktivierte Abonnement die Schritte 4 und 5, bis alle Abonnements gelöscht wurden.

## <a name="step-4-disable-multi-factor-authentication"></a>Schritt 4: Deaktivieren der mehrstufigen Authentifizierung

1. Wechseln Sie im Admin Center zur Seite **Benutzer**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">aktive Benutzer</a> .

2. Wählen Sie die mehrstufige **Authentifizierung**aus.

3. Deaktivieren Sie auf der Seite mehrstufige Authentifizierung alle Konten mit Ausnahme des globalen Administratorkontos, das Sie derzeit verwenden.

Sie können auch <a href="https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-userstates#change-state-using-powershell">PowerShell verwenden, um die mehrstufige Authentifizierung für mehrere Benutzer zu deaktivieren</a>.

## <a name="step-5-delete-the-directory-in-azure-active-directory"></a>Schritt 5: Löschen des Verzeichnisses in Azure Active Directory

1. Melden Sie sich beim <a href="https://aad.portal.azure.com/" target="_blank">Azure AD Admin Center</a> mit einem globalen Administrator Konto an.

2. Wählen Sie **Azure Active Directory** aus.

3. Wechseln Sie zu dem Verzeichnis, das Sie löschen möchten.

4. Wählen Sie **Verzeichnis löschen**aus.

5. Wenn Ihr Verzeichnis mindestens eine Überprüfung ausfällt, wird ein Link zu weiteren Informationen zum übergeben der Prüfungen angezeigt. Nachdem Sie alle Prüfungen übergeben haben, wählen Sie **Delete** aus, um den Vorgang abzuschließen.

Nachdem Sie diesen letzten Schritt abgeschlossen haben, wird Ihr Konto bei Microsoft geschlossen und gelöscht.
