---
title: Esquemas de mensajes para los procedimientos almacenados, funciones y API PL-SQL | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6d707f10-470d-4390-bb5b-0301c326f375
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 029c48c1e6066d09d43da51b2bb1f6786a516f54
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="message-schemas-for-stored-procedures-functions-and-plsql-apis"></a>Esquemas de mensaje para los procedimientos almacenados, funciones y las API de PL/SQL
El [!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)]superficies del Oracle subyacente de base de datos los procedimientos almacenados, funciones y las API de PL/SQL (procedimientos almacenados y funciones dentro de un paquete) como operaciones. Esta sección describe la estructura de los mensajes y acciones que se usan para invocar procedimientos almacenados, funciones y las API de PL/SQL.  
  
## <a name="message-structure-of-stored-procedures-functions-and-plsql-apis"></a>Estructura de mensaje de los procedimientos almacenados, funciones y las API de PL/SQL  
 Las operaciones se exhibe para funciones y procedimientos almacenados siguen un patrón de intercambio de mensajes de solicitud y respuesta. En la tabla siguiente se muestra la estructura de estos mensajes de solicitud y respuesta.  
  
> [!NOTE]
>  Ver una descripción de la entidad después de la tabla.  
  
|Operación|Mensaje XML|Description|  
|---------------|-----------------|-----------------|  
|Solicitud de procedimiento almacenado|`<[SP_NAME] xmlns="[VERSION]/Procedures/[SCHEMA]">   <[PRM1_NAME]>value1</[PRM1_NAME]>   <[PRM2_NAME]>value2</[PRM2_NAME]>   … </[SP_NAME]>`|Admite parámetros IN de Oracle y en espera en el cuerpo del mensaje|  
|Respuesta de procedimiento almacenado|`<[SP_NAME]Response xmlns="[VERSION]/Procedures/[SCHEMA]">   <[PRM1_NAME]>value1<[PRM1_NAME]>   <[PRM2_NAME]>value2</[PRM2_NAME]>   … </[SP_NAME]Response>`|Es compatible con los parámetros OUT de Oracle y en espera en el cuerpo del mensaje|  
|Solicitud de una función|`<[FN_NAME] xmlns="[VERSION]/Functions/[SCHEMA] ">   <[PRM1_NAME]>value1</[PRM1_NAME]>   <[PRM2_NAME]>value2</[PRM2_NAME]>   … </[FN_NAME]>`|Admite parámetros IN de Oracle y en espera en el cuerpo del mensaje|  
|Respuesta de la función|`<[FN_NAME]Response xmlns="[VERSION]/Functions/[SCHEMA]">   <[FN_NAME]Result>return_value</[FN_NAME]Result>   <[PRM1_NAME]>value1</[PRM1_NAME]>   <[PRM2_NAME]>value2</[PRM2_NAME]>   …    </[FN_NAME]Response>`|Es compatible con los parámetros OUT de Oracle y en espera en el cuerpo del mensaje<br /><br /> Se devuelve el valor devuelto de función en la \<[fn_name especial] resultado\> elemento. Este es el primer elemento en el mensaje de respuesta. Se trata de antes de los parámetros.|  
|Solicitud de API de PL/SQL|`<[SP_NAME] xmlns="[VERSION]/PackageApis/[SCHEMA]/[PACKAGE_NAME/[SP_NAME]">   <[PRM1_NAME]>value1</[PRM1_NAME]>   <[PRM2_NAME]>value2</[PRM2_NAME]>   … </[SP_NAME]>`|Igual que la función o procedimiento almacenado|  
|Procedimiento empaquetada o respuesta de la función|`<[SP_NAME]Response xmlns="[VERSION]/PackageApis/[SCHEMA]/[PACKAGE_NAME]/[SP_NAME]">   <[PRM1_NAME]>value1</[PRM1_NAME]>   <[PRM2_NAME]>value2</[PRM2_NAME]>   … </[SP_NAME]Response>`|Igual que la función o procedimiento almacenado|  
  
 Descripciones de entidad:  
  
 [Versión] = http://schemas.microsoft.com/OracleEBS/2008/05.  
  
 [Esquema] = artefactos de la colección de Oracle; Por ejemplo, SCOTT.  
  
 [SP_NAME] = el procedimiento almacenado que se ejecutará; Por ejemplo, SP_INSERT.  
  
 [Fn_name especial] = la función que se ejecuta; Por ejemplo, FN_GETID.  
  
 [PRM1_NAME] = el nombre del parámetro de Oracle. Vea la columna de descripción para las direcciones de parámetros admitidos por cada mensaje.  
  
 [NombreDePaquete] = el nombre del paquete que contiene el destino de procedimiento o función.  
  
 La base de datos de Oracle admite la sobrecarga de funciones y procedimientos almacenados. El [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] es compatible con esta funcionalidad mediante la anexión de una cadena de sobrecarga para el espacio de nombres de destino para cada artefacto sobrecargado. El valor de esta cadena es "overload1" para la primera sobrecarga, "overload2" para la segunda sobrecarga y así sucesivamente. En el ejemplo siguiente se muestra la estructura del mensaje para ver los dos procedimientos almacenados sobrecargados.  
  
