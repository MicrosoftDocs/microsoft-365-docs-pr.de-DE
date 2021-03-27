---
title: Aktivieren von Sicherheitseinstellungen
f1.keywords:
- NOCSH
ms.author: sharik
author: SKjerland
manager: scotv
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
- M365-identity-device-management
- M365-Campaigns
- m365solution-smb
ms.custom:
- Adm_O365
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
- MOE150
description: Erfahren Sie, wie Sicherheitseinstellungen Ihre Organisation vor identitätsbezogenen Angriffen schützen können, indem sie vorkonfigurierte Sicherheitseinstellungen bereitstellen.
ms.openlocfilehash: ea36ba45af26a767b08ee1e75931dca54dacea64
ms.sourcegitcommit: c5d1528559953c6db7dca1d5cb453e0aa3215f02
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/27/2021
ms.locfileid: "51398291"
---
# <a name="turn-on-security-defaults"></a>Aktivieren von Sicherheitseinstellungen

Sicherheitseinstellungen schützen Ihre Organisation vor identitätsbezogenen Angriffen, indem sie vorkonfigurierte Sicherheitseinstellungen bereitstellen, die Microsoft im Auftrag Ihrer Organisation verwaltet. Zu diesen Einstellungen gehört das Aktivieren der mehrstufigen Authentifizierung (MFA) für alle Administratoren und Benutzerkonten. Für die meisten Organisationen bieten Sicherheitseinstellungen ein hohes Maß an zusätzlicher Anmeldesicherheit.

Weitere Informationen zu Sicherheitseinstellungen und den von ihnen erzwungenen Richtlinien finden Sie unter [Was sind Sicherheitseinstellungen?](/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)

Wenn Ihr Abonnement am oder nach dem 22. Oktober 2019 erstellt wurde, wurden Sicherheitseinstellungen möglicherweise automatisch aktiviert, damit Sie Ihre Einstellungen überprüfen können, um dies &mdash; zu bestätigen.

So aktivieren Sie Sicherheitseinstellungen in Ihrem Azure Active Directory (Azure AD) oder überprüfen Sie, ob sie bereits aktiviert sind:

1. Melden Sie sich beim <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 Admin Center</a> mit globalen Administratoranmeldeinformationen an.

2. Wählen Sie im linken Bereich Alle anzeigen **aus,** und wählen Sie dann unter **Admin Center** **Azure Active Directory aus.**

3. Wählen Sie im linken Bereich des **Azure Active Directory Admin Center** Azure Active Directory **aus.**

4. Wählen Sie im linken Menü des Dashboards im Abschnitt **Verwalten** die Option **Eigenschaften aus.**

    :::image type="content" source="../media/m365-campaigns-conditional-access/azure-ad-properties.png" alt-text="Screenshot des Azure Active Directory Admin Center mit dem Speicherort des Menüelements Eigenschaften.":::

5. Wählen Sie unten auf der **Seite Eigenschaften** die Option **Sicherheitseinstellungen verwalten aus.**

6. Im rechten Bereich wird die Einstellung **Sicherheitseinstellungen aktivieren** angezeigt. Wenn **Ja** ausgewählt ist, sind die Sicherheitseinstellungen bereits aktiviert, und es sind keine weiteren Aktionen erforderlich. Wenn Sicherheitseinstellungen derzeit nicht aktiviert sind, wählen Sie Ja aus, um sie zu aktivieren, und wählen Sie dann **Speichern aus.** 

> [!NOTE]
> Wenn Sie Richtlinien für bedingten Zugriff verwendet haben, müssen Sie sie deaktivieren, bevor Sie Sicherheitseinstellungen verwenden.
>
> Sie können entweder Sicherheitseinstellungen oder Richtlinien für bedingten Zugriff verwenden, aber Sie können beide nicht gleichzeitig verwenden.

## <a name="consider-using-conditional-access"></a>Erwägen sie die Verwendung von bedingten Zugriff

Wenn Ihre Organisation komplexe Sicherheitsanforderungen hat oder Sie eine genauere Kontrolle über Ihre Sicherheitsrichtlinien benötigen, sollten Sie die Verwendung von bedingtem Zugriff anstelle von Sicherheitseinstellungen in Betracht ziehen, um eine ähnliche oder höhere Sicherheitslage zu erreichen. 

Mit bedingten Zugriff können Sie Richtlinien erstellen und definieren, die auf Anmeldeereignisse reagieren und zusätzliche Aktionen anfordern, bevor einem Benutzer Zugriff auf eine Anwendung oder einen Dienst gewährt wird. Richtlinien für bedingten Zugriff können präzise und spezifisch sein und es Benutzern ermöglichen, jederzeit produktiv zu sein, aber auch Ihre Organisation zu schützen.

Sicherheitseinstellungen sind für alle Kunden verfügbar, während für bedingten Zugriff eine Lizenz für einen der folgenden Pläne erforderlich ist:

- Azure Active Directory Premium P1 oder P2
- Microsoft 365 Business Premium
- Microsoft 365 E3 oder E5
- Enterprise Mobility & Security E3 oder E5

Wenn Sie bedingten Zugriff verwenden möchten, um Richtlinien zu konfigurieren, die den durch Sicherheitseinstellungen aktivierten Richtlinien entsprechen, lesen Sie die folgenden schrittweisen Anleitungen:

- [MFA für Administratoren erforderlich](/azure/active-directory/conditional-access/howto-conditional-access-policy-admin-mfa)
- [MFA für die Azure-Verwaltung erforderlich](/azure/active-directory/conditional-access/howto-conditional-access-policy-azure-management)
- [Blockieren von Legacy-Authentifizierung](/azure/active-directory/conditional-access/howto-conditional-access-policy-block-legacy)
- [MFA für alle Nutzer erforderlich](/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa)
- [Azure AD MFA-Registrierung erforderlich](/azure/active-directory/identity-protection/howto-identity-protection-configure-mfa-policy) – Erfordert Azure AD Identity Protection, das Teil von Azure Active Directory Premium P2 ist

Weitere Informationen zum bedingten Zugriff finden Sie unter [Was ist bedingter Zugriff?](/azure/active-directory/conditional-access/overview) Weitere Informationen zum Erstellen von Richtlinien für bedingten Zugriff finden Sie unter [Create a Conditional Access policy](/azure/active-directory/authentication/tutorial-enable-azure-mfa#create-a-conditional-access-policy).

> [!NOTE]
> Wenn Sie über einen Plan oder eine Lizenz verfügen, die bedingten Zugriff bietet, aber noch keine Richtlinien für bedingten Zugriff erstellt haben, können Sie Sicherheitseinstellungen verwenden. Sie müssen jedoch Sicherheitseinstellungen deaktivieren, bevor Sie Richtlinien für bedingten Zugriff verwenden können.
