---
title: Esquemas de mensaje para la operación SQLEXECUTE | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- SQLEXECUTE operations, message schemas for
ms.assetid: 744645f4-0674-44e0-bf8d-8df70086b0f1
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d7c7efc6a59e9dd4c163388803763a7b90a13b31
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="message-schemas-for-the-sqlexecute-operation"></a>Esquemas de mensaje para la operación SQLEXECUTE
[!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]expone metadatos fuertemente tipada de artefactos presentes en el sistema LOB y expone las operaciones estándares de estos artefactos. Sin embargo, hay escenarios donde una aplicación puede requerir la ejecución de una instrucción SQL arbitraria que se controla mediante la lógica de negocios en la aplicación. Por ejemplo, puede:  
  
-   Realizar una operación en artefactos de base de datos que no se exponen a través de la [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]; por ejemplo, obtenga el CURVAL o NEXTVAL de las secuencias de Oracle.  
  
-   Realizar operaciones de lenguaje de definición de datos; Por ejemplo, crear una tabla.  
  
-   Realizar operaciones en un artefacto de la base de datos que no estaba presente en tiempo de diseño; Por ejemplo, actualizar registros en una tabla temporal que se crea mediante la lógica de negocios.  
  
-   Realizar operaciones más complejas de DML en tablas que las operaciones obtenidas por el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]; por ejemplo realizar una consulta que incluya una cláusula de combinación.  
  
 La [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] expone una operación especial que se llamó a la operación SQLEXECUTE para admitir estos escenarios. Mediante el uso de esta operación, puede especificar una instrucción SQL arbitraria para el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] para ejecutar en la base de datos de Oracle. También puede especificar varios bloques de parámetros de entrada a la instrucción SQL. El [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] se ejecuta la instrucción SQL una vez para cada conjunto de parámetros y devuelve el resultado como un conjunto de registros (débilmente tipada) genérico.  
  
> [!NOTE]
>  Puede pasar en y en los parámetros OUT procedimientos, funciones y paquetes en la operación SQLEXECUTE. El artefacto invocado se ejecutará con los parámetros proporcionados en la base de datos de Oracle; Sin embargo, la operación SQLEXECUTE devuelve el valor de salida y los parámetros en espera para el cliente. Si desea invocar procedimientos, funciones o paquetes, Microsoft recomienda que lo hace mediante la invocación de las operaciones dedicadas que la [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] expone para que estos artefactos de Oracle.  
  
 El siguiente XML muestra la estructura de la operación SQLEXECUTE:  
  
```  
<SQLEXECUTE xmlns="SQLEXECUTE">  
  <SQLSTATEMENT> [STATEMENT] </SQLSTATEMENT>  
  <PARAMETERSCHEMA>[PARAM_SPEC]</PARAMETERSCHEMA>  
  <PARAMETERSET>  
    <PARAMETERDATA>  
      <PARAMETER xmlns:c="http://schemas.microsoft.com/2003/10/Serialization/Arrays">  
        <c:string>[PARAM_VAL_1]</c:string>  
      </PARAMETER>  
    </PARAMETERDATA>  
    …  
  </PARAMETERSET>  
</SQLEXECUTE>  
```  
  
 [Instrucción] = la instrucción SQL que se ejecuta; Por ejemplo, "Seleccione * de emp WHERE empno =: emp_no".  
  
 [PARAM_SPEC] = la lista de los parámetros IN en la instrucción SQL y sus tipos de datos; Por ejemplo, "emp_no número".  
  
 [PARAM_VAL_1] = el valor del primer parámetro.  
  
 Cada \<PARAMETERDATA\> sección contiene un conjunto completo de \<parámetro\> elementos que coinciden con el esquema en el \<PARAMETERSCHEMA\> sección. El \<PARAMETERSET\> puede contener varios \<PARAMETERDATA\> secciones. Si este es el caso, la instrucción SQL se ejecuta varias veces, una vez en cada conjunto de parámetros.  
  
## <a name="see-also"></a>Vea también  
 [Mensajes y esquemas de mensaje para el adaptador de BizTalk para la base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/messages-and-message-schemas-for-biztalk-adapter-for-oracle-database.md)