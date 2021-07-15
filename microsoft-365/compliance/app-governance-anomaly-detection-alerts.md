---
title: Untersuchen von Benachrichtigungen zur Anomalieerkennung
f1.keywords:
- NOCSH
ms.author: v-tophillips
author: v-tophillips
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection: m365-security-compliance
localization_priority: Priority
search.appverid:
- MOE150
- MET150
description: Untersuchen Sie Benachrichtigungen zur Anomalieerkennung.
ms.openlocfilehash: 6797cdcbfd2a2d3c32768a158a5f8cd0fc579d56
ms.sourcegitcommit: 41c7f7bd5c808ee5ceca0f6efe13d4e67da0262b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/14/2021
ms.locfileid: "53420244"
---
# <a name="investigate-anomaly-detection-alerts"></a>Untersuchen von Benachrichtigungen zur Anomalieerkennung

 Die Microsoft App-Governance bietet Sicherheitserkennungen und Benachrichtigungen für bösartige Aktivitäten. Der Zweck dieses Leitfadens ist es, Ihnen allgemeine und praktische Informationen zu jeder Benachrichtigung zu geben, um Sie bei Ihren Untersuchungs- und Behebungsaufgaben zu unterstützen. In diesem Leitfaden eingeschlossen sind allgemeine Informationen über die Bedingungen für das Auslösen von Benachrichtigungen. Weil Anomalie-Erkennungen von Natur aus nicht-deterministisch sind, werden sie nur ausgelöst, wenn es ein von der Norm abweichendes Verhalten gibt. Schließlich können einige Benachrichtigungen in der Vorschau sein, daher sollten Sie regelmäßig die offizielle Dokumentation auf den aktuellen Status der Benachrichtigungen überprüfen.

## <a name="mitre-attck"></a>MITRE ATT&CK

Um die Beziehung zwischen den Microsoft App-Governance-Benachrichtigungen und der bekannten MITRE ATT&CK-Matrix einfacher abbilden zu können, haben wir die Benachrichtigungen nach der entsprechenden MITRE ATT&CK-Taktik kategorisiert. Diese zusätzliche Referenz erleichtert das Verständnis der mutmaßlichen Angriffstechnik, die möglicherweise verwendet wird, wenn die Microsoft-Anwendungssicherheits- und Governance-Benachrichtigung ausgelöst wird.

Dieser Leitfaden enthält Informationen zur Untersuchung und Behebung von Microsoft App-Governance-Benachrichtigungen in den folgenden Kategorien.

- Erstzugriff
- Ausführung
- Persistenz
- Rechteausweitung
- Verteidigungsumgehung
- Zugriff auf Anmeldeinformationen
- Sammlung
- Exfiltration
- Auswirkung

## <a name="security-alert-classifications"></a>Klassifizierungen der Sicherheitsbenachrichtigungen

Nach einer ordnungsgemäßen Untersuchung können alle Microsoft App-Governance-Benachrichtigungen einem der folgenden Aktivitätstypen zugeordnet werden:

- Wahr-Positiv (True positive, TP): Eine Benachrichtigung über eine bestätigte bösartige Aktivität.
- Gutartig Wahr-Positiv (Benign true positive, B-TP): Eine Benachrichtigung über eine verdächtige, aber nicht bösartige Aktivität, wie z. B. ein Penetrationstest oder eine andere, autorisierte verdächtige Aktion.
- Falsch-Positiv (False positive, FP): Eine Benachrichtigung über eine nicht-bösartige Aktivität.

## <a name="general-investigation-steps"></a>Allgemeine Untersuchungsschritte

Verwenden Sie die folgende allgemeine Richtlinie, wenn Sie eine beliebige Art von Benachrichtigung untersuchen, um ein besseres Verständnis der potenziellen Bedrohung zu erhalten, bevor Sie die empfohlene Maßnahme anwenden.

