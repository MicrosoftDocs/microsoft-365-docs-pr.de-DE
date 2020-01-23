---
title: Versionshinweise zu Microsoft Compliance Score
ms.author: chvukosw
author: chvukosw
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Versionshinweise und bekannte Probleme für Microsoft Compliance Score (Preview), ein Feature im M365 Compliance Center, das das vereinfachen und Automatisieren von Risikobewertungen erleichtert.
ms.openlocfilehash: 370c714c927d09a16272f8ab265c7b0c4e36381a
ms.sourcegitcommit: 5fc0f2cd1f2596fd10299333c826c501936dcd98
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/22/2020
ms.locfileid: "41261869"
---
# <a name="microsoft-compliance-score-preview-release-notes"></a>Versionshinweise zu Microsoft Compliance Score (Preview)

Die Public Preview of Microsoft Compliance Score bietet Ihnen frühzeitigen Zugriff auf bevorstehende Funktionen und Updates. Überprüfen Sie diese Seite häufig, um Neuigkeiten zu erfahren.

Compliance Score ist ein neues Feature im [Microsoft 365 Compliance Center](microsoft-365-compliance-center.md) , das eine risikobasierte Bewertung berechnet und den Fortschritt bei der Durchführung von empfohlenen Aktionen misst, die zur Verringerung der Compliance-Risiken beitragen.

## <a name="whats-new"></a>Neuerungen

### <a name="new-templates-for-assessments"></a>Neue Vorlagen für Bewertungen

