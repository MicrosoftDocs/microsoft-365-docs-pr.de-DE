---
title: Schließen Ihres Kontos
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
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
ms.openlocfilehash: bdcf4408ddc9c198fab1d68b4c096fad9059b975
ms.sourcegitcommit: 20d1158c54a5058093eb8aac23d7e4dc68054688
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2020
ms.locfileid: "49376317"
---
# <a name="close-your-account"></a>Schließen Ihres Kontos

::: moniker range="o365-21vianet"

> [!NOTE]
> Das Admin Center wird geändert. Wenn Ihre Erfahrung nicht den hier aufgeführten Details entspricht, lesen Sie [über das neue Microsoft 365 Admin Center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true).

::: moniker-end

Wenn Sie Ihr Microsoft-Konto schließen, werden alle Informationen zu Ihrem Konto gelöscht. Diese Informationen umfassen Abonnements, Lizenzen, Zahlungsmethoden, Benutzer und Benutzerdaten.

## <a name="before-you-begin"></a>Bevor Sie beginnen

Bevor Sie diesen Vorgang starten, stellen Sie sicher, dass Sie alle Daten gesichert haben, die Sie beibehalten möchten.

Sie müssen ein globaler oder abrechnungsadministrator sein, um die Aufgaben in diesem Artikel durchführen zu können. Weitere Informationen finden Sie unter [Informationen zu Administratorrollen](../admin/add-users/about-admin-roles.md).

## <a name="step-1-delete-users"></a>Schritt 1: Löschen von Benutzern

Löschen Sie alle Benutzer mit Ausnahme eines globalen Administrators. Der globale Administrator schließt die Schritte zum Schließen des Kontos ab. Bevor Sie das Verzeichnis am Ende dieses Prozesses löschen können, müssen Sie alle anderen Benutzer löschen.

Wenn Benutzer lokal synchronisiert werden, deaktivieren Sie zunächst die Synchronisierung, und löschen Sie dann die Benutzer im Cloud-Verzeichnis mithilfe des Azure-Portals oder der Azure PowerShell-Cmdlets.

Informationen zum Löschen von Benutzern finden Sie unter <a href="https://docs.microsoft.com/office365/admin/add-users/delete-a-user?view=o365-worldwide#user-management-admin-delete-one-or-more-users-from-office-365">Benutzer Verwaltungs Administrator: Löschen eines oder mehrerer Benutzer</a>.

Sie können auch das Cmdlet <a href="https://go.microsoft.com/fwlink/?linkid=842230">Remove-MsolUser</a> PowerShell verwenden, um Benutzer in Massen zu löschen.

Wenn Ihre Organisation Active Directory verwendet, die mit Microsoft Azure Active Directory synchronisiert (Azure AD), löschen Sie stattdessen das Benutzerkonto aus Active Directory. Anweisungen finden Sie unter <a href="https://docs.microsoft.com/azure/active-directory/users-groups-roles/users-bulk-delete">Massenlöschung von Benutzern in Azure Active Directory</a>.

## <a name="step-2-cancel-all-active-subscriptions"></a>Schritt 2: Abbrechen aller aktiven Abonnements

1. Navigieren Sie im Admin Center zur Seite **Abrechnung** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Ihre Produkte</a>.
2. Suchen Sie auf der Registerkarte " **Produkte** " ein aktives Abonnement. Wählen Sie **Weitere Aktionen** (drei Punkte) und dann **Abonnement kündigen** aus.
3. Wählen Sie im Bereich **Abonnement kündigen** einen Grund aus, warum Sie kündigen. Geben Sie optional Feedback.
4. Klicken Sie auf **Speichern**.
5. Wiederholen Sie die Schritte 1 bis 4, um alle aktiven Abonnements abzubrechen.

## <a name="step-3-delete-all-disabled-subscriptions"></a>Schritt 3: Löschen aller deaktivierten Abonnements

1. Navigieren Sie im Admin Center zur Seite **Abrechnung** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Ihre Produkte</a>.
2. Wählen Sie auf der Registerkarte **Produkte** ein deaktiviertes Abonnement aus.
3. Wählen Sie auf der Seite Abonnementdetails im Abschnitt **Abonnement-und Zahlungseinstellungen** die Option **Abonnement löschen** aus.
4. Wählen Sie im Bereich **Abonnement löschen** die Option **Abonnement löschen** aus.
5. Wählen Sie im Dialogfeld **Abonnement löschen** die Option **Ja** aus.
6. Wiederholen Sie für jedes deaktivierte Abonnement die Schritte 3 bis 5, bis alle Abonnements gelöscht wurden.

> [!NOTE]
> Wenn ein deaktiviertes Abonnement nicht sofort gelöscht werden kann, <a href="https://go.microsoft.com/fwlink/p/?linkid=518322" target="_blank">wenden Sie sich an den Support</a> .

## <a name="step-4-disable-multi-factor-authentication"></a>Schritt 4: Deaktivieren der mehrstufigen Authentifizierung

1. Melden Sie sich mit einem globalen Administratorkonto beim Admin Center an. Informationen zum Überprüfen der Rollen, die Sie besitzen, finden Sie unter [Überprüfen der Administratorrollen in Ihrer Organisation](../admin/add-users/assign-admin-roles.md#check-admin-roles-in-your-organization).
2. Wechseln Sie zur Seite **Benutzer**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">aktive Benutzer</a> .
3. Wählen Sie die mehrstufige **Authentifizierung** aus.
4. Deaktivieren Sie auf der Seite mehrstufige Authentifizierung alle Konten mit Ausnahme des globalen Administratorkontos, das Sie derzeit verwenden.

Sie können auch <a href="https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-userstates#change-state-using-powershell">PowerShell verwenden, um die mehrstufige Authentifizierung für mehrere Benutzer zu deaktivieren</a>.

## <a name="step-5-delete-the-directory-in-azure-active-directory"></a>Schritt 5: Löschen des Verzeichnisses in Azure Active Directory

1. Melden Sie sich beim <a href="https://aad.portal.azure.com/" target="_blank">Azure AD Admin Center</a> mit einem globalen Administratorkonto an.
2. Wählen Sie **Azure Active Directory** aus.
3. Wechseln Sie zu der Organisation, die Sie löschen möchten.
4. Wählen Sie **Mandant löschen** aus.
5. Wenn in Ihrer Organisation mindestens eine Prüfung fehlschlägt, wird ein Link zu weiteren Informationen zum übergeben der Prüfungen angezeigt. Nachdem Sie alle Prüfungen übergeben haben, wählen Sie **Delete** aus, um den Vorgang abzuschließen.

Nachdem Sie diesen letzten Schritt abgeschlossen haben, wird Ihr Konto bei Microsoft geschlossen und gelöscht.