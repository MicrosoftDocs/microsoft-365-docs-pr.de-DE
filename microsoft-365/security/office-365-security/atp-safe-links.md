---
title: ATP-sichere Links
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
audience: Admin
ms.topic: overview
f1_keywords:
- "197503"
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
search.appverid:
- MET150
- MOE150
- ZVO160
- ZXL160
- ZPP160
- ZWD160
ms.assetid: dd6a1fef-ec4a-4cf4-a25a-bb591c5811e3
description: In diesem Artikel erfahren Sie, wie Sie sichere Links zum Schutz Ihrer Organisation vor Phishing und anderen Angriffen verwenden.
ms.openlocfilehash: 5baf18c249d67551c7ae1eeb643a401ea16d2b6c
ms.sourcegitcommit: fa8e488936a36e4b56e1252cb4061b5bd6c0eafc
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/13/2020
ms.locfileid: "46656981"
---
# <a name="atp-safe-links"></a>ATP-sichere Links

## <a name="overview-of-office-365-atp-safe-links"></a>Übersicht über Office 365 sichere ATP-Links

> [!IMPORTANT]
> Dieser Artikel richtet sich an Geschäftskunden, die über [Office 365 Advanced Threat Protection](office-365-atp.md) verfügen. Wenn Sie Outlook.com, Microsoft 365-Familie oder Microsoft 365 Personal verwenden und nach Informationen zu sicheren Links in Outlook suchen, lesen Sie [Erweiterte Outlook.com-Sicherheit](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).

