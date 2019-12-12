---
title: Einrichten von Office 365 ATP-Richtlinien für die Anti-Phishing
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
audience: ITPro
ms.topic: article
ms.date: 08/29/2019
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 5a6f2d7f-d998-4f31-b4f5-f7cbf6f38578
ms.collection:
- M365-security-compliance
description: Anti-Phishing-Schutz mit umfassendem Schutz als Bestandteil von Office 365 Advanced Threat Protection und grundlegenden Schutz in Office 365 Exchange Online Schutz helfen, Ihre Organisation vor böswilligen Identitätswechsel basierten Phishing-Angriffen zu schützen. und andere Phishing-Angriffe.
ms.openlocfilehash: c3efed345baec7b0350d089a56e931006a4724a6
ms.sourcegitcommit: 5710ce729c55d95b8b452d99ffb7ea92b5cb254a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/11/2019
ms.locfileid: "39970271"
---
# <a name="set-up-office-365-atp-anti-phishing-and-anti-phishing-policies"></a>Einrichten von Office 365 ATP-Richtlinien für Anti-Phishing und Anti-Phishing

Der [ATP-Schutz gegen Phishing](atp-anti-phishing.md), ein Teil [Office 365 Advanced Threat Protection](office-365-atp.md), kann zum Schutz Ihrer Organisation vor böswilligen Identitätswechsel basierten Phishing-Angriffen und anderen Phishing-Angriffen beitragen. Wenn Sie ein Office 365 Enterprise globaler oder Sicherheitsadministrator sind, können Sie Richtlinien für die ATP-Anti-Phishing einrichten.

Phishing-Angriffe werden in einer Vielzahl von Formen von Rohstoff basierten Angriffen bis hin zu gezieltem Speer-Phishing oder Walfang eingesetzt. Mit der wachsenden Komplexität ist es für selbst geschulte Augen schwierig, einige dieser ausgeklügelten Angriffe zu identifizieren. Glücklicherweise kann Office 365 Advanced Threat Protection hilfreich sein. Sie können eine ATP-Anti-Phishing-Richtlinie einrichten, um sicherzustellen, dass Ihre Organisation vor solchen Angriffen geschützt ist.

