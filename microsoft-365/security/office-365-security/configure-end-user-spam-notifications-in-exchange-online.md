---
title: Konfigurieren von Spambenachrichtigungen für Endbenutzer in Exchange Online
ms.author: tracyp
author: MSFTTracyp
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: bfc91c73-a955-40e1-a95f-ad466624339a
ms.collection:
- M365-security-compliance
description: Sie können Spambenachrichtigungen für Endbenutzer für die standardmäßige unternehmensweite Spamfilter Richtlinie oder für benutzerdefinierte Spamfilter Richtlinien konfigurieren, die auf Domänen angewendet werden.
ms.openlocfilehash: 7292d75afb07864fc50d4df30fa5f84691087820
ms.sourcegitcommit: 3f8957ddd04b8710bb5f314a0902fdee50c7c9b7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "41573012"
---
# <a name="configure-end-user-spam-notifications-in-exchange-online"></a>Konfigurieren von Spambenachrichtigungen für Endbenutzer in Exchange Online

> [!IMPORTANT]
> Dieses Thema richtet sich an Exchange Online-Kunden, die cloudgehostete Postfächer schützen. Selbstständige Kunden mit Exchange Online Protection (EoP), die lokale Postfächer schützen, sollten stattdessen das folgende Thema lesen: [configure End-User Spam Notifications in EoP](configure-end-user-spam-notifications-in-eop.md). 
  
Sie können Spambenachrichtigungen für Endbenutzer für die standardmäßige unternehmensweite Spamfilter Richtlinie oder für benutzerdefinierte Spamfilter Richtlinien konfigurieren. Durch die Aktivierung von Spambenachrichtigungen für Endbenutzer können Ihre Benutzer ihre eigenen Nachrichten mit Spamquarantäne verwalten. 
  
Spambenachrichtigungen für Endbenutzer enthalten eine Liste aller Nachrichten in der Spamquarantäne, die der Endbenutzer in dem von Ihnen konfigurierten Zeitraum (zwischen 1 und 15 Tagen) erhalten hat. Sie können auch die Sprache festlegen, in der die Benachrichtigung geschrieben wird.
  
Nach dem Empfang einer Benachrichtigung können Endbenutzer eine der folgenden Optionen auswählen:

**Absender blockieren** , wenn Office 365 den Absender zu Ihrer Liste blockierter Absender hinzufügen möchten.

**Release** wenn es sich bei der Nachricht nicht um Spam handelt und Sie möchten, dass Office 365 die Nachricht an Ihr Postfach sendet.

**Überprüfen** Sie, um zum Quarantäne Portal im Sicherheits #a0 Compliance Center zu navigieren, wenn Sie andere Aktionen wie Vorschau oder Release ausführen möchten.
  
## <a name="what-do-you-need-to-know-before-you-begin"></a>Was sollten Sie wissen, bevor Sie beginnen?

Geschätzte Zeit bis zum Abschließen des Vorgangs: 2 Minuten
  
