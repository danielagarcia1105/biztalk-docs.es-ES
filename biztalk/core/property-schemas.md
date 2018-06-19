---
title: Esquemas de propiedad | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8018bb72-a037-4eeb-bbbe-dd0cc6209aec
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d2fb50536b2521e77994baf0b6457206614b7eed
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22270044"
---
# <a name="property-schemas"></a>Esquemas de propiedades

## <a name="promoted-properties"></a>Propiedades promocionadas
En Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], las propiedades promocionadas permiten que varios componentes de BizTalk Server tengan acceso a elementos de datos clave, conocidos en este contexto como campos distintivos y campos de propiedades que llegan dentro un mensaje de instancia sin que sea necesario saber cómo buscarlos dentro del propio mensaje. Puede determinar qué elementos de datos deben promocionarse a un nivel más visible para los distintos tipos de mensajes. En función de cómo elija promocionar esos campos, puede que tenga que crear y definir un esquema de propiedades asociado.  
  
> [!NOTE]
>  Las propiedades promocionadas se restringen a atributos o elementos que no son de repetición.  
  
 El acceso a los campos distintivos sólo se puede obtener desde las orquestaciones y estos campos no necesitan que se cree un esquema de propiedades correspondiente. Si solamente tiene que tener acceso a los datos promocionados de un mensaje desde una orquestación, puede promocionar los datos como uno o más campos distintivos.  
  
 El acceso a los campos de propiedades se obtiene desde varios componentes de BizTalk Server, incluidas las canalizaciones y las orquestaciones. Los campos de propiedades también se pueden utilizar para el enrutamiento de mensajes. Si necesita tener acceso a los datos promocionados de un mensaje desde contextos distintos a las orquestaciones, debe crear uno o más esquemas de propiedades para describir los datos que está promocionando.  
  
 Un esquema de propiedades es un esquema especial que el usuario asocia a un esquema de mensaje. Se utiliza para promocionar valores específicos de un mensaje de instancia en el contexto de mensaje. La promoción de propiedades ofrece un mecanismo centralizado de extraer bloques principales de información de un mensaje de instancia (los que defina el usuario) y facilitar notablemente su acceso a los componentes de BizTalk Server que manipulan el mensaje cuando éste pasa por BizTalk Server.  
  
## <a name="create-property-schema-overview"></a>Crear información general sobre el esquema de propiedad
 Puede crear automáticamente un esquema de propiedades predeterminado mediante la característica Promoción rápida de BizTalk Server. Ésta es la forma más sencilla de crear el esquema de propiedades necesario para la promoción de los campos de propiedades. Para obtener más información acerca de cómo realizar promociones rápidas, vea [cómo copiar datos en el contexto del mensaje como campos de propiedades](../core/how-to-copy-data-to-the-message-context-as-property-fields.md).  
  
 También puede crear el nuevo esquema de propiedad. Cuando se abre un proyecto de BizTalk, seleccione el proyecto de BizTalk, el menú contextual y seleccione **agregar**, haga clic en **nuevo elemento**y, a continuación, haga clic en **esquema**.  
  
> [!NOTE]
>  - Si un esquema de propiedades está asociado a un esquema de mensaje, ambos esquemas deben estar en el mismo proyecto de BizTalk. No se admite separar el esquema de propiedades del esquema de mensaje asociado en distintos proyectos de BizTalk.  
>
>  - Si tiene dos esquemas de propiedades que tienen el mismo espacio de nombres, aunque se definan en ensamblados diferentes, los esquemas no se resolverán correctamente en tiempo de ejecución. Producirá un error de enrutamiento en tiempo de ejecución.  

## <a name="distinguished-fields-and-property-fields"></a>Campos distintivos y campos de propiedades 
 Hay dos tipos de promoción de propiedades: campos distintivos y campos de propiedades. El último tipo utiliza esquemas de propiedades. En el Editor de BizTalk, administra estos dos tipos de promoción de propiedades mediante la **promocionar propiedades** cuadro de diálogo, que puede tener acceso mediante el uso de la **promocionar propiedades** propiedad de la  **Esquema** nodo.  
  
> [!NOTE]
>  - Existen algunas restricciones en cuanto a los valores que puede promocionar. Para obtener más información, vea la tabla de [promocionar propiedades](../core/promoting-properties.md).  
>
>  - Los campos distintivos no aparecen en las expresiones de filtro. Únicamente aparecen campos de propiedades en las expresiones de filtro.  
  
 Los esquemas de propiedades son sencillos si se comparan con los esquemas de mensaje. En el árbol de esquema, sólo se pueden insertar **elemento de campo** nodos como nodos secundarios inmediatos de la **esquema** nodo, crea una estructura que está dos niveles de profundidad. En su mayor parte, establecer las propiedades de la **elemento de campo** nodos como se haría para **elemento de campo** nodos que aparecen en un esquema de mensaje. Tiene no obstante una limitación: sólo puede utilizar tipos simples XSD.  
  
> [!IMPORTANT]
>  No debe cambiar el nombre de ningún esquema que utilice otro esquema. Esto incluye los esquemas de propiedades para los que ya se han establecido promociones. Si lo hace, el esquema en uso no podrá encontrar el otro esquema porque el nombre que contiene ya no será exacto.  
  
 El **Property Schema Base** es única para la propiedad **elemento de campo** nodos tal y como aparecen en los esquemas de propiedad. Esta propiedad está en blanco de forma predeterminada, pero se puede establecer en **MessageDataPropertyBase** o **MessageContextPropertyBase**, da lugar a un **propSchFieldBase** atributo se agrega a la **fieldInfo** elemento de anotación con uno u otro de estos valores.  
  
 Cuando el **propSchFieldBase** atributo está establecido en **MessageDataPropertyBase**, significa que el valor de la propiedad promocionada se corresponde a los datos en el mensaje, como el valor de algún campo. Cuando el **propSchFieldBase** atributo está establecido en **MessageContextPropertyBase**, significa que el valor de la propiedad promocionada puede ser de otro sitio, como un sobre, o que es posible establecer un componente de canalización.  
  
 **Elemento de campo** nodos en esquemas de propiedades también tienen una propiedad denominada **información confidencial**, que cuando se establece en **Sí**, impide que el valor correspondiente sea visible desde dentro de El Explorador de BizTalk y el mensaje de evento e instancias de servicio de seguimiento, con lo que se conserva su naturaleza confidencial.  Vea **información confidencial** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)] para obtener más detalles.
  
 La siguiente representación de un esquema de propiedades en el lenguaje de definición de esquemas XML (XSD) contiene una anotación asociada al elemento schema que identifica a este esquema como un esquema de propiedades (schema_type="property"). También incluye tres **elemento de campo** nodos subordinados el **esquema** nodo. La primera **elemento de campo** nodo, denominado PromProp1, no tiene un valor definido para su **Property Schema Base** propiedad, pero los dos últimos **elemento de campo** nodos tienen que propiedad establecida en **MessageDataPropertyBase** y **MessageContextPropertyBase**, respectivamente.  
  
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
  
## <a name="see-also"></a>Vea también  
 [Diferentes tipos de esquemas de BizTalk](../core/different-types-of-biztalk-schemas.md)