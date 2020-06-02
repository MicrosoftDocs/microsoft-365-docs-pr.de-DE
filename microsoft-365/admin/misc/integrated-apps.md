---
title: Verwalten der Zustimmung von Benutzern zu apps in Microsoft 365
f1.keywords:
- CSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 7e453a40-66df-44ab-92a1-96786cb7fb34
description: Erfahren Sie mehr über die Benutzer Zustimmung zu apps und wie Sie Sie aktivieren, damit Drittanbieter-apps auf die Microsoft 365-Informationen von Benutzern zugreifen können.
ms.openlocfilehash: df81d2cf3e1d796e462d2b9240b8288273ed5372
ms.sourcegitcommit: ff1af42b036bfdf75729db8c78f10cf4642616ac
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/01/2020
ms.locfileid: "44477172"
---
# <a name="managing-user-consent-to-apps-in-microsoft-365"></a>Verwalten der Zustimmung von Benutzern zu apps in Microsoft 365

Mit dieser Einstellung wird gesteuert, ob Benutzer diese Zustimmung für apps erteilen können, die OpenID Connect und OAuth 2,0 für die Anmeldung und Anforderungen für den Zugriff auf Daten verwenden. Eine APP kann in ihrer eigenen Organisation erstellt werden oder aus einer anderen Office 365 Organisation oder einem Drittanbieter stammen.

Wenn Sie diese Einstellung aktivieren, werden die Benutzer von diesen apps aufgefordert, die Berechtigungen für den Zugriff auf die Daten Ihrer Organisation aufzurufen, und die Benutzer können entscheiden, ob Sie Sie zulassen möchten. Wenn Sie diese Einstellung deaktivieren, müssen Administratoren diesen apps zustimmen, bevor Sie von Benutzern verwendet werden können. In diesem Fall sollten Sie einen Administrator-Genehmigungsworkflow im Azure-Portal einrichten, damit Benutzer eine Anforderung zur Genehmigung des Administrators senden können, um eine blockierte APP zu verwenden.

Ein Benutzer kann nur Apps, deren Besitzer er ist, Zugriff auf seine Office 365-Informationen gewähren. Sie können einer App keinen Zugriff auf die Informationen anderer Benutzer gewähren.

## <a name="turning-user-consent-on-or-off"></a>Aktivieren oder Deaktivieren der Benutzer Zustimmung
<a name="__toc379982114"> </a>

Hier erfahren Sie, wie Sie die Zustimmung von Benutzern zu Apps aktivieren oder deaktivieren.

1. Wechseln Sie im Admin Center zur Seite **Einstellungen** für \> **Organisationseinstellungen**für  >  [Dienste](https://go.microsoft.com/fwlink/p/?linkid=2053743) , und wählen Sie dann **Benutzer Zustimmung für apps**aus.

2. Wählen Sie auf der Seite **Benutzer Zustimmung für apps** die Option aus, um integrierte apps ein-oder auszuschalten.

## <a name="more-info"></a>Weitere Informationen
<a name="__toc379982114"> </a>

Informationen zum Konfigurieren ihrer Zustimmungs Einstellungen in Azure Active Directory finden Sie unter [Konfigurieren des Administrator-Genehmigungsworkflows](https://docs.microsoft.com/azure/active-directory/manage-apps/configure-admin-consent-workflow).

Informationen zum Verwalten der Benutzer Zustimmung zu apps finden Sie unter [Verwalten der Zustimmung zu Anwendungen und bewerten von Zustimmungs Anforderungen](https://docs.microsoft.com/azure/active-directory/manage-apps/manage-consent-requests).