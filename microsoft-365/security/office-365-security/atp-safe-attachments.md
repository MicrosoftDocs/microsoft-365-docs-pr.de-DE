---
title: Office 365 sichere ATP-Anhänge
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
audience: Admin
ms.date: 05/17/2019
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 6e13311e-92ae-495e-a619-56d770199170
ms.collection:
- M365-security-compliance
description: Das Feature "sichere Anlagen" bietet eine Zeit-für-Klick-Überprüfung von e-Mail-Anlagen. Verwenden Sie sichere Anlagen, um Ihre Organisation vor böswilligen Dateien zu schützen, die Personen in e-Mails senden oder empfangen.
ms.openlocfilehash: 60a5a95af846fe6dbe8c2c7aa6dced9deaae1a2d
ms.sourcegitcommit: d00efe6010185559e742304b55fa2d07127268fa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2020
ms.locfileid: "43033458"
---
# <a name="office-365-atp-safe-attachments"></a>Office 365 sichere ATP-Anhänge

## <a name="overview-of-office-365-atp-safe-attachments"></a>Übersicht über Office 365 sichere ATP-Anhänge

ATP-sichere Anlagen (zusammen mit [ATP-Sicherheits Links](atp-safe-links.md)) sind Bestandteil von [Office 365 Advanced Threat Protection](office-365-atp.md) (ATP). Das Feature "ATP-sichere Anlagen" prüft, ob e-Mail-Anlagen bösartig sind, und ergreift dann Maßnahmen zum Schutz Ihrer Organisation. Das Feature "ATP-sichere Anlagen" schützt Ihre Organisation gemäß den [Richtlinien für ATP-sichere Anlagen](set-up-atp-safe-attachments-policies.md) , die von Ihren Office 365 globalen oder Sicherheitsadministratoren festgelegt werden.

ATP-Schutz kann auch auf Dateien in SharePoint Online, OneDrive für Unternehmen und Microsoft Teams erweitert werden. Weitere Informationen finden Sie unter [Office 365 Advanced Threat Protection für SharePoint, OneDrive und Microsoft Teams](atp-for-spo-odb-and-teams.md).

## <a name="how-to-get-atp-safe-attachments"></a>So erhalten Sie ATP-sichere Anlagen

