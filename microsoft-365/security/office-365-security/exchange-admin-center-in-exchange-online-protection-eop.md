---
title: Exchange Admin Center in EOP als eigenständige Lösung
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: overview
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 97921f0e-832f-40c7-b56d-414faede5191
ms.collection:
- M365-security-compliance
description: Erfahren Sie mehr über die Webverwaltungsschnittstelle in eigenständigem Exchange Online Protection (EOP).
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: ab834d14673370a39e148aefa568591ff4c50b8f
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50916994"
---
# <a name="exchange-admin-center-in-standalone-eop"></a>Exchange Admin Center in EOP als eigenständige Lösung

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gilt für**
-  [Exchange Online Protection eigenständig](exchange-online-protection-overview.md)

Das Exchange Admin Center (EAC) ist eine webbasierte Verwaltungskonsole für eigenständige Exchange Online Protection (EOP).

Suchen Sie die Exchange Online-Version dieses Themas? Weitere Informationen finden Sie unter [Exchange admin center in Exchange Online](/exchange/exchange-admin-center).

## <a name="open-the-eac-in-eop"></a>Öffnen der EAC in EOP

Eigenständige EOP-Kunden können mithilfe der folgenden Methoden auf die EAC zugreifen:

- **Aus dem Microsoft 365 Admin Center**:

  1. Wechseln Sie <https://admin.microsoft.com> zu, und klicken **Sie auf Alle anzeigen.**

     ![Klicken Sie im Microsoft 365 Admin Center auf Alle anzeigen](../../media/m365-center-show-all.png)

  2. Klicken Sie **im angezeigten** Abschnitt Admin Center auf **Alle Admin Center**.

     ![Klicken Sie im Microsoft 365 Admin Center auf Alle Admin Center](../../media/m365-center-select-all-admin-centers.png)

  3. Klicken Sie **auf der** angezeigten Seite Alle Admin Center auf Exchange **Online Protection**.

- Wechseln Sie direkt zu `https://admin.protection.outlook.com/ecp/` .

## <a name="common-user-interface-elements-in-the-eac-in-eop"></a>Allgemeine Benutzeroberflächenelemente in der EAC in EOP

In diesem Abschnitt werden die Elemente der Benutzeroberfläche der Exchange-Verwaltungskonsole beschrieben.

![Das Exchange Admin Center in Exchange Online Protection](../../media/EOP-AdminCenter.png)

### <a name="feature-pane"></a>Featurebereich

Dies ist die erste Navigationsebene für die meisten Aufgaben, die Sie in der Exchange-Verwaltungskonsole ausführen. Der Featurebereich ist nach Funktionsbereichen organisiert.

- **Empfänger:** Hier werden Gruppen und externe Kontakte angezeigt.

- **Berechtigungen**: Hier verwalten Sie Administratorrollen.

- **Complianceverwaltung:** Hier finden Sie den Administratorrollegruppenbericht und den Administrator-Überwachungsprotokollbericht.

- **Schutz**: Hier können Sie An malware-Richtlinien, die Standardmäßige Verbindungsfilterrichtlinie und DKIM verwalten.

  > [!NOTE]
  > Sie sollten Anti-Malware-Richtlinien und die Standardmäßige Verbindungsfilterrichtlinie im Security & Compliance Center verwalten. Weitere Informationen finden Sie unter [Configure anti-malware policies in EOP](configure-anti-malware-policies.md) und [Configure connection filtering in EOP](configure-the-connection-filter-policy.md).

- **Nachrichtenfluss:** Hier verwalten Sie Nachrichtenflussregeln (auch als Transportregeln bezeichnet), akzeptierte Domänen und Connectors sowie nachrichtenablaufverfolgung.

- **Hybrid:** Hier können Sie den Assistenten für die [Hybridkonfiguration](/Exchange/hybrid-configuration-wizard)ausführen und das [Exchange Online PowerShell-Modul installieren.](/powershell/exchange/mfa-connect-to-exchange-online-powershell)

### <a name="tabs"></a>Registerkarten

Die Registerkarten sind Ihre zweite Ebene der Navigation. Alle Featurebereiche enthalten verschiedene Registerkarten, die jeweils ein Feature repräsentieren.

### <a name="toolbar"></a>Symbolleiste

Für die meisten Registerkarten wird eine Symbolleiste angezeigt, nachdem Sie auf sie geklickt haben. Die Symbolleiste enthält Symbole, die jeweils eine bestimmte Aktion auslösen. Die folgende Tabelle beschreibt die Symbole und deren Aktionen.

****

|Symbol|Name|Aktion|
|---|---|---|
|![Hinzufügen (Symbol)](../../media/ITPro-EAC-AddIcon.gif)|Hinzufügen, Neu|Über dieses Symbol können Sie ein neues Objekt erstellen. Bei einigen dieser Symbole gibt es einen dazugehörigen nach unten zeigenden Pfeil, auf den Sie klicken können, um weitere Objekte anzuzeigen, die Sie erstellen können.|
|![Bearbeitungssymbol](../../media/ITPro-EAC-EditIcon.gif)|Bearbeiten|Über dieses Symbol können Sie ein Objekt bearbeiten.|
|![Löschen (Symbol)](../../media/ITPro-EAC-DeleteIcon.gif)|Löschen|Über dieses Symbol können Sie ein Objekt löschen. Bei einigen Löschsymbolen gibt es einen nach unten zeigenden Pfeil, auf den Sie zum Einblenden weiterer Optionen klicken können.|
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

Über die **Ich**-Kachel können Sie sich bei der Exchange-Verwaltungskonsole abmelden und als ein anderer Benutzer anmelden. Im **Dropdownmenü Hilfesymbol** ![ können Sie die folgenden Aktionen ](../../media/ITPro-EAC-HelpIcon.gif) ausführen:

- **Hilfe**: Klicken Sie auf das ![Hilfesymbol](../../media/ITPro-EAC-HelpIcon.gif), damit der Inhalt der Onlinehilfe angezeigt wird.
- **Feedback:** Feedback hinterlassen.
- **Community**: Stellen Sie eine Frage, um Antworten in den Communityforen zu finden.
- **Hilfe-Sprechblase deaktivieren**: In der Hilfe-Sprechblase wird Kontexthilfe für Felder angezeigt, wenn Sie ein Objekt erstellen oder bearbeiten. Sie können die Hilfeblase deaktivieren oder aktivieren, wenn sie deaktiviert wurde.
- **Befehlsprotokollierung anzeigen:** Es wird ein neues Fenster geöffnet, in dem die entsprechenden PowerShell-Befehle basierend auf den in der EAC konfigurierten Einstellungen angezeigt werden.

## <a name="supported-browsers"></a>Unterstützte Browser

Für eine optimale Nutzung des EAC sollten Sie immer die neuesten Browser, Office-Clients und Apps verwenden. Zudem wird empfohlen, dass Sie Softwareupdates installieren, sobald sie verfügbar werden. Weitere Informationen zu den unterstützten Browsern und Systemanforderungen für den Dienst finden Sie unter [System requirements for Office](https://products.office.com/office-system-requirements).

## <a name="supported-languages"></a>Unterstützte Sprachen

Die folgenden Sprachen werden für die EAC im eigenständigen EOP unterstützt und verfügbar.

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