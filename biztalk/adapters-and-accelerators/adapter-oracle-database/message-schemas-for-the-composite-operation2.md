---
title: Los esquemas de mensajes para la composición Operation2 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0164ea07-a373-430b-b569-3e29df1d081b
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 04ff8ec57d3c94e2191b1615593f0047e01b0e01
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36967997"
---
# <a name="message-schemas-for-the-composite-operation"></a>Esquemas de mensaje para la operación compuesta
El [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] le permite ejecutar operaciones compuestas en la base de datos de Oracle. Una operación compuesta puede contener varias operaciones y en cualquier orden. Para obtener información sobre qué operaciones se pueden incluir en una operación compuesta, consulte [ejecutar operaciones compuestas en la base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/run-composite-operations-in-oracle-database.md).  
  
 Para obtener información sobre cómo realizar operaciones compuestas mediante el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)], consulte [ejecutar operaciones compuestas en la base de datos de Oracle con BizTalk Server](../../adapters-and-accelerators/adapter-oracle-database/run-composite-operations-on-oracle-database-using-biztalk-server.md).  
  
## <a name="message-structure-for-the-composite-operation"></a>Estructura de mensaje para la operación compuesta  
 Dado que una operación compuesta contiene varias operaciones individuales; la estructura del mensaje de una operación compuesta contiene estructuras de mensajes de las operaciones individuales. El mensaje de operación compuesta sigue un patrón de intercambio de mensajes de solicitud y respuesta.  
  
 En la tabla siguiente se muestra la estructura de los mensajes de solicitud y respuesta de una operación compuesta que contiene una operación de inserción, un procedimiento almacenado empaquetado que no tome ningún parámetros de entrada y una operación de eliminación.  
  
|Operación|Mensaje XML|  
|---------------|-----------------|  
|Solicitud de operación compuesta|`<?xml version="1.0" encoding="utf-8" ?> <Request xmlns="http://[PROJECT_NAME].[COMPOSITE_SCHEMA_NAME]">   <Insert xmlns="[VERSION]/[SCHEMA]/Table/[TABLE_NAME]">     <RECORDSET>       <[TABLE_NAME]RECORDINSERT>         <[FIELD1_NAME]>[value1]</[FIELD1_NAME]>         <[FIELD2_NAME]>[value2]</[FIELD2_NAME]>         …       </[TABLE_NAME]RECORDINSERT>    </RECORDSET>   </Insert>   <[SP_NAME] xmlns="[VERSION]/[SCHEMA]/Procedure" />   <Delete xmlns="[VERSION]/[SCHEMA]/Table/[TABLE_NAME]">     <FILTER>[WHERE_clause]</FILTER>   </Delete> </Request>`|  
|Respuesta de operación compuesta|`<?xml version="1.0" encoding="utf-8" ?>  <RequestResponse xmlns="http://[PROJECT_NAME].[COMPOSITE_SCHEMA_NAME]">   <InsertResponse xmlns="[VERSION]/[SCHEMA]/Table/[TABLE_NAME]">     <InsertResult>[value]</InsertResult>    </InsertResponse>   <[SP_NAME]Response xmlns="[VERSION]/[SCHEMA]/Procedure">     <[PRM1_NAME]>value1<[PRM1_NAME]>     <[PRM2_NAME]>value2</[PRM2_NAME]>     …   </[SP_NAME]Response>    <DeleteResponse xmlns="[VERSION]/[SCHEMA]/Table/[TABLE_NAME]">     <DeleteResult>[value]</DeleteResult>    </DeleteResponse> </RequestResponse>`|  
  
 [Versión] = la cadena de versión de mensaje; Por ejemplo, http://Microsoft.LobServices.OracleDB/2007/03  
  
 [Nombre_proyecto] = nombre del proyecto de BizTalk que contiene el esquema de operación compuesta.  
  
 [COMPOSITE_SCHEMA_NAME] = nombre del esquema de operación compuesta por parte del usuario.  
  
 [Esquema] = artefactos de la colección de Oracle; Por ejemplo, SCOTT.  
  
 [NombreTabla] = nombre de la tabla; Por ejemplo, el empleado.  
  
 [FIELD1_NAME] = nombre de campo de tabla; Por ejemplo, el nombre.  
  
 [SP_NAME] = el procedimiento almacenado empaquetado para ejecutarse; Por ejemplo, ADD_EMP_DETAILS.  
  
 [PRM1_NAME] = el nombre del parámetro de Oracle en el procedimiento almacenado.  
  
## <a name="message-action-for-the-composite-operation"></a>Acción de mensaje para la operación compuesta  
 La acción de mensaje para la operación compuesta es"<http://Microsoft.LobServices.OracleDB/2007/03/CompositeOperation.”>  
  
## <a name="see-also"></a>Vea también  
 [Mensajes y esquemas de mensaje para el adaptador de BizTalk para la base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/messages-and-message-schemas-for-biztalk-adapter-for-oracle-database.md)