---
title: Componente de canalización de desarrollo de un sondeo | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- pipeline components [custom], probing
- IProbeMessage interface
- pipeline interfaces, IProbeMessage
ms.assetid: c3da467d-5270-4c7f-9c38-ce9989bf1b63
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0be44929609eaba5ec30a6e40c1bdda14192e351
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36987365"
---
# <a name="developing-a-probing-pipeline-component"></a><span data-ttu-id="f3dc4-102">Desarrollar un componente de canalización de búsqueda</span><span class="sxs-lookup"><span data-stu-id="f3dc4-102">Developing a Probing Pipeline Component</span></span>
<span data-ttu-id="f3dc4-103">Un componente de canalización (general, ensamblado o desensamblado) puede implementar la `IProbeMessage` si debe admitir la funcionalidad de búsqueda de mensajes de la interfaz.</span><span class="sxs-lookup"><span data-stu-id="f3dc4-103">Any pipeline component (general, assembling, or disassembling) can implement the `IProbeMessage` interface if it must support message probing functionality.</span></span> <span data-ttu-id="f3dc4-104">Un componente de búsqueda se usa en las etapas de canalización que tienen **FirstMatch** modo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="f3dc4-104">A probing component is used in the pipeline stages that have **FirstMatch** execution mode.</span></span> <span data-ttu-id="f3dc4-105">En tales fases, el motor de mensajería de BizTalk entrega la parte inicial del mensaje al componente para determinar si el componente identifica el formato del mensaje.</span><span class="sxs-lookup"><span data-stu-id="f3dc4-105">In such stages, the BizTalk Messaging Engine gives the beginning part of the message to the component to determine if the component recognizes the format of the message.</span></span> <span data-ttu-id="f3dc4-106">Si el componente reconoce el formato, se entrega el mensaje completo al componente para que lo procese.</span><span class="sxs-lookup"><span data-stu-id="f3dc4-106">If the component recognizes the format, the entire message is given to the component for processing.</span></span>  
  
 <span data-ttu-id="f3dc4-107">El **IProbeMessage** interfaz expone un método único, **sondeo**, lo que permite al componente comprobar la parte inicial del mensaje.</span><span class="sxs-lookup"><span data-stu-id="f3dc4-107">The **IProbeMessage** interface exposes a single method, **Probe**, which enables the component to check the beginning part of the message.</span></span> <span data-ttu-id="f3dc4-108">El valor devuelto determina si se ejecuta el componente.</span><span class="sxs-lookup"><span data-stu-id="f3dc4-108">The return value determines whether this component is run.</span></span> <span data-ttu-id="f3dc4-109">Los siguientes pasos explican cómo el motor de mensajería de BizTalk ejecuta una fase que requiere reconocimiento:</span><span class="sxs-lookup"><span data-stu-id="f3dc4-109">The following steps outline how the BizTalk Messaging Engine runs a stage that requires recognition:</span></span>  
  
1. <span data-ttu-id="f3dc4-110">Si la fase no contiene ningún componente, la fase no se ejecuta y el mensaje se entrega a las fases posteriores para su procesamiento.</span><span class="sxs-lookup"><span data-stu-id="f3dc4-110">If the stage does not contain any components, the stage is not run and the message is given to the subsequent stages for processing.</span></span>  
  
2. <span data-ttu-id="f3dc4-111">Compruebe si el componente implementa la **IProbeMessage** interfaz.</span><span class="sxs-lookup"><span data-stu-id="f3dc4-111">Check if the component implements the **IProbeMessage** interface.</span></span> <span data-ttu-id="f3dc4-112">En caso contrario, el motor de mensajería invoca el componente.</span><span class="sxs-lookup"><span data-stu-id="f3dc4-112">If not, the Messaging Engine invokes the component.</span></span> <span data-ttu-id="f3dc4-113">Se realiza el procesamiento de la fase y el mensaje se entrega a la siguiente fase.</span><span class="sxs-lookup"><span data-stu-id="f3dc4-113">The stage processing is done and the message is given to the next stage.</span></span>  
  
