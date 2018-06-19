---
title: Propiedades de Descriptor de mensajes TIBCO EMS | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fc164c12-6dc3-4b74-9aa9-024e18faf80a
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c1a2a7d6529cffba6afa3969964d1ea436d7fcda
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/07/2017
ms.locfileid: "24014827"
---
# <a name="tibco-enterprise-message-service-message-descriptor-properties"></a><span data-ttu-id="a318d-102">Propiedades del descriptor de mensajes de TIBCO Enterprise Message Service</span><span class="sxs-lookup"><span data-stu-id="a318d-102">TIBCO Enterprise Message Service Message Descriptor Properties</span></span>

## <a name="descriptor-properties-and-values"></a><span data-ttu-id="a318d-103">Propiedades de descriptor y valores</span><span class="sxs-lookup"><span data-stu-id="a318d-103">Descriptor properties, and values</span></span>
<span data-ttu-id="a318d-104">En la tabla siguiente se muestra el conjunto completo de propiedades disponibles del descriptor de mensajes (estructura TibcoEMSMD), así como los valores y tipos correspondientes.</span><span class="sxs-lookup"><span data-stu-id="a318d-104">The following table shows the complete set of available Message Descriptor (TibcoEMSMD structure) properties and their corresponding types and values.</span></span>  
  
|<span data-ttu-id="a318d-105">Nombre</span><span class="sxs-lookup"><span data-stu-id="a318d-105">Name</span></span>|<span data-ttu-id="a318d-106">Tipo</span><span class="sxs-lookup"><span data-stu-id="a318d-106">Type</span></span>|<span data-ttu-id="a318d-107">Value</span><span class="sxs-lookup"><span data-stu-id="a318d-107">Value</span></span>|<span data-ttu-id="a318d-108">Notas</span><span class="sxs-lookup"><span data-stu-id="a318d-108">Notes</span></span>|  
|----------|----------|-----------|-----------|  
|<span data-ttu-id="a318d-109">TibcoEMS .CorrelationID</span><span class="sxs-lookup"><span data-stu-id="a318d-109">TibcoEMS .CorrelationID</span></span>|<span data-ttu-id="a318d-110">string</span><span class="sxs-lookup"><span data-stu-id="a318d-110">string</span></span>|||  
|<span data-ttu-id="a318d-111">TibcoEMS .DelieveryMode</span><span class="sxs-lookup"><span data-stu-id="a318d-111">TibcoEMS .DelieveryMode</span></span>|<span data-ttu-id="a318d-112">string</span><span class="sxs-lookup"><span data-stu-id="a318d-112">string</span></span>|<span data-ttu-id="a318d-113">Uno PERSISTENT o NON-PERSISTENT</span><span class="sxs-lookup"><span data-stu-id="a318d-113">One of PERSISENT or NON-PERSISTENT</span></span>||  
|<span data-ttu-id="a318d-114">TibcoEMS .Destination</span><span class="sxs-lookup"><span data-stu-id="a318d-114">TibcoEMS .Destination</span></span>|<span data-ttu-id="a318d-115">string</span><span class="sxs-lookup"><span data-stu-id="a318d-115">string</span></span>||<span data-ttu-id="a318d-116">Solo lectura</span><span class="sxs-lookup"><span data-stu-id="a318d-116">Read-only</span></span>|  
|<span data-ttu-id="a318d-117">TibcoEMS .Expiration</span><span class="sxs-lookup"><span data-stu-id="a318d-117">TibcoEMS .Expiration</span></span>|<span data-ttu-id="a318d-118">long</span><span class="sxs-lookup"><span data-stu-id="a318d-118">long</span></span>|||  
|<span data-ttu-id="a318d-119">TibcoEMS .MessageID</span><span class="sxs-lookup"><span data-stu-id="a318d-119">TibcoEMS .MessageID</span></span>|<span data-ttu-id="a318d-120">string</span><span class="sxs-lookup"><span data-stu-id="a318d-120">string</span></span>||<span data-ttu-id="a318d-121">Solo lectura</span><span class="sxs-lookup"><span data-stu-id="a318d-121">Read-only</span></span>|  
|<span data-ttu-id="a318d-122">TibcoEMS .Priority</span><span class="sxs-lookup"><span data-stu-id="a318d-122">TibcoEMS .Priority</span></span>|<span data-ttu-id="a318d-123">integer</span><span class="sxs-lookup"><span data-stu-id="a318d-123">integer</span></span>|<span data-ttu-id="a318d-124">De 0 a 9</span><span class="sxs-lookup"><span data-stu-id="a318d-124">From 0 to 9</span></span>||  
|<span data-ttu-id="a318d-125">TibcoEMS .Redelivered</span><span class="sxs-lookup"><span data-stu-id="a318d-125">TibcoEMS .Redelivered</span></span>|<span data-ttu-id="a318d-126">boolean</span><span class="sxs-lookup"><span data-stu-id="a318d-126">boolean</span></span>||<span data-ttu-id="a318d-127">Solo lectura</span><span class="sxs-lookup"><span data-stu-id="a318d-127">Read-only</span></span>|  
|<span data-ttu-id="a318d-128">TibcoEMS .ReplyTo</span><span class="sxs-lookup"><span data-stu-id="a318d-128">TibcoEMS .ReplyTo</span></span>|<span data-ttu-id="a318d-129">string</span><span class="sxs-lookup"><span data-stu-id="a318d-129">string</span></span>|<span data-ttu-id="a318d-130">Similar al destino</span><span class="sxs-lookup"><span data-stu-id="a318d-130">Similar to Destination</span></span>||  
|<span data-ttu-id="a318d-131">TibcoEMS .Timestamp</span><span class="sxs-lookup"><span data-stu-id="a318d-131">TibcoEMS .Timestamp</span></span>|<span data-ttu-id="a318d-132">long</span><span class="sxs-lookup"><span data-stu-id="a318d-132">long</span></span>||<span data-ttu-id="a318d-133">Solo lectura</span><span class="sxs-lookup"><span data-stu-id="a318d-133">Read-only</span></span>|  
  
 <span data-ttu-id="a318d-134">Las propiedades de solo lectura son aquellas que TIBCO Enterprise Message Service establece cuando el mensaje se entrega al adaptador de Microsoft BizTalk para TIBCO EMS.</span><span class="sxs-lookup"><span data-stu-id="a318d-134">The read-only properties are those properties that are set by TIBCO Enterprise Message Service when the message is delivered to Microsoft BizTalk Adapter for TIBCO EMS.</span></span> <span data-ttu-id="a318d-135">Cambiar el valor, aunque es posible en la expresión de la forma de asignación del mensaje, no afecta al mensaje.</span><span class="sxs-lookup"><span data-stu-id="a318d-135">Changing the value, although it is possible in the expression of the message assignment shape, does not affect the message.</span></span>  
  
 <span data-ttu-id="a318d-136">Para otras propiedades que se deben mover del mensaje de EMS al mensaje de BizTalk Server, se debe crear un DLL de propiedades y usarlo en el proyecto.</span><span class="sxs-lookup"><span data-stu-id="a318d-136">For other properties that must be moved from the EMS message to the BizTalk Server message, you must create a properties DLL and use it in the project.</span></span>  
  
 <span data-ttu-id="a318d-137">El siguiente ejemplo de esquema de propiedades permite que la orquestación use la propiedad de mensaje `JMSXDeliveryCount`.</span><span class="sxs-lookup"><span data-stu-id="a318d-137">The following sample properties schema enables the orchestration to use the `JMSXDeliveryCount` message property.</span></span>  
  
