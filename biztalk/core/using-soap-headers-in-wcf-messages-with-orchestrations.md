---
title: Usar encabezados SOAP en mensajes WCF con orquestaciones | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- orchestrations, SOAP headers [WCF services]
- WCF services, orchestrations
- WCF services, SOAP headers
ms.assetid: 31c01e35-a2a6-4ea9-bdf4-6d4311268dbe
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6e8248ec62e75a058566eefef1942e1f82061dbb
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="using-soap-headers-in-wcf-messages-with-orchestrations"></a><span data-ttu-id="7cbd1-102">Usar encabezados SOAP en mensajes WCF con orquestaciones</span><span class="sxs-lookup"><span data-stu-id="7cbd1-102">Using SOAP Headers in WCF Messages with Orchestrations</span></span>
<span data-ttu-id="7cbd1-103">Para enviar los encabezados SOAP personalizados con mensajes WCF salientes en orquestaciones, use la propiedad de contexto **WCF. OutboundCustomHeaders**.</span><span class="sxs-lookup"><span data-stu-id="7cbd1-103">To send the custom SOAP headers with outgoing WCF messages in orchestrations, you use the context property, **WCF.OutboundCustomHeaders**.</span></span> <span data-ttu-id="7cbd1-104">Los adaptadores de WCF envían encabezados SOAP personalizados combinados con los encabezados SOAP estándar que utiliza la infraestructura de WCF para estándares de servicios Web, por ejemplo, WS-Addressing, WS-Security y WS-AtomicTransaction.</span><span class="sxs-lookup"><span data-stu-id="7cbd1-104">The WCF adapters send the custom SOAP headers combined with the standard SOAP headers that the WCF infrastructure uses for Web services standards such as WS-Addressing, WS-Security, and WS-AtomicTransaction.</span></span> <span data-ttu-id="7cbd1-105">Cuando se usa el **OutboundCustomHeaders** propiedad, la propiedad debe tener la \< **encabezados** \> elemento como el elemento raíz.</span><span class="sxs-lookup"><span data-stu-id="7cbd1-105">When you use the **OutboundCustomHeaders** property, the property must have the \<**headers**\> element as the root element.</span></span> <span data-ttu-id="7cbd1-106">Todos los encabezados SOAP personalizados deben colocarse dentro de la \< **encabezados** \> elemento.</span><span class="sxs-lookup"><span data-stu-id="7cbd1-106">All of the custom SOAP headers must be placed inside the \<**headers**\> element.</span></span> <span data-ttu-id="7cbd1-107">Si el valor del encabezado SOAP personalizado es una cadena vacía, debe asignar \< **encabezados**\>\</**encabezados** \> o \< **encabezados** / \> a la **OutboundCustomHeaders** propiedad.</span><span class="sxs-lookup"><span data-stu-id="7cbd1-107">If the custom SOAP header value is an empty string, you must assign \<**headers**\>\</**headers**\> or \<**headers**/\> to the **OutboundCustomHeaders** property.</span></span>  
  
 <span data-ttu-id="7cbd1-108">Respecto a las orquestaciones, las propiedades de contexto del encabezado SOAP están establecidas como cadenas que contienen datos XML.</span><span class="sxs-lookup"><span data-stu-id="7cbd1-108">For orchestrations, the SOAP header context properties are set to strings that contain XML data.</span></span> <span data-ttu-id="7cbd1-109">Establezca estas cadenas utilizando el Editor de expresiones de BizTalk en un **asignación de mensajes** o **expresión** forma.</span><span class="sxs-lookup"><span data-stu-id="7cbd1-109">You set these strings by using BizTalk Expression Editor in a **Message Assignment** or **Expression** shape.</span></span> <span data-ttu-id="7cbd1-110">Para obtener más información acerca de cómo usar encabezados SOAP con los adaptadores WCF, vea el ejemplo de SDK Using Custom SOAP Headers with the WCF Adapters de [http://go.microsoft.com/fwlink/?LinkId=79960](http://go.microsoft.com/fwlink/?LinkId=79960).</span><span class="sxs-lookup"><span data-stu-id="7cbd1-110">For more information about how to use SOAP headers with the WCF adapters, see the SDK sample, Using Custom SOAP Headers with the WCF Adapters, from [http://go.microsoft.com/fwlink/?LinkId=79960](http://go.microsoft.com/fwlink/?LinkId=79960).</span></span>  
  
 <span data-ttu-id="7cbd1-111">El siguiente ejemplo (de una forma Asignación de mensajes o Expresión) muestra la configuración de la cadena de la propiedad de contexto:</span><span class="sxs-lookup"><span data-stu-id="7cbd1-111">The following example (from a Message Assignment or an Expression shape) shows the string setting the context property:</span></span>  
  
```  
outboundMessageInstance(WCF.OutboundCustomHeaders) = "<headers><Origination>Home</Origination><Destination>Work</Destination></headers>"  
```  
  
## <a name="creating-an-xmldocument-to-set-context-properties"></a><span data-ttu-id="7cbd1-112">Crear un XmlDocument para establecer propiedades de contexto</span><span class="sxs-lookup"><span data-stu-id="7cbd1-112">Creating an XmlDocument to set context properties</span></span>  
 <span data-ttu-id="7cbd1-113">Puede establecer el **WCF. OutboundCustomHeaders** propiedad de contexto mediante la creación de un **XmlDocument** y escribir el valor de cadena de la **XmlDocument** a la propiedad de contexto.</span><span class="sxs-lookup"><span data-stu-id="7cbd1-113">You can set the **WCF.OutboundCustomHeaders** context property by creating an **XmlDocument** and writing the string value of the **XmlDocument** to the context property.</span></span> <span data-ttu-id="7cbd1-114">Declare una variable de tipo **XMLDocument** y asigne los datos XML.</span><span class="sxs-lookup"><span data-stu-id="7cbd1-114">You declare a variable of type **XMLDocument** and assign the XML data.</span></span>  
  
 <span data-ttu-id="7cbd1-115">En el ejemplo siguiente se muestra la declaración de una variable de tipo **XMLDocument** y asignar los datos XML:</span><span class="sxs-lookup"><span data-stu-id="7cbd1-115">The following example shows declaring a variable of type **XMLDocument** and assigning the XML data:</span></span>  
  
```  
xmlDoc.LoadXml("<headers><Origination>Home</Origination><Destination>Work</Destination></headers>");  
```  
  
 <span data-ttu-id="7cbd1-116">El siguiente ejemplo muestra la configuración de la propiedad de contexto:</span><span class="sxs-lookup"><span data-stu-id="7cbd1-116">The following example shows setting the context property:</span></span>  
  
```  
RequestMessageInstance(WCF.OutboundCustomHeaders) = xmlDoc.OuterXml;  
```  
  
 <span data-ttu-id="7cbd1-117">Para obtener más información acerca de cómo utilizar el Editor de expresiones de BizTalk, consulte [requisitos y limitaciones para las expresiones](../core/requirements-and-limitations-for-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="7cbd1-117">For more information about using BizTalk Expression Editor, see [Requirements and Limitations for Expressions](../core/requirements-and-limitations-for-expressions.md).</span></span> <span data-ttu-id="7cbd1-118">Para obtener más información acerca de las llamadas [!INCLUDE[btsDotNet](../includes/btsdotnet-md.md)] clases, vea el artículo [construir mensajes en el código de usuario](../core/constructing-messages-in-user-code.md).</span><span class="sxs-lookup"><span data-stu-id="7cbd1-118">For more information about calling [!INCLUDE[btsDotNet](../includes/btsdotnet-md.md)] classes, see [Constructing Messages in User Code](../core/constructing-messages-in-user-code.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7cbd1-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="7cbd1-119">See Also</span></span>  
 <span data-ttu-id="7cbd1-120">[Propiedades y esquema de propiedades de adaptadores WCF](../core/wcf-adapters-property-schema-and-properties.md) </span><span class="sxs-lookup"><span data-stu-id="7cbd1-120">[WCF Adapters Property Schema and Properties](../core/wcf-adapters-property-schema-and-properties.md) </span></span>  
 <span data-ttu-id="7cbd1-121">[Encabezados SOAP con servicios WCF consumidos](../core/soap-headers-with-consumed-wcf-services.md) </span><span class="sxs-lookup"><span data-stu-id="7cbd1-121">[SOAP Headers with Consumed WCF Services](../core/soap-headers-with-consumed-wcf-services.md) </span></span>  
 [<span data-ttu-id="7cbd1-122">Encabezados SOAP con servicios WCF publicados</span><span class="sxs-lookup"><span data-stu-id="7cbd1-122">SOAP Headers with Published WCF Services</span></span>](../core/soap-headers-with-published-wcf-services.md)