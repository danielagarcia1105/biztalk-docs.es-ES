---
title: Las rutas de acceso de bucle | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Looping functoids, paths
- maps, conditional looping
ms.assetid: 4612dc2d-2c39-427d-88ac-65f9e85873c7
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e69e7d1c092ee5ca34b8c2ef3f309eff6c44b271
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22262156"
---
# <a name="loop-paths"></a><span data-ttu-id="a5b6d-102">Rutas de bucle</span><span class="sxs-lookup"><span data-stu-id="a5b6d-102">Loop Paths</span></span>
<span data-ttu-id="a5b6d-103">Un elemento en un esquema está en bucle si su propiedad Max Occurs es mayor que 1.</span><span class="sxs-lookup"><span data-stu-id="a5b6d-103">An element in a schema is looping if its Max Occurs property is greater than 1.</span></span> <span data-ttu-id="a5b6d-104">Una ruta de acceso de bucle se produce cuando se dibuja un vínculo entre un elemento de bucle del esquema de origen y un elemento de bucle del esquema de destino.</span><span class="sxs-lookup"><span data-stu-id="a5b6d-104">A loop path occurs when you draw a link between a looping element in the source schema and a looping element in the destination schema.</span></span>  
  
## <a name="configuring-a-loop-path"></a><span data-ttu-id="a5b6d-105">Configurar una ruta de bucle</span><span class="sxs-lookup"><span data-stu-id="a5b6d-105">Configuring a Loop Path</span></span>  
 <span data-ttu-id="a5b6d-106">El asignador de BizTalk controla automáticamente los registros de bucle cuando se crea una ruta de acceso de bucle.</span><span class="sxs-lookup"><span data-stu-id="a5b6d-106">BizTalk Mapper automatically handles the looping records when you create a loop path.</span></span>  
  
 <span data-ttu-id="a5b6d-107">Puede configurar una ruta de bucle en una asignación vinculando un campo de un registro de bucle del esquema de origen con un campo de un registro de bucle del esquema de destino.</span><span class="sxs-lookup"><span data-stu-id="a5b6d-107">You can configure a loop path in a map by linking a field in a looping record in the source schema to a field that is in a looping record in the destination schema.</span></span> <span data-ttu-id="a5b6d-108">La ilustración siguiente muestra una asignación que copia solo registros de encuestas de comida a una lista de direcciones maestra.</span><span class="sxs-lookup"><span data-stu-id="a5b6d-108">The figure below shows a map that copies only food survey records into a master address list.</span></span>  
  
 <span data-ttu-id="a5b6d-109">![Mapa que ilustra el uso de una ruta de acceso de bucle. ] (../core/media/correct-loop-path-map.gif "correct_loop_path_map")</span><span class="sxs-lookup"><span data-stu-id="a5b6d-109">![Map illustrating the use of a loop path.](../core/media/correct-loop-path-map.gif "correct_loop_path_map")</span></span>  
<span data-ttu-id="a5b6d-110">Asignación de ruta de acceso</span><span class="sxs-lookup"><span data-stu-id="a5b6d-110">Loop Path Map</span></span>  
  
## <a name="multiple-loop-paths"></a><span data-ttu-id="a5b6d-111">Varias rutas de bucle</span><span class="sxs-lookup"><span data-stu-id="a5b6d-111">Multiple Loop Paths</span></span>  
 <span data-ttu-id="a5b6d-112">En una asignación se produce una ruta de bucle múltiple al vincular campos incluidos en dos o más registros de bucle con campos incluidos en un registro de bucle simple.</span><span class="sxs-lookup"><span data-stu-id="a5b6d-112">A multiple loop path occurs in a map when you link fields contained by two or more looping records to fields contained in a single looping record.</span></span> <span data-ttu-id="a5b6d-113">En la siguiente ilustración se muestra cómo se intentan combinar direcciones recopiladas de dos encuestas diferentes en una única lista de direcciones maestra.</span><span class="sxs-lookup"><span data-stu-id="a5b6d-113">The following figure shows an attempt to combine addresses collected from two different surveys into a single master address list.</span></span>  
  
 <span data-ttu-id="a5b6d-114">![Asignación con varias rutas de bucle](../core/media/multiple-loop-path-map.gif "multiple_loop_path_map")</span><span class="sxs-lookup"><span data-stu-id="a5b6d-114">![Map with multiple loop paths](../core/media/multiple-loop-path-map.gif "multiple_loop_path_map")</span></span>  
