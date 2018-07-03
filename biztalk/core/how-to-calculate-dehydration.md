---
title: Cómo calcular la deshidratación | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 88f2d09c-60db-4daf-b850-23f2c8915502
caps.latest.revision: 18
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: db413cfef1e49f1f3177d8a9f578c94f5a2a1a28
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36998149"
---
# <a name="how-to-calculate-dehydration"></a>Cómo calcular la deshidratación
Para calcular la deshidratación, use las propiedades configuradas y determinados valores de tiempo de ejecución. En el ejemplo siguiente se muestra cómo calcular un escenario de deshidratación hipotético.  
  
### <a name="to-calculate-dehydration"></a>Para calcular la deshidratación  
  
1. Permita que alfa represente un factor entre 0 y 1 que mida la sobrecarga de la memoria.  En la práctica, alfa tiene un componente para cada uno de los tres criterios de limitación de la memoria (propiedades de deshidratación); en este ejemplo, se indican como alpha(virtual), alpha(private) y alpha(physical). Defina lo siguiente:  
  
   ```  
   IF ActualPrivateBytes < OptimalUsage  
      alpha(private) = 1  
   ELSE IF ActualPrivateBytes > MaximalUsage  
      alpha(private) = 0  
   ELSE  
      alpha(private) = (MaximalUsage - ActualPrivateBytes) / (MaximalUsage - OptimalUsage)  
   ```  
  
   > [!NOTE]
   >  OptimalUsage y MaximalUsage tienen valores predeterminados para cada propiedad de deshidratación. Estos valores se pueden cambiar en el archivo BTSNTSvc.exe.config. Para obtener más información, consulte [propiedades predeterminadas de deshidratación](../core/dehydration-default-properties.md).  
  
2. Defina los otros componentes alfa de forma similar. Defina lo siguiente:  
  
   ```  
   alpha = Minimum { alpha(virtual), alpha(private), alpha(physical) }  
   where alpha(…) = 1 whenever IsActive=false for that given memory unit  
   ```  
  
3. A continuación, defina TestThreshold (TestThreshold, MinThreshold y MaxThreshold se definen en segundos):  
  
   ```  
   TestThreshold = MinThreshold + (alpha * (MaxThreshold – MinThreshold))  
   ```  
  
   > [!NOTE]
   >  Valor predeterminado de MinThreshold = 1. Valor predeterminado de MaxThreshold = 1800. Estos valores se pueden cambiar en el archivo BTSNTSvc.exe.config. Para obtener más información, consulte [propiedades predeterminadas de deshidratación](../core/dehydration-default-properties.md).  
  
4. A continuación, defina TimeBlocked y EstimatedTime:  
  
   -   TimeBlocked = tiempo real que se ha esperado a que se satisficiera esta suscripción  
  
   -   EstimatedTime = tiempo estimado que esta orquestación permanecerá inactiva (por ejemplo, tiempo de espera restante en la escucha)  
  
   La decisión sobre si se debe deshidratar es el resultado la siguiente condición booleana (true = deshidratar):  
  
-   Deshidratar = (EstimatedTime > TestThreshold OR TimeBlocked > (2* TestThreshold))  
  
> [!NOTE]
>  El tiempo estimado es el tiempo restante hasta que termina el retraso (si se retrasa 5 minutos y han pasado 2 minutos, TimeBlocked=120 segundos, EstimatedTime=180 segundos).  
  
## <a name="see-also"></a>Vea también  
 [Propiedades predeterminadas de deshidratación](../core/dehydration-default-properties.md)   
 [BTSNTSvc.exe.config (archivo)](../core/btsntsvc-exe-config-file.md)