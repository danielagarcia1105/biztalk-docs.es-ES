---
title: Esquemas de mensajes para el compuesto Operation1 | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 768473ef-da8d-4e58-86cb-597c28ded49c
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3b22861d36693ab3ef487e5e3d0b86544f048e95
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22215180"
---
# <a name="message-schemas-for-the-composite-operation"></a>Esquemas de mensaje para la operación de composición
El [!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)] permite ejecutar operaciones compuestas en Oracle E-Business Suite. Una operación compuesta puede contener varias operaciones y en cualquier orden. Para obtener información sobre qué operaciones pueden incluirse en una operación compuesta, consulte [compatibilidad para operaciones compuestas](../../adapters-and-accelerators/adapter-oracle-ebs/support-for-composite-operations2.md).  
  
 Para obtener información acerca de cómo realizar operaciones compuestas mediante la [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)], consulte [ejecutar operaciones compuestas en la base de datos de Oracle mediante BizTalk Server](../../adapters-and-accelerators/adapter-oracle-database/run-composite-operations-on-oracle-database-using-biztalk-server.md).  
  
## <a name="message-structure-for-the-composite-operation"></a>Estructura del mensaje para la operación de composición  
 Puesto que una operación compuesta contiene varias operaciones individuales; la estructura del mensaje de una operación compuesta contiene estructuras de mensajes de las operaciones individuales. El mensaje de operación compuesta sigue un patrón de intercambio de mensajes de solicitud y respuesta.  
  
 En la tabla siguiente muestra la estructura de los mensajes de solicitud y respuesta de una operación compuesta que contiene una operación de inserción, un procedimiento almacenado empaquetado que no tome ningún parámetros de entrada y una operación de eliminación.  
  
> [!NOTE]
>  Ver una descripción de la entidad después de la tabla.  
  
|Operación|Mensaje XML|  
|---------------|-----------------|  
|Solicitud de operación compuesta|`<?xml version="1.0" encoding="utf-8" ?> <Request xmlns="http://[PROJECT_NAME].[COMPOSITE_SCHEMA_NAME]">   <Insert xmlns="http://schemas.microsoft.com/OracleEBS/2008/05/Tables/[SCHEMA]/[TABLE_NAME]">     <Recordset>       <InsertRecord>         <[FIELD1_NAME]>[value1]</[FIELD1_NAME]>           <InLineValue>[value]</InlineValue>         <[FIELD2_NAME]>[value2]</[FIELD2_NAME]>           <InLineValue>[value]</InlineValue>         …       <InsertRecord>    </RECORDSET>   </Insert>   <[SP_NAME] xmlns="http://schemas.microsoft.com/OracleEBS/2008/05/PackageApis/[SCHEMA]/[APP_NAME]" />   <Delete xmlns="http://schemas.microsoft.com/OracleEBS/2008/05/Tables/[SCHEMA]/[TABLE_NAME]">     <FILTER>[WHERE_clause]</FILTER>   </Delete> </Request>`|  
|Respuesta de operación compuesta|`<?xml version="1.0" encoding="utf-8" ?>  <RequestResponse xmlns="http://[PROJECT_NAME].[COMPOSITE_SCHEMA_NAME]">   <InsertResponse xmlns="http://schemas.microsoft.com/OracleEBS/2008/05/Tables/[SCHEMA]/[TABLE_NAME]">     <InsertResult>[value]</InsertResult>    </InsertResponse>   <[SP_NAME]Response xmlns="http://schemas.microsoft.com/OracleEBS/2008/05/Procedures/[SCHEMA]">     <[PRM1_NAME]>value1<[PRM1_NAME]>     <[PRM2_NAME]>value2</[PRM2_NAME]>     …   </[SP_NAME]Response>    <DeleteResponse xmlns="http://schemas.microsoft.com/OracleEBS/2008/05/TableOp/[SCHEMA]/[TABLE_NAME]">     <DeleteResult>[value]</DeleteResult>    </DeleteResponse> </RequestResponse>`|  
  
 Descripciones de entidad:  
  
 [Nombre_proyecto] = nombre del proyecto de BizTalk que contiene el esquema de operación compuesta.  
  
 [COMPOSITE_SCHEMA_NAME] = nombre del esquema de operación compuesta proporcionado por el usuario.  
  
 [Esquema] = artefactos de la colección de Oracle; Por ejemplo, SCOTT.  
  
 [NombreTabla] = nombre de la tabla; Por ejemplo, el empleado.  
  
 [FIELD1_NAME] = nombre de campo de la tabla; Por ejemplo, el nombre.  
  
 [SP_NAME] = el procedimiento almacenado empaquetado que se ejecutará; Por ejemplo, ADD_EMP_DETAILS.  
  
 [APP_NAME] = nombre de la aplicación de Oracle que contiene el procedimiento almacenado empaquetado.  
  
 [PRM1_NAME] = el nombre del parámetro de Oracle en el procedimiento almacenado empaquetado.  
  
## <a name="message-action-for-the-composite-operation"></a>Acción de mensaje para la operación de composición  
 La acción de mensaje para la operación compuesta es "CompositeOperation."  
  
## <a name="see-also"></a>Vea también  
 [Mensajes y esquemas de mensaje para el adaptador de BizTalk para Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/messages-and-message-schemas-for-biztalk-adapter-for-oracle-e-business-suite.md)