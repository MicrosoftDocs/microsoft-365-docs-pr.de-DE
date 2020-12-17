---
title: Verhindern von Datenverlust
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- adminvideo
monikerRange: o365-worldwide
search.appverid:
- BCS160
- MET150
- MOE150
description: Hier erfahren Sie, wie Sie Richtlinien zur Verhinderung von Datenverlusten verwalten.
ms.openlocfilehash: 93c06af0203a5eb590d22d86e597d7485d7af238
ms.sourcegitcommit: f231eece2927f0d01072fd092db1eab15525bbc2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/17/2020
ms.locfileid: "49702244"
---
# <a name="prevent-data-loss-with-dlp"></a>Verhindern von Datenverlust mit DLP

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3TGvL?autoplay=false]

Policies zur Verhinderung von Datenverlusten helfen beim identifizieren und Schützen vertraulicher Informationen Ihres Unternehmens wie Sozialversicherungsnummern oder medizinischen Datensätzen. 

## <a name="try-it"></a>Probieren Sie es aus!

1. Um zu beginnen, wechseln Sie zum [Admin Center](https://admin.microsoft.com), und wählen Sie **Setup** aus.
1. Scrollen Sie nach unten, um die **Verhinderung von Datenverlust einzurichten**, und wählen Sie dann **anzeigen** und dann **Verwalten** aus.
1. Zum Bearbeiten einer Richtlinie wählen Sie Sie aus, wählen Sie **Richtlinie bearbeiten** aus, und wählen Sie dann zu ändernde Elemente aus. Wählen Sie beispielsweise **Orte** aus, um zu ändern, was gescannt wird.
1. Um die Überprüfung auf Inhalte in Microsoft Teams zu aktivieren, aktivieren Sie die Umschaltfläche in die Position **ein** , und wählen Sie dann **Speichern** aus.
1. Wählen Sie zum Bearbeiten von Richtlinieneinstellungen die Option **Bearbeiten** aus.
1. Sie müssen separate Regeln festlegen, die auf kleine und große Mengen vertraulicher Inhalte angewendet werden, die erkannt wurden. Erweitern Sie die Regel für geringes Volumen. Klicken Sie auf **Regel bearbeiten**.
1. Überprüfen Sie Ihre Einstellungen, und passen Sie Sie bei Bedarf an. Sie können beispielsweise festlegen, dass **der e-Mail-Text angepasst** und **der richtlinientipp Text angepasst** werden soll. Klicken Sie auf **Speichern**.
1. Wiederholen Sie diese Schritte für die Regel für hohe Lautstärke. Klicken Sie auf **Speichern** und dann auf **Schließen**.
1. Wählen Sie zum Erstellen einer neuen Richtlinie **Richtlinie erstellen** aus.
1. Sie können eine benutzerdefinierte Richtlinie erstellen oder mit einer Vorlage beginnen. Um beispielsweise eine HIPAA-Richtlinie zu erstellen, wählen Sie die Vorlage **Medizin und Integrität** aus, und wählen Sie dann **US-Krankenversicherungsgesetz (HIPAA)** aus. Wählen Sie **Weiter** aus.
1. Geben Sie einen Namen und eine Beschreibung für Ihre Richtlinie ein. Wählen Sie **Weiter** aus.
1. Wählen Sie die zu überprüfenden Speicherorte aus. Wählen Sie **Weiter** aus.
1. Wählen Sie den Inhaltstyp aus, den Sie schützen möchten. Wählen Sie **Weiter** aus.
1. Wählen Sie aus, was geschehen soll, wenn vertrauliche Informationen erkannt werden. Wählen Sie **Weiter** aus.
1. Passen Sie Ihre Zugriffs-und Außerkraftsetzungs Berechtigungen an. Wählen Sie **Weiter** aus.
1. Wählen Sie aus, wann die Richtlinie wirksam werden soll. Wählen Sie **Weiter** aus.
1. Überprüfen Sie Ihre Einstellungen, und wählen Sie **Erstellen** aus. Nachdem Ihre Richtlinie wirksam wurde, werden e-Mails, die die beschriebenen vertraulichen Informationen enthalten, blockiert, und der Absender, der versucht hat, diese Informationen zu senden, wird eine Warnmeldung angezeigt.