---
title: Esquemas de propiedad | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8018bb72-a037-4eeb-bbbe-dd0cc6209aec
caps.latest.revision: "14"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d2fb50536b2521e77994baf0b6457206614b7eed
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="property-schemas"></a><span data-ttu-id="4bb6a-102">Esquemas de propiedades</span><span class="sxs-lookup"><span data-stu-id="4bb6a-102">Property Schemas</span></span>

## <a name="promoted-properties"></a><span data-ttu-id="4bb6a-103">Propiedades promocionadas</span><span class="sxs-lookup"><span data-stu-id="4bb6a-103">Promoted properties</span></span>
<span data-ttu-id="4bb6a-104">En Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], las propiedades promocionadas permiten que varios componentes de BizTalk Server tengan acceso a elementos de datos clave, conocidos en este contexto como campos distintivos y campos de propiedades que llegan dentro un mensaje de instancia sin que sea necesario saber cómo buscarlos dentro del propio mensaje.</span><span class="sxs-lookup"><span data-stu-id="4bb6a-104">In Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], promoted properties enable various BizTalk Server components to access key items of data, known in this context as distinguished fields and property fields that arrive within an instance message without needing to know how to look for them within the message itself.</span></span> <span data-ttu-id="4bb6a-105">Puede determinar qué elementos de datos deben promocionarse a un nivel más visible para los distintos tipos de mensajes.</span><span class="sxs-lookup"><span data-stu-id="4bb6a-105">For different types of messages, you can determine which items of data require promotion to a more visible level.</span></span> <span data-ttu-id="4bb6a-106">En función de cómo elija promocionar esos campos, puede que tenga que crear y definir un esquema de propiedades asociado.</span><span class="sxs-lookup"><span data-stu-id="4bb6a-106">Depending on how you choose to promote such fields, you may need to create and define an associated property schema.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4bb6a-107">Las propiedades promocionadas se restringen a atributos o elementos que no son de repetición.</span><span class="sxs-lookup"><span data-stu-id="4bb6a-107">Promoted properties are restricted to non-repeating elements/attributes.</span></span>  
  
 <span data-ttu-id="4bb6a-108">El acceso a los campos distintivos sólo se puede obtener desde las orquestaciones y estos campos no necesitan que se cree un esquema de propiedades correspondiente.</span><span class="sxs-lookup"><span data-stu-id="4bb6a-108">Distinguished fields are accessible only within orchestrations and do not require the creation of a corresponding property schema.</span></span> <span data-ttu-id="4bb6a-109">Si solamente tiene que tener acceso a los datos promocionados de un mensaje desde una orquestación, puede promocionar los datos como uno o más campos distintivos.</span><span class="sxs-lookup"><span data-stu-id="4bb6a-109">If you only need to access promoted message data from within an orchestration, you can promote the data as one or more distinguished fields.</span></span>  
  
 <span data-ttu-id="4bb6a-110">El acceso a los campos de propiedades se obtiene desde varios componentes de BizTalk Server, incluidas las canalizaciones y las orquestaciones.</span><span class="sxs-lookup"><span data-stu-id="4bb6a-110">Property fields are accessible from within various BizTalk Server components, including pipelines and orchestrations.</span></span> <span data-ttu-id="4bb6a-111">Los campos de propiedades también se pueden utilizar para el enrutamiento de mensajes.</span><span class="sxs-lookup"><span data-stu-id="4bb6a-111">Property fields can also be used for message routing.</span></span> <span data-ttu-id="4bb6a-112">Si necesita tener acceso a los datos promocionados de un mensaje desde contextos distintos a las orquestaciones, debe crear uno o más esquemas de propiedades para describir los datos que está promocionando.</span><span class="sxs-lookup"><span data-stu-id="4bb6a-112">If you need to access promoted message data from contexts other than within orchestrations, you must create one or more property schemas to describe the data you are promoting.</span></span>  
  
 <span data-ttu-id="4bb6a-113">Un esquema de propiedades es un esquema especial que el usuario asocia a un esquema de mensaje.</span><span class="sxs-lookup"><span data-stu-id="4bb6a-113">A property schema is a special schema that you associate with a message schema.</span></span> <span data-ttu-id="4bb6a-114">Se utiliza para promocionar valores específicos de un mensaje de instancia en el contexto de mensaje.</span><span class="sxs-lookup"><span data-stu-id="4bb6a-114">It is used for promoting specific values from within an instance message into the message context.</span></span> <span data-ttu-id="4bb6a-115">La promoción de propiedades ofrece un mecanismo centralizado de extraer bloques principales de información de un mensaje de instancia (los que defina el usuario) y facilitar notablemente su acceso a los componentes de BizTalk Server que manipulan el mensaje cuando éste pasa por BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="4bb6a-115">Property promotion provides a centralized mechanism for pulling key pieces of information that you define from within an instance message and making it more easily accessible to BizTalk Server components that are handling the message as it passes through BizTalk Server.</span></span>  
  
