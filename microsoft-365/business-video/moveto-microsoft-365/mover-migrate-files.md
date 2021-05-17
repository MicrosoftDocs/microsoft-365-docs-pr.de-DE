---
title: 'Migrieren von Google-Dateien zu Microsoft 365 Business '
f1.keywords:
- NOCSH
ms.author: twerner
author: twernermsft
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
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
description: Erfahren Sie, wie Sie Google-Dateien mithilfe von Mover Microsoft 365 Unternehmens migrieren.
ms.openlocfilehash: 6feabff7e36e84f7dba56e74333648325cf43920
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50913574"
---
# <a name="migrate-google-files-to-microsoft-365-for-business"></a>Migrieren von Google-Dateien zu Microsoft 365 Business 

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4MhaD?autoplay=false]

Wenn Sie zu Microsoft 365 business wechseln, sollten Sie Ihre Dateien aus dem Google Drive. Sie können die Mover-App verwenden, um Dateien von persönlichen und freigegebenen Laufwerken zu verschieben. Weitere Informationen finden Sie unter [Mover Cloud Migration](/sharepointmigration/mover-plan-migration).

> [!NOTE]
> Mover erstellt eine Kopie der Dateien und verschiebt die Kopien in Microsoft 365 Unternehmen. Die originalen Dateien bleiben auch in Google Drives erhalten.

## <a name="before-you-start"></a>Vorbereitende Schritte

Alle Benutzer sollten sich bei Microsoft 365 angemeldet und ihre OneDrive for Business. Wechseln Sie dazu zu [office.com](https://office.com), melden Sie sich mit Microsoft 365 für Geschäftsanmeldeinformationen an, und wählen Sie dann OneDrive.

## <a name="try-it"></a>Probieren Sie es aus!

### <a name="install-mover"></a>Installieren von Mover

1. Melden Sie sich bei Ihrer Google Workspace Admin Console unter [admin.google.com.](https://admin.google.com)

1. Wählen **Sie Apps** Google Workspace Marketplace  >  **apps** App zu  >  **Domäneninstallationsliste hinzufügen aus.**

1. Suchen Sie nach Mover, und wählen Sie ihn aus.

1. Wählen **Sie Domäneninstallation** aus, und fahren Sie **dann fort.**

1. Überprüfen Sie die Berechtigungen, aktivieren Sie das Kontrollkästchen, um den Bedingungen zu zustimmen, und wählen Sie **Dann Zulassen** aus, wählen Sie **Weiter** und dann **Fertig aus.**

### <a name="create-connectors-and-run-the-migration"></a>Erstellen von Connectors und Ausführen der Migration

1. Kehren Sie zu **Google Workspace Marketplace-Apps zurück.**
1. Aktualisieren Sie Ihren Browser, und wählen Sie die **Mover-App** aus.
1. Scrollen Sie nach unten, und wählen Sie den universellen Navigationslink aus.
1. Wählen **Sie Neuen Connector autorisieren,** G Suite **(Admin)** suchen und **Autorisieren aus.**
1. Ändern Sie **den Anzeigenamen**, wenn Sie möchten, und wählen Sie **Dann Autorisieren aus.**
1. Wählen Sie ein Google-Administratorkonto aus, überprüfen Sie die Berechtigungen, und wählen Sie dann **Zulassen aus.**

    Mover zeigt die Anzahl der gefundenen Teamlaufwerke und Benutzerlaufwerke an. 

1. Wählen **Sie unter Ziel auswählen** die Option Neuen Connector **autorisieren** aus, **suchen Office 365**, und wählen Sie **Autorisieren aus.**
1. Zum Erteilen von Berechtigungen für die Mover-App in Azure Active Directory Navigieren Sie zu [aka.ms/Office365MoverAuth](https://aka.ms/Office365MoverAuth).
1. Wählen **Office 365 Mover**, **Permissions**, Erteilen **der Administratorzusendung für Ihr Unternehmen aus.**
1. Wählen Sie Ihr Konto aus, überprüfen Sie die Berechtigungen, und wählen Sie **Akzeptieren aus.**
1. Wählen **Sie Eigenschaften** aus, und vergewissern Sie sich, dass die **Benutzerzuweisung erforderlich ist?** aktiviert ist.
1. Kehren Sie zur Mover-App zurück, ändern Sie den **Anzeigenamen**, wenn Sie möchten, wählen Sie **Autorisieren** aus, und wählen Sie dann ein Microsoft-Administratorkonto aus.

    Mover informiert Sie über die Anzahl der SharePoint (oder SPO)-Websites und -Benutzer.
1. Wählen **Sie Setup für die Migration fortsetzen** aus, wählen Sie Benutzer **hinzufügen** und dann Benutzer automatisch ermitteln und **hinzufügen aus.**

    Die Mover-App versucht, Laufwerke vom Quellpfad in Google dem Zielpfad in Microsoft 365. 

    Wenn ein Laufwerk nicht automatisch zuordnung wird, fügen Sie seinen Zielpfad zu einer CSV-Datei hinzu, die wir später zum Migrieren des freigegebenen Laufwerks zu einer SharePoint verwenden. 

1. In diesem Fall haben wir eine SharePoint migrierte Dateien hinzugefügt und die URL für die Dokumentseite zur Kenntnis genommen. 
1. Anschließend haben wir eine CSV-Datei mit dem Format Source Path, Destination Path und Tags erstellt. 

    Weitere Informationen finden Sie [unter aka.ms/movercsv](/sharepointmigration/mover-create-migration-csv).

    Entfernen Sie beim Hinzufügen der Zielpfad-URL alles nach freigegebenen Dokumenten. Diese vollständige URL funktioniert beispielsweise nicht: `https://TENANT01.sharepoint.com/sites/SiteName/Shared Documents/Forms/AllItems.aspx`

    Ändern Sie sie zu `https://TENANT01.sharepoint.com/sites/SiteName/Shared Documents`

1. Sobald Ihre CSV-Datei bereit ist, wählen Sie **Migrationsaktionen**, **Migration hinzufügen**, Datei zum Hochladen **auswählen aus.**
1. Navigieren Sie zu Ihrer CSV-Datei, wählen Sie sie aus, und wählen Sie dann **Öffnen aus.**
1. Wählen Sie die Benutzerlaufwerke aus, deren Dateien Sie migrieren möchten, und wählen Sie **dann Migrieren von Benutzern starten aus.**
1. Überprüfen Sie die Migrationsinformationen, wählen Sie aus, wann die Migration gestartet werden soll, stimmen Sie den **Allgemeinen** Geschäftsbedingungen zu und wählen Sie dann **Weiter aus.**

Die Mover-App informiert Sie, wenn der Migrationsprozess abgeschlossen ist.