---
title: Exchange Admin Center in eigenständigen EoP
f1.keywords:
- NOCSH
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
description: Erfahren Sie mehr über die Webverwaltungsoberfläche in eigenständigen Exchange Online Schutz (EoP).
ms.openlocfilehash: 378754f2565604236f7ac33e471d1f991238d304
ms.sourcegitcommit: 93c0088d272cd45f1632a1dcaf04159f234abccd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/12/2020
ms.locfileid: "44209731"
---
# <a name="exchange-admin-center-in-standalone-eop"></a>Exchange Admin Center in eigenständigen EoP

Das Exchange Admin Center (EAC) ist eine webbasierte Verwaltungskonsole für eigenständige Exchange Online Schutz (EoP).

Suchen Sie die Exchange Online-Version dieses Themas? Weitere Informationen finden Sie unter [Exchange admin center in Exchange Online](https://docs.microsoft.com/exchange/exchange-admin-center).

## <a name="open-the-eac-in-eop"></a>Öffnen der Exchange-Verwaltungskonsole in EoP

Eigenständige EoP-Kunden können mithilfe der folgenden Methoden auf die Exchange-Verwaltungskonsole zugreifen:

- **Aus dem Microsoft 365 Admin Center**:

  1. Wechseln Sie zu, <https://admin.microsoft.com> und klicken Sie auf **Alle anzeigen**.

     ![Klicken Sie im Microsoft 365 Admin Center auf alle anzeigen.](../../media/m365-center-show-all.png)

  2. Klicken Sie im angezeigten Abschnitt **Admin Centers** auf **alle Admin Center**.

     ![Klicken Sie auf alle Admin Center im Microsoft 365 Admin Center](../../media/m365-center-select-all-admin-centers.png)

  3. Klicken Sie auf der Seite **alle Admin Center** , die angezeigt wird, auf **Exchange Online Schutz**.

- Wechseln Sie direkt zu `https://admin.protection.outlook.com/ecp/` .

## <a name="common-user-interface-elements-in-the-eac-in-eop"></a>Allgemeine Elemente der Benutzeroberfläche in der Exchange-Verwaltungskonsole in EoP

In diesem Abschnitt werden die Elemente der Benutzeroberfläche der Exchange-Verwaltungskonsole beschrieben.

![EoP-Admincenter](../../media/EOP-AdminCenter.png)

### <a name="feature-pane"></a>Featurebereich

Dies ist die erste Navigationsebene für die meisten Aufgaben, die Sie in der Exchange-Verwaltungskonsole ausführen. Der Featurebereich ist nach Funktionsbereichen organisiert.

- **Recipients**: Hier werden Gruppen und externe Kontakte angezeigt.

- **Berechtigungen**: Hier können Sie Administratorrollen verwalten.

- **Compliance-Verwaltung**: Hier finden Sie den Administrator-Rollengruppen Bericht und den Bericht admin-Überwachungsprotokoll.

- **Schutz**: Hier können Sie Antischadsoftware-Richtlinien, die standardmäßige Verbindungsfilter Richtlinie und DKIM verwalten.

  > [!NOTE]
  > Sie sollten Antischadsoftware-Richtlinien und die standardmäßige Verbindungsfilter Richtlinie im Security & Compliance Center verwalten. Weitere Informationen finden Sie unter [configure Anti-Malware Policies in EoP](configure-anti-malware-policies.md) und [Konfigurieren der Verbindungsfilterung in EoP](configure-the-connection-filter-policy.md).

- **Nachrichtenfluss**: Hier können Sie Nachrichtenfluss Regeln (auch bekannt als Transportregeln), akzeptierte Domänen und Connectors verwalten sowie den Weg zur Ausführung der Nachrichtenablaufverfolgung.

- **Hybrid**: Dies ist der Ort, an dem Sie den [Assistenten für die Hybrid Konfiguration](https://docs.microsoft.com/Exchange/hybrid-configuration-wizard)ausführen können und auf dem Sie das [Exchange Online-PowerShell-Modul](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/mfa-connect-to-exchange-online-powershell)installieren können.

### <a name="tabs"></a>Registerkarten

Die Registerkarten sind Ihre zweite Ebene der Navigation. Alle Featurebereiche enthalten verschiedene Registerkarten, die jeweils ein Feature repräsentieren.

### <a name="toolbar"></a>Symbolleiste

Für die meisten Registerkarten wird eine Symbolleiste angezeigt, nachdem Sie auf sie geklickt haben. Die Symbolleiste enthält Symbole, die jeweils eine bestimmte Aktion auslösen. Die folgende Tabelle beschreibt die Symbole und deren Aktionen.

||||
|---|---|---|
|**Symbol**|**Name**|**Action**|
|![Hinzufügen (Symbol)](../../media/ITPro-EAC-AddIcon.gif)|Hinzufügen, Neu|Über dieses Symbol können Sie ein neues Objekt erstellen. Bei einigen dieser Symbole gibt es einen dazugehörigen nach unten zeigenden Pfeil, auf den Sie klicken können, um weitere Objekte anzuzeigen, die Sie erstellen können.|
|![Bearbeitungssymbol](../../media/ITPro-EAC-EditIcon.gif)|Bearbeiten|Über dieses Symbol können Sie ein Objekt bearbeiten.|
|![Löschen (Symbol)](../../media/ITPro-EAC-DeleteIcon.gif)|Delete|Über dieses Symbol können Sie ein Objekt löschen. Bei einigen Löschsymbolen gibt es einen nach unten zeigenden Pfeil, auf den Sie zum Einblenden weiterer Optionen klicken können.|
|![Suchen (Symbol)](../../media/ITPro-EAC-.gif)|Suche|Über dieses Symbol können Sie ein Suchfeld öffnen, in das Sie den Suchbegriff für ein zu suchendes Objekt eingeben können.|
|![Aktualisieren (Symbol)](../../media/ITPro-EAC-RefreshIcon.gif)|Aktualisieren|Über dieses Symbol können Sie die Listenansicht aktualisieren.|
|![Weitere Optionen (Symbol)](../../media/ITPro-EAC-MoreOptionsIcon.gif)|Weitere Optionen|Über dieses Symbol können Sie mehrere Aktionen anzeigen, die Sie auf die Objekte dieser Registerkarte anwenden können. Wenn Sie z. B. unter **Empfänger \> Benutzer** auf dieses Symbol klicken, wird die Option **Erweiterte Suche** angezeigt.  |
|![NACH-OBEN-TASTE (Symbol)](../../media/ITPro-EAC-UpArrowIcon.gif)![NACH-UNTEN-TASTE (Symbol)](../../media/ITPro-EAC-DownArrowIcon.gif)|Pfeil nach oben und Pfeil nach unten|Mithilfe dieser Symbole können Sie die Priorität eines Objekts nach oben oder unten verschieben.|
|![Entfernen (Symbol)](../../media/ITPro-EAC-RemoveIcon.gif)|Entfernen|Über dieses Symbol können Sie Objekte aus einer Liste entfernen.|
|

### <a name="list-view"></a>Listenansicht

Wenn Sie auf eine Registerkarte klicken, sehen Sie in den meisten Fällen eine Listenansicht. In der Listenansicht der Exchange-Verwaltungskonsole können ungefähr 10.000 Objekte angezeigt werden. Darüber hinaus können Sie die Ergebnisse seitenweise anzeigen.

### <a name="details-pane"></a>Bereich "Details"

Wenn Sie in der Listenansicht ein Objekt auswählen, werden Informationen zu diesem Objekt im Detailbereich angezeigt. In einigen Fällen enthält der Detailbereich Verwaltungsaufgaben.

### <a name="me-tile-and-help"></a>Ich-Kachel und Hilfe

Über die **Ich**-Kachel können Sie sich bei der Exchange-Verwaltungskonsole abmelden und als ein anderer Benutzer anmelden. Über das Dropdownmenü der **Hilfe**![Hilfe (Symbol)](../../media/ITPro-EAC-HelpIcon.gif) können Sie folgende Aktionen ausführen:

- **Hilfe**: Klicken Sie auf ![ Hilfesymbol ](../../media/ITPro-EAC-HelpIcon.gif) , um den Inhalt der Online Hilfe anzuzeigen.

- **Feedback**: hinterlassen Sie Feedback.

- **Community**: Stellen Sie eine Frage für Find Answers in den Community-Foren bereit.

- **Hilfe Blase deaktivieren**: in der Hilfe-Sprechblase wird Kontexthilfe für Felder angezeigt, wenn Sie ein Objekt erstellen oder bearbeiten. Sie können die Hilfe Blase deaktivieren oder aktivieren, wenn Sie deaktiviert wurde.

- **Befehlsprotokollierung anzeigen**: Es wird ein neues Fenster geöffnet, in dem die entsprechenden PowerShell-Befehle basierend auf den in der Exchange-Verwaltungskonsole konfigurierten angezeigt werden.

## <a name="supported-browsers"></a>Unterstützte Browser

Für eine optimale Nutzung des EAC sollten Sie immer die neuesten Browser, Office-Clients und Apps verwenden. Zudem wird empfohlen, dass Sie Softwareupdates installieren, sobald sie verfügbar werden. Weitere Informationen zu den unterstützten Browsern und Systemanforderungen für den Dienst finden Sie unter [System Requirements for Office](https://products.office.com/office-system-requirements).

## <a name="supported-languages"></a>Unterstützte Sprachen

Die folgenden Sprachen werden für die Exchange-Verwaltungskonsole in eigenständigen EoP unterstützt und zur Verfügung gestellt.

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
