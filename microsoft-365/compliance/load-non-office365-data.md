---
title: Laden nicht Office 365er Daten in Beweise
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
ms.openlocfilehash: 3be5e4054e34cabb61505d48524feb2dbbfd0e44
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2020
ms.locfileid: "41600572"
---
# <a name="load-non-office-365-data-into-evidence"></a>Laden nicht Office 365er Daten in Beweise

Nicht alle Dokumente, die Sie möglicherweise in einer Datenuntersuchung analysieren müssen, befinden sich in Office 365. Mit der nicht Office 365en Funktion zum Importieren von Inhalten können Sie Dokumente, die nicht in Office 365 Leben, in Beweise hochladen, damit Sie in einer Datenuntersuchung analysiert werden können.

>[!Note]
>Für die Untersuchung von Daten ist ein Office 365 E3 mit dem Advanced Compliance-Add-on oder einem E5-Abonnement für Ihre Organisation erforderlich. Wenn Sie diesen Plan nicht haben und Advanced eDiscovery testen möchten, können Sie sich für eine Testversion von Office 365 Enterprise E5 anmelden.

## <a name="before-you-begin"></a>Bevor Sie beginnen:

Wenn Sie das Feature nicht Office 365 hochladen wie in diesem Verfahren beschrieben verwenden, benötigen Sie Folgendes:

- Ein Office 365 E3 mit Advanced Compliance-Add-on oder E5-Abonnement.

- Alle Verwalter, deren nicht Office 365 Inhalt hochgeladen wird, müssen über E3 mit Advanced Compliance Add-on oder E5-Lizenzen verfügen.

- Ein vorhandener eDiscovery-Fall.

- Alle Dateien für das Hochladen wurden in Ordner gesammelt, in denen pro Depot ein Ordner vorhanden ist und der Name des Ordners in diesem Format *Alias@Domainname*. Die *Alias@Domainname* müssen Benutzer Office 365 Alias und Domäne sein. Sie können alle *Alias@Domainname* Ordner in einem Stammordner sammeln. Der Stammordner kann nur die *Alias@Domainname* Ordner enthalten, es dürfen keine losen Dateien im Stammordner vorhanden sein.

- Ein Konto, bei dem es sich um einen eDiscovery-Manager oder eDiscovery-Administrator handelt Microsoft Azure Speicher Tools, die auf einem Computer installiert sind, der Zugriff auf die nicht Office 365 Inhaltsordner Struktur hat.

- Installieren Sie AzCopy, was Sie von hier aus tun können:https://docs.microsoft.com/azure/storage/common/storage-use-azcopy

## <a name="upload-non-office-365-content-in-to-a-data-investigation"></a>Hochladen nicht Office 365er Inhalte in eine Datenuntersuchung

1. Open * * * * Data Investigations * *, dann die Untersuchung, in die die nicht Office 365 Daten hochgeladen werden.  Klicken Sie auf die Registerkarte **Beweise** , und wählen Sie dann den Beweissatz aus, in den Sie die nicht Office 365 Daten laden möchten.  Wenn Sie noch keinen Beweis Sätze erstellt haben, können Sie dies jetzt tun.  Klicken Sie schließlich auf **Beweise verwalten** , und zeigen Sie dann **Uploads** im Abschnitt nicht Office 365 Daten an.

2. Klicken Sie auf die Schaltfläche **Dateien hochladen** , um den nicht Office 365 Datenimport-Assistenten zu starten.

![Dateien hochladen](media/574f4059-4146-4058-9df3-ec97cf28d7c7.png)

3. Im ersten Schritt des Assistenten wird einfach ein sicheres Azure-BLOB für die zu hochzuladenden Dateien vorbereitet.  Klicken Sie nach Abschluss der Vorbereitung auf die Schaltfläche **Weiter: Dateien hochladen** .

![Vorbereiten des Datenimports ohne Office 365](media/0670a347-a578-454a-9b3d-e70ef47aec57.png)
 
4. Geben Sie im Schritt **Upload Files** den **Pfad zum Speicherort der Dateien**an, hier befinden sich die nicht Office 365 Daten, die Sie beim Import planen.  Durch Festlegen des richtigen Speicherorts wird sichergestellt, dass der AzCopy-Befehl ordnungsgemäß aktualisiert wird.

> [!NOTE]
> Wenn Sie AzCopy nicht bereits installiert haben, können Sie dies hier tun:https://docs.microsoft.com/azure/storage/common/storage-use-azcopy

5. Kopieren Sie den vordefinierten Befehl, indem Sie auf den Link **in Zwischenablage kopieren** klicken. Starten Sie eine Windows-Eingabeaufforderung, fügen Sie den Befehl ein, und drücken Sie die EINGABETASTE.  Die Dateien werden in den sicheren Azure-BLOB-Speicher für den nächsten Schritt hochgeladen.

![Hochladen von Dateien für nicht Office 365 Datenimport](media/3ea53b5d-7f9b-4dfc-ba63-90a38c14d41a.png)

![Verwenden von AzCopy zum Importieren nicht Office 365er Daten](media/504e2dbe-f36f-4f36-9b08-04aea85d8250.png)

6. Kehren Sie schließlich zur Sicherheits #a0 Compliance zurück, und klicken Sie auf die Schaltfläche **Weiter: Prozessdateien** .  Dadurch werden Verarbeitung, Textextraktion und Indizierung der hochgeladenen Dateien initiiert.  Sie können den Fortschritt der Verarbeitung hier oder auf der Registerkarte **Aufträge** nachverfolgen.  Sobald der Vorgang abgeschlossen ist, sind die neuen Dateien im Evidence-Paket verfügbar.  Nachdem die Verarbeitung abgeschlossen ist, können Sie den Assistenten schließen.

![Nicht Office 365 Import Prozessdateien](media/218b1545-416a-4a9f-9b25-3b70e8508f67.png)

