---
title: Laden nicht Office 365er Daten in Beweise
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
ms.openlocfilehash: ee1e6f8a064567126d75b099cc3003e8a4d6a020
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/20/2019
ms.locfileid: "37081635"
---
# <a name="load-non-office-365-data-into-evidence"></a>Laden nicht Office 365er Daten in Beweise

Nicht alle Dokumente, die Sie möglicherweise mit Office 365 Advanced eDiscovery analysieren müssen, werden in Office 365 Live verwendet. Mit der nicht Office 365den Funktion zum Importieren von Inhalten in Advanced eDiscovery können Sie Dokumente, die nicht in Office 365 Leben, in einen Arbeitsumfang hochladen, sodass Sie mit Advanced eDiscovery analysiert werden. In diesem Verfahren erfahren Sie, wie Sie Ihre nicht-Office 365-Dokumente zur Analyse in Advanced eDiscovery integrieren.

>[!Note]
>Advanced eDiscovery erfordert eine Office 365 E3 mit dem Advanced Compliance-Add-on oder ein E5-Abonnement für Ihre Organisation. Wenn Sie diesen Plan nicht haben und Advanced eDiscovery testen möchten, können Sie sich für eine Testversion von Office 365 Enterprise E5 anmelden.

## <a name="before-you-begin"></a>Bevor Sie beginnen
Wenn Sie das Feature nicht Office 365 hochladen wie in diesem Verfahren beschrieben verwenden, benötigen Sie Folgendes:

- Ein Office 365 E3 mit Advanced Compliance-Add-on oder E5-Abonnement.

- Alle Verwalter, deren nicht Office 365 Inhalt hochgeladen wird, müssen über E3 mit Advanced Compliance Add-on oder E5-Lizenzen verfügen.

- Ein vorhandener eDiscovery-Fall.

- Alle Dateien für das Hochladen wurden in Ordner gesammelt, in denen ein Ordner pro Depotbank vorhanden ist, und der Name des Ordners ist in diesem Format *Alias @ Domain* Name. *Bei dem Alias @ Domain Name* muss es sich um Benutzer Office 365 Alias und Domäne handeln. Sie können alle Alias- *@ Domain Name* -Ordner in einem Stammordner sammeln. Der Stammordner darf nur die Ordner *Alias @ Domain Name* enthalten, es dürfen keine losen Dateien im Stammordner vorhanden sein.

- Ein Konto, bei dem es sich um einen eDiscovery-Manager oder eDiscovery-Administrator handelt Microsoft Azure Speicher Tools, die auf einem Computer installiert sind, der Zugriff auf die nicht Office 365 Inhaltsordner Struktur hat.

- Installieren Sie AzCopy, was Sie von hier aus tun können:https://docs.microsoft.com/en-us/azure/storage/common/storage-use-azcopy

## <a name="upload-non-office-365-content-into-advanced-ediscovery"></a>Hochladen nicht Office 365er Inhalte in die erweiterte eDiscovery

1. Öffnen Sie als eDiscovery-Manager oder eDiscovery-Administrator Advanced eDiscovery, dann werden die nicht Office 365-Daten hochgeladen.  Klicken Sie auf die Registerkarte **Arbeitsmappen** , und wählen Sie dann den Arbeitssatz aus, in den Sie die nicht Office 365 Daten laden möchten.  Wenn Sie noch keine Arbeitsmappe erstellt haben, können Sie dies jetzt tun.  Klicken Sie schließlich auf " **Arbeitsaufgaben verwalten** " und dann auf " **Uploads** " im Abschnitt "nicht Office 365 Daten" anzeigen

2. Klicken Sie auf die Schaltfläche **Dateien hochladen** , um den nicht Office 365 Datenimport-Assistenten zu starten.

![Hochladen von Dateien](media/574f4059-4146-4058-9df3-ec97cf28d7c7.png)

3. Im ersten Schritt des Assistenten wird einfach ein sicheres Azure-BLOB für die zu hochzuladenden Dateien vorbereitet.  Wenn die Vorbereitung compelted ist, klicken Sie auf die Schaltfläche **Weiter: Dateien hochladen** .

![Nicht Office 365 Import – Prepare](media/0670a347-a578-454a-9b3d-e70ef47aec57.png)
 
4. Geben Sie im Schritt **Upload Files** den **Pfad zum Speicherort der Dateien**an, hier befinden sich die nicht Office 365 Daten, die Sie beim Import planen.  Durch Festlegen des richtigen Speicherorts wird sichergestellt, dass der AzCopy-Befehl ordnungsgemäß aktualisiert wird.

> [!NOTE]
> Wenn Sie AzCopy nicht bereits installiert haben, können Sie dies hier tun:https://docs.microsoft.com/en-us/azure/storage/common/storage-use-azcopy

5. Kopieren Sie den vordefinierten Befehl, indem Sie auf den Link **in Zwischenablage kopieren** klicken. Starten Sie eine Windows-Eingabeaufforderung, fügen Sie den Befehl ein, und drücken Sie die EINGABETASTE.  Die Dateien werden in den sicheren Azure-BLOB-Speicher für den nächsten Schritt hochgeladen.

![Nicht Office 365 Import-Upload-Dateien](media/3ea53b5d-7f9b-4dfc-ba63-90a38c14d41a.png)

![Nicht Office 365 Import – AzCopy](media/504e2dbe-f36f-4f36-9b08-04aea85d8250.png)

6. Kehren Sie schließlich zur Sicherheits #a0 Compliance zurück, und klicken Sie auf die Schaltfläche **Weiter: Prozessdateien** .  Dadurch wird die Verarbeitung, die Textextraktion und die Indizierung der hochgeladenen Dateien initiiert.  Sie können den Fortschritt der Verarbeitung hier oder auf der Registerkarte **Aufträge** nachverfolgen.  Sobald der Vorgang abgeschlossen ist, sind die neuen Dateien im Arbeitspaket verfügbar.  Nachdem die Verarbeitung abgeschlossen ist, können Sie den Assistenten schließen.

![Nicht Office 365 Import Prozess-Dateien](media/218b1545-416a-4a9f-9b25-3b70e8508f67.png)

