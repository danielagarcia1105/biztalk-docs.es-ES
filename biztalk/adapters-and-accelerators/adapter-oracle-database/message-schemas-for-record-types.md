---
title: Los esquemas de mensajes para tipos de registros | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- RECORD types, message schemas for
- RECORD types, support for
ms.assetid: 637c42f2-eed0-4941-a6cd-7e03d01088b8
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: aae82fad713fd9a2789e165845958421e1213402
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36996925"
---
# <a name="message-schemas-for-record-types"></a>Esquemas de mensaje para tipos de registro
Tipos de registros de Oracle son tipos de datos estructurados de PL/SQL que se componen de uno o más los tipos de base de datos estructurados o simple. Tipos de registros se utilizan principalmente en las funciones y procedimientos almacenados de PL/SQL para enviar y recibir datos jerárquicos.  
  
 El [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] es compatible con tipos de registros de la siguiente manera:  
  
- Tipos de registro se exponen como tipos complejos.  
  
- Tipos de registro pueden ser (registro anidado en un registro).  
  
- Tipos de registros se pueden declarar como parámetros de tipo de fila de tabla % en procedimientos almacenados y funciones.  
  
- Tipos de registros se pueden declarar como parámetros de tipo de registro en los paquetes de PL/SQL; Por ejemplo, `TYPE rec_type1 IS RECORD(name varchar2(100), age number(3));`.  
  
  > [!NOTE]
  >  El [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] no admite tipos BFILE como miembros de registro.  
  
  Cuando se utiliza un parámetro de tipo de registro en un procedimiento almacenado o una función, está calificado con el espacio de nombres de esa operación. El siguiente XML muestra la estructura de un tipo de registro en un mensaje:  
  
```  
<[REC_PARAM_NAME]>  
  <[FIELD_NAME1] xmlns="[OPERATION_NAMESPACE]">value1</[FIELD_NAME1]>  
  <[FIELD_NAME2] xmlns="[OPERATION_NAMESPACE]">value2</[FIELD_NAME2]>  
  …  
</[REC_PARAM_NAME]>  
```  
  
 [REC_PARAM_NAME] es el nombre del parámetro de registro.  
  
 [Nombre_de_campo] es el nombre de un campo en el tipo de registro.  
  
 [OPERATION_NAMESPACE] es el espacio de nombres del procedimiento almacenado o función en el que se usa el parámetro de registro.  
  
 El siguiente XML muestra la estructura de un parámetro de tipo de registro con un campo de tipo de registro anidado:  
  
```  
<[REC_PARAM_NAME]>    
  <[FIELD_NAME1] xmlns="[OPERATION_NAMESPACE]">value1</[FIELD_NAME1]>  
  <[FIELD_NAME2] xmlns="[OPERATION_NAMESPACE]">value2</[FIELD_NAME2]>  
  <[REC_PARAM_NAME2]>  
    <[FIELD_NAME1] xmlns="[OPERATION_NAMESPACE]">value1</[FIELD_NAME1]>  
    <[FIELD_NAME2] xmlns="[OPERATION_NAMESPACE]">value1</[FIELD_NAME2]>  
    …  
  </[REC_PARAM_NAME2]>  
  …  
</[REC_PARAM_NAME]>  
```  
  
## <a name="see-also"></a>Vea también  
 [Mensajes y esquemas de mensaje para el adaptador de BizTalk para la base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/messages-and-message-schemas-for-biztalk-adapter-for-oracle-database.md)