---
title: Verwalten von Microsoft-Feedback für Ihre Organisation
f1.keywords:
- NOCSH
ms.author: Kwekua
author: Kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
description: Verwalten Sie Feedback, das Ihre Benutzer an Microsoft zu Microsoft-Produkten senden können.
ms.openlocfilehash: c92adec1689d6f0c46b03ae4f46c567f054b6457
ms.sourcegitcommit: a46532bb422ee51331f478ff50cc5444586bf6a9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/09/2021
ms.locfileid: "51650016"
---
# <a name="manage-microsoft-feedback-for-your-organization"></a>Verwalten von Microsoft-Feedback für Ihre Organisation

Als Administrator einer Microsoft 365-Organisation gibt es nun mehrere Richtlinien, mit denen Sie die Feedbacksammlung und die Kundenbindungserfahrung Ihrer Benutzer bei der Verwendung von Microsoft 365-Anwendungen verwalten können. Sie können für jede dieser Richtlinien vorhandene Azure Active Directory-Gruppen in Ihrer Organisation erstellen und verwenden. Mit diesen Policen können Sie steuern, wie verschiedene Abteilungen in Ihrer Organisation Feedback an Microsoft senden können. Microsoft überprüft alle von Kunden übermittelten Feedbacks und verwendet dieses Feedback, um das Produkt zu verbessern. Wenn Sie die Feedbackerfahrung **aktiviert** halten, können Sie sehen, was Ihre Benutzer zu den von ihnen verwendeten Microsoft-Produkten sagen. Das Feedback, das wir von Ihren Benutzern sammeln, wird bald im Microsoft 365 Admin Center verfügbar sein."

Weitere Informationen zu den Arten von Feedback und dazu, wie Microsoft Benutzerfeedback verwendet, finden Sie unter Erfahren Sie mehr über [Das Feedback von Microsoft für Ihre Organisation.](../misc/feedback-user-control.md)

Die folgende Tabelle stellt dar, welche Apps und Dienste derzeit mit den Feedbackrichtlinien in der folgenden Tabelle mit Feedbackrichtlinien verbunden sind. Unter der Tabelle finden Sie Screenshotbeispiele.

|**Apps & Services**|**Produktfeedback** <br> |**In-Product-Umfragen** <br> |**Metadatensammlung** <br> |**Kundenbindung** <br> |
|:-----|:-----|:-----|:-----|:-----|
|**Access**|Ja|Ja|Ja|Ja|
|**Excel**|Ja|Ja|Ja|Ja|
|**Office.com**|Bald verfügbar|Bald verfügbar|Bald verfügbar|Bald verfügbar|
|**OneNote**|Ja|Ja|Ja|Ja|
|**OneDrive**|[Einige Einstellungen, die derzeit von anderen Steuerelementen verwaltet werden.](/onedrive/disable-contact-support-send-feedback)||||
|**Outlook**|Bald verfügbar|Bald verfügbar|Bald verfügbar|Bald verfügbar|
|**PowerPoint**|Ja|Ja|Ja|Ja|
|**Project**|Bald verfügbar|Bald verfügbar|Bald verfügbar|Bald verfügbar|
|**Herausgeber**|Ja|Ja|Ja|Ja|
|**SharePoint**|[Einige Einstellungen, die derzeit von anderen Steuerelementen verwaltet werden.](/powershell/module/sharepoint-online/set-spotenant)||||
|**Teams**|[Einige Einstellungen, die derzeit von anderen Steuerelementen verwaltet werden.](/microsoftteams/manage-feedback-policies-in-teams)||||
|**Word**|Ja|Ja|Ja|Ja|
|**Visio**|Ja|Ja|Ja|Ja|
|**Yammer**|Ja|Ja|Ja|Ja|

