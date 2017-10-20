---
title: Esquemas de mensajes para las funciones y procedimientos | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- functions and procedures, message structure of
- functions and procedures, message actions of
ms.assetid: 90b77b15-a4c6-487d-a09e-a078ceddfd1e
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 85585945ae6376e11ddc39e7a1280f69d024c439
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="message-schemas-for-functions-and-procedures"></a>Esquemas de mensaje para funciones y procedimientos
El [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] funciones y procedimientos almacenados como operaciones de base de datos superficies de Oracle. Esta sección describe la estructura de los mensajes y acciones que se usan para invocar funciones y procedimientos.  
  
## <a name="message-structure-of-functions-and-procedures"></a>Estructura de los mensajes de funciones y procedimientos  
 Las operaciones se exhibe para funciones y procedimientos almacenados siguen un patrón de intercambio de mensajes de solicitud y respuesta. En la tabla siguiente se muestra la estructura de estos mensajes de solicitud y respuesta.  
  
|Operación|Mensaje XML|Description|  
|---------------|-----------------|-----------------|  
|Solicitud de procedimiento almacenado|`<[SP_NAME] xmlns="http://Microsoft.LobServices.OracleDB/2007/03/[SCHEMA]/Procedure">   <[PRM1_NAME]>value1</[PRM1_NAME]>   <[PRM2_NAME]>value2</[PRM2_NAME]>   … </[SP_NAME]>`|Admite parámetros IN de Oracle y en espera en el cuerpo del mensaje|  
|Respuesta de procedimiento almacenado|`<[SP_NAME]Response xmlns="http://Microsoft.LobServices.OracleDB/2007/03/[SCHEMA]/Procedure">   <[PRM1_NAME]>value1<[PRM1_NAME]>   <[PRM2_NAME]>value2</[PRM2_NAME]>   … </[SP_NAME]Response>`|Es compatible con los parámetros OUT de Oracle y en espera en el cuerpo del mensaje|  
|Solicitud de una función|`<[FN_NAME] xmlns="http://Microsoft.LobServices.OracleDB/2007/03/[SCHEMA]/Function">   <[PRM1_NAME]>value1</[PRM1_NAME]>   <[PRM2_NAME]>value2</[PRM2_NAME]>   … </[FN_NAME]>`|Admite parámetros IN de Oracle y en espera en el cuerpo del mensaje|  
|Respuesta de la función|`<[FN_NAME]Response xmlns="http://Microsoft.LobServices.OracleDB/2007/03/[SCHEMA]/Function">   <[FN_NAME]Result>return_value</[FN_NAME]Result>   <[PRM1_NAME]>value1</[PRM1_NAME]>   <[PRM2_NAME]>value2</[PRM2_NAME]>   …    </[FN_NAME]Response>`|Es compatible con los parámetros OUT de Oracle y en espera en el cuerpo del mensaje<br /><br /> -El valor devuelto de función se devuelve en el \<[fn_name especial] resultado > elemento. Este es el primer elemento en el mensaje de respuesta. Se trata de antes de los parámetros.|  
|Solicitud de función o procedimiento empaquetada|`<[SP_NAME] xmlns="http://Microsoft.LobServices.OracleDB/2007/03/[SCHEMA]/Package/[PACKAGE_NAME]">   <[PRM1_NAME]>value1</[PRM1_NAME]>   <[PRM2_NAME]>value2</[PRM2_NAME]>   … </[SP_NAME]>`|Igual que la función o procedimiento almacenado|  
|Procedimiento empaquetada o respuesta de la función|`<[SP_NAME]Response xmlns="http://Microsoft.LobServices.OracleDB/2007/03/[SCHEMA]/Package/[PACKAGE_NAME]">   <[PRM1_NAME]>value1</[PRM1_NAME]>   <[PRM2_NAME]>value2</[PRM2_NAME]>   … </[SP_NAME]Response>`|Igual que la función o procedimiento almacenado|  
  
 [Esquema] = artefactos de la colección de Oracle; Por ejemplo, SCOTT.  
  
 [SP_NAME] = el procedimiento almacenado que se ejecutará; Por ejemplo, SP_INSERT.  
  
 [Fn_name especial] = la función que se ejecuta; Por ejemplo, FN_GETID.  
  
 [PRM1_NAME] = el nombre del parámetro de Oracle. Vea la columna de descripción para las direcciones de parámetros admitidos por cada mensaje.  
  
 [NombreDePaquete] = el nombre del paquete que contiene el destino de procedimiento o función.  
  
 La base de datos de Oracle admite la sobrecarga de funciones y procedimientos almacenados. El [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] es compatible con esta funcionalidad mediante la anexión de una cadena de sobrecarga para el espacio de nombres de destino para cada artefacto sobrecargado. El valor de esta cadena es "overload1" para la primera sobrecarga, "overload2" para la segunda sobrecarga y así sucesivamente. En el ejemplo siguiente se muestra la estructura del mensaje para ver los dos procedimientos almacenados sobrecargados.  
  
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
 El [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] usa las siguientes acciones de mensaje para las operaciones de procedimiento y la función almacenadas.  
  
