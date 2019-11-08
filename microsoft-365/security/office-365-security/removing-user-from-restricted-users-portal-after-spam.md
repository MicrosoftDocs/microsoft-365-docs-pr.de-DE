---
title: Entfernen eines Benutzers aus dem Portal für Benutzer mit eingeschränktem Zugriff nach dem Senden von Spam-E-Mails
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 07/10/2019
audience: ITPro
ms.topic: article
f1_keywords:
- ms.exch.eac.ActionCenter.Restricted.Users.RestrictedUsers
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.assetid: 712cfcc1-31e8-4e51-8561-b64258a8f1e5
ms.collection:
- M365-security-compliance
description: Wenn Benutzer ständig E-Mails von Office 365 senden, die als Spam klassifiziert werden, werden sie für das Senden von E-Mails gesperrt.
ms.openlocfilehash: 4abb37bbda20d17b19144d6f62b4ef1a4fc8fb4c
ms.sourcegitcommit: 70e920f76526f47fc849df615de4569e0ac2f4be
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/07/2019
ms.locfileid: "38032160"
---
# <a name="removing-a-user-from-the-restricted-users-portal-after-sending-spam-email"></a>Entfernen eines Benutzers aus dem Portal für Benutzer mit eingeschränktem Zugriff nach dem Senden von Spam-E-Mails

Wenn Benutzer ständig E-Mails von Office 365 senden, die als Spam klassifiziert werden, werden sie für das Senden von E-Mails gesperrt, können aber weiterhin E-Mails empfangen. Der Benutzer wird in dem Dienst als ungültiger ausgehender Absender gelistet und erhält einen Unzustellbarkeitsbericht (Non-Delivery Report, NDR), der Folgendes besagt:

> „Ihre Nachricht konnte nicht übermittelt werden, weil Sie nicht als gültiger Absender erkannt wurden. Der häufigste Grund dafür ist, dass der Verdacht besteht, dass von Ihrer E-Mail-Adresse Spam versandt wurde, und dass deshalb das Senden von E-Mails nicht mehr zugelassen wird.  Sollten Sie Unterstützung benötigen, wenden Sie sich an Ihren E-Mail-Administrator. Der Remoteserver hat „550 5.1.8 Zugriff verweigert, ungültiger ausgehender Absender“ zurückgegeben.“

## <a name="what-do-you-need-to-know-before-you-begin"></a>Was sollten Sie wissen, bevor Sie beginnen?
<a name="sectionSection0"> </a>

Geschätzte Zeit bis zum Abschließen des Vorgangs: 5 Minuten
  
