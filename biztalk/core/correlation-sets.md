---
title: Conjuntos de correlaciones | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- correlation sets, inspecting
- correlation sets, about correlation sets
- correlation sets, passing as parameters
- messages, correlation sets
- correlation sets
- correlation sets, following correlation sets
- correlation sets, initializing
ms.assetid: 528dcd6c-d364-4bb8-8deb-cd4a0791867f
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 09bad0bf41f5b509f9a64e9484cac84f66a84e4b
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="correlation-sets"></a><span data-ttu-id="b60fb-102">Conjuntos de correlaciones</span><span class="sxs-lookup"><span data-stu-id="b60fb-102">Correlation Sets</span></span>
<span data-ttu-id="b60fb-103">Este tipo de correlación de mensajes con instancias de orquestación se consigue mediante la definición de conjuntos de correlaciones.</span><span class="sxs-lookup"><span data-stu-id="b60fb-103">You can achieve this sort of correlation of messages with orchestration instances by defining correlation sets.</span></span> <span data-ttu-id="b60fb-104">Un conjunto de correlaciones es un conjunto de propiedades *con valores específicos*.</span><span class="sxs-lookup"><span data-stu-id="b60fb-104">A correlation set is a set of properties *with specific values*.</span></span> <span data-ttu-id="b60fb-105">Es diferente de un tipo de correlación, que no es más que una lista de propiedades.</span><span class="sxs-lookup"><span data-stu-id="b60fb-105">This is different from a correlation type, which is simply a list of properties.</span></span> <span data-ttu-id="b60fb-106">Si un mensaje entrante no tiene todas estas propiedades, con valores coincidentes para cada una de ellas, se producirá un error en la correlación y la instancia de orquestación no recibirá el mensaje.</span><span class="sxs-lookup"><span data-stu-id="b60fb-106">If an incoming message does not have all of these properties, with matching values for each, correlation will fail and the message will not be received by the orchestration instance.</span></span>  
  
 <span data-ttu-id="b60fb-107">Los tipos de correlación definen un conjunto de propiedades en el que se correlacionarán mensajes.</span><span class="sxs-lookup"><span data-stu-id="b60fb-107">Correlation types define a set of properties on which you will be correlating messages.</span></span> <span data-ttu-id="b60fb-108">Éstos pueden ser cualquier propiedad definida anteriormente en un esquema de propiedades e implementada con algún proyecto de BizTalk, incluidas las propiedades del sistema implementadas con GlobalPropertySchemas, que se instala como parte de la instalación básica de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="b60fb-108">These can be any properties which were previously defined in a property schema and deployed with some BizTalk Project including "system" properties deployed with the GlobalPropertySchemas which is installed as part of the base BizTalk install.</span></span> <span data-ttu-id="b60fb-109">Un conjunto de correlaciones define un conjunto de propiedades, así como de valores de estas últimas, que un mensaje debe contener para que su procesamiento se efectúe en una orquestación concreta.</span><span class="sxs-lookup"><span data-stu-id="b60fb-109">A correlation set defines a set of properties and values for these properties that a message must contain to be processed by a particular orchestration.</span></span>  
  
 <span data-ttu-id="b60fb-110">Por ejemplo, un tipo de correlación se compondría de las propiedades siguientes:</span><span class="sxs-lookup"><span data-stu-id="b60fb-110">For example, a correlation type could consist of the following properties:</span></span>  
  
|<span data-ttu-id="b60fb-111">Tipo de correlación (propiedad)</span><span class="sxs-lookup"><span data-stu-id="b60fb-111">Correlation Type Property</span></span>|<span data-ttu-id="b60fb-112">Posible representación XML</span><span class="sxs-lookup"><span data-stu-id="b60fb-112">Possible XML Representation</span></span>|  
|-------------------------------|---------------------------------|  
|<span data-ttu-id="b60fb-113">Número de la seguridad social</span><span class="sxs-lookup"><span data-stu-id="b60fb-113">Social Security number</span></span>|<span data-ttu-id="b60fb-114">\<Nº DE SS\>\</SSN\></span><span class="sxs-lookup"><span data-stu-id="b60fb-114">\<SSN\>\</SSN\></span></span>|  
|<span data-ttu-id="b60fb-115">Fecha de nacimiento</span><span class="sxs-lookup"><span data-stu-id="b60fb-115">Date of Birth</span></span>|<span data-ttu-id="b60fb-116">\<FECHA DE NACIMIENTO\>\</DOB\></span><span class="sxs-lookup"><span data-stu-id="b60fb-116">\<DOB\>\</DOB\></span></span>|  
|<span data-ttu-id="b60fb-117">Gender</span><span class="sxs-lookup"><span data-stu-id="b60fb-117">Gender</span></span>|<span data-ttu-id="b60fb-118">\<Sexo\> \< /género\></span><span class="sxs-lookup"><span data-stu-id="b60fb-118">\<Gender\>\</Gender\></span></span>|  
  
 <span data-ttu-id="b60fb-119">Mientras que un conjunto de correlación derivado de este tipo de correlación constaría de las propiedades y valores siguientes:</span><span class="sxs-lookup"><span data-stu-id="b60fb-119">While a correlation set derived from this correlation type could consist of the following properties and values:</span></span>  
  
