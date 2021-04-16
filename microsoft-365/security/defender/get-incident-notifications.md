---
title: Vorfallbenachrichtigungen in Microsoft 365 Defender erhalten
description: Informationen zum Erstellen von Regeln zum Erhalten von E-Mail-Benachrichtigungen für Vorfälle in Microsoft 365 Defender
keywords: Incident, email, email notfications, configure, users, mailbox, email, incidents
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 72a1f8fe71efcfa7f4f73671611576a454b508e6
ms.sourcegitcommit: 22505ce322f68a2d0ce70d71caf3b0a657fa838a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/16/2021
ms.locfileid: "51861313"
---
# <a name="get-incident-notifications-by-email"></a>Vorfallbenachrichtigungen per E-Mail erhalten

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gilt für:**
- Microsoft 365 Defender

Sie können Microsoft 365 Defender einrichten, um Ihre Mitarbeiter per E-Mail über neue Vorfälle oder Updates zu vorhandenen Vorfällen zu benachrichtigen. Sie können Benachrichtigungen basierend auf:

- Schweregrad des Vorfalls.
- Gerätegruppe.
- Nur beim ersten Update pro Vorfall.

Die E-Mail-Benachrichtigung enthält wichtige Details zu dem Vorfall, z. B. den Vorfallnamen, schweregrad und Kategorien. Sie können auch direkt zu dem Vorfall wechseln und ihre Untersuchung sofort starten. Weitere Informationen finden Sie unter [Investigate incidents](investigate-incidents.md).

Sie können Empfänger in den E-Mail-Benachrichtigungen hinzufügen oder entfernen. Neue Empfänger werden über Vorfälle benachrichtigt, nachdem sie hinzugefügt wurden. 

>[!NOTE]
>Sie benötigen die Berechtigung "Sicherheitseinstellungen verwalten", um E-Mail-Benachrichtigungseinstellungen zu konfigurieren. Wenn Sie sich für die Verwendung der grundlegenden Berechtigungsverwaltung entschieden haben, können Benutzer mit Sicherheitsadministrator- oder globalen Administratorrollen E-Mail-Benachrichtigungen für Sie konfigurieren. <br> <br>
Wenn Ihre Organisation rollenbasierte Zugriffssteuerung (Role-Based Access Control, RBAC) verwendet, können Sie nur Benachrichtigungen basierend auf Gerätegruppen erstellen, bearbeiten, löschen und empfangen, die Sie verwalten dürfen.

## <a name="create-a-rule-for-email-notifications"></a>Erstellen einer Regel für E-Mail-Benachrichtigungen

Führen Sie die folgenden Schritte aus, um eine neue Regel zu erstellen und E-Mail-Benachrichtigungseinstellungen anzupassen.

1. Wählen Sie im Navigationsbereich Einstellungen **> Microsoft 365 Defender > Vorfall-E-Mail-Benachrichtigungen aus.**
2. Wählen **Sie Element hinzufügen aus.**
3. Geben Sie **auf der** Seite Grundlagen den Regelnamen und eine Beschreibung ein, und wählen Sie dann **Weiter aus.**
4. Konfigurieren Sie **auf der** Seite Benachrichtigungseinstellungen:
    - **Warnungsschweregrad:** Wählen Sie den Warnungsschweregrad aus, der eine Vorfallbenachrichtigung auslöst. Wenn Sie beispielsweise nur über Vorfälle mit hohem Schweregrad informiert werden möchten, wählen Sie **Hoch aus.**
    - **Gerätegruppenbereich** : Sie können alle Gerätegruppen angeben oder aus der Liste der Gerätegruppen in Ihrem Mandanten auswählen.
    - **Nur beim ersten Auftreten pro Vorfall** benachrichtigen – Wählen Sie aus, wenn Sie eine Benachrichtigung nur für die erste Warnung wünschen, die Mit Ihrer anderen Auswahl entspricht. Spätere Updates oder Warnungen im Zusammenhang mit dem Vorfall senden keine zusätzlichen Benachrichtigungen.
    - **Organisationsname in die E-Mail eingeben** – Wählen Sie aus, ob Ihr Organisationsname in der E-Mail-Benachrichtigung angezeigt werden soll.
    - **Mandantenspezifischer Portallink hinzufügen** – Wählen Sie aus, ob Sie einen Link mit der Mandanten-ID in der E-Mail-Benachrichtigung für den Zugriff auf einen bestimmten Microsoft 365-Mandanten hinzufügen möchten.

    :::image type="content" source="../../media/get-incident-notifications/incidents-ss-email-notification-settings.png" alt-text="Benachrichtigungseinstellungen für Vorfall-E-Mail-Benachrichtigungen":::

5. Wählen Sie **Weiter** aus. Fügen Sie **auf der** Seite Empfänger die E-Mail-Adressen hinzu, die die Vorfallbenachrichtigungen erhalten. Wählen **Sie Nach** eingabe jeder neuen E-Mail-Adresse hinzufügen aus. Um Benachrichtigungen zu testen und sicherzustellen, dass die Empfänger sie in den Posteingangen empfangen, wählen Sie **Test-E-Mail senden aus.** 
6. Wählen Sie **Weiter** aus. Überprüfen Sie **auf der Seite** Regel überprüfen die Einstellungen der Regel, und wählen Sie dann Regel erstellen **aus.** Empfänger erhalten Benachrichtigungen über Vorfälle über E-Mail basierend auf den Einstellungen.

Um eine vorhandene Regel zu bearbeiten, wählen Sie sie aus der Liste der Regeln aus. Wählen Sie im Bereich mit  dem Regelnamen Regel bearbeiten aus, und nehmen Sie ihre Änderungen auf den Seiten **Grundlagen, Benachrichtigungseinstellungen** **und** **Empfänger** vor.

Um eine vorhandene Regel zu bearbeiten, wählen Sie sie aus der Liste der Regeln aus. Wählen Sie im Bereich mit dem Regelnamen Löschen **aus.**

## <a name="see-also"></a>Siehe auch
- [Übersicht über Vorfälle](incidents-overview.md)
- [Priorisieren von Vorfällen](incident-queue.md)
- [Untersuchen von Vorfällen](investigate-incidents.md)
