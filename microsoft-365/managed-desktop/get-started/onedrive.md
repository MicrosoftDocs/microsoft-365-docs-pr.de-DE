---
title: Microsoft OneDrive
description: So richtet Microsoft Managed Desktop OneDrive für registrierte Geräte ein
keywords: Microsoft Managed Desktop, Microsoft 365, Dienst, Dokumentation, Apps, Branchen-Apps
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 6cd2c993e0ca9d4c456a2914b866b65b59799afa
ms.sourcegitcommit: a62ac3c01ba700a51b78a647e2301f27ac437c5a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/12/2021
ms.locfileid: "50233921"
---
# <a name="microsoft-onedrive"></a>Microsoft OneDrive

Microsoft Managed Desktop verwendet [OneDrive for Business](https://docs.microsoft.com/onedrive/plan-onedrive-enterprise) als Cloudspeicherdienst für alle Microsoft Managed Desktop-Geräte, um sicherzustellen, dass die Geräte so statuslos wie möglich sind. Der Benutzer kann seine Dateien suchen, unabhängig davon, auf welchem Gerät er sich anmeldet. Wenn Sie beispielsweise ein Microsoft Managed Desktop-Gerät durch ein neues ersetzen, werden Dateien automatisch mit dem neuen Gerät synchronisiert.

Diese Einstellungen werden auf verwalteten Geräten von Microsoft standardmäßig automatisch konfiguriert:

- OneDrive wird automatisch mit dem Benutzerkonto konfiguriert und automatisch (ohne Benutzerinteraktion) beim Benutzerkonto angemeldet, das für die Anmeldung bei Windows verwendet wurde. Weitere Informationen finden Sie unter ["Automatisches Konfigurieren von Benutzerkonten - OneDrive"](https://docs.microsoft.com/onedrive/use-silent-account-configuration)

- Das Feature "Dateien bei Bedarf" ist aktiviert, sodass Benutzer über ihren Cloudspeicher in OneDrive auf Dateien zugreifen können, ohne unnötig Speicherplatz auf dem Datenträger nutzen zu müssen. Weitere Informationen finden Sie unter ["Speichern von Speicherplatz mit #A0 bei Bedarf für Windows 10".](https://support.microsoft.com/office/save-disk-space-with-onedrive-files-on-demand-for-windows-10-0e6860d3-d9f3-4971-b321-7092438fb38e)

- Das Feature "Verschieben bekannter Ordner" wird automatisch aktiviert, um die Daten von Benutzern in der Cloud zu sichern, wodurch sie von jedem Gerät aus auf ihre Dateien zugreifen können. Weitere Informationen finden Sie unter Sichern Ihrer Dokumente, Bilder und [Desktopordner mit OneDrive](https://support.microsoft.com/office/back-up-your-documents-pictures-and-desktop-folders-with-onedrive-d61a7930-a6fb-4b95-b28a-6552e77c3057).

- Benutzer können das Feature zum Verschieben bekannter Ordner nicht deaktivieren oder den Speicherort bekannter Ordner ändern, um eine konsistente Benutzererfahrung auf allen Microsoft Managed Desktop-Geräten zu gewährleisten.

## <a name="user-experience"></a>Verwendung durch den Benutzer

Wenn Microsoft Managed Desktop-Benutzer ein neues Gerät erhalten, werden sie bei der ersten Ausführung durch die Eingabe ihrer Azure-Anmeldeinformationen beim Einrichten des Geräts geführt. Nachdem dieser Prozess abgeschlossen ist, können sie auf ihren Desktop zugreifen und die #A0 verwenden.

1. Das System teilt Benutzern mit, dass OneDrive konfiguriert wurde und dass sie automatisch bei OneDrive angemeldet wurden.

:::image type="content" source="media/onedrive-sync.png" alt-text="Benachrichtigungen, die Sie jetzt synchronisieren, und Sie können Dateien in OneDrive bearbeiten. Klicken Sie hier, um Ihre Dateien anzeigen zu können.":::

2. Das System teilt den Benutzern mit, dass das Verschieben bekannter Ordner in OneDrive für sie konfiguriert wurde.

:::image type="content" source="media/onedrive-folders.png" alt-text="Ihre IT-Abteilung hat Ihre wichtigen Ordner mit einer Benachrichtigung gesichert. Die Ordner werden jetzt auf OneDrive gesichert und sind auf anderen Geräten verfügbar.":::

3. Um doppelte Symbole auf dem Desktop zu verhindern, wenn Geräte zurückgesetzt oder erneut aktualisiert werden, entfernt das System automatisch Microsoft Edge- und Microsoft #A0 aus der OneDrive-Synchronisierung, wie in dieser Ansicht im #A1 dargestellt.

:::image type="content" source="media/onedrive-teams.png" alt-text="Der Datei-Explorer zeigt Teams- und Edgeauflistungen mit aus der Synchronisierung ausgeschlossenen Kontrollkästchen und Hovertext aus.":::


## <a name="onedrive-sync-restrictions"></a>#A0

Wenn Sie die #A0 einschränken müssen, empfehlen wir, den Zugriff mit einer Azure Active #A1 für bedingten Zugriff zu steuern. Weitere Informationen finden Sie unter Aktivieren der Unterstützung für [bedingten Zugriff in der OneDrive-Synchronisierungs-App.](https://docs.microsoft.com/onedrive/enable-conditional-access)

Wenn Sie keine Azure AD-Richtlinie für bedingten Zugriff in Ihrer Organisation verwenden können, sollte Ihr IT-Administrator die folgenden Schritte ausführen:

1. Wenn Sie sie noch nicht kennen, suchen Sie Nachschau nach Ihrer Mandanten-ID, wie unter ["Suchen Ihrer Microsoft 365-Mandanten-ID" beschrieben.](https://docs.microsoft.com/onedrive/find-your-office-365-tenant-id)
2. Melden Sie sich beim OneDrive Admin Center an, und wählen Sie dann im linken Bereich **"Synchronisieren"** aus. Aktivieren Sie **das Kontrollkästchen** Synchronisierung nur auf PCs zulassen, die mit bestimmten Domänen verbunden sind, und fügen Sie dann die Mandanten-ID zur Liste der Domänen hinzu. Weitere Informationen finden Sie unter ["Synchronisierung zulassen" nur auf Computern, die mit bestimmten Domänen verbunden sind.](https://docs.microsoft.com/onedrive/allow-syncing-only-on-specific-domains)

> [!NOTE]
> Dieser Leitfaden gilt nur für Mandanten in Microsoft Managed Desktop. Es werden weitere Einstellungen verwendet, die in diesem Artikel nicht behandelt werden.
