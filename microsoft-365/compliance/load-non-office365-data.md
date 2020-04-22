---
title: Laden von nicht von Microsoft 365 Daten in Beweise
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
ms.openlocfilehash: 9eef3b38ceef7efc42e1f66c45069f51a0a95d45
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/21/2020
ms.locfileid: "43632630"
---
# <a name="load-non-microsoft-365-data-into-evidence"></a>Laden von nicht von Microsoft 365 Daten in Beweise

Nicht alle Dokumente, die Sie möglicherweise in einer Datenuntersuchung analysieren müssen, befinden sich in Microsoft 365. Mit der nicht-Microsoft 365-Funktion zum Importieren von Inhalten können Sie Dokumente, die nicht in Microsoft 365 Leben, in Beweise hochladen, damit Sie in einer Datenuntersuchung analysiert werden können.

## <a name="before-you-begin"></a>Bevor Sie beginnen

Wenn Sie das Feature "nicht-Microsoft 365 hochladen" wie in diesem Verfahren beschrieben verwenden, benötigen Sie Folgendes:

- Ein Microsoft 365-oder Office 365 E5-Abonnement.

- Alle Personen, deren Inhalt nicht von Microsoft 365 hochgeladen wird, müssen über die entsprechende E5-oder E5-Add-on-Lizenz verfügen.

- Ein vorhandener eDiscovery-Fall.

- Alle Dateien für das Hochladen wurden in Ordner gesammelt, in denen pro Depot ein Ordner vorhanden ist und der Name des Ordners in diesem Format *Alias@Domainname*. Das *Alias@Domainname* muss der Alias und die Domäne des Benutzers sein. Sie können alle *Alias@Domainname* Ordner in einem Stammordner sammeln. Der Stammordner kann nur die *Alias@Domainname* Ordner enthalten, es dürfen keine losen Dateien im Stammordner vorhanden sein.

- Ein Konto, bei dem es sich entweder um einen eDiscovery-Manager oder eDiscovery-Administrator handelt Microsoft Azure Speicher Tools, die auf einem Computer installiert sind, der Zugriff auf die Struktur eines nicht von Microsoft 365 Inhaltsordner hat.

- Installieren Sie AzCopy, was Sie von hier aus tun können:https://docs.microsoft.com/azure/storage/common/storage-use-azcopy

## <a name="upload-non-microsoft-365-content-in-to-a-data-investigation"></a>Hochladen von nicht-Microsoft 365-Inhalten in eine Datenuntersuchung

1. Öffnen Sie **Daten Untersuchungen** , und gehen Sie zu der Untersuchung, in die die Daten von nicht-Microsoft 365 hochgeladen werden.  Klicken Sie auf die Registerkarte **Beweise** , und wählen Sie dann den Beweissatz aus, in den Sie die Daten laden möchten.  Wenn Sie noch keinen Beweis Sätze erstellt haben, können Sie dies jetzt tun.  Klicken Sie schließlich auf **Beweise verwalten** , und zeigen Sie dann **Uploads** im Abschnitt Data an.

2. Klicken Sie auf die Schaltfläche **Dateien hochladen** , um den Datenimport-Assistenten von nicht Microsoft 365 zu starten.

![Dateien hochladen](../media/574f4059-4146-4058-9df3-ec97cf28d7c7.png)

3. Im ersten Schritt des Assistenten wird einfach ein sicheres Azure-BLOB für die zu hochzuladenden Dateien vorbereitet.  Klicken Sie nach Abschluss der Vorbereitung auf die Schaltfläche **Weiter: Dateien hochladen** .

![Vorbereiten des Datenimports von nicht-Microsoft 365](../media/0670a347-a578-454a-9b3d-e70ef47aec57.png)
 
4. Geben Sie im Schritt **Upload Files** den **Pfad zum Speicherort der Dateien**an, wo sich die nicht von Microsoft 365 Daten befinden, die Sie importieren möchten.  Durch Festlegen des richtigen Speicherorts wird sichergestellt, dass der AzCopy-Befehl ordnungsgemäß aktualisiert wird.

> [!NOTE]
> Wenn Sie AzCopy nicht bereits installiert haben, können Sie dies hier tun:https://docs.microsoft.com/azure/storage/common/storage-use-azcopy

5. Kopieren Sie den vordefinierten Befehl, indem Sie auf den Link **in Zwischenablage kopieren** klicken. Starten Sie eine Windows-Eingabeaufforderung, fügen Sie den Befehl ein, und drücken Sie die EINGABETASTE.  Die Dateien werden in den sicheren Azure-BLOB-Speicher für den nächsten Schritt hochgeladen.

![Hochladen von Dateien für den Datenimport von nicht-Microsoft 365](../media/3ea53b5d-7f9b-4dfc-ba63-90a38c14d41a.png)

![Verwenden von AzCopy zum Importieren von nicht von Microsoft 365 Daten](../media/504e2dbe-f36f-4f36-9b08-04aea85d8250.png)

6. Kehren Sie schließlich zur Sicherheits & Compliance zurück, und klicken Sie auf die Schaltfläche **Weiter: Prozessdateien** .  Dadurch werden Verarbeitung, Textextraktion und Indizierung der hochgeladenen Dateien initiiert.  Sie können den Fortschritt der Verarbeitung hier oder auf der Registerkarte **Aufträge** nachverfolgen.  Sobald der Vorgang abgeschlossen ist, sind die neuen Dateien im Evidence-Paket verfügbar.  Nachdem die Verarbeitung abgeschlossen ist, können Sie den Assistenten schließen.

![Nicht von Microsoft 365 Import Prozessdateien](../media/218b1545-416a-4a9f-9b25-3b70e8508f67.png)

