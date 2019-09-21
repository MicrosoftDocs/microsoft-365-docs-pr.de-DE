---
title: Exemplarische Vorgehensweise Spoof Intelligence Insight
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 7/30/2018
audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 59a3ecaf-15ed-483b-b824-d98961d88bdd
ms.collection:
- M365-security-compliance
description: Erfahren Sie, wie die neue Spoof Intelligence-Einblicke funktioniert.
ms.openlocfilehash: 652dde07d615a4eef98074fb8d2b5c676f65d633
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/20/2019
ms.locfileid: "37082152"
---
# <a name="walkthrough-spoof-intelligence-insight"></a>Exemplarische Vorgehensweise: Spoof Intelligence Insight

Mithilfe der Spoof Intelligence-Einblicke können Sie schnell ermitteln, welche Absender legitimerweise nicht authentifizierte e-Mails senden. Durch die Möglichkeit, gefälschte Nachrichten zu senden, können Sie das Risiko verringern, dass falsch positive Ergebnisse an Ihre Benutzer gesendet werden.
  
Darüber hinaus können Sie auch Spoof Intelligence-Überwachung verwenden und zugelassene Domänen Paare verwalten, um eine zusätzliche Sicherheitsebene bereitzustellen und zu verhindern, dass unsichere Nachrichten in Ihrer Organisation eingehen.
  
Sie können die Spoof Intelligence-Einblicke im &amp; Security Compliance Center verwenden, wenn Ihr Arbeits-oder Schulkonto Office 365 globaler Administrator, Sicherheitsadministrator oder Berechtigungen für Sicherheits Leser erteilt wurde. Weitere Informationen finden Sie unter [Permissions in the Office 365 &amp; Security Compliance Center](permissions-in-the-security-and-compliance-center.md).
  
Wenn Sie noch keine [Erfahrung mit Berichten und Einblicken im &amp; Office 365 Security Compliance Center](reports-and-insights-in-security-and-compliance.md)haben, kann es hilfreich sein, zu sehen, wie Sie einfach von einem Dashboard zu einer Einblicke und empfohlenen Aktionen navigieren können.
  
Sie können die Einblicke in Spoof Intelligence aus mehreren Dashboards im Security &amp; Compliance Center anzeigen. Unabhängig davon, für welches Dashboard Sie sich interessieren, bietet die Insight dieselben Details und ermöglicht Ihnen, schnell dieselben Aufgaben auszuführen.
  
Dies ist eine von mehreren exemplarischen Vorgehens &amp; weisen für das Security Compliance Center. Informationen zum Navigieren in Berichten und Einblicken finden Sie unter Exemplarische Vorgehensweisen im Abschnitt "Verwandte Themen".
  
## <a name="getting-to-the-spoof-intelligence-insight-in-the-security-amp-compliance-center"></a>Einblicke in Spoof Intelligence im Security &amp; Compliance Center

1. Um zu beginnen, müssen Sie [zum Security &amp; Compliance Center wechseln](../../compliance/go-to-the-securitycompliance-center.md).
    
2. Wechseln Sie im &amp; Security Compliance Center zu **Threat Management** \> **Dashboard.**
    
3. Suchen Sie in der Zeile **Insights** nach der Spoof Intelligence-Einblicke. Wenn Sie Spoof Intelligence aktiviert haben, werden die Einblicke mit dem Namen **gefälschte Domänen bezeichnet, bei denen die Authentifizierung der letzten 30 Tage nicht erfolgreich**war. Wenn Sie den spoofschutz nicht aktiviert haben, werden Sie von der Einblicke dazu aufgefordert, dies mithilfe des Titels **Spoof-Schutz aktivieren**zu tun. 
    
## <a name="about-the-insight-on-the-dashboard"></a>Informationen zur Einblicke in das Dashboard

Die Einblicke in das Dashboard zeigt Ihnen Informationen wie diese.
  
