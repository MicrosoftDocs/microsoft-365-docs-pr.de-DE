---
title: Definieren von Nachrichtenflussregeln zum Verschlüsseln von E-Mail-Nachrichten
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 9b7daf19-d5f2-415b-bc43-a0f5f4a585e8
ms.collection:
- M365-security-compliance
description: Administratoren können lernen, Nachrichtenflussregeln (Transportregeln) zum Verschlüsseln und Entschlüsseln von Nachrichten mithilfe von Office 365-Nachrichtenverschlüsselung zu erstellen.
ms.openlocfilehash: 5274c2368de9825bd0568b7abd4e060e22fe9c70
ms.sourcegitcommit: 997a21b83795789cda0a6b4a77f9985a3233d0c0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/14/2021
ms.locfileid: "53430456"
---
# <a name="define-mail-flow-rules-to-encrypt-email-messages"></a>Definieren von Nachrichtenflussregeln zum Verschlüsseln von E-Mail-Nachrichten

Als Administrator, der Exchange Online verwaltet, können Sie Nachrichtenflussregeln (auch als Transportregeln bezeichnet) erstellen, um E-Mail-Nachrichten zu schützen, die Sie senden und empfangen. Sie können Regeln einrichten, um alle ausgehenden E-Mail-Nachrichten zu verschlüsseln und die Verschlüsselung von verschlüsselten Nachrichten aus Ihrer Organisation oder aus Antworten auf verschlüsselte Nachrichten zu entfernen, die von Ihrer Organisation gesendet werden. Sie können das Exchange Admin Center (EAC) oder Exchange Online PowerShell verwenden, um diese Regeln zu erstellen. Zusätzlich zu den allgemeinen Verschlüsselungsregeln können Sie auch die Aktivierung oder Deaktivierung einzelner von Optionen für die Verschlüsselung einzelner Nachrichten für Endbenutzer auswählen.

Eingehende E-Mails von Absendern außerhalb Ihrer Organisation können nicht verschlüsselt werden.

Wenn Sie kürzlich von Active Directory RMS zu Azure Information Protection migriert haben, müssen Sie Ihre vorhandenen Nachrichtenflussregeln überprüfen, um sicherzustellen, dass sie in Ihrer neuen Umgebung weiterhin funktionieren. Wenn Sie die neuen OME-Funktionen (Office 365-Nachrichtenverschlüsselung) nutzen möchten, die Ihnen über Azure Information Protection zur Verfügung stehen, müssen Sie außerdem Ihre vorhandenen Nachrichtenflussregeln aktualisieren. Andernfalls erhalten Ihre Benutzer weiterhin verschlüsselte E-Mails, die das vorherige HTML-Anlagenformat anstelle der neuen, nahtlosen OME-Benutzeroberfläche verwenden. Wenn Sie OME noch nicht eingerichtet haben, finden Sie weitere Informationen unter ["Einrichten neuer Office 365-Nachrichtenverschlüsselung"-Funktionen.](set-up-new-message-encryption-capabilities.md)

Informationen zu den Komponenten, aus denen Nachrichtenflussregeln bestehen, und zur Funktionsweise von Nachrichtenflussregeln finden Sie unter [Nachrichtenflussregeln (Transportregeln) in Exchange Online.](/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) Weitere Informationen zur Funktionsweise von Nachrichtenflussregeln mit Azure Information Protection finden Sie unter [Konfigurieren Exchange Online Nachrichtenflussregeln für Azure Information Protection-Bezeichnungen.](/azure/information-protection/deploy-use/configure-exo-rules)