- Überprüfen Sie den Schweregrad der App und vergleichen Sie ihn mit dem Rest der Apps in Ihrem Mandanten. Diese Überprüfung wird Ihnen beim Identifizieren der Apps in Ihrem Mandanten helfen, die ein größeres Risiko darstellen.
- Wenn Sie ein TP-Ereignis identifizieren, überprüfen Sie alle App-Aktivitäten, um ein Verständnis über die Auswirkung zu erhalten. Überprüfen Sie beispielsweise die folgenden App-Informationen:

  - Bereiche mit gewährtem Zugriff
  - Ungewohntes Verhalten  
  - IP-Adresse und Standort

## <a name="initial-access-alerts"></a>Benachrichtigungen beim Erstzugriff

In diesem Abschnitt werden Benachrichtigungen beschrieben, die darauf hinweisen, dass eine bösartige App möglicherweise versucht, in Ihrer Organisation Fuß zu fassen.  

### <a name="encoded-app-name-with-suspicious-consent-scopes"></a>Codierter App-Name mit verdächtigen Zustimmungsbereichen

**Schweregrad:** Mittel

**Beschreibung**: Diese Erkennung identifiziert OAuth-Apps mit Zeichen, beispielsweise Unicode oder codierten Zeichen, die für verdächtige Zustimmungsbereiche angefordert wurden, und die auf E-Mail-Ordner von Benutzern über die Graph-API zugegriffen haben. Diese Benachrichtigung kann auf einen Versuch hinweisen, eine bösartige App als bekannte und vertrauenswürdige App zu tarnen, damit Angreifer die Benutzer dazu verleiten können, der bösartigen App zuzustimmen.

**TP oder FP?**

- **TP**: Wenn Sie bestätigen können, dass die OAuth-App den Anzeigenamen mit verdächtigen Bereichen codiert hat, die von einer unbekannten Quelle geliefert wurden, dann wird ein Wahr-Positiv angezeigt.  

  **Empfohlene Aktion**: Überprüfen Sie die Berechtigungsebene, welche diese App angefordert hat, und welche Benutzer den Zugriff gewährten. Sie können basierend auf Ihrer Untersuchung entscheiden, den Zugriff auf diese App zu verbieten.

  Um den Zugriff auf die App zu verbieten, wählen Sie auf der Seite der OAuth-Apps in der Zeile, in der die zu verbietende App erscheint, das Verbotssymbol. Sie können entscheiden, ob Sie die Benutzer informieren wollen, dass die von ihnen installierte und autorisierte App verboten wurde. Die Benachrichtigung teilt den Benutzern mit, dass die App deaktiviert wird, und dass sie keinen Zugriff auf die verbundene App haben werden. Wenn die Benutzer dies nicht erfahren sollen, deaktivieren Sie im Dialogfeld die Option „Benutzer benachrichtigen, die Zugriff auf diese gesperrte App erteilt haben“. Es wird empfohlen, dass Sie den App-Benutzern mitteilen, dass die Verwendung ihrer App demnächst verboten wird.

- **FP**: Wenn Sie bestätigen werden, dass die App einen codierten Namen hat, aber eine legitime geschäftliche Verwendung in der Organisation besitzt.

  **Empfohlene Aktion**: Schließen Sie die Benachrichtigung.

#### <a name="understand-the-scope-of-the-breach"></a>Verständnis des Umfangs der Sicherheitsverletzung

Folgen Sie dem Lernprogramm zur [Untersuchung riskanter OAuth-Apps](/cloud-app-security/investigate-risky-oauth).

### <a name="oauth-app-with-read-scopes-have-suspicious-reply-url"></a>OAuth-Apps mit Lesebereichen haben eine verdächtige Antwort-URL

**Schweregrad**: Mittel

