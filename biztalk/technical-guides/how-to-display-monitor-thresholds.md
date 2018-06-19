---
title: Cómo mostrar umbrales del Monitor | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 88d88b15-0691-49d9-b116-1a2ae95bead9
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: be3818512f76e95655e0441f039176fe6f855344
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22297708"
---
# <a name="how-to-display-monitor-thresholds"></a><span data-ttu-id="ac476-102">Cómo mostrar umbrales del Monitor</span><span class="sxs-lookup"><span data-stu-id="ac476-102">How to Display Monitor Thresholds</span></span>
<span data-ttu-id="ac476-103">Para mostrar umbrales del monitor, use el script descrito en esta sección.</span><span class="sxs-lookup"><span data-stu-id="ac476-103">To display monitor thresholds, use the script described in this section.</span></span> <span data-ttu-id="ac476-104">Este script funciona para la mayoría de los monitores.</span><span class="sxs-lookup"><span data-stu-id="ac476-104">This script works for the majority of monitors.</span></span> <span data-ttu-id="ac476-105">Crea un archivo .csv que incluye las columnas descritas en la siguiente tabla y puede verse mediante Office Excel.</span><span class="sxs-lookup"><span data-stu-id="ac476-105">It creates a .csv file that includes the columns described in the following table, and can be viewed using Office Excel.</span></span>  
  
|<span data-ttu-id="ac476-106">Columna</span><span class="sxs-lookup"><span data-stu-id="ac476-106">Column</span></span>|<span data-ttu-id="ac476-107">Description</span><span class="sxs-lookup"><span data-stu-id="ac476-107">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="ac476-108">Tipo</span><span class="sxs-lookup"><span data-stu-id="ac476-108">Type</span></span>|<span data-ttu-id="ac476-109">El tipo de objetos que supervisa el monitor.</span><span class="sxs-lookup"><span data-stu-id="ac476-109">The type of objects the monitor is targeted.</span></span>|  
|<span data-ttu-id="ac476-110">DisplayName</span><span class="sxs-lookup"><span data-stu-id="ac476-110">DisplayName</span></span>|<span data-ttu-id="ac476-111">El nombre para mostrar del monitor.</span><span class="sxs-lookup"><span data-stu-id="ac476-111">The display name of the monitor.</span></span>|  
|<span data-ttu-id="ac476-112">Umbral</span><span class="sxs-lookup"><span data-stu-id="ac476-112">Threshold</span></span>|<span data-ttu-id="ac476-113">El umbral utilizado por el monitor.</span><span class="sxs-lookup"><span data-stu-id="ac476-113">The threshold used by the monitor.</span></span>|  
|<span data-ttu-id="ac476-114">AlertOnState</span><span class="sxs-lookup"><span data-stu-id="ac476-114">AlertOnState</span></span>|<span data-ttu-id="ac476-115">Determina si el monitor genera una alerta cuando cambia el estado.</span><span class="sxs-lookup"><span data-stu-id="ac476-115">Determines whether the monitor generates an alert when the state changes.</span></span>|  
|<span data-ttu-id="ac476-116">AutoResolveAlert</span><span class="sxs-lookup"><span data-stu-id="ac476-116">AutoResolveAlert</span></span>|<span data-ttu-id="ac476-117">Determina si la alerta generada se resolverá automáticamente cuando el estado del monitor vuelve a verde.</span><span class="sxs-lookup"><span data-stu-id="ac476-117">Determines whether the generated alert will be automatically resolved when the monitor state goes back to green.</span></span>|  
|<span data-ttu-id="ac476-118">AlertSeverity</span><span class="sxs-lookup"><span data-stu-id="ac476-118">AlertSeverity</span></span>|<span data-ttu-id="ac476-119">La gravedad de la alerta generada.</span><span class="sxs-lookup"><span data-stu-id="ac476-119">The severity of the generated alert.</span></span>|  
  
#### <a name="to-display-monitor-thresholds"></a><span data-ttu-id="ac476-120">Para mostrar umbrales del monitor</span><span class="sxs-lookup"><span data-stu-id="ac476-120">To display monitor thresholds</span></span>  
 <span data-ttu-id="ac476-121">Ejecute el script siguiente para crear el archivo .csv que muestra los umbrales de monitor:</span><span class="sxs-lookup"><span data-stu-id="ac476-121">Run the following script to create the .csv file that displays the monitor thresholds:</span></span>  
  
```  
function GetThreshold ([String] $configuration)   
{   
  $config = [xml] ("<config>" + $configuration + "</config>")   
  $threshold = $config.Config.Threshold   
  if($threshold -eq $null)   
  {   
    $threshold = $config.Config.MemoryThreshold   
  }   
  if($threshold -eq $null)   
  {   
    $threshold = $config.Config.CPUPercentageThreshold   
  }   
  if($threshold -eq $null)   
  {   
    if($config.Config.Threshold1 -ne $null -and $config.Config.Threshold2 -ne $null)   
    {   
      $threshold = "first threshold is: " + $config.Config.Threshold1 + " second threshold is: " + $config.Config.Threshold2   
    }   
  }   
  if($threshold -eq $null)   
  {   
    if($config.Config.ThresholdWarnSec -ne $null -and $config.Config.ThresholdErrorSec -ne $null)   
    {   
      $threshold = "warning threshold is: " + $config.Config.ThresholdWarnSec + " error threshold is: " + $config.Config.ThresholdErrorSec   
    }   
  }   
  if($threshold -eq $null)   
  {   
    if($config.Config.LearningAndBaseliningSettings -ne $null)   
    {   
      $threshold = "no threshold (baseline monitor)"   
    }   
  }   
  return $threshold   
}   
#$perfMonitors = get-monitor -Criteria:"IsUnitMonitor=1 and Category='PerformanceHealth'"   
$perfMonitors = Get-ScommanagementPack -DisplayName "BizTalk Server Monitoring" | get-scommonitor | where-object{$_.XmlTag -eq "UnitMonitor" -and $_.Category -eq "PerformanceHealth"}  
  
$perfMonitors | select-object @{name="Target";expression={foreach-object {(Get-SCOMClass -Id:$_.Target.Id).DisplayName}}},DisplayName, @{name="Threshold";expression={foreach-object {GetThreshold $_.Configuration}}}, @{name="AlertOnState";expression={foreach-object {$_.AlertSettings.AlertOnState}}}, @{name="AutoResolveAlert";expression={foreach-object {$_.AlertSettings.AutoResolve}}}, @{name="AlertSeverity";expression={foreach-object {$_.AlertSettings.AlertSeverity}}} | sort Target, DisplayName | export-csv "c:\monitor_thresholds.csv"  
  
```