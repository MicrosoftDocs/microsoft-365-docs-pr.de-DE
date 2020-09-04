---
title: Vorbereiten der Suchergebnisse für Advanced eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: how-to
f1_keywords:
- ms.o365.cc.CustomizeExportWithZoom
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: 0b6fac2d-8627-4b05-9df0-03609db6248b
description: In diesem Artikel erfahren Sie, wie Sie die Ergebnisse einer Inhaltssuche im Security & Compliance Center zur weiteren Analyse mit dem erweiterten eDiscovery-Tool vorbereiten.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: b403987c39d1ddcc1f22fd0abbeba85e60591414
ms.sourcegitcommit: 9ce9001aa41172152458da27c1c52825355f426d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/03/2020
ms.locfileid: "47358567"
---
# <a name="prepare-search-results-for-advanced-ediscovery-classic"></a>Vorbereiten der Suchergebnisse für Advanced eDiscovery (classic)

> [!IMPORTANT]
> Während wir weiterhin in neuere Versionen von Advanced eDiscovery investieren, kündigen wir jetzt die Deaktivierung von Advanced eDiscovery (auch bekannt als *Advanced eDiscovery (Classic)* oder *Advanced eDiscovery v1.0*) an. Wenn Sie noch mit Advanced eDiscovery v1.0 arbeiten, wechseln Sie so bald wie möglich zu [Advanced eDiscovery v2.0](overview-ediscovery-20.md) (auch bekannt als *Advanced eDiscovery-Lösung in Microsoft 365*). Advanced eDiscovery 2.0 enthält ähnliche Funktionen wie Advanced eDiscovery v1.0, bietet aber auch viele neue Funktionen wie z. B. Verwahrerverwaltung, Kommunikationsverwaltung und Prüfungssätze. Um mehr über die Deaktivierung von Advanced eDiscovery v1.0 zu erfahren, siehe [Deaktivierung von veralteten eDiscovery-Tools](legacy-ediscovery-retirement.md#advanced-ediscovery-v10).  

Nachdem eine Suche, die einem eDiscovery-Fall im Security & Compliance Center zugeordnet ist, erfolgreich ausgeführt wurde, können Sie die Suchergebnisse zur weiteren Analyse mit Advanced eDiscovery vorbereiten, mit der Sie große, unstrukturierte Datasets analysieren und die für einen rechtlichen Fall relevante Datenmenge reduzieren können. Zu den erweiterten eDiscovery-Features gehören:
  
- **Optische Zeichenerkennung** – Wenn Sie Suchergebnisse für Advanced eDiscovery vorbereiten, extrahiert die optische Zeichenerkennung (OCR)-Funktion automatisch Text aus Bildern und enthält diese mit den Suchergebnissen, die in Advanced eDiscovery for Analysis geladen werden. OCR wird für lose Dateien, E-Mail-Anlagen und eingebettete Bilder unterstützt. Auf diese Weise können Sie die Textanalyse Funktionen von Advanced eDiscovery (Near-Duplicates, e-Mail-Threading, Themes und Predictive Coding) auf den Textinhalt in Bilddateien anwenden. Die erweiterte eDiscovery-OCR unterstützt die folgenden Formate für Bilddateien:

    - GIF
    - JPEG
    - JPG
    - PNG
    - TIFF
    
- **Erkennung bei** gleichzeitigen Duplikaten-ermöglicht Ihnen eine effizientere Strukturierung ihrer Datenüberprüfung, sodass eine Person eine Gruppe ähnlicher Dokumente überprüft. Dadurch kann verhindert werden, dass mehrere Bearbeiter verschiedene Versionen desselben Dokuments anzeigen müssen. 
    
- **E-Mail-Threading** – unterstützt Sie bei der Identifizierung der eindeutigen Nachrichten in einem e-Mail-Thread, sodass Sie sich nur auf die neuen Informationen in jeder Nachricht konzentrieren können. In einem E-Mail-Thread enthält die zweite Nachricht die erste Nachricht. Analog dazu enthalten spätere Nachrichten alle vorherigen Nachrichten. E-Mail-Threading entfällt, dass alle Nachrichten in ihrer Gesamtheit in einem e-Mail-Thread überprüft werden müssen. 
    
- **Designs** – Sie erhalten wertvolle Einblicke in Ihre Daten, die sich über die Stichwortsuche hinaus erst restatistikieren. Designs unterstützen Untersuchungen, indem Sie verwandte Dokumente gruppieren, damit Sie die Dokumente im Kontext anzeigen können. Wenn Sie Designs verwenden, können Sie die verwandten Designs für eine Reihe von Dokumenten anzeigen, Überschneidungen bestimmen und dann Querschnitte verwandter Daten identifizieren. 
    
- **Predictive Coding** -ermöglicht es Ihnen, das System auf das zu Schulen, was Sie suchen, indem Sie Entscheidungen treffen können (unabhängig davon, ob etwas relevant ist oder nicht) für eine kleine Gruppe von Dokumenten. Advanced eDiscovery wendet dann das Lernen (basierend auf ihrer Anleitung) an, wenn alle Dokumente im Datensatz analysiert werden. Basierend auf diesem Lernmaterial bietet Advanced eDiscovery eine Relevanz-Rangfolge, sodass Sie entscheiden können, welche Dokumente überprüft werden sollen, je nachdem, welches Dokument am ehesten für den Fall relevant ist. 
    
- **Exportieren von Daten für Überprüfungs Anwendungen**  -Sie können Daten aus Advanced eDiscovery und Microsoft 365 exportieren, nachdem Sie Ihre Analyse abgeschlossen und das DataSet reduziert haben. Das Exportpaket enthält eine CSV-Datei, die die Eigenschaften aus den exportierten Inhalts-und Analyse Metadaten enthält. Dieses Exportpaket kann dann in eine eDiscovery-Überprüfungs Anwendung importiert werden. 
    
## <a name="get-licenses-and-permissions"></a>Abrufen von Lizenzen und Berechtigungen

- Um die Daten eines Benutzers mithilfe von Advanced eDiscovery zu analysieren, muss dem Benutzer (dem Verwalter der Daten) eine Office 365 E5-Lizenz zugewiesen werden. Alternativ können Benutzern mit einer Office 365 E1-oder E3-Lizenz eine erweiterte eDiscovery-eigenständige Lizenz zugewiesen werden. Administratoren und Compliance Officer, die Fällen zugeordnet sind, und Verwenden von Advanced eDiscovery zum Analysieren von Daten benötigen keine E5-Lizenz. 
    
- Sie müssen ein eDiscovery-Manager oder ein eDiscovery-Administrator im Security & Compliance Center sein, um Suchergebnisse für Advanced eDiscovery vorzubereiten. Ein eDiscovery-Manager ist ein Mitglied der Rollengruppe "eDiscovery-Manager". Ein eDiscovery-Administrator ist ebenfalls Mitglied der Rollengruppe "eDiscovery-Manager", ihm wurden jedoch zusätzliche Berechtigungen zugewiesen. Anweisungen zum Zuweisen von eDiscovery-Administrator Berechtigungen finden Sie unter Schritt 1 in [eDiscovery-Fällen](ediscovery-cases.md#step-1-assign-ediscovery-permissions-to-potential-case-members).
    
## <a name="step-1-prepare-search-results-for-advanced-ediscovery"></a>Schritt 1: Vorbereiten der Suchergebnisse für Advanced eDiscovery

Sie können die Ergebnisse einer Suche vorbereiten, die einem eDiscovery-Fall zugeordnet ist. Wenn Sie Suchergebnisse für Advanced eDiscovery vorbereiten, werden die Daten hochgeladen und temporär in einem eindeutigen Windows Azure-Speicherbereich in der Microsoft-Cloud gespeichert. An dieser Position extrahiert die OCR-Funktion Text aus Bildern in den Suchergebnissen. In [Schritt 2](#step-2-add-the-search-results-data-to-the-case-in-advanced-ediscovery)werden dieser Text und die anderen Suchergebnis Daten in den Fall in Advanced eDiscovery geladen.
  
1. Klicken Sie im Security & Compliance Center auf **eDiscovery** \> **eDiscovery** , um die Liste der Fälle in Ihrer Organisation anzuzeigen. 
    
2. Klicken Sie neben dem Fall, für den Sie Suchergebnisse für die Analyse in Advanced eDiscovery vorbereiten möchten, auf **Öffnen** . 
    
3. Klicken Sie auf der **Start** Seite für den Fall auf **Suche**, und wählen Sie dann die Suche aus.
    
4. Klicken Sie im Detailbereich unter **Ergebnisse mit erweiterter eDiscovery analysieren**auf **Ergebnisse zur Analyse vorbereiten**.
    
    > [!NOTE]
    > Wenn die Suchergebnisse älter als 7 Tage sind, werden Sie aufgefordert, die Suchergebnisse zu aktualisieren. 
  
5. Gehen Sie auf der Seite **Ergebnisse für Analyse vorbereiten** folgendermaßen vor:  
    
    - Wählen Sie aus, ob indizierte Elemente, indexierte und nicht indizierte Elemente oder nur nicht indizierte Elemente zur Analyse in Advanced eDiscovery vorbereitet werden sollen.
    
    - Legen Sie fest, ob alle Versionen von Dokumenten in SharePoint einbezogen werden sollen, die die Suchkriterien erfüllen. Diese Option wird nur dann angezeigt, wenn die Inhaltsquellen für die Suche Websites umfassen.
    
    - Geben Sie an, ob eine Benachrichtigung an eine Person gesendet (oder kopiert) werden soll, wenn der Vorbereitungsprozess abgeschlossen ist und die Daten für die Verarbeitung in Advanced eDiscovery bereit sind.
    
6. Klicken Sie auf **Vorbereiten**.
    
    Die Suchergebnisse werden mit Advanced eDiscovery für die Analyse vorbereitet.
    
7. Klicken Sie im Detailbereich auf **Vorbereitungsstatus überprüfen** , um Informationen zum Vorbereitungsprozess anzuzeigen. Wenn der Vorbereitungsprozess abgeschlossen ist, können Sie den Fall in Advanced eDiscovery aufrufen, um die Daten für die Analyse zu verarbeiten. 
    
## <a name="step-2-add-the-search-results-data-to-the-case-in-advanced-ediscovery"></a>Schritt 2: Hinzufügen der Suchergebnis Daten zu dem Fall in Advanced eDiscovery
<a name="step2"> </a>

Wenn die Vorbereitung abgeschlossen ist, besteht der nächste Schritt darin, zu Advanced eDiscovery zu wechseln und die Suchergebnis Daten (die in einen Azure-Speicherbereich in der Microsoft-Cloud hochgeladen wurden) in den Fall in Advanced eDiscovery zu laden. Wie bereits erläutert, müssen Sie für den Zugriff auf Advanced eDiscovery ein eDiscovery-Administrator im Security & Compliance Center oder ein Administrator in Advanced eDiscovery sein.
  
> [!NOTE]
> Je nach der Größe der Ergebnisse der eDiscovery-Suche variiert die Zeit, die für die Daten aus dem Security & Compliance Center zur Verfügung steht, um einem Fall in Advanced eDiscovery hinzuzufügen. 
  
1. Klicken Sie im Security & Compliance Center auf **eDiscovery** \> **eDiscovery** , um die Liste der Fälle in Ihrer Organisation anzuzeigen. 
    
2. Klicken Sie neben dem Fall, in dem Sie Daten laden möchten in Advanced eDiscovery auf **Öffnen** . 
    
3. Klicken Sie auf der Seite **Start** für den Fall auf **Zu Advanced eDiscovery**. 
    
    ![Klicken Sie auf zu Erweiterte eDiscovery wechseln, um die Anfrage in Advanced eDiscovery zu öffnen.](../media/8e34ba23-62e3-4e68-a530-b6ece39b54be.png)
  
    Die **Verbindung mit der erweiterten eDiscovery** -Statusleiste wird angezeigt. Wenn Sie mit Advanced eDiscovery verbunden sind, wird auf der Seite Setup für den Fall eine Liste mit Containern angezeigt. 
    
    ![Der Fall wird in Advanced eDiscovery angezeigt.](../media/8036e152-70dc-4bb7-9379-61c1ed8326b4.png)
  
     Diese Container stellen die Suchergebnisse dar, die Sie für die Analyse in Advanced eDiscovery in Schritt 1 vorbereitet haben. Beachten Sie, dass der Name des Containers denselben Namen hat wie die Suche in dem Fall im Security & Compliance Center. Die Container in der Liste sind diejenigen, die Sie vorbereitet haben. Wenn ein anderer Benutzer Suchergebnisse für Advanced eDiscovery vorbereitet hat, werden die entsprechenden Container nicht in die Liste aufgenommen. 
    
4. Wenn Sie die Suchergebnis Daten aus einem Container in den Fall in Advanced eDiscovery laden möchten, wählen Sie einen Container aus, und klicken Sie dann auf **verarbeiten**.
    
## <a name="next-steps"></a>Nächste Schritte

Nachdem die Ergebnisse einer eDiscovery-Suche einem Fall hinzugefügt wurden, besteht der nächste Schritt in der Verwendung der erweiterten eDiscovery-Tools, um die Daten zu analysieren und den Inhalt zu identifizieren, der auf einen bestimmten Rechtsfall reagiert. Informationen zur Verwendung von Advanced eDiscovery finden Sie unter [Advanced eDiscovery (Classic)](office-365-advanced-ediscovery.md).
  
## <a name="more-information"></a>Weitere Informationen

Alle RMS-verschlüsselten e-Mail-Nachrichten, die in den Suchergebnissen enthalten sind, werden entschlüsselt, wenn Sie Sie für die Analyse in Advanced eDiscovery vorbereiten. Diese Entschlüsselungsfunktion ist für Mitglieder der eDiscovery-Manager-Rollengruppe standardmäßig aktiviert. Dies liegt daran, dass die Verwaltungsrolle "RMS Decrypt" dieser Rollengruppe zugewiesen ist. Beachten Sie beim Entschlüsseln von e-Mail-Nachrichten die folgenden Punkte:
  
- Derzeit umfasst diese Entschlüsselungsfunktion keine verschlüsselten Inhalte aus SharePoint und OneDrive für Unternehmen Websites. Nur RMS-verschlüsselte e-Mail-Nachrichten werden entschlüsselt, wenn Sie Sie exportieren.
    
- Wenn eine RMS-verschlüsselte e-Mail-Nachricht eine Anlage (beispielsweise ein Dokument oder eine andere e-Mail-Nachricht) enthält, die ebenfalls verschlüsselt ist, wird nur die e-Mail-Nachricht der obersten Ebene entschlüsselt.
    
- Wenn Sie verhindern müssen, dass eine Person RMS-verschlüsselte Nachrichten entschlüsselt, wenn Sie Suchergebnisse für die Analyse in Advanced eDiscovery vorbereiten, müssen Sie eine benutzerdefinierte Rollengruppe erstellen (durch Kopieren der integrierten eDiscovery-Manager-Rollengruppe) und dann die Verwaltungsrolle "RMS Decrypt" aus der benutzerdefinierten Rollengruppe entfernen. Fügen Sie dann die Person hinzu, die Nachrichten nicht als Mitglied der benutzerdefinierten Rollengruppe entschlüsseln soll.
