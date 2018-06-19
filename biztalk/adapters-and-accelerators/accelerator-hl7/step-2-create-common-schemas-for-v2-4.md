---
title: 'Paso 2: Crear los esquemas comunes para V2.4 | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- interrogative tutorial, common schemas
ms.assetid: 333ae85a-a307-4ab1-97f4-4d7b986e91de
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 60b199bcd350a3341640baa05b875347c4f04bb5
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
ms.locfileid: "25960714"
---
# <a name="step-2-create-common-schemas-for-v24"></a>Paso 2: Crear los esquemas comunes para V2.4
Los esquemas V2.4 son esquemas normalmente se hace referencia, que se utilizan para validar las instancias de mensaje de consulta y respuesta.  
  
### <a name="to-create-the-common-schemas-for-v24"></a>Para crear los esquemas comunes para V2.4  
  
1.  En [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], en la **archivo** menú, elija **New**y, a continuación, haga clic en **proyecto**.  
  
2.  En el cuadro de diálogo nuevo proyecto, en la **tipos de proyecto** lista, expanda **proyectos de BizTalk**y, a continuación, seleccione **BTAHL7Projects**.  
  
3.  En el **plantillas** lista, seleccione **BTAHL7V24Common proyecto**.  
  
4.  En el **nombre** , escriba **Interrogative_24Schemas**.  
  
5.  En el campo de la solución, seleccione **agregar a solución**y, a continuación, haga clic en **Aceptar**.  
  
     En el Explorador de soluciones, tenga en cuenta que los tres esquemas (datatypes_24.xsd, segments_24.xsd y tablevalues_24.xsd) se incluyen en el proyecto.  
  
6.  En el Explorador de soluciones, haga clic en **Interrogative_24Schemas** del proyecto y, a continuación, haga clic en **propiedades**.  
  
7.  En el cuadro de diálogo páginas de propiedades de Interrogative_24Schemas, haga clic en **ensamblado**.  
  
8.  En el panel derecho, desplácese hacia abajo hasta la **nombre seguro** sección, haga clic en el campo a la derecha del **archivo de clave de ensamblado**y, a continuación, haga clic en el botón de puntos suspensivos (...).  
  
9. En el **archivo de clave de ensamblado** cuadro de diálogo, vaya a \< *unidad*\>: \Program BizTalk \<versión\> Acelerador para HL7\SDK\ Haga clic en de Tutorial, interrogative **key.snk**y, a continuación, haga clic en **abiertos**.  
  
10. En el cuadro de diálogo páginas de propiedades de Interrogative_24Schemas, haga clic en **Aceptar** para guardar los cambios.  
  
11. En el Explorador de soluciones, haga clic en **Interrogative_24Schemas** del proyecto y, a continuación, haga clic en **implementar**. Haga clic en **Aceptar** al cuadro de diálogo que pregunta si desea guardar los cambios a la solución. Asegúrese de que aparece un mensaje de confirmación en la ventana de salida.  
  
    > [!NOTE]
    >  Si no aparece el mensaje correcto, utilice [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] para solucionar problemas de los esquemas.  
  
 Continúe con [paso 3: crear e implementar un proyecto de desencadenador de eventos (mensaje)](../../adapters-and-accelerators/accelerator-hl7/step-3-create-and-deploy-a-trigger-event-message-project-hl7-main.md).