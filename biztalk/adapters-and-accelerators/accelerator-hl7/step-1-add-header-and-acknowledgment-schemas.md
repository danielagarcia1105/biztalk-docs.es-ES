---
title: 'Paso 1: Agregar esquemas de encabezado y confirmación | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 808132bf-02e7-4ff4-b914-9fae5d27e5fd
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ae0712e2ee4498b8f6f2eb8cb9527aa8ee8e4582
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37011319"
---
# <a name="step-1-add-header-and-acknowledgment-schemas"></a>Paso 1: Agregar esquemas de encabezado y confirmación
En este paso, creará un nuevo proyecto basado en la plantilla de proyecto BTAHL72XCommon. Esta plantilla contiene los tres esquemas comunes para los encabezados del mensaje (MSH_25_GLO_DEF.xsd) y confirmaciones (ACK_24_GLO_DEF.xsd) y (ACK_25_GLO_DEF.xsd). Debe incluir por lo que estos esquemas en un proyecto que el Acelerador de BizTalk para HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) compila y valida los encabezados de mensaje y las confirmaciones correctamente. Este proceso es común en todas las versiones de esquema de [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] 2.X.  
  
 También crea una clave segura, asignarlo al ensamblado y, a continuación, implemente el ensamblado. La clave segura proporciona seguridad e identidad para el ensamblado y es necesaria para la implementación. Al implementar el ensamblado, se almacena en la base de datos de configuración (también conocido como la base de datos de administración de BizTalk) y la caché global de ensamblados (GAC).  
  
### <a name="to-create-the-project-and-add-header-and-acknowledgment-schemas"></a>Para crear el proyecto y agregar esquemas de encabezado y confirmación  
  
1. En [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], en el **archivo** menú, elija **New**y, a continuación, haga clic en **proyecto**.  
  
2. En el cuadro de diálogo nuevo proyecto, en el **tipos de proyecto** lista, expanda **proyectos de BizTalk**y, a continuación, haga clic en **BTAHL7Projects**.  
  
3. En el **plantillas** lista, haga clic en **proyecto BTAHL7V2XCommon**.  
  
4. En el **nombre** , escriba **BTAHL7V2XCommon** como el nombre del proyecto.  
  
5. En el **ubicación** cuadro, vaya a **\<** <em>unidad</em>**:\>\Batching Tutorial**.  
  
6. Haga clic en **Aceptar**.  
  
> [!NOTE]
>  En el Explorador de soluciones, los tres esquemas (MSH_25_GLO_DEF.xsd, ACK_24_GLO_DEF.xsd y ACK_25_GLO_DEF.xsd) se incluyen en el proyecto.  
  
### <a name="to-assign-a-strong-key-to-the-assembly-and-deploy"></a>Para asignar una clave segura para el ensamblado e implementar  
  
1. Abra **símbolo del sistema de Visual Studio**.  
  
2. En el [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] símbolo del sistema, vaya a la **\<** <em>unidad</em>**\>: \Batching Tutorial** carpeta.  
  
3. En el símbolo del sistema, escriba **sn – k key.snk**, y, a continuación, presione ENTRAR. Asegúrese de que aparece un mensaje de éxito en la ventana de salida.  
  
   > [!NOTE]
   >  Si no aparece el mensaje correcto, use [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] para solucionar problemas de su ensamblado.  
  
4. En el Explorador de soluciones, haga clic en **proyecto BTAHL7V2Xcommon**y, a continuación, haga clic en **propiedades**.  
  
5. En el **página de propiedades de proyecto BTAHL7V2XCommon** cuadro de diálogo, haga clic en **firma**.  
  
6. Comprobar **firmar el ensamblado** casilla de verificación.  
  
7. En **elegir un nombre seguro** desplegable archivo de clave de lista, seleccione  **\<Examinar... \>**.  
  
8. Vaya a \< *unidad*\>: Tutorial, seleccione \Batching **key.snk**y, a continuación, haga clic en **abierto**.  
  
9. En la ventana páginas de propiedades de proyecto BTAHL7V2XCommon, haga clic en **Aceptar** para guardar los cambios.  
  
10. En el Explorador de soluciones, haga clic en **proyecto BTAHL7V2Xcommon**y, a continuación, haga clic en **implementar**. Asegúrese de que aparece un mensaje de éxito en la ventana de salida.  
  
    > [!NOTE]
    >  Si no aparece el mensaje de la implementación correcta, utilice [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] para solucionar problemas de implementación.  
  
    Continúe con [paso 2: adición de esquemas comunes para v2.3.1](../../adapters-and-accelerators/accelerator-hl7/step-2-add-common-schemas-for-v2-3-1.md).