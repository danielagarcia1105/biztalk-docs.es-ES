---
title: Elemento EventSource del interceptor | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d78846c1-3984-43af-a13f-9d5c0a66d3b5
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 35b5cd6b2e872f689988f3d10d18df002f66d6a0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22257476"
---
# <a name="interceptor-eventsource-element"></a><span data-ttu-id="d3c87-102">Elemento EventSource del interceptor</span><span class="sxs-lookup"><span data-stu-id="d3c87-102">Interceptor EventSource Element</span></span>
<span data-ttu-id="d3c87-103">El **EventSource** elemento proporciona información sobre el origen de uno o varios de los eventos que aparecen en el archivo de configuración de interceptor.</span><span class="sxs-lookup"><span data-stu-id="d3c87-103">The **EventSource** element provides information about the source of one or more of the events appearing in the interceptor configuration file.</span></span> <span data-ttu-id="d3c87-104">Además del nombre de origen de eventos, debe indicar la tecnología y el manifiesto del origen.</span><span class="sxs-lookup"><span data-stu-id="d3c87-104">In addition to an event source name, you need to indicate the technology and a manifest for the source.</span></span>  
  
## <a name="format"></a><span data-ttu-id="d3c87-105">Formato</span><span class="sxs-lookup"><span data-stu-id="d3c87-105">Format</span></span>  
 <span data-ttu-id="d3c87-106">El elemento `EventSource` cuenta con tres atributos y puede disponer de elementos secundarios, en función de los esquemas que se incluyan.</span><span class="sxs-lookup"><span data-stu-id="d3c87-106">The `EventSource` element has three attributes and may or may not have child elements depending upon which schemas are included.</span></span> <span data-ttu-id="d3c87-107">Por ejemplo, el esquema WCF WcfInterceptorConfiguration.xsd proporciona el elemento `NamespaceMapping`.</span><span class="sxs-lookup"><span data-stu-id="d3c87-107">For example, the WCF schema WcfInterceptorConfiguration.xsd provides for the `NamespaceMapping` element.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d3c87-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="d3c87-108">Attributes</span></span>  
  
|<span data-ttu-id="d3c87-109">Nombre del atributo</span><span class="sxs-lookup"><span data-stu-id="d3c87-109">Attribute name</span></span>|<span data-ttu-id="d3c87-110">Description</span><span class="sxs-lookup"><span data-stu-id="d3c87-110">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="d3c87-111">Nombre</span><span class="sxs-lookup"><span data-stu-id="d3c87-111">Name</span></span>|<span data-ttu-id="d3c87-112">Nombre del origen de eventos.</span><span class="sxs-lookup"><span data-stu-id="d3c87-112">Name for this event source.</span></span> <span data-ttu-id="d3c87-113">Este nombre se usa por **OnEvent** entradas para hacer referencia al origen.</span><span class="sxs-lookup"><span data-stu-id="d3c87-113">This name is used by **OnEvent** entries to refer to the source.</span></span>|  
|<span data-ttu-id="d3c87-114">Tecnología</span><span class="sxs-lookup"><span data-stu-id="d3c87-114">Technology</span></span>|<span data-ttu-id="d3c87-115">El tipo de tecnología que aloja el origen de eventos indicado en el manifiesto.</span><span class="sxs-lookup"><span data-stu-id="d3c87-115">Technology type hosting the event source indicated in the manifest.</span></span> <span data-ttu-id="d3c87-116">Utilice "WF" para Windows Workflow Foundation y "WCF" para Windows Communication Framework.</span><span class="sxs-lookup"><span data-stu-id="d3c87-116">Use "WF" for Windows Workflow Foundation and "WCF" for Windows Communication Framework.</span></span>|  
|<span data-ttu-id="d3c87-117">Manifiesto</span><span class="sxs-lookup"><span data-stu-id="d3c87-117">Manifest</span></span>|<span data-ttu-id="d3c87-118">Nombre de clase cualificado por el ensamblado del tipo que se va a usar como origen de eventos.</span><span class="sxs-lookup"><span data-stu-id="d3c87-118">Assembly-qualified class name of the type to use as an event source.</span></span> <span data-ttu-id="d3c87-119">Por ejemplo, `TopNamespace.SubNameSpace.ContainingClass+NestedClass, MyAssembly, Version=1.3.0.0, Culture=neutral, PublicKeyToken=b17a5c561934e08`</span><span class="sxs-lookup"><span data-stu-id="d3c87-119">For example, `TopNamespace.SubNameSpace.ContainingClass+NestedClass, MyAssembly, Version=1.3.0.0, Culture=neutral, PublicKeyToken=b17a5c561934e08`</span></span><br /><br /> <span data-ttu-id="d3c87-120">Si no cuenta con un token de clave pública, utilice `PublicKeyToken=null`.</span><span class="sxs-lookup"><span data-stu-id="d3c87-120">If you do not have a public key token, use `PublicKeyToken=null`.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="d3c87-121">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="d3c87-121">Example</span></span>  
 <span data-ttu-id="d3c87-122">En el siguiente ejemplo contiene dos **EventSource** elementos, un WF de destino y un WCF de destino.</span><span class="sxs-lookup"><span data-stu-id="d3c87-122">The following example contains two **EventSource** elements, one targeting WF and one targeting WCF.</span></span>  
  
```  
<!-- WF -->  
<ic:EventSource Name="OrderWorkflow" Technology="WF" Manifest="SimpleWorkflow.OrderWorkflow, SimpleWorkflow, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null"/>  
<!-- WCF -->  
<ic:EventSource Name="PurchaseService" Technology="WCF" Manifest="Service.IProcessPOContract, DuplexService, Version=1.0.0.0, Culture=neutral, PublicKeyToken=null"/>  
```