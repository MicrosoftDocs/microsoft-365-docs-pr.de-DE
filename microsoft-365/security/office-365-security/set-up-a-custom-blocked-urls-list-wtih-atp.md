---
title: Einrichten einer benutzerdefinierten Liste blockierter URLs mithilfe von ATP-Sicherheits Links
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
ms.assetid: 896a7efb-1683-465e-a394-261349e5d866
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: In diesem Artikel erfahren Sie, wie Sie eine Liste blockierter URLs für Ihre Organisation mit Office 365 Advanced Threat Protection einrichten.
ms.openlocfilehash: 9e0c6e75358c97a21ab0765edf5a15bafe53d75e
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/05/2020
ms.locfileid: "44035372"
---
# <a name="set-up-a-custom-blocked-urls-list-using-atp-safe-links"></a>Einrichten einer benutzerdefinierten Liste blockierter URLs mithilfe von ATP-Sicherheits Links

> [!IMPORTANT]
> Dieser Artikel richtet sich an Geschäftskunden, die über [Office 365 Advanced Threat Protection](office-365-atp.md) verfügen. Wenn Sie ein Privatbenutzer sind, der nach Informationen zu sicheren Links in Outlook sucht, lesen Sie [Erweiterte Outlook.com-Sicherheit](https://support.office.com/article/882d2243-eab9-4545-a58a-b36fee4a46e2).

Mit [Office 365 Advanced Threat Protection](office-365-atp.md) (ATP) kann Ihre Organisation eine benutzerdefinierte Liste der blockierten Websiteadressen (URLs) haben. Wenn eine URL blockiert wird, werden Personen, die auf Links zur gesperrten URL klicken, zu einer [Warnungsseite](atp-safe-links-warning-pages.md) geleitet, die dem folgenden Bild ähnelt: 
  
![Diese Website ist blockiert](../../media/6b4bda2d-a1e6-419e-8b10-588e83c3af3f.png)
  
Die Liste Blockierte URLs wird vom Microsoft 365 for Business-Sicherheitsteam Ihrer Organisation definiert, und diese Liste gilt für alle Benutzer in der Organisation, die von Office 365 Richtlinien für ATP-sichere Links abgedeckt werden. 
  
In diesem Artikel erfahren Sie, wie Sie die Liste der benutzerdefinierten blockierten URLs Ihrer Organisation für [ATP-sichere Links in Office 365](atp-safe-links.md)einrichten.
  
## <a name="view-or-edit-a-custom-list-of-blocked-urls"></a>Anzeigen oder Bearbeiten einer benutzerdefinierten Liste blockierter URLs

[Für ATP-sichere Links in Office 365](atp-safe-links.md) werden mehrere Listen verwendet, einschließlich der Liste der benutzerdefinierten blockierten URLs in Ihrer Organisation. Wenn Sie über die erforderlichen Berechtigungen verfügen, können Sie die benutzerdefinierte Liste Ihrer Organisation einrichten. Hierzu bearbeiten Sie die Standardrichtlinie für sichere Links in Ihrer Organisation.

Um ATP-Richtlinien zu bearbeiten oder zu definieren, müssen Sie einer der in der folgenden Tabelle beschriebenen Rollen zugewiesen sein: 

|Rolle  |Wo/wie zugewiesen  |
|---------|---------|
|globaler Administrator |Die Person, die sich zum Kauf von Microsoft 365 anmeldet, ist standardmäßig ein globaler Administrator. (Weitere Informationen finden Sie unter [Informationen zu Microsoft 365-Administratorrollen](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles) .)         |
|Sicherheitsadministrator |Azure Active Directory Admin Center ([https://aad.portal.azure.com](https://aad.portal.azure.com))|
|Exchange Online-Organisationsverwaltung |Exchange Admin Center ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp)) <br>oder <br>  PowerShell-Cmdlets (siehe [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell)) |

> [!TIP]
> Weitere Informationen zu Rollen und Berechtigungen finden Sie unter [Permissions in the &amp; Security Compliance Center](permissions-in-the-security-and-compliance-center.md).

### <a name="to-view-or-edit-a-custom-blocked-urls-list"></a>So zeigen Sie eine benutzerdefinierte Liste blockierter URLs an oder bearbeiten Sie
  
1. Wechseln Sie [https://protection.office.com](https://protection.office.com) zu, und melden Sie sich mit ihrem geschäftlichen oder Schulkonto an. 
    
2. Wählen Sie im linken Navigationsbereich unter **Threat Management**die Option **Richtlinien** \> **sichere Links**aus.
    
3. Wählen Sie in den **Richtlinien für den Abschnitt gesamte Organisation** die Option **Standard**aus, und klicken Sie dann auf **Bearbeiten** (die Schaltfläche Bearbeiten ähnelt einem Bleistift).<br/>![Klicken Sie auf Bearbeiten, um die Standardrichtlinie für den Schutz von sicheren Links zu bearbeiten.](../../media/d08f9615-d947-4033-813a-d310ec2c8cca.png)<br/>Auf diese Weise können Sie die Liste der blockierten URLs anzeigen. Auf den ersten sind hier möglicherweise keine URLs aufgeführt.<br/>![Liste der blockierten URLs in der Standardrichtlinie für sichere Links](../../media/575e1449-6191-40ac-b626-030a2fd3fb11.png)
  
4. Aktivieren Sie das Kontrollkästchen **gültige URL eingeben** , geben Sie eine URL ein, und klicken Sie dann**+** auf das Pluszeichen (). 

5. Wenn Sie das Hinzufügen von URLs abgeschlossen haben, wählen Sie in der unteren rechten Ecke des Bildschirms **Speichern**aus.
    
## <a name="a-few-things-to-keep-in-mind"></a>Einige Dinge, die Sie beachten sollten

Achten Sie beim Hinzufügen von URLs zu Ihrer Liste darauf, Folgendes zu beachten: 

- Fügen Sie am Ende der URL keinen **/** Schrägstrich () ein. Geben Sie beispielsweise anstatt Eingabe `https://www.contoso.com/`ein ein `https://www.contoso.com`.
    
- Sie können eine nur-Domänen-URL angeben ( `contoso.com` wie `tailspintoys.com`oder). Dadurch wird das Klicken auf eine URL blockiert, die die Domäne enthält.

- Sie können eine Unterdomäne (like `toys.contoso.com*`) angeben, ohne eine vollständige Domäne ( `contoso.com`like) zu blockieren. Dadurch wird das Klicken auf eine URL blockiert, die die Unterdomäne enthält, es werden jedoch keine Klicks auf eine URL blockiert, die die vollständige Domäne enthält.  
    
- Sie können bis zu drei Platzhalter Sternchen (\*) pro URL hinzufügen. In der folgenden Tabelle sind einige Beispiele aufgeführt, die Sie eingeben können und welche Auswirkungen diese Einträge haben.
    
|**Beispieleintrag**|**Funktionsweise**|
|:-----|:-----|
|`contoso.com` oder `*contoso.com*`  <br/> |Blockiert die Domäne, Unterdomänen und Pfade, wie `https://www.contoso.com`, und `https://sub.contoso.com``https://contoso.com/abc`  <br/> |
|`https://contoso.com/a`  <br/> |Blockiert eine Website `https://contoso.com/a` , jedoch keine weiteren untergeordneten Pfade wie`https://contoso.com/a/b`  <br/> |
|`https://contoso.com/a*`  <br/> |Blockiert eine Website `https://contoso.com/a` und weitere untergeordnete Pfade wie`https://contoso.com/a/b`  <br/> |
|`https://toys.contoso.com*`  <br/> |Blockiert eine Unterdomäne ("Toys" in diesem Fall), aber Sie können Klicks auf andere Domänen- `https://contoso.com` URLs `https://home.contoso.com`(wie oder) zulassen.  <br/> |
   

## <a name="how-to-define-exceptions-for-certain-users-in-an-organization"></a>Vorgehensweise definieren von Ausnahmen für bestimmte Benutzer in einer Organisation

Wenn Sie möchten, dass bestimmte Gruppen URLs anzeigen können, die möglicherweise für andere Personen blockiert wurden, können Sie eine Richtlinie für ATP-sichere Links angeben, die für bestimmte Empfänger gilt. Weitere Informationen finden Sie unter [Einrichten einer benutzerdefinierten Liste "URLs nicht umschreiben" unter Verwendung von ATP-Safe-Links](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md).
  

