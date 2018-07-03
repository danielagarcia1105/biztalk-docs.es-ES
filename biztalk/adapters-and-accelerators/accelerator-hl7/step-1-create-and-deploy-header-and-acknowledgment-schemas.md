---
title: 'Paso 1: Crear e implementar esquemas de encabezado y confirmación | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- end-to-end tutorial, header schemas
- header schemas
ms.assetid: 3ff013a4-6c67-4bac-be97-81b2dc5b6119
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 50aa394f033d935c3838e056c715ee74e296b063
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36989397"
---
# <a name="step-1-create-and-deploy-header-and-acknowledgment-schemas"></a>Paso 1: Crear e implementar esquemas de encabezado y confirmación
Utilice el esquema de encabezado para validar el encabezado (segmento MSH) de la instancia de mensaje. Utilice el esquema de confirmación para generar la confirmación para la instancia de mensaje. Este proceso es común en todas las versiones de esquemas de [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] 2.X.  
  
### <a name="to-create-the-header-and-acknowledgment-schemas"></a>Para crear los esquemas de encabezado y confirmación  
  
1. Inicie **Microsoft Visual Studio 2012**.  
  
2. En [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], en el **archivo** menú, elija **New**y, a continuación, haga clic en **proyecto**.  
  
3. En el cuadro de diálogo nuevo proyecto, en el **tipos de proyecto** sección, expanda **proyectos de BizTalk**y, a continuación, seleccione **BTAHL7Projects**.  
  
4. En la sección plantillas, seleccione **proyecto BTAHL7V2XCommon**y, a continuación, haga clic en **Aceptar**.  
  
    En el Explorador de soluciones, tenga en cuenta que los tres esquemas (ACK_24_GLO_DEF.xsd ACK_25_GLO_DEF.xsd y MSH_25_GLO_DEF.xsd) se incluyen en el proyecto.  
  
## <a name="step-1a-assign-a-strong-key-to-the-assembly-and-deploy"></a>Paso 1A: asignar una clave segura para el ensamblado e implementar  
 Utilice el procedimiento siguiente para asignar una clave segura para el ensamblado y, a continuación, implemente el ensamblado.  
  
#### <a name="to-assign-a-strong-key-and-deploy-the-assembly"></a>Para asignar una clave segura e implementar el ensamblado  
  
1. Inicie un **símbolo del sistema de Visual Studio 2012**.  
  
2. En el [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] símbolo del sistema, vaya a la \< *unidad*\>: \Program archivos\\Microsoft BizTalk \<versión\> Acelerador para HL7 \SDK\End-to-End Carpeta tutorial.  
  
3. En el símbolo del sistema, escriba **sn – k key.snk**, y, a continuación, presione ENTRAR. Asegúrese de que aparece el siguiente mensaje de éxito en la ventana de salida y, a continuación, cierre la ventana de comandos.  
  
    **"Par de claves escrito en key.snk."**  
  
   > [!NOTE]
   >  Si no aparece el mensaje correcto, use [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] para solucionar problemas de su ensamblado.  
  
4. En el Explorador de soluciones, haga clic en **BTAHL7V2XCommon Project1**y, a continuación, haga clic en **propiedades**.  
  
5. En la página de páginas de propiedades de Project1 BTAHL7V2XCommon **ensamblado**.  
  
6. En el panel derecho, desplácese hacia abajo hasta la **nombre seguro** sección, haga clic en el campo a la derecha del **archivo clave de ensamblado**y, a continuación, haga clic en el botón de puntos suspensivos (**...** ) botón.  
  
7. En el cuadro de diálogo de archivo de clave de ensamblado, vaya a \< *unidad*\>: \Program archivos\\Microsoft BizTalk \<versión\> acelerador HL7\SDK\End a otro tutorial, Seleccione **key.snk**y, a continuación, haga clic en **abierto**.  
  
8. En la página de propiedades de proyecto BTAHL7V2XCommon **Aceptar** para guardar los cambios.  
  
9. En [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], en **el Explorador de soluciones**, haga clic en **proyecto BTAHL7V2XCommon**y, a continuación, haga clic en **implementar**. Asegúrese de que aparece un mensaje de éxito en la ventana de salida.  
  
   > [!NOTE]
   >  Si no aparece el mensaje de la implementación correcta, utilice [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] para solucionar problemas de implementación.  
  
   Continúe con [paso 2: crear los esquemas comunes para V2.3.1](../../adapters-and-accelerators/accelerator-hl7/step-2-create-common-schemas-for-v2-3-1.md).