> [!IMPORTANT]
> Bei Hybridumgebungen Exchange können lokale Benutzer verschlüsselte E-Mails nur dann mithilfe von OME senden und empfangen, wenn E-Mails über Exchange Online weitergeleitet werden. Um OME in einer hybriden Exchange Umgebung zu konfigurieren, müssen Sie zuerst [die Hybridbereitstellung mithilfe des Assistenten für die Hybridkonfiguration konfigurieren](/Exchange/exchange-hybrid) und dann [E-Mails so konfigurieren, dass sie von Office 365 zu Ihrem E-Mail-Server fließen,](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/set-up-connectors-to-route-mail#part-1-configure-mail-to-flow-from-office-365-to-your-on-premises-email-server) und [E-Mails so konfigurieren, dass sie von Ihrem E-Mail-Server an Office 365 gesendet werden.](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/set-up-connectors-to-route-mail#part-2-configure-mail-to-flow-from-your-email-server-to-office-365) Nachdem Sie E-Mails für den Fluss durch Office 365 konfiguriert haben, können Sie mithilfe dieser Anleitung Nachrichtenflussregeln für OME konfigurieren.

## <a name="create-mail-flow-rules-to-encrypt-email-messages-with-the-new-ome-capabilities"></a>Erstellen von Nachrichtenflussregeln zum Verschlüsseln von E-Mail-Nachrichten mit den neuen OME-Funktionen

Sie können Nachrichtenflussregeln zum Auslösen der Nachrichtenverschlüsselung mit den neuen OME-Funktionen mithilfe des EAC definieren.

### <a name="use-the-eac-to-create-a-rule-for-encrypting-email-messages-with-the-new-ome-capabilities"></a>Verwenden des EAC zum Erstellen einer Regel zum Verschlüsseln von E-Mail-Nachrichten mit den neuen OME-Funktionen

1. Melden Sie sich in einem Webbrowser unter Verwendung eines Geschäfts-, Schul- oder Unikontos, dem globale Administratorberechtigungen gewährt wurden, [bei Office 365 an.](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser)

2. Wählen Sie die **Kachel "Administrator"** aus.

3. Wählen Sie im Microsoft 365 Admin Center **Admin Centers** \> **Exchange** aus.

4. Wechseln Sie im **Exchange-Verwaltungskonsole** zu \> **Nachrichtenflussregeln,** und wählen Sie **das** Symbol ![ "Neu ](../media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) \> **Neu" aus, um eine neue Regel zu erstellen.** Weitere Informationen zur Verwendung des EAC finden Sie im [Exchange Admin Center in Exchange Online.](/exchange/exchange-admin-center)

5. Geben Sie unter **"Name"** einen Namen für die Regel ein, z. B. "E-Mail für DrToniRamos@hotmail.com verschlüsseln".

6. Wählen Sie unter **"Diese Regel anwenden, wenn"** eine Bedingung aus, und geben Sie bei Bedarf einen Wert ein. Um z. B. Nachrichten zu verschlüsseln, die zu DrToniRamos@hotmail.com:

   1. Wählen Sie unter **Diese Regel anwenden, wenn****the recipient is** (Der Empfänger ist) aus.

   2. Wählen Sie in der Kontaktliste einen vorhandenen Namen aus, oder geben Sie im Feld **Namen prüfen** eine neue E-Mail-Adresse ein.

      - Um einen vorhandenen Namen auszuwählen, wählen Sie ihn in der Liste aus, und klicken Sie dann auf **OK**.

      - Geben Sie zum Eingeben eines neuen Namens eine E-Mail-Adresse in das **Kontrollkästchen "Namen"** ein, und aktivieren Sie dann **"Namen aktivieren** \> **OK".**

7. Wenn Sie weitere Bedingungen hinzufügen möchten, wählen Sie **"Weitere Optionen"** und dann **"Bedingung hinzufügen"** und dann aus der Liste aus.

   Wenn Sie die Regel beispielsweise nur anwenden möchten, wenn sich der Empfänger außerhalb Ihrer Organisation befindet, wählen Sie **Bedingung hinzufügen** und dann **"Empfänger ist extern/intern** \> **Außerhalb der Organisation** \> **OK"** aus.

8. Um die Verschlüsselung mithilfe der neuen OME-Funktionen zu aktivieren, wählen Sie unter **"Folgendes"** die Option **"Nachrichtensicherheit ändern"** und dann **"Anwenden Office 365-Nachrichtenverschlüsselung und Rechteschutz"** aus. Wählen Sie eine RMS-Vorlage aus der Liste aus, klicken Sie auf **"Speichern"** und dann auf **"OK".**
  
  Die Liste der Vorlagen enthält alle Standardvorlagen und -optionen sowie alle benutzerdefinierten Vorlagen, die Sie zur Verwendung durch Office 365 erstellt haben. Wenn die Liste leer ist, stellen Sie sicher, dass Sie Office 365-Nachrichtenverschlüsselung mit den neuen Funktionen eingerichtet haben, wie unter [Einrichten neuer Office 365-Nachrichtenverschlüsselung-Funktionen](set-up-new-message-encryption-capabilities.md)beschrieben. Informationen zu den Standardvorlagen finden Sie unter [Konfigurieren und Verwalten von Vorlagen für Azure Information Protection.](/information-protection/deploy-use/configure-policy-templates) Informationen zur Option **"Nicht weiterleiten"** finden Sie unter ["Nicht weiterleiten"-Option für E-Mails.](/information-protection/deploy-use/configure-usage-rights#do-not-forward-option-for-emails) Informationen zur Option **"Nur verschlüsseln"** finden Sie unter ["Nur verschlüsseln" für E-Mails.](/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails)

  Sie können **die Aktion hinzufügen** auswählen, wenn Sie eine andere Aktion angeben möchten.

### <a name="use-the-eac-to-update-an-existing-mail-flow-rule-to-use-the-new-ome-capabilities"></a>Verwenden des EAC zum Aktualisieren einer vorhandenen Nachrichtenflussregel zur Verwendung der neuen OME-Funktionen

1. Melden Sie sich in einem Webbrowser unter Verwendung eines Geschäfts-, Schul- oder Unikontos, dem globale Administratorberechtigungen gewährt wurden, [bei Office 365 an.](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser)

2. Wählen Sie die **Kachel "Administrator"** aus.

3. Wählen Sie im Microsoft 365 Admin Center **Admin Centers** \> **Exchange** aus.

4. Navigieren Sie in der Exchange-Verwaltungskonsole zu **Nachrichtenfluss** \> **Regeln**.

5. Wählen Sie in der Liste der Nachrichtenflussregeln die Regel aus, die Sie ändern möchten, um die neuen OME-Funktionen zu verwenden, und **wählen** Sie dann das ![ Bearbeitungssymbol ](../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif) aus.

6. Um die Verschlüsselung mit den neuen OME-Funktionen zu aktivieren, wählen Sie unter **"Folgendes"** die Option **"Nachrichtensicherheit ändern"** und dann **"Anwenden Office 365-Nachrichtenverschlüsselung und Rechteschutz"** aus. Wählen Sie eine RMS-Vorlage aus der Liste aus, wählen Sie **"Speichern"** und dann **"OK"** aus.

   Die Liste der Vorlagen enthält alle Standardvorlagen und -optionen sowie alle benutzerdefinierten Vorlagen, die Sie zur Verwendung durch Office 365 erstellt haben. Wenn die Liste leer ist, stellen Sie sicher, dass Sie Office 365-Nachrichtenverschlüsselung mit den neuen Funktionen eingerichtet haben, wie unter ["Einrichten neuer Office 365-Nachrichtenverschlüsselung Funktionen,](set-up-new-message-encryption-capabilities.md)die auf Azure Information Protection aufbauen" beschrieben. Informationen zu den Standardvorlagen finden Sie unter [Konfigurieren und Verwalten von Vorlagen für Azure Information Protection.](/information-protection/deploy-use/configure-policy-templates) Informationen zur Option "Nicht weiterleiten" finden Sie unter ["Nicht weiterleiten"-Option für E-Mails.](/information-protection/deploy-use/configure-usage-rights#do-not-forward-option-for-emails) Informationen zur Option "Nur verschlüsseln" finden Sie unter ["Nur verschlüsseln" für E-Mails.](/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails)

   Sie können **die Aktion hinzufügen** auswählen, wenn Sie eine andere Aktion angeben möchten.

7. Entfernen Sie aus der Liste **"Do the following"** alle Aktionen, **die zum Ändern der Nachrichtensicherheit** zugewiesen \> **sind. Wenden Sie die vorherige Version von OME** an.

8. Wählen Sie **Speichern** aus.

## <a name="create-mail-flow-rules-to-remove-encryption-for-email-messages-with-the-new-ome-capabilities"></a>Erstellen von Nachrichtenflussregeln zum Entfernen der Verschlüsselung für E-Mail-Nachrichten mit den neuen OME-Funktionen

Sie können Nachrichtenflussregeln zum Auslösen der Nachrichtenverschlüsselung mit den neuen OME-Funktionen mithilfe des EAC definieren.

### <a name="use-the-eac-to-create-a-rule-to-remove-encryption-from-email-messages-with-the-new-ome-capabilities"></a>Verwenden des EAC zum Erstellen einer Regel zum Entfernen der Verschlüsselung aus E-Mail-Nachrichten mit den neuen OME-Funktionen

Sie können verschlüsselung entfernen, die von Ihrer Organisation angewendet wird.

1. Melden Sie sich in einem Webbrowser unter Verwendung eines Geschäfts-, Schul- oder Unikontos, dem globale Administratorberechtigungen gewährt wurden, [bei Office 365 an.](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser)

2. Wählen Sie die **Kachel "Administrator"** aus.

3. Wählen Sie im Microsoft 365 Admin Center **Admin Centers** \> **Exchange** aus.

4. Wechseln Sie im **Exchange-Verwaltungskonsole** zu \> **Nachrichtenflussregeln,** und wählen Sie **das** Symbol ![ "Neu ](../media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) \> **Neu" aus, um eine neue Regel zu erstellen.** Weitere Informationen zur Verwendung des EAC finden Sie im [Exchange Admin Center in Exchange Online.](/exchange/exchange-admin-center)

5. Geben Sie unter **"Name"** einen Namen für die Regel ein, z. B. "Verschlüsselung von ausgehenden E-Mails entfernen".

6. Wählen Sie **unter "Diese Regel anwenden, wenn"** die Bedingungen aus, unter denen die Verschlüsselung aus Nachrichten entfernt werden soll. Add **The sender is located** Inside the \> **organization** for sending mail _or_ The recipient **is located** Inside the \> **organization** for receiving mail.

7. Wählen Sie **unter "Folgendes"** die Option **"Nachrichtensicherheit** \> **entfernen Office 365-Nachrichtenverschlüsselung und Rechteschutz** ändern" aus.

8. Klicken Sie auf **Speichern**.

## <a name="create-mail-flow-rules-for-office-365-message-encryption-without-the-new-capabilities"></a>Erstellen von Nachrichtenflussregeln für Office 365-Nachrichtenverschlüsselung ohne die neuen Funktionen

Wenn Sie Ihre Organisation noch nicht auf die neuen OME-Funktionen umgestellt haben, empfiehlt Microsoft, einen Plan für den Wechsel zu den neuen OME-Funktionen zu erstellen, sobald dies für Ihre Organisation sinnvoll ist. Anweisungen finden Sie unter [Einrichten neuer Office 365-Nachrichtenverschlüsselung Funktionen, die auf Azure Information Protection aufbauen.](set-up-new-message-encryption-capabilities.md) Andernfalls finden Sie weitere Informationen unter [Definieren von Nachrichtenflussregeln für Office 365-Nachrichtenverschlüsselung, die die neuen OME-Funktionen nicht verwenden.](legacy-information-for-message-encryption.md#defining-mail-flow-rules-for-office-365-message-encryption-that-dont-use-the-new-ome-capabilities)

## <a name="related-topics"></a>Verwandte Themen

[Verschlüsselung in Office 365](encryption.md)

[Einrichten neuer Office 365-Nachrichtenverschlüsselungsfunktionen](set-up-new-message-encryption-capabilities.md)

[Hinzufügen von Branding zu verschlüsselten Nachrichten](add-your-organization-brand-to-encrypted-messages.md)

[Nachrichtenflussregeln (Transportregeln) in Exchange Online](/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)
