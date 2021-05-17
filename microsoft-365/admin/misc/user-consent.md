---
title: Verwalten der Zustimmung des Benutzers zu Apps in Microsoft 365
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
description: Erfahren Sie mehr über die Zustimmung des Benutzers zu Apps und darüber, wie Sie sie aktivieren, damit Apps von Drittanbietern auf die Benutzerinformationen Microsoft 365 können.
ms.openlocfilehash: 1f6f08161d6dd85964f07ec4d48f9f2cc23a1ead
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50914558"
---
# <a name="managing-user-consent-to-apps-in-microsoft-365"></a>Verwalten der Zustimmung des Benutzers zu Apps in Microsoft 365

Diese Einstellung steuert, ob Benutzer apps, die OpenID Verbinden und OAuth 2.0 für die Anmeldung und Anforderungen für den Zugriff auf Daten verwenden, diese Zustimmung erteilen können. Eine App kann in Ihrer eigenen Organisation erstellt werden, oder sie kann von einer anderen organisation Office 365 oder von einem Drittanbieter stammen.

Wenn Sie diese Einstellung aktivieren, bitten diese Apps Benutzer um Die Berechtigung für den Zugriff auf die Daten Ihrer Organisation, und Benutzer können auswählen, ob sie zulässig sind. Wenn Sie diese Einstellung deaktivieren, müssen Administratoren diesen Apps zustimmen, bevor Benutzer sie verwenden können. In diesem Fall sollten Sie einen Administrator-Zustimmungsworkflow im Azure-Portal einrichten, damit Benutzer eine Administratorgenehmigungsanforderung senden können, um blockierte Apps zu verwenden.

Ein Benutzer kann nur Apps, deren Besitzer er ist, Zugriff auf seine Office 365-Informationen gewähren. Sie können einer App keinen Zugriff auf die Informationen anderer Benutzer gewähren.

## <a name="turning-user-consent-on-or-off"></a>Aktivieren oder Deaktivieren der Zustimmung des Benutzers
<a name="__toc379982114"> </a>

Hier erfahren Sie, wie Sie die Zustimmung des Benutzers zu Apps aktivieren oder deaktivieren.

1. Wechseln Sie im Admin Center zur Seite **Einstellungen** Organisationseinstellungen Dienste, und wählen Sie dann \>   >  [](https://go.microsoft.com/fwlink/p/?linkid=2053743) **Benutzer-Zustimmung zu Apps aus.**

2. Wählen Sie **auf der** Seite Benutzer-Zustimmung zu Apps die Option aus, um die Zustimmung des Benutzers ein- oder auszuschalten.

## <a name="more-info"></a>Weitere Informationen
<a name="__toc379982114"> </a>

Informationen zum Konfigurieren Ihrer Zustimmungseinstellungen in Azure Active Directory finden Sie unter [Configure the admin consent workflow](/azure/active-directory/manage-apps/configure-admin-consent-workflow).

Weitere Informationen zum Verwalten der Zustimmung des Benutzers zu Apps finden Sie unter [Managing consent to applications und evaluating consent requests](/azure/active-directory/manage-apps/manage-consent-requests).