## <a name="create-property-schema-overview"></a><span data-ttu-id="4bb6a-116">Crear información general sobre el esquema de propiedad</span><span class="sxs-lookup"><span data-stu-id="4bb6a-116">Create property schema overview</span></span>
 <span data-ttu-id="4bb6a-117">Puede crear automáticamente un esquema de propiedades predeterminado mediante la característica Promoción rápida de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="4bb6a-117">You can automatically create a default property schema by using the quick promotion feature of BizTalk Server.</span></span> <span data-ttu-id="4bb6a-118">Ésta es la forma más sencilla de crear el esquema de propiedades necesario para la promoción de los campos de propiedades.</span><span class="sxs-lookup"><span data-stu-id="4bb6a-118">This is the easiest way to create the property schema required for property field promotion.</span></span> <span data-ttu-id="4bb6a-119">Para obtener más información acerca de cómo realizar promociones rápidas, vea [cómo copiar datos en el contexto del mensaje como campos de propiedades](../core/how-to-copy-data-to-the-message-context-as-property-fields.md).</span><span class="sxs-lookup"><span data-stu-id="4bb6a-119">For more information about how to perform quick promotions, see [How to Copy Data to the Message Context as Property Fields](../core/how-to-copy-data-to-the-message-context-as-property-fields.md).</span></span>  
  
 <span data-ttu-id="4bb6a-120">También puede crear el nuevo esquema de propiedad.</span><span class="sxs-lookup"><span data-stu-id="4bb6a-120">You can also create new property schema.</span></span> <span data-ttu-id="4bb6a-121">Cuando se abre un proyecto de BizTalk, seleccione el proyecto de BizTalk, el menú contextual y seleccione **agregar**, haga clic en **nuevo elemento**y, a continuación, haga clic en **esquema**.</span><span class="sxs-lookup"><span data-stu-id="4bb6a-121">When a BizTalk project is open, select the BizTalk project, right-click and select **Add**, click **New Item**, and then click **Schema**.</span></span>  
  
> [!NOTE]
>  - <span data-ttu-id="4bb6a-122">Si un esquema de propiedades está asociado a un esquema de mensaje, ambos esquemas deben estar en el mismo proyecto de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="4bb6a-122">If a property schema is associated with a message schema, then these two must be in the same BizTalk project.</span></span> <span data-ttu-id="4bb6a-123">No se admite separar el esquema de propiedades del esquema de mensaje asociado en distintos proyectos de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="4bb6a-123">Separating property schema from its associated message schema in different BizTalk projects is not supported.</span></span>  
>
>  - <span data-ttu-id="4bb6a-124">Si tiene dos esquemas de propiedades que tienen el mismo espacio de nombres, aunque se definan en ensamblados diferentes, los esquemas no se resolverán correctamente en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="4bb6a-124">If you have two property schemas that have the same namespace, even though they are defined in different assemblies, the schemas will not resolve properly at runtime.</span></span> <span data-ttu-id="4bb6a-125">Producirá un error de enrutamiento en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="4bb6a-125">You will get a routing failure at runtime.</span></span>  

## <a name="distinguished-fields-and-property-fields"></a><span data-ttu-id="4bb6a-126">Campos distintivos y campos de propiedades</span><span class="sxs-lookup"><span data-stu-id="4bb6a-126">Distinguished fields and property fields</span></span> 
 <span data-ttu-id="4bb6a-127">Hay dos tipos de promoción de propiedades: campos distintivos y campos de propiedades.</span><span class="sxs-lookup"><span data-stu-id="4bb6a-127">There are two types of property promotion: distinguished fields and property fields.</span></span> <span data-ttu-id="4bb6a-128">El último tipo utiliza esquemas de propiedades.</span><span class="sxs-lookup"><span data-stu-id="4bb6a-128">The latter type uses property schemas.</span></span> <span data-ttu-id="4bb6a-129">En el Editor de BizTalk, administra estos dos tipos de promoción de propiedades mediante la **promocionar propiedades** cuadro de diálogo, que puede tener acceso mediante el uso de la **promocionar propiedades** propiedad de la  **Esquema** nodo.</span><span class="sxs-lookup"><span data-stu-id="4bb6a-129">In BizTalk Editor, you manage both of these types of property promotion by using the **Promote Properties** dialog box, which you access by using the **Promote Properties** property of the **Schema** node.</span></span>  
  
