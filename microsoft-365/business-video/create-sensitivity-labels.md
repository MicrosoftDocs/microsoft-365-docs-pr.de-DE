---
title: Erstellen von Vertraulichkeitsbezeichnungen
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- adminvideo
- okr_smb
monikerRange: o365-worldwide
search.appverid:
- BCS160
- MET150
- MOE150
description: Erfahren Sie, wie Sie Vertraulichkeitsbezeichnungen erstellen und verwalten.
ms.openlocfilehash: c8d528e7a742ca60345def415ce47b29b371c738
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/22/2021
ms.locfileid: "49927322"
---
# <a name="protect-documents-with-sensitivity-labels"></a>Schützen von Dokumenten mit Vertraulichkeitsbezeichnungen

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3VRGT?autoplay=false]

Mit Vertraulichkeitsbezeichnungen können Sie Inhalte klassifizieren und schützen, die für Ihr Unternehmen vertraulich sind.

## <a name="try-it"></a>Probieren Sie es aus!

1. Wählen Sie [im Admin Center](https://admin.microsoft.com)das Compliance **Admin** Center aus.
1. Wählen Sie **"Klassifizierung"** und dann **"Vertraulichkeitsbezeichnungen" aus.**
1. Wählen **Sie "Bezeichnung erstellen"** aus, und wenn die Warnung angezeigt wird, wählen Sie **"Ja" aus.**
1. Geben Sie einen **Bezeichnungsnamen,** **eine QuickInfo** und eine **Beschreibung ein.** Wählen Sie **Weiter** aus.
1. Aktivieren Sie **verschlüsselung**. Wählen Sie aus, wann Sie Berechtigungen zuweisen möchten, ob der Zugriff ihrer Benutzer auf die Inhalte ablaufen soll und ob Sie den Offlinezugriff zulassen möchten.
1. **Wählen Sie "Berechtigungen zuweisen"** aus, und **fügen Sie diese E-Mail-Adressen oder Domänen hinzu.**
1. Geben Sie eine E-Mail-Adresse oder einen Domänennamen ein (z. B. Contoso.org).  Wählen **Sie "Hinzufügen"** aus, und wiederholen Sie dies für jede E-Mail-Adresse oder Domäne, die Sie hinzufügen möchten.
1. Wählen **Sie "Berechtigungen aus voreingestellter oder benutzerdefinierter Berechtigung auswählen" aus.**
1. Verwenden Sie die Dropdownliste, um voreingestellte Berechtigungen auszuwählen, z. B. **"Reviewer"** oder **"Viewer",** oder **"Benutzerdefinierte Berechtigungen".** Wenn Sie **"Benutzerdefiniert"** ausgewählt haben, wählen Sie die Berechtigungen aus der Liste aus. Wählen **Sie "Speichern",** **"Speichern"** und dann **"Weiter" aus.**
1. Aktivieren Sie **die Inhaltskennzeichnung,** und wählen Sie die zu verwendenden Markierungen aus.
1. Wählen Sie für jede ausgewählte Markierung Text **anpassen aus.** Geben Sie den Text ein, der im Dokument angezeigt werden soll, und legen Sie die Schriftart und layoutoptionen. Wählen **Sie "Speichern"** aus, und wiederholen Sie dann alle weiteren Markierungen. Wählen Sie **Weiter** aus.
1. Optional können Sie die Verhinderung von **Datenverlust am Endpunkt aktivieren.** Wählen Sie **Weiter** aus.
1. Optional können Sie die automatische **Bezeichnung aktivieren.** Fügen Sie eine Bedingung hinzu. Wählen Sie beispielsweise unter **"Inhalt erkennen, der enthält"** die Option **"Bedingung hinzufügen" aus.** Geben Sie die Bedingung ein; Fügen Sie beispielsweise eine Bedingung hinzu, dass die Bezeichnung hinzugefügt wird, wenn Passport, Sozialversicherung oder andere vertrauliche Informationen erkannt werden. Wählen Sie **Weiter** aus.
1. Überprüfen Sie Ihre Einstellungen, und wählen Sie **"Erstellen" aus.** Ihre Bezeichnung wurde erstellt. Wiederholen Sie diesen Vorgang für alle zusätzlichen Bezeichnungen, die Sie verwenden möchten.
1. Standardmäßig werden Bezeichnungen in den Office-Apps in dieser Reihenfolge angezeigt: **Vertraulich,** **Intern** und **Öffentlich.** Um die Reihenfolge zu ändern, wählen Sie für jede Bezeichnung weitere Aktionen **(die** Auslassungspunkte) aus, und verschieben Sie die Beschriftung nach oben oder unten. In der Regel werden Berechtigungen von der niedrigsten bis zur höchsten Berechtigungsstufe aufgeführt.
1. Wenn Sie einer Bezeichnung eine Unterbezeichnung hinzufügen möchten, wählen Sie **"Weitere Aktionen"** und dann **"Unterebene hinzufügen" aus.**
1. Wenn Sie fertig sind, wählen **Sie "Bezeichnungen veröffentlichen",** **"Zu veröffentlichende** Bezeichnungen auswählen" und dann **"Hinzufügen" aus.** Wählen Sie die Bezeichnungen aus, die Sie veröffentlichen möchten, und wählen Sie dann **"Hinzufügen",** **"Fertig"** und dann "Weiter" **aus.**
1. Standardmäßig wird die neue Bezeichnungsrichtlinie auf alle angewendet. Wenn Sie einschränken möchten, auf wen die Richtlinie angewendet wird, wählen **Sie "Benutzer** oder Gruppen auswählen" und dann "Hinzufügen" **aus.** Wählen Sie aus, auf wen die Richtlinie angewendet werden soll, und wählen Sie dann "Hinzufügen", **"Fertig"** und dann "Weiter" **aus.**
1. Wenn Sie eine Standardbezeichnung für Dokumente und E-Mails wünschen, wählen Sie die bezeichnung aus der Dropdownliste aus. Überprüfen Sie die verbleibenden Einstellungen, passen Sie sie nach Bedarf an, und wählen Sie dann **"Weiter" aus.**
1. Geben Sie **einen Namen** und **eine Beschreibung** für Ihre Richtlinie ein. Wählen Sie **Weiter** aus.
1. Überprüfen Sie Ihre Einstellungen, und wählen Sie dann Veröffentlichen **aus.**

Damit Ihre Bezeichnungen funktionieren, muss jeder Benutzer den Azure Information Protection-Client für einheitliche Bezeichnungen herunterladen. Durchsuchen Sie das Web **nachAzinfoProtection_UL.exe,** laden Sie es aus dem Microsoft Download Center herunter, und führen Sie es auf den Computern Ihrer Benutzer aus.

Wenn Sie das nächste Mal eine Office-App wie Word öffnen, werden die erstellten Vertraulichkeitsbezeichnungen angezeigt. Um eine Bezeichnung zu ändern oder anzuwenden, wählen Sie "Vertraulichkeit" und dann eine Bezeichnung aus.

