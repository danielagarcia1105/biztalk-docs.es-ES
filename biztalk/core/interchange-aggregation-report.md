---
title: Informe de agregación de intercambio | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4619e8d0-9e9e-4d19-a67a-ac1058a0579b
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 578747267c73c4428e28eefd8b07ba51e8196fed
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36977957"
---
# <a name="interchange-aggregation-report"></a>Informe de agregación de intercambio
Este informe proporciona un registro que indica el número de intercambios EDI que comparten el mismo tipo de codificación EDI, la entidad remitente, la entidad receptora y la dirección. Este informe no ofrece detalles sobre los intercambios individuales.  
  
 Este informe de estado se muestra al hacer clic en el vínculo Informe de agregación del intercambio situado en la parte inferior de la página Concentrador de grupo de la consola de administración de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
## <a name="fields-in-the-status-report"></a>Campos del informe de estado  
 El Informe de agregación de intercambio muestra la siguiente información para cada registro:  
  
- Un recuento de la cantidad de intercambios que comparten el mismo tipo de codificación EDI, la misma entidad remitente, entidad receptora y dirección.  
  
- La entidad remitente de cada intercambio en el registro.  
  
- La entidad receptora de cada intercambio en el registro.  
  
- La dirección (de recepción o de envío) de cada intercambio en el registro.  
  
- La fecha y la hora a las que se envió o recibió el primer intercambio en el intervalo de tiempo (Primera fecha y hora de inicio).  
  
  > [!NOTE]
  >  Para los documentos recibidos, si la fecha especificada en el intercambio se encuentra en formato AAMMDD y AA es mayor o igual a 75, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] mostrará el año como 19AA. Si la fecha es inferior a 75, se mostrará como 20AA.  
  > 
  >  Por ejemplo, si recibe un intercambio que contiene el valor 991113 en ISA09, la más antigua a fecha y hora se mostrarán en el informe como 11/13/1999.  
  
- La fecha y la hora a las que se envió o recibió el último intercambio en el intervalo de tiempo (Última fecha y hora de finalización).  
  
- El tipo de codificación EDI de cada intercambio en el registro.  
  
## <a name="fields-in-the-query-expression-for-the-status-report"></a>Campos de Expresión de consulta para el informe de estado  
 Para personalizar el Informe de agregación de intercambio, cambie los campos de la expresión de consulta que determina los datos que se muestran. Están disponibles los campos siguientes:  
  
|||||  
|-|-|-|-|  
|Campo Expresión de consulta|Operadores potenciales|Valores potenciales|¿Incluido de forma predeterminada?|  
|Buscar|Es igual a|Informe de agregación de intercambio|Sí (obligatorio)|  
|Fecha y hora de intercambio|Menor o igual que<br /><br /> Mayor o igual que|Fecha y hora específica<br /><br /> Hoy<br /><br /> Hoy - 1|Sí<br /><br /> Nota: Se pueden incluir dos veces en la expresión de consulta, una vez con un menor-que el operador y una vez con una mayor-que el operador para proporcionar un intervalo.|  
|N.º máximo de coincidencias|Es igual a|Entero (predeterminado de 50)|Sí|  
|Dirección|Es igual a|Todos (opción predeterminada)<br /><br /> Receive<br /><br /> Send|no|  
|Nombre de la entidad receptora|Es igual a|Todos (opción predeterminada)<br /><br /> Nombre de entidad específico (cadena AN)|no|  
|Nombre de la entidad remitente|Es igual a|Todos (opción predeterminada)<br /><br /> Nombre de entidad específico (cadena AN)|no|  
|Estado|Es igual a<br /><br /> No es igual a|Aceptado<br /><br /> Aceptado con errores<br /><br /> Enviado<br /><br /> All<br /><br /> Confirmación esperada<br /><br /> Confirmación inesperada<br /><br /> Rechazado|no|