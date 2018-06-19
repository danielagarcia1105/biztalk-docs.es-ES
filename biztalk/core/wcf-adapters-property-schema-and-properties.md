---
title: Esquema de propiedades de adaptadores WCF y propiedades | Documentos de Microsoft
ms.custom: ''
ms.date: 02/09/2018
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2093745e-86c0-4276-a7cc-a0187391ca4a
caps.latest.revision: 19
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 04bb48f54347eabeb886d91fa245bae18c34de55
ms.sourcegitcommit: 50798e04fdcaf5dce5288aa18608e2a981b162fc
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/11/2018
ms.locfileid: "29139300"
---
# <a name="wcf-adapters-property-schema-and-properties"></a><span data-ttu-id="0a7c0-102">Propiedades y esquema de propiedades de adaptadores de WCF</span><span class="sxs-lookup"><span data-stu-id="0a7c0-102">WCF Adapters Property Schema and Properties</span></span>
<span data-ttu-id="0a7c0-103">Obtenga información acerca de las propiedades promocionadas en el esquema de propiedades del adaptador WCF.</span><span class="sxs-lookup"><span data-stu-id="0a7c0-103">Read about the promoted properties in the WCF adapter property schema.</span></span> <span data-ttu-id="0a7c0-104">Los adaptadores de WCF asignan valores a las propiedades que puede utilizar en su aplicación.</span><span class="sxs-lookup"><span data-stu-id="0a7c0-104">The WCF adapters assign values to the properties that you can use in your application.</span></span> <span data-ttu-id="0a7c0-105">El adaptador de WCF también proporciona un mecanismo para leer pero no promociona las propiedades personalizadas en el contexto de mensaje de BizTalk y un mecanismo para promocionar las propiedades personalizadas en el contexto de mensaje de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="0a7c0-105">WCF adapter also provides a mechanism to write but not promote the custom properties to the BizTalk message context, and a mechanism to promote the custom properties to the BizTalk message context.</span></span> <span data-ttu-id="0a7c0-106">Para obtener más información, consulte [encabezados SOAP con servicios de WCF publican](../core/soap-headers-with-published-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="0a7c0-106">For more details, see [SOAP Headers with Published WCF Services](../core/soap-headers-with-published-wcf-services.md).</span></span>  

## <a name="promoted-properties"></a><span data-ttu-id="0a7c0-107">Propiedades promocionadas</span><span class="sxs-lookup"><span data-stu-id="0a7c0-107">Promoted properties</span></span>  
<span data-ttu-id="0a7c0-108">**Namespace:** http://schemas.microsoft.com/BizTalk/2006/01/Adapters/WCF-properties</span><span class="sxs-lookup"><span data-stu-id="0a7c0-108">**Namespace:** http://schemas.microsoft.com/BizTalk/2006/01/Adapters/WCF-properties</span></span>  

#### <a name="action"></a><span data-ttu-id="0a7c0-109">Acción</span><span class="sxs-lookup"><span data-stu-id="0a7c0-109">Action</span></span>
<span data-ttu-id="0a7c0-110">Especifique el **SOAPAction** campo de encabezado para los mensajes salientes.</span><span class="sxs-lookup"><span data-stu-id="0a7c0-110">Specify the **SOAPAction** header field for outgoing messages.</span></span> <span data-ttu-id="0a7c0-111">Puede especificar este valor de dos maneras diferentes: el formato de acción única y el formato de asignación de acciones.</span><span class="sxs-lookup"><span data-stu-id="0a7c0-111">You can specify this value in two different ways: the single action format and the action mapping format.</span></span> <span data-ttu-id="0a7c0-112">Si establece esta propiedad en el formato de acción única: por ejemplo, http://contoso.com/Svc/Op1: el **SOAPAction** encabezado mensajes salientes siempre se establece en el valor especificado en esta propiedad.</span><span class="sxs-lookup"><span data-stu-id="0a7c0-112">If you set this property in the single action format—for example, http://contoso.com/Svc/Op1 — the **SOAPAction** header for outgoing messages is always set to the value specified in this property.</span></span>

<span data-ttu-id="0a7c0-113">Si establece esta propiedad en el formato de asignación de acción, la salida **SOAPAction** encabezado viene determinado por la **BTS. Operación** propiedad de contexto.</span><span class="sxs-lookup"><span data-stu-id="0a7c0-113">If you set this property in the action mapping format, the outgoing **SOAPAction** header is determined by the **BTS.Operation** context property.</span></span> <span data-ttu-id="0a7c0-114">Por ejemplo, si esta propiedad se establece en el siguiente formato XML y **BTS. Operación** propiedad está establecida en Op1, el adaptador de envío WCF usa `http://contoso.com/Svc/Op1` para los salientes **SOAPAction** encabezado.</span><span class="sxs-lookup"><span data-stu-id="0a7c0-114">For example, if this property is set to the following XML format and the **BTS.Operation** property is set to Op1, the WCF send adapter uses `http://contoso.com/Svc/Op1` for the outgoing **SOAPAction** header.</span></span>

```
<BtsActionMapping>
<Operation Name="Op1" Action="http://contoso.com/Svc/Op1">
<Operation Name="Op2" Action="http://contoso.com/Svc/Op2">
</BtsActionMapping>
```

<span data-ttu-id="0a7c0-115">Si los mensajes salientes proceden de un puerto de orquestación, las instancias de orquestación establecen dinámicamente la **BTS. Operación** propiedad con el nombre de la operación del puerto.</span><span class="sxs-lookup"><span data-stu-id="0a7c0-115">If outgoing messages come from an orchestration port, orchestration instances dynamically set the **BTS.Operation** property with the operation name of the port.</span></span> <span data-ttu-id="0a7c0-116">Si los mensajes salientes se enrutan con enrutamiento por contenidos, puede establecer el **BTS. Operación** propiedad en componentes de canalización.</span><span class="sxs-lookup"><span data-stu-id="0a7c0-116">If outgoing messages are routed with content-based routing, you can set the **BTS.Operation** property in pipeline components.</span></span>
<span data-ttu-id="0a7c0-117">Esta propiedad se promociona automáticamente a partir de los mensajes entrantes con el formato de acción única.</span><span class="sxs-lookup"><span data-stu-id="0a7c0-117">This property is automatically promoted from incoming messages with the single action format.</span></span>

<span data-ttu-id="0a7c0-118">Tipo: cadena</span><span class="sxs-lookup"><span data-stu-id="0a7c0-118">Type: String</span></span>  
<span data-ttu-id="0a7c0-119">Valor predeterminado: una cadena vacía</span><span class="sxs-lookup"><span data-stu-id="0a7c0-119">Default value: An empty string</span></span>  
<span data-ttu-id="0a7c0-120">Se aplica a: WCF todos los adaptadores de envío</span><span class="sxs-lookup"><span data-stu-id="0a7c0-120">Applies to: All WCF send adapters</span></span>

#### <a name="affiliateapplicationname"></a><span data-ttu-id="0a7c0-121">AffiliateApplicationName</span><span class="sxs-lookup"><span data-stu-id="0a7c0-121">AffiliateApplicationName</span></span>
<span data-ttu-id="0a7c0-122">Especificar la aplicación afiliada que se utilizará para el inicio de sesión único empresarial (SSO).</span><span class="sxs-lookup"><span data-stu-id="0a7c0-122">Specify the affiliate application to use for Enterprise Single Sign-On (SSO).</span></span> <span data-ttu-id="0a7c0-123">Esta propiedad es necesaria si la **UseSSO** propiedad está establecida en **True**.</span><span class="sxs-lookup"><span data-stu-id="0a7c0-123">This property is required if the **UseSSO** property is set to **True**.</span></span> 

<span data-ttu-id="0a7c0-124">Tipo: cadena</span><span class="sxs-lookup"><span data-stu-id="0a7c0-124">Type: String</span></span>  
<span data-ttu-id="0a7c0-125">Valor predeterminado: una cadena vacía</span><span class="sxs-lookup"><span data-stu-id="0a7c0-125">Default value: An empty string</span></span>  
<span data-ttu-id="0a7c0-126">Se aplica a: WCF todos los adaptadores de envío *excepto* el adaptador WCF-NetNamedPipe</span><span class="sxs-lookup"><span data-stu-id="0a7c0-126">Applies to: All WCF send adapters *except* the WCF-NetNamedPipe adapter</span></span>

#### <a name="algorithmsuite"></a><span data-ttu-id="0a7c0-127">AlgorithmSuite</span><span class="sxs-lookup"><span data-stu-id="0a7c0-127">AlgorithmSuite</span></span>
<span data-ttu-id="0a7c0-128">Especificar el cifrado de mensajes y los algoritmos de encapsulado de claves.</span><span class="sxs-lookup"><span data-stu-id="0a7c0-128">Specify the message encryption and key-wrap algorithms.</span></span> <span data-ttu-id="0a7c0-129">Estos algoritmos se asignan a los que se indican en la especificación Security Policy Language (WS-SecurityPolicy).</span><span class="sxs-lookup"><span data-stu-id="0a7c0-129">These algorithms map to those specified in the Security Policy Language (WS-SecurityPolicy) specification.</span></span>

<span data-ttu-id="0a7c0-130">Para obtener más información acerca de los valores aplicables para la **AlgorithmSuite** propiedad, vea la **algorithmsuite** propiedad en la **cuadro de diálogo de propiedades de transporte de WCF-NetTcp, envío, Seguridad** ficha [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span><span class="sxs-lookup"><span data-stu-id="0a7c0-130">For more information about the applicable values for the **AlgorithmSuite** property, see the **Algorithm suite** property in the **WCF-NetTcp Transport Properties Dialog Box, Send, Security** tab [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span>

<span data-ttu-id="0a7c0-131">Tipo: cadena</span><span class="sxs-lookup"><span data-stu-id="0a7c0-131">Type: String</span></span>  
<span data-ttu-id="0a7c0-132">Valor predeterminado: **Basic256**</span><span class="sxs-lookup"><span data-stu-id="0a7c0-132">Default value: **Basic256**</span></span>  
<span data-ttu-id="0a7c0-133">Se aplica a:</span><span class="sxs-lookup"><span data-stu-id="0a7c0-133">Applies to:</span></span> 

- <span data-ttu-id="0a7c0-134">Adaptador de WCF-BasicHttp</span><span class="sxs-lookup"><span data-stu-id="0a7c0-134">WCF-BasicHttp adapter</span></span>
- <span data-ttu-id="0a7c0-135">Adaptador de WCF-NetMsmq</span><span class="sxs-lookup"><span data-stu-id="0a7c0-135">WCF-NetMsmq adapter</span></span>
- <span data-ttu-id="0a7c0-136">Adaptador de WCF-NetTcp</span><span class="sxs-lookup"><span data-stu-id="0a7c0-136">WCF-NetTcp adapter</span></span>
- <span data-ttu-id="0a7c0-137">Adaptador de WCF-WSHttp</span><span class="sxs-lookup"><span data-stu-id="0a7c0-137">WCF-WSHttp adapter</span></span>

#### <a name="bindingconfiguration"></a><span data-ttu-id="0a7c0-138">BindingConfiguration</span><span class="sxs-lookup"><span data-stu-id="0a7c0-138">BindingConfiguration</span></span>
<span data-ttu-id="0a7c0-139">Especificar una cadena XML con el  **\<enlace\>**  elemento que se va a configurar los distintos tipos de enlaces predefinidos proporcionados por Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="0a7c0-139">Specify an XML string with the **\<binding\>** element to configure different types of predefined bindings provided by Windows Communication Foundation (WCF).</span></span> <span data-ttu-id="0a7c0-140">Para obtener más información sobre el enlace proporcionado por el sistema y el enlace personalizado, vea los temas correspondientes en la sección Vea también.</span><span class="sxs-lookup"><span data-stu-id="0a7c0-140">For more information about the system-provided binding and custom binding, see the appropriate topics in See Also.</span></span>

<span data-ttu-id="0a7c0-141">Ejemplo:</span><span class="sxs-lookup"><span data-stu-id="0a7c0-141">Example:</span></span>

```
<binding name="wsHttpBinding" transactionFlow="true">
<security><message clientCredentialType="UserName"></security>
</binding>
```

<span data-ttu-id="0a7c0-142">Tipo: cadena</span><span class="sxs-lookup"><span data-stu-id="0a7c0-142">Type: String</span></span>  
<span data-ttu-id="0a7c0-143">Valor predeterminado: una cadena vacía</span><span class="sxs-lookup"><span data-stu-id="0a7c0-143">Default value: An empty string</span></span>  
<span data-ttu-id="0a7c0-144">Se aplica a: adaptador de WCF-Custom, adaptador de WCF-CustomIsolated</span><span class="sxs-lookup"><span data-stu-id="0a7c0-144">Applies to: WCF-Custom adapter, WCF-CustomIsolated adapter</span></span>

#### <a name="bindingtype"></a><span data-ttu-id="0a7c0-145">BindingType</span><span class="sxs-lookup"><span data-stu-id="0a7c0-145">BindingType</span></span>
<span data-ttu-id="0a7c0-146">Especifique qué tipo de enlace utilizar para el extremo.</span><span class="sxs-lookup"><span data-stu-id="0a7c0-146">Specify the type of the binding to use for the endpoint.</span></span> <span data-ttu-id="0a7c0-147">Para obtener más información acerca de los valores aplicables para el **BindingType** propiedad, vea la **BindingType** propiedad en la **cuadro de diálogo de propiedades de transporte WCF-Custom, envío, enlace** ficha [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span><span class="sxs-lookup"><span data-stu-id="0a7c0-147">For more information about the applicable values for the **BindingType** property, see the **Binding Type** property in the **WCF-Custom Transport Properties Dialog Box, Send, Binding** tab [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span>

<span data-ttu-id="0a7c0-148">Tipo: cadena</span><span class="sxs-lookup"><span data-stu-id="0a7c0-148">Type: String</span></span>  
<span data-ttu-id="0a7c0-149">Valor predeterminado: una cadena vacía</span><span class="sxs-lookup"><span data-stu-id="0a7c0-149">Default value: An empty string</span></span>  
<span data-ttu-id="0a7c0-150">Se aplica a: adaptador de WCF-Custom, adaptador de WCF-CustomIsolated</span><span class="sxs-lookup"><span data-stu-id="0a7c0-150">Applies to: WCF-Custom adapter, WCF-CustomIsolated adapter</span></span>

#### <a name="clientcertificate"></a><span data-ttu-id="0a7c0-151">ClientCertificate</span><span class="sxs-lookup"><span data-stu-id="0a7c0-151">ClientCertificate</span></span>
<span data-ttu-id="0a7c0-152">Especificar la huella digital del certificado X.509 para la autenticación de este puerto de envío en servicios.</span><span class="sxs-lookup"><span data-stu-id="0a7c0-152">Specify the thumbprint of the X.509 certificate for authenticating this send port to services.</span></span> <span data-ttu-id="0a7c0-153">Esta propiedad es necesaria si la **ClientCredentialsType** propiedad está establecida en **certificado**.</span><span class="sxs-lookup"><span data-stu-id="0a7c0-153">This property is required if the **ClientCredentialsType** property is set to **Certificate**.</span></span> <span data-ttu-id="0a7c0-154">El certificado que se usará para esta propiedad debe estar instalado en el **mi** almacenar en la **usuario actual** ubicación.</span><span class="sxs-lookup"><span data-stu-id="0a7c0-154">The certificate to be used for this property must be installed into the **My** store in the **Current User** location.</span></span>

<span data-ttu-id="0a7c0-155">Tipo: cadena</span><span class="sxs-lookup"><span data-stu-id="0a7c0-155">Type: String</span></span>  
<span data-ttu-id="0a7c0-156">Valor predeterminado: una cadena vacía</span><span class="sxs-lookup"><span data-stu-id="0a7c0-156">Default value: An empty string</span></span>  
<span data-ttu-id="0a7c0-157">Se aplica a:</span><span class="sxs-lookup"><span data-stu-id="0a7c0-157">Applies to:</span></span> 

- <span data-ttu-id="0a7c0-158">Adaptador de envío WCF-BasicHttp</span><span class="sxs-lookup"><span data-stu-id="0a7c0-158">WCF-BasicHttp send adapter</span></span>
- <span data-ttu-id="0a7c0-159">Adaptador de envío WCF-WSHttp</span><span class="sxs-lookup"><span data-stu-id="0a7c0-159">WCF-WSHttp send adapter</span></span>
- <span data-ttu-id="0a7c0-160">Adaptador de envío WCF-NetTcp</span><span class="sxs-lookup"><span data-stu-id="0a7c0-160">WCF-NetTcp send adapter</span></span>
- <span data-ttu-id="0a7c0-161">Adaptador de envío WCF-NetMsmq</span><span class="sxs-lookup"><span data-stu-id="0a7c0-161">WCF-NetMsmq send adapter</span></span>

#### <a name="closetimeout"></a><span data-ttu-id="0a7c0-162">CloseTimeout</span><span class="sxs-lookup"><span data-stu-id="0a7c0-162">CloseTimeout</span></span>
<span data-ttu-id="0a7c0-163">Especificar un valor de marco temporal que indica el intervalo de tiempo proporcionado para que se complete una operación de cierre del canal.</span><span class="sxs-lookup"><span data-stu-id="0a7c0-163">Specify a time span value that indicates the interval of time provided for a channel close operation to complete.</span></span>

<span data-ttu-id="0a7c0-164">Tipo: cadena</span><span class="sxs-lookup"><span data-stu-id="0a7c0-164">Type: String</span></span>  
<span data-ttu-id="0a7c0-165">Valor predeterminado: 00:01:00</span><span class="sxs-lookup"><span data-stu-id="0a7c0-165">Default value: 00:01:00</span></span>  
<span data-ttu-id="0a7c0-166">Se aplica a: todos los adaptadores WCF *excepto* WCF-Custom y WCF-CustomIsolated</span><span class="sxs-lookup"><span data-stu-id="0a7c0-166">Applies to: All WCF adapters *except* WCF-Custom and WCF-CustomIsolated</span></span>

#### <a name="customdeadletterqueue"></a><span data-ttu-id="0a7c0-167">CustomDeadLetterQueue</span><span class="sxs-lookup"><span data-stu-id="0a7c0-167">CustomDeadLetterQueue</span></span>
<span data-ttu-id="0a7c0-168">Especifique el URI completo con el **net.msmq** esquema para la ubicación de la cola de mensajes no enviados por aplicación, donde se colocan los mensajes que han expirado o cuya transferencia o entrega ha fallado.</span><span class="sxs-lookup"><span data-stu-id="0a7c0-168">Specify the fully qualified URI with the **net.msmq** scheme for the location of the per-application dead-letter queue, where messages that have expired or that have failed transfer or delivery are placed.</span></span> <span data-ttu-id="0a7c0-169">Por ejemplo, net.msmq://localhost/deadLetterQueueName.</span><span class="sxs-lookup"><span data-stu-id="0a7c0-169">For example, net.msmq://localhost/deadLetterQueueName.</span></span> <span data-ttu-id="0a7c0-170">La cola de mensajes con problemas de entrega es una cola en el administrador de cola de la aplicación de envío para mensajes caducados que no se han podido entregar.</span><span class="sxs-lookup"><span data-stu-id="0a7c0-170">The dead-letter queue is a queue on the queue manager of the sending application for expired messages that have failed to be delivered.</span></span> <span data-ttu-id="0a7c0-171">Esta propiedad es necesaria si la **DeadLetterQueue** propiedad está establecida en **personalizado**.</span><span class="sxs-lookup"><span data-stu-id="0a7c0-171">This property is required if the **DeadLetterQueue** property is set to **Custom**.</span></span>

<span data-ttu-id="0a7c0-172">Tipo: cadena</span><span class="sxs-lookup"><span data-stu-id="0a7c0-172">Type: String</span></span>  
<span data-ttu-id="0a7c0-173">Valor predeterminado: una cadena vacía</span><span class="sxs-lookup"><span data-stu-id="0a7c0-173">Default value: An empty string</span></span>  
<span data-ttu-id="0a7c0-174">Se aplica a: adaptador de envío WCF-NetMsmq</span><span class="sxs-lookup"><span data-stu-id="0a7c0-174">Applies to: WCF-NetMsmq send adapter</span></span>

#### <a name="deadletterqueue"></a><span data-ttu-id="0a7c0-175">DeadLetterQueue</span><span class="sxs-lookup"><span data-stu-id="0a7c0-175">DeadLetterQueue</span></span>
<span data-ttu-id="0a7c0-176">Especificar la cola de mensajes con problemas de entrega a la que se transferirán los mensajes que no se han podido entregar a la aplicación.</span><span class="sxs-lookup"><span data-stu-id="0a7c0-176">Specify the dead-letter queue where messages that have failed to be delivered to the application will be transferred.</span></span> <span data-ttu-id="0a7c0-177">Para obtener más información sobre los mensajes entregados a la cola de mensajes no enviados, consulte el **enlace de cuadro de diálogo de propiedades de transporte WCF-NetMsmq, envío,** ficha [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span><span class="sxs-lookup"><span data-stu-id="0a7c0-177">For more information about the messages delivered to the dead-letter queue, see the **WCF-NetMsmq Transport Properties Dialog Box, Send, Binding** tab [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span>

<span data-ttu-id="0a7c0-178">Tipo: cadena</span><span class="sxs-lookup"><span data-stu-id="0a7c0-178">Type: String</span></span>  
<span data-ttu-id="0a7c0-179">Valor predeterminado: **sistema**</span><span class="sxs-lookup"><span data-stu-id="0a7c0-179">Default value: **System**</span></span>  
<span data-ttu-id="0a7c0-180">Se aplica a: adaptador de envío WCF-NetMsmq</span><span class="sxs-lookup"><span data-stu-id="0a7c0-180">Applies to: WCF-NetMsmq send adapter</span></span>

#### <a name="disablelocationonfailure"></a><span data-ttu-id="0a7c0-181">DisableLocationOnFailure</span><span class="sxs-lookup"><span data-stu-id="0a7c0-181">DisableLocationOnFailure</span></span>
<span data-ttu-id="0a7c0-182">Especificar si se va a deshabilitar la ubicación de recepción cuyo procesamiento de entrada no se puede realizar correctamente debido a un error de canalización de recepción o de enrutamiento.</span><span class="sxs-lookup"><span data-stu-id="0a7c0-182">Specify whether to disable the receive location that fails inbound processing due to a receive pipeline failure or a routing failure.</span></span> <span data-ttu-id="0a7c0-183">Puede que desee establecer esta propiedad en **True** cuando recibe se pueden deshabilitar ubicaciones y denegación de servicio (DoS) no constituye un problema.</span><span class="sxs-lookup"><span data-stu-id="0a7c0-183">You may want to set this property to **True** when receive locations can be disabled and Denial-of-Service (DoS) is not a concern.</span></span>

<span data-ttu-id="0a7c0-184">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="0a7c0-184">For example:</span></span>  
- <span data-ttu-id="0a7c0-185">Adaptador de WCF-Custom: cuando el **BindingType** propiedad está establecida en **netMsmqBinding**.</span><span class="sxs-lookup"><span data-stu-id="0a7c0-185">WCF-Custom adapter: When the **BindingType** property is set to **netMsmqBinding**.</span></span>
- <span data-ttu-id="0a7c0-186">Adaptador de WCF-Custom: cuando el **BindingType** propiedad está establecida en **customBinding**y el **BindingConfiguration** está configurado para usar canales personalizados que se basan en los transportes en cola como MSMQ.</span><span class="sxs-lookup"><span data-stu-id="0a7c0-186">WCF-Custom adapter: When the **BindingType** property is set to **customBinding**, and the **BindingConfiguration** property is configured to use custom channels that rely on queued transports such as MSMQ.</span></span>
- <span data-ttu-id="0a7c0-187">Adaptador de WCF-CustomIsolated: cuando el **BindingType** propiedad está establecida en **customBinding**y el **BindingConfiguration** está configurado para usar canales personalizados que se basan en transportes en cola como MSMQ</span><span class="sxs-lookup"><span data-stu-id="0a7c0-187">WCF-CustomIsolated adapter: When the **BindingType** property is set to **customBinding**, and the **BindingConfiguration** property is configured to use custom channels that rely on queued transports such as MSMQ</span></span>
- <span data-ttu-id="0a7c0-188">Adaptador de WCF-NetMsmq</span><span class="sxs-lookup"><span data-stu-id="0a7c0-188">WCF-NetMsmq adapter</span></span>

<span data-ttu-id="0a7c0-189">Tipo: booleano</span><span class="sxs-lookup"><span data-stu-id="0a7c0-189">Type: Boolean</span></span>  
<span data-ttu-id="0a7c0-190">Valor predeterminado: **False**</span><span class="sxs-lookup"><span data-stu-id="0a7c0-190">Default: **False**</span></span>  
<span data-ttu-id="0a7c0-191">Se aplica a:</span><span class="sxs-lookup"><span data-stu-id="0a7c0-191">Applies to:</span></span>  
- <span data-ttu-id="0a7c0-192">Adaptador de recepción de WCF-NetMsmq</span><span class="sxs-lookup"><span data-stu-id="0a7c0-192">WCF-NetMsmq receive adapter</span></span>
- <span data-ttu-id="0a7c0-193">Adaptador de recepción de WCF-Custom</span><span class="sxs-lookup"><span data-stu-id="0a7c0-193">WCF-Custom receive adapter</span></span>
- <span data-ttu-id="0a7c0-194">Adaptador de recepción WCF-CustomIsolated</span><span class="sxs-lookup"><span data-stu-id="0a7c0-194">WCF-CustomIsolated receive adapter</span></span>

#### <a name="enabletransaction"></a><span data-ttu-id="0a7c0-195">EnableTransaction</span><span class="sxs-lookup"><span data-stu-id="0a7c0-195">EnableTransaction</span></span>
<span data-ttu-id="0a7c0-196">El efecto de esta propiedad varía dependiendo del adaptador de WCF.</span><span class="sxs-lookup"><span data-stu-id="0a7c0-196">The effect of this property varies depending on the WCF adapter.</span></span> <span data-ttu-id="0a7c0-197">Para obtener más información acerca de esta propiedad, vea los temas "Cómo..." para cada adaptador WCF en [adaptadores de WCF](../core/wcf-adapters.md).</span><span class="sxs-lookup"><span data-stu-id="0a7c0-197">For more information about this property, see how-to topics for each WCF adapter in [WCF Adapters](../core/wcf-adapters.md).</span></span>

<span data-ttu-id="0a7c0-198">Tipo: booleano</span><span class="sxs-lookup"><span data-stu-id="0a7c0-198">Type: Boolean</span></span>  
<span data-ttu-id="0a7c0-199">Se aplica a:</span><span class="sxs-lookup"><span data-stu-id="0a7c0-199">Applies to:</span></span> 

- <span data-ttu-id="0a7c0-200">Adaptador de WCF-WSHttp</span><span class="sxs-lookup"><span data-stu-id="0a7c0-200">WCF-WSHttp adapter</span></span>
- <span data-ttu-id="0a7c0-201">Adaptador de WCF-NetTcp</span><span class="sxs-lookup"><span data-stu-id="0a7c0-201">WCF-NetTcp adapter</span></span>
- <span data-ttu-id="0a7c0-202">Adaptador de WCF-NetNamedPipe</span><span class="sxs-lookup"><span data-stu-id="0a7c0-202">WCF-NetNamedPipe adapter</span></span>
- <span data-ttu-id="0a7c0-203">Adaptador de WCF-NetMsmq</span><span class="sxs-lookup"><span data-stu-id="0a7c0-203">WCF-NetMsmq adapter</span></span>

#### <a name="endpointbehaviorconfiguration"></a><span data-ttu-id="0a7c0-204">EndpointBehaviorConfiguration</span><span class="sxs-lookup"><span data-stu-id="0a7c0-204">EndpointBehaviorConfiguration</span></span>
<span data-ttu-id="0a7c0-205">Especificar una cadena XML con el  **\<comportamiento\>**  elemento de la  **\<endpointBehaviors\>**  elemento que se va a configurar las opciones de comportamiento de un Punto de conexión WCF.</span><span class="sxs-lookup"><span data-stu-id="0a7c0-205">Specify an XML string with the **\<behavior\>** element of the **\<endpointBehaviors\>** element to configure the behavior settings of a WCF endpoint.</span></span> <span data-ttu-id="0a7c0-206">Para obtener más información sobre la  **\<endpointBehaviors\>**  elemento, vea el tema correspondiente en la sección Vea también.</span><span class="sxs-lookup"><span data-stu-id="0a7c0-206">For more information about the **\<endpointBehaviors\>** element, see the appropriate topic in See Also.</span></span>

<span data-ttu-id="0a7c0-207">Ejemplo:</span><span class="sxs-lookup"><span data-stu-id="0a7c0-207">Example:</span></span> 
```
<behavior name="sampleBehavior"><callbackTimeouts/></behavior>
```

<span data-ttu-id="0a7c0-208">Tipo: cadena</span><span class="sxs-lookup"><span data-stu-id="0a7c0-208">Type: String</span></span>  
<span data-ttu-id="0a7c0-209">Valor predeterminado: una cadena vacía</span><span class="sxs-lookup"><span data-stu-id="0a7c0-209">Default value: An empty string</span></span>  
<span data-ttu-id="0a7c0-210">Se aplica a: adaptador de envío WCF-Custom</span><span class="sxs-lookup"><span data-stu-id="0a7c0-210">Applies to: WCF-Custom send adapter</span></span>

#### <a name="establishsecuritycontext"></a><span data-ttu-id="0a7c0-211">EstablishSecurityContext</span><span class="sxs-lookup"><span data-stu-id="0a7c0-211">EstablishSecurityContext</span></span>
<span data-ttu-id="0a7c0-212">Especificar si el canal de seguridad establece una sesión segura.</span><span class="sxs-lookup"><span data-stu-id="0a7c0-212">Specify whether the security channel establishes a secure session.</span></span> <span data-ttu-id="0a7c0-213">Una sesión segura establece un token de contexto de seguridad (SCR) antes de intercambiar los mensajes de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="0a7c0-213">A secure session establishes a Security Context Token (SCT) before exchanging the application messages.</span></span>

<span data-ttu-id="0a7c0-214">Tipo: booleano</span><span class="sxs-lookup"><span data-stu-id="0a7c0-214">Type: Boolean</span></span>  
<span data-ttu-id="0a7c0-215">Valor predeterminado: True</span><span class="sxs-lookup"><span data-stu-id="0a7c0-215">Default value: True</span></span>  
<span data-ttu-id="0a7c0-216">Aplicar a: adaptador de WCF-WSHttp</span><span class="sxs-lookup"><span data-stu-id="0a7c0-216">Applied to: WCF-WSHttp adapter</span></span>

#### <a name="fromaddress"></a><span data-ttu-id="0a7c0-217">FromAddress</span><span class="sxs-lookup"><span data-stu-id="0a7c0-217">FromAddress</span></span>
<span data-ttu-id="0a7c0-218">Indicar la dirección de extremo de origen a través de la que se envían los mensajes WCF entrantes.</span><span class="sxs-lookup"><span data-stu-id="0a7c0-218">Indicate the source endpoint address through which the incoming WCF messages are sent.</span></span> <span data-ttu-id="0a7c0-219">La propiedad se promociona automáticamente desde los mensajes entrantes.</span><span class="sxs-lookup"><span data-stu-id="0a7c0-219">The property is automatically promoted from incoming messages.</span></span>

<span data-ttu-id="0a7c0-220">Tipo: cadena</span><span class="sxs-lookup"><span data-stu-id="0a7c0-220">Type: String</span></span>  
<span data-ttu-id="0a7c0-221">Se aplica a: todos los adaptadores WCF *excepto* adaptador de envío WCF-NetMsmq</span><span class="sxs-lookup"><span data-stu-id="0a7c0-221">Applies to: All WCF adapters *except* the WCF-NetMsmq send adapter</span></span>
  
#### <a name="headers"></a><span data-ttu-id="0a7c0-222">Encabezados</span><span class="sxs-lookup"><span data-stu-id="0a7c0-222">Headers</span></span>
<span data-ttu-id="0a7c0-223">Especificar las referencias de extremo utilizadas para proporcionar información de dirección adicional más allá del URI.</span><span class="sxs-lookup"><span data-stu-id="0a7c0-223">Specify the endpoint references used to provide additional addressing information beyond the URI.</span></span> <span data-ttu-id="0a7c0-224">Cuando se utiliza esta propiedad, esta propiedad debe tener la \< **encabezados** \> elemento como el elemento raíz.</span><span class="sxs-lookup"><span data-stu-id="0a7c0-224">When this property is used, this property must have the \<**headers**\> element as the root element.</span></span> <span data-ttu-id="0a7c0-225">Todos los encabezados de dirección deben colocarse dentro de la \< **encabezados** \> elemento.</span><span class="sxs-lookup"><span data-stu-id="0a7c0-225">All of the address headers must be placed inside the \<**headers**\> element.</span></span> <span data-ttu-id="0a7c0-226">Esta propiedad se promociona automáticamente para los mensajes entrantes.</span><span class="sxs-lookup"><span data-stu-id="0a7c0-226">This property is automatically promoted for incoming messages.</span></span>

<span data-ttu-id="0a7c0-227">Ejemplo:</span><span class="sxs-lookup"><span data-stu-id="0a7c0-227">Example:</span></span>
```
<headers>
<Region xmlns="Uri">"String"</Region>
<Member xmlns="Uri">"String"</Member> 
</headers>
```

<span data-ttu-id="0a7c0-228">Tipo: cadena</span><span class="sxs-lookup"><span data-stu-id="0a7c0-228">Type: String</span></span>  
<span data-ttu-id="0a7c0-229">Se aplica a: todos los adaptadores WCF</span><span class="sxs-lookup"><span data-stu-id="0a7c0-229">Applies to: All WCF adapters</span></span>
  
#### <a name="identity"></a><span data-ttu-id="0a7c0-230">Identidad</span><span class="sxs-lookup"><span data-stu-id="0a7c0-230">Identity</span></span>
<span data-ttu-id="0a7c0-231">Especificar la identidad del servicio que proporciona una ubicación de recepción o espera un puerto de envío.</span><span class="sxs-lookup"><span data-stu-id="0a7c0-231">Specify the identity of the service that a receive location provides or a send port expects.</span></span> <span data-ttu-id="0a7c0-232">Los valores que se pueden especificar para el **identidad** propiedad difieren según la configuración de seguridad.</span><span class="sxs-lookup"><span data-stu-id="0a7c0-232">The values that can be specified for the **Identity** property differ according to the security configuration.</span></span> <span data-ttu-id="0a7c0-233">Esta configuración permite a los clientes autenticar servicios.</span><span class="sxs-lookup"><span data-stu-id="0a7c0-233">These settings enable clients to authenticate services.</span></span> <span data-ttu-id="0a7c0-234">En el proceso de negociación entre los clientes y los servicios, la infraestructura de Windows Communication Foundation (WCF) asegurará que la identidad de los servicios coincide con los valores de los clientes.</span><span class="sxs-lookup"><span data-stu-id="0a7c0-234">In the handshake process between clients and services, the Windows Communication Foundation (WCF) infrastructure will ensure that the identity of the services matches the values of the clients.</span></span>

<span data-ttu-id="0a7c0-235">Ejemplo:</span><span class="sxs-lookup"><span data-stu-id="0a7c0-235">Example:</span></span>
```
<identity>
<userPrincipalName value="username@contoso.com"/>
</identity>
```

<span data-ttu-id="0a7c0-236">Tipo: cadena</span><span class="sxs-lookup"><span data-stu-id="0a7c0-236">Type: String</span></span>  
<span data-ttu-id="0a7c0-237">Valor predeterminado: una cadena vacía</span><span class="sxs-lookup"><span data-stu-id="0a7c0-237">Default value: An empty string</span></span>  
<span data-ttu-id="0a7c0-238">Se aplica a: todos los adaptadores WCF</span><span class="sxs-lookup"><span data-stu-id="0a7c0-238">Applies to: All WCF adapters</span></span>

#### <a name="inboundbodylocation"></a><span data-ttu-id="0a7c0-239">InboundBodyLocation</span><span class="sxs-lookup"><span data-stu-id="0a7c0-239">InboundBodyLocation</span></span>
<span data-ttu-id="0a7c0-240">Especifique la selección de datos para el mensaje SOAP **cuerpo** elemento de mensajes WCF entrantes.</span><span class="sxs-lookup"><span data-stu-id="0a7c0-240">Specify the data selection for the SOAP **Body** element of incoming WCF messages.</span></span> <span data-ttu-id="0a7c0-241">Para obtener más información sobre cómo usar el **InboundBodyLocation** propiedad, vea [especificar el cuerpo del mensaje para los adaptadores de WCF](../core/specifying-the-message-body-for-the-wcf-adapters.md).</span><span class="sxs-lookup"><span data-stu-id="0a7c0-241">For more information about how to use the **InboundBodyLocation** property, see [Specifying the Message Body for the WCF Adapters](../core/specifying-the-message-body-for-the-wcf-adapters.md).</span></span>

<span data-ttu-id="0a7c0-242">Tipo: cadena</span><span class="sxs-lookup"><span data-stu-id="0a7c0-242">Type: String</span></span>  
<span data-ttu-id="0a7c0-243">Valor predeterminado: UseBodyElement</span><span class="sxs-lookup"><span data-stu-id="0a7c0-243">Default value: UseBodyElement</span></span>  

    Applicable values are:  
        - UseBodyElement: Use the content of the SOAP **Body** element of an incoming message to create the BizTalk message body part. If the **Body** element has more than one child element, only the first element becomes the BizTalk message body part.
        - UseEnvelope: Create the BizTalk message body part from the entire SOAP **Envelope** of an incoming message.
        - UseBodyPath: Use the body path expression in the **InboundBodyPathExpression** property to create the BizTalk message body part. The body path expression is evaluated against the immediate child element of the SOAP **Body** element of an incoming message. This property is valid only for solicit-response ports.  

<span data-ttu-id="0a7c0-244">Se aplica a: todos los adaptadores WCF *excepto* envío WCF-NetMsmq</span><span class="sxs-lookup"><span data-stu-id="0a7c0-244">Applies to: All WCF adapters *except* WCF-NetMsmq send</span></span>  

#### <a name="inboundbodypathexpression"></a><span data-ttu-id="0a7c0-245">InboundBodyPathExpression</span><span class="sxs-lookup"><span data-stu-id="0a7c0-245">InboundBodyPathExpression</span></span>
<span data-ttu-id="0a7c0-246">Especificar la expresión de ruta de cuerpo para identificar una parte específica de un mensaje entrante utilizada para crear la parte del cuerpo del mensaje de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="0a7c0-246">Specify the body path expression to identify a specific part of an incoming message used to create the BizTalk message body part.</span></span> <span data-ttu-id="0a7c0-247">Esta expresión se evalúa con respecto al elemento secundario inmediato del mensaje SOAP **cuerpo** nodo de un mensaje entrante.</span><span class="sxs-lookup"><span data-stu-id="0a7c0-247">This body path expression is evaluated against the immediate child element of the SOAP **Body** node of an incoming message.</span></span> <span data-ttu-id="0a7c0-248">Si esta expresión de ruta de cuerpo devuelve varios nodos, solo se elegirá el primero de ellos para la parte del cuerpo del mensaje de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="0a7c0-248">If this body path expression returns more than one node, only the first node is chosen for the BizTalk message body part.</span></span> <span data-ttu-id="0a7c0-249">Esta propiedad es necesaria si la **InboundBodyLocation** propiedad está establecida en **UseBodyPath**.</span><span class="sxs-lookup"><span data-stu-id="0a7c0-249">This property is required if the **InboundBodyLocation** property is set to **UseBodyPath**.</span></span> <span data-ttu-id="0a7c0-250">Para obtener más información sobre cómo usar el **InboundBodyPathExpression** propiedad, vea [propiedades y esquema de propiedades de adaptadores de WCF](../core/wcf-adapters-property-schema-and-properties.md).</span><span class="sxs-lookup"><span data-stu-id="0a7c0-250">For more information about how to use the **InboundBodyPathExpression** property, see [WCF Adapters Property Schema and Properties](../core/wcf-adapters-property-schema-and-properties.md).</span></span>

<span data-ttu-id="0a7c0-251">Tipo: cadena</span><span class="sxs-lookup"><span data-stu-id="0a7c0-251">Type: String</span></span>  
<span data-ttu-id="0a7c0-252">Valor predeterminado: una cadena vacía</span><span class="sxs-lookup"><span data-stu-id="0a7c0-252">Default value: An empty string</span></span>  
<span data-ttu-id="0a7c0-253">Se aplica a: todos los adaptadores WCF *excepto* adaptador de envío WCF-NetMsmq</span><span class="sxs-lookup"><span data-stu-id="0a7c0-253">Applies to: All WCF adapters *except* the WCF-NetMsmq send adapter</span></span>

#### <a name="inboundheaders"></a><span data-ttu-id="0a7c0-254">InboundHeaders</span><span class="sxs-lookup"><span data-stu-id="0a7c0-254">InboundHeaders</span></span>
<span data-ttu-id="0a7c0-255">Use la **InboundHeaders** propiedad para tener acceso a los encabezados SOAP de mensajes WCF entrantes.</span><span class="sxs-lookup"><span data-stu-id="0a7c0-255">Use the **InboundHeaders** property to access the SOAP headers of incoming WCF messages.</span></span> <span data-ttu-id="0a7c0-256">Los adaptadores de WCF copian todos los valores de encabezado SOAP en mensajes entrantes a esta propiedad, que incluyen encabezados SOAP y encabezados SOAP estándares que la infraestructura WCF usa para WS-Addressing, WS-Security y WS-AtomicTransaction.</span><span class="sxs-lookup"><span data-stu-id="0a7c0-256">The WCF adapters copy all the SOAP header values in inbound messages to this property, which include custom SOAP headers and standard SOAP headers that the WCF infrastructure uses for such as WS-Addressing, WS-Security, and WS-AtomicTransaction.</span></span> <span data-ttu-id="0a7c0-257">El valor contenido en la propiedad de contexto es una cadena que contiene los datos XML con la \< **encabezados** \> elemento raíz y los encabezados SOAP entrantes se copian como elementos secundarios de la \< **encabezados** \> elemento.</span><span class="sxs-lookup"><span data-stu-id="0a7c0-257">The value contained in the context property is a string containing XML data with the \<**headers**\> root element, and the incoming SOAP headers are copied as child elements of the \<**headers**\> element.</span></span> <span data-ttu-id="0a7c0-258">Para obtener más información acerca de cómo los encabezados SOAP de acceso con los adaptadores de WCF, vea el ejemplo de SDK Using Custom SOAP Headers with the WCF Adapters de [http://go.microsoft.com/fwlink/?LinkId=79960](http://go.microsoft.com/fwlink/?LinkId=79960).</span><span class="sxs-lookup"><span data-stu-id="0a7c0-258">For more information about how to access SOAP headers with the WCF adapters, see the SDK sample, Using Custom SOAP Headers with the WCF Adapters, from [http://go.microsoft.com/fwlink/?LinkId=79960](http://go.microsoft.com/fwlink/?LinkId=79960).</span></span>

<span data-ttu-id="0a7c0-259">Tipo: cadena</span><span class="sxs-lookup"><span data-stu-id="0a7c0-259">Type: String</span></span>  
<span data-ttu-id="0a7c0-260">Se aplica a: todos los adaptadores WCF *excepto* adaptador de envío WCF-NetMsmq</span><span class="sxs-lookup"><span data-stu-id="0a7c0-260">Applies to: All WCF adapters *except* the WCF-NetMsmq send adapter</span></span>

#### <a name="inboundnodeencoding"></a><span data-ttu-id="0a7c0-261">InboundNodeEncoding</span><span class="sxs-lookup"><span data-stu-id="0a7c0-261">InboundNodeEncoding</span></span>
<span data-ttu-id="0a7c0-262">Especifique el tipo de codificación que WCF adaptador de recepción utiliza para descodificar el nodo identificado por la expresión de ruta de acceso de cuerpo especificada en **InboundBodyPathExpression**.</span><span class="sxs-lookup"><span data-stu-id="0a7c0-262">Specify the type of encoding that the WCF receive adapter uses to decode the node identified by the body path expression specified in **InboundBodyPathExpression**.</span></span> <span data-ttu-id="0a7c0-263">Esta propiedad es necesaria si la **InboundBodyLocation** propiedad está establecida en **UseBodyPath**.</span><span class="sxs-lookup"><span data-stu-id="0a7c0-263">This property is required if the **InboundBodyLocation** property is set to **UseBodyPath**.</span></span>

<span data-ttu-id="0a7c0-264">Tipo: cadena</span><span class="sxs-lookup"><span data-stu-id="0a7c0-264">Type: String</span></span>  
<span data-ttu-id="0a7c0-265">Valor predeterminado: XML</span><span class="sxs-lookup"><span data-stu-id="0a7c0-265">Default value: XML</span></span>  

    Applicable values are:  
        - Base64: Base64 encoding
        - Hex: Hexadecimal encoding
        - String: Text encoding - UTF-8
        - XML: The WCF adapters create the BizTalk message body with the outer XML of the node selected by the body path expression in **InboundBodyPathExpression**.  

<span data-ttu-id="0a7c0-266">Se aplica a: todos los adaptadores WCF *excepto* adaptador de envío WCF-NetMsmq</span><span class="sxs-lookup"><span data-stu-id="0a7c0-266">Applies to: All WCF adapters *except* the WCF-NetMsmq send adapter</span></span>

#### <a name="isfault"></a><span data-ttu-id="0a7c0-267">IsFault</span><span class="sxs-lookup"><span data-stu-id="0a7c0-267">IsFault</span></span>
<span data-ttu-id="0a7c0-268">Indicar si los mensajes de error SOAP se han recibido.</span><span class="sxs-lookup"><span data-stu-id="0a7c0-268">Indicate whether SOAP fault messages are received.</span></span> <span data-ttu-id="0a7c0-269">La propiedad se promociona automáticamente desde los mensajes entrantes.</span><span class="sxs-lookup"><span data-stu-id="0a7c0-269">The property is automatically promoted from incoming messages.</span></span> 

<span data-ttu-id="0a7c0-270">**Nota**</span><span class="sxs-lookup"><span data-stu-id="0a7c0-270">**Note**</span></span>  
<span data-ttu-id="0a7c0-271">El **IsFault** propiedad no se puede usar para comprobar los mensajes recibidos para los errores de transporte, como el error HTTP 404 (archivo o directorio no encontrado).</span><span class="sxs-lookup"><span data-stu-id="0a7c0-271">The **IsFault** property cannot be used to check the received messages for transport errors such as the HTTP 404 (File or Directory Not Found) error.</span></span>

<span data-ttu-id="0a7c0-272">Tipo: booleano</span><span class="sxs-lookup"><span data-stu-id="0a7c0-272">Type: Boolean</span></span>  
<span data-ttu-id="0a7c0-273">Se aplica a: todos los adaptadores WCF *excepto* adaptador de envío WCF-NetMsmq</span><span class="sxs-lookup"><span data-stu-id="0a7c0-273">Applies to: All WCF adapters *except* the WCF-NetMsmq send adapter</span></span>

#### <a name="leasetimeout"></a><span data-ttu-id="0a7c0-274">LeaseTimeout</span><span class="sxs-lookup"><span data-stu-id="0a7c0-274">LeaseTimeout</span></span>
<span data-ttu-id="0a7c0-275">Especificar la duración máxima de una conexión agrupada activa.</span><span class="sxs-lookup"><span data-stu-id="0a7c0-275">Specify the maximum lifetime of an active pooled connection.</span></span> <span data-ttu-id="0a7c0-276">Después de transcurrir el tiempo especificado, la conexión se cierra cuando se atiende la solicitud actual.</span><span class="sxs-lookup"><span data-stu-id="0a7c0-276">After the specified time elapses, the connection closes after the current request is serviced.</span></span>

<span data-ttu-id="0a7c0-277">El adaptador de WCF-NetTcp usa el [NetTcpBinding](http://go.microsoft.com/fwlink/?LinkId=81087) clase para comunicarse con un punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="0a7c0-277">The WCF-NetTcp adapter leverages the [NetTcpBinding](http://go.microsoft.com/fwlink/?LinkId=81087) class to communicate with an endpoint.</span></span> <span data-ttu-id="0a7c0-278">Cuando se usa el [NetTcpBinding](http://go.microsoft.com/fwlink/?LinkId=81087) en escenarios con equilibrio de carga, considere la posibilidad de reducir el tiempo de espera de concesión predeterminado. Para obtener más información acerca del equilibrio de carga cuando se usa el [NetTcpBinding](http://go.microsoft.com/fwlink/?LinkId=81087), vea el tema correspondiente en la sección Vea también.</span><span class="sxs-lookup"><span data-stu-id="0a7c0-278">When using the [NetTcpBinding](http://go.microsoft.com/fwlink/?LinkId=81087) in load-balanced scenarios, consider reducing the default lease time-out. For more information about load balancing when using the [NetTcpBinding](http://go.microsoft.com/fwlink/?LinkId=81087), see the appropriate topic in See Also.</span></span>

<span data-ttu-id="0a7c0-279">Tipo: cadena</span><span class="sxs-lookup"><span data-stu-id="0a7c0-279">Type: String</span></span>  
<span data-ttu-id="0a7c0-280">Valor predeterminado: 00:05:00</span><span class="sxs-lookup"><span data-stu-id="0a7c0-280">Default value: 00:05:00</span></span>  
<span data-ttu-id="0a7c0-281">Se aplica a: adaptador de recepción de WCF-NetTcp</span><span class="sxs-lookup"><span data-stu-id="0a7c0-281">Applies to: WCF-NetTcp receive adapter</span></span>  

#### <a name="maxconcurrentcalls"></a><span data-ttu-id="0a7c0-282">MaxConcurrentCalls</span><span class="sxs-lookup"><span data-stu-id="0a7c0-282">MaxConcurrentCalls</span></span>
<span data-ttu-id="0a7c0-283">Especificar el número de llamadas concurrentes en una instancia de servicio única.</span><span class="sxs-lookup"><span data-stu-id="0a7c0-283">Specify the number of concurrent calls to a single service instance.</span></span> <span data-ttu-id="0a7c0-284">Las llamadas que superan el límite se ponen en cola.</span><span class="sxs-lookup"><span data-stu-id="0a7c0-284">Calls in excess of the limit are queued.</span></span> <span data-ttu-id="0a7c0-285">Establecer este valor como 0 es equivalente a establecerlo como **Int32.MaxValue**.</span><span class="sxs-lookup"><span data-stu-id="0a7c0-285">Setting this value to 0 is equivalent to setting it to **Int32.MaxValue**.</span></span> 

<span data-ttu-id="0a7c0-286">**Nota**</span><span class="sxs-lookup"><span data-stu-id="0a7c0-286">**Note**</span></span>  
<span data-ttu-id="0a7c0-287">No se puede realizar el seguimiento de esta propiedad en la base de datos de importación principal de BAM con los perfiles de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="0a7c0-287">This property cannot be tracked in the BAM Primary Import database with tracking profiles.</span></span> 

<span data-ttu-id="0a7c0-288">Tipo: entero</span><span class="sxs-lookup"><span data-stu-id="0a7c0-288">Type: Integer</span></span>  
<span data-ttu-id="0a7c0-289">Valor predeterminado: 200</span><span class="sxs-lookup"><span data-stu-id="0a7c0-289">Default value: 200</span></span>  
<span data-ttu-id="0a7c0-290">Se aplica a: WCF todos los adaptadores de recepción *excepto* los adaptadores de WCF-Custom y WCF-CustomIsolated</span><span class="sxs-lookup"><span data-stu-id="0a7c0-290">Applies to: All WCF receive adapters *except* the WCF-Custom and WCF-CustomIsolated adapters</span></span>

#### <a name="maxconnections"></a><span data-ttu-id="0a7c0-291">MaxConnections</span><span class="sxs-lookup"><span data-stu-id="0a7c0-291">MaxConnections</span></span>
<span data-ttu-id="0a7c0-292">Especificar el número máximo de conexiones que el agente de escucha puede tener esperando la aceptación de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="0a7c0-292">Specify the maximum number of connections that the listener can have waiting to be accepted by the application.</span></span> <span data-ttu-id="0a7c0-293">Cuando se supera este valor de cuota, se interrumpen las nuevas conexiones entrantes en lugar de esperar la aceptación.</span><span class="sxs-lookup"><span data-stu-id="0a7c0-293">When this quota value is exceeded, new incoming connections are dropped rather than waiting to be accepted.</span></span> 

<span data-ttu-id="0a7c0-294">**Nota**</span><span class="sxs-lookup"><span data-stu-id="0a7c0-294">**Note**</span></span>  
<span data-ttu-id="0a7c0-295">Ya que esta es una propiedad de controlador de adaptador, éste no puede configurarse en componentes de canalización y orquestaciones.</span><span class="sxs-lookup"><span data-stu-id="0a7c0-295">Because this is an adapter handler property, this property cannot be configured in pipeline components and orchestrations.</span></span> 

<span data-ttu-id="0a7c0-296">**Nota**</span><span class="sxs-lookup"><span data-stu-id="0a7c0-296">**Note**</span></span>  
<span data-ttu-id="0a7c0-297">No se puede realizar el seguimiento de esta propiedad en la base de datos de importación principal de BAM con los perfiles de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="0a7c0-297">This property cannot be tracked in the BAM Primary Import database with tracking profiles.</span></span> 

<span data-ttu-id="0a7c0-298">Tipo: entero</span><span class="sxs-lookup"><span data-stu-id="0a7c0-298">Type: Integer</span></span>  
<span data-ttu-id="0a7c0-299">Valor predeterminado: 10</span><span class="sxs-lookup"><span data-stu-id="0a7c0-299">Default value: 10</span></span>  
<span data-ttu-id="0a7c0-300">Se aplica a: adaptador de WCF-NetNamedPipe, adaptador de WCF-NetTcp</span><span class="sxs-lookup"><span data-stu-id="0a7c0-300">Applies to: WCF-NetNamedPipe adapter, WCF-NetTcp adapter</span></span>  

#### <a name="maxreceivedmessagesize"></a><span data-ttu-id="0a7c0-301">MaxReceivedMessageSize</span><span class="sxs-lookup"><span data-stu-id="0a7c0-301">MaxReceivedMessageSize</span></span>
<span data-ttu-id="0a7c0-302">Especificar el tamaño máximo, en bytes, para mensajes (con encabezados incluidos) que se pueden recibir a través de la red.</span><span class="sxs-lookup"><span data-stu-id="0a7c0-302">Specify the maximum size, in bytes, for a message (including headers) that can be received on the wire.</span></span> <span data-ttu-id="0a7c0-303">El tamaño de los mensajes se limita mediante la cantidad de memoria asignada a cada mensaje.</span><span class="sxs-lookup"><span data-stu-id="0a7c0-303">The size of the messages is bounded by the amount of memory allocated for each message.</span></span> <span data-ttu-id="0a7c0-304">Puede usar esta propiedad para limitar la exposición a ataques por denegación de servicio (DoS).</span><span class="sxs-lookup"><span data-stu-id="0a7c0-304">You can use this property to limit exposure to denial of service (DoS) attacks.</span></span>

<span data-ttu-id="0a7c0-305">Tipo: entero</span><span class="sxs-lookup"><span data-stu-id="0a7c0-305">Type: Integer</span></span>  
<span data-ttu-id="0a7c0-306">Valor predeterminado: 65536</span><span class="sxs-lookup"><span data-stu-id="0a7c0-306">Default value: 65536</span></span>  
<span data-ttu-id="0a7c0-307">Se aplica a:</span><span class="sxs-lookup"><span data-stu-id="0a7c0-307">Applies to:</span></span> 
- <span data-ttu-id="0a7c0-308">Adaptador de WCF-BasicHttp</span><span class="sxs-lookup"><span data-stu-id="0a7c0-308">WCF-BasicHttp adapter</span></span>
- <span data-ttu-id="0a7c0-309">Adaptador de WCF-WSHttp</span><span class="sxs-lookup"><span data-stu-id="0a7c0-309">WCF-WSHttp adapter</span></span>
- <span data-ttu-id="0a7c0-310">Adaptador de WCF-NetTcp</span><span class="sxs-lookup"><span data-stu-id="0a7c0-310">WCF-NetTcp adapter</span></span>
- <span data-ttu-id="0a7c0-311">Adaptador de WCF-NetNamedPipe</span><span class="sxs-lookup"><span data-stu-id="0a7c0-311">WCF-NetNamedPipe adapter</span></span>
- <span data-ttu-id="0a7c0-312">Adaptador de recepción de WCF-NetMsmq</span><span class="sxs-lookup"><span data-stu-id="0a7c0-312">WCF-NetMsmq receive adapter</span></span>

#### <a name="messageclientcredentialtype"></a><span data-ttu-id="0a7c0-313">MessageClientCredentialType</span><span class="sxs-lookup"><span data-stu-id="0a7c0-313">MessageClientCredentialType</span></span>
<span data-ttu-id="0a7c0-314">Especificar el tipo de credenciales que se va a usar a la hora de realizar la autenticación de cliente mediante la seguridad basada en mensajes.</span><span class="sxs-lookup"><span data-stu-id="0a7c0-314">Specify the type of credential to be used when performing client authentication using message-based security.</span></span>

<span data-ttu-id="0a7c0-315">Los valores aplicables son distintos para cada adaptador de WCF.</span><span class="sxs-lookup"><span data-stu-id="0a7c0-315">The applicable values differ for each WCF adapter.</span></span> <span data-ttu-id="0a7c0-316">Para obtener más información sobre la **MessageClientCredentialType** propiedad, vea los temas sobre cada adaptador de WCF en [adaptadores de WCF](../core/wcf-adapters.md).</span><span class="sxs-lookup"><span data-stu-id="0a7c0-316">For more information about the **MessageClientCredentialType** property, see how-to topics for each WCF adapter in [WCF Adapters](../core/wcf-adapters.md).</span></span>

<span data-ttu-id="0a7c0-317">Tipo: cadena</span><span class="sxs-lookup"><span data-stu-id="0a7c0-317">Type: String</span></span>  
<span data-ttu-id="0a7c0-318">Se aplica a:</span><span class="sxs-lookup"><span data-stu-id="0a7c0-318">Applies to:</span></span> 
- <span data-ttu-id="0a7c0-319">Adaptador de WCF-BasicHttp</span><span class="sxs-lookup"><span data-stu-id="0a7c0-319">WCF-BasicHttp adapter</span></span>
- <span data-ttu-id="0a7c0-320">Adaptador de WCF-WSHttp</span><span class="sxs-lookup"><span data-stu-id="0a7c0-320">WCF-WSHttp adapter</span></span>
- <span data-ttu-id="0a7c0-321">Adaptador de WCF-NetTcp</span><span class="sxs-lookup"><span data-stu-id="0a7c0-321">WCF-NetTcp adapter</span></span>
- <span data-ttu-id="0a7c0-322">Adaptador de WCF-NetNamedPipe</span><span class="sxs-lookup"><span data-stu-id="0a7c0-322">WCF-NetNamedPipe adapter</span></span>

#### <a name="messageencoding"></a><span data-ttu-id="0a7c0-323">MessageEncoding</span><span class="sxs-lookup"><span data-stu-id="0a7c0-323">MessageEncoding</span></span>
<span data-ttu-id="0a7c0-324">Especificar el codificador que se usa para codificar el mensaje SOAP.</span><span class="sxs-lookup"><span data-stu-id="0a7c0-324">Specify the encoder used to encode the SOAP message.</span></span>

<span data-ttu-id="0a7c0-325">Tipo: cadena</span><span class="sxs-lookup"><span data-stu-id="0a7c0-325">Type: String</span></span>  
<span data-ttu-id="0a7c0-326">Valor predeterminado: texto</span><span class="sxs-lookup"><span data-stu-id="0a7c0-326">Default value: Text</span></span>  

    Applicable values: 
        - Text: Use a text message encoder
        - Mtom: Use a Message Transmission Organization Mechanism 1.0 (MTOM) encoder  

<span data-ttu-id="0a7c0-327">Se aplica a: adaptador de WCF-BasicHttp, adaptador de WCF-WSHttp</span><span class="sxs-lookup"><span data-stu-id="0a7c0-327">Applies to: WCF-BasicHttp adapter, WCF-WSHttp adapter</span></span>


#### <a name="msmqauthenticationmode"></a><span data-ttu-id="0a7c0-328">MsmqAuthenticationMode</span><span class="sxs-lookup"><span data-stu-id="0a7c0-328">MsmqAuthenticationMode</span></span>
<span data-ttu-id="0a7c0-329">Especificar cómo el transporte de MSMQ debe autenticar el mensaje.</span><span class="sxs-lookup"><span data-stu-id="0a7c0-329">Specify how the message must be authenticated by the MSMQ transport.</span></span>

<span data-ttu-id="0a7c0-330">Tipo: cadena</span><span class="sxs-lookup"><span data-stu-id="0a7c0-330">Type: String</span></span>  
<span data-ttu-id="0a7c0-331">Valor predeterminado: **WindowsDomain**</span><span class="sxs-lookup"><span data-stu-id="0a7c0-331">Default value: **WindowsDomain**</span></span>  
    <span data-ttu-id="0a7c0-332">Para obtener más información acerca de los valores aplicables para la **MsmqAuthenticationMode** propiedad, vea la **MsmqAuthenticationMode** propiedad en la **propiedades de transporte de WCF-NetMsmq Cuadro de diálogo cuadro, envío, seguridad** ficha [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span><span class="sxs-lookup"><span data-stu-id="0a7c0-332">For more information about the applicable values for the **MsmqAuthenticationMode** property, see the **MSMQ authentication mode** property in the **WCF-NetMsmq Transport Properties Dialog Box, Send, Security** tab [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span>
<span data-ttu-id="0a7c0-333">Se aplica a: adaptador de WCF-NetMsmq</span><span class="sxs-lookup"><span data-stu-id="0a7c0-333">Applies to: WCF-NetMsmq adapter</span></span>  

#### <a name="msmqencryptionalgorithm"></a><span data-ttu-id="0a7c0-334">MsmqEncryptionAlgorithm</span><span class="sxs-lookup"><span data-stu-id="0a7c0-334">MsmqEncryptionAlgorithm</span></span>
<span data-ttu-id="0a7c0-335">Especificar el algoritmo que se usará para el cifrado de mensajes a través de la red al transferir mensajes entre los administradores de cola de mensajes.</span><span class="sxs-lookup"><span data-stu-id="0a7c0-335">Specify the algorithm to be used for message encryption on the wire when transferring messages between message queue managers.</span></span> <span data-ttu-id="0a7c0-336">Esta propiedad está disponible solo si el **MsmqProtectionLevel** propiedad está establecida en **EncryptAndSign**.</span><span class="sxs-lookup"><span data-stu-id="0a7c0-336">This property is available only if the **MsmqProtectionLevel** property is set to **EncryptAndSign**.</span></span>

<span data-ttu-id="0a7c0-337">Tipo: cadena</span><span class="sxs-lookup"><span data-stu-id="0a7c0-337">Type: String</span></span>  
<span data-ttu-id="0a7c0-338">Valor predeterminado: **RC4Stream**</span><span class="sxs-lookup"><span data-stu-id="0a7c0-338">Default value: **RC4Stream**</span></span>  

    Applicable values are: RC4Stream, AES

<span data-ttu-id="0a7c0-339">Se aplica a: adaptador de WCF-NetMsmq</span><span class="sxs-lookup"><span data-stu-id="0a7c0-339">Applies to: WCF-NetMsmq adapter</span></span>  

#### <a name="msmqprotectionlevel"></a><span data-ttu-id="0a7c0-340">MsmqProtectionLevel</span><span class="sxs-lookup"><span data-stu-id="0a7c0-340">MsmqProtectionLevel</span></span>
<span data-ttu-id="0a7c0-341">Especificar el modo en que los mensajes están protegidos en el nivel de transporte de MSMQ.</span><span class="sxs-lookup"><span data-stu-id="0a7c0-341">Specify the way messages are secured at the level of the MSMQ transport.</span></span>

<span data-ttu-id="0a7c0-342">Tipo: cadena</span><span class="sxs-lookup"><span data-stu-id="0a7c0-342">Type: String</span></span>  
<span data-ttu-id="0a7c0-343">Valor predeterminado: **inicio de sesión**</span><span class="sxs-lookup"><span data-stu-id="0a7c0-343">Default value: **Sign**</span></span>  

    Applicable values are:
        - None: No protection
        - Sign: Messages are signed
        - EncryptAndSign: Messages are encrypted and signed. To use this protection level, you must enable **Active Directory Integration** for **MSMQ**  

<span data-ttu-id="0a7c0-344">Se aplica a: adaptador de WCF-NetMsmq</span><span class="sxs-lookup"><span data-stu-id="0a7c0-344">Applies to: WCF-NetMsmq adapter</span></span>  

#### <a name="msmqsecurehashalgorithm"></a><span data-ttu-id="0a7c0-345">MsmqSecureHashAlgorithm</span><span class="sxs-lookup"><span data-stu-id="0a7c0-345">MsmqSecureHashAlgorithm</span></span>
<span data-ttu-id="0a7c0-346">Especificar el algoritmo hash que se usará para calcular la síntesis del mensaje.</span><span class="sxs-lookup"><span data-stu-id="0a7c0-346">Specify the hash algorithm to be used for computing the message digest.</span></span> <span data-ttu-id="0a7c0-347">Esta propiedad no está disponible si la **MsmqProtectionLevel** propiedad está establecida en **ninguno**.</span><span class="sxs-lookup"><span data-stu-id="0a7c0-347">This property is not available if the **MsmqProtectionLevel** property is set to **None**.</span></span>

<span data-ttu-id="0a7c0-348">Tipo: cadena</span><span class="sxs-lookup"><span data-stu-id="0a7c0-348">Type: String</span></span>  
<span data-ttu-id="0a7c0-349">Valor predeterminado: **SHA1**</span><span class="sxs-lookup"><span data-stu-id="0a7c0-349">Default value: **SHA1**</span></span>  

    Applicable values are: MD5, SHA1, SHA25, SHA512  

<span data-ttu-id="0a7c0-350">Se aplica a: adaptador de WCF-NetMsmq</span><span class="sxs-lookup"><span data-stu-id="0a7c0-350">Applies to: WCF-NetMsmq adapter</span></span>  

#### <a name="negotiateservicecredential"></a><span data-ttu-id="0a7c0-351">NegotiateServiceCredential</span><span class="sxs-lookup"><span data-stu-id="0a7c0-351">NegotiateServiceCredential</span></span>
<span data-ttu-id="0a7c0-352">Especificar si la credencial de servicio se suministra en este cliente fuera de banda o se obtiene del servicio en el cliente a través de un proceso de negociación.</span><span class="sxs-lookup"><span data-stu-id="0a7c0-352">Specify whether the service credential is provisioned at the client out of band, or is obtained from the service to the client through a process of negotiation.</span></span> <span data-ttu-id="0a7c0-353">Dicha negociación es precursora del intercambio de mensajes habitual.</span><span class="sxs-lookup"><span data-stu-id="0a7c0-353">Such a negotiation is a precursor to the usual message exchange.</span></span>

<span data-ttu-id="0a7c0-354">Si el **MessageClientCredentialType** propiedad es igual a **ninguno**, **nombre de usuario**, o **certificado**, establecer esta propiedad como  **False** implica que el certificado de servicio está disponible en el cliente fuera de banda y que el cliente necesita especificar el certificado de servicio.</span><span class="sxs-lookup"><span data-stu-id="0a7c0-354">If the **MessageClientCredentialType** property equals **None**, **Username**, or **Certificate**, setting this property to **False** implies that the service certificate is available at the client out of band and that the client needs to specify the service certificate.</span></span> <span data-ttu-id="0a7c0-355">Este modo es interoperable con pilas SOAP que implementan WS-Trust y WS-SecureConversation.</span><span class="sxs-lookup"><span data-stu-id="0a7c0-355">This mode is interoperable with SOAP stacks that implement WS-Trust and WS-SecureConversation.</span></span>

<span data-ttu-id="0a7c0-356">Si el **MessageClientCredentialType** propiedad está establecida en **Windows**, establecer esta propiedad en **False** especifica la autenticación basada en Kerberos.</span><span class="sxs-lookup"><span data-stu-id="0a7c0-356">If the **MessageClientCredentialType** property is set to **Windows**, setting this property to **False** specifies Kerberos-based authentication.</span></span> <span data-ttu-id="0a7c0-357">Esto significa que el cliente y el servicio deben formar parte del mismo dominio de Kerberos.</span><span class="sxs-lookup"><span data-stu-id="0a7c0-357">This means that the client and service must be part of the same Kerberos domain.</span></span> <span data-ttu-id="0a7c0-358">Este modo puede interoperar con pilas de SOAP que implementan el perfil de token de Kerberos (como se define en OASIS WSS TC), así como WS-Trust y WS-SecureConversation.</span><span class="sxs-lookup"><span data-stu-id="0a7c0-358">This mode is interoperable with SOAP stacks that implement the Kerberos token profile (as defined at OASIS WSS TC) as well as WS-Trust and WS-SecureConversation.</span></span>

<span data-ttu-id="0a7c0-359">Cuando esta propiedad es **True**, hace que una negociación .NET SOAP que tuneliza el intercambio de SPNego mediante mensajes SOAP.</span><span class="sxs-lookup"><span data-stu-id="0a7c0-359">When this property is **True**, it causes a .NET SOAP negotiation that tunnels SPNego exchange over SOAP messages.</span></span>

<span data-ttu-id="0a7c0-360">Tipo: booleano</span><span class="sxs-lookup"><span data-stu-id="0a7c0-360">Type: Boolean</span></span>  
<span data-ttu-id="0a7c0-361">Valor predeterminado: True</span><span class="sxs-lookup"><span data-stu-id="0a7c0-361">Default value: True</span></span>  
<span data-ttu-id="0a7c0-362">Se aplica a: adaptador de WCF-WSHttp</span><span class="sxs-lookup"><span data-stu-id="0a7c0-362">Applies to: WCF-WSHttp adapter</span></span>  

#### <a name="opentimeout"></a><span data-ttu-id="0a7c0-363">OpenTimeout</span><span class="sxs-lookup"><span data-stu-id="0a7c0-363">OpenTimeout</span></span>
<span data-ttu-id="0a7c0-364">Especificar un valor de marco temporal que indica el intervalo de tiempo proporcionado para que se complete una operación de apertura del canal.</span><span class="sxs-lookup"><span data-stu-id="0a7c0-364">Specify a time span value that indicates the interval of time provided for a channel open operation to complete.</span></span> 

<span data-ttu-id="0a7c0-365">**Nota**</span><span class="sxs-lookup"><span data-stu-id="0a7c0-365">**Note**</span></span>  
<span data-ttu-id="0a7c0-366">No se puede realizar el seguimiento de esta propiedad en la base de datos de importación principal de BAM con los perfiles de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="0a7c0-366">This property cannot be tracked in the BAM Primary Import database with tracking profiles.</span></span> 

<span data-ttu-id="0a7c0-367">Tipo: cadena</span><span class="sxs-lookup"><span data-stu-id="0a7c0-367">Type: String</span></span>  
<span data-ttu-id="0a7c0-368">Valor predeterminado: 00:01:00</span><span class="sxs-lookup"><span data-stu-id="0a7c0-368">Default value: 00:01:00</span></span>  
<span data-ttu-id="0a7c0-369">Se aplica a: todos los adaptadores WCF *excepto* los adaptadores de WCF-Custom y WCF-CustomIsolated</span><span class="sxs-lookup"><span data-stu-id="0a7c0-369">Applies to: All WCF adapters *except* the WCF-Custom and WCF-CustomIsolated adapters</span></span>

#### <a name="orderedprocessing"></a><span data-ttu-id="0a7c0-370">OrderedProcessing</span><span class="sxs-lookup"><span data-stu-id="0a7c0-370">OrderedProcessing</span></span>
<span data-ttu-id="0a7c0-371">Especifica si los mensajes se procesan en serie.</span><span class="sxs-lookup"><span data-stu-id="0a7c0-371">Specify whether to process messages serially.</span></span> <span data-ttu-id="0a7c0-372">Cuando esta propiedad está activada, esta ubicación de recepción permite la entrega de mensajes ordenada cuando se utiliza junto con un puerto de envío de orquestación o mensajería de BizTalk que tiene el **entrega ordenada** opción establecida en `True`.</span><span class="sxs-lookup"><span data-stu-id="0a7c0-372">When this property is selected, this receive location accommodates ordered message delivery when used in conjunction with a BizTalk messaging or orchestration send port that has the **Ordered Delivery** option set to `True`.</span></span> <span data-ttu-id="0a7c0-373">Para obtener más información sobre la **entrega ordenada** opción, vea los temas correspondientes en la sección Vea también.</span><span class="sxs-lookup"><span data-stu-id="0a7c0-373">For more information about the **Ordered Delivery** option, see the appropriate topics in See Also.</span></span>

<span data-ttu-id="0a7c0-374">Esta propiedad es aplicable en los siguientes casos:</span><span class="sxs-lookup"><span data-stu-id="0a7c0-374">This property is applicable in the following cases:</span></span>
- <span data-ttu-id="0a7c0-375">Adaptador de WCF-Custom: cuando el **BindingType** propiedad está establecida en **netMsmqBinding**</span><span class="sxs-lookup"><span data-stu-id="0a7c0-375">WCF-Custom adapter: When the **BindingType** property is set to **netMsmqBinding**</span></span>
- <span data-ttu-id="0a7c0-376">Adaptador de WCF-Custom: cuando el **BindingType** propiedad está establecida en **customBinding**y el **BindingConfiguration** está configurado para usar canales personalizados que se basan en transportes compatibles con la entrega ordenada como MSMQ.</span><span class="sxs-lookup"><span data-stu-id="0a7c0-376">WCF-Custom adapter: When the **BindingType** property is set to **customBinding**, and the **BindingConfiguration** property is configured to use custom channels that rely on transports supporting ordered delivery such as MSMQ.</span></span>
- <span data-ttu-id="0a7c0-377">Adaptador de WCF-CustomIsolated: cuando el **BindingType** propiedad está establecida en **customBinding**y el **BindingConfiguration** está configurado para usar canales personalizados que se basan en transportes compatibles con la entrega ordenada.</span><span class="sxs-lookup"><span data-stu-id="0a7c0-377">WCF-CustomIsolated adapter: When the **BindingType** property is set to **customBinding**, and the **BindingConfiguration** property is configured to use custom channels that rely on transports supporting ordered delivery.</span></span>
- <span data-ttu-id="0a7c0-378">Adaptador de WCF-NetMsmq</span><span class="sxs-lookup"><span data-stu-id="0a7c0-378">WCF-NetMsmq adapter</span></span>

<span data-ttu-id="0a7c0-379">Tipo: cadena</span><span class="sxs-lookup"><span data-stu-id="0a7c0-379">Type: String</span></span>  
<span data-ttu-id="0a7c0-380">Valor predeterminado: **False**</span><span class="sxs-lookup"><span data-stu-id="0a7c0-380">Default value: **False**</span></span>  
<span data-ttu-id="0a7c0-381">Se aplica a:</span><span class="sxs-lookup"><span data-stu-id="0a7c0-381">Applies to:</span></span> 
- <span data-ttu-id="0a7c0-382">Adaptador de recepción de WCF-NetMsmq</span><span class="sxs-lookup"><span data-stu-id="0a7c0-382">WCF-NetMsmq receive adapter</span></span>
- <span data-ttu-id="0a7c0-383">Adaptador de recepción de WCF-Custom</span><span class="sxs-lookup"><span data-stu-id="0a7c0-383">WCF-Custom receive adapter</span></span>
- <span data-ttu-id="0a7c0-384">Adaptador de recepción WCF-CustomIsolated</span><span class="sxs-lookup"><span data-stu-id="0a7c0-384">WCF-CustomIsolated receive adapter</span></span>

#### <a name="outboundbodylocation"></a><span data-ttu-id="0a7c0-385">OutboundBodyLocation</span><span class="sxs-lookup"><span data-stu-id="0a7c0-385">OutboundBodyLocation</span></span>
<span data-ttu-id="0a7c0-386">Especifique la selección de datos para el mensaje SOAP **cuerpo** elemento de mensajes WCF salientes.</span><span class="sxs-lookup"><span data-stu-id="0a7c0-386">Specify the data selection for the SOAP **Body** element of outgoing WCF messages.</span></span> <span data-ttu-id="0a7c0-387">Para obtener más información sobre cómo usar el **OutboundBodyLocation** propiedad, vea [especificar el cuerpo del mensaje para los adaptadores de WCF](../core/specifying-the-message-body-for-the-wcf-adapters.md).</span><span class="sxs-lookup"><span data-stu-id="0a7c0-387">For more information about how to use the **OutboundBodyLocation** property, see [Specifying the Message Body for the WCF Adapters](../core/specifying-the-message-body-for-the-wcf-adapters.md).</span></span>

<span data-ttu-id="0a7c0-388">Tipo: cadena</span><span class="sxs-lookup"><span data-stu-id="0a7c0-388">Type: String</span></span>  
<span data-ttu-id="0a7c0-389">Valor predeterminado: UseBodyElement</span><span class="sxs-lookup"><span data-stu-id="0a7c0-389">Default value: UseBodyElement</span></span>  

    Applicable values are:
        - UseBodyElement: Use the BizTalk message body part to create the content of the SOAP **Body** element for an outgoing message
        - **UseTem****plate**: Use the template supplied in the OutboundXMLTemplate property to create the content of the SOAP **Body** element for an outgoing message

<span data-ttu-id="0a7c0-390">Se aplica a: todos los adaptadores WCF *excepto* adaptador de recepción de WCF-NetMsmq</span><span class="sxs-lookup"><span data-stu-id="0a7c0-390">Applies to: All WCF adapters *except* the WCF-NetMsmq receive adapter</span></span>

#### <a name="outboundcustomheaders"></a><span data-ttu-id="0a7c0-391">OutboundCustomHeaders</span><span class="sxs-lookup"><span data-stu-id="0a7c0-391">OutboundCustomHeaders</span></span>
<span data-ttu-id="0a7c0-392">Especificar encabezados SOAP personalizados para mensajes salientes.</span><span class="sxs-lookup"><span data-stu-id="0a7c0-392">Specify the custom SOAP headers for outgoing messages.</span></span> <span data-ttu-id="0a7c0-393">Cuando se utiliza esta propiedad, la propiedad debe tener la \< **encabezados** \> elemento como el elemento raíz.</span><span class="sxs-lookup"><span data-stu-id="0a7c0-393">When this property is used, the property must have the \<**headers**\> element as the root element.</span></span> <span data-ttu-id="0a7c0-394">Todos los encabezados SOAP personalizados deben colocarse dentro de la \< **encabezados** \> elemento.</span><span class="sxs-lookup"><span data-stu-id="0a7c0-394">All of the custom SOAP headers must be placed inside the \<**headers**\> element.</span></span> <span data-ttu-id="0a7c0-395">Si el valor del encabezado SOAP personalizado es una cadena vacía, debe asignar \< **encabezados**\>\</**encabezados** \> o \< **encabezados** \> a esta propiedad.</span><span class="sxs-lookup"><span data-stu-id="0a7c0-395">If the custom SOAP header value is an empty string, you must assign \<**headers**\>\</**headers**\> or \<**headers**\> to this property.</span></span> <span data-ttu-id="0a7c0-396">Para obtener más información acerca de cómo usar encabezados SOAP con los adaptadores WCF, vea el ejemplo de SDK Using Custom SOAP Headers with the WCF Adapters de [http://go.microsoft.com/fwlink/?LinkId=79960](http://go.microsoft.com/fwlink/?LinkId=79960).</span><span class="sxs-lookup"><span data-stu-id="0a7c0-396">For more information about how to use SOAP headers with the WCF adapters, see the SDK sample, Using Custom SOAP Headers with the WCF Adapters, from [http://go.microsoft.com/fwlink/?LinkId=79960](http://go.microsoft.com/fwlink/?LinkId=79960).</span></span>

<span data-ttu-id="0a7c0-397">Tipo: cadena</span><span class="sxs-lookup"><span data-stu-id="0a7c0-397">Type: String</span></span>  
<span data-ttu-id="0a7c0-398">Se aplica a: todos los adaptadores WCF *excepto* adaptador de recepción de WCF-NetMsmq</span><span class="sxs-lookup"><span data-stu-id="0a7c0-398">Applies to: All WCF adapters *except* the WCF-NetMsmq receive adapter</span></span>

#### <a name="outboundxmltemplate"></a><span data-ttu-id="0a7c0-399">OutboundXmlTemplate</span><span class="sxs-lookup"><span data-stu-id="0a7c0-399">OutboundXmlTemplate</span></span>
<span data-ttu-id="0a7c0-400">Especifique la plantilla con formato XML para el contenido del mensaje SOAP **cuerpo** elemento de un mensaje saliente.</span><span class="sxs-lookup"><span data-stu-id="0a7c0-400">Specify the XML-formatted template for the content of the SOAP **Body** element of an outgoing message.</span></span> <span data-ttu-id="0a7c0-401">Esta propiedad es necesaria si la **OutboundBodyLocation** propiedad está establecida en **UseTemplate**.</span><span class="sxs-lookup"><span data-stu-id="0a7c0-401">This property is required if the **OutboundBodyLocation** property is set to **UseTemplate**.</span></span> <span data-ttu-id="0a7c0-402">Para obtener más información sobre cómo usar el **OutboundXMLTemplate** propiedad, vea [especificar el cuerpo del mensaje para los adaptadores de WCF](../core/specifying-the-message-body-for-the-wcf-adapters.md).</span><span class="sxs-lookup"><span data-stu-id="0a7c0-402">For more information about how to use the **OutboundXMLTemplate** property, see [Specifying the Message Body for the WCF Adapters](../core/specifying-the-message-body-for-the-wcf-adapters.md).</span></span>

<span data-ttu-id="0a7c0-403">Tipo: cadena</span><span class="sxs-lookup"><span data-stu-id="0a7c0-403">Type: String</span></span>  
<span data-ttu-id="0a7c0-404">Valor predeterminado: una cadena vacía</span><span class="sxs-lookup"><span data-stu-id="0a7c0-404">Default value: An empty string</span></span>  
<span data-ttu-id="0a7c0-405">Se aplica a: todos los adaptadores WCF *excepto* adaptador de recepción de WCF-NetMsmq</span><span class="sxs-lookup"><span data-stu-id="0a7c0-405">Applies to: All WCF adapters *except* the WCF-NetMsmq receive adapter</span></span>

#### <a name="password"></a><span data-ttu-id="0a7c0-406">Contraseña</span><span class="sxs-lookup"><span data-stu-id="0a7c0-406">Password</span></span>
<span data-ttu-id="0a7c0-407">Especifique la contraseña que se utilizará para la autenticación con el servidor de destino cuando la **UseSSO** propiedad está establecida en **False**.</span><span class="sxs-lookup"><span data-stu-id="0a7c0-407">Specify the password to use for authentication with the destination server when the **UseSSO** property is set to **False**.</span></span>

<span data-ttu-id="0a7c0-408">Tipo: cadena</span><span class="sxs-lookup"><span data-stu-id="0a7c0-408">Type: String</span></span>  
<span data-ttu-id="0a7c0-409">Valor predeterminado: una cadena vacía</span><span class="sxs-lookup"><span data-stu-id="0a7c0-409">Default value: An empty string</span></span>  
<span data-ttu-id="0a7c0-410">Se aplica a: WCF todos los adaptadores de envío *excepto* el adaptador WCF-NetNamedPipe</span><span class="sxs-lookup"><span data-stu-id="0a7c0-410">Applies to: All WCF send adapters *except* the WCF-NetNamedPipe adapter</span></span>  

#### <a name="propagatefaultmessage"></a><span data-ttu-id="0a7c0-411">PropagateFaultMessage</span><span class="sxs-lookup"><span data-stu-id="0a7c0-411">PropagateFaultMessage</span></span>
<span data-ttu-id="0a7c0-412">Especificar si se enrutan o se suspenden mensajes que generan errores en el procesamiento de salida.</span><span class="sxs-lookup"><span data-stu-id="0a7c0-412">Specify whether to route or suspend messages that fail in outbound processing.</span></span> <span data-ttu-id="0a7c0-413">Esta propiedad sólo es válida para puertos de petición-respuesta.</span><span class="sxs-lookup"><span data-stu-id="0a7c0-413">This property is valid only for solicit-response ports.</span></span> 

<span data-ttu-id="0a7c0-414">**Nota**</span><span class="sxs-lookup"><span data-stu-id="0a7c0-414">**Note**</span></span>  
<span data-ttu-id="0a7c0-415">No se puede realizar el seguimiento de esta propiedad en la base de datos de importación principal de BAM con los perfiles de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="0a7c0-415">This property cannot be tracked in the BAM Primary Import database with tracking profiles.</span></span>

<span data-ttu-id="0a7c0-416">Tipo: booleano</span><span class="sxs-lookup"><span data-stu-id="0a7c0-416">Type: Boolean</span></span>  
<span data-ttu-id="0a7c0-417">Valor predeterminado: **True**</span><span class="sxs-lookup"><span data-stu-id="0a7c0-417">Default value: **True**</span></span>  

    Applicable values are:  
        - True: Route the message that fails outbound processing to a subscribing application (such as another receive port or orchestration schedule)
        - False: Suspend failed messages and generate a negative acknowledgment (NACK)

<span data-ttu-id="0a7c0-418">Se aplica a: WCF todos los adaptadores de envío *excepto* el adaptador WCF-NetMsmq</span><span class="sxs-lookup"><span data-stu-id="0a7c0-418">Applies to: All WCF send adapters *except* the WCF-NetMsmq adapter</span></span>
  
#### <a name="proxyaddress"></a><span data-ttu-id="0a7c0-419">ProxyAddress</span><span class="sxs-lookup"><span data-stu-id="0a7c0-419">ProxyAddress</span></span>
<span data-ttu-id="0a7c0-420">Especificar la dirección del servidor proxy.</span><span class="sxs-lookup"><span data-stu-id="0a7c0-420">Specify the address of the proxy server.</span></span> <span data-ttu-id="0a7c0-421">Use la **https** o **http** esquema según la configuración de seguridad.</span><span class="sxs-lookup"><span data-stu-id="0a7c0-421">Use the **https** or the **http** scheme depending on the security configuration.</span></span> <span data-ttu-id="0a7c0-422">Esta dirección puede ir seguida de dos puntos y el número de puerto.</span><span class="sxs-lookup"><span data-stu-id="0a7c0-422">This address can be followed by a colon and the port number.</span></span> <span data-ttu-id="0a7c0-423">La propiedad es obligatoria si la **ProxyToUse** propiedad está establecida en **UserSpecified** (por ejemplo, http://127.0.0.1: 8080)</span><span class="sxs-lookup"><span data-stu-id="0a7c0-423">The property is required if the **ProxyToUse** property is set to **UserSpecified** (For example, http://127.0.0.1:8080)</span></span>

<span data-ttu-id="0a7c0-424">Tipo: cadena</span><span class="sxs-lookup"><span data-stu-id="0a7c0-424">Type: String</span></span>  
<span data-ttu-id="0a7c0-425">Valor predeterminado: una cadena vacía</span><span class="sxs-lookup"><span data-stu-id="0a7c0-425">Default value: An empty string</span></span>  
<span data-ttu-id="0a7c0-426">Se aplica a: adaptador de envío WCF-BasicHttp, adaptador de envío WCF-WSHttp</span><span class="sxs-lookup"><span data-stu-id="0a7c0-426">Applies to: WCF-BasicHttp send adapter, WCF-WSHttp send adapter</span></span>  

#### <a name="proxypassword"></a><span data-ttu-id="0a7c0-427">ProxyPassword</span><span class="sxs-lookup"><span data-stu-id="0a7c0-427">ProxyPassword</span></span>
<span data-ttu-id="0a7c0-428">Especifique la contraseña que se utilizará para el servidor proxy especificado en el **ProxyAddress** propiedad.</span><span class="sxs-lookup"><span data-stu-id="0a7c0-428">Specify the password to use for the proxy server specified in the **ProxyAddress** property.</span></span>

<span data-ttu-id="0a7c0-429">Tipo: cadena</span><span class="sxs-lookup"><span data-stu-id="0a7c0-429">Type: String</span></span>  
<span data-ttu-id="0a7c0-430">Valor predeterminado: una cadena vacía</span><span class="sxs-lookup"><span data-stu-id="0a7c0-430">Default value: An empty string</span></span>  
<span data-ttu-id="0a7c0-431">Se aplica a: adaptador de envío WCF-BasicHttp, adaptador de envío WCF-WSHttp</span><span class="sxs-lookup"><span data-stu-id="0a7c0-431">Applies to: WCF-BasicHttp send adapter, WCF-WSHttp send adapter</span></span>

#### <a name="proxytouse"></a><span data-ttu-id="0a7c0-432">ProxyToUse</span><span class="sxs-lookup"><span data-stu-id="0a7c0-432">ProxyToUse</span></span>
<span data-ttu-id="0a7c0-433">Especificar el servidor de proxy que se va a utilizar para el tráfico HTTP saliente.</span><span class="sxs-lookup"><span data-stu-id="0a7c0-433">Specify which proxy server to use for outgoing HTTP traffic.</span></span>

<span data-ttu-id="0a7c0-434">Tipo: cadena</span><span class="sxs-lookup"><span data-stu-id="0a7c0-434">Type: String</span></span>  
<span data-ttu-id="0a7c0-435">Valor predeterminado: **ninguno**</span><span class="sxs-lookup"><span data-stu-id="0a7c0-435">Default value: **None**</span></span>  

    Applicable values are:  
        - None: Do not use a proxy server for this send port
        - Default: Use the proxy settings in the send handler hosting this send port
        - UserSpecified: Use the proxy server specified in the **ProxyAddress** property

<span data-ttu-id="0a7c0-436">Se aplica a: adaptador de envío WCF-BasicHttp, adaptador de envío WCF-WSHttp</span><span class="sxs-lookup"><span data-stu-id="0a7c0-436">Applies to: WCF-BasicHttp send adapter, WCF-WSHttp send adapter</span></span>  

#### <a name="proxyusername"></a><span data-ttu-id="0a7c0-437">ProxyUsername</span><span class="sxs-lookup"><span data-stu-id="0a7c0-437">ProxyUserName</span></span>
<span data-ttu-id="0a7c0-438">Especifique el nombre de usuario que se utilizará para el servidor proxy especificado en el **ProxyAddress** propiedad.</span><span class="sxs-lookup"><span data-stu-id="0a7c0-438">Specify the user name to use for the proxy server specified in the **ProxyAddress** property.</span></span> <span data-ttu-id="0a7c0-439">La propiedad es obligatoria si la **ProxyToUse** propiedad está establecida en **UserSpecified**.</span><span class="sxs-lookup"><span data-stu-id="0a7c0-439">The property is required if the **ProxyToUse** property is set to **UserSpecified**.</span></span>

<span data-ttu-id="0a7c0-440">Para obtener más información acerca de esta propiedad, vea [cómo configurar un puerto de envío WCF-WSHttp](../core/how-to-configure-a-wcf-wshttp-send-port.md) y [cómo configurar un puerto de envío WCF-BasicHttp](http://msdn.microsoft.com/library/acdb50fa-57fe-4657-9561-b6b2f4919c7f).</span><span class="sxs-lookup"><span data-stu-id="0a7c0-440">For more information about this property, see [How to Configure a WCF-WSHttp Send Port](../core/how-to-configure-a-wcf-wshttp-send-port.md) and [How to Configure a WCF-BasicHttp Send Port](http://msdn.microsoft.com/library/acdb50fa-57fe-4657-9561-b6b2f4919c7f).</span></span>

<span data-ttu-id="0a7c0-441">Tipo: cadena</span><span class="sxs-lookup"><span data-stu-id="0a7c0-441">Type: String</span></span>  
<span data-ttu-id="0a7c0-442">Se aplica a: adaptador de envío WCF-BasicHttp, adaptador de envío WCF-WSHttp</span><span class="sxs-lookup"><span data-stu-id="0a7c0-442">Applies to: WCF-BasicHttp send adapter, WCF-WSHttp send adapter</span></span>

#### <a name="replytoaddress"></a><span data-ttu-id="0a7c0-443">ReplyToAddress</span><span class="sxs-lookup"><span data-stu-id="0a7c0-443">ReplyToAddress</span></span>
<span data-ttu-id="0a7c0-444">Indicar la dirección de extremo de respuesta para los mensajes WCF salientes que corresponden a los mensajes entrantes recibidos a través de las ubicaciones de recepción de solicitud-respuesta.</span><span class="sxs-lookup"><span data-stu-id="0a7c0-444">Indicate the reply endpoint address for the outgoing WCF messages corresponding to incoming messages received through the request-response receive locations.</span></span> <span data-ttu-id="0a7c0-445">La propiedad se promociona automáticamente desde los mensajes entrantes.</span><span class="sxs-lookup"><span data-stu-id="0a7c0-445">The property is automatically promoted from incoming messages.</span></span>

<span data-ttu-id="0a7c0-446">Tipo: cadena</span><span class="sxs-lookup"><span data-stu-id="0a7c0-446">Type: String</span></span>  
<span data-ttu-id="0a7c0-447">Valor predeterminado: una cadena vacía</span><span class="sxs-lookup"><span data-stu-id="0a7c0-447">Default value: An empty string</span></span>  
<span data-ttu-id="0a7c0-448">Se aplica a: todos los adaptadores WCF *excepto* el adaptador WCF-NetMsmq</span><span class="sxs-lookup"><span data-stu-id="0a7c0-448">Applies to: All WCF adapters *except* the WCF-NetMsmq adapter</span></span>

#### <a name="securitymode"></a><span data-ttu-id="0a7c0-449">SecurityMode</span><span class="sxs-lookup"><span data-stu-id="0a7c0-449">SecurityMode</span></span>
<span data-ttu-id="0a7c0-450">Especificar el tipo de seguridad que se usa.</span><span class="sxs-lookup"><span data-stu-id="0a7c0-450">Specify the type of security that is used.</span></span> <span data-ttu-id="0a7c0-451">Los valores aplicables son distintos para cada adaptador de WCF.</span><span class="sxs-lookup"><span data-stu-id="0a7c0-451">The applicable values differ for each WCF adapter.</span></span> <span data-ttu-id="0a7c0-452">Para obtener más información sobre la **SecurityMode** propiedad, vea los temas sobre cada adaptador de WCF en [adaptadores de WCF](../core/wcf-adapters.md).</span><span class="sxs-lookup"><span data-stu-id="0a7c0-452">For more information about the **SecurityMode** property, see how-to topics for each WCF adapter in [WCF Adapters](../core/wcf-adapters.md).</span></span> 

<span data-ttu-id="0a7c0-453">**Nota**</span><span class="sxs-lookup"><span data-stu-id="0a7c0-453">**Note**</span></span>  
<span data-ttu-id="0a7c0-454">No se puede realizar el seguimiento de esta propiedad en la base de datos de importación principal de BAM con los perfiles de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="0a7c0-454">This property cannot be tracked in the BAM Primary Import database with tracking profiles.</span></span>

<span data-ttu-id="0a7c0-455">Tipo: cadena</span><span class="sxs-lookup"><span data-stu-id="0a7c0-455">Type: String</span></span>  
<span data-ttu-id="0a7c0-456">Se aplica a: todos los adaptadores WCF *excepto* los adaptadores de WCF-Custom y WCF-CustomIsolated</span><span class="sxs-lookup"><span data-stu-id="0a7c0-456">Applies to: All WCF adapters *except* the WCF-Custom and WCF-CustomIsolated adapters</span></span>

#### <a name="sendtimeout"></a><span data-ttu-id="0a7c0-457">SendTimeout</span><span class="sxs-lookup"><span data-stu-id="0a7c0-457">SendTimeout</span></span>
<span data-ttu-id="0a7c0-458">Especificar un valor de marco temporal que indica el intervalo de tiempo proporcionado para que se complete una operación de envío.</span><span class="sxs-lookup"><span data-stu-id="0a7c0-458">Specify a time span value that indicates the interval of time provided for a send operation to complete.</span></span> <span data-ttu-id="0a7c0-459">Este valor especifica un marco temporal para que se complete toda la interacción, incluso si el remitente envía un mensaje de gran tamaño.</span><span class="sxs-lookup"><span data-stu-id="0a7c0-459">This value specifies a time span for the whole interaction to complete, even if the correspondent sends a large message.</span></span>

<span data-ttu-id="0a7c0-460">Tipo: cadena</span><span class="sxs-lookup"><span data-stu-id="0a7c0-460">Type: String</span></span>  
<span data-ttu-id="0a7c0-461">Valor predeterminado: 00:01:00</span><span class="sxs-lookup"><span data-stu-id="0a7c0-461">Default value: 00:01:00</span></span>  
<span data-ttu-id="0a7c0-462">Se aplica a: todos los adaptadores WCF *excepto* los adaptadores de WCF-Custom y WCF-CustomIsolated</span><span class="sxs-lookup"><span data-stu-id="0a7c0-462">Applies to: All WCF adapters *except* the WCF-Custom and WCF-CustomIsolated adapters</span></span>

#### <a name="servicebehaviorconfiguration"></a><span data-ttu-id="0a7c0-463">ServiceBehaviorConfiguration</span><span class="sxs-lookup"><span data-stu-id="0a7c0-463">ServiceBehaviorConfiguration</span></span>
<span data-ttu-id="0a7c0-464">Especificar una cadena XML con el  **\<comportamiento\>**  elemento de la  **\<serviceBehaviors\>**  elemento que se va a configurar las opciones de comportamiento de WCF servicio.</span><span class="sxs-lookup"><span data-stu-id="0a7c0-464">Specify an XML string with the **\<behavior\>** element of the **\<serviceBehaviors\>** element to configure the behavior settings of a WCF service.</span></span> <span data-ttu-id="0a7c0-465">Para obtener más información sobre la  **\<serviceBehaviors\>**  elemento, vea el tema correspondiente en la sección Vea también.</span><span class="sxs-lookup"><span data-stu-id="0a7c0-465">For more information about the **\<serviceBehaviors\>** element, see the appropriate topic in See Also.</span></span>

<span data-ttu-id="0a7c0-466">Ejemplo:</span><span class="sxs-lookup"><span data-stu-id="0a7c0-466">Example:</span></span>

```
<behavior name="SampleServiceBehavior">
<serviceAuthorization principalPermissionMode="UseAspNetRoles"/>
<serviceCredentials>
<serviceCertificate findValue="539d9ab3089bb6dc187fa7dbb382cf01f8d78f5f" storeLocation="CurrentUser" x509FindType="FindByThumbprint"/>
</serviceCredentials>
<serviceMetadata httpGetEnabled="true"/>
</behavior>
```

<span data-ttu-id="0a7c0-467">Tipo: cadena</span><span class="sxs-lookup"><span data-stu-id="0a7c0-467">Type: String</span></span>  
<span data-ttu-id="0a7c0-468">Valor predeterminado: una cadena vacía</span><span class="sxs-lookup"><span data-stu-id="0a7c0-468">Default value: An empty string</span></span>  
<span data-ttu-id="0a7c0-469">Se aplica a: adaptador, adaptador de WCF-CustomIsolated de recepción WCF-Custom</span><span class="sxs-lookup"><span data-stu-id="0a7c0-469">Applies to: WCF-Custom receive adapter, WCF-CustomIsolated adapter</span></span>

#### <a name="servicecertificate"></a><span data-ttu-id="0a7c0-470">ServiceCertificate</span><span class="sxs-lookup"><span data-stu-id="0a7c0-470">ServiceCertificate</span></span>
<span data-ttu-id="0a7c0-471">Si esta propiedad se usa para ubicaciones de recepción, especifique la huella digital del certificado X.509 para las ubicaciones de recepción que los clientes utilizan para autenticar el servicio.</span><span class="sxs-lookup"><span data-stu-id="0a7c0-471">If this property is used for receive locations, specify the thumbprint of the X.509 certificate for the receive locations that clients use to authenticate the service.</span></span> <span data-ttu-id="0a7c0-472">El certificado que se usará para esta propiedad debe estar instalado en el **mi** almacenar en la **usuario actual** ubicación.</span><span class="sxs-lookup"><span data-stu-id="0a7c0-472">The certificate to be used for this property must be installed into the **My** store in the **Current User** location.</span></span>

<span data-ttu-id="0a7c0-473">Si esta propiedad se usar para puertos de envío, especifique la huella digital del certificado X.509 para autenticar el servicio al que este puerto de envío envía los mensajes.</span><span class="sxs-lookup"><span data-stu-id="0a7c0-473">If this property is used for send ports, specify the thumbprint of the X.509 certificate for authenticating the service to which this send port sends messages.</span></span> <span data-ttu-id="0a7c0-474">El certificado que se usará para esta propiedad debe estar instalado en el **otras personas** almacenar en la **equipo Local** ubicación.</span><span class="sxs-lookup"><span data-stu-id="0a7c0-474">The certificate to be used for this property must be installed into the **Other People** store in the **Local Machine** location.</span></span>

<span data-ttu-id="0a7c0-475">Tipo: cadena</span><span class="sxs-lookup"><span data-stu-id="0a7c0-475">Type: String</span></span>  
<span data-ttu-id="0a7c0-476">Valor predeterminado: una cadena vacía</span><span class="sxs-lookup"><span data-stu-id="0a7c0-476">Default value: An empty string</span></span>  
<span data-ttu-id="0a7c0-477">Se aplica a:</span><span class="sxs-lookup"><span data-stu-id="0a7c0-477">Applies to:</span></span> 
- <span data-ttu-id="0a7c0-478">Adaptador de WCF-BasicHttp</span><span class="sxs-lookup"><span data-stu-id="0a7c0-478">WCF-BasicHttp adapter</span></span>
- <span data-ttu-id="0a7c0-479">Adaptador de WCF-NetMsmq</span><span class="sxs-lookup"><span data-stu-id="0a7c0-479">WCF-NetMsmq adapter</span></span>
- <span data-ttu-id="0a7c0-480">Adaptador de WCF-WSHttp</span><span class="sxs-lookup"><span data-stu-id="0a7c0-480">WCF-WSHttp adapter</span></span>
- <span data-ttu-id="0a7c0-481">Adaptador de recepción WCF-NetTcp</span><span class="sxs-lookup"><span data-stu-id="0a7c0-481">WCF-NetTcp receive adapter</span></span>

#### <a name="suspendmessageonfailure"></a><span data-ttu-id="0a7c0-482">SuspendMessageOnFailure</span><span class="sxs-lookup"><span data-stu-id="0a7c0-482">SuspendMessageOnFailure</span></span>
<span data-ttu-id="0a7c0-483">Especificar si se va a suspender el mensaje de solicitud cuyo procesamiento de entrada no se puede realizar correctamente debido a un error de canalización de recepción o de enrutamiento.</span><span class="sxs-lookup"><span data-stu-id="0a7c0-483">Specify whether to suspend the request message that fails inbound processing due to a receive pipeline failure or a routing failure.</span></span>

<span data-ttu-id="0a7c0-484">Tipo: booleano</span><span class="sxs-lookup"><span data-stu-id="0a7c0-484">Type: Boolean</span></span>  
<span data-ttu-id="0a7c0-485">Valor predeterminado: True</span><span class="sxs-lookup"><span data-stu-id="0a7c0-485">Default value: True</span></span>  
<span data-ttu-id="0a7c0-486">Se aplica a: WCF todos los adaptadores de recepción</span><span class="sxs-lookup"><span data-stu-id="0a7c0-486">Applies to: All WCF receive adapters</span></span>  

#### <a name="textencoding"></a><span data-ttu-id="0a7c0-487">TextEncoding</span><span class="sxs-lookup"><span data-stu-id="0a7c0-487">TextEncoding</span></span>
<span data-ttu-id="0a7c0-488">Especifique la codificación que se usará para emitir los mensajes en el enlace del juego de caracteres cuando la **MessageEncoding** propiedad está establecida en **texto**.</span><span class="sxs-lookup"><span data-stu-id="0a7c0-488">Specify the character set encoding to be used for emitting messages on the binding when the **MessageEncoding** property is set to **Text**.</span></span> 

<span data-ttu-id="0a7c0-489">**Nota**</span><span class="sxs-lookup"><span data-stu-id="0a7c0-489">**Note**</span></span>  
<span data-ttu-id="0a7c0-490">No se puede realizar el seguimiento de esta propiedad en la base de datos de importación principal de BAM con los perfiles de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="0a7c0-490">This property cannot be tracked in the BAM Primary Import database with tracking profiles.</span></span> 

<span data-ttu-id="0a7c0-491">Tipo: cadena</span><span class="sxs-lookup"><span data-stu-id="0a7c0-491">Type: String</span></span>  
<span data-ttu-id="0a7c0-492">Valor predeterminado: utf-8</span><span class="sxs-lookup"><span data-stu-id="0a7c0-492">Default value: utf-8</span></span>  

    Applicable values are:  
        - unicodeFFF: Unicode BigEndian encoding
        - utf-16: 16-bit encoding
        - utf-8: 8-bit encoding

<span data-ttu-id="0a7c0-493">Se aplica a: adaptador de WCF-BasicHttp, adaptador de WCF-WSHttp</span><span class="sxs-lookup"><span data-stu-id="0a7c0-493">Applies to: WCF-BasicHttp adapter, WCF-WSHttp adapter</span></span>
  
#### <a name="timetolive"></a><span data-ttu-id="0a7c0-494">TimeToLive</span><span class="sxs-lookup"><span data-stu-id="0a7c0-494">TimeToLive</span></span>
<span data-ttu-id="0a7c0-495">Especificar el período de validez de los mensajes antes de que caduquen y se coloquen en la cola de mensajes con problemas de entrega.</span><span class="sxs-lookup"><span data-stu-id="0a7c0-495">Specify a time span for how long the messages are valid before they are expired and put into the dead-letter queue.</span></span> <span data-ttu-id="0a7c0-496">Esta propiedad se define para garantizar que los mensajes con limitaciones temporales no se conviertan en obsoletos antes de que un puerto de envío los procese.</span><span class="sxs-lookup"><span data-stu-id="0a7c0-496">This property is set to ensure that time-sensitive messages do not become stale before they are processed by a send port.</span></span> <span data-ttu-id="0a7c0-497">Se dice que los mensajes que se encuentren en una cola y no hayan sido consumidos por este puerto de envío en el intervalo especificado caducarán.</span><span class="sxs-lookup"><span data-stu-id="0a7c0-497">A message in a queue that is not consumed by this send port within the time interval specified is said to be expired.</span></span> <span data-ttu-id="0a7c0-498">Los mensajes caducados se envían a una cola especial denominada cola de mensajes con problemas de entrega.</span><span class="sxs-lookup"><span data-stu-id="0a7c0-498">Expired messages are sent to special queue called the dead-letter queue.</span></span> <span data-ttu-id="0a7c0-499">La ubicación de la cola de mensajes no enviados se establece con el **DeadLetterQueue** propiedad.</span><span class="sxs-lookup"><span data-stu-id="0a7c0-499">The location of the dead-letter queue is set with the **DeadLetterQueue** property.</span></span>

<span data-ttu-id="0a7c0-500">Tipo: cadena</span><span class="sxs-lookup"><span data-stu-id="0a7c0-500">Type: String</span></span>  
<span data-ttu-id="0a7c0-501">Valor predeterminado: 1.00:00:00</span><span class="sxs-lookup"><span data-stu-id="0a7c0-501">Default value: 1.00:00:00</span></span>  
<span data-ttu-id="0a7c0-502">Se aplica a: adaptador de envío WCF-NetMsmq</span><span class="sxs-lookup"><span data-stu-id="0a7c0-502">Applies to: WCF-NetMsmq send adapter</span></span>

#### <a name="to"></a><span data-ttu-id="0a7c0-503">A</span><span class="sxs-lookup"><span data-stu-id="0a7c0-503">To</span></span>
<span data-ttu-id="0a7c0-504">Especificar la dirección de extremo de destino para mensajes WCF salientes que envían los puertos de envío WCF.</span><span class="sxs-lookup"><span data-stu-id="0a7c0-504">Specify the destination endpoint address for outgoing WCF messages that the WCF send ports send.</span></span>

<span data-ttu-id="0a7c0-505">Tipo: cadena</span><span class="sxs-lookup"><span data-stu-id="0a7c0-505">Type: String</span></span>  
<span data-ttu-id="0a7c0-506">Valor predeterminado: una cadena vacía</span><span class="sxs-lookup"><span data-stu-id="0a7c0-506">Default value: An empty string</span></span>  
<span data-ttu-id="0a7c0-507">Se aplica a: WCF todos los adaptadores de envío</span><span class="sxs-lookup"><span data-stu-id="0a7c0-507">Applies to: All WCF send adapters</span></span>  

#### <a name="transactionprotocol"></a><span data-ttu-id="0a7c0-508">TransactionProtocol</span><span class="sxs-lookup"><span data-stu-id="0a7c0-508">TransactionProtocol</span></span>
<span data-ttu-id="0a7c0-509">Especificar el protocolo de transacción que se usará con este enlace.</span><span class="sxs-lookup"><span data-stu-id="0a7c0-509">Specify the transaction protocol to be used with this binding.</span></span> <span data-ttu-id="0a7c0-510">Esta propiedad es necesaria si la **EnableTransaction** propiedad está establecida en **True**.</span><span class="sxs-lookup"><span data-stu-id="0a7c0-510">This property is required if the **EnableTransaction** property is set to **True**.</span></span>

<span data-ttu-id="0a7c0-511">Tipo: cadena</span><span class="sxs-lookup"><span data-stu-id="0a7c0-511">Type: String</span></span>  
<span data-ttu-id="0a7c0-512">Valor predeterminado: OleTransaction</span><span class="sxs-lookup"><span data-stu-id="0a7c0-512">Default value: OleTransaction</span></span>  

    Applicable values are: OleTransaction, WS-AtomicTransaction

<span data-ttu-id="0a7c0-513">Se aplica a: adaptador de WCF-NetNamedPipe, adaptador de WCF-NetTcp</span><span class="sxs-lookup"><span data-stu-id="0a7c0-513">Applies to: WCF-NetNamedPipe adapter,  WCF-NetTcp adapter</span></span>  

#### <a name="transportclientcredentialtype"></a><span data-ttu-id="0a7c0-514">TransportClientCredentialType</span><span class="sxs-lookup"><span data-stu-id="0a7c0-514">TransportClientCredentialType</span></span>
<span data-ttu-id="0a7c0-515">Especificar el tipo de credenciales que se va a usar a la hora de realizar la autenticación del puerto de envío.</span><span class="sxs-lookup"><span data-stu-id="0a7c0-515">Specify the type of credential to be used when performing the send port authentication.</span></span> <span data-ttu-id="0a7c0-516">Los valores aplicables son distintos para cada adaptador de WCF.</span><span class="sxs-lookup"><span data-stu-id="0a7c0-516">The applicable values differ for each WCF adapter.</span></span> <span data-ttu-id="0a7c0-517">Para obtener más información sobre la **TransportClientCredentialType** propiedad, vea los temas sobre cada adaptador de WCF en [adaptadores de WCF](../core/wcf-adapters.md).</span><span class="sxs-lookup"><span data-stu-id="0a7c0-517">For more information about the **TransportClientCredentialType** property, see how-to topics for each WCF adapter in [WCF Adapters](../core/wcf-adapters.md).</span></span>

<span data-ttu-id="0a7c0-518">Tipo: cadena</span><span class="sxs-lookup"><span data-stu-id="0a7c0-518">Type: String</span></span>  
<span data-ttu-id="0a7c0-519">Se aplica a: adaptador de WCF-Basic, el adaptador WCF-NetTcp, el adaptador WCF-WSHttp</span><span class="sxs-lookup"><span data-stu-id="0a7c0-519">Applies to: WCF-Basic adapter, WCF-NetTcp adapter, WCF-WSHttp adapter</span></span>  

#### <a name="transportprotectionlevel"></a><span data-ttu-id="0a7c0-520">TransportProtectionLevel</span><span class="sxs-lookup"><span data-stu-id="0a7c0-520">TransportProtectionLevel</span></span>
<span data-ttu-id="0a7c0-521">Especificar la seguridad en el nivel de transporte TCP.</span><span class="sxs-lookup"><span data-stu-id="0a7c0-521">Specify security at the level of the TCP transport.</span></span> <span data-ttu-id="0a7c0-522">Si se firman los mensajes, se reduce el riesgo de que manipulen el mensaje terceros mientras éste se transfiere.</span><span class="sxs-lookup"><span data-stu-id="0a7c0-522">Signing messages mitigates the risk of a third party tampering with the message while it is being transferred.</span></span> <span data-ttu-id="0a7c0-523">El cifrado proporciona privacidad de nivel de datos durante el transporte.</span><span class="sxs-lookup"><span data-stu-id="0a7c0-523">Encryption provides data-level privacy during transport.</span></span>

<span data-ttu-id="0a7c0-524">Tipo: cadena</span><span class="sxs-lookup"><span data-stu-id="0a7c0-524">Type: String</span></span>  
<span data-ttu-id="0a7c0-525">Valor predeterminado: **EncryptAndSign**</span><span class="sxs-lookup"><span data-stu-id="0a7c0-525">Default value: **EncryptAndSign**</span></span>  

    Applicable values are:  
        - None: No protection
        - Sign: Messages are signed
        - EncryptAndSign: Messages are encrypted and signed

<span data-ttu-id="0a7c0-526">Se aplica a: adaptador de WCF-NetTcp, adaptador de WCF-NetNamedPipe</span><span class="sxs-lookup"><span data-stu-id="0a7c0-526">Applies to: WCF-NetTcp adapter, WCF-NetNamedPipe adapter</span></span>  

#### <a name="username"></a><span data-ttu-id="0a7c0-527">UserName</span><span class="sxs-lookup"><span data-stu-id="0a7c0-527">UserName</span></span>
<span data-ttu-id="0a7c0-528">Especifique el nombre de usuario que se utilizará para la autenticación con el servidor de destino cuando la **UseSSO** propiedad está establecida en **False**.</span><span class="sxs-lookup"><span data-stu-id="0a7c0-528">Specify the user name to use for authentication with the destination server when the **UseSSO** property is set to **False**.</span></span> <span data-ttu-id="0a7c0-529">No tiene que usar el formato dominio\usuario para esta propiedad.</span><span class="sxs-lookup"><span data-stu-id="0a7c0-529">You do not have to use the domain\user format for this property.</span></span>

<span data-ttu-id="0a7c0-530">Tipo: cadena</span><span class="sxs-lookup"><span data-stu-id="0a7c0-530">Type: String</span></span>  
<span data-ttu-id="0a7c0-531">Valor predeterminado: una cadena vacía</span><span class="sxs-lookup"><span data-stu-id="0a7c0-531">Default value: An empty string</span></span>  
<span data-ttu-id="0a7c0-532">Se aplica a: WCF todos los adaptadores de envío *excepto* el adaptador WCF-NetNamedPipe</span><span class="sxs-lookup"><span data-stu-id="0a7c0-532">Applies to: All WCF send adapters *except* the WCF-NetNamedPipe adapter</span></span>

#### <a name="usesourcejournal"></a><span data-ttu-id="0a7c0-533">UseSourceJournal</span><span class="sxs-lookup"><span data-stu-id="0a7c0-533">UseSourceJournal</span></span>
<span data-ttu-id="0a7c0-534">Especificar si se deben almacenar copias de mensajes procesados por este puerto de envío en la cola de diario de origen.</span><span class="sxs-lookup"><span data-stu-id="0a7c0-534">Specify whether copies of messages processed by this send port should be stored in the source journal queue.</span></span>

<span data-ttu-id="0a7c0-535">Tipo: booleano</span><span class="sxs-lookup"><span data-stu-id="0a7c0-535">Type: Boolean</span></span>  
<span data-ttu-id="0a7c0-536">Valor predeterminado: False</span><span class="sxs-lookup"><span data-stu-id="0a7c0-536">Default value: False</span></span>  
<span data-ttu-id="0a7c0-537">Se aplica a: adaptador de envío WCF-NetMsmq</span><span class="sxs-lookup"><span data-stu-id="0a7c0-537">Applies to: WCF-NetMsmq send adapter</span></span>  

#### <a name="usesso"></a><span data-ttu-id="0a7c0-538">UseSSO</span><span class="sxs-lookup"><span data-stu-id="0a7c0-538">UseSSO</span></span>
<span data-ttu-id="0a7c0-539">Especificar si se utiliza el inicio de sesión único (SSO) para recuperar credenciales de cliente para la autenticación con el servidor de destino.</span><span class="sxs-lookup"><span data-stu-id="0a7c0-539">Specify whether to use Single Sign-On to retrieve client credentials for authentication with the destination server.</span></span> 

<span data-ttu-id="0a7c0-540">**Nota**</span><span class="sxs-lookup"><span data-stu-id="0a7c0-540">**Note**</span></span>  
<span data-ttu-id="0a7c0-541">No se puede realizar el seguimiento de esta propiedad en la base de datos de importación principal de BAM con los perfiles de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="0a7c0-541">This property cannot be tracked in the BAM Primary Import database with tracking profiles.</span></span> 

<span data-ttu-id="0a7c0-542">Tipo: booleano</span><span class="sxs-lookup"><span data-stu-id="0a7c0-542">Type: Boolean</span></span>  
<span data-ttu-id="0a7c0-543">Valor predeterminado: False</span><span class="sxs-lookup"><span data-stu-id="0a7c0-543">Default value: False</span></span>  
<span data-ttu-id="0a7c0-544">Se aplica a: WCF todos los adaptadores de envío *excepto* el adaptador WCF-NetNamedPipe</span><span class="sxs-lookup"><span data-stu-id="0a7c0-544">Applies to: All WCF send adapters *except* the WCF-NetNamedPipe adapter</span></span>

#### <a name="referencedbindings"></a><span data-ttu-id="0a7c0-545">ReferencedBindings</span><span class="sxs-lookup"><span data-stu-id="0a7c0-545">ReferencedBindings</span></span>
<span data-ttu-id="0a7c0-546">Especificar las configuraciones de enlace al que hace referencia el **bindingConfiguration** atributo de la  **\<emisor\>**  (elemento) para el  **wsFederationHttpBinding** y **customBinding**, lo que indica el Token de seguridad servicio (STS) que emite tokens de seguridad.</span><span class="sxs-lookup"><span data-stu-id="0a7c0-546">Specify the binding configurations referenced by the **bindingConfiguration** attribute of the **\<issuer\>** element for the **wsFederationHttpBinding** and **customBinding**, which indicates the Security Token Service (STS) that issues security tokens.</span></span> <span data-ttu-id="0a7c0-547">Para obtener más información sobre la  **\<emisor\>**  elemento, vea el tema "\<emisor\>" en [http://go.microsoft.com/fwlink/?LinkId=83476](http://go.microsoft.com/fwlink/?LinkId=83476).</span><span class="sxs-lookup"><span data-stu-id="0a7c0-547">For more information about the **\<issuer\>** element, see the topic, "\<issuer\>" at [http://go.microsoft.com/fwlink/?LinkId=83476](http://go.microsoft.com/fwlink/?LinkId=83476).</span></span>

<span data-ttu-id="0a7c0-548">La información de enlace, como la  **\<emisor\>**  (elemento) para la **wsFederationHttpBinding** y **customBinding** puede ser configurar a través de la **BindingConfiguration** propiedad de los adaptadores de WCF-Custom y WCF-CustomIsolated.</span><span class="sxs-lookup"><span data-stu-id="0a7c0-548">The binding information including the **\<issuer\>** element for the **wsFederationHttpBinding** and **customBinding** can be configured through the **BindingConfiguration** property of the WCF-Custom and WCF-CustomIsolated adapters.</span></span> <span data-ttu-id="0a7c0-549">Todas las configuraciones de enlace que se hace referencia para esta propiedad se deben colocar en el formulario de la [ \<enlaces\> ](http://go.microsoft.com/fwlink/?LinkID=80878) elemento.</span><span class="sxs-lookup"><span data-stu-id="0a7c0-549">All of the referenced binding configurations for this property must be placed in the form of the [\<bindings\>](http://go.microsoft.com/fwlink/?LinkID=80878) element.</span></span> 

<span data-ttu-id="0a7c0-550">**Nota**</span><span class="sxs-lookup"><span data-stu-id="0a7c0-550">**Note**</span></span>  
<span data-ttu-id="0a7c0-551">El **bindingConfiguration** atributo de la  **\<emisor\>**  el elemento debe hacer referencia a un nombre de enlace válido en esta propiedad.</span><span class="sxs-lookup"><span data-stu-id="0a7c0-551">The **bindingConfiguration** attribute of the **\<issuer\>** element must refer to a valid binding name in this property.</span></span> 

<span data-ttu-id="0a7c0-552">**Nota**</span><span class="sxs-lookup"><span data-stu-id="0a7c0-552">**Note**</span></span>  
<span data-ttu-id="0a7c0-553">El  **\<emisor\>**  elemento en las configuraciones de enlace que se hace referencia también puede hacer referencia a una configuración de enlace diferentes en esta propiedad si esta cadena de referencia no tiene una dependencia circular.</span><span class="sxs-lookup"><span data-stu-id="0a7c0-553">The **\<issuer\>** element in the referenced binding configurations can also refer to a different binding configuration in this property if this reference chain does not make a circular dependency.</span></span> 

<span data-ttu-id="0a7c0-554">Ejemplo:</span><span class="sxs-lookup"><span data-stu-id="0a7c0-554">Example:</span></span> 

```
WCF.BindingConfiguration = @"<wsFederationHttpBinding>
<binding name=""sampleBinding"">
<security mode=""Message"">
<message issuedKeyType=""AsymmetricKey"">
<issuer address=""http://www.contoso.com/samplests"" binding=""wsFederationHttpBinding"" bindingConfiguration=""**contosoSTSBinding**""/>
</message>
</security>
</binding>
</wsFederationHttpBinding>";
WCF.ReferencedBinding =@"<bindings>
<wsFederationHttpBinding>
<binding name=""**contosoSTSBinding**"">
<security mode=""Message"">
<message negotiateServiceCredential=""false"">
<issuer address=""http://northwind.com/samplests"" bindingConfiguration=""**northwindBinding**"" binding=""wsHttpBinding"">
</issuer>
</message>
</security>
</binding>
</wsFederationHttpBinding>
<wsHttpBinding>
<binding name=""**northwindBinding**"">
<security mode=""Message"">
<message clientCredentialType=""Certificate""/>
</security>
</binding>
</wsHttpBinding>
</bindings>" 
``` 

<span data-ttu-id="0a7c0-555">**Nota**</span><span class="sxs-lookup"><span data-stu-id="0a7c0-555">**Note**</span></span>  
<span data-ttu-id="0a7c0-556">**ReferencedBinding** no debe contener la configuración de enlace utilizada en el **BindingConfiguration** propiedad.</span><span class="sxs-lookup"><span data-stu-id="0a7c0-556">**ReferencedBinding** property must not contain the binding configuration used in the **BindingConfiguration** property.</span></span>

<span data-ttu-id="0a7c0-557">Tipo: cadena</span><span class="sxs-lookup"><span data-stu-id="0a7c0-557">Type: String</span></span>  
<span data-ttu-id="0a7c0-558">Valor predeterminado: una cadena vacía</span><span class="sxs-lookup"><span data-stu-id="0a7c0-558">Default value: An empty string</span></span>  
<span data-ttu-id="0a7c0-559">Se aplica a: adaptador de WCF-Custom, adaptador de WCF-CustomIsolated</span><span class="sxs-lookup"><span data-stu-id="0a7c0-559">Applies to: WCF-Custom adapter, WCF-CustomIsolated adapter</span></span>
  
## <a name="see-also"></a><span data-ttu-id="0a7c0-560">Vea también</span><span class="sxs-lookup"><span data-stu-id="0a7c0-560">See Also</span></span>  
 <span data-ttu-id="0a7c0-561">[Adaptadores de WCF](../core/wcf-adapters.md) </span><span class="sxs-lookup"><span data-stu-id="0a7c0-561">[WCF Adapters](../core/wcf-adapters.md) </span></span>  
 <span data-ttu-id="0a7c0-562">[\<comportamiento\> de \<endpointBehaviors\>](http://go.microsoft.com/fwlink/?LinkId=80879) </span><span class="sxs-lookup"><span data-stu-id="0a7c0-562">[\<behavior\> of \<endpointBehaviors\>](http://go.microsoft.com/fwlink/?LinkId=80879) </span></span>  
 <span data-ttu-id="0a7c0-563">[\<enlaces\>](http://go.microsoft.com/fwlink/?LinkId=80878) </span><span class="sxs-lookup"><span data-stu-id="0a7c0-563">[\<bindings\>](http://go.microsoft.com/fwlink/?LinkId=80878) </span></span>  
 <span data-ttu-id="0a7c0-564">[\<comportamiento\> de \<serviceBehaviors\>](http://go.microsoft.com/fwlink/?LinkId=81095) </span><span class="sxs-lookup"><span data-stu-id="0a7c0-564">[\<behavior\> of \<serviceBehaviors\>](http://go.microsoft.com/fwlink/?LinkId=81095) </span></span>  
 <span data-ttu-id="0a7c0-565">[Entrega ordenada de mensajes](../core/ordered-delivery-of-messages.md) </span><span class="sxs-lookup"><span data-stu-id="0a7c0-565">[Ordered Delivery of Messages](../core/ordered-delivery-of-messages.md) </span></span>  
 [<span data-ttu-id="0a7c0-566">Equilibrio de carga</span><span class="sxs-lookup"><span data-stu-id="0a7c0-566">Load Balancing</span></span>](http://go.microsoft.com/fwlink/?LinkId=81089)
