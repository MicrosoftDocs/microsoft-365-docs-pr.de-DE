---
title: Importieren von nicht-Microsoft 365-Inhalten für erweiterte eDiscovery-Analysen
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
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
ms.openlocfilehash: 03220e6baf16662ad8dfa970ef4d7077d08b0826
ms.sourcegitcommit: 47de4402174c263ae8d70c910ca068a7581d04ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/12/2020
ms.locfileid: "49662900"
---
# <a name="import-non-microsoft-365-content-for-advanced-ediscovery-classic-analysis"></a>Importieren von nicht-Microsoft 365-Inhalten für die erweiterte eDiscovery-Analyse (klassisch)

Nicht alle Dokumente, die Sie möglicherweise mit Advanced eDiscovery analysieren müssen, werden in Microsoft 365 Live verwendet. Mit der nicht-Microsoft 365-Inhalts Importfunktion in Advanced eDiscovery können Sie Dokumente, die nicht in Microsoft 365 (außer PST-Dateien) Leben, in einen verknüpften Fall mit Azure Storage BLOB hochladen und mit Advanced eDiscovery analysieren. In diesem Verfahren erfahren Sie, wie Sie Ihre nicht-Microsoft 365-Dokumente zur Analyse in Advanced eDiscovery integrieren.
  
