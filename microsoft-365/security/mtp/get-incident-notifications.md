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
ms.author: maccruz
author: schmurky
ms.localizationpriority: medium
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
ms.openlocfilehash: c6b255f7815a5b49cd0fb5ed27da0cf642ff2ca7
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50928832"
---
# <a name="get-incident-notifications-by-email"></a>Vorfallbenachrichtigungen per E-Mail erhalten

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gilt für:**
- Microsoft 365 Defender

Sie können Microsoft 365 Defender so einrichten, dass Sie per E-Mail benachrichtigt werden, wenn es neue Vorfälle oder neue Updates zu vorhandenen Vorfällen gibt. 

Sie können Benachrichtigungen basierend auf dem Schweregrad des Vorfalls oder nach Gerätegruppe erhalten. Sie können auch festlegen, dass eine Benachrichtigung nur für das erste Update pro Vorfall angezeigt wird.

Sie können Empfänger in den E-Mail-Benachrichtigungen hinzufügen oder entfernen. Neu hinzugefügte Empfänger werden über Vorfälle benachrichtigt, nachdem sie hinzugefügt wurden. 

Die E-Mail-Benachrichtigung enthält wichtige Details zu dem Vorfall, z. B. den Vorfallnamen, schweregrad und Kategorien. Sie können auch direkt zu Vorfällen wechseln, damit Sie ihre Untersuchung sofort starten können. Weitere Informationen zur Untersuchung von Vorfällen finden Sie unter [Investigate incidents in Microsoft 365 Defender](./investigate-incidents.md).

>[!NOTE]
>Sie benötigen Berechtigungen zum Verwalten von Sicherheitseinstellungen, um E-Mail-Benachrichtigungseinstellungen zu konfigurieren. Wenn Sie sich für die Verwendung der grundlegenden Berechtigungsverwaltung entschieden haben, können Benutzer mit Sicherheitsadministrator- oder globalen Administratorrollen E-Mail-Benachrichtigungen für Sie konfigurieren. <br> <br>
Wenn Ihre Organisation rollenbasierte Zugriffssteuerung (Role-Based Access Control, RBAC) verwendet, können Sie nur Benachrichtigungen basierend auf Gerätegruppen erstellen, bearbeiten, löschen und empfangen, die Sie verwalten dürfen.

## <a name="create-rules-for-incident-notifications"></a>Erstellen von Regeln für Vorfallbenachrichtigungen

Erstellen Sie zum Einrichten der ersten E-Mail-Benachrichtigung für Vorfälle eine neue Regel, und passen Sie die Einstellungen für E-Mail-Benachrichtigungen an.

1. Wählen Sie im Navigationsbereich Einstellungen  >  **Vorfall-E-Mail-Benachrichtigungen aus.**
2. Wählen **Sie Element hinzufügen aus.**
3. Geben Sie der Regel einen Namen in **Name und** geben Sie eine **Beschreibung an.**

    ![Erstellen eines Regelfensters für Vorfall-E-Mail-Notifen](../../media/incidentemailnotif1.png) 
4. Wählen **Sie Weiter** aus, um zu **Benachrichtigungseinstellungen zu wechseln.** Hier können Sie angeben:
    - **Warnungsschweregrad:** Wählen Sie den Warnungsschweregrad aus, der eine Vorfallbenachrichtigung auslöst. Wenn Sie beispielsweise nur über Vorfälle mit hohem Schweregrad informiert werden möchten, wählen Sie Hoch aus.
    - **Gerätegruppenbereich** – In diesem Dropdown werden alle Gerätegruppen angezeigt, auf die der Benutzer zugreifen kann. Wählen Sie aus, für welche Gerätegruppen Sie die Vorfallbenachrichtigungsregeln erstellen.
    - **Nur beim ersten Auftreten pro** Vorfall benachrichtigen – Wenn Sie diese Option auswählen, wird nur bei der ersten Warnung eine E-Mail-Benachrichtigung gesendet, die Mit Ihrer anderen Auswahl entspricht. Spätere Updates oder Warnungen im Zusammenhang mit dem Vorfall lösen keine Benachrichtigung aus.
    - **Name der Organisation angeben** – Gibt an, ob der Name des Kunden in der E-Mail-Benachrichtigung angezeigt wird oder nicht.
    - **Mandantenspezifischer Portallink hinzufügen** – Fügt einen Link mit der Mandanten-ID hinzu, um zugriff auf einen bestimmten Mandanten zu ermöglichen.
    
    ![Notif settings window for incident email notifs](../../media/incidentemailnotif2.png)
5. Wählen **Sie Weiter** aus, um den Abschnitt **Empfänger** zu wechseln. Hier können Sie E-Mail-Adressen angeben, die die Vorfall-E-Mail-Benachrichtigungen erhalten. Wählen **Sie Nach eingabe jeder** E-Mail-Adresse einen Empfänger hinzufügen aus.

    ![Hinzufügen eines Empfängerfensters für Vorfall-E-Mail-Notifen](../../media/incidentemailnotif3.png) 

6. Wählen Sie schließlich **Weiter** aus, um zu **Überprüfungsregel zu wechseln,** damit Sie alle Einstellungen sehen können, die ihrer neuen Regel zugeordnet sind. Empfänger erhalten Benachrichtigungen über Vorfälle über E-Mail basierend auf den Einstellungen.

## <a name="see-also"></a>Siehe auch
- [Übersicht über Vorfälle in Microsoft 365 Defender](./incidents-overview.md)
- [Priorisieren von Vorfällen in Microsoft 365 Defender](./incident-queue.md)
- [Untersuchen von Vorfällen in Microsoft 365 Defender](./investigate-incidents.md)