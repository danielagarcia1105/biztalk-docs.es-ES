---
title: Los esquemas de mensajes para las funciones y procedimientos | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- functions and procedures, message structure of
- functions and procedures, message actions of
ms.assetid: 90b77b15-a4c6-487d-a09e-a078ceddfd1e
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0a821de5ac4a05165f33fa7035880d239bd6892b
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37008581"
---
# <a name="message-schemas-for-functions-and-procedures"></a>Esquemas de mensaje para funciones y procedimientos
El [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] funciones y procedimientos almacenados como operaciones de base de datos Oracle superficies. En esta sección se describe la estructura de mensaje y acciones que se usan para invocar funciones y procedimientos.  

## <a name="message-structure-of-functions-and-procedures"></a>Estructura de los mensajes de funciones y procedimientos  
 Las operaciones se exponen para las funciones y procedimientos almacenados siguen un patrón de intercambio de mensajes de solicitud y respuesta. En la tabla siguiente se muestra la estructura de estos mensajes de solicitud y respuesta.  

|Operación|Mensaje XML|Descripción|  
|---------------|-----------------|-----------------|  
|Solicitud de procedimiento almacenado|`<[SP_NAME] xmlns="http://Microsoft.LobServices.OracleDB/2007/03/[SCHEMA]/Procedure">   <[PRM1_NAME]>value1</[PRM1_NAME]>   <[PRM2_NAME]>value2</[PRM2_NAME]>   … </[SP_NAME]>`|Admite parámetros IN de Oracle y en espera en el cuerpo del mensaje|  
|Respuesta de procedimiento almacenado|`<[SP_NAME]Response xmlns="http://Microsoft.LobServices.OracleDB/2007/03/[SCHEMA]/Procedure">   <[PRM1_NAME]>value1<[PRM1_NAME]>   <[PRM2_NAME]>value2</[PRM2_NAME]>   … </[SP_NAME]Response>`|Admite los parámetros OUT de Oracle y en espera en el cuerpo del mensaje|  
|Solicitud de función|`<[FN_NAME] xmlns="http://Microsoft.LobServices.OracleDB/2007/03/[SCHEMA]/Function">   <[PRM1_NAME]>value1</[PRM1_NAME]>   <[PRM2_NAME]>value2</[PRM2_NAME]>   … </[FN_NAME]>`|Admite parámetros IN de Oracle y en espera en el cuerpo del mensaje|  
|Respuesta de la función|`<[FN_NAME]Response xmlns="http://Microsoft.LobServices.OracleDB/2007/03/[SCHEMA]/Function">   <[FN_NAME]Result>return_value</[FN_NAME]Result>   <[PRM1_NAME]>value1</[PRM1_NAME]>   <[PRM2_NAME]>value2</[PRM2_NAME]>   …    </[FN_NAME]Response>`|Admite los parámetros OUT de Oracle y en espera en el cuerpo del mensaje<br /><br /> - El valor devuelto de función se devuelve en el \<[fn_name especial] resultado\> elemento. Este es el primer elemento en el mensaje de respuesta. Viene antes que los parámetros.|  
|Procedimiento empaquetada o solicitud de función|`<[SP_NAME] xmlns="http://Microsoft.LobServices.OracleDB/2007/03/[SCHEMA]/Package/[PACKAGE_NAME]">   <[PRM1_NAME]>value1</[PRM1_NAME]>   <[PRM2_NAME]>value2</[PRM2_NAME]>   … </[SP_NAME]>`|Igual que la función o procedimiento almacenado|  
|Procedimiento empaquetada o respuesta de la función|`<[SP_NAME]Response xmlns="http://Microsoft.LobServices.OracleDB/2007/03/[SCHEMA]/Package/[PACKAGE_NAME]">   <[PRM1_NAME]>value1</[PRM1_NAME]>   <[PRM2_NAME]>value2</[PRM2_NAME]>   … </[SP_NAME]Response>`|Igual que la función o procedimiento almacenado|  

 [Esquema] = artefactos de la colección de Oracle; Por ejemplo, SCOTT.  

 [SP_NAME] = el procedimiento almacenado que se ejecutará; Por ejemplo, SP_INSERT.  

 [Fn_name especial] = la función que se ejecutará; Por ejemplo, FN_GETID.  

 [PRM1_NAME] = el nombre del parámetro de Oracle. Consulte la columna de descripción de direcciones de parámetros admitidos para cada mensaje.  

 [Nombre_del_paquete] = el nombre del paquete que contiene el destino del procedimiento o función.  

 La base de datos de Oracle admite la sobrecarga de funciones y procedimientos almacenados. El [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] es compatible con esta funcionalidad mediante la anexión de una cadena de sobrecarga para el espacio de nombres de destino para cada artefacto sobrecargado. El valor de esta cadena es "overload1" para la primera sobrecarga, "overload2" para la segunda sobrecarga y así sucesivamente. El ejemplo siguiente muestra la estructura del mensaje para dos procedimientos almacenados sobrecargados.  

