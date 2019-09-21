---
title: Importieren nicht Office 365der Inhalte für die erweiterte eDiscovery-Analyse
ms.author: chrfox
author: chrfox
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- OEC150
- MET150
ms.assetid: 0ee60763-a30b-495b-8543-971c3384a801
description: Vorgehensweise zum Importieren von Inhalten, die nicht in O365 gespeichert sind, in ein Azure-BLOB, damit es mit AeD analysiert werden kann
ms.openlocfilehash: 1c971c9f95d03d05db76f80344adeb93b0a72c06
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/20/2019
ms.locfileid: "37081381"
---
# <a name="import-non-office-365-content-for-advanced-ediscovery-analysis"></a>Importieren nicht Office 365der Inhalte für die erweiterte eDiscovery-Analyse

Nicht alle Dokumente, die Sie möglicherweise mit Office 365 Advanced eDiscovery analysieren müssen, werden in Office 365 Live verwendet. Mit der nicht Office 365 Inhalts Importfunktion in Advanced eDiscovery können Sie Dokumente hochladen, die nicht in Office 365 (außer PST-Dateien) Leben, in einen verknüpften Fall, ein Azure-Speicher-BLOB, und diese mit Advanced eDiscovery analysieren. In diesem Verfahren erfahren Sie, wie Sie Ihre nicht-Office 365-Dokumente zur Analyse in Advanced eDiscovery integrieren.
  
