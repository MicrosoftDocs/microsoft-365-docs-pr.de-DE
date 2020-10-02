---
title: Bild-Tagging in SharePoint Syntex
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: MET150
localization_priority: Priority
description: Mehr zu Bild-Tagging in SharePoint Syntex
ms.openlocfilehash: 7b41422633934593de881bdb0c04f0a845a3fe5f
ms.sourcegitcommit: f7ca339bdcad38796c550064fb152ea09687d0f3
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/30/2020
ms.locfileid: "48321253"
---
# <a name="image-tagging-in-sharepoint-syntex"></a>Bild-Tagging in SharePoint Syntex

Mit Bild-Tagging in SharePoint Syntex können Benutzer Bilder über die Suche finden, indem Sie nach Bild-Tags suchen und Workflows basierend auf Bild-Tags erstellen. Standardmäßig ist Bild-Tagging für Microsoft Office SharePoint Online und OneDrive aktiviert. Bilder, die an einen der beiden Standorte hochgeladen werden, werden automatisch gescannt und, falls verfügbar, werden anwendbare Tags aus einer Liste von 37 Basis-Tags angewendet. Benutzer können Bilder über die Suche finden, indem Sie Bild-Tags durchsuchen.

Wenn ein Benutzer ein Bild hochlädt, läuft der Tagging-Prozess automatisch ab. Wenn ein Bild bearbeitet wird, läuft der Tagging-Prozess erneut ab, um die Tags zu aktualisieren.

Benutzer mit Berechtigungen für die Bilddatei können die Tags im Dateiinformationsfenster oder auf der Suchergebnisseite sehen und bearbeiten. Sobald ein Benutzer die Tags eines Bildes bearbeitet, führt das System keine automatische Markierung mehr für dieses Bild durch, selbst wenn es bearbeitet ist.

Wenn Sie den Tagging-Prozess ausschalten, werden Bilder nicht mehr automatisch mit Tags versehen. Vorhandene Tags werden nicht entfernt.

> [!NOTE]
> Vom System generierte Tags können sich durch Updates des Bilds oder unserer Tag-Technologie ändern.


## <a name="configure-image-tagging"></a>Bild-Tagging konfigurieren

Nachdem Sie [SharePoint Syntex eingerichtet haben](set-up-content-understanding.md), können Sie Bild-Tagging im Microsoft 365 Admin Center konfigurieren.  

So schalten Sie die Bild-Tagging-Funktion ein oder aus

1. Klicken Sie im Microsoft 365 Admin Center auf **Setup**.

2. Klicken Sie unter **Organisationswissen** auf **Inhaltsverständnis automatisieren**.

3. Klicken Sie auf **Verwalten**.

4. Klicken Sie auf der Registerkarte **Bild-Tagging** auf **Bearbeiten**.

5. Wählen Sie, ob Sie **Basic Tagging** zulassen oder Markieren **ausschalten** möchten.

6. Klicken Sie auf **Speichern**.

    ![Screenshot der Bild-Tagging-Steuerung](../media/content-understanding/sharepoint-syntex-image-tagging-control.png)
