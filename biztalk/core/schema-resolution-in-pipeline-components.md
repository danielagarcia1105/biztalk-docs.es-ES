---
title: Resolución de esquemas en componentes de canalización | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- pipelines, schema resolution
- pipeline components, schema resolution
- schemas, pipeline components
ms.assetid: 35a79a6f-788b-4ca1-8483-36dcba5ae580
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c269ff3a7a5d973356754a222699c93179c90362
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36984789"
---
# <a name="schema-resolution-in-pipeline-components"></a>Resolución de esquemas en componentes de canalización
Los componentes de canalización de desensamblador y de ensamblador utilizan esquemas XSD para procesar los mensajes. Los esquemas contienen información, como la lista de propiedades promocionadas, campos distintivos, anotaciones para mensajes de archivo sin formato y anotaciones para sobres XML.  
  
 Los componentes estándar de desensamblador y de ensamblador admiten la recuperación de esquemas implementados mediante el nombre de tipo de esquema y el tipo de mensaje. Algunos componentes recuperan utilizando tanto el nombre de tipo de esquema como el tipo de mensaje, mientras que otros (por ejemplo, el desensamblador de archivo sin formato) recuperan únicamente por el tipo de esquema.  
  
 Los componentes de canalización que reciben mensajes XML determinan el tipo de mensaje examinando el espacio de nombres y el elemento raíz del mensaje. Por ejemplo, el tipo de mensaje para el siguiente código XML es "<http://MyDocument.org#MyDocument>".  
  
```  
<ns0:MyDocument xmlns:ns0="http://MyDocument.org">  
  
</ns0:MyDocument>  
```  
  
 Si un esquema no tiene un espacio de nombres definido para ella, el tipo de mensaje es "\<**rootNode**\>". Por ejemplo, si el anterior ejemplo XML no tuviera espacio de nombres, el tipo de mensaje sería "MyDocument".  
  
 Los componentes estándar de canalización utilizan el tipo de mensaje para recuperar el esquema apropiado de la base de datos. Las canalizaciones de recepción y de envío XML predeterminadas siempre determinan qué esquema cargar mediante el tipo de mensaje descubierto dinámicamente en tiempo de ejecución a partir del contenido XML del mensaje (a no ser que el componente de canalización esté establecido para permitir mensajes desconocidos). El desensamblador XML puede quitar el sobre del mensaje mediante este mecanismo; sin embargo, el ensamblador XML no puede crear un sobre para un mensaje saliente sin conocer qué esquema de sobres utilizar.  
  
 El esquema de sobres se especifica en las propiedades de configuración para el ensamblador XML en el Diseñador de canalizaciones.  
  
## <a name="how-schemas-are-resolved"></a>Cómo se resuelven esquemas  
 Suponiendo que no está especificando el esquema directamente en el XmlDisassembler, los esquemas se resolverán de la siguiente manera:  
  
1. En primer lugar, una búsqueda en los esquemas implementados no se realiza con el nombre del nodo raíz y el espacio de nombres (por ejemplo, http://MyNamespace#MyRoot). Si se encuentra una única coincidencia, se resuelve el esquema. Si se encuentran varias coincidencias que solo difieren en el número de versión y una está activa, se utiliza esa versión y se resuelve el esquema. Si el mismo esquema está activo en varias aplicaciones, se encontrarán varios esquemas activos y la búsqueda continuará en el paso 2.  
  
2. Si hay varias coincidencias que el paso 1 no se pueden resolver, la búsqueda está calificada por el ensamblado que se ejecuta la canalización. Si se encuentra un esquema único dentro del mismo ensamblado que se ejecuta la canalización, entonces se resuelve el esquema.  
  
3. Si no hay ninguna coincidencia, se utiliza el editor para resolver el esquema. La búsqueda se limita mediante el nodo raíz, el espacio de nombres y el token de clave pública. Si se encuentra un único esquema en esta búsqueda, se resuelve el esquema.  
  
4. No se puede resolver el esquema. Se devuelve un error que indica que no se encuentra ningún esquema único.  
  
   Para otras consideraciones, incluido el efecto de intercalación de SQL Server y las minúsculas en resolución de esquemas, vea [Namespace administración](../core/namespace-management.md).  
  
   Para crear un sobre en el ensamblador XML o un encabezado y un finalizador en el ensamblador de archivo sin formato, puede llevar a cabo alguna de las operaciones siguientes:  
  
- Cree una canalización de envío personalizada y especifique los esquemas para el sobre en las propiedades de configuración para el ensamblador XML. Esto se hace en el Diseñador de canalizaciones.  
  
- En la consola de administración de servidor BizTalk Server especifique XMLTransmit en un puerto de envío para la propiedad Canalización de envío. Haga clic en los puntos suspensivos para configurar las propiedades de canalización y especificar el esquema para el sobre en la propiedad EnvelopeDocSpecNames.  
  
  La resolución de esquemas mediante tipo de mensaje puede no funcionar si se implementan intencionada o accidentalmente varias versiones del mismo esquema en la base de datos (por ejemplo, en una implementación adyacente o si varios escenarios no tienen tipos de mensaje únicos). Si la resolución de esquemas mediante tipo de mensaje no se lleva cabo correctamente, se agrega un error de "ambigüedad de esquema" al registro de eventos. Para asegurarse de que la resolución de esquemas mediante tipo de mensaje funciona correctamente, realice una de las siguientes operaciones:  
  
- Defina los esquemas en el mismo proyecto de BizTalk que la canalización personalizada.  
  
- Firme el ensamblado con los esquemas con la misma clave que el ensamblado que contiene las canalizaciones.  
  
- Especifique de manera explícita esquemas en los componentes de canalización (los nombres de tipo de mensaje deben ser únicos en toda la base de datos de administración de BizTalk).  
  
> [!IMPORTANT]
>  Cuando esquemas del mismo ensamblado comparten un tipo de mensaje, no debe incluir los esquemas en el mismo ensamblado de componente de canalización por las limitaciones de resolución de ambigüedad; en vez de eso, haga referencia a los esquemas externos en el ensamblado de componente de canalización. La resolución de ambigüedad no funciona cuando los esquemas y los componentes de canalización están en el mismo ensamblado, incluso si los nombres de tipo de esquema se especifican explícitamente en los componentes de canalización en canalizaciones personalizadas.  
  
> [!NOTE]
>  Componentes de canalización personalizado que utilicen **IPipelineContext** obtener esquemas implementados debe obtener esquemas mediante tipo de esquema solo si no se especifica el nombre del tipo de esquema para el componente en tiempo de ejecución y obtener esquemas mediante tipo de mensaje solo Si la información de tipo de esquema no está disponible cuando se ejecuta el componente.  
  
## <a name="see-also"></a>Vea también  
 [Componentes de canalización](../core/pipeline-components.md)