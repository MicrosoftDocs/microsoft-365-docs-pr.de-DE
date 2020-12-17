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
monikerRange: o365-worldwide
search.appverid:
- BCS160
- MET150
- MOE150
description: Hier erfahren Sie, wie Sie Sensitivitäts Bezeichnungen erstellen und verwalten.
ms.openlocfilehash: ff3f7eb5ffddf797e254fac0ed8fc87d96940455
ms.sourcegitcommit: f231eece2927f0d01072fd092db1eab15525bbc2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/17/2020
ms.locfileid: "49702397"
---
# <a name="protect-documents-with-sensitivity-labels"></a>Schützen von Dokumenten mit Vertraulichkeits Bezeichnungen

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3VRGT?autoplay=false]

Mit Sensitivitäts Bezeichnungen können Sie Inhalte klassifizieren und schützen, die für Ihr Unternehmen vertraulich sind.

## <a name="try-it"></a>Probieren Sie es aus!

1. Wählen Sie im [Admin Center](https://admin.microsoft.com)das **Compliance** Admin Center aus.
1. Wählen Sie **Klassifizierung** und dann **Vertraulichkeits Bezeichnungen** aus.
1. Wählen Sie **Create a Label** aus, und wählen Sie wenn die Warnung angezeigt wird, **Ja** aus.
1. Geben Sie einen **Bezeichnungsnamen**, eine **QuickInfo** und eine **Beschreibung** ein. Wählen Sie **Weiter** aus.
1. Aktivieren Sie die **Verschlüsselung**. Wählen Sie aus, wann Berechtigungen zugewiesen werden sollen, ob der Zugriff der Benutzer auf die Inhalte ablaufen soll und ob Sie Offlinezugriff gewähren möchten.
1. **Wählen Sie Berechtigungen zuweisen aus**, und fügen Sie dann **diese e-Mail-Adressen oder Domänen hinzu**.
1. Geben Sie eine e-Mail-Adresse oder einen Domänennamen ein (beispielsweise contoso.org).  Wählen Sie **Hinzufügen** und wiederholen Sie diese Schritte für jede e-Mail-Adresse oder Domäne, die Sie hinzufügen möchten.
1. Wählen Sie **Berechtigungen aus Vorgabe oder Benutzerdefiniert auswählen aus**.
1. Verwenden Sie die Dropdownliste, um vordefinierte Berechtigungen wie **Prüfer** oder **Viewer** auszuwählen, oder wählen Sie **benutzerdefinierte** Berechtigungen aus. Wenn Sie **Benutzerdefiniert** ausgewählt haben, wählen Sie die Berechtigungen aus der Liste aus. Klicken Sie auf **Speichern**, **Speichern** und dann auf **weiter**.
1. Aktivieren Sie die **Inhalts Markierung**, und wählen Sie die Markierungen aus, die Sie verwenden möchten.
1. Wählen Sie für jede Markierung, die Sie auswählen, **Text anpassen** aus. Geben Sie den Text ein, der im Dokument angezeigt werden soll, und legen Sie die Optionen für Schriftart und Layout fest. Wählen Sie **Speichern** aus, und wiederholen Sie diese Option, um weitere Markierungen zu erhalten. Wählen Sie **Weiter** aus.
1. Aktivieren Sie optional die **Verhinderung von Endpunkt Datenverlust**. Wählen Sie **Weiter** aus.
1. Aktivieren Sie optional die **Automatische Kennzeichnung**. Fügen Sie eine Bedingung hinzu. Wählen Sie beispielsweise unter **Inhalt ermitteln, der enthält die** Option **Bedingung hinzufügen** aus. Geben Sie die Bedingung ein; Fügen Sie beispielsweise eine Bedingung hinzu, dass wenn Passport, soziale Sicherheit oder andere vertrauliche Informationen erkannt werden, die Bezeichnung hinzugefügt wird. Wählen Sie **Weiter** aus.
1. Überprüfen Sie Ihre Einstellungen, und wählen Sie **Erstellen** aus. Ihre Bezeichnung wurde erstellt. Wiederholen Sie diesen Vorgang für alle gewünschten zusätzlichen Bezeichnungen.
1. Standardmäßig werden Bezeichnungen in Office-Apps in dieser Reihenfolge angezeigt: **vertraulich**, **intern** und **öffentlich**. Um die Reihenfolge für jede Beschriftung zu ändern, wählen Sie **Weitere Aktionen** (die Auslassungspunkte) aus, und ziehen Sie die Beschriftung dann nach oben oder unten. Normalerweise werden Berechtigungen von der niedrigsten bis zur höchsten Berechtigungsstufe aufgeführt.
1. Wenn Sie einer Bezeichnung eine unter Bezeichnung hinzufügen möchten, wählen Sie **Weitere Aktionen** und dann **unter Ebene hinzufügen** aus.
1. Wenn Sie fertig sind, wählen Sie **Bezeichnungen veröffentlichen** aus, **Wählen Sie Beschriftungen zum Veröffentlichen** aus, und fügen Sie dann **hinzu**. Wählen Sie die Beschriftungen aus, die Sie veröffentlichen möchten, und klicken Sie dann auf **Hinzufügen**, **Fertig** und dann auf **weiter**.
1. Standardmäßig wird die neue Bezeichnungsrichtlinie auf alle Benutzer angewendet. Wenn Sie einschränken möchten, auf wen die Richtlinie angewendet wird, wählen Sie **Benutzer oder Gruppen auswählen** und dann **Hinzufügen** aus. Wählen Sie die Person aus, auf die die Richtlinie angewendet werden soll, und klicken Sie dann auf **Hinzufügen**, **Fertig** und dann auf **weiter**.
1. Wenn Sie eine Standardbezeichnung für Dokumente und e-Mails wünschen, wählen Sie in der Dropdownliste die gewünschte Bezeichnung aus. Überprüfen Sie die verbleibenden Einstellungen, passen Sie Sie bei Bedarf an, und wählen Sie dann **weiter** aus.
1. Geben Sie einen **Namen** und eine **Beschreibung** für Ihre Richtlinie ein. Wählen Sie **Weiter** aus.
1. Überprüfen Sie Ihre Einstellungen, und wählen Sie dann **veröffentlichen** aus.

Damit ihre Beschriftungen funktionieren, muss jeder Benutzer den Azure Information Protection Unified Labeling-Client herunterladen. Suchen Sie im Internet nach **AzinfoProtection_UL.exe**, laden Sie es dann aus dem Microsoft Download Center herunter, und führen Sie es auf den Computern Ihrer Benutzer aus.

Wenn Sie das nächste Mal eine Office-App wie Word öffnen, werden die erstellten Sensitivitäts Bezeichnungen angezeigt. Wählen Sie zum Ändern oder Anwenden einer Bezeichnung die Option Empfindlichkeit aus, und wählen Sie eine Bezeichnung aus.

