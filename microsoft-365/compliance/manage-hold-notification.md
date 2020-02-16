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
description: ''
ms.openlocfilehash: f10995e5180afc0d8aa7de2b2fdb8040f0f838ac
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42072012"
---
# <a name="manage-hold-notifications"></a>Verwalten von Aufbewahrungsbenachrichtigungen

Nachdem Sie den Benachrichtigungs Workflow für juristische Aufbewahrung initiiert haben, können Sie die erweiterte eDiscovery nutzen, um den Status Ihrer Kommunikation nachzuverfolgen. Auf der Registerkarte Kommunikationen werden alle Aufbewahrungs Benachrichtigungen in Ihrem erweiterten eDiscovery-Fall präsentiert. Hier werden Details angezeigt, beispielsweise die Anzahl der Verwalter, denen die Benachrichtigung zugewiesen wurde oder die den Hinweis bestätigt haben.

## <a name="view-communication-details"></a>Anzeigen von Kommunikationsdetails

### <a name="track-acknowledgements"></a>Nachverfolgen von Bestätigungen

Nachdem Sie eine Kommunikation über die Registerkarte **Kommunikationen**ausgewählt haben, können Sie eine Liste der Verwalter anzeigen, die einen halte Hinweis bestätigt haben. 

### <a name="preview-acknowledgements"></a>Vorschau Bestätigungen

Im Flyout Kommunikationsdetails können Sie die Details zur rechtlichen Aufbewahrungs Kommunikation in einer Vorschau anzeigen. Im **Vorschaufenster** können Sie eine kurze Momentaufnahme ihres rechtlichen Aufbewahrungs Vermerks sowie die Einstellungen und Inhalte für Ihre Workflow Benachrichtigungen sehen. Im Vorschaufenster werden außerdem Details angezeigt, um die die Verwalter den Hinweis bereits bestätigt haben.

## <a name="taking-action-on-existing-communications"></a>Ausführen von Aktionen für die vorhandene Kommunikation

### <a name="re-send-a-hold-notice"></a>Erneutes Senden eines halte Vermerks

Gelegentlich verlieren depotverwalter Ihre e-Mails in Ihrer alltäglichen Arbeit. Bei einem langwierigen Rechtsstreit kann ein depotverwalter möglicherweise einen Antrag stellen und Sie bitten, eine Nachricht erneut zu senden. Wenn Sie Ihren Workflow um rechtliche Aufbewahrungs Vermerke verwalten, müssen Sie möglicherweise erneut einen Hinweis senden, um ihn wieder an die "Oberseite des Postfachs eines Benutzers" zurückzusenden.

Sie können einen Aufbewahrungs Bescheid erneut an Ihre Depotbank senden, indem Sie:
1. Navigieren Sie zu einem Fall in **Security and Compliance > Advanced eDiscovery**.
2. Nachdem Sie einen Fall ausgewählt haben, navigieren Sie zur Registerkarte **Kommunikationen** .
3. Um eine rechtliche Aufbewahrungsfrist an eine Depotbank erneut zu senden, wählen Sie die Kommunikation aus, und klicken Sie auf die Option **erneut senden** .
4. Wenn ein depotverwalter seine Aufbewahrungs Benachrichtigung noch nicht bestätigt hat, wird der Erinnerungs-und Eskalations Fluss neu gestartet. Wenn ein depotverwalter den Aufbewahrungs Bescheid bereits bestätigt hat, erhält der Verwalter lediglich eine Kopie des ursprünglichen Aufbewahrungs Bescheids.

> [!NOTE]
> Sie können eine rechtliche Aufbewahrungs Benachrichtigung nur an Verwalter senden, die der Kommunikation zugeordnet sind. 

### <a name="edit-a-communication"></a>Bearbeiten einer Kommunikation

#### <a name="update-preservation-requirements"></a>Aktualisieren von Aufbewahrungsanforderungen
  
Im Fall von Fortschritten müssen Verwalter möglicherweise zusätzliche oder weniger Daten aufbewahren, als zuvor angewiesen wurde. In eDiscovery-Ausdrücken müssen Sie den halte Hinweis mit aktualisierten Inhalten erneut ausgeben.

So aktualisieren Sie den Inhalt des ersten halte Vermerks:

1. Navigieren Sie zu einem Fall in **Security and Compliance > Advanced eDiscovery**.
2. Nachdem Sie einen Fall ausgewählt haben, navigieren Sie zur Registerkarte **Kommunikationen** .
3. Wählen Sie den Aufbewahrungs Hinweis aus, den Sie aktualisieren möchten, und klicken Sie auf **Bearbeiten**.
4. Wählen Sie im Workflow bearbeiten die Option **Portal Inhalt definieren** aus, und aktualisieren Sie den Inhalt des Benachrichtigungs Inhalts. 
5. Klicken Sie auf **Speichern**. Nach dem Speichern wird die erneute Veröffentlichungs Benachrichtigung an alle Verwalter gesendet, die der rechtlichen Aufbewahrungs Benachrichtigung derzeit zugewiesen sind. Wenn die Mahnungen/Eskalations Benachrichtigungen aktiviert sind, werden diese Workflows ebenfalls neu gestartet. 


#### <a name="update-legal-hold-notifications-and-settings"></a>Benachrichtigungen und Einstellungen für Legal Hold-Speicher aktualisieren

Wenn Sie den Inhalt oder die Einstellungen der Veröffentlichungs-, Freigabe-, Erinnerungs-oder Eskalations Benachrichtigung aktualisieren, gelten diese Änderungen für alle zukünftigen vom Workflow generierten Kommunikationen.

## <a name="related-information"></a>Weitere Informationen 

- [Erstellen eines rechtlichen Aufbewahrungs Vermerks](create-hold-notification.md)
    
- [Bestätigen einer Aufbewahrungsbenachrichtigung](acknowledge-hold-notification.md)
    
- [Hinzufügen von Verwaltungsberechtigten zu einem Fall](add-custodians-to-case.md)
