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
description: Verwenden Sie den Kommunikationsworkflow in Advanced eDiscovery, um den Status Ihrer Benachrichtigungen zum rechtlichen Haltestatus nachverfolgt und gegebenenfalls zu aktualisieren und erneut zu senden.
ms.openlocfilehash: 8852bfd1651e1855d276b60ba6fac35c378d4631
ms.sourcegitcommit: 6d672eb8287526a9db90df5fa85bc4984a7047d1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/26/2020
ms.locfileid: "42280113"
---
# <a name="manage-hold-notifications"></a>Verwalten von Aufbewahrungsbenachrichtigungen

Nachdem Sie den Workflow für Benachrichtigungen über rechtliches Haltestatus initiiert haben, können Sie den Kommunikationsworkflow in Advanced eDiscovery verwenden, um den Status Ihrer Kommunikation nachverfolgt. Die Registerkarte Kommunikation enthält eine Liste aller Benachrichtigungen innerhalb Advanced eDiscovery Fall. Sie können Details wie die Anzahl der Verwahrer anzeigen, die zugewiesen wurden oder den Hinweis bestätigt haben.

## <a name="monitor-acknowledgments"></a>Überwachen von Bestätigungen

Nachdem Sie auf der  Registerkarte Kommunikation eine Kommunikation ausgewählt haben, können Sie eine Liste der Verwahrer anzeigen, die eine Haltebenachrichtigung bestätigt haben. 

1. Wechseln Sie im Compliance Center zu **eDiscovery > Advanced eDiscovery**.

2. Wählen Sie einen Fall aus, und klicken Sie dann auf die **Registerkarte** Kommunikation.

3. Wählen Sie eine Kommunikation aus, um die Flyoutseite **für die Custodian-Kommunikation** angezeigt zu werden.

Eine Liste der Custodians, die der ausgewählten Kommunikation zugeordnet sind, wird auf der Flyoutseite für die Kommunikation angezeigt. Auf dieser Seite werden auch Einblicke und informationen darüber angezeigt, wie viele Bestätigungen empfangen wurden und wie viele ausstehen. Die Seite zeigt auch, welche Verwahrer eine Bestätigung gesendet haben, dass sie die Haltebenachrichtigung erhalten haben.

## <a name="re-send-a-hold-notice"></a>Erneutes Senden einer Haltebenachrichtigung

Gelegentlich verlieren Verwahrer den Überblick über E-Mail-Nachrichten in ihrer täglichen Arbeit. Oder bei einem langen Rechtsstreit kann sich ein Custodian an Sie oder andere wenden und sie bitten, eine Benachrichtigung erneut zu senden. Wenn Sie den Kommunikationsworkflow für rechtliche Hinweise verwalten, müssen Sie möglicherweise eine Benachrichtigung erneut senden, um sie wieder an den "oberen Rand des Postfachs eines Benutzers" zu bringen.

So senden Sie eine Haltebenachrichtigung erneut an einen Custodian:

1. Wählen Advanced eDiscovery Fall aus, und klicken Sie dann **auf** die Registerkarte Kommunikation.

2. Wählen Sie eine Kommunikation aus, um die Flyoutseite **für die Custodian-Kommunikation** angezeigt zu werden.

3. Klicken **Sie auf Weitere > Benachrichtigung zum Erneuten Senden des Haltebemerks**.

4. Wählen Sie auf der **Flyoutseite** Benachrichtigungsbenachrichtigung erneut senden die Benachrichtigungsverwahrer aus, die Sie erneut senden möchten, und geben Sie einen optionalen Grund ein.

5. Klicken **Sie auf Erneut senden,** um den Hinweis an die ausgewählten Verwahrer zu senden.

Wenn ein Verwahrer die Haltebenachrichtigung nicht bestätigt hat, wird der Erinnerungs- und Eskalationsworkflow neu gestartet. Wenn ein Verwahrer die Haltebenachrichtigung bestätigt hat, erhält der Custodian eine Kopie des ursprünglichen Haltehinweises.

> [!NOTE]
> Sie können eine Benachrichtigung über das gesetzliche Halterecht nur an Verwahrer senden, die der Kommunikation zugewiesen sind. 

## <a name="update-preservation-requirements"></a>Updateerhaltungsanforderungen
  
Im Weiteren müssen Verwahrer möglicherweise zusätzliche oder weniger Daten als zuvor angewiesen beibehalten. In eDiscovery-Begriffen müssen Sie den Haltehinweise mit aktualisierten Inhalten erneut ausheften.

So aktualisieren Sie den Inhalt des ursprünglichen Haltehinweises:

1. Wählen Advanced eDiscovery Fall aus, und klicken Sie dann **auf** die Registerkarte Kommunikation.

2. Wählen Sie die Haltebenachrichtigung aus, die Sie aktualisieren möchten, und **klicken** Sie auf der Flyoutseite für die Benachrichtigung **über** die Verwahrung auf Bearbeiten.

3. Klicken Sie **im Assistenten** kommunikation bearbeiten im linken Bereich des Assistenten auf **Portalinhalt** definieren, und aktualisieren Sie den Inhalt des Hinweises.

4. Klicken Sie auf **Speichern**.

Der Benachrichtigung über die erneute Ausstellung wird an alle Verwahrer gesendet, die der Benachrichtigung über das gesetzliche Halterecht zugewiesen sind. Wenn außerdem die Erinnerungs- oder Eskalationsbenachrichtigung aktiviert ist, werden die Workflows für diese Arten von Benachrichtigungen neu gestartet.

## <a name="update-legal-hold-notifications-and-settings"></a>Aktualisieren von Benachrichtigungen und Einstellungen für das gesetzliche Haltehalten

Wenn Sie die Inhalte oder Einstellungen der Benachrichtigung zur Ausstellung, Veröffentlichung, Neuauflage, Erinnerung oder Eskalation aktualisieren, gelten diese Änderungen für alle zukünftigen Kommunikationen, die vom Workflow generiert werden.

## <a name="more-information"></a>Weitere Informationen

- [Hinzufügen von Verwaltungsberechtigten zu einem Fall](add-custodians-to-case.md)

- [Erstellen eines Rechtlichen Haltehinweises](create-hold-notification.md)

- [Bestätigen einer Aufbewahrungsbenachrichtigung](acknowledge-hold-notification.md)
