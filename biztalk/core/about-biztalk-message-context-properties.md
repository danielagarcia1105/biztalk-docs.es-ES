---
title: Acerca de las propiedades de contexto de mensaje de BizTalk | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: bc700e43-a44c-482b-b91c-9f1d997a486a
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 49d802ad2ca50538c25182311c68604c26d5a832
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22225500"
---
# <a name="about-biztalk-message-context-properties"></a>Propiedades de contexto de mensaje de BizTalk
Cuando un adaptador de BizTalk Server recibe un documento, crea un mensaje de BizTalk para el documento. El mensaje de BizTalk contiene el documento recibido y un contexto de mensaje. El contexto de mensaje es un contenedor de varios proyectos que utiliza BizTalk Server al procesar el documento. Cada propiedad del contexto de mensaje se compone de tres elementos: un nombre, un espacio de nombres y un valor. Por ejemplo, la siguiente propiedad de contexto de mensaje describe el Id. de intercambio de un documento:  
  
```  
<Property Name="InterchangeID" Namespace="http://schemas.microsoft.com/BizTalk/2003/system-properties" Value="{AC07BF30-2F1A-42B0-8390-191EF38BA839}"/>  
```  
  
 Las propiedades de contexto de mensaje se agregan al contexto de mensaje durante el tiempo que el mensaje pasa a través de BizTalk Server.  
  
 BizTalk utiliza los dos tipos de propiedades de contexto de mensaje que se describen a continuación:  
  
## <a name="property-fields"></a>Campos de propiedades  
 Los campos de propiedades son propiedades de contexto de mensaje que utiliza el motor de mensajería de BizTalk con fines de enrutamiento de documentos, seguimiento de mensajes y evaluación de orquestaciones. Puede elevar explícitamente un campo en un documento en el contexto del mensaje como un campo de propiedad si edita el esquema del documento en el esquema de Editor de BizTalk Server que está disponible en [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]. Para escribir un campo de un documento en el contexto de mensaje como un campo de propiedad, el esquema de documento debe tener un esquema de propiedades asociado. Los campos de propiedades tienen una limitación de 255 caracteres. El **IsPromoted** propiedad de campos de propiedades en el contexto del mensaje está establecida en **True**.  
  
## <a name="distinguished-fields"></a>Campos distintivos  
 Los campos distintivos son propiedades de contexto de mensaje que no necesitan un esquema de propiedades independiente y a los que solamente se puede tener acceso desde las orquestaciones. Los campos distintivos no se pueden usar para enrutamiento ni seguimiento. Puesto que los campos distintivos no necesitan un esquema de propiedades independiente, la evaluación que realiza el motor de orquestaciones de este tipo de campos consume una menor sobrecarga que la de los campos de propiedades. La evaluación de los campos de propiedades requiere una consulta XPath, la evaluación de campos distintivos no requiere una consulta XPath ya que el desensamblador de canalizaciones rellena los campos distintivos en el contexto y el motor de orquestaciones lee los valores almacenados en la caché. Sin embargo, si el motor de orquestación no encuentra la propiedad en el contexto, iniciará una consulta de XPath para buscar el valor. Los campos distintivos no tienen una limitación de tamaño. El **IsPromoted** propiedad de campos distintivos en el contexto del mensaje está establecida en **False**.  
  
## <a name="summary-of-differences-between-property-fields-and-distinguished-fields"></a>Resumen de las diferencias entre los campos de propiedades y los campos distintivos  
 En la siguiente tabla se resumen las diferencias y similitudes entre los campos de propiedades y los campos distintivos:  
  
|**Atributo**|**Campo de propiedad**|**Campo distintivo**|  
|-------------------|------------------------|-----------------------------|  
|Propiedad IsPromoted|True|False|  
|Limitación de tamaño|255 caracteres|Sin límite|  
|Usado para enrutamiento|Sí|No|  
|Usado para seguimiento|Sí|No|  
|Usado en orquestaciones|Sí|Sí|  
|Requiere esquema de propiedades|Sí|No|  
|Accesible por canalizaciones y puertos|Sí|No|  
  
## <a name="see-also"></a>Vea también  
 [Formas de usar el contenido de mensaje para el procesamiento de mensajes de Control](../core/ways-to-use-message-content-to-control-message-processing.md)