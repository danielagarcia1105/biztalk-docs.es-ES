---
title: Usar campos distintivos y campos de propiedades | Microsoft Docs
description: Obtenga información acerca de las diferencias entre los conjuntos de propiedades, campos distintivos y campos de propiedades. Los campos distintivos utilizan la ruta de acceso en el campo de mensaje, los campos de propiedades que se usa el nombre del mensaje y el espacio de nombres de esquema y conjuntos de propiedades asignación las propiedades de contexto de un mensaje (un conjunto de propiedades) a las propiedades de contexto de otro mensaje de BizTalk Server
ms.custom: ''
ms.date: 05/02/2018
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 264ee15e-be9a-4ba2-9c61-a1570b20378e
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dd58f8b9e72f955bc02c5b7116469390468937d9
ms.sourcegitcommit: 53b16fe6c1b1707ecf233dbd05f780653eb19419
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/01/2018
ms.locfileid: "50752307"
---
# <a name="using-distinguished-fields-and-property-fields"></a><span data-ttu-id="4f60c-104">Usar campos distintivos y campos de propiedades</span><span class="sxs-lookup"><span data-stu-id="4f60c-104">Using Distinguished Fields and Property Fields</span></span>
<span data-ttu-id="4f60c-105">los campos distintivos son datos de mensaje de especial interés que se usan principalmente para tomar decisiones o manipular datos de la orquestación.</span><span class="sxs-lookup"><span data-stu-id="4f60c-105">Distinguished fields are message data of special interest that you use primarily to make decisions or to manipulate data in your orchestration.</span></span>  
  
 <span data-ttu-id="4f60c-106">Propiedades de mensaje son datos: contenido del propio mensaje, o "metadata", información de contexto sobre el mensaje como marcas de tiempo o información de enrutamiento.</span><span class="sxs-lookup"><span data-stu-id="4f60c-106">Message properties are either data—contents of the message itself—or "metadata"—context information about the message such as time stamps or routing information.</span></span> <span data-ttu-id="4f60c-107">Puede usar propiedades de contexto de transporte o mensaje definidas por el sistema o bien puede definir sus propias propiedades mediante la referencia a campos de esquema desde un esquema de propiedades.</span><span class="sxs-lookup"><span data-stu-id="4f60c-107">You can use system-defined message context properties or transport context properties, or you can define your own properties by making reference to schema fields from within a property schema.</span></span> <span data-ttu-id="4f60c-108">Las propiedades se usan en suscripciones y correlaciones.</span><span class="sxs-lookup"><span data-stu-id="4f60c-108">Properties are used in subscriptions and correlations.</span></span>  
  
-   <span data-ttu-id="4f60c-109">Puede designar un campo en un esquema como campo distintivo o campo de propiedad mediante la **promocionar propiedades** cuadro de diálogo en el Editor.</span><span class="sxs-lookup"><span data-stu-id="4f60c-109">You can designate a field in a schema as a distinguished field or property field by using the **Promote Properties** dialog box from within the Editor.</span></span> <span data-ttu-id="4f60c-110">Para obtener más información, consulte [promocionar propiedades](../core/promoting-properties.md)</span><span class="sxs-lookup"><span data-stu-id="4f60c-110">For more information, see [Promoting Properties](../core/promoting-properties.md)</span></span>  
  
-   <span data-ttu-id="4f60c-111">Puede designar un campo en un tipo .NET como campo distintivo al decorarlo con el atributo DistinguishedField o como propiedad con el atributo Property.</span><span class="sxs-lookup"><span data-stu-id="4f60c-111">You can designate a field in a .NET type as a distinguished field by decorating it with the DistinguishedField attribute, or as a property by the Property attribute.</span></span>  
  
## <a name="using-distinguished-fields"></a><span data-ttu-id="4f60c-112">Usar campos distintivos</span><span class="sxs-lookup"><span data-stu-id="4f60c-112">Using Distinguished Fields</span></span>  
 <span data-ttu-id="4f60c-113">Los campos distintivos se denominan mediante la ruta al campo en el mensaje, con puntos para separar el nombre del mensaje, los nombres de los registros que cierran el campo y el propio nombre del campo:</span><span class="sxs-lookup"><span data-stu-id="4f60c-113">Distinguished fields are referred to by the path to the field in the message, using periods to separate the message name, the names of any records that enclose the field, and the name of the field itself:</span></span>  
  
```  
MyMessage.MyRecord.MySubrecord.MyDistinguishedField  
```  
  
