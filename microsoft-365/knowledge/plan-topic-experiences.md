---
title: Planen von Microsoft Viva Topics
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: nkokoye
audience: admin
ms.topic: article
ms.service: o365-administration
search.appverid: MET150
localization_priority: Normal
description: Erfahren Sie, wie Sie die Planung für Microsoft Viva Topics planen
ms.openlocfilehash: a407fd6e6919c3b85235e317e5ed3ff103607700
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/30/2021
ms.locfileid: "53229539"
---
# <a name="plan-for-microsoft-viva-topics"></a>Planen von Microsoft Viva Topics

Sie haben die Kontrolle darüber, wie Themen in Ihrer Organisation behandelt werden. Ihre Planungsentscheidungen für Themen stellen sicher, dass Ihren Benutzern qualitativ hochwertige Themen angezeigt werden und sie über die richtigen Berechtigungen zum Nutzen und Beitragen von Wissen verfügen.

In diesem Artikel werden die folgenden Planungsentscheidungen behandelt:

- Welche SharePoint Websites sie für Themen durchforsten möchten
- Welche Themen sie ggf. von der Themenerfahrung ausschließen möchten
- Benutzer, für die Sie Themen sichtbar machen möchten
- Welche Benutzer Sie Berechtigungen zum Verwalten von Themen im Themencenter erteilen möchten
- Welche Benutzer Sie berechtigungen zum Erstellen oder Bearbeiten von Themen im Themencenter erteilen möchten
- Welchen Namen Sie Ihrem Themencenter geben möchten

Die Sicherheit und der Datenschutz Ihrer Daten werden berücksichtigt, und Themenerfahrungen gewähren Benutzern keinen zusätzlichen Zugriff auf Dateien, auf die sie keine Rechte haben. Wir empfehlen Ihnen, auch [die Sicherheit und den Datenschutz](topic-experiences-security-privacy.md) von Microsoft Viva Topics im Rahmen Ihres Planungsprozesses zu lesen.

