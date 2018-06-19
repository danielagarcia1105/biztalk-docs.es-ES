---
title: 'Paso 4: Generar el proyecto | Documentos de Microsoft'
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
ms.openlocfilehash: 0f1d6fa03b4a686537ef04f0121c1ae168e525ff
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22225668"
---
# <a name="step-4-build-the-project"></a>Paso 4: Generar el proyecto
![Paso 4 de 4](../../adapters-and-accelerators/adapter-oracle-ebs/media/step-4of4.gif "Step_4of4")  
  
 **Tiempo en completarse:** 5 minutos  
  
 **Objetivo:** en este paso, compilará el proyecto de orquestación de BizTalk.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Debe haber completado [paso 3: enviar el mensaje de solicitud para insertar registros y recibir una respuesta](../../adapters-and-accelerators/adapter-sql/step-3-send-the-request-message-to-insert-records-and-receive-a-response.md).  
  
### <a name="to-build-the-biztalk-orchestration-project"></a>Para compilar el proyecto de orquestación de BizTalk  
  
1.  En el Explorador de soluciones, haga clic en el nombre del proyecto de BizTalk y, a continuación, haga clic en **propiedades**.  
  
2.  En el cuadro de diálogo páginas de propiedades, en el panel del árbol, expanda **propiedades comunes**, haga clic en **ensamblado**y, a continuación, en la lista de propiedades, haga clic en el **archivo de clave de ensamblado** puntos suspensivos **[...]** .  
  
3.  Especifique una ruta de acceso al archivo de clave de ensamblado que creó como se describe en [los requisitos previos para crear aplicaciones de SQL mediante el adaptador de SQL](../../adapters-and-accelerators/adapter-sql/prerequisites-to-create-sql-applications-using-the-sql-adapter.md)y, a continuación, haga clic en **abiertos**.  
  
4.  En el cuadro de diálogo páginas de propiedades, en el panel del árbol, expanda **propiedades de configuración**, haga clic en **implementación**, y, a continuación, realice lo siguiente:  
  
    1.  Para el **nombre de la aplicación** propiedad, escriba `SampleApplication`.  
  
    2.  Para el **volver a implementar** propiedad, seleccione **True**.  
  
     Haga clic en **Aceptar**.  
  
5.  En el menú **Archivo** , haga clic en **Guardar todo**.  
  
6.  En el Explorador de soluciones, haga clic en el nombre de la solución y, a continuación, haga clic en **generar solución**.  
  
     El panel de salida en la parte inferior de la pantalla se lea: **compilar: 3 se ha realizado correctamente o actualizados, 0 incorrectos, 0 omitidos.**  
  
## <a name="what-did-i-just-do"></a>Síntesis  
 En este paso, ha compilado la solución que contiene el proyecto de BizTalk y dos proyectos de biblioteca de clases.  
  
## <a name="next-steps"></a>Pasos siguientes  
 Implementar la solución, como se describe en [lección 5: implementar la solución](../../adapters-and-accelerators/adapter-sql/lesson-5-deploy-the-solution.md).  
  
## <a name="see-also"></a>Vea también  
 [Paso 3: Enviar el mensaje de solicitud para insertar registros y recibir una respuesta](../../adapters-and-accelerators/adapter-sql/step-3-send-the-request-message-to-insert-records-and-receive-a-response.md)   
 [Lección 4: Realizar una operación de inserción en la tabla de orden de compra](../../adapters-and-accelerators/adapter-sql/lesson-4-perform-an-insert-operation-on-the-purchase-order-table.md)