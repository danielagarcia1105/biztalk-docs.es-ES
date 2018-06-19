---
title: 'Lección 2: Confirmar la implementación mediante la herramienta de Compositor de reglas de negocios | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- business rules, verifying
- verifying, business rules
- verifying, Business Rule Composer tool
- business rules, Business Rule Composer tool
- Business Rule Composer tool
ms.assetid: 337dc469-cf9e-406b-90ae-0f580b17d7c9
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3115dc425fedca9019f0e5e5171f7234e6fbdbb2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22210244"
---
# <a name="lesson-2-confirming-the-deployment-using-the-business-rule-composer-tool"></a>Lección 2: Confirmar la implementación mediante la herramienta de Compositor de reglas de negocios
En esta lección, confirme que la herramienta de Compositor de reglas de negocios creado los vocabularios e implementado las directivas. Un vocabulario es una colección de elementos de vocabulario utilizados en la composición de regla. Las directivas son colecciones de reglas de negocios y tienen asignada una versión.  
  
### <a name="to-confirm-the-deployment-using-the-business-rule-composer-tool"></a>Para confirmar la implementación mediante la herramienta de Compositor de reglas de negocios  
  
1.  Iniciar **Compositor de reglas de negocios** en BizTalk Server.  
  
2.  En el cuadro de diálogo Abrir almacén de reglas, haga clic en **Aceptar**.  
  
3.  En el panel Explorador de hechos de la herramienta de Compositor de reglas de negocios, confirme que los vocabularios que desea que aparezcan en el Explorador de hechos, como se muestra en la ilustración siguiente.  
  
     ![](../../adapters-and-accelerators/accelerator-swift/media/tut2-scrn2.gif "Tut2_scrn2")  
  
4.  En el Explorador de directivas, confirme que la herramienta de Compositor de reglas de negocio implementa las siguientes directivas:  
  
     MT103_Master_Policy  
  
     MT103_Validation_Policy  
  
     SWIFT_NetworkRule149_Policy  
  
     SWIFT_NetworkRule150_Policy  
  
     SWIFT_NetworkRule151_Policy  
  
     SWIFT_NetworkRule175_Policy  
  
     SWIFT_NetworkRule2_Policy  
  
     SWIFT_NetworkRule201_Policy  
  
     SWIFT_NetworkRule202_Policy  
  
     SWIFT_NetworkRule203_Policy  
  
     SWIFT_NetworkRule204_Policy  
  
     SWIFT_NetworkRule205_Policy  
  
     SWIFT_NetworkRule206_Policy  
  
     SWIFT_NetworkRule207_Policy  
  
     SWIFT_NetworkRule209_Policy  
  
     SWIFT_NetworkRule210_Policy  
  
     SWIFT_NetworkRule212_Policy  
  
     SWIFT_NetworkRule213_Policy  
  
     SWIFT_NetworkRule215_Policy  
  
     SWIFT_NetworkRule216_Policy  
  
     SWIFT_NetworkRule217_Policy  
  
     SWIFT_NetworkRule218_Policy  
  
     SWIFT_NetworkRule244_Policy  
  
     SWIFT_NetworkRule245_Policy  
  
     SWIFT_NetworkRule81_Policy  
  
     SWIFT_PartyIdentifier_Policy  
  
     SWIFT_Reference_Policy  
  
### <a name="to-view-a-policy"></a>Para ver una directiva  
  
1.  En el panel Explorador de directivas del compositor de reglas de negocios, asegúrese de que el **SWIFT_NetworkRule149_Policy** se expande y, a continuación, expanda el **versión 1.0 – implementada** nodo.  
  
2.  Haga doble clic en el **Validate_MT103** nodo para abrirlo.  
  
     La directiva se abre en el panel del editor en el lado derecho de la pantalla.  
  
 Continúe con [módulo 7: probar una instancia de archivo sin formato válido](../../adapters-and-accelerators/accelerator-swift/module-7-testing-a-valid-flat-file-instance.md).