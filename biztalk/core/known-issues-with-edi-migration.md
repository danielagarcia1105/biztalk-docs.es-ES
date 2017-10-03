---
title: "Problemas conocidos con la migración de EDI | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: cc5d0a7e-974d-4e3b-a406-412420779456
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b642c56151750232be3d17aa3f3cb3b8c858474c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="known-issues-with-edi-migration"></a>Problemas conocidos de la migración de EDI
Este tema describe los problemas conocidos en la migración del modelo de adaptador EDI/HIPAA en [!INCLUDE[btsBizTalkServer2006](../includes/btsbiztalkserver2006-md.md)] a [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)].  
  
## <a name="credential-information-not-migrated-for-a-file-send-port"></a>Información de credenciales no migradas para un puerto de envío de archivo  
 Al migrar un puerto de envío con el tipo de transporte de archivo, las credenciales empleadas para obtener acceso a la carpeta de archivos cuando el host no dispone de acceso al recurso compartido de red no se migran. Tras la migración, deberá habilitar las credenciales manualmente, y escriba el nombre de usuario y contraseña que se utilizará, en la **autenticación** página de la **propiedades de transporte de archivo** cuadro de diálogo.  
  
## <a name="see-also"></a>Vea también  
 [Solución de problemas de soluciones EDI y AS2](../core/troubleshooting-edi-and-as2-solutions.md)   
 [Utilidades de migración de EDI](../core/edi-migration-utilities.md)