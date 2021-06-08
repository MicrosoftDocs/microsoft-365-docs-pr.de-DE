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
ms.openlocfilehash: d4cedf420dd605d04328b7f1edeabbd4e1bb5ac7
ms.sourcegitcommit: e1e275eb88153bafddf93327adf8f82318913a8d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2021
ms.locfileid: "52809165"
---
# <a name="scheduler-for-microsoft-365-faqs"></a>Scheduler für Microsoft 365 FAQs

**Frage:** Wie lässt sich Scheduler in andere Cortana-Features integrieren, z. B. *Cortana für Windows,* *tägliche Briefing-E-Mail* und *Meine E-Mails wiedergeben?*</br>
Scheduler ist ein unabhängiger Dienst von anderen Cortana-Features. Andere Cortana-Features können auf Mandantenebene deaktiviert werden, und scheduler kann weiterhin mithilfe der cortana@yourdomain.com E-Mail-Adresse aktiviert werden. Derzeit können Benutzer nur per E-Mail mit Scheduler interagieren.

**Frage:** Funktioniert dies nur mit Outlook? Werden andere E-Mail-Produkte unterstützt?</br>
Solange Sie über eine Lizenz verfügen, außer den drei oben genannten Anforderungen, können Benutzer cortana@yourdomain.com von jedem E-Mail-Client auf jedem Gerät per E-Mail senden.

**Frage:** Können Sich Kontakte in einer persönlichen Kontaktliste auf Outlook und GAL oder einem anderen Unternehmen befinden?</br>
Besprechungsteilnehmer können alle Personen sein, die eine E-Mail-Adresse innerhalb oder außerhalb des Unternehmens haben. Leider kann Scheduler Namen nicht automatisch in E-Mail-Adressen/Aliase übersetzen, indem er sie heute in der GAL nachschlägt.

**Frage:** Kann ich Scheduler mit meiner installierten (lokalen) Version von Outlook verwenden?</br>
Der Scheduler erfordert Exchange Online. Funktioniert nicht mit Exchange Server (lokal). Funktioniert mit jedem E-Mail-Client, Outlook Desktop, OWA, iOS, Android, Gmail usw.

**Frage:** Muss Outlook im Hintergrund geöffnet sein?</br>
Outlook muss nicht im Hintergrund geöffnet sein. Sie müssen cortana lediglich eine E-Mail senden und sich darauf verlassen, dass sie den Großteil der Arbeit erledigt.

## <a name="frequently-asked-trust-and-privacy-questions"></a>Häufig gestellte Vertrauens- und Datenschutzfragen

**Frage:** Wie funktioniert Scheduler?</br>
Scheduler verwendet Planungsintelligenz (SCHEDULING Intelligence, KI), die mit menschlichen Assistenten erweitert wird. Wenn KI-Modelle Unterstützung in der natürlichen Sprache der Kommunikation mit Cortana generieren, eskaliert die Besprechungsanfrage zur Überprüfung und Zum Abschluss an einen Menschen.

**Frage:** Wer sind die Menschen, die eskalierte Anforderungen überprüfen? </br>
Planerassistenten sind Microsoft Supplier Security and Privacy Assurance (SSPA) für persönliche und streng vertrauliche Informationen zertifiziert. 

**Frage:** Was können SSPA-Assistenten anzeigen?</br>
Der Planer und die SSPA-Assistenten können die E-Mails anzeigen, die an Cortana adressiert sind. In einem Thread-E-Mail-Austausch werden nur die E-Mails verarbeitet, die Cortanas E-Mail-Adresse enthalten, nicht die vorherigen E-Mails im Thread, bevor Cortana hinzugefügt wurde.   

**Frage:** Werden Kundendaten in den Daten Flow des Planers aufbewahrt? </br>
Scheduler speichert alle Kundeninhalte innerhalb der Mandantengrenzen und speichert Daten gemäß dsgvo-Richtlinien, Microsoft 365 Trust & Datenschutzrichtlinien und Mandanten-E-Mail-Richtlinien.

**Frage:** Wie verarbeitet Scheduler die Frei/Gebucht-Daten interner Teilnehmer? </br>
Die Automatisierung des Schedulers verwendet den *findMeetingTimes-Dienst,* um Zeiten zu identifizieren, die für Teilnehmer und den Organisator gegenseitig verfügbar sind. Dieser Dienst unterstützt andere Outlook Wie z. *B. vorgeschlagene Uhrzeiten* im Outlook Besprechungsformular. Frei/Gebucht-Teilnehmerinformationen werden nicht explizit als Frei/Gebucht-Blöcke genutzt. 

**Frage:** Ist Scheduler DSGVO-konform? </br>
Ja.

**Frage:** Wer Zugriff auf das Cortana-Postfach hat? </br>
Der Planer verarbeitet Besprechungsanfragen und zugehörige E-Mails, die an das Cortana-Postfach Ihres Mandanten gesendet werden. Microsoft hat keinen anderen Zugriff auf das Cortana-Postfach, außer über die Lockbox-Genehmigung auf Anforderung des Mandantenadministrators.  

**Frage:** Werden Kundendaten für die Schulung von KI-Modellen verwendet?</br>
Es können keine Kundeninhalte von Scheduler für Microsoft 365 für Datenschulungen verwendet werden. Alle Kundeninhalte befinden sich im Kundenmandanten.  

**Frage:** Verarbeitet Scheduler verschlüsselte E-Mails?</br>
Nein, verschlüsselte E-Mails werden vom Scheduler-Workflow abgelehnt. 




