---
title: Zur Identität und darüber hinaus – ein Architektur Standpunkt
description: Eine Beschreibung.
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
ms.custom: ''
f1.keywords: NOCSH
ms.openlocfilehash: 99112b70715770b24c1454fbd9442d2b5b6f08ea
ms.sourcegitcommit: 89636f35b0194986f156302fc1bb96af25d4805b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/18/2020
ms.locfileid: "44800131"
---
# <a name="to-identity-and-beyond--one-architects-viewpoint"></a>Zur Identität und darüber hinaus – ein Architektur Standpunkt

In diesem Artikel werden die wichtigsten Entwurfsstrategien für Unternehmensorganisationen, die Microsoft 365 und andere Microsoft Cloud-Dienste annehmen, von [Alex Shteynberg](https://www.linkedin.com/in/alex-shteynberg/), Principal Technical Architect bei Microsoft, erläutert.

## <a name="about-the-author"></a>Über den Autor

:::image type="content" source="../media/solutions-architecture-center/identity-and-beyond-alex-shteynberg.jpg" alt-text="Alex Shteynberg Foto":::

Ich bin Principal Technical Architect im New York [Microsoft Technology Center](https://www.microsoft.com/mtc?rtc=1). Ich arbeite meistens mit großen Kunden und komplexen Anforderungen. Meine Ansichten und Meinungen basieren auf diesen Interaktionen und gelten möglicherweise nicht für jede Situation. Wenn wir jedoch Kunden bei den komplexesten Herausforderungen helfen können, können wir allen Kunden helfen. 

Ich arbeite normalerweise jedes Jahr mit 100 + Kunden zusammen. Während jede Organisation eindeutige Merkmale aufweist, ist es interessant, Trends und Gemeinsamkeiten zu sehen. Ein Trend ist beispielsweise ein branchenübergreifendes Interesse für viele Kunden. Schließlich kann eine Bankfiliale auch ein Coffee Shop und ein Community Center sein. 

In meiner Rolle konzentriere ich mich darauf, Kunden bei der Ankunft der besten technischen Lösung zu unterstützen, um Ihre eindeutigen Unternehmensziele zu erfüllen. Offiziell konzentriere ich mich auf Identität, Sicherheit, Datenschutz und Compliance. Ich liebe die Tatsache, dass diese alles, was wir tun, berühren. Es gibt mir die Möglichkeit, mit den meisten Projekten beteiligt zu sein. Dies hält mich sehr beschäftigt und genießt diese Rolle. 

Ich lebe in New York City (The Best!) und genieße wirklich die Vielfalt seiner Kultur, Lebensmittel und Menschen (kein Verkehr). Ich liebe es zu reisen, wenn ich den Großteil der Welt in meinem Leben sehen kann und hoffe. Ich recherchiere derzeit eine Reise nach Afrika, um mehr über Wildlife zu erfahren.

## <a name="guiding-principles"></a>Leitlinien 

- **Einfach ist häufig besser** – Sie können (fast) nichts mit Technologie tun. Dies bedeutet nicht, dass Sie dies sollten. Vor allem im Sicherheitsbereich bieten viele Kunden Lösungen für overengineer. Ich mag [dieses Video](https://www.youtube.com/watch?v=SOQgABDSYZE) von der Stripe-Konferenz von Google, um diesen Punkt zu unterstreichen.
- **People, Process, Technology** – [Design für Personen](https://en.wikipedia.org/wiki/Human-centered_design) zur Verbesserung des Prozesses, nicht für Tech First. Es gibt keine "perfekten" Lösungen. Wir müssen verschiedene Risikofaktoren abgleichen, und Entscheidungen werden für jedes Unternehmen unterschiedlich sein. Zu viele Kunden entwerfen eine Herangehensweise, die Ihre Benutzer später vermeiden.
- **Konzentrieren Sie sich zunächst auf "Warum" und "wie" später** – seien Sie das lästige 7 yr old Kid mit einer Million Fragen. Wir können nicht zur richtigen Antwort gelangen, wenn wir nicht die richtigen Fragen kennen, die Sie stellen müssen. Viele Kunden machen Annahmen darüber, wie Dinge funktionieren müssen, anstatt das Geschäftsproblem zu definieren. Es gibt immer mehrere Pfade, die ausgeführt werden können.
- **Long Tail of Past Best Practices** – erkennen Sie, dass sich bewährte Methoden bei schwacher Geschwindigkeit ändern. Wenn Sie Azure AD vor mehr als drei Monaten betrachtet haben, sind Sie wahrscheinlich veraltet. Alle hier unterliegen Änderungen nach der Veröffentlichung. "Beste" Option heute möglicherweise nicht die gleichen 6 Monate ab jetzt.

## <a name="baseline-concepts"></a>Grundlegende Konzepte

Überspringen Sie diesen Abschnitt nicht. Ich finde häufig, dass ich zu diesen Themen zurückkehren muss, selbst für Kunden, die seit Jahren Cloud-Dienste verwenden.
Leider ist Sprache kein präzises Tool. Wir verwenden häufig das gleiche Wort, um verschiedene Konzepte oder andere Wörter zu verstehen, die dasselbe Konzept bedeuten. Ich verwende häufig dieses Diagramm unten, um eine grundlegende Terminologie und ein "Hierarchiemodell" festzulegen.
<br><br>

![Abbildung des Mandanten, des Abonnements, des Diensts und der Daten](../media/solutions-architecture-center/Identity-and-beyond-tenant-level.png)  

<br>

Wenn Sie schwimmen lernen, ist es besser, im Pool zu beginnen und nicht in der Mitte des Ozeans. Ich versuche nicht, technisch korrekt mit diesem Diagramm zu sein. Es handelt sich um ein Modell zur Erörterung einiger grundlegender Konzepte. 

Aus dem Diagramm geht Folgendes hervor:
- Mandant = eine Instanz von Azure AD. Sie befindet sich am oberen Rand einer Hierarchie oder Ebene 1 im Diagramm. Wir können dies als die "[Grenze](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-directory-independence)" bezeichnen, in der alles andere ([Azure AD B2B](https://docs.microsoft.com/azure/active-directory/b2b/what-is-b2b) beiseite) stattfindet. Alle Microsoft Enterprise Cloud-Dienste sind Teil eines dieser Mandanten. Consumer-Dienste sind getrennt. "Mandant" wird in der Dokumentation als Office 365 Mandanten, Azure-Mandanten, Oktober-Mandanten usw. angezeigt. Diese Variationen verursachen häufig Verwirrung für Kunden.
- Dienste/Abonnements, Ebene 2 im Diagramm, gehören nur einem Mandanten an. Die meisten Saas-Dienste sind 1:1 und können sich ohne Migration nicht mehr umsetzen. Azure unterscheidet, können Sie die Abrechnung und/oder ein [Abonnement](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-how-subscriptions-associated-directory) an einen anderen Mandanten [verlagern](https://docs.microsoft.com/azure/cost-management-billing/manage/billing-subscription-transfer) . Es gibt viele Kunden, die Azure-Abonnements migrieren müssen. Dies hat verschiedene Implikationen. Objekte, die sich außerhalb des Abonnements befinden (beispielsweise RBAC-und Azure AD-Objekte, einschließlich Gruppen, apps, Richtlinien usw.), werden nicht weitergegeben. Außerdem werden einige Dienste (Azure Key Vault, Daten Ziegel usw.) in einem nicht funktionalen Zustand verschoben. Migrieren Sie keine Dienste ohne eine gute geschäftliche Anforderung. Einige Skripts, die für die Migration hilfreich sein können, werden [auf GitHub freigegeben](https://github.com/lwajswaj/azure-tenant-migration). 
- Ein bestimmter Dienst hat in der Regel eine Art "unter Ebene"-Begrenzung oder Ebene 3 (L3). Dies ist hilfreich, um die Trennung von Sicherheit, Richtlinien, Steuerung usw. zu verstehen. Leider gibt es keinen einheitlichen Namen, von dem ich weiß. Einige Beispiele für die Namen von L3 sind: Azure Subscription = [Resource](https://docs.microsoft.com/azure/azure-resource-manager/management/manage-resources-portal); Dynamics 365 CE = [Instanz](https://docs.microsoft.com/dynamics365/admin/new-instance-management); Power BI = [Arbeitsbereich](https://docs.microsoft.com/power-bi/service-create-the-new-workspaces); Power apps = [Umgebung](https://docs.microsoft.com/power-platform/admin/environments-overview); usw.
- Ebene 4 ist der Ort, an dem die tatsächlichen Daten Leben. Diese "Datenebene" ist ein komplexes Thema. Einige Dienste verwenden Azure AD für RBAC, andere nicht. Ich werde es ein wenig besprechen, wenn wir zu Delegations Themen gelangen.

Einige zusätzliche Konzepte, bei denen ich viele Kunden (und Microsoft-Mitarbeiter) finde, sind verwirrt oder haben Fragen zu folgenden Themen:


- Jeder kann viele Mandanten [kostenlos](https://azure.microsoft.com/pricing/details/active-directory/) [Erstellen](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-access-create-new-tenant) . Sie benötigen keinen Dienst, der in der IT-Abteilung vorgesehen ist. Ich habe Dutzende. Jeder Mandantenname ist im globalen clouddienst von Microsoft eindeutig (keine zwei Mandanten können denselben Namen haben). Sie alle haben das Format TenantName.onmicrosoft.com. Es gibt auch Prozesse, die Mandanten automatisch erstellen ([nicht verwaltete Mandanten](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-self-service-signup)). Dies kann beispielsweise der Fall sein, wenn sich ein Benutzer für einen Enterprise-Dienst mit einer e-Mail-Domäne anmeldet, die in keinem anderen Mandanten vorhanden ist. 
- In einem verwalteten Mandanten können viele [DNS-Domänen](https://docs.microsoft.com/azure/active-directory/fundamentals/add-custom-domain) darin registriert werden. Dadurch wird der ursprüngliche Mandantenname nicht geändert. Es gibt derzeit keine einfache Möglichkeit, einen Mandanten umzubenennen (außer Migration). Obwohl der Mandantenname in diesen Tagen technisch gesehen nicht kritisch ist, kann es sein, dass einige dies einschränken.
- Sie sollten einen Mandantennamen für Ihre Organisation auch dann reservieren, wenn Sie noch nicht planen, Dienste bereitzustellen. Andernfalls kann ihn jemand von Ihnen übernehmen, und es gibt keinen einfachen Prozess, um ihn zurück zu nehmen (dasselbe Problem wie DNS-Namen). Ich höre diesen Weg zu oft von Kunden. Was Ihr Mandantenname sein sollte, ist auch ein Diskussionsthema.
- Wenn Sie einen eigenen DNS-Namespace (s) besitzen, sollten Sie all diese zu ihren Mandanten hinzufügen. Andernfalls könnte ein [nicht verwalteter Mandant](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-self-service-signup) mit diesem Namen erstellt werden, der dann Unterbrechungen verursacht, [sodass er verwaltet](https://docs.microsoft.com/azure/active-directory/users-groups-roles/domains-admin-takeover)wird.
- Der DNS-Namespace (beispielsweise contoso.com) kann nur einem Mandanten angehören. Dies hat Implikationen für verschiedene Szenarien (beispielsweise das Freigeben einer e-Mail-Domäne während einer Fusion oder eines Erwerbs usw.). Es gibt eine Möglichkeit, ein DNS-Sub (beispielsweise div.contoso.com) in einem anderen Mandanten zu registrieren, dies sollte jedoch vermieden werden. Wenn Sie einen Domänennamen der obersten Ebene registrieren, wird davon ausgegangen, dass alle Unterdomänen zum gleichen Mandanten gehören. In Szenarien mit mehreren Mandanten (siehe unten) würde ich normalerweise einen anderen Domänennamen der obersten Ebene (beispielsweise contoso.ch oder ch-contoso.com) empfehlen.
- Wer sollte ein Mandant "besitzen"? Ich sehe häufig Kunden, die nicht wissen, wer Ihren Mandanten derzeit besitzt. Dies ist eine große rote Fahne. Rufen Sie den Microsoft-Support ASaP an. Problematisch ist auch, wenn ein Dienstbesitzer (häufig ein Exchange-Administrator) zum Verwalten eines Mandanten bestimmt ist. Der Mandant enthält alle Dienste, die in Zukunft möglicherweise gewünscht werden. Der Mandanten Besitzer sollte eine Gruppe sein, die eine Entscheidung für die Aktivierung aller Cloud-Dienste in einer Organisation treffen kann. Ein weiteres Problem besteht darin, dass eine Mandanten Besitzer Gruppe zur Verwaltung aller Dienste aufgefordert wird. Dies wird für große Organisationen nicht skaliert.
- Es gibt kein Konzept eines Sub/Super-Mandanten. Aus irgendeinem Grund wird dieser Mythos sich immer wiederholt. Dies gilt auch für [Azure AD B2C](https://docs.microsoft.com/azure/active-directory-b2c/) -Mandanten. Ich höre zu viele Male: "meine B2C-Umgebung befindet sich in meinem XYZ-Mandanten" oder "Wie verschiebe ich meinen Azure-Mandanten in meinen Office 365 Mandanten?"
- Dieses Dokument konzentriert sich hauptsächlich auf die kommerzielle weltweite Cloud, da dies die meisten Kunden verwenden. Es ist manchmal nützlich, über [souveräne Wolken](https://docs.microsoft.com/azure/active-directory/develop/authentication-national-cloud)zu wissen. Souveräne Clouds weisen weitere Implikationen auf, die nicht im Rahmen dieser Diskussion liegen.


## <a name="baseline-identity-topics"></a>Grundlegende Identitäts Themen

Es gibt viele Dokumentationen zur Identitäts Plattform von Microsoft – Azure Active Directory (Azure AD). Für diejenigen, die gerade erst beginnen, fühlt es sich oft überwältigend an. Selbst nachdem Sie davon erfahren haben, kann es eine Herausforderung sein, mit ständiger Innovation und Veränderung Schritt zu halten. In meinen Kundeninteraktionen befinde ich mich häufig als "Übersetzer" zwischen Geschäftszielen und "gut, besser, am besten" Ansätzen, um diese zu adressieren (sowie menschliche "Klippen" für diese Themen). Es gibt selten eine perfekte Antwort, und die "richtige" Entscheidung ist eine Balance verschiedener Risikofaktoren. Im folgenden finden Sie einige der häufigsten Fragen und Verwirrungs Bereiche, die ich mit Kunden besprechen möchte.

### <a name="provisioning"></a>Bereitstellung
Azure AD löst sich nicht aufgrund fehlender Steuerung in Ihrer Identitäts Welt! Die [Identitäts Steuerung](https://docs.microsoft.com/azure/active-directory/governance/identity-governance-overview) sollte ein entscheidendes Element unabhängig von Cloud-Entscheidungen sein. Governance-Anforderungen ändern sich im Laufe der Zeit, weshalb es sich um ein Programm und kein Tool handelt. 

[Azure AD Connect](https://docs.microsoft.com/azure/active-directory/hybrid/whatis-azure-ad-connect) vs. [Microsoft Identity Manager](https://docs.microsoft.com/microsoft-identity-manager/microsoft-identity-manager-2016) (MIM) vs. Something Else (3rd Party oder Custom)? Sparen Sie sich eine Menge Kopfschmerzen jetzt und in Zukunft und gehen Sie mit Azure AD Connect. Es gibt alle Arten von Smarts in diesem Tool, um spezielle Kunden Konfigurationen und fortlaufende Innovationen zu adressieren. 

Einige Rand Fälle, die zu einer komplexeren Architektur führen können:
- Ich habe mehrere AD-Gesamtstrukturen ohne Netzwerkverbindung zwischen diesen. Es gibt eine neue Option, die als [Cloud](https://docs.microsoft.com/azure/active-directory/cloud-provisioning/what-is-cloud-provisioning)-Prothesen bezeichnet wird.
- Ich habe weder Active Directory noch möchte ich Sie installieren. Azure AD Connect kann konfiguriert werden, um [von LDAP zu synchronisieren](https://docs.microsoft.com/azure/active-directory/hybrid/plan-hybrid-identity-design-considerations-tools-comparison) (möglicherweise ist ein Partner erforderlich).
- Ich muss die gleichen Objekte für mehrere Mandanten zur Verfügung stellen. Dies wird technisch nicht unterstützt, hängt jedoch von der Definition von "gleich" ab.

Sollte ich die Standard Synchronisierungsregeln anpassen ([Filterobjekte](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-sync-configure-filtering), [Attribute ändern](https://docs.microsoft.com/azure/active-directory/hybrid/reference-connect-sync-attributes-synchronized), [Alternative Anmelde-ID](https://docs.microsoft.com/azure/active-directory/hybrid/plan-connect-userprincipalname)usw.)? Vermeiden Sie es! Eine Identitäts Plattform ist nur so wertvoll wie die Dienste, die Sie verwenden. Sie können zwar alle Arten von nussigen Konfigurationen ausführen, um diese Frage zu beantworten, müssen Sie sich jedoch mit den Auswirkungen auf Anwendungen befassen. Wenn Sie e-Mail-aktivierte Objekte filtern, ist die GAL für Onlinedienste unvollständig; Wenn die Anwendung bestimmte Attribute verwendet, hat die Filterung eine unvorhersehbare Auswirkung. usw. Es handelt sich nicht um eine Identitäts teamentscheidung.

Unterstützt XYZ-Saas die Just-in-time (JIT)-Vorgehensweise, warum müssen Sie mich synchronisieren? Siehe weiter oben. Viele Anwendungen benötigen "Profil"-Informationen für die Funktionalität. Sie können keine GAL haben, wenn alle e-Mail-aktivierten Objekte nicht verfügbar sind. Gleiches gilt für [Benutzer](https://docs.microsoft.com/azure/active-directory/app-provisioning/user-provisioning) Prothesen in Anwendungen, die in Azure AD integriert sind.


### <a name="authentication"></a>Authentifizierung

[Kennwort-Hash-Synchronisierung](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-password-hash-synchronization) (PHS) vs. [Pass-Through-Authentifizierung](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-pta-how-it-works) (PTA) vs. [Federation](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-fed-compatibility).

In der Regel gibt es eine leidenschaftliche [Debatte](https://docs.microsoft.com/azure/active-directory/hybrid/choose-ad-authn) um die Föderation. Einfacher ist normalerweise besser und verwendet daher PHS, es sei denn, Sie haben einen guten Grund. Es ist auch möglich, unterschiedliche Authentifizierungsmethoden für unterschiedliche DNS-Domänen in demselben Mandanten zu konfigurieren. 

Einige Kunden aktivieren Partnerverbund + PHS hauptsächlich für:
- Eine Option zum [zurückgreifen](https://docs.microsoft.com/azure/active-directory/hybrid/plan-migrate-adfs-password-hash-sync) auf (Notfallwiederherstellung), wenn der Verbunddienst nicht verfügbar ist.
- Zusätzliche Funktionen (z. b.: [Azure AD DS](https://docs.microsoft.com/azure/active-directory-domain-services/tutorial-configure-password-hash-sync)) und Sicherheitsdienste (z. b.: durch [gesickerte Anmeldeinformationen](https://docs.microsoft.com/azure/active-directory/reports-monitoring/concept-risk-events#leaked-credentials))
- Unterstützung für Dienste in Azure, die die Verbundauthentifizierung nicht verstehen (z. b.: [Azure-Dateien](https://docs.microsoft.com/azure/storage/files/storage-files-active-directory-overview)).

Ich gehe häufig Kunden durch den Client Authentifizierungs Fluss, um Missverständnisse zu verdeutlichen. Das Ergebnis sieht wie das folgende Bild aus, das nicht so gut wie der interaktive Prozess des Erhaltens ist.

:::image type="content" source="../media/solutions-architecture-center/identity-beyond-whiteboard-example.png" alt-text="Beispiel für Whiteboard-Unterhaltung":::

Diese Art von Whiteboard-Zeichnung veranschaulicht, wo Sicherheitsrichtlinien innerhalb des Ablaufs einer Authentifizierungsanforderung angewendet werden. In diesem Beispiel werden Richtlinien, die über Active Directory Verbunddienst (AD FS) erzwungen werden, auf die erste Dienstanforderung angewendet, jedoch nicht auf nachfolgende Dienstanforderungen. Dies ist mindestens ein Grund, um Sicherheitssteuerelemente so weit wie möglich in die Cloud zu versetzen.

Wir verfolgen den Traum von [einmaligem Anmelden (Single Sign-on](https://docs.microsoft.com/azure/active-directory/manage-apps/what-is-single-sign-on) , SSO), solange ich mich daran erinnern kann. Einige Kunden glauben, dass Sie dies erreichen können, indem Sie den Anbieter "Right" (STS) auswählen. Azure AD kann wesentlich dazu beitragen, SSO-Funktionen zu [aktivieren](https://docs.microsoft.com/azure/active-directory/manage-apps/plan-sso-deployment) , aber kein STS ist magisch. Es gibt zu viele "Legacy"-Authentifizierungsmethoden, die weiterhin für kritische Anwendungen verwendet werden. Das Erweitern von Azure AD mit [Partnerlösungen](https://docs.microsoft.com/azure/active-directory/saas-apps/tutorial-list) kann viele dieser Szenarien lösen. SSO ist eine Strategie und eine Reise. Sie können nicht dorthin gelangen, ohne auf [Standards für Anwendungen](https://docs.microsoft.com/azure/active-directory/develop/v2-app-types)zuzugehen. Im Zusammenhang mit diesem Thema finden Sie eine Reise zur [Kenn Wort](https://docs.microsoft.com/azure/active-directory/authentication/concept-authentication-passwordless) unsicheren Authentifizierung, die auch nicht über eine magische Antwort verfügt. 

[Mehrstufige Authentifizierung](https://docs.microsoft.com/azure/active-directory/authentication/concept-mfa-howitworks) (MFA) ist heute wesentlich ([hier](https://techcommunity.microsoft.com/t5/azure-active-directory-identity/your-pa-word-doesn-t-matter/ba-p/731984) für mehr). Fügen Sie der IT- [Benutzerverhaltens Analyse](https://docs.microsoft.com/azure/active-directory/authentication/tutorial-risk-based-sspr-mfa) hinzu, und Sie haben eine Lösung, die die meisten gängigen Cyber-Angriffe verhindert. Selbst Consumer-Dienste bewegen sich zu erfordern MFA. Dennoch bin ich immer noch mit vielen Kunden zusammengetroffen, die nicht zu [modernen Authentifizierungs](https://docs.microsoft.com/office365/enterprise/hybrid-modern-auth-overview) Ansätzen übergehen möchten. Das größte Argument, das ich höre, ist, dass es sich auf Benutzer und ältere Anwendungen auswirkt. Manchmal kann ein guter Kick Kunden dabei helfen, die Änderungen entlang Exchange Online [angekündigten Änderungen](https://techcommunity.microsoft.com/t5/exchange-team-blog/basic-auth-and-exchange-online-february-2020-update/ba-p/1191282)voranzubringen. Zahlreiche Azure AD [Berichte](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-block-legacy-authentication) stehen jetzt zur Verfügung, um Kunden bei dieser Umstellung zu unterstützen.



### <a name="authorization"></a>Authorization

Pro [Wikipedia](https://en.wikipedia.org/wiki/Authorization)"zu autorisieren" ist das Definieren einer Zugriffsrichtlinie. Viele Menschen betrachten Sie als die Möglichkeit, Zugriffssteuerelemente auf ein Objekt (Datei, Dienst usw.) zu definieren. In der aktuellen Welt der Cyber-Bedrohungen entwickelt sich dieses Konzept schnell zu einer dynamischen Richtlinie, die auf verschiedene Bedrohungs Vektoren reagieren und die Zugriffssteuerungen als Reaktion auf diese schnell anpassen kann. Wenn ich beispielsweise von einem ungewöhnlichen Standort auf mein Bankkonto zuzugreifen, erhalte ich zusätzliche Bestätigungsschritte. Um dies zu erreichen, müssen wir nicht nur die Richtlinie selbst, sondern auch das Ökosystem der Erkennung von Bedrohungen und Signal Korrelations Methoden in Frage stellen.

Das Richtlinienmodul von Azure AD wird mithilfe von [Richtlinien für bedingten Zugriff](https://docs.microsoft.com/azure/active-directory/conditional-access/overview)implementiert. Dieses System hängt von Informationen aus einer Vielzahl anderer Systeme zur Erkennung von Bedrohungen ab, um dynamische Entscheidungen zu treffen. Eine einfache Ansicht wäre wie in der folgenden Abbildung dargestellt.

:::image type="content" source="../media/solutions-architecture-center/identity-and-beyond-illustration-3.png" alt-text="Richtlinienmodul in Azure AD":::

Wenn Sie alle diese Signale miteinander kombinieren, können Sie dynamische Richtlinien wie die folgenden zusammenfassen:
- Wenn auf Ihrem Gerät eine Bedrohung erkannt wird, wird der Zugriff auf die Daten nur dann auf das Internet reduziert, wenn Sie nicht heruntergeladen werden können.
- Wenn Sie eine ungewöhnlich hohe Datenmenge herunterladen, werden alle von Ihnen heruntergeladenen Daten verschlüsselt und eingeschränkt.
- Wenn Sie über ein nicht verwaltetes Gerät auf einen Dienst zugreifen, werden Sie von hoch vertraulichen Daten blockiert, können jedoch auf nicht eingeschränkte Daten zugreifen, ohne Sie an einen anderen Speicherort kopieren zu können.

Wenn Sie mit dieser erweiterten Definition der Autorisierung einverstanden sind, müssen Sie zusätzliche Lösungen implementieren. Welche Lösungen Sie implementieren, hängt davon ab, wie dynamisch die Richtlinie sein soll und welche Bedrohungen priorisiert werden sollen. Einige Beispiele für solche Systeme sind:
- [Azure AD Identity Protection](https://docs.microsoft.com/azure/active-directory/identity-protection/) 
- [Azure Advanced Threat Protection](https://docs.microsoft.com/azure-advanced-threat-protection/) (Azure ATP)
- [Microsoft Defender Advanced Threat Protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) (Microsoft Defender ATP)
- [Office 365 Advanced Threat Protection](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp?view=o365-worldwide) (Office 365 ATP)
- [Microsoft Cloud-App-Sicherheit](https://docs.microsoft.com/cloud-app-security/) (MCAS)
- [Microsoft Threat Protection](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-threat-protection?view=o365-worldwide) (MTP)
- [Microsoft Intune](https://docs.microsoft.com/mem/intune/)
- [Microsoft Information Protection](https://docs.microsoft.com/microsoft-365/compliance/protect-information?view=o365-worldwide) (MIP)
- [Azure Sentinel](https://docs.microsoft.com/azure/sentinel/) 

Selbstverständlich verfügen verschiedene Dienste und Anwendungen neben Azure AD über eigene spezifische Autorisierungsmodelle. Einige davon werden weiter unten im Abschnitt Delegierung erläutert.

### <a name="audit"></a>Überwachung
Azure AD verfügt über detaillierte [Überwachungs-und Bericht Erstellungs](https://docs.microsoft.com/azure/active-directory/reports-monitoring/) Funktionen. Dies ist jedoch in der Regel nicht die einzige Informationsquelle, die zum Treffen von Sicherheitsentscheidungen benötigt wird. Weitere Erläuterungen hierzu finden Sie im Abschnitt delegieren.

## <a name="there-is-no-exchange"></a>Es gibt keine Exchange

Keine Panik! Dies bedeutet nicht, dass Exchange veraltet ist (oder SharePoint, etc.). Es ist nach wie vor ein zentraler Dienst. Was ich meine, ist, dass Technologieanbieter seit geraumer Zeit den Übergang von Benutzer Erfahrungen (UX) zur Einbeziehung von Komponenten mehrerer Dienste durchführen. In Microsoft 365 handelt es sich um ein einfaches Beispiel "[moderne Anlagen](https://support.office.com/article/Attach-files-or-insert-pictures-in-Outlook-email-messages-BDFAFEF5-792A-42B1-9A7B-84512D7DE7FC)", in dem e-Mail-Anhänge in SharePoint Online oder OneDrive für Unternehmen gespeichert werden. 

:::image type="content" source="../media/solutions-architecture-center/modern-attachments.png" alt-text="Anfügen einer Datei an eine e-Mail":::


Wenn Sie sich den Outlook-Client ansehen, können Sie viele Dienste sehen, die im Rahmen dieser Erfahrung "verbunden" sind, und nicht nur Exchange. Hierzu gehören Azure AD, Microsoft Search, apps, Profile, Compliance und Office 365 Gruppen. 

:::image type="content" source="../media/solutions-architecture-center/identity-and-beyond-conceptual-screenshot.png" alt-text="Outlook-Schnittstelle mit Legenden":::

Hier finden Sie Informationen zu [Microsoft Fluid Framework](https://techcommunity.microsoft.com/t5/microsoft-365-blog/microsoft-ignite-blog-microsoft-fluid-framework-preview/ba-p/978268) für die Vorschau auf bevorstehende Funktionen. In der Vorschau kann ich jetzt in Microsoft Teams-Unterhaltungen direkt in Outlook lesen und auf diese Antworten. Tatsächlich ist der Microsoft [Teams-Client](https://products.office.com/microsoft-teams/download-app) eines der prominentesten Beispiele für diese Strategie. 

Insgesamt wird es immer schwieriger, eine klare Verbindung zwischen Office 365 und anderen Diensten in Microsoft Clouds zu zeichnen. Ich betrachte es als großen Vorteil für Kunden, da Sie von der gesamten Innovation über alles profitieren können, was wir tun, auch wenn Sie eine Komponente verwenden. Ziemlich cool und hat weit reichende Auswirkungen für viele Kunden.

Heute finde ich viele Kunden-IT-Gruppen sind um "Produkte" strukturiert. Es ist logisch für eine lokale Welt, da Sie einen Fachmann für jedes spezifische Produkt benötigen. Allerdings bin ich absolut glücklich, dass ich eine Active Directory oder Exchange-Datenbank nie wieder Debuggen muss, da diese Dienste in die Cloud verschoben wurden. Automation (welche Cloud Art ist) entfernt bestimmte sich wiederholende manuelle Aufträge (schauen Sie sich an, was mit Factories passiert ist). Diese werden jedoch durch komplexere Anforderungen ersetzt, um die dienstübergreifende Interaktion, die Auswirkungen, die geschäftlichen Anforderungen usw. zu verstehen. Wenn Sie bereit sind zu [lernen](https://docs.microsoft.com/learn/), gibt es große Möglichkeiten, die von der Cloud-Transformation aktiviert werden. Vor dem Sprung in die Technologie spreche ich häufig mit Kunden über die Verwaltung von Änderungen an IT-Fertigkeiten und Teamstrukturen.

Wenden Sie sich an alle SharePoint-Fan-Personen und Entwickler, um zu Fragen: "wie kann ich XYZ in SharePoint Online ausführen?" Verwenden Sie [Power Automation](https://docs.microsoft.com/power-automate/) (aka Flow) für Workflow, es ist eine wesentlich leistungsstärkere Plattform. Verwenden Sie [Azure bot Framework](https://docs.microsoft.com/azure/bot-service/?view=azure-bot-service-4.0) , um eine bessere UX für Ihre 500.000-Elementliste zu erstellen. Beginnen Sie mit [Microsoft Graph](https://developer.microsoft.com/graph/) anstelle von CSOM. [Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/Teams-overview) umfasst SharePoint, aber auch eine Welt mehr. Es gibt viele andere Beispiele, die ich auflisten kann. Es gibt ein riesiges und wunderbares Universum da draußen. Öffnen Sie die Tür, und beginnen Sie mit der [Erkundung](https://docs.microsoft.com).

Die anderen allgemeinen Auswirkungen liegen im Kompatibilitätsbereich. Dieser Cross-Services-Ansatz scheint viele Konformitätsrichtlinien vollständig zu verwirren. Ich sehe immer wieder Organisationen mit dem Status "Ich muss alle e-Mail-Kommunikationen an ein eDiscovery-System Journal". Was bedeutet dies wirklich, wenn e-Mail nicht mehr nur e-Mails, sondern ein Fenster in andere Dienste ist? Office 365 hat einen umfassenden Ansatz für die [Einhaltung von Anforderungen](https://docs.microsoft.com/microsoft-365/compliance/), aber das Ändern von Personen und Prozessen ist häufig weitaus schwieriger als die Technologie.

Es gibt viele andere Personen und Auswirkungen auf den Prozess. Meiner Meinung nach ist dies ein kritischer und unter diskutierter Bereich. Vielleicht mehr in einem anderen Artikel.

## <a name="tenant-structure-options"></a>Mandantenstruktur Optionen

### <a name="single-tenant-vs-multi-tenant"></a>Einzelner Mandant im Vergleich zu mehreren Mandanten

Im Allgemeinen sollten die meisten Kunden nur einen Produktions Mandanten haben. Es gibt viele Gründe, warum mehrere Mandanten eine Herausforderung darstellen ( [Bing-Suche](https://www.bing.com/search?q=office%20365%20multiple%20tenants)) oder dieses [Whitepaper](https://aka.ms/multi-tenant-user)lesen können. Gleichzeitig haben viele Unternehmenskunden, mit denen ich zusammenarbeite, einen weiteren (kleinen) Mandanten für IT-Lern-, Test-und Experimentier arbeiten. Ein Mandanten übergreifender Azure-Zugriff wird mit [Azure Lighthouse](https://azure.microsoft.com/services/azure-lighthouse/)vereinfacht. Office 365 und viele andere Saas-Dienste haben Grenzen für Mandantenübergreifende Szenarien. In [Azure AD B2B](https://docs.microsoft.com/azure/active-directory/b2b/what-is-b2b) -Szenarien ist viel zu prüfen.

Viele Kunden enden mit mehreren Produktions Mandanten nach einer Fusion und Akquisition (M&a) und möchten eine Konsolidierung durchführen. Heute ist dies nicht einfach und erfordert Microsoft Consulting Services (MCS) oder einen Partner sowie Drittanbietersoftware. Es gibt eine kontinuierliche technische Arbeit, um in Zukunft verschiedene Szenarien mit Mandanten mit mehreren Mandanten zu adressieren. 

Einige Kunden entscheiden sich für das wechseln mit mehr als einem Mandanten. Dies sollte eine sehr sorgfältige Entscheidung sein und fast immer Geschäfts Vernunft getrieben! Einige Beispiele umfassen Folgendes:
- Eine holdingtyp-Unternehmensstruktur, in der eine einfache Zusammenarbeit zwischen verschiedenen Entitäten nicht erforderlich ist und eine starke administrative und andere Isolierung benötigt wird.
- Nach einer Akquisition wird eine geschäftliche Entscheidung getroffen, um zwei Entitäten voneinander getrennt zu halten.
- Simulation der Kundenumgebung, die die Produktionsumgebung des Kunden nicht ändert. 
- Entwicklung von Software für Kunden.

In diesen Szenarien mit mehreren Mandanten möchten Kunden häufig die gleiche Konfiguration für Mandanten beibehalten oder Konfigurationsänderungen und-Verschiebungen melden. Dies bedeutet häufig das Wechseln von manuellen Änderungen zur Konfiguration als Code. Microsoft Premiere Support bietet einen Workshop für diese Arten von Anforderungen basierend auf dieser öffentlichen IP: [https://Microsoft365dsc.com](https://Microsoft365dsc.com) .


### <a name="multi-geo"></a>Multi-Geo 

Auf [Multi-Geo](https://docs.microsoft.com/office365/enterprise/office-365-multi-geo) oder nicht auf Multi-Geo, das ist die Frage. Mit Office 365 Multi-Geo können Sie Daten im Ruhezustand in den geografischen Speicherorten bereitstellen und speichern, die Sie für die Anforderungen an den [Daten Wohnsitz](https://docs.microsoft.com/office365/enterprise/o365-data-locations) ausgewählt haben. Es gibt viele Missverständnisse über diese Funktion. Denken Sie dabei an Folgendes: 
- Es bietet keine Leistungsvorteile. Die Leistung kann schlechter werden, wenn das [Netzwerk Design](https://aka.ms/office365networking) nicht richtig ist. Geräte "Schließen" im Microsoft-Netzwerk abrufen, nicht unbedingt für Ihre Daten.
- Es handelt sich nicht um eine Lösung für die [dsgvo-Compliance](https://www.microsoft.com/trust-center/privacy/gdpr-overview). Dsgvo konzentriert sich nicht auf Daten Souveränität oder Speicherorte. Dafür gibt es andere Compliance-Frameworks.
- Die Delegierung der Verwaltung (siehe unten) oder [Informationsbarrieren](https://docs.microsoft.com/microsoft-365/compliance/information-barriers)wird nicht gelöst.
- Es ist nicht identisch mit Mehrmandantenfähigkeit und erfordert zusätzliche Workflows für die [Benutzer](https:/docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-sync-feature-preferreddatalocation) Einrichtung.
- [Ihr Mandant](https://docs.microsoft.com/office365/enterprise/moving-data-to-new-datacenter-geos) (Ihr Azure AD) wird nicht in eine andere Geographie verschoben. 

## <a name="delegation-of-administration"></a>Delegierung der Verwaltung

In den meisten großen Organisationen ist die Trennung von Aufgaben und die rollenbasierte Zugriffssteuerung (RBAC) eine notwendige Realität. Ich werde mich vor der Zeit entschuldigen. Dies ist nicht so einfach, wie es einige Kundenwünschen. Kunden-, rechtliche, Compliance-und andere Anforderungen sind unterschiedlich und treten manchmal weltweit in Konflikt. Einfachheit und Flexibilität sind häufig auf gegenüberliegenden Seiten voneinander. Versteh mich nicht falsch, wir können eine bessere Arbeit an diesem zu tun. Es wurden (und werden) erhebliche Verbesserungen im Laufe der Zeit. Besuchen Sie Ihr lokales [Microsoft Technology Center](https://www.microsoft.com/mtc) , um das Modell zu erarbeiten, das Ihren geschäftlichen Anforderungen entspricht, ohne 379230 docs zu lesen! Hier werde ich mich auf das konzentrieren, woran Sie denken sollten und nicht, warum es so ist. Im folgenden finden Sie fünf verschiedene Bereiche für die Planung und einige der häufigsten Fragen, die mir aufgetreten sind.

### <a name="azure-ad-and-microsoft-365-admin-centers"></a>Azure AD und Microsoft 365 Admin Center

Es gibt eine lange und wachsende Liste [integrierter Rollen](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles). Jede Rolle besteht aus einer Liste von Rollen Berechtigungen, die zusammen gruppiert werden, damit bestimmte Aktionen ausgeführt werden können. Sie können diese Berechtigungen in der Registerkarte "Beschreibung" in jeder Rolle sehen. Alternativ können Sie eine besser lesbare Version davon im Microsoft 365 Admin Center sehen. Die Definitionen für integrierte Rollen können nicht geändert werden. Ich gruppieren diese in der Regel in drei Kategorien:

- **Globaler Administrator** – diese "All powerful"-Rolle sollte genau wie in anderen Systemen [stark geschützt](https://docs.microsoft.com/office365/enterprise/protect-your-global-administrator-accounts) sein. Typische Empfehlungen sind: keine dauerhafte Zuweisung und Verwendung Azure AD privilegierten Identitätsverwaltung (PIM); starke Authentifizierung; usw. Interessanterweise gibt Ihnen diese Rolle nicht standardmäßig Zugriff auf alles. In der Regel sehe ich Verwirrung hinsichtlich des Kompatibilitäts Zugriffs und des Azure-Zugriffs, die später besprochen werden. Diese Rolle kann jedoch immer Zugriff auf andere Dienste im Mandanten zuweisen. 
- **Bestimmte Dienstadministratoren** – einige Dienste (Exchange, SharePoint, Power BI usw.) beanspruchen Verwaltungsrollen auf höherer Ebene aus Azure AD. Dies ist nicht für alle Dienste konsistent, und es werden später weitere dienstspezifische Rollen behandelt.
- **Funktional** – es gibt eine lange (und wachsende) Liste von Rollen, die sich auf bestimmte Vorgänge (Gast Inviter usw.) konzentrieren. In regelmäßigen Abständen werden diese basierend auf den Kundenanforderungen hinzugefügt.

Es ist nicht möglich, alles zu delegieren (obwohl die Lücke abnimmt), was bedeutet, dass die globale Administratorrolle manchmal verwendet werden muss. Konfigurationscode und Automatisierung sollten anstelle der Personen Mitgliedschaft in dieser Rolle berücksichtigt werden.

**Hinweis**: das Microsoft 365 Admin Center verfügt über eine benutzerfreundlichere Oberfläche, verfügt jedoch über eine Teilmenge der Funktionen im Vergleich zum Azure AD Administrator Erlebnis. Beide Portale verwenden dieselben Azure AD Rollen, sodass Änderungen an der gleichen Stelle stattfinden. Tipp: Wenn Sie eine auf Identitätsverwaltung ausgerichtete Verwaltungsbenutzeroberfläche ohne alle Azure clutter möchten, verwenden Sie [https://aad.portal.azure.com](https://aad.portal.azure.com) . 

Was ist im Namen? Machen Sie keine Annahmen aus dem Namen der Rolle. Sprache ist kein sehr präzises Tool. Ziel sollte es sein, Vorgänge zu definieren, die delegiert werden müssen, bevor Sie sich mit den erforderlichen Rollen begeben. Durch das Hinzufügen einer Person zur Rolle "Sicherheits Leser" werden keine Sicherheitseinstellungen in allen Bereichen angezeigt. 

Die Möglichkeit, [benutzerdefinierte Rollen](https://docs.microsoft.com/azure/active-directory/users-groups-roles/roles-custom-overview) zu erstellen, ist eine häufige Frage. Dies ist in Azure AD heute (siehe unten) limitiert, wird jedoch im Laufe der Zeit in den Fähigkeiten wachsen. Ich denke an diese wie für Funktionen in Azure AD und möglicherweise nicht über das Hierarchiemodell (oben erläutert). Immer, wenn ich mit "Custom" beschäftige, neige ich dazu, zu meinem Prinzipal von "Simple is better" zurückzukehren.

Eine weitere häufige Frage ist die Fähigkeit, Rollen auf eine Teilmenge eines Verzeichnisses zu stellen. Ein Beispiel ist so etwas wie "Helpdesk-Administrator für Benutzer in der EU." Die [Verwaltungseinheiten](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-administrative-units) (AU) sollen dies beheben. Wie oben denke ich an diese wie für Funktionen in Azure AD und möglicherweise nicht überspannen "nach unten". Selbstverständlich haben bestimmte Rollen keinen Sinn für den Bereich (globale Administratoren, Dienstadministratoren usw.).

Alle diese Rollen erfordern heute eine direkte Mitgliedschaft (oder dynamische Zuweisung, wenn Sie [Azure AD PIM](https://docs.microsoft.com/azure/active-directory/privileged-identity-management/)verwenden). Dies bedeutet, dass Kunden diese direkt in Azure AD verwalten müssen, und diese können nicht auf einer Sicherheitsgruppenmitgliedschaft basieren. Ich bin kein Fan von Erstellungsskripts zum Verwalten dieser, da es mit erhöhten Rechten ausgeführt werden müsste. Ich empfehle generell die API-Integration in Prozess Systeme wie ServiceNow oder die Verwendung von Partner Steuerungstools wie Saviynt. Es werden technische arbeiten durchlaufen, um dies im Laufe der Zeit zu beheben.

Ich erwähnte [Azure AD PIM](https://docs.microsoft.com/azure/active-directory/privileged-identity-management/) ein paar Mal. Es gibt eine entsprechende Microsoft Identity Manager (MIM)-Lösung für [privilegierte Zugriffsverwaltung](https://docs.microsoft.com/microsoft-identity-manager/pam/privileged-identity-management-for-active-directory-domain-services) (PAM) für lokale Steuerelemente. Möglicherweise möchten Sie auch die [Berechtigungen für privilegierte Zugriffs Arbeitsstationen](https://docs.microsoft.com/windows-server/identity/securing-privileged-access/privileged-access-workstations) (PAWs) und [Azure AD Identity Governance](https://docs.microsoft.com/azure/active-directory/governance/identity-governance-overview)betrachten. Es gibt auch eine Vielzahl von Tools von Drittanbietern, die Just-in-Time-, Just-Enough-und dynamische Rollen Anhebung ermöglichen können. Dies ist normalerweise Teil einer größeren Diskussion zum Sichern einer Umgebung. 

In manchen Szenarien wird zum Hinzufügen eines externen Benutzers zu einer Rolle aufgerufen (siehe den Abschnitt mit mehreren Mandanten, weiter oben). Dies funktioniert ganz gut. [Azure AD B2B](https://docs.microsoft.com/azure/active-directory/b2b/) ist ein weiteres großes und unterhaltsames Thema, um Kunden zu durchlaufen, möglicherweise in einem anderen Artikel.

### <a name="security-and-compliance-center-scc"></a>Security and Compliance Center (SCC)

[Berechtigungen im Office 365 Security & Compliance Center](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center) sind eine Sammlung von "Rollengruppen", die voneinander getrennt sind und sich von Azure AD Rollen unterscheiden. Dies kann verwirrend sein, da einige dieser Rollengruppen denselben Namen haben wie Azure AD Rollen (beispielsweise Sicherheits Leser), aber Sie können unterschiedliche Mitgliedschaft haben. Ich bevorzuge die Verwendung von Azure AD Rollen. Jede Rollengruppe besteht aus einer oder mehreren "Rollen" (siehe was ich meine zur Wiederverwendung des gleichen Wortes?) und haben Mitglieder aus Azure AD, die e-Mail-aktivierte Objekte sind. Außerdem können Sie eine Rollengruppe mit dem gleichen Namen wie eine Rolle erstellen, die diese Rolle enthalten kann oder auch nicht (vermeiden Sie diese Verwirrung).

In gewisser Hinsicht handelt es sich dabei um eine Entwicklung des Exchange-Rollengruppenmodells. Exchange Online verfügt jedoch über eine eigene Benutzeroberfläche für die [Rollengruppenverwaltung](https://docs.microsoft.com/exchange/permissions-exo) . Einige Rollengruppen in Exchange Online werden aus Azure AD oder dem Security & Compliance Center gesperrt und verwaltet, andere können jedoch dieselben oder ähnliche Namen haben und in Exchange Online verwaltet werden (Hinzufügen zur Verwirrung). Es wird empfohlen, die Verwendung der Exchange Online-Benutzeroberfläche zu vermeiden, es sei denn, Sie benötigen Bereiche für die Exchange-Verwaltung.

Sie können keine benutzerdefinierten Rollen erstellen. Rollen werden durch von Microsoft erstellte Dienste definiert und werden bei der Einführung neuer Dienste anwachsen. Dies ähnelt dem Konzept der [von Anwendungen in Azure AD definierten Rollen](https://docs.microsoft.com/azure/active-directory/develop/howto-add-app-roles-in-azure-ad-apps) . Wenn neue Dienste aktiviert sind, müssen häufig neue Rollengruppen erstellt werden, um den Zugriff auf diese zu gewähren oder zu delegieren (beispielsweise [Insider Risk Management](https://docs.microsoft.com/microsoft-365/compliance/insider-risk-management-configure?view=o365-worldwide#step-1-required-enable-permissions-for-insider-risk-management)).

Diese Rollengruppen erfordern auch eine direkte Mitgliedschaft und können keine Azure Ad Gruppen enthalten. Leider werden diese Rollengruppen heute nicht von Azure AD PIM unterstützt. Wie Azure AD Rollen empfehle ich, diese über APIs oder ein Partner Steuerungs Produkt wie Saviynt oder andere zu verwalten.

Sicherheits & Compliance Center-Rollen umfassen Microsoft 365, und Sie können diese Rollengruppen nicht auf eine Teilmenge der Umgebung umstellen (wie bei administrativen Einheiten in Azure AD). Viele Kunden Fragen, wie Sie unter delegieren können. Beispiel: "Erstellen einer DLP-Richtlinie nur für EU-Benutzer". Wenn Sie heute Rechte an einer bestimmten Funktion im Security & Compliance Center haben, haben Sie Rechte an allem, was von dieser Funktion im Mandanten abgedeckt wird. Viele Richtlinien verfügen jedoch über Funktionen zum Ziel einer Teilmenge der Umgebung (beispielsweise "diese [Bezeichnungen](https://docs.microsoft.com/microsoft-365/compliance/create-sensitivity-labels#publish-sensitivity-labels-by-creating-a-label-policy) nur diesen Benutzern zur Verfügung stellen"). Eine ordnungsgemäße Steuerung und Kommunikation sind eine wichtige Komponente zur Vermeidung von Konflikten. Einige Kunden entscheiden sich für die Implementierung eines "Configuration as Code"-Ansatzes zur Adressierung von unter Delegierung im Security & Compliance Center. Einige spezifische Dienste unterstützen die untergeordnete Delegierung (siehe unten). 

Es sollte darauf hingewiesen werden, dass Steuerelemente, die derzeit über das Security & Compliance Center (Protection.Office.com) verwaltet werden, in den Prozess der Migration zu zwei separaten Administrator Portalen migriert werden: Security.Microsoft.com und Compliance.Microsoft.com. Änderung ist die einzige Konstante!

### <a name="service-specific"></a>Dienst spezifisch

Wie bereits erwähnt, suchen viele Kunden nach einem präziseren Delegierungsmodell. Ein allgemeines Beispiel: "XYZ-Dienst nur für Division X-Benutzer und-Standorte verwalten" (oder eine andere Dimension). Die Möglichkeit, dies zu tun, hängt von den einzelnen Diensten ab und ist nicht für alle Dienste und Funktionen konsistent. Darüber hinaus verfügt jeder Dienst möglicherweise über ein separates und ein eindeutiges RBAC-Modell. Anstatt all diese zu besprechen (es wird ewig dauern), füge ich relevante Links für jeden Dienst hinzu. Dies ist keine vollständige Liste, aber Sie erhalten den Einstieg.

- **Exchange Online** - [https://docs.microsoft.com/exchange/permissions-exo/permissions-exo](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo) 
- **SharePoint Online** - [https://docs.microsoft.com/sharepoint/manage-site-collection-administrators](https://docs.microsoft.com/sharepoint/manage-site-collection-administrators) 
- **Microsoft Teams**  -  [https://docs.microsoft.com/microsoftteams/itadmin-readiness ](https://docs.microsoft.com/microsoftteams/itadmin-readiness )
- **eDiscovery** - [https://docs.microsoft.com/microsoft-365/compliance/assign-ediscovery-permissions](https://docs.microsoft.com/microsoft-365/compliance/) 
  + **Berechtigungs Filterung**  -  [https://docs.microsoft.com/microsoft-365/compliance/permissions-filtering-for-content-search ](https://docs.microsoft.com/microsoft-365/compliance/)
  + **Compliance-Grenzen**  -  [https://docs.microsoft.com/microsoft-365/compliance/set-up-compliance-boundaries ](https://docs.microsoft.com/microsoft-365/compliance/set-up-compliance-boundaries )
  + **Erweiterte eDiscovery**  -  [https://docs.microsoft.com/microsoft-365/compliance/overview-ediscovery-20 ](https://docs.microsoft.com/microsoft-365/compliance/overview-ediscovery-20 )
- **Yammer** - [https://docs.microsoft.com/yammer/manage-yammer-users/manage-yammer-admins](https://docs.microsoft.com/yammer/manage-yammer-users/manage-yammer-admins) 
- **Multi-Geo** - [https://docs.microsoft.com/office365/enterprise/add-a-sharepoint-geo-admin](https://docs.microsoft.com/office365/enterprise/add-a-sharepoint-geo-admin) 
- **Dynamics 365** –[https://docs.microsoft.com/dynamics365/](https://docs.microsoft.com/dynamics365/) <br>
  Hinweis: dieser Link befindet sich im Stammverzeichnis der Dokumentation. Es gibt mehrere Arten von Diensten mit Variationen im Administrator/Delegierungsmodell.
- **Power-Plattform**  -  [https://docs.microsoft.com/power-platform/admin/admin-documentation ](https://docs.microsoft.com/power-platform/admin/admin-documentation )
  + **Power-apps**  -  [https://docs.microsoft.com/power-platform/admin/wp-security ](https://docs.microsoft.com/power-platform/admin/wp-security ) <br>
    Hinweis: Es gibt mehrere Typen mit Variationen in den Modellen admin/Delegation.
  + **Power-Automatisierung**  -  [https://docs.microsoft.com/power-automate/environments-overview-admin ](https://docs.microsoft.com/power-automate/environments-overview-admin )
  + **PowerBI**  -  [https://docs.microsoft.com/power-bi/service-admin-governance ](https://docs.microsoft.com/power-bi/service-admin-governance ) <br>
Hinweis: Sicherheit und Delegierung von Datenplattformen (die Power BI ist eine Komponente) ist ein komplexer Bereich.
- **Mem/InTune**  -  [https://docs.microsoft.com/mem/intune/fundamentals/role-based-access-control ](https://docs.microsoft.com/mem/intune/fundamentals/role-based-access-control )
- **Microsoft Defender ATP**  -  [https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/user-roles ](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/user-roles )
- **Microsoft Threat Protection** - [https://docs.microsoft.com/microsoft-365/security/mtp/mtp-permissions](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-permissions)
- **Microsoft Cloud-App-Sicherheit** - [https://docs.microsoft.com/cloud-app-security/manage-admins](https://docs.microsoft.com/cloud-app-security/manage-admins)
- **Datenstrom**  -  [https://docs.microsoft.com/stream/assign-administrator-user-role ](https://docs.microsoft.com/stream/assign-administrator-user-role )
- **Informationsbarrieren**  -  [https://docs.microsoft.com/microsoft-365/compliance/information-barriers ](https://docs.microsoft.com/microsoft-365/compliance/information-barriers )

Für den Rest war die Suche in Dokumenten in letzter Zeit wirklich gut [https://docs.microsoft.com/](https://docs.microsoft.com/microsoft-365/compliance/information-barriers) . 


### <a name="activity-logs"></a>Aktivitätsprotokolle
Office 365 verfügt über ein [einheitliches Überwachungsprotokoll](https://docs.microsoft.com/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance). Es handelt sich um ein sehr [Detailliertes Protokoll](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema), aber nicht zu viel in den Namen zu lesen. Sie enthält möglicherweise nicht alles, was Sie für Ihre Sicherheits-und Compliance-Anforderungen wünschen oder benötigen. Außerdem sind einige Kunden wirklich an einer [erweiterten Überwachung](https://docs.microsoft.com/microsoft-365/compliance/advanced-audit)interessiert. 

Beispiele für Microsoft 365-Protokolle, auf die über andere APIs zugegriffen wird, sind folgende:
- [Azure AD](https://docs.microsoft.com/azure/azure-monitor/platform/diagnostic-settings) (Aktivitäten, die nicht mit Office 365 in Zusammenhangstehen)
- [Exchange-Nachrichtenverfolgung](https://docs.microsoft.com/powershell/module/exchange/get-messagetrace?view=exchange-ps)
- Oben beschriebene Threat/UEBA-Systeme (beispielsweise Azure AD Identity Protection, Microsoft Cloud App Security, Microsoft Defender ATP, etc.)
- [Microsoft Information Protection](https://docs.microsoft.com/microsoft-365/compliance/data-classification-activity-explorer?view=o365-worldwide)
- [Microsoft Defender ATP](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/api-power-bi)
- [Microsoft Graph](https://graph.microsoft.com)

Es ist wichtig, zunächst alle Protokollquellen zu identifizieren, die für ein Sicherheits-und Kompatibilitäts Programm benötigt werden. Beachten Sie auch, dass unterschiedliche Protokolle über unterschiedliche Online-Aufbewahrungs Grenzwerte verfügen. 

Aus Sicht der Administrator Delegierung verfügen die meisten Microsoft 365-Aktivitätsprotokolle nicht über ein integriertes RBAC-Modell. Wenn Sie über die Berechtigung zum Anzeigen eines Protokolls verfügen, können Sie alles darin sehen. Ein häufiges Beispiel für eine Kundenanforderung ist: "Ich möchte Aktivitäten nur für EU-Benutzer Abfragen können" (oder eine andere Dimension). Um diese Anforderung zu erfüllen, müssen Sie Protokolle an einen anderen Dienst übertragen. In der Microsoft-Cloud wird empfohlen, Sie an [Azure Sentinel](https://docs.microsoft.com/azure/sentinel/overview) oder [Log Analytics](https://docs.microsoft.com/azure/azure-monitor/learn/quick-create-workspace)zu übertragen. 

Diagramm auf hoher Ebene:

![Diagramm auf hoher Ebene des Protokoll Flusses](../media/solutions-architecture-center/identity-beyond-illustration-4.png)  

Das obige Diagramm stellt integrierte Funktionen zum Senden von Protokollen an Event Hub und/oder Azure Storage und/oder Azure Log Analytics dar. Nicht alle Systeme enthalten diese out-of-the-Box noch. Es gibt aber auch andere Ansätze, diese Protokolle an dasselbe Repository zu senden. Beispielsweise finden Sie unter [Protecting Your Teams with Azure Sentinel](https://techcommunity.microsoft.com/t5/azure-sentinel/protecting-your-teams-with-azure-sentinel/ba-p/1265761).

Die Kombination aller Protokolle zu einem Speicherort umfasst zusätzlichen Vorteil, wie etwa Korrelationen, benutzerdefinierte Aufbewahrungszeiten, die Erweiterung mit Daten, die für die Unterstützung des RBAC-Modells erforderlich sind, usw. Sobald sich Daten in diesem Speichersystem befinden, können Sie ein PowerBI-Dashboard (oder eine andere Art der Visualisierung) mit einem entsprechenden RBAC-Modell erstellen.

Protokolle müssen nicht nur an eine Stelle weitergeleitet werden. Es kann auch vorteilhaft sein, [Office 365 Protokolle mit Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security/connect-office-365-to-microsoft-cloud-app-security) oder einem benutzerdefinierten RBAC-Modell in [Power BI](https://docs.microsoft.com/microsoft-365/admin/usage-analytics/usage-analytics?view=o365-worldwide)zu integrieren. Unterschiedliche Repositories weisen unterschiedliche Vorteile und Benutzergruppen auf.

Es ist erwähnenswert, dass es ein sehr umfangreiches integriertes Analysesystem für Sicherheit, Bedrohungen, Sicherheitsrisiken usw. in einem Dienst namens " [Microsoft Threat Protection](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-threat-protection?view=o365-worldwide)" gibt.

Viele große Kunden möchten diese Protokolldaten in ein Drittanbietersystem übertragen (beispielsweise Siem). Dafür gibt es verschiedene Ansätze, aber in-General [Azure Event Hub](https://docs.microsoft.com/azure/azure-monitor/platform/stream-monitoring-data-event-hubs) und [Graph](https://docs.microsoft.com/graph/security-integration) sind gute Ausgangspunkte.


### <a name="azure"></a>Azure 
Ich werde häufig gefragt, ob es eine Möglichkeit gibt, Rollen mit hoher Berechtigungsstufe zwischen Azure AD, Azure und SaaS zu trennen (z. b.: globaler Administrator für Office 365, jedoch nicht Azure).  Nicht wirklich.  Die Architektur mit mehreren Mandanten ist erforderlich, wenn eine vollständige administrative Trennung erforderlich ist, dies jedoch eine erhebliche [Komplexität](https://aka.ms/multi-tenant-user) mit sich bringt (siehe oben). Alle diese Dienste sind Teil derselben Sicherheits-/Identitäts Grenze (siehe Hierarchiemodell oben).  

Es ist wichtig, die Beziehungen zwischen verschiedenen Diensten in demselben Mandanten zu verstehen. Ich arbeite mit vielen Kunden zusammen, die Business-Lösungen erstellen, die sich auf Azure-, Office 365-und Power-Plattform (und häufig auch auf lokale und Drittanbieter-Cloud-Dienste) erstrecken. Ein allgemeines Beispiel: 
-   Ich möchte an einer Reihe von Dokumenten/Bildern/etc zusammenarbeiten (Office 365)
-   jeden einzelnen von diesen über einen Genehmigungsprozess (Power Platform) senden
-   Nachdem alle Komponenten genehmigt wurden, können Sie diese in eine vereinheitlichte (n) Lieferumfang (en) (Azure) [Microsoft Graph-API](https://docs.microsoft.com/azure/active-directory/develop/microsoft-graph-intro) einbauen, ist Ihr bester Freund für diese.  Nicht unmöglich, aber wesentlich komplexer, um eine Lösung zu entwerfen, die [mehrere Mandanten](https://docs.microsoft.com/azure/active-directory/develop/single-and-multi-tenant-apps)umfasst.

Die Azure-rollenbasierte Zugriffssteuerung (RBAC) ermöglicht eine abgestimmte Zugriffsverwaltung für Azure. Mit RBAC können Sie den Zugriff auf Ressourcen verwalten, indem Sie Benutzern die wenigsten Berechtigungen für die Ausführung Ihrer Aufträge erteilen. Details liegen außerhalb des Bereichs für dieses Dokument, aber weitere Informationen zu RBAC finden Sie unter [Was ist rollenbasierte Zugriffssteuerung (Role-Based Access Control, RBAC) in Azure?](https://docs.microsoft.com/azure/role-based-access-control/overview) RBAC ist wichtig, aber nur ein Teil der Steuerungs Überlegungen für Azure. [Cloud Adoption Framework](https://docs.microsoft.com/azure/cloud-adoption-framework/govern/) ist ein guter Ausgangspunkt, um weitere Informationen zu erhalten. Ich mag, wie mein Freund, Andres schluchtt Kunden Schritt für Schritt durch verschiedene Komponenten, um über den Ansatz zu entscheiden, geht. Eine allgemeine Ansicht für verschiedene Elemente (nicht so gut wie der Prozess zum Erreichen des tatsächlichen Kundenmodells) ist wie folgt:

:::image type="content" source="../media/solutions-architecture-center/identity-beyond-illustration-5.png" alt-text="allgemeine Ansicht von Azure-Komponenten für die delegierte Verwaltung":::

Wie Sie aus der obigen Abbildung sehen können, sollten viele andere Dienste als Teil des Entwurfs betrachtet werden (beispielsweise: [Azure-Richtlinien](https://docs.microsoft.com/azure/governance/policy/overview), [Azure-Blaupausen](https://docs.microsoft.com/azure/governance/blueprints/overview), [Verwaltungsgruppen](https://docs.microsoft.com/azure/governance/management-groups/)usw.).

## <a name="conclusion"></a>Schlussbemerkung
Begonnen als kurze Zusammenfassung, endete länger als erwartet.  Ich hoffe, Sie sind jetzt in der Lage, ein detailliertes Beispiel für die Erstellung des Delegierungsmodells für Ihre Organisation zu finden.  Diese Unterhaltung ist bei Kunden sehr verbreitet. Es gibt kein einziges Modell, das für jeden geeignet ist. Warten auf einige geplante Verbesserungen von Microsoft Engineering vor dem dokumentieren allgemeiner Muster, die wir Across Kunden sehen. In der Zwischenzeit können Sie mit Ihrem Microsoft-Konto Team zusammenarbeiten, um einen Besuch im nächsten [Microsoft Technology Center](https://www.microsoft.com/mtc)zu arrangieren.  Wir sehen uns dort!