> [!NOTE]
> Für Advanced eDiscovery ist ein Office 365 E3-Abonnement mit dem Add-On für erweiterte Compliance oder ein E5-Abonnement für Ihre Organisation erforderlich. Wenn Sie nicht über diesen Plan verfügen und Advanced eDiscovery ausprobieren möchten, können Sie sich [für eine Testversion von Office 365 Enterprise E5 anmelden](https://go.microsoft.com/fwlink/p/?LinkID=698279). 
  
> [!NOTE]
> Sie können ein erweitertes eDiscovery Data Storage-Add-on-Abonnement für Ihre nicht von Microsoft 365 Inhalte erwerben. Dies steht ausschließlich für Inhalte zur Verfügung, die mit Advanced eDiscovery analysiert werden sollen. Befolgen Sie die Schritte unter [kaufen oder Bearbeiten eines Add-ons für Microsoft 365 for Business](https://docs.microsoft.com/microsoft-365/commerce/buy-or-edit-an-add-on) , und erwerben Sie das erweiterte eDiscovery-Speicher-Add-on. 
  
## <a name="requirements-to-upload-non-office-365-content"></a>Anforderungen zum Hochladen nicht Office 365der Inhalte

Wenn Sie das Feature nicht Office 365 hochladen wie in diesem Verfahren beschrieben verwenden, benötigen Sie Folgendes:
  
- Ein Office 365 E3 mit Advanced Compliance-Add-on oder E5-Abonnement.
    
- Alle Verwalter, deren nicht Office 365 Inhalt hochgeladen wird, müssen über E3 mit Advanced Compliance Add-on oder E5-Lizenzen verfügen.
    
- Ein vorhandener eDiscovery-Fall.
    
- Alle Dateien für das Hochladen wurden in Ordner gesammelt, in denen pro Depot ein Ordner vorhanden ist und der Name des Ordners in diesem Format  *Alias@Domainname*  . Die  *Alias@Domainname*  müssen Benutzer Office 365 Alias und Domäne sein. Sie können alle  *Alias@Domainname*  Ordner in einem Stammordner sammeln. Der Stammordner kann nur die  *Alias@Domainname*  Ordner enthalten, es dürfen keine losen Dateien im Stammordner vorhanden sein.
    
- Ein Konto, das entweder eDiscovery-Manager oder eDiscovery-Administrator ist.
    
- [Microsoft Azure Speicher Tools](https://aka.ms/downloadazcopy) , die auf einem Computer installiert sind, der Zugriff auf die Struktur nicht Office 365 Inhaltsordner hat. 
    
## <a name="upload-non-office-365-content-into-advanced-ediscovery"></a>Hochladen nicht Office 365er Inhalte in die erweiterte eDiscovery


1. Öffnen Sie als eDiscovery-Manager oder eDiscovery-Administrator **eDiscovery**, und öffnen Sie den Fall, dass die nicht Office 365 Daten hochgeladen werden. Wenn Sie einen Fall erstellen müssen, finden Sie weitere Informationen unter [Verwalten von eDiscovery-Fällen im Security &amp; Compliance Center](ediscovery-cases.md).
    
2. Klicken Sie auf **zu Advanced eDiscovery wechseln**.

3. Wählen Sie im Menü **Überprüfungs Sätze** aus.

4. Wählen Sie einen vorhandenen Überprüfungs aus, oder wählen Sie **Add Review Sets** aus.

5. Wählen Sie **Manage Review Sets** aus.

6. Wählen Sie auf der nicht Office 365-Datenkarte die Option **Uploads anzeigen** aus.

7. Wählen Sie **Dateien hochladen** aus, um den Dateiupload-Assistenten zu starten.

8. Die erste Registerkarte ist **1. Vorbereiten des Schritts**. Wählen Sie **Weiter: Upload Files** aus.

9. Auf der **2.** Registerkarte "Dateien hochladen" Sie werden aufgefordert, AzCopy.exe herunterzuladen, wenn Sie dies nicht bereits getan haben, und dann den Pfad zum Dateispeicherort anzugeben. Beispielsweise `C:\Upload`  erhalten Sie den Befehl zum Ausführen AzCopy.exe. Mit wird `C:\Upload` Folgendes angezeigt:

   `"%ProgramFiles(x86)%\Microsoft SDKs\Azure\AzCopy\AzCopy.exe" /Source:"c:\upload" /Dest:"https://spnam03salinkexternal003.blob.core.windows.net/16d13440-a6a4-4bc5-a82b-10ac9cfe9d7c-1601401811-externalstore?sv=2017-07-29&sr=c&si=ExternalStore63%7C0&sig=9Dq5v20TwkxByYDHhIEx%2FHSLlmlqUjY0njkJyTO0zGA%3D" /s`
  
10. Öffnen Sie ein Eingabeaufforderungsfenster, und führen Sie den Befehl AzCopy.exe aus, um die Daten in Azure zu importieren. Nachdem alle Daten geladen wurden, wählen Sie **Weiter: Process files**.

11. Die nächste Registerkarte ist **3. Verarbeiten von Dateien** , in denen die depotverwalter angezeigt werden, denen Daten zugeordnet sind, und der Fortschritt der importierten Daten wird angezeigt.
        
    Weitere Informationen zur Azcopy-Syntax finden Sie unter [übertragen von Daten mit dem Azcopy unter Windows](https://docs.microsoft.com/azure/storage/common/storage-use-azcopy). 
    
    Weitere Informationen zur erweiterten eDiscovery-Verarbeitung finden Sie unter [Ausführen des Prozess Moduls und Laden von Daten in Advanced eDiscovery (Classic)](run-the-process-module-and-load-data-in-advanced-ediscovery.md). 
    
    > [!IMPORTANT]
    > Pro Benutzer muss ein Stammordner vorhanden sein, und der Ordnername muss das <b>Alias@Domainname</b>  Format aufweisen. 
   
    > [!IMPORTANT]
    > Nachdem der Container in Advanced eDiscovery erfolgreich verarbeitet wurde, können Sie dem SAS-Speicher in Azure keine neuen Inhalte mehr hinzufügen. Wenn Sie zusätzliche Inhalte erfassen und Sie dem Fall für die erweiterte eDiscovery-Analyse hinzufügen möchten, müssen Sie einen neuen **nicht-Office 365-Daten** Container erstellen und dieses Verfahren wiederholen. 
  
    > [!NOTE]
    > Wenn der Container  *aufgrund von Ordner Benennungs Problemen nicht erfolgreich verarbeitet*  wird und Sie dann die Probleme beheben, müssen Sie weiterhin einen neuen Container erstellen und die wiederherstellen und erneut mit den Verfahren in diesem Artikel hochladen.