**Beschreibung**: Diese Erkennung identifiziert eine OAuth-App mit nur Lesebereichen wie User.Read, People.Read, Contacts.Read, Mail.Read, Contacts.Read.Shared, umgeleitet über die Graph-API an eine verdächtige Antwort-URL. Diese Aktivität soll darauf hinweisen, dass eine bösartige App mit weniger privilegierten Berechtigungen (z. B. Lesebereiche) ausgenutzt werden könnte, um das Benutzerkonto auszuspähen.

**TP oder FP?**

- **TP**: Wenn Sie bestätigen können, dass die OAuth-App mit Lesebereich von einer unbekannten Quelle geliefert wird und auf eine verdächtige URL umleitet, dann wird ein TP angezeigt.

  **Empfohlene Aktion**: Überprüfen Sie die Antwort-URL und die Bereiche, die von der App angeforderte werden. Sie können basierend auf Ihrer Untersuchung entscheiden, den Zugriff auf diese App zu verbieten. Überprüfen Sie die Berechtigungsebene, welche diese App angefordert hat, und welche Benutzer den Zugriff gewährt haben.

  Um den Zugriff auf die App zu verbieten, wählen Sie auf der Seite der OAuth-Apps in der Zeile, in der die zu verbietende App erscheint, das Verbotssymbol. Sie können entscheiden, ob Sie die Benutzer informieren wollen, dass die von ihnen installierte und autorisierte App verboten wurde. Die Benachrichtigung teilt den Benutzern mit, dass die App deaktiviert wird, und dass sie keinen Zugriff auf die verbundene App haben werden. Wenn die Benutzer dies nicht erfahren sollen, deaktivieren Sie im Dialogfeld die Option „Benutzer benachrichtigen, die Zugriff auf diese gesperrte App erteilt haben“. Es wird empfohlen, dass Sie den App-Benutzern mitteilen, dass die Verwendung ihrer App demnächst verboten wird.

- **B-TP**: Wenn Sie nach der Untersuchung bestätigen können, dass die App eine legitime geschäftliche Verwendung in der Organisation besitzt.

  **Empfohlene Aktion**: Schließen Sie die Benachrichtigung.

#### <a name="understand-the-scope-of-the-breach"></a>Verständnis des Umfangs der Sicherheitsverletzung 

1. Überprüfen Sie alle von dieser App ausgeführten Aktivitäten.
1. Wenn Sie vermuten, dass eine App verdächtig ist, empfehlen wir Ihnen, den Namen und die Antwort-URL der App in verschiedenen App-Stores zu untersuchen. Wenn Sie App-Stores überprüfen, konzentrieren Sie sich auf die folgenden Typen von Apps:
   - Apps, die kürzlich erstellt wurden.
   - Apps mit einer verdächtigen Antwort-URL
   - Apps, die in der letzten Zeit nicht aktualisiert wurden. Fehlende Aktualisierungen können darauf hinweisen, dass die App nicht mehr unterstützt wird.
1. Wenn Sie immer noch vermuten, dass eine App verdächtig ist, können Sie den Namen der App, den Namen des Herausgebers und die Antwort-URL online recherchieren.  

## <a name="persistence-alerts"></a>Persistenz-Benachrichtigungen

In diesem Abschnitt werden Benachrichtigungen beschrieben, die darauf hinweisen, dass ein bösartiger Akteur möglicherweise versucht, in Ihrer Organisation Fuß zu fassen.

### <a name="app-with-suspicious-oauth-scope-creates-inbox-rule"></a>App mit verdächtigem OAuth-Bereich erstellt eine Posteingangsregel  

**Schweregrad**: Mittel

**MITRE-IDs**: T1137.005, T1114  

Diese Erkennung identifiziert eine OAuth-App, die verdächtigen Bereichen zugestimmt hat, eine verdächtige Posteingangsregel erstellt und dann über die Graph-API auf die E-Mail-Ordner und -Nachrichten von Benutzern zugegriffen hat. Posteingangsregeln, wie z. B. das Weiterleiten aller oder bestimmter E-Mails an ein anderes E-Mail-Konto, und Graph-Aufrufe für den Zugriff auf E-Mails und das Senden an ein anderes E-Mail-Konto, können ein Versuch sein, Informationen aus Ihrer Organisation zu exfiltrieren.  

