---
title: "Recepción desde PeopleSoft | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9acc71ec-05b8-4490-b3ba-0ce7f27a5a6a
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 11c5add7e71e56f250b95736d97f0434adf72282
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="receiving-from-peoplesoft"></a><span data-ttu-id="8aa6a-102">Recepción desde PeopleSoft</span><span class="sxs-lookup"><span data-stu-id="8aa6a-102">Receiving from PeopleSoft</span></span>
<span data-ttu-id="8aa6a-103">Microsoft Adapter para PeopleSoft Enterprise es un adaptador de envío.</span><span class="sxs-lookup"><span data-stu-id="8aa6a-103">The Microsoft Adapter for PeopleSoft Enterprise is a send adapter.</span></span> <span data-ttu-id="8aa6a-104">El adaptador admite los envíos de solicitud-respuesta para que pueda enviar una consulta y obtener una respuesta.</span><span class="sxs-lookup"><span data-stu-id="8aa6a-104">The adapter supports solicit-response, so that you can send a query and get back a response.</span></span> <span data-ttu-id="8aa6a-105">No obstante, si únicamente desea recibir datos de PeopleSoft, deberá realizar otros dos pasos:</span><span class="sxs-lookup"><span data-stu-id="8aa6a-105">However, if you want only to receive data from PeopleSoft, you must take two additional steps:</span></span>  
  
1.  <span data-ttu-id="8aa6a-106">Crear una canalización de recepción personalizada con el componente de canalización de establecer espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="8aa6a-106">Create a custom receive pipeline using the Set Namespace pipeline component.</span></span>  
  
2.  <span data-ttu-id="8aa6a-107">Crear un puerto de recepción accesible desde PeopleSoft, como un puerto que use el adaptador HTTP.</span><span class="sxs-lookup"><span data-stu-id="8aa6a-107">Create a receive port accessible from PeopleSoft such as a port using the HTTP Adapter.</span></span> <span data-ttu-id="8aa6a-108">Use la canalización de recepción personalizada con el puerto de recepción.</span><span class="sxs-lookup"><span data-stu-id="8aa6a-108">Use the custom receive pipeline with the receive port.</span></span>  
  
## <a name="the-set-namespace-pipeline-component"></a><span data-ttu-id="8aa6a-109">Componente de canalización de establecer espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="8aa6a-109">The Set Namespace Pipeline Component</span></span>  
 <span data-ttu-id="8aa6a-110">Los mensajes recibidos de PeopleSoft no incluyen espacios de nombres.</span><span class="sxs-lookup"><span data-stu-id="8aa6a-110">Messages received from PeopleSoft do not include namespaces.</span></span> <span data-ttu-id="8aa6a-111">El componente de canalización de establecer espacio de nombres permite agregar un espacio de nombres al mensaje entrante.</span><span class="sxs-lookup"><span data-stu-id="8aa6a-111">The Set Namespace pipeline component enables you to add a namespace to the incoming message.</span></span>  
  
 <span data-ttu-id="8aa6a-112">La ubicación predeterminada para el componente de canalización de establecer espacio de nombres es C:\Archivos de programa\Microsoft BizTalk Adapters for Enterprise Applications\Pipeline Component.</span><span class="sxs-lookup"><span data-stu-id="8aa6a-112">The default location for the Set Namespace pipeline component is C:\Program Files\Microsoft BizTalk Adapters for Enterprise Applications\Pipeline Component.</span></span> <span data-ttu-id="8aa6a-113">Debe copiar el componente Microsoft.BizTalk.Adapters.Pipeline.SetNSForMsg.dll en el directorio Pipeline Component usado por BizTalk.</span><span class="sxs-lookup"><span data-stu-id="8aa6a-113">You need to copy the component, Microsoft.BizTalk.Adapters.Pipeline.SetNSForMsg.dll, to the Pipeline Component directory used by BizTalk.</span></span> <span data-ttu-id="8aa6a-114">También debe agregar el componente al cuadro de herramientas de Visual Studio para usarlo en el Diseñador de canalizaciones.</span><span class="sxs-lookup"><span data-stu-id="8aa6a-114">You also need to add the component to the Visual Studio Toolbox in order to use it in the Pipeline Designer.</span></span>  
  
 <span data-ttu-id="8aa6a-115">Para obtener información sobre dónde instalar el componente, vea [implementar componentes de canalización](../core/deploying-pipeline-components.md).</span><span class="sxs-lookup"><span data-stu-id="8aa6a-115">For information about where to install the component, see [Deploying Pipeline Components](../core/deploying-pipeline-components.md).</span></span>  
  
 <span data-ttu-id="8aa6a-116">Para obtener información acerca de cómo agregar el componente en el cuadro de herramientas de Visual Studio, vea [cómo utilizar el cuadro de herramientas](../core/how-to-use-the-toolbox.md).</span><span class="sxs-lookup"><span data-stu-id="8aa6a-116">For information about adding the component to the Visual Studio Toolbox, see [How to Use the Toolbox](../core/how-to-use-the-toolbox.md).</span></span>  
  
