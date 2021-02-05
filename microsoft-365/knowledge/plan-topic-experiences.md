---
title: Planen von Microsoft -Themen
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: nkokoye
audience: admin
ms.topic: article
ms.service: o365-administration
search.appverid: MET150
localization_priority: Normal
description: Hier erfahren Sie, wie Sie den Plan für Microsoft -Themen planen.
ms.openlocfilehash: 65983f342b3277d33c7bfeb21d8481b1d3d5e817
ms.sourcegitcommit: a048fefb081953aefa7747c08da52a7722e77288
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2021
ms.locfileid: "50107954"
---
# <a name="plan-for-microsoft-viva-topics"></a>Planen von Microsoft -Themen

Sie haben die Kontrolle darüber, wie Themen in Ihrer Organisation behandelt werden. Ihre Planungsentscheidungen für Themen stellen sicher, dass Ihren Benutzern Themen mit hoher Qualität angezeigt werden und dass sie über die richtigen Berechtigungen zum Nutzen und Zum Beitragen von Wissen verfügen.

In diesem Artikel werden diese Planungsentscheidungen behandelt:

- Welche SharePoint-Websites sie nach Themen durchforsten möchten
- Welche Themen sie gegebenenfalls aus der Themenerfahrung ausschließen möchten
- Für welche Benutzer Sie Themen sichtbar machen möchten
- Welche Benutzer Sie berechtigungen zum Verwalten von Themen im Themencenter erteilen möchten
- Welche Benutzer Sie berechtigungen zum Erstellen oder Bearbeiten von Themen im Themencenter erteilen möchten
- Welchen Namen Möchten Sie Ihrem Themencenter geben?

Die Sicherheit und der Datenschutz Ihrer Daten wird berücksichtigt, und Themenerfahrungen gewähren Benutzern keinen zusätzlichen Zugriff auf Dateien, auf die sie keine Rechte haben. Es wird empfohlen, dass Sie im Rahmen Ihres Planungsprozesses auch die Themen "Sicherheit und Datenschutz in [Microsoft Topics"](topic-experiences-security-privacy.md) lesen.

## <a name="requirements"></a>Anforderungen

Sie müssen ein globaler Administrator oder ein SharePoint-Administrator sein, um auf das Microsoft 365 Admin Center zugreifen und Themen einrichten zu können.

Alle Benutzer, die Themen verwenden möchten, benötigen **eine Topic Experiences-Lizenz.** Das Zuweisen von Lizenzen wird in [den Themen zum Einrichten von Microsoft Topics behandelt.](set-up-topic-experiences.md)

## <a name="topic-discovery"></a>Themenermittlung

Die Themenerkennungseinstellungen geben an, welche SharePoint-Websites als Quellen für Themen verwendet werden. Sie können alle SharePoint-Websites, eine bestimmte Liste von Websites oder keine Websites hinzufügen. Es wird empfohlen, alle Websites zu wählen, damit themenerfahrungen eine große Anzahl von guten Themen für Ihre Benutzer entdecken können.

Beim Einrichten von Themen können Sie aus den folgenden Optionen auswählen:

- **Alle Websites:** Alle SharePoint-Websites in Ihrer Organisation. Dazu gehören aktuelle und zukünftige Websites.
- **Alle, mit Ausnahme ausgewählter Websites:** Alle Websites mit Ausnahme der von Ihnen angegebenen Websites. Websites, die in Zukunft erstellt werden, werden als Quellen für die Themenermittlung einbezogen. 
- **Nur ausgewählte Websites:** Nur die von Ihnen angegebenen Websites. Websites, die in Zukunft erstellt werden, werden nicht als Quellen für die Themenermittlung einbezogen.
- **Keine Websites:** Keine SharePoint-Websites enthalten.

Wenn Sie **"Alle"** mit Ausnahme ausgewählter Websites oder **"Nur** ausgewählte Websites" auswählen, können Sie eine .csv-Datei mit einer Liste von Websites hochladen. Diese Optionen sind hilfreich, wenn Sie ein Pilotprojekt machen und eine begrenzte Anzahl von Websites zum Starten verwenden möchten.

Sie können die .csv-Vorlage unten kopieren:

``` csv
Site name,URL
```

Es wird nicht empfohlen, "Keine Websites" zu **wählen,** da dadurch verhindert wird, dass Themen automatisch erstellt oder aktualisiert werden. Sie können diese Option jedoch auswählen, wenn Sie Themen einrichten und später Websites hinzufügen möchten.

Es wird empfohlen, einen Prozess für Benutzer oder Wissensmanager zu erstellen, um an verlangen, dass einzelne Websites bei Bedarf aus der Themenermittlung in Ihrer Organisation entfernt werden.

## <a name="user-permissions"></a>Benutzerberechtigungen

Die von Ihnen angegebenen Benutzerberechtigungen bestimmen, welche Personen in Ihrer Organisation mit Themen interagieren und was sie tun können.

*Verwalten von Themen*

Wissensmanager überwachen die Qualität von Informationen, deren Struktur und andere bewährte Methoden in Ihrer Organisation. Sie können Themen bestätigen und ablehnen.

Sie können zwar einzelne Themenmanager angeben, es wird jedoch empfohlen, eine Sicherheitsgruppe zu erstellen (oder eine vorhandene zu verwenden), die die Personen enthält, die Sie als Wissensmanager verwenden möchten. Sie können diese Sicherheitsgruppe während des Setupprozesses angeben.

*Erstellen und Bearbeiten von Themen*

Mitwirkende sind die Experten und Experten in Ihrer Organisation. Sie können Themen erstellen und bearbeiten. 

