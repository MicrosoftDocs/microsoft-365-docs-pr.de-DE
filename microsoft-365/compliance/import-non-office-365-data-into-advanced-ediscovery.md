---
title: Importieren von nicht-Microsoft 365-Inhalten für erweiterte eDiscovery-Analysen
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
titleSuffix: Office 365
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- OEC150
- MET150
ms.assetid: 0ee60763-a30b-495b-8543-971c3384a801
description: Vorgehensweise zum Importieren von Inhalten, die nicht in Microsoft 365 gespeichert sind, in ein Azure-BLOB, damit es mit AeD analysiert werden kann
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: fbb21f6bc3fdfd2a5251a9ec773a22351db5749e
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/19/2020
ms.locfileid: "44817594"
---
# <a name="import-non-microsoft-365-content-for-advanced-ediscovery-classic-analysis"></a>Importieren von nicht-Microsoft 365-Inhalten für die erweiterte eDiscovery-Analyse (klassisch)

Nicht alle Dokumente, die Sie möglicherweise mit Advanced eDiscovery analysieren müssen, werden in Microsoft 365 Live verwendet. Mit der nicht-Microsoft 365-Inhalts Importfunktion in Advanced eDiscovery können Sie Dokumente, die nicht in Microsoft 365 (außer PST-Dateien) Leben, in einen verknüpften Fall mit Azure Storage BLOB hochladen und mit Advanced eDiscovery analysieren. In diesem Verfahren erfahren Sie, wie Sie Ihre nicht-Microsoft 365-Dokumente zur Analyse in Advanced eDiscovery integrieren.
  
