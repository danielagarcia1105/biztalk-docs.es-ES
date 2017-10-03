---
title: "Paso 1: Agregar encabezado y esquemas de confirmación | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 808132bf-02e7-4ff4-b914-9fae5d27e5fd
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0b5fb871bed9f6a4f54261db7e54587c65244344
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="step-1-add-header-and-acknowledgment-schemas"></a>Paso 1: Agregar encabezado y esquemas de confirmación
En este paso, creará un proyecto nuevo basado en la plantilla de proyecto de BTAHL72XCommon. Esta plantilla contiene los tres esquemas comunes para encabezados de mensaje (MSH_25_GLO_DEF.xsd) y confirmaciones (ACK_24_GLO_DEF.xsd) y (ACK_25_GLO_DEF.xsd). Debe incluir estos esquemas en un proyecto de modo que ese Acelerador de BizTalk para HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) genera o valida correctamente los encabezados de mensaje y confirmaciones. Este proceso es común en todas las versiones de esquema de [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] 2.X.  
  
 Crear una clave segura, asignar al ensamblado y, a continuación, implemente el ensamblado. La clave segura proporciona seguridad y la identidad para el ensamblado y es necesaria para la implementación. Al implementar el ensamblado, se almacena en la base de datos de configuración (también conocido como la base de datos de administración de BizTalk) y la caché de ensamblados global (GAC).  
  
### <a name="to-create-the-project-and-add-header-and-acknowledgment-schemas"></a>Para crear el proyecto y agregar esquemas de encabezado y de confirmación  
  
1.  En [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], en la **archivo** menú, elija **New**y, a continuación, haga clic en **proyecto**.  
  
2.  En el cuadro de diálogo nuevo proyecto, en la **tipos de proyecto** lista, expanda **proyectos de BizTalk**y, a continuación, haga clic en **BTAHL7Projects**.  
  
3.  En el **plantillas** lista, haga clic en **proyecto BTAHL7V2XCommon**.  
  
4.  En el **nombre** , escriba **BTAHL7V2XCommon** como el nombre del proyecto.  
  
5.  En el **ubicación** cuadro, vaya a  **\<**  *unidad***: > \Batching Tutorial**.  
  
6.  Haga clic en **Aceptar**.  
  
> [!NOTE]
>  En el Explorador de soluciones, se incluyen tres esquemas (MSH_25_GLO_DEF.xsd, ACK_24_GLO_DEF.xsd y ACK_25_GLO_DEF.xsd) en el proyecto.  
  
### <a name="to-assign-a-strong-key-to-the-assembly-and-deploy"></a>Para asignar una clave segura para el ensamblado e implementar  
  
1.  Abra  **[!INCLUDE[vs2012](../../includes/vs2012-md.md)] símbolo**.  
  
2.  En el [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] símbolo del sistema, vaya a la  **\<**  *unidad***>: \Batching Tutorial** carpeta.  
  
3.  En el símbolo del sistema, escriba **sn – k key.snk**, y, a continuación, presione ENTRAR. Asegúrese de que aparece un mensaje de confirmación en la ventana de salida.  
  
    > [!NOTE]
    >  Si no aparece el mensaje correcto, utilice [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] para solucionar problemas de su ensamblado.  
  
4.  En el Explorador de soluciones, haga clic en **proyecto BTAHL7V2Xcommon**y, a continuación, haga clic en **propiedades**.  
  
5.  En el **página de propiedades de proyecto BTAHL7V2XCommon** cuadro de diálogo, haga clic en **firma**.  
  
6.  Comprobar **firmar el ensamblado** casilla de verificación.  
  
7.  En **elegir un nombre seguro** desplegable archivo de clave de lista, seleccione  **\<Examinar... >**.  
  
8.  Vaya a \< *unidad*>: Tutorial, seleccione \Batching **key.snk**y, a continuación, haga clic en **abiertos**.  
  
9. En la ventana páginas de propiedades de proyecto BTAHL7V2XCommon, haga clic en **Aceptar** para guardar los cambios.  
  
10. En el Explorador de soluciones, haga clic en **proyecto BTAHL7V2Xcommon**y, a continuación, haga clic en **implementar**. Asegúrese de que aparece un mensaje de confirmación en la ventana de salida.  
  
    > [!NOTE]
    >  Si no aparece el mensaje de implementación correcta, utilice [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] para solucionar problemas de la implementación.  
  
 Continúe con [paso 2: agregar los esquemas comunes para v2.3.1](../../adapters-and-accelerators/accelerator-hl7/step-2-add-common-schemas-for-v2-3-1.md).