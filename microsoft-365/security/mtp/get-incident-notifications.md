---
title: Vorfallbenachrichtigungen in Microsoft 365 Defender erhalten
description: Erfahren Sie, wie Sie Regeln erstellen, um E-Mail-Benachrichtigungen für Vorfälle in Microsoft 365 Defender zu erhalten.
keywords: Vorfall, E-Mail, E-Mail-Notationen, konfigurieren, Benutzer, Postfach, E-Mail, Vorfälle
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
ms.openlocfilehash: 9db025818fdd5eb2635a9a676e4a10e20f3036b6
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/22/2021
ms.locfileid: "49930978"
---
# <a name="get-incident-notifications-by-email"></a>Vorfallbenachrichtigungen per E-Mail erhalten

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gilt für:**
- Microsoft 365 Defender

Sie können Microsoft 365 Defender so einrichten, dass Sie jedes Mal per E-Mail benachrichtigt werden, wenn es neue Vorfälle oder neue Updates für vorhandene Vorfälle gibt. 

Sie können Benachrichtigungen basierend auf dem Schweregrad des Vorfalls oder nach Gerätegruppe erhalten. Sie können auch festlegen, dass eine Benachrichtigung nur beim ersten Update pro Vorfall angezeigt wird.

Sie können Empfänger in den E-Mail-Benachrichtigungen hinzufügen oder entfernen. Neu hinzugefügte Empfänger werden über Vorfälle benachrichtigt, nachdem sie hinzugefügt wurden. 

Die E-Mail-Benachrichtigung enthält wichtige Details zu dem Vorfall, z. B. den Vorfallnamen, schweregrad und Kategorien. Sie können auch direkt zu Vorfällen wechseln, damit Sie ihre Untersuchung sofort starten können. Weitere Informationen zur Untersuchung von Vorfällen finden Sie unter ["Untersuchen von Vorfällen in Microsoft 365 Defender".](https://docs.microsoft.com/microsoft-365/security/mtp/investigate-incidents)

>[!NOTE]
>Sie benötigen die Berechtigungen "Sicherheitseinstellungen verwalten", um E-Mail-Benachrichtigungseinstellungen zu konfigurieren. Wenn Sie sich für die Verwendung der grundlegenden Berechtigungsverwaltung entschieden haben, können Benutzer mit Sicherheitsadministrator- oder globalen Administratorrollen E-Mail-Benachrichtigungen für Sie konfigurieren. <br> <br>
Wenn Ihre Organisation die rollenbasierte Zugriffssteuerung (Role-Based Access Control, RBAC) verwendet, können Sie entsprechend nur Benachrichtigungen basierend auf Gerätegruppen erstellen, bearbeiten, löschen und empfangen, die Sie verwalten dürfen.

## <a name="create-rules-for-incident-notifications"></a>Erstellen von Regeln für Vorfallbenachrichtigungen

Erstellen Sie zum Einrichten Ihrer ersten E-Mail-Benachrichtigung für Vorfälle eine neue Regel, und passen Sie die Einstellungen für E-Mail-Benachrichtigungen an.

1. Wählen Sie im Navigationsbereich E-Mail-Benachrichtigungen  >  **zu Einstellungen für Vorfälle aus.**
2. Wählen Sie **"Element hinzufügen" aus.**
3. Geben Sie der Regel einen Namen im **Namen und** geben Sie eine **Beschreibung an.**

    ![Erstellen eines Regelfensters für Vorfall-E-Mail-Notififen](../../media/incidentemailnotif1.png) 
4. Wählen **Sie "Weiter"** aus, um zu den **Benachrichtigungseinstellungen zu wechseln.** Hier können Sie angeben:
    - **Warnungsschweregrad** : Wählen Sie den Warnungsschweregrad aus, der eine Vorfallbenachrichtigung auslöst. Wenn Sie beispielsweise nur über Vorfälle mit hohem Schweregrad informiert werden möchten, wählen Sie "Hoch" aus.
    - **Gerätegruppenbereich** – In dieser Dropdownliste werden alle Gerätegruppen angezeigt, auf die der Benutzer zugreifen kann. Wählen Sie aus, für welche Gerätegruppen Sie vorfallbenachrichtigungsregeln erstellen.
    - **Nur beim ersten Auftreten pro** Vorfall benachrichtigen – Wenn Sie diese Option auswählen, wird nur bei der ersten Warnung eine E-Mail-Benachrichtigung gesendet, die Ihrer anderen Auswahl entspricht. Spätere Updates oder Warnungen im Zusammenhang mit dem Vorfall lösen keine Benachrichtigung aus.
    - **Name der Organisation angeben** – Gibt an, ob der Name des Kunden in der E-Mail-Benachrichtigung angezeigt wird oder nicht.
    - **Mandantenspezifische Portallink hinzufügen** – Fügt einen Link mit der Mandanten-ID hinzu, um den Zugriff auf einen bestimmten Mandanten zu ermöglichen.
    
    ![Fenster "Notif settings" für Vorfall-E-Mail-Notifen](../../media/incidentemailnotif2.png)
5. Wählen **Sie "Weiter"** aus, um zum Abschnitt **"Empfänger" zu** wechseln. Hier können Sie E-Mail-Adressen angeben, die die Vorfall-E-Mail-Benachrichtigungen erhalten. Wählen **Sie nach der Eingabe jeder** E-Mail-Adresse die Option "Empfänger hinzufügen" aus.

    ![Fenster "Empfänger hinzufügen" für Vorfall-E-Mail-Notifen](../../media/incidentemailnotif3.png) 

6. Wählen Sie schließlich **"Weiter"** aus, **um** zur Regel "Überprüfen" zu wechseln, damit Sie alle Einstellungen sehen können, die der neuen Regel zugeordnet sind. Empfänger erhalten Benachrichtigungen über Vorfälle per E-Mail basierend auf den Einstellungen.

## <a name="see-also"></a>Siehe auch
- [Übersicht über Vorfälle in Microsoft 365 Defender](https://docs.microsoft.com/microsoft-365/security/mtp/incidents-overview)
- [Priorisieren von Vorfällen in Microsoft 365 Defender](https://docs.microsoft.com/microsoft-365/security/mtp/incident-queue)
- [Untersuchen von Vorfällen in Microsoft 365 Defender](https://docs.microsoft.com/microsoft-365/security/mtp/investigate-incidents)