[Hier finden Sie einige Beispiele für Produktumfragen und Feedback.](https://docs.microsoft.com/microsoft-365/admin/misc/feedback-user-control?view=o365-worldwide#in-product-surveys)

**Metadatensammlung**

:::image type="content" source="../../media/feedback-metadata2.png" alt-text="Screenshot: Feedbackseite mit Metadatenbeispiel":::

**Kundenbindung**

:::image type="content" source="../../media/feedback-in-product-customer-engagement.png" alt-text="Screenshot: In-Product Customer Research Question Example":::

## <a name="before-you-begin"></a>Bevor Sie beginnen

Ihre Geräte müssen sich auf einer Mindest buildnummer für die Verwendung dieser Richtlinien benennen. Weitere Informationen finden Sie in der folgenden Tabelle.

|**Build #**|**Win32**|**iOS**|**Android**|**Mac**|**Web**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|Produktfeedback|Mindestens 16.0.13328|Mindestens 2,42|Mindestens 16.0.13328|Mindestens 16,42|Öffentlich verfügbar|
|In-Product-Umfragen|Mindestens 16.0.13328|Mindestens 2,42|Mindestens 16.0.13426|Mindestens 16,42|Ausstehendes Rollout|
|Metadatensammlung|Mindestens 16.0.13328|Mindestens 2,42|Mindestens 16.0.13328|Mindestens 16,42|Öffentlich verfügbar|
|Kundenbindung|Mindestens 16.0.13328|Mindestens 2,42|Mindestens 16.0.13426|Mindestens 16,42|Ausstehendes Rollout|

## <a name="specific-policies-you-can-configure"></a>Bestimmte Richtlinien, die Sie konfigurieren können

### <a name="feedback-policies"></a>Feedbackrichtlinien

|**Name der Richtlinie**|**Standardzustand**|**Steuerelementzusammenfassung**|
|:-----|:-----|:-----|
|Zulassen, dass Benutzer Feedback an Microsoft senden|Ein|Steuert Feedback-Einstiegspunkte in mehreren Anwendungen|
|Zulassen, dass Benutzer Produktumfragen von Microsoft empfangen und beantworten können|Ein|Steuert Umfrageaufforderungen innerhalb des Produkts|
|Zulassen, dass Benutzer Screenshots und Anlagen hinzufügen, wenn sie Feedback an Microsoft senden|Off|Bestimmt, welche Metadaten der Benutzer mit Feedback/Umfrage übermitteln kann|
|Zulassen, dass Microsoft Feedback von Benutzern weiter verfolgen kann|Off|Bestimmt, ob Benutzer Kontaktinformationen mit Feedback/Umfrage freigeben können|
|Zulassen, dass Benutzer Protokolldateien und Inhaltsbeispiele enthalten, wenn Feedback an Microsoft übermittelt wird|Off|Bestimmt Metadaten, die der Benutzer mit Feedback/Umfrage übermitteln kann|

## <a name="configure-policies"></a>Konfigurieren von Richtlinien

1. Wechseln Sie [https://config.office.com](https://config.office.com) zu und melden Sie sich als Benutzer mit globalen Administratorberechtigungen an.
1. Wählen **Sie Anpassung** und dann **Richtlinienverwaltung aus.**
1. Wählen Sie **Erstellen** aus.
1. Geben **Sie Namen** und Beschreibung **ein.**
1. Wählen Sie die Azure Active -Verzeichnisgruppen aus, die Sie konfigurieren möchten.
1. Suchen Sie nach **Feedback** und **Umfrage**.
1. Legen Sie für jede aufgeführte Richtlinie den wert, den Sie möchten.

Weitere Informationen finden Sie [unter Overview of the Office cloud policy service](/deployoffice/overview-office-cloud-policy-service).

Diese Richtlinieneinstellungen sind auch verfügbar, wenn Sie Gruppenrichtlinien verwenden. Um diese Richtlinieneinstellungen zu verwenden, laden Sie mindestens Version 5146.1000 der administrativen Vorlagendateien [(ADMX/ADML)](https://www.microsoft.com/download/details.aspx?id=49030)herunter, die am 22. März 2021 veröffentlicht wurden.

Diese Richtlinieneinstellungen finden Sie unter Benutzerkonfiguration -> Richtlinien -> Administrative Vorlagen -> Microsoft Office 2016 -> Privacy -> Trust Center.

> [!NOTE]
> Es dauert einige Stunden, bis die Clientanwendungen aktualisiert werden.
