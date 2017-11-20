---
title: GetActivityName | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 479552fa-1535-4f3d-90ff-4615f14c88b1
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 55e8f35746f5f4ed1bbbe10a4d45300895340869
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="getactivityname"></a><span data-ttu-id="aabf9-102">GetActivityName</span><span class="sxs-lookup"><span data-stu-id="aabf9-102">GetActivityName</span></span>
<span data-ttu-id="aabf9-103">Inserta el nombre de la actividad en curso en la pila.</span><span class="sxs-lookup"><span data-stu-id="aabf9-103">Pushes the name of the current activity onto the stack.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aabf9-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="aabf9-104">Syntax</span></span>  
  
```  
  
<wf:Operation Name="GetActivityName"/>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="aabf9-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="aabf9-105">Parameters</span></span>  
 <span data-ttu-id="aabf9-106">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="aabf9-106">None.</span></span>  
  
## <a name="pushed-value"></a><span data-ttu-id="aabf9-107">Valor insertado</span><span class="sxs-lookup"><span data-stu-id="aabf9-107">Pushed Value</span></span>  
 <span data-ttu-id="aabf9-108">Cadena que contiene el nombre de la actividad en curso.</span><span class="sxs-lookup"><span data-stu-id="aabf9-108">String containing the current activity name.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="aabf9-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="aabf9-109">Remarks</span></span>  
 <span data-ttu-id="aabf9-110">Windows Workflow Foundation realiza su trabajo como una serie de actividades configurada por el programador.</span><span class="sxs-lookup"><span data-stu-id="aabf9-110">Windows Workflow Foundation performs its work as a series of activities configured by the developer.</span></span> <span data-ttu-id="aabf9-111">Cada una de estas actividades tiene asignada un nombre único en el flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="aabf9-111">Each of these activities is assigned a unique name within the workflow.</span></span> <span data-ttu-id="aabf9-112">Puede interceptar datos para una actividad específica mediante el filtrado, basándose en su nombre único.</span><span class="sxs-lookup"><span data-stu-id="aabf9-112">You can intercept data for a specific activity by filtering based on its unique name.</span></span>  
  
## <a name="example"></a><span data-ttu-id="aabf9-113">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="aabf9-113">Example</span></span>  
 <span data-ttu-id="aabf9-114">El siguiente ejemplo contiene una expresión de filtro de eventos configurada para buscar una actividad específica, FoodAndDrinksPolicy, en un flujo de trabajo cerrado.</span><span class="sxs-lookup"><span data-stu-id="aabf9-114">The following sample contains an event filter expression configured to find a specific activity—FoodAndDrinksPolicy—in a Closed workflow.</span></span> <span data-ttu-id="aabf9-115">Para ello, se usa una combinación de operaciones, incluidas `GetActivityName`, `GetActivityEvent` y operaciones lógicas.</span><span class="sxs-lookup"><span data-stu-id="aabf9-115">This is done by using a combination of operations including `GetActivityName`, `GetActivityEvent`, and logical operations.</span></span>  
  
```  
<ic:Filter>  
  <ic:Expression>  
    <wf:Operation Name="GetActivityName"/>  
    <ic:Operation Name="Constant">  
      <ic:Argument>FoodAndDrinksPolicy</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals"/>  
    <wf:Operation Name="GetActivityEvent"/>  
    <ic:Operation Name="Constant">  
      <ic:Argument>Closed</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals"/>  
    <ic:Operation Name="And"/>  
  </ic:Expression>  
</ic:Filter>  
```  
  
 <span data-ttu-id="aabf9-116">Este patrón de filtro es habitual con los archivos de configuración del interceptor de Windows Workflow Foundation.</span><span class="sxs-lookup"><span data-stu-id="aabf9-116">This filter pattern is common with Windows Workflow Foundation interceptor configuration files.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="aabf9-117">Los argumentos no requieren comillas dobles a menos que intente hacer coincidir, de forma explícita, una cadena que contiene comillas dobles.</span><span class="sxs-lookup"><span data-stu-id="aabf9-117">Arguments do not require quotation marks unless you are explicitly trying to match a string that contains quotation marks.</span></span>