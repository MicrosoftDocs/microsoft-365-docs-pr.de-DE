---
title: Verwalten von Aufbewahrungsbenachrichtigungen
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: Verwenden Sie den Kommunikations Workflow in Advanced eDiscovery, um den Status Ihrer Benachrichtigungen über rechtliche Aufbewahrungen nachzuverfolgen und gegebenenfalls zu aktualisieren und erneut zu senden.
ms.openlocfilehash: 8852bfd1651e1855d276b60ba6fac35c378d4631
ms.sourcegitcommit: 6d672eb8287526a9db90df5fa85bc4984a7047d1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/26/2020
ms.locfileid: "42280113"
---
# <a name="manage-hold-notifications"></a>Verwalten von Aufbewahrungsbenachrichtigungen

Nachdem Sie den Benachrichtigungs Workflow für juristische Aufbewahrung initiiert haben, können Sie den Kommunikations Workflow in Advanced eDiscovery verwenden, um den Status Ihrer Kommunikation nachzuverfolgen. Die Registerkarte Kommunikationen enthält eine Liste aller Benachrichtigungen in Ihrem erweiterten eDiscovery-Fall. Sie können Details sehen, beispielsweise die Anzahl der Verwalter, denen die Benachrichtigung zugewiesen wurde oder die den Hinweis bestätigt haben.

## <a name="monitor-acknowledgments"></a>Überwachen von Bestätigungen

Nachdem Sie eine Kommunikation auf der Registerkarte **Kommunikationen** ausgewählt haben, können Sie eine Liste der Verwalter anzeigen, die einen halte Hinweis bestätigt haben. 

1. Wechseln Sie im Compliance Center zu **eDiscovery > Advanced eDiscovery**.

2. Wählen Sie einen Fall aus, und klicken Sie dann auf die Registerkarte **Kommunikation** .

3. Wählen Sie eine Kommunikation aus, um die Flyout-Seite für die **Depot Kommunikation** anzuzeigen.

Auf der Seite mit den Kommunikations Flyouts wird eine Liste der Verwalter angezeigt, die der ausgewählten Kommunikation zugeordnet sind. Auf dieser Seite werden außerdem Einblicke und Informationen darüber angezeigt, wie viele Bestätigungen empfangen wurden und wie viele hervorragend sind. Auf der Seite wird auch gezeigt, welche Verwalter eine Bestätigung gesendet haben, dass Sie die Aufbewahrungs Benachrichtigung erhalten haben.

## <a name="re-send-a-hold-notice"></a>Erneutes Senden eines halte Vermerks

Gelegentlich verlieren depotverwalter die Spuren von e-Mail-Nachrichten in ihrer täglichen Arbeit. Oder für einen langwierigen Rechtsstreit Fall kann ein depotverwalter Sie oder andere kontaktieren und bitten, dass Sie eine Benachrichtigung erneut senden. Wenn Sie den Kommunikations Workflow für rechtliche Aufbewahrungs Benachrichtigungen verwalten, müssen Sie möglicherweise erneut einen Hinweis senden, um ihn wieder an die "Oberseite des Postfachs eines Benutzers" zurückzusenden.

So senden Sie einen Aufbewahrungs Bescheid erneut an eine Depotbank:

1. Wählen Sie in Advanced eDiscovery einen Fall aus, und klicken Sie dann auf die Registerkarte **Kommunikationen** .

2. Wählen Sie eine Kommunikation aus, um die Flyout-Seite für die **Depot Kommunikation** anzuzeigen.

3. Klicken Sie auf **Weitere > halte Hinweis erneut senden**.

4. Wählen Sie auf der Flyout-Seite zum **erneuten Senden von halte** hinweisen die Verwalter aus, denen Sie den Hinweis erneut senden möchten, und geben Sie einen optionalen Grund ein.

5. Klicken Sie auf **erneut senden** , um den Hinweis an die ausgewählten Verwalter zu senden.

Wenn ein depotverwalter die Aufbewahrungs Benachrichtigung nicht bestätigt hat, wird der Erinnerungs-und Eskalations Workflow neu gestartet. Wenn ein depotverwalter den Aufbewahrungs Vermerk bestätigt hat, erhält der Verwalter eine Kopie des ursprünglichen Aufbewahrungs Bescheids.

> [!NOTE]
> Sie können eine rechtliche Aufbewahrungs Benachrichtigung nur an Verwalter senden, die der Kommunikation zugeordnet sind. 

## <a name="update-preservation-requirements"></a>Aktualisieren von Aufbewahrungsanforderungen
  
Im Fall von Fortschritten müssen Verwalter möglicherweise zusätzliche oder weniger Daten aufbewahren, als zuvor angewiesen wurde. In eDiscovery-Ausdrücken müssen Sie den halte Hinweis mit aktualisierten Inhalten erneut ausgeben.

So aktualisieren Sie den Inhalt des ersten halte Vermerks:

1. Wählen Sie in Advanced eDiscovery einen Fall aus, und klicken Sie dann auf die Registerkarte **Kommunikationen** .

2. Wählen Sie den Aufbewahrungs Hinweis aus, den Sie aktualisieren möchten, und klicken Sie auf der Flyout-Seite " **Depot Kommunikation** " auf **Bearbeiten** .

3. Klicken Sie im Assistenten zum **Bearbeiten von Kommunikation** im linken Bereich des Assistenten auf **Portal Inhalt definieren** , und aktualisieren Sie den Inhalt des Benachrichtigungs-Assistenten.

4. Klicken Sie auf **Speichern**.

Die Ankündigung zur erneuten Veröffentlichung wird an alle Verwalter gesendet, die der rechtlichen Aufbewahrungs Benachrichtigung zugeordnet sind. Wenn die Erinnerung oder der Eskalations Hinweis aktiviert ist, werden die Workflows für diese Arten von Benachrichtigungen außerdem neu gestartet.

## <a name="update-legal-hold-notifications-and-settings"></a>Benachrichtigungen und Einstellungen für Legal Hold-Speicher aktualisieren

Wenn Sie den Inhalt oder die Einstellungen der Veröffentlichungs-, Freigabe-, Erinnerungs-oder Eskalations Benachrichtigung aktualisieren, gelten diese Änderungen für die gesamte vom Workflow generierte zukünftige Kommunikation.

## <a name="more-information"></a>Weitere Informationen

- [Hinzufügen von Verwaltungsberechtigten zu einem Fall](add-custodians-to-case.md)

- [Erstellen eines rechtlichen Aufbewahrungs Vermerks](create-hold-notification.md)

- [Bestätigen einer Aufbewahrungsbenachrichtigung](acknowledge-hold-notification.md)
