---
title: Teams für den Schutz hochgradig vertraulicher Daten konfigurieren
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
description: Hier erfahren Sie, wie Sie Teams bereitstellen, in denen hochgradig vertrauliche Daten geschützt sind.
ms.openlocfilehash: 6354de5a37547d14b16a4d6a0857ddc390d531e6
ms.sourcegitcommit: 98b889e674ad1d5fa37d4b6c5fc3eda60a1d67f3
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/05/2021
ms.locfileid: "49750809"
---
# <a name="configure-teams-with-protection-for-highly-sensitive-data"></a>Teams für den Schutz hochgradig vertraulicher Daten konfigurieren

In diesem Artikel sehen wir uns das Einrichten eines Teams an, in dem hochgradig vertrauliche Daten geschützt sind. Bevor Sie die Schritte in diesem Artikel ausführen, müssen Sie die Schritte unter [Bereitstellen von Microsoft Teams mit Basisschutz ](configure-teams-baseline-protection.md) abgeschlossen haben.

Für diese Schutzebene erstellen wir eine Vertraulichkeitsbezeichnung, die in Ihrem Unternehmen für hochgradig vertrauliche Teams und Dateien verwendet werden kann. Nur Mitglieder Ihrer Organisation und Gäste, die Sie angegeben haben, können Dateien entschlüsseln, die diese Bezeichnung verwenden. Wenn Sie die Berechtigungen weiter einschränken müssen, so dass nur Mitglieder eines bestimmten Teams Dateien entschlüsseln können, siehe [Team mit Sicherheitseinschränkung bereitstellen](secure-teams-security-isolation.md).

Die "Hochgradig vertraulich"-Stufe bietet den folgenden zusätzlichen Schutz gegenüber der Basisstufe:

- Eine Vertraulichkeitsbezeichnung für das Team, die es Ihnen ermöglicht, die Gastfreigabe ein- oder auszuschalten und den Zugriff auf SharePoint-Inhalte für nicht verwaltete Geräte auf die Webebene zu beschränken. Diese Bezeichnung kann auch zum Klassifizieren und Verschlüsseln von Dateien verwendet werden.
- Einen restriktiveren standardmäßigen Freigabe-Linktyp
- Nur Teambesitzer können private Kanäle erstellen.
- Zugriffsanforderungen für die zugehörige SharePoint-Website werden deaktiviert.

## <a name="guest-sharing"></a>Gastfreigabe

Je nach Art des Unternehmens ist möglicherweise die Gastfreigabe für Teams erforderlich, in denen hochgradig vertrauliche Daten vorhanden sind. Wenn Sie die Zusammenarbeit mit Personen außerhalb Ihrer Organisation in einem solchen Team planen, empfiehlt es sich, die Gastfreigabe zu aktivieren. Microsoft 365 umfasst eine Vielzahl von Sicherheits- und Compliance-Features, um vertrauliche Inhalte sicher freigeben zu können. Dies ist in der Regel eine sicherere Option als das direkte Senden von Inhalten an Personen außerhalb Ihrer Organisation.

Details zur sicheren Freigabe für Gäste finden Sie in den folgenden Ressourcen:

