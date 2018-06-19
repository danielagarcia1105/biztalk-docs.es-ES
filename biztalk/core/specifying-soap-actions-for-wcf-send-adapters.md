---
title: Especificar acciones SOAP para WCF adaptadores de envío | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- send adapters, mapping
- send adapters, WCF services
- mapping, send adapters
- mapping, WCF send adapters
ms.assetid: fa9878eb-65b5-4ccc-b727-ff7e09ba6302
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 385e92f7801dc2512fbd038bd0b005d95c503e57
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22276644"
---
# <a name="specifying-soap-actions-for-wcf-send-adapters"></a><span data-ttu-id="5bd52-102">Especificar acciones SOAP para adaptadores de envío WCF</span><span class="sxs-lookup"><span data-stu-id="5bd52-102">Specifying SOAP Actions for WCF Send Adapters</span></span>
<span data-ttu-id="5bd52-103">Puede establecer el **WCF. Acción** propiedad de contexto en el cuadro de diálogo de propiedades de transporte WCF envío adaptador o en la orquestación **expresión** formas.</span><span class="sxs-lookup"><span data-stu-id="5bd52-103">You can set the **WCF.Action** context property in the WCF send adapter transport properties dialog box or in the orchestration **Expression** shapes.</span></span> <span data-ttu-id="5bd52-104">Si establece la **WCF. Acción** propiedad de contexto en la orquestación, debe dejar el **acción** campo en blanco en el cuadro de diálogo de propiedades WCF adaptador transporte para los puertos de envío estático.</span><span class="sxs-lookup"><span data-stu-id="5bd52-104">If you set the **WCF.Action** context property in the orchestration, you need to leave the **Action** field blank in the WCF adapter transport properties dialog box for the static send ports.</span></span> <span data-ttu-id="5bd52-105">Si también especifica una acción en los puertos de envío estáticos, el **WCF. Acción** se invalidará la propiedad de contexto se establece en la orquestación.</span><span class="sxs-lookup"><span data-stu-id="5bd52-105">If you also specify an action in the static send ports, the **WCF.Action** context property you set in the orchestration will be overridden.</span></span>  
  
 <span data-ttu-id="5bd52-106">Además, hay dos maneras de especificar esta propiedad: el formato de acción única y el formato de asignación de acciones.</span><span class="sxs-lookup"><span data-stu-id="5bd52-106">Moreover, there are two ways to specify this property: the single action format and the action mapping format.</span></span> <span data-ttu-id="5bd52-107">Si establece esta propiedad en el formato de acción única: por ejemplo, http://MyService/IMyContract/MyAction1: cuadro de diálogo de propiedades de transporte de adaptador de envío de la acción de SOAP de WCF para los mensajes salientes siempre se establece en el valor especificado en esta propiedad.</span><span class="sxs-lookup"><span data-stu-id="5bd52-107">If you set this property in the single action format—for example, http://MyService/IMyContract/MyAction1—the SOAP action in the WCF send adapter transport properties dialog box for outgoing messages is always set to the value specified in this property.</span></span> <span data-ttu-id="5bd52-108">Como alternativa, puede establecer el formato de acción única en la orquestación **expresión** forma.</span><span class="sxs-lookup"><span data-stu-id="5bd52-108">Alternatively, you can set the single action format in the orchestration **Expression** shape.</span></span> <span data-ttu-id="5bd52-109">Por ejemplo,</span><span class="sxs-lookup"><span data-stu-id="5bd52-109">For example,</span></span>  
  
```  
OutboundMessage(WCF.Action)="http://MyService/IMyContract/MyAction1";  
```  
  
 <span data-ttu-id="5bd52-110">Si establece esta propiedad en el formato de asignación de acciones, la acción de SOAP saliente viene determinada por la **BTS. Operación** propiedad de contexto.</span><span class="sxs-lookup"><span data-stu-id="5bd52-110">If you set this property in the action mapping format, the outgoing SOAP action is determined by the **BTS.Operation** context property.</span></span> <span data-ttu-id="5bd52-111">Por ejemplo, si esta propiedad se establece en el siguiente formato XML en WCF cuadro de diálogo de propiedades de transporte de adaptador de envío y la **BTS. Operación** propiedad está establecida en **Operation_1** en el puerto de envío en la orquestación, el adaptador de envío WCF usa http://MyService/IMyContract/MyAction1 para la acción SOAP saliente.</span><span class="sxs-lookup"><span data-stu-id="5bd52-111">For example, if this property is set to the following XML format in the WCF send adapter transport properties dialog box and the **BTS.Operation** property is set to **Operation_1** in the send port in the orchestration, the WCF send adapter uses http://MyService/IMyContract/MyAction1 for the outgoing SOAP action.</span></span>  
  
