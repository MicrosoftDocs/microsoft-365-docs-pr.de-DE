---
title: Verwalten von Self-Service-Anmelde Abonnements
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
- M365-subscription-management
- Adm_O365
- commerce
- Adm_NonTOC
search.appverid:
- MET150
description: Hier erfahren Sie, wie Sie ﻿kostenlose Self-Service-Anmelde Abonnements für Ihre Organisation verwalten.
ms.openlocfilehash: 056ae95f9f5067ea3fa86164b620c72c84e3aad4
ms.sourcegitcommit: e525bcf073a61e1350484719a0c3ceb6ff0d8db1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/06/2020
ms.locfileid: "43154132"
---
# <a name="manage-self-service-sign-up-subscriptions"></a>Verwalten von Self-Service-Anmelde Abonnements

## <a name="what-are-self-service-sign-up-subscriptions"></a>Was sind Self-Service-Anmelde Abonnements?

Es gibt eine beschränkte Anzahl von kostenlosen Self-Service-Anmelde Abonnements, für die sich Benutzer in Ihrer Organisation anmelden können. Ein Benutzer kann sich nur für sich selbst registrieren und ein Self-Service-Anmelde Abonnement verwenden. Diese Abonnements werden auf der Seite **Produkte & Dienste** angezeigt, sind als **kostenlos**gekennzeichnet und weisen einen Hinweis darauf auf, dass "dies ein kostenloses Abonnement ist, das von Benutzern in Ihrem Unternehmen aktiviert wird." Sie können Self-Service-Anmelde Abonnements verwalten, indem Sie Benutzer daran hindern, sich anzumelden, und indem Sie ﻿Kostenlose Abonnements löschen, für die Benutzer sich angemeldet haben. Weitere Informationen zur Self-Service-Registrierung und den verfügbaren Abonnements finden Sie unter [Verwenden der Self-Service-Registrierung in Ihrer Organisation](../../admin/misc/self-service-sign-up.md).

## <a name="how-are-these-subscriptions-different-from-self-service-purchase-subscriptions"></a>Inwiefern unterscheiden sich diese Abonnements von Self-Service-Abonnements für den Kauf?

Self-Service-Anmelde Abonnements sind kostenlos und stehen für eine größere Produktliste als Self-Service-Abonnements zur Verfügung. Wenn sich ein Benutzer für ein Self-Service-Abonnement anmeldet, ist er für die Zahlung verantwortlich. Außerdem stehen Self-Service Subscription-Abonnements nur für Power Platform-Produkte (Power BI, Power apps und Power Automation) zur Verfügung. Weitere Informationen finden Sie unter [Self-Service purchase FAQ](self-service-purchase-faq.md).

## <a name="block-users-from-signing-up"></a>Blockieren der Anmeldung von Benutzern

Verwenden Sie das Cmdlet " [**MsolCompanySettings**](https://docs.microsoft.com/powershell/module/msonline/set-msolcompanysettings?view=azureadps-1.0) " mit dem Parameter " **AllowAdHocSubscriptions** ", um zu steuern, ob sich Benutzer für Self-Service-Anmelde Abonnements anmelden können. Weitere Informationen finden Sie unter [wie kann ich Self-Service-Einstellungen steuern?](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-self-service-signup#how-do-i-control-self-service-settings)

## <a name="delete-a-self-service-sign-up-subscription"></a>Löschen eines Self-Service-Anmelde Abonnements

> [!IMPORTANT]
> Wenn Sie ein Self-Service-Anmelde Abonnement löschen, werden alle Benutzer daran gehindert, auf Ihre Daten zuzugreifen und alle Daten und e-Mails zu löschen.

1. Wechseln Sie im Admin Center zur Seite **Abrechnungs** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Produkte & Dienste</a> .
2. Suchen Sie nach dem Self-Service-Anmelde Abonnement, das Sie löschen möchten. Wählen Sie im Abschnitt **Einstellungen & Aktionen** die Option **Abonnement löschen**aus.
3. Aktivieren Sie im Bereich **Abonnement löschen** das Kontrollkästchen, und wählen Sie dann **Abonnement löschen**aus.

## <a name="i-have-a-self-service-sign-up-subscription-that-blocks-directory-deletion"></a>Ich habe ein Self-Service-Anmelde Abonnement, das das Löschen von Verzeichnissen blockiert.

Die Self-Service-Anmelde Produkte, mit denen sich einzelne Benutzer anmelden können, erstellen auch einen Gastbenutzer für die Authentifizierung in Ihrem Azure AD-Verzeichnis. Um Datenverlust zu vermeiden, blockieren diese Self-Service-Produkte Verzeichnis Löschungen, bis Sie vollständig aus dem Verzeichnis gelöscht werden. Sie können nur vom Azure AD Administrator gelöscht werden. Weitere Informationen finden Sie unter [Löschen eines Verzeichnisses in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-delete-howto).