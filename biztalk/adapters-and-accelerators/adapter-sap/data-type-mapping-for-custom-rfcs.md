---
title: Tipo de datos de asignación para las solicitudes de cambio personalizadas | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- custom RFCs, data type mapping
ms.assetid: 33539a5a-bdfc-423f-8026-436f69a20c70
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cac254734a35658e3aa635b086f765e8f06494a7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="data-type-mapping-for-custom-rfcs"></a>Asignación de tipos de datos para las solicitudes de cambio personalizadas
En la tabla siguiente proporciona información sobre los tipos de datos SAP y cómo se asignan a tipos de datos de .NET para la solicitud de cambio de Z_EXTRACT_DATA_OO. Este RFC personalizada se usa por la [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)].  
  
> [!NOTE]
>  Caso Z_EXECUTE_SAP_QUERY, que se utiliza en el [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] para ejecutar el comando EXECQUERY, todos los tipos de datos SAP se convierten en tipos de cadena. NET.  
  
|Tipo de datos SAP|Tipo de datos de .NET|  
|-------------------|--------------------|  
|ACCP|-Int32<br />-Cadena, si **disabledatavalidation** opción está establecida en la instrucción SELECT o EXEC.|  
|CHAR|String|  
|CLNT|String|  
|CUKY|String|  
|DIV|Decimal, si una precisión menor o igual que 28<br /><br /> Cadena, si precisión superior a 28|  
|DATS|-Fecha y hora<br />-Cadena, si **disabledatavalidation** opción está establecida en la instrucción SELECT o EXEC.|  
|DEC|Decimal|  
|FLTP|Doble|  
|INT1|Byte|  
|INT2|Int16|  
|INT4|Int32|  
|LANG|String|  
|NUMC|-Int32, si el campo longitud menor o igual a 9<br />-Int64, si el campo longitud mayor que 9 y menor o igual a 19<br />-Cadena, si es mayor que 19<br />-Cadena, si **disabledatavalidation** opción está establecida en la instrucción SELECT o EXEC.|  
|PREC|Int16|  
|QUAN|Decimal|  
|RAW|Byte]|  
|RSTR|Byte]|  
|SSTR|String|  
|STRG|String|  
|TIM|-TimeSpan<br />-Cadena, si **disabledatavalidation** opción está establecida en la instrucción SELECT o EXEC.|  
|UNIDAD|String|  
|LCHR|String|  
|LRAW|Byte]|  
  
## <a name="see-also"></a>Vea también  
 [Mensajes y esquemas de mensaje para el adaptador de BizTalk para mySAP Business Suite](../../adapters-and-accelerators/adapter-sap/messages-and-message-schemas-for-biztalk-adapter-for-mysap-business-suite.md)