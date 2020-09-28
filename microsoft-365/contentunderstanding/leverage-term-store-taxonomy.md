---
title: Terminologiespeicher-Taxonomie beim Erstellen eines Extraktors nutzen
ms.author: efrene
author: efrene
manager: pamgreen
ms.date: 10/1/2020
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
description: Nutzen Sie die Terminologiespeicher-Taxonomie beim Erstellen eines Extraktors in Ihrem Dokument Understanding Model in Microsoft SharePoint Syntex.
ms.openlocfilehash: 94f7a0389d2f06e0f8c1a60a341a02e43dfb2071
ms.sourcegitcommit: 15be7822220041c25fc52565f1c64d252e442d89
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/28/2020
ms.locfileid: "48295860"
---
# <a name="leverage-term-store-taxonomy-when-creating-an-extractor"></a>Terminologiespeicher-Taxonomie beim Erstellen eines Extraktors nutzen


</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CSoL]

</br>

Wenn Sie einen Extraktor in Ihrem Dokument Understanding Model in SharePoint Syntex erstellen, können Sie die Terminologiespeicher-Taxonomie für [verwaltete](https://docs.microsoft.com/sharepoint/managed-metadata#terms) Metadatendienst nutzen, um bevorzugte Ausdrücke für extrahierte Daten anzuzeigen.  

Beispielsweise identifiziert und klassifiziert Ihr Modell alle **Vertrags** Dokumente, die in die Dokumentbibliothek hochgeladen werden.  Darüber hinaus extrahiert das Modell auch einen **Vertrags Dienst** Wert aus jedem Vertrag und zeigt ihn in einer Spalte in der Bibliotheksansicht an. Unter den verschiedenen Contract Services-Werten in den Verträgen gibt es mehrere ältere Werte, die Ihr Unternehmen nicht mehr verwendet und umbenannt wurde. Beispielsweise sollten alle Verweise auf die Begriffe *Design*, *Grafiken*oder *Topographie* -Vertrags Dienste nun als *Creative*bezeichnet werden. Wenn Ihr Modell einen der veralteten Begriffe aus einem Vertragsdokument extrahiert, soll der aktuelle Ausdruck-Creative in ihrer Bibliotheksansicht angezeigt werden. Im folgenden Beispiel sehen wir beim Training des Modells, dass ein Beispieldokument den veralteten Ausdruck von *Design*enthält.

   ![Terminologiespeicher](../media/content-understanding/design.png)</br>


## <a name="term-set-synonyms"></a>Synonyme für Ausdruckssätze 

Ausdruckssätze werden im SharePoint Admin Center im Terminologiespeicher für verwaltete Metadatendienst konfiguriert. Im folgenden Beispiel ist der [Ausdruckssätze](https://docs.microsoft.com/sharepoint/managed-metadata#term-set) *Contract Services* so konfiguriert, dass er eine Reihe von Begriffen enthält, einschließlich *Creative*.  Die Details dafür zeigen, dass der Ausdruck drei Synonyme enthält (*Design*, *Grafiken*und *Topographie*), und die Synonyme sollten in *Creative*übersetzt werden.

   ![Ausdruckssatz](../media/content-understanding/term-store.png)</br>

<Mike, hier bin ich unsicher, wie ich dies beschreiben kann.  Welche Aktion weist das Modell darauf hin, dass beim Erstellen eines Extraktors zum Extrahieren und Anzeigen einer Vertrags Dienst Spalte die Spalte "markiert" ist, um den Ausdruckssätze für verwaltete Metadaten für Creative Services zu verwenden? >

## <a name="configure-your-document-library-site-column-for-a-managed-metadata-field"></a>Konfigurieren der Website Spalte für die Dokumentbibliothek für ein verwaltetes Metadatenfeld


   ![Erstellen verwalteter Metadaten](../media/content-understanding/creative.png)</br>

## <a name="see-also"></a>Siehe auch
[Einführung in verwaltete Metadaten](https://docs.microsoft.com/sharepoint/managed-metadata#terms)</br>
[Erstellen eines Extraktions Moduls](create-an-extractor.md)</br>
[Erstellen einer Spalte mit verwalteten Metadaten](https://support.microsoft.com/office/create-a-managed-metadata-column-8fad9e35-a618-4400-b3c7-46f02785d27f?redirectSourcePath=%252farticle%252fc2a06717-8105-4aea-890d-3082853ab7b7&ui=en-US&rs=en-US&ad=US)</br>





