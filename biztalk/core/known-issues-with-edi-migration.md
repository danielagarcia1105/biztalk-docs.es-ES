---
title: Problemas conocidos con la migración de EDI | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: cc5d0a7e-974d-4e3b-a406-412420779456
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bd62c1c965e814929537a62dc5d49be7e017ae3b
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/01/2017
ms.locfileid: "26005973"
---
# <a name="known-issues-with-edi-migration"></a>Problemas conocidos de la migración de EDI
En este tema se describe problemas conocidos con la migración desde el modelo de adaptador EDI e HIPAA en [!INCLUDE[btsBizTalkServer2006](../includes/btsbiztalkserver2006-md.md)] a BizTalk Server.  
  
## <a name="credential-information-not-migrated-for-a-file-send-port"></a>Información de credenciales no migradas para un puerto de envío de archivo  
 Al migrar un puerto de envío con el tipo de transporte de archivo, las credenciales empleadas para obtener acceso a la carpeta de archivos cuando el host no dispone de acceso al recurso compartido de red no se migran. Tras la migración, deberá habilitar las credenciales manualmente, y escriba el nombre de usuario y contraseña que se utilizará, en la **autenticación** página de la **propiedades de transporte de archivo** cuadro de diálogo.  
  
## <a name="see-also"></a>Vea también  
 [Solución de problemas de soluciones EDI y AS2](../core/troubleshooting-edi-and-as2-solutions.md)   
 [Utilidades de migración de EDI](../core/edi-migration-utilities.md)