![Screenshot von Spoof Intelligence Insight](../media/28aeabac-c1a1-4d16-9fbe-14996f742a9a.png)
  
Diese Einblicke umfasst zwei Modi:
  
 **Insight-Modus**. Wenn Sie eine Spoof-Richtlinie aktiviert haben, zeigt Ihnen die Einsicht, wie viele e-Mails in den letzten 30 Tagen von unseren Spoof Intelligence-Funktionen betroffen waren. 
  
 **Was ist, wenn-Modus**. Wenn Sie keine Spoof-Richtlinie aktiviert haben, zeigt Ihnen die Einsicht, wie viele e-Mails von unseren Spoof Intelligence-Funktionen in den letzten 30 Tagen betroffen *wären* . 
  
In beiden Fällen werden die in der Insight angezeigten gefälschten Domänen in zwei Kategorien unterteilt. verdächtige Domänen Paare und nicht verdächtige Domänen Paare. Diese Kategorien werden weiter in drei verschiedene Buckets unterteilt, die Sie überprüfen können. 
  
Ein *Domänenpaar* ist eine Kombination aus der "von:"-Adresse und der sendenden Infrastruktur. 
  
- Die "von"-Adresse ist die Adresse, die von Ihrer e-Mail-Anwendung als Absenderadresse angezeigt wird. Diese Adresse identifiziert den Autor der E-Mail. Das heißt, das Postfach der Person oder des Systems, das sich für das Schreiben der Nachricht verantwortlich zeichnet. Dies wird manchmal auch als 5322.From-Adresse bezeichnet.
    
- Die sendende Infrastruktur oder der Absender ist die Organisationsdomäne des PTR-Eintrags der sendenden IP-Adresse. Wenn die sendende IP-Adresse keinen PTR-Eintrag hat, wird der Absender von der sendenden IP mit der Subnetzmaske 255.255.255.0 in der CIDR-Notation (/24) identifiziert. Wenn die IP-Adresse beispielsweise 192.168.100.100 lautet, lautet die vollständige IP-Adresse des Absenders 192.168.100.100/24.
    
 Zu den **verdächtigen Domänen Paaren** gehören: 
  
- **Spoof mit hoher Vertrauens**Würdigkeit. Office 365 erhielt starke Signale, dass diese Domänen verdächtig sind, basierend auf den Verlaufs Sende Mustern und dem Reputations Ergebnis der Domänen. Office 365 ist sehr zuversichtlich, dass die Domänen Spoofing sind und dass von diesen Domänen gesendete Nachrichten mit geringerer Wahrscheinlichkeit Legitimität aufweisen. 
    
