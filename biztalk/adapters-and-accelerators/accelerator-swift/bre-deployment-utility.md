---
title: "Utilidad de implementación de BRE | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- BRE Deployment utility
- deploying, BRE Deployment utility
ms.assetid: 5b04592c-ea1e-4ded-8ca4-dcd051d6375e
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 731f40a75d898369cfc730ba5cb4f25c199e1333
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="bre-deployment-utility"></a>Utilidad de implementación de BRE
Puede usar la utilidad de implementación del BRE para publicar e implementar los vocabularios del motor de reglas de negocios (BRE) y las directivas necesarias para un esquema SWIFT. Para habilitar la validación de BRE para el tipo de mensaje, es necesario publicar e implementar estas directivas y vocabularios.  
  
 También puede implementar reglas de negocios mediante las guías de versión de estándares de SWIFT (SRGs) para identificar las reglas requeridas y, a continuación, el [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] herramienta de Compositor de reglas de negocios para implementar las directivas y vocabularios. Sin embargo, es mucho más fácil usar la utilidad de implementación del BRE.  
  
 La utilidad de implementación del BRE lleva a cabo lo siguiente:  
  
-   Examina el ensamblado implementado que especifique y determina los esquemas de mensaje que ha implementado para el ensamblado.  
  
-   Publica el [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]_CodeLists.xml y [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]vocabularios _Functions.xml necesarios para [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] de procesamiento de reglas de negocios.  
  
-   Publica e implementa las SWIFT base directivas (directiva de referencia, la directiva de identificador de entidad y directivas de reglas de red) asociadas a los esquemas de mensaje.  
  
-   Publica e implementa la directiva principal y la directiva de validación asociados a cada esquema de mensaje.  
  
-   Genera un archivo de registro que indica todos los pasos que se tarda. Este archivo es BREDeploymentLog.txt en la \< *unidad*>: \Documents and carpeta Settings\All Users\Application Data.  
  
    > [!NOTE]
    >  La utilidad de implementación del BRE no implementa la directiva de maestro de BIC y la directiva de validación de BIC. Debe implementarlas mediante el Asistente para implementación de motor de reglas.  
  
    > [!NOTE]
    >  Si ha instalado [!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)] en un directorio no predeterminado (que no sea de C:\Program Files\Microsoft [!INCLUDE[btaA4SWIFTNoVersion](../../includes/btaa4swiftnoversion-md.md)]), o está trabajando en un equipo de 64 bits, la utilidad de implementación del BRE no funcionará correctamente hasta que cambie las rutas de acceso en el Archivo BREDeployment.exe.config. Este archivo de configuración se encuentra en la \< *unidad*>: \Program [!INCLUDE[btaA4SWIFTNoVersion](../../includes/btaa4swiftnoversion-md.md)]\SDK\Tools carpeta. Para actualizar la configuración de la utilidad, abra BREDeployment.exe.config en el Bloc de notas y cambiar las carpetas de las directivas de base, esquemas y directorios de vocabulario.  
  
 También puede usar la utilidad de implementación a la inversa de este proceso, anular la implementación y anular la publicación de las directivas y vocabularios. La utilidad ha ambos implementar y anular la implementación de funcionalidad.  
  
### <a name="to-use-the-bre-deployment-utility"></a>Para usar la utilidad de implementación del BRE  
  
1.  Haga clic en **iniciar**, seleccione **programas**, seleccione **Acelerador de Microsoft BizTalk para SWIFT**y, a continuación, haga clic en **utilidad de implementación del BRE**.  
  
2.  En la utilidad de implementación del BRE, haga clic en **examinar**.  
  
3.  Seleccione el ensamblado implementado o ensamblados para los que desea publicar, implementar directivas y vocabularios y, a continuación, haga clic en **Aceptar**.  
  
4.  Haga clic en **implementar**.  
  
    > [!NOTE]
    >  En función de los esquemas que ha implementado con ese ensamblado, la utilidad de implementación del BRE pasa por el proceso de identificar las reglas relacionadas y publicarlas para su uso con el BRE. Cuando haya finalizado, la utilidad de implementación del BRE muestra el siguiente mensaje: **ha completado la implementación**. Use el Compositor de reglas de negocios para comprobar una implementación correcta.  
  
    > [!NOTE]
    >  Para anular la implementación de las directivas y vocabularios, haga clic en **anular la implementación**. El proceso de anular la implementación no anular la implementación de los vocabularios A4SWIFT_CodeLists.xml y A4SWIFT_Functions.xml, que pueden ser utilizados por otras directivas implementadas.  
  
5.  Busque \< *unidad*>: \Documents and Settings\All Users\Application datos para confirmar que la utilidad creado el registro de archivo BREDeploymentLog.txt.  
  
    > [!NOTE]
    >  Puede abrir el archivo de registro mediante un editor de texto para confirmar cada paso de implementación.  
  
## <a name="see-also"></a>Vea también  
 [Herramientas](../../adapters-and-accelerators/accelerator-swift/tools.md)