```  
Stored Procedure Overload 1:  
<[SP_NAME] xmlns="[VERSION]/PackageApis/[SCHEMA]/[PACKAGE_NAME]/[SP_NAME]/overload1">    
  <[PRM1_NAME]>value1</[PRM1_NAME]>  
  <[PRM2_NAME]>value1</[PRM2_NAME]>  
  …  
</[SP_NAME]>  
  
Stored Procedure Overload 2:  
<[SP_NAME] xmlns="[VERSION]/PackageApis/[SCHEMA]/[PACKAGE_NAME]/[SP_NAME]/overload2">    
  <[PRM1_NAME]>value1</I_[PRM1_NAME]>  
  <[PRM2_NAME]>value1</I_[PRM2_NAME]>  
  …  
</[SP_NAME]>  
```  
  
## <a name="message-actions-of-stored-procedures-functions-and-plsql-apis"></a>Acciones de mensaje de los procedimientos almacenados, funciones y las API de PL/SQL  
 El [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] usa las siguientes acciones de mensaje para el procedimiento almacenado, función y las operaciones de API de PL/SQL.  
  
> [!NOTE]
>  Ver una descripción de la entidad después de la tabla.  
  
|de mensaje|Acción|Ejemplo|  
|-------------|------------|-------------|  
|Solicitud de procedimiento almacenado|Procedimientos / [esquema] / [SP_NAME]|Procedimientos, SCOTT/SP_INSERT|  
|Respuesta de procedimiento almacenado|Procedimientos / [esquema] / [SP_NAME] / respuesta|Procedimientos/SCOTT/SP_INSERT/respuesta|  
|Solicitud de una función|Funciones / [esquema] / [fn_name especial]|SCOTT/funciones/FN_GETID|  
|Respuesta de la función|Funciones / [esquema] / [fn_name especial] / respuesta|Funciones/SCOTT/FN_GETID/respuesta|  
|Solicitud de API de PL/SQL|[Esquema] /Package/ [nombreDePaquete] / [SP_NAME]|SCOTT/paquetes/CUSTOMER/SP_INSERT|  
|Empaquetar la respuesta de procedimiento almacenado|[Esquema] /Package/ [nombreDePaquete] / [SP_NAME] / respuesta|SCOTT/paquetes / / SP_INSERT/respuesta del cliente|  
|Solicitud de una función empaquetada|[Esquema] /Package/ [nombreDePaquete] / [fn_name especial]|SCOTT/paquetes/CUSTOMER/FN_GETID|  
|Respuesta de la función empaquetada|[Esquema] /Package/ [nombreDePaquete] / [fn_name especial] / respuesta|SCOTT/paquetes / / FN_GETID/respuesta del cliente|  
|Solicitud de procedimiento almacenado sobrecargado|[Esquema] /Procedure/ [SP_NAME] / [sobrecarga]|SCOTT/procedimiento/SP_INSERT/overload1|  
|Sobrecargar la respuesta de procedimiento almacenado|[Esquema] /Procedure/ [SP_NAME] / [sobrecarga] / respuesta|SCOTT/procedimiento/SP_INSERT/overload1/respuesta|  
  
 Descripciones de entidad:  
  
 [Esquema] = artefactos de la colección de Oracle; Por ejemplo, SCOTT.  
  
 [SP_NAME] = el procedimiento almacenado que se ejecutará; Por ejemplo, SP_INSERT.  
  
 [Fn_name especial] = la función que se ejecuta; Por ejemplo, FN_GETID.  
  
 [NombreDePaquete] = el nombre del paquete que contiene el destino de procedimiento o función.  
  
 [Sobrecarga] = sobrecargar el parámetro. Los valores posibles son overload1, overload2 y así sucesivamente.  
  
## <a name="see-also"></a>Vea también  
 [Mensajes y esquemas de mensaje para el adaptador de BizTalk para Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/messages-and-message-schemas-for-biztalk-adapter-for-oracle-e-business-suite.md)