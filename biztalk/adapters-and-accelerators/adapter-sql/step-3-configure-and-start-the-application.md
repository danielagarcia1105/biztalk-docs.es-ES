---
title: 'Paso 3: Configurar e iniciar la aplicación | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e4252470-805e-404f-80d5-df8d1ff3af63
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9f932ca1f3570f080de239dd90c52d9a5f5db721
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36988205"
---
# <a name="step-3-configure-and-start-the-application"></a>Paso 3: Configurar e iniciar la aplicación
![Paso 3 de 4](../../adapters-and-accelerators/adapter-oracle-ebs/media/step-3of4.gif "Step_3of4")  
  
 **Tiempo en completarse:** 10 minutos  
  
 **Objetivo:** en este paso, configurará e iniciará la aplicación SampleApplication. Al configurar la aplicación SampleApplication, asocie los artefactos lógicos creados en [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] con sus homólogos físicos.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Debe haber completado [paso 2: configurar los puertos](../../adapters-and-accelerators/adapter-sql/step-2-configure-the-ports.md).  
  
### <a name="to-configure-and-start-the-application"></a>Para configurar e iniciar la aplicación  
  
1. Iniciar el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración.  
  
2. En el árbol de consola en el lado izquierdo, expanda **administración de BizTalk Server**, haga clic en **grupo de BizTalk**y, a continuación, haga clic en **actualizar**.  
  
3. Expanda **grupo de BizTalk**, expanda **aplicaciones**, haga clic en **SampleApplication**y, a continuación, haga clic en **configurar**.  
  
4. En el **Configurar aplicación** cuadro de diálogo el **EmployeeOrch** ficha, realice lo siguiente:  
  
   1.  Para **Host** lista desplegable, seleccione **BizTalkServerApplication**.  
  
   2.  Haga doble clic en la celda en **ReceiveNotification** y seleccione **NotifyReceivePort** en la lista desplegable.  
  
   3.  Haga doble clic en la celda en **SQLOutboundPort** y seleccione **SQLOutboundPort** en la lista desplegable.  
  
   4.  Haga doble clic en la celda en **SaveResponsePort** y seleccione **EmailResponse** en la lista desplegable.  
  
5. La siguiente ilustración muestra una aplicación configurada.  
  
    ![Configurar aplicación](../../adapters-and-accelerators/adapter-sql/media/sql-adap-tut-011-configure-app.gif "sql_adap_tut_011_configure_app")  
  
6. En el **Configurar aplicación** cuadro de diálogo, haga clic en **Aceptar**.  
  
7. En el árbol de consola, haga clic en **SampleApplication**y, a continuación, haga clic en **iniciar**.  
  
8. En el árbol de consola, haga clic en **aplicaciones**.  
  
9. En el panel de detalles de las aplicaciones, compruebe que la **estado** de **SampleApplication** es **iniciado**.  
  
## <a name="what-did-i-just-do"></a>Síntesis  
 Ha configurado e iniciado la aplicación SampleApplication  
  
## <a name="next-steps"></a>Pasos siguientes  
 Probar la aplicación mediante la inserción de nuevos empleados en el **empleado** de tabla, como se describe en [paso 4: probar la aplicación](../../adapters-and-accelerators/adapter-sql/step-4-test-the-application.md).  
  
## <a name="see-also"></a>Vea también  
 [Paso 2: Configurar los puertos](../../adapters-and-accelerators/adapter-sql/step-2-configure-the-ports.md)   
 [Paso 4: Probar la aplicación](../../adapters-and-accelerators/adapter-sql/step-4-test-the-application.md)   
 [Lección 5: Implementar la solución](../../adapters-and-accelerators/adapter-sql/lesson-5-deploy-the-solution.md)