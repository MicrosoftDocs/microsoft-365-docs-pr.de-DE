---
title: Einrichten einer benutzerdefinierten Liste "do-not-Rewrite-URLs" mithilfe von ATP-Safe-Links
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.topic: article
ms.date: ''
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 35dbfd99-da5a-422b-9b0e-c6caf3b645fa
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Hier erfahren Sie, wie Sie benutzerdefinierte blockierte URLs für Benutzer einrichten und eine Liste mit URLs für eine Gruppe von Benutzern in Office 365 Richtlinien für ATP-sichere Links erstellen.
ms.openlocfilehash: 17828566769f438439eebcb4e460ecac1147a648
ms.sourcegitcommit: 445b249a6f0420b32e49742fd7744006c7090b2b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/18/2020
ms.locfileid: "46798330"
---
# <a name="set-up-a-custom-do-not-rewrite-urls-list-using-atp-safe-links"></a>Einrichten einer benutzerdefinierten Liste "do-not-Rewrite-URLs" mithilfe von ATP-Safe-Links

> [!IMPORTANT]
> Dieser Artikel richtet sich an Geschäftskunden, die über [Office 365 Advanced Threat Protection](office-365-atp.md) verfügen. Wenn Sie ein Privatbenutzer sind, der nach Informationen zu sicheren Links in Outlook sucht, lesen Sie [Erweiterte Outlook.com-Sicherheit](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).

Mit [Office 365 Advanced Threat Protection](office-365-atp.md) (ATP) kann Ihre Organisation eine [benutzerdefinierte Blockierte URL](set-up-a-custom-blocked-urls-list-atp.md)haben, wenn Personen in e-Mail-Nachrichten oder bestimmten Office-Dokumenten auf Webadressen (URLs) klicken, wird verhindert, dass Sie zu diesen URLs wechseln. Ihre Organisation kann auch benutzerdefinierte Listen für bestimmte Gruppen in Ihrer Organisation erstellen. Eine Liste "nicht umschreiben" ermöglicht einigen Benutzern das Aufrufen von URLs, die ansonsten durch [ATP-sichere Links in Office 365](atp-safe-links.md)blockiert werden.

In diesem Artikel wird beschrieben, wie Sie eine Liste von URLs angeben, die von der Überprüfung der ATP-sichere Links ausgeschlossen werden, und einige wichtige Punkte, die beachtet werden sollten.

> [!NOTE]
> Wenn Ihre Organisation Richtlinien für sichere Links verwendet, ist die Liste "nicht umschreiben" die einzige unterstützte Methode für Phishing-Tests von Drittanbietern.

## <a name="set-up-a-do-not-rewrite-list"></a>Einrichten einer Liste "nicht umschreiben"

Der Schutz für ATP-Verknüpfungen verwendet mehrere Listen, einschließlich der Liste der blockierten URLs Ihrer Organisation und der Listen "nicht umschreiben" für Ausnahmen. Wenn Sie über die erforderlichen Berechtigungen verfügen, können Sie die benutzerdefinierten Listen "nicht umschreiben" einrichten. Sie tun dies, wenn Sie Richtlinien für sichere Links hinzufügen oder bearbeiten, die für bestimmte Empfänger in Ihrer Organisation gelten.

Um ATP-Richtlinien zu bearbeiten (oder zu definieren), muss Ihnen eine entsprechende Rolle zugewiesen sein. Die folgende Tabelle enthält einige Beispiele. Weitere Informationen finden Sie unter [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).

