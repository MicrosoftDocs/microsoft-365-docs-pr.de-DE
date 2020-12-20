---
title: Verwenden Sie den Assistenten für das Schema exakter Datenübereinstimmung und vertrauliche Informationstypen.
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.date: ''
localization_priority: Priority
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Erfahren Sie, wie Sie den Assistenten für das Schema exakter Datenübereinstimmung und vertrauliche Informationstypen verwenden können.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 2081de887e09794350222dac3527bb3ff932837a
ms.sourcegitcommit: 884ac262443c50362d0c3ded961d36d6b15d8b73
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/16/2020
ms.locfileid: "49699147"
---
# <a name="use-the-exact-data-match-schema-and-sensitive-information-type-wizard"></a>Verwenden Sie den Assistenten für das Schema exakter Datenübereinstimmung und vertrauliche Informationstypen.

[Das Erstellen eines benutzerdefinierten Typs vertraulicher Informationen mit auf genauer Datenübereinstimmung (Exact Data Match, EDM) basierender Klassifizierung](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md) umfasst mehrere Schritte.  Sie können diesen Assistenten verwenden, im Ihre Schema- und Musterdateien für vertrauliche Informationstypen (Regelpaket) zu erstellen, um den Prozess zu vereinfachen.

> [!NOTE]
> Der Assistent für das Schema genauer Datenübereinstimmung und vertraulicher Informationstypen ist nur für die World Wide- und GCC-Cloud verfügbar.

Der Assistent kann verwendet werden an Stelle von:

- [Definieren des Schemas für Ihre Datenbank mit vertraulichen Informationen](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md#define-the-schema-for-your-database-of-sensitive-information)
- [Richten Sie ein Muster (Regelpaket) ein](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md#set-up-a-rule-package)

Schritte für [Teil 1: Einrichten der EDM-basierten Klassifizierung](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md#part-1-set-up-edm-based-classification).

## <a name="pre-requisites"></a>Voraussetzungen

1. Machen Sie sich mit den Schritten vertraut, um einen benutzerdefinierten vertraulichen Informationstyp mit dem EDM-[Workflow auf einen Blick](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md#the-work-flow-at-a-glance) zu erstellen.

2. Führen Sie die Schritte im Abschnitt [Vertrauliche Daten im .csv-Format speichern](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md#save-sensitive-data-in-csv-format) durch.

## <a name="use-the-exact-data-match-schema-and-sensitive-information-type-pattern-wizard"></a>Verwenden Sie den Assistenten für das Schema für exakte Datenübereinstimmung und Muster vertraulicher Informationstypen

1. Wechseln Sie im Microsoft 365 Compliance Center Ihres Mandaten zu **Datenklassifizierung** > **Genaue Datenübereinstimmung**.

2. Wählen Sie **EDM-Schema erstellen**, um das Flyout des Assistenten für die Schema-Konfiguration zu öffnen.

![Flyout des Assistenten für die Erstellung der EDM-Schema-Konfiguration](../media/edm-schema-wizard-1.png)

3. Geben Sie einen geeigneten **Namen** und eine **Beschreibung** ein.

4. Wählen Sie **Trennzeichen und Satzzeichen für alle Schemafelder ignorieren**, wenn Sie dieses Verhalten wünschen. Weitere Informationen zum Konfigurieren von EDM zum Ignorieren von Groß- und Kleinschreibung oder Trennzeichen finden Sie unter [Erstellen eines benutzerdefinierten vertraulichen Informationstyps mit auf EDM (genaue Datenübereinstimmung) basierender Klassifizierung](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md).

5. Geben Sie die gewünschten Werte ein für Ihr **Schemafeld #1** und fügen Sie wenn notwendig weitere Felder ein. 

> [!IMPORTANT]
> Mindestens eines, aber nicht mehr als fünf Ihrer Schemafelder müssen als durchsuchbar gekennzeichnet sein.

6. Wählen Sie Speichern aus. Ihr Schema wird jetzt aufgeführt sein.

7. Wählen Sie **Vertrauliche EDM-Informationstypen** und **Erstellen von vertraulichen EDM-Informationstypen**, um den Assistenten für die Konfigurations von vertraulichen Informationstypen zu öffnen.

8. Wählen Sie **Auswahl eines bestehenden EDM-Schemas** und wählen Sie dann das Schema aus, das Sie in den Schritten 2–6 der Liste erstellt haben.

9. Wählen Sie **Weiter** und dann **Muster erstellen**.

10. Wählen Sie das **Konfidenzniveau** und das **Primäre Element** aus.  Weitere Informationen zum Konfigurieren eines Musters finden Sie unter [Erstellen eines vertraulichen Informationstyps im Compliance-Center](create-a-custom-sensitive-information-type.md)

11.  Wählen Sie den **Vertraulicher Informationstyp des primären Elementes**, um ihn zuzuordnen. Weitere Informationen über die verfügbaren vertraulichen Informationstypen finden Sie unter [Entitätsdefinitionen für vertrauliche Informationstypen](sensitive-information-type-entity-definitions.md).

12. Klicken Sie auf **Fertig**.

13. Wählen Sie ihre gewünschten **Konfidenzniveau und Zeichennähe**.  Dies wird der Standardwert sein für sämtliche vertraulichen EDM-Informationstypen

13. Wählen Sie **Muster erstellen** aus, wenn Sie zusätzliche Muster für Ihre vertraulichen EDM-Informationstypen erstellen wollen.

14. Wählen Sie **Weiter** und geben Sie einen **Namen** und eine **Beschreibung für Administratoren** ein.

15. Überprüfen Sie und wählen Sie dann **Übermitteln** aus.

Sie können ein Muster für vertrauliche Informationstypen löschen oder bearbeiten, indem Sie es auswählen, wodurch die Steuerelemente für das Löschen und Bearbeiten angezeigt werden.

> [!IMPORTANT]
> Wenn Sie ein Schema entfernen möchten, dieses aber bereits mit einem vertraulichen EDM-Informationstyp verbunden ist, dann müssen Sie zuerst den vertraulichen EDM-Informationstyp löschen, um das Schema löschen zu können.

## <a name="post-steps"></a>Nachbearbeitungsschritte

Nachdem Sie diesen Assistenten für die Erstellung der EDM-Schema- und -Musterdateien (Regelpaket) verwendet haben, müssen Sie trotzdem noch die Schritte in [Teil 2: Hashing und Hochladen der vertraulichen Daten](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md#part-2-hash-and-upload-the-sensitive-data) durchführen, bevor Sie den benutzerdefinierten vertraulichen EDM-Informationstyp verwenden können.