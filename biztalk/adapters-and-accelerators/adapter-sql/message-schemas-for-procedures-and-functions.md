---
title: Esquemas de mensajes para los procedimientos y funciones | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4acfb29e-8774-4eb7-ba10-2dcb93d2b41a
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 374b4d3365ec3aaac86fb5004969cd4cc189271d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="message-schemas-for-procedures-and-functions"></a>Esquemas de mensaje para los procedimientos y funciones
El [!INCLUDE[adaptersql](../../includes/adaptersql-md.md)] superficies de SQL Server, escalares y procedimientos almacenados de la base de datos y funciones con valores como operaciones de tabla. Esta sección describe la estructura de los mensajes y acciones que se usan para invocar procedimientos y funciones.  
  
## <a name="message-structure-of-procedures-and-functions"></a>Estructura de mensaje de los procedimientos y funciones  
 Las operaciones se exhibe para procedimientos y funciones siguen un patrón de intercambio de mensajes de solicitud y respuesta. En la tabla siguiente se muestra la estructura de estos mensajes de solicitud y respuesta.  
  
|Operación|Mensaje XML|Description|  
|---------------|-----------------|-----------------|  
|Solicitud de procedimiento almacenado|`<[SP_NAME] xmlns="http://schemas.microsoft.com/Sql/2008/05/Procedures/[SCHEMA]">   <[PRM1_NAME]>value1</[PRM1_NAME]>   <[PRM2_NAME]>value2</[PRM2_NAME]>   … </[SP_NAME]>`|-|  
|Respuesta de procedimiento almacenado|`<[SP_NAME]Response xmlns="http://schemas.microsoft.com/Sql/2008/05/Procedures/[SCHEMA]">   <[SP_NAME]Result>      <DataSet>        <any>[Value]</any>       <any>[Value]</any>       …     </DataSet>   </[SP_NAME]Result>   <ReturnValue>[Value]</ReturnValue> </[SP_NAME]Response>`|El valor devuelto de un procedimiento almacenado es una matriz de conjunto de datos.|  
|Inflexible solicitud de procedimiento almacenado|`<[STRNG_SP_NAME] xmlns="http://schemas.microsoft.com/Sql/2008/05/TypedProcedures/[SCHEMA]">   <[PRM1_NAME]>value1<[PRM1_NAME]>   <[PRM2_NAME]>value2</[PRM2_NAME]>   … </[STRNG_SP_NAME]>`|-|  
|Respuesta de procedimiento almacenado fuertemente tipados|`<[STRNG_SP_NAME]Response xmlns="http://schemas.microsoft.com/Sql/2008/05/TypedProcedures/[SCHEMA]">     <StoredProcedureResultSet0>          <StoredProcedureResultSet0 xmlns:ns1="http://schemas.microsoft.com/Sql/2008/05/ProcedureResultSets/[SCHEMA]/[STRNG_SP_NAME]">               <[PRM1_NAME]>value1<[PRM1_NAME]>               <[PRM2_NAME]>value2</[PRM2_NAME]>               …         </StoredProcedureResultSet0>     </StoredProcedureResultSet0>    <ReturnValue>[Value]</ReturnValue> </[STRNG_SP_NAME]Response>`|El valor devuelto de un procedimiento almacenado fuertemente tipado es una matriz de datos fuertemente tipados.|  
|Solicitud de una función escalar|`<[SCLR_FN_NAME] xmlns="http://schemas.microsoft.com/Sql/2008/05/ScalarFunctions/[SCHEMA]">   <[PRM_NAME]>value</[PRM_NAME]> </[SCLR_FN_NAME]>`|-|  
|Respuesta de la función escalar|`<[SCLR_FN_NAME]Response xmlns="http://schemas.microsoft.com/Sql/2008/05/ScalarFunctions/[SCHEMA]">   <[SCLR_FN_NAME]Result>return_value</[SCLR_FN_NAME]Result>   <[PRM_NAME]>value</[PRM_NAME]>   </[SCLR_FN_NAME]Response>`|-|  
|Solicitud de la función con valores de tabla|`<[TBL_FN_NAME] xmlns="http://schemas.microsoft.com/Sql/2008/05/TableValuedFunctions/[SCHEMA]">   <[PRM1_NAME]>value1</[PRM1_NAME]>   <[PRM2_NAME]>value2</[PRM2_NAME]>   … </[TBL_FN_NAME]>`|-|  
|Respuesta de la función con valores de tabla|`<[TBL_FN_NAME]Response xmlns="http://schemas.microsoft.com/Sql/2008/05/TableValuedFunctions/[SCHEMA]">   <[TBL_FN_NAME]Result>      <[TBL_FN_NAME] xmlns="http://schemas.microsoft.com/Sql/2008/05/TableValuedFunctions/[SCHEMA]">         <[PRM1_NAME]>value1</[PRM1_NAME]>         <[PRM2_NAME]>value2</[PRM2_NAME]>         ...      </[TBL_FN_NAME]">        ...      </[TBL_FN_NAME]Result> </[TBL_FN_NAME]Response>`||  
  
 [Esquema] = artefactos de la colección de SQL Server; Por ejemplo, dbo.  
  
 [SP_NAME] = el procedimiento almacenado que se ejecutará; Por ejemplo, ADD_EMP_DETAILS.  
  
 [STRNG_SP_NAME] = el procedimiento almacenado fuertemente tipado para ejecutarse; Por ejemplo, GET_EMP_DETAILS.  
  
 [SCLR_FN_NAME] = la función escalar a ejecutarse; Por ejemplo, GET_EMP_ID.  
  
 [TBL_FN_NAME] = la función con valores de tabla que se ejecutará; Por ejemplo, TVF_EMPLOYEE.  
  
 [PRM_NAME] = el nombre del parámetro de SQL Server.  
  
