---
title: Informe de agregación de conjunto de transacciones | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a6e1417e-e0c6-4d30-aab5-d9bfe14cd4b8
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7c95dcb1bc0ff0038b431505cbcccf004d772921
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37015077"
---
# <a name="transaction-set-aggregation-report"></a>Informe de agregación de conjunto de transacciones
El informe proporciona un único registro que muestra el número de conjuntos de transacciones EDI que comparten el mismo Id. de conjunto de transacciones, el tipo de codificación EDI, la entidad remitente, la entidad receptora y la dirección. Este informe no ofrece detalles sobre los conjuntos de transacciones individuales.  
  
 Este informe de estado se muestra al hacer clic en el vínculo Informe de agregación del conjunto de transacciones situado en la parte inferior de la página Concentrador de grupo de la consola de administración de BizTalk Server.  
  
## <a name="fields-in-the-status-report"></a>Campos del informe de estado  
 El Informe de agregación de conjunto de transacciones muestra la siguiente información correspondiente a los intercambios recibidos o enviados:  
  
- Un recuento de la cantidad de conjuntos de transacciones que comparten el mismo Id. de conjunto de transacciones, el tipo de codificación EDI, la entidad remitente, la entidad receptora y la dirección.  
  
- La entidad remitente de cada conjunto de transacciones en el registro  
  
- La entidad receptora de cada conjunto de transacciones en el registro  
  
- La dirección (de recepción o envío) de cada conjunto de transacciones en el registro  
  
- La fecha y la hora a las que se envió o recibió el primer conjunto de transacciones en el intervalo de tiempo (Primera fecha y hora de inicio)  
  
  > [!NOTE]
  >  Para los documentos recibidos, si la fecha especificada en el intercambio se encuentra en formato AAMMDD y AA es mayor o igual a 75, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] mostrará el año como 19AA. Si la fecha es inferior a 75, se mostrará como 20AA.  
  > 
  >  Por ejemplo, si recibe un intercambio que contiene el valor 991113 en ISA09, la primera fecha y hora de inicio se mostrará en el informe como 11/13/1999.  
  
- La fecha y la hora a las que se envió o recibió el último conjunto de transacciones en el intervalo de tiempo (Última fecha y hora de finalización)  
  
## <a name="fields-in-the-query-expression-for-the-status-report"></a>Campos de Expresión de consulta para el informe de estado  
 Para personalizar el Informe de agregación de intercambio, cambie los campos de la expresión de consulta que determina los datos que se muestran. Están disponibles los campos siguientes:  
  
|||||  
|-|-|-|-|  
|Campo Expresión de consulta|Operadores potenciales|Valores potenciales|¿Incluido de forma predeterminada?|  
|Buscar|Es igual a|Informe de agregación de conjunto de transacciones|Sí (obligatorio)|  
|Fecha y hora de intercambio|Menor o igual que<br /><br /> Mayor o igual que|Fecha y hora específica<br /><br /> Hoy<br /><br /> Hoy - 1|Sí<br /><br /> Nota: Se pueden incluir dos veces en la expresión de consulta, una vez con un menor-que el operador y una vez con una mayor-que el operador para proporcionar un intervalo|  
|N.º máximo de coincidencias|Es igual a|Entero (predeterminado de 50)|Sí|  
|Dirección|Es igual a|Todos (opción predeterminada)<br /><br /> Receive<br /><br /> Send|no|  
|Nombre de la entidad receptora|Es igual a|Todos (opción predeterminada)<br /><br /> Nombre de entidad específico (cadena AN)|no|  
|Nombre de la entidad remitente|Es igual a|Todos (opción predeterminada)<br /><br /> Nombre de entidad específico (cadena AN)|no|  
|Estado|Es igual a<br /><br /> No es igual a|Aceptado<br /><br /> Aceptado con errores<br /><br /> Enviado<br /><br /> All<br /><br /> Confirmación esperada<br /><br /> Confirmación inesperada<br /><br /> Rechazado|no|  
|Id. de conjunto de transacciones|Es igual a|Todos (opción predeterminada)<br /><br /> Id. de conjunto de transacciones específico|no|  
  