Es wird empfohlen, allen Benutzern in Ihrer Organisation das Erstellen und Bearbeiten von Themen zu ermöglichen, da die Themenerfahrung am besten funktioniert, wenn alle Benutzer Informationen freigeben können.

Wenn Sie das Erstellen und Bearbeiten von Themen auf bestimmte Personen oder Gruppen beschränken möchten, erstellen Sie eine Sicherheitsgruppe für diese Personen, und geben Sie sie während des Setupprozesses an.

Sie können auswählen, dass niemand an Themen mit beiträgen darf, dies wird jedoch nicht empfohlen. Wissensmanager können weiterhin Themen bearbeiten und erstellen, wenn Sie diese Option auswählen.

*Themenanzeigen*

Themenanzeigen können Informationen auf Themenseiten, in Suchergebnissen und bei hervorgehobenen Themen in Inhalten wie SharePoint-Seiten anzeigen. Benutzer können ermittelte Themen nur sehen, wenn sie Zugriff auf die Dateien und Seiten haben, auf denen das Thema gefunden wurde.

Beim Einrichten von Themenanzeigen haben Sie die Wahl zwischen:

- **Jeder in meiner Organisation**
- **Nur ausgewählte Personen oder Sicherheitsgruppen**
- **Niemand**

We recommend **Everyone in my organization**, but if you're doing a pilot you may want to choose only selected people or security groups. You can also choose **No one** if you want to set up Topics, but not allow people to see topics yet. (Wissensmanager haben weiterhin Zugriff, um ihnen das Anzeigen der Themen und Hilfe bei der Entscheidung zu ermöglichen, Themen allgemein verfügbar zu machen.)

## <a name="knowledge-rules"></a>Wissensregeln

Als Administrator können Sie bestimmte Themen aus der Themenerfahrung ausschließen. Dies ist hilfreich, wenn Vertrauliche Daten nicht in Themen angezeigt werden sollen. Während Knowledge Manager Themen im Themencenter ausschließen können, sind vom Administrator ausgeschlossene Themen nicht einmal für Wissensmanager sichtbar. (Wissensmanager können nach der Ermittlung auch Themen im Themencenter entfernen.)

Wenn Sie Themen auf Administratorebene ausschließen möchten, müssen Sie sie einer CSV-Datei hinzufügen und die Datei hochladen. Sie können dies während des Setups oder höher tun.

Die .csv-Datei muss die folgenden Parameter enthalten:

- **Name**: Geben Sie den Namen des Themas ein, das Sie ausschließen möchten. Sie können auf zwei Arten vorgehen:
- **MatchType-Exact/Partial**: Geben Sie ein, ob der eingegebene Name ein *exakter* oder teilweiser *Übereinstimmungstyp* war.
    - Genaue Übereinstimmung: Sie können den genauen Namen oder das Akronym (z. B. *Contoso* oder *ATL) verwenden.*
    - Teilweise Übereinstimmung: Sie können alle Themen ausschließen, in denen ein bestimmtes Wort enthalten ist.  Der Bogen *schließt* z. B. alle Themen aus, *in* denen der Wortbogen enthalten ist, z. B. Bogenkreis,  *Arkusbogen* oder *Schulungsbogen.* Beachten Sie, dass Themen, in denen der Text als Teil eines Worts enthalten ist, wie z. B. Architektur, nicht *ausgeschlossen werden.*
- **Steht für (optional):**(Auch als Erweiterung *bezeichnet)* Wenn Sie ein Akronym ausschließen möchten, geben Sie die Wörter ein, für die das Akronym steht.

    ![Ausschließen von Themen in der CSV-Vorlage](../media/exclude-topics-csv.png) 

Sie können die folgende CSV-Vorlage kopieren:

``` csv
Name (required),Expansion,MatchType- Exact/Partial (required)
```

## <a name="administration"></a>Verwaltung

Wenn Sie Themen im Rahmen des Einrichtungsprozesses einrichten, wird automatisch ein Themencenter erstellt. Überlegen Sie, wie Sie das Themencenter benennen möchten und wie die URL sein soll. Sie können den Namen und die URL im Rahmen des Setupprozesses festlegen und den Namen (jedoch nicht die URL) später im Microsoft 365 Admin Center ändern. Sie können nur ein Themencenter haben.

## <a name="setup-checklist"></a>Prüfliste für das Setup

Wenn Sie Themenerfahrungen einrichten, benötigen Sie die folgenden Elemente, während Sie den Setup-Assistenten durchgehen:

> [!div class="checklist"]
> * Liste der Websites, die ein- oder ausgeschlossen werden, wenn nicht alle Websites für die Themenermittlung enthalten sind
> * Sicherheitsgruppe für Themenbetrachter, wenn nicht allen Benutzern das Anzeigen von Themen erlaubt wird
> * Sicherheitsgruppe für Mitwirkende von Themen, wenn nicht allen Benutzern das Erstellen und Bearbeiten von Themen erlaubt wird
> * Sicherheitsgruppe für Wissensverwalter von Themen, wenn nicht allen Benutzern die Verwaltung von Themen erlaubt wird
> * Liste der vertraulichen Themen, die von der Themenermittlung ausgeschlossen werden
> * Ein Name für Ihre Themencenterwebsite

## <a name="see-also"></a>Siehe auch

[Topic Experiences einrichten](set-up-topic-experiences.md)

[Verwalten der Themenermittlung in Microsoft 365](topic-experiences-discovery.md)

[Verwalten der Sichtbarkeit von Themen in Microsoft 365](topic-experiences-knowledge-rules.md)

[Verwalten von Themenberechtigungen in Microsoft 365](topic-experiences-user-permissions.md)

[Ändern des Namens des Themencenters in Microsoft 365](topic-experiences-administration.md)