|<span data-ttu-id="b60fb-120">Propiedad o valor del conjunto de correlación</span><span class="sxs-lookup"><span data-stu-id="b60fb-120">Correlation Set Property/Value</span></span>|<span data-ttu-id="b60fb-121">Posible representación XML</span><span class="sxs-lookup"><span data-stu-id="b60fb-121">Possible XML representation</span></span>|  
|-------------------------------------|---------------------------------|  
|<span data-ttu-id="b60fb-122">Número de la seguridad social = 222112222</span><span class="sxs-lookup"><span data-stu-id="b60fb-122">Social Security number = 222112222</span></span>|<span data-ttu-id="b60fb-123">\<Nº DE SS\>222112222\</SSN\></span><span class="sxs-lookup"><span data-stu-id="b60fb-123">\<SSN\>222112222\</SSN\></span></span>|  
|<span data-ttu-id="b60fb-124">Fecha de nacimiento= “1/1/1995”</span><span class="sxs-lookup"><span data-stu-id="b60fb-124">Date of Birth = “1/1/1995”</span></span>|<span data-ttu-id="b60fb-125">\<FECHA DE NACIMIENTO\>"1/1/1995"\</DOB\></span><span class="sxs-lookup"><span data-stu-id="b60fb-125">\<DOB\>”1/1/1995”\</DOB\></span></span>|  
|<span data-ttu-id="b60fb-126">Sexo = Varón</span><span class="sxs-lookup"><span data-stu-id="b60fb-126">Gender = Male</span></span>|<span data-ttu-id="b60fb-127">\<Sexo\>M \< /género\></span><span class="sxs-lookup"><span data-stu-id="b60fb-127">\<Gender\>M\</Gender\></span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="b60fb-128">Cada conjunto de correlación admite un máximo de tres parámetros.</span><span class="sxs-lookup"><span data-stu-id="b60fb-128">Each correlation set supports a maximum of three parameters.</span></span>  
  
## <a name="initializing-correlation-sets"></a><span data-ttu-id="b60fb-129">Conjuntos de correlaciones de inicialización</span><span class="sxs-lookup"><span data-stu-id="b60fb-129">Initializing Correlation Sets</span></span>  
  
-   <span data-ttu-id="b60fb-130">**Conjuntos de correlaciones inicializados en una acción de recepción**</span><span class="sxs-lookup"><span data-stu-id="b60fb-130">**Correlation Sets initialized on a Receive action**</span></span>  
  
     <span data-ttu-id="b60fb-131">Los conjuntos de correlaciones inicializados en una acción de recepción definen el conjunto exacto de propiedades que debe contener un mensaje publicado para que lo procesen las acciones de recepción correspondientes en una orquestación.</span><span class="sxs-lookup"><span data-stu-id="b60fb-131">Correlation sets initialized on a Receive action define the exact set of properties that must exist in a published message in order for it to be processed by the corresponding receive action(s) in an orchestration.</span></span> <span data-ttu-id="b60fb-132">Un conjunto de correlaciones de inicialización creará un conjunto a partir de un tipo de correlación basado en los valores correspondientes de un documento.</span><span class="sxs-lookup"><span data-stu-id="b60fb-132">An initializing correlation set will create a correlation set from a correlation type based on the corresponding values in a document.</span></span>  
  
-   <span data-ttu-id="b60fb-133">**Conjuntos de correlaciones inicializados en una acción de envío**</span><span class="sxs-lookup"><span data-stu-id="b60fb-133">**Correlation Sets initialized on a Send action**</span></span>  
  
     <span data-ttu-id="b60fb-134">Los conjuntos de correlaciones inicializados en una acción de envío se crean a partir de un tipo de correlación basado en los valores correspondientes de un documento y promocionan las propiedades de correlación en el documento saliente.</span><span class="sxs-lookup"><span data-stu-id="b60fb-134">Correlation sets initialized on a Send action are created from a correlation type based upon the corresponding values in a document and promote the correlation properties in the outbound document.</span></span>  
  
