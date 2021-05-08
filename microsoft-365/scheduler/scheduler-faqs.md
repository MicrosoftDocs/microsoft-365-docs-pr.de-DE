---
title: Scheduler für Microsoft 365 FAQs
ms.author: v-aiyengar
author: AshaIyengar21
manager: serdars
audience: Admin
ms.topic: article
ms.service: scheduler
localization_priority: Normal
description: Scheduler für Microsoft 365 FAQs
ms.openlocfilehash: 12c2c00761b9a10fac6c62bc4d7ff5909ac935a7
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2021
ms.locfileid: "52286201"
---
# <a name="scheduler-for-microsoft-365-faqs"></a>Scheduler für Microsoft 365 FAQs

**Frage:** Wie integriert sich Scheduler in andere Cortana-Features, z. B. *Cortana für Windows,* *Tägliche Briefing-E-Mails* und *Meine E-Mails abspielen?*</br>
Scheduler ist ein unabhängiger Dienst von anderen Cortana-Features. Andere Cortana-Features können auf Mandantenebene deaktiviert werden, und Scheduler kann weiterhin mithilfe der cortana@yourdomain.com aktiviert werden. Derzeit können Benutzer nur per E-Mail mit Scheduler interagieren.

**Frage:** Funktioniert dies nur mit Outlook? Werden andere E-Mail-Produkte unterstützt?</br>
Solange Sie über eine Lizenz verfügen, können Benutzer über die drei oben genannten Anforderungen hinaus cortana@yourdomain.com E-Mail von jedem E-Mail-Client auf jedem Gerät senden.

**Frage:** Können Kontakte in einer persönlichen Kontaktliste auf Outlook gal oder einer anderen Unternehmensäquivalente enthalten sein?</br>
Besprechungsteilnehmer können jeder sein, der innerhalb oder außerhalb des Unternehmens eine E-Mail-Adresse hat. Leider kann Scheduler Namen nicht automatisch in E-Mail-Adressen/Alias übersetzen, indem er sie heute in der GAL nachschaut.

**Frage:** Kann ich Scheduler mit meiner installierten (lokalen) Version von Outlook?</br>
Scheduler erfordert Exchange Online. Funktioniert nicht mit Exchange Server (On-Prem). Funktioniert mit jedem E-Mail-Client, Outlook Desktop, OWA, iOS, Android, Gmail und so weiter.

**Frage:** Muss Outlook im Hintergrund geöffnet sein?</br>
Outlook muss nicht im Hintergrund geöffnet sein. Alles, was Sie tun müssen, ist, Cortana eine E-Mail zu senden und sich darauf zu verlassen, um den Großteil der Arbeit zu tun.

## <a name="frequently-asked-trust-and-privacy-questions"></a>Häufig gestellte Vertrauens- und Datenschutzfragen

**Frage:** Wie funktioniert Scheduler?</br>
Scheduler verwendet ai (Scheduling Intelligence) erweitert mit menschlichen Assistenten. Wenn KI-Modelle unterstützungsbedarf in der natürlichen Sprache der Kommunikation mit Cortana generieren, wird die Besprechungsanfrage zur Überprüfung und Fertigstellung an einen Menschen eskaliert.

**Frage:** Wer menschen, die eskalierte Anforderungen überprüfen? </br>
Scheduler-Assistenten sind Microsoft Supplier Security and Privacy Assurance (SSPA) für persönliche und streng vertrauliche Informationen zertifiziert. 

**Frage:** Was können SSPA-Assistenten anzeigen?</br>
Scheduler und die SSPA-Assistenten können die E-Mails anzeigen, die an Cortana adressiert sind. In einem Thread-E-Mail-Austausch werden nur die E-Mails verarbeitet, die Cortanas E-Mail-Adresse enthalten, nicht die vorherigen E-Mails im Thread, bevor Cortana hinzugefügt wurde.   

**Frage:** Werden Kundendaten in den Daten des Schedulers Flow? </br>
Der Scheduler speichert alle Kundeninhalte innerhalb der Mandantengrenzen und speichert Daten gemäß den DSGVO-Richtlinien, Microsoft 365 & Datenschutzrichtlinien und Mandanten-E-Mail-Richtlinien.

**Frage:** Wie verarbeiten Scheduler die Frei/Gebucht-Daten interner Teilnehmer? </br>
Die Automatisierung des Schedulers verwendet den *findMeetingTimes-Dienst,* um Zeiten zu identifizieren, die für Teilnehmer und den Organisator gegenseitig verfügbar sind. Dieser Dienst macht andere Outlook, z. B. vorgeschlagene *Zeiten* im Outlook Besprechungsformular. Frei/Gebucht-Teilnehmerinformationen werden nicht explizit als Frei/Gebucht-Blöcke genutzt. 

**Frage:** Ist die Scheduler-DSGVO kompatibel? </br>
Ja.

**Frage:** Wer Zugriff auf das Cortana-Postfach hat? </br>
Der Scheduler verarbeitet Besprechungsanfragen und zugeordnete E-Mails, die an das Cortana-Postfach Ihres Mandanten gesendet werden. Microsoft hat keinen anderen Zugriff auf das Cortana-Postfach, außer über die Genehmigung durch lockbox auf Anforderung des Mandantenadministrators.  

**Frage:** Werden Kundendaten für die Schulung von KI-Modellen verwendet?</br>
Es können keine Kundeninhalte von Scheduler für Microsoft 365 für Datenschulungssätze verwendet werden. Alle Kundeninhalte befinden sich im Kunden-Mandanten.  

**Frage:** Werden verschlüsselte E-Mails vom Scheduler verarbeiten?</br>
Nein, verschlüsselte E-Mails werden vom Scheduler-Workflow abgelehnt. 