Stellen Sie zunächst sicher, dass Ihr Abonnement [Advanced Threat Protection](office-365-atp.md)umfasst. ATP ist in Abonnements wie [Microsoft 365 E5](https://www.microsoft.com/microsoft-365/enterprise/home), [Microsoft 365 Business](https://www.microsoft.com/microsoft-365/business), Office 365 E5, Office 365 A5 usw. enthalten. Wenn Ihre Organisation über ein Office 365es Abonnement verfügt, das nicht Office 365 ATP umfasst, können Sie ATP als Add-on möglicherweise erwerben. Weitere Informationen finden Sie unter [Office 365 Advanced Threat Protection-Pläne und-Preise](https://products.office.com/exchange/advance-threat-protection) und der [Office 365 Advanced Threat Protection-Dienstbeschreibung](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description).

Stellen Sie als nächstes sicher, dass Ihre ATP-Richtlinien für sichere Anlagen definiert sind. (Weitere Informationen finden Sie unter [Einrichten Office 365 ATP-Richtlinien für sichere Anlagen](set-up-atp-safe-attachments-policies.md)) Features für ATP-sichere Anlagen sind in folgenden Fällen aktiv:

- Richtlinien für ATP-sichere Anlagen werden eingerichtet. (Weitere Informationen finden Sie unter [Einrichten von Richtlinien für sichere ATP-Anlagen in Office 365](set-up-atp-safe-attachments-policies.md).)

- Benutzer haben sich bei Office 365 über Ihr geschäftliches oder Schulkonto angemeldet. (Weitere Informationen finden Sie unter [Anmelden bei Office oder Office 365](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426).)

Um ATP-Richtlinien zu definieren oder zu bearbeiten, muss Ihnen eine entsprechende Rolle zugewiesen sein. In der folgenden Tabelle werden einige Beispiele beschrieben:

|Rolle|Wo/wie zugewiesen|
|---------|---------|
|Globaler Office 365-Administrator|Die Person, die sich zum Kauf Office 365 registriert, ist standardmäßig ein globaler Administrator. (Weitere Informationen finden Sie unter [Informationen zu Office 365 Administratorrollen](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles) .)|
|Sicherheitsadministrator|Azure Active Directory Admin Center ([https://aad.portal.azure.com](https://aad.portal.azure.com))|
|Exchange Online-Organisationsverwaltung|Exchange Admin Center ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp)) <br>oder <br>  PowerShell-Cmdlets (siehe [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell))|

## <a name="how-to-know-if-atp-safe-attachments-protection-is-in-place"></a>So erfahren Sie, ob der Schutz für ATP-sichere Anlagen vorhanden ist

Nachdem Sie [Ihre Richtlinien für ATP-sichere Anlagen definiert (oder überprüft)](set-up-atp-safe-attachments-policies.md)haben, ist eine gute Möglichkeit, um zu sehen, wie der Dienst funktioniert, indem Sie [Berichte für Advanced Threat Protection anzeigen](view-reports-for-atp.md).

In der folgenden Tabelle werden einige Beispielszenarien beschrieben. In allen diesen Fällen wird davon ausgegangen, dass die Organisation über ein Office 365es Abonnement verfügt, das Advanced Threat Protection umfasst.

|**Beispielszenario**|**Gilt in diesem Fall der Schutz für ATP-sichere Anlagen?**|
|:-----|:-----|
|Pat es Organisation hat Office 365 E5, aber noch keine Richtlinien für ATP-sichere Anlagen definiert.|Nein. Obwohl das Feature verfügbar ist, muss mindestens eine Richtlinie für ATP-sichere Anlagen definiert sein, damit der Schutz für ATP-sichere Anlagen vorhanden ist.|
|Lee ist ein Mitarbeiter in der Vertriebsabteilung bei Contoso. Die Organisation von Lee verfügt über eine Richtlinie für ATP-sichere Anlagen, die nur für Mitarbeiter von Finanzmitteln gilt.|Nein. In diesem Fall hätten Finanzmitarbeiter einen ATP-Schutz für sichere Anlagen, aber andere Mitarbeiter, einschließlich der Vertriebsabteilung, würden erst dann Richtlinien definieren, die diese Gruppen enthalten.|
|Gestern hat ein Office 365 Administrator bei Jeans Organisation eine Richtlinie für ATP-sichere Anlagen eingerichtet, die für alle Mitarbeiter gilt. Bereits heute hat Jean eine e-Mail-Nachricht erhalten, die eine Anlage enthält.|Ja. In diesem Beispiel verfügt Jean über eine Lizenz für Advanced Threat Protection, und eine Richtlinie für ATP-sichere Anlagen, die Jean enthält, wurde definiert. In der Regel dauert es etwa 30 Minuten, bis eine neue Richtlinie in den Rechenzentren wirksam wird. Da ein Tag in diesem Fall vergangen ist, sollte die Richtlinie wirksam sein.|
|Die Organisation von Chris hat Office 365 E5 mit ATP-Richtlinien für sichere Anlagen für alle Benutzer in der Organisation implementiert. Chris erhält eine e-Mail mit einer Anlage und leitet die Nachricht an andere Personen weiter, die sich außerhalb der Organisation befinden.|Der Schutz für ATP-sichere Anlagen ist für Nachrichten, die Chris empfängt, vorhanden. Wenn die Empfängerorganisationen auch Richtlinien für ATP-sichere Anlagen haben, wird die Nachricht, die von Chris weitergeleitet wird, beim Eintreffen der weitergeleiteten Nachricht diesen Richtlinien unterworfen.|
|In Jamies Organisation wurden Richtlinien für ATP-sichere Anlagen eingerichtet, und [ATP für SharePoint, OneDrive und Microsoft Teams](atp-for-spo-odb-and-teams.md) wurde aktiviert. Jamie geht davon aus, dass jede Datei in SharePoint Online überprüft wurde und gefahrlos geöffnet oder heruntergeladen werden kann.|Der Schutz für ATP-sichere Anlagen erfolgt entsprechend den definierten Richtlinien. Dies bedeutet jedoch nicht, dass jede einzelne Datei in SharePoint Online, OneDrive für Unternehmen oder Microsoft Teams überprüft wird. (Weitere Informationen finden Sie unter [ATP für SharePoint, OneDrive und Microsoft Teams](atp-for-spo-odb-and-teams.md).)|

## <a name="submitting-files-for-malware-analysis"></a>Übermitteln von Dateien für die Malware Analyse

- Wenn Sie eine Datei erhalten, die Sie von Microsoft analysieren möchten, besuchen Sie [Submit a file for Malware Analysis](https://aka.ms/wdsi/submit).

- Wenn Sie eine e-Mail-Nachricht (mit oder ohne Anlage) erhalten, die Sie zur Analyse an Microsoft übermitteln möchten, lesen Sie [Bericht Nachrichten und Dateien an Microsoft](report-junk-email-messages-to-microsoft.md).
