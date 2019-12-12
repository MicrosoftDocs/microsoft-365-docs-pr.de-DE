---
title: Einrichten einer benutzerdefinierten Liste "do-not-Rewrite-URLs" mithilfe Office 365 sicherer ATP-Links
ms.author: tracyp
author: msfttracyp
manager: dansimp
audience: Admin
ms.topic: article
ms.date: 08/29/2019
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 35dbfd99-da5a-422b-9b0e-c6caf3b645fa
ms.collection:
- M365-security-compliance
description: Wenn Sie Ihre ATP-Richtlinien für sichere Links einrichten, können Sie eine "do-not-rewrite"-Liste mit URLs einfügen, um es einigen Personen in Ihrer Organisation zu ermöglichen, Websites zu besuchen, die Sie in Ihre Liste aufnehmen.
ms.openlocfilehash: b823ac1e995177a6f576d01c3ef686288ed47cbf
ms.sourcegitcommit: 5710ce729c55d95b8b452d99ffb7ea92b5cb254a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/11/2019
ms.locfileid: "39971463"
---
# <a name="set-up-a-custom-do-not-rewrite-urls-list-using-office-365-atp-safe-links"></a>Einrichten einer benutzerdefinierten Liste "do-not-Rewrite-URLs" mithilfe Office 365 sicherer ATP-Links