> [!NOTE]
>  - <span data-ttu-id="4bb6a-130">Existen algunas restricciones en cuanto a los valores que puede promocionar.</span><span class="sxs-lookup"><span data-stu-id="4bb6a-130">There are some restrictions on values that you can promote.</span></span> <span data-ttu-id="4bb6a-131">Para obtener más información, vea la tabla de [promocionar propiedades](../core/promoting-properties.md).</span><span class="sxs-lookup"><span data-stu-id="4bb6a-131">For more information, see the table in [Promoting Properties](../core/promoting-properties.md).</span></span>  
>
>  - <span data-ttu-id="4bb6a-132">Los campos distintivos no aparecen en las expresiones de filtro.</span><span class="sxs-lookup"><span data-stu-id="4bb6a-132">Distinguished fields do not appear in filter expressions.</span></span> <span data-ttu-id="4bb6a-133">Únicamente aparecen campos de propiedades en las expresiones de filtro.</span><span class="sxs-lookup"><span data-stu-id="4bb6a-133">Only property fields appear in filter expressions.</span></span>  
  
 <span data-ttu-id="4bb6a-134">Los esquemas de propiedades son sencillos si se comparan con los esquemas de mensaje.</span><span class="sxs-lookup"><span data-stu-id="4bb6a-134">Property schemas are simple when compared to message schemas.</span></span> <span data-ttu-id="4bb6a-135">En el árbol de esquema, sólo se pueden insertar **elemento de campo** nodos como nodos secundarios inmediatos de la **esquema** nodo, crea una estructura que está dos niveles de profundidad.</span><span class="sxs-lookup"><span data-stu-id="4bb6a-135">In the schema tree, you are only allowed to insert **Field Element** nodes as immediate child nodes of the **Schema** node, creating a structure that is two levels deep.</span></span> <span data-ttu-id="4bb6a-136">En su mayor parte, establecer las propiedades de la **elemento de campo** nodos como se haría para **elemento de campo** nodos que aparecen en un esquema de mensaje.</span><span class="sxs-lookup"><span data-stu-id="4bb6a-136">For the most part, you set the properties of the **Field Element** nodes as you would for **Field Element** nodes appearing in a message schema.</span></span> <span data-ttu-id="4bb6a-137">Tiene no obstante una limitación: sólo puede utilizar tipos simples XSD.</span><span class="sxs-lookup"><span data-stu-id="4bb6a-137">You are limited to using only XSD simple types.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="4bb6a-138">No debe cambiar el nombre de ningún esquema que utilice otro esquema.</span><span class="sxs-lookup"><span data-stu-id="4bb6a-138">You should not rename any schema that is being used by another schema.</span></span> <span data-ttu-id="4bb6a-139">Esto incluye los esquemas de propiedades para los que ya se han establecido promociones.</span><span class="sxs-lookup"><span data-stu-id="4bb6a-139">This includes property schemas for which promotions have already been established.</span></span> <span data-ttu-id="4bb6a-140">Si lo hace, el esquema en uso no podrá encontrar el otro esquema porque el nombre que contiene ya no será exacto.</span><span class="sxs-lookup"><span data-stu-id="4bb6a-140">If you do so, the schema that is being used will not be able to find the other schema because the name it contains will no longer be accurate.</span></span>  
  
 <span data-ttu-id="4bb6a-141">El **Property Schema Base** es única para la propiedad **elemento de campo** nodos tal y como aparecen en los esquemas de propiedad.</span><span class="sxs-lookup"><span data-stu-id="4bb6a-141">The **Property Schema Base** property is unique to **Field Element** nodes as they appear in property schemas.</span></span> <span data-ttu-id="4bb6a-142">Esta propiedad está en blanco de forma predeterminada, pero se puede establecer en **MessageDataPropertyBase** o **MessageContextPropertyBase**, da lugar a un **propSchFieldBase** atributo se agrega a la **fieldInfo** elemento de anotación con uno u otro de estos valores.</span><span class="sxs-lookup"><span data-stu-id="4bb6a-142">This property is blank by default, but can be set to either **MessageDataPropertyBase** or **MessageContextPropertyBase**, resulting in a **propSchFieldBase** attribute being added to the **fieldInfo** annotation element with one or the other of these values.</span></span>  
  
 <span data-ttu-id="4bb6a-143">Cuando el **propSchFieldBase** atributo está establecido en **MessageDataPropertyBase**, significa que el valor de la propiedad promocionada se corresponde a los datos en el mensaje, como el valor de algún campo.</span><span class="sxs-lookup"><span data-stu-id="4bb6a-143">When the **propSchFieldBase** attribute is set to **MessageDataPropertyBase**, it means that the value of the promoted property corresponds to data in the message, such as the value of some field.</span></span> <span data-ttu-id="4bb6a-144">Cuando el **propSchFieldBase** atributo está establecido en **MessageContextPropertyBase**, significa que el valor de la propiedad promocionada puede ser de otro sitio, como un sobre, o que es posible establecer un componente de canalización.</span><span class="sxs-lookup"><span data-stu-id="4bb6a-144">When the **propSchFieldBase** attribute is set to **MessageContextPropertyBase**, it means that the value of the promoted property may be from somewhere else, such as an envelope, or that it may be set by a pipeline component.</span></span>  
  
 <span data-ttu-id="4bb6a-145">**Elemento de campo** nodos en esquemas de propiedades también tienen una propiedad denominada **información confidencial**, que cuando se establece en **Sí**, impide que el valor correspondiente sea visible desde dentro de El Explorador de BizTalk y el mensaje de evento e instancias de servicio de seguimiento, con lo que se conserva su naturaleza confidencial.</span><span class="sxs-lookup"><span data-stu-id="4bb6a-145">**Field Element** nodes in property schemas also have a property called **Sensitive Information**, which when set to **Yes**, will keep the corresponding value from being visible from within BizTalk Explorer and message event and service instance tracking, thereby preserving its sensitive nature.</span></span>  <span data-ttu-id="4bb6a-146">Vea **información confidencial** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)] para obtener más detalles.</span><span class="sxs-lookup"><span data-stu-id="4bb6a-146">See **Sensitive Information** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)] for more details.</span></span>
  
 <span data-ttu-id="4bb6a-147">La siguiente representación de un esquema de propiedades en el lenguaje de definición de esquemas XML (XSD) contiene una anotación asociada al elemento schema que identifica a este esquema como un esquema de propiedades (schema_type="property").</span><span class="sxs-lookup"><span data-stu-id="4bb6a-147">The following XML Schema definition (XSD) language representation of a property schema contains an annotation associated with the schema element that identifies this schema as a property schema (schema_type="property").</span></span> <span data-ttu-id="4bb6a-148">También incluye tres **elemento de campo** nodos subordinados el **esquema** nodo.</span><span class="sxs-lookup"><span data-stu-id="4bb6a-148">It also contains three **Field Element** nodes below the **Schema** node.</span></span> <span data-ttu-id="4bb6a-149">La primera **elemento de campo** nodo, denominado PromProp1, no tiene un valor definido para su **Property Schema Base** propiedad, pero los dos últimos **elemento de campo** nodos tienen que propiedad establecida en **MessageDataPropertyBase** y **MessageContextPropertyBase**, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="4bb6a-149">The first **Field Element** node, named PromProp1, does not have a value defined for its **Property Schema Base** property, but the latter two **Field Element** nodes have that property set to **MessageDataPropertyBase** and **MessageContextPropertyBase**, respectively.</span></span>  
  
