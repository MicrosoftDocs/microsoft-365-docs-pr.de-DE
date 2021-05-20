---
title: Teams für den Schutz vertraulicher Daten konfigurieren
f1.keywords: NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- m365solution-3tiersprotection
- m365solution-securecollab
ms.custom:
- Ent_Solutions
recommendations: false
description: Hier erfahren Sie, wie Sie Teams bereitstellen, in denen vertrauliche Daten geschützt sind.
ms.openlocfilehash: 16b60230c18f4a4f5e10b4bd421fd1bf02b39779
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2021
ms.locfileid: "52538183"
---
# <a name="configure-teams-with-protection-for-sensitive-data"></a>Teams für den Schutz vertraulicher Daten konfigurieren

In diesem Artikel sehen wir uns das Einrichten eines Teams an, in dem vertrauliche Daten geschützt sind. Bevor Sie die Schritte in diesem Artikel ausführen, müssen Sie die Schritte unter [Bereitstellen von Microsoft Teams mit Basisschutz ](configure-teams-baseline-protection.md) abgeschlossen haben. Die "Vertraulich"-Stufe bietet den folgenden zusätzlichen Schutz gegenüber der Basisstufe:

- Eine Vertraulichkeitsbezeichnung für das Team, die es Ihnen ermöglicht, die Gastfreigabe ein- oder auszuschalten und den Zugriff auf SharePoint-Inhalte für nicht verwaltete Geräte auf die Webebene zu beschränken. Diese Bezeichnung kann auch zum klassifizieren von Dateien verwendet werden.
- Einen restriktiveren standardmäßigen Freigabe-Linktyp
- Nur Teambesitzer können private Kanäle erstellen.

## <a name="guest-sharing"></a>Gastfreigabe

Je nach Art des Unternehmens ist möglicherweise die Gastfreigabe für Teams erforderlich, in denen vertrauliche Daten vorhanden sind. Wenn Sie die Zusammenarbeit mit Personen außerhalb Ihrer Organisation in einem solchen Team planen, empfiehlt es sich, die Gastfreigabe zu aktivieren. Microsoft 365 umfasst eine Vielzahl von Sicherheits- und Compliance-Features, um vertrauliche Inhalte sicher freigeben zu können. Dies ist in der Regel eine sicherere Option als das direkte Senden von Inhalten an Personen außerhalb Ihrer Organisation.

Details zur sicheren Freigabe für Gäste finden Sie in den folgenden Ressourcen:

- [Begrenzen der versehentlichen Gefährdung von Dateien bei der Freigabe für Personen außerhalb Ihrer Organisation](./share-limit-accidental-exposure.md)
- [Erstellen einer sicheren Gastfreigabeumgebung](./create-secure-guest-sharing-environment.md)

Für das Zulassen oder Blockieren des Gastfreigabe verwenden wir eine Kombination aus einer Vertraulichkeitsbezeichnung für das Team und Steuerelementen für die Freigabe auf Team- und Websiteebene für die zugeordnete SharePoint-Website, die beide später behandelt werden.

## <a name="sensitivity-labels"></a>Vertraulichkeitsbezeichnungen

Für den Schutz auf Vertraulichkeitsebene werden wir eine Vertraulichkeitsbezeichnung verwenden, um das Team zu klassifizieren. Diese Bezeichnung kann auch verwendet werden, um einzelne Dateien in diesem oder anderen Teams oder an anderen Speicherorten wie SharePoint oder OneDrive zu klassifizieren. 

Als ersten Schritt müssen Sie Vertraulichkeitsbezeichnungen für Microsoft Teams aktivieren. Weitere Informationen finden Sie unter [Verwenden von Vertraulichkeitsbezeichnungen zum Schutz von Inhalten in Microsoft Teams, Office 365-Gruppen und SharePoint-Websites](../compliance/sensitivity-labels-teams-groups-sites.md).

Wenn Sie in Ihrer Organisation bereits über Vertraulichkeitsbezeichnungen verfügen, überlegen Sie, wie sich diese Bezeichnung in Ihre allgemeine Bezeichnungsstrategie einfügt. Sie können den Namen oder die Einstellungen bei Bedarf an die Anforderungen Ihrer Organisation anpassen.

Sobald Sie Vertraulichkeitsbezeichnungen für Microsoft Teams aktiviert haben, besteht der nächste Schritt darin, die erforderliche Bezeichnung zu erstellen.