- [Begrenzen der versehentlichen Gefährdung von Dateien bei der Freigabe für Personen außerhalb Ihrer Organisation](https://docs.microsoft.com/microsoft-365/solutions/share-limit-accidental-exposure)
- [Erstellen einer sicheren Gastfreigabeumgebung](https://docs.microsoft.com/microsoft-365/solutions/create-secure-guest-sharing-environment)

Für das Zulassen oder Blockieren des Gastfreigabe verwenden wir eine Kombination aus einer Vertraulichkeitsbezeichnung für das Team und Steuerelementen für die Freigabe auf Team- und Websiteebene für die zugeordnete SharePoint-Website, die beide später behandelt werden.

## <a name="sensitivity-labels"></a>Vertraulichkeitsbezeichnungen

Für den Schutz auf hochgradig Vertraulichkeitsebene werden wir eine Vertraulichkeitsbezeichnung verwenden, um das Team zu klassifizieren. Diese Bezeichnung kann auch verwendet werden, um einzelne Dateien in diesem oder anderen Teams oder an anderen Speicherorten wie SharePoint oder OneDrive zu klassifizieren und verschlüsseln. 

Als ersten Schritt müssen Sie Vertraulichkeitsbezeichnungen für Microsoft Teams aktivieren. Weitere Informationen finden Sie unter [Verwenden von Vertraulichkeitsbezeichnungen zum Schutz von Inhalten in Microsoft Teams, Office 365-Gruppen und SharePoint-Websites](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites).

Wenn Sie in Ihrer Organisation bereits über Vertraulichkeitsbezeichnungen verfügen, überlegen Sie, wie sich diese Bezeichnung in Ihre allgemeine Bezeichnungsstrategie einfügt. Sie können den Namen oder die Einstellungen bei Bedarf an die Anforderungen Ihrer Organisation anpassen.

Sobald Sie Vertraulichkeitsbezeichnungen für Microsoft Teams aktiviert haben, besteht der nächste Schritt darin, die erforderliche Bezeichnung zu erstellen.

Erstellen einer Vertraulichkeitsbezeichnung
1. Öffnen Sie das [Microsoft 365 Compliance Center](https://compliance.microsoft.com).
2. Klicken Sie unter **Lösungen** auf **Informationsschutz**.
3. Klicken Sie auf **Bezeichnung erstellen**.
4. Weisen Sie der Bezeichnung einen Namen zu. Wir empfehlen **Vertraulich**, Sie können aber auch einen anderen Namen auswählen, falls dieser bereits verwendet wird.
5. Fügen Sie einen Namen und eine Beschreibung hinzu, und klicken Sie auf **Weiter**.
6. Wählen Sie auf der Seite **Definieren des Bereichs für diese Bezeichnung** die Option **Dateien & E-Mails** und **Gruppen & Websites** aus und klicken Sie **Weiter**.
7. Wählen Sie auf der Seite **Schutzeinstellungen für Dateien und E-Mails auswählen** die Option **Dateien und E-Mails verschlüsseln** aus und klicken Sie dann **Weiter**.
8. Wählen Sie auf der Seite **Verschlüsselung** die Option **Verschlüsselungseinstellungen konfigurieren** aus.
9. Klicken Sie unter **Berechtigungen bestimmten Benutzern und Gruppen zuweisen** auf **Berechtigungen zuweisen**.
10. Klicken Sie auf **Alle Benutzer und Gruppen in Ihrer Organisation hinzufügen**.
11. Wenn es Gäste gibt, die Berechtigungen zum Entschlüsseln von Dateien haben sollten, klicken Sie auf **Benutzer oder Gruppen** hinzufügen, und fügen Sie sie hinzu.
12.  Klicken Sie auf **Speichern** und dann auf **Weiter**.
13. Klicken Sie auf der Seite *Automatische Bezeichnung für Dateien und E-Mails** auf **Weiter**.
14. Wählen Sie auf der Seite **Definieren der Schutzeinstellungen für Gruppen und Websites** die Option **Einstellungen für Datenschutz und den Zugriff externer Benutzer** und **Einstellungen für Gerätezugriff und externe Freigabe** aus und klicken Sie **Weiter**.
15. Wählen Sie auf der Seite **Definieren von Einstellungen für Datenschutz und den Zugriff externer Benutzer** unter **Datenschutz** die Option **Privat** aus.
16. Wenn Sie Gastzugriffe zulassen wollen, wählen Sie unter **Externer Benutzerzugriff** die Option **Zulassen, dass Microsoft 365-Gruppenbesitzer Personen außerhalb Ihrer Organisation als Gäste zur Gruppe hinzufügen**.
17. Klicken Sie auf **Weiter**.
18. Wählen Sie auf der Seite **Definieren der Einstellungen für externe Freigabe und Gerätezugriff** die Option **Steuerung der externen Freigabe aus bezeichneten SharePoint-Websites**.
19. Wählen Sie unter **Inhalt kann geteilt werden mit** die Option **Neue und bestehende Gäste** aus, wenn Sie den Gastzugriff erlauben wollen, oder anderenfalls **Nur Personen in Ihrer Organisation**.
20. Wählen Sie unter **Zugriff von nicht verwalteten Geräten** die Option **Zugriff blockieren**.
21. Klicken Sie auf **Weiter**.
22. Klicken Sie auf der Seite **Automatisches Bezeichnen von Datenbank-Spalten** auf **Weiter**.
23. Klicken Sie auf **Bezeichnung erstellen** und anschließend auf **Fertig**.

Nachdem Sie die Bezeichnung erstellt haben, müssen Sie sie für die Benutzer veröffentlichen, die sie verwenden sollen. Zum Schutz vertraulicher Daten werden die Bezeichnungen für alle Benutzer verfügbar gemacht. Die Bezeichnung wird im Microsoft 365 Compliance Center auf der Seite **Schutz von Daten** auf der Registerkarte **Bezeichnungsrichtlinien** veröffentlicht. Wenn bereits eine Richtlinie vorhanden ist, die für alle Benutzer gilt, fügen Sie diese Bezeichnung zu dieser Richtlinie hinzu. Wenn Sie eine neue Richtlinie erstellen müssen, lesen Sie [Veröffentlichen von Vertraulichkeitsbezeichnungen durch Erstellen einer Bezeichnungsrichtlinie](https://docs.microsoft.com/microsoft-365/compliance/create-sensitivity-labels#publish-sensitivity-labels-by-creating-a-label-policy).

## <a name="create-a-team"></a>Ein Team erstellen

Weitere Konfigurationsschritte für das hochgradig Vertraulichkeitsszenario erfolgen auf der SharePoint-Website, die dem Team zugeordnet ist. Deshalb besteht der nächste Schritt darin, ein Team zu erstellen.

So erstellen Sie ein Team für hochgradig vertrauliche Informationen
1. Klicken Sie in Microsoft Teams auf der linken Seite auf **Teams** und dann unten in der Teamliste auf **Einem Team beitreten oder ein Team erstellen**.
2. Klicken Sie auf **Team erstellen** (erste Karte, obere linke Ecke).
3. Wählen Sie **Neuerstellen eines Teams**.
4. Wählen Sie in der Liste **Vertraulichkeit** die Bezeichnung **Hochgradig vertraulich** aus, die Sie soeben erstellt haben.
5. Klicken Sie unter **Datenschutz** auf **Privat**.
6. Geben Sie einen Namen für die Gruppe ein, und klicken Sie dann auf **Erstellen**.
7. Fügen Sie Benutzer zu dem Team hinzu, und klicken Sie dann auf **Schließen**.

## <a name="private-channel-settings"></a>Einstellungen für private Kanäle

Auf dieser Ebene wird die Möglichkeit der Erstellung privater Kanäle auf Teambesitzer eingeschränkt.

So schränken Sie die Erstellung privater Kanäle ein
1. Klicken Sie im Team auf **Weitere Optionen** und dann auf **Team verwalten**.
2. Erweitern Sie auf der Registerkarte **Einstellungen** den Eintrag **Mitgliedsberechtigungen**.
3. Deaktivieren Sie das Kontrollkästchen **Mitglieder können private Kanäle erstellen**.

Sie können auch [Teams-Richtlinien](https://docs.microsoft.com/MicrosoftTeams/teams-policies) verwenden, um zu steuern, wer private Kanäle erstellen kann.

## <a name="sharepoint-settings"></a>SharePoint-Einstellungen

Jedes Mal, wenn Sie ein neues Team mit der Bezeichnung „Hochgradig vertraulich“ erstellen, müssen Sie in SharePoint zwei Schritte ausführen:

- Aktualisieren Sie die Gastfreigabeeinstellungen für die Website im SharePoint Admin Center so, dass sie jenen entsprechen, die Sie beim Erstellen der Bezeichnung vorgenommen haben, und legen Sie für den standardmäßigen Freigabelink *Personen mit vorhandenem Zugriff* fest.
- Aktualisieren Sie die Website-Freigabeeinstellungen auf der Website selbst, um zu verhindern, dass Mitglieder Dateien, Ordner oder die Website freigeben, und Zugriffsanforderungen ausschalten.

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
5. Wenn Sie beim Erstellen der Bezeichnung „Hochgradig vertraulich“ die Gastfreigabe zugelassen haben, stellen Sie sicher, dass **Neue und vorhandene Gäste** ausgewählt ist. Wenn Sie beim Erstellen der Bezeichnung keine Freigabe zugelassen haben, wählen Sie **Nur Personen in Ihrer Organisation** aus.
6. Deaktivieren Sie unter "Standardmäßiger Freigabe-Linktyp" das Kontrollkästchen **Identisch mit der Einstellung auf Organisationsebene**, und wählen Sie **Personen mit vorhandenem Zugriff** aus.
7. Klicken Sie auf **Speichern**.

Wenn Sie dies als Teil des Team-Erstellungsprozesses in Form eines Skripts festlegen möchten, können Sie [Set-SPOSite](https://docs.microsoft.com/powershell/module/sharepoint-online/set-sposite) mit den folgenden Parametern verwenden:

- `-SharingCapability Disabled` um die Gastfreigabe zu deaktivieren (standardmäßig aktiviert)
- `-DefaultSharingLinkType Internal` um den standardmäßigen Freigabelink zu *Bestimmte Personen* zu ändern

#### <a name="private-channels"></a>Private Kanäle

Wenn Sie dem Team private Kanäle hinzufügen, erstellt jeder private Kanal eine neue SharePoint-Website mit den Standardeinstellungen für die Freigabe. Diese Websites werden im SharePoint Admin Center nicht angezeigt, daher müssen Sie das Cmdlet "Set-SPOSite PowerShell" verwenden, um die Gast-Freigabeeinstellungen zu aktualisieren.

### <a name="site-sharing-settings"></a>Freigabeeinstellungen für Websites

Um sicherzustellen, dass die SharePoint-Website nicht mit Personen geteilt wird, die nicht Mitglieder des Teams sind, schränken Sie die Freigabe auf die Besitzer ein. Außerdem beschränken wir das Freigeben von Dateien und Ordnern auf die Teambesitzer. Auf diese Weise wird sichergestellt, dass die Besitzer informiert sind, wenn eine Datei an jemanden außerhalb des Teams freigegeben wird.

So beschränken Sie die Websitefreigabe auf die Besitzer
1. Gehen Sie in Teams zur Registerkarte **Allgemein** des Teams, das Sie aktualisieren möchten.
2. Klicken Sie auf der Symbolleiste des Teams auf **Dateien**.
3. Klicken Sie auf die drei Punkte "(…)" und dann auf **In SharePoint öffnen**.
4. Klicken Sie in der Symbolleiste der zugrunde liegenden SharePoint-Website auf das Symbol "Einstellungen" und anschließend auf **Websiteberechtigungen**.
5. Klicken Sie im Bereich "Websiteberechtigungen" unter **Freigabeeinstellungen** auf **Freigabeeinstellungen ändern**.
6. Wählen Sie unter **Freigabeberechtigungen** die Option **Nur Websitebesitzer können Dateien, Ordner und die Website teilen** aus.
7. Legen Sie **Zugriffsanforderungen zulassen** auf **Aus** fest, und klicken Sie dann auf **Speichern**.

## <a name="see-also"></a>Siehe auch

[Erstellen und Konfigurieren von Vertraulichkeitsbezeichnungen und deren Richtlinien](https://docs.microsoft.com/microsoft-365/compliance/create-sensitivity-labels)