## <a name="configuring-the-set-namespace-pipeline-component"></a><span data-ttu-id="8aa6a-117">Configuración del componente de canalización de establecer espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="8aa6a-117">Configuring the Set Namespace Pipeline Component</span></span>  
 <span data-ttu-id="8aa6a-118">El componente de canalización de establecer espacio de nombres tiene dos propiedades que se pueden establecer:</span><span class="sxs-lookup"><span data-stu-id="8aa6a-118">The Set Namespace pipeline component has two properties you can set:</span></span>  
  
|<span data-ttu-id="8aa6a-119">Use</span><span class="sxs-lookup"><span data-stu-id="8aa6a-119">Use this</span></span>|<span data-ttu-id="8aa6a-120">Para</span><span class="sxs-lookup"><span data-stu-id="8aa6a-120">To do this</span></span>|  
|--------------|----------------|  
|<span data-ttu-id="8aa6a-121">**Namespace de destino predeterminado**</span><span class="sxs-lookup"><span data-stu-id="8aa6a-121">**Default Target Namespace**</span></span>|<span data-ttu-id="8aa6a-122">Coloque un espacio de nombres fijo en el mensaje entrante.</span><span class="sxs-lookup"><span data-stu-id="8aa6a-122">Put a fixed namespace in the incoming message.</span></span>|  
|<span data-ttu-id="8aa6a-123">**Target Namespace XPath**</span><span class="sxs-lookup"><span data-stu-id="8aa6a-123">**Target Namespace XPath**</span></span>|<span data-ttu-id="8aa6a-124">Extraiga el espacio de nombres del mensaje entrante tomándolo de la ubicación especificada por XPath.</span><span class="sxs-lookup"><span data-stu-id="8aa6a-124">Extract the namespace from the incoming message taking it from the location specified by the XPath.</span></span> <span data-ttu-id="8aa6a-125">Si el componente no encuentra un espacio de nombres válido, registra una advertencia en el registro de eventos de la aplicación y, si está especificado, usa el espacio de nombres de destino predeterminado.</span><span class="sxs-lookup"><span data-stu-id="8aa6a-125">If the component does not find a valid namespace, it logs a warning in the Application Event Log and, if it is specified, uses the Default Target Namespace.</span></span>|  
  
 <span data-ttu-id="8aa6a-126">Si deja ambas propiedades en blanco, el componente no asigna espacios de nombres a los mensajes entrantes pero escribe advertencias en el registro de eventos de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="8aa6a-126">If you leave both properties blank, the component does not assign namespaces to incoming messages but does write warnings to the Application Event Log.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8aa6a-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="8aa6a-127">See Also</span></span>  
 [<span data-ttu-id="8aa6a-128">Desarrollo de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="8aa6a-128">Developing Applications</span></span>](../core/developing-applications4.md)