---
title: Planen von Microsoft Viva-Themen
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: nkokoye
audience: admin
ms.topic: article
ms.service: o365-administration
search.appverid: MET150
localization_priority: Normal
description: Informationen zum Planen von Plan for Microsoft Viva Topics
ms.openlocfilehash: d64e4b341fe96d7aa3636f58bffe3dd8f388838e
ms.sourcegitcommit: b6763a8ab240fbdd56078a7c9452445d0c4b9545
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/22/2021
ms.locfileid: "51957539"
---
# <a name="plan-for-microsoft-viva-topics"></a>Planen von Microsoft Viva-Themen

Sie haben die Kontrolle darüber, wie Themen in Ihrer Organisation behandelt werden. Ihre Planungsentscheidungen für Themen stellen sicher, dass Ihren Benutzern qualitativ hochwertige Themen angezeigt werden und dass sie über die richtigen Berechtigungen zum Nutzen und Zum Beitragen von Wissen verfügen.

In diesem Artikel werden die folgenden Planungsentscheidungen untersucht:

- Welche SharePoint-Websites Sie nach Themen durchforsten möchten
- Welche Themen Sie von den Themenerfahrungen ausschließen möchten, falls dies der Fall ist
- Für welche Benutzer Sie Themen sichtbar machen möchten
- Welche Benutzer Sie berechtigungen zum Verwalten von Themen im Themencenter erteilen möchten
- Welche Benutzer Sie berechtigungen zum Erstellen oder Bearbeiten von Themen im Themencenter erteilen möchten
- Welchen Namen möchten Sie Ihrem Themencenter geben?

Die Sicherheit und der Datenschutz Ihrer Daten werden berücksichtigt, und die Themenerfahrung gewährt Benutzern keinen zusätzlichen Zugriff auf Dateien, auf die sie keine Rechte haben. Es wird empfohlen, im Rahmen Ihres Planungsprozesses auch Die Sicherheit und den Datenschutz von [Microsoft Viva Topics](topic-experiences-security-privacy.md) zu lesen.

## <a name="requirements"></a>Anforderungen

