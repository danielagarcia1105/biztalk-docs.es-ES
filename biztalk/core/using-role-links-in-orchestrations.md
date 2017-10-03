---
title: "Usar vínculos de rol en orquestaciones | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- role links
- roles, links
- roles
- roles, about roles
- role links, about role links
- role links, properties
- role links, initializing
ms.assetid: 0cf85544-12c9-4541-8925-61a6e946cce0
caps.latest.revision: "20"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0e3c4e4a4c3a99fb6e1962299d440717eaa8d51b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="using-role-links-in-orchestrations"></a>Usar vínculos de rol en orquestaciones
Los vínculos de rol constituyen una abstracción de las interacciones entre la orquestación y sus socios comerciales. Los vínculos de rol permiten elegir de manera dinámica con qué socio comercial desea interactuar según la resolución de éste último, el contenido del mensaje o los resultados de una búsqueda en la base de datos, manteniendo intacto el proceso empresarial global.  
  
 Por ejemplo, en un escenario de negocio a negocio, existen varios compradores, un solo proveedor y varias agencias de envío para el proveedor. Cuando un comprador envía un pedido al proveedor, éste último sabe, gracias a la resolución de entidades, qué comprador envía el pedido, y puede aplicarle el descuento apropiado. Además, según los productos del pedido, el proveedor determina en tiempo de ejecución qué agencia de envío se encargará de la entrega. Aunque cada agencia de envío puede tener su propio protocolo de transporte, el proveedor puede usar el mismo proceso empresarial en tiempo de ejecución para controlar todas las agencias de envío y determinar con cuál de ellas desea interactuar. En una fase posterior, si una agencia de envío actualiza su protocolo de transporte, por ejemplo, de FTP a HTTP, el proveedor solo tendrá que usar el Explorador de BizTalk o la consola de administración de BizTalk Server para actualizar el puerto de envío asociado a esa Agencia de envío concreta. El proveedor no tendrá que modificar su proceso empresarial, que reside en la orquestación.  
  
## <a name="roles"></a>Roles  
 Existen dos roles en una orquestación:  
  
-   Un rol de "implementaciones" para recibir y procesar los mensajes. Este rol también se denomina el "proveedor".  
  
-   Un rol de "usos" para enviar los mensajes. Este rol también se denomina el "consumidor".  
  
## <a name="role-links"></a>Vínculos de función  
 Un vínculo de rol puede incluir un rol de consumidor o de proveedor, o uno de cada. Un rol de consumidor consume los servicios proporcionados por el rol de proveedor. Al definir un vínculo de rol con uno de estos roles, o con ambos, se asume que el socio comercial cumple el rol complementario con el que está estableciendo el enlace.  
  
 Un vínculo de función tiene un **SourceParty** propiedad, un **DestinationParty** propiedad y un rol de inicio. Un rol de inicio es el rol en el que se produce la primera comunicación y que, por tanto, inicia el vínculo de función estableciendo el valor de la **DestinationParty** propiedad.  
  
 Si el rol de inicio es un consumidor para enviar mensajes, se establece explícitamente el **DestinationParty** propiedad (una vez y solo una vez) en la orquestación. Para ello, establezca el valor de la **DestinationParty** en el **expresión** forma, como en el ejemplo siguiente, donde ConfirmOrder es el nombre de un vínculo de función, y PartnerName y OrganizationName son parámetros de una entidad:  
  
```  
ConfirmOrder(Microsoft.XLANGs.BaseTypes.DestinationParty) = new Microsoft.XLANGs.BaseTypes.Party("PartnerName", "OrganizationName");  
```  
  
 Si el rol de inicio es un proveedor para recibir mensajes, la **DestinationParty** propiedad se inicializa automáticamente por el receptor. El **DestinationParty** se establece en el proveedor. El **SourceParty** propiedad es de solo lectura y se proporciona a través de un componente de canalización de confianza para resolver el nombre de la entidad en función del identificador de seguridad (SID) del remitente o de un certificado asociado a la entidad. El host que ejecuta el componente de canalización debe marcarse como **autenticación de confianza**. Puede obtener el valor de la **SourceParty** en el **expresión** forma mediante el código de ejemplo siguiente:  
  
 `PartyName = Buyer_Supplier(Microsoft.XLANGs.BaseTypes.SourceParty);`  
  
## <a name="role-link-types"></a>Tipos de vínculo de rol  
 Un vínculo de rol es una instancia de un tipo de vínculo de rol que consta de uno o dos roles. Tenga en cuenta lo siguiente cuando trabaje con un tipo de vínculo de rol:  
  
-   solo puede hacer referencia una vez a un tipo de puerto concreto dentro de un tipo de vínculo de rol individual.  
  
-   Dado que una definición de tipo de vínculo de rol incluye tipos de puerto, el ámbito de un tipo de puerto debe incluir el de cualquier tipo de vínculo de rol que lo utilice.  
  
-   Cuando trabaje con los Servicios de la actividad de negocio (BAS), el esquema de parámetros estructurados deberá definirse en el mismo ensamblado de BizTalk que el tipo de vínculo de rol al que esté asociado. Puesto que el esquema está asociado al tipo de vínculo de rol, y no a los roles individuales que componen ese tipo de vínculo de rol, si las entidades que desempeñan los distintos roles comparten el ensamblado que contiene el tipo de vínculo de rol, ambas entidades verán los mismos esquemas de parámetros estructurados. Si las dos entidades usan el mismo tipo de vínculo de rol pero tienen que tener esquemas de parámetros estructurados distintos, deberá crearse un ensamblado diferente para cada entidad. El tipo de vínculo de rol deberá duplicarse en cada ensamblado.  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Cómo crear vínculos de rol en orquestaciones](../core/how-to-create-role-links-in-orchestrations.md)  
  
-   [Cómo usar la forma de vínculo de función](../core/how-to-use-the-role-link-shape.md)  
  
-   [Cómo usar al Asistente para vínculo de función](../core/how-to-use-the-role-link-wizard.md)  
  
## <a name="see-also"></a>Vea también  
 [Cómo configurar el componente de canalización de resolución de entidades](../core/how-to-configure-the-party-resolution-pipeline-component.md)   
 [Uso de puertos en orquestaciones](../core/using-ports-in-orchestrations.md)