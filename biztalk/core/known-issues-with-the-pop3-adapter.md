---
title: Problemas conocidos con el adaptador de POP3 | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b6d621a2-4801-44fe-a266-d4c05ac82633
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4bc86b2ae14b04b160f7387f870615116e659b3f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22261948"
---
# <a name="known-issues-with-the-pop3-adapter"></a>Problemas conocidos del adaptador de POP3
Esta sección contiene información que puede servir de ayuda para evitar errores.  
  
## <a name="known-issues"></a>Problemas conocidos  
  
#### <a name="the-pop3-adapter-fails-to-process-documents-when-running-on-a-64-bit-operating-system"></a>Se produce un error en el adaptador de POP3 al procesar documentos cuando se ejecuta en un sistema operativo de 64 bits  
  
##### <a name="problem"></a>Problema  
 El adaptador de POP3 no procesará documentos cuando se ejecute en un sistema operativo de 64 bits.  
  
##### <a name="cause"></a>Causa  
 El controlador del adaptador de POP3 no puede ejecutarse en una instancia de host de 64 bits.  
  
##### <a name="resolution"></a>Solución  
 Si el adaptador de POP3 se ejecuta en un equipo de 64 bits, configure los controladores del adaptador de POP3 para que se ejecuten en un host de 32 bits. Esta opción está disponible en la página de propiedades de host, a la que se tiene acceso desde la consola de administración de BizTalk.  
  
## <a name="see-also"></a>Vea también  
 [Solucionar problemas del adaptador de POP3](../core/troubleshooting-the-pop3-adapter.md)