---
title: Verwalten von Self-Service-Anmelde Abonnements
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
- M365-subscription-management
- Adm_O365
- commerce
- Adm_NonTOC
ms.custom: AdminSurgePortfolio
search.appverid:
- MET150
description: Hier erfahren Sie, wie Sie ﻿kostenlose Self-Service-Anmelde Abonnements für Ihre Organisation verwalten.
ms.openlocfilehash: 589466908dcda1461011f046b99be21788c1a018
ms.sourcegitcommit: 20d1158c54a5058093eb8aac23d7e4dc68054688
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2020
ms.locfileid: "49376305"
---
# <a name="manage-self-service-sign-up-subscriptions"></a>Verwalten von Self-Service-Anmelde Abonnements

## <a name="what-are-self-service-sign-up-subscriptions"></a>Was sind Self-Service-Anmelde Abonnements?

Es gibt eine beschränkte Anzahl von kostenlosen Self-Service-Anmelde Abonnements, die Benutzern in Ihrer Organisation zur Anmeldung zur Verfügung stehen. Ein Benutzer kann sich nur für sich selbst registrieren und ein Self-Service-Anmelde Abonnement verwenden. Sie können Self-Service-Anmelde Abonnements verwalten, indem Sie Benutzer daran hindern, sich anzumelden, und indem Sie ﻿Kostenlose Abonnements löschen, für die Benutzer sich angemeldet haben. Weitere Informationen zur Self-Service-Registrierung und den verfügbaren Abonnements finden Sie unter [Verwenden der Self-Service-Registrierung in Ihrer Organisation](../../admin/misc/self-service-sign-up.md).

## <a name="view-a-list-of-self-service-sign-up-subscriptions"></a>Anzeigen einer Liste von Self-Service-Anmelde Abonnements

1. Navigieren Sie im Admin Center zur Seite **Abrechnung** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Ihre Produkte</a>.
2. Klicken Sie auf der Registerkarte **Produkte** auf das Filtersymbol, und wählen Sie dann **kostenlos** aus. Eine Liste aller Self-Service-Anmelde Abonnements wird angezeigt.

## <a name="how-are-these-subscriptions-different-from-self-service-purchase-subscriptions"></a>Inwiefern unterscheiden sich diese Abonnements von Self-Service-Abonnements für den Kauf?

Self-Service-Anmelde Abonnements sind kostenlos und stehen für eine größere Produktliste als Self-Service-Abonnements zur Verfügung. Wenn sich ein Benutzer für ein Self-Service-Abonnement registriert, sind Sie dafür verantwortlich. Self-Service-Abonnements sind nur für Power Platform-Produkte (Power BI, Power apps und Power Automation), Project und Visio verfügbar. Weitere Informationen finden Sie unter [Self-Service purchase FAQ](self-service-purchase-faq.md).

## <a name="block-users-from-signing-up"></a>Blockieren der Anmeldung von Benutzern

Verwenden Sie das Cmdlet " [**MsolCompanySettings**](https://docs.microsoft.com/powershell/module/msonline/set-msolcompanysettings?view=azureadps-1.0&preserve-view=true) " mit dem Parameter " **AllowAdHocSubscriptions** ", um zu steuern, ob sich Benutzer für Self-Service-Anmelde Abonnements anmelden können. Weitere Informationen finden Sie unter [wie kann ich Self-Service-Einstellungen steuern?](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-self-service-signup#how-do-i-control-self-service-settings)

## <a name="delete-a-self-service-sign-up-subscription"></a>Löschen eines Self-Service-Anmelde Abonnements

> [!IMPORTANT]
> Wenn Sie ein Self-Service-Anmelde Abonnement löschen, werden alle Benutzer daran gehindert, auf Ihre Daten zuzugreifen und alle Daten und e-Mails zu löschen.

1. Navigieren Sie im Admin Center zur Seite **Abrechnung** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Ihre Produkte</a>.
2. Klicken Sie auf der Registerkarte **Produkte** auf das Filtersymbol, und wählen Sie dann **kostenlos** aus.
3. Wählen Sie das Self-Service-Anmelde Abonnement aus, das Sie löschen möchten. 
4. Wählen Sie auf der Seite Abonnementdetails im Abschnitt **Abonnements und Zahlungseinstellungen** die Option **Abonnement löschen** aus.
5. Aktivieren Sie im Bereich **Abonnement löschen** das Kontrollkästchen, und wählen Sie dann **Abonnement löschen** aus.

## <a name="i-have-a-self-service-sign-up-subscription-that-blocks-directory-deletion"></a>Ich habe ein Self-Service-Anmelde Abonnement, das das Löschen von Verzeichnissen blockiert.

Die Self-Service-Anmelde Produkte, mit denen sich einzelne Benutzer anmelden können, erstellen auch einen Gastbenutzer für die Authentifizierung in Ihrem Azure AD-Verzeichnis. Um Datenverlust zu vermeiden, blockieren diese Self-Service-Produkte Verzeichnis Löschungen, bis Sie vollständig aus dem Verzeichnis gelöscht werden. Sie können nur vom Azure AD Administrator gelöscht werden. Weitere Informationen finden Sie unter [Löschen eines Verzeichnisses in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-delete-howto).