---
title: Abrufen von Vorfallbenachrichtigungen in Microsoft 365 Defender
description: Informationen zum Erstellen von Regeln zum Abrufen von e-Mail-Benachrichtigungen für Vorfälle in Microsoft 365 Defender
keywords: Vorfall, e-Mail, e-Mail-notfications, konfigurieren, Benutzer, Postfach, e-Mail, Vorfälle
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
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
ms.openlocfilehash: 3af1dcfec165c88a18cbc0d8cbf6866bb6398adc
ms.sourcegitcommit: 1a9f0f878c045e1ddd59088ca2a94397605a242a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/14/2020
ms.locfileid: "49668322"
---
# <a name="get-incident-notifications-by-email"></a>Abrufen von Vorfallbenachrichtigungen per e-Mail

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

>[!IMPORTANT]
> Das Feature e-Mail-Benachrichtigungen für Vorfälle befindet sich derzeit in der öffentlichen Vorschau. Einige Informationen zu dieser Funktion können sich vor der kommerziellen Verfügbarkeit ändern. Microsoft übernimmt mit diesen Informationen keinerlei Gewährleistung, sei sie ausdrücklich oder konkludent.

**Gilt für:**
- Microsoft 365 Defender

Sie können Microsoft 365 Defender so einrichten, dass Sie jedes Mal, wenn neue Vorfälle oder neue Updates für vorhandene Vorfälle vorliegen, per e-Mail benachrichtigt werden. 

Sie können auswählen, ob Benachrichtigungen basierend auf dem Schweregrad des Vorfalls oder nach Gerätegruppen abgerufen werden sollen. Sie können auch festlegen, dass eine Benachrichtigung nur beim ersten Update pro Vorfall abgerufen wird.

Sie können Empfänger in e-Mail-Benachrichtigungen hinzufügen oder entfernen. Neu hinzugefügte Empfänger werden über Vorfälle benachrichtigt, nachdem Sie hinzugefügt wurden. 

Die e-Mail-Benachrichtigung enthält wichtige Details zu dem Vorfall, beispielsweise den Vorfall Namen, den Schweregrad und die Kategorien, unter anderem. Sie können auch direkt zu Vorfälle wechseln, damit Sie sofort mit der Untersuchung beginnen können. Weitere Informationen zur Untersuchung von Vorfällen finden Sie unter [untersuchen von Vorfällen in Microsoft 365 Defender](https://docs.microsoft.com/microsoft-365/security/mtp/investigate-incidents).

>[!NOTE]
>Sie benötigen die Berechtigungen "Sicherheitseinstellungen verwalten" zum Konfigurieren von Einstellungen für e-Mail-Benachrichtigungen. Wenn Sie sich für die Verwendung der grundlegenden Berechtigungsverwaltung entschieden haben, können Benutzer mit Sicherheitsadministrator-oder globalen Administrator Rollen e-Mail-Benachrichtigungen für Sie konfigurieren. <br> <br>
Wenn Ihre Organisation rollenbasierte Zugriffssteuerung (Role-Based Access Control, RBAC) verwendet, können Sie Benachrichtigungen nur basierend auf Gerätegruppen erstellen, bearbeiten, löschen und empfangen, die Sie verwalten dürfen.

## <a name="create-rules-for-incident-notifications"></a>Erstellen von Regeln für Vorfallbenachrichtigungen

Um Ihre erste e-Mail-Benachrichtigung für Vorfälle einzurichten, erstellen Sie eine neue Regel und passen die Einstellungen für e-Mail-Benachrichtigungen an.

1. Wählen Sie im Navigationsbereich die Option **Einstellungen** für  >  **Vorfall-e-Mail-Benachrichtigungen** aus.
2. Wählen Sie **Element hinzufügen** aus.
3. Geben Sie der Regel einen Namen in **Name** , und geben Sie eine **Beschreibung** an.

    ![Fenster "Regel erstellen" für Vorfall-e-Mail notifs](../../media/incidentemailnotif1.png) 
4. Wählen Sie **weiter** aus, um zu **Benachrichtigungseinstellungen** zu wechseln. Hier können Sie Folgendes angeben:
    - **Warnungsschweregrad** – wählen Sie den Warnungsschweregrad aus, der eine Vorfall Benachrichtigung auslösen wird. Wenn Sie beispielsweise nur über Vorfälle mit hohem Schweregrad informiert werden möchten, wählen Sie hoch.
    - **Gerätegruppen Bereich** : in diesem Dropdown werden alle Gerätegruppen angezeigt, auf die der Benutzer zugreifen kann. Wählen Sie aus, für welche Gerätegruppen die Vorfall Benachrichtigungsregeln erstellt werden sollen.
    - **Nur beim ersten Auftreten pro Vorfall Benachrichtigen** – Wenn Sie diese Option auswählen, wird eine e-Mail-Benachrichtigung nur bei der ersten Benachrichtigung gesendet, die ihren anderen Auswahlen entspricht. Spätere Aktualisierungen oder Warnungen im Zusammenhang mit dem Vorfall lösen keine Benachrichtigung aus.
    - **Organisationsname einbeziehen** : gibt an, ob der Name des Kunden in der e-Mail-Benachrichtigung angezeigt wird oder nicht.
    - **Mandanten spezifischer Portal Link einbeziehen** – fügt einen Link mit der Mandanten-ID hinzu, um den Zugriff auf einen bestimmten Mandanten zuzulassen.
    
    ![Benach-Einstellungsfenster für Vorfall-e-Mail-notifs](../../media/incidentemailnotif2.png)
5. Wählen Sie **weiter** aus, um den Abschnitt **Empfänger** zu wechseln. Hier können Sie e-Mail-Adressen angeben, die die Vorfall-e-Mail-Benachrichtigungen erhalten sollen. Wählen Sie **Empfänger hinzufügen** aus, nachdem Sie jede e-Mail-Adresse eingegeben haben.

    ![Fenster "Empfänger hinzufügen" für Vorfall-e-Mail notifs](../../media/incidentemailnotif3.png) 

6. Wählen Sie schließlich **weiter** , um zur **Überprüfungsregel** zu wechseln, damit Sie alle mit der neuen Regel verknüpften Einstellungen sehen können. Empfänger erhalten Benachrichtigungen über e-Mails basierend auf den Einstellungen.

## <a name="see-also"></a>Siehe auch
- [Übersicht über Vorfälle in Microsoft 365 Defender](https://docs.microsoft.com/microsoft-365/security/mtp/incidents-overview)
- [Priorisieren von Vorfällen in Microsoft 365 Defender](https://docs.microsoft.com/microsoft-365/security/mtp/incident-queue)
- [Untersuchen von Vorfällen in Microsoft 365 Defender](https://docs.microsoft.com/microsoft-365/security/mtp/investigate-incidents)

