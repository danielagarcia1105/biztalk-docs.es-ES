---
title: "Informar de errores de componentes de canalización | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- IErrorInfo object
- pipeline components [custom], errors
- SetErrorInfo method
- Exception object
ms.assetid: ad7c519e-829a-4a92-a42f-3e367d5dbaa8
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9d181f557d64152ff79f70b09986c05727076121
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="reporting-errors-from-pipeline-components"></a><span data-ttu-id="1efda-102">Informar de errores de componentes de canalización</span><span class="sxs-lookup"><span data-stu-id="1efda-102">Reporting Errors from Pipeline Components</span></span>
<span data-ttu-id="1efda-103">Los componentes de canalización informan de errores de dos formas:</span><span class="sxs-lookup"><span data-stu-id="1efda-103">Pipeline components report errors in two ways:</span></span>  
  
-   <span data-ttu-id="1efda-104">En el caso de los componentes basados en .NET, mediante el inicio de una excepción.</span><span class="sxs-lookup"><span data-stu-id="1efda-104">For .NET-based components, by throwing an exception.</span></span>  
  
-   <span data-ttu-id="1efda-105">Componentes basados en COM, estableciendo el **ErrorInfo** objeto y devuelve un HRESULT de error.</span><span class="sxs-lookup"><span data-stu-id="1efda-105">For COM-based components, by setting the **ErrorInfo** object and returning a failure HRESULT.</span></span>  
  
## <a name="reporting-errors-from-net-pipeline-components"></a><span data-ttu-id="1efda-106">Notificar errores desde los componentes de canalización .NET</span><span class="sxs-lookup"><span data-stu-id="1efda-106">Reporting errors from .NET pipeline components</span></span>  
 <span data-ttu-id="1efda-107">Para notificar un error, el componente de canalización basado en .NET necesita iniciar una excepción en la ubicación en la que informa del error.</span><span class="sxs-lookup"><span data-stu-id="1efda-107">To report an error, a .NET-based pipeline component needs to throw an exception where it reports the error description.</span></span> <span data-ttu-id="1efda-108">Para notificar el nombre del componente que se produce un error, establezca el **origen** propiedad de la **excepción** objeto.</span><span class="sxs-lookup"><span data-stu-id="1efda-108">To report the name of the component that throws an error, set the **Source** property of the **Exception** object.</span></span>  
  
 <span data-ttu-id="1efda-109">El motor de mensajería utiliza el **mensaje** y **origen** propiedades de la **excepción** objeto que se va a notificar un error.</span><span class="sxs-lookup"><span data-stu-id="1efda-109">The Messaging Engine uses the **Message** and **Source** properties of the **Exception** object to report an error.</span></span> <span data-ttu-id="1efda-110">Se escribe el siguiente mensaje en el registro de eventos:</span><span class="sxs-lookup"><span data-stu-id="1efda-110">The following message is written to the event log:</span></span>  
  
 <span data-ttu-id="1efda-111">"Hubo un error al ejecutar el [recepción &#124; envío] canalización: \<nombre de la canalización > origen: \<origen > [ubicación de recepción &#124; Puerto de envío:] \<ubicación &#124; nombre de puerto > razón: \<mensaje >. "</span><span class="sxs-lookup"><span data-stu-id="1efda-111">"There was a failure executing the [receive&#124;send] pipeline: \<pipeline name> Source: \<Source> [Receive Location&#124;Send Port:] \<location&#124;port name> Reason: \<Message>."</span></span>  
  
## <a name="reporting-errors-from-com-pipeline-components"></a><span data-ttu-id="1efda-112">Notificar errores desde los componentes de canalización COM</span><span class="sxs-lookup"><span data-stu-id="1efda-112">Reporting errors from COM pipeline components</span></span>  
 <span data-ttu-id="1efda-113">Para notificar un error, los componentes de canalización basados en COM realizan las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="1efda-113">To report an error, COM-based pipeline components perform the following actions:</span></span>  
  
1.  <span data-ttu-id="1efda-114">Los grupos de componentes de canalización del **IErrorInfo** objeto mediante una llamada a la **SetErrorInfo** método.</span><span class="sxs-lookup"><span data-stu-id="1efda-114">The pipeline component sets the **IErrorInfo** object by calling the **SetErrorInfo** method.</span></span>  
  
2.  <span data-ttu-id="1efda-115">El componente de canalización devuelve un error de HRESULT al motor de mensajería.</span><span class="sxs-lookup"><span data-stu-id="1efda-115">The pipeline component returns a failed HRESULT to the Messaging Engine.</span></span>  
  
 <span data-ttu-id="1efda-116">El motor de mensajería utiliza el **GetSource** y **GetDescription** propiedades de la **IErrorInfo** objeto que se va a notificar un error.</span><span class="sxs-lookup"><span data-stu-id="1efda-116">The Messaging Engine uses the **GetSource** and **GetDescription** properties of the **IErrorInfo** object to report an error.</span></span> <span data-ttu-id="1efda-117">Si no se ha establecido el origen, se usa el nombre del componente.</span><span class="sxs-lookup"><span data-stu-id="1efda-117">If the source is not set, the name of the component is used.</span></span> <span data-ttu-id="1efda-118">Si la descripción no está establecido o todo el **ErrorInfo** objeto no está establecido, se notifica el HRESULT devuelto en lugar de la descripción.</span><span class="sxs-lookup"><span data-stu-id="1efda-118">If the description is not set or the whole **ErrorInfo** object is not set, the returned HRESULT is reported instead of the description.</span></span> <span data-ttu-id="1efda-119">Se escribe el siguiente mensaje en el registro de eventos:</span><span class="sxs-lookup"><span data-stu-id="1efda-119">The following message is written to the event log:</span></span>  
  
 <span data-ttu-id="1efda-120">"Hubo un error al ejecutar el [recepción &#124; envío] canalización: \<nombre de la canalización > origen: \<GetSource > [ubicación de recepción &#124; Puerto de envío:] \<ubicación &#124; nombre de puerto > razón: \<GetDescription o HRESULT >. "</span><span class="sxs-lookup"><span data-stu-id="1efda-120">"There was a failure executing the [receive&#124;send] pipeline: \<pipeline name> Source: \<GetSource> [Receive Location&#124;Send Port:] \<location&#124;port name> Reason: \<GetDescription or HRESULT>."</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1efda-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="1efda-121">See Also</span></span>  
 [<span data-ttu-id="1efda-122">Desarrollar componentes de canalización personalizado</span><span class="sxs-lookup"><span data-stu-id="1efda-122">Developing Custom Pipeline Components</span></span>](../core/developing-custom-pipeline-components.md)