**TP oder FP?**

- **TP**: Wenn Sie bestätigen können, dass die Posteingangsregel von einer OAuth-App einer Drittpartei erstellt wurde, mit verdächtigen Bereichen, die von einer unbekannten Quelle geliefert wurden, dann wird ein Wahr-Positiv angezeigt.

  **Empfohlene Aktion**: Deaktivieren und entfernen Sie die App, setzen Sie das Kennwort zurück, und entfernen Sie die Posteingangsregel.

  Folgen Sie dem Lernprogramm zum „Zurücksetzen eines Passworts mit Azure Active Directory“ und folgen Sie dem Lernprogramm zum „Entfernen der Posteingangsregel“.

- **FP**: Wenn Sie bestätigen können, dass die App aus legitimen Gründen eine Posteingangsregel für ein neues oder persönliches externes E-Mail-Konto erstellt hat.

  **Empfohlene Aktion**: Schließen Sie die Benachrichtigung.

#### <a name="understand-the-scope-of-the-breach"></a>Verständnis des Umfangs der Sicherheitsverletzung

1. Überprüfen Sie alle von dieser App ausgeführten Aktivitäten.
1. Überprüfen Sie die Bereiche, die von der App gewährt wurden.
1. Überprüfen Sie die Aktion und die Bedingung der Posteingangsregel, die von der App erstellt wurde.

## <a name="collection-alerts"></a>Sammlungsbenachrichtigungen

In diesem Abschnitt werden Benachrichtigungen beschrieben, die darauf hinweisen, dass ein bösartiger Akteur möglicherweise versucht, in Ihrer Organisation die für sein Ziel interessanten Daten zu sammeln.

### <a name="app-made-anomalous-graph-calls-to-read-e-mail"></a>App hat anomale Graph-Aufrufe gemacht, um E-Mails zu lesen

**Schweregrad**: Mittel

**MITRE-ID**: T1114

Diese Erkennung identifiziert, wenn die Branchen (Line of Business, LOB)-OAuth-App über die Graph-API auf ein ungewöhnliches und hohes Volumen von E-Mail-Ordnern und -Nachrichten des Benutzers zugreift, was auf eine versuchte Sicherheitsverletzung in Ihrer Organisation hinweisen kann.

**TP oder FP?**

- **TP**: Wenn Sie bestätigen können, dass die ungewöhnliche Graph-Aktivität von der Branchen (Line of Business, LOB)-OAuth-App durchgeführt wurde, dann wird ein Wahr-Positiv angezeigt.

  **Empfohlene Aktionen**: Deaktivieren Sie die App vorübergehend, setzen Sie das Kennwort zurück, und aktivieren Sie dann die App erneut.

  Folgen Sie dem Lernprogramm zum „Zurücksetzen eines Kennworts mit dem Azure Active Directory“.

- **FP**: Wenn Sie bestätigen können, dass die App für ein ungewöhnlich hohes Volumen an Graph-Aufrufen vorgesehen ist.

  **Empfohlene Aktion**: Schließen Sie die Benachrichtigung.

#### <a name="understand-the-scope-of-the-breach"></a>Verständnis des Umfangs der Sicherheitsverletzung

1. Überprüfen Sie das Aktivitätsprotokoll auf Ereignisse, die von dieser App ausgeführt wurden, um ein besseres Verständnis für andere Aktivitäten von Graph zu erhalten, die E-Mails lesen und versuchen, vertrauliche E-Mail-Informationen der Benutzer zu sammeln.
1. Überwachen Sie, ob der App unerwartete Anmeldeinformationen hinzugefügt werden.
