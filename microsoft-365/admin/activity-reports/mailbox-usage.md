---
title: Microsoft 365-Berichte im Admin Center – Postfachnutzung
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: beffbe01-ce2d-4614-9ae5-7898868e2729
description: Erfahren Sie, wie Sie den Bericht zur Postfachnutzung über die Aktivitäten der Benutzer mit einem Benutzerpostfach informieren.
ms.openlocfilehash: 806309e262215e63c49fa2334e136b4b004a4246
ms.sourcegitcommit: 7ecd10b302b3b3dfa4ba3be3a6986dd3c189fbff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/21/2021
ms.locfileid: "49921304"
---
# <a name="microsoft-365-reports-in-the-admin-center---mailbox-usage"></a>Microsoft 365-Berichte im Admin Center – Postfachnutzung

Der  Bericht zur Postfachnutzung enthält Informationen zu Benutzern mit einem Benutzerpostfach und zum Aktivitätsgrad der einzelnen Benutzer basierend auf der E-Mail-Aktivität zum Senden, Lesen, Erstellen eines Termins, zum Senden einer Besprechung, zum Annehmen einer Besprechung, zum Ablehnen von Besprechungen und zum Abbrechen der Besprechungsaktivität. Er enthält außerdem Informationen zu dem belegten Speicher jedes Benutzerpostfachs und der Anzahl der Postfächer, die sich ihren Speicherkontingenten nähern. 
  
> [!NOTE]
> Sie müssen ein globaler Administrator, ein globaler Leser oder ein Leser von Berichten in Microsoft 365 oder ein Exchange-, SharePoint-, Teams-Dienst-, Teams Communications- oder Skype for Business-Administrator sein, um Berichte anzeigen zu können. 
 
## <a name="how-to-get-to-the-mailbox-usage-report"></a>So gelangen Sie zum Bericht zur Postfachnutzung

1. Wechseln Sie im Admin Center zur Seite **Berichte** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Verwendung</a>.
2. Select **View More** under Email **activity**. 
3. Wählen Sie **in der** Dropdownliste "E-Mail-Aktivität" die Verwendung des  \> **Exchange-Postfachs aus.**

## <a name="interpret-the-mailbox-usage-report"></a>Interpretieren des Berichts zur Postfachnutzung

Sie können die **Postfachnutzung** in Ihrer Organisation anzeigen, indem Sie sich die Diagramme **Postfach**, **Speicher** und **Kontingent** anschauen. 
  
![Bericht zur Postfachnutzung](../../media/9f610e91-cbc1-4e59-b824-7b1ddd84b738.png)