## <a name="following-correlation-sets"></a><span data-ttu-id="b60fb-135">Siguientes conjuntos de correlaciones</span><span class="sxs-lookup"><span data-stu-id="b60fb-135">Following Correlation Sets</span></span>  
 <span data-ttu-id="b60fb-136">Los conjuntos de correlaciones siguientes solo pueden enlazarse a una acción de recepción de no activación o a una acción de envío.</span><span class="sxs-lookup"><span data-stu-id="b60fb-136">Following correlation sets can only be bound to a non-activating receive action or to a send action.</span></span> <span data-ttu-id="b60fb-137">Estos conjuntos de correlaciones se especifican conjuntamente con los conjuntos de correlación inicializados anteriormente.</span><span class="sxs-lookup"><span data-stu-id="b60fb-137">Following correlation sets are specified in tandem with previously initialized correlation sets.</span></span>  
  
-   <span data-ttu-id="b60fb-138">**Siguientes conjuntos de correlaciones enlazados a una acción de recepción**</span><span class="sxs-lookup"><span data-stu-id="b60fb-138">**Following Correlation Sets bound to a Receive action**</span></span>  
  
     <span data-ttu-id="b60fb-139">Los conjuntos de correlaciones siguientes enlazados a una acción de recepción definen las propiedades y los valores que el documento debe contener para su recepción.</span><span class="sxs-lookup"><span data-stu-id="b60fb-139">Following correlation sets bound to a receive action define the set of properties and values that the document must contain to be received.</span></span>  <span data-ttu-id="b60fb-140">Las acciones de recepción con conjuntos de correlaciones siguientes aceptan documentos que contienen propiedades de un conjunto de correlación inicializado anterior.</span><span class="sxs-lookup"><span data-stu-id="b60fb-140">Receive actions with following correlation sets accept documents that contain properties from a previously initialized correlation set.</span></span>  
  
-   <span data-ttu-id="b60fb-141">**Siguientes conjuntos de correlaciones enlazados a una acción de envío**</span><span class="sxs-lookup"><span data-stu-id="b60fb-141">**Following Correlation Sets bound to a Send action**</span></span>  
  
     <span data-ttu-id="b60fb-142">Los conjuntos de correlaciones siguientes enlazados a una acción de envío indican que el conjunto de propiedades del conjunto se promociona en el documento saliente.</span><span class="sxs-lookup"><span data-stu-id="b60fb-142">Following correlation sets bound to a send action dictate that the set of properties in the correlation set are promoted in the outbound document.</span></span>  
  
## <a name="inspecting-correlation-sets"></a><span data-ttu-id="b60fb-143">Inspeccionar conjuntos de correlaciones</span><span class="sxs-lookup"><span data-stu-id="b60fb-143">Inspecting Correlation Sets</span></span>  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="b60fb-144">proporciona la capacidad de inspeccionar conjuntos de correlaciones.</span><span class="sxs-lookup"><span data-stu-id="b60fb-144"> provides the ability to inspect correlation sets.</span></span> <span data-ttu-id="b60fb-145">Puede inspeccionar un conjunto de correlaciones en una forma Expresión mediante código parecido al siguiente:</span><span class="sxs-lookup"><span data-stu-id="b60fb-145">You can inspect a correlation set in an Expression Shape using code similar to the following:</span></span>  
  
```  
MsgLen = Correlation_1(BTS.MessageLength);  
```  
  
 <span data-ttu-id="b60fb-146">El ejemplo anterior se supone que ha creado una variable denominada **MsgLen** de tipo **System.Int16** y que la orquestación contiene una correlación de conjunto con nombre **Correlation_1**.</span><span class="sxs-lookup"><span data-stu-id="b60fb-146">The example above assumes that you have created a variable named **MsgLen** of type **System.Int16** and that your orchestration contains a correlation set named **Correlation_1**.</span></span> <span data-ttu-id="b60fb-147">La capacidad de inspeccionar conjuntos de correlaciones puede resultar útil si necesita inspeccionar el valor de una correlación que una orquestación ha pasado a otra.</span><span class="sxs-lookup"><span data-stu-id="b60fb-147">The ability to inspect correlation sets may be useful if you need to inspect the value of a correlation that was passed to an orchestration by another orchestration.</span></span>  
  
## <a name="passing-correlation-sets-as-parameters-to-orchestrations"></a><span data-ttu-id="b60fb-148">Pasar conjuntos de correlaciones a orquestaciones como parámetros</span><span class="sxs-lookup"><span data-stu-id="b60fb-148">Passing Correlation Sets as Parameters to Orchestrations</span></span>  
 <span data-ttu-id="b60fb-149">Puede pasar correlaciones como *en* parámetros a otras orquestaciones.</span><span class="sxs-lookup"><span data-stu-id="b60fb-149">You can pass correlations as *in* parameters to other orchestrations.</span></span>