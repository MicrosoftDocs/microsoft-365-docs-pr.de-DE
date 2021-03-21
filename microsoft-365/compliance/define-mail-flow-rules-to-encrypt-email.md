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
description: Administratoren können lernen, Nachrichtenflussregeln (Transportregeln) zum Verschlüsseln und Entschlüsseln von Nachrichten mithilfe der Office 365-Nachrichtenverschlüsselung zu erstellen.
ms.openlocfilehash: 5c0f67acdb5d8fbfff216742cab1c49732c4ab24
ms.sourcegitcommit: 30c3054004ddc9d6059c11d55577552aa2464810
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/20/2021
ms.locfileid: "50939646"
---
# <a name="define-mail-flow-rules-to-encrypt-email-messages"></a>Definieren von Nachrichtenflussregeln zum Verschlüsseln von E-Mail-Nachrichten

Als Administrator, der Exchange Online verwaltet, können Sie Nachrichtenflussregeln (auch als Transportregeln bezeichnet) erstellen, um E-Mail-Nachrichten zu schützen, die Sie senden und empfangen. Sie können Regeln einrichten, um alle ausgehenden E-Mail-Nachrichten zu verschlüsseln und die Verschlüsselung aus verschlüsselten Nachrichten zu entfernen, die aus Ihrer Organisation oder aus Antworten auf verschlüsselte Nachrichten von Ihrer Organisation gesendet werden. Sie können das Exchange Admin Center (EAC) oder Exchange Online PowerShell verwenden, um diese Regeln zu erstellen. Zusätzlich zu den allgemeinen Verschlüsselungsregeln können Sie auch die Aktivierung oder Deaktivierung einzelner von Optionen für die Verschlüsselung einzelner Nachrichten für Endbenutzer auswählen.

Eingehende E-Mails von Absendern außerhalb Ihrer Organisation können nicht verschlüsselt werden.

Wenn Sie kürzlich von Active Directory RMS zu Azure Information Protection migriert haben, müssen Sie Ihre vorhandenen Nachrichtenflussregeln überprüfen, um sicherzustellen, dass sie in Ihrer neuen Umgebung weiterhin funktionieren. Wenn Sie außerdem die neuen Office 365 Message Encryption (OME)-Funktionen nutzen möchten, die Ihnen über Azure Information Protection zur Verfügung stehen, müssen Sie Ihre vorhandenen Nachrichtenflussregeln aktualisieren. Andernfalls erhalten Ihre Benutzer weiterhin verschlüsselte E-Mails, die das vorherige HTML-Anlagenformat anstelle der neuen, nahtlosen OME-Erfahrung verwenden. Wenn Sie OME noch nicht eingerichtet haben, finden Sie weitere Informationen unter Einrichten neuer [Office 365-Nachrichtenverschlüsselungsfunktionen.](set-up-new-message-encryption-capabilities.md)

Informationen zu den Komponenten, die Nachrichtenflussregeln enthalten, und zur Funktionsweise von Nachrichtenflussregeln finden Sie unter [Nachrichtenflussregeln (Transportregeln) in Exchange Online](/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules). Weitere Informationen zur Funktionsweise von Nachrichtenflussregeln mit Azure Information Protection finden Sie unter [Configuring Exchange Online mail flow rules for Azure Information Protection labels](/azure/information-protection/deploy-use/configure-exo-rules).

