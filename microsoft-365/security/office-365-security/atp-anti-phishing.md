---
title: ATP-Antiphishingfunktionen in Office 365
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyp
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 5076d0f6-7a59-4d6c-bd07-ba95033f0682
ms.collection:
- M365-security-compliance
description: Das ATP-Anti-Phishing ist Teil Office 365 Advanced Threat Protection. ATP Anti-Phishing wendet eine Reihe von Modellen des maschinellen Lernens zusammen mit Algorithmen zur Erkennung von Imitationen auf eingehende Nachrichten an, um den Schutz von Produkten und Spear-Phishing-Angriffen zu gewährleisten. Alle Nachrichten unterliegeneiner umfassenden Gruppe von maschinellen Lernmodellen, die zum Erkennen von Phishing-Nachrichten ausgebildet wurden, sowie einer Reihe von erweiterten Algorithmen, die zum Schutz gegen verschiedene Benutzer-und Domänen Identitätswechsel Angriffe verwendet werden.
ms.openlocfilehash: eca12a1f75057aee94762a8a5eef0cceffe327d3
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2020
ms.locfileid: "41599832"
---
# <a name="atp-anti-phishing-capabilities-in-office-365"></a>ATP-Antiphishingfunktionen in Office 365

Das ATP-Anti-Phishing ist Teil [Office 365 Advanced Threat Protection](office-365-atp.md). ATP Anti-Phishing wendet eine Reihe von Modellen des maschinellen Lernens zusammen mit Algorithmen zur Erkennung von Imitationen auf eingehende Nachrichten an, um den Schutz von Produkten und Spear-Phishing-Angriffen zu gewährleisten. Alle Nachrichten unterliegeneiner umfassenden Gruppe von maschinellen Lernmodellen, die zum Erkennen von Phishing-Nachrichten ausgebildet wurden, sowie einer Reihe von erweiterten Algorithmen, die zum Schutz gegen verschiedene Benutzer-und Domänen Identitätswechsel Angriffe verwendet werden. Das ATP-Anti-Phishing schützt Ihre Organisation gemäß den Policies, die von Ihren Office 365 globalen oder Sicherheitsadministratoren festgelegt werden.
  
Weitere Informationen finden Sie unter [Einrichten von Anti-Phishing-Richtlinien in Office 365](set-up-anti-phishing-policies.md).
  
