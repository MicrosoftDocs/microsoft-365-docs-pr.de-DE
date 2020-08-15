---
title: Beispiel für eine allgemeine Bereitstellung der neuesten Versionen
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
ms.date: 07/21/2020
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- Strat_O365_Enterprise
- M365-subscription-management
ms.custom: ''
description: Die Art und Weise, in der eine Organisation, die die neueste Version bereitstellt, Kanäle für Windows 10- und Microsoft 365-Apps verwendet.
ms.openlocfilehash: fd1d8ddd342b2781470378c879ef70d2ba304316
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46686166"
---
# <a name="example-of-broad-deployment-for-the-latest-releases"></a>Beispiel für eine allgemeine Bereitstellung der neuesten Versionen

In diesem Beispiel für die Kanalkonfiguration handelt es sich um eine Organisation, die die schnelle Bereitstellung der neuesten Versionen verwendet, um die folgenden Unternehmensprioritäten zu erfüllen:

- Sicherstellen der Geschäftskontinuität mit Microsoft-Apps und -Diensten.
- Maximieren der Geräte-, Dienst- und Datensicherheit mit den neuesten Features und Updates von Microsoft.
- Maximieren der Benutzerproduktivität mit den neuesten Funktionen von Microsoft.

Aufgrund dieser Ziele muss ein Gleichgewicht zwischen schneller Produktionsbereitstellung und frühzeitiger Überprüfung mit einer repräsentativen Untergruppe von Benutzern und Geräten gefunden werden, um die Funktionalität vor der allgemeinen Bereitstellung zu validieren.

Unsere Beispielorganisation hat 5.000 Mitarbeiter in Gebäuden in Europa, Afrika, Asien und Amerika. 70 % der Mitarbeiter verwenden Microsoft 365 E3. der Rest der Organisation verwendet Microsoft 365 E5.

>[!Note]
>In diesem Beispiel wird gezeigt, wie Sie Bereitstellungsphasen und -gruppen verwenden können, die für Organisationen vieler Typen und Größen geeignet sind.
>

Die IT-Infrastruktur dieser Organisation: 

- Ist weitestgehend homogen (Windows, Microsoft 365-Apps und Microsoft-Cloud-Dienste machen 60 % der installierten Basis aus). Einige ältere Systeme bleiben nach intensiven mehrjährigen Anstrengungen zur Vereinfachung und Rationalisierung der IT-Infrastruktur erhalten.
- Wird von sehr erfahrenen Mitarbeitern gewartet, deren Aufgabe es ist, Benutzer und deren Geräte produktiv und sicher zu halten, indem sie sich in ihren Versionen an die Vorgaben von Microsoft halten.

## <a name="deployment-and-update-stages"></a>Phasen der Bereitstellung und Aktualisierung

Auf der Grundlage der schnellen Bereitstellungsziele der neuesten Version verwendet diese Beispielorganisation einen Bereitstellungsprozess in zwei Schritten.

1. **Verwenden einer Vorschau- oder Pilotbereitstellung:** Überprüfen Sie Early Adopters, IT-Mitarbeiter, Benutzer mit repräsentativen Konfigurationen und Schulungspersonal. 

   Die Early Adopters, IT-Mitarbeiter und Benutzer mit repräsentativen Konfigurationen können die Funktionalität mit anderen Apps und auf Geräten überprüfen, bevor die neuen Features für die übrige Organisation bereitgestellt werden.

   Änderungsmanager erhalten vorab einen Einblick in die neuen Features vor der allgemeinen Einführung und können die Bekanntgabe und den Rollout entsprechend planen.

   Schulungsmitarbeiter können neue interne Kurse planen oder vorhandene Kurse für die neuen Funktionen vor der allgemeinen Einführung aktualisieren.

2. **Produktionsbereitstellung:** Einführung für alle verbleibenden Benutzer nach Region, Abteilung oder einer anderen Bereitstellungsmethode.

## <a name="deployment-configuration-for-windows-10"></a>Bereitstellungskonfiguration für Windows 10

Das übergeordnete Ziel besteht darin, eine allgemeine Bereitstellung der neuesten halbjährlichen Kanalversion nach der Überprüfung der Änderungen an der Kanalversion (Vorschau) durch eine Gruppe von repräsentativen Benutzern und deren Geräten auszuführen.