## <a name="message-actions-of-functions-and-procedures"></a>Acciones de mensaje de funciones y procedimientos  
 El [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] usa las siguientes acciones de mensaje para las operaciones de procedimiento y la función almacenadas.  
  
|de mensaje|Acción|Ejemplo|  
|-------------|------------|-------------|  
|Solicitud de procedimiento almacenado|Procedimiento / [esquema] / [SP_NAME]|Procedimiento/dbo/ADD_EMP_DETAILS|  
|Respuesta de procedimiento almacenado|Procedimiento / [esquema] / [SP_NAME] / respuesta|Procedimiento/dbo/ADD_EMP_DETAILS/respuesta|  
|Inflexible solicitud de procedimiento almacenado|TypedProcedure / [esquema] / [STRNG_SP_NAME]|TypedProcedure/dbo/GET_EMP_DETAILS|  
|Respuesta de procedimiento almacenado fuertemente tipados|TypedProcedure / [esquema] / [STRNG_SP_NAME] / respuesta|TypedProcedure/dbo/GET_EMP_DETAILS/respuesta|  
|PARA XML almacena la solicitud de procedimiento|XmlProcedure / [esquema] / [SP_NAME]|XmlProcedure/dbo/GET_EMP_DETAILS_FOR_XML|  
|PARA XML almacenados respuesta de procedimiento|XmlProcedure / [esquema] / [SP_NAME] / resp.|XmlProcedure/dbo/GET_EMP_DETAILS_FOR_XML/respuesta|  
|Solicitud de una función escalar|ScalarFunction / [esquema] / [SCLR_FN_NAME]|ScalarFunction/dbo/GET_EMP_ID|  
|Respuesta de la función escalar|ScalarFunction / [esquema] / [SCLR_FN_NAME] / respuesta|ScalarFunction/dbo/GET_EMP_ID/respuesta|  
|Solicitud de la función con valores de tabla|TableFunction / [esquema] / [TBL_FN_NAME]|TableFunction/dbo/TVF_EMPLOYEE|  
|Respuesta de la función con valores de tabla|TableFunction / [esquema] / [TBL_FN_NAME] / respuesta|TableFunction/dbo/TVF_EMPLOYEE/respuesta|  
  
 [SP_NAME] = el procedimiento almacenado que se ejecutará; Por ejemplo, ADD_EMP_DETAILS.  
  
 [STRNG_SP_NAME] = el procedimiento almacenado fuertemente tipado para ejecutarse; Por ejemplo, GET_EMP_DETAILS.  
  
 [SCLR_FN_NAME] = la función escalar a ejecutarse; Por ejemplo, GET_EMP_ID.  
  
 [TBL_FN_NAME] = el nombre de la función con valores de tabla que se ejecutará; Por ejemplo, TVF_EMPLOYEE.  
  
## <a name="see-also"></a>Vea también  
 [Mensajes y esquemas de mensaje para el adaptador de BizTalk para SQL Server](../../adapters-and-accelerators/adapter-sql/messages-and-message-schemas-for-biztalk-adapter-for-sql-server.md)