> [!NOTE]
> Für Advanced eDiscovery ist ein Office 365 E3-Abonnement mit dem Add-On für erweiterte Compliance oder ein E5-Abonnement für Ihre Organisation erforderlich. Wenn Sie nicht über diesen Plan verfügen und Advanced eDiscovery ausprobieren möchten, können Sie sich [für eine Testversion von Office 365 Enterprise E5 anmelden](https://go.microsoft.com/fwlink/p/?LinkID=698279). 
  
> [!NOTE]
> Sie können ein Office 365 erweitertes eDiscovery Data Storage-Add-on-Abonnement für Ihre nicht Office 365 Inhalte erwerben. Dies steht ausschließlich für Inhalte zur Verfügung, die mit Advanced eDiscovery analysiert werden sollen. Führen Sie die Schritte in [kaufen oder bearbeiten und Add-on für Office 365 für Unternehmen](https://support.office.com/article/Buy-or-edit-an-add-on-for-Office-365-for-business-4e7b57d6-b93b-457d-aecd-0ea58bff07a6) aus, und kaufen Sie das Office 365 Advanced eDiscovery Storage Add-on. 
  
## <a name="before-you-begin"></a>Bevor Sie beginnen

Wenn Sie das Feature nicht Office 365 hochladen wie in diesem Verfahren beschrieben verwenden, benötigen Sie Folgendes:
  
- Ein Office 365 E3 mit Advanced Compliance-Add-on oder E5-Abonnement
    
- Alle Verwalter, deren nicht Office 365 Inhalt hochgeladen wird, müssen über E3 mit Advanced Compliance Add-on oder E5-Lizenzen verfügen.
    
- Ein vorhandener eDiscovery-Fall
    
- Alle Dateien für das Hochladen wurden in Ordner gesammelt, in denen ein Ordner pro Depotbank vorhanden ist, und der Name des Ordners ist in diesem Format *Alias @ Domain* Name. *Bei dem Alias @ Domain Name* muss es sich um Benutzer Office 365 Alias und Domäne handeln. Sie können alle Alias- *@ Domain Name* -Ordner in einem Stammordner sammeln. Der Stammordner darf nur die Ordner *Alias @ Domain Name* enthalten, es dürfen keine losen Dateien im Stammordner vorhanden sein. 
    
- Ein Konto, das entweder eDiscovery-Manager oder eDiscovery-Administrator ist
    
- [Microsoft Azure Speicher Tools](https://aka.ms/downloadazcopy) , die auf einem Computer installiert sind, der Zugriff auf die Struktur nicht Office 365 Inhaltsordner hat. 
    
## <a name="upload-non-office-365-content-into-advanced-ediscovery"></a>Hochladen nicht Office 365er Inhalte in die erweiterte eDiscovery

1. Öffnen Sie als eDiscovery-Manager oder eDiscovery-Administrator **eDiscovery**, und öffnen Sie den Fall, dass die nicht Office 365 Daten hochgeladen werden. Wenn Sie einen Fall erstellen müssen, finden Sie weitere Informationen unter [Verwalten von eDiscovery- &amp; Fällen im Office 365 Security Compliance Center](manage-ediscovery-cases.md)
    
2. Klicken Sie auf **zu Advanced eDiscovery wechseln** .
    
3. Wählen **** Sie unter Quelltext **nicht Office 365 Daten**aus.
    
4. Klicken Sie auf **Container hinzufügen**. Nennen Sie den Container, und fügen Sie eine Beschreibung hinzu.
    
5. Wählen Sie den neu hinzugefügten Container aus der Container Liste aus, und kopieren Sie die URL, die im Container Detailbereich angezeigt wird, und schließen Sie dann den Bereich.
    
6. Öffnen Sie eine Eingabeaufforderung als Administrator, und ändern Sie das Verzeichnis in Ordner, in dem Sie AzCopy installiert haben..
    
7. Erstellen Sie die AzCopy-Befehlszeile, um die Dateien wie folgt hochzuladen:
    
    AzCopy/Source: " *Vollständiger Pfad zum Stammordner auf dem lokalen Computer* "/dest: " *Container-URL bis einschließlich der?*  "/DestSAS:" *Rest der Container-URL aus dem? bis zum Ende* "/s 
    
    Verwenden Sie beispielsweise die folgenden Werte: 
    
  - Stammordner – C:\Collected-Daten 
    
  - Container-URL https://zoomsabcprodeuss114.blob.core.windows.net/ingestion53d059efe5f74784afb308f66cdebf17?sv=2015-04-05&amp-; SR =&amp;c Si = NonOfficeData15%&amp;7C0 SIG = Bk5INP8CUfv1y4CSJiJl3pJt3Ekvu8GS3P8NkOvoQxA% 3D
    
    die AzCopy-Befehlszeilensyntax lautet wie folgt:
    
     `AzCopy /Source:"C:\CollectedData" /Dest:"https://zoomsabcprodeuss114.blob.core.windows.net/ingestion53d059efe5f74784afb308f66cdebf17" /DestSAS:"?sv=2015-04-05&amp;sr=c&amp;si=NonOfficeData15%7C0&amp;sig=Bk5INP8CUfv1y4CSJiJl3pJt3Ekvu8GS3P8NkOvoQxA%3D" /S`
    
    Weitere Informationen zur Azcopy-Syntax finden Sie unter [übertragen von Daten mit dem Azcopy unter Windows](https://docs.microsoft.com/azure/storage/common/storage-use-azcopy) . 
    
    > [!IMPORTANT]
    > Es muss einen Stammordner pro Benutzer geben, und der Ordnername muss im *Alias @ Domain* Name Format liegen. 
  
8. Nachdem die Ordner fertig hochgeladen wurden, wechseln Sie zurück zu Advanced eDiscovery. Der Inhalt in den Ordnern, die Sie hochgeladen haben, ist nun für die Verarbeitung in Advanced eDiscovery verfügbar. Wählen Sie den Container aus, und klicken Sie auf die Schaltfläche Prozess. Weitere Informationen zur erweiterten eDiscovery-Verarbeitung finden Sie unter [Ausführen des Prozess Moduls und Laden von Daten in Office 365 Advanced eDiscovery](run-the-process-module-and-load-data-in-advanced-ediscovery.md) .
    
    > [!IMPORTANT]
    > Nachdem der Container in Advanced eDiscovery erfolgreich verarbeitet wurde, können Sie dem SAS-Speicher in Azure keine neuen Inhalte mehr hinzufügen. Wenn Sie zusätzliche Inhalte erfassen und Sie dem Fall für die erweiterte eDiscovery-Analyse hinzufügen möchten, müssen Sie einen neuen **nicht-Office 365-Daten** Container erstellen und dieses Verfahren wiederholen. 
  
    > [!NOTE]
    > Wenn der Container *aufgrund von Ordner Benennungs Problemen nicht erfolgreich verarbeitet* wird und Sie dann die Probleme beheben, müssen Sie weiterhin einen neuen Container erstellen und die wiederherstellen und erneut mit den Verfahren in diesem Artikel hochladen. 
  