- **Gemäßigte Vertrauens Parodie**. Office 365 erhalten moderat signalisiert, dass diese Domänen verdächtig sind, basierend auf Verlaufs Sende Mustern und dem Reputations Ergebnis der Domänen. Office 365 ist gemäßigt zuversichtlich, dass die Domänen Spoofing sind und dass von diesen Domänen gesendete Nachrichten legitim sind. Dieser Bucket hat eine größere Chance, falsch positive Ergebnisse (fps) zu enthalten als den Spoofing-Bucket mit hoher Vertrauenswürdigkeit. 
    
 **Nicht-verdächtige Domänen Paare** umfassen die **geretteten spoofs**. "Gerettete spoofs" sind Domänen, bei denen die explizite Authentifizierungsüberprüfung ( [SPF](https://docs.microsoft.com/office365/SecurityCompliance/how-office-365-uses-spf-to-prevent-spoofing), [DKIM](https://docs.microsoft.com/office365/SecurityCompliance/use-dkim-to-validate-outbound-email), [DMARC](https://docs.microsoft.com/office365/SecurityCompliance/use-dmarc-to-validate-email)) fehlgeschlagen ist, aber unsere erweiterten Authentifizierungsprüfungen bestanden haben. Aus diesem Grund haben Office 365 die e-Mails in Ihrem Namen gerettet, und es wurde keine Antispoofing-Aktion auf die e-Mail angewendet. 
  
## <a name="view-detailed-information-about-suspicious-domain-pairs-from-the-spoof-intelligence-insight"></a>Anzeigen detaillierter Informationen zu verdächtigen Domänen Paaren aus dem Spoof Intelligence-Insight

1. Klicken Sie auf der Spoof Intelligence-Einblicke auf eines der Domänen Paare (hoch, moderat oder gerettet).
  
Die Seite **Spoof Intelligence Insight** wird angezeigt und zeigt eine Liste von Absendern an, die nicht authentifizierte e-Mails an Ihre Organisation senden. Die Informationen auf dieser Seite helfen Ihnen zu bestimmen, ob gefälschte Nachrichten autorisiert sind oder nicht, oder ob Sie weitere Aktionen ausführen müssen. Sie können die Informationen nach Nachrichtenanzahl, dem Datum, an dem die Spoof zuletzt erkannt wurde, und vieles mehr sortieren. (Klicken Sie beispielsweise auf Spaltenüberschriften wie **Nachrichtenanzahl** oder **zuletzt gesehen**.) 
    
2. Wählen Sie ein Element in der Tabelle aus, um einen Detailbereich mit umfangreichen Informationen über das Domänenpaar zu öffnen, einschließlich der Gründe für diese Erfassung, was Sie tun müssen, eine Domänen Zusammenfassung, Whois-Daten über den Absender und ähnliche e-Mails, die wir in Ihrem Mandanten vom gleichen Absender gesehen haben. Von hier aus können Sie auch das Domänenpaar aus der Liste sicherer Absender von **AllowedToSpoof** hinzufügen oder entfernen. 
  
![Screenshot einer Domäne im Detailbereich "Spoof Intelligence Insight"](../media/03ad3e6e-2010-4e8e-b92e-accc8bbebb79.png)
  
## <a name="add-or-remove-a-domain-from-the-allowedtospoof-safe-sender-list"></a>Hinzufügen oder Entfernen einer Domäne aus der Liste sicherer Absender von AllowedToSpoof

Sie können eine Domäne aus der Liste sicherer Absender von AllowedToSpoof hinzufügen oder entfernen, während Sie das Domänenpaar im Detailbereich der Spoof Intelligence-Einblicke überprüfen. Legen Sie die Umschaltfläche einfach entsprechend fest.
  
Dadurch wird die eindeutige Kombination aus Domänen Paaren der gefälschten Domäne und der sendenden Infrastruktur geändert, und es wird keine Abdeckung für die gesamte Spoofing-Domäne oder die sendende Infrastruktur isoliert bereitgestellt. Wenn Sie beispielsweise das folgende Domänenpaar zur Absender Zulassungsliste "AllowedToSpoof" hinzufügen: die *spoofed-Domäne* "gmail.com" und die *Sendeinfrastruktur* "TMS *. MX.com",* dann dürfen nur e-Mails von diesem Domänenpaar Spoofing durchführen. Andere Absender, die versuchen, "gmail.com" und andere Domänen zu spoofen, die "TMS.MX.com" Spoof versuchen, werden weiterhin durch Spoof Intelligence geschützt. 
  
## <a name="related-topics"></a>Verwandte Themen

[Weitere Informationen zu Spoofing Intelligence](learn-about-spoof-intelligence.md)
  
[Antispoofingschutz in Office 365](anti-spoofing-protection.md)
  
[Exemplarische Vorgehensweise – Vom Dashboard zum Einblick](from-a-dashboard-to-an-insight.md)
  
[Exemplarische Vorgehensweise – Vom detaillierten Bericht zum Einblick](from-a-detailed-report-to-an-insight.md)
  
[Exemplarische Vorgehensweise – Vom Einblick zum detaillierten Bericht](from-an-insight-to-a-detailed-report.md)
  

