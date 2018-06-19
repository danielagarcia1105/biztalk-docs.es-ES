---
title: Cómo mostrar las reglas de recopilación de rendimiento | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 546aa853-c372-4e26-a1ed-19294c658583
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cd7b7d1d2e368572740a3c7a54799bc56b2330e3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22298188"
---
# <a name="how-to-display-performance-collection-rules"></a><span data-ttu-id="7c81e-102">Cómo mostrar las reglas de recopilación de rendimiento</span><span class="sxs-lookup"><span data-stu-id="7c81e-102">How to Display Performance Collection Rules</span></span>
<span data-ttu-id="7c81e-103">Para mostrar las reglas de recopilación de rendimiento, utilice la secuencia de comandos de esta sección.</span><span class="sxs-lookup"><span data-stu-id="7c81e-103">To display performance collection rules, use the script in this section.</span></span> <span data-ttu-id="7c81e-104">Este script funciona para la mayoría de las reglas.</span><span class="sxs-lookup"><span data-stu-id="7c81e-104">This script works for the majority of rules.</span></span> <span data-ttu-id="7c81e-105">Crea un archivo .csv que incluye las columnas enumeradas en la siguiente tabla y puede verse mediante Office Excel.</span><span class="sxs-lookup"><span data-stu-id="7c81e-105">It creates a .csv file that includes the columns listed in the following table, and can be viewed using Office Excel.</span></span>  
  
|<span data-ttu-id="7c81e-106">Columna</span><span class="sxs-lookup"><span data-stu-id="7c81e-106">Column</span></span>|<span data-ttu-id="7c81e-107">Description</span><span class="sxs-lookup"><span data-stu-id="7c81e-107">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="7c81e-108">WriteToDB o CollectionPerformanceData</span><span class="sxs-lookup"><span data-stu-id="7c81e-108">WriteToDB or CollectionPerformanceData</span></span>|<span data-ttu-id="7c81e-109">Escribe en la base de datos de Operations Manager.</span><span class="sxs-lookup"><span data-stu-id="7c81e-109">Writes to the Operations Manager database.</span></span>|  
|<span data-ttu-id="7c81e-110">WriteToDW o CollectPerfDataWarehouse</span><span class="sxs-lookup"><span data-stu-id="7c81e-110">WriteToDW or CollectPerfDataWarehouse</span></span>|<span data-ttu-id="7c81e-111">Escribe en el almacén de datos.</span><span class="sxs-lookup"><span data-stu-id="7c81e-111">Writes to the data warehouse.</span></span>|  
|<span data-ttu-id="7c81e-112">CENTRO DE TRABAJO</span><span class="sxs-lookup"><span data-stu-id="7c81e-112">WC</span></span>|<span data-ttu-id="7c81e-113">Almacena los datos de un contador de rendimiento de línea base en la base de datos operativa.</span><span class="sxs-lookup"><span data-stu-id="7c81e-113">Stores baseline data for a performance counter into the operational database.</span></span>|  
  
#### <a name="to-display-performance-collection-rules"></a><span data-ttu-id="7c81e-114">Para mostrar las reglas de recopilación de rendimiento</span><span class="sxs-lookup"><span data-stu-id="7c81e-114">To display performance collection rules</span></span>  
 <span data-ttu-id="7c81e-115">Para mostrar las reglas de recopilación de rendimiento en el grupo de administración, ejecute el script siguiente:</span><span class="sxs-lookup"><span data-stu-id="7c81e-115">To display the performance collection rules in the management group, run the following script:</span></span>  
  
```  
function GetPerfCounterName ([String] $configuration)   
{   
$config = [xml] ("<config>" + $configuration + "</config>")   
return ($config.Config.ObjectName + "\" + $config.Config.CounterName)   
}   
function GetFrequency ([String] $configuration)   
{   
$config = [xml] ("<config>" + $configuration + "</config>")   
$frequency = $config.Config.Frequency;   
if($frequency -eq $null)   
{   
$frequency = $config.Config.IntervalSeconds;   
}   
return ($frequency)   
}   
function GetDisplayName($performanceRule)   
{   
if($performanceRule.DisplayName -eq $null)   
{   
return ($performanceRule.Name);   
}   
else   
{   
return ($performanceRule.DisplayName);   
}   
}   
function GetWriteActionNames($performanceRule)   
{   
$writeActions = "";   
foreach($writeAction in $performanceRule.WriteActionCollection)   
{   
$writeActions += " " + $writeAction.Name;   
}   
return ($writeActions);   
}   
$perf_collection_rules = Get-SCOMManagementPack -DisplayName "BizTalk Server Monitoring" | Get-SCOMRule | where-object{$_.Category -eq "PerformanceCollection"}  
  
$perf_collection_rules | select-object @{name="Type";expression={foreach-object {(Get-SCOMClass -id:$_.Target.Id).DisplayName}}},@{name="RuleDisplayName";expression={foreach-object {GetDisplayName $_}}} ,@{name="CounterName";expression={foreach-object {GetPerfCounterName $_.DataSourceCollection[0].Configuration}}},@{name="Frequency";expression={foreach-object {GetFrequency $_.DataSourceCollection[0].Configuration}}},@{name="WriteActions";expression={foreach-object {GetWriteActionNames $_}}} | sort Type,RuleDisplayName,CounterName | export-csv "c:\perf_collection_rules.csv"  
  
```