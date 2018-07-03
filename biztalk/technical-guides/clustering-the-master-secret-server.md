---
title: Agrupación en clústeres el servidor secreto principal | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 14aa3622-8462-4ed9-abde-40090d4f96ff
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9c19702cfa7179399ee89f6799b65f1d2cec27a3
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36977301"
---
# <a name="clustering-the-master-secret-server"></a>Agrupación en clústeres el servidor secreto principal
El servicio de aplicación de BizTalk Server mantiene una dependencia codificada de forma rígida con el servicio de inicio de sesión único (SSO) empresarial que se instala con [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. El servicio SSO debe ser capaz de comunicarse con el servidor secreto principal para iniciar. Se recomienda agrupar el servicio de inicio de sesión único en el servidor secreto principal para proporcionar tolerancia a errores para el servidor secreto principal. Para obtener más información, consulte [opciones de instalación de SSO de alta disponibilidad](http://go.microsoft.com/fwlink/?LinkId=156838) (<http://go.microsoft.com/fwlink/?LinkId=156838>) en la Ayuda de BizTalk Server.  
  
## <a name="preparing-for-clustering-the-master-secret-server"></a>Preparación para la agrupación en clústeres el servidor secreto principal  
  
### <a name="deciding-whether-to-use-a-dedicated-cluster-or-the-sql-server-cluster"></a>Decidir entre usar un clúster dedicado o el clúster de SQL Server  
 Agrupación en clústeres de hardware es costosa. Para reducir los recursos de hardware para una solución de alta disponibilidad, puede agregar el servidor secreto principal como un recurso de clúster en su [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] clúster de base de datos. Si usas el [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] clúster de base de datos, se recomienda no colocar el servidor secreto principal en el mismo nodo activo como la base de datos de cuadro de mensajes. La base de datos de cuadro de mensajes es normalmente mayor que otras bases de datos. Aunque el servidor secreto principal no consume muchos recursos de hardware, es mejor moverlo a un nodo de clúster activo diferentes desde el nodo activo de base de datos de cuadro de mensajes.  
  
### <a name="clustering-the-sso-database"></a>Agrupación en clústeres de la base de datos SSO  
 El servidor secreto principal depende de la base de datos SSO. Para crear un inicio de sesión único de alta disponibilidad, debe agrupar la base de datos SSO. Para obtener más información sobre los clústeres de bases de datos de BizTalk, consulte [agrupación en clústeres el BizTalk Server2](../technical-guides/clustering-the-biztalk-server-databases2.md).  
  
### <a name="creating-domain-groups-and-accounts"></a>Creación de cuentas y grupos de dominio  
 Deberá configurar los siguientes grupos de dominio y cuentas antes de agrupar el servidor secreto principal:  
  
-   Crear grupos de dominio con los nombres de los administradores de SSO y administradores afiliados de SSO. Para crear una instancia agrupada del servicio SSO empresarial, debe crear los grupos de administradores de SSO y administradores afiliados de SSO como grupos de dominio.  
  
-   Cree o designe una cuenta de dominio que sea miembro del grupo Administradores de SSO de dominio. El Servicio SSO empresarial de cada nodo se configurará para iniciar sesión como esta cuenta de dominio. Esta cuenta debe tener el derecho "Iniciar sesión como servicio" en cada nodo del clúster. Esta cuenta también debe tener acceso de Control total para el clúster.  
  
## <a name="clustering-the-master-secret-server"></a>Agrupación en clústeres el servidor secreto principal  
 Estos son los pasos básicos para la agrupación en clústeres el servidor secreto principal:  
  
1. Instale y configure SSO empresarial en los nodos del clúster.  
  
2. Crear el recurso de SSO empresarial agrupado y los recursos dependientes.  
  
3. Restaurar el secreto principal en el segundo nodo del clúster. Si mueve el servidor secreto principal en el clúster, debe restaurar el secreto principal en el primer nodo de clúster.  
  
4. Ponga el grupo de clúster que contiene el servicio de inicio de sesión único en línea.  
  
5. Actualice el nombre de secreto maestro en la base de datos de administración.  
  
   Para obtener pasos detallados en el servidor secreto principal de agrupación en clústeres, consulte [cómo agrupar el servidor secreto principal](http://go.microsoft.com/fwlink/?LinkId=156839) (<http://go.microsoft.com/fwlink/?LinkId=156839>) en [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ayuda.  
  
## <a name="see-also"></a>Vea también  
 [Designación manual de un nuevo servidor de secreto maestro](../technical-guides/designating-a-new-master-secret-server-manually.md)