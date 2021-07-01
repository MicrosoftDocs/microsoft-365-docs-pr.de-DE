---
title: Erstellen von Aktivitätswarnungen
f1.keywords:
- NOCSH
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
ROBOTS: NOINDEX, NOFOLLOW
description: Hinzufügen und Verwalten von Aktivitätswarnungen im Security & Compliance Center, damit Microsoft 365 Ihnen E-Mail-Benachrichtigungen senden, wenn Benutzer bestimmte Aktivitäten ausführen
ms.openlocfilehash: d0daa9249a8ea69c376ef7bbc8b7a90253e411db
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/30/2021
ms.locfileid: "53227163"
---
# <a name="create-activity-alerts"></a>Erstellen von Aktivitätswarnungen

Sie können eine Aktivitätswarnung erstellen, die Ihnen eine E-Mail-Benachrichtigung sendet, wenn Benutzer bestimmte Aktivitäten in Office 365 ausführen. Aktivitätswarnungen ähneln der Suche nach Ereignissen im Überwachungsprotokoll, mit der Ausnahme, dass Sie eine E-Mail-Nachricht erhalten, wenn ein Ereignis für eine Aktivität auftritt, für die Sie eine Warnung erstellt haben.

 **Warum Aktivitätswarnungen verwenden, anstatt das Überwachungsprotokoll zu durchsuchen?** Möglicherweise gibt es bestimmte Arten von Aktivitäten, die von bestimmten Benutzern ausgeführt werden, die Sie wirklich kennen möchten. Anstatt sich daran erinnern zu müssen, das Überwachungsprotokoll nach diesen Aktivitäten zu durchsuchen, können Sie Aktivitätswarnungen verwenden, um Ihnen Microsoft 365 eine E-Mail-Nachricht zu senden, wenn Benutzer diese Aktivitäten ausführen. Sie können z. B. eine Aktivitätswarnung erstellen, um Sie zu benachrichtigen, wenn ein Benutzer Dateien in SharePoint löscht, oder Sie können eine Warnung erstellen, um Sie zu benachrichtigen, wenn ein Benutzer Nachrichten dauerhaft aus dem Postfach löscht. Die an Sie gesendete E-Mail-Benachrichtigung enthält Informationen dazu, welche Aktivität ausgeführt wurde und welcher Benutzer sie ausgeführt hat.

> [!NOTE]
> Aktivitätswarnungen sind veraltet. Es wird empfohlen, mit der Verwendung von Warnungsrichtlinien im Security and Compliance Center zu beginnen, anstatt neue Aktivitätswarnungen zu erstellen. Alert policies provide addition functionality such as the ability to create an alert policy that triggers an alert when any user performs a specified activity, and displaying alerts on the **View alerts** page in the security and compliance center. Weitere Informationen finden Sie unter [Warnungsrichtlinien.](alert-policies.md)

## <a name="confirm-roles-and-configure-audit-logging"></a>Bestätigen von Rollen und Konfigurieren der Überwachungsprotokollierung

- Ihnen muss die Rolle "Organisationskonfiguration" im Security & Compliance Center zugewiesen sein, um Aktivitätswarnungen zu verwalten. Standardmäßig wird diese Rolle den Rollengruppen "Complianceadministrator" und "Organisationsverwaltung" zugewiesen. Weitere Informationen zum Hinzufügen von Mitgliedern zu Rollengruppen finden Sie unter ["Benutzern Zugriff auf das Security & Compliance Center gewähren".](../security/office-365-security/grant-access-to-the-security-and-compliance-center.md)

- Sie (oder ein anderer Administrator) müssen zuerst die Überwachungsprotokollierung für Ihre Organisation aktivieren, bevor Sie mit der Verwendung von Aktivitätswarnungen beginnen können. Klicken Sie dazu einfach auf der Seite **"Aktivitätswarnungen"** auf "Aufzeichnung von **Benutzer- und Administratoraktivitäten starten".** (Wenn dieser Link nicht angezeigt wird, wurde die Überwachung bereits für Ihre Organisation aktiviert.) Sie können die Überwachung auch auf der **Seite "Überwachungsprotokollsuche"** im Security & Compliance Center aktivieren (wechseln Sie zur **Suche** nach \> **Überwachungsprotokollen).** Sie müssen dies nur einmal für Ihre Organisation tun.

