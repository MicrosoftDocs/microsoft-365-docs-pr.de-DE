---
title: Versionshinweise zu Microsoft Compliance Score
f1.keywords:
- NOCSH
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
ms.openlocfilehash: 1567921b8bd07b0fe4deda0bab6601898eed75a9
ms.sourcegitcommit: 56772bed89516cebc5eb370e292ccfbb4889cb38
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2020
ms.locfileid: "44330779"
---
# <a name="microsoft-compliance-score-preview-release-notes"></a>Versionshinweise zu Microsoft Compliance Score (Preview)

Die Public Preview of Microsoft Compliance Score bietet Ihnen frühzeitigen Zugriff auf bevorstehende Funktionen und Updates. Überprüfen Sie diese Seite häufig, um Neuigkeiten zu erfahren.

Compliance Score ist ein neues Feature im [Microsoft 365 Compliance Center](microsoft-365-compliance-center.md) , das eine risikobasierte Bewertung berechnet und den Fortschritt bei der Durchführung von empfohlenen Aktionen misst, die zur Verringerung der Compliance-Risiken beitragen.

## <a name="new-templates-for-assessments"></a>Neue Vorlagen für Bewertungen

Neue vorkonfigurierte Vorlagen für Bewertungen werden in Produktion für das Kompatibilitäts Ergebnis (Preview) veröffentlicht, sobald diese verfügbar werden. Überprüfen Sie die [vollständige Liste der Vorlagen hier](compliance-score.md#templates). Zu den zuletzt hinzugefügten Vorlagen gehören:

- Brasilien – allgemeine Datenschutz Gesetze (LGPD)
- Dubai Information Security Resolution (DGISR)
- IRAP/australische Regierung ISM (Vorschau)
- ISO 27701:2019
- SOC 1
- SOC 2

## <a name="improvements-in-managing-assessments"></a>Verbesserungen bei der Verwaltung von Bewertungen

Die neueste Version von Compliance-Manager im April 2020 enthält Updates, die das Erstellen und Anpassen von Bewertungen vereinfachen und Sie auf dem neuesten Stand halten. Details finden Sie in den Versionshinweisen zu [Compliance-Manager](compliance-manager-release-notes.md) .

## <a name="language-support"></a>Sprachunterstützung

Das Kompatibilitäts Ergebnis steht nun zusätzlich zu Englisch in den folgenden Sprachen zur Verfügung: Chinesisch (vereinfacht), Chinesisch (traditionell), Französisch, Deutsch, Italienisch, Japanisch, Koreanisch, Portugiesisch (Brasilien), Russisch und Spanisch.

## <a name="common-actions-will-synch-status-across-groups"></a>Häufige Aktionen synchronisieren den Status über Gruppen hinweg.

Wenn Ihre Organisation über mehrere Bewertungsgruppen verfügt, hat sich das Verhalten von **technischen** Aktionen (also Aktionen, die sich auf Ihre gesamte Organisation auswirken) geändert. Doppelte Aktionen in mehreren Gruppen wurden zu einer einzigen Aktion zusammengefasst. Diese einzelne Aktion enthält alle hochgeladenen Notizen und Beweise aus den doppelten Versionen. Durch diese Änderung verhalten sich technische Aktionen nun so, wie Sie es in der gleichen Gruppe getan haben. Alle Änderungen, die an der Aktion in einer Gruppe oder Bewertung vorgenommen werden, werden nun in allen Instanzen wiedergegeben. Der **Implementierungsstatus**, das **Implementierungsdatum**, der **Test Status**und das **Test Datum**   spiegeln die neuesten Aktualisierungen wider.

## <a name="compliance-score-relationship-to-compliance-manager"></a>Kompatibilitäts Bewertungspunkt-Beziehung zum Compliance-Manager

Viele der Funktionen, die im Compliance-Manager verarbeitet werden, können jetzt in der Kompatibilitätsbewertung ausgeführt werden. Einige Funktionen sind jedoch weiterhin im Compliance-Manager zu beleben. Beachten Sie beim Arbeiten mit dem Kompatibilitäts Bewertungs-und Compliance-Manager während der öffentlichen Vorschau die folgenden Punkte:

- **Verwalten von Bewertungen**: Benutzer können Bewertungen und deren Statusdetails in der Kompatibilitätsbewertung anzeigen. Benutzer können jedoch nur Assessment-Verwaltungsaufgaben im Compliance-Manager ausführen ([Anweisungen anzeigen](working-with-compliance-manager.md#assessments)). Beispiele für diese Aufgaben sind:
    - Erstellen und Kopieren von Bewertungen
    - Export Bewertungen
    - Archiv Bewertungen
    - Anzeigen archivierter Bewertungen
 - **Erstellen von Vorlagen für Bewertungen**: 
   - Benutzer müssen zum Compliance-Manager wechseln, um neue Vorlagen zu erstellen und vorhandene [Vorlagen](working-with-compliance-manager.md#templates)zu ändern. 
   - Beim Erstellen einer Vorlage müssen Sie Dimensionen für **Produkt** und **Zertifizierung** einschließen, um sicherzustellen, dass Ihre Vorlage im Kompatibilitäts Bewertungsergebnis angezeigt wird.
 - **Festlegen von Berechtigungen**: Benutzer, die noch nicht über Berechtigungen im Compliance-Manager verfügen, müssen Ihre Berechtigungen im Microsoft 365 Compliance Center festgelegt haben ([Weitere Informationen](compliance-score-setup.md#set-user-permissions-and-assign-roles)).
- **Übertragung von Daten**: Organisationen mit Daten im Compliance-Manager sehen diese Daten in der Kompatibilitätsbewertung, und das gleiche gilt umgekehrt.
- **Anmelden beim Compliance-Manager aus Kompatibilitätsbewertung**: Wenn ein Benutzer bei der Kompatibilitätsbewertung angemeldet ist und einen Link auswählt, um zum Compliance-Manager zu wechseln, muss sich der Benutzer nicht erneut anmelden. Nachdem Sie auf den Link geklickt haben, wird in Ihrem Browser eine neue Registerkarte mit einem Dialogfeld geöffnet. Im oberen Abschnitt mit dem Header "bereits Microsoft Cloud Services-Kunde? Melden Sie sich bei Ihrem Konto an, "wählen Sie die Schaltfläche **Anmelden** aus, um sich automatisch beim Compliance-Manager anzumelden.

## <a name="known-issues-in-compliance-score-preview"></a>Bekannte Probleme in Compliance Score (Preview)

In den folgenden Abschnitten werden bekannte Probleme behandelt, die in bevorstehenden Versionen von Compliance Score behoben werden sollten.

### <a name="long-load-times-for-non-admin-users"></a>Lange Ladezeiten für Benutzer ohne Administratorrechte
Kompatibilitätsbewertung Benutzer, die andere Rollen als eine Administratorrolle innehaben, können lange Ladezeiten beim Versuch einer Anmeldung auftreten. Wenn Sie den Browser aktualisieren, wird dieses Problem behoben. (Weitere Informationen finden Sie unter [Compliance Score Roles](compliance-score-setup.md#set-user-permissions-and-assign-roles).)

### <a name="supported-browsers"></a>Unterstützte Browser

- Die neuesten Versionen von Microsoft Edge, Chrome und Safari werden unterstützt.
- Aktualisierte Daten werden manchmal erst angezeigt, wenn Ihr Browser aktualisiert wurde.
- Internet Explorer wird nicht unterstützt.
