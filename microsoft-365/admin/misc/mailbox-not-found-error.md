---
title: Fehlermeldung "Postfach nicht gefunden" in Outlook im Web erhalten
f1.keywords:
- CSH
ms.author: pebaum
author: pebaum
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
ROBOTS: NOINDEX, NOFOLLOW
search.appverid:
- MET150
ms.assetid: 7e453a40-66df-44ab-92a1-96786cb7fb34
description: Der Fehler **Postfach konnte nicht gefunden werden** bedeutet, dass das Konto, das Sie für die Verbindung mit Outlook im Web verwendet haben, keine Exchange Online-Lizenz besitzt.
ms.openlocfilehash: cb82f917adca8f1fc183fd9516321a524c63eb69
ms.sourcegitcommit: 17f0aada83627d9defa0acf4db03a2d58e46842f
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/24/2021
ms.locfileid: "52635786"
---
# <a name="getting-a-mailbox-not-found-error-in-outlook-on-the-web"></a>Fehlermeldung "Postfach nicht gefunden" in Outlook im Web erhalten?

Wenn Sie Outlook im Web verwenden und die Fehlermeldung  **Postfach konnte nicht gefunden werden für**  angezeigt wird, verfügt das Konto, das Sie für die Verbindung mit Outlook im Web verwendet haben, nicht über eine Exchange Online-Lizenz und daher ist dem Konto kein Postfach zugeordnet. 

## <a name="assign-a-license-to-your-account"></a>Eine Lizenz Ihrem Konto zuweisen

Ihr Administrator kann Ihrem Konto eine Lizenz zuweisen, indem er die folgenden Schritte ausführt:

1. Öffnen Sie das  [ Microsoft 365 Admin Center](https://portal.office.com/adminportal/home#/homepage)  und gehen Sie zu  **Aktive Benutzer**  im Abschnitt  **Benutzer**  und wählen Sie den Benutzer aus, bei dem der Fehler auftritt.
1. Wechseln Sie auf der sich öffnenden Benutzerseite in den Bereich  **Lizenzen und Apps**, wählen Sie den entsprechenden  **Standortwert**  aus und weisen Sie eine Lizenz zu, die Exchange Online enthält (erweitern Sie die Lizenz, um ihre Details zu sehen). 
1. Klicken Sie nach Abschluss des Vorgangs auf **Änderungen speichern**.

## <a name="related-content"></a>Verwandte Inhalte

[Hinzufügen eines weiteren E-Mail-Alias für einen Benutzer](../email/add-another-email-alias-for-a-user.md) (Artikel)\
[Konfigurieren der E-Mail-Weiterleitung in Microsoft 365](../email/configure-email-forwarding.md) (Artikel)\
[Erstellen eines freigegebenen Postfachs](../email/create-a-shared-mailbox.md) (Artikel)