|de mensaje|Acción|Ejemplo|  
|-------------|------------|-------------|  
|Solicitud de procedimiento almacenado|http://Microsoft.LobServices.oracledb/2007/03/[esquema]/Procedure/[SP_NAME]|http://Microsoft.LobServices.oracledb/2007/03/Scott/Procedure/SP_INSERT|  
|Respuesta de procedimiento almacenado|http://Microsoft.LobServices.oracledb/2007/03/[esquema]/Procedure/[SP_NAME]/respuesta|http://Microsoft.LobServices.oracledb/2007/03/Scott/Procedure/SP_INSERT/Response|  
|Solicitud de una función|http://Microsoft.LobServices.oracledb/2007/03/[esquema]/Function/[fn_nameespecial]|http://Microsoft.LobServices.oracledb/2007/03/Scott/Function/FN_GETID|  
|Respuesta de la función|http://Microsoft.LobServices.oracledb/2007/03/[esquema]/Function/[fn_nameespecial]/respuesta|http://Microsoft.LobServices.oracledb/2007/03/Scott/Function/FN_GETID/Response|  
|Solicitud de procedimiento almacenado empaquetadas|http://Microsoft.LobServices.oracledb/2007/03/[esquema]/Package/[nombreDePaquete]/[SP_NAME]|http://Microsoft.LobServices.oracledb/2007/03/Scott/Package/Customer/SP_INSERT|  
|Empaquetar la respuesta de procedimiento almacenado|http://Microsoft.LobServices.oracledb/2007/03/[esquema]/Package/[nombreDePaquete]/[SP_NAME]/respuesta|http://Microsoft.LobServices.oracledb/2007/03/Scott/Package/Customer/SP_INSERT/Response|  
|Solicitud de una función empaquetada|http://Microsoft.LobServices.oracledb/2007/03/[esquema]/Package/[nombreDePaquete]/[fn_nameespecial]|http://Microsoft.LobServices.oracledb/2007/03/Scott/Package/Customer/FN_GETID|  
|Respuesta de la función empaquetada|http://Microsoft.LobServices.oracledb/2007/03/[esquema]/Package/[nombreDePaquete]/[fn_nameespecial]/respuesta|http://Microsoft.LobServices.oracledb/2007/03/Scott/Package/Customer/FN_GETID/Response|  
|Solicitud de procedimiento almacenado sobrecargado|http://Microsoft.LobServices.oracledb/2007/03/[esquema]/Procedure/[SP_NAME]/[sobrecarga]|http://Microsoft.LobServices.oracledb/2007/03/Scott/Procedure/SP_INSERT/overload1|  
|Sobrecargar la respuesta de procedimiento almacenado|http://Microsoft.LobServices.oracledb/2007/03/[esquema]/Procedure/[SP_NAME]/[sobrecarga]/respuesta|http://Microsoft.LobServices.oracledb/2007/03/Scott/Procedure/SP_INSERT/overload1/Response|  
  
 [Esquema] = artefactos de la colección de Oracle; Por ejemplo, SCOTT.  
  
 [SP_NAME] = el procedimiento almacenado que se ejecutará; Por ejemplo, SP_INSERT.  
  
 [Fn_name especial] = la función que se ejecuta; Por ejemplo, FN_GETID.  
  
 [NombreDePaquete] = el nombre del paquete que contiene el destino de procedimiento o función.  
  
 [Sobrecarga] = sobrecargar el parámetro. Los valores posibles son overload1, overload2 y así sucesivamente.  
  
## <a name="see-also"></a>Vea también  
 [Mensajes y esquemas de mensaje para el adaptador de BizTalk para base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/messages-and-message-schemas-for-biztalk-adapter-for-oracle-database.md)