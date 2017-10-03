---
title: Esquemas de mensajes para operaciones compuestas | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d80c023b-1912-43d4-be29-eb9e1b323593
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b89c354baea2ddb46abf549752dc09699b9c9695
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="message-schemas-for-composite-operations"></a>Esquemas de mensaje para operaciones compuestas
El [!INCLUDE[adaptersql](../../includes/adaptersql-md.md)] permite ejecutar operaciones compuestas en la base de datos de SQL Server. Una operación compuesta puede contener varias operaciones, incluida la inserción, actualización y eliminar operaciones en las tablas y vistas y las operaciones en los procedimientos almacenados. Una operación compuesta puede incluir estas operaciones en cualquier orden.  
  
 Para obtener más información acerca de:  
  
-   Operaciones compuestas, consulte [compatibilidad para operaciones compuestas](../../adapters-and-accelerators/adapter-oracle-ebs/support-for-composite-operations2.md).  
  
-   Cómo realizar operaciones compuestas mediante la [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)], consulte [ejecutar operaciones compuestas en SQL Server mediante el adaptador de SQL](../../adapters-and-accelerators/adapter-sql/run-composite-operations-in-sql-server-using-the-sql-adapter.md).  
  
## <a name="message-structure-for-the-composite-operation"></a>Estructura del mensaje para la operación de composición  
 Puesto que una operación compuesta contiene varias operaciones individuales; la estructura del mensaje de una operación compuesta contiene estructuras de mensajes de las operaciones individuales. Como una operación compuesta contiene operaciones en tablas, vistas y procedimientos almacenados, el mensaje de operación compuesta sigue un patrón de intercambio de mensajes de solicitud y respuesta.  
  
 En la tabla siguiente muestra la estructura de los mensajes de solicitud y respuesta de una operación compuesta que contiene una operación de inserción, un procedimiento almacenado que no tome ningún parámetros de entrada y una operación de eliminación.  
  
|Operación|Mensaje XML|  
|---------------|-----------------|  
|Solicitud de operación compuesta|`<?xml version="1.0" encoding="utf-8" ?> <Request xmlns="http://[PROJECT_NAME].[COMPOSITE_SCHEMA_NAME]">   <Insert xmlns="http://schemas.microsoft.com/Sql/2008/05/TableOp/[SCHEMA]/[TABLE_NAME]">     <Rows>       <[TABLE_NAME]>         <[FIELD1_NAME]>[Value1]</[FIELD1_NAME]>         <[FIELD2_NAME]>[Value1]</[FIELD2_NAME]>         …       </[TABLE_NAME]>     </Rows>   </Insert>   <[SP_NAME] xmlns="http://schemas.microsoft.com/Sql/2008/05/Procedures/[SCHEMA]" />   <Delete xmlns="http://schemas.microsoft.com/Sql/2008/05/TableOp/[SCHEMA]/[TABLE_NAME]">     <Rows>       <[TABLE_NAME]>         <[FIELD1_NAME]>[Value1]</[FIELD1_NAME]>       </[TABLE_NAME]>     </Rows>   </Delete> </Request>`|  
|Respuesta de operación compuesta|`<?xml version="1.0" encoding="utf-8" ?>  <RequestResponse xmlns="http://[PROJECT_NAME].[COMPOSITE_SCHEMA_NAME]">   <InsertResponse xmlns="http://schemas.microsoft.com/Sql/2008/05/TableOp/[SCHEMA]/[TABLE_NAME]">     <InsertResult>       <long>[value]</long>      </InsertResult>   </InsertResponse>   <[SP_NAME]Response xmlns="http://schemas.microsoft.com/Sql/2008/05/Procedures/[SCHEMA]">     <[SP_NAME]Result>       <DataSet>         <any>[Value]</any>          <any>[Value]</any>          …       </DataSet>     </[SP_NAME]Result>     <ReturnValue>[value]</ReturnValue>    </[SP_NAME]Response>   <DeleteResponse xmlns="http://schemas.microsoft.com/Sql/2008/05/TableOp/[SCHEMA]/[TABLE_NAME]">     <DeleteResult>[value]</DeleteResult>    </DeleteResponse> </RequestResponse>`|  
  
 [Nombre_proyecto] = nombre del proyecto de BizTalk que contiene el esquema de operación compuesta.  
  
 [COMPOSITE_SCHEMA_NAME] = nombre del esquema de operación compuesta proporcionado por el usuario.  
  
 [Esquema] = artefactos de la colección de SQL Server; Por ejemplo, dbo.  
  
 [NombreTabla] = nombre de la tabla; Por ejemplo, el empleado.  
  
 [FIELD1_NAME] = nombre de campo de la tabla; Por ejemplo, el nombre.  
  
 [SP_NAME] = el procedimiento almacenado que se ejecutará; Por ejemplo, ADD_EMP_DETAILS.  
  
## <a name="message-action-for-the-composite-operation"></a>Acción de mensaje para la operación de composición  
 La acción de mensaje para la operación compuesta es "CompositeOperation."  
  
## <a name="see-also"></a>Vea también  
 [Mensajes y esquemas de mensaje para el adaptador de BizTalk para SQL Server](../../adapters-and-accelerators/adapter-sql/messages-and-message-schemas-for-biztalk-adapter-for-sql-server.md)