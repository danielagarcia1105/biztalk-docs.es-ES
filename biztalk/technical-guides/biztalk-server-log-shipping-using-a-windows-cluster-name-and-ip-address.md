---
title: BizTalk Server trasvase de registros mediante una dirección IP y el nombre del clúster de Windows | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 82ef6908-6009-4d06-8315-0bc85a0aad18
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a1b3df08da6753a7f936bfca54ecfb69b86d058c
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37023426"
---
# <a name="biztalk-server-log-shipping-using-a-windows-cluster-name-and-ip-address"></a>BizTalk Server trasvase de registros usando una dirección IP y el nombre del clúster de Windows
Es posible simplificar [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] trasvase de registros mediante el uso de dos instancias de un [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] clúster como los servidores de origen y destino en un [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] escenario de trasvase de registros. A continuación, en el caso de un evento de recuperación ante desastres, recuperación de base de datos se ha simplificado cambiando simplemente el nombre y los recursos de dirección IP asociados con el clúster [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] instancias tal como se describe a continuación. Cuando se usa este enfoque no hay ninguna necesidad de ejecutar el script UpdateDatabase.vbs tal como se describe en el tema [cómo restaurar bases de datos en el trabajo de copia de seguridad de BizTalk Server](../technical-guides/how-to-restore-databases-in-the-backup-biztalk-server-job.md) porque se ha modificado el nombre de la base de datos.  
  
> [!NOTE]
>  Para aumentar la tolerancia a errores para el clúster [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] instancias, el clúster [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] instancias deben estar separadas geográficamente.  
  
### <a name="to-implement-biztalk-server-log-shipping-using-a-windows-server-cluster-name-and-ip-address-resource"></a>Para implementar el registro de BizTalk Server recurso de dirección de envío mediante un nombre de clúster de Windows Server e IP  
  
1. Detener los servidores BizTalk Server de producción.  
  
2. Realizar una [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Iniciar restauración de trasvase de registros en la base de datos secundaria [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] clúster.  
  
3. Siga los pasos descritos en el tema [configurar BizTalk Server del trasvase de registros](../technical-guides/configuring-biztalk-server-log-shipping.md) para volver a configurar [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] trasvase de registros para que la base de datos secundaria [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] instancia de clúster es ahora el grupo de origen y el servidor principal [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]instancia en clúster es ahora el grupo de destino.  
  
4. Detenga la dirección IP y el recurso de nombre PublicSQLClustername en el servidor principal de la red [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] instancia en clúster.  
  
5. Configurar e iniciar los recursos de clúster de nombre PublicSQLClustername IP y la red en la base de datos secundaria [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] instancia en clúster.  
  
6. Inicie los servidores BizTalk Server de producción.  
  
7. Comprobar la restauración de trasvase de registros.  
  
8. Iniciar [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] relacionadas con servicios en el sitio de producción.  
  
   Después de realizar estos pasos, el grupo de BizTalk está señalando a la base de datos secundaria [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] instancia en clúster como se muestra en la ilustración siguiente.  
  
   La ilustración siguiente muestra cómo configurar [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] trasvase de registros mediante el uso de dos instancias agrupadas de [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] y pasar el nombre de clúster e IP de recurso de dirección.  
  
   ![Trasvase de registros de BizTalk mediante un nombre de clúster e IP](../technical-guides/media/5055689e-c26b-4077-a531-74a50fec1393.gif "5055689e-c26b-4077-a531-74a50fec1393")  
  
   **Implementación de trasvase de registros de BizTalk Server con el nombre del clúster de Windows Server y los recursos de dirección IP**  
  
## <a name="see-also"></a>Vea también  
 [Alta disponibilidad para bases de datos](../technical-guides/high-availability-for-databases.md)   
 [Trasvase de registros de configuración de BizTalk Server](../technical-guides/configuring-biztalk-server-log-shipping.md)   
 [Cómo restaurar bases de datos en el trabajo de copia de seguridad de BizTalk Server](../technical-guides/how-to-restore-databases-in-the-backup-biztalk-server-job.md)