---
title: Adaptador de envío de WCF | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- messages, headers
- serializing, SOAP messages
- WCF adapters, extracting information
- messages, extracting information
- SOAP messages, serializing
- WCF adapters, message bodies
- send adapters, WCF adapters
- Web services, headers
- WCF adapters, send adapters
ms.assetid: 226a020a-2e12-41fe-a4a2-6683d9e98219
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 70604fbc15f5f15b0a7ff2325debdc28ac3a97c1
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22288764"
---
# <a name="wcf-send-adapter"></a><span data-ttu-id="e3dfa-102">Adaptador de envío WCF</span><span class="sxs-lookup"><span data-stu-id="e3dfa-102">WCF Send Adapter</span></span>
<span data-ttu-id="e3dfa-103">El adaptador de envío WCF le permite llamar a un Servicio WCF a través del contrato sin tipo.</span><span class="sxs-lookup"><span data-stu-id="e3dfa-103">The WCF send adapter enables you to call a WCF service through the typeless contract.</span></span>  
  
## <a name="specifying-the-wcf-message-body"></a><span data-ttu-id="e3dfa-104">Especificar el cuerpo de mensaje WCF</span><span class="sxs-lookup"><span data-stu-id="e3dfa-104">Specifying the WCF Message Body</span></span>  
 <span data-ttu-id="e3dfa-105">El cuerpo de mensaje que necesita enviar al servidor BizTalk Server puede insertarse en el mensaje SOAP mediante la utilización de una de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="e3dfa-105">The message body that needs to be sent from BizTalk Server can be inserted into the SOAP message by using one of the following options:</span></span>  
  
-   <span data-ttu-id="e3dfa-106">Extraer el contenido del cuerpo del mensaje de BizTalk</span><span class="sxs-lookup"><span data-stu-id="e3dfa-106">Extract the content of the BizTalk message body</span></span>  
  
-   <span data-ttu-id="e3dfa-107">Especificar el contenido mediante la plantilla</span><span class="sxs-lookup"><span data-stu-id="e3dfa-107">Specify the content by using the template</span></span>  
  
 <span data-ttu-id="e3dfa-108">Puede configurar estas opciones en el cuadro de diálogo de propiedades de transporte de puerto de envío.</span><span class="sxs-lookup"><span data-stu-id="e3dfa-108">You can configure these options in the send port transport properties dialog box.</span></span>  
  
#### <a name="extract-the-content-of-the-biztalk-message-body"></a><span data-ttu-id="e3dfa-109">Extraer el contenido del cuerpo de mensaje de BizTalk</span><span class="sxs-lookup"><span data-stu-id="e3dfa-109">Extract the Content of the BizTalk Message Body</span></span>  
 <span data-ttu-id="e3dfa-110">Cuando se selecciona esta opción, se inserta el contenido del cuerpo de mensaje de BizTalk en el elemento de Cuerpo de SOAP para el cuerpo de mensaje de salida de WCF.</span><span class="sxs-lookup"><span data-stu-id="e3dfa-110">When this option is selected, the content of the BizTalk message body is inserted into the SOAP Body element for the outbound WCF message body.</span></span>  
  
#### <a name="specify-the-content-by-using-the-template"></a><span data-ttu-id="e3dfa-111">Especificar el contenido utilizando la plantilla</span><span class="sxs-lookup"><span data-stu-id="e3dfa-111">Specify the Content by Using the Template</span></span>  
 <span data-ttu-id="e3dfa-112">Cuando se selecciona esta opción, se sitúa del cuerpo de mensaje de BizTalk en el elemento de cuerpo de SOAP para la plantilla XML para el cuerpo de mensaje de salida de WCF.</span><span class="sxs-lookup"><span data-stu-id="e3dfa-112">When this option is selected, the BizTalk message body is placed in the SOAP body element under the given XML template for the outbound WCF message body.</span></span>  
  
## <a name="serializing-the-biztalk-message-into-a-soap-message"></a><span data-ttu-id="e3dfa-113">Serializar el mensaje de BizTalk en un mensaje SOAP</span><span class="sxs-lookup"><span data-stu-id="e3dfa-113">Serializing the BizTalk Message into a SOAP Message</span></span>  
 <span data-ttu-id="e3dfa-114">El adaptador de envío serializa el mensaje de BizTalk en un mensaje SOPA antes de enviarlo. Las siguientes reglas se aplican durante la serialización del mensaje:</span><span class="sxs-lookup"><span data-stu-id="e3dfa-114">The send adapter serializes the BizTalk message into a SOAP message before sending it out. The following rules apply during serialization of the message:</span></span>  
  
-   <span data-ttu-id="e3dfa-115">Si el mensaje de BizTalk es un mensaje de varias partes, sólo se usa la parte del cuerpo.</span><span class="sxs-lookup"><span data-stu-id="e3dfa-115">If the BizTalk message is a multipart message, then only the body part is used.</span></span>  
  
-   <span data-ttu-id="e3dfa-116">Si el mensaje de BizTalk contiene el sobre de SOAP completo, se envuelve un otro sobre SOAP.</span><span class="sxs-lookup"><span data-stu-id="e3dfa-116">If the BizTalk message contains the entire SOAP envelope, then it is wrapped into another SOAP envelope.</span></span>  
  
-   <span data-ttu-id="e3dfa-117">Si el mensaje de BizTalk contiene datos XML arbitrarios, el mensaje de BizTalk se coloca en el elemento Cuerpo de SOAP.</span><span class="sxs-lookup"><span data-stu-id="e3dfa-117">If the BizTalk message contains arbitrary XML data, then the BizTalk message is placed into the SOAP Body element.</span></span>  
  
