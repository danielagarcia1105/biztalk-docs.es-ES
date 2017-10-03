---
title: Limitaciones al consultar y recuperar listas | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- JD Edwards OneWorld adapters, querying limitations
- querying, limitations [JD Edwards OneWorld adapters]
ms.assetid: 1b6f5d2a-d1e2-4c78-8f4a-f00d10f008b9
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0f2e0f813a793aa05756ef52925081375203f2f0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="limitations-when-querying-and-retrieving-lists"></a>Limitaciones cuando se realizan consultas y recuperaciones de listas
La arquitectura de comunicación JD Edwards OneWorld es una arquitectura de respuesta única de mensaje único. No puede devolver una lista de mensajes o una matriz. El código subyacente es C++, que llama con un puntero a una estructura única, realiza cambios en la estructura y, a continuación, se cierra.  
  
## <a name="querying-and-retrieving-lists"></a>Listas de consultas y recuperaciones  
 No puede realizar consultas y recuperaciones de listas de registros basados en criterios de búsqueda mediante el adaptador de Microsoft BizTalk para JD Edwards OneWorld debido a una limitación con la arquitectura de la función empresarial de JD Edwards OneWorld.  
  
 En JD Edwards OneWorld, se proporciona conectividad de base de datos mediante un conjunto de llamadas de función interna de propiedad (y compleja). Estas llamadas enmascaran la versión de base de datos subyacente mediante el requerimiento de llamadas muy explícitas y llamadas de bajo nivel para crear listas de columnas con el fin de recuperar o actualizar y crear estructuras especializadas para la ordenación o selección. Los conjuntos de API no se exponen mediante el método de conectividad de Java (o cualquier otro), sin embargo, los conjuntos de recursos no se pueden administrar a través de funciones empresariales.  
  
 Dentro del conjunto de herramientas de JD Edwards OneWorld, puede crear funciones empresariales que administran un único registro o funcionan en un grupo de registro, sin embargo, el acceso a las listas de productos fuera de las herramientas de JD Edwards One World es más complicado.  
  
 Para solucionar este problema, puede crear una función empresarial personalizada que devuelve una lista de claves de registro basada en una consulta. Debe segmentar las listas, debido a que JDENET (la API de mensajería de propietario interno de JD Edwards OneWorld) tienen una limitación en el tamaño del búfer de mensajes para administrar conjuntos de resultados sin enlazar o de gran tamaño. El código de cliente se debe repetir (bucle) a través de las llamadas sucesivas en la función empresarial hasta que se devuelva un indicador que indique que la lista se ha completado.  
  
## <a name="controlling-iteration"></a>Controlar iteración  
 Todas las llamadas a las funciones empresariales de JD Edwards OneWorld tiene instancias sin estado. Por lo tanto, la función empresarial no puede mantener un cursor abierto y devolver más filas en la solicitud. La colocación de la información se debe pasar a la función empresarial de JD Edwards OneWorld XE en cada llamada.  
  
 A continuación se encuentra una lista de técnicas para controlar la iteración:  
  
-   En la parte de JD Edwards OneWorld, escriba el conjunto de resultados en el archivo de almacenamiento temporal, que devuelve un Id. (como un nombre de archivo o un número de tarea) que pueden darse e en las sucesivas llamadas junto con el número de registro para colocar el cursor. Las sucesivas llamadas se colocan dentro de la lista basada en el número de registro que se ha pasado.  
  
    > [!NOTE]
    >  Las llamadas a través del adaptador de BizTalk para JD Edwards One World pueden tener equilibrio de carga, sin embargo, se proporcionan finalmente por un único servidor de aplicaciones que se basa en las credenciales y funciones empresariales que se van a invocar. Por lo tanto, si una llamada crea un archivo temporal en un servidor, las llamadas adicionales se sirven mediante el mismo servidor. Para obtener más información, vea la asignación de configuración de objetos en las guías de JD Edwards OneWorld CNC.  
  
-   La información de la colocación (como la del valor de clave primaria) puede devolverse en la segunda llamada y en las siguientes y la consulta puede volver a emitirse basando la clave como un parámetro adicional. Este método se utiliza en el código de exploración del repositorio para el adaptador de BizTalk para JD Edwards OneWorld.  
  
    > [!NOTE]
    >  De las primeras dos técnicas, el método recomendado utilizará los valores de la clave principal y volver a emitir la consulta. Este método requiere la cantidad mínima de código y sitúa la optimización y almacenamiento en caché de carga en la base de datos.  
  
-   La aplicación que realiza la llamada puede almacenar una lista de claves principales (como un referencia cruzada). Por ejemplo, si un sistema de administración de relaciones con los clientes (CRM) crea un registro de clientes y, a continuación, lo agrega a JD Edwards One World mediante la llamada de función empresarial, la función empresarial que agrega un registro de clientes establece el valor para el campo AN8 (número de dirección corta) y se visualiza en el búfer de retorno. Este número puede escribirse en un campo de referencia en el registro de cliente original o almacenarse en una tabla de referencia cruzada personalizada.  
  
-   La mayoría de todos los registros maestros en JD Edwards One World tienen un concepto de búsqueda o clave alternativa. Esta clave puede utilizarse para almacenar la información esencial del sistema de llamada. Las funciones empresariales pueden realizar la búsqueda en la parte de JD Edwards One World. Cuando los parámetros pasan a la función empresarial crean un registro de clientes, se establece el valor de clave larga.  
  
 Para obtener más información sobre estos conceptos, vea el tema de interoperabilidad en el sistema de ayuda de JD Edwards OneWorld.  
  
## <a name="see-also"></a>Vea también  
 [Planeamiento y arquitectura](../core/planning-and-architecture17.md)