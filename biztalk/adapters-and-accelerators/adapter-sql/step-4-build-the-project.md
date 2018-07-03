---
title: 'Paso 4: Generar el proyecto | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d88b1407-ecdd-4dbf-90da-02dc4781568c
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cfa718d31c7b93d1cc05cefb8251a635cc70ef22
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36977941"
---
# <a name="step-4-build-the-project"></a>Paso 4: Generar el proyecto
![Paso 4 de 4](../../adapters-and-accelerators/adapter-oracle-ebs/media/step-4of4.gif "Step_4of4")  
  
 **Tiempo en completarse:** 5 minutos  
  
 **Objetivo:** en este paso, compilará el proyecto de orquestación de BizTalk.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Debe haber completado [paso 3: enviar el mensaje de solicitud para insertar registros y recibir una respuesta](../../adapters-and-accelerators/adapter-sql/step-3-send-the-request-message-to-insert-records-and-receive-a-response.md).  
  
### <a name="to-build-the-biztalk-orchestration-project"></a>Para compilar el proyecto de orquestación de BizTalk  
  
1. En el Explorador de soluciones, haga clic en el nombre del proyecto de BizTalk y, a continuación, haga clic en **propiedades**.  
  
2. En el cuadro de diálogo páginas de propiedades, en el panel del árbol, expanda **propiedades comunes**, haga clic en **ensamblado**y, a continuación, en la lista de propiedades, haga clic en el **archivo clave de ensamblado** puntos suspensivos **[...]** .  
  
3. Especifique una ruta de acceso al archivo de clave de ensamblado que creó como se describe en [requisitos previos para crear aplicaciones de SQL con el adaptador SQL](../../adapters-and-accelerators/adapter-sql/prerequisites-to-create-sql-applications-using-the-sql-adapter.md)y, a continuación, haga clic en **abierto**.  
  
4. En el cuadro de diálogo páginas de propiedades, en el panel del árbol, expanda **propiedades de configuración**, haga clic en **implementación**, y, a continuación, haga lo siguiente:  
  
   1. Para el **nombre de la aplicación** propiedad, tipo `SampleApplication`.  
  
   2. Para el **volver a implementar** propiedad, seleccione **True**.  
  
      Haga clic en **Aceptar**.  
  
5. En el menú **Archivo** , haga clic en **Guardar todo**.  
  
6. En el Explorador de soluciones, haga clic en el nombre de la solución y, a continuación, haga clic en **compilar solución**.  
  
    El panel de salida en la parte inferior de la pantalla debe leer: **compilar: 3 correctos o actualizados, 0 incorrectos, 0 omitidos.**  
  
## <a name="what-did-i-just-do"></a>Síntesis  
 En este paso, ha compilado la solución que contiene el proyecto de BizTalk y dos proyectos de biblioteca de clases.  
  
## <a name="next-steps"></a>Pasos siguientes  
 Implementar la solución, como se describe en [lección 5: implementar la solución](../../adapters-and-accelerators/adapter-sql/lesson-5-deploy-the-solution.md).  
  
## <a name="see-also"></a>Vea también  
 [Paso 3: Enviar el mensaje de solicitud para insertar registros y recibir una respuesta](../../adapters-and-accelerators/adapter-sql/step-3-send-the-request-message-to-insert-records-and-receive-a-response.md)   
 [Lección 4: Realizar una operación de inserción en la tabla de pedidos de compra](../../adapters-and-accelerators/adapter-sql/lesson-4-perform-an-insert-operation-on-the-purchase-order-table.md)