Erstellen einer Vertraulichkeitsbezeichnung
1. Öffnen Sie das [Microsoft 365 Compliance Center](https://compliance.microsoft.com).
2. Klicken Sie unter **Lösungen** auf **Informationsschutz**.
3. Klicken Sie auf **Bezeichnung erstellen**.
4. Weisen Sie der Bezeichnung einen Namen zu. Wir empfehlen **Vertraulich**, Sie können aber auch einen anderen Namen auswählen, falls dieser bereits verwendet wird.
5. Fügen Sie einen Namen und eine Beschreibung hinzu, und klicken Sie auf **Weiter**.
6. Wählen Sie auf der Seite **Definieren des Bereichs für diese Bezeichnung** die Option **Dateien & E-Mails** und **Gruppen & Websites** aus und klicken Sie **Weiter**.
7. Klicken Sie auf der Seite **Auswählen der Schutzeinstellungen für Dateien und E-Mails** auf **Weiter**.
8. Klicken Sie auf der Seite *Automatische Bezeichnung für Dateien und E-Mails* auf **Weiter**.
9. Wählen Sie auf der Seite **Definieren der Schutzeinstellungen für Gruppen und Websites** die Option **Einstellungen für Datenschutz und den Zugriff externer Benutzer** und **Einstellungen für Gerätezugriff und externe Freigabe** aus und klicken Sie **Weiter**.
10. Wählen Sie auf der Seite **Definieren von Einstellungen für Datenschutz und den Zugriff externer Benutzer** unter **Datenschutz** die Option **Privat** aus.
11. Wenn Sie Gastzugriffe zulassen wollen, wählen Sie unter **Externer Benutzerzugriff** die Option **Zulassen, dass Microsoft 365-Gruppenbesitzer Personen außerhalb Ihrer Organisation als Gäste zur Gruppe hinzufügen**.
12. Klicken Sie auf **Weiter**.
13. Wählen Sie auf der Seite **Definieren der Einstellungen für externe Freigabe und Gerätezugriff** die Option **Steuerung der externen Freigabe aus bezeichneten SharePoint-Websites**.
14. Wählen Sie unter **Inhalt kann geteilt werden mit** die Option **Neue und bestehende Gäste**, wenn Sie den Gastzugriff erlauben wollen, oder anderenfalls **Nur Personen in Ihrer Organisation**.
15. Wählen Sie unter **Zugriff von nicht verwalteten Geräten** die Option **Eingeschränkten, reinen Webzugriff zulassen**.
16. Klicken Sie auf **Weiter**.
17. Klicken Sie auf der Seite **Automatisches Bezeichnen von Datenbank-Spalten** auf **Weiter**.
18. Klicken Sie auf **Bezeichnung erstellen** und anschließend auf **Fertig**.

Nachdem Sie die Bezeichnung erstellt haben, müssen Sie sie für die Benutzer veröffentlichen, die sie verwenden sollen. Zum Schutz vertraulicher Daten werden die Bezeichnungen für alle Benutzer verfügbar gemacht. Die Bezeichnung wird im Microsoft 365 Compliance Center auf der Seite **Schutz von Daten** auf der Registerkarte **Bezeichnungsrichtlinien** veröffentlicht. Wenn bereits eine Richtlinie vorhanden ist, die für alle Benutzer gilt, fügen Sie diese Bezeichnung zu dieser Richtlinie hinzu. Wenn Sie eine neue Richtlinie erstellen müssen, lesen Sie [Veröffentlichen von Vertraulichkeitsbezeichnungen durch Erstellen einer Bezeichnungsrichtlinie](../compliance/create-sensitivity-labels.md#publish-sensitivity-labels-by-creating-a-label-policy).

## <a name="create-a-team"></a>Ein Team erstellen

Weitere Konfigurationsschritte für das Vertraulichkeitsszenario erfolgen auf der SharePoint-Website, die dem Team zugeordnet ist. Deshalb besteht der nächste Schritt darin, ein Team zu erstellen.

So erstellen Sie ein Team für vertrauliche Informationen
1. Klicken Sie in Microsoft Teams auf der linken Seite auf **Teams** und dann unten in der Teamliste auf **Einem Team beitreten oder ein Team erstellen**.
2. Klicken Sie auf **Team erstellen** (erste Karte, obere linke Ecke).
3. Wählen Sie **Neuerstellen eines Teams**.
4. Wählen Sie in der Liste **Vertraulichkeit** die **Vertraulichkeitsbezeichnung** aus, die Sie soeben erstellt haben.
5. Klicken Sie unter **Datenschutz** auf **Privat**.
6. Geben Sie einen Namen für die Gruppe ein, und klicken Sie dann auf **Erstellen**.
7. Fügen Sie Benutzer zu dem Team hinzu, und klicken Sie dann auf **Schließen**.

## <a name="private-channel-settings"></a>Einstellungen für private Kanäle

Auf dieser Ebene wird die Möglichkeit der Erstellung privater Kanäle auf Teambesitzer eingeschränkt.

So schränken Sie die Erstellung privater Kanäle ein
1. Klicken Sie im Team auf **Weitere Optionen** und dann auf **Team verwalten**.
2. Erweitern Sie auf der Registerkarte **Einstellungen** den Eintrag **Mitgliedsberechtigungen**.
3. Deaktivieren Sie das Kontrollkästchen **Mitglieder können private Kanäle erstellen**.

Sie können auch [Teams-Richtlinien](/MicrosoftTeams/teams-policies) verwenden, um zu steuern, wer private Kanäle erstellen kann.

## <a name="sharepoint-settings"></a>SharePoint-Einstellungen

Jedes Mal, wenn Sie ein neues Team mit der Vertraulichkeitsbezeichnung erstellen, müssen Sie in SharePoint zwei Schritte ausführen:

- Aktualisieren Sie die Gastfreigabeeinstellungen für die Website im SharePoint Admin Center so, dass sie jenen entsprechen, die Sie beim Erstellen der Bezeichnung vorgenommen haben, und legen Sie für den standardmäßigen Freigabelink *Bestimmte Personen* fest.
- Aktualisieren Sie die Website-Freigabeeinstellungen auf der Website selbst, um zu verhindern, dass Mitglieder die Website freigeben.

### <a name="site-guest-sharing-settings"></a>Einstellungen für die Gastfreigabe von Websites

Die Einstellung für die Gastfreigabe, die Sie beim Erstellen der Bezeichnung ausgewählt haben (die sich nur auf die Teammitgliedschaft auswirkt), sollten mit den Gast-Freigabeeinstellungen für die zugeordnete SharePoint-Website wie folgt übereinstimmen:

|Bezeichnungseinstellung|Einstellung für die SharePoint-Website|
|:------------|:----------------------|
|**Office 365-Gruppenbesitzer dürfen Personen außerhalb der Organisation zur Gruppe hinzufügen** ausgewählt|**Neue und vorhandene Gäste** (Standard für neue Teams)|
|**Office 365-Gruppenbesitzer dürfen Personen außerhalb der Organisation zur Gruppe hinzufügen** nicht ausgewählt|**Nur Personen in Ihrer Organisation**|

So aktualisieren Sie Websiteeinstellungen
1. Öffnen Sie das [SharePoint Admin Center](https://admin.microsoft.com/sharepoint).
2. Klicken Sie unter **Websites** auf **Aktive Websites**.
3. Klicken Sie auf die dem Team zugeordnete Website.
4. Klicken Sie auf der Registerkarte **Richtlinien** unter **Externe Freigabe** auf **Bearbeiten**.
5. Wenn Sie beim Erstellen der Vertraulichkeitsbezeichnung die Gastfreigabe zugelassen haben, stellen Sie sicher, dass **Neue und vorhandene Gäste** ausgewählt ist. Wenn Sie beim Erstellen der Bezeichnung keine Freigabe zugelassen haben, wählen Sie **Nur Personen in Ihrer Organisation** aus.
6. Deaktivieren Sie unter "Standardmäßiger Freigabe-Linktyp" das Kontrollkästchen **Identisch mit der Einstellung auf Organisationsebene**, und wählen Sie **Bestimmte Personen (nur die Personen, die der Benutzer angibt)** aus.
7. Klicken Sie auf **Speichern**.

Wenn Sie dies als Teil des Team-Erstellungsprozesses in Form eines Skripts festlegen möchten, können Sie [Set-SPOSite](/powershell/module/sharepoint-online/set-sposite) mit den folgenden Parametern verwenden:

- `-SharingCapability Disabled` um die Gastfreigabe zu deaktivieren (standardmäßig aktiviert)
- `-DefaultSharingLinkType Internal` um den standardmäßigen Freigabelink zu *Bestimmte Personen* zu ändern

#### <a name="private-channels"></a>Private Kanäle

Wenn Sie dem Team private Kanäle hinzufügen, erstellt jeder private Kanal eine neue SharePoint-Website mit den Standardeinstellungen für die Freigabe. Diese Websites werden im SharePoint Admin Center nicht angezeigt, daher müssen Sie das Cmdlet "Set-SPOSite PowerShell" verwenden, um die Gast-Freigabeeinstellungen zu aktualisieren.

### <a name="site-sharing-settings"></a>Freigabeeinstellungen für Websites

Um sicherzustellen, dass die SharePoint-Website nicht mit Personen geteilt wird, die nicht Mitglieder des Teams sind, schränken Sie die Freigabe auf die Besitzer ein.

So beschränken Sie die Websitefreigabe auf die Besitzer
1. Gehen Sie in Teams zur Registerkarte **Allgemein** des Teams, das Sie aktualisieren möchten.
2. Klicken Sie auf der Symbolleiste des Teams auf **Dateien**.
3. Klicken Sie auf die drei Punkte "(…)" und dann auf **In SharePoint öffnen**.
4. Klicken Sie in der Symbolleiste der zugrunde liegenden SharePoint-Website auf das Symbol "Einstellungen" und anschließend auf **Websiteberechtigungen**.
5. Klicken Sie im Bereich **Websiteberechtigungen** unter **Websitefreigabe** auf **Ändern, wie Mitglieder teilen können**.
6. Wählen Sie unter **Freigabeberechtigungen** die Option **Websitebesitzer und -mitglieder sowie Personen mit Bearbeitungsberechtigungen können Dateien und Ordner freigeben, aber nur Websitebesitzer können die Website freigeben**, und klicken Sie dann auf **Speichern**.


## <a name="see-also"></a>Siehe auch

[Erstellen und Konfigurieren von Vertraulichkeitsbezeichnungen und deren Richtlinien](../compliance/create-sensitivity-labels.md)