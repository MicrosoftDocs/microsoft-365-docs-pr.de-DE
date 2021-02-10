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
description: Erfahren Sie, wie Sie Mithilfe von Mover Google-Dateien zu Microsoft 365 Business migrieren.
ms.openlocfilehash: 72ea81ad86a20e01b4650915fef96a713b207c3b
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/09/2021
ms.locfileid: "50166159"
---
# <a name="migrate-google-files-to-microsoft-365-for-business"></a>Migrieren von Google-Dateien zu Microsoft 365 Business 

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4MhaD?autoplay=false]

Wenn Sie zu Microsoft 365 Business wechseln, sollten Sie Ihre Dateien von Google Drive migrieren. Sie können die Mover-App verwenden, um Dateien von persönlichen und freigegebenen Laufwerken zu verschieben. Weitere Informationen finden Sie unter [Mover Cloud Migration](https://docs.microsoft.com/sharepointmigration/mover-plan-migration).

> [!NOTE]
> Mover erstellt eine Kopie der Dateien und verschiebt die Kopien nach Microsoft 365 Business. Die originalen Dateien bleiben auch in Google Drives.

## <a name="before-you-start"></a>Vor der Bereitstellung

Alle Benutzer sollten sich bei Microsoft 365 Business angemeldet und ihr OneDrive for Business eingerichtet haben. Wechseln Sie dazu zu [office.com](https://office.com), melden Sie sich mit Ihren Microsoft 365 #A0 an, und wählen Sie dann OneDrive aus.

## <a name="try-it"></a>Probieren Sie es aus!

### <a name="install-mover"></a>Installieren von Mover

1. Melden Sie sich bei Ihrer Google Workspace-Verwaltungskonsole [unter admin.google.com](https://admin.google.com).

1. Choose **Apps**  >  **Google Workspace Marketplace apps** Add app to Domain Install  >  **list**.

1. Suchen Sie nach Mover, und wählen Sie ihn aus.

1. Choose **Domain Install**, then **Continue**.

1. Überprüfen Sie die Berechtigungen, aktivieren Sie das Kontrollkästchen, um den Bedingungen zu zustimmen, und wählen Sie dann **"Zulassen",** **"Weiter"** und dann "Fertig" **aus.**

### <a name="create-connectors-and-run-the-migration"></a>Erstellen von Connectors und Ausführen der Migration

1. Zurück zu **Google Workspace Marketplace-Apps.**
1. Aktualisieren Sie Ihren Browser, und wählen Sie die **Mover-App** aus.
1. Scrollen Sie nach unten, und wählen Sie den universellen Navigationslink aus.
1. Wählen **Sie "Neuen Connector autorisieren",** suchen **Sie nach G Suite (Administrator)** und wählen Sie **"Autorisieren" aus.**
1. Ändern Sie **den Anzeigenamen,** wenn Sie möchten, und wählen Sie **"Autorisieren" aus.**
1. Wählen Sie ein Google-Administratorkonto aus, überprüfen Sie die Berechtigungen, und wählen Sie dann **"Zulassen" aus.**

    Mover zeigt die Anzahl der ermittelten Teamlaufwerke und Benutzerlaufwerke an. 

1. Wählen **Sie unter Ziel auswählen** die Option **"Neuen Connector autorisieren"** aus, suchen Sie nach Office **365,** und wählen Sie **"Autorisieren" aus.**
1. Um der Mover-App in Ihrem Azure Active Directory Berechtigungen zu erteilen, navigieren Sie zu [aka.ms/Office365MoverAuth](https://aka.ms/Office365MoverAuth).
1. Wählen **Sie Office 365 Mover**, **Berechtigungen**, **Administratorzuwilligung für Ihr Unternehmen erteilen.**
1. Wählen Sie Ihr Konto aus, überprüfen Sie die Berechtigungen, und wählen Sie **"Annehmen" aus.**
1. Choose **Properties** and verify that **User assignment required?** is turned on.
1. Kehren Sie zur Mover-App zurück, ändern Sie den **Anzeigenamen,** wenn Sie möchten, wählen Sie **"Autorisieren"** aus, und wählen Sie dann ein Microsoft-Administratorkonto aus.

    Mover informiert Sie über die Anzahl von SharePoint Online-Websites (oder SPO)-Websites und -Benutzern, die ermittelt wurden.
1. Choose **Continue Migration Setup**, select Add **Users**, then Automatically Discover and **Add Users**.

    Die Mover-App versucht, Laufwerke aus dem Quellpfad in Google dem Zielpfad in Microsoft 365 zu zuordnungen. 

    Wenn ein Laufwerk nicht automatisch zuordnungiert wird, fügen Sie seinen Zielpfad zu einer CSV-Datei hinzu, die wir später zum Migrieren des freigegebenen Laufwerks zu einer SharePoint-Dokumentbibliothek verwenden. 

1. In diesem Fall haben wir eine SharePoint-Website namens "Migrierte Dateien" hinzugefügt und die URL für die Dokumentseite notiert. 
1. Anschließend haben wir eine CSV-Datei mit dem Format "Quellpfad", "Zielpfad" und "Tags" erstellt. 

    Weitere Informationen finden Sie [unter aka.ms/movercsv](https://docs.microsoft.com/sharepointmigration/mover-create-migration-csv).

    Entfernen Sie beim Hinzufügen der Zielpfad-URL alles nach freigegebenen Dokumenten. Diese vollständige URL funktioniert beispielsweise nicht: `https://TENANT01.sharepoint.com/sites/SiteName/Shared Documents/Forms/AllItems.aspx`

    Ändern Sie sie zu `https://TENANT01.sharepoint.com/sites/SiteName/Shared Documents`

1. Sobald Ihre CSV-Datei bereit ist, wählen **Sie "Migrationsaktionen",** **"Zur Migration** hinzufügen" und **"Datei zum Hochladen" aus.**
1. Navigieren Sie zu Ihrer CSV-Datei, wählen Sie sie aus, und wählen Sie dann **Öffnen aus.**
1. Wählen Sie die Benutzerlaufwerke aus, deren Dateien Sie migrieren möchten, und wählen Sie dann **"Migration von Benutzern starten" aus.**
1. Überprüfen Sie die Migrationsinformationen, wählen Sie den Start der Migration aus, stimmen Sie den Allgemeinen Geschäftsbedingungen **zu,** und wählen Sie dann **"Weiter" aus.**

Die Mover-App informiert Sie, wenn der Migrationsprozess abgeschlossen ist.
