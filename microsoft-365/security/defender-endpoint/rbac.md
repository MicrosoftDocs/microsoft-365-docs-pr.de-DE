---
title: Verwenden der rollenbasierten Zugriffssteuerung zum Gewähren eines feinkörnigen Zugriffs auf das Microsoft Defender Security Center
description: Erstellen Sie Rollen und Gruppen innerhalb Ihrer Sicherheitsvorgänge, um Zugriff auf das Portal zu gewähren.
keywords: rbac, role, based, access, control, groups, control, tier, aad
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: d95163bd7caf6e05295fc35b3f9c2bf95230dc83
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51063840"
---
# <a name="manage-portal-access-using-role-based-access-control"></a>Verwalten des Portalzugriffs mithilfe der rollenbasierten Zugriffssteuerung

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:**
- Azure Active Directory
- Office 365

> Möchten Sie Defender for Endpoint erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-rbac-abovefoldlink)

Mithilfe der rollenbasierten Zugriffssteuerung (Role-Based Access Control, RBAC) können Sie Rollen und Gruppen innerhalb Ihres Sicherheitsbetriebsteams erstellen, um den entsprechenden Zugriff auf das Portal zu gewähren. Basierend auf den von Ihnen erstellten Rollen und Gruppen haben Sie eine feinkörnige Kontrolle darüber, was Benutzer mit Zugriff auf das Portal sehen und tun können. 

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4bJ2a]

Große geo verteilte Sicherheitsteams übernehmen in der Regel ein ebenenbasiertes Modell zum Zuweisen und Autorisieren des Zugriffs auf Sicherheitsportale. Typische Ebenen umfassen die folgenden drei Ebenen:

Ebene | Beschreibung
:---|:---
Ebene 1 | **Lokales Sicherheitsteam/IT-Team** <br> Dieses Team untersucht in der Regel Warnungen, die in ihrer Geolocation enthalten sind, und eskaliert in Fällen, in denen eine aktive Korrektur erforderlich ist, auf Ebene 2.
Ebene 2 | **Team für regionale Sicherheitsvorgänge** <br> Dieses Team kann alle Geräte für seine Region sehen und Korrekturaktionen ausführen.
Ebene 3 | **Team für globale Sicherheitsvorgänge** <br> Dieses Team besteht aus Sicherheitsexperten und ist autorisiert, alle Aktionen aus dem Portal zu sehen und durchzuführen.

Defender for Endpoint RBAC wurde entwickelt, um Ihr ebenen- oder rollenbasiertes Auswahlmodell zu unterstützen und ihnen eine präzise Kontrolle darüber zu geben, welche Rollen angezeigt werden können, auf welche Geräte sie zugreifen können und welche Aktionen sie ausführen können. Das RBAC-Framework ist um die folgenden Steuerelemente zentriert:

- **Steuern, wer bestimmte Aktionen ergreifen kann**
  - Erstellen Sie benutzerdefinierte Rollen, und steuern Sie, auf welche Defender for Endpoint-Funktionen sie präzise zugreifen können.
 
- **Steuern, wer Informationen zu bestimmten Gerätegruppen oder -gruppen sehen kann**
  - [Erstellen Sie Gerätegruppen](machine-groups.md) nach bestimmten Kriterien wie Namen, Tags, Domänen und anderen, und gewähren Sie ihnen dann mithilfe einer bestimmten Azure Active Directory (Azure AD)-Benutzergruppe Rollenzugriff.

Zum Implementieren des rollenbasierten Zugriffs müssen Sie Administratorrollen definieren, entsprechende Berechtigungen zuweisen und den Rollen zugewiesene Azure AD-Benutzergruppen zuweisen.


### <a name="before-you-begin"></a>Vorbereitung
Vor der Verwendung von RBAC ist es wichtig, dass Sie die Rollen verstehen, die Berechtigungen erteilen können, und die Folgen des Aktivierens von RBAC.


> [!WARNING]
> Bevor Sie das Feature aktivieren, ist es wichtig, dass Sie über eine Rolle des globalen Administrators oder Sicherheitsadministrators in Azure AD verfügen und dass Ihre Azure AD-Gruppen bereit sind, das Risiko zu verringern, dass das Portal gesperrt wird. 

Wenn Sie sich zum ersten Mal beim Microsoft Defender Security Center anmelden, erhalten Sie entweder Vollzugriff oder schreibgeschützten Zugriff. Vollzugriffsrechte werden Benutzern mit Sicherheitsadministrator- oder globalen Administratorrollen in Azure AD gewährt. Benutzer mit einer Rolle "Security Reader" in Azure AD erhalten schreibgeschützten Zugriff. 

Eine Person mit einer Administratorrolle "Defender for Endpoint Global" hat uneingeschränkten Zugriff auf alle Geräte, unabhängig von ihrer Gerätegruppenzuordnung und den Azure AD-Benutzergruppenzuweisungen.

> [!WARNING]
> Anfangs können nur Personen mit den Rechten des globalen Azure AD-Administrators oder des Sicherheitsadministrators Rollen im Microsoft Defender Security Center erstellen und zuweisen. Daher ist es wichtig, dass die richtigen Gruppen in Azure AD bereit sind.
>
> **Wenn Sie die rollenbasierte Zugriffssteuerung aktivieren, verlieren Benutzer mit schreibgeschützten Berechtigungen (z. B. Benutzer, die der Azure AD Security-Leserrolle zugewiesen sind) den Zugriff, bis sie einer Rolle zugewiesen sind.** 
>
>Benutzern mit Administratorberechtigungen wird automatisch die standardmäßig integrierte globale Administratorrolle Defender for Endpoint mit vollständigen Berechtigungen zugewiesen. Nachdem Sie sich für die Verwendung von RBAC angemeldet haben, können Sie der globalen Administratorrolle Defender for Endpoint weitere Benutzer zuweisen, die keine Azure AD Global- oder Sicherheitsadministratoren sind. 
>
> Nachdem Sie sich für die Verwendung von RBAC angemeldet haben, können Sie nicht wie bei der ersten Anmeldung am Portal zu den ursprünglichen Rollen zurückkehren. 



## <a name="related-topic"></a>Verwandtes Thema
- [Erstellen und Verwalten von Gerätegruppen in Microsoft Defender for Endpoint](machine-groups.md)
