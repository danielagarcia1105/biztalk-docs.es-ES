---
title: 'Paso 3: Asignar un nombre seguro al ensamblado | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- assemblies
- message enrichment tutorial, strong name assemblies
- strong name assemblies
ms.assetid: 8709e4e1-b428-42af-ba3c-08225c17a9eb
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 591423d04d8551620036e94a6ec780271e04feec
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37012629"
---
# <a name="step-3-assign-a-strong-name-to-the-assembly"></a>Paso 3: Asignar un nombre seguro al ensamblado
En este paso, creará y asignar un nombre seguro para el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] ensamblado. Un ensamblado con nombre seguro proporciona varias ventajas de seguridad y es necesario para implementar el proyecto en la caché global de ensamblados (GAC). Un nombre seguro garantiza la exclusividad del ensamblado mediante la asignación de una firma digital y un único par de claves. Además, esto protege el linaje del ensamblado al garantizar que nadie puede generar una versión posterior del ensamblado. Por último, un nombre seguro proporciona una comprobación de integridad importante para garantizar que el contenido del ensamblado no ha cambiado desde que se compiló.  
  
### <a name="to-assign-a-strong-name-to-the-assembly"></a>Para asignar un nombre seguro al ensamblado  
  
1. Iniciar **símbolo del sistema de Visual Studio**.  
  
   > [!NOTE]
   >  Si ya ha creado una clave de nombre seguro, puede volver a usar.  
  
2. En el símbolo del sistema, vaya a<strong>\<*unidad*\>: \Tutorial\BTAHL7V22Common</strong> (donde \< *unidad* \> es la letra de unidad de instalación) y, a continuación, presione **ENTRAR**.  
  
3. En el símbolo del sistema, escriba **sn – k key.snk**y, a continuación, presione **ENTRAR**. Aparece un mensaje indicando que [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] escribió el par de claves en el archivo de clave de key.snk.  
  
4. En el Explorador de soluciones, haga clic en el **BTAHL7V22Common** del proyecto y, a continuación, haga clic en **propiedades**.  
  
5. En el cuadro de diálogo páginas de propiedades BTAHL7V22Common, haga clic en **ensamblado**.  
  
6. En el panel derecho, desplácese hacia abajo hasta la **nombre seguro** sección, haga clic en el campo a la derecha del **archivo clave de ensamblado**y, a continuación, haga clic en el botón de puntos suspensivos (...).  
  
7. En el cuadro de diálogo de archivo de clave de ensamblado, vaya a  **\< *unidad*\>: \Tutorial\BTAHL7V22Common\key.snk**, haga clic en **abierto**y, a continuación, haga clic en **Aceptar**.  
  
8. En el Explorador de soluciones, haga clic en **BTAHL7V22Common**y, a continuación, haga clic en **implementar**. [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] crea un ensamblado que puede hacer referencia desde su próximo proyecto.  
  
9. Repita los pasos del 4 al 8 para el proyecto BTAHL7V2XCommon.  
  
   Continúe con [paso 4: crear los esquemas](../../adapters-and-accelerators/accelerator-hl7/step-4-create-the-schemas.md).  
  
## <a name="see-also"></a>Vea también  
 [Tutorial de enriquecimiento de mensajes](../../adapters-and-accelerators/accelerator-hl7/message-enrichment-tutorial.md)