> [!NOTE]
> Für Advanced eDiscovery ist ein Office 365 E3-Abonnement mit dem Add-On für erweiterte Compliance oder ein E5-Abonnement für Ihre Organisation erforderlich. Wenn Sie nicht über diesen Plan verfügen und Advanced eDiscovery ausprobieren möchten, können Sie sich [für eine Testversion von Office 365 Enterprise E5 anmelden](https://go.microsoft.com/fwlink/p/?LinkID=698279). 
  
> [!NOTE]
> Sie können ein erweitertes eDiscovery Data Storage-Add-on-Abonnement für Ihre nicht von Microsoft 365 Inhalte erwerben. Dies steht ausschließlich für Inhalte zur Verfügung, die mit Advanced eDiscovery analysiert werden sollen. Befolgen Sie die Schritte unter [kaufen oder Bearbeiten eines Add-ons für Microsoft 365 for Business](https://docs.microsoft.com/microsoft-365/commerce/buy-or-edit-an-add-on) , und erwerben Sie das erweiterte eDiscovery-Speicher-Add-on. 
  
## <a name="requirements-to-upload-non-office-365-content"></a>Anforderungen zum Hochladen nicht Office 365der Inhalte

Wenn Sie das Feature nicht Office 365 hochladen wie in diesem Verfahren beschrieben verwenden, benötigen Sie Folgendes:
  
- Ein Office 365 E3 mit Advanced Compliance-Add-on oder E5-Abonnement
    
- Alle Verwalter, deren nicht Office 365 Inhalt hochgeladen wird, müssen über E3 mit Advanced Compliance Add-on oder E5-Lizenzen verfügen.
    
- Ein vorhandener eDiscovery-Fall
    
- Alle Dateien für das Hochladen wurden in Ordner gesammelt, in denen pro Depot ein Ordner vorhanden ist und der Name des Ordners in diesem Format *Alias@Domainname* . Die *Alias@Domainname* müssen Benutzer Office 365 Alias und Domäne sein. Sie können alle *Alias@Domainname* Ordner in einem Stammordner sammeln. Der Stammordner kann nur die *Alias@Domainname* Ordner enthalten, es dürfen keine losen Dateien im Stammordner vorhanden sein. 
    
- Ein Konto, das entweder eDiscovery-Manager oder eDiscovery-Administrator ist
    
- [Microsoft Azure Speicher Tools](https://aka.ms/downloadazcopy) , die auf einem Computer installiert sind, der Zugriff auf die Struktur nicht Office 365 Inhaltsordner hat. 
    
## <a name="upload-non-office-365-content-into-advanced-ediscovery"></a>Hochladen nicht Office 365er Inhalte in die erweiterte eDiscovery


1. Öffnen Sie als eDiscovery-Manager oder eDiscovery-Administrator **eDiscovery**, und öffnen Sie den Fall, dass die nicht Office 365 Daten hochgeladen werden. Wenn Sie einen Fall erstellen müssen, finden Sie weitere Informationen unter [Verwalten von eDiscovery-Fällen im Security &amp; Compliance Center](ediscovery-cases.md) .
    
2. Klicken Sie auf **zu Advanced eDiscovery wechseln** .
    
3. Wählen **Source type** Sie unter Quelltext **nicht Office 365 Daten**aus.
    
4. Klicken Sie auf **Container hinzufügen**. Nennen Sie den Container, und fügen Sie eine Beschreibung hinzu.
    
5. Wählen Sie den neu hinzugefügten Container aus der Container Liste aus, und kopieren Sie die URL, die im Container Detailbereich angezeigt wird, und schließen Sie dann den Bereich.
    
6. Öffnen Sie eine Eingabeaufforderung als Administrator, und ändern Sie das Verzeichnis in Ordner, in dem Sie AzCopy installiert haben..
    
7. Erstellen Sie die AzCopy-Befehlszeile, um die Dateien wie folgt hochzuladen:
    
    AzCopy/Source: " *Vollständiger Pfad zum Stammordner auf dem lokalen Computer* "/dest: " *Container-URL bis einschließlich der?*  "/DestSAS:" *Rest der Container-URL aus dem? bis zum Ende* "/s 
    
    Verwenden Sie beispielsweise die folgenden Werte: 
    
  - Stammordner – C:\Collected-Daten 
    
  - Container-URL- https://zoomsabcprodeuss114.blob.core.windows.net/ingestion53d059efe5f74784afb308f66cdebf17?sv=2015-04-05&amp ; SR = c &amp; Si = NonOfficeData15% 7C0 &amp; sig = Bk5INP8CUfv1y4CSJiJl3pJt3Ekvu8GS3P8NkOvoQxA% 3D
    
    die AzCopy-Befehlszeilensyntax lautet wie folgt:
    
     `AzCopy /Source:"C:\CollectedData" /Dest:"https://zoomsabcprodeuss114.blob.core.windows.net/ingestion53d059efe5f74784afb308f66cdebf17" /DestSAS:"?sv=2015-04-05&amp;sr=c&amp;si=NonOfficeData15%7C0&amp;sig=Bk5INP8CUfv1y4CSJiJl3pJt3Ekvu8GS3P8NkOvoQxA%3D" /S`
    
    Weitere Informationen zur Azcopy-Syntax finden Sie unter [übertragen von Daten mit dem Azcopy unter Windows](https://docs.microsoft.com/azure/storage/common/storage-use-azcopy) . 
    
    > [!IMPORTANT]
    > Pro Benutzer muss ein Stammordner vorhanden sein, und der Ordnername muss das *Alias@Domainname* Format aufweisen. 
  
8. Nachdem die Ordner fertig hochgeladen wurden, wechseln Sie zurück zu Advanced eDiscovery. Der Inhalt in den Ordnern, die Sie hochgeladen haben, ist nun für die Verarbeitung in Advanced eDiscovery verfügbar. Wählen Sie den Container aus, und klicken Sie auf die Schaltfläche Prozess. Weitere Informationen zur erweiterten eDiscovery-Verarbeitung finden Sie unter [Ausführen des Prozess Moduls und Laden von Daten in Advanced eDiscovery](run-the-process-module-and-load-data-in-advanced-ediscovery.md) .
    
    > [!IMPORTANT]
    > Nachdem der Container in Advanced eDiscovery erfolgreich verarbeitet wurde, können Sie dem SAS-Speicher in Azure keine neuen Inhalte mehr hinzufügen. Wenn Sie zusätzliche Inhalte erfassen und Sie dem Fall für die erweiterte eDiscovery-Analyse hinzufügen möchten, müssen Sie einen neuen **nicht-Office 365-Daten** Container erstellen und dieses Verfahren wiederholen. 
  
    > [!NOTE]
    > Wenn der Container *aufgrund von Ordner Benennungs Problemen nicht erfolgreich verarbeitet* wird und Sie dann die Probleme beheben, müssen Sie weiterhin einen neuen Container erstellen und die wiederherstellen und erneut mit den Verfahren in diesem Artikel hochladen.
