---
title: Planen von Themen Erfahrungen in Microsoft 365
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: nkokoye
audience: admin
ms.topic: article
ms.service: o365-administration
search.appverid: MET150
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
description: Informationen zum Planen von Themen Erfahrungen in Microsoft 365
ms.openlocfilehash: 153937cf6bc4a12f0a27866204b2286c343ddf55
ms.sourcegitcommit: 1a9f0f878c045e1ddd59088ca2a94397605a242a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/14/2020
ms.locfileid: "49668156"
---
# <a name="plan-topic-experiences-in-microsoft-365"></a>Planen von Themen Erfahrungen in Microsoft 365

Sie haben die Kontrolle darüber, wie Themen in Ihrer Organisation erlebbar sind. Ihre Planungsentscheidungen für Themenerfahrung stellt sicher, dass Ihren Benutzern qualitativ hochwertige Themen angezeigt werden und Sie über die richtigen Berechtigungen zum Nutzen und zur Mitwirkung von Wissen verfügen.

In diesem Artikel werden die folgenden Planungsentscheidungen untersucht:

- Die SharePoint-Websites, die Sie nach Themen durchforsten möchten.
- Welche Themen (falls vorhanden) von den Themen Erfahrungen ausgeschlossen werden sollen
- Die Benutzer, für die Sie Themen sichtbar machen möchten.
- Die Benutzer, denen Sie Berechtigungen zum Verwalten von Themen im Themen Center erteilen möchten.
- Die Benutzer, denen Sie Berechtigungen zum Erstellen oder Bearbeiten von Themen im Themen Center erteilen möchten.
- Welchen Namen möchten Sie Ihrem Themen Center geben?

Die Sicherheit und der Datenschutz Ihrer Daten werden respektiert, und durch Themen Erfahrungen erhalten Benutzer keinen zusätzlichen Zugriff auf Dateien, für die Sie keine Rechte haben. Es wird empfohlen, dass Sie auch im Rahmen Ihres Planungsprozesses die [Themen Sicherheit und Datenschutz](topic-experiences-security-privacy.md) lesen.

## <a name="requirements"></a>Anforderungen

Sie müssen ein globaler Administrator oder SharePoint-Administrator sein, um auf das Microsoft 365 Admin Center zuzugreifen und Themen Erfahrungen einzurichten.

Für alle Benutzer, die Themen Erfahrungen verwenden möchten, ist eine Lizenz für das **Thema Experiences** erforderlich. Das Zuweisen von Lizenzen wird in " [Einrichten von Themen Erfahrungen](set-up-topic-experiences.md)" behandelt.

## <a name="topic-discovery"></a>Thema Ermittlung

Die Themen Ermittlungs Einstellungen geben an, welche SharePoint-Websites als Quellen für Themen verwendet werden. Sie können auswählen, ob alle SharePoint-Websites, eine bestimmte Liste von Websites oder keine Websites eingeschlossen werden sollen. Es wird empfohlen, dass Sie alle Websites auswählen, sodass mit dem Thema Erfahrungen eine große Anzahl von guten Themen für Ihre Benutzer ermittelt werden kann.

Wenn Sie Themen Erfahrungen einrichten, können Sie eine der folgenden Optionen auswählen:

- **Alle Websites**: alle SharePoint-Websites in Ihrer Organisation. Dazu gehören aktuelle und zukünftige Websites.
- **Alle, außer ausgewählte Websites**: alle Websites mit Ausnahme der von Ihnen angegebenen. In Zukunft erstellte Websites werden als Quellen für die Themen Ermittlung hinzugefügt. 
- **Nur ausgewählte Websites**: nur die Websites, die Sie angeben. In der Zukunft erstellte Websites werden nicht als Quellen für die Themen Ermittlung einbezogen.
- **Keine Websites**: keine SharePoint-Websites einschließen.