## <a name="handling-web-services-headers"></a><span data-ttu-id="e3dfa-118">Controlar encabezados de servicios Web</span><span class="sxs-lookup"><span data-stu-id="e3dfa-118">Handling Web Services Headers</span></span>  
 <span data-ttu-id="e3dfa-119">Durante las operaciones de envío, BizTaklk Server no tiene control sobre los encabezados estándar de servicios Web.</span><span class="sxs-lookup"><span data-stu-id="e3dfa-119">During send operations BizTalk Server does not have control over Web services standard headers.</span></span> <span data-ttu-id="e3dfa-120">WCF establece y procesa los encabezados.</span><span class="sxs-lookup"><span data-stu-id="e3dfa-120">Those headers are set and processed by the WCF.</span></span> <span data-ttu-id="e3dfa-121">El único encabezado estándar que se puede modificar mediante la aplicación de BizTalk Server es el **un: acción** encabezado.</span><span class="sxs-lookup"><span data-stu-id="e3dfa-121">The only standard header that can be modified by the BizTalk Server application is the **a:Action** header.</span></span> <span data-ttu-id="e3dfa-122">Si la propiedad de contexto **acción** se especifica en el espacio de nombres de adaptador, el adaptador de envío WCF utilizará el valor de la propiedad para establecer el **acción** en el mensaje SOAP.</span><span class="sxs-lookup"><span data-stu-id="e3dfa-122">If the context property **Action** is specified on the adapter namespace, then the WCF send adapter will use the value of the property to set the **Action** on the SOAP message.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e3dfa-123">Para dinámicas de puertos de envío, si **acción** se especifica en el **OutboundHeaders**, la propiedad de contexto establecido para el **WCF. Acción** se pasará por alto.</span><span class="sxs-lookup"><span data-stu-id="e3dfa-123">For dynamic send ports, if **Action** is specified in the **OutboundHeaders**, the context property you set for the **WCF.Action** will be ignored.</span></span>  
  
## <a name="specifying-the-btsisdynamicsend-context-property"></a><span data-ttu-id="e3dfa-124">Especificar la propiedad de contexto BTS.IsDynamicSend</span><span class="sxs-lookup"><span data-stu-id="e3dfa-124">Specifying the BTS.IsDynamicSend Context Property</span></span>  
 <span data-ttu-id="e3dfa-125">El adaptador de envío WCF almacena la configuración para los puertos de envío.</span><span class="sxs-lookup"><span data-stu-id="e3dfa-125">The WCF send adapter caches the configuration for send ports.</span></span> <span data-ttu-id="e3dfa-126">Si el **BTS. IsDynamicSend** propiedad está establecida en true, el envío WCF adaptador no usa la configuración almacenada en caché, sino que lee toda la información de configuración desde el mensaje de propiedades de contexto de los mensajes salientes.</span><span class="sxs-lookup"><span data-stu-id="e3dfa-126">If the **BTS.IsDynamicSend** property is set to true, the WCF send adapter does not use the cached configuration, but instead reads all configuration information from the message context properties of the outbound messages.</span></span> <span data-ttu-id="e3dfa-127">En un puerto de envío estático, WCF adaptador de envío utiliza **BTS. SPLastUpdatedTime**, que es el momento en que la configuración del puerto de envío estático se modificó por última vez, para detectar si hay cualquier configuración de puerto de envío de cambios en el método estático.</span><span class="sxs-lookup"><span data-stu-id="e3dfa-127">On a static send port, the WCF send adapter uses **BTS.SPLastUpdatedTime**, which is the time that the static send port settings were last modified, to detect if there are any configuration changes on the static send port.</span></span> <span data-ttu-id="e3dfa-128">De esta forma, el adaptador de envío WCF no necesita leer todas las configuraciones de todos los contextos de mensaje.</span><span class="sxs-lookup"><span data-stu-id="e3dfa-128">In this way the WCF send adapter does not need to read all of the settings from every message context.</span></span>  
  
 <span data-ttu-id="e3dfa-129">Si desea invalidar las propiedades de puerto de envío estático distinto de la **WCF. Acción** propiedad en una canalización de envío, debe establecer el **BTS. IsDynamicSend** no ha cambiado la propiedad en true para que el adaptador de envío WCF no usará la configuración almacenada en caché aunque la última marca de tiempo actualizada.</span><span class="sxs-lookup"><span data-stu-id="e3dfa-129">If you want to override the static send port properties other than the **WCF.Action** property in a send pipeline, you need to set the **BTS.IsDynamicSend** property to true so that the WCF send adapter will not use the cached configuration even though the last updated timestamp has not changed.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e3dfa-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="e3dfa-130">See Also</span></span>  
 <span data-ttu-id="e3dfa-131">[Especificar el cuerpo del mensaje para los adaptadores de WCF](../core/specifying-the-message-body-for-the-wcf-adapters.md) </span><span class="sxs-lookup"><span data-stu-id="e3dfa-131">[Specifying the Message Body for the WCF Adapters](../core/specifying-the-message-body-for-the-wcf-adapters.md) </span></span>  
 <span data-ttu-id="e3dfa-132">[Adaptador de recepción de WCF](../core/wcf-receive-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="e3dfa-132">[WCF Receive Adapter](../core/wcf-receive-adapter.md) </span></span>  
 <span data-ttu-id="e3dfa-133">[¿Cuáles son los adaptadores de WCF?](../core/what-are-the-wcf-adapters.md) </span><span class="sxs-lookup"><span data-stu-id="e3dfa-133">[What Are the WCF Adapters?](../core/what-are-the-wcf-adapters.md) </span></span>  
 [<span data-ttu-id="e3dfa-134">Cómo utilizar propiedades de contexto de mensaje</span><span class="sxs-lookup"><span data-stu-id="e3dfa-134">How to Use Message Context Properties</span></span>](../core/how-to-use-message-context-properties.md)