> [!IMPORTANT]
> Dieser Artikel richtet sich an Geschäftskunden, die über [Office 365 Advanced Threat Protection](office-365-atp.md) verfügen. Wenn Sie ein Privatbenutzer sind, der nach Informationen zu sicheren Links in Outlook sucht, lesen Sie [Erweiterte Outlook.com-Sicherheit](https://support.office.com/article/882d2243-eab9-4545-a58a-b36fee4a46e2).

Mit [Office 365 Advanced Threat Protection](office-365-atp.md) (ATP) kann Ihre Organisation eine [benutzerdefinierte Blockierte URL](set-up-a-custom-blocked-urls-list-wtih-atp.md)haben, wenn Personen in e-Mail-Nachrichten oder bestimmten Office-Dokumenten auf Webadressen (URLs) klicken, wird verhindert, dass Sie zu diesen URLs wechseln. Ihre Organisation kann auch benutzerdefinierte Listen für bestimmte Gruppen in Ihrer Organisation erstellen. Eine Liste "nicht umschreiben" ermöglicht einigen Benutzern das Aufrufen von URLs, die ansonsten durch [ATP-sichere Links in Office 365](atp-safe-links.md)blockiert werden. 
  
In diesem Artikel wird beschrieben, wie Sie eine Liste von URLs angeben, die von der Überprüfung der ATP-sichere Links ausgeschlossen werden, und einige wichtige Punkte, die beachtet werden sollten.

## <a name="set-up-a-do-not-rewrite-list"></a>Einrichten einer Liste "nicht umschreiben"

Der Schutz für ATP-Verknüpfungen verwendet mehrere Listen, einschließlich der Liste der blockierten URLs Ihrer Organisation und der Listen "nicht umschreiben" für Ausnahmen. Wenn Sie über die erforderlichen Berechtigungen verfügen, können Sie die benutzerdefinierten Listen "nicht umschreiben" einrichten. Sie tun dies, wenn Sie Richtlinien für sichere Links hinzufügen oder bearbeiten, die für bestimmte Empfänger in Ihrer Organisation gelten. 

Um ATP-Richtlinien zu bearbeiten (oder zu definieren), muss Ihnen eine entsprechende Rolle zugewiesen sein. Die folgende Tabelle enthält einige Beispiele. Weitere Informationen finden Sie unter [Berechtigungen im Office 365 Security #a0 Compliance Center](permissions-in-the-security-and-compliance-center.md).

|Rolle  |Wo/wie zugewiesen  |
|---------|---------|
|Globaler Office 365-Administrator |Die Person, die sich zum Kauf Office 365 registriert, ist standardmäßig ein globaler Administrator. (Weitere Informationen finden Sie unter [Informationen zu Office 365 Administratorrollen](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles) .)         |
|Sicherheitsadministrator |Azure Active Directory Admin Center ([https://aad.portal.azure.com](https://aad.portal.azure.com))|
|Exchange Online-Organisationsverwaltung |Exchange Admin Center ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp)) <br>oder <br>  PowerShell-Cmdlets (siehe [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell)) |

> [!TIP]
> Weitere Informationen zu Rollen und Berechtigungen finden Sie unter [Permissions in the Office 365 &amp; Security Compliance Center](permissions-in-the-security-and-compliance-center.md).

### <a name="to-view-or-edit-a-custom-do-not-rewrite-urls-list"></a>So zeigen Sie eine benutzerdefinierte Liste der URLs "nicht umschreiben" an oder bearbeiten diese
  
1. Wechseln Sie [https://protection.office.com](https://protection.office.com) zu, und melden Sie sich mit ihrem geschäftlichen oder Schulkonto an. 
    
2. Klicken Sie im linken Navigationsbereich unter **sichere Links**zur **Bedrohungs Verwaltungs** \> **Richtlinie** \> .
    
3. Wählen Sie im Abschnitt **Richtlinien für bestimmte Empfänger** festlegen die Option **neu** aus (die Schaltfläche neu ähnelt einem Plus **+** Zeichen ()), um eine neue Richtlinie zu erstellen. (Alternativ können Sie eine vorhandene Richtlinie bearbeiten.)<br/>![Wählen Sie neu aus, um eine Richtlinie zu sicheren Links für bestimmte e-Mail-Empfänger hinzuzufügen](../media/01073f42-3cec-4ddb-8c10-4d33ec434676.png)
  
4. Geben Sie einen Namen und eine Beschreibung für Ihre Richtlinie an.
    
5. Aktivieren Sie im Abschnitt **folgende URLs nicht umschreiben** das Kontrollkästchen **gültige URL eingeben** , und geben Sie dann eine URL ein, und wählen Sie dann das Pluszeichen (+) aus. 
    
6. Wählen Sie im Abschnitt **angewendet für** **den Empfänger ist Mitglied von aus**, und wählen Sie dann die Gruppe (n) aus, die Sie in Ihre Richtlinie einschließen möchten. Klicken Sie auf **Hinzufügen**, und wählen Sie dann **OK**aus.
    
7. Wenn Sie das Hinzufügen von URLs abgeschlossen haben, wählen Sie in der unteren rechten Ecke des Bildschirms **Speichern**aus.
    
> [!NOTE]
> Stellen Sie sicher, dass Sie die benutzerdefinierte Liste der blockierten URLs in Ihrer Organisation überprüft haben. Weitere Informationen finden Sie unter [Einrichten einer benutzerdefinierten Liste blockierter URLs mithilfe von ATP-Sicherheits Links](set-up-a-custom-blocked-urls-list-wtih-atp.md). 
  
## <a name="important-points-to-keep-in-mind"></a>Wichtige Punkte, die beachtet werden sollten

- Alle URLs, die Sie in der Liste "nicht umschreiben" angeben, werden von der Überprüfung der ATP-sichere Links für die von Ihnen angegebenen Empfänger ausgeschlossen.
 
- Wenn Sie bereits über eine Liste von URLs in Ihrer Liste "nicht umschreiben" verfügen, stellen Sie sicher, dass Sie diese Liste überprüfen und je nach Bedarf Platzhalter hinzufügen. Wenn Ihre vorhandene Liste beispielsweise einen Eintrag wie `https://contoso.com/a` enthält und Sie untergeordnete Pfade wie `https://contoso.com/a/b` in Ihrer Richtlinie einschließen möchten, fügen Sie Ihrem Eintrag ein Platzhalterzeichen hinzu, `https://contoso.com/a/*`damit es aussieht.
    
- Fügen Sie keinen Schrägstrich (/) in die URLs ein, die Sie in der Liste "nicht umschreiben" angeben. Geben Sie `contoso.com`beispielsweise nicht in `contoso.com/` die Liste "nicht umschreiben" ein.

- Wenn Sie eine Liste "nicht umschreiben" für eine Richtlinie für ATP-sichere Links angeben, können Sie bis zu drei Platzhalter Sternchen\*() einschließen. Platzhalterzeichen\*() werden verwendet, um explizit Präfixe oder Unterdomänen wie `https://` oder `https://`hinzuzufügen. Ein Eintrag, wie er `contoso.com` nicht mit der Liste " `*.contoso.com/*` nicht umschreiben" übereinstimmt. Sie müssen, `*.contoso.com/*` Wenn Sie den Benutzern das Besuchen einer Domäne und ihrer Unterdomänen und Pfade gestatten möchten.
    
In der folgenden Tabelle sind Beispiele aufgeführt, was Sie eingeben können und welche Auswirkungen diese Einträge haben.
    
|**Beispieleintrag**|**Funktionsweise**|
|:-----|:-----|
|`contoso.com`|Ermöglicht Empfängern das Aufrufen einer Website `https://contoso.com` wie, aber keine Unterdomänen oder Pfade.|
|`*.contoso.com/*`  <br/> |Ermöglicht Empfängern das Besuchen einer Domäne, Unterdomänen und Pfaden, wie `https://www.contoso.com`, `https://www.contoso.com` `https://maps.contoso.com`, oder`https://www.contoso.com/a`  <br/> |
|`https://contoso.com/a`  <br/> |Ermöglicht bestimmten Empfängern das Besuchen einer Website `https://contoso.com/a`wie, aber keine untergeordneten Pfade wie`https://contoso.com/a/b`  <br/> |
|`https://contoso.com/a/*`  <br/> |Ermöglicht bestimmten Empfängern das Besuchen einer Website `https://contoso.com/a` wie und untergeordnete Pfade wie`https://contoso.com/a/b`  <br/> |
   
 