Sie müssen ["Viva Topics"](https://www.microsoft.com/microsoft-viva/topics) abonniert haben und ein globaler Administrator oder SharePoint-Administrator sein, um auf das Microsoft 365 Admin Center zu zugreifen und Themen einrichten zu können.

Alle Benutzer, die Themen verwenden möchten, benötigen eine **Topic Experiences-Lizenz.** Zuweisen von Lizenzen finden Sie unter [Einrichten von Microsoft Viva Topics](set-up-topic-experiences.md).

## <a name="topic-discovery"></a>Themasuche

Die Einstellungen für die Themenermittlung geben an, welche SharePoint-Websites als Quellen für Themen verwendet werden. Sie können alle SharePoint-Websites, eine bestimmte Liste von Websites oder keine Websites hinzufügen. Es wird empfohlen, alle Websites zu wählen, damit themenerfahrungen eine große Anzahl von guten Themen für Ihre Benutzer entdecken können.

Beim Einrichten von Themen können Sie aus den folgenden Optionen auswählen:

- **Alle Websites**: Alle SharePoint-Websites in Ihrer Organisation. Dies umfasst aktuelle und zukünftige Websites.
- **Alle, mit Ausnahme ausgewählter Websites:** Alle Websites mit Ausnahme der angegebenen Websites. Websites, die in Zukunft erstellt werden, werden als Quellen für die Themenerkennung einbezogen. 
- **Nur ausgewählte Websites:** Nur die angegebenen Websites. Websites, die in Zukunft erstellt werden, werden nicht als Quellen für die Themenerkennung einbezogen.
- **Keine Websites**: Keine SharePoint-Websites enthalten.

Wenn Sie entweder **Alle auswählen, mit** Ausnahme ausgewählter Websites oder **Nur** ausgewählte Websites, können Sie eine CSV-Datei mit einer Liste von Websites hochladen. Diese Optionen sind hilfreich, wenn Sie ein Pilotprojekt erstellen und eine begrenzte Anzahl von Websites zum Starten verwenden möchten.

Sie können die CSV-Vorlage unten kopieren:

``` csv
Site name,URL
```

Es wird nicht empfohlen, keine Websites **zu wählen,** da dadurch verhindert wird, dass Themen automatisch erstellt oder aktualisiert werden. Sie können diese Option jedoch auswählen, wenn Sie Themen einrichten und später Websites hinzufügen möchten.

Es wird empfohlen, einen Prozess für Benutzer oder Wissensmanager zu erstellen, um zu fordern, dass einzelne Websites bei Bedarf in Ihrer Organisation aus der Themensuche entfernt werden.

### <a name="multi-geo"></a>Multi-Geo

Wenn Ihre Organisation [Microsoft 365 Multi-Geo](/microsoft-365/enterprise/microsoft-365-multi-geo)bereitgestellt hat, wird das Themencenter am zentralen Standort bereitgestellt, und nur SharePoint-Websites am zentralen Standort stehen als Quellen für Themen zur Verfügung. (Wenn Sie Alle **Websites auswählen,** verwendet "Viva Topics" alle Websites am zentralen Standort.)

Die Verarbeitung und Speicherung von Inhalten erfolgt an zentraler Stelle.

## <a name="user-permissions"></a>Benutzerberechtigungen

Die von Ihnen angegebenen Benutzerberechtigungen bestimmen, welche Personen in Ihrer Organisation mit Themen interagieren und was sie tun können.

> [!Note] 
> Derzeit unterstützt Viva Topics die Bereitstellung von Lizenzen oder Benutzerberechtigungen für Gastbenutzer (externe Benutzer) nicht. 

*Themen verwalten*

Wissensmanager überwachen die Qualität der Informationen, deren Struktur und andere bewährte Methoden in Ihrer Organisation. Sie können Themen bestätigen und ablehnen.

Sie können zwar einzelne Themenmanager angeben, es wird jedoch empfohlen, eine Sicherheitsgruppe (oder eine vorhandene) zu erstellen, die die Personen enthält, die Sie als Wissensmanager verwenden möchten. Sie können diese Sicherheitsgruppe während des Setupvorgangs angeben.

*Erstellen und Bearbeiten von Themen*

Mitwirkende sind die Experten für Themen und Experten in Ihrer Organisation. Sie können Themen erstellen und bearbeiten. 

Es wird empfohlen, allen Benutzern in Ihrer Organisation das Erstellen und Bearbeiten von Themen zu ermöglichen, da die Themenerfahrungen am besten funktionieren, wenn alle Benutzer Informationen freigeben können.

Wenn Sie das Erstellen und Bearbeiten von Themen auf bestimmte Personen oder Gruppen beschränken möchten, erstellen Sie eine Sicherheitsgruppe für sie, und geben Sie sie während des Einrichtungsprozesses an.

Sie können auswählen, dass niemand an Themen mit beitragen kann, dies wird jedoch nicht empfohlen. Wissensmanager können weiterhin Themen bearbeiten und erstellen, wenn Sie diese Option auswählen.

*Themenbetrachter*

Themenbetrachter können Informationen auf Themenseiten, in Suchergebnissen und in Den Inhalten wie SharePoint-Seiten anzeigen. Benutzer können nur dann ermittelte Themen sehen, wenn sie Zugriff auf die Dateien und Seiten haben, in denen das Thema entdeckt wurde.

Beim Einrichten von Themenbetrachtern können Sie aus:

- **Jeder in meiner Organisation**
- **Nur ausgewählte Personen oder Sicherheitsgruppen**
- **Niemand**

Wir empfehlen **Jeder in meiner Organisation,** aber wenn Sie ein Pilotprojekt erstellen, sollten Sie möglicherweise nur ausgewählte Personen oder Sicherheitsgruppen auswählen. Sie können auch Niemand **auswählen,** wenn Sie Themen einrichten möchten, aber noch keine Themen sehen können. (Wissensmanager haben weiterhin Zugriff darauf, dass sie die Themen anzeigen und bei der Entscheidung helfen, Themen allgemein verfügbar zu machen.)

## <a name="knowledge-rules"></a>Wissensregeln

Als Administrator können Sie bestimmte Themen von der Themenerfahrung ausschließen. Dies ist hilfreich, wenn Vertrauliche Daten nicht in Themen angezeigt werden sollen. Während Wissensmanager Themen im Themencenter ausschließen können, sind vom Administrator ausgeschlossene Themen nicht einmal für Wissensmanager sichtbar. (Wissensmanager können nach der Ermittlung auch Themen im Themencenter entfernen.)

Wenn Sie Themen auf Administratorebene ausschließen möchten, müssen Sie sie einer CSV-Datei hinzufügen und die Datei hochladen. Sie können dies während des Setups oder höher tun.

Die CSV-Datei muss die folgenden Parameter enthalten:

- **Name**: Geben Sie den Namen des Themas ein, das Sie ausschließen möchten. Sie können auf zwei Arten vorgehen:
- **MatchType-Exact/Partial**: Geben Sie ein, ob der eingegebene Name ein exakter oder *teilweiser* *Übereinstimmungstyp* war.
    - Genaue Übereinstimmung: Sie können den genauen Namen oder das Akronym (z. B. *Contoso* oder *ATL) eingeben.*
    - Teilweise Übereinstimmung: Sie können alle Themen ausschließen, in denen ein bestimmtes Wort enthalten ist.  Der Bogen schließt *beispielsweise* alle Themen  aus, in denen der Wortbogen enthalten ist, z. B. Bogenkreis, Lichtbogenverschwesung oder *Schulungsbogen.*  Beachten Sie, dass Themen, in denen der Text als Teil eines Worts enthalten ist, wie z. B. Architektur, nicht *ausgeschlossen werden.*
- **Steht für (optional)**: (Auch als Erweiterung *bezeichnet)* Wenn Sie ein Akronym ausschließen möchten, geben Sie die Wörter ein, für die das Akronym steht.

    ![Ausschließen von Themen in der CSV-Vorlage](../media/exclude-topics-csv.png) 

Sie können die folgende CSV-Vorlage kopieren:

``` csv
Name (required),Expansion,MatchType- Exact/Partial (required)
```

## <a name="administration"></a>Verwaltung

Wenn Sie Themen als Teil des Einrichtungsprozesses einrichten, wird automatisch ein Themencenter erstellt. Überlegen Sie, wie Sie das Themencenter benennen möchten und wie die URL sein soll. Sie können sowohl den Namen als auch die URL im Rahmen des Einrichtungsprozesses festlegen und den Namen (jedoch nicht die URL) später im Microsoft 365 Admin Center ändern. Sie können nur ein Themencenter haben.

## <a name="setup-checklist"></a>Prüfliste zum Einrichten

Wenn Sie Themenerfahrungen einrichten, benötigen Sie die folgenden Elemente, während Sie den Setup-Assistenten durchgehen:

> [!div class="checklist"]
> * Liste der Websites, die ein- oder ausgeschlossen werden, wenn nicht alle Websites für die Themenerkennung enthalten sind
> * Sicherheitsgruppe für Themenbetrachter, wenn nicht allen Benutzern das Anzeigen von Themen erlaubt wird
> * Sicherheitsgruppe für Mitwirkende von Themen, wenn nicht allen Benutzern das Erstellen und Bearbeiten von Themen ermöglicht wird
> * Sicherheitsgruppe für Themenwissensmanager, wenn nicht allen Benutzern die Verwaltung von Themen ermöglicht wird
> * Liste der vertraulichen Themen, die von der Themenerkennung ausgeschlossen werden
> * Ein Name für Ihre Themencenterwebsite

## <a name="see-also"></a>Siehe auch

[Topic Experiences einrichten](set-up-topic-experiences.md)

[Verwalten der Themenerkennung in Microsoft 365](topic-experiences-discovery.md)

[Verwalten der Thementransparenz in Microsoft 365](topic-experiences-knowledge-rules.md)

[Verwalten von Themenberechtigungen in Microsoft 365](topic-experiences-user-permissions.md)

[Ändern des Namens des Themencenters in Microsoft 365](topic-experiences-administration.md)
