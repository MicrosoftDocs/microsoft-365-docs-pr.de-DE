---
title: Verwalten von Self-Service-Anmeldeabonnements
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
ms.reviewer: jkinma, jmueller
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- commerce_subscriptions
search.appverid: MET150
description: Erfahren Sie, wie Sie kostenlose Self-Service-Anmeldeabonnements für Ihre Organisation verwalten.
ms.date: 03/17/2021
ms.openlocfilehash: b469515a649399c71ef64ba2567dfa376f21e9a7
ms.sourcegitcommit: 967f64dfa1a05f31179c8316b96bfb7758a5d990
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/12/2021
ms.locfileid: "52333218"
---
# <a name="manage-self-service-sign-up-subscriptions"></a>Verwalten von Self-Service-Anmeldeabonnements

## <a name="what-are-self-service-sign-up-subscriptions"></a>Was sind Self-Service-Anmeldeabonnements?

Es gibt eine begrenzte Anzahl kostenloser Self-Service-Anmeldeabonnements, für die sich Benutzer in Ihrer Organisation registrieren können. Ein Benutzer kann sich nur für sich selbst registrieren und ein Self-Service-Anmeldeabonnement verwenden. Sie verwalten Self-Service-Anmeldeabonnements, indem Sie Die Anmeldung von Benutzern blockieren und kostenlose Abonnements löschen, für die sich Benutzer angemeldet haben. Weitere Informationen zur Self-Service-Anmeldung und den verfügbaren Abonnements finden Sie unter [Using self-service sign up in your organization](../../admin/misc/self-service-sign-up.md).

## <a name="view-a-list-of-self-service-sign-up-subscriptions"></a>Anzeigen einer Liste der Self-Service-Anmeldeabonnements

1. Navigieren Sie im Admin Center zur Seite **Abrechnung** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Ihre Produkte</a>.
2. Wählen Sie **auf der** Registerkarte Produkte das Filtersymbol aus, und wählen Sie dann **Frei aus.** Eine Liste aller Self-Service-Anmeldeabonnements wird angezeigt.

## <a name="how-are-these-subscriptions-different-from-self-service-purchase-subscriptions"></a>Wie unterscheiden sich diese Abonnements von Self-Service-Kaufabonnements?

Self-Service-Anmeldeabonnements sind kostenlos und stehen für eine größere Liste von Produkten zur Verfügung als Self-Service-Kaufabonnements. Wenn sich ein Benutzer für ein Self-Service-Kaufabonnement einschreibt, ist er für die Zahlung verantwortlich. Self-Service-Kaufabonnements sind nur für Power Platform-Produkte (Power BI, Power Apps und Power Automate), Project und Visio verfügbar. Weitere Informationen finden Sie unter Häufig gestellte Fragen [zum Self-Service-Kauf.](self-service-purchase-faq.md)

## <a name="block-users-from-signing-up"></a>Blockieren der Anmeldung von Benutzern

Sie verwenden das [**Cmdlet Set-MsolCompanySettings**](/powershell/module/msonline/set-msolcompanysettings?preserve-view=true&view=azureadps-1.0) mit dem **Parameter AllowAdHocSubscriptions,** um zu steuern, ob Sich Benutzer für Self-Service-Anmeldeabonnements registrieren können. Weitere Informationen finden Sie unter [How do I control self-service settings?](/azure/active-directory/users-groups-roles/directory-self-service-signup#how-do-i-control-self-service-settings)

## <a name="delete-a-self-service-sign-up-subscription"></a>Löschen eines Self-Service-Anmeldeabonnements

> [!IMPORTANT]
> Wenn Sie ein Self-Service-Anmeldeabonnement löschen, blockieren Sie alle Benutzer am Zugriff auf ihre Daten und E-Mails und löschen alle Daten und E-Mails.

1. Navigieren Sie im Admin Center zur Seite **Abrechnung** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Ihre Produkte</a>.
2. Wählen Sie **auf der** Registerkarte Produkte das Filtersymbol aus, und wählen Sie dann **Frei aus.**
3. Wählen Sie das Self-Service-Anmeldeabonnement aus, das Sie löschen möchten. 
4. Wählen Sie auf der Seite Abonnementdetails im Abschnitt **Abonnements und** Zahlungseinstellungen Abonnement **löschen aus.**
5. Aktivieren Sie **im Bereich** Abonnement löschen das Kontrollkästchen und dann **Abonnement löschen.**

## <a name="i-have-a-self-service-sign-up-subscription-that-blocks-directory-deletion"></a>Ich habe ein Self-Service-Anmeldeabonnement, das die Verzeichnislöschung blockiert

Die Self-Service-Anmeldeprodukte, für die sich einzelne Benutzer registrieren können, erstellen auch einen Gastbenutzer für die Authentifizierung in Ihrem Azure AD-Verzeichnis. Um Datenverluste zu vermeiden, blockieren diese Self-Service-Produkte Verzeichnislöschungen, bis sie vollständig aus dem Verzeichnis gelöscht werden. Sie können nur vom Azure AD-Administrator gelöscht werden. Weitere Informationen finden Sie [unter Löschen eines Verzeichnisses in Azure Active Directory](/azure/active-directory/users-groups-roles/directory-delete-howto).
