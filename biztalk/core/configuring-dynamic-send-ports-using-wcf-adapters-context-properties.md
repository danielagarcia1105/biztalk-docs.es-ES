---
title: "Configuración de puertos de envío dinámicos mediante propiedades de contexto de adaptadores de WCF | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- WCF services, send ports
- send ports, WCF services
- dynamic send ports, WCF services
- send ports, dynamic
ms.assetid: 2a7e2cd2-fa2d-45da-bb8e-eb8bab21bfa3
caps.latest.revision: "19"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2bca34afa85c8764215f47d1272c115354889fa5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="configuring-dynamic-send-ports-using-wcf-adapters-context-properties"></a><span data-ttu-id="e544d-102">Configurar puertos de envío dinámico mediante el uso de propiedades de contexto de adaptadores de WCF</span><span class="sxs-lookup"><span data-stu-id="e544d-102">Configuring Dynamic Send Ports Using WCF Adapters Context Properties</span></span>
<span data-ttu-id="e544d-103">Puede configurar puertos de envío dinámico para adaptadores de WCF.</span><span class="sxs-lookup"><span data-stu-id="e544d-103">You can configure dynamic send ports for WCF adapters.</span></span> <span data-ttu-id="e544d-104">La URI, la acción y el enlace pueden se determina a partir de una propiedad en un mensaje entrante y, a continuación, se especifica en el **expresión** forma, tal y como se muestra en el siguiente adaptador de WCF-NetTcp:</span><span class="sxs-lookup"><span data-stu-id="e544d-104">The URI, action, and binding might be determined from a property on an incoming message, and then specified in the **Expression** shape, as shown in the following WCF-NetTcp adapter:</span></span>  
  
```  
MessageOut=MessageIn;  
MessageOut(WCF.Action)="http://tempuri.org/IReceiveMessage/ReceiveMessage";  
MessageOut(WCF.SecurityMode)="Transport";  
MessageOut(WCF.TransportClientCredentialType)="Windows";  
DynamicSendPort(Microsoft.XLANGs.BaseTypes.Address)="net.tcp://localhost:8001/netTcp";  
DynamicSendPort(Microsoft.XLANGs.BaseTypes.TransportType)="WCF-NetTcp";  
```  
  
 <span data-ttu-id="e544d-105">El código siguiente muestra un ejemplo de cómo especificar las propiedades de contexto WCF en el **expresión** forma para un adaptador de WCF-Custom:</span><span class="sxs-lookup"><span data-stu-id="e544d-105">The following code shows an example of how to specify the WCF context properties in the **Expression** shape for a WCF-Custom adapter:</span></span>  
  
```  
MessageOut=MessageIn;  
MessageOut(WCF.BindingType)="customBinding";  
MessageOut(WCF.Action)="http://tempuri.org/IReceiveMessage/ReceiveMessage";  
MessageOut(WCF.BindingConfiguration)=@"<binding name=""customBinding""><binaryMessageEncoding /><tcpTransport /></binding>";  
DynamicSendPort(Microsoft.XLANGs.BaseTypes.Address)="net.tcp://localhost:8001/customNetTcp";  
DynamicSendPort(Microsoft.XLANGs.BaseTypes.TransportType)="WCF-Custom";  
```  
  
 <span data-ttu-id="e544d-106">Al especificar propiedades de contexto de WCF, debe tenerse en cuenta lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="e544d-106">Considerations when specifying WCF context properties are as follows:</span></span>  
  
