---
title: Nutzung der Terminologiespeichertaxonomie beim Erstellen eines Extraktors
ms.author: efrene
author: efrene
manager: pamgreen
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection: enabler-strategic
localization_priority: Priority
description: Nutzen Sie die Taxonomie von Terminologiespeicher, wenn Sie einen Extraktor in Ihrem Dokumentverständnismodell in Microsoft SharePoint Syntex erstellen.
ms.openlocfilehash: a8078e6ff2d2ecd0f98c22b602a54675f7d62816
ms.sourcegitcommit: f231eece2927f0d01072fd092db1eab15525bbc2
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/17/2020
ms.locfileid: "49701095"
---
# <a name="leverage-term-store-taxonomy-when-creating-an-extractor"></a>Nutzung der Terminologiespeichertaxonomie beim Erstellen eines Extraktors

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4GpJJ]  

</br>

Wenn Sie mit SharePoint Syntex einen Extraktor in Ihrem Dokumentverständnis-Modell erstellen, können Sie die Taxonomie des Terminologiespeichers der [Verwalteten Metadatendienste](https://docs.microsoft.com/sharepoint/managed-metadata#terms) nutzen, um bevorzugte Begriffe für die von Ihnen extrahierten Daten anzuzeigen.  

Ihr Modell identifiziert und klassifiziert beispielsweise alle **Vertrags** dokumente, die in die Dokumentbibliothek hochgeladen werden.  Darüber hinaus extrahiert das Modell aus jedem Vertrag einen **Vertragsdienst** wert und zeigt ihn in einer Spalte in Ihrer Bibliotheksansicht an. Unter den verschiedenen Vertragsdienst-Werten in den Verträgen gibt es mehrere ältere Werte, die Ihr Unternehmen nicht mehr verwendet und die umbenannt wurden. So sollten beispielsweise alle Bezüge auf die Begriffe *Design*, *Grafiken* oder *Topographie*-Vertragsdienste als *Kreativ* bezeichnet werden. Wenn Ihr Modell einen der veralteten Begriffe aus einem Vertragsdokument extrahiert, soll der aktuelle Ausdruck – Kreativ – in Ihrer Bibliotheksansicht angezeigt werden. Im folgenden Beispiel sehen wir beim Trainieren des Modells, dass ein Beispieldokument den veralteten Begriff *Design* enthält.

   ![Terminologiespeicher](../media/content-understanding/design.png)</br>

## <a name="use-a-managed-metadata-column-in-your-extractor"></a>Verwenden Sie eine Spalte für verwaltete Metadaten in Ihrem Extraktor

Ausdruckssätze werden im Terminologiespeicher für verwaltete Metadatendienste (MMS) im SharePoint Online Admin Center konfiguriert. Im folgenden Beispiel ist der [Ausdruckssatz](https://docs.microsoft.com/sharepoint/managed-metadata#term-set) für *Vertragsdienste* so konfiguriert, dass er eine Reihe von Begriffen enthält, einschließlich *Kreativ*.  Die Details dafür zeigen, dass der Begriff drei Synonyme (*Design*, *Grafiken* und *Topographie*) aufweist, und die Synonyme sollten in *Kreativ* übersetzt werden. 

   ![Ausdruckssatz](../media/content-understanding/term-store.png)</br>

> [!NOTE]
>  Ausdruckssätze werden im MMS-Feld des Inhaltscenters als „global“ konfiguriert.

Es kann mehrere Gründe geben, warum Sie möglicherweise ein Synonym in Ihrem Ausdruckssatz verwenden möchten. Beispielsweise kann es veraltete Ausdrücke, umbenannte Ausdrücke oder Abweichungen zwischen den Abteilungen Ihres Unternehmens bei der Benennung geben.

Damit Sie das Feld für verwaltete Metadaten beim Erstellen Ihres Extraktors in Ihrem Modell auswählen können, müssen Sie es als [Site-Spalte für verwaltete Metadaten hinzufügen](https://support.microsoft.com/office/8fad9e35-a618-4400-b3c7-46f02785d27f). Nachdem Sie die Site-Spalte hinzugefügt haben, können Sie diese auswählen, wenn Sie den Extraktor für Ihr Modell erstellen.

   ![Vertragsservice](../media/content-understanding/contract-services.png)</br>


Nach dem Anwenden Ihres Modells auf die Dokumentbibliothek wird beim Hochladen von Dokumenten in die Bibliothek in der Spalte *Kreative Dienste* der bevorzugte Ausdruck (*Kreativ*) angezeigt, wenn der Extraktor einen der Werte des Synonyms ermittelt (*Design*, *Grafik* und *Topographie*).

   ![Vertragsdienstspalte](../media/content-understanding/creative.png)</br>


## <a name="see-also"></a>Siehe auch
[Einführung in Verwaltete Metadaten](https://docs.microsoft.com/sharepoint/managed-metadata#terms)

[Erstellen eines Extraktors](create-an-extractor.md)

[Erstellen einer verwalteten Metadatenspalte](https://support.microsoft.com/office/create-a-managed-metadata-column-8fad9e35-a618-4400-b3c7-46f02785d27f?redirectSourcePath=%252farticle%252fc2a06717-8105-4aea-890d-3082853ab7b7&ui=en-US&rs=en-US&ad=US)