3. <span data-ttu-id="f3dc4-114">El **sondeo** se invoca el método.</span><span class="sxs-lookup"><span data-stu-id="f3dc4-114">The **Probe** method is invoked.</span></span> <span data-ttu-id="f3dc4-115">Si el valor devuelto es **True**, se ejecuta el componente.</span><span class="sxs-lookup"><span data-stu-id="f3dc4-115">If the return value is **True**, the component is run.</span></span> <span data-ttu-id="f3dc4-116">A continuación, se realiza el procesamiento de la fase y el mensaje se entrega a una fase siguiente.</span><span class="sxs-lookup"><span data-stu-id="f3dc4-116">Then the stage processing is done and the message is given to a next stage.</span></span>  
  
4. <span data-ttu-id="f3dc4-117">El motor de mensajería obtiene el siguiente componente de la fase.</span><span class="sxs-lookup"><span data-stu-id="f3dc4-117">The Messaging Engine gets the next component in the stage.</span></span> <span data-ttu-id="f3dc4-118">Si no hay más componentes y ninguno de ellos se ha ejecutado, genera un error que indica que se ha producido un error en el procesamiento de canalización.</span><span class="sxs-lookup"><span data-stu-id="f3dc4-118">If there are no more components and none of the components have been run, it generates an error that pipeline processing has failed.</span></span> <span data-ttu-id="f3dc4-119">Si no hay más componentes y se ha ejecutado como mínimo un componente, se lleva a cabo el procesamiento.</span><span class="sxs-lookup"><span data-stu-id="f3dc4-119">If there are no more components and at least one component has been run, the processing is done.</span></span>  
  
   <span data-ttu-id="f3dc4-120">Si una fase no necesita reconocimiento (por ejemplo, el modo de ejecución es **todas**), el motor de mensajería invoca el componente sin consultar primero para la **IProbeMessage** interfaz y una llamada a la **Sondeo** método.</span><span class="sxs-lookup"><span data-stu-id="f3dc4-120">If a stage does not require recognition (for example, the execution mode is **All**), the Messaging Engine invokes the component without first querying for the **IProbeMessage** interface and calling the **Probe** method.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f3dc4-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="f3dc4-121">See Also</span></span>  
 <span data-ttu-id="f3dc4-122">[Desarrollar un componente de canalización generales](../core/developing-a-general-pipeline-component.md) </span><span class="sxs-lookup"><span data-stu-id="f3dc4-122">[Developing a General Pipeline Component](../core/developing-a-general-pipeline-component.md) </span></span>  
 <span data-ttu-id="f3dc4-123">[Desarrollar un componente de canalización de ensamblado](../core/developing-an-assembling-pipeline-component.md) </span><span class="sxs-lookup"><span data-stu-id="f3dc4-123">[Developing an Assembling Pipeline Component](../core/developing-an-assembling-pipeline-component.md) </span></span>  
 <span data-ttu-id="f3dc4-124">[Desarrollar un componente de canalización de desensamblado](../core/developing-a-disassembling-pipeline-component.md) </span><span class="sxs-lookup"><span data-stu-id="f3dc4-124">[Developing a Disassembling Pipeline Component](../core/developing-a-disassembling-pipeline-component.md) </span></span>  
 <span data-ttu-id="f3dc4-125">[Informes de errores de componentes de canalización](../core/reporting-errors-from-pipeline-components.md) </span><span class="sxs-lookup"><span data-stu-id="f3dc4-125">[Reporting Errors from Pipeline Components](../core/reporting-errors-from-pipeline-components.md) </span></span>  
 <span data-ttu-id="f3dc4-126">[Configurar componentes de canalización nativos](../core/configuring-native-pipeline-components.md) </span><span class="sxs-lookup"><span data-stu-id="f3dc4-126">[Configuring Native Pipeline Components](../core/configuring-native-pipeline-components.md) </span></span>  
 [<span data-ttu-id="f3dc4-127">Implementación de componentes de canalización</span><span class="sxs-lookup"><span data-stu-id="f3dc4-127">Deploying Pipeline Components</span></span>](../core/deploying-pipeline-components.md)