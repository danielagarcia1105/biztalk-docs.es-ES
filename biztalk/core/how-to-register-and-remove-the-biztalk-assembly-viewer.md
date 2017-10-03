---
title: "Cómo registrar y quitar el Visor de ensamblado de BizTalk | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6f80b906-0a9e-4bcd-984d-db4550f2e51f
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: deae453be1a89049f223e2da9813e449d68eeb07
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-register-and-remove-the-biztalk-assembly-viewer"></a>Cómo registrar y quitar el Visor de ensamblado de BizTalk
El Visor de ensamblado de BizTalk no se registra automáticamente durante la instalación de BizTalk Server. Para registrar y quitar el Visor de ensamblado de BizTalk, siga estos pasos.  
  
### <a name="to-add-assembly-viewer-to-the-windows-registry"></a>Para agregar el Visor de ensamblado al Registro de Windows  
  
1.  Desde el **iniciar** menú, haga clic en **ejecutar**.  
  
2.  En el cuadro de diálogo Ejecutar, escriba **cmd**.  
  
3.  Desde la línea de comandos, vaya a \< *carpeta de instalación de BizTalk Server*> \Developer Tools\ donde se encuentra BTSAsmExt.dll.  
  
4.  En la línea de comandos, escriba:  
  
     regsvr32 BTSAsmExt.dll  
  
5.  Para comenzar a usar la vista Ensamblado, cierre sesión y, a continuación, vuelva a iniciarla en el equipo.  
  
### <a name="to-remove-assembly-viewer-from-the-windows-registry"></a>Para quitar el Visor de ensamblado del Registro de Windows  
  
1.  Desde el **iniciar** menú, haga clic en **ejecutar**.  
  
2.  En el **ejecutar** cuadro de diálogo, escriba **cmd**.  
  
3.  Desde la línea de comandos, vaya a \< *carpeta de instalación de BizTalk Server*> \Developer Tools\ donde se encuentra BTSAsmExt.dll.  
  
4.  En la línea de comandos, escriba:  
  
     regsvr32/u BTSAsmExt.dll  
  
5.  Para completar la eliminación, cierre sesión y, a continuación, vuelva a iniciarla en el equipo.  
  
## <a name="see-also"></a>Vea también  
 [Ver ensamblados con el Visor de ensamblado de BizTalk](../core/viewing-assemblies-with-the-biztalk-assembly-viewer.md)