Office 365 ATP-sichere Links (Teil [Office 365 Advanced Threat Protection](office-365-atp.md)) können zum Schutz Ihrer Organisation beitragen, indem Sie die Zeit-für-Klick-Überprüfung von Webadressen (URLs) in [e-Mail-Nachrichten](how-atp-safe-links-works.md#how-atp-safe-links-works-with-urls-in-email) und [Office-Dokumenten](how-atp-safe-links-works.md#how-atp-safe-links-works-with-urls-in-office-documents)ermöglichen. Der Schutz wird durch [Richtlinien für ATP-sichere Links](set-up-atp-safe-links-policies.md) definiert, die von Ihrem Microsoft 365-Sicherheitsteam festgelegt werden.

Sobald Ihre ATP-Richtlinien für sichere Links vorhanden sind, können globale Administratoren, Sicherheitsadministratoren und Sicherheits Leser [Berichte für Advanced Threat Protection anzeigen](view-reports-for-atp.md). Die Informationen in diesen Berichten helfen dem Sicherheitsteam, weitere Schritte zum Schutz Ihrer Organisation oder Sicherheitsvorfälle in der Forschung durchführen zu können.

Wenn [ATP neue Features hinzugefügt werden](office-365-atp.md#new-features-in-office-365-atp), kann Ihr Microsoft 365-Sicherheitsteam die [Richtlinien für ATP-sichere Links](set-up-atp-safe-links-policies.md)Ihrer Organisation hinzufügen oder bearbeiten. Darüber hinaus können Sie Änderungen und Verbesserungen feststellen, beispielsweise unsere neu überarbeiteten [Warn Seiten](atp-safe-links-warning-pages.md) und das systemeigene Link Rendering in Outlook (eingeführt in Microsoft 365 apps for Enterprise Version 1809).

## <a name="how-to-get-atp-safe-links-protection"></a>So erhalten Sie den ATP-Schutz für sichere Links

**Stellen Sie zunächst sicher, dass Ihr Abonnement [Office 365 Advanced Threat Protection](office-365-atp.md) enthält.** Plan 1 oder Plan 2. Office 365 ATP ist in Abonnements enthalten, wie [Microsoft 365 Enterprise E5](https://www.microsoft.com/microsoft-365/enterprise/home), [Microsoft 365 Business Premium](https://www.microsoft.com/microsoft-365/business), Office 365 Enterprise E5, Office 365 Education A5, etc. Wenn Ihre Organisation über ein Microsoft 365-Abonnement verfügt, das nicht Office 365 ATP umfasst, können Sie ATP möglicherweise als Add-on erwerben. Weitere Informationen finden Sie in den folgenden Ressourcen: 

- [Office 365 Advanced Threat Protection-Pläne und-Preise](https://products.office.com/exchange/advance-threat-protection)

- [Office 365 Advanced Threat Protection-Dienstbeschreibung](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)

**Stellen Sie als nächstes sicher, dass Ihre ATP-Richtlinien für sichere Links definiert sind**. (Weitere Informationen finden Sie unter [Einrichten Office 365 Richtlinien für ATP-sichere Links](set-up-atp-safe-links-policies.md).) Features für ATP-sichere Links sind in folgenden Fällen aktiv:

- Richtlinien für ATP-sichere Links werden für e-Mails und für Office-Dokumente eingerichtet. (Weitere Informationen finden Sie unter [Einrichten von Richtlinien für ATP-sichere Links](set-up-atp-safe-links-policies.md).)

- Microsoft 365-Client-apps sind für die Verwendung der modernen Authentifizierung konfiguriert (Dies gilt für den Schutz von ATP-Links in Office-Dokumenten). (Weitere Informationen finden Sie unter [moderne Authentifizierung für Office 2016](https://docs.microsoft.com/office365/enterprise/modern-auth-for-office-2013-and-2016).)

- Benutzer haben sich mit Ihrem Arbeits-oder Schulkonto angemeldet. (Weitere Informationen finden Sie unter [Anmelden bei Office](https://support.microsoft.com/office/b9582171-fd1f-4284-9846-bdd72bb28426).)

- Die e-Mail-Adresse Ihrer Organisation durchläuft Exchange Online Schutz.

**Stellen Sie außerdem sicher, dass Sie über die erforderlichen Berechtigungen verfügen**. Um ATP-Richtlinien zu definieren oder zu bearbeiten, muss Ihnen eine entsprechende Rolle zugewiesen sein. In der folgenden Tabelle werden einige Beispiele beschrieben:

****

|Rolle|Wo/wie zugewiesen|
|---|---|
|globaler Administrator|Die Person, die sich zum Kauf von Microsoft 365 anmeldet, ist standardmäßig ein globaler Administrator. (Weitere Informationen finden Sie unter [Informationen zu Microsoft 365-Administratorrollen](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles) .)|
|Sicherheitsadministrator|Azure Active Directory Admin Center ( <https://aad.portal.azure.com> )|
|Exchange Online-Organisationsverwaltung|Exchange Admin Center ( <https://outlook.office365.com/ecp> ) <br>oder <br>  PowerShell-Cmdlets (siehe [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell))|
|

## <a name="how-to-make-sure-atp-safe-links-protection-is-in-place"></a>So stellen Sie sicher, dass der ATP-Schutz für sichere Links vorhanden ist

Achten Sie darauf, dass Sie als globaler Administrator oder Sicherheitsadministrator regelmäßig Ihre [Richtlinien für ATP-sichere Links](set-up-atp-safe-links-policies.md) überprüfen. Richtlinien für ATP-sichere Links bestimmen, ob der Schutz nur für Hyperlinks in e-Mail-Nachrichten oder auch für URLs in Office-Dokumenten gilt.

Nachdem Richtlinien für ATP-sichere Links vorhanden sind, kann das Sicherheitsteam Ihrer Organisation sehen, wie der Schutz für ATP-sichere Links in Ihrer Organisation funktioniert, indem Sie [Berichte für Advanced Threat Protection anzeigen](view-reports-for-atp.md).

## <a name="example-scenarios"></a>Beispielszenarien

In der folgenden Tabelle werden einige Beispielszenarien beschrieben, in denen der Schutz für ATP-sichere Links möglicherweise nicht vorhanden ist. (In allen diesen Fällen wird davon ausgegangen, dass die Organisation Office 365 Enterprise E5 hat.)

****

|Beispielszenario|Gilt der ATP-Schutz für sichere Links in diesem Fall?|
|---|---|
|Jean ist Mitglied einer Gruppe, die Richtlinien für ATP-sichere Links enthält, die URLs in e-Mail-und Office-Dokumenten umfassen. Jean öffnet eine PowerPoint-Präsentation, die von einem Benutzer gesendet wurde, und klickt dann in der Präsentation auf eine URL.|Ja. Die definierten Richtlinien für ATP-sichere Links gelten für Jeans Gruppe, Jeans e-Mail und Word-, Excel-, PowerPoint-oder Visio-Dokumente, die Jean öffnet, solange Jean mit Microsoft 365 apps for Enterprise auf Windows-, IOS-oder Android-Geräten angemeldet ist.|
|In der Organisation von Chris haben keine globalen oder Sicherheitsadministratoren noch keine Richtlinien für ATP-sichere Links definiert. Chris erhält eine e-Mail mit einer URL zu einer bösartigen Website. Chris ist nicht bewusst, dass die URL bösartig ist, und klickt auf den Link.|Nein. Die Standardrichtlinie, die URLs für alle Benutzer in der Organisation abdeckt, muss definiert werden, damit der Schutz in Kraft ist.|
|In der Organisation von Pat haben keine globalen oder Sicherheitsadministratoren noch keine Richtlinien für ATP-sichere Links definiert oder bearbeitet. Pat öffnet ein Word-Dokument und klickt auf eine URL in der Datei.|Nein. Eine Richtlinie, die Office-Dokumente umfasst, muss definiert sein, damit der Schutz vorhanden ist. Weitere Informationen finden Sie unter [Einrichten von Richtlinien für ATP-sichere Links in Office 365](set-up-atp-safe-links-policies.md).|
|Lees Organisation verfügt über eine Richtlinie für ATP-sichere Links, die `https://tailspintoys.com` als blockierte Website aufgeführt ist. Lee erhält eine e-Mail-Nachricht, die eine URL zu enthält `https://tailspintoys.com/aboutus/trythispage` . Lee klickt auf die URL.|Dies hängt davon ab, ob die gesamte Website und alle ihre Unterseiten in der Liste der blockierten URLs enthalten sind. Weitere Informationen finden Sie unter [Einrichten einer benutzerdefinierten Liste blockierter URLs mithilfe von ATP-Sicherheits Links](set-up-a-custom-blocked-urls-list-atp.md).|
|Jamie, Jean es Kollege, sendet eine e-Mail an Jean, ohne zu wissen, dass die e-Mail eine bösartige URL enthält.|Dies hängt davon ab, ob Richtlinien für ATP-sichere Links für innerhalb der Organisation gesendete e-Mails definiert sind. Weitere Informationen finden Sie unter [Einrichten von Richtlinien für ATP-sichere Links in Office 365](set-up-atp-safe-links-policies.md).|
|
