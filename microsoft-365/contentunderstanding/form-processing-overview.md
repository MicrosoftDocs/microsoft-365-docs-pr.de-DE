---
title: Übersicht über die Formularverarbeitung (Vorschau)
ms.author: efrene
author: efrene
manager: pamgreen
ms.date: 8/1/2020
audience: admin
ms.topic: article
ms.service: ''
search.appverid: ''
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
description: Erfahren Sie mehr über die Formularverarbeitung in Project Cortex.
ms.openlocfilehash: 9709c8170f5dc6ce0edbeb2d90cb4e1f6d759c64
ms.sourcegitcommit: 3a47efcbdf3d2b39caa2798ea5be806839b05ed1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/01/2020
ms.locfileid: "46540058"
---
# <a name="form-processing-overview-preview"></a>Übersicht über die Formularverarbeitung (Vorschau)
> [!Note]
> Der Inhalt dieses Artikels ist für Project Cortex private Preview. [Erfahren Sie mehr über Project Cortex](https://aka.ms/projectcortex).

Project Cortex verwendet Microsoft PowerApps [AI Builder](https://docs.microsoft.com/ai-builder/overview) -Formularverarbeitung zum Erstellen von Modellen in SharePoint-Dokumentbibliotheken.
Sie können die AI Builder-Formularverarbeitung zum Erstellen von AI-Modellen verwenden, die maschinelle Lerntechnologie zum Identifizieren und Extrahieren von Schlüssel/Wert-Paaren und Tabellendaten aus strukturierten oder semi-strukturierten Dokumenten wie Formularen und Rechnungen verwenden.

Unternehmen erhalten häufig Rechnungen in großen Mengen und aus einer Vielzahl von Quellen wie e-Mail, Fax, e-Mail oder persönlich. Die Verarbeitung dieser Dokumente und die manuelle Eingabe in Ihre Datenbank kann sehr viel Zeit in Anspruch nehmen. Durch die Verwendung von AI zum Extrahieren von Text, Schlüssel/Wert-Paaren und Tabellen aus Ihren Dokumenten wird dieser Prozess von der Formularverarbeitung automatisiert. 

Sie können beispielsweise ein Formular Verarbeitungsmodell erstellen, mit dem alle Bestelldokumente identifiziert werden, die in die Dokumentbibliothek hochgeladen werden. Und aus jeder Bestellung können Sie bestimmte Daten extrahieren und anzeigen, die für Sie wichtig sind, beispielsweise *Bestellnummer*, *Datum*oder *Gesamtkosten*.

Sie verwenden Beispieldateien, um Ihr Modell zu trainieren und die Informationen zu definieren, die aus dem Formular extrahiert werden sollen. Das Layout Ihres Dokuments wird durch Schulung Ihres Modells erlernt. Für die ersten Schritte benötigen Sie nur fünf Formular Dokumente. Im AI-Gebäude werden Ihre Beispieldateien für Schlüssel-Wert-Paare analysiert, und Sie können auch manuell erkennen, welche möglicherweise nicht erkannt wurden.  Mit AI Builder können Sie die Genauigkeit Ihres Modells in ihren Beispieldateien testen.

Nachdem Sie Ihr Modell trainiert und veröffentlicht haben, erstellen Sie einen Power- [Automatisierungs Fluss](https://docs.microsoft.com/power-automate/getting-started) , der ausgeführt wird, wenn eine Datei in die SharePoint-Dokumentbibliothek hochgeladen wird und Daten extrahiert, die im Modell identifiziert wurden. Die extrahierten Daten werden in den Spalten in der Dokumentbibliotheksansicht Ihres Modells angezeigt.

Ein Office 365 Administrator muss die [Formularverarbeitung](https://docs.microsoft.com/microsoft-365/contentunderstanding/set-up-content-understanding?view=o365-worldwide#to-set-up-content-understanding) für die SharePoint-Dokumentbibliothek aktivieren, damit Benutzer [ein Formular Verarbeitungsmodell](create-a-form-processing-model.md) in dieser erstellen können.



## <a name="see-also"></a>Siehe auch
  
[Power Automation-Dokumentation](https://docs.microsoft.com/power-automate/)</br>
[Erstellen eines Formular Verarbeitungsmodells](create-a-form-processing-model.md)</br>
[Dokument Verständnis Übersicht](document-understanding-overview.md)</br>
[Schulung: verbessern der Geschäftsleistung mit AI Builder](https://docs.microsoft.com/learn/paths/improve-business-performance-ai-builder/?source=learn)</br>




