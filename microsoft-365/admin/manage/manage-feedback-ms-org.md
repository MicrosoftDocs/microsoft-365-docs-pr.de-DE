---
title: Microsoft-Feedback für Ihre Organisation verwalten
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
ms.openlocfilehash: 70ea1d5c176dd603f6a5addb09356909f13f9ace
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2021
ms.locfileid: "52840670"
---
# <a name="manage-microsoft-feedback-for-your-organization"></a>Microsoft-Feedback für Ihre Organisation verwalten

Als Administrator einer Microsoft 365 Organisation gibt es jetzt mehrere Richtlinien, mit denen Sie die Feedbacksammlung und die Kundenbindung Ihrer Benutzer bei der Verwendung Microsoft 365 Anwendungen verwalten können. Sie können vorhandene Azure Active Directory-Gruppen in Ihrer Organisation für jede dieser Richtlinien erstellen und verwenden. Mit diesen Richtlinien können Sie steuern, wie verschiedene Abteilungen in Ihrer Organisation Feedback an Microsoft senden können. Microsoft überprüft alle von Kunden übermittelten Feedbacks und verwendet dieses Feedback, um das Produkt zu verbessern. Wenn Sie die Feedback-Erfahrungen **aktiviert** lassen, können Sie sehen, was Ihre Benutzer zu den von ihnen verwendeten Microsoft-Produkten sagen. Das Feedback, das wir von Ihren Benutzern sammeln, wird in Kürze im Microsoft 365 Admin Center verfügbar sein.

Weitere Informationen zu den Arten von Feedback und zur Verwendung von Benutzerfeedback durch Microsoft finden Sie unter ["Informationen zu Microsoft-Feedback für Ihre Organisation".](../misc/feedback-user-control.md)

Die folgende Tabelle gibt an, welche Apps und Dienste derzeit mit den Feedbackrichtlinien verbunden sind, die in der nachstehenden Tabelle mit den Feedbackrichtlinien aufgeführt sind. Screenshotbeispiele finden Sie unter der Tabelle.

|**Apps &-Dienste**|**Produktinternes Feedback** <br> |**Produktinterne Umfragen** <br> |**Metadatensammlung** <br> |**Kundenbindung** <br> |
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

[Hier finden Sie einige Beispiele für Produktumfragen und Feedback.](/microsoft-365/admin/misc/feedback-user-control#in-product-surveys)

**Metadatensammlung**

:::image type="content" source="../../media/feedback-metadata2.png" alt-text="Screenshot: Feedbackseite mit Metadatenbeispiel":::

**Kundenbindung**

:::image type="content" source="../../media/feedback-in-product-customer-engagement.png" alt-text="Screenshot: Beispiel für Produktfrage zur Kundenrecherchfrage":::

## <a name="before-you-begin"></a>Bevor Sie beginnen

Ihre Geräte müssen mindestens eine Buildnummer aufweisen, um diese Richtlinien verwenden zu können. Weitere Informationen finden Sie in der folgenden Tabelle.

|**Bauen #**|**Win32**|**iOS**|**Android**|**Mac**|**Web**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|Produktinternes Feedback|Mindestens 16.0.13328|Mindestens 2,42|Mindestens 16.0.13328|Mindestens 16,42|Öffentlich verfügbar|
|Produktinterne Umfragen|Mindestens 16.0.13328|Mindestens 2,42|Mindestens 16.0.13426|Mindestens 16,42|Ausstehendes Rollout|
|Metadatensammlung|Mindestens 16.0.13328|Mindestens 2,42|Mindestens 16.0.13328|Mindestens 16,42|Öffentlich verfügbar|
|Kundenbindung|Mindestens 16.0.13328|Mindestens 2,42|Mindestens 16.0.13426|Mindestens 16,42|Ausstehendes Rollout|

## <a name="specific-policies-you-can-configure"></a>Spezifische Richtlinien, die Sie konfigurieren können

### <a name="feedback-policies"></a>Feedbackrichtlinien

|**Name der Richtlinie**|**Standardzustand**|**Steuerelementzusammenfassung**|
|:-----|:-----|:-----|
|Zulassen, dass Benutzer Feedback an Microsoft senden|Ein|Steuert Feedback-Einstiegspunkte in allen Anwendungen|
|Zulassen, dass Benutzer Produktinterne Umfragen von Microsoft empfangen und beantworten können|Ein|Steuert Umfrageaufforderungen innerhalb des Produkts|
|Zulassen, dass Benutzer Screenshots und Anlagen einschließen, wenn sie Feedback an Microsoft senden|Aus|Bestimmt, welche Metadaten der Benutzer mit Feedback/Umfrage übermitteln kann|
|Zulassen, dass Microsoft das von Benutzern übermittelte Feedback nachverfolgung|Aus|Bestimmt, ob Benutzer Kontaktinformationen mit Feedback/Umfrage teilen können|
|Zulassen, dass Benutzer Protokolldateien und Inhaltsbeispiele einschließen, wenn Feedback an Microsoft gesendet wird|Aus|Legt Metadaten fest, die der Benutzer mit Feedback/Umfrage übermitteln kann|

## <a name="configure-policies"></a>Konfigurieren von Richtlinien

1. Wechseln Sie zu [https://config.office.com](https://config.office.com) und melden Sie sich als Benutzer mit globalen Administratorberechtigungen an.
1. Wählen Sie **"Anpassung"** und dann **"Richtlinienverwaltung" aus.**
1. Wählen Sie **Erstellen** aus.
1. Geben Sie **den Namen** und die **Beschreibung** ein.
1. Wählen Sie die Azure Active Directory-Gruppen aus, die Sie konfigurieren möchten.
1. Suchen Sie nach **Feedback** und **Umfrage.**
1. Legen Sie für jede aufgeführte Richtlinie den gewünschten Wert fest.

Weitere Informationen finden Sie unter [Übersicht über den Office Cloudrichtliniendienst.](/deployoffice/overview-office-cloud-policy-service)

Diese Richtlinieneinstellungen sind auch verfügbar, wenn Sie Gruppenrichtlinien verwenden. Um diese Richtlinieneinstellungen zu verwenden, laden Sie mindestens Version 5146.1000 der [administrativen Vorlagendateien (ADMX/ADML)](https://www.microsoft.com/download/details.aspx?id=49030)herunter, die am 22. März 2021 veröffentlicht wurden.

Sie finden diese Richtlinieneinstellungen unter "Benutzerkonfiguration – > Richtlinien –> Administrative Vorlagen –> Microsoft Office 2016 -> Datenschutz – > Trust Center".

> [!NOTE]
> Es dauert ein paar Stunden, bis die Clientanwendungen aktualisiert wurden.
