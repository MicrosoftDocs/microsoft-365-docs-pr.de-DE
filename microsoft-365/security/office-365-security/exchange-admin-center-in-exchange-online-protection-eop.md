---
title: Exchange Admin Center in Exchange Online Protection
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 97921f0e-832f-40c7-b56d-414faede5191
ms.collection:
- M365-security-compliance
description: Die Exchange-Verwaltungskonsole (EAC) ist die webbasierte Verwaltungskonsole für Microsoft Exchange Online Protection (EOP).
ms.openlocfilehash: 6ef800b9f440f67d45f3eaa08b4731989fcf2652
ms.sourcegitcommit: 2468bcb01625f97a322459814d81b9faad717859
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/05/2019
ms.locfileid: "39871861"
---
# <a name="exchange-admin-center-in-exchange-online-protection"></a>Exchange Admin Center in Exchange Online Protection

Die Exchange-Verwaltungskonsole (EAC) ist die webbasierte Verwaltungskonsole für Microsoft Exchange Online Protection (EOP).

Suchen Sie die Exchange Server-Version dieses Themas? Weitere Informationen finden Sie unter [Exchange Admin Center in Exchange Server](https://docs.microsoft.com/exchange/architecture/client-access/exchange-admin-center).

Suchen Sie die Exchange Online-Version dieses Themas? Weitere Informationen finden Sie unter [Exchange admin center in Exchange Online](https://docs.microsoft.com/exchange/exchange-admin-center).

## <a name="accessing-the-eac"></a>Zugreifen auf die Exchange-Verwaltungskonsole

In den meisten Fällen greifen EoP-Kunden über das Microsoft 365 Admin Center auf die Exchange-Verwaltungskonsole zu. Einen Link zu EOP finden Sie im Dropdownmenü der **Admin**-Kachel, die sich neben der **Ich**-Kachel befindet. Klicken Sie auf die **Admin**-Kachel, und wählen Sie im Dropdownmenü **Exchange Online Protection**, um die Exchange-Verwaltungskonsole aufzurufen.

Sie können auch über den folgenden URL direkt auf das EAC-Zeichen auf der Seite zugreifen: `https://admin.protection.outlook.com/ecp/<companydomain>`. Beispiel: `https://admin.protection.outlook.com/ecp/contoso.onmicrosoft.com`. Nachdem Sie Ihre Benutzeranmeldeinformationen eingegeben haben, gelangen Sie direkt zur Exchange-Verwaltungskonsole.

## <a name="common-user-interface-elements-in-the-eac"></a>Allgemeine Elemente der Benutzeroberfläche in der Exchange-Verwaltungskonsole

In diesem Abschnitt werden die Elemente der Benutzeroberfläche der Exchange-Verwaltungskonsole beschrieben.

![EoP-Admincenter](../media/EOP-AdminCenter.png)

### <a name="feature-pane"></a>Featurebereich

Dies ist die erste Navigationsebene für die meisten Aufgaben, die Sie in der Exchange-Verwaltungskonsole ausführen. Der Featurebereich ist nach Funktionsbereichen organisiert.

1. **Recipients**: Dies ist der Ort, an dem Sie interne Benutzer und externe Kontakte anzeigen können.

2. **Berechtigungen**: Hier können Sie Administratorrollen verwalten.

3. **Compliance-Verwaltung**: Hier finden Sie Überwachungsprotokolle und Berichte wie den Administrator-Rollengruppen Bericht.

4. **Schutz**: Hier können Sie Antischadsoftware-und Antispamschutz für Ihre Organisation sowie Nachrichten in Quarantäne verwalten.

5. **Nachrichtenfluss**: Hier können Sie Regeln, akzeptierte Domänen und Connectors verwalten sowie die Nachrichtenablaufverfolgung durchführen.

### <a name="tabs"></a>Registerkarten

Die Registerkarten sind Ihre zweite Ebene der Navigation. Alle Featurebereiche enthalten verschiedene Registerkarten, die jeweils ein Feature repräsentieren.

### <a name="toolbar"></a>Symbolleiste

Für die meisten Registerkarten wird eine Symbolleiste angezeigt, nachdem Sie auf sie geklickt haben. Die Symbolleiste enthält Symbole, die jeweils eine bestimmte Aktion auslösen. Die folgende Tabelle beschreibt die Symbole und deren Aktionen.

|**Symbol**|**Name**|**Action**|
|:-----|:-----|:-----|
|![Hinzufügen (Symbol)](../media/ITPro-EAC-AddIcon.gif)|Hinzufügen, Neu|Über dieses Symbol können Sie ein neues Objekt erstellen. Bei einigen dieser Symbole gibt es einen dazugehörigen nach unten zeigenden Pfeil, auf den Sie klicken können, um weitere Objekte anzuzeigen, die Sie erstellen können.|
|![Bearbeitungssymbol](../media/ITPro-EAC-EditIcon.gif)|Bearbeiten|Über dieses Symbol können Sie ein Objekt bearbeiten.|
|![Löschen (Symbol)](../media/ITPro-EAC-DeleteIcon.gif)|Delete|Über dieses Symbol können Sie ein Objekt löschen. Bei einigen Löschsymbolen gibt es einen nach unten zeigenden Pfeil, auf den Sie zum Einblenden weiterer Optionen klicken können.|
|![Suchen (Symbol)](../media/ITPro-EAC-.gif)|Suche|Über dieses Symbol können Sie ein Suchfeld öffnen, in das Sie den Suchbegriff für ein zu suchendes Objekt eingeben können.|
|![Aktualisieren (Symbol)](../media/ITPro-EAC-RefreshIcon.gif)|Aktualisieren|Über dieses Symbol können Sie die Listenansicht aktualisieren.|
|![Weitere Optionen (Symbol)](../media/ITPro-EAC-MoreOptionsIcon.gif)|Weitere Optionen|Über dieses Symbol können Sie mehrere Aktionen anzeigen, die Sie auf die Objekte dieser Registerkarte anwenden können. Wenn Sie z. B. unter **Empfänger \> Benutzer** auf dieses Symbol klicken, wird die Option **Erweiterte Suche** angezeigt.  |
|![NACH-OBEN-TASTE (Symbol)](../media/ITPro-EAC-UpArrowIcon.gif)![NACH-UNTEN-TASTE (Symbol)](../media/ITPro-EAC-DownArrowIcon.gif)|Pfeil nach oben und Pfeil nach unten|Mithilfe dieser Symbole können Sie die Priorität eines Objekts nach oben oder unten verschieben.|
|![Entfernen (Symbol)](../media/ITPro-EAC-RemoveIcon.gif)|Entfernen|Über dieses Symbol können Sie Objekte aus einer Liste entfernen.|

### <a name="list-view"></a>Listenansicht

Wenn Sie auf eine Registerkarte klicken, sehen Sie in den meisten Fällen eine Listenansicht. In der Listenansicht der Exchange-Verwaltungskonsole können ungefähr 10.000 Objekte angezeigt werden. Darüber hinaus können Sie die Ergebnisse seitenweise anzeigen.

### <a name="details-pane"></a>Bereich "Details"

Wenn Sie in der Listenansicht ein Objekt auswählen, werden Informationen zu diesem Objekt im Detailbereich angezeigt. In einigen Fällen enthält der Detailbereich Verwaltungsaufgaben.

### <a name="me-tile-and-help"></a>Ich-Kachel und Hilfe

Über die **Ich**-Kachel können Sie sich bei der Exchange-Verwaltungskonsole abmelden und als ein anderer Benutzer anmelden. Über das Dropdownmenü der **Hilfe**![Hilfe (Symbol)](../media/ITPro-EAC-HelpIcon.gif) können Sie folgende Aktionen ausführen:

1. **Hilfe**: Klicken ![Sie auf](../media/ITPro-EAC-HelpIcon.gif) Hilfesymbol, um den Inhalt der Online Hilfe anzuzeigen.

2. **Hilfe Blase deaktivieren**: in der Hilfe-Sprechblase wird Kontexthilfe für Felder angezeigt, wenn Sie ein Objekt erstellen oder bearbeiten. Sie können die Hilfe Blase deaktivieren oder aktivieren, wenn Sie deaktiviert wurde.

3. **Copyright**: Klicken Sie auf diesen Link, um den Copyright-Hinweis für Exchange Online Protection zu lesen.

4. **Privacy**: Klicken Sie hier, um die Datenschutzrichtlinie für Exchange Online Schutz zu lesen.

## <a name="supported-browsers"></a>Unterstützte Browser

Für eine optimale Nutzung des EAC sollten Sie immer die neuesten Browser, Office-Clients und Apps verwenden. Zudem wird empfohlen, dass Sie Softwareupdates installieren, sobald sie verfügbar werden. Weitere Informationen zu den unterstützten Browsern und zu den Systemanforderungen für den Dienst finden Sie unter [Office 365-Systemanforderungen](https://go.microsoft.com/fwlink/p/?LinkID=402699).

## <a name="supported-languages-in-eop"></a>Unterstützte Sprachen in EOP

Die folgenden Sprachen werden für Exchange Online Protection unterstützt und zur Verfügung gestellt.

- Amharisch

- Arabisch

- Baskisch (Baskisch)

- Bengali (Indien)

- Bulgarisch

- Katalanisch

- Chinesisch (vereinfacht)

- Chinesisch (traditionell)

- Kroatisch

- Tschechisch

- Dänisch

- Niederländisch

- Niederländisch

- Englisch

- Estnisch

- Filipino (Philippinen)

- Finnisch

- Französisch

- Galizisch

- Deutsch

- Griechisch

- Gujarati

- Hebräisch

- Hindi

- Ungarisch

- Isländisch

- Indonesisch

- Italienisch

- Japanisch

- Kannada

- Kasachisch

- Kisuaheli

- Koreanisch

- Lettisch

- Litauisch

- Malaiisch (Brunei Darussalam)

- Malaiisch (Malaysia)

- Malayalam

- Marathi

- Norwegisch (Bokmål)

- Norwegisch (Nynorsk)

- Odia

- Persisch

- Polnisch

- Portugiesisch (Brasilien)

- Portugiesisch (Portugal)

- Rumänisch

- Russisch

- Serbisch (Kyrillisch, Serbien)

- Serbisch (Lateinisch)

- Slowakisch

- Slowenisch

- Spanisch

- Schwedisch

- Tamil

- Telugu

- Thailändisch

- Türkisch

- Ukrainisch

- Urdu

- Vietnamesisch

- Walisisch