Wenn Sie entweder **alle, außer ausgewählte Websites** oder **nur ausgewählte Websites** auswählen, können Sie eine CSV-Datei mit einer Liste von Websites hochladen. Diese Optionen sind hilfreich, wenn Sie ein Pilotprojekt ausführen und eine beschränkte Anzahl von Websites für den Start einschließen möchten.

Sie können die CSV-Vorlage unten kopieren:

``` csv
Site name,URL
```

Es wird nicht empfohlen, **keine Websites** auszuwählen, da verhindert wird, dass Themen automatisch erstellt oder aktualisiert werden. Sie können diese Option jedoch auswählen, wenn Sie Themen Erfahrungen einrichten und dann später Websites hinzufügen möchten.

Es wird empfohlen, einen Prozess für Benutzer oder Wissensmanager zu erstellen, um zu fordern, dass einzelne Websites bei Bedarf in Ihrer Organisation aus der Thema Ermittlung entfernt werden.

## <a name="user-permissions"></a>Benutzerberechtigungen

Die von Ihnen angegebenen Benutzerberechtigungen bestimmen, welche Personen in Ihrer Organisation mit Themen interagieren und was Sie tun können.

*Verwalten von Themen*

Wissensmanager überwachen die Qualität der Informationen, ihre Strukturierung und andere bewährte Methoden in Ihrer Organisation. Sie können Themen bestätigen und ablehnen.

Während Sie einzelne Themen Manager angeben können, wird empfohlen, dass Sie eine Sicherheitsgruppe erstellen (oder eine vorhandene verwenden), die die Personen enthält, die Sie als Wissens Verwalter bezeichnen möchten. Sie können diese Sicherheitsgruppe während des Installationsvorgangs angeben.

*Erstellen und Bearbeiten von Themen*

Thema Mitwirkende sind die Champions und Fachexperten in Ihrer Organisation. Sie können Themen erstellen und bearbeiten. 

Es wird empfohlen, dass Sie allen in Ihrer Organisation das Erstellen und Bearbeiten von Themen erlauben, da Themen Erfahrungen am besten funktionieren, wenn alle Benutzerinformationen freigeben können.

Wenn Sie das Erstellen und Bearbeiten von Themen auf bestimmte Personen oder Gruppen beschränken möchten, erstellen Sie für diese eine Sicherheitsgruppe, und geben Sie Sie während des Installationsvorgangs an.

Sie können festlegen, dass niemand Beiträge zu Themen leisten darf, dies wird jedoch nicht empfohlen. Die Knowledge Manager können weiterhin Themen bearbeiten und erstellen.

*Themen Betrachter*

Thema Betrachter können Informationen zu Themenseiten, in Suchergebnissen und wenn Themen im Inhalt wie SharePoint-Seiten hervorgehoben werden, angezeigt werden. Benutzer können nur entdeckte Themen anzeigen, wenn Sie Zugriff auf die Dateien und Seiten haben, in denen das Thema entdeckt wurde.

Beim Einrichten von Themen Ansichten stehen Ihnen folgende Möglichkeiten zur Verfügung:

- **Jeder in meiner Organisation**
- **Nur ausgewählte Personen oder Sicherheitsgruppen**
- **Niemand**

Wir empfehlen **alle Mitarbeiter in meiner Organisation**, aber wenn Sie ein Pilotprojekt ausführen, können Sie nur ausgewählte Personen oder Sicherheitsgruppen auswählen. Sie können auch **keines** auswählen, wenn Sie Themen Erfahrungen einrichten möchten, aber nicht zulassen, dass Personen noch angezeigt werden. (Knowledge Manager haben weiterhin Zugriff, um die Themen anzeigen zu lassen und die Entscheidung zu unterstützen, Themen Erfahrungen allgemein verfügbar zu machen.)

## <a name="knowledge-rules"></a>Wissens Regeln