-   <span data-ttu-id="e544d-107">Hay direcciones que pueden asignarse a diversos adaptadores.</span><span class="sxs-lookup"><span data-stu-id="e544d-107">There are addresses that can be mapped to multiple adapters.</span></span> <span data-ttu-id="e544d-108">Por ejemplo, una dirección que empieza por http:// o https:// puede controlarla el adaptador de HTTP, así como los adaptadores WCF-BasicHttp, WCF-WsHttp o WCF-Custom.</span><span class="sxs-lookup"><span data-stu-id="e544d-108">For example, an address that starts with http:// or https:// can be handled by the HTTP adapter as well as by the WCF-BasicHttp, WCF-WsHttp, or WCF-Custom adapters.</span></span> <span data-ttu-id="e544d-109">Para ver otro ejemplo, en el código de ejemplo expuesto anteriormente, ambos usan la dirección que empieza por net.tcp://, y dado que el segundo código de ejemplo usa el enlace personalizado, el adaptador de WCF-Custom debe usarse para controlar la dirección.</span><span class="sxs-lookup"><span data-stu-id="e544d-109">For another example, in the above sample code, both of them are using the address starts with net.tcp://, yet because the second sample code uses custom binding, WCF-Custom adapter should be used to handle the address.</span></span> <span data-ttu-id="e544d-110">Por lo tanto, para identificar el adaptador correcto, debe configurar opcional **Microsoft.XLANGs.BaseTypes.TransportType** campo en un **expresión** forma con el adaptador que desea utilizar.</span><span class="sxs-lookup"><span data-stu-id="e544d-110">Therefore, to identify the correct adapter, you must configure the optional **Microsoft.XLANGs.BaseTypes.TransportType** field in an **Expression** shape with the adapter that you want to use.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="e544d-111">Si la dirección empieza por http:// o https:// y no se especifica la **Microsoft.XLANGs.BaseTypes.TransportType** campo, de forma predeterminada, el motor de BizTalk usará el adaptador de HTTP.</span><span class="sxs-lookup"><span data-stu-id="e544d-111">If the address starts with http:// or https://, and if you do not specify the **Microsoft.XLANGs.BaseTypes.TransportType** field, by default, the BizTalk engine will use the HTTP adapter.</span></span>  
  
-   <span data-ttu-id="e544d-112">El **WCF. BindingType** identifica el enlace por nombre.</span><span class="sxs-lookup"><span data-stu-id="e544d-112">The **WCF.BindingType** identifies the binding by name.</span></span> <span data-ttu-id="e544d-113">Puede tener uno de los valores siguientes:</span><span class="sxs-lookup"><span data-stu-id="e544d-113">It can be one of the following:</span></span>  
  
    -   <span data-ttu-id="e544d-114">basicHttpBinding</span><span class="sxs-lookup"><span data-stu-id="e544d-114">basicHttpBinding</span></span>  
  
    -   <span data-ttu-id="e544d-115">customBinding</span><span class="sxs-lookup"><span data-stu-id="e544d-115">customBinding</span></span>  
  
    -   <span data-ttu-id="e544d-116">netMsmqBinding</span><span class="sxs-lookup"><span data-stu-id="e544d-116">netMsmqBinding</span></span>  
  
    -   <span data-ttu-id="e544d-117">netNamedPipeBinding</span><span class="sxs-lookup"><span data-stu-id="e544d-117">netNamedPipeBinding</span></span>  
  
    -   <span data-ttu-id="e544d-118">netTcpBinding</span><span class="sxs-lookup"><span data-stu-id="e544d-118">netTcpBinding</span></span>  
  
    -   <span data-ttu-id="e544d-119">wsFederationHttpBinding</span><span class="sxs-lookup"><span data-stu-id="e544d-119">wsFederationHttpBinding</span></span>  
  
    -   <span data-ttu-id="e544d-120">wsHttpBinding</span><span class="sxs-lookup"><span data-stu-id="e544d-120">wsHttpBinding</span></span>  
  
     <span data-ttu-id="e544d-121">La lista anterior puede ampliarse.</span><span class="sxs-lookup"><span data-stu-id="e544d-121">The above list can be extended.</span></span> <span data-ttu-id="e544d-122">Por ejemplo, puede agregar su propio enlace, como FtpBinding.</span><span class="sxs-lookup"><span data-stu-id="e544d-122">For example, you can add your own binding to it such as FtpBinding.</span></span>  
  
