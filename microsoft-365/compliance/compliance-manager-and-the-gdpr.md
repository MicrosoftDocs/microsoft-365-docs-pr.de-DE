---
title: Microsoft Compliance Manager und die DSGVO
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Microsoft Compliance Manager ist ein kostenloses, Workflow-basiertes Tool zur Risikobewertung im Microsoft Service Trust-Portal. Mit Compliance Manager können Sie gesetzliche Compliance-Aktivitäten im Zusammenhang mit Microsoft Cloud-Diensten verfolgen, zuweisen und überprüfen.
ms.openlocfilehash: 69e6551620fb654cb09d46554e6e3c98b6a2fc60
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2020
ms.locfileid: "41595802"
---
# <a name="microsoft-compliance-manager-and-the-gdpr"></a>Microsoft Compliance Manager und die DSGVO

Die von der Europäischen Union erlassene Allgemeine Datenschutzverordnung (DSGVO) kann sich auf Ihre Compliance-Strategie auswirken und spezifische Maßnahmen zur Verwaltung der im Compliance Manager verwendeten Benutzer- und Kundeninformationen vorschreiben.

## <a name="user-privacy-settings"></a>Datenschutzeinstellungen

Bestimmte Vorschriften erfordern, dass eine Organisation in der Lage sein muss, Verlaufsdaten von Benutzern zu löschen. Der Compliance-Manager bietet Funktionen für **Datenschutzeinstellungen**, mit denen Administratoren folgende Aufgaben ausführen können:
  
- [Suchen eines Benutzers](#search-for-a-user)
- [Exportieren eines Berichts mit Kontoverlaufsdaten](#export-a-report-of-account-data-history)
- [Löschen der Verlaufsdaten von Benutzern](#delete-user-data-history)
  
## <a name="search-for-a-user"></a>Suchen eines Benutzers

So suchen Sie nach einem Benutzerkonto
  
1. Geben Sie den E-Mail-Alias des Benutzers ein (die Informationen links vom @-Symbol) und wählen Sie den Domänennamen aus der Liste der Domänensuffixe auf der rechten Seite aus. Bei Organisationen mit mehreren registrierten Domänen überprüfen Sie das Domänensuffix, um sicherzustellen, dass es korrekt ist.

2. Wenn Sie den Benutzernamen richtig eingegeben haben, wählen Sie **Suche**.

3. Bei Benutzerkonten, die nicht zurückgegeben werden, wird auf der Seite angezeigt: **Benutzer nicht gefunden**. Überprüfen Sie die E-Mail-Adressinformationen des Benutzers, und nehmen Sie bei Bedarf Korrekturen vor. Um es erneut zu versuchen, wählen Sie **Suche** aus.

4. Bei zurückgegebenen Benutzerkonten ändert sich der Text der Schaltfläche von **Suche** in **Löschen**. Dies weist darauf hin, dass das zurückgegebene Benutzerkonto der Betriebssystemkontext für die zusätzlichen Funktionen ist und dass diese Funktionen für dieses Benutzerkonto gelten.

5. Um Suchergebnisse zu löschen und nach einem anderen Benutzer zu suchen, wählen Sie **Löschen**.

## <a name="export-a-report-of-account-data-history"></a>Exportieren eines Berichts mit Kontoverlaufsdaten

Für jedes identifizierte Benutzerkonto können Sie einen Bericht der mit dem Konto verknüpften Abhängigkeiten generieren. Diese Informationen ermöglichen es Ihnen, geöffnete Aktionselemente erneut zuzuweisen oder den Zugriff auf zuvor hochgeladene Nachweise sicherzustellen.
  
 So generieren und exportieren Sie einen Bericht:
  
1. Klicken Sie auf **Exportieren**, um einen Bericht über die Compliance Manager-Steuerelement-Aktionselemente zu generieren und herunterzuladen, die derzeit dem zurückgegebenen Benutzerkonto zugewiesen sind, sowie die Liste der von diesem Benutzer hochgeladenen Dokumente. Wenn keine zugewiesenen Aktionen oder hochgeladenen Dokumente enthalten sind, wird in einer Fehlermeldung „Keine Daten für diesen Benutzer“ angezeigt.

2. Der Bericht wird im Hintergrund des aktiven Browserfensters heruntergeladen, wenn kein Popupfenster für Downloads angezeigt wird, das Sie im Downloadverlauf Ihres Browsers überprüfen sollten.

3. Öffnen Sie das Dokument, um die Berichtsdaten zu überprüfen.

> [!IMPORTANT]
> Die Berichtsdaten sind keine Verlaufsliste, in der Zustandsänderungen des Zuordnungsverlaufs für Aktionselement beibehalten und angezeigt werden. Der generierte Bericht ist eine Momentaufnahme des Steuerelements "Aktionen", das zum Zeitpunkt der Ausführung des Berichts zugewiesen wurde (Datums- und Zeitstempel, der in den Bericht geschrieben wurde). Beispielsweise führt jede nachfolgende Neusignierung von Aktionselementen zu unterschiedlichen Momentaufnahmeberichtsdaten, wenn der Bericht für denselben Benutzer erneut generiert wird.
  
## <a name="delete-user-data-history"></a>Löschen der Verlaufsdaten von Benutzern

Setzt alle dem zurückgegebenen Benutzer zugewiesenen Steuerungsaktionselemente auf "nicht zugewiesen" fest. Legt den Wert für **hochgeladen von** für jegliche Dokumente, die vom zurückgegebenen Benutzer hochgeladen wurden, auf "Benutzer entfernt" fest.
  
So löschen Sie das Aktionselement für das Benutzerkonto und den Uploadverlauf des Dokuments:
  
1. Klicken Sie auf **Löschen**.

    Es wird ein Bestätigungsdialogfeld angezeigt: „*Dadurch werden alle Steuerelementzuweisungen des Aktionselements und der Verlauf des Dokumentuploads für den ausgewählten Benutzer entfernt. Diese Aktion ist dauerhaft. Möchten Sie wirklich fortfahren?*“

2. Um fortzufahren, wählen Sie **OK** aus, andernfalls **Abbrechen**.
