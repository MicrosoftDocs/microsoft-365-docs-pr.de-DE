---
title: Erstellen von Aktivitäts Warnungen im Office 365
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 11/7/2017
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- BCS160
- MET150
ms.assetid: 72bbad69-035b-4d33-b8f4-549a2743e97d
description: Hinzufügen und Verwalten von Aktivitäts Warnungen im Security and Compliance Center, sodass Office 365 Ihnen e-Mail-Benachrichtigungen sendet, wenn Benutzer bestimmte Aktivitäten in Office 365 ausführen.
ms.openlocfilehash: 0cfe3edfcfcad50d6d04a1ef009498c0e13c7842
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/20/2019
ms.locfileid: "37080905"
---
# <a name="create-activity-alerts-in-the-office-365"></a>Erstellen von Aktivitäts Warnungen im Office 365

Sie können eine Aktivitäts Warnung erstellen, mit der Sie eine e-Mail-Benachrichtigung erhalten, wenn Benutzer bestimmte Aktivitäten in Office 365 durchführen. Aktivitäts Warnungen ähneln der Suche nach Ereignissen im Überwachungsprotokoll Office 365, es sei denn, es wird eine e-Mail-Nachricht gesendet, wenn ein Ereignis für eine Aktivität, für die Sie eine Benachrichtigung erstellt haben, erfolgt. 
  
 **Warum sollten Aktivitäts Warnungen verwendet werden, anstatt das Überwachungsprotokoll zu durchsuchen?** Es können bestimmte Arten von Aktivitäten oder Aktivitäten von bestimmten Benutzern ausgeführt werden, über die Sie wirklich Bescheid wissen möchten. Anstatt sich daran zu erinnern, das Überwachungsprotokoll für diese Aktivitäten zu durchsuchen, können Sie Aktivitäts Warnungen verwenden, um Ihnen Office 365 eine e-Mail-Nachricht zu senden, wenn Benutzer diese Aktivitäten ausführen. Sie können beispielsweise eine Aktivitäts Warnung erstellen, um Sie zu benachrichtigen, wenn ein Benutzer Dateien in SharePoint löscht, oder Sie können eine Warnung erstellen, um Sie zu benachrichtigen, wenn ein Benutzer Nachrichten endgültig aus seinem Postfach löscht. Die an Sie gesendete e-Mail-Benachrichtigung enthält Informationen darüber, welche Aktivität ausgeführt wurde, und den Benutzer, der Sie ausgeführt hat. 

> [!NOTE]
> Es wird empfohlen, Warnungsrichtlinien im Security and Compliance Center zu verwenden, anstatt neue Aktivitäts Warnungen zu erstellen. Warnungsrichtlinien bieten zusätzliche Funktionen, beispielsweise die Möglichkeit, eine Warnungs Richtlinie zu erstellen, die eine Warnung auslöst, wenn ein beliebiger Benutzer eine bestimmte Aktivität ausführt, und Warnungen auf der Seite **Benachrichtigungen anzeigen** im Security and Compliance Center anzuzeigen. Weitere Informationen finden Sie unter [Warnungsrichtlinien](alert-policies.md).
  
## <a name="before-you-begin"></a>Bevor Sie beginnen

- Sie müssen die Rolle Organisationskonfiguration im Sicherheits #a0 Compliance Center zugewiesen sein, um Aktivitäts Warnungen zu verwalten. Diese Rolle wird standardmäßig den Rollengruppen Compliance-Administrator und Organisationsverwaltung zugewiesen. Weitere Informationen zum Hinzufügen von Mitgliedern zu Rollengruppen finden Sie unter [Erteilen von Benutzern den Zugriff auf das Security #a0 Compliance Center](../security/office-365-security/grant-access-to-the-security-and-compliance-center.md).
    
- Sie (oder ein anderer Administrator) müssen zuerst die Überwachungsprotokollierung für Ihre Organisation aktivieren, bevor Sie mit der Verwendung von Aktivitäts Warnungen beginnen können. Klicken Sie dazu auf der Seite **Aktivitäts Benachrichtigungen** auf **Aufzeichnung von Benutzer-und Administratoraktivitäten starten** . (Wenn dieser Link nicht angezeigt wird, wurde die Überwachung für Ihre Organisation bereits aktiviert.) Sie können die Überwachung auch auf der Seite **Überwachungsprotokoll Suche** im Security #a0 Compliance Center aktivieren **(Such** \> **Überwachungsprotokoll**-Suche aufrufen). Sie müssen dies nur einmal für Ihre Organisation durchführen.
  
