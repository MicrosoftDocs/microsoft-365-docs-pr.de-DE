---
title: Adressraumrechner für Azure-Gatewaysubnetze
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 01/07/2021
audience: ITPro
ms.topic: hub-page
ms.service: o365-administration
localization_priority: Normal
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom:
- PowerShell
- Ent_Office_Other
- seo-marvel-apr2020
description: 'Zusammenfassung: Berechnen Sie den Adressraum eines Azure-Gatewaysubnetzes mit C3, Python oder PowerShell.'
ms.openlocfilehash: d92bea5c36fde6277154d19365ed0bdaa5df4254
ms.sourcegitcommit: ec293978e951b09903b79e6642aa587824935e0c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/07/2021
ms.locfileid: "49780568"
---
# <a name="address-space-calculator-for-azure-gateway-subnets"></a><span data-ttu-id="f7725-103">Adressraumrechner für Azure-Gatewaysubnetze</span><span class="sxs-lookup"><span data-stu-id="f7725-103">Address space calculator for Azure gateway subnets</span></span>

<span data-ttu-id="f7725-104">Ein virtuelles Netzwerk (VNet) in Azure-Infrastrukturdiensten, das mit anderen Netzwerken verbunden ist, muss über ein Gatewaysubnetz verfügen.</span><span class="sxs-lookup"><span data-stu-id="f7725-104">A virtual network (VNet) in Azure infrastructure services that is connected to other networks must have a gateway subnet.</span></span> <span data-ttu-id="f7725-105">Die bewährten Methoden zum Definieren des Gatewaysubnetzes sind:</span><span class="sxs-lookup"><span data-stu-id="f7725-105">The best practices for defining the gateway subnet are:</span></span>

- <span data-ttu-id="f7725-106">Die Präfixlänge des Gatewaysubnetzes kann eine maximale Präfixlänge von 29 haben (z. B. 10.119.255.248/29), aber die aktuelle Empfehlung ist, dass Sie eine Präfixlänge von 27 verwenden (z. B. 10.119.255.224/27).</span><span class="sxs-lookup"><span data-stu-id="f7725-106">The prefix length of the gateway subnet can have a maximum prefix length of 29 (for example, 10.119.255.248/29), but the current recommendation is that you use a prefix length of 27 (for example, 10.119.255.224/27).</span></span>
- <span data-ttu-id="f7725-107">Verwenden Sie beim Definieren des Adressraums des Gatewaysubnetzes den letzten Teil des VNet-Adressraums.</span><span class="sxs-lookup"><span data-stu-id="f7725-107">When defining the address space of the gateway subnet, use the last part of the VNet address space.</span></span>

<span data-ttu-id="f7725-108">Für die zweite Empfehlung können Sie den Adressraum des Gatewaysubnetzes bestimmen, indem Sie die für das Gatewaysubnetz verwendeten Bits auf 0 und die verbleibenden Bits im VNet-Adressraum auf 1 festlegen.</span><span class="sxs-lookup"><span data-stu-id="f7725-108">For the second recommendation, you can determine the address space of the gateway subnet by setting the bits used for the gateway subnet to 0 and the remaining bits in the VNet address space to 1.</span></span> <span data-ttu-id="f7725-109">Um den Adressraum des Gatewaysubnetzs schnell zu berechnen, ohne in binäre und zurück in Dezimalzahlen konvertieren zu müssen, können Sie eine Konsolenanwendung verwenden, die in C# oder Python oder mit einem PowerShell-Befehlsblock geschrieben wurde.</span><span class="sxs-lookup"><span data-stu-id="f7725-109">To quickly calculate the gateway subnet address space without having to convert to binary and back to decimal, you can use a console application written in C# or Python or with a PowerShell command block.</span></span>

<span data-ttu-id="f7725-110">Dieser Artikel enthält C#-, Python- und PowerShell-Codeblöcke, die den Adressraum des Gatewaysubnetzs basierend auf den Werten von w.x.y.z/n für das VNet-Adresspräfix und die Länge des Gatewaysubnetzpräfixs berechnen.</span><span class="sxs-lookup"><span data-stu-id="f7725-110">This article contains C#, Python, and PowerShell code blocks that calculate the gateway subnet address space based on the values of w.x.y.z/n for the VNet address prefix and the gateway subnet prefix length.</span></span>

## <a name="c-code-block"></a><span data-ttu-id="f7725-111">C# Codeblock</span><span class="sxs-lookup"><span data-stu-id="f7725-111">C# code block</span></span>

<span data-ttu-id="f7725-112">Verwenden Sie diesen Codeblock, um eine Konsolen-App in einem C#.</span><span class="sxs-lookup"><span data-stu-id="f7725-112">Use this code block to create a console app in C#.</span></span>