|Rolle|Wo/wie zugewiesen|
|---|---|
|globaler Administrator|Die Person, die sich zum Kauf von Microsoft 365 anmeldet, ist standardmäßig ein globaler Administrator. (Weitere Informationen finden Sie unter [Informationen zu Microsoft 365-Administratorrollen](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles) .)|
|Sicherheitsadministrator|Azure Active Directory Admin Center ( [https://aad.portal.azure.com](https://aad.portal.azure.com) )|
|Exchange Online-Organisationsverwaltung|Exchange Admin Center ( [https://outlook.office365.com/ecp](https://outlook.office365.com/ecp) ) <br>oder <br>  PowerShell-Cmdlets (siehe [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell))|
|

> [!TIP]
> Weitere Informationen zu Rollen und Berechtigungen finden Sie unter [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).

### <a name="to-view-or-edit-a-custom-do-not-rewrite-urls-list"></a>So zeigen Sie eine benutzerdefinierte Liste der URLs "nicht umschreiben" an oder bearbeiten diese

1. Wechseln Sie zu, [https://protection.office.com](https://protection.office.com) und melden Sie sich mit ihrem geschäftlichen oder Schulkonto an.

2. Klicken Sie im linken Navigationsbereich unter sichere Links zur **Bedrohungs Verwaltungs** \> **Richtlinie** \> **Safe Links**.

3. Wählen Sie im Abschnitt **Richtlinien für bestimmte Empfänger** festlegen die Option **neu** aus (die Schaltfläche neu ähnelt einem Pluszeichen ( **+** )), um eine neue Richtlinie zu erstellen. (Alternativ können Sie eine vorhandene Richtlinie bearbeiten.)<br/>![Wählen Sie neu aus, um eine Richtlinie zu sicheren Links für bestimmte e-Mail-Empfänger hinzuzufügen](../../media/01073f42-3cec-4ddb-8c10-4d33ec434676.png)

4. Geben Sie einen Namen und eine Beschreibung für Ihre Richtlinie an.

5. Aktivieren **von URLs wird** umgeschrieben und anhand einer Liste bekannter böswilliger Links überprüft, wenn der Benutzer auf den Link klickt.

6. Aktivieren Sie im Abschnitt **folgende URLs nicht umschreiben** das Kontrollkästchen **gültige URL eingeben** , geben Sie eine URL ein, und klicken Sie dann auf das Pluszeichen (+).

7. Wählen Sie im Abschnitt **angewendet für** **den Empfänger ist Mitglied von aus**, und wählen Sie dann die Gruppe (n) aus, die Sie in Ihre Richtlinie einschließen möchten. Klicken Sie auf **Hinzufügen**, und wählen Sie dann **OK**aus.

8. Wenn Sie das Hinzufügen von URLs abgeschlossen haben, wählen Sie in der unteren rechten Ecke des Bildschirms **Speichern**aus.

> [!NOTE]
> Stellen Sie sicher, dass Sie die benutzerdefinierte Liste der blockierten URLs in Ihrer Organisation überprüft haben. Weitere Informationen finden Sie unter [Einrichten einer benutzerdefinierten Liste blockierter URLs mithilfe von ATP-Sicherheits Links](set-up-a-custom-blocked-urls-list-atp.md).

## <a name="important-points-to-keep-in-mind"></a>Wichtige Punkte, die beachtet werden sollten

- Alle URLs, die Sie in der Liste "nicht umschreiben" angeben, werden von der Überprüfung der ATP-sichere Links für die von Ihnen angegebenen Empfänger ausgeschlossen.

- Sie sollten häufig verwendete interne URLs zur Liste "nicht umschreiben" hinzufügen, um die Benutzerfreundlichkeit zu verbessern. Wenn Sie beispielsweise lokale Dienste wie Skype for Business oder SharePoint haben, können Sie Ihre URLs zur Liste hinzufügen, um Sie von der Überprüfung auszuschließen.

- Wenn Sie bereits über eine Liste von URLs in Ihrer Liste "nicht umschreiben" verfügen, stellen Sie sicher, dass Sie diese Liste überprüfen und je nach Bedarf Platzhalter hinzufügen. Wenn Ihre vorhandene Liste beispielsweise einen Eintrag wie enthält und Sie untergeordnete `https://contoso.com/a` Pfade wie `https://contoso.com/a/b` in Ihrer Richtlinie einschließen möchten, fügen Sie Ihrem Eintrag ein Platzhalterzeichen hinzu, damit es aussieht `https://contoso.com/a/*` .

- Wenn Sie eine Liste "nicht umschreiben" für eine Richtlinie für ATP-sichere Links angeben, können Sie bis zu drei Platzhalterzeichen ( \* ) einschließen. Platzhalter enthalten explizit Präfixe oder Unterdomänen. Beispielsweise ist der Eintrag `contoso.com` nicht identisch `*.contoso.com/*` mit, da `*.contoso.com/*` es Benutzern ermöglicht, Unterdomänen und Pfade in der angegebenen Domäne zu besuchen.

In der folgenden Tabelle sind Beispiele aufgeführt, was Sie eingeben können und welche Auswirkungen diese Einträge haben.

****

|Beispieleintrag|Funktionsweise|
|---|---|
|`contoso.com`|Ermöglicht Empfängern das Aufrufen einer Website wie, `https://contoso.com` aber keine Unterdomänen oder Pfade.|
|`*.contoso.com/*`|Ermöglicht Empfängern das Aufrufen einer Domäne, Unterdomänen und Pfaden, beispielsweise `https://www.contoso.com` ,,, `https://www.contoso.com` `https://maps.contoso.com` oder `https://www.contoso.com/a` . <br/><br/> Dieser Eintrag ist grundsätzlich besser als `*contoso.com*` , da er potenziell betrügerische Websites wie oder nicht enthält. `https://www.falsecontoso.com``https://www.false.contoso.completelyfalse.com`|
|`https://contoso.com/a`|Ermöglicht bestimmten Empfängern das Besuchen einer Website wie `https://contoso.com/a` , aber keine untergeordneten Pfade wie `https://contoso.com/a/b`|
|`https://contoso.com/a/*`|Ermöglicht bestimmten Empfängern das Besuchen einer Website wie und untergeordnete `https://contoso.com/a` Pfade wie `https://contoso.com/a/b`|
|