```  
<?xml version="1.0" encoding="utf-16" ?>   
<xs:schema xmlns="http://BizTalk_Server_Project1.PropertySchema1"  
           xmlns:b="http://schemas.microsoft.com/BizTalk/2003"  
           targetNamespace="http://BizTalk_Server_Project1.PropertySchema1"  
           xmlns:xs="http://www.w3.org/2001/XMLSchema">  
    <xs:annotation>  
       <xs:appinfo>  
  
        </xs:appinfo>  
    </xs:annotation>  
    <xs:element name="" type="xs:string">  
        <xs:annotation>  
            <xs:appinfo>  
  
            </xs:appinfo>  
        </xs:annotation>  
    </xs:element>  
    <xs:element name="" type="xs:string">  
        <xs:annotation>  
            <xs:appinfo>  
  
            </xs:appinfo>  
        </xs:annotation>  
    </xs:element>  
    <xs:element name="" type="xs:string">  
        <xs:annotation>  
            <xs:appinfo>  
  
            </xs:appinfo>  
        </xs:annotation>  
    </xs:element>  
</xs:schema>  
  
```  
  
## <a name="see-also"></a><span data-ttu-id="4bb6a-150">Vea también</span><span class="sxs-lookup"><span data-stu-id="4bb6a-150">See Also</span></span>  
 [<span data-ttu-id="4bb6a-151">Diferentes tipos de esquemas de BizTalk</span><span class="sxs-lookup"><span data-stu-id="4bb6a-151">Different Types of BizTalk Schemas</span></span>](../core/different-types-of-biztalk-schemas.md)