```c#
using System; 
using System.Collections.Generic; 
using System.Linq; 
using System.Text; 
using System.Threading.Tasks; 
 
namespace ConsoleApplication1 
{ 
    class Program 
    { 
        static void Main(string[] args) 
        { 
            // Declare variables. 
            const long wOctet = 16777216;  
            const long xOctet = 65536; 
            const long yOctet = 256; 
            double D; 
            int w, x, y, z, vnetPrefLen, gwPrefLen; 
            long d, w2, x2, y2, z2; 
             
 
            // Get the five values needed from the keyboard. 
            Console.WriteLine("**************************************************************************"); 
            Console.WriteLine("**_ Gateway subnet address space calculator for Azure virtual networks _*_");             
            Console.WriteLine("_*************************************************************************");  
            Console.WriteLine(); 
            Console.WriteLine("Please supply your virtual network address space in the form of w.x.y.z/n."); 
            Console.WriteLine(); 
            Console.WriteLine("w="); 
            w = Convert.ToInt32(Console.ReadLine()); 
            Console.WriteLine("x="); 
            x = Convert.ToInt32(Console.ReadLine()); 
            Console.WriteLine("y="); 
            y = Convert.ToInt32(Console.ReadLine()); 
            Console.WriteLine("z="); 
            z = Convert.ToInt32(Console.ReadLine()); 
            Console.WriteLine("n="); 
            vnetPrefLen = Convert.ToInt32(Console.ReadLine()); 
            Console.WriteLine(); 
            Console.WriteLine("Now supply the prefix length of your gateway subnet:"); 
            gwPrefLen = Convert.ToInt32(Console.ReadLine()); 
            Console.WriteLine(); 
 
            // Perform the calculation. 
            D = w * wOctet + x * xOctet + y * yOctet + z; 
            for (int i = vnetPrefLen + 1; i < gwPrefLen + 1; i++) 
            { 
                D = D + Math.Pow(2, 32 - i); 
            } 
            d = Convert.ToInt64(D); 
            w2 = d / wOctet; 
            x2 = (d - w2 * wOctet) / xOctet;  
            y2 = (d - w2 * wOctet - x2 * xOctet) / yOctet; 
            z2 = d - w2 * wOctet - x2 * xOctet - y2 * yOctet; 
             
            // Display the result.             
            Console.WriteLine("**************************************************************************");  
            Console.WriteLine("For the Azure virtual address space {0}.{1}.{2}.{3}/{4}", w, x, y, z, vnetPrefLen); 
            Console.WriteLine("and gateway prefix length of {0}, the gateway subnet address space is:", gwPrefLen); 
            Console.WriteLine(); 
            Console.WriteLine("{0}.{1}.{2}.{3}/{4}", w2, x2, y2, z2, gwPrefLen); 
            Console.WriteLine(); 
            Console.WriteLine("Press ENTER to quit."); 
            Console.ReadLine(); 
        } 
    } 
} 
```

## <a name="python-code-block"></a><span data-ttu-id="f7725-113">Python-Codeblock</span><span class="sxs-lookup"><span data-stu-id="f7725-113">Python code block</span></span>

<span data-ttu-id="f7725-114">Verwenden Sie diesen Codeblock, um eine Konsolen-App in Python zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="f7725-114">Use this code block to create a console app in Python.</span></span>

```python
import math 
# Collect the values of w.x.y.z/n for your VNet address space and g, the prefix length of your gateway subnet 
print("**************************************************************************")  
print("**_ Gateway subnet address space calculator for Azure virtual networks _*_")  
print("_*************************************************************************\n")   
print("Please supply your virtual network address space in the form of w.x.y.z/n.");  
w=int(input("w = ")) 
x=int(input("x = ")) 
y=int(input("y = ")) 
z=int(input("z = ")) 
n=int(input("n = ")) 
print("")  
g=int(input("Now supply the prefix length of your gateway subnet: ")) 
print("")  
 
# Calculate  
wOctet = 16777216  
xOctet = 65536  
yOctet = 256  
D = w * wOctet + x * xOctet + y * yOctet + z 
for index in range(n + 1,g + 1): 
    D += 2**(32 - index)  
 
w2 = math.floor(D / wOctet)  
x2 = math.floor((D - w2 * wOctet) / xOctet) 
y2 = math.floor((D - w2 * wOctet - x2 * xOctet) / yOctet) 
z2 = D - w2 * wOctet - x2 * xOctet - y2 * yOctet  
 
# Display the result  
gwAddrPref= "Your gateway address prefix is: " + str(w2) + "." + str(x2) + "." + str(y2) + "." + str(z2) + "/" + str(g)  
print(gwAddrPref) 
```


## <a name="powershell-command-block"></a><span data-ttu-id="f7725-115">PowerShell-Befehlsblock</span><span class="sxs-lookup"><span data-stu-id="f7725-115">PowerShell command block</span></span>

<span data-ttu-id="f7725-116">Füllen Sie die Werte aus, und führen Sie den resultierenden Befehlsblock in einem PowerShell-Fenster oder in der integrierten PowerShell-Skriptumgebung (ISE) aus.</span><span class="sxs-lookup"><span data-stu-id="f7725-116">Fill in the values and run the resulting command block in a PowerShell window or in the PowerShell Integrated Script Environment (ISE).</span></span>

```powershell
# Specify the values of w.x.y.z/n for your VNet address space and g, the prefix length of your gateway subnet: 
$w= 
$x= 
$y= 
$z= 
$n= 
$g= 
# Calculate 
$wOctet = 16777216 
$xOctet = 65536 
$yOctet = 256 
[long]$D = $w * $wOctet + $x * $xOctet + $y * $yOctet + $z; 
for ($i = $n + 1; $i -lt $g + 1; $i++) 
{ 
$D = $D + [math]::pow(2, 32 - $i) 
} 
$w2 = [math]::floor($D / $wOctet) 
$x2 = [math]::floor( ($D - $w2 * $wOctet) / $xOctet ) 
$y2 = [math]::floor( ($D - $w2 * $wOctet - $x2 * $xOctet) / $yOctet ) 
$z2 = $D - $w2 * $wOctet - $x2 * $xOctet - $y2 * $yOctet 
# Display the result 
$dx= [string]$w2 + "." + [string]$x2 + "." + [string]$y2 + "." + [string]$z2 + "/" + [string]$g 
Write-Host "Your gateway address prefix is: " $dx
```
    
## <a name="related-topics"></a><span data-ttu-id="f7725-117">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="f7725-117">Related topics</span></span>

[<span data-ttu-id="f7725-118">Verwalten von Microsoft 365 mit PowerShell</span><span class="sxs-lookup"><span data-stu-id="f7725-118">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)