<span data-ttu-id="a5b6d-115">Asignación con varias rutas de bucle (incorrecto)</span><span class="sxs-lookup"><span data-stu-id="a5b6d-115">Map With Multiple Loop Paths (Incorrect)</span></span>  
  
 <span data-ttu-id="a5b6d-116">Esta asignación no producirá los resultados esperados.</span><span class="sxs-lookup"><span data-stu-id="a5b6d-116">This map will not produce the expected results.</span></span> <span data-ttu-id="a5b6d-117">Cuando el Asignador encuentra varias rutas de bucle durante la compilación, genera una advertencia y selecciona la primera ruta de bucle de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="a5b6d-117">When the Mapper encounters multiple loop paths during compilation, it produces a warning and selects the first loop path by default.</span></span> <span data-ttu-id="a5b6d-118">Para combinar las dos direcciones diferentes en una lista de direcciones maestra única, utilice un **bucle** functoid tal como se muestra en la asignación siguiente.</span><span class="sxs-lookup"><span data-stu-id="a5b6d-118">In order to combine the two different addresses into a single master address list, use a **Looping** functoid as shown in the map below.</span></span>  
  
 <span data-ttu-id="a5b6d-119">![Mapa que ilustra el uso del functoid de bucle. ] (../core/media/loopingfunctoid.gif "loopingfunctoid")</span><span class="sxs-lookup"><span data-stu-id="a5b6d-119">![Map illustrating the use of the looping functoid.](../core/media/loopingfunctoid.gif "loopingfunctoid")</span></span>  
<span data-ttu-id="a5b6d-120">Asignación con functoid de bucle (correcto)</span><span class="sxs-lookup"><span data-stu-id="a5b6d-120">Looping Functoid Map (Correct)</span></span>  
  
 <span data-ttu-id="a5b6d-121">El **bucle** functoid debe usarse en lugar de varias rutas de bucle en los escenarios siguientes:</span><span class="sxs-lookup"><span data-stu-id="a5b6d-121">The **Looping** functoid should be used instead of multiple loop paths in the following scenarios:</span></span>  
  
1.  <span data-ttu-id="a5b6d-122">Cuándo el Asignador no genera el resultado deseado en un escenario de varias rutas de bucle.</span><span class="sxs-lookup"><span data-stu-id="a5b6d-122">When the Mapper does not produce the desired output in a multiple loop paths scenario.</span></span>  
  
2.  <span data-ttu-id="a5b6d-123">Para combinar varias estructuras de repetición en un mensaje de instancia de entrada en una única estructura de repetición en el mensaje de instancia de salida.</span><span class="sxs-lookup"><span data-stu-id="a5b6d-123">To combine multiple repeating structures in an input instance message into a single repeating structure in the output instance message.</span></span>  
  
3.  <span data-ttu-id="a5b6d-124">Para convertir un esquema sin formato en un esquema jerárquico asignando un único registro a múltiples registros.</span><span class="sxs-lookup"><span data-stu-id="a5b6d-124">To convert a flat schema to a hierarchical schema by mapping a single record to multiple records.</span></span> <span data-ttu-id="a5b6d-125">Ésta es una operación común para convertir esquemas sin formato en catálogos de Microsoft Commerce Server.</span><span class="sxs-lookup"><span data-stu-id="a5b6d-125">This is a common operation in converting flat schemas to Microsoft Commerce Server catalogs.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a5b6d-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="a5b6d-126">See Also</span></span>  
 <span data-ttu-id="a5b6d-127">[Cómo agregar Functoids a una asignación de bucle](../core/how-to-add-looping-functoids-to-a-map.md) </span><span class="sxs-lookup"><span data-stu-id="a5b6d-127">[How to Add Looping Functoids to a Map](../core/how-to-add-looping-functoids-to-a-map.md) </span></span>  
 [<span data-ttu-id="a5b6d-128">Functoid de bucle</span><span class="sxs-lookup"><span data-stu-id="a5b6d-128">Looping Functoid</span></span>](../core/looping-functoid.md)