Bevor Sie diese Verfahren ausführen können, müssen Ihnen die entsprechenden Berechtigungen zugewiesen werden. Informationen zu den von Ihnen benötigten Berechtigungen finden Sie unter "Anti-Spam" im Thema [Feature Permissions in Exchange Online](https://docs.microsoft.com/exchange/permissions-exo/feature-permissions) . 
  
Informationen zu Tastenkombinationen, die möglicherweise für die Verfahren in diesem Thema gelten, finden Sie unter [Tastenkombinationen für das Exchange Admin Center in Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).
  
## <a name="use-the-eac-to-configure-end-user-spam-notifications"></a>Konfigurieren von Spambenachrichtigungen für Endbenutzer über die Exchange-Verwaltungskonsole

1. Navigieren Sie in der Exchange-Verwaltungskonsole zu **Schutz** \> **Spamfilter**.
    
2. Wählen Sie die Spamfilter Richtlinie aus, für die Sie Spambenachrichtigungen für Endbenutzer aktivieren möchten (Sie sind standardmäßig deaktiviert).
    
3. Klicken Sie im rechten Teilfenster, in dem eine Übersicht über Ihre Richtlinie angezeigt wird, auf den Link **Configure End-user spam notifications** (Spambenachrichtigungen für Endbenutzer konfigurieren). 
    
4. Konfigurieren Sie im daraufhin angezeigten Dialogfeld die folgenden Optionen:
    
   - **Enable end-user spam notifications** (Spambenachrichtigungen für Endbenutzer aktivieren) Markieren Sie dieses Kontrollkästchen, um Benachrichtigungen an Endbenutzer für diese Richtlinie zu aktivieren. (Wenn diese Richtlinie aktiviert ist, können Sie auf das Kontrollkästchen klicken, um Spambenachrichtigungen an Endbenutzer für diese Richtlinie zu deaktivieren.) 
    
   - **Send end-user spam notifications every (days)** (Spambenachrichtigungen an Endbenutzer senden alle ... Tage) Gibt an, wie oft Spambenachrichtigungen an Endbenutzer gesendet werden sollen. Der Standardwert beträgt 3 Tage. Sie können zwischen 1 und 15 Tagen angeben. Wenn Sie beispielsweise 7 Tage angeben, enthält die Benachrichtigung eine Liste aller Nachrichten der letzten 7 Tage für diesen Benutzer, die stattdessen in die Spamquarantäne verschoben wurden. 
    
   - **Notification language** (Benachrichtigungssprache) Wählen Sie in der Dropdown-Liste die Sprache aus, in der Endbenutzer-Spambenachrichtigungen für diese Richtlinie geschrieben werden sollen. 
    
   - Klicken Sie auf **Speichern**. Eine Zusammenfassung der Einstellungen für Spamfilter Richtlinien, einschließlich der Einstellungen für Spambenachrichtigungen für Endbenutzer, wird im rechten Bereich angezeigt.
    
> [!NOTE]
>  Spambenachrichtigungen für Endbenutzer sind nur für aktivierte Spamfilter Richtlinien funktionsfähig. >  Spam Endbenutzerbenachrichtigungen sind nur einmal pro Tag versendet. Die Zustellungszeit der Benachrichtigung kann für einen bestimmten Kunden nicht garantiert werden und kann nicht konfiguriert werden. 
  
 **Tipp:** Wenn Sie Spambenachrichtigungen für Endbenutzer testen möchten, indem Sie Sie an eine beschränkte Gruppe von Benutzern senden, bevor Sie sie vollständig implementieren, erstellen Sie eine benutzerdefinierte Spamfilter Richtlinie, die Endbenutzer-Spambenachrichtigungen für die Domänen ermöglicht, in denen sich die Benutzer befinden. Erstellen Sie dann in der Exchange-Verwaltungskonsole unter **Nachrichtenfluss \> Regeln**eine Nachrichtenfluss Regel (auch als Transportregel bezeichnet), um Nachrichten von Quarantine@Messaging.Microsoft.com (der e-Mail-Adresse, die Benachrichtigungen sendet) mit Ausnahmen für die Benutzer zu blockieren, die die Benachrichtigungen erhalten sollen. Die folgende Abbildung zeigt ein Beispiel für die Erstellung einer Ausnahme für zwei Benutzer (SaraD and AlexD) in der Domäne Contoso.com: 
  
![Transportregel zum Testen von Spambenachrichtigungen für Endbenutzer](../media/EOP-ESN-testspecificusers.jpg)
  
## <a name="use-the-scc-to-configure-end-user-spam-notifications"></a>Konfigurieren von Spambenachrichtigungen für Endbenutzer mithilfe der SCC

Sie können auch das Security and Compliance Center (SCC) verwenden, um Spambenachrichtigungen für Endbenutzer zu konfigurieren. Führen Sie die folgenden Schritte aus:

1. Öffnen Sie das Security and Compliance Center, navigieren Sie zu **Threat Management** \> **Policy** \> **Anti-Spam** , oder verwenden https://protection.office.com/antispamSie den Direct Link.

2. Klicken Sie auf den Pfeil nach unten neben der Spamfilter Richtlinie, für die Sie Spambenachrichtigungen für Endbenutzer aktivieren möchten.

3. Klicken Sie auf den Link **Endbenutzer-Spambenachrichtigungen konfigurieren** .

4. Konfigurieren Sie im daraufhin angezeigten Dialogfeld die folgenden Optionen:
    
   - **Enable end-user spam notifications** (Spambenachrichtigungen für Endbenutzer aktivieren) Markieren Sie dieses Kontrollkästchen, um Benachrichtigungen an Endbenutzer für diese Richtlinie zu aktivieren. (Wenn diese Richtlinie aktiviert ist, können Sie auf das Kontrollkästchen klicken, um Spambenachrichtigungen an Endbenutzer für diese Richtlinie zu deaktivieren.) 
    
   - **Send end-user spam notifications every (days)** (Spambenachrichtigungen an Endbenutzer senden alle ... Tage) Gibt an, wie oft Spambenachrichtigungen an Endbenutzer gesendet werden sollen. Der Standardwert beträgt 3 Tage. Sie können zwischen 1 und 15 Tagen angeben. Wenn Sie beispielsweise 7 Tage angeben, enthält die Benachrichtigung eine Liste aller Nachrichten der letzten 7 Tage für diesen Benutzer, die stattdessen in die Spamquarantäne verschoben wurden. 
    
   - **Notification language** (Benachrichtigungssprache) Wählen Sie in der Dropdown-Liste die Sprache aus, in der Endbenutzer-Spambenachrichtigungen für diese Richtlinie geschrieben werden sollen. 
    
   - Klicken Sie auf **Speichern**. Eine Zusammenfassung der Einstellungen für Spamfilter Richtlinien, einschließlich der Einstellungen für Spambenachrichtigungen für Endbenutzer, wird im Bereich angezeigt.

## <a name="for-more-information"></a>Weitere Informationen

[Konfigurieren von Spamfilterrichtlinien](configure-your-spam-filter-policies.md)
  
