---
title: Lokalisieren der Benutzeroberfläche
description: So lokalisieren Sie Geräte für Benutzer
keywords: Microsoft Managed Desktop, Microsoft 365, Dienst, Dokumentation
ms.service: m365-md
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
manager: laurawi
ms.topic: article
audience: Admin
ms.openlocfilehash: 20456ce837be60b707569ae07d4fb00b695b3a98
ms.sourcegitcommit: 39609c4d8c432c8e7d7a31cb35c8020e5207385b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/30/2021
ms.locfileid: "51445981"
---
# <a name="localize-the-user-experience"></a>Lokalisieren der Benutzeroberfläche

Benutzer von Microsoft Managed Desktop-Geräten können die Sprache ihrer Wahl entweder während des Setupvorgangs (die "out-of-box"-Erfahrung) oder danach auswählen.

## <a name="during-setup-the-out-of-box-experience"></a>Während des Setups (die "out-of-box"-Erfahrung)

Während des Abschlusses des Setups können Benutzer die Sprache ihrer Wahl auswählen. Diese Auswahl wirkt sich auf die folgenden Attribute aus:

- Windows 10-Sprachfeatures:
    - Anzeigesprache
    - Tastatursprache
    - Sprachbezogene Features bei Bedarf

- Sprachfeatures für Microsoft 365 Apps for Enterprise:
    - Anzeigesprache
    - Korrekturhilfen und Erstellungstools

> [!NOTE]
> Benutzer können nur sprachbezogene Features bei Bedarf erhalten, indem sie die Sprache während des Setupvorgangs auswählen.

## <a name="after-completing-setup"></a>Nach Abschluss des Setups

Benutzer können die Sprache ihrer Wahl für Windows 10 und Microsoft 365 Apps for Enterprise jederzeit nach Abschluss des Einrichtungsprozesses auswählen. Insbesondere gilt:

- Windows 10-Sprachfeatures:
    - Anzeigesprache
    - Tastatursprache

- Sprachfeatures für Microsoft 365 Apps for Enterprise:
    - Anzeigesprache
    - Korrekturhilfen und Erstellungstools

Um die [unterstützten](#supported-languages) Sprachen für Microsoft 365 Apps for Enterprise für Ihre Benutzer verfügbar zu machen, fügen Sie die Benutzer der Gruppe **Modern Workplace-Office-Language_Packs** hinzu. Die Sprachen sind im Intune-Unternehmensportal verfügbar.


## <a name="supported-languages"></a>Unterstützte Sprachen

Für neue Geräte muss Ihr Hersteller Gerätebilder bereitstellen, die die von Ihnen benötigten Sprachen enthalten. Wenn das Image Ihres Herstellers andere Als die in der Liste der unterstützten Sprachen bereitgestellten Sprachen enthält, wird es weiterhin vom Dienst unterstützt.

Wenn Sie vorhandene Geräte erneut verwenden, müssen Sie möglicherweise mit Ihrem Microsoft-Kontomitarbeiter zusammenarbeiten, um geeignete Bilder zu erhalten. Weitere Informationen finden Sie unter [Gerätebilder](../service-description/device-images.md).

Das [von](../service-description/device-images.md#universal-image) Microsoft Managed Desktop bereitgestellte universelle Bild umfasst die folgenden Sprachen und für Windows 10:

- Englisch (US, GB, AU, CA, IN)
- Spanisch (Spanien, Mexiko)
- Japanisch
- Französisch (Frankreich, Kanada)
- Deutsch
- Portugiesisch (Brasilien)
- Italienisch
- Chinese Simplified
- Niederländisch  
- Schwedisch
- Dänisch  
- Finnisch 
- Russisch 
- Norwegisch (Bokmal)
- Koreanisch
- Chinese Traditional
- Polnisch
- Türkisch
- Arabisch
- Hebräisch
- Portugiesisch (Portugal)
- Tschechisch
- Ungarisch
- Thailändisch
- Indonesisch
- Griechisch
- Slowakisch
- Vietnamesisch
- Slowenisch
- Kroatisch
- Rumänisch
- Litauisch
- Bulgarisch
- Serbisch (lateinisches Alphabet)
- Lettisch
- Ukrainisch
- Estnisch

Microsoft 365 Apps for Enterprise unterstützt möglicherweise eine etwas andere Liste.

Wenn Ihre Benutzer eine andere Sprache als die [](../working-with-managed-desktop/admin-support.md) hier aufgeführten benötigen, stellen Sie eine Supportanfrage mithilfe des [Admin-Portals.](access-admin-portal.md)

## <a name="languages-for-support-and-operations"></a>Sprachen für Support und Vorgänge

### <a name="user-support"></a>Benutzerunterstützung
Microsoft Managed Desktop bietet Unterstützung nur in Englisch. Wenn Benutzer in der App Hilfe erhalten eine andere Sprache auswählen, erhalten sie Unterstützung von den allgemeinen Microsoft-Supportkanälen und nicht direkt von Microsoft Managed Desktop. Weitere Informationen finden Sie unter [Abrufen von Hilfe für Benutzer](../working-with-managed-desktop/end-user-support.md).

Wenn Ihre Benutzer Unterstützung in anderen Sprachen benötigen, müssen Sie dies über Nicht-Microsoft-Supportquellen oder aus Ihrer eigenen Organisation bereitstellen.

### <a name="admin-support-and-operations"></a>Administratorunterstützung und -vorgänge
Microsoft Managed Desktop bietet Administratorunterstützung nur in Englisch. Dies umfasst das Administratorportal und die gesamte Kommunikation mit Microsoft Managed Desktop Operations. Sie sollten davon ausgehen, dass alle administratorbezogenen Interaktionen und Schnittstellen in Englisch sind, sofern nicht anders angegeben.