Um mehr über die KI-Technologie hinter Viva Topics zu erfahren, lesen Sie ["Viva" in Microsoft Viva Topics: von Big Data bis hin zu großem Wissen.](https://www.microsoft.com/research/blog/alexandria-in-microsoft-viva-topics-from-big-data-to-big-knowledge)

## <a name="requirements"></a>Anforderungen

Sie müssen [Viva Topics abonniert](https://www.microsoft.com/microsoft-viva/topics) haben und ein globaler Administrator oder SharePoint Administrator sein, um auf die Microsoft 365 Admin Center zugreifen und Topics einrichten zu können.

Alle Benutzer, die Topics verwenden möchten, benötigen eine Lizenz für **Themenerfahrungen.** Das Zuweisen von Lizenzen wird in ["Einrichten von Microsoft Viva Topics"](set-up-topic-experiences.md)behandelt.

## <a name="topic-discovery"></a>Themensuche

Die Einstellungen für die Themensuche geben an, welche SharePoint-Websites als Quellen für Themen verwendet werden. Dazu gehören sowohl klassische und moderne Websites als auch Websites, die Microsoft Teams und Microsoft 365-Gruppen zugeordnet sind. OneDrive Websites sind nicht enthalten.

Sie können wählen, ob Sie alle SharePoint-Websites, eine bestimmte Liste von Websites oder keine Websites einschließen möchten. Es wird empfohlen, dass Sie alle Websites auswählen, damit Themenerfahrungen eine große Anzahl von guten Themen für Ihre Benutzer entdecken können.

Wenn Sie Topics einrichten, können Sie unter folgenden Optionen wählen:

- **Alle Websites**: Alle SharePoint-Websites in Ihrer Organisation. Dies schließt aktuelle und zukünftige Websites ein.
- **Alle, mit Ausnahme von ausgewählten Websites**: Alle Websites mit Ausnahme der von Ihnen angegebenen Websites. Websites, die in Zukunft erstellt werden, werden als Quellen für die Themensuche einbezogen. 
- **Nur ausgewählte Websites:** Nur die von Ihnen angegebenen Websites. Zukünftig erstellte Websites werden nicht als Quellen für die Themensuche einbezogen.
- **Keine Websites**: Schließen Sie keine SharePoint-Websites ein.

Wenn Sie entweder **"Alle", mit Ausnahme ausgewählter Websites** oder **"Nur ausgewählte Websites",** auswählen, können Sie eine .csv Datei mit einer Liste von Websites hochladen. Diese Optionen sind nützlich, wenn Sie ein Pilotprojekt durchführen und eine begrenzte Anzahl von Websites zum Starten einschließen möchten.

Sie können die .csv Vorlage unten kopieren:

``` csv
Site name,URL
```

Es wird nicht empfohlen, **"Keine Websites"** auszuwählen, da dadurch verhindert wird, dass Themen automatisch erstellt oder aktualisiert werden. Sie können diese Option jedoch auswählen, wenn Sie Topics einrichten und später Websites hinzufügen möchten.

Es wird empfohlen, einen Prozess für Benutzer oder Wissensmanager zu erstellen, um anzufordern, dass einzelne Websites bei Bedarf in Ihrer Organisation aus der Themensuche entfernt werden.

### <a name="multi-geo"></a>Multi-Geo

Wenn Ihre Organisation [Microsoft 365 Multi-Geo](/microsoft-365/enterprise/microsoft-365-multi-geo)bereitgestellt hat, wird das Themencenter am zentralen Standort bereitgestellt, und nur SharePoint Standorte am zentralen Standort stehen als Quellen für Themen zur Verfügung. (Wenn Sie **alle Websites** auswählen, verwendet Viva Topics alle Websites am zentralen Ort.)

Die gesamte Verarbeitung und Speicherung von Inhalten erfolgt am zentralen Ort.

## <a name="user-permissions"></a>Benutzerberechtigungen

Die von Ihnen angegebenen Benutzerberechtigungen bestimmen, welche Personen in Ihrer Organisation mit Themen interagieren und was sie tun können.

> [!Note] 
> Derzeit unterstützt Viva Topics nicht die Bereitstellung von Lizenzen oder Benutzerberechtigungen für Gastbenutzer (externe). 

*Themen verwalten*

Wissensmanager überwachen die Qualität von Informationen, deren Struktur und andere bewährte Methoden in Ihrer Organisation. Sie können Themen bestätigen und ablehnen.

Sie können zwar einzelne Themenmanager angeben, es wird jedoch empfohlen, eine Sicherheitsgruppe zu erstellen (oder eine vorhandene zu verwenden), die die Personen enthält, die Wissensmanager sein sollen. Sie können diese Sicherheitsgruppe während des Setupprozesses angeben.

*Erstellen und Bearbeiten von Themen*

Themenmitwirkende sind die Experten und Fachexperten in Ihrer Organisation. Sie können Themen erstellen und bearbeiten. 

Es wird empfohlen, allen Benutzern in Ihrer Organisation das Erstellen und Bearbeiten von Themen zu ermöglichen, da Themen am besten funktionieren, wenn alle Benutzer Informationen freigeben können.

Wenn Sie das Erstellen und Bearbeiten von Themen auf bestimmte Personen oder Gruppen beschränken möchten, erstellen Sie eine Sicherheitsgruppe für sie, und geben Sie diese während des Setupprozesses an.

Sie können festlegen, dass niemand an Themen mitwirken darf, dies wird jedoch nicht empfohlen. Wissensmanager können weiterhin Themen bearbeiten und erstellen, wenn Sie diese Option auswählen.

*Betrachter von Topics*

Themenbetrachter können Informationen auf Themenseiten, in Suchergebnissen und wenn Themen im Inhalt hervorgehoben werden, z. B. SharePoint Seiten, anzeigen. Benutzer können erkannte Themen nur sehen, wenn sie Zugriff auf die Dateien und Seiten haben, auf denen das Thema entdeckt wurde.

Beim Einrichten von Themenviewern können Sie aus folgenden Möglichkeiten wählen:

- **Jeder in meiner Organisation**
- **Nur ausgewählte Personen oder Sicherheitsgruppen**
- **Niemand**

Wir empfehlen **jeder in meiner Organisation,** aber wenn Sie ein Pilotprojekt durchführen, möchten Sie möglicherweise nur ausgewählte Personen oder Sicherheitsgruppen auswählen. Sie können auch **"Niemand"** auswählen, wenn Sie "Topics" einrichten möchten, aber noch keine Themen anzeigen dürfen. (Wissensmanager haben weiterhin Zugriff, damit sie die Themen anzeigen und bei der Entscheidung helfen können, Themen allgemein verfügbar zu machen.)

## <a name="knowledge-rules"></a>Wissensregeln

Als Administrator können Sie bestimmte Themen aus der Themenerfahrung ausschließen. Dies ist hilfreich, wenn Vertrauliche Daten nicht in Themen angezeigt werden sollen. Während Wissensmanager Themen im Themencenter ausschließen können, sind vom Administrator ausgeschlossene Themen nicht einmal für Wissensmanager sichtbar. (Wissensmanager können auch Themen im Themencenter nach der Ermittlung entfernen.)

Wenn Sie Themen auf Administratorebene ausschließen möchten, müssen Sie sie einer .csv-Datei hinzufügen und die Datei hochladen. Sie können dies während des Setups oder später tun.

Die .csv Datei muss die folgenden Parameter enthalten:

- **Name**: Geben Sie den Namen des Themas ein, das ausgeschlossen werden soll. Sie können auf zwei Arten vorgehen:
- **MatchType-Exact/Partial:** Geben Sie an, ob der eingegebene Name ein *exakter* oder *teilweiser* Übereinstimmungstyp war.
    - Genaue Übereinstimmung: Sie können den genauen Namen oder das Akronym angeben (z. B. *Contoso* oder *ATL).*
    - Partielle Übereinstimmung: Sie können alle Themen ausschließen, die ein bestimmtes Wort enthalten.  Beispielsweise schließt *Arc* alle Themen mit dem Wort *Bogen* aus, z. B. *Arc Circle,* *Arc Arc-* oder *Training Arc.* Beachten Sie, dass Themen, in denen der Text als Teil eines Worts enthalten ist, wie z. B. *Architektur,* nicht ausgeschlossen werden.
- **Steht für (optional)**: (auch bekannt als *Erweiterung)* Wenn Sie ein Akronym ausschließen möchten, geben Sie die Wörter ein, für die das Akronym steht.

    ![Ausschließen von Themen in csv-Vorlage](../media/exclude-topics-csv.png) 

Sie können die csv-Vorlage unten kopieren:

``` csv
Name (required),Expansion,MatchType- Exact/Partial (required)
```

## <a name="administration"></a>Verwaltung

Wenn Sie Topics im Rahmen des Setupprozesses einrichten, wird automatisch ein Themencenter erstellt. Überlegen Sie, wie Sie das Themencenter benennen möchten und wie die URL sein soll. Sie können sowohl den Namen als auch die URL im Rahmen des Setupprozesses festlegen und den Namen (aber nicht die URL) später im Microsoft 365 Admin Center ändern. Sie können nur ein Themencenter haben.

## <a name="setup-checklist"></a>Prüfliste zum Einrichten

Wenn Sie Themenoberflächen einrichten, benötigen Sie die folgenden Elemente, während Sie den Setup-Assistenten durchlaufen:

> [!div class="checklist"]
> * Liste der ein- oder auszuschließenden Websites, wenn nicht alle Websites für die Themenentdeckung eingeschlossen werden
> * Sicherheitsgruppe für Themenbetrachter, wenn nicht alle Benutzer Themen anzeigen können
> * Sicherheitsgruppe für Themenmitwirkende, wenn nicht alle Benutzer Themen erstellen und bearbeiten können
> * Sicherheitsgruppe für Themenwissensverwalter, wenn nicht alle Benutzer Themen verwalten können
> * Liste vertraulicher Themen, die von der Themensuche ausgeschlossen werden sollen
> * Ein Name für Ihre Themencenterwebsite

## <a name="see-also"></a>Siehe auch

[Topic Experiences einrichten](set-up-topic-experiences.md)

[Verwalten der Themensuche in Microsoft 365](topic-experiences-discovery.md)

[Verwalten der Themensichtbarkeit in Microsoft 365](topic-experiences-knowledge-rules.md)

[Verwalten von Themenberechtigungen in Microsoft 365](topic-experiences-user-permissions.md)

[Ändern des Namens des Themencenters in Microsoft 365](topic-experiences-administration.md)
