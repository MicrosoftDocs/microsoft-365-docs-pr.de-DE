---
title: Sicherheit und Datenschutz in Microsoft Viva Topics
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: nkokoye, cjtan
audience: admin
ms.topic: article
ms.service: o365-administration
search.appverid: MET150
localization_priority: Normal
description: Erfahren Sie, wie Sie Sicherheit und Datenschutz von Microsoft Viva Topics planen
ms.openlocfilehash: b8c82b1914df739ea9086a4ce1585733a7b6d854
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/14/2021
ms.locfileid: "52925491"
---
# <a name="microsoft-viva-topics-security-and-privacy"></a>Sicherheit und Datenschutz in Microsoft Viva Topics

Themen verwenden vorhandene Inhaltssicherheitsfeatures in Microsoft 365 zusammen mit administrativen Kontrollen, um zu steuern, welche von KI generierten Inhalte Benutzern in Ihrer Organisation angezeigt werden. Es ist die Kombination aus Microsoft 365 Sicherheitseinstellungen (Berechtigungen für Websites, Dateien und Ordner) und Administratoreinstellungen für Topics, die bestimmen, was ein bestimmter Benutzer in Themen sehen kann.

Durch das Einrichten von Themen werden keine vorhandenen Zugriffssteuerelemente für Inhalte in Ihrer Organisation geändert. Benutzern werden nur die Dokumente angezeigt, auf die sie bereits Zugriff haben.

In diesem Artikel wird beschrieben, wie Topics aus Sicherheitsperspektive funktioniert und welche Optionen Wissensadministratoren und Wissensmanager haben, um die Sichtbarkeit von Themen zu steuern. Lesen Sie diesen Artikel im Rahmen Ihrer [Planung für Themen.](plan-topic-experiences.md)

Sie sollten damit vertraut [sein, was Topics ist,](topic-experiences-overview.md)das [Themencenter](topic-center-overview.md)und wie Sie [mit Themen im Themencenter arbeiten,](manage-topics.md) bevor Sie diesen Artikel lesen.

## <a name="what-users-can-see-in-topics"></a>Was Benutzer in Themen sehen können

Um Themen anzuzeigen, muss ein Benutzer Folgendes tun:

