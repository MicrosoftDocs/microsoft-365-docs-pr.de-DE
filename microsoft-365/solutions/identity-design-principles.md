---
title: Microsoft 365 Enterprise Resource Planning – Sicherheitsarchitektur
description: Erfahren Sie mehr über top design strategies for Microsoft Enterprise architecture von Alex Shteynberg, Technical Principal Architect bei Microsoft.
ms.author: bcarter
author: brendacarter
manager: bcarter
ms.audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-identity-device-management
- M365-security-compliance
- M365solutions
ms.custom: seo-marvel-jun2020
f1.keywords: NOCSH
ms.openlocfilehash: 10cebf0ab74936d7275586f2e8f09c841c8c653f
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50918314"
---
# <a name="to-identity-and-beyondone-architects-viewpoint"></a>Zur Identität und darüber hinaus – Ansicht eines Architekten

In diesem Artikel erläutert [Alex Shteynberg](https://www.linkedin.com/in/alex-shteynberg/), Principal Technical Architect bei Microsoft, die wichtigsten Entwurfsstrategien für Unternehmen, die Microsoft 365 und andere Microsoft Cloud Services übernehmen.

## <a name="about-the-author"></a>Über den Autor

![Alex Shteynberg Foto](../media/solutions-architecture-center/identity-and-beyond-alex-shteynberg.jpg)

Ich bin Principal Technical Architect im New York [Microsoft Technology Center](https://www.microsoft.com/mtc?rtc=1). Ich arbeite hauptsächlich mit großen Kunden und komplexen Anforderungen. Meine Ansichten und Ansichten basieren auf diesen Interaktionen und gelten möglicherweise nicht für jede Situation. Wenn wir Kunden jedoch bei den komplexesten Herausforderungen unterstützen können, können wir meiner Erfahrung nach allen Kunden helfen.

Ich arbeite in der Regel mit mehr als 100 Kunden pro Jahr. Obwohl jede Organisation eindeutige Merkmale aufweist, ist es interessant, Trends und Gemeinsamkeiten zu sehen. Ein Trend ist beispielsweise branchenübergreifendes Interesse für viele Kunden. Schließlich kann eine Bankfiliale auch ein Café und ein Community Center sein.

In meiner Rolle fokussiere ich mich darauf, Kunden dabei zu helfen, die beste technische Lösung zu finden, um ihre einzigartigen Geschäftsziele zu erreichen. Offiziell fokussiere ich mich auf Identität, Sicherheit, Datenschutz und Compliance. Ich finde es gut, dass diese alles berühren, was wir tun. Es gibt mir die Möglichkeit, mich an den meisten Projekten zu beteiligen. Dadurch bin ich sehr beschäftigt und habe spaßig an dieser Rolle.

Ich wohne in New York City (am besten!) und möchte die Vielfalt seiner Kultur, seines Essens und seiner Personen (nicht des Verkehrs) wirklich genießen. Ich reise gerne, wenn ich den größten Teil der Welt in meinem Leben sehen kann. Ich recherchiert gerade eine Reise nach Afrika, um mehr über Wildtieren zu erfahren.

## <a name="guiding-principles"></a>Leitprinzipien

- **Einfach ist oft besser:** Sie können (fast) alles mit Technologie tun, aber es bedeutet nicht, dass Sie sollten. Insbesondere im Sicherheitsbereich überfingen viele Kunden Lösungen. Ich mag [dieses Video aus](https://www.youtube.com/watch?v=SOQgABDSYZE) der Stripe-Konferenz von Google, um diesen Punkt zu unterstreichen.
- **Personen, Prozess, Technologie:** Entwerfen sie für [Personen, um](https://en.wikipedia.org/wiki/Human-centered_design) den Prozess zu verbessern, nicht zuerst die Technologie. Es gibt keine "perfekten" Lösungen. Wir müssen verschiedene Risikofaktoren ausgleichen, und die Entscheidungen sind für jedes Unternehmen unterschiedlich. Zu viele Kunden entwerfen einen Ansatz, den ihre Benutzer später vermeiden.
- Konzentrieren Sie sich zuerst auf **"warum" und später auf "Wie":** Das lästige 7-yr alte Kind mit einer Million Fragen. Wir können nicht zu der richtigen Antwort gelangen, wenn wir die richtigen Fragen nicht kennen. Viele Kunden nehmen an, wie die Dinge funktionieren müssen, anstatt das Geschäftsproblem zu definieren. Es gibt immer mehrere Pfade, die verwendet werden können.
- **Langes Ende der bewährten Methoden** der Vergangenheit: Erkennen Sie, dass sich bewährte Methoden mit leichter Geschwindigkeit ändern. Wenn Sie sich Azure AD vor mehr als drei Monaten angeschaut haben, sind Sie wahrscheinlich veraltet. Alles hier kann nach der Veröffentlichung geändert werden. Die "Beste"-Option von heute ist in sechs Monaten möglicherweise nicht identisch.

## <a name="baseline-concepts"></a>Basiskonzepte

Überspringen Sie diesen Abschnitt nicht. Ich finde oft, dass ich zu diesen Themen einen Schritt zurück gehen muss, auch für Kunden, die Clouddienste seit Jahren verwenden.
Leider ist Sprache kein präzises Tool. Wir verwenden häufig dasselbe Wort, um unterschiedliche Konzepte oder unterschiedliche Wörter zu verwenden, um dasselbe Konzept zu meinen. Ich verwende dieses Diagramm unten häufig, um eine grundlegende Terminologie und ein "Hierarchiemodell" zu erstellen.
<br><br>

![Abbildung von Mandanten, Abonnement, Dienst und Daten](../media/solutions-architecture-center/Identity-and-beyond-tenant-level.png)  

<br>

Wenn Sie lernen, zu schwimmen, ist es besser, im Pool zu beginnen und nicht in der Mitte des Ozeans. Ich versuche nicht, mit diesem Diagramm technisch genau zu sein. Es ist ein Modell, um einige grundlegende Konzepte zu besprechen.

Aus dem Diagramm geht Folgendes hervor:

- Mandant = eine Instanz von Azure AD. Sie befindet sich am oberen Rand einer Hierarchie oder ebene 1 im Diagramm. Wir können dies als["Grenze"](/azure/active-directory/users-groups-roles/licensing-directory-independence)betrachten, an der alles andere stattfindet ([Azure AD B2B](/azure/active-directory/b2b/what-is-b2b) beiseite). Alle Microsoft Enterprise Cloud Services sind Teil eines dieser Mandanten. Verbraucherdienste sind getrennt. "Mandant" wird in der Dokumentation als Office 365-Mandant, Azure-Mandant, WVD-Mandant und so weiter angezeigt. Ich finde häufig, dass diese Variationen für Kunden Verwirrung stiften.
- Dienste/Abonnements, Ebene 2 im Diagramm, gehören zu einem und nur einem Mandanten. Die meisten SaaS-Dienste sind 1:1 und können ohne Migration nicht bewegt werden. Azure ist anders, Sie können [die Abrechnung](/azure/cost-management-billing/manage/billing-subscription-transfer) und/oder ein [Abonnement in](/azure/active-directory/fundamentals/active-directory-how-subscriptions-associated-directory) einen anderen Mandanten verschieben. Es gibt viele Kunden, die Azure-Abonnements verschieben müssen. Dies hat verschiedene Auswirkungen. Objekte, die außerhalb des Abonnements vorhanden sind, werden nicht bewegt (z. B. rollenbasierte Zugriffssteuerung oder Azure RBAC und Azure AD-Objekte, einschließlich Gruppen, Apps, Richtlinien und so weiter). Außerdem einige Dienste (z. B. Azure Key Vault, Data Bricks und so weiter). Migrieren Sie Dienste nicht ohne eine gute Geschäftliche Notwendigkeit. Einige Skripts, die für die Migration hilfreich sein können, [werden auf GitHub freigegeben.](https://github.com/lwajswaj/azure-tenant-migration)
- Ein gegebener Dienst hat in der Regel eine Art "Unterebene"-Grenze oder Ebene 3 (L3). Dies ist nützlich, um die Trennung von Sicherheit, Richtlinien, Governance und so weiter zu verstehen. Leider gibt es keinen einheitlichen Namen, den ich kenne. Beispiele für L3 sind: Azure Subscription = [resource](/azure/azure-resource-manager/management/manage-resources-portal); Dynamics 365 CE = [Instanz](/dynamics365/admin/new-instance-management); Power BI = [Arbeitsbereich](/power-bi/service-create-the-new-workspaces); Power Apps = [Umgebung](/power-platform/admin/environments-overview); Und so weiter.
- Ebene 4 ist der Ort, an dem die tatsächlichen Daten gespeichert sind. Diese "Datenebene" ist ein komplexes Thema. Einige Dienste verwenden Azure AD für RBAC, andere nicht. Ich werde es ein wenig besprechen, wenn wir zu Delegierungsthemen kommen.

Einige zusätzliche Konzepte, zu deren Lösung ich viele Kunden (und Microsoft-Mitarbeiter) finde, sind verwirrt oder haben Fragen zu folgenden Themen:

- Jeder kann [viele](/azure/active-directory/fundamentals/active-directory-access-create-new-tenant) Mandanten ohne [Kosten erstellen.](https://azure.microsoft.com/pricing/details/active-directory/) Sie benötigen keinen in ihr bereitgestellten Dienst. Ich habe Dutzende. Jeder Mandantname ist im weltweiten Clouddienst von Microsoft eindeutig (d. h., es dürfen keine zwei Mandanten denselben Namen haben). Sie alle haben das Format TenantName.onmicrosoft.com. Es gibt auch Prozesse, die Mandanten automatisch erstellen ([nicht verwaltete Mandanten](/azure/active-directory/users-groups-roles/directory-self-service-signup)). Dies kann beispielsweise auftreten, wenn sich ein Benutzer bei einem Unternehmensdienst mit einer E-Mail-Domäne meldet, die in keinem anderen Mandanten vorhanden ist.
- In einem verwalteten Mandanten können viele [DNS-Domänen](/azure/active-directory/fundamentals/add-custom-domain) in ihm registriert werden. Dadurch wird der ursprüngliche Mandantenname nicht geändert. Es gibt derzeit keine einfache Möglichkeit, einen Mandanten umzubenennen (mit Der Migration). Obwohl der Name des Mandanten in diesen Tagen technisch nicht wichtig ist, kann dies für einige als einschränkend bezeichnet werden.
- Sie sollten einen Mandantennamen für Ihre Organisation reservieren, auch wenn Sie noch keine Dienste bereitstellen möchten. Andernfalls kann es von jemandem von Ihnen entfernt werden, und es gibt keinen einfachen Prozess, um ihn zurück zu nehmen (dasselbe Problem wie DNS-Namen). Ich höre dies zu oft von Kunden. Der Name Ihres Mandanten sollte auch ein Diskussionsthema sein.
- Wenn Sie dns-Namespaces besitzen, sollten Sie all diese zu Ihren Mandanten hinzufügen. Andernfalls könnte ein [nicht verwalteter Mandant](/azure/active-directory/users-groups-roles/directory-self-service-signup) mit diesem Namen erstellt werden, was dann zu Unterbrechungen führt, [damit er verwaltet wird.](/azure/active-directory/users-groups-roles/domains-admin-takeover)
- DER DNS-Namespace (z. B. contoso.com) kann zu einem und nur einem Mandanten gehören. Dies hat Auswirkungen auf verschiedene Szenarien (z. B. das Freigeben einer E-Mail-Domäne während einer Fusion oder eines Kaufs und so weiter). Es gibt eine Möglichkeit, einen DNS-Sub (z. B. div.contoso.com) in einem anderen Mandanten zu registrieren, dies sollte jedoch vermieden werden. Bei der Registrierung eines Domänennamens auf oberster Ebene wird davon ausgegangen, dass alle Unterdomänen demselben Mandanten angehören. In Szenarien mit mehreren Mandanten (siehe unten) würde ich normalerweise die Verwendung eines anderen Domänennamens auf oberster Ebene empfehlen (z. B. contoso.ch oder ch-contoso.com).
- Wem sollte ein Mandant "besitzen"? Ich sehe häufig Kunden, die nicht wissen, wem ihr Mandant derzeit besitzt. Dies ist eine große rote Kennzeichnung. Rufen Sie microsoft support ASAP an. Ebenso problematisch ist es, wenn ein Dienstbesitzer (häufig ein Exchange-Administrator) zum Verwalten eines Mandanten bestimmt ist. Der Mandant enthält alle Dienste, die Sie in Zukunft wünschen. Der Mandantenbesitzer sollte eine Gruppe sein, die die Entscheidung für die Aktivierung aller Clouddienste in einer Organisation treffen kann. Ein weiteres Problem ist, wenn eine Mandantenbesitzergruppe aufgefordert wird, alle Dienste zu verwalten. Dies wird für große Organisationen nicht skaliert.
- Es gibt kein Konzept eines Sub-/Super-Mandanten. Aus einem bestimmten Grund wiederholt sich dieser Legende immer wieder. Dies gilt [auch für Azure AD B2C-Mandanten.](/azure/active-directory-b2c/) Ich höre zu oft: "Meine B2C-Umgebung befindet sich in meinem XYZ-Mandanten" oder "Wie verschiebe ich meinen Azure-Mandanten in meinen Office 365-Mandanten?"
- Dieses Dokument konzentriert sich hauptsächlich auf die kommerzielle weltweite Cloud, da dies von den meisten Kunden verwendet wird. Manchmal ist es hilfreich, über [hoheItenwolken zu wissen.](/azure/active-directory/develop/authentication-national-cloud) Unabhängigen Clouds haben zusätzliche Auswirkungen auf die Diskussion, die für diese Diskussion nicht in Frage kommen.

## <a name="baseline-identity-topics"></a>Grundlegende Identitätsthemen

Es gibt eine große Dokumentation zur Identitätsplattform von Microsoft – Azure Active Directory (Azure AD). Für diejenigen, die gerade erst beginnen, wirkt es oft überwältigend. Auch nachdem Sie mehr darüber erfahren haben, kann es schwierig sein, mit ständiger Innovation und Änderung mithalten zu können. In meinen Kundeninteraktionen sehe ich mich häufig als "Übersetzer" zwischen Geschäftszielen und "Guten, besseren, besten" Ansätzen, um diese (und menschliche "Klippennotizen" für diese Themen) zu adressieren. Es gibt selten eine perfekte Antwort, und die "richtige" Entscheidung ist eine Balance aus verschiedenen Risikofaktoren. Nachfolgend finden Sie einige der häufig gestellten Fragen und Verwirrungsbereiche, die ich mit Kunden besprechen möchte.

### <a name="provisioning"></a>Bereitstellung

Azure AD löst nicht aus Mangel an Steuerung in Ihrer Identitätswelt! [Die Identitätsverwaltung](/azure/active-directory/governance/identity-governance-overview) sollte unabhängig von jeder Cloudentscheidung ein wichtiges Element sein. Die Governanceanforderungen ändern sich im Laufe der Zeit, weshalb es sich um ein Programm und nicht um ein Tool handelt.

[Azure AD Connect](/azure/active-directory/hybrid/whatis-azure-ad-connect) vs. [Microsoft Identity Manager](/microsoft-identity-manager/microsoft-identity-manager-2016) (MIM) im Vergleich zu etwas anderem (Drittanbieter oder benutzerdefinierten)? Sparen Sie sich jetzt und in Zukunft viel Kopfzerbrechen, und verwenden Sie Azure AD Connect. Es gibt alle Arten von Smarts in diesem Tool, um besondere Kundenkonfigurationen und fortlaufende Innovationen zu adressiert.

Einige Edgefälle, die zu einer komplexeren Architektur verf sten können:

- Ich habe mehrere AD-Gesamtstrukturen ohne Netzwerkverbindung zwischen diesen. Es gibt eine neue Option namens [Cloud Provisioning](/azure/active-directory/cloud-provisioning/what-is-cloud-provisioning).
- Ich habe weder Active Directory noch möchte ich es installieren. Azure AD Connect kann für die Synchronisierung über [LDAP](/azure/active-directory/hybrid/plan-hybrid-identity-design-considerations-tools-comparison) konfiguriert werden (Möglicherweise ist ein Partner erforderlich).
- Ich muss die gleichen Objekte für mehrere Mandanten bereitstellen. Dies wird technisch nicht unterstützt, hängt aber von der Definition von "same" ab.

Soll ich Standardsynchronisierungsregeln anpassen ([Filterobjekte](/azure/active-directory/hybrid/how-to-connect-sync-configure-filtering), [Attribute ändern,](/azure/active-directory/hybrid/reference-connect-sync-attributes-synchronized) [alternative Anmelde-ID](/azure/active-directory/hybrid/plan-connect-userprincipalname)und so weiter)? Vermeiden Sie es! Eine Identitätsplattform ist nur so wertvoll wie die Dienste, die sie verwenden. Sie können zwar alle Arten von nußigen Konfigurationen tun, aber um diese Frage zu beantworten, müssen Sie sich die Auswirkungen auf Anwendungen anschauen. Wenn Sie E-Mail-aktivierte Objekte filtern, ist die GAL für Onlinedienste unvollständig. Wenn die Anwendung bestimmte Attribute verwendet, hat das Filtern dieser Attribute unvorhersehbare Auswirkungen. Und so weiter. Es ist keine Entscheidung des Identitätsteams.

XYZ SaaS unterstützt die Just-in-Time(JIT)-Bereitstellung, warum müssen Sie mich synchronisieren? Siehe weiter oben. Viele Anwendungen benötigen "Profil"-Informationen für die Funktionalität. Sie können keine GAL verwenden, wenn nicht alle E-Mail-aktivierten Objekte verfügbar sind. Gleiches gilt für [die Benutzerbereitstellung](/azure/active-directory/app-provisioning/user-provisioning) in Anwendungen, die in Azure AD integriert sind.

### <a name="authentication"></a>Authentifizierung

[Kennworthashsynchronisierung](/azure/active-directory/hybrid/how-to-connect-password-hash-synchronization) (Password Hash Sync, PHS) im Vergleich zur [Pass-Through-Authentifizierung (Pass-Through Authentication,](/azure/active-directory/hybrid/how-to-connect-pta-how-it-works) PTA) im Vergleich zum [Verbund](/azure/active-directory/hybrid/how-to-connect-fed-compatibility).

In der Regel gibt es eine [leidenschaftliche Diskussion um](/azure/active-directory/hybrid/choose-ad-authn) den Verbund. Einfacher ist in der Regel besser und verwenden Sie daher PHS, es sei denn, Sie haben einen guten Grund, dies nicht zu tun. Es ist auch möglich, verschiedene Authentifizierungsmethoden für unterschiedliche DNS-Domänen im gleichen Mandanten zu konfigurieren. 

Einige Kunden aktivieren Verbund + PHS hauptsächlich für:

- Eine Option, [auf die (für die](/azure/active-directory/hybrid/plan-migrate-adfs-password-hash-sync) Notfallwiederherstellung) zurückfallen kann, wenn der Verbunddienst nicht verfügbar ist.
- Zusätzliche Funktionen (z. B.: [Azure AD DS](/azure/active-directory-domain-services/tutorial-configure-password-hash-sync)) und Sicherheitsdienste (z. B.: [nicht gelaufene Anmeldeinformationen](/azure/active-directory/reports-monitoring/concept-risk-events#leaked-credentials))
- Unterstützung für Dienste in Azure, die die Verbundauthentifizierung nicht verstehen (z. B. [Azure Files](/azure/storage/files/storage-files-active-directory-overview)).

Häufig durchlaufe ich Kunden durch den Clientauthentifizierungsfluss, um einige falsche Vorstellungen zu verdeutlichen. Das Ergebnis sieht wie das folgende Bild aus, das nicht so gut ist wie der interaktive Prozess des Abrufens.

![Beispiel für eine Whiteboard-Unterhaltung](../media/solutions-architecture-center/identity-beyond-whiteboard-example.png)

Diese Art von Whiteboardzeichnung veranschaulicht, wo Sicherheitsrichtlinien innerhalb des Ablaufs einer Authentifizierungsanforderung angewendet werden. In diesem Beispiel werden Richtlinien, die über den Active Directory Federation Service (AD FS) erzwungen werden, auf die erste Dienstanforderung angewendet, jedoch nicht auf nachfolgende Dienstanforderungen. Dies ist mindestens ein Grund, sicherheitskontrollen so weit wie möglich in die Cloud zu verschieben.

Wir haben den Wunsch nach einmaligem Anmelden [(Single Sign-On,](/azure/active-directory/manage-apps/what-is-single-sign-on) SSO) so lange geträumst, wie ich mich erinnern kann. Einige Kunden glauben, dass sie dies erreichen können, indem sie den Anbieter für den "richtigen" Verbund (Right Federation, STS) auswählen. Azure AD kann erheblich zur Aktivierung [von SSO-Funktionen](/azure/active-directory/manage-apps/plan-sso-deployment) beitragen, aber kein STS ist magisch. Es gibt zu viele "legacy"-Authentifizierungsmethoden, die weiterhin für kritische Anwendungen verwendet werden. Das Erweitern von Azure AD [mit Partnerlösungen](/azure/active-directory/saas-apps/tutorial-list) kann viele dieser Szenarien adressieren. SSO ist eine Strategie und eine Reise. Sie können dies nicht erreichen, ohne sich auf [Standards für Anwendungen zu verdingen.](/azure/active-directory/develop/v2-app-types) Im Zusammenhang mit diesem Thema steht eine Reise zur [kennwortlosen](/azure/active-directory/authentication/concept-authentication-passwordless) Authentifizierung, die auch keine magische Antwort hat.

[Die mehrstufige Authentifizierung (Multi-Factor Authentication,](/azure/active-directory/authentication/concept-mfa-howitworks) MFA) ist heute unerlässlich[(hier](https://techcommunity.microsoft.com/t5/azure-active-directory-identity/your-pa-word-doesn-t-matter/ba-p/731984) für mehr). Fügen Sie der [Benutzerverhaltensanalyse](/azure/active-directory/authentication/tutorial-risk-based-sspr-mfa) hinzu, und Sie haben eine Lösung, die die häufigsten Cyberangriffe verhindert. Selbst Verbraucherdienste benötigen MFA. Dennoch treffe ich mich mit vielen Kunden, die nicht zu modernen Authentifizierungsansätzen [wechseln](../enterprise/hybrid-modern-auth-overview.md) möchten. Das größte Argument, das ich höre, ist, dass es Sich auf Benutzer und Ältere Anwendungen auswirken wird. Manchmal hilft ein guter Kick Kunden, sich zu bewegen – Exchange Online [hat Änderungen angekündigt.](https://techcommunity.microsoft.com/t5/exchange-team-blog/basic-auth-and-exchange-online-february-2020-update/ba-p/1191282) Viele Azure [AD-Berichte](/azure/active-directory/fundamentals/concept-fundamentals-block-legacy-authentication) stehen jetzt zur Verfügung, um Kunden bei diesem Übergang zu helfen.

### <a name="authorization"></a>Authorization

Laut [Wikipedia](https://en.wikipedia.org/wiki/Authorization)ist "zu autorisieren" das Definieren einer Zugriffsrichtlinie. Viele Personen betrachten es als die Möglichkeit, Zugriffssteuerelemente für ein Objekt (Datei, Dienst und so weiter) zu definieren. In der aktuellen Welt der Cyberbedrohungen entwickelt sich dieses Konzept schnell zu einer dynamischen Richtlinie, die auf verschiedene Bedrohungsvektoren reagieren und zugriffssteuerungen als Reaktion darauf schnell anpassen kann. Wenn ich z. B. von einem ungewöhnlichen Standort aus auf mein Bankkonto zu zugegriffen habe, erhalten sie zusätzliche Bestätigungsschritte. Um diesem Ansatz zu nähern, müssen wir nicht nur die Richtlinie selbst, sondern auch das Ökosystem der Methoden zur Erkennung von Bedrohungen und signalkorrelation berücksichtigen.

Das Richtlinienmodul von Azure AD wird mithilfe von Richtlinien für [bedingten Zugriff implementiert.](/azure/active-directory/conditional-access/overview) Dieses System hängt von Informationen aus einer Vielzahl anderer Bedrohungserkennungssysteme ab, um dynamische Entscheidungen zu treffen. Eine einfache Ansicht würde etwa wie die folgende Abbildung aussehen:

![Richtlinienmodul in Azure AD](../media/solutions-architecture-center/identity-and-beyond-illustration-3.png)

Die Kombination aller dieser Signale ermöglicht dynamische Richtlinien wie die folgenden:

- Wenn eine Bedrohung auf Ihrem Gerät erkannt wird, wird Ihr Zugriff auf Daten nur auf das Web reduziert, ohne dass Sie herunterladen können.
- Wenn Sie ein ungewöhnlich hohes Datenvolumen herunterladen, werden alle heruntergeladenen Daten verschlüsselt und eingeschränkt.
- Wenn Sie auf einen Dienst von einem nicht verwalteten Gerät aus zugreifen, werden Sie von hochsensiblen Daten blockiert, dürfen jedoch auf nicht eingeschränkte Daten zugreifen, ohne ihn an einen anderen Speicherort kopieren zu können.

Wenn Sie dieser erweiterten Definition der Autorisierung zustimmen, müssen Sie zusätzliche Lösungen implementieren. Welche Lösungen Sie implementieren, hängt davon ab, wie dynamisch die Richtlinie sein soll und welche Bedrohungen Sie priorisieren möchten. Beispiele für solche Systeme sind:

- [Azure AD Identity Protection](/azure/active-directory/identity-protection/) 
- [Microsoft Defender for Identity](/azure-advanced-threat-protection/)
- [Microsoft Defender für Endpunkt](/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)
- [Microsoft Defender für Office 365](../security/office-365-security/office-365-atp.md?view=o365-worldwide)
- [Microsoft Cloud App Security](/cloud-app-security/) (MCAS)
- [Microsoft 365 Defender](../security/mtp/microsoft-threat-protection.md?view=o365-worldwide)
- [Microsoft Intune](/mem/intune/)
- [Microsoft Information Protection](../compliance/information-protection.md?view=o365-worldwide) (MIP)
- [Azure Sentinel](/azure/sentinel/)

Neben Azure AD verfügen natürlich verschiedene Dienste und Anwendungen über eigene spezifische Autorisierungsmodelle. Einige dieser Themen werden später im Abschnitt "Delegierung" behandelt.

### <a name="audit"></a>Überwachung

Azure AD verfügt über detaillierte [Überwachungs- und Berichtsfunktionen.](/azure/active-directory/reports-monitoring/) Dies ist jedoch in der Regel nicht die einzige Informationsquelle, die benötigt wird, um Sicherheitsentscheidungen zu treffen. Weitere Informationen dazu finden Sie im Abschnitt Delegierung.

## <a name="theres-no-exchange"></a>Es gibt kein Exchange

Keine Panik! Dies bedeutet nicht, dass Exchange veraltet ist (oder SharePoint, und so weiter). Es ist immer noch ein Kerndienst. Was ich meine, ist, dass Technologieanbieter seit einiger Zeit die Benutzererfahrungen (User Experiences, UX) so umstiegen, dass sie Komponenten mehrerer Dienste umfassen. In Microsoft 365 ist ein einfaches Beispiel "[moderne](https://support.office.com/article/Attach-files-or-insert-pictures-in-Outlook-email-messages-BDFAFEF5-792A-42B1-9A7B-84512D7DE7FC)Anlagen ", bei denen Anlagen an E-Mails in SharePoint Online oder OneDrive for Business gespeichert werden.

![Anfügen einer Datei an eine E-Mail](../media/solutions-architecture-center/modern-attachments.png)

Wenn Sie sich den Outlook-Client anschauen, sehen Sie viele Dienste, die im Rahmen dieser Erfahrung "verbunden" sind, nicht nur Exchange. Dies umfasst Azure AD-, Microsoft Search-, Apps-, Profil-, Compliance- und Office 365-Gruppen. 

![Outlook-Schnittstelle mit Callouts](../media/solutions-architecture-center/identity-and-beyond-conceptual-screenshot.png)

Informationen zu [Microsoft Fluid Framework finden](https://techcommunity.microsoft.com/t5/microsoft-365-blog/microsoft-ignite-blog-microsoft-fluid-framework-preview/ba-p/978268) Sie unter Vorschau auf bevorstehende Funktionen. In der Vorschau jetzt kann ich Teams-Unterhaltungen direkt in Outlook lesen und beantworten. Tatsächlich ist der [Teams-Client](https://products.office.com/microsoft-teams/download-app) eines der prominenteren Beispiele für diese Strategie. 

Insgesamt wird es schwieriger, eine klare Linie zwischen Office 365 und anderen Diensten in Microsoft Clouds zu zeichnen. Ich sehe es als großen Vorteil für Kunden, da sie von der gesamten Innovation in allen von uns verwendeten Komponenten profitieren können, auch wenn sie eine Komponente verwenden. Ziemlich cool und hat weitreichende Auswirkungen auf viele Kunden.

Heute finde ich, dass viele Kunden-IT-Gruppen um "Produkte" herum strukturiert sind. Es ist logisch für eine lokale Welt, da Sie einen Experten für jedes bestimmte Produkt benötigen. Ich bin jedoch total froh, dass ich keine Active Directory- oder Exchange-Datenbank jemals wieder debuggen muss, da diese Dienste in die Cloud verschoben wurden. Durch die Automatisierung (welche Cloud ist) werden bestimmte sich wiederholende manuelle Aufträge entfernt (sehen Sie sich an, was mit Fabriken passiert ist). Diese werden jedoch durch komplexere Anforderungen ersetzt, um die interaktionsübergreifende Interaktion, Auswirkungen, Geschäftsanforderungen und so weiter zu verstehen. Wenn Sie bereit sind zu [lernen,](/learn/)gibt es große Möglichkeiten, die durch die Cloudtransformation ermöglicht werden. Bevor ich auf Technologie zuspringe, rede ich häufig mit Kunden über die Verwaltung von Änderungen in den IT-Fähigkeiten und Teamstrukturen.

An alle SharePoint-Fan-Personen und -Entwickler wenden Sie sich bitte nicht mehr an die Frage "Wie kann ich XYZ in SharePoint online tun?" Verwenden [Sie Power Automate](/power-automate/) (oder Flow) für Workflows, es ist eine wesentlich leistungsfähigere Plattform. Verwenden [Sie Azure Bot Framework,](/azure/bot-service/?view=azure-bot-service-4.0) um eine bessere UX für Ihre 500-K-Elementliste zu erstellen. Beginnen Sie mit [der Verwendung von Microsoft Graph](https://developer.microsoft.com/graph/) anstelle von CSOM. [Microsoft Teams](/MicrosoftTeams/Teams-overview) enthält SharePoint, aber auch eine Welt mehr. Es gibt viele andere Beispiele, die ich auflisten kann. Es gibt ein riesiges und großartiges Weltall. Öffnen Sie die Tür, und [beginnen Sie zu erkunden.]()

Die anderen gemeinsamen Auswirkungen sind im Compliancebereich. Dieser dienstübergreifende Ansatz scheint viele Compliancerichtlinien vollständig zu verwechseln. Ich sehe immer wieder Organisationen mit dem Status "Ich muss die gesamte E-Mail-Kommunikation in einem eDiscovery-System journalieren". Was bedeutet dies wirklich, wenn E-Mails nicht mehr nur E-Mails, sondern ein Fenster in andere Dienste sind? Office 365 hat einen umfassenden Ansatz für [compliance,](../compliance/index.yml)aber das Ändern von Personen und Prozessen ist oft viel schwieriger als technologie.

Es gibt viele andere Personen und Prozessauswirkungen. Meiner Meinung nach ist dies ein kritischer und nicht behandelter Bereich. Vielleicht mehr in einem anderen Artikel.

## <a name="tenant-structure-options"></a>Mandantenstrukturoptionen

### <a name="single-tenant-vs-multi-tenant"></a>Einzelner Mandant im Vergleich zu mehreren Mandanten

Im Allgemeinen sollten die meisten Kunden nur einen Produktions mandanten haben. Es gibt viele Gründe, warum mehrere Mandanten eine Herausforderung darstellen (geben Sie ihm eine [Bing-Suche)](https://www.bing.com/search?q=office%20365%20multiple%20tenants)oder lesen Sie dieses [Whitepaper](https://aka.ms/multi-tenant-user). Gleichzeitig verfügen viele Unternehmenskunden, mit der ich arbeite, über einen anderen (kleinen) Mandanten für IT-Lernen, -Tests und -Experimente. Der mandantenübergreifende Azure-Zugriff wird mit [Azure Faro erleichtert.](https://azure.microsoft.com/services/azure-lighthouse/) Office 365 und viele andere SaaS-Dienste haben Grenzwerte für mandantenübergreifende Szenarien. In Azure [AD B2B-Szenarien](/azure/active-directory/b2b/what-is-b2b) gibt es vieles zu berücksichtigen.

Viele Kunden haben nach einer Fusion und Übernahme (M&A) mehrere Produktions mandanten und möchten sich konsolidieren. Dies ist heute nicht einfach und würde Microsoft Consulting Services (MCS) oder einen Partner sowie Software von Drittanbietern erfordern. Es gibt fortlaufende technische Arbeiten, um verschiedene Szenarien mit Mandantenkunden in der Zukunft zu adressieren.

Einige Kunden entscheiden sich für mehr als einen Mandanten. Dies sollte eine sehr sorgfältige Entscheidung und fast immer geschäftsorientierter Grund sein! Beispiele hierfür sind:

- Eine Unternehmensstruktur des Holdingtyps, bei der keine einfache Zusammenarbeit zwischen verschiedenen Entitäten erforderlich ist und starke administrative und andere Isolationsanforderungen erfüllt sind.
- Nach einem Kauf wird eine Geschäftliche Entscheidung getroffen, zwei Entitäten voneinander getrennt zu halten.
- Simulation der Umgebung eines Kunden, die die Produktionsumgebung des Kunden nicht ändert. 
- Entwicklung von Software für Kunden.

In diesen szenarien mit mehreren Mandanten möchten Kunden häufig eine Konfiguration mandantenübergreifend gleich halten oder Konfigurationsänderungen und -driften melden. Dies bedeutet häufig, dass von manuellen Änderungen zur Konfiguration als Code wechselt. Microsoft -Support bietet einen Workshop für diese Arten von Anforderungen basierend auf dieser öffentlichen IP: [https://Microsoft365dsc.com](https://Microsoft365dsc.com) .

### <a name="multi-geo"></a>Multi-Geo

Für [Multi-Geo](../enterprise/microsoft-365-multi-geo.md) oder nicht für Multi-Geo ist dies die Frage. Mit Office 365 Multi-Geo können Sie Ruhedaten an den geografischen Standorten bereitstellen und speichern, die Sie ausgewählt haben, um die Anforderungen an die Datenresidenz [zu](../enterprise/o365-data-locations.md) erfüllen. Es gibt viele falsche Vorstellungen zu dieser Funktion. Denken Sie dabei an Folgendes:

- Es bietet keine Leistungsvorteile. Die Leistung kann schlechter werden, wenn der [Netzwerkentwurf](https://aka.ms/office365networking) nicht korrekt ist. Holen Sie Geräte "nah" an das Microsoft-Netzwerk, nicht unbedingt an Ihre Daten.
- Es ist keine Lösung für die Einhaltung der [DSGVO.](https://www.microsoft.com/trust-center/privacy/gdpr-overview) Die DSGVO konzentriert sich nicht auf Datenhoheit oder Speicherorte. Dafür gibt es andere Complianceframeworks.
- Die Delegierung der Verwaltung (siehe unten) oder Informationsbarrieren [wird nicht gelöst.](../compliance/information-barriers.md)
- Es ist nicht identisch mit mehr mandanten- und erfordert zusätzliche [Benutzerbereitstellungsworkflows.](https://github.com/MicrosoftDocs/azure-docs-pr/blob/master/articles/active-directory/hybrid/how-to-connect-sync-feature-preferreddatalocation.md)
- Es verschiebt [Ihren Mandanten](../enterprise/moving-data-to-new-datacenter-geos.md) (Azure AD) nicht in eine andere Geografie. 

## <a name="delegation-of-administration"></a>Delegierung der Verwaltung

In den meisten großen Organisationen ist die Trennung von Aufgaben und der rollenbasierten Zugriffssteuerung (RBAC) eine notwendige Realität. Ich möchte mich im Voraus entschuldigen. Dies ist nicht so einfach, wie es einige Kunden wünschen. Kunden-, Rechts-, Compliance- und andere Anforderungen unterscheiden sich und sind manchmal auf der ganzen Welt widersprüchlich. Einfachheit und Flexibilität befinden sich häufig auf den gegenüberliegenden Seiten. Machen Sie mich nicht falsch, wir können hier einen besseren Job machen. Im Laufe der Zeit wurden (und werden) erhebliche Verbesserungen vorgenommen. Besuchen Sie Ihr [lokales Microsoft Technology Center,](https://www.microsoft.com/mtc) um das Modell zu erstellen, das Ihren Geschäftlichen Anforderungen entspricht, ohne 379230-Dokumente zu lesen! Hier fokussiere ich mich auf das, was Sie denken sollten, und nicht, warum es so ist. Im Folgenden sind fünf verschiedene Bereiche aufgeführt, für die ich planen soll, und einige der häufig gestellten Fragen.

### <a name="azure-ad-and-microsoft-365-admin-centers"></a>Azure AD und Microsoft 365 Admin Center

Es gibt eine lange und wachsende Liste von [integrierten Rollen.](/azure/active-directory/users-groups-roles/directory-assign-admin-roles) Jede Rolle besteht aus einer Liste von Rollenberechtigungen, die in einer Gruppe aufgeführt sind, damit bestimmte Aktionen ausgeführt werden können. Diese Berechtigungen werden in jeder Rolle auf der Registerkarte "Beschreibung" angezeigt. Alternativ können Sie eine besser lesbare Version dieser Versionen im Microsoft 365 Admin Center sehen. Die Definitionen für integrierte Rollen können nicht geändert werden. Im Allgemeinen werden diese in drei Kategorien unterteilt:

- **Globaler Administrator:** Diese "alle leistungsstarken" Rolle sollte genau wie in anderen Systemen stark geschützt sein. [](../enterprise/protect-your-global-administrator-accounts.md) Typische Empfehlungen sind: keine dauerhafte Zuweisung und Verwendung von Azure AD Privileged Identity Management (PIM); starke Authentifizierung; Und so weiter. Interessanterweise bietet ihnen diese Rolle standardmäßig keinen Zugriff auf alles. In der Regel sehe ich Verwirrung über den Compliancezugriff und den Azure-Zugriff, der später behandelt wird. Diese Rolle kann jedoch immer Zugriff auf andere Dienste im Mandanten zuweisen. 
- **Bestimmte Dienstadministratoren:** Einige Dienste (Exchange, SharePoint, Power BI und so weiter) nutzen Verwaltungsrollen auf hoher Ebene aus Azure AD. Dies ist nicht für alle Dienste konsistent, und es werden später weitere dienstspezifische Rollen behandelt.
- **Funktional**: Es gibt eine lange (und wachsende) Liste von Rollen, die sich auf bestimmte Vorgänge (Gast einladend, und so weiter) konzentrieren. In regelmäßigen Abständen werden mehr davon basierend auf kundenbezogenen Anforderungen hinzugefügt.

Es ist nicht möglich, alles zu delegieren (obwohl die Lücke abnimmt), was bedeutet, dass die rolle des globalen Administrators manchmal verwendet werden müsste. Configuration-as-Code und Automatisierung sollten anstelle der Personenmitgliedschaft dieser Rolle berücksichtigt werden.

**Hinweis:** Das Microsoft 365 Admin Center verfügt über eine benutzerfreundlichere Benutzeroberfläche, verfügt aber im Vergleich zur Azure AD-Administratorerfahrung über eine Teilmenge der Funktionen. Beide Portale verwenden dieselben Azure AD-Rollen, sodass Änderungen an derselben Stelle vorgenommen werden. Tipp: Wenn Sie eine identitätsverwaltungsorientierte Administratorbenutzeroberfläche ohne alle Azure-Unübersichtlichkeiten wünschen, verwenden Sie [https://aad.portal.azure.com](https://aad.portal.azure.com) . 

Was ist im Namen? Machen Sie keine Annahmen aus dem Namen der Rolle. Sprache ist kein sehr präzises Tool. Das Ziel sollte es sein, Vorgänge zu definieren, die delegiert werden müssen, bevor sie sich mit den erforderlichen Rollen abm nnen. Wenn Sie jemanden zur Rolle "Security Reader" hinzufügen, werden die Sicherheitseinstellungen nicht in allen Fällen angezeigt.

Die Möglichkeit, benutzerdefinierte [Rollen zu erstellen,](/azure/active-directory/users-groups-roles/roles-custom-overview) ist eine häufige Frage. Dies ist in Azure AD heute begrenzt (siehe unten), wird jedoch im Laufe der Zeit an Funktionen zunehmen. Ich halte diese für anwendbar für Funktionen in Azure AD und kann das Hierarchiemodell nicht "unten" (oben erläutert) umfassen. Immer wenn ich mich mit "benutzerdefinierten" begeh", gehe ich zu meinem Prinzipal "Einfach ist besser" zurück.

Eine weitere häufige Frage ist die Möglichkeit, Rollen auf eine Teilmenge eines Verzeichnisses zu beschränken. Ein Beispiel ist "Helpdeskadministrator nur für Benutzer in der EU". [Administrative Einheiten](/azure/active-directory/users-groups-roles/directory-administrative-units) (AU) sind dafür vorgesehen. Wie oben halte ich diese für anwendbar für Funktionen in Azure AD und kann nicht "unten" umfassen. Natürlich sind bestimmte Rollen für den Bereich nicht sinnvoll (globale Administratoren, Dienstadministratoren und so weiter).

Heute erfordern alle diese Rollen eine direkte Mitgliedschaft (oder dynamische Zuweisung, wenn Sie [Azure AD PIM verwenden).](/azure/active-directory/privileged-identity-management/) Dies bedeutet, dass Kunden diese direkt in Azure AD verwalten müssen, und diese können nicht auf einer Sicherheitsgruppenmitgliedschaft basieren. Ich bin kein Fan des Erstellens von Skripts, um diese zu verwalten, da es mit erhöhten Rechten ausgeführt werden müsste. I generally recommend API integration with process systems like ServiceNow or using partner governance tools like Saviynt. Dies wird im Laufe der Zeit von der Technischen Arbeit an orts- und ortssind.

Ich habe [Azure AD PIM ein](/azure/active-directory/privileged-identity-management/) paar Mal erwähnt. Es gibt eine entsprechende Microsoft Identity Manager (MIM) [Privileged Access Management](/microsoft-identity-manager/pam/privileged-identity-management-for-active-directory-domain-services) (PAM)-Lösung für lokale Steuerelemente. Möglicherweise möchten Sie auch privileged [Access Workstations](/windows-server/identity/securing-privileged-access/privileged-access-workstations) (PAWs) und [Azure AD Identity Governance überprüfen.](/azure/active-directory/governance/identity-governance-overview) Es gibt auch verschiedene Tools von Drittanbietern, die just-in-time, just-enough und dynamic role elevation ermöglichen können. Dies ist in der Regel Teil einer größeren Diskussion zum Sichern einer Umgebung. 

Manchmal wird in Szenarien das Hinzufügen eines externen Benutzers zu einer Rolle (siehe Abschnitt mit mehreren Mandanten oben) erforderlich. Dies funktioniert einfach gut. [Azure AD B2B ist ein](/azure/active-directory/b2b/) weiteres großes und unterhaltsames Thema, mit dem Kunden, z. B. in einem anderen Artikel, durch die Kunden gehen können.

### <a name="security-and-compliance-center-scc"></a>Security and Compliance Center (SCC)

[Berechtigungen im Office 365 Security & Compliance Center](../security/office-365-security/permissions-in-the-security-and-compliance-center.md) sind eine Sammlung von "Rollengruppen", die sich von Azure AD-Rollen unterscheiden. Dies kann verwirrend sein, da einige dieser Rollengruppen denselben Namen wie Azure AD-Rollen haben (z. B. Security Reader), aber sie können unterschiedliche Mitgliedschaften haben. Ich bevorzuge die Verwendung von Azure AD-Rollen. Jede Rollengruppe besteht aus einer oder mehreren "Rollen" (siehe was ich meine, um dasselbe Wort wieder zu verwenden?) und mitglieder aus Azure AD, d. h. E-Mail-aktivierte Objekte. Außerdem können Sie eine Rollengruppe mit demselben Namen wie eine Rolle erstellen, die diese Rolle enthalten kann oder nicht (vermeiden Sie diese Verwirrung).

In gewissem Sinne sind dies eine Weiterentwicklung des Exchange-Rollengruppenmodells. Exchange Online verfügt jedoch über eine eigene [Rollengruppenverwaltungsschnittstelle.](/exchange/permissions-exo) Einige Rollengruppen in Exchange Online werden von Azure AD oder dem Security & Compliance Center gesperrt und verwaltet, andere haben möglicherweise dieselben oder ähnliche Namen und werden in Exchange Online verwaltet (was zur Verwirrung führt). Es wird empfohlen, die Verwendung der Exchange Online-Benutzeroberfläche zu vermeiden, es sei denn, Sie benötigen Bereiche für die Exchange-Verwaltung.

Sie können keine benutzerdefinierten Rollen erstellen. Rollen werden durch von Microsoft erstellte Dienste definiert und werden mit der Einführung neuer Dienste zunehmen. Dies ist im Konzept mit Rollen [vergleichbar, die von Anwendungen](/azure/active-directory/develop/howto-add-app-roles-in-azure-ad-apps) in Azure AD definiert werden. Wenn neue Dienste aktiviert sind, müssen häufig neue Rollengruppen erstellt werden, um diesen Zugriff zu gewähren oder zu delegieren (z. B. [Insider risk management](../compliance/insider-risk-management-configure.md?view=o365-worldwide#step-1-required-enable-permissions-for-insider-risk-management)).

Diese Rollengruppen erfordern auch eine direkte Mitgliedschaft und können keine Azure AD-Gruppen enthalten. Leider werden diese Rollengruppen heute nicht von Azure AD PIM unterstützt. Wie Azure AD-Rollen empfehle ich die Verwaltung dieser Rollen über APIs oder ein Partner-Governance-Produkt wie Saviynt oder andere.

Security & Compliance Center-Rollen umfassen Microsoft 365, und Sie können diese Rollengruppen nicht auf eine Teilmenge der Umgebung beschränken (z. B. mit administrativen Einheiten in Azure AD). Viele Kunden fragen, wie sie subdelegate werden können. Beispiel: "Erstellen Sie eine DLP-Richtlinie nur für BENUTZER in der EU." Wenn Sie heute im Security & Compliance Center Über Rechte an einer bestimmten Funktion haben, haben Sie Rechte an allem, was von dieser Funktion im Mandanten abgedeckt wird. Viele Richtlinien verfügen jedoch über Funktionen für eine Teilmenge der Umgebung (z. B. "Diese Bezeichnungen nur [für](../compliance/create-sensitivity-labels.md#publish-sensitivity-labels-by-creating-a-label-policy) diese Benutzer verfügbar machen"). Eine ordnungsgemäße Steuerung und Kommunikation sind eine wichtige Komponente, um Konflikte zu vermeiden. Einige Kunden entscheiden sich für die Implementierung eines Ansatzes "Konfiguration als Code", um die Unterdelegation im Security & Compliance Center zu adressieren. Einige bestimmte Dienste unterstützen die Unterdelegation (siehe unten).

Es ist erwähnenswert, dass steuerelemente, die derzeit über das Security & Compliance Center (protection.office.com) verwaltet werden, zu zwei separaten Administratorportalen migriert werden: security.microsoft.com und compliance.microsoft.com. Change ist die einzige Konstante!

### <a name="service-specific"></a>Dienstspezifisch

Wie bereits erwähnt, suchen viele Kunden nach einem differenzierteren Delegierungsmodell. Ein gängiges Beispiel: "Manage XYZ service only for Division X users and locations" (oder eine andere Dimension). Die Möglichkeit dazu hängt von jedem Dienst ab und ist nicht für alle Dienste und Funktionen konsistent. Darüber hinaus kann jeder Dienst über ein separates und eindeutiges RBAC-Modell verfügen. Anstatt all diese Themen zu besprechen (es dauert für immer), möchte ich relevante Links für jeden Dienst hinzufügen. Dies ist keine vollständige Liste, aber Sie können damit beginnen.

- **Exchange Online** - [https://docs.microsoft.com/exchange/permissions-exo/permissions-exo](/exchange/permissions-exo/permissions-exo) 
- **SharePoint Online** - [https://docs.microsoft.com/sharepoint/manage-site-collection-administrators](/sharepoint/manage-site-collection-administrators) 
- **Microsoft Teams**  -  [https://docs.microsoft.com/microsoftteams/itadmin-readiness](/microsoftteams/itadmin-readiness)
- **eDiscovery** - [https://docs.microsoft.com/microsoft-365/compliance/assign-ediscovery-permissions](../compliance/index.yml) 
  + **Berechtigungsfilterung**  -  [https://docs.microsoft.com/microsoft-365/compliance/permissions-filtering-for-content-search](../compliance/index.yml)
  + **Compliancegrenzen**  -  [https://docs.microsoft.com/microsoft-365/compliance/set-up-compliance-boundaries](../compliance/set-up-compliance-boundaries.md)
  + **Advanced eDiscovery**  -  [https://docs.microsoft.com/microsoft-365/compliance/overview-ediscovery-20](../compliance/overview-ediscovery-20.md)
- **Yammer** - [https://docs.microsoft.com/yammer/manage-yammer-users/manage-yammer-admins](/yammer/manage-yammer-users/manage-yammer-admins) 
- **Multi-Geo** - [https://docs.microsoft.com/microsoft-365/enterprise/add-a-sharepoint-geo-admin](../enterprise/add-a-sharepoint-geo-admin.md) 
- **Dynamics 365** – [https://docs.microsoft.com/dynamics365/](/dynamics365/) <br>
  Hinweis: Dieser Link befindet sich im Stammverzeichnis der Dokumentation. Es gibt mehrere Arten von Diensten mit Variationen im Administrator-/Delegierungsmodell.
- **Power Platform**  -  [https://docs.microsoft.com/power-platform/admin/admin-documentation](/power-platform/admin/admin-documentation)
  + **Power Apps**  -  [https://docs.microsoft.com/power-platform/admin/wp-security](/power-platform/admin/wp-security) <br>
    Hinweis: Es gibt mehrere Typen mit Variationen in den Verwaltungs-/Delegierungsmodellen.
  + **Power Automate**  -  [https://docs.microsoft.com/power-automate/environments-overview-admin](/power-automate/environments-overview-admin)
  + **Power BI**  -  [https://docs.microsoft.com/power-bi/service-admin-governance](/power-bi/service-admin-governance) <br>
Hinweis: Sicherheit und Delegierung der Datenplattform (power BI ist eine Komponente) ist ein komplexer Bereich.
- **MEM/Intune**  -  [https://docs.microsoft.com/mem/intune/fundamentals/role-based-access-control](/mem/intune/fundamentals/role-based-access-control)
- **Microsoft Defender for Endpoint**  -  [https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/user-roles](/windows/security/threat-protection/microsoft-defender-atp/user-roles)
- **Microsoft 365 Defender** - [https://docs.microsoft.com/microsoft-365/security/mtp/mtp-permissions](../security/mtp/mtp-permissions.md)
- **Microsoft Cloud App Security** - [https://docs.microsoft.com/cloud-app-security/manage-admins](/cloud-app-security/manage-admins)
- **Stream**  -  [https://docs.microsoft.com/stream/assign-administrator-user-role](/stream/assign-administrator-user-role)
- **Informationsbarrieren**  -  [https://docs.microsoft.com/microsoft-365/compliance/information-barriers](../compliance/information-barriers.md)

Im Übrigen war die Suche in Docs in letzter Zeit wirklich gut – [https://docs.microsoft.com/](../compliance/information-barriers.md) . 

### <a name="activity-logs"></a>Aktivitätsprotokolle

Office 365 verfügt über ein [einheitliches Überwachungsprotokoll](../compliance/search-the-audit-log-in-security-and-compliance.md). Es ist ein sehr [detailliertes Protokoll,](/office/office-365-management-api/office-365-management-activity-api-schema)aber lesen Sie nicht zu viel in den Namen ein. Es enthält möglicherweise nicht alles, was Sie für Ihre Sicherheits- und Complianceanforderungen benötigen. Außerdem sind einige Kunden wirklich an advanced [Audit interessiert.](../compliance/advanced-audit.md)

Beispiele für Microsoft 365-Protokolle, auf die über andere APIs zugegriffen wird, sind:

- [Azure AD](/azure/azure-monitor/platform/diagnostic-settings) (Aktivitäten, die nicht mit Office 365 in Zusammenhang stehen)
- [Exchange-Nachrichtenverfolgung](/powershell/module/exchange/get-messagetrace)
- Oben beschriebene Bedrohungs-/UEBA-Systeme (z. B. Azure AD Identity Protection, Microsoft Cloud App Security, Microsoft Defender for Endpoint und so weiter)
- [Microsoft Information Protection](../compliance/data-classification-activity-explorer.md?view=o365-worldwide)
- [Microsoft Defender für Endpunkt](/windows/security/threat-protection/microsoft-defender-atp/api-power-bi)
- [Microsoft Graph](https://graph.microsoft.com)

Es ist wichtig, zunächst alle Protokollquellen zu identifizieren, die für ein Sicherheits- und Complianceprogramm erforderlich sind. Beachten Sie außerdem, dass unterschiedliche Protokolle unterschiedliche Onlineaufbewahrungsgrenzwerte haben. 

Aus Sicht der Administratordelegierung verfügen die meisten Microsoft 365-Aktivitätsprotokolle nicht über ein integriertes RBAC-Modell. Wenn Sie über die Berechtigung zum Sehen eines Protokolls verfügen, können Sie alles in diesem Protokoll sehen. Ein gängiges Beispiel für eine Kundenanforderung ist: "Ich möchte aktivitäten nur für BENUTZER in der EU abfragen können" (oder eine andere Dimension). Um diese Anforderung zu erfüllen, müssen wir Protokolle an einen anderen Dienst übertragen. In der Microsoft Cloud wird empfohlen, sie entweder auf [Azure Sentinel oder](/azure/sentinel/overview) Log Analytics zu [übertragen.](/azure/azure-monitor/learn/quick-create-workspace) 

Diagramm auf hoher Ebene:

![Diagramm der Protokollquellen für ein Sicherheits- und Complianceprogramm](../media/solutions-architecture-center/identity-beyond-illustration-4.png)  

Das obige Diagramm stellt integrierte Funktionen zum Senden von Protokollen an Event Hub und/oder Azure Storage und/oder Azure Log Analytics dar. Noch nicht alle Systeme enthalten dieses out-of-the-box-System. Es gibt jedoch andere Ansätze zum Senden dieser Protokolle an dasselbe Repository. Weitere Informationen finden Sie unter [Protecting your Teams with Azure Sentinel](https://techcommunity.microsoft.com/t5/azure-sentinel/protecting-your-teams-with-azure-sentinel/ba-p/1265761).

Die Kombination aller Protokolle in einem Speicherort bietet zusätzliche Vorteile, z. B. Korrelationen, benutzerdefinierte Aufbewahrungszeiten, die Erweiterung mit Daten, die zur Unterstützung des RBAC-Modells erforderlich sind, und so weiter. Sobald sich Daten in diesem Speichersystem befindet, können Sie ein Power BI-Dashboard (oder eine andere Art von Visualisierung) mit einem geeigneten RBAC-Modell erstellen.

Protokolle müssen nicht nur an einen Ort geleitet werden. Es kann auch von Vorteil sein, [Office 365-Protokolle in Microsoft Cloud App Security](/cloud-app-security/connect-office-365-to-microsoft-cloud-app-security) oder ein benutzerdefiniertes RBAC-Modell in Power BI zu [integrieren.](../admin/usage-analytics/usage-analytics.md?view=o365-worldwide) Unterschiedliche Repositorys haben unterschiedliche Vorteile und Zielgruppen.

Es ist erwähnenswert, dass es ein sehr umfangreiches integriertes Analysesystem für Sicherheit, Bedrohungen, Sicherheitsrisiken und so weiter in einem Dienst namens [Microsoft 365 Defender gibt.](../security/mtp/microsoft-threat-protection.md?view=o365-worldwide)

Viele große Kunden möchten diese Protokolldaten an ein Drittanbietersystem (z. B. SIEM) übertragen. Dafür gibt es unterschiedliche Ansätze, aber im Allgemeinen [sind Azure Event Hub](/azure/azure-monitor/platform/stream-monitoring-data-event-hubs) und [Graph](/graph/security-integration) gute Ausgangspunkte.

### <a name="azure"></a>Azure

Ich werde häufig gefragt, ob es eine Möglichkeit gibt, Rollen mit hohen Rechten zwischen Azure AD, Azure und SaaS zu trennen (z. B.: Globaler Administrator für Office 365, jedoch nicht Azure).  Nicht wirklich.  Die Architektur mit mehreren Mandanten ist erforderlich, wenn eine vollständige administrative Trennung erforderlich ist, was jedoch zu einer erheblichen Komplexität [führt](https://aka.ms/multi-tenant-user) (siehe oben). Alle diese Dienste sind Teil der gleichen Sicherheits-/Identitätsgrenze (siehe oben im Hierarchiemodell).  

Es ist wichtig, die Beziehungen zwischen verschiedenen Diensten im gleichen Mandanten zu verstehen. Ich arbeite mit vielen Kunden zusammen, die Geschäftslösungen entwickeln, die Azure, Office 365 und Power Platform umfassen (und häufig auch lokale und Clouddienste von Drittanbietern). Ein häufiges Beispiel:

1. Ich möchte an einer Reihe von Dokumenten/Bildern/usw. zusammenarbeiten (Office 365)
2. Senden sie alle über einen Genehmigungsprozess (Power Platform)
3.  Nachdem alle Komponenten genehmigt wurden, können Sie diese zu einer einheitlichen Bereitstellungs-API (Azure) [zusammenstellen.](/azure/active-directory/develop/microsoft-graph-intro)  Nicht unmöglich, aber wesentlich komplexer, um eine Lösung zu entwerfen, die mehrere [Mandanten umfasst.](/azure/active-directory/develop/single-and-multi-tenant-apps)

Azure Role-Based Access Control (RBAC) ermöglicht eine feinkörnige Zugriffsverwaltung für Azure. Mithilfe von RBAC können Sie den Zugriff auf Ressourcen verwalten, indem Sie Benutzern die wenigsten Berechtigungen erteilen, die zum Ausführen ihrer Aufträge erforderlich sind. Details sind für dieses Dokument nicht verfügbar, weitere Informationen zur RBAC finden Sie unter Was ist rollenbasierte Zugriffssteuerung [(RBAC) in Azure?](/azure/role-based-access-control/overview) RBAC ist wichtig, aber nur Teil der Überlegungen zur Steuerung für Azure. [Cloud Adoption Framework](/azure/cloud-adoption-framework/govern/) ist ein guter Ausgangspunkt, um mehr zu erfahren. Ich mag, wie mein Freund Andres Ravinet Kunden Schritt für Schritt durch verschiedene Komponenten führt, um sich für den Ansatz zu entscheiden. Die Ansicht auf hoher Ebene für verschiedene Elemente (nicht so gut wie der Prozess, um zum tatsächlichen Kundenmodell zu kommen) ist etwa wie folgt:

![Ansicht auf hoher Ebene von Azure-Komponenten für delegierte Verwaltung](../media/solutions-architecture-center/identity-beyond-illustration-5.png)

Wie Sie oben sehen können, sollten viele andere Dienste als Teil des Entwurfs berücksichtigt werden (z. B.: [Azure Policies](/azure/governance/policy/overview), [Azure Blueprints](/azure/governance/blueprints/overview), [Management Groups](/azure/governance/management-groups/)und so weiter).

## <a name="conclusion"></a>Schlussbemerkung

Als kurze Zusammenfassung gestartet, endete länger als erwartet.  Ich hoffe, Dass Sie jetzt bereit sind, einen tiefen Einblick in die Erstellung eines Delegierungsmodells für Ihre Organisation zu wagen.  Diese Unterhaltung ist bei Kunden sehr häufig. Es gibt kein Modell, das für alle funktioniert. Warten Sie auf einige geplante Verbesserungen von Microsoft Engineering, bevor Sie allgemeine Muster dokumentieren, die wir kundenübergreifend sehen. In der Zwischenzeit können Sie mit Ihrem Microsoft-Kontoteam zusammenarbeiten, um einen Besuch im nächstgelegenen [Microsoft Technology Center zu organisieren.](https://www.microsoft.com/mtc)  Sehen Sie sich dort an!