- Sie können Benachrichtigungen für dieselben Aktivitäten erstellen, nach denen Sie im Office 365 Überwachungsprotokoll suchen können. Im Abschnitt [Weitere Informationen](#more-information) finden Sie eine Liste der häufigsten Szenarien (und die zu überwachenden spezifischen Aktivitäten), für die Sie Warnungen erstellen können. 
    
- Sie können die Seite **Aktivitäts Benachrichtigungen** im Security #a0 Compliance Center verwenden, um Benachrichtigungen nur für Aktivitäten zu erstellen, die von Benutzern ausgeführt werden, die im Adressbuch Ihrer Organisation aufgeführt sind. Sie können diese Seite nicht verwenden, um Benachrichtigungen für Aktivitäten zu erstellen, die von externen Benutzern ausgeführt werden, die nicht im Adressbuch aufgeführt sind. 
    
## <a name="create-an-activity-alert"></a>Erstellen einer Aktivitäts Warnung

1. Wechseln Sie zu [https://protection.office.com/managealerts](https://protection.office.com/managealerts).
    
2. Melden Sie sich bei Office 365 mit Ihrem Geschäfts-, Schul- oder Unikonto an.
    
3. Klicken Sie auf der Seite **Aktivitäts Benachrichtigungen** auf ![](media/8ee52980-254b-440b-99a2-18d068de62d3.gif) **Neues**Symbol hinzufügen.

   Die Flyout-Seite zum Erstellen einer Aktivitäts Warnung wird angezeigt.

    
    ![Erstellen einer Aktivitäts Warnung](media/53888bd5-9fa2-4398-8ccc-1a9dc72517ac.png)
  
4. Füllen Sie die folgenden Felder aus, um eine Aktivitäts Warnung zu erstellen:
    
    a. **Name** – geben Sie einen Namen für die Warnung ein. Warnungsnamen müssen innerhalb Ihrer Organisation eindeutig sein.
    
    b. **Beschreibung** (Optional) – beschreiben Sie die Benachrichtigung, beispielsweise die Aktivitäten und Benutzer, die nachverfolgt werden, und die Benutzer, an die e-Mail-Benachrichtigungen gesendet werden. Beschreibungen bieten eine schnelle und einfache Möglichkeit, den Zweck der Warnung für andere Administratoren zu beschreiben.
    
    c. **Warnungstyp** – stellen Sie sicher, dass die **benutzerdefinierte** Option ausgewählt ist. 

    d. **Senden Sie diese Warnung, wenn** Sie auf **Diese Warnung senden** klicken, wenn Sie diese beiden Felder konfigurieren:
    
    - **Aktivitäten** – klicken Sie auf die Dropdownliste, um die Aktivitäten anzuzeigen, für die Sie eine Warnung erstellen können. Dies ist die gleiche Aktivitätsliste, die angezeigt wird, wenn Sie das Office 365 Überwachungsprotokoll durchsuchen. Sie können eine oder mehrere bestimmte Aktivitäten auswählen, oder Sie können auf den Namen der Aktivitätsgruppe klicken, um alle Aktivitäten in der Gruppe auszuwählen. Eine Beschreibung dieser Aktivitäten finden Sie im Abschnitt "überwachte Aktivitäten" unter [Durchsuchen des Überwachungsprotokolls](search-the-audit-log-in-security-and-compliance.md#audited-activities). Wenn ein Benutzer eine der Aktivitäten ausführt, die Sie der Benachrichtigung hinzugefügt haben, wird eine e-Mail-Benachrichtigung gesendet. 
    
     - **Benutzer** – klicken Sie auf dieses Feld, und wählen Sie dann einen oder mehrere Benutzer aus. Wenn die Benutzer in diesem Feld die Aktivitäten ausführen, die Sie dem Feld **Aktivitäten** hinzugefügt haben, wird eine Warnung gesendet. Lassen Sie das Feld **Benutzer** leer, um eine Warnung zu senden, wenn ein beliebiger Benutzer in Ihrer Organisation die von der Warnung angegebenen Aktivitäten ausführt. 

    e. **Diese Warnung senden** klicken Sie auf **Diese Warnung senden**, und klicken Sie dann auf in das Feld **Empfänger** , und geben Sie einen Namen ein, um Benutzer hinzuzufügen, die eine e-Mail-Benachrichtigung erhalten, wenn ein Benutzer (im Feld **Benutzer** angegeben) eine Aktivität ausführt (angegeben im Feld **Aktivitäten** ). Beachten Sie, dass Sie standardmäßig der Liste der Empfänger hinzugefügt werden. Sie können Ihren Namen aus dieser Liste entfernen.
    
5. Klicken Sie auf **Speichern** , um die Warnung zu erstellen. 
    
    Die neue Warnung wird in der Liste auf der Seite **Aktivitäts Benachrichtigungen** angezeigt. 
    
    ![Auf der Seite Aktivitäts Benachrichtigungen wird eine Liste mit Warnungen angezeigt.](media/02b774f2-1719-41de-bbc9-5e5b7576f335.png)
  
    Der Status der Warnung ist **auf "ein**" festgelegt. Beachten Sie, dass die Empfänger, die eine e-Mail-Benachrichtigung erhalten, wenn eine Warnung gesendet wird, ebenfalls aufgeführt werden. 
  
## <a name="turn-off-an-activity-alert"></a>Deaktivieren einer Aktivitäts Warnung

Sie können eine Aktivitäts Warnung deaktivieren, sodass keine e-Mail-Benachrichtigung gesendet wird. Nachdem Sie die Aktivitäts Warnung deaktiviert haben, wird Sie weiterhin in der Liste der Aktivitäts Warnungen für Ihre Organisation angezeigt, und Sie können ihre Eigenschaften weiterhin anzeigen.
  
1. Wechseln Sie zu [https://protection.office.com/managealerts](https://protection.office.com/managealerts).
    
2. Melden Sie sich bei Office 365 mit Ihrem Geschäfts-, Schul- oder Unikonto an.
    
3. Klicken Sie in der Liste der Aktivitäts Warnungen für Ihre Organisation auf die Warnung, die Sie deaktivieren möchten.
    
4. Klicken Sie auf der Seite **Benachrichtigung bearbeiten** auf den Schalter **bei** Toggle, um den Status auf **aus**zu ändern, und klicken Sie dann auf **Speichern**.
    
    Der Status der Warnung auf den Seiten **Aktivitäts Warnungen** ist auf **aus**festgelegt. 
    
Wenn Sie eine Aktivitäts Warnung wieder aktivieren möchten, wiederholen Sie diese Schritte, und klicken Sie auf die Option aus Umschaltfläche **aus** , um den Status **auf ein zu ändern.**
  
## <a name="more-information"></a>Weitere Informationen

- Im folgenden finden Sie ein Beispiel für die e-Mail-Benachrichtigung, die an die Benutzer gesendet wird, die im Security #a0 Compliance Center im Feld "diese Benachrichtigung an" gesendet wurden (und auf der Seite " **Aktivitäts Warnungen** " unter **Empfänger** aufgeführt sind). 
    
    ![Beispiel einer e-Mail-notifcation, die für eine Aktivitäts Warnung gesendet wurde](media/a5f91611-fae6-4fe9-82f5-58521a2e2541.png)
  
- Im folgenden finden Sie einige allgemeine Dokument-und e-Mail-Aktivitäten, für die Sie Aktivitäts Warnungen erstellen können. In den Tabellen werden die Aktivität, der Name der Aktivität zum Erstellen einer Benachrichtigung für und der Name der Aktivitätsgruppe, unter der die Aktivität aufgeführt ist, in der Dropdownliste **Aktivitäten** beschrieben. Eine vollständige Liste der Aktivitäten, für die Sie Aktivitäts Warnungen erstellen können, finden Sie im Abschnitt "überwachte Aktivitäten" unter [Durchsuchen des Überwachungsprotokolls](search-the-audit-log-in-security-and-compliance.md#audited-activities).
    
    > [!TIP]
    > Möglicherweise möchten Sie eine Aktivitäts Benachrichtigung für nur eine Aktivität erstellen, die von einem beliebigen Benutzer ausgeführt wird. Sie können auch eine Aktivitäts Warnung erstellen, mit der mehrere von einem oder mehreren Benutzern ausgeführte Aktivitäten nachverfolgt werden. 
  
    In der folgenden Tabelle sind einige gängige dokumentbezogene Aktivitäten in SharePoint oder OneDrive für Unternehmen aufgeführt.
    
    |**Wenn ein Benutzer dies tut...**|**Erstellen einer Benachrichtigung für diese Aktivität**|**Aktivitätsgruppe**|
    |:-----|:-----|:-----|
    |Zeigt ein Dokument auf einer Website an.  <br/> |Datei wird aufgerufen  <br/> |Datei-und Ordner Aktivitäten  <br/> |
    |Bearbeitet oder ändert ein Dokument.  <br/> |Geänderte Datei  <br/> |Datei-und Ordner Aktivitäten  <br/> |
    |Freigabe eines Dokuments für einen Benutzer außerhalb Ihrer Organisation.  <br/> |Freigeben von Datei, Ordner oder Website  <br/> Und  <br/> Erstellte Freigabeeinladung  <br/> Weitere Informationen finden Sie unter [Use Sharing Auditing in the Office 365 Audit Log](use-sharing-auditing.md).  <br/> |Freigabe-und Zugriffs Anforderungs Aktivitäten  <br/> |
    |Lädt ein Dokument hoch oder lädt es herunter.  <br/> |Hochgeladene Datei  <br/> Und/oder  <br/> Heruntergeladene Datei  <br/> |Datei-und Ordner Aktivitäten  <br/> |
    |Ändert die Zugriffsberechtigungen für eine Website.  <br/> |Geänderte Websiteberechtigungen  <br/> |Website Verwaltungsaktivitäten  <br/> |

    In der folgenden Tabelle sind einige häufige e-Mail-bezogene Aktivitäten in Exchange Online aufgeführt.

    |**Wenn ein Benutzer dies tut...**|**Erstellen einer Benachrichtigung für diese Aktivität**|**Aktivitätsgruppe**|
    |:-----|:-----|:-----|
    |Löscht dauerhaft eine e-Mail-Nachricht aus Ihrem Postfach (bereinigt).  <br/> |Bereinigte Nachrichten aus dem Postfach  <br/> | Exchange-Postfachaktivitäten  <br/> |
    |Sendet eine e-Mail-Nachricht aus einem freigegebenen Postfach.  <br/> |Gesendete Nachricht mit "Senden als"-Berechtigungen  <br/> Und  <br/> Gesendete Nachricht mit Berechtigungen "Senden im Auftrag von"  <br/> | Exchange-Postfachaktivitäten  <br/> |
   
- Sie können auch die Cmdlets **New-ActivityAlert** und **ActivityAlert** in Security #a0 Compliance Center PowerShell verwenden, um Aktivitäts Warnungen zu erstellen und zu bearbeiten. Beachten Sie Folgendes, wenn Sie diese Cmdlets zum Erstellen oder Bearbeiten von Aktivitäts Warnungen verwenden: 
    
  - Wenn Sie ein Cmdlet zum Hinzufügen einer Aktivität zu der Warnung verwenden, die nicht in der Dropdownliste **Aktivitäten** aufgeführt ist, wird eine Meldung auf der Eigenschaftenseite für die Warnung angezeigt, die besagt, dass benutzerdefinierte Vorgänge in der Auswahl nicht aufgeführt sind. 
    
  - Ein guter Grund für die Verwendung der Cmdlets zum Erstellen oder Bearbeiten einer Aktivitäts Warnung ist das Senden von e-Mail-Benachrichtigungen an Personen außerhalb Ihrer Organisation. Dieser externe Benutzer wird in der Liste der Empfänger für die Warnung aufgeführt. Wenn Sie diesen externen Benutzer aber aus der Warnung entfernen, kann dieser Benutzer der Benachrichtigung nicht mithilfe der Seite " **Benachrichtigung bearbeiten** " erneut hinzugefügt werden. Sie müssen den externen Benutzer erneut mit dem Cmdlet " **ActivityAlert** " hinzufügen oder das Cmdlet **New-ActivityAlert** verwenden, um denselben (oder anderen) externen Benutzer einer neuen Warnung hinzuzufügen. 
