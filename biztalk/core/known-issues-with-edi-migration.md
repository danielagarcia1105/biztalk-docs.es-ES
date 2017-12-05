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
ms.openlocfilehash: bd62c1c965e814929537a62dc5d49be7e017ae3b
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/01/2017
---
# <a name="known-issues-with-edi-migration"></a><span data-ttu-id="5e0ae-102">Problemas conocidos de la migración de EDI</span><span class="sxs-lookup"><span data-stu-id="5e0ae-102">Known Issues with EDI Migration</span></span>
<span data-ttu-id="5e0ae-103">En este tema se describe problemas conocidos con la migración desde el modelo de adaptador EDI e HIPAA en [!INCLUDE[btsBizTalkServer2006](../includes/btsbiztalkserver2006-md.md)] a BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="5e0ae-103">This topic describes known issues with migration from the EDI/HIPAA adapter model in [!INCLUDE[btsBizTalkServer2006](../includes/btsbiztalkserver2006-md.md)] to BizTalk Server.</span></span>  
  
## <a name="credential-information-not-migrated-for-a-file-send-port"></a><span data-ttu-id="5e0ae-104">Información de credenciales no migradas para un puerto de envío de archivo</span><span class="sxs-lookup"><span data-stu-id="5e0ae-104">Credential Information Not Migrated for a FILE Send Port</span></span>  
 <span data-ttu-id="5e0ae-105">Al migrar un puerto de envío con el tipo de transporte de archivo, las credenciales empleadas para obtener acceso a la carpeta de archivos cuando el host no dispone de acceso al recurso compartido de red no se migran.</span><span class="sxs-lookup"><span data-stu-id="5e0ae-105">When migrating a send port using the FILE transport type, the credentials used to access the file folder when the host does not have access to the network share will not be migrated.</span></span> <span data-ttu-id="5e0ae-106">Tras la migración, deberá habilitar las credenciales manualmente, y escriba el nombre de usuario y contraseña que se utilizará, en la **autenticación** página de la **propiedades de transporte de archivo** cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="5e0ae-106">After migration, you will need to manually enable credentials, and enter the user name and password to be used, on the **Authentication** page of the **FILE Transport Properties** dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5e0ae-107">Vea también</span><span class="sxs-lookup"><span data-stu-id="5e0ae-107">See Also</span></span>  
 <span data-ttu-id="5e0ae-108">[Solución de problemas de soluciones EDI y AS2](../core/troubleshooting-edi-and-as2-solutions.md) </span><span class="sxs-lookup"><span data-stu-id="5e0ae-108">[Troubleshooting EDI and AS2 Solutions](../core/troubleshooting-edi-and-as2-solutions.md) </span></span>  
 [<span data-ttu-id="5e0ae-109">Utilidades de migración de EDI</span><span class="sxs-lookup"><span data-stu-id="5e0ae-109">EDI Migration Utilities</span></span>](../core/edi-migration-utilities.md)