---
title: 'Módulo 6: Implementación de las reglas de negocio | Microsoft Docs'
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
ms.openlocfilehash: 389d8038b5a216f90d85399eeefaebde86284c71
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36972845"
---
# <a name="module-6-deploying-the-business-rules"></a>Módulo 6: Implementación de las reglas de negocios
En este módulo, implementar las reglas de negocios, confirme el registro de instalación y confirmar la implementación mediante la herramienta Compositor de reglas de negocios.  
  
 Usar reglas de negocios para asegurarse de que Microsoft [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] mensajes cumplen con las especificaciones de formato, especificaciones de los campos y las reglas de red validado tal como se define en la sociedad de estándares de telecomunicaciones financieros entre bancos más (SWIFT) en todo el mundo. Especificaciones de formato se refieren a la estructura del mensaje como un todo y cada campo en el mensaje de detalles de especificaciones de los campos. Las reglas de red validado se aplican a las validaciones de campos cruzados y son complejas por naturaleza.  
  
 A4SWIFT proporciona especificaciones de esquema XSD para cada mensaje. El Desensamblador de A4SWIFT (DASM) y de ensamblador (ASM) usan el esquema para analizar o serializar y validar los mensajes de archivo sin formato nativos. Las validaciones se limitan a las especificaciones de formato y especificaciones de los campos que codifica el esquema. Sin embargo, no puede codificar algunos formatos y reglas relacionadas están dentro del esquema de campo.  
  
 A4SWIFT también incluye un conjunto de reglas de negocios que siga las guías de versión de estándares (SRG) de SWIFT. El motor de reglas de negocios (BRE) de BizTalk Server llama a las directivas de A4SWIFT y aplica las reglas de negocios de A4SWIFT.  
  
 Estas reglas de negocios se incluyen debido a las complejas validaciones relativas a dar formato y los campos y reglas de red validado que superan la capacidad física del esquema. Los componentes de SWIFT DASM o ASM dentro de una canalización de envío o recepción llaman el BRE.  
  
 Activar las validaciones o desactivar cambiando el **BREValidation** propiedad para el DASM dentro de la canalización.  
  
 Esta sección contiene:  
  
-   [Lección 1: Implementación de las reglas de negocio relacionadas](../../adapters-and-accelerators/accelerator-swift/lesson-1-deploying-the-related-business-rules.md)  
  
-   [Lección 2: Confirmación de la implementación mediante la herramienta Compositor de reglas de negocio](../../adapters-and-accelerators/accelerator-swift/lesson-2-confirming-the-deployment-using-the-business-rule-composer-tool.md)