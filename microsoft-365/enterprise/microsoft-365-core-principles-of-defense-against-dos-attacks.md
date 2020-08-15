---
title: Microsoft 365 Kernprinzipien der Abwehr von Denial-of-Service-Angriffen
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
f1.keywords:
- NOCSH
description: Wie Microsoft die Kernprinzipien der Absorption, Erkennung und Minderung bei der Abwehr von DOS-Angriffen (Denial of Service) verwendet.
ms.openlocfilehash: b04ec717f7c97e44c6ed4011156666e8c27f06c0
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46690487"
---
# <a name="core-principles-of-defense-against-denial-of-service-attacks"></a><span data-ttu-id="797e2-103">Grundlegende Prinzipien der Abwehr von Denial-of-Service-Angriffen</span><span class="sxs-lookup"><span data-stu-id="797e2-103">Core principles of defense against denial-of-service attacks</span></span>

<span data-ttu-id="797e2-104">Die drei Hauptprinzipien bei der Verteidigung gegen netzwerkbasierte DOS-Angriffe sind Absorption, Erkennung und Minderung.</span><span class="sxs-lookup"><span data-stu-id="797e2-104">The three core principles when defending against network-based DoS attacks are Absorption, Detection, and Mitigation.</span></span> <span data-ttu-id="797e2-105">Die Absorption erfolgt vor der Erkennung, und die Erkennung erfolgt vor der Minderung.</span><span class="sxs-lookup"><span data-stu-id="797e2-105">Absorption happens before detection, and detection happens before mitigation.</span></span> <span data-ttu-id="797e2-106">Absorption ist die beste Verteidigung gegen einen DOS-Angriff.</span><span class="sxs-lookup"><span data-stu-id="797e2-106">Absorption is the best defense against a DoS attack.</span></span> <span data-ttu-id="797e2-107">Wenn der Angriff nicht erkannt werden kann, kann er nicht gemindert werden.</span><span class="sxs-lookup"><span data-stu-id="797e2-107">If the attack can't be detected, it can't be mitigated.</span></span> <span data-ttu-id="797e2-108">Wenn aber selbst der kleinste DOS-Angriff nicht absorbiert werden kann, werden Dienste nicht lange genug überleben, damit der Angriff erkannt wird.</span><span class="sxs-lookup"><span data-stu-id="797e2-108">But if even the smallest DoS attack can't be absorbed, then services aren't going to survive long enough for the attack to be detected.</span></span>

<span data-ttu-id="797e2-109">Für die meisten Organisationen ist es nicht wirtschaftlich möglich, überschüssige Kapazitäten für die Aufnahme von DOS-Angriffen zu erwerben, da dies erhebliche Investitionen in Technologie und technische Fertigkeiten erfordert.</span><span class="sxs-lookup"><span data-stu-id="797e2-109">It is not economically feasible for most organizations to purchase excess capacity to absorb DoS attacks, as this requires a considerable investment in technology and technical skills.</span></span> <span data-ttu-id="797e2-110">Dies zeigt einen der Sicherheitsvorteile der Verwendung von Microsoft Cloud Services.</span><span class="sxs-lookup"><span data-stu-id="797e2-110">This highlights one of the security benefits of using Microsoft cloud services.</span></span> <span data-ttu-id="797e2-111">Die schiere Skalierung von Microsoft-Diensten bietet Cloud-Kunden einen starken Netzwerkschutz auf kosteneffektive Weise.</span><span class="sxs-lookup"><span data-stu-id="797e2-111">The sheer scale of Microsoft services provides strong network protection to cloud customers in a cost-effective manner.</span></span> <span data-ttu-id="797e2-112">Aber selbst im großen Maßstab muss es ein Gleichgewichtzwischen Absorption, Erkennung und Minderung geben.</span><span class="sxs-lookup"><span data-stu-id="797e2-112">But even at a large scale, there must be a balance between absorption, detection, and mitigation.</span></span> <span data-ttu-id="797e2-113">Um dieses Gleichgewicht zu finden, untersucht Microsoft die Angriffs Raten, um abzuschätzen, wie viel Microsoft absorbieren muss.</span><span class="sxs-lookup"><span data-stu-id="797e2-113">To find that balance, Microsoft studies attack growth rates to estimate how much Microsoft needs to absorb.</span></span>

<span data-ttu-id="797e2-114">Die Erkennung ist ein Katz-und-Maus-Spiel.</span><span class="sxs-lookup"><span data-stu-id="797e2-114">Detection is a cat-and-mouse game.</span></span> <span data-ttu-id="797e2-115">Sie müssen ständig nach neuen Wegen suchen, die Menschen angreifen und versuchen, ihre Systeme zu besiegen.</span><span class="sxs-lookup"><span data-stu-id="797e2-115">You must constantly look for new ways people are attack and try to defeat your systems.</span></span> <span data-ttu-id="797e2-116">"Detect-> mindern-> Detect-> mindern usw. ist ein dauerhafter, persistenter Status, der unbegrenzt fortgesetzt wird.</span><span class="sxs-lookup"><span data-stu-id="797e2-116">Detect -> Mitigate -> Detect -> Mitigate, etc., is a perpetual, persistent state that continues indefinitely.</span></span>