- Sie können Warnungen für dieselben Aktivitäten erstellen, nach denen Sie im Überwachungsprotokoll suchen können. Im Abschnitt ["Weitere Informationen"](#more-information) finden Sie eine Liste allgemeiner Szenarien (und der zu überwachenden spezifischen Aktivität), für die Sie Warnungen erstellen können.

- Sie können die Seite **"Aktivitätswarnungen"** im Security & Compliance Center verwenden, um Warnungen nur für Aktivitäten zu erstellen, die von Benutzern ausgeführt werden, die im Adressbuch Ihrer Organisation aufgeführt sind. Sie können diese Seite nicht verwenden, um Warnungen für Aktivitäten zu erstellen, die von externen Benutzern ausgeführt werden, die nicht im Adressbuch aufgeführt sind.

## <a name="create-an-activity-alert"></a>Erstellen einer Aktivitätswarnung

1. Wechseln Sie zu [https://protection.office.com/managealerts](https://protection.office.com/managealerts).

2. Melden Sie sich mit Ihrem Geschäfts-, Schul- oder Unikonto an.

3. Klicken Sie auf der Seite **"Aktivitätswarnungen"** auf ![ das Symbol ](../media/8ee52980-254b-440b-99a2-18d068de62d3.gif) **"Neu** hinzufügen".

   Die Flyoutseite zum Erstellen einer Aktivitätswarnung wird angezeigt.


    ![Erstellen einer Aktivitätswarnung](../media/53888bd5-9fa2-4398-8ccc-1a9dc72517ac.png)

4. Füllen Sie die folgenden Felder aus, um eine Aktivitätswarnung zu erstellen:

    a. **Name** – Geben Sie einen Namen für die Warnung ein. Warnungsnamen müssen innerhalb Ihrer Organisation eindeutig sein.

    b. **Beschreibung** (optional) – Beschreiben Sie die Warnung, z. B. die Aktivitäten und Benutzer, die nachverfolgt werden, und die Benutzer, an die E-Mail-Benachrichtigungen gesendet werden. Beschreibungen bieten eine schnelle und einfache Möglichkeit, den Zweck der Warnung für andere Administratoren zu beschreiben.

    c. **Warnungstyp** : Stellen Sie sicher, dass die Option **"Benutzerdefiniert"** ausgewählt ist.

    d. **Senden Sie diese Warnung, wenn** – klicken Sie **auf "Warnung senden", wenn** sie angezeigt wird, und konfigurieren Sie dann diese beiden Felder:

    - **Aktivitäten** – Klicken Sie auf die Dropdownliste, um die Aktivitäten anzuzeigen, für die Sie eine Warnung erstellen können. Dies ist die gleiche Aktivitätsliste, die beim Durchsuchen des Überwachungsprotokolls angezeigt wird. Sie können eine oder mehrere bestimmte Aktivitäten auswählen oder auf den Namen der Aktivitätsgruppe klicken, um alle Aktivitäten in der Gruppe auszuwählen. Eine Beschreibung dieser Aktivitäten finden Sie im Abschnitt "Überwachte Aktivitäten" unter ["Durchsuchen des Überwachungsprotokolls".](search-the-audit-log-in-security-and-compliance.md#audited-activities) Wenn ein Benutzer eine der Aktivitäten ausführt, die Sie der Warnung hinzugefügt haben, wird eine E-Mail-Benachrichtigung gesendet.

     - **Benutzer** – Klicken Sie auf dieses Kontrollkästchen, und wählen Sie dann einen oder mehrere Benutzer aus. Wenn die Benutzer in diesem Feld die Aktivitäten ausführen, die Sie dem Feld **"Aktivitäten"** hinzugefügt haben, wird eine Warnung gesendet. Lassen Sie das Feld **"Benutzer"** leer, um eine Warnung zu senden, wenn ein Benutzer in Ihrer Organisation die in der Warnung angegebenen Aktivitäten ausführt.

    e. **Senden Sie diese Warnung an** – Klicken Sie auf Diese Warnung **senden,** und klicken Sie dann in das Feld **"Empfänger",** und geben Sie einen Namen ein, um einen Benutzer hinzuzufügen, der eine E-Mail-Benachrichtigung erhält, wenn ein Benutzer (im Feld **"Benutzer"** angegeben) eine Aktivität ausführt (im Feld **"Aktivitäten"** angegeben). Beachten Sie, dass Sie der Liste der Empfänger standardmäßig hinzugefügt werden. Sie können Ihren Namen aus dieser Liste entfernen.

5. Klicken Sie auf **"Speichern",** um die Warnung zu erstellen.

    Die neue Warnung wird in der Liste auf der Seite **"Aktivitätswarnungen"** angezeigt.

    ![Eine Liste der Warnungen wird auf der Seite "Aktivitätswarnungen" angezeigt.](../media/02b774f2-1719-41de-bbc9-5e5b7576f335.png)

    Der Status der Warnung ist auf **"Ein"** festgelegt. Beachten Sie, dass die Empfänger, die beim Senden einer Warnung eine E-Mail-Benachrichtigung erhalten haben, ebenfalls aufgeführt sind.

## <a name="turn-off-an-activity-alert"></a>Deaktivieren einer Aktivitätswarnung

Sie können eine Aktivitätswarnung deaktivieren, damit keine E-Mail-Benachrichtigung gesendet wird. Nachdem Sie die Aktivitätswarnung deaktiviert haben, wird sie weiterhin in der Liste der Aktivitätswarnungen für Ihre Organisation angezeigt, und Sie können ihre Eigenschaften weiterhin anzeigen.

1. Wechseln Sie zu Gehe [https://protection.office.com/managealerts](https://protection.office.com/managealerts) zu .

2. Melden Sie sich mit Ihrem Geschäfts-, Schul- oder Unikonto an.

3. Klicken Sie in der Liste der Aktivitätswarnungen für Ihre Organisation auf die Warnung, die Sie deaktivieren möchten.

4. Klicken Sie auf der **Seite "Warnung bearbeiten"** auf die Umschaltfläche **"Ein",** um den Status in **"Aus"** zu ändern, und klicken Sie dann auf **"Speichern".**

    Der Status der Warnung auf den Seiten **"Aktivitätswarnungen"** ist auf **"Aus"** festgelegt.

Um eine Aktivitätswarnung wieder einzuschalten, wiederholen Sie einfach diese Schritte, und klicken Sie auf den Schalter **"Aus",** um den Status in **"Ein"** zu ändern.

## <a name="more-information"></a>Weitere Informationen

- Hier ist ein Beispiel für die E-Mail-Benachrichtigung, die an die Benutzer gesendet wird, die im Feld "Diese Warnung an senden" angegeben sind (und unter **"Empfänger"** auf der Seite **"Aktivitätswarnungen"** aufgeführt) im Security & Compliance Center aufgeführt sind.

    ![Beispiel für eine E-Mail-Benachrichtigung, die für eine Aktivitätswarnung gesendet wurde](../media/a5f91611-fae6-4fe9-82f5-58521a2e2541.png)

- Nachfolgend finden Sie einige allgemeine Dokument- und E-Mail-Aktivitäten, für die Sie Aktivitätswarnungen erstellen können. Die Tabellen beschreiben die Aktivität, den Namen der Aktivität, für die eine Warnung erstellt werden soll, und den Namen der Aktivitätsgruppe, unter der die Aktivität in der Dropdownliste **Aktivitäten** aufgeführt ist. Eine vollständige Liste der Aktivitäten, für die Sie Aktivitätswarnungen erstellen können, finden Sie im Abschnitt "Überwachte Aktivitäten" unter ["Durchsuchen des Überwachungsprotokolls".](search-the-audit-log-in-security-and-compliance.md#audited-activities)

    > [!TIP]
    > Möglicherweise möchten Sie eine Aktivitätswarnung für nur eine Aktivität erstellen, die von einem beliebigen Benutzer ausgeführt wird. Sie können auch eine Aktivitätswarnung erstellen, die mehrere Aktivitäten nachverfolgt, die von einem oder mehreren Benutzern ausgeführt werden.

    In der folgenden Tabelle sind einige allgemeine dokumentbezogene Aktivitäten in SharePoint oder OneDrive for Business aufgeführt.

    |**Wenn ein Benutzer dies tut...**|**Erstellen einer Warnung für diese Aktivität**|**Aktivitätsgruppe**|
    |:-----|:-----|:-----|
    |Zeigt ein Dokument auf einer Website an.  <br/> |Dateizugriff  <br/> |Datei- und Ordneraktivitäten  <br/> |
    |Bearbeitet oder ändert ein Dokument.  <br/> |Datei geändert  <br/> |Datei- und Ordneraktivitäten  <br/> |
    |Gibt ein Dokument für einen Benutzer außerhalb Ihrer Organisation frei.  <br/> |Freigeben von Dateien, Ordnern oder Websites  <br/> Und  <br/> Freigabeeinladung erstellt  <br/> Weitere Informationen finden Sie unter [Verwenden der Freigabeüberwachung im Überwachungsprotokoll](use-sharing-auditing.md).  <br/> |Freigabe- und Zugriffsanforderungsaktivitäten   <br/> |
    |Lädt ein Dokument hoch oder lädt es herunter.  <br/> |Datei hochgeladen  <br/> Und/oder  <br/> Datei heruntergeladen  <br/> |Datei- und Ordneraktivitäten  <br/> |
    |Ändert die Zugriffsberechtigungen für eine Website.  <br/> |Websiteberechtigungen geändert  <br/> |Websiteverwaltungsaktivitäten  <br/> |

    In der folgenden Tabelle sind einige allgemeine E-Mail-bezogene Aktivitäten in Exchange Online aufgeführt.

    |**Wenn ein Benutzer dies tut...**|**Erstellen einer Warnung für diese Aktivität**|**Aktivitätsgruppe**|
    |:-----|:-----|:-----|
    |Löscht (löscht) eine E-Mail-Nachricht dauerhaft aus ihrem Postfach.  <br/> |Nachrichten aus Postfach gelöscht  <br/> | Exchange-Postfachaktivitäten  <br/> |
    |Sendet eine E-Mail-Nachricht von einem freigegebenen Postfach.  <br/> |Nachricht mit Berechtigungen vom Typ "Senden als" gesendet  <br/> Und  <br/> Nachricht mit Berechtigungen vom Typ "Senden im Auftrag von" gesendet  <br/> | Exchange-Postfachaktivitäten  <br/> |

- Sie können auch die Cmdlets **"New-ActivityAlert"** und **"Set-ActivityAlert"** in Security & Compliance Center PowerShell verwenden, um Aktivitätswarnungen zu erstellen und zu bearbeiten. Beachten Sie folgende Punkte, wenn Sie diese Cmdlets zum Erstellen oder Bearbeiten von Aktivitätswarnungen verwenden:

  - Wenn Sie ein Cmdlet verwenden, um der Warnung eine Aktivität hinzuzufügen, die nicht in der Dropdownliste **"Aktivitäten"** aufgeführt ist, wird auf der Eigenschaftenseite für die Warnung eine Meldung angezeigt, die besagt: "Diese Warnung enthält benutzerdefinierte Vorgänge, die nicht in der Auswahl aufgeführt sind."

  - Ein guter Grund für die Verwendung der Cmdlets zum Erstellen oder Bearbeiten einer Aktivitätswarnung ist das Senden von E-Mail-Benachrichtigungen an eine Person außerhalb Ihrer Organisation. Dieser externe Benutzer wird in der Liste der Empfänger für die Warnung aufgeführt. Wenn Sie diesen externen Benutzer jedoch aus der Warnung entfernen, kann dieser Benutzer nicht mithilfe der **Seite "Warnung bearbeiten"** erneut zur Warnung hinzugefügt werden. Sie müssen den externen Benutzer mithilfe des Cmdlets **"Set-ActivityAlert"** erneut hinzufügen oder das Cmdlet **"New-ActivityAlert"** verwenden, um einer neuen Warnung denselben (oder einen anderen) externen Benutzer hinzuzufügen.