Weitere Informationen zu den Bereitstellungsmethoden und-Strategien für Windows 10 finden Sie unter [Windows 10-Bereitstellung](https://docs.microsoft.com/windows/deployment/).

| Stufe | Kanal | Bereitstellungsgruppe |
|:-------|:-------|:-----|
| Pilotprojekt |  **Kanal der Versionsvorschau**  <ul><li>Zweck: Bereitstellung von Featureupdates für IT-Mitarbeiter und Early Adopters zur Validierung von repräsentativen Geräten und Konfigurationen (Sprachen, Apps von Drittanbietern). </li><li> Status: Vollständig kompatibel und für kommerzielle Kunden unterstützt, wird nicht auf Ihre Supportverträge angerechnet. </li></ul> | **Win10ReleasePreviewChannel** (Beispielname) <br><br> Mitglieder sind Gruppen, die Folgendes enthalten: <ul><li> Windows-Enthusiasten über Abteilungen und Standorte hinweg </li><li> Mitarbeiter mit Konfigurationen, die eine Überprüfung erfordern </li><li> IT-Administratoren und IT-Bereitstellungsmitarbeiter </li><li> Änderungsmanager </li><li> Interne Schulungsmitarbeiter </li></ul> |
| Produktion |  **Halbjährlicher Kanal**  <ul><li>Zweck: Allgemeine Bereitstellung der neuesten Featureupdates für den Rest der Organisation. </li><li> Status: Vollständig kompatibel und unterstützt. </li></ul> | **Win10SemiAnnualChannel** (Beispielname) <br><br> Mitglieder sind alle Benutzer, die sich nicht in der Win10ReleasePreviewChannel-Gruppe befinden. |
||||

Diese Organisation verwendet die bewährten Methoden der Nutzlast der aktuellen Kanalversion auf die gleiche Weise wie die Bereitstellung von halbjährlichen Kanalversionen, z. B. Windows Update oder Windows Server Update Services. Außerdem werden dieselben Richtlinien für beide Kanalupdates angewendet.

Fortlaufender Updateprozess:

1. Änderungen am Versionsvorschaukanal werden im Win10ReleasePreviewChannel (Beispielname) bereitgestellt.
2. Die Mitglieder der Win10ReleasePreviewChannel-Gruppe bestätigen, dass Änderungen am Versionsvorschaukanal für die IT-Bereitstellungsmitarbeiter eingesetzt werden, die Feedback an Microsoft senden und zur weiteren Überprüfung auf Änderungen des nächsten Versionsvorschaukanals warten können.
3. Featureänderungen im halbjährlichen Kanal werden in der Win10SemiAnnualChannel-Bereitstellungsgruppe bereitgestellt. 

>[!Note]
>Der halbjährliche Kanal ist zwar der empfohlene Kanal, Ihre IT-Abteilung sollte aber ihre Verwaltungstools verwenden und bestimmen, wann die halbjährliche Kanalversion in der Organisation bereitgestellt werden soll, und diese dann in mehreren Phasen einführen.
>

## <a name="deployment-configuration-for-microsoft-365-apps"></a>Bereitstellungskonfiguration für Microsoft 365-Apps

Das übergeordnete Ziel besteht darin, eine allgemeine Bereitstellung der neuesten Version des aktuellen Kanals nach der Überprüfung der Änderungen am aktuellen Kanal (Vorschau) durch eine Gruppe von repräsentativen Benutzern auszuführen.

Weitere Informationen zu den Bereitstellungsmethoden und -strategien für Microsoft 365-Apps finden Sie unter [Bereitstellung für Microsoft 365-Apps](https://docs.microsoft.com/deployoffice/plan-office-365-proplus).

| Stufe | Kanal | Bereitstellungsgruppe |
|:-------|:-------|:-----|
| Pilotprojekt |  **Aktueller Kanal (Vorschau)** <ul><li> Zweck: {Geben Sie einer Gruppe von repräsentativen Benutzern einen kurzen Überblick über die neuen Features von Microsoft 365-Apps} Bereitstellung von Featureupdates, sobald diese mit Benutzern des aktuellen Kanals (Vorschau) getestet wurden und bereit für die Produktion sind. </li><li> Status: Vollständig kompatibel und unterstützt.</li><li> Häufigkeit: Updates 2-3 Mal monatlich. </li></ul> | **AppsCurrentChannelPreview** (Beispielname) <br><br> Mitglieder sind Gruppen, die Folgendes enthalten: <ul><li> Office-Apps-Enthusiasten über Abteilungen und Standorte hinweg </li><li> Mitarbeiter mit Konfigurationen, die eine Überprüfung erfordern </li><li> IT-Administratoren und IT-Bereitstellungsmitarbeiter </li><li> Änderungsmanager </li><li> Interne Schulungsmitarbeiter </li></ul>|
| Produktion | **Aktueller Kanal** <ul><li> Zweck: Allgemeine Bereitstellung der neuesten Featureupdates für den Rest der Organisation. </li><li> Status: Vollständig kompatibel und unterstützt. </li></ul> |  **AppsCurrentChannel** (Beispielname) <br><br> Mitglieder sind alle Benutzer, die sich nicht in der AppsCurrentChannelPreview-Gruppe befinden. |
|||

Fortlaufender Updateprozess:

1. Änderungen am aktuellen Kanal (Vorschau) werden in der AppsCurrentChannelPreview-Bereitstellungsgruppe bereitgestellt.
2. Die Mitglieder der AppsCurrentChannelPreview-Gruppe bestätigen, dass Änderungen am aktuellen Kanal (Vorschau) für die IT-Bereitstellungsmitarbeiter eingesetzt werden, die Feedback an Microsoft senden und zur weiteren Überprüfung auf Änderungen des aktuellen Kanals (Vorschau) warten können.
3. Änderungen am aktuellen Kanal werden in der AppsCurrentChannel-Bereitstellungsgruppe bereitgestellt. 

## <a name="visual-summary"></a>Visuelle Zusammenfassung

Nachfolgend sehen die Produkte, deren Kanäle und die in dieser Beispielorganisation verwendeten Bereitstellungsgruppen. 

![Bereitstellungsgruppen für die allgemeine Bereitstellung der neuesten Versionen](../media/deploy-update-channels-examples-rapid-deploy/group-summary.png)

## <a name="see-also"></a>Siehe auch

[Bereitstellung und Aktualisierung der Beispielkonfigurationen des Kanals](deploy-update-channels-examples.md)

[Übersicht über Microsoft 365 Enterprise](microsoft-365-overview.md)

[Testumgebungsanleitungen](m365-enterprise-test-lab-guides.md)