## <a name="defending-against-dos-attacks"></a><span data-ttu-id="797e2-117">Abwehr von DOS-Angriffen</span><span class="sxs-lookup"><span data-stu-id="797e2-117">Defending Against DoS Attacks</span></span>

<span data-ttu-id="797e2-118">Um eine erfolgreiche Abwehr von DOS-Angriffen zu erhalten, ist eine frühzeitige Erkennung unerlässlich.</span><span class="sxs-lookup"><span data-stu-id="797e2-118">To successfully defend against a DoS attack, early detection is essential.</span></span> <span data-ttu-id="797e2-119">Wenn ein Angriff erkannt wird, bevor das System überlastet ist, können Verteidiger einen Antwort Plan ausführen.</span><span class="sxs-lookup"><span data-stu-id="797e2-119">By detecting an attack before the system is overwhelmed, defenders can execute a response plan.</span></span>

<span data-ttu-id="797e2-120">Die folgende Formel hilft, die Zeit bis zur Auswirkung eines DoS-Angriffs näher zu befolgen:</span><span class="sxs-lookup"><span data-stu-id="797e2-120">The following formula helps approximate the time to impact of a DoS attack:</span></span>

   <span data-ttu-id="797e2-121">**Maximale Kapazität (in Bytes/Sek.)/Zuwachs Rate (in Bytes/s) = Zeit bis Auswirkung (in Sekunden)**</span><span class="sxs-lookup"><span data-stu-id="797e2-121">**Maximum Capacity (in bytes/sec) / Growth Rate (in bytes/sec) = Time to Impact (in sec)**</span></span>

<span data-ttu-id="797e2-122">Wenn die Zeit-zu-Erkennung nach einer Zeit-zu-Wirkung auftritt, ist es wahrscheinlich, dass der DOS-Angriff erfolgreich sein wird.</span><span class="sxs-lookup"><span data-stu-id="797e2-122">If the time-to-detection occurs after time-to-impact, it is likely the DoS attack will be successful.</span></span> <span data-ttu-id="797e2-123">Wenn die Zeit-zu-Erkennung vor Zeit-zu-Wirkung auftritt, sollten die angegriffenen Dienste Online und zugänglich bleiben, wenn Minderungsstrategien verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="797e2-123">If the time-to-detection occurs before time-to-impact, the attacked services should remain online and accessible if mitigation strategies are used.</span></span> <span data-ttu-id="797e2-124">Daher gibt es nur zwei Dinge, die zur Abwehr von DOS-Angriffen ausgeführt werden können:</span><span class="sxs-lookup"><span data-stu-id="797e2-124">Thus, there are only two things that can be done to defend against DoS attacks:</span></span>

- <span data-ttu-id="797e2-125">Erhöhen der Kapazität zur Anhebung der Obergrenze der maximalen Kapazität (was wiederum mehr Zeit zum Erkennen eines Angriffs bietet); oder</span><span class="sxs-lookup"><span data-stu-id="797e2-125">Increase capacity to raise the ceiling of maximum capacity (which in turn provides more time to detect an attack); or</span></span>
- <span data-ttu-id="797e2-126">Verringern Sie die zu erkennende Zeit.</span><span class="sxs-lookup"><span data-stu-id="797e2-126">Decrease the time to detect.</span></span>

<span data-ttu-id="797e2-127">Die zunehmende Kapazität hat eine direkte steuerliche Auswirkung.</span><span class="sxs-lookup"><span data-stu-id="797e2-127">Increasing capacity has a direct fiscal impact.</span></span> <span data-ttu-id="797e2-128">Microsoft empfiehlt, dass Kunden mindestens die grundlegende Absorptionskapazität entwickeln, um sicherzustellen, dass Sie einen gewissen Grad an DOS-Angriffen überleben können.</span><span class="sxs-lookup"><span data-stu-id="797e2-128">Microsoft recommends that customers develop at least basic absorption capacity to ensure that they can survive some level of DoS attack.</span></span> <span data-ttu-id="797e2-129">Die tatsächliche Absorptionskapazität variiert von Kunde zu Kunde, da jeder Kunde über eigene Schwellenwerte für Belichtung, Risiko und finanziellen Aufwand verfügt.</span><span class="sxs-lookup"><span data-stu-id="797e2-129">The actual absorption capacity varies from customer to customer, as each customer has their own thresholds for exposure, risk, and financial outlay.</span></span> <span data-ttu-id="797e2-130">Aus wirtschaftlichen Gründen sind Investitionen in Forschung und Zeit für Methoden zur Verringerung der Zeit-zu-Erkennung in der Regel die kostengünstigste Verteidigung.</span><span class="sxs-lookup"><span data-stu-id="797e2-130">For economic reasons, investments in research and time for ways to decrease time-to-detection are usually the most cost-effective defense.</span></span>