-   <span data-ttu-id="e544d-123">El **WCF. BindingConfiguration** especifica la configuración de enlace para el tipo de enlace.</span><span class="sxs-lookup"><span data-stu-id="e544d-123">The **WCF.BindingConfiguration** specifies the binding configuration for the binding type.</span></span> <span data-ttu-id="e544d-124">Toma cualquier enlace registrado en el archivo de configuración del equipo.</span><span class="sxs-lookup"><span data-stu-id="e544d-124">It takes any binding that are registered in the machine configuration file.</span></span> <span data-ttu-id="e544d-125">También toma la configuración XML en el mismo formato usado en la configuración del enlace del archivo de configuración WCF.</span><span class="sxs-lookup"><span data-stu-id="e544d-125">It also takes the XML configuration in the same format as used in the binding configuration in the WCF configuration file.</span></span>  
  
-   <span data-ttu-id="e544d-126">Puede que tenga que especificar propiedades de WCF adicionales.</span><span class="sxs-lookup"><span data-stu-id="e544d-126">You may need to specify additional WCF properties.</span></span> <span data-ttu-id="e544d-127">Puede escribir **WCF** en el Editor de expresiones y las características de IntelliSense característica debe enumerar todas las propiedades de contexto disponibles.</span><span class="sxs-lookup"><span data-stu-id="e544d-127">You can type **WCF** in the Expression Editor, and the IntelliSense feature should list all the available context properties.</span></span> <span data-ttu-id="e544d-128">Para obtener más información acerca de las propiedades de contexto WCF, vea [propiedades y esquema de propiedades de adaptadores de WCF](../core/wcf-adapters-property-schema-and-properties.md).</span><span class="sxs-lookup"><span data-stu-id="e544d-128">For more information about WCF context properties, see [WCF Adapters Property Schema and Properties](../core/wcf-adapters-property-schema-and-properties.md).</span></span>  
  
 <span data-ttu-id="e544d-129">Los ejemplos anteriores muestran cómo configurar **WCF. Acción** con una sola acción.</span><span class="sxs-lookup"><span data-stu-id="e544d-129">The preceding examples show how to configure **WCF.Action** with a single action.</span></span> <span data-ttu-id="e544d-130">Para varios escenarios de asignación de acciones, el adaptador de WCF no es compatible con el uso de varias asignaciones de acciones con puertos de envío dinámicos.</span><span class="sxs-lookup"><span data-stu-id="e544d-130">For multiple actions mapping scenarios, WCF adapter do not support using multiple actions mapping with dynamic send ports.</span></span> <span data-ttu-id="e544d-131">Basta con establecer la acción real el **WCF. Acción** propiedad de contexto como se muestra anteriormente.</span><span class="sxs-lookup"><span data-stu-id="e544d-131">You can just set the actual action in the **WCF.Action** context property as showing in above.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e544d-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="e544d-132">See Also</span></span>  
 <span data-ttu-id="e544d-133">[Especificar acciones SOAP para WCF adaptadores de envío](../core/specifying-soap-actions-for-wcf-send-adapters.md) </span><span class="sxs-lookup"><span data-stu-id="e544d-133">[Specifying SOAP Actions for WCF Send Adapters](../core/specifying-soap-actions-for-wcf-send-adapters.md) </span></span>  
 <span data-ttu-id="e544d-134">[Cómo usar expresiones para asignar valores a puertos dinámicos](../core/how-to-use-expressions-to-assign-values-to-dynamic-ports.md) </span><span class="sxs-lookup"><span data-stu-id="e544d-134">[How to Use Expressions to Assign Values to Dynamic Ports](../core/how-to-use-expressions-to-assign-values-to-dynamic-ports.md) </span></span>  
 [<span data-ttu-id="e544d-135">Enlaces de puertos</span><span class="sxs-lookup"><span data-stu-id="e544d-135">Port Bindings</span></span>](../core/port-bindings.md)