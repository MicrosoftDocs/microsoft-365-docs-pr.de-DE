---
title: 'Info zu Intune-Administratorrollen im Microsoft 365 Admin Center '
f1.keywords:
- CSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
description: Administratorrollen sind Geschäftsfunktionen zugeordnet. Über sie werden Berechtigungen für bestimmte Aufgaben im Admin Center erteilt. Der Dienstadministrator öffnet beispielsweise Supporttickets bei Microsoft.
ms.openlocfilehash: 60a1f21e65df007e78077d8c3bb22161313c1073
ms.sourcegitcommit: 223a36a86753fe9cebee96f05ab4c9a144133677
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/14/2021
ms.locfileid: "51755726"
---
# <a name="intune-admin-roles-in-the-microsoft-365-admin-center"></a>Intune-Administratorrollen im Microsoft 365 Admin Center 

Ihr Microsoft 365- oder Office 365-Abonnement bietet eine Reihe von Administratorrollen, die Sie Benutzern in Ihrer Organisation mithilfe von Microsoft 365 Admin Center zuweisen können. Jede Administratorrolle ist häufig genutzten Geschäftsfunktionen zugeordnet. Über diese Rollen erhalten Personen in Ihrer Organisation die Berechtigung zum Ausführen bestimmter Aufgaben in den Admin Centern.

Im Microsoft 365 Admin Center können Sie Microsoft Intune-Rollen verwalten. Bei diesen Rollen handelt es sich jedoch um eine Teilmenge der Rollen, die im Intune Admin Center verfügbar sind. Sind Sie an detaillierten Rollenbeschreibungen für Microsoft Intune interessiert? Siehe [Rollenbasierte Zugriffssteuerung (RBAC) mit Microsoft Intune](/mem/intune/fundamentals/role-based-access-control).

Weitere Informationen zum Zuweisen von Rollen im Microsoft 365 Admin Center finden Sie unter [Zuweisen von Administratorrollen](assign-admin-roles.md).

Im Microsoft 365 Admin Center können Sie zu **Rollen** wechseln und dann eine beliebige Rolle auswählen, um den entsprechenden Detailbereich zu öffnen. Wählen Sie die Registerkarte **Berechtigungen** aus, um eine detaillierte Liste der Berechtigungen anzuzeigen, über die Administratoren mit dieser Rolle verfügen. Wählen Sie die Registerkarte **Zugewiesene** oder **Zugewiesene Administratoren** aus, um Benutzer zu Rollen hinzuzufügen.

## <a name="microsoft-intune-roles-available-in-the-microsoft-365-admin-center"></a>Im Microsoft 365 Admin Center verfügbare Microsoft Intune-Rollen

|Administratorrolle     |Wem sollte diese Rolle zugewiesen werden?  |
|---------|---------|
|Anwendungsmanager     |   Weisen Sie die Rolle des Anwendungsmanagers Benutzern zu, die den Anwendungs-Lebenszyklus für mobile Anwendungen verwalten, richtlinienverwaltete Anwendungen konfigurieren und Geräteinformationen und Konfigurationsprofile anzeigen.  |
|Helpdesk-Operator     |   Weisen Sie die Helpdesk-Operator-Rolle den Benutzern zu, die Benutzern und Geräten Anwendungen und Richtlinien zuweisen. |
|Intune-Rollenadministrator    |   Weisen Sie den Intune-Rollenadministrator Benutzern zu, die anderen Administratoren Intune-Berechtigungen zuweisen und benutzerdefinierte und eingebaute Intune-Rollen verwalten können.   |
|Richtlinien- und Profilmanager     |   Weisen Sie die Rolle des Richtlinien- und Profilmanagers den Benutzern zu, die Konformitätsrichtlinien, Konfigurationsprofile und Registrierung bei Apple verwalten.   |
|Operator für „Schreibgeschützt“     |   Weisen Sie Benutzern, die nur Benutzer, Geräte, Anmeldedetails und Konfigurationen anzeigen können, die Rolle des Operators für „Schreibgeschützt“ zu.   |
|Schuladministrator     |   Weisen Sie den Benutzern die Rolle des Schuladministrators zu, damit sie vollen Zugriff auf die Verwaltung von Windows 10 und iOS-Geräten, Anwendungen und Konfigurationen in Intune for Education haben.   |

## <a name="delegated-administration-for-microsoft-partners"></a>Delegierte Administration für Microsoft-Partner

Wenn Sie mit einem Microsoft-Partner arbeiten, können Sie den entsprechenden Personen Administratorrollen zuweisen. Diese können wiederum Benutzern in Ihrem (oder deren) Unternehmen Administratorrollen zuweisen. Dies kann beispielsweise sinnvoll sein, wenn diese Personen Ihre Online-Organisation für Sie einrichten und verwalten.
  
Ein Partner kann die folgenden Rollen zuweisen: 
  
- Vollständige Verwaltung mit Berechtigungen, die jenen eines globalen Administrators entsprechen, mit der Ausnahme, dass die mehrstufige Authentifizierung über das Partner Center verwaltet wird.

- Eingeschränkte Verwaltung mit Berechtigungen, die jenen eines Helpdesk-Administrators entsprechen.

Bevor der Partner diese Rollen Benutzern zuweisen kann, müssen Sie ihn als delegierten Administrator zu Ihrem Konto hinzufügen. Dieser Vorgang wird von einem autorisierten Partner initiiert. Der Partner fragt Sie in einer E-Mail-Nachricht, ob Sie ihm die Berechtigung erteilen möchten, als delegierter Administrator zu fungieren. Weitere Informationen hierzu finden Sie unter [Autorisieren oder Entfernen von Partnerbeziehungen](../misc/add-partner.md).
  
## <a name="related-articles"></a>Verwandte Artikel

[Informationen zu Microsoft 365-Administratorrollen](about-admin-roles.md)

[Zuweisen von Administratorrollen](assign-admin-roles.md)

[Teams-Aktivitätsberichte im Microsoft 365 Admin Center](../activity-reports/activity-reports.md)