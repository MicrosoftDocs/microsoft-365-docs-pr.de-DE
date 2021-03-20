---
title: Erstellen eines inhaltscenters in Microsoft SharePoint Syntex
ms.author: efrene
author: efrene
manager: pamgreen
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-syntex
localization_priority: Priority
description: Erhalten Sie Informationen zum Erstellen eines Inhaltscenters.
ms.openlocfilehash: 34ba45cd62214743e5a6784893e0f24e9815fdfb
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50905824"
---
# <a name="create-a-content-center-in-microsoft-sharepoint-syntex"></a>Erstellen eines inhaltscenters in Microsoft SharePoint Syntex


</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CPSF]

</br>

Zum Erstellen und Verwalten von Dokumentverständnismodellen benötigen Sie zuerst ein Inhaltscenter. Beim Inhaltscenter handelt es sich um die Modellerstellungsoberfläche. Es enthält aber auch Informationen dazu, auf welche Dokumentbibliotheken veröffentlichte Modelle angewendet wurden.</br>

   ![Auswählen einer Dokumentbibliothek](../media/content-understanding/content-center-page.png)</br>

Sie erstellen ein Standardinhaltscenter während des [Setups](set-up-content-understanding.md). Ein SharePoint-Administrator kann aber bei Bedarf auch zusätzliche Center erstellen. Während ein einzelnes Inhaltscenter für Umgebungen, für die Sie eine Rollup aller Modellaktivitäten durchführen möchten, möglicherweise in Ordnung ist, möchten Sie möglicherweise zusätzliche Zentren für mehrere Abteilungen in Ihrer Organisation einrichten, die möglicherweise unterschiedliche Bedürfnisse und Berechtigungsanforderungen an Ihre Modelle haben.

> [!NOTE]
> Wenn Sie in einer [Microsoft 365 Multi-Geo-Umgebung](../enterprise/microsoft-365-multi-geo.md) ein einzelnes Standardinhaltscenter an Ihrem zentralen Speicherort haben, können Sie nur ein Rollup der Modellaktivität von diesem Speicherort aus bereitstellen. In einer Multi-Geo-Umgebung können Sie derzeit kein Rollup der Modellaktivität über Farmgrenzen hinweg erhalten. 


## <a name="create-a-content-center"></a>Erstellen eines Inhaltscenters

Ein SharePoint-Administrator kann eine Inhaltscenter-Website erstellen, wie er auch eine beliebige andere [SharePoint-Website](/sharepoint/create-site-collection) über den Bereitstellungsbereich der Admin Center-Website erstellen würde.

So erstellen Sie ein neues Inhaltscenter:

1. Wechseln Sie im Microsoft 365 Admin Center zum SharePoint Admin Center.

2. Wählen Sie im SharePoint Admin Center unter **Websites** die Option **Aktive Websites** aus.

3. Klicken Sie auf der Seite **Aktive Websites** auf **Erstellen**, und wählen Sie dann **Sonstige Optionen** aus.

4. Wählen Sie im Menü **Vorlage auswählen** die Option **Inhaltscenter** aus.

5. Stellen Sie für die neue Website Angaben für **Websitename**, **Primärer Administrator** und **Sprache** bereit.</br>

   > [!NOTE] 
   > Sie können eine inhaltscenter-Website für die Darstellung in einer der verfügbaren Sprachen auswählen. Beachten Sie jedoch, dass zurzeit nur für englische Dateien Modelle erstellt werden können. Beachten Sie auch, dass die Standardsprache der Website nach der Erstellung (wie bei anderen Websitevorlagen) nicht mehr bearbeitet werden kann.</br>

6. Wählen Sie **Fertigstellen** aus.
 
Nachdem Sie eine Inhaltscenter-Website erstellt haben, wird Sie im SharePoint Admin Center auf der Seite **Aktive Websites** angezeigt. 

### <a name="give-access-to-additional-users"></a>Gewähren des Zugriffs für zusätzliche Benutzer
 
Nachdem Sie die Website erstellt haben, können Sie zusätzlichen Benutzern den Zugriff auf die Website über das standardmäßige [SharePoint-Websiteberechtigungsmodell](/sharepoint/modern-experience-sharing-permissions) gewähren.

## <a name="see-also"></a>Siehe auch
[Erstellen einer Klassifizierung](create-a-classifier.md)

[Erstellen eines Extraktors](create-an-extractor.md)

[Erstellen eines Inhaltscenters](create-a-content-center.md)

[Übersicht über das Dokumentenverständnis](document-understanding-overview.md)

[Erstellen eines Formularverarbeitungsmodells](create-a-form-processing-model.md)

[Anwenden eines Modells](apply-a-model.md)