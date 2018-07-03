---
title: Utilidad de implementación de BRE | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- BRE Deployment utility
- deploying, BRE Deployment utility
ms.assetid: 5b04592c-ea1e-4ded-8ca4-dcd051d6375e
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5b2449795a52bd26bed0326a3aa2fcf57f8bb552
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37010157"
---
# <a name="bre-deployment-utility"></a>Utilidad de implementación de BRE
Puede usar la utilidad de implementación de BRE para publicar e implementar los vocabularios del motor de reglas de negocios (BRE) y las directivas requeridas para un esquema SWIFT. Es necesario publicar e implementar estos vocabularios y directivas para habilitar la validación del BRE para el tipo de mensaje.  
  
 También puede implementar las reglas de negocios mediante las guías de versión de los estándares de SWIFT (SRGs) para identificar las reglas necesarias y, a continuación, usar Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] herramienta de Compositor de reglas de negocios para implementar las directivas y vocabularios. Sin embargo, es mucho más fácil mediante la utilidad de implementación de BRE.  
  
 La utilidad de implementación de BRE lleva a cabo lo siguiente:  
  
- Examina el ensamblado implementado que especifique y determina los esquemas de mensaje que ha implementado para el ensamblado.  
  
- Publica el [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]_CodeLists.xml y [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]_Functions.xml los vocabularios necesarios para Microsoft [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] procesamiento de reglas de negocios.  
  
- Publica e implementa el SWIFT bases directivas (directiva de referencia, la directiva de identificador de entidad y directivas de reglas de red) asociadas con los esquemas de mensaje.  
  
- Publica e implementa la directiva principal y la directiva de validación asociado con cada esquema de mensaje.  
  
- Genera un archivo de registro que indica todos los pasos que se tarda. Este archivo es BREDeploymentLog.txt en el \< *unidad*\>: \Documents and carpeta Settings\All Users\Application Data.  
  
  > [!NOTE]
  >  La utilidad de implementación de BRE no implementa la directiva de maestro de BIC y directiva de validación de BIC. Debe implementar estos con el Asistente para la implementación del motor de reglas.  
  > 
  > [!NOTE]
  >  Si ha instalado [!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)] en un directorio que no sea predeterminado (que no sean C:\Program Files\Microsoft [!INCLUDE[btaA4SWIFTNoVersion](../../includes/btaa4swiftnoversion-md.md)]), o está trabajando en un equipo de 64 bits, la utilidad de implementación de BRE no funcionará correctamente hasta que cambie las rutas de acceso en el Archivo BREDeployment.exe.config. Este archivo de configuración se encuentra en la \< *unidad*\>: \Program Files\Microsoft [!INCLUDE[btaA4SWIFTNoVersion](../../includes/btaa4swiftnoversion-md.md)]\SDK\Tools carpeta. Para actualizar la configuración de la utilidad, abra BREDeployment.exe.config en el Bloc de notas y cambie las carpetas para las directivas de bases, esquemas y los directorios de vocabulario.  
  
  También puede usar la utilidad de implementación para invertir este proceso, anular la implementación y anular la publicación de las directivas y vocabularios. La utilidad ha ambos implementar y anular la implementación de funcionalidad.  
  
### <a name="to-use-the-bre-deployment-utility"></a>Para usar la utilidad de implementación de BRE  
  
1.  Haga clic en **iniciar**, apunte a **programas**, apunte a **Acelerador de Microsoft BizTalk para SWIFT**y, a continuación, haga clic en **utilidad de implementación de BRE**.  
  
2.  En la utilidad de implementación de BRE, haga clic en **examinar**.  
  
3.  Seleccione el ensamblado implementado o para el que desea publicar e implementar directivas y vocabularios y, a continuación, haga clic en los ensamblados **Aceptar**.  
  
4.  Haga clic en **implementar**.  
  
    > [!NOTE]
    >  Según los esquemas que ha implementado con ese ensamblado, la utilidad de implementación de BRE recorre el proceso de identificar las reglas relacionadas y publicarlas para su uso con el BRE. Cuando haya terminado, la utilidad de implementación de BRE muestra el siguiente mensaje: **implementación se haya completado**. Usar el Compositor de reglas de negocio para comprobar la implementación correcta.  
  
    > [!NOTE]
    >  Para anular la implementación de las directivas y vocabularios, haga clic en **Undeploy**. El proceso de anular la implementación no anular la implementación de los vocabularios A4SWIFT_CodeLists.xml y A4SWIFT_Functions.xml, que podrían utilizarse por otras directivas implementadas.  
  
5.  Busque \< *unidad*\>: \Documents and Settings\All Users\Application Data para confirmar que la utilidad creado el registro de archivo BREDeploymentLog.txt.  
  
    > [!NOTE]
    >  Puede abrir el archivo de registro mediante un editor de texto para confirmar cada paso de implementación.  
  
## <a name="see-also"></a>Vea también  
 [Herramientas](../../adapters-and-accelerators/accelerator-swift/tools.md)