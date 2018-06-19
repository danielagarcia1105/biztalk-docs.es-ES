---
title: 'Módulo 6: Implementar las reglas de negocios | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- tutorial, deploying business rules
- deploying, business rules
- business rules
ms.assetid: e8fb8993-3450-4795-80fd-ff28bff8fe97
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8e890456b7ff3e467a0f513a261d12a52f92689f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22207996"
---
# <a name="module-6-deploying-the-business-rules"></a>Módulo 6: Implementar las reglas de negocios
En este módulo, implementar las reglas de negocios, confirme el registro de instalación y confirmar la implementación mediante la herramienta de Compositor de reglas de negocios.  
  
 Utilizar reglas de negocios para asegurarse de que [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] mensajes cumplen con las especificaciones de formato, especificaciones de los campos y las reglas de red valida tal como se define en la sociedad de normas de telecomunicaciones financieros bancos vinculados (SWIFT) en todo el mundo. Especificaciones de formato relativos a la estructura del mensaje como un todo y especificaciones de los campos de detalle cada campo en el mensaje. Reglas de red que se valida se aplican a las validaciones de campos cruzados y son complejas por naturaleza.  
  
 A4SWIFT proporciona especificaciones de esquema XSD para cada mensaje. El Desensamblador de A4SWIFT (DASM) y de ensamblador (ASM) usar el esquema para analizar o serializar y validar los mensajes de archivo sin formato nativo. Las validaciones se limitan a las especificaciones de formato y especificaciones de los campos que codifica el esquema. Sin embargo, no puede codificar algunos formatos y las reglas relacionadas dentro del esquema de campo.  
  
 A4SWIFT también incluye un conjunto de reglas de negocios que siguen las guías de versión de estándares de SWIFT (SRG). El motor de reglas de negocios (BRE) de BizTalk Server llama a las directivas de A4SWIFT y aplica las reglas de negocios de A4SWIFT.  
  
 Estas reglas de negocios se incluyen debido a las validaciones complejas relacionadas con formato y campos y reglas validar de red que están más allá de la capacidad física del esquema. Los componentes de SWIFT DASM o ASM dentro de una canalización de envío o recepción llaman el BRE.  
  
 Activar las validaciones o desactivar cambiando el **BREValidation** propiedad para el DASM dentro de la canalización.  
  
 Esta sección contiene:  
  
-   [Lección 1: Implementar las reglas de negocios relacionadas](../../adapters-and-accelerators/accelerator-swift/lesson-1-deploying-the-related-business-rules.md)  
  
-   [Lección 2: Confirmar la implementación mediante la herramienta de Compositor de reglas de negocios](../../adapters-and-accelerators/accelerator-swift/lesson-2-confirming-the-deployment-using-the-business-rule-composer-tool.md)