> [!NOTE]
> ATP-Anti-Phishing ist nur in Advanced Threat Protection (ATP) verfügbar. ATP ist in Abonnements enthalten, wie [Microsoft 365 Enterprise](https://www.microsoft.com/microsoft-365/enterprise/home), [Microsoft 365 Business](https://www.microsoft.com/microsoft-365/business), Office 365 Enterprise E5, Office 365 Education A5, etc. Wenn Ihre Organisation über ein Office 365es Abonnement verfügt, das nicht Office 365 ATP umfasst, können Sie ATP als Add-on möglicherweise erwerben. Weitere Informationen finden Sie unter [Office 365 Advanced Threat Protection-Pläne und-Preise](https://products.office.com/exchange/advance-threat-protection) und der [Office 365 Advanced Threat Protection-Dienstbeschreibung](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description). Stellen Sie sicher, dass Ihre Organisation die neueste Version von Office 365 ProPlus unter Windows verwendet, um den Vorteil des ATP-Anti-Phishing-Schutzes vollständig zu nutzen.

Eine Anti-Phishing-Richtlinie steht auch für Office 365 Exchange Online Schutz zur Verfügung, mit einem begrenzten Schutz vor Spoofing, der vor Authentifizierungs basierten und Täuschungs basierten Angriffen geschützt werden soll.

Was ist zu tun:

1. Überprüfen Sie die Voraussetzungen.

2. Erfahren Sie mehr über Ihre Anti-Phishing-und ATP-AntiPhishing-Richtlinienoptionen.

3. Richten Sie eine Anti-Phishing-Richtlinie oder eine ATP-Anti-Phishing-Richtlinie ein.

> [!IMPORTANT]
> Informationen dazu, wie mehrere Technologien angewendet werden, finden Sie unter [welche Richtlinie gilt, wenn mehrere Schutzmethoden und Erkennungs Scans in Ihren e-Mails ausgeführt](how-policies-and-protections-are-combined.md)werden.

## <a name="review-the-prerequisites"></a>Überprüfen der Voraussetzungen

- Um ATP-Richtlinien zu definieren oder zu bearbeiten, muss Ihnen eine entsprechende Rolle zugewiesen sein. In der folgenden Tabelle werden einige Beispiele beschrieben:

  |Rolle|Wo/wie zugewiesen|
  |---------|---------|
  |Globaler Office 365-Administrator|Die Person, die sich zum Kauf Office 365 registriert, ist standardmäßig ein globaler Administrator. (Weitere Informationen finden Sie unter [Informationen zu Office 365 Administratorrollen](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles) .)|
  |Sicherheitsadministrator|Azure Active Directory Admin Center ([https://aad.portal.azure.com](https://aad.portal.azure.com))|
  |Exchange Online-Organisationsverwaltung|Exchange Admin Center ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp)) <br>oder <br>  PowerShell-Cmdlets (siehe [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell))|

  Weitere Informationen zu Rollen und Berechtigungen finden Sie unter [Permissions in the Office 365 &amp; Security Compliance Center](permissions-in-the-security-and-compliance-center.md).

- Sie werden wahrscheinlich mehrere Anti-Phishing-Richtlinien für Ihre Organisation einrichten. Office 365 erzwingt diese Richtlinien in der Reihenfolge, in der Sie auf der **Seite "AntiPhishing"** und " **ATP Anti-Phishing** " im &amp; Security Compliance Center aufgeführt sind. Nachdem Sie Ihre [Richtlinienoptionen](#learn-about-atp-anti-phishing-policy-options)überprüft haben, müssen Sie sich einige Zeit nehmen, um festzustellen, wie viele Richtlinien Sie benötigen und welche Priorität Sie haben.

- Planen Sie etwa 5-15 Minuten für die Einrichtung ihrer ersten Anti-Phishing-Richtlinie.

- Erlauben Sie bis zu 30 Minuten, bis Ihre neue oder aktualisierte Richtlinie auf alle Office 365-Rechenzentren verteilt ist.

## <a name="set-up-an-anti-phishing-or-atp-anti-phishing-policy"></a>Einrichten einer Anti-Phishing-oder ATP-Anti-Phishing-Richtlinie

Jede Organisation in Office 365 verfügt über eine standardmäßige Anti-Phishing-Richtlinie, die für alle Benutzer gilt. Sie können mehrere benutzerdefinierte Anti-Phishing-Richtlinien erstellen, die Sie bestimmten Benutzern, Gruppen oder Domänen innerhalb Ihrer Organisation zur Verfügung stellen können. Die von Ihnen erstellten benutzerdefinierten Richtlinien übernehmen Vorrang vor der Standardrichtlinie. Sie können Anti-Phishing-Richtlinien im Office 365 Security &amp; Compliance Center hinzufügen, bearbeiten und löschen.

1. Wechseln Sie [https://protection.office.com](https://protection.office.com) zu, und melden Sie sich mit ihrem geschäftlichen oder Schulkonto an.

2. Wählen Sie im Office 365 &amp; Security Compliance Center im linken Navigationsbereich unter **Bedrohungs Verwaltung**die Option **Richtlinie**aus.

3. Wählen Sie auf der Seite **Richtlinie** die Option **Anti-Phishing** oder **ATP Anti-Phishing**aus.

4. Führen Sie auf der Seite **Anti-Phishing** oder **ATP Anti-Phishing** einen der folgenden Schritte aus:

   - Zum Hinzufügen einer neuen Richtlinie wählen Sie **+ Erstellen**aus.

   - Zum Bearbeiten einer vorhandenen Richtlinie wählen Sie den Richtliniennamen aus der Liste aus, die auf der Seite **Anti-Phishing** angezeigt wird. (Alternativ können Sie auch die **Standardrichtlinie** oberhalb der Liste auswählen.) Klicken Sie auf der angezeigten Seite auf **Richtlinie bearbeiten**.

5. Geben Sie den Namen, die Beschreibung sowie Einstellungen für Ihre Richtlinie an. Weitere Informationen finden Sie unter [Learn about ATP Anti-Phishing Policy Options](#learn-about-atp-anti-phishing-policy-options) .

6. Nachdem Sie Ihre Einstellungen überprüft haben, wählen Sie **Diese Richtlinie erstellen** (oder **Speichern**) aus.

## <a name="learn-about-atp-anti-phishing-policy-options"></a>Informationen zu den Optionen für die ATP-Anti-Phishing-Richtlinie

Wenn Sie Ihre ATP-Anti-Phishing-Richtlinien einrichten oder bearbeiten, können Sie aus mehreren Optionen auswählen, die den anspruchsvollsten und umfassendsten Schutz bieten, wie in der folgenden Tabelle beschrieben:

|**Diese Einstellung**|**Funktion**|**Verwenden Sie Folgendes, wenn Sie möchten:**|
|:-----|:-----|:-----|
|**Zu schützende Benutzer hinzufügen**|Definiert, welche e-Mail-Adressen durch die Richtlinie geschützt werden. Sie können bis zu 60 interne und externe Adressen hinzufügen, die Sie vor dem Identitätswechsel schützen möchten.|Wenn Sie sicherstellen möchten, dass e-Mails von außerhalb Ihrer Organisation kein Identitätswechsel eines Benutzers in der Liste der Benutzer sind, die Sie schützen. Beispiele für Benutzer, die Sie möglicherweise schützen möchten, sind hochrangige Führungskräfte, Geschäftsbesitzer, externe Verwaltungsratsmitglieder usw.  <br/> Diese Liste geschützter Benutzer unterscheidet sich von der Liste der Personen, für die die Richtlinie gilt, oder besser gesagt, für die die Richtlinie erzwungen wird. Sie definieren die Liste "gilt für" im Abschnitt " **angewendet** am" der Richtlinienoptionen.  <br/> Wenn Sie beispielsweise als zu `Mary Smith <marys@contoso.com>` schützender Benutzer hinzufügen, wenden Sie die Richtlinie auf die Gruppe "alle Benutzer" an. Dadurch wird sichergestellt, dass eine e-Mail-Nachricht, die dem Identitätswechsel von "Mary Smith" erschien, an einen Benutzer in der Gruppe "alle Benutzer" gesendet wurde, von der Richtlinie verarbeitet würde.|
|**Zu schützende Domänen hinzufügen**|Ermöglicht Ihnen die Auswahl der Domänen, die vor dem Identitätswechsel geschützt werden sollen. Sie können angeben, dass die Richtlinie alle benutzerdefinierten Domänen enthält, eine durch trennzeichengetrennte Liste von Domänen oder eine Kombination aus beiden. Wenn Sie **automatisch Domänen einschließen, die ich besitze**, und Sie später eine Domäne zu Ihrer Office 365 Organisation hinzufügen, wird diese Anti-Phishing-Richtlinie für die neue Domäne eingerichtet.|Wenn Sie sicherstellen möchten, dass e-Mails von außerhalb Ihrer Organisation nicht als Identitätswechsel einer der Domänen definiert sind, die in der Liste der überprüften Domänen oder einer Partnerdomäne definiert sind.|
|**Aktionen auswählen**|Wählen Sie die auszuführende Aktion aus, wenn Office 365 einen Identitätswechsel Versuch für die Benutzer und Domänen erkennt, die Sie der Richtlinie hinzugefügt haben. Sie können unterschiedliche Aktionen für Benutzer und Domänen in derselben Anti-Phishing-Richtlinie auswählen. Diese Aktionen gelten für alle eingehenden e-Mails, die von Office 365 als Identität eines Benutzerkontos oder einer Domäne identifiziert wurden, die unter dem Schutz dieser Anti-Phishing-Richtlinie steht.  <br/> **Quarantäne Nachricht** E-Mail wird an Office 365 Quarantäne gesendet. Wenn Sie diese Option auswählen, wird die e-Mail nicht an den ursprünglichen Empfänger gesendet.  <br/> **Weiterleiten von Nachrichten an eine andere e-Mail-Adresse** E-Mail wird an die von Ihnen angegebene e-Mail-Adresse gesendet. Sie können mehrere e-Mail-Adressen angeben. Wenn Sie diese Option auswählen, wird die e-Mail nicht an den ursprünglichen Empfänger gesendet.  <br/> **Nachricht in den Junk-e-Mail-Ordner des Empfängers verlagern** E-Mail wird an den Junk-e-Mail-Ordner des Empfängers gesendet. Wenn Sie diese Option auswählen, wird die e-Mail-Nachricht weiterhin an den ursprünglichen Empfänger gesendet, aber nicht im Posteingang des Empfängers gespeichert.  <br/> **Senden der Nachricht und Hinzufügen weiterer Adressen zur Bcc-Zeile** E-Mail wird an den ursprünglichen Empfänger zugestellt. Darüber hinaus werden die von Ihnen identifizierten Benutzer der Bcc-Zeile der Nachricht hinzugefügt, bevor Sie zugestellt wird. Wenn Sie diese Option auswählen, wird die e-Mail-Nachricht weiterhin an den Posteingang des ursprünglichen Empfängers gesendet.  <br/> Keine **Aktion anwenden** E-Mail wird an den Posteingang des ursprünglichen Empfängers zugestellt. Für die e-Mail-Nachricht werden keine weiteren Aktionen ausgeführt.  <br/> **Aktivieren von Tipps zum Schutz vor Phishing** Aktiviert Anti-Phishing-Sicherheitstipps in e-Mails.|Wenn Sie eine Aktion für Nachrichten durchführen möchten, die von Office 365 als Identitätswechsel eines Benutzers oder einer Domäne gemäß der Definition in der Richtlinie festgelegt wurde.|
|**Aktivieren der Post Fach Intelligenz**|Aktiviert oder deaktiviert die Post Fach Intelligenz für diese Richtlinie. Sie können die Post Fach Intelligenz nur für cloudbasierten Konten aktivieren, also für Konten, deren Postfach vollständig in Office 365 gehostet wird.| Dieses Feature verwendet Maschinelles Lernen, um die e-Mail-Muster eines Benutzers mit seinen Kontakten zu ermitteln. Mit diesen Informationen kann die AI besser zwischen echten und Phishing-e-Mails unterscheiden.|
|**Aktivieren des Post Fach informationsbasierten Identitätswechsel Schutzes**|Aktiviert oder deaktiviert die Post Fach Intelligenz für den Identitätswechsel Schutz für diese Richtlinie. Wichtig hierbei ist die Steuerung des Identitätswechsels für ein bestimmtes Postfach.|Wenn Sie die Ergebnisse des Identitätswechsels für Benutzer basierend auf der individuellen Absender Zuordnung jedes Benutzers verbessern möchten. Diese Intelligenz ermöglicht Office 365, die Erkennung von Benutzer Identitätswechseln anzupassen und besser mit falsch positiven Ergebnissen zu umgehen. Wenn der Benutzeridentitätswechsel basierend auf der Post Fach Intelligenz erkannt wird, können Sie definieren, welche Aktion für die Nachricht ausgeführt werden soll.|
|**Vertrauenswürdige Absender und Domänen hinzufügen**|Definiert e-Mail-Adressen und Domänen, die durch diese Richtlinie nicht als Identitätswechsel betrachtet werden. Nachrichten von den Absender-E-Mail-Adressen und Domänen, die Sie als vertrauenswürdige Absender und Domänen hinzufügen, werden nicht als auf einem Identitätswechsel basierte Angriffe eingestuft. Daher werden die Aktionen und Einstellungen in dieser Richtlinie nicht auf Nachrichten von diesen Absendern und Domänen angewendet.  <br/><br/>Der maximale Grenzwert für diese Listen beträgt ca. 1000 Einträge.|Wenn Benutzer mit Domänen oder Benutzern interagieren, die einen Identitätswechsel auslösen, jedoch als sicher eingestuft werden. Wenn ein Partner beispielsweise den gleichen/ähnlichen Anzeigenamen oder Domänennamen hat wie ein in der Liste definierter Benutzer.|
|**Angewendet auf**|Definiert die Empfänger, deren eingehende e-Mail-Nachrichten den Regeln der Richtlinie unterworfen werden. Sie können Bedingungen und Ausnahmen für die Empfänger erstellen, die der Richtlinie zugeordnet sind.  <br/> Sie können beispielsweise eine globale Richtlinie für Ihre Organisation erstellen, indem Sie die Regel auf alle Empfänger in Ihrer Domäne anwenden.  <br/> Sie können auch Ausnahmeregeln erstellen, beispielsweise eine Regel, die keine e-Mail-Nachrichten für eine bestimmte Empfängergruppe scannt.|Jede Richtlinie muss einer Reihe von Benutzern zugeordnet sein, beispielsweise Benutzern in einer bestimmten Gruppe oder Domäne.|
|**Erweiterte Phishing-Schwellenwerte**|Definiert die Ebene der Einstellungen für die Behandlung von Phishing-Nachrichten.  <br/> **Standard mäßig** E-Mail, die als Phishing vermutet wird, wird auf Standard-Weise verarbeitet.  <br/> **Aggressiv** E-Mail, die als Phishing mit hoher oder sehr hoher Zuverlässigkeit vermutet wird, wird vom System auf die gleiche Weise verarbeitet.  <br/> **Aggressiver** E-Mail, die als Phishing mit einem mittleren, hohen oder sehr hohen Maß an Zuverlässigkeit vermutet wird, wird vom System auf die gleiche Weise verarbeitet.  <br/> **Aggressivste** E-Mail-Verdacht auf Phishing mit niedrigem, mittlerem, hohem oder sehr hohem Maß an Zuverlässigkeit werden vom System auf die gleiche Weise behandelt.|Wenn Sie bei der Behandlung von potenziell Phishing-Nachrichten in Office 365 aggressiver vorgehen möchten. Beispielsweise werden Nachrichten mit einer sehr hohen Wahrscheinlichkeit, dass es sich um Phishing handelt, die aggressivsten Aktionen durchgeführt, während Nachrichten mit niedriger Wahrscheinlichkeit weniger aggressive Aktionen für Sie durchgeführt haben. Diese Einstellung wirkt sich auch auf andere Teile des Filtersystems aus, die Signale miteinander kombinieren. Dies bedeutet nicht zwangsläufig, dass unterschiedliche Aktionen implementiert werden.  Im wesentlichen legen Sie die Wahrscheinlichkeit für die Phishing-e-Mail fest, um die (gleiche) festgelegte Aktion zu bestimmen. Die Wahrscheinlichkeit, dass gute Nachrichten verschoben werden, steigt, wenn die Einstellungsstufe zunimmt.|

## <a name="learn-about-anti-phishing-policy-options"></a>Informationen zu Optionen für Anti-Phishing-Richtlinien

Wenn Sie Ihr Anti-Phishing-Feature einrichten oder bearbeiten, können Sie aus mehreren Optionen auswählen, wie in der folgenden Tabelle beschrieben:

|**Diese Einstellung**|**Funktion**|**Verwenden Sie Folgendes, wenn Sie möchten:**|
|:-----|:-----|:-----|
|**Angewendet auf**|Definiert die Empfänger, deren eingehende e-Mail-Nachrichten den Regeln der Richtlinie unterworfen werden. Sie können Bedingungen und Ausnahmen für die Empfänger erstellen, die der Richtlinie zugeordnet sind.  <br/> Sie können beispielsweise eine globale Richtlinie für Ihre Organisation erstellen, indem Sie die Regel auf alle Empfänger in Ihrer Domäne anwenden.  <br/> Sie können auch Ausnahmeregeln erstellen, beispielsweise eine Regel, die keine e-Mail-Nachrichten für eine bestimmte Empfängergruppe scannt.|Jede Richtlinie muss einer Reihe von Benutzern zugeordnet sein, beispielsweise Benutzern in einer bestimmten Gruppe oder Domäne.|
|**Aktionen auswählen**|Wählen Sie die Aktion aus, die ausgeführt werden soll, wenn Office 365 einen organisationsinternen oder einen externen org-Spoofing-Versuch für Ihre Benutzer erkennt. Diese Aktionen gelten für alle eingehenden e-Mails, die von Office 365 als Spoofing-Versuch für Benutzer identifiziert wurden, die unter dem Schutz dieser Anti-Phishing-Richtlinie stehen.  <br/> **Quarantäne Nachricht** E-Mail wird an Office 365 Quarantäne gesendet. Wenn Sie diese Option auswählen, wird die e-Mail nicht an den ursprünglichen Empfänger gesendet.  <br/> **Nachricht in den Junk-e-Mail-Ordner des Empfängers verlagern** E-Mail wird an den Junk-e-Mail-Ordner des Empfängers gesendet. Wenn Sie diese Option auswählen, wird die e-Mail-Nachricht weiterhin an den ursprünglichen Empfänger gesendet, aber nicht im Posteingang des Empfängers gespeichert.  <br/> Keine **Aktion anwenden** E-Mail wird an den Posteingang des ursprünglichen Empfängers zugestellt. Für die e-Mail-Nachricht werden keine weiteren Aktionen ausgeführt.|Wenn Sie eine Aktion für Nachrichten durchführen möchten, die von Office 365 als Spoofing-Versuch für interne oder externe Domänen gemäß der Definition in der Richtlinie festgelegt wurde.|

Nachdem Ihre Organisation Anti-Phishing-Richtlinien oder ATP-AntiPhishing-Richtlinien eingerichtet hat, können Sie sehen, wie der Dienst funktioniert, indem Sie [Berichte für Advanced Threat Protection anzeigen](view-reports-for-atp.md).

## <a name="example-anti-phishing-policy-to-protect-a-user-and-a-domain"></a>Beispiel: Anti-Phishing-Richtlinie zum Schutz von Benutzern und Domänen

In diesem Beispiel wird eine Richtlinie mit dem Namen "Domäne und CEO" eingerichtet, die sowohl Benutzer-als auch Domänen Schutz vor Identitätswechsel bereitstellt und dann die Richtlinie auf alle `contoso.com`e-Mails anwendet, die von Benutzern innerhalb der Domäne empfangen werden. Der Sicherheitsadministrator hat festgelegt, dass die Richtlinie diesen Geschäftsanforderungen entsprechen muss:

- Die Richtlinie muss den Schutz des E-Mail-Kontos und der gesamten Domain des CEO gewährleisten.

- Nachrichten, die als Imitationsversuche gegen das Benutzerkonto des CEO bestimmt sind, müssen an die E-Mail-Adresse des Sicherheitsadministrators weitergeleitet werden.

- Nachrichten, die als Imitationsversuche gegen die Domäne bestimmt sind, sind weniger dringend und sollten für eine spätere Überprüfung unter Quarantäne gestellt werden.

Der Sicherheitsadministrator von Contoso kann Werte wie die folgenden verwenden, um eine Anti-Phishing-Richtlinie zu erstellen, die diesen Anforderungen entspricht.

|||
|:-----|:-----|
|**Einstellung oder Option**|**Beispiel**|
|Name|Domäne und CEO|
|Beschreibung|Stellen Sie sicher, dass der CEO und unsere Domäne nicht imitiert werden.|
|Zu schützende Benutzer hinzufügen|Mindestens die E-Mail-Adresse des CEO.|
|Zu schützende Domänen hinzufügen|Die organisatorische Domäne, die das Büro des CEO umfasst.|
|Aktionen auswählen|Wenn e-Mail von einem imitierten Benutzer gesendet wird: Wählen Sie **Nachricht an eine andere e-Mail-Adresse umleiten** aus, und geben Sie dann die e `securityadmin@contoso.com`-Mail-Adresse des Sicherheitsadministrators ein, beispielsweise.  <br/> Wenn eine E-Mail von einer imitierten Domäne gesendet wird: Wählen Sie **Nachricht in Quarantäne verschieben**aus.|
|Mailbox Intelligence|Standardmäßig wird die Mailbox Intelligence ausgewählt, wenn Sie eine neue Anti-Phishing-Richtlinie erstellen. Lassen Sie diese Einstellung auf **Ein**, um optimale Ergebnisse zu erzielen.|
|Vertrauenswürdige Absender und Domänen hinzufügen|Definieren Sie in diesem Beispiel keine Außerkraftsetzungen.|
|Angewendet auf|Wählen Sie **Die Domäne des Empfängers ist** aus. Wählen Sie unter **Einer dieser**, **Auswählen** aus. Wählen Sie **+ Hinzufügen** aus. Aktivieren Sie das Kontrollkästchen neben dem Namen der Domäne, beispielsweise `contoso.com`in der Liste, und wählen Sie dann **Hinzufügen**aus. Wählen Sie **Fertig** aus.|

## <a name="delete-an-anti-phishing-or-atp-anti-phishing-policy"></a>Löschen einer Anti-Phishing-oder ATP-Anti-Phishing-Richtlinie

Sie können benutzerdefinierte Richtlinien löschen, die Sie mithilfe des &amp; Security Compliance Center erstellt haben. Die Standardrichtlinie für Ihre Organisation kann nicht gelöscht werden. Es wird empfohlen, eine &amp; ihrer ATP-Richtlinien über das Security Compliance Center zu überprüfen oder zu bearbeiten.

1. Wechseln Sie [https://protection.office.com](https://protection.office.com) zu, und melden Sie sich mit ihrem geschäftlichen oder Schulkonto an.

2. Wählen Sie im linken Navigationsbereich unter **Bedrohungs Verwaltung**die Option **Richtlinie**aus.

3. Wählen Sie auf der Seite **Richtlinie** die Option **Anti-Phishing** oder **ATP Anti-Phishing**aus.

4. Wählen Sie auf der Seite **Anti-Phishing** oder **ATP Anti-Phishing** den Richtliniennamen aus der Liste aus.

5. Wählen Sie auf der angezeigten Seite die Option **Richtlinie löschen**aus. Lassen Sie bis zu 30 Minuten zu, bis Ihre Änderungen auf alle Office 365-Rechenzentren verteilt sind.

## <a name="next-steps"></a>Nächste Schritte

Sobald Ihre Anti-Phishing-Richtlinien vorhanden sind, können Sie sehen, wie ihre Funktionen zum Schutz vor Bedrohungen für Ihre Organisation funktionieren, indem Sie Berichte anzeigen. Weitere Informationen finden Sie in den folgenden Ressourcen:

- [Anzeigen von Berichten für Office 365 ATP](view-reports-for-atp.md) oder [Anzeigen von e-Mail-Sicherheitsberichten](../../compliance/view-email-security-reports.md)

- [Verwenden von Threat Explorer (oder Echtzeiterkennung)](threat-explorer.md)

Bleiben Sie auf dem neuesten Stand neuer Features, die zu ATP kommen. Besuchen Sie die [Microsoft 365-Roadmap](https://www.microsoft.com/microsoft-365/roadmap?filters=O365) , und erfahren Sie mehr über die [neuen Features, die ATP hinzugefügt werden](office-365-atp.md#new-features-in-office-365-atp).