> [!IMPORTANT]
> In hybriden Exchange-Umgebungen können lokale Benutzer verschlüsselte E-Mails nur mit OME senden und empfangen, wenn E-Mails über Exchange Online geroutet werden. Um OME in einer hybriden Exchange-Umgebung zu konfigurieren, müssen Sie zunächst die Hybridkonfiguration mithilfe des Assistenten für die Hybridkonfiguration konfigurieren und dann E-Mails so konfigurieren, dass sie von [Office 365](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/set-up-connectors-to-route-mail#part-1-configure-mail-to-flow-from-office-365-to-your-on-premises-email-server) zu Ihrem E-Mail-Server fließen und E-Mails so konfigurieren, dass sie von Ihrem E-Mail-Server zu [Office 365](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/set-up-connectors-to-route-mail#part-2-configure-mail-to-flow-from-your-email-server-to-office-365)fließen. [](/Exchange/exchange-hybrid) Nachdem Sie E-Mails für den Fluss durch Office 365 konfiguriert haben, können Sie mithilfe dieser Anleitung Nachrichtenflussregeln für OME konfigurieren.

## <a name="create-mail-flow-rules-to-encrypt-email-messages-with-the-new-ome-capabilities"></a>Erstellen von Nachrichtenflussregeln zum Verschlüsseln von E-Mail-Nachrichten mit den neuen OME-Funktionen

Sie können Nachrichtenflussregeln für das Auslösen der Nachrichtenverschlüsselung mit den neuen OME-Funktionen mithilfe der EAC definieren.

### <a name="use-the-eac-to-create-a-rule-for-encrypting-email-messages-with-the-new-ome-capabilities"></a>Verwenden der EAC zum Erstellen einer Regel zum Verschlüsseln von E-Mail-Nachrichten mit den neuen OME-Funktionen

1. Melden Sie sich in einem Webbrowser mit einem Geschäfts- oder Schulkonto an, dem globale Administratorberechtigungen erteilt wurden, [bei Office 365](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser).

2. Wählen Sie die **Kachel Admin** aus.

3. Wählen Sie im Microsoft 365 Admin Center **Admin Centers** \> **Exchange** aus.

4. Wechseln Sie in der EAC zu **Nachrichtenflussregeln,** \>  und wählen **Sie Neues** Symbol Neue Regel ![ erstellen ](../media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) \> **aus.** Weitere Informationen zur Verwendung der EAC finden Sie unter [Exchange Admin Center in Exchange Online](/exchange/exchange-admin-center).

5. Geben Sie unter **Name** einen Namen für die Regel ein, z. B. Verschlüsseln von E-Mails für DrToniRamos@hotmail.com.

6. Wählen **Sie unter Diese Regel anwenden, wenn**, eine Bedingung aus, und geben Sie bei Bedarf einen Wert ein. So verschlüsseln Sie z. B. Nachrichten, die an DrToniRamos@hotmail.com:

   1. Wählen Sie unter **Diese Regel anwenden, wenn****the recipient is** (Der Empfänger ist) aus.

   2. Wählen Sie in der Kontaktliste einen vorhandenen Namen aus, oder geben Sie im Feld **Namen prüfen** eine neue E-Mail-Adresse ein.

      - Um einen vorhandenen Namen auszuwählen, wählen Sie ihn in der Liste aus, und klicken Sie dann auf **OK**.

      - Geben Sie zum Eingeben eines neuen Namens eine E-Mail-Adresse in **das** Kontrollkästchen Namen ein, und wählen Sie dann **Namen überprüfen** \> **OK aus.**

7. Wenn Sie weitere Bedingungen hinzufügen möchten, wählen Sie **Weitere Optionen** aus, und wählen Sie dann Bedingung **hinzufügen aus,** und wählen Sie aus der Liste aus.

   Um die Regel beispielsweise nur anzuwenden, wenn sich der Empfänger außerhalb Ihrer Organisation befindet, wählen Sie **Bedingung** hinzufügen aus, und wählen Sie dann Der Empfänger ist **extern/intern** Außerhalb der \> **Organisation** \> **OK aus.**

8. Um die Verschlüsselung mithilfe der neuen OME-Funktionen zu aktivieren, wählen Sie unter Gehen Sie **wie** folgt aus **Ändern** der Nachrichtensicherheit aus, und wählen Sie dann **Office 365-Nachrichtenverschlüsselung und Rechteschutz anwenden aus.** Wählen Sie in der Liste eine RMS-Vorlage aus, wählen Sie **Speichern** und dann **OK aus.**
  
  Die Liste der Vorlagen enthält alle Standardvorlagen und -optionen sowie alle benutzerdefinierten Vorlagen, die Sie für die Verwendung durch Office 365 erstellt haben. Wenn die Liste leer ist, stellen Sie sicher, dass Sie die Office 365-Nachrichtenverschlüsselung mit den neuen Funktionen eingerichtet haben, wie unter Einrichten neuer [Office 365-Nachrichtenverschlüsselungsfunktionen beschrieben.](set-up-new-message-encryption-capabilities.md) Informationen zu den Standardvorlagen finden Sie unter [Configuring and managing templates for Azure Information Protection](/information-protection/deploy-use/configure-policy-templates). Weitere Informationen zur Option **Nicht** weiterleiten finden Sie unter [Do Not Forward option for emails](/information-protection/deploy-use/configure-usage-rights#do-not-forward-option-for-emails). Informationen zur Option nur **verschlüsseln** finden Sie unter [Encrypt-only option for emails](/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails).

  Sie können Die **Aktion hinzufügen auswählen,** wenn Sie eine andere Aktion angeben möchten.

### <a name="use-the-eac-to-update-an-existing-mail-flow-rule-to-use-the-new-ome-capabilities"></a>Aktualisieren einer vorhandenen Nachrichtenflussregel mithilfe der EAC zur Verwendung der neuen OME-Funktionen

1. Melden Sie sich in einem Webbrowser mit einem Geschäfts- oder Schulkonto an, dem globale Administratorberechtigungen erteilt wurden, [bei Office 365](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser).

2. Wählen Sie die **Kachel Admin** aus.

3. Wählen Sie im Microsoft 365 Admin Center **Admin Centers** \> **Exchange** aus.

4. Navigieren Sie in der Exchange-Verwaltungskonsole zu **Nachrichtenfluss** \> **Regeln**.

5. Wählen Sie in der Liste der Nachrichtenflussregeln die Regel aus, die Sie ändern möchten, um die neuen OME-Funktionen zu verwenden, und wählen Sie dann **Bearbeiten** ![ -Symbol ](../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif) aus.

6. Um die Verschlüsselung mithilfe der neuen OME-Funktionen zu aktivieren, wählen Sie unter Gehen Sie **wie** folgt aus **Ändern** der Nachrichtensicherheit aus, und wählen Sie dann **Office 365-Nachrichtenverschlüsselung und Rechteschutz anwenden aus.** Wählen Sie in der Liste eine RMS-Vorlage aus, wählen Sie **Speichern** und dann **OK aus.**

   Die Liste der Vorlagen enthält alle Standardvorlagen und -optionen sowie alle benutzerdefinierten Vorlagen, die Sie für die Verwendung durch Office 365 erstellt haben. Wenn die Liste leer ist, stellen Sie sicher, dass Sie die Office 365-Nachrichtenverschlüsselung mit den neuen Funktionen eingerichtet haben, wie unter Einrichten neuer [Office 365-Nachrichtenverschlüsselungsfunktionen](set-up-new-message-encryption-capabilities.md)beschrieben, die auf Azure Information Protection aufgebaut sind. Informationen zu den Standardvorlagen finden Sie unter [Configuring and managing templates for Azure Information Protection](/information-protection/deploy-use/configure-policy-templates). Weitere Informationen zur Option Nicht weiterleiten finden Sie unter [Do Not Forward option for emails](/information-protection/deploy-use/configure-usage-rights#do-not-forward-option-for-emails). Informationen zur Option nur verschlüsseln finden Sie unter [Encrypt Only option for emails](/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails).

   Sie können Die **Aktion hinzufügen auswählen,** wenn Sie eine andere Aktion angeben möchten.

7. Entfernen Sie **in der Liste** Ausführen der  folgenden Liste alle Aktionen, die dem Ändern der Nachrichtensicherheit zugewiesen sind Anwenden \> **der vorherigen Version von OME**.

8. Wählen Sie **Speichern** aus.

## <a name="create-mail-flow-rules-to-remove-encryption-for-email-messages-with-the-new-ome-capabilities"></a>Erstellen von Nachrichtenflussregeln zum Entfernen der Verschlüsselung für E-Mail-Nachrichten mit den neuen OME-Funktionen

Sie können Nachrichtenflussregeln für das Auslösen der Nachrichtenverschlüsselung mit den neuen OME-Funktionen mithilfe der EAC definieren.

### <a name="use-the-eac-to-create-a-rule-to-remove-encryption-from-email-messages-with-the-new-ome-capabilities"></a>Verwenden der EAC zum Erstellen einer Regel zum Entfernen der Verschlüsselung aus E-Mail-Nachrichten mit den neuen OME-Funktionen

Sie können die Verschlüsselung entfernen, auf die Von Ihrer Organisation zugegriffen werden kann. Dies bedeutet alle E-Mails mit Verschlüsselung, die von der Organisation angewendet werden, oder alle E-Mails, die nur durch Verschlüsselungseinschränkungen geschützt sind.

1. Melden Sie sich in einem Webbrowser mit einem Geschäfts- oder Schulkonto an, dem globale Administratorberechtigungen erteilt wurden, [bei Office 365](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser).

2. Wählen Sie die **Kachel Admin** aus.

3. Wählen Sie im Microsoft 365 Admin Center **Admin Centers** \> **Exchange** aus.

4. Wechseln Sie in der EAC zu **Nachrichtenflussregeln,** \>  und wählen **Sie Neues** Symbol Neue Regel ![ erstellen ](../media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) \> **aus.** Weitere Informationen zur Verwendung der EAC finden Sie unter [Exchange Admin Center in Exchange Online](/exchange/exchange-admin-center).

5. Geben **Sie unter Name** einen Namen für die Regel ein, z. B. Verschlüsselung aus ausgehenden E-Mails entfernen.

6. Wählen **Sie unter Diese Regel anwenden if** die Bedingungen aus, unter denen die Verschlüsselung aus Nachrichten entfernt werden soll. Hinzufügen **Der Absender befindet sich** innerhalb der \> **Organisation** _oder_ Der Empfänger befindet **sich** innerhalb \> **der Organisation.**

7. Wählen **Sie unter Gehen Sie wie folgt** vor, die Option **Nachrichtensicherheit** \> **entfernen Office 365-Nachrichtenverschlüsselung und -rechteschutz ändern aus.**

8. Wählen Sie **Speichern** aus.

## <a name="create-mail-flow-rules-for-office-365-message-encryption-without-the-new-capabilities"></a>Erstellen von Nachrichtenflussregeln für die Office 365-Nachrichtenverschlüsselung ohne die neuen Funktionen

Wenn Sie Ihre Organisation noch nicht in die neuen OME-Funktionen verschoben haben, empfiehlt Microsoft, einen Plan für den Wechsel zu den neuen OME-Funktionen zu erstellen, sobald es für Ihre Organisation sinnvoll ist. Anweisungen finden Sie [unter Einrichten neuer Office 365-Nachrichtenverschlüsselungsfunktionen,](set-up-new-message-encryption-capabilities.md)die auf Azure Information Protection aufgebaut sind. Weitere Informationen finden Sie unter [Defining mail flow rules for Office 365 Message Encryption that don't use the new OME capabilities](legacy-information-for-message-encryption.md#defining-mail-flow-rules-for-office-365-message-encryption-that-dont-use-the-new-ome-capabilities).

## <a name="related-topics"></a>Verwandte Themen

[Verschlüsselung in Office 365](encryption.md)

[Einrichten neuer Office 365-Nachrichtenverschlüsselungsfunktionen](set-up-new-message-encryption-capabilities.md)

[Hinzufügen von Branding zu verschlüsselten Nachrichten](add-your-organization-brand-to-encrypted-messages.md)

[Nachrichtenflussregeln (Transportregeln) in Exchange Online](/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)

[Nachrichtenflussregeln (Transportregeln) in Exchange Online Protection](../security/office-365-security/mail-flow-rules-transport-rules-0.md)