```  
BtsActionMapping xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">  
<Operation Name="Operation_1" Action="http://MyService/IMyContract/MyAction1" />  
<Operation Name="Operation_2" Action="http://MyService/IMyContract/MyAction2" />  
<Operation Name="Operation_3" Action="http://MyService/IMyContract/MyAction3" />  
</BtsActionMapping>  
```  
  
 <span data-ttu-id="5bd52-112">Especificar asignación de acción de **WCF. Acción** en un **expresión** no se admite la forma.</span><span class="sxs-lookup"><span data-stu-id="5bd52-112">Specifying action mapping for **WCF.Action** in an **Expression** shape is not supported.</span></span> <span data-ttu-id="5bd52-113">Es necesario especificar la asignación de acciones en el cuadro de diálogo de propiedades de transporte WCF.</span><span class="sxs-lookup"><span data-stu-id="5bd52-113">You need to specify the action mapping in the WCF transport properties dialog box.</span></span> <span data-ttu-id="5bd52-114">A continuación, el adaptador de WCF buscará la acción SOAP mediante el uso de la **BTS. Operación** propiedad de contexto, que la orquestación establece el nombre de la operación en el puerto que se envía el mensaje.</span><span class="sxs-lookup"><span data-stu-id="5bd52-114">Then the WCF adapter will look up the SOAP action by using the **BTS.Operation** context property, which the orchestration sets to the name of the operation on the port where the message is sent.</span></span>  
  
 <span data-ttu-id="5bd52-115">Si los mensajes salientes se enrutan con enrutamiento por contenidos (CBR) donde el **http://schemas.microsoft.com/BizTalk/2003/system-properties#Operation** propiedad no está establecida, adaptadores de envío WCF establecerá la asignación de acción completa cadena a la acción de los mensajes salientes de WCF.</span><span class="sxs-lookup"><span data-stu-id="5bd52-115">If outgoing messages are routed with content-based routing (CBR) where the **http://schemas.microsoft.com/BizTalk/2003/system-properties#Operation** property is not set, WCF send adapters will set the whole action mapping string to the action of the outgoing WCF messages.</span></span> <span data-ttu-id="5bd52-116">Para resolver este problema, siga uno de los siguientes:</span><span class="sxs-lookup"><span data-stu-id="5bd52-116">To work around this, you can do one of the following:</span></span>  
  
-   <span data-ttu-id="5bd52-117">Establecer el campo de acción en el puerto de envío como http://MyService/IMyContract/MyAction1.</span><span class="sxs-lookup"><span data-stu-id="5bd52-117">Set the action field on the send port to http://MyService/IMyContract/MyAction1.</span></span>  
  
-   <span data-ttu-id="5bd52-118">Establecer el **BTS. Operación** propiedad de contexto en una canalización.</span><span class="sxs-lookup"><span data-stu-id="5bd52-118">Set the **BTS.Operation** context property in a pipeline.</span></span> <span data-ttu-id="5bd52-119">Por ejemplo, establezca el valor de **http://schemas.microsoft.com/BizTalk/2003/system-properties#Operation** como Operation1.</span><span class="sxs-lookup"><span data-stu-id="5bd52-119">For example, set the value of **http://schemas.microsoft.com/BizTalk/2003/system-properties#Operation** to Operation1.</span></span>  
  
-   <span data-ttu-id="5bd52-120">Dejar en blanco el campo de acción y, en su lugar, usar la acción del mensaje entrante.</span><span class="sxs-lookup"><span data-stu-id="5bd52-120">Leave the action field blank and use the action from the incoming message instead.</span></span>  
  
 <span data-ttu-id="5bd52-121">También puede usar el Asistente para consumición del Servicio WCF de BizTalk para consumir los servicios WCF con una única acción o con asignación de acciones.</span><span class="sxs-lookup"><span data-stu-id="5bd52-121">You can also use the BizTalk WCF Service Consuming Wizard to consume the WCF services with single action or action mapping.</span></span> <span data-ttu-id="5bd52-122">Para obtener más información, consulte [cómo utilizar el Asistente de consumición de servicio WCF de BizTalk para consumir un servicio WCF](../core/how-to-use-the-biztalk-wcf-service-consuming-wizard-to-consume-a-wcf-service.md).</span><span class="sxs-lookup"><span data-stu-id="5bd52-122">For more details, see [How to Use the BizTalk WCF Service Consuming Wizard to Consume a WCF Service](../core/how-to-use-the-biztalk-wcf-service-consuming-wizard-to-consume-a-wcf-service.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5bd52-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="5bd52-123">See Also</span></span>  
 [<span data-ttu-id="5bd52-124">Configuración de puertos de envío dinámicos mediante propiedades de contexto de adaptadores de WCF</span><span class="sxs-lookup"><span data-stu-id="5bd52-124">Configuring Dynamic Send Ports Using WCF Adapters Context Properties</span></span>](../core/configuring-dynamic-send-ports-using-wcf-adapters-context-properties.md)