- Verfügen über eine Viva Topics-Lizenz
- [Themenbetrachter,](topic-experiences-knowledge-rules.md#change-who-can-see-topics-in-your-organization) [Mitwirkender oder Wissensmanager](topic-experiences-user-permissions.md) sein

Diese beiden Dinge ermöglichen Benutzern den Zugriff auf das Themencenter und ermöglichen es ihnen, Highlights und Themenkarten anzuzeigen.

Themenmitwirkende verfügen darüber hinaus über [Erstellungs- und Bearbeitungsberechtigungen](topic-experiences-user-permissions.md) für Themen, und Wissensmanager können Themen bestätigen oder entfernen.

Wenn ein Thema zum ersten Mal entdeckt wird, können Wissensmanager es im Themencenter sehen. Abhängig von der Vollständigkeit und Relevanz des Themas wird den Themenbetrachtern möglicherweise das Thema in Themenkarten angezeigt.

Themen können von KI generierte Informationen und Informationen enthalten, die von Themenmitwirkenden oder Wissensmanagern hinzugefügt oder bearbeitet wurden.

- Informationen in einem Thema, die von KI hinzugefügt wurden, sind nur für Personen sichtbar, die Zugriff auf den Quellinhalt haben.
- Text, der manuell von einem Themenmitwirkenden oder Wissensmanager hinzugefügt oder bearbeitet wurde, ist für jeden sichtbar, der das Thema sehen kann.

Themenbetrachter und Mitwirkende können die Liste der bestätigten und veröffentlichten Themen im Themencenter sehen, aber die Themendetails, die eine bestimmte Person sehen kann, hängen von den Berechtigungen ab, die sie für das Quellmaterial haben, und davon, ob das Thema manuell bearbeitet wurde.

In der folgenden Tabelle wird beschrieben, welche Benutzer – Themenviewer, Mitwirkende und Wissensmanager – in einem bestimmten Thema basierend auf ihren Berechtigungen sehen können.

|Themenelement|Anzeige für Benutzer|
|:---------|:------------------|
|Themenname|Benutzer können den Themennamen der Themen im Themencenter sehen. Einige Themen sind möglicherweise nicht sichtbar, wenn Benutzer nicht über Berechtigungen für den Quellinhalt verfügen oder eine geringe Relevanz für den Benutzer haben.|
|Beschreibung des Themas|Von der KI generierten Beschreibungen sind nur für Benutzer sichtbar, die über Berechtigungen für den Quellinhalt verfügen. Manuell eingegebene oder bearbeitete Beschreibungen sind für alle Benutzer sichtbar.|
|Personen|Angeheftete Personen sind für alle Benutzer sichtbar. Vorgeschlagene Personen sind nur für Benutzer sichtbar, die über Berechtigungen für den Quellinhalt verfügen.|
|Dateien|Dateien sind nur für Benutzer sichtbar, die über Berechtigungen für den Quellinhalt verfügen.|
|Seiten|Seiten sind nur für Benutzer sichtbar, die über Berechtigungen für den Quellinhalt verfügen.|
|Websites|Websites sind nur für Benutzer sichtbar, die über Berechtigungen für den Quellinhalt verfügen.|

## <a name="users-personal-and-private-data"></a>Persönliche und private Daten von Benutzern

Viva Topics findet nur Themen in den von Ihnen angegebenen SharePoint Websites. Der persönliche Speicher der Benutzer, z. B. persönliche E-Mails oder OneDrive, ist nicht enthalten.

## <a name="best-practices"></a>Bewährte Methoden

Themen enthalten Informationen für Benutzer basierend auf ihren vorhandenen Berechtigungen für Inhalte. Microsoft 365 bietet eine Vielzahl von Möglichkeiten, um sicherzustellen, dass vertrauliche Inhalte auf geeignete Benutzer beschränkt sind. Über die standardmäßigen Team- oder Websiteberechtigungen hinaus können Sie [Vertraulichkeitsbezeichnungen](../compliance/sensitivity-labels.md) oder [Die Verhinderung von Datenverlust](../compliance/dlp-learn-about-dlp.md) verwenden, um den Zugriff auf Inhalte einzuschränken, und [Zugriffsüberprüfungen,](/azure/active-directory/governance/access-reviews-overview) um den Benutzerzugriff auf vertrauliche Informationen regelmäßig zu überprüfen.

Es wird empfohlen, diese Tools zu verwenden, um sicherzustellen, dass Ihre Inhaltsberechtigungen innerhalb Ihrer Organisation entsprechend festgelegt sind. Anschließend können Themenerfahrungen nützliche und passende Informationen für Ihre Benutzer bereitstellen.

Wenn Es Themen gibt, die Sie vollständig von der Themenerfahrung ausschließen möchten, können Sie auch Folgendes:

- [Schließen Sie vertrauliche SharePoint Websites von der Themensuche aus.](topic-experiences-discovery.md#select-sharepoint-topic-sources) Inhalte auf diesen Websites werden in der Themenerfahrung nicht angezeigt.

- [Themen nach Name ausschließen.](topic-experiences-discovery.md#exclude-topics-by-name) Themen, die explizit ausgeschlossen werden, werden in der Themenerfahrung nicht angezeigt.

- Wissensmanager müssen Themen im Themencenter entfernen.

Darüber hinaus empfehlen wir die folgenden bewährten Methoden:

- Rekrutieren von Wissensmanagern aus verschiedenen Bereichen Ihrer Organisation. Wissensmanager mit einer Vielzahl von Fachwissen – und Zugriff auf die zugrunde liegenden Inhalte, die von KI verwendet werden – können Ihnen dabei helfen, das nützlichste Wissen für Ihre Benutzer zu erstellen und vertrauliche Informationen zu entfernen, wenn sie gefunden werden.

- Richten Sie einen Workflow zum Anfordern von Änderungen ein. Wissensmanager oder Team- oder Websitebesitzer sollten über einen Prozess verfügen, mit dem sie den Ausschluss von Themen oder Websites anfordern können, wenn neue Projekte in Ihrer Organisation gestartet werden oder wenn sie Inhalte mit unangemessenen Berechtigungseinstellungen finden.

- Beachten Sie beim Erstellen von Themenbeschreibungen die Benutzergruppe und die Vertraulichkeit von Informationen. Diese Beschreibungen sind möglicherweise für Benutzer sichtbar, die nicht über Berechtigungen für den Quellinhalt des Themas verfügen.

Sie können zwar die Berechtigungen auf einzelnen Themenseiten ändern, um den Zugriff auf eine bestimmte Benutzergruppe einzuschränken, aber wegen des hohen Verwaltungsaufwands wird diese Vorgehensweise nicht empfohlen.

## <a name="see-also"></a>Siehe auch

[Konfigurieren von Microsoft Teams mit drei Schutzebenen](../solutions/configure-teams-three-tiers-protection.md)

[Topic Experiences planen](plan-topic-experiences.md)

[Topic Experiences einrichten](set-up-topic-experiences.md)