```  
Stored Procedure Overload 1:  
<[SP_NAME] xmlns="http://Microsoft.LobServices.OracleDB/2007/03/[SCHEMA]/Package/[PACKAGE_NAME]/[SP_NAME]/overload1">    
  <[PRM1_NAME]>value1</[PRM1_NAME]>  
  <[PRM2_NAME]>value1</[PRM2_NAME]>  
  …  
</[SP_NAME]>  

Stored Procedure Overload 2:  
<[SP_NAME] xmlns="http://Microsoft.LobServices.OracleDB/2007/03/[SCHEMA]/Package/[PACKAGE_NAME]/[SP_NAME]/overload2">    
  <[PRM1_NAME]>value1</I_[PRM1_NAME]>  
  <[PRM2_NAME]>value1</I_[PRM2_NAME]>  
  …  
</[SP_NAME]>  
```  

## <a name="message-actions-of-functions-and-procedures"></a>Acciones de mensaje de funciones y procedimientos  
 El [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] usa las siguientes acciones de mensaje para las operaciones de función y procedimiento almacenadas.  


|               de mensaje                |                                              Acción                                              |                                          Ejemplo                                           |
|--------------------------------------|--------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------|
|       Solicitud de procedimiento almacenado       |            http://Microsoft.LobServices.OracleDB/2007/03/[SCHEMA]/Procedure/[SP_NAME]            |          http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Procedure/SP_INSERT           |
|      Respuesta de procedimiento almacenado       |       http://Microsoft.LobServices.OracleDB/2007/03/[esquema]/Procedure/[SP_NAME]/respuesta        |      http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Procedure/SP_INSERT/response      |
|           Solicitud de función           |            http://Microsoft.LobServices.OracleDB/2007/03/[fn_name especial]/Function/[esquema]             |           http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Function/FN_GETID            |
|          Respuesta de la función           |        http://Microsoft.LobServices.OracleDB/2007/03/[esquema]/Function/[fn_name especial] / respuesta        |       http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Function/FN_GETID/response       |
|  Solicitud de empaquetado de procedimiento almacenado   |     http://Microsoft.LobServices.OracleDB/2007/03/[SCHEMA]/Package/[PACKAGE_NAME]/[SP_NAME]      |       http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Package/CUSTOMER/SP_INSERT       |
|  Empaqueta la respuesta del procedimiento almacenado  | http://Microsoft.LobServices.OracleDB/2007/03/[SCHEMA]/Package/[PACKAGE_NAME]/[SP_NAME]/response |  http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Package/CUSTOMER/SP_INSERT/response   |
|      Solicitud de una función empaquetada       |     http://Microsoft.LobServices.OracleDB/2007/03/[SCHEMA]/Package/[PACKAGE_NAME]/[FN_NAME]      |       http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Package/CUSTOMER/FN_GETID        |
|      Respuesta de la función empaquetada      | http://Microsoft.LobServices.OracleDB/2007/03/[SCHEMA]/Package/[PACKAGE_NAME]/[FN_NAME]/response |   http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Package/CUSTOMER/FN_GETID/response   |
| Solicitud de procedimiento almacenado sobrecargado  |      http://Microsoft.LobServices.OracleDB/2007/03/[SCHEMA]/Procedure/[SP_NAME]/[OVERLOAD]       |     http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Procedure/SP_INSERT/overload1      |
| Sobrecargar un procedimiento almacenado respuesta |  http://Microsoft.LobServices.OracleDB/2007/03/[SCHEMA]/Procedure/[SP_NAME]/[OVERLOAD]/response  | http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Procedure/SP_INSERT/overload1/response |

 [Esquema] = artefactos de la colección de Oracle; Por ejemplo, SCOTT.  

 [SP_NAME] = el procedimiento almacenado que se ejecutará; Por ejemplo, SP_INSERT.  

 [Fn_name especial] = la función que se ejecutará; Por ejemplo, FN_GETID.  

 [Nombre_del_paquete] = el nombre del paquete que contiene el destino del procedimiento o función.  

 [SOBRECARGAR] = sobrecargar el parámetro. Los valores posibles son overload1, overload2 y así sucesivamente.  

## <a name="see-also"></a>Vea también  
 [Mensajes y esquemas de mensaje para el adaptador de BizTalk para la base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/messages-and-message-schemas-for-biztalk-adapter-for-oracle-database.md)