|Element|Beschreibung|
|:-----|:-----|
|1.  <br/> |Im Bericht **Postfachnutzung** werden die Trends über die letzten 7 Tage, 30 Tage, 90 Tage oder 180 Tage angezeigt. Wenn Sie im Bericht jedoch einen bestimmten Tag auswählen, werden in der Tabelle Daten für bis zu 28 Tage ab dem aktuellen Datum angezeigt (nicht ab dem Datum, an dem der Bericht generiert wurde).  <br/> |
|2.  <br/> |Die Daten in den einzelnen Berichten decken in der Regel die letzten 24 bis 48 Stunden ab.  <br/> |
|3.  <br/> |Das Diagramm "Postfach" zeigt die Gesamtzahl der Benutzerpostfächer in Ihrer Organisation an, sowie die Gesamtzahl der aktiven Postfächer an einem gegebenen Tag des Berichtszeitraums. Ein Benutzerpostfach wird als aktiv betrachtet, wenn eine E-Mail gesendet, gelesen, Termin erstellt, Besprechung gesendet, Besprechungen akzeptiert, Besprechungsaktivitäten ablehnen und Besprechungsaktivitäten absagen.  <br/> |
|4.  <br/> |Das Diagramm **Speicher** zeigt die Menge des Speicherplatzes an, der von Ihrer Organisation verwendet wird. Das Speicherdiagramm enthält keine Archivpostfächer. Weitere Informationen zur automatisch erweiterten Archivierung finden Sie unter Übersicht über die unbegrenzte Archivierung [in Microsoft 365.](https://docs.microsoft.com/microsoft-365/compliance/unlimited-archiving)<br/> |
|5.  <br/> | Das Diagramm **Kontingent** zeigt die Anzahl der Benutzerpostfächer in jeder Kontingentkategorie an. Es gibt vier Kontingentkategorien:  <br/>  "Gut" - Anzahl der Benutzer, deren verwendeter Speicher unterhalb der Kontingentwarnungsschwelle liegt.  <br/>  "Warnung" - Anzahl der Benutzer, deren verwendeter Speicher an der oder über der Warnungsschwelle liegt, deren Sendekontingent jedoch noch nicht überschritten ist.  <br/>  "Senden nicht möglich" - Anzahl der Benutzer, deren verwendeter Speicher das Sendekontingent erreicht oder überschritten hat, die jedoch noch nicht das Sende-/Empfangskontingent überschritten haben.  <br/>  "Senden/Empfangen nicht möglich" - Anzahl der Benutzer, deren verwendeter Speicher das Sende-/Empfangskontingent überschritten hat.  <br/> |
|6.  <br/> | Im Diagramm **Postfach** gibt die Y-Achse die Anzahl der Benutzerpostfächer an.  <br/>  Im Diagramm **Speicher** gibt die Y-Achse die von den Benutzerpostfächern in Ihrer Organisation belegten Speicher an.  <br/>  Im Diagramm **Kontingent** gibt die Y-Achse die Anzahl der Benutzerpostfächer in jeder Kontingentkategorie an.  <br/>  Die X-Achse in den Diagrammen "Postfach" und "Speicher" entspricht dem ausgewählten Zeitraum für diesen bestimmten Bericht.  <br/>  Die X-Achse in den Kontingentdiagrammen gibt die Kontingentkategorie an.  <br/> |
|7.  <br/> |Sie können die angezeigten Diagramme filtern, indem Sie ein Element in der Legende auswählen.  <br/> |
|8.  <br/> | Die Tabelle zeigt eine Aufschlüsselung der Postfachnutzung auf Ebene der einzelnen Benutzer. Sie können weitere Spalten zur Tabelle hinzufügen.  <br/> **Benutzername** ist die E-Mail-Adresse des Benutzers.  <br/> **Anzeigename** ist der vollständige Name des Benutzers.  <br/> **Gelöscht** bezieht sich auf das Postfach, dessen aktueller Status "Gelöscht" ist, das aber während eines Teils des Berichtszeitraums aktiv war.  <br/> **Gelöscht am** ist das Datum, an dem das Postfach gelöscht wurde.  <br/> **Erstellt am** ist das Datum, an dem das Postfach erstellt wurde.  <br/> **Datum der letzten Aktivität** ist das Datum, an dem von diesem Postfach eine E-Mail gesendet oder empfangen wurde.  <br/> **Anzahl Elemente** gibt die Gesamtzahl der Elemente in Postfach an.  <br/> **Verwendeter Speicher (MB)** gibt den insgesamt verwendeten Speicher an.  <br/> **"Anzahl gelöschter** Elemente" bezieht sich auf die Gesamtzahl der gelöschten Elemente im Postfach. <br/> **"Größe gelöschter Elemente" (MB)** bezieht sich auf die Gesamtgröße aller gelöschten Elemente im Postfach. <br/> **Kontingent für Problemwarnung (MB)** bezieht sich auf das Speicherkontingent, ab dem der Postfachbesitzer eine Warnung erhält, dass er demnächst sein Speicherkontingent überschreitet.  <br/> **Kontingent für Senden verbieten (MB)** bezieht sich auf das Speicherkontingent, ab dem über das Postfach keine E-Mails mehr gesendet werden können.  <br/> **Kontingent für Empfangen verbieten (MB)** bezieht sich auf das Speicherkontingent, ab dem über das Postfach keine E-Mails mehr gesendet oder empfangen werden können.  <br/>  Wenn die Richtlinien Ihrer Organisation eine Anzeige von Berichten verhindern, in denen Benutzerinformationen identifizierbar sind, können Sie die Datenschutzeinstellung für alle diese Berichte ändern. Check out the **Hide user details in the reports** section in the Activity Reports in the Microsoft [365 admin center](activity-reports.md).  <br/> |
|9.  <br/> |Wählen **Sie Spalten zum** Hinzufügen oder Entfernen von Spalten aus dem Bericht aus.  <br/> ![Bericht zur Postfachnutzung – Spalten auswählen](../../media/ea3d0b18-6ac6-41b0-9bb9-4844f040ea75.png)|
|10.  <br/> |Sie können die Berichtsdaten auch im CSV-Format in eine Excel-Datei exportieren, indem Sie den Link **Exportieren** auswählen.  <br/> |
|||
   