Bevor Sie dieses Verfahren bzw. diese Verfahren ausführen können, müssen Ihnen die entsprechenden Berechtigungen zugewiesen werden. Informationen zu den von Ihnen benötigten Berechtigungen finden Sie unter dem Eintrag „Antispam“ im Thema [Featureberechtigungen in Exchange Online](https://technet.microsoft.com/library/15073ce1-0917-403b-8839-02a2ebc96e16.aspx).

Das folgende Verfahren kann auch über Remote-PowerShell erfolgen. Verwenden Sie das Cmdlet Get-BlockedSenderAddress, um die Liste der eingeschränkten Benutzer abzurufen und Remove-BlockedSenderAddress, um die Einschränkung zu entfernen. Wie Sie mit Windows PowerShell eine Verbindung mit Exchange Online herstellen, können Sie unter [Mit Exchange Online PowerShell verbinden](https://go.microsoft.com/fwlink/p/?linkid=396554) nachlesen.

## <a name="remove-restrictions-for-a-blocked-office-365-email-account"></a>Einschränkungen für ein gesperrtes Office 365-E-Mail-Konto entfernen

Sie schließen diese Aufgabe im Security & Compliance Center (SCC) ab. [Wechseln Sie zum Security & Compliance Center](../../compliance/go-to-the-securitycompliance-center.md), um mehr über das SCC zu erfahren. Sie müssen in der Rollengruppe **Organisationsverwaltung** oder **Sicherheitsadministrator** sein, um diese Funktionen ausführen zu können. [Wechseln Sie im Security & Compliance Center zu den Berechtigungen](permissions-in-the-security-and-compliance-center.md), um mehr über SCC-Rollengruppen zu erfahren.

1. Melden Sie sich mit einem Geschäfts-, Schul- oder Unikonto, das über globale Administratorberechtigungen für Office 365 verfügt, beim Office 365 Security & Compliance Center an, und klappen Sie in der Liste auf der linken Seite **Bedrohungsmanagement** aus, wählen Sie **Überprüfen** aus und wählen Sie dann **Eingeschränkte Benutzer** aus.
    
    > [!TIP]
    > Sie können die Seite **Eingeschränkte Benutzer** (früher Info-Center) im Security &amp; Compliance Center direkt über diese URL aufrufen: [https://protection.office.com/#/restrictedusers](https://protection.office.com/?hash=/restrictedusers)

2. Diese Seite enthält eine Liste der Benutzer, die für das Senden von E-Mails gesperrt wurden.  Suchen Sie den Benutzer, dessen Einschränkungen Sie entfernen möchten, und wählen Sie **Entsperren** aus.

3. Details zu dem Konto, für das das Senden eingeschränkt wurde, werden in einem Popup-Fenster angezeigt. Gehen Sie die Empfehlungen durch und stellen Sie sicher, dass Sie die richtigen Maßnahmen für den Fall ergreifen, dass das Konto tatsächlich kompromittiert ist. Klicken Sie abschließend auf **Weiter**.

4. Der nächste Bildschirm enthält Empfehlungen zur Verhinderung zukünftiger Kompromittierungen. Das Aktivieren der mehrstufigen Authentifizierung (MFA) und das Ändern der Kennwörter sind eine gute Abwehr. Klicken Sie abschließend auf **Benutzer entsperren**.

5. Klicken Sie zur Änderungsbestätigung auf **Ja**.

    > [!NOTE]
    > Es kann bis zu 30 Minuten oder länger dauern, bis Einschränkungen aufgehoben werden. 

## <a name="making-sure-admins-are-alerted-when-this-happens"></a>Sicherstellen, dass Administratoren benachrichtigt werden, wenn dies geschieht

Eine Benachrichtigung „Benutzer für das Senden von E-Mails gesperrt“ ist als Richtlinie auf der Seite für Benachrichtigungsrichtlinien in Office 365 Security & Compliance verfügbar. Dies war früher die Richtlinie über ausgehende Spamnachrichten, ist aber jetzt Teil der Office 365-Benachrichtigungsplattform. Wechseln Sie zu [Benachrichtigungsrichtlinien im Security & Compliance Center](../../compliance/alert-policies.md), um mehr über Benachrichtigungen zu erfahren.

> [!IMPORTANT]
> Damit Benachrichtigungen funktionieren, muss die Überwachungsprotokollsuche aktiviert sein. Weitere Informationen finden Sie unter [Aktivieren oder Deaktivieren der Office 365-Überwachungsprotokollsuche](../../compliance/turn-audit-log-search-on-or-off.md).

Die Richtlinie für diese Benachrichtigung ist standardmäßig in jedem Office 365-Mandanten enthalten und muss nicht eingerichtet werden. Sie wird als Warnung mit hohem Schweregrad eingestuft und sendet jedes Mal, wenn ein Benutzer für das Senden von E-Mails gesperrt und die Benachrichtigung ausgelöst wird, eine E-Mail an die konfigurierte TenantAdmins-Gruppe. Administratoren können die Gruppe, die bei dieser Warnung benachrichtigt wird, aktualisieren, indem Sie im SCC-Portal unter „Benachrichtigungen“ > „Benachrichtigungsrichtlinien“ > „Für das Senden von E-Mails gesperrte Benutzer“ zu dieser Warnung wechseln.

Sie können die Benachrichtigung wie folgt bearbeiten:
- E-Mail-Benachrichtigungen aktivieren/deaktivieren
- E-Mail an erforderliche Empfänger senden
- Anzahl von Benachrichtigungen pro Tag begrenzen

## <a name="checking-for-and-removing-restrictions-using-powershell"></a>Überprüfen auf und Entfernen von Einschränkungen mithilfe von PowerShell
Die PowerShell-Befehle für eingeschränkte Benutzer sind:
- `Get-BlockedSenderAddress`: Zum Abrufen der Liste von für das Senden von E-Mails gesperrten Benutzern verwenden
- `Remove-BlockedSenderAddress`: Zum Entsperren von Benutzern verwenden

## <a name="for-more-information"></a>Weitere Informationen

[Auf ein kompromittiertes E-Mail-Konto reagieren](../../compliance/responding-to-a-compromised-email-account.md)

[Grundlegendes zu der Benachrichtigung über zum Senden von E-Mails gesperrte Benutzer](https://docs.microsoft.com/office365/securitycompliance/alert-policies)

[Pool für besonders riskante Zustellungen für ausgehende Nachrichten](high-risk-delivery-pool-for-outbound-messages.md)

[Berechtigungen im Security & Compliance Center](permissions-in-the-security-and-compliance-center.md)

[Benachrichtigungsrichtlinien im Security & Compliance Center](https://docs.microsoft.com/office365/securitycompliance/alert-policies)
