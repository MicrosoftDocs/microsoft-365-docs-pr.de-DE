---
title: Verwalten der Benutzerzustimmung für Apps in Microsoft 365
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
ms.custom:
- AdminSurgePortfolio
- AdminTemplateSet
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 7e453a40-66df-44ab-92a1-96786cb7fb34
description: Erfahren Sie mehr über die Zustimmung der Benutzer zu Apps und wie Sie sie aktivieren können, um Drittanbieter-Apps den Zugriff auf Microsoft 365 Informationen von Benutzern zu ermöglichen.
ms.openlocfilehash: 629e64494c6d72a13c3b155370a8f47505e9fa20
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/12/2021
ms.locfileid: "53391231"
---
# <a name="managing-user-consent-to-apps-in-microsoft-365"></a>Verwalten der Benutzerzustimmung für Apps in Microsoft 365

Mit dieser Einstellung wird gesteuert, ob Benutzer apps zustimmen können, die OpenID Verbinden und OAuth 2.0 für die Anmeldung und Anforderungen für den Zugriff auf Daten verwenden. Eine App kann innerhalb Ihrer eigenen Organisation erstellt werden, oder sie kann von einer anderen Office 365 Organisation oder einem Drittanbieter stammen.

Wenn Sie diese Einstellung aktivieren, werden die Benutzer von diesen Apps um die Berechtigung für den Zugriff auf die Daten Ihrer Organisation gebeten, und Benutzer können auswählen, ob sie dies zulassen möchten. Wenn Sie diese Einstellung deaktivieren, müssen Administratoren diesen Apps zustimmen, bevor Benutzer sie verwenden können. In diesem Fall sollten Sie einen Administratorzustimmungsworkflow im Azure-Portal einrichten, damit Benutzer eine Anforderung zur Administratorgenehmigung senden können, um blockierte Apps zu verwenden.

Ein Benutzer kann nur Apps, deren Besitzer er ist, Zugriff auf seine Office 365-Informationen gewähren. Sie können einer App keinen Zugriff auf die Informationen anderer Benutzer gewähren.

## <a name="turning-user-consent-on-or-off"></a>Aktivieren oder Deaktivieren der Zustimmung des Benutzers

Hier erfahren Sie, wie Sie die Benutzerzustimmung für Apps aktivieren oder deaktivieren.

1. Wechseln Sie im Admin Center zur Seite **Einstellungen** Dienste für \> **Organisationseinstellungen,**  >  [](https://go.microsoft.com/fwlink/p/?linkid=2053743) und wählen Sie dann die Zustimmung des Benutzers **zu Apps** aus.

2. Wählen Sie auf der Seite **"Benutzerzustimmung für Apps"** die Option zum Aktivieren oder Deaktivieren der Benutzerzustimmung aus.

## <a name="related-content"></a>Verwandte Inhalte 

[Konfigurieren des Workflows für die Administratorzustimmung](/azure/active-directory/manage-apps/configure-admin-consent-workflow) (Artikel)\
[Verwalten der Zustimmung zu Anwendungen und Auswerten von Zustimmungsanforderungen](/azure/active-directory/manage-apps/manage-consent-requests) (Artikel)