Neue vorkonfigurierte Vorlagen für Bewertungen werden in Produktion für das Kompatibilitäts Ergebnis (Preview) veröffentlicht, sobald diese verfügbar werden. Überprüfen Sie die [vollständige Liste der Vorlagen hier](compliance-score.md#templates). Zu den zuletzt hinzugefügten Vorlagen gehören:

- Brasilien – allgemeine Datenschutz Gesetze (LGPD)
- IRAP/australische Regierung ISM (Vorschau)
- ISO 27701:2019
- SOC 1
- SOC 2

### <a name="compliance-score-relationship-to-compliance-manager"></a>Kompatibilitäts Bewertungspunkt-Beziehung zum Compliance-Manager

Viele der Compliance-Funktionen, die im Compliance-Manager behandelt werden, können jetzt in der Kompatibilitätsbewertung ausgeführt werden. Einige Funktionen befinden sich jedoch weiterhin nur im Compliance-Manager, und einige frühere Funktionen im Compliance-Manager werden während des öffentlichen Vorschauzeitraums geändert. 

Beachten Sie beim Arbeiten mit dem Kompatibilitäts Bewertungs-und Compliance-Manager während der öffentlichen Vorschau die folgenden Punkte:

- **Verwalten von Bewertungen**: Benutzer können Bewertungen und deren Statusdetails in der Kompatibilitätsbewertung anzeigen. Benutzer können jedoch nur Assessment-Verwaltungsaufgaben im Compliance-Manager ausführen ([Anweisungen anzeigen](working-with-compliance-manager.md#assessments)), und die Aufgaben sind auf Folgendes beschränkt:
    - Neue Bewertungen hochladen, jedoch vorhandene Bewertungen nicht ändern. Wenn Sie eine vorhandene Bewertung ändern müssen, müssen Sie eine neue Vorlage hochladen.
    - Export Bewertungen
    - Archiv Bewertungen
    - Anzeigen archivierter Bewertungen
 - **Erstellen von Vorlagen für Bewertungen**: 
   - Benutzer müssen zum Compliance-Manager wechseln, um neue Vorlagen zu erstellen und vorhandene Vorlagen zu exportieren. 
   - Vorhandene Vorlagen können nicht angepasst werden. Lesen Sie Anweisungen zum [Verwalten von Vorlagen im Compliance-Manager](working-with-compliance-manager.md#templates).
   - Beim Erstellen einer Vorlage müssen Sie Dimensionen für **Produkt** und **Zertifizierung** einschließen, um sicherzustellen, dass Ihre Vorlage im Kompatibilitäts Bewertungsergebnis angezeigt wird.
 - **Festlegen von Berechtigungen**: Konformitäts Bewertungs Benutzer, denen zuvor keine Berechtigungen im Compliance-Manager erteilt wurden, müssen Ihre Berechtigungen im Microsoft 365 Compliance Center festgelegt haben ([Weitere Informationen](compliance-score-setup.md#set-user-permissions-and-assign-roles)). Benutzer, deren Rollen zuvor im Compliance-Manager festgelegt wurden, können dieselbe Zugriffsebene verwenden, wenn Sie in der Kompatibilitätsbewertung arbeiten.
- **Übertragung von Daten**: Organisationen mit Daten, die sich im Compliance-Manager befinden, sehen diese Daten in der Kompatibilitätsbewertung und umgekehrt.
- **Anmelden beim Compliance-Manager aus Kompatibilitätsbewertung**: Wenn ein Benutzer bei der Kompatibilitätsbewertung angemeldet ist und einen Link auswählt, um zum Compliance-Manager zu wechseln, muss sich der Benutzer nicht erneut anmelden. Nachdem Sie auf den Link geklickt haben, wird in Ihrem Browser eine neue Registerkarte mit einem Dialogfeld geöffnet. Im oberen Abschnitt mit dem Header "bereits Microsoft Cloud Services-Kunde? Melden Sie sich bei Ihrem Konto an, "wählen Sie die Schaltfläche **Anmelden** aus, um sich automatisch beim Compliance-Manager anzumelden.

## <a name="known-issues-in-compliance-score-preview"></a>Bekannte Probleme in Compliance Score (Preview)

In den folgenden Abschnitten werden bekannte Probleme behandelt, die in bevorstehenden Versionen von Compliance Score behoben werden sollten.

### <a name="launch-now-links-in-certain-improvement-actions"></a>Jetzt starten Links in bestimmten Verbesserungs Aktionen

Bei bestimmten Verbesserungs Aktionen wird beim Auswählen des Hyperlinks **jetzt starten** , der unterhalb der Implementierungsanweisungen angezeigt wird, ein Fehler ausgegeben. Führen Sie die folgenden Schritte aus, um auf das richtige Ziel (SharePoint Admin Center) zuzugreifen:

1. Wechseln Sie zum [Microsoft 365 Admin Center](https://admin.microsoft.com).
2. Wählen Sie im linken Navigationsmenü die Option **Alle anzeigen**aus.
3. Wählen Sie unter **Admin Center** die Option **SharePoint**aus.

Im folgenden finden Sie die betroffenen Verbesserungs Aktionen, die sich alle in der Kategorie **Protect Information** befinden:
  - Anwenden der Verschlüsselung auf die SharePoint-Bibliothek
  - Klassifizieren von Daten in SharePoint Online
  - Konfigurieren externer Freigabe Links für Ablauf
  - Aktivieren der Versionsverwaltung für Dokumentbibliotheken

### <a name="long-load-times-for-non-admin-users"></a>Lange Ladezeiten für Benutzer ohne Administratorrechte
Kompatibilitätsbewertung Benutzer, die andere Rollen als eine Administratorrolle innehaben, können lange Ladezeiten beim Versuch einer Anmeldung auftreten. Wenn Sie den Browser aktualisieren, wird dieses Problem behoben. (Weitere Informationen finden Sie unter [Compliance Score Roles](compliance-score-setup.md#set-user-permissions-and-assign-roles).)

### <a name="supported-browsers"></a>Unterstützte Browser

- Die neuesten Versionen von Microsoft Edge, Chrome und Safari werden unterstützt.
- Es gibt möglicherweise Fälle, in denen aktualisierte Daten erst angezeigt werden, wenn Ihr Browser aktualisiert wurde.
- Die Preview-Version von Microsoft Edge wird nicht unterstützt, aber es sind keine bekannten Probleme aufgetreten.
- Internet Explorer wird nicht unterstützt.
 
### <a name="language-support"></a>Sprachunterstützung

- Das Kompatibilitäts Ergebnis steht nur in Englisch (USA) zur Verfügung.