Als Administrator können Sie bestimmte Themen aus thematischen Erfahrungen ausschließen. Dies ist hilfreich, wenn Sie verhindern möchten, dass vertrauliche Daten in Themen angezeigt werden. Während Knowledge Manager Themen im Themen Center ausschließen können, sind die vom Administrator ausgegrenzten Themen auch für Wissensmanager nicht sichtbar. (Knowledge Manager können auch Themen im Themen Center nach der Ermittlung entfernen.)

Wenn Sie Themen auf Administratorebene ausschließen möchten, müssen Sie Sie zu einer CSV-Datei hinzufügen und die Datei hochladen. Dies können Sie während der Installation oder später tun.

Die CSV-Datei muss die folgenden Parameter enthalten:

- **Name**: Geben Sie den Namen des Themas ein, das Sie ausschließen möchten. Sie können auf zwei Arten vorgehen:
- **MatchType-Exact/Partial**: Geben Sie an, ob es sich bei dem von Ihnen eingegebenen Namen um einen *genauen* oder *partiellen* Übereinstimmungs handelt.
    - Exakte Übereinstimmung: Sie können den genauen Namen oder das Akronym angeben (beispielsweise *contoso* oder *ATL*).
    - Partielle Übereinstimmung: Sie können alle Themen ausschließen, die ein bestimmtes Wort enthalten.  Beispielsweise schließt *Bogen* alle Themen mit dem Wort *Bogen* in ihm aus, wie *Bogen Kreis*, *Plasma Schweißen* oder *Schulungs Bogen*. Beachten Sie, dass die Themen, in denen der Text als Teil eines Wortes eingeschlossen ist, wie etwa die *Architektur*, nicht ausgeschlossen werden.
- **Steht für (optional)**: (wird auch als *Erweiterung* bezeichnet) Wenn Sie ein Akronym ausschließen möchten, geben Sie die Wörter ein, für die die Abkürzung steht.

    ![Themen in CSV-Vorlage ausschließen](../media/exclude-topics-csv.png) 

Sie können die CSV-Vorlage unten kopieren:

``` csv
Name (required),Expansion,MatchType- Exact/Partial (required)
```

## <a name="administration"></a>Verwaltung

Wenn Sie im Rahmen des Installationsvorgangs Themen Erfahrungen einrichten, wird automatisch ein Themen Center erstellt. Überlegen Sie, was Sie dem Themen Center nennen möchten und wie die URL sein soll. Sie können den Namen und die URL als Teil des Installationsvorgangs festlegen, und Sie können den Namen (aber nicht die URL) später im Microsoft 365 Admin Center ändern. Sie können nur ein Themen Center haben.

## <a name="setup-checklist"></a>Prüfliste für Setup

Wenn Sie Themen Erfahrungen einrichten, benötigen Sie die folgenden Elemente, wenn Sie den Setup-Assistenten durchgehen:

> [!div class="checklist"]
> * Liste der einzuschließenden oder auszuschließenden Websites, wenn nicht alle Websites für die Themen Ermittlung eingeschlossen werden
> * Sicherheitsgruppe für Themen Betrachter, wenn nicht allen Benutzern das Anzeigen von Themen gestattet wird
> * Sicherheitsgruppe für Thema Mitwirkende, wenn nicht allen Benutzern das Erstellen und Bearbeiten von Themen gestattet wird
> * Sicherheitsgruppe für Thema Wissensmanager, wenn nicht allen Benutzern das Verwalten von Themen gestattet wird
> * Liste der vertraulichen Themen, die von der Thema Ermittlung ausgeschlossen werden sollen
> * Ein Name für Ihre Themen Center-Website

## <a name="see-also"></a>Siehe auch

[Einrichten von Themen Erfahrungen](set-up-topic-experiences.md)

[Verwalten der Themen Ermittlung in Microsoft 365](topic-experiences-discovery.md)

[Verwalten der Themen Sichtbarkeit in Microsoft 365](topic-experiences-knowledge-rules.md)

[Verwalten von Themen Berechtigungen in Microsoft 365](topic-experiences-user-permissions.md)

[Ändern des Namens des Themen Centers in Microsoft 365](topic-experiences-administration.md)
