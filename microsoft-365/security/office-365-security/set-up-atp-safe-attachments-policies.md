---
title: Einrichten Office 365 Richtlinien für ATP-sichere Anlagen
f1.keywords:
- NOCSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
audience: Admin
ms.topic: article
ms.date: 02/06/2019
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 078eb946-819a-4e13-8673-fe0c0ad3a775
ms.collection:
- M365-security-compliance
description: In diesem Artikel erfahren Sie, wie Sie Richtlinien für sichere Anlagen zum Schutz Ihrer Organisation vor bösartigen Dateien in e-Mails definieren.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: d826cb6e0dd4370a1e02722901d083d4f021e2b4
ms.sourcegitcommit: 2de6e07ec55d78a5c5cf2f45732ae68acf058bcf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/05/2020
ms.locfileid: "44588120"
---
# <a name="set-up-office-365-atp-safe-attachments-policies"></a>Einrichten Office 365 Richtlinien für ATP-sichere Anlagen

> [!IMPORTANT]
> Dieser Artikel richtet sich an Geschäftskunden, die über [Office 365 Advanced Threat Protection](office-365-atp.md) verfügen. Wenn Sie ein Privatbenutzer sind, der nach Informationen zu sicheren Anlagen in Outlook sucht, lesen Sie [Erweiterte Outlook.com-Sicherheit](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).

Personen senden, empfangen und teilen regelmäßig Anlagen wie Dokumente, Präsentationen, Tabellenkalkulationen und vieles mehr. Es ist nicht immer einfach zu erkennen, ob eine Anlage sicher oder böswillig ist, indem nur eine e-Mail-Nachricht angezeigt wird. Und das letzte, was Sie möchten, ist eine böswillige Anlage, die durchkommt und verheerende Verwüstungen für Ihre Organisation anrichtet. Glücklicherweise kann [Office 365 Advanced Threat Protection](office-365-atp.md) (ATP) hilfreich sein. Sie können Richtlinien für [ATP-sichere Anlagen](atp-safe-attachments.md) einrichten, um sicherzustellen, dass Ihre Organisation vor Angriffen durch nicht sichere e-Mail-Anlagen geschützt ist.

## <a name="what-to-do"></a>Nächste Schritte

1. Überprüfen der Voraussetzungen

2. Einrichten einer Richtlinie für ATP-sichere Anlagen

3. Informationen zu Richtlinienoptionen für ATP-sichere Anlagen

## <a name="step-1-review-the-prerequisites"></a>Schritt 1: Überprüfen der Voraussetzungen

- Stellen Sie sicher, dass Ihre Organisation über [Office 365 Advanced Threat Protection](office-365-atp.md)verfügt.

