---
title: 'Paso 1: Crear e implementar esquemas de confirmación y de encabezado común | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- interrogative tutorial, headers
ms.assetid: e0f11f58-9a8c-4567-a537-3d182fa7dce2
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 988c2922d09412aa248c08c36e727709d45e5a66
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36989269"
---
# <a name="step-1-create-and-deploy-common-header-and-acknowledgment-schemas"></a>Paso 1: Crear e implementar esquemas de confirmación y de encabezado comunes
Utilice el esquema de encabezado para validar el encabezado (segmento MSH) de la instancia de mensaje. Utilice el esquema de confirmación para generar la confirmación para la instancia de mensaje. Este proceso es común en todas las versiones de esquema HL7.  
  
### <a name="to-create-the-header-and-acknowledgment-schemas"></a>Para crear los esquemas de encabezado y confirmación  
  
1. Inicie **Microsoft Visual Studio 2012**.  
  
2. En [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], en el **archivo** menú, elija **New**y, a continuación, haga clic en **proyecto**.  
  
3. En el cuadro de diálogo nuevo proyecto, en el **tipos de proyecto** lista, expanda **proyectos de BizTalk**y, a continuación, seleccione **BTAHL7Projects**.  
  
4. En el **plantillas** lista, seleccione **proyecto BTAHL7V2XCommon**.  
  
5. En el **nombre** , escriba **Interrogative_2XSchemas**y, a continuación, haga clic en **Aceptar**.  
  
    En el Explorador de soluciones, tenga en cuenta que los tres esquemas (ACK_24_GLO_DEF.xsd, ACK_25_GLO_DEF.xsd y MSH_25_GLO_DEF.xsd) se incluyen en el proyecto.  
  
    Deje abierto Visual Studio.  
  
## <a name="step-1a-assign-a-strong-key-to-the-assembly-and-deploy"></a>Paso 1A: asignar una clave segura para el ensamblado e implementar  
 Utilice el procedimiento siguiente para asignar una clave segura para el ensamblado y, a continuación, implemente el ensamblado.  
  
#### <a name="to-assign-a-strong-key-and-deploy-the-assembly"></a>Para asignar una clave segura e implementar el ensamblado  
  
1. Inicie un **símbolo del sistema de Visual Studio 2012**.  
  
2. En el [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] símbolo, cambie el directorio a la \< *unidad*\>: \Program Files\Microsoft BizTalk \<versión\> Acelerador para HL7\SDK\Interrogative Carpeta tutorial.  
  
3. En el símbolo del sistema, escriba **sn – k key.snk**y, a continuación, presione **ENTRAR**. Asegúrese de que aparece un mensaje de éxito en la ventana de salida.  
  
   > [!NOTE]
   >  Si no aparece el mensaje correcto, use [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] para solucionar problemas de su ensamblado.  
  
4. En el Explorador de soluciones, haga clic en **Interrogative_2XSchemas** del proyecto y, a continuación, haga clic en **propiedades**.  
  
5. En el cuadro de diálogo páginas de propiedades Interrogative_2XSchemas, haga clic en **ensamblado**.  
  
6. En el panel derecho, desplácese hacia abajo hasta la **nombre seguro** sección, haga clic en el campo a la derecha del **archivo clave de ensamblado**y, a continuación, haga clic en el botón de puntos suspensivos (...).  
  
7. En el cuadro de diálogo de archivo de clave de ensamblado, vaya a \< *unidad*\>: \Program Files\Microsoft BizTalk \<versión\> acelerador HL7\SDK\Interrogative tutorial, haga clic en **key.snk**y, a continuación, haga clic en **abierto**.  
  
8. En el cuadro de diálogo páginas de propiedades Interrogative_2XSchemas, haga clic en **Aceptar** para guardar los cambios.  
  
9. En [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], en el Explorador de soluciones, haga clic en **Interrogative_2XSchemas** del proyecto y, a continuación, haga clic en **implementar**. Asegúrese de que aparece un mensaje de éxito en la ventana de salida.  
  
   > [!NOTE]
   >  Si no aparece el mensaje de la implementación correcta, utilice [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] para solucionar problemas de implementación.  
  
   Continúe con [paso 2: crear los esquemas comunes para V2.4](../../adapters-and-accelerators/accelerator-hl7/step-2-create-common-schemas-for-v2-4.md).