```  
<?xml version="1.0" encoding="utf-16"?>  
<xs:schema xmlns:b="http://schemas.microsoft.com/BizTalk/2003" targetNamespace="http://schemas.microsoft.com/BizTalk/TibcoEMS-properties" xmlns:xs="http://www.w3.org/2001/XMLSchema">  
    <xs:annotation>  
        <xs:appinfo>  
            <b:schemaInfo schema_type="property" xmlns:b="http://schemas.microsoft.com/BizTalk/2003" />  
        </xs:appinfo>  
    </xs:annotation>  
    <xs:element name="JMSXDeliveryCount" type="xs:long">  
        <xs:annotation>  
            <xs:appinfo>  
                <b:fieldInfo propertyGuid="f62f1a4b-a528-45fb-b1f8-bd880e9f46db" />  
            </xs:appinfo>  
        </xs:annotation>  
    </xs:element>  
</xs:schema>   
```  
  
 <span data-ttu-id="a318d-138">Asegúrese de que se usa el espacio de nombres de destino; únicamente la propiedades que usan este espacio de nombres se copian al mensaje de BizTalk Server o de EMS.</span><span class="sxs-lookup"><span data-stu-id="a318d-138">Make sure that the target namespace is used; only properties that use this namespace are copied to the BizTalk Server message or to the EMS message.</span></span> <span data-ttu-id="a318d-139">Consulte la documentación de BizTalk Server para obtener más información acerca de las propiedades de contexto del mensaje.</span><span class="sxs-lookup"><span data-stu-id="a318d-139">See the BizTalk Server documentation for more information about message context properties.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a318d-140">Vea también</span><span class="sxs-lookup"><span data-stu-id="a318d-140">See Also</span></span>  
[<span data-ttu-id="a318d-141">Propiedades de contexto del mensaje de TIBCO EMS</span><span class="sxs-lookup"><span data-stu-id="a318d-141">TIBCO EMS message context properties</span></span>](../core/message-context-properties-in-biztalk-server.md)