- Stellen Sie sicher, dass Sie über die erforderlichen Berechtigungen verfügen. Um ATP-Richtlinien zu definieren (oder zu bearbeiten), müssen Sie entweder eine Exchange Online Organisations Verwaltungsrolle (globaler Administrator ist dieser Rolle standardmäßig zugewiesen) oder beide Rollen Exchange Online Verwaltung von Hygiene-und Sicherheitsadministratoren zugewiesen sein. Weitere Informationen finden Sie in der folgenden Tabelle:

  |Rolle|Wo/wie zugewiesen|
  |---------|---------|
  |globaler Administrator |Die Person, die sich zum Kauf von Microsoft 365 anmeldet, ist standardmäßig ein globaler Administrator. (Weitere Informationen finden Sie unter [Informationen zu Microsoft 365-Administratorrollen](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles) .)|
  |Sicherheitsadministrator |Azure Active Directory Admin Center ( [https://aad.portal.azure.com](https://aad.portal.azure.com) )|
  |Exchange Online Organisationsverwaltung, Exchange Online Hygiene Management |Exchange Admin Center ( [https://outlook.office365.com/ecp](https://outlook.office365.com/ecp) ) <br>oder <br>  PowerShell-Cmdlets (siehe [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell))|
  |

  Weitere Informationen zu Rollen und Berechtigungen finden Sie unter [Permissions in the Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md).

- [Erfahren Sie mehr über die Richtlinienoptionen für ATP-sichere Anlagen](#step-3-learn-about-atp-safe-attachments-policy-options) (in diesem Artikel). Einige Optionen, beispielsweise die Optionen "Monitor" oder "ersetzen", können zu einer geringfügigen Verzögerung von e-Mails führen, während Anlagen gescannt werden. Um Verzögerungen bei der Nachrichtenübermittlung zu vermeiden, sollten Sie die [dynamische Zustellung und Vorschau](dynamic-delivery-and-previewing.md)verwenden.

- Erlauben Sie bis zu 30 Minuten, bis Ihre neue oder aktualisierte Richtlinie auf alle Microsoft 365-Rechenzentren verteilt ist.

## <a name="step-2-set-up-or-edit-an-atp-safe-attachments-policy"></a>Schritt 2: einrichten (oder bearbeiten) einer Richtlinie für ATP-sichere Anlagen

1. Wechseln Sie zu, [https://protection.office.com](https://protection.office.com) und melden Sie sich mit ihrem geschäftlichen oder Schulkonto an.

2. &amp;Wählen Sie im Security Compliance Center im linken Navigationsbereich unter **Bedrohungs Verwaltung**die Option **Richtlinien** für \> **sichere Anlagen**aus.

3. Wenn Sie **ATP für SharePoint, OneDrive und Microsoft Teams aktivieren**sehen, sollten Sie diese Option auswählen. Dadurch wird [Office 365 Advanced Threat Protection für SharePoint, OneDrive und Microsoft Teams](atp-for-spo-odb-and-teams.md) für Ihre Microsoft 365-Umgebung aktiviert.

4. Wählen Sie **neu** (die Schaltfläche neu ähnelt einem Pluszeichen ( **+** )), um mit dem Erstellen Ihrer Richtlinie zu beginnen.

5. Geben Sie den Namen, die Beschreibung und die Einstellungen für die Richtlinie an.<br/><br/>**Beispiel:** Um eine Richtlinie mit dem Namen "keine Verzögerungen" einzurichten, die alle Nachrichten sofort bereitstellt und dann Anlagen nach dem Scannen erneut anfügt, können Sie die folgenden Einstellungen angeben:

   - Geben Sie im Feld **Name** keine Verzögerungen ein.

   - Geben Sie im Feld **Beschreibung** eine Beschreibung ein, wie, sendet Nachrichten sofort und fügt Anlagen nach dem Scannen erneut an.

   - Wählen Sie im Abschnitt Antwort die Option **dynamische Zustellung** aus. ([Weitere Informationen zur dynamischen Zustellung und zur Vorschau mit ATP-sicheren Anlagen](dynamic-delivery-and-previewing.md).)

   - Wählen Sie im Abschnitt **Umleitungs Anlage** die Option zum Aktivieren der Umleitung aus, und geben Sie die e-Mail-Adresse des globalen Administrators, des Sicherheitsadministrators oder des Sicherheitsanalysten ein, der böswillige Anlagen untersuchen soll.

   - Wählen Sie im Abschnitt **angewendet für** **die Option Empfängerdomäne**aus, und wählen Sie dann Ihre Domäne aus. Klicken Sie auf **Hinzufügen**, und wählen Sie dann **OK**aus.

6. Wählen Sie **Speichern** aus.

Sie sollten mehrere ATP-Richtlinien für sichere Anlagen für Ihre Organisation einrichten. Diese Richtlinien werden in der Reihenfolge angewendet, in der Sie auf der Seite **ATP-sichere Anlagen** aufgeführt sind. Nachdem eine Richtlinie definiert oder bearbeitet wurde, müssen Sie mindestens 30 Minuten in Anspruch nehmen, damit die Policen in Microsoft-Rechenzentren wirksam werden.

## <a name="step-3-learn-about-atp-safe-attachments-policy-options"></a>Schritt 3: Informationen zu Richtlinienoptionen für ATP-sichere Anlagen

Bei der Einrichtung Ihrer Richtlinien für ATP-sichere Anlagen wählen Sie unter vielen Optionen aus, darunter Monitor, blockieren, ersetzen, dynamische Zustellung usw. Wenn Sie sich Fragen, was diese Optionen angeht, fasst die folgende Tabelle die einzelnen Effekte zusammen.

||||
|---|---|---|
|**Option**|**Effect**|**Verwenden Sie Folgendes, wenn Sie möchten:**|
|**Off**|Scannt keine Anlagen für Schadsoftware  <br/> Verzögert die Nachrichtenzustellung nicht|Deaktivieren der Überprüfung bei Scannern, Faxnachrichten oder intelligenten Hosts, die nur bekannte, gute Anlagen senden werden  <br/> Vermeiden Sie unnötige Verzögerungen beim Weiterleiten interner e-Mails.  <br/> **Diese Option wird für die meisten Benutzer nicht empfohlen. Sie sollten diese Option nur verwenden, um die Überprüfung der ATP-Sicherheit von Anlagen für eine kleine Gruppe vertrauenswürdiger Absender zu deaktivieren.**|
|**Monitor**|Sendet Nachrichten mit Anlagen und verfolgt dann, was mit erkannter Schadsoftware geschieht.|Ermitteln, wo erkannte Schadsoftware in Ihrer Organisation eingeht|
|**Block**|Verhindert, dass Nachrichten mit erkannten Schadsoftware-Anlagen fortgesetzt werden  <br/> Sendet Nachrichten mit erkannter Schadsoftware [in Quarantäne in Office 365, in](manage-quarantined-messages-and-files.md) denen ein Sicherheitsadministrator oder Analyst diese Nachrichten überprüfen und freigeben (oder löschen) kann.  <br/> Automatisches Blockieren zukünftiger Nachrichten und Anlagen|Schützen Ihrer Organisation vor wiederholten Angriffen mit denselben Schadsoftware-Anlagen|
|**Replace**|Entfernt erkannte Schadsoftware-Anlagen  <br/> Benachrichtigt Empfänger, dass Anlagen entfernt wurden.  <br/> Sendet Nachrichten mit erkannter Schadsoftware [in Quarantäne in Office 365, in](manage-quarantined-messages-and-files.md) denen ein Sicherheitsadministrator oder Analyst diese Nachrichten überprüfen und freigeben (oder löschen) kann.|Erhöhen der Sichtbarkeit für Empfänger, die Anlagen aufgrund erkannter Schadsoftware entfernt haben|
|**Dynamische Zustellung**|Sendet sofort Nachrichten  <br/> Ersetzt Anlagen durch eine Platzhalterdatei, bis die Überprüfung abgeschlossen ist, und fügt dann die Anlagen erneut an, wenn keine Schadsoftware erkannt wird.  <br/> Enthält Funktionen zur Vorschau der Anlage für die meisten PDFs und Office-Dateien während der Überprüfung  <br/> Sendet Nachrichten mit erkannter Schadsoftware in Quarantäne, in denen ein Sicherheitsadministrator oder Analyst diese Nachrichten überprüfen und freigeben (oder löschen) kann.  <br/> [Informationen zur dynamischen Zustellung und Vorschau mit ATP-sicheren Anlagen](dynamic-delivery-and-previewing.md) <br/> |Vermeiden von Nachrichten Verzögerungen beim Schutz von Empfängern vor bösartigen Dateien  <br/> Aktivieren von Empfängern zum Anzeigen einer Vorschau von Anlagen im abgesicherten Modus, während der Scan stattfindet|
|**Umleitung aktivieren**|Gilt, wenn die Option Monitor, Block oder ersetzen ausgewählt ist.  <br/> Sendet Anlagen an eine angegebene e-Mail-Adresse, die von Sicherheitsadministratoren oder Analysten untersucht werden kann.|Aktivieren von Sicherheitsadministratoren und Analysten zum Recherchieren verdächtiger Anlagen|
|**Anwenden der obigen Auswahl, wenn bei der Malwareüberprüfung nach Anlagen ein Timeout oder ein Fehler auftritt**|Wendet die für unsichere Anlagen konfigurierte Aktion auf die Anlagen an, die nicht gescannt werden können (aufgrund eines Timeouts oder Fehlers)|
|

## <a name="next-steps"></a>Weitere Schritte

Sobald Ihre ATP-Richtlinien für sichere Anlagen vorhanden sind, können Sie sehen, wie ATP für Ihre Organisation funktioniert, indem Sie Berichte anzeigen. Weitere Informationen finden Sie in den folgenden Ressourcen:

- [Anzeigen von Berichten für Office 365 Advanced Threat Protection](view-reports-for-atp.md)

- [Verwenden des Explorers im Security & Compliance Center](threat-explorer.md)

Bleiben Sie auf dem neuesten Stand neuer Features, die zu ATP kommen. Besuchen Sie die [Microsoft 365-Roadmap](https://www.microsoft.com/microsoft-365/roadmap?filters=O365) , und erfahren Sie mehr über die [neuen Features, die ATP hinzugefügt werden](office-365-atp.md#new-features-in-office-365-atp).