## <a name="using-property-fields"></a><span data-ttu-id="4f60c-114">Usar campos de propiedades</span><span class="sxs-lookup"><span data-stu-id="4f60c-114">Using Property Fields</span></span>  
 <span data-ttu-id="4f60c-115">Una vez que ha agregado un campo a un esquema de propiedades, se puede tener acceso a su valor en la orquestación con código y en expresiones de filtro.</span><span class="sxs-lookup"><span data-stu-id="4f60c-115">Once you have added a field to a property schema, its value can be accessed in the orchestration with code and in filter expressions.</span></span> <span data-ttu-id="4f60c-116">Para obtener más información acerca de los esquemas de propiedad, vea [esquemas de propiedad](../core/property-schemas.md).</span><span class="sxs-lookup"><span data-stu-id="4f60c-116">For more information about property schemas, see [Property Schemas](../core/property-schemas.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4f60c-117">Propiedades de contenido o los datos de mensajes son esencialmente accesos directos a los datos subyacentes: si modifica la propiedad, se modificarán los datos y viceversa.</span><span class="sxs-lookup"><span data-stu-id="4f60c-117">Message content or data properties are essentially shortcuts to the underlying data: if you modify the property, the data will be modified, and vice versa.</span></span>  
  
 <span data-ttu-id="4f60c-118">Las propiedades de los mensajes se denominan mediante el nombre del mensaje seguido del espacio de nombres (el esquema) y el nombre de la propiedad entre paréntesis:</span><span class="sxs-lookup"><span data-stu-id="4f60c-118">Message properties are referred to by the name of the message followed by the namespace (the schema) and property name in parentheses:</span></span>  
  
```  
MyMessage(Invoice.PropertySchema.InvoiceID)  
```  
  
> [!NOTE]
>  <span data-ttu-id="4f60c-119">Cuando utiliza una palabra clave reservada como el nombre de un campo en un esquema y promocionar el campo seleccionando promoción rápida, el nombre del campo de propiedad se cambia a __\<palabra clave reservada\>.</span><span class="sxs-lookup"><span data-stu-id="4f60c-119">When you use a reserved keyword as the name of a field in a schema, and you promote the field by selecting Quick Promotion, the property name of the field is changed to __\<Reserved Keyword\>.</span></span> <span data-ttu-id="4f60c-120">(El subrayado doble se agrega delante del nombre de la propiedad.) Sin embargo, si usa este nombre de propiedad en una expresión de orquestación, recibirá un error del compilador al crear la orquestación.</span><span class="sxs-lookup"><span data-stu-id="4f60c-120">(The double underscore is added before the property name.) However, if you use this property name in an orchestration expression, you will receive a compiler error when building the orchestration.</span></span>  <span data-ttu-id="4f60c-121">Para solucionar este error, deberá agregar manualmente \@ delante del subrayado doble.</span><span class="sxs-lookup"><span data-stu-id="4f60c-121">To work around this error, you need to manually add \@ before the double underscore.</span></span> <span data-ttu-id="4f60c-122">Por ejemplo,</span><span class="sxs-lookup"><span data-stu-id="4f60c-122">For example,</span></span>  
>   
>  `MyMessage(Invoice.PropertySchema.@__Name) = "Product Name";`  
  
## <a name="property-sets"></a><span data-ttu-id="4f60c-123">Conjuntos de propiedades</span><span class="sxs-lookup"><span data-stu-id="4f60c-123">Property Sets</span></span>  
 <span data-ttu-id="4f60c-124">También puede asignar todas las propiedades de contexto de un mensaje (un conjunto de propiedades) a las propiedades de contexto de otro mensaje.</span><span class="sxs-lookup"><span data-stu-id="4f60c-124">You can also assign all of the context properties of one message (a property set) to the context properties of another message.</span></span> <span data-ttu-id="4f60c-125">Para asignar un conjunto de propiedades, basta con colocar un asterisco entre paréntesis después de los dos nombres de mensaje, igual que si colocara una propiedad entre paréntesis:</span><span class="sxs-lookup"><span data-stu-id="4f60c-125">To assign a property set, you simply place an asterisk in parentheses after both message names, in the same way you would put a property in parentheses:</span></span>  
  
```  
MyMessage2(*)=MyMessage1(*);  
```  
  
 <span data-ttu-id="4f60c-126">Después de que el conjunto de propiedades se ha asignado a MyMessage2 en el ejemplo, todas las propiedades en MyMessage2 contienen los mismos valores que las propiedades en MyMessage1.</span><span class="sxs-lookup"><span data-stu-id="4f60c-126">After the property set has been assigned to MyMessage2 in the example, all of the properties in MyMessage2 contain the same values as the properties in MyMessage1.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4f60c-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="4f60c-127">See Also</span></span>  
 <span data-ttu-id="4f60c-128">[Promoción de propiedades](../core/promoting-properties.md) </span><span class="sxs-lookup"><span data-stu-id="4f60c-128">[Promoting Properties](../core/promoting-properties.md) </span></span>  
 <span data-ttu-id="4f60c-129">[Uso de filtros con la forma recibir mensaje](../core/using-filters-with-the-receive-message-shape.md) </span><span class="sxs-lookup"><span data-stu-id="4f60c-129">[Using Filters With the Receive Message Shape](../core/using-filters-with-the-receive-message-shape.md) </span></span>  
 <span data-ttu-id="4f60c-130">[Uso de los mensajes en orquestaciones](../core/using-messages-in-orchestrations.md) </span><span class="sxs-lookup"><span data-stu-id="4f60c-130">[Using Messages in Orchestrations](../core/using-messages-in-orchestrations.md) </span></span>  
 [<span data-ttu-id="4f60c-131">Propiedades de contexto de mensaje de BizTalk</span><span class="sxs-lookup"><span data-stu-id="4f60c-131">About BizTalk Message Context Properties</span></span>](../core/about-biztalk-message-context-properties.md)
