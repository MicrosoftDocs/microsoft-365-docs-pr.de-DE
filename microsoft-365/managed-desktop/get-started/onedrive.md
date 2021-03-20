---
title: Microsoft OneDrive
description: Einrichten von OneDrive für registrierte Geräte durch Microsoft Managed Desktop
keywords: Microsoft Managed Desktop, Microsoft 365, Dienst, Dokumentation, Apps, Branchen-Apps, Branchen-Apps
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: a26500c1671afffc7b70d509a4242914631b937c
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50904840"
---
# <a name="microsoft-onedrive"></a>Microsoft OneDrive

Microsoft Managed Desktop verwendet [OneDrive for Business](/onedrive/plan-onedrive-enterprise) als Cloudspeicherdienst für alle Microsoft Managed Desktop-Geräte, um sicherzustellen, dass die Geräte so zustandslos wie möglich sind. Der Benutzer kann seine Dateien unabhängig davon finden, bei welchem Gerät er sich anmeldet. Wenn Sie beispielsweise ein Microsoft Managed Desktop-Gerät durch ein neues ersetzen, werden Dateien automatisch mit dem neuen Gerät synchronisiert.

Diese Einstellungen werden auf verwalteten Microsoft-Geräten standardmäßig automatisch konfiguriert:

- OneDrive wird im Hintergrund mit dem Benutzerkonto konfiguriert und automatisch (ohne Benutzerinteraktion) beim Benutzerkonto angemeldet, das für die Anmeldung bei Windows verwendet wurde. Weitere Informationen finden Sie unter [Automatisches Konfigurieren von Benutzerkonten – OneDrive](/onedrive/use-silent-account-configuration)

- Das Feature Files-On-Demand ist aktiviert, sodass Benutzer über ihren Cloudspeicher in OneDrive auf Dateien zugreifen können, ohne unnötig Speicherplatz verwenden zu müssen. Weitere Informationen finden Sie [unter Save disk space with OneDrive Files On-Demand for Windows 10](https://support.microsoft.com/office/save-disk-space-with-onedrive-files-on-demand-for-windows-10-0e6860d3-d9f3-4971-b321-7092438fb38e).

- Das Feature "Verschieben bekannter Ordner" wird automatisch aktiviert, um die Daten von Benutzern in der Cloud zu sichern, wodurch sie von jedem Gerät aus Zugriff auf ihre Dateien erhalten. Weitere Informationen finden Sie unter Sichern Ihrer Ordner ["Dokumente", "Bilder" und "Desktop" mit OneDrive](https://support.microsoft.com/office/back-up-your-documents-pictures-and-desktop-folders-with-onedrive-d61a7930-a6fb-4b95-b28a-6552e77c3057).

- Benutzer können das Feature "Verschieben bekannter Ordner" nicht deaktivieren oder den Speicherort bekannter Ordner ändern, um eine einheitliche Benutzererfahrung auf Microsoft Managed Desktop-Geräten sicherzustellen.

## <a name="user-experience"></a>Verwendung durch den Benutzer

Wenn Microsoft Managed Desktop-Benutzer ein neues Gerät erhalten, können sie beim Einrichten des Geräts ihre Azure-Anmeldeinformationen eingeben. Nachdem dieser Prozess abgeschlossen ist, können sie auf ihren Desktop zugreifen und die #A0 verwenden.

1. Das System teilt Benutzern mit, dass OneDrive konfiguriert wurde und dass sie automatisch bei OneDrive angemeldet wurden.

:::image type="content" source="media/onedrive-sync.png" alt-text="Benachrichtigungen, die Sie jetzt oneDrive synchronisieren, und Sie können Dateien in OneDrive bearbeiten. Klicken Sie hier, um Ihre Dateien zu sehen":::

2. Das System teilt Den Benutzern mit, dass die #A0 für sie konfiguriert wurde.

:::image type="content" source="media/onedrive-folders.png" alt-text="Benachrichtigungsleseanzeige Ihre IT-Abteilung hat Ihre wichtigen Ordner gesichert. Die Ordner werden jetzt auf OneDrive gesichert und von anderen Geräten verfügbar":::

3. Um zu verhindern, dass doppelte Symbole auf dem Desktop beim Zurücksetzen oder Erneutbilden von Geräten vorhanden sind, entfernt das System automatisch Microsoft Edge- und Microsoft #A0 aus der OneDrive-Synchronisierung, wie in dieser Ansicht im Datei-Explorer dargestellt.

:::image type="content" source="media/onedrive-teams.png" alt-text="Datei-Explorer mit Teams- und Edgeauflistungen mit ausgecheckten Kontrollkästchen und Hovertextlesung Ausgeschlossen von der Synchronisierung.":::


## <a name="onedrive-sync-restrictions"></a>OneDrive-Synchronisierungseinschränkungen

Wenn Sie die #A0 einschränken müssen, wird empfohlen, den Zugriff mit einer Azure Active Directory-Richtlinie für bedingten Zugriff zu steuern. Weitere Informationen finden Sie unter Aktivieren der Unterstützung [für bedingten Zugriff in der OneDrive-Synchronisierungs-App.](/onedrive/enable-conditional-access)

Wenn Sie keine Azure AD-Richtlinie für bedingten Zugriff in Ihrer Organisation verwenden können, sollte Ihr IT-Administrator die folgenden Schritte ausführen:

1. Wenn Sie dies noch nicht wissen, suchen Sie nach Ihrer Mandanten-ID, wie unter [Suchen Ihrer Microsoft 365-Mandanten-ID beschrieben.](/onedrive/find-your-office-365-tenant-id)
2. Melden Sie sich beim OneDrive Admin Center an, und wählen Sie dann **Synchronisierung im** linken Bereich aus. Aktivieren Sie **das Kontrollkästchen** Synchronisierung nur auf PCs zulassen, die bestimmten Domänen zugeordnet sind, und fügen Sie dann die Mandanten-ID der Liste der Domänen hinzu. Weitere Informationen finden Sie unter [Allow syncing only on computers joined to specific domains](/onedrive/allow-syncing-only-on-specific-domains).

> [!NOTE]
> Diese Anleitung gilt nur für Mandanten in Microsoft Managed Desktop. Es werden weitere Einstellungen verwendet, die in diesem Artikel nicht behandelt werden.