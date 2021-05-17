---
title: Erstellen von Vertraulichkeitsbezeichnungen
f1.keywords:
- NOCSH
ms.author: efrene
author: efrene
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- adminvideo
monikerRange: o365-worldwide
search.appverid:
- BCS160
- MET150
- MOE150
description: Erfahren Sie, wie Sie Vertraulichkeitsbezeichnungen erstellen und verwalten.
ms.openlocfilehash: 997b05ba549d3dc57e1793585331dfcfae1e277b
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/02/2021
ms.locfileid: "51578939"
---
# <a name="protect-documents-with-sensitivity-labels"></a>Schützen von Dokumenten mit Vertraulichkeitsbezeichnungen

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3VRGT?autoplay=false]

Vertraulichkeitsbezeichnungen ermöglichen ihnen das Klassifizieren und Schützen von Inhalten, die für Ihr Unternehmen sensibel sind.

## <a name="try-it"></a>Probieren Sie es aus!

1. Wählen Sie [im Admin Center](https://admin.microsoft.com)das Compliance **Admin** Center aus.
1. Wählen **Sie Klassifizierung** und dann **Vertraulichkeitsbezeichnungen aus.**
1. Wählen **Sie Bezeichnung erstellen** aus, und wenn die Warnung angezeigt wird, wählen Sie Ja **aus.**
1. Geben Sie **einen Bezeichnungsnamen,** **eine QuickInfo** und eine **Beschreibung ein.** Wählen Sie **Weiter** aus.
1. Aktivieren Sie **Verschlüsselung**. Wählen Sie aus, wann Sie Berechtigungen zuweisen möchten, ob der Zugriff ihrer Benutzer auf den Inhalt ablaufen soll und ob Sie den Offlinezugriff zulassen möchten.
1. **Wählen Sie Berechtigungen zuweisen** aus, und fügen **Sie dann diese E-Mail-Adressen oder Domänen hinzu.**
1. Geben Sie eine E-Mail-Adresse oder einen Domänennamen ein (z. B. Contoso.org).  Wählen **Sie Hinzufügen** aus, und wiederholen Sie dies für jede E-Mail-Adresse oder Domäne, die Sie hinzufügen möchten.
1. Wählen **Sie Berechtigungen aus voreingestellten oder benutzerdefinierten auswählen aus.**
1. Wählen Sie in der Dropdownliste voreingestellte Berechtigungen aus, z. B. **Reviewer** oder **Viewer,** oder **wählen** Sie Benutzerdefinierte Berechtigungen aus. Wenn Sie Custom **ausgewählt** haben, wählen Sie die Berechtigungen aus der Liste aus. Wählen **Sie Speichern**, **Speichern** und dann **Weiter aus.**
1. Aktivieren Sie **die Inhaltsmarkierung,** und wählen Sie die zu verwendenden Markierungen aus.
1. Wählen Sie für jede ausgewählte Markierung text **anpassen aus.** Geben Sie den Text ein, der im Dokument angezeigt werden soll, und legen Sie die Schriftart- und Layoutoptionen festlegen. Wählen **Sie Speichern** aus, und wiederholen Sie dann alle zusätzlichen Markierungen. Wählen Sie **Weiter** aus.
1. Aktivieren Sie optional endpoint **data loss prevention**. Wählen Sie **Weiter** aus.
1. Aktivieren Sie optional die **automatische Bezeichnung**. Fügen Sie eine Bedingung hinzu. Wählen Sie beispielsweise unter **Inhalt erkennen, der enthält,** die Option **Bedingung hinzufügen aus.** Geben Sie die Bedingung ein. Fügen Sie beispielsweise eine Bedingung hinzu, dass die Bezeichnung hinzugefügt wird, wenn Reisepass, Sozialversicherung oder andere vertrauliche Informationen erkannt werden. Wählen Sie **Weiter** aus.
1. Überprüfen Sie Ihre Einstellungen, und wählen Sie **Erstellen aus.** Ihre Bezeichnung wurde erstellt. Wiederholen Sie diesen Vorgang für beliebige zusätzliche Bezeichnungen.
1. Standardmäßig werden Bezeichnungen in Office in der reihenfolge **angezeigt: Vertraulich,** **Intern** und **Öffentlich**. Um die Reihenfolge zu ändern, wählen Sie für jede Bezeichnung weitere Aktionen **(die** Auslassungspunkte) aus, und verschieben Sie dann die Bezeichnung nach oben oder unten. In der Regel werden Berechtigungen von der niedrigsten bis zur höchsten Berechtigungsstufe aufgelistet.
1. Wenn Sie einer Bezeichnung eine Unterbezeichnung hinzufügen möchten, wählen Sie **Weitere Aktionen** und dann **Unterebene hinzufügen aus.**
1. Wählen Sie nach Abschluss **der Option Bezeichnungen veröffentlichen,** **zu veröffentlichende Bezeichnungen** auswählen und dann **Hinzufügen aus.** Wählen Sie die Bezeichnungen aus, die Sie veröffentlichen möchten, und wählen Sie **dann Hinzufügen**, **Fertig** und dann **Weiter aus.**
1. Standardmäßig wird die neue Bezeichnungsrichtlinie auf alle angewendet. Wenn Sie einschränken möchten, auf wen die Richtlinie angewendet wird, wählen Sie **Benutzer** oder Gruppen auswählen und dann **Hinzufügen aus.** Wählen Sie aus, auf wen die Richtlinie angewendet werden soll, und wählen Sie **dann Hinzufügen**, **Fertig** und dann **Weiter aus.**
1. Wenn Sie eine Standardbezeichnung für Dokumente und E-Mails wünschen, wählen Sie in der Dropdownliste die zu verwendende Bezeichnung aus. Überprüfen Sie die verbleibenden Einstellungen, passen Sie sie nach Bedarf an, und wählen Sie dann **Weiter aus.**
1. Geben Sie **einen Namen** und **eine Beschreibung** für Ihre Richtlinie ein. Wählen Sie **Weiter** aus.
1. Überprüfen Sie Ihre Einstellungen, und wählen Sie dann **Veröffentlichen aus.**

Damit Ihre Bezeichnungen funktionieren, muss jeder Benutzer den Azure Information Protection Unified Labeling-Client herunterladen. Durchsuchen Sie das Web **nachAzinfoProtection_UL.exe,** laden Sie es dann aus dem Microsoft Download Center herunter, und führen Sie es auf den Computern Ihrer Benutzer aus.

Wenn Sie das nächste Mal ein Office-App wie Word öffnen, werden die erstellten Vertraulichkeitsbezeichnungen angezeigt. Wählen Sie Vertraulichkeit aus, und wählen Sie eine Bezeichnung aus, um eine Bezeichnung zu ändern oder anzuwenden.

