---
title: Erstellen eines inhaltscenters in Microsoft SharePoint Syntex
ms.author: efrene
author: efrene
manager: pamgreen
ms.date: 8/1/2020
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
description: Hier erfahren Sie, wie Sie ein inhaltscenter erstellen.
ms.openlocfilehash: 62977bc5a34b041e9e958ff46e0dbc010d6bd822
ms.sourcegitcommit: 15be7822220041c25fc52565f1c64d252e442d89
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/28/2020
ms.locfileid: "48295432"
---
# <a name="create-a-content-center-in-microsoft-sharepoint-syntex"></a>Erstellen eines inhaltscenters in Microsoft SharePoint Syntex

Der Inhalt in diesem Artikel ist für die Project Cortex private Preview. [Erfahren Sie mehr über Project Cortex](https://aka.ms/projectcortex).</br>

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CPSF]

</br>

Zum Erstellen und Verwalten von Dokument Verständnis Modellen benötigen Sie zunächst ein inhaltscenter. Das inhaltscenter ist die Modell Erstellungs Schnittstelle und enthält außerdem Informationen darüber, auf welche Dokumentbibliotheken veröffentlichte Modelle angewendet wurden.</br>

   ![Auswählen einer doc-Bibliothek](../media/content-understanding/content-center-page.png)</br>

Sie erstellen ein anfängliches inhaltscenter während des [Setups](set-up-content-understanding.md). Ein SharePoint-Administrator kann aber auch zusätzliche Center bei Bedarf erstellen. Während ein einzelnes inhaltscenter für Umgebungen geeignet ist, für die Sie eine Rollup aller Modell Aktivitäten durchführen möchten, können Sie zusätzliche Center für mehrere Abteilungen in Ihrer Organisation benötigen, die unterschiedliche Anforderungen und Anforderungen für Ihre Modelle haben können.

> [!NOTE]
> Ein SharePoint-Administrator kann eine inhaltscenter-Website erstellen, wie Sie eine [beliebige andere SharePoint-Website](https://docs.microsoft.com/sharepoint/create-site-collection) mithilfe einer Websitevorlage erstellen würde.

So erstellen Sie ein neues inhaltscenter:

1. Wechseln Sie im Microsoft 365 Admin Center zum SharePoint Admin Center.
2. Wählen Sie im SharePoint Admin Center unter **Websites**die Option **aktive Websites**aus.
3. Klicken Sie auf der Seite **aktive Websites** auf **Erstellen**, und wählen Sie dann **andere Optionen**aus.
4. Wählen Sie im Menü **Vorlage auswählen** die Option **Inhalts Center**aus.
5. Geben Sie für die neue Website einen **Websitenamen**, einen **primären Administrator**und eine **Sprache**an.</br>

> [!NOTE] 
> Optional können Sie eine inhaltscenter-Website auswählen, die in einer der verfügbaren Sprachen gerendert werden soll. Für englische Dateien können nur aktuelle Modelle erstellt werden.</br>

6. Wählen Sie **Fertig**aus.

### <a name="give-access-to-additional-users"></a>Zugriff auf zusätzliche Benutzer gewähren
 
Nachdem Sie die Website erstellt haben, können Sie über das standardmäßige [SharePoint-Website Berechtigungsmodell](https://docs.microsoft.com/sharepoint/modern-experience-sharing-permissions)weiteren Benutzern Zugriff auf die Website gewähren.

## <a name="see-also"></a>Siehe auch
[Erstellen einer Klassifizierung](create-a-classifier.md)</br>
[Erstellen eines Extraktions Moduls](create-an-extractor.md)</br>
[Erstellen eines inhaltscenters](create-a-content-center.md) 
 [Dokument Verständnis Übersicht](document-understanding-overview.md)</br>
[Erstellen eines Formular Verarbeitungsmodells](create-a-form-processing-model.md)</br>
[Anwenden eines Modells](apply-a-model.md)    
