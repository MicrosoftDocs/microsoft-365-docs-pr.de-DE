---
title: Bild-Tagging in SharePoint Syntex
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: Priority
description: Mehr zu Bild-Tagging in SharePoint Syntex
ms.openlocfilehash: 38b9ad6823aa5f63a4ddec87bab7fec52a37f163
ms.sourcegitcommit: 15be7822220041c25fc52565f1c64d252e442d89
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/28/2020
ms.locfileid: "48296096"
---
# <a name="image-tagging-in-sharepoint-syntex"></a>Bild-Tagging in SharePoint Syntex

Standardmäßig ist Bild-Tagging für Microsoft Office SharePoint Online und OneDrive aktiviert. Bilder, die an einen der beiden Standorte hochgeladen werden, werden automatisch gescannt und, falls verfügbar, werden anwendbare Tags aus einer Liste von 37 Basis-Tags angewendet. Benutzer können Bilder über die Suche finden, indem Sie Bild-Tags durchsuchen.

Wenn ein Benutzer ein Bild hochlädt, läuft der Tagging-Prozess automatisch ab. Wenn ein Bild bearbeitet wird, läuft der Tagging-Prozess erneut ab, um die Tags zu aktualisieren.

Benutzer mit Berechtigungen für die Bilddatei können die Tags im Dateiinformationsfenster oder auf der Suchergebnisseite sehen und bearbeiten. Sobald ein Benutzer die Tags eines Bildes bearbeitet, führt das System keine automatische Markierung mehr für dieses Bild durch, selbst wenn es bearbeitet wird.

Wenn Sie Markieren ausschalten, werden Bilder nicht mehr automatisch mit Tags versehen. Vorhandene Tags werden nicht entfernt.

## <a name="configure-image-tagging"></a>Bild-Tagging konfigurieren

Sie können Bild-Tagging im Microsoft 365 Admin Center konfigurieren.  

So schalten Sie die Bild-Tagging-Funktion ein oder aus

1. Klicken Sie im Microsoft 365 Admin Center auf **Setup**.

2. Klicken Sie unter **Organisationswissen** auf **Inhaltsverständnis automatisieren**.

3. Klicken Sie auf **Verwalten**.

4. Klicken Sie auf der Registerkarte **Bild-Tagging** auf **Bearbeiten**.

5. Wählen Sie, ob Sie **Basic Tagging** zulassen oder Markieren **ausschalten** möchten.

6. Klicken Sie auf **Speichern**.

    ![Screenshot der Bild-Tagging-Steuerung](../media/content-understanding/sharepoint-syntex-image-tagging-control.png)

## <a name="see-also"></a>Mehr dazu

[Inhaltsverständnis einrichten](set-up-content-understanding.md)