> [!NOTE]
> Das ATP-Anti-Phishing steht nur in Advanced Threat Protection zur Verfügung, das in Abonnements enthalten ist, wie [Microsoft 365 Enterprise](https://www.microsoft.com/microsoft-365/enterprise/home), [Microsoft 365 Business](https://www.microsoft.com/microsoft-365/business), Office 365 Enterprise E5, Office 365 Education A5 usw. Wenn Ihre Organisation über ein Office 365es Abonnement verfügt, das nicht Office 365 ATP umfasst, können Sie ATP als Add-on möglicherweise erwerben. Weitere Informationen finden Sie unter [Office 365 Advanced Threat Protection-Pläne und-Preise](https://products.office.com/exchange/advance-threat-protection) und der [Office 365 Advanced Threat Protection-Dienstbeschreibung](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description).

## <a name="how-atp-anti-phishing-works"></a>Funktionsweise von ATP-Anti-Phishing

ATP-Anti-Phishing überprüft eingehende Nachrichten auf Indikatoren, bei denen die Nachricht möglicherweise als Phishing bezeichnet wird. Wenn ein Benutzer von einer ATP-Richtlinie abgedeckt wird (sichere Anlagen, sichere Links oder Anti-Phishing), wird die eingehende Nachricht von mehreren maschinellen Lernmodellen ausgewertet, die die Nachricht analysieren, um festzustellen, ob die Richtlinie für die Nachricht gilt und die entsprechende Aktion basierend auf der konfigurierten Richtlinie übernommen.
  
Das ATP-Anti-Phishing ermöglicht Office 365 globalen Administratoren oder Sicherheitsadministratoren, Richtlinien zu definieren, die Schutz vor Phishing-Angriffen bieten, die einen Identitätswechsel von Benutzern oder Domänen einschließen. (oder beides). Office 365 globale Administratoren oder Sicherheitsadministratoren definieren innerhalb der Richtlinie, welche Benutzer und Domänen vor Identitätswechsel-Angriffen geschützt werden sollen, indem Sie entweder eine feste Liste von Benutzern oder Domänen oder mithilfe der Post Fach Intelligenz verwenden. Mailbox Intelligence ist ein erweitertes Verständnis der e-Mail-Gewohnheiten und persönlichen Kontakte eines Benutzers. ATP erlernt, wie jeder einzelne Benutzer mit anderen Benutzern innerhalb und außerhalb der Organisation kommuniziert und eine Zuordnung dieser Beziehungen aufbaut. Diese Zuordnung ermöglicht es ATP, mehr Details darüber zu erfahren, wie Sie sicherstellen können, dass die richtigen Nachrichten als Identitätswechsel identifiziert werden.
  
ATP-Anti-Phishing-Policies können auf eine bestimmte Gruppe von Personen oder Gruppen in Ihrer Organisation oder auf eine ganze Domäne oder alle benutzerdefinierten Domänen angewendet werden. Weitere Informationen finden Sie unter [Einrichten von Anti-Phishing-Richtlinien in Office 365](set-up-anti-phishing-policies.md).
  
## <a name="how-to-get-atp-anti-phishing"></a>So erhalten Sie ATP-Anti-Phishing

Funktionen für die Anti-Phishing-Funktion von ATP sind Teil des [erweiterten Bedrohungsschutzes](office-365-atp.md); bei der Definition von Anti-Phishing-Richtlinien gilt allerdings der ATP-Schutz gegen Phishing. (Ein Beispiel ist eine Identitätswechsel basierte Richtlinie.) Weitere Informationen finden Sie unter [Einrichten von Anti-Phishing-Richtlinien in Office 365](set-up-anti-phishing-policies.md).
  
## <a name="how-to-know-if-atp-anti-phishing-is-in-place"></a>So erfahren Sie, ob das ATP-Anti-Phishing vorhanden ist

ATP-Anti-Phishing-Richtlinien müssen definiert sein, damit der Schutz wirksam ist. Überprüfen Sie zunächst, ob der Schutz in Kraft ist.

Darüber hinaus stehen Berichte zur Verfügung, um zu zeigen, wie der Dienst für Ihre Organisation funktioniert. Weitere Informationen finden Sie unter [Anzeigen von Berichten für Office 365 Advanced Threat Protection](view-reports-for-atp.md).

Damit die Lernmodelle für ATP-antiphishingmaschinen für einen bestimmten Benutzer aktiv sein müssen, muss dieser Benutzer Teil eines definierten [ATP-Safe-Attachments](atp-safe-attachments.md), [ATP-Sicherheits Links](atp-safe-links.md)oder einer ATP-Anti-Phishing-Richtlinie sein. 

In der folgenden Tabelle werden einige Beispielszenarien beschrieben. In jedem dieser Beispiele verwendet die Organisation Office 365 Enterprise E5, wozu auch Advanced Threat Protection gehört.
  
|**Beispielszenario**|**Gilt in diesem Fall das ATP-Anti-Phishing?**|
|:-----|:-----|
|Pat es Organisation hat Office 365 Enterprise E5, aber es wurden keine Richtlinien für ATP-sichere Anlagen, ATP-sichere Links oder ATP Advanced Phishing definiert.|Nein. Obwohl das Feature verfügbar ist, muss mindestens eine ATP-Richtlinie definiert sein, damit die Lernmodelle für ATP-Computer funktionieren. Für den Identitätswechsel muss auch eine ATP-Anti-Phishing-Richtlinie vorhanden sein.|
|Lee ist ein Mitarbeiter in der Vertriebsabteilung bei Contoso. Die Organisation von Lee hat eine ATP-Richtlinie zum Schutz vor Phishing, die nur für Mitarbeiter von Finanzmitteln gilt.|Nein. In diesem Fall würde ATP-AntiPhishing (Computermodelle und Identitätswechsel Schutz) für die Finanzierung von Mitarbeitern gelten, aber andere Mitarbeiter, einschließlich der Vertriebsabteilung, würden dies nicht tun.|
|Gestern richtete ein Office 365 Administrator bei Jeans Organisation eine ATP-Anti-Phishing-Richtlinie ein, die für alle Mitarbeiter gilt. Anfang heute hat Jean eine e-Mail-Nachricht erhalten, die einen Identitätswechsel enthält, der von der Richtlinie abgedeckt wird.|Ja. In diesem Beispiel hat Jean eine Lizenz für Advanced Threat Protection und eine ATP-Anti-Phishing-Richtlinie, die Jean enthält, wurde definiert. In der Regel dauert es etwa 30 Minuten, bis eine neue Richtlinie in den Rechenzentren wirksam wird. Da ein Tag in diesem Fall vergangen ist, sollte die Richtlinie wirksam sein.|

## <a name="related-topics"></a>Verwandte Themen

[Office 365 Advanced Threat Protection](office-365-atp.md)
  
[Antiphishingschutz in Office 365](anti-phishing-protection.md)
  
[Einrichten von Anti-Phishing-Richtlinien in Office 365](set-up-anti-phishing-policies.md)
  
[ATP-sichere Links in Office 365](atp-safe-links.md)
  
[Einrichten von Richtlinien für ATP-sichere Links in Office 365](set-up-atp-safe-links-policies.md)
  
[Sichere ATP-Anhänge in Office 365](atp-safe-attachments.md)
  
[Einrichten von Richtlinien für ATP-sichere Anlagen in Office 365](set-up-atp-safe-attachments-policies.md)
  
[Anzeigen der Berichte zu Advanced Threat Protection](view-reports-for-atp.md)
