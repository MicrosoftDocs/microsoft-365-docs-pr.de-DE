---
title: Visual Studio-Familie – Datensubjektanforderungen für die DSGVO
description: Visual Studio-Familie – Datensubjektanforderungen für die DSGVO
keywords: Visual Studio, Visual Studio Code, Visual Studio für Mac, Visual Studio-Dokumentation, Datenschutz, DSGVO
localization_priority: Priority
audience: itpro
ms.prod: visual-studio-family
ms.topic: article
ms.date: 05/24/2018
author: PoulChapman
ms.author: olholder
manager: pchapman
ms.collection: GDPR
ms.workload:
- multiple
ms.openlocfilehash: 744935cb41e1521970e6fac05493129eaaf7910d
ms.sourcegitcommit: 0dde96d5864e5b16ea24cfb302930b041c7a8091
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/24/2019
ms.locfileid: "34431546"
---
# <a name="visual-studio-family-data-subject-requests-for-the-gdpr"></a>Visual Studio-Familie – Datensubjektanforderungen für die DSGVO

Die [Datenschutz-Grundverordnung (DSGVO)](https://ec.europa.eu/justice/data-protection/reform/index_en.htm) der Europäischen Union gewährt Personen (die in den Bestimmungen als „betroffene Personen“ oder _Datensubjekte_ bezeichnet werden) Rechte zum Verwalten ihrer personenbezogenen Daten. Personenbezogene Daten sind im Rahmen der DSGVO sehr weitgefasst als Daten definiert, die sich auf eine identifizierte oder identifizierbare natürliche Person beziehen. Die DSGVO erteilt Datensubjekten bestimmte Rechte für ihre personenbezogenen Daten. Hierzu gehören das Kopieren der personenbezogenen Daten, das Anfordern von Korrekturen, das Einschränken der Verarbeitung, das Löschen oder das Erhalten in einem elektronischen Format. Eine formelle Anforderung, die von einem Datensubjekt an einen Datencontroller (einen Arbeitgeber oder eine andere Art von Behörde oder Organisation, die die Kontrolle über personenbezogene Daten besitzt) gesendet wird, damit für die personenbezogenen Daten dieses Datensubjekts eine Aktion durchgeführt wird, wird als _Datensubjektanforderung_ bezeichnet. Allgemeine Informationen zur DSGVO finden Sie im [DSGVO-Abschnitt im Service Trust Portal](https://servicetrust.microsoft.com/ViewPage/GDPRGetStarted).

## <a name="products-covered-by-this-guide"></a>In diesem Leitfaden behandelte Produkte

In diesem Leitfaden wird beschrieben, wie Sie Microsoft-Tools nutzen, um personenbezogene Daten, die im Verlauf von authentifizierten (angemeldeten) Sitzungen von Visual Studio und Visual Studio für Mac sowie dazugehörigen Microsoft-Erweiterungen und Erweiterungen für Visual Studio Code erfasst werden, zu exportieren oder zu löschen. Darüber hinaus wird in diesem Leitfaden beschrieben, wie Sie Datensubjektanforderungen für personenbezogene Daten durchführen, wenn Sie die Visual Studio Developer Community, NuGet.org und die ASP.NET-Website verwenden. Diese Produkte ermöglichen Ihnen ggf. die Nutzung von Tools und Erweiterungen, die nicht von Microsoft stammen und für die Microsoft nicht als Datenverarbeiter oder Controller fungiert. Benutzer sollten sich an den Anbieter des Tools bzw. der Erweiterung wenden, um sich mit den Richtlinien zu den personenbezogenen Daten und zur Erfassung für diese Tools und Erweiterungen vertraut zu machen.

## <a name="additional-privacy-information"></a>Zusätzliche Datenschutzinformationen

Unsere Methoden zur Datenverarbeitung sind in den Microsoft-Software-Lizenzbedingungen der Produkte, der [Datenschutzerklärung von Microsoft](https://go.microsoft.com/fwlink/?LinkId=660726) und den [DSGVO-Verpflichtungen von Microsoft](https://docs.microsoft.com/legal/gdpr) beschrieben.

## <a name="visual-studio-visual-studio-for-mac-and-visual-studio-code"></a>Visual Studio, Visual Studio für Mac und Visual Studio Code

### <a name="personal-data-we-collect"></a>Von uns erfasste personenbezogene Daten

Als Datenverarbeiter im Rahmen der DSGVO erfasst Microsoft von Benutzern die Daten, die benötigt werden, um Benutzeroberflächen für Visual Studio und Visual Studio für Mac sowie für dazugehörige Microsoft-Erweiterungen und Erweiterungen für Visual Studio Code bereitzustellen und zu verbessern. Es gibt zwei Kategorien von Daten: Kundendaten und vom System generierte Protokolle. Zu den Kundendaten gehören personenbezogene Transaktions- und Interaktionsdaten, die von diesen Produkten zum Bereitstellen des jeweiligen Diensts benötigt werden. Um Benutzern beispielsweise personalisierte Benutzeroberflächen, z.B. Roamingeinstellungen, bieten zu können, müssen wir Benutzerkontoinformationen und Einstellungsdaten erfassen. Vom System generierte Protokolle umfassen Nutzungs- oder Diagnosedaten, die zum Identifizieren und Behandeln von Problemen und Verbessern unserer Produkte und Dienste verwendet werden. Außerdem können sie personenbezogene Endbenutzerinformationen enthalten, z.B. einen Benutzernamen. Die vom System generierten Protokolle werden maximal 18 Monate lang aufbewahrt. Beispielsweise werden vom System generierte Protokolle für jeden Tag der Produktnutzung aggregiert und enthalten das Nutzungsdatum, das verwendete Produkt (z.B. „Visual Studio 2017“), die durchgeführte Aktion (z.B. „vs/core/packagecostsummary/solutionload“) und eine Angabe dazu, wie häufig die Aktion durchgeführt wurde. Dies ist in diesem Beispiel dargestellt:

```
{Time":"2/23/2018 12:00:00 AM","AppName":"Visual Studio 2017","Action":"vs/core/packagecostsummary/solutionload","Target":"1 times",
"DevicePlatform":"Windows 10 Enterprise","IP":null,"InputMethod":null,
"SearchTerm":null,"SearchResult":null}

{Time":"2/23/2018 12:00:00 AM","AppName":"Visual Studio 2017","Action":"vs/ide/connected/accountmanagement/account","Target":"1 times",
"DevicePlatform": "Windows 10 Enterprise","IP":null,"InputMethod":null,
"SearchTerm":null,"SearchResult":null}

{"Time":"2/27/2018 12:00:00 AM","AppName":"Visual Studio 2017","Action":"vs/core/perf/satellitepagefileusage","Target":"23 times",
"DevicePlatform":"Windows 10 Enterprise","IP":null,"InputMethod":null,
"SearchTerm":null,"SearchResult":null}
```

Weitere Informationen finden Sie unter [System-generated logs collected by Visual Studio](https://docs.microsoft.com/visualstudio/ide/diagnostic-data-collection) (Vom System generierte Protokolle, die von Visual Studio erfasst werden).

Nur personenbezogene Daten, die mit authentifizierten Identitäten verknüpft sind, können per Datensubjektanforderung behandelt werden. Da Visual Studio Code die Anmeldung nicht unterstützt, werden vom System generierte Protokolle dafür nicht mit einer authentifizierten Identität verknüpft und können nicht behandelt werden. Es kann aber sein, dass einige Microsoft-Erweiterungen für Visual Studio Code authentifizierte Daten bereitstellen, und diese Daten können per Datensubjektanforderung behandelt werden. Weitere Informationen finden Sie unter [DSGVO und Visual Studio Code](https://code.visualstudio.com/docs/supporting/faq#_gdpr-and-vs-code). Im Allgemeinen speichern wir keine Daten für Visual Studio 2013 und früher. Unter Umständen liefern aber bestimmte Erweiterungen und Komponenten Daten, die mit authentifizierten Identitäten verknüpft sind und wie unten beschrieben per Datensubjektanforderung behandelt werden können.

### <a name="how-users-can-control-personal-data"></a>Kontrolle personenbezogener Daten durch Benutzer

Visual Studio 2015 und höher, Visual Studio für Mac und Visual Studio Code verfügen über die folgenden Optionen, mit denen Ihre Benutzer die Datensammlung beenden und Sie als Controller Daten exportieren oder bereits erfasste Daten löschen können.

#### <a name="in-app-settings"></a>In-App-Einstellungen

Benutzer können die Datenschutzeinstellungen für diese Produkte kontrollieren. Weitere Informationen finden Sie in den Artikeln zu den folgenden Themen:

- [Verwalten von Datenschutzeinstellungen in Visual Studio](https://docs.microsoft.com/visualstudio/ide/visual-studio-experience-improvement-program).
- [Verwalten von Datenschutzeinstellungen in Visual Studio für Mac](https://docs.microsoft.com/visualstudio/mac/visual-studio-experience-improvement-program).
- [Deaktivieren der Telemetrieberichterstellung in Visual Studio Code](https://code.visualstudio.com/docs/supporting/faq#_how-to-disable-telemetry-reporting).

#### <a name="exporting-or-deleting-data"></a>Exportieren oder Löschen von Daten

Für Controller gibt es zwei Methoden, mit denen Kundendaten und vom System generierte Protokolle, die für ihre Datensubjekte erfasst werden, verwaltet werden können. Dies richtet sich danach, wie die Visual Studio-Produktfamilie oder die Microsoft-Erweiterungen registriert wurden. In einigen Fällen müssen beide Methoden verwendet werden. Beide Methoden ermöglichen es Controllern, eine Kopie ihres Aktivitätsverlaufs herunterzuladen, der mit dieser Methode verwaltet wird. Beim Schließen eines AAD- oder MSA-Kontos werden die zugeordneten Visual Studio-Kundendaten gelöscht, und die personenbezogenen Daten in vom System generierten Protokollen, die zu diesen Produkten gehören, werden anonymisiert. Anonymisierte vom System generierte Protokolle werden maximal 18 Monate lang aufbewahrt.

- Benutzer, die ein Produkt der Visual Studio-Familie über ein Konto registriert haben, das auf einem Azure-Mandanten basiert (z.B. ein AAD- oder MSA-Konto unter einem Azure-Abonnement), können die Anleitung unter [Azure-Datensubjektanforderungen für die DSGVO](gdpr-dsr-azure.md) befolgen.
- Benutzer, die ein Produkt der Visual Studio-Familie ohne Konto auf Basis eines Azure-Mandanten registriert haben (z.B. in vielen Fällen ein Microsoft-Konto (MSA)), können das [webbasierte Microsoft Privacy Response Center](https://aka.ms/userprivacysite) nutzen. Es ist über das Microsoft-Konto verfügbar und ermöglicht das übergreifende Anzeigen, Kontrollieren und Löschen von Aktivitätsdaten, die mit dem Microsoft-Konto verknüpft sind, für mehrere Microsoft-Dienste. In diesem Szenario ist der Benutzer ein Controller für seine eigenen personenbezogenen Daten.

> [!NOTE]
> Wenn ein MSA-Kontoinhaber sein Konto löscht, werden alle personenbezogenen Daten gelöscht, die zu diesen Produkten gehören – unabhängig davon, ob das Konto auf einem Azure-Mandanten basiert. Die vom System generierten Protokolle werden anonymisiert.

Für Visual Studio 2013 werden die erfassten Daten von uns anonymisiert. Für Visual Studio 2012 und vorherige Releases werden die Daten sofort nach dem Erhalt gelöscht. In beiden Fällen sind keine Daten vorhanden, die später angezeigt, exportiert oder gelöscht werden können.

## <a name="visual-studio-developer-community"></a>Visual Studio Developer Community

Wir unterstützen Anforderungen im Rahmen der [Datenschutz-Grundverordnung (DSGVO)](https://ec.europa.eu/justice/data-protection/reform/index_en.htm) über die Website der [Entwickler-Community](https://developercommunity.visualstudio.com). Sie können Ihre Feedbackdaten anzeigen, exportieren oder löschen.

### <a name="personal-data-we-collect"></a>Von uns erfasste personenbezogene Daten

Microsoft erfasst Daten, damit wir Probleme reproduzieren und behandeln können, die Sie über Produkte der Visual Studio-Familie melden. Zu diesen Daten gehören personenbezogene Daten und öffentliches Feedback. Personenbezogene Daten umfassen Folgendes:

- Ihre Profilinformationen aus der [Entwickler-Community](https://developercommunity.visualstudio.com)
- Einstellungen und Benachrichtigungen
- Anhänge und vom System generierte Protokolle, die Sie bereitgestellt haben, als Sie [in Visual Studio](https://docs.microsoft.com/visualstudio/ide/how-to-report-a-problem-with-visual-studio-2017) oder über die [Entwickler-Community](https://developercommunity.visualstudio.com) ein Problem gemeldet haben
- Ihre abgegebenen Stimmen

Das öffentliche Feedback umfasst Folgendes: gemeldete Probleme, Kommentare und Lösungen

### <a name="how-users-can-control-personal-data"></a>Kontrolle personenbezogener Daten durch Benutzer

#### <a name="view"></a>Anzeige

Führen Sie diese Schritte aus, um Ihre Feedbackdaten anzuzeigen:

1. Melden Sie sich bei der [Entwicklercommunity](https://developercommunity.visualstudio.com) an. Klicken Sie oben rechts auf Ihr Profil, und wählen Sie **Profil und Einstellungen**.
2. Klicken Sie auf die Registerkarte **Profil**, **Benachrichtigungen**, **Aktivität** oder **Anhänge**, um die an die Feedbacksysteme übermittelten Daten anzuzeigen.
   1. **Profil** bezieht sich auf Ihr Profil für die [Entwickler-Community](https://developercommunity.visualstudio.com) und enthält den Benutzernamen, die E-Mail-Adresse, allgemeine Informationen usw.
   2. **Benachrichtigungen steuern, welche E-Mail-Benachrichtigungen Sie erhalten.
   3. Unter **Aktivität** sind die Feedbackelemente, für die Sie Aktionen durchgeführt haben (Posten, Kommentieren usw.), und die Aktivitäten aufgeführt.
   4. Unter **Anhänge** wird eine Liste mit Ihrem Anhangverlauf beispielsweise im folgenden Format `FileName was attached to the problem "ProblemName" Tue, Apr 10, 18 2:27 PM` angezeigt.

#### <a name="export"></a>Export

Sie können Ihre Feedbackdaten im Rahmen der Datensubjektanforderung exportieren. Wir erstellen mindestens ein ZIP-Archiv mit folgendem Inhalt:

- Ihre Profilinformationen aus der [Entwickler-Community](https://developercommunity.visualstudio.com)
- Einstellungen und Benachrichtigungseinstellungen
- Anhänge, die Sie bereitgestellt haben, als Sie [in Visual Studio](https://docs.microsoft.com/visualstudio/ide/how-to-report-a-problem-with-visual-studio-2017) oder über die [Entwickler-Community](https://developercommunity.visualstudio.com) ein Problem gemeldet haben

> [!NOTE]
> Wir schließen das folgende öffentliche Feedback aus, das Sie aus Ihrem Archiv bereitgestellt haben: Kommentare, Lösungen, gemeldete Probleme.

Führen Sie diese Schritte aus, um einen Export zu starten:

1. Melden Sie sich bei der [Entwicklercommunity](https://developercommunity.visualstudio.com) an. Klicken Sie oben rechts auf Ihr Profil, und wählen Sie **Profil und Einstellungen**.
2. Klicken Sie auf die Registerkarte **Datenschutz**, und klicken Sie dann auf **Archiv erstellen**, um den Export Ihrer Daten anzufordern.
3. **Archivstatus** wird aktualisiert, um anzuzeigen, dass die Daten aufbereitet werden. Der Zeitraum bis zur Verfügbarkeit der Daten richtet sich nach der Menge der Daten, die exportiert werden müssen.
4. Wenn die Daten bereitstehen, senden wir Ihnen eine E-Mail.
5. Klicken Sie in der E-Mail auf **Archiv herunterladen**, oder greifen Sie wieder auf die Registerkarte „Datenschutz“ zu, um Ihre Daten herunterzuladen.

> [!NOTE]
> - Wir senden keine E-Mail, wenn Sie auf der Registerkarte „Benachrichtigungen“ angegeben haben, dass Sie keine Benachrichtigungen erhalten möchten.
> - Falls Sie den Export erneut anfordern, entfernen wir Ihr altes Archiv und erstellen ein neues.

#### <a name="delete"></a>Löschung

Beim Löschvorgang werden die folgenden Informationen zu Ihrer Person aus der [Entwickler-Community](https://developercommunity.visualstudio.com) gelöscht:

- Profilinformationen
- Einstellungen und Benachrichtigungseinstellungen
- Anhänge, die Sie bereitgestellt haben, als Sie [in Visual Studio](https://docs.microsoft.com/visualstudio/ide/how-to-report-a-problem-with-visual-studio-2017) oder über die [Entwickler-Community](https://developercommunity.visualstudio.com) ein Problem gemeldet haben
- Ihre abgegebenen Stimmen

> [!NOTE]
> Wir löschen die folgenden öffentlichen Informationen nicht, aber wir anonymisieren sie: Ihre Kommentare, Ihre Lösungen und die von Ihnen gemeldeten Probleme.
>
> [!IMPORTANT]
> Beim Löschvorgang für ein AAD- oder MSA-Konto wird der Löschvorgang für die [Entwickler-Community](https://developercommunity.visualstudio.com) ausgelöst.

Führen Sie diese Schritte aus, um den Löschvorgang zu initiieren:

1. Melden Sie sich an der [Entwickler-Community](https://developercommunity.visualstudio.com) an. Klicken Sie oben rechts auf Ihr Profil, und wählen Sie **Profil und Einstellungen**.
2. Klicken Sie auf die Registerkarte **Datenschutz** und dann auf **Daten und Konto löschen**, um den Löschvorgang für Ihre Daten zu starten.
3. Ein Bestätigungsbildschirm wird angezeigt.
4. Geben Sie im Feld „delete“ ein, und klicken Sie anschließend auf **Mein Konto löschen**.

Nachdem Sie auf **Mein Konto löschen** geklickt haben,

- melden wir Sie ab.
- Wir löschen Ihr Konto für die [Entwickler-Community](https://developercommunity.visualstudio.com), Ihre personenbezogenen Daten und die Anhänge.
- Wir anonymisieren Ihr öffentliches Feedback. Ihr öffentliches Feedback bleibt in der Entwickler-Community verfügbar, aber es wird angegeben, dass es von einem anonymen Benutzer stammt.
- Sie erhalten von uns nach dem Löschen Ihres Kontos keine E-Mails mehr, weil Sie nicht mehr im System vorhanden sind.
- Wenn Sie ein neues Problem melden oder sich an der [Entwickler-Community](https://developercommunity.visualstudio.com) anmelden, werden Sie als neuer Benutzer behandelt.
- Wenn Sie Ihr Konto für die [Entwickler-Community](https://developercommunity.visualstudio.com) löschen, wird es nicht für andere Microsoft-Dienste gelöscht.

## <a name="xamarin-forums-and-bugzilla"></a>Xamarin-Foren und Bugzilla

### <a name="personal-data-we-collect"></a>Von uns erfasste personenbezogene Daten

Über die Benutzercommunity in den [Xamarin-Foren](https://forums.xamarin.com) und die Websites zur Meldung von Fehlern unter [Xamarin Bugzilla](https://bugzilla.xamarin.com/) sammelt Microsoft von Ihnen angegebene Daten, damit wir Probleme reproduzieren und behandeln können, die bei Microsoft-Produkten und -Diensten unter Umständen auftreten. Zu diesen Daten gehören auch personenbezogene Daten und öffentliches Feedback. Bei den gesammelten personenbezogenen Daten handelt es sich um Benutzerkontodaten (z.B. Benutzernamen und E-Mail-Adressen Ihrer Konten für die Xamarin-Foren oder Bugzilla), und das erfasste öffentliche Feedback enthält Fehler, Probleme, Kommentare und Lösungen, die Sie über die Xamarin-Foren oder die Website zur Meldung von Fehlern unter Xamarin Bugzilla bereitstellen.

### <a name="how-you-can-control-your-data"></a>Vorgehensweise bei der Kontrolle Ihrer Daten

#### <a name="xamarin-forums"></a>Xamarin-Foren

##### <a name="view"></a>Anzeige

Benutzer mit aktiven Konten für Xamarin-Foren können ihre personenbezogenen Daten und ihr öffentliches Feedback (z.B. alle geposteten Threads und Beiträge) auf der Xamarin-Forum-Kontoseite anzeigen. Benutzer können ihre personenbezogenen Daten auch über ihre Kontoseite bearbeiten.

##### <a name="export"></a>Export

Xamarin-Foren werden von einem Drittanbieter, Vanilla Forums, gehostet. Zum Anfordern des Exports ihrer öffentlichen Daten sollten sich Benutzer an „forums@xamarin.com“ (vom Xamarin-Team überwacht) wenden. Wir arbeiten dann direkt mit Vanilla Forums zusammen, um diese Anforderung zu verarbeiten.

##### <a name="delete"></a>Löschen

Xamarin-Foren werden von einem Drittanbieter, Vanilla Forums, gehostet. Zum Anfordern der Löschung ihrer personenbezogenen und öffentlichen Daten sollten sich Benutzer an „forums@xamarin.com“ (vom Xamarin-Team überwacht) wenden. Wir nehmen dann manuell die angeforderte Löschung der personenbezogenen Daten des Benutzers vor.

#### <a name="bugzilla-for-xamarin"></a>Bugzilla für Xamarin

##### <a name="view"></a>Anzeige

Benutzer mit aktiven Xamarin Bugzilla-Konten können alle gemeldeten Fehler und alle Kommentare anzeigen, die sie Fehlern hinzugefügt haben, indem sie auf der Xamarin Bugzilla-Startseite auf die entsprechenden Links klicken.

##### <a name="export"></a>Export

Der Export von personenbezogenen Daten wird nicht unterstützt.

##### <a name="delete"></a>Löschung

Zum Anfordern der Löschung von personenbezogenen Daten, die in Verbindung mit der Xamarin-Website „Bugzilla“ zum Melden von Fehlern verwendet werden, können Benutzer ihr Xamarin Bugzilla-Konto schließen, indem sie auf der [Seite mit den Benutzereinstellungen](https://bugzilla.xamarin.com/userprefs.cgi) die Registerkarte **Konto schließen** wählen. Geben Sie Ihr Bugzilla-Kennwort ein, und aktivieren Sie das Kontrollkästchen, um das endgültige Löschen Ihres Kontos zu bestätigen. Öffentliches Feedback (z.B. Fehler, Probleme, Kommentare und Lösungen), das von Benutzern unter Xamarin Bugzilla gepostet wurde, wird nach Erhalt einer Löschanforderung nicht gelöscht. Stattdessen wird das öffentliche Feedback anonymisiert, indem für das gesamte öffentliche Feedback, das vom anfordernden Benutzer erstellt wurde, der Name und die E-Mail-Adresse entfernt werden.

## <a name="nuget"></a>NuGet

Weitere Informationen zu Datensubjektanforderungen für NuGet.org finden Sie unter [Benutzerdatenanforderungen](https://docs.microsoft.com/nuget/policies/data-requests).

## <a name="aspnet"></a>ASP.NET

Informationen zu Datensubjektanforderungen für die ASP.NET-Website finden Sie unter [The ASP.NET Website and GDPR Data Subject Request processing](https://www.asp.net/gdpr) (ASP.NET-Website und Verarbeitung von Datensubjektanforderungen gemäß DSGVO)

## <a name="iisnet"></a>IIS.NET

Informationen zu Datensubjektanforderungen für die IIS.NET-Website finden Sie unter [The IIS.NET Website and GDPR Data Subject Request processing](https://www.iis.net/gdpr) (IIS.NET-Website und Verarbeitung von Datensubjektanforderungen gemäß DSGVO)

## <a name="other-visual-studio-family-services"></a>Andere Dienste der Visual Studio-Familie

### <a name="surveymonkey"></a>SurveyMonkey

Von Zeit zu Zeit bitten wir Kunden um Feedback zu diesen Produkten per SurveyMonkey. Diese Daten werden innerhalb von 28 Tagen gelöscht. Falls bei der Bearbeitung von Datensubjektanforderungen für diese Produkte authentifizierte Antworten auf Umfragen vorliegen, fügen wir diese in den Export- und Löschvorgang ein.

### <a name="uservoice"></a>UserVoice

Wir bitten unsere Kunden, auf den UserVoice.com-Websites Vorschläge zu diesen Produkten anzugeben. Die Websites werden separat von UserVoice betrieben, und auch die Datensubjektanforderungen werden von UserVoice verwaltet.

- [https://visualstudio.uservoice.com/](https://visualstudio.uservoice.com/)
- [https://aspnet.uservoice.com/](https://aspnet.uservoice.com/)
- [https://xamarin.uservoice.com/](https://xamarin.uservoice.com/)

Informationen zu Datensubjektanforderungen für diese Daten finden Sie in der UserVoice-Anleitung zum [Exportieren von Daten](https://feedback.uservoice.com/knowledgebase/articles/1850245-export-my-personal-data) bzw. zum [Löschen von Daten](https://feedback.uservoice.com/knowledgebase/articles/1848856-delete-my-profile-information).

## <a name="learn-more"></a>Weitere Informationen

- [Microsoft's GDPR Commitments to Customers of our Generally Available Enterprise Software Products](https://docs.microsoft.com/legal/gdpr) (DSGVO-Verpflichtungen von Microsoft für Kunden unserer allgemein verfügbaren Unternehmenssoftwareprodukte)
- [Microsoft Trust Center](https://www.microsoft.com/TrustCenter/Privacy/gdpr/default.aspx)
- [Service Trust Portal (STP)](https://servicetrust.microsoft.com/ViewPage/GDPRGetStarted)
- [Microsoft-Datenschutzdashboard](https://account.microsoft.com/privacy)
- [Microsoft Privacy Response Center](https://aka.ms/userprivacysite)
- [Azure-Datensubjektanforderungen für die DSGVO](gdpr-dsr-azure.md)
