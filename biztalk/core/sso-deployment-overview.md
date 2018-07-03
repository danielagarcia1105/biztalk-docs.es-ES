---
title: Información general sobre la implementación de SSO | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- SSO, deploying example
- SSO, deploying
- deploying, SSO
- SSO, multiple computers
- examples, deploying
ms.assetid: 6eccee26-c392-41fe-97fb-3afe1685540f
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c98a12c11ae735945f4e69631e7211c05c0b9186
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37022370"
---
# <a name="sso-deployment-overview"></a>Información general sobre la implementación de SSO
El sistema de este ejemplo se implementa en tres dominios que contienen los siguientes equipos:  
  
 **Dominio ORCH.com**  
  
- Controlador de dominio ORCH  
  
- HIS1, el servidor HISSO  
  
- HIS2, el servidor secreto principal  
  
- HIS3, la base de datos de administración  
  
  **Dominio SQL.com**  
  
- Controlador de dominio SQL  
  
- SQL2, la base de datos de SSO  
  
  **Dominio HIS.com**  
  
- Controlador de dominio HIS  
  
- Base de datos HIS4  
  
  Los puntos clave que definen esta implementación son:  
  
- El domino ORCH.com y el dominio SQL.com tienen una relación de confianza selectiva bidireccional.  
  
- El dominio ORCH.com está configurado con nivel funcional [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)] o [!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)] nativo.  
  
- Todos los servicios SSO se ejecutan con una cuenta de usuario del dominio ORCH.com (Orch\SSOSvcUser). El usuario está configurado con permiso de acceso en el equipo SQL2 del dominio SQL.com. El usuario está configurado para transición de protocolo y delegación restringida en el dominio ORCH.com.  
  
- Otro usuario del dominio ORCH.com (Orch\TestAppUser) está establecido para ejecutar programas de prueba. Este usuario está también configurado para transición de protocolo y delegación restringida.  
  
## <a name="see-also"></a>Vea también  
 [Proceso de implementación](../core/deployment-process.md)