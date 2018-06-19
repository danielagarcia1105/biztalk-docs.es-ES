---
title: Esquemas de mensajes para el sondeo Operations2 | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- POLLINGSTMT operation, message actions for
- POLLINGSTMT operation, message structure for
ms.assetid: b82edcc2-9437-4c7b-ba2b-7b966fff3f15
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: beb28e7b769c16f1798023adb8b30c3e636a3407
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22214604"
---
# <a name="message-schemas-for-the-polling-operations"></a>Esquemas de mensaje para las operaciones de sondeo
La [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] expone varias operaciones de entrada relacionadas para sondeo según el objeto de destino en la base de datos de Oracle. Para sondear las tablas y vistas, aparece una sola operación POLLINGSTMT mientras que cada procedimiento almacenado, las funciones y empaquetados procedimientos y funciones se exponen como operaciones de entrada para el sondeo.  
  
 Puede especificar un **PollingId** parámetro en la cadena de consulta del URI para calificar el espacio de nombres de la operación de POLLINGSTMT de conexión. Establecer este parámetro califica solo el espacio de nombres de la operación de POLLINGSTMT; no cambia la acción de mensaje. Para obtener más información sobre el URI de conexión de adaptador de base de datos de Oracle, vea [crear el URI de conexión de base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/create-the-oracle-database-connection-uri.md).  
  
 Configurar las operaciones de sondeo estableciendo las propiedades de enlace el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]. Para obtener más información acerca de estas propiedades de enlace, vea [leer acerca de las propiedades de enlace del adaptador de base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/read-about-the-oracle-database-adapter-binding-properties.md). Establece el **PollingStatement** enlace de propiedad para especificar una instrucción SQL, procedimiento almacenado, función o un procedimiento dentro de un paquete para la consulta de sondeo. El conjunto de resultados de esta consulta se devuelve como datos en el código en la operación de sondeo.  
  
## <a name="message-structure-for-the-polling-operations"></a>Estructura de los mensajes para las operaciones de sondeo  
 En la tabla siguiente se muestra la estructura del mensaje XML para las distintas operaciones de sondeo.  
  
|Operación|Objeto de destino|Mensaje XML|Description|  
|---------------|-------------------|-----------------|-----------------|  
|POLLINGSTMT|-Tablas<br /><br /> -Vistas|`<?xml version="1.0" encoding="utf-8" ?>  <POLLINGSTMT xmlns="[VERSION]/POLLINGSTMT[POLLING_ID]">   <POLLINGSTMTRECORD>     <POLLINGSTMTRECORD>       <FIELD1_NAME>val1</FIELD1_NAME>        <FIELD2_NAME>val2</FIELD2_NAME>       …     </POLLINGSTMTRECORD>      …    </POLLINGSTMTRECORD> </POLLINGSTMT>`|La estructura del contenido en los tipos POLLINGSTMTRECORD de conjunto de resultados se determina por los metadatos que expone el adaptador para la consulta SELECT de SQL.<br /><br /> El espacio de nombres de la operación de POLLINGSTMT se determina por el parámetro PollingId en el URI de conexión.|  
|[CustomPollingOperation]|-Procedimientos<br /><br /> : Funciones<br /><br /> -Paquetes|**Procedimientos almacenados**<br /><br /> `<?xml version="1.0" encoding="utf-8" ?>  <[CustomPollingOperation] xmlns="[Version]/[SCHEMA]/PollingProcedure">    <[CustomPollingOperation]Result>      <PRM1>[Value]</PRM1>      <PRM2>[Value]</PRM2>      …    </[CustomPollingOperation]Result> </[CustomPollingOperation]>`<br /><br /> **Funciones**<br /><br /> `<?xml version="1.0" encoding="utf-8" ?> <[CustomPollingOperation] xmlns="[Version]/[Schema]/PollingFunction">    <[CustomPollingOperation]Result>      <COL1>[Value]</COL1]>      <COL2>[Value]</COL2>      …    </[CustomPollingOperation]Result> </[CustomPollingOperation]>`<br /><br /> **Paquetes**<br /><br /> `<?xml version="1.0" encoding="utf-8" ?>  <[CustomPollingOperation] xmlns="[Version]/[Schema]/PollingPackage/[PACKAGE_NAME]/">    <[CustomPollingOperation]Result>[Value]</[CustomPollingOperation]Result> </[CustomPollingOperation]>`|La estructura del conjunto en la operación de sondeo de resultados se determina por el tipo de datos de los elementos en el objeto de destino.|  
  
 [Versión] = http://Microsoft.LobServices.OracleDB/2007/03.  
  
 [CustomPollingOperation] = es el mismo que el procedimiento almacenado, función o procedimiento empaquetada o nombre de la función que se exponen como la operación de entrada de sondeo.  
  
 [Esquema] = nombre del esquema de Oracle. Por ejemplo, SCOTT.  
  
## <a name="see-also"></a>Vea también  
 [Mensajes y esquemas de mensaje para el adaptador de BizTalk para base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/messages-and-message-schemas-for-biztalk-adapter-for-oracle-database.md)