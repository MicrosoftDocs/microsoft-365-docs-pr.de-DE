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
ms.openlocfilehash: 0ee0a649a9adb93ecdbb1cd9dbedbc04dfb46ba0
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/02/2021
ms.locfileid: "51579746"
---
# <a name="close-your-account"></a>Schließen Ihres Kontos

Wenn Sie Ihr Microsoft-Konto schließen, werden alle Informationen zu Ihrem Konto gelöscht. Diese Informationen umfassen Abonnements, Lizenzen, Zahlungsmethoden, Benutzer und Benutzerdaten.

## <a name="before-you-begin"></a>Bevor Sie beginnen:

Bevor Sie diesen Vorgang starten, stellen Sie sicher, dass Sie alle Daten gesichert haben, die Sie beibehalten möchten.

Sie müssen ein globaler oder ein Rechnungsadministrator sein, um die in diesem Artikel beschriebenen Schritte durchführen zu können. Weitere Informationen finden Sie unter [Informationen zu Administratorrollen](../admin/add-users/about-admin-roles.md).

## <a name="step-1-delete-users"></a>Schritt 1: Löschen von Benutzern

Löschen Sie alle Benutzer mit Ausnahme eines globalen Administrators. Der globale Administrator schließt die Schritte zum Schließen des Kontos. Bevor Sie das Verzeichnis am Ende dieses Vorgangs löschen können, müssen Sie alle anderen Benutzer löschen.

Wenn Benutzer lokal synchronisiert werden, deaktivieren Sie zuerst die Synchronisierung, und löschen Sie dann die Benutzer im Cloudverzeichnis mithilfe des Azure-Portals oder der Azure PowerShell-Cmdlets.

Informationen zum Löschen von Benutzern finden Sie unter <a href="/office365/admin/add-users/delete-a-user?view=o365-worldwide#user-management-admin-delete-one-or-more-users-from-office-365">Benutzerverwaltungsadministrator: Löschen eines oder mehrere Benutzer</a>.

Sie können auch das <a href="https://go.microsoft.com/fwlink/?linkid=842230">Remove-MsolUser</a> PowerShell-Cmdlet verwenden, um Benutzer massenlos zu löschen.

Wenn Ihre Organisation Active Directory verwendet, das mit Microsoft Azure Active Directory (Azure AD) synchronisiert wird, löschen Sie stattdessen das Benutzerkonto aus Active Directory. Anweisungen finden Sie unter <a href="/azure/active-directory/users-groups-roles/users-bulk-delete">Massenlöschen von Benutzern in Azure Active Directory</a>.

## <a name="step-2-cancel-all-active-subscriptions"></a>Schritt 2: Kündigen aller aktiven Abonnements

1. Navigieren Sie im Admin Center zur Seite **Abrechnung** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Ihre Produkte</a>.
2. Suchen Sie **auf** der Registerkarte Produkte nach einem aktiven Abonnement. Wählen Sie **Weitere Aktionen** (drei Punkte) und dann **Abonnement kündigen** aus.
3. Wählen Sie im Bereich **Abonnement kündigen** einen Grund aus, warum Sie kündigen. Geben Sie optional Feedback.
4. Wählen Sie **Speichern** aus.
5. Wiederholen Sie die Schritte 1 bis 4, um alle aktiven Abonnements zu kündigen.

## <a name="step-3-delete-all-disabled-subscriptions"></a>Schritt 3: Löschen aller deaktivierten Abonnements

1. Navigieren Sie im Admin Center zur Seite **Abrechnung** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Ihre Produkte</a>.
2. Wählen Sie **auf der** Registerkarte Produkte ein deaktiviertes Abonnement aus.
3. Wählen Sie auf der Seite Abonnementdetails im Abschnitt **Abonnement- und** Zahlungseinstellungen Abonnement **löschen aus.**
4. Wählen Sie **im Bereich** Abonnement löschen die Option Abonnement **löschen aus.**
5. Wählen Sie **im Dialogfeld Abonnement** löschen die Option Ja **aus.**
6. Wiederholen Sie für jedes deaktivierte Abonnement die Schritte 3 bis 5, bis alle Abonnements gelöscht werden.

> [!NOTE]
> Wenn Sie ein deaktiviertes Abonnement nicht sofort löschen können, wenden <a href="/microsoft-365/Admin/contact-support-for-business-products" target="_blank">Sie sich an den Support.</a>

## <a name="step-4-disable-multi-factor-authentication"></a>Schritt 4: Deaktivieren der mehrstufigen Authentifizierung

1. Melden Sie sich mit einem globalen Administratorkonto beim Admin Center an. Informationen dazu, welche Rollen Sie haben, finden Sie unter [Überprüfen von Administratorrollen in Ihrer Organisation](../admin/add-users/assign-admin-roles.md#check-admin-roles-in-your-organization).
2. Wechseln Sie zur **Seite**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Benutzer Aktive</a> Benutzer.
3. Wählen **Sie Mehrstufige Authentifizierung aus.**
4. Deaktivieren Sie auf der Seite mehrstufige Authentifizierung alle Konten mit Ausnahme des globalen Administratorkontos, das Sie derzeit verwenden.

Sie können <a href="/azure/active-directory/authentication/howto-mfa-userstates#change-state-using-powershell">PowerShell auch verwenden, um die mehrstufige</a>Authentifizierung für mehrere Benutzer zu deaktivieren.

## <a name="step-5-delete-the-directory-in-azure-active-directory"></a>Schritt 5: Löschen des Verzeichnisses in Azure Active Directory

1. Melden Sie sich mit einem globalen <a href="https://aad.portal.azure.com/" target="_blank">Administratorkonto</a> beim Azure AD Admin Center an.
2. Wählen Sie **Azure Active Directory** aus.
3. Wechseln Sie zu der Organisation, die Sie löschen möchten.
4. Wählen **Sie Mandanten löschen** aus.
5. Wenn in Ihrer Organisation eine oder mehrere Prüfungen nicht erfolgreich sind, wird ein Link zu weiteren Informationen zum Bestehen der Prüfungen sehen. Nachdem Sie alle Prüfungen bestanden haben, wählen Sie **Löschen aus,** um den Vorgang zu abschließen.

Nachdem Sie diesen letzten Schritt abgeschlossen haben, wird Ihr Konto bei Microsoft geschlossen und gelöscht.