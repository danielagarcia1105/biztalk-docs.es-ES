---
title: 'Lección 1: Envío de un archivo plano de ejemplo | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- testing, flat files
- submitting, flat files
- flat files, testing
- flat files, submitting
ms.assetid: 3064246d-19d5-48c5-af13-3ea075355147
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 63e93b348e90bd01607d96b1ea86a6751f00b161
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37014549"
---
# <a name="lesson-1-submitting-a-sample-flat-file"></a>Lección 1: Envío de un archivo plano de ejemplo
Enviar un archivo plano de ejemplo para probar la solución.  
  
### <a name="to-submit-a-sample-mt103-flat-file"></a>Para enviar un archivo plano de ejemplo MT103  
  
1. Copie el archivo MT103_Sample.txt desde \< *unidad*\>: Acelerador de BizTalk para SWIFT\SDK\Tutorial \Program Files\Microsoft a \< *unidad* \>: Carpeta \Labs\Inbound\FlatFile.  
  
2. Compruebe que, tras unos instantes, el archivo MT103_Sample.txt desaparece de la carpeta.  
  
3. Vaya a la \< *unidad*\>: carpeta \Labs\Outbound. Compruebe que la carpeta contiene un archivo denominado {GUID} .xml.  
  
4. Haga clic en la extensión de archivo {GUID} .xml, apunte a **abrir con**y, a continuación, haga clic en **el Bloc de notas**. Lo mismo para el archivo denominado MT103_Sample.txt desde \< *unidad*\>: Acelerador de BizTalk para SWIFT\SDK\Tutorial \Program Files\Microsoft. Compruebe que el contenido dentro de las etiquetas del archivo XML es el mismo que el contenido del archivo plano.  
  
   > [!NOTE]
   >  No elimine el archivo resultante; se usará en una lección posterior.  
  
   Continúe con [lección 2: enviar un mensaje MT103 que no es válido](../../adapters-and-accelerators/accelerator-swift/lesson-2-submitting-an-mt103-message-that-is-not-valid.md).